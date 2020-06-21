---
title: Mogelijkheden voor bedreigingsbescherming implementeren in Microsoft 365
description: Meer informatie over het implementeren van services en mogelijkheden voor bedreigingsbescherming in Microsoft 365 E5.
ms.author: bcarter
author: brendacarter
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- M365solutions
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: e39e69fa7c65d7846cc91b3603c5b6ef96f56752
ms.sourcegitcommit: 92f641cad63379bf16417854a43b16b48a71a30a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/12/2020
ms.locfileid: "44724844"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365"></a>Mogelijkheden voor bedreigingsbescherming implementeren in Microsoft 365

[Malware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware), en geavanceerde cyberaanvallen, zoals [fileless bedreigingen](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats), komen vaak voor. Bedrijven moeten zichzelf en hun klanten beschermen. Dergelijke aanvallen kunnen grote problemen veroorzaken voor uw organisatie, variërend van verlies van vertrouwen tot financiële ellende, bedrijfsbedreigende downtime en meer. Bescherming tegen bedreigingen is belangrijk, maar het kan een uitdaging zijn om te bepalen waar u de tijd, moeite en middelen van uw organisatie richten. 

Microsoft-beveiligingsoplossingen zijn ingebouwd in onze producten en services. Automatiserings- en machine learning-mogelijkheden verminderen de belasting van uw beveiligingsteams om ervoor te zorgen dat de juiste items worden aangepakt. En de kracht van Microsoft-beveiligingsoplossingen is gebaseerd op triljoenen signalen die we dagelijks verwerken in onze [Intelligent Security Graph.](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph) Microsoft 365-beveiligingsoplossingen omvatten [Microsoft Threat Protection,](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)een oplossing die signalen over uw e-mail, gegevens, apparaten en identiteiten samenbrengt om een beeld te schetsen van geavanceerde bedreigingen tegen uw organisatie.

Bekijk deze video voor een overzicht van het implementatieproces.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

Gebruik dit artikel als een handleiding voor het implementeren van uw oplossing voor bedreigingsbescherming.

## <a name="threat-protection-in-microsoft-365-e5"></a>Bescherming tegen bedreigingen in Microsoft 365 E5

[Met Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) u uw organisatie beschermen met adaptieve, ingebouwde intelligentie. Met de functies voor bedreigingsbescherming in Microsoft 365 E5 u geavanceerde bedreigingen, gecompromitteerde identiteiten en schadelijke acties in uw on-premises en cloudomgevingen detecteren en onderzoeken.

In Microsoft 365 E5 zijn de mogelijkheden voor bedreigingsbescherming standaard geïntegreerd. Signalen van elke mogelijkheid voegen kracht toe aan het algemene vermogen om bedreigingen te detecteren en erop te reageren. De gecombineerde reeks mogelijkheden biedt de beste bescherming voor organisaties, met name multinationale organisaties, in vergelijking met het uitvoeren van niet-Microsoft-producten. De volgende afbeelding toont de bedreigingenbeschermingsservices en -mogelijkheden in Microsoft 365 E5 die in dit artikel worden beschreven.

![Overzicht van microsoft-bedreigingsbeveiliging](../media/solutions-architecture-center/deploy-threat-protection-across-m365-overview.png)

Zodra u een van de geavanceerde mogelijkheden voor bedreigingsbescherming implementeert, u Microsoft Threat Protection inschakelen, waardoor de signalen en gegevens op één plaats worden samengebracht. 

![Conceptuele illustratie van het dashboard van Microsoft Threat Protection](../media/solutions-architecture-center/deploy-threat-protection-across-m365-mtp.png)

In de volgende afbeelding wordt een aanbevolen pad weergegeven voor het implementeren van deze afzonderlijke mogelijkheden. 

![M365 bedreigingsbeschermingssignalen](../media/solutions-architecture-center/deploy-threat-protection-across-m365.png)

|Oplossing/mogelijkheden  |Beschrijving  |
|---------|---------|
|Meervoudige verificatie en voorwaardelijke toegang     |Bescherm tegen gecompromitteerde identiteiten en apparaten. Begin met deze bescherming omdat het fundamenteel is. De in deze richtlijnen aanbevolen configuratie bevat Azure AD Identity Protection als voorwaarde.     |
|Azure Advanced Threat Protection     |  Een cloudgebaseerde beveiligingsoplossing die uw on-premises Active Directory-signalen gebruikt om geavanceerde bedreigingen, gecompromitteerde identiteiten en schadelijke insider-acties gericht op uw organisatie te identificeren, te detecteren en te onderzoeken. Focus op deze volgende omdat het beschermt uw on-prem en uw cloud-infrastructuur, heeft geen afhankelijkheden of vereisten, en kan onmiddellijk voordeel bieden.       | 
|Office 365 Advanced Threat Protection     | Beschermt uw organisatie tegen schadelijke bedreigingen van e-mailberichten, koppelingen (URL's) en samenwerkingstools. Beveiligingen voor malware, phishing, spoofing en andere soorten aanvallen. Dit wordt vervolgens aanbevolen omdat het implementeren van het besturingselement wijzigen, migreren van het bestaande systeem en andere overwegingen langer kunnen duren. <br><br>Opmerking: Zorg ervoor dat u ook de mogelijkheden voor bedreigingsbeveiliging configureert die zijn opgenomen in alle Office 365-abonnementen (Exchange Online Protection).       |
|Microsoft Defender Advanced Threat Protection    | Een endpoint protection platform dat helpt bij het voorkomen, detecteren, onderzoeken en reageren op geavanceerde bedreigingen. Dit duurt langer om te implementeren, maar kan parallel met de andere mogelijkheden worden gedaan als andere beheerders verantwoordelijk zijn.   |
|Microsoft Cloud App Security     |   Een cloudtoegangsbeveiligingsmakelaar voor detectie, onderzoek en governance. U dit vroeg mogelijk maken om te beginnen met het verzamelen van gegevens en inzichten. Het implementeren van informatie en andere gerichte beveiliging in uw SaaS-apps houdt planning in en kan meer tijd in beslag nemen.       | 

> [!TIP]
> Organisaties met meerdere beveiligingsteams kunnen deze mogelijkheden parallel implementeren.

## <a name="deploy-your-threat-protection-solution"></a>Uw oplossing voor bedreigingsbescherming implementeren

Om ervoor te zorgen dat uw organisatie over de best mogelijke beveiliging beschikt, stelt u uw beveiligingsoplossing in en implementeer deze om de volgende stappen op te nemen:

1. [Beleid voor meerstapverificatie en beleid voor voorwaardelijke toegang instellen](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [Azure Advanced Threat Protection configureren](deploy-threat-protection-configure.md#step-2-configure-azure-advanced-threat-protection)
3. [Microsoft Threat Protection inschakelen](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-threat-protection)
4. [Geavanceerde bedreigingsbeveiliging van Office 365 configureren](deploy-threat-protection-configure.md#step-4-configure-office-365-advanced-threat-protection)
5. [Geavanceerde bedreigingsbeveiliging van Microsoft Defender configureren](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-advanced-threat-protection)
6. [Beveiliging van Microsoft Cloud App configureren](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [Status bewaken en acties uitvoeren](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [Treingebruikers](deploy-threat-protection-configure.md#step-8-train-users)

Uw functies voor bedreigingsbeveiliging kunnen parallel worden geconfigureerd, dus als u meerdere beveiligingsteams hebt die verantwoordelijk zijn voor verschillende services, kunnen ze tegelijkertijd de beveiligingsfuncties van uw organisatie configureren. In het volgende diagram wordt het proces op hoog niveau voor het implementeren van mogelijkheden voor bedreigingsbescherming weergedrukt. 

![Proces voor het implementeren van mogelijkheden voor bedreigingsbescherming](../media/solutions-architecture-center/deploy-threat-protection-across-m365-grid.png) 


