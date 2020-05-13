---
title: Exchange-beheercentrum in zelfstandige EOP
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
description: Meer informatie over de webbeheerinterface in de zelfstandige Exchange Online Protection (EOP).
ms.openlocfilehash: 378754f2565604236f7ac33e471d1f991238d304
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209728"
---
# <a name="exchange-admin-center-in-standalone-eop"></a>Exchange-beheercentrum in zelfstandige EOP

Het Exchange-beheercentrum (EAC) is een webgebaseerde beheerconsole voor zelfstandige Exchange Online Protection (EOP).

Op zoek naar de Exchange Online-versie van dit onderwerp? Zie [Exchange-beheercentrum in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

## <a name="open-the-eac-in-eop"></a>Open de EAC in EOP

Zelfstandige EOP-klanten hebben toegang tot de EAC via de volgende methoden:

- **Vanuit het Microsoft 365-beheercentrum:**

  1. Ga naar <https://admin.microsoft.com> en klik op Alles **weergeven**.

     ![Klik op Alles weergeven in het Microsoft 365-beheercentrum](../../media/m365-center-show-all.png)

  2. Klik in de sectie **Beheercentra** die wordt weergegeven op **Alle beheercentra**.

     ![Klik op Alle beheercentra in het Microsoft 365-beheercentrum](../../media/m365-center-select-all-admin-centers.png)

  3. Klik op de pagina **Alle beheercentra** die wordt weergegeven op **Exchange Online Protection**.

- Ga direct naar `https://admin.protection.outlook.com/ecp/` .

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a>Algemene gebruikersinterface-elementen in de EAC in EOP

In deze sectie worden de elementen van de gebruikersinterface beschreven die in de EAC worden gevonden.

![EOP-AdminCenter](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a>Functiedeelvenster

Dit is het eerste navigatieniveau voor de meeste taken die u in de EAC uitvoert. Het functievenster is geordend op functiegebieden.

- **Ontvangers**: Hier u groepen en externe contactpersonen bekijken.

- **Machtigingen:** hier beheert u beheerdersrollen.

- **Compliance Management**: Hier vindt u het rapport van de beheerdersrolgroep en het rapport van het beheercontrolelogboek.

- **Beveiliging:** hier u anti-malwarebeleid, het standaardbeleid voor verbindingsfilter en DKIM beheren.

  > [!NOTE]
  > U moet het anti-malwarebeleid en het standaardverbindingsfilterbeleid beheren in het Beveiligings& Compliance Center. Zie [Beleid voor antimalware configureren in EOP](configure-anti-malware-policies.md) en [Verbindingsfiltering configureren in EOP](configure-the-connection-filter-policy.md)voor meer informatie.

- **E-mailstroom:** hier beheert u de regels voor e-mailstroom (ook wel transportregels genoemd), geaccepteerde domeinen en connectoren, evenals waar u berichttracering uitvoeren.

- **Hybride:** hier u de [wizard Hybride configuratie](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard)uitvoeren en u de Exchange Online [PowerShell-module](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell)installeren.

### <a name="tabs"></a>Tabbladen

De tabbladen zijn uw tweede niveau van navigatie. Elk van de functiegebieden bevat verschillende tabbladen, die elk een functie vertegenwoordigen.

### <a name="toolbar"></a>Werkbalk

Wanneer u op de meeste tabbladen klikt, ziet u een werkbalk. De werkbalk heeft pictogrammen die een specifieke actie uitvoeren. In de volgende tabel worden de pictogrammen en hun acties beschreven.

||||
|---|---|---|
|**Pictogram**|**Naam**|**Actie**|
|![Pictogram Toevoegen](../../media/ITPro-EAC-AddIcon.gif)|Toevoegen, Nieuw|Gebruik dit pictogram om een nieuw object te maken. Sommige van deze pictogrammen hebben een bijbehorende pijl-omlaag waarop u klikken om extra objecten weer te geven die u maken.|
|![Pictogram Bewerken](../../media/ITPro-EAC-EditIcon.gif)|Bewerken|Gebruik dit pictogram om een object te bewerken.|
|![Pictogram Verwijderen](../../media/ITPro-EAC-DeleteIcon.gif)|Verwijderen|Gebruik dit pictogram om een object te verwijderen. Sommige pictogrammen verwijderen hebben een pijl-omlaag waarop u klikken om extra opties weer te geven.|
|![Pictogram Zoeken](../../media/ITPro-EAC-.gif)|Zoek|Gebruik dit pictogram om een zoekvak te openen waarin u de zoekwoord typen voor een object dat u wilt vinden.|
|![Pictogram Vernieuwen](../../media/ITPro-EAC-RefreshIcon.gif)|Vernieuwen|Gebruik dit pictogram om de lijstweergave te vernieuwen.|
|![Pictogram Meer opties](../../media/ITPro-EAC-MoreOptionsIcon.gif)|Meer opties|Gebruik dit pictogram om meer acties weer te geven die u voor de objecten van dat tabblad uitvoeren. In Ontvangers ** \> geeft gebruikers die** op dit pictogram klikken bijvoorbeeld de optie aan om een geavanceerd **zoekopdracht**uit te voeren .|
|![Pictogram Pijl-omhoog](../../media/ITPro-EAC-UpArrowIcon.gif)![Pictogram Pijl-omlaag](../../media/ITPro-EAC-DownArrowIcon.gif)|Pijl-omhoog en pijl-omlaag|Gebruik deze pictogrammen om de prioriteit van een object omhoog of omlaag te verplaatsen.|
|![Pictogram Verwijderen](../../media/ITPro-EAC-RemoveIcon.gif)|Verwijderen|Gebruik dit pictogram om objecten uit een lijst te verwijderen.|
|

### <a name="list-view"></a>Lijstweergave

Wanneer u een tabblad selecteert, ziet u in de meeste gevallen een lijstweergave. De weergavebare limiet met de EAC-lijstweergave is ongeveer 10.000 objecten. Daarnaast is paging opgenomen, zodat u pagina naar de resultaten.

### <a name="details-pane"></a>Deelvenster Details

Wanneer u een object selecteert in de lijstweergave, wordt informatie over dat object weergegeven in het detailvenster. In sommige gevallen bevat het detailvenster beheertaken.

### <a name="me-tile-and-help"></a>Tegel en Help voor mij

Met **Me** de me-tegel u de EAC afmelden en u aanmelden als een andere gebruiker. In **Help**de ![ vervolgkeuzelijst Help-pictogram ](../../media/ITPro-EAC-HelpIcon.gif) kunt u de volgende acties uitvoeren:

- **Help:** Klik op ![ Help-pictogram ](../../media/ITPro-EAC-HelpIcon.gif) om de online help-inhoud te bekijken.

- **Feedback**: Feedback geven.

- **Community**: Plaats een vraag voor het vinden van antwoorden in de community forums.

- **Help-belbellen uitschakelen:** in de Help-bel wordt contextuele hulp weergegeven voor velden wanneer u een object maakt of bewerkt. U de Help-bel uitschakelen of inschakelen als deze is uitgeschakeld.

- **Command Logging weergeven:** er wordt een nieuw venster geopend waarin de gelijkwaardige PowerShell-opdrachten worden weergegeven op basis van wat u in EAC hebt geconfigureerd.

## <a name="supported-browsers"></a>Ondersteunde browsers

Voor de beste ervaring met de EAC raden we u aan altijd de nieuwste browsers, Office-clients en apps te gebruiken. We raden u ook aan software-updates te installeren wanneer deze beschikbaar zijn. Zie [Systeemvereisten voor Office voor](https://products.office.com/office-system-requirements)meer informatie over de ondersteunde browsers en systeemvereisten voor de service.

## <a name="supported-languages"></a>Ondersteunde talen

De volgende talen worden ondersteund en beschikbaar voor de EAC in standalone EOP.

- Amharic

- Arabisch

- Baskisch (Baskisch)

- Bengaals (India)

- Bulgaars

- Catalaans

- Chinees (vereenvoudigd)

- Chinees (Traditioneel)

- Kroatisch

- Tsjechisch

- Deens

- Nederlands

- Nederlands

- Engels

- Estisch

- Filipijnse (Filippijnen)

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
