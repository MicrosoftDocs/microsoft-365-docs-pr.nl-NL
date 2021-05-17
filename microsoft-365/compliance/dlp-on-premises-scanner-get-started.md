---
title: Aan de slag met de Microsoft 365 preventie van gegevensverlies on-premises scanner (preview)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Stel Microsoft 365 preventie van gegevensverlies on-premises scanner
ms.openlocfilehash: 242956a3c6469756481fb823340e715a210562af
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162911"
---
# <a name="get-started-with-the-data-loss-prevention-on-premises-scanner-preview"></a><span data-ttu-id="3edc8-103">Aan de slag met de preventie van gegevensverlies on-premises scanner (preview)</span><span class="sxs-lookup"><span data-stu-id="3edc8-103">Get started with the data loss prevention on-premises scanner (preview)</span></span>

<span data-ttu-id="3edc8-104">In dit artikel worden de vereisten en configuratie voor de on-premises scanner voor preventie van gegevensverlies van Microsoft 365 beschreven.</span><span class="sxs-lookup"><span data-stu-id="3edc8-104">This article walks you through the prerequisites and configuration for the Microsoft 365 data loss prevention on-premises scanner.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="3edc8-105">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="3edc8-105">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="3edc8-106">SKU/abonnementenlicenties</span><span class="sxs-lookup"><span data-stu-id="3edc8-106">SKU/subscriptions licensing</span></span>

<span data-ttu-id="3edc8-107">Voordat u aan de slag gaat met DLP on-premises scanner, moet u uw [abonnement op Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) en eventuele invoegtoepassingen bevestigen.</span><span class="sxs-lookup"><span data-stu-id="3edc8-107">Before you get started with DLP on-premises scanner, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="3edc8-108">Als u wilt deelnemen aan de preview-versie, moet aan het beheerdersaccount waarin de DLP-regels worden gemaakt, een van de volgende licenties worden toegewezen:</span><span class="sxs-lookup"><span data-stu-id="3edc8-108">To participate in the preview the admin account that sets up the DLP rules must be assigned one of the following licenses:</span></span>

- <span data-ttu-id="3edc8-109">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="3edc8-109">Microsoft 365 E5</span></span>
- <span data-ttu-id="3edc8-110">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="3edc8-110">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="3edc8-111">Microsoft 365 E5 Information Protection & Governance</span><span class="sxs-lookup"><span data-stu-id="3edc8-111">Microsoft 365 E5 Information Protection & Governance</span></span> 


<span data-ttu-id="3edc8-112">Zie [Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) voor volledige details over licenties</span><span class="sxs-lookup"><span data-stu-id="3edc8-112">For full licensing details see: [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)</span></span>

### <a name="permissions"></a><span data-ttu-id="3edc8-113">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="3edc8-113">Permissions</span></span>


<span data-ttu-id="3edc8-114">Gegevens van DL -on-premises scanners kunnen worden weergegeven in [Activity Explorer](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="3edc8-114">Data from DLP on-premises scanner can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="3edc8-115">Er zijn vier rollen die machtigingen verlenen aan Activiteitenverkenner. Het account dat u gebruikt voor het openen van de gegevens, moet lid zijn van een van deze rollen.</span><span class="sxs-lookup"><span data-stu-id="3edc8-115">There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="3edc8-116">Globale beheerder</span><span class="sxs-lookup"><span data-stu-id="3edc8-116">Global administrator</span></span>
- <span data-ttu-id="3edc8-117">Beheerder voor naleving</span><span class="sxs-lookup"><span data-stu-id="3edc8-117">Compliance administrator</span></span>
- <span data-ttu-id="3edc8-118">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="3edc8-118">Security administrator</span></span>
- <span data-ttu-id="3edc8-119">Beheerder van nalevingsgegevens</span><span class="sxs-lookup"><span data-stu-id="3edc8-119">Compliance data administrator</span></span>

### <a name="dlp-on-premises-scanner-prerequisites"></a><span data-ttu-id="3edc8-120">Vereisten van on-premises DLP-scanner</span><span class="sxs-lookup"><span data-stu-id="3edc8-120">DLP on-premises scanner prerequisites</span></span>

- <span data-ttu-id="3edc8-121">De AIP-scanner (Azure Information Protection) implementeert de DLP-beleidsaanpassing en het afdwingen van beleid.</span><span class="sxs-lookup"><span data-stu-id="3edc8-121">The Azure Information Protection (AIP) scanner implements DLP policy matching and policy enforcement.</span></span> <span data-ttu-id="3edc8-122">De scanner is geïnstalleerd als onderdeel van de AIP-client, zodat uw installatie moet voldoen aan alle vereisten voor AIP, de AIP-client en de geïntegreerde labelingsscanner AIP.</span><span class="sxs-lookup"><span data-stu-id="3edc8-122">The scanner is installed as part of the AIP client so your installation must meet all the prerequisites  for AIP, the AIP client, and the AIP unified labeling scanner.</span></span>
- <span data-ttu-id="3edc8-123">Implementeer de AIP-client en -scanner.</span><span class="sxs-lookup"><span data-stu-id="3edc8-123">Deploy the AIP  client and scanner.</span></span> <span data-ttu-id="3edc8-124">[Installeer de geïntegreerde AIP-labelingclient](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) en [], en raadpleeg [Configureren en installeren van de geïntegreerde labelscanner van Azure Information Protection](/azure/information-protection/deploy-aip-scanner-configure-install) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3edc8-124">For more information [Install the AIP unified labeling client](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) and [], see [Configuring and installing the Azure Information Protection unified labeling scanner](/azure/information-protection/deploy-aip-scanner-configure-install).</span></span>
- <span data-ttu-id="3edc8-125">Er moet ten minste één label en beleid in de tenant zijn gepubliceerd, zelfs als alle detectieregels alleen zijn gebaseerd op vertrouwelijke informatietypen.</span><span class="sxs-lookup"><span data-stu-id="3edc8-125">There must be at least one label and policy published in the tenant, even if all your detection rules are based on sensitive information types only.</span></span>

## <a name="deploy-the-dlp-on-premises-scanner"></a><span data-ttu-id="3edc8-126">Implementeer de DLP on-premises scanner</span><span class="sxs-lookup"><span data-stu-id="3edc8-126">Deploy the DLP on-premises scanner</span></span>

1. <span data-ttu-id="3edc8-127">Volg de procedures in [AIP-client voor geïntegreerde labeling installeren](/azure/information-protection/rms-client/install-unifiedlabelingclient-app).</span><span class="sxs-lookup"><span data-stu-id="3edc8-127">Follow the procedures in [Install the AIP unified labeling client](/azure/information-protection/rms-client/install-unifiedlabelingclient-app).</span></span> 
2. <span data-ttu-id="3edc8-128">Volg de procedures in [Configureren en installeren van de geïntegreerde labelscanner van Azure Information Protection](/azure/information-protection/deploy-aip-scanner-configure-install) om de installatie van de scanner te voltooien.</span><span class="sxs-lookup"><span data-stu-id="3edc8-128">Follow the procedures in [Configuring and installing the Azure Information Protection unified labeling scanner](/azure/information-protection/deploy-aip-scanner-configure-install) to complete the scanner installation.</span></span>
    1. <span data-ttu-id="3edc8-129">Configuratie van netwerkdetectietaken is een optionele stap.</span><span class="sxs-lookup"><span data-stu-id="3edc8-129">Network discovery jobs configuration is an optional step.</span></span> <span data-ttu-id="3edc8-130">U kunt dit overslaan en specifieke opslagplaatsen definiëren die moeten worden gescand in uw inhoudsscan.</span><span class="sxs-lookup"><span data-stu-id="3edc8-130">You can skip it and define specific repositories to be scanned in your content scan job.</span></span>
    2. <span data-ttu-id="3edc8-131">U moet een inhoudsscantaak maken en de opslagplaatsen opgeven die als host dienen voor de bestanden die door de DLP-engine moeten worden geëvalueerd.</span><span class="sxs-lookup"><span data-stu-id="3edc8-131">You must create content scan job and specify the repositories that host files that need to be evaluated by the DLP engine.</span></span>
    3. <span data-ttu-id="3edc8-132">Schakel DLP-regels in voor de gemaakte inhoudsscan of stel de optie **Afdwingen** in op **Uit**, tenzij u rechtstreeks wilt doorgaan naar de fase van het afdwingen van DLP.</span><span class="sxs-lookup"><span data-stu-id="3edc8-132">Enable DLP rules in the created Content scan job, and set the **Enforce** option to **Off**, unless you want to proceed directly to the DLP enforcement stage.</span></span>
3. <span data-ttu-id="3edc8-133">Controleer of de taak voor de inhoudsscan aan het juiste cluster is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="3edc8-133">Verify that you content scan job is assigned to the right cluster.</span></span> <span data-ttu-id="3edc8-134">Als u nog steeds geen inhoudsscan hebt gemaakt, maakt u een nieuwe taak en wijst u deze toe aan het cluster met de scannerknooppunten die de openbare preview-versie uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="3edc8-134">If you still did not create a content scan job create a new one and assign it to the cluster that contains the scanner nodes that run the public preview version.</span></span>

4. <span data-ttu-id="3edc8-135">Maak verbinding met de [Azure Information Protection-extensie in het Azure-portaal](https://portal.azure.com/#blade/Microsoft_Azure_InformationProtection/DataClassGroupEditBlade/scannerProfilesBlade) en voeg uw opslagplaatsen toe aan de inhoudsscantaak die de scan gaat uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="3edc8-135">Connect to the [Azure Information Protection extension in Azure portal](https://portal.azure.com/#blade/Microsoft_Azure_InformationProtection/DataClassGroupEditBlade/scannerProfilesBlade) and add your repositories to the content scan job that will perform the scan.</span></span>

5. <span data-ttu-id="3edc8-136">Voer een van de volgende handelingen uit als u een scan wilt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="3edc8-136">Do one of the following to run your scan:</span></span>
    1. <span data-ttu-id="3edc8-137">het scannerschema instellen</span><span class="sxs-lookup"><span data-stu-id="3edc8-137">set the scanner schedule</span></span>
    1. <span data-ttu-id="3edc8-138">de optie **Nu scannen** in de handleiding in het portaal gebruiken</span><span class="sxs-lookup"><span data-stu-id="3edc8-138">use the manual **Scan Now** option in the portal</span></span>
    1. <span data-ttu-id="3edc8-139">of **Start-AIPScan** PowerShell-cmdlet uitvoeren</span><span class="sxs-lookup"><span data-stu-id="3edc8-139">or run **Start-AIPScan** PowerShell cmdlet</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="3edc8-140">De scanner voert standaard een deltascan van de opslagplaats uit en de bestanden die al zijn gescand in de vorige scancyclus, worden overgeslagen tenzij het bestand is gewijzigd, of indien u een volledige scan hebt gestart.</span><span class="sxs-lookup"><span data-stu-id="3edc8-140">Remember that the scanner runs a delta scan of the repository by default and the files that were already scanned in the previous scan cycle will be skipped unless the file was changed or you initiated a full rescan.</span></span> <span data-ttu-id="3edc8-141">Volledige herscan kan worden gestart met de optie **Alle bestanden opnieuw scannen** in de gebruikersinterface of door **Start-AIPScan-Reset** uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="3edc8-141">Full rescan can be initiated by using **Rescan all files** option in the UI or by running **Start-AIPScan-Reset**.</span></span>

6.  <span data-ttu-id="3edc8-142">Ga in het Microsoft 365-compliancecentrum naar de pagina [Preventie van gegevensverlies](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="3edc8-142">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) in the Microsoft 365 Compliance center.</span></span>

7. <span data-ttu-id="3edc8-143">Kies **Beleid maken** en maak een DLP-testbeleid.</span><span class="sxs-lookup"><span data-stu-id="3edc8-143">Choose **Create policy** and create a test DLP policy.</span></span> <span data-ttu-id="3edc8-144">Zie [een DLP-beleid maken op basis van een sjabloon](create-a-dlp-policy-from-a-template.md) als u hulp nodig hebt bij het maken van een beleid.</span><span class="sxs-lookup"><span data-stu-id="3edc8-144">See [Create a DLP policy from a template](create-a-dlp-policy-from-a-template.md) if you need help creating a policy.</span></span> <span data-ttu-id="3edc8-145">Voer de test uit totdat u vertrouwd bent met deze functie.</span><span class="sxs-lookup"><span data-stu-id="3edc8-145">Be sure to run it in test until you are comfortable with this feature.</span></span> <span data-ttu-id="3edc8-146">Gebruik deze parameters voor uw beleid:</span><span class="sxs-lookup"><span data-stu-id="3edc8-146">Use these parameters for your policy:</span></span>
    1. <span data-ttu-id="3edc8-147">Breid het vereik van de DLP-regel voor on-premises scanners zo nodig uit naar specifieke locaties.</span><span class="sxs-lookup"><span data-stu-id="3edc8-147">Scope the DLP on-premises scanner rule to specific locations if needed.</span></span> <span data-ttu-id="3edc8-148">Als u het bereik **locaties** beperkt tot **Alle**, worden alle bestanden die met de scanner worden gescand, onderworpen aan de DLP-regelaanpassing en -afdwinging.</span><span class="sxs-lookup"><span data-stu-id="3edc8-148">If you scope **locations** to **All**, all files scanned by the scanner will be subject to the DLP rule matching and enforcement.</span></span>
    1. <span data-ttu-id="3edc8-149">Wanneer u de locaties opgeeft, kunt u een uitsluitings- of inclusielijst gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3edc8-149">When specifying the locations, you can use either exclusion or inclusion list.</span></span> <span data-ttu-id="3edc8-150">Tijdens een openbare preview kunt u ze niet beide instellen.</span><span class="sxs-lookup"><span data-stu-id="3edc8-150">During public preview you cannot set both of them.</span></span> <span data-ttu-id="3edc8-151">U kunt definiëren dat de regel alleen relevant is voor paden die overeenkomen met een van de vermelde patronen in de inclusielijst of, alle bestanden, behalve de bestanden die overeenkomen met het patroon dat wordt weergegeven in de inclusielijst.</span><span class="sxs-lookup"><span data-stu-id="3edc8-151">You can either define that the rule is relevant only to paths matching one of the patterns listed in inclusion list or, all files, except the files matching the pattern listed in inclusion list.</span></span> <span data-ttu-id="3edc8-152">Er worden geen lokale paden ondersteund.</span><span class="sxs-lookup"><span data-stu-id="3edc8-152">No local paths are supported.</span></span> <span data-ttu-id="3edc8-153">Hier ziet u een aantal voorbeelden van geldige paden:</span><span class="sxs-lookup"><span data-stu-id="3edc8-153">Here are some examples of valid paths:</span></span>
      - <span data-ttu-id="3edc8-154">\\\server\share</span><span class="sxs-lookup"><span data-stu-id="3edc8-154">\\\server\share</span></span>
      - <span data-ttu-id="3edc8-155">\\\server\share\folder1\subfolderabc</span><span class="sxs-lookup"><span data-stu-id="3edc8-155">\\\server\share\folder1\subfolderabc</span></span>
      - <span data-ttu-id="3edc8-156">\*\\folder1</span><span class="sxs-lookup"><span data-stu-id="3edc8-156">\*\\folder1</span></span>
      - <span data-ttu-id="3edc8-157">\*secret\*.docx</span><span class="sxs-lookup"><span data-stu-id="3edc8-157">\*secret\*.docx</span></span>
      - <span data-ttu-id="3edc8-158">\*secret\*.\*</span><span class="sxs-lookup"><span data-stu-id="3edc8-158">\*secret\*.\*</span></span>
      - <span data-ttu-id="3edc8-159"> https:// sp2010.local/sites/HR</span><span class="sxs-lookup"><span data-stu-id="3edc8-159">https:// sp2010.local/sites/HR</span></span>
      - <span data-ttu-id="3edc8-160"> https://\*/HR</span><span class="sxs-lookup"><span data-stu-id="3edc8-160">https://\*/HR</span></span> 
    3. <span data-ttu-id="3edc8-161">Hier zijn enkele voorbeelden van onaanvaardbaar gebruik van waarden:</span><span class="sxs-lookup"><span data-stu-id="3edc8-161">Here are some examples of unacceptable values use:</span></span>
      - \*
      - <span data-ttu-id="3edc8-162">\*\\a</span><span class="sxs-lookup"><span data-stu-id="3edc8-162">\*\\a</span></span>
      - <span data-ttu-id="3edc8-163">Aaa</span><span class="sxs-lookup"><span data-stu-id="3edc8-163">Aaa</span></span>
      - <span data-ttu-id="3edc8-164">c:</span><span class="sxs-lookup"><span data-stu-id="3edc8-164">c:</span></span>\
      - <span data-ttu-id="3edc8-165">C:\test</span><span class="sxs-lookup"><span data-stu-id="3edc8-165">C:\test</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3edc8-166">De lijst met uitsluitingen heeft voorrang op de inclusielijst.</span><span class="sxs-lookup"><span data-stu-id="3edc8-166">The exclusion list takes precedence over the inclusions list.</span></span>

### <a name="viewing-dlp-on-premises-scanner-alerts-in-dlp-alerts-management-dashboard"></a><span data-ttu-id="3edc8-167">DLP-waarschuwingen voor on-premises scanners voor weergeven in het dashboard DLP-waarschuwingenbeheer</span><span class="sxs-lookup"><span data-stu-id="3edc8-167">Viewing DLP on-premises scanner alerts in DLP Alerts Management dashboard</span></span>

1. <span data-ttu-id="3edc8-168">Ga in het Microsoft 365-compliancecentrum naar de [pagina Preventie van gegevensverlies](https://compliance.microsoft.com/datalossprevention?viewid=policies) en kies **Waarschuwingen**.</span><span class="sxs-lookup"><span data-stu-id="3edc8-168">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) in the Microsoft 365 Compliance center and select **Alerts**.</span></span>

2. <span data-ttu-id="3edc8-169">Raadpleeg de procedures in [Informatie over het configureren en weergeven van waarschuwingen voor uw DLP-beleid](dlp-configure-view-alerts-policies.md) om waarschuwingen voor uw DLP-beleid voor eindpunten weer te geven.</span><span class="sxs-lookup"><span data-stu-id="3edc8-169">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>

### <a name="viewing-dlp-on-premises-scanner-in-activity-explorer-and-audit-log"></a><span data-ttu-id="3edc8-170">DLP on-premises scanner weergeven in Activity Explorer en auditlogboek</span><span class="sxs-lookup"><span data-stu-id="3edc8-170">Viewing DLP on-premises scanner in activity explorer and audit log</span></span>

> [!NOTE]
> <span data-ttu-id="3edc8-171">Voor de on-premises scanner moet controle zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="3edc8-171">The on-premises scanner requires that auditing be enabled.</span></span> <span data-ttu-id="3edc8-172">In Microsoft 365 is de controle standaard ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="3edc8-172">In Microsoft 365 auditing is enabled by default.</span></span>

1. <span data-ttu-id="3edc8-173">Open de [pagina Gegevensclassificatie voor](https://compliance.microsoft.com/dataclassification?viewid=overview) uw domein in het Microsoft 365-compliancecentrum en kies Activiteitenverkenner.</span><span class="sxs-lookup"><span data-stu-id="3edc8-173">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and select Activity explorer.</span></span>

2. <span data-ttu-id="3edc8-174">Raadpleeg de procedures in [Aan de slag met Activiteitenverkenner](data-classification-activity-explorer.md) om alle gegevens voor uw on-premises scannerlocaties weer te geven en te filteren.</span><span class="sxs-lookup"><span data-stu-id="3edc8-174">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your on-premises scanner locations.</span></span>

3. <span data-ttu-id="3edc8-175">Open in het [auditlogboek in het compliancecentrum](https://security.microsoft.com/auditlogsearch).</span><span class="sxs-lookup"><span data-stu-id="3edc8-175">Open the [Audit log in the Compliance center](https://security.microsoft.com/auditlogsearch).</span></span> <span data-ttu-id="3edc8-176">Tijdens de openbare preview zijn de DLP-regelovereenkomsten ook beschikbaar in de gebruikersinterface van het auditlogboek of beschikbaar door [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3edc8-176">During the public preview the DLP rule matches are available in Audit log UI or accessible by [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) PowerShell</span></span> 


## <a name="next-steps"></a><span data-ttu-id="3edc8-177">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="3edc8-177">Next steps</span></span>
<span data-ttu-id="3edc8-178">Nu u een testbeleid heeft ge\*implementeerd voor DLP on-premises locaties en de activiteitsgegevens kunt bekijken in Activiteitenverkenner, kunt u verder gaan met de volgende stap, waarin u DLP-beleid maakt voor het beveiligen van uw gevoelige items.</span><span class="sxs-lookup"><span data-stu-id="3edc8-178">Now that you have deployed a test policy for DLP on-premises locations and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="3edc8-179">DLP on-premises gebruiken (preview)</span><span class="sxs-lookup"><span data-stu-id="3edc8-179">Using DLP on-premises (preview)</span></span>](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a><span data-ttu-id="3edc8-180">Zie ook</span><span class="sxs-lookup"><span data-stu-id="3edc8-180">See also</span></span>

- [<span data-ttu-id="3edc8-181">Meer informatie over DLP-on-premises scanner (preview)</span><span class="sxs-lookup"><span data-stu-id="3edc8-181">Learn about DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-learn.md)
- [<span data-ttu-id="3edc8-182">DLP-on-premises scanner gebruiken (preview)</span><span class="sxs-lookup"><span data-stu-id="3edc8-182">Use DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-use.md)
- [<span data-ttu-id="3edc8-183">Meer informatie over preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="3edc8-183">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="3edc8-184">Een DLP-beleid maken, testen en afstemmen</span><span class="sxs-lookup"><span data-stu-id="3edc8-184">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="3edc8-185">Aan de slag met Activity Explorer</span><span class="sxs-lookup"><span data-stu-id="3edc8-185">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="3edc8-186">Microsoft 365-abonnement</span><span class="sxs-lookup"><span data-stu-id="3edc8-186">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)