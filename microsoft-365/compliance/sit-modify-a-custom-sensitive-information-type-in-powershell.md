---
title: Een aangepast type gevoelige informatie wijzigen met PowerShell
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Meer informatie over het wijzigen van aangepaste gevoelige informatie met PowerShell.
ms.openlocfilehash: 9f8a9ef119e632c695113320ab86a3bdfef8a197
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322564"
---
# <a name="modify-a-custom-sensitive-information-type-using-powershell"></a>Een aangepast type gevoelige informatie wijzigen met PowerShell

Om in compliancecentrum PowerShell een aangepast type vertrouwelijke gegevens te bewerken, moet u:

1. het bestaande regelpakket dat het aangepaste type vertrouwelijke gegevens bevat exporteren naar een XML-bestand (of het bestaande XML-bestand gebruiken als u dat hebt).

2. het aangepaste type vertrouwelijke gegevens in het geëxporteerde XML-bestand bewerken.

3. het bijgewerkte XML-bestand importeren in het bestaande regelpakket.

Zie [Verbinding maken met compliancecentrum PowerShell](/powershell/exchange/exchange-online-powershell) om verbinding te maken met compliancecentrum PowerShell. 

### <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a>Stap 1: Het bestaande regelpakket exporteren naar een XML-bestand

> [!NOTE]
> Als u een kopie van het XML-bestand hebt (bijvoorbeeld als u het net hebt gemaakt en geïmporteerd) kunt u verdergaan met de volgende stap om het XML-bestand te bewerken.

1. Voer de cmdlet [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) uit om de naam van het aangepaste regelpakket te vinden als u die nog niet weet:

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

   > [!NOTE]
   > Het ingebouwde regelpakket dat de ingebouwde typen vertrouwelijke gegevens bevat heet Microsoft Regelpakket. Het regelpakket dat de aangepaste typen vertrouwelijke gegevens bevat die u hebt gemaakt in de compliancecentrum-gebruikersinterface heet Microsoft.SCCManaged.CustomRulePack.

2. Gebruik de cmdlet [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) om het aangepaste regelpakket op te slaan in een variabele:

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageName"
   ```

   Als de naam van het regelpakket bijvoorbeeld 'Medewerkers-ID aangepast regelpakket' is, voert u de volgende cmdlet uit:

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

3. Gebruik de cmdlet [Set-Content](/powershell/module/microsoft.powershell.management/set-content) om het aangepaste regelpakket te exporteren naar een XML-bestand:

   ```powershell
   Set-Content -Path "XMLFileAndPath" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

   In dit voorbeeld wordt het regelpakket geëxporteerd naar een bestand met de naam ExportedRulePackage.xml in de map C:\Mijn documenten.

   ```powershell
   Set-Content -Path "C:\My Documents\ExportedRulePackage.xml" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

#### <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a>Stap 2: het type vertrouwelijke gegevens in het geëxporteerde XML-bestand bewerken

Typen vertrouwelijke gegevens in het XML-bestand en andere elementen in het bestand worden eerder in dit onderwerp beschreven.

#### <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a>Stap 3: het bijgewerkte XML-bestand importeren in het bestaande regelpakket

Gebruik de cmdlet [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) om het bijgewerkte XML-bestand te importeren in het bestaande regelpakket:

```powershell
Set-DlpSensitiveInformationTypeRulePackage -FileData ([Byte[]]$(Get-Content -Path "C:\My Documents\External Sensitive Info Type Rule Collection.xml" -Encoding Byte -ReadCount 0))
```

Zie [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) voor meer gedetailleerde syntaxis- en parameterinformatie.


## <a name="more-information"></a>Meer informatie

- [Meer informatie over preventie van gegevensverlies](dlp-learn-about-dlp.md)

- [Definities van entiteiten van het type vertrouwelijke gegevens](sensitive-information-type-entity-definitions.md)

- [Doel van de DLP-functies](what-the-dlp-functions-look-for.md)
