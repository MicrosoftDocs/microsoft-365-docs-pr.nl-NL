---
title: Een gebruikersaccount onderzoeken in Microsoft Defender ATP
description: Onderzoek een gebruikersaccount naar mogelijke gecompromitteerde referenties of draaipunt op het bijbehorende gebruikersaccount tijdens een onderzoek.
keywords: onderzoeken, account, gebruiker, gebruikersentiteit, waarschuwing, microsoft defender atp
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: e79e558a7d256c46178e91b89bff27bfa6893ce9
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186711"
---
# <a name="investigate-a-user-account-in-microsoft-defender-for-endpoint"></a>Een gebruikersaccount onderzoeken in Microsoft Defender voor Eindpunt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatgeuser-abovefoldlink)

## <a name="investigate-user-account-entities"></a>Entiteiten van gebruikersaccounts onderzoeken

Identificeer gebruikersaccounts met de meest actieve waarschuwingen (weergegeven op het dashboard als 'Gebruikers met risico') en onderzoek gevallen van mogelijke gecompromitteerde referenties, of draai in het bijbehorende gebruikersaccount bij het onderzoeken van een waarschuwing of apparaat om mogelijke zijbewegingen tussen apparaten met dat gebruikersaccount te identificeren.

U kunt gebruikersaccountgegevens vinden in de volgende weergaven:

- Dashboard
- Waarschuwingswachtrij
- Pagina Apparaatdetails

Er is een klikbare koppeling voor gebruikersaccounts beschikbaar in deze weergaven, die u naar de pagina met gebruikersaccountgegevens gaat waar meer informatie over het gebruikersaccount wordt weergegeven.

Wanneer u een entiteit van een gebruikersaccount onderzoekt, ziet u:

- Gebruikersaccountgegevens, Azure Advanced Threat Protection -waarschuwingen (Azure ATP) en aangemeld op apparaten, rol, aanmeldingstype en andere details
- Overzicht van de incidenten en apparaten van de gebruiker
- Waarschuwingen met betrekking tot deze gebruiker
- Waargenomen in organisatie (apparaten die zijn aangemeld bij)

![Afbeelding van de pagina met de details van de gebruikersaccount-entiteit](images/atp-user-details-view.png)

### <a name="user-details"></a>Gebruikersgegevens

Het **deelvenster** Gebruikersdetails aan de linkerkant bevat informatie over de gebruiker, zoals gerelateerde geopende incidenten, actieve waarschuwingen, SAM-naam, SID, Azure ATP-waarschuwingen, het aantal apparaten waarop de gebruiker is aangemeld, wanneer de gebruiker voor het eerst en het laatst is gezien, rol- en aanmeldingstypen. Afhankelijk van de integratiefuncties die u hebt ingeschakeld, ziet u andere details. Als u bijvoorbeeld de integratie van Skype voor Bedrijven inschakelen, kunt u contact opnemen met de gebruiker via de portal. De **sectie Azure ATP-waarschuwingen** bevat een koppeling die u naar de Azure ATP-pagina gaat, als u de Azure ATP-functie hebt ingeschakeld en er waarschuwingen zijn met betrekking tot de gebruiker. De Azure ATP-pagina geeft meer informatie over de waarschuwingen.

>[!NOTE]
>U moet de integratie op zowel Azure ATP als Defender for Endpoint inschakelen om deze functie te kunnen gebruiken. In Defender voor Eindpunt kunt u deze functie inschakelen in geavanceerde functies. Zie Geavanceerde functies inschakelen voor meer informatie over het inschakelen van [geavanceerde functies.](advanced-features.md)

Het overzicht, waarschuwingen en waargenomen in organisatie zijn verschillende tabbladen die verschillende kenmerken over het gebruikersaccount weergeven.

### <a name="overview"></a>Overzicht

Op **het** tabblad Overzicht ziet u de details van incidenten en een lijst met de apparaten waar de gebruiker zich bij heeft aangemeld. U kunt deze uitv vouwen om de details van de logboekgebeurtenissen voor elk apparaat te bekijken.

### <a name="alerts"></a>Waarschuwingen

Het **tabblad** Waarschuwingen bevat een lijst met waarschuwingen die zijn gekoppeld aan het gebruikersaccount. Deze lijst is een gefilterde weergave van de waarschuwingswachtrij en toont waarschuwingen waarin de context van de gebruiker het geselecteerde gebruikersaccount is, de datum waarop de laatste activiteit is gedetecteerd, een korte beschrijving van de waarschuwing, het apparaat dat aan de waarschuwing is gekoppeld, de ernst van de waarschuwing, de status van de waarschuwing in de wachtrij en wie de waarschuwing heeft toegewezen. [](alerts-queue.md)

### <a name="observed-in-organization"></a>Waargenomen in organisatie

Op het tabblad Waargenomen **in** organisatie kunt u een datumbereik opgeven om een lijst weer te geven met apparaten waarop deze gebruiker is aangemeld, het meest voorkomende en minst vaak aangemelde gebruikersaccount voor elk van deze apparaten en het totaal aantal waargenomen gebruikers op elk apparaat.

Als u een item selecteert in de tabel Waargenomen in organisatie, wordt het item uitgebreid, met meer informatie over het apparaat. Als u rechtstreeks een koppeling in een item selecteert, wordt u naar de bijbehorende pagina doorsturen.

## <a name="search-for-specific-user-accounts"></a>Specifieke gebruikersaccounts zoeken

1. Selecteer **Gebruiker** in de **vervolgkeuzelijst** Zoekbalk.
2. Voer het gebruikersaccount in het **veld Zoeken** in.
3. Klik op het zoekpictogram of druk op **Enter.**

Er wordt een lijst met gebruikers weergegeven die overeenkomen met de querytekst. U ziet het domein en de naam van het gebruikersaccount, wanneer het gebruikersaccount voor het laatst is gezien, en het totale aantal apparaten waarop het is geregistreerd in de afgelopen 30 dagen.

U kunt de resultaten filteren op de volgende tijdsperioden:

- 1 dag
- 3 dagen
- 7 dagen
- 30 dagen
- 6 maanden

## <a name="related-topics"></a>Verwante onderwerpen

- [De wachtrij waarschuwingen voor Microsoft Defender voor eindpunten weergeven en ordenen](alerts-queue.md)
- [Waarschuwingen voor Microsoft Defender voor eindpunten beheren](manage-alerts.md)
- [Microsoft Defender onderzoeken voor eindpuntwaarschuwingen](investigate-alerts.md)
- [Een bestand onderzoeken dat is gekoppeld aan een waarschuwing van Defender voor eindpunt](investigate-files.md)
- [Apparaten onderzoeken in de lijst Defender voor eindpuntapparaten](investigate-machines.md)
- [Een IP-adres onderzoeken dat is gekoppeld aan een waarschuwing van Defender voor eindpunt](investigate-ip.md)
- [Een domein onderzoeken dat is gekoppeld aan een waarschuwing van Defender voor eindpunt](investigate-domain.md)
