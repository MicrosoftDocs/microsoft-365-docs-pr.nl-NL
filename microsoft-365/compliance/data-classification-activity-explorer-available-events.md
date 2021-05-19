---
title: In Activiteitenverkenner gerapporteerde labelacties
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: vermelding van labelactiviteiten die beschikbaar zijn in activity explorer.
ms.openlocfilehash: d4f6884ad39b16aeb0345f0c976d6ad87f03c05a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52532252"
---
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a>Labeling-activiteiten die beschikbaar zijn in Activiteitenverkenner

## <a name="sensitivity-label-applied"></a>Gevoeligheidslabel toegepast

Deze gebeurtenis wordt gegenereerd telkens als een document zonder label wordt gelabeld of een e-mailbericht wordt verzonden met een gevoeligheidslabel. 

- Het wordt vastgelegd op het moment van opslaan in Office native toepassingen en webtoepassingen. 
- De gegevens worden vastgelegd op het moment dat de invoegvoegingen van Azure Information Protection worden gebruikt. 
- Acties voor het upgraden en downgraden van labels kunnen ook worden gecontroleerd via het *veld labeltype en* het filter.   


|Source  |Gerapporteerd in activiteitsverkenner | Opmerking  |
|---------|---------|---------|
| Word, Excel, PowerPoint|ja |
|Outlook| ja |van Win 32 |
|SharePoint online, OneDrive|ja | |
|Exchange        |ja         | |
|Azure Information Protection (AIP) unified client en AIP unified scanner |ja |de nieuwe *labelactie* AIP is in kaart gebracht aan het label dat *is toegepast* in activiteitsverkenner   |
|Microsoft information protection (MIP) SDK         |ja|de nieuwe *labelactie* AIP is in kaart gebracht aan het label dat *is toegepast* in activiteitsverkenner|
|Rights Management Service (RMS)         |niet van toepassing         | |
|Power BI bureaublad en web        | nee| toegankelijk in de Microsoft 365 auditlogboeken         |
|Microsoft Cloud App Security (MCAS)         |nee|         |

## <a name="sensitivity-label-changed"></a>Gevoeligheidslabel gewijzigd

Deze gebeurtenis wordt gegenereerd telkens wanneer een gevoeligheidslabel wordt bijgewerkt in het document of e-mailbericht.

- Voor de AIP Unified-client, Unified Scanner en MIP SDK-bronnen is het *AIP-upgradelabel* en *downgradelabelactiekaarten* naar het label Activity Explorer *gewijzigd*

- Het wordt vastgelegd op het moment van opslaan in Office native toepassingen en webtoepassingen. 
- Het wordt vastgelegd op het moment van het optreden in geïntegreerde client-invoegingen en scanners voor Azure Information Protection
- Acties voor het upgraden en downgraden van labels kunnen ook worden gecontroleerd via het *veld labeltype en* het filter. De *tekst* van de uitvulling wordt ook vastgelegd, behalve SharePoint Online en OneDrive.
- Gevoeligheidslabels die zijn uitgevoerd in Office native apps op Outlook verzamelt de laatste actie die is gegenereerd voordat acties voor het opslaan/verzenden van bestanden per e-mail zijn gegenereerd. Als de gebruiker bijvoorbeeld het label voor een e-mail meerdere keren wijzigt voordat deze wordt verzonden, wordt het laatste label dat is gevonden in de e-mail wanneer deze wordt verzonden vastgelegd in het auditlogboek en vervolgens gerapporteerd in activity explorer. 


|Source  |Gerapporteerd in activiteitsverkenner|Opmerking  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |ja         |
|Outlook         |ja         |Win 32|
|SharePoint Online, OneDrive         |ja         |
|Exchange         |ja         |
|AIP-geïntegreerde client         |ja         |
|Geïntegreerde AIP-scanner         |ja         |
|MIP SDK         |ja         |
|RMS-service         |niet van toepassing         |
|Power BI bureaublad en web         |nee         |toegankelijk in de Microsoft 365 auditlogboeken |
|MCAS     |nee         |         |

## <a name="sensitivity-label-removed"></a>Gevoeligheidslabel verwijderd

Deze gebeurtenis wordt gegenereerd telkens als een gevoeligheidslabel uit een bestand of document wordt verwijderd.

- Deze gebeurtenis wordt vastgelegd op het moment van opslaan in Office eigen toepassingen en webtoepassingen.
- De gegevens worden vastgelegd op het moment dat de invoegvoegingen van Azure Information Protection worden gebruikt. 
- Gevoeligheidslabels, met Office eigen MIP-label, worden op Outlook de laatste labelinggebeurtenis verzameld die is gegenereerd voordat acties voor het opslaan/verzenden van bestanden per e-mail zijn gegenereerd.

|Source  |Gerapporteerd in activiteitsverkenner | Opmerking  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |ja         |
|Outlook         |ja         |Win 32|
|SharePoint Online, OneDrive         |ja         |
|Exchange         |ja         |
|AIP-geïntegreerde client         |ja         |de actie Label *verwijderen* van AIP is in kaart gebracht aan de *actie labelverwijdering* in activiteitenverkenner|
|Geïntegreerde AIP-scanner         |ja         |de actie Label *verwijderen* van AIP is in kaart gebracht aan de *actie labelverwijdering* in activiteitenverkenner |
|MIP SDK         |ja         |de actie Label *verwijderen* van AIP is in kaart gebracht aan de *actie labelverwijdering* in activiteitenverkenner |
|RMS-service         |niet van toepassing         |
|Power BI bureaublad en web         |nee         |toegankelijk in de Microsoft 365 auditlogboeken |
|MCAS     |nee         |         |
 

## <a name="sensitivity-label-file-read"></a>Gevoeligheidslabelbestand gelezen

Deze gebeurtenis wordt gegenereerd telkens als een gevoeligheidslabel of beveiligd document wordt geopend.

|Source  |Gerapporteerd in activiteitsverkenner | Opmerking  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |ja         |
|Outlook         |nee         |
|SharePoint Online, OneDrive         |nee         |
|Exchange         |nee         |
|AIP-geïntegreerde client         |ja         |de actie *AIP-toegang* wordt in kaart gebracht aan de actie Bestand *lezen* in de verkenner|
|Geïntegreerde AIP-scanner         |ja         |de actie *AIP-toegang* wordt in kaart gebracht aan de actie Bestand *lezen* in de verkenner|
|MIP SDK         |ja         |de actie *AIP-toegang* wordt in kaart gebracht aan de actie Bestand *lezen* in de verkenner|
|RMS-service         |ja         |de *toegangsactie* is in kaart gebracht aan de actie Bestand *lezen* in activiteitenverkenner |
|Power BI bureaublad en web         |nee         |toegankelijk in de Microsoft 365 auditlogboeken |
|MCAS     |nee         |         |


## <a name="files-discovered"></a>Bestanden gevonden

Deze gebeurtenis wordt gegenereerd telkens wanneer bestanden worden gevonden wanneer AIP Scanner wordt gebruikt voor het scannen van gevoelige gegevens op verschillende locaties en bestanden vindt.

|Source  |Gerapporteerd in activiteitsverkenner | Opmerking  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |niet van toepassing         |
|Outlook         |niet van toepassing         |
|SharePoint Online, OneDrive         |niet van toepassing         |
|Exchange         |niet van toepassing         |
|AIP-geïntegreerde client         |niet van toepassing       |
|Geïntegreerde AIP-scanner         |ja         |de actie AIP *ontdekken* is in kaart gebracht aan de *bestanden die zijn* gevonden in activiteitsverkenner|
|MIP SDK         |ja         |de actie AIP *ontdekken* is in kaart gebracht aan de *actie bestand dat* is gevonden in activiteitenverkenner|
|RMS-service         |niet van toepassing         |
|Power BI bureaublad en web         |niet van toepassing         |
|MCAS     |niet van toepassing         |         |


## <a name="sensitivity-label-file-renamed"></a>Naam van gevoeligheidslabelbestand gewijzigd

Deze gebeurtenis wordt gegenereerd telkens als de naam van een document met een gevoeligheidslabel wordt gewijzigd. 

|Source  | Gerapporteerd in activiteitsverkenner | Opmerking  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |ja         |
|Outlook         |niet van toepassing         |
|SharePoint Online, OneDrive         |nee        |
|Exchange         |niet van toepassing         |
|AIP-geïntegreerde client         |nee         |
|Geïntegreerde AIP-scanner         |nee         |
|MIP SDK         |nee         |
|RMS-service         |nee      |
|Power BI bureaublad en web         |nee         |
|MCAS     |nee         |         |


## <a name="file-removed"></a>Bestand verwijderd

Deze gebeurtenis wordt gegenereerd telkens wanneer de AIP-scanner detecteert dat een eerder gescand bestand is verwijderd.

|Source  |Gerapporteerd in activiteitsverkenner | Opmerking  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |niet van toepassing         |
|Outlook         |niet van toepassing         |
|SharePoint Online, OneDrive         |niet van toepassing           |
|Exchange         |niet van toepassing         |
|AIP-geïntegreerde client         |niet van toepassing            |
|Geïntegreerde AIP-scanner         |ja         |
|MIP SDK         |niet van toepassing            |
|RMS-service         |niet van toepassing         |
|Power BI bureaublad en web         |niet van toepassing  |
|MCAS     |niet van toepassing        |         |

### <a name="protection-applied"></a>Toegepaste beveiliging

Deze gebeurtenis wordt gegenereerd de eerste keer dat de beveiliging handmatig wordt toegevoegd aan een item dat geen label heeft.

|Source  |Gerapporteerd in activiteitsverkenner | Opmerking  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |nee         |
|Outlook         |nee         |
|SharePoint Online, OneDrive         |niet van toepassing           |
|Exchange         |nee       |
|AIP-geïntegreerde client         |ja            |
|Geïntegreerde AIP-scanner         |niet van toepassing         |
|MIP SDK         |ja            |
|RMS-service         |niet van toepassing         |
|Power BI bureaublad en web         |niet van toepassing            |
|MCAS     |niet van toepassing        |         |

## <a name="protection-changed"></a>Beveiliging gewijzigd

Deze gebeurtenis wordt gegenereerd telkens als de beveiliging van een document zonder label handmatig wordt gewijzigd.

|Source  |Gerapporteerd in activiteitsverkenner |
|---------|---------| 
|Word, Excel, PowerPoint         |nee         |
|Outlook         |nee         |
|SharePoint Online, OneDrive         |niet van toepassing           |
|Exchange         |nee       |
|AIP-geïntegreerde client         |ja            |
|Geïntegreerde AIP-scanner         |niet van toepassing         |
|MIP SDK         |ja            |
|RMS-service         |niet van toepassing         |
|Power BI bureaublad en web         |niet van toepassing            |
|MCAS     |niet van toepassing        |

## <a name="protection-removed"></a>Beveiliging verwijderd

Deze gebeurtenis wordt gegenereerd telkens als de beveiliging van een document zonder label handmatig wordt gewijzigd.

|Source  |Gerapporteerd in activiteitsverkenner |
|---------|---------| 
|Word, Excel, PowerPoint         |nee         |
|Outlook         |nee         |
|SharePoint Online, OneDrive         |niet van toepassing           |
|Exchange         |nee       |
|AIP-geïntegreerde client         |ja            |
|Geïntegreerde AIP-scanner         |niet van toepassing         |
|MIP SDK         |ja            |
|RMS-service         |niet van toepassing         |
|Power BI bureaublad en web         |niet van toepassing            |
|MCAS     |niet van toepassing        |

## <a name="dlp-policy-matched"></a>DLP-beleid gematched

Deze gebeurtenis wordt gegenereerd telkens als een DLP-beleid is afgestemd op een document of e-mail.

|Source  |Gerapporteerd in activiteitsverkenner |
|---------|---------| 
|Exchange         |ja       |
|SharePoint Online|ja          |
|OneDrive |ja|
|Teams |ja   |
|Windows 10-apparaten         |ja |
|MAC         |nee     |
|on-premises         |nee|
|MCAS     |nee        | 

De gebeurtenissen voor Windows 10 Apparaten (Endpoint DLP) zijn:

- bestand verwijderd
- bestand gemaakt
- bestand is gekopieerd naar het klembord
- bestand gewijzigd
- bestand gelezen
- bestand is afgedrukt
- bestand hernoemd
- bestand is gekopieerd naar netwerkshare
- bestand dat is toegankelijk via niet-toegestaan app


## <a name="retention-label-applied"></a>Bewaarlabel toegepast 

Deze gebeurtenis wordt gegenereerd telkens als een document zonder label wordt gelabeld of een e-mailbericht wordt verzonden met een bewaarlabel.

- Deze wordt vastgelegd op het moment van opslaan voor een document en op het moment van verzenden voor een e-mail.

|Source  |Gerapporteerd in activiteitsverkenner |
|---------|---------| 
|Exchange         |nee       |
|SharePoint Online|ja          |
|OneDrive |ja|

## <a name="retention-label-changed"></a>Bewaarlabel gewijzigd

Deze gebeurtenis wordt gegenereerd telkens wanneer een label wordt bijgewerkt in een document of e-mailbericht.

- Deze wordt vastgelegd op het moment van opslaan voor een document en op het moment van verzenden voor een e-mail.

|Source  |Gerapporteerd in activiteitsverkenner |
|---------|---------| 
|Exchange         |nee       |
|SharePoint Online|ja          |
|OneDrive |ja|
 
## <a name="retention-label-removed"></a>Bewaarlabel verwijderd

Deze gebeurtenis wordt gegenereerd telkens als een label uit een bestand of document wordt verwijderd.

- Deze wordt vastgelegd op het moment van opslaan voor een document en op het moment van verzenden voor een e-mail.

|Source  |Gerapporteerd in activiteitsverkenner |
|---------|---------| 
|Exchange         |nee       |
|SharePoint Online|ja          |
|OneDrive |ja|


## <a name="known-issues"></a>Bekende problemen
  
- Wanneer de aanbevolen labelhulpmiddeltip wordt weergegeven aan een eindgebruiker, wordt deze niet vastgelegd. Maar als de gebruiker ervoor kiest het aanbevolen label toe te passen, wordt het label weergegeven onder het veld Hoe *toegepast* als *Aanbevolen*  

- Tekst uitvullen is momenteel niet beschikbaar voor downgrade van gevoeligheidslabels vanuit Sharepoint en OneDrive.  

- Gevoelige informatietypen zijn momenteel niet beschikbaar voor autolabelingactiviteiten van Word, Excel, PowerPoint en Outlook, evenals SharePoint Online en OneDrive.
