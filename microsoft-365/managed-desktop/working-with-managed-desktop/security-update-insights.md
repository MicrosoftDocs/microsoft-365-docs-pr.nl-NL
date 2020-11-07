---
title: Inzichten in Windows-beveiligingsupdates
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b3b1f43217b3be285f20925065bf9710a38f9606
ms.sourcegitcommit: 36795a6735cd3fc678c7d5db71ddc97fac3f6f8a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/06/2020
ms.locfileid: "48941439"
---
# <a name="windows-security-update-insights"></a>Inzichten in Windows-beveiligingsupdates
Deze weergave bevat een overzicht van de status van beveiligingsupdates voor uw beheerde bureaublad apparaten van Microsoft. 

Als u gebruiksgegevens wilt weergeven, selecteert u het tabblad <strong>Windows-beveiligingsupdates</strong> .

![Deelvenster Windows-beveiligingsupdates: staafgrafieken van de apparaatstatus en de versie bijwerken in de linkerkolom, de voortgang van de implementatie in de kolom gecentreerd bijwerken en het percentage actieve apparaten per implementatiegroep, en het aantal dagen dat het implementatie doel voor 95% in de rechterkolom is bereikt.](../../media/update-insights.jpg)

## <a name="device-status"></a>Apparaatstatus

Voor apparaten die moeten worden bijgewerkt door Windows Update, moeten ze verbinding hebben met internet en niet in de slaapstand gedurende minimaal zes uur, waarvan de slaapstand niet lang moet zijn. Hoewel het mogelijk is dat een apparaat dat niet aan deze vereisten voldoet, wordt bijgewerkt, zijn de apparaten die aan hen voldoen de beste kans om te worden bijgewerkt. 

De hardware-activiteit wordt in de context van Windows Update met deze voorwaarden gecategoriseerd:

- <strong>Actief:</strong> Apparaten die voldoen aan de minimale activiteiten criteria (zes uur, twee continu) voor de meest recente update van beveiligingsupdates en met Microsoft intune minstens elke vijf dagen zijn ingecheckt
- <strong>Gesynchroniseerd:</strong> Apparaten die zijn ingecheckt met intune in de afgelopen 28 dagen
- <strong>Niet gesynchroniseerd:</strong> Apparaten die <i>niet</i> zijn ingecheckt met intune in de afgelopen 30 dagen




## <a name="update-version-status"></a>Versie status bijwerken

Microsoft brengt beveiligingsupdates elk de tweede dinsdag van de maand uit. Met elke release worden belangrijke updates voor bekende beveiligingsproblemen opgeteld. Microsoft Managed Desktop zorgt ervoor dat 95% van de beheerde apparaten wordt bijgewerkt met de nieuwste beschikbare beveiligingsupdate per maand. Beveiligingsupdates worden soms op andere momenten uitgebracht om nieuwe bedreigingen dringend te verhelpen. Microsoft Managed Desktop implementeert deze updates op een soortgelijke manier.

De status van de versies van beveiligingsupdate wordt met deze voorwaarden gecategoriseerd:

- <strong>Huidig:</strong> Apparaten waarop de update is uitgebracht in de huidige maand
- <strong>Vorige:</strong> Apparaten waarop de update wordt uitgevoerd die in de vorige maand werd uitgebracht
- <strong>Ouder:</strong> Apparaten met een of meer beveiligingsupdates die zijn uitgebracht vóór de vorige maand

U ziet slechts enkele apparaten in de <strong>oudere</strong> categorie: een grote of groeiende populatie duidt waarschijnlijk op een probleem met het systeem aan dat u moet rapporteren voor Microsoft Managed Desktop, zodat we kunnen onderzoeken.


## <a name="deployment-progress"></a>Voortgang van implementatie

Aan het begin van elke release cyclus van beveiligingsupdates, wordt door Microsoft beheerde bureaubladtoepassing een momentopname van de bevolking van het apparaat gehouden en wordt het implementatie doel ingesteld op 95% van die populatie. Het gebied voortgang van de <strong>implementatie</strong> toont een historische trend, bijgewerkt op dag, waarop u kunt nagaan hoe nauw de update-implementatie voor elke release aan deze doel voldoet. Deze grafiek toont alleen apparaten met de actieve status.

U kunt deze gegevens voor eerdere update cycli weergeven met behulp van de vervolgkeuzelijst in de rechterbovenhoek. De periode die u in dit menu hebt geselecteerd, is van toepassing op alle gegevens op de hele pagina.

Het gebied <strong>met bijgewerkte actieve apparaten per distributiegroep</strong> biedt een andere weergave door de voortgang van de installatie van de update te tonen voor elk van de beheerde groepen Microsoft Managed Desktop Deployment.

In het <strong>doelgebied dagen voor bereiken</strong> wordt de duur van 95% van het totale aantal apparaten dat wordt bijgewerkt met de huidige beveiligingsupdate weergegeven. Tijdens de implementatie wordt dit gebied <strong>nog steeds bijgewerkt</strong> totdat het 95% target voor de geselecteerde update is bereikt.

## <a name="device-details-area"></a>Gebied Details van apparaat

De onderkant van het dashboard is een tabel met gedetailleerde informatie voor uw apparaten, waaronder de status van het [apparaat](#device-status) en de [status van update versies](#update-version-status). U kunt deze lijst doorzoeken of filteren op een waarde in de lijst.


![De tabel apparaatgegevens met de kolommen voor de naam van het apparaat, de toegewezen gebruiker, de apparaatstatus, de versie van het besturingssysteem, de versie van het besturingssysteem en de datum waarop het apparaat de laatste keer is gesynchroniseerd.](../../media/security-update-insights-device-table-sterile.png)
