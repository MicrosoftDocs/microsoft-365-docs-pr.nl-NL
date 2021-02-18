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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: Meer informatie over de webbeheerinterface in de zelfstandige Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ec9dcbccbee734ea7c475b1ac0a5f9a92a0b401b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286955"
---
# <a name="exchange-admin-center-in-standalone-eop"></a>Exchange-beheercentrum in standalone EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
-  [Zelfstandige versie van Exchange Online Protection](exchange-online-protection-overview.md)

Het Exchange-beheercentrum (EAC) is een webbeheerconsole voor zelfstandige Exchange Online Protection (EOP).

Zoekt u de Exchange Online-versie van dit onderwerp? Zie [het Exchange-beheercentrum in Exchange Online.](https://docs.microsoft.com/exchange/exchange-admin-center)

## <a name="open-the-eac-in-eop"></a>Het EAC openen in EOP

Zelfstandige EOP-klanten hebben toegang tot het EAC via de volgende methoden:

- **Vanuit het Microsoft 365-beheercentrum:**

  1. Ga naar <https://admin.microsoft.com> en klik op Alles **tonen.**

     ![Klik op Alles tonen in het Microsoft 365-beheercentrum](../../media/m365-center-show-all.png)

  2. Klik in **de sectie Beheercentra** die wordt weergegeven op **Alle beheercentra.**

     ![Klik op Alle beheercentra in het Microsoft 365-beheercentrum](../../media/m365-center-select-all-admin-centers.png)

  3. Klik op **de pagina Alle beheercentra** die wordt weergegeven op **Exchange Online Protection.**

- Ga rechtstreeks naar `https://admin.protection.outlook.com/ecp/` .

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a>Algemene elementen van de gebruikersinterface in het EAC in EOP

In deze sectie worden de elementen van de gebruikersinterface beschreven die in het EAC worden gevonden.

![Het Exchange-beheercentrum in Exchange Online Protection](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a>Functievenster

Dit is het eerste navigatieniveau voor de meeste taken die u uitvoert in het EAC. Het functievenster is ingedeeld op functiegebieden.

- **Geadresseerden:** hier ziet u groepen en externe contactpersonen.

- **Machtigingen:** dit waar u beheerdersrollen beheert.

- **Compliancebeheer:** hier vindt u het rapport met beheerdersrollen en het auditlogboek voor beheerders.

- **Beveiliging:** hier kunt u antimalwarebeleidsregels, het standaardbeleid voor verbindingsfilters en DKIM beheren.

  > [!NOTE]
  > U dient antimalwarebeleid en het standaardbeleid voor verbindingsfilters te beheren in het & compliancecentrum. Zie [Antimalwarebeleid](configure-anti-malware-policies.md) configureren in EOP en [Verbindingsfilters configureren in EOP voor meer informatie.](configure-the-connection-filter-policy.md)

- **E-mailstroom:** hier beheert u regels voor de e-mailstroom (ook wel transportregels genoemd), geaccepteerde domeinen en connectors, en waar u bericht traceren kunt uitvoeren.

- **Hybride:** hier kunt u de wizard Hybride configuratie uitvoeren [en](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard)de Exchange [Online PowerShell-module installeren.](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell)

### <a name="tabs"></a>Tabbladen

De tabbladen zijn uw tweede navigatieniveau. Elk van de functiegebieden bevat verschillende tabbladen, die elk een functie vertegenwoordigen.

### <a name="toolbar"></a>Werkbalk

Wanneer u op de meeste tabbladen klikt, ziet u een werkbalk. De werkbalk heeft pictogrammen die een bepaalde actie uitvoeren. In de volgende tabel worden de pictogrammen en hun acties beschreven.

****

|Pictogram|Naam|Actie|
|---|---|---|
|![Pictogram Toevoegen](../../media/ITPro-EAC-AddIcon.gif)|Toevoegen, Nieuw|Gebruik dit pictogram om een nieuw object te maken. Sommige van deze pictogrammen hebben een bijbehorende pijl-omlaag waar u op kunt klikken om andere objecten weer te geven die u kunt maken.|
|![Pictogram Bewerken](../../media/ITPro-EAC-EditIcon.gif)|Bewerken|Gebruik dit pictogram om een object te bewerken.|
|![Pictogram Verwijderen](../../media/ITPro-EAC-DeleteIcon.gif)|Verwijderen|Gebruik dit pictogram om een object te verwijderen. Sommige pictogrammen voor verwijderen hebben een pijl-omlaag waar u op kunt klikken om extra opties weer te geven.|
|![Pictogram Zoeken](../../media/ITPro-EAC-.gif)|Zoeken|Gebruik dit pictogram om een zoekvak te openen waarin u de zoekterm kunt typen voor een object dat u zoekt.|
|![Pictogram Vernieuwen](../../media/ITPro-EAC-RefreshIcon.gif)|Vernieuwen|Gebruik dit pictogram om de lijstweergave te vernieuwen.|
|![Pictogram Meer opties](../../media/ITPro-EAC-MoreOptionsIcon.gif)|Meer opties|Gebruik dit pictogram om meer acties weer te geven die u voor de objecten van dat tabblad kunt uitvoeren. Als gebruikers van **geadresseerden \> bijvoorbeeld** op dit pictogram klikken, wordt de optie weergegeven voor het uitvoeren van **een geavanceerde zoekopdracht.**|
|![Pictogram met pijl-omhoog](../../media/ITPro-EAC-UpArrowIcon.gif)![Pictogram met pijl-omlaag](../../media/ITPro-EAC-DownArrowIcon.gif)|Pijl-omhoog en pijl-omlaag|Gebruik deze pictogrammen om de prioriteit van een object omhoog of omlaag te verplaatsen.|
|![Pictogram Verwijderen](../../media/ITPro-EAC-RemoveIcon.gif)|Verwijderen|Gebruik dit pictogram om objecten uit een lijst te verwijderen.|
|

### <a name="list-view"></a>Lijstweergave

Wanneer u een tabblad selecteert, ziet u in de meeste gevallen een lijstweergave. De limiet die kan worden weergegeven voor de weergave van de EAC-lijst is ongeveer 10.000 objecten. Paginering is ook opgenomen zodat u kunt pagina's maken naar resultaten.

### <a name="details-pane"></a>Detailvenster

Wanneer u een object selecteert in de lijstweergave, wordt informatie over dat object weergegeven in het detailvenster. In sommige gevallen bevat het detailvenster beheertaken.

### <a name="me-tile-and-help"></a>Tegel Ik en Help

Met **de** tegel Ik kunt u zich afloggen bij het EAC en u aanmelden als een andere gebruiker. In de ![ vervolgkeuzelijst ](../../media/ITPro-EAC-HelpIcon.gif) Help-pictogram kunt u de volgende acties uitvoeren:

- **Help:** klik op ![ het ](../../media/ITPro-EAC-HelpIcon.gif) Help-pictogram om de online Help-inhoud weer te geven.
- **Feedback:** feedback geven.
- **Community:** post een vraag voor antwoorden in de communityforums.
- **Help-bellen uitschakelen:** de Help-bel geeft contextuele Help weer voor velden wanneer u een object maakt of bewerkt. U kunt de Help-bel uitschakelen of in- of uitschakelen als deze is uitgeschakeld.
- **Opdrachtregistratie weergeven:** er wordt een nieuw venster geopend waarin de overeenkomstige PowerShell-opdrachten worden weergegeven op basis van wat u hebt geconfigureerd in het EAC.

## <a name="supported-browsers"></a>Ondersteunde browsers

Voor een optimaal gebruik van het EAC raden we u aan altijd de meest recente browsers, Office-clients en apps te gebruiken. We raden u ook aan software-updates te installeren zodra deze beschikbaar zijn. Zie de systeemvereisten voor Office voor meer informatie over de ondersteunde browsers en systeemvereisten [voor de service.](https://products.office.com/office-system-requirements)

## <a name="supported-languages"></a>Ondersteunde talen

De volgende talen worden ondersteund en beschikbaar voor het EAC in de zelfstandige EOP.

- Amhaars
- Arabisch
- Baskisch (Baskenland)
- Bengali (India)
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
- Iya
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
