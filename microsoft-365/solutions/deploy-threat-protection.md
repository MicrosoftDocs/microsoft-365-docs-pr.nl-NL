---
title: Mogelijkheden voor bedreigingsbeveiliging implementeren in Microsoft 365
description: Meer informatie over het implementeren van bedreigingsbeveiligingsservices en beveiligingsfuncties in Microsoft 365 E5.
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
audience: Admin
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 3156e6bc7715db9847b295add7850dcbd0ff6642
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918404"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365"></a>Mogelijkheden voor bedreigingsbeveiliging implementeren in Microsoft 365

[Malware](/windows/security/threat-protection/intelligence/understanding-malware)en geavanceerde cyberaanvallen, zoals [bestandsloze](/windows/security/threat-protection/intelligence/fileless-threats)bedreigingen, komen vaak voor. Bedrijven moeten zichzelf en hun klanten beschermen met effectieve IT-beveiligingsmogelijkheden. Cyberaanvallen kunnen grote problemen veroorzaken voor uw organisatie, variërend van een verlies van vertrouwen tot financiële problemen, bedrijfsbedreigende downtime en meer. Bescherming tegen bedreigingen is belangrijk, maar het kan lastig zijn om te bepalen waar u de tijd, moeite en resources van uw organisatie kunt concentreren. 

Microsoft-beveiligingsoplossingen zijn ingebouwd in onze producten en services. Automatiserings- en machine learning-mogelijkheden verminderen de belasting van uw beveiligingsteams om ervoor te zorgen dat de juiste items worden aangepakt. En de kracht van Microsoft-beveiligingsoplossingen is gebaseerd op triljoenen signalen die we elke dag verwerken in [onze Intelligent Security Graph.](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph) Microsoft 365-beveiligingsoplossingen zijn [Microsoft 365 Defender,](../security/mtp/microsoft-threat-protection.md)een oplossing waarmee signalen in uw e-mail, gegevens, apparaten en identiteiten worden verzameld om een beeld te schetsen van geavanceerde bedreigingen tegen uw organisatie.


Bekijk deze video voor een overzicht van het implementatieproces.
<br><br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

Gebruik dit artikel als handleiding voor het implementeren van uw oplossing voor bedreigingsbeveiliging.

## <a name="threat-protection-in-microsoft-365-e5"></a>Bedreigingsbeveiliging in Microsoft 365 E5

[Met Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) kunt u uw organisatie beschermen met adaptieve, ingebouwde intelligentie. Met de functies voor bedreigingsbeveiliging in Microsoft 365 E5 kunt u geavanceerde bedreigingen, gecompromitteerde identiteiten en schadelijke acties detecteren en onderzoeken in uw on-premises en cloudomgeving.

In Microsoft 365 E5 zijn de mogelijkheden voor bedreigingsbeveiliging standaard geïntegreerd. Signalen van elke mogelijkheid vergroten de algehele mogelijkheid om bedreigingen op te sporen en te beantwoorden. De gecombineerde set mogelijkheden biedt de beste bescherming voor organisaties, met name multinationale organisaties, in vergelijking met het uitvoeren van niet-Microsoft-producten. In de volgende afbeelding worden de services en mogelijkheden voor bedreigingsbeveiliging in Microsoft 365 E5 weergegeven die in dit artikel worden beschreven.

![Overzicht van Microsoft 365 Defender](../media/deploy-threat-protection/deploy-threat-protection-across-m365-overview.png)

Zodra u een van de Defender voor Office 365-mogelijkheden implementeert, kunt u Microsoft 365 Defender in- en in- en uit- zetten, zodat de signalen en gegevens op één plaats worden samengebouwd. 

![Conceptuele afbeelding van microsoft 365 Defender-dashboard](../media/deploy-threat-protection/deploy-threat-protection-across-m365-mtp.png)

In de volgende afbeelding wordt een aanbevolen pad weergegeven voor het implementeren van deze afzonderlijke mogelijkheden. 

![M365-bedreigingssignalen](../media/deploy-threat-protection/deploy-threat-protection-across-m365.png)

|Oplossing/mogelijkheden  |Beschrijving  |
|---------|---------|
|Meervoudige verificatie en Voorwaardelijke toegang     |Bescherm u tegen gecompromitteerde identiteiten en apparaten. Begin met deze beveiliging omdat deze basis is. De configuratie die in deze richtlijn wordt aanbevolen, bevat Azure AD Identity Protection als een vereiste.     |
|Microsoft Defender for Identity     |  Een cloudgebaseerde beveiligingsoplossing die gebruik maakt van uw on-premises AD DS-signalen (Active Directory Domain Services) om geavanceerde bedreigingen, gecompromitteerde identiteiten en schadelijke insideracties die zijn gericht op uw organisatie te identificeren, te detecteren en te onderzoeken. Focus vervolgens op Microsoft Defender voor identiteit omdat het uw on-premises en cloudinfrastructuur beschermt, geen afhankelijkheden of vereisten heeft en directe beveiligingsvoordelen kan bieden. | 
|Microsoft Defender voor Office 365     | Beschermt uw organisatie tegen schadelijke bedreigingen die worden veroorzaakt door e-mailberichten, koppelingen (URL's) en samenwerkingshulpmiddelen. Beveiligingen voor malware, phishing, spoofing en andere soorten aanvallen. Het configureren van Microsoft Defender voor Office 365 wordt vervolgens aanbevolen, omdat het implementeren van beheer, het migreren van instellingen van het bestaande systeem en andere aandachtspunten langer kan duren. <br><br>Opmerking: Zorg ervoor dat u de mogelijkheden voor bedreigingsbeveiliging configureert die zijn opgenomen in alle Office 365-abonnementen (Exchange Online Protection).       |
|Microsoft Defender for Endpoint    | Een eindpuntbeveiligingsplatform waarmee geavanceerde bedreigingen worden voorkomen, gedetecteerd, onderzocht en beantwoord.  Het kan enige tijd duren om Defender voor Eindpunt te implementeren, maar de configuratie kan parallel met andere mogelijkheden worden uitgevoerd.   |
|Microsoft Cloud App Security     |   Een beveiligingsagent voor cloudtoegang voor detectie, onderzoek en beheer. U kunt Microsoft Cloud App Security vroeg inschakelen om te beginnen met het verzamelen van gegevens en inzichten. Bij het implementeren van informatie en andere gerichte beveiliging in uw SaaS-apps is planning nodig en kan het meer tijd kosten.       | 

> [!TIP]
> Organisaties met meerdere beveiligingsteams kunnen deze mogelijkheden parallel implementeren.

## <a name="deploy-your-threat-protection-solution"></a>Uw bedreigingsbeveiligingsoplossing implementeren

Als u ervoor wilt zorgen dat uw organisatie de best mogelijke beveiliging biedt, stelt u uw beveiligingsoplossing in en implementeert u deze om de volgende stappen uit te voeren:

1. [Beleidsregels voor meervoudige verificatie en voorwaardelijke toegang instellen](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [Microsoft Defender configureren voor identiteit](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)
3. [Microsoft 365 Defender in-](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender)
4. [Defender configureren voor Office 365](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)
5. [Microsoft Defender configureren voor eindpunt](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)
6. [Microsoft Cloud App-beveiliging configureren](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [Status controleren en acties uitvoeren](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [Gebruikers wegwijs maken](deploy-threat-protection-configure.md#step-8-train-users)

Uw beveiligingsfuncties voor bedreigingen kunnen parallel worden geconfigureerd, dus als u meerdere netwerkbeveiligingsteams hebt die verantwoordelijk zijn voor verschillende services, kunnen ze de beveiligingsfuncties van uw organisatie tegelijkertijd configureren. In het volgende diagram ziet u het proces op hoog niveau voor het implementeren van mogelijkheden voor bedreigingsbeveiliging. 

![Proces voor het implementeren van mogelijkheden voor bedreigingsbeveiliging](../media/deploy-threat-protection/deploy-threat-protection-across-m365-grid.png)