---
title: Vergaderingen Microsoft Teams Canvas gebruiken
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
description: Vergaderingen Microsoft Teams canvas integreren
ms.openlocfilehash: 54dd3cc2709933ffb7b7d5fecdd181fad2abb42b
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454671"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a>Vergaderingen Microsoft Teams Canvas gebruiken

Microsoft Teams vergaderingen is een app Learning Tools Interoperability (LTI) waarmee docenten en leerlingen eenvoudig kunnen navigeren tussen hun Learning Management System (LMS) en Teams. Gebruikers hebben rechtstreeks vanuit hun LMS toegang tot hun klasteams die aan hun cursus zijn gekoppeld.

## <a name="microsoft-office-365-admin"></a>Microsoft Office 365 Beheerder

Voordat u de Microsoft Teams-integratie binnen Instructure Canvas beheert, is het belangrijk dat de **Microsoft-Teams-Sync-for-Canvas Azure-app** van Canvas is goedgekeurd door de Microsoft Office 365-beheerder van uw instelling in uw Microsoft Azure-tenant voordat u de canvasbeheerderconfiguratie voltooit.

1. Meld u aan bij Canvas.

2. Selecteer de **koppeling** Beheerder in de globale navigatie en selecteer vervolgens uw account.

3. Selecteer in de navigatie van de **beheerder de Instellingen** koppeling en vervolgens op het tabblad **Integraties.**

4. Voer uw Microsoft-tenantnaam en aanmeldingskenmerk in.

   Het aanmeldingskenmerk wordt gebruikt voor het koppelen van de Canvas-gebruiker aan een Azure Active Directory gebruiker.

5. Selecteer **Bijwerken Instellingen** eenmaal klaar.

6. Als u toegang wilt goedkeuren voor de **Microsoft-Teams-Sync-for-Canvas Azure-app** van Canvas, selecteert u de koppeling **Tenanttoegang verlenen.** U wordt omgeleid naar het Microsoft Identity Platform Admin Consent Endpoint.

   ![machtigingen](media/permissions.png)

7. Selecteer **Accepteren.**

8. Schakel de Microsoft Teams synchronisatie in door de schakelknop in te schakelen.

   ![teams-sync](media/teams-sync.png)

## <a name="canvas-admin"></a>Canvasbeheerder

Stel de Microsoft Teams LTI 1.3-integratie in.

Als canvasbeheerder moet u de LTI-app voor vergaderingen Microsoft Teams in uw omgeving toevoegen. Noteer de LTI-client-id voor de app.

 - Microsoft Teams vergaderingen - 170000000000703

1. Access **Admin settings**  >  **Apps**.

2. Selecteer **+ App** om de Teams LTI-apps toe te voegen.

   ![externe apps](media/external-apps.png)

3. Selecteer **Op client-id** voor configuratietype.

   ![app toevoegen](media/add-app.png)

4. Voer de opgegeven client-id in en selecteer **Verzenden.**

   U ziet de naam van Microsoft Teams LTI-app voor de client-id ter bevestiging.

5. Kies **Installeren**.

   De Microsoft Teams LTI-app voor vergaderingen wordt toegevoegd aan de lijst met externe apps.
   
## <a name="enable-for-canvas-courses"></a>Canvascursussen inschakelen

Als u de LTI in een cursus wilt gebruiken, moet een docent van de canvascursus de synchronisatie van de integraties inschakelen. Elke cursus moet door een docent zijn ingeschakeld om een overeenkomstige Teams te maken; er is geen globaal mechanisme voor het Teams maken. Dit is ontworpen uit voorzorg om te voorkomen dat ongewenste Teams worden gemaakt.

Raadpleeg uw docenten voor documentatie over [docenten](https://support.microsoft.com/en-us/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) voor het inschakelen van de LTI voor elke cursus en het afronden van de integratie-instelling.
