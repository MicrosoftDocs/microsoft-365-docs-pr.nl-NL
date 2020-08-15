---
title: Microsoft 365 bewaken en testen Tenant grenzen
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
description: In dit artikel leest u hoe Microsoft continu de grenzen van de tenants controleert en test voor Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cd0aa3f88de3a8e22ef67283b20ecfae9959cb05
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688914"
---
# <a name="monitoring-and-testing-tenant-boundaries"></a>Tenant grenzen controleren en testen

Microsoft continu wordt gecontroleerd en expliciet getest op zwakke plekken en kwetsbaarheden in Tenant grenzen, waaronder toezicht voor indringers, machtigings pogingen en bronnen Starvation. We gebruiken ook meerdere interne systemen voor voortdurend monitor voor ongeschikt Resourcegebruik, dat wil zeggen, een ingebouwde beperking.

Microsoft 365 heeft interne monitoring systemen die continu controleren op fouten en geautomatiseerde herstel problemen wanneer de fout wordt gedetecteerd. Microsoft 365-systemen analyseren van afwijkingen in het servicegedrag en initiëren automatisch herstelprocessen die in het systeem zijn ingebouwd. In Microsoft 365 wordt ook buiten gebruik gebruikgemaakt van de bewaking van de bewaking vanaf meerdere locaties van vertrouwde services van derden (voor onafhankelijke SLA-verificatie) en onze eigen datacenters voor het verhogen van waarschuwingen. Voor diagnostische gegevens hebben we uitgebreid logboekregistratie, controle en tracering. Met granulaire tracering en controle kunt u problemen isoleren en de analyse van basis oorzaken versnellen en effectief uitvoeren.

Hoewel Microsoft 365 geautomatiseerde herstelacties bevat, zijn Microsoft-aanbieders van technici van Microsoft niet altijd beschikbaar om alle beveiligings-en kwaliteits verbeteringen te onderzoeken, en achteraf beoordelingen te ondernemen. Dit team omvat ondersteuningstechnici, productontwikkelaars, programma managers, product beheerders en senior leiderschap. Onze on-call-medewerkers zorgen voor een juiste back-up en kunnen vaak herstelacties automatiseren, zodat u de volgende keer een gebeurtenis kunt herstellen.

Microsoft voert een uitgebreide bespreking van de nabespreking uit telkens wanneer een Microsoft 365-beveiligingsincident zich voordoet, ongeacht de omvang van de invloed. Een beoordeling na de bespreking omvat een analyse van wat er is gebeurd, wat we hebben gereageerd en wat we in de toekomst tegen soortgelijke incidenten kunnen voorkomen. Met het oog op transparantie en verantwoording delen we de bespreking van het post-incident voor alle belangrijke service-incidenten met betrokken klanten. Zie [Office 365 Security Incident Management](https://aka.ms/Office365SIM)voor specifieke informatie.

## <a name="assume-breach-methodology"></a>De methodologie van de overtreding aannemen

Op basis van gedetailleerde analyses van beveiligings trends is Microsoft in Microsoft geïnvesteerd en markeert u de noodzaak van extra investeringen voor heractieve beveiligings processen en technologieën die aandacht vestigen op de detectie en respons van de opkomende bedreigingen, en niet alleen voor het voorkomen van deze bedreigingen. Vanwege wijzigingen in de instellingen voor de scherpte en de grondige beveiliging, heeft Microsoft de beveiligingsstrategie verfijnd buiten de gang van een betere bescherming tegen een betere uittreding van de schending wanneer ze zich voordoen: een strategie waarbij belangrijke beveiligingsgebeurtenissen worden beschouwd als belangrijk, maar wanneer.

Hoewel Microsoft [ervan uitgaat dat de overtreding](https://www.microsoft.com/TrustCenter/Security/default.aspx) van Microsoft niet voldoende is, zijn veel klanten niet op de hoogte van het werk dat achter de schermen wordt uitgevoerd om de Microsoft-Cloud te versterken. Ervan uitgaan dat schending een Mindset is dat beveiligings investeringen, ontwerpbeslissingen en functionele beveiligingsmaatregelen begeleidt. Verstel de limieten voor de vertrouwensrelaties in toepassingen, services, identiteiten en netwerken ervan uit dat deze allemaal, intern en extern, als onveilig en extern zijn besmet. Hoewel de strategie voor de schending ervan niet is geboren tegen een daadwerkelijke schending van een Microsoft Enterprise-of cloudservice, was het een verantwoording dat veel organisaties, in de branche, al proberen te voorkomen. Aangezien het voorkomen van schending een essentieel onderdeel is van de activiteiten van een organisatie, moeten deze werkwijzen continu worden getest en uitgebreid om moderne adversaries en geavanceerde duurzame bedreigingen te bevorderen. Een organisatie die een schending voorbereidt, moet eerst krachtig, herhaalbare en uitvoerig geteste beveiligingsprocedures maken en onderhouden.

Bij het voorkomen dat beveiligings processen van schending, zoals bedreigings modellering, code beoordelingen en beveiliging van beveiligings tests zeer nuttig zijn in een deel van de [levenscyclus](https://www.microsoft.com/securityengineering/sdl/)van de veiligheid, wordt uitgegaan van schending van talrijke voordelen voor het uitoefenen van een overtreding en het meten van nieuwe functies in het geval van een schending.

Bij Microsoft hebben we ons opgezet voor het uitvoeren van IT-begeleidende oorlogs games en het testen van live site penetratie voor ons beveiligingsantwoord, met het doel om de detectie en de antwoord mogelijkheden te verbeteren. Microsoft simuleert regelmatig de schendingen van onze wereld, voert voortdurende beveiligings monitoring uit en oefent toezicht beveiliging van beveiligingsincidenten om de beveiliging van Microsoft 365, Azure en andere Microsoft-cloudservices te valideren en te verbeteren.

Microsoft voert een overtredings beveiligingsstrategie uit van twee kern groepen:
- Rode teams (hackers)
- Blauwe teams (verdedigingers)

Microsoft Azure en Microsoft 365-medewerkers afzonderlijke fulltime teams en blauw teams.

De aanpak van de zogenaamde '[rode teams](https://go.microsoft.com/fwlink/?linkid=518599)' is de aanpak voor het testen van Azure-en microsoft 365-systemen en-activiteiten met behulp van dezelfde tactiek, technieken en procedures als echte adversaries, op basis van de live productie-infrastructuur, zonder de Foreknowledge van de engineering-of bewerkings teams. Hiermee kunt u de detectie en antwoord mogelijkheden van Microsoft testen en helpt u bij het identificeren van beveiligingsproblemen, configuratiefouten, ongeldige hypothesen en andere beveiligingskwesties op een gecontroleerde manier. Elke rode schending van het team wordt gevolgd door volledige informatie tussen teams om hiaten, informatie over de resultaten te identificeren en de reactie op een schending te verbeteren.

**Opmerking**: er worden geen klantgegevens op de proef gericht tijdens een rode team of live site penetratie tests. De tests bevinden zich in Microsoft 365 en Azure-infrastructuur en-platforms, evenals de eigen tenants, toepassingen en gegevens van Microsoft. Klant tenants, toepassingen en inhoud die worden gehost in Microsoft 365 of Azure zijn nooit bedoeld.

## <a name="red-teams"></a>Rode teams

Het rode team is een groep fulltime personeel in Microsoft die de infrastructuur van Microsoft, platform en eigen tenants en toepassingen van Microsoft schendt. Ze zijn de gespecialiseerde Adversary (een groep ethische hackers) met gerichte en permanente aanvallen van Online Services (infrastructuur, platforms en toepassingen van de Microsoft-app, maar geen klanten of inhoud van het einde van de klant).

De rol van het rode team is een aanval en een penetratie omgeving met dezelfde stappen als een Adversary:
 
![Strijdings fasen](../media/office-365-isolation-breach-stages.png)

Met andere functies proberen de rode teams nadrukkelijk te overgaan op de isolatie grenzen van de Tenant om fouten of hiaten te vinden in onze isolatie-ontwerp.

## <a name="blue-teams"></a>Blauwe teams

Het blauwe team is samengesteld uit een gespecialiseerde reeks beveiligings beantwoorders of-leden van gedurende het antwoord op de beveiligingsincident, de technische dienst en de operationele organisatie. Ongeacht hun opvullen zijn ze onafhankelijk en werken ze los van het rode team. Het blauwe team volgt de opgezette beveiligings processen en gebruikt de nieuwste hulpprogramma's en technologieën voor het detecteren en beantwoorden van aanvallen en penetratie. Net als bij een aanval via de wereld, dan is het blauwe team niet bekend wanneer of de manier waarop de werking van het rode team plaatsvindt of welke methoden kunnen worden gebruikt. Hun taak, of het nu een rode team aanval is of een echte Assault, is het detecteren en beantwoorden van alle beveiligingsincidenten. Om die reden is het blauwe team continu voortdurend on-call en moet reageren op een rood team, op dezelfde manier als voor elke andere schending.

Wanneer een Adversary, zoals een rood team, een omgeving heeft geschonden, moet het blauwe team:

- Gegevens van de Adversary verzamelen
- Detectie van de bewijzen als aanwijzing van de compromissen
- Waarschuwen voor de juiste technische en bewerkings team (en)
- Sortering de waarschuwingen om na te gaan of de persoon nader onderzoek rechtvaardigt
- De context van de omgeving verzamelen om de schending te bereiken
- Een herstelabonnement maken om de Adversary te kunnen bevatten of verwijderen
- Voer het herstelplan uit en herstel de schending van de schending

Deze stappen vormen de reactie van beveiligingsincidenten die parallel worden uitgevoerd met de Adversary, zoals hieronder wordt weergegeven:
 
![Antwoord fasen voor de schending](../media/office-365-isolation-breach-response-stages.png)

Met een rode team aanval kan de mogelijkheid van het blauwe team de mogelijkheid bieden te bieden de mogelijkheid van end-to-end aanvallen te ontdekken en erop te reageren. Het belangrijkste is dat u het antwoord op een geoefend beveiligingsincident moet beantwoorden voordat u een echte schending krijgt. Daarnaast is het blauw team, aangezien het rode team niet schendt, de situatie bemoeilijkt te verbeteren, wat waardevol kan zijn bij het werken met toekomstige overtredingen (zowel van het rode team als een andere Adversary). Tijdens het detecteren en beantwoorden wordt het blauwe team veroorzaakte informatie over een actie en een verhoging van de beschikbaarheid in de werkelijke voorwaarden van de omgeving (en) die ze proberen te verdedigen. Dit gebeurt meestal via gegevensanalyse en Forensics, uitgevoerd door het blauwe team, wanneer ze reageren op rode team aanvallen en door risico indicatoren te creëren, zoals indicatoren van compromissen. Wanneer het rode team hiaten in het beveiligings verhaal identificeert, kunt u met blauwe teams hiaten identificeren in hun vermogen om te ontdekken en te reageren. Daarnaast kan het blauwe team, aangezien de rode aanvallen van de professionele teams, nauwkeurig op hun vermogen, of tegen de mogelijkheid, voor het afhandelen van vastgestelde en permanente adversaries. Tot slot is het rode team overtredingen de enige voorbereiding en impact van ons schendende antwoord meet.
