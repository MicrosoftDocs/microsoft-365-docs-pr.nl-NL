---
title: Schakel Microsoft 365 Defender in in het Microsoft 365-beveiligingscentrum
description: Meer informatie over het inschakelen van Microsoft 365 Defender en het integreren van uw beveiligingsincident en -reactie.
keywords: aan de slag, schakel MTP, Microsoft Threat Protection, M365, beveiliging, gegevenslocatie, vereiste machtigingen, geschiktheid voor licenties, instellingenpagina
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 19f035a271626077911b05082a4aba6d67355cdb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930220"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="8dbac-104">Microsoft 365 Defender in te zetten</span><span class="sxs-lookup"><span data-stu-id="8dbac-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8dbac-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8dbac-105">**Applies to:**</span></span>
- <span data-ttu-id="8dbac-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8dbac-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="8dbac-107">[Microsoft 365 Defender](microsoft-threat-protection.md) defificeert uw incidentreactieproces door belangrijke mogelijkheden te integreren tussen Microsoft Defender voor eindpunt, Microsoft Defender voor Office 365, Microsoft Cloud App-beveiliging en Microsoft Defender voor identiteit.</span><span class="sxs-lookup"><span data-stu-id="8dbac-107">[Microsoft 365 Defender](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="8dbac-108">Deze geïntegreerde ervaring biedt krachtige functies die u kunt openen in het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="8dbac-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="8dbac-109">Microsoft 365 Defender wordt automatisch in schakelt wanneer in aanmerking komende klanten met de vereiste machtigingen naar het Microsoft 365-beveiligingscentrum gaan.</span><span class="sxs-lookup"><span data-stu-id="8dbac-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="8dbac-110">Lees dit artikel voor meer informatie over verschillende vereisten en hoe Microsoft 365 Defender wordt ingericht.</span><span class="sxs-lookup"><span data-stu-id="8dbac-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="8dbac-111">Controleer of de licentie in aanmerking komt en de vereiste machtigingen</span><span class="sxs-lookup"><span data-stu-id="8dbac-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="8dbac-112">Een licentie voor een Microsoft 365-beveiligingsproduct biedt u in het algemeen een recht om Microsoft 365 Defender te gebruiken in het Microsoft 365-beveiligingscentrum zonder extra licentiekosten.</span><span class="sxs-lookup"><span data-stu-id="8dbac-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="8dbac-113">We raden u aan een beveiligingslicentie voor Microsoft 365 E5, E5, A5 of A5 te verkrijgen of een geldige combinatie van licenties die toegang biedt tot alle ondersteunde services.</span><span class="sxs-lookup"><span data-stu-id="8dbac-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="8dbac-114">Lees de licentievereisten voor [meer informatie over licenties.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="8dbac-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="8dbac-115">Controleer uw rol</span><span class="sxs-lookup"><span data-stu-id="8dbac-115">Check your role</span></span>

<span data-ttu-id="8dbac-116">U moet een globale beheerder **of** beveiligingsbeheerder **in** Azure Active Directory zijn om Microsoft 365 Defender in te zetten.</span><span class="sxs-lookup"><span data-stu-id="8dbac-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="8dbac-117">Uw rollen weergeven in Azure AD</span><span class="sxs-lookup"><span data-stu-id="8dbac-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="8dbac-118">Ondersteunde services</span><span class="sxs-lookup"><span data-stu-id="8dbac-118">Supported services</span></span>

<span data-ttu-id="8dbac-119">Microsoft 365 Defender verzamelt gegevens uit de verschillende ondersteunde services die u al hebt geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="8dbac-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="8dbac-120">Gegevens worden centraal verwerkt en opgeslagen om nieuwe inzichten te identificeren en gecentraliseerde antwoordwerkstromen mogelijk te maken.</span><span class="sxs-lookup"><span data-stu-id="8dbac-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="8dbac-121">Dit gebeurt zonder dat dit van invloed is op bestaande implementaties, instellingen of gegevens die zijn gekoppeld aan de geïntegreerde services.</span><span class="sxs-lookup"><span data-stu-id="8dbac-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="8dbac-122">Voor de beste bescherming en optimaliseren van Microsoft 365 Defender, raden we u aan alle toepasselijke ondersteunde services op uw netwerk te implementeren.</span><span class="sxs-lookup"><span data-stu-id="8dbac-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="8dbac-123">Lees meer over het [implementeren van ondersteunde services.](deploy-supported-services.md)</span><span class="sxs-lookup"><span data-stu-id="8dbac-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="8dbac-124">Voordat u de service start</span><span class="sxs-lookup"><span data-stu-id="8dbac-124">Before starting the service</span></span>

<span data-ttu-id="8dbac-125">Voordat u de service in dienst gaat, wordt in het Microsoft 365-beveiligingscentrum [(security.microsoft.com)](https://security.microsoft.com)de pagina met  Microsoft 365 Defender-instellingen weergegeven wanneer u **Incidenten,** Actiecentrum of Zoeken selecteert in het navigatiedeelvenster.</span><span class="sxs-lookup"><span data-stu-id="8dbac-125">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft 365 Defender settings page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="8dbac-126">Deze navigatie-items worden niet weergegeven als u niet in aanmerking komt voor het gebruik van Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="8dbac-126">These navigation items are not shown if you are not eligible to use Microsoft 365 Defender.</span></span>

<span data-ttu-id="8dbac-127">![Afbeelding van de pagina met microsoft 365 Defender-instellingen die wordt weergegeven als Microsoft 365 Defender geen Microsoft 365 Defender-instellingen heeft ingeschakeld in het ](../../media/mtp-enable/mtp-settings.png)
 *Microsoft 365-beveiligingscentrum*</span><span class="sxs-lookup"><span data-stu-id="8dbac-127">![Image of the Microsoft 365 Defender settings page shown if Microsoft 365 Defender has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft 365 Defender settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="8dbac-128">De service starten</span><span class="sxs-lookup"><span data-stu-id="8dbac-128">Starting the service</span></span>

<span data-ttu-id="8dbac-129">Als u Microsoft 365 Defender wilt in turnen, selecteert u **Microsoft 365 Defender** in te zetten en de wijziging toe te passen.</span><span class="sxs-lookup"><span data-stu-id="8dbac-129">To turn on Microsoft 365 Defender, simply select **Turn on Microsoft 365 Defender** and apply the change.</span></span> <span data-ttu-id="8dbac-130">U kunt deze optie ook openen door **Instellingen** [(security.microsoft.com/settings)](https://security.microsoft.com/settings)te selecteren in het navigatiedeelvenster en vervolgens **Microsoft 365 Defender te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="8dbac-130">You can also access this option by selecting **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft 365 Defender**.</span></span>

> [!NOTE]
> <span data-ttu-id="8dbac-131">Als u Instellingen niet ziet in **het** navigatiedeelvenster of als u de pagina niet kunt openen, controleert u uw machtigingen en licenties.</span><span class="sxs-lookup"><span data-stu-id="8dbac-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="8dbac-132">Locatie van datacenter</span><span class="sxs-lookup"><span data-stu-id="8dbac-132">Data center location</span></span>

<span data-ttu-id="8dbac-133">Microsoft 365 Defender zal gegevens opslaan en verwerken op dezelfde locatie die door [Microsoft Defender voor Eindpunt wordt gebruikt.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="8dbac-133">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="8dbac-134">Als u microsoft Defender voor eindpunt niet hebt, wordt automatisch een nieuwe locatie van het datacenter geselecteerd op basis van de locatie van actieve beveiligingsservices van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8dbac-134">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="8dbac-135">De geselecteerde locatie van het datacenter wordt weergegeven op het scherm.</span><span class="sxs-lookup"><span data-stu-id="8dbac-135">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="8dbac-136">Selecteer **Hulp nodig?** In het Microsoft 365-beveiligingscentrum kunt u contact opnemen met Microsoft Ondersteuning over de inrichting van Microsoft 365 Defender op een andere locatie in het datacenter.</span><span class="sxs-lookup"><span data-stu-id="8dbac-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="8dbac-137">Microsoft Defender voor eindpunt richt automatisch voorzieningen in datacenters van de Europese Unie (EU) indien ingeschakeld via Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="8dbac-137">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="8dbac-138">Microsoft 365 Defender wordt automatisch ingericht in hetzelfde EU-datacenter voor klanten die Defender voor eindpunt op deze manier hebben ingericht.</span><span class="sxs-lookup"><span data-stu-id="8dbac-138">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="8dbac-139">Controleer of de service is</span><span class="sxs-lookup"><span data-stu-id="8dbac-139">Confirm that the service is on</span></span>

<span data-ttu-id="8dbac-140">Nadat de service is ingericht, wordt het volgende toegevoegd:</span><span class="sxs-lookup"><span data-stu-id="8dbac-140">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="8dbac-141">Incidentenbeheer</span><span class="sxs-lookup"><span data-stu-id="8dbac-141">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="8dbac-142">Een actiecentrum voor het beheren [van automatisch onderzoek en antwoorden](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="8dbac-142">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="8dbac-143">[Geavanceerde mogelijkheden voor](advanced-hunting-overview.md) zoeken</span><span class="sxs-lookup"><span data-stu-id="8dbac-143">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="8dbac-144">![Afbeelding van navigatiedeelvenster van het Microsoft 365-beveiligingscentrum met Microsoft 365 Defender-functies Microsoft 365-beveiligingscentrum met beheer van incidenten en andere mogelijkheden van ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365 Defender*</span><span class="sxs-lookup"><span data-stu-id="8dbac-144">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="8dbac-145">Microsoft Defender voor identiteitsgegevens verkrijgen</span><span class="sxs-lookup"><span data-stu-id="8dbac-145">Getting Microsoft Defender for Identity data</span></span>

<span data-ttu-id="8dbac-146">Als u Microsoft Defender voor identiteitsgegevens wilt delen met Microsoft 365 Defender, moet Microsoft Cloud App Security en Microsoft Defender voor identiteitsintegratie zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8dbac-146">To share Microsoft Defender for Identity data with Microsoft 365 Defender, ensure that Microsoft Cloud App Security and Microsoft Defender for Identity integration is turned on.</span></span> <span data-ttu-id="8dbac-147">[Meer informatie over deze integratie.](https://docs.microsoft.com/cloud-app-security/mdi-integration)</span><span class="sxs-lookup"><span data-stu-id="8dbac-147">[Learn more about this integration](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span></span>

## <a name="get-assistance"></a><span data-ttu-id="8dbac-148">Ondersteuning krijgen</span><span class="sxs-lookup"><span data-stu-id="8dbac-148">Get assistance</span></span>

<span data-ttu-id="8dbac-149">Lees de veelgestelde vragen voor antwoorden op de meest gestelde vragen over het in- en uitschakelen [van](mtp-enable-faq.md)Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="8dbac-149">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="8dbac-150">Microsoft-ondersteuningsmedewerkers kunnen u helpen bij het inrichten of de inrichting van de service en gerelateerde resources in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="8dbac-150">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="8dbac-151">Selecteer Hulp nodig in **het** Microsoft 365-beveiligingscentrum voor hulp.</span><span class="sxs-lookup"><span data-stu-id="8dbac-151">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="8dbac-152">Als u contact op kunt nemen met ondersteuning, vermeldt u Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="8dbac-152">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8dbac-153">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="8dbac-153">Related topics</span></span>

- [<span data-ttu-id="8dbac-154">Veelgestelde vragen</span><span class="sxs-lookup"><span data-stu-id="8dbac-154">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="8dbac-155">Licentievereisten en andere vereisten</span><span class="sxs-lookup"><span data-stu-id="8dbac-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="8dbac-156">Ondersteunde services implementeren</span><span class="sxs-lookup"><span data-stu-id="8dbac-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="8dbac-157">Overzicht van Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8dbac-157">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="8dbac-158">Overzicht van Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="8dbac-158">Microsoft Defender for Endpoint overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="8dbac-159">Overzicht van Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="8dbac-159">Defender for Office 365 overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="8dbac-160">Overzicht van beveiliging van Microsoft Cloud-apps</span><span class="sxs-lookup"><span data-stu-id="8dbac-160">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="8dbac-161">Overzicht van Microsoft Defender voor identiteit</span><span class="sxs-lookup"><span data-stu-id="8dbac-161">Microsoft Defender for Identity overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="8dbac-162">Gegevensopslag met Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="8dbac-162">Microsoft Defender for Endpoint data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
