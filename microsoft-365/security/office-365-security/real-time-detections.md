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
ms.openlocfilehash: 7ab7b5731d121106d930868b03330d4ac7befd77
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300123"
---
# <a name="threat-explorer-and-real-time-detections-basics"></a>Bedreigingsverkenner en basisbeginselen van realtime detecties

In dit artikel:

- [Verschillen tussen Threat Explorer en Realtime detecties](#differences-between-threat-explorer-and-real-time-detections)<br/>
- [Vereiste licenties en machtigingen](#required-licenses-and-permissions)

> [!NOTE]
> Dit maakt deel uit van een reeks van drie artikelen over **Threat Explorer (Explorer),** **e-mailbeveiliging** **en** explorer- en **realtimedetecties** (zoals verschillen tussen de hulpprogramma's en machtigingen die nodig zijn om ze te kunnen gebruiken). De andere twee artikelen in deze reeks zijn [Threat hunting in Threat Explorer](threat-hunting-in-threat-explorer.md) en [E-mailbeveiliging met Threat Explorer.](email-security-in-microsoft-defender.md)

In dit artikel wordt uitgelegd wat het verschil is tussen het verkennen van bedreigingen en realtime detecties en de benodigde licenties en machtigingen.

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Als uw organisatie [Microsoft Defender](defender-for-office-365.md)voor Office 365 heeft en u de machtigingen [hebt,](#required-licenses-and-permissions)kunt u **Threat Explorer** (explorer) of **realtimedetecties** gebruiken om bedreigingen te detecteren en te corrigeren.

Ga in & **Beveiligingscentrum** naar **Bedreigingsbeheer** en kies **explorer**  of **realtime detecties.**

<br>

****

|Met Microsoft Defender voor Office 365 Plan 2 ziet u:|Met Microsoft Defender voor Office 365 plan 1 ziet u:|
|---|---|
|![Bedreigingsverkenner](../../media/threatmgmt-explorer.png)|![Detecties in realtime](../../media/threatmgmt-realtimedetections.png)|
|

Met deze hulpmiddelen kunt u het volgende doen:

- Bekijk malware die is gedetecteerd door Microsoft 365 beveiligingsfuncties.
- Bekijk phishing-URL en klik op vonnisgegevens.
- Start een geautomatiseerd onderzoek en antwoordproces vanuit een weergave in Explorer.
- Onderzoek schadelijke e-mail en meer.

Zie E-mailbeveiliging [met Threat Explorer voor meer informatie.](email-security-in-microsoft-defender.md)

## <a name="differences-between-threat-explorer-and-real-time-detections"></a>Verschillen tussen Threat Explorer en Realtime detecties

- *Realtime detecties* is een rapportagehulpmiddel dat beschikbaar is in Defender Office 365 plan 1. *Threat Explorer* is een hulpprogramma voor het zoeken en herstellen van bedreigingen dat beschikbaar is in Defender Office 365 plan 2.
- Met het rapport Realtimedetecties kunt u detecties in realtime bekijken. Threat Explorer doet dit ook, maar biedt extra details voor een bepaalde aanval, zoals het markeren van aanvalscampagnes, [](automated-investigation-response-office.md)en biedt beveiligingsteams de mogelijkheid om bedreigingen te corrigeren (waaronder het starten van een geautomatiseerd onderzoek en antwoordonderzoek).
- Een *weergave Alle e-mail* is beschikbaar in Threat Explorer, maar is niet opgenomen in het rapport Realtimedetecties.
- Uitgebreide filtermogelijkheden en herstelacties zijn opgenomen in Threat Explorer. Zie Microsoft Defender for [Office 365 Service Description: Feature availability across Defender for Office 365 plans voor meer informatie.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)

## <a name="required-licenses-and-permissions"></a>Vereiste licenties en machtigingen

U moet [Microsoft Defender hebben om Office 365](defender-for-office-365.md) explorer of realtime detecties te kunnen gebruiken:

- Explorer is echter alleen opgenomen in Defender voor Office 365 Plan 2.
- Het realtimedetectierapport is opgenomen in Defender voor Office 365 Plan 1.

Beveiligingsbewerkingsteams moeten licenties toewijzen voor alle gebruikers die moeten worden beveiligd door Defender voor Office 365 en zich ervan bewust zijn dat explorer- en realtimedetecties detectiegegevens weergeven voor gelicentieerde gebruikers.

Als u *Explorer-* of realtimedetecties wilt bekijken en gebruiken, moet u het volgende hebben:

- Voor het Beveiligings- & compliancecentrum:

  - Organisatiebeheer
  - Beveiligingsbeheerder (dit kan worden toegewezen in het Azure Active Directory beheercentrum ( <https://aad.portal.azure.com> )
  - Beveiligingslezer

- Voor Exchange Online:

  - Organisatiebeheer
  - View-Only Organisatiebeheer
  - View-Only Geadresseerden
  - Compliancebeheer

Zie de volgende bronnen voor meer informatie over rollen en machtigingen:

- [Machtigingen in het Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md)
- [Functiemachtigingen in Exchange Online](/exchange/permissions-exo/feature-permissions)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a>Meer informatie
- [Threat Explorer verzamelt e-mailgegevens op de pagina e-mailentiteit](mdo-email-entity-page.md)
- [Schadelijke e-mail zoeken en onderzoeken die is bezorgd](investigate-malicious-email-that-was-delivered.md)
- [Schadelijke bestanden weergeven die zijn gedetecteerd in SharePoint Online, OneDrive en Microsoft Teams](mdo-for-spo-odb-and-teams.md)
- [Statusrapport bedreigingsbeveiliging](view-email-security-reports.md#threat-protection-status-report)
- [Geautomatiseerd onderzoek en antwoord in Microsoft Threat Protection](automated-investigation-response-office.md)