---
title: Windows 10 Enterprise implementeren voor bestaande apparaten als een upgrade op zijn plaats
description: Biedt richtlijnen voor het configureren en implementeren van een Windows 10 Enterprise-afbeelding met Microsoft Endpoint Configuration Manager als een in-place upgrade.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365-documentatie, Windows 10 Enterprise, implementatie, in-place upgrade, Configuration Manager, Configuration Manager
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2018
f1.keywords:
- NOCSH
ms.author: greglin
ms.openlocfilehash: ca5abb97628d04a9f29bb3a3fb9b43a578dbab74
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42811293"
---
# <a name="step-2-deploy-windows-10-enterprise-for-existing-devices-as-an-in-place-upgrade"></a>Stap 2: Windows 10 Enterprise implementeren voor bestaande apparaten als een in-place upgrade

*Dit artikel is van toepassing op zowel de E3- als de E5-versies van Microsoft 365 Enterprise*

![Fase 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Het eenvoudigste pad om pc's te upgraden die momenteel Windows 7 of Windows 8.1 naar Windows 10 uitvoeren, is via een in-place upgrade. U een taakreeks Configuration Manager (Configuration Manager) gebruiken om het proces volledig te automatiseren. 

Als u bestaande computers met Windows 7 of Windows 8.1 hebt, raden we dit pad aan als uw organisatie Windows 10 implementeert. Dit maakt gebruik van het Windows-installatieprogramma (Setup.exe) om een in-place upgrade uit te voeren, die automatisch alle gegevens, instellingen, toepassingen en stuurprogramma's van de bestaande versie van het besturingssysteem behoudt. Dit vereist de minste IT-inspanning, omdat er geen complexe implementatie-infrastructuur nodig is.

Volg deze stappen voor het configureren en implementeren van een Windows 10 Enterprise-afbeelding met Microsoft Endpoint Configuration Manager als in-place upgrade.

## <a name="the-windows-10-deployment-with-configuration-manager-poster"></a>De Windows 10-implementatie met configuratiebeheerposter

De poster Configuration Manager is één pagina in de landschapsmodus (17x11). Klik op de afbeelding hieronder om een PDF in uw browser te bekijken. 

[![Windows 10 implementeren met poster Configuration Manager](../media/windows10-deploy-inplaceupgrade/windows10-deployment-config-manager.png)](https://docs.microsoft.com/windows/deployment/media/Windows10DeploymentConfigManager.pdf)

U deze poster ook downloaden in [PDF-](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10DeploymentConfigManager.pdf) of [Visio-indeling.](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10DeploymentConfigManager.vsdx)

## <a name="part-1-verify-readiness-to-upgrade-windows"></a>Deel 1: Controleer de gereedheid om Windows te upgraden

Gebruik eerst de upgradegereedheidsmogelijkheid van Windows Analytics om krachtige inzichten en aanbevelingen te bieden over de computers, toepassingen en stuurprogramma's in uw organisatie, zonder extra kosten en zonder extra infrastructuurvereisten. Deze nieuwe service begeleidt u bij upgrade- en functieupdateprojecten met behulp van een werkstroom op basis van aanbevolen procedures van Microsoft. Met up-to-date voorraadgegevens u kosten en risico's in uw upgradeprojecten in evenwicht brengen.

Zie [Windows-upgrades beheren met gereedheid voor upgrade](https://docs.microsoft.com/windows/deployment/upgrade/manage-windows-upgrades-with-upgrade-readiness) om meer te weten te komen, aan de slag te gaan, te gebruiken en problemen op te lossen met gereedheid voor upgrades.

Volg vervolgens de handleiding voor het gebruik van Configuration Manager (Current Branch) om windows 7 of hoger besturingssysteem te upgraden naar Windows 10. Zoals bij elke implementatie met een hoog risico raden we u aan een back-up van gebruikersgegevens te maken voordat u verdergaat. OneDrive-cloudopslag is klaar voor gebruik voor gelicentieerde Microsoft 365-gebruikers en kan worden gebruikt om hun bestanden veilig op te slaan. Zie [Snelaande handleiding voor OneDrive](https://aka.ms/ODfBquickstartguide)voor meer informatie. Als u toegang wilt krijgen tot deze pagina, moet u zich aanmelden als tenantbeheerder of globale beheerder in een Office 365- of Microsoft 365-tenant.

Zie [Ondersteuning voor Windows 10 voor Configuratiebeheer voor](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10)een lijst met Configuratiebeheerversies en de bijbehorende Windows 10-clientversies die worden ondersteund.

**De gereedheid voor een upgrade van Windows verifiëren**

Bekijk deze vereisten voordat u uw Windows 10-implementatie start:

- **Windows-edities die in aanmerking komen voor een upgrade** : uw apparaten moeten edities van Windows 7 of Windows 8.1 uitvoeren die in aanmerking komen voor een upgrade naar Windows 10 Enterprise. Zie [Windows 10-upgradepaden](https://aka.ms/win10upgradepaths)voor een lijst met ondersteunde edities. 
- **Ondersteunde apparaten** - De meeste computers die compatibel zijn met Windows 8.1 zijn compatibel met Windows 10. Mogelijk moet u bijgewerkte stuurprogramma's installeren in Windows 10 om uw apparaten goed te laten functioneren. Zie [Windows 10 specificaties](https://aka.ms/windows10specifications) voor meer info.
- **Implementatievoorbereiding** : Controleer of u het volgende hebt voordat u de implementatie gaat configureren:
    - Windows 10 installatiemedia - De installatiemedia moeten zich op een apart station bevinden, waarbij de ISO al is gemonteerd. U de ISO verkrijgen bij [MSDN Subscriber Downloads](https://aka.ms/msdn-subscriber-downloads) of bij het [Volume Licensing Service Center.](https://aka.ms/mvlsc)
    - Back-ups van gebruikersgegevens - Hoewel gebruikersgegevens worden gemigreerd in de upgrade, is het beste om een back-upscenario te configureren. Exporteer bijvoorbeeld alle gebruikersgegevens naar een OneDrive-account, BitLocker To Go-versleuteld USB-flashstation of netwerkbestandsserver. Zie [Gegevens maken van een back-up of overdracht in Windows](https://aka.ms/backuptransferdatawindows)voor meer informatie.
- **Omgevingsvoorbereiding** - U gebruikt een bestaande configuration manager-serverstructuur om u voor te bereiden op de implementatie van het besturingssysteem. Naast de basisinstelling moeten de volgende configuraties worden gemaakt in de configuratiebeheeromgeving:
    1. [Breid het Active Directory-schema uit](https://aka.ms/extendadschema) en [maak een systeembeheercontainer.](https://aka.ms/createsysmancontainer)
    2. Active Directory Forest Discovery en Active Directory System Discovery inschakelen. Zie [Detectiemethoden configureren voor Configuratiebeheer voor](https://aka.ms/configurediscoverymethods)meer informatie.
    3. Ip-bereikgrenzen en grensgroep maken voor inhoud en sitetoewijzing. Zie [Sitegrenzen en grensgroepen definiëren voor Configuratiebeheer voor](https://aka.ms/definesiteboundaries)meer informatie.
    4. De functie Van de rapportagepunten van Configuration Manager toevoegen en configureren. Zie [Rapportage configureren in Configuratiebeheer](https://aka.ms/configurereporting)voor meer informatie .
    5. Maak een mapstructuur voor bestandssystemen voor pakketten.
    6. Maak een configuratiebeheermapstructuur voor pakketten.
    7. Configuratiebeheer (Huidige branch)-updates en eventuele aanvullende Vereisten voor Windows 10 installeren.

## <a name="part-2-add-a-windows-10-os-image-using-configuration-manager"></a>Deel 2: Een Afbeelding van Windows 10-besturingssysteem toevoegen met Configuratiebeheer
Nu moet u een upgradepakket voor het besturingssysteem maken dat de volledige Installatiemedia van Windows 10 bevat. In de volgende stappen gebruikt u Configuratiebeheer om een upgradepakket voor Windows 10 Enterprise x64 te maken.

**Een Windows 10-afbeelding toevoegen met Configuratiebeheer**

1. Klik met de console Configuratiebeheer in de werkruimte **Softwarebibliotheek** met de rechtermuisknop op het knooppunt **Upgradepakketten voor het besturingssysteem** en selecteer vervolgens **Upgradepakket besturingssysteem toevoegen.**
2. Geef op de pagina **Gegevensbron** het UNC-pad op naar het Windows 10 Enterprise x64-media en selecteer **Volgende**.
3. Geef op de pagina **Algemeen** de optie **Windows 10 Enterprise x64 Upgrade**op en selecteer **Volgende**. 
4. Selecteer **op** de pagina Overzicht de optie **Volgende**en selecteer **Sluiten**. 
5. Klik met de rechtermuisknop op het gemaakte **Windows 10 Enterprise x64 Update-pakket** en selecteer **Inhoud distribueren**. 
6. Kies uw distributiepunt.

## <a name="part-3-configure-deployment-settings"></a>Deel 3: Implementatie-instellingen configureren
In deze stap configureert u een upgradetaakreeks met de instellingen voor de Windows 10-upgrade. Vervolgens identificeert u de apparaten die u wilt upgraden en implementeert u de taakreeks op die apparaten.

### <a name="create-a-task-sequence"></a>Een taakreeks maken
Voer de volgende stappen uit om een upgradetaakreeks te maken:
  
1. Vouw in de console Configuratiebeheer in de werkruimte **Softwarebibliotheek** **besturingssystemen**uit. 
2. Klik met de rechtermuisknop op het knooppunt **Taakreeksen** en selecteer **Taakreeks maken**.
3. Selecteer op de pagina **Een nieuwe taakreeks maken** de optie Een **besturingssysteem bijwerken uit het upgradepakket**en selecteer **Volgende**.
4. Geef op de pagina **Taakreeksgegevens** de optie **Windows 10 Enterprise x64 Upgrade**op en selecteer **Volgende**.
5. Selecteer op de pagina **Het Windows-besturingssysteem bijwerken de** optie **Bladeren** en kies het **upgradepakket voor windows 10 Enterprise x64-upgrade,** selecteer **OK**en selecteer **Volgende**.
6. Ga door de resterende wizardpagina's en selecteer **Sluiten**.

### <a name="create-a-device-collection"></a>Een apparaatverzameling maken
Nadat u de upgradetaakreeks hebt gemaakt, moet u een verzameling maken die de apparaten bevat die u wilt upgraden.

> [!NOTE]
> Gebruik de volgende instellingen om de implementatie op één apparaat te testen. U verschillende lidmaatschapsregels gebruiken om groepen apparaten op te nemen wanneer u er klaar voor bent. Zie [Collecties maken in Configuration Manager](https://docs.microsoft.com/configmgr/core/clients/manage/collections/create-collections)voor meer informatie.

1. Klik in de console Configuratiebeheer in de werkruimte **Assets en Compliance** met de rechtermuisknop op **Apparaatverzamelingen**en selecteer **vervolgens Apparaatverzameling maken**. 
2. Voer in de wizard Apparaatverzameling maken op de pagina **Algemeen** de volgende instellingen in en selecteer **Volgende:**
    - Naam: Windows 10 Enterprise x64 Upgrade
    - Beperkende verzameling: alle systemen
3. Selecteer op de pagina **Lidmaatschapsregels** de**regel** **Direct** > toevoegen om de wizard Direct lidmaatschapsregel maken te starten.
4. Selecteer **Volgende**op **de** welkomstpagina van de wizard Direct lidmaatschap maken .
5. Voer **op** de pagina Zoeken naar bronnen de volgende instellingen in en vervang de tijdelijke aanduiding **Waardetekst** door de naam van het apparaat dat u upgradet: 
    - Resourceklasse: systeembron
    - Kenmerknaam: naam
    - Waarde: *PC0003*
6. Selecteer **op** de pagina Bronnen selecteren uw apparaat en selecteer **Volgende**.
7. Voltooi de wizard Direct lidmaatschap maken en de wizard Apparaatverzameling maken.  
8. Bekijk de verzameling Windows 10 Enterprise x64 Upgrade. Ga niet door totdat u de machines ziet die u in de collectie hebt toegevoegd.

### <a name="create-an-operating-system-deployment"></a>Een implementatie van een besturingssysteem maken
Volg deze stappen om een implementatie voor de taakreeks te maken.

1. Klik in de console Configuratiebeheer in de werkruimte **Softwarebibliotheek** met de rechtermuisknop op de taakreeks die u in een vorige stap hebt gemaakt en selecteer **Vervolgens Implementeren**.
2. Selecteer **op** de pagina Algemeen de verzameling **Windows 10 Enterprise x64 Upgrade** en selecteer **Volgende**.
3. Selecteer **volgende**op de pagina **Inhoud** .
4. Selecteer op de pagina **Implementatie-instellingen** de volgende instellingen en selecteer **Volgende:**

    > [!NOTE]
    > Voor deze testimplementatie stelt u het doel in op **Beschikbaar,** waarvoor tussenkomst van de gebruiker nodig is om de implementatie te starten. In een productieomgeving u de implementatie automatiseren met het vereiste doel, waarbij u extra opties moet configureren, zoals het plannen wanneer de implementatie wordt uitgevoerd. 

    - Actie: Installeren
    - Doel: Beschikbaar

5. Accepteer **op de** pagina Plannen de standaardinstellingen en selecteer **Volgende**.
6. Accepteer op de pagina **Gebruikerservaring** de standaardinstellingen en selecteer **Volgende**.
7. Accepteer op de pagina **Waarschuwingen** de standaardinstellingen en selecteer **Volgende**.
8. Selecteer **op** de pagina Overzicht de optie **Volgende**en selecteer **Sluiten**.

## <a name="part-4-start-the-windows-10-upgrade-task-sequence"></a>Deel 4: De taakreeks voor upgraden van Windows 10 starten
Voer deze stappen uit om de taakreeks Windows 10-upgrade te starten op het apparaat dat u aan het upgraden bent.
 
1. Meld u aan bij de Windows-computer en start **Software Center**.
2. Selecteer de taakreeks die u in een vorige stap hebt gemaakt en selecteer **Vervolgens Installeren**.
3. Wanneer de taakreeks begint, wordt automatisch het upgradeproces op de plaats gestart door een beroep te doen op het Windows-installatieprogramma (Setup.exe) met de nodige opdrachtregelparameters om een geautomatiseerde upgrade uit te voeren, waarbij alle gegevens, instellingen, apps en Stuurprogramma 's.
4. Nadat de taakreeks is voltooid, wordt de computer volledig geüpgraded naar Windows 10.

Als u problemen ondervindt bij het gebruik van Windows 10 in een bedrijfsomgeving, u [de belangrijkste Microsoft Support-oplossingen raadplegen voor de meest voorkomende problemen.](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions) Deze bronnen omvatten KB-artikelen, updates en bibliotheekartikelen.

Gebruik tijdens de implementatie van updates in uw hele organisatie de updatecompliance-mogelijkheid van Windows Analytics om een holistische weergave te bieden van de naleving van de os-update, de voortgang van de implementatie van updates en het oplossen van problemen met fouten voor Windows 10-apparaten. Deze nieuwe service maakt gebruik van diagnostische gegevens, waaronder de voortgang van de installatie, windows update-configuratie en andere informatie om dergelijke inzichten te bieden, zonder extra kosten en zonder extra infrastructuurvereisten. Of het nu wordt gebruikt met Windows Update voor Bedrijven of andere beheertools, u er zeker van zijn dat uw apparaten correct zijn bijgewerkt.

Zie [Windows-updates en Windows Defender-antivirus controleren met naleving van updates](https://docs.microsoft.com/windows/deployment/update/update-compliance-monitor) voor meer informatie, aan de slag en gebruik Update Compliance.

Als tussencontrolepunt ziet u de [exitcriteria](windows10-exit-criteria.md#crit-windows10-step2) die overeenkomen met deze stap.

## <a name="next-step"></a>Volgende stap

|||
|:-------|:-----|
|![Stap 3](../media/stepnumbers/Step3.png)| [Windows 10 Enterprise implementeren voor nieuwe apparaten met Windows Autopilot](windows10-deploy-autopilot.md) |
