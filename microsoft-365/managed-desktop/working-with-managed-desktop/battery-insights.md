---
title: Batterij-inzichten
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 434f62d5ddfc8bc75c54de422aafc8c6325c4086
ms.sourcegitcommit: 1c445d68e54ca4249024ca4bb72460dd6fac0a2d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/20/2020
ms.locfileid: "42812075"
---
# <a name="battery-insights"></a>Batterij-inzichten
Deze weergave biedt statistieken over stroom-, batterij- en app-gebruik voor uw Microsoft Managed Desktop-apparaten. Voor deze doeleinden wordt een app beschouwd als "in gebruik" als deze wordt uitgevoerd en scherp is.

Als u gebruiksgegevens wilt weergeven, selecteert u het tabblad **Batterij.**

![Batterijvenster: voorspelde levensduur van de batterij per apparaatmodel linksboven, topenergieverbruikers (via app) rechtsboven, tabel met inzichten aan de onderkant. Documentatielink rechtsboven.](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a>Voorspelde levensduur van de batterij

In het **voorspelde batterijduurgebied** bieden we voorspellingen voor de verwachte levensduur van de batterij voor uw apparaten, georganiseerd op apparaatmodel.

> [!NOTE]
> Deze gegevens zijn afgeleid van het samplen van energieverbruik, gebruikstijd en batterijcapaciteit van een willekeurige <em>selectie</em> van de apparaten in uw Microsoft Managed Desktop-implementatie die ook gegevens rapporteren.

De tabel biedt de voorspelde levensduur van de batterij (in uren), de gemiddelde levensduur van de batterij voor dezelfde modellen in andere Microsoft Managed Desktop-implementaties en het aantal apparaten dat deze gegevens in uw omgeving rapporteert. Sorteer de gegevens door de kolomkoppen te selecteren.



## <a name="top-energy-consumers"></a>Top energieverbruikers

In de top **van energieconsumenten** vind je de apps in je omgeving die de meeste energie verbruiken in milliWatt-uren (mWh). De getoonde apps zijn per specifiek apparaat, dat u selecteert in de sectie **Voorspelde levensduur van** de batterij aan de linkerkant. Als u bijvoorbeeld het verbruik per app voor uw Microsoft Surface Book 2-apparaten wilt zien, selecteert u die rij in het gebied van de levensduur van de batterij. Als u geen model selecteert, zijn de weergegeven gegevens over het app-verbruik voor alle apps waarvoor we gegevens gezamenlijk hebben.

 Voor elke app tonen gekleurde segmenten u de verdeling van het energieverbruik van de app over deze categorieën:

- Cpu
- Weergeven
- Netwerk
- Andere

"Andere" kunnen het energieverbruik door verschillende bronnen omvatten, zoals schijfactiviteit, mobiel breedbandgebruik en energie die verloren gaat aan interne weerstand. 

U deze weergave filteren om alleen apps op de voorgrond, achtergrond-apps of beide weer te geven met behulp van het menu rechtsboven. Voorgrond-apps zijn apps die de afgelopen 28 dagen interactie met gebruikers hebben gehad, zoals het selecteren van iets met een muis.

## <a name="insights"></a>Inzichten

Het **insights-gebied** toont de top drie van energieconsumenten in de CPU- en netwerkcategorieën. Deze items verbruiken meer dan gemiddelde energie in vergelijking met alle Microsoft Managed Desktop-implementaties. We tonen de weergavebron niet omdat deze sterk afhankelijk is van de gebruikstijd van het apparaat en de instellingen voor schermhelderheid. 

Selecteer de aanbiedingen in de kolom **Details** voor meer informatie.

## <a name="battery-optimization"></a>Batterijoptimalisatie

Windows 10 biedt tal van [apparaatinstellingen](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) om het energieverbruik te verbeteren en de levensduur van de batterij van uw Microsoft Managed Desktop-apparaten te verhogen. Sommige van deze instellingen kunnen andere Windows-functionaliteit verminderen, dus u moet ook rekening houden met andere factoren, zoals de rol van het apparaat in uw organisatie. Windows-ondersteuning houdt een lijst bij van deze [tips voor batterijbesparing.](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)

Gebruikers kunnen sommige instellingen zelf aanpassen zonder dat er beheerdersverhoging of ondersteuning nodig is. Andere instellingen vereisen ondersteuning van de IT-beheerder van uw organisatie.
