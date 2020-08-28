---
title: App-bediening
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
ms.openlocfilehash: 32ed3f95ebb4299796c5ad3eb71802c949701b65
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289125"
---
# <a name="app-control"></a>App-bediening

App-besturingselement is een optionele beveiligingsprocedure in Microsoft Managed Desktop waarmee de uitvoering van code op clientapparaten wordt beperkt. Dit besturingselement verkleint het risico van malware of kwaadaardige scripts door aan te geven dat alleen code die is ondertekend door een door de klant goedgekeurde lijst met uitgevers, kan worden uitgevoerd. Dit besturingselement biedt veel beveiligingsvoordelen, maar dit is vooral bedoeld om gegevens en identiteit te beschermen tegen exploits op basis van client.

Microsoft Managed Desktop vergemakkelijkt het beheer van app-beheerbeleidsregels door een basisbeleid te maken dat scenario's voor kern productiviteit mogelijk maakt. U kunt vertrouwen op extra ondertekeners uitbreiden die specifiek zijn voor de apps en scripts in uw omgeving. 


Voor elke beveiligingstechnologie is een evenwicht tussen de gebruikerservaring, beveiliging en kosten vereist. Met app-beheer wordt de bedreiging van schadelijke software in uw omgeving beperkt, maar er zijn gevolgen voor de gebruiker en aanvullende acties voor uw IT-beheerder.

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

Microsoft Managed Desktop, in samenwerking met Microsoft Cyber Security experts, maakt en onderhoudt een standaardbeleid waarmee de meeste apps die via Microsoft intune worden geïmplementeerd, worden ingeschakeld tijdens het blokkeren van schadelijke activiteiten, zoals de compilatie van schadelijke activiteiten of het uitvoeren van niet-vertrouwde bestanden

Het Basisbeleid heeft de volgende aanpak voor het beperken van software-uitvoering:

- Bestanden die door beheerders worden uitgevoerd, kunnen worden uitgevoerd.
- Bestanden op locaties die zich *niet* in de door de gebruiker beschrijfbare directory's bevinden, kunnen worden uitgevoerd.
- Bestanden zijn ondertekend door een [vertrouwde ondertekenaar](#signer-requests).
- De meeste bestanden die zijn ondertekend door Microsoft worden uitgevoerd, maar sommige worden geblokkeerd om taken met een hoge risico te voorkomen, zoals code compilatie.


Als een andere gebruiker dan een beheerder een app of een script kon toevoegen aan een apparaat (dat wil zeggen dat het zich in een door de gebruiker geschrijf bare map) bevindt, kan het programma niet worden uitgevoerd, tenzij het al specifiek is toegestaan door een beheerder. Als een gebruiker het probleem wil doen met het installeren van malware en een aanvaller in een app die de gebruiker probeert malware te installeren of als een gebruiker voornemens is een niet-geautoriseerde app of script uit te voeren, wordt het programma beëindigd.

### <a name="signer-requests"></a>Verzender aanvragen

U verwittigt welke apps door leveranciers van software worden geleverd door een *Onderteken aanvraag*te archiveren. Door dit te doen, voegen we die vertrouwensgegevens toe aan het beleid voor basislijn toepassingen en toestaan dat alle software die met het certificaat van de uitgever is ondertekend, wordt uitgevoerd op uw apparaten.

## <a name="audit-and-enforced-policies"></a>Beleidsregels controleren en afdwingen

Microsoft Managed Desktop gebruikt twee Microsoft intune-beleidsregels voor het instellen van app-beheer:

### <a name="audit-policy"></a>Controlebeleid
Met dit beleid maakt u Logboeken om te bepalen of een app of script wordt geblokkeerd door het beleid dat wordt afgedwongen. Controlebeleid beoordeelt geen app-besturings regels en is bedoeld om te testen of een toepassing een Publisher-uitzondering vereist. Het logboek maakt waarschuwingen (8003 of 8006 Events) in Logboeken in plaats van de uitvoering of installatie van bepaalde apps of scripts te blokkeren.

### <a name="enforced-policy"></a>Beleid voor geforceerde beperking
Met dit beleid blokkeert u niet-vertrouwde apps en scripts van uitvoering en maakt u Logboeken wanneer u een app of script blokkeert. Beleidsregels met uitgaand beleid voorkomen dat standaardgebruikers van apps of scripts worden uitgevoerd die in de door de gebruiker geschrijf bare directory's zijn opgeslagen.

Voor apparaten in de test groep is een controlebeleid toegepast, zodat u deze kunt gebruiken om te controleren of toepassingen problemen kunnen veroorzaken. Alle overige groepen (voor het eerst, snel en algemeen) gebruik een afgedwongen beleid, zodat gebruikers in die groepen niet-vertrouwde apps of scripts kunnen uitvoeren.







