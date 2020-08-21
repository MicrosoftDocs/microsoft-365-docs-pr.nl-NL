---
title: Toegestane en geblokkeerde Url's beheren in de lijst Tenant toestaan/blokkeren
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie over de configuratie van URL-items in de lijst Tenant toestaan/blokkeren in het beveiligings & nalevings centrum.
ms.openlocfilehash: 888a96f23daf2cf47847466ad4080f310be7f9b4
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845940"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a><span data-ttu-id="ccab3-103">URL's beheren in de lijst met toegestane/geblokkeerde tenants</span><span class="sxs-lookup"><span data-stu-id="ccab3-103">Manage URLs in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="ccab3-104">De functies die in dit onderwerp worden beschreven, zijn in de preview-versie en kunnen worden gewijzigd, en zijn niet beschikbaar in alle organisaties.</span><span class="sxs-lookup"><span data-stu-id="ccab3-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="ccab3-105">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken, kunt u niet akkoord met de EOP-filter Verdict.</span><span class="sxs-lookup"><span data-stu-id="ccab3-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="ccab3-106">U kunt bijvoorbeeld een goed bericht markeren als beschadigd (een fout-positief) of een onjuist bericht mag worden toegestaan via (een onwaar negatief).</span><span class="sxs-lookup"><span data-stu-id="ccab3-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="ccab3-107">Met de lijst Tenant toestaan/blokkeren in de beveiligings & nalevings centrum kunt u de Microsoft 365-filtering handmatig vervangen door de Verdicts.</span><span class="sxs-lookup"><span data-stu-id="ccab3-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="ccab3-108">De lijst Tenant toestaan/blokkeren wordt gebruikt tijdens de e-mail stroom en wanneer de gebruiker klikt.</span><span class="sxs-lookup"><span data-stu-id="ccab3-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="ccab3-109">U kunt Url's opgeven voor het toestaan of blokkeren van de lijst Tenant toestaan/blokkeren.</span><span class="sxs-lookup"><span data-stu-id="ccab3-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="ccab3-110">In dit onderwerp wordt beschreven hoe u items in de lijst met toegestane/geblokkeerde tenants van de beveiligings & of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties kunt configureren met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder postvakken van Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ccab3-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ccab3-111">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="ccab3-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ccab3-112">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="ccab3-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ccab3-113">Als u direct naar de pagina met de **lijst met toegestane/geblokkeerde tenants** wilt gaan, gebruikt u <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="ccab3-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="ccab3-114">In dit onderwerp vindt u een beschrijving van de beschikbare URL-waarden in de [URL-syntaxis voor de sectie lijst met toegestane/geblokkeerde tenants](#url-syntax-for-the-tenant-allowblock-list)</span><span class="sxs-lookup"><span data-stu-id="ccab3-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="ccab3-115">De lijst Tenant toestaan/blokkeren mag maximaal 500 vermeldingen voor Url's zijn.</span><span class="sxs-lookup"><span data-stu-id="ccab3-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLs.</span></span>

- <span data-ttu-id="ccab3-116">Een vermelding moet binnen 15 minuten actief zijn.</span><span class="sxs-lookup"><span data-stu-id="ccab3-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="ccab3-117">Blok vermeldingen hebben voorrang op vermeldingen voor toestaan.</span><span class="sxs-lookup"><span data-stu-id="ccab3-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="ccab3-118">Standaard verloopt de invoer van vermeldingen in de lijst Tenant toestaan/blokkeren na 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="ccab3-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="ccab3-119">U kunt een datum opgeven of instellen dat deze nooit verloopt.</span><span class="sxs-lookup"><span data-stu-id="ccab3-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="ccab3-120">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ccab3-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="ccab3-121">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ccab3-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ccab3-122">U moet beschikken over bepaalde machtigingen om de procedures in dit onderwerp te kunnen uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="ccab3-122">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="ccab3-123">Als u waarden wilt toevoegen aan of verwijderen uit de lijst Tenant toestaan/blokkeren, moet u lid zijn van een van de volgende groepen rollen:</span><span class="sxs-lookup"><span data-stu-id="ccab3-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="ccab3-124">**Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ccab3-124">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="ccab3-125">**Organisatiebeheer** of **Hygiënebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="ccab3-125">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="ccab3-126">Voor alleen-lezen toegang tot de lijst Tenant toestaan/blokkeren moet u lid zijn van een van de volgende rollen groepen:</span><span class="sxs-lookup"><span data-stu-id="ccab3-126">For read-only access to the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="ccab3-127">**Beveiligingslezer** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ccab3-127">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="ccab3-128">**Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="ccab3-128">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ccab3-129">Gebruik het compliance-beveiligings & voor het maken van URL-vermeldingen in de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="ccab3-129">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ccab3-130">Zie voor meer informatie over de syntaxis voor URL-vermeldingen de [URL-syntaxis voor de sectie lijst met toegestane/geblokkeerde tenants](#url-syntax-for-the-tenant-allowblock-list) in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="ccab3-130">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="ccab3-131">Ga in het beveiligings & compliance naar beleidsregels voor het beleid voor **bedreigings beheer** van de \> **Policy** \> **Tenant**.</span><span class="sxs-lookup"><span data-stu-id="ccab3-131">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ccab3-132">Zorg dat op de pagina **lijst met toegestane/geblokkeerde tenants** de optie het tabblad **url's** is geselecteerd en klik op **toevoegen** .</span><span class="sxs-lookup"><span data-stu-id="ccab3-132">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="ccab3-133">Configureer de volgende instellingen in het vervolgmenu **nieuwe Url's toevoegen** dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="ccab3-133">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="ccab3-134">**Url's met jokertekens toevoegen**: Voer één URL per regel in, tot maximaal 20.</span><span class="sxs-lookup"><span data-stu-id="ccab3-134">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="ccab3-135">**Blokkeren/toestaan**: Selecteer of u de opgegeven Url's wilt **toestaan** of **blokkeren** .</span><span class="sxs-lookup"><span data-stu-id="ccab3-135">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="ccab3-136">**Verloopt nooit**: Voer een van de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="ccab3-136">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="ccab3-137">Controleer of de instelling is uitgeschakeld (schakelt ![ uit ](../../media/scc-toggle-off.png) ) en gebruik het vak **verloopt op** om de vervaldatum voor de items op te geven.</span><span class="sxs-lookup"><span data-stu-id="ccab3-137">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="ccab3-138">of</span><span class="sxs-lookup"><span data-stu-id="ccab3-138">or</span></span>

     - <span data-ttu-id="ccab3-139">Zet de wisselknop naar rechts om de items zodanig te configureren dat deze nooit verloopt:</span><span class="sxs-lookup"><span data-stu-id="ccab3-139">Move the toggle to the right to configure the entries to never expire:</span></span> ![Inschakelen](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="ccab3-141">.</span><span class="sxs-lookup"><span data-stu-id="ccab3-141">.</span></span>

   - <span data-ttu-id="ccab3-142">**Optionele opmerking**: Voer een beschrijvende tekst voor de vermeldingen in.</span><span class="sxs-lookup"><span data-stu-id="ccab3-142">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="ccab3-143">Wanneer u klaar bent, klikt u op **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="ccab3-143">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ccab3-144">De beveiligings & voor compliance gebruiken om vermeldingen weer te geven in de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="ccab3-144">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="ccab3-145">Ga in het beveiligings & compliance naar beleidsregels voor het beleid voor **bedreigings beheer** van de \> **Policy** \> **Tenant**.</span><span class="sxs-lookup"><span data-stu-id="ccab3-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ccab3-146">Selecteer het tabblad **url's** .</span><span class="sxs-lookup"><span data-stu-id="ccab3-146">Select the **URLs** tab.</span></span>

<span data-ttu-id="ccab3-147">Klik op de volgende kolomkoppen om te sorteren in oplopende of aflopende volgorde:</span><span class="sxs-lookup"><span data-stu-id="ccab3-147">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="ccab3-148">**Value**</span><span class="sxs-lookup"><span data-stu-id="ccab3-148">**Value**</span></span>
- <span data-ttu-id="ccab3-149">**Actie**: **blokkeren** of **toestaan**.</span><span class="sxs-lookup"><span data-stu-id="ccab3-149">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="ccab3-150">**Laatste update datum**</span><span class="sxs-lookup"><span data-stu-id="ccab3-150">**Last updated date**</span></span>
- <span data-ttu-id="ccab3-151">**Vervaldatum**</span><span class="sxs-lookup"><span data-stu-id="ccab3-151">**Expiration date**</span></span>
- <span data-ttu-id="ccab3-152">**Ziet**</span><span class="sxs-lookup"><span data-stu-id="ccab3-152">**Note**</span></span>

<span data-ttu-id="ccab3-153">Klik op **groeperen** om de items te groeperen op **actie** (**blokkeren** of **toestaan**) of **geen**.</span><span class="sxs-lookup"><span data-stu-id="ccab3-153">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="ccab3-154">Klik op **zoeken**, typ de gehele of gedeeltelijke waarde en druk op ENTER om een bepaalde waarde te zoeken.</span><span class="sxs-lookup"><span data-stu-id="ccab3-154">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="ccab3-155">Wanneer u klaar bent, klikt u op de knop **Zoek** actie wissen ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="ccab3-155">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="ccab3-156">Klik op **filter**.</span><span class="sxs-lookup"><span data-stu-id="ccab3-156">Click **Filter**.</span></span> <span data-ttu-id="ccab3-157">Configureer de volgende instellingen in de **gefilterde** flyout van het filter dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="ccab3-157">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="ccab3-158">**Actie**: Selecteer **toestaan**, **blokkeren** of beide.</span><span class="sxs-lookup"><span data-stu-id="ccab3-158">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="ccab3-159">**Verloopt nooit**: selecteren (uitschakelen ![ ](../../media/scc-toggle-off.png) ) of aan ( ![ wisselknop ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ).</span><span class="sxs-lookup"><span data-stu-id="ccab3-159">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="ccab3-160">**Laatst bijgewerkt**: Selecteer een begindatum (**van**), een einddatum (**en**) of beide.</span><span class="sxs-lookup"><span data-stu-id="ccab3-160">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="ccab3-161">**Vervaldatum**: Selecteer een begindatum (**van**), een einddatum (**en**) of beide.</span><span class="sxs-lookup"><span data-stu-id="ccab3-161">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="ccab3-162">Wanneer u klaar bent, klikt u op **toepassen**.</span><span class="sxs-lookup"><span data-stu-id="ccab3-162">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="ccab3-163">Als u bestaande filters wilt wissen, klikt u op **filter**en klikt u in het **filter** flyout dat wordt weergegeven op **filters wissen**.</span><span class="sxs-lookup"><span data-stu-id="ccab3-163">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ccab3-164">Met behulp van het compliance-beveiligings & voor het wijzigen van vermeldingen in de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="ccab3-164">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ccab3-165">U kunt de URL-waarde zelf niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="ccab3-165">You can't modify the URL value itself.</span></span> <span data-ttu-id="ccab3-166">In plaats daarvan moet u de vermelding verwijderen en opnieuw maken.</span><span class="sxs-lookup"><span data-stu-id="ccab3-166">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="ccab3-167">Ga in het beveiligings & compliance naar beleidsregels voor het beleid voor **bedreigings beheer** van de \> **Policy** \> **Tenant**.</span><span class="sxs-lookup"><span data-stu-id="ccab3-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ccab3-168">Selecteer het tabblad **url's** .</span><span class="sxs-lookup"><span data-stu-id="ccab3-168">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="ccab3-169">Selecteer de vermelding die u wilt wijzigen en klik vervolgens op het **Edit** ![ pictogram bewerken bewerken ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="ccab3-169">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="ccab3-170">Configureer de volgende instellingen in het vervolgmenu dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="ccab3-170">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="ccab3-171">**Blokkeren/toestaan**: Selecteer **accepteren** of **blokkeren**.</span><span class="sxs-lookup"><span data-stu-id="ccab3-171">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="ccab3-172">**Verloopt nooit**: Voer een van de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="ccab3-172">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="ccab3-173">Controleer of de instelling is uitgeschakeld (uitgeschakeld ![ ](../../media/scc-toggle-off.png) ) en gebruik het vak **verloopt op** om de verloopdatum voor de invoer op te geven.</span><span class="sxs-lookup"><span data-stu-id="ccab3-173">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="ccab3-174">of</span><span class="sxs-lookup"><span data-stu-id="ccab3-174">or</span></span>

     - <span data-ttu-id="ccab3-175">Schuif de wisselknop naar rechts om het item zo te configureren dat het nooit verloopt:</span><span class="sxs-lookup"><span data-stu-id="ccab3-175">Move the toggle to the right to configure the entry to never expire:</span></span> ![Inschakelen](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="ccab3-177">.</span><span class="sxs-lookup"><span data-stu-id="ccab3-177">.</span></span>

   - <span data-ttu-id="ccab3-178">**Optionele opmerking**: Typ een beschrijvende tekst voor de vermelding.</span><span class="sxs-lookup"><span data-stu-id="ccab3-178">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="ccab3-179">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="ccab3-179">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="ccab3-180">Met behulp van het compliance-beveiligings & voor het verwijderen van vermeldingen uit de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="ccab3-180">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="ccab3-181">Ga in het beveiligings & compliance naar beleidsregels voor het beleid voor **bedreigings beheer** van de \> **Policy** \> **Tenant**.</span><span class="sxs-lookup"><span data-stu-id="ccab3-181">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ccab3-182">Selecteer het tabblad **url's** .</span><span class="sxs-lookup"><span data-stu-id="ccab3-182">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="ccab3-183">Selecteer de vermelding die u **wilt verwijderen en klik op** ![ verwijderen ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="ccab3-183">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="ccab3-184">In het waarschuwingsvenster dat wordt weergegeven, klikt u op **verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="ccab3-184">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="ccab3-185">PowerShell van Exchange Online of zelfstandige EOP PowerShell gebruiken voor het configureren van de lijst met toegestane/geblokkeerde tenants</span><span class="sxs-lookup"><span data-stu-id="ccab3-185">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ccab3-186">PowerShell gebruiken om vermeldingen toe te voegen in de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="ccab3-186">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ccab3-187">Gebruik de volgende syntaxis om vermeldingen toe te voegen aan de lijst Tenant toestaan/blokkeren:</span><span class="sxs-lookup"><span data-stu-id="ccab3-187">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="ccab3-188">In dit voorbeeld wordt een URL-blok vermelding toegevoegd voor contoso.com en alle subdomeinen (bijvoorbeeld contoso.com, www.contoso.com en xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ccab3-188">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="ccab3-189">Aangezien we de parameters voor ExpirationDate en verstrijken niet gebruiken, verloopt de invoer na 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="ccab3-189">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="ccab3-190">Zie [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="ccab3-190">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ccab3-191">PowerShell gebruiken om vermeldingen weer te geven in de lijst met toegestane/geblokkeerde tenants</span><span class="sxs-lookup"><span data-stu-id="ccab3-191">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ccab3-192">Als u vermeldingen wilt weergeven in de lijst Tenant toestaan/blokkeren, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="ccab3-192">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="ccab3-193">In het volgende voorbeeld worden alle geblokkeerde Url's geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="ccab3-193">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="ccab3-194">Zie [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="ccab3-194">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ccab3-195">PowerShell gebruiken om vermeldingen te wijzigen in de lijst met toegestane/geblokkeerde tenants</span><span class="sxs-lookup"><span data-stu-id="ccab3-195">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ccab3-196">U kunt de URL-waarde zelf niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="ccab3-196">You can't modify the URL value itself.</span></span> <span data-ttu-id="ccab3-197">In plaats daarvan moet u de vermelding verwijderen en opnieuw maken.</span><span class="sxs-lookup"><span data-stu-id="ccab3-197">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="ccab3-198">Gebruik de volgende syntaxis om vermeldingen te wijzigen in de lijst toestaan/blokkeren van de Tenant:</span><span class="sxs-lookup"><span data-stu-id="ccab3-198">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="ccab3-199">In dit voorbeeld wordt de vervaldatum van het opgegeven item gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="ccab3-199">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="ccab3-200">Zie [set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="ccab3-200">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="ccab3-201">PowerShell gebruiken om vermeldingen te verwijderen uit de lijst toestaan/blokkeren van de Tenant</span><span class="sxs-lookup"><span data-stu-id="ccab3-201">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="ccab3-202">Gebruik de volgende syntaxis om vermeldingen te verwijderen uit de lijst toestaan/blokkeren van de Tenant:</span><span class="sxs-lookup"><span data-stu-id="ccab3-202">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="ccab3-203">In dit voorbeeld wordt de opgegeven URL-vermelding uit de lijst toestaan/blok Tenant verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ccab3-203">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="ccab3-204">Zie [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="ccab3-204">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="ccab3-205">URL-syntaxis voor de lijst met toegestane/geblokkeerde tenants</span><span class="sxs-lookup"><span data-stu-id="ccab3-205">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="ccab3-206">IP4v en IPv6-adressen zijn toegestaan, maar de TCP/UDP-poorten zijn niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="ccab3-206">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="ccab3-207">Bestandsextensies zijn niet toegestaan (bijvoorbeeld test.pdf).</span><span class="sxs-lookup"><span data-stu-id="ccab3-207">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="ccab3-208">Unicode wordt niet ondersteund, maar punycode is.</span><span class="sxs-lookup"><span data-stu-id="ccab3-208">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="ccab3-209">Hostnamen zijn toegestaan als alle volgende instructies waar zijn:</span><span class="sxs-lookup"><span data-stu-id="ccab3-209">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="ccab3-210">De hostname bevat een punt.</span><span class="sxs-lookup"><span data-stu-id="ccab3-210">The hostname contains a period.</span></span>
  - <span data-ttu-id="ccab3-211">Het teken links van de periode moet minimaal één teken bevatten.</span><span class="sxs-lookup"><span data-stu-id="ccab3-211">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="ccab3-212">Rechts van de periode bestaan minimaal twee tekens.</span><span class="sxs-lookup"><span data-stu-id="ccab3-212">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="ccab3-213">Dit is bijvoorbeeld `t.co` toegestaan; `.com` of `contoso.` niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="ccab3-213">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="ccab3-214">Subpaden zijn niet impliciet.</span><span class="sxs-lookup"><span data-stu-id="ccab3-214">Subpaths are not implied.</span></span>

  <span data-ttu-id="ccab3-215">Dit is bijvoorbeeld `contoso.com` niet inbegrepen `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="ccab3-215">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="ccab3-216">Jokertekens (\*) zijn toegestaan in de volgende scenario's:</span><span class="sxs-lookup"><span data-stu-id="ccab3-216">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="ccab3-217">Een sterretje links moet worden gevolgd door een punt voor het opgeven van een subdomein.</span><span class="sxs-lookup"><span data-stu-id="ccab3-217">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="ccab3-218">`*.contoso.com`Is bijvoorbeeld toegestaan; mag `*contoso.com` niet worden toegestaan.</span><span class="sxs-lookup"><span data-stu-id="ccab3-218">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="ccab3-219">Een jokerteken voor rechts moet de volgende schuine streep (/) volgen om een pad op te geven.</span><span class="sxs-lookup"><span data-stu-id="ccab3-219">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="ccab3-220">Dit is bijvoorbeeld `contoso.com/*` toegestaan; `contoso.com*` of `contoso.com/ab*` niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="ccab3-220">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="ccab3-221">Alle subpaden zijn niet impliciet door een juiste jokerteken.</span><span class="sxs-lookup"><span data-stu-id="ccab3-221">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="ccab3-222">Dit is bijvoorbeeld `contoso.com/*` niet inbegrepen `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="ccab3-222">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="ccab3-223">`*.com*` is ongeldig (geen oplosbaar domein en de juiste jokertekens volgen geen schuine streep naar rechts).</span><span class="sxs-lookup"><span data-stu-id="ccab3-223">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="ccab3-224">Jokertekens zijn niet toegestaan in IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="ccab3-224">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="ccab3-225">Het tilde (~) is beschikbaar in de volgende scenario's:</span><span class="sxs-lookup"><span data-stu-id="ccab3-225">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="ccab3-226">Een wegge tilde houdt een domein en alle subdomeinen in.</span><span class="sxs-lookup"><span data-stu-id="ccab3-226">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="ccab3-227">Bijvoorbeeld `~contoso.com` bevat `contoso.com` en `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="ccab3-227">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="ccab3-228">URL-vermeldingen die protocollen bevatten (bijvoorbeeld, `http://` `https://` of `ftp://` ), mislukken omdat URL-vermeldingen op alle protocollen van toepassing zijn.</span><span class="sxs-lookup"><span data-stu-id="ccab3-228">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="ccab3-229">Een gebruikersnaam of wachtwoord wordt niet ondersteund of vereist.</span><span class="sxs-lookup"><span data-stu-id="ccab3-229">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="ccab3-230">Aanhalingstekens (' of ') zijn ongeldige tekens.</span><span class="sxs-lookup"><span data-stu-id="ccab3-230">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="ccab3-231">Een URL moet alle redirecties bevatten, waar mogelijk.</span><span class="sxs-lookup"><span data-stu-id="ccab3-231">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="ccab3-232">Scenario's voor URL-invoer</span><span class="sxs-lookup"><span data-stu-id="ccab3-232">URL entry scenarios</span></span>

<span data-ttu-id="ccab3-233">Geldige URL-vermeldingen en de bijbehorende resultaten worden beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="ccab3-233">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="ccab3-234">Scenario: geen jokertekens</span><span class="sxs-lookup"><span data-stu-id="ccab3-234">Scenario: No wildcards</span></span>

<span data-ttu-id="ccab3-235">**Invoer**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="ccab3-235">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="ccab3-236">**Overeenkomst toestaan**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccab3-236">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="ccab3-237">Mag **niet worden vergeleken**:</span><span class="sxs-lookup"><span data-stu-id="ccab3-237">**Allow not matched**:</span></span>

  - <span data-ttu-id="ccab3-238">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccab3-238">abc-contoso.com</span></span>
  - <span data-ttu-id="ccab3-239">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ccab3-239">contoso.com/a</span></span>
  - <span data-ttu-id="ccab3-240">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccab3-240">payroll.contoso.com</span></span>
  - <span data-ttu-id="ccab3-241">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccab3-241">test.com/contoso.com</span></span>
  - <span data-ttu-id="ccab3-242">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccab3-242">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="ccab3-243">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccab3-243">www.contoso.com</span></span>
  - <span data-ttu-id="ccab3-244">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="ccab3-244">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="ccab3-245">**Blok treffer**:</span><span class="sxs-lookup"><span data-stu-id="ccab3-245">**Block match**:</span></span>

  - <span data-ttu-id="ccab3-246">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccab3-246">contoso.com</span></span>
  - <span data-ttu-id="ccab3-247">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ccab3-247">contoso.com/a</span></span>
  - <span data-ttu-id="ccab3-248">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccab3-248">payroll.contoso.com</span></span>
  - <span data-ttu-id="ccab3-249">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccab3-249">test.com/contoso.com</span></span>
  - <span data-ttu-id="ccab3-250">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccab3-250">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="ccab3-251">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccab3-251">www.contoso.com</span></span>
  - <span data-ttu-id="ccab3-252">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="ccab3-252">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="ccab3-253">**Blok niet-gerelateerde**waarde: ABC-contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccab3-253">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="ccab3-254">Scenario: links jokerteken (subdomein)</span><span class="sxs-lookup"><span data-stu-id="ccab3-254">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="ccab3-255">**Invoer**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="ccab3-255">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="ccab3-256">Overeenkomst toestaan en **blokkeren** **toestaan** :</span><span class="sxs-lookup"><span data-stu-id="ccab3-256">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ccab3-257">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccab3-257">www.contoso.com</span></span>
  - <span data-ttu-id="ccab3-258">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccab3-258">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="ccab3-259">**Niet-gematchte** en **geblokkeerde blokkeren**:</span><span class="sxs-lookup"><span data-stu-id="ccab3-259">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ccab3-260">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccab3-260">123contoso.com</span></span>
  - <span data-ttu-id="ccab3-261">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccab3-261">contoso.com</span></span>
  - <span data-ttu-id="ccab3-262">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccab3-262">test.com/contoso.com</span></span>
  - <span data-ttu-id="ccab3-263">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="ccab3-263">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="ccab3-264">Scenario: rechts jokerteken boven aan het pad</span><span class="sxs-lookup"><span data-stu-id="ccab3-264">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="ccab3-265">**Invoer**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="ccab3-265">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="ccab3-266">Overeenkomst toestaan en **blokkeren** **toestaan** :</span><span class="sxs-lookup"><span data-stu-id="ccab3-266">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ccab3-267">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="ccab3-267">contoso.com/a/b</span></span>
  - <span data-ttu-id="ccab3-268">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="ccab3-268">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="ccab3-269">contoso. com/a/? q = joe@t. com</span><span class="sxs-lookup"><span data-stu-id="ccab3-269">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="ccab3-270">**Niet-gematchte** en **geblokkeerde blokkeren**:</span><span class="sxs-lookup"><span data-stu-id="ccab3-270">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ccab3-271">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccab3-271">contoso.com</span></span>
  - <span data-ttu-id="ccab3-272">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ccab3-272">contoso.com/a</span></span>
  - <span data-ttu-id="ccab3-273">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccab3-273">www.contoso.com</span></span>
  - <span data-ttu-id="ccab3-274">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="ccab3-274">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="ccab3-275">Scenario: de tilde links</span><span class="sxs-lookup"><span data-stu-id="ccab3-275">Scenario: Left tilde</span></span>

<span data-ttu-id="ccab3-276">**Invoer**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="ccab3-276">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="ccab3-277">Overeenkomst toestaan en **blokkeren** **toestaan** :</span><span class="sxs-lookup"><span data-stu-id="ccab3-277">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ccab3-278">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccab3-278">contoso.com</span></span>
  - <span data-ttu-id="ccab3-279">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccab3-279">www.contoso.com</span></span>
  - <span data-ttu-id="ccab3-280">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccab3-280">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="ccab3-281">**Niet-gematchte** en **geblokkeerde blokkeren**:</span><span class="sxs-lookup"><span data-stu-id="ccab3-281">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ccab3-282">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccab3-282">123contoso.com</span></span>
  - <span data-ttu-id="ccab3-283">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="ccab3-283">contoso.com/abc</span></span>
  - <span data-ttu-id="ccab3-284">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="ccab3-284">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="ccab3-285">Scenario: achtervoegsel van jokerteken</span><span class="sxs-lookup"><span data-stu-id="ccab3-285">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="ccab3-286">**Invoer**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="ccab3-286">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="ccab3-287">Overeenkomst toestaan en **blokkeren** **toestaan** :</span><span class="sxs-lookup"><span data-stu-id="ccab3-287">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ccab3-288">contoso. com/? q = whatever@fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="ccab3-288">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="ccab3-289">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ccab3-289">contoso.com/a</span></span>
  - <span data-ttu-id="ccab3-290">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="ccab3-290">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="ccab3-291">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="ccab3-291">contoso.com/ab</span></span>
  - <span data-ttu-id="ccab3-292">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="ccab3-292">contoso.com/b</span></span>
  - <span data-ttu-id="ccab3-293">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="ccab3-293">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="ccab3-294">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="ccab3-294">contoso.com/ba</span></span>

- <span data-ttu-id="ccab3-295">**Niet-afgestemde** en niet- **gematchte blokkeren**toestaan: contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccab3-295">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="ccab3-296">Scenario: het subdomein met jokertekens en het achtervoegsel rechts</span><span class="sxs-lookup"><span data-stu-id="ccab3-296">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="ccab3-297">**Invoer**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="ccab3-297">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="ccab3-298">Overeenkomst toestaan en **blokkeren** **toestaan** :</span><span class="sxs-lookup"><span data-stu-id="ccab3-298">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ccab3-299">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="ccab3-299">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="ccab3-300">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="ccab3-300">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="ccab3-301">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ccab3-301">www.contoso.com/a</span></span>
  - <span data-ttu-id="ccab3-302">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="ccab3-302">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="ccab3-303">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="ccab3-303">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="ccab3-304">**Niet-afgestemde** en niet- **gematchte blokkeren**toestaan: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="ccab3-304">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="ccab3-305">Scenario: linker-en rechter tilde</span><span class="sxs-lookup"><span data-stu-id="ccab3-305">Scenario: Left and right tilde</span></span>

<span data-ttu-id="ccab3-306">**Invoer**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="ccab3-306">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="ccab3-307">Overeenkomst toestaan en **blokkeren** **toestaan** :</span><span class="sxs-lookup"><span data-stu-id="ccab3-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ccab3-308">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccab3-308">contoso.com</span></span>
  - <span data-ttu-id="ccab3-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ccab3-309">contoso.com/a</span></span>
  - <span data-ttu-id="ccab3-310">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccab3-310">www.contoso.com</span></span>
  - <span data-ttu-id="ccab3-311">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="ccab3-311">www.contoso.com/b</span></span>
  - <span data-ttu-id="ccab3-312">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccab3-312">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="ccab3-313">**Niet-gematchte** en **geblokkeerde blokkeren**:</span><span class="sxs-lookup"><span data-stu-id="ccab3-313">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ccab3-314">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccab3-314">123contoso.com</span></span>
  - <span data-ttu-id="ccab3-315">contoso.org</span><span class="sxs-lookup"><span data-stu-id="ccab3-315">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="ccab3-316">Scenario: IP-adres</span><span class="sxs-lookup"><span data-stu-id="ccab3-316">Scenario: IP address</span></span>

<span data-ttu-id="ccab3-317">**Invoer**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="ccab3-317">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="ccab3-318">**Overeenkomst toestaan** en **blokkeren**toestaan: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="ccab3-318">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="ccab3-319">**Niet-gematchte** en **geblokkeerde blokkeren**:</span><span class="sxs-lookup"><span data-stu-id="ccab3-319">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ccab3-320">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="ccab3-320">1.2.3.4/a</span></span>
  - <span data-ttu-id="ccab3-321">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="ccab3-321">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="ccab3-322">IP-adres met jokerteken rechts</span><span class="sxs-lookup"><span data-stu-id="ccab3-322">IP address with right wildcard</span></span>

<span data-ttu-id="ccab3-323">**Invoer**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="ccab3-323">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="ccab3-324">Overeenkomst toestaan en **blokkeren** **toestaan** :</span><span class="sxs-lookup"><span data-stu-id="ccab3-324">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ccab3-325">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="ccab3-325">1.2.3.4/b</span></span>
  - <span data-ttu-id="ccab3-326">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="ccab3-326">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="ccab3-327">Voorbeelden van ongeldige vermeldingen</span><span class="sxs-lookup"><span data-stu-id="ccab3-327">Examples of invalid entries</span></span>

<span data-ttu-id="ccab3-328">De volgende vermeldingen zijn ongeldig:</span><span class="sxs-lookup"><span data-stu-id="ccab3-328">The following entries are invalid:</span></span>

- <span data-ttu-id="ccab3-329">**Ontbrekende of ongeldige domein waarden**:</span><span class="sxs-lookup"><span data-stu-id="ccab3-329">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="ccab3-330">uitgeverij</span><span class="sxs-lookup"><span data-stu-id="ccab3-330">contoso</span></span>
  - <span data-ttu-id="ccab3-331">\*uitgeverij.\*</span><span class="sxs-lookup"><span data-stu-id="ccab3-331">\*.contoso.\*</span></span>
  - <span data-ttu-id="ccab3-332">\*. com</span><span class="sxs-lookup"><span data-stu-id="ccab3-332">\*.com</span></span>
  - <span data-ttu-id="ccab3-333">\*. PDF</span><span class="sxs-lookup"><span data-stu-id="ccab3-333">\*.pdf</span></span>

- <span data-ttu-id="ccab3-334">**Jokertekens voor tekst of zonder spaties**:</span><span class="sxs-lookup"><span data-stu-id="ccab3-334">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="ccab3-335">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccab3-335">\*contoso.com</span></span>
  - <span data-ttu-id="ccab3-336">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="ccab3-336">contoso.com\*</span></span>
  - <span data-ttu-id="ccab3-337">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="ccab3-337">\*1.2.3.4</span></span>
  - <span data-ttu-id="ccab3-338">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="ccab3-338">1.2.3.4\*</span></span>
  - <span data-ttu-id="ccab3-339">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="ccab3-339">contoso.com/a\*</span></span>
  - <span data-ttu-id="ccab3-340">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="ccab3-340">contoso.com/ab\*</span></span>

- <span data-ttu-id="ccab3-341">**IP-adressen met poorten**:</span><span class="sxs-lookup"><span data-stu-id="ccab3-341">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="ccab3-342">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="ccab3-342">contoso.com:443</span></span>
  - <span data-ttu-id="ccab3-343">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="ccab3-343">abc.contoso.com:25</span></span>

- <span data-ttu-id="ccab3-344">**Niet-beschrijvende jokertekens**:</span><span class="sxs-lookup"><span data-stu-id="ccab3-344">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="ccab3-345">\*.\*</span><span class="sxs-lookup"><span data-stu-id="ccab3-345">\*.\*</span></span>

- <span data-ttu-id="ccab3-346">**Jokertekens**voor het midden:</span><span class="sxs-lookup"><span data-stu-id="ccab3-346">**Middle wildcards**:</span></span>

  - <span data-ttu-id="ccab3-347">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="ccab3-347">conto\*so.com</span></span>
  - <span data-ttu-id="ccab3-348">rel. com</span><span class="sxs-lookup"><span data-stu-id="ccab3-348">conto~so.com</span></span>

- <span data-ttu-id="ccab3-349">**Dubbele jokertekens**</span><span class="sxs-lookup"><span data-stu-id="ccab3-349">**Double wildcards**</span></span>

  - <span data-ttu-id="ccab3-350">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="ccab3-350">contoso.com/\*\*</span></span>
  - <span data-ttu-id="ccab3-351">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="ccab3-351">contoso.com/\*/\*</span></span>
