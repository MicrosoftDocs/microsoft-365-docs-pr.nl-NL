---
title: Gebruik Microsoft Teams met Canvas
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sovaish
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: De Microsoft Teams met Canvas integreren
ms.openlocfilehash: e8ab45de84fe8325f6d5b349deb96aa831d54e36
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454683"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a>Gebruik Microsoft Teams met Canvas

Microsoft Teams lessen is een Learning app Hulpmiddelen interoperabiliteit (LTI) waarmee docenten en leerlingen eenvoudig kunnen navigeren tussen hun Learning Management System (LMS) en Teams. Gebruikers hebben rechtstreeks vanuit hun LMS toegang tot hun klasteams die aan hun cursus zijn gekoppeld.

## <a name="prerequisites-before-deployment"></a>Vereisten vóór implementatie

> [!NOTE]
> De huidige class Teams LTI ondersteunt alleen het synchroniseren van Canvas-gebruikers met Microsoft Azure Active Directory (AAD) in een beperkt bereik. 
> - Uw tenant moet een exacte overeenkomst hebben tussen een Canvas-veld (e-mail, gebruikers-id of SIS-id) en de UPN in Microsoft AAD. We werken eraan om de flexibiliteit voor de synchronisatiefunctionaliteit uit te breiden, maar in de tussentijd worden gebruikers in Canvas die niet zijn afgestemd op een UPN in AAD niet toegevoegd aan de Teams-klas gesynchroniseerd met Canvas. 
> - Er kan slechts één Microsoft-tenant worden gebruikt voor het toewijzen van gebruikers tussen Canvas en Microsoft.
> - U moet SDS uitschakelen voordat u de klasse Teams LTI gebruikt om duplicatie van groepen te voorkomen.

## <a name="microsoft-office-365-admin"></a>Microsoft Office 365 Beheerder

Voordat u de Microsoft Teams-integratie binnen Instructure Canvas beheert, is het belangrijk dat de **Microsoft-Teams-Sync-for-Canvas Azure-app** van Canvas is goedgekeurd door de Microsoft Office 365-beheerder van uw instelling in uw Microsoft Azure-tenant voordat u de canvasbeheerderconfiguratie voltooit.

1. Meld u aan bij Canvas.

2. Selecteer de **koppeling** Beheerder in de globale navigatie en selecteer vervolgens uw account.

3. Selecteer in de navigatie van de **beheerder de Instellingen** koppeling en vervolgens op het tabblad **Integraties.**

4. Schakel Microsoft Teams synchroniseren in door de schakelknop in te schakelen.

   ![teams-sync](media/teams-sync.png)

5. Voer uw Microsoft-tenantnaam en aanmeldingskenmerk in.

   Het aanmeldingskenmerk wordt gebruikt voor het koppelen van de Canvas-gebruiker aan een Azure Active Directory gebruiker.

6. Selecteer **Bijwerken Instellingen** eenmaal klaar.

7. Als u toegang wilt goedkeuren voor de **Microsoft-Teams-Sync-for-Canvas Azure-app** van Canvas, selecteert u de koppeling **Tenanttoegang verlenen.** U wordt omgeleid naar het Microsoft Identity Platform Admin Consent Endpoint.

   ![machtigingen](media/permissions.png)

8. Selecteer **Accepteren.**

## <a name="canvas-admin"></a>Canvasbeheerder

Stel de Microsoft Teams LTI 1.3-integratie in.

Als canvasbeheerder moet u de LTI-app Microsoft Teams in uw omgeving toevoegen. Noteer de LTI-client-id voor de app.

 - Microsoft Teams klassen - 170000000000570

1. Access **Admin settings**  >  **Apps**.

2. Selecteer **+ App** om de Teams LTI-apps toe te voegen.

   ![externe apps](media/external-apps.png)

3. Selecteer **Op client-id** voor configuratietype.

   ![app toevoegen](media/add-app.png)

4. Voer de opgegeven client-id in en selecteer **Verzenden.**

   U ziet de naam van Microsoft Teams LTI-app voor de client-id ter bevestiging.

5. Kies **Installeren**.

   De Microsoft Teams klassen LTI-app wordt toegevoegd aan de lijst met externe apps.
   
## <a name="enabling-the-lti-app-for-canvas-courses"></a>De LTI-app voor canvascursussen inschakelen

Als u de LTI-app in een cursus wilt gebruiken, moet een docent van de canvascursus integratiessynchronisatie inschakelen. Elke cursus moet door een docent zijn ingeschakeld voor het maken van een overeenkomend team. er is geen globaal mechanisme voor het maken van teams. Dit is ontworpen als een voorzorgsmaatregel om te voorkomen dat ongewenste teams worden gemaakt.

Verwijs uw docenten naar de documentatie voor docenten [voor](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) het inschakelen van de LTI-app voor elke cursus en het voltooien van de integratie-instelling.
