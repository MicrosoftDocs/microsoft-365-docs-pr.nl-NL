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
ms.openlocfilehash: bf8672ee6c3332ea6f8522f5086d72e58d1b9048
ms.sourcegitcommit: bdf65d48b20f0f428162c39ee997accfa84f4e5d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2020
ms.locfileid: "49371488"
---
# <a name="configurable-settings---microsoft-managed-desktop"></a>Configureerbare instellingen - Microsoft Managed Desktop

Microsoft Managed Desktop implementeert instellingen en beleidsregels die worden toegepast op alle apparaten die worden beheerd door Microsoft Managed Desktop. Zie Apparaatconfiguratie voor [meer informatie.](../service-description/device-policies.md)

Configureerbare instellingen in Microsoft Managed Desktop it-beheerders een manier bieden om instellingen aan te passen en te implementeren die uniek zijn voor hun organisatie en zakelijke behoeften. Deze instellingen zijn naast apparaatconfiguratie-instellingen en -beleidsregels die worden beheerd door Microsoft Managed Desktop.  

Configureerbare instellingswijzigingen worden aangebracht in de cloud en toegepast op uw Microsoft Managed Desktop apparaten in gedefinieerde implementatiegroepen. Dit proces is vergelijkbaar met hoe Microsoft Managed Desktop wijzigingen in instellingen en beleidsregels voor apparaatconfiguraties beheert die zijn gedefinieerd en beheerd door de service. Door hetzelfde proces te gebruiken dat Microsoft Managed Desktop voor het implementeren van wijzigingen, blijft u uw organisatie vooruit helpen met moderne IT-beheerpraktijken.

## <a name="when-to-use-configurable-settings"></a>Wanneer kunt u configureerbare instellingen gebruiken?

Er zijn enkele keren configureerbare instellingen te gebruiken. 

**Onboardingproces:** Microsoft Managed Desktop raadt u aan configureerbare instellingen aan te passen wanneer u aan boord gaat van Microsoft Managed Desktop-service of wanneer u een groot aantal apparaten (20 of meer) aan boord hebt. Het instellen van categorieën wordt geconfigureerd in Microsoft Managed Desktop beheerportal. Nadat u de beheerportal hebt ge onboarded en toegang hebt tot de beheerportal, kunt u bepalen welke instellingscategorieën u wilt aanpassen voor uw organisatie, de wijzigingen aanbrengen, een implementatie opzetten en vervolgens uw wijzigingen implementeren.

**Instellingen onderhouden:** controleer uw instellingen regelmatig en pas de benodigde updates aan. Mogelijk moet u wijzigingen aanbrengen om een wijziging in uw bedrijf te ondersteunen.   

## <a name="setting-categories"></a>Categorieën instellen

Dit zijn de configureerbare instellingencategorieën die u kunt aanpassen:
- [Bureaubladachtergrondafbeelding:](config-setting-ref.md#desktop-background-picture) pas de achtergrondafbeelding van het bureaublad aan voor Microsoft Managed Desktop apparaten. 
- [Startpagina's van browser:](config-setting-ref.md#browser-start-pages) startpagina's toevoegen voor gebruik met Microsoft Edge. Zie Startpagina browser
- [Lijst met sites in de ondernemingsmodus:](config-setting-ref.md#enterprise-mode-site-list-location) sites toevoegen en de compatibiliteitsmodus. Sites in de lijst beginnen in Internet Explorer. 
- [Vertrouwde sites:](config-setting-ref.md#trusted-sites) voeg vertrouwde sites toe en stel beveiligingszones in voor elke site. 
- [Uitzonderingen op proxysite:](config-setting-ref.md#proxy) stel het adresnummer en poortnummer van de proxyserver in en voeg uitzonderingen op de proxysite toe.

Elke instellingscategorie kan zelf worden aangepast en geïmplementeerd. U kunt wijzigingen in meerdere instellingscategorieën tegelijk implementeren, maar u kunt slechts één wijziging tegelijk implementeren in een instellingscategorie.

Bijvoorbeeld:
- U kunt wijzigingen in bureaubladachtergrondafbeeldingen en vertrouwde sites tegelijk implementeren als hun eigen implementatie. 
- U kunt twee implementaties niet tegelijk implementeren naar startpagina's van de browser. Met de meest recente implementatie worden eerdere implementaties gestopt die nog in uitvoering zijn.

## <a name="configurable-setting-process"></a>Configureerbare instelling

Microsoft Managed Desktop raadt u aan een proces te volgen dat lijkt op het volgende bij het gebruik van configureerbare instellingen voor uw organisatie:

**Stap 1 - Plannen** - Meer informatie over configureerbare instellingen en bepalen welke instellingscategorieën u wilt configureren voor uw organisatie. Maak een tijdlijn voor wanneer u wijzigingen voor elke groep verwacht te implementeren. Plan communicatie met uw gebruikers die voldoen aan uw interne processen voor wijzigingsbeheer. Als u bijvoorbeeld startpagina's voor browsers toevoegt, laat uw gebruikers weten dat ze na de implementatie een nieuwe set startpagina's in hun browser hebben.  

**Stap 2 - Configureren en implementeren van** fases - Wijzigingen aanbrengen in configureerbare instellingen in Microsoft Managed Desktop beheerportal. Faseer de wijzigingen zodat ze klaar zijn om te worden geïmplementeerd. Vergeet niet om uw gebruikers te laten weten over de wijzigingen en hoe de wijzigingen hun apparaatervaring zullen wijzigen.   

U configureert en faseeert wijzigingen in de Microsoft Managed Desktop beheerportal. Zie Configureerbare instellingen [aanpassen voor meer informatie.](config-setting-ref.md) 

**Stap 3 - Wijzigingen communiceren** Communiceer informatie over aanstaande wijzigingen aan uw gebruikers. Voltooi voor elke implementatie de communicatie die deel uitmaakt van uw veranderingsbeheerprocessen. U moet duidelijk elke wijziging communiceren die van invloed is op de manier waarop een gebruiker werkt of wat hij of zij op zijn of haar apparaten ziet.

**Stap 4 : wijzigingen implementeren:** implementeer uw wijzigingen, te beginnen met de groep Testen. Met de groep Testen kunt u problemen in een groep met minder apparaten valideren en oplossen voordat u wijzigingen implementeert op grotere groepen apparaten. Als er problemen zijn, kunt u de wijziging terugdraaien, de instelling bijwerken en een nieuwe implementatie uitvoeren. Microsoft Managed Desktop raadt u aan de gestructureerde aanpak te volgen en deze te implementeren voor groepen in deze volgorde: Test, First, Fast en vervolgens Broad.   

Alle configureerbare instellingen worden beheerd met de Microsoft Managed Desktop beheerportal. Zie Wijzigingen implementeren [voor meer informatie.](config-setting-deploy.md) 

**Stap 5 : Wijzigingen bijhouden:** de voortgang bijhouden voor de wijzigingen in de implementatiestatus. Voor elke instelling kunt u het volgende doen:
- **Voortgang bijhouden:** de status bijhouden nadat u de wijziging hebt geïmplementeerd. De status wordt gewijzigd **in In uitvoering** en vervolgens **voltooid** of **Mislukt.** Als een implementatie mislukt, wordt automatisch een ondersteuningsaanvraag geopend voor Microsoft Managed Desktop operations om het probleem te onderzoeken.  
- **Versie geïmplementeerd bekijken:** elke geïmplementeerde wijziging heeft een versienummer.
- **Wijzigingen terugdraaien:** als u een wijziging terugzet, wordt de huidige implementatie gestopt en worden alle groepen terugverzet naar de laatste wijzigingen die zijn geïmplementeerd voor alle groepen. U wordt teruggerold naar de laatst bekende-goede instellingswaarde.
- **Wijzigingen valideren:** nadat de implementatie is voltooid, moet u de wijzigingen valideren zoals u had verwacht.  

Als een implementatie is mislukt of als u een wijziging niet kunt terugdraaien, opent u een [ondersteuningsaanvraag](admin-support.md) met Microsoft Managed Desktop Operations. 

Zie Configureerbare instellingen [implementeren en bijhouden voor meer informatie.](config-setting-deploy.md)

## <a name="additional-resources"></a>Aanvullende bronnen
- [Verwijzing naar configureerbare instellingen](config-setting-ref.md) 
- [Configureerbare instellingen implementeren](config-setting-deploy.md) 
