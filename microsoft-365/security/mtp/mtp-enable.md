---
title: Microsoft Threat Protection inschakelen in het Microsoft 365-Beveiligingscentrum
description: Meer informatie over het inschakelen van Microsoft Threat Protection en het integreren van uw beveiligingsincident en-antwoord.
keywords: aan de slag, MTP, Microsoft Threat Protection, M365, beveiliging, gegevenslocatie, vereiste machtigingen, licentie komt, pagina instellingen weergeven
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
ms.openlocfilehash: 65e3a2609bc41ddeda95134874e5873e184a2a54
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201157"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="d8171-104">Microsoft Threat Protection inschakelen</span><span class="sxs-lookup"><span data-stu-id="d8171-104">Turn on Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d8171-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="d8171-105">**Applies to:**</span></span>
- <span data-ttu-id="d8171-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d8171-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="d8171-107">[Microsoft Threat Protection](microsoft-threat-protection.md) bundelt uw incident-antwoord proces door de belangrijkste functies in Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud app Security en Azure ATP te integreren.</span><span class="sxs-lookup"><span data-stu-id="d8171-107">[Microsoft Threat Protection](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="d8171-108">Deze geïntegreerde ervaring voegt krachtige functies toe die u kunt gebruiken in het Microsoft 365-Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="d8171-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="d8171-109">Microsoft Threat Protection wordt automatisch ingeschakeld wanneer klanten die in aanmerking komen met de vereiste machtigingen naar Microsoft 365-Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="d8171-109">Microsoft Threat Protection automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="d8171-110">Lees dit artikel voor meer informatie over diverse vereisten en de manier waarop Microsoft Threat Protection wordt ingericht.</span><span class="sxs-lookup"><span data-stu-id="d8171-110">Read this article to understand various prerequisites and how Microsoft Threat Protection is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="d8171-111">Geschiktheid voor de licentie en de vereiste machtigingen controleren</span><span class="sxs-lookup"><span data-stu-id="d8171-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="d8171-112">Met een licentie voor een Microsoft 365-beveiligings product hebt u algemene informatie over het gebruik van Microsoft Threat Protection in Microsoft 365 Beveiligingscentrum zonder extra licentiekosten.</span><span class="sxs-lookup"><span data-stu-id="d8171-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft Threat Protection in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="d8171-113">U wordt aangeraden een Microsoft 365 E5-, E5-beveiligings licentie, A5, of A5-beveiligings licentie of een geldige combinatie van licenties te verkrijgen die toegang biedt tot alle ondersteunde services.</span><span class="sxs-lookup"><span data-stu-id="d8171-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="d8171-114">[Lees de licentievereisten](prerequisites.md#licensing-requirements)voor uitgebreide licentiegegevens.</span><span class="sxs-lookup"><span data-stu-id="d8171-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="d8171-115">Uw rol controleren</span><span class="sxs-lookup"><span data-stu-id="d8171-115">Check your role</span></span>
<span data-ttu-id="d8171-116">U moet een **globale beheerder** of een **beveiligingsbeheerder** van Azure Active Directory zijn om Microsoft Threat Protection in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="d8171-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="d8171-117">Uw rollen weergeven in azure AD</span><span class="sxs-lookup"><span data-stu-id="d8171-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="d8171-118">Ondersteunde services</span><span class="sxs-lookup"><span data-stu-id="d8171-118">Supported services</span></span>
<span data-ttu-id="d8171-119">Microsoft Threat Protection voegt gegevens samen van de verschillende ondersteunde services die u al hebt geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="d8171-119">Microsoft Threat Protection aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="d8171-120">De gegevens worden centraal verwerkt en opgeslagen om nieuwe inzichten te identificeren en mogelijk gecentraliseerde antwoord werkstromen te maken.</span><span class="sxs-lookup"><span data-stu-id="d8171-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="d8171-121">Dit gebeurt zonder dat dit invloed heeft op bestaande installaties, instellingen of gegevens die zijn gekoppeld aan de geïntegreerde services.</span><span class="sxs-lookup"><span data-stu-id="d8171-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="d8171-122">Om de beste beveiliging te bieden en Microsoft Threat Protection te optimaliseren, wordt u aangeraden alle toepasselijke ondersteunde services op uw netwerk te implementeren.</span><span class="sxs-lookup"><span data-stu-id="d8171-122">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="d8171-123">Lees voor meer informatie [over het implementeren van ondersteunde services](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="d8171-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="d8171-124">Voordat u de service start</span><span class="sxs-lookup"><span data-stu-id="d8171-124">Before starting the service</span></span>
<span data-ttu-id="d8171-125">Voordat u de service inschakelt, ziet u in het micro[soft 365-beveiligings](https://security.microsoft.com)centrum de pagina instellingen voor Microsoft Threat Protection wanneer u **incidenten**, **Onderhoudscentrum**of **jacht** selecteert in het navigatiedeelvenster.</span><span class="sxs-lookup"><span data-stu-id="d8171-125">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection settings page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="d8171-126">Deze navigatie-items worden niet weergegeven als u niet in aanmerking komt om Microsoft Threat Protection te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d8171-126">These navigation items are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="d8171-127">![Afbeelding van de pagina met instellingen voor Microsoft Threat Protection wordt weergegeven als Microsoft Bedreigingsbeveiliging niet is ingeschakeld op de instellingen voor Microsoft Threat ](../../media/mtp-enable/mtp-settings.png)
 *Protection in microsoft 365 Beveiligingscentrum*</span><span class="sxs-lookup"><span data-stu-id="d8171-127">![Image of the Microsoft Threat Protection settings page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft Threat Protection settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="d8171-128">De service starten</span><span class="sxs-lookup"><span data-stu-id="d8171-128">Starting the service</span></span>
<span data-ttu-id="d8171-129">Als u Microsoft Threat Protection wilt inschakelen, selecteert u **Microsoft bedreigingsbeveiliging inschakelen** en voegt u de wijziging toe.</span><span class="sxs-lookup"><span data-stu-id="d8171-129">To turn on Microsoft Threat Protection, simply select **Turn on Microsoft Threat Protection** and apply the change.</span></span> <span data-ttu-id="d8171-130">U kunt deze optie ook openen door **instellingen** ([Security.Microsoft.com/Settings](https://security.microsoft.com/settings)) te selecteren in het navigatiedeelvenster en vervolgens **Microsoft Threat Protection**te selecteren.</span><span class="sxs-lookup"><span data-stu-id="d8171-130">You can also access this option by selecting **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft Threat Protection**.</span></span>

>[!NOTE]
><span data-ttu-id="d8171-131">Als u **instellingen** niet ziet in het navigatiedeelvenster of de pagina niet kunt openen, controleert u de machtigingen en licenties.</span><span class="sxs-lookup"><span data-stu-id="d8171-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="d8171-132">Locatie van het Data Center</span><span class="sxs-lookup"><span data-stu-id="d8171-132">Data center location</span></span>
<span data-ttu-id="d8171-133">Microsoft Threat Protection opslaat en verwerkt gegevens op [dezelfde locatie als in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="d8171-133">Microsoft Threat Protection will store and process data in the [same location used by Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="d8171-134">Als u niet over Microsoft Defender ATP beschikt, wordt een nieuwe locatie voor het datacenter automatisch geselecteerd op basis van de locatie van de actieve beveiligingsservices van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d8171-134">If you don't have Microsoft Defender ATP, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="d8171-135">De geselecteerde locatie van het datacenter wordt in het scherm weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d8171-135">The selected data center location is shown in the screen.</span></span> 

<span data-ttu-id="d8171-136">Selecteer **hulp nodig?** in het microsoft 365-Beveiligingscentrum kunt u contact opnemen met Microsoft ondersteuning voor het inrichten van Microsoft Threat Protection op een andere locatie van het datacenter.</span><span class="sxs-lookup"><span data-stu-id="d8171-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft Threat Protection in a different data center location.</span></span> 

>[!NOTE]
><span data-ttu-id="d8171-137">In Microsoft Defender ATP worden automatisch de voorzieningen van de Europese Unie (EU)-datacenters automatisch ingericht wanneer ze zijn ingeschakeld via Azure Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="d8171-137">Microsoft Defender ATP automatically provisions in European Union (EU) data centers when turned on through Azure Security Center.</span></span> <span data-ttu-id="d8171-138">Microsoft Threat Protection wordt automatisch ingericht in hetzelfde EU-datacenter voor klanten die op deze manier Microsoft Defender ATP hebben ingericht.</span><span class="sxs-lookup"><span data-stu-id="d8171-138">Microsoft Threat Protection will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender ATP in this manner.</span></span> 

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="d8171-139">Ga na of de service is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="d8171-139">Confirm that the service is on</span></span>
<span data-ttu-id="d8171-140">Wanneer de service is ingericht, wordt het volgende toegevoegd:</span><span class="sxs-lookup"><span data-stu-id="d8171-140">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="d8171-141">Beheer van incidenten</span><span class="sxs-lookup"><span data-stu-id="d8171-141">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="d8171-142">Een Actiecentrum voor het beheren van [geautomatiseerde onderzoek en reacties](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="d8171-142">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="d8171-143">[Geavanceerde](advanced-hunting-overview.md) functies voor de jacht</span><span class="sxs-lookup"><span data-stu-id="d8171-143">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="d8171-144">![Afbeelding van het navigatiedeelvenster van Microsoft 365-Beveiligingscentrum met Microsoft Threat Protection-functies ](../../media/mtp-enable/mtp-on.png)
 *microsoft 365 Beveiligingscentrum met incidentenbeheer en andere mogelijkheden van Microsoft Threat Protection*</span><span class="sxs-lookup"><span data-stu-id="d8171-144">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="d8171-145">Azure ATP-gegevens verkrijgen</span><span class="sxs-lookup"><span data-stu-id="d8171-145">Getting Azure ATP data</span></span>
<span data-ttu-id="d8171-146">Als u Azure ATP-gegevens wilt delen met Microsoft Threat Protection, moet u ervoor zorgen dat Microsoft Cloud app Security en Azure ATP-integratie is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="d8171-146">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="d8171-147">Meer informatie over deze integratie</span><span class="sxs-lookup"><span data-stu-id="d8171-147">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="d8171-148">Microsoft Threat Protection uitschakelen</span><span class="sxs-lookup"><span data-stu-id="d8171-148">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="d8171-149">Als u wilt stoppen met het gebruik van Microsoft Threat Protection, gaat u naar **instellingen**  >  **Microsoft bedreigingsbeveiliging**  >  **/Afmelden** in het Microsoft 365-Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="d8171-149">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="d8171-150">Schakel **Microsoft Threat Protection uit** en pas de wijzigingen toe.</span><span class="sxs-lookup"><span data-stu-id="d8171-150">Unselect **Turn on Microsoft Threat Protection** and apply the changes.</span></span>

<span data-ttu-id="d8171-151">De bijbehorende functies worden verwijderd uit het Microsoft 365-Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="d8171-151">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="d8171-152">Ondersteuning vragen</span><span class="sxs-lookup"><span data-stu-id="d8171-152">Get assistance</span></span>

<span data-ttu-id="d8171-153">Voor antwoorden op de meest gestelde vragen over het inschakelen van Microsoft Threat Protection [raadpleegt u de veelgestelde vragen](mtp-enable-faq.md).</span><span class="sxs-lookup"><span data-stu-id="d8171-153">To get answers to the most commonly asked questions about turning on Microsoft Threat Protection, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="d8171-154">Ondersteuningspersoneel van Microsoft kan u helpen bij het inrichten van of het inrichten van de service en verwante bronnen voor uw Tenant.</span><span class="sxs-lookup"><span data-stu-id="d8171-154">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="d8171-155">Als u hulp nodig hebt, selecteert u **hulp nodig?** in het microsoft 365-Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="d8171-155">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="d8171-156">Vermeld Microsoft Threat Protection wanneer u contact opneemt met de ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="d8171-156">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d8171-157">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="d8171-157">Related topics</span></span>

- [<span data-ttu-id="d8171-158">Veelgestelde vragen</span><span class="sxs-lookup"><span data-stu-id="d8171-158">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="d8171-159">Licentievereisten en andere vereisten</span><span class="sxs-lookup"><span data-stu-id="d8171-159">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="d8171-160">Ondersteunde services implementeren</span><span class="sxs-lookup"><span data-stu-id="d8171-160">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="d8171-161">Overzicht van Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d8171-161">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="d8171-162">Overzicht van Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="d8171-162">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="d8171-163">Overzicht van Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="d8171-163">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="d8171-164">Overzicht van de beveiliging van Microsoft Cloud-app</span><span class="sxs-lookup"><span data-stu-id="d8171-164">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="d8171-165">Overzicht van Azure ATP</span><span class="sxs-lookup"><span data-stu-id="d8171-165">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="d8171-166">Microsoft Defender ATP Data Storage</span><span class="sxs-lookup"><span data-stu-id="d8171-166">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
