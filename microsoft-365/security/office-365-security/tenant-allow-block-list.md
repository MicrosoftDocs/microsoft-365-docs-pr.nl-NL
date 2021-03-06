---
title: Uw sta- en blokkeringen beheren in de tenantlijst toestaan/blokkeren
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Beheerders kunnen in de beveiligingsportal meer informatie krijgen over het configureren van toegestane en geblokkeerde tenants in de lijst Met toegestane/geblokkeerde tenants.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 20e460f4e93f7b87faaead8b87ba561224e38938
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515206"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="036b5-103">Tenant Toestaan/Blokkeren-lijst beheren</span><span class="sxs-lookup"><span data-stu-id="036b5-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="036b5-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="036b5-104">**Applies to**</span></span>
- [<span data-ttu-id="036b5-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="036b5-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="036b5-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="036b5-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="036b5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="036b5-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
>
> <span data-ttu-id="036b5-108">De functies die in dit artikel worden beschreven, zijn in preview beschikbaar, kunnen worden gewijzigd en zijn niet in alle organisaties beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="036b5-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>
>
> <span data-ttu-id="036b5-109">U kunt momenteel geen **toegestane** items in de tenantlijst Toestaan/Blokkeren configureren.</span><span class="sxs-lookup"><span data-stu-id="036b5-109">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="036b5-110">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken, bent u het mogelijk niet eens met de filtering van EOP.</span><span class="sxs-lookup"><span data-stu-id="036b5-110">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="036b5-111">Een goed bericht kan bijvoorbeeld als slecht zijn gemarkeerd (een fout-positief) of een slecht bericht kan zijn toegestaan (een fout-negatief).</span><span class="sxs-lookup"><span data-stu-id="036b5-111">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="036b5-112">Met de lijst met tenants toestaan/blokkeren in het & compliancecentrum voor beveiliging kunt u het filterbeleid van Microsoft 365 handmatig overschrijven.</span><span class="sxs-lookup"><span data-stu-id="036b5-112">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="036b5-113">De tenantlijst toestaan/blokkeren wordt gebruikt tijdens de e-mailstroom en tijdens het klikken door de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="036b5-113">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="036b5-114">U kunt URL's of bestanden opgeven die u altijd wilt blokkeren.</span><span class="sxs-lookup"><span data-stu-id="036b5-114">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="036b5-115">In dit artikel wordt beschreven hoe u vermeldingen configureert in de lijst Toestaan/blokkeren van de tenant in het beveiligings- & compliancecentrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).</span><span class="sxs-lookup"><span data-stu-id="036b5-115">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="036b5-116">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="036b5-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="036b5-117">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="036b5-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="036b5-118">Als u rechtstreeks naar de **pagina Tenant toestaan/blokkeren wilt** gaan, gebruikt u <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="036b5-118">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="036b5-119">U geeft bestanden op met behulp van de SHA256-hashwaarde van het bestand.</span><span class="sxs-lookup"><span data-stu-id="036b5-119">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="036b5-120">U kunt de SHA256-hashwaarde van een bestand in Windows vinden door de volgende opdracht uit te voeren in een opdrachtprompt:</span><span class="sxs-lookup"><span data-stu-id="036b5-120">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="036b5-121">Een voorbeeldwaarde is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="036b5-121">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="036b5-122">Perceptual hash -waarden (pHash) worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="036b5-122">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="036b5-123">De beschikbare URL-waarden worden beschreven in de URL-syntaxis voor de [sectie Toestaan/blokkeerlijst](#url-syntax-for-the-tenant-allowblock-list) voor tenants verderop in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="036b5-123">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="036b5-124">De tenantlijst toestaan/blokkeren biedt maximaal 500 vermeldingen voor URL's en 500 vermeldingen voor bestand-hashes.</span><span class="sxs-lookup"><span data-stu-id="036b5-124">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="036b5-125">Het maximum aantal tekens voor elke invoer is:</span><span class="sxs-lookup"><span data-stu-id="036b5-125">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="036b5-126">Bestandshashes = 64</span><span class="sxs-lookup"><span data-stu-id="036b5-126">File hashes = 64</span></span>
  - <span data-ttu-id="036b5-127">URL = 250</span><span class="sxs-lookup"><span data-stu-id="036b5-127">URL = 250</span></span>

- <span data-ttu-id="036b5-128">Een item moet binnen 30 minuten actief zijn.</span><span class="sxs-lookup"><span data-stu-id="036b5-128">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="036b5-129">Standaard verlopen vermeldingen in de lijst met toegestane/geblokkeerde tenants na 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="036b5-129">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="036b5-130">U kunt een datum opgeven of instellen dat deze nooit verloopt.</span><span class="sxs-lookup"><span data-stu-id="036b5-130">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="036b5-131">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="036b5-131">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="036b5-132">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="036b5-132">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="036b5-133">U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="036b5-133">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="036b5-134">Als u waarden wilt toevoegen aan en verwijderen uit de tenantlijst toestaan/blokkeren, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="036b5-134">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="036b5-135">Voor alleen-lezen toegang tot de tenantlijst Toestaan/Blokkeren moet  u lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="036b5-135">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="036b5-136">Zie [Machtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="036b5-136">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="036b5-137">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="036b5-137">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="036b5-138">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="036b5-138">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  > - <span data-ttu-id="036b5-139">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="036b5-139">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="036b5-140">Gebruik het beveiligings- & compliancecentrum om URL-vermeldingen te maken in de lijst Met toegestane/geblokkeerde tenants</span><span class="sxs-lookup"><span data-stu-id="036b5-140">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="036b5-141">Zie de syntaxis van de URL voor de sectie Lijst met tenants [toestaan/blokkeren](#url-syntax-for-the-tenant-allowblock-list) verderop in dit artikel voor meer informatie over de syntaxis voor URL-vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="036b5-141">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="036b5-142">Ga in het & compliancecentrum  naar de tenant Voor \>  \> **risicobeheerbeleid : toegestane/geblokkeerde lijsten.**</span><span class="sxs-lookup"><span data-stu-id="036b5-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="036b5-143">Controleer op **de pagina Tenant toestaan/blokkeren** of het tabblad **URL's** is geselecteerd en klik vervolgens op **Blokkeren**</span><span class="sxs-lookup"><span data-stu-id="036b5-143">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="036b5-144">Configureer **de volgende** instellingen in de flyout Blok-URL's die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="036b5-144">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="036b5-145">**Url's toevoegen die u wilt blokkeren:** voer één URL per regel in, maximaal 20.</span><span class="sxs-lookup"><span data-stu-id="036b5-145">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="036b5-146">**Verloopt nooit:** ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="036b5-146">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="036b5-147">Controleer of de instelling is uitgeschakeld (in-/uitschakelen) en gebruik het vak Verloopt in om de vervaldatum voor de items ![ ](../../media/scc-toggle-off.png) op te geven. </span><span class="sxs-lookup"><span data-stu-id="036b5-147">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="036b5-148">of</span><span class="sxs-lookup"><span data-stu-id="036b5-148">or</span></span>

     - <span data-ttu-id="036b5-149">Verplaats de schakelknop naar rechts om de vermeldingen zo te configureren dat ze nooit verlopen:</span><span class="sxs-lookup"><span data-stu-id="036b5-149">Move the toggle to the right to configure the entries to never expire:</span></span> ![Inschakelen](../../media/scc-toggle-on.png)<span data-ttu-id="036b5-151">.</span><span class="sxs-lookup"><span data-stu-id="036b5-151">.</span></span>

   - <span data-ttu-id="036b5-152">**Optionele opmerking:** voer beschrijvende tekst in voor de vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="036b5-152">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="036b5-153">Klik op Toevoegen wanneer u **klaar bent.**</span><span class="sxs-lookup"><span data-stu-id="036b5-153">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="036b5-154">Gebruik het beveiligings- & compliancecentrum om bestandsgegevens te maken in de lijst Met toegestane/geblokkeerde tenants</span><span class="sxs-lookup"><span data-stu-id="036b5-154">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="036b5-155">Ga in het & compliancecentrum  naar de tenant voor het \>  \> **risicobeheerbeleid : toegestane/geblokkeerde lijsten.**</span><span class="sxs-lookup"><span data-stu-id="036b5-155">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="036b5-156">Selecteer op **de pagina Lijst met tenants toestaan/blokkeren** het tabblad Bestanden en klik op **Blokkeren.** </span><span class="sxs-lookup"><span data-stu-id="036b5-156">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="036b5-157">Configureer **de volgende instellingen** in het dialoogvenster Bestanden toevoegen om de flyout te blokkeren die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="036b5-157">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="036b5-158">**Bestandshashes toevoegen:** voer één SHA256-hashwaarde per regel in, tot maximaal 20.</span><span class="sxs-lookup"><span data-stu-id="036b5-158">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="036b5-159">**Verloopt nooit:** ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="036b5-159">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="036b5-160">Controleer of de instelling is uitgeschakeld (in-/uitschakelen) en gebruik het vak Verloopt in om de vervaldatum voor de items ![ ](../../media/scc-toggle-off.png) op te geven. </span><span class="sxs-lookup"><span data-stu-id="036b5-160">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="036b5-161">of</span><span class="sxs-lookup"><span data-stu-id="036b5-161">or</span></span>

     - <span data-ttu-id="036b5-162">Verplaats de schakelknop naar rechts om de vermeldingen zo te configureren dat ze nooit verlopen:</span><span class="sxs-lookup"><span data-stu-id="036b5-162">Move the toggle to the right to configure the entries to never expire:</span></span> ![Inschakelen](../../media/scc-toggle-on.png)<span data-ttu-id="036b5-164">.</span><span class="sxs-lookup"><span data-stu-id="036b5-164">.</span></span>

   - <span data-ttu-id="036b5-165">**Optionele opmerking:** voer beschrijvende tekst in voor de vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="036b5-165">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="036b5-166">Klik op Toevoegen wanneer u **klaar bent.**</span><span class="sxs-lookup"><span data-stu-id="036b5-166">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="036b5-167">Het beveiligings- & compliancecentrum gebruiken om vermeldingen in de lijst Met toegestane/geblokkeerde tenants weer te geven</span><span class="sxs-lookup"><span data-stu-id="036b5-167">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="036b5-168">Ga in het & compliancecentrum  naar de tenant Voor \>  \> **risicobeheerbeleid : toegestane/geblokkeerde lijsten.**</span><span class="sxs-lookup"><span data-stu-id="036b5-168">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="036b5-169">Selecteer het **tabblad URL's** of het **tabblad** Bestanden.</span><span class="sxs-lookup"><span data-stu-id="036b5-169">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="036b5-170">Klik op de volgende kolomkoppen om in oplopende of aflopende volgorde te sorteren:</span><span class="sxs-lookup"><span data-stu-id="036b5-170">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="036b5-171">**Waarde:** de URL of de bestandshash.</span><span class="sxs-lookup"><span data-stu-id="036b5-171">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="036b5-172">**Laatst bijgewerkte datum**</span><span class="sxs-lookup"><span data-stu-id="036b5-172">**Last updated date**</span></span>
- <span data-ttu-id="036b5-173">**Vervaldatum**</span><span class="sxs-lookup"><span data-stu-id="036b5-173">**Expiration date**</span></span>
- <span data-ttu-id="036b5-174">**Opmerking**</span><span class="sxs-lookup"><span data-stu-id="036b5-174">**Note**</span></span>

<span data-ttu-id="036b5-175">Klik **op** Zoeken, voer een waarde in (een deel ervan) en druk op Enter om een specifieke waarde te zoeken.</span><span class="sxs-lookup"><span data-stu-id="036b5-175">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="036b5-176">Wanneer u klaar bent, klikt u op **het pictogram Zoeken** ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) verwijderen.</span><span class="sxs-lookup"><span data-stu-id="036b5-176">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="036b5-177">Klik **op Filter.**</span><span class="sxs-lookup"><span data-stu-id="036b5-177">Click **Filter**.</span></span> <span data-ttu-id="036b5-178">Configureer **een van** de volgende instellingen in de flyout Filter die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="036b5-178">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="036b5-179">**Nooit verlopen:** uit- of ![ ](../../media/scc-toggle-off.png) uitschakelen: ![ In-/uitschakelen: In-/uitschakelen. ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="036b5-179">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="036b5-180">**Laatst bijgewerkt:** Selecteer een begindatum **(Van),** een einddatum **(Aan)** of beide.</span><span class="sxs-lookup"><span data-stu-id="036b5-180">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="036b5-181">**Vervaldatum:** selecteer een begindatum **(van),** een einddatum **(aan)** of beide.</span><span class="sxs-lookup"><span data-stu-id="036b5-181">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="036b5-182">Klik op Toepassen wanneer u **klaar bent.**</span><span class="sxs-lookup"><span data-stu-id="036b5-182">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="036b5-183">Als u bestaande filters wilt wissen, klikt u op **Filter** en klikt u in de **flyout** Filter die wordt weergegeven op **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="036b5-183">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="036b5-184">Gebruik het beveiligingscentrum & blokkeringsgegevens in de lijst Met tenant toestaan/blokkeren te wijzigen</span><span class="sxs-lookup"><span data-stu-id="036b5-184">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="036b5-185">U kunt de bestaande geblokkeerde URL of bestandswaarden in een vermelding niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="036b5-185">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="036b5-186">Als u deze waarden wilt wijzigen, moet u de vermelding verwijderen en opnieuw maken.</span><span class="sxs-lookup"><span data-stu-id="036b5-186">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="036b5-187">Ga in het & compliancecentrum  naar de tenant Voor \>  \> **risicobeheerbeleid : toegestane/geblokkeerde lijsten.**</span><span class="sxs-lookup"><span data-stu-id="036b5-187">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="036b5-188">Selecteer het **tabblad URL's** of het **tabblad** Bestanden.</span><span class="sxs-lookup"><span data-stu-id="036b5-188">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="036b5-189">Selecteer het blok dat u wilt wijzigen en klik op **het pictogram** ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) Bewerken.</span><span class="sxs-lookup"><span data-stu-id="036b5-189">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="036b5-190">Configureer de volgende instellingen in de flyout die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="036b5-190">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="036b5-191">**Verloopt nooit:** ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="036b5-191">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="036b5-192">Controleer of de instelling is uitgeschakeld (in-/uitschakelen) en gebruik het vak Verloopt in om de vervaldatum voor de vermelding ![ ](../../media/scc-toggle-off.png) op te geven. </span><span class="sxs-lookup"><span data-stu-id="036b5-192">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

       <span data-ttu-id="036b5-193">of</span><span class="sxs-lookup"><span data-stu-id="036b5-193">or</span></span>

     - <span data-ttu-id="036b5-194">Verplaats de schakelknop naar rechts om de vermelding zo te configureren dat deze nooit verloopt:</span><span class="sxs-lookup"><span data-stu-id="036b5-194">Move the toggle to the right to configure the entry to never expire:</span></span> ![Inschakelen](../../media/scc-toggle-on.png)<span data-ttu-id="036b5-196">.</span><span class="sxs-lookup"><span data-stu-id="036b5-196">.</span></span>

   - <span data-ttu-id="036b5-197">**Optionele opmerking:** voer een beschrijvende tekst voor de invoer in.</span><span class="sxs-lookup"><span data-stu-id="036b5-197">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="036b5-198">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="036b5-198">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="036b5-199">Het beveiligings- & compliancecentrum gebruiken om geblokkeerde items uit de lijst Met toegestane/geblokkeerde tenants te verwijderen</span><span class="sxs-lookup"><span data-stu-id="036b5-199">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="036b5-200">Ga in het & compliancecentrum  naar de tenant Voor \>  \> **risicobeheerbeleid : toegestane/geblokkeerde lijsten.**</span><span class="sxs-lookup"><span data-stu-id="036b5-200">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="036b5-201">Selecteer het **tabblad URL's** of het **tabblad** Bestanden.</span><span class="sxs-lookup"><span data-stu-id="036b5-201">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="036b5-202">Selecteer het blok dat u wilt verwijderen en klik op **het pictogram** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) Verwijderen.</span><span class="sxs-lookup"><span data-stu-id="036b5-202">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="036b5-203">Klik in het waarschuwingsvenster dat wordt weergegeven op **Verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="036b5-203">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="036b5-204">Exchange Online PowerShell of een zelfstandige EOP PowerShell gebruiken om de lijst met tenants toestaan/blokkeren te configureren</span><span class="sxs-lookup"><span data-stu-id="036b5-204">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="036b5-205">PowerShell gebruiken om geblokkeerde items toe te voegen aan de lijst Met toegestane/geblokkeerde tenants</span><span class="sxs-lookup"><span data-stu-id="036b5-205">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="036b5-206">Gebruik de volgende syntaxis om geblokkeerde items toe te voegen aan de tenantlijst Toestaan/Blokkeren:</span><span class="sxs-lookup"><span data-stu-id="036b5-206">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="036b5-207">In dit voorbeeld wordt een BLOK-URL-vermelding toegevoegd voor contoso.com en alle subdomeinen (bijvoorbeeld contoso.com, www.contoso.com en xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="036b5-207">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="036b5-208">Omdat we de parameters ExpirationDate of NoExpiration niet hebben gebruikt, verloopt de invoer na 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="036b5-208">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="036b5-209">In dit voorbeeld wordt een blokkeringsbestandsinvoer toegevoegd voor de opgegeven bestanden die nooit verlopen.</span><span class="sxs-lookup"><span data-stu-id="036b5-209">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="036b5-210">Zie [New-TenantAllowBlockListItems voor](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="036b5-210">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="036b5-211">PowerShell gebruiken om vermeldingen in de lijst Toestaan/blokkeren van tenants weer te geven</span><span class="sxs-lookup"><span data-stu-id="036b5-211">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="036b5-212">Gebruik de volgende syntaxis om vermeldingen weer te geven in de lijst Met toegestane/geblokkeerde tenants:</span><span class="sxs-lookup"><span data-stu-id="036b5-212">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="036b5-213">In dit voorbeeld worden alle geblokkeerde URL's als retourneert.</span><span class="sxs-lookup"><span data-stu-id="036b5-213">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="036b5-214">In dit voorbeeld worden gegevens voor de opgegeven hash-waarde voor het bestand als resultaat gegeven.</span><span class="sxs-lookup"><span data-stu-id="036b5-214">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="036b5-215">Zie [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="036b5-215">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="036b5-216">PowerShell gebruiken om geblokkeerde items in de lijst Met tenant toestaan/blokkeren te wijzigen</span><span class="sxs-lookup"><span data-stu-id="036b5-216">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="036b5-217">U kunt de bestaande URL- of bestandswaarden in een blokinvoer niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="036b5-217">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="036b5-218">Als u deze waarden wilt wijzigen, moet u de vermelding verwijderen en opnieuw maken.</span><span class="sxs-lookup"><span data-stu-id="036b5-218">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="036b5-219">Gebruik de volgende syntaxis om geblokkeerde items in de tenantlijst toestaan/blokkeren te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="036b5-219">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="036b5-220">In dit voorbeeld wordt de vervaldatum van de opgegeven blokinvoer gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="036b5-220">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="036b5-221">Zie [Set-TenantAllowBlockListItems voor](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="036b5-221">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="036b5-222">PowerShell gebruiken om geblokkeerde items uit de lijst Met toegestane/geblokkeerde tenants te verwijderen</span><span class="sxs-lookup"><span data-stu-id="036b5-222">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="036b5-223">Gebruik de volgende syntaxis om geblokkeerde items uit de lijst Met tenant toestaan/blokkeren te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="036b5-223">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="036b5-224">In dit voorbeeld wordt het opgegeven blok url-item verwijderd uit de lijst met toegestane/geblokkeerde tenants.</span><span class="sxs-lookup"><span data-stu-id="036b5-224">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="036b5-225">Zie [Remove-TenantAllowBlockListItems voor gedetailleerde](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="036b5-225">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="036b5-226">Url-syntaxis voor de lijst met tenants toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="036b5-226">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="036b5-227">IP4v- en IPv6-adressen zijn toegestaan, maar TCP/UDP-poorten niet.</span><span class="sxs-lookup"><span data-stu-id="036b5-227">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="036b5-228">Bestandsextensies zijn niet toegestaan (bijvoorbeeld test.pdf).</span><span class="sxs-lookup"><span data-stu-id="036b5-228">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="036b5-229">Unicode wordt niet ondersteund, maar Punycode wel.</span><span class="sxs-lookup"><span data-stu-id="036b5-229">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="036b5-230">Hostnamen zijn toegestaan als alle volgende instructies waar zijn:</span><span class="sxs-lookup"><span data-stu-id="036b5-230">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="036b5-231">De hostnaam bevat een punt.</span><span class="sxs-lookup"><span data-stu-id="036b5-231">The hostname contains a period.</span></span>
  - <span data-ttu-id="036b5-232">Er staat ten minste één teken links van de punt.</span><span class="sxs-lookup"><span data-stu-id="036b5-232">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="036b5-233">Er staan ten minste twee tekens rechts van de punt.</span><span class="sxs-lookup"><span data-stu-id="036b5-233">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="036b5-234">Is bijvoorbeeld `t.co` toegestaan of `.com` niet `contoso.` toegestaan.</span><span class="sxs-lookup"><span data-stu-id="036b5-234">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="036b5-235">Subpaths worden niet geïmpliceerd.</span><span class="sxs-lookup"><span data-stu-id="036b5-235">Subpaths are not implied.</span></span>

  <span data-ttu-id="036b5-236">Bevat bijvoorbeeld `contoso.com` niet `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="036b5-236">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="036b5-237">Jokertekens (\*) zijn toegestaan in de volgende scenario's:</span><span class="sxs-lookup"><span data-stu-id="036b5-237">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="036b5-238">Een linker-jokerteken moet worden gevolgd door een punt om een subdomein op te geven.</span><span class="sxs-lookup"><span data-stu-id="036b5-238">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="036b5-239">Is bijvoorbeeld `*.contoso.com` toegestaan; `*contoso.com` is niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="036b5-239">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="036b5-240">Een rechter-jokerteken moet een slash (/) volgen om een pad op te geven.</span><span class="sxs-lookup"><span data-stu-id="036b5-240">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="036b5-241">Is bijvoorbeeld `contoso.com/*` toegestaan of `contoso.com*` niet `contoso.com/ab*` toegestaan.</span><span class="sxs-lookup"><span data-stu-id="036b5-241">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="036b5-242">Alle subpaths worden niet geïmpliceerd door een rechter jokerteken.</span><span class="sxs-lookup"><span data-stu-id="036b5-242">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="036b5-243">Bevat bijvoorbeeld `contoso.com/*` niet `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="036b5-243">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="036b5-244">`*.com*` ongeldig is (geen omsloten domein en het rechter jokerteken volgt geen slash).</span><span class="sxs-lookup"><span data-stu-id="036b5-244">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="036b5-245">Jokertekens zijn niet toegestaan in IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="036b5-245">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="036b5-246">Het tildeteken (~) is beschikbaar in de volgende scenario's:</span><span class="sxs-lookup"><span data-stu-id="036b5-246">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="036b5-247">Een linker tilde betekent een domein en alle subdomeinen.</span><span class="sxs-lookup"><span data-stu-id="036b5-247">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="036b5-248">Bijvoorbeeld inclusief `~contoso.com` `contoso.com` en `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="036b5-248">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="036b5-249">URL-vermeldingen die protocollen bevatten (bijvoorbeeld , of ) mislukken, omdat URL-vermeldingen van toepassing zijn `http://` `https://` op alle `ftp://` protocollen.</span><span class="sxs-lookup"><span data-stu-id="036b5-249">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="036b5-250">Een gebruikersnaam of wachtwoord wordt niet ondersteund of is niet vereist.</span><span class="sxs-lookup"><span data-stu-id="036b5-250">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="036b5-251">Aanhalingstekens (' of ") zijn ongeldige tekens.</span><span class="sxs-lookup"><span data-stu-id="036b5-251">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="036b5-252">Een URL moet waar mogelijk alle omleidingen bevatten.</span><span class="sxs-lookup"><span data-stu-id="036b5-252">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="036b5-253">Scenario's voor URL-invoer</span><span class="sxs-lookup"><span data-stu-id="036b5-253">URL entry scenarios</span></span>

<span data-ttu-id="036b5-254">Geldige URL-vermeldingen en de resultaten worden in de volgende secties beschreven.</span><span class="sxs-lookup"><span data-stu-id="036b5-254">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="036b5-255">Scenario: Geen jokertekens</span><span class="sxs-lookup"><span data-stu-id="036b5-255">Scenario: No wildcards</span></span>

<span data-ttu-id="036b5-256">**Invoer:**`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="036b5-256">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="036b5-257">**Overeenkomst toestaan**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-257">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="036b5-258">**Geen overeenkomst toestaan:**</span><span class="sxs-lookup"><span data-stu-id="036b5-258">**Allow not matched**:</span></span>

  - <span data-ttu-id="036b5-259">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-259">abc-contoso.com</span></span>
  - <span data-ttu-id="036b5-260">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="036b5-260">contoso.com/a</span></span>
  - <span data-ttu-id="036b5-261">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-261">payroll.contoso.com</span></span>
  - <span data-ttu-id="036b5-262">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-262">test.com/contoso.com</span></span>
  - <span data-ttu-id="036b5-263">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-263">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="036b5-264">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-264">www.contoso.com</span></span>
  - <span data-ttu-id="036b5-265">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-265">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="036b5-266">**Overeenkomst blokkeren:**</span><span class="sxs-lookup"><span data-stu-id="036b5-266">**Block match**:</span></span>

  - <span data-ttu-id="036b5-267">contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-267">contoso.com</span></span>
  - <span data-ttu-id="036b5-268">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="036b5-268">contoso.com/a</span></span>
  - <span data-ttu-id="036b5-269">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-269">payroll.contoso.com</span></span>
  - <span data-ttu-id="036b5-270">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-270">test.com/contoso.com</span></span>
  - <span data-ttu-id="036b5-271">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-271">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="036b5-272">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-272">www.contoso.com</span></span>
  - <span data-ttu-id="036b5-273">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-273">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="036b5-274">**Blok komt niet overeen:** abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-274">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="036b5-275">Scenario: Linker-jokerteken (subdomein)</span><span class="sxs-lookup"><span data-stu-id="036b5-275">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="036b5-276">**Invoer:**`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="036b5-276">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="036b5-277">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="036b5-277">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="036b5-278">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-278">www.contoso.com</span></span>
  - <span data-ttu-id="036b5-279">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-279">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="036b5-280">**Geen overeenkomst van overeenkomst toestaan** en Blokkeren niet **overeen:**</span><span class="sxs-lookup"><span data-stu-id="036b5-280">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="036b5-281">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-281">123contoso.com</span></span>
  - <span data-ttu-id="036b5-282">contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-282">contoso.com</span></span>
  - <span data-ttu-id="036b5-283">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-283">test.com/contoso.com</span></span>
  - <span data-ttu-id="036b5-284">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="036b5-284">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="036b5-285">Scenario: Rechts-jokerteken boven aan pad</span><span class="sxs-lookup"><span data-stu-id="036b5-285">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="036b5-286">**Invoer:**`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="036b5-286">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="036b5-287">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="036b5-287">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="036b5-288">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="036b5-288">contoso.com/a/b</span></span>
  - <span data-ttu-id="036b5-289">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="036b5-289">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="036b5-290">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="036b5-290">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="036b5-291">**Geen overeenkomst van overeenkomst toestaan** en Blokkeren niet **overeen:**</span><span class="sxs-lookup"><span data-stu-id="036b5-291">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="036b5-292">contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-292">contoso.com</span></span>
  - <span data-ttu-id="036b5-293">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="036b5-293">contoso.com/a</span></span>
  - <span data-ttu-id="036b5-294">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-294">www.contoso.com</span></span>
  - <span data-ttu-id="036b5-295">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-295">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="036b5-296">Scenario: Linker tilde</span><span class="sxs-lookup"><span data-stu-id="036b5-296">Scenario: Left tilde</span></span>

<span data-ttu-id="036b5-297">**Invoer:**`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="036b5-297">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="036b5-298">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="036b5-298">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="036b5-299">contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-299">contoso.com</span></span>
  - <span data-ttu-id="036b5-300">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-300">www.contoso.com</span></span>
  - <span data-ttu-id="036b5-301">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-301">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="036b5-302">**Geen overeenkomst van overeenkomst toestaan** en Blokkeren niet **overeen:**</span><span class="sxs-lookup"><span data-stu-id="036b5-302">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="036b5-303">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-303">123contoso.com</span></span>
  - <span data-ttu-id="036b5-304">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="036b5-304">contoso.com/abc</span></span>
  - <span data-ttu-id="036b5-305">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="036b5-305">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="036b5-306">Scenario: Rechts jokertekenachtervoegsel</span><span class="sxs-lookup"><span data-stu-id="036b5-306">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="036b5-307">**Invoer:**`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="036b5-307">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="036b5-308">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="036b5-308">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="036b5-309">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="036b5-309">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="036b5-310">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="036b5-310">contoso.com/a</span></span>
  - <span data-ttu-id="036b5-311">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="036b5-311">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="036b5-312">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="036b5-312">contoso.com/ab</span></span>
  - <span data-ttu-id="036b5-313">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="036b5-313">contoso.com/b</span></span>
  - <span data-ttu-id="036b5-314">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="036b5-314">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="036b5-315">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="036b5-315">contoso.com/ba</span></span>

- <span data-ttu-id="036b5-316">**Geen overeenkomst toestaan en** **Blokkeren niet overeen:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-316">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="036b5-317">Scenario: Linker-jokertekensubdomein en rechterachtervoegsel met jokerteken</span><span class="sxs-lookup"><span data-stu-id="036b5-317">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="036b5-318">**Invoer:**`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="036b5-318">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="036b5-319">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="036b5-319">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="036b5-320">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="036b5-320">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="036b5-321">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="036b5-321">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="036b5-322">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="036b5-322">www.contoso.com/a</span></span>
  - <span data-ttu-id="036b5-323">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="036b5-323">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="036b5-324">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="036b5-324">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="036b5-325">**Geen overeenkomst toestaan en** **Blokkeren niet overeen:** contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="036b5-325">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="036b5-326">Scenario: Linker- en rechtert tilde</span><span class="sxs-lookup"><span data-stu-id="036b5-326">Scenario: Left and right tilde</span></span>

<span data-ttu-id="036b5-327">**Invoer:**`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="036b5-327">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="036b5-328">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="036b5-328">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="036b5-329">contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-329">contoso.com</span></span>
  - <span data-ttu-id="036b5-330">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="036b5-330">contoso.com/a</span></span>
  - <span data-ttu-id="036b5-331">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-331">www.contoso.com</span></span>
  - <span data-ttu-id="036b5-332">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="036b5-332">www.contoso.com/b</span></span>
  - <span data-ttu-id="036b5-333">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-333">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="036b5-334">**Geen overeenkomst van overeenkomst toestaan** en Blokkeren niet **overeen:**</span><span class="sxs-lookup"><span data-stu-id="036b5-334">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="036b5-335">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-335">123contoso.com</span></span>
  - <span data-ttu-id="036b5-336">contoso.org</span><span class="sxs-lookup"><span data-stu-id="036b5-336">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="036b5-337">Scenario: IP-adres</span><span class="sxs-lookup"><span data-stu-id="036b5-337">Scenario: IP address</span></span>

<span data-ttu-id="036b5-338">**Invoer:**`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="036b5-338">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="036b5-339">**Overeenkomst en** **overeenkomst blokkeren toestaan:** 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="036b5-339">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="036b5-340">**Geen overeenkomst van overeenkomst toestaan** en Blokkeren niet **overeen:**</span><span class="sxs-lookup"><span data-stu-id="036b5-340">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="036b5-341">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="036b5-341">1.2.3.4/a</span></span>
  - <span data-ttu-id="036b5-342">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="036b5-342">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="036b5-343">IP-adres met rechter jokerteken</span><span class="sxs-lookup"><span data-stu-id="036b5-343">IP address with right wildcard</span></span>

<span data-ttu-id="036b5-344">**Invoer:**`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="036b5-344">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="036b5-345">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="036b5-345">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="036b5-346">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="036b5-346">1.2.3.4/b</span></span>
  - <span data-ttu-id="036b5-347">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="036b5-347">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="036b5-348">Voorbeelden van ongeldige vermeldingen</span><span class="sxs-lookup"><span data-stu-id="036b5-348">Examples of invalid entries</span></span>

<span data-ttu-id="036b5-349">De volgende vermeldingen zijn ongeldig:</span><span class="sxs-lookup"><span data-stu-id="036b5-349">The following entries are invalid:</span></span>

- <span data-ttu-id="036b5-350">**Ontbrekende of ongeldige domeinwaarden:**</span><span class="sxs-lookup"><span data-stu-id="036b5-350">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="036b5-351">contoso</span><span class="sxs-lookup"><span data-stu-id="036b5-351">contoso</span></span>
  - <span data-ttu-id="036b5-352">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="036b5-352">\*.contoso.\*</span></span>
  - <span data-ttu-id="036b5-353">\*.COM</span><span class="sxs-lookup"><span data-stu-id="036b5-353">\*.com</span></span>
  - <span data-ttu-id="036b5-354">\*.PDF</span><span class="sxs-lookup"><span data-stu-id="036b5-354">\*.pdf</span></span>

- <span data-ttu-id="036b5-355">**Jokertekens in tekst of zonder spatiëringstekens:**</span><span class="sxs-lookup"><span data-stu-id="036b5-355">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="036b5-356">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="036b5-356">\*contoso.com</span></span>
  - <span data-ttu-id="036b5-357">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="036b5-357">contoso.com\*</span></span>
  - <span data-ttu-id="036b5-358">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="036b5-358">\*1.2.3.4</span></span>
  - <span data-ttu-id="036b5-359">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="036b5-359">1.2.3.4\*</span></span>
  - <span data-ttu-id="036b5-360">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="036b5-360">contoso.com/a\*</span></span>
  - <span data-ttu-id="036b5-361">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="036b5-361">contoso.com/ab\*</span></span>

- <span data-ttu-id="036b5-362">**IP-adressen met poorten:**</span><span class="sxs-lookup"><span data-stu-id="036b5-362">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="036b5-363">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="036b5-363">contoso.com:443</span></span>
  - <span data-ttu-id="036b5-364">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="036b5-364">abc.contoso.com:25</span></span>

- <span data-ttu-id="036b5-365">**Niet-beschrijvende jokertekens:**</span><span class="sxs-lookup"><span data-stu-id="036b5-365">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="036b5-366">\*.\*</span><span class="sxs-lookup"><span data-stu-id="036b5-366">\*.\*</span></span>

- <span data-ttu-id="036b5-367">**Middelste jokertekens:**</span><span class="sxs-lookup"><span data-stu-id="036b5-367">**Middle wildcards**:</span></span>

  - <span data-ttu-id="036b5-368">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="036b5-368">conto\*so.com</span></span>
  - <span data-ttu-id="036b5-369">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="036b5-369">conto~so.com</span></span>

- <span data-ttu-id="036b5-370">**Dubbele jokertekens**</span><span class="sxs-lookup"><span data-stu-id="036b5-370">**Double wildcards**</span></span>

  - <span data-ttu-id="036b5-371">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="036b5-371">contoso.com/\*\*</span></span>
  - <span data-ttu-id="036b5-372">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="036b5-372">contoso.com/\*/\*</span></span>
