---
title: Microsoft 365 Defender in het Microsoft 365-beveiligingscentrum in-
description: Meer informatie over het inschakelen van Microsoft 365 Defender en het integreren van uw beveiligingsincident en antwoord.
keywords: aan de slag, MTP inschakelen, Microsoft Threat Protection, M365, beveiliging, gegevenslocatie, vereiste machtigingen, licentie in aanmerking komen, instellingenpagina
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
ms.openlocfilehash: 18564b2a5a47b2cf4a8bbd94a3e3a315c8f269ec
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51200255"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="c81f2-104">Microsoft 365 Defender in-</span><span class="sxs-lookup"><span data-stu-id="c81f2-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c81f2-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c81f2-105">**Applies to:**</span></span>
- <span data-ttu-id="c81f2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c81f2-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c81f2-107">[Microsoft 365 Defender](microsoft-365-defender.md) maakt het reactieproces voor incidenten los door belangrijke mogelijkheden te integreren in Microsoft Defender voor Eindpunt, Microsoft Defender voor Office 365, Microsoft Cloud App Security en Microsoft Defender voor identiteit.</span><span class="sxs-lookup"><span data-stu-id="c81f2-107">[Microsoft 365 Defender](microsoft-365-defender.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="c81f2-108">Deze geïntegreerde ervaring voegt krachtige functies toe die u kunt openen in het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="c81f2-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="c81f2-109">Microsoft 365 Defender schakelt automatisch in wanneer in aanmerking komende klanten met de vereiste machtigingen naar het Microsoft 365-beveiligingscentrum gaan.</span><span class="sxs-lookup"><span data-stu-id="c81f2-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="c81f2-110">Lees dit artikel voor meer informatie over verschillende vereisten en hoe Microsoft 365 Defender is ingericht.</span><span class="sxs-lookup"><span data-stu-id="c81f2-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="c81f2-111">Controleer de geschiktheid van licenties en vereiste machtigingen</span><span class="sxs-lookup"><span data-stu-id="c81f2-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="c81f2-112">Een licentie voor een Microsoft 365-beveiligingsproduct geeft u over het algemeen het recht microsoft 365 Defender te gebruiken in het Microsoft 365-beveiligingscentrum zonder extra licentiekosten.</span><span class="sxs-lookup"><span data-stu-id="c81f2-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="c81f2-113">We raden u aan een microsoft 365 E5-, E5-beveiligings-, A5- of A5-beveiligingslicentie te krijgen of een geldige combinatie van licenties die toegang biedt tot alle ondersteunde services.</span><span class="sxs-lookup"><span data-stu-id="c81f2-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="c81f2-114">Lees de licentievereisten voor [gedetailleerde licentiegegevens.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="c81f2-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="c81f2-115">Uw rol controleren</span><span class="sxs-lookup"><span data-stu-id="c81f2-115">Check your role</span></span>

<span data-ttu-id="c81f2-116">U moet een globale beheerder **of** beveiligingsbeheerder **zijn** in Azure Active Directory om Microsoft 365 Defender in te zetten.</span><span class="sxs-lookup"><span data-stu-id="c81f2-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="c81f2-117">Uw rollen weergeven in Azure AD</span><span class="sxs-lookup"><span data-stu-id="c81f2-117">View your roles in Azure AD</span></span>](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="c81f2-118">Ondersteunde services</span><span class="sxs-lookup"><span data-stu-id="c81f2-118">Supported services</span></span>

<span data-ttu-id="c81f2-119">Microsoft 365 Defender verzamelt gegevens van de verschillende ondersteunde services die u al hebt geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="c81f2-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="c81f2-120">Er worden gegevens centraal verwerkt en opgeslagen om nieuwe inzichten te identificeren en gecentraliseerde antwoordwerkstromen mogelijk te maken.</span><span class="sxs-lookup"><span data-stu-id="c81f2-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="c81f2-121">Dit doet het zonder dat dit gevolgen heeft voor bestaande implementaties, instellingen of gegevens die zijn gekoppeld aan de geïntegreerde services.</span><span class="sxs-lookup"><span data-stu-id="c81f2-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="c81f2-122">Voor de beste beveiliging en het optimaliseren van Microsoft 365 Defender raden we u aan alle van toepassing zijnde ondersteunde services op uw netwerk te implementeren.</span><span class="sxs-lookup"><span data-stu-id="c81f2-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="c81f2-123">Lees voor meer informatie [over het implementeren van ondersteunde services.](deploy-supported-services.md)</span><span class="sxs-lookup"><span data-stu-id="c81f2-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="onboard-to-the-service"></a><span data-ttu-id="c81f2-124">Aan boord van de service</span><span class="sxs-lookup"><span data-stu-id="c81f2-124">Onboard to the service</span></span>
<span data-ttu-id="c81f2-125">Onboarding naar Microsoft 365 Defender is eenvoudig.</span><span class="sxs-lookup"><span data-stu-id="c81f2-125">Onboarding to Microsoft 365 Defender is simple.</span></span> <span data-ttu-id="c81f2-126">Selecteer in het navigatiemenu een item onder de sectie Eindpunten, zoals Incidenten, Jagen, Actiecentrum of Bedreigingsanalyse om het onboardingproces te starten.</span><span class="sxs-lookup"><span data-stu-id="c81f2-126">From the navigation menu, select any item under the Endpoints section, such as Incidents, Hunting, Action center, or Threat analytics to initiate the onboarding process.</span></span> 

### <a name="data-center-location"></a><span data-ttu-id="c81f2-127">Locatie van datacenter</span><span class="sxs-lookup"><span data-stu-id="c81f2-127">Data center location</span></span>

<span data-ttu-id="c81f2-128">Microsoft 365 Defender zal gegevens opslaan en verwerken op dezelfde locatie die [door Microsoft Defender voor Eindpunt wordt gebruikt.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="c81f2-128">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="c81f2-129">Als u geen Microsoft Defender voor Eindpunt hebt, wordt automatisch een nieuwe datacenterlocatie geselecteerd op basis van de locatie van actieve Microsoft 365-beveiligingsservices.</span><span class="sxs-lookup"><span data-stu-id="c81f2-129">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="c81f2-130">De geselecteerde locatie van het datacenter wordt weergegeven in het scherm.</span><span class="sxs-lookup"><span data-stu-id="c81f2-130">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="c81f2-131">Selecteer **Hulp nodig?** in het Microsoft 365-beveiligingscentrum om contact op te nemen met microsoft-ondersteuning over het inrichten van Microsoft 365 Defender op een andere datacenterlocatie.</span><span class="sxs-lookup"><span data-stu-id="c81f2-131">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="c81f2-132">Microsoft Defender voor Eindpunt biedt automatisch voorzieningen in datacenters van de Europese Unie (EU) wanneer deze zijn ingeschakeld via Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="c81f2-132">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="c81f2-133">Microsoft 365 Defender wordt automatisch ingericht in hetzelfde EU-datacenter voor klanten die Defender op deze manier voor Eindpunt hebben ingericht.</span><span class="sxs-lookup"><span data-stu-id="c81f2-133">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="c81f2-134">Controleren of de service is aan</span><span class="sxs-lookup"><span data-stu-id="c81f2-134">Confirm that the service is on</span></span>

<span data-ttu-id="c81f2-135">Wanneer de service is ingericht, wordt het volgende toegevoegd:</span><span class="sxs-lookup"><span data-stu-id="c81f2-135">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="c81f2-136">Incidentenbeheer</span><span class="sxs-lookup"><span data-stu-id="c81f2-136">Incidents management</span></span>](incidents-overview.md)
- [<span data-ttu-id="c81f2-137">Waarschuwingenwachtrij</span><span class="sxs-lookup"><span data-stu-id="c81f2-137">Alerts queue</span></span>](investigate-alerts.md)
- <span data-ttu-id="c81f2-138">Een actiecentrum voor het beheren [van geautomatiseerd onderzoek en antwoord](m365d-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="c81f2-138">An action center for managing [automated investigation and response](m365d-autoir.md)</span></span>
- <span data-ttu-id="c81f2-139">[Geavanceerde mogelijkheden voor](advanced-hunting-overview.md) jagen</span><span class="sxs-lookup"><span data-stu-id="c81f2-139">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>
- <span data-ttu-id="c81f2-140">Dreigingsanalyse</span><span class="sxs-lookup"><span data-stu-id="c81f2-140">Threat analytics</span></span>

<span data-ttu-id="c81f2-141">![Afbeelding van het navigatiedeelvenster van het Microsoft 365-beveiligingscentrum met Microsoft 365 Defender bevat Microsoft 365-beveiligingscentrum met incidentenbeheer en andere ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365 Defender-mogelijkheden*</span><span class="sxs-lookup"><span data-stu-id="c81f2-141">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="c81f2-142">Microsoft Defender voor identiteitsgegevens verkrijgen</span><span class="sxs-lookup"><span data-stu-id="c81f2-142">Getting Microsoft Defender for Identity data</span></span> 
<span data-ttu-id="c81f2-143">Als u de integratie met Microsoft Cloud App Security wilt inschakelen, moet u zich ten minste eenmaal aanmelden bij de Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="c81f2-143">To enable the integration with Microsoft Cloud App Security, you'll need to login to the Microsoft Cloud App Security at least once.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="c81f2-144">Hulp krijgen</span><span class="sxs-lookup"><span data-stu-id="c81f2-144">Get assistance</span></span>

<span data-ttu-id="c81f2-145">Als u antwoorden wilt op de meestgestelde vragen over het in- en uitschakelen van Microsoft 365 Defender, leest u [de veelgestelde vragen.](m365d-enable-faq.md)</span><span class="sxs-lookup"><span data-stu-id="c81f2-145">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](m365d-enable-faq.md).</span></span>

<span data-ttu-id="c81f2-146">Microsoft-ondersteuningsmedewerkers kunnen helpen bij het inrichten of deprovisie van de service en gerelateerde resources op uw tenant.</span><span class="sxs-lookup"><span data-stu-id="c81f2-146">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="c81f2-147">Selecteer Hulp nodig **in** het Microsoft 365-beveiligingscentrum voor hulp.</span><span class="sxs-lookup"><span data-stu-id="c81f2-147">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="c81f2-148">Vermeld Microsoft 365 Defender wanneer u contact op gaat met de ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="c81f2-148">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c81f2-149">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="c81f2-149">Related topics</span></span>

- [<span data-ttu-id="c81f2-150">Veelgestelde vragen</span><span class="sxs-lookup"><span data-stu-id="c81f2-150">Frequently asked questions</span></span>](m365d-enable-faq.md)
- [<span data-ttu-id="c81f2-151">Licentievereisten en andere vereisten</span><span class="sxs-lookup"><span data-stu-id="c81f2-151">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="c81f2-152">Ondersteunde services implementeren</span><span class="sxs-lookup"><span data-stu-id="c81f2-152">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="c81f2-153">Overzicht van Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c81f2-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="c81f2-154">Overzicht van Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="c81f2-154">Microsoft Defender for Endpoint overview</span></span>](../defender-endpoint/microsoft-defender-endpoint.md)
- [<span data-ttu-id="c81f2-155">Overzicht van Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="c81f2-155">Defender for Office 365 overview</span></span>](../office-365-security/defender-for-office-365.md)
- [<span data-ttu-id="c81f2-156">Overzicht van Microsoft Cloud App-beveiliging</span><span class="sxs-lookup"><span data-stu-id="c81f2-156">Microsoft Cloud App Security overview</span></span>](/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="c81f2-157">Overzicht van Microsoft Defender voor identiteit</span><span class="sxs-lookup"><span data-stu-id="c81f2-157">Microsoft Defender for Identity overview</span></span>](/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="c81f2-158">Microsoft Defender voor endpoint-gegevensopslag</span><span class="sxs-lookup"><span data-stu-id="c81f2-158">Microsoft Defender for Endpoint data storage</span></span>](../defender-endpoint/data-storage-privacy.md)
