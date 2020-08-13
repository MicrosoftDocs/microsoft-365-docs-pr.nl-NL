---
title: Schadelijke e-mail herstellen die is bezorgd in Office 365
author: msfttracyp
ms.author: tracyp
manager: dansimp
ms.topic: article
ms.service: Microsoft Threat Protection
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection: ''
search.appverid: MET150
description: Bedreiging voor herbemiddeling
appliesto:
- Microsoft Threat Protection
ms.openlocfilehash: 9ffa3f71dafec4728294b17530ae1f9490d480da
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656681"
---
# <a name="remediate-malicious-email-that-was-delivered-in-office-365"></a>Schadelijke e-mail herstellen die is bezorgd in Office 365

Herstel middelen houdt de mogelijkheid een actie te ondernemen tegen een bedreiging. Kwaadwillende e-mailberichten die naar uw organisatie worden verzonden, kunnen worden opgeschoond door het systeem, via ZAP (automatische opschoning van nul uur), of door de beveiligings teams via herstel activiteiten, zoals verplaatsen naar Postvak in, verplaatsen naar ongewenste e-mail, verplaatsen naar de map Verwijderde items, zacht verwijderen of permanent verwijderen. Office Advanced Threat Protection (Office ATP) P2/E5 biedt beveiligingsactiviteiten teams waarmee de Risico's van e-mailberichten en samenwerkingsproblemen kunnen worden opgelost via handmatig jacht en geautomatiseerde onderzoek.

> [!NOTE]
> Als u wilt dat beveiligings teams een e-mailbericht willen herstellen, moeten ze de rol zoeken en wissen toewijzen. Roltoewijzing wordt uitgevoerd via machtigingen in beveiliging en compliance Center.

## <a name="what-you-need-to-know-before-you-begin"></a>Wat u moet weten voordat u begint

Als u bepaalde acties wilt uitvoeren, zoals het weergeven van berichtkoppen of het downloaden van e-mailberichten, moet u een nieuwe rol genaamd *voorbeeld* toevoegen aan een andere bijbehorende rollen groep. In de volgende tabel worden vereiste rollen en machtigingen duidelijker.

****

|Activiteit|Rollen groep|Is de functie voorbeeld nodig?|
|---|---|---|
|Het gebruik van bedreigings Verkenner (en real-time detecties) om bedreigingen te analyseren |Globale beheerder <br> Beveiligingsbeheerder <br> Beveiligings lezer|Nee|
|De weergave van bedreigings Verkenner (en realtime-detectie) gebruiken om kopteksten voor e-mailberichten weer te geven en voorbeelden van e-mailberichten in quarantaine te downloaden|Globale beheerder <br> Beveiligingsbeheerder <br>Beveiligings lezer|Nee|
|Met behulp van de bedreigings Verkenner kopteksten en e-mailberichten die zijn bezorgd bij postvakken weergeven|Globale beheerder <br>Beveiligingsbeheerder <br> Beveiligings lezer <br> Voorbeeld|Ja|
|

> [!NOTE]
> *Voorbeeld* is een rol en geen rollen groep. de rol van voorbeeld moet worden toegevoegd aan een bestaande rollen groep voor Office 365. De rol van de globale beheerder wordt het Microsoft 365-Beheercentrum toegewezen [https://admin.microsoft.com](https://admin.microsoft.com) , en de rollen Beveiligingsbeheerder en beveiligings lezer worden toegewezen in het beveiligings & nalevings centrum ( [https://protection.office.com](https://protection.office.com) ). Als u meer wilt weten over rollen en machtigingen, raadpleegt u [machtigingen in de sectie beveiliging & nalevings centrum](permissions-in-the-security-and-compliance-center.md).

> [!NOTE]
> Beheerders kunnen de juiste actie ondernemen voor e-mailberichten maar de actie hiervan is goedgekeurd, en de rol ' zoeken en verwijderen ' is toegewezen via beveiliging en compliance Center > machtigingen.

## <a name="manual-and-automated-remediation"></a>Handmatige en geautomatiseerde herstel

**Handmatige jacht** vindt plaats wanneer beveiligings teams handmatig hun bedreigingen identificeren met behulp van de functies voor zoeken en filteren in de bedreigings Verkenner. Handmatig herstel van e-mailberichten kan worden geactiveerd via een e-mail weergave (malware, phishing of alle e-mail) nadat u een reeks e-mailberichten hebt gevonden die moeten worden hersteld.

[Handmatige jacht in Office 365 Threat Explorer op datum.](../../media/tp-RemediationArticle1.png)

De selectie van e-mailberichten kan op verschillende manieren worden gedaan via de Threat Explorer:

1. Handmatig een e-mailbericht kiezen: Dit betekent dat beveiligingsactiviteiten met filters in de desbetreffende weergaven kunnen worden gebruikt en selecteer een aantal e-mailberichten van de bedreigings Verkenner die u wilt herstellen. De maximumlimiet voor het selecteren van e-mailberichten is 100 (100). Beveiligingsactiviteiten teams kunnen niet meer dan honderd e-mailberichten kiezen.

2. Query selectie: beveiligingsactiviteiten teams kunnen een hele query selecteren met behulp van de ' knop Alles selecteren '. De query wordt ook weergegeven in het Actiecentrum.

3. Query selectie met uitsluiting: er zijn situaties mogelijk waarin beveiligingsactiviteiten teams besluiten e-mail te herstellen door zowel een gehele query te selecteren als een paar e-mailberichten van de query uit te sluiten. Daarom kan een beheerder het selectievakje Alles selecteren gebruiken en omlaag schuiven om enkele e-mailberichten uit te sluiten. Het maximale aantal e-mailberichten van de query is 1000 (1.000) en het maximale aantal uitsluitingen is 100 (100), in dit geval.

Nadat u e-mailberichten hebt geselecteerd in de bedreigings Verkenner, kan het maken van een herstelbewerking plaatsvinden door direct actie te ondernemen, of door e-mailberichten in de wachtrij te plaatsen.

1. Rechtstreeks goedkeuren: wanneer acties zoals ' verplaatsen naar Postvak in ', ' naar ongewenste e-mail ' gaan ', ' naar verwijderde items ', ' naar verwijderde items ', ' hard delete ', ' hard delete ' en de volgende stappen worden uitgevoerd met de juiste machtigingen, begint het herstelproces om een geselecteerde actie uit te voeren. Een tijdelijke flyout toont een herstelbewerking.

2. Goedkeuring in twee stappen: ' toevoegen aan herstelactie ' kan worden uitgevoerd door een beheerder die niet de juiste machtigingen heeft of dat de actie langer moet wachten om de actie uit te voeren. In dit geval wordt de actie herstel niet rechtstreeks uitgevoerd. In plaats daarvan worden e-mailberichten toegevoegd aan een herstel container die moet worden goedgekeurd voor uitvoering. Het e-mailbericht kan niet worden hersteld. Wanneer het herstel is goedgekeurd, worden de acties in het e-mailbericht opgenomen.

**Geautomatiseerd onderzoek en antwoord acties (lucht)** worden geactiveerd door waarschuwingen of via beveiligings bewerkings teams vanuit de bedreigings Verkenner. Mogelijk zijn er mogelijk aanbevolen herstelbewerkingen die moeten worden goedgekeurd door beveiligingsactiviteiten teams. Deze herstelacties worden opgenomen op het tabblad actie binnen het geautomatiseerde onderzoek.

[E-mail met malware is zapped pagina met de tijd van zap-uitvoering.](../../media/tp-RemediationArticle3.png)

Alle herstelbewerkingen (directe goedkeuring of goedkeuring van twee stappen) die zijn gemaakt via de bedreigings Verkenner, en goedgekeurde acties die afkomstig zijn van geautomatiseerde tests, worden weergegeven in het Onderhoudscentrum, die toegankelijk zijn via het linkernavigatievenster onder * controleren * > **Actiecentrum**.

[Het Actiecentrum met een lijst met bedreigingen op datum en ernst.](../../media/tp-RemediationArticle4.png)

In het Actiecentrum worden alle herstelacties voor de afgelopen 30 dagen weergegeven. Acties die u hebt uitgevoerd via Explorer, worden weergegeven met dezelfde naam als de teams van beveiligingsbewerkingen wanneer de herstelbewerking is voltooid. Acties die via geautomatiseerde onderzoek worden verricht, worden geopper gezet met titels die beginnen met de gerelateerde melding die het onderzoek heeft geactiveerd, bijvoorbeeld ' ZAP-e-mail cluster... '.

U kunt elk herstelitem openen om de details ervan weer te geven. Wanneer een herstelitem wordt geopend, bevat dit de basis Details voor herbemiddeling, de naam voor herbemiddeling, de aanmaakdatum, de beschrijving, de ernst van de bedreiging en de status. Er worden ook twee tabbladen weergegeven.

1. **Tabblad e-mail verzenden**: dit is het aantal e-mailberichten dat u hebt ontvangen via de Threat Explorer of de geautomatiseerde onderzoeken die u wilt herstellen. Deze e-mailberichten kunnen worden:

   [Het Actiecentrum met een actie en geen bedreigingen.](../../media/tp-RemediationArticle5.png)

   - **Actie**: e-mailberichten in de volgende locaties in het postvak van de Cloud kunnen op basis van de locatie van de inhoud van de cloud worden gewijzigd en verplaatst naar een andere locatie:

     - Postvak in
     - Ongewenste e-mail
     - Map verwijderd
     - Map met verwijderde tijdelijke bestanden

     [!NOTE]
     > Op dit moment kan alleen eindgebruikers van toegang tot het postvak items herstellen uit een tijdelijke map verwijderen.

   - **Niet-actioneel**: e-mailberichten op de volgende locaties kunnen niet worden gewijzigd of verplaatst als onderdeel van de e-mail acties, dat wil zeggen dat e-mailberichten in een niet-herstelbare categorie niet kunnen worden verwijderd in de categorie niet-herstelbaar, noch in herstelbare. Niet-herstelbaar locaties zijn:

     - Quarantaine
     - Map voor permanent verwijderen
     - On-premises/extern
     - Mislukt/neergezet

   Verdachte berichten verzonden worden gecategoriseerd als onherstelbaar of niet-herstelbaar. In de meeste gevallen, herstelbaar en niet-herstelbaar berichten, moeten de totale verzonden berichten worden opgeteld. Het kan zijn dat berichten die zijn ingediend, vaak niet konden worden toegevoegd aan de som van herstelbaar en niet-herstelbare items en mogelijk hoger of lager is dan het totale aantal verzonden berichten. Dit kan gebeuren vanwege systeem vertragingen, time-outs of verlopen berichten. Berichten verlopen op basis van de bewaarperiode van Explorer voor uw organisatie.

   U wordt aangeraden items opnieuw te herstellen als u oude berichten terugkeert na de bewaarperiode van uw organisatie, als u inconsistenties ziet. Herstel updates worden in enkele uren meestal vernieuwd voor vertragingen van het systeem.

   Als de bewaarperiode voor e-mailberichten in Explorer 30 dagen duurt en u e-mailberichten terugkeert naar 29-30 dagen, worden de verzendings punten voor e-mail mogelijk niet altijd opgeteld omdat de e-mailberichten al zijn verzonden.

   Als herstel na een tijdje een tijdje uitvalt, is dit waarschijnlijk vanwege een systeem vertraging. Het kan een paar uur duren voordat het probleem is verholpen. U kunt een variant in de lijst met e-mail verzendingen van e-mailberichten ontvangen omdat sommige e-mailberichten geen deel uitmaken van de query tijdens het starten van herstel, vanwege systeem vertragingen. Het is een goed idee om in dergelijke gevallen opnieuw te proberen.

   Voor de beste resultaten moet herbemiddeling in kleinere batches van rondom 50k of minder e-mailberichten plaatsvinden.

   Bij alle e-mailberichten die worden verzonden, zijn herstelbare e-mailberichten de enige die tijdens het herstel worden uitgevoerd. Niet-herstelbare e-mailberichten kunnen niet worden doorgevoerd in het Office 365-e-mailsysteem, aangezien deze niet zijn opgeslagen in Cloud postvakken.

   Voor e-mailberichten die zijn gevonden in Quarantine, kunnen beheerders naar Quarantine gaan om indien nodig een actie uit te voeren voor deze e-mailberichten. E-mailberichten die zijn gequarantine vanwege kwaadaardige inhoud zijn niet toegankelijk voor eindgebruikers en daarom moeten beveiligingspersoneel geen specifieke actie ondernemen om de bedreiging in quarantaine te halen. Als het e-mailbericht on-premises of extern is, kan de eindgebruiker contact met u opnemen om het verdachte e-mailadres of afzonderlijke e-mailserver/beveiligingshulpprogramma's voor verwijdering te gebruiken. Deze e-mailberichten kunnen worden geïdentificeerd door bezorgingslocatie toe te passen = on-premises/extern filter in de bedreigings Verkenner. Voor mislukte of genegeerde e-mailberichten of e-mailberichten die niet toegankelijk zijn voor de eindgebruiker, mag u geen e-mail meer ontvangen, omdat ze het postvak niet bereiken.

   Zo wordt een ingediend in het Actiecentrum. Een herstel kan meerdere inzendingen bevatten. Wanneer meerdere acties worden goedgekeurd via één automatisch onderzoek, worden elke actie van het e-mailbericht of e-mail cluster in dezelfde herstelactie weergegeven als een andere verzending.

   [Deelvenster van flyout voor e-mail cluster van ZAP.](../../media/tp-RemediationArticle6.png)

   Als u op een verzendings item voor een e-mail klikt, worden details van die herstelfunctie weergegeven, zoals de query (wanneer herstel wordt geactiveerd via geautomatiseerde onderzoeken of de bedreigings Verkenner via een query), begintijd en eindtijd, van herstel. Ook wordt een lijst weergegeven met berichten die zijn ingediend voor herstel. Wanneer berichten vanuit de bewaarperiode van de Explorer worden verplaatst, verdwijnen de berichten uit deze lijst. In deze lijst ziet u ook afzonderlijke berichten van de lijst die kunnen worden hersteld.

2. **Tabblad Actielogboek**: dit tabblad bevat het resultaat van het verholpen berichten, waaronder details zoals goedgekeurde datum, goedkeurder (beheerder die de actie heeft goedgekeurd), actie, status en aantal.

   Status is de algemene status van het herstel. Status kan zijn:

     - Aan de **slag**: wanneer een herstelactie wordt geactiveerd.
     - **In de wachtrij geplaatst**: wanneer het herstel in de wachtrij staat voor het beperken van e-mailberichten.
     - Wordt **uitgevoerd**: wanneer de beperking wordt uitgevoerd.
     - **Voltooid**: wanneer de beperking voor alle herstelbare e-mailberichten succesvol is of met een aantal storingen.
     - **Mislukt**: als er geen herstelpogingen succesvol zijn.

   Wanneer alleen herstelbare e-mailberichten kunnen worden vastgelegd, wordt de opschoning van elk e-mailbericht al gelukt of mislukt. Tegen het totale aantal oplossbare e-mailberichten geven we de succesvolle en mislukte beperkingen.

   - **Succes**: wanneer de gewenste actie op het herstelbare e-mailberichten wordt uitgevoerd en de intentie van de beheerder overeenstemt. Een beheerder wil bijvoorbeeld e-mailberichten uit postvakken verwijderen zodat ze de actie ondernemen voor het verwijderen van e-mailberichten. Als na het uitvoeren van de actie een herstelbaar e-mailadres niet in de oorspronkelijke map wordt gevonden, wordt de status weergegeven als voltooid.

   - **Fout**: als de gewenste handeling voor herstelbare e-mailberichten mislukt. Een beheerder wil bijvoorbeeld e-mailberichten verwijderen uit postvakken, zodat hij of zij de actie ondernemen voor het verwijderen van e-mailberichten. Als er nog steeds herstelbaar e-mailbericht in het postvak wordt gevonden, wordt de status weergegeven als mislukt.

   Als u op een item in het Actielogboek klikt, worden details van herstel weergegeven. Voor succesvolle items: als de details gezegd, geslaagd of niet vinden in Postvak, betekent dit dat het item al uit het postvak is verwijderd. Soms treden er fouten op als gevolg van een systeemfout tijdens het herstel, en in deze gevallen is het verstandig om opnieuw te proberen herstel te doen.

   Herstel is een krachtig hulpmiddel om bedreigingen te beperken en verdachte e-mailberichten te verhelpen. Een organisatie helpt een organisatie veilig en veilig te houden.

## <a name="more-info"></a>Meer informatie

Zie [kwaadaardige E-mail onderzoeken](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered?view=o365-worldwide)
