---
title: 'Stap 2: classificatie voor uw omgeving configureren'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Informatie over en configuratie van verschillende manieren om gegevens in uw organisatie te classificeren.
ms.openlocfilehash: 57d4c692630826f371ea825d86fc64b959b71df2
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005808"
---
# <a name="step-2-configure-classification-for-your-environment"></a><span data-ttu-id="f9112-103">Stap 2: classificatie voor uw omgeving configureren</span><span class="sxs-lookup"><span data-stu-id="f9112-103">Step 2: Configure classification for your environment</span></span>

<span data-ttu-id="f9112-104">*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="f9112-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 6: Gegevensbeveiliging](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="f9112-106">In deze stap werkt u met uw juridische en nalevingsteams om een classificatieschema te definiëren voor de gegevens van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f9112-106">In this step, you work with your legal and compliance teams to define a classification scheme for your organization’s data.</span></span>

## <a name="microsoft-365-classification-types"></a><span data-ttu-id="f9112-107">Classificatietypen van Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f9112-107">Microsoft 365 classification types</span></span>

<span data-ttu-id="f9112-108">Microsoft 365 bevat vier classificatietypen:</span><span class="sxs-lookup"><span data-stu-id="f9112-108">Microsoft 365 includes four types of classification:</span></span>

- <span data-ttu-id="f9112-109">Gevoelige informatietypen</span><span class="sxs-lookup"><span data-stu-id="f9112-109">Sensitive information types</span></span>
- <span data-ttu-id="f9112-110">Retentielabels</span><span class="sxs-lookup"><span data-stu-id="f9112-110">Retention labels</span></span>
- <span data-ttu-id="f9112-111">Gevoeligheidslabels</span><span class="sxs-lookup"><span data-stu-id="f9112-111">Sensitivity labels</span></span>
- <span data-ttu-id="f9112-112">Labels en bescherming van Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="f9112-112">Azure Information Protection labels and protection</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="f9112-113">Gevoelige informatietypen</span><span class="sxs-lookup"><span data-stu-id="f9112-113">Sensitive information types</span></span>

<span data-ttu-id="f9112-114">Met gevoelige informatietypen voor Microsoft 365 definieert u hoe geautomatiseerd processen herkent, zoals het zoeken naar specifieke gegevenstypen.</span><span class="sxs-lookup"><span data-stu-id="f9112-114">Sensitive information types for Microsoft 365 define how automated processes such as search recognize specific information types.</span></span> <span data-ttu-id="f9112-115">Dit zijn onder andere gevoelige gegevens van werknemers of klanten, zoals burgerservicenummers en creditcardnummers.</span><span class="sxs-lookup"><span data-stu-id="f9112-115">These include sensitive employee or customer data such as health service numbers and credit card numbers.</span></span> <span data-ttu-id="f9112-116">U gebruikt de gevoelige informatietypen voor het zoeken naar gevoelige gegevens en u past DLP-regels en -beleid (preventie van gegevensverlies) toe om deze gegevens te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="f9112-116">You use sensitive information types to find sensitive data and apply data loss prevention (DLP) rules and policies to protect this data.</span></span> <span data-ttu-id="f9112-117">Zie [wat DLP-beleid omvat](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f9112-117">For more information, see [what a DLP policy contains](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains).</span></span> 

<span data-ttu-id="f9112-118">Gevoelige informatietypen zijn met name handig om te voldoen aan naleving en vereisten van regelgeving, zoals voor de Algemene Verordening Gegevensbescherming (AVG).</span><span class="sxs-lookup"><span data-stu-id="f9112-118">Sensitive information types are especially helpful for meeting compliance and regulation requirements, such as for the General Data Protection Regulation (GDPR).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="f9112-119">Retentielabels</span><span class="sxs-lookup"><span data-stu-id="f9112-119">Retention labels</span></span>

<span data-ttu-id="f9112-120">Een deel van het definiëren van een strategie van gegevensbeheer bestaat uit het bepalen hoe lang bepaalde typen documenten of documenten met specifieke inhoud moeten worden bewaard in overeenstemming met het organisatiebeleid en regionale regelgeving.</span><span class="sxs-lookup"><span data-stu-id="f9112-120">Part of defining a data governance strategy is deciding how long specific types of documents or documents with specific contents should be retained in compliance with organization policies and regional regulations.</span></span> <span data-ttu-id="f9112-121">Zo moeten sommige typen documenten gedurende een bepaalde periode worden bewaard en vervolgens verwijderd, en moeten andere voor onbepaalde tijd bewaard blijven.</span><span class="sxs-lookup"><span data-stu-id="f9112-121">For example, some types of documents should be retained for a set amount of time and then deleted and others must be retained indefinitely.</span></span>

<span data-ttu-id="f9112-122">Voor documenten die zijn opgeslagen in Microsoft 365, definieert u en past u retentielabels toe op documenten en gegevens die zijn opgeslagen in Exchange-e-mail, SharePoint Online, OneDrive voor Bedrijven en chat- en kanaalberichten van Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f9112-122">For documents stored in Microsoft 365, you define and apply retention labels to documents and data stored in Exchange email, SharePoint Online, OneDrive for Business, and Teams chat and channel messages.</span></span> 

<span data-ttu-id="f9112-123">Als u retentielabels gebruikt, moet u een label configureren voor elke categorie met bestanden waarop een bewaarbeleid moet worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="f9112-123">If you use retention labels, you should configure a label for each category of file that needs to have a retention policy applied.</span></span> <span data-ttu-id="f9112-124">Met het retentielabel kunt u het volgende opgeven:</span><span class="sxs-lookup"><span data-stu-id="f9112-124">Within the retention label, you can specify:</span></span>

- <span data-ttu-id="f9112-125">Een verzameling beschrijvingen voor de bestanden (bijvoorbeeld op bedrijfsafdeling, bestandscategorie of voorschrift).</span><span class="sxs-lookup"><span data-stu-id="f9112-125">A set of descriptors for the files (for example, by business department, file category, or regulation).</span></span>
- <span data-ttu-id="f9112-126">De retentie-instellingen voor de bestanden waaraan het retentielabel is gekoppeld, zoals de bewaartijden en gedragingen nadat de bewaartijd is bereikt.</span><span class="sxs-lookup"><span data-stu-id="f9112-126">The retention settings for the files that have the retention label attached, such as retain times and behaviors after the retain time has been reached.</span></span>

<span data-ttu-id="f9112-127">U kunt een retentielabel ook automatisch op bestanden toepassen door een SharePoint Online-site zodanig te configureren dat een standaardretentielabel wordt toegepast op alle nieuwe documenten op de site.</span><span class="sxs-lookup"><span data-stu-id="f9112-127">You can also apply a retention label to files automatically by configuring a SharePoint Online site to apply a default retention label to all new documents in the site.</span></span> 

<span data-ttu-id="f9112-128">Zie het [overzicht met retentielabels](https://docs.microsoft.com/office365/securitycompliance/labels) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f9112-128">For more information, see the [overview of retention labels](https://docs.microsoft.com/office365/securitycompliance/labels).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="f9112-129">Gevoeligheidslabels</span><span class="sxs-lookup"><span data-stu-id="f9112-129">Sensitivity labels</span></span>

<span data-ttu-id="f9112-130">Bij het beschermen en implementeren van beveiliging voor specifieke soorten documenten of documenten met specifieke inhoud worden deze onder meer gemarkeerd met een label zodat de extra beveiliging kan worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="f9112-130">Part of protecting and implementing security for specific types of documents or documents with specific contents is marking them with a label so that the additional security can be applied.</span></span> <span data-ttu-id="f9112-131">Met gevoeligheidslabels in Microsoft 365 kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="f9112-131">With sensitivity labels in Microsoft 365, you can:</span></span>

- <span data-ttu-id="f9112-132">Beveiligingsinstellingen afdwingen, zoals versleuteling, machtigingen of het toevoegen van een watermerk.</span><span class="sxs-lookup"><span data-stu-id="f9112-132">Enforce protection settings such as encryption, permissions, or adding a watermark.</span></span>
- <span data-ttu-id="f9112-133">Endpoint Protection van Windows-gegevensbescherming gebruiken om te voorkomen dat inhoud wordt gekopieerd naar een app van derden, zoals Twitter of Gmail, of wordt gekopieerd naar verwisselbare opslag, zoals een USB-station.</span><span class="sxs-lookup"><span data-stu-id="f9112-133">Use Windows Information Protection (WIP) endpoint protection to prevent that content from being copied to a third-party app, such as Twitter or Gmail, or being copied to removable storage, such as a USB drive.</span></span>
- <span data-ttu-id="f9112-134">Microsoft Cloud App Security (CAS) gebruiken om inhoud in apps en services van derden te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="f9112-134">Use Microsoft Cloud App Security (CAS) to protect content in third-party apps and services.</span></span> 
- <span data-ttu-id="f9112-135">Inhoud classificeren zonder beveiligingsinstellingen.</span><span class="sxs-lookup"><span data-stu-id="f9112-135">Classify content without using any protection settings.</span></span>

<span data-ttu-id="f9112-136">Als u gevoeligheidslabels gebruikt, moet u een label configureren voor elk beveiligings- en informatiebeschermingsniveau.</span><span class="sxs-lookup"><span data-stu-id="f9112-136">If you use sensitivity labels, you should configure a label for each security and information protection level.</span></span> <span data-ttu-id="f9112-137">Maak bijvoorbeeld drie gevoeligheidslabels voor:</span><span class="sxs-lookup"><span data-stu-id="f9112-137">For example, create three sensitivity labels for:</span></span>

- <span data-ttu-id="f9112-138">Basislijn</span><span class="sxs-lookup"><span data-stu-id="f9112-138">Baseline</span></span>
- <span data-ttu-id="f9112-139">Gevoelig</span><span class="sxs-lookup"><span data-stu-id="f9112-139">Sensitive</span></span>
- <span data-ttu-id="f9112-140">Sterk gereglementeerd</span><span class="sxs-lookup"><span data-stu-id="f9112-140">Highly regulated</span></span>

<span data-ttu-id="f9112-141">Als u bestanden met sterk gereglementeerde gegevens opslaat op een SharePoint Online-site en u wilt dat deze bestanden dezelfde machtigingen hebben als de site indien de bestanden de site verlaten, moet u een extra gevoeligheidslabel maken met dezelfde machtigingen als voor de site.</span><span class="sxs-lookup"><span data-stu-id="f9112-141">If you store files with highly regulated data in a SharePoint Online site and want those files to have the same permissions as the site if the files leave the site, you need to create an additional sensitivity label whose permissions are the same as the site.</span></span>

<span data-ttu-id="f9112-142">Zie dit [overzicht met gevoeligheidslabels ](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f9112-142">For more information, see this [overview of sensitivity labels](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels).</span></span>

### <a name="azure-information-protection-labels-and-protection"></a><span data-ttu-id="f9112-143">Labels en bescherming van Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="f9112-143">Azure Information Protection labels and protection</span></span>

<span data-ttu-id="f9112-144">U kunt Azure Information Protection-labels gebruiken om de documenten en e-mailberichten in uw organisatie te classificeren.</span><span class="sxs-lookup"><span data-stu-id="f9112-144">You can use Azure Information Protection labels to classify, and optionally protect, your organization’s documents and emails.</span></span> <span data-ttu-id="f9112-145">Deze labels kunnen worden toegepast op documenten die zijn opgeslagen buiten Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f9112-145">These labels can apply to documents that are stored outside of Microsoft 365.</span></span> <span data-ttu-id="f9112-146">Deze labels kunnen automatisch worden toegepast door beheerders die regels en voorwaarden definiëren, handmatig door gebruikers, of door een combinatie waarin gebruikers aanbevelingen hebben gekregen.</span><span class="sxs-lookup"><span data-stu-id="f9112-146">These labels can be applied automatically by administrators who define rules and conditions, manually by users, or a combination where users are given recommendations.</span></span>

<span data-ttu-id="f9112-147">Ga als volgt te werk om Azure Information Protection-labels en -beveiliging te plannen en te implementeren:</span><span class="sxs-lookup"><span data-stu-id="f9112-147">To plan and deploy Azure Information Protection labels and protection, do the following:</span></span>

1. <span data-ttu-id="f9112-148">Bekijk de [vereisten voor Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span><span class="sxs-lookup"><span data-stu-id="f9112-148">Review the [requirements for Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span></span>
2. <span data-ttu-id="f9112-149">Volg het [implementatieschema voor classificatie, labels en bescherming](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span><span class="sxs-lookup"><span data-stu-id="f9112-149">Follow the [deployment roadmap for classification, labeling, and protection](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span></span>

<span data-ttu-id="f9112-150">Zie de [bibliotheek met documentatie van Azure Information Protection](https://docs.microsoft.com/information-protection/) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f9112-150">For more information, see the [library of Azure Information Protection documentation](https://docs.microsoft.com/information-protection/).</span></span>

<span data-ttu-id="f9112-151">Bestaande Azure Information Protection-labels werken naadloos samen met gevoeligheidslabels.</span><span class="sxs-lookup"><span data-stu-id="f9112-151">Existing Azure Information Protection labels work seamlessly with sensitivity labels.</span></span> <span data-ttu-id="f9112-152">U kunt bijvoorbeeld uw bestaande labels voor Azure Information Protection-labels en de labels die worden toegepast op documenten en e-mail behouden.</span><span class="sxs-lookup"><span data-stu-id="f9112-152">For example, you can keep your existing Azure Information Protection labels and the labels that are applied to documents and email.</span></span>

<span data-ttu-id="f9112-153">Als u zowel gevoeligheidslabels als Azure Information Protection-labels hebt, moet u de [Azure Information Protection-labels naar de gevoeligheidslabels migreren](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#sensitivity-labels-and-azure-information-protection).</span><span class="sxs-lookup"><span data-stu-id="f9112-153">If you have both sensitivity and Azure Information Protection labels, you should [migrate your Azure Information Protection labels to sensitivity labels](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#sensitivity-labels-and-azure-information-protection).</span></span>

## <a name="example-classification-for-gdpr"></a><span data-ttu-id="f9112-154">Voorbeeld: classificatie voor AVG</span><span class="sxs-lookup"><span data-stu-id="f9112-154">Example: Classification for GDPR</span></span>

<span data-ttu-id="f9112-155">Zie [Architect a classification schema for personal data](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data) (Een classificatieschema voor persoonlijke gegevens ontwikkelen) voor een voorbeeld van een classificatieschema dat persoonlijke gegevens voor AVG bevat.</span><span class="sxs-lookup"><span data-stu-id="f9112-155">For an example classification scheme that includes personal data for GDPR, see [Architect a classification schema for personal data](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span></span>

## <a name="take-it-for-a-test-drive"></a><span data-ttu-id="f9112-156">Doe de test</span><span class="sxs-lookup"><span data-stu-id="f9112-156">Take it for a test drive</span></span>

|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="f9112-158">Handleiding voor het testlab: gegevensclassificatie</span><span class="sxs-lookup"><span data-stu-id="f9112-158">Test Lab Guide: Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="f9112-159">Zie de [afsluitcriteria](infoprotect-exit-criteria.md#crit-infoprotect-step2) voor deze stap als tussentijds controlepunt.</span><span class="sxs-lookup"><span data-stu-id="f9112-159">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step2) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="f9112-160">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="f9112-160">Next step</span></span>

|||
|:-------|:-----|
|![Stap 3](../media/stepnumbers/Step3.png)|[<span data-ttu-id="f9112-162">Verbeterde beveiliging voor Office 365 configureren</span><span class="sxs-lookup"><span data-stu-id="f9112-162">Configure increased security for Office 365</span></span>](infoprotect-configure-increased-security-office-365.md)|

