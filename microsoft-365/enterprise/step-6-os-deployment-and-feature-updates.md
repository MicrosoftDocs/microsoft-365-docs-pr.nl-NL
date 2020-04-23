---
title: Stap 6 - Implementatie van besturingssysteem en functie-updates
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/30/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Meer informatie over de opties voor de implementatie van een besturingssysteem en functie-updates.
ms.openlocfilehash: d22a0993b256a1bea1a6a5ac61f14b144c6ac6c7
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636757"
---
# <a name="step-6-os-deployment-and-feature-updates"></a>Stap 6: Implementatie van besturingssysteem en functie-updates

![](../media/step-6-os-deployment-and-feature-updates-media/step-6-os-deployment-and-feature-updates-media-1.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-9.png" alt="Step 6" height="144" width="144" /></td>
<td><p><strong>Stap 6: Implementatie van besturingssysteem en functie-updates</strong></p>
<p>Implementatie met behulp van een takenreeks wordt gebruikt voor het automatiseren van een grootschalige, gefaseerde implementatie van BMR-installaties, pc-vernieuwingen en pc-vervangingen. Het gebruiken van takenreeksen voor upgrades helpt u ook op de hoogte te blijven van de belangrijkste halfjaarlijkse updates. Windows Autopilot is een recente toevoeging waarmee het proces voor het aanschaffen van een nieuwe pc is gemoderniseerd.</p></td>
<td><a href="https://aka.ms/ddev6" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-19.png" alt="Step 6" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>Implementatie van het besturingssysteem en functie-updates vormen de zesde stap in ons aanbevolen implementatieproces voor de implementatie van Windows 10, upgrades en functie-updates. Ga naar het [Desktop Deployment Center](https://aka.ms/HowToShift) om het volledige desktop-implementatieproces te bekijken.
>

Als u het implementatieproces tot nu toe hebt gevolgd, hebt u de stappen voor het gereedmaken van apparaten en apps minstens deels voltooid, en hebt u de infrastructuur voorbereid, app-pakketten geconfigureerd en verzameld, een plan opgesteld voor het migreren van gebruikersbestanden en het configureren van standaardinstellingen alsook een plan voor het behouden van uw bestaande veiligheidscontroles en mogelijk het implementeren van nieuwe.

Nu zijn we aangekomen op het punt waarop u al deze onderdelen samenvoegt om zoveel mogelijk te automatiseren voor het installeren van Windows 10 en Microsoft 365-apps voor ondernemingen, evenals de vereiste sturingsprogramma's, apps en andere items.

Uiteindelijk heeft de implementatie van een besturingssysteem de grootste kans op succes wanneer wordt voldaan aan de verwachtingen van gebruikers en onderbrekingen van werkzaamheden worden voorkomen. Tijdens deze stap begint u met het testen en implementeren voor proefgebruikers als onderdeel van de gefaseerde implementatie. En één tip hier is dat u voordat u de implementatie uitbreidt, verder moet gaan naar stap 8 van het implementatieproces - [Communicatie en training voor gebruikers](https://aka.ms/mdd8) - om te garanderen dat gebruikers op de hoogte zijn van en voorbereid zijn op wijzigingen en dat u het tempo van de uitbreiding met continue validatie kunt uitvoeren door middel van Gefaseerde implementatie.

## <a name="windows-imaging-process"></a>Imaging-proces Windows

In de meeste organisaties wordt het proces van PC-imaging gebruikt voor het configureren en registreren van een kloon van Windows, met inbegrip van een aantal standaard-apps die zijn geïnstalleerd, of een nog smallere installatiekopie met alleen runtimes van toepassingen en updates. De beste manier om dit te doen, is met behulp van een virtuele machine voor dit proces om te voorkomen dat zich onverwachte compatibiliteitsproblemen met het stuurprogramma voordoen en voor automatiseringsdoeleinden.

Als u kiest voor imaging, kunt u het beste zoveel mogelijk automatiseren om ervoor te zorgen dat de installatiekopie van de beste kwaliteit is en u een herhaalbaar proces opstelt. In de meeste gevallen wordt u aangeraden om zo min mogelijk aanpassingen en vooraf geïnstalleerde apps in de Windows-image te gebruiken voordat u deze opneemt. Dit is de zogenaamde 'thin-image'-methode waarmee u bespaart op de totale bandbreedte in het netwerk door het aantal apps in de installatiekopie te minimaliseren. Als u begint met een smalle basisinstallatiekopie, kunt u lagen opbouwen van vereiste apps, talen en configuraties die dynamisch zijn afgestemd op de gebruikers.

Tijdens het opbouw- en opnameproces gebruiken hulpmiddelen zoals Microsoft Endpoint Configuration Manager (huidige versie) en de Microsoft Deployment Toolkit het hulpprogramma System Preparation Tool (of Sysprep) in combinatie met de opdracht “Generaliseren” om uw installatiekopie opnieuw te verzegelen voordat de Windows 10-installatie als een installatiekopie wordt opgenomen.

De vastgelegde installatiekopie heeft het Windows-installatiekopieformaat (of WIM), zoals standaard Windows-installatiemedia. Zodra u uw aangepaste WIM-bestand hebt, kunt u een andere takenreeks gebruiken als onderdeel van de implementatie van het besturingssysteem in Configuration Manager of de Microsoft Deployment Toolkit om implementatietaken uit te voeren, de installatiekopie toe te passen en taken uit te voeren voordat en nadat de Windows-installatiekopie is toegepast.

[Een referentie-image voor Windows 10 maken](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/create-a-windows-10-reference-image)

[Een takenreeks maken om een besturingssysteem te installeren](https://docs.microsoft.com/configmgr/osd/deploy-use/create-a-task-sequence-to-install-an-operating-system)

### <a name="deployment-types"></a>Implementatietypen

Nu uw aangepaste installatiekopie klaar is, zijn er verschillende soorten installatie- en migratietypen om uit te kiezen: 

  - Ten eerste, **bare metal-implementatie**. Dit is het scenario dat wordt gebruikt voor het implementeren van een installatiekopie op een schone schijf of voor het opnieuw instellen van een computer waarvan u de gegevens niet wilt opslaan op de schijf

  - De tweede, **Computer vernieuwen**, is vergelijkbaar met bare metal, waarbij het belangrijkste verschil is dat de gebruikersstatus op de schijf blijft staan\* of wordt hersteld nadat de installatie is voltooid.

  - De laatste methode is **Computer vervangen**. Zoals de naam al aangeeft, vervang je hierbij de ene pc met een andere pc. In dit geval wordt er vaak een back-up van de gebruikersbestanden van de eerste pc gemaakt op een centrale locatie, waarna die bestanden worden overgezet op de tweede pc.

Alle drie deze scenario's hebben iets gemeen: bij de uitvoering wordt gebruikgemaakt van een takenreeks en er kan telkens een installatiekopie worden toegepast.

[Meer informatie over implementatiescenario's voor Windows 10](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)

### <a name="in-place-upgrade-using-task-sequence-automation"></a>Een in-place upgrade uitvoeren met behulp van takenreeksautomatisering

Naast deze implementatietypen is er nu een nieuwe optie beschikbaar als takenreeks van Microsoft Endpoint Configuration Manager (huidige versie) met Windows 10 en in-place upgrade met behulp van de Upgrade Task Sequence.

Voor in-place upgrades van een eerdere versie van Windows is geen takenreeks nodig, maar het is een aanbevolen aanpak bij de implementatie op ondernemingsschaal. Bij een in-place upgrade is het niet mogelijk om een aangepaste installatiekopie te gebruiken voor toepassingen, maar u kunt de standaard install.wim wel bijwerken door middel van offline onderhoud. U kunt bijvoorbeeld controleren of de meest recente Windows-updates zijn toegepast voorafgaand aan de upgrades.

Voor in-place upgrades wordt Windows Setup gebruikt. De installatiemotor voert voorafgaand aan de installatie verschillende kleine controles uit op zoek naar bekende compatibiliteitsproblemen. Bovendien blijven de gebruikersstatus en -toepassingen behouden en wordt alleen de inhoud verwijderd die niet compatibel is met de versie van Windows 10 die wordt geïnstalleerd. Met deze optie blijven eerder geïnstalleerde toepassingen en gebruikersstatus behouden. In-place upgrade geeft u ook de mogelijkheid om het vorige besturingssysteem terug te zetten indien dit nodig is voor het oplossen van problemen.

[Pre-upgrade validatie voor Windows 10 met behulp van setup.exe](https://blogs.technet.microsoft.com/mniehaus/2015/08/23/windows-10-pre-upgrade-validation-using-setup-exe/)

![](../media/step-6-os-deployment-and-feature-updates-media/step-6-os-deployment-and-feature-updates-media-3.png)

Het in-place upgradescenario kan worden gebruikt om te migreren naar Windows 10 vanuit oudere versies van Windows, alsook voor een upgrade van vorige versies van Windows 10. Nadat Windows Setup de upgrade heeft voltooid, kunt u de takenreeks blijven uitvoeren en toepassingen zoals Office upgraden, sturingsprogramma‘s vervangen en personalisatie-instellingen toepassen. Op dezelfde manier kunt u de Upgrade Task Sequence gebruiken voor het uitvoeren van pre-installatie taken of controles voorafgaand aan de upgrade.

[Een in-place upgrade uitvoeren naar Windows 10 met Configuration Manager](https://docs.microsoft.com/windows/deployment/upgrade/upgrade-to-windows-10-with-system-center-configuraton-manager)

[Een taakreeks maken voor het upgraden van een besturingssysteem in Configuration Manager](https://docs.microsoft.com/configmgr/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system)

### <a name="phased-deployment"></a>Gefaseerde implementatie

Tijdens het plannen van de implementatie richt u zich op bare metal-, vernieuwings-, vervangings- en upgradepaden. In dit geval kunt u het beste gefaseerde implementatie gebruiken voor verzamelingen van vergelijkbare computers. Op deze manier kunt u compatibiliteit, levering, automatisering, gebruikersacceptatie, verbruik van de netwerkbandbreedte en andere factoren valideren voordat u de schaal van de implementatie verhoogt.

![](../media/step-6-os-deployment-and-feature-updates-media/step-6-os-deployment-and-feature-updates-media-4.png)

### <a name="recommended-tools-microsoft-endpoint-configuration-manager-current-branch-and-the-microsoft-deployment-toolkit"></a>Aanbevolen hulpmiddelen: Microsoft Endpoint Configuration Manager (huidige versie) en de Microsoft Deployment Toolkit

Ongeacht het implementatietype dat u kiest, moet u ervoor zorgen dat dit zo geautomatiseerd mogelijk is ten behoeve van de voorspelbaarheid en herhaalbaarheid. Microsoft biedt twee oplossingen voor het automatiseren van de implementatie van het besturingssysteem met behulp van geautomatiseerde takenreeksen:

  - **[Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/core/understand/introduction)** (ConfigMgr) biedt ingebouwde implementatiemogelijkheden voor besturingssystemen waarmee de mogelijkheden voor softwaredistributie en software-updatebeheer worden aangevuld. ConfigMgr wordt veel gebruikt door organisaties van elke omvang en biedt ondersteuning voor alle vier de Windows-implementatietypen. U kunt ConfigMgr daarnaast ook integreren met Microsoft Intune om extra mogelijkheden voor implementatie en apparaatbeheer toe te voegen.

  - Een andere populaire implementatieoptie is de gratis **[Microsoft Deployment Toolkit](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/get-started-with-the-microsoft-deployment-toolkit)** (MDT), die meestal door kleine en middelgrote organisaties wordt gebruikt voor de implementatie van het besturingssysteem. Hiervoor is zeer weinig infrastructuur vereist. MDT wordt geïntegreerd met Windows Deployment Services (WDS) voor het opstarten van het netwerk. Hiermee worden alle vier de implementatietypen ondersteund, alsook de installatie van toepassingen, sturingsprogramma's en instellingen. En uiteraard kan MDT worden geïntegreerd met Configuration Manager.

![](../media/step-6-os-deployment-and-feature-updates-media/step-6-os-deployment-and-feature-updates-media-5.png)

### <a name="windows-autopilot"></a>Windows Autopilot

Een nieuwe optie voor Windows 10 is het configureren van nieuwe pc's als onderdeel van de hardwarevernieuwingscyclus van Windows Autopilot. Hiermee kunt u samen met ondersteunende hardwareleveranciers werken aan het aanpassen van de standaardwerking van Windows door bijvoorbeeld de opties die worden weergegeven aan gebruikers, zoals licentie-overeenkomsten of instellingen voor diagnostische gegevens, te verwijderen.

Wanneer een gebruiker zich tijdens de installatie op de pc aanmeldt met behulp van hun referenties voor Azure AD, registreert het apparaat zich bij Microsoft Intune, dat vervolgens het implementatieproces kan overnemen en toepassingen, configuraties van software-updates en het nalevingsbeleid kan toepassen. Met Windows Autopilot kunt u er desgewenst ook voor zorgen dat de gebruiker geen toegang meer heeft tot de eerste sessie tot de implementatie is voltooid.

[Overzicht van Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot)

[Vereisten voor Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot#prerequisites)

## <a name="windows-update-for-business-for-feature-updates"></a>Windows Update voor Bedrijven voor functie-updates

Windows Update voor Bedrijven is een gratis service die IT-professionals in staat stelt Windows 10-apparaten altijd up-to-date te houden door de apparaten rechtstreeks te verbinden met de Windows Update-service. Windows Update voor Bedrijven kan via Groepsbeleid of via MDM-oplossingen, zoals Microsoft Intune, worden geconfigureerd en biedt IT-medewerkers de mogelijkheid om [gefaseerde implementatie](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates) toe te passen voor het valideren van nieuwe ontwerpen. Het is geïntegreerd in bestaande beheerprogramma's, zoals Windows Server Update Services (WSUS), Microsoft Endpoint Configuration Manager (huidige tak) en Microsoft Intune. Bovendien ondersteunt Windows Update voor Bedrijven peer-to-peer-levering om de efficiëntie van de bandbreedte te optimaliseren en netwerkcongestie te beperken.

Voor meer informatie over Windows Update voor Bedrijven raadpleegt u de volgende documentatie:

- [Implementeer updates met behulp van Windows Update voor Bedrijven](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [Configureer Windows Update voor Bedrijven](https://docs.microsoft.com/windows/deployment/update/waas-configure-wufb)
- [Integreer Windows Update voor Bedrijven met bestaande beheerhulpmiddelen](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb)
- [Gebruik Groepsbeleid om Windows Update voor Bedrijven te configureren](https://docs.microsoft.com/windows/deployment/update/waas-wufb-group-policy)
- [Gebruik Microsoft Intune om Windows Update voor Bedrijven te configureren](https://docs.microsoft.com/intune/windows-update-for-business-configure)

## <a name="next-step"></a>Volgende stap 

## <a name="step-7-windows-and-office-servicing"></a>[Stap 7: Onderhoud van Windows en Office](https://aka.ms/mdd7)

## <a name="previous-step"></a>Vorige stap

## <a name="step-5-security-and-compliance-considerations"></a>[Stap 5: Overwegingen met betrekking tot beveiliging en naleving](https://aka.ms/mdd5)
