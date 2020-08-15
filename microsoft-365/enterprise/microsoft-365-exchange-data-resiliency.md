---
title: Gegevens tolerantie voor Exchange Online in Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
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
description: In dit artikel vindt u een beschrijving van de verschillende aspecten van gegevens tolerantie binnen Exchange Online en Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dfc53fd48a6de61cf47a0441cd2f8b0fa35a73f1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695708"
---
# <a name="exchange-online-data-resiliency-in-microsoft-365"></a>Gegevens tolerantie voor Exchange Online in Microsoft 365

Er zijn twee typen schade die van invloed kunnen zijn op een Exchange-database: fysiek beschadigd, die meestal wordt veroorzaakt door hardware (met name voor de opslag van hardware), en logische beschadiging, wat zich als gevolg van andere factoren voordoet. In het algemeen zijn er twee typen logische beschadiging die kunnen optreden in een Exchange-database: 
- **Logische fout in database** : de controlesom van de databasepagina, maar de gegevens op de pagina zijn niet logisch. Dit kan gebeuren wanneer de database-engine (de Extensible Storage Engine) probeert een databasepagina te schrijven, terwijl het besturingssysteem een succes bericht retourneert, worden de gegevens niet naar de verkeerde plaats geschreven. Dit wordt een *verloren flush*genoemd. ESE bevat diverse functies en beveiligingsfuncties die zijn ontworpen om fysiek beschadiging van een database en andere scenario's voor verlies van gegevens te voorkomen. Om te voorkomen dat u verloren gegane gegevens kwijtraakt, bevat ESE een verloren flush detectiemechanisme in de database, samen met een functie (herstel van één pagina) om de fout te corrigeren. 
- **Logische beschadiging opslaan** : gegevens worden toegevoegd, verwijderd of gemanipuleerd, zodat de gebruiker dat niet verwacht. Deze gevallen worden algemeen veroorzaakt door toepassingen van derden. Het is doorgaans slechts een beschadiging in de zin dat de gebruiker het als beschadigd weergeeft. De Exchange Store beschouwt de transactie die de logische beschadiging heeft gemaakt voor een reeks geldige MAPI-bewerkingen. De functies voor [in-place bewaring](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds) in Exchange Online bieden beveiliging tegen logische beschadiging van de opslag (omdat hierdoor wordt voorkomen dat inhoud permanent wordt verwijderd door een gebruiker of toepassing). 

Exchange Online voert diverse consistentiecontroles uit op gerepliceerde logboekbestanden tijdens de controle van beide gebeurtenissen en logboek herhaling. Met deze consistentiecontroles wordt voorkomen dat fysiek beschadigd door het systeem wordt gerepliceerd. Tijdens de inspectie van een logboek is er bijvoorbeeld een fysieke integriteitscontrole waarmee het logboekbestand wordt gecontroleerd en gevalideerd dat de controlesom die in het logboekbestand is opgenomen, overeenkomt met de in het geheugen gemaakte controlesom. Daarnaast wordt de header van het logboekbestand onderzocht, zodat u zeker weet dat de handtekening van het logboekbestand in de logboek header overeenkomt met die van het logboekbestand. Tijdens het opnieuw afspelen van het logboek wordt het logboekbestand verder onderzocht. De koptekst van een database bevat bijvoorbeeld de logboekhandtekening die wordt vergeleken met de handtekening van het logboekbestand om ervoor te zorgen dat deze overeenkomen. 

Beveiliging tegen beschadiging van postvakgegevens in Exchange Online wordt behaald met behulp van Exchange native Data Protection, een tolerantie strategie waarmee de replicatie op basis van toepassingen op meerdere servers en meerdere datacenters wordt gebruikt, samen met andere functies waarmee de bescherming van gegevens verloren gaat vanwege corruptie of andere redenen. Deze functies zijn ingebouwde functies die worden beheerd door Microsoft of de Exchange Online-toepassing zelf, zoals:

- [Groepen voor gegevensbeschikbaarheid](https://docs.microsoft.com/exchange/back-up-email)
- Oplossing voor één bit 
- Online database scannen 
- Verloren flush detectie 
- Terugzetten op één pagina 
- Service postvak replicatie 
- Controle van logboekbestanden 
- Implementatie in het robuuste bestandssysteem 

Voor meer informatie over de hierboven genoemde functies die hierboven worden vermeld, klikt u op de bovenstaande hyperlinks en zie hieronder voor meer informatie en voor meer informatie over items zonder hyperlinks. Naast deze interne functies bevat Exchange Online ook functies voor gegevens tolerantie die klanten kunnen beheren, zoals: 
- [Eenmalige artikel herstel (standaard ingeschakeld)](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages) 
- [Bewaren en ter plaatse bewaren](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds) 
- [Verwijderde Bewaar en verwijderde postvakken (beide standaard ingeschakeld)](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes) 

## <a name="database-availability-groups"></a>Database Beschikbaarheidsgroepen 
Elke postvakdatabase in Microsoft 365 wordt gehost in een [database Availability Group (dag)](https://docs.microsoft.com/exchange/back-up-email) en wordt gerepliceerd naar geografisch afzonderlijke datacenters in dezelfde regio. De meest voorkomende configuratie bevat vier databasekopieën in vier datacenters. Sommige regio's hebben echter minder datacenters (databases worden gerepliceerd naar drie datacenters in India en twee databases in Australië en Japan). In alle gevallen bevat elke postvakdatabase vier kopieën die in meerdere datacenters zijn verdeeld, zodat de gegevens van het postvak niet worden beveiligd tegen software-, hardware-en zelfs datacenter storingen. 

Bij deze vier kopieën zijn drie de versies geconfigureerd als in de hoogst beschikbare versies. De vierde kopie is geconfigureerd als een [betraagd database exemplaar](https://docs.microsoft.com/Exchange/high-availability/manage-ha/activate-lagged-db-copies). De kopie van de gewilde database is niet bedoeld voor herstel van een apart Postvak of voor herstel van postvakken. Het doel is een herstel mechanisme te verschaffen voor het zeldzame geval van een System-Wide, onherstelbare logische beschadiging. 

Onzichtbare databasekopieën in Exchange Online worden geconfigureerd met een vertragingstijd voor het opnieuw afspelen van logboekbestanden van zeven dagen. Daarnaast is de functie voor het opnieuw instellen van het Exchange-herhalings beheer ingeschakeld voor het afspelen van een dynamisch logboekbestand voor beschadigde kopieën, zodat de groei van databasekopieën kan worden hersteld en de groei van logboekbestanden kan worden hersteld. Hoewel het maken van databasekopieën in Exchange Online wordt gebruikt, is het belangrijk dat u begrijpt dat ze geen gegarandeerde back-up van de tijd zijn. Onzichtbare databasekopieën in Exchange Online hebben een beschikbaarheids drempel, meestal rond 90%, omdat de schijf met een onzichtbare kopie verloren gaat als gevolg van de schijfstoring, de geraakte kopie wordt een zeer beschikbare kopie en de perioden waarin de ongebruikte databasekopie opnieuw wordt samengesteld. 

## <a name="transport-resilience"></a>Transport tolerantie 
Exchange Online bevat twee primaire transport functies voor de kracht van een transport: schaduw-en veiligheids netwerk. Met schaduw herstel houdt u een overbodige kopie van een bericht in de transit. Beveiligings netwerk houdt een overtollige kopie van een bericht op dat de bezorging van het bericht is afgeleverd. 

Met schaduw redundantie maakt elke Exchange Online-Transport Server een kopie van elk bericht dat wordt ontvangen voordat het bericht naar de verzendende server wordt verzonden. Hiermee zorgt u ervoor dat alle berichten in de transport pijplijn overbodig worden in de transit. Als in Exchange Online wordt bepaald dat het oorspronkelijke bericht in transit verloren is gegaan, wordt een overtollige kopie van het bericht opnieuw bezorgd. 

Veiligheid netwerk is een transport wachtrij die is gekoppeld aan de transportservice op een mailbox-server. Deze wachtrij bevat kopieën van berichten die zijn verwerkt door de server. Wanneer een postvakdatabase of serverfout het activeren van een verouderde versie van de postvakdatabase vereist, worden berichten in de netwerkwachtrij voor veiligheid automatisch opnieuw verzonden naar de nieuwe actieve kopie van de postvakdatabase. Het nettovermogen van de veiligheid is ook overbodig, zodat transport niet als één moment van storing wordt veroorzaakt. Met het concept van een primair veiligheids netwerk en een Spellings veiligheids netwerk in de vorm van het primaire veiligheids netwerk is het niet mogelijk om meer dan 12 uur, moet u opnieuw een aanvraag indienen voor het opnieuw verzenden van berichten, en worden de berichten opnieuw geleverd via het internet.

Berichten worden opnieuw ingediend via het actieve beheeronderdeel van de Microsoft Exchange-service voor het beheren van DAGs-en postvakdatabase kopieën. U hoeft geen handmatige acties te ondernemen voor het opnieuw verzenden van berichten via het veiligheid-net. 

## <a name="single-bit-correction"></a>Oplossing voor één bit 
ESE omvat een mechanisme voor het detecteren en oplossen van eenmalige CRC-fouten (aka enkele-bits gespiegelde) die het resultaat zijn van hardwarefouten (en omdat ze fysiek corruptie weergeven). Wanneer deze fouten optreden, worden deze automatisch door ESE verholpen en wordt een gebeurtenis in het logboek logboek vastgelegd. 

## <a name="online-database-scanning"></a>Online database scannen 
Online database scan (ook wel *databases*toevoegen) is het proces waarbij een ESE een databaseconsistentie controle gebruikt om elke pagina te lezen en de beschadigde pagina's te controleren. Het belangrijkste doel is fysieke beschadiging en verloren vermiste leegmaak opdrachten op te sporen die mogelijk niet door transacties worden gedetecteerd. Met het scannen van databases worden ook crash activiteiten na de opslag uitgevoerd. De ruimte kan worden gelekt vanwege vastlopen en bij het scannen van online databases wordt verloren ruimte gevonden en hersteld. Het systeem is zo ontworpen dat elke database telkens eenmaal zeven dagen volledig wordt gescand. 

## <a name="lost-flush-detection"></a>Verloren flush detectie 
Een verloren Flushing doet zich voor wanneer een database schrijven en het besturingssysteem die als voltooid is geretourneerd, niet naar de schijf is geschreven of op de verkeerde locatie is geschreven. Verloren flush-incidenten kunnen resulteren in een logische beschadiging van de database, zodat verloren gegane gegevens verloren gaan, zodat geraakte gegevens verloren gaan, aangezien ESE een verloren flush detectiemechanisme omvat. Als databasepagina's zijn geschreven naar passieve kopieën, wordt een controle uitgevoerd voor verloren gegane verplaatsingen op de actieve kopie. Als een verloren leegmaak actie is gedetecteerd, kan ESE het proces met een patch proces voor pagina's herstellen. 

## <a name="single-page-restore"></a>Terugzetten op één pagina 
Het herstellen van enkele pagina's, aka *pagina patches*is een automatisch proces waarbij beschadigde databasepagina's worden vervangen door gezonde kopieën van een gezonde replica. Het herstelproces voor een beschadigde pagina is afhankelijk van het feit of de database-kopie actief of passief is. Wanneer een kopie van een actieve database een beschadigde pagina tegenkomt, kan deze een pagina uit een van de replica's kopiëren, op voorwaarde dat de gekopieerde pagina compleet is. Dit doet u door een aanvraag voor de pagina in de logboek stroom te plaatsen, dat wil zeggen de basis van de replicatie van de postvakdatabase. Zodra een replica een aanvraag voor de pagina bevindt, reageert de pagina en stuurt u een kopie van de pagina naar de aanvraag voor het aanvragen van een database. Herstel via één pagina biedt ook een asynchroon communicatie mechanisme waarmee een pagina wordt opgevraagd bij replica's, zelfs als de replica's momenteel offline zijn. 

Als een database beschadigd is en een kopie met een ongebruikte database wordt opgeslagen, kunt u een willekeurige pagina altijd veilig kopiëren van de actieve kopie naar een passieve kopie. Een passieve databasekopie is zo sterk beschikbaar, dus tijdens het patchings proces van de pagina wordt het opnieuw afspelen van het logboek stopgezet en wordt het kopiëren van gebeurtenissen voortgezet. Met de passieve databasekopie wordt een kopie van de beschadigde pagina van de actieve versie opgehaald en gewacht tot het logboekbestand voldoet aan de vereiste vereiste logboekgeneratie, en vervolgens wordt de beschadigde pagina op een andere pagina opgeslagen. Meld u opnieuw aan bij het aanmelden bij de pagina. Het proces is hetzelfde voor het onzichtbare database exemplaar, met uitzondering van de gestorete database voor het eerst alle logboekbestanden die nodig zijn om een patch te verkrijgen. 

## <a name="mailbox-replication-service"></a>Service postvak replicatie 
Postvakken verplaatsen is een belangrijk onderdeel van het beheren van een grootschalige e-mail service. Er zijn altijd updates voor technologieën en de hardware en versie van upgrades voor het oplossen van problemen, zodat onze ingenieurs een krachtig en vertraagd systeem kan uitvoeren, zodat onze technici deze werk doorzichtig kunnen maken (door ervoor te zorgen dat de gegevens in de hele procedure online blijven) de juiste manier van werken. 

De Exchange Mailbox Replication-service (MEVR) is verantwoordelijk voor het verplaatsen van postvakken tussen databases. Tijdens de verhuizing voert MEVR een consistentiecontrole uit op alle items in het postvak. Als het probleem zich voordoet, kunt u het probleem verhelpen door MEVR te raken of de beschadigde items over te slaan. 

Aangezien MEVR een onderdeel is van Exchange Online, kunnen we wijzigingen in de code aanbrengen om nieuwe vormen van beschadigingen die in de toekomst worden gedetecteerd, op te lossen. Als we bijvoorbeeld een consistent probleem detecteren dat MEVR niet mogelijk is te herstellen, kunnen we de beschadiging analyseren, de gemevre code wijzigen en de inconsistentie corrigeren (als we weten wat u wilt doen). 

## <a name="log-file-checks"></a>Controle van logboekbestanden 
Alle logbestanden met transactielogbestanden die zijn gegenereerd door een Exchange-database, worden in diverse vormen van consistentiecontroles uitgevoerd. Wanneer een logboekbestand wordt gemaakt, wordt het eerste patroon gemaakt en wordt een reeks logboeken uitgevoerd. Hiermee kan Exchange Online een aantal controles uitvoeren (Flush, CRC en andere controles) voor het valideren van elk logboekbestand terwijl het wordt vastgelegd, en opnieuw wanneer het wordt gerepliceerd. 

## <a name="deployment-on-resilient-file-system"></a>Implementatie in het robuuste bestandssysteem 
Om te voorkomen dat een bestand op het bestandssysteem wordt beschadigd, wordt Exchange Online geïmplementeerd op een programma voor een flexibele bestandssysteem (ReFS) voor betere herstelmogelijkheden. ReFS is een bestandssysteem in Windows Server 2012 en hoger, dat is ontworpen om krachtigere gegevens te bieden tegen beschadiging en de beschikbaarheid en integriteit van gegevens te optimaliseren. Met name zorgt ReFS voor een betere beveiliging van de manier waarop metagegevens worden bijgewerkt, wat betere bescherming biedt voor gegevens en de schade van beschadigde gegevens vermindert. Er worden ook controlefuncties gebruikt om de integriteit van bestandsgegevens en metagegevens te controleren, zodat beschadigde gegevens gemakkelijk kunnen worden gevonden en hersteld. 

Exchange Online profiteert van diverse ReFS-voordelen: 
- Meer tolerantie voor de integriteit van gegevens betekent minder gegevensbeschadiging. Verminderen van het aantal beschadigde incidenten betekent dat u minder onnodige database-inhoudings zaden hoeft te maken. 
- Checksum voert de detectie van beschadigings problemen sneller en verder deterministisch in, zodat ons de hoeveelheid gegevens van klanten kan repareren voordat grijs fouten zich voordoen op gegevensvolumes.
- Ontworpen om goed te werken met extreem grote gegevenssets, petabytes en groter, zonder gevolgen voor de prestaties
- Ondersteuning voor andere functies die door Exchange Online worden gebruikt, zoals BitLocker-versleuteling. 

Exchange Online profiteert ook van andere ReFS-functies: 
- **Integriteit (integriteits gegevens)** -ReFS slaat gegevens op een andere manier op, zodat deze te beschermen tegen een groot aantal veelvoorkomende fouten die tot gevolg kunnen hebben dat gegevens verloren gaan. In Microsoft 365 Search wordt gebruikgemaakt van integriteits stromen voor de detectie en controle van de inhoud van de oudere schijf. Met de functie worden ook beschadigings problemen vertraagd als gevolg van afgebroken schrijfbewerkingen (wanneer een schrijfbewerking niet wordt voltooid vanwege verouderings kracht, enzovoort). 
- **Beschikbaarheid (restwaarde)** : ReFS doet de beschikbaarheid van gegevens. Historisch: bestandssystemen waren vaak gevoelig voor beschadigde gegevens, waarvoor het systeem offline werd gebruikt voor herstel. Hoewel dit niet het geval is, kan de ReFS, indien beschadigd, worden gebruikt door ReFS, een functie waarmee de beschadigde gegevens uit de naamruimte op een live volume worden verwijderd en ervoor zorgt dat goede gegevens niet nadelig worden beïnvloed door niet-herstelbare beschadigde gegevens. Als u de functie rest. na toepast en beschadigde gegevens opisoleert voor Exchange Online-database volumes, kunnen we niet-getroffen databases op een beschadigd volume bewaren tussen de tijd van beschadigd raken en de reparatieactie. Hierdoor wordt de beschikbaarheid van databases die normaal gevolgen voor beschadigde schijfproblemen beïnvloed, verhoogd. 