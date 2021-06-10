---
title: De wizard voor het schema voor exacte gegevensovereenkomst en het type gevoelige informatie gebruiken
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Leer hoe u de wizard voor het schema voor exacte gegevensovereenkomst en het type gevoelige informatie gebruikt.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d9d6f870239b963ee7483b9f08e93e40b10f4f0b
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878002"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a><span data-ttu-id="a8315-103">De wizard voor het schema voor exacte gegevensovereenkomst en het type gevoelige informatie gebruiken</span><span class="sxs-lookup"><span data-stu-id="a8315-103">Use the Exact Data Match Schema and Sensitive Information Type Wizard</span></span>

<span data-ttu-id="a8315-104">[Het maken van een aangepast type gevoelige informatie met EDM-gebaseerde (exacte gegevensovereenkomst) classificatie](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) bestaat uit vele stappen.</span><span class="sxs-lookup"><span data-stu-id="a8315-104">[Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)  involves many steps.</span></span>  <span data-ttu-id="a8315-105">U kunt deze wizard gebruiken om bestanden met het schema en het gevoelige informatietype (SIT)-patroon (regelpakket) te maken om het proces te vereenvoudigen.</span><span class="sxs-lookup"><span data-stu-id="a8315-105">You can use this wizard to create your schema and sensitive information type (SIT) pattern (rule package) files to help simplify the process.</span></span>

> [!NOTE]
> <span data-ttu-id="a8315-106">De wizard voor het schema voor exacte gegevensovereenkomst en het type gevoelige informatie is alleen beschikbaar voor de wereldwijde en GCC-cloud.</span><span class="sxs-lookup"><span data-stu-id="a8315-106">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

<span data-ttu-id="a8315-107">Deze wizard kan worden gebruikt in plaats van de:</span><span class="sxs-lookup"><span data-stu-id="a8315-107">This wizard can be used instead of the:</span></span>

- [<span data-ttu-id="a8315-108">Het schema voor uw database met gevoelige informatie definiëren</span><span class="sxs-lookup"><span data-stu-id="a8315-108">Define the schema for your database of sensitive information</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [<span data-ttu-id="a8315-109">Een patroon (regelpakket) instellen</span><span class="sxs-lookup"><span data-stu-id="a8315-109">Set up a pattern (rule package)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

<span data-ttu-id="a8315-110">stappen in [Deel 1: EDM-gebaseerde classificatie instellen](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span><span class="sxs-lookup"><span data-stu-id="a8315-110">steps in [Part 1: Set up EDM-based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="a8315-111">Vereisten</span><span class="sxs-lookup"><span data-stu-id="a8315-111">Pre-requisites</span></span>

1. <span data-ttu-id="a8315-112">Maak uzelf bekend met de stappen voor het maken van een aangepast type gevoelige informatie met EDM [werkstroom in een oogopslag](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).</span><span class="sxs-lookup"><span data-stu-id="a8315-112">Familiarize yourself with the steps to create a custom sensitive information type with EDM [work flow at a glance](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).</span></span>

2. <span data-ttu-id="a8315-113">Voer de stappen uit in [Gevoelige gegevens opslaan in .csv of .tsv-indeling.](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-or-tsv-format)</span><span class="sxs-lookup"><span data-stu-id="a8315-113">Perform the steps in [Save sensitive data in .csv or .tsv format](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-or-tsv-format).</span></span>

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a><span data-ttu-id="a8315-114">De wizard voor het schema voor exacte gegevensovereenkomst en het patroon voor het type gevoelige informatie gebruiken</span><span class="sxs-lookup"><span data-stu-id="a8315-114">Use the exact data match schema and sensitive information type pattern wizard</span></span>

1. <span data-ttu-id="a8315-115">Ga in het Microsoft 365-compliancecentrum voor uw tenant naar **Gegevensclassificatie** > **Exacte gegevensoverkomsten**.</span><span class="sxs-lookup"><span data-stu-id="a8315-115">In the Microsoft 365 Compliance center for your tenant go to **Data classification** > **Exact data matches**.</span></span>

2. <span data-ttu-id="a8315-116">Kies **EDM-schema maken** om de configuratie-flyout van de wizard te openen.</span><span class="sxs-lookup"><span data-stu-id="a8315-116">Choose **Create EDM schema** to open the schema wizard configuration flyout.</span></span>

![Configuratie-flyout van de wizard EDM-schema maken](../media/edm-schema-wizard-1.png)

3. <span data-ttu-id="a8315-118">Vul een toepasselijke **Naam** en **Beschrijving** in.</span><span class="sxs-lookup"><span data-stu-id="a8315-118">Fill in an appropriate **Name** and **Description**.</span></span>

4. <span data-ttu-id="a8315-119">Kies **Scheidingstekens en interpunctie negeren** voor alle schemavelden als u dat wilt.</span><span class="sxs-lookup"><span data-stu-id="a8315-119">Choose **Ignore delimiters and punctuation for all schema fields** if you want that behavior.</span></span> <span data-ttu-id="a8315-120">Zie Een aangepast type gevoelige informatie maken met de classificatie [Exact Data Match (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)voor meer informatie over het configureren van EDM om case's of scheidingstekens te negeren.</span><span class="sxs-lookup"><span data-stu-id="a8315-120">To learn more about configuring EDM to ignore case or delimiters, see [Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

5. <span data-ttu-id="a8315-121">Vul de gewenste waarden in voor uw **Schemaveld #1** en voeg zo nodig meer velden toe.</span><span class="sxs-lookup"><span data-stu-id="a8315-121">Fill in your desired values for your **Schema field #1** and add more fields as needed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="a8315-122">Ten minste één (maar niet meer dan vijf) van uw schemavelden moet worden aangewezen als doorzoekbaar.</span><span class="sxs-lookup"><span data-stu-id="a8315-122">At least one, but no more than five of your schema fields must be designated as searchable.</span></span>

6. <span data-ttu-id="a8315-123">Kies Opslaan.</span><span class="sxs-lookup"><span data-stu-id="a8315-123">Choose save.</span></span> <span data-ttu-id="a8315-124">Uw schema wordt nu vermeld.</span><span class="sxs-lookup"><span data-stu-id="a8315-124">Your schema will now be listed.</span></span>

7. <span data-ttu-id="a8315-125">Kies **Typen gevoelige informatie met EDM** en **Type gevoelige informatie met EDM maken** om de configuratiewizard voor typen gevoelige informatie te openen.</span><span class="sxs-lookup"><span data-stu-id="a8315-125">Choose **EDM sensitive info types** and **Create EDM sensitive info type** to open the sensitive info type configuration wizard.</span></span>

8. <span data-ttu-id="a8315-126">Kies **Een bestaand EDM-schema kiezen** en kies het schema dat u in stap 2-6 hebt gemaakt uit de lijst.</span><span class="sxs-lookup"><span data-stu-id="a8315-126">Choose **Choose an existing EDM schema** and choose the schema you created in steps 2-6 from the list.</span></span>

9. <span data-ttu-id="a8315-127">Kies **Volgende** en kies **Patroon maken**.</span><span class="sxs-lookup"><span data-stu-id="a8315-127">Choose **Next** and choose **Create pattern**.</span></span>

10. <span data-ttu-id="a8315-128">Kies het **Betrouwbaarheidsniveau** en **Primaire element**.</span><span class="sxs-lookup"><span data-stu-id="a8315-128">Choose the **Confidence level** and **Primary element**.</span></span>  <span data-ttu-id="a8315-129">Zie [Een aangepast type gevoelige informatie maken in het Compliancecentrum](create-a-custom-sensitive-information-type.md) voor meer informatie over het configureren van een patroon.</span><span class="sxs-lookup"><span data-stu-id="a8315-129">To learn more about configuring a pattern, see [Create a custom sensitive information type in the Compliance Center](create-a-custom-sensitive-information-type.md)</span></span>

11.  <span data-ttu-id="a8315-130">Kies het **Type gevoelige informatie van het primaire element** waaraan het moet worden gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="a8315-130">Choose the **Primary element's sensitive info type** to associate it with.</span></span> <span data-ttu-id="a8315-131">Zie [Entiteitsdefinities van typen gevoelige informatie](sensitive-information-type-entity-definitions.md) voor meer informatie over de beschikbare typen gevoelige informatie.</span><span class="sxs-lookup"><span data-stu-id="a8315-131">See [Sensitive Information Type Entity Definitions](sensitive-information-type-entity-definitions.md) to learn more about the available sensitive information types.</span></span>

12. <span data-ttu-id="a8315-132">Kies **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="a8315-132">Choose **Done**.</span></span>

13. <span data-ttu-id="a8315-133">Kies uw gewenste **Betrouwbaarheidsniveau en tekennabijheid**.</span><span class="sxs-lookup"><span data-stu-id="a8315-133">Choose your desired **Confidence level and character proximity**.</span></span>  <span data-ttu-id="a8315-134">Dit is de standaardwaarde voor het hele type gevoelige informatie met EDM</span><span class="sxs-lookup"><span data-stu-id="a8315-134">This will be the default value for the whole EDM sensitive info type</span></span>

13. <span data-ttu-id="a8315-135">Kies **Patroon maken** als u extra patronen wilt maken voor uw EDM-gevoelige informatietype.</span><span class="sxs-lookup"><span data-stu-id="a8315-135">Choose **Create pattern** if you want to create additional patterns for your EDM sensitive info type.</span></span>

14. <span data-ttu-id="a8315-136">Kies **Volgende** en vul een **Naam** en **Beschrijving voor beheerders** in.</span><span class="sxs-lookup"><span data-stu-id="a8315-136">Choose **Next** and fill in a **Name** and **Description for admins**.</span></span>

15. <span data-ttu-id="a8315-137">Controleer uw invoer en kies **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="a8315-137">Review and choose **Submit**.</span></span>

<span data-ttu-id="a8315-138">U kunt het patroon voor het type gevoelige informatie verwijderen of bewerken door het te selecteren, waarna de besturingselementen voor bewerken en verwijderen worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a8315-138">You can delete or edit the sensitive information type pattern by selecting it which surfaces the edit and delete controls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8315-139">Als u een schema wilt verwijderen dat al is gekoppeld aan een type gevoelige informatie met EDM, moet u eerst het type gevoelige informatie met EDM verwijderen. Vervolgens kunt u het schema verwijderen.</span><span class="sxs-lookup"><span data-stu-id="a8315-139">If you want to remove a schema, and it is already associated with an EDM sensitive info type, you must first delete the EDM sensitive info type, then you can delete the schema.</span></span>

## <a name="post-creation-steps"></a><span data-ttu-id="a8315-140">Stappen voor het maken van berichten</span><span class="sxs-lookup"><span data-stu-id="a8315-140">Post creation steps</span></span>

<span data-ttu-id="a8315-141">Nadat u deze wizard hebt gebruikt om uw EDM-schema en patroonbestanden (regelpakket) te maken, moet u nog steeds de stappen in [Deel 2: De gevoelige gegevens hashen en uploaden](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) uitvoeren voordat u het aangepaste type gevoelige informatie met EDM kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a8315-141">After you have used this wizard to create your EDM schema and pattern (rule package) files, you still have to perform the steps in [Part 2: Hash and upload the sensitive data](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) before you can use the EDM custom sensitive information type.</span></span>

<span data-ttu-id="a8315-142">Nadat u hebt gecontroleerd of de tabel met gevoelige informatie correct is geüpload, kunt u testen of deze correct werkt.</span><span class="sxs-lookup"><span data-stu-id="a8315-142">After verifying that your sensitive information table has correctly been uploaded, you can test that it's working properly.</span></span>

1. <span data-ttu-id="a8315-143">Open **Compliancecentrum**  >  **Gegevensclassificatie**  >  **Gevoelige informatietypen**.</span><span class="sxs-lookup"><span data-stu-id="a8315-143">Open **Compliance center** > **Data classification** > **Sensitive Information Types**.</span></span>
2. <span data-ttu-id="a8315-144">Selecteer uw EDM SIT in de lijst en selecteer **vervolgens Testen** in het deelvenster Flyout.</span><span class="sxs-lookup"><span data-stu-id="a8315-144">Select your EDM SIT from the list and then select **Test** in the flyout pane.</span></span> 
3. <span data-ttu-id="a8315-145">Upload item dat gegevens bevat die u wilt detecteren, bijvoorbeeld een item maken dat een deel van de gegevens in de tabel met gevoelige informatie bevat.</span><span class="sxs-lookup"><span data-stu-id="a8315-145">Upload an item that contains data you want to detect, for example create an item that contains some of the data in your sensitive information table.</span></span> <span data-ttu-id="a8315-146">Als u de configureerbare overeenkomstfunctie in uw schema hebt gebruikt om genegeerde scheidingstekens te definiëren, moet u ervoor zorgen dat het item voorbeelden bevat met en zonder deze scheidingstekens.</span><span class="sxs-lookup"><span data-stu-id="a8315-146">If you used the configurable match feature in your schema to define ignored delimiters, make sure the item includes examples with and without those delimiters.</span></span>
4. <span data-ttu-id="a8315-147">Nadat het bestand is geüpload en gescand, controleert u op overeenkomsten met uw EDM SIT.</span><span class="sxs-lookup"><span data-stu-id="a8315-147">After the file has been uploaded and scanned, check for matches to your EDM SIT.</span></span>
5. <span data-ttu-id="a8315-148">Als de **functie Test** in de SIT een overeenkomst detecteert, controleert u of deze niet wordt bijgesneden of niet onjuist wordt geëxtraheert.</span><span class="sxs-lookup"><span data-stu-id="a8315-148">If the **Test** function in the SIT detects a match, check that it is not trimming it or extracting it incorrectly.</span></span> <span data-ttu-id="a8315-149">Bijvoorbeeld door alleen een subtekenreeks op te halen van de volledige tekenreeks die deze moet detecteren, of door alleen het eerste woord in een tekenreeks met meerdere woorden op te halen, of door extra symbolen of tekens in de extractie op te nemen.</span><span class="sxs-lookup"><span data-stu-id="a8315-149">For example by extracting only a substring of the full string it is supposed to detect, or picking up only the first word in a multi-word string, or including extra symbols or characters in the extraction.</span></span> <span data-ttu-id="a8315-150">Zie [Normale expressietaal - Snelle verwijzing voor](/dotnet/standard/base-types/regular-expression-language-quick-reference) de reguliere verwijzing naar expressietaal.</span><span class="sxs-lookup"><span data-stu-id="a8315-150">See [Regular Expression Language - Quick Reference](/dotnet/standard/base-types/regular-expression-language-quick-reference) for the regular expression language reference.</span></span> 

### <a name="troubleshooting"></a><span data-ttu-id="a8315-151">Problemen oplossen</span><span class="sxs-lookup"><span data-stu-id="a8315-151">Troubleshooting</span></span>

<span data-ttu-id="a8315-152">Als u geen overeenkomsten vindt, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="a8315-152">If you don't find any matches, try the following:</span></span>
- <span data-ttu-id="a8315-153">Controleer of uw gevoelige gegevens correct zijn geüpload met behulp van de opdrachten die worden uitgelegd in de richtlijnen voor het uploaden van uw gevoelige gegevens met het [hulpprogramma EDM.](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)</span><span class="sxs-lookup"><span data-stu-id="a8315-153">Confirm that your sensitive data was uploaded correctly using the commands explained in [the guidance for uploading your sensitive data using the EDM tool](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>
- <span data-ttu-id="a8315-154">Controleer of de voorbeelden die u hebt ingevoerd in het item aanwezig zijn in de tabel met gevoelige informatie en of de genegeerde scheidingstekens juist zijn.</span><span class="sxs-lookup"><span data-stu-id="a8315-154">Check that the examples you entered in the item are present in your sensitive information table and that the ignored delimiters are correct.</span></span>
- <span data-ttu-id="a8315-155">**Test** de SIT die u hebt gebruikt bij het configureren van het primaire element in elk van uw patronen.</span><span class="sxs-lookup"><span data-stu-id="a8315-155">**Test** the SIT you used when you configured the primary element in each of your patterns.</span></span> <span data-ttu-id="a8315-156">Hiermee wordt bevestigd dat de SIT kan overeenkomen met de voorbeelden in het item.</span><span class="sxs-lookup"><span data-stu-id="a8315-156">This will confirm that the SIT is able to match the examples in the item.</span></span> 
  -  <span data-ttu-id="a8315-157">Als de SIT die u hebt geselecteerd voor een primair element in het EDM-type, geen overeenkomst in het item vindt of minder overeenkomsten vindt dan u verwacht, controleert u of het scheidingstekens en scheidingstekens ondersteunt die in de inhoud aanwezig zijn.</span><span class="sxs-lookup"><span data-stu-id="a8315-157">If the SIT you selected for a primary element in the EDM type doesn't find a match in the item or finds fewer matches than you expected, check that it supports separators and delimiters that exist in the content.</span></span> <span data-ttu-id="a8315-158">Zorg ervoor dat u de genegeerde scheidingstekens in uw schema op moet nemen.</span><span class="sxs-lookup"><span data-stu-id="a8315-158">Be sure to include the ignored delimiters defined in your schema.</span></span> 
  -  <span data-ttu-id="a8315-159">Als de **functie Test** helemaal geen inhoud detecteert, controleert u of de sit die u hebt geselecteerd vereisten bevat voor aanvullende trefwoorden of andere validaties.</span><span class="sxs-lookup"><span data-stu-id="a8315-159">If the **Test** function does not detect any content at all, check if the SIT you selected includes requirements for additional keywords or other validations.</span></span> <span data-ttu-id="a8315-160">Zie Entiteitsdefinities voor [](sensitive-information-type-entity-definitions.md) gevoelige informatietypen voor de ingebouwde ST's om te controleren wat de minimumvereisten zijn voor het overeenkomen van elk type.</span><span class="sxs-lookup"><span data-stu-id="a8315-160">For the built-in SITs, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md) to verify what the minimum requirements are for matching each type.</span></span>
