---
title: Microsoft 365 Defender inschakelen in het Microsoft 365 Beveiligingscentrum
description: Meer informatie over het inschakelen van Microsoft 365 Defender en het integreren van uw beveiligingsincident en-antwoord.
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
ms.openlocfilehash: fbe98b814b253551432ea35102f2bd6eeba921f8
ms.sourcegitcommit: 1beaf89d2faa32f11fe1613be2fa2b31c4bc4a91
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/08/2020
ms.locfileid: "49602084"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="82c00-104">Microsoft 365 Defender inschakelen</span><span class="sxs-lookup"><span data-stu-id="82c00-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="82c00-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="82c00-105">**Applies to:**</span></span>
- <span data-ttu-id="82c00-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="82c00-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="82c00-107">[Microsoft 365 Defender](microsoft-threat-protection.md) verenigt uw incident-antwoord proces door de belangrijkste mogelijkheden van Microsoft Defender for endpoints te integreren, Microsoft Defender for Office 365, Microsoft Cloud app Security en Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="82c00-107">[Microsoft 365 Defender](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="82c00-108">Deze geïntegreerde ervaring voegt krachtige functies toe die u kunt gebruiken in het Microsoft 365-Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="82c00-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="82c00-109">Microsoft 365 Defender wordt automatisch ingeschakeld wanneer klanten in aanmerking komen met de vereiste machtigingen naar Microsoft 365 Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="82c00-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="82c00-110">In dit artikel vindt u meer informatie over diverse vereisten en hoe Microsoft 365 Defender wordt ingericht.</span><span class="sxs-lookup"><span data-stu-id="82c00-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="82c00-111">Geschiktheid voor de licentie en de vereiste machtigingen controleren</span><span class="sxs-lookup"><span data-stu-id="82c00-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="82c00-112">Met een licentie voor een Microsoft 365-beveiligings product hebt u algemene informatie over het gebruik van Microsoft 365 Defender in Microsoft 365 Beveiligingscentrum zonder extra licentiekosten.</span><span class="sxs-lookup"><span data-stu-id="82c00-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="82c00-113">U wordt aangeraden een Microsoft 365 E5-, E5-beveiligings licentie, A5, of A5-beveiligings licentie of een geldige combinatie van licenties te verkrijgen die toegang biedt tot alle ondersteunde services.</span><span class="sxs-lookup"><span data-stu-id="82c00-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="82c00-114">[Lees de licentievereisten](prerequisites.md#licensing-requirements)voor uitgebreide licentiegegevens.</span><span class="sxs-lookup"><span data-stu-id="82c00-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="82c00-115">Uw rol controleren</span><span class="sxs-lookup"><span data-stu-id="82c00-115">Check your role</span></span>
<span data-ttu-id="82c00-116">U moet een **globale beheerder** of een **beveiligingsbeheerder** in azure Active Directory zijn om Microsoft 365 Defender in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="82c00-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="82c00-117">Uw rollen weergeven in azure AD</span><span class="sxs-lookup"><span data-stu-id="82c00-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="82c00-118">Ondersteunde services</span><span class="sxs-lookup"><span data-stu-id="82c00-118">Supported services</span></span>
<span data-ttu-id="82c00-119">Microsoft 365 Defender voegt gegevens samen van de verschillende ondersteunde services die u al hebt geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="82c00-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="82c00-120">De gegevens worden centraal verwerkt en opgeslagen om nieuwe inzichten te identificeren en mogelijk gecentraliseerde antwoord werkstromen te maken.</span><span class="sxs-lookup"><span data-stu-id="82c00-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="82c00-121">Dit gebeurt zonder dat dit invloed heeft op bestaande installaties, instellingen of gegevens die zijn gekoppeld aan de geïntegreerde services.</span><span class="sxs-lookup"><span data-stu-id="82c00-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="82c00-122">Om de beste beveiliging te bieden en Microsoft 365 Defender te optimaliseren, wordt u aangeraden alle toepasselijke ondersteunde services op uw netwerk te implementeren.</span><span class="sxs-lookup"><span data-stu-id="82c00-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="82c00-123">Lees voor meer informatie [over het implementeren van ondersteunde services](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="82c00-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="82c00-124">Voordat u de service start</span><span class="sxs-lookup"><span data-stu-id="82c00-124">Before starting the service</span></span>
<span data-ttu-id="82c00-125">Voordat u de service inschakelt, ziet u in het micro [soft 365-beveiligings](https://security.microsoft.com)centrum de pagina met instellingen voor microsoft 365 Defender wanneer u **incidenten**, **Onderhoudscentrum** of **jacht** selecteert in het navigatiedeelvenster.</span><span class="sxs-lookup"><span data-stu-id="82c00-125">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft 365 Defender settings page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="82c00-126">Deze navigatie-items worden niet weergegeven als u niet in aanmerking komt voor het gebruik van Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="82c00-126">These navigation items are not shown if you are not eligible to use Microsoft 365 Defender.</span></span>

<span data-ttu-id="82c00-127">![Afbeelding van de pagina met instellingen voor Microsoft 365 Defender, die wordt weergegeven als Microsoft 365 Defender niet is ingeschakeld voor de ](../../media/mtp-enable/mtp-settings.png)
 *instellingen van microsoft 365 Defender in microsoft 365 Beveiligingscentrum*</span><span class="sxs-lookup"><span data-stu-id="82c00-127">![Image of the Microsoft 365 Defender settings page shown if Microsoft 365 Defender has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft 365 Defender settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="82c00-128">De service starten</span><span class="sxs-lookup"><span data-stu-id="82c00-128">Starting the service</span></span>
<span data-ttu-id="82c00-129">Als u Microsoft 365 Defender wilt inschakelen, selecteert u **Microsoft 365 Defender inschakelen** en voegt u de wijziging toe.</span><span class="sxs-lookup"><span data-stu-id="82c00-129">To turn on Microsoft 365 Defender, simply select **Turn on Microsoft 365 Defender** and apply the change.</span></span> <span data-ttu-id="82c00-130">U kunt deze optie ook openen door **instellingen** ([Security.Microsoft.com/Settings](https://security.microsoft.com/settings)) te selecteren in het navigatiedeelvenster en vervolgens **Microsoft 365 Defender** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="82c00-130">You can also access this option by selecting **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft 365 Defender**.</span></span>

>[!NOTE]
><span data-ttu-id="82c00-131">Als u **instellingen** niet ziet in het navigatiedeelvenster of de pagina niet kunt openen, controleert u de machtigingen en licenties.</span><span class="sxs-lookup"><span data-stu-id="82c00-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="82c00-132">Locatie van het Data Center</span><span class="sxs-lookup"><span data-stu-id="82c00-132">Data center location</span></span>
<span data-ttu-id="82c00-133">In Microsoft 365 Defender worden gegevens opgeslagen en verwerkt op [dezelfde locatie die wordt gebruikt door Microsoft Defender voor eindpunt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="82c00-133">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="82c00-134">Als u Microsoft Defender voor eindpunten niet hebt, wordt een nieuwe locatie voor het datacenter automatisch geselecteerd op basis van de locatie van de actieve Microsoft 365-beveiligingsservices.</span><span class="sxs-lookup"><span data-stu-id="82c00-134">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="82c00-135">De geselecteerde locatie van het datacenter wordt in het scherm weergegeven.</span><span class="sxs-lookup"><span data-stu-id="82c00-135">The selected data center location is shown in the screen.</span></span> 

<span data-ttu-id="82c00-136">Selecteer **hulp nodig?** in het microsoft 365-Beveiligingscentrum kunt u contact opnemen met Microsoft ondersteuning voor het inrichten van microsoft 365 Defender op een andere locatie van het datacenter.</span><span class="sxs-lookup"><span data-stu-id="82c00-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span> 

>[!NOTE]
><span data-ttu-id="82c00-137">Microsoft Defender voor eindpunten in de Europese Unie (EU)-datacenters worden automatisch aangerekend wanneer Azure Defender wordt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="82c00-137">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="82c00-138">Microsoft 365 Defender voorziet automatisch in hetzelfde EU-datacenter voor klanten die de einddatum van de einddatum van eindpunten op deze manier hebben ingericht.</span><span class="sxs-lookup"><span data-stu-id="82c00-138">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span> 

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="82c00-139">Ga na of de service is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="82c00-139">Confirm that the service is on</span></span>
<span data-ttu-id="82c00-140">Wanneer de service is ingericht, wordt het volgende toegevoegd:</span><span class="sxs-lookup"><span data-stu-id="82c00-140">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="82c00-141">Beheer van incidenten</span><span class="sxs-lookup"><span data-stu-id="82c00-141">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="82c00-142">Een Actiecentrum voor het beheren van [geautomatiseerde onderzoek en reacties](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="82c00-142">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="82c00-143">[Geavanceerde](advanced-hunting-overview.md) functies voor de jacht</span><span class="sxs-lookup"><span data-stu-id="82c00-143">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="82c00-144">![Afbeelding van het navigatiedeelvenster van Microsoft 365-Beveiligingscentrum met Microsoft 365 Defender-functies ](../../media/mtp-enable/mtp-on.png)
 *microsoft 365 Beveiligingscentrum met incidentenbeheer en andere microsoft 365-mogelijkheden*</span><span class="sxs-lookup"><span data-stu-id="82c00-144">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="82c00-145">Microsoft Defender voor identiteitsgegevens verkrijgen</span><span class="sxs-lookup"><span data-stu-id="82c00-145">Getting Microsoft Defender for Identity data</span></span>
<span data-ttu-id="82c00-146">Als u Microsoft Defender wilt delen voor identiteitsgegevens met Microsoft 365 Defender, moet u ervoor zorgen dat Microsoft Cloud app Security en Microsoft Defender voor identiteits integratie is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="82c00-146">To share Microsoft Defender for Identity data with Microsoft 365 Defender, ensure that Microsoft Cloud App Security and Microsoft Defender for Identity integration is turned on.</span></span> [<span data-ttu-id="82c00-147">Meer informatie over deze integratie</span><span class="sxs-lookup"><span data-stu-id="82c00-147">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="get-assistance"></a><span data-ttu-id="82c00-148">Ondersteuning vragen</span><span class="sxs-lookup"><span data-stu-id="82c00-148">Get assistance</span></span>

<span data-ttu-id="82c00-149">Voor antwoorden op de meest gestelde vragen over het inschakelen van Microsoft 365 Defender [raadpleegt u de veelgestelde vragen](mtp-enable-faq.md).</span><span class="sxs-lookup"><span data-stu-id="82c00-149">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="82c00-150">Ondersteuningspersoneel van Microsoft kan u helpen bij het inrichten van of het inrichten van de service en verwante bronnen voor uw Tenant.</span><span class="sxs-lookup"><span data-stu-id="82c00-150">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="82c00-151">Als u hulp nodig hebt, selecteert u **hulp nodig?** in het microsoft 365-Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="82c00-151">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="82c00-152">Vermeld Microsoft 365 Defender wanneer u contact opneemt met de ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="82c00-152">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="82c00-153">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="82c00-153">Related topics</span></span>

- [<span data-ttu-id="82c00-154">Veelgestelde vragen</span><span class="sxs-lookup"><span data-stu-id="82c00-154">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="82c00-155">Licentievereisten en andere vereisten</span><span class="sxs-lookup"><span data-stu-id="82c00-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="82c00-156">Ondersteunde services implementeren</span><span class="sxs-lookup"><span data-stu-id="82c00-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="82c00-157">Overzicht van Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="82c00-157">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="82c00-158">Overzicht van Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="82c00-158">Microsoft Defender for Endpoint overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="82c00-159">Overzicht van Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="82c00-159">Defender for Office 365 overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="82c00-160">Overzicht van de beveiliging van Microsoft Cloud-app</span><span class="sxs-lookup"><span data-stu-id="82c00-160">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="82c00-161">Overzicht van Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="82c00-161">Microsoft Defender for Identity overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="82c00-162">Gegevensopslag voor Microsoft Defender voor eindpunten</span><span class="sxs-lookup"><span data-stu-id="82c00-162">Microsoft Defender for Endpoint data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
