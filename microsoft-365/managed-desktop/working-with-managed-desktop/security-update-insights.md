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
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739795"
---
# <a name="windows-security-update-insights"></a>Inzichten in Windows-beveiligingsupdates
Deze weergave bevat een overzicht van de status van beveiligingsupdates voor uw Microsoft Managed Desktop apparaten. 

Als u gebruiksgegevens wilt weergeven, selecteert <strong>u Windows tabblad Beveiligingsupdates.</strong>

![Windows beveiligingsupdatesvenster: staafdiagrammen van de apparaatstatus en updateversie in de linkerkolom, de voortgang van de implementatie bijwerken in de middelste kolom en het percentage actieve apparaten per implementatiegroep, evenals het aantal dagen dat nodig is om het implementatiedoel van 95% in de rechterkolom te bereiken.](../../media/update-insights.jpg)

## <a name="device-status"></a>Apparaatstatus

Als apparaten worden bijgewerkt door Windows Update, moeten ze zijn verbonden met internet en niet gedurende minimaal zes uur in de slaapstand blijven staan, waarvan er twee doorlopend moeten zijn. Hoewel het mogelijk is dat een apparaat dat niet aan deze vereisten voldoet, wordt bijgewerkt, hebben apparaten die aan deze apparaten voldoen de grootste kans dat ze worden bijgewerkt. 

We categoriseren apparaatactiviteit in de context van Windows Bijwerken met de volgende voorwaarden:

- <strong>Actief:</strong> Apparaten die voldoen aan de minimumactiviteitscriteria (zes uur, twee doorlopend) voor de meest recente release van beveiligingsupdates en die zich ten minste om de vijf dagen met Microsoft Intune hebben ingecheckt
- <strong>Gesynchroniseerd:</strong> Apparaten die in de afgelopen 28 dagen met Intune zijn ingecheckt
- <strong>Niet gesynchroniseerd:</strong> Apparaten die de <i>afgelopen</i> 28 dagen niet zijn ingecheckt met Intune




## <a name="update-version-status"></a>Versiestatus bijwerken

Microsoft brengt elke tweede dinsdag van de maand beveiligingsupdates uit. Elke release voegt belangrijke updates toe voor bekende beveiligingsproblemen. Microsoft Managed Desktop zorgt ervoor dat 95% van de beheerde apparaten elke maand wordt bijgewerkt met de meest recente beveiligingsupdate. Beveiligingsupdates worden soms op andere momenten uitgebracht om nieuwe bedreigingen dringend aan te pakken. Microsoft Managed Desktop worden deze updates op een vergelijkbare manier geïmplementeerd.

We categoriseren de status van beveiligingsupdateversies met de volgende voorwaarden:

- <strong>Huidige:</strong> Apparaten met de update die in de huidige maand is uitgebracht
- <strong>Vorige:</strong> Apparaten met de update die in de vorige maand is uitgebracht
- <strong>Ouder:</strong> Apparaten met een beveiligingsupdate die vóór de vorige maand is uitgebracht

U ziet weinig apparaten <strong></strong> in de categorie Ouder. Een grote of groeiende populatie geeft waarschijnlijk een systeemprobleem aan dat u moet rapporteren aan Microsoft Managed Desktop zodat we dit kunnen onderzoeken.


## <a name="deployment-progress"></a>Implementatie-voortgang

Aan het begin van elke releasecyclus voor beveiligingsupdates maakt Microsoft Managed Desktop momentopname van de apparaatpopulatie en stelt u het implementatiedoel in op 95% van die populatie. Het <strong>gebied Implementatie-voortgang</strong> toont een historische trend die dagelijks wordt bijgewerkt en die bij houdt hoe nauw de update-implementatie aan dit doel voor elke release voldoet. In deze grafiek ziet u alleen apparaten met de actieve status.

U kunt deze gegevens voor eerdere updatecyclussen bekijken met behulp van de vervolgkeuzelijst in de rechterbovenhoek. De periode die u in dit menu selecteert, is van toepassing op alle informatie op de hele pagina.

Het <strong>gebied Bijgewerkte actieve apparaten per</strong> implementatiegroep biedt een andere weergave door de voortgang van de update-installatie weer te geven voor elk van de Microsoft Managed Desktop implementatiegroepen.

In <strong>het doelgebied</strong> Dagen wordt weergegeven hoe lang het duurde voordat 95% van het totale aantal apparaten werd bijgewerkt met de huidige beveiligingsupdate. Terwijl de implementatie aan de gang is, wordt in dit gebied <strong>Nog steeds</strong> bijgewerkt weergegeven totdat het doel van 95% is bereikt voor de geselecteerde update.

## <a name="device-details-area"></a>Gebied met apparaatdetails

De onderkant van het dashboard is een tabel met gedetailleerde informatie voor uw apparaten, waaronder de [apparaatstatus](#device-status) en de [versiestatus Bijwerken.](#update-version-status) U kunt in deze lijst zoeken of filteren op elke weergegeven waarde.


![Tabel apparaatdetails met kolommen voor de naam van het apparaat, de toegewezen gebruiker, de apparaatstatus, de updateversie, de versie van het besturingssysteem en de datum waarop het apparaat het laatst is gesynchroniseerd.](../../media/security-update-insights-device-table-sterile.png)
