---
title: Toegang tot Microsoft Threat Protection-Api's met behulp van gebruikersnamen
description: Meer informatie over het openen van Microsoft Threat Protection-Api's met behulp van gebruikersnamen
keywords: toegang, in naam van gebruiker, API, toepassing, gebruiker, toegangstoken, token,
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: a62d90004d00e8c553f1b011e77b871df7cd94f4
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197795"
---
# <a name="access-microsoft-threat-protection-apis-on-behalf-of-user"></a>Toegang tot Api's voor Microsoft Threat Protection namens een gebruiker

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Threat Protection

>[!IMPORTANT] 
>Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd. Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.


Op deze pagina wordt beschreven hoe u een toepassing maakt om via een programma toegang te krijgen tot Microsoft Threat Protection namens een gebruiker.

Zie [een app maken om toegang te krijgen tot Microsoft Threat Protection zonder een gebruiker](api-create-app-web.md)als u Microsoft Threat Protection zonder een gebruiker via programmacode moet openen.

Als u niet zeker weet welke toegang u nodig hebt, raadpleegt u de [Access-api's voor Microsoft Threat Protection](api-access.md).

Microsoft Threat Protection geeft veel van zijn gegevens en acties getoond via een set programmeer Api's. Met deze Api's kunt u werkstromen en innoveren automatiseren op basis van de mogelijkheden van Microsoft Threat Protection. Voor API-toegang is OAuth 2.0-authenticatie vereist. Voor meer informatie raadpleegt u [OAuth 2,0 Authorization code flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

In het algemeen dient u de volgende stappen uit te voeren om de Api's te gebruiken:
- Een AAD-toepassing maken
- Een toegangstoken verkrijgen met deze toepassing
- Het token gebruiken om toegang te krijgen tot de Microsoft Threat Protection API

Op deze pagina wordt uitgelegd hoe u een AAD-toepassing maakt, een toegangstoken krijgt voor Microsoft Threat Protection en het token valideert.

>[!NOTE]
> Wanneer u de Microsoft Threat Protection-API namens een gebruiker opent, hebt u de juiste machtigingen voor de toepassing en de gebruikersmachtigingen nodig.


>[!TIP]
> Als u gemachtigd bent om een actie uit te voeren in de portal, hebt u de machtiging om de actie uit te voeren in de API.

## <a name="create-an-app"></a>Een app maken

1. Meld u aan bij [Azure](https://portal.azure.com) met een gebruiker die de rol van **globale beheerder** heeft.

2. Ga naar de **Azure Active Directory**-  >  **app registraties**  >  **nieuwe registratie**. 

   ![Afbeelding van Microsoft Azure en navigatie naar toepassing registreren](../../media/atp-azure-new-app2.png)

3. Voer in de registratie van de volgende gegevens in en klik vervolgens op **registeren**.

   ![Afbeelding van het venster toepassing maken](../../media/nativeapp-create2.PNG)

   - **Naam:** Naam van de toepassing
   - **Type toepassing:** Openbare client
   - **URI omleiden:**https://portal.azure.com

4. Als u de app wilt gebruiken voor toegang tot Microsoft Threat Protection en de machtigingen voor deze persoon wilt toewijzen, selecteert u op de Toepassingspagina **API-machtigingen**de optie API-  >  api's**toevoegen**  >  **Mijn organisatie gebruikt** >, typt u **Microsoft Threat Protection**en selecteert u vervolgens **Microsoft Threat Protection**.

    >[!NOTE]
    > Microsoft Threat Protection wordt niet weergegeven in de oorspronkelijke lijst. U moet de naam ervan beginnen te schrijven in het tekstvak om de naam weer te geven.

      ![Afbeelding van API-toegang en API-selectie](../../media/apis-in-my-org-tab.PNG)

    - Kies **gedelegeerde machtigingen** > Kies de relevante machtigingen voor uw scenario, bijvoorbeeld **incident. Read**, en selecteer vervolgens **machtigingen toevoegen**.

      ![Afbeelding van API-toegang en API-selectie](../../media/request-api-permissions-delegated.PNG)

     >[!IMPORTANT]
     >U moet de relevante machtigingen selecteren. 

    -  Om te bepalen welke machtigingen u nodig hebt, raadpleegt u de sectie **machtigingen** in de API die u wilt bellen.

    - Klik op **toestemming verlenen**

      >[!NOTE]
      >Telkens wanneer u toestemming toevoegt, moet u op **toestemming verlenen** om de nieuwe machtiging van kracht te laten worden.

      ![Afbeelding van machtiging verlenen](../../media/grant-consent-delegated.PNG)

6. Noteer de toepassings-ID en uw Tenant-ID:

   - Ga op de pagina toepassing naar **overzicht** en kopieer de volgende opties:

   ![Afbeelding van gemaakte app-id](../../media/app-and-tenant-ids.png)


## <a name="get-an-access-token-using-powershell"></a>Een toegangstoken verkrijgen met PowerShell

```
#Install the ADAL.PS package if it's not installed.
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps }

$authority = "https://login.windows.net/{tenant-id}" # replace {tenant-id} with your tenant ID.

$clientId = "{application-id}" #replace {application-id} with your application ID.

$redirectUri = "{redirect-uri}" # replace {redirect-uri} with your application redirect URI.

$resourceUrl = "https://api.security.microsoft.com"

$response = Get-ADALToken -Resource $resourceUrl -ClientId $clientId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip
$response.AccessToken
```

## <a name="related-topics"></a>Verwante onderwerpen
- [Toegang tot de Microsoft Threat Protection-Api's](api-access.md)
- [Toegang tot Microsoft Threat Protection met toepassingscontext](api-create-app-web.md)
