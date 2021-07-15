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
ms.openlocfilehash: bc8c739132de52abb69c15479cd851462e9f6ce7
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420163"
---
# <a name="app-governance-add-on-to-microsoft-cloud-app-security-in-preview"></a><span data-ttu-id="b2fec-103">Invoegtoepassing voor app-beheer voor Microsoft Cloud App Security (in preview)</span><span class="sxs-lookup"><span data-stu-id="b2fec-103">App governance add-on to Microsoft Cloud App Security (in preview)</span></span>

><span data-ttu-id="b2fec-104">*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en naleving](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="b2fec-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="b2fec-105">Cyberaanvallen zijn steeds geavanceerder geworden in de manier waarop ze de apps exploiteren die u in uw on-premises- en cloudinfrastructuren hebt geïmplementeerd, waardoor een beginpunt ontstaat voor escalatie van bevoegdheden, zijwaartse verplaatsing en exfiltratie van uw gegevens.</span><span class="sxs-lookup"><span data-stu-id="b2fec-105">Cyberattacks have become increasingly sophisticated in the ways they exploit the apps you have deployed in your on-premises and cloud infrastructures, establishing a starting point for privilege escalation, lateral movement, and exfiltration of your data.</span></span> <span data-ttu-id="b2fec-106">Om de potentiële risico's te begrijpen en dit soort aanvallen te stoppen, moet u duidelijk inzicht krijgen in de app-nalevingspostuur van uw organisatie om snel te kunnen identificeren wanneer een app afwijkend gedrag vertoont en om te reageren wanneer dit gedrag risico's met zich meebrengt voor uw omgeving, gegevens en gebruikers.</span><span class="sxs-lookup"><span data-stu-id="b2fec-106">To understand the potential risks and stop these types of attacks, you need to gain clear visibility into your organization’s app compliance posture to quickly identify when an app exhibits anomalous behaviors and to respond when these behaviors present risks to your environment, data, and users.</span></span>

<span data-ttu-id="b2fec-107">De invoegtoepassing voor app-beheer voor Microsoft Cloud App Security is een functie voor beveiligings- en beleidsbeheer die is ontworpen voor OAuth-apps die toegang hebben tot Microsoft 365-gegevens via Microsoft Graph API's.</span><span class="sxs-lookup"><span data-stu-id="b2fec-107">The app governance add-on feature to Microsoft Cloud App Security is a security and policy management capability designed for OAuth-enabled apps that access Microsoft 365 data through Microsoft Graph APIs.</span></span> <span data-ttu-id="b2fec-108">App-beheer biedt volledig inzicht, herstel en beheer van hoe deze apps en hun gebruikers toegang krijgen tot uw gevoelige gegevens die zijn opgeslagen in Microsoft 365, hoe ze deze gebruiken en delen via bruikbare inzichten en geautomatiseerde beleidswaarschuwingen en -acties.</span><span class="sxs-lookup"><span data-stu-id="b2fec-108">App governance delivers full visibility, remediation, and governance into how these apps and their users access, use, and share your sensitive data stored in Microsoft 365 through actionable insights and automated policy alerts and actions.</span></span>

<!--
The scale of ongoing cybersecurity incidents affecting large enterprises and smaller businesses highlights the dangers of supply chain attacks and the need to strengthen the security and compliance posture of every organization. Accelerated cloud adoption with Microsoft 365 and its rich application ecosystem are constantly growing. Attackers are gaining organizational footholds through applications because:

- Users are typically unaware of the risks when consenting to the use of applications. 
- App developers and independent software vendors (ISVs) do not yet have Security Development Lifecycle (SDL) best practices in place to address attacker techniques.
-->

<span data-ttu-id="b2fec-109">App-beheer biedt uitgebreide:</span><span class="sxs-lookup"><span data-stu-id="b2fec-109">App governance provides you with comprehensive:</span></span>

- <span data-ttu-id="b2fec-110">**Inzichten**: bekijk een overzicht van alle apps van derden voor het Microsoft 365-platform in uw tenant op één dashboard.</span><span class="sxs-lookup"><span data-stu-id="b2fec-110">**Insights**: See a view of all the third-party apps for the Microsoft 365 platform in your tenant on a single dashboard.</span></span> <span data-ttu-id="b2fec-111">U kunt alle status- en waarschuwingsactiviteiten van de apps zien en erop reageren of antwoorden.</span><span class="sxs-lookup"><span data-stu-id="b2fec-111">You can see all the apps’ status and alert activities and react or respond to them.</span></span>
- <span data-ttu-id="b2fec-112">**Beheer**: maak proactief of reactief beleid voor app- en gebruikerspatronen en -gedrag en bescherm uw gebruikers tegen het gebruik van niet-conforme of schadelijke apps en beperk de toegang van risicovolle apps tot uw gegevens.</span><span class="sxs-lookup"><span data-stu-id="b2fec-112">**Governance**: Create proactive or reactive policies for app and user patterns and behaviors and protect your users from using non-compliant or malicious apps and limiting the access of risky apps to your data.</span></span>
- <span data-ttu-id="b2fec-113">**Detectie**: ontvang een waarschuwing en een melding wanneer er afwijkingen zijn in app-activiteit en wanneer niet-conforme, kwaadaardige of risicovolle apps worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="b2fec-113">**Detection**: Be alerted and notified when there are anomalies in app activity and when non-compliant, malicious, or risky apps are used.</span></span>
- <span data-ttu-id="b2fec-114">**Herstel**: gebruik naast automatische herstelmogelijkheden tijdig herstelcontroles om te reageren op detecties van afwijkende app-activiteiten.</span><span class="sxs-lookup"><span data-stu-id="b2fec-114">**Remediation**: Along with automatic remediation capabilities, use remediation controls in a timely manner to respond to anomalous app activity detections.</span></span>

<span data-ttu-id="b2fec-115">App-beheer is een platformgebaseerde oplossing die een integraal onderdeel is van het Microsoft 365-app-ecosysteem.</span><span class="sxs-lookup"><span data-stu-id="b2fec-115">App governance is a platform-based solution that is an integral part of the Microsoft 365 app ecosystem.</span></span> <span data-ttu-id="b2fec-116">App-governance houdt toezicht op en beheert OAuth-apps die zijn geregistreerd bij Azure Active Directory (Azure AD) en heeft toegang tot gegevens via de Microsoft Graph API.</span><span class="sxs-lookup"><span data-stu-id="b2fec-116">App governance oversees and governs OAuth-enabled apps that are registered with Azure Active Directory (Azure AD) and access data through the Microsoft Graph API.</span></span> <span data-ttu-id="b2fec-117">App-beheer biedt besturingselementen voor app-gedrag om de beveiliging en naleving van uw IT-infrastructuur te versterken.</span><span class="sxs-lookup"><span data-stu-id="b2fec-117">App governance provides you with application behavior controls to help strengthen the security and compliance posture of your IT infrastructure.</span></span>

<!--
Unlike other application governance products in the marketplace, MAPG is a platform-based solution that is an integral part of the Microsoft 365 application ecosystem. MAPG's initial focus is on OAuth-enabled apps published to the Microsoft 365 platform that are registered with Azure AD and access data through the Graph API. For the initial release, MAPG does not support other, non-OAuth-enabled M365 apps, add-ins (such as PowerBI), or other app vendor ecosystems such as Google, Facebook, Amazon Web Services, Workplace, and Salesforce. MAPG’s focus is on third-party published apps for the Microsoft 365 application platform.

Microsoft allows developers to build cloud applications using Azure Active Directory (Azure AD), Microsoft’s cloud identity platform, and other resources and access to tenant data through the Microsoft Graph. Because of MAPG's visibility, insights, and control capabilities, app developers have the incentive to comply with publisher verification, self-attestation, and Microsoft certification, and can build high-quality productivity apps that are secure and compliant.
-->

## <a name="a-first-glimpse-at-app-governance"></a><span data-ttu-id="b2fec-118">Een eerste blik op app-beheer</span><span class="sxs-lookup"><span data-stu-id="b2fec-118">A first glimpse at app governance</span></span>

<span data-ttu-id="b2fec-119">Als u het dashboard voor app-beheer wilt zien, gaat u naar [https://compliance.microsoft.com/appgovernance](https://compliance.microsoft.com/appgovernance).</span><span class="sxs-lookup"><span data-stu-id="b2fec-119">To see the app governance dashboard, go to [https://compliance.microsoft.com/appgovernance](https://compliance.microsoft.com/appgovernance).</span></span> <span data-ttu-id="b2fec-120">Houd er rekening mee dat uw aanmeldingsaccount een van de [beheerdersrollen](app-governance-get-started.md#administrator-roles) moet hebben om app-beheergegevens weer te geven.</span><span class="sxs-lookup"><span data-stu-id="b2fec-120">Note that your sign-in account must have one of the [administrator roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>

## <a name="app-governance-integration-with-azure-ad-and-microsoft-cloud-app-security"></a><span data-ttu-id="b2fec-121">Integratie van app-beheer met Azure AD en Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b2fec-121">App governance integration with Azure AD and Microsoft Cloud App Security</span></span>

<span data-ttu-id="b2fec-122">App-beheer, Azure AD en Microsoft Cloud App Security verzamelen en leveren verschillende gegevenssets:</span><span class="sxs-lookup"><span data-stu-id="b2fec-122">App governance, Azure AD, and Microsoft Cloud App Security collect and provide different data sets:</span></span>

- <span data-ttu-id="b2fec-123">App-beheer biedt gedetailleerde informatie over de activiteit van een app op API-niveau.</span><span class="sxs-lookup"><span data-stu-id="b2fec-123">App governance provides detailed information about an app’s activity at the API level.</span></span>
- <span data-ttu-id="b2fec-124">Azure AD biedt basismetagegevens voor apps en gedetailleerde informatie over aanmeldingen bij apps.</span><span class="sxs-lookup"><span data-stu-id="b2fec-124">Azure AD provides foundational app metadata and detailed information on sign-ins to apps.</span></span>
- <span data-ttu-id="b2fec-125">Microsoft Cloud App Security biedt informatie over app-risico's.</span><span class="sxs-lookup"><span data-stu-id="b2fec-125">Microsoft Cloud App Security provides app risk information.</span></span>

<span data-ttu-id="b2fec-126">Door informatie te delen tussen app-beheer, Azure AD en Microsoft Cloud App Security, kunt u geaggregeerde informatie in één portal weergeven en eenvoudig een koppeling maken naar een andere portal voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b2fec-126">By sharing information across app governance, Azure AD, and Microsoft Cloud App Security, you can display aggregate information in one portal and easily link to another portal for more information.</span></span> <span data-ttu-id="b2fec-127">Hier zijn enkele voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="b2fec-127">Here are some examples:</span></span>

- <span data-ttu-id="b2fec-128">Aanmeldingsgegevens voor apps in app-beheer:</span><span class="sxs-lookup"><span data-stu-id="b2fec-128">App sign-in information in app governance:</span></span>

  <span data-ttu-id="b2fec-129">Vanuit de portal voor app-beheer kunt u de geaggregeerde aanmeldingsactiviteit voor elke app zien en terugkoppelen naar het Azure Active Directory-beheercentrum voor details van aanmeldingsgebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="b2fec-129">From the app governance portal, you can see the aggregated sign-in activity for each app and link back to the Azure Active Directory admin center for the details of sign-in events.</span></span>

<!--
- App API usage information in the Azure Active Directory admin center:

  From the Azure Active Directory admin center, you can see the aggregated app usage information and link to the app governance portal for the details of app usage.
-->
- <span data-ttu-id="b2fec-130">API-gebruiksgegevens in de Microsoft Cloud App Security-portal:</span><span class="sxs-lookup"><span data-stu-id="b2fec-130">API usage information in the Microsoft Cloud App Security portal:</span></span>

  <span data-ttu-id="b2fec-131">In de Microsoft Cloud App Security-portal kunt u het API-gebruiksniveau en de geaggregeerde gegevensoverdracht bekijken en voor meer informatie een koppeling naar de portal voor app-beheer maken.</span><span class="sxs-lookup"><span data-stu-id="b2fec-131">From the Microsoft Cloud App Security portal, you can see API usage level and aggregate data transfer and link to the app governance portal for the details.</span></span>

<span data-ttu-id="b2fec-132">Hier is een samenvatting van de integratie.</span><span class="sxs-lookup"><span data-stu-id="b2fec-132">Here's a summary of the integration.</span></span>

![Integratie van app-beheer met Azure AD en Microsoft Cloud App Security](..\media\manage-app-protection-governance\mapg-integration.png)

<span data-ttu-id="b2fec-134">Bovendien stuurt app-beheer waarschuwingen als signalen naar Microsoft Cloud App Security en Microsoft 365 Defender, en ontvangt app-beheer waarschuwingen van Microsoft Cloud App Security, om een meer gedetailleerde analyse van app-gebaseerde beveiligingsincidenten mogelijk te maken.</span><span class="sxs-lookup"><span data-stu-id="b2fec-134">Additionally, app governance sends its alerts as signals to Microsoft Cloud App Security and Microsoft 365 Defender, and app governance receives alerts from Microsoft Cloud App Security, to enable more detailed analysis of app-based security incidents.</span></span>

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

## <a name="using-app-governance"></a><span data-ttu-id="b2fec-135">App-beheer gebruiken</span><span class="sxs-lookup"><span data-stu-id="b2fec-135">Using app governance</span></span>

<span data-ttu-id="b2fec-136">Het gebruik van app-beheer om uw tenant en de bijbehorende gegevens te beschermen tegen potentieel schadelijke of zich slecht gedragende apps valt uiteen in de volgende drie kernmogelijkheden:</span><span class="sxs-lookup"><span data-stu-id="b2fec-136">Using app governance to protect your tenant and its data from potentially malicious or ill-behaved apps falls into these three core capabilities:</span></span>

| <span data-ttu-id="b2fec-137">Mogelijkheid</span><span class="sxs-lookup"><span data-stu-id="b2fec-137">Capability</span></span> | <span data-ttu-id="b2fec-138">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="b2fec-138">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="b2fec-139">Zichtbaarheid en inzichten van apps</span><span class="sxs-lookup"><span data-stu-id="b2fec-139">App visibility and insights</span></span>](app-governance-visibility-insights-overview.md) | <span data-ttu-id="b2fec-140">Bekijk een 360°-weergave van verkeer en activiteit van de Microsoft 365 toepassingen in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="b2fec-140">Get a 360° view on traffic and activity of the Microsoft 365 applications in your tenant.</span></span> |
| [<span data-ttu-id="b2fec-141">App-beleid voor versterkt beheer</span><span class="sxs-lookup"><span data-stu-id="b2fec-141">App policies for reinforced governance</span></span>](app-governance-app-policies-overview.md) | <span data-ttu-id="b2fec-142">Maak proactief of reactief app-beleid, waarmee u beheer kunt afdwingen voor uw Microsoft 365-apps.</span><span class="sxs-lookup"><span data-stu-id="b2fec-142">Create proactive or reactive app policies, which will allow you to enforce governance for your Microsoft 3635 apps.</span></span> |
| [<span data-ttu-id="b2fec-143">Detectie en herstel</span><span class="sxs-lookup"><span data-stu-id="b2fec-143">Detection and remediation</span></span>](app-governance-detect-remediate-overview.md) | <span data-ttu-id="b2fec-144">Op basis van platformdetectiewaarschuwingen of door beleid gegenereerde detectiewaarschuwingen controleert u uw apps op afwijkend app-gedrag en herstelt u deze, automatisch op basis van app-beleidsinstellingen of handmatig.</span><span class="sxs-lookup"><span data-stu-id="b2fec-144">Based on platform detection alerts or policy-generated detection alerts, monitor your apps for anomalous app behavior and remediate them, either automatically based on app policy settings or manually.</span></span> |
|||
