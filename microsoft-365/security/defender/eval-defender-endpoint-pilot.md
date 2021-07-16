---
title: Test Microsoft Defender voor Eindpunt, een pilot instellen, testmogelijkheden in evaluatie
description: Lees hoe u een pilot voor Microsoft Defender for Endpoint(MDE) kunt uitvoeren, inclusief het verifiëren van de testgroep en het proberen van mogelijkheden.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: d1efc37bd6412e441593dc9cf81296162f7fa754
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457740"
---
# <a name="pilot-microsoft-defender-for-endpoint"></a>Pilot Microsoft Defender voor Eindpunt

In dit artikel wordt u begeleid bij het uitvoeren van een pilot voor Microsoft Defender voor Eindpunt. 

Gebruik de volgende stappen om de pilot voor Microsoft Defender voor Eindpunt in te stellen en te configureren. 

![Stappen voor het toevoegen van Microsoft Defender voor identiteit aan de evaluatieomgeving van Defender](../../media/defender/m365-defender-endpoint-pilot-steps.png)

- Stap 1. Testgroep controleren
- Stap 2. Mogelijkheden uitproberen

Wanneer u Microsoft Defender voor Eindpunt test, kunt u ervoor kiezen om een paar apparaten aan te boord van de service voordat u uw hele organisatie onboardt.  

U kunt vervolgens mogelijkheden uitproberen die beschikbaar zijn, zoals het uitvoeren van aanvalssimulaties en zien hoe In Defender voor Eindpunt schadelijke activiteiten aan de oppervlakte brengen en u in staat stelt een efficiënte reactie uit te voeren. 

## <a name="step-1-verify-pilot-group"></a>Stap 1. Testgroep controleren
Nadat u de onboarding-stappen [](eval-defender-endpoint-enable-eval.md) hebt doorlopen die zijn beschreven in de sectie Evaluatie inschakelen, ziet u de apparaten ongeveer na een uur in de lijst Apparaatvoorraad. 

Wanneer u uw onboarded-apparaten ziet, kunt u verder gaan met het proberen van mogelijkheden. 

## <a name="step-2-try-out-capabilities"></a>Stap 2. Mogelijkheden uitproberen
Nu u klaar bent met het onboarden van bepaalde apparaten en hebt geverifieerd dat ze rapporteren aan de service, maakt u vertrouwd met het product door de krachtige mogelijkheden uit te proberen die direct vanuit het vak beschikbaar zijn.

Tijdens de pilot kunt u eenvoudig aan de slag met het proberen van een aantal functies om het product in actie te zien zonder complexe configuratiestappen te doorlopen.

Laten we beginnen door de dashboards te bekijken.

### <a name="view-the-device-inventory"></a>De inventaris van het apparaat weergeven
In de apparaatvoorraad ziet u de lijst met eindpunten, netwerkapparaten en IoT-apparaten in uw netwerk. Het biedt u niet alleen een weergave van de apparaten in uw netwerk, maar biedt ook uitgebreide informatie over deze apparaten, zoals domein, risiconiveau, besturingssysteemplatform en andere details voor eenvoudige identificatie van apparaten die het meest risico lopen.

### <a name="view-the-threat-and-vulnerability-management-dashboard"></a>Het dashboard Bedreiging en vulnerability management weergeven 
Bedreiging en vulnerability management helpt u zich te concentreren op de zwakke punten die het meest urgente en hoogste risico vormen voor de organisatie. Vanuit het dashboard krijgt u een overzicht op hoog niveau van de blootstellingsscore van de organisatie, Microsoft Secure Score voor apparaten, apparaatblootstellingsdistributie, topbeveiligingsaanbevelingen, de meest kwetsbare software, de belangrijkste herstelactiviteiten en de belangrijkste blootgestelde apparaatgegevens. 

### <a name="run-a-simulation"></a>Een simulatie uitvoeren
Microsoft Defender voor Eindpunt wordt geleverd met aanvalsscenario's ['Doe het zelf'](https://securitycenter.windows.com/tutorials) die u kunt uitvoeren op uw testapparaten.  Elk document bevat besturingssysteem- en toepassingsvereisten, evenals gedetailleerde instructies die specifiek zijn voor een aanvalsscenario. Deze scripts zijn veilig, gedocumenteerd en eenvoudig te gebruiken. Deze scenario's weerspiegelen de mogelijkheden van Defender voor eindpunten en helpen u bij het onderzoeken.

Als u een van de meegeleverde simulaties wilt uitvoeren, hebt u ten minste [één apparaat met onboarding nodig.](../defender-endpoint/onboard-configure.md)

1. Selecteer **in**  >  **Help-& zelfstudies** welke van de beschikbare aanvalsscenario's u wilt simuleren:

   - **Scenario 1: Document dropt backdoor-** simuleert de bezorging van een sociaal ontworpen lokmiddeldocument. Het document start een speciaal ontworpen backdoor die aanvallers controle geeft.

   - **Scenario 2: PowerShell-script in bestandsloze** aanval : simuleert een bestandsloze aanval die afhankelijk is van PowerShell, waarbij de surface reduction van de aanval wordt belicht en de detectie van schadelijke geheugenactiviteit op apparaten wordt gedetecteerd.

   - **Scenario 3: Geautomatiseerde reactie** op incidenten : activeert automatisch onderzoek, waarmee automatisch wordt gejaagd naar en herstelt van inbreukartefacten om de reactiecapaciteit voor incidenten te vergroten.

2. Download en lees het bijbehorende doorloopdocument dat bij het geselecteerde scenario is geleverd.

3. Download het simulatiebestand of kopieer het simulatiescript door naar  >  **Help-& navigeren.** U kunt ervoor kiezen om het bestand of script te downloaden op het testapparaat, maar dit is niet verplicht.

4. Voer het simulatiebestand of script uit op het testapparaat, zoals wordt geïnstrueerd in het doorloopdocument.

> [!NOTE]
> Simulatiebestanden of scripts bootsen aanvalsactiviteit na, maar zijn in feite goedaardig en kunnen het testapparaat niet schaden of in gevaar brengen.

## <a name="next-steps"></a>Volgende stappen
[Evaluatie van Microsoft Cloud App Security](eval-defender-mcas-overview.md)

Terug naar het overzicht voor [Microsoft Defender evalueren voor eindpunt](eval-defender-endpoint-overview.md)

Ga terug naar het overzicht voor [Evalueren en Microsoft 365 Defender](eval-overview.md)