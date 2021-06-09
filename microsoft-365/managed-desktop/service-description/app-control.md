---
title: App-bediening
description: App-beheer en vertrouwen gebruiken met toepassingen
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 6f5cc923b5a18b1f45dd186e88228db8c3a891cc
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841301"
---
# <a name="app-control"></a>App-bediening

App-besturingselement is een optionele beveiligingspraktijk in Microsoft Managed Desktop waarmee de uitvoering van code op clientapparaten wordt beperkt. Dit besturingselement beperkt het risico op malware of schadelijke scripts door te vereisen dat alleen code die is ondertekend door een door de klant goedgekeurde lijst met uitgevers, kan worden uitgevoerd. Er zijn veel beveiligingsvoordelen van dit besturingselement, maar het is voornamelijk bedoeld om gegevens en identiteit te beschermen tegen op de client gebaseerde exploits.

Microsoft Managed Desktop het beheer van beleidsregels voor app-beheer vereenvoudigt door een basisbeleid te maken dat basisscenario's voor productiviteit mogelijk maakt. U kunt het vertrouwen uitbreiden naar andere ondertekenaars die specifiek zijn voor de apps en scripts in uw omgeving. 


Elke beveiligingstechnologie vereist een evenwicht tussen gebruikerservaring, beveiliging en kosten. App-beheer vermindert de bedreiging van schadelijke software in uw omgeving, maar er zijn gevolgen voor de gebruiker en verdere acties voor uw IT-beheerder.

**Extra beveiliging:**

Apps of scripts die niet worden vertrouwd door het beleid voor app-beheer, worden geblokkeerd voor gebruik op apparaten.

**Uw extra verantwoordelijkheden:**

- U bent verantwoordelijk voor het testen van uw apps om te bepalen of deze worden geblokkeerd door het beleid voor toepassingsbeheer.
- Als een app is (of wordt) geblokkeerd, bent u verantwoordelijk voor het identificeren van de benodigde ondertekenaarsgegevens en het aanvragen van een wijziging via de beheerportal.

**Microsoft Managed Desktop verantwoordelijkheden:**

- Microsoft Managed Desktop het basisbeleid dat basisproducten van Microsoft in staat stelt, zoals M365-apps, Windows, Teams, OneDrive, en ga zo maar door.
- Microsoft Managed Desktop uw vertrouwde ondertekenaars in en implementeert het bijgewerkte beleid op uw apparaten.


## <a name="managing-trust-in-applications"></a>Vertrouwen in toepassingen beheren

Microsoft Managed Desktop een basisbeleid dat de basisonderdelen van Microsoft-technologieën vertrouwt. Vervolgens voegt *u* vertrouwen toe voor uw eigen toepassingen en scripts door u te informeren Microsoft Managed Desktop welke van de toepassingen u al vertrouwt.

### <a name="base-policy"></a>Basisbeleid

Microsoft Managed Desktop maakt en onderhoudt in samenwerking met microsoft-experts op het gebied van cyberbeveiliging een standaardbeleid waarmee de meeste apps via Microsoft Intune kunnen worden geïmplementeerd en gevaarlijke activiteiten, zoals het opstellen of uitvoeren van niet-vertrouwde bestanden, worden geblokkeerd.

Het basisbeleid gaat als volgt te werk om de uitvoering van software te beperken:

- Bestanden die worden uitgevoerd door beheerders, kunnen worden uitgevoerd.
- Bestanden op locaties die *niet* in door de gebruiker geschreven mappen staan, kunnen worden uitgevoerd.
- Bestanden worden ondertekend door een [vertrouwde ondertekenaar.](#signer-requests)
- De meeste bestanden die door Microsoft zijn ondertekend, worden uitgevoerd, maar sommige zijn geblokkeerd om acties met een hoog risico, zoals codecompilatie, te voorkomen.


Als een andere gebruiker dan een beheerder een app of script kan hebben toegevoegd aan een apparaat (dat wil zeggen dat deze zich in een door de gebruiker kan schrijven adreslijst) heeft, is het niet toegestaan om deze uit te voeren, tenzij dit al specifiek is toegestaan door een beheerder. Als een gebruiker wordt misleid om malware te installeren, als een beveiligingsprobleem in een app wordt uitgevoerd, probeert de gebruiker malware te installeren of als een gebruiker opzettelijk een niet-geautoriseerde app of script probeert uit te voeren, wordt de uitvoering van ons beleid gestopt.

### <a name="signer-requests"></a>Aanmeldingsaanvragen

U informeert ons welke apps worden geleverd door software-uitgevers die u vertrouwt door een *aanvraag voor een ondertekenaar in te dienen.* Op deze manier voegen we die vertrouwensgegevens toe aan het beleid voor basislijntoepassingsbeheer en staan we toe dat software die is ondertekend met het certificaat van die uitgever op uw apparaten kan worden uitgevoerd.

## <a name="audit-and-enforced-policies"></a>Controle- en afgedwongen beleidsregels

Microsoft Managed Desktop gebruikt twee Microsoft Intune beleidsregels voor app-beheer:

### <a name="audit-policy"></a>Controlebeleid
Met dit beleid worden logboeken gemaakt om vast te stellen of een app of script wordt geblokkeerd door het afgedwongen beleid. Controlebeleid dwingt geen regels voor app-beheer af en is bedoeld voor testdoeleinden om te bepalen of voor een toepassing een uitgevervrijstelling vereist is. Hiermee worden waarschuwingen (8003 of 8006 gebeurtenissen) in Gebeurtenisviewer vastgelegd in plaats van de uitvoering of installatie van opgegeven apps of scripts te blokkeren.

### <a name="enforced-policy"></a>Afgedwongen beleid
Met dit beleid worden niet-vertrouwde apps en scripts niet uitgevoerd en worden logboeken gemaakt wanneer een app of script wordt geblokkeerd. Afgedwongen beleid voorkomt dat standaardgebruikers apps of scripts uitvoeren die zijn opgeslagen in door gebruikers geschreven directories.

Apparaten in de groep Test hebben een auditbeleid toegepast, zodat u ze kunt gebruiken om te valideren of toepassingen problemen veroorzaken. Alle andere groepen (First, Fast en Broad) gebruiken een afgedwongen beleid, zodat gebruikers in die groepen geen niet-vertrouwde apps of scripts kunnen uitvoeren.







