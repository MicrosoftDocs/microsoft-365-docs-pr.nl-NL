---
title: App-beheer in Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Beheermogelijkheden voor Microsoft-apps implementeren om uw apps te beheren.
ms.openlocfilehash: 63bd6684bc041c3c82ba6b8ddcc28c2600182b26
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430694"
---
# <a name="app-governance-add-on-to-microsoft-cloud-app-security-in-preview"></a>Invoegtoepassing voor app-beheer voor Microsoft Cloud App Security (in preview)

>*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en naleving](https://aka.ms/ComplianceSD).*

Cyberaanvallen zijn steeds geavanceerder geworden in de manier waarop ze de apps exploiteren die u in uw on-premises- en cloudinfrastructuren hebt geïmplementeerd, waardoor een beginpunt ontstaat voor escalatie van bevoegdheden, zijwaartse verplaatsing en exfiltratie van uw gegevens. Om de potentiële risico's te begrijpen en dit soort aanvallen te stoppen, moet u duidelijk inzicht krijgen in de app-nalevingspostuur van uw organisatie om snel te kunnen identificeren wanneer een app afwijkend gedrag vertoont en om te reageren wanneer dit gedrag risico's met zich meebrengt voor uw omgeving, gegevens en gebruikers.

De invoegtoepassing voor app-beheer voor Microsoft Cloud App Security is een functie voor beveiligings- en beleidsbeheer die is ontworpen voor OAuth-apps die toegang hebben tot Microsoft 365-gegevens via Microsoft Graph API's. App-beheer biedt volledig inzicht, herstel en beheer van hoe deze apps en hun gebruikers toegang krijgen tot uw gevoelige gegevens die zijn opgeslagen in Microsoft 365, hoe ze deze gebruiken en delen via bruikbare inzichten en geautomatiseerde beleidswaarschuwingen en -acties.

<!--
The scale of ongoing cybersecurity incidents affecting large enterprises and smaller businesses highlights the dangers of supply chain attacks and the need to strengthen the security and compliance posture of every organization. Accelerated cloud adoption with Microsoft 365 and its rich application ecosystem are constantly growing. Attackers are gaining organizational footholds through applications because:

- Users are typically unaware of the risks when consenting to the use of applications. 
- App developers and independent software vendors (ISVs) do not yet have Security Development Lifecycle (SDL) best practices in place to address attacker techniques.
-->

App-beheer biedt uitgebreide:

- **Inzichten**: bekijk een overzicht van alle apps van derden voor het Microsoft 365-platform in uw tenant op één dashboard. U kunt alle status- en waarschuwingsactiviteiten van de apps zien en erop reageren of antwoorden.
- **Beheer**: maak proactief of reactief beleid voor app- en gebruikerspatronen en -gedrag en bescherm uw gebruikers tegen het gebruik van niet-conforme of schadelijke apps en beperk de toegang van risicovolle apps tot uw gegevens.
- **Detectie**: ontvang een waarschuwing en een melding wanneer er afwijkingen zijn in app-activiteit en wanneer niet-conforme, kwaadaardige of risicovolle apps worden gebruikt.
- **Herstel**: gebruik naast automatische herstelmogelijkheden tijdig herstelcontroles om te reageren op detecties van afwijkende app-activiteiten.

App-beheer is een platformgebaseerde oplossing die een integraal onderdeel is van het Microsoft 365-app-ecosysteem. App-governance houdt toezicht op en beheert OAuth-apps die zijn geregistreerd bij Azure Active Directory (Azure AD) en heeft toegang tot gegevens via de Microsoft Graph API. App-beheer biedt besturingselementen voor app-gedrag om de beveiliging en naleving van uw IT-infrastructuur te versterken.

<!--
Unlike other application governance products in the marketplace, MAPG is a platform-based solution that is an integral part of the Microsoft 365 application ecosystem. MAPG's initial focus is on OAuth-enabled apps published to the Microsoft 365 platform that are registered with Azure AD and access data through the Graph API. For the initial release, MAPG does not support other, non-OAuth-enabled M365 apps, add-ins (such as PowerBI), or other app vendor ecosystems such as Google, Facebook, Amazon Web Services, Workplace, and Salesforce. MAPG’s focus is on third-party published apps for the Microsoft 365 application platform.

Microsoft allows developers to build cloud applications using Azure Active Directory (Azure AD), Microsoft’s cloud identity platform, and other resources and access to tenant data through the Microsoft Graph. Because of MAPG's visibility, insights, and control capabilities, app developers have the incentive to comply with publisher verification, self-attestation, and Microsoft certification, and can build high-quality productivity apps that are secure and compliant.
-->

## <a name="a-first-glimpse-at-app-governance"></a>Een eerste blik op app-beheer

Als u het dashboard voor app-beheer wilt zien, gaat u naar [https://aka.ms/appgovernance](https://aka.ms/appgovernance). Houd er rekening mee dat uw aanmeldingsaccount een van de [beheerdersrollen](app-governance-get-started.md#administrator-roles) moet hebben om app-beheergegevens weer te geven.

## <a name="app-governance-integration-with-azure-ad-and-microsoft-cloud-app-security"></a>Integratie van app-beheer met Azure AD en Microsoft Cloud App Security

App-beheer, Azure AD en Microsoft Cloud App Security verzamelen en leveren verschillende gegevenssets:

- App-beheer biedt gedetailleerde informatie over de activiteit van een app op API-niveau.
- Azure AD biedt basismetagegevens voor apps en gedetailleerde informatie over aanmeldingen bij apps.
- Microsoft Cloud App Security biedt informatie over app-risico's.

Door informatie te delen tussen app-beheer, Azure AD en Microsoft Cloud App Security, kunt u geaggregeerde informatie in één portal weergeven en eenvoudig een koppeling maken naar een andere portal voor meer informatie. Hier zijn enkele voorbeelden:

- Aanmeldingsgegevens voor apps in app-beheer:

  Vanuit de portal voor app-beheer kunt u de geaggregeerde aanmeldingsactiviteit voor elke app zien en terugkoppelen naar het Azure Active Directory-beheercentrum voor details van aanmeldingsgebeurtenissen.

<!--
- App API usage information in the Azure Active Directory admin center:

  From the Azure Active Directory admin center, you can see the aggregated app usage information and link to the app governance portal for the details of app usage.
-->
- API-gebruiksgegevens in de Microsoft Cloud App Security-portal:

  In de Microsoft Cloud App Security-portal kunt u het API-gebruiksniveau en de geaggregeerde gegevensoverdracht bekijken en voor meer informatie een koppeling naar de portal voor app-beheer maken.

Hier is een samenvatting van de integratie.

![Integratie van app-beheer met Azure AD en Microsoft Cloud App Security](..\media\manage-app-protection-governance\mapg-integration.png)

Bovendien stuurt app-beheer waarschuwingen als signalen naar Microsoft Cloud App Security en Microsoft 365 Defender, en ontvangt app-beheer waarschuwingen van Microsoft Cloud App Security, om een meer gedetailleerde analyse van app-gebaseerde beveiligingsincidenten mogelijk te maken.

<!--
Integration of alerts with MCAS and M365 Defender
Azure AD IP detections in progress to surface in M365 Defender

## Integration with Azure AD

**Feedback from Anand:** We should add some details on how MAPG works with M365 Defender (previously MTP). Also, we should highlight the integration with MCAS and AAD.

Key cross-reference resources:

- [What is application management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-application-management)
- [Common application management scenarios for Azure Active Directory (especially scenarios 3-4)](https://docs.microsoft.com/cloud-app-security/monitor-alerts)
- [Azure Active Directory Identity Governance documentation](https://docs.microsoft.com/azure/active-directory/governance/)
- [Managing access to apps using Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-access-management)

## Integration with Microsoft Cloud App Security

Key cross-reference resources:

- [Cloud App Security anomaly detection alerts investigation guide](https://docs.microsoft.com/cloud-app-security/investigate-anomaly-alerts#unusual-addition-of-credentials-to-an-oauth-app)
- [Monitor alerts raised in Cloud App Security](https://docs.microsoft.com/cloud-app-security/monitor-alerts)
- [Control which third-party cloud OAuth apps get permissions](https://docs.microsoft.com/cloud-app-security/manage-app-permissions)

-->

## <a name="using-app-governance"></a>App-beheer gebruiken

Het gebruik van app-beheer om uw tenant en de bijbehorende gegevens te beschermen tegen potentieel schadelijke of zich slecht gedragende apps valt uiteen in de volgende drie kernmogelijkheden:

| Mogelijkheid | Beschrijving |
|:-------|:-----|
| [Zichtbaarheid en inzichten van apps](app-governance-visibility-insights-overview.md) | Bekijk een 360°-weergave van verkeer en activiteit van de Microsoft 365 toepassingen in uw tenant. |
| [App-beleid voor versterkt beheer](app-governance-app-policies-overview.md) | Maak proactief of reactief app-beleid, waarmee u beheer kunt afdwingen voor uw Microsoft 365-apps. |
| [Detectie en herstel](app-governance-detect-remediate-overview.md) | Op basis van platformdetectiewaarschuwingen of door beleid gegenereerde detectiewaarschuwingen controleert u uw apps op afwijkend app-gedrag en herstelt u deze, automatisch op basis van app-beleidsinstellingen of handmatig. |
|||
