---
title: Configureerbare instellingen voor Microsoft Managed Desktop
description: Informatie over configureerbare instellingen met Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie, instellingen, configureerbare instellingen
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: d8ebe4519d169db5500c55a3337836ca2d0986c0
ms.sourcegitcommit: 427c6459614d58f6ef7c74354ae1816423e22323
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/28/2019
ms.locfileid: "42809844"
---
# <a name="configurable-settings---microsoft-managed-desktop"></a>Configureerbare instellingen - Microsoft Managed Desktop

Microsoft Managed Desktop implementeert instellingen en beleidsregels die worden toegepast op alle apparaten die door Microsoft Managed Desktop worden beheerd. Zie [Apparaatconfiguratie](../service-description/device-policies.md)voor meer informatie.

Configureerbare instellingen in Microsoft Managed Desktop bieden IT-beheerders een manier om instellingen aan te passen en te implementeren die uniek zijn voor hun organisatie en bedrijfsbehoeften. Deze instellingen vormen een aanvulling op de configuratie-instellingen en het beleid van het apparaat die worden beheerd door Microsoft Managed Desktop.  

Configureerbare instellingswijzigingen worden aangebracht in de cloud en toegepast op uw Microsoft Managed Desktop-apparaten in gedefinieerde implementatiegroepen. Dit proces is vergelijkbaar met de manier waarop Microsoft Managed Desktop wijzigingen beheert in instellingen en beleidsregels voor apparaatconfiguratie die door de service worden gedefinieerd en beheerd. Door hetzelfde proces te gebruiken dat Microsoft Managed Desktop gebruikt voor het implementeren van wijzigingen, blijft u uw organisatie vooruit helpen met behulp van moderne IT-beheerpraktijken.

## <a name="when-to-use-configurable-settings"></a>Wanneer configureerbare instellingen gebruiken?

Er zijn een paar keer om configureerbare instellingen te gebruiken. 

**Onboarding-proces** : Microsoft Managed Desktop raadt u aan configureerbare instellingen aan te passen wanneer u aan boord gaat van de Microsoft Managed Desktop-service of wanneer u een groot aantal apparaten aan boord brengt (20 of meer). Instellingscategorieën zijn geconfigureerd in de beheerportal van Microsoft Managed Desktop. Nadat u de beheerdersportal hebt ingegaan en toegang hebt tot de beheerdersportal, u bepalen welke instellingscategorieën u wilt aanpassen voor uw organisatie, de wijzigingen aanbrengen, een implementatie infaseeren en vervolgens uw wijzigingen implementeren.

**Instellingen behouden** - Controleer uw instellingen regelmatig en breng benodigde updates uit. Mogelijk moet u wijzigingen aanbrengen om een wijziging in uw bedrijf te ondersteunen.   

## <a name="setting-categories"></a>Categorieën instellen

Dit zijn de configureerbare instellingencategorieën die u aanpassen:
- Afbeelding van de [bureaubladachtergrond](config-setting-ref.md#desktop-background-picture) : pas de bureaubladachtergrondafbeelding aan voor Microsoft Managed Desktop-apparaten. 
- [Startpagina's voor](config-setting-ref.md#browser-start-pages) de browser : voeg startpagina's toe om te gebruiken met Microsoft Edge. Zie startpagina browser
- [Sitelijst in de bedrijfsmodus](config-setting-ref.md#enterprise-mode-site-list-location) : sites toevoegen en de compatibiliteitsmodus. Sites in de lijst worden gestart in Internet Explorer. 
- [Vertrouwde sites](config-setting-ref.md#trusted-sites) : voeg vertrouwde sites toe en stel beveiligingszones in voor elke site. 
- Uitzonderingen op [proxysite:](config-setting-ref.md#proxy) stel het adresnummer en het poortnummer van uw proxyserver in en voeg uitzonderingen op proxysite toe.

Elke instellingscategorie kan worden aangepast en op zichzelf worden geïmplementeerd. U wijzigingen in meerdere instellingscategorieën tegelijk implementeren, maar u slechts één wijziging tegelijk implementeren in een instellingscategorie.

Bijvoorbeeld:
- U wijzigingen in de achtergrondfoto en vertrouwde sites op het bureaublad, elk als hun eigen implementatie, tegelijkertijd implementeren. 
- U twee implementaties niet tegelijkertijd implementeren voor startpagina's van de browser. De meest recente implementatie stopt eerdere implementaties die nog in uitvoering zijn.

## <a name="configurable-setting-process"></a>Configureerbaar instellingsproces

Microsoft Managed Desktop raadt aan een proces te volgen dat vergelijkbaar is met het volgende bij het gebruik van configureerbare instellingen voor uw organisatie:

**Stap 1 - Plan** - Meer informatie over configureerbare instellingen en bepaal welke instellingscategorieën u voor uw organisatie wilt configureren. Maak een tijdlijn voor wanneer u verwacht wijzigingen in elke groep te implementeren. Plan communicatie naar uw gebruikers die voldoet aan uw interne change management processen. Als u bijvoorbeeld startpagina's van de browser toevoegt, laat u uw gebruikers weten dat ze na de implementatie een nieuwe set startpagina's in hun browser hebben.  

**Stap 2 - Implementatie configureren en fasen** - Wijzigingen aanbrengen in configureerbare instellingen in de beheerportal van Microsoft Managed Desktop. Faseer de wijzigingen zodat ze klaar zijn om te worden geïmplementeerd. Vergeet niet om uw gebruikers op de hoogte te stellen van de wijzigingen en hoe de wijzigingen hun apparaatervaring zullen veranderen.   

U configureert en faseert wijzigingen in de beheerportal van Microsoft Managed Desktop. Zie [Configureerbare instellingen aanpassen](config-setting-ref.md)voor meer informatie. 

**Stap 3 - Wijzigingen communiceren** Communiceer informatie over aankomende wijzigingen aan uw gebruikers. Voltooi voor elke implementatie de communicatie die deel uitmaakt van uw change management processen. U moet duidelijk communiceren elke verandering die van invloed is op hoe een gebruiker werkt, of wat ze zullen zien op hun apparaten.

**Stap 4 - Wijzigingen implementeren** – Implementeer uw wijzigingen, te beginnen met de groep Testen. Met de groep Test u problemen in een groep met minder apparaten valideren en oplossen voordat u wijzigingen implementeert in grotere groepen apparaten. Als u problemen tegenkomt, u de wijziging terugdraaien, de instelling bijwerken en een nieuwe implementatie uitvoeren. Microsoft Managed Desktop raadt u aan de gestructureerde aanpak te volgen en te implementeren in groepen in deze volgorde: Eerst, Snel en vervolgens Breed.   

Alle configureerbare instellingen worden beheerd met behulp van de microsoft Managed Desktop-beheerportal. Zie [Wijzigingen implementeren](config-setting-deploy.md)voor meer informatie. 

**Stap 5 - Wijzigingen bijhouden** – Houd de voortgang bij voor uw wijzigingen in de implementatiestatus. Voor elke instelling u:
- **Voortgang bijhouden** : volg de status nadat u de wijziging hebt geïmplementeerd. De status wordt gewijzigd in **In progress**en vervolgens **voltooien**of **mislukt.** Als een implementatie mislukt, wordt er automatisch een ondersteuningsverzoek geopend voor Microsoft Managed Desktop Operations om het probleem te onderzoeken.  
- **Versie geïmplementeerd** : elke geïmplementeerde wijziging heeft een versienummer.
- **Wijzigingen terugdraaien** : als u een wijziging terugzet, wordt de huidige implementatie gestopt en worden alle groepen teruggezet naar de laatste wijzigingen die zijn geïmplementeerd in alle groepen. U rolt terug naar de laatst bekende-goede instellingswaarde.
- **Wijzigingen valideren** - Nadat de implementatie is voltooid, valideren de wijzigingen zijn toegepast zoals u had verwacht.  

Als een implementatie is mislukt of als u een wijziging niet terugdraaien, [opent u een ondersteuningsverzoek](admin-support.md) met Microsoft Managed Desktop Operations. 

Zie [Configureerbare instellingen implementeren en bijhouden](config-setting-deploy.md)voor meer informatie.

## <a name="additional-resources"></a>Aanvullende bronnen
- [Referentie voor configureerbare instellingen](config-setting-ref.md) 
- [Configureerbare instellingen implementeren](config-setting-deploy.md) 
