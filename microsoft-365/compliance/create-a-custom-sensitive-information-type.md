---
title: Aan de slag met aangepaste typen vertrouwelijke informatie
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
description: Informatie over het maken, wijzigen, verwijderen en testen van aangepaste gevoelige informatietypen voor DLP in het Beveiligings- & Compliancecentrum.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0f65ba38c75cc1d9886cb4c3013d7f707912f72a
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300391"
---
# <a name="get-started-with-custom-sensitive-information-types"></a>Aan de slag met aangepaste typen vertrouwelijke informatie

Als de vooraf geconfigureerde typen gevoelige informatie niet aan uw behoeften voldoen, kunt u uw eigen aangepaste typen gevoelige informatie maken die u volledig definieert of u kunt een van de vooraf geconfigureerde typen kopiëren en wijzigen.

De aangepaste typen vertrouwelijke informatie die u met deze methode maakt, worden toegevoegd aan het regelpakket met de naam `Microsoft.SCCManaged.CustomRulePack`.

Er zijn twee manieren om een nieuw type gevoelige informatie te maken:

- [waarbij u alle elementen volledig definieert](#create-a-custom-sensitive-information-type)
- [een bestaand type vertrouwelijke informatie kopiëren en wijzigen](#copy-and-modify-a-sensitive-information-type)


## <a name="before-you-begin"></a>Voordat u begint

- U moet bekend zijn met typen vertrouwelijke informatie en waar ze uit bestaan. Zie [Meer informatie over typen gevoelige informatie](sensitive-information-type-learn-about.md). Het is essentieel dat u inzicht heeft in de rollen van:
    - [reguliere expressies](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/) - Microsoft 365-typen gevoelige informatie gebruikt de engine Boost.RegEx 5.1.3
    - trefwoordlijsten: u kunt uw eigen lijst maken terwijl u het type gevoelige informatie definieert of een keuze maken uit bestaande trefwoordlijsten
    - [Trefwoordenlijst](create-a-keyword-dictionary.md)
    - [functies](what-the-dlp-functions-look-for.md)
    - [betrouwbaarheidsniveaus](sensitive-information-type-learn-about.md#more-on-confidence-levels)
 
- U moet globale beheerdersmachtigingen of beheerdersmachtigingen voor compliance hebben om een aangepast type gevoelige informatie te maken, testen en implementeren via de gebruikersinterface. Zie [Over beheerdersrollen](/office365/admin/add-users/about-admin-roles) in Office 365.

- Uw organisatie moet een abonnement hebben, zoals Office 365 Enterprise, dat preventie van gegevensverlies (DLP) omvat. Zie [berichtenbeleid en nalevingsservicedescription](/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc). 


> [!IMPORTANT]
> Microsoft Klantenservice & Ondersteuning kan u niet helpen bij het maken van aangepaste classificaties of reguliere expressiepatronen. Ondersteunings technici kunnen beperkte ondersteuning bieden voor de functie, zoals het aanbieden van voorbeelden van reguliere expressiepatronen voor testdoeleinden of het oplossen van het oplossen van problemen met een bestaand standaardexpressiepatroon dat niet zoals verwacht wordt uitgevoerd, maar dat niet kan garanderen dat aangepaste ontwikkeling van inhoudsaanpassing voldoet aan uw vereisten of verplichtingen.

## <a name="create-a-custom-sensitive-information-type"></a>Een aangepast type gevoelige informatie maken

Gebruik deze procedure om een nieuw type gevoelige informatie te maken dat u volledig definieert. 

1. Ga in het Compliancecentrum naar **Classificatie van gegevens** \> **Gevoelige informatietypen** en kies **Gegevenstype**.
2. Vul waarden in voor **Naam** en **Beschrijving** in en kies **Volgende**.
3. Kies **Patroon maken**. U kunt meerdere patronen maken, elk met verschillende elementen en betrouwbaarheidsniveaus, terwijl u het nieuwe type gevoelige informatie definieert.
4. Kies het standaard betrouwbaarheidsniveau voor het patroon. De waarden zijn **Lage betrouwbaarheid**, **Gemiddelde betrouwbaarheid** en **Hoge betrouwbaarheid**.
5. Kies en definieer **Primaire element**. Het primaire element kan een **Reguliere expressie** met een optionele validator, een **Lijst met trefwoorden**, een **Trefwoordenlijst** of een van de vooraf geconfigureerde **Functies**. Zie [Doel van de DLP-functies](what-the-dlp-functions-look-for.md) voor meer informatie over DLP-functies. Zie Meer informatie over validators voor reguliere expressies voor meer informatie over de datum en de checksum [validators.](#more-information-on-regular-expression-validators)
6. Vul een waarde in voor **Nabijheid van tekens**.
7. (Optioneel) Voeg zo nodig ondersteunende elementen toe. Het primaire element kan een Reguliere expressie met een optionele validator, een Lijst met trefwoorden, een Trefwoordenlijst of een van de vooraf geconfigureerde Functies. Ondersteunende elementen kunnen een eigen karakter **naderingsconfiguratie** hebben. 
8. (Optioneel) Voeg alle [**aanvullende controles toe die**](#more-information-on-additional-checks) worden weergegeven in de lijst met beschikbare controles.
9. Kies **Maken**.
10. Kies **Volgende**.
11. Kies de **aanbevolen betrouwbaarheidsniveau** dit type gevoelige informatie.
12. Controleer uw instellingen en kies **Verzenden**.

> [!IMPORTANT]
> Microsoft 365 gebruikt de zoekverkenner om vertrouwelijke gegevens te identificeren en te classificeren in SHarePoint Online en OneDrive voor Bedrijven. Maar om uw nieuwe aangepaste type vertrouwelijke gegevens te identificeren in alle bestaande inhoud, moet die inhoud opnieuw worden verkend. Inhoud wordt verkend op basis van een planning, maar u kunt inhoud voor een siteverzameling, lijst of bibliotheek handmatig opnieuw crawlen. Zie voor meer informatie [Het verkennen en opnieuw indexeren van een site, bibliotheek of lijst handmatig aanvragen](/sharepoint/crawl-site-content).

13. Op de pagina **Gegevensclassificatie** worden alle typen gevoelige informatie weergegeven. Kies **Vernieuwen** en blader naar het zoekhulpmiddel of gebruik het zoekprogramma om het type gevoelige informatie te zoeken dat u hebt gemaakt.

## <a name="test-a-sensitive-information-type"></a>Een gevoelig informatietype maken

U kunt elk type gevoelige informatie in de lijst testen. Het is aan te raden elk type gevoelige informatie dat u maakt te testen voordat u het in een beleid gebruikt.

1. Maak twee bestanden, zoals een Word-document. Een met inhoud die overeenkomt met de elementen die u hebt opgegeven in uw type gevoelige informatie en een die niet overeenkomt.
2. Ga in het Compliancecentrum naar **Gegevensclassificatie** \> **Gevoelige informatietypen** en kies het type gevoelige informatie in de lijst om het detailvenster te openen en kies **Testen**.
3. Upload een bestand en kies **Testen**.
4. Bekijk de resultaten op de pagina **Overeenkomsten resultaten** en kies **Voltooien**.

## <a name="modify-custom-sensitive-information-types-in-the-compliance-center"></a>Een aangepast type gevoelige informatie wijzigen in het compliancecentrum

1. Ga in het Compliancecentrum naar **Gegevensclassificatie** \> **Gevoelige informatietypen** en kies het type gevoelige informatie die u wilt wijzigen en kies **Bewerken**.
2. U kunt andere patronen toevoegen, met unieke primaire en ondersteunende elementen, betrouwbaarheidsniveaus, nabijheid van tekens en [**Extra controles**](#more-information-on-additional-checks) de bestaande te bewerken of te verwijderen.

## <a name="remove-custom-sensitive-information-types-in-the-compliance-center"></a>Een aangepast type gevoelige informatie verwijderen in het compliancecentrum 

> [!NOTE]
> U kunt enkel aangepaste typen gevoelige informatie verwijderen: u kunt ingebouwde typen gevoelige informatie niet verwijderen.

> [!IMPORTANT]
> Controleer voordat u een aangepast type vertrouwelijke gegevens verwijdert dat er geen DLP-beleid of Exchange-berichtenstroomregels (ook wel transportregels genoemd) meer verwijzen naar het type vertrouwelijke gegevens.

1. Ga in het Compliancecentrum naar **Gegevensclassificatie** \> **Gevoelige informatietypen** en kies het type gevoelige informatie die u wilt verwijderen.
2. Kies in de flyout die wordt geopend **Verwijderen**.

## <a name="copy-and-modify-a-sensitive-information-type"></a>En type vertrouwelijke informatie kopiëren en wijzigen

Gebruik deze procedure om een nieuw type gevoelige informatie te maken dat is gebaseerd op een bestaand type gevoelige informatie. 

1. Ga in het Compliancecentrum naar **Gegevensclassificatie** \> **Gevoelige informatietypen** en kies het type gevoelige informatie die u wilt kopiëren.
2. Kies in de flyout de optie **Kopiëren**.
3. Kies **Vernieuwen** in de lijst met typen gevoelige informatie en blader of zoek de kopie die u zojuist hebt gemaakt. Gedeeltelijke zoekopdrachten in een zoekopdracht werken, dus u kunt alleen zoeken naar `copy` en de zoekopdracht zou alle typen gevoelige informatie retourneren met het woord `copy` in de naam. 
4. Vul waarden in voor **Naam** en **Beschrijving** in en kies **Volgende**.
5. Kies het type kopie van uw gevoelige informatie en kies **Bewerken**. 
6. Geef uw nieuw type vertrouwelijke informatie een nieuwe **Naam** en **Beschrijving**.
7. U kunt de bestaande patronen bewerken of verwijderen en nieuwe patronen toevoegen. Kies het standaard betrouwbaarheidsniveau voor het nieuwe patroon. De waarden zijn **Lage betrouwbaarheid**, **Gemiddelde betrouwbaarheid** en **Hoge betrouwbaarheid**.
8. Kies en definieer **Primaire element**. Het primaire element kan een **Reguliere expressie**, een **Lijst met trefwoorden**, een **Trefwoordenlijst** of een van de vooraf geconfigureerde **Functies**. Zoe [Doel van de DLP-functies](what-the-dlp-functions-look-for.md).
9. Vul een waarde in voor **Nabijheid van tekens**.
10. (Optioneel) Als u **Ondersteuningselementen** of [**Aanvullende controles**](#more-information-on-additional-checks) heeft, voeg ze dan toe. U kunt zo nodig de verschillende **Ondersteunende elementen** groeperen.
11. Kies **Maken**.
12. Kies **Volgende**.
13. Kies de **aanbevolen betrouwbaarheidsniveau** dit type gevoelige informatie.
14. Controleer uw instellingen en kies **Verzenden**.

U kunt ook aangepaste typen gevoelige informatie maken met behulp van powershell- en exacte gegevensmatchingsfuncties. Zie voor meer informatie over deze methoden:
- [Een aangepast type gevoelige informatie maken in het Beveiligings- en compliancecentrum PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [Aangepast type gevoelige informatie voor DLP maken met exacte gegevensovereenkomsten (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

## <a name="more-information-on-regular-expression-validators"></a>Meer informatie over reguliere expressie-validators

### <a name="checksum-validator"></a>Checksum-validator

Als u een checksum wilt uitvoeren op een cijfer in een normale expressie, kunt u de *checksum validator gebruiken.* Stel dat u een SIT moet maken voor een licentienummer met acht cijfers, waarbij het laatste cijfer een checksumcijfer is dat wordt gevalideerd met een mod 9-berekening. U hebt het algoritme checksum als dit ingesteld:

Som = cijfer 1 * 1 + cijfer 2 * 2 + cijfer 3 * 3 * 3 + cijfer 4 * gewicht 4 + cijfer 5 * 5 * 5 + cijfer 6 * gewicht 6 + cijfer 7 * gewicht 7 + cijfer 8 * gewicht 8 Mod waarde = Som % 9 Als Mod-waarde == cijfer 8 Accountnummer geldig is Als Mod-waarde != cijfer 8 Accountnummer ongeldig is

1. Definieer het primaire element met deze normale expressie:

   ```console
   \d{8}
   ```

2. Voeg vervolgens de checksum-validator toe.
3. Voeg de gewogen waarden toe die zijn gescheiden door komma's, de positie van het controlecijfer en de waarde Mod. Zie Modulo-bewerking voor meer informatie over de bewerking [Modulo.](https://en.wikipedia.org/wiki/Modulo_operation)

> [!NOTE]
> Als het controlecijfer geen deel uitmaakt van de checksumberekening, gebruikt u 0 als het gewicht voor het controlecijfer. In het bovenstaande geval is 8 bijvoorbeeld gelijk aan 0 als het controlecijfer niet moet worden gebruikt voor het berekenen van het controlecijfer.  Modulo_operation).

![schermafbeelding van geconfigureerde checksum validator](../media/checksum-validator.png)

### <a name="date-validator"></a>Datum validator

Als een datumwaarde die is ingesloten in normale expressie, deel uitmaakt van een nieuw patroon dat u maakt, kunt u de *datum-validator* gebruiken om te testen of deze voldoet aan uw criteria. Stel dat u een SIT wilt maken voor een werknemeridentificatienummer met negen cijfers. De eerste zes cijfers zijn de datum van inhuur in DDMMYY-indeling en de laatste drie zijn willekeurig gegenereerde getallen. Controleer of de eerste zes cijfers de juiste notatie hebben.

1. Definieer het primaire element met deze normale expressie:

   ```console
   \d{9}
   ```

2. Voeg vervolgens de datum-validator toe.
3. Selecteer de datumnotatie en de begin verschuiving. Aangezien de datumreeks de eerste zes cijfers is, is de verschuiving `0` .

![schermafbeelding van de geconfigureerde datum-validator](../media/date-validator.png)

### <a name="functional-processors-as-validators"></a>Functionele processors als validators

U kunt functieprocessors gebruiken voor een aantal van de meest gebruikte ST's als validators. Op deze manier kunt u uw eigen reguliere expressie definiëren en ervoor zorgen dat ze de extra controles door de SIT kunnen uitvoeren. Zo zorgt Func_India_Aadhar ervoor dat de aangepaste reguliere expressie die door u is gedefinieerd, de validatielogica doorstaat die vereist is voor De Indiase Aadhar-kaart. Zie Wat [de DLP-functies zoeken](what-the-dlp-functions-look-for.md#what-the-dlp-functions-look-for)voor meer informatie over DLP-functies die als validators kunnen worden gebruikt. 

### <a name="luhn-check-validator"></a>Validator van Luhn-controle

U kunt de Luhn-controle-validator gebruiken als u een aangepast type gevoelige informatie hebt dat een normale expressie bevat die door het [Luhn-algoritme moet worden gebruikt.](https://en.wikipedia.org/wiki/Luhn_algorithm)

## <a name="more-information-on-additional-checks"></a>Meer informatie over extra controles

Hier zijn de definities en enkele voorbeelden voor de beschikbare extra controles.

**Specifieke overeenkomsten uitsluiten**: met deze controle kunt u trefwoorden definiëren die u wilt uitsluiten bij het detecteren van overeenkomsten voor het patroon dat u bewerkt. Testnummers zoals '4111111111111111' kunnen bijvoorbeeld worden uitgesloten, zodat deze niet worden gematcht als een geldig getal.

**Begint of begint niet met tekens**: met deze controle kunt u de tekens definiëren waarmee de overeenkomende items moeten beginnen. Als u bijvoorbeeld wilt dat met het patroon alleen creditcardnummers worden gedetecteerd die beginnen met 41, 42 of 43, selecteert u **Begint met** en voegt u 41, 42 en 43 toe aan de lijst, gescheiden door komma's. 

**Eindigt of begint niet met tekens**: met deze controle kunt u de tekens definiëren waarmee de overeenkomende items moeten eindigen. Als uw werknemersnummer bijvoorbeeld niet kan eindigen op 0 of 1, selecteert u **Niet eindigt op** en voegt u 0 en 1 toe aan de lijst, gescheiden door komma's.

**Dubbele tekens uitsluiten**: met deze controle kunt u overeenkomsten negeren waarbij alle cijfers hetzelfde zijn. Als het werknemer-id-nummer van zes cijfers bijvoorbeeld niet alle cijfers hetzelfde kan hebben, kunt u **Dubbele tekens uitsluiten**: 111111, 222222, 333333, 444444, 555555, 666666, 777777, 888888, 999999 en 000000 van de lijst met geldige overeenkomsten voor de werknemer-id.

**Voorvoegsels opnemen of uitsluiten**: met deze controle kunt u de trefwoorden definiëren die direct vóór de overeenkomende entiteit moeten worden gevonden of niet mogen worden gevonden. Afhankelijk van uw selectie worden entiteiten gematcht of niet gematcht als ze worden voorafgegaan door de voorvoegsels die u hier op neemt. Als u bijvoorbeeld het voorvoegsel **GUID:** **Uitsluit** wordt elke entiteit die wordt voorafgegaan door **GUID:** niet beschouwd als een overeenkomst.

**Achtervoegsels opnemen of uitsluiten**: met deze controle kunt u de trefwoorden definiëren die direct na de overeenkomende entiteit moeten worden gevonden of niet mogen worden gevonden. Afhankelijk van uw selectie worden entiteiten gematcht of niet gematcht als ze worden gevolgd door de achtervoegsels die u hier op neemt. Als u bijvoorbeeld het achtervoegsel **:GUID** **Uitsluit**, wordt alle tekst die wordt gevolgd door **:GUID** niet gematcht.


> [!NOTE]
> Microsoft 365 Information Protection ondersteunt dubbelbyte tekensettalen voor:
> - Vereenvoudigd Chinees
> - Traditioneel Chinees
> - Koreaks
> - Japans
>
>Deze ondersteuning is beschikbaar voor typen gevoelige informatie. Zie [Ondersteuning voor Information Protection voor releaseopmerkingen bij dubbel-bytetekensets (preview)](mip-dbcs-relnotes.md) voor meer informatie.

> [!TIP]
> Om patronen te detecteren die Chinese/Japanse karakters en enkelbyte karakters bevatten of om patronen te detecteren die Chinees/Japans en Engels bevatten, definieert u twee varianten van het trefwoord of de regex. 
>
> Om bijvoorbeeld een trefwoord als "机密的document" te detecteren, gebruikt u twee varianten van het trefwoord; een met een spatie tussen de Japanse en Engelse tekst en een andere zonder een spatie tussen de Japanse en Engelse tekst. De trefwoorden die in de SIT moeten worden toegevoegd, moeten dus "机密的 document" en "机密的document" zijn. Evenzo moeten twee varianten worden gebruikt om een zin "東京オリンピック2020" te detecteren; "東京オリンピック 2020" en "東京オリンピック2020".
>
> Zorg er bij het maken van een regex met een dubbelbyte-afbreekstreepje of een dubbele-byte-periode voor dat u beide tekens escaped, zoals een koppelteken of een punt in een regex. Hier is een voorbeeldregex ter referentie:
>
>    - (?<!\d)([４][０-９]{3}[\-?\－\t]*[０-９]{4}
>
> We raden u aan een tekenreeksovereenkomst te gebruiken in plaats van een woordovereenkomst in een zoekwoordenlijst.
