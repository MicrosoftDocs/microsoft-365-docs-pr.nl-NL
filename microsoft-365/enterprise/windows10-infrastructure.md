---
title: Windows 10 Enterprise-infrastructuur voor Microsoft 365 Enterprise
description: Biedt een richtlijnen op hoog niveau voor de stappen die u nodig hebt om Windows 10 Enterprise op pc's te implementeren als onderdeel van Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365-documentatie, Windows 10 Enterprise, implementatie
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/28/2019
f1.keywords:
- NOCSH
ms.author: greglin
ms.openlocfilehash: 72a355a524ff3dd56300566ff228b5ff5007c6cb
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42808413"
---
# <a name="phase-3-windows-10-enterprise"></a>Fase 3: Windows 10 Enterprise

![Fase 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon.png)

Microsoft 365 Enterprise bevat Windows 10 Enterprise, waarmee u de tools hebt om meer te doen en veilig te blijven. Windows 10 Enterprise:

- **Is geïntegreerd voor eenvoud** - Benut de kracht van de cloud om de complexiteit van het beheer van de moderne IT-apparaatomgeving van vandaag te verminderen, ongeacht de grootte.
- **Heeft intelligente beveiliging** - Het is de veiligste release van Windows ooit, met intelligente beveiligingsmogelijkheden die zijn ontworpen om samen te werken om uw organisatie beter te beschermen.
- **Maakt creativiteit en teamwork mogelijk** - Ontsluit creativiteit en teamwork om de meest productieve ervaring te bieden waar zowel gebruikers als IT dol op zullen zijn.

U moet de verschillende manieren begrijpen waarop u het Windows 10-besturingssysteem implementeren en de juiste optie voor uw organisatie kiezen. Afhankelijk van uw Microsoft 365 Enterprise-abonnement zijn er ook Windows 10-services en beveiligingsfuncties die u moet configureren om het meeste uit Windows 10 te halen.

>[!Note]
>Zie het [Modern Desktop Deployment Center](https://aka.ms/howtoshift)om zowel Windows 10 Enterprise als Office 365 ProPlus samen te implementeren en over te schakelen naar een modern [bureaublad.](https://www.microsoft.com/microsoft-365/modern-desktop)
>

## <a name="windows-10-deployment"></a>Windows 10-implementatie

U Windows 10 Enterprise op meerdere manieren implementeren voor uw organisatie. Hier richten we ons op hoe u een Windows 10 Enterprise-afbeelding configureren en implementeren via deze moderne implementatiescenario's.

| Implementatiescenario | Wanneer te gebruiken |
|:--- |:--- |
| [Microsoft Endpoint Configuration Manager gebruiken als een in-place upgrade](windows10-deploy-inplaceupgrade.md) | Selecteer deze optie als u Windows 7- of Windows 8.1-computers moet upgraden naar de <a href="https://aka.ms/windows-10-release-information" target="_blank">huidige versie</a> van Windows 10 Enterprise en uw computers momenteel worden beheerd met Configuration <a href="https://docs.microsoft.com/configmgr/core/understand/introduction" target="_blank">Manager (Huidige branch).</a> |
| [Automatische piloot van Windows gebruiken](windows10-deploy-autopilot.md) | Selecteer deze optie als u nieuwe Windows-computers instelt waarop Windows 10 Enterprise, versie 1703 of hoger vooraf zijn geïnstalleerd. Eindgebruikers starten de installatie met behulp van de gewenste configuratie door hun werk- of schoolaccountgegevens in te voeren. |

Als deze implementatiescenario's niet voldoen aan de behoeften van uw organisatie, u meer te weten komen over andere scenario's en inzicht krijgen in de mogelijkheden en beperkingen van elk in [Windows 10-implementatiescenario's.](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios) U ook zelf <a href="https://aka.ms/planforwin10deployment" target="_blank">plannen voor Windows 10-implementatie.</a>

Meer informatie over Windows 10 vindt u in deze artikelen:

- [Microsoft 365 Enterprise-productpagina](https://www.microsoft.com/microsoft-365/enterprise)
- [Windows 10](https://docs.microsoft.com/windows/windows-10)
- [Windows 10 implementeren en bijwerken](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a>Aanvullende services en functies
Als onderdeel van uw implementatie van Windows 10 Enterprise u deze extra services en functies toevoegen.

### <a name="windows-analytics"></a>Windows Analytics

Windows gebruikt diagnostische gegevens om uitgebreide, bruikbare informatie te verstrekken om u te helpen diepgaande inzichten te krijgen in operationele efficiëntie en de gezondheid van Windows 10-apparaten in uw omgeving.

* Gereedheid voor upgrade - Gereedheid bijwerken helpt u over te stappen naar Windows 10 en op de hoogte te blijven van nieuwe Windows 10-functie-updates. 
* Naleving bijwerken - Naleving bijwerken is gericht op de IT-beheerder die een holistisch beeld wil krijgen van al zijn Windows 10-apparaten, zonder extra infrastructuurvereisten.
* Apparaatstatus - U apparaatstatus gebruiken om problemen met de impact van eindgebruikers proactief op te sporen en te veranen.

Zie [Windows Analytics Overzicht](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) voor meer informatie.

### <a name="windows-security"></a>Windows-beveiliging

Windows 10 biedt functies om bedreigingen te beschermen, u te helpen uw apparaten te beveiligen en u te helpen bij toegangscontrole. Met Windows 10 krijgt u vanaf het begin kritieke beveiligingsfuncties die uw apparaat beschermen. Microsoft 365 E3 voegt beveiligingsfuncties toe, zoals Windows Hello voor Bedrijven, Windows Defender Application Control en Windows Information Protection. Met Microsoft 365 E5 krijgt u alle bescherming tegen Microsoft 365 E3-beveiliging plus cloudgebaseerde beveiligingsfuncties en Microsoft Defender Advanced Threat Protection. 

Zie [Stap 5: Windows 10 Enterprise-beveiligingsfuncties](windows10-enable-security-features.md)implementeren voor meer informatie over de beveiligingsfuncties die u met Windows 10 Enterprise krijgt en richtlijnen voor het implementeren, beheren, configureren en oplossen van drie belangrijke beveiligingsfuncties.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Hoe Microsoft microsoft 365 Enterprise doet

Bekijk binnen Microsoft en ontdek hoe het bedrijf [Windows 10 Enterprise heeft geïmplementeerd en gebruik maakt van sterke verificatie, Intune en Microsoft Defender ATP.](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR6)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Hoe Contoso microsoft 365 Enterprise deed

Bekijk hoe de Contoso Corporation, een fictief maar representatief multinationaal bedrijf, [Windows 10 Enterprise heeft geïmplementeerd.](contoso-win10.md)

![De Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Volgende stap

|||
|:-------|:-----|
|![Stap 1](../media/stepnumbers/Step1.png)| [Uw organisatie voorbereiden op Windows 10 Enterprise](windows10-prepare-your-org.md) |
