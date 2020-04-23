---
title: 'Fase 3: Afsluitcriterium Windows 10 Enterprise-infrastructuur'
f1.keywords:
- NOCSH
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: 03/05/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Zorg ervoor dat uw configuratie voldoet aan de Microsoft 365 Enterprise-criteria voor Windows 10 Enterprise.
ms.openlocfilehash: cf4a813a6cf89029eebde8e5947caf7b3c2ea553
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636685"
---
# <a name="phase-3-windows-10-enterprise-infrastructure-exit-criteria"></a>Fase 3: Afsluitcriterium Windows 10 Enterprise-infrastructuur

![Fase 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Zorg ervoor dat uw Windows 10 Enterprise-infrastructuur voldoet aan de volgende vereiste criteria en dat u de optionele criteria hebt overwogen.

<a name="crit-windows10-step1"></a>
## <a name="required-your-microsoft-365-domains-are-added-and-verified"></a>Vereist: uw Microsoft 365-domeinen zijn toegevoegd en gecontroleerd

De Azure AD-tenant voor uw Office 365- en Intune-abonnementen is geconfigureerd met uw internetdomeinnamen (zoals contoso.com), in plaats van alleen een domeinnaam die "onmicrosoft.com" bevat. 

Als u dit niet doet, bent u beperkt in de verificatiemethoden die u kunt configureren. Pass-through en federatieve verificatie kunnen bijvoorbeeld niet de domeinnaam 'onmicrosoft.com' gebruiken.

[Stap 1](windows10-prepare-your-org.md) kan u bij deze optie desgewenst helpen.

## <a name="optional-your-users-are-added-and-licensed"></a>Optioneel: uw gebruikers worden toegevoegd en gelicentieerd

De accounts die overeenkomen met uw gebruikers worden toegevoegd, ofwel rechtstreeks aan uw Azure AD-tenant voor uw Office 365- en Intune-abonnementen, of door adreslijstsynchronisatie vanuit uw on-premises Active Directory Domain Services (AD DS).

Zodra de gebruikers zijn toegevoegd, kunt u aan hen Microsoft 365 Enterprise-licenties toewijzen, hetzij rechtstreeks als globale of gebruikersbeheerder, of automatisch via groepslidmaatschap.

[Stap 1](windows10-prepare-your-org.md) kan u bij deze optie desgewenst helpen.

## <a name="optional-diagnostics-are-enabled"></a>Optioneel: diagnostiek is ingeschakeld

U hebt instellingen voor diagnostische gegevens ingeschakeld met Groepsbeleid, Microsoft Intune, de Register-editor of met de opdrachtprompt.

[Stap 1](windows10-prepare-your-org.md) kan u bij deze optie desgewenst helpen.

<a name="crit-windows10-step2"></a>
## <a name="required-for-in-place-upgrade-created-a-configuration-manager-task-sequence-for-an-operating-system-deployment"></a>Vereist voor in-place upgrade: een Configuration Manager-takenreeks gemaakt voor een besturingssysteemimplementatie

Om een takenreeks van Configuration Manager te starten om een interne upgrade uit te voeren op een apparaat met Windows 7 of Windows 8.1, moet u het volgende doen:

- Stel het juiste gegevensniveau voor diagnostische gegevens van Windows in
- Verifieer de gereedheid voor een upgrade van Windows
- Maak een Configuration Manager-takenreeks met een apparaatverzameling en een besturingssysteemimplementatie met een Windows 10 OS-installatiekopie

Zodra dit is gebeurd, kunt u in-place upgrades uitvoeren op apparaten die gereed zijn om Windows te upgraden. Upgrade zoveel mogelijk apparaten met Windows 7 en Windows 8.1 om het maximale uit Microsoft 365 Enterprise te halen. 

Elk apparaat met Windows 10 Enterprise kan profiteren van de voordelen van de geïntegreerde oplossing van Microsoft 365 Enterprise. Op de overige apparaten met Windows 7 of Windows 8.1 kunt u geen gebruikmaken van de met de cloud verbonden technologieën en geavanceerde beveiligingsfuncties van Windows 10 Enterprise.

Via [Stap 2](windows10-deploy-inplaceupgrade.md) kunt u zo nodig aan deze vereisten voldoen.

<a name="crit-windows10-step3"></a>
## <a name="required-for-new-devices-configured-windows-autopilot"></a>Vereist voor nieuwe apparaten: geconfigureerde Windows Autopilot

Voor het gebruik van Windows Autopilot om Windows 10 Enterprise te implementeren en aan te passen op een nieuw apparaat, moet u het volgende doen:

- Stel het juiste gegevensniveau voor diagnostische gegevens van Windows in
- Configureer de vereisten voor Windows Autopilot, waaronder:
   - Apparaatregistratie en OOBE-aanpassing
   - Bedrijfshuisstijl voor OOBE
   - Automatische MDM-inschrijving in Microsoft Intune
   - Netwerkverbindingen met cloudservices die worden gebruikt door Windows Autopilot
- Apparaten die vooraf zijn geïnstalleerd met Windows 10, versie 1703 of hoger
- Selecteer het Windows Autopilot Deployment Program voor uw organisatie

Zodra de Windows Autopilot-configuratie aanwezig is, kunt u deze gebruiken om Windows 10 Enterprise te configureren en aan te passen voor de kant-en-klare ervaring (OOBE) voor:

- Nieuwe apparaten
- Apparaten die al een kant-en-klare installatie van uw organisatie hebben voltooid. 

Windows Autopilot configureert het apparaat en verbindt het met Azure AD.

Zonder Windows Autopilot moet u nieuwe apparaten handmatig configureren, inclusief de verbinding met Azure AD.

Via [Stap 3](windows10-deploy-autopilot.md) kunt u zo nodig aan deze vereisten voldoen.

<a name="crit-windows10-step4"></a>
## <a name="optional-you-are-using-windows-analytics-device-health-to-monitor-your-windows-10-enterprise-based-devices"></a>Optioneel: u gebruikt Windows Analytics Device Health om uw Windows 10 Enterprise-apparaten te bewaken

U hebt de gegevens van Device Health gebruikt om de status van apparaten te controleren en om problemen te ontdekken en op te lossen die gevolgen hebben voor gebruikers. Door snel problemen met eindgebruikers aan te pakken, kunt u uw ondersteuningskosten verlagen en uw gebruikers laten zien dat IT zich inzet voor Windows 10 Enterprise, wat de acceptatie binnen uw organisatie kan stimuleren. 

[Stap 4](windows10-enable-windows-analytics.md) kan u bij deze optie desgewenst helpen.

<a name="crit-windows10-step5a"></a>
## <a name="required-you-are-using-windows-defender-antivirus-or-your-own-antimalware-solution"></a>Vereist: u gebruikt Windows Defender Antivirus of uw eigen antimalware-oplossing

U hebt Windows Defender Antivirus of uw eigen antivirusoplossing geïmplementeerd om uw apparaten met Windows 10 Enterprise te beveiligen tegen schadelijke software. Als u Windows Defender Antivirus heeft geïmplementeerd, heeft u een rapportagemethode geïmplementeerd, zoals Microsoft Endpoint Configuration Manager of Microsoft Intune, om antivirusgebeurtenissen en -activiteiten te monitoren.

Via [Stap 5](windows10-enable-security-features.md#windows10-sec-av) kunt u zo nodig aan deze vereisten voldoen.

<a name="crit-windows10-step5b"></a>
## <a name="required-you-are-using-windows-defender-exploit-guard"></a>Vereist: u gebruikt Windows Defender Exploit Guard

U hebt Windows Defender Exploit Guard ingezet om uw apparaten met Windows 10 Enterprise te beschermen tegen inbraak en heeft een rapportagemethode geïmplementeerd, zoals Configuration Manager of Microsoft Intune, om inbraakgebeurtenissen en -activiteiten te bewaken.

[Stap 5](windows10-enable-security-features.md#windows10-sec-eg) kan u bij deze optie desgewenst helpen.

<a name="crit-windows10-step5c"></a>
## <a name="required-you-are-using-microsoft-defender-advanced-threat-protection-microsoft-365-e5-only"></a>Vereist: u gebruikt Microsoft Defender Advanced Threat Protection (alleen Microsoft 365 E5)

U hebt Microsoft Defender Advanced Threat Protection (ATP) ingezet om geavanceerde bedreigingen tegen uw netwerk en apparaten met Windows 10 Enterprise te detecteren, te onderzoeken en erop te reageren. 

U hebt Microsoft Defender ATP als optie geïntegreerd met andere tools om de mogelijkheden uit te breiden.

Via [Stap 5](windows10-enable-security-features.md#windows10-sec-atp) kunt u zo nodig aan deze vereisten voldoen.

## <a name="results-and-next-steps"></a>Resultaten en volgende stappen

Uw Windows 10 Enterprise-infrastructuur is klaar voor de installatie van nieuwe apparaten en upgrades-in-place op apparaten met eerdere versies van Windows en u gebruikt de belangrijke beveiligingsfuncties van Windows 10 Enterprise.

|||
|:-------|:-----|
|![Fase 4: Microsoft 365-apps voor ondernemingen](../media/deploy-foundation-infrastructure/O365proplus_icon-small.png)| Als u de fasen voor de end-to-end-implementatie van Microsoft 365 Enterprise volgt, is [Microsoft 365-apps voor ondernemingen](office365proplus-infrastructure.md) de volgende fase. |
