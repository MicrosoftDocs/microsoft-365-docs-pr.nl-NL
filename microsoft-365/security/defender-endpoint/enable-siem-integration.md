---
title: SIEM-integratie inschakelen in Microsoft Defender voor Eindpunt
description: Schakel SIEM-integratie in om detecties te ontvangen in uw siem-oplossing (Security Information and Event Management).
keywords: siem connector, siem, connector, beveiligingsgegevens en gebeurtenissen inschakelen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 337eb28b7e4b4a7c57b63ff45fb1cea81db43604
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060365"
---
# <a name="enable-siem-integration-in-microsoft-defender-for-endpoint"></a>SIEM-integratie inschakelen in Microsoft Defender voor Eindpunt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)


>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink) 

Schakel beveiligingsgegevens en SIEM-integratie (Security Information And Event Management) in, zodat u detecties kunt halen uit het Microsoft Defender-beveiligingscentrum. Detecties trekken met uw SIEM-oplossing of door rechtstreeks verbinding te maken met de REST-API voor detecties.

>[!NOTE]
>- [Microsoft Defender for Endpoint Alert](alerts.md) is samengesteld uit een of meer detecties.
>- [Microsoft Defender voor eindpuntdetectie](api-portal-mapping.md) is samengesteld uit de verdachte gebeurtenis op het apparaat en de bijbehorende waarschuwingsgegevens.
>- De Microsoft Defender for Endpoint Alert API is de nieuwste API voor waarschuwingsverbruik en bevat een gedetailleerde lijst met verwante gegevens voor elke waarschuwing. Zie Waarschuwingsmethoden en [-eigenschappen](alerts.md) en [Lijstwaarschuwingen](get-alerts.md)voor meer informatie.

## <a name="prerequisites"></a>Vereisten

- De gebruiker die de instelling activeert, moet machtigingen hebben om een app te maken in Azure Active Directory (AAD). Dit is iemand met de volgende rollen: 

  - Beveiligingsbeheerder en globale beheerder
  - Cloudtoepassingsbeheerder
  - Toepassingsbeheerder
  - Eigenaar van de service-principal

- Tijdens de eerste activering wordt een pop-upscherm weergegeven waarin referenties moeten worden ingevoerd. Zorg ervoor dat u pop-ups voor deze site toestaat.

## <a name="enabling-siem-integration"></a>SIEM-integratie inschakelen 
1. Selecteer in het navigatiedeelvenster **Instellingen**  >  **SIEM**.

    ![Afbeelding van SIEM-integratie in menu Instellingen1](images/enable_siem.png)

    >[!TIP]
    >Als er een fout is opgetreden bij het inschakelen van de SIEM-verbindingstoepassing, controleert u de pop-upblokkeringsinstellingen van uw browser. Mogelijk wordt het nieuwe venster geblokkeerd wanneer u de functie inschakelen. 

2. Selecteer **SIEM-integratie inschakelen.** Hiermee activeert u de sectie toegangsgegevens van **de SIEM-verbindingslijn** met vooraf ingevulde waarden en wordt er een toepassing gemaakt onder uw Azure Active Directory -tenant (Azure AD).

    > [!WARNING]
    >Het clientgeheim wordt slechts eenmaal weergegeven. Zorg ervoor dat u een kopie ervan op een veilige plaats houdt.<br>
     

    ![Afbeelding van SIEM-integratie in het menu Instellingen2](images/siem_details.png)

3. Kies het SIEM-type dat u in uw organisatie gebruikt.

   > [!NOTE]
   > Als u HP ArcSight selecteert, moet u deze twee configuratiebestanden opslaan:<br>
   > - WDATP-connector.jsonparser.properties
   > - WDATP-connector.properties <br>

   Als u rechtstreeks verbinding wilt maken met de DETECTIES REST API via programmatische toegang, kiest u **Generic API.**

4. Kopieer de afzonderlijke waarden of selecteer **Details opslaan in bestand om** een bestand te downloaden dat alle waarden bevat.

5. Selecteer **Tokens genereren** om toegang te krijgen en token te vernieuwen.
  
   > [!NOTE]
   > U moet elke 90 dagen een nieuw vernieuwingsken genereren. 

6. Volg de instructies voor het [maken van een Azure AD-app-registratie](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp) voor Microsoft Defender voor Eindpunt en wijs de juiste machtigingen toe om waarschuwingen te lezen.

U kunt nu doorgaan met het configureren van uw SIEM-oplossing of verbinding maken met de DETECTIES REST API via programmatische toegang. U moet de tokens gebruiken bij het configureren van uw SIEM-oplossing, zodat deze detecties kan ontvangen van het Microsoft Defender-beveiligingscentrum.

## <a name="integrate-microsoft-defender-for-endpoint-with-ibm-qradar"></a>Microsoft Defender voor eindpunt integreren met IBM QRadar 
U kunt IBM QRadar zo configureren dat detecties worden verzameld van Microsoft Defender voor Eindpunt. Zie IBM Knowledge Center voor [meer informatie.](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)

## <a name="see-also"></a>Zie ook
- [HP ArcSight configureren om Microsoft Defender te gebruiken voor eindpuntdetecties](configure-arcsight.md)
- [Microsoft Defender voor eindpuntdetectievelden](api-portal-mapping.md)
- [Microsoft Defender voor eindpuntdetecties trekken met REST API](pull-alerts-using-rest-api.md)
- [Problemen met de integratie van SIEM-hulpprogramma's oplossen](troubleshoot-siem.md)
