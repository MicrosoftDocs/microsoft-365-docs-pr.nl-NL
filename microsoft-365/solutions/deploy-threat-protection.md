---
title: Functionaliteit voor bedreigingsbeveiliging implementeren in Microsoft 365
description: Informatie over het implementeren van services voor bedreigingsbeveiliging en beveiligingsmogelijkheden in Microsoft 365 E5.
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
ms.openlocfilehash: a2d758ca4628e4cd5f73e77d0d86946e350163c5
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/04/2021
ms.locfileid: "50424085"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365"></a>Functionaliteit voor bedreigingsbeveiliging implementeren in Microsoft 365

[Malware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware)en geavanceerde cyberaanvallen, zoals [](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats)bestandsloze bedreigingen, komen vaak voor. Bedrijven moeten zichzelf en hun klanten beschermen met effectieve IT-beveiligingsmogelijkheden. Cyberaanvallen kunnen grote problemen voor uw organisatie veroorzaken, variërend van verlies van vertrouwen tot financiële problemen, uitval van bedrijfsproblemen en meer. Beveiligen tegen bedreigingen is belangrijk, maar het kan lastig zijn om te bepalen waar u de tijd, inspanning en resources van uw organisatie op moet concentreren. 

Microsoft-beveiligingsoplossingen zijn ingebouwd in onze producten en services. Automatiserings- en machine learning-mogelijkheden verminderen de belasting van uw beveiligingsteams om ervoor te zorgen dat de juiste items worden aangepakt. En de kracht van beveiligingsoplossingen van Microsoft is gebaseerd op de signalen die we elke dag verwerken in [Intelligent Security Graph.](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph) Microsoft 365-beveiligingsoplossingen omvatten [Microsoft 365 Defender,](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)een oplossing waarmee u via e-mail, gegevens, apparaten en identiteiten een beeld kunt krijgen van geavanceerde bedreigingen in uw organisatie.


Bekijk deze video voor een overzicht van het implementatieproces.
<br><br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

>[!Note]
>In deze video worden de eerdere namen van producten en functies van Threat Protection gebruikt, maar de concepten zijn hetzelfde. Er wordt aan een update van deze video uitgevoerd.
>

Gebruik dit artikel als richtlijn voor het implementeren van uw oplossing voor bedreigingsbeveiliging.

## <a name="threat-protection-in-microsoft-365-e5"></a>Bedreigingsbeveiliging in Microsoft 365 E5

[Met Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) kunt u uw organisatie beschermen met adaptieve, ingebouwde intelligentie. Met de functies voor bedreigingsbeveiliging in Microsoft 365 E5 kunt u geavanceerde bedreigingen, gekromde identiteiten en kwaadaardige acties in uw on-premises en cloudomgeving detecteren en onderzoeken.

In Microsoft 365 E5 zijn risicobeveiligingsfuncties standaard geïntegreerd. Signalen van elke mogelijkheid dragen kracht bij aan de algehele mogelijkheid om bedreigingen te detecteren en te beantwoorden. De gecombineerde set mogelijkheden biedt de beste bescherming voor organisaties, met name multinationale organisaties, in vergelijking met het uitvoeren van niet-Microsoft-producten. In de volgende afbeelding worden de services en mogelijkheden voor bedreigingsbeveiliging in Microsoft 365 E5 weergegeven die in dit artikel worden beschreven.

![Overzicht van Microsoft 365 Defender](../media/deploy-threat-protection/deploy-threat-protection-across-m365-overview.png)

Zodra u een van de mogelijkheden van Defender voor Office 365 implementeert, kunt u Microsoft 365 Defender in turnen, waarmee de signalen en gegevens op één plaats worden samenbrengen. 

![Conceptuele afbeelding van Microsoft 365 Defender-dashboard](../media/deploy-threat-protection/deploy-threat-protection-across-m365-mtp.png)

In de volgende afbeelding wordt een aanbevolen pad weergegeven voor het implementeren van deze afzonderlijke mogelijkheden. 

![Risicobeveiligingssignalen voor M365](../media/deploy-threat-protection/deploy-threat-protection-across-m365.png)

|Oplossing/mogelijkheden  |Beschrijving  |
|---------|---------|
|Meervoudige verificatie en voorwaardelijke toegang     |Bescherm u tegen gekromde identiteiten en apparaten. Begin met deze beveiliging, omdat het een basis biedt. De configuratie die in deze richtlijnen wordt aanbevolen, bevat Azure AD-identiteitsbescherming als vereiste.     |
|Microsoft Defender for Identity     |  Een cloudgebaseerde beveiligingsoplossing die gebruik maakt van uw on-premises AD DS (Active Directory Domain Services) geeft aan dat u geavanceerde bedreigingen, gekromde identiteiten en kwaadaardige insideracties die zijn gericht op uw organisatie, kunt identificeren, detecteren en onderzoeken. Richt u vervolgens op Microsoft Defender voor identiteit omdat het uw on-premises en cloudinfrastructuur beschermt, geen afhankelijkheden of vereisten heeft en direct beveiligingsvoordelen kan bieden. | 
|Microsoft Defender voor Office 365     | Beschermt uw organisatie tegen schadelijke bedreigingen in plaats van e-mailberichten, koppelingen (URL's) en samenwerkingshulpmiddelen. Beveiligingen voor malware, phishing, spoofing en andere typen aanvallen. Het configureren van Microsoft Defender voor Office 365 wordt aanbevolen, omdat het dan mogelijk is om de besturing te wijzigen, de instellingen vanuit het systeem te migreren en andere zaken langer kunnen duren om de implementatie uit te zetten. <br><br>Opmerking: Configureer de mogelijkheden voor bedreigingsbeveiliging die deel uit maken van alle Office 365-abonnementen (Exchange Online Protection).       |
|Microsoft Defender for Endpoint    | Een eindpuntbeveiligingsplatform waarmee geavanceerde bedreigingen kunnen worden voorkomen, gedetecteerd, onderzocht en beantwoord.  De implementatie van Defender voor eindpunt kan enige tijd duren, maar de configuratie kan parallel met andere mogelijkheden worden uitgevoerd.   |
|Microsoft Cloud App Security     |   Een beveiligingsadviseur voor cloudtoegang voor detectie, onderzoek en beheermodel. U kunt Microsoft Cloud App Security vroeg inschakelen om te beginnen met het verzamelen van gegevens en inzichten. Bij het implementeren van informatie en andere gerichte bescherming in uw SaaS-apps moet u planningen uitvoeren en dit kan meer tijd kosten.       | 

> [!TIP]
> Organisaties met meerdere beveiligingsteams kunnen deze mogelijkheden parallel implementeren.

## <a name="deploy-your-threat-protection-solution"></a>Uw oplossing voor bedreigingsbeveiliging implementeren

Om ervoor te zorgen dat uw organisatie de best mogelijke bescherming biedt, stelt u uw beveiligingsoplossing in en implementeert u deze met de volgende stappen:

1. [Meervoudige verificatie en beleidsregels voor voorwaardelijke toegang instellen](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [Microsoft Defender configureren voor identiteit](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)
3. [Microsoft 365 Defender in te zetten](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender)
4. [Defender voor Office 365 configureren](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)
5. [Microsoft Defender voor eindpunt configureren](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)
6. [Beveiliging van Microsoft Cloud-apps configureren](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [Status controleren en acties uitvoeren](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [Gebruikers wegwijs maken](deploy-threat-protection-configure.md#step-8-train-users)

Uw functies voor bedreigingsbeveiliging kunnen parallel worden geconfigureerd, dus als u meerdere netwerkbeveiligingsteams hebt die verantwoordelijk zijn voor verschillende services, kunnen ze de beveiligingsfuncties van uw organisatie tegelijkertijd configureren. In het volgende diagram ziet u het geavanceerde proces voor het implementeren van mogelijkheden voor risicobeveiliging. 

![Proces voor het implementeren van mogelijkheden voor bedreigingsbeveiliging](../media/deploy-threat-protection/deploy-threat-protection-across-m365-grid.png) 
