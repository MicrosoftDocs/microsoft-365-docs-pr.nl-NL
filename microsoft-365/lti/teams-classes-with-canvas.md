---
title: Gebruik Microsoft Teams met Canvas
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: De Microsoft Teams met Canvas integreren
ms.openlocfilehash: 1a16d6a4f5e0cfbb592c335163bb4e33fd3c1301
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821880"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a>Gebruik Microsoft Teams met Canvas

> [!IMPORTANT]
> Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden. Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.

Microsoft Teams lessen is een LTI-app (Learning Tools Interoperability) waarmee docenten en leerlingen eenvoudig kunnen navigeren tussen hun LMS (Learning Management System) en Teams. Gebruikers hebben rechtstreeks vanuit hun LMS toegang tot hun klasteams die aan hun cursus zijn gekoppeld.

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
