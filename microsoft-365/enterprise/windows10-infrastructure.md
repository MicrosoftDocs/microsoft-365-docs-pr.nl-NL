---
title: Windows 10 Enterprise-infrastructuur voor Microsoft 365 Enterprise
description: Biedt een advies op hoog niveau over de stappen die u nodig hebt om Windows 10 Enterprise op pc's te implementeren als onderdeel van Microsoft 365 Enterprise.
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
ms.openlocfilehash: 53c38ba2e915cd439c8d7629bc7f9cd56ebc8647
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636673"
---
# <a name="phase-3-windows-10-enterprise"></a>Fase 3: Windows 10 Enterprise

![Fase 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon.png)

Microsoft 365 Enterprise bevat Windows 10 Enterprise, waarmee u de tools hebt om meer te doen en veilig te blijven. Windows 10 Enterprise:

- **Is geïntegreerd voor eenvoud** - Benut de kracht van de cloud om de complexiteit van het beheer van de moderne IT-apparaatomgeving te verminderen, ongeacht de grootte.
- **Heeft intelligente beveiliging** - Het is de veiligste release van Windows ooit, met intelligente beveiligingsmogelijkheden die zijn ontworpen om samen te werken om uw organisatie beter te beschermen.
- **Maakt creativiteit en teamwork mogelijk** - ontgrendelt creativiteit en teamwork om de meest productieve ervaring te bieden waar zowel gebruikers als IT dol op zullen zijn.

U moet inzicht krijgen in de verschillende manieren waarop u het Windows 10-besturingssysteem implementeren en de juiste optie voor uw organisatie kiezen. Afhankelijk van uw Microsoft 365 Enterprise-abonnement zijn er ook Windows 10-services en beveiligingsfuncties die u moet configureren om het meeste uit Windows 10 te halen.

>[!Note]
>Zie het [Modern Desktop Deployment Center](https://aka.ms/howtoshift)om zowel Windows 10 Enterprise- als Microsoft 365-apps voor bedrijven samen te implementeren en over te schakelen naar een moderne [desktop.](https://www.microsoft.com/microsoft-365/modern-desktop)
>

## <a name="windows-10-deployment"></a>Windows 10-implementatie

Er zijn meerdere manieren waarop u Windows 10 Enterprise voor uw organisatie implementeren. Hier richten we ons op hoe u een Windows 10 Enterprise-afbeelding configureren en implementeren via deze moderne implementatiescenario's.

| Implementatiescenario | Wanneer te gebruiken |
|:--- |:--- |
| [Microsoft Endpoint Configuration Manager gebruiken als een in-place upgrade](windows10-deploy-inplaceupgrade.md) | Selecteer deze optie als u Windows 7- of Windows 8.1-computers moet upgraden naar de <a href="https://aka.ms/windows-10-release-information" target="_blank">huidige versie</a> van Windows 10 Enterprise en uw computers momenteel worden beheerd met Configuration <a href="https://docs.microsoft.com/configmgr/core/understand/introduction" target="_blank">Manager (Huidige branch).</a> |
| [Windows Autopilot gebruiken](windows10-deploy-autopilot.md) | Selecteer deze optie als u nieuwe Windows-computers instelt waarop Windows 10 Enterprise, versie 1703 of hoger is geïnstalleerd. Eindgebruikers starten de installatie met de gewenste configuratie door hun rechten van het werk- of schoolaccount in te voeren. |

Als deze implementatiescenario's niet voldoen aan de behoeften van uw organisatie, u meer te weten komen over andere scenario's en inzicht krijgen in de mogelijkheden en beperkingen van elk van deze [scenario's in Windows 10-implementatiescenario's.](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios) U kunt ook zelf <a href="https://aka.ms/planforwin10deployment" target="_blank">de implementatie van Windows 10 plannen</a>.

U meer informatie over Windows 10 lezen met deze artikelen:

- [Microsoft 365 Enterprise-productpagina](https://www.microsoft.com/microsoft-365/enterprise)
- [Windows 10](https://docs.microsoft.com/windows/windows-10)
- [Windows 10 implementeren en bijwerken](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a>Aanvullende services en functies
Als onderdeel van uw implementatie van Windows 10 Enterprise u deze extra services en functies toevoegen.

### <a name="windows-analytics"></a>Windows Analytics

Windows gebruikt diagnostische gegevens om uitgebreide, bruikbare informatie te bieden om u te helpen diepgaande inzichten te krijgen in de operationele efficiëntie en de status van Windows 10-apparaten in uw omgeving.

* Gereedheid voor upgrade - Met de gereedheid voor upgrade u overstappen naar Windows 10 en op de hoogte blijven van nieuwe Windows 10-functie-updates. 
* Compliance bijwerken - Update Compliance is gericht op de IT-beheerder die een holistisch beeld wil krijgen van al hun Windows 10-apparaten, zonder extra infrastructuurvereisten.
* Apparaatstatus - U apparaatstatus gebruiken om problemen met problemen met de gevolgen van eindgebruikers proactief op te sporen en op te lossen.

Zie [Overzicht van Windows Analytics](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) voor meer informatie.

### <a name="windows-security"></a>Windows-beveiliging

Windows 10 biedt functies om u te beschermen tegen bedreigingen, u te helpen uw apparaten te beveiligen en te helpen bij toegangscontrole. Met Windows 10 krijgt u kritieke beveiligingsfuncties die uw apparaat vanaf het begin beschermen. Microsoft 365 E3 voegt beveiligingsfuncties toe, zoals Windows Hello for Business, Windows Defender Application Control en Windows Information Protection. Met Microsoft 365 E5 krijgt u alle bescherming van Microsoft 365 E3-beveiliging plus cloudgebaseerde beveiligingsfuncties en Microsoft Defender Advanced Threat Protection. 

Zie [Stap 5: Windows 10 Enterprise-beveiligingsfuncties implementeren](windows10-enable-security-features.md)voor meer informatie over de beveiligingsfuncties die u met Windows 10 Enterprise krijgt en voor meer informatie over de beveiligingsfuncties die u met Windows 10 Enterprise implementeren, beheren, configureren en oplossen.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Hoe Microsoft omgaat met Microsoft 365 Enterprise

Neem een kijkje in Microsoft en ontdek hoe het bedrijf [Windows 10 Enterprise heeft geïmplementeerd en sterke verificatie, Intune en Microsoft Defender ATP gebruikt.](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR6)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Hoe Contoso Microsoft 365 Enterprise gebruikt

Bekijk hoe de Contoso Corporation, een fictief maar representatief multinationaal bedrijf, [Windows 10 Enterprise heeft geïmplementeerd.](contoso-win10.md)

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Volgende stap

|||
|:-------|:-----|
|![Stap 1](../media/stepnumbers/Step1.png)| [Uw organisatie voorbereiden op Windows 10 Enterprise](windows10-prepare-your-org.md) |
