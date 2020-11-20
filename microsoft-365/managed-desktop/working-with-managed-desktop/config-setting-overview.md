---
title: Configureerbare instellingen voor Microsoft Managed Desktop
description: Info over configureerbare instellingen met Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, service, Documentatie, instellingen, configureerbare instellingen
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

Microsoft Managed Desktop implementeert instellingen en beleidsregels die worden toegepast op alle apparaten die door Microsoft worden beheerd. Zie [apparaatconfiguratie configureren](../service-description/device-policies.md)voor meer informatie.

Configureerbare instellingen in Microsoft Managed desktop bieden IT-beheerders een manier om instellingen aan te passen en te implementeren die uniek zijn voor hun organisatie en de bedrijfsbehoeften. Deze instellingen zijn niet alleen geconfigureerd voor configuratie van apparaatconfiguratie en beleidsregels die worden beheerd door Microsoft beheerde bureaublad.  

Instellingen voor het configureren van de instellingen worden in de Cloud gemaakt en toegepast op uw door Microsoft beheerde bureaublad apparaten in gedefinieerde implementatie groepen. Dit proces is vergelijkbaar met de manier waarop Microsoft Managed Desktop wijzigingen beheert in configuratie-instellingen en beleid van de apparaatconfiguratie, die worden gedefinieerd en beheerd door de service. Met behulp van het proces dat door Microsoft door Microsoft wordt gebruikt voor de implementatie van wijzigingen, blijft u uw organisatie verder verplaatsen met behulp van moderne IT-beheer praktijken.

## <a name="when-to-use-configurable-settings"></a>Wanneer gebruikt u configureerbare instellingen?

Er zijn een paar keer dat u configureerbare instellingen kunt gebruiken. 

**Onboarding** : Microsoft Managed Desktop adviseert configureerbare instellingen aan te passen wanneer u de Microsoft beheerde bureaublad service uitvalt, of als u een groot aantal apparaten hebt opruimen (20 of meer). Het instellen van categorieën wordt geconfigureerd in de portal van de beheerde bureaublad beheerder van Microsoft. Wanneer u de beheerder hebt geklikt en u toegang hebt tot de beheerportal, kunt u bepalen welke instellings categorieën u wilt aanpassen voor uw organisatie, de wijzigingen aanbrengen, een implementatie klaarzetten en de wijzigingen vervolgens implementeren.

**Instellingen onderhouden** : Controleer de instellingen regelmatig en breng de benodigde wijzigingen aan. Mogelijk moet u wijzigingen aanbrengen ter ondersteuning van een wijziging in uw bedrijf.   

## <a name="setting-categories"></a>Categorieën instellen

Dit zijn de categorieën configureerbare instellingen die u kunt aanpassen:
- [Afbeelding van bureaubladachtergrond](config-setting-ref.md#desktop-background-picture) : de afbeelding van het bureaublad aanpassen voor Microsoft beheerde bureaublad apparaten. 
- [Startpagina's in browser](config-setting-ref.md#browser-start-pages) : startpagina's toevoegen voor gebruik met Microsoft Edge. De startpagina van de browser weergeven
- [Site lijst voor ondernemingsmodus](config-setting-ref.md#enterprise-mode-site-list-location) : sites toevoegen en de compatibiliteitsmodus. Sites in de lijst worden gestart in Internet Explorer. 
- [Vertrouwde sites](config-setting-ref.md#trusted-sites) : vertrouwde websites toevoegen en beveiligingszones voor elke site instellen. 
- [Uitzonderingen op proxy site](config-setting-ref.md#proxy) -u kunt het adres nummer en het poortnummer van de proxyserver instellen en proxy site-uitzonderingen toevoegen.

Elke instellings categorie kan worden aangepast en geïmplementeerd. U kunt wijzigingen in meerdere instellings categorieën tegelijk implementeren, maar u kunt slechts één wijziging tegelijk toepassen op een instellings categorie.

Bijvoorbeeld:
- U kunt wijzigingen op de bureaubladachtergrond afbeelding en de vertrouwde sites op elk moment implementeren. 
- Het is niet mogelijk om twee implementaties te implementeren voor het openen van pagina's in de browser. De meest recente implementatie stopt eerdere implementaties die nog actief zijn.

## <a name="configurable-setting-process"></a>Instelbare instellingsproces

Microsoft Managed Desktop adviseert een proces dat vergelijkbaar is met het volgende bij het gebruik van configureerbare instellingen voor uw organisatie:

**Stap 1:** Maak informatie over configureerbare instellingen en bepaal welke instellings categorieën u wilt configureren voor uw organisatie. Maak een tijdlijn waarvoor u wijzigingen wilt implementeren voor elke groep. Plan de communicatie met uw gebruikers die voldoet aan uw interne processen voor wijzigingsbeheer. Als u bijvoorbeeld startpagina's voor een browser toevoegt, kunnen uw gebruikers weten dat ze na de implementatie een nieuwe set startpagina's in hun browser hebben.  

**Stap 2: implementatie configureren en stage** -wijzigingen aanbrengen in configureerbare instellingen in Microsoft Managed Desktop admin Portal. Stage de wijzigingen zodat ze klaar zijn voor de implementatie. Vergeet niet dat uw gebruikers op de hoogte kunnen blijven van de wijzigingen en wat de werking van het apparaat verandert.   

U configureert wijzigingen en stage-wijzigingen in de beheerportal van Microsoft Managed Desktop. Zie [configureerbare instellingen aanpassen](config-setting-ref.md)voor meer informatie. 

**Stap 3: wijzigingen communiceren** Communiceer informatie over aanstaande wijzigingen aan uw gebruikers. Maak voor elke implementatie de communicatie die deel uitmaakt van uw processen voor wijzigingsbeheer. U dient duidelijk te communiceren welke wijziging van invloed is op de werking van een gebruiker, of wat ze op hun apparaat te zien krijgen.

**Stap 4: wijzigingen implementeren** – uw wijzigingen implementeren, beginnend bij de groep testen. Met de groep testen kunt u problemen in een groep met minder apparaten valideren en oplossen voordat u wijzigingen aanbrengt in grotere groepen apparaten. Als u problemen ondervindt, kunt u de wijziging herstellen, de instelling bijwerken en een nieuwe implementatie stage. Microsoft Managed Desktop adviseert de gestructureerde aanpak en implementeer de groepen in deze volgorde: testen, voor het eerst, snel en vervolgens algemeen.   

Alle instellingen die kunnen worden geconfigureerd, worden beheerd met behulp van de beheerde portal voor Microsoft-bureaubladbeheer. Zie [wijzigingen implementeren](config-setting-deploy.md)voor meer informatie. 

**Stap 5: wijzigingen bijhouden** : de voortgang bijhouden voor de wijzigingen op de implementatiestatus. Voor elke instelling kunt u het volgende doen:
- **Voortgang bijhouden** – status bijhouden nadat u de wijziging hebt geïmplementeerd. De status wordt gewijzigd **in voortgang** en vervolgens **voltooid**, of **mislukt**. Als een implementatie mislukt, wordt een ondersteuningsverzoek automatisch geopend voor Microsoft beheerde bureaublad bewerkingen om het probleem te onderzoeken.  
- **Zie versie geïmplementeerd** – elke geïmplementeerde wijziging heeft een versienummer.
- **Wijzigingen ongedaan** maken: als u een wijziging aanbrengt, stopt de huidige implementatie en keert alle groepen terug naar de laatste wijzigingen die zijn geïmplementeerd voor alle groepen. U keert terug naar de laatst bekende goede instellingswaarde.
- **Wijzigingen valideren** -nadat de implementatie is voltooid, controleert u of de wijzigingen zijn toegepast zoals u verwacht.  

Als een implementatie mislukt, of als u de wijziging niet kunt terugdraaien, [opent u een ondersteuningsaanvraag](admin-support.md) met Microsoft beheerde bureaublad bewerkingen. 

Zie [configureerbare instellingen implementeren en bijhouden](config-setting-deploy.md)voor meer informatie.

## <a name="additional-resources"></a>Aanvullende bronnen
- [Verwijzing naar configureerbare instellingen](config-setting-ref.md) 
- [Configureerbare instellingen implementeren](config-setting-deploy.md) 
