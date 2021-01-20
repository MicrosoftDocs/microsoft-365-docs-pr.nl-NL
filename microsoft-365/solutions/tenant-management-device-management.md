---
title: Stap 5. Apparaten en apps beheren voor uw Microsoft 365 for Enterprise-tenants
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: Implementeer de juiste optie voor apparatuur en app-beheer voor uw Microsoft 365-tenants.
ms.openlocfilehash: a581af3ec2ec192112656f1919e27f5b05a41cb1
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908507"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="622a6-104">Stap 5.</span><span class="sxs-lookup"><span data-stu-id="622a6-104">Step 5.</span></span> <span data-ttu-id="622a6-105">Apparaten en apps beheren voor uw Microsoft 365 for Enterprise-tenants</span><span class="sxs-lookup"><span data-stu-id="622a6-105">Device and app management for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="622a6-106">Microsoft 365 voor Enterprise bevat functies waarmee u apparaten en het gebruik van apps op deze apparaten binnen uw organisatie kunt beheren met een MDM (Mobile Device Management) en Mobile Application Management (MAM).</span><span class="sxs-lookup"><span data-stu-id="622a6-106">Microsoft 365 for enterprise includes features to help manage devices and the use of apps on those devices within your organization with mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="622a6-107">U kunt apparaten van iOS, Android, macOS en Windows beheren om de toegang tot de bronnen van uw organisatie te beschermen, waaronder uw gegevens.</span><span class="sxs-lookup"><span data-stu-id="622a6-107">You can manage iOS, Android, macOS, and Windows devices to protect access to your organization's resources, including your data.</span></span> <span data-ttu-id="622a6-108">U kunt voorkomen dat e-mailberichten naar personen buiten uw organisatie worden verzonden of organisatiegegevens van persoonlijke gegevens op de persoonlijke apparaten van de werknemer isoleren.</span><span class="sxs-lookup"><span data-stu-id="622a6-108">For example, you can prevent emails from being sent to people outside your organization or isolate organization data from personal data on your worker's personal devices.</span></span>

<span data-ttu-id="622a6-109">Hier ziet u een voorbeeld van de validering en het beheer van gebruikers, de bijbehorende apparaten en het gebruik van apps voor lokale en Cloud productiviteit, zoals Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="622a6-109">Here is an example of the validation and management of users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![Validatie en beheer van gebruikers, apparaten en apps](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

<span data-ttu-id="622a6-111">Microsoft 365 for Enterprise bevat functies waarmee u apparaten en hun toegang tot apps kunt beschermen en beschermen.</span><span class="sxs-lookup"><span data-stu-id="622a6-111">To help you secure and protect your organization's resources, Microsoft 365 for enterprise includes features to help manage devices and their access to apps.</span></span> <span data-ttu-id="622a6-112">Er zijn twee opties voor Apparaatbeheer:</span><span class="sxs-lookup"><span data-stu-id="622a6-112">There are two options for device management:</span></span>

- <span data-ttu-id="622a6-113">Microsoft intune (dit is een uitgebreide oplossing voor apparatuur en app-beheer) voor ondernemingen.</span><span class="sxs-lookup"><span data-stu-id="622a6-113">Microsoft Intune, which is a comprehensive device and app management solution for enterprises.</span></span>
- <span data-ttu-id="622a6-114">Basis mobiliteit en beveiliging, een subset van intune-services die deel uitmaken van alle Microsoft 365-producten voor het beheren van apparaten in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="622a6-114">Basic Mobility and Security, which is a subset of Intune services included with all Microsoft 365 products for managing devices in your organization.</span></span> <span data-ttu-id="622a6-115">Zie [mogelijkheden van basis mobiliteit en beveiliging](https://docs.microsoft.com/microsoft-365/admin/basic-mobility-security/capabilities)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="622a6-115">For more information, see [Capabilities of Basic Mobility and Security](https://docs.microsoft.com/microsoft-365/admin/basic-mobility-security/capabilities).</span></span>

<span data-ttu-id="622a6-116">Als u Microsoft 365 E3 of E5 hebt, gebruikt u intune.</span><span class="sxs-lookup"><span data-stu-id="622a6-116">If you have Microsoft 365 E3 or E5, you should use Intune.</span></span>

## <a name="microsoft-intune"></a><span data-ttu-id="622a6-117">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="622a6-117">Microsoft Intune</span></span>

<span data-ttu-id="622a6-118">U kunt [Microsoft intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide) gebruiken om de toegang tot uw organisatie te beheren via MDM of mam.</span><span class="sxs-lookup"><span data-stu-id="622a6-118">You use [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide) to manage access to your organization using MDM or MAM.</span></span> <span data-ttu-id="622a6-119">MDM is wanneer gebruikers de optie hun apparaat registreren in intune.</span><span class="sxs-lookup"><span data-stu-id="622a6-119">MDM is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="622a6-120">Als een apparaat is ingeschreven, is dit een beheerd apparaat en kan het beleid, de regels en instellingen van uw organisatie worden ontvangen.</span><span class="sxs-lookup"><span data-stu-id="622a6-120">After a device is enrolled, it is a managed device and can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="622a6-121">U kunt bijvoorbeeld bepaalde apps installeren, een wachtwoordbeleid maken, een VPN-verbinding installeren en nog veel meer.</span><span class="sxs-lookup"><span data-stu-id="622a6-121">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="622a6-122">Gebruikers met hun eigen persoonlijke apparaten willen hun apparaten mogelijk niet registreren of worden beheerd door intune en het beleid van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="622a6-122">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="622a6-123">U moet de bronnen en gegevens van uw organisatie nog altijd beschermen.</span><span class="sxs-lookup"><span data-stu-id="622a6-123">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="622a6-124">In dit scenario kunt u uw apps beschermen met behulp van MAM.</span><span class="sxs-lookup"><span data-stu-id="622a6-124">In this scenario, you can protect your apps using MAM.</span></span> <span data-ttu-id="622a6-125">U kunt bijvoorbeeld een MAM-beleid gebruiken waarbij een gebruiker een pincode moet invoeren bij het openen van SharePoint op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="622a6-125">For example, you can use an MAM policy that requires a user to enter a PIN when accessing SharePoint on the device.</span></span>

<span data-ttu-id="622a6-126">U kunt ook bepalen hoe u persoonlijke apparaten en apparaten met de eigen organisatie gaat beheren.</span><span class="sxs-lookup"><span data-stu-id="622a6-126">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="622a6-127">U kunt apparaten anders behandelen, afhankelijk van hun gebruik.</span><span class="sxs-lookup"><span data-stu-id="622a6-127">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="identity-and-device-access-configurations"></a><span data-ttu-id="622a6-128">Configuratie van identiteiten en apparaattoegang</span><span class="sxs-lookup"><span data-stu-id="622a6-128">Identity and device access configurations</span></span>

<span data-ttu-id="622a6-129">Microsoft biedt een reeks configuraties voor [identiteit en Apparaattoegang,](../security/office-365-security/microsoft-365-policies-configurations.md) zodat u zich kunt beschermen tegen een veilig en productief personeel.</span><span class="sxs-lookup"><span data-stu-id="622a6-129">Microsoft provides a set of configurations for [identity and device access](../security/office-365-security/microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="622a6-130">Voor deze configuraties gelden de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="622a6-130">These configurations include the use of:</span></span>

- <span data-ttu-id="622a6-131">Azure AD-beleid voor voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="622a6-131">Azure AD Conditional Access policies</span></span>
- <span data-ttu-id="622a6-132">Naleving van Microsoft intune-apparaat en beleid voor app-beveiliging</span><span class="sxs-lookup"><span data-stu-id="622a6-132">Microsoft Intune device compliance and app protection policies</span></span>
- <span data-ttu-id="622a6-133">Azure AD Identity Protection User Risk policies</span><span class="sxs-lookup"><span data-stu-id="622a6-133">Azure AD Identity Protection user risk policies</span></span>
- <span data-ttu-id="622a6-134">Extra beleidsregels voor Cloud-apps</span><span class="sxs-lookup"><span data-stu-id="622a6-134">Additional policies of cloud apps</span></span>

<span data-ttu-id="622a6-135">Hier ziet u een voorbeeld van de toepassing van deze instellingen en beleidsregels voor het valideren en beperken van gebruikers, hun apparaten, en het gebruik van de apps voor lokale en Cloud productiviteit zoals Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="622a6-135">Here is an example of the application of these settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![Configuraties voor identiteits-en Apparaattoegang voor vereisten en beperkingen voor gebruikers, hun apparaten en het gebruik van apps](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

<span data-ttu-id="622a6-137">Gebruik voor toegang tot apparaten en app-beheer de configuraties in de volgende artikelen:</span><span class="sxs-lookup"><span data-stu-id="622a6-137">For device access and app management, use the configurations in these articles:</span></span>

- [<span data-ttu-id="622a6-138">Vereisten</span><span class="sxs-lookup"><span data-stu-id="622a6-138">Prerequisites</span></span>](../security/office-365-security/identity-access-prerequisites.md)
- [<span data-ttu-id="622a6-139">Algemeen beleid voor identiteiten en apparaattoegang</span><span class="sxs-lookup"><span data-stu-id="622a6-139">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a><span data-ttu-id="622a6-140">Resultaten van stap 5</span><span class="sxs-lookup"><span data-stu-id="622a6-140">Results of Step 5</span></span>

<span data-ttu-id="622a6-141">Voor apparaat-en app-beheer voor uw Microsoft 365-Tenant hebt u de intune-instellingen en het beleid vastgesteld voor het valideren en beperken van gebruikers, hun apparaten en het gebruik van de apps voor lokale en Cloud productiviteit.</span><span class="sxs-lookup"><span data-stu-id="622a6-141">For device and app management for your Microsoft 365 tenant, you have determined the Intune settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps.</span></span>

<span data-ttu-id="622a6-142">Hier ziet u een voorbeeld van een Tenant met intune-apparaat en app-beheer waarbij de nieuwe elementen zijn gemarkeerd.</span><span class="sxs-lookup"><span data-stu-id="622a6-142">Here is an example of a tenant with Intune device and app management with the new elements highlighted.</span></span>

![Voorbeeld van een Tenant met intune-apparaat en app-beheer](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

<span data-ttu-id="622a6-144">In deze afbeelding is de Tenant:</span><span class="sxs-lookup"><span data-stu-id="622a6-144">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="622a6-145">Apparaten met een organisatie die zijn geregistreerd voor intune.</span><span class="sxs-lookup"><span data-stu-id="622a6-145">Organization-owned devices enrolled in Intune.</span></span>
- <span data-ttu-id="622a6-146">InTune-apparaat en app-beleid voor ingeschreven en persoonlijke apparaten.</span><span class="sxs-lookup"><span data-stu-id="622a6-146">Intune device and app policies for enrolled and personal devices.</span></span>

## <a name="ongoing-maintenance-for-device-and-app-management"></a><span data-ttu-id="622a6-147">Voortdurend onderhoud van apparatuur en apps beheren</span><span class="sxs-lookup"><span data-stu-id="622a6-147">Ongoing maintenance for device and app management</span></span>

<span data-ttu-id="622a6-148">Het kan zijn dat u het volgende moet doen:</span><span class="sxs-lookup"><span data-stu-id="622a6-148">On an ongoing basis, you might need to:</span></span> 

- <span data-ttu-id="622a6-149">De registratie van apparaten beheren.</span><span class="sxs-lookup"><span data-stu-id="622a6-149">Manage device enrollment.</span></span>
- <span data-ttu-id="622a6-150">De instellingen en het beleid voor extra apps, apparaten en beveiligingsvereisten wijzigen.</span><span class="sxs-lookup"><span data-stu-id="622a6-150">Revise your settings and policies for additional apps, devices, and security requirements.</span></span>
