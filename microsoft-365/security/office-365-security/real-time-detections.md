---
title: Basisbeginselen voor bedreigingsverkenner en realtimedetectie in Microsoft Defender voor Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Gebruik Explorer- of realtimedetecties om bedreigingen efficiënt te onderzoeken en te beantwoorden.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4d0a9ba7ee40c8ad97df745a20d6b5b3314bb3d8
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083186"
---
# <a name="explorer-and-real-time-detections-basics"></a>Basisprincipes van Explorer- en realtimedetecties

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In dit artikel:

- [Verschillen tussen Explorer- en realtimedetecties](#differences-between-explorer-and-real-time-detections)
- [Vereiste licenties en machtigingen](#required-licenses-and-permissions)

> [!NOTE]
> Dit maakt deel uit van een reeks van drie artikelen over **Verkenner (ook** wel Threat Explorer genoemd), **e-mailbeveiliging** **en** basisprincipes van Explorer- en **realtimedetecties** (zoals verschillen tussen de hulpprogramma's en machtigingen die nodig zijn om ze te kunnen gebruiken). De andere twee artikelen in deze reeks zijn [Bedreigingsjacht in Verkenner](threat-hunting-in-threat-explorer.md) en [E-mailbeveiliging met Explorer.](email-security-in-microsoft-defender.md)

In dit artikel wordt uitgelegd wat het verschil is tussen Explorer- en realtimedetectierapportage en de benodigde licenties en machtigingen.

Als uw organisatie [Microsoft Defender](defender-for-office-365.md)voor Office 365 heeft en u de machtigingen [hebt,](#required-licenses-and-permissions)kunt u **Explorer** (ook wel **Threat Explorer** genoemd) of **realtimedetecties** gebruiken om bedreigingen te detecteren en te corrigeren.

Ga in Microsoft 365 Defender portal ( ) naar E-mail & samenwerking en kies explorer of <https://security.microsoft.com>   **realtime detecties.** 

Met deze hulpmiddelen kunt u het volgende doen:

- Bekijk malware die is gedetecteerd door Microsoft 365 beveiligingsfuncties.
- Bekijk phishing-URL en klik op vonnisgegevens.
- Start een geautomatiseerd onderzoek en antwoordproces vanuit een weergave in Explorer.
- Onderzoek schadelijke e-mail en meer.

Zie E-mailbeveiliging [met Explorer voor meer informatie.](email-security-in-microsoft-defender.md)

## <a name="differences-between-explorer-and-real-time-detections"></a>Verschillen tussen Explorer- en realtimedetecties

- *Realtime detecties* is een rapportagehulpmiddel dat beschikbaar is in Defender Office 365 plan 1. *Threat Explorer* is een hulpprogramma voor het zoeken en herstellen van bedreigingen dat beschikbaar is in Defender Office 365 plan 2.
- Met het rapport Realtimedetecties kunt u detecties in realtime bekijken. Threat Explorer doet dit ook, maar biedt extra details voor een bepaalde aanval, zoals het markeren van aanvalscampagnes, [](automated-investigation-response-office.md)en biedt beveiligingsteams de mogelijkheid om bedreigingen te corrigeren (waaronder het starten van een geautomatiseerd onderzoek en antwoordonderzoek).
- Een *weergave Alle e-mail* is beschikbaar in Threat Explorer, maar is niet opgenomen in het rapport Realtimedetecties.
- Uitgebreide filtermogelijkheden en herstelacties zijn opgenomen in Threat Explorer. Zie Microsoft Defender for [Office 365 Service Description: Feature availability across Defender for Office 365 plans voor meer informatie.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)

## <a name="required-licenses-and-permissions"></a>Vereiste licenties en machtigingen

U moet [Microsoft Defender hebben om Office 365](defender-for-office-365.md) explorer of realtime detecties te kunnen gebruiken:

- Explorer is alleen opgenomen in Defender voor Office 365 Plan 2.
- Het realtimedetectierapport is opgenomen in Defender voor Office 365 Plan 1.

Beveiligingsbewerkingsteams moeten licenties toewijzen voor alle gebruikers die moeten worden beveiligd door Defender voor Office 365 en zich ervan bewust zijn dat explorer- en realtimedetecties detectiegegevens weergeven voor gelicentieerde gebruikers.

Als u *Explorer-* of realtimedetecties wilt bekijken en gebruiken, hebt u de volgende machtigingen nodig:

- In Defender voor Office 365:
  - Organisatiebeheer
  - Beveiligingsbeheerder (dit kan worden toegewezen in het Azure Active Directory beheercentrum ( <https://aad.portal.azure.com> )
  - Beveiligingslezer
- In Exchange Online:
  - Organisatiebeheer
  - View-Only Organisatiebeheer
  - View-Only Geadresseerden
  - Compliancebeheer

Zie de volgende artikelen voor meer informatie over rollen en machtigingen:

- [Machtigingen in de Microsoft 365 Defender-portal](permissions-microsoft-365-security-center.md)
- [Machtigingen in Exchange Online](/e/exchange/permissions-exo/permissions-exo)

## <a name="more-information"></a>Meer informatie

- [Threat Explorer verzamelt e-mailgegevens op de pagina e-mailentiteit](mdo-email-entity-page.md)
- [Schadelijke e-mail zoeken en onderzoeken die is bezorgd](investigate-malicious-email-that-was-delivered.md)
- [Schadelijke bestanden weergeven die zijn gedetecteerd in SharePoint Online, OneDrive en Microsoft Teams](mdo-for-spo-odb-and-teams.md)
- [Statusrapport bedreigingsbeveiliging](view-email-security-reports.md#threat-protection-status-report)
- [Geautomatiseerd onderzoek en antwoord in Microsoft Threat Protection](automated-investigation-response-office.md)
