---
title: Veelgestelde vragen bij het inschakelen van Microsoft 365 Defender
description: Krijg antwoord op de meest gestelde vragen over licenties, machtigingen, initiële instellingen en andere producten en services met betrekking tot het inschakelen van Microsoft 365 Defender
keywords: veelgestelde vragen, VEELGESTELDE VRAGEN, GCC, aan de slag, Microsoft 365 Defender inschakelen, Microsoft 365 Defender, M365, beveiliging, gegevenslocatie, vereiste machtigingen, geschiktheid voor licenties, instellingenpagina
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 008e3cc6ee65597a032aa932b74a64ac591927f2
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572763"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="fdf14-104">Veelgestelde vragen bij het inschakelen van Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fdf14-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fdf14-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="fdf14-105">**Applies to:**</span></span>
- <span data-ttu-id="fdf14-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fdf14-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="fdf14-107">Lees antwoorden op de meest gestelde vragen over het inschakelen [van Microsoft 365 Defender,](microsoft-365-defender.md)inclusief vereiste licenties en machtigingen, het implementeren van ondersteuningsservices en initiële instellingen.</span><span class="sxs-lookup"><span data-stu-id="fdf14-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-365-defender.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="fdf14-108">[Lees Microsoft 365 Defender inschakelen](m365d-enable.md)voor instructies over het inschakelen van de service.</span><span class="sxs-lookup"><span data-stu-id="fdf14-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="fdf14-109">Ik heb geen Microsoft 365 E5 rijbewijs.</span><span class="sxs-lookup"><span data-stu-id="fdf14-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="fdf14-110">Kan ik Microsoft 365 Defender nog gebruiken?</span><span class="sxs-lookup"><span data-stu-id="fdf14-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="fdf14-111">Klanten met de volgende niet-E5-licenties kunnen Microsoft 365 Defender gebruiken:</span><span class="sxs-lookup"><span data-stu-id="fdf14-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="fdf14-112">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="fdf14-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="fdf14-113">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="fdf14-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="fdf14-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="fdf14-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="fdf14-115">Verdediger voor Office 365 (Plan 2)</span><span class="sxs-lookup"><span data-stu-id="fdf14-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="fdf14-116">[Lees de licentievereisten](prerequisites.md#licensing-requirements)voor een volledige lijst met ondersteunde licenties.</span><span class="sxs-lookup"><span data-stu-id="fdf14-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="fdf14-117">Moet ik iets installeren of implementeren om Microsoft 365 Defender te kunnen gebruiken?</span><span class="sxs-lookup"><span data-stu-id="fdf14-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="fdf14-118">Nee, Microsoft 365 Defender consolideert gegevens van Microsoft 365 beveiligingsservices die u al hebt geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="fdf14-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="fdf14-119">Zodra u het inschakelt, beginnen incident-, automatiserings- en jachtervaringen te werken binnen het bereik van de geïmplementeerde producten.</span><span class="sxs-lookup"><span data-stu-id="fdf14-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="fdf14-120">Als geen van deze producten correct is geïmplementeerd, geeft Microsoft 365 Defender geen gegevens weer en kan deze geen actie ondernemen.</span><span class="sxs-lookup"><span data-stu-id="fdf14-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="fdf14-121">Om uw Microsoft 365 Defender-ervaringen te optimaliseren, raden we u aan *alle* ondersteunde [Microsoft 365 beveiligingsproducten en -services](deploy-supported-services.md)te implementeren.</span><span class="sxs-lookup"><span data-stu-id="fdf14-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="fdf14-122">Waar verwerkt en bewaart Microsoft 365 Defender mijn gegevens?</span><span class="sxs-lookup"><span data-stu-id="fdf14-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="fdf14-123">Microsoft 365 Defender selecteert automatisch een optimale locatie voor het datacenter waar geconsolideerde gegevens worden verwerkt en opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="fdf14-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="fdf14-124">Als u Microsoft Defender voor Eindpunt hebt, wordt dezelfde locatie geselecteerd die door Defender voor Eindpunt wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="fdf14-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="fdf14-125">Microsoft Defender for Endpoint voorziet automatisch in datacenters van de Europese Unie (EU) wanneer deze zijn ingeschakeld via Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="fdf14-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="fdf14-126">Microsoft 365 Defender wordt automatisch in hetzelfde EU-datacenter ingericht voor klanten die Microsoft Defender op deze manier hebben ingericht voor Endpoint.</span><span class="sxs-lookup"><span data-stu-id="fdf14-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="fdf14-127">De locatie van het datacenter wordt weergegeven voor en nadat de service is ingericht op de instellingenpagina voor Microsoft 365 Defender (**Instellingen > Microsoft 365 Defender**).</span><span class="sxs-lookup"><span data-stu-id="fdf14-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender (**Settings > Microsoft 365 Defender**).</span></span> <span data-ttu-id="fdf14-128">Als u liever een andere datacenterlocatie gebruikt, selecteert u **Hulp nodig?** in het beveiligingscentrum Microsoft 365 om contact op te nemen met Microsoft-ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="fdf14-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="fdf14-129">Waar kan ik Microsoft 365 Defender bereiken?</span><span class="sxs-lookup"><span data-stu-id="fdf14-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="fdf14-130">Microsoft 365 Defender is beschikbaar in Microsoft 365 beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="fdf14-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="fdf14-131">Als u naar het beveiligingscentrum wilt gaan, bladert u naar de URL [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="fdf14-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="fdf14-132">Welke machtigingen heb ik nodig om toegang te krijgen tot Microsoft 365 Defender in Microsoft 365 beveiligingscentrum?</span><span class="sxs-lookup"><span data-stu-id="fdf14-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="fdf14-133">Accounts waaraan de volgende azure AD-rollen (Azure Active Directory) zijn toegewezen, hebben toegang tot Microsoft 365 Defender-functionaliteit en -gegevens:</span><span class="sxs-lookup"><span data-stu-id="fdf14-133">Accounts assigned the following Azure Active Directory (Azure AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="fdf14-134">Globale beheerder</span><span class="sxs-lookup"><span data-stu-id="fdf14-134">Global administrator</span></span>
- <span data-ttu-id="fdf14-135">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="fdf14-135">Security administrator</span></span>
- <span data-ttu-id="fdf14-136">Beveiligingsoperator</span><span class="sxs-lookup"><span data-stu-id="fdf14-136">Security Operator</span></span>
- <span data-ttu-id="fdf14-137">Algemene lezer</span><span class="sxs-lookup"><span data-stu-id="fdf14-137">Global Reader</span></span>
- <span data-ttu-id="fdf14-138">Beveiligingslezer</span><span class="sxs-lookup"><span data-stu-id="fdf14-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="fdf14-139">Op rollen gebaseerde instellingen voor toegangsbeheer in Microsoft Defender voor eindpunt hebben invloed op de toegang tot gegevens.</span><span class="sxs-lookup"><span data-stu-id="fdf14-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="fdf14-140">Lees meer over [het beheren van de toegang tot Microsoft 365 Defender](m365d-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="fdf14-140">For more information, read about [managing access to Microsoft 365 Defender](m365d-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="fdf14-141">In welke tijdzone wordt Microsoft 365 Defender standaard ingesteld?</span><span class="sxs-lookup"><span data-stu-id="fdf14-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="fdf14-142">Standaard geeft Microsoft 365 Defender tijdgegevens weer in de tijdzone UTC.</span><span class="sxs-lookup"><span data-stu-id="fdf14-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="fdf14-143">U kunt deze instelling wijzigen om uw lokale tijdzone te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="fdf14-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="fdf14-144">Meer informatie over het instellen van de tijdzone</span><span class="sxs-lookup"><span data-stu-id="fdf14-144">Learn about setting the time zone</span></span>](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="fdf14-145">Hoe kan ik meer te weten komen over nieuwe Microsoft 365 Defender-functie en UI-updates?</span><span class="sxs-lookup"><span data-stu-id="fdf14-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="fdf14-146">Microsoft verstrekt regelmatig informatie via de verschillende kanalen, waaronder:</span><span class="sxs-lookup"><span data-stu-id="fdf14-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="fdf14-147">Het [berichtencentrum](../../admin/manage/message-center.md) in Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="fdf14-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="fdf14-148">Blogposts in de [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="fdf14-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="fdf14-149">Krijg de nieuwste openbaar beschikbare ervaringen door [preview-functies](preview.md)in te schakelen .</span><span class="sxs-lookup"><span data-stu-id="fdf14-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="fdf14-150">Is Microsoft 365 Defender beschikbaar voor Amerikaanse Government Community Cloud (GCC) of GCC High?</span><span class="sxs-lookup"><span data-stu-id="fdf14-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="fdf14-151">Op dit moment is het niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="fdf14-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fdf14-152">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="fdf14-152">Related topics</span></span>

- [<span data-ttu-id="fdf14-153">Microsoft 365 Defender overzicht</span><span class="sxs-lookup"><span data-stu-id="fdf14-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- <span data-ttu-id="fdf14-154">[Schakel Microsoft 365 Defender in.](m365d-enable.md)</span><span class="sxs-lookup"><span data-stu-id="fdf14-154">[Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>
- [<span data-ttu-id="fdf14-155">Licentievereisten en andere vereisten</span><span class="sxs-lookup"><span data-stu-id="fdf14-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="fdf14-156">Ondersteunde services implementeren</span><span class="sxs-lookup"><span data-stu-id="fdf14-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="fdf14-157">Preview-functies inschakelen</span><span class="sxs-lookup"><span data-stu-id="fdf14-157">Turn on preview features</span></span>](preview.md)
