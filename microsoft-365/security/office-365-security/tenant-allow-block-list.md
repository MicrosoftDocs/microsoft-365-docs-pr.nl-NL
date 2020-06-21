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
ms.openlocfilehash: 742a44c7ed63c8a3037e2ada295c94f89afa9c93
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726809"
---
# <a name="manage-urls-and-files-in-the-tenant-allowblock-list"></a><span data-ttu-id="0f1c1-103">URL's en bestanden beheren in de lijst Tenant Allow/Block</span><span class="sxs-lookup"><span data-stu-id="0f1c1-103">Manage URLs and files in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="0f1c1-104">De functies die in dit onderwerp worden beschreven, staan in Voorbeeld, kunnen worden gewijzigd en zijn niet in alle organisaties beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="0f1c1-105">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken, u het niet eens zijn met het EOP-filteroordeel.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="0f1c1-106">Een goed bericht kan bijvoorbeeld als slecht worden gemarkeerd (een fout-positief) of een slecht bericht kan worden toegestaan door (een vals negatief).</span><span class="sxs-lookup"><span data-stu-id="0f1c1-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="0f1c1-107">De tenantlijst toestaan/blokkeren in het Security & Compliance Center biedt u een manier om de Microsoft 365-filtervonnten handmatig te overschrijven.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="0f1c1-108">De tenantlijst toestaan/blokkeren wordt gebruikt tijdens de e-mailstroom en op het moment dat de gebruiker klikt.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="0f1c1-109">U URL's en bestanden opgeven om toe te staan of te blokkeren in de lijst tenant-toestaan/blokkeren.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-109">You can specify URLs and files to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="0f1c1-110">In dit onderwerp wordt beschreven hoe u vermeldingen configureert in de lijst tenant-toestaan/blokkeren in het Security & Compliance Center of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).</span><span class="sxs-lookup"><span data-stu-id="0f1c1-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0f1c1-111">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="0f1c1-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0f1c1-112">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="0f1c1-113">Als u rechtstreeks naar de pagina **Tenant allow/block list wilt** gaan, gebruikt u <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="0f1c1-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="0f1c1-114">U geeft bestanden op met de SHA256-hashwaarde van het bestand.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-114">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="0f1c1-115">Voer de volgende opdracht uit in een opdrachtprompt om de SHA256-hashwaarde van een bestand in Windows te zoeken:</span><span class="sxs-lookup"><span data-stu-id="0f1c1-115">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="0f1c1-116">Een voorbeeldwaarde is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="0f1c1-116">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="0f1c1-117">Perceptuele hash (pHash) waarden zijn niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-117">Perceptual hash (pHash) values are not allowed.</span></span>

- <span data-ttu-id="0f1c1-118">De beschikbare URL-waarden worden later in dit onderwerp beschreven in de syntaxis van de URL voor de sectie [Tenant toestaan/blokkeren.](#url-syntax-for-the-tenant-allowblock-list)</span><span class="sxs-lookup"><span data-stu-id="0f1c1-118">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="0f1c1-119">Met de tenantlijst toestaan/blokkeren kunnen maximaal 500 vermeldingen voor URL's en 500 vermeldingen voor bestandshashes.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-119">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="0f1c1-120">Een vermelding moet binnen 15 minuten actief zijn.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-120">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="0f1c1-121">Blokvermeldingen hebben voorrang op toestaan.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-121">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="0f1c1-122">Standaard verlopen vermeldingen in de lijst tenant-toestaan/blokkeren na 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-122">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="0f1c1-123">U een datum opgeven of instellen dat deze nooit verloopt.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-123">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="0f1c1-124">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-124">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="0f1c1-125">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-125">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="0f1c1-126">U moet machtigingen krijgen voordat u de procedures in dit onderwerp uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="0f1c1-126">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="0f1c1-127">Als u waarden wilt toevoegen en verwijderen uit de lijst tenant-toestaan/blokkeren, moet u lid zijn van een van de volgende rolgroepen:</span><span class="sxs-lookup"><span data-stu-id="0f1c1-127">To add and remove values from the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="0f1c1-128">**Organisatiebeheer** of **beveiligingsbeheerder** in het [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="0f1c1-128">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="0f1c1-129">**Organisatiebeheer** of **hygiënebeheer** in [Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)</span><span class="sxs-lookup"><span data-stu-id="0f1c1-129">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="0f1c1-130">Voor alleen-lezen toegang tot de tenant-lijst voor toestaan/blokkeren, moet u lid zijn van een van de volgende rolgroepen:</span><span class="sxs-lookup"><span data-stu-id="0f1c1-130">For read-only access to the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="0f1c1-131">**Security Reader** in het [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="0f1c1-131">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="0f1c1-132">**Alleen-weergeven organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="0f1c1-132">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0f1c1-133">Gebruik het Security & Compliance Center om URL-vermeldingen te maken in de lijst Tenant Allow/Block</span><span class="sxs-lookup"><span data-stu-id="0f1c1-133">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="0f1c1-134">Zie de [URL-syntaxis voor de sectie Tenant toestaan/blokkeren](#url-syntax-for-the-tenant-allowblock-list) lijst later in dit onderwerp voor meer informatie over de syntaxis voor URL-vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-134">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="0f1c1-135">Ga in het Security & Compliance Center naar Tenant Allow/Block Lists **voor bedreigingsbeheerbeleid** \> **Policy** \> **Tenant Allow/Block Lists**.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-135">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="0f1c1-136">Controleer op de pagina **Tenant toestaan/blokkeren** of het tabblad **URL's** is geselecteerd en klik vervolgens op **Toevoegen**</span><span class="sxs-lookup"><span data-stu-id="0f1c1-136">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="0f1c1-137">Configureer in de flyout **Voor nieuwe URL's toevoegen** die wordt weergegeven de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="0f1c1-137">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="0f1c1-138">**URL's met jokertekens**toevoegen : Voer één URL per regel in, tot een maximum van 20.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-138">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="0f1c1-139">**Blokkeren/Toestaan**: Selecteer of u de opgegeven URL's wilt **toestaan** of **blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="0f1c1-139">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="0f1c1-140">**Nooit verlopen**: Doe een van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="0f1c1-140">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="0f1c1-141">Controleer of de instelling is uitgeschakeld ( ![ ](../../media/scc-toggle-off.png) Uitschakelen) en gebruik het vak **Verlopen op** om de vervaldatum voor de vermeldingen op te geven.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-141">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="0f1c1-142">of</span><span class="sxs-lookup"><span data-stu-id="0f1c1-142">or</span></span>

     - <span data-ttu-id="0f1c1-143">Verplaats de schakelaar naar rechts om de items te configureren om nooit te verlopen:</span><span class="sxs-lookup"><span data-stu-id="0f1c1-143">Move the toggle to the right to configure the entries to never expire:</span></span> ![Inschakelen](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="0f1c1-145">.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-145">.</span></span>

   - <span data-ttu-id="0f1c1-146">**Optionele notitie**: Voer beschrijvende tekst in voor de vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-146">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="0f1c1-147">Klik op Toevoegen als u klaar bent met **toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="0f1c1-147">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0f1c1-148">Gebruik het Security & Compliance Center om bestandsvermeldingen te maken in de lijst Tenant Allow/Block</span><span class="sxs-lookup"><span data-stu-id="0f1c1-148">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="0f1c1-149">Ga in het Security & Compliance Center naar Tenant Allow/Block Lists **voor bedreigingsbeheerbeleid** \> **Policy** \> **Tenant Allow/Block Lists**.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-149">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="0f1c1-150">Selecteer op de pagina **Tenant toestaan/blokkeren** het tabblad **Bestanden** en klik vervolgens op **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-150">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="0f1c1-151">Configureer in de flyout **nieuwe bestanden toevoegen** die wordt weergegeven de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="0f1c1-151">In the **Add new files** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="0f1c1-152">**Bestandshashes toevoegen:** Voer één SHA256-hashwaarde per regel in, tot een maximum van 20.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-152">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="0f1c1-153">**Blokkeren/Toestaan**: Selecteer of u de opgegeven bestanden wilt **toestaan** of **blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="0f1c1-153">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified files.</span></span>

   - <span data-ttu-id="0f1c1-154">**Nooit verlopen**: Doe een van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="0f1c1-154">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="0f1c1-155">Controleer of de instelling is uitgeschakeld ( ![ ](../../media/scc-toggle-off.png) Uitschakelen) en gebruik het vak **Verlopen op** om de vervaldatum voor de vermeldingen op te geven.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-155">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="0f1c1-156">of</span><span class="sxs-lookup"><span data-stu-id="0f1c1-156">or</span></span>

     - <span data-ttu-id="0f1c1-157">Verplaats de schakelaar naar rechts om de items te configureren om nooit te verlopen:</span><span class="sxs-lookup"><span data-stu-id="0f1c1-157">Move the toggle to the right to configure the entries to never expire:</span></span> ![Inschakelen](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="0f1c1-159">.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-159">.</span></span>

   - <span data-ttu-id="0f1c1-160">**Optionele notitie**: Voer beschrijvende tekst in voor de vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-160">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="0f1c1-161">Klik op Toevoegen als u klaar bent met **toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="0f1c1-161">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0f1c1-162">Gebruik het Security & Compliance Center om URL- en bestandsvermeldingen weer te geven in de lijst Tenant Allow/Block</span><span class="sxs-lookup"><span data-stu-id="0f1c1-162">Use the Security & Compliance Center to view URL and file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="0f1c1-163">Ga in het Security & Compliance Center naar Tenant Allow/Block Lists **voor bedreigingsbeheerbeleid** \> **Policy** \> **Tenant Allow/Block Lists**.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-163">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="0f1c1-164">Selecteer het tabblad **URL's** of het tabblad **Bestanden.**</span><span class="sxs-lookup"><span data-stu-id="0f1c1-164">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="0f1c1-165">Klik op de volgende kolomkoppen om in oplopende of aflopende volgorde te sorteren:</span><span class="sxs-lookup"><span data-stu-id="0f1c1-165">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="0f1c1-166">**Waarde**: De URL of de bestandshash.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-166">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="0f1c1-167">**Actie**: **Blokkeren** of **toestaan**.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-167">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="0f1c1-168">**Laatst bijgewerkte datum**</span><span class="sxs-lookup"><span data-stu-id="0f1c1-168">**Last updated date**</span></span>
- <span data-ttu-id="0f1c1-169">**Vervaldatum**</span><span class="sxs-lookup"><span data-stu-id="0f1c1-169">**Expiration date**</span></span>
- <span data-ttu-id="0f1c1-170">**Opmerking**</span><span class="sxs-lookup"><span data-stu-id="0f1c1-170">**Note**</span></span>

<span data-ttu-id="0f1c1-171">Klik **op Groeperen** om de items te groeperen op **actie** **(Blokkeren** of **Toestaan)** of **Geen**.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-171">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="0f1c1-172">Klik **op Zoeken,** voer een URL of bestandswaarde geheel of gedeeltelijk in en druk op ENTER om een specifieke waarde te vinden.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-172">Click **Search**, enter all or part of a URL or file value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="0f1c1-173">Wanneer u klaar bent, klikt u op **Clear search** ![ Zoekfunctie wissen ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) wissen.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-173">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="0f1c1-174">Klik op **Filter**.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-174">Click **Filter**.</span></span> <span data-ttu-id="0f1c1-175">Configureer een van de volgende instellingen in de flyout **Filter** die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="0f1c1-175">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="0f1c1-176">**Actie**: Selecteer **Toestaan,** **Blokkeren** of beide.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-176">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="0f1c1-177">**Nooit verlopen**: Uitzetten ( ![ ](../../media/scc-toggle-off.png) Uitschakelen) of aan ( ![ Schakel ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) aan).</span><span class="sxs-lookup"><span data-stu-id="0f1c1-177">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="0f1c1-178">**Laatst bijgewerkt**: Selecteer een begindatum (**Van),** een einddatum (**Naar**) of beide.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-178">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="0f1c1-179">**Vervaldatum**: Selecteer een begindatum (**Vanaf),** een einddatum (**Tot**) of beide.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-179">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="0f1c1-180">Klik op **Toepassen**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-180">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="0f1c1-181">Als u bestaande filters wilt wissen, klikt u op **Filter**en klikt u in de flyout **Filter** die wordt weergegeven op **Filters wissen**.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-181">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0f1c1-182">Gebruik het Security & Compliance Center om URL- en bestandsvermeldingen in de lijst Tenant allow/block te wijzigen</span><span class="sxs-lookup"><span data-stu-id="0f1c1-182">Use the Security & Compliance Center to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="0f1c1-183">U de URL of bestandswaarde zelf niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-183">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="0f1c1-184">In plaats daarvan moet u de vermelding verwijderen en opnieuw maken.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-184">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="0f1c1-185">Ga in het Security & Compliance Center naar Tenant Allow/Block Lists **voor bedreigingsbeheerbeleid** \> **Policy** \> **Tenant Allow/Block Lists**.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="0f1c1-186">Selecteer het tabblad **URL's** of het tabblad **Bestanden.**</span><span class="sxs-lookup"><span data-stu-id="0f1c1-186">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="0f1c1-187">Selecteer het item dat u wilt wijzigen en **klik** op ![ pictogram Bewerken ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) bewerken .</span><span class="sxs-lookup"><span data-stu-id="0f1c1-187">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="0f1c1-188">Configureer in de flyout die wordt weergegeven de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="0f1c1-188">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="0f1c1-189">**Blokkeren/toestaan**: **Selecteren Toestaan** of **blokkeren**.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-189">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="0f1c1-190">**Nooit verlopen**: Doe een van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="0f1c1-190">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="0f1c1-191">Controleer of de instelling is uitgeschakeld ( ![ ](../../media/scc-toggle-off.png) Uitschakelen) en gebruik het vak **Verlopen op** om de vervaldatum voor de vermelding op te geven.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-191">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="0f1c1-192">of</span><span class="sxs-lookup"><span data-stu-id="0f1c1-192">or</span></span>

     - <span data-ttu-id="0f1c1-193">Verplaats de schakelaar naar rechts om de vermelding te configureren om nooit te verlopen:</span><span class="sxs-lookup"><span data-stu-id="0f1c1-193">Move the toggle to the right to configure the entry to never expire:</span></span> ![Inschakelen](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="0f1c1-195">.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-195">.</span></span>

   - <span data-ttu-id="0f1c1-196">**Optionele notitie**: Voer beschrijvende tekst in voor de vermelding.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-196">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="0f1c1-197">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-197">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="0f1c1-198">Gebruik het Security & Compliance Center om URL- en bestandsvermeldingen uit de lijst tenant-toestaan/blokkeren te verwijderen</span><span class="sxs-lookup"><span data-stu-id="0f1c1-198">Use the Security & Compliance Center to remove URL and file entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="0f1c1-199">Ga in het Security & Compliance Center naar Tenant Allow/Block Lists **voor bedreigingsbeheerbeleid** \> **Policy** \> **Tenant Allow/Block Lists**.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-199">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="0f1c1-200">Selecteer het tabblad **URL's** of het tabblad **Bestanden.**</span><span class="sxs-lookup"><span data-stu-id="0f1c1-200">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="0f1c1-201">Selecteer het item dat u wilt verwijderen en **klik** op ![ pictogram Verwijderen verwijderen ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="0f1c1-201">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="0f1c1-202">Klik in het waarschuwingsdialoogvenster dat wordt weergegeven op **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-202">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="0f1c1-203">Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken om de tenant-lijst voor toestaan/blokkeren te configureren</span><span class="sxs-lookup"><span data-stu-id="0f1c1-203">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0f1c1-204">PowerShell gebruiken om URL- en bestandsvermeldingen toe te voegen in de lijst Tenant Toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="0f1c1-204">Use PowerShell to add URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="0f1c1-205">Als u URL- en bestandsvermeldingen wilt toevoegen in de lijst Tenant toestaan/blokkeren, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="0f1c1-205">To add URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="0f1c1-206">In dit voorbeeld wordt een URL-blokvermelding toegevoegd voor contoso.com en alle subdomeinen (bijvoorbeeld contoso.com, www.contoso.com en xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="0f1c1-206">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="0f1c1-207">Omdat we de parameters voor vervaldatum of niet-uitademing niet hebben gebruikt, verloopt de vermelding na 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-207">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Action Allow -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="0f1c1-208">In dit voorbeeld wordt een bestand toegevoegd voor de opgegeven bestanden die nooit verlopen.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-208">This example adds a file allow entry for the specified files that never expires.</span></span>

<span data-ttu-id="0f1c1-209">Zie [Nieuwe-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)voor gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="0f1c1-209">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0f1c1-210">PowerShell gebruiken om URL- en bestandsvermeldingen weer te geven in de lijst Tenant Toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="0f1c1-210">Use PowerShell to view URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="0f1c1-211">Als u URL- en bestandsvermeldingen in de lijst Tenant toestaan/blokkeren wilt weergeven, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="0f1c1-211">To view URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="0f1c1-212">In dit voorbeeld worden alle geblokkeerde URL's geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-212">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="0f1c1-213">In dit voorbeeld worden gegevens geretourneerd voor de opgegeven bestandshashwaarde.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-213">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="0f1c1-214">Zie Lijstitems voor gedetailleerde syntaxis en [parametergegevens](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="0f1c1-214">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0f1c1-215">PowerShell gebruiken om URL- en bestandsvermeldingen in de lijst tenant-toestaan/blokkeren te wijzigen</span><span class="sxs-lookup"><span data-stu-id="0f1c1-215">Use PowerShell to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="0f1c1-216">U de URL of bestandswaarde zelf niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-216">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="0f1c1-217">In plaats daarvan moet u de vermelding verwijderen en opnieuw maken.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-217">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="0f1c1-218">Als u URL- en bestandsvermeldingen in de lijst Tenant toestaan/blokkeren wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="0f1c1-218">To modify URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="0f1c1-219">In dit voorbeeld wordt de vervaldatum van de opgegeven vermelding gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-219">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="0f1c1-220">Zie [Set-TenantAllowBlockListIteMs voor](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="0f1c1-220">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="0f1c1-221">PowerShell gebruiken om URL- en bestandsvermeldingen uit de lijst tenant-toestaan/blokkeren te verwijderen</span><span class="sxs-lookup"><span data-stu-id="0f1c1-221">Use PowerShell to remove URL and file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="0f1c1-222">Als u URL- en bestandsvermeldingen wilt verwijderen uit de lijst tenant-toestaan/blokkeren, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="0f1c1-222">To remove URL and file entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="0f1c1-223">In dit voorbeeld wordt de opgegeven URL-vermelding verwijderd uit de lijst tenant-toestaan/blokkeren.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-223">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="0f1c1-224">Zie [Remove-TenantAllowBlockListIteMs voor](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="0f1c1-224">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="0f1c1-225">URL-syntaxis voor de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="0f1c1-225">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="0f1c1-226">IP4v- en IPv6-adressen zijn toegestaan, maar TCP/UDP-poorten niet.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-226">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="0f1c1-227">Bestandsnaamextensies zijn niet toegestaan (bijvoorbeeld test.pdf).</span><span class="sxs-lookup"><span data-stu-id="0f1c1-227">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="0f1c1-228">Unicode wordt niet ondersteund, maar Punycode wel.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-228">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="0f1c1-229">Hostnamen zijn toegestaan als alle volgende instructies waar zijn:</span><span class="sxs-lookup"><span data-stu-id="0f1c1-229">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="0f1c1-230">De hostnaam bevat een periode.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-230">The hostname contains a period.</span></span>
  - <span data-ttu-id="0f1c1-231">Er is ten minste één teken aan de linkerkant van de periode.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-231">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="0f1c1-232">Er zijn ten minste twee tekens aan de rechterkant van de periode.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-232">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="0f1c1-233">Is bijvoorbeeld `t.co` toegestaan; `.com` of `contoso.` zijn niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-233">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="0f1c1-234">Subpaden worden niet geïmpliceerd.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-234">Subpaths are not implied.</span></span>

  <span data-ttu-id="0f1c1-235">Omvat bijvoorbeeld `contoso.com` niet `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="0f1c1-235">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="0f1c1-236">Jokertekens (\*) zijn toegestaan in de volgende scenario's:</span><span class="sxs-lookup"><span data-stu-id="0f1c1-236">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="0f1c1-237">Een linker wildcard moet worden gevolgd door een periode om een subdomein op te geven.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-237">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="0f1c1-238">Is bijvoorbeeld `*.contoso.com` toegestaan; `*contoso.com` is niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-238">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="0f1c1-239">Een rechter wildcard moet een slash voorwaarts (/) volgen om een pad op te geven.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-239">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="0f1c1-240">Is bijvoorbeeld `contoso.com/*` toegestaan; `contoso.com*` of `contoso.com/ab*` zijn niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-240">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="0f1c1-241">Alle subpaden worden niet geïmpliceerd door een juiste wildcard.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-241">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="0f1c1-242">Omvat bijvoorbeeld `contoso.com/*` niet `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="0f1c1-242">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="0f1c1-243">`*.com*`is ongeldig (geen oplosbaar domein en de juiste wildcard volgt geen slash).</span><span class="sxs-lookup"><span data-stu-id="0f1c1-243">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="0f1c1-244">Wildcards zijn niet toegestaan in IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-244">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="0f1c1-245">Het teken tilde (~) is beschikbaar in de volgende scenario's:</span><span class="sxs-lookup"><span data-stu-id="0f1c1-245">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="0f1c1-246">Een linker tilde impliceert een domein en alle subdomeinen.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-246">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="0f1c1-247">Bijvoorbeeld `~contoso.com` omvat `contoso.com` en `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="0f1c1-247">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="0f1c1-248">URL-vermeldingen die protocollen bevatten (bijvoorbeeld `http://` `https://` , of ) `ftp://` mislukken, omdat URL-vermeldingen van toepassing zijn op alle protocollen.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-248">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="0f1c1-249">Een gebruikersnaam of wachtwoord wordt niet ondersteund of vereist.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-249">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="0f1c1-250">Citaten (' of ') zijn ongeldige tekens.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-250">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="0f1c1-251">Een URL moet waar mogelijk alle omleidingen bevatten.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-251">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="0f1c1-252">URL-invoerscenario's</span><span class="sxs-lookup"><span data-stu-id="0f1c1-252">URL entry scenarios</span></span>

<span data-ttu-id="0f1c1-253">Geldige URL-vermeldingen en de resultaten ervan worden beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="0f1c1-253">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="0f1c1-254">Scenario: Geen wildcards</span><span class="sxs-lookup"><span data-stu-id="0f1c1-254">Scenario: No wildcards</span></span>

<span data-ttu-id="0f1c1-255">**Vermelding**:`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="0f1c1-255">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="0f1c1-256">**Match toestaan**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-256">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="0f1c1-257">**Niet overeenkomen met:**</span><span class="sxs-lookup"><span data-stu-id="0f1c1-257">**Allow not matched**:</span></span>

  - <span data-ttu-id="0f1c1-258">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-258">abc-contoso.com</span></span>
  - <span data-ttu-id="0f1c1-259">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="0f1c1-259">contoso.com/a</span></span>
  - <span data-ttu-id="0f1c1-260">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-260">payroll.contoso.com</span></span>
  - <span data-ttu-id="0f1c1-261">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-261">test.com/contoso.com</span></span>
  - <span data-ttu-id="0f1c1-262">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-262">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="0f1c1-263">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-263">www.contoso.com</span></span>
  - <span data-ttu-id="0f1c1-264">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-264">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="0f1c1-265">**Blokwedstrijd**:</span><span class="sxs-lookup"><span data-stu-id="0f1c1-265">**Block match**:</span></span>

  - <span data-ttu-id="0f1c1-266">contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-266">contoso.com</span></span>
  - <span data-ttu-id="0f1c1-267">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="0f1c1-267">contoso.com/a</span></span>
  - <span data-ttu-id="0f1c1-268">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-268">payroll.contoso.com</span></span>
  - <span data-ttu-id="0f1c1-269">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-269">test.com/contoso.com</span></span>
  - <span data-ttu-id="0f1c1-270">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-270">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="0f1c1-271">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-271">www.contoso.com</span></span>
  - <span data-ttu-id="0f1c1-272">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-272">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="0f1c1-273">**Blok niet aan elkaar gewaagd**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-273">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="0f1c1-274">Scenario: Linker wildcard (subdomein)</span><span class="sxs-lookup"><span data-stu-id="0f1c1-274">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="0f1c1-275">**Vermelding**:`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="0f1c1-275">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="0f1c1-276">Match en **Block match** **toestaan:**</span><span class="sxs-lookup"><span data-stu-id="0f1c1-276">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0f1c1-277">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-277">www.contoso.com</span></span>
  - <span data-ttu-id="0f1c1-278">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-278">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="0f1c1-279">**Niet overeenkomen en** **Blokkeren niet overeenkomen:**</span><span class="sxs-lookup"><span data-stu-id="0f1c1-279">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="0f1c1-280">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-280">123contoso.com</span></span>
  - <span data-ttu-id="0f1c1-281">contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-281">contoso.com</span></span>
  - <span data-ttu-id="0f1c1-282">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-282">test.com/contoso.com</span></span>
  - <span data-ttu-id="0f1c1-283">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="0f1c1-283">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="0f1c1-284">Scenario: Juiste wildcard boven aan het pad</span><span class="sxs-lookup"><span data-stu-id="0f1c1-284">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="0f1c1-285">**Vermelding**:`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="0f1c1-285">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="0f1c1-286">Match en **Block match** **toestaan:**</span><span class="sxs-lookup"><span data-stu-id="0f1c1-286">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0f1c1-287">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="0f1c1-287">contoso.com/a/b</span></span>
  - <span data-ttu-id="0f1c1-288">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="0f1c1-288">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="0f1c1-289">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-289">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="0f1c1-290">**Niet overeenkomen en** **Blokkeren niet overeenkomen:**</span><span class="sxs-lookup"><span data-stu-id="0f1c1-290">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="0f1c1-291">contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-291">contoso.com</span></span>
  - <span data-ttu-id="0f1c1-292">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="0f1c1-292">contoso.com/a</span></span>
  - <span data-ttu-id="0f1c1-293">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-293">www.contoso.com</span></span>
  - <span data-ttu-id="0f1c1-294">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-294">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="0f1c1-295">Scenario: Linker tilde</span><span class="sxs-lookup"><span data-stu-id="0f1c1-295">Scenario: Left tilde</span></span>

<span data-ttu-id="0f1c1-296">**Vermelding**:`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="0f1c1-296">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="0f1c1-297">Match en **Block match** **toestaan:**</span><span class="sxs-lookup"><span data-stu-id="0f1c1-297">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0f1c1-298">contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-298">contoso.com</span></span>
  - <span data-ttu-id="0f1c1-299">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-299">www.contoso.com</span></span>
  - <span data-ttu-id="0f1c1-300">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-300">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="0f1c1-301">**Niet overeenkomen en** **Blokkeren niet overeenkomen:**</span><span class="sxs-lookup"><span data-stu-id="0f1c1-301">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="0f1c1-302">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-302">123contoso.com</span></span>
  - <span data-ttu-id="0f1c1-303">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="0f1c1-303">contoso.com/abc</span></span>
  - <span data-ttu-id="0f1c1-304">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="0f1c1-304">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="0f1c1-305">Scenario: Rechts wildcard achtervoegsel</span><span class="sxs-lookup"><span data-stu-id="0f1c1-305">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="0f1c1-306">**Vermelding**:`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="0f1c1-306">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="0f1c1-307">Match en **Block match** **toestaan:**</span><span class="sxs-lookup"><span data-stu-id="0f1c1-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0f1c1-308">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-308">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="0f1c1-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="0f1c1-309">contoso.com/a</span></span>
  - <span data-ttu-id="0f1c1-310">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="0f1c1-310">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="0f1c1-311">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="0f1c1-311">contoso.com/ab</span></span>
  - <span data-ttu-id="0f1c1-312">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="0f1c1-312">contoso.com/b</span></span>
  - <span data-ttu-id="0f1c1-313">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="0f1c1-313">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="0f1c1-314">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="0f1c1-314">contoso.com/ba</span></span>

- <span data-ttu-id="0f1c1-315">**Niet overeenkomen en** **Blok niet overeenkomen :** contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-315">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="0f1c1-316">Scenario: Subdomein voor linker wildcard en het achtervoegsel van de rechter wildcard</span><span class="sxs-lookup"><span data-stu-id="0f1c1-316">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="0f1c1-317">**Vermelding**:`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="0f1c1-317">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="0f1c1-318">Match en **Block match** **toestaan:**</span><span class="sxs-lookup"><span data-stu-id="0f1c1-318">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0f1c1-319">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="0f1c1-319">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="0f1c1-320">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="0f1c1-320">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="0f1c1-321">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="0f1c1-321">www.contoso.com/a</span></span>
  - <span data-ttu-id="0f1c1-322">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="0f1c1-322">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="0f1c1-323">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="0f1c1-323">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="0f1c1-324">**Niet overeenkomen en** **Blok niet overeenkomen :** contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="0f1c1-324">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="0f1c1-325">Scenario: Links en rechts tilde</span><span class="sxs-lookup"><span data-stu-id="0f1c1-325">Scenario: Left and right tilde</span></span>

<span data-ttu-id="0f1c1-326">**Vermelding**:`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="0f1c1-326">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="0f1c1-327">Match en **Block match** **toestaan:**</span><span class="sxs-lookup"><span data-stu-id="0f1c1-327">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0f1c1-328">contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-328">contoso.com</span></span>
  - <span data-ttu-id="0f1c1-329">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="0f1c1-329">contoso.com/a</span></span>
  - <span data-ttu-id="0f1c1-330">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-330">www.contoso.com</span></span>
  - <span data-ttu-id="0f1c1-331">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="0f1c1-331">www.contoso.com/b</span></span>
  - <span data-ttu-id="0f1c1-332">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-332">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="0f1c1-333">**Niet overeenkomen en** **Blokkeren niet overeenkomen:**</span><span class="sxs-lookup"><span data-stu-id="0f1c1-333">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="0f1c1-334">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-334">123contoso.com</span></span>
  - <span data-ttu-id="0f1c1-335">contoso.org</span><span class="sxs-lookup"><span data-stu-id="0f1c1-335">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="0f1c1-336">Scenario: IP-adres</span><span class="sxs-lookup"><span data-stu-id="0f1c1-336">Scenario: IP address</span></span>

<span data-ttu-id="0f1c1-337">**Vermelding**:`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="0f1c1-337">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="0f1c1-338">**Wedstrijd en** **blok wedstrijd toestaan**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="0f1c1-338">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="0f1c1-339">**Niet overeenkomen en** **Blokkeren niet overeenkomen:**</span><span class="sxs-lookup"><span data-stu-id="0f1c1-339">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="0f1c1-340">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="0f1c1-340">1.2.3.4/a</span></span>
  - <span data-ttu-id="0f1c1-341">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="0f1c1-341">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="0f1c1-342">IP-adres met juiste wildcard</span><span class="sxs-lookup"><span data-stu-id="0f1c1-342">IP address with right wildcard</span></span>

<span data-ttu-id="0f1c1-343">**Vermelding**:`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="0f1c1-343">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="0f1c1-344">Match en **Block match** **toestaan:**</span><span class="sxs-lookup"><span data-stu-id="0f1c1-344">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0f1c1-345">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="0f1c1-345">1.2.3.4/b</span></span>
  - <span data-ttu-id="0f1c1-346">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="0f1c1-346">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="0f1c1-347">Voorbeelden van ongeldige vermeldingen</span><span class="sxs-lookup"><span data-stu-id="0f1c1-347">Examples of invalid entries</span></span>

<span data-ttu-id="0f1c1-348">De volgende vermeldingen zijn ongeldig:</span><span class="sxs-lookup"><span data-stu-id="0f1c1-348">The following entries are invalid:</span></span>

- <span data-ttu-id="0f1c1-349">**Ontbrekende of ongeldige domeinwaarden:**</span><span class="sxs-lookup"><span data-stu-id="0f1c1-349">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="0f1c1-350">Contoso</span><span class="sxs-lookup"><span data-stu-id="0f1c1-350">contoso</span></span>
  - <span data-ttu-id="0f1c1-351">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="0f1c1-351">\*.contoso.\*</span></span>
  - <span data-ttu-id="0f1c1-352">\*.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-352">\*.com</span></span>
  - <span data-ttu-id="0f1c1-353">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="0f1c1-353">\*.pdf</span></span>

- <span data-ttu-id="0f1c1-354">**Wildcard op tekst of zonder spatiëringtekens:**</span><span class="sxs-lookup"><span data-stu-id="0f1c1-354">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="0f1c1-355">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-355">\*contoso.com</span></span>
  - <span data-ttu-id="0f1c1-356">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="0f1c1-356">contoso.com\*</span></span>
  - <span data-ttu-id="0f1c1-357">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="0f1c1-357">\*1.2.3.4</span></span>
  - <span data-ttu-id="0f1c1-358">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="0f1c1-358">1.2.3.4\*</span></span>
  - <span data-ttu-id="0f1c1-359">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="0f1c1-359">contoso.com/a\*</span></span>
  - <span data-ttu-id="0f1c1-360">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="0f1c1-360">contoso.com/ab\*</span></span>

- <span data-ttu-id="0f1c1-361">**IP-adressen met poorten:**</span><span class="sxs-lookup"><span data-stu-id="0f1c1-361">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="0f1c1-362">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="0f1c1-362">contoso.com:443</span></span>
  - <span data-ttu-id="0f1c1-363">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="0f1c1-363">abc.contoso.com:25</span></span>

- <span data-ttu-id="0f1c1-364">**Niet-beschrijvende wildcards**:</span><span class="sxs-lookup"><span data-stu-id="0f1c1-364">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="0f1c1-365">\*.\*</span><span class="sxs-lookup"><span data-stu-id="0f1c1-365">\*.\*</span></span>

- <span data-ttu-id="0f1c1-366">**Middelste wildcards**:</span><span class="sxs-lookup"><span data-stu-id="0f1c1-366">**Middle wildcards**:</span></span>

  - <span data-ttu-id="0f1c1-367">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-367">conto\*so.com</span></span>
  - <span data-ttu-id="0f1c1-368">conto ~ so.com</span><span class="sxs-lookup"><span data-stu-id="0f1c1-368">conto~so.com</span></span>

- <span data-ttu-id="0f1c1-369">**Dubbele wildcards**</span><span class="sxs-lookup"><span data-stu-id="0f1c1-369">**Double wildcards**</span></span>

  - <span data-ttu-id="0f1c1-370">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="0f1c1-370">contoso.com/\*\*</span></span>
  - <span data-ttu-id="0f1c1-371">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="0f1c1-371">contoso.com/\*/\*</span></span>
