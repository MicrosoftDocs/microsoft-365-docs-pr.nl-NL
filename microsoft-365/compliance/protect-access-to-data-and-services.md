---
title: Toegang van gebruikers en apparaten beveiligen
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: Informatie over het beveiligen van gebruikers- en apparaattoegang tot Microsoft 365 en services en beschermen tegen gegevensverlies.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9ff7bd2ff8b4b333eb30a6cc82797a8968941e0b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "52162275"
---
# <a name="protect-user-and-device-access"></a><span data-ttu-id="d7615-103">Toegang van gebruikers en apparaten beveiligen</span><span class="sxs-lookup"><span data-stu-id="d7615-103">Protect user and device access</span></span>

<span data-ttu-id="d7615-104">De toegang tot uw Microsoft 365 en services is van cruciaal belang om u te beschermen tegen cyberaanvallen en om te beschermen tegen gegevensverlies.</span><span class="sxs-lookup"><span data-stu-id="d7615-104">Protecting access to your Microsoft 365 data and services is crucial to defending against cyberattacks and guarding against data loss.</span></span> <span data-ttu-id="d7615-105">Dezelfde beveiligingen kunnen worden toegepast op andere SaaS-toepassingen in uw omgeving en zelfs op on-premises toepassingen die zijn gepubliceerd met Azure Active Directory Application Proxy.</span><span class="sxs-lookup"><span data-stu-id="d7615-105">The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="d7615-106">Stap 1: Aanbevelingen controleren</span><span class="sxs-lookup"><span data-stu-id="d7615-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="d7615-107">Aanbevolen mogelijkheden voor het beschermen van identiteiten en apparaten die toegang krijgen tot Office 365, andere SaaS-Services en on-premises toepassingen die worden gepubliceerd met de Azure AD-toepassingsproxy.</span><span class="sxs-lookup"><span data-stu-id="d7615-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="d7615-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656)  |  [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657)  |  [Meer talen](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="d7615-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-protect-administrator-accounts-and-access"></a><span data-ttu-id="d7615-109">Stap 2: Beheerdersaccounts en toegang beveiligen</span><span class="sxs-lookup"><span data-stu-id="d7615-109">Step 2: Protect administrator accounts and access</span></span>
<span data-ttu-id="d7615-110">De beheeraccounts die u gebruikt om uw Microsoft 365 beheren, bevatten verhoogde bevoegdheden.</span><span class="sxs-lookup"><span data-stu-id="d7615-110">The administrative accounts you use to administer your Microsoft 365 environment include elevated privileges.</span></span> <span data-ttu-id="d7615-111">Dit zijn waardevolle doelen voor hackers en cyberattackers.</span><span class="sxs-lookup"><span data-stu-id="d7615-111">These are valuable targets for hackers and cyberattackers.</span></span> 

<span data-ttu-id="d7615-112">Gebruik eerst alleen beheerdersaccounts voor beheer.</span><span class="sxs-lookup"><span data-stu-id="d7615-112">Begin by using administrator accounts only for administration.</span></span> <span data-ttu-id="d7615-113">Beheerders moeten een afzonderlijk gebruikersaccount hebben voor regelmatig, niet-administratief gebruik en hun beheeraccount alleen gebruiken wanneer dat nodig is om een taak te voltooien die is gekoppeld aan hun functie.</span><span class="sxs-lookup"><span data-stu-id="d7615-113">Admins should have a separate user account for regular, non-administrative use and only use their administrative account when necessary to complete a task associated with their job function.</span></span>

<span data-ttu-id="d7615-114">Bescherm uw beheerdersaccounts met meervoudige verificatie en voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="d7615-114">Protect your administrator accounts with multi-factor authentication and conditional access.</span></span> <span data-ttu-id="d7615-115">Zie Beheerdersaccounts beveiligen voor [meer informatie.](../security/defender-365-security/identity-access-prerequisites.md#protecting-administrator-accounts)</span><span class="sxs-lookup"><span data-stu-id="d7615-115">For more information, see [Protecting administrator accounts](../security/defender-365-security/identity-access-prerequisites.md#protecting-administrator-accounts).</span></span> 

<span data-ttu-id="d7615-116">Configureer vervolgens het beheer van geprivilegieerde toegang in Office 365.</span><span class="sxs-lookup"><span data-stu-id="d7615-116">Next, configure privileged access management in Office 365.</span></span> <span data-ttu-id="d7615-117">Met bevoorrecht toegangsbeheer kunt u gedetailleerde toegangsbeheer over bevoorrechte beheertaken in Office 365.</span><span class="sxs-lookup"><span data-stu-id="d7615-117">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="d7615-118">Het kan uw organisatie helpen beschermen tegen inbreuken die bestaande bevoorrechte beheerdersaccounts kunnen gebruiken met permanente toegang tot gevoelige gegevens of toegang tot kritieke configuratie-instellingen.</span><span class="sxs-lookup"><span data-stu-id="d7615-118">It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span>

- [<span data-ttu-id="d7615-119">Overzicht van bevoorrecht toegangsbeheer</span><span class="sxs-lookup"><span data-stu-id="d7615-119">Overview of privileged access management</span></span>](privileged-access-management-overview.md)
- [<span data-ttu-id="d7615-120">Bevoorrecht toegangsbeheer configureren</span><span class="sxs-lookup"><span data-stu-id="d7615-120">Configure privileged access management</span></span>](privileged-access-management-configuration.md)

<span data-ttu-id="d7615-121">Een andere topaanbeveling is het gebruik van werkstations die speciaal zijn geconfigureerd voor beheerwerk.</span><span class="sxs-lookup"><span data-stu-id="d7615-121">Another top recommendation is to use workstations specifically configured for administrative work.</span></span> <span data-ttu-id="d7615-122">Dit zijn speciale apparaten die alleen worden gebruikt voor beheertaken.</span><span class="sxs-lookup"><span data-stu-id="d7615-122">These are dedicated devices that are only used for administrative tasks.</span></span> <span data-ttu-id="d7615-123">Zie [Geprivilegieerde toegang beveiligen.](/windows-server/identity/securing-privileged-access/securing-privileged-access)</span><span class="sxs-lookup"><span data-stu-id="d7615-123">See [Securing privileged access](/windows-server/identity/securing-privileged-access/securing-privileged-access).</span></span>

<span data-ttu-id="d7615-124">Ten slotte kunt u de impact van onbedoelde afwezigheid van beheerderstoegang beperken door twee of meer accounts voor toegang voor noodgevallen te maken in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="d7615-124">Finally, you can mitigate the impact of inadvertent lack of administrative access by creating two or more emergency access accounts in your tenant.</span></span> <span data-ttu-id="d7615-125">Zie [Accounts voor toegang voor noodgevallen beheren in Azure AD](/azure/active-directory/users-groups-roles/directory-emergency-access).</span><span class="sxs-lookup"><span data-stu-id="d7615-125">See [Manage emergency access accounts in Azure AD](/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span> 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a><span data-ttu-id="d7615-126">Stap 3: Aanbevolen identiteits- en apparaattoegangsbeleid configureren</span><span class="sxs-lookup"><span data-stu-id="d7615-126">Step 3: Configure recommended identity and device access policies</span></span>
<span data-ttu-id="d7615-127">Multi-factor authentication (MFA) en beleid voor voorwaardelijke toegang zijn krachtige hulpprogramma's om gecompromitteerde accounts en ongeautoriseerde toegang te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="d7615-127">Multi-factor authentication (MFA) and conditional access policies are powerful tools for mitigating against compromised accounts and unauthorized access.</span></span> <span data-ttu-id="d7615-128">We raden u aan een set beleidsregels te implementeren die samen zijn getest.</span><span class="sxs-lookup"><span data-stu-id="d7615-128">We recommend implementing a set of policies that have been tested together.</span></span> <span data-ttu-id="d7615-129">Zie Identiteits- en [apparaattoegangsconfiguraties](../security/defender-365-security/microsoft-365-policies-configurations.md)voor meer informatie, inclusief implementatiestappen.</span><span class="sxs-lookup"><span data-stu-id="d7615-129">For more information, including deployment steps, see [Identity and device access configurations](../security/defender-365-security/microsoft-365-policies-configurations.md).</span></span>

 <span data-ttu-id="d7615-130">Met dit beleid worden de volgende mogelijkheden geïmplementeerd:</span><span class="sxs-lookup"><span data-stu-id="d7615-130">These policies implement the following capabilities:</span></span>
- <span data-ttu-id="d7615-131">Mult-factor-verificatie</span><span class="sxs-lookup"><span data-stu-id="d7615-131">Mult-factor authentication</span></span>
- <span data-ttu-id="d7615-132">Voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="d7615-132">Conditional access</span></span>
- <span data-ttu-id="d7615-133">Intune-appbeveiliging (app en gegevensbescherming voor apparaten)</span><span class="sxs-lookup"><span data-stu-id="d7615-133">Intune app protection (app and data protection for devices)</span></span>
- <span data-ttu-id="d7615-134">Intune-apparaat compliance</span><span class="sxs-lookup"><span data-stu-id="d7615-134">Intune device compliance</span></span>
- <span data-ttu-id="d7615-135">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="d7615-135">Azure AD Identity Protection</span></span>

<span data-ttu-id="d7615-136">Voor het implementeren van intune-apparaat compliance is apparaatinschrijving vereist.</span><span class="sxs-lookup"><span data-stu-id="d7615-136">Implementing Intune device compliance requires device enrollment.</span></span> <span data-ttu-id="d7615-137">Als u apparaten beheert, kunt u ervoor zorgen dat ze gezond en compatibel zijn voordat u ze toegang geeft tot resources in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="d7615-137">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment.</span></span> <span data-ttu-id="d7615-138">Zie [Apparaten voor beheer registreren in Intune](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="d7615-138">See [Enroll devices for management in Intune](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span></span>

## <a name="step-4-configure-sharepoint-device-access-policies"></a><span data-ttu-id="d7615-139">Stap 4: Beleid SharePoint apparaattoegang configureren</span><span class="sxs-lookup"><span data-stu-id="d7615-139">Step 4: Configure SharePoint device access policies</span></span>

<span data-ttu-id="d7615-140">Microsoft raadt u aan om inhoud op SharePoint sites te beveiligen met gevoelige en sterk gereguleerde inhoud met besturingselementen voor apparaattoegang.</span><span class="sxs-lookup"><span data-stu-id="d7615-140">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="d7615-141">Zie Beleidsaanbevelingen voor het beveiligen van SharePoint [sites en bestanden voor meer informatie.](../security/defender-365-security/sharepoint-file-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="d7615-141">For more information, see [Policy recommendations for securing SharePoint sites and files](../security/defender-365-security/sharepoint-file-access-policies.md).</span></span>



