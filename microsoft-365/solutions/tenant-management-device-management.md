---
title: Stap 5. Apparaat- en app-beheer voor uw Microsoft 365 voor enterprise tenants
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
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Implementeer de juiste optie voor apparaat- en app-beheer voor uw Microsoft 365 tenants.
ms.openlocfilehash: 0351f6be3f191e1a131da5b0b665a205a0abda8c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51050992"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="43175-104">Stap 5.</span><span class="sxs-lookup"><span data-stu-id="43175-104">Step 5.</span></span> <span data-ttu-id="43175-105">Apparaat- en app-beheer voor uw Microsoft 365 voor enterprise tenants</span><span class="sxs-lookup"><span data-stu-id="43175-105">Device and app management for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="43175-106">Microsoft 365 voor bedrijven bevat functies voor het beheren van apparaten en het gebruik van apps op die apparaten binnen uw organisatie met MDM (Mobile Device Management) en Mobile Application Management (MAM).</span><span class="sxs-lookup"><span data-stu-id="43175-106">Microsoft 365 for enterprise includes features to help manage devices and the use of apps on those devices within your organization with mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="43175-107">U kunt iOS, Android, macOS en Windows beheren om de toegang tot de resources van uw organisatie, inclusief uw gegevens, te beschermen.</span><span class="sxs-lookup"><span data-stu-id="43175-107">You can manage iOS, Android, macOS, and Windows devices to protect access to your organization's resources, including your data.</span></span> <span data-ttu-id="43175-108">U kunt bijvoorbeeld voorkomen dat e-mailberichten worden verzonden naar personen buiten uw organisatie of organisatiegegevens isoleren van persoonlijke gegevens op de persoonlijke apparaten van uw werknemer.</span><span class="sxs-lookup"><span data-stu-id="43175-108">For example, you can prevent emails from being sent to people outside your organization or isolate organization data from personal data on your worker's personal devices.</span></span>

<span data-ttu-id="43175-109">Hier ziet u een voorbeeld van de validatie en het beheer van gebruikers, hun apparaten en hun gebruik van lokale en cloudproductiviteitsapps, zoals Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="43175-109">Here is an example of the validation and management of users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![Validatie en beheer van gebruikers, apparaten en apps](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

<span data-ttu-id="43175-111">Als u de resources van uw organisatie wilt beveiligen en beveiligen, bevat Microsoft 365 voor bedrijven functies voor het beheren van apparaten en hun toegang tot apps.</span><span class="sxs-lookup"><span data-stu-id="43175-111">To help you secure and protect your organization's resources, Microsoft 365 for enterprise includes features to help manage devices and their access to apps.</span></span> <span data-ttu-id="43175-112">Er zijn twee opties voor apparaatbeheer:</span><span class="sxs-lookup"><span data-stu-id="43175-112">There are two options for device management:</span></span>

- <span data-ttu-id="43175-113">Microsoft Intune, een uitgebreide oplossing voor apparaat- en app-beheer voor ondernemingen.</span><span class="sxs-lookup"><span data-stu-id="43175-113">Microsoft Intune, which is a comprehensive device and app management solution for enterprises.</span></span>
- <span data-ttu-id="43175-114">Basismobiliteit en beveiliging, een subset van Intune-services die is opgenomen in alle Microsoft 365 voor het beheren van apparaten in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="43175-114">Basic Mobility and Security, which is a subset of Intune services included with all Microsoft 365 products for managing devices in your organization.</span></span> <span data-ttu-id="43175-115">Zie Mogelijkheden van [basismobiliteit](../admin/basic-mobility-security/capabilities.md)en beveiliging voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="43175-115">For more information, see [Capabilities of Basic Mobility and Security](../admin/basic-mobility-security/capabilities.md).</span></span>

<span data-ttu-id="43175-116">Als u een Microsoft 365 E3 of E5 hebt, moet u Intune gebruiken.</span><span class="sxs-lookup"><span data-stu-id="43175-116">If you have Microsoft 365 E3 or E5, you should use Intune.</span></span>

## <a name="microsoft-intune"></a><span data-ttu-id="43175-117">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="43175-117">Microsoft Intune</span></span>

<span data-ttu-id="43175-118">U gebruikt [Microsoft Intune](/mem/intune/fundamentals/planning-guide) om de toegang tot uw organisatie te beheren met behulp van MDM of MAM.</span><span class="sxs-lookup"><span data-stu-id="43175-118">You use [Microsoft Intune](/mem/intune/fundamentals/planning-guide) to manage access to your organization using MDM or MAM.</span></span> <span data-ttu-id="43175-119">MDM is wanneer gebruikers hun apparaten 'registreren' in Intune.</span><span class="sxs-lookup"><span data-stu-id="43175-119">MDM is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="43175-120">Nadat een apparaat is geregistreerd, is het een beheerd apparaat en kan het beleid, de regels en instellingen van uw organisatie worden ontvangen.</span><span class="sxs-lookup"><span data-stu-id="43175-120">After a device is enrolled, it is a managed device and can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="43175-121">U kunt bijvoorbeeld specifieke apps installeren, een wachtwoordbeleid maken, een VPN-verbinding installeren en meer.</span><span class="sxs-lookup"><span data-stu-id="43175-121">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="43175-122">Gebruikers met hun eigen persoonlijke apparaten willen hun apparaten mogelijk niet registreren of worden beheerd door Intune en het beleid van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="43175-122">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="43175-123">Maar u moet nog steeds de resources en gegevens van uw organisatie beschermen.</span><span class="sxs-lookup"><span data-stu-id="43175-123">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="43175-124">In dit scenario kunt u uw apps beveiligen met MAM.</span><span class="sxs-lookup"><span data-stu-id="43175-124">In this scenario, you can protect your apps using MAM.</span></span> <span data-ttu-id="43175-125">U kunt bijvoorbeeld een MAM-beleid gebruiken waarin een gebruiker een pincode moet invoeren bij het openen van SharePoint op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="43175-125">For example, you can use an MAM policy that requires a user to enter a PIN when accessing SharePoint on the device.</span></span>

<span data-ttu-id="43175-126">U bepaalt ook hoe u persoonlijke apparaten en apparaten van de organisatie gaat beheren.</span><span class="sxs-lookup"><span data-stu-id="43175-126">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="43175-127">Mogelijk wilt u apparaten anders behandelen, afhankelijk van hun gebruik.</span><span class="sxs-lookup"><span data-stu-id="43175-127">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="identity-and-device-access-configurations"></a><span data-ttu-id="43175-128">Configuratie van identiteiten en apparaattoegang</span><span class="sxs-lookup"><span data-stu-id="43175-128">Identity and device access configurations</span></span>

<span data-ttu-id="43175-129">Microsoft biedt een set configuraties voor identiteits- en [apparaattoegang](../security/defender-365-security/microsoft-365-policies-configurations.md) om een veilig en productief personeel te garanderen.</span><span class="sxs-lookup"><span data-stu-id="43175-129">Microsoft provides a set of configurations for [identity and device access](../security/defender-365-security/microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="43175-130">Deze configuraties omvatten het gebruik van:</span><span class="sxs-lookup"><span data-stu-id="43175-130">These configurations include the use of:</span></span>

- <span data-ttu-id="43175-131">Azure AD-beleid voor voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="43175-131">Azure AD Conditional Access policies</span></span>
- <span data-ttu-id="43175-132">Microsoft Intune beleid voor apparaat compliance en app-beveiliging</span><span class="sxs-lookup"><span data-stu-id="43175-132">Microsoft Intune device compliance and app protection policies</span></span>
- <span data-ttu-id="43175-133">Beleid voor gebruikersrisico's voor Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="43175-133">Azure AD Identity Protection user risk policies</span></span>
- <span data-ttu-id="43175-134">Aanvullende beleidsregels voor cloud-apps</span><span class="sxs-lookup"><span data-stu-id="43175-134">Additional policies of cloud apps</span></span>

<span data-ttu-id="43175-135">Hier ziet u een voorbeeld van de toepassing van deze instellingen en beleidsregels voor het valideren en beperken van gebruikers, hun apparaten en het gebruik van lokale en cloudproductiviteitsapps, zoals Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="43175-135">Here is an example of the application of these settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![Configuraties voor identiteits- en apparaattoegang voor vereisten en beperkingen voor gebruikers, hun apparaten en het gebruik van apps](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

<span data-ttu-id="43175-137">Gebruik de configuraties in deze artikelen voor apparaattoegang en app-beheer:</span><span class="sxs-lookup"><span data-stu-id="43175-137">For device access and app management, use the configurations in these articles:</span></span>

- [<span data-ttu-id="43175-138">Vereisten</span><span class="sxs-lookup"><span data-stu-id="43175-138">Prerequisites</span></span>](../security/defender-365-security/identity-access-prerequisites.md)
- [<span data-ttu-id="43175-139">Algemeen beleid voor identiteiten en apparaattoegang</span><span class="sxs-lookup"><span data-stu-id="43175-139">Common identity and device access policies</span></span>](../security/defender-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a><span data-ttu-id="43175-140">Resultaten van stap 5</span><span class="sxs-lookup"><span data-stu-id="43175-140">Results of Step 5</span></span>

<span data-ttu-id="43175-141">Voor apparaat- en app-beheer voor uw Microsoft 365 tenant hebt u de Intune-instellingen en -beleidsregels bepaald om gebruikers, hun apparaten en hun gebruik van lokale en cloudproductiviteitsapps te valideren en te beperken.</span><span class="sxs-lookup"><span data-stu-id="43175-141">For device and app management for your Microsoft 365 tenant, you have determined the Intune settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps.</span></span>

<span data-ttu-id="43175-142">Hier is een voorbeeld van een tenant met Intune-apparaat- en app-beheer met de nieuwe elementen gemarkeerd.</span><span class="sxs-lookup"><span data-stu-id="43175-142">Here is an example of a tenant with Intune device and app management with the new elements highlighted.</span></span>

![Voorbeeld van een tenant met Intune-apparaat- en app-beheer](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

<span data-ttu-id="43175-144">In deze afbeelding heeft de tenant:</span><span class="sxs-lookup"><span data-stu-id="43175-144">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="43175-145">Apparaten die eigendom zijn van de organisatie die zijn geregistreerd bij Intune.</span><span class="sxs-lookup"><span data-stu-id="43175-145">Organization-owned devices enrolled in Intune.</span></span>
- <span data-ttu-id="43175-146">Intune-apparaat- en app-beleid voor geregistreerde en persoonlijke apparaten.</span><span class="sxs-lookup"><span data-stu-id="43175-146">Intune device and app policies for enrolled and personal devices.</span></span>

## <a name="ongoing-maintenance-for-device-and-app-management"></a><span data-ttu-id="43175-147">Doorlopend onderhoud voor apparaat- en app-beheer</span><span class="sxs-lookup"><span data-stu-id="43175-147">Ongoing maintenance for device and app management</span></span>

<span data-ttu-id="43175-148">Op permanente basis moet u mogelijk het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="43175-148">On an ongoing basis, you might need to:</span></span> 

- <span data-ttu-id="43175-149">Apparaatinschrijving beheren.</span><span class="sxs-lookup"><span data-stu-id="43175-149">Manage device enrollment.</span></span>
- <span data-ttu-id="43175-150">Wijzig uw instellingen en beleid voor extra apps, apparaten en beveiligingsvereisten.</span><span class="sxs-lookup"><span data-stu-id="43175-150">Revise your settings and policies for additional apps, devices, and security requirements.</span></span>