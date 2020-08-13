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
description: Meer informatie over de web management interface in standalone Exchange Online Protection (EOP).
ms.openlocfilehash: d5753f687461a5495c2431db687263d7211bcbf5
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/12/2020
ms.locfileid: "46652907"
---
# <a name="exchange-admin-center-in-standalone-eop"></a>Exchange-beheercentrum in standalone EOP

Het Exchange-Beheercentrum is een webgebaseerd beheerconsole voor standalone Exchange Online Protection (EOP).

Zoekt u de Exchange Online-versie van dit onderwerp? Zie [Exchange-Beheercentrum in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

## <a name="open-the-eac-in-eop"></a>Het Exchange-Beheercentrum openen in EOP

Zelfstandige EOP-klanten hebben toegang tot het SBV-programma met behulp van de volgende methoden:

- **Vanuit het Microsoft 365-Beheercentrum**:

  1. Ga naar <https://admin.microsoft.com> en klik op **AllesWeergeven**.

     ![Klik op AllesWeergeven in het Microsoft 365-Beheercentrum](../../media/m365-center-show-all.png)

  2. Klik in de sectie **beheer centra** die wordt weergegeven op **alle beheer centra**.

     ![Klik op alle beheer centra in het Microsoft 365-Beheercentrum.](../../media/m365-center-select-all-admin-centers.png)

  3. Op de pagina **all admin Centers** die worden weergegeven, klikt u op **Exchange Online Protection**.

- Ga rechtstreeks naar `https://admin.protection.outlook.com/ecp/` .

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a>Veelvoorkomende elementen van de gebruikersinterface in het Exchange-Beheercentrum in EOP

In deze sectie worden de onderdelen van de gebruikersinterface beschreven die zijn gevonden in het Exchange-Beheercentrum.

![EOP-Te102827792beheercentrum](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a>Deelvenster functie

Dit is het eerste niveau van navigatie voor de meeste taken die u in het Exchange-Beheercentrum uitvoert. Het deelvenster functie is ingedeeld op functiegebieden.

- **Geadresseerden**: in dit voorbeeld ziet u groepen en externe contactpersonen.

- **Machtigingen**: Hiermee beheert u beheerdersrollen.

- **Nalevings beheer**: Hier vindt u het rapport met rollen van beheerders en het controleverslag van de beheerder.

- **Beveiliging**: hier kunt u beleidsregels voor anti malware, het standaardbeleid voor verbindings filters en dkim.

  > [!NOTE]
  > U dient beleidsregels voor anti-malware en het standaardbeleid voor verbindings filters te beheren in het compliance-& Beveiligingscentrum. Zie voor meer informatie [anti-malwarebeleid in EOP configureren](configure-anti-malware-policies.md) en het [filteren van verbindingen in EOP configureren](configure-the-connection-filter-policy.md).

- **E-mail stroom**: dit is waar u de e-mail stroom regels (ook wel de zogenaamde transportregels genoemd), geaccepteerde domeinen en connectors beheert, en waar u de bericht tracering kunt uitvoeren.

- **Hybride**: dit is de plek waar u de [wizard hybride configuratie](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard)kunt uitvoeren en waar u de [PowerShell-module van Exchange Online](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell)kunt installeren.

### <a name="tabs"></a>Tabvolgorde

De tabbladen vormen een tweede navigatieniveau. Elk functiegebied bevat diverse tabbladen, elk met een functie.

### <a name="toolbar"></a>Werkbalk

Wanneer u op de meeste tabbladen klikt, wordt een werkbalk weergegeven. De werkbalk bevat pictogrammen die een specifieke actie uitvoeren. In de volgende tabel worden de pictogrammen en de bijbehorende acties beschreven.

****

|Pictogram|Naam|Actierij|
|---|---|---|
|![Pictogram toevoegen](../../media/ITPro-EAC-AddIcon.gif)|Toevoegen, nieuw|Gebruik dit pictogram om een nieuw object te maken. Sommige van deze pictogrammen bevatten een pijl-omlaag waarop u kunt klikken om extra objecten weer te geven die u kunt maken.|
|![Pictogram bewerken](../../media/ITPro-EAC-EditIcon.gif)|Bewerken|Gebruik dit pictogram als u een object wilt bewerken.|
|![Pictogram Verwijderen](../../media/ITPro-EAC-DeleteIcon.gif)|Wissen|Gebruik dit pictogram om een object te verwijderen. Sommige delete-pictogrammen bevatten een pijl-omlaag waarop u kunt klikken om extra opties weer te geven.|
|![Pictogram Zoeken](../../media/ITPro-EAC-.gif)|Vinden|Gebruik dit pictogram om een zoekvak te openen waarin u de zoekterm kunt typen voor een object dat u wilt zoeken.|
|![Pictogram Vernieuwen](../../media/ITPro-EAC-RefreshIcon.gif)|Vernieuwen|Gebruik dit pictogram om de lijstweergave te vernieuwen.|
|![Pictogram meer opties](../../media/ITPro-EAC-MoreOptionsIcon.gif)|Meer opties|Gebruik dit pictogram om meer acties weer te geven die u voor dit tabblad objecten kunt uitvoeren. Bij ** \> gebruikers** die op dit pictogram klikken, ziet u bijvoorbeeld de optie voor het uitvoeren van een **Geavanceerd zoeken**.|
|![Pictogram pijl-omhoog](../../media/ITPro-EAC-UpArrowIcon.gif)![Pictogram pijl-omlaag](../../media/ITPro-EAC-DownArrowIcon.gif)|Pijl-omhoog en pijl-omlaag|Gebruik deze pictogrammen als u de prioriteit van een object omhoog of omlaag wilt verplaatsen.|
|![Pictogram Verwijderen](../../media/ITPro-EAC-RemoveIcon.gif)|Schakel|Gebruik dit pictogram om objecten uit een lijst te verwijderen.|
|

### <a name="list-view"></a>Lijstweergave

Wanneer u een tabblad selecteert, ziet u in de meeste gevallen een lijstweergave. De zichtbare limiet met de lijstweergave van het SBV is ongeveer 10.000 objecten. Daarnaast is paginering ook opgenomen, zodat u de resultaten van de pagina kunt laten opvallen.

### <a name="details-pane"></a>Deelvenster Details

Wanneer u in de lijstweergave een object selecteert, wordt informatie over dat object weergegeven in het detailvenster. In sommige gevallen bevat het detailvenster beheertaken.

### <a name="me-tile-and-help"></a>Ik-tegel en Help

Met de tegel **Ik** kunt u zich afmelden bij het SBV-bericht en u aanmelden als een andere gebruiker. In het **Help** ![ ](../../media/ITPro-EAC-HelpIcon.gif) vervolgkeuzemenu Help-Help-pictogram kunt u de volgende acties uitvoeren:

- **Help**: Klik op ![ Help-pictogram ](../../media/ITPro-EAC-HelpIcon.gif) om de inhoud van de online-Help weer te geven.

- **Feedback**: Geef feedback.

- **Community**: Stel een vraag voor het zoeken van antwoorden op de forums van de community.

- **Help bellen uitschakelen**: de Help-Bel wordt contextuele Help voor velden weergegeven wanneer u een object maakt of bewerkt. U kunt de Help bellen uitschakelen of inschakelen als deze functie is uitgeschakeld.

- **Logboekregistratie weergeven**: er wordt een nieuw venster geopend waarin de overeenkomstige PowerShell-opdrachten worden weergegeven op basis van wat u hebt geconfigureerd in het SBV

## <a name="supported-browsers"></a>Ondersteunde browsers

Voor de beste ervaring met het beheer van het beheer wordt u aangeraden altijd de meest recente browsers, Office-clients en apps te gebruiken. We raden u ook aan software-updates te installeren wanneer deze beschikbaar komen. Zie [systeemvereisten voor Office](https://products.office.com/office-system-requirements)voor meer informatie over de ondersteunde browsers en systeemvereisten voor de service.

## <a name="supported-languages"></a>Ondersteunde talen

De volgende talen worden ondersteund en zijn beschikbaar voor de EOP in standalone.

- Amhaars
- Arabisch
- Baskisch (Baskisch)
- Bengalees (India)
- Bulgarian
- Catalan
- Chinees (vereenvoudigd)
- Chinees (traditioneel)
- Croatian
- Czech
- Danish
- Dutch
- English
- Estonian
- Filipijns (Filipijnen)
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
- Swahili
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
- Servisch (Latijns)
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
