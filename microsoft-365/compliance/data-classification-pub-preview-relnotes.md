---
title: Opmerkingen bij de release van gegevensclassificatie
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: normal
recommendations: false
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Releasenotities voor gegevensclassificatie.
ms.openlocfilehash: bbce01555367c6151a7b16b551d5580ebcaf9d43
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/29/2021
ms.locfileid: "52162852"
---
# <a name="data-classification-release-notes"></a>Opmerkingen bij de release van gegevensclassificatie


## <a name="exchange-mailbox-count"></a>Exchange aantal postvakken

U ziet een kleine knoptip wanneer u inzoomt op Exchange postvakken. Dit betekent dat het statistische aantal dat wordt weergegeven voor het type gevoelige informatie, het gevoeligheidslabel en het bewaarlabel mogelijk niet exact overeenkomen met het aantal items dat u in het postvak vindt. Dit komt doordat de inzooming in de map de liveweergave van inhoud op haalt, die is geclassificeerd, terwijl het samengevoegde aantal wordt berekend.


## <a name="rendering-of-encrypted-documents"></a>Weergave van versleutelde documenten

SharePoint, Exchange en OneDrive bestanden die zijn versleuteld, worden niet weergegeven in de inhoudsverkenner. Dit is een gevoelig probleem dat een evenwicht vereist tussen de noodzaak om bestandsinhoud te zien in inhoudsverkenner en de noodzaak om de inhoud versleuteld te houden. Met de machtigingen die zijn verleend  door Inhoudsverkenner-lijstviewer en inhoudsverkenner-rollengroepen, ziet u een lijstweergave van de bestanden, de bestandsmetagegevens en een koppeling die u kunt gebruiken om de inhoud te openen via de webclient. 

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a>Ondersteunde tekens in namen van bewaarlabels in SharePoint zoeken

SharePoint zoeken ondersteunt geen namen van bewaarlabels `-` met of `_` in deze. Bijvoorbeeld, `Label-MIP` en `Label_MIP` worden niet ondersteund. SharePoint zoeken ondersteunt deze tekens in namen van gevoeligheidslabels en gevoelige gegevenstypenamen.

## <a name="onedrive-remains-in-preview"></a>OneDrive blijft in voorbeeld

Bedankt voor uw waardevolle feedback over OneDrive integratie tijdens ons preview-programma. Wanneer we de specifieke gegevens doors uitvoeren, kan het zijn dat u inconsistente gegevens/stromen tegen komt. We blijven de OneDrive voorbeeld weergeven totdat alle oplossingen zijn opgelost. We waarderen uw voortdurende ondersteuning.


## <a name="see-also"></a>Zie ook

- [Aan de slag met gegevensclassificatie (voorbeeld)](data-classification-overview.md)
- [Labelactiviteit weergeven (voorbeeld)](data-classification-activity-explorer.md)
- [Gelabelde inhoud weergeven (voorbeeld)](data-classification-content-explorer.md)
- [Meer informatie over vertrouwelijkheidslabels](sensitivity-labels.md)
- [Meer informatie over bewaarbeleid en retentielabels](retention.md)
- [Definities van entiteiten van het type vertrouwelijke gegevens](sensitive-information-type-entity-definitions.md)