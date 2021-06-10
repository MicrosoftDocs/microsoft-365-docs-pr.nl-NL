---
title: Uw organisatiemerk toevoegen aan uw versleutelde berichten
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/1/2020
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Lees hoe Office 365 globale beheerders de huisstijl van uw organisatie kunnen toepassen op versleutelde e-mailberichten & inhoud van de versleutelingsportal.
ms.openlocfilehash: 2898e12ad00d11cd9eb2f3be5d817ef113607e79
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/26/2021
ms.locfileid: "52162485"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a><span data-ttu-id="1274d-103">Het merk van uw organisatie toevoegen aan uw Microsoft 365 berichtenversleuteling voor bedrijven</span><span class="sxs-lookup"><span data-stu-id="1274d-103">Add your organization's brand to your Microsoft 365 for business Message Encryption encrypted messages</span></span>

<span data-ttu-id="1274d-104">U kunt de huisstijl van uw bedrijf toepassen om het uiterlijk van de e-mailberichten van uw organisatie en de versleutelingsportal aan te passen.</span><span class="sxs-lookup"><span data-stu-id="1274d-104">You can apply your company branding to customize the look of your organization's email messages and the encryption portal.</span></span> <span data-ttu-id="1274d-105">U moet globale beheerdersmachtigingen toepassen op uw werk- of schoolaccount voordat u aan de slag kunt.</span><span class="sxs-lookup"><span data-stu-id="1274d-105">You'll need to apply global administrator permissions to your work or school account before you can get started.</span></span> <span data-ttu-id="1274d-106">Wanneer u deze machtigingen hebt, gebruikt u de Get-OMEConfiguration en Set-OMEConfiguration Windows PowerShell cmdlets om deze onderdelen van versleutelde e-mailberichten aan te passen:</span><span class="sxs-lookup"><span data-stu-id="1274d-106">Once you have these permissions, use the Get-OMEConfiguration and Set-OMEConfiguration Windows PowerShell cmdlets to customize these parts of encrypted email messages:</span></span>
  
- <span data-ttu-id="1274d-107">Inleidende tekst</span><span class="sxs-lookup"><span data-stu-id="1274d-107">Introductory text</span></span>

- <span data-ttu-id="1274d-108">Vrijwaringstekst</span><span class="sxs-lookup"><span data-stu-id="1274d-108">Disclaimer text</span></span>

- <span data-ttu-id="1274d-109">URL voor de privacyverklaring van uw organisatie</span><span class="sxs-lookup"><span data-stu-id="1274d-109">URL for Your organization's privacy statement</span></span>

- <span data-ttu-id="1274d-110">Tekst in de OME-portal</span><span class="sxs-lookup"><span data-stu-id="1274d-110">Text in the OME portal</span></span>

- <span data-ttu-id="1274d-111">Logo dat wordt weergegeven in het e-mailbericht en de OME-portal, of dat u helemaal geen logo wilt gebruiken</span><span class="sxs-lookup"><span data-stu-id="1274d-111">Logo that appears in the email message and OME portal, or whether to use a logo at all</span></span>

- <span data-ttu-id="1274d-112">Achtergrondkleur in het e-mailbericht en de OME-portal</span><span class="sxs-lookup"><span data-stu-id="1274d-112">Background color in the email message and OME portal</span></span>

<span data-ttu-id="1274d-113">U kunt ook op elk moment terugkeren naar het standaard-uiterlijk.</span><span class="sxs-lookup"><span data-stu-id="1274d-113">You can also revert back to the default look and feel at any time.</span></span>

<span data-ttu-id="1274d-114">Als u meer controle wilt, gebruikt u Office 365 Advanced Message Encryption om meerdere sjablonen te maken voor versleutelde e-mailberichten die afkomstig zijn van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="1274d-114">If you'd like more control, use Office 365 Advanced Message Encryption to create multiple templates for encrypted emails originating from your organization.</span></span> <span data-ttu-id="1274d-115">Gebruik deze sjablonen om delen van de eindgebruikerservaring te beheren.</span><span class="sxs-lookup"><span data-stu-id="1274d-115">Use these templates to control parts of the end-user experience.</span></span> <span data-ttu-id="1274d-116">Geef bijvoorbeeld op of geadresseerden Google, Yahoo en Microsoft-accounts kunnen gebruiken om zich aan te melden bij de versleutelingsportal.</span><span class="sxs-lookup"><span data-stu-id="1274d-116">For example, specify whether recipients can use Google, Yahoo, and Microsoft Accounts to sign in to the encryption portal.</span></span> <span data-ttu-id="1274d-117">Gebruik sjablonen om aan verschillende gebruiksgevallen te voldoen, zoals:</span><span class="sxs-lookup"><span data-stu-id="1274d-117">Use templates to fulfill several use cases, such as:</span></span>

- <span data-ttu-id="1274d-118">Afzonderlijke afdelingen, zoals Financiën, Verkoop, en dergelijke.</span><span class="sxs-lookup"><span data-stu-id="1274d-118">Individual departments, such as Finance, Sales, and so on.</span></span>

- <span data-ttu-id="1274d-119">Verschillende producten</span><span class="sxs-lookup"><span data-stu-id="1274d-119">Different products</span></span>

- <span data-ttu-id="1274d-120">Verschillende geografische regio's of landen</span><span class="sxs-lookup"><span data-stu-id="1274d-120">Different geographical regions or countries</span></span>

- <span data-ttu-id="1274d-121">Of u wilt toestaan dat e-mailberichten worden ingetrokken</span><span class="sxs-lookup"><span data-stu-id="1274d-121">Whether you want to allow emails to be revoked</span></span>

- <span data-ttu-id="1274d-122">Of u wilt dat e-mailberichten die naar externe geadresseerden worden verzonden, na een bepaald aantal dagen verlopen.</span><span class="sxs-lookup"><span data-stu-id="1274d-122">Whether you want emails sent to external recipients to expire after a specified number of days.</span></span>

<span data-ttu-id="1274d-123">Nadat u de sjablonen hebt gemaakt, kunt u deze toepassen op versleutelde e-mailberichten met behulp van Exchange regels voor e-mailstroom.</span><span class="sxs-lookup"><span data-stu-id="1274d-123">Once you've created the templates, you can apply them to encrypted emails by using Exchange mail flow rules.</span></span> <span data-ttu-id="1274d-124">Als u een Office 365 Advanced Message Encryption, kunt u alle e-mailberichten die u hebt gebrandmerkt, intrekken met behulp van deze sjablonen.</span><span class="sxs-lookup"><span data-stu-id="1274d-124">If you have Office 365 Advanced Message Encryption, you can revoke any email that you've branded by using these templates.</span></span>

## <a name="work-with-ome-branding-templates"></a><span data-ttu-id="1274d-125">Werken met OME-huisstijlsjablonen</span><span class="sxs-lookup"><span data-stu-id="1274d-125">Work with OME branding templates</span></span>

<span data-ttu-id="1274d-126">U kunt verschillende functies in een huisstijlsjabloon wijzigen.</span><span class="sxs-lookup"><span data-stu-id="1274d-126">You can modify several features within a branding template.</span></span> <span data-ttu-id="1274d-127">U kunt de standaardsjabloon wijzigen, maar niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="1274d-127">You can modify, but not remove, the default template.</span></span> <span data-ttu-id="1274d-128">Als u geavanceerde berichtversleuteling hebt, kunt u ook aangepaste sjablonen maken, wijzigen en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="1274d-128">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span> <span data-ttu-id="1274d-129">Gebruik Windows PowerShell om met één huisstijlsjabloon tegelijk te werken.</span><span class="sxs-lookup"><span data-stu-id="1274d-129">Use Windows PowerShell to work with one branding template at a time.</span></span>

- <span data-ttu-id="1274d-130">[Set-OMEConfiguration-](/powershell/module/exchange/set-omeconfiguration) Wijzig de standaardbrandingsjabloon of een aangepaste huisstijlsjabloon die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="1274d-130">[Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) - Modify the default branding template or a custom branding template that you created.</span></span>
- <span data-ttu-id="1274d-131">[New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) - Maak een nieuwe huisstijlsjabloon, alleen Geavanceerde berichtversleuteling.</span><span class="sxs-lookup"><span data-stu-id="1274d-131">[New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) - Create a new branding template, Advanced Message Encryption only.</span></span>
- <span data-ttu-id="1274d-132">[Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration) - Verwijder een aangepaste huisstijlsjabloon, alleen Geavanceerde berichtversleuteling.</span><span class="sxs-lookup"><span data-stu-id="1274d-132">[Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration) - Remove a custom branding template, Advanced Message Encryption only.</span></span> <span data-ttu-id="1274d-133">U kunt de standaardsjabloon voor huisstijl niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="1274d-133">You can't delete the default branding template.</span></span>
  
## <a name="modify-an-ome-branding-template"></a><span data-ttu-id="1274d-134">Een OME-huisstijlsjabloon wijzigen</span><span class="sxs-lookup"><span data-stu-id="1274d-134">Modify an OME branding template</span></span>

<span data-ttu-id="1274d-135">Gebruik Windows PowerShell om één huisstijlsjabloon tegelijk te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="1274d-135">Use Windows PowerShell to modify one branding template at a time.</span></span> <span data-ttu-id="1274d-136">Als u geavanceerde berichtversleuteling hebt, kunt u ook aangepaste sjablonen maken, wijzigen en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="1274d-136">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span>

1. <span data-ttu-id="1274d-137">Als u een werk- of schoolaccount gebruikt met globale beheerdersmachtigingen in uw organisatie, start u een Windows PowerShell en maakt u verbinding met Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1274d-137">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="1274d-138">Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="1274d-138">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="1274d-139">Gebruik de Set-OMEConfiguration cmdlet zoals beschreven in [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration) of gebruik de volgende afbeelding en tabel voor richtlijnen.</span><span class="sxs-lookup"><span data-stu-id="1274d-139">Use the Set-OMEConfiguration cmdlet as described in [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration) or use the following graphic and table for guidance.</span></span>

![Aanpasbare e-mailonderdelen](../media/ome-template-breakout.png)

|<span data-ttu-id="1274d-141">**Deze functie van de versleutelingservaring aanpassen**</span><span class="sxs-lookup"><span data-stu-id="1274d-141">**To customize this feature of the encryption experience**</span></span>|<span data-ttu-id="1274d-142">**Deze opdrachten gebruiken**</span><span class="sxs-lookup"><span data-stu-id="1274d-142">**Use these commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1274d-143">Achtergrondkleur</span><span class="sxs-lookup"><span data-stu-id="1274d-143">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> <span data-ttu-id="1274d-144">**Voorbeeld:**</span><span class="sxs-lookup"><span data-stu-id="1274d-144">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> <span data-ttu-id="1274d-145">Zie de sectie Achtergrondkleuren [](#background-color-reference) verder in dit artikel voor meer informatie over achtergrondkleuren.</span><span class="sxs-lookup"><span data-stu-id="1274d-145">For more information about background colors, see the [Background colors](#background-color-reference) section later in this article.</span></span>|
|<span data-ttu-id="1274d-146">Logo</span><span class="sxs-lookup"><span data-stu-id="1274d-146">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> <span data-ttu-id="1274d-147">**Voorbeeld:**</span><span class="sxs-lookup"><span data-stu-id="1274d-147">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> <span data-ttu-id="1274d-148">Ondersteunde bestandsindelingen: .png, .jpg, .bmp of .tiff</span><span class="sxs-lookup"><span data-stu-id="1274d-148">Supported file formats: .png, .jpg, .bmp, or .tiff</span></span>  <br/> <span data-ttu-id="1274d-149">Optimale grootte van het logobestand: minder dan 40 KB</span><span class="sxs-lookup"><span data-stu-id="1274d-149">Optimal size of logo file: less than 40 KB</span></span>  <br/> <span data-ttu-id="1274d-150">Optimale grootte van de afbeelding van het logo: 170x70 pixels.</span><span class="sxs-lookup"><span data-stu-id="1274d-150">Optimal size of logo image: 170x70 pixels.</span></span> <span data-ttu-id="1274d-151">Als de afbeelding deze dimensies overschrijdt, wordt het logo voor weergave in de portal door de service van het 1000-jaar-10-2017-2019-2019-2019-2010-2019-</span><span class="sxs-lookup"><span data-stu-id="1274d-151">If your image exceeds these dimensions, the service resizes your logo for display in the portal.</span></span> <span data-ttu-id="1274d-152">De service wijzigt het afbeeldingsbestand zelf niet.</span><span class="sxs-lookup"><span data-stu-id="1274d-152">The service doesn't modify the graphic file itself.</span></span> <span data-ttu-id="1274d-153">Gebruik de optimale grootte voor het beste resultaat.</span><span class="sxs-lookup"><span data-stu-id="1274d-153">For best results, use the optimal size.</span></span>|
|<span data-ttu-id="1274d-154">Tekst naast de naam en het e-mailadres van de afzender</span><span class="sxs-lookup"><span data-stu-id="1274d-154">Text next to the sender's name and email address</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> <span data-ttu-id="1274d-155">**Voorbeeld:**</span><span class="sxs-lookup"><span data-stu-id="1274d-155">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|<span data-ttu-id="1274d-156">Tekst die wordt weergegeven op de knop Bericht lezen</span><span class="sxs-lookup"><span data-stu-id="1274d-156">Text that appears on the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> <span data-ttu-id="1274d-157">**Voorbeeld:**</span><span class="sxs-lookup"><span data-stu-id="1274d-157">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|<span data-ttu-id="1274d-158">Tekst die wordt weergegeven onder de knop Bericht lezen</span><span class="sxs-lookup"><span data-stu-id="1274d-158">Text that appears below the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> <span data-ttu-id="1274d-159">**Voorbeeld:**</span><span class="sxs-lookup"><span data-stu-id="1274d-159">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|<span data-ttu-id="1274d-160">URL voor de koppeling Privacyverklaring</span><span class="sxs-lookup"><span data-stu-id="1274d-160">URL for the Privacy Statement link</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> <span data-ttu-id="1274d-161">**Voorbeeld:**</span><span class="sxs-lookup"><span data-stu-id="1274d-161">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|<span data-ttu-id="1274d-162">Vrijwaringsverklaring in het e-mailbericht met het versleutelde bericht</span><span class="sxs-lookup"><span data-stu-id="1274d-162">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> <span data-ttu-id="1274d-163">**Voorbeeld:**</span><span class="sxs-lookup"><span data-stu-id="1274d-163">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|<span data-ttu-id="1274d-164">Tekst die boven aan de portal voor het weergeven van versleutelde e-mail wordt weergegeven</span><span class="sxs-lookup"><span data-stu-id="1274d-164">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> <span data-ttu-id="1274d-165">**Voorbeeld:**</span><span class="sxs-lookup"><span data-stu-id="1274d-165">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|<span data-ttu-id="1274d-166">Verificatie in- of uitschakelen met een een time pass-code voor deze aangepaste sjabloon</span><span class="sxs-lookup"><span data-stu-id="1274d-166">To enable or disable authentication with a one-time pass code for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> <span data-ttu-id="1274d-167">**Voorbeelden:**</span><span class="sxs-lookup"><span data-stu-id="1274d-167">**Examples:**</span></span> <br/><span data-ttu-id="1274d-168">Een een time passcodes inschakelen voor deze aangepaste sjabloon</span><span class="sxs-lookup"><span data-stu-id="1274d-168">To enable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> <span data-ttu-id="1274d-169">Een een time passcodes uitschakelen voor deze aangepaste sjabloon</span><span class="sxs-lookup"><span data-stu-id="1274d-169">To disable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|<span data-ttu-id="1274d-170">Verificatie met Microsoft-, Google- of Yahoo-identiteiten in- of uitschakelen voor deze aangepaste sjabloon</span><span class="sxs-lookup"><span data-stu-id="1274d-170">To enable or disable authentication with Microsoft, Google, or Yahoo identities for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> <span data-ttu-id="1274d-171">**Voorbeelden:**</span><span class="sxs-lookup"><span data-stu-id="1274d-171">**Examples:**</span></span> <br/><span data-ttu-id="1274d-172">Sociale ID's inschakelen voor deze aangepaste sjabloon</span><span class="sxs-lookup"><span data-stu-id="1274d-172">To enable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> <span data-ttu-id="1274d-173">Sociale ID's uitschakelen voor deze aangepaste sjabloon</span><span class="sxs-lookup"><span data-stu-id="1274d-173">To disable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a><span data-ttu-id="1274d-174">Een OME-huisstijlsjabloon maken (Geavanceerde berichtversleuteling)</span><span class="sxs-lookup"><span data-stu-id="1274d-174">Create an OME branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="1274d-175">Als u een Office 365 Advanced Message Encryption, kunt u aangepaste huisstijlsjablonen voor uw organisatie maken met de cmdlet [New-OMEConfiguration.](/powershell/module/exchange/new-omeconfiguration)</span><span class="sxs-lookup"><span data-stu-id="1274d-175">If you have Office 365 Advanced Message Encryption, you can create custom branding templates for your organization by using the [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) cmdlet.</span></span> <span data-ttu-id="1274d-176">Nadat u de sjabloon hebt gemaakt, wijzigt u de sjabloon met de Set-OMEConfiguration cmdlet zoals beschreven in [Een OME-merksjabloon wijzigen.](#modify-an-ome-branding-template)</span><span class="sxs-lookup"><span data-stu-id="1274d-176">Once you've created the template, you modify the template by using the Set-OMEConfiguration cmdlet as described in [Modify an OME branding template](#modify-an-ome-branding-template).</span></span> <span data-ttu-id="1274d-177">U kunt meerdere sjablonen maken.</span><span class="sxs-lookup"><span data-stu-id="1274d-177">You can create multiple templates.</span></span>

<span data-ttu-id="1274d-178">Een nieuwe sjabloon voor aangepaste huisstijl maken:</span><span class="sxs-lookup"><span data-stu-id="1274d-178">To create a new custom branding template:</span></span>

1. <span data-ttu-id="1274d-179">Als u een werk- of schoolaccount gebruikt met globale beheerdersmachtigingen in uw organisatie, start u een Windows PowerShell en maakt u verbinding met Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1274d-179">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="1274d-180">Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="1274d-180">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="1274d-181">Gebruik de [cmdlet Nieuw-OMEConfiguratie](/powershell/module/exchange/new-omeconfiguration) om een nieuwe sjabloon te maken.</span><span class="sxs-lookup"><span data-stu-id="1274d-181">Use the [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) cmdlet to create a new template.</span></span>

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   <span data-ttu-id="1274d-182">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="1274d-182">For example,</span></span>

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a><span data-ttu-id="1274d-183">De standaardsjabloon voor huisstijl retourneren naar de oorspronkelijke waarden</span><span class="sxs-lookup"><span data-stu-id="1274d-183">Return the default branding template to its original values</span></span>

<span data-ttu-id="1274d-184">Als u alle wijzigingen uit de standaardsjabloon wilt verwijderen, inclusief merkaanpassingen, en dergelijke, gaat u als volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="1274d-184">To remove all modifications from the default template, including brand customizations, and so on, complete these steps:</span></span>
  
1. <span data-ttu-id="1274d-185">Als u een werk- of schoolaccount gebruikt met globale beheerdersmachtigingen in uw organisatie, start u een Windows PowerShell en maakt u verbinding met Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1274d-185">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="1274d-186">Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="1274d-186">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="1274d-187">Gebruik de **cmdlet Set-OMEConfiguration** zoals beschreven in [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration).</span><span class="sxs-lookup"><span data-stu-id="1274d-187">Use the **Set-OMEConfiguration** cmdlet as described in [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration).</span></span> <span data-ttu-id="1274d-188">Als u de merkaanpassingen van uw organisatie wilt verwijderen uit de waarden DisclaimerTekst, E-mailtekst en PortalTekst, stelt u de waarde in op een lege `""` tekenreeks, .</span><span class="sxs-lookup"><span data-stu-id="1274d-188">To remove your organization's branded customizations from the DisclaimerText, EmailText, and PortalText values, set the value to an empty string, `""`.</span></span> <span data-ttu-id="1274d-189">Voor alle afbeeldingswaarden, zoals Logo, stelt u de waarde in op  `"$null"` .</span><span class="sxs-lookup"><span data-stu-id="1274d-189">For all image values, such as Logo, set the value to  `"$null"`.</span></span>

   <span data-ttu-id="1274d-190">In de volgende tabel wordt de standaardinstelling voor versleutelingsaanpassing beschreven.</span><span class="sxs-lookup"><span data-stu-id="1274d-190">The following table describes the encryption customization option defaults.</span></span>

   |<span data-ttu-id="1274d-191">Deze functie van de versleutelingservaring terugdraaien naar de standaardtekst en afbeelding</span><span class="sxs-lookup"><span data-stu-id="1274d-191">To revert this feature of the encryption experience back to the default text and image</span></span>|<span data-ttu-id="1274d-192">Deze opdrachten gebruiken</span><span class="sxs-lookup"><span data-stu-id="1274d-192">Use these commands</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="1274d-193">Standaardtekst die wordt geleverd met versleutelde e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="1274d-193">Default text that comes with encrypted email messages.</span></span>  <span data-ttu-id="1274d-194">De standaardtekst wordt weergegeven boven de instructies voor het weergeven van versleutelde berichten</span><span class="sxs-lookup"><span data-stu-id="1274d-194">The default text appears above the instructions for viewing encrypted messages</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> <span data-ttu-id="1274d-195">**Voorbeeld:**</span><span class="sxs-lookup"><span data-stu-id="1274d-195">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |<span data-ttu-id="1274d-196">Vrijwaringsverklaring in het e-mailbericht met het versleutelde bericht</span><span class="sxs-lookup"><span data-stu-id="1274d-196">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> <span data-ttu-id="1274d-197">**Voorbeeld:**</span><span class="sxs-lookup"><span data-stu-id="1274d-197">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |<span data-ttu-id="1274d-198">Tekst die boven aan de portal voor het weergeven van versleutelde e-mail wordt weergegeven</span><span class="sxs-lookup"><span data-stu-id="1274d-198">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> <span data-ttu-id="1274d-199">**Voorbeeld om terug te keren naar standaard:**</span><span class="sxs-lookup"><span data-stu-id="1274d-199">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |<span data-ttu-id="1274d-200">Logo</span><span class="sxs-lookup"><span data-stu-id="1274d-200">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> <span data-ttu-id="1274d-201">**Voorbeeld om terug te keren naar standaard:**</span><span class="sxs-lookup"><span data-stu-id="1274d-201">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |<span data-ttu-id="1274d-202">Achtergrondkleur</span><span class="sxs-lookup"><span data-stu-id="1274d-202">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> <span data-ttu-id="1274d-203">**Voorbeeld om terug te keren naar standaard:**</span><span class="sxs-lookup"><span data-stu-id="1274d-203">**Example reverting back to default:**</span></span> <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a><span data-ttu-id="1274d-204">Een aangepaste huisstijlsjabloon verwijderen (Geavanceerde berichtversleuteling)</span><span class="sxs-lookup"><span data-stu-id="1274d-204">Remove a custom branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="1274d-205">U kunt alleen merksjablonen verwijderen of verwijderen die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="1274d-205">You can only remove or delete branding templates that you've made.</span></span> <span data-ttu-id="1274d-206">U kunt de standaardsjabloon voor huisstijl niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="1274d-206">You can't remove the default branding template.</span></span>

<span data-ttu-id="1274d-207">Een aangepaste huisstijlsjabloon verwijderen:</span><span class="sxs-lookup"><span data-stu-id="1274d-207">To remove a custom branding template:</span></span>
  
1. <span data-ttu-id="1274d-208">Als u een werk- of schoolaccount gebruikt met globale beheerdersmachtigingen in uw organisatie, start u een Windows PowerShell en maakt u verbinding met Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1274d-208">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="1274d-209">Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="1274d-209">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="1274d-210">Gebruik de **cmdlet Remove-OMEConfiguration** als volgt:</span><span class="sxs-lookup"><span data-stu-id="1274d-210">Use the **Remove-OMEConfiguration** cmdlet as follows:</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   <span data-ttu-id="1274d-211">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="1274d-211">For example,</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   <span data-ttu-id="1274d-212">Zie [Remove-OMEConfiguration (Verwijderen-OMEConfiguration) voor meer informatie.](/powershell/module/exchange/remove-omeconfiguration)</span><span class="sxs-lookup"><span data-stu-id="1274d-212">For more information, see [Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration).</span></span>

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a><span data-ttu-id="1274d-213">Maak een Exchange e-mailstroomregel die uw aangepaste huisstijl op versleutelde e-mailberichten van toepassing is</span><span class="sxs-lookup"><span data-stu-id="1274d-213">Create an Exchange mail flow rule that applies your custom branding to encrypted emails</span></span>

<span data-ttu-id="1274d-214">Nadat u de standaardsjabloon hebt gewijzigd of nieuwe huisstijlsjablonen hebt gemaakt, kunt u Exchange regels voor e-mailstroom maken om uw aangepaste huisstijl toe te passen op basis van bepaalde voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="1274d-214">After you've either modified the default template or created new branding templates, you can create Exchange mail flow rules to apply your custom branding based on certain conditions.</span></span> <span data-ttu-id="1274d-215">Een dergelijke regel is in de volgende scenario's van toepassing op aangepaste huisstijl:</span><span class="sxs-lookup"><span data-stu-id="1274d-215">Such a rule will apply custom branding in the following scenarios:</span></span>

- <span data-ttu-id="1274d-216">Als de e-mail handmatig is versleuteld door de eindgebruiker met Outlook of Outlook op het web, voorheen Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="1274d-216">If the email was manually encrypted by the end user using Outlook or Outlook on the web, formerly Outlook Web App</span></span>

- <span data-ttu-id="1274d-217">Als de e-mail automatisch is versleuteld door een Exchange regel voor e-mailstroom of beleid voor preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="1274d-217">If the email was automatically encrypted by an Exchange mail flow rule or Data Loss Prevention policy</span></span>

<span data-ttu-id="1274d-218">Zie Regels voor e-mailstroom definiëren om e-mailberichten te versleutelen in Office 365 voor informatie over het maken van een Exchange [e-mailstroomregel](define-mail-flow-rules-to-encrypt-email.md)die versleuteling van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="1274d-218">For information on how to create an Exchange mail flow rule that applies encryption, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

1. <span data-ttu-id="1274d-219">Meld u in een webbrowser met behulp van een werk- of schoolaccount dat globale beheerdersmachtigingen is verleend, [aan bij Office 365.](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)</span><span class="sxs-lookup"><span data-stu-id="1274d-219">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="1274d-220">Kies de **tegel** Beheerder.</span><span class="sxs-lookup"><span data-stu-id="1274d-220">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="1274d-221">Kies in Microsoft 365 beheercentrum de optie **Beheercentra** \> **Exchange.**</span><span class="sxs-lookup"><span data-stu-id="1274d-221">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="1274d-222">Ga in het EAC naar **E-mailstroomregels** \>  en selecteer **Nieuw** nieuw pictogram Een nieuwe ![ regel ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **maken.**</span><span class="sxs-lookup"><span data-stu-id="1274d-222">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="1274d-223">Zie voor meer informatie over het gebruik van het EAC [Exchange beheercentrum in Exchange Online.](/exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="1274d-223">For more information about using the EAC, see [Exchange admin center in Exchange Online](/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="1274d-224">Typ **in Naam** een naam voor de regel, zoals Huisstijl voor verkoopafdeling.</span><span class="sxs-lookup"><span data-stu-id="1274d-224">In **Name**, type a name for the rule, such as Branding for sales department.</span></span>

6. <span data-ttu-id="1274d-225">Selecteer **in Deze regel toepassen als** de voorwaarde De afzender bevindt zich **binnen** de organisatie en andere voorwaarden die u wilt in de lijst met beschikbare voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="1274d-225">In **Apply this rule if**, select the condition **The sender is located inside the organization** and other conditions you want from the list of available conditions.</span></span> <span data-ttu-id="1274d-226">U kunt bijvoorbeeld een bepaalde huisstijlsjabloon toepassen op:</span><span class="sxs-lookup"><span data-stu-id="1274d-226">For example, you might want to apply a particular branding template to:</span></span>

   - <span data-ttu-id="1274d-227">Alle versleutelde e-mailberichten die zijn verzonden van leden van de financiële afdeling</span><span class="sxs-lookup"><span data-stu-id="1274d-227">All encrypted emails sent from members of the finance department</span></span>
   - <span data-ttu-id="1274d-228">Versleutelde e-mailberichten die zijn verzonden met een bepaald trefwoord, zoals 'Extern' of 'Partner'.</span><span class="sxs-lookup"><span data-stu-id="1274d-228">Encrypted emails sent with a certain keyword such as "External" or "Partner"</span></span>
   - <span data-ttu-id="1274d-229">Versleutelde e-mailberichten die naar een bepaald domein zijn verzonden</span><span class="sxs-lookup"><span data-stu-id="1274d-229">Encrypted emails sent to a particular domain</span></span>

7. <span data-ttu-id="1274d-230">Selecteer **in Ga als volgt** te werk en selecteer De **berichtbeveiliging** Aanpassen Aangepaste \> **huisstijl toepassen op OME-berichten.**</span><span class="sxs-lookup"><span data-stu-id="1274d-230">From **Do the following**, select **Modify the message security** \> **Apply custom branding to OME messages**.</span></span> <span data-ttu-id="1274d-231">Selecteer vervolgens in de vervolgkeuzekeuzepagina een huisstijlsjabloon.</span><span class="sxs-lookup"><span data-stu-id="1274d-231">Next, from the drop-down, select a branding template.</span></span>

8. <span data-ttu-id="1274d-232">(Optioneel) U kunt de regel voor de e-mailstroom zo configureren dat versleuteling en aangepaste huisstijl worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="1274d-232">(Optional) You can configure the mail flow rule to apply encryption and custom branding.</span></span> <span data-ttu-id="1274d-233">Selecteer **in Ga als volgt** te werk, selecteer De **berichtbeveiliging wijzigen** en kies vervolgens Office 365-berichtversleuteling en **rechtenbescherming toepassen.**</span><span class="sxs-lookup"><span data-stu-id="1274d-233">From **Do the following**, select **Modify the message security**, and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="1274d-234">Selecteer een RMS-sjabloon in de lijst, kies **Opslaan** en kies **ok.**</span><span class="sxs-lookup"><span data-stu-id="1274d-234">Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
   <span data-ttu-id="1274d-235">De lijst met sjablonen bevat standaardsjablonen en opties en eventuele aangepaste sjablonen die u maakt.</span><span class="sxs-lookup"><span data-stu-id="1274d-235">The list of templates includes default templates and options and any custom templates you create.</span></span> <span data-ttu-id="1274d-236">Als de lijst leeg is, moet u ervoor zorgen dat u Office 365-berichtversleuteling met de nieuwe mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="1274d-236">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities.</span></span> <span data-ttu-id="1274d-237">Zie Nieuwe functies voor Office 365-berichtversleuteling instellen voor [instructies.](set-up-new-message-encryption-capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="1274d-237">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="1274d-238">Zie Sjablonen configureren en beheren voor [Azure Information Protection](/information-protection/deploy-use/configure-policy-templates)voor meer informatie over de standaardsjablonen.</span><span class="sxs-lookup"><span data-stu-id="1274d-238">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="1274d-239">Zie Optie  Niet doorsturen voor e-mailberichten voor informatie over de optie Niet doorsturen. [](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="1274d-239">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="1274d-240">Zie Alleen **versleutelen** voor e-mailberichten voor informatie over de enige optie [voor versleutelen.](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="1274d-240">For information about the **encrypt only** option, see [Encrypt Only option for emails](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

   <span data-ttu-id="1274d-241">Kies **Actie toevoegen** als u een andere actie wilt opgeven.</span><span class="sxs-lookup"><span data-stu-id="1274d-241">Choose **add action** if you want to specify another action.</span></span>

## <a name="background-color-reference"></a><span data-ttu-id="1274d-242">Achtergrondkleurverwijzing</span><span class="sxs-lookup"><span data-stu-id="1274d-242">Background color reference</span></span>

<span data-ttu-id="1274d-243">De kleurnamen die u voor de achtergrondkleur kunt gebruiken, zijn beperkt.</span><span class="sxs-lookup"><span data-stu-id="1274d-243">The color names that you can use for the background color are limited.</span></span> <span data-ttu-id="1274d-244">In plaats van een kleurnaam kunt u een hexcodewaarde (#RRGGBB).</span><span class="sxs-lookup"><span data-stu-id="1274d-244">Instead of a color name, you can use a hex code value (#RRGGBB).</span></span> <span data-ttu-id="1274d-245">U kunt een hexcodewaarde gebruiken die overeenkomt met een kleurnaam of u kunt een aangepaste hex-codewaarde gebruiken.</span><span class="sxs-lookup"><span data-stu-id="1274d-245">You can use a hex code value that corresponds to a color name, or you can use a custom hex code value.</span></span> <span data-ttu-id="1274d-246">Zorg ervoor dat u de hexcodewaarde tussen aanhalingstekens (bijvoorbeeld) `"#f0f8ff"` omsluit.</span><span class="sxs-lookup"><span data-stu-id="1274d-246">Be sure to enclose the hex code value in quotation marks (for example, `"#f0f8ff"`).</span></span>

<span data-ttu-id="1274d-247">De beschikbare achtergrondkleurnamen en de bijbehorende hexcodewaarden worden in de volgende tabel beschreven.</span><span class="sxs-lookup"><span data-stu-id="1274d-247">The available background color names and their corresponding hex code values are described in the following table.</span></span>

|<span data-ttu-id="1274d-248">**Naam van kleur**</span><span class="sxs-lookup"><span data-stu-id="1274d-248">**Color name**</span></span>|<span data-ttu-id="1274d-249">**Kleurcode**</span><span class="sxs-lookup"><span data-stu-id="1274d-249">**Color code**</span></span>|
|---|---|
|`aliceblue`|<span data-ttu-id="1274d-250">#f0f8ff</span><span class="sxs-lookup"><span data-stu-id="1274d-250">#f0f8ff</span></span>|
|`antiquewhite`|<span data-ttu-id="1274d-251">#faebd7</span><span class="sxs-lookup"><span data-stu-id="1274d-251">#faebd7</span></span>|
|`aqua`|<span data-ttu-id="1274d-252">#00ffff</span><span class="sxs-lookup"><span data-stu-id="1274d-252">#00ffff</span></span>|
|`aquamarine`|<span data-ttu-id="1274d-253">#7fffd4</span><span class="sxs-lookup"><span data-stu-id="1274d-253">#7fffd4</span></span>|
|`azure`|<span data-ttu-id="1274d-254">#f0ffff</span><span class="sxs-lookup"><span data-stu-id="1274d-254">#f0ffff</span></span>|
|`beige`|<span data-ttu-id="1274d-255">#f5f5dc</span><span class="sxs-lookup"><span data-stu-id="1274d-255">#f5f5dc</span></span>|
|`bisque`|<span data-ttu-id="1274d-256">#ffe4c4</span><span class="sxs-lookup"><span data-stu-id="1274d-256">#ffe4c4</span></span>|
|`black`|<span data-ttu-id="1274d-257">#000000</span><span class="sxs-lookup"><span data-stu-id="1274d-257">#000000</span></span>|
|`blanchedalmond`|<span data-ttu-id="1274d-258">#ffebcd</span><span class="sxs-lookup"><span data-stu-id="1274d-258">#ffebcd</span></span>|
|`blue`|<span data-ttu-id="1274d-259">#0000ff</span><span class="sxs-lookup"><span data-stu-id="1274d-259">#0000ff</span></span>|
|`blueviolet`|<span data-ttu-id="1274d-260">#8a2be2</span><span class="sxs-lookup"><span data-stu-id="1274d-260">#8a2be2</span></span>|
|`brown`|<span data-ttu-id="1274d-261">#a52a2a</span><span class="sxs-lookup"><span data-stu-id="1274d-261">#a52a2a</span></span>|
|`burlywood`|<span data-ttu-id="1274d-262">#deb887</span><span class="sxs-lookup"><span data-stu-id="1274d-262">#deb887</span></span>|
|`cadetblue`|<span data-ttu-id="1274d-263">#5f9ea0</span><span class="sxs-lookup"><span data-stu-id="1274d-263">#5f9ea0</span></span>|
|`chartreuse`|<span data-ttu-id="1274d-264">#7fff00</span><span class="sxs-lookup"><span data-stu-id="1274d-264">#7fff00</span></span>|
|`chocolate`|<span data-ttu-id="1274d-265">#d2691e</span><span class="sxs-lookup"><span data-stu-id="1274d-265">#d2691e</span></span>|
|`coral`|<span data-ttu-id="1274d-266">#ff7f50</span><span class="sxs-lookup"><span data-stu-id="1274d-266">#ff7f50</span></span>|
|`cornflowerblue`|<span data-ttu-id="1274d-267">#6495ed</span><span class="sxs-lookup"><span data-stu-id="1274d-267">#6495ed</span></span>|
|`cornsilk`|<span data-ttu-id="1274d-268">#fff8dc</span><span class="sxs-lookup"><span data-stu-id="1274d-268">#fff8dc</span></span>|
|`crimson`|<span data-ttu-id="1274d-269">#dc143c</span><span class="sxs-lookup"><span data-stu-id="1274d-269">#dc143c</span></span>|
|`cyan`|<span data-ttu-id="1274d-270">#00ffff</span><span class="sxs-lookup"><span data-stu-id="1274d-270">#00ffff</span></span>|
|`darkblue`|<span data-ttu-id="1274d-271">#00008b</span><span class="sxs-lookup"><span data-stu-id="1274d-271">#00008b</span></span>|
|`darkcyan`|<span data-ttu-id="1274d-272">#008b8b</span><span class="sxs-lookup"><span data-stu-id="1274d-272">#008b8b</span></span>|
|`darkgoldenrod`|<span data-ttu-id="1274d-273">#b8860b</span><span class="sxs-lookup"><span data-stu-id="1274d-273">#b8860b</span></span>|
|`darkgray`|<span data-ttu-id="1274d-274">#a9a9a9</span><span class="sxs-lookup"><span data-stu-id="1274d-274">#a9a9a9</span></span>|
|`darkgreen`|<span data-ttu-id="1274d-275">#006400</span><span class="sxs-lookup"><span data-stu-id="1274d-275">#006400</span></span>|
|`darkkhaki`|<span data-ttu-id="1274d-276">#bdb76b</span><span class="sxs-lookup"><span data-stu-id="1274d-276">#bdb76b</span></span>|
|`darkmagenta`|<span data-ttu-id="1274d-277">#8b008b</span><span class="sxs-lookup"><span data-stu-id="1274d-277">#8b008b</span></span>|
|`darkolivegreen`|<span data-ttu-id="1274d-278">#556b2f</span><span class="sxs-lookup"><span data-stu-id="1274d-278">#556b2f</span></span>|
|`darkorange`|<span data-ttu-id="1274d-279">#ff8c00</span><span class="sxs-lookup"><span data-stu-id="1274d-279">#ff8c00</span></span>|
|`darkorchid`|<span data-ttu-id="1274d-280">#9932cc</span><span class="sxs-lookup"><span data-stu-id="1274d-280">#9932cc</span></span>|
|`darkred`|<span data-ttu-id="1274d-281">#8b0000</span><span class="sxs-lookup"><span data-stu-id="1274d-281">#8b0000</span></span>|
|`darksalmon`|<span data-ttu-id="1274d-282">#e9967a</span><span class="sxs-lookup"><span data-stu-id="1274d-282">#e9967a</span></span>|
|`darkseagreen`|<span data-ttu-id="1274d-283">#8fbc8f</span><span class="sxs-lookup"><span data-stu-id="1274d-283">#8fbc8f</span></span>|
|`darkslateblue`|<span data-ttu-id="1274d-284">#483d8b</span><span class="sxs-lookup"><span data-stu-id="1274d-284">#483d8b</span></span>|
|`darkslategray`|<span data-ttu-id="1274d-285">#2f4f4f</span><span class="sxs-lookup"><span data-stu-id="1274d-285">#2f4f4f</span></span>|
|`darkturquoise`|<span data-ttu-id="1274d-286">#00ced1</span><span class="sxs-lookup"><span data-stu-id="1274d-286">#00ced1</span></span>|
|`darkviolet`|<span data-ttu-id="1274d-287">#9400d3</span><span class="sxs-lookup"><span data-stu-id="1274d-287">#9400d3</span></span>|
|`deeppink`|<span data-ttu-id="1274d-288">#ff1493</span><span class="sxs-lookup"><span data-stu-id="1274d-288">#ff1493</span></span>|
|`deepskyblue`|<span data-ttu-id="1274d-289">#00bfff</span><span class="sxs-lookup"><span data-stu-id="1274d-289">#00bfff</span></span>|
|`dimgray`|<span data-ttu-id="1274d-290">#696969</span><span class="sxs-lookup"><span data-stu-id="1274d-290">#696969</span></span>|
|`dodgerblue`|<span data-ttu-id="1274d-291">#1e90ff</span><span class="sxs-lookup"><span data-stu-id="1274d-291">#1e90ff</span></span>|
|`firebrick`|<span data-ttu-id="1274d-292">#b22222</span><span class="sxs-lookup"><span data-stu-id="1274d-292">#b22222</span></span>|
|`floralwhite`|<span data-ttu-id="1274d-293">#fffaf0</span><span class="sxs-lookup"><span data-stu-id="1274d-293">#fffaf0</span></span>|
|`forestgreen`|<span data-ttu-id="1274d-294">#228b22</span><span class="sxs-lookup"><span data-stu-id="1274d-294">#228b22</span></span>|
|`fuchsia`|<span data-ttu-id="1274d-295">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="1274d-295">#ff00ff</span></span>|
|`gainsboro`|<span data-ttu-id="1274d-296">#dcdcdc</span><span class="sxs-lookup"><span data-stu-id="1274d-296">#dcdcdc</span></span>|
|`ghostwhite`|<span data-ttu-id="1274d-297">#f8f8ff</span><span class="sxs-lookup"><span data-stu-id="1274d-297">#f8f8ff</span></span>|
|`gold`|<span data-ttu-id="1274d-298">#ffd700</span><span class="sxs-lookup"><span data-stu-id="1274d-298">#ffd700</span></span>|
|`goldenrod`|<span data-ttu-id="1274d-299">#daa520</span><span class="sxs-lookup"><span data-stu-id="1274d-299">#daa520</span></span>|
|`gray`|<span data-ttu-id="1274d-300">#808080</span><span class="sxs-lookup"><span data-stu-id="1274d-300">#808080</span></span>|
|`green`|<span data-ttu-id="1274d-301">#008000</span><span class="sxs-lookup"><span data-stu-id="1274d-301">#008000</span></span>|
|`greenyellow`|<span data-ttu-id="1274d-302">#adff2f</span><span class="sxs-lookup"><span data-stu-id="1274d-302">#adff2f</span></span>|
|`honeydew`|<span data-ttu-id="1274d-303">#f0fff0</span><span class="sxs-lookup"><span data-stu-id="1274d-303">#f0fff0</span></span>|
|`hotpink`|<span data-ttu-id="1274d-304">#ff69b4</span><span class="sxs-lookup"><span data-stu-id="1274d-304">#ff69b4</span></span>|
|`indianred`|<span data-ttu-id="1274d-305">#cd5c5c</span><span class="sxs-lookup"><span data-stu-id="1274d-305">#cd5c5c</span></span>|
|`indigo`|<span data-ttu-id="1274d-306">#4b0082</span><span class="sxs-lookup"><span data-stu-id="1274d-306">#4b0082</span></span>|
|`ivory`|<span data-ttu-id="1274d-307">#fffff0</span><span class="sxs-lookup"><span data-stu-id="1274d-307">#fffff0</span></span>|
|`khaki`|<span data-ttu-id="1274d-308">#f0e68c</span><span class="sxs-lookup"><span data-stu-id="1274d-308">#f0e68c</span></span>|
|`lavender`|<span data-ttu-id="1274d-309">#e6e6fa</span><span class="sxs-lookup"><span data-stu-id="1274d-309">#e6e6fa</span></span>|
|`lavenderblush`|<span data-ttu-id="1274d-310">#fff0f5</span><span class="sxs-lookup"><span data-stu-id="1274d-310">#fff0f5</span></span>|
|`lawngreen`|<span data-ttu-id="1274d-311">#7cfc00</span><span class="sxs-lookup"><span data-stu-id="1274d-311">#7cfc00</span></span>|
|`lemonchiffon`|<span data-ttu-id="1274d-312">#fffacd</span><span class="sxs-lookup"><span data-stu-id="1274d-312">#fffacd</span></span>|
|`lightblue`|<span data-ttu-id="1274d-313">#add8e6</span><span class="sxs-lookup"><span data-stu-id="1274d-313">#add8e6</span></span>|
|`lightcoral`|<span data-ttu-id="1274d-314">#f08080</span><span class="sxs-lookup"><span data-stu-id="1274d-314">#f08080</span></span>|
|`lightcyan`|<span data-ttu-id="1274d-315">#e0ffff</span><span class="sxs-lookup"><span data-stu-id="1274d-315">#e0ffff</span></span>|
|`lightgoldenrodyellow`|<span data-ttu-id="1274d-316">#fafad2</span><span class="sxs-lookup"><span data-stu-id="1274d-316">#fafad2</span></span>|
|`lightgray`|<span data-ttu-id="1274d-317">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="1274d-317">#d3d3d3</span></span>|
|`lightgrey`|<span data-ttu-id="1274d-318">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="1274d-318">#d3d3d3</span></span>|
|`lightgreen`|<span data-ttu-id="1274d-319">#90ee90</span><span class="sxs-lookup"><span data-stu-id="1274d-319">#90ee90</span></span>|
|`lightpink`|<span data-ttu-id="1274d-320">#ffb6c1</span><span class="sxs-lookup"><span data-stu-id="1274d-320">#ffb6c1</span></span>|
|`lightsalmon`|<span data-ttu-id="1274d-321">#ffa07a</span><span class="sxs-lookup"><span data-stu-id="1274d-321">#ffa07a</span></span>|
|`lightseagreen`|<span data-ttu-id="1274d-322">#20b2aa</span><span class="sxs-lookup"><span data-stu-id="1274d-322">#20b2aa</span></span>|
|`lightskyblue`|<span data-ttu-id="1274d-323">#87cefa</span><span class="sxs-lookup"><span data-stu-id="1274d-323">#87cefa</span></span>|
|`lightslategray`|<span data-ttu-id="1274d-324">#778899</span><span class="sxs-lookup"><span data-stu-id="1274d-324">#778899</span></span>|
|`lightsteelblue`|<span data-ttu-id="1274d-325">#b0c4de</span><span class="sxs-lookup"><span data-stu-id="1274d-325">#b0c4de</span></span>|
|`lightyellow`|<span data-ttu-id="1274d-326">#ffffe0</span><span class="sxs-lookup"><span data-stu-id="1274d-326">#ffffe0</span></span>|
|`lime`|<span data-ttu-id="1274d-327">#00ff00</span><span class="sxs-lookup"><span data-stu-id="1274d-327">#00ff00</span></span>|
|`limegreen`|<span data-ttu-id="1274d-328">#32cd32</span><span class="sxs-lookup"><span data-stu-id="1274d-328">#32cd32</span></span>|
|`linen`|<span data-ttu-id="1274d-329">#faf0e6</span><span class="sxs-lookup"><span data-stu-id="1274d-329">#faf0e6</span></span>|
|`magenta`|<span data-ttu-id="1274d-330">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="1274d-330">#ff00ff</span></span>|
|`maroon`|<span data-ttu-id="1274d-331">#800000</span><span class="sxs-lookup"><span data-stu-id="1274d-331">#800000</span></span>|
|`mediumaquamarine`|<span data-ttu-id="1274d-332">#66cdaa</span><span class="sxs-lookup"><span data-stu-id="1274d-332">#66cdaa</span></span>|
|`mediumblue`|<span data-ttu-id="1274d-333">#0000cd</span><span class="sxs-lookup"><span data-stu-id="1274d-333">#0000cd</span></span>|
|`mediumorchid`|<span data-ttu-id="1274d-334">#ba55d3</span><span class="sxs-lookup"><span data-stu-id="1274d-334">#ba55d3</span></span>|
|`mediumpurple`|<span data-ttu-id="1274d-335">#9370db</span><span class="sxs-lookup"><span data-stu-id="1274d-335">#9370db</span></span>|
|`mediumseagreen`|<span data-ttu-id="1274d-336">#3cb371</span><span class="sxs-lookup"><span data-stu-id="1274d-336">#3cb371</span></span>|
|`mediumslateblue`|<span data-ttu-id="1274d-337">#7b68ee</span><span class="sxs-lookup"><span data-stu-id="1274d-337">#7b68ee</span></span>|
|`mediumspringgreen`|<span data-ttu-id="1274d-338">#00fa9a</span><span class="sxs-lookup"><span data-stu-id="1274d-338">#00fa9a</span></span>|
|`mediumturquoise`|<span data-ttu-id="1274d-339">#48d1cc</span><span class="sxs-lookup"><span data-stu-id="1274d-339">#48d1cc</span></span>|
|`mediumvioletred`|<span data-ttu-id="1274d-340">#c71585</span><span class="sxs-lookup"><span data-stu-id="1274d-340">#c71585</span></span>|
|`midnightblue`|<span data-ttu-id="1274d-341">#191970</span><span class="sxs-lookup"><span data-stu-id="1274d-341">#191970</span></span>|
|`mintcream`|<span data-ttu-id="1274d-342">#f5fffa</span><span class="sxs-lookup"><span data-stu-id="1274d-342">#f5fffa</span></span>|
|`mistyrose`|<span data-ttu-id="1274d-343">#ffe4e1</span><span class="sxs-lookup"><span data-stu-id="1274d-343">#ffe4e1</span></span>|
|`moccasin`|<span data-ttu-id="1274d-344">#ffe4b5</span><span class="sxs-lookup"><span data-stu-id="1274d-344">#ffe4b5</span></span>|
|`navajowhite`|<span data-ttu-id="1274d-345">#ffdead</span><span class="sxs-lookup"><span data-stu-id="1274d-345">#ffdead</span></span>|
|`navy`|<span data-ttu-id="1274d-346">#000080</span><span class="sxs-lookup"><span data-stu-id="1274d-346">#000080</span></span>|
|`oldlace`|<span data-ttu-id="1274d-347">#fdf5e6</span><span class="sxs-lookup"><span data-stu-id="1274d-347">#fdf5e6</span></span>|
|`olive`|<span data-ttu-id="1274d-348">#808000</span><span class="sxs-lookup"><span data-stu-id="1274d-348">#808000</span></span>|
|`olivedrab`|<span data-ttu-id="1274d-349">#6b8e23</span><span class="sxs-lookup"><span data-stu-id="1274d-349">#6b8e23</span></span>|
|`orange`|<span data-ttu-id="1274d-350">#ffa500</span><span class="sxs-lookup"><span data-stu-id="1274d-350">#ffa500</span></span>|
|`orangered`|<span data-ttu-id="1274d-351">#ff4500</span><span class="sxs-lookup"><span data-stu-id="1274d-351">#ff4500</span></span>|
|`orchid`|<span data-ttu-id="1274d-352">#da70d6</span><span class="sxs-lookup"><span data-stu-id="1274d-352">#da70d6</span></span>|
|`palegoldenrod`|<span data-ttu-id="1274d-353">#eee8aa</span><span class="sxs-lookup"><span data-stu-id="1274d-353">#eee8aa</span></span>|
|`palegreen`|<span data-ttu-id="1274d-354">#98fb98</span><span class="sxs-lookup"><span data-stu-id="1274d-354">#98fb98</span></span>|
|`paleturquoise`|<span data-ttu-id="1274d-355">#afeeee</span><span class="sxs-lookup"><span data-stu-id="1274d-355">#afeeee</span></span>|
|`palevioletred`|<span data-ttu-id="1274d-356">#db7093</span><span class="sxs-lookup"><span data-stu-id="1274d-356">#db7093</span></span>|
|`papayawhip`|<span data-ttu-id="1274d-357">#ffefd5</span><span class="sxs-lookup"><span data-stu-id="1274d-357">#ffefd5</span></span>|
|`peachpuff`|<span data-ttu-id="1274d-358">#ffdab9</span><span class="sxs-lookup"><span data-stu-id="1274d-358">#ffdab9</span></span>|
|`peru`|<span data-ttu-id="1274d-359">#cd853f</span><span class="sxs-lookup"><span data-stu-id="1274d-359">#cd853f</span></span>|
|`pink`|<span data-ttu-id="1274d-360">#ffc0cb</span><span class="sxs-lookup"><span data-stu-id="1274d-360">#ffc0cb</span></span>|
|`plum`|<span data-ttu-id="1274d-361">#dda0dd</span><span class="sxs-lookup"><span data-stu-id="1274d-361">#dda0dd</span></span>|
|`powderblue`|<span data-ttu-id="1274d-362">#b0e0e6</span><span class="sxs-lookup"><span data-stu-id="1274d-362">#b0e0e6</span></span>|
|`purple`|<span data-ttu-id="1274d-363">#800080</span><span class="sxs-lookup"><span data-stu-id="1274d-363">#800080</span></span>|
|`red`|<span data-ttu-id="1274d-364">#ff0000</span><span class="sxs-lookup"><span data-stu-id="1274d-364">#ff0000</span></span>|
|`rosybrown`|<span data-ttu-id="1274d-365">#bc8f8f</span><span class="sxs-lookup"><span data-stu-id="1274d-365">#bc8f8f</span></span>|
|`royalblue`|<span data-ttu-id="1274d-366">#4169e1</span><span class="sxs-lookup"><span data-stu-id="1274d-366">#4169e1</span></span>|
|`saddlebrown`|<span data-ttu-id="1274d-367">#8b4513</span><span class="sxs-lookup"><span data-stu-id="1274d-367">#8b4513</span></span>|
|`salmon`|<span data-ttu-id="1274d-368">#fa8072</span><span class="sxs-lookup"><span data-stu-id="1274d-368">#fa8072</span></span>|
|`sandybrown`|<span data-ttu-id="1274d-369">#f4a460</span><span class="sxs-lookup"><span data-stu-id="1274d-369">#f4a460</span></span>|
|`seagreen`|<span data-ttu-id="1274d-370">#00ff00</span><span class="sxs-lookup"><span data-stu-id="1274d-370">#00ff00</span></span>|
|`seashell`|<span data-ttu-id="1274d-371">#fff5ee</span><span class="sxs-lookup"><span data-stu-id="1274d-371">#fff5ee</span></span>|
|`sienna`|<span data-ttu-id="1274d-372">#a0522d</span><span class="sxs-lookup"><span data-stu-id="1274d-372">#a0522d</span></span>|
|`silver`|<span data-ttu-id="1274d-373">#c0c0c0</span><span class="sxs-lookup"><span data-stu-id="1274d-373">#c0c0c0</span></span>|
|`skyblue`|<span data-ttu-id="1274d-374">#87ceeb</span><span class="sxs-lookup"><span data-stu-id="1274d-374">#87ceeb</span></span>|
|`slateblue`|<span data-ttu-id="1274d-375">#6a5acd</span><span class="sxs-lookup"><span data-stu-id="1274d-375">#6a5acd</span></span>|
|`slategray`|<span data-ttu-id="1274d-376">#708090</span><span class="sxs-lookup"><span data-stu-id="1274d-376">#708090</span></span>|
|`snow`|<span data-ttu-id="1274d-377">#fffafa</span><span class="sxs-lookup"><span data-stu-id="1274d-377">#fffafa</span></span>|
|`springgreen`|<span data-ttu-id="1274d-378">#00ff7f</span><span class="sxs-lookup"><span data-stu-id="1274d-378">#00ff7f</span></span>|
|`steelblue`|<span data-ttu-id="1274d-379">#4682b4</span><span class="sxs-lookup"><span data-stu-id="1274d-379">#4682b4</span></span>|
|`tan`|<span data-ttu-id="1274d-380">#d2b48c</span><span class="sxs-lookup"><span data-stu-id="1274d-380">#d2b48c</span></span>|
|`teal`|<span data-ttu-id="1274d-381">#008080</span><span class="sxs-lookup"><span data-stu-id="1274d-381">#008080</span></span>|
|`thistle`|<span data-ttu-id="1274d-382">#d8bfd8</span><span class="sxs-lookup"><span data-stu-id="1274d-382">#d8bfd8</span></span>|
|`tomato`|<span data-ttu-id="1274d-383">#ff6347</span><span class="sxs-lookup"><span data-stu-id="1274d-383">#ff6347</span></span>|
|`turquoise`|<span data-ttu-id="1274d-384">#40e0d0</span><span class="sxs-lookup"><span data-stu-id="1274d-384">#40e0d0</span></span>|
|`violet`|<span data-ttu-id="1274d-385">#ee82ee</span><span class="sxs-lookup"><span data-stu-id="1274d-385">#ee82ee</span></span>|
|`wheat`|<span data-ttu-id="1274d-386">#f5deb3</span><span class="sxs-lookup"><span data-stu-id="1274d-386">#f5deb3</span></span>|
|`white`|<span data-ttu-id="1274d-387">#ffffff</span><span class="sxs-lookup"><span data-stu-id="1274d-387">#ffffff</span></span>|
|`whitesmoke`|<span data-ttu-id="1274d-388">#f5f5f5</span><span class="sxs-lookup"><span data-stu-id="1274d-388">#f5f5f5</span></span>|
|`yellow`|<span data-ttu-id="1274d-389">#ffff00</span><span class="sxs-lookup"><span data-stu-id="1274d-389">#ffff00</span></span>|
|`yellowgreen`|<span data-ttu-id="1274d-390">#9acd32</span><span class="sxs-lookup"><span data-stu-id="1274d-390">#9acd32</span></span>|