---
title: Een ingebouwd type gevoelige informatie aanpassen
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Lees hoe u een aangepast type gevoelige informatie maakt waarmee u regels kunt gebruiken die voldoen aan de behoeften van uw organisatie.
ms.openlocfilehash: da79c525a268ff686c2edaf777cedf447335ed27
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227029"
---
# <a name="customize-a-built-in-sensitive-information-type"></a><span data-ttu-id="39ebd-103">Een ingebouwd type gevoelige informatie aanpassen</span><span class="sxs-lookup"><span data-stu-id="39ebd-103">Customize a built-in sensitive information type</span></span>

<span data-ttu-id="39ebd-104">Wanneer u op zoek bent naar gevoelige informatie in inhoud, moet u die informatie beschrijven in een zogenaamde  *regel*  .</span><span class="sxs-lookup"><span data-stu-id="39ebd-104">When looking for sensitive information in content, you need to describe that information in what's called a  *rule*  .</span></span> <span data-ttu-id="39ebd-105">Preventie van gegevensverlies (DLP) bevat regels voor de meest voorkomende typen gevoelige informatie die u direct kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="39ebd-105">Data loss prevention (DLP) includes rules for the most-common sensitive information types that you can use right away.</span></span> <span data-ttu-id="39ebd-106">Als u deze regels wilt gebruiken, moet u deze opnemen in een beleid.</span><span class="sxs-lookup"><span data-stu-id="39ebd-106">To use these rules, you have to include them in a policy.</span></span> <span data-ttu-id="39ebd-107">Mogelijk wilt u deze ingebouwde regels aanpassen aan de specifieke behoeften van uw organisatie. U kunt dit doen door een aangepast type gevoelige informatie te maken.</span><span class="sxs-lookup"><span data-stu-id="39ebd-107">You might find that you want to adjust these built-in rules to meet your organization's specific needs, and you can do that by creating a custom sensitive information type.</span></span> <span data-ttu-id="39ebd-108">In dit onderwerp ziet u hoe u het XML-bestand met de bestaande regelverzameling kunt aanpassen om een groter aantal mogelijke creditcardgegevens te detecteren.</span><span class="sxs-lookup"><span data-stu-id="39ebd-108">This topic shows you how to customize the XML file that contains the existing rule collection to detect a wider range of potential credit-card information.</span></span>

<span data-ttu-id="39ebd-109">U kunt dit voorbeeld gebruiken en toepassen op andere ingebouwde typen gevoelige informatie.</span><span class="sxs-lookup"><span data-stu-id="39ebd-109">You can take this example and apply it to other built-in sensitive information types.</span></span> <span data-ttu-id="39ebd-110">Zie [Entiteitsdefinities voor gevoelige informatie](sensitive-information-type-entity-definitions.md) voor een lijst met standaardtypen voor gevoelige informatie en XML-definities.</span><span class="sxs-lookup"><span data-stu-id="39ebd-110">For a list of default sensitive information types and XML definitions, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>

## <a name="export-the-xml-file-of-the-current-rules"></a><span data-ttu-id="39ebd-111">Het XML-bestand van de huidige regels exporteren</span><span class="sxs-lookup"><span data-stu-id="39ebd-111">Export the XML file of the current rules</span></span>

<span data-ttu-id="39ebd-112">Als u de XML wilt exporteren, moet [verbinding maken met het beveiligings- en compliancecentrum via externe PowerShell.](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="39ebd-112">To export the XML, you need to [connect to the Security and Compliance Center via Remote PowerShell.](/powershell/exchange/connect-to-scc-powershell).</span></span>

1. <span data-ttu-id="39ebd-113">Typ in de PowerShell het volgende om de regels van uw organisatie op het scherm weer te geven.</span><span class="sxs-lookup"><span data-stu-id="39ebd-113">In the PowerShell, type the following to display your organization's rules on screen.</span></span> <span data-ttu-id="39ebd-114">Als u uw eigen regels nog niet hebt gemaakt, ziet u alleen de ingebouwde standaardregels met het label 'Microsoft-regelpakket'.</span><span class="sxs-lookup"><span data-stu-id="39ebd-114">If you haven't created your own, you'll only see the default, built-in rules, labeled "Microsoft Rule Package."</span></span>

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

2. <span data-ttu-id="39ebd-115">Sla de regels van uw organisatie op in een variabele door het volgende te typen.</span><span class="sxs-lookup"><span data-stu-id="39ebd-115">Store your organization's rules in a variable by typing the following.</span></span> <span data-ttu-id="39ebd-116">Door iets in een variabele op te slaan, is het later gemakkelijk beschikbaar in een indeling die werkt voor externe PowerShell-opdrachten.</span><span class="sxs-lookup"><span data-stu-id="39ebd-116">Storing something in a variable makes it easily available later in a format that works for remote PowerShell commands.</span></span>

   ```powershell
   $ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
   ```

3. <span data-ttu-id="39ebd-117">Maak een opgemaakt XML-bestand met al die gegevens door het volgende te typen.</span><span class="sxs-lookup"><span data-stu-id="39ebd-117">Make a formatted XML file with all that data by typing the following.</span></span> <span data-ttu-id="39ebd-118">(`Set-content` is het deel van de cmdlet dat de XML naar het bestand schrijft.)</span><span class="sxs-lookup"><span data-stu-id="39ebd-118">(`Set-content` is the part of the cmdlet that writes the XML to the file.)</span></span>

   ```powershell
   Set-Content -path C:\custompath\exportedRules.xml -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="39ebd-119">Zorg ervoor dat u de bestandslocatie gebruikt waar uw regelpakket is opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="39ebd-119">Make sure that you use the file location where your rule pack is actually stored.</span></span> <span data-ttu-id="39ebd-120">`C:\custompath\` is een tijdelijke aanduiding.</span><span class="sxs-lookup"><span data-stu-id="39ebd-120">`C:\custompath\` is a placeholder.</span></span>

## <a name="find-the-rule-that-you-want-to-modify-in-the-xml"></a><span data-ttu-id="39ebd-121">De regel in de XML zoeken die u wilt wijzigen</span><span class="sxs-lookup"><span data-stu-id="39ebd-121">Find the rule that you want to modify in the XML</span></span>

<span data-ttu-id="39ebd-122">Met de bovenstaande cmdlets is gehele *verzameling van regels*, die de standaardregels bevat die we bieden, geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="39ebd-122">The cmdlets above exported the entire *rule collection*, which includes the default rules we provide.</span></span> <span data-ttu-id="39ebd-123">Vervolgens moet u specifiek zoeken naar de regel met het creditcardnummer die u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="39ebd-123">Next you'll need to look specifically for the Credit Card Number rule that you want to modify.</span></span>

1. <span data-ttu-id="39ebd-124">Gebruik een teksteditor om het XML-bestand te openen dat u in de vorige sectie hebt geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="39ebd-124">Use a text editor to open the XML file that you exported in the previous section.</span></span>

2. <span data-ttu-id="39ebd-125">Schuif omlaag naar de tag `<Rules>`, wat het begin van de sectie met de DLP-regels is.</span><span class="sxs-lookup"><span data-stu-id="39ebd-125">Scroll down to the `<Rules>` tag, which is the start of the section that contains the DLP rules.</span></span> <span data-ttu-id="39ebd-126">Omdat dit XML-bestand de informatie voor de hele regelverzameling bevat, bevat het boven aan het bestand andere informatie waar u langs moet schuiven om naar de regels te gaan.</span><span class="sxs-lookup"><span data-stu-id="39ebd-126">Because this XML file contains the information for the entire rule collection, it contains other information at the top that you need to scroll past to get to the rules.</span></span>

3. <span data-ttu-id="39ebd-127">Zoek *Func_credit_card* om de regeldefinitie van het creditcardnummer te vinden.</span><span class="sxs-lookup"><span data-stu-id="39ebd-127">Look for *Func_credit_card* to find the Credit Card Number rule definition.</span></span> <span data-ttu-id="39ebd-128">Regelnamen in de XML mogen geen spaties bevatten, dus worden de spaties meestal vervangen door onderstrepingstekens. Soms worden regelnamen afgekort.</span><span class="sxs-lookup"><span data-stu-id="39ebd-128">In the XML, rule names can't contain spaces, so the spaces are usually replaced with underscores, and rule names are sometimes abbreviated.</span></span> <span data-ttu-id="39ebd-129">Een voorbeeld hiervan is de regel voor het socialezekerheidsnummer voor de Verenigde Staten, die wordt afgekort tot _SSN_.</span><span class="sxs-lookup"><span data-stu-id="39ebd-129">An example of this is the U.S. Social Security number rule, which is abbreviated _SSN_.</span></span> <span data-ttu-id="39ebd-130">De XML-regel voor het creditcardnummer moet er uitzien als het volgende codevoorbeeld.</span><span class="sxs-lookup"><span data-stu-id="39ebd-130">The Credit Card Number rule XML should look like the following code sample.</span></span>

   ```xml
   <Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085"
          patternsProximity="300" recommendedConfidence="85">
         <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_credit_card" />
           <Any minMatches="1">
             <Match idRef="Keyword_cc_verification" />
             <Match idRef="Keyword_cc_name" />
             <Match idRef="Func_expiration_date" />
           </Any>
         </Pattern>
       </Entity>
   ```

<span data-ttu-id="39ebd-131">Nu u de regeldefinitie voor het creditcardnummer in de XML hebt gevonden, kunt u de XML van de regel aanpassen aan uw behoeften.</span><span class="sxs-lookup"><span data-stu-id="39ebd-131">Now that you have located the Credit Card Number rule definition in the XML, you can customize the rule's XML to meet your needs.</span></span> <span data-ttu-id="39ebd-132">Zie de [Woordenlijst](#term-glossary) aan het einde van dit onderwerp voor meer informatie over XML-definities.</span><span class="sxs-lookup"><span data-stu-id="39ebd-132">For a refresher on the XML definitions, see the [Term glossary](#term-glossary) at the end of this topic.</span></span>

## <a name="modify-the-xml-and-create-a-new-sensitive-information-type"></a><span data-ttu-id="39ebd-133">De XML wijzigen en een nieuw type gevoelige informatie maken</span><span class="sxs-lookup"><span data-stu-id="39ebd-133">Modify the XML and create a new sensitive information type</span></span>

<span data-ttu-id="39ebd-134">Eerst moet u een nieuw type gevoelige informatie maken, omdat u de standaardregels niet rechtstreeks kunt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="39ebd-134">First, you need to create a new sensitive information type because you can't directly modify the default rules.</span></span> <span data-ttu-id="39ebd-135">U kunt allerlei dingen doen met aangepaste typen gevoelige informatie. Deze worden beschreven in [Een aangepast type gevoelige informatie maken in het Beveiligings- en compliancecentrum PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="39ebd-135">You can do a wide variety of things with custom sensitive information types, which are outlined in [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="39ebd-136">In dit voorbeeld houden we het eenvoudig en verwijderen we alleen bevestigende gegevens en voegen we trefwoorden toe aan de regel Creditcardnummer.</span><span class="sxs-lookup"><span data-stu-id="39ebd-136">For this example, we'll keep it simple and only remove corroborative evidence and add keywords to the Credit Card Number rule.</span></span>

<span data-ttu-id="39ebd-137">Alle XML-regeldefinities zijn gebaseerd op de volgende algemene sjabloon.</span><span class="sxs-lookup"><span data-stu-id="39ebd-137">All XML rule definitions are built on the following general template.</span></span> <span data-ttu-id="39ebd-138">U moet de XML-definitie van het creditcardnummer in de sjabloon kopiëren en plakken en bepaalde waarden wijzigen (let op de '.</span><span class="sxs-lookup"><span data-stu-id="39ebd-138">You need to copy and paste the Credit Card Number definition XML in the template, modify some values (notice the ".</span></span> <span data-ttu-id="39ebd-139">.</span><span class="sxs-lookup"><span data-stu-id="39ebd-139">.</span></span> <span data-ttu-id="39ebd-140">."</span><span class="sxs-lookup"><span data-stu-id="39ebd-140">."</span></span> <span data-ttu-id="39ebd-141">tijdelijke aanduidingen in het volgende voorbeeld). Upload vervolgens de gewijzigde XML als een nieuwe regel die in beleid kan worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="39ebd-141">placeholders in the following example), and then upload the modified XML as a new rule that can be used in policies.</span></span>

```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce">
  <RulePack id=". . .">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id=". . ." />
    <Details defaultLangCode=". . .">
      <LocalizedDetails langcode=" . . . ">
         <PublisherName>. . .</PublisherName>
         <Name>. . .</Name>
         <Description>. . .</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>

 <Rules>
   <!-- Paste the Credit Card Number rule definition here.-->
      <LocalizedStrings>
         <Resource idRef=". . .">
           <Name default="true" langcode=" . . . ">. . .</Name>
           <Description default="true" langcode=". . ."> . . .</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

<span data-ttu-id="39ebd-142">U hebt nu iets dat eruitziet als de volgende XML.</span><span class="sxs-lookup"><span data-stu-id="39ebd-142">Now, you have something that looks similar to the following XML.</span></span> <span data-ttu-id="39ebd-143">Omdat regelpakketten en -regels worden geïdentificeerd door hun unieke GUID's, moet u twee GUID's genereren: een voor het regelpakket en een voor de GUID voor de regel Creditcardnummer.</span><span class="sxs-lookup"><span data-stu-id="39ebd-143">Because rule packages and rules are identified by their unique GUIDs, you need to generate two GUIDs: one for the rule package and one to replace the GUID for the Credit Card Number rule.</span></span> <span data-ttu-id="39ebd-144">De GUID voor de entiteits-id in het volgende codevoorbeeld is de GUID voor onze ingebouwde regeldefinitie, die u moet vervangen door een nieuwe.</span><span class="sxs-lookup"><span data-stu-id="39ebd-144">The GUID for the entity ID in the following code sample is the one for our built-in rule definition, which you need to replace with a new one.</span></span> <span data-ttu-id="39ebd-145">Er zijn verschillende manieren om GUID's te genereren, maar u kunt het eenvoudig in PowerShell doen door **[guid]::NewGuid()** te typen.</span><span class="sxs-lookup"><span data-stu-id="39ebd-145">There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing **[guid]::NewGuid()**.</span></span>

```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce">
  <RulePack id="8aac8390-e99f-4487-8d16-7f0cdee8defc">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id="8d34806e-cd65-4178-ba0e-5d7d712e5b66" />
    <Details defaultLangCode="en">
      <LocalizedDetails langcode="en">
        <PublisherName>Contoso Ltd.</PublisherName>
        <Name>Financial Information</Name>
        <Description>Modified versions of the Microsoft rule package</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>

 <Rules>
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f"
       patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
      <LocalizedStrings>
         <Resource idRef="db80b3da-0056-436e-b0ca-1f4cf7080d1f">
<!-- This is the GUID for the preceding Credit Card Number entity because the following text is for that Entity. -->
           <Name default="true" langcode="en-us">Modified Credit Card Number</Name>
           <Description default="true" langcode="en-us">Credit Card Number that looks for additional keywords, and another version of Credit Card Number that doesn't require keywords (but has a lower confidence level)</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

## <a name="remove-the-corroborative-evidence-requirement-from-a-sensitive-information-type"></a><span data-ttu-id="39ebd-146">De vereiste voor bevestigende bewijzen verwijderen uit een type gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="39ebd-146">Remove the corroborative evidence requirement from a sensitive information type</span></span>

<span data-ttu-id="39ebd-147">U hebt nu een nieuw type gevoelige informatie dat u kunt uploaden naar het Beveiligings- &amp; Compliancecentrum. In de volgende stap gaat u de regel specifieker maken.</span><span class="sxs-lookup"><span data-stu-id="39ebd-147">Now that you have a new sensitive information type that you're able to upload to the Security &amp; Compliance Center, the next step is to make the rule more specific.</span></span> <span data-ttu-id="39ebd-148">Pas de regel zo aan dat er alleen wordt gezocht naar een getal van 16 cijfers dat de controlesom doorstaat, maar geen aanvullende (bevestigende) bewijzen, zoals trefwoorden, vereist.</span><span class="sxs-lookup"><span data-stu-id="39ebd-148">Modify the rule so that it only looks for a 16-digit number that passes the checksum but doesn't require additional (corroborative) evidence, like keywords.</span></span> <span data-ttu-id="39ebd-149">Hiervoor moet u het deel van de XML verwijderen dat zoekt naar bevestigende bewijzen.</span><span class="sxs-lookup"><span data-stu-id="39ebd-149">To do this, you need to remove the part of the XML that looks for corroborative evidence.</span></span> <span data-ttu-id="39ebd-150">Bevestigend bewijs is zeer nuttig bij het verminderen van onterecht positieven.</span><span class="sxs-lookup"><span data-stu-id="39ebd-150">Corroborative evidence is very helpful in reducing false positives.</span></span> <span data-ttu-id="39ebd-151">In dit geval zijn er meestal bepaalde trefwoorden of een vervaldatum naast het creditcardnummer.</span><span class="sxs-lookup"><span data-stu-id="39ebd-151">In this case there are usually certain keywords or an expiration date near the credit card number.</span></span> <span data-ttu-id="39ebd-152">Als u dat bewijs verwijdert, moet u ook aanpassen hoe zeker u bent dat u een creditcardnummer hebt gevonden door het `confidenceLevel` te verlagen, in het voorbeeld 85.</span><span class="sxs-lookup"><span data-stu-id="39ebd-152">If you remove that evidence, you should also adjust how confident you are that you found a credit card number by lowering the  `confidenceLevel`, which is 85 in the example.</span></span>

```xml
<Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="300"
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
      </Pattern>
    </Entity>
```

## <a name="look-for-keywords-that-are-specific-to-your-organization"></a><span data-ttu-id="39ebd-153">Trefwoorden zoeken die specifiek zijn voor uw organisatie</span><span class="sxs-lookup"><span data-stu-id="39ebd-153">Look for keywords that are specific to your organization</span></span>

<span data-ttu-id="39ebd-154">Het kan nodig zijn om bevestigende bewijzen te vereisen, waarbij u verschillende of aanvullende trefwoorden wilt – en misschien wilt u wijzigen waar u naar dat bewijs wilt zoeken.</span><span class="sxs-lookup"><span data-stu-id="39ebd-154">You might want to require corroborative evidence but want different or additional keywords, and perhaps you want to change where to look for that evidence.</span></span> <span data-ttu-id="39ebd-155">U kunt de `patternsProximity` aanpassen om de omvang voor bevestigende aanwijzingen rond het getal van 16 cijfers te vergroten of verkleinen.</span><span class="sxs-lookup"><span data-stu-id="39ebd-155">You can adjust the  `patternsProximity` to expand or shrink the window for corroborative evidence around the 16-digit number.</span></span> <span data-ttu-id="39ebd-156">U moet een lijst met trefwoorden definiëren en hier binnen de regel naar verwijzen om uw eigen trefwoorden toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="39ebd-156">To add your own keywords, you need to define a keyword list and reference it within your rule.</span></span> <span data-ttu-id="39ebd-157">In de volgende XML worden de trefwoorden 'zakelijke pas' en 'Contoso-pas' toegevoegd, zodat elk bericht met deze woordgroepen binnen 150 tekens van een creditcardnummer wordt geïdentificeerd als een creditcardnummer.</span><span class="sxs-lookup"><span data-stu-id="39ebd-157">The following XML adds the keywords "company card" and "Contoso card" so that any message that contains those phrases within 150 characters of a credit card number will be identified as a credit card number.</span></span>

```xml
<Rules>
<! -- Modify the patternsProximity to be "150" rather than "300." -->
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="150" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
<!-- Add the following XML, which references the keywords at the end of the XML sample. -->
          <Match idRef="My_Additional_Keywords" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
<!-- Add the following XML, and update the information inside the <Term> tags with the keywords that you want to detect. -->
    <Keyword id="My_Additional_Keywords">
      <Group matchStyle="word">
        <Term caseSensitive="false">company card</Term>
        <Term caseSensitive="false">Contoso card</Term>
      </Group>
    </Keyword>
```

## <a name="upload-your-rule"></a><span data-ttu-id="39ebd-158">Uw regel uploaden</span><span class="sxs-lookup"><span data-stu-id="39ebd-158">Upload your rule</span></span>

<span data-ttu-id="39ebd-159">Ga als volgt te werk om uw regel te uploaden.</span><span class="sxs-lookup"><span data-stu-id="39ebd-159">To upload your rule, you need to do the following.</span></span>

1. <span data-ttu-id="39ebd-160">Sla het op als .xml-bestand met Unicode-codering.</span><span class="sxs-lookup"><span data-stu-id="39ebd-160">Save it as an .xml file with Unicode encoding.</span></span> <span data-ttu-id="39ebd-161">Dit is belangrijk omdat de regel niet werkt als het bestand wordt opgeslagen met een andere codering.</span><span class="sxs-lookup"><span data-stu-id="39ebd-161">This is important because the rule won't work if the file is saved with a different encoding.</span></span>

2. [<span data-ttu-id="39ebd-162">Maak verbinding met het beveiligings- en compliancecentrum via externe PowerShell.</span><span class="sxs-lookup"><span data-stu-id="39ebd-162">Connect to the Security and Compliance Center via Remote PowerShell.</span></span>](/powershell/exchange/connect-to-scc-powershell)

3. <span data-ttu-id="39ebd-163">Typ het volgende in de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="39ebd-163">In the PowerShell, type the following.</span></span>

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\custompath\MyNewRulePack.xml" -Encoding Byte)
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="39ebd-164">Zorg ervoor dat u de bestandslocatie gebruikt waar uw regelpakket is opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="39ebd-164">Make sure that you use the file location where your rule pack is actually stored.</span></span>  <span data-ttu-id="39ebd-165">`C:\custompath\` is een tijdelijke aanduiding.</span><span class="sxs-lookup"><span data-stu-id="39ebd-165">`C:\custompath\` is a placeholder.</span></span>

4. <span data-ttu-id="39ebd-166">Typ Y en druk op **Enter** om uw keuze te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="39ebd-166">To confirm, type Y, and then press **Enter**.</span></span>

5. <span data-ttu-id="39ebd-167">Controleer of de nieuwe regel is geüpload en wat de weergavenaam is door het volgende te typen:</span><span class="sxs-lookup"><span data-stu-id="39ebd-167">Verify that your new rule was uploaded and its display name by typing:</span></span>

   ```powershell
   Get-DlpSensitiveInformationType
   ```

<span data-ttu-id="39ebd-168">Als u met de nieuwe regel gevoelige informatie wilt detecteren, moet u de regel toevoegen aan een DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="39ebd-168">To start using the new rule to detect sensitive information, you need to add the rule to a DLP policy.</span></span> <span data-ttu-id="39ebd-169">Zie [DLP-beleid maken op basis van een sjabloon](create-a-dlp-policy-from-a-template.md) om te leren hoe u de regel aan een beleid kunt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="39ebd-169">To learn how to add the rule to a policy, see [Create a DLP policy from a template](create-a-dlp-policy-from-a-template.md).</span></span>

## <a name="term-glossary"></a><span data-ttu-id="39ebd-170">Woordenlijst</span><span class="sxs-lookup"><span data-stu-id="39ebd-170">Term glossary</span></span>

<span data-ttu-id="39ebd-171">Dit zijn de definities voor de termen die u tijdens deze procedure hebt aangetroffen.</span><span class="sxs-lookup"><span data-stu-id="39ebd-171">These are the definitions for the terms you encountered during this procedure.</span></span>

|<span data-ttu-id="39ebd-172">**Term**</span><span class="sxs-lookup"><span data-stu-id="39ebd-172">**Term**</span></span>|<span data-ttu-id="39ebd-173">**Definitie**</span><span class="sxs-lookup"><span data-stu-id="39ebd-173">**Definition**</span></span>|
|:-----|:-----|
|<span data-ttu-id="39ebd-174">Entiteit</span><span class="sxs-lookup"><span data-stu-id="39ebd-174">Entity</span></span>|<span data-ttu-id="39ebd-175">Entiteiten zijn typen gevoelige informatie, zoals creditcardnummers.</span><span class="sxs-lookup"><span data-stu-id="39ebd-175">Entities are what we call sensitive information types, such as credit card numbers.</span></span> <span data-ttu-id="39ebd-176">Elke entiteit heeft een unieke GUID als ID.</span><span class="sxs-lookup"><span data-stu-id="39ebd-176">Each entity has a unique GUID as its ID.</span></span> <span data-ttu-id="39ebd-177">Als u een GUID kopieert en hier naar zoekt in de XML, vindt u de XML-regeldefinitie en alle gelokaliseerde vertalingen van die XML-regel.</span><span class="sxs-lookup"><span data-stu-id="39ebd-177">If you copy a GUID and search for it in the XML, you'll find the XML rule definition and all the localized translations of that XML rule.</span></span> <span data-ttu-id="39ebd-178">U kunt deze definitie ook vinden door de GUID voor de vertaling te vinden en vervolgens naar die GUID te zoeken.</span><span class="sxs-lookup"><span data-stu-id="39ebd-178">You can also find this definition by locating the GUID for the translation and then searching for that GUID.</span></span>|
|<span data-ttu-id="39ebd-179">Functies</span><span class="sxs-lookup"><span data-stu-id="39ebd-179">Functions</span></span>|<span data-ttu-id="39ebd-180">Het XML-bestand verwijst naar `Func_credit_card`, een functie in gecompileerde code.</span><span class="sxs-lookup"><span data-stu-id="39ebd-180">The XML file references  `Func_credit_card`, which is a function in compiled code.</span></span> <span data-ttu-id="39ebd-181">Functies worden gebruikt om complexe reguliere expressies uit te voeren en te controleren of controlesommen overeenkomen met onze ingebouwde regels. Omdat dit in de code gebeurt, worden sommige variabelen niet weergegeven in het XML-bestand.</span><span class="sxs-lookup"><span data-stu-id="39ebd-181">Functions are used to run complex regexes and verify that checksums match for our built-in rules.) Because this happens in the code, some of the variables don't appear in the XML file.</span></span>|
|<span data-ttu-id="39ebd-182">IdMatch</span><span class="sxs-lookup"><span data-stu-id="39ebd-182">IdMatch</span></span>|<span data-ttu-id="39ebd-183">Dit is de id waarmee het patroon overeenkomst probeert te bereiken, zoals een creditcardnummer.</span><span class="sxs-lookup"><span data-stu-id="39ebd-183">This is the identifier that the pattern is to trying to match—for example, a credit card number.</span></span>|
|<span data-ttu-id="39ebd-184">Trefwoordlijsten</span><span class="sxs-lookup"><span data-stu-id="39ebd-184">Keyword lists</span></span>|<span data-ttu-id="39ebd-185">Het XML-bestand verwijst ook naar `keyword_cc_verification` en `keyword_cc_name`. Dit zijn lijsten met trefwoorden op basis waarvan we zoeken naar overeenkomsten binnen de `patternsProximity` voor de entiteit.</span><span class="sxs-lookup"><span data-stu-id="39ebd-185">The XML file also references  `keyword_cc_verification` and  `keyword_cc_name`, which are lists of keywords from which we are looking for matches within the  `patternsProximity` for the entity.</span></span> <span data-ttu-id="39ebd-186">Deze worden momenteel niet weergegeven in de XML.</span><span class="sxs-lookup"><span data-stu-id="39ebd-186">These aren't currently displayed in the XML.</span></span>|
|<span data-ttu-id="39ebd-187">Patroon</span><span class="sxs-lookup"><span data-stu-id="39ebd-187">Pattern</span></span>|<span data-ttu-id="39ebd-188">Het patroon bevat de lijst met waar het gevoeligheidstype naar zoekt.</span><span class="sxs-lookup"><span data-stu-id="39ebd-188">The pattern contains the list of what the sensitive type is looking for.</span></span> <span data-ttu-id="39ebd-189">Hieronder vallen trefwoorden, reguliere expressies en interne functies, waarmee taken zoals het verifiëren van controlesommen worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="39ebd-189">This includes keywords, regexes, and internal functions, which perform tasks like verifying checksums.</span></span> <span data-ttu-id="39ebd-190">Typen voor gevoelige gegevens kunnen meerdere patronen met unieke betrouwbaarheden.</span><span class="sxs-lookup"><span data-stu-id="39ebd-190">Sensitive information types can have multiple patterns with unique confidences.</span></span> <span data-ttu-id="39ebd-191">Dit is handig bij het maken van een type gevoelige informatie dat een hoge betrouwbaarheid retourneert als bevestigende gegevens worden gevonden en een lagere betrouwbaarheid als er weinig of geen bevestigende bewijzen worden gevonden.</span><span class="sxs-lookup"><span data-stu-id="39ebd-191">This is useful when creating a sensitive information type that returns a high confidence if corroborative evidence is found and a lower confidence if little or no corroborative evidence is found.</span></span>|
|<span data-ttu-id="39ebd-192">Betrouwbaarheidsniveau van het patroon</span><span class="sxs-lookup"><span data-stu-id="39ebd-192">Pattern confidenceLevel</span></span>|<span data-ttu-id="39ebd-193">Dit is het betrouwbaarheidsniveau dat de DLP-engine een overeenkomst heeft gevonden.</span><span class="sxs-lookup"><span data-stu-id="39ebd-193">This is the level of confidence that the DLP engine found a match.</span></span> <span data-ttu-id="39ebd-194">Dit betrouwbaarheidsniveau is gekoppeld aan een overeenkomst met het patroon als aan de vereisten van het patroon wordt voldaan.</span><span class="sxs-lookup"><span data-stu-id="39ebd-194">This level of confidence is associated with a match for the pattern if the pattern's requirements are met.</span></span> <span data-ttu-id="39ebd-195">Dit is de betrouwbaarheidsmeting waar u rekening mee moet houden bij het gebruik van Exchange-regels voor e-mailstromen (ook wel transportregels genoemd).</span><span class="sxs-lookup"><span data-stu-id="39ebd-195">This is the confidence measure you should consider when using Exchange mail flow rules (also known as transport rules).</span></span>|
|<span data-ttu-id="39ebd-196">patternsProximity</span><span class="sxs-lookup"><span data-stu-id="39ebd-196">patternsProximity</span></span>|<span data-ttu-id="39ebd-197">Als we een patroon vinden dat op een creditcardnummer lijkt, is `patternsProximity` de nabijheid van dat nummer waar we naar bevestigende bewijzen zoeken.</span><span class="sxs-lookup"><span data-stu-id="39ebd-197">When we find what looks like a credit card number pattern,  `patternsProximity` is the proximity around that number where we'll look for corroborative evidence.</span></span>|
|<span data-ttu-id="39ebd-198">recommendedConfidence</span><span class="sxs-lookup"><span data-stu-id="39ebd-198">recommendedConfidence</span></span>|<span data-ttu-id="39ebd-199">Dit is het betrouwbaarheidsniveau dat we voor deze regel aanraden.</span><span class="sxs-lookup"><span data-stu-id="39ebd-199">This is the confidence level we recommend for this rule.</span></span> <span data-ttu-id="39ebd-200">De aanbevolen betrouwbaarheid geldt voor entiteiten en affiniteiten.</span><span class="sxs-lookup"><span data-stu-id="39ebd-200">The recommended confidence applies to entities and affinities.</span></span> <span data-ttu-id="39ebd-201">Voor entiteiten wordt dit getal nooit geëvalueerd op basis van de `confidenceLevel` van het patroon.</span><span class="sxs-lookup"><span data-stu-id="39ebd-201">For entities, this number is never evaluated against the  `confidenceLevel` for the pattern.</span></span> <span data-ttu-id="39ebd-202">Het is slechts een suggestie om u te helpen bij het kiezen van een betrouwbaarheidsniveau als u er een wilt toepassen.</span><span class="sxs-lookup"><span data-stu-id="39ebd-202">It's merely a suggestion to help you choose a confidence level if you want to apply one.</span></span> <span data-ttu-id="39ebd-203">Voor affiniteiten moet het `confidenceLevel` van het patroon hoger zijn dan het nummer van de `recommendedConfidence` om een actie voor een e-mailstroomregel te kunnen aanroepen.</span><span class="sxs-lookup"><span data-stu-id="39ebd-203">For affinities, the  `confidenceLevel` of the pattern must be higher than the  `recommendedConfidence` number for a mail flow rule action to be invoked.</span></span> <span data-ttu-id="39ebd-204">Het `recommendedConfidence` is het standaard betrouwbaarheidsniveau dat wordt gebruikt in regels voor de e-mailstroom waarmee een actie wordt aanroepen.</span><span class="sxs-lookup"><span data-stu-id="39ebd-204">The  `recommendedConfidence` is the default confidence level used in mail flow rules that invokes an action.</span></span> <span data-ttu-id="39ebd-205">Als u wilt, kunt u de regel voor de e-mailstroom handmatig wijzigen zodat deze wordt aangeroepen op basis van het betrouwbaarheidsniveau van het patroon.</span><span class="sxs-lookup"><span data-stu-id="39ebd-205">If you want, you can manually change the mail flow rule to be invoked based off the pattern's confidence level, instead.</span></span>|

## <a name="for-more-information"></a><span data-ttu-id="39ebd-206">Voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="39ebd-206">For more information</span></span>

- [<span data-ttu-id="39ebd-207">Entiteitsdefinities voor het type gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="39ebd-207">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="39ebd-208">Een aangepast type gevoelige informatie maken</span><span class="sxs-lookup"><span data-stu-id="39ebd-208">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
- [<span data-ttu-id="39ebd-209">Meer informatie over preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="39ebd-209">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)