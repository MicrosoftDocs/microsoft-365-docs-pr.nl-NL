---
title: Vertrouwelijkheidslabels gebruiken als voorwaarden in DLP-beleid
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: meer informatie over de services en itemtypen waarvoor u gevoeligheidslabels kunt gebruiken als voorwaarden in DLP-beleid
ms.openlocfilehash: 94d5e9f53471f6113dcc755995a3f94e95a58e53
ms.sourcegitcommit: 50f484fc501d81506a714b127a56a6979888d849
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2021
ms.locfileid: "52779841"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies"></a>Vertrouwelijkheidslabels gebruiken als voorwaarden in DLP-beleid

U kunt [vertrouwelijkheidslabels](sensitivity-labels.md) gebruiken als voorwaarde in DLP-beleid voor deze locaties:

- Exchange Online-e-mailberichten
- SharePoint Online
- OneDrive voor Bedrijven-sites
- Windows 10-apparaten

Gevoeligheidslabels worden weergegeven als een optie in de lijst **Inhoud bevat**.

> [!div class="mx-imgBorder"]
> ![gevoeligheidslabel als voorwaarde](../media/dlp-sensitivity-label-as-a-condition.png)

> [!IMPORTANT]
> **Gevoeligheidslabels** als voorwaarde zijn niet beschikbaar als u **Chat- en kanaalberichten in Teams** hebt geselecteerd als een locatie om het DLP-beleid toe te passen.


## <a name="supported-items-scenarios-and-policy-tips"></a>Ondersteunde items, scenario's en beleidstips

U kunt gevoeligheidslabels gebruiken als voorwaarden op deze items en in deze scenario's.

### <a name="supported-items"></a>Ondersteunde items

|Service  |Itemtype  |Beschikbaar voor beleidstip  |Afdwingbaar  |
|---------|---------|---------|---------|
|Exchange    |e-mailbericht         |ja         |ja         |
|Exchange    |e-mailbijlage         |nee         |ja *         |
|SharePoint Online     |items in SharePoint Online         |ja         |ja         |
|OneDrive voor Bedrijven     |items         |ja         |ja         |
|Teams     |Teams en kanaalberichten         |niet van toepassing         |niet van toepassing         |
|Teams     |bijlagen         |ja **         |ja **         |
|Windows 10-apparaten     |items         |ja         |ja         |
|MCAS (preview-versie) |items         |ja         |ja         |

\* DLP-detectie van e-mailbijlagen die als vertrouwelijk zijn gemarkeerd, wordt alleen ondersteund voor Office-bestandstypen.

\** Bijlagen die via een privéchat of kanalen in Teams worden verzonden, worden automatisch geüpload naar OneDrive voor Bedrijven en SharePoint. Dus als SharePoint Online of OneDrive voor Bedrijven als locaties zijn opgenomen in uw DLP-beleid, worden gelabelde bijlagen die worden verzonden in Teams automatisch opgenomen in het bereik van deze voorwaarde. Teams als locatie hoeft niet te zijn geselecteerd in het DLP-beleid.

> [!NOTE]
> De mogelijkheid van DLP om gevoeligheidslabels te detecteren in SharePoint en OneDrive voor Bedrijven is beperkt. Raadpleeg [Vertrouwelijkheidslabels inschakelen voor Office-bestanden in SharePoint en OneDrive](sensitivity-labels-sharepoint-onedrive-files.md#limitations) voor meer informatie.

### <a name="supported-scenarios"></a>Ondersteunde scenario's

- Een DLP-beheerder kan een lijst met alle gevoeligheidslabels in de tenant zien wanneer ze ervoor kiezen om één of meer gevoeligheidslabels als voorwaarde op te nemen.

- Het gebruik van gevoeligheidslabels als voorwaarde wordt ondersteund voor alle werkbelastingen, zoals aangegeven in de bovenstaande ondersteuningsmatrix.

- DLP-beleidstips blijven zichtbaar in alle werkbelastingen (behalve Outlook Win32) voor DLP-beleid dat een gevoeligheidslabel als voorwaarde bevat.

- Gevoeligheidslabels worden ook weergegeven als onderdeel van het e-mailbericht met het incidentenrapport als een DLP-beleid met een gevoeligheidslabel als voorwaarde overeenkomt.

- Gevoeligheidslabeldetails worden ook weergegeven in het auditlogboek met DLP-regelovereenkomsten voor een DLP-beleid dat een gevoeligheidslabel als voorwaarde bevat.


### <a name="support-policy-tips"></a>Beleidstips ondersteunen


|Werkbelasting  |Ondersteunde/niet-ondersteunde beleidstips  |
|---------|---------|
|OWA |    ondersteund     |
|Outlook Win 32    |  niet ondersteund       |
|SharePoint   |   ondersteund      |
|OneDrive voor Bedrijven    |    ondersteund     |
|eindpuntapparaten   |  niet ondersteund       |
