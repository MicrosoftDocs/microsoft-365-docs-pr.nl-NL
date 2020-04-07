---
title: Fase 5 - Beheer van mobiele apparaten
description: Microsoft 365 Enterprise omvat beheer van mobiele apparaten met Behulp van Microsoft Intune. Bekijk de vereisten en vereisten, stel Intune in met uw Azure Active Directory-bron, schrijf iOS-, macOS-, Android- en Windows-apparaten in, implementeer apps, maak een configureerprofiel, gebruik een nalevingsbeleid en schakel voorwaardelijke toegang in voor beheer van mobiele apparaten met Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365-documentatie, beheer van mobiele apparaten, Intune
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/03/2019
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: a957ef037aed1f9aba923af428c2a440790dbfba
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153890"
---
# <a name="phase-5-mobile-device-management-for-microsoft-365-enterprise"></a>Fase 5: Beheer van mobiele apparaten voor Microsoft 365 Enterprise

![Fase 5: Mobile Device Management](../media/deploy-foundation-infrastructure/mobiledevicemgmt_icon.png)

*Deze functie is van toepassing op de E3- en E5-versies van Microsoft 365 Enterprise*

Microsoft 365 Enterprise bevat functies voor het beheren van apparaten en hun apps binnen uw organisatie. Met Microsoft Intune u iOS-, Android-, macOS- en Windows-apparaten beheren om de toegang tot de bronnen van uw organisatie, inclusief uw gegevens, te beschermen. 

In deze fase schrijft u uw apparaten in in Intune en maakt en handhaaft u beleid om uw gegevens veilig en beschermd te houden. De volledige bibliotheek van Intune documentatie is [online beschikbaar.](https://docs.microsoft.com/intune) Het is ook een goede gewoonte om de [intune-implementatieplannings-, ontwerp- en implementatiehandleiding](https://docs.microsoft.com/intune/planning-guide) te bekijken voordat u aan de slag gaat.

## <a name="step-1-plan-for-your-scenario"></a>Stap 1: Plan voor uw scenario

Een van de belangrijkste redenen om mobiele apparaten te beheren, is het beveiligen en beschermen van de bronnen van uw organisatie. [Veelgebruikte manieren om Microsoft Intune te gebruiken](https://docs.microsoft.com/intune/common-scenarios) bevatten enkele voorbeelden in de echte wereld, waaronder het beveiligen van Office 365-e-mail en -gegevens.

Intune biedt u opties om toegang tot uw organisatie te beheren met behulp van Mobile Device Management (MDM) of Mobile Application Management (MAM). MDM is wanneer gebruikers "inschrijven" hun apparaten in Intune. Eenmaal ingeschreven, zijn ze beheerde apparaten en kunnen alle beleidsregels, regels en instellingen ontvangen die door uw organisatie worden gebruikt. U bijvoorbeeld specifieke apps installeren, een wachtwoordbeleid maken, een VPN-verbinding installeren en meer.

Gebruikers met hun eigen persoonlijke apparaten willen hun apparaten mogelijk niet inschrijven of worden beheerd door Intune en uw beleid. Maar u moet nog steeds de bronnen en gegevens van uw organisatie beschermen. In dit scenario u uw apps beveiligen met MAM. U bijvoorbeeld een MAM-beleid gebruiken waarvoor een gebruiker een pincode moet invoeren wanneer hij toegang krijgt tot SharePoint op het apparaat.

U bepaalt ook hoe u apparaten die eigendom zijn van een organisatie of een organisatie gaat beheren. U apparaten anders behandelen, afhankelijk van het gebruik ervan. U wilt bijvoorbeeld verschillende plannen voor gebruikers in Human Resources (HR) of gebruikers in Sales. [Identificeer gebruiksscenario's voor het beheer van mobiele apparaten](https://docs.microsoft.com/intune/planning-guide-scenarios) u op weg helpen en bevat enkele richtlijnen voor deze verschillende scenario's.

## <a name="step-2-get-your-prerequisites"></a>Stap 2: Krijg je voorwaarden

Ontvang vervolgens uw vereisten op basis van uw vereisten en uw scenario's die in de vorige stap zijn gemaakt. [Implement your plan](https://docs.microsoft.com/intune/planning-guide-onboarding) lists all the requirements. Dit zijn de belangrijke items die u nodig hebt voor Intune met Microsoft 365:

- **Intune-abonnement:** inbegrepen bij Microsoft 365 en geeft u toegang tot Microsoft Intune in de [Azure-portal](https://portal.azure.com)
- **Office 365-abonnement**: inbegrepen bij Microsoft 365 en wordt gebruikt voor Office-apps, waaronder e-mail
- **Azure Active Directory (Azure AD) premium:** inbegrepen bij Microsoft 365 en wordt gebruikt om gebruikers- of beveiligingsgroepen te maken. Deze groepen ontvangen Intune-beleid dat u maakt, zoals het forceren van een wachtwoordlengte om een apparaat te ontgrendelen. De groepen die u maakt in [fase 2: Identiteit](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure) kan worden gebruikt.

Er kunnen enkele aanvullende vereisten zijn, afhankelijk van de behoeften van uw organisatie. Als u bijvoorbeeld iOS-apparaten beheert, hebt u een Apple MDM Push-certificaat nodig. Als u on-premises Exchange gebruikt, hebt u de on-premises Exchange-connector nodig. Deze aanvullende vereisten worden beschreven wanneer u bij deze stappen komt.

## <a name="step-3-set-up-intune"></a>Stap 3: Intune instellen

Intune gebruikt veel functies in Azure AD, waaronder uw domein, uw gebruikers en uw groepen. U ook nieuwe gebruikers en nieuwe groepen maken die passen bij uw bedrijfsbehoeften. U bijvoorbeeld een groep met de naam **iOS-apparaten**of **Alle HR-gebruikers**maken.  Profiteer van [dynamische groepen](https://docs.microsoft.com/intune/groups-add) waarmee u gebruikers- of apparaatgroepen samenstellen op basis van eenvoudige of geavanceerde regels.

Deze stap richt zich op het instellen van Intune en het klaarmaken voor u om uw apparaten te beheren.

1. **[Controleer of uw apparaten worden ondersteund.](https://docs.microsoft.com/intune/supported-devices-browsers)** Controleer of je iOS-, macOS-, Android-, Galaxy- en Windows-apparaten worden ondersteund door Intune. Als uw organisatie apparaten bevat die niet worden ondersteund, wordt het beleid niet toegepast op die apparaten.

2. **[Uw domeinnaam aanpassen](https://docs.microsoft.com/intune/custom-domain-name-configure)**. Standaard wordt een domein met de naam iets als **your-domain.onmicrosoft.com** automatisch gemaakt in Azure AD. **onmicrosoft.com** worden aangepast voor uw organisatie. Wanneer u zich aanpast, geeft het gebruikers ook een vertrouwd domein wanneer ze verbinding maken met Intune en resources gebruiken.

3. **[Log hier in](https://docs.microsoft.com/intune/account-sign-up)** Wanneer u zich aanmeldt, wordt u mogelijk gevraagd om informatie over uw organisatie in te voeren. Intune is inbegrepen bij Microsoft 365 en kan rechtstreeks vanuit het [Microsoft 365-beheercentrum](https://admin.microsoft.com)worden geopend. U Intune ook rechtstreeks openen vanuit de [Azure-portal.](https://portal.azure.com)

4. **[Kies uw configuratie voor het beheer van mobiele apparaten.](https://docs.microsoft.com/intune/mdm-authority-set)** De eerste keer dat u Intune gebruikt, moet u apparaatbeheer inschakelen. Intune kan worden gebruikt als een cloud-only service, een hybride met Intune en Microsoft Endpoint Configuration Manager, of met behulp van Mobile Device Management voor Office 365. U kiezen welke setup het beste werkt voor uw organisatie.

5. **[Gebruikers toevoegen](https://docs.microsoft.com/intune/users-add)** en **[groepen toevoegen](https://docs.microsoft.com/intune/groups-add)**. 

   U gebruikers handmatig toevoegen of hybride identiteit en Azure AD Connect gebruiken om uw on-premises gebruikersaccounts te synchroniseren met Intune. U ook beheerdersrollen aan specifieke gebruikers geven. Gebruikers zijn verplicht, tenzij uw apparaten 'gebruikersloze' apparaten zijn, zoals kioskapparaten.

   Azure AD-groepen worden gebruikt om de manier waarop u apparaten en gebruikers beheert in Intune te vereenvoudigen. Met behulp van groepen u veel verschillende taken uitvoeren. Uw organisatie wil bijvoorbeeld een specifieke app op Android-apparaten vereisen. U een Groep Android-apparaten maken en een beleid met deze app implementeren in de groep.

    In Intune u gebruikers of groepen toevoegen die u maakt in [fase 2: Identiteit](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure)

6. **[Licenties toewijzen](https://docs.microsoft.com/intune/licenses-assign)**. Voor gebruikers of apparaten die zich willen inschrijven in Intune, hebben ze een Microsoft 365-licentie nodig met de Intune-service die is ingeschakeld om toegang te krijgen tot de Intune-service. U wijst Microsoft 365-licenties toe, waarvoor de Microsoft Intune-service standaard is ingeschakeld, in het Microsoft 365-beheercentrum of met PowerShell.

## <a name="step-4-enroll-devices"></a>Stap 4: Apparaten inschrijven

Om apparaten te beheren, moeten de apparaten zijn ingeschreven in Intune. Als beheerder stelt u inschrijvingsbeperkingen en -beleid in voor uw gebruikers en apparaten. Elk apparaatplatform (iOS, Android, macOS en Windows) heeft verschillende opties. U uw gebruikers zich laten inschrijven. U de inschrijving ook automatiseren, zodat gebruikers zich eenvoudig bij het apparaat aanmelden.

Inschrijving is een belangrijke stap bij het gebruik van Intune. [Apparaten inschrijven bevat](https://docs.microsoft.com/intune/device-enrollment) de stappen voor de verschillende apparaten.

|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Test Lab Guide: iOS en Android apparaat inschrijving](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md) |
|||


## <a name="step-5-add-and-deploy-apps"></a>Stap 5: Apps toevoegen en implementeren

Apps op mobiele apparaten zijn vaak de snelste manier waarop gebruikers toegang krijgen tot uw bedrijfsbronnen. 

Er zijn uitdagingen bij het gebruik van apps, omdat er verschillende apparaten zijn, waaronder persoonlijke apparaten en zakelijke apparaten. En u wilt de bronnen en de gegevens van uw organisatie beschermen en er ook voor zorgen dat gebruikers productief zijn.

Intune kan apps beheren, waaronder apps toevoegen, toewijzen aan verschillende gebruikers of groepen en andere belangrijke details bekijken. U bijvoorbeeld zien welke apps niet worden geïnstalleerd, de versie van een app controleren en meer.

Wanneer gebruikers een mobiel apparaat krijgen, is een van de eerste taken toegang tot e-mail en documenten van organisaties. Met Intune u [e-mailinstellingen maken en implementeren](https://docs.microsoft.com/intune/email-settings-configure) met e-mailapps die vooraf zijn geïnstalleerd op de apparaten. 

In het artikel [Apps toevoegen](https://docs.microsoft.com/intune/apps/apps-add) worden de stappen weergegeven waarmee apps op apparaten in uw organisatie moeten worden toegevoegd, geïmplementeerd, bewaakt, geconfigureerd en beschermd.

|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testlabgids: nalevingsbeleid voor apparaten](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md) |
|||

## <a name="step-6-turn-on-compliance-and-conditional-access"></a>Stap 6: Compliance en voorwaardelijke toegang inschakelen

In de vorige stappen stelt u uw omgeving in en hebt u Intune ingeschakeld. Nu bent u klaar om een aantal beleidsregels te maken met behulp van compliance en voorwaardelijke toegang.

Naleving en voorwaardelijke toegang zijn belangrijk voor het beheer van apparaten. [Nalevingsbeleid](https://docs.microsoft.com/intune/device-compliance-get-started) is gemaakt om de bronnen van uw organisatie te beschermen. Wanneer u een nalevingsbeleid maakt, definieert u de standaard of de 'basislijn' van wat een apparaat moet hebben. U bijvoorbeeld een acceptabel (of onaanvaardbaar) dreigingsniveau kiezen, jailbroken-apparaten blokkeren, een wachtwoordlengte vereisen en meer. Als deze apparaten niet aan uw regels voldoen, wat betekent dat ze niet voldoen, u de toegang tot uw bronnen blokkeren.

Deze "blokkering" introduceert [Voorwaardelijke toegang](https://docs.microsoft.com/intune/conditional-access). Als een apparaat als niet-compatibel wordt beschouwd, u de toegang tot e-mail, SharePoint en meer blokkeren.

Met Intune in de [Azure-portal](https://portal.azure.com) u deze beleidsregels maken en toepassen op uw gebruikers en apparaten. Als een best practice, beginnen klein, en gebruik maken van een geënsceneerde aanpak. Maak bijvoorbeeld een iOS-beleid dat apparaten met een gevangenis kapot te blokkeren. Pas het beleid toe (wijs" toe in Intune) op een pilot- of testgroep. Na de eerste tests voegt u meer gebruikers toe aan de pilotgroep. Met behulp van een gefaseerde aanpak u feedback krijgen van een breed scala aan gebruikerstypen.

Zie [Aan de slag met het nalevingsbeleid voor apparaten](https://docs.microsoft.com/intune/device-compliance-get-started) en Meer informatie over voorwaardelijke toegang en [intune?](https://docs.microsoft.com/intune/conditional-access)

## <a name="step-7-apply-features-and-settings"></a>Stap 7: Functies en instellingen toepassen

Deze functies en instellingen worden vaak beschouwd als het "coole" deel van Intune, en zijn zeer krachtig. Zodra u een aantal nalevingsbeleidsregels hebt afgedwongen met voorwaardelijke toegang, u **apparaatprofielen**maken.

Met Intune in de [Azure-portal](https://portal.azure.com) u verschillende profielen maken op basis van uw apparaatplatform - iOS, macOS, Android en Windows. U kunt bijvoorbeeld:

- Gebruik Endpoint-beveiliging op Windows 10-apparaten om verschillende BitLocker-opties in te schakelen, waaronder versleuteling.
- Gebruik de functie Beperkte apps op iOS-apparaten om een lijst met goedgekeurde apps te maken die kunnen worden geïnstalleerd. Of maak een lijst met verboden apps.
- Gebruik de kiosk-instellingen om te kiezen welke apps kunnen worden gebruikt op Android-apparaten die in de kioskmodus worden uitgevoerd.
- Pas een Wi-Fi-verbinding en de instellingen daarvan toe, inclusief het beveiligingstype, op apparaten waarop macOS wordt uitgevoerd.

[Functies en instellingen toepassen op uw apparaten met apparaatprofielen](https://docs.microsoft.com/intune/device-profiles) is een geweldige plek om te lezen over profielen, te zien hoe u een profiel maakt en meer.

Vergeet niet, begin klein en gebruik een gefaseerde aanpak. Wijs het profiel toe aan een piloot of testgroep. Wijs het profiel vervolgens toe aan meer pilotgroepen.

## <a name="step-8-get-to-know-the-other-features"></a>Stap 8: Maak kennis met de andere functies

Intune is een krachtige service en bevat veel functies. Hier volgen enkele andere taken die u uitvoeren met Intune:

- Software en updates beheren op & [Windows-apparaten en](https://docs.microsoft.com/intune/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune) [devices](https://docs.microsoft.com/intune/windows-update-for-business-configure) [iOS-apparaten](https://docs.microsoft.com/intune/software-updates-ios)
- Schakel [Microsoft Defender Advanced Threat Protection (ATP)](https://docs.microsoft.com/intune/advanced-threat-protection) in op uw Windows 10-apparaten en gebruik naleving en voorwaardelijke toegang om de toegang tot bedrijfsbronnen, zoals SharePoint of Exchange Online, te beschermen
- [Lookout,](https://docs.microsoft.com/intune/lookout-mobile-threat-defense-connector) [Symantec](https://docs.microsoft.com/intune/skycure-mobile-threat-defense-connector)en andere samenwerkingspartners voor mobiele verdedigingsbedreigingen gebruiken
- Een [partnercertificeringsinstantie (CA)](https://docs.microsoft.com/intune/certificate-authority-add-scep-overview) toevoegen om certificaten uit te geven en te vernieuwen
- [Geef uw eindgebruikers richtlijnen](https://docs.microsoft.com/intune/end-user-educate) in de App Bedrijfsportal, apps downloaden en meer
- Controleer [apps](https://docs.microsoft.com/intune/apps-monitor) en [apparaatnalevings- en configuratieprofielen](https://docs.microsoft.com/intune/compliance-policy-monitor)en meer telemetrie met behulp van de controlelogboeken. U ook verbinding maken met het [Intune Data Warehouse](https://docs.microsoft.com/intune/reports-nav-create-intune-reports) en Power BI gebruiken voor nog meer rapportagebehoeften.


## <a name="identity-and-device-access-recommendations"></a>Aanbevelingen voor identiteits- en apparaattoegang

Microsoft biedt een aantal aanbevelingen voor [identiteits- en apparaattoegang](microsoft-365-policies-configurations.md) om te zorgen dat uw personeel veilig en productief blijft. Voor apparaattoegang gebruikt u de aanbevelingen en instellingen in de volgende artikelen, samen met de stappen in deze fase:

- [Vereisten](identity-access-prerequisites.md)
- [Algemeen beleid voor identiteits- en apparaattoegang](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Hoe Microsoft omgaat met Microsoft 365 Enterprise

Ontdek hoe IT-experts bij Microsoft [apparaten beheren met EMS.](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR8)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Hoe Contoso Microsoft 365 Enterprise gebruikt

Bekijk hoe de Contoso Corporation, een fictief maar representatief multinationaal bedrijf, [hun infrastructuur voor het beheer van mobiele apparaten heeft geïmplementeerd](contoso-mdm.md) met Microsoft 365-cloudservices.

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Volgende stap

[Criteria voor het afsluiten van infrastructuur voor mobiele apparatuur](mobility-infrastructure-exit-criteria.md)

