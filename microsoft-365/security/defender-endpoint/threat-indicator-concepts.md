---
title: Begrip van bedreigingsinformatieconcepten in Microsoft Defender voor Eindpunt
description: Aangepaste bedreigingswaarschuwingen maken voor uw organisatie en de concepten leren over bedreigingsinformatie in Microsoft Defender voor Eindpunt
keywords: bedreigingsinformatie, waarschuwingsdefinities, indicatoren van compromissen, ioc
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: bb82634c8c2ef11131a43e8e479bf88d5626ed03
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059302"
---
# <a name="understand-threat-intelligence-concepts"></a>Concepten voor bedreigingsinformatie begrijpen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-threatindicator-abovefoldlink) 

Geavanceerde cyberbeveiligingsaanvallen bestaan uit meerdere complexe schadelijke gebeurtenissen, kenmerken en contextuele informatie. Het identificeren en bepalen van welke van deze activiteiten als verdacht worden gekwalificeerd, kan een lastige taak zijn. Uw kennis van bekende kenmerken en abnormale activiteiten die specifiek zijn voor uw branche, is essentieel als u weet wanneer u een waargenomen gedrag als verdacht moet noemen.

Met Microsoft Defender voor Eindpunt kunt u aangepaste bedreigingswaarschuwingen maken om mogelijke aanvalsactiviteiten in uw organisatie bij te houden. U kunt verdachte gebeurtenissen markeren om aanwijzingen samen te brengen en mogelijk een aanvalsketen te stoppen. Deze aangepaste bedreigingswaarschuwingen worden alleen weergegeven in uw organisatie en markeren gebeurtenissen die u hebt ingesteld op bijhouden.

Voordat u aangepaste bedreigingswaarschuwingen maakt, is het belangrijk om de concepten achter waarschuwingsdefinities en indicatoren van compromissen (IOC's) en de relatie tussen deze waarschuwingen te kennen.

## <a name="alert-definitions"></a>Waarschuwingsdefinities
Waarschuwingsdefinities zijn contextuele kenmerken die gezamenlijk kunnen worden gebruikt om vroege aanwijzingen voor een mogelijke cyberbeveiligingsaanval te identificeren. Deze indicatoren zijn meestal een combinatie van activiteiten, kenmerken en acties die door een aanvaller worden uitgevoerd om het doel van een aanval te bereiken. Het controleren van deze combinaties van kenmerken is essentieel bij het verkrijgen van een vantagepunt tegen aanvallen en het mogelijk verstoren van de keten van gebeurtenissen voordat het doel van een aanvaller wordt bereikt.

## <a name="indicators-of-compromise-ioc"></a>Indicatoren voor compromissen (IOC)
IOC's zijn individueel bekende schadelijke gebeurtenissen die aangeven dat een netwerk of apparaat al is geschonden. In tegenstelling tot waarschuwingsdefinities worden deze indicatoren beschouwd als bewijs van een inbreuk. Ze worden vaak gezien nadat er al een aanval is uitgevoerd en het doel is bereikt, zoals exfiltration. Het bijhouden van IOC's is ook belangrijk tijdens de gerechtelijke onderzoeken. Hoewel het mogelijk niet de mogelijkheid biedt om tussenbeide te komen met een aanvalsketen, kan het verzamelen van deze indicatoren nuttig zijn bij het maken van betere verdediging voor mogelijke toekomstige aanvallen.

## <a name="relationship-between-alert-definitions-and-iocs"></a>Relatie tussen waarschuwingsdefinities en IOC's
In de context van Microsoft Defender voor Eindpunt zijn waarschuwingsdefinities containers voor IOC's en definieert u de waarschuwing, inclusief de metagegevens die worden opgehaald in het geval van een specifieke IOC-overeenkomst. Diverse metagegevens worden geleverd als onderdeel van de waarschuwingsdefinities. Metagegevens, zoals de naam van de waarschuwingsdefinitie van de aanval, ernst en beschrijving, worden samen met andere opties weergegeven.

Elke IOC definieert de logica voor de concrete detectie op basis van het type en de waarde en de actie, die bepaalt hoe deze wordt afgestemd. Deze is afhankelijk van een specifieke waarschuwingsdefinitie die definieert hoe een detectie wordt weergegeven als een waarschuwing op de Microsoft Defender voor Eindpunt-console.

Hier is een voorbeeld van een IOC:
- Type: Sha1
- Waarde: 92cfceb39d57d914ed8b14d0e37643de0797ae56
- Actie: Is gelijk aan

IOC's hebben een veel-op-een-relatie met waarschuwingsdefinities, zodat een waarschuwingsdefinitie veel IOC's kan hebben die overeenkomen met deze definitie.

## <a name="in-this-section"></a>In deze sectie

Onderwerp | Beschrijving
:---|:---
[Detecties naar uw SIEM-hulpprogramma's trekken](configure-siem.md)| Meer informatie over verschillende manieren om detecties te trekken.
[SIEM-integratie inschakelen in Microsoft Defender voor Eindpunt](enable-siem-integration.md)| Meer informatie over het inschakelen  van de siem-integratiefunctie op de pagina Instellingen in de portal, zodat u de vereiste informatie kunt gebruiken en genereren om ondersteunde SIEM-hulpprogramma's te configureren.
[Splunk configureren om Microsoft Defender voor eindpuntdetecties op te halen](configure-siem.md)| Meer informatie over het installeren van de REST API Modular Input App en andere configuratie-instellingen om Splunk in staat te stellen Microsoft Defender te gebruiken voor eindpuntdetecties.
[HP ArcSight configureren om Microsoft Defender te gebruiken voor eindpuntdetecties](configure-arcsight.md)| Meer informatie over het installeren van het HP ArcSight REST FlexConnector-pakket en de bestanden die u nodig hebt om ArcSight te configureren om Microsoft Defender te gebruiken voor eindpuntdetecties.
[Microsoft Defender voor eindpuntdetectievelden](api-portal-mapping.md) | Meer informatie over de gegevensvelden die worden weergegeven als onderdeel van de API voor waarschuwingen en hoe deze worden toebedeeld aan het Microsoft Defender-beveiligingscentrum.
[Microsoft Defender voor eindpuntdetecties trekken met REST API](pull-alerts-using-rest-api.md) | Gebruik de OAuth 2.0-stroom Clientreferenties om detecties van Microsoft Defender voor Eindpunt op te halen met REST API.
[Problemen met de integratie van SIEM-hulpprogramma's oplossen](troubleshoot-siem.md) | Problemen oplossen die u mogelijk ondervindt bij het gebruik van de SIEM-integratiefunctie.



## <a name="related-topics"></a>Verwante onderwerpen
- [Indicatoren beheren](manage-indicators.md)
