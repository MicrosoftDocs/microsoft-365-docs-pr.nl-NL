---
title: Uw toegestane en geblokkeerde URL's beheren in de lijst tenant-toestaan/blokkeren
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
description: Beheerders kunnen leren hoe u URL-vermeldingen configureert in de lijst tenant-toestaan/blokkeren in het Security & Compliance Center.
ms.openlocfilehash: 5ff34cca922f18a015bd9da847facc8177cf8790
ms.sourcegitcommit: 89178b8f20d59ca88cfca303a13062b91fbeae9d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552548"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a><span data-ttu-id="e59be-103">URL's beheren in de lijst Tenant allow/block</span><span class="sxs-lookup"><span data-stu-id="e59be-103">Manage URLs in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="e59be-104">De functies die in dit onderwerp worden beschreven, staan in Voorbeeld, kunnen worden gewijzigd en zijn niet in alle organisaties beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="e59be-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="e59be-105">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken, u het niet eens zijn met het EOP-filteroordeel.</span><span class="sxs-lookup"><span data-stu-id="e59be-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="e59be-106">Een goed bericht kan bijvoorbeeld als slecht worden gemarkeerd (een fout-positief) of een slecht bericht kan worden toegestaan door (een vals negatief).</span><span class="sxs-lookup"><span data-stu-id="e59be-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="e59be-107">De tenantlijst toestaan/blokkeren in het Security & Compliance Center biedt u een manier om de Microsoft 365-filtervonnten handmatig te overschrijven.</span><span class="sxs-lookup"><span data-stu-id="e59be-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="e59be-108">De tenantlijst toestaan/blokkeren wordt gebruikt tijdens de e-mailstroom en op het moment dat de gebruiker klikt.</span><span class="sxs-lookup"><span data-stu-id="e59be-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="e59be-109">U URL's opgeven om toe te staan of te blokkeren in de lijst tenant-toestaan/blokkeren.</span><span class="sxs-lookup"><span data-stu-id="e59be-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="e59be-110">In dit onderwerp wordt beschreven hoe u vermeldingen configureert in de lijst tenant-toestaan/blokkeren in het Security & Compliance Center of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).</span><span class="sxs-lookup"><span data-stu-id="e59be-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e59be-111">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="e59be-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e59be-112">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="e59be-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="e59be-113">Als u rechtstreeks naar de pagina **Tenant allow/block list wilt** gaan, gebruikt u <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="e59be-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="e59be-114">De beschikbare URL-waarden worden later in dit onderwerp beschreven in de syntaxis van de URL voor de sectie [Tenant toestaan/blokkeren.](#url-syntax-for-the-tenant-allowblock-list)</span><span class="sxs-lookup"><span data-stu-id="e59be-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="e59be-115">De tenant-lijst voor toestaan/blokkeren maakt maximaal 500 vermeldingen voor URL's mogelijk.</span><span class="sxs-lookup"><span data-stu-id="e59be-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLss.</span></span>

- <span data-ttu-id="e59be-116">Een vermelding moet binnen 15 minuten actief zijn.</span><span class="sxs-lookup"><span data-stu-id="e59be-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="e59be-117">Blokvermeldingen hebben voorrang op toestaan.</span><span class="sxs-lookup"><span data-stu-id="e59be-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="e59be-118">Standaard verlopen vermeldingen in de lijst tenant-toestaan/blokkeren na 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="e59be-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="e59be-119">U een datum opgeven of instellen dat deze nooit verloopt.</span><span class="sxs-lookup"><span data-stu-id="e59be-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="e59be-120">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e59be-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="e59be-121">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e59be-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="e59be-122">U moet beschikken over bepaalde machtigingen om de procedures in dit onderwerp te kunnen uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="e59be-122">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="e59be-123">Als u waarden wilt toevoegen en verwijderen uit de lijst tenant-toestaan/blokkeren, moet u lid zijn van een van de volgende rolgroepen:</span><span class="sxs-lookup"><span data-stu-id="e59be-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="e59be-124">**Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e59be-124">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="e59be-125">**Organisatiebeheer** of **Hygiënebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="e59be-125">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="e59be-126">Voor alleen-lezen toegang tot de tenant-lijst voor toestaan/blokkeren, moet u lid zijn van een van de volgende rolgroepen:</span><span class="sxs-lookup"><span data-stu-id="e59be-126">For read-only access to the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="e59be-127">**Beveiligingslezer** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e59be-127">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="e59be-128">**Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="e59be-128">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="e59be-129">Gebruik het Security & Compliance Center om URL-vermeldingen te maken in de lijst Tenant Allow/Block</span><span class="sxs-lookup"><span data-stu-id="e59be-129">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="e59be-130">Zie de [URL-syntaxis voor de sectie Tenant toestaan/blokkeren](#url-syntax-for-the-tenant-allowblock-list) lijst later in dit onderwerp voor meer informatie over de syntaxis voor URL-vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="e59be-130">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="e59be-131">Ga in het Security & Compliance Center naar Tenant Allow/Block Lists **voor bedreigingsbeheerbeleid** \> **Policy** \> **Tenant Allow/Block Lists**.</span><span class="sxs-lookup"><span data-stu-id="e59be-131">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="e59be-132">Controleer op de pagina **Tenant toestaan/blokkeren** of het tabblad **URL's** is geselecteerd en klik vervolgens op **Toevoegen**</span><span class="sxs-lookup"><span data-stu-id="e59be-132">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="e59be-133">Configureer in de flyout **Voor nieuwe URL's toevoegen** die wordt weergegeven de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="e59be-133">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="e59be-134">**URL's met jokertekens**toevoegen : Voer één URL per regel in, tot een maximum van 20.</span><span class="sxs-lookup"><span data-stu-id="e59be-134">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="e59be-135">**Blokkeren/Toestaan**: Selecteer of u de opgegeven URL's wilt **toestaan** of **blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="e59be-135">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="e59be-136">**Nooit verlopen**: Doe een van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="e59be-136">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="e59be-137">Controleer of de instelling is uitgeschakeld ( ![ ](../../media/scc-toggle-off.png) Uitschakelen) en gebruik het vak **Verlopen op** om de vervaldatum voor de vermeldingen op te geven.</span><span class="sxs-lookup"><span data-stu-id="e59be-137">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="e59be-138">of</span><span class="sxs-lookup"><span data-stu-id="e59be-138">or</span></span>

     - <span data-ttu-id="e59be-139">Verplaats de schakelaar naar rechts om de items te configureren om nooit te verlopen:</span><span class="sxs-lookup"><span data-stu-id="e59be-139">Move the toggle to the right to configure the entries to never expire:</span></span> ![Inschakelen](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="e59be-141">.</span><span class="sxs-lookup"><span data-stu-id="e59be-141">.</span></span>

   - <span data-ttu-id="e59be-142">**Optionele notitie**: Voer beschrijvende tekst in voor de vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="e59be-142">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="e59be-143">Klik op Toevoegen als u klaar bent met **toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="e59be-143">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="e59be-144">Gebruik het Security & Compliance Center om vermeldingen in de tenant-lijst voor tenant-toestaan/blokkeren weer te geven</span><span class="sxs-lookup"><span data-stu-id="e59be-144">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="e59be-145">Ga in het Security & Compliance Center naar Tenant Allow/Block Lists **voor bedreigingsbeheerbeleid** \> **Policy** \> **Tenant Allow/Block Lists**.</span><span class="sxs-lookup"><span data-stu-id="e59be-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="e59be-146">Selecteer het tabblad **URL's.**</span><span class="sxs-lookup"><span data-stu-id="e59be-146">Select the **URLs** tab.</span></span>

<span data-ttu-id="e59be-147">Klik op de volgende kolomkoppen om in oplopende of aflopende volgorde te sorteren:</span><span class="sxs-lookup"><span data-stu-id="e59be-147">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="e59be-148">**Value**</span><span class="sxs-lookup"><span data-stu-id="e59be-148">**Value**</span></span>
- <span data-ttu-id="e59be-149">**Actie**: **Blokkeren** of **toestaan**.</span><span class="sxs-lookup"><span data-stu-id="e59be-149">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="e59be-150">**Laatst bijgewerkte datum**</span><span class="sxs-lookup"><span data-stu-id="e59be-150">**Last updated date**</span></span>
- <span data-ttu-id="e59be-151">**Vervaldatum**</span><span class="sxs-lookup"><span data-stu-id="e59be-151">**Expiration date**</span></span>
- <span data-ttu-id="e59be-152">**Opmerking**</span><span class="sxs-lookup"><span data-stu-id="e59be-152">**Note**</span></span>

<span data-ttu-id="e59be-153">Klik **op Groeperen** om de items te groeperen op **actie** **(Blokkeren** of **Toestaan)** of **Geen**.</span><span class="sxs-lookup"><span data-stu-id="e59be-153">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="e59be-154">Klik **op Zoeken,** voer een waarde geheel of gedeeltelijk in en druk op ENTER om een specifieke waarde te zoeken.</span><span class="sxs-lookup"><span data-stu-id="e59be-154">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="e59be-155">Wanneer u klaar bent, klikt u op **Clear search** ![ Zoekfunctie wissen ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) wissen.</span><span class="sxs-lookup"><span data-stu-id="e59be-155">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="e59be-156">Klik op **Filter**.</span><span class="sxs-lookup"><span data-stu-id="e59be-156">Click **Filter**.</span></span> <span data-ttu-id="e59be-157">Configureer een van de volgende instellingen in de flyout **Filter** die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="e59be-157">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="e59be-158">**Actie**: Selecteer **Toestaan,** **Blokkeren** of beide.</span><span class="sxs-lookup"><span data-stu-id="e59be-158">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="e59be-159">**Nooit verlopen**: Uitzetten ( ![ ](../../media/scc-toggle-off.png) Uitschakelen) of aan ( ![ Schakel ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) aan).</span><span class="sxs-lookup"><span data-stu-id="e59be-159">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="e59be-160">**Laatst bijgewerkt**: Selecteer een begindatum (**Van),** een einddatum (**Naar**) of beide.</span><span class="sxs-lookup"><span data-stu-id="e59be-160">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="e59be-161">**Vervaldatum**: Selecteer een begindatum (**Vanaf),** een einddatum (**Tot**) of beide.</span><span class="sxs-lookup"><span data-stu-id="e59be-161">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="e59be-162">Klik op **Toepassen**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="e59be-162">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="e59be-163">Als u bestaande filters wilt wissen, klikt u op **Filter**en klikt u in de flyout **Filter** die wordt weergegeven op **Filters wissen**.</span><span class="sxs-lookup"><span data-stu-id="e59be-163">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="e59be-164">Gebruik het Security & Compliance Center om vermeldingen in de tenant-lijst voor tenant-toestaan/blokkeren te wijzigen</span><span class="sxs-lookup"><span data-stu-id="e59be-164">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="e59be-165">U de URL-waarde zelf niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="e59be-165">You can't modify the URL value itself.</span></span> <span data-ttu-id="e59be-166">In plaats daarvan moet u de vermelding verwijderen en opnieuw maken.</span><span class="sxs-lookup"><span data-stu-id="e59be-166">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="e59be-167">Ga in het Security & Compliance Center naar Tenant Allow/Block Lists **voor bedreigingsbeheerbeleid** \> **Policy** \> **Tenant Allow/Block Lists**.</span><span class="sxs-lookup"><span data-stu-id="e59be-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="e59be-168">Selecteer het tabblad **URL's.**</span><span class="sxs-lookup"><span data-stu-id="e59be-168">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="e59be-169">Selecteer het item dat u wilt wijzigen en **klik** op ![ pictogram Bewerken ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) bewerken .</span><span class="sxs-lookup"><span data-stu-id="e59be-169">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="e59be-170">Configureer in de flyout die wordt weergegeven de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="e59be-170">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="e59be-171">**Blokkeren/toestaan**: **Selecteren Toestaan** of **blokkeren**.</span><span class="sxs-lookup"><span data-stu-id="e59be-171">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="e59be-172">**Nooit verlopen**: Doe een van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="e59be-172">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="e59be-173">Controleer of de instelling is uitgeschakeld ( ![ ](../../media/scc-toggle-off.png) Uitschakelen) en gebruik het vak **Verlopen op** om de vervaldatum voor de vermelding op te geven.</span><span class="sxs-lookup"><span data-stu-id="e59be-173">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="e59be-174">of</span><span class="sxs-lookup"><span data-stu-id="e59be-174">or</span></span>

     - <span data-ttu-id="e59be-175">Verplaats de schakelaar naar rechts om de vermelding te configureren om nooit te verlopen:</span><span class="sxs-lookup"><span data-stu-id="e59be-175">Move the toggle to the right to configure the entry to never expire:</span></span> ![Inschakelen](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="e59be-177">.</span><span class="sxs-lookup"><span data-stu-id="e59be-177">.</span></span>

   - <span data-ttu-id="e59be-178">**Optionele notitie**: Voer beschrijvende tekst in voor de vermelding.</span><span class="sxs-lookup"><span data-stu-id="e59be-178">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="e59be-179">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="e59be-179">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="e59be-180">Gebruik het Security & Compliance Center om vermeldingen uit de tenant-lijst voor tenant-toestaan/blokkeren te verwijderen</span><span class="sxs-lookup"><span data-stu-id="e59be-180">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="e59be-181">Ga in het Security & Compliance Center naar Tenant Allow/Block Lists **voor bedreigingsbeheerbeleid** \> **Policy** \> **Tenant Allow/Block Lists**.</span><span class="sxs-lookup"><span data-stu-id="e59be-181">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="e59be-182">Selecteer het tabblad **URL's.**</span><span class="sxs-lookup"><span data-stu-id="e59be-182">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="e59be-183">Selecteer het item dat u wilt verwijderen en **klik** op ![ pictogram Verwijderen verwijderen ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="e59be-183">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="e59be-184">Klik in het waarschuwingsdialoogvenster dat wordt weergegeven op **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="e59be-184">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="e59be-185">Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken om de tenant-lijst voor toestaan/blokkeren te configureren</span><span class="sxs-lookup"><span data-stu-id="e59be-185">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="e59be-186">PowerShell gebruiken om vermeldingen toe te voegen aan de lijst Tenant Allow/Block</span><span class="sxs-lookup"><span data-stu-id="e59be-186">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="e59be-187">Als u vermeldingen wilt toevoegen aan de lijst tenant-toestaan/blokkeren, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="e59be-187">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="e59be-188">In dit voorbeeld wordt een URL-blokvermelding toegevoegd voor contoso.com en alle subdomeinen (bijvoorbeeld contoso.com, www.contoso.com en xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="e59be-188">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="e59be-189">Omdat we de parameters voor vervaldatum of niet-uitademing niet hebben gebruikt, verloopt de vermelding na 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="e59be-189">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="e59be-190">Zie [Nieuwe-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)voor gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="e59be-190">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="e59be-191">PowerShell gebruiken om vermeldingen in de lijst Tenant toestaan/blokkeren weer te geven</span><span class="sxs-lookup"><span data-stu-id="e59be-191">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="e59be-192">Als u vermeldingen in de lijst tenant-toestaan/blokkeren wilt weergeven, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="e59be-192">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="e59be-193">In dit voorbeeld worden alle geblokkeerde URL's geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="e59be-193">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="e59be-194">Zie Lijstitems voor gedetailleerde syntaxis en [parametergegevens](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="e59be-194">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="e59be-195">PowerShell gebruiken om vermeldingen in de lijst tenant-toestaan/blokkeren te wijzigen</span><span class="sxs-lookup"><span data-stu-id="e59be-195">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="e59be-196">U de URL-waarde zelf niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="e59be-196">You can't modify the URL value itself.</span></span> <span data-ttu-id="e59be-197">In plaats daarvan moet u de vermelding verwijderen en opnieuw maken.</span><span class="sxs-lookup"><span data-stu-id="e59be-197">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="e59be-198">Als u vermeldingen in de lijst tenant-toestaan/blokkeren wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="e59be-198">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="e59be-199">In dit voorbeeld wordt de vervaldatum van de opgegeven vermelding gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="e59be-199">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="e59be-200">Zie [Set-TenantAllowBlockListIteMs voor](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="e59be-200">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="e59be-201">PowerShell gebruiken om vermeldingen uit de tenantlijst voor toestaan/blokkeren te verwijderen</span><span class="sxs-lookup"><span data-stu-id="e59be-201">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="e59be-202">Als u vermeldingen uit de lijst tenant-toestaan/blokken wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="e59be-202">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="e59be-203">In dit voorbeeld wordt de opgegeven URL-vermelding verwijderd uit de lijst tenant-toestaan/blokkeren.</span><span class="sxs-lookup"><span data-stu-id="e59be-203">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="e59be-204">Zie [Remove-TenantAllowBlockListIteMs voor](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="e59be-204">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="e59be-205">URL-syntaxis voor de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="e59be-205">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="e59be-206">IP4v- en IPv6-adressen zijn toegestaan, maar TCP/UDP-poorten niet.</span><span class="sxs-lookup"><span data-stu-id="e59be-206">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="e59be-207">Bestandsnaamextensies zijn niet toegestaan (bijvoorbeeld test.pdf).</span><span class="sxs-lookup"><span data-stu-id="e59be-207">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="e59be-208">Unicode wordt niet ondersteund, maar Punycode wel.</span><span class="sxs-lookup"><span data-stu-id="e59be-208">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="e59be-209">Hostnamen zijn toegestaan als alle volgende instructies waar zijn:</span><span class="sxs-lookup"><span data-stu-id="e59be-209">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="e59be-210">De hostnaam bevat een periode.</span><span class="sxs-lookup"><span data-stu-id="e59be-210">The hostname contains a period.</span></span>
  - <span data-ttu-id="e59be-211">Er is ten minste één teken aan de linkerkant van de periode.</span><span class="sxs-lookup"><span data-stu-id="e59be-211">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="e59be-212">Er zijn ten minste twee tekens aan de rechterkant van de periode.</span><span class="sxs-lookup"><span data-stu-id="e59be-212">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="e59be-213">Is bijvoorbeeld `t.co` toegestaan; `.com` of `contoso.` zijn niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="e59be-213">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="e59be-214">Subpaden worden niet geïmpliceerd.</span><span class="sxs-lookup"><span data-stu-id="e59be-214">Subpaths are not implied.</span></span>

  <span data-ttu-id="e59be-215">Omvat bijvoorbeeld `contoso.com` niet `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="e59be-215">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="e59be-216">Jokertekens (\*) zijn toegestaan in de volgende scenario's:</span><span class="sxs-lookup"><span data-stu-id="e59be-216">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="e59be-217">Een linker wildcard moet worden gevolgd door een periode om een subdomein op te geven.</span><span class="sxs-lookup"><span data-stu-id="e59be-217">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="e59be-218">Is bijvoorbeeld `*.contoso.com` toegestaan; `*contoso.com` is niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="e59be-218">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="e59be-219">Een rechter wildcard moet een slash voorwaarts (/) volgen om een pad op te geven.</span><span class="sxs-lookup"><span data-stu-id="e59be-219">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="e59be-220">Is bijvoorbeeld `contoso.com/*` toegestaan; `contoso.com*` of `contoso.com/ab*` zijn niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="e59be-220">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="e59be-221">Alle subpaden worden niet geïmpliceerd door een juiste wildcard.</span><span class="sxs-lookup"><span data-stu-id="e59be-221">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="e59be-222">Omvat bijvoorbeeld `contoso.com/*` niet `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="e59be-222">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="e59be-223">`*.com*`is ongeldig (geen oplosbaar domein en de juiste wildcard volgt geen slash).</span><span class="sxs-lookup"><span data-stu-id="e59be-223">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="e59be-224">Wildcards zijn niet toegestaan in IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="e59be-224">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="e59be-225">Het teken tilde (~) is beschikbaar in de volgende scenario's:</span><span class="sxs-lookup"><span data-stu-id="e59be-225">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="e59be-226">Een linker tilde impliceert een domein en alle subdomeinen.</span><span class="sxs-lookup"><span data-stu-id="e59be-226">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="e59be-227">Bijvoorbeeld `~contoso.com` omvat `contoso.com` en `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="e59be-227">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="e59be-228">URL-vermeldingen die protocollen bevatten (bijvoorbeeld `http://` `https://` , of ) `ftp://` mislukken, omdat URL-vermeldingen van toepassing zijn op alle protocollen.</span><span class="sxs-lookup"><span data-stu-id="e59be-228">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="e59be-229">Een gebruikersnaam of wachtwoord wordt niet ondersteund of vereist.</span><span class="sxs-lookup"><span data-stu-id="e59be-229">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="e59be-230">Citaten (' of ') zijn ongeldige tekens.</span><span class="sxs-lookup"><span data-stu-id="e59be-230">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="e59be-231">Een URL moet waar mogelijk alle omleidingen bevatten.</span><span class="sxs-lookup"><span data-stu-id="e59be-231">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="e59be-232">URL-invoerscenario's</span><span class="sxs-lookup"><span data-stu-id="e59be-232">URL entry scenarios</span></span>

<span data-ttu-id="e59be-233">Geldige URL-vermeldingen en de resultaten ervan worden beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="e59be-233">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="e59be-234">Scenario: Geen wildcards</span><span class="sxs-lookup"><span data-stu-id="e59be-234">Scenario: No wildcards</span></span>

<span data-ttu-id="e59be-235">**Vermelding**:`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="e59be-235">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="e59be-236">**Match toestaan**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-236">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="e59be-237">**Niet overeenkomen met:**</span><span class="sxs-lookup"><span data-stu-id="e59be-237">**Allow not matched**:</span></span>

  - <span data-ttu-id="e59be-238">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-238">abc-contoso.com</span></span>
  - <span data-ttu-id="e59be-239">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="e59be-239">contoso.com/a</span></span>
  - <span data-ttu-id="e59be-240">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-240">payroll.contoso.com</span></span>
  - <span data-ttu-id="e59be-241">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-241">test.com/contoso.com</span></span>
  - <span data-ttu-id="e59be-242">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-242">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="e59be-243">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-243">www.contoso.com</span></span>
  - <span data-ttu-id="e59be-244">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-244">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="e59be-245">**Blokwedstrijd**:</span><span class="sxs-lookup"><span data-stu-id="e59be-245">**Block match**:</span></span>

  - <span data-ttu-id="e59be-246">contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-246">contoso.com</span></span>
  - <span data-ttu-id="e59be-247">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="e59be-247">contoso.com/a</span></span>
  - <span data-ttu-id="e59be-248">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-248">payroll.contoso.com</span></span>
  - <span data-ttu-id="e59be-249">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-249">test.com/contoso.com</span></span>
  - <span data-ttu-id="e59be-250">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-250">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="e59be-251">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-251">www.contoso.com</span></span>
  - <span data-ttu-id="e59be-252">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-252">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="e59be-253">**Blok niet aan elkaar gewaagd**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-253">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="e59be-254">Scenario: Linker wildcard (subdomein)</span><span class="sxs-lookup"><span data-stu-id="e59be-254">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="e59be-255">**Vermelding**:`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="e59be-255">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="e59be-256">Match en **Block match** **toestaan:**</span><span class="sxs-lookup"><span data-stu-id="e59be-256">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="e59be-257">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-257">www.contoso.com</span></span>
  - <span data-ttu-id="e59be-258">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-258">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="e59be-259">**Niet overeenkomen en** **Blokkeren niet overeenkomen:**</span><span class="sxs-lookup"><span data-stu-id="e59be-259">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="e59be-260">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-260">123contoso.com</span></span>
  - <span data-ttu-id="e59be-261">contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-261">contoso.com</span></span>
  - <span data-ttu-id="e59be-262">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-262">test.com/contoso.com</span></span>
  - <span data-ttu-id="e59be-263">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="e59be-263">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="e59be-264">Scenario: Juiste wildcard boven aan het pad</span><span class="sxs-lookup"><span data-stu-id="e59be-264">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="e59be-265">**Vermelding**:`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="e59be-265">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="e59be-266">Match en **Block match** **toestaan:**</span><span class="sxs-lookup"><span data-stu-id="e59be-266">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="e59be-267">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="e59be-267">contoso.com/a/b</span></span>
  - <span data-ttu-id="e59be-268">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="e59be-268">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="e59be-269">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="e59be-269">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="e59be-270">**Niet overeenkomen en** **Blokkeren niet overeenkomen:**</span><span class="sxs-lookup"><span data-stu-id="e59be-270">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="e59be-271">contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-271">contoso.com</span></span>
  - <span data-ttu-id="e59be-272">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="e59be-272">contoso.com/a</span></span>
  - <span data-ttu-id="e59be-273">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-273">www.contoso.com</span></span>
  - <span data-ttu-id="e59be-274">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-274">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="e59be-275">Scenario: Linker tilde</span><span class="sxs-lookup"><span data-stu-id="e59be-275">Scenario: Left tilde</span></span>

<span data-ttu-id="e59be-276">**Vermelding**:`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="e59be-276">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="e59be-277">Match en **Block match** **toestaan:**</span><span class="sxs-lookup"><span data-stu-id="e59be-277">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="e59be-278">contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-278">contoso.com</span></span>
  - <span data-ttu-id="e59be-279">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-279">www.contoso.com</span></span>
  - <span data-ttu-id="e59be-280">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-280">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="e59be-281">**Niet overeenkomen en** **Blokkeren niet overeenkomen:**</span><span class="sxs-lookup"><span data-stu-id="e59be-281">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="e59be-282">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-282">123contoso.com</span></span>
  - <span data-ttu-id="e59be-283">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="e59be-283">contoso.com/abc</span></span>
  - <span data-ttu-id="e59be-284">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="e59be-284">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="e59be-285">Scenario: Rechts wildcard achtervoegsel</span><span class="sxs-lookup"><span data-stu-id="e59be-285">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="e59be-286">**Vermelding**:`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="e59be-286">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="e59be-287">Match en **Block match** **toestaan:**</span><span class="sxs-lookup"><span data-stu-id="e59be-287">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="e59be-288">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="e59be-288">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="e59be-289">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="e59be-289">contoso.com/a</span></span>
  - <span data-ttu-id="e59be-290">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="e59be-290">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="e59be-291">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="e59be-291">contoso.com/ab</span></span>
  - <span data-ttu-id="e59be-292">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="e59be-292">contoso.com/b</span></span>
  - <span data-ttu-id="e59be-293">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="e59be-293">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="e59be-294">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="e59be-294">contoso.com/ba</span></span>

- <span data-ttu-id="e59be-295">**Niet overeenkomen en** **Blok niet overeenkomen :** contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-295">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="e59be-296">Scenario: Subdomein voor linker wildcard en het achtervoegsel van de rechter wildcard</span><span class="sxs-lookup"><span data-stu-id="e59be-296">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="e59be-297">**Vermelding**:`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="e59be-297">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="e59be-298">Match en **Block match** **toestaan:**</span><span class="sxs-lookup"><span data-stu-id="e59be-298">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="e59be-299">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="e59be-299">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="e59be-300">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="e59be-300">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="e59be-301">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="e59be-301">www.contoso.com/a</span></span>
  - <span data-ttu-id="e59be-302">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="e59be-302">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="e59be-303">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="e59be-303">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="e59be-304">**Niet overeenkomen en** **Blok niet overeenkomen :** contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="e59be-304">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="e59be-305">Scenario: Links en rechts tilde</span><span class="sxs-lookup"><span data-stu-id="e59be-305">Scenario: Left and right tilde</span></span>

<span data-ttu-id="e59be-306">**Vermelding**:`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="e59be-306">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="e59be-307">Match en **Block match** **toestaan:**</span><span class="sxs-lookup"><span data-stu-id="e59be-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="e59be-308">contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-308">contoso.com</span></span>
  - <span data-ttu-id="e59be-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="e59be-309">contoso.com/a</span></span>
  - <span data-ttu-id="e59be-310">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-310">www.contoso.com</span></span>
  - <span data-ttu-id="e59be-311">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="e59be-311">www.contoso.com/b</span></span>
  - <span data-ttu-id="e59be-312">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-312">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="e59be-313">**Niet overeenkomen en** **Blokkeren niet overeenkomen:**</span><span class="sxs-lookup"><span data-stu-id="e59be-313">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="e59be-314">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-314">123contoso.com</span></span>
  - <span data-ttu-id="e59be-315">contoso.org</span><span class="sxs-lookup"><span data-stu-id="e59be-315">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="e59be-316">Scenario: IP-adres</span><span class="sxs-lookup"><span data-stu-id="e59be-316">Scenario: IP address</span></span>

<span data-ttu-id="e59be-317">**Vermelding**:`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="e59be-317">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="e59be-318">**Wedstrijd en** **blok wedstrijd toestaan**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="e59be-318">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="e59be-319">**Niet overeenkomen en** **Blokkeren niet overeenkomen:**</span><span class="sxs-lookup"><span data-stu-id="e59be-319">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="e59be-320">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="e59be-320">1.2.3.4/a</span></span>
  - <span data-ttu-id="e59be-321">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="e59be-321">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="e59be-322">IP-adres met juiste wildcard</span><span class="sxs-lookup"><span data-stu-id="e59be-322">IP address with right wildcard</span></span>

<span data-ttu-id="e59be-323">**Vermelding**:`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="e59be-323">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="e59be-324">Match en **Block match** **toestaan:**</span><span class="sxs-lookup"><span data-stu-id="e59be-324">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="e59be-325">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="e59be-325">1.2.3.4/b</span></span>
  - <span data-ttu-id="e59be-326">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="e59be-326">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="e59be-327">Voorbeelden van ongeldige vermeldingen</span><span class="sxs-lookup"><span data-stu-id="e59be-327">Examples of invalid entries</span></span>

<span data-ttu-id="e59be-328">De volgende vermeldingen zijn ongeldig:</span><span class="sxs-lookup"><span data-stu-id="e59be-328">The following entries are invalid:</span></span>

- <span data-ttu-id="e59be-329">**Ontbrekende of ongeldige domeinwaarden:**</span><span class="sxs-lookup"><span data-stu-id="e59be-329">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="e59be-330">Contoso</span><span class="sxs-lookup"><span data-stu-id="e59be-330">contoso</span></span>
  - <span data-ttu-id="e59be-331">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="e59be-331">\*.contoso.\*</span></span>
  - <span data-ttu-id="e59be-332">\*.com</span><span class="sxs-lookup"><span data-stu-id="e59be-332">\*.com</span></span>
  - <span data-ttu-id="e59be-333">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="e59be-333">\*.pdf</span></span>

- <span data-ttu-id="e59be-334">**Wildcard op tekst of zonder spatiëringtekens:**</span><span class="sxs-lookup"><span data-stu-id="e59be-334">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="e59be-335">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="e59be-335">\*contoso.com</span></span>
  - <span data-ttu-id="e59be-336">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="e59be-336">contoso.com\*</span></span>
  - <span data-ttu-id="e59be-337">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="e59be-337">\*1.2.3.4</span></span>
  - <span data-ttu-id="e59be-338">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="e59be-338">1.2.3.4\*</span></span>
  - <span data-ttu-id="e59be-339">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="e59be-339">contoso.com/a\*</span></span>
  - <span data-ttu-id="e59be-340">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="e59be-340">contoso.com/ab\*</span></span>

- <span data-ttu-id="e59be-341">**IP-adressen met poorten:**</span><span class="sxs-lookup"><span data-stu-id="e59be-341">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="e59be-342">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="e59be-342">contoso.com:443</span></span>
  - <span data-ttu-id="e59be-343">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="e59be-343">abc.contoso.com:25</span></span>

- <span data-ttu-id="e59be-344">**Niet-beschrijvende wildcards**:</span><span class="sxs-lookup"><span data-stu-id="e59be-344">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="e59be-345">\*.\*</span><span class="sxs-lookup"><span data-stu-id="e59be-345">\*.\*</span></span>

- <span data-ttu-id="e59be-346">**Middelste wildcards**:</span><span class="sxs-lookup"><span data-stu-id="e59be-346">**Middle wildcards**:</span></span>

  - <span data-ttu-id="e59be-347">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="e59be-347">conto\*so.com</span></span>
  - <span data-ttu-id="e59be-348">conto ~ so.com</span><span class="sxs-lookup"><span data-stu-id="e59be-348">conto~so.com</span></span>

- <span data-ttu-id="e59be-349">**Dubbele wildcards**</span><span class="sxs-lookup"><span data-stu-id="e59be-349">**Double wildcards**</span></span>

  - <span data-ttu-id="e59be-350">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="e59be-350">contoso.com/\*\*</span></span>
  - <span data-ttu-id="e59be-351">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="e59be-351">contoso.com/\*/\*</span></span>
