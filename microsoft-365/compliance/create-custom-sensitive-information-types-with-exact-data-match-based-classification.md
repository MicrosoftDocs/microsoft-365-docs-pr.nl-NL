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
ms.openlocfilehash: ff190fa85e631562a07dcecc1f75713ecacdf07e
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822115"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="445dd-103">Aangepaste gevoelige informatietypen maken met een classificatie op basis van Exacte gegevensmatch</span><span class="sxs-lookup"><span data-stu-id="445dd-103">Create custom sensitive information types with Exact Data Match based classification</span></span>



<span data-ttu-id="445dd-104">[Aangepaste gevoelige informatietypen worden](sensitive-information-type-learn-about.md) gebruikt om gevoelige items te identificeren, zodat u kunt voorkomen dat ze per ongeluk of ongepast worden gedeeld.</span><span class="sxs-lookup"><span data-stu-id="445dd-104">[Custom sensitive information types](sensitive-information-type-learn-about.md) are used to help identify sensitive items so that you can prevent them from being inadvertently or inappropriately shared.</span></span> <span data-ttu-id="445dd-105">U definieert een aangepast type gevoelige informatie op basis van:</span><span class="sxs-lookup"><span data-stu-id="445dd-105">You define a custom sensitive information type based on:</span></span>

- <span data-ttu-id="445dd-106">patronen</span><span class="sxs-lookup"><span data-stu-id="445dd-106">patterns</span></span>
- <span data-ttu-id="445dd-107">trefwoordbewijs, *zoals werknemer,* *badge* of *id*</span><span class="sxs-lookup"><span data-stu-id="445dd-107">keyword evidence such as *employee*, *badge*, or *ID*</span></span>
- <span data-ttu-id="445dd-108">teken nabijheid van bewijs in een bepaald patroon</span><span class="sxs-lookup"><span data-stu-id="445dd-108">character proximity to evidence in a particular pattern</span></span>
- <span data-ttu-id="445dd-109">betrouwbaarheidsniveaus</span><span class="sxs-lookup"><span data-stu-id="445dd-109">confidence levels</span></span>

 <span data-ttu-id="445dd-110">Dergelijke aangepaste gevoelige informatietypen voldoen aan de zakelijke behoeften van veel organisaties.</span><span class="sxs-lookup"><span data-stu-id="445dd-110">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="445dd-111">Maar wat als u een aangepast type gevoelige informatie (SIT) wilt dat exacte gegevenswaarden gebruikt, in plaats van een type dat overeenkomsten op basis van algemene patronen heeft gevonden?</span><span class="sxs-lookup"><span data-stu-id="445dd-111">But what if you wanted a custom sensitive information type (SIT) that uses exact data values, instead of one that found matches based on generic patterns?</span></span> <span data-ttu-id="445dd-112">Met de classificatie Exact Data Match (EDM) kunt u een aangepast type gevoelige informatie maken dat is ontworpen voor:</span><span class="sxs-lookup"><span data-stu-id="445dd-112">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="445dd-113">dynamisch en eenvoudig worden vernieuwd</span><span class="sxs-lookup"><span data-stu-id="445dd-113">be dynamic and easily refreshed</span></span>
- <span data-ttu-id="445dd-114">schaalbaarder zijn</span><span class="sxs-lookup"><span data-stu-id="445dd-114">be more scalable</span></span>
- <span data-ttu-id="445dd-115">leiden tot minder onwaar-positieven</span><span class="sxs-lookup"><span data-stu-id="445dd-115">result in fewer false-positives</span></span>
- <span data-ttu-id="445dd-116">werken met gestructureerde gevoelige gegevens</span><span class="sxs-lookup"><span data-stu-id="445dd-116">work with structured sensitive data</span></span>
- <span data-ttu-id="445dd-117">gevoelige informatie veiliger verwerken</span><span class="sxs-lookup"><span data-stu-id="445dd-117">handle sensitive information more securely</span></span>
- <span data-ttu-id="445dd-118">worden gebruikt met verschillende Microsoft-cloudservices</span><span class="sxs-lookup"><span data-stu-id="445dd-118">be used with several Microsoft cloud services</span></span>

![Classificatie op basis van EDM](../media/EDMClassification.png)

<span data-ttu-id="445dd-120">Met EDM-classificatie kunt u aangepaste gevoelige informatietypen maken die verwijzen naar exacte waarden in een database met gevoelige informatie.</span><span class="sxs-lookup"><span data-stu-id="445dd-120">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="445dd-121">De database kan dagelijks worden vernieuwd en maximaal 100 miljoen rijen met gegevens bevatten.</span><span class="sxs-lookup"><span data-stu-id="445dd-121">The database can be refreshed daily, and contain up to 100 million rows of data.</span></span> <span data-ttu-id="445dd-122">Als werknemers, patiënten of klanten komen en gaan en records veranderen, blijven uw aangepaste gevoelige informatietypen actueel en van toepassing.</span><span class="sxs-lookup"><span data-stu-id="445dd-122">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="445dd-123">En u kunt classificatie op basis van EDM gebruiken met beleidsregels, zoals beleid voor preventie van gegevensverlies of Microsoft Cloud App Security [bestandsbeleid.](/cloud-app-security/data-protection-policies) [](dlp-learn-about-dlp.md)</span><span class="sxs-lookup"><span data-stu-id="445dd-123">And, you can use EDM-based classification with policies, such as [data loss prevention policies](dlp-learn-about-dlp.md) or [Microsoft Cloud App Security file policies](/cloud-app-security/data-protection-policies).</span></span>

> [!NOTE]
> <span data-ttu-id="445dd-124">Microsoft 365 Information Protection ondersteunt talen voor preview van dubbel-byte-tekensets voor:</span><span class="sxs-lookup"><span data-stu-id="445dd-124">Microsoft 365 Information Protection supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="445dd-125">Vereenvoudigd Chinees</span><span class="sxs-lookup"><span data-stu-id="445dd-125">Chinese (simplified)</span></span>
> - <span data-ttu-id="445dd-126">Traditioneel Chinees</span><span class="sxs-lookup"><span data-stu-id="445dd-126">Chinese (traditional)</span></span>
> - <span data-ttu-id="445dd-127">Koreaks</span><span class="sxs-lookup"><span data-stu-id="445dd-127">Korean</span></span>
> - <span data-ttu-id="445dd-128">Japans</span><span class="sxs-lookup"><span data-stu-id="445dd-128">Japanese</span></span>
> 
> <span data-ttu-id="445dd-129">Deze ondersteuning is beschikbaar voor typen gevoelige informatie.</span><span class="sxs-lookup"><span data-stu-id="445dd-129">This support is available for sensitive information types.</span></span> <span data-ttu-id="445dd-130">Zie [Ondersteuning voor Information Protection voor releaseopmerkingen bij dubbel-bytetekensets (preview)](mip-dbcs-relnotes.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="445dd-130">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>
 

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="445dd-131">Vereiste licenties en machtigingen</span><span class="sxs-lookup"><span data-stu-id="445dd-131">Required licenses and permissions</span></span>

<span data-ttu-id="445dd-132">U moet een globale beheerder, compliancebeheerder of Exchange Online zijn om de taken uit te voeren die in dit artikel worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="445dd-132">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="445dd-133">Zie [Machtigingen](data-loss-prevention-policies.md#permissions) voor meer informatie over DLP-machtigingen.</span><span class="sxs-lookup"><span data-stu-id="445dd-133">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="445dd-134">EDM-gebaseerde classificatie is inbegrepen in deze abonnementen</span><span class="sxs-lookup"><span data-stu-id="445dd-134">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="445dd-135">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="445dd-135">Office 365 E5</span></span>
- <span data-ttu-id="445dd-136">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="445dd-136">Microsoft 365 E5</span></span>
- <span data-ttu-id="445dd-137">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="445dd-137">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="445dd-138">Microsoft E5/A5 Gegevensbeveiliging en -beheer</span><span class="sxs-lookup"><span data-stu-id="445dd-138">Microsoft E5/A5 Information Protection and Governance</span></span>

## <a name="portal-links-for-your-subscription"></a><span data-ttu-id="445dd-139">Portalkoppelingen voor uw abonnement</span><span class="sxs-lookup"><span data-stu-id="445dd-139">Portal links for your subscription</span></span>


|<span data-ttu-id="445dd-140">Portal</span><span class="sxs-lookup"><span data-stu-id="445dd-140">Portal</span></span>  |<span data-ttu-id="445dd-141">World Wide/GCC</span><span class="sxs-lookup"><span data-stu-id="445dd-141">World Wide/GCC</span></span>  |<span data-ttu-id="445dd-142">GCC-High</span><span class="sxs-lookup"><span data-stu-id="445dd-142">GCC-High</span></span>  |<span data-ttu-id="445dd-143">DOD</span><span class="sxs-lookup"><span data-stu-id="445dd-143">DOD</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="445dd-144">Office SCC</span><span class="sxs-lookup"><span data-stu-id="445dd-144">Office SCC</span></span>     |  <span data-ttu-id="445dd-145">protection.office.com</span><span class="sxs-lookup"><span data-stu-id="445dd-145">protection.office.com</span></span>       |<span data-ttu-id="445dd-146">scc.office365.us</span><span class="sxs-lookup"><span data-stu-id="445dd-146">scc.office365.us</span></span>         |<span data-ttu-id="445dd-147">scc.protection.apps.mil</span><span class="sxs-lookup"><span data-stu-id="445dd-147">scc.protection.apps.mil</span></span> |
|<span data-ttu-id="445dd-148">Microsoft 365 Beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="445dd-148">Microsoft 365 Security center</span></span>     |<span data-ttu-id="445dd-149">security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="445dd-149">security.microsoft.com</span></span>         |<span data-ttu-id="445dd-150">security.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="445dd-150">security.microsoft.us</span></span>         |<span data-ttu-id="445dd-151">security.apps.mil</span><span class="sxs-lookup"><span data-stu-id="445dd-151">security.apps.mil</span></span>|
|<span data-ttu-id="445dd-152">Microsoft 365 Compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="445dd-152">Microsoft 365 Compliance center</span></span>     |<span data-ttu-id="445dd-153">compliance.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="445dd-153">compliance.microsoft.com</span></span>         |<span data-ttu-id="445dd-154">compliance.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="445dd-154">compliance.microsoft.us</span></span>         |<span data-ttu-id="445dd-155">compliance.apps.mil</span><span class="sxs-lookup"><span data-stu-id="445dd-155">compliance.apps.mil</span></span>|


## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="445dd-156">De werkstroom in één oogopslag</span><span class="sxs-lookup"><span data-stu-id="445dd-156">The work flow at a glance</span></span>

|<span data-ttu-id="445dd-157">Fase</span><span class="sxs-lookup"><span data-stu-id="445dd-157">Phase</span></span>  |<span data-ttu-id="445dd-158">Wat is er nodig</span><span class="sxs-lookup"><span data-stu-id="445dd-158">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="445dd-159">Deel 1: Classificatie op basis van EDM instellen</span><span class="sxs-lookup"><span data-stu-id="445dd-159">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="445dd-160">(Indien nodig)</span><span class="sxs-lookup"><span data-stu-id="445dd-160">(As needed)</span></span><br/><span data-ttu-id="445dd-161">- [Het databaseschema bewerken](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="445dd-161">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="445dd-162">- [Het schema verwijderen](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="445dd-162">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="445dd-163">- Lees de toegang tot de gevoelige gegevens</span><span class="sxs-lookup"><span data-stu-id="445dd-163">- Read access to the sensitive data</span></span><br/><span data-ttu-id="445dd-164">- Databaseschema in XML-indeling (voorbeeld opgegeven)</span><span class="sxs-lookup"><span data-stu-id="445dd-164">- Database schema in XML format (example provided)</span></span><br/><span data-ttu-id="445dd-165">- Regelpakket in XML-indeling (voorbeeld beschikbaar)</span><span class="sxs-lookup"><span data-stu-id="445dd-165">- Rule package in XML format (example provided)</span></span><br/><span data-ttu-id="445dd-166">- Beheerdersmachtigingen voor het beveiligings- & compliancecentrum (met PowerShell)</span><span class="sxs-lookup"><span data-stu-id="445dd-166">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="445dd-167">Deel 2: Hash en upload de gevoelige gegevens</span><span class="sxs-lookup"><span data-stu-id="445dd-167">Part 2: Hash and upload the sensitive data</span></span>](#part-2-hash-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="445dd-168">(Indien nodig)</span><span class="sxs-lookup"><span data-stu-id="445dd-168">(As needed)</span></span><br/>[<span data-ttu-id="445dd-169">De gegevens vernieuwen</span><span class="sxs-lookup"><span data-stu-id="445dd-169">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="445dd-170">- Aangepaste beveiligingsgroep en gebruikersaccount</span><span class="sxs-lookup"><span data-stu-id="445dd-170">- Custom security group and user account</span></span><br/><span data-ttu-id="445dd-171">- Toegang van lokale beheerder tot machine met EDM-Upload Agent</span><span class="sxs-lookup"><span data-stu-id="445dd-171">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="445dd-172">- Lees de toegang tot de gevoelige gegevens</span><span class="sxs-lookup"><span data-stu-id="445dd-172">- Read access to the sensitive data</span></span><br/><span data-ttu-id="445dd-173">- Verwerken en plannen voor het vernieuwen van de gegevens</span><span class="sxs-lookup"><span data-stu-id="445dd-173">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="445dd-174">Deel 3: Classificatie op basis van EDM gebruiken met uw Microsoft-cloudservices</span><span class="sxs-lookup"><span data-stu-id="445dd-174">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="445dd-175">- Microsoft 365 abonnement met DLP</span><span class="sxs-lookup"><span data-stu-id="445dd-175">- Microsoft 365 subscription with DLP</span></span><br/><span data-ttu-id="445dd-176">- Classificatiefunctie op basis van EDM ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="445dd-176">- EDM-based classification feature enabled</span></span> |

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="445dd-177">Deel 1: Classificatie op basis van EDM instellen</span><span class="sxs-lookup"><span data-stu-id="445dd-177">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="445dd-178">Het instellen en configureren van classificatie op basis van EDM houdt in:</span><span class="sxs-lookup"><span data-stu-id="445dd-178">Setting up and configuring EDM-based classification involves:</span></span>

1. [<span data-ttu-id="445dd-179">Gevoelige gegevens opslaan in .csv indeling</span><span class="sxs-lookup"><span data-stu-id="445dd-179">Saving sensitive data in .csv format</span></span>](#save-sensitive-data-in-csv-format)
2. [<span data-ttu-id="445dd-180">Het databaseschema voor gevoelige informatie definiëren</span><span class="sxs-lookup"><span data-stu-id="445dd-180">Define your sensitive information database schema</span></span>](#define-the-schema-for-your-database-of-sensitive-information)
3. [<span data-ttu-id="445dd-181">Een regelpakket maken</span><span class="sxs-lookup"><span data-stu-id="445dd-181">Create a rule package</span></span>](#set-up-a-rule-package)


#### <a name="save-sensitive-data-in-csv-format"></a><span data-ttu-id="445dd-182">Gevoelige gegevens opslaan in .csv indeling</span><span class="sxs-lookup"><span data-stu-id="445dd-182">Save sensitive data in .csv format</span></span>

1. <span data-ttu-id="445dd-183">Identificeer de gevoelige informatie die u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="445dd-183">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="445dd-184">Exporteert de gegevens naar een app, zoals Microsoft Excel, en sla het bestand op in .csv indeling.</span><span class="sxs-lookup"><span data-stu-id="445dd-184">Export the data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="445dd-185">Het gegevensbestand kan een maximum van:</span><span class="sxs-lookup"><span data-stu-id="445dd-185">The data file can include a maximum of:</span></span>
      - <span data-ttu-id="445dd-186">Maximaal 100 miljoen rijen met gevoelige gegevens</span><span class="sxs-lookup"><span data-stu-id="445dd-186">Up to 100 million rows of sensitive data</span></span>
      - <span data-ttu-id="445dd-187">Maximaal 32 kolommen (velden) per gegevensbron</span><span class="sxs-lookup"><span data-stu-id="445dd-187">Up to 32 columns (fields) per data source</span></span>
      - <span data-ttu-id="445dd-188">Maximaal 5 kolommen (velden) gemarkeerd als doorzoekbaar</span><span class="sxs-lookup"><span data-stu-id="445dd-188">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="445dd-189">Structureer de gevoelige gegevens in het .csv zodanig dat de eerste rij de namen bevat van de velden die voor de classificatie op basis van EDM worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="445dd-189">Structure the sensitive data in the .csv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="445dd-190">In uw .csv hebt u mogelijk veldnamen, zoals 'ssn', 'geboortedatum', 'voornaam', 'achternaam'.</span><span class="sxs-lookup"><span data-stu-id="445dd-190">In your .csv file, you might have field names, such as "ssn", "birthdate", "firstname", "lastname".</span></span> <span data-ttu-id="445dd-191">De namen van de kolomkoppen kunnen geen spaties of onderstrepingstekens bevatten.</span><span class="sxs-lookup"><span data-stu-id="445dd-191">The column header names can't include spaces or underscores.</span></span> <span data-ttu-id="445dd-192">Het voorbeeldbestand .csv dat we in dit artikel gebruiken, heeft bijvoorbeeld de naam *PatientRecords.csv* en de kolommen zijn *PatientID,* *MRN,* *LastName,* *FirstName,* *SSN* en meer.</span><span class="sxs-lookup"><span data-stu-id="445dd-192">For example, the sample .csv file that we use in this article is named *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN*, and more.</span></span>

3. <span data-ttu-id="445dd-193">Let op de opmaak van de gevoelige gegevensvelden.</span><span class="sxs-lookup"><span data-stu-id="445dd-193">Pay attention to the format of the sensitive data fields.</span></span> <span data-ttu-id="445dd-194">Met name velden die komma's in hun inhoud kunnen bevatten (bijvoorbeeld een adres met de waarde 'Seattle,WA') worden geparseerd als twee afzonderlijke velden wanneer ze worden geparseerd door het hulpmiddel EDM.</span><span class="sxs-lookup"><span data-stu-id="445dd-194">In particular, fields that may contain commas in their content (e.g. a street address that contains the value "Seattle,WA") would be parsed as two separate fields when parsed by the EDM tool.</span></span> <span data-ttu-id="445dd-195">Om dit te voorkomen, moet u ervoor zorgen dat dergelijke velden worden omgeven door enkele of dubbele aanhalingstekens in de gevoelige gegevenstabel.</span><span class="sxs-lookup"><span data-stu-id="445dd-195">In order to avoid this, you need to ensure such fields are surrounded by single or double quotes in the sensitive data table.</span></span> <span data-ttu-id="445dd-196">Als velden met komma's daarin ook spaties kunnen bevatten, moet u een aangepast type gevoelige informatie maken dat overeenkomt met de bijbehorende opmaak (bijvoorbeeld een tekenreeks met meerdere woorden met komma's en spaties daarin) om ervoor te zorgen dat de tekenreeks correct wordt aangepast wanneer het document wordt gescand.</span><span class="sxs-lookup"><span data-stu-id="445dd-196">If fields with commas in them may also contain spaces, you would need to create a custom Sensitive Information Type that matches the corresponding format (e.g. a multi-word string with commas and spaces in it) to ensure the string is correctly matched when the document is scanned.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="445dd-197">Het schema voor uw database met gevoelige informatie definiëren</span><span class="sxs-lookup"><span data-stu-id="445dd-197">Define the schema for your database of sensitive information</span></span>

<span data-ttu-id="445dd-198">Als u om zakelijke of technische redenen liever geen PowerShell of opdrachtregel gebruikt om uw schema en EDM-patroon (regelpakket) te maken, kunt u de wizard Exacte gegevensmatch en Gevoelige [informatietype](sit-edm-wizard.md) gebruiken om deze te maken.</span><span class="sxs-lookup"><span data-stu-id="445dd-198">If for business or technical reasons, you prefer not to use PowerShell or command line to create your schema and EDM sensitive info type pattern (rule package), you can use the [Exact Data Match Schema and Sensitive Information Type Wizard](sit-edm-wizard.md) to create them.</span></span> <span data-ttu-id="445dd-199">Wanneer u klaar bent met het maken van het schema en het EDM-gevoelige infotypepatroon, gaat u terug naar alle stappen die nodig zijn om uw op EDM gebaseerde gevoelige informatietype beschikbaar te maken voor gebruik.</span><span class="sxs-lookup"><span data-stu-id="445dd-199">When you are done creating the schema and EDM sensitive info type pattern, return to complete all the steps necessary to make your EDM based sensitive information type available for use.</span></span>

> [!NOTE]
> <span data-ttu-id="445dd-200">De wizard voor het schema voor exacte gegevensovereenkomst en het type gevoelige informatie is alleen beschikbaar voor de wereldwijde en GCC-cloud.</span><span class="sxs-lookup"><span data-stu-id="445dd-200">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

1. <span data-ttu-id="445dd-201">Definieer het schema voor de database met gevoelige informatie in XML-indeling (vergelijkbaar met ons voorbeeld hieronder).</span><span class="sxs-lookup"><span data-stu-id="445dd-201">Define the schema for the database of sensitive information in XML format (similar to our example below).</span></span> <span data-ttu-id="445dd-202">Noem dit schemabestand **edm.xml** en configureer het zo dat er voor elke kolom in de database een regel is waarin de syntaxis wordt gebruikt:</span><span class="sxs-lookup"><span data-stu-id="445dd-202">Name this schema file **edm.xml**, and configure it such that for each column in the database, there is a line that uses the syntax:</span></span> 

      <span data-ttu-id="445dd-203">`\<Field name="" searchable=""/\>`.</span><span class="sxs-lookup"><span data-stu-id="445dd-203">`\<Field name="" searchable=""/\>`.</span></span>

      - <span data-ttu-id="445dd-204">Kolomnamen gebruiken voor *veldnaamwaarden.*</span><span class="sxs-lookup"><span data-stu-id="445dd-204">Use column names for *Field name* values.</span></span>
      - <span data-ttu-id="445dd-205">Gebruik *searchable="true"* voor de velden die u wilt doorzoeken tot maximaal 5 velden.</span><span class="sxs-lookup"><span data-stu-id="445dd-205">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="445dd-206">Ten minste één veld moet doorzoekbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="445dd-206">At least one field must be searchable.</span></span>

      <span data-ttu-id="445dd-207">In het volgende XML-bestand wordt bijvoorbeeld het schema voor een patiëntenrecorddatabase gedefinieerd, met vijf velden die als doorzoekbaar zijn opgegeven: *PatientID,* *MRN,* *SSN,* *Telefoon* en *DOB.*</span><span class="sxs-lookup"><span data-stu-id="445dd-207">As an example, the following XML file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

      <span data-ttu-id="445dd-208">(U kunt ons voorbeeld kopiëren, wijzigen en gebruiken.)</span><span class="sxs-lookup"><span data-stu-id="445dd-208">(You can copy, modify, and use our example.)</span></span>

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

##### <a name="configurable-match-using-the-caseinsensitive-and-ignoreddelimiters-fields"></a><span data-ttu-id="445dd-209">Configureerbare overeenkomst met de velden CaseInensitive en ignoredDelimiters</span><span class="sxs-lookup"><span data-stu-id="445dd-209">Configurable match using the caseInsensitive and ignoredDelimiters fields</span></span>

<span data-ttu-id="445dd-210">In het bovenstaande XML-voorbeeld wordt gebruik gemaakt van `caseInsensitive` de velden en de `ignoredDelimiters` velden.</span><span class="sxs-lookup"><span data-stu-id="445dd-210">The above XML sample makes use of the `caseInsensitive` and the `ignoredDelimiters` fields.</span></span> 

<span data-ttu-id="445dd-211">Wanneer u het veld \***caseInsensitive** _ op de waarde van in uw schemadefinitie op neemt, wordt een item niet uitgesloten op basis van `true` caseverschillen voor `PatientID` veld.</span><span class="sxs-lookup"><span data-stu-id="445dd-211">When you include the \***caseInsensitive** _ field set to the value of `true` in your schema definition, EDM will not exclude an item based on case differences for `PatientID` field.</span></span> <span data-ttu-id="445dd-212">Dus EDM ziet, `PatientID` _ *FOO-1234*\* en **fOo-1234** als identiek.</span><span class="sxs-lookup"><span data-stu-id="445dd-212">So EDM will see, `PatientID` _ *FOO-1234*\* and **fOo-1234** as being identical.</span></span>

<span data-ttu-id="445dd-213">Wanneer u het veld \***ignoredDelimiters** _ met ondersteunde tekens op neemt, worden deze tekens genegeerd in `PatientID` de .</span><span class="sxs-lookup"><span data-stu-id="445dd-213">When you include the \***ignoredDelimiters** _ field with supported characters,  EDM will ignore those characters in the `PatientID`.</span></span> <span data-ttu-id="445dd-214">Dus EDM ziet, `PatientID` _ *FOO-1234*\* en `PatientID` **FOO#1234** als identiek.</span><span class="sxs-lookup"><span data-stu-id="445dd-214">So EDM will see, `PatientID` _ *FOO-1234*\* and `PatientID` **FOO#1234** as being identical.</span></span> <span data-ttu-id="445dd-215">De `ignoredDelimiters` vlag ondersteunt alle niet-alfanumerieke tekens. Hier volgen enkele voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="445dd-215">The `ignoredDelimiters` flag supports any non-alphanumeric character, here are some examples:</span></span>
- <span data-ttu-id="445dd-216">\.</span><span class="sxs-lookup"><span data-stu-id="445dd-216">\.</span></span>
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

<span data-ttu-id="445dd-217">The `ignoredDelimiters` vlag ondersteunt het volgende niet:</span><span class="sxs-lookup"><span data-stu-id="445dd-217">The `ignoredDelimiters` flag doesn't support:</span></span>
- <span data-ttu-id="445dd-218">tekens 0-9</span><span class="sxs-lookup"><span data-stu-id="445dd-218">characters 0-9</span></span>
- <span data-ttu-id="445dd-219">A-Z</span><span class="sxs-lookup"><span data-stu-id="445dd-219">A-Z</span></span>
- <span data-ttu-id="445dd-220">a-z</span><span class="sxs-lookup"><span data-stu-id="445dd-220">a-z</span></span>
- \"
- \,

<span data-ttu-id="445dd-221">In dit voorbeeld, waarin beide en worden gebruikt, worden `caseInsensitive` `ignoredDelimiters` **FOO-1234** en **fOo#1234** door EDM als identiek geclassificeerd en wordt het item geclassificeerd als een type gevoelige informatie voor patiëntenrecords.</span><span class="sxs-lookup"><span data-stu-id="445dd-221">In this example, where both `caseInsensitive` and `ignoredDelimiters` are used, EDM would see **FOO-1234** and **fOo#1234** as  identical and classify the item as a patient record sensitive information type.</span></span> 

4. <span data-ttu-id="445dd-222">Verbinding maken met het Beveiligings- en compliancecentrum met behulp van de procedures in [Verbinding maken met Beveiligings- en compliancecentrum van PowerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="445dd-222">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

5. <span data-ttu-id="445dd-223">Als u het databaseschema wilt uploaden, moet u de volgende cmdlets één voor één uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="445dd-223">To upload the database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="445dd-224">U wordt als volgt gevraagd om dit te bevestigen:</span><span class="sxs-lookup"><span data-stu-id="445dd-224">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="445dd-225">Bevestigen</span><span class="sxs-lookup"><span data-stu-id="445dd-225">Confirm</span></span>
      >
      > <span data-ttu-id="445dd-226">Weet u zeker dat u deze actie wilt uitvoeren?</span><span class="sxs-lookup"><span data-stu-id="445dd-226">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="445dd-227">Nieuw EDM-schema voor het gegevensopslag 'patiëntenrecords' wordt geïmporteerd.</span><span class="sxs-lookup"><span data-stu-id="445dd-227">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
      >
      > <span data-ttu-id="445dd-228">\[Y \] Yes A Yes to All N No L No to All \[ \] \[ \] \[ \] \[ ? \] Help (standaard is 'Y'):</span><span class="sxs-lookup"><span data-stu-id="445dd-228">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="445dd-229">Als u wilt dat uw wijzigingen zonder bevestiging plaatsvinden, gebruikt u in stap 5 deze cmdlet: New-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="445dd-229">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="445dd-230">Het kan 10 tot 60 minuten duren voordat het EDMSchema wordt bijgewerkt met toevoegingen.</span><span class="sxs-lookup"><span data-stu-id="445dd-230">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="445dd-231">De update moet worden voltooid voordat u stappen uitvoert die gebruikmaken van de toevoegingen.</span><span class="sxs-lookup"><span data-stu-id="445dd-231">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="set-up-a-rule-package"></a><span data-ttu-id="445dd-232">Een regelpakket instellen</span><span class="sxs-lookup"><span data-stu-id="445dd-232">Set up a rule package</span></span>

1. <span data-ttu-id="445dd-233">Maak een regelpakket in XML-indeling (met Unicode-codering), vergelijkbaar met het volgende voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="445dd-233">Create a rule package in XML format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="445dd-234">(U kunt ons voorbeeld kopiëren, wijzigen en gebruiken.)</span><span class="sxs-lookup"><span data-stu-id="445dd-234">(You can copy, modify, and use our example.)</span></span>

      <span data-ttu-id="445dd-235">Wanneer u uw regelpakket in stelt, moet u de juiste verwijzing naar het .csv en het **edm.xml** maken.</span><span class="sxs-lookup"><span data-stu-id="445dd-235">When you set up your rule package, make sure to correctly reference your .csv file and **edm.xml** file.</span></span> <span data-ttu-id="445dd-236">U kunt ons voorbeeld kopiëren, wijzigen en gebruiken.</span><span class="sxs-lookup"><span data-stu-id="445dd-236">You can copy, modify, and use our example.</span></span> <span data-ttu-id="445dd-237">In deze voorbeeld-xml moeten de volgende velden worden aangepast om het gevoelige type EDM te maken:</span><span class="sxs-lookup"><span data-stu-id="445dd-237">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

      - <span data-ttu-id="445dd-238">**RulePack-id & ExactMatch-id:** Gebruik [Nieuwe GUID](/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) om een GUID te genereren.</span><span class="sxs-lookup"><span data-stu-id="445dd-238">**RulePack id & ExactMatch id**: Use [New-GUID](/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) to generate a GUID.</span></span>

      - <span data-ttu-id="445dd-239">**Gegevensstore:** in dit veld wordt aangegeven dat het opzoekgegevensopslag van EDM moet worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="445dd-239">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="445dd-240">U geeft een gegevensbronnaam op van een geconfigureerd EDM-schema.</span><span class="sxs-lookup"><span data-stu-id="445dd-240">You provide a data source name of a configured EDM Schema.</span></span>

      - <span data-ttu-id="445dd-241">**idMatch:** dit veld wijst naar het primaire element voor EDM.</span><span class="sxs-lookup"><span data-stu-id="445dd-241">**idMatch**: This field points to the primary element for EDM.</span></span>
        - <span data-ttu-id="445dd-242">Overeenkomsten: hiermee geeft u het veld op dat moet worden gebruikt voor exacte opzoekactie.</span><span class="sxs-lookup"><span data-stu-id="445dd-242">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="445dd-243">U geeft een doorzoekbare veldnaam op in EDM-schema voor de DataStore.</span><span class="sxs-lookup"><span data-stu-id="445dd-243">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
        - <span data-ttu-id="445dd-244">Classificatie: Dit veld geeft de gevoelige type overeenkomst aan die EDM-opzoekactie activeert.</span><span class="sxs-lookup"><span data-stu-id="445dd-244">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="445dd-245">U kunt de naam of GUID van een bestaand ingebouwde of aangepaste gevoelige informatietype geven.</span><span class="sxs-lookup"><span data-stu-id="445dd-245">You can provide the Name or GUID of an existing built-in or custom sensitive information type.</span></span> <span data-ttu-id="445dd-246">Elke tekenreeks die overeenkomt met het opgegeven type gevoelige informatie, wordt gehasht en vergeleken met elke vermelding in de tabel met gevoelige informatie.</span><span class="sxs-lookup"><span data-stu-id="445dd-246">Be aware that any string that matches the sensitive information type provided will be hashed and compared to every entry in the sensitive information table.</span></span> <span data-ttu-id="445dd-247">Als u een aangepast type gevoelige informatie gebruikt als het element Classificatie in EDM, vermijdt u het gebruik van een element dat past bij een groot percentage inhoud (zoals 'elk getal' of 'een woord met vijf letters') door ondersteunende trefwoorden toe te voegen of opmaak toe te voegen in de definitie van het aangepaste classificatiegevoelige informatietype.</span><span class="sxs-lookup"><span data-stu-id="445dd-247">In order to avoid causing performance issues, if you use a custom sensitive information type as the Classification element in EDM, avoid using one that will match a large percentage of content (such as "any number" or "any five-letter word") by adding supporting keywords or including formatting in the definition of the custom classification sensitive information type.</span></span> 

      - <span data-ttu-id="445dd-248">**Overeenkomen:** Dit veld wijst naar extra bewijs dat is gevonden in de nabijheid van idMatch.</span><span class="sxs-lookup"><span data-stu-id="445dd-248">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
        - <span data-ttu-id="445dd-249">Overeenkomsten: U geeft een veldnaam op in het EDM-schema voor DataStore.</span><span class="sxs-lookup"><span data-stu-id="445dd-249">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
      - <span data-ttu-id="445dd-250">**Resource:** In deze sectie worden de naam en beschrijving opgegeven voor het gevoelige type in meerdere locales.</span><span class="sxs-lookup"><span data-stu-id="445dd-250">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
        - <span data-ttu-id="445dd-251">idRef: U geeft GUID voor ExactMatch-id.</span><span class="sxs-lookup"><span data-stu-id="445dd-251">idRef: You provide GUID for ExactMatch ID.</span></span>
        - <span data-ttu-id="445dd-252">Naam & beschrijvingen: zo nodig aanpassen.</span><span class="sxs-lookup"><span data-stu-id="445dd-252">Name & descriptions: customize as required.</span></span>

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

2. <span data-ttu-id="445dd-253">Upload het regelpakket door de volgende PowerShell-cmdlets één voor één uit te laten lopen:</span><span class="sxs-lookup"><span data-stu-id="445dd-253">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

<span data-ttu-id="445dd-254">Op dit moment hebt u classificatie op basis van EDM ingesteld.</span><span class="sxs-lookup"><span data-stu-id="445dd-254">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="445dd-255">De volgende stap is om de gevoelige gegevens te hashen en vervolgens de hashes voor indexering te uploaden.</span><span class="sxs-lookup"><span data-stu-id="445dd-255">The next step is to hash the sensitive data, and then upload the hashes for indexing.</span></span>

<span data-ttu-id="445dd-256">In de vorige procedure wordt in ons schema PatientRecords vijf velden gedefinieerd als doorzoekbaar: *PatientID,* *MRN, SSN,* *Telefoon* en *DOB.* </span><span class="sxs-lookup"><span data-stu-id="445dd-256">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="445dd-257">Ons voorbeeldregelpakket bevat deze velden en verwijst naar het databaseschemabestand **(edm.xml),** met één *ExactMatch-item* per doorzoekbaar veld.</span><span class="sxs-lookup"><span data-stu-id="445dd-257">Our example rule package includes those fields and references the database schema file (**edm.xml**), with one *ExactMatch* item per searchable field.</span></span> <span data-ttu-id="445dd-258">Houd rekening met het volgende ExactMatch-item:</span><span class="sxs-lookup"><span data-stu-id="445dd-258">Consider the following ExactMatch item:</span></span>

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

<span data-ttu-id="445dd-259">Houd er in dit voorbeeld rekening mee dat:</span><span class="sxs-lookup"><span data-stu-id="445dd-259">In this example, note that:</span></span>

- <span data-ttu-id="445dd-260">De gegevensStore-naam verwijst naar het .csv bestand dat we eerder hebben gemaakt: **dataStore = "PatientRecords"**.</span><span class="sxs-lookup"><span data-stu-id="445dd-260">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="445dd-261">De idMatch-waarde verwijst naar een doorzoekbaar veld dat wordt weergegeven in het databaseschemabestand: **idMatch matches = "SSN"**.</span><span class="sxs-lookup"><span data-stu-id="445dd-261">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="445dd-262">De classificatiewaarde verwijst naar een bestaand of aangepast type gevoelige informatie: **classificatie = "U.S. Social Security Number (SSN)"**.</span><span class="sxs-lookup"><span data-stu-id="445dd-262">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="445dd-263">(In dit geval gebruiken we het bestaande type gevoelige informatie van het Amerikaanse sociale-zekerheidsnummer.)</span><span class="sxs-lookup"><span data-stu-id="445dd-263">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="445dd-264">Het kan 10 tot 60 minuten duren voordat het EDMSchema wordt bijgewerkt met toevoegingen.</span><span class="sxs-lookup"><span data-stu-id="445dd-264">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="445dd-265">De update moet worden voltooid voordat u stappen uitvoert die gebruikmaken van de toevoegingen.</span><span class="sxs-lookup"><span data-stu-id="445dd-265">The update must complete before you execute steps that use the additions.</span></span>
 
<span data-ttu-id="445dd-266">Nadat u uw regelpakket hebt geïmporteerd met uw EDM-gevoelige gegevenstype en uw gevoelige gegevenstabel hebt geïmporteerd, kunt u het nieuwe type testen met de functie **Test** in de wizard EDM in het compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="445dd-266">After you have imported your rule package with your EDM sensitive info type and have imported your sensitive data table, you can test your newly created type by using the **Test** function in the EDM wizard in the compliance center.</span></span> <span data-ttu-id="445dd-267">Zie [De wizard Exacte gegevensmatchschema en wizard Gevoelige](sit-edm-wizard.md) informatie gebruiken voor instructies over het gebruik van deze functionaliteit.</span><span class="sxs-lookup"><span data-stu-id="445dd-267">See [Use the Exact Data Match Schema and Sensitive Information Type Wizard](sit-edm-wizard.md) for instructions on using this functionality.</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="445dd-268">Het schema voor classificatie op basis van EDM bewerken</span><span class="sxs-lookup"><span data-stu-id="445dd-268">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="445dd-269">Als u wijzigingen wilt  aanbrengen in uwedm.xmlbestand, zoals het wijzigen van de velden die worden gebruikt voor op EDM gebaseerde classificatie, volgt u de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="445dd-269">If you want to make changes to your **edm.xml** file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

> [!TIP]
> <span data-ttu-id="445dd-270">U kunt uw EDM-schema en gegevensbestand wijzigen om te profiteren van **configureerbare overeenkomst.**</span><span class="sxs-lookup"><span data-stu-id="445dd-270">You can change your EDM schema and data file to take advantage of **configurable match**.</span></span> <span data-ttu-id="445dd-271">Wanneer EDM is geconfigureerd, worden caseverschillen en enkele scheidingstekens genegeerd wanneer een item wordt geëvalueerd.</span><span class="sxs-lookup"><span data-stu-id="445dd-271">When configured, EDM will ignore case differences and some delimiters when it evaluates an item.</span></span> <span data-ttu-id="445dd-272">Dit maakt het definiëren van uw xml-schema en uw gevoelige gegevensbestanden eenvoudiger.</span><span class="sxs-lookup"><span data-stu-id="445dd-272">This makes defining your xml schema and your sensitive data files easier.</span></span> <span data-ttu-id="445dd-273">Zie Schema voor exacte gegevensmatch wijzigen om configureerbare overeenkomst te gebruiken voor [meer informatie.](sit-modify-edm-schema-configurable-match.md)</span><span class="sxs-lookup"><span data-stu-id="445dd-273">To learn more see, [Modify Exact Data Match schema to use configurable match](sit-modify-edm-schema-configurable-match.md).</span></span>

1. <span data-ttu-id="445dd-274">Bewerk **uwedm.xml** bestand (dit is het bestand dat wordt besproken in de sectie Het [schema](#define-the-schema-for-your-database-of-sensitive-information) definiëren van dit artikel).</span><span class="sxs-lookup"><span data-stu-id="445dd-274">Edit your **edm.xml** file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="445dd-275">Verbinding maken met het Beveiligings- en compliancecentrum met behulp van de procedures in [Verbinding maken met Beveiligings- en compliancecentrum van PowerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="445dd-275">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

3. <span data-ttu-id="445dd-276">Als u het databaseschema wilt bijwerken, moet u de volgende cmdlets één voor één uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="445dd-276">To update your database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="445dd-277">U wordt als volgt gevraagd om dit te bevestigen:</span><span class="sxs-lookup"><span data-stu-id="445dd-277">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="445dd-278">Bevestigen</span><span class="sxs-lookup"><span data-stu-id="445dd-278">Confirm</span></span>
      >
      > <span data-ttu-id="445dd-279">Weet u zeker dat u deze actie wilt uitvoeren?</span><span class="sxs-lookup"><span data-stu-id="445dd-279">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="445dd-280">EDM-schema voor het gegevensopslag 'patiëntenrecords' wordt bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="445dd-280">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
      >
      > <span data-ttu-id="445dd-281">\[Y \] Yes A Yes to All N No L No to All \[ \] \[ \] \[ \] \[ ? \] Help (standaard is 'Y'):</span><span class="sxs-lookup"><span data-stu-id="445dd-281">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      > <span data-ttu-id="445dd-282">Als u wilt dat uw wijzigingen zonder bevestiging plaatsvinden, gebruikt u in stap 3 in plaats daarvan deze cmdlet: Set-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="445dd-282">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

      > [!NOTE]
      > <span data-ttu-id="445dd-283">Het kan 10 tot 60 minuten duren voordat het EDMSchema wordt bijgewerkt met toevoegingen.</span><span class="sxs-lookup"><span data-stu-id="445dd-283">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="445dd-284">De update moet worden voltooid voordat u stappen uitvoert die gebruikmaken van de toevoegingen.</span><span class="sxs-lookup"><span data-stu-id="445dd-284">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="445dd-285">Het schema voor classificatie op basis van EDM verwijderen</span><span class="sxs-lookup"><span data-stu-id="445dd-285">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="445dd-286">(Indien nodig) Als u het schema wilt verwijderen dat u gebruikt voor op EDM gebaseerde classificatie, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="445dd-286">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="445dd-287">Verbinding maken met het Beveiligings- en compliancecentrum met behulp van de procedures in [Verbinding maken met Beveiligings- en compliancecentrum van PowerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="445dd-287">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="445dd-288">Voer de volgende PowerShell-cmdlets uit en vervang de naam van de gegevensopslag van 'patiëntenrecords' met de cmdlets die u wilt verwijderen:</span><span class="sxs-lookup"><span data-stu-id="445dd-288">Run the following PowerShell cmdlets, substituting the data store name of "patient records" with the one you want to remove:</span></span>

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      <span data-ttu-id="445dd-289">U wordt gevraagd het volgende te bevestigen:</span><span class="sxs-lookup"><span data-stu-id="445dd-289">You will be prompted to confirm:</span></span>

      > <span data-ttu-id="445dd-290">Bevestigen</span><span class="sxs-lookup"><span data-stu-id="445dd-290">Confirm</span></span>
      >
      > <span data-ttu-id="445dd-291">Weet u zeker dat u deze actie wilt uitvoeren?</span><span class="sxs-lookup"><span data-stu-id="445dd-291">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="445dd-292">EDM-schema voor het gegevensopslag 'patiëntenrecords' wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="445dd-292">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
      >
      > <span data-ttu-id="445dd-293">\[Y \] Yes A Yes to All N No L No to All \[ \] \[ \] \[ \] \[ ? \] Help (standaard is 'Y'):</span><span class="sxs-lookup"><span data-stu-id="445dd-293">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      >  <span data-ttu-id="445dd-294">Als u wilt dat uw wijzigingen zonder bevestiging plaatsvinden, gebruikt u in stap 2 deze cmdlet: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span><span class="sxs-lookup"><span data-stu-id="445dd-294">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>

### <a name="part-2-hash-and-upload-the-sensitive-data"></a><span data-ttu-id="445dd-295">Deel 2: Hash en upload de gevoelige gegevens</span><span class="sxs-lookup"><span data-stu-id="445dd-295">Part 2: Hash and upload the sensitive data</span></span>

<span data-ttu-id="445dd-296">In deze fase stelt u een aangepaste beveiligingsgroep en gebruikersaccount in en stelt u het hulpprogramma EDM Upload Agent in.</span><span class="sxs-lookup"><span data-stu-id="445dd-296">In this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="445dd-297">Vervolgens gebruikt u het hulpprogramma om de gevoelige gegevens te hashen met een zoutwaarde en deze te uploaden.</span><span class="sxs-lookup"><span data-stu-id="445dd-297">Then, you use the tool to hash with salt value the sensitive data, and upload it.</span></span>

<span data-ttu-id="445dd-298">Het hashen en uploaden kan worden uitgevoerd met één computer of u kunt de stap voor hashing scheiden van de uploadstap voor meer beveiliging.</span><span class="sxs-lookup"><span data-stu-id="445dd-298">The hashing and uploading can be done using one computer or you can separate the hashing step from the upload step for greater security.</span></span>

<span data-ttu-id="445dd-299">Als u wilt hashen en uploaden vanaf één computer, moet u dit doen vanaf een computer die rechtstreeks verbinding kan maken met uw Microsoft 365 tenant.</span><span class="sxs-lookup"><span data-stu-id="445dd-299">If you want to hash and upload from one computer, you need to do it from a computer that can directly connect to your Microsoft 365 tenant.</span></span> <span data-ttu-id="445dd-300">Hiervoor moeten uw duidelijke tekstgevoelige gegevensbestanden op die computer staan voor hashing.</span><span class="sxs-lookup"><span data-stu-id="445dd-300">This requires that your clear text sensitive data files are on that computer for hashing.</span></span>

<span data-ttu-id="445dd-301">Als u het gevoelige gegevensbestand met duidelijke tekst niet wilt onthullen, kunt u het hashen op een computer op een veilige locatie en vervolgens het hashbestand en het zoutbestand kopiëren naar een computer die rechtstreeks verbinding kan maken met uw Microsoft 365-tenant voor uploaden.</span><span class="sxs-lookup"><span data-stu-id="445dd-301">If you do not want to expose your clear text sensitive data file, you can hash it on a computer in a secure location and then copy the hash file and the salt file to a computer that can directly connect to your Microsoft 365 tenant for upload.</span></span> <span data-ttu-id="445dd-302">In dit scenario hebt u de EDMUploadAgent op beide computers nodig.</span><span class="sxs-lookup"><span data-stu-id="445dd-302">In this scenario, you will need the EDMUploadAgent on both computers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="445dd-303">Als u de wizard Exacte gegevensmatch en de wizard Gevoelige gegevenstype hebt gebruikt om uw schema- en patroonbestanden te maken, moet u ***het*** schema voor deze procedure downloaden.</span><span class="sxs-lookup"><span data-stu-id="445dd-303">If you used the Exact Data Match schema and sensitive information type wizard to create your schema and pattern files, you ***must*** download the schema for this procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="445dd-304">Als uw organisatie Klantsleutel heeft ingesteld voor Microsoft 365 op [tenantniveau,](customer-key-overview.md)wordt de versleutelingsfunctionaliteit van Exact data match automatisch gebruikt.</span><span class="sxs-lookup"><span data-stu-id="445dd-304">If your organization has set up [Customer Key for Microsoft 365 at the tenant level](customer-key-overview.md), Exact data match will make use of its encryption functionality automatically.</span></span> <span data-ttu-id="445dd-305">Dit is alleen beschikbaar voor E5-gelicentieerde tenants in de commerciële cloud.</span><span class="sxs-lookup"><span data-stu-id="445dd-305">This is available only to E5 licensed tenants in the Commercial cloud.</span></span>

#### <a name="prerequisites"></a><span data-ttu-id="445dd-306">Vereisten</span><span class="sxs-lookup"><span data-stu-id="445dd-306">Prerequisites</span></span>

- <span data-ttu-id="445dd-307">een werk- of schoolaccount voor Microsoft 365 dat wordt toegevoegd aan de **beveiligingsgroep EDM \_ DataUploaders**</span><span class="sxs-lookup"><span data-stu-id="445dd-307">a work or school account for Microsoft 365  that will be added to the **EDM\_DataUploaders** security group</span></span>
- <span data-ttu-id="445dd-308">een Windows 10 of Windows Server 2016 met .NET versie 4.6.2 voor het uitvoeren van de EDMUploadAgent</span><span class="sxs-lookup"><span data-stu-id="445dd-308">a Windows 10 or Windows Server 2016 machine with .NET version 4.6.2 for running the EDMUploadAgent</span></span>
- <span data-ttu-id="445dd-309">een adreslijst op uw uploadmachine voor het volgende:</span><span class="sxs-lookup"><span data-stu-id="445dd-309">a directory on your upload machine for the:</span></span>
    -  <span data-ttu-id="445dd-310">EDMUploadAgent</span><span class="sxs-lookup"><span data-stu-id="445dd-310">EDMUploadAgent</span></span>
    - <span data-ttu-id="445dd-311">uw gevoelige itembestand in csv-indeling **PatientRecords.csv** in onze voorbeelden</span><span class="sxs-lookup"><span data-stu-id="445dd-311">your sensitive item file in csv format **PatientRecords.csv** in our examples</span></span>
    -  <span data-ttu-id="445dd-312">en de uitvoerhash- en zoutbestanden</span><span class="sxs-lookup"><span data-stu-id="445dd-312">and the output hash and salt files</span></span>
    - <span data-ttu-id="445dd-313">de gegevensstorenaam uit **hetedm.xml** bestand, voor dit voorbeeld de naam `PatientRecords`</span><span class="sxs-lookup"><span data-stu-id="445dd-313">the datastore name from the **edm.xml** file, for this example its `PatientRecords`</span></span>
- <span data-ttu-id="445dd-314">Als u de wizard Exacte gegevensmatch en de wizard [Gevoelige gegevenstype hebt gebruikt,](sit-edm-wizard.md) ***moet u het*** downloaden</span><span class="sxs-lookup"><span data-stu-id="445dd-314">If you used the [Exact Data Match schema and sensitive information type wizard](sit-edm-wizard.md) you ***must*** download it</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="445dd-315">De beveiligingsgroep en het gebruikersaccount instellen</span><span class="sxs-lookup"><span data-stu-id="445dd-315">Set up the security group and user account</span></span>

1. <span data-ttu-id="445dd-316">Als globale beheerder gaat u naar het beheercentrum met de juiste [koppeling](#portal-links-for-your-subscription) voor uw abonnement en maakt u een [beveiligingsgroep](/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) met de naam **EDM \_ DataUploaders.**</span><span class="sxs-lookup"><span data-stu-id="445dd-316">As a global administrator, go to the admin center using the appropriate [link for your subscription](#portal-links-for-your-subscription) and [create a security group](/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called **EDM\_DataUploaders**.</span></span>

2. <span data-ttu-id="445dd-317">Voeg een of meer gebruikers toe aan de **beveiligingsgroep EDM \_ DataUploaders.**</span><span class="sxs-lookup"><span data-stu-id="445dd-317">Add one or more users to the **EDM\_DataUploaders** security group.</span></span> <span data-ttu-id="445dd-318">(Deze gebruikers beheren de database met gevoelige informatie.)</span><span class="sxs-lookup"><span data-stu-id="445dd-318">(These users will manage the database of sensitive information.)</span></span>

#### <a name="hash-and-upload-from-one-computer"></a><span data-ttu-id="445dd-319">Hash en upload vanaf één computer</span><span class="sxs-lookup"><span data-stu-id="445dd-319">Hash and upload from one computer</span></span>

<span data-ttu-id="445dd-320">Deze computer moet directe toegang hebben tot uw Microsoft 365 tenant.</span><span class="sxs-lookup"><span data-stu-id="445dd-320">This computer must have direct access to your Microsoft 365 tenant.</span></span>

>[!NOTE]
> <span data-ttu-id="445dd-321">Voordat u deze procedure start, moet u ervoor zorgen dat u lid bent van de **beveiligingsgroep EDM \_ DataUploaders.**</span><span class="sxs-lookup"><span data-stu-id="445dd-321">Before you begin this procedure, make sure that you are a member of the **EDM\_DataUploaders** security group.</span></span>

> [!TIP]
> <span data-ttu-id="445dd-322">U kunt eventueel een validatie uitvoeren voor het CSV-bestand voordat u het uploadt. Voer het volgende uit:</span><span class="sxs-lookup"><span data-stu-id="445dd-322">Optionally, you can run a validation against your csv file before uploading by running:</span></span>
>
>`EdmUploadAgent.exe /ValidateData /DataFile [data file] /Schema [schema file]`
>
><span data-ttu-id="445dd-323">Voor meer informatie over alle EdmUploadAgent.exe >ondersteunde parameters uitvoeren</span><span class="sxs-lookup"><span data-stu-id="445dd-323">For more information on all the EdmUploadAgent.exe >supported parameters run</span></span>
>
> `EdmUploadAgent.exe /?`


#### <a name="links-to-edm-upload-agent-by-subscription-type"></a><span data-ttu-id="445dd-324">Koppelingen naar EDM-uploadagent per abonnementstype</span><span class="sxs-lookup"><span data-stu-id="445dd-324">Links to EDM upload agent by subscription type</span></span>

- <span data-ttu-id="445dd-325">[Commercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - de meeste commerciële klanten moeten dit gebruiken</span><span class="sxs-lookup"><span data-stu-id="445dd-325">[Commercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - most commercial customers should use this</span></span>
- <span data-ttu-id="445dd-326">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - Dit is specifiek voor abonnees van de cloud van de overheid met hoge beveiliging</span><span class="sxs-lookup"><span data-stu-id="445dd-326">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - This is specifically for high security government cloud subscribers</span></span>
- <span data-ttu-id="445dd-327">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - dit is specifiek voor klanten van de cloud van het Department of Defense van de Verenigde Staten</span><span class="sxs-lookup"><span data-stu-id="445dd-327">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - this is specifically for United States Department of Defense cloud customers</span></span>

1. <span data-ttu-id="445dd-328">Maak een werkmap voor de EDMUploadAgent.</span><span class="sxs-lookup"><span data-stu-id="445dd-328">Create a working directory for the EDMUploadAgent.</span></span> <span data-ttu-id="445dd-329">Bijvoorbeeld **C:\EDM\Data.**</span><span class="sxs-lookup"><span data-stu-id="445dd-329">For example, **C:\EDM\Data**.</span></span> <span data-ttu-id="445dd-330">Plaats het **PatientRecords.csv** daar.</span><span class="sxs-lookup"><span data-stu-id="445dd-330">Place the **PatientRecords.csv** file there.</span></span>

2. <span data-ttu-id="445dd-331">Download en installeer de juiste [EDM-Upload agent](#links-to-edm-upload-agent-by-subscription-type) voor uw abonnement in de adreslijst die u in stap 1 hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="445dd-331">Download and install the appropriate [EDM Upload Agent](#links-to-edm-upload-agent-by-subscription-type) for your subscription into the directory you created in step 1.</span></span>

   > [!NOTE]
   > <span data-ttu-id="445dd-332">De EDMUploadAgent op de bovenstaande koppelingen is bijgewerkt om automatisch een zoute waarde toe te voegen aan de gehashte gegevens.</span><span class="sxs-lookup"><span data-stu-id="445dd-332">The EDMUploadAgent at the above links has been updated to automatically add a salt value to the hashed data.</span></span> <span data-ttu-id="445dd-333">U kunt ook uw eigen zoutwaarde leveren.</span><span class="sxs-lookup"><span data-stu-id="445dd-333">Alternately, you can provide your own salt value.</span></span> <span data-ttu-id="445dd-334">Wanneer u deze versie hebt gebruikt, kunt u de vorige versie van de EDMUploadAgent niet meer gebruiken.</span><span class="sxs-lookup"><span data-stu-id="445dd-334">Once you have used this version, you will not be able to use the previous version of the EDMUploadAgent.</span></span>
   >
   > <span data-ttu-id="445dd-335">U kunt gegevens met de EDMUploadAgent slechts twee keer per dag uploaden naar een bepaalde gegevensopslag.</span><span class="sxs-lookup"><span data-stu-id="445dd-335">You can upload data with the EDMUploadAgent to any given data store only twice per day.</span></span>

   > [!TIP]
   > <span data-ttu-id="445dd-336">Als u een lijst wilt halen uit de ondersteunde opdrachtparameters, moet u de agent geen argumenten geven.</span><span class="sxs-lookup"><span data-stu-id="445dd-336">To a get a list out of the supported command parameters, run the agent no arguments.</span></span> <span data-ttu-id="445dd-337">Bijvoorbeeld 'EdmUploadAgent.exe'.</span><span class="sxs-lookup"><span data-stu-id="445dd-337">For example 'EdmUploadAgent.exe'.</span></span>

2. <span data-ttu-id="445dd-338">Machtig de EDM-Upload agent, open het venster Opdrachtprompt (als beheerder), schakel over naar de **adreslijst C:\EDM\Data** en voer vervolgens de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="445dd-338">Authorize the EDM Upload Agent, open  Command Prompt window (as an administrator), switch to the **C:\EDM\Data** directory and then run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="445dd-339">Meld u aan met uw werk- of schoolaccount voor Microsoft 365 die is toegevoegd aan de EDM_DataUploaders beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="445dd-339">Sign in with your work or school account for Microsoft 365 that was added to the EDM_DataUploaders security group.</span></span> <span data-ttu-id="445dd-340">Uw tenantgegevens worden uit het gebruikersaccount gehaald om de verbinding te maken.</span><span class="sxs-lookup"><span data-stu-id="445dd-340">Your tenant information is extracted from the user account to make the connection.</span></span>

   <span data-ttu-id="445dd-341">OPTIONEEL: Als u de wizard Exacte gegevensmatch en de wizard Gevoelige gegevenstype hebt gebruikt om uw schema- en patroonbestanden te maken, voer dan de volgende opdracht uit in een opdrachtpromptvenster:</span><span class="sxs-lookup"><span data-stu-id="445dd-341">OPTIONAL: If you used the Exact Data Match schema and sensitive information type wizard to create your schema and pattern files, run the following command in a Command Prompt window:</span></span>

   `EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>`

4. <span data-ttu-id="445dd-342">Als u de gevoelige gegevens wilt hashen en uploaden, voer u de volgende opdracht uit in het venster Opdrachtprompt:</span><span class="sxs-lookup"><span data-stu-id="445dd-342">To hash and upload the sensitive data, run the following command in Command Prompt window:</span></span>

   `EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file]`

   <span data-ttu-id="445dd-343">Voorbeeld: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span><span class="sxs-lookup"><span data-stu-id="445dd-343">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span></span>

   <span data-ttu-id="445dd-344">Hierdoor wordt automatisch een willekeurig gegenereerde zoutwaarde aan de hash opgewaardeerd voor meer beveiliging.</span><span class="sxs-lookup"><span data-stu-id="445dd-344">This will automatically add a randomly generated salt value to the hash for greater security.</span></span> <span data-ttu-id="445dd-345">Als u desgewenst uw eigen zoutwaarde wilt gebruiken, voegt u de **/Salt <saltvalue>** toe aan de opdracht.</span><span class="sxs-lookup"><span data-stu-id="445dd-345">Optionally, if you want to use your own salt value, add the **/Salt <saltvalue>** to the command.</span></span> <span data-ttu-id="445dd-346">Deze waarde moet 64 tekens lang zijn en mag alleen de a-z-tekens en 0-9 tekens bevatten.</span><span class="sxs-lookup"><span data-stu-id="445dd-346">This value must be 64 characters in length and can only contain the a-z characters and 0-9 characters.</span></span>

5. <span data-ttu-id="445dd-347">Controleer de uploadstatus door deze opdracht uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="445dd-347">Check the upload status by running this command:</span></span>

   `EdmUploadAgent.exe /GetSession /DataStoreName \<DataStoreName\>`

   <span data-ttu-id="445dd-348">Voorbeeld: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span><span class="sxs-lookup"><span data-stu-id="445dd-348">Example: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span></span>

   <span data-ttu-id="445dd-349">Zoek naar de status in **ProcessingInProgress.**</span><span class="sxs-lookup"><span data-stu-id="445dd-349">Look for the status to be in **ProcessingInProgress**.</span></span> <span data-ttu-id="445dd-350">Controleer opnieuw om de paar minuten totdat de status wordt gewijzigd in **Voltooid.**</span><span class="sxs-lookup"><span data-stu-id="445dd-350">Check again every few minutes until the status changes to **Completed**.</span></span> <span data-ttu-id="445dd-351">Wanneer de status is voltooid, zijn uw EDM-gegevens klaar voor gebruik.</span><span class="sxs-lookup"><span data-stu-id="445dd-351">Once the status is completed, your EDM data is ready for use.</span></span>

#### <a name="separate-hash-and-upload"></a><span data-ttu-id="445dd-352">Hash scheiden en uploaden</span><span class="sxs-lookup"><span data-stu-id="445dd-352">Separate Hash and upload</span></span>

<span data-ttu-id="445dd-353">Voer de hash uit op een computer in een veilige omgeving.</span><span class="sxs-lookup"><span data-stu-id="445dd-353">Perform the hash on a computer in a secure environment.</span></span>

<span data-ttu-id="445dd-354">OPTIONEEL: Als u de wizard Exacte gegevensmatch en de wizard Gevoelige gegevenstype hebt gebruikt om uw schema- en patroonbestanden te maken, voer dan de volgende opdracht uit in een opdrachtpromptvenster:</span><span class="sxs-lookup"><span data-stu-id="445dd-354">OPTIONAL: If you used the Exact Data Match schema and sensitive information type wizard to create your schema and pattern files, run the following command in a Command Prompt window:</span></span>

`EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>`

1. <span data-ttu-id="445dd-355">Voer de volgende opdracht uit in opdrachtpromptvensters:</span><span class="sxs-lookup"><span data-stu-id="445dd-355">Run the following command in Command Prompt windows:</span></span>

   `EdmUploadAgent.exe /CreateHash /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file] >`

   <span data-ttu-id="445dd-356">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="445dd-356">For example:</span></span>

   > <span data-ttu-id="445dd-357">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span><span class="sxs-lookup"><span data-stu-id="445dd-357">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span></span>

   <span data-ttu-id="445dd-358">Hiermee worden een gehasht bestand en een zoutbestand met deze extensies uitgevoerd als u de optie **/Zout <saltvalue>** niet hebt opgegeven:</span><span class="sxs-lookup"><span data-stu-id="445dd-358">This will output a hashed file and a salt file with these extensions if you didn't specify the **/Salt <saltvalue>** option:</span></span>
   - <span data-ttu-id="445dd-359">. EdmHash</span><span class="sxs-lookup"><span data-stu-id="445dd-359">.EdmHash</span></span>
   - <span data-ttu-id="445dd-360">. EdmSalt</span><span class="sxs-lookup"><span data-stu-id="445dd-360">.EdmSalt</span></span>

2. <span data-ttu-id="445dd-361">Kopieer deze bestanden op een veilige manier naar de computer die u gebruikt om uw csv-bestand met gevoelige items (PatientRecords) te uploaden naar uw tenant.</span><span class="sxs-lookup"><span data-stu-id="445dd-361">Copy these files in a secure fashion to the computer you will use to upload your sensitive items csv file (PatientRecords) to your tenant.</span></span>

   <span data-ttu-id="445dd-362">Als u de gehashte gegevens wilt uploaden, moet u de volgende opdracht uitvoeren in Windows opdrachtprompt:</span><span class="sxs-lookup"><span data-stu-id="445dd-362">To upload the hashed data, run the following command in Windows Command Prompt:</span></span>

   `EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

   <span data-ttu-id="445dd-363">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="445dd-363">For example:</span></span>

   > <span data-ttu-id="445dd-364">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C: \\ Edm \\ Hash \\ PatientRecords.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="445dd-364">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span></span>


   <span data-ttu-id="445dd-365">Voer de volgende opdracht uit in het venster Opdrachtprompt om te controleren of uw gevoelige gegevens zijn geüpload:</span><span class="sxs-lookup"><span data-stu-id="445dd-365">To verify that your sensitive data has been uploaded, run the following command in Command Prompt window:</span></span>

   `EdmUploadAgent.exe /GetDataStore`

   <span data-ttu-id="445dd-366">U ziet een lijst met gegevensopslag en wanneer deze voor het laatst zijn bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="445dd-366">You'll see a list of data stores and when they were last updated.</span></span>

   <span data-ttu-id="445dd-367">Als u alle gegevens uploads naar een bepaalde winkel wilt zien, voer dan de volgende opdracht uit in Windows opdrachtprompt:</span><span class="sxs-lookup"><span data-stu-id="445dd-367">If you want to see all the data uploads to a particular store, run the following command in a Windows command prompt:</span></span>

   `EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>`

   <span data-ttu-id="445dd-368">Ga verder met het instellen van uw proces en planning voor [het vernieuwen van de database met gevoelige informatie.](#refreshing-your-sensitive-information-database)</span><span class="sxs-lookup"><span data-stu-id="445dd-368">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="445dd-369">Op dit moment kunt u de classificatie op basis van EDM gebruiken met uw Microsoft-cloudservices.</span><span class="sxs-lookup"><span data-stu-id="445dd-369">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="445dd-370">U kunt bijvoorbeeld een [DLP-beleid instellen met EDM-classificatie.](#to-create-a-dlp-policy-with-edm)</span><span class="sxs-lookup"><span data-stu-id="445dd-370">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="445dd-371">Uw database met gevoelige informatie vernieuwen</span><span class="sxs-lookup"><span data-stu-id="445dd-371">Refreshing your sensitive information database</span></span>

<span data-ttu-id="445dd-372">U kunt de database met gevoelige gegevens dagelijks vernieuwen en met het EDM-Upload kunt u de gevoelige gegevens opnieuw indexeren en vervolgens de geïndexeerde gegevens opnieuw uploaden.</span><span class="sxs-lookup"><span data-stu-id="445dd-372">You can refresh your sensitive information database daily, and the EDM Upload Tool can reindex the sensitive data and then reupload the indexed data.</span></span>

1. <span data-ttu-id="445dd-373">Bepaal uw proces en frequentie (dagelijks of wekelijks) voor het vernieuwen van de database met gevoelige informatie.</span><span class="sxs-lookup"><span data-stu-id="445dd-373">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="445dd-374">Export de gevoelige gegevens opnieuw naar een app, zoals Microsoft Excel, en sla het bestand op in .csv indeling.</span><span class="sxs-lookup"><span data-stu-id="445dd-374">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="445dd-375">Bewaar dezelfde bestandsnaam en locatie die u hebt gebruikt toen u de stappen in Hash hebt gevolgd [en de gevoelige gegevens uploadt.](#part-2-hash-and-upload-the-sensitive-data)</span><span class="sxs-lookup"><span data-stu-id="445dd-375">Keep the same file name and location you used when you followed the steps described in [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data).</span></span>

      > [!NOTE]
      > <span data-ttu-id="445dd-376">Als er geen wijzigingen zijn aangebracht in de structuur (veldnamen) van het .csv-bestand, hoeft u geen wijzigingen aan te brengen in het databaseschemabestand wanneer u de gegevens vernieuwt.</span><span class="sxs-lookup"><span data-stu-id="445dd-376">If there are no changes to the structure (field names) of the .csv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="445dd-377">Maar als u wijzigingen moet aanbrengen, moet u het databaseschema en het regelpakket dienovereenkomstig bewerken.</span><span class="sxs-lookup"><span data-stu-id="445dd-377">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="445dd-378">Gebruik [Taakplanning om stap](/windows/desktop/TaskSchd/task-scheduler-start-page) 2 en 3 in de hash te automatiseren en de gevoelige [gegevensprocedure te](#part-2-hash-and-upload-the-sensitive-data) uploaden.</span><span class="sxs-lookup"><span data-stu-id="445dd-378">Use [Task Scheduler](/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="445dd-379">U kunt taken op verschillende manieren plannen:</span><span class="sxs-lookup"><span data-stu-id="445dd-379">You can schedule tasks using several methods:</span></span>

      | <span data-ttu-id="445dd-380">Methode</span><span class="sxs-lookup"><span data-stu-id="445dd-380">Method</span></span>             | <span data-ttu-id="445dd-381">Wat moet u doen?</span><span class="sxs-lookup"><span data-stu-id="445dd-381">What to do</span></span> |
      | ---------------------- | ---------------- |
      | <span data-ttu-id="445dd-382">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="445dd-382">Windows PowerShell</span></span>     | <span data-ttu-id="445dd-383">Zie de [documentatie van ScheduledTasks](/powershell/module/scheduledtasks/?view=win10-ps) en het [voorbeeld van PowerShell-script](#example-powershell-script-for-task-scheduler) in dit artikel</span><span class="sxs-lookup"><span data-stu-id="445dd-383">See the [ScheduledTasks](/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span> |
      | <span data-ttu-id="445dd-384">Task Scheduler API</span><span class="sxs-lookup"><span data-stu-id="445dd-384">Task Scheduler API</span></span>     | <span data-ttu-id="445dd-385">Zie de [documentatie van Taakplanning](/windows/desktop/TaskSchd/using-the-task-scheduler)</span><span class="sxs-lookup"><span data-stu-id="445dd-385">See the [Task Scheduler](/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>                                                                                                                                                                                                                                                                                |
      | <span data-ttu-id="445dd-386">Windows gebruikersinterface</span><span class="sxs-lookup"><span data-stu-id="445dd-386">Windows user interface</span></span> | <span data-ttu-id="445dd-387">Klik Windows op **Start** en typ Taakplanning.</span><span class="sxs-lookup"><span data-stu-id="445dd-387">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="445dd-388">Klik vervolgens in de lijst met resultaten met de rechtermuisknop op **Taakplanning** en kies **Uitvoeren als beheerder.**</span><span class="sxs-lookup"><span data-stu-id="445dd-388">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="445dd-389">Voorbeeld van PowerShell-script voor taakplanning</span><span class="sxs-lookup"><span data-stu-id="445dd-389">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="445dd-390">Deze sectie bevat een voorbeeld van PowerShell-script dat u kunt gebruiken om uw taken te plannen voor het hashen van gegevens en het uploaden van de gehashte gegevens:</span><span class="sxs-lookup"><span data-stu-id="445dd-390">This section includes an example PowerShell script you can use to schedule your tasks for hashing data and uploading the hashed data:</span></span>

##### <a name="to-schedule-hashing-and-upload-in-a-combined-step"></a><span data-ttu-id="445dd-391">Hashing plannen en uploaden in een gecombineerde stap</span><span class="sxs-lookup"><span data-stu-id="445dd-391">To schedule hashing and upload in a combined step</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$schemaext = '.xml'
\# Assuming CSV file name is same as data store name
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

#### <a name="to-schedule-hashing-and-upload-as-separate-steps"></a><span data-ttu-id="445dd-392">Hashing plannen en uploaden als afzonderlijke stappen</span><span class="sxs-lookup"><span data-stu-id="445dd-392">To schedule hashing and upload as separate steps</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$edmext = '.EdmHash'
$schemaext = '.xml'
\# Assuming CSV file name is same as data store name
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

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="445dd-393">Deel 3: Classificatie op basis van EDM gebruiken met uw Microsoft-cloudservices</span><span class="sxs-lookup"><span data-stu-id="445dd-393">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="445dd-394">Deze locaties ondersteunen EDM-gevoelige informatietypen:</span><span class="sxs-lookup"><span data-stu-id="445dd-394">These locations are support EDM sensitive information types:</span></span>

- <span data-ttu-id="445dd-395">DLP voor Exchange Online (e-mail)</span><span class="sxs-lookup"><span data-stu-id="445dd-395">DLP for Exchange Online (email)</span></span>
- <span data-ttu-id="445dd-396">OneDrive voor Bedrijven (bestanden)</span><span class="sxs-lookup"><span data-stu-id="445dd-396">OneDrive for Business (files)</span></span>
- <span data-ttu-id="445dd-397">Microsoft Teams (gesprekken)</span><span class="sxs-lookup"><span data-stu-id="445dd-397">Microsoft Teams (conversations)</span></span>
- <span data-ttu-id="445dd-398">DLP voor SharePoint (bestanden)</span><span class="sxs-lookup"><span data-stu-id="445dd-398">DLP for SharePoint (files)</span></span>
- <span data-ttu-id="445dd-399">Microsoft Cloud App Security DLP-beleid</span><span class="sxs-lookup"><span data-stu-id="445dd-399">Microsoft Cloud App Security DLP policies</span></span>
- <span data-ttu-id="445dd-400">Beleid voor automatisch labelen op de server - beschikbaar voor commerciële cloudklanten</span><span class="sxs-lookup"><span data-stu-id="445dd-400">Server-side auto-labeling policies - available for commercial cloud customers</span></span> <!--, UNCOMMENT THIS ON 6/15 and government cloud customers-->

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="445dd-401">Een DLP-beleid maken met EDM</span><span class="sxs-lookup"><span data-stu-id="445dd-401">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="445dd-402">Ga naar het Beveiligings- & compliancecentrum met de juiste [koppeling voor uw abonnement.](#portal-links-for-your-subscription)</span><span class="sxs-lookup"><span data-stu-id="445dd-402">Go to the Security & Compliance Center using the appropriate [link for your subscription](#portal-links-for-your-subscription).</span></span>

2. <span data-ttu-id="445dd-403">Kies **Beleid voor preventie van** \> **gegevensverlies.**</span><span class="sxs-lookup"><span data-stu-id="445dd-403">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="445dd-404">Kies **Een beleid aangepaste** \> **volgende** \> **maken.**</span><span class="sxs-lookup"><span data-stu-id="445dd-404">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="445dd-405">Geef op **het tabblad Naam** uw beleid een naam en beschrijving op en kies **volgende**.</span><span class="sxs-lookup"><span data-stu-id="445dd-405">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="445dd-406">Selecteer op **het tabblad** Locaties kiezen de optie Laat mij specifieke **locaties kiezen** en kies vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="445dd-406">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="445dd-407">Selecteer in **de kolom** Status **Exchange e-mail, OneDrive accounts, Teams chat-** en kanaalbericht en kies vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="445dd-407">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message**, and then choose **Next**.</span></span>

7. <span data-ttu-id="445dd-408">Kies op **het tabblad** Beleidsinstellingen de optie Geavanceerde **instellingen gebruiken** en kies vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="445dd-408">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="445dd-409">Kies **+ Nieuwe regel**.</span><span class="sxs-lookup"><span data-stu-id="445dd-409">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="445dd-410">Geef in **de** sectie Naam een naam en beschrijving op voor de regel.</span><span class="sxs-lookup"><span data-stu-id="445dd-410">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="445dd-411">Kies in **de sectie** Voorwaarden in de lijst + **Een voorwaarde** toevoegen de optie Inhoud bevat **gevoelig type.**</span><span class="sxs-lookup"><span data-stu-id="445dd-411">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span>

      ![Inhoud bevat gevoelige informatietypen](../media/edm-dlp-newrule-conditions.png)

11. <span data-ttu-id="445dd-413">Zoek naar het gevoelige informatietype dat u hebt gemaakt bij het instellen van het regelpakket en kies **vervolgens + Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="445dd-413">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>  
    <span data-ttu-id="445dd-414">Kies vervolgens **Klaar**.</span><span class="sxs-lookup"><span data-stu-id="445dd-414">Then choose **Done**.</span></span>

12. <span data-ttu-id="445dd-415">Selecteer de opties voor uw regel, zoals Gebruikersmeldingen, Gebruiker **overschrijven,** **Incidentrapporten,** en kies **vervolgens Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="445dd-415">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="445dd-416">Controleer op **het tabblad** Beleidsinstellingen uw regels en kies **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="445dd-416">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="445dd-417">Geef op of u het beleid meteen wilt in- of uitschakelen, of uitgeschakeld wilt houden.</span><span class="sxs-lookup"><span data-stu-id="445dd-417">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="445dd-418">Kies vervolgens **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="445dd-418">Then choose **Next**.</span></span>

15. <span data-ttu-id="445dd-419">Controleer uw **beleid op het** tabblad Uw instellingen controleren.</span><span class="sxs-lookup"><span data-stu-id="445dd-419">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="445dd-420">Breng de benodigde wijzigingen aan.</span><span class="sxs-lookup"><span data-stu-id="445dd-420">Make any needed changes.</span></span> <span data-ttu-id="445dd-421">Wanneer u klaar bent, kiest u **Maken.**</span><span class="sxs-lookup"><span data-stu-id="445dd-421">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="445dd-422">Sta ongeveer één uur toe dat uw nieuwe DLP-beleid zijn weg door uw datacenter kan vinden.</span><span class="sxs-lookup"><span data-stu-id="445dd-422">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="445dd-423">Aanverwante artikelen</span><span class="sxs-lookup"><span data-stu-id="445dd-423">Related articles</span></span>

- [<span data-ttu-id="445dd-424">Definities van entiteiten van het type gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="445dd-424">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="445dd-425">Meer informatie over typen gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="445dd-425">Learn about sensitive information types</span></span>](sensitive-information-type-learn-about.md)
- [<span data-ttu-id="445dd-426">Meer informatie over preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="445dd-426">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="445dd-427">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="445dd-427">Microsoft Cloud App Security</span></span>](/cloud-app-security)
- [<span data-ttu-id="445dd-428">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="445dd-428">New-DlpEdmSchema</span></span>](/powershell/module/exchange/new-dlpedmschema)
- [<span data-ttu-id="445dd-429">Schema exacte gegevensmatch wijzigen om configureerbare overeenkomst te gebruiken</span><span class="sxs-lookup"><span data-stu-id="445dd-429">Modify Exact Data Match schema to use configurable match</span></span>](sit-modify-edm-schema-configurable-match.md)
