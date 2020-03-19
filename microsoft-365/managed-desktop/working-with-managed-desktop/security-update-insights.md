---
title: Inzichten over Windows-beveiligingsupdate
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: ef2d5c897709e7f7d2484d032b7471031be77d74
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/29/2020
ms.locfileid: "42805586"
---
# <a name="windows-security-update-insights"></a>Inzichten over Windows-beveiligingsupdate
In deze weergave vindt u een overzicht van de status van beveiligingsupdates voor uw Microsoft Managed Desktop-apparaten. 

Als u gebruiksgegevens wilt weergeven, selecteert u het tabblad <strong>Windows-beveiligingsupdates.</strong>

![Windows-beveiligingsupdates: weergrafieken van de apparaatstatus en updateversie in de linkerkolom, update implementatievoortgang in de loop van de tijd in middelste kolom en percentage actieve apparaten per implementatiegroep, evenals het aantal dagen dat nodig is om de implementatie van 95% te bereiken doel in de rechterkolom.](../../media/update-insights.jpg)

## <a name="device-status"></a>Apparaatstatus

Voor apparaten die door Windows Update moeten worden bijgewerkt, moeten ze zijn verbonden met het internet en niet gedurende minimaal zes uur in de sluimerstand zijn, waarvan er twee continu moeten zijn. Zolang een apparaat is aangesloten en niet in de sluimerstand, wordt het beschouwd als "in gebruik." Hoewel het mogelijk is dat een apparaat dat niet aan deze vereisten voldoet, wordt bijgewerkt, hebben apparaten die eraan voldoen de grootste kans om te worden bijgewerkt. 

We categoriseren apparaatactiviteit in de context van Windows Update met de volgende termen:

- <strong>Actief:</strong> Apparaten die hebben voldaan aan de minimale gebruikscriteria (zes uur, twee continu) voor de meest recente versie van de beveiligingsupdate en ten minste om de vijf dagen hebben ingecheckt bij Microsoft Intune
- <strong>Gesynchroniseerd:</strong> Apparaten die in de afgelopen 28 dagen zijn ingecheckt bij Intune
- <strong>Niet synchroon:</strong> Apparaten die de afgelopen 28 dagen <i>niet</i> zijn ingecheckt bij Intune




## <a name="update-version-status"></a>Versiestatus bijwerken

Microsoft brengt elke tweede dinsdag van de maand beveiligingsupdates uit. Elke release voegt belangrijke updates toe voor bekende beveiligingsproblemen. Microsoft Managed Desktop zorgt ervoor dat 95% van de beheerde apparaten elke maand wordt bijgewerkt met de nieuwste beschikbare beveiligingsupdate. Beveiligingsupdates worden soms op andere momenten uitgebracht om nieuwe bedreigingen dringend aan te pakken. Microsoft Managed Desktop implementeert deze updates op een vergelijkbare manier.

We categoriseren de status van beveiligingsupdateversies met de volgende voorwaarden:

- <strong>Stroom:</strong> Apparaten waarop de update wordt uitgevoerd die in de huidige maand is uitgebracht
- <strong>Vorige:</strong> Apparaten met de update die in de vorige maand is uitgebracht
- <strong>Ouder:</strong> Apparaten met een beveiligingsupdate die vóór de vorige maand is uitgebracht

U ziet weinig apparaten in de <strong>oudere</strong> categorie - een grote of groeiende populatie duidt waarschijnlijk op een systemisch probleem dat u moet rapporteren aan Microsoft Managed Desktop, zodat we dit kunnen onderzoeken.


## <a name="deployment-progress"></a>Implementatievoortgang

Aan het begin van elke releasecyclus van elke beveiligingsupdate maakt Microsoft Managed Desktop een momentopname van de apparaatpopulatie en stelt het implementatiedoel in op 95% van die populatie. Het <strong>voortgangsgebied Implementatie</strong> toont een historische trend, die dagelijks wordt bijgewerkt en bijhoudt hoe nauw de update-implementatie aan dit doel voldoet voor elke release. Deze grafiek toont alleen apparaten met de actieve status.

U deze gegevens voor eerdere updatecycli bekijken met behulp van het vervolgkeuzemenu rechtsboven. De periode die u selecteert in dit menu is van toepassing op alle informatie op de hele pagina.

Het gebied <strong>Actieve apparaten bijgewerkt op implementatiegroep</strong> biedt een andere weergave door de voortgang van de update-installatie voor elk van de microsoft Managed Desktop-implementatiegroepen weer te geven.

De <strong>dagen om het doelgebied te bereiken,</strong> geeft aan hoe lang het duurde voordat 95% van het totale aantal apparaten werd bijgewerkt met de huidige beveiligingsupdate. Terwijl de implementatie aan de gang is, wordt in dit gebied <strong>nog steeds bijgewerkt</strong> totdat de doelstelling van 95% is bereikt voor de geselecteerde update.

## <a name="device-details-area"></a>Gebied Apparaatdetails

Onder aan het dashboard vindt u een tabel met gedetailleerde informatie voor uw apparaten, waaronder de [apparaatstatus](#device-status) en de [status van de updateversie.](#update-version-status) U deze lijst doorzoeken of filteren op een vermelde waarde.


![Tabel Met tabel met apparaatdetails met kolommen voor apparaatnaam, toegewezen gebruiker, apparaatstatus, updateversie, versie van het besturingssysteem en de datum waarop het apparaat het laatst is gesynchroniseerd.](../../media/security-update-insights-device-table-sterile.png)
