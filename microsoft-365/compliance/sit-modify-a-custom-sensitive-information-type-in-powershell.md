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
# <a name="modify-a-custom-sensitive-information-type-using-powershell"></a><span data-ttu-id="6e3a2-103">Een aangepast type gevoelige informatie wijzigen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e3a2-103">Modify a custom sensitive information type using PowerShell</span></span>

<span data-ttu-id="6e3a2-104">Om in compliancecentrum PowerShell een aangepast type vertrouwelijke gegevens te bewerken, moet u:</span><span class="sxs-lookup"><span data-stu-id="6e3a2-104">In Compliance center PowerShell, modifying a custom sensitive information type requires you to:</span></span>

1. <span data-ttu-id="6e3a2-105">het bestaande regelpakket dat het aangepaste type vertrouwelijke gegevens bevat exporteren naar een XML-bestand (of het bestaande XML-bestand gebruiken als u dat hebt).</span><span class="sxs-lookup"><span data-stu-id="6e3a2-105">Export the existing rule package that contains the custom sensitive information type to an XML file (or use the existing XML file if you have it).</span></span>

2. <span data-ttu-id="6e3a2-106">het aangepaste type vertrouwelijke gegevens in het geëxporteerde XML-bestand bewerken.</span><span class="sxs-lookup"><span data-stu-id="6e3a2-106">Modify the custom sensitive information type in the exported XML file.</span></span>

3. <span data-ttu-id="6e3a2-107">het bijgewerkte XML-bestand importeren in het bestaande regelpakket.</span><span class="sxs-lookup"><span data-stu-id="6e3a2-107">Import the updated XML file back into the existing rule package.</span></span>

<span data-ttu-id="6e3a2-108">Zie [Verbinding maken met compliancecentrum PowerShell](/powershell/exchange/exchange-online-powershell) om verbinding te maken met compliancecentrum PowerShell. </span><span class="sxs-lookup"><span data-stu-id="6e3a2-108">To connect to Compliance Center PowerShell, see [Connect to Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell).</span></span>

### <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a><span data-ttu-id="6e3a2-109">Stap 1: Het bestaande regelpakket exporteren naar een XML-bestand</span><span class="sxs-lookup"><span data-stu-id="6e3a2-109">Step 1: Export the existing rule package to an XML file</span></span>

> [!NOTE]
> <span data-ttu-id="6e3a2-110">Als u een kopie van het XML-bestand hebt (bijvoorbeeld als u het net hebt gemaakt en geïmporteerd) kunt u verdergaan met de volgende stap om het XML-bestand te bewerken.</span><span class="sxs-lookup"><span data-stu-id="6e3a2-110">If you have a copy of the XML file (for example, you just created and imported it), you can skip to the next step to modify the XML file.</span></span>

1. <span data-ttu-id="6e3a2-111">Voer de cmdlet [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) uit om de naam van het aangepaste regelpakket te vinden als u die nog niet weet:</span><span class="sxs-lookup"><span data-stu-id="6e3a2-111">If you don't already know it, run the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to find the name of the custom rule package:</span></span>

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

   > [!NOTE]
   > <span data-ttu-id="6e3a2-112">Het ingebouwde regelpakket dat de ingebouwde typen vertrouwelijke gegevens bevat heet Microsoft Regelpakket.</span><span class="sxs-lookup"><span data-stu-id="6e3a2-112">The built-in rule package that contains the built-in sensitive information types is named Microsoft Rule Package.</span></span> <span data-ttu-id="6e3a2-113">Het regelpakket dat de aangepaste typen vertrouwelijke gegevens bevat die u hebt gemaakt in de compliancecentrum-gebruikersinterface heet Microsoft.SCCManaged.CustomRulePack.</span><span class="sxs-lookup"><span data-stu-id="6e3a2-113">The rule package that contains the custom sensitive information types that you created in the Compliance center UI is named Microsoft.SCCManaged.CustomRulePack.</span></span>

2. <span data-ttu-id="6e3a2-114">Gebruik de cmdlet [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) om het aangepaste regelpakket op te slaan in een variabele:</span><span class="sxs-lookup"><span data-stu-id="6e3a2-114">Use the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet to store the custom rule package to a variable:</span></span>

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageName"
   ```

   <span data-ttu-id="6e3a2-115">Als de naam van het regelpakket bijvoorbeeld 'Medewerkers-ID aangepast regelpakket' is, voert u de volgende cmdlet uit:</span><span class="sxs-lookup"><span data-stu-id="6e3a2-115">For example, if the name of the rule package is "Employee ID Custom Rule Pack", run the following cmdlet:</span></span>

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

3. <span data-ttu-id="6e3a2-116">Gebruik de cmdlet [Set-Content](/powershell/module/microsoft.powershell.management/set-content) om het aangepaste regelpakket te exporteren naar een XML-bestand:</span><span class="sxs-lookup"><span data-stu-id="6e3a2-116">Use the [Set-Content](/powershell/module/microsoft.powershell.management/set-content) cmdlet to export the custom rule package to an XML file:</span></span>

   ```powershell
   Set-Content -Path "XMLFileAndPath" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

   <span data-ttu-id="6e3a2-117">In dit voorbeeld wordt het regelpakket geëxporteerd naar een bestand met de naam ExportedRulePackage.xml in de map C:\Mijn documenten.</span><span class="sxs-lookup"><span data-stu-id="6e3a2-117">This example export the rule package to the file named ExportedRulePackage.xml in the C:\My Documents folder.</span></span>

   ```powershell
   Set-Content -Path "C:\My Documents\ExportedRulePackage.xml" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

#### <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a><span data-ttu-id="6e3a2-118">Stap 2: het type vertrouwelijke gegevens in het geëxporteerde XML-bestand bewerken</span><span class="sxs-lookup"><span data-stu-id="6e3a2-118">Step 2: Modify the sensitive information type in the exported XML file</span></span>

<span data-ttu-id="6e3a2-119">Typen vertrouwelijke gegevens in het XML-bestand en andere elementen in het bestand worden eerder in dit onderwerp beschreven.</span><span class="sxs-lookup"><span data-stu-id="6e3a2-119">Sensitive information types in the XML file and other elements in the file are described earlier in this topic.</span></span>

#### <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a><span data-ttu-id="6e3a2-120">Stap 3: het bijgewerkte XML-bestand importeren in het bestaande regelpakket</span><span class="sxs-lookup"><span data-stu-id="6e3a2-120">Step 3: Import the updated XML file back into the existing rule package</span></span>

<span data-ttu-id="6e3a2-121">Gebruik de cmdlet [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) om het bijgewerkte XML-bestand te importeren in het bestaande regelpakket:</span><span class="sxs-lookup"><span data-stu-id="6e3a2-121">To import the updated XML back into the existing rule package, use the [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) cmdlet:</span></span>

```powershell
Set-DlpSensitiveInformationTypeRulePackage -FileData ([Byte[]]$(Get-Content -Path "C:\My Documents\External Sensitive Info Type Rule Collection.xml" -Encoding Byte -ReadCount 0))
```

<span data-ttu-id="6e3a2-122">Zie [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) voor meer gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="6e3a2-122">For detailed syntax and parameter information, see [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage).</span></span>


## <a name="more-information"></a><span data-ttu-id="6e3a2-123">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="6e3a2-123">More information</span></span>

- [<span data-ttu-id="6e3a2-124">Meer informatie over preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="6e3a2-124">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="6e3a2-125">Definities van entiteiten van het type vertrouwelijke gegevens</span><span class="sxs-lookup"><span data-stu-id="6e3a2-125">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="6e3a2-126">Doel van de DLP-functies</span><span class="sxs-lookup"><span data-stu-id="6e3a2-126">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
