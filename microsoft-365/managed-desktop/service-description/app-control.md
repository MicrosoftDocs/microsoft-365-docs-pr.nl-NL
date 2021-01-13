---
title: App-bediening
description: Het besturingselement voor apps en vertrouwen met toepassingen gebruiken
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

App-besturingselement is een optionele beveiligingsprocedure in Microsoft Managed Desktop waarmee de uitvoering van code op clientapparaten wordt beperkt. Dit besturingselement verkleint het risico van malware of kwaadaardige scripts door aan te geven dat alleen code die is ondertekend door een door de klant goedgekeurde lijst met uitgevers, kan worden uitgevoerd. Dit besturingselement biedt veel beveiligingsvoordelen, maar dit is vooral bedoeld om gegevens en identiteit te beschermen tegen exploits op basis van client.

Microsoft Managed Desktop vergemakkelijkt het beheer van app-beheerbeleidsregels door een basisbeleid te maken dat scenario's voor kern productiviteit mogelijk maakt. U kunt een vertrouwensrelatie uitbreiden naar andere ondertekeners die specifiek zijn voor de apps en scripts in uw omgeving. 


Voor elke beveiligingstechnologie is een evenwicht tussen de gebruikerservaring, beveiliging en kosten vereist. Met app-beheer wordt de bedreiging van schadelijke software in uw omgeving beperkt, maar er zijn gevolgen voor de gebruiker en verdere acties voor uw IT-beheerder.

**Extra beveiliging:**

Apps of scripts die niet worden vertrouwd door het app-besturings beleid, worden geblokkeerd voor de uitvoering van apparaten.

**Uw nieuwe verantwoordelijkheden:**

- U bent verantwoordelijk voor het testen van uw apps om te bepalen of deze worden geblokkeerd door het Toepassingsbeheerbeleid.
- Als een app (of zou zijn) wordt geblokkeerd, moet u verantwoordelijk zijn voor het identificeren van de benodigde details van de ondertekenaar en het aanvragen van een wijziging via de beheerportal.

**Microsoft beheerde bureaublad verantwoordelijkheden:**

- Microsoft Managed Desktop onderhoudt het basisbeleid voor het inschakelen van belangrijkste Microsoft-producten zoals M365-apps, Windows, teams, OneDrive enzovoort.
- Microsoft Managed Desktop voegt uw vertrouwde ondertekeners in en implementeert het bijgewerkte beleid op uw apparaten.


## <a name="managing-trust-in-applications"></a>Vertrouwen in toepassingen beheren

Microsoft Managed Desktop met een Basisbeleid dat de kernonderdelen van Microsoft-technologieën vertrouwt. U voegt vervolgens een vertrouwensrelatie *toe* aan uw eigen toepassingen en scripts door Microsoft Managed Desktop aan te vormen van de persoon die u al vertrouwt.

### <a name="base-policy"></a>Basisbeleid

Microsoft Managed Desktop, samen met Microsoft Cyber Security experts, maakt en onderhoudt een standaardbeleid waarmee de meeste apps die worden geïmplementeerd via Microsoft intune, worden ingeschakeld tijdens het blokkeren van gevaarlijke activiteiten, zoals het maken van schadelijke activiteiten of het uitvoeren van niet-vertrouwde bestanden.

Het Basisbeleid heeft de volgende aanpak voor het beperken van software-uitvoering:

- Bestanden die door beheerders worden uitgevoerd, kunnen worden uitgevoerd.
- Bestanden op locaties die zich *niet* in de door de gebruiker beschrijfbare directory's bevinden, kunnen worden uitgevoerd.
- Bestanden zijn ondertekend door een [vertrouwde ondertekenaar](#signer-requests).
- De meeste bestanden die zijn ondertekend door Microsoft worden uitgevoerd, maar sommige worden geblokkeerd om taken met een hoge risico te voorkomen, zoals code compilatie.


Als een andere gebruiker dan een beheerder een app of een script kon toevoegen aan een apparaat (dat wil zeggen dat het zich in een door de gebruiker geschrijf bare map) bevindt, kan het programma niet worden uitgevoerd, tenzij het al specifiek is toegestaan door een beheerder. Als een gebruiker het probleem wil doen met het installeren van malware en een aanvaller in een app die de gebruiker probeert malware te installeren of als een gebruiker voornemens is een niet-geautoriseerde app of script uit te voeren, wordt het programma beëindigd.

### <a name="signer-requests"></a>Verzender aanvragen

U verwittigt welke apps door software-uitgevers worden geleverd door een *Onderteken aanvraag* te archiveren. Door dit te doen, voegen we die vertrouwensgegevens toe aan het beleid voor basislijn toepassingen en toestaan dat alle software die met het certificaat van de uitgever is ondertekend, wordt uitgevoerd op uw apparaten.

## <a name="audit-and-enforced-policies"></a>Beleidsregels controleren en afdwingen

Microsoft Managed Desktop gebruikt twee Microsoft intune-beleidsregels voor het instellen van app-beheer:

### <a name="audit-policy"></a>Controlebeleid
Met dit beleid maakt u Logboeken om te bepalen of een app of script wordt geblokkeerd door het beleid dat wordt afgedwongen. Controlebeleid beoordeelt geen app-besturings regels en is bedoeld om te testen of een toepassing een Publisher-uitzondering vereist. Het logboek maakt waarschuwingen (8003 of 8006 Events) in Logboeken in plaats van de uitvoering of installatie van bepaalde apps of scripts te blokkeren.

### <a name="enforced-policy"></a>Beleid voor geforceerde beperking
Met dit beleid blokkeert u niet-vertrouwde apps en scripts van uitvoering en maakt u Logboeken wanneer u een app of script blokkeert. Beleidsregels met uitgaand beleid voorkomen dat standaardgebruikers van apps of scripts worden uitgevoerd die in de door de gebruiker geschrijf bare directory's zijn opgeslagen.

Voor apparaten in de test groep is een controlebeleid toegepast, zodat u deze kunt gebruiken om te controleren of toepassingen problemen kunnen veroorzaken. Alle overige groepen (voor het eerst, snel en algemeen) gebruik een afgedwongen beleid, zodat gebruikers in die groepen niet-vertrouwde apps of scripts kunnen uitvoeren.







