---
title: Labelingacties die zijn gerapporteerd in Activiteitsverkenner
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
description: een lijst met labelacties die beschikbaar zijn in activity explorer.
ms.openlocfilehash: ed51c908d6968e3aeae0adbe06d9ba55887bcf83
ms.sourcegitcommit: 1c53f114a810e7aaa2dc876b84d66348492ea36c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "51902944"
---
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a>Labeling-activiteiten die beschikbaar zijn in Activiteitenverkenner

## <a name="sensitivity-label-applied"></a>Gevoeligheidslabel toegepast

Deze gebeurtenis wordt gegenereerd telkens als een document zonder label wordt gelabeld of een e-mailbericht wordt verzonden met een label. 

- Het wordt vastgelegd op het moment van opslaan in office-native toepassingen en webtoepassingen. 
- De gegevens worden vastgelegd op het moment dat de invoegvoegingen van Azure Information Protection worden gebruikt. 
- Acties voor het upgraden en downgraden van labels kunnen ook worden gecontroleerd via het *veld labeltype en* het filter.   


|Source  |Gerapporteerd in activiteitsverkenner | Opmerking  |
|---------|---------|---------|
| Word, Excel, PowerPoint|Ja |
|Outlook| Ja |van Win 32 |
|SharePoint online, OneDrive|Ja | |
|Exchange        |Ja         | |
|Azure Information Protection (AIP) unified client en AIP unified scanner |Ja |de nieuwe *labelactie* AIP is in kaart gebracht aan het label dat *is toegepast* in activiteitsverkenner   |
|Microsoft information protection (MIP) SDK         |Ja|de nieuwe *labelactie* AIP is in kaart gebracht aan het label dat *is toegepast* in activiteitsverkenner|
|Rights Management Service (RMS)         |niet van toepassing         | |
|Bureaublad en web van Power BI        | nee| toegankelijk in de Microsoft 365-auditlogboeken         |
|Microsoft Cloud App Security (MCAS)         |nee|         |

## <a name="sensitivity-label-changed"></a>Gevoeligheidslabel gewijzigd

Deze gebeurtenis wordt gegenereerd telkens wanneer een label wordt bijgewerkt in het document of e-mailbericht.

- Voor de AIP Unified-client, Unified Scanner en MIP SDK-bronnen is het *AIP-upgradelabel* en *downgradelabelactiekaarten* naar het label Activity Explorer *gewijzigd*

- Het wordt vastgelegd op het moment van opslaan in office-native toepassingen en webtoepassingen. 
- Het wordt vastgelegd op het moment van het optreden in geïntegreerde client-invoegingen en scanners voor Azure Information Protection
- Acties voor het upgraden en downgraden van labels kunnen ook worden gecontroleerd via het *veld labeltype en* het filter. De *tekst van* de uitvulling wordt ook vastgelegd, behalve voor SharePoint Online en OneDrive.
- Met gevoeligheidslabels die zijn uitgevoerd in office-native apps in Outlook, wordt de laatste actie verzameld die is gegenereerd voordat acties voor het opslaan/verzenden van bestanden per e-mail zijn gegenereerd. Als de gebruiker bijvoorbeeld het label voor een e-mail meerdere keren wijzigt voordat deze wordt verzonden, wordt het laatste label dat is gevonden in de e-mail wanneer deze wordt verzonden vastgelegd in het auditlogboek en vervolgens gerapporteerd in activity explorer. 


|Source  |Gerapporteerd in activiteitsverkenner|Opmerking  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |Ja         |
|Outlook         |Ja         |Win 32|
|SharePoint Online, OneDrive         |Ja         |
|Exchange         |Ja         |
|AIP-geïntegreerde client         |Ja         |
|Geïntegreerde AIP-scanner         |Ja         |
|MIP SDK         |Ja         |
|RMS-service         |niet van toepassing         |
|Bureaublad en web van Power BI         |nee         |toegankelijk in de Microsoft 365-auditlogboeken |
|MCAS     |nee         |         |

## <a name="sensitivity-label-removed"></a>Gevoeligheidslabel verwijderd

Deze gebeurtenis wordt gegenereerd telkens als een label uit een bestand of document wordt verwijderd.

- Deze gebeurtenis wordt vastgelegd op het moment van opslaan in office-native toepassingen en webtoepassingen.
- De gegevens worden vastgelegd op het moment dat de invoegvoegingen van Azure Information Protection worden gebruikt. 
- Met gevoeligheidslabels, met een MIP-label voor Office, wordt in Outlook de laatste labelingsgebeurtenis verzameld die is gegenereerd voordat acties voor het opslaan/verzenden van bestanden per e-mail zijn gegenereerd.

|Source  |Gerapporteerd in activiteitsverkenner | Opmerking  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |Ja         |
|Outlook         |Ja         |Win 32|
|SharePoint Online, OneDrive         |Ja         |
|Exchange         |Ja         |
|AIP-geïntegreerde client         |Ja         |de actie Label *verwijderen* van AIP is in kaart gebracht aan de *actie labelverwijdering* in activiteitenverkenner|
|Geïntegreerde AIP-scanner         |Ja         |de actie Label *verwijderen* van AIP is in kaart gebracht aan de *actie labelverwijdering* in activiteitenverkenner |
|MIP SDK         |Ja         |de actie Label *verwijderen* van AIP is in kaart gebracht aan de *actie labelverwijdering* in activiteitenverkenner |
|RMS-service         |niet van toepassing         |
|Bureaublad en web van Power BI         |nee         |toegankelijk in de Microsoft 365-auditlogboeken |
|MCAS     |nee         |         |
 

## <a name="sensitivity-label-file-read"></a>Gevoeligheidslabelbestand gelezen

Deze gebeurtenis wordt gegenereerd telkens als een document met een label of een beveiligd document wordt geopend.

|Source  |Gerapporteerd in activiteitsverkenner | Opmerking  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |Ja         |
|Outlook         |nee         |
|SharePoint Online, OneDrive         |nee         |
|Exchange         |nee         |
|AIP-geïntegreerde client         |Ja         |de actie *AIP-toegang* wordt in kaart gebracht aan de actie Bestand *lezen* in de verkenner|
|Geïntegreerde AIP-scanner         |Ja         |de actie *AIP-toegang* wordt in kaart gebracht aan de actie Bestand *lezen* in de verkenner|
|MIP SDK         |Ja         |de actie *AIP-toegang* wordt in kaart gebracht aan de actie Bestand *lezen* in de verkenner|
|RMS-service         |Ja         |de *toegangsactie* is in kaart gebracht aan de actie Bestand *lezen* in activiteitenverkenner |
|Bureaublad en web van Power BI         |nee         |toegankelijk in de Microsoft 365-auditlogboeken |
|MCAS     |nee         |         |


## <a name="sensitivity-label-files-discovered"></a>Gevoeligheidslabelbestanden gevonden

Deze gebeurtenis wordt gegenereerd telkens wanneer bestanden worden gevonden wanneer AIP Scanner wordt gebruikt voor het scannen van gevoelige gegevens op verschillende locaties en bestanden vindt.

|Source  |Gerapporteerd in activiteitsverkenner | Opmerking  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |niet van toepassing         |
|Outlook         |niet van toepassing         |
|SharePoint Online, OneDrive         |niet van toepassing         |
|Exchange         |niet van toepassing         |
|AIP-geïntegreerde client         |niet van toepassing       |
|Geïntegreerde AIP-scanner         |Ja         |de actie AIP *ontdekken* is in kaart gebracht aan de *bestanden die zijn* gevonden in activiteitsverkenner|
|MIP SDK         |Ja         |de actie AIP *ontdekken* is in kaart gebracht aan de *actie bestand dat* is gevonden in activiteitenverkenner|
|RMS-service         |niet van toepassing         |
|Bureaublad en web van Power BI         |niet van toepassing         |
|MCAS     |niet van toepassing         |         |


## <a name="sensitivity-label-file-renamed"></a>Naam van gevoeligheidslabelbestand gewijzigd

Deze gebeurtenis wordt gegenereerd telkens als de naam van een document met een gevoeligheidslabel wordt gewijzigd. 

|Source  | Gerapporteerd in activiteitsverkenner | Opmerking  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |Ja         |
|Outlook         |niet van toepassing         |
|SharePoint Online, OneDrive         |nee        |
|Exchange         |niet van toepassing         |
|AIP-geïntegreerde client         |nee         |
|Geïntegreerde AIP-scanner         |nee         |
|MIP SDK         |nee         |
|RMS-service         |nee      |
|Bureaublad en web van Power BI         |nee         |
|MCAS     |nee         |         |


## <a name="sensitivity-label-file-removed"></a>Gevoeligheidslabelbestand verwijderd

Deze gebeurtenis wordt gegenereerd telkens wanneer de AIP-scanner detecteert dat een eerder gescand bestand is verwijderd.

|Source  |Gerapporteerd in activiteitsverkenner | Opmerking  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |niet van toepassing         |
|Outlook         |niet van toepassing         |
|SharePoint Online, OneDrive         |niet van toepassing           |
|Exchange         |niet van toepassing         |
|AIP-geïntegreerde client         |niet van toepassing            |
|Geïntegreerde AIP-scanner         |Ja         |
|MIP SDK         |niet van toepassing            |
|RMS-service         |niet van toepassing         |
|Bureaublad en web van Power BI         |niet van toepassing  |
|MCAS     |niet van toepassing        |         |

### <a name="sensitivity-label-protection-applied"></a>Gevoeligheidslabelbeveiliging toegepast

Deze gebeurtenis wordt gegenereerd de eerste keer dat de beveiliging handmatig wordt toegevoegd aan een item dat geen label heeft.

|Source  |Gerapporteerd in activiteitsverkenner | Opmerking  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |nee         |
|Outlook         |nee         |
|SharePoint Online, OneDrive         |niet van toepassing           |
|Exchange         |nee       |
|AIP-geïntegreerde client         |Ja            |
|Geïntegreerde AIP-scanner         |niet van toepassing         |
|MIP SDK         |Ja            |
|RMS-service         |niet van toepassing         |
|Bureaublad en web van Power BI         |niet van toepassing            |
|MCAS     |niet van toepassing        |         |

## <a name="sensitivity-label-protection-changed"></a>Gevoeligheidslabelbeveiliging gewijzigd

Deze gebeurtenis wordt gegenereerd telkens als de beveiliging van een document zonder label handmatig wordt gewijzigd.

|Source  |Gerapporteerd in activiteitsverkenner |
|---------|---------| 
|Word, Excel, PowerPoint         |nee         |
|Outlook         |nee         |
|SharePoint Online, OneDrive         |niet van toepassing           |
|Exchange         |nee       |
|AIP-geïntegreerde client         |Ja            |
|Geïntegreerde AIP-scanner         |niet van toepassing         |
|MIP SDK         |Ja            |
|RMS-service         |niet van toepassing         |
|Bureaublad en web van Power BI         |niet van toepassing            |
|MCAS     |niet van toepassing        |

## <a name="sensitivity-label-protection-removed"></a>Gevoeligheidslabelbeveiliging verwijderd

Deze gebeurtenis wordt gegenereerd telkens als de beveiliging van een document zonder label handmatig wordt gewijzigd.

|Source  |Gerapporteerd in activiteitsverkenner |
|---------|---------| 
|Word, Excel, PowerPoint         |nee         |
|Outlook         |nee         |
|SharePoint Online, OneDrive         |niet van toepassing           |
|Exchange         |nee       |
|AIP-geïntegreerde client         |Ja            |
|Geïntegreerde AIP-scanner         |niet van toepassing         |
|MIP SDK         |Ja            |
|RMS-service         |niet van toepassing         |
|Bureaublad en web van Power BI         |niet van toepassing            |
|MCAS     |niet van toepassing        |

## <a name="sensitivity-label-dlp-policy-matched"></a>Gevoeligheidslabel DLP-beleid overeenkomend

Deze gebeurtenis wordt gegenereerd telkens als een DLP-beleid is afgestemd.

|Source  |Gerapporteerd in activiteitsverkenner |
|---------|---------| 
|Exchange         |Ja       |
|SharePoint Online|Ja          |
|OneDrive |Ja|
|Teams |Ja   |
|Windows 10-apparaten         |Ja |
|MAC         |nee     |
|on-premises         |nee|
|MCAS     |nee        | 

De gebeurtenissen voor Windows 10-apparaten (Endpoint DLP) zijn:

- bestand verwijderd
- bestand gemaakt
- bestand gekopieerd naar klembord
- bestand gewijzigd
- bestand gelezen
- bestand afgedrukt
- bestand hernoemd
- bestand gekopieerd naar netwerk delen
- bestand dat is toegankelijk via niet-toegestaan app


## <a name="retention-label-applied"></a>Bewaarlabel toegepast 

Deze gebeurtenis wordt gegenereerd telkens als een document zonder label wordt gelabeld of een e-mailbericht wordt verzonden met een label.

- Het wordt vastgelegd op het moment van opslaan in office-native toepassingen en webtoepassingen.

|Source  |Gerapporteerd in activiteitsverkenner |
|---------|---------| 
|Exchange         |nee       |
|SharePoint Online|Ja          |
|OneDrive |Ja|

## <a name="retention-label-changed"></a>Bewaarlabel gewijzigd

Deze gebeurtenis wordt gegenereerd telkens wanneer een label wordt bijgewerkt in een document of e-mailbericht.

- Deze wordt vastgelegd op het moment van opslaan.

|Source  |Gerapporteerd in activiteitsverkenner |
|---------|---------| 
|Exchange         |nee       |
|SharePoint Online|Ja          |
|OneDrive |Ja|
 
## <a name="retention-label-removed"></a>Bewaarlabel verwijderd

Deze gebeurtenis wordt gegenereerd telkens als een label uit een bestand of document wordt verwijderd.

- Deze wordt vastgelegd op het moment van opslaan.

|Source  |Gerapporteerd in activiteitsverkenner |
|---------|---------| 
|Exchange         |nee       |
|SharePoint Online|Ja          |
|OneDrive |Ja|


## <a name="known-issues"></a>Bekende problemen
  
- Wanneer de aanbevolen labelhulpmiddeltip wordt weergegeven aan een eindgebruiker, wordt deze niet vastgelegd. Maar als de gebruiker ervoor kiest het aanbevolen label toe te passen, wordt het label weergegeven onder het veld Hoe *toegepast* als *Aanbevolen*  

- Tekst met rechtvaardiging is momenteel niet beschikbaar voor downgrade van gevoeligheidslabels vanuit Sharepoint en OneDrive.  

- Gevoelige informatietypen zijn momenteel niet beschikbaar voor autolabelingactiviteiten van Word, Excel, PowerPoint en Outlook, evenals SharePoint Online en OneDrive.
