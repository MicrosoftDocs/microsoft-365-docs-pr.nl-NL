---
title: Een aangepast type gevoelige informatie verwijderen met PowerShell
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
description: Meer informatie over het verwijderen van een aangepast type gevoelige informatie met PowerShell
ms.openlocfilehash: 9365eeff6100b16c94b9fa09b06dc51b272b60a6
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322563"
---
# <a name="remove-a-custom-sensitive-information-type-using-powershell"></a>Een aangepast type gevoelige informatie verwijderen met PowerShell



In compliancecentrum PowerShell zijn er twee methoden om aangepaste typen vertrouwelijke gegevens te verwijderen:

- **Afzonderlijke aangepaste gevoelige informatietypen verwijderen:** gebruik de methode die is beschreven in Een aangepast type gevoelige informatie [wijzigen met PowerShell.](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell) U exporteert het aangepaste regelpakket dat het aangepaste type vertrouwelijke gegevens bevat, verwijdert het type vertrouwelijke gegevens uit het XML-bestand en importeert het bijgewerkte XML-bestand in het bestaande aangepaste regelpakket.

- **Een aangepast regelpakket en alle aangepaste typen vertrouwelijke gegevens die het bevat, verwijderen**: deze methode wordt in dit gedeelte beschreven.

> [!NOTE]
> Controleer voordat u een aangepast type vertrouwelijke gegevens verwijdert dat er geen DLP-beleid of Exchange-berichtenstroomregels (ook wel transportregels genoemd) meer verwijzen naar het type vertrouwelijke gegevens.

1. [Verbinding maken met compliancecentrum PowerShell](/powershell/exchange/exchange-online-powershell)

2. Om een aangepast regelpakket te verwijderen, gebruikt u de cmdlet [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage):

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity"
   ```

   U kunt de naamwaarde (voor elke taal) gebruiken of de `RulePack id`-waarde (GUID) om het regelpakket te identificeren.

   In dit voorbeeld wordt het regelpakket met de naam 'Medewerkers-ID aangepast regelpakket' verwijderd.

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

   Zie [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) voor meer gedetailleerde syntaxis- en parameterinformatie.

3. Voer een van de volgende stappen uit om er zeker van te zijn dat u een aangepast type vertrouwelijke gegevens hebt verwijderd:

   - Voer de cmdlet [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) uit en controleer dat het regelpakket niet meer in de lijst wordt vermeld:

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ```

   - Voer de cmdlet [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) uit om te verifiëren dat de typen vertrouwelijke gegevens in het verwijderde regelpakket niet meer in de lijst worden vermeld:

     ```powershell
     Get-DlpSensitiveInformationType
     ```

     Voor aangepaste typen vertrouwelijke gegevens wordt de waarde van de eigenschap Uitgever iets anders dan Microsoft Corporation.

   - Vervang \<Name\> met de naamwaarde van het type vertrouwelijke gegevens (bijvoorbeeld Medewerkers-ID) en voer de cmdlet [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) uit om te verifiëren dat het type vertrouwelijke gegevens niet meer in de lijst wordt vermeld:

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```

## <a name="more-information"></a>Meer informatie

- [Meer informatie over preventie van gegevensverlies](dlp-learn-about-dlp.md)

- [Definities van entiteiten van het type vertrouwelijke gegevens](sensitive-information-type-entity-definitions.md)

- [Doel van de DLP-functies](what-the-dlp-functions-look-for.md)
