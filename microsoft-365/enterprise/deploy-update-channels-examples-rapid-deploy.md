---
title: Voorbeeld van een brede implementatie voor de meest recente releases
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
ms.custom: ''
description: Hoe een organisatie die de meest recente release implementeert, kanalen gebruikt voor Windows 10- en Microsoft 365-apps.
ms.openlocfilehash: 29bda1651a83f0e043cf8a0d2a102c6c2e461bfd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919072"
---
# <a name="example-of-broad-deployment-for-the-latest-releases"></a>Voorbeeld van een brede implementatie voor de meest recente releases

Dit voorbeeld van een kanaalconfiguratie is voor een organisatie die gebruikmaakt van een snelle implementatie van de meest recente releases voor de volgende bedrijfsprioriteiten:

- Zorg voor een optimale bedrijfscontinuïteit met Microsoft-apps en -services.
- Maximaliseer de beveiliging van apparaten, services en gegevens met de nieuwste functies en fixes van Microsoft.
- Maximaliseer de productiviteit van gebruikers met de nieuwste functies van Microsoft.

Dit zijn de doelstellingen voor het vinden van de balans tussen een snelle productie-implementatie en voorbereidend onderzoek met een representatieve subset van gebruikers en apparaten om functioneel te valideren voorafgaand aan een brede implementatie.

Onze voorbeeldorganisatie heeft 5000 werknemers in kantoren in Europa, Afrika, Azië en Amerika. 70% van de werknemers maakt gebruik van Microsoft 365 E3 en de rest van de organisatie maakt gebruik van Microsoft 365 E5.

>[!Note]
>Dit voorbeeld is bedoeld om aan te geven hoe u implementatiefasen en -groepen kunt gebruiken. Dit is geschikt voor diverse typen organisaties met verschillende aantallen werknemers.
>

De IT-infrastructuur van dit bedrijf: 

- Is in hoge mate homogeen, waarbij Windows, Microsoft 365-apps en Microsoft-cloudservices voor 60% deel uitmaken van de geïnstalleerde basisapparatuur. Na een intensieve, meerjarige fase om de IT-infrastructuur te vereenvoudigen en te stroomlijnen, blijft een deel van de oudere systemen overeind.
- Wordt onderhouden door uiterst ervaren personeel en moet gebruikers en hun apparaten productief en veilig houden door Microsoft-releases als leidraad te nemen.

## <a name="deployment-and-update-stages"></a>Implementatie- en updatefasen

Deze voorbeeldorganisatie maakt gebruik van een tweetraps implementatieproces, uitgaande van een snelle implementatie van de mest recente release.

1. **Gebruik een voorbeeld- of pilot-implementatie:** gebruik early adopters, IT-personeel, gebruikers met representatieve configuraties en trainingspersoneel voor validatie en iteratie (herhaald gebruik). 

   De early adopters, IT-medewerkers, gebruikers met een representatieve configuratie kunnen de functionaliteit valideren met andere apps en op apparaten, voordat de nieuwe functies naar de rest van de organisatie worden uitgerold.

   Verandermanagers kunnen al kennismaken met de nieuwe functies voorafgaand aan de implementatie en kunnen berichtgeving en implementaties plannen.

   Trainingspersoneel kan voorafgaand aan de brede implementatie nieuwe, interne cursussen plannen of bestaande cursussen voor de nieuwe functies bijwerken.

2. **Productie-implementatie:** uitrol naar alle resterende gebruikers per regio, afdeling of andere implementatiemethode.

## <a name="deployment-configuration-for-windows-10"></a>Implementatieconfiguratie voor Windows 10

Het algehele doel is om een brede implementatie van de meest recente release van het Semi-Annual-kanaal uit te voeren. Dit gebeurt na validatie van de wijzigingen aan het Release-preview-kanaal door een groep representatieve gebruikers en hun apparaten.

Zie [Windows 10 deployment](/windows/deployment/) (Windows 10-implementatie) voor meer informatie over de implementatiemethoden en -strategieën van Windows 10.

| Fase | Kanaal | Implementatiegroep |
|:-------|:-------|:-----|
| Pilot |  **Release-preview-kanaal**  <ul><li>Doel: implementatie van functie-updates voor IT-medewerkers en early adopters voor validatie op representatieve apparaten en configuraties (talen, apps van derden). </li><li> Toestand: volledig compatibel en ondersteund voor commerciële klanten en niet in mindering gebracht op uw ondersteuningsovereenkomsten. </li></ul> | **Win10ReleasePreviewKanaal** (voorbeeldnaam) <br><br> Leden zijn groepen met: <ul><li> Windows-liefhebbers in alle afdelingen en locaties </li><li> Personeel met configuraties die moeten worden gevalideerd </li><li> IT-beheerders en IT-implementatiemedewerkers </li><li> Verandermanagers </li><li> Intern trainingspersoneel </li></ul> |
| Productie |  **Semi-Annual-kanaal**  <ul><li>Doel: een brede implementatie van de meest recente functie-updates voor de rest van de organisatie. </li><li> Toestand: volledig compatibel en ondersteund. </li></ul> | **Win10SemiAnnualChannel** (voorbeeldnaam) <br><br> De leden zijn alle gebruikers die niet in de groep Win10ReleasePreviewKanaal aanwezig zijn. |
||||

Deze organisatie maakt gebruik van de beste manier om de payload van het Release-preview-kanaal op dezelfde manier te implementeren als de releases van het Semi-Annual-kanaal, zoals Windows Update of Windows Server Update Services. Dezelfde beleidsregels moeten worden toegepast op beide kanaal-updates.

Doorlopend updateproces:

1. Wijzigingen aan het Release-preview-kanaal worden geïmplementeerd in de implementatiegroep Win10ReleasePreviewKanaal (voorbeeldnaam).
2. Leden van de groep Win10ReleasePreviewKanaal controleren of wijzigingen aan het Release-preview-kanaal functioneren voor de IT-implementatiemedewerkers, die feedback kunnen geven aan Microsoft en op de volgende wijzigingen aan het Release-preview-kanaal wachten voor aanvullende validatie.
3. Functiewijzigingen aan het Semi-Annual-kanaal worden geïmplementeerd in de implementatiegroep Win10SemiAnnualKanaal. 

>[!Note]
>Hoewel het Semi-Annual-kanaal het aanbevolen kanaal is, moet de IT-afdeling de eigen beheerhulpmiddelen gebruiken en bepalen wanneer de nieuwste release van het Semi-Annual-kanaal binnen de organisatie moet worden geïmplementeerd en vervolgens in fasen uitgerold.
>

## <a name="deployment-configuration-for-microsoft-365-apps"></a>Implementatieconfiguratie voor Microsoft 365-apps

Het algehele doel is om een brede implementatie van de meest recente release van het huidige kanaal uit te voeren. Dit gebeurt na validatie van de wijzigingen aan het Huidig kanaal (voorbeeld) door een groep representatieve gebruikers.

Zie [Microsoft 365 Apps deployment](/deployoffice/plan-office-365-proplus) (Implementatie van Microsoft 365-apps) voor meer informatie over de implementatiemethoden en -strategieën van Microsoft 365-apps.

| Fase | Kanaal | Implementatiegroep |
|:-------|:-------|:-----|
| Pilot |  **Huidig kanaal (voorbeeld)** <ul><li> Doel: {een groep representatieve gebruikers vooraf kennis laten maken met de nieuwe functies van Microsoft 365-apps} implementatie van functie-updates zodra deze worden getest met het Huidig kanaal (voorbeeld) en gereed zijn voor productie. </li><li> Toestand: volledig compatibel en ondersteund.</li><li> Hoe vaak: 2-3 keer per maand bijgewerkt. </li></ul> | **AppsHuidigKanaalVoorbeeld** (voorbeeldnaam) <br><br> Leden zijn groepen met: <ul><li> Office-apps in alle afdelingen en locaties </li><li> Personeel met configuraties die moeten worden gevalideerd </li><li> IT-beheerders en IT-implementatiemedewerkers </li><li> Verandermanagers </li><li> Intern trainingspersoneel </li></ul>|
| Productie | **Huidig kanaal** <ul><li> Doel: een brede implementatie van de meest recente functie-updates voor de rest van de organisatie. </li><li> Toestand: volledig compatibel en ondersteund. </li></ul> |  **AppsHuidigKanaal** (voorbeeldnaam) <br><br> Leden zijn alle gebruikers die niet in de groep AppsHuidigKanaalPreview aanwezig zijn. |
|||

Doorlopend updateproces:

1. Wijzigingen aan het Huidig kanaal (voorbeeld) worden geïmplementeerd in de implementatiegroep AppsHuidigKanaalVoorbeeld.
2. Leden van de groep AppsHuidigeKanaalVoorbeeld controleren of wijzigingen aan het Huidig kanaal (voorbeeld) functioneren voor de IT-implementatiemedewerkers, die feedback kunnen geven aan Microsoft en op de volgende wijzigingen aan het Huidig kanaal (voorbeeld) wachten voor aanvullende validatie.
3. Wijzigingen aan het Huidig kanaal worden geïmplementeerd in de implementatiegroep AppsHuidigKanaal. 

## <a name="visual-summary"></a>Visueel overzicht

Dit zijn de producten, hun kanalen en de implementatiegroepen die in deze voorbeeldorganisatie worden gebruikt. 

![Implementatiegroepen voor een brede implementatie van de meest recente releases](../media/deploy-update-channels-examples-rapid-deploy/group-summary.png)

## <a name="see-also"></a>Zie ook

[Voorbeeldconfiguraties voor het implementeren en bijwerken van kanalen](deploy-update-channels-examples.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Testlabrichtlijnen](m365-enterprise-test-lab-guides.md)