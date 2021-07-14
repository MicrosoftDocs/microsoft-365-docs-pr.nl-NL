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
ms.openlocfilehash: 95320e9f268f19cedd993efe4fa0e68fd75af125
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430730"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a><span data-ttu-id="e6b39-103">Het merk van uw organisatie toevoegen aan uw Microsoft 365 berichtenversleuteling voor bedrijven</span><span class="sxs-lookup"><span data-stu-id="e6b39-103">Add your organization's brand to your Microsoft 365 for business Message Encryption encrypted messages</span></span>

<span data-ttu-id="e6b39-104">U kunt de huisstijl van uw bedrijf toepassen om het uiterlijk van de e-mailberichten van uw organisatie en de versleutelingsportal aan te passen.</span><span class="sxs-lookup"><span data-stu-id="e6b39-104">You can apply your company branding to customize the look of your organization's email messages and the encryption portal.</span></span> <span data-ttu-id="e6b39-105">U moet globale beheerdersmachtigingen toepassen op uw werk- of schoolaccount voordat u aan de slag kunt.</span><span class="sxs-lookup"><span data-stu-id="e6b39-105">You'll need to apply global administrator permissions to your work or school account before you can get started.</span></span> <span data-ttu-id="e6b39-106">Wanneer u deze machtigingen hebt, gebruikt u de Get-OMEConfiguration en Set-OMEConfiguration Windows PowerShell cmdlets om deze onderdelen van versleutelde e-mailberichten aan te passen:</span><span class="sxs-lookup"><span data-stu-id="e6b39-106">Once you have these permissions, use the Get-OMEConfiguration and Set-OMEConfiguration Windows PowerShell cmdlets to customize these parts of encrypted email messages:</span></span>
  
- <span data-ttu-id="e6b39-107">Inleidende tekst</span><span class="sxs-lookup"><span data-stu-id="e6b39-107">Introductory text</span></span>

- <span data-ttu-id="e6b39-108">Vrijwaringstekst</span><span class="sxs-lookup"><span data-stu-id="e6b39-108">Disclaimer text</span></span>

- <span data-ttu-id="e6b39-109">URL voor de privacyverklaring van uw organisatie</span><span class="sxs-lookup"><span data-stu-id="e6b39-109">URL for Your organization's privacy statement</span></span>

- <span data-ttu-id="e6b39-110">Tekst in de OME-portal</span><span class="sxs-lookup"><span data-stu-id="e6b39-110">Text in the OME portal</span></span>

- <span data-ttu-id="e6b39-111">Logo dat wordt weergegeven in het e-mailbericht en de OME-portal, of dat u helemaal geen logo wilt gebruiken</span><span class="sxs-lookup"><span data-stu-id="e6b39-111">Logo that appears in the email message and OME portal, or whether to use a logo at all</span></span>

- <span data-ttu-id="e6b39-112">Achtergrondkleur in het e-mailbericht en de OME-portal</span><span class="sxs-lookup"><span data-stu-id="e6b39-112">Background color in the email message and OME portal</span></span>

<span data-ttu-id="e6b39-113">U kunt ook op elk moment terugkeren naar het standaard-uiterlijk.</span><span class="sxs-lookup"><span data-stu-id="e6b39-113">You can also revert back to the default look and feel at any time.</span></span>

<span data-ttu-id="e6b39-114">Als u meer controle wilt, gebruikt u Office 365 Advanced Message Encryption om meerdere sjablonen te maken voor versleutelde e-mailberichten die afkomstig zijn van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="e6b39-114">If you'd like more control, use Office 365 Advanced Message Encryption to create multiple templates for encrypted emails originating from your organization.</span></span> <span data-ttu-id="e6b39-115">Gebruik deze sjablonen om delen van de eindgebruikerservaring te beheren.</span><span class="sxs-lookup"><span data-stu-id="e6b39-115">Use these templates to control parts of the end-user experience.</span></span> <span data-ttu-id="e6b39-116">Geef bijvoorbeeld op of geadresseerden Google, Yahoo en Microsoft-accounts kunnen gebruiken om zich aan te melden bij de versleutelingsportal.</span><span class="sxs-lookup"><span data-stu-id="e6b39-116">For example, specify whether recipients can use Google, Yahoo, and Microsoft Accounts to sign in to the encryption portal.</span></span> <span data-ttu-id="e6b39-117">Gebruik sjablonen om aan verschillende gebruiksgevallen te voldoen, zoals:</span><span class="sxs-lookup"><span data-stu-id="e6b39-117">Use templates to fulfill several use cases, such as:</span></span>

- <span data-ttu-id="e6b39-118">Afzonderlijke afdelingen, zoals Financiën, Verkoop, en dergelijke.</span><span class="sxs-lookup"><span data-stu-id="e6b39-118">Individual departments, such as Finance, Sales, and so on.</span></span>

- <span data-ttu-id="e6b39-119">Verschillende producten</span><span class="sxs-lookup"><span data-stu-id="e6b39-119">Different products</span></span>

- <span data-ttu-id="e6b39-120">Verschillende geografische regio's of landen</span><span class="sxs-lookup"><span data-stu-id="e6b39-120">Different geographical regions or countries</span></span>

- <span data-ttu-id="e6b39-121">Of u wilt toestaan dat e-mailberichten worden ingetrokken</span><span class="sxs-lookup"><span data-stu-id="e6b39-121">Whether you want to allow emails to be revoked</span></span>

- <span data-ttu-id="e6b39-122">Of u wilt dat e-mailberichten die naar externe geadresseerden worden verzonden, na een bepaald aantal dagen verlopen.</span><span class="sxs-lookup"><span data-stu-id="e6b39-122">Whether you want emails sent to external recipients to expire after a specified number of days.</span></span>

<span data-ttu-id="e6b39-123">Nadat u de sjablonen hebt gemaakt, kunt u deze toepassen op versleutelde e-mailberichten met behulp van Exchange regels voor e-mailstroom.</span><span class="sxs-lookup"><span data-stu-id="e6b39-123">Once you've created the templates, you can apply them to encrypted emails by using Exchange mail flow rules.</span></span> <span data-ttu-id="e6b39-124">Als u een Office 365 Advanced Message Encryption, kunt u alle e-mailberichten die u hebt gebrandmerkt, intrekken met behulp van deze sjablonen.</span><span class="sxs-lookup"><span data-stu-id="e6b39-124">If you have Office 365 Advanced Message Encryption, you can revoke any email that you've branded by using these templates.</span></span>

## <a name="work-with-ome-branding-templates"></a><span data-ttu-id="e6b39-125">Werken met OME-huisstijlsjablonen</span><span class="sxs-lookup"><span data-stu-id="e6b39-125">Work with OME branding templates</span></span>

<span data-ttu-id="e6b39-126">U kunt verschillende functies in een huisstijlsjabloon wijzigen.</span><span class="sxs-lookup"><span data-stu-id="e6b39-126">You can modify several features within a branding template.</span></span> <span data-ttu-id="e6b39-127">U kunt de standaardsjabloon wijzigen, maar niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="e6b39-127">You can modify, but not remove, the default template.</span></span> <span data-ttu-id="e6b39-128">Als u geavanceerde berichtversleuteling hebt, kunt u ook aangepaste sjablonen maken, wijzigen en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="e6b39-128">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span> <span data-ttu-id="e6b39-129">Gebruik Windows PowerShell om met één huisstijlsjabloon tegelijk te werken.</span><span class="sxs-lookup"><span data-stu-id="e6b39-129">Use Windows PowerShell to work with one branding template at a time.</span></span>

- <span data-ttu-id="e6b39-130">[Set-OMEConfiguration-](/powershell/module/exchange/set-omeconfiguration) Wijzig de standaardbrandingsjabloon of een aangepaste huisstijlsjabloon die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="e6b39-130">[Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) - Modify the default branding template or a custom branding template that you created.</span></span>
- <span data-ttu-id="e6b39-131">[New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) - Maak een nieuwe huisstijlsjabloon, alleen Geavanceerde berichtversleuteling.</span><span class="sxs-lookup"><span data-stu-id="e6b39-131">[New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) - Create a new branding template, Advanced Message Encryption only.</span></span>
- <span data-ttu-id="e6b39-132">[Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration) - Verwijder een aangepaste huisstijlsjabloon, alleen Geavanceerde berichtversleuteling.</span><span class="sxs-lookup"><span data-stu-id="e6b39-132">[Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration) - Remove a custom branding template, Advanced Message Encryption only.</span></span> <span data-ttu-id="e6b39-133">U kunt de standaardsjabloon voor huisstijl niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="e6b39-133">You can't delete the default branding template.</span></span>
  
## <a name="modify-an-ome-branding-template"></a><span data-ttu-id="e6b39-134">Een OME-huisstijlsjabloon wijzigen</span><span class="sxs-lookup"><span data-stu-id="e6b39-134">Modify an OME branding template</span></span>

<span data-ttu-id="e6b39-135">Gebruik Windows PowerShell om één huisstijlsjabloon tegelijk te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="e6b39-135">Use Windows PowerShell to modify one branding template at a time.</span></span> <span data-ttu-id="e6b39-136">Als u geavanceerde berichtversleuteling hebt, kunt u ook aangepaste sjablonen maken, wijzigen en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="e6b39-136">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span>

1. <span data-ttu-id="e6b39-137">Als u een werk- of schoolaccount gebruikt met globale beheerdersmachtigingen in uw organisatie, start u een Windows PowerShell en maakt u verbinding met Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e6b39-137">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e6b39-138">Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="e6b39-138">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="e6b39-139">Gebruik de Set-OMEConfiguration cmdlet zoals beschreven in [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration) of gebruik de volgende afbeelding en tabel voor richtlijnen.</span><span class="sxs-lookup"><span data-stu-id="e6b39-139">Use the Set-OMEConfiguration cmdlet as described in [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration) or use the following graphic and table for guidance.</span></span>

![Aanpasbare e-mailonderdelen](../media/ome-template-breakout.png)

|<span data-ttu-id="e6b39-141">**Deze functie van de versleutelingservaring aanpassen**</span><span class="sxs-lookup"><span data-stu-id="e6b39-141">**To customize this feature of the encryption experience**</span></span>|<span data-ttu-id="e6b39-142">**Deze opdrachten gebruiken**</span><span class="sxs-lookup"><span data-stu-id="e6b39-142">**Use these commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e6b39-143">Achtergrondkleur</span><span class="sxs-lookup"><span data-stu-id="e6b39-143">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> <span data-ttu-id="e6b39-144">**Voorbeeld:**</span><span class="sxs-lookup"><span data-stu-id="e6b39-144">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> <span data-ttu-id="e6b39-145">Zie de sectie Achtergrondkleuren [](#background-color-reference) verder in dit artikel voor meer informatie over achtergrondkleuren.</span><span class="sxs-lookup"><span data-stu-id="e6b39-145">For more information about background colors, see the [Background colors](#background-color-reference) section later in this article.</span></span>|
|<span data-ttu-id="e6b39-146">Logo</span><span class="sxs-lookup"><span data-stu-id="e6b39-146">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> <span data-ttu-id="e6b39-147">**Voorbeeld:**</span><span class="sxs-lookup"><span data-stu-id="e6b39-147">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> <span data-ttu-id="e6b39-148">Ondersteunde bestandsindelingen: .png, .jpg, .bmp of .tiff</span><span class="sxs-lookup"><span data-stu-id="e6b39-148">Supported file formats: .png, .jpg, .bmp, or .tiff</span></span>  <br/> <span data-ttu-id="e6b39-149">Optimale grootte van het logobestand: minder dan 40 KB</span><span class="sxs-lookup"><span data-stu-id="e6b39-149">Optimal size of logo file: less than 40 KB</span></span>  <br/> <span data-ttu-id="e6b39-150">Optimale grootte van de afbeelding van het logo: 170x70 pixels.</span><span class="sxs-lookup"><span data-stu-id="e6b39-150">Optimal size of logo image: 170x70 pixels.</span></span> <span data-ttu-id="e6b39-151">Als de afbeelding deze dimensies overschrijdt, wordt het logo voor weergave in de portal door de service van het 1000-jaar-10-2017-2019-2019-2019-2010-2019-</span><span class="sxs-lookup"><span data-stu-id="e6b39-151">If your image exceeds these dimensions, the service resizes your logo for display in the portal.</span></span> <span data-ttu-id="e6b39-152">De service wijzigt het afbeeldingsbestand zelf niet.</span><span class="sxs-lookup"><span data-stu-id="e6b39-152">The service doesn't modify the graphic file itself.</span></span> <span data-ttu-id="e6b39-153">Gebruik de optimale grootte voor het beste resultaat.</span><span class="sxs-lookup"><span data-stu-id="e6b39-153">For best results, use the optimal size.</span></span>|
|<span data-ttu-id="e6b39-154">Tekst naast de naam en het e-mailadres van de afzender</span><span class="sxs-lookup"><span data-stu-id="e6b39-154">Text next to the sender's name and email address</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> <span data-ttu-id="e6b39-155">**Voorbeeld:**</span><span class="sxs-lookup"><span data-stu-id="e6b39-155">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|<span data-ttu-id="e6b39-156">Tekst die wordt weergegeven op de knop Bericht lezen</span><span class="sxs-lookup"><span data-stu-id="e6b39-156">Text that appears on the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> <span data-ttu-id="e6b39-157">**Voorbeeld:**</span><span class="sxs-lookup"><span data-stu-id="e6b39-157">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|<span data-ttu-id="e6b39-158">Tekst die wordt weergegeven onder de knop Bericht lezen</span><span class="sxs-lookup"><span data-stu-id="e6b39-158">Text that appears below the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> <span data-ttu-id="e6b39-159">**Voorbeeld:**</span><span class="sxs-lookup"><span data-stu-id="e6b39-159">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|<span data-ttu-id="e6b39-160">URL voor de koppeling Privacyverklaring</span><span class="sxs-lookup"><span data-stu-id="e6b39-160">URL for the Privacy Statement link</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> <span data-ttu-id="e6b39-161">**Voorbeeld:**</span><span class="sxs-lookup"><span data-stu-id="e6b39-161">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|<span data-ttu-id="e6b39-162">Vrijwaringsverklaring in het e-mailbericht met het versleutelde bericht</span><span class="sxs-lookup"><span data-stu-id="e6b39-162">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> <span data-ttu-id="e6b39-163">**Voorbeeld:**</span><span class="sxs-lookup"><span data-stu-id="e6b39-163">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|<span data-ttu-id="e6b39-164">Tekst die boven aan de portal voor het weergeven van versleutelde e-mail wordt weergegeven</span><span class="sxs-lookup"><span data-stu-id="e6b39-164">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> <span data-ttu-id="e6b39-165">**Voorbeeld:**</span><span class="sxs-lookup"><span data-stu-id="e6b39-165">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|<span data-ttu-id="e6b39-166">Verificatie in- of uitschakelen met een een time pass-code voor deze aangepaste sjabloon</span><span class="sxs-lookup"><span data-stu-id="e6b39-166">To enable or disable authentication with a one-time pass code for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> <span data-ttu-id="e6b39-167">**Voorbeelden:**</span><span class="sxs-lookup"><span data-stu-id="e6b39-167">**Examples:**</span></span> <br/><span data-ttu-id="e6b39-168">Een een time passcodes inschakelen voor deze aangepaste sjabloon</span><span class="sxs-lookup"><span data-stu-id="e6b39-168">To enable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> <span data-ttu-id="e6b39-169">Een een time passcodes uitschakelen voor deze aangepaste sjabloon</span><span class="sxs-lookup"><span data-stu-id="e6b39-169">To disable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|<span data-ttu-id="e6b39-170">Verificatie met Microsoft-, Google- of Yahoo-identiteiten in- of uitschakelen voor deze aangepaste sjabloon</span><span class="sxs-lookup"><span data-stu-id="e6b39-170">To enable or disable authentication with Microsoft, Google, or Yahoo identities for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> <span data-ttu-id="e6b39-171">**Voorbeelden:**</span><span class="sxs-lookup"><span data-stu-id="e6b39-171">**Examples:**</span></span> <br/><span data-ttu-id="e6b39-172">Sociale ID's inschakelen voor deze aangepaste sjabloon</span><span class="sxs-lookup"><span data-stu-id="e6b39-172">To enable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> <span data-ttu-id="e6b39-173">Sociale ID's uitschakelen voor deze aangepaste sjabloon</span><span class="sxs-lookup"><span data-stu-id="e6b39-173">To disable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a><span data-ttu-id="e6b39-174">Een OME-huisstijlsjabloon maken (Geavanceerde berichtversleuteling)</span><span class="sxs-lookup"><span data-stu-id="e6b39-174">Create an OME branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="e6b39-175">Als u een Office 365 Advanced Message Encryption, kunt u aangepaste huisstijlsjablonen voor uw organisatie maken met de cmdlet [New-OMEConfiguration.](/powershell/module/exchange/new-omeconfiguration)</span><span class="sxs-lookup"><span data-stu-id="e6b39-175">If you have Office 365 Advanced Message Encryption, you can create custom branding templates for your organization by using the [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) cmdlet.</span></span> <span data-ttu-id="e6b39-176">Nadat u de sjabloon hebt gemaakt, wijzigt u de sjabloon met de Set-OMEConfiguration cmdlet zoals beschreven in [Een OME-merksjabloon wijzigen.](#modify-an-ome-branding-template)</span><span class="sxs-lookup"><span data-stu-id="e6b39-176">Once you've created the template, you modify the template by using the Set-OMEConfiguration cmdlet as described in [Modify an OME branding template](#modify-an-ome-branding-template).</span></span> <span data-ttu-id="e6b39-177">U kunt meerdere sjablonen maken.</span><span class="sxs-lookup"><span data-stu-id="e6b39-177">You can create multiple templates.</span></span>

<span data-ttu-id="e6b39-178">Een nieuwe sjabloon voor aangepaste huisstijl maken:</span><span class="sxs-lookup"><span data-stu-id="e6b39-178">To create a new custom branding template:</span></span>

1. <span data-ttu-id="e6b39-179">Als u een werk- of schoolaccount gebruikt met globale beheerdersmachtigingen in uw organisatie, start u een Windows PowerShell en maakt u verbinding met Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e6b39-179">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e6b39-180">Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="e6b39-180">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="e6b39-181">Gebruik de [cmdlet Nieuw-OMEConfiguratie](/powershell/module/exchange/new-omeconfiguration) om een nieuwe sjabloon te maken.</span><span class="sxs-lookup"><span data-stu-id="e6b39-181">Use the [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) cmdlet to create a new template.</span></span>

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   <span data-ttu-id="e6b39-182">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="e6b39-182">For example,</span></span>

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a><span data-ttu-id="e6b39-183">De standaardsjabloon voor huisstijl retourneren naar de oorspronkelijke waarden</span><span class="sxs-lookup"><span data-stu-id="e6b39-183">Return the default branding template to its original values</span></span>

<span data-ttu-id="e6b39-184">Als u alle wijzigingen uit de standaardsjabloon wilt verwijderen, inclusief merkaanpassingen, en dergelijke, gaat u als volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="e6b39-184">To remove all modifications from the default template, including brand customizations, and so on, complete these steps:</span></span>
  
1. <span data-ttu-id="e6b39-185">Als u een werk- of schoolaccount gebruikt met globale beheerdersmachtigingen in uw organisatie, start u een Windows PowerShell en maakt u verbinding met Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e6b39-185">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e6b39-186">Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="e6b39-186">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="e6b39-187">Gebruik de **cmdlet Set-OMEConfiguration** zoals beschreven in [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration).</span><span class="sxs-lookup"><span data-stu-id="e6b39-187">Use the **Set-OMEConfiguration** cmdlet as described in [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration).</span></span> <span data-ttu-id="e6b39-188">Als u de merkaanpassingen van uw organisatie wilt verwijderen uit de waarden DisclaimerTekst, E-mailtekst en PortalTekst, stelt u de waarde in op een lege `""` tekenreeks, .</span><span class="sxs-lookup"><span data-stu-id="e6b39-188">To remove your organization's branded customizations from the DisclaimerText, EmailText, and PortalText values, set the value to an empty string, `""`.</span></span> <span data-ttu-id="e6b39-189">Voor alle afbeeldingswaarden, zoals Logo, stelt u de waarde in op  `"$null"` .</span><span class="sxs-lookup"><span data-stu-id="e6b39-189">For all image values, such as Logo, set the value to  `"$null"`.</span></span>

   <span data-ttu-id="e6b39-190">In de volgende tabel wordt de standaardinstelling voor versleutelingsaanpassing beschreven.</span><span class="sxs-lookup"><span data-stu-id="e6b39-190">The following table describes the encryption customization option defaults.</span></span>

   |<span data-ttu-id="e6b39-191">Deze functie van de versleutelingservaring terugdraaien naar de standaardtekst en afbeelding</span><span class="sxs-lookup"><span data-stu-id="e6b39-191">To revert this feature of the encryption experience back to the default text and image</span></span>|<span data-ttu-id="e6b39-192">Deze opdrachten gebruiken</span><span class="sxs-lookup"><span data-stu-id="e6b39-192">Use these commands</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="e6b39-193">Standaardtekst die wordt geleverd met versleutelde e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="e6b39-193">Default text that comes with encrypted email messages.</span></span>  <span data-ttu-id="e6b39-194">De standaardtekst wordt weergegeven boven de instructies voor het weergeven van versleutelde berichten</span><span class="sxs-lookup"><span data-stu-id="e6b39-194">The default text appears above the instructions for viewing encrypted messages</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> <span data-ttu-id="e6b39-195">**Voorbeeld:**</span><span class="sxs-lookup"><span data-stu-id="e6b39-195">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |<span data-ttu-id="e6b39-196">Vrijwaringsverklaring in het e-mailbericht met het versleutelde bericht</span><span class="sxs-lookup"><span data-stu-id="e6b39-196">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> <span data-ttu-id="e6b39-197">**Voorbeeld:**</span><span class="sxs-lookup"><span data-stu-id="e6b39-197">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |<span data-ttu-id="e6b39-198">Tekst die boven aan de portal voor het weergeven van versleutelde e-mail wordt weergegeven</span><span class="sxs-lookup"><span data-stu-id="e6b39-198">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> <span data-ttu-id="e6b39-199">**Voorbeeld om terug te keren naar standaard:**</span><span class="sxs-lookup"><span data-stu-id="e6b39-199">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |<span data-ttu-id="e6b39-200">Logo</span><span class="sxs-lookup"><span data-stu-id="e6b39-200">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> <span data-ttu-id="e6b39-201">**Voorbeeld om terug te keren naar standaard:**</span><span class="sxs-lookup"><span data-stu-id="e6b39-201">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |<span data-ttu-id="e6b39-202">Achtergrondkleur</span><span class="sxs-lookup"><span data-stu-id="e6b39-202">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> <span data-ttu-id="e6b39-203">**Voorbeeld om terug te keren naar standaard:**</span><span class="sxs-lookup"><span data-stu-id="e6b39-203">**Example reverting back to default:**</span></span> <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a><span data-ttu-id="e6b39-204">Een aangepaste huisstijlsjabloon verwijderen (Geavanceerde berichtversleuteling)</span><span class="sxs-lookup"><span data-stu-id="e6b39-204">Remove a custom branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="e6b39-205">U kunt alleen merksjablonen verwijderen of verwijderen die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="e6b39-205">You can only remove or delete branding templates that you've made.</span></span> <span data-ttu-id="e6b39-206">U kunt de standaardsjabloon voor huisstijl niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="e6b39-206">You can't remove the default branding template.</span></span>

<span data-ttu-id="e6b39-207">Een aangepaste huisstijlsjabloon verwijderen:</span><span class="sxs-lookup"><span data-stu-id="e6b39-207">To remove a custom branding template:</span></span>
  
1. <span data-ttu-id="e6b39-208">Als u een werk- of schoolaccount gebruikt met globale beheerdersmachtigingen in uw organisatie, start u een Windows PowerShell en maakt u verbinding met Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e6b39-208">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e6b39-209">Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="e6b39-209">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="e6b39-210">Gebruik de **cmdlet Remove-OMEConfiguration** als volgt:</span><span class="sxs-lookup"><span data-stu-id="e6b39-210">Use the **Remove-OMEConfiguration** cmdlet as follows:</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   <span data-ttu-id="e6b39-211">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="e6b39-211">For example,</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   <span data-ttu-id="e6b39-212">Zie [Remove-OMEConfiguration (Verwijderen-OMEConfiguration) voor meer informatie.](/powershell/module/exchange/remove-omeconfiguration)</span><span class="sxs-lookup"><span data-stu-id="e6b39-212">For more information, see [Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration).</span></span>

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a><span data-ttu-id="e6b39-213">Maak een Exchange e-mailstroomregel die uw aangepaste huisstijl op versleutelde e-mailberichten van toepassing is</span><span class="sxs-lookup"><span data-stu-id="e6b39-213">Create an Exchange mail flow rule that applies your custom branding to encrypted emails</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e6b39-214">Toepassingen van derden die e-mail scannen en wijzigen, kunnen voorkomen dat OME-huisstijl correct wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="e6b39-214">Third-party applications that scan and modify mail can prevent OME branding from being applied correctly.</span></span>

<span data-ttu-id="e6b39-215">Nadat u de standaardsjabloon hebt gewijzigd of nieuwe huisstijlsjablonen hebt gemaakt, kunt u Exchange regels voor e-mailstroom maken om uw aangepaste huisstijl toe te passen op basis van bepaalde voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="e6b39-215">After you've either modified the default template or created new branding templates, you can create Exchange mail flow rules to apply your custom branding based on certain conditions.</span></span> <span data-ttu-id="e6b39-216">Een dergelijke regel is in de volgende scenario's van toepassing op aangepaste huisstijl:</span><span class="sxs-lookup"><span data-stu-id="e6b39-216">Such a rule will apply custom branding in the following scenarios:</span></span>

- <span data-ttu-id="e6b39-217">Als de e-mail handmatig is versleuteld door de eindgebruiker met Outlook of webversie van Outlook, voorheen Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="e6b39-217">If the email was manually encrypted by the end user using Outlook or Outlook on the web, formerly Outlook Web App</span></span>

- <span data-ttu-id="e6b39-218">Als de e-mail automatisch is versleuteld door een Exchange regel voor e-mailstroom of beleid voor preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="e6b39-218">If the email was automatically encrypted by an Exchange mail flow rule or Data Loss Prevention policy</span></span>

<span data-ttu-id="e6b39-219">Zie Regels voor e-mailstroom definiëren om e-mailberichten te versleutelen in Office 365 voor informatie over het maken van een Exchange [e-mailstroomregel](define-mail-flow-rules-to-encrypt-email.md)die versleuteling van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="e6b39-219">For information on how to create an Exchange mail flow rule that applies encryption, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

1. <span data-ttu-id="e6b39-220">Meld u in een webbrowser met behulp van een werk- of schoolaccount dat globale beheerdersmachtigingen is verleend, [aan bij Office 365.](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)</span><span class="sxs-lookup"><span data-stu-id="e6b39-220">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="e6b39-221">Kies de **tegel** Beheerder.</span><span class="sxs-lookup"><span data-stu-id="e6b39-221">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="e6b39-222">Kies beheercentra Microsoft 365-beheercentrum de  \> Exchange.</span><span class="sxs-lookup"><span data-stu-id="e6b39-222">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="e6b39-223">Ga in het EAC naar **E-mailstroomregels** \>  en selecteer **Nieuw** nieuw pictogram Een nieuwe ![ regel ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **maken.**</span><span class="sxs-lookup"><span data-stu-id="e6b39-223">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="e6b39-224">Zie voor meer informatie over het gebruik van het EAC [Exchange beheercentrum in Exchange Online.](/exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="e6b39-224">For more information about using the EAC, see [Exchange admin center in Exchange Online](/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="e6b39-225">Typ **in Naam** een naam voor de regel, zoals Huisstijl voor verkoopafdeling.</span><span class="sxs-lookup"><span data-stu-id="e6b39-225">In **Name**, type a name for the rule, such as Branding for sales department.</span></span>

6. <span data-ttu-id="e6b39-226">Selecteer **in Deze regel toepassen als** de voorwaarde De afzender bevindt zich **binnen** de organisatie en andere voorwaarden die u wilt in de lijst met beschikbare voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="e6b39-226">In **Apply this rule if**, select the condition **The sender is located inside the organization** and other conditions you want from the list of available conditions.</span></span> <span data-ttu-id="e6b39-227">U kunt bijvoorbeeld een bepaalde huisstijlsjabloon toepassen op:</span><span class="sxs-lookup"><span data-stu-id="e6b39-227">For example, you might want to apply a particular branding template to:</span></span>

   - <span data-ttu-id="e6b39-228">Alle versleutelde e-mailberichten die zijn verzonden van leden van de financiële afdeling</span><span class="sxs-lookup"><span data-stu-id="e6b39-228">All encrypted emails sent from members of the finance department</span></span>
   - <span data-ttu-id="e6b39-229">Versleutelde e-mailberichten die zijn verzonden met een bepaald trefwoord, zoals 'Extern' of 'Partner'.</span><span class="sxs-lookup"><span data-stu-id="e6b39-229">Encrypted emails sent with a certain keyword such as "External" or "Partner"</span></span>
   - <span data-ttu-id="e6b39-230">Versleutelde e-mailberichten die naar een bepaald domein zijn verzonden</span><span class="sxs-lookup"><span data-stu-id="e6b39-230">Encrypted emails sent to a particular domain</span></span>

7. <span data-ttu-id="e6b39-231">Selecteer **in Ga als volgt** te werk en selecteer De **berichtbeveiliging** Aanpassen Aangepaste \> **huisstijl toepassen op OME-berichten.**</span><span class="sxs-lookup"><span data-stu-id="e6b39-231">From **Do the following**, select **Modify the message security** \> **Apply custom branding to OME messages**.</span></span> <span data-ttu-id="e6b39-232">Selecteer vervolgens in de vervolgkeuzekeuzepagina een huisstijlsjabloon.</span><span class="sxs-lookup"><span data-stu-id="e6b39-232">Next, from the drop-down, select a branding template.</span></span>

8. <span data-ttu-id="e6b39-233">(Optioneel) U kunt de regel voor de e-mailstroom zo configureren dat versleuteling en aangepaste huisstijl worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="e6b39-233">(Optional) You can configure the mail flow rule to apply encryption and custom branding.</span></span> <span data-ttu-id="e6b39-234">Selecteer **in Ga als volgt** te werk, selecteer De **berichtbeveiliging wijzigen** en kies vervolgens Office 365-berichtversleuteling en **rechtenbescherming toepassen.**</span><span class="sxs-lookup"><span data-stu-id="e6b39-234">From **Do the following**, select **Modify the message security**, and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="e6b39-235">Selecteer een RMS-sjabloon in de lijst, kies **Opslaan** en kies **ok.**</span><span class="sxs-lookup"><span data-stu-id="e6b39-235">Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
   <span data-ttu-id="e6b39-236">De lijst met sjablonen bevat standaardsjablonen en opties en eventuele aangepaste sjablonen die u maakt.</span><span class="sxs-lookup"><span data-stu-id="e6b39-236">The list of templates includes default templates and options and any custom templates you create.</span></span> <span data-ttu-id="e6b39-237">Als de lijst leeg is, moet u ervoor zorgen dat u Office 365-berichtversleuteling met de nieuwe mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="e6b39-237">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities.</span></span> <span data-ttu-id="e6b39-238">Zie Nieuwe functies voor Office 365-berichtversleuteling instellen voor [instructies.](set-up-new-message-encryption-capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="e6b39-238">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="e6b39-239">Zie Sjablonen configureren en beheren voor [Azure Information Protection](/information-protection/deploy-use/configure-policy-templates)voor meer informatie over de standaardsjablonen.</span><span class="sxs-lookup"><span data-stu-id="e6b39-239">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="e6b39-240">Zie Optie  Niet doorsturen voor e-mailberichten voor informatie over de optie Niet doorsturen. [](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="e6b39-240">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="e6b39-241">Zie Alleen **versleutelen** voor e-mailberichten voor informatie over de enige optie [voor versleutelen.](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="e6b39-241">For information about the **encrypt only** option, see [Encrypt Only option for emails](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

   <span data-ttu-id="e6b39-242">Kies **Actie toevoegen** als u een andere actie wilt opgeven.</span><span class="sxs-lookup"><span data-stu-id="e6b39-242">Choose **add action** if you want to specify another action.</span></span>

## <a name="background-color-reference"></a><span data-ttu-id="e6b39-243">Achtergrondkleurverwijzing</span><span class="sxs-lookup"><span data-stu-id="e6b39-243">Background color reference</span></span>

<span data-ttu-id="e6b39-244">De kleurnamen die u voor de achtergrondkleur kunt gebruiken, zijn beperkt.</span><span class="sxs-lookup"><span data-stu-id="e6b39-244">The color names that you can use for the background color are limited.</span></span> <span data-ttu-id="e6b39-245">In plaats van een kleurnaam kunt u een hexcodewaarde (#RRGGBB).</span><span class="sxs-lookup"><span data-stu-id="e6b39-245">Instead of a color name, you can use a hex code value (#RRGGBB).</span></span> <span data-ttu-id="e6b39-246">U kunt een hexcodewaarde gebruiken die overeenkomt met een kleurnaam of u kunt een aangepaste hex-codewaarde gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e6b39-246">You can use a hex code value that corresponds to a color name, or you can use a custom hex code value.</span></span> <span data-ttu-id="e6b39-247">Zorg ervoor dat u de hexcodewaarde tussen aanhalingstekens (bijvoorbeeld) `"#f0f8ff"` omsluit.</span><span class="sxs-lookup"><span data-stu-id="e6b39-247">Be sure to enclose the hex code value in quotation marks (for example, `"#f0f8ff"`).</span></span>

<span data-ttu-id="e6b39-248">De beschikbare achtergrondkleurnamen en de bijbehorende hexcodewaarden worden in de volgende tabel beschreven.</span><span class="sxs-lookup"><span data-stu-id="e6b39-248">The available background color names and their corresponding hex code values are described in the following table.</span></span>

|<span data-ttu-id="e6b39-249">**Naam van kleur**</span><span class="sxs-lookup"><span data-stu-id="e6b39-249">**Color name**</span></span>|<span data-ttu-id="e6b39-250">**Kleurcode**</span><span class="sxs-lookup"><span data-stu-id="e6b39-250">**Color code**</span></span>|
|---|---|
|`aliceblue`|<span data-ttu-id="e6b39-251">#f0f8ff</span><span class="sxs-lookup"><span data-stu-id="e6b39-251">#f0f8ff</span></span>|
|`antiquewhite`|<span data-ttu-id="e6b39-252">#faebd7</span><span class="sxs-lookup"><span data-stu-id="e6b39-252">#faebd7</span></span>|
|`aqua`|<span data-ttu-id="e6b39-253">#00ffff</span><span class="sxs-lookup"><span data-stu-id="e6b39-253">#00ffff</span></span>|
|`aquamarine`|<span data-ttu-id="e6b39-254">#7fffd4</span><span class="sxs-lookup"><span data-stu-id="e6b39-254">#7fffd4</span></span>|
|`azure`|<span data-ttu-id="e6b39-255">#f0ffff</span><span class="sxs-lookup"><span data-stu-id="e6b39-255">#f0ffff</span></span>|
|`beige`|<span data-ttu-id="e6b39-256">#f5f5dc</span><span class="sxs-lookup"><span data-stu-id="e6b39-256">#f5f5dc</span></span>|
|`bisque`|<span data-ttu-id="e6b39-257">#ffe4c4</span><span class="sxs-lookup"><span data-stu-id="e6b39-257">#ffe4c4</span></span>|
|`black`|<span data-ttu-id="e6b39-258">#000000</span><span class="sxs-lookup"><span data-stu-id="e6b39-258">#000000</span></span>|
|`blanchedalmond`|<span data-ttu-id="e6b39-259">#ffebcd</span><span class="sxs-lookup"><span data-stu-id="e6b39-259">#ffebcd</span></span>|
|`blue`|<span data-ttu-id="e6b39-260">#0000ff</span><span class="sxs-lookup"><span data-stu-id="e6b39-260">#0000ff</span></span>|
|`blueviolet`|<span data-ttu-id="e6b39-261">#8a2be2</span><span class="sxs-lookup"><span data-stu-id="e6b39-261">#8a2be2</span></span>|
|`brown`|<span data-ttu-id="e6b39-262">#a52a2a</span><span class="sxs-lookup"><span data-stu-id="e6b39-262">#a52a2a</span></span>|
|`burlywood`|<span data-ttu-id="e6b39-263">#deb887</span><span class="sxs-lookup"><span data-stu-id="e6b39-263">#deb887</span></span>|
|`cadetblue`|<span data-ttu-id="e6b39-264">#5f9ea0</span><span class="sxs-lookup"><span data-stu-id="e6b39-264">#5f9ea0</span></span>|
|`chartreuse`|<span data-ttu-id="e6b39-265">#7fff00</span><span class="sxs-lookup"><span data-stu-id="e6b39-265">#7fff00</span></span>|
|`chocolate`|<span data-ttu-id="e6b39-266">#d2691e</span><span class="sxs-lookup"><span data-stu-id="e6b39-266">#d2691e</span></span>|
|`coral`|<span data-ttu-id="e6b39-267">#ff7f50</span><span class="sxs-lookup"><span data-stu-id="e6b39-267">#ff7f50</span></span>|
|`cornflowerblue`|<span data-ttu-id="e6b39-268">#6495ed</span><span class="sxs-lookup"><span data-stu-id="e6b39-268">#6495ed</span></span>|
|`cornsilk`|<span data-ttu-id="e6b39-269">#fff8dc</span><span class="sxs-lookup"><span data-stu-id="e6b39-269">#fff8dc</span></span>|
|`crimson`|<span data-ttu-id="e6b39-270">#dc143c</span><span class="sxs-lookup"><span data-stu-id="e6b39-270">#dc143c</span></span>|
|`cyan`|<span data-ttu-id="e6b39-271">#00ffff</span><span class="sxs-lookup"><span data-stu-id="e6b39-271">#00ffff</span></span>|
|`darkblue`|<span data-ttu-id="e6b39-272">#00008b</span><span class="sxs-lookup"><span data-stu-id="e6b39-272">#00008b</span></span>|
|`darkcyan`|<span data-ttu-id="e6b39-273">#008b8b</span><span class="sxs-lookup"><span data-stu-id="e6b39-273">#008b8b</span></span>|
|`darkgoldenrod`|<span data-ttu-id="e6b39-274">#b8860b</span><span class="sxs-lookup"><span data-stu-id="e6b39-274">#b8860b</span></span>|
|`darkgray`|<span data-ttu-id="e6b39-275">#a9a9a9</span><span class="sxs-lookup"><span data-stu-id="e6b39-275">#a9a9a9</span></span>|
|`darkgreen`|<span data-ttu-id="e6b39-276">#006400</span><span class="sxs-lookup"><span data-stu-id="e6b39-276">#006400</span></span>|
|`darkkhaki`|<span data-ttu-id="e6b39-277">#bdb76b</span><span class="sxs-lookup"><span data-stu-id="e6b39-277">#bdb76b</span></span>|
|`darkmagenta`|<span data-ttu-id="e6b39-278">#8b008b</span><span class="sxs-lookup"><span data-stu-id="e6b39-278">#8b008b</span></span>|
|`darkolivegreen`|<span data-ttu-id="e6b39-279">#556b2f</span><span class="sxs-lookup"><span data-stu-id="e6b39-279">#556b2f</span></span>|
|`darkorange`|<span data-ttu-id="e6b39-280">#ff8c00</span><span class="sxs-lookup"><span data-stu-id="e6b39-280">#ff8c00</span></span>|
|`darkorchid`|<span data-ttu-id="e6b39-281">#9932cc</span><span class="sxs-lookup"><span data-stu-id="e6b39-281">#9932cc</span></span>|
|`darkred`|<span data-ttu-id="e6b39-282">#8b0000</span><span class="sxs-lookup"><span data-stu-id="e6b39-282">#8b0000</span></span>|
|`darksalmon`|<span data-ttu-id="e6b39-283">#e9967a</span><span class="sxs-lookup"><span data-stu-id="e6b39-283">#e9967a</span></span>|
|`darkseagreen`|<span data-ttu-id="e6b39-284">#8fbc8f</span><span class="sxs-lookup"><span data-stu-id="e6b39-284">#8fbc8f</span></span>|
|`darkslateblue`|<span data-ttu-id="e6b39-285">#483d8b</span><span class="sxs-lookup"><span data-stu-id="e6b39-285">#483d8b</span></span>|
|`darkslategray`|<span data-ttu-id="e6b39-286">#2f4f4f</span><span class="sxs-lookup"><span data-stu-id="e6b39-286">#2f4f4f</span></span>|
|`darkturquoise`|<span data-ttu-id="e6b39-287">#00ced1</span><span class="sxs-lookup"><span data-stu-id="e6b39-287">#00ced1</span></span>|
|`darkviolet`|<span data-ttu-id="e6b39-288">#9400d3</span><span class="sxs-lookup"><span data-stu-id="e6b39-288">#9400d3</span></span>|
|`deeppink`|<span data-ttu-id="e6b39-289">#ff1493</span><span class="sxs-lookup"><span data-stu-id="e6b39-289">#ff1493</span></span>|
|`deepskyblue`|<span data-ttu-id="e6b39-290">#00bfff</span><span class="sxs-lookup"><span data-stu-id="e6b39-290">#00bfff</span></span>|
|`dimgray`|<span data-ttu-id="e6b39-291">#696969</span><span class="sxs-lookup"><span data-stu-id="e6b39-291">#696969</span></span>|
|`dodgerblue`|<span data-ttu-id="e6b39-292">#1e90ff</span><span class="sxs-lookup"><span data-stu-id="e6b39-292">#1e90ff</span></span>|
|`firebrick`|<span data-ttu-id="e6b39-293">#b22222</span><span class="sxs-lookup"><span data-stu-id="e6b39-293">#b22222</span></span>|
|`floralwhite`|<span data-ttu-id="e6b39-294">#fffaf0</span><span class="sxs-lookup"><span data-stu-id="e6b39-294">#fffaf0</span></span>|
|`forestgreen`|<span data-ttu-id="e6b39-295">#228b22</span><span class="sxs-lookup"><span data-stu-id="e6b39-295">#228b22</span></span>|
|`fuchsia`|<span data-ttu-id="e6b39-296">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="e6b39-296">#ff00ff</span></span>|
|`gainsboro`|<span data-ttu-id="e6b39-297">#dcdcdc</span><span class="sxs-lookup"><span data-stu-id="e6b39-297">#dcdcdc</span></span>|
|`ghostwhite`|<span data-ttu-id="e6b39-298">#f8f8ff</span><span class="sxs-lookup"><span data-stu-id="e6b39-298">#f8f8ff</span></span>|
|`gold`|<span data-ttu-id="e6b39-299">#ffd700</span><span class="sxs-lookup"><span data-stu-id="e6b39-299">#ffd700</span></span>|
|`goldenrod`|<span data-ttu-id="e6b39-300">#daa520</span><span class="sxs-lookup"><span data-stu-id="e6b39-300">#daa520</span></span>|
|`gray`|<span data-ttu-id="e6b39-301">#808080</span><span class="sxs-lookup"><span data-stu-id="e6b39-301">#808080</span></span>|
|`green`|<span data-ttu-id="e6b39-302">#008000</span><span class="sxs-lookup"><span data-stu-id="e6b39-302">#008000</span></span>|
|`greenyellow`|<span data-ttu-id="e6b39-303">#adff2f</span><span class="sxs-lookup"><span data-stu-id="e6b39-303">#adff2f</span></span>|
|`honeydew`|<span data-ttu-id="e6b39-304">#f0fff0</span><span class="sxs-lookup"><span data-stu-id="e6b39-304">#f0fff0</span></span>|
|`hotpink`|<span data-ttu-id="e6b39-305">#ff69b4</span><span class="sxs-lookup"><span data-stu-id="e6b39-305">#ff69b4</span></span>|
|`indianred`|<span data-ttu-id="e6b39-306">#cd5c5c</span><span class="sxs-lookup"><span data-stu-id="e6b39-306">#cd5c5c</span></span>|
|`indigo`|<span data-ttu-id="e6b39-307">#4b0082</span><span class="sxs-lookup"><span data-stu-id="e6b39-307">#4b0082</span></span>|
|`ivory`|<span data-ttu-id="e6b39-308">#fffff0</span><span class="sxs-lookup"><span data-stu-id="e6b39-308">#fffff0</span></span>|
|`khaki`|<span data-ttu-id="e6b39-309">#f0e68c</span><span class="sxs-lookup"><span data-stu-id="e6b39-309">#f0e68c</span></span>|
|`lavender`|<span data-ttu-id="e6b39-310">#e6e6fa</span><span class="sxs-lookup"><span data-stu-id="e6b39-310">#e6e6fa</span></span>|
|`lavenderblush`|<span data-ttu-id="e6b39-311">#fff0f5</span><span class="sxs-lookup"><span data-stu-id="e6b39-311">#fff0f5</span></span>|
|`lawngreen`|<span data-ttu-id="e6b39-312">#7cfc00</span><span class="sxs-lookup"><span data-stu-id="e6b39-312">#7cfc00</span></span>|
|`lemonchiffon`|<span data-ttu-id="e6b39-313">#fffacd</span><span class="sxs-lookup"><span data-stu-id="e6b39-313">#fffacd</span></span>|
|`lightblue`|<span data-ttu-id="e6b39-314">#add8e6</span><span class="sxs-lookup"><span data-stu-id="e6b39-314">#add8e6</span></span>|
|`lightcoral`|<span data-ttu-id="e6b39-315">#f08080</span><span class="sxs-lookup"><span data-stu-id="e6b39-315">#f08080</span></span>|
|`lightcyan`|<span data-ttu-id="e6b39-316">#e0ffff</span><span class="sxs-lookup"><span data-stu-id="e6b39-316">#e0ffff</span></span>|
|`lightgoldenrodyellow`|<span data-ttu-id="e6b39-317">#fafad2</span><span class="sxs-lookup"><span data-stu-id="e6b39-317">#fafad2</span></span>|
|`lightgray`|<span data-ttu-id="e6b39-318">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="e6b39-318">#d3d3d3</span></span>|
|`lightgrey`|<span data-ttu-id="e6b39-319">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="e6b39-319">#d3d3d3</span></span>|
|`lightgreen`|<span data-ttu-id="e6b39-320">#90ee90</span><span class="sxs-lookup"><span data-stu-id="e6b39-320">#90ee90</span></span>|
|`lightpink`|<span data-ttu-id="e6b39-321">#ffb6c1</span><span class="sxs-lookup"><span data-stu-id="e6b39-321">#ffb6c1</span></span>|
|`lightsalmon`|<span data-ttu-id="e6b39-322">#ffa07a</span><span class="sxs-lookup"><span data-stu-id="e6b39-322">#ffa07a</span></span>|
|`lightseagreen`|<span data-ttu-id="e6b39-323">#20b2aa</span><span class="sxs-lookup"><span data-stu-id="e6b39-323">#20b2aa</span></span>|
|`lightskyblue`|<span data-ttu-id="e6b39-324">#87cefa</span><span class="sxs-lookup"><span data-stu-id="e6b39-324">#87cefa</span></span>|
|`lightslategray`|<span data-ttu-id="e6b39-325">#778899</span><span class="sxs-lookup"><span data-stu-id="e6b39-325">#778899</span></span>|
|`lightsteelblue`|<span data-ttu-id="e6b39-326">#b0c4de</span><span class="sxs-lookup"><span data-stu-id="e6b39-326">#b0c4de</span></span>|
|`lightyellow`|<span data-ttu-id="e6b39-327">#ffffe0</span><span class="sxs-lookup"><span data-stu-id="e6b39-327">#ffffe0</span></span>|
|`lime`|<span data-ttu-id="e6b39-328">#00ff00</span><span class="sxs-lookup"><span data-stu-id="e6b39-328">#00ff00</span></span>|
|`limegreen`|<span data-ttu-id="e6b39-329">#32cd32</span><span class="sxs-lookup"><span data-stu-id="e6b39-329">#32cd32</span></span>|
|`linen`|<span data-ttu-id="e6b39-330">#faf0e6</span><span class="sxs-lookup"><span data-stu-id="e6b39-330">#faf0e6</span></span>|
|`magenta`|<span data-ttu-id="e6b39-331">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="e6b39-331">#ff00ff</span></span>|
|`maroon`|<span data-ttu-id="e6b39-332">#800000</span><span class="sxs-lookup"><span data-stu-id="e6b39-332">#800000</span></span>|
|`mediumaquamarine`|<span data-ttu-id="e6b39-333">#66cdaa</span><span class="sxs-lookup"><span data-stu-id="e6b39-333">#66cdaa</span></span>|
|`mediumblue`|<span data-ttu-id="e6b39-334">#0000cd</span><span class="sxs-lookup"><span data-stu-id="e6b39-334">#0000cd</span></span>|
|`mediumorchid`|<span data-ttu-id="e6b39-335">#ba55d3</span><span class="sxs-lookup"><span data-stu-id="e6b39-335">#ba55d3</span></span>|
|`mediumpurple`|<span data-ttu-id="e6b39-336">#9370db</span><span class="sxs-lookup"><span data-stu-id="e6b39-336">#9370db</span></span>|
|`mediumseagreen`|<span data-ttu-id="e6b39-337">#3cb371</span><span class="sxs-lookup"><span data-stu-id="e6b39-337">#3cb371</span></span>|
|`mediumslateblue`|<span data-ttu-id="e6b39-338">#7b68ee</span><span class="sxs-lookup"><span data-stu-id="e6b39-338">#7b68ee</span></span>|
|`mediumspringgreen`|<span data-ttu-id="e6b39-339">#00fa9a</span><span class="sxs-lookup"><span data-stu-id="e6b39-339">#00fa9a</span></span>|
|`mediumturquoise`|<span data-ttu-id="e6b39-340">#48d1cc</span><span class="sxs-lookup"><span data-stu-id="e6b39-340">#48d1cc</span></span>|
|`mediumvioletred`|<span data-ttu-id="e6b39-341">#c71585</span><span class="sxs-lookup"><span data-stu-id="e6b39-341">#c71585</span></span>|
|`midnightblue`|<span data-ttu-id="e6b39-342">#191970</span><span class="sxs-lookup"><span data-stu-id="e6b39-342">#191970</span></span>|
|`mintcream`|<span data-ttu-id="e6b39-343">#f5fffa</span><span class="sxs-lookup"><span data-stu-id="e6b39-343">#f5fffa</span></span>|
|`mistyrose`|<span data-ttu-id="e6b39-344">#ffe4e1</span><span class="sxs-lookup"><span data-stu-id="e6b39-344">#ffe4e1</span></span>|
|`moccasin`|<span data-ttu-id="e6b39-345">#ffe4b5</span><span class="sxs-lookup"><span data-stu-id="e6b39-345">#ffe4b5</span></span>|
|`navajowhite`|<span data-ttu-id="e6b39-346">#ffdead</span><span class="sxs-lookup"><span data-stu-id="e6b39-346">#ffdead</span></span>|
|`navy`|<span data-ttu-id="e6b39-347">#000080</span><span class="sxs-lookup"><span data-stu-id="e6b39-347">#000080</span></span>|
|`oldlace`|<span data-ttu-id="e6b39-348">#fdf5e6</span><span class="sxs-lookup"><span data-stu-id="e6b39-348">#fdf5e6</span></span>|
|`olive`|<span data-ttu-id="e6b39-349">#808000</span><span class="sxs-lookup"><span data-stu-id="e6b39-349">#808000</span></span>|
|`olivedrab`|<span data-ttu-id="e6b39-350">#6b8e23</span><span class="sxs-lookup"><span data-stu-id="e6b39-350">#6b8e23</span></span>|
|`orange`|<span data-ttu-id="e6b39-351">#ffa500</span><span class="sxs-lookup"><span data-stu-id="e6b39-351">#ffa500</span></span>|
|`orangered`|<span data-ttu-id="e6b39-352">#ff4500</span><span class="sxs-lookup"><span data-stu-id="e6b39-352">#ff4500</span></span>|
|`orchid`|<span data-ttu-id="e6b39-353">#da70d6</span><span class="sxs-lookup"><span data-stu-id="e6b39-353">#da70d6</span></span>|
|`palegoldenrod`|<span data-ttu-id="e6b39-354">#eee8aa</span><span class="sxs-lookup"><span data-stu-id="e6b39-354">#eee8aa</span></span>|
|`palegreen`|<span data-ttu-id="e6b39-355">#98fb98</span><span class="sxs-lookup"><span data-stu-id="e6b39-355">#98fb98</span></span>|
|`paleturquoise`|<span data-ttu-id="e6b39-356">#afeeee</span><span class="sxs-lookup"><span data-stu-id="e6b39-356">#afeeee</span></span>|
|`palevioletred`|<span data-ttu-id="e6b39-357">#db7093</span><span class="sxs-lookup"><span data-stu-id="e6b39-357">#db7093</span></span>|
|`papayawhip`|<span data-ttu-id="e6b39-358">#ffefd5</span><span class="sxs-lookup"><span data-stu-id="e6b39-358">#ffefd5</span></span>|
|`peachpuff`|<span data-ttu-id="e6b39-359">#ffdab9</span><span class="sxs-lookup"><span data-stu-id="e6b39-359">#ffdab9</span></span>|
|`peru`|<span data-ttu-id="e6b39-360">#cd853f</span><span class="sxs-lookup"><span data-stu-id="e6b39-360">#cd853f</span></span>|
|`pink`|<span data-ttu-id="e6b39-361">#ffc0cb</span><span class="sxs-lookup"><span data-stu-id="e6b39-361">#ffc0cb</span></span>|
|`plum`|<span data-ttu-id="e6b39-362">#dda0dd</span><span class="sxs-lookup"><span data-stu-id="e6b39-362">#dda0dd</span></span>|
|`powderblue`|<span data-ttu-id="e6b39-363">#b0e0e6</span><span class="sxs-lookup"><span data-stu-id="e6b39-363">#b0e0e6</span></span>|
|`purple`|<span data-ttu-id="e6b39-364">#800080</span><span class="sxs-lookup"><span data-stu-id="e6b39-364">#800080</span></span>|
|`red`|<span data-ttu-id="e6b39-365">#ff0000</span><span class="sxs-lookup"><span data-stu-id="e6b39-365">#ff0000</span></span>|
|`rosybrown`|<span data-ttu-id="e6b39-366">#bc8f8f</span><span class="sxs-lookup"><span data-stu-id="e6b39-366">#bc8f8f</span></span>|
|`royalblue`|<span data-ttu-id="e6b39-367">#4169e1</span><span class="sxs-lookup"><span data-stu-id="e6b39-367">#4169e1</span></span>|
|`saddlebrown`|<span data-ttu-id="e6b39-368">#8b4513</span><span class="sxs-lookup"><span data-stu-id="e6b39-368">#8b4513</span></span>|
|`salmon`|<span data-ttu-id="e6b39-369">#fa8072</span><span class="sxs-lookup"><span data-stu-id="e6b39-369">#fa8072</span></span>|
|`sandybrown`|<span data-ttu-id="e6b39-370">#f4a460</span><span class="sxs-lookup"><span data-stu-id="e6b39-370">#f4a460</span></span>|
|`seagreen`|<span data-ttu-id="e6b39-371">#00ff00</span><span class="sxs-lookup"><span data-stu-id="e6b39-371">#00ff00</span></span>|
|`seashell`|<span data-ttu-id="e6b39-372">#fff5ee</span><span class="sxs-lookup"><span data-stu-id="e6b39-372">#fff5ee</span></span>|
|`sienna`|<span data-ttu-id="e6b39-373">#a0522d</span><span class="sxs-lookup"><span data-stu-id="e6b39-373">#a0522d</span></span>|
|`silver`|<span data-ttu-id="e6b39-374">#c0c0c0</span><span class="sxs-lookup"><span data-stu-id="e6b39-374">#c0c0c0</span></span>|
|`skyblue`|<span data-ttu-id="e6b39-375">#87ceeb</span><span class="sxs-lookup"><span data-stu-id="e6b39-375">#87ceeb</span></span>|
|`slateblue`|<span data-ttu-id="e6b39-376">#6a5acd</span><span class="sxs-lookup"><span data-stu-id="e6b39-376">#6a5acd</span></span>|
|`slategray`|<span data-ttu-id="e6b39-377">#708090</span><span class="sxs-lookup"><span data-stu-id="e6b39-377">#708090</span></span>|
|`snow`|<span data-ttu-id="e6b39-378">#fffafa</span><span class="sxs-lookup"><span data-stu-id="e6b39-378">#fffafa</span></span>|
|`springgreen`|<span data-ttu-id="e6b39-379">#00ff7f</span><span class="sxs-lookup"><span data-stu-id="e6b39-379">#00ff7f</span></span>|
|`steelblue`|<span data-ttu-id="e6b39-380">#4682b4</span><span class="sxs-lookup"><span data-stu-id="e6b39-380">#4682b4</span></span>|
|`tan`|<span data-ttu-id="e6b39-381">#d2b48c</span><span class="sxs-lookup"><span data-stu-id="e6b39-381">#d2b48c</span></span>|
|`teal`|<span data-ttu-id="e6b39-382">#008080</span><span class="sxs-lookup"><span data-stu-id="e6b39-382">#008080</span></span>|
|`thistle`|<span data-ttu-id="e6b39-383">#d8bfd8</span><span class="sxs-lookup"><span data-stu-id="e6b39-383">#d8bfd8</span></span>|
|`tomato`|<span data-ttu-id="e6b39-384">#ff6347</span><span class="sxs-lookup"><span data-stu-id="e6b39-384">#ff6347</span></span>|
|`turquoise`|<span data-ttu-id="e6b39-385">#40e0d0</span><span class="sxs-lookup"><span data-stu-id="e6b39-385">#40e0d0</span></span>|
|`violet`|<span data-ttu-id="e6b39-386">#ee82ee</span><span class="sxs-lookup"><span data-stu-id="e6b39-386">#ee82ee</span></span>|
|`wheat`|<span data-ttu-id="e6b39-387">#f5deb3</span><span class="sxs-lookup"><span data-stu-id="e6b39-387">#f5deb3</span></span>|
|`white`|<span data-ttu-id="e6b39-388">#ffffff</span><span class="sxs-lookup"><span data-stu-id="e6b39-388">#ffffff</span></span>|
|`whitesmoke`|<span data-ttu-id="e6b39-389">#f5f5f5</span><span class="sxs-lookup"><span data-stu-id="e6b39-389">#f5f5f5</span></span>|
|`yellow`|<span data-ttu-id="e6b39-390">#ffff00</span><span class="sxs-lookup"><span data-stu-id="e6b39-390">#ffff00</span></span>|
|`yellowgreen`|<span data-ttu-id="e6b39-391">#9acd32</span><span class="sxs-lookup"><span data-stu-id="e6b39-391">#9acd32</span></span>|
