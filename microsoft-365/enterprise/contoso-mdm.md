---
title: Beheer van mobiele apparaten voor Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Meer informatie over hoe Contoso Microsoft Intune gebruikt in Microsoft 365 Enterprise voor het beheren van haar apparaten en de apps die erop worden uitgevoerd.
ms.openlocfilehash: 7232c89cc105525cc57facd5a1b9de06426adbca
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42811285"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="f8cdd-103">Beheer van mobiele apparaten voor Contoso</span><span class="sxs-lookup"><span data-stu-id="f8cdd-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="f8cdd-104">Microsoft 365 Enterprise omvat Intune en een verzameling Azure-services om mobiele apparaten, toepassingsbeheer en beveiliging te ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="f8cdd-104">Microsoft 365 Enterprise includes Intune and a set of Azure services to support mobile device and application management and security.</span></span>

<span data-ttu-id="f8cdd-105">Contoso heeft veel mobiele medewerkers, waarvan sommigen een werkplek hebben in Contoso-locaties en anderen niet.</span><span class="sxs-lookup"><span data-stu-id="f8cdd-105">Contoso has many mobile-enabled employees, some of which have offices in Contoso locations and some of which have no offices.</span></span> <span data-ttu-id="f8cdd-106">Contoso had behoefte aan een manier om de productiviteit van medewerkers in te schakelen, maar de apparaten, de gegevens op die apparaten en het gedrag van toepassingen veilig te houden.</span><span class="sxs-lookup"><span data-stu-id="f8cdd-106">Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="f8cdd-107">Plannen</span><span class="sxs-lookup"><span data-stu-id="f8cdd-107">Plan</span></span>

<span data-ttu-id="f8cdd-108">Al vroeg in de analyse van beheer van mobiele apparaten voor Microsoft 365 Enterprise identificeerde Contoso de volgende Intune-use cases:</span><span class="sxs-lookup"><span data-stu-id="f8cdd-108">Early in the analysis of mobile device management for Microsoft 365 Enterprise, Contoso identified the following Intune use cases:</span></span>

- <span data-ttu-id="f8cdd-109">Exchange Online-e-mail en -gegevens beschermen, zodat ze veilig kunnen worden gebruikt door mobiele apparaten</span><span class="sxs-lookup"><span data-stu-id="f8cdd-109">Protect Exchange Online email and data so it can be safely accessed by mobile devices</span></span>
- <span data-ttu-id="f8cdd-110">Een BYOD-programma (Bring Your Own Device) implementeren voor Contoso-werknemers</span><span class="sxs-lookup"><span data-stu-id="f8cdd-110">Implement a bring your own device (BYOD) program for Contoso employees</span></span>
- <span data-ttu-id="f8cdd-111">Telefoons en gedeelde tabletten met beperkt gebruik in eigendom van Contoso uitgeven aan Contoso-werknemers.</span><span class="sxs-lookup"><span data-stu-id="f8cdd-111">Issue organization-owned phones and limited-use shared tablets to Contoso employees</span></span>

<span data-ttu-id="f8cdd-112">Contoso gebruikt Intune niet om:</span><span class="sxs-lookup"><span data-stu-id="f8cdd-112">Contoso is not using Intune to:</span></span>

- <span data-ttu-id="f8cdd-113">Werknemers veilige toegang te bieden tot Office 365 vanuit een onbeheerde openbare kiosk</span><span class="sxs-lookup"><span data-stu-id="f8cdd-113">Allow employees to securely access Office 365 from an unmanaged public kiosk</span></span>
- <span data-ttu-id="f8cdd-114">On-premises e-mail en gegevens te beschermen, zodat ze veilig kunnen worden gebruikt door mobiele apparaten, omdat er geen on-premises Microsoft Exchange-servers meer zijn.</span><span class="sxs-lookup"><span data-stu-id="f8cdd-114">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no longer on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="f8cdd-115">Implementeren</span><span class="sxs-lookup"><span data-stu-id="f8cdd-115">Deploy</span></span>

<span data-ttu-id="f8cdd-116">Dit is de manier waarop Contoso de infrastructuur voor het beheer van mobiele apparaten heeft ingesteld:</span><span class="sxs-lookup"><span data-stu-id="f8cdd-116">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="f8cdd-117">Intune als MDM-instantie (Mobile Device Management) ingesteld en Intune op Azure om de inhoud en apparaten te beheren</span><span class="sxs-lookup"><span data-stu-id="f8cdd-117">Set Intune as the Mobile Device Management (MDM) authority and are using Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="f8cdd-118">Azure AD-groepen gemaakt voor apparaten voor registratie en Intune-instellingen en beleid voor voorwaardelijke toegang voor apparaten</span><span class="sxs-lookup"><span data-stu-id="f8cdd-118">Created Azure AD groups for devices for enrollment and Intune settings and device-based Conditional Access policies</span></span>

  <span data-ttu-id="f8cdd-119">Zie [Beleid voor voorwaardelijke toegang van Contoso](contoso-identity.md#conditional-access-policies-for-identity-and-device-access) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f8cdd-119">See [Contoso's Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access) for more information.</span></span>

- <span data-ttu-id="f8cdd-120">Het Apple-apparaatplatform ingeschakeld om medewerkers met iPads, iMacs, iPhones te ondersteunen en voor op iPhone-gebaseerde telefoons van Contoso</span><span class="sxs-lookup"><span data-stu-id="f8cdd-120">Enabled the Apple device platform to support employees with iPads, iMacs, iPhones, and for iPhone-based corporate-owned phones</span></span>
- <span data-ttu-id="f8cdd-121">Specifiek Contoso-voorwaardenbeleid gemaakt, dat wordt weergegeven tijdens de installatie van het bedrijfsportaal van Contoso op mobiele apparaten</span><span class="sxs-lookup"><span data-stu-id="f8cdd-121">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="f8cdd-122">Een verzameling MAM-beleid (Mobile Application Management) gemaakt om verificatie te eisen voor toegang tot Office 365-services voor apparaten die niet zijn geregistreerd</span><span class="sxs-lookup"><span data-stu-id="f8cdd-122">For devices that are not enrolled, a set of Mobile Application Management (MAM) policies to require authentication for access to Office 365 services</span></span>
- <span data-ttu-id="f8cdd-123">Intune-beleid gemaakt dat het volgende afdwingt:</span><span class="sxs-lookup"><span data-stu-id="f8cdd-123">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="f8cdd-124">Goedgekeurde apps</span><span class="sxs-lookup"><span data-stu-id="f8cdd-124">Allowed apps</span></span>
  - <span data-ttu-id="f8cdd-125">Apparaatversleuteling om ongeoorloofde toegang te voorkomen</span><span class="sxs-lookup"><span data-stu-id="f8cdd-125">Device encryption to help prevent unauthorized access</span></span>
  - <span data-ttu-id="f8cdd-126">Een pincode of wachtwoord van zes cijfers</span><span class="sxs-lookup"><span data-stu-id="f8cdd-126">A six-digit PIN or password</span></span>
  - <span data-ttu-id="f8cdd-127">Een timeout-periode als niet actief</span><span class="sxs-lookup"><span data-stu-id="f8cdd-127">An inactivity timeout period</span></span>
  - <span data-ttu-id="f8cdd-128">Antivirus- en malwarebescherming en handtekeningupdates met Windows Defender op Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="f8cdd-128">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices</span></span>
  - <span data-ttu-id="f8cdd-129">Automatische updates op Windows 10-apparaten inclusief de nieuwste beveiligingsupdates</span><span class="sxs-lookup"><span data-stu-id="f8cdd-129">Automatic updates on Windows 10 devices that include the latest security updates</span></span>
  - <span data-ttu-id="f8cdd-130">Certificaten pushen naar beheerde apparaten</span><span class="sxs-lookup"><span data-stu-id="f8cdd-130">Pushing certificates to managed devices</span></span>
  - <span data-ttu-id="f8cdd-131">Een duidelijke scheiding tussen bedrijfs- en persoonlijke gegevens. </span><span class="sxs-lookup"><span data-stu-id="f8cdd-131">A clear separation of business and personal data.</span></span> <span data-ttu-id="f8cdd-132">Gebruikers of beheerders kunnen selectief bedrijfsgegevens van het apparaat wissen en persoonlijke gegevens als foto’s, persoonlijke e-mailaccounts en persoonlijke bestanden ongemoeid laten.</span><span class="sxs-lookup"><span data-stu-id="f8cdd-132">Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="f8cdd-133">Na de implementatie registreerde Contoso pc’s en smartphones en tablets van het bedrijf door ze toe te voegen aan de juiste Intune-apparaatgroepen en implementeerde een BYOD-programma voor werknemers, zodat die hun persoonlijke apparaten konden registreren.</span><span class="sxs-lookup"><span data-stu-id="f8cdd-133">Once deployed, Contoso enrolled PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups and rolled out a BYOD program for employees to enroll their personal devices.</span></span> <span data-ttu-id="f8cdd-134">Registreerde apparaten ontvingen Intune-beleid en dat resulteerde in beheerde en beveiligde apparaten en toepassingen.</span><span class="sxs-lookup"><span data-stu-id="f8cdd-134">Enrolled devices received Intune policies, resulting in managed and secured devices and their applications.</span></span> <span data-ttu-id="f8cdd-135">Apparaten die niet zijn geregistreerd hebben MAM-beleid (Mobile Application Management) dat de toegestane toepassingen specificeert.</span><span class="sxs-lookup"><span data-stu-id="f8cdd-135">Devices that are not enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

<span data-ttu-id="f8cdd-136">Hieronder ziet u de implementatie-architectuur voor het beheer van mobiele apparaten van Contoso.</span><span class="sxs-lookup"><span data-stu-id="f8cdd-136">Here is Contoso's mobile device management deployment architecture.</span></span>

![De implementatie-infrastructuur voor het beheer van mobiele apparaten van Contoso](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a><span data-ttu-id="f8cdd-138">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="f8cdd-138">Next step</span></span>

<span data-ttu-id="f8cdd-139">[Meer informatie](contoso-info-protect.md) over hoe Contoso de mogelijkheden voor gegevensbescherming van Microsoft 365 Enterprise gebruikt om belangrijke digitale activa binnen de organisatie te classificeren, te identificeren en te beschermen.</span><span class="sxs-lookup"><span data-stu-id="f8cdd-139">[Learn](contoso-info-protect.md) how Contoso uses the information protection capabilities of Microsoft 365 Enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8cdd-140">Zie ook</span><span class="sxs-lookup"><span data-stu-id="f8cdd-140">See also</span></span>

[<span data-ttu-id="f8cdd-141">Beheer van mobiele apparaten voor Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f8cdd-141">Mobile device management for Microsoft 365 Enterprise</span></span>](mobility-infrastructure.md)

[<span data-ttu-id="f8cdd-142">Implementatiehandleiding</span><span class="sxs-lookup"><span data-stu-id="f8cdd-142">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="f8cdd-143">Testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="f8cdd-143">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

