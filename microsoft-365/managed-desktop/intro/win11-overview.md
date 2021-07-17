---
title: Microsoft Managed Desktop en Windows 11
description: Hoe en wanneer Windows 11 beschikbaar is in de service
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1c5f2a7f60097bb02cb11eaabd66cad88657c505
ms.sourcegitcommit: 2abc6bf9939b14a427647e88f319dbb70de49ca6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/16/2021
ms.locfileid: "53457978"
---
# <a name="microsoft-managed-desktop-and-windows-11"></a>Microsoft Managed Desktop en Windows 11

Na de aankondiging van Windows 11 bent u mogelijk begonnen met het plannen van Windows 11 migraties als onderdeel van uw inspanningen om Windows 10 apparaten up-to-date te houden. In dit artikel worden belangrijke aandachtspunten beschreven en Microsoft Managed Desktop soepele overgangen in uw omgevingen ondersteunen. Zie voor meer Windows 11 zelf [Windows 11 overzicht.](/windows/whats-new/windows-11)

Zie Windows Voorbeeld en test Windows [Microsoft Managed Desktop 11](../working-with-managed-desktop/test-win11-mmd.md)met Microsoft Managed Desktop.

## <a name="timeline-for-windows-11"></a>Tijdlijn voor Windows 11

Windows 11 preview-builds zijn beschikbaar vanaf 28 juni 2021 tot en [met Windows Insider Program.](/windows-insider/) We verwachten dat release-builds algemeen beschikbaar zijn tegen het einde van kalenderjaar 2021.

U kunt preview-builds installeren op apparaten, ongeacht of ze worden beheerd door Microsoft Managed Desktop of niet. We blijven ondersteuning Windows 10 ondersteuning totdat het einde van de ondersteuning is bereikt.

Wanneer Windows 11 algemeen beschikbaar is, worden er meer validatietests uitgevoerd. We verwachten dat januari 2022 de snelste zal zijn die Windows 11 wordt aangeboden aan Microsoft Managed Desktop productieapparaten via onze standaardimplementatiegroepen.

We raadplegen en adviseren beheerders om migratieplannen voor elke tenant te ontwikkelen en te implementeren op basis van technische gereedheid en uw zakelijke overwegingen.

## <a name="assessing-pre-release-versions-of-windows-11"></a>Evaluatie van pre-releaseversies van Windows 11

Meer dan 95% van Microsoft Managed Desktop apparaten komen in aanmerking voor Windows 11, dus misschien wilt u een voorbeeld van de upgrade bekijken op testapparaten vóór de productie-implementatie. Zie voor meer Windows 11 systeemvereisten [Windows 11 vereisten.](/windows/whats-new/windows-11-requirements) U kunt gegevens over de geschiktheidsstatus van uw apparaten op Microsoft Managed Desktop.

Voor Microsoft Managed Desktop apparaten kunt u een aanvraag indienen om testapparaten toe te voegen aan de groep Moderne Windows **\[ \] 11 pre-release testapparaten.** Deze groep ontvangt Windows 11 preview-builds samen met een Microsoft Managed Desktop basislijnconfiguratie. Microsoft Managed Desktop de releasefrequentie van Windows 11 preview-builds niet beheert, zodat leden van deze apparaatgroep mogelijk vaker updates ontvangen dan Windows 10 apparaatgroepen.

Voor uw apparaten die niet worden beheerd door Microsoft Managed Desktop, kunt u deelnemen aan het [Windows Insider-programma](/windows-insider/) om preview-versies te downloaden en hulp te krijgen bij het implementeren van Windows 11 zelf. Als u apparaten hebt met Windows 11 pre-release builds en deze later inschrijft in Microsoft Managed Desktop, worden ze niet terug naar Windows 10.

## <a name="support-for-pre-release-windows-11-devices"></a>Ondersteuning voor pre-release Windows 11 apparaten

De pre-release builds van elk platform bevatten naar verwachting gebreken en compatibiliteitsproblemen met toepassingen die kunnen worden geïdentificeerd en opgelost vóór de algemene beschikbaarheid. Daarom beschouwen we apparaten met pre-release builds van Windows 11 als testapparaten, maar we controleren ze samen met de rest van de omgeving op beveiligingsrisico's en ze zijn onderworpen aan dezelfde beveiligingswaarschuwingsreactie als andere Microsoft Managed Desktop-apparaten.

Omdat we u helpen bij het migreren naar Windows 11 terwijl u productief blijft, raden we u aan fouten te melden die u ondervindt bij pre-release builds. We geven prioriteit aan fouten die de productiviteit van gebruikers blokkeren bij een brede implementatie van Windows 11 en defecten die de productiviteit van gebruikers op Windows 10 blokkeren.

## <a name="testing-application-compatibility"></a>Compatibiliteit met toepassingen testen

Toepassingscompatibiliteit is een van de meest voorkomende problemen in een platformmigratie vanwege het potentieel voor productiviteitsonderbrekingen. We gebruiken verschillende proactieve en reactieve metingen om u te helpen vertrouwen te hebben in soepele app-overgangen naar Windows 11.

### <a name="proactive-measures"></a>Proactieve maatregelen

**Veelgebruikte apps:** Microsoft test de meest voorkomende bedrijfstoepassingen en -suites die zijn geïmplementeerd op builds van Windows 11. We werken samen met externe software-uitgevers en interne productteams om eventuele problemen op te lossen die tijdens het testen zijn ontdekt. Zie de blog Toepassingscompatibiliteit voor meer [informatie](https://blogs.windows.com/windowsexperience/2019/01/15/application-compatibility-in-the-windows-ecosystem/)over onze proactieve compatibiliteitstests.

**Line-of-business-apps:** [Test Base](https://www.microsoft.com/testbase) is een resource die app-uitgevers en IT-beheerders kunnen gebruiken om apps en test cases voor Microsoft in te dienen op een virtuele machine met Windows 11 builds in een beveiligde Azure-omgeving. Resultaten, testinzichten en regressieanalyses voor elke testuitvoering zijn beschikbaar op een persoonlijke Azure-portal. Microsoft Managed Desktop helpt u prioriteit te geven aan uw line-of-business-apps voor validatie op basis van app-gebruiks- en betrouwbaarheidsgegevens. Zie [TestBasis](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/test-base-for-microsoft-365-microsoft-ignite-2021-updates/ba-p/2185566)voor Microsoft 365.

### <a name="reactive-measures"></a>Reactieve metingen

Als u problemen ondervindt met de compatibiliteit van apps in test- of productieomgevingen, kunt u ondersteuning krijgen door [App Assure](/fasttrack/products-and-capabilities) of FastTrack in te stellen. Voor Windows 11 omvat dit alle functies met Office, Microsoft Edge en Teams toepassingen die worden uitgevoerd op de meest recente versies van het besturingssysteem. App Assure schakelt app-uitgevers rechtstreeks in om problemen met de compatibiliteit van apps te bepalen en op te lossen.