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
# <a name="remove-a-custom-sensitive-information-type-using-powershell"></a><span data-ttu-id="5ee9c-103">Een aangepast type gevoelige informatie verwijderen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ee9c-103">Remove a custom sensitive information type using PowerShell</span></span>



<span data-ttu-id="5ee9c-104">In compliancecentrum PowerShell zijn er twee methoden om aangepaste typen vertrouwelijke gegevens te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="5ee9c-104">In Compliance center PowerShell, there are two methods to remove custom sensitive information types:</span></span>

- <span data-ttu-id="5ee9c-105">**Afzonderlijke aangepaste gevoelige informatietypen verwijderen:** gebruik de methode die is beschreven in Een aangepast type gevoelige informatie [wijzigen met PowerShell.](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell)</span><span class="sxs-lookup"><span data-stu-id="5ee9c-105">**Remove individual custom sensitive information types**: Use the method documented in [Modify a custom sensitive information type using PowerShell](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell).</span></span> <span data-ttu-id="5ee9c-106">U exporteert het aangepaste regelpakket dat het aangepaste type vertrouwelijke gegevens bevat, verwijdert het type vertrouwelijke gegevens uit het XML-bestand en importeert het bijgewerkte XML-bestand in het bestaande aangepaste regelpakket.</span><span class="sxs-lookup"><span data-stu-id="5ee9c-106">You export the custom rule package that contains the custom sensitive information type, remove the sensitive information type from the XML file, and import the updated XML file back into the existing custom rule package.</span></span>

- <span data-ttu-id="5ee9c-107">**Een aangepast regelpakket en alle aangepaste typen vertrouwelijke gegevens die het bevat, verwijderen**: deze methode wordt in dit gedeelte beschreven.</span><span class="sxs-lookup"><span data-stu-id="5ee9c-107">**Remove a custom rule package and all custom sensitive information types that it contains**: This method is documented in this section.</span></span>

> [!NOTE]
> <span data-ttu-id="5ee9c-108">Controleer voordat u een aangepast type vertrouwelijke gegevens verwijdert dat er geen DLP-beleid of Exchange-berichtenstroomregels (ook wel transportregels genoemd) meer verwijzen naar het type vertrouwelijke gegevens.</span><span class="sxs-lookup"><span data-stu-id="5ee9c-108">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. [<span data-ttu-id="5ee9c-109">Verbinding maken met compliancecentrum PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ee9c-109">Connect to Compliance center PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

2. <span data-ttu-id="5ee9c-110">Om een aangepast regelpakket te verwijderen, gebruikt u de cmdlet [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage):</span><span class="sxs-lookup"><span data-stu-id="5ee9c-110">To remove a custom rule package, use the [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) cmdlet:</span></span>

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity"
   ```

   <span data-ttu-id="5ee9c-111">U kunt de naamwaarde (voor elke taal) gebruiken of de `RulePack id`-waarde (GUID) om het regelpakket te identificeren.</span><span class="sxs-lookup"><span data-stu-id="5ee9c-111">You can use the Name value (for any language) or the `RulePack id` (GUID) value to identify the rule package.</span></span>

   <span data-ttu-id="5ee9c-112">In dit voorbeeld wordt het regelpakket met de naam 'Medewerkers-ID aangepast regelpakket' verwijderd.</span><span class="sxs-lookup"><span data-stu-id="5ee9c-112">This example removes the rule package named "Employee ID Custom Rule Pack".</span></span>

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

   <span data-ttu-id="5ee9c-113">Zie [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) voor meer gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="5ee9c-113">For detailed syntax and parameter information, see [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage).</span></span>

3. <span data-ttu-id="5ee9c-114">Voer een van de volgende stappen uit om er zeker van te zijn dat u een aangepast type vertrouwelijke gegevens hebt verwijderd:</span><span class="sxs-lookup"><span data-stu-id="5ee9c-114">To verify that you've successfully removed a custom sensitive information type, do any of the following steps:</span></span>

   - <span data-ttu-id="5ee9c-115">Voer de cmdlet [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) uit en controleer dat het regelpakket niet meer in de lijst wordt vermeld:</span><span class="sxs-lookup"><span data-stu-id="5ee9c-115">Run the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet and verify the rule package is no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ```

   - <span data-ttu-id="5ee9c-116">Voer de cmdlet [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) uit om te verifiëren dat de typen vertrouwelijke gegevens in het verwijderde regelpakket niet meer in de lijst worden vermeld:</span><span class="sxs-lookup"><span data-stu-id="5ee9c-116">Run the [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information types in the removed rule package are no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType
     ```

     <span data-ttu-id="5ee9c-117">Voor aangepaste typen vertrouwelijke gegevens wordt de waarde van de eigenschap Uitgever iets anders dan Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="5ee9c-117">For custom sensitive information types, the Publisher property value will be something other than Microsoft Corporation.</span></span>

   - <span data-ttu-id="5ee9c-118">Vervang \<Name\> met de naamwaarde van het type vertrouwelijke gegevens (bijvoorbeeld Medewerkers-ID) en voer de cmdlet [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) uit om te verifiëren dat het type vertrouwelijke gegevens niet meer in de lijst wordt vermeld:</span><span class="sxs-lookup"><span data-stu-id="5ee9c-118">Replace \<Name\> with the Name value of the sensitive information type (for example, Employee ID) and run the [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information type is no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```

## <a name="more-information"></a><span data-ttu-id="5ee9c-119">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="5ee9c-119">More information</span></span>

- [<span data-ttu-id="5ee9c-120">Meer informatie over preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="5ee9c-120">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="5ee9c-121">Definities van entiteiten van het type vertrouwelijke gegevens</span><span class="sxs-lookup"><span data-stu-id="5ee9c-121">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="5ee9c-122">Doel van de DLP-functies</span><span class="sxs-lookup"><span data-stu-id="5ee9c-122">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
