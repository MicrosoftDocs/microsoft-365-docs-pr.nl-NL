---
title: Gebruik Microsoft 365 preventie van gegevensverlies on-premises scanner (preview)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: how-to
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
description: Lees hoe u met de preventie van gegevensverlies in Microsoft 365 op een on-premises scanner data-at-rest kunt scannen en beschermende maatregelen kunt implementeren voor het on-premises delen van bestanden en on-premises SharePoint-mappen en -documentbibliotheken.
ms.openlocfilehash: b2512c47b82ab3624d892d349611dd3f1e5aed3c
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289173"
---
# <a name="use-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a><span data-ttu-id="c6b3e-103">Gebruik de Microsoft 365 preventie van gegevensverlies on-premises scanner (preview)</span><span class="sxs-lookup"><span data-stu-id="c6b3e-103">Use the Microsoft 365 data loss prevention on-premises scanner (preview)</span></span>

<span data-ttu-id="c6b3e-104">Om u vertrouwd te maken met de on-premises functies van DLP en hoe deze worden gebruikt in DLP-beleid, hebben we enkele scenario's opgesteld die u kunt volgen.</span><span class="sxs-lookup"><span data-stu-id="c6b3e-104">To help familiarize you with DLP on-premises features and how they surface in DLP policies, we've put together some scenarios for you to follow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c6b3e-105">Deze on-premises DLP-scenario's zijn niet de officiële procedures voor het maken en afstemmen van DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="c6b3e-105">These DLP on-premises scenarios are not the official procedures for creating and tuning DLP policies.</span></span> <span data-ttu-id="c6b3e-106">Raadpleeg de onderstaande onderwerpen wanneer u in het algemeen met DLP-beleid moet werken:</span><span class="sxs-lookup"><span data-stu-id="c6b3e-106">Refer to the below topics when you need to work with DLP policies in general situations:</span></span>
>
> - [<span data-ttu-id="c6b3e-107">Meer informatie over preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="c6b3e-107">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
> - [<span data-ttu-id="c6b3e-108">Aan de slag met het standaard DLP-beleid</span><span class="sxs-lookup"><span data-stu-id="c6b3e-108">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
> - [<span data-ttu-id="c6b3e-109">Een DLP-beleid maken vanuit een sjabloon</span><span class="sxs-lookup"><span data-stu-id="c6b3e-109">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
> - [<span data-ttu-id="c6b3e-110">Een DLP-beleid maken, testen en afstemmen</span><span class="sxs-lookup"><span data-stu-id="c6b3e-110">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-discover-files-matching-dlp-rules"></a><span data-ttu-id="c6b3e-111">Scenario: Ontdek bestanden die overeenkomen met DLP-regels</span><span class="sxs-lookup"><span data-stu-id="c6b3e-111">Scenario: Discover files matching DLP rules</span></span>

<span data-ttu-id="c6b3e-112">Gegevens van DLP-on-premises scanner komen in verschillende gebieden voor</span><span class="sxs-lookup"><span data-stu-id="c6b3e-112">Data from DLP on-premises scanner surfaces in several areas</span></span>

#### <a name="activity-explorer"></a><span data-ttu-id="c6b3e-113">Activiteitenverkenner</span><span class="sxs-lookup"><span data-stu-id="c6b3e-113">Activity explorer</span></span>

 <span data-ttu-id="c6b3e-114">Microsoft DLP voor on-premises detecteert DLP-regelovereenkomsten en rapporteert deze aan [Activiteitenverkenner](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer).</span><span class="sxs-lookup"><span data-stu-id="c6b3e-114">Microsoft DLP for on-premises detects DLP rule matches and reports them to [Activity Explorer](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer).</span></span>

#### <a name="microsoft-365-audit-log"></a><span data-ttu-id="c6b3e-115">Microsoft 365-auditlogboek</span><span class="sxs-lookup"><span data-stu-id="c6b3e-115">Microsoft 365 Audit log</span></span>

<span data-ttu-id="c6b3e-116">Tijdens de openbare preview zijn de DLP-regelovereenkomsten ook beschikbaar in de gebruikersinterface van het auditlogboek. Zie [Het auditlogboek zoeken in het compliancecentrum](search-the-audit-log-in-security-and-compliance.md)  of beschikbaar door [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c6b3e-116">During the public preview the DLP rule matches are available in Audit log UI, see [Search the audit log in the compliance center](search-the-audit-log-in-security-and-compliance.md)  or accessible by [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) PowerShell.</span></span>

#### <a name="aip"></a><span data-ttu-id="c6b3e-117">AIP</span><span class="sxs-lookup"><span data-stu-id="c6b3e-117">AIP</span></span>

<span data-ttu-id="c6b3e-118">Detectiegegevens zijn beschikbaar in een lokaal rapport in de CSV-indeling en zijn opgeslagen onder:</span><span class="sxs-lookup"><span data-stu-id="c6b3e-118">Discovery data is available in a local report in csv format which is stored under:</span></span>

<span data-ttu-id="c6b3e-119">**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv report**.</span><span class="sxs-lookup"><span data-stu-id="c6b3e-119">**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv report**.</span></span>

 <span data-ttu-id="c6b3e-120">Zoek de volgende kolommen:</span><span class="sxs-lookup"><span data-stu-id="c6b3e-120">Look for the following columns:</span></span>

- <span data-ttu-id="c6b3e-121">DLP-modus</span><span class="sxs-lookup"><span data-stu-id="c6b3e-121">DLP Mode</span></span>
- <span data-ttu-id="c6b3e-122">DLP-status</span><span class="sxs-lookup"><span data-stu-id="c6b3e-122">DLP Status</span></span>
- <span data-ttu-id="c6b3e-123">DLP-opmerking</span><span class="sxs-lookup"><span data-stu-id="c6b3e-123">DLP Comment</span></span>
- <span data-ttu-id="c6b3e-124">DLP-regelnaam</span><span class="sxs-lookup"><span data-stu-id="c6b3e-124">DLP Rule Name</span></span>
- <span data-ttu-id="c6b3e-125">DLP-acties</span><span class="sxs-lookup"><span data-stu-id="c6b3e-125">DLP Actions</span></span>
- <span data-ttu-id="c6b3e-126">Eigenaar</span><span class="sxs-lookup"><span data-stu-id="c6b3e-126">Owner</span></span>
- <span data-ttu-id="c6b3e-127">Huidige NTFS-machtigingen (SDDL)</span><span class="sxs-lookup"><span data-stu-id="c6b3e-127">Current NTFS Permissions (SDDL)</span></span>
- <span data-ttu-id="c6b3e-128">Toegepaste NTFS-machtigingen (SDDL)</span><span class="sxs-lookup"><span data-stu-id="c6b3e-128">Applied NTFS Permissions (SDDL)</span></span>
- <span data-ttu-id="c6b3e-129">Type NTFS-machtigingen</span><span class="sxs-lookup"><span data-stu-id="c6b3e-129">NTFS permissions type</span></span>

### <a name="scenario-enforce-dlp-rule"></a><span data-ttu-id="c6b3e-130">Scenario: DLP-regel afdwingen</span><span class="sxs-lookup"><span data-stu-id="c6b3e-130">Scenario: Enforce DLP rule</span></span>

<span data-ttu-id="c6b3e-131">Als u DLP-regels wilt afdwingen voor de gescande bestanden, moet afdwingen zijn ingeschakeld op zowel de inhoudsscantaak in AIP als op het beleidsniveau in DLP.</span><span class="sxs-lookup"><span data-stu-id="c6b3e-131">If you want to enforce DLP rules on the scanned files, enforcement must be enabled on both the content scan job in AIP and at the policy level in DLP.</span></span>

#### <a name="configure-dlp-to-enforce-policy-actions"></a><span data-ttu-id="c6b3e-132">DLP configureren voor het afdwingen van beleidsacties</span><span class="sxs-lookup"><span data-stu-id="c6b3e-132">Configure DLP to enforce policy actions</span></span>

1. <span data-ttu-id="c6b3e-133">Open de [pagina voor preventie van gegevensverlies](https://compliance.microsoft.com/datalossprevention?viewid=policies) en selecteer het DLP-beleid dat is gericht op de on-premises locatie-opslagplaatsen die u in AIP hebt geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="c6b3e-133">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) and select the DLP policy that is targeted to the on-premises location repositories you have configured in AIP.</span></span>
2. <span data-ttu-id="c6b3e-134">Geef het beleid een naam.</span><span class="sxs-lookup"><span data-stu-id="c6b3e-134">Edit the policy.</span></span>
3. <span data-ttu-id="c6b3e-135">Selecteer op de pagina **Het beleid testen of inschakelen\*\*\*\*Ja en schakel het meteen in**.</span><span class="sxs-lookup"><span data-stu-id="c6b3e-135">On the **Test or turn on the policy** page, select **Yes, turn it on right away**.</span></span>

## <a name="see-also"></a><span data-ttu-id="c6b3e-136">Zie ook</span><span class="sxs-lookup"><span data-stu-id="c6b3e-136">See also</span></span>

- [<span data-ttu-id="c6b3e-137">Meer informatie over DLP-on-premises scanner (preview)</span><span class="sxs-lookup"><span data-stu-id="c6b3e-137">Learn about DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-learn.md)
- [<span data-ttu-id="c6b3e-138">Aan de slag met DLP-on-premises scanner (preview)</span><span class="sxs-lookup"><span data-stu-id="c6b3e-138">Get started with  DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-get-started.md)
- [<span data-ttu-id="c6b3e-139">Meer informatie over preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="c6b3e-139">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="c6b3e-140">Een DLP-beleid maken, testen en afstemmen</span><span class="sxs-lookup"><span data-stu-id="c6b3e-140">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="c6b3e-141">Aan de slag met de activiteitenverkenner</span><span class="sxs-lookup"><span data-stu-id="c6b3e-141">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
