---
title: Overzicht van inactieve postvakken
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 1fbd74e8-7a60-4157-afe8-fe79f05d2038
ms.custom:
- seo-marvel-apr2020
description: Informatie over het behouden van postvakinhoud voor voormalige werknemers door van het postvak een inactief postvak te maken.
ms.openlocfilehash: 6aeb10f1557a991523b60b8e8e85a99fc61f4b87
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161894"
---
# <a name="overview-of-inactive-mailboxes"></a>Overzicht van inactieve postvakken

Uw organisatie moet mogelijk de e-mail van voormalige werknemers behouden nadat ze de organisatie hebben verlaten. Afhankelijk van de bewaarvereisten van uw organisatie, moet u postvakinhoud mogelijk enkele maanden of jaren behouden na het einde van de dienst, of moet u postvakinhoud mogelijk voor onbepaalde tijd behouden. Ongeacht hoe lang u e-mail moet behouden, kunt u inactieve postvakken maken om het postvak van voormalige werknemers te behouden.

## <a name="what-are-inactive-mailboxes"></a>Wat zijn inactieve postvakken?

Wanneer een werknemer uw organisatie verlaat (of langer verlof heeft), kunt u zijn of haar account Microsoft 365 verwijderen. De postvakgegevens van de werknemer worden bewaard voor 30 dagen nadat het account is verwijderd. Tijdens deze periode kunt u de postvakgegevens nog steeds herstellen door het account te verwijderen. Na 30 dagen worden de gegevens definitief verwijderd.

Maar als uw organisatie postvakinhoud voor voormalige werknemers moet behouden, kunt u van het postvak een inactief postvak maken door het postvak in De bewaring van geschillen te plaatsen of een Microsoft 365-bewaarbeleid toe te passen op het postvak in het beveiligings- & compliancecentrum en vervolgens het bijbehorende Microsoft 365-account te verwijderen. De inhoud van een inactief postvak blijft behouden gedurende de duur van de bewaring van rechtszaken die in het postvak is geplaatst of de bewaarperiode van het bewaarbeleid dat op het postvak is toegepast voordat het postvak werd verwijderd. U kunt het bijbehorende gebruikersaccount nog steeds herstellen voor een periode van 30 dagen. Na 30 dagen blijft het inactieve postvak echter behouden in Microsoft 365 totdat het bewaar- of bewaringsbeleid wordt verwijderd.

> [!IMPORTANT]
> Terwijl we op verschillende manieren blijven investeren om postvakinhoud te behouden, kondigen we de uittreding aan van In-Place Holds in het Exchange beheercentrum. Dit betekent dat u een inactief postvak moet maken met Microsoft 365 bewaarbeleid. Vanaf 1 juli 2020 kunt u geen nieuwe In-Place in Exchange Online. Maar u kunt de duur van de wachttijd van een In-Place in een inactief postvak wijzigen. Vanaf 1 oktober 2020 kunt u de duur van de wachttijd echter niet wijzigen. U kunt alleen een inactief postvak verwijderen door de In-Place verwijderen. Bestaande inactieve postvakken die in de wacht In-Place blijven behouden totdat de wacht wordt verwijderd. Zie Retirement of legacy eDiscovery tools (Oude eDiscovery-hulpprogramma's) voor meer informatie over wanneer de In-Place worden [ingetrokken.](legacy-ediscovery-retirement.md)

## <a name="inactive-mailboxes-and-microsoft-365-retention-policies"></a>Inactieve postvakken en Microsoft 365 bewaarbeleid

Naast De bewaring van rechtszaken is het gebruik van de nieuwe functie Microsoft 365 bewaarbeleid in het Microsoft 365 compliancecentrum een andere manier om een postvak inactief te maken. Een bewaarbeleid gebruiken om een inactief postvak te maken:

- Deze moet zijn geconfigureerd om inhoud te behouden of inhoud te behouden en vervolgens te verwijderen. Als een bewaarbeleid is geconfigureerd om alleen inhoud te verwijderen, wordt een postvak waarop het beleid is toegepast, niet inactief wanneer het gebruikersaccount wordt verwijderd.

- Het moet worden toegepast op Exchange postvakken of Skype voor Bedrijven locaties (omdat Skype-gerelateerde inhoud wordt opgeslagen in het postvak van de gebruiker).

- De query kan op query's zijn gebaseerd, zodat alleen items worden bewaard die overeenkomen met een zoekquery.

Zie Bewaarbeleid en bewaarlabels voor meer informatie over [bewaarbeleid.](retention.md)

Als u een bewaarbeleid gebruikt om een inactief postvak te maken, Microsoft 365 het bewaarbeleid voor het inactieve postvak verder verwerkt. Dit betekent dat als het bewaarbeleid is geconfigureerd om inhoud te behouden en vervolgens te verwijderen, items worden verplaatst naar de map Herstelbare items wanneer de bewaarduur verloopt en vervolgens uiteindelijk uit het inactieve postvak wordt verwijderd. Als bewaarbeleid niet is geconfigureerd voor verwijderde items, worden items die niet permanent zijn verwijderd door de gebruiker (voordat het postvak inactief is gemaakt) niet verplaatst naar de map Herstelbare items en worden ze voor onbepaalde tijd bewaard nadat het postvak inactief is geworden.

U kunt overwegen om een bewaarbeleid Microsoft 365 speciaal voor inactieve postvakken. Hier zijn enkele redenen om dit te doen en om rekening mee te houden.

- U kunt het bewaarbeleid zo configureren dat postvakinhoud alleen wordt behouden zolang dat nodig is om te voldoen aan de vereisten van uw organisatie voor voormalige werknemers.

- Het is een goede manier om inactieve postvakken te identificeren, omdat het bewaarbeleid alleen wordt toegepast op inactieve postvakken.

- U kunt snel het bewaarbeleid identificeren dat is toegewezen aan inactieve postvakken in uw organisatie. Zo kunt u de instellingen voor het bewaren (of verwijderen) zo nodig wijzigen. Het wordt ook gemakkelijker om een inactief postvak permanent te verwijderen, omdat u het kunt verwijderen uit het beleid met behulp van het Beveiligings- & Compliancecentrum. Anders moet u Exchange Online PowerShell gebruiken om een procesbewaring te verwijderen uit een niet-actief postvak & Beveiligings- & Compliancecentrum PowerShell om een inactief postvak uit te sluiten van een Microsoft 365 bewaarbeleid voor de hele organisatie.

- Als u een bewaarbeleid Microsoft 365 speciaal voor inactieve postvakken, kunt u maximaal 1000 postvakken toevoegen aan het beleid. Als u een grote organisatie bent, moet u mogelijk meer dan één bewaarbeleid Microsoft 365 voor inactieve postvakken.

> [!CAUTION]
> Als u een bewaarbeleid gebruikt om een postvak inactief te maken, wijzigt of verwijdert u de upn (User Principal Name) voor het postvak niet voordat u het bijbehorende gebruikersaccount verwijdert. Wijzig bovendien het primaire SMTP-adres (dat is afgeleid van de UPN) of verwijder dit e-mailadres niet uit de lijst met secundaire SMTP-adressen die aan het postvak zijn gekoppeld voordat u het postvak inactief maakt. Als u de UPN of e-mailadressen wijzigt (die aan het postvak zijn toegewezen op het moment dat het bewaarbeleid erop is toegepast) en vervolgens het gebruikersaccount verwijdert om het postvak inactief te maken, kunt u het inactieve postvak niet meer verwijderen wanneer u het postvak niet meer hoeft te behouden. Dat komt omdat u het inactieve postvak niet kunt verwijderen uit het bewaarbeleid met behulp van een UPN- of e-mailadres (om het inactieve postvak te identificeren) dat anders is dan het postvak dat bestond toen het bewaarbeleid in eerste instantie op het postvak werd toegepast. Zie Een inactief postvak verwijderen in Office 365 voor meer informatie over het verwijderen van inactieve [postvakken.](delete-an-inactive-mailbox.md)

## <a name="inactive-mailboxes-and-ediscovery-case-holds"></a>Inactieve postvakken en eDiscovery-case holds

Als een wacht die is gekoppeld aan een eDiscovery-zaak in het beveiligings- & compliancecentrum in een postvak wordt geplaatst en het postvak of het account van de gebruiker wordt verwijderd, wordt het postvak een inactief postvak. Het is echter niet raadzaam eDiscovery-hoesjes te gebruiken om een postvak inactief te maken. Dat komt omdat eDiscovery-zaken zijn bedoeld voor specifieke, tijdgebonden zaken die betrekking hebben op een juridisch probleem. Op een gegeven moment eindigt een juridische zaak waarschijnlijk en worden de aan de zaak gekoppelde aan de zaak ingetrokken en wordt de eDiscovery-zaak gesloten. Als een wacht in een inactief postvak is gekoppeld aan een eDiscovery-zaak en de wacht wordt vrijgegeven of de eDiscovery-zaak wordt gesloten (of verwijderd), wordt het inactieve postvak definitief verwijderd. U kunt ook geen tijdgebaseerde eDiscovery-wachttijd maken. Dat betekent dat inhoud in een inactief postvak voor altijd behouden blijft of totdat de wacht wordt verwijderd en het inactieve postvak wordt verwijderd. Daarom wordt u aangeraden een procesophoud of bewaarbeleid te gebruiken voor inactieve postvakken.

Zie [eDiscovery-zaken](./get-started-core-ediscovery.md)voor meer informatie over eDiscovery-zaken en -bezit.

## <a name="inactive-mailboxes-and-labels"></a>Inactieve postvakken en etiketten

Met bewaarlabels kunt u e-mailgegevens in uw organisatie classificeren voor beheer en bewaarregels afdwingen op basis van die classificatie. Een bewaarlabel kan handmatig door gebruikers of automatisch door beheerders op een e-mailitem worden toegepast en aan een e-mailitem kan slechts één label zijn toegewezen. Als aan één e-mailitem in het postvak van een gebruiker een label is toegewezen (en het is geconfigureerd om het item te behouden of te behouden en vervolgens te verwijderen) en het postvak of het account van de gebruiker wordt verwijderd, wordt het postvak een inactief postvak. Net als bij eDiscovery wordt u niet aangeraden bewaarlabels te gebruiken om een postvak inactief te maken. In plaats daarvan wordt u aangeraden een bewaringsbeleid of een bewaarbeleid te gebruiken. In het geval van bewaarlabels realiseert u zich mogelijk niet dat er een bewaarlabel is toegepast op een e-mailitem en maakt u vervolgens per ongeluk een inactief postvak wanneer u het account van de gebruiker verwijdert.

Zie Meer informatie over bewaarbeleid en bewaarlabels [in](retention.md)Office 365.

## <a name="inactive-mailboxes-and-auto-expanding-archives"></a>Inactieve postvakken en automatisch uitbreidende archieven

Een inactief postvak dat is geconfigureerd met een automatisch uitbreidend archief, kan niet worden hersteld of hersteld. In situaties waarin het nodig is om gegevens te herstellen uit een inactief postvak met een automatisch uitvijfbaar archief, wordt u aangeraden het zoekprogramma voor inhoud te gebruiken om de gegevens uit het postvak te exporteren en vervolgens te importeren in een ander postvak. Zie voor stapsgewijs instructies om in een inactief postvak te zoeken en de zoekresultaten te exporteren:

- [Inhoud zoeken](content-search.md)

- [Zoekresultaten voor inhoud exporteren](export-search-results.md)

## <a name="inactive-mailboxes-and-exchange-mrm-retention-policies"></a>Inactieve postvakken en Exchange MRM-bewaarbeleid

Als een Exchange-bewaarbeleid (het beheer van berichtenrecords of mrm, functie in Exchange Online) is toegepast op het postvak toen het inactief werd gemaakt, worden alle verwijderingsbeleidsregels (die bewaarlabels zijn geconfigureerd met een bewaaractie Verwijderen) nog steeds verwerkt in het inactieve postvak.  Dit betekent dat items die zijn gemarkeerd met een verwijderingsbeleid, worden verplaatst naar de map Herstelbare items wanneer de bewaarperiode verloopt. Deze items worden verwijderd uit het inactieve postvak wanneer de duur van de wachttijd verloopt. Als een duur van de wachttijd niet is opgegeven voor het inactieve postvak, blijven items in de map Items herstellen voor onbepaalde tijd behouden.

Archiefbeleid (bewaarlabels die zijn geconfigureerd met een actie Voorarchiveren van **MoveToArchive)** die zijn opgenomen in het bewaarbeleid dat is toegewezen aan een inactief postvak, wordt daarentegen genegeerd. Dit betekent dat items in een inactief postvak die zijn gelabeld met een archiefbeleid, in het primaire postvak blijven wanneer de bewaarperiode verloopt. Ze worden niet verplaatst naar het archiefpostvak of naar de map Herstelbare items in het archiefpostvak. Deze blijven voor onbepaalde tijd behouden.

## <a name="creating-an-inactive-mailbox"></a>Een inactief postvak maken

Als u een postvak inactief wilt maken, moet er een Exchange Online Abonnement 2-licentie (of een Exchange Online Plan 1-licentie met een Exchange Online Archiving-invoeglicentie) aan het postvak worden toegewezen, zodat een beleid voor bewaring van rechtszaken of Microsoft 365 kan worden toegepast op het postvak voordat het wordt verwijderd. Nadat het gebruikersaccount is verwijderd, is Exchange Online licentie die is gekoppeld aan het gebruikersaccount beschikbaar om toe te wijzen aan een nieuwe gebruiker.

In de volgende tabel wordt een overzicht van het proces van het maken van een inactief postvak voor verschillende bewaarscenario's. Zie Inactieve postvakken beheren voor [meer informatie.](create-and-manage-inactive-mailboxes.md)

****

|Aan...|Doe dit...|Resultaat|
|---|---|---|
|Inhoud van postvak voor onbepaalde tijd behouden nadat een werknemer de organisatie heeft verlaat|Plaats het postvak in De bewaring van rechtszaken of pas een Microsoft 365 bewaarbeleid (dat is geconfigureerd om inhoud te behouden) toe op het postvak. <br/> Geef geen bewaringsduur op voor de bewaring van rechtszaken of configureer het bewaarbeleid niet om items te verwijderen. U kunt ook een bewaarbeleid gebruiken dat items voor altijd behoudt. <br/> Verwijder het account van Microsoft 365 gebruiker.|Alle inhoud in het inactieve postvak, inclusief items in de map Herstelbare items, blijft voor onbepaalde tijd behouden.|
|Postvakinhoud behouden voor een bepaalde periode nadat een werknemer de organisatie heeft verlaat en deze vervolgens verwijdert|Een bewaarbeleid Microsoft 365 op het postvak toepassen. <br/> Configureer het bewaarbeleid om items te behouden en vervolgens te verwijderen wanneer de bewaarperiode verloopt. <br/> Verwijder het account van Microsoft 365 gebruiker.|Wanneer de bewaarperiode voor een postvakitem verloopt, wordt het item verplaatst naar de map Herstelbare items en wordt het permanent verwijderd (verwijderd) uit het inactieve postvak wanneer de bewaarperiode van het verwijderde item (voor Exchange-postvakken) verloopt. De bewaarperiode van Microsoft 365 bewaarbeleid kan worden geconfigureerd op basis van de oorspronkelijke datum waarop een postvakitem is ontvangen of gemaakt of wanneer het voor het laatst is gewijzigd.|
|

**OPMERKING:** Als een procesbewaring al is geplaatst in een postvak of als een bewaarbeleid voor Microsoft 365 (dat is geconfigureerd voor het behouden of behouden en vervolgens verwijderen van inhoud) al is toegepast op het postvak, hoeft u alleen het bijbehorende gebruikersaccount te verwijderen om een inactief postvak te maken.

## <a name="managing-inactive-mailboxes"></a>Inactieve postvakken beheren

Nadat u een postvak inactief hebt, kunt u verschillende beheertaken uitvoeren op inactieve postvakken.

- **Wijzig de duur van de wacht voor een inactief postvak.** Nadat een postvak inactief is gemaakt, kunt u de duur van de bewaring van het bewaringsbeleid voor rechtszaken wijzigen of Microsoft 365 bewaarbeleid toepassen op het inactieve postvak. Zie De duur van de wacht voor een inactief postvak wijzigen voor [stapsgewijse procedures.](change-the-hold-duration-for-an-inactive-mailbox.md)

  > [!NOTE]
  > U kunt geen ander bewaarbeleid toepassen op een inactief postvak. U kunt alleen de bewaarduur wijzigen van een bestaand bewaarbeleid dat is toegepast op het inactieve postvak.

- **Een inactief postvak herstellen.** Als een voormalige werknemer (of een werknemer met verlof) terugkeert naar uw organisatie of als een nieuwe werknemer wordt aangenomen om de taaktaken van de voormalige werknemer op zich te nemen, kunt u de inhoud van het inactieve postvak herstellen. Wanneer u een inactief postvak herstelt, wordt het postvak geconverteerd naar een nieuw postvak, blijven de inhoud en de mapstructuur van het inactieve postvak behouden en is het postvak gekoppeld aan een nieuw gebruikersaccount. Nadat het is hersteld, bestaat het inactieve postvak niet meer. Zie Een inactief postvak herstellen voor stapsgewijs procedures en informatie over wat er gebeurt wanneer u een inactief postvak [herstelt.](recover-an-inactive-mailbox.md)

  > [!NOTE]
  > Als u een inactief postvak herstelt dat is toegewezen aan een bewaarbeleid met Bewaringsvergrendeling (een vergrendeld bewaarbeleid *genoemd),* wordt het herstelde postvak toegewezen aan hetzelfde vergrendelde bewaarbeleid. Als u een inactief postvak herstelt dat is toegewezen aan een bewaarbeleid zonder Bewaringsvergrendeling, wordt het herstelde postvak verwijderd uit het ontgrendelde bewaarbeleid. De bewaring van rechtszaken is echter ingeschakeld in het herstelde postvak om te voorkomen dat postvakinhoud wordt verwijderd op basis van een organisatiebreed bewaarbeleid dat inhoud verwijdert die ouder is dan een bepaalde leeftijd.

- **Een inactief postvak herstellen.** Als een andere werknemer de taakverantwoordelijkheden van een voormalige werknemer op zich neemt of als een andere persoon toegang nodig heeft tot de inhoud van het inactieve postvak, kunt u de inhoud van het inactieve postvak herstellen (of samenvoegen) naar een bestaand postvak. Wanneer u een inactief postvak herstelt, wordt de inhoud gekopieerd naar een ander postvak. Het inactieve postvak blijft behouden en blijft een inactief postvak. Het inactieve postvak kan nog steeds worden doorzocht met behulp van eDiscovery-hulpprogramma's, de inhoud ervan kan worden hersteld naar een ander postvak en kan later worden hersteld of verwijderd. Zie Een inactief postvak herstellen voor [stapsgewijse procedures.](restore-an-inactive-mailbox.md)

- **Een inactief postvak verwijderen.** Wanneer u de inhoud van een inactief postvak niet meer hoeft te behouden, kunt u het permanent verwijderen door alle bewaarbeleidsregels voor bewaring of Microsoft 365 te verwijderen die zijn toegepast op het inactieve postvak. Als een postvak meer dan 30 dagen geleden inactief is gemaakt, wordt het gemarkeerd voor permanent verwijderen nadat u de wacht hebt verwijderd. Als het postvak inactief is gemaakt in de afgelopen 30 dagen, kunt u het opnieuw activeren nadat u het bewaarbeleid hebt verwijderd. Zie Een inactief postvak verwijderen voor [stapsgewijse procedures.](delete-an-inactive-mailbox.md)