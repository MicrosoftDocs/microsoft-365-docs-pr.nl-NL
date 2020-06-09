---
title: Exchange-beheercentrum in standalone EOP
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
description: Meer informatie over de webmanagementinterface in standalone Exchange Online Protection (EOP).
ms.openlocfilehash: 777597489e54c642220cb42f0c686b675101897f
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616996"
---
# <a name="exchange-admin-center-in-standalone-eop"></a>Exchange-beheercentrum in standalone EOP

Het Exchange-beheercentrum (EAC) is een webgebaseerde beheerconsole voor standalone Exchange Online Protection (EOP).

Op zoek naar de Exchange Online-versie van dit onderwerp? Zie [Exchange-beheercentrum in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

## <a name="open-the-eac-in-eop"></a>Open de EAC in EOP

Standalone EOP-klanten hebben toegang tot de EAC via de volgende methoden:

- **Vanuit het Microsoft 365-beheercentrum**:

  1. Ga naar <https://admin.microsoft.com> en klik op Alles **weergeven.**

     ![Klik op Alles weergeven in het Microsoft 365-beheercentrum](../../media/m365-center-show-all.png)

  2. Klik in de sectie **Beheercentra** die wordt weergegeven op **Alle beheercentra**.

     ![Klik op Alle beheercentra in het Microsoft 365-beheercentrum](../../media/m365-center-select-all-admin-centers.png)

  3. Klik op de pagina **Alle beheercentra** die wordt weergegeven op **Exchange Online Protection**.

- Ga direct naar `https://admin.protection.outlook.com/ecp/` .

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a>Gemeenschappelijke gebruikersinterface-elementen in de EAC in EOP

In deze sectie worden de elementen van de gebruikersinterface beschreven die in de EAC worden gevonden.

![EOP-AdminCenter](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a>Functievenster

Dit is het eerste navigatieniveau voor de meeste taken die u in de EAC uitvoert. Het functievenster wordt georganiseerd op functiegebieden.

- **Geadresseerden**: hier ziet u groepen en externe contactpersonen.

- **Machtigingen**: hiermee beheert u beheerdersrollen.

- **Compliance Management**: Hier vindt u het rapport van de beheerdersrolgroep en het logboekrapport voor beheerderscontrole.

- **Beveiliging:** hier u anti-malwarebeleid, het standaardverbindingsfilterbeleid en DKIM beheren.

  > [!NOTE]
  > U moet antimalwarebeleid en het standaardfilterbeleid voor verbinding beheren in het Security & Compliance Center. Zie [Anti-malwarebeleid configureren in EOP](configure-anti-malware-policies.md) en [Verbindingsfiltering configureren in EOP](configure-the-connection-filter-policy.md)voor meer informatie.

- **E-mailstroom:** hiermee beheert u e-mailstroomregels (ook wel transportregels genoemd), geaccepteerde domeinen en connectoren, evenals waar u berichttracering uitvoeren.

- **Hybride:** Hier u de [wizard Hybride configuratie](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard)uitvoeren en u de Exchange Online [PowerShell-module](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell)installeren.

### <a name="tabs"></a>Tabbladen

De tabbladen zijn uw tweede niveau van navigatie. Elk van de functiegebieden bevat verschillende tabbladen, die elk een functie vertegenwoordigen.

### <a name="toolbar"></a>Werkbalk

Wanneer u op de meeste tabbladen klikt, ziet u een werkbalk. Op de werkbalk zijn pictogrammen die een specifieke actie uitvoeren. In de volgende tabel worden de pictogrammen en hun acties beschreven.

||||
|---|---|---|
|**Pictogram**|**Naam**|**Actie**|
|![Pictogram toevoegen](../../media/ITPro-EAC-AddIcon.gif)|Toevoegen, Nieuw|Gebruik dit pictogram om een nieuw object te maken. Sommige van deze pictogrammen hebben een bijbehorende pijl-omlaag waarop u klikken om extra objecten weer te geven die u maken.|
|![Pictogram Bewerken](../../media/ITPro-EAC-EditIcon.gif)|Bewerken|Gebruik dit pictogram om een object te bewerken.|
|![Pictogram Verwijderen](../../media/ITPro-EAC-DeleteIcon.gif)|Verwijderen|Gebruik dit pictogram om een object te verwijderen. Sommige verwijderpictogrammen hebben een pijl-omlaag waarop u klikken om extra opties weer te geven.|
|![Pictogram Zoeken](../../media/ITPro-EAC-.gif)|Zoek|Gebruik dit pictogram om een zoekvak te openen waarin u de zoekterm typen voor een object dat u wilt zoeken.|
|![Pictogram Vernieuwen](../../media/ITPro-EAC-RefreshIcon.gif)|Vernieuwen|Gebruik dit pictogram om de lijstweergave te vernieuwen.|
|![Pictogram Meer opties](../../media/ITPro-EAC-MoreOptionsIcon.gif)|Meer opties|Gebruik dit pictogram om meer acties weer te geven die u uitvoeren voor de objecten van dat tabblad. In ontvangers ** \> gebruikers** die op dit pictogram klikken, ziet u bijvoorbeeld de optie om een **geavanceerd zoeken**uit te voeren.|
|![Pictogram Pijl-omhoog](../../media/ITPro-EAC-UpArrowIcon.gif)![Pictogram Pijl-omlaag](../../media/ITPro-EAC-DownArrowIcon.gif)|Pijl-omhoog en pijl-omlaag|Gebruik deze pictogrammen om de prioriteit van een object omhoog of omlaag te verplaatsen.|
|![Pictogram Verwijderen](../../media/ITPro-EAC-RemoveIcon.gif)|Verwijderen|Gebruik dit pictogram om objecten uit een lijst te verwijderen.|
|

### <a name="list-view"></a>Lijstweergave

Wanneer u een tabblad selecteert, ziet u in de meeste gevallen een lijstweergave. De zichtbare limiet met de EAC-lijstweergave is ongeveer 10.000 objecten. Bovendien is paging opgenomen, zodat u pagina naar de resultaten.

### <a name="details-pane"></a>Detailvenster

Wanneer u een object selecteert in de lijstweergave, wordt informatie over dat object weergegeven in het detailvenster. In sommige gevallen bevat het detailvenster beheertaken.

### <a name="me-tile-and-help"></a>Me tegel en Help

Met de tegel **Ik** u de EAC afmelden en u aanmelden als een andere gebruiker. In **Help**het ![ ](../../media/ITPro-EAC-HelpIcon.gif) vervolgkeuzemenu Help-pictogram help u de volgende acties uitvoeren:

- **Help:** klik op ![ Help-pictogram ](../../media/ITPro-EAC-HelpIcon.gif) om de online help-inhoud te bekijken.

- **Feedback**: Feedback geven.

- **Community**: Plaats een vraag om antwoorden te vinden in de communityforums.

- **Help-bel uitschakelen:** in de Help-bel wordt contextuele hulp weergegeven voor velden wanneer u een object maakt of bewerkt. U de Help-bel uitschakelen of inschakelen als deze is uitgeschakeld.

- **Command Logging weergeven**: er wordt een nieuw venster geopend met de gelijkwaardige PowerShell-opdrachten op basis van wat u hebt geconfigureerd in EAC.

## <a name="supported-browsers"></a>Ondersteunde browsers

Voor de beste ervaring met de EAC raden we u aan altijd de nieuwste browsers, Office-clients en -apps te gebruiken. We raden u ook aan software-updates te installeren wanneer deze beschikbaar zijn. Zie [Systeemvereisten voor Office voor](https://products.office.com/office-system-requirements)meer informatie over de ondersteunde browsers en systeemvereisten voor de service.

## <a name="supported-languages"></a>Ondersteunde talen

De volgende talen worden ondersteund en beschikbaar voor de EAC in standalone EOP.

- Amharic

- Arabisch

- Baskisch (Baskisch)

- Bengaals (India)

- Bulgarian

- Catalan

- Chinees (vereenvoudigd)

- Chinees (traditioneel)

- Croatian

- Czech

- Danish

- Dutch

- Dutch

- English

- Estonian

- Filipijns (Filippijnen)

- Finnish

- French

- Galician

- German

- Greek

- Gujarati

- Hebrew

- Hindi

- Hungarian

- IJslands

- Indonesian

- Italian

- Japanese

- Kannada

- Kazakh

- Kiswahili

- Korean

- Latvian

- Lithuanian

- Maleis (Brunei Darussalam)

- Maleis (Maleisië)

- Malajalam

- Marathi

- Noors (Bokmål)

- Noors (Nynorsk)

- Oriya

- Perzisch

- Polish

- Portugees (Brazilië)

- Portugees (Portugal)

- Romanian

- Russian

- Servisch (Cyrillisch, Servië)

- Servisch (Latijn)

- Slovak

- Slovenian

- Spanish

- Swedish

- Tamil

- Telugu

- Thai

- Turkish

- Ukrainian

- Urdu

- Vietnamese

- Welsh
