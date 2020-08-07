---
title: Functies voor bedreigingsbeveiliging implementeren in Microsoft 365
description: Meer informatie over het implementeren van Threat Protection-Services en-functies in Microsoft 365 E5.
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
ms.openlocfilehash: 312df25bf4fe2b91bb60b4122378b4457b25723c
ms.sourcegitcommit: b812771805c8b9e92b64deb1928e265e60d80405
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/07/2020
ms.locfileid: "46588182"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365"></a>Functies voor bedreigingsbeveiliging implementeren in Microsoft 365

Malware en geavanceerde cyberattacks, zoals bedreigingen met een [kwaadaardige](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware) [bedreiging](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats), zijn een gangbare gebeurtenis. Bedrijven dienen zichzelf en hun klanten te beschermen. Aanvallen via een aanval kunnen grote problemen veroorzaken voor uw organisatie, variërend van een vertrouwensrelatie met financieel Woes, Business-bedreigen en meer. Het is belangrijk om te beschermen tegen bedreigingen, maar het kan lastig zijn om te bepalen waar de tijd, inspanning en resources van uw organisatie zich richten. 

Microsoft-beveiligingsoplossingen zijn ingebouwd in onze producten en services. De mogelijkheden van automatisering en machine learning verlagen de belasting van uw beveiligings teams om te zorgen dat de juiste items zijn geadresseerd. En de dosering van Microsoft-beveiligingsoplossingen is ontwikkeld op triljoen punten die we elke dag in onze [intelligente beveiligings grafiek](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph)verwerken. Microsoft 365-beveiligingsoplossingen bestaan uit [Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection), waarmee signalen voor uw e-mail, gegevens, apparaten en identiteiten worden gecombineerd om een afbeelding van geavanceerde bedreigingen te schilderen tegen uw organisatie.

Bekijk deze video voor een overzicht van het implementatieproces.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

Gebruik dit artikel als leidraad bij het implementeren van uw oplossing voor Threat Protection.

## <a name="threat-protection-in-microsoft-365-e5"></a>Bedreigingsbeveiliging in Microsoft 365 E5

Met [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) kunt u uw organisatie beschermen met adaptieve, ingebouwde informatie. Met de functies voor risico beveiliging in Microsoft 365 E5 kunt u geavanceerde bedreigingen, compromisloze identiteiten en schadelijke acties in de on-premises omgeving en de cloudomgeving detecteren en onderzoeken.

In Microsoft 365 E5 worden de mogelijkheden voor beveiliging van bedreigingen standaard geïntegreerd. Met elke mogelijkheid wordt sterkte toegevoegd aan de algehele mogelijkheid om bedreigingen te detecteren en te reageren. De gecombineerde set mogelijkheden biedt de beste bescherming voor organisaties, met name multicore-organisaties, vergeleken met het werken met niet-Microsoft-producten. In de volgende afbeelding ziet u de Threat Protection-Services en mogelijkheden in Microsoft 365 E5 die in dit artikel worden beschreven.

![Overzicht van Microsoft Threat Protection](../media/solutions-architecture-center/deploy-threat-protection-across-m365-overview.png)

Zodra u een van de geavanceerde functies voor bedreigingsbeveiliging implementeert, kunt u Microsoft Bedreigingsbeveiliging inschakelen, zodat de signalen en gegevens samen op één plaats worden weer gebracht. 

![Conceptuele illustratie van Microsoft Threat Protection-dashboard](../media/solutions-architecture-center/deploy-threat-protection-across-m365-mtp.png)

In de volgende afbeelding wordt een aanbevolen pad getoond voor de implementatie van deze afzonderlijke mogelijkheden. 

![Signalen voor M365 Threat Protection](../media/solutions-architecture-center/deploy-threat-protection-across-m365.png)

|Oplossing/mogelijkheden  |Beschrijving  |
|---------|---------|
|Meervoudige verificatie en voorwaardelijke toegang     |Beveilig tegen met compromisloze identiteiten en apparaten. Begin met deze bescherming omdat dit de basis vormt. De configuratie die in deze richtlijnen wordt aanbevolen bevat Azure AD-identiteitsbeveiliging.     |
|Azure Advanced Threat Protection     |  Een op de cloud gebaseerde beveiligingsoplossing waarmee u uw on-premises Active Directory-Signa rekken kunt identificeren, detecteren en onderzoeken, en hoe u geavanceerde bedreigingen, compromisloze identiteiten, en schadelijke Insider-acties die u kunt uitvoeren op uw organisatie. Concentreer u op Azure Advanced Threat Protection, aangezien dit uw on-premises en de Cloud infrastructuur beschermt, geen afhankelijkheden of vereisten heeft en direct een goede vergoeding kan geven.       | 
|Office 365 Advanced Threat Protection     | Beschermt uw organisatie tegen kwaadaardige bedreigingen van e-mailberichten, koppelingen (Url's) en samenwerkingsprogramma's. Beveiligingsmaatregelen voor malware, phishing, spoofing en andere soorten aanval. Het configureren van de Advanced Threat Protection van Office 365 wordt op de volgende manieren aangeraden: wijzigings besturing, migratie van instellingen van het systeem en andere aandachtspunten voor de implementatie. <br><br>Opmerking: Zorg ervoor dat u de mogelijkheden voor beveiliging van bedreigingen configureert die zijn opgenomen in alle Office 365-abonnementen (Exchange Online Protection).       |
|Microsoft Defender Advanced Threat Protection    | Een Endpoint Protection platform dat helpt bij het voorkomen, analyseren, onderzoeken en beantwoorden van geavanceerde bedreigingen. Microsoft Defender Advanced Threat Protection kan enige tijd duren voor de implementatie, maar u kunt de configuratie parallel met andere mogelijkheden voltooien.   |
|Microsoft Cloud App Security     |   Een beveiligings Broker voor Cloud toegang voor ontdekking, onderzoek en governance. U kunt de beveiliging van Microsoft Cloud-apps vroegtijdig inschakelen om te beginnen met het verzamelen van gegevens en inzichten. Als u informatie implementeert en andere gerichte beveiliging toepast op uw SaaS-apps, moet de planning en tijd in beslag nemen.       | 

> [!TIP]
> Organisaties met meerdere beveiligings teams kunnen deze functionaliteit parallel implementeren.

## <a name="deploy-your-threat-protection-solution"></a>Uw oplossing voor bedreigingsbeveiliging implementeren

Om ervoor te zorgen dat uw organisatie de beste beveiliging heeft, kunt u de volgende stappen uitvoeren om uw beveiligingsoplossing op te zetten en toe te passen:

1. [Multi-factor Authentication en regels voor voorwaardelijke toegang instellen](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [Azure Advanced Threat Protection configureren](deploy-threat-protection-configure.md#step-2-configure-azure-advanced-threat-protection)
3. [Microsoft Threat Protection inschakelen](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-threat-protection)
4. [Office 365 Advanced Threat Protection configureren](deploy-threat-protection-configure.md#step-4-configure-office-365-advanced-threat-protection)
5. [Microsoft Defender Advanced Threat Protection configureren](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-advanced-threat-protection)
6. [Beveiligingsupdates voor Microsoft Cloud app configureren](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [De status controleren en acties ondernemen](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [Gebruikers wegwijs maken](deploy-threat-protection-configure.md#step-8-train-users)

Uw functies voor risico beveiliging kunnen parallel worden geconfigureerd, dus als u meerdere beveiligings teams verantwoordelijk hebt voor verschillende services, kunnen ze de beveiligingsfuncties van uw organisatie op hetzelfde moment configureren. In het volgende diagram ziet u het proces voor het uitvoeren van bedreigingen voor beveiliging op hoog niveau. 

![Proces voor de implementatie van functies voor bedreigingsbeveiliging](../media/solutions-architecture-center/deploy-threat-protection-across-m365-grid.png) 


