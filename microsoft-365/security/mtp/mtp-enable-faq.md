---
title: Veelgestelde vragen bij het inschakelen van Microsoft Threat Protection
description: Antwoorden krijgen op de meest gestelde vragen over licenties, machtigingen, initiële instellingen en andere producten en services met betrekking tot het inschakelen van Microsoft Threat Protection
keywords: veelgestelde vragen, FAQ, GCC, aan de slag, inschakelen MTP, Microsoft Threat Protection, M365, beveiliging, gegevens locatie, vereiste machtigingen, licentie geschiktheid, instellingen pagina
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
ms.openlocfilehash: 9dcfeb5616afc8953e862d6d1a542d694582b157
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2020
ms.locfileid: "44845062"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-threat-protection"></a><span data-ttu-id="69131-104">Veelgestelde vragen bij het inschakelen van Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="69131-104">Frequently asked questions when turning on Microsoft Threat Protection</span></span>

<span data-ttu-id="69131-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="69131-105">**Applies to:**</span></span>
- <span data-ttu-id="69131-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="69131-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="69131-107">Lees antwoorden op de meest gestelde vragen over het inschakelen van [Microsoft Threat Protection](microsoft-threat-protection.md), inclusief vereiste licenties en machtigingen, het implementeren van ondersteuningsservices en de eerste instellingen.</span><span class="sxs-lookup"><span data-stu-id="69131-107">Read responses to the most commonly asked questions about turning on [Microsoft Threat Protection](microsoft-threat-protection.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="69131-108">[Lees Microsoft Threat Protection inschakelen](mtp-enable.md)voor instructies voor het inschakelen van de service.</span><span class="sxs-lookup"><span data-stu-id="69131-108">For instructions on how to turn on the service, [read Turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-threat-protection"></a><span data-ttu-id="69131-109">Ik heb geen Microsoft 365 E5 licentie.</span><span class="sxs-lookup"><span data-stu-id="69131-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="69131-110">Kan ik nog steeds Microsoft Threat Protection gebruiken?</span><span class="sxs-lookup"><span data-stu-id="69131-110">Can I still use Microsoft Threat Protection?</span></span>

<span data-ttu-id="69131-111">Klanten met de volgende niet-E5-licenties kunnen Microsoft Threat Protection gebruiken:</span><span class="sxs-lookup"><span data-stu-id="69131-111">Customers with the following non-E5 licenses can use Microsoft Threat Protection:</span></span>

- <span data-ttu-id="69131-112">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="69131-112">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="69131-113">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="69131-113">Azure Advanced Threat Protection</span></span>
- <span data-ttu-id="69131-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="69131-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="69131-115">Geavanceerde bedreigingsbeveiliging van Office 365 (abonnement 2)</span><span class="sxs-lookup"><span data-stu-id="69131-115">Office 365 Advanced Threat Protection (Plan 2)</span></span>
 
<span data-ttu-id="69131-116">[Lees de licentievereisten](prerequisites.md#licensing-requirements)voor een volledige lijst met ondersteunde licenties.</span><span class="sxs-lookup"><span data-stu-id="69131-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-threat-protection"></a><span data-ttu-id="69131-117">Moet ik iets installeren of implementeren om Microsoft Threat Protection te kunnen gebruiken?</span><span class="sxs-lookup"><span data-stu-id="69131-117">Do I need to install or deploy anything to start using Microsoft Threat Protection?</span></span>

<span data-ttu-id="69131-118">Nee, Microsoft Threat Protection consolideert gegevens van Microsoft 365-beveiligingsservices die u al hebt geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="69131-118">No, Microsoft Threat Protection consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="69131-119">Zodra u het inschakelt, zullen incident-, automatiserings- en jachtervaringen gaan werken binnen het bereik van de geïmplementeerde producten.</span><span class="sxs-lookup"><span data-stu-id="69131-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="69131-120">Als geen van deze producten correct is geïmplementeerd, geeft Microsoft Threat Protection geen gegevens weer en kan er geen actie worden ondernomen.</span><span class="sxs-lookup"><span data-stu-id="69131-120">If none of these products are properly deployed, Microsoft Threat Protection will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="69131-121">Om uw Microsoft Threat Protection-ervaringen te optimaliseren, raden we u aan *alle* ondersteunde [Microsoft 365-beveiligingsproducten en -services](deploy-supported-services.md)te implementeren.</span><span class="sxs-lookup"><span data-stu-id="69131-121">To optimize your Microsoft Threat Protection experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-threat-protection-process-and-store-my-data"></a><span data-ttu-id="69131-122">Waar verwerkt en slaat Microsoft Threat Protection mijn gegevens op?</span><span class="sxs-lookup"><span data-stu-id="69131-122">Where does Microsoft Threat Protection process and store my data?</span></span>
<span data-ttu-id="69131-123">Microsoft Threat Protection selecteert automatisch een optimale locatie voor het datacenter waar geconsolideerde gegevens worden verwerkt en opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="69131-123">Microsoft Threat Protection automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="69131-124">Als u Microsoft Defender ATP hebt, selecteert u dezelfde locatie die wordt gebruikt door Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="69131-124">If you have Microsoft Defender ATP, it selects the same location used by Microsoft Defender ATP.</span></span>

>[!NOTE]
><span data-ttu-id="69131-125">Microsoft Defender ATP-bepalingen in datacenters van de Europese Unie (EU) automatisch worden ingeschakeld via Azure Security Center.</span><span class="sxs-lookup"><span data-stu-id="69131-125">Microsoft Defender ATP automatically provisions in European Union (EU) data centers when turned on through Azure Security Center.</span></span> <span data-ttu-id="69131-126">Microsoft Threat Protection voorziet automatisch in hetzelfde EU-datacenter voor klanten die Microsoft Defender ATP op deze manier hebben ingericht.</span><span class="sxs-lookup"><span data-stu-id="69131-126">Microsoft Threat Protection will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender ATP in this manner.</span></span> 

<span data-ttu-id="69131-127">De locatie van het datacenter wordt voor en na de service weergegeven op de instellingenpagina voor Microsoft Threat Protection **(Instellingen > Microsoft Threat Protection**).</span><span class="sxs-lookup"><span data-stu-id="69131-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft Threat Protection (**Settings > Microsoft Threat Protection**).</span></span> <span data-ttu-id="69131-128">Als u liever een andere locatie van het datacenter gebruikt, selecteert u **Hulp nodig?**</span><span class="sxs-lookup"><span data-stu-id="69131-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-threat-protection"></a><span data-ttu-id="69131-129">Waar heb ik toegang tot Microsoft Threat Protection?</span><span class="sxs-lookup"><span data-stu-id="69131-129">Where can I access Microsoft Threat Protection?</span></span>

<span data-ttu-id="69131-130">Microsoft Threat Protection is beschikbaar in het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="69131-130">Microsoft Threat Protection is available in Microsoft 365 security center.</span></span> <span data-ttu-id="69131-131">Als u naar het beveiligingscentrum wilt gaan, bladert u naar de URL [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="69131-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-threat-protection-in-microsoft-365-security-center"></a><span data-ttu-id="69131-132">Welke machtigingen heb ik nodig om toegang te krijgen tot Microsoft Threat Protection in het Microsoft 365-beveiligingscentrum?</span><span class="sxs-lookup"><span data-stu-id="69131-132">What permissions do I need to access Microsoft Threat Protection in Microsoft 365 security center?</span></span>

<span data-ttu-id="69131-133">Accounts die de volgende Azure Active Directory(AD)-rollen hebben toegewezen, hebben toegang tot de functionaliteit en gegevens van Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="69131-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft Threat Protection functionality and data:</span></span>

- <span data-ttu-id="69131-134">Globale beheerder</span><span class="sxs-lookup"><span data-stu-id="69131-134">Global administrator</span></span>
- <span data-ttu-id="69131-135">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="69131-135">Security administrator</span></span>
- <span data-ttu-id="69131-136">Beveiligingsoperator</span><span class="sxs-lookup"><span data-stu-id="69131-136">Security Operator</span></span>
- <span data-ttu-id="69131-137">Global Reader</span><span class="sxs-lookup"><span data-stu-id="69131-137">Global Reader</span></span>
- <span data-ttu-id="69131-138">Beveiligingslezer</span><span class="sxs-lookup"><span data-stu-id="69131-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="69131-139">Op rollen gebaseerde toegangscontrole-instellingen in Microsoft Defender ATP beïnvloeden de toegang tot gegevens.</span><span class="sxs-lookup"><span data-stu-id="69131-139">Role-based access control settings in Microsoft Defender ATP influence access to data.</span></span> <span data-ttu-id="69131-140">Lees voor meer informatie over [het beheren van de toegang tot Microsoft Threat Protection.](mtp-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="69131-140">For more information, read about [managing access to Microsoft Threat Protection](mtp-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-threat-protection-default-to"></a><span data-ttu-id="69131-141">Tot welke tijdzone wordt Microsoft Threat Protection standaard gebruikt?</span><span class="sxs-lookup"><span data-stu-id="69131-141">What time zone does Microsoft Threat Protection default to?</span></span>
<span data-ttu-id="69131-142">Microsoft Threat Protection geeft standaard tijdsinformatie weer in de UTC-tijdzone.</span><span class="sxs-lookup"><span data-stu-id="69131-142">By default, Microsoft Threat Protection displays time information in the UTC time zone.</span></span> <span data-ttu-id="69131-143">U deze instelling wijzigen om uw lokale tijdzone te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="69131-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="69131-144">Meer informatie over het instellen van de tijdzone</span><span class="sxs-lookup"><span data-stu-id="69131-144">Learn about setting the time zone</span></span>](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-threat-protection-feature-and-ui-updates"></a><span data-ttu-id="69131-145">Hoe kom ik meer te weten over de nieuwe Microsoft Threat Protection-functie en UI-updates?</span><span class="sxs-lookup"><span data-stu-id="69131-145">How can I learn about new Microsoft Threat Protection feature and UI updates?</span></span>

<span data-ttu-id="69131-146">Microsoft verstrekt regelmatig informatie via de verschillende kanalen, waaronder:</span><span class="sxs-lookup"><span data-stu-id="69131-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="69131-147">Het [berichtencentrum](../../admin/manage/message-center.md) in het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="69131-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="69131-148">Blogposts in de [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="69131-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="69131-149">Ontvang de nieuwste openbaar beschikbare ervaringen door [preview-functies](preview.md)in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="69131-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="69131-150">Is Microsoft Threat Protection beschikbaar voor GCC of GCC High van de Amerikaanse overheid?</span><span class="sxs-lookup"><span data-stu-id="69131-150">Is Microsoft Threat Protection available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="69131-151">Op dit moment is het niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="69131-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="69131-152">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="69131-152">Related topics</span></span>

- [<span data-ttu-id="69131-153">Overzicht van Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="69131-153">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- <span data-ttu-id="69131-154">[Schakel Microsoft Threat Protection in](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="69131-154">[Turn on Microsoft Threat Protection](mtp-enable.md).</span></span>
- [<span data-ttu-id="69131-155">Licentievereisten en andere voorwaarden</span><span class="sxs-lookup"><span data-stu-id="69131-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="69131-156">Ondersteunde services implementeren</span><span class="sxs-lookup"><span data-stu-id="69131-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="69131-157">Voorbeeldfuncties inschakelen</span><span class="sxs-lookup"><span data-stu-id="69131-157">Turn on preview features</span></span>](preview.md)