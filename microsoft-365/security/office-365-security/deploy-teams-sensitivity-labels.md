---
title: Bestanden in teams beschermen met gevoeligheidslabels.
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: 'Overzicht: gevoeligheidslabels toepassen om bestanden in een zeer vertrouwelijk team te beveiligen.'
ms.openlocfilehash: c36daef7f28ad8bd3306fd7f3f7f1558a3594e68
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637614"
---
# <a name="protect-files-in-teams-with-sensitivity-labels"></a>Bestanden in teams beschermen met gevoeligheidslabels.


Een zeer vertrouwelijk team heeft, in tegenstelling tot een gevoeligheidslabel voor sterk gereglementeerde gegevens die iedereen op een bestand kan toepassen, een eigen label of sublabel nodig, zodat toegewezen bestanden:

- Afzonderlijk worden versleuteld.
- Aangepaste machtigingen bevatten, zodat alleen leden van het team ze kunnen openen.

Om dit extra beveiligingsniveau te halen voor bestanden die zijn opgeslagen op de SharePoint-site van een team, moet u een aangepast gevoeligheidslabel configureren dat een afzonderlijk label is of een sublabel van het algemene label voor sterk gereglementeerde bestanden. Alleen teamleden zien het aangepaste etiket of sublabel in hun lijst met labels.

Gebruik een gevoeligheidslabel wanneer u een klein aantal labels nodig hebt voor zowel globaal gebruik als afzonderlijke privéteams. 

Gebruik een gevoeligheids-sublabel wanneer u een groot aantal labels nodig hebt of als u labels wilt organiseren voor zeer vertrouwelijke teams onder het sterk gereglementeerde label.

Gebruik [deze instructies](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) om een afzonderlijk label of sublabel met de volgende instellingen te configureren:

- De naam van het label bevat de naam van het team
- Versleuteling is ingeschakeld
- De Microsoft 365-groep voor het team heeft machtigingen voor cocreatie

Na het maken van het nieuwe label of sublabel voor uw gebruikers, die ze vervolgens lokaal kunnen toepassen op bestanden voordat ze worden geüpload naar het team of later zodra het bestand is opgeslagen in het team.

Hier vindt u de configuratie van het zeer vertrouwelijke team dat gebruikmaakt van gevoeligheidslabels voor bestandsversleuteling en machtigingen.

![Basisbeveiliging voor een openbaar team.](../../media/highly-confidential-team-dlp-sensitivity-labels.png)


## <a name="see-also"></a>Zie ook

[Bestanden beveiligen in Microsoft Teams](secure-files-in-teams.md)
  
[Cloud adoption and hybrid solutions](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions) (Overstappen op de cloud en hybride oplossingen)
