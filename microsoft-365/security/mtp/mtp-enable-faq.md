---
title: Veelgestelde vragen over het inschakelen van Microsoft Threat Protection
description: Hier vindt u antwoorden op de meest gestelde vragen over licenties, machtigingen, initiële instellingen en andere producten en services met betrekking tot het inschakelen van Microsoft Threat Protection
keywords: Veelgestelde vragen, veelgestelde vragen, GCC, aan de slag, MTP inschakelen, Microsoft Threat Protection, M365, beveiliging, gegevenslocatie, vereiste machtigingen, licentie komt, pagina instellingen
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 6b0d8d9be0cc84e61a3228f79fc14f1bfc9f8a83
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198837"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-threat-protection"></a><span data-ttu-id="07076-104">Veelgestelde vragen over het inschakelen van Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="07076-104">Frequently asked questions when turning on Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="07076-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="07076-105">**Applies to:**</span></span>
- <span data-ttu-id="07076-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="07076-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="07076-107">Lees de antwoorden op de meest gestelde vragen over het inschakelen van [Microsoft Threat Protection](microsoft-threat-protection.md), waaronder vereiste licenties en machtigingen, het implementeren van ondersteuningsservices en de eerste instellingen.</span><span class="sxs-lookup"><span data-stu-id="07076-107">Read responses to the most commonly asked questions about turning on [Microsoft Threat Protection](microsoft-threat-protection.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="07076-108">[Zie Microsoft Threat Protection inschakelen](mtp-enable.md)voor instructies over het inschakelen van de service.</span><span class="sxs-lookup"><span data-stu-id="07076-108">For instructions on how to turn on the service, [read Turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-threat-protection"></a><span data-ttu-id="07076-109">Ik heb geen Microsoft 365 E5-licentie.</span><span class="sxs-lookup"><span data-stu-id="07076-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="07076-110">Kan ik nog steeds Microsoft Threat Protection gebruiken?</span><span class="sxs-lookup"><span data-stu-id="07076-110">Can I still use Microsoft Threat Protection?</span></span>

<span data-ttu-id="07076-111">Klanten met de volgende non-E5-licenties kunnen Microsoft Threat Protection gebruiken:</span><span class="sxs-lookup"><span data-stu-id="07076-111">Customers with the following non-E5 licenses can use Microsoft Threat Protection:</span></span>

- <span data-ttu-id="07076-112">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="07076-112">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="07076-113">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="07076-113">Azure Advanced Threat Protection</span></span>
- <span data-ttu-id="07076-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="07076-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="07076-115">Office 365 Advanced Threat Protection (abonnement 2)</span><span class="sxs-lookup"><span data-stu-id="07076-115">Office 365 Advanced Threat Protection (Plan 2)</span></span>
 
<span data-ttu-id="07076-116">Voor een volledige lijst met ondersteunde licenties [raadpleegt u de licentievereisten](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="07076-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-threat-protection"></a><span data-ttu-id="07076-117">Moet ik alles installeren of implementeren om Microsoft Threat Protection te kunnen gebruiken?</span><span class="sxs-lookup"><span data-stu-id="07076-117">Do I need to install or deploy anything to start using Microsoft Threat Protection?</span></span>

<span data-ttu-id="07076-118">Nee, Microsoft Threat Protection kan gegevens van Microsoft 365-beveiligingsservices die u al hebt geïmplementeerd, samenvoegen.</span><span class="sxs-lookup"><span data-stu-id="07076-118">No, Microsoft Threat Protection consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="07076-119">Wanneer u de functie hebt ingeschakeld, kunnen incident-, automatiserings-en jacht-ervaringen werken binnen het bereik van de gedistribueerde producten.</span><span class="sxs-lookup"><span data-stu-id="07076-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="07076-120">Als geen van deze producten op de juiste manier is geïmplementeerd, worden geen gegevens in Microsoft Threat Protection weergegeven en kan geen actie ondernemen.</span><span class="sxs-lookup"><span data-stu-id="07076-120">If none of these products are properly deployed, Microsoft Threat Protection will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="07076-121">Om uw ervaringen met Microsoft Threat Protection te optimaliseren, wordt u aangeraden *alle* ondersteunde [Microsoft 365-beveiligingsproducten en-services](deploy-supported-services.md)te implementeren.</span><span class="sxs-lookup"><span data-stu-id="07076-121">To optimize your Microsoft Threat Protection experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-threat-protection-process-and-store-my-data"></a><span data-ttu-id="07076-122">Waar kan ik Microsoft Threat Protection processen en mijn gegevens opslaan?</span><span class="sxs-lookup"><span data-stu-id="07076-122">Where does Microsoft Threat Protection process and store my data?</span></span>
<span data-ttu-id="07076-123">Microsoft Threat Protection selecteert automatisch een optimale locatie voor het datacenter waar geconsolideerde gegevens worden verwerkt en opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="07076-123">Microsoft Threat Protection automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="07076-124">Als u Microsoft Defender ATP hebt, wordt de locatie geselecteerd die wordt gebruikt in Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="07076-124">If you have Microsoft Defender ATP, it selects the same location used by Microsoft Defender ATP.</span></span>

>[!NOTE]
><span data-ttu-id="07076-125">In Microsoft Defender ATP worden automatisch de voorzieningen van de Europese Unie (EU)-datacenters automatisch ingericht wanneer ze zijn ingeschakeld via Azure Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="07076-125">Microsoft Defender ATP automatically provisions in European Union (EU) data centers when turned on through Azure Security Center.</span></span> <span data-ttu-id="07076-126">Microsoft Threat Protection wordt automatisch ingericht in hetzelfde EU-datacenter voor klanten die op deze manier Microsoft Defender ATP hebben ingericht.</span><span class="sxs-lookup"><span data-stu-id="07076-126">Microsoft Threat Protection will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender ATP in this manner.</span></span> 

<span data-ttu-id="07076-127">De locatie van het datacenter wordt weergegeven vóór en na het inrichten van de service op de pagina instellingen voor Microsoft Threat Protection (**instellingen > Microsoft Threat Protection**).</span><span class="sxs-lookup"><span data-stu-id="07076-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft Threat Protection (**Settings > Microsoft Threat Protection**).</span></span> <span data-ttu-id="07076-128">Als u liever een andere locatie voor het datacenter wilt gebruiken, selecteert u **hulp nodig?** in het microsoft 365-Beveiligingscentrum voor contact opnemen met Microsoft ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="07076-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-threat-protection"></a><span data-ttu-id="07076-129">Waar kan ik Microsoft Threat Protection openen?</span><span class="sxs-lookup"><span data-stu-id="07076-129">Where can I access Microsoft Threat Protection?</span></span>

<span data-ttu-id="07076-130">Microsoft Threat Protection is beschikbaar in het Beveiligingscentrum van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="07076-130">Microsoft Threat Protection is available in Microsoft 365 security center.</span></span> <span data-ttu-id="07076-131">Blader naar de URL om naar het Beveiligingscentrum te gaan [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="07076-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-threat-protection-in-microsoft-365-security-center"></a><span data-ttu-id="07076-132">Welke machtigingen heb ik nodig voor het openen van Microsoft Threat Protection in Microsoft 365 Beveiligingscentrum?</span><span class="sxs-lookup"><span data-stu-id="07076-132">What permissions do I need to access Microsoft Threat Protection in Microsoft 365 security center?</span></span>

<span data-ttu-id="07076-133">Accounts die zijn toegewezen aan de volgende Azure Active Directory (AD) rollen hebben toegang tot de functies en gegevens van Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="07076-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft Threat Protection functionality and data:</span></span>

- <span data-ttu-id="07076-134">Globale beheerder</span><span class="sxs-lookup"><span data-stu-id="07076-134">Global administrator</span></span>
- <span data-ttu-id="07076-135">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="07076-135">Security administrator</span></span>
- <span data-ttu-id="07076-136">Beveiligings operator</span><span class="sxs-lookup"><span data-stu-id="07076-136">Security Operator</span></span>
- <span data-ttu-id="07076-137">Algemene lezer</span><span class="sxs-lookup"><span data-stu-id="07076-137">Global Reader</span></span>
- <span data-ttu-id="07076-138">Beveiligings lezer</span><span class="sxs-lookup"><span data-stu-id="07076-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="07076-139">De instellingen voor toegangsbeheer op basis van rollen in Microsoft Defender ATP beïnvloeden de toegang tot gegevens.</span><span class="sxs-lookup"><span data-stu-id="07076-139">Role-based access control settings in Microsoft Defender ATP influence access to data.</span></span> <span data-ttu-id="07076-140">Lees voor meer informatie over [het beheren van de toegang tot Microsoft Threat Protection](mtp-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="07076-140">For more information, read about [managing access to Microsoft Threat Protection](mtp-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-threat-protection-default-to"></a><span data-ttu-id="07076-141">Voor welke tijdzone is Microsoft Threat Protection standaard?</span><span class="sxs-lookup"><span data-stu-id="07076-141">What time zone does Microsoft Threat Protection default to?</span></span>
<span data-ttu-id="07076-142">Standaard worden in Microsoft Bedreigingsbeveiliging tijds informatie weergegeven in de UTC-tijdzone.</span><span class="sxs-lookup"><span data-stu-id="07076-142">By default, Microsoft Threat Protection displays time information in the UTC time zone.</span></span> <span data-ttu-id="07076-143">U kunt deze instelling wijzigen om uw lokale tijdzone te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="07076-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="07076-144">Meer informatie over het instellen van de tijdzone</span><span class="sxs-lookup"><span data-stu-id="07076-144">Learn about setting the time zone</span></span>](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-threat-protection-feature-and-ui-updates"></a><span data-ttu-id="07076-145">Hoe kan ik meer te weten komen over de nieuwe functies en UI-updates voor Microsoft Threat Protection?</span><span class="sxs-lookup"><span data-stu-id="07076-145">How can I learn about new Microsoft Threat Protection feature and UI updates?</span></span>

<span data-ttu-id="07076-146">Microsoft biedt regelmatig informatie over de verschillende kanalen, waaronder:</span><span class="sxs-lookup"><span data-stu-id="07076-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="07076-147">Het [berichtencentrum](../../admin/manage/message-center.md) in het microsoft 365-Beheercentrum</span><span class="sxs-lookup"><span data-stu-id="07076-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="07076-148">Blogposts in de [Microsoft 365-beveiligings & compliance tech Community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="07076-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="07076-149">U krijgt de nieuwste, algemeen beschikbare [functies door Voorbeeldfuncties](preview.md)in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="07076-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="07076-150">Is Microsoft Threat Protection beschikbaar voor US Government Community Cloud (GCC) of GCC High?</span><span class="sxs-lookup"><span data-stu-id="07076-150">Is Microsoft Threat Protection available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="07076-151">Dit is momenteel niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="07076-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="07076-152">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="07076-152">Related topics</span></span>

- [<span data-ttu-id="07076-153">Overzicht van Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="07076-153">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- <span data-ttu-id="07076-154">[Schakel Microsoft Threat Protection in](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="07076-154">[Turn on Microsoft Threat Protection](mtp-enable.md).</span></span>
- [<span data-ttu-id="07076-155">Licentievereisten en andere vereisten</span><span class="sxs-lookup"><span data-stu-id="07076-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="07076-156">Ondersteunde services implementeren</span><span class="sxs-lookup"><span data-stu-id="07076-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="07076-157">Voorbeeldfuncties inschakelen</span><span class="sxs-lookup"><span data-stu-id="07076-157">Turn on preview features</span></span>](preview.md)
