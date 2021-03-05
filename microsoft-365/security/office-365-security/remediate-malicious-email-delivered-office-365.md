---
title: Schadelijke e-mail herstellen die is bezorgd in Office 365
author: msfttracyp
ms.author: tracyp
manager: dansimp
ms.topic: article
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection: ''
search.appverid: MET150
description: Bedreigingsremediatie
appliesto:
- Microsoft 365 Defender
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6c5c94ce3994424a6d4b6f4a4ac587f5cc5e33ca
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454695"
---
# <a name="remediate-malicious-email-delivered-in-office-365"></a>Schadelijke e-mail herstellen die wordt bezorgd in Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)

Herstel betekent het nemen van een voorgeschreven actie tegen een bedreiging. Schadelijke e-mailberichten die naar uw organisatie worden verzonden, kunnen door het systeem worden opgeschoond via ZAP (Zero-Hour Auto Purge) of door beveiligingsteams via herstelacties zoals verplaatsen naar Postvak *IN,* verplaatsen naar ongewenste e-mail, verplaatsen naar verwijderde *items,* soft *delete* of hard *delete.* Met Microsoft Defender voor Office 365 P2/E5 kunnen beveiligingsteams bedreigingen in e-mail- en samenwerkingsfunctionaliteit herstellen via handmatig en geautomatiseerd onderzoek.

> [!NOTE]
> Om schadelijke e-mail te herstellen, moeten de zoek- en *herstelrol* aan de beveiligingsteams zijn toegewezen. Roltoewijzing wordt uitgevoerd via machtigingen in het beveiligings- en compliancecentrum.

## <a name="what-you-need-to-know-before-you-begin"></a>Wat u moet weten voordat u begint

Beheerders kunnen vereiste acties uitvoeren op e-mailberichten, maar om die acties goedgekeurd te krijgen, moet de zoek- en *purge-rol* aan hen zijn toegewezen via machtigingen & **Compliancecentrum.** \>  Zonder de rol Zoeken en purge toegevoegd aan een van de rollengroepen, kunnen ze de actie niet uitvoeren.

## <a name="manual-and-automated-remediation"></a>Handmatige en geautomatiseerde herstel

*Handmatig zoeken* vindt plaats wanneer beveiligingsteams bedreigingen handmatig identificeren met behulp van de zoek- en filtermogelijkheden in Bedreigingsverkenner. Handmatige e-mail remediation kan worden geactiveerd via elke e-mailweergave *(Malware,* *Phish* of *Alle* e-mail) nadat u een reeks e-mailberichten hebt gevonden die moeten worden verankerd.

> [!div class="mx-imgBorder"]
> [![Handmatig zoeken in Office 365 Threat Explorer op datum.](../../media/tp-RemediationArticle1.png)](../../media/tp-RemediationArticle1.png#lightbox)

Beveiligingsteams kunnen Bedreigingsverkenner gebruiken om e-mailberichten op verschillende manieren te selecteren:

- Kies e-mailberichten met de hand: filters gebruiken in verschillende weergaven. Selecteer maximaal 100 e-mailberichten om te herstellen.

- Queryselectie: een hele query selecteren met behulp van de bovenste **knop Alles** selecteren. Dezelfde query wordt ook weergegeven in de gegevens voor het indienen van e-mail in het actiecentrum.

- Selectie van query's met uitsluiting: Soms willen teams met beveiligingsbewerkingen e-mailberichten herstellen door een hele query te selecteren en bepaalde e-mailberichten handmatig uit de query uit te sluiten. Een beheerder kan dit doen  door het selectievakje Alles selecteren te gebruiken en omlaag te schuiven om e-mailberichten handmatig uit te sluiten. De query kan maximaal 1000 e-mailberichten lang zijn. Het maximum aantal uitsluitingen is 100.

Nadat e-mailberichten zijn geselecteerd via Bedreigingsverkenner, kunt u beginnen met herstel door direct actie te ondernemen of door e-mailberichten in de wachtrij te zetten voor een actie:

- Directe goedkeuring: wanneer acties zoals verplaatsen naar Postvak *IN,* Verplaatsen naar  ongewenste e-mail, Verplaatsen naar verwijderde *items,* zacht verwijderen of definitief verwijderen zijn geselecteerd door beveiligingsmedewerkers die over de juiste machtigingen machtigingen hebben, en de volgende stappen voor herstel worden gevolgd, begint het herstelproces met het uitvoeren van de geselecteerde actie.  Een tijdelijke flyout toont herstel in uitvoering.

- Goedkeuring in twee stappen: een actie 'Toevoegen aan herstel' kan worden uitgevoerd door beheerders die niet over de juiste machtigingen of die moeten wachten met het uitvoeren van de actie. In dit geval worden de gerichte e-mailberichten toegevoegd aan een herstelcontainer. Goedkeuring is nodig voordat de oplossing wordt uitgevoerd.

**Geautomatiseerde onderzoeks- en antwoordacties** worden geactiveerd door waarschuwingen of door teams met beveiligingsbewerkingen van Bedreigingsverkenner. Dit kunnen aanbevolen herstelacties zijn die moeten worden goedgekeurd door een beveiligingsteam. Deze acties worden opgenomen op het **tabblad Actie** in het geautomatiseerde onderzoek.

> [!div class="mx-imgBorder"]
> [![E-mail met malware op de pagina 'Zapped' met de tijd waarop Zap is uitgevoerd.](../../media/tp-RemediationArticle3.png)](../../media/tp-RemediationArticle3.png#lightbox)

Alle herstelacties (directe goedkeuring of goedkeuring in twee stappen) die zijn gemaakt in Bedreigingsverkenner en goedgekeurde acties die afkomstig zijn van geautomatiseerde onderzoeken, worden weergegeven in het Actiecentrum. U kunt deze openen  via het linkernavigatiedeelvenster onder \> **Actiecentrum controleren.**

> [!div class="mx-imgBorder"]
> [![Het actiecentrum met een lijst met bedreigingen op datum en ernst.](../../media/tp-RemediationArticle4.png)](../../media/tp-RemediationArticle4.png#lightbox)

In het Actiecentrum ziet u alle herstelacties van de afgelopen 30 dagen. Acties die worden uitgevoerd via Bedreigingsverkenner, worden weergegeven met de naam die het team voor beveiligingsbewerkingen heeft opgegeven bij het maken van de oplossing. Acties die worden ondernomen via geautomatiseerde onderzoeken, hebben titels die beginnen met de bijbehorende waarschuwing die het onderzoek heeft geactiveerd, zoals 'Zap email cluster... '.

Open een herstelitem om details ervan weer te geven, zoals de naam, aanmaakdatum, beschrijving, ernst van bedreiging en status. U ziet ook de volgende twee tabbladen.

- **Tabblad** E-mailverzending: Hier wordt het aantal e-mailberichten weergegeven dat wordt ingediend via Bedreigingsverkenner of via geautomatiseerde onderzoeken die moeten worden vereenigd. Er kan al dan niet een actie worden ondernomen via deze e-mails.

  > [!div class="mx-imgBorder"]
  > [![Het actiecentrum met bedreigingen die wel en niet onder acties kunnen worden ondernomen.](../../media/tp-RemediationArticle5.png)](../../media/tp-RemediationArticle5.png#lightbox)

  - **Actie mogelijk:** e-mailberichten in de volgende postvaklocaties in de cloud kunnen worden geacteerd en verplaatst:
    - Postvak IN
    - Ongewenste e-mail
    - Map verwijderd
    - Map met zacht verwijderde items

      > [!NOTE]
      > Op dit moment kan alleen een gebruiker met toegang tot het postvak items uit een voorlopig verwijderde map herstellen.

  - **Niet mogelijk:** E-mailberichten op de volgende locaties kunnen niet worden gebruikt om actie te ondernemen of te worden verplaatst met herstelacties:
    - Quarantaine
    - Moeilijk verwijderde map
    - On-premises/extern
    - Mislukt/ingetrokken

  Verdachte berichten worden gecategoriseerd als herstelbaar of niet herstelbaar. In de meeste gevallen is het totaal aantal verzonden berichten gelijk aan het totale aantal verzonden berichten door herstellende en niet-herstelbare berichten. Maar in zeldzame gevallen is dit niet waar. Dit kan komen door systeemvertraingen, time-outs of verlopen berichten. Berichten verlopen op basis van de bewaarperiode van Bedreigingsverkenner voor uw organisatie.

  Tenzij u oude berichten herstelt na de bewaarperiode van Bedreigingsverkenner van uw organisatie, is het aan te raden items opnieuw te herstellen als de inconsistenties in het aantal worden weergegeven. Voor systeemvertraging worden herstelupdates meestal binnen een paar uur vernieuwd.

  Als de bewaarperiode van uw organisatie voor e-mail in Bedreigingsverkenner 30 dagen is en u herstelt e-mailberichten die 29-30 dagen terug gaan, worden de tellingen voor e-mailverzending mogelijk niet altijd bij elkaar opgetelde. De e-mailberichten zijn mogelijk al begonnen met het afkwaren van de bewaarperiode.

  Als herstel een tijdje blijft hangen in de status 'Wordt uitgevoerd', wordt dit waarschijnlijk veroorzaakt door systeemvertraingen. Het kan enkele uren duren om de oplossing te herstellen. Mogelijk ziet u variaties in het aantal e-mailinzendingen, omdat de query aan het begin van de herstelquery mogelijk niet is opgenomen vanwege systeemvertraging. Het is een goed idee om in dergelijke gevallen opnieuw te proberen te herstellen.

  > [!NOTE]
  > Voor de beste resultaten moet herstel worden uitgevoerd in batches van 50.000 of minder.

  Er wordt alleen een oplossing voor e-mailberichten gebruikt tijdens herstel. Niet-herstelbare e-mailberichten kunnen niet worden opgelost door het Office 365-e-mailsysteem, omdat ze niet worden opgeslagen in postvakken in de cloud.

  Beheerders kunnen zo nodig acties uitvoeren op e-mailberichten in quarantaine, maar die e-mailberichten verlopen in quarantaine als ze niet handmatig worden verwijderd. E-mailberichten die in quarantaine zijn geplaatst vanwege schadelijke inhoud, zijn niet toegankelijk voor gebruikers, dus personeel van de beveiliging hoeft niets te doen om bedreigingen in quarantaine te verwijderen. Als de e-mailberichten on-premises of extern zijn, kan contact worden opgenomen met de gebruiker om het verdachte e-mailbericht te adresseerd. Beheerders kunnen ook afzonderlijke e-mailserver-/beveiligingshulpprogramma's gebruiken voor verwijdering. Deze e-mailberichten kunt u herkennen door de bezorgingslocatie *= on-prem* external filter in Threat Explorer toe te passen. Voor mislukte of verwijderde e-mailberichten of voor e-mailberichten die niet toegankelijk zijn voor gebruikers, wordt er geen e-mail beperkt, omdat deze e-mailberichten niet in het postvak komen.

  In de volgende afbeelding ziet u hoe een inzending eruitziet in het Actiecentrum. Een herstel kan meerdere inzendingen bevatten. Als meerdere acties worden goedgekeurd via één geautomatiseerd onderzoek, wordt elke e-mail- of e-mailclusteractie in dezelfde oplossing weergegeven als een andere inzending.

  > [!div class="mx-imgBorder"]
  > [![Flyoutvenster van ZAP-e-mailcluster.](../../media/tp-RemediationArticle6.png)](../../media/tp-RemediationArticle6.png#lightbox)

  Selecteer een item voor het indienen van e-mail om de details van die herstelfunctie weer te geven, zoals de query (wanneer herstel wordt geactiveerd via geautomatiseerde onderzoeken of Bedreigingsverkenner door een query te selecteren) en de begin- en eindtijd van herstel. Er wordt ook een lijst weergegeven met berichten die zijn ingediend voor herstel. Wanneer berichten uit de bewaarperiode van Bedreigingsverkenner worden verplaatst, verdwijnen de berichten uit deze lijst. In de lijst ziet u ook afzonderlijke berichten die kunnen worden vereenigbaar.

- **Actielogboeken:** dit tabblad bevat de berichten die zijn herstellen, inclusief de goedgekeurde datum, de beheerder die de actie, actie, status en tellingen heeft goedgekeurd.

  Status kan de volgende status hebben:

  - **Gestart:** Herstel wordt geactiveerd.
  - **In wachtrij:** oplossing wordt in de wachtrij geplaatst voor risicobeperking van e-mailberichten.
  - **Wordt uitgevoerd:** risicobeperking wordt uitgevoerd.
  - **Voltooid:** risicobeperking voor alle herstelbare e-mailberichten voltooid of met een aantal fouten.
  - **Mislukt:** er zijn geen herstel is gelukt.

  Aangezien alleen herstel van e-mailberichten kan worden onder controle, wordt het opschonen van elke e-mail als geslaagd of mislukt weergegeven. Van de totale herstelbare e-mailberichten worden succesvolle en mislukte risicobeperking gerapporteerd.

  - **Succes:** De gewenste actie voor het herstellen van e-mailberichten is voltooid. Bijvoorbeeld: Een beheerder wil e-mailberichten verwijderen uit postvakken, dus de beheerder voert de actie uit om e-mailberichten te verwijderen. Als er geen herstelbare e-mail wordt gevonden in de oorspronkelijke map nadat de actie is ondernomen, wordt de status als geslaagd weergeven.

  - **Fout:** De gewenste actie bij het herstellen van e-mailberichten is mislukt. Bijvoorbeeld: Een beheerder wil e-mailberichten verwijderen uit postvakken, dus de beheerder voert de actie uit om e-mailberichten te verwijderen. Als er nog steeds een herstelbaar e-mailbericht in het postvak is gevonden nadat de actie is ondernomen, wordt de status als mislukt weergeven.
  
  - **Al in bestemming:** De gewenste actie is al ondernomen op het e-mailbericht OF het e-mailbericht bestaat al op de doellocatie. Bijvoorbeeld: Een e-mailbericht is op dag 1 door de beheerder in Verkenner zacht verwijderd. Vergelijkbare e-mailberichten worden dan op dag 2 we zien, die weer zacht worden verwijderd door de beheerder. Wanneer u deze e-mailberichten selecteert, worden sommige e-mailberichten van de eerste dag automatisch door de beheerder geselecteerd, die al zacht zijn verwijderd. Er wordt nu geen actie ondernomen op deze e-mailberichten, ze worden alleen maar als 'al in bestemming' gezien, omdat er geen actie is ondernomen op deze e-mailberichten zoals ze op de doellocatie aanwezig zijn.

  Selecteer een item in het actielogboek om hersteldetails weer te geven. Als de gegevens 'geslaagd' of 'niet gevonden in postvak' zeggen, is dat item al uit het postvak verwijderd. Soms is er een systeemfout tijdens herstel. In die gevallen is het een goed idee om herstel te proberen.

  Als u grote batches herstelt, kunt u ook de berichten exporteren die worden verzonden voor herstel via E-mailverzending en berichten die zijn herstellen via Actielogboeken. De exportlimiet is verhoogd tot 100.000 records.

  Herstel is een krachtig hulpmiddel om bedreigingen tegen te gaan en verdachte e-mails aan te pakken. Het helpt een organisatie veilig te houden.
