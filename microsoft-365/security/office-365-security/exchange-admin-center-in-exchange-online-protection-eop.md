---
title: Exchange-beheercentrum in Exchange Online Protection
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: Het Exchange-beheercentrum (EAC) is de webgebaseerde beheerconsole voor Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: 3b5fb014e56a9928d58abffd5e4c96e1eef463ad
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42812426"
---
# <a name="exchange-admin-center-in-exchange-online-protection"></a>Exchange-beheercentrum in Exchange Online Protection

Het Exchange-beheercentrum (EAC) is de webgebaseerde beheerconsole voor Microsoft Exchange Online Protection (EOP).

Op zoek naar de Exchange Server-versie van dit onderwerp? Zie [Exchange-beheercentrum in Exchange Server](https://docs.microsoft.com/exchange/architecture/client-access/exchange-admin-center).

Op zoek naar de Exchange Online versie van dit onderwerp? Zie [Exchange-beheercentrum in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

## <a name="accessing-the-eac"></a>Toegang tot de EAC

In de meeste gevallen krijgen EOP-klanten toegang tot de EAC via het Microsoft 365-beheercentrum. U vindt een link naar EOP in het vervolgkeuzemenu in de tegel **Beheerder,** die naast de tegel **Ik** staat. Klik op de tegel **Beheerder** en selecteer **Exchange Online Protection** in het vervolgkeuzemenu dat naar de EAC moet worden gebracht.

U ook rechtstreeks via de volgende URL `https://admin.protection.outlook.com/ecp/<companydomain>`toegang krijgen tot de eac-aanmeldingspagina:. Bijvoorbeeld `https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com`. Na het opgeven van uw gebruikersreferenties wordt u rechtstreeks naar de EAC gebracht.

## <a name="common-user-interface-elements-in-the-eac"></a>Veelvoorkomende gebruikersinterface-elementen in de EAC

In deze sectie worden de elementen van de gebruikersinterface beschreven die in de EAC worden gevonden.

![EOP-Beheercentrum](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a>Functievenster

Dit is het eerste navigatieniveau voor de meeste taken die u in de EAC uitvoert. Het functievenster is ingedeeld op functiegebieden.

1. **Geadresseerden:** hier ziet u interne gebruikers en externe contactpersonen.

2. **Machtigingen:** hier beheert u beheerdersrollen.

3. **Compliance Management:** Hier vindt u controlelogboeken en rapporten, zoals het rapport van de groep beheerdersfuncties.

4. **Bescherming:** Hier beheert u anti-malware- en antispambescherming voor uw organisatie en beheert u berichten in quarantaine.

5. **Mail Flow:** Hier beheert u regels, geaccepteerde domeinen en connectoren en waar u naartoe gaat om berichttracering uit te voeren.

### <a name="tabs"></a>Tabbladen

De tabbladen zijn uw tweede niveau van navigatie. Elk van de functiegebieden bevat verschillende tabbladen, die elk een functie vertegenwoordigen.

### <a name="toolbar"></a>Werkbalk

Wanneer u op de meeste tabbladen klikt, ziet u een werkbalk. De werkbalk heeft pictogrammen die een specifieke actie uitvoeren. In de volgende tabel worden de pictogrammen en hun acties beschreven.

|**Pictogram**|**Naam**|**Actie**|
|:-----|:-----|:-----|
|![Pictogram toevoegen](../../media/ITPro-EAC-AddIcon.gif)|Toevoegen, Nieuw|Gebruik dit pictogram om een nieuw object te maken. Sommige van deze pictogrammen hebben een bijbehorende pijl-omlaag waarop u klikken om extra objecten weer te geven die u maken.|
|![Pictogram Bewerken](../../media/ITPro-EAC-EditIcon.gif)|Bewerken|Gebruik dit pictogram om een object te bewerken.|
|![Pictogram Verwijderen](../../media/ITPro-EAC-DeleteIcon.gif)|Verwijderen|Gebruik dit pictogram om een object te verwijderen. Sommige verwijderpictogrammen hebben een pijl-omlaag waarop u klikken om extra opties weer te geven.|
|![Pictogram Zoeken](../../media/ITPro-EAC-.gif)|Zoek|Gebruik dit pictogram om een zoekvak te openen waarin u de zoekterm typen voor een object dat u wilt vinden.|
|![Pictogram Vernieuwen](../../media/ITPro-EAC-RefreshIcon.gif)|Vernieuwen|Gebruik dit pictogram om de lijstweergave te vernieuwen.|
|![Pictogram Meer opties](../../media/ITPro-EAC-MoreOptionsIcon.gif)|Meer opties|Gebruik dit pictogram om meer acties weer te geven die u voor de objecten van dat tabblad uitvoeren. In ** \> Ontvangers** die bijvoorbeeld op dit pictogram klikken, wordt de optie weergegeven om een **geavanceerd zoeken**uit te voeren.|
|![Pictogram Pijl-omhoog](../../media/ITPro-EAC-UpArrowIcon.gif)![Pictogram Pijl-omlaag](../../media/ITPro-EAC-DownArrowIcon.gif)|Pijl-omhoog en pijl-omlaag|Gebruik deze pictogrammen om de prioriteit van een object omhoog of omlaag te verplaatsen.|
|![Pictogram Verwijderen](../../media/ITPro-EAC-RemoveIcon.gif)|Verwijderen|Gebruik dit pictogram om objecten uit een lijst te verwijderen.|

### <a name="list-view"></a>Lijstweergave

Wanneer u een tabblad selecteert, ziet u in de meeste gevallen een lijstweergave. De zichtbaarbare limiet met de EAC-lijstweergave is ongeveer 10.000 objecten. Bovendien is paging opgenomen, zodat u pagina naar resultaten.

### <a name="details-pane"></a>Details venster

Wanneer u een object selecteert in de lijstweergave, wordt informatie over dat object weergegeven in het detailvenster. In sommige gevallen bevat het detailvenster beheertaken.

### <a name="me-tile-and-help"></a>Mijn tegel en Help

Met de tegel **Ik** u de EAC afmelden en u als andere gebruiker aanmelden. In het vervolgkeuzemenu Help-pictogram-pictogram **Help**![](../../media/ITPro-EAC-HelpIcon.gif) u de volgende acties uitvoeren:

1. **Help:** ![Klik](../../media/ITPro-EAC-HelpIcon.gif) op Help-pictogram om de online help-inhoud te bekijken.

2. **Help-bel uitschakelen:** in de Help-bel worden contextuele help voor velden weergegeven wanneer u een object maakt of bewerkt. U de Help-bel uitschakelen of inschakelen als deze is uitgeschakeld.

3. **Auteursrecht**: Klik op deze link om de copyright verklaring voor Exchange Online Protection te lezen.

4. **Privacy**: Klik hier om het privacybeleid voor Exchange Online Protection te lezen.

## <a name="supported-browsers"></a>Ondersteunde browsers

Voor de beste ervaring met de EAC raden we u aan altijd de nieuwste browsers, Office-clients en apps te gebruiken. We raden u ook aan software-updates te installeren wanneer deze beschikbaar zijn. Zie [Systeemvereisten voor Office voor](https://products.office.com/office-system-requirements)meer informatie over de ondersteunde browsers en systeemvereisten voor de service.

## <a name="supported-languages-in-eop"></a>Ondersteunde talen in EOP

De volgende talen worden ondersteund en beschikbaar voor Exchange Online Protection.

- Amharic

- Arabisch

- Baskisch (Baskisch)

- Bengaals (India)

- Bulgaars

- Catalaans

- Chinees (vereenvoudigd)

- Chinees (traditioneel)

- Kroatisch

- Tsjechisch

- Deens

- Nederlands

- Nederlands

- Engels

- Estisch

- Filipijns (Filippijnen)

- Fins

- Frans

- Galicisch

- Duits

- Grieks

- Gujarati

- Hebreeuws

- Hindi

- Hongaars

- IJslands

- Indonesisch

- Italiaans

- Japans

- Kannada

- Kazachstaans

- Kiswahili

- Koreaans

- Lets

- Litouws

- Maleis (Brunei Darussalam)

- Maleis (Maleisië)

- Malajalam

- Marathi

- Noors (Bokmål)

- Noors (Nynorsk)

- Oriya

- Perzisch

- Pools

- Portugees (Brazilië)

- Portugees (Portugal)

- Roemeens

- Russisch

- Servisch (Cyrillisch, Servië)

- Servisch (Latijn)

- Slowaaks

- Sloveens

- Spaans

- Zweeds

- Tamil

- Telugu

- Thais

- Turks

- Oekraïens

- Urdu

- Vietnamees

- Welsh


