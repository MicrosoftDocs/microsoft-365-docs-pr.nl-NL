---
title: Scenario's en use cases voor Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: laurieellis
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
description: Zoek scenario's over het gebruik SharePoint Syntex in uw organisatie.
ms.openlocfilehash: b28239a304c8fab209436c12e6cdbffe160b7981
ms.sourcegitcommit: a3359982fea01339c7377e3ee89f223788cee0bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/28/2021
ms.locfileid: "52697059"
---
# <a name="scenarios-and-use-cases-for-microsoft-sharepoint-syntex"></a>Scenario's en use cases voor Microsoft SharePoint Syntex

Gebruik de volgende voorbeeldscenario's om ideeën te vragen over hoe u syntex in SharePoint organisatie kunt gebruiken.

- [Scenario: Gegevens van facturen bijhouden met formulierverwerking](adoption-scenarios.md#scenario-track-data-from-invoices-with-form-processing)
- [Scenario: Gegevens uit contracten bijhouden met documentkennis](adoption-scenarios.md#scenario-track-information-from-contracts-with-document-understanding)
- [Scenario: Risico's vermijden met recordsbeheer, documentbeheer en complianceprocessen op basis van SharePoint Syntex](adoption-scenarios.md#scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex)
- [Scenario: Gegevens uit eerder ontoegankelijke documenten vastleggen](adoption-scenarios.md#scenario-capture-information-from-previously-inaccessible-documents)
- [Scenario: Gegevensverwerking verbeteren om inzichten en analyses te bieden](adoption-scenarios.md#scenario-improve-data-processing-to-provide-insights-and-analytics)
- [Scenario: Orderverwerking automatiseren](adoption-scenarios.md#scenario-automate-order-processing)
- [Scenario: Vereenvoudig het verlengingsproces voor visa](adoption-scenarios.md#scenario-simplify-visa-renewal-process)

## <a name="scenario-track-data-from-invoices-with-form-processing"></a>Scenario: Gegevens van facturen bijhouden met formulierverwerking

U kunt bijvoorbeeld een proces instellen met behulp van SharePoint Syntex en Power Automate om facturen bij te houden en te controleren.

1. Stel een bibliotheek in om de factuurdocumenten op te slaan.
1. Train het model om velden in de documenten te herkennen.
1. Haal de velden op die u wilt bijhouden in een lijst.
1. Een stroom instellen om u op de hoogte te stellen van specifieke gebeurtenissen, zoals:
    - Er wordt een nieuwe factuur toegevoegd.
    - Een factuur is na de einddatum.
    - Een factuur is voor een bedrag dat groter is dan uw automatische goedkeuringsbedrag.

![Facturen bijhouden en controleren met SharePoint Syntex en Power Automate](../media/content-understanding/process-invoices-flow.png)

Wanneer u dit scenario automatiseert, kunt u het volgende doen:

- Bespaar tijd en geld door automatisch gegevens uit de facturen op te halen in plaats van handmatig te doen.
- Verminder mogelijke fouten en zorg voor een betere naleving door werkstromen te gebruiken om facturen te controleren en u op de hoogte te stellen van eventuele problemen.

## <a name="scenario-track-information-from-contracts-with-document-understanding"></a>Scenario: Gegevens uit contracten bijhouden met documentkennis

Als een ander voorbeeld kunt u een proces instellen om contracten te identificeren die uw bedrijf heeft met andere bedrijven of personen. Stel een model in om belangrijke informatie uit die contracten op te halen, zoals de klantnaam, kosten, datums of andere belangrijke informatie, en voeg de informatie toe aan de bibliotheek als velden die u snel kunt bekijken. Een bewaarlabel toepassen op de documentbibliotheek om ervoor te zorgen dat contracten niet vóór een bepaalde periode kunnen worden verwijderd voor de juiste naleving van uw bedrijfsvoorschriften.

1. Begin in het inhoudscentrum en maak een nieuw documentkennismodel voor contracten.
1. Upload voorbeelddocumenten voor positieve en negatieve voorbeelden en voer vervolgens de training uit om contractdocumenten te identificeren en de resultaten te bekijken.
1. Train de extractor om velden in de contracten te identificeren, zoals de naam, kosten en datum van de klant, en test vervolgens de extractor.
1. Wanneer het model is voltooid, kunt u het model toepassen op een bibliotheek waar u contracten kunt uploaden.
1. Pas een bewaarlabel toe op het datumveld, zodat contracten voor de vereiste tijd in de bibliotheek worden bewaard.

![Contracten bijhouden en controleren met SharePoint Syntex- en bewaarlabels](../media/content-understanding/process-contracts-flow.png)

Wanneer u dit scenario automatiseert, kunt u het volgende doen:

- Bespaar tijd en geld door automatisch gegevens uit de contracten op te halen in plaats van handmatig te doen.
- Zorg voor betere naleving door bewaarlabels te gebruiken om ervoor te zorgen dat de contracten op de juiste manier worden bewaard.

## <a name="scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex"></a>Scenario: Risico's vermijden met recordsbeheer, documentbeheer en complianceprocessen op basis van SharePoint Syntex

Het beperken van risico's is een gemeenschappelijk doel voor de meeste bedrijven. Mogelijk hebt u het volgende nodig:

- Een betere manier om informatiebeheer in uw tenant op te geven/af te dwingen.
- Het systeem voor de classificatie van documenten, e-mailberichten en andere communicatievormen als 'records' voor projecten verbeteren.
- Om ontvangstbevestigingen, contracten, en meer te controleren, om ervoor te zorgen dat het bedrijfsbeleid wordt nageleefd.
- Om ervoor te zorgen dat projecten alle documentatie hebben die nodig is voor naleving.

Stel een aantal processen in voor naleving SharePoint Syntex om documenten en formulieren die beter beheer nodig hebben, vast te leggen en op de juiste manier te classificeren, te controleren en te markeren. U kunt op syntex SharePoint vertrouwen om inhoud automatisch te classificeren in plaats van dat u erop vertrouwt dat eindgebruikers handmatig labelen of het complianceteam om handmatig beheerregels en archivering toe te passen. En u kunt een vereenvoudigde zoekervaring inschakelen, gegevensvolumes beheren, recordsbeheer- en bewaarbeleid toepassen, naleving en best practice-archiverings- en purgingpraktijken garanderen.

Wanneer u dit scenario automatiseert, kunt u zich er zeker van voelen dat:

- Naleving wordt gehandhaafd en het risico wordt verminderd.
- Taxonomie- en recordsbeheer wordt consistent en nauwkeurig toegepast.
- Inhoudsvolumes worden beheerd.
- Werknemers kunnen eenvoudig de juiste informatie vinden in de juiste context.

## <a name="scenario-capture-information-from-previously-inaccessible-documents"></a>Scenario: Gegevens uit eerder ontoegankelijke documenten vastleggen

De meeste organisaties hebben grote opslagplaatsen van juridische documenten, beleidsregels, contracten, HR-documenten en beheerrichtlijnen. Gebruik deze gegevensopslag om waardevolle informatie op te halen, zoals: projecten, sectoren, thema's, personen, geografische gebieden, en dergelijke.

Een HR-directeur moet bijvoorbeeld snel toegang hebben tot alle HR-documenten, inclusief cv's, HR-beleid en andere formulieren. En ze willen snel de benodigde informatie uit cv's en andere HR-gerelateerde documenten identificeren zonder de documenten handmatig te doorzenden. Ze zijn op zoek naar een oplossing waarmee ze snel de informatie kunnen vinden die ze nodig hebben, zonder dat ze handmatig duizenden cv's, HR-beleid en andere documentatie hoeven te bekijken die over verschillende sites kunnen worden verspreid.

Wanneer u dit scenario automatiseert, kunt u het volgende doen:

- Ontgrendel kennis van digitale inhoud.
- Classificeer HR-beleid, cv's, verkoopdocumenten, technische blauwdrukken, accountplannen en haal informatie op.
- Zoek snel de juiste informatie of het juiste document dat u zoekt.
- Krijg direct toegang tot de meest recente informatie.
- Zoektijden verminderen.

## <a name="scenario-improve-data-processing-to-provide-insights-and-analytics"></a>Scenario: Gegevensverwerking verbeteren om inzichten en analyses te bieden

Een farmaceutisch bedrijf kan bijvoorbeeld een SharePoint Syntex gebruiken om informatie op te halen uit FDA-documenten om vragen te beantwoorden die hun leiders hebben. Als u de antwoorden gemakkelijker toegankelijk hebt, kunt u minder tijd nodig hebben om deze antwoorden te geven en de beschikbaarheid van gegevens vergroten om nauwkeurigere antwoorden te genereren op leiderschapsvragen.

Een projectmanager moet bijvoorbeeld snel antwoorden geven op productgerelateerde vragen van mijn leidinggevende team. Ze moeten informatie en metrische gegevens met betrekking tot query's vinden in één samengevoegd dashboard. Ze zijn op zoek naar een oplossing die de informatie haalt die ze nodig hebben uit productlabels, productpamfletten en andere materialen en een geconsolideerd rapport genereert dat ze kunnen gebruiken bij het rapporteren aan hun leidinggevende team.

Wanneer u dit scenario automatiseert, kunt u het volgende doen:

- Verminder de tijd om antwoorden te produceren.
- De beschikbaarheid van gegevens vergroten.
- Geef nauwkeurigere antwoorden.

## <a name="scenario-automate-order-processing"></a>Scenario: Orderverwerking automatiseren

Met SharePoint Syntex kunt u de tijd van handmatige verwerking van klantorders verminderen. U kunt bijvoorbeeld orders van fax, e-mail of papier uploaden naar SharePoint door OCR-verwerking te gebruiken en vervolgens de metagegevens uit deze orders op te halen, zodat u deze kunt uitvoeren met behulp van geautomatiseerde processen.

Een supply chain manager wil bijvoorbeeld fouten beperken die worden veroorzaakt door handmatige gegevensinvoer. Ze willen handmatige controle en gegevensinvoer van binnenkomende klantorders (papier, fax of e-mail) voorkomen om fouten in hun bedrijfssystemen te beperken. Ze willen een oplossing waarmee AI- en machine learning-technieken worden toegepast om binnenkomende ordergegevens te valideren, kerngegevens op te halen en deze automatisch in hun ERP-systeem te plaatsen, voor orderafhandeling en afstemming.

Wanneer u dit scenario automatiseert, kunt u ervoor zorgen dat:

- Order- en verzendingsnauwkeurigheid neemt toe.
- Kosten of boetes die zijn gekoppeld aan order- of verzendingsfouten, worden verlaagd.
- Vertragingen in facturering of betalingen nemen af.
- De personeelskosten worden verlaagd.

## <a name="scenario-simplify-visa-renewal-process"></a>Scenario: Vereenvoudig het verlengingsproces voor visa

SharePoint Syntex kan u helpen herinneringen en verlengingen te automatiseren voor belangrijke contractgegevens. Een HR-directeur moet er bijvoorbeeld voor zorgen dat de visa van werknemers up-to-date zijn en/of op tijd worden verlengd. Ze willen mensen een eenvoudig en intuïtief proces bieden voor het bijwerken van hun Visa. Ze hebben een oplossing nodig die verlengingsdatums uit contracten haalt en werknemers automatisch herinneringen stuurt wanneer hun verlengingsdatum nadert.

Wanneer u dit scenario automatiseert, kunt u ervoor zorgen dat:

- De niveaus van niet-naleving worden verminderd.
- Het aantal handmatige herinneringen wordt verminderd.
- Het aantal boetes voor niet-naleving wordt verminderd.

## <a name="see-also"></a>Zie ook

[Microsoft SharePoint Syntex-acceptatie: Aan de slag](adoption-getstarted.md)