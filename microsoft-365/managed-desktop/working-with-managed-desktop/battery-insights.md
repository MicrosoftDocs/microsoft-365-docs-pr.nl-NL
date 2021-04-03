---
title: Inzichten in batterijen
description: Een rapport met gegevens over de voorspelde levensduur van de batterij en de beste consumenten van stroomverbruikers
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 32ab3a984d5ab46aac26989518cd3e570082d688
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579708"
---
# <a name="battery-insights"></a>Inzichten in batterijen
Deze weergave biedt metrische energie, batterij en app-gebruik voor uw Microsoft Managed Desktop-apparaten. Voor deze doeleinden wordt een app beschouwd als 'in gebruik' als deze wordt uitgevoerd en in focus staat.

Als u gebruiksgegevens wilt weergeven, selecteert u het **tabblad** Batterij.

![Batterijdeelvenster: voorspelde levensduur van de batterij per apparaatmodel in de linkerbovenhoek, beste energieverbruikers (per app) in de rechterbovenhoek, inzichtentabel aan de onderkant. Koppeling documentatie in de rechterbovenhoek](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a>Voorspelde levensduur van de batterij

In het **gebied Voorspelde levensduur** van de batterij geven we voorspellingen voor de verwachte levensduur van de batterij voor uw apparaten, ingedeeld per apparaatmodel.

> [!NOTE]
> Deze gegevens zijn afgeleid van het gebruik van energie, <em></em> de gebruiksduur en de batterijcapaciteit van een willekeurige selectie van de apparaten in uw Microsoft Managed Desktop-implementatie die ook gegevens rapporteren.

De tabel bevat de voorspelde levensduur van de batterij (in uren), de gemiddelde levensduur van de batterij voor dezelfde modellen in andere Microsoft Managed Desktop-implementaties en het aantal apparaten dat deze gegevens in uw omgeving rapporteert. Sorteer de gegevens door de kolomkoppen te selecteren.



## <a name="top-energy-consumers"></a>Beste energieverbruikers

In het **gebied Top energy consumers** vindt u de apps in uw omgeving die de meeste energie verbruiken in milliWatt-uren (mWh). De weergegeven apps zijn per specifiek apparaat, dat u selecteert in de sectie **Voorspelde** batterijduur aan de linkerkant. Als u bijvoorbeeld het verbruik per app wilt zien voor uw Microsoft Surface Book 2-apparaten, selecteert u die rij in het batterijduurgebied. Als u geen model selecteert, zijn de weergegeven verbruiksgegevens voor apps voor alle apps waar we gegevens voor hebben.

 In gekleurde segmenten voor elke app ziet u de verdeling van het energiegebruik van de app over deze categorieën:

- CPU
- Weergeven
- Netwerk
- Overige

'Overige' kan het energieverbruik omvatten van diverse bronnen, zoals schijfactiviteit, mobiel breedbandgebruik en energie die verloren gaat door interne weerstand. 

U kunt deze weergave filteren om alleen voorgrond-apps, achtergrond-apps of beide weer te geven met behulp van het menu in de rechterbovenhoek. Voorgrond-apps zijn apps die de afgelopen 28 dagen interactie hebben gehad met de gebruiker, zoals het selecteren van iets met een muis.

## <a name="insights"></a>Inzichten

In **het gebied** Inzichten ziet u de drie beste energieverbruikers in de cpu- en netwerkcategorieën. Deze items verbruiken meer dan gemiddelde energie in vergelijking met alle Microsoft Managed Desktop-implementaties. De weergaveresource wordt niet weergegeven, omdat deze sterk afhankelijk is van de tijd van apparaatgebruik en de schermhelderheidsinstellingen. 

Selecteer de vermeldingen in de **kolom Details** voor meer informatie.

## <a name="battery-optimization"></a>Batterijoptimalisatie

Windows 10 biedt talloze [apparaatinstellingen om](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) het stroomverbruik te verbeteren en de levensduur van de batterij van uw Microsoft Managed Desktop-apparaten te verbeteren. Sommige van deze instellingen kunnen andere Windows-functionaliteit verminderen, dus u moet ook rekening houden met andere factoren, zoals de rol van het apparaat in uw organisatie. Windows-ondersteuning onderhoudt een lijst met deze [tips voor batterijbesparing.](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)

Gebruikers kunnen bepaalde instellingen zelf aanpassen zonder dat ze de beheerder hoeven te verheffing of ondersteuning nodig hebben. Voor andere instellingen is ondersteuning nodig van de IT-beheerder van uw organisatie.
