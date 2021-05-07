---
title: Wijzig het schema voor exacte gegevensovereenkomst om een configureerbare overeenkomst te gebruiken
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Lees hoe u een edm-schema kunt wijzigen om configureerbare overeenkomst te gebruiken.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7d470b986d4a94206935efb832deec7171f8e404
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162913"
---
# <a name="modify-exact-data-match-schema-to-use-configurable-match"></a><span data-ttu-id="9afa1-103">Wijzig het schema voor exacte gegevensovereenkomst om een configureerbare overeenkomst te gebruiken</span><span class="sxs-lookup"><span data-stu-id="9afa1-103">Modify Exact Data Match schema to use configurable match</span></span>

<span data-ttu-id="9afa1-104">Met EDM-classificatie (exacte gegevensovereenkomst) kunt u aangepaste typen gevoelige informatie maken die verwijzen naar exacte waarden in een database met gevoelige informatie.</span><span class="sxs-lookup"><span data-stu-id="9afa1-104">Exact Data Match (EDM) based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="9afa1-105">Wanneer u varianten van een exacte tekenreeks wilt toestaan, kunt u *configureerbare overeenkomst* gebruiken om Microsoft 365 op te geven dat hoofdletters en bepaalde scheidingstekens moeten worden genegeerd.</span><span class="sxs-lookup"><span data-stu-id="9afa1-105">When you need to allow for variants of a exact string, you can use *configurable match* to tell Microsoft 365 to ignore case and some delimiters.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="9afa1-106">Gebruik deze procedure om een bestaand EDM-schema en gegevensbestand te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="9afa1-106">Use this procedure to modify an existing EDM schema and data file.</span></span>

1. <span data-ttu-id="9afa1-107">Verwijder de **EdmUploadAgent.exe** van de computer die u gebruikt om verbinding te maken met Microsoft 365 voor het EDM-schema en voor uploaddoeleinden van gegevensbestand.</span><span class="sxs-lookup"><span data-stu-id="9afa1-107">Uninstall the **EdmUploadAgent.exe** from the computer that you use to connect to Microsoft 365 for EDM schema and data file upload purposes.</span></span>

2. <span data-ttu-id="9afa1-108">Download het juiste **EdmUploadAgent.exe** bestand voor uw abonnement via de onderstaande koppelingen:</span><span class="sxs-lookup"><span data-stu-id="9afa1-108">Download the appropriate **EdmUploadAgent.exe** file for your subscription using the links below:</span></span>
    - <span data-ttu-id="9afa1-109">[Commercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - de meeste commerciële klanten moeten dit gebruiken</span><span class="sxs-lookup"><span data-stu-id="9afa1-109">[Commercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - most commercial customers should use this</span></span>
    - <span data-ttu-id="9afa1-110">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - Dit is specifiek voor abonnees van de cloud van de overheid met hoge beveiliging</span><span class="sxs-lookup"><span data-stu-id="9afa1-110">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - This is specifically for high security government cloud subscribers</span></span>
    - <span data-ttu-id="9afa1-111">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - dit is specifiek voor klanten van de cloud van het Department of Defense van de Verenigde Staten</span><span class="sxs-lookup"><span data-stu-id="9afa1-111">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - this is specifically for United States Department of Defense cloud customers</span></span>

3. <span data-ttu-id="9afa1-112">Autoriseer de EDM Upload Agent, open het opdrachtpromptvenster (als administrator) en voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="9afa1-112">Authorize the EDM Upload Agent, open Command Prompt window (as an administrator) and run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

4. <span data-ttu-id="9afa1-113">Als u nog geen kopie van het bestaande schema hebt, moet u een kopie van het bestaande schema downloaden. Voer deze opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="9afa1-113">If you don't have a current copy of the existing schema, you'll need to download a copy of the existing schema, run this command:</span></span>

    `EdmUploadAgent.exe /SaveSchema /DataStoreName <dataStoreName> [/OutputDir [Output dir location]]`

5. <span data-ttu-id="9afa1-114">Pas het schema aan zodat elke kolom gebruikmaakt van 'caseInsensitive' en / of 'ignoredDelimiters'.</span><span class="sxs-lookup"><span data-stu-id="9afa1-114">Customize the schema so each column utilizes “caseInsensitive” and / or “ignoredDelimiters”.</span></span>  <span data-ttu-id="9afa1-115">De standaardwaarde voor 'caseInsensitive' is 'false' en voor 'ignoredDelimiters' is het een lege tekenreeks.</span><span class="sxs-lookup"><span data-stu-id="9afa1-115">The default value for “caseInsensitive” is “false” and for “ignoredDelimiters”, it is an empty string.</span></span> 

> [!NOTE]
> <span data-ttu-id="9afa1-116">Het onderliggende type aangepaste gevoelige informatie of het ingebouwde type gevoelige informatie waarmee het algemene reguliere expressie-patroon wordt gedetecteerd, moet de detectie van variaties die worden vermeld bij 'ignoredDelimiters' ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="9afa1-116">The underlying custom sensitive information type or built in sensitive information type used to detect the general regex pattern must support detection of the variations inputs listed with ignoredDelimiters.</span></span> <span data-ttu-id="9afa1-117">Met het ingebouwde type gevoelige informatie van het Amerikaanse socialezekerheidsnummer (SSN) kunnen bijvoorbeeld variaties in de gegevens worden gedetecteerd die streepjes, spaties of gebrek aan spaties bevatten tussen de gegroepeerde getallen waartussen de SSN bestaat.</span><span class="sxs-lookup"><span data-stu-id="9afa1-117">For example, the built in U.S. social security number (SSN) sensitive information type can detect variations in the data that include dashes, spaces, or lack of spaces between the grouped numbers that make up the SSN.</span></span> <span data-ttu-id="9afa1-118">Daardoor zijn de enige scheidingstekens die relevant zijn voor het opnemen in ignoredDelimiters van EDM voor SSN-gegevens: streepje en spatie.</span><span class="sxs-lookup"><span data-stu-id="9afa1-118">As a result, the only delimiters that are relevant to include in EDM’s ignoredDelimiters for SSN data are: dash and space.</span></span>

<span data-ttu-id="9afa1-119">Hier ziet u een voorbeeldschema waarin een niet-hoofdlettergevoelige overeenkomst wordt nagebootst door de extra kolommen te maken die nodig zijn om variaties in de hoofdletters in de gevoelige gegevens te herkennen.</span><span class="sxs-lookup"><span data-stu-id="9afa1-119">Here is a sample schema that simulates case insensitive match by creating the extra columns needed to recognize case variations in the sensitive data.</span></span>

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
           <Field name="PolicyNumber" searchable="true" />
           <Field name="PolicyNumberLowerCase" searchable="true" />
           <Field name="PolicyNumberUpperCase" searchable="true" />
           <Field name="PolicyNumberCapitalLetters" searchable="true" />
  </DataStore>
</EdmSchema>
```

<span data-ttu-id="9afa1-120">In het bovenstaande voorbeeld zijn de variaties van de oorspronkelijke kolom `PolicyNumber` niet meer nodig als zowel `caseInsensitive` als `ignoredDelimiters` zijn toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="9afa1-120">In the above example, the variations of the original `PolicyNumber` column will no longer be needed if both `caseInsensitive` and `ignoredDelimiters` are added.</span></span>

<span data-ttu-id="9afa1-121">Als u dit schema wilt bijwerken, zodat EDM gebruikmaakt van configureerbare overeenkomst, gebruikt `caseInsensitive` en `ignoredDelimiters` vlaggen.</span><span class="sxs-lookup"><span data-stu-id="9afa1-121">To update this schema so that EDM uses configurable match use the `caseInsensitive` and `ignoredDelimiters` flags.</span></span>  <span data-ttu-id="9afa1-122">Dit ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="9afa1-122">Here's how that looks:</span></span>

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
         <Field name="PolicyNumber" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
  </DataStore>
</EdmSchema>
```

<span data-ttu-id="9afa1-123">De `ignoredDelimiters` vlag ondersteunt alle niet-alfanumerieke tekens. Hier volgen enkele voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="9afa1-123">The `ignoredDelimiters` flag supports any non-alphanumeric character, here are some examples:</span></span>
- <span data-ttu-id="9afa1-124">\.</span><span class="sxs-lookup"><span data-stu-id="9afa1-124">\.</span></span>
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

<span data-ttu-id="9afa1-125">The `ignoredDelimiters` vlag ondersteunt het volgende niet:</span><span class="sxs-lookup"><span data-stu-id="9afa1-125">The `ignoredDelimiters` flag doesn't support:</span></span>
- <span data-ttu-id="9afa1-126">tekens 0-9</span><span class="sxs-lookup"><span data-stu-id="9afa1-126">characters 0-9</span></span>
- <span data-ttu-id="9afa1-127">A-Z</span><span class="sxs-lookup"><span data-stu-id="9afa1-127">A-Z</span></span>
- <span data-ttu-id="9afa1-128">a-z</span><span class="sxs-lookup"><span data-stu-id="9afa1-128">a-z</span></span>
- \"
- \,

6. <span data-ttu-id="9afa1-129">Verbinding maken met het Beveiligings- en compliancecentrum met behulp van de procedures in [Verbinding maken met Beveiligings- en compliancecentrum van PowerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="9afa1-129">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

> [!NOTE]
> <span data-ttu-id="9afa1-130">Als uw organisatie [Klantsleutel voor Microsoft 365 heeft ingesteld op tenantniveau (openbare preview)](customer-key-tenant-level.md#overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview), wordt de versleutelingsfunctionaliteit automatisch gebruikt door exacte gegevensmatch.</span><span class="sxs-lookup"><span data-stu-id="9afa1-130">If your organization has set up [Customer Key for Microsoft 365 at the tenant level (public preview)](customer-key-tenant-level.md#overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview), Exact data match will make use of its encryption functionality automatically.</span></span> <span data-ttu-id="9afa1-131">Dit is alleen beschikbaar voor E5-gelicentieerde tenants in de commerciële cloud.</span><span class="sxs-lookup"><span data-stu-id="9afa1-131">This is available only to E5 licensed tenants in the Commercial cloud.</span></span>

7. <span data-ttu-id="9afa1-132">Werk uw schema bij door deze cmdlets een voor een uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="9afa1-132">Update your schema by running these cmdlets one at a time:</span></span>

`$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0`

`Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

8. <span data-ttu-id="9afa1-133">Werk het gegevensbestand zo nodig bij aan de nieuwe schemaversie</span><span class="sxs-lookup"><span data-stu-id="9afa1-133">If necessary, update the data file to match the new schema version</span></span>

> [!TIP]
> <span data-ttu-id="9afa1-134">U kunt eventueel een validatie uitvoeren voor het CSV-bestand voordat u het uploadt. Voer het volgende uit:</span><span class="sxs-lookup"><span data-stu-id="9afa1-134">Optionally, you can run a validation against your csv file before uploading by running:</span></span>
>
>`EdmUploadAgent.exe /ValidateData /DataFile [data file] [schema file]`
>
><span data-ttu-id="9afa1-135">Voor meer informatie over alle EdmUploadAgent.exe >ondersteunde parameters uitvoeren</span><span class="sxs-lookup"><span data-stu-id="9afa1-135">For more information on all the EdmUploadAgent.exe >supported parameters run</span></span>
>
> `EdmUploadAgent.exe /?`

9. <span data-ttu-id="9afa1-136">Open het opdrachtpromptvenster (als administrator) en voer de volgende opdracht uit om uw gevoelige informatie te hashen en uploaden:</span><span class="sxs-lookup"><span data-stu-id="9afa1-136">Open Command Prompt window (as an administrator) and run the following command to hash and upload your sensitive data:</span></span>

    `EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Salt [custom salt] /Schema [Schema file]`


## <a name="related-articles"></a><span data-ttu-id="9afa1-137">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="9afa1-137">Related articles</span></span>

- [<span data-ttu-id="9afa1-138">Aangepaste typen gevoelige informatie maken met de classificatie van exacte gegevensovereenkomsten</span><span class="sxs-lookup"><span data-stu-id="9afa1-138">Create a custom sensitive information type with Exact Data Match based classification</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [<span data-ttu-id="9afa1-139">Definities van entiteiten van het type gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="9afa1-139">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="9afa1-140">Aangepaste typen gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="9afa1-140">Custom sensitive information types</span></span>](./sensitive-information-type-learn-about.md)
- [<span data-ttu-id="9afa1-141">Meer informatie over preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="9afa1-141">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="9afa1-142">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="9afa1-142">Microsoft Cloud App Security</span></span>](/cloud-app-security)
- [<span data-ttu-id="9afa1-143">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="9afa1-143">New-DlpEdmSchema</span></span>](/powershell/module/exchange/new-dlpedmschema)