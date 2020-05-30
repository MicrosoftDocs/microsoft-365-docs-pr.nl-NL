---
title: Uw toegestane en geblokkeerde URL's en bestanden beheren in de lijst tenant-toestaan/blokkeren
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Beheerders kunnen leren hoe u URL- en bestandsvermeldingen configureert in de lijst Tenant Toestaan/blokkeren in het Security & Compliance Center.
ms.openlocfilehash: b3a25458bbde2b3a78cfecc60ccb75fe298013f7
ms.sourcegitcommit: 6746fae2f68400fd985711b1945b66766d2a59a4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/29/2020
ms.locfileid: "44419259"
---
# <a name="manage-urls-and-files-in-the-tenant-allowblock-list"></a><span data-ttu-id="22ca6-103">URL's en bestanden beheren in de lijst Tenant Allow/Block</span><span class="sxs-lookup"><span data-stu-id="22ca6-103">Manage URLs and files in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="22ca6-104">De functies die in dit onderwerp worden beschreven, staan in Voorbeeld, kunnen worden gewijzigd en zijn niet in alle organisaties beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="22ca6-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="22ca6-105">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken, u het niet eens zijn met het EOP-filteroordeel.</span><span class="sxs-lookup"><span data-stu-id="22ca6-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="22ca6-106">Een goed bericht kan bijvoorbeeld als slecht worden gemarkeerd (een fout-positief) of een slecht bericht kan worden toegestaan door (een vals negatief).</span><span class="sxs-lookup"><span data-stu-id="22ca6-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="22ca6-107">De tenantlijst toestaan/blokkeren in het Security & Compliance Center biedt u een manier om de Microsoft 365-filtervonnten handmatig te overschrijven.</span><span class="sxs-lookup"><span data-stu-id="22ca6-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="22ca6-108">De tenantlijst toestaan/blokkeren wordt gebruikt tijdens de e-mailstroom en op het moment dat de gebruiker klikt.</span><span class="sxs-lookup"><span data-stu-id="22ca6-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="22ca6-109">U URL's en bestanden opgeven om toe te staan of te blokkeren in de lijst tenant-toestaan/blokkeren.</span><span class="sxs-lookup"><span data-stu-id="22ca6-109">You can specify URLs and files to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="22ca6-110">In dit onderwerp wordt beschreven hoe u vermeldingen configureert in de lijst tenant-toestaan/blokkeren in het Security & Compliance Center of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).</span><span class="sxs-lookup"><span data-stu-id="22ca6-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="22ca6-111">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="22ca6-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="22ca6-112">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="22ca6-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="22ca6-113">Als u rechtstreeks naar de pagina **Tenant allow/block list wilt** gaan, gebruikt u <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="22ca6-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="22ca6-114">U geeft bestanden op met de SHA256-hashwaarde van het bestand.</span><span class="sxs-lookup"><span data-stu-id="22ca6-114">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="22ca6-115">Voer de volgende opdracht uit in een opdrachtprompt om de SHA256-hashwaarde van een bestand in Windows te zoeken:</span><span class="sxs-lookup"><span data-stu-id="22ca6-115">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="22ca6-116">Een voorbeeldwaarde is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="22ca6-116">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="22ca6-117">Perceptuele hash (pHash) waarden zijn niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="22ca6-117">Perceptual hash (pHash) values are not allowed.</span></span>

- <span data-ttu-id="22ca6-118">De beschikbare URL-waarden worden later in dit onderwerp beschreven in de syntaxis van de URL voor de sectie [Tenant toestaan/blokkeren.](#url-syntax-for-the-tenant-allowblock-list)</span><span class="sxs-lookup"><span data-stu-id="22ca6-118">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="22ca6-119">Met de tenantlijst toestaan/blokkeren kunnen maximaal 500 vermeldingen voor URL's en 500 vermeldingen voor bestandshashes.</span><span class="sxs-lookup"><span data-stu-id="22ca6-119">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="22ca6-120">Een vermelding moet binnen 15 minuten actief zijn.</span><span class="sxs-lookup"><span data-stu-id="22ca6-120">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="22ca6-121">Blokvermeldingen hebben voorrang op toestaan.</span><span class="sxs-lookup"><span data-stu-id="22ca6-121">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="22ca6-122">Standaard verlopen vermeldingen in de lijst tenant-toestaan/blokkeren na 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="22ca6-122">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="22ca6-123">U een datum opgeven of instellen dat deze nooit verloopt.</span><span class="sxs-lookup"><span data-stu-id="22ca6-123">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="22ca6-124">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22ca6-124">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="22ca6-125">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22ca6-125">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="22ca6-126">U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="22ca6-126">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="22ca6-127">Als u waarden wilt toevoegen en verwijderen uit de lijst tenant-toestaan/blokkeren, moet u lid zijn van de rolgroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="22ca6-127">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="22ca6-128">Voor alleen-lezen toegang tot de tenant-lijst voor toestaan/blokkeren, moet u lid zijn van de rolgroep **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="22ca6-128">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="22ca6-129">Zie [Machtigingen in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="22ca6-129">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="22ca6-130">Gebruik het Security & Compliance Center om URL-vermeldingen te maken in de lijst Tenant Allow/Block</span><span class="sxs-lookup"><span data-stu-id="22ca6-130">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="22ca6-131">Zie de [URL-syntaxis voor de sectie Tenant toestaan/blokkeren](#url-syntax-for-the-tenant-allowblock-list) lijst later in dit onderwerp voor meer informatie over de syntaxis voor URL-vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="22ca6-131">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="22ca6-132">Ga in het Security & Compliance Center naar Tenant Allow/Block Lists **voor bedreigingsbeheerbeleid** \> **Policy** \> **Tenant Allow/Block Lists**.</span><span class="sxs-lookup"><span data-stu-id="22ca6-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="22ca6-133">Controleer op de pagina **Tenant toestaan/blokkeren** of het tabblad **URL's** is geselecteerd en klik vervolgens op **Toevoegen**</span><span class="sxs-lookup"><span data-stu-id="22ca6-133">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="22ca6-134">Configureer in de flyout **Voor nieuwe URL's toevoegen** die wordt weergegeven de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="22ca6-134">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="22ca6-135">**URL's met jokertekens**toevoegen : Voer één URL per regel in, tot een maximum van 20.</span><span class="sxs-lookup"><span data-stu-id="22ca6-135">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="22ca6-136">**Blokkeren/Toestaan**: Selecteer of u de opgegeven URL's wilt **toestaan** of **blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="22ca6-136">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="22ca6-137">**Nooit verlopen**: Doe een van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="22ca6-137">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="22ca6-138">Controleer of de instelling is uitgeschakeld ( ![ ](../../media/scc-toggle-off.png) Uitschakelen) en gebruik het vak **Verlopen op** om de vervaldatum voor de vermeldingen op te geven.</span><span class="sxs-lookup"><span data-stu-id="22ca6-138">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="22ca6-139">of</span><span class="sxs-lookup"><span data-stu-id="22ca6-139">or</span></span>

     - <span data-ttu-id="22ca6-140">Verplaats de schakelaar naar rechts om de items te configureren om nooit te verlopen:</span><span class="sxs-lookup"><span data-stu-id="22ca6-140">Move the toggle to the right to configure the entries to never expire:</span></span> ![Inschakelen](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="22ca6-142">.</span><span class="sxs-lookup"><span data-stu-id="22ca6-142">.</span></span>

   - <span data-ttu-id="22ca6-143">**Optionele notitie**: Voer beschrijvende tekst in voor de vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="22ca6-143">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="22ca6-144">Klik op Toevoegen als u klaar bent met **toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="22ca6-144">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="22ca6-145">Gebruik het Security & Compliance Center om bestandsvermeldingen te maken in de lijst Tenant Allow/Block</span><span class="sxs-lookup"><span data-stu-id="22ca6-145">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="22ca6-146">Ga in het Security & Compliance Center naar Tenant Allow/Block Lists **voor bedreigingsbeheerbeleid** \> **Policy** \> **Tenant Allow/Block Lists**.</span><span class="sxs-lookup"><span data-stu-id="22ca6-146">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="22ca6-147">Selecteer op de pagina **Tenant toestaan/blokkeren** het tabblad **Bestanden** en klik vervolgens op **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="22ca6-147">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="22ca6-148">Configureer in de flyout **nieuwe bestanden toevoegen** die wordt weergegeven de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="22ca6-148">In the **Add new files** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="22ca6-149">**Bestandshashes toevoegen:** Voer één SHA256-hashwaarde per regel in, tot een maximum van 20.</span><span class="sxs-lookup"><span data-stu-id="22ca6-149">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="22ca6-150">**Blokkeren/Toestaan**: Selecteer of u de opgegeven bestanden wilt **toestaan** of **blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="22ca6-150">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified files.</span></span>

   - <span data-ttu-id="22ca6-151">**Nooit verlopen**: Doe een van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="22ca6-151">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="22ca6-152">Controleer of de instelling is uitgeschakeld ( ![ ](../../media/scc-toggle-off.png) Uitschakelen) en gebruik het vak **Verlopen op** om de vervaldatum voor de vermeldingen op te geven.</span><span class="sxs-lookup"><span data-stu-id="22ca6-152">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="22ca6-153">of</span><span class="sxs-lookup"><span data-stu-id="22ca6-153">or</span></span>

     - <span data-ttu-id="22ca6-154">Verplaats de schakelaar naar rechts om de items te configureren om nooit te verlopen:</span><span class="sxs-lookup"><span data-stu-id="22ca6-154">Move the toggle to the right to configure the entries to never expire:</span></span> ![Inschakelen](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="22ca6-156">.</span><span class="sxs-lookup"><span data-stu-id="22ca6-156">.</span></span>

   - <span data-ttu-id="22ca6-157">**Optionele notitie**: Voer beschrijvende tekst in voor de vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="22ca6-157">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="22ca6-158">Klik op Toevoegen als u klaar bent met **toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="22ca6-158">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="22ca6-159">Gebruik het Security & Compliance Center om URL- en bestandsvermeldingen weer te geven in de lijst Tenant Allow/Block</span><span class="sxs-lookup"><span data-stu-id="22ca6-159">Use the Security & Compliance Center to view URL and file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="22ca6-160">Ga in het Security & Compliance Center naar Tenant Allow/Block Lists **voor bedreigingsbeheerbeleid** \> **Policy** \> **Tenant Allow/Block Lists**.</span><span class="sxs-lookup"><span data-stu-id="22ca6-160">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="22ca6-161">Selecteer het tabblad **URL's** of het tabblad **Bestanden.**</span><span class="sxs-lookup"><span data-stu-id="22ca6-161">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="22ca6-162">Klik op de volgende kolomkoppen om in oplopende of aflopende volgorde te sorteren:</span><span class="sxs-lookup"><span data-stu-id="22ca6-162">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="22ca6-163">**Waarde**: De URL of de bestandshash.</span><span class="sxs-lookup"><span data-stu-id="22ca6-163">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="22ca6-164">**Actie**: **Blokkeren** of **toestaan**.</span><span class="sxs-lookup"><span data-stu-id="22ca6-164">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="22ca6-165">**Laatst bijgewerkte datum**</span><span class="sxs-lookup"><span data-stu-id="22ca6-165">**Last updated date**</span></span>
- <span data-ttu-id="22ca6-166">**Vervaldatum**</span><span class="sxs-lookup"><span data-stu-id="22ca6-166">**Expiration date**</span></span>
- <span data-ttu-id="22ca6-167">**Opmerking**</span><span class="sxs-lookup"><span data-stu-id="22ca6-167">**Note**</span></span>

<span data-ttu-id="22ca6-168">Klik **op Groeperen** om de items te groeperen op **actie** **(Blokkeren** of **Toestaan)** of **Geen**.</span><span class="sxs-lookup"><span data-stu-id="22ca6-168">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="22ca6-169">Klik **op Zoeken,** voer een URL of bestandswaarde geheel of gedeeltelijk in en druk op ENTER om een specifieke waarde te vinden.</span><span class="sxs-lookup"><span data-stu-id="22ca6-169">Click **Search**, enter all or part of a URL or file value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="22ca6-170">Wanneer u klaar bent, klikt u op **Clear search** ![ Zoekfunctie wissen ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) wissen.</span><span class="sxs-lookup"><span data-stu-id="22ca6-170">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="22ca6-171">Klik op **Filter**.</span><span class="sxs-lookup"><span data-stu-id="22ca6-171">Click **Filter**.</span></span> <span data-ttu-id="22ca6-172">Configureer een van de volgende instellingen in de flyout **Filter** die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="22ca6-172">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="22ca6-173">**Actie**: Selecteer **Toestaan,** **Blokkeren** of beide.</span><span class="sxs-lookup"><span data-stu-id="22ca6-173">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="22ca6-174">**Nooit verlopen**: Uitzetten ( ![ ](../../media/scc-toggle-off.png) Uitschakelen) of aan ( ![ Schakel ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) aan).</span><span class="sxs-lookup"><span data-stu-id="22ca6-174">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="22ca6-175">**Laatst bijgewerkt**: Selecteer een begindatum (**Van),** een einddatum (**Naar**) of beide.</span><span class="sxs-lookup"><span data-stu-id="22ca6-175">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="22ca6-176">**Vervaldatum**: Selecteer een begindatum (**Vanaf),** een einddatum (**Tot**) of beide.</span><span class="sxs-lookup"><span data-stu-id="22ca6-176">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="22ca6-177">Klik op **Toepassen**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="22ca6-177">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="22ca6-178">Als u bestaande filters wilt wissen, klikt u op **Filter**en klikt u in de flyout **Filter** die wordt weergegeven op **Filters wissen**.</span><span class="sxs-lookup"><span data-stu-id="22ca6-178">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="22ca6-179">Gebruik het Security & Compliance Center om URL- en bestandsvermeldingen in de lijst Tenant allow/block te wijzigen</span><span class="sxs-lookup"><span data-stu-id="22ca6-179">Use the Security & Compliance Center to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="22ca6-180">U de URL of bestandswaarde zelf niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="22ca6-180">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="22ca6-181">In plaats daarvan moet u de vermelding verwijderen en opnieuw maken.</span><span class="sxs-lookup"><span data-stu-id="22ca6-181">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="22ca6-182">Ga in het Security & Compliance Center naar Tenant Allow/Block Lists **voor bedreigingsbeheerbeleid** \> **Policy** \> **Tenant Allow/Block Lists**.</span><span class="sxs-lookup"><span data-stu-id="22ca6-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="22ca6-183">Selecteer het tabblad **URL's** of het tabblad **Bestanden.**</span><span class="sxs-lookup"><span data-stu-id="22ca6-183">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="22ca6-184">Selecteer het item dat u wilt wijzigen en **klik** op ![ pictogram Bewerken ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) bewerken .</span><span class="sxs-lookup"><span data-stu-id="22ca6-184">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="22ca6-185">Configureer in de flyout die wordt weergegeven de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="22ca6-185">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="22ca6-186">**Blokkeren/toestaan**: **Selecteren Toestaan** of **blokkeren**.</span><span class="sxs-lookup"><span data-stu-id="22ca6-186">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="22ca6-187">**Nooit verlopen**: Doe een van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="22ca6-187">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="22ca6-188">Controleer of de instelling is uitgeschakeld ( ![ ](../../media/scc-toggle-off.png) Uitschakelen) en gebruik het vak **Verlopen op** om de vervaldatum voor de vermelding op te geven.</span><span class="sxs-lookup"><span data-stu-id="22ca6-188">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="22ca6-189">of</span><span class="sxs-lookup"><span data-stu-id="22ca6-189">or</span></span>

     - <span data-ttu-id="22ca6-190">Verplaats de schakelaar naar rechts om de vermelding te configureren om nooit te verlopen:</span><span class="sxs-lookup"><span data-stu-id="22ca6-190">Move the toggle to the right to configure the entry to never expire:</span></span> ![Inschakelen](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="22ca6-192">.</span><span class="sxs-lookup"><span data-stu-id="22ca6-192">.</span></span>

   - <span data-ttu-id="22ca6-193">**Optionele notitie**: Voer beschrijvende tekst in voor de vermelding.</span><span class="sxs-lookup"><span data-stu-id="22ca6-193">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="22ca6-194">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="22ca6-194">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="22ca6-195">Gebruik het Security & Compliance Center om URL- en bestandsvermeldingen uit de lijst tenant-toestaan/blokkeren te verwijderen</span><span class="sxs-lookup"><span data-stu-id="22ca6-195">Use the Security & Compliance Center to remove URL and file entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="22ca6-196">Ga in het Security & Compliance Center naar Tenant Allow/Block Lists **voor bedreigingsbeheerbeleid** \> **Policy** \> **Tenant Allow/Block Lists**.</span><span class="sxs-lookup"><span data-stu-id="22ca6-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="22ca6-197">Selecteer het tabblad **URL's** of het tabblad **Bestanden.**</span><span class="sxs-lookup"><span data-stu-id="22ca6-197">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="22ca6-198">Selecteer het item dat u wilt verwijderen en **klik** op ![ pictogram Verwijderen verwijderen ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="22ca6-198">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="22ca6-199">Klik in het waarschuwingsdialoogvenster dat wordt weergegeven op **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="22ca6-199">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="22ca6-200">Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken om de tenant-lijst voor toestaan/blokkeren te configureren</span><span class="sxs-lookup"><span data-stu-id="22ca6-200">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="22ca6-201">PowerShell gebruiken om URL- en bestandsvermeldingen toe te voegen in de lijst Tenant Toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="22ca6-201">Use PowerShell to add URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="22ca6-202">Als u URL- en bestandsvermeldingen wilt toevoegen in de lijst Tenant toestaan/blokkeren, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="22ca6-202">To add URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="22ca6-203">In dit voorbeeld wordt een URL-blokvermelding toegevoegd voor contoso.com en alle subdomeinen (bijvoorbeeld contoso.com, www.contoso.com en xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="22ca6-203">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="22ca6-204">Omdat we de parameters voor vervaldatum of niet-uitademing niet hebben gebruikt, verloopt de vermelding na 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="22ca6-204">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Action Allow -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="22ca6-205">In dit voorbeeld wordt een bestand toegevoegd voor de opgegeven bestanden die nooit verlopen.</span><span class="sxs-lookup"><span data-stu-id="22ca6-205">This example adds a file allow entry for the specified files that never expires.</span></span>

<span data-ttu-id="22ca6-206">Zie [Nieuwe-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)voor gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="22ca6-206">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="22ca6-207">PowerShell gebruiken om URL- en bestandsvermeldingen weer te geven in de lijst Tenant Toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="22ca6-207">Use PowerShell to view URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="22ca6-208">Als u URL- en bestandsvermeldingen in de lijst Tenant toestaan/blokkeren wilt weergeven, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="22ca6-208">To view URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="22ca6-209">In dit voorbeeld worden alle geblokkeerde URL's geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="22ca6-209">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="22ca6-210">In dit voorbeeld worden gegevens geretourneerd voor de opgegeven bestandshashwaarde.</span><span class="sxs-lookup"><span data-stu-id="22ca6-210">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="22ca6-211">Zie Lijstitems voor gedetailleerde syntaxis en [parametergegevens](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="22ca6-211">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="22ca6-212">PowerShell gebruiken om URL- en bestandsvermeldingen in de lijst tenant-toestaan/blokkeren te wijzigen</span><span class="sxs-lookup"><span data-stu-id="22ca6-212">Use PowerShell to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="22ca6-213">U de URL of bestandswaarde zelf niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="22ca6-213">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="22ca6-214">In plaats daarvan moet u de vermelding verwijderen en opnieuw maken.</span><span class="sxs-lookup"><span data-stu-id="22ca6-214">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="22ca6-215">Als u URL- en bestandsvermeldingen in de lijst Tenant toestaan/blokkeren wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="22ca6-215">To modify URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="22ca6-216">In dit voorbeeld wordt de vervaldatum van de opgegeven vermelding gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="22ca6-216">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="22ca6-217">Zie [Set-TenantAllowBlockListIteMs voor](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="22ca6-217">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="22ca6-218">PowerShell gebruiken om URL- en bestandsvermeldingen uit de lijst tenant-toestaan/blokkeren te verwijderen</span><span class="sxs-lookup"><span data-stu-id="22ca6-218">Use PowerShell to remove URL and file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="22ca6-219">Als u URL- en bestandsvermeldingen wilt verwijderen uit de lijst tenant-toestaan/blokkeren, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="22ca6-219">To remove URL and file entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="22ca6-220">In dit voorbeeld wordt de opgegeven URL-vermelding verwijderd uit de lijst tenant-toestaan/blokkeren.</span><span class="sxs-lookup"><span data-stu-id="22ca6-220">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="22ca6-221">Zie [Remove-TenantAllowBlockListIteMs voor](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="22ca6-221">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="22ca6-222">URL-syntaxis voor de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="22ca6-222">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="22ca6-223">IP4v- en IPv6-adressen zijn toegestaan, maar TCP/UDP-poorten niet.</span><span class="sxs-lookup"><span data-stu-id="22ca6-223">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="22ca6-224">Bestandsnaamextensies zijn niet toegestaan (bijvoorbeeld test.pdf).</span><span class="sxs-lookup"><span data-stu-id="22ca6-224">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="22ca6-225">Unicode wordt niet ondersteund, maar Punycode wel.</span><span class="sxs-lookup"><span data-stu-id="22ca6-225">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="22ca6-226">Hostnamen zijn toegestaan als alle volgende instructies waar zijn:</span><span class="sxs-lookup"><span data-stu-id="22ca6-226">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="22ca6-227">De hostnaam bevat een periode.</span><span class="sxs-lookup"><span data-stu-id="22ca6-227">The hostname contains a period.</span></span>
  - <span data-ttu-id="22ca6-228">Er is ten minste één teken aan de linkerkant van de periode.</span><span class="sxs-lookup"><span data-stu-id="22ca6-228">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="22ca6-229">Er zijn ten minste twee tekens aan de rechterkant van de periode.</span><span class="sxs-lookup"><span data-stu-id="22ca6-229">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="22ca6-230">Is bijvoorbeeld `t.co` toegestaan; `.com` of `contoso.` zijn niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="22ca6-230">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="22ca6-231">Subpaden worden niet geïmpliceerd.</span><span class="sxs-lookup"><span data-stu-id="22ca6-231">Subpaths are not implied.</span></span>

  <span data-ttu-id="22ca6-232">Omvat bijvoorbeeld `contoso.com` niet `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="22ca6-232">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="22ca6-233">Jokertekens (\*) zijn toegestaan in de volgende scenario's:</span><span class="sxs-lookup"><span data-stu-id="22ca6-233">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="22ca6-234">Een linker wildcard moet worden gevolgd door een periode om een subdomein op te geven.</span><span class="sxs-lookup"><span data-stu-id="22ca6-234">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="22ca6-235">Is bijvoorbeeld `*.contoso.com` toegestaan; `*contoso.com` is niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="22ca6-235">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="22ca6-236">Een rechter wildcard moet een slash voorwaarts (/) volgen om een pad op te geven.</span><span class="sxs-lookup"><span data-stu-id="22ca6-236">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="22ca6-237">Is bijvoorbeeld `contoso.com/*` toegestaan; `contoso.com*` of `contoso.com/ab*` zijn niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="22ca6-237">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="22ca6-238">Alle subpaden worden niet geïmpliceerd door een juiste wildcard.</span><span class="sxs-lookup"><span data-stu-id="22ca6-238">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="22ca6-239">Omvat bijvoorbeeld `contoso.com/*` niet `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="22ca6-239">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="22ca6-240">`*.com*`is ongeldig (geen oplosbaar domein en de juiste wildcard volgt geen slash).</span><span class="sxs-lookup"><span data-stu-id="22ca6-240">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="22ca6-241">Wildcards zijn niet toegestaan in IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="22ca6-241">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="22ca6-242">Het teken tilde (~) is beschikbaar in de volgende scenario's:</span><span class="sxs-lookup"><span data-stu-id="22ca6-242">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="22ca6-243">Een linker tilde impliceert een domein en alle subdomeinen.</span><span class="sxs-lookup"><span data-stu-id="22ca6-243">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="22ca6-244">Bijvoorbeeld `~contoso.com` omvat `contoso.com` en `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="22ca6-244">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="22ca6-245">URL-vermeldingen die protocollen bevatten (bijvoorbeeld `http://` `https://` , of ) `ftp://` mislukken, omdat URL-vermeldingen van toepassing zijn op alle protocollen.</span><span class="sxs-lookup"><span data-stu-id="22ca6-245">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="22ca6-246">Een gebruikersnaam of wachtwoord wordt niet ondersteund of vereist.</span><span class="sxs-lookup"><span data-stu-id="22ca6-246">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="22ca6-247">Citaten (' of ') zijn ongeldige tekens.</span><span class="sxs-lookup"><span data-stu-id="22ca6-247">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="22ca6-248">Een URL moet waar mogelijk alle omleidingen bevatten.</span><span class="sxs-lookup"><span data-stu-id="22ca6-248">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="22ca6-249">URL-invoerscenario's</span><span class="sxs-lookup"><span data-stu-id="22ca6-249">URL entry scenarios</span></span>

<span data-ttu-id="22ca6-250">Geldige URL-vermeldingen en de resultaten ervan worden beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="22ca6-250">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="22ca6-251">Scenario: Geen wildcards</span><span class="sxs-lookup"><span data-stu-id="22ca6-251">Scenario: No wildcards</span></span>

<span data-ttu-id="22ca6-252">**Vermelding**:`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="22ca6-252">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="22ca6-253">**Match toestaan**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-253">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="22ca6-254">**Niet overeenkomen met:**</span><span class="sxs-lookup"><span data-stu-id="22ca6-254">**Allow not matched**:</span></span>

  - <span data-ttu-id="22ca6-255">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-255">abc-contoso.com</span></span>
  - <span data-ttu-id="22ca6-256">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="22ca6-256">contoso.com/a</span></span>
  - <span data-ttu-id="22ca6-257">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-257">payroll.contoso.com</span></span>
  - <span data-ttu-id="22ca6-258">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-258">test.com/contoso.com</span></span>
  - <span data-ttu-id="22ca6-259">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-259">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="22ca6-260">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-260">www.contoso.com</span></span>
  - <span data-ttu-id="22ca6-261">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-261">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="22ca6-262">**Blokwedstrijd**:</span><span class="sxs-lookup"><span data-stu-id="22ca6-262">**Block match**:</span></span>

  - <span data-ttu-id="22ca6-263">contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-263">contoso.com</span></span>
  - <span data-ttu-id="22ca6-264">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="22ca6-264">contoso.com/a</span></span>
  - <span data-ttu-id="22ca6-265">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-265">payroll.contoso.com</span></span>
  - <span data-ttu-id="22ca6-266">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-266">test.com/contoso.com</span></span>
  - <span data-ttu-id="22ca6-267">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-267">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="22ca6-268">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-268">www.contoso.com</span></span>
  - <span data-ttu-id="22ca6-269">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-269">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="22ca6-270">**Blok niet aan elkaar gewaagd**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-270">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="22ca6-271">Scenario: Linker wildcard (subdomein)</span><span class="sxs-lookup"><span data-stu-id="22ca6-271">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="22ca6-272">**Vermelding**:`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="22ca6-272">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="22ca6-273">Match en **Block match** **toestaan:**</span><span class="sxs-lookup"><span data-stu-id="22ca6-273">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="22ca6-274">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-274">www.contoso.com</span></span>
  - <span data-ttu-id="22ca6-275">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-275">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="22ca6-276">**Niet overeenkomen en** **Blokkeren niet overeenkomen:**</span><span class="sxs-lookup"><span data-stu-id="22ca6-276">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="22ca6-277">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-277">123contoso.com</span></span>
  - <span data-ttu-id="22ca6-278">contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-278">contoso.com</span></span>
  - <span data-ttu-id="22ca6-279">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-279">test.com/contoso.com</span></span>
  - <span data-ttu-id="22ca6-280">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="22ca6-280">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="22ca6-281">Scenario: Juiste wildcard boven aan het pad</span><span class="sxs-lookup"><span data-stu-id="22ca6-281">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="22ca6-282">**Vermelding**:`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="22ca6-282">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="22ca6-283">Match en **Block match** **toestaan:**</span><span class="sxs-lookup"><span data-stu-id="22ca6-283">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="22ca6-284">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="22ca6-284">contoso.com/a/b</span></span>
  - <span data-ttu-id="22ca6-285">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="22ca6-285">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="22ca6-286">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-286">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="22ca6-287">**Niet overeenkomen en** **Blokkeren niet overeenkomen:**</span><span class="sxs-lookup"><span data-stu-id="22ca6-287">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="22ca6-288">contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-288">contoso.com</span></span>
  - <span data-ttu-id="22ca6-289">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="22ca6-289">contoso.com/a</span></span>
  - <span data-ttu-id="22ca6-290">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-290">www.contoso.com</span></span>
  - <span data-ttu-id="22ca6-291">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-291">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="22ca6-292">Scenario: Linker tilde</span><span class="sxs-lookup"><span data-stu-id="22ca6-292">Scenario: Left tilde</span></span>

<span data-ttu-id="22ca6-293">**Vermelding**:`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="22ca6-293">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="22ca6-294">Match en **Block match** **toestaan:**</span><span class="sxs-lookup"><span data-stu-id="22ca6-294">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="22ca6-295">contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-295">contoso.com</span></span>
  - <span data-ttu-id="22ca6-296">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-296">www.contoso.com</span></span>
  - <span data-ttu-id="22ca6-297">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-297">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="22ca6-298">**Niet overeenkomen en** **Blokkeren niet overeenkomen:**</span><span class="sxs-lookup"><span data-stu-id="22ca6-298">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="22ca6-299">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-299">123contoso.com</span></span>
  - <span data-ttu-id="22ca6-300">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="22ca6-300">contoso.com/abc</span></span>
  - <span data-ttu-id="22ca6-301">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="22ca6-301">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="22ca6-302">Scenario: Rechts wildcard achtervoegsel</span><span class="sxs-lookup"><span data-stu-id="22ca6-302">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="22ca6-303">**Vermelding**:`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="22ca6-303">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="22ca6-304">Match en **Block match** **toestaan:**</span><span class="sxs-lookup"><span data-stu-id="22ca6-304">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="22ca6-305">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-305">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="22ca6-306">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="22ca6-306">contoso.com/a</span></span>
  - <span data-ttu-id="22ca6-307">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="22ca6-307">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="22ca6-308">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="22ca6-308">contoso.com/ab</span></span>
  - <span data-ttu-id="22ca6-309">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="22ca6-309">contoso.com/b</span></span>
  - <span data-ttu-id="22ca6-310">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="22ca6-310">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="22ca6-311">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="22ca6-311">contoso.com/ba</span></span>

- <span data-ttu-id="22ca6-312">**Niet overeenkomen en** **Blok niet overeenkomen :** contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-312">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="22ca6-313">Scenario: Subdomein voor linker wildcard en het achtervoegsel van de rechter wildcard</span><span class="sxs-lookup"><span data-stu-id="22ca6-313">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="22ca6-314">**Vermelding**:`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="22ca6-314">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="22ca6-315">Match en **Block match** **toestaan:**</span><span class="sxs-lookup"><span data-stu-id="22ca6-315">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="22ca6-316">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="22ca6-316">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="22ca6-317">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="22ca6-317">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="22ca6-318">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="22ca6-318">www.contoso.com/a</span></span>
  - <span data-ttu-id="22ca6-319">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="22ca6-319">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="22ca6-320">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="22ca6-320">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="22ca6-321">**Niet overeenkomen en** **Blok niet overeenkomen :** contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="22ca6-321">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="22ca6-322">Scenario: Links en rechts tilde</span><span class="sxs-lookup"><span data-stu-id="22ca6-322">Scenario: Left and right tilde</span></span>

<span data-ttu-id="22ca6-323">**Vermelding**:`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="22ca6-323">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="22ca6-324">Match en **Block match** **toestaan:**</span><span class="sxs-lookup"><span data-stu-id="22ca6-324">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="22ca6-325">contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-325">contoso.com</span></span>
  - <span data-ttu-id="22ca6-326">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="22ca6-326">contoso.com/a</span></span>
  - <span data-ttu-id="22ca6-327">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-327">www.contoso.com</span></span>
  - <span data-ttu-id="22ca6-328">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="22ca6-328">www.contoso.com/b</span></span>
  - <span data-ttu-id="22ca6-329">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-329">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="22ca6-330">**Niet overeenkomen en** **Blokkeren niet overeenkomen:**</span><span class="sxs-lookup"><span data-stu-id="22ca6-330">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="22ca6-331">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-331">123contoso.com</span></span>
  - <span data-ttu-id="22ca6-332">contoso.org</span><span class="sxs-lookup"><span data-stu-id="22ca6-332">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="22ca6-333">Scenario: IP-adres</span><span class="sxs-lookup"><span data-stu-id="22ca6-333">Scenario: IP address</span></span>

<span data-ttu-id="22ca6-334">**Vermelding**:`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="22ca6-334">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="22ca6-335">**Wedstrijd en** **blok wedstrijd toestaan**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="22ca6-335">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="22ca6-336">**Niet overeenkomen en** **Blokkeren niet overeenkomen:**</span><span class="sxs-lookup"><span data-stu-id="22ca6-336">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="22ca6-337">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="22ca6-337">1.2.3.4/a</span></span>
  - <span data-ttu-id="22ca6-338">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="22ca6-338">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="22ca6-339">IP-adres met juiste wildcard</span><span class="sxs-lookup"><span data-stu-id="22ca6-339">IP address with right wildcard</span></span>

<span data-ttu-id="22ca6-340">**Vermelding**:`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="22ca6-340">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="22ca6-341">Match en **Block match** **toestaan:**</span><span class="sxs-lookup"><span data-stu-id="22ca6-341">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="22ca6-342">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="22ca6-342">1.2.3.4/b</span></span>
  - <span data-ttu-id="22ca6-343">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="22ca6-343">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="22ca6-344">Voorbeelden van ongeldige vermeldingen</span><span class="sxs-lookup"><span data-stu-id="22ca6-344">Examples of invalid entries</span></span>

<span data-ttu-id="22ca6-345">De volgende vermeldingen zijn ongeldig:</span><span class="sxs-lookup"><span data-stu-id="22ca6-345">The following entries are invalid:</span></span>

- <span data-ttu-id="22ca6-346">**Ontbrekende of ongeldige domeinwaarden:**</span><span class="sxs-lookup"><span data-stu-id="22ca6-346">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="22ca6-347">Contoso</span><span class="sxs-lookup"><span data-stu-id="22ca6-347">contoso</span></span>
  - <span data-ttu-id="22ca6-348">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="22ca6-348">\*.contoso.\*</span></span>
  - <span data-ttu-id="22ca6-349">\*.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-349">\*.com</span></span>
  - <span data-ttu-id="22ca6-350">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="22ca6-350">\*.pdf</span></span>

- <span data-ttu-id="22ca6-351">**Wildcard op tekst of zonder spatiëringtekens:**</span><span class="sxs-lookup"><span data-stu-id="22ca6-351">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="22ca6-352">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-352">\*contoso.com</span></span>
  - <span data-ttu-id="22ca6-353">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="22ca6-353">contoso.com\*</span></span>
  - <span data-ttu-id="22ca6-354">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="22ca6-354">\*1.2.3.4</span></span>
  - <span data-ttu-id="22ca6-355">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="22ca6-355">1.2.3.4\*</span></span>
  - <span data-ttu-id="22ca6-356">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="22ca6-356">contoso.com/a\*</span></span>
  - <span data-ttu-id="22ca6-357">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="22ca6-357">contoso.com/ab\*</span></span>

- <span data-ttu-id="22ca6-358">**IP-adressen met poorten:**</span><span class="sxs-lookup"><span data-stu-id="22ca6-358">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="22ca6-359">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="22ca6-359">contoso.com:443</span></span>
  - <span data-ttu-id="22ca6-360">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="22ca6-360">abc.contoso.com:25</span></span>

- <span data-ttu-id="22ca6-361">**Niet-beschrijvende wildcards**:</span><span class="sxs-lookup"><span data-stu-id="22ca6-361">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="22ca6-362">\*.\*</span><span class="sxs-lookup"><span data-stu-id="22ca6-362">\*.\*</span></span>

- <span data-ttu-id="22ca6-363">**Middelste wildcards**:</span><span class="sxs-lookup"><span data-stu-id="22ca6-363">**Middle wildcards**:</span></span>

  - <span data-ttu-id="22ca6-364">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-364">conto\*so.com</span></span>
  - <span data-ttu-id="22ca6-365">conto ~ so.com</span><span class="sxs-lookup"><span data-stu-id="22ca6-365">conto~so.com</span></span>

- <span data-ttu-id="22ca6-366">**Dubbele wildcards**</span><span class="sxs-lookup"><span data-stu-id="22ca6-366">**Double wildcards**</span></span>

  - <span data-ttu-id="22ca6-367">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="22ca6-367">contoso.com/\*\*</span></span>
  - <span data-ttu-id="22ca6-368">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="22ca6-368">contoso.com/\*/\*</span></span>
