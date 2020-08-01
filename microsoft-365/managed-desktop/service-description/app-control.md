---
title: App-besturingselement
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: f11c7a4aa69c96232a33c565e7bf20d04b96d1f7
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529969"
---
# <a name="app-control"></a>App-besturingselement

App-besturingselement is een optionele beveiligingspraktijk in Microsoft Managed Desktop die de uitvoering van code op clientapparaten beperkt. Deze controle vermindert het risico op malware of kwaadaardige scripts door te eisen dat alleen code die is ondertekend door een door de klant goedgekeurde lijst met uitgevers kan worden uitgevoerd. Er zijn veel beveiligingsvoordelen van deze controle, maar het is vooral bedoeld om gegevens en identiteit te beschermen tegen client-gebaseerde exploits.

Microsoft Managed Desktop vereenvoudigt het beheer van app-beheerbeleid door een basisbeleid te maken dat kernproductiviteitsscenario's mogelijk maakt. U het vertrouwen uitbreiden naar andere ondertekenaars die specifiek zijn voor de apps en scripts in uw omgeving. 


Elke beveiligingstechnologie vereist een evenwicht tussen gebruikerservaring, beveiliging en kosten. App-controle vermindert de dreiging van schadelijke software in uw omgeving, maar er zijn gevolgen voor de eindgebruiker en aanvullende acties voor uw IT-beheerder.

**Extra beveiliging:**

Apps of scripts die niet worden vertrouwd door het app-besturingselementbeleid, worden geblokkeerd op apparaten.

**Uw bijkomende verantwoordelijkheden:**

- U bent verantwoordelijk voor het testen van uw apps om te bepalen of ze zouden worden geblokkeerd door het beleid voor toepassingscontrole.
- Als een app is (of zou worden) geblokkeerd, bent u verantwoordelijk voor het identificeren van de benodigde ondertekenaarsgegevens en het aanvragen van een wijziging via de admin-portal.

**Microsoft Managed Desktop-verantwoordelijkheden:**

- Microsoft Managed Desktop handhaaft het basisbeleid waarmee belangrijke Microsoft-producten zoals M365 Apps, Windows, Teams, OneDrive enzovoort kunnen worden ingeschakeld.
- Microsoft Managed Desktop voegt uw vertrouwde ondertekenaars in en implementeert het bijgewerkte beleid op uw apparaten.


## <a name="managing-trust-in-applications"></a>Vertrouwen in toepassingen beheren

Microsoft Managed Desktop beheert een basisbeleid dat de kerncomponenten van Microsoft-technologieën vertrouwt. Vervolgens *voegt u* vertrouwen toe voor uw eigen toepassingen en scripts door Microsoft Managed Desktop te informeren welke van hen u al vertrouwt.

### <a name="base-policy"></a>Basisbeleid

Microsoft Managed Desktop maakt en onderhoudt in samenwerking met microsoft cybersecurity-experts een standaardbeleid waarmee de meeste apps kunnen worden geïmplementeerd via Microsoft Intune, terwijl gevaarlijke activiteiten zoals het verzamelen van code of de uitvoering van niet-vertrouwde bestanden worden geblokkeerd.

Het basisbeleid hanteert de volgende benadering om de uitvoering van software te beperken:

- Bestanden die door beheerders worden uitgevoerd, mogen worden uitgevoerd.
- Bestanden op locaties die *zich niet* in door de gebruiker beschrijfbare mappen bevinden, mogen worden uitgevoerd.
- Bestanden worden ondertekend door een [vertrouwde ondertekenaar](#signer-requests).
- De meeste bestanden die door Microsoft zijn ondertekend, worden uitgevoerd, maar sommige worden geblokkeerd om acties met een hoog risico, zoals het verzamelen van code, te voorkomen.


Als een andere gebruiker dan een beheerder een app of script aan een apparaat had kunnen toevoegen (dat wil zeggen in een door de gebruiker geschreven map), staan we deze niet toe, tenzij dit al specifiek is toegestaan door een beheerder. Als een gebruiker wordt misleid om malware te proberen te installeren, als een kwetsbaarheid in een app die de gebruiker uitvoert pogingen om malware te installeren of als een gebruiker opzettelijk een onbevoegde app of script probeert uit te voeren, wordt de uitvoering gestopt.

### <a name="signer-requests"></a>Ondertekenaarsverzoeken

U informeert ons welke apps worden geleverd door softwareleveranciers die u vertrouwt door een *ondertekenaarverzoek in te dienen.* Op die manier voegen we die vertrouwensinformatie toe aan het beleid voor toepassingsbeheer voor basislijn en laten we alle software die is ondertekend met het certificaat van die uitgever, op uw apparaten worden uitgevoerd.

## <a name="audit-and-enforced-policies"></a>Controle- en afgedwongenbeleid

Microsoft Managed Desktop gebruikt twee Microsoft Intune-beleidsregels om app-controle te bieden:

### <a name="audit-policy"></a>Controlebeleid
Met dit beleid worden logboeken gemaakt om vast te leggen of een app of script wordt geblokkeerd door het beleid afgedwongen. Controlebeleid dwingt geen regels voor app-beheer af en is bedoeld voor testdoeleinden om te bepalen of een toepassing een vrijstelling van uitgevers vereist. Het registreert waarschuwingen (8003 of 8006 gebeurtenissen) in Logboeken in plaats van het blokkeren van de uitvoering of installatie van bepaalde apps of script.

### <a name="enforced-policy"></a>Afgedwongen beleid
Met dit beleid worden niet-vertrouwde apps en scripts niet-vertrouwd en maakt u logboeken wanneer een app of script wordt geblokkeerd. Afdwingen beleid voorkomen dat standaardgebruikers apps of scripts uitvoeren die zijn opgeslagen in door gebruikers beschrijfbare mappen.

Apparaten in de groep Testen hebben een controlebeleid toegepast, zodat u ze gebruiken om te valideren of toepassingen problemen zullen veroorzaken. Alle andere groepen (First, Fast en Broad) gebruiken een afgedwongen beleid, zodat eindgebruikers in die groepen geen niet-vertrouwde apps of scripts kunnen uitvoeren.







