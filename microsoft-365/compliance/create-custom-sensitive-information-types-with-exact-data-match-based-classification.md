---
title: Aangepaste gevoelige informatietypen maken met Exacte gegevensmatch
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Meer informatie over het maken van aangepaste gevoelige informatietypen met op Exacte gegevens overeenkomende classificatie.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6839401bc1dd00acc45992f902a6360eb7f20120
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878194"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="8469d-103">Aangepaste gevoelige informatietypen maken met een classificatie op basis van Exacte gegevensmatch</span><span class="sxs-lookup"><span data-stu-id="8469d-103">Create custom sensitive information types with Exact Data Match based classification</span></span>



<span data-ttu-id="8469d-104">[Aangepaste gevoelige informatietypen worden](sensitive-information-type-learn-about.md) gebruikt om gevoelige items te identificeren, zodat u kunt voorkomen dat ze per ongeluk of ongepast worden gedeeld.</span><span class="sxs-lookup"><span data-stu-id="8469d-104">[Custom sensitive information types](sensitive-information-type-learn-about.md) are used to help identify sensitive items so that you can prevent them from being inadvertently or inappropriately shared.</span></span> <span data-ttu-id="8469d-105">U definieert een aangepast type gevoelige informatie (SIT)op basis van:</span><span class="sxs-lookup"><span data-stu-id="8469d-105">You define a custom sensitive information type (SIT)based on:</span></span>

- <span data-ttu-id="8469d-106">patronen</span><span class="sxs-lookup"><span data-stu-id="8469d-106">patterns</span></span>
- <span data-ttu-id="8469d-107">trefwoordbewijs, *zoals werknemer,* *badge* of *id*</span><span class="sxs-lookup"><span data-stu-id="8469d-107">keyword evidence such as *employee*, *badge*, or *ID*</span></span>
- <span data-ttu-id="8469d-108">teken nabijheid van bewijs in een bepaald patroon</span><span class="sxs-lookup"><span data-stu-id="8469d-108">character proximity to evidence in a particular pattern</span></span>
- <span data-ttu-id="8469d-109">betrouwbaarheidsniveaus</span><span class="sxs-lookup"><span data-stu-id="8469d-109">confidence levels</span></span>

 <span data-ttu-id="8469d-110">Dergelijke aangepaste gevoelige informatietypen voldoen aan de zakelijke behoeften van veel organisaties.</span><span class="sxs-lookup"><span data-stu-id="8469d-110">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="8469d-111">Maar wat als u een aangepast type gevoelige informatie (SIT) wilt dat exacte gegevenswaarden gebruikt, in plaats van een type dat overeenkomsten op basis van algemene patronen heeft gevonden?</span><span class="sxs-lookup"><span data-stu-id="8469d-111">But what if you wanted a custom sensitive information type (SIT) that uses exact data values, instead of one that found matches based on generic patterns?</span></span> <span data-ttu-id="8469d-112">Met de classificatie Exact Data Match (EDM) kunt u een aangepast type gevoelige informatie maken dat is ontworpen voor:</span><span class="sxs-lookup"><span data-stu-id="8469d-112">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="8469d-113">dynamisch en eenvoudig worden vernieuwd</span><span class="sxs-lookup"><span data-stu-id="8469d-113">be dynamic and easily refreshed</span></span>
- <span data-ttu-id="8469d-114">schaalbaarder zijn</span><span class="sxs-lookup"><span data-stu-id="8469d-114">be more scalable</span></span>
- <span data-ttu-id="8469d-115">leiden tot minder onwaar-positieven</span><span class="sxs-lookup"><span data-stu-id="8469d-115">result in fewer false-positives</span></span>
- <span data-ttu-id="8469d-116">werken met gestructureerde gevoelige gegevens</span><span class="sxs-lookup"><span data-stu-id="8469d-116">work with structured sensitive data</span></span>
- <span data-ttu-id="8469d-117">gevoelige informatie veiliger verwerken</span><span class="sxs-lookup"><span data-stu-id="8469d-117">handle sensitive information more securely</span></span>
- <span data-ttu-id="8469d-118">worden gebruikt met verschillende Microsoft-cloudservices</span><span class="sxs-lookup"><span data-stu-id="8469d-118">be used with several Microsoft cloud services</span></span>

![Classificatie op basis van EDM](../media/EDMClassification.png)

<span data-ttu-id="8469d-120">Met EDM-classificatie kunt u aangepaste gevoelige informatietypen maken die verwijzen naar exacte waarden in een database met gevoelige informatie.</span><span class="sxs-lookup"><span data-stu-id="8469d-120">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="8469d-121">De database kan dagelijks worden vernieuwd en maximaal 100 miljoen rijen met gegevens bevatten.</span><span class="sxs-lookup"><span data-stu-id="8469d-121">The database can be refreshed daily, and contain up to 100 million rows of data.</span></span> <span data-ttu-id="8469d-122">Als werknemers, patiënten of klanten komen en gaan en records veranderen, blijven uw aangepaste gevoelige informatietypen actueel en van toepassing.</span><span class="sxs-lookup"><span data-stu-id="8469d-122">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="8469d-123">En u kunt classificatie op basis van EDM gebruiken met beleidsregels, zoals beleid voor preventie van gegevensverlies of Microsoft Cloud App Security [bestandsbeleid.](/cloud-app-security/data-protection-policies) [](dlp-learn-about-dlp.md)</span><span class="sxs-lookup"><span data-stu-id="8469d-123">And, you can use EDM-based classification with policies, such as [data loss prevention policies](dlp-learn-about-dlp.md) or [Microsoft Cloud App Security file policies](/cloud-app-security/data-protection-policies).</span></span>

> [!NOTE]
> <span data-ttu-id="8469d-124">Microsoft 365 Information Protection ondersteunt talen voor preview van dubbel-byte-tekensets voor:</span><span class="sxs-lookup"><span data-stu-id="8469d-124">Microsoft 365 Information Protection supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="8469d-125">Vereenvoudigd Chinees</span><span class="sxs-lookup"><span data-stu-id="8469d-125">Chinese (simplified)</span></span>
> - <span data-ttu-id="8469d-126">Traditioneel Chinees</span><span class="sxs-lookup"><span data-stu-id="8469d-126">Chinese (traditional)</span></span>
> - <span data-ttu-id="8469d-127">Koreaks</span><span class="sxs-lookup"><span data-stu-id="8469d-127">Korean</span></span>
> - <span data-ttu-id="8469d-128">Japans</span><span class="sxs-lookup"><span data-stu-id="8469d-128">Japanese</span></span>
> 
> <span data-ttu-id="8469d-129">Deze ondersteuning is beschikbaar voor typen gevoelige informatie.</span><span class="sxs-lookup"><span data-stu-id="8469d-129">This support is available for sensitive information types.</span></span> <span data-ttu-id="8469d-130">Zie [Ondersteuning voor Information Protection voor releaseopmerkingen bij dubbel-bytetekensets (preview)](mip-dbcs-relnotes.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8469d-130">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>
 

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="8469d-131">Vereiste licenties en machtigingen</span><span class="sxs-lookup"><span data-stu-id="8469d-131">Required licenses and permissions</span></span>

<span data-ttu-id="8469d-132">U moet een globale beheerder, compliancebeheerder of Exchange Online zijn om de taken uit te voeren die in dit artikel worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="8469d-132">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="8469d-133">Zie [Machtigingen](data-loss-prevention-policies.md#permissions) voor meer informatie over DLP-machtigingen.</span><span class="sxs-lookup"><span data-stu-id="8469d-133">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="8469d-134">EDM-gebaseerde classificatie is inbegrepen in deze abonnementen</span><span class="sxs-lookup"><span data-stu-id="8469d-134">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="8469d-135">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="8469d-135">Office 365 E5</span></span>
- <span data-ttu-id="8469d-136">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="8469d-136">Microsoft 365 E5</span></span>
- <span data-ttu-id="8469d-137">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="8469d-137">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="8469d-138">Microsoft E5/A5 Gegevensbeveiliging en -beheer</span><span class="sxs-lookup"><span data-stu-id="8469d-138">Microsoft E5/A5 Information Protection and Governance</span></span>

## <a name="portal-links-for-your-subscription"></a><span data-ttu-id="8469d-139">Portalkoppelingen voor uw abonnement</span><span class="sxs-lookup"><span data-stu-id="8469d-139">Portal links for your subscription</span></span>


|<span data-ttu-id="8469d-140">Portal</span><span class="sxs-lookup"><span data-stu-id="8469d-140">Portal</span></span>  |<span data-ttu-id="8469d-141">World Wide/GCC</span><span class="sxs-lookup"><span data-stu-id="8469d-141">World Wide/GCC</span></span>  |<span data-ttu-id="8469d-142">GCC-High</span><span class="sxs-lookup"><span data-stu-id="8469d-142">GCC-High</span></span>  |<span data-ttu-id="8469d-143">DOD</span><span class="sxs-lookup"><span data-stu-id="8469d-143">DOD</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="8469d-144">Office SCC</span><span class="sxs-lookup"><span data-stu-id="8469d-144">Office SCC</span></span>     |  <span data-ttu-id="8469d-145">protection.office.com</span><span class="sxs-lookup"><span data-stu-id="8469d-145">protection.office.com</span></span>       |<span data-ttu-id="8469d-146">scc.office365.us</span><span class="sxs-lookup"><span data-stu-id="8469d-146">scc.office365.us</span></span>         |<span data-ttu-id="8469d-147">scc.protection.apps.mil</span><span class="sxs-lookup"><span data-stu-id="8469d-147">scc.protection.apps.mil</span></span> |
|<span data-ttu-id="8469d-148">Microsoft 365 Beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="8469d-148">Microsoft 365 Security center</span></span>     |<span data-ttu-id="8469d-149">security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8469d-149">security.microsoft.com</span></span>         |<span data-ttu-id="8469d-150">security.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="8469d-150">security.microsoft.us</span></span>         |<span data-ttu-id="8469d-151">security.apps.mil</span><span class="sxs-lookup"><span data-stu-id="8469d-151">security.apps.mil</span></span>|
|<span data-ttu-id="8469d-152">Microsoft 365 Compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="8469d-152">Microsoft 365 Compliance center</span></span>     |<span data-ttu-id="8469d-153">compliance.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8469d-153">compliance.microsoft.com</span></span>         |<span data-ttu-id="8469d-154">compliance.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="8469d-154">compliance.microsoft.us</span></span>         |<span data-ttu-id="8469d-155">compliance.apps.mil</span><span class="sxs-lookup"><span data-stu-id="8469d-155">compliance.apps.mil</span></span>|


## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="8469d-156">De werkstroom in één oogopslag</span><span class="sxs-lookup"><span data-stu-id="8469d-156">The work flow at a glance</span></span>

|<span data-ttu-id="8469d-157">Fase</span><span class="sxs-lookup"><span data-stu-id="8469d-157">Phase</span></span>  |<span data-ttu-id="8469d-158">Wat is er nodig</span><span class="sxs-lookup"><span data-stu-id="8469d-158">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="8469d-159">Deel 1: Classificatie op basis van EDM instellen</span><span class="sxs-lookup"><span data-stu-id="8469d-159">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="8469d-160">(Indien nodig)</span><span class="sxs-lookup"><span data-stu-id="8469d-160">(As needed)</span></span><br/><span data-ttu-id="8469d-161">- [Het databaseschema bewerken](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="8469d-161">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="8469d-162">- [Het schema verwijderen](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="8469d-162">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="8469d-163">- Lees de toegang tot de gevoelige gegevens</span><span class="sxs-lookup"><span data-stu-id="8469d-163">- Read access to the sensitive data</span></span><br/><span data-ttu-id="8469d-164">- Databaseschema in XML-indeling (voorbeeld opgegeven)</span><span class="sxs-lookup"><span data-stu-id="8469d-164">- Database schema in XML format (example provided)</span></span><br/><span data-ttu-id="8469d-165">- Regelpakket in XML-indeling (voorbeeld beschikbaar)</span><span class="sxs-lookup"><span data-stu-id="8469d-165">- Rule package in XML format (example provided)</span></span><br/><span data-ttu-id="8469d-166">- Beheerdersmachtigingen voor het beveiligings- & compliancecentrum (met PowerShell)</span><span class="sxs-lookup"><span data-stu-id="8469d-166">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="8469d-167">Deel 2: Hash en upload de gevoelige gegevens</span><span class="sxs-lookup"><span data-stu-id="8469d-167">Part 2: Hash and upload the sensitive data</span></span>](#part-2-hash-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="8469d-168">(Indien nodig)</span><span class="sxs-lookup"><span data-stu-id="8469d-168">(As needed)</span></span><br/>[<span data-ttu-id="8469d-169">De gegevens vernieuwen</span><span class="sxs-lookup"><span data-stu-id="8469d-169">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="8469d-170">- Aangepaste beveiligingsgroep en gebruikersaccount</span><span class="sxs-lookup"><span data-stu-id="8469d-170">- Custom security group and user account</span></span><br/><span data-ttu-id="8469d-171">- Toegang van lokale beheerder tot machine met EDM-Upload Agent</span><span class="sxs-lookup"><span data-stu-id="8469d-171">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="8469d-172">- Lees de toegang tot de gevoelige gegevens</span><span class="sxs-lookup"><span data-stu-id="8469d-172">- Read access to the sensitive data</span></span><br/><span data-ttu-id="8469d-173">- Verwerken en plannen voor het vernieuwen van de gegevens</span><span class="sxs-lookup"><span data-stu-id="8469d-173">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="8469d-174">Deel 3: Classificatie op basis van EDM gebruiken met uw Microsoft-cloudservices</span><span class="sxs-lookup"><span data-stu-id="8469d-174">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="8469d-175">- Microsoft 365 abonnement met DLP</span><span class="sxs-lookup"><span data-stu-id="8469d-175">- Microsoft 365 subscription with DLP</span></span><br/><span data-ttu-id="8469d-176">- Classificatiefunctie op basis van EDM ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="8469d-176">- EDM-based classification feature enabled</span></span> |

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="8469d-177">Deel 1: Classificatie op basis van EDM instellen</span><span class="sxs-lookup"><span data-stu-id="8469d-177">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="8469d-178">Het instellen en configureren van classificatie op basis van EDM houdt in:</span><span class="sxs-lookup"><span data-stu-id="8469d-178">Setting up and configuring EDM-based classification involves:</span></span>

1. [<span data-ttu-id="8469d-179">Gevoelige gegevens opslaan in .csv of .tsv-indeling</span><span class="sxs-lookup"><span data-stu-id="8469d-179">Saving sensitive data in .csv or .tsv format</span></span>](#save-sensitive-data-in-csv-or-tsv-format)
2. [<span data-ttu-id="8469d-180">Het databaseschema voor gevoelige informatie definiëren</span><span class="sxs-lookup"><span data-stu-id="8469d-180">Define your sensitive information database schema</span></span>](#define-the-schema-for-your-database-of-sensitive-information)
3. [<span data-ttu-id="8469d-181">Een regelpakket maken</span><span class="sxs-lookup"><span data-stu-id="8469d-181">Create a rule package</span></span>](#set-up-a-rule-package)


#### <a name="save-sensitive-data-in-csv-or-tsv-format"></a><span data-ttu-id="8469d-182">Gevoelige gegevens opslaan in .csv of .tsv-indeling</span><span class="sxs-lookup"><span data-stu-id="8469d-182">Save sensitive data in .csv or .tsv format</span></span>

1. <span data-ttu-id="8469d-183">Identificeer de gevoelige informatie die u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="8469d-183">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="8469d-184">Exporteert de gegevens naar een app, zoals Microsoft Excel, en sla het bestand op in een tekstbestand.</span><span class="sxs-lookup"><span data-stu-id="8469d-184">Export the data to an app, such as Microsoft Excel, and save the file in a text file.</span></span> <span data-ttu-id="8469d-185">Het bestand kan worden opgeslagen in .csv (door komma's gescheiden waarden), .tsv (door tabbladen gescheiden waarden) of door een |.</span><span class="sxs-lookup"><span data-stu-id="8469d-185">The file can be saved in .csv (comma-separated values), .tsv (tab-separated values), or pipe-separated (|) format.</span></span> <span data-ttu-id="8469d-186">De TSV-indeling wordt aanbevolen in gevallen waarin uw gegevenswaarden komma's kunnen bevatten, zoals straatadressen.</span><span class="sxs-lookup"><span data-stu-id="8469d-186">The .tsv format is recommended in cases where your data values may included commas, such as street addresses.</span></span>
<span data-ttu-id="8469d-187">Het gegevensbestand kan een maximum van:</span><span class="sxs-lookup"><span data-stu-id="8469d-187">The data file can include a maximum of:</span></span>
      - <span data-ttu-id="8469d-188">Maximaal 100 miljoen rijen met gevoelige gegevens</span><span class="sxs-lookup"><span data-stu-id="8469d-188">Up to 100 million rows of sensitive data</span></span>
      - <span data-ttu-id="8469d-189">Maximaal 32 kolommen (velden) per gegevensbron</span><span class="sxs-lookup"><span data-stu-id="8469d-189">Up to 32 columns (fields) per data source</span></span>
      - <span data-ttu-id="8469d-190">Maximaal 5 kolommen (velden) gemarkeerd als doorzoekbaar</span><span class="sxs-lookup"><span data-stu-id="8469d-190">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="8469d-191">Structureer de gevoelige gegevens in het .csv of .tsv-bestand zodanig dat de eerste rij de namen bevat van de velden die worden gebruikt voor op EDM gebaseerde classificatie.</span><span class="sxs-lookup"><span data-stu-id="8469d-191">Structure the sensitive data in the .csv or .tsv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="8469d-192">In uw bestand hebt u mogelijk veldnamen zoals 'ssn', 'geboortedatum', 'voornaam', 'achternaam'.</span><span class="sxs-lookup"><span data-stu-id="8469d-192">In your file you might have field names such as "ssn", "birthdate", "firstname", "lastname".</span></span> <span data-ttu-id="8469d-193">De namen van de kolomkoppen kunnen geen spaties of onderstrepingstekens bevatten.</span><span class="sxs-lookup"><span data-stu-id="8469d-193">The column header names can't include spaces or underscores.</span></span> <span data-ttu-id="8469d-194">Het voorbeeldbestand .csv dat we in dit artikel gebruiken, heeft bijvoorbeeld de naam *PatientRecords.csv* en de kolommen zijn *PatientID,* *MRN,* *LastName,* *FirstName,* *SSN* en meer.</span><span class="sxs-lookup"><span data-stu-id="8469d-194">For example, the sample .csv file that we use in this article is named *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN*, and more.</span></span>

3. <span data-ttu-id="8469d-195">Let op de opmaak van de gevoelige gegevensvelden.</span><span class="sxs-lookup"><span data-stu-id="8469d-195">Pay attention to the format of the sensitive data fields.</span></span> <span data-ttu-id="8469d-196">Met name velden die komma's in hun inhoud kunnen bevatten, bijvoorbeeld een straatadres met de waarde 'Seattle,WA', worden geparseerd als twee afzonderlijke velden wanneer ze worden geparseerd als de .csv-indeling is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="8469d-196">In particular, fields that may contain commas in their content, for example, a street address that contains the value "Seattle,WA" would be parsed as two separate fields when parsed if the .csv format is selected.</span></span> <span data-ttu-id="8469d-197">U kunt dit voorkomen door de TSV-indeling te gebruiken of de komma met waarden te omgeven door dubbele aanhalingstekens in de gevoelige gegevenstabel.</span><span class="sxs-lookup"><span data-stu-id="8469d-197">To avoid this, use the .tsv format or surrounded the comma containing values by double quotes in the sensitive data table.</span></span> <span data-ttu-id="8469d-198">Als komma's ook spaties bevatten, moet u een aangepaste SIT maken die overeenkomt met de bijbehorende indeling.</span><span class="sxs-lookup"><span data-stu-id="8469d-198">If comma containing values also contain spaces, you need to create a custom SIT that matches the corresponding format.</span></span> <span data-ttu-id="8469d-199">Een SIT bijvoorbeeld die tekenreeks met meerdere woorden detecteert met komma's en spaties.</span><span class="sxs-lookup"><span data-stu-id="8469d-199">For example, a SIT that detects multi-word string with commas and spaces in it.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="8469d-200">Het schema voor uw database met gevoelige informatie definiëren</span><span class="sxs-lookup"><span data-stu-id="8469d-200">Define the schema for your database of sensitive information</span></span>

<span data-ttu-id="8469d-201">Als u om zakelijke of technische redenen liever geen PowerShell of opdrachtregel gebruikt om uw schema en EDM-patroon (regelpakket) te maken, kunt u de wizard Exacte gegevensmatch en Gevoelige [informatietype](sit-edm-wizard.md) gebruiken om deze te maken.</span><span class="sxs-lookup"><span data-stu-id="8469d-201">If for business or technical reasons, you prefer not to use PowerShell or command line to create your schema and EDM sensitive info type pattern (rule package), you can use the [Exact Data Match Schema and Sensitive Information Type Wizard](sit-edm-wizard.md) to create them.</span></span> <span data-ttu-id="8469d-202">Wanneer u klaar bent met het maken van het schema en het EDM-gevoelige infotypepatroon, gaat u terug naar alle stappen die nodig zijn om uw op EDM gebaseerde gevoelige informatietype beschikbaar te maken voor gebruik.</span><span class="sxs-lookup"><span data-stu-id="8469d-202">When you are done creating the schema and EDM sensitive info type pattern, return to complete all the steps necessary to make your EDM based sensitive information type available for use.</span></span>

> [!NOTE]
> <span data-ttu-id="8469d-203">De wizard voor het schema voor exacte gegevensovereenkomst en het type gevoelige informatie is alleen beschikbaar voor de wereldwijde en GCC-cloud.</span><span class="sxs-lookup"><span data-stu-id="8469d-203">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

1. <span data-ttu-id="8469d-204">Definieer het schema voor de database met gevoelige informatie in XML-indeling (vergelijkbaar met ons voorbeeld hieronder).</span><span class="sxs-lookup"><span data-stu-id="8469d-204">Define the schema for the database of sensitive information in XML format (similar to our example below).</span></span> <span data-ttu-id="8469d-205">Noem dit schemabestand **edm.xml** en configureer het zo dat er voor elke kolom in de database een regel is waarin de syntaxis wordt gebruikt:</span><span class="sxs-lookup"><span data-stu-id="8469d-205">Name this schema file **edm.xml**, and configure it such that for each column in the database, there is a line that uses the syntax:</span></span> 

      <span data-ttu-id="8469d-206">`\<Field name="" searchable=""/\>`.</span><span class="sxs-lookup"><span data-stu-id="8469d-206">`\<Field name="" searchable=""/\>`.</span></span>

      - <span data-ttu-id="8469d-207">Kolomnamen gebruiken voor *veldnaamwaarden.*</span><span class="sxs-lookup"><span data-stu-id="8469d-207">Use column names for *Field name* values.</span></span>
      - <span data-ttu-id="8469d-208">Gebruik *searchable="true"* voor de velden die u wilt doorzoeken tot maximaal 5 velden.</span><span class="sxs-lookup"><span data-stu-id="8469d-208">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="8469d-209">Ten minste één veld moet doorzoekbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="8469d-209">At least one field must be searchable.</span></span>

      <span data-ttu-id="8469d-210">In het volgende XML-bestand wordt bijvoorbeeld het schema voor een patiëntenrecorddatabase gedefinieerd, met vijf velden die als doorzoekbaar zijn opgegeven: *PatientID,* *MRN,* *SSN,* *Telefoon* en *DOB.*</span><span class="sxs-lookup"><span data-stu-id="8469d-210">As an example, the following XML file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

      <span data-ttu-id="8469d-211">(U kunt ons voorbeeld kopiëren, wijzigen en gebruiken.)</span><span class="sxs-lookup"><span data-stu-id="8469d-211">(You can copy, modify, and use our example.)</span></span>

      ```xml
      <EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
            <DataStore name="PatientRecords" description="Schema for patient records" version="1">
                  <Field name="PatientID" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
                  <Field name="MRN" searchable="true" />
                  <Field name="FirstName" />
                  <Field name="LastName" />
                  <Field name="SSN" searchable="true" />
                  <Field name="Phone" searchable="true" />
                  <Field name="DOB" searchable="true" />
                  <Field name="Gender" />
                  <Field name="Address" />
            </DataStore>
      </EdmSchema>
      ```

##### <a name="configurable-match-using-the-caseinsensitive-and-ignoreddelimiters-fields"></a><span data-ttu-id="8469d-212">Configureerbare overeenkomst met de velden CaseInensitive en ignoredDelimiters</span><span class="sxs-lookup"><span data-stu-id="8469d-212">Configurable match using the caseInsensitive and ignoredDelimiters fields</span></span>

<span data-ttu-id="8469d-213">In het bovenstaande XML-voorbeeld wordt gebruik gemaakt van `caseInsensitive` de velden en de `ignoredDelimiters` velden.</span><span class="sxs-lookup"><span data-stu-id="8469d-213">The above XML sample makes use of the `caseInsensitive` and the `ignoredDelimiters` fields.</span></span> 

<span data-ttu-id="8469d-214">Wanneer u het veld \***caseInsensitive** _ op de waarde van in uw schemadefinitie op neemt, wordt een item niet uitgesloten op basis van `true` caseverschillen voor `PatientID` veld.</span><span class="sxs-lookup"><span data-stu-id="8469d-214">When you include the \***caseInsensitive** _ field set to the value of `true` in your schema definition, EDM will not exclude an item based on case differences for `PatientID` field.</span></span> <span data-ttu-id="8469d-215">Dus EDM ziet, `PatientID` _ *FOO-1234*\* en **fOo-1234** als identiek.</span><span class="sxs-lookup"><span data-stu-id="8469d-215">So EDM will see, `PatientID` _ *FOO-1234*\* and **fOo-1234** as being identical.</span></span>

<span data-ttu-id="8469d-216">Wanneer u het veld \***ignoredDelimiters** _ met ondersteunde tekens op neemt, worden deze tekens genegeerd in `PatientID` de .</span><span class="sxs-lookup"><span data-stu-id="8469d-216">When you include the \***ignoredDelimiters** _ field with supported characters,  EDM will ignore those characters in the `PatientID`.</span></span> <span data-ttu-id="8469d-217">Dus EDM ziet, `PatientID` _ *FOO-1234*\* en `PatientID` **FOO#1234** als identiek.</span><span class="sxs-lookup"><span data-stu-id="8469d-217">So EDM will see, `PatientID` _ *FOO-1234*\* and `PatientID` **FOO#1234** as being identical.</span></span> <span data-ttu-id="8469d-218">De `ignoredDelimiters` vlag ondersteunt alle niet-alfanumerieke tekens. Hier volgen enkele voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="8469d-218">The `ignoredDelimiters` flag supports any non-alphanumeric character, here are some examples:</span></span>
- <span data-ttu-id="8469d-219">\.</span><span class="sxs-lookup"><span data-stu-id="8469d-219">\.</span></span>
- \-
- \/
- \_
- \*
- \^
- \#
- \!
- \?
- \[
- \]
- \{
- \}
- \\
- \~
- \; 

<span data-ttu-id="8469d-220">The `ignoredDelimiters` vlag ondersteunt het volgende niet:</span><span class="sxs-lookup"><span data-stu-id="8469d-220">The `ignoredDelimiters` flag doesn't support:</span></span>
- <span data-ttu-id="8469d-221">tekens 0-9</span><span class="sxs-lookup"><span data-stu-id="8469d-221">characters 0-9</span></span>
- <span data-ttu-id="8469d-222">A-Z</span><span class="sxs-lookup"><span data-stu-id="8469d-222">A-Z</span></span>
- <span data-ttu-id="8469d-223">a-z</span><span class="sxs-lookup"><span data-stu-id="8469d-223">a-z</span></span>
- \"
- \,

<span data-ttu-id="8469d-224">In dit voorbeeld, waarin beide en worden gebruikt, worden `caseInsensitive` `ignoredDelimiters` **FOO-1234** en **fOo#1234** door EDM als identiek geclassificeerd en wordt het item geclassificeerd als een type gevoelige informatie voor patiëntenrecords.</span><span class="sxs-lookup"><span data-stu-id="8469d-224">In this example, where both `caseInsensitive` and `ignoredDelimiters` are used, EDM would see **FOO-1234** and **fOo#1234** as  identical and classify the item as a patient record sensitive information type.</span></span> 

4. <span data-ttu-id="8469d-225">Verbinding maken met het Beveiligings- en compliancecentrum met behulp van de procedures in [Verbinding maken met Beveiligings- en compliancecentrum van PowerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="8469d-225">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

5. <span data-ttu-id="8469d-226">Als u het databaseschema wilt uploaden, moet u de volgende cmdlets één voor één uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="8469d-226">To upload the database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="8469d-227">U wordt als volgt gevraagd om dit te bevestigen:</span><span class="sxs-lookup"><span data-stu-id="8469d-227">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="8469d-228">Bevestigen</span><span class="sxs-lookup"><span data-stu-id="8469d-228">Confirm</span></span>
      >
      > <span data-ttu-id="8469d-229">Weet u zeker dat u deze actie wilt uitvoeren?</span><span class="sxs-lookup"><span data-stu-id="8469d-229">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="8469d-230">Nieuw EDM-schema voor het gegevensopslag 'patiëntenrecords' wordt geïmporteerd.</span><span class="sxs-lookup"><span data-stu-id="8469d-230">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
      >
      > <span data-ttu-id="8469d-231">\[Y \] Yes A Yes to All N No L No to All \[ \] \[ \] \[ \] \[ ? \] Help (standaard is 'Y'):</span><span class="sxs-lookup"><span data-stu-id="8469d-231">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="8469d-232">Als u wilt dat uw wijzigingen zonder bevestiging plaatsvinden, gebruikt u in stap 5 deze cmdlet: New-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="8469d-232">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="8469d-233">Het kan 10 tot 60 minuten duren voordat het EDMSchema wordt bijgewerkt met toevoegingen.</span><span class="sxs-lookup"><span data-stu-id="8469d-233">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="8469d-234">De update moet worden voltooid voordat u stappen uitvoert die gebruikmaken van de toevoegingen.</span><span class="sxs-lookup"><span data-stu-id="8469d-234">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="set-up-a-rule-package"></a><span data-ttu-id="8469d-235">Een regelpakket instellen</span><span class="sxs-lookup"><span data-stu-id="8469d-235">Set up a rule package</span></span>

1. <span data-ttu-id="8469d-236">Maak een regelpakket in XML-indeling (met Unicode-codering), vergelijkbaar met het volgende voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="8469d-236">Create a rule package in XML format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="8469d-237">(U kunt ons voorbeeld kopiëren, wijzigen en gebruiken.)</span><span class="sxs-lookup"><span data-stu-id="8469d-237">(You can copy, modify, and use our example.)</span></span>

      <span data-ttu-id="8469d-238">Wanneer u het regelpakket in stelt, moet u uw .csv of .tsv-bestand en hetedm.xml **verwijzen.**</span><span class="sxs-lookup"><span data-stu-id="8469d-238">When you set up your rule package, make sure to correctly reference your .csv or .tsv file and **edm.xml** file.</span></span> <span data-ttu-id="8469d-239">U kunt ons voorbeeld kopiëren, wijzigen en gebruiken.</span><span class="sxs-lookup"><span data-stu-id="8469d-239">You can copy, modify, and use our example.</span></span> <span data-ttu-id="8469d-240">In deze voorbeeld-xml moeten de volgende velden worden aangepast om het gevoelige type EDM te maken:</span><span class="sxs-lookup"><span data-stu-id="8469d-240">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

      - <span data-ttu-id="8469d-241">**RulePack-id & ExactMatch-id:** Gebruik [Nieuwe GUID](/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) om een GUID te genereren.</span><span class="sxs-lookup"><span data-stu-id="8469d-241">**RulePack id & ExactMatch id**: Use [New-GUID](/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) to generate a GUID.</span></span>

      - <span data-ttu-id="8469d-242">**Gegevensstore:** in dit veld wordt aangegeven dat het opzoekgegevensopslag van EDM moet worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="8469d-242">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="8469d-243">U geeft een gegevensbronnaam op van een geconfigureerd EDM-schema.</span><span class="sxs-lookup"><span data-stu-id="8469d-243">You provide a data source name of a configured EDM Schema.</span></span>

      - <span data-ttu-id="8469d-244">**idMatch:** dit veld wijst naar het primaire element voor EDM.</span><span class="sxs-lookup"><span data-stu-id="8469d-244">**idMatch**: This field points to the primary element for EDM.</span></span>
        - <span data-ttu-id="8469d-245">Overeenkomsten: hiermee geeft u het veld op dat moet worden gebruikt voor exacte opzoekactie.</span><span class="sxs-lookup"><span data-stu-id="8469d-245">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="8469d-246">U geeft een doorzoekbare veldnaam op in EDM-schema voor de DataStore.</span><span class="sxs-lookup"><span data-stu-id="8469d-246">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
        - <span data-ttu-id="8469d-247">Classificatie: Dit veld geeft de gevoelige type overeenkomst aan die EDM-opzoekactie activeert.</span><span class="sxs-lookup"><span data-stu-id="8469d-247">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="8469d-248">U kunt de naam of GUID van een bestaand ingebouwde of aangepaste gevoelige informatietype geven.</span><span class="sxs-lookup"><span data-stu-id="8469d-248">You can provide the Name or GUID of an existing built-in or custom sensitive information type.</span></span> <span data-ttu-id="8469d-249">Elke tekenreeks die overeenkomt met het opgegeven type gevoelige informatie, wordt gehasht en vergeleken met elke vermelding in de tabel met gevoelige informatie.</span><span class="sxs-lookup"><span data-stu-id="8469d-249">Be aware that any string that matches the sensitive information type provided will be hashed and compared to every entry in the sensitive information table.</span></span> <span data-ttu-id="8469d-250">Als u een aangepast type gevoelige informatie gebruikt als het element Classificatie in EDM, vermijdt u het gebruik van een element dat past bij een groot percentage inhoud (zoals 'elk getal' of 'een woord met vijf letters') door ondersteunende trefwoorden toe te voegen of opmaak toe te voegen in de definitie van het aangepaste classificatiegevoelige informatietype.</span><span class="sxs-lookup"><span data-stu-id="8469d-250">In order to avoid causing performance issues, if you use a custom sensitive information type as the Classification element in EDM, avoid using one that will match a large percentage of content (such as "any number" or "any five-letter word") by adding supporting keywords or including formatting in the definition of the custom classification sensitive information type.</span></span> 

      - <span data-ttu-id="8469d-251">**Overeenkomen:** Dit veld wijst naar extra bewijs dat is gevonden in de nabijheid van idMatch.</span><span class="sxs-lookup"><span data-stu-id="8469d-251">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
        - <span data-ttu-id="8469d-252">Overeenkomsten: U geeft een veldnaam op in het EDM-schema voor DataStore.</span><span class="sxs-lookup"><span data-stu-id="8469d-252">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
      - <span data-ttu-id="8469d-253">**Resource:** In deze sectie worden de naam en beschrijving opgegeven voor het gevoelige type in meerdere locales.</span><span class="sxs-lookup"><span data-stu-id="8469d-253">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
        - <span data-ttu-id="8469d-254">idRef: U geeft GUID voor ExactMatch-id.</span><span class="sxs-lookup"><span data-stu-id="8469d-254">idRef: You provide GUID for ExactMatch ID.</span></span>
        - <span data-ttu-id="8469d-255">Naam & beschrijvingen: zo nodig aanpassen.</span><span class="sxs-lookup"><span data-stu-id="8469d-255">Name & descriptions: customize as required.</span></span>

      ```xml
      <RulePackage xmlns="http://schemas.microsoft.com/office/2018/edm">
        <RulePack id="fd098e03-1796-41a5-8ab6-198c93c62b11">
          <Version build="0" major="2" minor="0" revision="0" />
          <Publisher id="eb553734-8306-44b4-9ad5-c388ad970528" />
          <Details defaultLangCode="en-us">
            <LocalizedDetails langcode="en-us">
              <PublisherName>IP DLP</PublisherName>
              <Name>Health Care EDM Rulepack</Name>
              <Description>This rule package contains the EDM sensitive type for health care sensitive types.</Description>
            </LocalizedDetails>
          </Details>
        </RulePack>
        <Rules>
          <ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
            <Pattern confidenceLevel="65">
              <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
            </Pattern>
            <Pattern confidenceLevel="75">
              <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
              <Any minMatches ="3" maxMatches ="6">
                <match matches="PatientID" />
                <match matches="MRN"/>
                <match matches="FirstName"/>
                <match matches="LastName"/>
                <match matches="Phone"/>
                <match matches="DOB"/>
              </Any>
            </Pattern>
          </ExactMatch>
          <LocalizedStrings>
            <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB371">
              <Name default="true" langcode="en-us">Patient SSN Exact Match.</Name>
              <Description default="true" langcode="en-us">EDM Sensitive type for detecting Patient SSN.</Description>
            </Resource>
          </LocalizedStrings>
        </Rules>
      </RulePackage>
      ```

2. <span data-ttu-id="8469d-256">Upload het regelpakket door de volgende PowerShell-cmdlets één voor één uit te laten lopen:</span><span class="sxs-lookup"><span data-stu-id="8469d-256">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

<span data-ttu-id="8469d-257">Op dit moment hebt u classificatie op basis van EDM ingesteld.</span><span class="sxs-lookup"><span data-stu-id="8469d-257">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="8469d-258">De volgende stap is om de gevoelige gegevens te hashen en vervolgens de hashes voor indexering te uploaden.</span><span class="sxs-lookup"><span data-stu-id="8469d-258">The next step is to hash the sensitive data, and then upload the hashes for indexing.</span></span>

<span data-ttu-id="8469d-259">In de vorige procedure wordt in ons schema PatientRecords vijf velden gedefinieerd als doorzoekbaar: *PatientID,* *MRN, SSN,* *Telefoon* en *DOB.* </span><span class="sxs-lookup"><span data-stu-id="8469d-259">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="8469d-260">Ons voorbeeldregelpakket bevat deze velden en verwijst naar het databaseschemabestand **(edm.xml),** met één *ExactMatch-item* per doorzoekbaar veld.</span><span class="sxs-lookup"><span data-stu-id="8469d-260">Our example rule package includes those fields and references the database schema file (**edm.xml**), with one *ExactMatch* item per searchable field.</span></span> <span data-ttu-id="8469d-261">Houd rekening met het volgende ExactMatch-item:</span><span class="sxs-lookup"><span data-stu-id="8469d-261">Consider the following ExactMatch item:</span></span>

```xml
<ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
      <Pattern confidenceLevel="65">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
        <Any minMatches ="3" maxMatches ="100">
          <match matches="PatientID" />
          <match matches="MRN"/>
          <match matches="FirstName"/>
          <match matches="LastName"/>
          <match matches="Phone"/>
          <match matches="DOB"/>
        </Any>
      </Pattern>
    </ExactMatch>
```

<span data-ttu-id="8469d-262">Houd er in dit voorbeeld rekening mee dat:</span><span class="sxs-lookup"><span data-stu-id="8469d-262">In this example, note that:</span></span>

- <span data-ttu-id="8469d-263">De gegevensStore-naam verwijst naar het .csv bestand dat we eerder hebben gemaakt: **dataStore = "PatientRecords"**.</span><span class="sxs-lookup"><span data-stu-id="8469d-263">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="8469d-264">De idMatch-waarde verwijst naar een doorzoekbaar veld dat wordt weergegeven in het databaseschemabestand: **idMatch matches = "SSN"**.</span><span class="sxs-lookup"><span data-stu-id="8469d-264">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="8469d-265">De classificatiewaarde verwijst naar een bestaand of aangepast type gevoelige informatie: **classificatie = "U.S. Social Security Number (SSN)"**.</span><span class="sxs-lookup"><span data-stu-id="8469d-265">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="8469d-266">(In dit geval gebruiken we het bestaande type gevoelige informatie van het Amerikaanse sociale-zekerheidsnummer.)</span><span class="sxs-lookup"><span data-stu-id="8469d-266">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="8469d-267">Het kan 10 tot 60 minuten duren voordat het EDMSchema wordt bijgewerkt met toevoegingen.</span><span class="sxs-lookup"><span data-stu-id="8469d-267">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="8469d-268">De update moet worden voltooid voordat u stappen uitvoert die gebruikmaken van de toevoegingen.</span><span class="sxs-lookup"><span data-stu-id="8469d-268">The update must complete before you execute steps that use the additions.</span></span>
 
<span data-ttu-id="8469d-269">Nadat u uw regelpakket hebt geïmporteerd met uw EDM-gevoelige gegevenstype en uw gevoelige gegevenstabel hebt geïmporteerd, kunt u het nieuwe type testen met de functie **Test** in de wizard EDM in het compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="8469d-269">After you have imported your rule package with your EDM sensitive info type and have imported your sensitive data table, you can test your newly created type by using the **Test** function in the EDM wizard in the compliance center.</span></span> <span data-ttu-id="8469d-270">Zie [De wizard Exacte gegevensmatchschema en wizard Gevoelige](sit-edm-wizard.md) informatie gebruiken voor instructies over het gebruik van deze functionaliteit.</span><span class="sxs-lookup"><span data-stu-id="8469d-270">See [Use the Exact Data Match Schema and Sensitive Information Type Wizard](sit-edm-wizard.md) for instructions on using this functionality.</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="8469d-271">Het schema voor classificatie op basis van EDM bewerken</span><span class="sxs-lookup"><span data-stu-id="8469d-271">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="8469d-272">Als u wijzigingen wilt  aanbrengen in uwedm.xmlbestand, zoals het wijzigen van de velden die worden gebruikt voor op EDM gebaseerde classificatie, volgt u de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="8469d-272">If you want to make changes to your **edm.xml** file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

> [!TIP]
> <span data-ttu-id="8469d-273">U kunt uw EDM-schema en gegevensbestand wijzigen om te profiteren van **configureerbare overeenkomst.**</span><span class="sxs-lookup"><span data-stu-id="8469d-273">You can change your EDM schema and data file to take advantage of **configurable match**.</span></span> <span data-ttu-id="8469d-274">Wanneer EDM is geconfigureerd, worden caseverschillen en enkele scheidingstekens genegeerd wanneer een item wordt geëvalueerd.</span><span class="sxs-lookup"><span data-stu-id="8469d-274">When configured, EDM will ignore case differences and some delimiters when it evaluates an item.</span></span> <span data-ttu-id="8469d-275">Dit maakt het definiëren van uw xml-schema en uw gevoelige gegevensbestanden eenvoudiger.</span><span class="sxs-lookup"><span data-stu-id="8469d-275">This makes defining your xml schema and your sensitive data files easier.</span></span> <span data-ttu-id="8469d-276">Zie Schema voor exacte gegevensmatch wijzigen om configureerbare overeenkomst te gebruiken voor [meer informatie.](sit-modify-edm-schema-configurable-match.md)</span><span class="sxs-lookup"><span data-stu-id="8469d-276">To learn more see, [Modify Exact Data Match schema to use configurable match](sit-modify-edm-schema-configurable-match.md).</span></span>

1. <span data-ttu-id="8469d-277">Bewerk **uwedm.xml** bestand (dit is het bestand dat wordt besproken in de sectie Het [schema](#define-the-schema-for-your-database-of-sensitive-information) definiëren van dit artikel).</span><span class="sxs-lookup"><span data-stu-id="8469d-277">Edit your **edm.xml** file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="8469d-278">Verbinding maken met het Beveiligings- en compliancecentrum met behulp van de procedures in [Verbinding maken met Beveiligings- en compliancecentrum van PowerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="8469d-278">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

3. <span data-ttu-id="8469d-279">Als u het databaseschema wilt bijwerken, moet u de volgende cmdlets één voor één uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="8469d-279">To update your database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="8469d-280">U wordt als volgt gevraagd om dit te bevestigen:</span><span class="sxs-lookup"><span data-stu-id="8469d-280">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="8469d-281">Bevestigen</span><span class="sxs-lookup"><span data-stu-id="8469d-281">Confirm</span></span>
      >
      > <span data-ttu-id="8469d-282">Weet u zeker dat u deze actie wilt uitvoeren?</span><span class="sxs-lookup"><span data-stu-id="8469d-282">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="8469d-283">EDM-schema voor het gegevensopslag 'patiëntenrecords' wordt bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="8469d-283">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
      >
      > <span data-ttu-id="8469d-284">\[Y \] Yes A Yes to All N No L No to All \[ \] \[ \] \[ \] \[ ? \] Help (standaard is 'Y'):</span><span class="sxs-lookup"><span data-stu-id="8469d-284">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      > <span data-ttu-id="8469d-285">Als u wilt dat uw wijzigingen zonder bevestiging plaatsvinden, gebruikt u in stap 3 in plaats daarvan deze cmdlet: Set-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="8469d-285">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

      > [!NOTE]
      > <span data-ttu-id="8469d-286">Het kan 10 tot 60 minuten duren voordat het EDMSchema wordt bijgewerkt met toevoegingen.</span><span class="sxs-lookup"><span data-stu-id="8469d-286">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="8469d-287">De update moet worden voltooid voordat u stappen uitvoert die gebruikmaken van de toevoegingen.</span><span class="sxs-lookup"><span data-stu-id="8469d-287">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="8469d-288">Het schema voor classificatie op basis van EDM verwijderen</span><span class="sxs-lookup"><span data-stu-id="8469d-288">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="8469d-289">(Indien nodig) Als u het schema wilt verwijderen dat u gebruikt voor op EDM gebaseerde classificatie, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="8469d-289">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="8469d-290">Verbinding maken met het Beveiligings- en compliancecentrum met behulp van de procedures in [Verbinding maken met Beveiligings- en compliancecentrum van PowerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="8469d-290">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="8469d-291">Voer de volgende PowerShell-cmdlets uit en vervang de naam van de gegevensopslag van 'patiëntenrecords' met de cmdlets die u wilt verwijderen:</span><span class="sxs-lookup"><span data-stu-id="8469d-291">Run the following PowerShell cmdlets, substituting the data store name of "patient records" with the one you want to remove:</span></span>

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      <span data-ttu-id="8469d-292">U wordt gevraagd het volgende te bevestigen:</span><span class="sxs-lookup"><span data-stu-id="8469d-292">You will be prompted to confirm:</span></span>

      > <span data-ttu-id="8469d-293">Bevestigen</span><span class="sxs-lookup"><span data-stu-id="8469d-293">Confirm</span></span>
      >
      > <span data-ttu-id="8469d-294">Weet u zeker dat u deze actie wilt uitvoeren?</span><span class="sxs-lookup"><span data-stu-id="8469d-294">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="8469d-295">EDM-schema voor het gegevensopslag 'patiëntenrecords' wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="8469d-295">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
      >
      > <span data-ttu-id="8469d-296">\[Y \] Yes A Yes to All N No L No to All \[ \] \[ \] \[ \] \[ ? \] Help (standaard is 'Y'):</span><span class="sxs-lookup"><span data-stu-id="8469d-296">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      >  <span data-ttu-id="8469d-297">Als u wilt dat uw wijzigingen zonder bevestiging plaatsvinden, gebruikt u in stap 2 deze cmdlet: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span><span class="sxs-lookup"><span data-stu-id="8469d-297">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>

### <a name="part-2-hash-and-upload-the-sensitive-data"></a><span data-ttu-id="8469d-298">Deel 2: Hash en upload de gevoelige gegevens</span><span class="sxs-lookup"><span data-stu-id="8469d-298">Part 2: Hash and upload the sensitive data</span></span>

<span data-ttu-id="8469d-299">In deze fase stelt u een aangepaste beveiligingsgroep en gebruikersaccount in en stelt u het hulpprogramma EDM Upload Agent in.</span><span class="sxs-lookup"><span data-stu-id="8469d-299">In this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="8469d-300">Vervolgens gebruikt u het hulpprogramma om de gevoelige gegevens te hashen met een zoutwaarde en deze te uploaden.</span><span class="sxs-lookup"><span data-stu-id="8469d-300">Then, you use the tool to hash with salt value the sensitive data, and upload it.</span></span>

<span data-ttu-id="8469d-301">Het hashen en uploaden kan worden uitgevoerd met één computer of u kunt de stap voor hashing scheiden van de uploadstap voor meer beveiliging.</span><span class="sxs-lookup"><span data-stu-id="8469d-301">The hashing and uploading can be done using one computer or you can separate the hashing step from the upload step for greater security.</span></span>

<span data-ttu-id="8469d-302">Als u wilt hashen en uploaden vanaf één computer, moet u dit doen vanaf een computer die rechtstreeks verbinding kan maken met uw Microsoft 365 tenant.</span><span class="sxs-lookup"><span data-stu-id="8469d-302">If you want to hash and upload from one computer, you need to do it from a computer that can directly connect to your Microsoft 365 tenant.</span></span> <span data-ttu-id="8469d-303">Hiervoor moeten uw duidelijke tekstgevoelige gegevensbestanden op die computer staan voor hashing.</span><span class="sxs-lookup"><span data-stu-id="8469d-303">This requires that your clear text sensitive data files are on that computer for hashing.</span></span>

<span data-ttu-id="8469d-304">Als u het gevoelige gegevensbestand met duidelijke tekst niet wilt onthullen, kunt u het hashen op een computer op een veilige locatie en vervolgens het hashbestand en het zoutbestand kopiëren naar een computer die rechtstreeks verbinding kan maken met uw Microsoft 365-tenant voor uploaden.</span><span class="sxs-lookup"><span data-stu-id="8469d-304">If you do not want to expose your clear text sensitive data file, you can hash it on a computer in a secure location and then copy the hash file and the salt file to a computer that can directly connect to your Microsoft 365 tenant for upload.</span></span> <span data-ttu-id="8469d-305">In dit scenario hebt u de EDMUploadAgent op beide computers nodig.</span><span class="sxs-lookup"><span data-stu-id="8469d-305">In this scenario, you will need the EDMUploadAgent on both computers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8469d-306">Als u de wizard Exacte gegevensmatch en de wizard Gevoelige gegevenstype hebt gebruikt om uw schema- en patroonbestanden te maken, moet u ***het*** schema voor deze procedure downloaden.</span><span class="sxs-lookup"><span data-stu-id="8469d-306">If you used the Exact Data Match schema and sensitive information type wizard to create your schema and pattern files, you ***must*** download the schema for this procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="8469d-307">Als uw organisatie Klantsleutel heeft ingesteld voor Microsoft 365 op [tenantniveau,](customer-key-overview.md)wordt de versleutelingsfunctionaliteit van Exact data match automatisch gebruikt.</span><span class="sxs-lookup"><span data-stu-id="8469d-307">If your organization has set up [Customer Key for Microsoft 365 at the tenant level](customer-key-overview.md), Exact data match will make use of its encryption functionality automatically.</span></span> <span data-ttu-id="8469d-308">Dit is alleen beschikbaar voor E5-gelicentieerde tenants in de commerciële cloud.</span><span class="sxs-lookup"><span data-stu-id="8469d-308">This is available only to E5 licensed tenants in the Commercial cloud.</span></span>

#### <a name="prerequisites"></a><span data-ttu-id="8469d-309">Vereisten</span><span class="sxs-lookup"><span data-stu-id="8469d-309">Prerequisites</span></span>

- <span data-ttu-id="8469d-310">een werk- of schoolaccount voor Microsoft 365 dat wordt toegevoegd aan de **beveiligingsgroep EDM \_ DataUploaders**</span><span class="sxs-lookup"><span data-stu-id="8469d-310">a work or school account for Microsoft 365  that will be added to the **EDM\_DataUploaders** security group</span></span>
- <span data-ttu-id="8469d-311">een Windows 10 of Windows Server 2016 met .NET versie 4.6.2 voor het uitvoeren van de EDMUploadAgent</span><span class="sxs-lookup"><span data-stu-id="8469d-311">a Windows 10 or Windows Server 2016 machine with .NET version 4.6.2 for running the EDMUploadAgent</span></span>
- <span data-ttu-id="8469d-312">een adreslijst op uw uploadmachine voor het volgende:</span><span class="sxs-lookup"><span data-stu-id="8469d-312">a directory on your upload machine for the:</span></span>
    -  <span data-ttu-id="8469d-313">EDMUploadAgent</span><span class="sxs-lookup"><span data-stu-id="8469d-313">EDMUploadAgent</span></span>
    - <span data-ttu-id="8469d-314">uw gevoelige itembestand in .csv of .tsv-indeling, **PatientRecords.csv** in onze voorbeelden</span><span class="sxs-lookup"><span data-stu-id="8469d-314">your sensitive item file in .csv or .tsv format, **PatientRecords.csv** in our examples</span></span>
    -  <span data-ttu-id="8469d-315">en de uitvoerhash- en zoutbestanden</span><span class="sxs-lookup"><span data-stu-id="8469d-315">and the output hash and salt files</span></span>
    - <span data-ttu-id="8469d-316">de gegevensstorenaam uit **hetedm.xml** bestand, voor dit voorbeeld de naam `PatientRecords`</span><span class="sxs-lookup"><span data-stu-id="8469d-316">the datastore name from the **edm.xml** file, for this example its `PatientRecords`</span></span>
- <span data-ttu-id="8469d-317">Als u de wizard Exacte gegevensmatch en de wizard [Gevoelige gegevenstype hebt gebruikt,](sit-edm-wizard.md) ***moet u het*** downloaden</span><span class="sxs-lookup"><span data-stu-id="8469d-317">If you used the [Exact Data Match schema and sensitive information type wizard](sit-edm-wizard.md) you ***must*** download it</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="8469d-318">De beveiligingsgroep en het gebruikersaccount instellen</span><span class="sxs-lookup"><span data-stu-id="8469d-318">Set up the security group and user account</span></span>

1. <span data-ttu-id="8469d-319">Als globale beheerder gaat u naar het beheercentrum met de juiste [koppeling](#portal-links-for-your-subscription) voor uw abonnement en maakt u een [beveiligingsgroep](/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) met de naam **EDM \_ DataUploaders.**</span><span class="sxs-lookup"><span data-stu-id="8469d-319">As a global administrator, go to the admin center using the appropriate [link for your subscription](#portal-links-for-your-subscription) and [create a security group](/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called **EDM\_DataUploaders**.</span></span>

2. <span data-ttu-id="8469d-320">Voeg een of meer gebruikers toe aan de **beveiligingsgroep EDM \_ DataUploaders.**</span><span class="sxs-lookup"><span data-stu-id="8469d-320">Add one or more users to the **EDM\_DataUploaders** security group.</span></span> <span data-ttu-id="8469d-321">(Deze gebruikers beheren de database met gevoelige informatie.)</span><span class="sxs-lookup"><span data-stu-id="8469d-321">(These users will manage the database of sensitive information.)</span></span>

#### <a name="hash-and-upload-from-one-computer"></a><span data-ttu-id="8469d-322">Hash en upload vanaf één computer</span><span class="sxs-lookup"><span data-stu-id="8469d-322">Hash and upload from one computer</span></span>

<span data-ttu-id="8469d-323">Deze computer moet directe toegang hebben tot uw Microsoft 365 tenant.</span><span class="sxs-lookup"><span data-stu-id="8469d-323">This computer must have direct access to your Microsoft 365 tenant.</span></span>

>[!NOTE]
> <span data-ttu-id="8469d-324">Voordat u deze procedure start, moet u ervoor zorgen dat u lid bent van de **beveiligingsgroep EDM \_ DataUploaders.**</span><span class="sxs-lookup"><span data-stu-id="8469d-324">Before you begin this procedure, make sure that you are a member of the **EDM\_DataUploaders** security group.</span></span>

> [!TIP]
> <span data-ttu-id="8469d-325">Desgewenst kunt u een validatie uitvoeren op uw .csv of .tsv-bestand voordat u het uploadt door het volgende uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="8469d-325">Optionally, you can run a validation against your .csv or .tsv file before uploading by running:</span></span>
>
>`EdmUploadAgent.exe /ValidateData /DataFile [data file] /Schema [schema file]`
>
><span data-ttu-id="8469d-326">Voor meer informatie over alle EdmUploadAgent.exe >ondersteunde parameters uitvoeren</span><span class="sxs-lookup"><span data-stu-id="8469d-326">For more information on all the EdmUploadAgent.exe >supported parameters run</span></span>
>
> `EdmUploadAgent.exe /?`


#### <a name="links-to-edm-upload-agent-by-subscription-type"></a><span data-ttu-id="8469d-327">Koppelingen naar EDM-uploadagent per abonnementstype</span><span class="sxs-lookup"><span data-stu-id="8469d-327">Links to EDM upload agent by subscription type</span></span>

- <span data-ttu-id="8469d-328">[Commercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - de meeste commerciële klanten moeten dit gebruiken</span><span class="sxs-lookup"><span data-stu-id="8469d-328">[Commercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - most commercial customers should use this</span></span>
- <span data-ttu-id="8469d-329">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - Dit is specifiek voor abonnees van de cloud van de overheid met hoge beveiliging</span><span class="sxs-lookup"><span data-stu-id="8469d-329">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - This is specifically for high security government cloud subscribers</span></span>
- <span data-ttu-id="8469d-330">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - dit is specifiek voor klanten van de cloud van het Department of Defense van de Verenigde Staten</span><span class="sxs-lookup"><span data-stu-id="8469d-330">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - this is specifically for United States Department of Defense cloud customers</span></span>

1. <span data-ttu-id="8469d-331">Maak een werkmap voor de EDMUploadAgent.</span><span class="sxs-lookup"><span data-stu-id="8469d-331">Create a working directory for the EDMUploadAgent.</span></span> <span data-ttu-id="8469d-332">Bijvoorbeeld **C:\EDM\Data.**</span><span class="sxs-lookup"><span data-stu-id="8469d-332">For example, **C:\EDM\Data**.</span></span> <span data-ttu-id="8469d-333">Plaats het **PatientRecords.csv** daar.</span><span class="sxs-lookup"><span data-stu-id="8469d-333">Place the **PatientRecords.csv** file there.</span></span>

2. <span data-ttu-id="8469d-334">Download en installeer de juiste [EDM-Upload agent](#links-to-edm-upload-agent-by-subscription-type) voor uw abonnement in de adreslijst die u in stap 1 hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="8469d-334">Download and install the appropriate [EDM Upload Agent](#links-to-edm-upload-agent-by-subscription-type) for your subscription into the directory you created in step 1.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8469d-335">De EDMUploadAgent op de bovenstaande koppelingen is bijgewerkt om automatisch een zoute waarde toe te voegen aan de gehashte gegevens.</span><span class="sxs-lookup"><span data-stu-id="8469d-335">The EDMUploadAgent at the above links has been updated to automatically add a salt value to the hashed data.</span></span> <span data-ttu-id="8469d-336">U kunt ook uw eigen zoutwaarde leveren.</span><span class="sxs-lookup"><span data-stu-id="8469d-336">Alternately, you can provide your own salt value.</span></span> <span data-ttu-id="8469d-337">Wanneer u deze versie hebt gebruikt, kunt u de vorige versie van de EDMUploadAgent niet meer gebruiken.</span><span class="sxs-lookup"><span data-stu-id="8469d-337">Once you have used this version, you will not be able to use the previous version of the EDMUploadAgent.</span></span>
   >
   > <span data-ttu-id="8469d-338">U kunt gegevens met de EDMUploadAgent slechts twee keer per dag uploaden naar een bepaalde gegevensopslag.</span><span class="sxs-lookup"><span data-stu-id="8469d-338">You can upload data with the EDMUploadAgent to any given data store only twice per day.</span></span>

   > [!TIP]
   > <span data-ttu-id="8469d-339">Als u een lijst wilt halen uit de ondersteunde opdrachtparameters, moet u de agent geen argumenten geven.</span><span class="sxs-lookup"><span data-stu-id="8469d-339">To a get a list out of the supported command parameters, run the agent no arguments.</span></span> <span data-ttu-id="8469d-340">Bijvoorbeeld 'EdmUploadAgent.exe'.</span><span class="sxs-lookup"><span data-stu-id="8469d-340">For example 'EdmUploadAgent.exe'.</span></span>

2. <span data-ttu-id="8469d-341">Machtig de EDM-Upload agent, open het venster Opdrachtprompt (als beheerder), schakel over naar de **adreslijst C:\EDM\Data** en voer vervolgens de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="8469d-341">Authorize the EDM Upload Agent, open  Command Prompt window (as an administrator), switch to the **C:\EDM\Data** directory and then run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="8469d-342">Meld u aan met uw werk- of schoolaccount voor Microsoft 365 die is toegevoegd aan de EDM_DataUploaders beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="8469d-342">Sign in with your work or school account for Microsoft 365 that was added to the EDM_DataUploaders security group.</span></span> <span data-ttu-id="8469d-343">Uw tenantgegevens worden uit het gebruikersaccount gehaald om de verbinding te maken.</span><span class="sxs-lookup"><span data-stu-id="8469d-343">Your tenant information is extracted from the user account to make the connection.</span></span>

   <span data-ttu-id="8469d-344">OPTIONEEL: Als u de wizard Exacte gegevensmatch en de wizard Gevoelige gegevenstype hebt gebruikt om uw schema- en patroonbestanden te maken, voer dan de volgende opdracht uit in een opdrachtpromptvenster:</span><span class="sxs-lookup"><span data-stu-id="8469d-344">OPTIONAL: If you used the Exact Data Match schema and sensitive information type wizard to create your schema and pattern files, run the following command in a Command Prompt window:</span></span>

   `EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>`

4. <span data-ttu-id="8469d-345">Als u de gevoelige gegevens wilt hashen en uploaden, voer u de volgende opdracht uit in het venster Opdrachtprompt:</span><span class="sxs-lookup"><span data-stu-id="8469d-345">To hash and upload the sensitive data, run the following command in Command Prompt window:</span></span>

   `EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file] /ColumnSeparator ["{Tab}"|"|"]`

   <span data-ttu-id="8469d-346">Voorbeeld: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span><span class="sxs-lookup"><span data-stu-id="8469d-346">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span></span>

   <span data-ttu-id="8469d-347">De standaardindeling voor het gevoelige gegevensbestand is door komma's gescheiden waarden.</span><span class="sxs-lookup"><span data-stu-id="8469d-347">The default format for the sensitive data file is comma-separated values.</span></span> <span data-ttu-id="8469d-348">U kunt een bestand met tabs opgeven door de optie {Tab}" aan te geven met de parameter /ColumnSeparator, of u kunt een door een pijp gescheiden bestand opgeven door de optie '|' aan te geven.</span><span class="sxs-lookup"><span data-stu-id="8469d-348">You can specify a tab-separated file by indicating the "{Tab}" option with the /ColumnSeparator parameter, or you can specify a pipe-separated file by indicating the "|" option.</span></span>  
   <span data-ttu-id="8469d-349">Deze opdracht voegt automatisch een willekeurig gegenereerde zoutwaarde toe aan de hash voor meer beveiliging.</span><span class="sxs-lookup"><span data-stu-id="8469d-349">This command will automatically add a randomly generated salt value to the hash for greater security.</span></span> <span data-ttu-id="8469d-350">Als u desgewenst uw eigen zoutwaarde wilt gebruiken, voegt u de **/Salt <saltvalue>** toe aan de opdracht.</span><span class="sxs-lookup"><span data-stu-id="8469d-350">Optionally, if you want to use your own salt value, add the **/Salt <saltvalue>** to the command.</span></span> <span data-ttu-id="8469d-351">Deze waarde moet 64 tekens lang zijn en mag alleen de a-z-tekens en 0-9 tekens bevatten.</span><span class="sxs-lookup"><span data-stu-id="8469d-351">This value must be 64 characters in length and can only contain the a-z characters and 0-9 characters.</span></span>

5. <span data-ttu-id="8469d-352">Controleer de uploadstatus door deze opdracht uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="8469d-352">Check the upload status by running this command:</span></span>

   `EdmUploadAgent.exe /GetSession /DataStoreName \<DataStoreName\>`

   <span data-ttu-id="8469d-353">Voorbeeld: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span><span class="sxs-lookup"><span data-stu-id="8469d-353">Example: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span></span>

   <span data-ttu-id="8469d-354">Zoek naar de status in **ProcessingInProgress.**</span><span class="sxs-lookup"><span data-stu-id="8469d-354">Look for the status to be in **ProcessingInProgress**.</span></span> <span data-ttu-id="8469d-355">Controleer opnieuw om de paar minuten totdat de status wordt gewijzigd in **Voltooid.**</span><span class="sxs-lookup"><span data-stu-id="8469d-355">Check again every few minutes until the status changes to **Completed**.</span></span> <span data-ttu-id="8469d-356">Wanneer de status is voltooid, zijn uw EDM-gegevens klaar voor gebruik.</span><span class="sxs-lookup"><span data-stu-id="8469d-356">Once the status is completed, your EDM data is ready for use.</span></span>

#### <a name="separate-hash-and-upload"></a><span data-ttu-id="8469d-357">Hash scheiden en uploaden</span><span class="sxs-lookup"><span data-stu-id="8469d-357">Separate Hash and upload</span></span>

<span data-ttu-id="8469d-358">Voer de hash uit op een computer in een veilige omgeving.</span><span class="sxs-lookup"><span data-stu-id="8469d-358">Perform the hash on a computer in a secure environment.</span></span>

<span data-ttu-id="8469d-359">OPTIONEEL: Als u de wizard Exacte gegevensmatch en de wizard Gevoelige gegevenstype hebt gebruikt om uw schema- en patroonbestanden te maken, voer dan de volgende opdracht uit in een opdrachtpromptvenster:</span><span class="sxs-lookup"><span data-stu-id="8469d-359">OPTIONAL: If you used the Exact Data Match schema and sensitive information type wizard to create your schema and pattern files, run the following command in a Command Prompt window:</span></span>

`EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>`

1. <span data-ttu-id="8469d-360">Voer de volgende opdracht uit in opdrachtpromptvensters:</span><span class="sxs-lookup"><span data-stu-id="8469d-360">Run the following command in Command Prompt windows:</span></span>

   `EdmUploadAgent.exe /CreateHash /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file] >`

   <span data-ttu-id="8469d-361">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8469d-361">For example:</span></span>

   > <span data-ttu-id="8469d-362">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span><span class="sxs-lookup"><span data-stu-id="8469d-362">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span></span>

   <span data-ttu-id="8469d-363">Hiermee worden een gehasht bestand en een zoutbestand met deze extensies uitgevoerd als u de optie **/Zout <saltvalue>** niet hebt opgegeven:</span><span class="sxs-lookup"><span data-stu-id="8469d-363">This will output a hashed file and a salt file with these extensions if you didn't specify the **/Salt <saltvalue>** option:</span></span>
   - <span data-ttu-id="8469d-364">. EdmHash</span><span class="sxs-lookup"><span data-stu-id="8469d-364">.EdmHash</span></span>
   - <span data-ttu-id="8469d-365">. EdmSalt</span><span class="sxs-lookup"><span data-stu-id="8469d-365">.EdmSalt</span></span>

2. <span data-ttu-id="8469d-366">Kopieer deze bestanden op een veilige manier naar de computer die u gebruikt om uw gevoelige items .csv of .tsv-bestand (PatientRecords) naar uw tenant te uploaden.</span><span class="sxs-lookup"><span data-stu-id="8469d-366">Copy these files in a secure fashion to the computer you will use to upload your sensitive items .csv or .tsv file (PatientRecords) to your tenant.</span></span>

   <span data-ttu-id="8469d-367">Als u de gehashte gegevens wilt uploaden, moet u de volgende opdracht uitvoeren in Windows opdrachtprompt:</span><span class="sxs-lookup"><span data-stu-id="8469d-367">To upload the hashed data, run the following command in Windows Command Prompt:</span></span>

   `EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

   <span data-ttu-id="8469d-368">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8469d-368">For example:</span></span>

   > <span data-ttu-id="8469d-369">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C: \\ Edm \\ Hash \\ PatientRecords.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="8469d-369">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span></span>


   <span data-ttu-id="8469d-370">Voer de volgende opdracht uit in het venster Opdrachtprompt om te controleren of uw gevoelige gegevens zijn geüpload:</span><span class="sxs-lookup"><span data-stu-id="8469d-370">To verify that your sensitive data has been uploaded, run the following command in Command Prompt window:</span></span>

   `EdmUploadAgent.exe /GetDataStore`

   <span data-ttu-id="8469d-371">U ziet een lijst met gegevensopslag en wanneer deze voor het laatst zijn bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="8469d-371">You'll see a list of data stores and when they were last updated.</span></span>

   <span data-ttu-id="8469d-372">Als u alle gegevens uploads naar een bepaalde winkel wilt zien, voer dan de volgende opdracht uit in Windows opdrachtprompt:</span><span class="sxs-lookup"><span data-stu-id="8469d-372">If you want to see all the data uploads to a particular store, run the following command in a Windows command prompt:</span></span>

   `EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>`

   <span data-ttu-id="8469d-373">Ga verder met het instellen van uw proces en planning voor [het vernieuwen van de database met gevoelige informatie.](#refreshing-your-sensitive-information-database)</span><span class="sxs-lookup"><span data-stu-id="8469d-373">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="8469d-374">Op dit moment kunt u de classificatie op basis van EDM gebruiken met uw Microsoft-cloudservices.</span><span class="sxs-lookup"><span data-stu-id="8469d-374">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="8469d-375">U kunt bijvoorbeeld een [DLP-beleid instellen met EDM-classificatie.](#to-create-a-dlp-policy-with-edm)</span><span class="sxs-lookup"><span data-stu-id="8469d-375">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="8469d-376">Uw database met gevoelige informatie vernieuwen</span><span class="sxs-lookup"><span data-stu-id="8469d-376">Refreshing your sensitive information database</span></span>

<span data-ttu-id="8469d-377">U kunt de database met gevoelige gegevens dagelijks vernieuwen en met het EDM-Upload kunt u de gevoelige gegevens opnieuw indexeren en vervolgens de geïndexeerde gegevens opnieuw uploaden.</span><span class="sxs-lookup"><span data-stu-id="8469d-377">You can refresh your sensitive information database daily, and the EDM Upload Tool can reindex the sensitive data and then reupload the indexed data.</span></span>

1. <span data-ttu-id="8469d-378">Bepaal uw proces en frequentie (dagelijks of wekelijks) voor het vernieuwen van de database met gevoelige informatie.</span><span class="sxs-lookup"><span data-stu-id="8469d-378">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="8469d-379">Export de gevoelige gegevens opnieuw naar een app, zoals Microsoft Excel, en sla het bestand op in een .csv of .tsv-indeling.</span><span class="sxs-lookup"><span data-stu-id="8469d-379">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv or .tsv format.</span></span> <span data-ttu-id="8469d-380">Bewaar dezelfde bestandsnaam en locatie die u hebt gebruikt toen u de stappen in Hash hebt gevolgd [en de gevoelige gegevens uploadt.](#part-2-hash-and-upload-the-sensitive-data)</span><span class="sxs-lookup"><span data-stu-id="8469d-380">Keep the same file name and location you used when you followed the steps described in [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data).</span></span>

      > [!NOTE]
      > <span data-ttu-id="8469d-381">Als er geen wijzigingen zijn aangebracht in de structuur (veldnamen) van het .csv- of TSV-bestand, hoeft u geen wijzigingen aan te brengen in het databaseschemabestand wanneer u de gegevens vernieuwt.</span><span class="sxs-lookup"><span data-stu-id="8469d-381">If there are no changes to the structure (field names) of the .csv or .tsv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="8469d-382">Maar als u wijzigingen moet aanbrengen, moet u het databaseschema en het regelpakket dienovereenkomstig bewerken.</span><span class="sxs-lookup"><span data-stu-id="8469d-382">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="8469d-383">Gebruik [Taakplanning om stap](/windows/desktop/TaskSchd/task-scheduler-start-page) 2 en 3 in de hash te automatiseren en de gevoelige [gegevensprocedure te](#part-2-hash-and-upload-the-sensitive-data) uploaden.</span><span class="sxs-lookup"><span data-stu-id="8469d-383">Use [Task Scheduler](/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="8469d-384">U kunt taken op verschillende manieren plannen:</span><span class="sxs-lookup"><span data-stu-id="8469d-384">You can schedule tasks using several methods:</span></span>

      | <span data-ttu-id="8469d-385">Methode</span><span class="sxs-lookup"><span data-stu-id="8469d-385">Method</span></span>             | <span data-ttu-id="8469d-386">Wat moet u doen?</span><span class="sxs-lookup"><span data-stu-id="8469d-386">What to do</span></span> |
      | ---------------------- | ---------------- |
      | <span data-ttu-id="8469d-387">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8469d-387">Windows PowerShell</span></span>     | <span data-ttu-id="8469d-388">Zie de [documentatie van ScheduledTasks](/powershell/module/scheduledtasks/?view=win10-ps) en het [voorbeeld van PowerShell-script](#example-powershell-script-for-task-scheduler) in dit artikel</span><span class="sxs-lookup"><span data-stu-id="8469d-388">See the [ScheduledTasks](/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span> |
      | <span data-ttu-id="8469d-389">Task Scheduler API</span><span class="sxs-lookup"><span data-stu-id="8469d-389">Task Scheduler API</span></span>     | <span data-ttu-id="8469d-390">Zie de [documentatie van Taakplanning](/windows/desktop/TaskSchd/using-the-task-scheduler)</span><span class="sxs-lookup"><span data-stu-id="8469d-390">See the [Task Scheduler](/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>                                                                                                                                                                                                                                                                                |
      | <span data-ttu-id="8469d-391">Windows gebruikersinterface</span><span class="sxs-lookup"><span data-stu-id="8469d-391">Windows user interface</span></span> | <span data-ttu-id="8469d-392">Klik Windows op **Start** en typ Taakplanning.</span><span class="sxs-lookup"><span data-stu-id="8469d-392">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="8469d-393">Klik vervolgens in de lijst met resultaten met de rechtermuisknop op **Taakplanning** en kies **Uitvoeren als beheerder.**</span><span class="sxs-lookup"><span data-stu-id="8469d-393">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="8469d-394">Voorbeeld van PowerShell-script voor taakplanning</span><span class="sxs-lookup"><span data-stu-id="8469d-394">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="8469d-395">Deze sectie bevat een voorbeeld van PowerShell-script dat u kunt gebruiken om uw taken te plannen voor het hashen van gegevens en het uploaden van de gehashte gegevens:</span><span class="sxs-lookup"><span data-stu-id="8469d-395">This section includes an example PowerShell script you can use to schedule your tasks for hashing data and uploading the hashed data:</span></span>

##### <a name="to-schedule-hashing-and-upload-in-a-combined-step"></a><span data-ttu-id="8469d-396">Hashing plannen en uploaden in een gecombineerde stap</span><span class="sxs-lookup"><span data-stu-id="8469d-396">To schedule hashing and upload in a combined step</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$schemaext = '.xml'
\# Assuming file name is same as data store name and file is in .csv format
$dataFile = "$fileLocation\\$dataStoreName$csvext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
\# Assuming Schema file name is same as data store name
$schemaFile = "$fileLocation\\$dataStoreName$schemaext"
$uploadDataArgs = '/UploadData /DataStoreName ' + $dataStoreName + ' /DataFile ' + $dataFile + ' /HashLocation' + $hashLocation + ' /Schema ' + $schemaFile
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadDataArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```

#### <a name="to-schedule-hashing-and-upload-as-separate-steps"></a><span data-ttu-id="8469d-397">Hashing plannen en uploaden als afzonderlijke stappen</span><span class="sxs-lookup"><span data-stu-id="8469d-397">To schedule hashing and upload as separate steps</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$edmext = '.EdmHash'
$schemaext = '.xml'
\# Assuming file name is same as data store name and file is in .csv format
$dataFile = "$fileLocation\\$dataStoreName$csvext"
$hashFile = "$fileLocation\\$dataStoreName$edmext"
\# Assuming Schema file name is same as data store name
$schemaFile = "$fileLocation\\$dataStoreName$schemaext "

\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$createHashArgs = '/CreateHash' + ' /DataFile ' + $dataFile + ' /HashLocation ' + $hashLocation + ' /Schema ' + $schemaFile
$uploadHashArgs = '/UploadHash /DataStoreName ' + $dataStoreName + ' /HashFile ' + $hashFile
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $createHashArgs -WorkingDirectory $edminstallpath
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadHashArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password

```

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="8469d-398">Deel 3: Classificatie op basis van EDM gebruiken met uw Microsoft-cloudservices</span><span class="sxs-lookup"><span data-stu-id="8469d-398">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="8469d-399">Deze locaties ondersteunen EDM-gevoelige informatietypen:</span><span class="sxs-lookup"><span data-stu-id="8469d-399">These locations are support EDM sensitive information types:</span></span>

- <span data-ttu-id="8469d-400">DLP voor Exchange Online (e-mail)</span><span class="sxs-lookup"><span data-stu-id="8469d-400">DLP for Exchange Online (email)</span></span>
- <span data-ttu-id="8469d-401">OneDrive voor Bedrijven (bestanden)</span><span class="sxs-lookup"><span data-stu-id="8469d-401">OneDrive for Business (files)</span></span>
- <span data-ttu-id="8469d-402">Microsoft Teams (gesprekken)</span><span class="sxs-lookup"><span data-stu-id="8469d-402">Microsoft Teams (conversations)</span></span>
- <span data-ttu-id="8469d-403">DLP voor SharePoint (bestanden)</span><span class="sxs-lookup"><span data-stu-id="8469d-403">DLP for SharePoint (files)</span></span>
- <span data-ttu-id="8469d-404">Microsoft Cloud App Security DLP-beleid</span><span class="sxs-lookup"><span data-stu-id="8469d-404">Microsoft Cloud App Security DLP policies</span></span>
- <span data-ttu-id="8469d-405">Beleid voor automatisch labelen op de server - beschikbaar voor commerciële cloudklanten</span><span class="sxs-lookup"><span data-stu-id="8469d-405">Server-side auto-labeling policies - available for commercial cloud customers</span></span> <!--, UNCOMMENT THIS ON 6/15 and government cloud customers-->

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="8469d-406">Een DLP-beleid maken met EDM</span><span class="sxs-lookup"><span data-stu-id="8469d-406">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="8469d-407">Ga naar het Beveiligings- & compliancecentrum met de juiste [koppeling voor uw abonnement.](#portal-links-for-your-subscription)</span><span class="sxs-lookup"><span data-stu-id="8469d-407">Go to the Security & Compliance Center using the appropriate [link for your subscription](#portal-links-for-your-subscription).</span></span>

2. <span data-ttu-id="8469d-408">Kies **Beleid voor preventie van** \> **gegevensverlies.**</span><span class="sxs-lookup"><span data-stu-id="8469d-408">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="8469d-409">Kies **Een beleid aangepaste** \> **volgende** \> **maken.**</span><span class="sxs-lookup"><span data-stu-id="8469d-409">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="8469d-410">Geef op **het tabblad Naam** uw beleid een naam en beschrijving op en kies **volgende**.</span><span class="sxs-lookup"><span data-stu-id="8469d-410">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="8469d-411">Selecteer op **het tabblad** Locaties kiezen de optie Laat mij specifieke **locaties kiezen** en kies vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="8469d-411">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="8469d-412">Selecteer in **de kolom** Status **Exchange e-mail, OneDrive accounts, Teams chat-** en kanaalbericht en kies vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="8469d-412">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message**, and then choose **Next**.</span></span>

7. <span data-ttu-id="8469d-413">Kies op **het tabblad** Beleidsinstellingen de optie Geavanceerde **instellingen gebruiken** en kies vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="8469d-413">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="8469d-414">Kies **+ Nieuwe regel**.</span><span class="sxs-lookup"><span data-stu-id="8469d-414">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="8469d-415">Geef in **de** sectie Naam een naam en beschrijving op voor de regel.</span><span class="sxs-lookup"><span data-stu-id="8469d-415">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="8469d-416">Kies in **de sectie** Voorwaarden in de lijst + **Een voorwaarde** toevoegen de optie Inhoud bevat **gevoelig type.**</span><span class="sxs-lookup"><span data-stu-id="8469d-416">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span>

      ![Inhoud bevat gevoelige informatietypen](../media/edm-dlp-newrule-conditions.png)

11. <span data-ttu-id="8469d-418">Zoek naar het gevoelige informatietype dat u hebt gemaakt bij het instellen van het regelpakket en kies **vervolgens + Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="8469d-418">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>  
    <span data-ttu-id="8469d-419">Kies vervolgens **Klaar**.</span><span class="sxs-lookup"><span data-stu-id="8469d-419">Then choose **Done**.</span></span>

12. <span data-ttu-id="8469d-420">Selecteer de opties voor uw regel, zoals Gebruikersmeldingen, Gebruiker **overschrijven,** **Incidentrapporten,** en kies **vervolgens Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="8469d-420">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="8469d-421">Controleer op **het tabblad** Beleidsinstellingen uw regels en kies **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="8469d-421">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="8469d-422">Geef op of u het beleid meteen wilt in- of uitschakelen, of uitgeschakeld wilt houden.</span><span class="sxs-lookup"><span data-stu-id="8469d-422">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="8469d-423">Kies vervolgens **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="8469d-423">Then choose **Next**.</span></span>

15. <span data-ttu-id="8469d-424">Controleer uw **beleid op het** tabblad Uw instellingen controleren.</span><span class="sxs-lookup"><span data-stu-id="8469d-424">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="8469d-425">Breng de benodigde wijzigingen aan.</span><span class="sxs-lookup"><span data-stu-id="8469d-425">Make any needed changes.</span></span> <span data-ttu-id="8469d-426">Wanneer u klaar bent, kiest u **Maken.**</span><span class="sxs-lookup"><span data-stu-id="8469d-426">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="8469d-427">Sta ongeveer één uur toe dat uw nieuwe DLP-beleid zijn weg door uw datacenter kan vinden.</span><span class="sxs-lookup"><span data-stu-id="8469d-427">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="8469d-428">Aanverwante artikelen</span><span class="sxs-lookup"><span data-stu-id="8469d-428">Related articles</span></span>

- [<span data-ttu-id="8469d-429">Definities van entiteiten van het type gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="8469d-429">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="8469d-430">Meer informatie over typen gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="8469d-430">Learn about sensitive information types</span></span>](sensitive-information-type-learn-about.md)
- [<span data-ttu-id="8469d-431">Meer informatie over preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="8469d-431">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="8469d-432">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="8469d-432">Microsoft Cloud App Security</span></span>](/cloud-app-security)
- [<span data-ttu-id="8469d-433">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="8469d-433">New-DlpEdmSchema</span></span>](/powershell/module/exchange/new-dlpedmschema)
- [<span data-ttu-id="8469d-434">Schema exacte gegevensmatch wijzigen om configureerbare overeenkomst te gebruiken</span><span class="sxs-lookup"><span data-stu-id="8469d-434">Modify Exact Data Match schema to use configurable match</span></span>](sit-modify-edm-schema-configurable-match.md)
