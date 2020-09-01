---
title: Wegwijzer voor Apparaatbeheer voor Microsoft 365
keywords: Microsoft 365, Microsoft 365 voor Enterprise, Microsoft 365-documentatie, beheer van mobiele apparaten, intune
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 08/10/2020
ms.topic: conceptual
f1.keywords:
- NOCSH
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
description: De routekaart voor het instellen van Apparaatbeheer voor Microsoft 365.
ms.openlocfilehash: 1a1bdb449aa1d1ba12cf1de422b3e279df6c1376
ms.sourcegitcommit: 19515d787246d38c4e0da579a767ce67b9dbc2bc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/31/2020
ms.locfileid: "47315739"
---
# <a name="device-management-roadmap-for-microsoft-365"></a><span data-ttu-id="9bb71-104">Wegwijzer voor Apparaatbeheer voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9bb71-104">Device management roadmap for Microsoft 365</span></span>


<span data-ttu-id="9bb71-105">Microsoft 365 voor Enterprise bevat functies waarmee u apparaten en hun apps binnen uw organisatie kunt beheren.</span><span class="sxs-lookup"><span data-stu-id="9bb71-105">Microsoft 365 for enterprise includes features to help manage devices, and their apps, within your organization.</span></span> <span data-ttu-id="9bb71-106">Door mobiele apparaten te beheren, kunt u de bronnen van uw organisatie beschermen en beschermen.</span><span class="sxs-lookup"><span data-stu-id="9bb71-106">Managing mobile devices helps you secure and protect your organization's resources.</span></span>

<span data-ttu-id="9bb71-107">Er zijn twee opties voor Apparaatbeheer.</span><span class="sxs-lookup"><span data-stu-id="9bb71-107">There are two options for device management.</span></span>

## <a name="microsoft-intune"></a><span data-ttu-id="9bb71-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="9bb71-108">Microsoft Intune</span></span>

<span data-ttu-id="9bb71-109">InTune biedt u opties voor het beheren van de toegang tot uw organisatie met behulp van MDM (Mobile Device Management) of Mobile Application Management (MAM).</span><span class="sxs-lookup"><span data-stu-id="9bb71-109">Intune gives you options to manage access to your organization using Mobile Device Management (MDM) or Mobile Application Management (MAM).</span></span> <span data-ttu-id="9bb71-110">MDM is wanneer gebruikers de optie hun apparaat registreren in intune.</span><span class="sxs-lookup"><span data-stu-id="9bb71-110">MDM is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="9bb71-111">Nadat u zich hebt geregistreerd, zijn ze beheerde apparaten en kunnen er beleidsregels, regels en instellingen worden ontvangen die door uw organisatie worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="9bb71-111">Once enrolled, they are managed devices, and can receive any policies, rules, and settings used by your organization.</span></span> <span data-ttu-id="9bb71-112">U kunt bijvoorbeeld bepaalde apps installeren, een wachtwoordbeleid maken, een VPN-verbinding installeren en nog veel meer.</span><span class="sxs-lookup"><span data-stu-id="9bb71-112">For example, you can install specifics apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="9bb71-113">Gebruikers met hun eigen persoonlijke apparaten willen hun apparaten mogelijk niet registreren of worden beheerd door intune en uw beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="9bb71-113">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your policies.</span></span> <span data-ttu-id="9bb71-114">U moet de bronnen en gegevens van uw organisatie nog altijd beschermen.</span><span class="sxs-lookup"><span data-stu-id="9bb71-114">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="9bb71-115">In dit scenario kunt u uw apps beschermen met behulp van MAM.</span><span class="sxs-lookup"><span data-stu-id="9bb71-115">In this scenario, you can protect your apps using MAM.</span></span> <span data-ttu-id="9bb71-116">U kunt bijvoorbeeld een MAM-beleid gebruiken waarbij een gebruiker een pincode moet invoeren bij het openen van SharePoint op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="9bb71-116">For example, you can use a MAM policy that requires a user to enter a PIN when accessing SharePoint on the device.</span></span>

<span data-ttu-id="9bb71-117">U kunt ook bepalen hoe u eigen apparaten met persoonlijke of organisatie-eigenaar gaat beheren.</span><span class="sxs-lookup"><span data-stu-id="9bb71-117">You'll also determine how you're going to manage personal or organization-owned devices.</span></span> <span data-ttu-id="9bb71-118">U kunt apparaten anders behandelen, afhankelijk van het gebruik.</span><span class="sxs-lookup"><span data-stu-id="9bb71-118">You may want to treat devices differently, depending on their use.</span></span> 

<span data-ttu-id="9bb71-119">Begin [hier](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide).</span><span class="sxs-lookup"><span data-stu-id="9bb71-119">Start [here](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide).</span></span>

## <a name="basic-mobility-and-security"></a><span data-ttu-id="9bb71-120">Basis mobiliteit en beveiliging</span><span class="sxs-lookup"><span data-stu-id="9bb71-120">Basic Mobility and Security</span></span>
 
<span data-ttu-id="9bb71-121">Dit is ingebouwd in Microsoft 365 en helpt u bij het beveiligen en beheren van mobiele apparaten van gebruikers, zoals iPhones, iPads, Android-en Windows phones.</span><span class="sxs-lookup"><span data-stu-id="9bb71-121">This is built into Microsoft 365 and helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="9bb71-122">U kunt beveiligingsbeleid voor apparaten maken en beheren, een apparaat op afstand wissen en gedetailleerde apparaatprofielen weergeven.</span><span class="sxs-lookup"><span data-stu-id="9bb71-122">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span> 

<span data-ttu-id="9bb71-123">Begin [hier](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd).</span><span class="sxs-lookup"><span data-stu-id="9bb71-123">Start [here](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd).</span></span>
 
## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="9bb71-124">Aanbevelingen voor identiteiten en apparaattoegang</span><span class="sxs-lookup"><span data-stu-id="9bb71-124">Identity and device access recommendations</span></span>

<span data-ttu-id="9bb71-125">Microsoft biedt een aantal aanbevelingen voor [identiteits- en apparaattoegang](microsoft-365-policies-configurations.md) om te zorgen dat uw personeel veilig en productief blijft.</span><span class="sxs-lookup"><span data-stu-id="9bb71-125">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="9bb71-126">Gebruik voor toegang tot apparaten de aanbevelingen en instellingen in deze artikelen:</span><span class="sxs-lookup"><span data-stu-id="9bb71-126">For device access, use the recommendations and settings in these articles:</span></span>

- [<span data-ttu-id="9bb71-127">Vereisten</span><span class="sxs-lookup"><span data-stu-id="9bb71-127">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="9bb71-128">Algemeen beleid voor identiteiten en apparaattoegang</span><span class="sxs-lookup"><span data-stu-id="9bb71-128">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a><span data-ttu-id="9bb71-129">Hoe contoso Apparaatbeheer voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9bb71-129">How Contoso did device management for Microsoft 365</span></span>

<span data-ttu-id="9bb71-130">Bekijk de manier waarop Contoso Corporation, een fictief maar representatief Business-Business, [de infrastructuur voor mobiel Apparaatbeheer](contoso-mdm.md) en de cloudservices van microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9bb71-130">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed their mobile device management infrastructure](contoso-mdm.md) with Microsoft 365 cloud services.</span></span>
