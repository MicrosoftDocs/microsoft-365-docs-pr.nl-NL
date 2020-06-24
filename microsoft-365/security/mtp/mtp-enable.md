---
title: Microsoft Threat Protection inschakelen in het Microsoft 365-beveiligingscentrum
description: Meer informatie over het inschakelen van Microsoft Threat Protection en het integreren van uw beveiligingsincident en -reactie.
keywords: aan de slag, schakel MTP, Microsoft Threat Protection, M365, beveiliging, gegevenslocatie, vereiste machtigingen, licentiegeschiktheid, instellingenpagina in
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
ms.openlocfilehash: 0badae0d81b52b89c47f950b889109d4b9d35dda
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844590"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="afdca-104">Microsoft Threat Protection inschakelen</span><span class="sxs-lookup"><span data-stu-id="afdca-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="afdca-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="afdca-105">**Applies to:**</span></span>
- <span data-ttu-id="afdca-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="afdca-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="afdca-107">[Microsoft Threat Protection](microsoft-threat-protection.md) verenigt uw incidentresponsproces door de belangrijkste mogelijkheden te integreren in Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security en Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="afdca-107">[Microsoft Threat Protection](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="afdca-108">Deze uniforme ervaring voegt krachtige functies toe die u openen in het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="afdca-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="afdca-109">Microsoft Threat Protection wordt automatisch ingeschakeld wanneer in aanmerking komende klanten met de vereiste machtigingen het Microsoft 365-beveiligingscentrum bezoeken.</span><span class="sxs-lookup"><span data-stu-id="afdca-109">Microsoft Threat Protection automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="afdca-110">Lees dit artikel om inzicht te krijgen in verschillende vereisten en hoe Microsoft Threat Protection is ingericht.</span><span class="sxs-lookup"><span data-stu-id="afdca-110">Read this article to understand various prerequisites and how Microsoft Threat Protection is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="afdca-111">Controleer de geschiktheid van de licentie en vereiste machtigingen</span><span class="sxs-lookup"><span data-stu-id="afdca-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="afdca-112">Een licentie voor een Microsoft 365-beveiligingsproduct geeft u over het algemeen het recht om Microsoft Threat Protection te gebruiken in het Microsoft 365-beveiligingscentrum zonder extra licentiekosten.</span><span class="sxs-lookup"><span data-stu-id="afdca-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft Threat Protection in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="afdca-113">We raden u aan een Microsoft 365 E5-, E5-beveiligings-, A5- of A5-beveiligingslicentie of een geldige combinatie van licenties te krijgen die toegang biedt tot alle ondersteunde services.</span><span class="sxs-lookup"><span data-stu-id="afdca-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="afdca-114">Lees voor gedetailleerde licentie-informatie [de licentievereisten](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="afdca-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="afdca-115">Controleer uw rol</span><span class="sxs-lookup"><span data-stu-id="afdca-115">Check your role</span></span>
<span data-ttu-id="afdca-116">U moet een **globale beheerder** of een **beveiligingsbeheerder** in Azure Active Directory zijn om Microsoft Threat Protection in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="afdca-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="afdca-117">Uw rollen weergeven in Azure AD</span><span class="sxs-lookup"><span data-stu-id="afdca-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="afdca-118">Ondersteunde services</span><span class="sxs-lookup"><span data-stu-id="afdca-118">Supported services</span></span>
<span data-ttu-id="afdca-119">Microsoft Threat Protection verzamelt gegevens van de verschillende ondersteunde services die u al hebt geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="afdca-119">Microsoft Threat Protection aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="afdca-120">Het verwerkt en slaat gegevens centraal op om nieuwe inzichten te identificeren en gecentraliseerde responsworkflows mogelijk te maken.</span><span class="sxs-lookup"><span data-stu-id="afdca-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="afdca-121">Dit gebeurt zonder dat dit gevolgen heeft voor bestaande implementaties, instellingen of gegevens die zijn gekoppeld aan de geïntegreerde services.</span><span class="sxs-lookup"><span data-stu-id="afdca-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="afdca-122">Om de beste bescherming te krijgen en Microsoft Threat Protection te optimaliseren, raden we u aan alle toepasselijke ondersteunde services in uw netwerk te implementeren.</span><span class="sxs-lookup"><span data-stu-id="afdca-122">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="afdca-123">Lees voor meer informatie [over het implementeren van ondersteunde services.](deploy-supported-services.md)</span><span class="sxs-lookup"><span data-stu-id="afdca-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="afdca-124">Voordat u met de service begint</span><span class="sxs-lookup"><span data-stu-id="afdca-124">Before starting the service</span></span>
<span data-ttu-id="afdca-125">Voordat u de service inschakelt, wordt in het Microsoft 365-beveiligingscentrum[(security.microsoft.com)](https://security.microsoft.com)de pagina Microsoft Threat Protection-instellingen weergegeven wanneer u **Incidenten,** **Actiecentrum**of **Hunting** selecteert in het navigatiedeelvenster.</span><span class="sxs-lookup"><span data-stu-id="afdca-125">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection settings page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="afdca-126">Deze navigatie-items worden niet weergegeven als u niet in aanmerking komt voor het gebruik van Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="afdca-126">These navigation items are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="afdca-127">![Afbeelding van de pagina Microsoft Threat Protection-instellingen die wordt weergegeven als Microsoft Threat Protection niet is ingeschakeld in ](../../media/mtp-enable/mtp-settings.png)
 *microsoft 365-beveiligingscentrum*</span><span class="sxs-lookup"><span data-stu-id="afdca-127">![Image of the Microsoft Threat Protection settings page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft Threat Protection settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="afdca-128">De service starten</span><span class="sxs-lookup"><span data-stu-id="afdca-128">Starting the service</span></span>
<span data-ttu-id="afdca-129">Als u Microsoft Threat Protection wilt inschakelen, selecteert u **Microsoft Threat Protection inschakelen** en past u de wijziging toe.</span><span class="sxs-lookup"><span data-stu-id="afdca-129">To turn on Microsoft Threat Protection, simply select **Turn on Microsoft Threat Protection** and apply the change.</span></span> <span data-ttu-id="afdca-130">U deze optie ook openen door **Instellingen** [(security.microsoft.com/settings)](https://security.microsoft.com/settings)in het navigatiedeelvenster te selecteren en **vervolgens Microsoft-bedreigingsbeveiliging te**selecteren.</span><span class="sxs-lookup"><span data-stu-id="afdca-130">You can also access this option by selecting **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft Threat Protection**.</span></span>

>[!NOTE]
><span data-ttu-id="afdca-131">Als u **Instellingen** niet ziet in het navigatiedeelvenster of geen toegang hebt tot de pagina, controleert u uw machtigingen en licenties.</span><span class="sxs-lookup"><span data-stu-id="afdca-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="afdca-132">Locatie datacenter</span><span class="sxs-lookup"><span data-stu-id="afdca-132">Data center location</span></span>
<span data-ttu-id="afdca-133">Microsoft Threat Protection slaat gegevens op en verwerkt deze op [dezelfde locatie die wordt gebruikt door Microsoft Defender ATP.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="afdca-133">Microsoft Threat Protection will store and process data in the [same location used by Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="afdca-134">Als u geen Microsoft Defender ATP hebt, wordt automatisch een nieuwe locatie van het datacenter geselecteerd op basis van de locatie van actieve Microsoft 365-beveiligingsservices.</span><span class="sxs-lookup"><span data-stu-id="afdca-134">If you don't have Microsoft Defender ATP, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="afdca-135">De geselecteerde locatie van het datacenter wordt weergegeven in het scherm.</span><span class="sxs-lookup"><span data-stu-id="afdca-135">The selected data center location is shown in the screen.</span></span>

>[!NOTE]
><span data-ttu-id="afdca-136">Selecteer **Hulp nodig?** In het Microsoft 365-beveiligingscentrum u contact opnemen met Microsoft-ondersteuning over het inrichten van Microsoft Threat Protection op een andere locatie van het datacenter.</span><span class="sxs-lookup"><span data-stu-id="afdca-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provision Microsoft Threat Protection in a different data center location.</span></span> 

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="afdca-137">Controleer of de service is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="afdca-137">Confirm that the service is on</span></span>
<span data-ttu-id="afdca-138">Zodra de service is ingericht, voegt zij eraan toe:</span><span class="sxs-lookup"><span data-stu-id="afdca-138">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="afdca-139">Incidentenbeheer</span><span class="sxs-lookup"><span data-stu-id="afdca-139">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="afdca-140">Een actiecentrum voor het beheren van [geautomatiseerd onderzoek en respons](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="afdca-140">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="afdca-141">[Geavanceerde jachtmogelijkheden](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="afdca-141">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="afdca-142">![Afbeelding van het navigatiedeelvenster van het Microsoft 365-beveiligingscentrum met Microsoft Threat Protection is voorzien van ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365-beveiligingscentrum met incidentenbeheer en andere microsoft Threat Protection-mogelijkheden*</span><span class="sxs-lookup"><span data-stu-id="afdca-142">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="afdca-143">Azure ATP-gegevens opvragen</span><span class="sxs-lookup"><span data-stu-id="afdca-143">Getting Azure ATP data</span></span>
<span data-ttu-id="afdca-144">Als u Azure ATP-gegevens wilt delen met Microsoft Threat Protection, moet u ervoor zorgen dat Microsoft Cloud App Security en Azure ATP-integratie zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="afdca-144">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="afdca-145">Meer informatie over deze integratie</span><span class="sxs-lookup"><span data-stu-id="afdca-145">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="afdca-146">Microsoft Threat Protection uitschakelen</span><span class="sxs-lookup"><span data-stu-id="afdca-146">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="afdca-147">Als u wilt stoppen met het gebruik van Microsoft Threat Protection, gaat u naar **Instellingen**  >  **Microsoft Threat Protection**  >  **Opt-in / Opt-out** in het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="afdca-147">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="afdca-148">Schakel **Microsoft-bedreigingsbeveiliging uitschakelen** en pas de wijzigingen toe.</span><span class="sxs-lookup"><span data-stu-id="afdca-148">Unselect **Turn on Microsoft Threat Protection** and apply the changes.</span></span>

<span data-ttu-id="afdca-149">De bijbehorende functies worden verwijderd uit het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="afdca-149">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="afdca-150">Hulp krijgen</span><span class="sxs-lookup"><span data-stu-id="afdca-150">Get assistance</span></span>

<span data-ttu-id="afdca-151">[Lees de veelgestelde](mtp-enable-faq.md)vragen voor antwoorden op de meest gestelde vragen over het inschakelen van Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="afdca-151">To get answers to the most commonly asked questions about turning on Microsoft Threat Protection, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="afdca-152">Microsoft-ondersteuningsmedewerkers kunnen helpen bij het inrichten of deprovisioneren van de service en gerelateerde bronnen op uw tenant.</span><span class="sxs-lookup"><span data-stu-id="afdca-152">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="afdca-153">Selecteer Hulp **nodig in** het Microsoft 365-beveiligingscentrum voor hulp.</span><span class="sxs-lookup"><span data-stu-id="afdca-153">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="afdca-154">Vermeld Microsoft Threat Protection wanneer u contact opneemt met ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="afdca-154">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="afdca-155">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="afdca-155">Related topics</span></span>

- [<span data-ttu-id="afdca-156">Veelgestelde vragen</span><span class="sxs-lookup"><span data-stu-id="afdca-156">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="afdca-157">Licentievereisten en andere voorwaarden</span><span class="sxs-lookup"><span data-stu-id="afdca-157">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="afdca-158">Ondersteunde services implementeren</span><span class="sxs-lookup"><span data-stu-id="afdca-158">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="afdca-159">Overzicht van Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="afdca-159">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="afdca-160">Microsoft Defender ATP-overzicht</span><span class="sxs-lookup"><span data-stu-id="afdca-160">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="afdca-161">AtP-overzicht van Office 365</span><span class="sxs-lookup"><span data-stu-id="afdca-161">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="afdca-162">Overzicht van microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="afdca-162">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="afdca-163">Azure ATP-overzicht</span><span class="sxs-lookup"><span data-stu-id="afdca-163">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="afdca-164">Microsoft Defender ATP-gegevensopslag</span><span class="sxs-lookup"><span data-stu-id="afdca-164">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)