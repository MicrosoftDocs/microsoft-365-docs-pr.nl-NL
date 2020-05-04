---
title: Microsoft Threat Protection inschakelen in het Microsoft 365-beveiligingscentrum
description: Meer informatie over het inschakelen van Microsoft Threat Protection en het integreren van uw beveiligingsincident en -reactie.
keywords: aan de slag, MTP, Microsoft Threat Protection, M365, beveiliging, gegevenslocatie, vereiste machtigingen, geschiktheid voor licenties, instellingenpagina inschakelen
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
ms.openlocfilehash: 0bb91f226a29fe6b175cf1ca4866316d1457291e
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011861"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="5fd10-104">Microsoft Threat Protection inschakelen</span><span class="sxs-lookup"><span data-stu-id="5fd10-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="5fd10-105">**Geldt voor:**</span><span class="sxs-lookup"><span data-stu-id="5fd10-105">**Applies to:**</span></span>
- <span data-ttu-id="5fd10-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="5fd10-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="5fd10-107">Microsoft Threat Protection maakt een oplossing voor incidentrespons door de integratie van belangrijke mogelijkheden voor Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security en Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="5fd10-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="5fd10-108">Deze uniforme ervaring voegt krachtige functies toe die u openen in het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="5fd10-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="5fd10-109">Om de beste bescherming te krijgen en Microsoft Threat Protection te optimaliseren, raden we u aan alle toepasselijke ondersteunde services in uw netwerk te implementeren.</span><span class="sxs-lookup"><span data-stu-id="5fd10-109">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="5fd10-110">Lees voor meer informatie [over het implementeren van ondersteunde services](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="5fd10-110">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="5fd10-111">Controleer de geschiktheid van de licentie en vereiste machtigingen</span><span class="sxs-lookup"><span data-stu-id="5fd10-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="5fd10-112">Een Microsoft 365 E5-, E5 Security-, A5- of A5-beveiligingslicentie of een geldige combinatie van licenties biedt toegang tot ondersteunde services en geeft u het recht om Microsoft Threat Protection te gebruiken in het Microsoft 365-beveiligingscentrum zonder extra licentiekosten.</span><span class="sxs-lookup"><span data-stu-id="5fd10-112">A Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses provides access to supported services and entitles you to use Microsoft Threat Protection in Microsoft 365 security center without additional licensing cost.</span></span>

<span data-ttu-id="5fd10-113">Lees voor gedetailleerde licentie-informatie [de licentievereisten.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="5fd10-113">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="5fd10-114">Controleer uw rol</span><span class="sxs-lookup"><span data-stu-id="5fd10-114">Check your role</span></span>
<span data-ttu-id="5fd10-115">U moet een **globale beheerder** of **beveiligingsbeheerder** in Azure Active Directory zijn om Microsoft Threat Protection in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="5fd10-115">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="5fd10-116">Uw rollen weergeven in Azure AD</span><span class="sxs-lookup"><span data-stu-id="5fd10-116">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a><span data-ttu-id="5fd10-117">De service gaan gebruiken</span><span class="sxs-lookup"><span data-stu-id="5fd10-117">Start using the service</span></span>

>[!IMPORTANT]
><span data-ttu-id="5fd10-118">Vanaf 3 mei 2020 zal Microsoft geleidelijk nieuwe, geoptimaliseerde ervaringen rond [licentievereisten](prerequisites.md#licensing-requirements) uitrollen en Microsoft Threat Protection inschakelen.</span><span class="sxs-lookup"><span data-stu-id="5fd10-118">Starting May 3, 2020, Microsoft will gradually roll out new, optimized experiences around [licensing requirements](prerequisites.md#licensing-requirements) and turning on Microsoft Threat Protection.</span></span> <span data-ttu-id="5fd10-119">Gedurende enkele weken tijdens deze periode zullen sommige klanten wijzigingen in hun portalervaringen gaan zien.</span><span class="sxs-lookup"><span data-stu-id="5fd10-119">For several weeks during this period, some customers will start to see changes to their portal experiences.</span></span> <span data-ttu-id="5fd10-120">Informatie over de nieuwe ervaringen zijn gemarkeerd **Nieuwe ervaring** in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="5fd10-120">Information about the new experiences are marked **New experience** in this article.</span></span>

<span data-ttu-id="5fd10-121">Microsoft Threat Protection verzamelt gegevens van de verschillende geïntegreerde services.</span><span class="sxs-lookup"><span data-stu-id="5fd10-121">Microsoft Threat Protection aggregates data from the various integrated services.</span></span> <span data-ttu-id="5fd10-122">Het zal gegevens centraal verwerken en opslaan om nieuwe inzichten te identificeren en gecentraliseerde responsworkflows mogelijk te maken.</span><span class="sxs-lookup"><span data-stu-id="5fd10-122">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="5fd10-123">Het doet dit zonder dat dit gevolgen heeft voor bestaande implementaties, instellingen of gegevens die zijn gekoppeld aan de geïntegreerde services.</span><span class="sxs-lookup"><span data-stu-id="5fd10-123">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="5fd10-124">Voordat u de service inschakelt, wordt in het Microsoft 365-beveiligingscentrum[(security.microsoft.com](https://security.microsoft.com)) de welkomstpagina van Microsoft Threat Protection weergegeven wanneer u **Incidenten,** **actiecentrum**of **Jagen** selecteert in het navigatiedeelvenster.</span><span class="sxs-lookup"><span data-stu-id="5fd10-124">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection welcome page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="5fd10-125">Deze navigatieopties worden niet weergegeven als u niet in aanmerking komt voor microsoft-beveiligingsbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="5fd10-125">These navigation options are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="5fd10-126">![Afbeelding van de welkomstpagina van Microsoft Threat Protection die](../../media/mtp-welcome.png)
wordt weergegeven als Microsoft Threat Protection niet is ingeschakeld op*de welkomstpagina van Microsoft Threat Protection in het Microsoft 365-beveiligingscentrum*</span><span class="sxs-lookup"><span data-stu-id="5fd10-126">![Image of the Microsoft Threat Protection welcome page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-welcome.png)
*Microsoft Threat Protection welcome page in Microsoft 365 security center*</span></span>

<span data-ttu-id="5fd10-127">Als u Microsoft Threat Protection wilt inschakelen, voltooit u het proces vanaf de welkomstpagina.</span><span class="sxs-lookup"><span data-stu-id="5fd10-127">To turn on Microsoft Threat Protection, simply complete the process from the welcome page.</span></span> <span data-ttu-id="5fd10-128">U Microsoft Threat Protection ook inschakelen door **instellingen** [(security.microsoft.com/settings)](https://security.microsoft.com/settings)in het navigatiedeelvenster te openen en **Microsoft Threat Protection te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="5fd10-128">You can also turn on Microsoft Threat Protection by accessing **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and selecting **Microsoft Threat Protection**.</span></span>

>[!NOTE]
><span data-ttu-id="5fd10-129">Als u **instellingen** niet ziet in het navigatiedeelvenster of geen toegang hebt tot de pagina, controleert u uw machtigingen en licenties.</span><span class="sxs-lookup"><span data-stu-id="5fd10-129">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>       

### <a name="select-data-center-location"></a><span data-ttu-id="5fd10-130">Locatie van het datacenter selecteren</span><span class="sxs-lookup"><span data-stu-id="5fd10-130">Select data center location</span></span>
<span data-ttu-id="5fd10-131">Als Microsoft Defender ATP is ingericht voor uw organisatie, worden gegevens opgeslagen en verwerkt op dezelfde datacenterlocatie die u hebt geselecteerd voor [uw ATP-gegevens](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)van Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="5fd10-131">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="5fd10-132">Als u geen Microsoft Defender ATP hebt, wordt u gevraagd om een nieuwe datacenterlocatie te kiezen die specifiek voor Microsoft Threat Protection is bedoeld.</span><span class="sxs-lookup"><span data-stu-id="5fd10-132">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> 
 
<span data-ttu-id="5fd10-133">U moet toestemming geven voordat gegevens worden gedeeld tussen services en worden samengevoegd.</span><span class="sxs-lookup"><span data-stu-id="5fd10-133">You need to provide consent before data is shared between services and aggregated.</span></span>

<span data-ttu-id="5fd10-134">**Nieuwe ervaring:** Vanaf 3 mei 2020 krijgen klanten geleidelijk wijzigingen in deze ervaring.</span><span class="sxs-lookup"><span data-stu-id="5fd10-134">**New experience:** Starting May 3, 2020, customers will gradually receive changes to this experience.</span></span> <span data-ttu-id="5fd10-135">Voor degenen met de nieuwe ervaring selecteert de service automatisch de optimale datacenterlocatie voor uw geaggregeerde gegevens op basis van uw bestaande Microsoft 365-beveiligingsservices.</span><span class="sxs-lookup"><span data-stu-id="5fd10-135">For those with the new experience, the service automatically selects the optimal data center location for your aggregated data based on your existing Microsoft 365 security services.</span></span> <span data-ttu-id="5fd10-136">De geselecteerde locatie van het datacenter wordt weergegeven in het scherm.</span><span class="sxs-lookup"><span data-stu-id="5fd10-136">The selected data center location is shown in the screen.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="5fd10-137">Controleren of de service is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="5fd10-137">Confirm that the service is on</span></span>
<span data-ttu-id="5fd10-138">Zodra de service is ingericht, voegt het toe:</span><span class="sxs-lookup"><span data-stu-id="5fd10-138">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="5fd10-139">Incidentenbeheer</span><span class="sxs-lookup"><span data-stu-id="5fd10-139">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="5fd10-140">Een actiecentrum voor het beheren van [geautomatiseerd onderzoek en respons](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="5fd10-140">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="5fd10-141">[Geavanceerde jachtmogelijkheden](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="5fd10-141">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="5fd10-142">![Afbeelding van het navigatiedeelvenster van het Beveiligingscentrum](../../media/mtp-on.png)
van Microsoft 365 met Microsoft Threat Protection-functies*Microsoft 365-beveiligingscentrum met incidentenbeheer en andere mogelijkheden voor Microsoft-bedreigingsbeveiliging*</span><span class="sxs-lookup"><span data-stu-id="5fd10-142">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="5fd10-143">Azure ATP-gegevens opvragen</span><span class="sxs-lookup"><span data-stu-id="5fd10-143">Getting Azure ATP data</span></span>
<span data-ttu-id="5fd10-144">Als u Azure ATP-gegevens wilt delen met Microsoft Threat Protection, moet u ervoor zorgen dat Microsoft Cloud App Security en Azure ATP-integratie zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="5fd10-144">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="5fd10-145">Meer informatie over deze integratie</span><span class="sxs-lookup"><span data-stu-id="5fd10-145">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="5fd10-146">Microsoft-bedreigingsbeveiliging uitschakelen</span><span class="sxs-lookup"><span data-stu-id="5fd10-146">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="5fd10-147">Als u microsoft-beveiligingsbeveiliging niet meer wilt gebruiken, gaat u naar >  **Opt-in-instellingen** > **van Microsoft Threat Protection**/**Opt-out** in het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="5fd10-147">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="5fd10-148">Schakel De optie **Microsoft Threat Protection inschakelen uit** en sla de wijzigingen op.</span><span class="sxs-lookup"><span data-stu-id="5fd10-148">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="5fd10-149">Overeenkomstige functies worden verwijderd uit het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="5fd10-149">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="5fd10-150">Hulp krijgen</span><span class="sxs-lookup"><span data-stu-id="5fd10-150">Get assistance</span></span>

<span data-ttu-id="5fd10-151">Microsoft-ondersteuningsmedewerkers kunnen helpen bij het inrichten of deprovisioneren van de service en gerelateerde bronnen op uw tenant.</span><span class="sxs-lookup"><span data-stu-id="5fd10-151">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="5fd10-152">Selecteer Hulp **nodig** in het Microsoft 365-beveiligingscentrum voor hulp?</span><span class="sxs-lookup"><span data-stu-id="5fd10-152">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="5fd10-153">Vermeld Microsoft Threat Protection wanneer u contact opneemt met ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="5fd10-153">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5fd10-154">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="5fd10-154">Related topics</span></span>

- [<span data-ttu-id="5fd10-155">Overzicht van Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="5fd10-155">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="5fd10-156">Licentievereisten en andere vereisten</span><span class="sxs-lookup"><span data-stu-id="5fd10-156">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="5fd10-157">Ondersteunde services implementeren</span><span class="sxs-lookup"><span data-stu-id="5fd10-157">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="5fd10-158">Overzicht van Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="5fd10-158">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="5fd10-159">Overzicht van Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="5fd10-159">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="5fd10-160">Overzicht van Microsoft Cloud App-beveiliging</span><span class="sxs-lookup"><span data-stu-id="5fd10-160">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="5fd10-161">Overzicht van Azure ATP</span><span class="sxs-lookup"><span data-stu-id="5fd10-161">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="5fd10-162">Microsoft Defender ATP-gegevensopslag</span><span class="sxs-lookup"><span data-stu-id="5fd10-162">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
