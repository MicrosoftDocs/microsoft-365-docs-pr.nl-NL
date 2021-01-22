---
title: Bedreigingsbeveiliging voor netwerkbeveiliging implementeren in Microsoft 365
description: Informatie over het implementeren van bedreigingsbeveiligingsservices en MOGELIJKHEDEN voor IT-netwerkbeveiliging in Microsoft 365 E5.
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 79352aca2012e6615f41b19f4a77fc5cf125f4c4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926748"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365"></a>Functionaliteit voor bedreigingsbeveiliging implementeren in Microsoft 365

[Malware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware)en geavanceerde cyberaanvallen, zoals [](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats)bestandsloze bedreigingen, komen vaak voor. Bedrijven moeten zichzelf en hun klanten beschermen met effectieve beveiligingsmogelijkheden voor het IT-netwerk. Dergelijke aanvallen kunnen voor uw organisatie grote problemen veroorzaken, variërend van verlies van vertrouwen tot financiële problemen, uitvaltijd van bedrijfsproblemen en meer. Beveiligen tegen bedreigingen is belangrijk, maar het kan lastig zijn om te bepalen waar u de tijd, inspanning en resources van uw organisatie op moet concentreren. 

Microsoft-beveiligingsoplossingen zijn ingebouwd in onze producten en services. Automatiserings- en machine learning-mogelijkheden verminderen de belasting van uw beveiligingsteams om ervoor te zorgen dat de juiste items worden geadresseerd. En de kracht van de beveiligingsoplossingen van het Microsoft-netwerk is gebaseerd op de signalen die we elke dag verwerken in [Intelligent Security Graph.](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph) Microsoft 365-beveiligingsoplossingen omvatten [Microsoft 365 Defender,](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)een oplossing waarmee u via e-mail, gegevens, apparaten en identiteiten een beeld kunt vormen van geavanceerde bedreigingen voor uw organisatie.


Bekijk deze video voor een overzicht van het implementatieproces.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

Gebruik dit artikel als richtlijn voor het implementeren van uw oplossing voor bedreigingsbeveiliging.

## <a name="threat-protection-in-microsoft-365-e5"></a>Bedreigingsbeveiliging in Microsoft 365 E5

[Met Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) kunt u uw organisatie beschermen met adaptieve, ingebouwde intelligentie. Met de functies voor bedreigingsbeveiliging in Microsoft 365 E5 kunt u geavanceerde bedreigingen, gekromde identiteiten en kwaadaardige acties in uw on-premises en cloudomgeving detecteren en onderzoeken.

In Microsoft 365 E5 zijn risicobeveiligingsfuncties standaard geïntegreerd. Signalen van elke mogelijkheid voegen kracht toe aan de algehele mogelijkheid om bedreigingen te detecteren en te beantwoorden. De gecombineerde set mogelijkheden biedt de beste bescherming voor organisaties, met name multinationale organisaties, in vergelijking met het uitvoeren van niet-Microsoft-producten. In de volgende afbeelding worden de services en mogelijkheden voor bedreigingsbeveiliging in Microsoft 365 E5 weergegeven die in dit artikel worden beschreven.

![Overzicht van Microsoft 365 Defender](../media/solutions-architecture-center/deploy-threat-protection-across-m365-overview.png)

Zodra u een van de mogelijkheden van Defender voor Office 365 implementeert, kunt u Microsoft 365 Defender in dienst gaan, waarmee de signalen en gegevens op één plaats worden samenbrengen. 

![Conceptuele afbeelding van Microsoft 365 Defender-dashboard](../media/solutions-architecture-center/deploy-threat-protection-across-m365-mtp.png)

In de volgende afbeelding wordt een aanbevolen pad weergegeven voor het implementeren van deze afzonderlijke mogelijkheden. 

![Risicobeveiligingssignalen voor M365](../media/solutions-architecture-center/deploy-threat-protection-across-m365.png)

|Oplossing/mogelijkheden  |Beschrijving  |
|---------|---------|
|Meervoudige verificatie en voorwaardelijke toegang     |Bescherm u tegen gekromde identiteiten en apparaten. Begin met deze beveiliging omdat deze een basis heeft. De configuratie die in deze richtlijnen wordt aanbevolen, bevat Azure AD-identiteitsbescherming als vereiste.     |
|Microsoft Defender for Identity     |  Een cloudgebaseerde beveiligingsoplossing die gebruik maakt van uw on-premises Active Directory-signalen voor het identificeren, detecteren en onderzoeken van geavanceerde bedreigingen, gekromde identiteiten en kwaadaardige Insider-acties die zijn gericht op uw organisatie. Richt u vervolgens op Microsoft Defender voor identiteit omdat dit uw on-prem en uw cloudinfrastructuur beschermt, geen afhankelijkheden of vereisten heeft en direct voordeel kan bieden.       | 
|Microsoft Defender voor Office 365     | Beschermt uw organisatie tegen schadelijke bedreigingen in plaats van e-mailberichten, koppelingen (URL's) en samenwerkingshulpmiddelen. Beveiligingen voor malware, phishing, spoofing en andere typen aanvallen. Het configureren van Microsoft Defender voor Office 365 wordt aanbevolen, omdat de implementatie van wijzigingsbeheer, het migreren van instellingen van het huidige systeem en andere overwegingen langer kan duren. <br><br>Opmerking: Configureer de mogelijkheden voor bedreigingsbeveiliging die deel uit maken van alle Office 365-abonnementen (Exchange Online Protection).       |
|Microsoft Defender for Endpoint    | Een eindpuntbeveiligingsplatform waarmee geavanceerde bedreigingen kunnen worden voorkomen, gedetecteerd, onderzocht en erop kan worden gereageerd.  De implementatie van Defender voor eindpunt kan enige tijd duren, maar de configuratie kan parallel met andere mogelijkheden worden uitgevoerd.   |
|Microsoft Cloud App Security     |   Een beveiligingsadviseur voor cloudtoegang voor detectie, onderzoek en beheermodel. U kunt Microsoft Cloud App Security vroeg inschakelen om te beginnen met het verzamelen van gegevens en inzichten. Het implementeren van informatie en andere gerichte beveiliging in uw SaaS-apps houdt planning in en kan meer tijd in nemen.       | 

> [!TIP]
> Organisaties met meerdere beveiligingsteams kunnen deze mogelijkheden parallel implementeren.

## <a name="deploy-your-threat-protection-solution"></a>Uw oplossing voor bedreigingsbeveiliging implementeren

Om ervoor te zorgen dat uw organisatie de best mogelijke bescherming biedt, stelt u uw beveiligingsoplossing in en implementeert u deze met de volgende stappen:

1. [Meervoudige verificatie en beleidsregels voor voorwaardelijke toegang instellen](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [Microsoft Defender configureren voor identiteit](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)
3. [Microsoft 365 Defender in te zetten](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender)
4. [Defender configureren voor Office 365](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)
5. [Microsoft Defender voor eindpunt configureren](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)
6. [Beveiliging van Microsoft Cloud-apps configureren](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [Status controleren en acties uitvoeren](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [Gebruikers wegwijs maken](deploy-threat-protection-configure.md#step-8-train-users)

Uw functies voor bedreigingsbeveiliging kunnen parallel worden geconfigureerd, dus als u meerdere beveiligingsteams hebt die verantwoordelijk zijn voor verschillende services, kunnen ze de beveiligingsfuncties van uw organisatie tegelijkertijd configureren. In het volgende diagram ziet u het geavanceerde proces voor het implementeren van mogelijkheden voor risicobeveiliging. 

![Proces voor het implementeren van mogelijkheden voor bedreigingsbeveiliging](../media/solutions-architecture-center/deploy-threat-protection-across-m365-grid.png) 
