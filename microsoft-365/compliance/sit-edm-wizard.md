---
title: De wizard voor het schema voor exacte gegevensovereenkomst en het type gevoelige informatie gebruiken
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
description: Leer hoe u de wizard voor het schema voor exacte gegevensovereenkomst en het type gevoelige informatie gebruikt.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2081de887e09794350222dac3527bb3ff932837a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/16/2020
ms.locfileid: "52161556"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a><span data-ttu-id="5264c-103">De wizard voor het schema voor exacte gegevensovereenkomst en het type gevoelige informatie gebruiken</span><span class="sxs-lookup"><span data-stu-id="5264c-103">Use the Exact Data Match Schema and Sensitive Information Type Wizard</span></span>

<span data-ttu-id="5264c-104">[Het maken van een aangepast type gevoelige informatie met EDM-gebaseerde (exacte gegevensovereenkomst) classificatie](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) bestaat uit vele stappen.</span><span class="sxs-lookup"><span data-stu-id="5264c-104">[Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)  involves many steps.</span></span>  <span data-ttu-id="5264c-105">U kunt deze wizard gebruiken om uw patroonbestanden (regelpakket) voor het schema en het type gevoelige informatie te maken om het proces te vereenvoudigen.</span><span class="sxs-lookup"><span data-stu-id="5264c-105">You can use this wizard to create your schema and sensitive information type pattern (rule package) files to help simplify the process.</span></span>

> [!NOTE]
> <span data-ttu-id="5264c-106">De wizard voor het schema voor exacte gegevensovereenkomst en het type gevoelige informatie is alleen beschikbaar voor de wereldwijde en GCC-cloud.</span><span class="sxs-lookup"><span data-stu-id="5264c-106">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

<span data-ttu-id="5264c-107">Deze wizard kan worden gebruikt in plaats van de:</span><span class="sxs-lookup"><span data-stu-id="5264c-107">This wizard can be used instead of the:</span></span>

- [<span data-ttu-id="5264c-108">Het schema voor uw database met gevoelige informatie definiëren</span><span class="sxs-lookup"><span data-stu-id="5264c-108">Define the schema for your database of sensitive information</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [<span data-ttu-id="5264c-109">Een patroon (regelpakket) instellen</span><span class="sxs-lookup"><span data-stu-id="5264c-109">Set up a pattern (rule package)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

<span data-ttu-id="5264c-110">stappen in [Deel 1: EDM-gebaseerde classificatie instellen](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span><span class="sxs-lookup"><span data-stu-id="5264c-110">steps in [Part 1: Set up EDM-based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="5264c-111">Vereisten</span><span class="sxs-lookup"><span data-stu-id="5264c-111">Pre-requisites</span></span>

1. <span data-ttu-id="5264c-112">Maak uzelf bekend met de stappen voor het maken van een aangepast type gevoelige informatie met EDM [werkstroom in een oogopslag](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).</span><span class="sxs-lookup"><span data-stu-id="5264c-112">Familiarize yourself with the steps to create a custom sensitive information type with EDM [work flow at a glance](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).</span></span>

2. <span data-ttu-id="5264c-113">Voer de stappen uit in de sectie [Gevoelige gegevens opslaan in CSV-indeling](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format).</span><span class="sxs-lookup"><span data-stu-id="5264c-113">Perform the steps in the [Save sensitive data in .csv format](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format) section.</span></span>

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a><span data-ttu-id="5264c-114">De wizard voor het schema voor exacte gegevensovereenkomst en het patroon voor het type gevoelige informatie gebruiken</span><span class="sxs-lookup"><span data-stu-id="5264c-114">Use the exact data match schema and sensitive information type pattern wizard</span></span>

1. <span data-ttu-id="5264c-115">Ga in het Microsoft 365-compliancecentrum voor uw tenant naar **Gegevensclassificatie** > **Exacte gegevensoverkomsten**.</span><span class="sxs-lookup"><span data-stu-id="5264c-115">In the Microsoft 365 Compliance center for your tenant go to **Data classification** > **Exact data matches**.</span></span>

2. <span data-ttu-id="5264c-116">Kies **EDM-schema maken** om de configuratie-flyout van de wizard te openen.</span><span class="sxs-lookup"><span data-stu-id="5264c-116">Choose **Create EDM schema** to open the schema wizard configuration flyout.</span></span>

![Configuratie-flyout van de wizard EDM-schema maken](../media/edm-schema-wizard-1.png)

3. <span data-ttu-id="5264c-118">Vul een toepasselijke **Naam** en **Beschrijving** in.</span><span class="sxs-lookup"><span data-stu-id="5264c-118">Fill in an appropriate **Name** and **Description**.</span></span>

4. <span data-ttu-id="5264c-119">Kies **Scheidingstekens en leestekens negeren voor alle schemavelden** als u dat wilt.</span><span class="sxs-lookup"><span data-stu-id="5264c-119">Choose **Ignore delimiters and punctuations for all schema fields** if you want that behavior.</span></span> <span data-ttu-id="5264c-120">Zie [Een aangepast type gevoelige informatie maken met EDM-gebaseerde (exacte gegevensovereenkomst) classificatie](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) voor meer informatie over het configureren van EDM om hoofdletters of scheidingsteken te negeren.</span><span class="sxs-lookup"><span data-stu-id="5264c-120">To learn more about configuring EDM to ignore case or delimitere, see [Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

5. <span data-ttu-id="5264c-121">Vul de gewenste waarden in voor uw **Schemaveld #1** en voeg zo nodig meer velden toe.</span><span class="sxs-lookup"><span data-stu-id="5264c-121">Fill in your desired values for your **Schema field #1** and add more fields as needed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="5264c-122">Ten minste één (maar niet meer dan vijf) van uw schemavelden moet worden aangewezen als doorzoekbaar.</span><span class="sxs-lookup"><span data-stu-id="5264c-122">At least one, but no more than five of your schema fields must be designated as searchable.</span></span>

6. <span data-ttu-id="5264c-123">Kies Opslaan.</span><span class="sxs-lookup"><span data-stu-id="5264c-123">Choose save.</span></span> <span data-ttu-id="5264c-124">Uw schema wordt nu vermeld.</span><span class="sxs-lookup"><span data-stu-id="5264c-124">Your schema will now be listed.</span></span>

7. <span data-ttu-id="5264c-125">Kies **Typen gevoelige informatie met EDM** en **Type gevoelige informatie met EDM maken** om de configuratiewizard voor typen gevoelige informatie te openen.</span><span class="sxs-lookup"><span data-stu-id="5264c-125">Choose **EDM sensitive info types** and **Create EDM sensitive info type** to open the sensitive info type configuration wizard.</span></span>

8. <span data-ttu-id="5264c-126">Kies **Een bestaand EDM-schema kiezen** en kies het schema dat u in stap 2-6 hebt gemaakt uit de lijst.</span><span class="sxs-lookup"><span data-stu-id="5264c-126">Choose **Choose an existing EDM schema** and choose the schema you created in steps 2-6 from the list.</span></span>

9. <span data-ttu-id="5264c-127">Kies **Volgende** en kies **Patroon maken**.</span><span class="sxs-lookup"><span data-stu-id="5264c-127">Choose **Next** and choose **Create pattern**.</span></span>

10. <span data-ttu-id="5264c-128">Kies het **Betrouwbaarheidsniveau** en **Primaire element**.</span><span class="sxs-lookup"><span data-stu-id="5264c-128">Choose the **Confidence level** and **Primary element**.</span></span>  <span data-ttu-id="5264c-129">Zie [Een aangepast type gevoelige informatie maken in het Compliancecentrum](create-a-custom-sensitive-information-type.md) voor meer informatie over het configureren van een patroon.</span><span class="sxs-lookup"><span data-stu-id="5264c-129">To learn more about configuring a pattern, see [Create a custom sensitive information type in the Compliance Center](create-a-custom-sensitive-information-type.md)</span></span>

11.  <span data-ttu-id="5264c-130">Kies het **Type gevoelige informatie van het primaire element** waaraan het moet worden gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="5264c-130">Choose the **Primary element's sensitive info type** to associate it with.</span></span> <span data-ttu-id="5264c-131">Zie [Entiteitsdefinities van typen gevoelige informatie](sensitive-information-type-entity-definitions.md) voor meer informatie over de beschikbare typen gevoelige informatie.</span><span class="sxs-lookup"><span data-stu-id="5264c-131">See [Sensitive Information Type Entity Definitions](sensitive-information-type-entity-definitions.md) to learn more about the available sensitive information types.</span></span>

12. <span data-ttu-id="5264c-132">Kies **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="5264c-132">Choose **Done**.</span></span>

13. <span data-ttu-id="5264c-133">Kies uw gewenste **Betrouwbaarheidsniveau en tekennabijheid**.</span><span class="sxs-lookup"><span data-stu-id="5264c-133">Choose your desired **Confidence level and character proximity**.</span></span>  <span data-ttu-id="5264c-134">Dit is de standaardwaarde voor het hele type gevoelige informatie met EDM</span><span class="sxs-lookup"><span data-stu-id="5264c-134">This will be the default value for the whole EDM sensitive info type</span></span>

13. <span data-ttu-id="5264c-135">Kies **Patroon maken** als u aanvullende patronen wilt maken voor uw type gevoelige informatie met EDM.</span><span class="sxs-lookup"><span data-stu-id="5264c-135">Choose **Create pattern** if you want to creaet additional patterns for your EDM sensitive info type.</span></span>

14. <span data-ttu-id="5264c-136">Kies **Volgende** en vul een **Naam** en **Beschrijving voor beheerders** in.</span><span class="sxs-lookup"><span data-stu-id="5264c-136">Choose **Next** and fill in a **Name** and **Description for admins**.</span></span>

15. <span data-ttu-id="5264c-137">Controleer uw invoer en kies **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="5264c-137">Review and choose **Submit**.</span></span>

<span data-ttu-id="5264c-138">U kunt het patroon voor het type gevoelige informatie verwijderen of bewerken door het te selecteren, waarna de besturingselementen voor bewerken en verwijderen worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="5264c-138">You can delete or edit the sensitive information type pattern by selecting it which surfaces the edit and delete controls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5264c-139">Als u een schema wilt verwijderen dat al is gekoppeld aan een type gevoelige informatie met EDM, moet u eerst het type gevoelige informatie met EDM verwijderen. Vervolgens kunt u het schema verwijderen.</span><span class="sxs-lookup"><span data-stu-id="5264c-139">If you want to remove a schema, and it is already associated with an EDM sensitive info type, you must first delete the EDM sensitive info type, then you can delete the schema.</span></span>

## <a name="post-steps"></a><span data-ttu-id="5264c-140">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="5264c-140">Post steps</span></span>

<span data-ttu-id="5264c-141">Nadat u deze wizard hebt gebruikt om uw EDM-schema en patroonbestanden (regelpakket) te maken, moet u nog steeds de stappen in [Deel 2: De gevoelige gegevens hashen en uploaden](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) uitvoeren voordat u het aangepaste type gevoelige informatie met EDM kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="5264c-141">After you have used this wizard to create your EDM schema and pattern (rule package) files, you still have to perform the steps in [Part 2: Hash and upload the sensitive data](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) before you can use the EDM custom sensitive information type.</span></span>