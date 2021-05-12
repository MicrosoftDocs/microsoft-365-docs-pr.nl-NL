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
ms.openlocfilehash: 7b24313c54fdf49876c58d1809cbb29159f4508f
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162959"
---
# <a name="customize-a-built-in-sensitive-information-type"></a>Een ingebouwd type gevoelige informatie aanpassen

Wanneer u op zoek bent naar gevoelige informatie in inhoud, moet u die informatie beschrijven in een zogenaamde  *regel*  . Preventie van gegevensverlies (DLP) bevat regels voor de meest voorkomende typen gevoelige informatie die u direct kunt gebruiken. Als u deze regels wilt gebruiken, moet u deze opnemen in een beleid. Mogelijk wilt u deze ingebouwde regels aanpassen aan de specifieke behoeften van uw organisatie. U kunt dit doen door een aangepast type gevoelige informatie te maken. In dit onderwerp ziet u hoe u het XML-bestand met de bestaande regelverzameling kunt aanpassen om een groter aantal mogelijke creditcardgegevens te detecteren. 
  
U kunt dit voorbeeld gebruiken en toepassen op andere ingebouwde typen gevoelige informatie. Zie [Entiteitsdefinities voor gevoelige informatie](sensitive-information-type-entity-definitions.md) voor een lijst met standaardtypen voor gevoelige informatie en XML-definities. 
  
## <a name="export-the-xml-file-of-the-current-rules"></a>Het XML-bestand van de huidige regels exporteren

Als u de XML wilt exporteren, moet [verbinding maken met het beveiligings- en compliancecentrum via externe PowerShell.](/powershell/exchange/connect-to-scc-powershell).
  
1. Typ in de PowerShell het volgende om de regels van uw organisatie op het scherm weer te geven. Als u uw eigen regels nog niet hebt gemaakt, ziet u alleen de ingebouwde standaardregels met het label 'Microsoft-regelpakket'.

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

2. Sla de regels van uw organisatie op in een variabele door het volgende te typen. Door iets in een variabele op te slaan, is het later gemakkelijk beschikbaar in een indeling die werkt voor externe PowerShell-opdrachten.

   ```powershell    
   $ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
   ```
    
3. Maak een opgemaakt XML-bestand met al die gegevens door het volgende te typen. (`Set-content` is het deel van de cmdlet dat de XML naar het bestand schrijft.) 

   ```powershell
   Set-Content -path C:\custompath\exportedRules.xml -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection
   ```

   > [!IMPORTANT]
   > Zorg ervoor dat u de bestandslocatie gebruikt waar uw regelpakket is opgeslagen.  `C:\custompath\` is een tijdelijke aanduiding. 
  
## <a name="find-the-rule-that-you-want-to-modify-in-the-xml"></a>De regel in de XML zoeken die u wilt wijzigen

Met de bovenstaande cmdlets is gehele *verzameling van regels*, die de standaardregels bevat die we bieden, geëxporteerd. Vervolgens moet u specifiek zoeken naar de regel met het creditcardnummer die u wilt wijzigen. 
  
1. Gebruik een teksteditor om het XML-bestand te openen dat u in de vorige sectie hebt geëxporteerd.
    
2. Schuif omlaag naar de tag `<Rules>`; deze is het begin van de sectie met de DLP-regels. Omdat dit XML-bestand de informatie voor de hele regelverzameling bevat, bevat het boven aan het bestand andere informatie waar u langs moet schuiven om naar de regels te gaan.
    
3. Zoek *Func_credit_card* om de regeldefinitie van het creditcardnummer te vinden. Regelnamen in de XML mogen geen spaties bevatten, dus worden de spaties meestal vervangen door onderstrepingstekens. Soms worden regelnamen afgekort. Een voorbeeld hiervan is de regel voor het socialezekerheidsnummer voor de Verenigde Staten, die wordt afgekort tot _SSN_. De XML-regel voor het creditcardnummer moet er uitzien als het volgende codevoorbeeld.
    
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

Nu u de regeldefinitie voor het creditcardnummer in de XML hebt gevonden, kunt u de XML van de regel aanpassen aan uw behoeften. Zie de [Woordenlijst](#term-glossary) aan het einde van dit onderwerp voor meer informatie over XML-definities.
  
## <a name="modify-the-xml-and-create-a-new-sensitive-information-type"></a>De XML wijzigen en een nieuw type gevoelige informatie maken

Eerst moet u een nieuw type gevoelige informatie maken, omdat u de standaardregels niet rechtstreeks kunt wijzigen. U kunt allerlei dingen doen met aangepaste typen gevoelige informatie. Deze worden beschreven in [Een aangepast type gevoelige informatie maken in het Beveiligings- en compliancecentrum PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md). In dit voorbeeld houden we het eenvoudig en verwijderen we alleen bevestigende gegevens en voegen we trefwoorden toe aan de regel Creditcardnummer.
  
Alle XML-regeldefinities zijn gebaseerd op de volgende algemene sjabloon. U moet de XML-definitie van het creditcardnummer in de sjabloon kopiëren en plakken en bepaalde waarden wijzigen (let op de '. . ." tijdelijke aanduidingen in het volgende voorbeeld). Upload vervolgens de gewijzigde XML als een nieuwe regel die in beleid kan worden gebruikt.
  
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

U hebt nu iets dat eruitziet als de volgende XML. Omdat regelpakketten en -regels worden geïdentificeerd door hun unieke GUID's, moet u twee GUID's genereren: een voor het regelpakket en een voor de GUID voor de regel Creditcardnummer. De GUID voor de entiteits-id in het volgende codevoorbeeld is de GUID voor onze ingebouwde regeldefinitie, die u moet vervangen door een nieuwe. Er zijn verschillende manieren om GUID's te genereren, maar u kunt het eenvoudig in PowerShell doen door **[guid]::NewGuid()** te typen. 
  
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

## <a name="remove-the-corroborative-evidence-requirement-from-a-sensitive-information-type"></a>De vereiste voor bevestigende bewijzen verwijderen uit een type gevoelige informatie

U hebt nu een nieuw type gevoelige informatie dat u kunt uploaden naar het Beveiligings- &amp; Compliancecentrum. In de volgende stap gaat u de regel specifieker maken. Pas de regel zo aan dat er alleen wordt gezocht naar een getal van 16 cijfers dat de controlesom doorstaat, maar geen aanvullende (bevestigende) bewijzen, zoals trefwoorden, vereist. Hiervoor moet u het deel van de XML verwijderen dat zoekt naar bevestigende bewijzen. Bevestigend bewijs is zeer nuttig bij het verminderen van onterecht positieven. In dit geval zijn er meestal bepaalde trefwoorden of een vervaldatum naast het creditcardnummer. Als u dat bewijs verwijdert, moet u ook aanpassen hoe zeker u bent dat u een creditcardnummer hebt gevonden door het `confidenceLevel` te verlagen, in het voorbeeld 85.
  
```xml
<Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="300"
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
      </Pattern>
    </Entity>
```

## <a name="look-for-keywords-that-are-specific-to-your-organization"></a>Trefwoorden zoeken die specifiek zijn voor uw organisatie

Het kan nodig zijn om bevestigende bewijzen te vereisen, waarbij u verschillende of aanvullende trefwoorden wilt – en misschien wilt u wijzigen waar u naar dat bewijs wilt zoeken. U kunt de `patternsProximity` aanpassen om de omvang voor bevestigende aanwijzingen rond het getal van 16 cijfers te vergroten of verkleinen. U moet een lijst met trefwoorden definiëren en hier binnen de regel naar verwijzen om uw eigen trefwoorden toe te voegen. In de volgende XML worden de trefwoorden 'zakelijke pas' en 'Contoso-pas' toegevoegd, zodat elk bericht met deze woordgroepen binnen 150 tekens van een creditcardnummer wordt geïdentificeerd als een creditcardnummer.
  
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

## <a name="upload-your-rule"></a>Uw regel uploaden

Ga als volgt te werk om uw regel te uploaden.
  
1. Sla het op als .xml-bestand met Unicode-codering. Dit is belangrijk omdat de regel niet werkt als het bestand wordt opgeslagen met een andere codering.
    
2. [Maak verbinding met het beveiligings- en compliancecentrum via externe PowerShell.](/powershell/exchange/connect-to-scc-powershell)
    
3. Typ het volgende in de PowerShell.

   ```powershell    
   New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\custompath\MyNewRulePack.xml" -Encoding Byte)
   ```
   
   > [!IMPORTANT]
   > Zorg ervoor dat u de bestandslocatie gebruikt waar uw regelpakket is opgeslagen.  `C:\custompath\` is een tijdelijke aanduiding. 
  
4. Typ Y en druk op **Enter** om uw keuze te bevestigen.

5. Controleer of de nieuwe regel is geüpload en wat de weergavenaam is door het volgende te typen:

   ```powershell
   Get-DlpSensitiveInformationType
   ```

Als u met de nieuwe regel gevoelige informatie wilt detecteren, moet u de regel toevoegen aan een DLP-beleid. Zie [DLP-beleid maken op basis van een sjabloon](create-a-dlp-policy-from-a-template.md) om te leren hoe u de regel aan een beleid kunt toevoegen.
  
## <a name="term-glossary"></a>Woordenlijst

Dit zijn de definities voor de termen die u tijdens deze procedure hebt aangetroffen.
  
|**Term**|**Definitie**|
|:-----|:-----|
|Entiteit|Entiteiten zijn typen gevoelige informatie, zoals creditcardnummers. Elke entiteit heeft een unieke GUID als ID. Als u een GUID kopieert en hier naar zoekt in de XML, vindt u de XML-regeldefinitie en alle gelokaliseerde vertalingen van die XML-regel. U kunt deze definitie ook vinden door de GUID voor de vertaling te vinden en vervolgens naar die GUID te zoeken.|
|Functies|Het XML-bestand verwijst naar `Func_credit_card`, een functie in gecompileerde code. Functies worden gebruikt om complexe reguliere expressies uit te voeren en te controleren of controlesommen overeenkomen met onze ingebouwde regels. Omdat dit in de code gebeurt, worden sommige variabelen niet weergegeven in het XML-bestand.|
|IdMatch|Dit is de id waarmee het patroon overeenkomst probeert te bereiken, zoals een creditcardnummer.|
|Trefwoordlijsten|Het XML-bestand verwijst ook naar `keyword_cc_verification` en `keyword_cc_name`. Dit zijn lijsten met trefwoorden op basis waarvan we zoeken naar overeenkomsten binnen de `patternsProximity` voor de entiteit. Deze worden momenteel niet weergegeven in de XML.|
|Patroon|Het patroon bevat de lijst met waar het gevoeligheidstype naar zoekt. Hieronder vallen trefwoorden, reguliere expressies en interne functies, waarmee taken zoals het verifiëren van controlesommen worden uitgevoerd. Typen voor gevoelige gegevens kunnen meerdere patronen met unieke betrouwbaarheden. Dit is handig bij het maken van een type gevoelige informatie dat een hoge betrouwbaarheid retourneert als bevestigende gegevens worden gevonden en een lagere betrouwbaarheid als er weinig of geen bevestigende bewijzen worden gevonden.|
|Betrouwbaarheidsniveau van het patroon|Dit is het betrouwbaarheidsniveau dat de DLP-engine een overeenkomst heeft gevonden. Dit betrouwbaarheidsniveau is gekoppeld aan een overeenkomst met het patroon als aan de vereisten van het patroon wordt voldaan. Dit is de betrouwbaarheidsmeting waar u rekening mee moet houden bij het gebruik van Exchange-regels voor e-mailstromen (ook wel transportregels genoemd).|
|patternsProximity|Als we een patroon vinden dat op een creditcardnummer lijkt, is `patternsProximity` de nabijheid van dat nummer waar we naar bevestigende bewijzen zoeken.|
|recommendedConfidence|Dit is het betrouwbaarheidsniveau dat we voor deze regel aanraden. De aanbevolen betrouwbaarheid geldt voor entiteiten en affiniteiten. Voor entiteiten wordt dit getal nooit geëvalueerd op basis van de `confidenceLevel` van het patroon. Het is slechts een suggestie om u te helpen bij het kiezen van een betrouwbaarheidsniveau als u er een wilt toepassen. Voor affiniteiten moet het `confidenceLevel` van het patroon hoger zijn dan het nummer van de `recommendedConfidence` om een actie voor een e-mailstroomregel te kunnen aanroepen. Het `recommendedConfidence` is het standaard betrouwbaarheidsniveau dat wordt gebruikt in regels voor de e-mailstroom waarmee een actie wordt aanroepen. Als u wilt, kunt u de regel voor de e-mailstroom handmatig wijzigen zodat deze wordt aangeroepen op basis van het betrouwbaarheidsniveau van het patroon.|
   
## <a name="for-more-information"></a>Voor meer informatie

- [Entiteitsdefinities voor het type gevoelige informatie](sensitive-information-type-entity-definitions.md)
- [Een aangepast type gevoelige informatie maken](create-a-custom-sensitive-information-type.md)
- [Meer informatie over preventie van gegevensverlies](dlp-learn-about-dlp.md)