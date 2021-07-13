---
title: E-mailanalyse in onderzoeken voor Microsoft Defender voor Office 365
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
keywords: geautomatiseerde reactie op incidenten, onderzoek, herstel, bedreigingsbeveiliging
description: Bekijk hoe e-mailanalyse in onderzoeken werkt in Microsoft Defender voor Office 365.
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d222e1c8b6b5ca9e111b1dbe6b7fb31138a157b2
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395048"
---
# <a name="email-analysis-in-investigations-for-microsoft-defender-for-office-365"></a>E-mailanalyse in onderzoeken voor Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Tijdens het geautomatiseerde onderzoek naar waarschuwingen analyseert Microsoft Defender voor Office 365 de oorspronkelijke e-mail voor bedreigingen en identificeert u andere e-mailberichten die betrekking hebben op de oorspronkelijke e-mail en mogelijk een deel van een aanval. Deze analyse is belangrijk omdat e-mailaanvallen zelden uit één e-mail bestaan.

De e-mailanalyse van het geautomatiseerde onderzoek identificeert e-mailclusters met behulp van kenmerken uit de oorspronkelijke e-mail om te zoeken naar e-mailberichten die door uw organisatie zijn verzonden en ontvangen. Dit is vergelijkbaar met een beveiligingsbewerkingsanalist die zou zoeken naar de gerelateerde e-mailberichten in Explorer of Geavanceerd zoeken. Er worden verschillende query's gebruikt om overeenkomende e-mailberichten te identificeren, omdat aanvallers meestal de e-mailparameters aanpassen om beveiligingsdetectie te voorkomen. Met de clusteranalyse worden deze controles uitgevoerd om te bepalen hoe e-mailberichten die betrokken zijn bij het onderzoek, moeten worden verwerkt:

- Met de e-mailanalyse worden query's (clusters) van e-mailberichten gemaakt met behulp van kenmerken uit de oorspronkelijke e-mail: afzenderwaarden (IP-adres, verzendend domein) en inhoud (onderwerp, cluster-id) om e-mailberichten te zoeken die gerelateerd zijn.
- Als bij analyse van de URL's en bestanden van de oorspronkelijke e-mail wordt aangegeven dat sommige e-mail schadelijk zijn (dat wil zeggen malware of phish), worden er ook query's of clusters met e-mailberichten gemaakt die de schadelijke URL of het bestand bevatten.
- E-mailclusteranalyse telt de bedreigingen die zijn gekoppeld aan de overeenkomende e-mailberichten in het cluster om te bepalen of de e-mailberichten schadelijk, verdacht of niet duidelijk zijn. Als het cluster met e-mailberichten dat overeenkomt met de query een voldoende hoeveelheid spam, normale phish-, phish- of malware-bedreigingen met hoog vertrouwen bevat, wordt dit type bedreiging toegepast op het e-mailcluster. 
- De e-mailclusteranalyse controleert ook de meest recente bezorgingslocatie van de oorspronkelijke e-mail en e-mailberichten in de e-mailclusters om te bepalen of de e-mailberichten mogelijk nog moeten worden verwijderd of al zijn verwijderd of voorkomen. Deze analyse is belangrijk omdat aanvallers schadelijke inhoud, plus beveiligingsbeleid en beveiliging, kunnen variëren tussen postvakken. Deze mogelijkheid leidt tot situaties waarin schadelijke inhoud nog steeds in postvakken kan worden geplaatst, ook al is een of meer schadelijke e-mailberichten gedetecteerd en verwijderd door Zap (Zero Hour Auto Protection).
- E-mailclusters die als schadelijk worden beschouwd als gevolg van malware, phish, schadelijke bestanden of schadelijke URL's, krijgen een in behandeling zijnde actie om de e-mailberichten te verwijderen wanneer er nog steeds in het postvak in de cloud (Postvak IN of ongewenste e-mailmap) staan. Als schadelijke e-mailberichten of e-mailclusters alleen 'Niet in postvak' zijn (geblokkeerd, in quarantaine geplaatst, mislukt, zacht verwijderd, enzovoort) of 'On-premises/extern' zonder in het postvak van de cloud, wordt er geen actie in behandeling ingesteld om ze te verwijderen.
- Als wordt vastgesteld dat een van de e-mailclusters schadelijk is, wordt de door het cluster geïdentificeerde bedreiging terug toegepast op de oorspronkelijke e-mail die betrokken is bij het onderzoek. Dit gedrag is vergelijkbaar met een beveiligingsanalist die e-mailjachtresultaten gebruikt om de uitkomst van een oorspronkelijke e-mail te bepalen op basis van overeenkomende e-mailberichten. Dit resultaat zorgt ervoor dat, ongeacht of de URL's, bestanden of bron-e-mailindicatoren van een oorspronkelijke e-mail worden gedetecteerd of niet, het systeem schadelijke e-mailberichten kan identificeren die detectie mogelijk omzeilen door middel van personalisatie, morphing, ontwijking of andere technieken voor aanvallers.
- In het onderzoek naar gebruikerscompromitteren worden extra e-mailclusters gemaakt om mogelijke e-mailproblemen te identificeren die door het postvak zijn gemaakt. Dit proces omvat een schone e-mailcluster (goede e-mailberichten van gebruikers, mogelijke gegevens exfiltratie en potentiële command/control-e-mailberichten), verdachte e-mailclusters (e-mailberichten met spam of normale phish) en schadelijke e-mailclusters (e-mailberichten met malware of phish met hoog vertrouwen). Deze e-mailclusters bevatten gegevens van beveiligingsbewerkingsanalisten om te bepalen welke andere problemen mogelijk moeten worden opgelost vanuit een compromis en welke e-mailberichten mogelijk de oorspronkelijke waarschuwingen hebben veroorzaakt (bijvoorbeeld phish/spam waardoor gebruikers beperkingen voor het verzenden hebben veroorzaakt)

E-mailclusteranalyse via overeenkomsten en kwaadaardige entiteitsquery's zorgt ervoor dat e-mailproblemen volledig worden geïdentificeerd en opgeschoond, zelfs als slechts één e-mail van een aanval wordt geïdentificeerd. U kunt koppelingen uit de zijvensterweergaven van het e-mailcluster gebruiken om de query's in Explorer of Geavanceerd zoeken te openen om diepere analyses uit te voeren en de query's zo nodig te wijzigen. Deze mogelijkheid maakt handmatige verfijning en herstel mogelijk als u de query's van het e-mailcluster te smal of te breed vindt (inclusief niet-gerelateerde e-mailberichten).

Hier zijn extra verbeteringen voor e-mailanalyses in onderzoeken.

## <a name="air-investigation-ignores-advanced-delivery-items-secops-mailbox-and-phishedu-messages"></a>Air-onderzoek negeert geavanceerde bezorgingsitems (SecOps-postvak en PhishEDU-berichten)

Tijdens de e-mailclusteranalyse worden bij alle clusterquery's beveiligingspostvakken genegeerd die zijn ingesteld als postvakken voor beveiligingsbewerkingen in het beleid voor geavanceerde bezorging. In de query's voor e-mailclustering worden phish-simulatieberichten (onderwijsberichten) genegeerd die zijn geconfigureerd in het beleid voor geavanceerde bezorging. De secops en de phishEdu-uitsluitingswaarden worden niet weergegeven in de query om de clusterkenmerken eenvoudiger en beter leesbaar te houden. Deze uitsluiting zorgt ervoor dat bedreigingsinformatie en operationele postvakken (SecOps-postvakken) en phish-simulaties (PhishEdu) worden genegeerd tijdens bedreigingsanalyse en niet worden verwijderd tijdens herstel. 

>[!Note]
>Wanneer u een e-mailcluster opent om deze in Explorer weer te geven vanaf de details van het e-mailcluster, worden de postvakfilters PhishEdu en SecOps toegepast in Explorer, maar deze worden niet weergegeven. Als u de Explorer-filters, -datums of -vernieuwingen wijzigt op de pagina, worden de uitsluitingen van phishEdu/SecOps-filter verwijderd en worden e-mailberichten die overeenkomen met deze weer weergegeven. Als u de Explorer-pagina vernieuwt met behulp van de browservernieuwingsfunctie, worden de oorspronkelijke queryfilters opnieuw geladen, inclusief de filters PhishEdu/SecOps, maar worden de volgende wijzigingen verwijderd.
>

## <a name="air-updates-pending-email-action-status"></a>AIR-updates in behandeling e-mailactiestatus

De analyse van e-mail van het onderzoek berekent e-mailbedreigingen en -locaties op het moment van het onderzoek om het onderzoeksonderzoek te maken. Deze gegevens kunnen verouderd en verouderd worden wanneer acties buiten het onderzoek van invloed zijn op de e-mailberichten die betrokken zijn bij het onderzoek. Beveiligingsbewerkingen kunnen bijvoorbeeld handmatig zoeken en herstellen e-mailberichten opruimen die zijn opgenomen in een onderzoek. Op dezelfde manier zijn e-mailberichten mogelijk verwijderd door verwijderingsacties die zijn goedgekeurd in parallelle onderzoeken of automatische quarantaineacties (Zero-hour Auto Protection, ZAP). Bovendien kunnen vertraagde detecties van bedreigingen na e-mailbezorging het aantal bedreigingen in de e-mailquery's/clusters van het onderzoek wijzigen. 

Om ervoor te zorgen dat de onderzoeksacties up-to-date zijn, worden de e-mailanalysequery's regelmatig opnieuw uitgevoerd om de e-maillocaties en -bedreigingen bij te werken. 

- Wanneer de gegevens van het e-mailcluster worden gewijzigd, worden het aantal bedreigingen en de meest recente bezorgingslocatie bijgewerkt. 
- Als e-mailberichten of e-mailcluster met in behandeling zijnde acties niet meer in het postvak staan, wordt de actie in behandeling geannuleerd en wordt de schadelijke e-mail/cluster als herstel beschouwd.
- Zodra alle bedreigingen van het onderzoek zijn opgelost of geannuleerd, zoals hierboven is vermeld, wordt het onderzoek overgeleverd aan een hersteltoestand en wordt de oorspronkelijke waarschuwing opgelost.

## <a name="the-display-of-incident-evidence-for-email-and-email-clusters"></a>Het weergeven van bewijs van incidenten voor e-mail- en e-mailclusters

Op e-mail gebaseerde gegevens op het tabblad Bewijs en antwoord voor een incident worden nu de volgende gegevens weergegeven.

:::image type="content" source="../../media/email-analysis-investigations/email-analysis-evidence-example.png" alt-text="Voorbeeld van e-mailanalysegegevens in Bewijs en antwoord" lightbox="../../media/email-analysis-investigations/email-analysis-evidence-example.png":::

Van de genummerde bijroepen in de afbeelding:

1. U kunt herstelacties uitvoeren, naast het **Actiecentrum.**
2. U kunt herstelactie ondernemen voor e-mailclusters met een **kwaadaardige** uitspraak (maar niet **verdacht).**
3. Voor de e-mail spam vonnis, phishing is gesplitst in hoog vertrouwen en normale phish.

   Voor een schadelijke uitspraak zijn de bedreigingscategorieën malware, phish met hoog vertrouwen, schadelijke URL en schadelijk bestand.

   Voor een verdachte uitspraak zijn de bedreigingscategorieën spam en normale phish.

4. Het aantal e-mailberichten is gebaseerd op de meest recente bezorgingslocatie en bevat tellers voor e-mail in postvakken, niet in postvakken en on-premises.
5. Bevat de datum en tijd van de query, die mogelijk worden bijgewerkt voor de meest recente gegevens.

Voor e-mail-  of e-mailclusters  op het tabblad Entiteiten van een incident betekent Voorkomen dat er geen schadelijke e-mailberichten in het postvak voor dit item (e-mail of cluster) waren. Hier volgt een voorbeeld.

:::image type="content" source="../../media/email-analysis-investigations/email-analysis-evidence-example-prevented.png" alt-text="Voorbeeld van een verhinderde e-mail" lightbox="../../media/email-analysis-investigations/email-analysis-evidence-example-prevented.png":::

In dit voorbeeld is de e-mail schadelijk, maar niet in een postvak.

## <a name="next-steps"></a>Volgende stappen

- [Lopende of voltooide herstelacties weergeven](air-review-approve-pending-completed-actions.md)