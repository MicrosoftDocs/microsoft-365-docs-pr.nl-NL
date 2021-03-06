---
title: Mogelijkheden voor bedreigingsbeveiliging implementeren in Microsoft 365
description: Krijg een overzicht van services voor bedreigingsbeveiliging en beveiligingsfuncties in Microsoft 365 E5. Bescherm uw gebruikersaccounts, apparaten, e-mailinhoud en meer met Microsoft 365 E5.
keywords: microsoft threat protection, defender, setup, advanced threat protection, security, microsoft 365 E5, protect devices
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
audience: ITPro
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 4008f4e0198058e2b13de62c34697e3034d499b2
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583218"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365-e5"></a>Mogelijkheden voor bedreigingsbeveiliging implementeren in Microsoft 365 E5

Deze oplossing beschrijft krachtige mogelijkheden voor bedreigingsbeveiliging in Microsoft 365 E5 en waarom bedreigingsbeveiliging belangrijk is. Krijg een overzicht van bedreigingsbeveiliging in Microsoft 365 E5 en bekijk hoe u de installatie en configuratie voor uw organisatie kunt benaderen.

## <a name="why-threat-protection-is-important"></a>Waarom bedreigingsbeveiliging belangrijk is 

[Malware](/windows/security/threat-protection/intelligence/understanding-malware)en geavanceerde cyberaanvallen, zoals [bestandsloze](/windows/security/threat-protection/intelligence/fileless-threats)bedreigingen, komen vaak voor. Bedrijven moeten zichzelf en hun klanten beschermen met effectieve IT-beveiligingsmogelijkheden. Cyberaanvallen kunnen grote problemen veroorzaken voor uw organisatie, variërend van een verlies van vertrouwen tot financiële problemen, bedrijfsbedreigende downtime en meer. Bescherming tegen bedreigingen is belangrijk, maar het kan lastig zijn om te bepalen waar u de tijd, moeite en resources van uw organisatie kunt concentreren. Microsoft 365 E5 kan u helpen. 

## <a name="threat-protection-in-microsoft-365-e5"></a>Bedreigingsbeveiliging in Microsoft 365 E5

Microsoft-beveiligingsoplossingen zijn ingebouwd in onze producten en services. Automatiserings- en machine learning-mogelijkheden verminderen de belasting van uw beveiligingsteams om ervoor te zorgen dat de juiste items worden aangepakt. De kracht van Microsoft-beveiligingsoplossingen is gebaseerd op triljoenen signalen die we elke dag verwerken in onze [intelligente Graph.](/graph/security-concept-overview) Microsoft 365 beveiligingsoplossingen zijn [Microsoft 365 Defender,](../security/defender/microsoft-365-defender.md)een oplossing waarmee signalen in uw e-mail, gegevens, apparaten en identiteiten worden verzameld om een beeld te schetsen van geavanceerde bedreigingen tegen uw organisatie.

[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) kunt u uw organisatie beschermen met adaptieve, ingebouwde intelligentie. Met de beveiligingsmogelijkheden in Microsoft 365 E5 kunt u geavanceerde bedreigingen, gecompromitteerde identiteiten en schadelijke acties in uw omgeving detecteren en onderzoeken (on-premises en in de cloud).

## <a name="better-protection-with-integration"></a>Betere beveiliging met integratie

In Microsoft 365 E5 zijn de mogelijkheden voor bedreigingsbeveiliging standaard geïntegreerd. Signalen van elke mogelijkheid vergroten de algehele mogelijkheid om bedreigingen op te sporen en te beantwoorden. De gecombineerde set mogelijkheden biedt de beste bescherming voor organisaties, met name multinationale organisaties, in vergelijking met het uitvoeren van niet-Microsoft-producten. In de volgende afbeelding worden de services en mogelijkheden voor bedreigingsbeveiliging weergegeven die in dit artikel worden beschreven.

![Overzicht van Microsoft 365 Defender](../media/deploy-threat-protection/deploy-threat-protection-across-m365-overview.png)

Microsoft 365 Defender brengt de signalen en gegevens samen in een [geïntegreerd Microsoft 365 beveiligingscentrum.](/microsoft-365/security/defender/overview-security-center) 

> [!div class="mx-imgBorder"]
> ![Conceptuele afbeelding van Microsoft 365 Defender-dashboard](../media/deploy-threat-protection/deploy-threat-protection-across-m365-mtp.png)

## <a name="deployment-overview"></a>Overzicht van implementatie

In de volgende afbeelding wordt een aanbevolen pad weergegeven voor het implementeren van deze afzonderlijke mogelijkheden. 

> [!div class="mx-imgBorder"]
> ![M365-bedreigingssignalen](../media/deploy-threat-protection/deploy-threat-protection-across-m365.png)

Bekijk deze video voor een overzicht van het implementatieproces.
<br><br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

In de volgende tabel worden de verschillende oplossingen/mogelijkheden beschreven die u kunt configureren en wat ze doen.

|Stap |Oplossing/mogelijkheden  |Beschrijving  |
|--|---------|---------|
| 1 |[Meervoudige verificatie en Voorwaardelijke toegang](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)     |Bescherm u tegen gecompromitteerde identiteiten en apparaten. Begin met deze beveiliging omdat deze basis is. De configuratie die in deze richtlijn wordt aanbevolen, bevat Azure AD Identity Protection als een vereiste. Zie [Azure AD Identity Protection](/azure/security/fundamentals/threat-detection#azure-active-directory-identity-protection)voor meer informatie.     |
| 2 |[Microsoft Defender for Identity](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)     |  Een cloudgebaseerde beveiligingsoplossing die uw on-premises Ad DS-signalen (Active Directory Domain Services) gebruikt om geavanceerde bedreigingen, gecompromitteerde identiteiten en kwaadaardige insideracties die zijn gericht op uw organisatie te identificeren, te detecteren en te onderzoeken. Focus vervolgens op Microsoft Defender voor identiteit omdat het uw on-premises en cloudinfrastructuur beschermt, geen afhankelijkheden of vereisten heeft en directe beveiligingsvoordelen kan bieden. Zie Wat [is Identiteitsbeveiliging? voor meer informatie.](/azure/active-directory/identity-protection/overview-identity-protection) | 
| 3 |[Microsoft 365 Defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender) |Hiermee combineert u signalen en brengt u mogelijkheden samen tot één oplossing. Stelt beveiligingsprofessionals in staat om bedreigingssignalen samen te borduren en het volledige bereik en de impact van een bedreiging te bepalen. Microsoft 365 Defender voert automatische acties uit om de aanval te voorkomen of te stoppen en getroffen postvakken, eindpunten en gebruikersidentiteiten te voorkomen of te herstellen. Zie voor meer informatie [Microsoft 365 Defender.](/microsoft-365/security/defender/microsoft-365-defender) |
| 4 |[Microsoft Defender voor Office 365](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)     | Beschermt uw organisatie tegen schadelijke bedreigingen die worden veroorzaakt door e-mailberichten, koppelingen (URL's) en samenwerkingshulpmiddelen. Beschermt tegen malware, phishing, spoofing en andere aanvalstypen. Het configureren van Microsoft Defender voor Office 365 wordt aanbevolen, omdat het implementeren van beheer, het migreren van instellingen van het huidige systeem en andere overwegingen langer kan duren. Zie Microsoft Defender voor meer [informatie Office 365.](/microsoft-365/security/office-365-security/defender-for-office-365)       |
| 5 |[Microsoft Defender voor Eindpunt](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)    | Hiermee voorkomt, detecteert, onderzoekt en reageert u op geavanceerde bedreigingen op verschillende apparaten (ook wel eindpunten genoemd). Defender for Endpoint is een krachtige bedreigingsbeveiliging. Zie [Microsoft Defender voor Eindpunt voor meer informatie.](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)  |
| 6 |[Microsoft Cloud App Security](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)     | Een beveiligingsagent voor cloudtoegang voor detectie, onderzoek en beheer. U kunt Microsoft Cloud App Security inschakelen om gegevens en inzichten te verzamelen. Bij het implementeren van informatie en andere gerichte beveiliging in uw SaaS-apps is planning nodig en kan het meer tijd kosten. Zie Wat [is Cloud App Security? voor meer Cloud App Security](/cloud-app-security/what-is-cloud-app-security)      | 

> [!TIP]
> Organisaties met meerdere beveiligingsteams kunnen mogelijkheden parallel implementeren. Eén team kan Bijvoorbeeld Defender configureren voor Office 365 terwijl een ander team Defender voor Eindpunt configureert. Configuratie hoeft onze voorgestelde volgorde niet precies te volgen. 

## <a name="plan-to-deploy-your-threat-protection-solution"></a>Plan om uw oplossing voor bedreigingsbeveiliging te implementeren

In het volgende diagram ziet u het proces op hoog niveau voor het implementeren van mogelijkheden voor bedreigingsbeveiliging. 

![Proces voor het implementeren van mogelijkheden voor bedreigingsbeveiliging](../media/deploy-threat-protection/deploy-threat-protection-across-m365-grid.png)

Als u ervoor wilt zorgen dat uw organisatie de best mogelijke beveiliging biedt, stelt u uw [beveiligingsoplossing](deploy-threat-protection-configure.md) in en implementeert u deze met een proces dat de volgende stappen bevat:

1. [Meervoudige verificatie en beleidsregels voor voorwaardelijke toegang instellen.](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [Microsoft Defender configureren voor identiteit.](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)
3. [Schakel Microsoft 365 Defender in.](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender)
4. [ConfigureEr Defender voor Office 365.](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)
5. [Microsoft Defender configureren voor eindpunt](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint).
6. [Configureer Microsoft Cloud App Security](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security).
7. [Status controleren en acties uitvoeren.](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [Train gebruikers](deploy-threat-protection-configure.md#step-8-train-users).

Uw beveiligingsfuncties voor bedreigingen kunnen parallel worden geconfigureerd, dus als u meerdere netwerkbeveiligingsteams hebt die verantwoordelijk zijn voor verschillende services, kunnen ze de beveiligingsfuncties van uw organisatie tegelijkertijd configureren.

## <a name="next-step"></a>Volgende stap

Ga verder [met Het configureren van mogelijkheden voor bedreigingsbeveiliging in Microsoft 365.](deploy-threat-protection-configure.md)


