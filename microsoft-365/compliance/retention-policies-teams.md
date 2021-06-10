---
title: Meer informatie over retentie voor Teams
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Lees meer over bewaarbeleid dat van toepassing is op Microsoft Teams.
ms.openlocfilehash: 607fbdd02cfaccfee79df67c4946c178ff3eb383
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861573"
---
# <a name="learn-about-retention-for-microsoft-teams"></a>Meer informatie over retentie voor Microsoft Teams

>*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!NOTE]
> Raadpleeg [Teams-berichten over bewaarbeleid](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b) als u in Teams een bericht ziet dat uw chats of berichten door een bewaarbeleid zijn verwijderd.
> 
> De informatie op deze pagina is voor IT-beheerders die dit bewaarbeleid beheren.

De informatie in dit artikel is een aanvulling op [Meer informatie over retentie](retention.md), omdat deze informatie specifiek is voor berichten in Microsoft Teams.

Zie voor andere workloads:

- [Meer informatie over retentie voor SharePoint en OneDrive](retention-policies-sharepoint.md)
- [Meer informatie over retentie voor Yammer](retention-policies-yammer.md)
- [Meer informatie over retentie voor Exchange](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a>Wat is inbegrepen voor retentie en verwijdering

Teams kunnen chatberichten en kanaalberichten verwijderen met behulp van bewaarbeleid voor Teams. Naast de tekst in de berichten kunnen de volgende items vanwege nalevingsredenen worden bewaard: ingesloten afbeeldingen, tabellen, hypertekstkoppelingen, koppelingen naar andere berichten en bestanden in Teams, en [inhoud van kaarten](/microsoftteams/platform/task-modules-and-cards/what-are-cards). Chatberichten bevatten alle namen van de personen in de chat en kanaalberichten bevatten de teamnaam en de berichttitel (indien opgegeven). 

> [!NOTE]
> Het opnemen van inhoud van kaarten in een bewaarbeleid voor Teams is een vrij recente toevoeging. Zie [Microsoft 365 compliance capabilities for Adaptive Card content through apps in Teams now available (Nalevingsmogelijkheden van Microsoft 365 voor inhoud van Adaptive Card via apps in Teams nu beschikbaar)](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-365-compliance-capabilities-for-adaptive-card-content/ba-p/2095869) voor meer informatie.

Berichten van teams in privékanalen worden momenteel niet ondersteund voor bewaarbeleid. Codefragmenten, opgenomen gesproken memo's van de mobiele Teams-client, miniaturen, aankondigingsafbeeldingen en reacties van anderen in de vorm van emoticons blijven niet behouden wanneer u bewaarbeleid voor Teams gebruikt.

E-mailberichten en bestanden die u gebruikt in Teams zijn niet opgenomen in bewaarbeleid voor Teams. Deze items hebben hun eigen bewaarbeleid.

## <a name="how-retention-works-with-microsoft-teams"></a>Hoe bewaarbeleid werkt met Microsoft Teams

Gebruik deze sectie als u wilt weten hoe aan uw nalevingsvereisten wordt voldaan door back-endopslag en -processen. Dit moet worden gecontroleerd met behulp van eDiscovery-hulpprogramma's in plaats van aan de hand van berichten die momenteel zichtbaar zijn in de Teams-app.

U kunt een bewaarbeleid gebruiken om gegevens uit chats en kanaalberichten in Teams te behouden en deze chats en berichten te verwijderen. Achter de schermen worden Exchange-postvakken gebruikt om gegevens op te slaan die uit deze berichten zijn gekopieerd. Gegevens uit Teams-chats worden opgeslagen in een verborgen map in het postvak van elke gebruiker die in de chat is opgenomen. Een soortgelijke verborgen map in een groepspostvak wordt gebruikt voor Teams-kanaalberichten. Deze verborgen mappen zijn niet ontworpen om rechtstreeks toegankelijk te zijn voor gebruikers of beheerders, maar slaan in plaats daarvan gegevens op die beheerders met eDiscovery-hulpprogramma's kunnen zoeken.

Deze postvakken worden weergegeven aan de hand van het kenmerk RecipientTypeDetails:

- **UserMailbox**: in deze postvakken worden berichtgegevens opgeslagen voor gebruikers van Teams in de cloud.
- **MailUser**: in deze postvakken worden berichtgegevens opgeslagen voor [on-premises Teams-gebruikers](search-cloud-based-mailboxes-for-on-premises-users.md).
- **GroupMailbox**: in deze postvakken worden berichtgegevens voor Teams-kanalen opgeslagen.

Andere postvakken, zoals RoomMailbox, die wordt gebruikt voor vergaderruimten in Teams, worden niet ondersteund voor bewaarbeleid van Teams.

Teams gebruikt een op Azure gebaseerd chatservice als primaire opslag voor alle berichten (chats en kanaalberichten). Als u Teamsberichten vanwege nalevingsredenen wilt verwijderen, kan het bewaarbeleid voor Teams berichten na een opgegeven periode verwijderen op basis van het moment dat ze zijn gemaakt. Berichten worden vervolgens definitief verwijderd uit zowel de Exchange-postvakken waarin ze zijn opgeslagen voor naleving, als uit de primaire opslag die wordt gebruikt door de onderliggende Azure-chatservice. Zie [Beveiliging en naleving in Microsoft Teams](/MicrosoftTeams/security-compliance-overview) en met name de sectie [Information Protection Architecture](/MicrosoftTeams/security-compliance-overview#information-protection-architecture) voor meer informatie over de onderliggende architectuur.

Hoewel deze gegevens van Teams-chats en -kanaalberichten in postvakken worden opgeslagen, moet u een bewaarbeleid configureren voor de locaties van **Teams-kanaalberichten** en **Teams-chats**. Teams-chats en -kanaalberichten worden niet opgenomen in bewaarbeleid dat is geconfigureerd voor Exchange-gebruikers- of groepspostvakken.

> [!NOTE]
> Als een gebruiker is opgenomen in een actief bewaarbeleid waarin Teamsberichten worden bewaard en u een postvak verwijdert van een gebruiker die in dit beleid is opgenomen, wordt het postvak omgezet naar een [inactief postvak](inactive-mailboxes-in-office-365.md) om de gegevens in Teams te behouden. Als u deze Teams-gegevens voor de gebruiker niet wilt bewaren, moet u het gebruikersaccount uitsluiten van het bewaarbeleid voordat u het postvak van de gebruiker verwijdert.

Nadat een bewaarbeleid voor chatberichten en kanaalberichten is geconfigureerd, controleert een timer voor de Exchange-service regelmatig items in de verborgen map waarin deze Teams-berichten zijn opgeslagen. Het duurt meestal 1-7 dagen voordat de timer wordt uitgevoerd. Wanneer de retentieperiode voor deze items is verstreken, worden ze verplaatst naar de map SubstrateHolds. Dit is een andere verborgen map in het postvak van elke gebruiker of groep waarin 'soft-verwijderde' items worden opgeslagen voordat ze definitief worden verwijderd. 

Berichten blijven ten minste één dag in de map in de map SubstrateHolds staan. Als ze in aanmerking komen voor verwijdering, worden deze bij de volgende uitvoering definitief verwijderd door de timer.

> [!NOTE]
> Vanwege het [eerste bewaarprincipe](retention.md#the-principles-of-retention-or-what-takes-precedence) wordt een permanente verwijdering altijd opgeschort als hetzelfde item moet worden bewaard vanwege een ander bewaarbeleid of als het om juridische of onderzoeksredenen onder een eDiscovery-bewaring valt.

Nadat een bewaarbeleid voor chat- en kanaalberichten is geconfigureerd, zijn de paden die de inhoud aflegt afhankelijk van of het bewaarbeleid bestaat uit het behouden en vervolgens verwijderen of alleen uit het behouden of verwijderen ervan.

Wanneer het bewaarbeleid bepaalt dat inhoud moet worden behouden en vervolgens moet worden verwijderd:

![Diagram van bewaarstroom voor Teams-chats en -kanaalberichten](../media/teamsretentionlifecycle.png)

Voor de twee paden in het diagram:

1. **Als een chat- of kanaalbericht wordt bewerkt of verwijderd** door een gebruiker tijdens de retentieperiode, wordt het oorspronkelijke bericht gekopieerd (indien bewerkt) of verplaatst (indien verwijderd) naar de map SubstrateHolds. Het bericht wordt daar ten minste één dag opgeslagen. Wanneer de retentieperiode is verstreken, wordt het bericht definitief verwijderd wanneer de timer de volgende keer wordt uitgevoerd (meestal tussen 1-7 dagen).

2. **Als een chat- of kanaalbericht niet wordt verwijderd** door een gebruiker, wordt het bericht (evenals huidige berichten na bewerking) naar de map SubstrateHolds verplaatst wanneer de retentieperiode is verstreken. Deze actie vindt meestal plaats tussen 1 en 7 dagen na de vervaldatum. Wanneer het bericht in de map SubstrateHolds is opgeslagen, wordt het daar ten minste één dag opgeslagen, waarna het bericht definitief wordt verwijderd wanneer de timer de volgende keer wordt uitgevoerd (meestal tussen 1-7 dagen). 

> [!NOTE]
> Berichten die in postvakken zijn opgeslagen, inclusief de verborgen mappen, zijn doorzoekbaar in eDiscovery-hulpprogramma's. Berichten blijven doorzoekbaar met eDiscovery-hulpprogramma's totdat ze permanent worden verwijderd uit de map SubstrateHolds.

Als berichten permanent uit de map SubstrateHolds worden verwijderd, wordt er een verwijderbewerking verzonden naar de Backend Azure-chatservice, die dezelfde bewerking daarna doorgeeft aan de Teams-clientapp. Vertragingen in deze communicatie of caching kunnen verklaren waarom gebruikers deze berichten mogelijk nog korte tijd in hun Teams-app zien, maar gegevens uit deze berichten worden niet geretourneerd in eDiscovery-zoekopdrachten. Berichten die zichtbaar zijn in de Teams-app, vormen geen nauwkeurige weerspiegeling van of ze worden bewaard of definitief zijn verwijderd vanwege nalevingsvereisten.

Als het bewaarbeleid is ingesteld op alleen bewaren of alleen verwijderen, is de route die de inhoud aflegt een variatie van bewaren en verwijderen.

### <a name="content-paths-for-retain-only-retention-policy"></a>Inhoudsroutes voor retentiebeleid voor alleen bewaren

1. **Als een chat- of kanaalbericht wordt bewerkt of verwijderd** door een gebruiker tijdens de retentieperiode, wordt het oorspronkelijke bericht gekopieerd (indien bewerkt) of verplaatst (indien verwijderd) naar de map SubstrateHolds en daar minimaal 1 dag bewaard. Als het bewaarbeleid is geconfigureerd voor altijd bewaren, blijft het item daar staan. Als het bewaarbeleid een einddatum voor de retentieperiode kent en deze verstrijkt, wordt het bericht definitief verwijderd wanneer de timer de volgende keer wordt uitgevoerd (meestal tussen 1-7 dagen).

2. **Als de chat of het kanaalbericht niet wordt gewijzigd of verwijderd** door een gebruiker tijdens de retentieperiode, en in geval van huidige berichten na bewerking tijdens de retentieperiode: er gebeurt niets voor en na de retentieperiode; het bericht blijft op de oorspronkelijke locatie staan.

### <a name="content-paths-for-delete-only-retention-policy"></a>Inhoudsroutes voor retentiebeleid voor alleen verwijderen

1. **Als het chat- of kanaalbericht wordt bewerkt of verwijderd** door een gebruiker tijdens de retentieperiode, wordt het oorspronkelijke bericht gekopieerd (indien bewerkt) of verplaatst (indien verwijderd) naar de map SubstrateHolds. Het bericht blijft daar minimaal 1 dag staan en wordt definitief verwijderd wanneer de timer de volgende keer wordt uitgevoerd (meestal 1-7 dagen).

2. **Als een chat- of kanaalbericht niet wordt verwijderd** door een gebruiker tijdens de retentieperiode: het bericht wordt aan het einde van de retentieperiode naar de map SubstrateHolds verplaatst. Deze actie vindt meestal plaats tussen 1 en 7 dagen na de vervaldatum. Het bericht blijft daar minimaal 1 dag staan en wordt daarna definitief verwijderd wanneer de timer de volgende keer wordt uitgevoerd (meestal 1-7 dagen).

#### <a name="example-flows-and-timings-for-retention-policies"></a>Voorbeeldstromen en tijdsinstellingen voor bewaarbeleid

Gebruik de volgende voorbeelden om te zien hoe de processen en tijdsinstellingen die in de vorige secties zijn uitgelegd, van toepassing zijn op bewaarbeleid met de volgende configuraties:

- [Voorbeeld 1: Alleen bewaren gedurende 7 jaar](#example-1-retain-only-for-7-years)
- [Voorbeeld 2: 30 dagen bewaren en vervolgens verwijderen](#example-2-retain-for-30-days-and-then-delete)
- [Voorbeeld 3: Alleen verwijderen na 1 dag](#example-3-delete-only-after-1-day)

Voor alle voorbeelden waarin naar permanente verwijdering wordt verwezen, geldt dat deze actie vanwege de [beginselen voor het bewaren](retention.md#the-principles-of-retention-or-what-takes-precedence) wordt opgeschort als voor het bericht een ander bewaarbeleid geldt om het item te behouden of als er sprake is van eDiscovery-bewaring.

##### <a name="example-1-retain-only-for-7-years"></a>Voorbeeld 1: Alleen bewaren gedurende 7 jaar

Een gebruiker maakt op dag 1 een chat- of kanaalbericht.

Op dag 5 bewerkt de gebruiker dat bericht.

Op dag 30 verwijdert de gebruiker het huidige bericht.

Resultaten van retentie:

- Voor het oorspronkelijke bericht:
    - Op dag 5 wordt het bericht gekopieerd naar de map SubstrateHolds, waar het nog minimaal 7 jaar vanaf dag 1 (de retentieperiode) kan worden gezocht met eDiscovery-hulpprogramma's.

- Voor het huidige (bewerkte) bericht:
    - Op dag 30 wordt het bericht verplaatst naar de map SubstrateHolds, waar het nog minimaal 7 jaar vanaf dag 1 (de retentieperiode) kan worden gezocht met eDiscovery-hulpprogramma's.

Als de gebruiker het huidige bericht ná de opgegeven retentieperiode in plaats van bínnen de retentieperiode heeft verwijderd, wordt het bericht nog steeds verplaatst naar de map SubstrateHolds. Nu de retentieperiode echter is verstreken, wordt het bericht na minimaal één dag en meestal binnen 1-7 dagen definitief verwijderd.

##### <a name="example-2-retain-for-30-days-and-then-delete"></a>Voorbeeld 2: 30 dagen bewaren en vervolgens verwijderen

Een gebruiker maakt op dag 1 een chat- of kanaalbericht.

Op dag 10 bewerkt de gebruiker dat bericht.

De gebruiker voert geen verdere wijzigingen door en verwijdert het bericht niet.

Resultaten van retentie:

- Voor het oorspronkelijke bericht:
    - Op dag 10 wordt het bericht gekopieerd naar de map SubstrateHolds, waar het nog steeds kan worden gezocht met eDiscovery-hulpprogramma's.
    - Aan het einde van de retentieperiode (30 dagen vanaf dag 1) wordt het bericht meestal binnen 1 7 dagen na minimaal 1 dag definitief verwijderd en vervolgens niet geretourneerd met eDiscovery-zoekopdrachten.

- Voor het huidige (bewerkte) bericht:
    - Aan het einde van de retentieperiode (30 dagen vanaf dag 1) wordt het bericht meestal binnen 1-7 dagen verplaatst naar de map SubstrateHolds, waar het nog steeds kan worden gezocht met eDiscovery-hulpprogramma's.
    - Het bericht wordt daarna na minimaal 1 dag meestal binnen 1 7 dagen definitief verwijderd en kan niet meer worden gevonden met eDiscovery-zoekopdrachten.

##### <a name="example-3-delete-only-after-1-day"></a>Voorbeeld 3: Alleen verwijderen na 1 dag

> [!NOTE]
> Vanwege de korte periode van 1 dag van deze configuratie- en bewaarprocessen, die plaatsvinden binnen een periode van 1-7 dagen, toont deze sectie voorbeeldtijdsinstellingen binnen de normale perioden.

Een gebruiker maakt op dag 1 een chat- of kanaalbericht.

Voorbeeld van bewaarresultaat als de gebruiker het bericht niet bewerkt of verwijdert:

- Dag 5 (meestal 1-7 dagen na het begin van de retentieperiode op dag 2):
    - Het bericht wordt verplaatst naar de map SubstrateHolds en blijft daar minimaal 1 dag, waar het nog steeds kan worden gezocht met eDiscovery-hulpprogramma's.

- Dag 9 (meestal 1-7 dagen na minimaal 1 dag in de map SubstrateHolds):
    - Het bericht wordt definitief verwijderd en wordt vervolgens niet geretourneerd met eDiscovery-zoekopdrachten.

Zoals u in dit voorbeeld kunt zien, kunt u een bewaarbeleid configureren om berichten na één dag te verwijderen. De service ondergaat meerdere processen om ervoor te zorgen dat berichten volgens de regels worden verwijderd. Hierdoor kan het na het verwijderen op dag 1 nog 16 dagen duren voordat het bericht definitief wordt verwijderd, zodat het niet meer wordt geretourneerd in eDiscovery-zoekopdrachten.

## <a name="skype-for-business-and-teams-interop-chats"></a>Uitwisseling van chats in Skype voor Bedrijven en Teams

Wanneer een Skype voor Bedrijven-chat binnenkomt in Teams, wordt het een bericht in een Teams-chatthread en opgenomen in het juiste postvak. Op deze berichten in de Teams-thread is bewaarbeleid voor Teams van toepassing. 

Maar als de gespreksgeschiedenis voor Skype voor Bedrijven en vanuit de Skype voor Bedrijven-client is ingeschakeld, wordt die geschiedenis opgeslagen in een postvak en worden die chatgegevens niet verwerkt door een bewaarbeleid voor Teams. Gebruik voor deze inhoud een bewaarbeleid dat is geconfigureerd voor Skype voor Bedrijven.

## <a name="meetings-and-external-users"></a>Vergaderingen en externe gebruikers

Berichten van kanaalvergaderingen worden op dezelfde manier opgeslagen als kanaalberichten. Selecteer voor deze gegevens de locatie voor de **Teams-kanaalberichten** wanneer u uw bewaarbeleid configureert.

Berichten voor ad hoc en geplande vergaderingen worden op dezelfde manier opgeslagen als groepsgespreksberichten. Selecteer voor deze gegevens de locatie voor de **Teams-chats** wanneer u uw bewaarbeleid configureert.

Wanneer externe gebruikers worden opgenomen in een vergadering die uw organisatie belegt:

- Als een externe gebruiker deelneemt met behulp van een gastaccount in uw tenant, heeft deze gebruiker een schaduwpostvak dat kan worden onderworpen aan het bewaarbeleid van uw organisatie voor Teams. Alle berichten van de vergadering worden opgeslagen in het postvak van de gebruikers en in het schaduwpostvak. 

- Als een externe gebruiker lid wordt van een account van een andere Microsoft 365-organisatie kunnen berichten voor deze gebruiker niet worden verwijderd door uw bewaarbeleid, omdat deze zijn opgeslagen in het postvak van die gebruiker in een andere tenant. Voor dezelfde vergadering kunnen berichten echter door uw bewaarbeleid worden verwijderd voor uw gebruikers.

## <a name="when-a-user-leaves-the-organization"></a>Wanneer een gebruiker de organisatie verlaat 

Als een gebruiker met een postvak in Exchange Online uw organisatie verlaat en zijn of haar Microsoft 365-account wordt verwijderd, worden chatberichten die moeten worden bewaard, opgeslagen in een inactief postvak. De chatberichten blijven onderworpen aan het bewaarbeleid dat op de gebruiker van toepassing was voordat het postvak inactief werd en de inhoud blijft beschikbaar voor een eDiscovery-zoekopdracht. Zie voor meer informatie [Inactive postvakken in Exchange Online](inactive-mailboxes-in-office-365.md). 

Raadpleeg de [equivalente sectie](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) voor SharePoint en OneDrive als de gebruiker bestanden in Teams heeft opgeslagen.

## <a name="limitations"></a>Beperkingen

We werken voortdurend aan het optimaliseren van functionaliteit voor bewaren in Teams. In de tussentijd moet u rekening houden met de volgende beperking wanneer u bewaarbeleid gebruikt voor kanaalberichten en chats van Teams:

- **Foutieve weergave in Outlook**. Als u bewaarbeleid voor Skype- of Teams-locaties maakt, wordt een van deze beleidsregels weergegeven als het standaardmapbeleid wanneer een gebruiker de eigenschappen van een postvakmap in de Outlook-bureaubladclient bekijkt. Dit is een foutieve weergave in Outlook; het [probleem is bekend](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies). In plaats daarvan zou u het bewaarbeleid voor postvakken moeten zien dat wordt toegepast op de map. Het bewaarbeleid voor Skype of Teams wordt niet toegepast op het postvak van de gebruiker.

## <a name="configuration-guidance"></a>Configuratie-richtlijnen

Zie [Aan de slag met bewaarbeleid en retentielabels](get-started-with-retention.md) als het configureren van retentie in Microsoft 365 nieuw voor u is.

Zie [Bewaarbeleid maken en configureren](create-retention-policies.md) als u een bewaarbeleid voor Teams wilt configureren.