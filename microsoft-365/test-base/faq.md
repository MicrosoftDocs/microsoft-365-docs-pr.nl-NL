---
title: Veelgestelde vragen over testbasis
description: Veelgestelde vragen bekijken
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 9d24ecb807e60733471be60353d12789f19be1b4
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322925"
---
# <a name="test-base-faq"></a>Veelgestelde vragen over testbasis

**V: Hoe verzenden we onze pakketten naar testbasisteam?**

**A:** Verzend uw pakketten rechtstreeks naar de Test Base-omgeving via onze self-serve portal.

Als u uw toepassingspakket wilt verzenden, gaat u naar de [Azure Portal](https://www.aka.ms/testbaseportal "Startpagina testbasis") en uploadt u een geritste map met binaries, afhankelijkheden en testscripts van uw toepassing via het dashboard van de self-serve Test Base-portal. 

Raadpleeg de onboarding-gebruikershandleiding voor meer informatie of neem contact op met ons team voor <testbasepreview@microsoft.com> hulp en meer informatie.

**V: Wat zijn out-of-box (OOB)-tests?**

**A:** Out-of-box (OOB)-tests zijn gestandaardiseerd, standaard worden test uitgevoerd waarbij toepassingspakketten zijn geïnstalleerd, dertig (30) keer zijn gestart en gesloten en vervolgens worden verwijderd. 

De pakketten die voor Test Base zijn gemaakt, hebben de volgende testscripts: installeren, starten, sluiten en eventueel het script verwijderen. 

De out-of-box -tests (OOB) bieden u gestandaardiseerde telemetrie in uw toepassing om te vergelijken tussen Windows builds.

**V: Kunnen we tests indienen buiten de out-of-box-tests (installeren, starten, sluiten, testscripts verwijderen)?**

**A:** Ja, klanten kunnen ook toepassingspakketten uploaden voor **functionele tests** via het dashboard van de self-serve portal.
**Functionele tests** zijn tests waarmee klanten hun scripts kunnen uitvoeren om aangepaste functionaliteit uit te voeren op hun toepassing.


## <a name="testing"></a>Testen

**V: Ondersteunt u functionele tests?**

**A:** Ja, Test Base ondersteunt functionele tests. Functionele tests zijn tests waarmee onze klanten hun scripts kunnen uitvoeren om aangepaste functionaliteit voor hun toepassing uit te voeren. 

Als u uw toepassingspakket wilt indienen voor functionele tests, uploadt u de geritste map met de binaries, afhankelijkheden en testscripts van uw toepassing via ons self-serve portaldashboard. 

Raadpleeg de onboarding-gebruikershandleiding voor meer informatie of neem contact op met ons team voor <testbasepreview@microsoft.com> hulp en meer informatie.

**V: Hoe gaat Test Base om met onze testgegevens?**

**A:** Test Base verzamelt en beheert uw testgegevens veilig in de Azure-omgeving. 

**V: Kan Test Base onze geautomatiseerde tests ondersteunen?**

Ja, Test Base ondersteunt geautomatiseerde tests, maar op dit moment ondersteunen we geen handmatige tests vanwege servicemogelijkheden.

**V: Welke talen en frameworks van geautomatiseerde tests ondersteunt u?**

**A:** We ondersteunen alle talen en frameworks. We roepen alle scripts aan via PowerShell. 

U moet ook de afhankelijke binaries van het vereiste framework verstrekken (uploaden).

**V: Hoe snel levert Test Base testresultaten op?**

**A:** Voor elke test die we uitvoeren met de pre-release builds, leveren we binnen 48 uur resultaten op uw [Azure Portal-dashboard.](https://www.aka.ms/testbaseportal "Startpagina testbasis")

**V: Kunt u opnieuw opstarten na de installatie?**

**A:** Ja, ons proces ondersteunt opnieuw opstarten na de installatie. Selecteer deze optie in de vervolgkeuzelijst 'Optionele  instellingen' wanneer u taken in de onboarding-portal instelt.

Voor OOB-tests (Out-of-box) kunt u opgeven of een herstart nodig is voor het _installatiescript._

![Afbeelding opnieuw opstarten](Media/reboot.png)

Voor functionele tests kunt u opgeven of een herstart vereist is voor elk script dat wordt toegevoegd.

![Functionele tests selecteren](Media/functionalreboot.png)

**V: Welke Windows versies ondersteunt u?**

**A:** Momenteel ondersteunen we Windows 10 clients, Windows Server 2016, Windows Server 2016 Core-versie, Windows Server 2019 en Windows Server 2019 Core-versie.

**V: Wat is het verschil tussen beveiligingsupdatetests en functieupdatetests?**

**A:** Voor beveiligingsupdatetests testen we de maandelijkse **<ins>pre-release</ins>** beveiligingsupdates op Windows die zijn gericht op het altijd beveiligen en beveiligen van onze gebruikers. Voor de onderdelenupdatetests wordt getest op de tweejaarlijkse **<ins>pre-releasefunctieupdates</ins>** die nieuwe functies en mogelijkheden introduceren op Windows.

## <a name="debugging-options"></a>Opties voor debuggen

**V: Krijgen we toegang tot virtuele machines (VM's) in geval van fouten? Wat deelt Test Base?**

**A:** Als de service compatibel is en de pre-release-updates veilig zijn, heeft alleen Microsoft toegang tot de VM's. Klanten kunnen echter testresultaten en andere testmetrische gegevens bekijken op hun portaldashboard, zoals crash- en hangsignalen, betrouwbaarheidsgegevens, geheugen- en CPU-gebruik, enzovoort. We genereren en bieden ook logboeken van test uitgevoerd op het dashboard voor download en verdere analyse. 

We kunnen ook geheugendumps bieden voor crashdebugging als dat nodig is.

**V: Als er tijdens het testen problemen zijn gevonden, wat zijn de volgende stappen om deze problemen op te lossen?**

**A:** Het Test Base-team voert een eerste triageproces uit om de hoofdoorzaak van de fout te bepalen. Afhankelijk van onze bevindingen worden we doorgeleid naar de klant of interne teams binnen Microsoft voor foutopsporing. 

We werken altijd nauw samen met onze klanten in gezamenlijke herstel om eventuele problemen op te lossen. 

**V: Houdt Microsoft de release van de beveiligingspatch in stand totdat het probleem is opgelost? Welke alternatieve resoluties zijn beschikbaar?**

**A:** Het doel van Test Base is ervoor te zorgen dat onze gezamenlijke eindklanten geen problemen hebben. We zullen hard werken met Softwareleveranciers om eventuele problemen vóór de release op te lossen, maar voor het geval de oplossing niet haalbaar is, hebben we andere oplossingen, zoals shims en blokken.

## <a name="miscellaneous"></a>Diversen

**V: Hoe werkt de service met een on-prem-server?**

**A:** We bieden momenteel geen ondersteuning voor on-prem-servers. Als de server echter HTTP-eindpunt aan de dag leggen, kunnen we er verbinding mee maken via internet.

**V: Wie de VM's host?**

**A:** Microsoft voor deze service stelt de VM in en neemt de belasting van de klant over.

**V: Biedt deze service ondersteuning voor web-, mobiele of desktoptoepassingen?**

**A:** Op dit moment ligt onze focus op desktoptoepassingen, maar we hebben plannen om webtoepassingen in de toekomst aan te nemen, maar we ondersteunen op dit moment geen mobiele toepassingen.

**V: Wat is het verschil tussen Test Base en SUVP?**

**A:** Het grootste verschil tussen Test Base en SUVP is dat onze partners hun toepassingen aan boord van de Test Base Azure-omgeving voor validatie uitvoeren tegen pre-releaseupdates in plaats van de tests zelf uit te voeren. 

Naast het testen van beveiligingsupdates die vooraf zijn uitgebracht, ondersteunen we het testen van functieupdates voor de pre-release op ons platform. We hebben veel andere soorten updates en besturingssysteemtests op onze routekaart.

**V: Zijn er kosten aan de service gekoppeld?**

**A:** De Test Base-service is gratis voor gebruikers tot algemene beschikbaarheid (GA). Op dat moment kondigen we een kostenstructuur aan die van kracht wordt voor alle klanten. 

**V: Hoe kan ik feedback geven over Test Base?**

**A:** Als u uw feedback over Test Base wilt delen, selecteert u het **pictogram Feedback** linksonder in de portal. Voeg een schermafbeelding toe bij uw inzending om Microsoft te helpen uw feedback beter te begrijpen. 

U kunt ook productsuggesties indienen en andere ideeën upvote op <testbasepreview@microsoft.com> .
