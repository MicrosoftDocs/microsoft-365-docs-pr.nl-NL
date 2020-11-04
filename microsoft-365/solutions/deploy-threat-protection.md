---
title: Beveiligings bedreiging voor netwerkbeveiliging implementeren in Microsoft 365
description: Meer informatie over het implementeren van beveiligingsfuncties voor Threat Protection en de functies voor IT-netwerken in Microsoft 365 E5.
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 1bf06c605290dc94f64da6c2aabca3683c234c9a
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906749"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365"></a>Functies voor bedreigingsbeveiliging implementeren in Microsoft 365

Malware en geavanceerde cyberattacks, zoals bedreigingen met een [kwaadaardige](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware) [bedreiging](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats), zijn een gangbare gebeurtenis. Bedrijven dienen zichzelf te beschermen en hun klanten met de juiste beveiligingsfuncties voor IT-netwerken. Dit kan leiden tot grote problemen voor uw organisatie, variërend van een vertrouwensrelatie met financieel Woes, bedrijfsrisico's en meer. Het is belangrijk om te beschermen tegen bedreigingen, maar het kan lastig zijn om te bepalen waar de tijd, inspanning en resources van uw organisatie zich richten. 

Microsoft-beveiligingsoplossingen zijn ingebouwd in onze producten en services. De mogelijkheden van automatisering en machine learning verlagen de belasting van uw beveiligings teams om te zorgen dat de juiste items zijn geadresseerd. En de sterkte van de beveiligingsoplossingen voor Microsoft-netwerken is ontwikkeld op triljoen punten die elke dag in onze [intelligente beveiligings grafiek](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph)verwerkt. Microsoft 365-beveiligingsoplossingen bestaan uit [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection), een oplossing waarmee signalen voor e-mail, gegevens, apparaten en identiteiten worden gebruikt om een afbeelding van geavanceerde bedreigingen te schilderen tegen uw organisatie.


Bekijk deze video voor een overzicht van het implementatieproces.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

Gebruik dit artikel als leidraad bij het implementeren van uw oplossing voor Threat Protection.

## <a name="threat-protection-in-microsoft-365-e5"></a>Bedreigingsbeveiliging in Microsoft 365 E5

Met [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) kunt u uw organisatie beschermen met adaptieve, ingebouwde informatie. Met de functies voor risico beveiliging in Microsoft 365 E5 kunt u geavanceerde bedreigingen, compromisloze identiteiten en schadelijke acties in de on-premises omgeving en de cloudomgeving detecteren en onderzoeken.

In Microsoft 365 E5 worden de mogelijkheden voor beveiliging van bedreigingen standaard geïntegreerd. Met elke mogelijkheid wordt sterkte toegevoegd aan de algehele mogelijkheid om bedreigingen te detecteren en te reageren. De gecombineerde set mogelijkheden biedt de beste bescherming voor organisaties, met name multicore-organisaties, vergeleken met het werken met niet-Microsoft-producten. In de volgende afbeelding ziet u de Threat Protection-Services en mogelijkheden in Microsoft 365 E5 die in dit artikel worden beschreven.

![Overzicht van Microsoft 365 Defender](../media/solutions-architecture-center/deploy-threat-protection-across-m365-overview.png)

Zodra u de functies van de Defender voor Office 365 implementeert, kunt u Microsoft 365 Defender inschakelen, zodat de signalen en gegevens samen op één plaats worden weer gebracht. 

![Conceptuele afbeelding van het dashboard van Microsoft 365 Defender](../media/solutions-architecture-center/deploy-threat-protection-across-m365-mtp.png)

In de volgende afbeelding wordt een aanbevolen pad getoond voor de implementatie van deze afzonderlijke mogelijkheden. 

![Signalen voor M365 Threat Protection](../media/solutions-architecture-center/deploy-threat-protection-across-m365.png)

|Oplossing/mogelijkheden  |Beschrijving  |
|---------|---------|
|Meervoudige verificatie en voorwaardelijke toegang     |Beveilig tegen met compromisloze identiteiten en apparaten. Begin met deze bescherming omdat dit de basis vormt. De configuratie die in deze richtlijnen wordt aanbevolen bevat Azure AD-identiteitsbeveiliging.     |
|Microsoft Defender for Identity     |  Een op de cloud gebaseerde beveiligingsoplossing waarmee u uw on-premises Active Directory-Signa rekken kunt identificeren, detecteren en onderzoeken, en hoe u geavanceerde bedreigingen, compromisloze identiteiten, en schadelijke Insider-acties die u kunt uitvoeren op uw organisatie. Richt ons op Microsoft Defender voor de identiteit, aangezien dit uw on-premises en de Cloud infrastructuur beschermt, geen afhankelijkheden of vereisten heeft en direct een goede vergoeding kan geven.       | 
|Microsoft Defender voor Office 365     | Beschermt uw organisatie tegen kwaadaardige bedreigingen van e-mailberichten, koppelingen (Url's) en samenwerkingsprogramma's. Beveiligingsmaatregelen voor malware, phishing, spoofing en andere soorten aanval. Het configureren van Microsoft Defender voor Office 365 wordt vervolgens aanbevolen omdat de instelling van het besturingselement wijzigen, het migreren van instellingen van het systeem en andere overwegingen voor de implementatie van de implementatie mogelijk langer duurt. <br><br>Opmerking: Zorg ervoor dat u de mogelijkheden voor beveiliging van bedreigingen configureert die zijn opgenomen in alle Office 365-abonnementen (Exchange Online Protection).       |
|Microsoft Defender voor Eindpunt     | Een Endpoint Protection platform dat helpt bij het voorkomen, analyseren, onderzoeken en beantwoorden van geavanceerde bedreigingen.  Het kan enige tijd duren voor de implementatie van eindpunten voor eindpunten is voltooid, maar de configuratie kan parallel worden uitgevoerd met andere mogelijkheden.   |
|Microsoft Cloud App Security     |   Een beveiligings Broker voor Cloud toegang voor ontdekking, onderzoek en governance. U kunt de beveiliging van Microsoft Cloud-apps vroegtijdig inschakelen om te beginnen met het verzamelen van gegevens en inzichten. Als u informatie implementeert en andere gerichte beveiliging toepast op uw SaaS-apps, moet de planning en tijd in beslag nemen.       | 

> [!TIP]
> Organisaties met meerdere beveiligings teams kunnen deze functionaliteit parallel implementeren.

## <a name="deploy-your-threat-protection-solution"></a>Uw oplossing voor bedreigingsbeveiliging implementeren

Om ervoor te zorgen dat uw organisatie de beste beveiliging heeft, kunt u de volgende stappen uitvoeren om uw beveiligingsoplossing op te zetten en toe te passen:

1. [Multi-factor Authentication en regels voor voorwaardelijke toegang instellen](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [Microsoft Defender configureren voor identiteit](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)
3. [Microsoft 365 Defender inschakelen](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender)
4. [Defender voor Office 365 configureren](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)
5. [Microsoft Defender voor eindpunt configureren](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)
6. [Beveiligingsupdates voor Microsoft Cloud app configureren](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [De status controleren en acties ondernemen](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [Gebruikers wegwijs maken](deploy-threat-protection-configure.md#step-8-train-users)

Uw functies voor beveiliging tegen bedreigingen kunnen parallel worden geconfigureerd, dus als u meerdere netwerk beveiligings teams hebt die verantwoordelijk zijn voor verschillende services, kunnen ze de beveiligingsfuncties van uw organisatie op hetzelfde moment configureren. In het volgende diagram ziet u het proces voor het uitvoeren van bedreigingen voor beveiliging op hoog niveau. 

![Proces voor de implementatie van functies voor bedreigingsbeveiliging](../media/solutions-architecture-center/deploy-threat-protection-across-m365-grid.png) 
