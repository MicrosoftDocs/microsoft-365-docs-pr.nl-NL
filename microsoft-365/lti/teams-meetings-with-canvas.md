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
ms.openlocfilehash: 946abaec52cb1c5060d5490b409758cf230a4e5a
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256877"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a>Vergaderingen Microsoft Teams Canvas gebruiken

> [!IMPORTANT]
> Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden. Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.

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
