---
title: Verwijzing naar aangepaste filters voor gevoelige informatie
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: In dit artikel wordt een lijst weergegeven met de filters die kunnen worden gecodeerd in aangepaste gevoelige informatietypen.
ms.openlocfilehash: 6dfa562d581f14c0b1ac41c4ce803e2367a94636
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322568"
---
# <a name="custom-sensitive-information-type-filters-reference"></a><span data-ttu-id="12cea-103">Verwijzing naar aangepaste filters voor het type gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="12cea-103">Custom sensitive information type filters reference</span></span>

<span data-ttu-id="12cea-104">In Microsoft kunt u filters of extra controles definiëren terwijl u een aangepaste, gevoelige informatietypen (SIT) maakt.</span><span class="sxs-lookup"><span data-stu-id="12cea-104">In Microsoft you can define filters or additional checks while creating a custom sensitive information types (SIT).</span></span>

## <a name="list-of-supported-filters-and-use-cases"></a><span data-ttu-id="12cea-105">Lijst met ondersteunde filters en use cases</span><span class="sxs-lookup"><span data-stu-id="12cea-105">List of supported filters and use cases</span></span>

### <a name="alldigitssame-exclude"></a><span data-ttu-id="12cea-106">AllDigitsSame Exclude</span><span class="sxs-lookup"><span data-stu-id="12cea-106">AllDigitsSame Exclude</span></span>

<span data-ttu-id="12cea-107">Beschrijving: Hiermee kunt u overeenkomsten uitsluiten die alle cijfers als dubbele cijfers hebben, zoals 111111111111 of 111-111-111-111</span><span class="sxs-lookup"><span data-stu-id="12cea-107">Description: Allows you to exclude matches which have all digits as duplicate digits, like 111111111 or 111-111-111</span></span>

<span data-ttu-id="12cea-108">Filters definiëren</span><span class="sxs-lookup"><span data-stu-id="12cea-108">Defining filters</span></span>
```xml
<Filters id="ssn_filters">
    <Filter type="AllDigitsSameFilter"></Filter>
</Filters>
```

<span data-ttu-id="12cea-109">Het gebruiken in een regelpakket op entiteitsniveau</span><span class="sxs-lookup"><span data-stu-id="12cea-109">Using it in rule package at the entity level</span></span>
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85"  filters="ssn_filters">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

<span data-ttu-id="12cea-110">Het gebruiken in een regelpakket op het patroonniveau</span><span class="sxs-lookup"><span data-stu-id="12cea-110">Using it in rule package at the pattern level</span></span>
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="ssn_filters">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

### <a name="textmatchfilter-startswith"></a><span data-ttu-id="12cea-111">TextMatchFilter StartsWith</span><span class="sxs-lookup"><span data-stu-id="12cea-111">TextMatchFilter StartsWith</span></span> 

<span data-ttu-id="12cea-112">Beschrijving: Hiermee kunt u de begintekens voor de entiteit definiëren.</span><span class="sxs-lookup"><span data-stu-id="12cea-112">Description: Allows you to define the starting characters for the entity.</span></span> <span data-ttu-id="12cea-113">Het heeft twee varianten, inclusief en uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="12cea-113">It has two variants, include and exclude.</span></span>

<span data-ttu-id="12cea-114">Als u bijvoorbeeld de getallen wilt uitsluiten die beginnen met 0500, 91, 091, 010 in een lijst als deze:</span><span class="sxs-lookup"><span data-stu-id="12cea-114">For example to exclude the numbers starting with 0500, 91, 091, 010 in a list like this:</span></span>

- <span data-ttu-id="12cea-115">0500-4500-027</span><span class="sxs-lookup"><span data-stu-id="12cea-115">0500-4500-027</span></span>
- <span data-ttu-id="12cea-116">91564721450</span><span class="sxs-lookup"><span data-stu-id="12cea-116">91564721450</span></span>
- <span data-ttu-id="12cea-117">91-8523697410</span><span class="sxs-lookup"><span data-stu-id="12cea-117">91-8523697410</span></span>
- <span data-ttu-id="12cea-118">700-8956-7844</span><span class="sxs-lookup"><span data-stu-id="12cea-118">700-8956-7844</span></span>
- <span data-ttu-id="12cea-119">1000-3265-9874</span><span class="sxs-lookup"><span data-stu-id="12cea-119">1000-3265-9874</span></span>
- <span data-ttu-id="12cea-120">0100-7892-3012</span><span class="sxs-lookup"><span data-stu-id="12cea-120">0100-7892-3012</span></span>

<span data-ttu-id="12cea-121">u kunt deze xml gebruiken</span><span class="sxs-lookup"><span data-stu-id="12cea-121">you can use this xml</span></span>

```xml
<Filters id="phone_number_filters_exc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Exclude" textProcessorId="Keyword_false_positives_sw">
</Filter>
</Filters>

  <Keyword id="Keyword_false_positives_sw">
    <Group matchStyle="string">
      <Term>0500</Term>
      <Term>91</Term>
      <Term>091</Term>
      <Term>0100</Term>
    </Group>
  </Keyword>
```
<span data-ttu-id="12cea-122">Als u bijvoorbeeld de getallen wilt opnemen die beginnen met 0500, 91, 091, 0100 in een lijst als deze:</span><span class="sxs-lookup"><span data-stu-id="12cea-122">For example, to include the numbers starting with 0500, 91, 091, 0100 in a list like this:</span></span> 

- <span data-ttu-id="12cea-123">0500-4500-027</span><span class="sxs-lookup"><span data-stu-id="12cea-123">0500-4500-027</span></span>
- <span data-ttu-id="12cea-124">91564721450</span><span class="sxs-lookup"><span data-stu-id="12cea-124">91564721450</span></span>
- <span data-ttu-id="12cea-125">91-8523697410</span><span class="sxs-lookup"><span data-stu-id="12cea-125">91-8523697410</span></span>
- <span data-ttu-id="12cea-126">700-8956-7844</span><span class="sxs-lookup"><span data-stu-id="12cea-126">700-8956-7844</span></span>
- <span data-ttu-id="12cea-127">1000-3265-9874</span><span class="sxs-lookup"><span data-stu-id="12cea-127">1000-3265-9874</span></span>
- <span data-ttu-id="12cea-128">0100-7892-3012</span><span class="sxs-lookup"><span data-stu-id="12cea-128">0100-7892-3012</span></span>

<span data-ttu-id="12cea-129">u kunt deze xml gebruiken</span><span class="sxs-lookup"><span data-stu-id="12cea-129">you can use this xml</span></span>

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-endswith"></a><span data-ttu-id="12cea-130">TextMatchFilter EndsWith</span><span class="sxs-lookup"><span data-stu-id="12cea-130">TextMatchFilter EndsWith</span></span> 

<span data-ttu-id="12cea-131">Beschrijving: Hiermee kunt u de eindtekens voor de entiteit definiëren.</span><span class="sxs-lookup"><span data-stu-id="12cea-131">Description: Allows you to define the ending characters for the entity.</span></span> 

<span data-ttu-id="12cea-132">Als u bijvoorbeeld de getallen wilt uitsluiten die eindigen met 0500.91.091, 0100 in een lijst als deze:</span><span class="sxs-lookup"><span data-stu-id="12cea-132">For example, to exclude the numbers ending with 0500,91,091, 0100 in a list like this:</span></span>

- <span data-ttu-id="12cea-133">1234567891</span><span class="sxs-lookup"><span data-stu-id="12cea-133">1234567891</span></span>
- <span data-ttu-id="12cea-134">1234-5678-0091</span><span class="sxs-lookup"><span data-stu-id="12cea-134">1234-5678-0091</span></span>
- <span data-ttu-id="12cea-135">1234.4567.7091</span><span class="sxs-lookup"><span data-stu-id="12cea-135">1234.4567.7091</span></span>
- <span data-ttu-id="12cea-136">1234-8091-4564</span><span class="sxs-lookup"><span data-stu-id="12cea-136">1234-8091-4564</span></span>

<span data-ttu-id="12cea-137">u kunt deze xml gebruiken</span><span class="sxs-lookup"><span data-stu-id="12cea-137">you can use this xml</span></span>

```xml
<Filters id="phone_number_filters_exc">
    <Filter type="TextMatchFilter" direction="EndsWith" logic="Exclude" textProcessorId="Keyword_false_positives_sw">
</Filter>

  <Keyword id="Keyword_false_positives_sw">
    <Group matchStyle="string">
      <Term>0500</Term>
      <Term>91</Term>
      <Term>091</Term>
      <Term>0100</Term>
    </Group>
  </Keyword>
```

<span data-ttu-id="12cea-138">Als u bijvoorbeeld de getallen die eindigen met 0500, 91, 091, 0100, wilt opnemen in een lijst als deze:</span><span class="sxs-lookup"><span data-stu-id="12cea-138">For example, to include the numbers ending with 0500, 91, 091, 0100, in a list like this:</span></span>

- <span data-ttu-id="12cea-139">1234567891</span><span class="sxs-lookup"><span data-stu-id="12cea-139">1234567891</span></span>
- <span data-ttu-id="12cea-140">1234-5678-0091</span><span class="sxs-lookup"><span data-stu-id="12cea-140">1234-5678-0091</span></span>
- <span data-ttu-id="12cea-141">1234.4567.7091</span><span class="sxs-lookup"><span data-stu-id="12cea-141">1234.4567.7091</span></span>
- <span data-ttu-id="12cea-142">1234-8091-4564</span><span class="sxs-lookup"><span data-stu-id="12cea-142">1234-8091-4564</span></span>

<span data-ttu-id="12cea-143">u kunt deze xml gebruiken</span><span class="sxs-lookup"><span data-stu-id="12cea-143">you can use this xml</span></span>

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction=" EndsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-full"></a><span data-ttu-id="12cea-144">TextMatchFilter Full</span><span class="sxs-lookup"><span data-stu-id="12cea-144">TextMatchFilter Full</span></span>

<span data-ttu-id="12cea-145">Beschrijving: Hiermee kunt u bepaalde overeenkomsten verbieden om te voorkomen dat deze de regel activeren.</span><span class="sxs-lookup"><span data-stu-id="12cea-145">Description: Allows you to prohibit certain matches to prevent them from triggering the rule.</span></span> <span data-ttu-id="12cea-146">Sluit bijvoorbeeld 411111111111111111111 uit in de lijst met geldige creditcardwedstrijden.</span><span class="sxs-lookup"><span data-stu-id="12cea-146">For example, exclude 4111111111111111 from the list of valid credit card matches.</span></span>

<span data-ttu-id="12cea-147">Als u bijvoorbeeld creditcardnummers zoals 41111111111111111111111 en 32418910311111 wilt uitsluiten in een lijst als deze:</span><span class="sxs-lookup"><span data-stu-id="12cea-147">For example, to exclude credit card numbers like 4111111111111111 and 3241891031113111 in a list like this:</span></span>

- <span data-ttu-id="12cea-148">4485 3647 3952 7352</span><span class="sxs-lookup"><span data-stu-id="12cea-148">4485 3647 3952 7352</span></span>
- <span data-ttu-id="12cea-149">4111111111111111</span><span class="sxs-lookup"><span data-stu-id="12cea-149">4111111111111111</span></span>
- <span data-ttu-id="12cea-150">3241891031113111</span><span class="sxs-lookup"><span data-stu-id="12cea-150">3241891031113111</span></span>

<span data-ttu-id="12cea-151">u kunt deze xml gebruiken</span><span class="sxs-lookup"><span data-stu-id="12cea-151">you can use this xml</span></span>

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Full" logic="Exclude" textProcessorId="Keyword_false_positives_full">
</Filter>

  <Keyword id="Keyword_false_positives_full">
    <Group matchStyle="string">
      <Term>4111111111111111</Term>
      <Term>3241891031113111</Term>
    </Group>
  </Keyword>
```

<span data-ttu-id="12cea-152">Als u bijvoorbeeld creditcardnummers zoals 411111111111111111111111 en 3241891031113111 wilt opnemen in een lijst als deze:</span><span class="sxs-lookup"><span data-stu-id="12cea-152">For example, to include credit card numbers like 4111111111111111 and 3241891031113111 in a list like this:</span></span>

- <span data-ttu-id="12cea-153">4485 3647 3952 7352</span><span class="sxs-lookup"><span data-stu-id="12cea-153">4485 3647 3952 7352</span></span>
- <span data-ttu-id="12cea-154">4111111111111111</span><span class="sxs-lookup"><span data-stu-id="12cea-154">4111111111111111</span></span>
- <span data-ttu-id="12cea-155">3241891031113111</span><span class="sxs-lookup"><span data-stu-id="12cea-155">3241891031113111</span></span>

<span data-ttu-id="12cea-156">u kunt deze xml gebruiken</span><span class="sxs-lookup"><span data-stu-id="12cea-156">you can use this xml</span></span>

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_false_positives_full">
</Filter>
```

### <a name="textmatchfilter-prefix"></a><span data-ttu-id="12cea-157">TextMatchFilter Voorvoegsel</span><span class="sxs-lookup"><span data-stu-id="12cea-157">TextMatchFilter Prefix</span></span>

<span data-ttu-id="12cea-158">Beschrijving: Hiermee kunt u de voorgaande tekens definiëren die altijd moeten worden opgenomen of uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="12cea-158">Description: Allows you to define the preceding characters that should be always included or excluded.</span></span> <span data-ttu-id="12cea-159">Als creditcardnummer bijvoorbeeld wordt voorafgegaan door 'Order-id:' verwijdert u de overeenkomst uit de geldige overeenkomsten.</span><span class="sxs-lookup"><span data-stu-id="12cea-159">For example, if Credit card number is preceded by ‘Order ID:’ then remove the match from the valid matches.</span></span>

<span data-ttu-id="12cea-160">Als u bijvoorbeeld telefoonnummers wilt uitsluiten  die een  Telefoon hebben en mij bellen bij tekenreeksen vóór het telefoonnummer, in een lijst als deze:</span><span class="sxs-lookup"><span data-stu-id="12cea-160">For example, to exclude occurrences of phone numbers which have **Phone number** and **call me at** strings before the phone number, in a list like this:</span></span>

- <span data-ttu-id="12cea-161">telefoonnummer 091-8974-653278</span><span class="sxs-lookup"><span data-stu-id="12cea-161">phone number 091-8974-653278</span></span>
- <span data-ttu-id="12cea-162">Telefoon 45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="12cea-162">Phone 45-124576532-123</span></span>
- <span data-ttu-id="12cea-163">45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="12cea-163">45-124576532-123</span></span>

<span data-ttu-id="12cea-164">u kunt deze xml gebruiken</span><span class="sxs-lookup"><span data-stu-id="12cea-164">you can use this xml</span></span>

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_prefix">
</Filter>
  <Keyword id="Keyword_false_positives_prefix">
    <Group matchStyle="string">
      <Term>phone number</Term>
      <Term>call me at</Term>
    </Group>
  </Keyword>
```

<span data-ttu-id="12cea-165">Als u bijvoorbeeld exemplaren  met creditcard- en **kaartnummerreeksen** vóór het creditcardnummer wilt opnemen, in een lijst als deze:</span><span class="sxs-lookup"><span data-stu-id="12cea-165">For example, to include occurrences that have **credit card** and **card #** strings before the credit card number, in a list like this:</span></span>

- <span data-ttu-id="12cea-166">Creditcard 45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="12cea-166">Credit card 45-124576532-123</span></span> 
- <span data-ttu-id="12cea-167">45-124576532-123 (mogelijk telefoonnummer)</span><span class="sxs-lookup"><span data-stu-id="12cea-167">45-124576532-123  (which could be phone number)</span></span>

<span data-ttu-id="12cea-168">u kunt deze xml gebruiken</span><span class="sxs-lookup"><span data-stu-id="12cea-168">you can use this xml</span></span>

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_true_positives_prefix">
</Filter>

  <Keyword id="Keyword_true_positives_prefix">
    <Group matchStyle="string">
      <Term>credit card</Term>
      <Term>card #</Term>
    </Group>
  </Keyword
```

### <a name="textmatchfilter-suffix"></a><span data-ttu-id="12cea-169">TextMatchFilter-achtervoegsel</span><span class="sxs-lookup"><span data-stu-id="12cea-169">TextMatchFilter Suffix</span></span>

<span data-ttu-id="12cea-170">Beschrijving: Hiermee kunt u de volgende tekens definiëren die altijd moeten worden opgenomen of uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="12cea-170">Description: Allows you to define the following characters that should be always included or excluded.</span></span> <span data-ttu-id="12cea-171">Als creditcardnummer bijvoorbeeld wordt gevolgd door '/xuid' verwijdert u de overeenkomst uit de geldige overeenkomsten.</span><span class="sxs-lookup"><span data-stu-id="12cea-171">For example, if Credit card number is followed by ‘/xuid’ then remove the match from the valid matches.</span></span>

<span data-ttu-id="12cea-172">Als er bijvoorbeeld nog vijf exemplaren van vier cijfers als achtervoegsel in een lijst als volgende voorkomen:</span><span class="sxs-lookup"><span data-stu-id="12cea-172">For example, top exclude occurrences if there are 5 more instances of four digits as suffix in a list like this:</span></span>

- <span data-ttu-id="12cea-173">1234-5678-9321 4500 9870 6321 48925566</span><span class="sxs-lookup"><span data-stu-id="12cea-173">1234-5678-9321 4500 9870 6321 48925566</span></span>
- <span data-ttu-id="12cea-174">1234-5678-9321</span><span class="sxs-lookup"><span data-stu-id="12cea-174">1234-5678-9321</span></span>

<span data-ttu-id="12cea-175">u kunt deze xml gebruiken</span><span class="sxs-lookup"><span data-stu-id="12cea-175">you can use this xml</span></span>

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Regex_false_positives_suffix">
</Filter>

  <Regexid="Regex_false_positives_suffix">(\d{4}){5,}</Regex>
```
<span data-ttu-id="12cea-176">Als u bijvoorbeeld exemplaren wilt uitsluiten als ze worden gevolgd door **/xuidsuffix,** zoals in deze lijst:</span><span class="sxs-lookup"><span data-stu-id="12cea-176">For example, to exclude occurrences if they are followed by **/xuidsuffix**, like one in this list:</span></span>

- <span data-ttu-id="12cea-177">1234-5678-9321 /xuid</span><span class="sxs-lookup"><span data-stu-id="12cea-177">1234-5678-9321 /xuid</span></span>
- <span data-ttu-id="12cea-178">1234-5678-9321</span><span class="sxs-lookup"><span data-stu-id="12cea-178">1234-5678-9321</span></span>

<span data-ttu-id="12cea-179">u kunt deze xml gebruiken</span><span class="sxs-lookup"><span data-stu-id="12cea-179">you can use this xml</span></span>

<span data-ttu-id="12cea-180">''xml <Filters id="cc_number_filters_exc"></span><span class="sxs-lookup"><span data-stu-id="12cea-180">\`\`xml <Filters id="cc_number_filters_exc"></span></span>
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_suffix">
</Filter>

  <span data-ttu-id="12cea-181"><Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      </span><span class="sxs-lookup"><span data-stu-id="12cea-181"><Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      </span></span><Term><span data-ttu-id="12cea-182">/xuid</span><span class="sxs-lookup"><span data-stu-id="12cea-182">/xuid</span></span></Term>
    <span data-ttu-id="12cea-183"></Group> </Keyword></span><span class="sxs-lookup"><span data-stu-id="12cea-183"></Group> </Keyword></span></span>
```

For example, to include an occurrence only if it is followed by **cvv** or **expires**, like two in this list:

- 45-124576532-123 
- 45-124576532-123  cvv 966
- 45-124576532-123  expires 03/23

you can use this xml

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_true_positives_suffix">
</Filter>

  <Keyword id="Keyword_true_positives_suffix">
    <Group matchStyle="string">
      <Term>cvv</Term>
      <Term>expires</Term>
    </Group>
  </Keyword>
```

## <a name="using-filters-in-rule-packages"></a><span data-ttu-id="12cea-184">Filters gebruiken in regelpakketten</span><span class="sxs-lookup"><span data-stu-id="12cea-184">Using filters in rule packages</span></span>

<span data-ttu-id="12cea-185">Filters kunnen worden gedefinieerd op de hele SIT of op een patroon.</span><span class="sxs-lookup"><span data-stu-id="12cea-185">Filters can be defined on the entire SIT or on a pattern.</span></span> <span data-ttu-id="12cea-186">Hier zijn enkele voorbeelden van codefragmenten.</span><span class="sxs-lookup"><span data-stu-id="12cea-186">Here are some code snippets examples.</span></span> 

### <a name="at-sensitive-information-type-level"></a><span data-ttu-id="12cea-187">Op het niveau van het type gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="12cea-187">At sensitive information type level</span></span>

<span data-ttu-id="12cea-188">Filters bij Entity - heeft betrekking op alle onderliggende patronen</span><span class="sxs-lookup"><span data-stu-id="12cea-188">Filters at Entity - will cover all child patterns</span></span>

<span data-ttu-id="12cea-189">De filters worden toegepast op **alle** exemplaren die zijn geclassificeerd door een van de patronen in die entiteit/ het gevoelige type</span><span class="sxs-lookup"><span data-stu-id="12cea-189">The filters will be applied on **all** the instances classified by any of the patterns in that entity / sensitive type</span></span>

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
```

### <a name="at-the-individual-pattern-of-the-sensitive-information-type-level"></a><span data-ttu-id="12cea-190">Op het afzonderlijke patroon van het niveau van het gevoelige informatietype</span><span class="sxs-lookup"><span data-stu-id="12cea-190">At the individual pattern of the sensitive information type level</span></span>

<span data-ttu-id="12cea-191">Filtert alleen op het patroonniveau.</span><span class="sxs-lookup"><span data-stu-id="12cea-191">Filters only at the pattern level.</span></span>

<span data-ttu-id="12cea-192">Het filter wordt toegepast op de exemplaren die overeenkomen met het patroon.</span><span class="sxs-lookup"><span data-stu-id="12cea-192">The filter will be applied on the instances matched by the pattern.</span></span>

```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Keyword_cc_verification" />
      </Pattern>
</Entity>
```


### <a name="at-sensitive-information-type-level-and-an-additional-filter-on-some-of-the-patterns-of-that-entity"></a><span data-ttu-id="12cea-193">Op het niveau van het type gevoelige informatie en een extra filter op een aantal patronen van die entiteit</span><span class="sxs-lookup"><span data-stu-id="12cea-193">At sensitive information type level and an additional filter on some of the patterns of that entity</span></span>

<span data-ttu-id="12cea-194">Filters bij Entity + pattern</span><span class="sxs-lookup"><span data-stu-id="12cea-194">Filters at Entity + pattern</span></span>

<span data-ttu-id="12cea-195">De filters worden toegepast op **alle** exemplaren die zijn geclassificeerd door een van de patronen in die entiteit/ het gevoelige type.</span><span class="sxs-lookup"><span data-stu-id="12cea-195">The filters will be applied on **all** the instances classified by any of the patterns in that entity / sensitive type.</span></span> <span data-ttu-id="12cea-196">Het filter op patroonniveau filtert de exemplaren die overeenkomen met dat patroon.</span><span class="sxs-lookup"><span data-stu-id="12cea-196">The pattern level filter will filter the instances matched by that pattern.</span></span>

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85" filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
``` 

 

## <a name="more-information"></a><span data-ttu-id="12cea-197">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="12cea-197">More information</span></span>

- [<span data-ttu-id="12cea-198">Meer informatie over preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="12cea-198">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="12cea-199">Definities van entiteiten van het type vertrouwelijke gegevens</span><span class="sxs-lookup"><span data-stu-id="12cea-199">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="12cea-200">Doel van de DLP-functies</span><span class="sxs-lookup"><span data-stu-id="12cea-200">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
