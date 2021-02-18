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
ms.openlocfilehash: 250b6223ffe663e0cd950069a3c3c7827b4aa57b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290163"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="a92f8-103">Tenant Toestaan/Blokkeren-lijst beheren</span><span class="sxs-lookup"><span data-stu-id="a92f8-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a92f8-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="a92f8-104">**Applies to**</span></span>
- [<span data-ttu-id="a92f8-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a92f8-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a92f8-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="a92f8-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="a92f8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a92f8-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
>
> <span data-ttu-id="a92f8-108">De functies die in dit artikel worden beschreven, zijn in preview beschikbaar, kunnen worden gewijzigd en zijn niet in alle organisaties beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="a92f8-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>
>
> <span data-ttu-id="a92f8-109">U kunt momenteel geen **toegestane** items configureren in de tenantlijst Toestaan/Blokkeren.</span><span class="sxs-lookup"><span data-stu-id="a92f8-109">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="a92f8-110">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken, bent u het mogelijk niet eens met de filtering van EOP.</span><span class="sxs-lookup"><span data-stu-id="a92f8-110">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="a92f8-111">Een goed bericht kan bijvoorbeeld als slecht zijn gemarkeerd (een fout-positief) of een slecht bericht kan zijn toegestaan (een fout-negatief).</span><span class="sxs-lookup"><span data-stu-id="a92f8-111">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="a92f8-112">Met de lijst met tenants toestaan/blokkeren in het & compliancecentrum kunt u het filterbeleid van Microsoft 365 handmatig overschrijven.</span><span class="sxs-lookup"><span data-stu-id="a92f8-112">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="a92f8-113">De tenantlijst toestaan/blokkeren wordt gebruikt tijdens de e-mailstroom en tijdens het klikken door de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="a92f8-113">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="a92f8-114">U kunt URL's of bestanden opgeven die u altijd wilt blokkeren.</span><span class="sxs-lookup"><span data-stu-id="a92f8-114">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="a92f8-115">In dit artikel wordt beschreven hoe u vermeldingen configureert in de lijst Tenant toestaan/blokkeren in het beveiligings- & compliancecentrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).</span><span class="sxs-lookup"><span data-stu-id="a92f8-115">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a92f8-116">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="a92f8-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a92f8-117">U opent het beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="a92f8-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="a92f8-118">Als u rechtstreeks naar de **pagina Tenant toestaan/blokkeren wilt** gaan, gebruikt u <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="a92f8-118">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="a92f8-119">U geeft bestanden op met de hashwaarde SHA256 van het bestand.</span><span class="sxs-lookup"><span data-stu-id="a92f8-119">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="a92f8-120">U kunt de SHA256-hashwaarde van een bestand in Windows vinden door de volgende opdracht uit te voeren in een opdrachtprompt:</span><span class="sxs-lookup"><span data-stu-id="a92f8-120">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="a92f8-121">Een voorbeeldwaarde is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="a92f8-121">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="a92f8-122">Perceptual hash (pHash) waarden worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="a92f8-122">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="a92f8-123">De beschikbare URL-waarden worden beschreven in de [URL-syntaxis voor de sectie Toestaan/blokkeerlijst](#url-syntax-for-the-tenant-allowblock-list) voor tenants verderop in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="a92f8-123">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="a92f8-124">De tenantlijst toestaan/blokkeren biedt maximaal 500 vermeldingen voor URL's en 500 vermeldingen voor bestand-hashes.</span><span class="sxs-lookup"><span data-stu-id="a92f8-124">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="a92f8-125">Een item moet binnen 15 minuten actief zijn.</span><span class="sxs-lookup"><span data-stu-id="a92f8-125">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="a92f8-126">Standaard verlopen vermeldingen in de lijst met toegestane/geblokkeerde tenants na 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="a92f8-126">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="a92f8-127">U kunt een datum opgeven of instellen dat deze nooit verloopt.</span><span class="sxs-lookup"><span data-stu-id="a92f8-127">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="a92f8-128">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a92f8-128">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a92f8-129">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a92f8-129">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a92f8-130">Je moet beschikken over toegewezen machtigingen in het Beveiligings- en compliancecentrum voor het uitvoeren van de procedures in dit onderwerp:</span><span class="sxs-lookup"><span data-stu-id="a92f8-130">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="a92f8-131">Als u waarden wilt toevoegen aan en verwijderen uit de tenantlijst toestaan/blokkeren, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="a92f8-131">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="a92f8-132">Voor alleen-lezen toegang tot de tenantlijst Toestaan/Blokkeren moet  u lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="a92f8-132">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="a92f8-133">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a92f8-133">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="a92f8-134">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="a92f8-134">**Notes**:</span></span>

  - <span data-ttu-id="a92f8-135">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a92f8-135">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="a92f8-136">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a92f8-136">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="a92f8-137">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="a92f8-137">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a92f8-138">Gebruik het beveiligings- & compliancecentrum om URL-vermeldingen te maken in de lijst Met toegestane/geblokkeerde tenants</span><span class="sxs-lookup"><span data-stu-id="a92f8-138">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a92f8-139">Zie de syntaxis van de URL voor de sectie Lijst met tenants [toestaan/blokkeren](#url-syntax-for-the-tenant-allowblock-list) verderop in dit artikel voor meer informatie over de syntaxis voor URL-vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="a92f8-139">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="a92f8-140">Ga in het & compliancecentrum  naar de tenant Voor \>  \> **risicobeheerbeleid : toegestane/geblokkeerde lijsten.**</span><span class="sxs-lookup"><span data-stu-id="a92f8-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a92f8-141">Controleer op **de pagina Tenant toestaan/blokkeren** of het tabblad **URL's** is geselecteerd en klik vervolgens op **Blokkeren**</span><span class="sxs-lookup"><span data-stu-id="a92f8-141">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="a92f8-142">Configureer **de volgende** instellingen in de flyout Blok-URL's die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="a92f8-142">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a92f8-143">**Url's toevoegen die u wilt blokkeren:** voer één URL per regel in, maximaal 20.</span><span class="sxs-lookup"><span data-stu-id="a92f8-143">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="a92f8-144">**Verloopt nooit:** ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="a92f8-144">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="a92f8-145">Controleer of de instelling is uitgeschakeld (in-/uitschakelen) en gebruik het vak Verloopt in om de vervaldatum voor de items ![ ](../../media/scc-toggle-off.png) op te geven. </span><span class="sxs-lookup"><span data-stu-id="a92f8-145">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="a92f8-146">of</span><span class="sxs-lookup"><span data-stu-id="a92f8-146">or</span></span>

     - <span data-ttu-id="a92f8-147">Verplaats de schakelknop naar rechts om de vermeldingen zo te configureren dat ze nooit verlopen:</span><span class="sxs-lookup"><span data-stu-id="a92f8-147">Move the toggle to the right to configure the entries to never expire:</span></span> ![Inschakelen](../../media/scc-toggle-on.png)<span data-ttu-id="a92f8-149">.</span><span class="sxs-lookup"><span data-stu-id="a92f8-149">.</span></span>

   - <span data-ttu-id="a92f8-150">**Optionele opmerking:** voer beschrijvende tekst in voor de vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="a92f8-150">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="a92f8-151">Klik op Toevoegen wanneer u **klaar bent.**</span><span class="sxs-lookup"><span data-stu-id="a92f8-151">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a92f8-152">Gebruik het beveiligings- & compliancecentrum om bestandsgegevens te maken in de lijst Met toegestane/geblokkeerde tenants</span><span class="sxs-lookup"><span data-stu-id="a92f8-152">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="a92f8-153">Ga in het & compliancecentrum  naar de tenant voor het \>  \> **risicobeheerbeleid : toegestane/geblokkeerde lijsten.**</span><span class="sxs-lookup"><span data-stu-id="a92f8-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a92f8-154">Selecteer op **de pagina Lijst met tenants toestaan/blokkeren** het tabblad Bestanden en klik op **Blokkeren.** </span><span class="sxs-lookup"><span data-stu-id="a92f8-154">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="a92f8-155">Configureer **de volgende instellingen in het dialoogvenster** Bestanden toevoegen om flyout te blokkeren die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="a92f8-155">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a92f8-156">**Bestandshashes toevoegen:** voer één SHA256-hashwaarde per regel in, tot maximaal 20.</span><span class="sxs-lookup"><span data-stu-id="a92f8-156">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="a92f8-157">**Verloopt nooit:** ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="a92f8-157">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="a92f8-158">Controleer of de instelling is uitgeschakeld (in-/uitschakelen) en gebruik het vak Verloopt in om de vervaldatum voor de items ![ ](../../media/scc-toggle-off.png) op te geven. </span><span class="sxs-lookup"><span data-stu-id="a92f8-158">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="a92f8-159">of</span><span class="sxs-lookup"><span data-stu-id="a92f8-159">or</span></span>

     - <span data-ttu-id="a92f8-160">Verplaats de schakelknop naar rechts om de vermeldingen zo te configureren dat ze nooit verlopen:</span><span class="sxs-lookup"><span data-stu-id="a92f8-160">Move the toggle to the right to configure the entries to never expire:</span></span> ![Inschakelen](../../media/scc-toggle-on.png)<span data-ttu-id="a92f8-162">.</span><span class="sxs-lookup"><span data-stu-id="a92f8-162">.</span></span>

   - <span data-ttu-id="a92f8-163">**Optionele opmerking:** voer beschrijvende tekst in voor de vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="a92f8-163">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="a92f8-164">Klik op Toevoegen wanneer u **klaar bent.**</span><span class="sxs-lookup"><span data-stu-id="a92f8-164">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a92f8-165">Het beveiligings- & compliancecentrum gebruiken om vermeldingen weer te geven in de lijst Met toegestane/geblokkeerde tenants</span><span class="sxs-lookup"><span data-stu-id="a92f8-165">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="a92f8-166">Ga in het & compliancecentrum  naar de tenant Voor \>  \> **risicobeheerbeleid : toegestane/geblokkeerde lijsten.**</span><span class="sxs-lookup"><span data-stu-id="a92f8-166">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a92f8-167">Selecteer het **tabblad URL's** of het **tabblad** Bestanden.</span><span class="sxs-lookup"><span data-stu-id="a92f8-167">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="a92f8-168">Klik op de volgende kolomkoppen om in oplopende of aflopende volgorde te sorteren:</span><span class="sxs-lookup"><span data-stu-id="a92f8-168">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="a92f8-169">**Waarde:** de URL of de bestandshash.</span><span class="sxs-lookup"><span data-stu-id="a92f8-169">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="a92f8-170">**Laatst bijgewerkte datum**</span><span class="sxs-lookup"><span data-stu-id="a92f8-170">**Last updated date**</span></span>
- <span data-ttu-id="a92f8-171">**Vervaldatum**</span><span class="sxs-lookup"><span data-stu-id="a92f8-171">**Expiration date**</span></span>
- <span data-ttu-id="a92f8-172">**Opmerking**</span><span class="sxs-lookup"><span data-stu-id="a92f8-172">**Note**</span></span>

<span data-ttu-id="a92f8-173">Klik **op** Zoeken, voer een waarde in (een deel ervan) en druk op Enter om een specifieke waarde te zoeken.</span><span class="sxs-lookup"><span data-stu-id="a92f8-173">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="a92f8-174">Wanneer u klaar bent, klikt u **op het pictogram Zoeken** ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) verwijderen.</span><span class="sxs-lookup"><span data-stu-id="a92f8-174">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="a92f8-175">Klik **op Filteren.**</span><span class="sxs-lookup"><span data-stu-id="a92f8-175">Click **Filter**.</span></span> <span data-ttu-id="a92f8-176">Configureer **een van** de volgende instellingen in de flyout Filter die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="a92f8-176">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="a92f8-177">**Nooit verlopen:** uit- of ![ ](../../media/scc-toggle-off.png) uitschakelen: ![ In-/uitschakelen: In-/uitschakelen. ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="a92f8-177">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="a92f8-178">**Laatst bijgewerkt:** selecteer een begindatum **(van),** een einddatum **(aan)** of beide.</span><span class="sxs-lookup"><span data-stu-id="a92f8-178">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="a92f8-179">**Vervaldatum:** selecteer een begindatum **(van),** een einddatum **(aan)** of beide.</span><span class="sxs-lookup"><span data-stu-id="a92f8-179">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="a92f8-180">Klik op Toepassen wanneer u **klaar bent.**</span><span class="sxs-lookup"><span data-stu-id="a92f8-180">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="a92f8-181">Als u bestaande filters wilt wissen, klikt u op **Filter** en klikt u in de **flyout** Filter die wordt weergegeven op **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="a92f8-181">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a92f8-182">Gebruik het beveiligings- & blokkeringsgegevens in de lijst met tenants toestaan/blokkeren te wijzigen</span><span class="sxs-lookup"><span data-stu-id="a92f8-182">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a92f8-183">U kunt de bestaande geblokkeerde URL of bestandswaarden in een vermelding niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="a92f8-183">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="a92f8-184">Als u deze waarden wilt wijzigen, moet u de vermelding verwijderen en opnieuw maken.</span><span class="sxs-lookup"><span data-stu-id="a92f8-184">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="a92f8-185">Ga in het & compliancecentrum  naar de tenant Voor \>  \> **risicobeheerbeleid : toegestane/geblokkeerde lijsten.**</span><span class="sxs-lookup"><span data-stu-id="a92f8-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a92f8-186">Selecteer het **tabblad URL's** of het **tabblad** Bestanden.</span><span class="sxs-lookup"><span data-stu-id="a92f8-186">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="a92f8-187">Selecteer het blok dat u wilt wijzigen en klik op **het pictogram** ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) Bewerken.</span><span class="sxs-lookup"><span data-stu-id="a92f8-187">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="a92f8-188">Configureer de volgende instellingen in de flyout die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="a92f8-188">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a92f8-189">**Verloopt nooit:** ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="a92f8-189">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="a92f8-190">Controleer of de instelling is uitgeschakeld (in-/uitschakelen) en gebruik het vak Verloopt in om de vervaldatum voor de vermelding ![ ](../../media/scc-toggle-off.png) op te geven. </span><span class="sxs-lookup"><span data-stu-id="a92f8-190">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="a92f8-191">of</span><span class="sxs-lookup"><span data-stu-id="a92f8-191">or</span></span>

     - <span data-ttu-id="a92f8-192">Verplaats de schakelknop naar rechts om de vermelding zo te configureren dat deze nooit verloopt:</span><span class="sxs-lookup"><span data-stu-id="a92f8-192">Move the toggle to the right to configure the entry to never expire:</span></span> ![Inschakelen](../../media/scc-toggle-on.png)<span data-ttu-id="a92f8-194">.</span><span class="sxs-lookup"><span data-stu-id="a92f8-194">.</span></span>

   - <span data-ttu-id="a92f8-195">**Optionele opmerking:** voer beschrijvende tekst voor de invoer in.</span><span class="sxs-lookup"><span data-stu-id="a92f8-195">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="a92f8-196">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="a92f8-196">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="a92f8-197">Het beveiligings- & compliancecentrum gebruiken om geblokkeerde items uit de lijst Met toegestane/geblokkeerde tenants te verwijderen</span><span class="sxs-lookup"><span data-stu-id="a92f8-197">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="a92f8-198">Ga in het & compliancecentrum  naar de tenant Voor \>  \> **risicobeheerbeleid : toegestane/geblokkeerde lijsten.**</span><span class="sxs-lookup"><span data-stu-id="a92f8-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a92f8-199">Selecteer het **tabblad URL's** of het **tabblad** Bestanden.</span><span class="sxs-lookup"><span data-stu-id="a92f8-199">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="a92f8-200">Selecteer het blok dat u wilt verwijderen en klik op **het pictogram** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) Verwijderen.</span><span class="sxs-lookup"><span data-stu-id="a92f8-200">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="a92f8-201">Klik in het waarschuwingsvenster dat wordt weergegeven op **Verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="a92f8-201">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="a92f8-202">Exchange Online PowerShell of een zelfstandige EOP PowerShell gebruiken om de lijst met tenants toestaan/blokkeren te configureren</span><span class="sxs-lookup"><span data-stu-id="a92f8-202">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="a92f8-203">PowerShell gebruiken om geblokkeerde items toe te voegen aan de lijst Met toegestane/geblokkeerde tenants</span><span class="sxs-lookup"><span data-stu-id="a92f8-203">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="a92f8-204">Gebruik de volgende syntaxis om geblokkeerde items toe te voegen aan de tenantlijst Toestaan/Blokkeren:</span><span class="sxs-lookup"><span data-stu-id="a92f8-204">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="a92f8-205">In dit voorbeeld wordt een BLOK-URL-vermelding toegevoegd voor contoso.com en alle subdomeinen (bijvoorbeeld contoso.com, www.contoso.com en xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="a92f8-205">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="a92f8-206">Omdat we de parameters ExpirationDate of NoExpiration niet hebben gebruikt, verloopt de invoer na 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="a92f8-206">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="a92f8-207">In dit voorbeeld wordt een blokkeringsbestandsinvoer toegevoegd voor de opgegeven bestanden die nooit verlopen.</span><span class="sxs-lookup"><span data-stu-id="a92f8-207">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="a92f8-208">Zie [New-TenantAllowBlockListItems voor](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="a92f8-208">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a92f8-209">PowerShell gebruiken om vermeldingen in de lijst Toestaan/blokkeren van tenants weer te geven</span><span class="sxs-lookup"><span data-stu-id="a92f8-209">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a92f8-210">Gebruik de volgende syntaxis om vermeldingen weer te geven in de lijst Met toegestane/geblokkeerde tenants:</span><span class="sxs-lookup"><span data-stu-id="a92f8-210">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="a92f8-211">In dit voorbeeld worden alle geblokkeerde URL's als retourneert.</span><span class="sxs-lookup"><span data-stu-id="a92f8-211">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="a92f8-212">In dit voorbeeld worden gegevens voor de opgegeven hash-waarde voor het bestand als resultaat gegeven.</span><span class="sxs-lookup"><span data-stu-id="a92f8-212">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="a92f8-213">Zie [Get-TenantAllowBlockListItems voor](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="a92f8-213">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a92f8-214">PowerShell gebruiken om geblokkeerde items in de lijst Met tenant toestaan/blokkeren te wijzigen</span><span class="sxs-lookup"><span data-stu-id="a92f8-214">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a92f8-215">U kunt de bestaande URL- of bestandswaarden in een blokinvoer niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="a92f8-215">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="a92f8-216">Als u deze waarden wilt wijzigen, moet u de vermelding verwijderen en opnieuw maken.</span><span class="sxs-lookup"><span data-stu-id="a92f8-216">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="a92f8-217">Gebruik de volgende syntaxis om geblokkeerde items in de tenantlijst toestaan/blokkeren te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="a92f8-217">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="a92f8-218">In dit voorbeeld wordt de vervaldatum van de opgegeven blokkeringsdatum gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="a92f8-218">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="a92f8-219">Zie [Set-TenantAllowBlockListItems voor](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="a92f8-219">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="a92f8-220">PowerShell gebruiken om geblokkeerde items uit de lijst Met toegestane/geblokkeerde tenants te verwijderen</span><span class="sxs-lookup"><span data-stu-id="a92f8-220">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="a92f8-221">Gebruik de volgende syntaxis om geblokkeerde items uit de lijst Met tenant toestaan/blokkeren te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="a92f8-221">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="a92f8-222">In dit voorbeeld wordt het opgegeven blok url-item verwijderd uit de lijst Met toegestane/geblokkeerde tenants.</span><span class="sxs-lookup"><span data-stu-id="a92f8-222">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="a92f8-223">Zie [Remove-TenantAllowBlockListItems voor gedetailleerde](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="a92f8-223">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="a92f8-224">Url-syntaxis voor de lijst met tenants toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="a92f8-224">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="a92f8-225">IP4v- en IPv6-adressen zijn toegestaan, maar TCP/UDP-poorten niet.</span><span class="sxs-lookup"><span data-stu-id="a92f8-225">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="a92f8-226">Bestandsextensies zijn niet toegestaan (bijvoorbeeld test.pdf).</span><span class="sxs-lookup"><span data-stu-id="a92f8-226">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="a92f8-227">Unicode wordt niet ondersteund, maar Punycode wel.</span><span class="sxs-lookup"><span data-stu-id="a92f8-227">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="a92f8-228">Hostnamen zijn toegestaan als alle volgende instructies waar zijn:</span><span class="sxs-lookup"><span data-stu-id="a92f8-228">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="a92f8-229">De hostnaam bevat een punt.</span><span class="sxs-lookup"><span data-stu-id="a92f8-229">The hostname contains a period.</span></span>
  - <span data-ttu-id="a92f8-230">Er staat ten minste één teken links van de punt.</span><span class="sxs-lookup"><span data-stu-id="a92f8-230">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="a92f8-231">Er staan ten minste twee tekens rechts van de punt.</span><span class="sxs-lookup"><span data-stu-id="a92f8-231">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="a92f8-232">Is bijvoorbeeld `t.co` toegestaan of `.com` niet `contoso.` toegestaan.</span><span class="sxs-lookup"><span data-stu-id="a92f8-232">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="a92f8-233">Subpaths worden niet geïmpliceerd.</span><span class="sxs-lookup"><span data-stu-id="a92f8-233">Subpaths are not implied.</span></span>

  <span data-ttu-id="a92f8-234">Bevat bijvoorbeeld `contoso.com` niet `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="a92f8-234">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="a92f8-235">Jokertekens (\*) zijn toegestaan in de volgende scenario's:</span><span class="sxs-lookup"><span data-stu-id="a92f8-235">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="a92f8-236">Een linker-jokerteken moet worden gevolgd door een punt om een subdomein op te geven.</span><span class="sxs-lookup"><span data-stu-id="a92f8-236">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="a92f8-237">Is bijvoorbeeld `*.contoso.com` toegestaan; `*contoso.com` is niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="a92f8-237">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="a92f8-238">Een rechter-jokerteken moet een slash (/) volgen om een pad op te geven.</span><span class="sxs-lookup"><span data-stu-id="a92f8-238">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="a92f8-239">Is bijvoorbeeld `contoso.com/*` toegestaan of `contoso.com*` niet `contoso.com/ab*` toegestaan.</span><span class="sxs-lookup"><span data-stu-id="a92f8-239">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="a92f8-240">Alle subpathen worden niet geïmpliceerd door een rechter jokerteken.</span><span class="sxs-lookup"><span data-stu-id="a92f8-240">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="a92f8-241">Bevat bijvoorbeeld `contoso.com/*` niet `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="a92f8-241">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="a92f8-242">`*.com*` ongeldig is (geen omsloten domein en het rechter jokerteken volgt geen slash).</span><span class="sxs-lookup"><span data-stu-id="a92f8-242">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="a92f8-243">Jokertekens zijn niet toegestaan in IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="a92f8-243">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="a92f8-244">Het tildeteken (~) is beschikbaar in de volgende scenario's:</span><span class="sxs-lookup"><span data-stu-id="a92f8-244">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="a92f8-245">Een linker tilde betekent een domein en alle subdomeinen.</span><span class="sxs-lookup"><span data-stu-id="a92f8-245">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="a92f8-246">Bijvoorbeeld inclusief `~contoso.com` `contoso.com` en `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="a92f8-246">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="a92f8-247">URL-vermeldingen die protocollen bevatten (bijvoorbeeld , of ) mislukken, omdat URL-vermeldingen van toepassing zijn `http://` `https://` op alle `ftp://` protocollen.</span><span class="sxs-lookup"><span data-stu-id="a92f8-247">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="a92f8-248">Een gebruikersnaam of wachtwoord wordt niet ondersteund of is niet vereist.</span><span class="sxs-lookup"><span data-stu-id="a92f8-248">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="a92f8-249">Aanhalingstekens (' of ") zijn ongeldige tekens.</span><span class="sxs-lookup"><span data-stu-id="a92f8-249">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="a92f8-250">Een URL moet waar mogelijk alle omleidingen bevatten.</span><span class="sxs-lookup"><span data-stu-id="a92f8-250">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="a92f8-251">Scenario's voor URL-invoer</span><span class="sxs-lookup"><span data-stu-id="a92f8-251">URL entry scenarios</span></span>

<span data-ttu-id="a92f8-252">Geldige URL-vermeldingen en de resultaten worden in de volgende secties beschreven.</span><span class="sxs-lookup"><span data-stu-id="a92f8-252">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="a92f8-253">Scenario: Geen jokertekens</span><span class="sxs-lookup"><span data-stu-id="a92f8-253">Scenario: No wildcards</span></span>

<span data-ttu-id="a92f8-254">**Invoer:**`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="a92f8-254">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="a92f8-255">**Overeenkomst toestaan**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-255">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="a92f8-256">**Geen overeenkomst toestaan:**</span><span class="sxs-lookup"><span data-stu-id="a92f8-256">**Allow not matched**:</span></span>

  - <span data-ttu-id="a92f8-257">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-257">abc-contoso.com</span></span>
  - <span data-ttu-id="a92f8-258">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a92f8-258">contoso.com/a</span></span>
  - <span data-ttu-id="a92f8-259">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-259">payroll.contoso.com</span></span>
  - <span data-ttu-id="a92f8-260">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-260">test.com/contoso.com</span></span>
  - <span data-ttu-id="a92f8-261">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-261">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="a92f8-262">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-262">www.contoso.com</span></span>
  - <span data-ttu-id="a92f8-263">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-263">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="a92f8-264">**Overeenkomst blokkeren:**</span><span class="sxs-lookup"><span data-stu-id="a92f8-264">**Block match**:</span></span>

  - <span data-ttu-id="a92f8-265">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-265">contoso.com</span></span>
  - <span data-ttu-id="a92f8-266">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a92f8-266">contoso.com/a</span></span>
  - <span data-ttu-id="a92f8-267">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-267">payroll.contoso.com</span></span>
  - <span data-ttu-id="a92f8-268">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-268">test.com/contoso.com</span></span>
  - <span data-ttu-id="a92f8-269">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-269">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="a92f8-270">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-270">www.contoso.com</span></span>
  - <span data-ttu-id="a92f8-271">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-271">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="a92f8-272">**Blok komt niet overeen:** abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-272">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="a92f8-273">Scenario: Linker-jokerteken (subdomein)</span><span class="sxs-lookup"><span data-stu-id="a92f8-273">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="a92f8-274">**Invoer:**`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="a92f8-274">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="a92f8-275">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="a92f8-275">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a92f8-276">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-276">www.contoso.com</span></span>
  - <span data-ttu-id="a92f8-277">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-277">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="a92f8-278">**Geen overeenkomst van overeenkomst toestaan** en Blokkeren niet **overeen:**</span><span class="sxs-lookup"><span data-stu-id="a92f8-278">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a92f8-279">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-279">123contoso.com</span></span>
  - <span data-ttu-id="a92f8-280">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-280">contoso.com</span></span>
  - <span data-ttu-id="a92f8-281">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-281">test.com/contoso.com</span></span>
  - <span data-ttu-id="a92f8-282">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="a92f8-282">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="a92f8-283">Scenario: Rechts-jokerteken boven aan pad</span><span class="sxs-lookup"><span data-stu-id="a92f8-283">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="a92f8-284">**Invoer:**`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="a92f8-284">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="a92f8-285">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="a92f8-285">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a92f8-286">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="a92f8-286">contoso.com/a/b</span></span>
  - <span data-ttu-id="a92f8-287">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="a92f8-287">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="a92f8-288">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-288">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="a92f8-289">**Geen overeenkomst van overeenkomst toestaan** en Blokkeren niet **overeen:**</span><span class="sxs-lookup"><span data-stu-id="a92f8-289">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a92f8-290">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-290">contoso.com</span></span>
  - <span data-ttu-id="a92f8-291">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a92f8-291">contoso.com/a</span></span>
  - <span data-ttu-id="a92f8-292">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-292">www.contoso.com</span></span>
  - <span data-ttu-id="a92f8-293">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-293">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="a92f8-294">Scenario: Linker tilde</span><span class="sxs-lookup"><span data-stu-id="a92f8-294">Scenario: Left tilde</span></span>

<span data-ttu-id="a92f8-295">**Invoer:**`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="a92f8-295">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="a92f8-296">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="a92f8-296">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a92f8-297">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-297">contoso.com</span></span>
  - <span data-ttu-id="a92f8-298">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-298">www.contoso.com</span></span>
  - <span data-ttu-id="a92f8-299">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-299">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="a92f8-300">**Geen overeenkomst van overeenkomst toestaan** en Blokkeren niet **overeen:**</span><span class="sxs-lookup"><span data-stu-id="a92f8-300">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a92f8-301">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-301">123contoso.com</span></span>
  - <span data-ttu-id="a92f8-302">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="a92f8-302">contoso.com/abc</span></span>
  - <span data-ttu-id="a92f8-303">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="a92f8-303">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="a92f8-304">Scenario: Rechts jokertekenachtervoegsel</span><span class="sxs-lookup"><span data-stu-id="a92f8-304">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="a92f8-305">**Invoer:**`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="a92f8-305">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="a92f8-306">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="a92f8-306">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a92f8-307">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-307">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="a92f8-308">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a92f8-308">contoso.com/a</span></span>
  - <span data-ttu-id="a92f8-309">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="a92f8-309">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="a92f8-310">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="a92f8-310">contoso.com/ab</span></span>
  - <span data-ttu-id="a92f8-311">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="a92f8-311">contoso.com/b</span></span>
  - <span data-ttu-id="a92f8-312">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="a92f8-312">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="a92f8-313">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="a92f8-313">contoso.com/ba</span></span>

- <span data-ttu-id="a92f8-314">**Geen overeenkomst toestaan en** **Blokkeren niet overeen:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-314">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="a92f8-315">Scenario: Linker-jokertekensubdomein en rechterachtervoegsel met jokertekens</span><span class="sxs-lookup"><span data-stu-id="a92f8-315">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="a92f8-316">**Invoer:**`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="a92f8-316">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="a92f8-317">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="a92f8-317">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a92f8-318">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="a92f8-318">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="a92f8-319">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="a92f8-319">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="a92f8-320">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a92f8-320">www.contoso.com/a</span></span>
  - <span data-ttu-id="a92f8-321">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="a92f8-321">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="a92f8-322">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="a92f8-322">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="a92f8-323">**Geen overeenkomst toestaan en** **Blokkeren niet overeen:** contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="a92f8-323">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="a92f8-324">Scenario: Tilde links en rechts</span><span class="sxs-lookup"><span data-stu-id="a92f8-324">Scenario: Left and right tilde</span></span>

<span data-ttu-id="a92f8-325">**Invoer:**`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="a92f8-325">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="a92f8-326">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="a92f8-326">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a92f8-327">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-327">contoso.com</span></span>
  - <span data-ttu-id="a92f8-328">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a92f8-328">contoso.com/a</span></span>
  - <span data-ttu-id="a92f8-329">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-329">www.contoso.com</span></span>
  - <span data-ttu-id="a92f8-330">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="a92f8-330">www.contoso.com/b</span></span>
  - <span data-ttu-id="a92f8-331">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-331">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="a92f8-332">**Geen overeenkomst van overeenkomst toestaan** en Blokkeren niet **overeen:**</span><span class="sxs-lookup"><span data-stu-id="a92f8-332">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a92f8-333">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-333">123contoso.com</span></span>
  - <span data-ttu-id="a92f8-334">contoso.org</span><span class="sxs-lookup"><span data-stu-id="a92f8-334">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="a92f8-335">Scenario: IP-adres</span><span class="sxs-lookup"><span data-stu-id="a92f8-335">Scenario: IP address</span></span>

<span data-ttu-id="a92f8-336">**Invoer:**`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="a92f8-336">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="a92f8-337">**Overeenkomst en** **overeenkomst blokkeren toestaan:** 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="a92f8-337">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="a92f8-338">**Geen overeenkomst van overeenkomst toestaan** en Blokkeren niet **overeen:**</span><span class="sxs-lookup"><span data-stu-id="a92f8-338">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a92f8-339">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="a92f8-339">1.2.3.4/a</span></span>
  - <span data-ttu-id="a92f8-340">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="a92f8-340">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="a92f8-341">IP-adres met rechter jokerteken</span><span class="sxs-lookup"><span data-stu-id="a92f8-341">IP address with right wildcard</span></span>

<span data-ttu-id="a92f8-342">**Invoer:**`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="a92f8-342">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="a92f8-343">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="a92f8-343">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a92f8-344">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="a92f8-344">1.2.3.4/b</span></span>
  - <span data-ttu-id="a92f8-345">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="a92f8-345">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="a92f8-346">Voorbeelden van ongeldige vermeldingen</span><span class="sxs-lookup"><span data-stu-id="a92f8-346">Examples of invalid entries</span></span>

<span data-ttu-id="a92f8-347">De volgende vermeldingen zijn ongeldig:</span><span class="sxs-lookup"><span data-stu-id="a92f8-347">The following entries are invalid:</span></span>

- <span data-ttu-id="a92f8-348">**Ontbrekende of ongeldige domeinwaarden:**</span><span class="sxs-lookup"><span data-stu-id="a92f8-348">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="a92f8-349">contoso</span><span class="sxs-lookup"><span data-stu-id="a92f8-349">contoso</span></span>
  - <span data-ttu-id="a92f8-350">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="a92f8-350">\*.contoso.\*</span></span>
  - <span data-ttu-id="a92f8-351">\*.COM</span><span class="sxs-lookup"><span data-stu-id="a92f8-351">\*.com</span></span>
  - <span data-ttu-id="a92f8-352">\*.PDF</span><span class="sxs-lookup"><span data-stu-id="a92f8-352">\*.pdf</span></span>

- <span data-ttu-id="a92f8-353">**Jokertekens in tekst of zonder spatiëringstekens:**</span><span class="sxs-lookup"><span data-stu-id="a92f8-353">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="a92f8-354">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-354">\*contoso.com</span></span>
  - <span data-ttu-id="a92f8-355">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="a92f8-355">contoso.com\*</span></span>
  - <span data-ttu-id="a92f8-356">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="a92f8-356">\*1.2.3.4</span></span>
  - <span data-ttu-id="a92f8-357">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="a92f8-357">1.2.3.4\*</span></span>
  - <span data-ttu-id="a92f8-358">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="a92f8-358">contoso.com/a\*</span></span>
  - <span data-ttu-id="a92f8-359">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="a92f8-359">contoso.com/ab\*</span></span>

- <span data-ttu-id="a92f8-360">**IP-adressen met poorten:**</span><span class="sxs-lookup"><span data-stu-id="a92f8-360">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="a92f8-361">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="a92f8-361">contoso.com:443</span></span>
  - <span data-ttu-id="a92f8-362">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="a92f8-362">abc.contoso.com:25</span></span>

- <span data-ttu-id="a92f8-363">**Niet-beschrijvende jokertekens:**</span><span class="sxs-lookup"><span data-stu-id="a92f8-363">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="a92f8-364">\*.\*</span><span class="sxs-lookup"><span data-stu-id="a92f8-364">\*.\*</span></span>

- <span data-ttu-id="a92f8-365">**Middelste jokertekens:**</span><span class="sxs-lookup"><span data-stu-id="a92f8-365">**Middle wildcards**:</span></span>

  - <span data-ttu-id="a92f8-366">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-366">conto\*so.com</span></span>
  - <span data-ttu-id="a92f8-367">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="a92f8-367">conto~so.com</span></span>

- <span data-ttu-id="a92f8-368">**Dubbele jokertekens**</span><span class="sxs-lookup"><span data-stu-id="a92f8-368">**Double wildcards**</span></span>

  - <span data-ttu-id="a92f8-369">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="a92f8-369">contoso.com/\*\*</span></span>
  - <span data-ttu-id="a92f8-370">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="a92f8-370">contoso.com/\*/\*</span></span>
