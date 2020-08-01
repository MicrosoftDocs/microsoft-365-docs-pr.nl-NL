---
title: Configureerbare instellingen voor Microsoft Managed Desktop
description: Informatie over configureerbare instellingen met Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie, instellingen, configureerbare instellingen
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1af320ee6151036000e4e8c6fedc4d9152411283
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530233"
---
# <a name="configurable-settings---microsoft-managed-desktop"></a>Configureerbare instellingen - Microsoft Managed Desktop

Microsoft Managed Desktop implementeert instellingen en beleidsregels die worden toegepast op alle apparaten die worden beheerd door Microsoft Managed Desktop. Zie [Apparaatconfiguratie voor](../service-description/device-policies.md)meer informatie.

Configureerbare instellingen in Microsoft Managed Desktop bieden IT-beheerders een manier om instellingen aan te passen en te implementeren die uniek zijn voor hun organisatie en zakelijke behoeften. Deze instellingen zijn naast apparaatconfiguratie-instellingen en -beleidsregels die worden beheerd door Microsoft Managed Desktop.  

Configureerbare instellingswijzigingen worden aangebracht in de cloud en toegepast op uw Microsoft Managed Desktop-apparaten in gedefinieerde implementatiegroepen. Dit proces is vergelijkbaar met de manier waarop Microsoft Managed Desktop wijzigingen beheert in instellingen voor apparaatconfiguratie en -beleidsregels die door de service zijn gedefinieerd en beheerd. Door hetzelfde proces te gebruiken dat Microsoft Managed Desktop gebruikt voor het implementeren van wijzigingen, blijft u uw organisatie vooruit helpen met behulp van moderne IT-beheerpraktijken.

## <a name="when-to-use-configurable-settings"></a>Wanneer configureerbare instellingen gebruiken?

Er zijn een paar keer om configureerbare instellingen te gebruiken. 

**Onboarding-proces** : Microsoft Managed Desktop raadt u aan configureerbare instellingen aan te passen wanneer u ingebruik bent bij de Microsoft Managed Desktop-service of wanneer u een groot aantal apparaten ingebruik bent (20 of meer). Instellingscategorieën zijn geconfigureerd in de beheerportal voor Beheerde bureaubladen van Microsoft. Nadat u hebt onboarded en toegang hebt tot de beheerportal, u bepalen welke instellingscategorieën u wilt aanpassen voor uw organisatie, de wijzigingen aanbrengen, een implementatie instellen en vervolgens uw wijzigingen implementeren.

**Instellingen behouden** - Controleer uw instellingen regelmatig en maak de benodigde updates. Mogelijk moet u wijzigingen aanbrengen om een wijziging in uw bedrijf te ondersteunen.   

## <a name="setting-categories"></a>Categorieën instellen

Dit zijn de configureerbare instellingencategorieën die u aanpassen:
- [Bureaubladachtergrondafbeelding](config-setting-ref.md#desktop-background-picture) : pas de bureaubladachtergrondafbeelding aan voor Microsoft Managed Desktop-apparaten. 
- [Startpagina's van](config-setting-ref.md#browser-start-pages) de browser : startpagina's toevoegen om te gebruiken met Microsoft Edge. Zie Startpagina browser
- [Enterprise mode site lijst](config-setting-ref.md#enterprise-mode-site-list-location) - Sites toevoegen, en hun compatibiliteitsmodus. Sites in de lijst worden gestart in Internet Explorer. 
- [Vertrouwde sites](config-setting-ref.md#trusted-sites) : voeg vertrouwde sites toe en stel beveiligingszones in voor elke site. 
- [Uitzonderingen op proxysite](config-setting-ref.md#proxy) : stel het adresnummer en het poortnummer van uw proxyserver in en voeg uitzonderingen op proxysite toe.

Elke instellingscategorie kan op zichzelf worden aangepast en geïmplementeerd. U wijzigingen tegelijkertijd implementeren in meerdere instellingscategorieën, maar u slechts één wijziging tegelijk implementeren in een instellingscategorie.

Bijvoorbeeld:
- U wijzigingen implementeren in bureaubladachtergrondafbeelding en vertrouwde sites, elk als hun eigen implementatie, tegelijkertijd. 
- U niet twee implementaties tegelijk implementeren in startpagina's in de browser. De meest recente implementatie stopt eerdere implementaties die nog in uitvoering zijn.

## <a name="configurable-setting-process"></a>Configureerbaar instellingsproces

Microsoft Managed Desktop raadt aan een proces te volgen dat vergelijkbaar is met het volgende wanneer u configureerbare instellingen voor uw organisatie gebruikt:

**Stap 1 - Plannen** - Meer informatie over configureerbare instellingen en bepaal welke instellingscategorieën u wilt configureren voor uw organisatie. Maak een tijdlijn voor wanneer u verwacht wijzigingen in elke groep te implementeren. Plan communicatie naar uw gebruikers die voldoet aan uw interne change management processen. Als u bijvoorbeeld startpagina's van de browser toevoegt, laat u uw gebruikers weten dat ze na de implementatie een nieuwe set startpagina's in hun browser hebben.  

**Stap 2 - Implementatie configureren en fase maken** - Wijzigingen aanbrengen in configureerbare instellingen in de beheerportal voor Beheerde bureaublad van Microsoft. De wijzigingen in scène zetten, zodat ze klaar zijn om te implementeren. Vergeet niet om uw gebruikers op de hoogte te brengen van de wijzigingen en hoe de wijzigingen hun apparaatervaring zullen veranderen.   

U configureert en faseert wijzigingen in de Microsoft Managed Desktop-beheerportal. Zie [Configureerbare instellingen aanpassen voor](config-setting-ref.md)meer informatie. 

**Stap 3 - Wijzigingen communiceren** Communiceer informatie over aankomende wijzigingen aan uw gebruikers. Voer voor elke implementatie de communicatie uit die deel uitmaakt van uw change management processen. U moet elke wijziging die van invloed is op de werking van een gebruiker of wat hij of zij op zijn of haar apparaten ziet, duidelijk communiceren.

**Stap 4 - Wijzigingen implementeren** : Implementeer uw wijzigingen, te beginnen met de groep Testen. Met de groep Testen u eventuele problemen in een groep met minder apparaten valideren en oplossen voordat wijzigingen worden geïmplementeerd in grotere groepen apparaten. Als u problemen ondervindt, u de wijziging terugdraaien, de instelling bijwerken en een nieuwe implementatie uitvoeren. Microsoft Managed Desktop raadt u aan de gestructureerde aanpak te volgen en te implementeren in groepen in deze volgorde: Test, First, Fast en vervolgens Broad.   

Alle configureerbare instellingen worden beheerd met behulp van de Microsoft Managed Desktop-beheerportal. Zie [Wijzigingen implementeren voor](config-setting-deploy.md)meer informatie. 

**Stap 5 - Wijzigingen bijhouden** : houd de voortgang bij voor uw wijzigingen in de implementatiestatus. Voor elke instelling u:
- **Voortgang bijhouden** : houd de status bij nadat u de wijziging hebt geïmplementeerd. De status wordt gewijzigd **in Aan de gang**en vervolgens **Voltooien**of **Mislukt**. Als een implementatie mislukt, wordt er automatisch een ondersteuningsverzoek geopend voor Microsoft Managed Desktop Operations om het probleem te onderzoeken.  
- **Zie geïmplementeerde versie** : elke geïmplementeerde wijziging heeft een versienummer.
- **Wijzigingen terugzetten** : als u een wijziging terugzet, wordt de huidige implementatie gestopt en worden alle groepen teruggezet naar de laatste wijzigingen die in alle groepen zijn geïmplementeerd. U draait terug naar de laatst bekende goede instellingswaarde.
- **Wijzigingen valideren** - Nadat de implementatie is voltooid, valideert u de wijzigingen die zijn toegepast zoals u had verwacht.  

Als een implementatie is mislukt of als u een wijziging niet terugdraaien, opent u [een ondersteuningsverzoek](admin-support.md) met Microsoft Managed Desktop Operations. 

Zie [Configureerbare instellingen implementeren en bijhouden](config-setting-deploy.md)voor meer informatie.

## <a name="additional-resources"></a>Overige informatiebronnen
- [Verwijzing naar configureerbare instellingen](config-setting-ref.md) 
- [Configureerbare instellingen implementeren](config-setting-deploy.md) 
