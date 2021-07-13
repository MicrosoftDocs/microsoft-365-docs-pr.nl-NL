---
title: Beleidsregels maken en beheren in Microsoft-privacybeheer (voorbeeld)
f1.keywords:
- CSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- M365-privacy-management
search.appverid:
- MOE150
- MET150
description: Informatie over het maken en beheren van beleidsregels voor het verwerken van de persoonlijke gegevens van uw organisatie in Microsoft 365, reageren op waarschuwingen en problemen oplossen.
ms.openlocfilehash: f9df027d01ffe4629654db1ddd006d141d57e387
ms.sourcegitcommit: 022d9d91263994c48efcebe08a84319573dc3a8c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53378513"
---
# <a name="create-and-manage-policies-in-privacy-management-preview"></a>Beleidsregels maken en beheren in privacybeheer (voorbeeld)

In dit artikel leert u  hoe u beleidsregels  kunt maken en aanpassen voor het verwerken van persoonlijke gegevens, waarschuwingen over beleidswedstrijden kunt krijgen en problemen kunt **oplossen.**

## <a name="purpose-of-policies"></a>Doel van beleid

Met beleidsregels kunt u de typen privacyrisico's definiëren waar u op moet passen in de Microsoft 365 van uw bedrijf en de gewenste resultaten vaststellen voor scenario's waarin overeenkomsten worden gevonden. Uw organisatie kan vanuit de resulterende waarschuwingen werken om overeenkomende gegevens te bekijken en problemen op te lossen, allemaal vanuit de oplossing voor privacybeheer.

Privacybeheer biedt sjablonen waarmee u eenvoudig aan de slag kunt met het maken van beleid en waarmee u uw aanpak kunt afstemmen via uitgebreide aanpassingsopties. De belangrijkste scenario's die worden bestreken door de sjablonen van privacybeheer zijn de volgende:

- **Gegevens overbelicht:** detecteert overbelichte persoonlijke gegevens en vraagt gebruikers deze te beveiligen.
- **Gegevensoverdracht:** helpt bij het beperken van de overdracht van persoonlijke gegevens over afdelingen of landgrenzen.
- **Gegevensminimatie:** helpt gebruikers de hoeveelheid ongebruikte persoonlijke gegevens te identificeren en te beperken.

Zie hieronder voor meer informatie over de mogelijkheden van elke sjabloon.

## <a name="policy-types"></a>Beleidstypen

### <a name="data-overexposure"></a>Gegevens overbelichting

Privacybeheer kan u helpen bij het opsporen en verwerken van situaties waarin gegevens die u hebt opgeslagen onvoldoende beveiligd zijn. Als de toegang tot een interne site bijvoorbeeld is geopend voor een te brede groep of als uw machtigingsinstellingen niet up-to-date zijn gehouden, kunnen persoonlijke gegevens die op die site zijn opgeslagen, kwetsbaar zijn voor een inbreuk. U kunt de gegevensbeleidssjabloon van privacybeheer gebruiken om uw gegevens te evalueren en u te waarschuwen voor mogelijke problemen.

### <a name="data-transfer"></a>Gegevensoverdracht

Door gegevens over afdelingen of landgrenzen over te brengen, kan het risico op blootstelling aan gegevens toenemen, bijvoorbeeld als deze wordt verzonden via niet-versleutelde e-mailberichten of naar niet-geautoriseerde geadresseerden. Dergelijke acties kunnen gevolgen hebben voor de regelgeving of kunnen ind strijd zijn met gevestigde procedures voor privacy. Als u de gegevensoverdrachtsjabloon gebruikt om beleidsregels voor privacybeheer te maken, kunt u dergelijke overdrachten herkennen en beperken.

> [!NOTE]
> Tijdens een openbare preview kunnen sommige tenants die beleidsregels voor gegevensoverdracht uitvoeren om overdrachten tussen regio's te detecteren, problemen ondervinden met synchronisatie die van invloed zijn op de zichtbaarheid van beleidsregels in Exchange en Teams gegevens. Het is raadzaam om u te concentreren op SharePoint en OneDrive terwijl u een voorbeeld van dit beleidstype bekijkt. Een update voor dit probleem wordt verwacht in het najaar van 2021.

### <a name="data-minimization"></a>Gegevensminimation

In de tijd kunnen bedrijven grote hoeveelheden persoonlijke gegevens verzamelen van klanten of werknemers. Soms omvat dit gegevens die boven de behoefte zijn verzameld of die anders niet worden gebruikt en die moeten worden beperkt om privacyrisico's rond die informatie te beperken. De gegevensminimationsjabloon kan worden gebruikt om risico's van dit type aan te pakken.

## <a name="get-started-with-default-templates"></a>Aan de slag met standaardsjablonen

Privacybeheer helpt uw gegevensevaluatieproces te starten door drie beleidsregels met standaardinstellingen te maken, met behulp van de sjablonen voor gegevensminimimatie, overbelichting van gegevens en gegevensoverdracht. Dit beleid is standaard ingeschakeld, maar zal niet automatisch meldingsberichten of herstelprompts activeren. Na de eerste installatie kunt u doorgaan met het maken en aanpassen van uw eigen beleid.

## <a name="create-a-privacy-management-policy"></a>Een privacybeleid maken

Er zijn twee paden voor het maken van privacybeheerbeleid. De eerste optie is om te kiezen uit de set vooraf gedefinieerde sjablonen. U kunt ook uw eigen beleid aanpassen, met behulp van een van deze sjablonen als uitgangspunt.

### <a name="create-a-policy-from-a-template"></a>Een beleid maken op basis van een sjabloon

Als u meteen aan de slag wilt met een beleid, selecteert u een van de drie vooraf ingestelde beleidstypen. Als u de details van een van deze opties wilt bekijken, kunt u Weergave-instellingen selecteren om de specifieke eigenschappen weer te geven die deel uit maken van het beleid, inclusief gegevenstypen, gegevenslocaties en de voorwaarden die het beleid activeren.

Wanneer u rechtstreeks vanuit een sjabloon een beleid maakt, worden er automatisch veel instellingen voor u gekozen. Dit geldt ook voor het standaard in- en uitschakelen van het beleid. Als u een voorbeeld van het beleid in actie wilt bekijken voordat u het volledig activeert, vindt u het in de lijst na het maken, bewerkt u het beleid en schakelt u het in de testmodus in. Zie Uw beleid [testen voor meer informatie.](#test-your-policy)

### <a name="create-custom-policy"></a>Aangepast beleid maken

Als u de instellingen van een beleid gedetailleerd wilt beheren, kunt u een aangepast beleid maken met behulp van een van de bestaande sjablonen als basislijn. Privacybeheer biedt een wizard om u door deze stappen te begeleiden.

Aanpasbare eigenschappen zijn:

- **Naam en type:** Kies de sjabloon waarop u uw beleid wilt bouwen en beschrijf de versie.
- **Gegevens die u wilt controleren:** Selecteer het type persoonlijke gegevens dat door uw beleid wordt gecontroleerd. Kies een van de beschikbare classificatiegroepen of kies uit de lijst met afzonderlijke gevoelige informatietypen. Zie Opties voor gegevenscontrole kiezen hieronder voor meer informatie.
- **Gebruikers:** Selecteer of dit beleid van toepassing is op alle gebruikers of geselecteerde gebruikers. Als u de tweede optie kiest, kunt u maximaal 300 gebruikers van uw keuze selecteren in de opgegeven lijst.
- **Locaties:** Kies de locaties binnen Microsoft 365 die in uw beleid moeten worden bestrijken, zoals de gegevens van uw organisatie SharePoint of Exchange gegevens.
- **Voorwaarden:** Selecteer de relevante voorwaarden voor uw type beleid. U kunt bijvoorbeeld opgeven welke typen overdrachten een beleid voor gegevensoverdracht moet zoeken of hoe onlangs gegevens zijn gebruikt voor een beleid voor gegevensminimimatie.
- **Resultaten:** Definieer resultaten wanneer een beleidsmatch wordt gedetecteerd. De opties zijn afhankelijk van het type beleid dat u wilt gebruiken. Mogelijke resultaten zijn:
  - **E-mailmeldingen:** met deze instelling kunt u verteerbare e-mailmeldingen activeren, inclusief koppelingen naar gerelateerde training. Zie E-mailmeldingen voor gebruikers instellen hieronder voor meer informatie.
  - **Teams:** Geef gebruikers in Teams beleidstips en aanbevelingen, samen met koppelingen naar gerelateerde training. Deze optie is beschikbaar voor beleid voor gegevensoverdracht.
- **Waarschuwingen:** Bepaal de frequentie van waarschuwingen aan beheerders wanneer een beleidsmatch wordt gedetecteerd. Opties zijn geen waarschuwingen, waarschuwingen voor elke beleidsmatch of waarschuwingen wanneer een specifieke drempel wordt bereikt. Als u de drempeloptie kiest, stelt u de gewenste parameters in.
- **Modus:** Bepaal of u eerst een beleid wilt uitvoeren in de testmodus of dat u het direct wilt inschakelen. Zie Uw beleid testen voor meer informatie.
Wanneer u alle instellingen in de wizard hebt door genomen, controleert u de instellingen, maakt u indien nodig de laatste wijzigingen en sla u uw beleid op.

#### <a name="choose-data-monitoring-options"></a>Opties voor gegevenscontrole kiezen

Wanneer u een aangepast beleid instelt, wordt u gevraagd te selecteren welke typen gegevens uw beleid moet controleren. De opties zijn als volgt:

- **Classificatiegroepen:** een doorzoekbare lijst met gegevenssets op basis van belangrijke privacyregels, zoals AVG of HIPAA. Bekijk de details van een groep om te zien welke typen gevoelige informatie de groep bestrijkt. Selecteer een of meer van deze sets om ze te gebruiken zoals het is. De groepen die momenteel beschikbaar zijn, zijn als volgt:
  - Australia Health Records Act (HRIP Act) Enhanced
  - Australië Privacy Act Enhanced
  - (EU) Algemene verordening gegevensbescherming (AVG) verbeterd
  - Persoonlijke gegevens (PII)-gegevens van Japan verbeterd
  - Japan Protection of Personal Information Enhanced
  - U.S. Gramm-Leach-Bliley Act (GLBA) Enhanced
  - U.S. Health Insurance Act (HIPAA) Enhanced
  - U.S. Patriot Act Enhanced
  - U.S. Persoonlijk identificeerbare gegevens (PII) Gegevens verbeterd
  - Amerikaanse wetten voor meldingsmelding door staatsinbreuk verbeterd
- **Afzonderlijke typen gevoelige informatie:** Door zelf specifieke typen gevoelige informatie te kiezen, zoals socialezekerheidsnummers of rijbewijsgegevens, kunt u uw eigen groep of groepen gegevens aanpassen om op te passen. Met deze wizard kunt u kiezen uit de volledige lijst met typen gevoelige informatie binnen privacybeheer. Elk informatietype heeft zijn eigen eigenschappen. Gebruik de infoknop naast een van deze opties voor meer informatie en notities over aanbevolen instellingen. Als u meer dan één groep maakt, kunt u met de wizard Booleaanse operatoren toepassen om deze te relateren en de volgorde van de bewerkingen te definiëren.

Als u vooraf ingesteld classificatiegroepen gebruikt, kunt u niet ook afzonderlijke typen selecteren of uw eigen groepen maken. Kies voor de meest flexibele informatietypen afzonderlijke gevoelige informatietypen. Als u de meest voorkomende standaarden wilt gebruiken, kiest u een van de classificatiegroepen.

#### <a name="test-your-policy"></a>Uw beleid testen

Als u een nieuw beleid wilt beoordelen voordat u het volledig activeert, stelt u uw beleid in op testmodus. Met de testmodus kunt u zoeken naar overeenkomsten van de afgelopen 30 dagen, het gedrag van het beleid meten en de gegenereerde typen waarschuwingen controleren. We raden u aan om testbeleid ten minste vijf dagen uit te voeren om representatieve resultaten te krijgen. U hebt de optie tijdens de testfase om de instellingen van het beleid te bewerken en aan te passen. Nadat u inzicht hebt verkregen bij het uitvoeren van de test, kunt u doorgaan met het in- en uit te zetten. Terwijl een beleid wordt uitgevoerd in de testmodus, worden er geen e-mailberichten met gebruikersmeldingen bezorgd.

#### <a name="set-user-email-notifications"></a>E-mailmeldingen voor gebruikers instellen

Bij e-mailmeldingen ontvangen gebruikers directe meldingen over beleidswedstrijden en belangrijke taken die moeten worden voltooid. De geadresseerden ontvangen e-mail digests waarin gegevens worden samengevat die moeten worden bekeken en mogelijke acties, zoals het privé maken van documenten, het bewaren van documenten in het bestand, het rapporteren van onwaar-positieve overeenkomsten en het toevoegen van notities voor toekomstige verwijzingen. Deze e-mailberichten bevatten ook koppelingen voor trainingsontvangers over het omgaan met deze zaken. Het verstrekken van deze koppelingen is vereist bij het in eerste instantie instellen van meldingen en dient te wijzen op uw eigen interne documentatie over processen en best practices.

Meldingen kunnen worden ingeschakeld voor afzonderlijke beleidsregels tijdens het maken van aangepaste beleidsregels of bij het bewerken van beleid. Gebruik de sectie Resultaten om te definiëren wat er gebeurt wanneer een beleidsmatch wordt gedetecteerd, inclusief de optie om deze meldingen in te stellen en in te stellen hoe vaak u wilt dat deze samenvattingen worden bezorgd.

De mogelijkheid voor e-mailmeldingen wordt beheerd op een globaal niveau binnen Instellingen. Deze functie is standaard ingeschakeld. Als u deze instelling uit schakelen, worden alle e-mailberichten gestopt, zelfs als specifieke meldingen zijn geconfigureerd op een afzonderlijk beleidsniveau. Zie Instellingen configureren onder [Aan de slag met privacybeheer voor meer informatie.](privacy-management-setup.md#configure-settings)

## <a name="view-policy-details"></a>Beleidsdetails weergeven

Nadat uw beleid is gemaakt, selecteert u het op de **hoofdpagina** Beleid om het volledige overzicht te bekijken. De pagina met beleidsdetails biedt inzicht in uw gegevens, stelt u in staat inhoud over specifieke beleidswedstrijden te bekijken en u te adviseren over de volgende stappen. Als uw beleid wordt uitgevoerd in de testmodus, kunt u op deze pagina ook uw beleid inschakelen wanneer het testen is voltooid.

Nadat uw beleid actief is, kunt u de pagina met beleidsdetails blijven bekijken om doorlopend inzicht te krijgen in probleemgebieden, ernst en trends van waarschuwingen en corrigerende acties.

## <a name="resolve-policy-alerts-and-issues"></a>Beleidswaarschuwingen en -problemen oplossen

Nadat uw beleid is geactiveerd, houdt privacybeheer u op de hoogte van belangrijke ontdekkingen door u te waarschuwen voor beleidswedstrijden, de ernst ervan te sorteren en u in staat te stellen actie te ondernemen door problemen te maken en op te lossen.

De pagina Overzicht van privacybeheer biedt een overzicht van deze bevindingen met dynamische updates over belangrijke aandachtspunten, zoals het beleid met de meeste overeenkomsten en uw momenteel actieve beleidswaarschuwingen. U hebt ook toegang tot details over uw waarschuwingen en problemen via de hoofdpagina Beleid.

### <a name="alerts"></a>Waarschuwingen

Als u uw actieve waarschuwingen wilt evalueren en wilt opgeven welke problemen moeten worden nagevolgd, gaat u naar **de pagina Waarschuwingen.** Het bevat een filterbare lijst met waarschuwingen die worden gegenereerd door uw beleid, die u afzonderlijk kunt controleren om te bepalen onder welke omstandigheden ze zijn geactiveerd.

Als u een waarschuwing selecteert, wordt een flyover-deelvenster geopend met aanvullende details, zoals het beleidstype, het aantal overeenkomende items en de ernst die wordt beoordeeld op uw beleidsinstellingen. Onder het **tabblad** Inhoud kunt u de bestanden bekijken die betrokken zijn bij deze waarschuwing. Deze informatie kan extra inzicht geven in de specifieke gebeurtenis die de waarschuwing heeft geactiveerd, waar de bestanden zich bevinden en welke typen persoonlijke gegevens hierbij betrokken zijn. Triggers voor waarschuwingen worden bepaald door de specifieke voorwaarden van elk beleid. Er kan bijvoorbeeld een waarschuwing worden geactiveerd bij een beleid voor gegevensoverdracht als privacybeheer een overdracht detecteert tussen de opgegeven afdelingen of regio's van het beleid.

Nadat u een waarschuwing in de lijst hebt beoordeeld, kunt u de actie Probleem **maken** gebruiken om nader onderzoek en actie te vragen. U wordt gevraagd het probleem een naam te geven en relevante opmerkingen toe te voegen voor context. U kunt hier ook waarschuwingen afwijzen als ze geen opvolging nodig hebben.

### <a name="issues"></a>Problemen

Zoals wordt beschreven in de sectie Waarschuwingen, worden er problemen gemaakt tijdens het beoordelen van waarschuwingen over beleidswedstrijden. Ga naar de pagina Problemen om de aangegeven problemen op te volgen en op te lossen. Hier kunt u afzonderlijke problemen bekijken, de aanstichtende voorwaarden onderzoeken, de gegevens controleren en de benodigde stappen ondernemen om de zaak te sluiten.

Op deze pagina vindt u een lijst met alle geopende problemen. Problemen worden vermeld op naam en gesorteerd op ernst, om u te helpen prioriteit te geven aan zaken, zoals hoge, gemiddelde en lage categorieën, samen met niet-toegewezen. Selecteer een probleem in de lijst om de inhoud te bekijken en actie te ondernemen om dit op te lossen. U kunt tijdens de beoordeling niet-toegewezen problemen een ernstbeoordeling geven.

#### <a name="issue-overview"></a>Overzicht van probleem

Pagina's met probleemdetails helpen u bij het oplossen van de geïdentificeerde privacyrisico's en het correct afhandelen van de aangegeven bestanden. Op het **tabblad** Overzicht ziet u de huidige stap die u moet uitvoeren, met de status van het probleem en de volgende aanbevolen acties. U kunt ook essentiële informatie bekijken over de betrokken inhoud, het bijbehorende beleid, details over de waarschuwing en de tijdlijn.

De volgende tabbladen bevatten meer informatie over de bijbehorende waarschuwingen en inhoud, samen met eventuele notities van anderen in uw team die aan het probleem werken. U kunt de lijst met actieve medewerkers beheren via **het tabblad Collaborateurs.**

#### <a name="share-the-issue"></a>Het probleem delen

Als u personen toevoegt als collaborateurs, kunt u het probleem delen met extra leden van uw bedrijf via een beveiligd Microsoft Teams-kanaal, bedrijfs-e-mail of door een koppeling rechtstreeks te delen naar de pagina van het probleem in privacybeheer. Deze opties zijn beschikbaar onder de **knop** Delen. Wanneer u via Teams deelt, wordt u gevraagd uit de beschikbare teams in uw organisatie te selecteren, het specifieke kanaal te selecteren en een bericht over het probleem achter te laten, dat wordt gedeeld met het opgegeven kanaal.

#### <a name="review-content-and-remediate"></a>Inhoud bekijken en herstellen

Als u de inhoud wilt bekijken die aan een probleem is gekoppeld, kiest u de actie Inhoud **controleren** als u daarom wordt gevraagd of het tabblad Inhoud opent. Selecteer een bestand in de lijst om het volledig weer te geven. Hier ziet u details over het bestand, alle activiteiten die zijn opgenomen en de herstelgeschiedenis ervan, als er eerdere stappen zijn ondernomen om dit bestand te beheren.

Gebruik de **knop Herstel om** uw eigen beslissingen te nemen voor het verwerken van gegevens voor deze inhoud. Als u de knop selecteert, kunt u kiezen uit een of meer herstelacties. Opties zijn:

**Alle beleidsregels**

- **Melding:** Informeer de eigenaar van de inhoud over het gedetecteerde probleem.
- **Bewaarlabel toepassen:** Voeg een label toe over het bewaren van gegevens voor dit item. 
- **Gevoeligheidslabel toepassen:** Voeg een label toe over de gevoeligheid van de gegevens van dit item.
- **Markeren als geen overeenkomst:** identificeer een zoekresultaat als een onwaar positief om het inhoudsitem uit overweging te verwijderen.

**Gegevensminimation**

- **Prullenbak/verwijderen:** Gebruik deze optie voor een zachte verwijdering van de gegevens. Inhoud wordt verplaatst naar de map met verwijderde items of de prullenbak (Exchange, SharePoint, OneDrive) of verwijderd met een optie om te herstellen (Teams berichten). Verwijdering kan binnen een bepaalde periode worden teruggedraaid, afhankelijk van de instellingen van de service.

**Gegevens overbelichting en gegevensoverdracht**

- **Delen verwijderen:** stop met het delen van een koppeling naar dit inhoudsitem.

Bij elke optie wordt u gevraagd opmerkingen en eventuele andere benodigde ondersteunende informatie voor de eigenaar van de inhoud achter te laten voordat u uw keuze bevestigt.

Nadat alle herstelstappen zijn ondernomen en het probleem kan worden gesloten, gebruikt u de knop Oplossen en voegt u uw laatste opmerkingen toe voordat u het probleem indient.

## <a name="delete-a-policy"></a>Een beleid verwijderen

Als u een bestaand privacybeleid wilt verwijderen, vindt u het in de lijst op de pagina Beleid, selecteert u het actiemenu (verticale beletsellijnen) en kiest u de actie Beleid verwijderen. U wordt gevraagd uw keuze te bevestigen voordat het verwijderen definitief is en het beleid definitief wordt verwijderd. Het verwijderen van een beleid heeft geen invloed op bestanden die eerder door het beleid zijn geëvalueerd en problemen en waarschuwingen die door het beleid worden gegenereerd, blijven bestaan.
