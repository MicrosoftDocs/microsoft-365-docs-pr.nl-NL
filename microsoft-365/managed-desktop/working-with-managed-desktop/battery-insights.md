---
title: Inzichten in batterijen
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f339fc98ea94c291c533045e9906f626f4b74e2a
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529837"
---
# <a name="battery-insights"></a>Inzichten in batterijen
Deze weergave biedt stroom-, batterij- en app-gebruiksstatistieken voor uw Microsoft Managed Desktop-apparaten. Voor deze doeleinden wordt een app beschouwd als 'in gebruik' als deze wordt uitgevoerd en scherp is.

Als u gebruiksgegevens wilt **weergeven,** selecteert u het tabblad Batterij.

![Batterijvenster: voorspelde levensduur van de batterij per apparaatmodel in de linkerbovenhoek, bovenenergieconsumenten (per app) in de rechterbovenhoek, insights tabel aan de onderkant. Documentatiekoppeling rechtsboven.](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a>Voorspelde levensduur van de batterij

In het gebied **Met de voorspelde levensduur** van de batterij geven we voorspellingen voor de verwachte levensduur van de batterij voor uw apparaten, georganiseerd op apparaatmodel.

> [!NOTE]
> Deze gegevens zijn afgeleid van het energieverbruik, de gebruiksduur en de batterijcapaciteit van een willekeurige <em>selectie</em> van de apparaten in uw Microsoft Managed Desktop-implementatie die ook gegevens rapporteren.

De tabel biedt de voorspelde levensduur van de batterij (in uren), de gemiddelde levensduur van de batterij voor dezelfde modellen in andere Microsoft Managed Desktop-implementaties en het aantal apparaten dat deze gegevens in uw omgeving rapporteert. Sorteer de gegevens door de kolomkoppen te selecteren.



## <a name="top-energy-consumers"></a>Top energieverbruikers

In de **top van de energieverbruikers** vindt u de apps in uw omgeving die de meeste energie verbruiken in milliWatt-uren (mWh). De weergegeven apps zijn per specifiek apparaat, dat u selecteert in de sectie **Voorspelde levensduur** van de batterij aan de linkerkant. Als u bijvoorbeeld het verbruik per app voor uw Microsoft Surface Book 2-apparaten wilt bekijken, selecteert u die rij in het gebied van de levensduur van de batterij. Als u geen enkel model selecteert, worden de weergegeven gegevens voor het verbruik van apps weergegeven voor alle apps waarvoor we gezamenlijk gegevens hebben.

 Voor elke app tonen gekleurde segmenten u de verdeling van het energieverbruik van de app over deze categorieën:

- Cpu
- Weergeven
- Netwerk
- Overige

"Andere" kan het energieverbruik van verschillende bronnen omvatten, zoals schijfactiviteit, mobiel breedbandgebruik en energie die verloren is gegaan door interne weerstand. 

U deze weergave filteren om alleen apps op de voorgrond, achtergrond-apps of beide weer te geven met behulp van het menu rechtsboven. Voorgrond apps zijn die gebruikersinteractie hebben gehad in de afgelopen 28 dagen, zoals het selecteren van iets met een muis.

## <a name="insights"></a>Inzichten

Het **insights-gebied** toont de top drie van energieconsumenten in de CPU- en netwerkcategorieën. Deze items verbruiken meer dan gemiddelde energie in vergelijking met alle Microsoft Managed Desktop-implementaties. We tonen de weergavebron niet omdat deze sterk afhankelijk is van de gebruikstijd van het apparaat en de instellingen voor schermhelderheid. 

Selecteer de aanbiedingen in de kolom **Details** voor meer informatie.

## <a name="battery-optimization"></a>Batterijoptimalisatie

Windows 10 biedt tal van [apparaatinstellingen](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) om het energieverbruik te verbeteren en de levensduur van de batterij van uw Microsoft Managed Desktop-apparaten te verlengen. Sommige van deze instellingen kunnen andere Windows-functionaliteit verminderen, dus u moet ook rekening houden met andere factoren, zoals de rol van het apparaat in uw organisatie. Windows-ondersteuning houdt een lijst bij van deze tips voor het opslaan van [batterijen.](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)

Gebruikers kunnen sommige instellingen zelf aanpassen zonder dat ze beheerdersverhoging of -ondersteuning nodig hebben. Andere instellingen vereisen ondersteuning van de IT-beheerder van uw organisatie.
