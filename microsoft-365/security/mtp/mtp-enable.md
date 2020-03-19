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
ms.openlocfilehash: fa970b28939ad43bf6a2717e603013277bc9130f
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42811336"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="ba7d6-104">Microsoft-bedreigingsbeveiliging inschakelen</span><span class="sxs-lookup"><span data-stu-id="ba7d6-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="ba7d6-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="ba7d6-105">**Applies to:**</span></span>
- <span data-ttu-id="ba7d6-106">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="ba7d6-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="ba7d6-107">Microsoft Threat Protection maakt uw incidentresponsproces los door belangrijke mogelijkheden te integreren in Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security en Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="ba7d6-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="ba7d6-108">Deze uniforme ervaring voegt krachtige functies toe die u openen in het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="ba7d6-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="ba7d6-109">Om de beste bescherming te krijgen en Microsoft Threat Protection te optimaliseren, raden we u aan alle toepasselijke ondersteunde services in uw netwerk te implementeren.</span><span class="sxs-lookup"><span data-stu-id="ba7d6-109">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="ba7d6-110">Lees voor meer informatie [over het implementeren van ondersteunde services](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="ba7d6-110">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="ba7d6-111">Controleer de geschiktheid en vereiste machtigingen voor licenties</span><span class="sxs-lookup"><span data-stu-id="ba7d6-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="ba7d6-112">Een Microsoft 365 E5-, E5-beveiligings- of A5-licentie of een geldige combinatie van licenties biedt toegang tot ondersteunde services en geeft u het recht om Microsoft Threat Protection te gebruiken in microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="ba7d6-112">A Microsoft 365 E5, E5 Security, or A5 license or a valid combination of licenses provides access to supported services and entitles you to use Microsoft Threat Protection in Microsoft 365 security center.</span></span>

<span data-ttu-id="ba7d6-113">Lees voor gedetailleerde licentiegegevens [de licentievereisten](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="ba7d6-113">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="ba7d6-114">Controleer uw rol</span><span class="sxs-lookup"><span data-stu-id="ba7d6-114">Check your role</span></span>
<span data-ttu-id="ba7d6-115">U moet een **globale beheerder** of een **beveiligingsbeheerder** in Azure Active Directory zijn om Microsoft Threat Protection in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="ba7d6-115">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="ba7d6-116">Uw rollen weergeven in Azure AD</span><span class="sxs-lookup"><span data-stu-id="ba7d6-116">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a><span data-ttu-id="ba7d6-117">De service gebruiken</span><span class="sxs-lookup"><span data-stu-id="ba7d6-117">Start using the service</span></span>
<span data-ttu-id="ba7d6-118">Microsoft Threat Protection verzamelt gegevens van de verschillende geïntegreerde services.</span><span class="sxs-lookup"><span data-stu-id="ba7d6-118">Microsoft Threat Protection aggregates data from the various integrated services.</span></span> <span data-ttu-id="ba7d6-119">Het zal gegevens centraal verwerken en opslaan om nieuwe inzichten te identificeren en gecentraliseerde responsworkflows mogelijk te maken.</span><span class="sxs-lookup"><span data-stu-id="ba7d6-119">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span>

<span data-ttu-id="ba7d6-120">Voordat u de service inschakelt, toont het Microsoft 365-beveiligingscentrum[(security.microsoft.com)](https://security.microsoft.com)de welkomstpagina voor Microsoft Threat Protection wanneer u **Incidenten,** **actiecentrum**of **Jacht** selecteert in het navigatiedeelvenster.</span><span class="sxs-lookup"><span data-stu-id="ba7d6-120">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection welcome page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="ba7d6-121">Deze navigatieopties worden niet weergegeven als u niet in aanmerking komt voor het gebruik van Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="ba7d6-121">These navigation options are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="ba7d6-122">![Afbeelding van de welkomstpagina van Microsoft Threat Protection weergegeven](../../media/mtp-welcome.png)
als Microsoft Threat Protection niet is ingeschakeld op*de welkomstpagina van Microsoft Threat Protection in microsoft 365-beveiligingscentrum*</span><span class="sxs-lookup"><span data-stu-id="ba7d6-122">![Image of the Microsoft Threat Protection welcome page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-welcome.png)
*Microsoft Threat Protection welcome page in Microsoft 365 security center*</span></span>

<span data-ttu-id="ba7d6-123">Als u Microsoft Threat Protection wilt inschakelen, voltooit u het proces eenvoudig vanaf de welkomstpagina.</span><span class="sxs-lookup"><span data-stu-id="ba7d6-123">To turn on Microsoft Threat Protection, simply complete the process from the welcome page.</span></span> <span data-ttu-id="ba7d6-124">U Microsoft Threat Protection ook inschakelen door toegang te krijgen tot **Instellingen** [(security.microsoft.com/settings)](https://security.microsoft.com/settings)in het navigatiedeelvenster en **Microsoft Threat Protection**te selecteren.</span><span class="sxs-lookup"><span data-stu-id="ba7d6-124">You can also turn on Microsoft Threat Protection by accessing **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and selecting **Microsoft Threat Protection**.</span></span>

>[!NOTE]
><span data-ttu-id="ba7d6-125">Als u **Instellingen** niet in het navigatiedeelvenster ziet of geen toegang hebt tot de pagina, controleert u uw machtigingen en licenties.</span><span class="sxs-lookup"><span data-stu-id="ba7d6-125">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="select-data-center-location"></a><span data-ttu-id="ba7d6-126">Datacenterlocatie selecteren</span><span class="sxs-lookup"><span data-stu-id="ba7d6-126">Select data center location</span></span>
<span data-ttu-id="ba7d6-127">Als Microsoft Defender ATP is ingericht voor uw organisatie, worden gegevens opgeslagen en verwerkt op dezelfde datacenterlocatie die u hebt geselecteerd voor [uw Microsoft Defender ATP-gegevens.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="ba7d6-127">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="ba7d6-128">Als u geen Microsoft Defender ATP hebt, wordt u gevraagd om een nieuwe datacenterlocatie te kiezen die specifiek voor Microsoft Threat Protection is bedoeld.</span><span class="sxs-lookup"><span data-stu-id="ba7d6-128">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> 

<span data-ttu-id="ba7d6-129">U moet toestemming geven voordat gegevens worden gedeeld tussen services en samengevoegd.</span><span class="sxs-lookup"><span data-stu-id="ba7d6-129">You need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="ba7d6-130">Controleer of de service is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="ba7d6-130">Confirm that the service is on</span></span>
<span data-ttu-id="ba7d6-131">Zodra de service is ingericht, voegt het:</span><span class="sxs-lookup"><span data-stu-id="ba7d6-131">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="ba7d6-132">Incidentenbeheer</span><span class="sxs-lookup"><span data-stu-id="ba7d6-132">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="ba7d6-133">Een actiecentrum voor het beheren van [geautomatiseerd onderzoek en respons](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="ba7d6-133">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="ba7d6-134">[Geavanceerde jachtmogelijkheden](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ba7d6-134">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="ba7d6-135">![Afbeelding van microsoft 365 security center navigatievenster met Microsoft Threat Protection functies](../../media/mtp-on.png)
Microsoft*365 security center met incidenten beheer en andere Microsoft Threat Protection mogelijkheden*</span><span class="sxs-lookup"><span data-stu-id="ba7d6-135">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="ba7d6-136">Azure ATP-gegevens verkrijgen</span><span class="sxs-lookup"><span data-stu-id="ba7d6-136">Getting Azure ATP data</span></span>
<span data-ttu-id="ba7d6-137">Als u Azure ATP-gegevens wilt delen met Microsoft Threat Protection, moet u ervoor zorgen dat Microsoft Cloud App Security en Azure ATP-integratie zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="ba7d6-137">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="ba7d6-138">Meer informatie over deze integratie</span><span class="sxs-lookup"><span data-stu-id="ba7d6-138">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="ba7d6-139">Microsoft-bedreigingsbeveiliging uitschakelen</span><span class="sxs-lookup"><span data-stu-id="ba7d6-139">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="ba7d6-140">Ga naar **Instellingen** > **voor Microsoft Threat Protection** > **Opt-in / Opt-out** in het Microsoft 365-beveiligingscentrum om te stoppen met het gebruik van Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="ba7d6-140">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="ba7d6-141">Schakel de optie **Microsoft Bedreigingsbeveiliging inschakelen** uit en sla de wijzigingen op.</span><span class="sxs-lookup"><span data-stu-id="ba7d6-141">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="ba7d6-142">De bijbehorende functies worden verwijderd uit het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="ba7d6-142">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="ba7d6-143">Hulp krijgen</span><span class="sxs-lookup"><span data-stu-id="ba7d6-143">Get assistance</span></span>

<span data-ttu-id="ba7d6-144">Microsoft-ondersteuningsmedewerkers kunnen helpen bij het inrichten of deprovisioneren van de service en gerelateerde resources op uw tenant.</span><span class="sxs-lookup"><span data-stu-id="ba7d6-144">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="ba7d6-145">Selecteer Hulp nodig in het Microsoft 365-beveiligingscentrum voor **hulp?**</span><span class="sxs-lookup"><span data-stu-id="ba7d6-145">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="ba7d6-146">Vermeld bij het contact met de ondersteuning Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="ba7d6-146">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ba7d6-147">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="ba7d6-147">Related topics</span></span>

- [<span data-ttu-id="ba7d6-148">Overzicht van Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ba7d6-148">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="ba7d6-149">Licentievereisten en andere vereisten</span><span class="sxs-lookup"><span data-stu-id="ba7d6-149">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="ba7d6-150">Ondersteunde services implementeren</span><span class="sxs-lookup"><span data-stu-id="ba7d6-150">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="ba7d6-151">Microsoft Defender ATP-overzicht</span><span class="sxs-lookup"><span data-stu-id="ba7d6-151">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="ba7d6-152">Office 365 ATP-overzicht</span><span class="sxs-lookup"><span data-stu-id="ba7d6-152">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="ba7d6-153">Overzicht van Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ba7d6-153">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="ba7d6-154">Azure ATP-overzicht</span><span class="sxs-lookup"><span data-stu-id="ba7d6-154">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="ba7d6-155">Microsoft Defender ATP-gegevensopslag</span><span class="sxs-lookup"><span data-stu-id="ba7d6-155">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
