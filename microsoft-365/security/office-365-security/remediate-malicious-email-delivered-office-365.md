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
description: Herstel van bedreigingen
appliesto:
- Microsoft 365 Defender
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 202ebc8b79368c8d41fd3727b67359ddcb8a08fa
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204721"
---
# <a name="remediate-malicious-email-delivered-in-office-365"></a>Schadelijke e-mail herstellen die is bezorgd in Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)

Herstel betekent een voorgeschreven actie ondernemen tegen een bedreiging. Schadelijke e-mail die naar uw organisatie wordt verzonden, kan worden opgeruimd door het systeem, via zap (Zero Hour Auto Purge) of door beveiligingsteams door middel van herstelacties zoals verplaatsen naar *Postvak IN,* naar ongewenste e-mail *gaan,* naar verwijderde *items* gaan, soft *delete* of *hard delete.* Met Microsoft Defender voor Office 365 P2/E5 kunnen beveiligingsteams bedreigingen in e-mail- en samenwerkingsfunctionaliteit corrigeren via handmatig en geautomatiseerd onderzoek.

> [!NOTE]
> Als u schadelijke e-mail wilt herstellen, hebben beveiligingsteams de zoek- en *zuiverrol* nodig die aan hen is toegewezen. Roltoewijzing wordt uitgevoerd via machtigingen in het beveiligings- en compliancecentrum.

## <a name="what-you-need-to-know-before-you-begin"></a>Wat u moet weten voordat u begint

Beheerders kunnen vereiste actie ondernemen voor e-mailberichten, maar  als ze deze acties willen goedkeuren, moeten ze de zoek- en zuiverrol aan hen hebben toegewezen via machtigingen &  \> **compliancecentrum.** Zonder de rol 'zoeken en zuiveren' die is toegevoegd aan een van de rollengroepen, kunnen ze de actie niet uitvoeren.

## <a name="manual-and-automated-remediation"></a>Handmatige en geautomatiseerde herstelmaatregelen

*Handmatig zoeken* vindt plaats wanneer beveiligingsteams bedreigingen handmatig identificeren met behulp van de zoek- en filtermogelijkheden in Threat Explorer. Handmatige e-mailsanering kan worden geactiveerd via een e-mailweergave *(Malware,* *Phish* of *Alle* e-mail) nadat u een set e-mailberichten hebt gevonden die moeten worden gesaneerd.

> [!div class="mx-imgBorder"]
> [![Handmatig zoeken in Office 365 Threat Explorer op datum.](../../media/tp-RemediationArticle1.png)](../../media/tp-RemediationArticle1.png#lightbox)

Beveiligingsteams kunnen Threat Explorer op verschillende manieren gebruiken om e-mailberichten te selecteren:

- Kies e-mailberichten met de hand: Filters gebruiken in verschillende weergaven. Selecteer maximaal 100 e-mailberichten om te corrigeren.

- Queryselectie: Selecteer een hele query met behulp van de bovenste **knop Alles** selecteren. Dezelfde query wordt ook weergegeven in de details van de postverzending van het actiecentrum.

- Selectie van query's met uitsluiting: Soms willen beveiligingsbewerkingsteams e-mailberichten herstellen door een hele query te selecteren en bepaalde e-mailberichten handmatig uit de query uit te sluiten. Een beheerder kan het selectievakje  Alles selecteren gebruiken en omlaag schuiven om e-mailberichten handmatig uit te sluiten. De query kan maximaal 1000 e-mailberichten vasthouden. Het maximum aantal uitsluitingen is 100.

Nadat e-mailberichten zijn geselecteerd via Threat Explorer, kunt u de herstelactie starten door direct actie te ondernemen of door e-mailberichten in de wachtrij te zetten voor een actie:

- Directe goedkeuring: Wanneer acties zoals verplaatsen naar *Postvak IN,* naar ongewenste e-mail *gaan,* naar verwijderde *items* gaan, soft *delete* of hard *delete* worden geselecteerd door beveiligingspersoneel dat over de juiste machtigingen heeft en de volgende stappen in de herstelprocedure worden gevolgd, wordt de geselecteerde actie uitgevoerd door het herstelproces. Een tijdelijke flyout toont herstel in uitvoering.

- Goedkeuring in twee stappen: beheerders die niet over de juiste machtigingen of die moeten wachten om de actie uit te voeren, kunnen een actie in twee stappen uitvoeren. In dit geval worden de gerichte e-mailberichten toegevoegd aan een herstelcontainer. Goedkeuring is nodig voordat de herstelmaatregelen worden uitgevoerd.

**Geautomatiseerde onderzoek- en antwoordacties** worden geactiveerd door waarschuwingen of door beveiligingsbewerkingsteams van Threat Explorer. Dit kunnen aanbevolen herstelacties zijn die moeten worden goedgekeurd door een beveiligingsteam. Deze acties worden opgenomen op het tabblad **Actie** in het geautomatiseerde onderzoek.

> [!div class="mx-imgBorder"]
> [![E-mail met malware op de pagina 'Zapped' met de tijd van zapuitvoering.](../../media/tp-RemediationArticle3.png)](../../media/tp-RemediationArticle3.png#lightbox)

Alle herstelacties (directe goedkeuring of goedkeuring in twee stappen) die zijn gemaakt in Threat Explorer en goedgekeurde acties die afkomstig zijn van geautomatiseerde onderzoeken, worden weergegeven in het Actiecentrum. Toegang tot deze gegevens  via het linkernavigatievenster onder \> **Actiecentrum controleren.**

> [!div class="mx-imgBorder"]
> [![Het actiecentrum met een lijst met bedreigingen op datum en ernst.](../../media/tp-RemediationArticle4.png)](../../media/tp-RemediationArticle4.png#lightbox)

Actiecentrum toont alle herstelacties van de afgelopen 30 dagen. Acties die worden uitgevoerd via Threat Explorer, worden weergegeven met de naam die het team voor beveiligingsbewerkingen heeft opgegeven bij het maken van de herstelbewerking. Acties die worden ondernomen via geautomatiseerde onderzoeken, hebben titels die beginnen met de bijbehorende waarschuwing die het onderzoek heeft geactiveerd, zoals 'Zap email cluster...'.

Open een herstelitem om details ervan weer te geven, zoals de naam, de aanmaakdatum, de beschrijving, de ernst van de bedreiging en de status. U ziet ook de volgende twee tabbladen.

- **Tabblad** E-mailverzending: hiermee wordt het aantal e-mailberichten weergegeven dat is verzonden via Threat Explorer of geautomatiseerde onderzoeken die moeten worden gesaneerd. Deze e-mailberichten kunnen wel of niet worden gebruikt.

  > [!div class="mx-imgBorder"]
  > [![Het actiecentrum met actiebare en niet-actiebare bedreigingen.](../../media/tp-RemediationArticle5.png)](../../media/tp-RemediationArticle5.png#lightbox)

  - **Actie:** E-mailberichten in de volgende cloudpostvaklocaties kunnen worden gebruikt en verplaatst:
    - Postvak IN
    - Ongewenste e-mail
    - Verwijderde map
    - Map met soft-deleted

      > [!NOTE]
      > Op dit moment kan alleen een gebruiker met toegang tot het postvak items herstellen uit een zacht verwijderde map.

  - **Niet actiebaar:** e-mailberichten op de volgende locaties kunnen niet worden gebruikt of verplaatst in herstelacties:
    - Quarantaine
    - Map met hard verwijderde bestanden
    - On-premises/extern
    - Mislukt/gedaald

  Verdachte berichten worden gecategoriseerd als herstelbaar of niet-herstelbaar. In de meeste gevallen zijn herstelbare en niet-herstelbare berichten gelijk aan het totale aantal verzonden berichten. Maar in zeldzame gevallen is dit mogelijk niet waar. Dit kan gebeuren vanwege systeemvertraging, time-outs of verlopen berichten. Berichten verlopen op basis van de bewaarperiode van Threat Explorer voor uw organisatie.

  Tenzij u oude berichten herstelt na de bewaarperiode van Threat Explorer van uw organisatie, is het raadzaam om items opnieuw te corrigeren als er getalconsequenties worden weergegeven. Voor systeemvertraging worden herstelupdates meestal binnen enkele uren vernieuwd.

  Als de bewaarperiode van uw organisatie voor e-mail in Threat Explorer 30 dagen is en u e-mailberichten herstelt die 29-30 dagen teruggaan, wordt het aantal e-mailberichten mogelijk niet altijd geteld. Mogelijk zijn de e-mailberichten al buiten de bewaarperiode gegaan.

  Als herstelmaatregelen een tijdje in de status 'In progress' blijven hangen, is dit waarschijnlijk het gevolg van systeemvertraging. Het kan enkele uren duren voordat de hersteltijd is vereend. Mogelijk ziet u variaties in het aantal e-mailberichten, omdat sommige e-mailberichten mogelijk niet zijn opgenomen in de query aan het begin van de herstelfunctie vanwege systeemvertraging. Het is een goed idee om in dergelijke gevallen opnieuw te proberen te corrigeren.

  > [!NOTE]
  > Voor de beste resultaten moet herstel worden uitgevoerd in batches van 50.000 of minder.

  Alleen herstelbare e-mailberichten worden tijdens het herstel gebruikt. Niet-herstelbare e-mailberichten kunnen niet worden gesaneerd door het Office 365-e-mailsysteem, omdat ze niet worden opgeslagen in cloudpostvakken.

  Beheerders kunnen indien nodig acties uitvoeren op e-mailberichten in quarantaine, maar deze e-mailberichten verlopen buiten quarantaine als ze niet handmatig worden verwijderd. E-mailberichten die in quarantaine zijn geplaatst vanwege schadelijke inhoud, zijn niet toegankelijk voor gebruikers, dus beveiligingspersoneel hoeft geen actie te ondernemen om bedreigingen in quarantaine te verwijderen. Als de e-mailberichten on-premises of extern zijn, kan er contact met de gebruiker worden opgenomen om de verdachte e-mail aan te pakken. Of de beheerders kunnen afzonderlijke e-mailserver-/beveiligingshulpmiddelen gebruiken om ze te verwijderen. Deze e-mailberichten kunnen worden geïdentificeerd door de bezorgingslocatie *= extern on-prem-filter* toe te passen in Threat Explorer. Voor mislukte of verwijderde e-mail of e-mail die niet toegankelijk is voor gebruikers, is er geen e-mail die u kunt beperken, omdat deze e-mailberichten het postvak niet bereiken.

  In de volgende afbeelding ziet u hoe een inzending eruitziet in het Actiecentrum. Een herstel kan meerdere inzendingen bevatten. Als meerdere acties worden goedgekeurd via één geautomatiseerd onderzoek, wordt elke e-mail- of e-mailclusteractie weergegeven in dezelfde herstelactie als een andere inzending.

  > [!div class="mx-imgBorder"]
  > [![ZAP-e-mailcluster flyoutvenster.](../../media/tp-RemediationArticle6.png)](../../media/tp-RemediationArticle6.png#lightbox)

  Selecteer een item voor het indienen van e-mail om de details van die herstelfunctie weer te geven, zoals de query (wanneer herstel wordt geactiveerd via geautomatiseerde onderzoeken of Threat Explorer door een query te selecteren) en de begin- en eindtijden van herstel. Er wordt ook een lijst weergegeven met berichten die zijn verzonden voor herstel. Wanneer berichten uit de bewaarperiode van Threat Explorer verdwijnen, verdwijnen de berichten uit deze lijst. In de lijst worden ook afzonderlijke berichten weergegeven die kunnen worden gesaneerd.

- **Actielogboeken:** Op dit tabblad ziet u de berichten die zijn gesaneerd, inclusief goedgekeurde datum, beheerder die de actie, actie, status en aantal heeft goedgekeurd.

  Status kan het volgende zijn:

  - **Gestart:** Herstel wordt geactiveerd.
  - **Wachtrij:** Herstel wordt in de wachtrij geplaatst voor het beperken van e-mailberichten.
  - **In uitvoering:** Mitigatie wordt uitgevoerd.
  - **Voltooid:** Beperking van alle herstelbare e-mailberichten die zijn voltooid of met bepaalde fouten.
  - **Mislukt:** er zijn geen herstels gelukt.

  Aangezien alleen herstelbare e-mailberichten kunnen worden gebruikt, wordt de opschoning van elke e-mail als succesvol of mislukt weergegeven. Van de totale herstelbare e-mailberichten worden succesvolle en mislukte mitigaties gerapporteerd.

  - **Succes:** De gewenste actie voor het herstellen van e-mailberichten is voltooid. Bijvoorbeeld: Een beheerder wil e-mailberichten uit postvakken verwijderen, zodat de beheerder de actie onderneemt voor het verwijderen van e-mailberichten. Als een herstelbare e-mail niet wordt gevonden in de oorspronkelijke map nadat de actie is ondernomen, wordt de status als succesvol weergeven.

  - **Fout:** De gewenste actie voor het herstellen van e-mailberichten is mislukt. Bijvoorbeeld: Een beheerder wil e-mailberichten uit postvakken verwijderen, zodat de beheerder de actie onderneemt voor het verwijderen van e-mailberichten. Als er nog steeds een herstelbare e-mail in het postvak wordt gevonden nadat de actie is ondernomen, wordt de status als mislukt weergeven.
  
  - **Al op bestemming:** De gewenste actie is al ondernomen op het e-mailbericht OF het e-mailbericht bestond al op de doellocatie. Bijvoorbeeld: Een e-mailbericht is op dag één door de beheerder door Explorer verwijderd. Vervolgens worden soortgelijke e-mailberichten op dag 2, die weer zacht worden verwijderd door de beheerder. Terwijl u deze e-mailberichten selecteert, worden sommige e-mailberichten vanaf dag één door de beheerder verwijderd. Deze e-mailberichten worden niet opnieuw beantwoord, ze worden alleen maar als 'al in bestemming' gezien er geen actie is ondernomen op deze e-mailberichten zoals ze op de bestemmingslocatie aanwezig waren.

  Selecteer een item in het actielogboek om hersteldetails weer te geven. Als op de details 'geslaagd' of 'niet gevonden in postvak' staat, is dat item al uit het postvak verwijderd. Soms is er een systeemfout tijdens herstel. In die gevallen is het een goed idee om herstel te proberen.

  Als u grote batches herstelt, kunt u ook de berichten exporteren die voor herstel worden verzonden via E-mailverzending en berichten die zijn gesaneerd via actielogboeken. De exportlimiet wordt verhoogd naar 100.000 records.

Beveiligingsteam kan maximaal 50 gelijktijdige handmatige herstelmaatregelen nemen. Er is echter geen limiet ingesteld voor geautomatiseerde onderzoek- en antwoordacties.

  Herstel is een krachtig hulpmiddel om bedreigingen te beperken en verdachte e-mailberichten aan te pakken. Het helpt een organisatie veilig te houden.
