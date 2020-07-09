---
title: Schadelijke e-mail herstellen die is geleverd in Office 365
author: MSFTTracyP
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
description: Bedreigingssanering
appliesto:
- Microsoft Threat Protection
ms.openlocfilehash: eb86c0b8e5368a42daa1002de5ac361613037090
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086689"
---
# <a name="remediate-malicious-email-that-was-delivered-in-office-365"></a>Schadelijke e-mail herstellen die is geleverd in Office 365

Sanering betekent het nemen van een verboden actie tegen een bedreiging. Schadelijke e-mails die naar uw organisatie worden verzonden, kunnen worden opgeschoond door het systeem, via ZAP (Zero-hour Auto-Purge) of door de beveiligingsteams door middel van herstelacties zoals verplaatsen naar inbox, verplaatsen naar ongewenste e-mail, verplaatsen naar de map verwijderde items, soft delete of hard delete. Office Advanced Threat Protection (Office ATP) P2 / E5 biedt beveiligingsteams de mogelijkheid om bedreigingen in e-mails en samenwerkingsproblemen te bemiddelen door middel van handmatige jacht en geautomatiseerde onderzoeken.

> [!NOTE]
> Als beveiligingsteams e-mails kunnen herstellen, moeten ze de zoek- en zuiveringsrol aan hen hebben toegewezen. Roltoewijzing gebeurt via machtigingen in het beveiligings- en compliancecentrum. <p>

## <a name="what-you-need-to-know-before-you-begin"></a>Wat u moet weten voordat u begint

Als u bepaalde acties wilt uitvoeren, zoals het bekijken van berichtkoppen of het downloaden van inhoud van e-mailberichten, moet u een nieuwe rol met de naam *Voorbeeld* hebben toegevoegd aan een andere geschikte rolgroep. In de volgende tabel worden vereiste rollen en machtigingen verduidelijkt.

|Activiteit  |Rolgroep |Voorbeeld rol nodig?  |
|---------|---------|---------|
|Threat Explorer (en realtime detecties) gebruiken om bedreigingen te analyseren     |Globale beheerder <br> Beveiligingsbeheerder <br> Beveiligingslezer     | Nee   |
|Gebruik Threat Explorer (en realtime detecties) om kopteksten voor e-mailberichten weer te geven en e-mailberichten in quarantaine te bekijken en te downloaden    |Globale beheerder <br> Beveiligingsbeheerder <br>Beveiligingslezer   |       Nee  |
|Threat Explorer gebruiken om kopteksten weer te geven en e-mailberichten te downloaden die aan postvakken worden bezorgd     |Globale beheerder <br>Beveiligingsbeheerder <br> Beveiligingslezer <br> Voorbeeld   |   Ja      |

> [!NOTE]
> *Voorbeeld* is een rol en geen rolgroep; de voorbeeldrol moet worden toegevoegd aan een bestaande rolgroep voor Office 365. De rol Global Administrator krijgt het Microsoft 365-beheercentrum [https://admin.microsoft.com](https://admin.microsoft.com) toegewezen en de rollen Beveiligingsbeheerder en beveiligingslezer worden toegewezen in het Security & Compliance Center ( [https://protection.office.com](https://protection.office.com) ). Zie [Machtigingen in het Security & Compliance Center voor](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center?view=o365-worldwide) meer informatie over rollen en machtigingen.

> [!NOTE]
> Beheerders kunnen vereiste acties uitvoeren op e-mails, maar om hun actie goedgekeurd te krijgen, moeten ze de rol 'Zoeken en zuiveren' aan hen hebben toegewezen via > machtigingen voor beveiliging en nalevingscentrum.

## <a name="manual-and-automated-remediation"></a>Handmatige en geautomatiseerde sanering

**Handmatige jacht** vindt plaats wanneer beveiligingsteams bedreigingen handmatig identificeren, met behulp van de zoek- en filtermogelijkheden in Threat Explorer. Handmatige herstel op e-mails kan worden geactiveerd via elke e-mailweergave (Malware, Phish of Alle e-mail) na het vinden van een set e-mails die moeten worden gesaneerd.

![Handmatige jacht in Office 365 Threat Explorer op datum.](../../../media/tp-RemediationArticle1.png "Bedreigingsverkenner")

De selectie van e-mails kan op meerdere manieren worden gedaan via Threat Explorer:

1. E-mails met de hand kiezen: dit betekent dat beveiligingsteams filters kunnen gebruiken in respectievelijke weergaven en een paar e-mails van Threat Explorer kunnen selecteren die moeten worden gesaneerd. De bovengrens voor het selecteren van e-mails is honderd (100). Beveiligingsteams kunnen niet meer dan honderd e-mails handmatig kiezen.

2. Queryselectie: Beveiligingsteams kunnen een hele query selecteren met de bovenste knop 'Alles selecteren'. Dezelfde query wordt ook weergegeven in de gegevens van de e-mailinzending van het actiecentrum.

3. Queryselectie met uitsluiting: er kunnen momenten zijn waarop beveiligingsteams besluiten e-mails te herstellen door zowel een hele query te selecteren als een paar e-mails handmatig uit de query uit te sluiten. Om dit te doen, kan een beheerder het selectievakje 'Alles selecteren' gebruiken en omlaag scrollen om een paar e-mails handmatig uit te sluiten. Het maximum aantal e-mails dat de query kan bevatten is duizend (1.000) en het maximum aantal uitsluitingen is honderd (100), in dit geval.

Zodra e-mails zijn geselecteerd uit Threat Explorer, kan het herstellen van herstel beginnen met het nemen van directe actie, of door e-mails in de rij te zetten voor een actie:

1. Directe goedkeuring: Wanneer acties zoals 'Verplaatsen naar inbox', 'Verplaatsen naar ongewenste items', 'Verplaatsen naar verwijderde items', 'Soft delete', 'Hard delete' worden geselecteerd door beveiligingspersoneel met de juiste machtigingen en de volgende stappen worden gevolgd tot het herstellen van herstel, begint het herstelproces een geselecteerde actie uit te voeren. Een tijdelijke flyout toont herstel in uitvoering.

2. Goedkeuring in twee stappen: 'Toevoegen aan herstel' actie kan worden ondernomen door een beheerder die niet over de juiste machtigingen beschikt of die langer moet wachten om de actie uit te voeren. In dit geval wordt de herstelactie niet rechtstreeks uitgevoerd. In plaats daarvan worden e-mails toegevoegd aan een herstelcontainer die moet worden goedgekeurd om uit te voeren. Totdat de sanering is goedgekeurd, wordt de e-mail niet gesaneerd. Zodra de sanering is goedgekeurd, zullen er acties worden ondernomen op de e-mail.

**Geautomatiseerde air-acties (investigation and response)** worden geactiveerd door waarschuwingen of door beveiligingsteams van binnen Threat Explorer. Ze kunnen een aantal aanbevolen bemiddeling bevatten die moet worden goedgekeurd door beveiligingsteams. Deze herstelacties zijn opgenomen op het tabblad Actie in het geautomatiseerde onderzoek.  

:::image type="content" source="../../../media/tp-RemediationArticle3.png" alt-text="E-mail met malware is Zapped pagina met de tijd van Zap uitvoering.":::

Alle bemiddeling (ofwel directe goedkeuring of goedkeuring in twee stappen) die is gemaakt via Threat Explorer en goedgekeurde acties afkomstig van geautomatiseerde onderzoeken, worden weergegeven in het Onderhoudscentrum, dat toegankelijk is via de linkernavigatie onder *Review* >  **Action Center**.

:::image type="content" source="../../../media/tp-RemediationArticle4.png" alt-text="Het actiecentrum met een lijst met bedreigingen op datum en ernst.":::

In het Onderhoudscentrum worden alle herstelacties van de afgelopen 30 dagen weergegeven. Acties die via Explorer worden uitgevoerd, worden weergegeven met dezelfde naam die door de beveiligingsteams is opgegeven toen de herstelbewerking is gemaakt. Acties die worden ondernomen door middel van geautomatiseerde onderzoeken worden opgedoken met titels die beginnen met de bijbehorende waarschuwing die het onderzoek heeft geactiveerd - bijvoorbeeld "Zap-e-mailcluster...".

Elk herstelitem kan worden geopend om details erover te bekijken. Wanneer een herstelitem wordt geopend, worden basishersteldetails, de herstelnaam, de aanmaakdatum, beschrijving, ernst van de bedreiging en de status weergegeven. Het toont ook twee tabbladen. 

1. **Tabblad E-mailinzending**: Dit zijn het aantal e-mails dat via Threat Explorer is verzonden of geautomatiseerde onderzoeken die moeten worden verholpen. Deze e-mails kunnen zijn:

**Actie:** E-mails in de volgende locaties van cloudpostvak kunnen worden uitgevoerd en verplaatst, d.w.z. elke e-mail binnen de herstelbare categorie kan van de ene locatie naar de andere worden verplaatst:
  - Inbox 
  - Ongewenste e-mail  
  - Verwijderde map
  - Zachte verwijderde map

>[!NOTE]
> Momenteel kan alleen een eindgebruiker met toegang tot het postvak items herstellen uit een zachte verwijdermap.

**Niet bruikbaar**: E-mails op de volgende locaties kunnen niet worden uitgevoerd of verplaatst als onderdeel van de e-mailacties, d.w.z. e-mails in niet-herstelbare categorie kunnen niet worden verplaatst in de niet-herstelbare categorie, noch in herstelbaar. Niet-herstelbare locaties zijn:

  - Quarantaine
  - Moeilijk verwijderde map
  - On-prem / extern
  - Mislukt / gedropt
  
Verdachte verzonden berichten worden gecategoriseerd als herstelbaar of niet-herstelbaar. In de meeste gevallen moeten herstelbare en niet-herstelbare berichten oplopen tot het totale aantal verzonden berichten. Er kunnen echter zeldzame gevallen zijn waarin verzonden berichten mogelijk niet optellen tot de som van herstelbare en niet-herstelbare items en hoger of lager kunnen zijn dan het totale aantal verzonden berichten. Dit kan gebeuren als gevolg van systeemvertragingen, time-outs of verlopen berichten. Berichten verlopen op basis van de bewaartermijn van Explorer voor uw organisatie.

Tenzij u oude berichten na de explorer-bewaarperiode van uw organisatie herstelt, is het raadzaam om items opnieuw te herstellen als u inconsistenties in aantallen ziet. Voor systeemvertragingen worden herstelupdates doorgaans binnen een paar uur vernieuwd.

Als de bewaartermijn van uw organisatie voor e-mail in Explorer 30 dagen bedraagt en u e-mails resproseert die 29-30 dagen terug gaan, telt het aantal e-mailinzenting mogelijk niet altijd op omdat de e-mails al uit de bewaarperiode zijn verhuis.

Als bemiddeling een tijdje vastzit in een status 'Aan de gang', is dit waarschijnlijk te wijten aan systeemvertragingen. Het kan tot een paar uur duren om te saneren. Er kan een variatie worden waargenomen in het indienen van e-mail telt als sommige van de e-mails waren geen onderdeel van de query tijdens het starten van de sanering, als gevolg van vertragingen in het systeem. Het is een goed idee om in dergelijke gevallen opnieuw te proberen te herstellen.  

Voor de beste resultaten, sanering moet worden gedaan in kleinere partijen van ongeveer 50k of minder e-mails.  

Van alle e-mails in e-mail indiening, herstelbare e-mails zijn de enigen die zal worden gehandeld op tijdens de sanering. Niet-herstelbare e-mails kunnen niet worden gesaneerd door het Office 365-e-mailsysteem, omdat ze niet in cloudpostvakken worden opgeslagen.

Voor e-mails die in quarantaine worden gevonden, kunnen beheerders naar quarantaine gaan om acties te ondernemen op die e-mails indien nodig, maar de e-mails verlopen uit quarantaine als ze niet handmatig worden verwijderd. E-mails die in quarantaine zijn geplaatst vanwege schadelijke inhoud, zijn niet toegankelijk voor eindgebruikers, dus beveiligingspersoneel hoeft geen specifieke actie te ondernemen om de dreiging in quarantaine te verwijderen. Als de e-mails zijn on-prem of extern, kan de eindgebruiker worden gecontacteerd om de verdachte e-mail aan te pakken of aparte e-mailserver / beveiligingstools te gebruiken voor verwijdering. Deze e-mails kunnen worden geïdentificeerd door het toepassen van leveringslocatie = on-prem / extern filter in Threat Explorer. Voor mislukte of verwijderde e-mail of e-mail die niet toegankelijk is voor de eindgebruiker, mag er geen e-mail zijn om te beperken, omdat ze het postvak niet bereiken.

Dit is hoe een inzending wordt weergegeven in het Onderhoudscentrum. Een herstel kan meerdere inzendingen bevatten. Als meerdere acties worden goedgekeurd via één geautomatiseerd onderzoek, wordt elke e-mail- of e-mailclusteractie weergegeven in dezelfde herstel als een andere inzending.

:::image type="content" source="../../../media/tp-RemediationArticle6.png" alt-text="Zap e-mail cluster fly-out paneel.":::

Als u op een item voor het indienen van e-mail klikt, worden details van die herstel weergegeven, zoals de query (wanneer herstel wordt geactiveerd door middel van geautomatiseerde onderzoeken of Threat Explorer door het selecteren van een query), begintijd en eindtijd van herstel. Er wordt ook een lijst weergegeven met berichten die zijn ingediend voor herstel. Als berichten uit de bewaarperiode van Explorer verdwijnen, verdwijnen de berichten uit deze lijst. In deze lijst worden ook afzonderlijke berichten uit de lijst weergegeven die opnieuw kunnen worden hersteld.

2. **Tabblad Actielogboeken**: op dit tabblad wordt het resultaat weergegeven van berichten die zijn verholpen, inclusief details zoals de goedgekeurde datum, de goedkeurder (beheerder die de actie heeft goedgekeurd), actie, status en tellingen.  

Status is de algemene status van de sanering. Status kan zijn:

  - **Gestart**: Wanneer een herstel wordt geactiveerd.
  - **In de wachtrij**: Wanneer de herstelwerkzaamheden in de wachtrij staan voor het beperken van e-mails.
  - **In uitvoering**: Wanneer de mitigatie aan de gang is.
  - **Voltooid**: Wanneer de mitigatie op alle herstelbare e-mails met succes of met een aantal fouten wordt gedaan. 
  - **Mislukt:** wanneer er geen herstelwerkzaamheden zijn geslaagd.

Omdat alleen herstelbare e-mails kunnen worden uitgevoerd, wordt de opruiming van elke e-mail als succesvol of mislukt beschouwd. Uit de totale herstelbare e-mails, leggen we de succesvolle en mislukte mitigaties bloot.

  - **Succes**: Wanneer de gewenste actie op herstelbare e-mails is bereikt en overeenkomt met de bedoeling van admin. Bijvoorbeeld: Een beheerder wil e-mails uit postvakken verwijderen, zodat ze de actie ondernemen om e-mails te verwijderen. Als een herstelbare e-mail niet in de oorspronkelijke map wordt gevonden nadat de actie is ondernomen, wordt de status als succesvol weergegeven.  

  - **Mislukt:** Wanneer de gewenste actie op herstelbare e-mails mislukt. Bijvoorbeeld: Een beheerder wil e-mails uit mailboxen verwijderen, dus hij neemt de actie van het verwijderen van e-mails. Als er nog steeds een herstelbare e-mail in het postvak wordt gevonden, wordt status weergegeven als mislukt.

Als u op een item in actielogboek klikt, worden de details van de sanering weergegeven. Voor succesvolle items, als de details zeggen, succesvol of niet gevonden in het postvak, betekent dit dat item al is verwijderd uit het postvak. Soms zijn er storingen die optreden als gevolg van een systemische fout tijdens de sanering, en in die gevallen is het een goed idee om opnieuw te proberen sanering.  

Herstel is een krachtig hulpmiddel om bedreigingen te beperken en verdachte e-mails aan te pakken. Het helpt een organisatie veilig te houden.  

## <a name="more-info"></a>Meer informatie

Zie<https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered?view=o365-worldwide>