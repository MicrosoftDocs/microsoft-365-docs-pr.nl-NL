---
title: Buffertijd instellen in Microsoft Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 271f43e4-b8f7-4d63-8059-b5747679bb7e
description: Stel buffertijd in voor of na een afspraak in Microsoft Bookings om tijd toe te staan voor het opruimen of opnieuw instellen van apparatuur.
ms.openlocfilehash: 882ab0340fe56976429ed8294f2fa386b801941f
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962345"
---
# <a name="set-buffer-time-in-microsoft-bookings"></a>Buffertijd instellen in Microsoft Bookings

Voor sommige afspraken is mogelijk tijd nodig vóór of nadat u met uw klant hebt vergaderd om uw ruimte en apparatuur in te stellen, op te schonen of opnieuw in te stellen. Of als u onderweg bent tussen klantafspraken, hebt u mogelijk tijd nodig om ervoor te zorgen dat u en uw team tussen afspraken kunnen reizen zonder dat de klant hoeft te wachten.

U kunt buffertijd instellen voordat afspraken beginnen, na het einde van afspraken, of beide om het personeel de extra tijd te geven die ze nodig hebben om zich voor te bereiden op hun volgende afspraak.

## <a name="set-buffer-time-defaults"></a>Standaardwaarden voor buffertijd instellen

Standaardwaarden voor buffertijd worden ingesteld op de **pagina Servicedetails** in Bookings. Net als alle standaardserviceinstellingen die op deze pagina zijn ingesteld, kunnen deze standaardinstellingen door u worden bewerkt voor een specifieke reservering om aan specifieke klantbehoeften te voldoen.

De instelling buffertijd vindt u net onder de **standaardduur** pickers op de **pagina Servicedetails.** Voordat deze voor een bepaalde service kan worden ingesteld, moet u de instelling buffertijd inschakelen door de schakelknop buffertijd te selecteren. Hierdoor worden de  **vervolgkeuze-downs** Voor en Na weergegeven, die worden gebruikt om de standaardtijd voor en na elke reservering te kiezen, zoals hier wordt weergegeven:

   ![Afbeelding van Bookings met buffertijd ingeschakeld](../media/bookings-buffertime.png)

## <a name="buffer-time-and-appointment-timing"></a>Buffertijd en tijdsinstelling van afspraken

Om verwarring te voorkomen over wanneer klanten u verwachten te ontmoeten, worden de buffertijd en het werkelijke tijdstip van de afspraak (het tijdstip waarop klanten u verwachten te ontmoeten) in Bookings in de agenda en in e-mailbevestigingen en herinneringen voor het betreffende personeel vermeld. Hieronder ziet u bijvoorbeeld wat u zou zien in Bookings voor een afspraak met een klant die 15 minuten buffertijd vóór afspraak bevat.

U ziet dat de gebeurtenis zelf (links in de onderstaande afbeelding) een lichtere arcering toont voor de buffertijd en een donkerdere arcering voor de werkelijke afspraak met de klant. In het afspraakoproepgesprek (dat wordt geopend wanneer u de gebeurtenis selecteert) wordt specifiek vermeld dat de afspraak is van 9:00 tot 10:00 am met Katie Jordan en 15 minuten buffertijd voor de afspraak en 0 minuten na de afspraak bevat. Bevestigingen en herinneringen aan personeel verwijzen op dezelfde manier naar specifieke buffer- en afspraaktijd, terwijl de klant alleen bevestigingen en herinneringen ontvangt die verwijzen naar een afspraaktijd van 9:00 tot 10:00 uur.

   ![Afbeelding van reserveringsafroep met buffertijd](../media/bookings-buffertime-callout.png)

## <a name="buffer-time-and-availability"></a>Buffertijd en beschikbaarheid

Uw klanten zien de buffertijden die u hebt ingesteld niet rechtstreeks en kunnen deze niet wijzigen. Omdat buffertijd echter wordt gebruikt om de totale duur van de service te berekenen, zien klanten u en uw relevante personeel als geboekt tijdens zowel buffer- als reguliere afspraaktijden. Klanten zien ook alleen de beschikbaarheid voor u en uw personeel als er voldoende tijd is voor zowel de afspraak als de buffertijd.

Een afspraak van één uur met een buffertijd van 15 minuten vóór afspraak vereist bijvoorbeeld een beschikbare tijdsblok van ten minste 1 uur en 15 minuten. Een afspraak voor deze service zou daarom een tijdsblok van 75 minuten in uw agenda vullen en heeft 75 minuten beschikbaarheid nodig om zonder conflict te kunnen boeken.
