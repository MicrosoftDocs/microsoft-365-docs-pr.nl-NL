---
title: Deze app-bedreigingen herstellen
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Deze app-bedreigingen herstellen.
ms.openlocfilehash: 73776621ef86523d64b2a216538412bb46ab5586
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420182"
---
# <a name="remediate-app-threats"></a>Deze app-bedreigingen herstellen

>*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](https://aka.ms/ComplianceSD).*

App-bedreigingen herstellen naar je Microsoft 365-tenant doe je via de pagina **Waarschuwingen** in de sectie Microsoft-app-governance van het Microsoft 365-compliancecentrum.

![De samenvattingspagina van de app-governancewaarschuwingen in het Microsoft 365-compliancecentrum](..\media\manage-app-protection-governance\mapg-cc-alerts.png)

De pagina **Waarschuwingen** geeft standaard een lijst weer met bedreigingswaarschuwingen die gegenereerd worden door app-governance en waarschuwingen die gegenereerd worden op basis van actief app-beleid. De gegevens van een specifieke waarschuwing kunnen weergegeven worden door deze te selecteren, waardoor een nieuw waarschuwingsvenster wordt geopend met aanvullende informatie en de mogelijkheid om de status te wijzigen.

![De informatiepagina van de app-governancewaarschuwingen in het Microsoft 365-compliancecentrum](..\media\manage-app-protection-governance\mapg-cc-alerts-alert.png)

Vanuit dit venster kan je de volgende aanvullende informatie vinden:

- Aanvullende gegevens over de waarschuwing uit het veld **Beschrijving**
- De naam van het app-beleid dat een waarschuwing heeft gegenereerd uit het veld **Beleidsnaam**. Je kan naar het app-beleid gaan dat de waarschuwing heeft gegenereerd door **Beleid weergeven** te selecteren.

App-beleid dat je geconfigureerd hebt voor automatisch herstel uit **Actie** heeft de status **Opgelost**.

Je kan een app-waarschuwing herstellen met de volgende stappen:

1. Onderzoek: onderzoek de informatie in de waarschuwing en wijzig de status naar **In behandeling**.
2. Resolutie: na het onderzoek en indien nodig de vaststelling van wijzigingen in het app-beleid of verdergaande app-ondersteuning in de tenant, wijzig de status naar **Opgelost**.

Je kan het passende app-beleid bijwerken en de **Actie**-instelling wijzigen op basis van app-waarschuwingspatronen om automatisch herstel uit te voeren. Hiermee verwijder je de nood om onderzoek uit te voeren en toekomstige waarschuwingen die door het app-beleid worden gegenereerd manueel op te lossen. Zie [App-beleid beheren](app-governance-app-policies-manage.md) voor meer informatie.
