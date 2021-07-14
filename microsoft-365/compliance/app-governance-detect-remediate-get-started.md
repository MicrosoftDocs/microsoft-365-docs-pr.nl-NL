---
title: Aan de slag met app-bedreigingsdetectie en herstel
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
description: Aan de slag met app-bedreigingsdetectie en herstel.
ms.openlocfilehash: 6229d2cf94ec1ba892929f399fe49cf88da608d1
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420176"
---
# <a name="get-started-with-app-threat-detection-and-remediation"></a>Aan de slag met app-bedreigingsdetectie en herstel

>*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](https://aka.ms/ComplianceSD).*

Microsoft-app-governance verzamelt bedreigingswaarschuwingen die gegenereerd worden door ingebouwde app-governancedetectiemethodes gebaseerd op schadelijke activiteiten en beleidswaarschuwingen gegenereerd door actief app-beleid dat door jouw is gemaakt.

De eerste plaats om app-waarschuwingen te bekijken is het app-governance-dashboard op [https://compliance.microsoft.com/appgovernance](https://compliance.microsoft.com/appgovernance).

![De overzichtpagina van app-governance in het Microsoft 365-compliancecentrum met de aandacht op de sectie Detectie en beleidswaarschuwingen](..\media\manage-app-protection-governance\mapg-cc-overview-alerts.png)

Op deze overzichtspagina geeft de sectie **Detectie en beleidswaarschuwingen** een lijst meet de nieuwste waarschuwingen. Je kan deze gebruiken om snel de huidige app-waarschuwingsactiviteit voor de tenant weer te geven.

Selecteer het tabblad **Waarschuwingen** om alle waarschuwingen weer te geven.

## <a name="whats-available-on-the-alerts-page"></a>Wat is er beschikbaar op de Waarschuwingen-pagina

De pagina **Waarschuwingen** geeft een lijst weer met alle waarschuwingen gebaseerd op app-governance voor de tenant.

![De samenvattingspagina van de app-governancewaarschuwingen in het Microsoft 365-compliancecentrum](..\media\manage-app-protection-governance\mapg-cc-alerts.png)

Elke opgelijste waarschuwing biedt de volgende informatie:

- **Waarschuwingsnaam**: Het type afwijkend gedrag.
- **App-naam**: De app die de waarschuwing heeft gegenereerd.
- **Ernst**: Het niveau van ernst toegewezen voor waarschuwing gegeneerd door app-governance of het niveua van ernst van het app-beleid gegeneerd door de waarschuwing. 
- **Bron**: Oorzaak van de waarschuwing, wat het resultaat van beleid (gemaakt door gebruiker), detectie (ingebouwd beleid) of MCAS kan zijn.
- **Status**: **Nieuw** geeft aan dat een waarschuwing geen status toegewezen heeft gekregen. Nadat de status toegewezen is kan het **In behandeling** zijn terwijl het onderzoek bezig is of **Opgelost** voor waarschuwingen die behandeld zijn vie automatisch herstel of manueel herstel.
- **Datum creatie**: De datum waarop de waarschuwing gegenereerd werd door app-governance-detectie of door app-beleid. Alle weergegeven datums zijn in de lokale tijdzone van het Microsoft 365-compliancecentrum.
- **Laatste activiteit**: De datum waarop de status van de waarschuwing gewijzigd werd. Alle weergegeven datums zijn in de lokale tijdzone van het Microsoft 365-compliancecentrum.

De lijst met waarschuwingen wordt standaard op **Datum creatie** gesorteerd. Selecteer de kenmerknaam om de lijst op een ander kenmerk te sorteren.

Je kan ook de huidige lijst met waarschuwingen exporteren naar een bestand met door komma's gescheiden waarden (CSV). Je kan bijvoorbeeld een CVS-bestand openen in Microsoft Excel en de lijst met waarschuwingen sorteren op **Ernst** en vervolgens op **Datum creatie**.

## <a name="next-step"></a>Volgende stap

[App-bedreigingen herstellen.](app-governance-detect-remediate-detect-threats.md)
