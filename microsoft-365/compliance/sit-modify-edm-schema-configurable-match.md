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
# <a name="modify-exact-data-match-schema-to-use-configurable-match"></a>Wijzig het schema voor exacte gegevensovereenkomst om een configureerbare overeenkomst te gebruiken

Met EDM-classificatie (exacte gegevensovereenkomst) kunt u aangepaste typen gevoelige informatie maken die verwijzen naar exacte waarden in een database met gevoelige informatie. Wanneer u varianten van een exacte tekenreeks wilt toestaan, kunt u *configureerbare overeenkomst* gebruiken om Microsoft 365 op te geven dat hoofdletters en bepaalde scheidingstekens moeten worden genegeerd. 

> [!IMPORTANT]
> Gebruik deze procedure om een bestaand EDM-schema en gegevensbestand te wijzigen.

1. Verwijder de **EdmUploadAgent.exe** van de computer die u gebruikt om verbinding te maken met Microsoft 365 voor het EDM-schema en voor uploaddoeleinden van gegevensbestand.

2. Download het juiste **EdmUploadAgent.exe** bestand voor uw abonnement via de onderstaande koppelingen:
    - [Commercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - de meeste commerciële klanten moeten dit gebruiken
    - [GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - Dit is specifiek voor abonnees van de cloud van de overheid met hoge beveiliging
    - [DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - dit is specifiek voor klanten van de cloud van het Department of Defense van de Verenigde Staten

3. Autoriseer de EDM Upload Agent, open het opdrachtpromptvenster (als administrator) en voer de volgende opdracht uit:

   `EdmUploadAgent.exe /Authorize`

4. Als u nog geen kopie van het bestaande schema hebt, moet u een kopie van het bestaande schema downloaden. Voer deze opdracht uit:

    `EdmUploadAgent.exe /SaveSchema /DataStoreName <dataStoreName> [/OutputDir [Output dir location]]`

5. Pas het schema aan zodat elke kolom gebruikmaakt van 'caseInsensitive' en / of 'ignoredDelimiters'.  De standaardwaarde voor 'caseInsensitive' is 'false' en voor 'ignoredDelimiters' is het een lege tekenreeks. 

> [!NOTE]
> Het onderliggende type aangepaste gevoelige informatie of het ingebouwde type gevoelige informatie waarmee het algemene reguliere expressie-patroon wordt gedetecteerd, moet de detectie van variaties die worden vermeld bij 'ignoredDelimiters' ondersteunen. Met het ingebouwde type gevoelige informatie van het Amerikaanse socialezekerheidsnummer (SSN) kunnen bijvoorbeeld variaties in de gegevens worden gedetecteerd die streepjes, spaties of gebrek aan spaties bevatten tussen de gegroepeerde getallen waartussen de SSN bestaat. Daardoor zijn de enige scheidingstekens die relevant zijn voor het opnemen in ignoredDelimiters van EDM voor SSN-gegevens: streepje en spatie.

Hier ziet u een voorbeeldschema waarin een niet-hoofdlettergevoelige overeenkomst wordt nagebootst door de extra kolommen te maken die nodig zijn om variaties in de hoofdletters in de gevoelige gegevens te herkennen.

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

In het bovenstaande voorbeeld zijn de variaties van de oorspronkelijke kolom `PolicyNumber` niet meer nodig als zowel `caseInsensitive` als `ignoredDelimiters` zijn toegevoegd.

Als u dit schema wilt bijwerken, zodat EDM gebruikmaakt van configureerbare overeenkomst, gebruikt `caseInsensitive` en `ignoredDelimiters` vlaggen.  Dit ziet er als volgt uit:

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
         <Field name="PolicyNumber" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
  </DataStore>
</EdmSchema>
```

De `ignoredDelimiters` vlag ondersteunt alle niet-alfanumerieke tekens. Hier volgen enkele voorbeelden:
- \.
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

The `ignoredDelimiters` vlag ondersteunt het volgende niet:
- tekens 0-9
- A-Z
- a-z
- \"
- \,

6. Verbinding maken met het Beveiligings- en compliancecentrum met behulp van de procedures in [Verbinding maken met Beveiligings- en compliancecentrum van PowerShell](/powershell/exchange/connect-to-scc-powershell).

> [!NOTE]
> Als uw organisatie [Klantsleutel voor Microsoft 365 heeft ingesteld op tenantniveau (openbare preview)](customer-key-tenant-level.md#overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview), wordt de versleutelingsfunctionaliteit automatisch gebruikt door exacte gegevensmatch. Dit is alleen beschikbaar voor E5-gelicentieerde tenants in de commerciële cloud.

7. Werk uw schema bij door deze cmdlets een voor een uit te voeren:

`$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0`

`Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

8. Werk het gegevensbestand zo nodig bij aan de nieuwe schemaversie

> [!TIP]
> U kunt eventueel een validatie uitvoeren voor het CSV-bestand voordat u het uploadt. Voer het volgende uit:
>
>`EdmUploadAgent.exe /ValidateData /DataFile [data file] [schema file]`
>
>Voor meer informatie over alle EdmUploadAgent.exe >ondersteunde parameters uitvoeren
>
> `EdmUploadAgent.exe /?`

9. Open het opdrachtpromptvenster (als administrator) en voer de volgende opdracht uit om uw gevoelige informatie te hashen en uploaden:

    `EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Salt [custom salt] /Schema [Schema file]`


## <a name="related-articles"></a>Verwante artikelen

- [Aangepaste typen gevoelige informatie maken met de classificatie van exacte gegevensovereenkomsten](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [Definities van entiteiten van het type gevoelige informatie](sensitive-information-type-entity-definitions.md)
- [Aangepaste typen gevoelige informatie](./sensitive-information-type-learn-about.md)
- [Meer informatie over preventie van gegevensverlies](dlp-learn-about-dlp.md)
- [Microsoft Cloud App Security](/cloud-app-security)
- [New-DlpEdmSchema](/powershell/module/exchange/new-dlpedmschema)