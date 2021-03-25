---
title: Uw Microsoft Defender voor endpoint-implementatie plannen
description: Selecteer de beste implementatiestrategie van Microsoft Defender voor eindpunten voor uw omgeving
keywords: deploy, plan, deployment strategy, cloud native, management, on prem, evaluation, onboarding, local, group policy, gp, endpoint manager, mem
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8cd670e72bbb4ec0abacd4ed053a9ea9af12608b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163573"
---
# <a name="plan-your-microsoft-defender-for-endpoint-deployment"></a>Uw Microsoft Defender voor endpoint-implementatie plannen 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 


Plan uw Microsoft Defender voor endpoint-implementatie, zodat u de beveiligingsmogelijkheden binnen de suite kunt maximaliseren en uw bedrijf beter kunt beschermen tegen cyberdreigingen.


Deze oplossing biedt richtlijnen voor het identificeren van uw omgevingsarchitectuur, het type implementatieprogramma dat het beste aansluit bij uw behoeften en richtlijnen voor het configureren van mogelijkheden.


![Afbeelding van implementatiestroom](images/deployment-guide-plan.png)


## <a name="step-1-identify-architecture"></a>Stap 1: Architectuur identificeren
We begrijpen dat elke ondernemingsomgeving uniek is, dus hebben we verschillende opties geboden om u de flexibiliteit te bieden bij het kiezen van de implementatie van de service.

Sommige hulpprogramma's zijn beter geschikt voor bepaalde architecturen, afhankelijk van uw omgeving. 

Gebruik het volgende materiaal om de juiste Defender voor eindpuntarchitectuur te selecteren die het beste past bij uw organisatie.

| Item | Beschrijving |
|:-----|:-----|
|[![Thumb image for Defender for Endpoint deployment strategy](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)<br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) | Met het materiaal voor architecten kunt u uw implementatie plannen voor de volgende architecturen: <ul><li> Cloud-native </li><li> Co-management </li><li> On-premises</li><li>Evaluatie en lokale onboarding</li>



## <a name="step-2-select-deployment-method"></a>Stap 2: Implementatiemethode selecteren
Defender voor Eindpunt ondersteunt diverse eindpunten die u aan boord van de service kunt gebruiken. 

De volgende tabel bevat de ondersteunde eindpunten en het bijbehorende implementatieprogramma dat u kunt gebruiken, zodat u de implementatie op de juiste manier kunt plannen.

| Eindpunt     | Implementatiehulpmiddel                       |
|--------------|------------------------------------------|
| **Windows**  |  [Lokaal script (maximaal 10 apparaten)](configure-endpoints-script.md) <br>  [Groepsbeleid](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/ Mobile Device Manager](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI-scripts](configure-endpoints-vdi.md)   |
| **macOS**    | [Lokaal script](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [Mobile Device Management](mac-install-with-other-mdm.md) |
| **Linux Server** | [Lokaal script](linux-install-manually.md) <br> [Poppop](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [App-gebaseerde](ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](android-intune.md)               | 



## <a name="step-3-configure-capabilities"></a>Stap 3: Mogelijkheden configureren
Nadat u eindpunten hebt onboarding, configureert u de beveiligingsmogelijkheden in Defender voor Eindpunt, zodat u de krachtige beveiliging kunt maximaliseren die beschikbaar is in de suite. De volgende mogelijkheden zijn:

- Eindpuntdetectie en -antwoord
- Beveiliging van de volgende generatie
- Surface-beperking voor aanvallen


  
## <a name="related-topics"></a>Verwante onderwerpen
- [Implementatiefasen](deployment-phases.md)
