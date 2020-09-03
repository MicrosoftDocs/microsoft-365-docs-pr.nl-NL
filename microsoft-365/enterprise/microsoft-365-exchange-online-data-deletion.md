---
title: Microsoft 365 Exchange Online gegevens verwijderen
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Meer informatie over de manier waarop u permanent en permanent gegevens kunt verwijderen voor postvakken en items binnen postvakken worden verwerkt in Exchange Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 63bb5dcde334f7c53554f910b1a8d17e1d0d69cc
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332518"
---
# <a name="exchange-online-data-deletion-in-microsoft-365"></a>Exchange Online data verwijdering in Microsoft 365

In Exchange Online zijn er twee soorten verwijderingen: tijdelijke verwijdering en permanent verwijderen. Dit geldt voor postvakken en items in een postvak.

## <a name="soft-deleted-and-hard-deleted-mailboxes"></a>Tijdelijke verwijderde en verwijderde postvakken
Een tijdelijk verwijderd gebruikerspostvak is een postvak dat is verwijderd met behulp van het Microsoft 365-Beheercentrum of de cmdlet Remove-Mailbox en de Prullenbak van Azure Active Directory nog minder dan 30 dagen. Een postvak kan worden verwijderd op een van de volgende manieren:
- Het gekoppelde Azure Active Directory-gebruikersaccount van het gebruikerspostvak wordt vloeiend verwijderd (het gebruikersobject valt buiten het bereik of in de container voor de Prullenbak).
- Het gekoppelde Azure Active Directory-gebruikersaccount van het gebruikerspostvak is permanent verwijderd, maar het postvak van de Exchange Online-postvak staat onder een voorstel of een eDiscovery-bewaring.
- Het gekoppelde Azure Active Directory-gebruikersaccount van het gebruikerspostvak is in de afgelopen 30 dagen opgeschoond. welke lengte van het maximale behoud van Exchange Online zorgt ervoor dat het postvak voortdurend wordt verwijderd en kan niet meer worden hersteld.

Een permanent verwijderd gebruikerspostvak is een postvak dat op een van de volgende manieren is verwijderd:
- Het postvak van de gebruiker is langer dan 30 dagen tijdelijk verwijderd en de gekoppelde Azure Active Directory-gebruiker is permanent verwijderd. Alle postvak inhoud, zoals e-mailberichten, contactpersonen en bestanden, worden permanent verwijderd.
- Het gebruikersaccount dat is gekoppeld aan het postvak van de gebruiker is permanent verwijderd uit Azure Active Directory. Het postvak van de gebruiker wordt op dit moment direct verwijderd in Exchange Online en blijft gedurende 30 dagen in de modus voor eenmalige verwijdering staan. Als u in de periode van 30 dagen een nieuwe Azure Active Directory-gebruiker synchroniseert met dezelfde **ExchangeGuid** of **ArchiveGuid**en dit nieuwe account een licentie heeft voor Exchange Online, resulteert dit in een definitieve verwijdering van het oorspronkelijke postvak van de gebruiker. Alle postvak inhoud, zoals e-mailberichten, contactpersonen en bestanden, worden permanent verwijderd.
- Een voorlopig verwijderd postvak wordt verwijderd met **Remove-Mailbox-PermanentlyDelete**.

Voor de bovenstaande verwijderings scenario's is ervan uitgegaan dat het postvak van de gebruiker zich niet in de wachtstand bevindt, zoals de persoonlijke voorkeuren of eDiscovery-bewaring. Als het postvak een willekeurig type wachtruimte bevat, kan het postvak niet worden verwijderd. Voor alle typen e-mail geadresseerden worden alle instellingen voor [vasthouden](https://support.office.com/article/manage-legal-investigations-in-office-365-2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e?ui=en-US&rs=en-US&ad=US) genegeerd en hebben ze geen gevolgen voor het verwijderen of verwijderen van de gebruiker.

## <a name="soft-deleted-and-hard-deleted-items"></a>Tijdelijke, verwijderde en permanent verwijderde items
Wanneer een gebruiker een postvak item (zoals een e-mailbericht, een contactpersoon, een agenda-afspraak of een taak) verwijdert, wordt het item verplaatst naar de map herstelbare items en naar een submap met de naam ' verwijderingen '. Dit wordt een tijdelijke verwijdering genoemd. Hoe lang verwijderde items worden bewaard in de map Verwijderde items, is afhankelijk van de bewaarperiode voor verwijderde items die is ingesteld voor het postvak. Een Exchange Online-postvak behoudt standaard verwijderde items voor 14 dagen, maar Exchange Online-beheerders kunnen deze instelling wijzigen om de periode tot maximaal 30 dagen te verhogen. (Zie [wijzigen hoelang permanent verwijderde items worden bewaard voor een Exchange Online-postvak](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/change-deleted-item-retention)voor uitgebreide stappen voor het verhogen van de bewaarperiode voor verwijderde items in een Exchange Online-postvak. Gebruikers kunnen verwijderde items herstellen of wissen voordat de bewaartijd voor een verwijderd item vervalt. Hiervoor gebruiken ze de functie Verwijderde items herstellen in Microsoft Outlook of de webversie van Outlook.

Als een gebruiker een verwijderd item verwijdert met de functie Verwijderde items herstellen in Outlook of de webversie van Outlook, wordt dit een tijdelijke verwijdering genoemd. In Exchange Online is eenmalige herstelfunctie voor eenmalige aanmelding ingeschakeld wanneer een nieuw postvak wordt gemaakt, zodat een beheerder permanent verwijderde items kan [herstellen](https://docs.microsoft.com/Exchange/recipients/user-mailboxes/recover-deleted-messages) voordat de bewaarperiode voor verwijderde items vervalt. Als een bericht wordt gewijzigd door een gebruiker of een proces, worden ook kopieën van het originele item bewaard wanneer het herstel van één item is ingeschakeld.

## <a name="page-zeroing"></a>Pagina nul maken
*Nullen* is een beveiligingsmechanisme waarmee nulwaarden of binaire patronen via verwijderde gegevens worden geschreven, zodat de verwijderde gegevens moeilijker te herstellen zijn. In Exchange Online worden met postvak databases *pagina's* als hun opslagruimte gebruikt en wordt een Overschrijf proces met de naam *pagina nullen*geïmplementeerd. Pagina 0-0 is standaard ingeschakeld en kan niet worden uitgeschakeld door klanten of door Microsoft. De bewerkingen voor het gelijk maken van pagina's worden vastgelegd in de logboekbestanden van de transactie, zodat alle kopieën van een bepaalde database op een vergelijkbare manier op de pagina worden gezet. Als u een pagina op een actieve database kopieert, wordt de pagina op een andere manier in de database gezet.

Met pagina 0 wordt een binair patroon met vaste, verwijderde records opgeslagen. Het patroon patroon voor de opvulling van pagina's is specifiek voor Extensible Storage Engine (ESE)-bewerkingen (de naam van de interne database-engine die wordt gebruikt door servers in Exchange Online) en is niet geschikt voor run-time bewerkingen en onderhoudsbewerkingen voor de achtergrond database. (Background database maintenance is een proces waarmee continu controlesommen worden gecontroleerd en elke database wordt gescand. De primaire functie is de controlesom voor databasepagina's, maar ook voor het opschonen van ruimte en het opruimen van records en pagina's die niet zijn vrijgezet vanwege een Store.

In de volgende tabel vindt u een overzicht van de opvulpatronen die overeenkomen met specifieke runtime bewerkingen.

| ESE run-time Operation   | Opvulpatroon |
|--------------------------|--------------|
| Vervangen                  | S            |
| Record/lange waarde verwijderen | 2D            |
| Vrijgestelde pagina ruimte         | T            |


In de volgende tabel vindt u een overzicht van de opvulpatronen die overeenkomen met specifieke bewerkingen die zich voordoen tijdens het onderhoud van de achtergrond database voor ESE.

| Onderhoudsbewerking van ESE-achtergrond database | Opvulpatroon |
|-----------------------------------------------|--------------|
| Record verwijderen                                 | 2D            |
| Long value Delete                             | L            |
| Vrijgestelde pagina ruimte van gedeeltelijk gebruikte pagina       | STB            |
| Vrijgestelde pagina ruimte van niet-gebruikte pagina               | V            |


### <a name="page-zeroing-process"></a>Pagina met nulwaarden
Het proces voor het verwijderen van pagina's is afhankelijk van het verwijderings scenario. In de volgende tabel vindt u een beschrijving van database Verwijder scenario's en wanneer de functies voor het gelijk maken van pagina's.

| Scenario voor het verwijderen van een database | ESE-proces en periode tot nul database |
|-----------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Item vervalt op basis van de bewaarperiode voor verwijderde items. | Met een asynchrone thread wordt een binair patroon voor de verwijderde gegevens weggeschreven. Deze actie vindt plaats binnen de milliseconden van de verwijdering van de record. Als het archief vastloopt, wordt de waarde van het opslaan beëindigd wanneer het asynchrone nulpunt van de werkwijze wordt geannuleerd (of als de opschoning van de versie van de versie van de versie van de versie van de versie van de versie van de database is geannuleerd vanwege een groei van de versieopslag). |
| Weergave scenario: verloop van items in de weergave voor de webversie van Outlook/Outlook (bijvoorbeeld discussieweergave) | Gegevens die nul worden gemaakt bij het maken van achtergrond database onderhouds processen van de database. |
| Postvak verplaatsen/postvak verwijderen scenario: bronpostvak verwijderd (verlopen van verwijderde postvak) | Gegevens die nul worden gemaakt bij het maken van achtergrond database onderhouds processen van de database. |

### <a name="mailbox-data-types-without-page-zeroing"></a>Gegevenstypen postvak zonder pagina nul
De volgende gegevenstypen in het postvak hebben geen voorwaarden voor het toevoegen van pagina's:
- **Transacties voor de postvakdatabase-transacties** -wanneer transactielogboeken worden verwijderd als onderdeel van de normale bewerkingen, is er geen manier om de blokken in het bestandssysteem te verwijderen waarin de verwijderde logboekbestanden zijn opgeslagen. Het maakt niet uit of het bestandssysteem snel de beschikbare ruimte voor nieuwe logboeken opnieuw gebruikt, maar er is geen garantie dat dit gebeurt.
- **Catalogusbestanden met Inhoudsindexen** -Exchange Online maakt gebruik van Search Foundation (ook wel snel bekend) voor de functies voor het indexeren van zoekopdrachten. De catalogus met zoekindexen bestaat uit diverse tien bestanden die zijn opgeslagen op hetzelfde volume als het databasebestand van de Postvak. Wanneer een bericht permanent wordt verwijderd uit de postvakdatabase, wordt de gekoppelde inhoud in de zoekcatalogus niet onmiddellijk verwijderd. Inhouds verwijdering vindt plaats wanneer met Search Foundation een bestand met schaduw (of hoofdsamenvoeging) wordt uitgevoerd voor een groot groter bestand. Wanneer de hoofdsamenvoeging is voltooid, worden de kleinere catalogusbestanden verwijderd. Er is geen proces om de blokken te 0 die de verwijderde catalogusbestanden hebben opgeslagen.

## <a name="continuous-replication"></a>Continue replicatie
Continue replicatie (ook wel bekend als logboekverzending en opnieuw afspelen) is technologie in Exchange Online waarmee kopieën van elke postvakdatabase worden gemaakt en bijgehouden om hoge beschikbaarheid, site tolerantie en calamiteitenherstel te kunnen zorgen. Voortdurende replicatie maakt de ondersteuning voor crashherstel van de Exchange Server-database om technologie te bieden waarmee asynchrone updates van een of meer kopieën van een postvakdatabase worden uitgevoerd. Elke postvakserver records met database updates die zijn gemaakt in een actieve database (bijvoorbeeld e-mail activiteit van gebruikers) als logboekrecords in een reeks logboekbestanden met 1 MB. Deze set bestanden wordt de logboek stroom genoemd. Bij continue replicatie wordt de logboekmap ook gebruikt om een of meer kopieën van een database asynchroon bij te werken. Dit houdt in dat u de logboeken naar een locatie met een passieve kopie van de actieve database verzendt en ze vervolgens opnieuw uitzendt in de versie van het passieve database. Als alle logboeken van de actieve database opnieuw worden afgespeeld tegen een passieve kopie van de database, zijn de twee databases vergelijkbaar en wordt dit proces door lopende fysieke wijziging van een actieve database naar alle passieve kopieën van die database gerepliceerd.

Elke verwijdering uit een postvakdatabase, of een postvak item of een heel postvak, en of een tijdelijke verwijdering of een vaste verwijdering een fysieke wijziging voor de actieve database vertegenwoordigt. Als u pagina nul maakt, moet u ook fysieke wijzigingen aanbrengen in de actieve database. Deze wijzigingen worden doorgevoerd in de logboekbestanden via een proces met de naam continue replicatie en wanneer deze logboekbestanden opnieuw worden afgespeeld tegen passieve kopieën van de database, worden dezelfde fysieke wijzigingen aangebracht in deze passieve databases.