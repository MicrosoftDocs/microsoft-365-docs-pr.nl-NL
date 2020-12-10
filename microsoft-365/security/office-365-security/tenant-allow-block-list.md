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
ms.openlocfilehash: 0fdfa23ba22b240032e7a6888948de180aa0f6ae
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/10/2020
ms.locfileid: "49614962"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a><span data-ttu-id="ee254-103">URL's beheren in de lijst met toegestane/geblokkeerde tenants</span><span class="sxs-lookup"><span data-stu-id="ee254-103">Manage URLs in the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="ee254-104">De functies die in dit onderwerp worden beschreven, zijn in de preview-versie en kunnen worden gewijzigd, en zijn niet beschikbaar in alle organisaties.</span><span class="sxs-lookup"><span data-stu-id="ee254-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="ee254-105">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken, kunt u niet akkoord met de EOP-filter Verdict.</span><span class="sxs-lookup"><span data-stu-id="ee254-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="ee254-106">U kunt bijvoorbeeld een goed bericht markeren als beschadigd (een fout-positief) of een onjuist bericht mag worden toegestaan via (een onwaar negatief).</span><span class="sxs-lookup"><span data-stu-id="ee254-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="ee254-107">Met de lijst Tenant toestaan/blokkeren in de beveiligings & nalevings centrum kunt u de Microsoft 365-filtering handmatig vervangen door de Verdicts.</span><span class="sxs-lookup"><span data-stu-id="ee254-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="ee254-108">De lijst Tenant toestaan/blokkeren wordt gebruikt tijdens de e-mail stroom en wanneer de gebruiker klikt.</span><span class="sxs-lookup"><span data-stu-id="ee254-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="ee254-109">U kunt Url's opgeven voor het toestaan of blokkeren van de lijst Tenant toestaan/blokkeren.</span><span class="sxs-lookup"><span data-stu-id="ee254-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="ee254-110">In dit onderwerp wordt beschreven hoe u items in de lijst met toegestane/geblokkeerde tenants van de beveiligings & of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties kunt configureren met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder postvakken van Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ee254-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ee254-111">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="ee254-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ee254-112">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="ee254-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ee254-113">Als u direct naar de pagina met de **lijst met toegestane/geblokkeerde tenants** wilt gaan, gebruikt u <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="ee254-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="ee254-114">In dit onderwerp vindt u een beschrijving van de beschikbare URL-waarden in de [URL-syntaxis voor de sectie lijst met toegestane/geblokkeerde tenants](#url-syntax-for-the-tenant-allowblock-list)</span><span class="sxs-lookup"><span data-stu-id="ee254-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="ee254-115">De lijst Tenant toestaan/blokkeren mag maximaal 500 vermeldingen voor Url's zijn.</span><span class="sxs-lookup"><span data-stu-id="ee254-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLs.</span></span>

- <span data-ttu-id="ee254-116">Een vermelding moet binnen 15 minuten actief zijn.</span><span class="sxs-lookup"><span data-stu-id="ee254-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="ee254-117">Blok vermeldingen hebben voorrang op vermeldingen voor toestaan.</span><span class="sxs-lookup"><span data-stu-id="ee254-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="ee254-118">Standaard verloopt de invoer van vermeldingen in de lijst Tenant toestaan/blokkeren na 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="ee254-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="ee254-119">U kunt een datum opgeven of instellen dat deze nooit verloopt.</span><span class="sxs-lookup"><span data-stu-id="ee254-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="ee254-120">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee254-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="ee254-121">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee254-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ee254-122">Je moet beschikken over toegewezen machtigingen in het Beveiligings- en compliancecentrum voor het uitvoeren van de procedures in dit onderwerp:</span><span class="sxs-lookup"><span data-stu-id="ee254-122">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="ee254-123">Als u waarden wilt toevoegen aan of verwijderen uit de lijst Tenant toestaan/blokkeren, moet u lid zijn van de rollen groepen **Organisatiebeheer** of **beveiligingsbeheerder** .</span><span class="sxs-lookup"><span data-stu-id="ee254-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="ee254-124">Voor alleen-lezen toegang tot de lijst Tenant toegestaan/blokkeren moet u lid zijn van de rollen groepen **algemene lezer** of **beveiligings lezer** .</span><span class="sxs-lookup"><span data-stu-id="ee254-124">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="ee254-125">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ee254-125">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="ee254-126">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="ee254-126">**Notes**:</span></span>

  - <span data-ttu-id="ee254-127">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ee254-127">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ee254-128">Raadpleeg [Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ee254-128">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="ee254-129">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="ee254-129">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ee254-130">Gebruik het compliance-beveiligings & voor het maken van URL-vermeldingen in de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="ee254-130">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ee254-131">Zie voor meer informatie over de syntaxis voor URL-vermeldingen de [URL-syntaxis voor de sectie lijst met toegestane/geblokkeerde tenants](#url-syntax-for-the-tenant-allowblock-list) in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="ee254-131">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="ee254-132">Ga in het beveiligings & compliance naar beleidsregels voor het beleid voor **bedreigings beheer** van de \> **Policy** \> **Tenant**.</span><span class="sxs-lookup"><span data-stu-id="ee254-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ee254-133">Zorg dat op de pagina **lijst met toegestane/geblokkeerde tenants** de optie het tabblad **url's** is geselecteerd en klik op **toevoegen** .</span><span class="sxs-lookup"><span data-stu-id="ee254-133">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="ee254-134">Configureer de volgende instellingen in het vervolgmenu **nieuwe Url's toevoegen** dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="ee254-134">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="ee254-135">**Url's met jokertekens toevoegen**: Voer één URL per regel in, tot maximaal 20.</span><span class="sxs-lookup"><span data-stu-id="ee254-135">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="ee254-136">**Blokkeren/toestaan**: Selecteer of u de opgegeven Url's wilt **toestaan** of **blokkeren** .</span><span class="sxs-lookup"><span data-stu-id="ee254-136">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="ee254-137">**Verloopt nooit**: Voer een van de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="ee254-137">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="ee254-138">Controleer of de instelling is uitgeschakeld (schakelt ![ uit ](../../media/scc-toggle-off.png) ) en gebruik het vak **verloopt op** om de vervaldatum voor de items op te geven.</span><span class="sxs-lookup"><span data-stu-id="ee254-138">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="ee254-139">of</span><span class="sxs-lookup"><span data-stu-id="ee254-139">or</span></span>

     - <span data-ttu-id="ee254-140">Zet de wisselknop naar rechts om de items zodanig te configureren dat deze nooit verloopt:</span><span class="sxs-lookup"><span data-stu-id="ee254-140">Move the toggle to the right to configure the entries to never expire:</span></span> ![Inschakelen](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="ee254-142">.</span><span class="sxs-lookup"><span data-stu-id="ee254-142">.</span></span>

   - <span data-ttu-id="ee254-143">**Optionele opmerking**: Voer een beschrijvende tekst voor de vermeldingen in.</span><span class="sxs-lookup"><span data-stu-id="ee254-143">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="ee254-144">Wanneer u klaar bent, klikt u op **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="ee254-144">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ee254-145">De beveiligings & voor compliance gebruiken om vermeldingen weer te geven in de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="ee254-145">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="ee254-146">Ga in het beveiligings & compliance naar beleidsregels voor het beleid voor **bedreigings beheer** van de \> **Policy** \> **Tenant**.</span><span class="sxs-lookup"><span data-stu-id="ee254-146">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ee254-147">Selecteer het tabblad **url's** .</span><span class="sxs-lookup"><span data-stu-id="ee254-147">Select the **URLs** tab.</span></span>

<span data-ttu-id="ee254-148">Klik op de volgende kolomkoppen om te sorteren in oplopende of aflopende volgorde:</span><span class="sxs-lookup"><span data-stu-id="ee254-148">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="ee254-149">**Value**</span><span class="sxs-lookup"><span data-stu-id="ee254-149">**Value**</span></span>
- <span data-ttu-id="ee254-150">**Actie**: **blokkeren** of **toestaan**.</span><span class="sxs-lookup"><span data-stu-id="ee254-150">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="ee254-151">**Laatste update datum**</span><span class="sxs-lookup"><span data-stu-id="ee254-151">**Last updated date**</span></span>
- <span data-ttu-id="ee254-152">**Vervaldatum**</span><span class="sxs-lookup"><span data-stu-id="ee254-152">**Expiration date**</span></span>
- <span data-ttu-id="ee254-153">**Ziet**</span><span class="sxs-lookup"><span data-stu-id="ee254-153">**Note**</span></span>

<span data-ttu-id="ee254-154">Klik op **groeperen** om de items te groeperen op **actie** (**blokkeren** of **toestaan**) of **geen**.</span><span class="sxs-lookup"><span data-stu-id="ee254-154">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="ee254-155">Klik op **zoeken**, typ de gehele of gedeeltelijke waarde en druk op ENTER om een bepaalde waarde te zoeken.</span><span class="sxs-lookup"><span data-stu-id="ee254-155">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="ee254-156">Wanneer u klaar bent, klikt u op de knop **Zoek** actie wissen ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="ee254-156">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="ee254-157">Klik op **filter**.</span><span class="sxs-lookup"><span data-stu-id="ee254-157">Click **Filter**.</span></span> <span data-ttu-id="ee254-158">Configureer de volgende instellingen in de **gefilterde** flyout van het filter dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="ee254-158">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="ee254-159">**Actie**: Selecteer **toestaan**, **blokkeren** of beide.</span><span class="sxs-lookup"><span data-stu-id="ee254-159">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="ee254-160">**Verloopt nooit**: selecteren (uitschakelen ![ ](../../media/scc-toggle-off.png) ) of aan ( ![ wisselknop ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ).</span><span class="sxs-lookup"><span data-stu-id="ee254-160">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="ee254-161">**Laatst bijgewerkt**: Selecteer een begindatum (**van**), een einddatum (**en**) of beide.</span><span class="sxs-lookup"><span data-stu-id="ee254-161">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="ee254-162">**Vervaldatum**: Selecteer een begindatum (**van**), een einddatum (**en**) of beide.</span><span class="sxs-lookup"><span data-stu-id="ee254-162">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="ee254-163">Wanneer u klaar bent, klikt u op **toepassen**.</span><span class="sxs-lookup"><span data-stu-id="ee254-163">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="ee254-164">Als u bestaande filters wilt wissen, klikt u op **filter** en klikt u in het **filter** flyout dat wordt weergegeven op **filters wissen**.</span><span class="sxs-lookup"><span data-stu-id="ee254-164">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ee254-165">Met behulp van het compliance-beveiligings & voor het wijzigen van vermeldingen in de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="ee254-165">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ee254-166">U kunt de URL-waarde zelf niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="ee254-166">You can't modify the URL value itself.</span></span> <span data-ttu-id="ee254-167">In plaats daarvan moet u de vermelding verwijderen en opnieuw maken.</span><span class="sxs-lookup"><span data-stu-id="ee254-167">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="ee254-168">Ga in het beveiligings & compliance naar beleidsregels voor het beleid voor **bedreigings beheer** van de \> **Policy** \> **Tenant**.</span><span class="sxs-lookup"><span data-stu-id="ee254-168">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ee254-169">Selecteer het tabblad **url's** .</span><span class="sxs-lookup"><span data-stu-id="ee254-169">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="ee254-170">Selecteer de vermelding die u wilt wijzigen en klik vervolgens op het **Edit** ![ pictogram bewerken bewerken ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="ee254-170">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="ee254-171">Configureer de volgende instellingen in het vervolgmenu dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="ee254-171">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="ee254-172">**Blokkeren/toestaan**: Selecteer **accepteren** of **blokkeren**.</span><span class="sxs-lookup"><span data-stu-id="ee254-172">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="ee254-173">**Verloopt nooit**: Voer een van de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="ee254-173">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="ee254-174">Controleer of de instelling is uitgeschakeld (uitgeschakeld ![ ](../../media/scc-toggle-off.png) ) en gebruik het vak **verloopt op** om de verloopdatum voor de invoer op te geven.</span><span class="sxs-lookup"><span data-stu-id="ee254-174">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="ee254-175">of</span><span class="sxs-lookup"><span data-stu-id="ee254-175">or</span></span>

     - <span data-ttu-id="ee254-176">Schuif de wisselknop naar rechts om het item zo te configureren dat het nooit verloopt:</span><span class="sxs-lookup"><span data-stu-id="ee254-176">Move the toggle to the right to configure the entry to never expire:</span></span> ![Inschakelen](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="ee254-178">.</span><span class="sxs-lookup"><span data-stu-id="ee254-178">.</span></span>

   - <span data-ttu-id="ee254-179">**Optionele opmerking**: Typ een beschrijvende tekst voor de vermelding.</span><span class="sxs-lookup"><span data-stu-id="ee254-179">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="ee254-180">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="ee254-180">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="ee254-181">Met behulp van het compliance-beveiligings & voor het verwijderen van vermeldingen uit de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="ee254-181">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="ee254-182">Ga in het beveiligings & compliance naar beleidsregels voor het beleid voor **bedreigings beheer** van de \> **Policy** \> **Tenant**.</span><span class="sxs-lookup"><span data-stu-id="ee254-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ee254-183">Selecteer het tabblad **url's** .</span><span class="sxs-lookup"><span data-stu-id="ee254-183">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="ee254-184">Selecteer de vermelding die u **wilt verwijderen en klik op** ![ verwijderen ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="ee254-184">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="ee254-185">In het waarschuwingsvenster dat wordt weergegeven, klikt u op **verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="ee254-185">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="ee254-186">PowerShell van Exchange Online of zelfstandige EOP PowerShell gebruiken voor het configureren van de lijst met toegestane/geblokkeerde tenants</span><span class="sxs-lookup"><span data-stu-id="ee254-186">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ee254-187">PowerShell gebruiken om vermeldingen toe te voegen in de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="ee254-187">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ee254-188">Gebruik de volgende syntaxis om vermeldingen toe te voegen aan de lijst Tenant toestaan/blokkeren:</span><span class="sxs-lookup"><span data-stu-id="ee254-188">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="ee254-189">In dit voorbeeld wordt een URL-blok vermelding toegevoegd voor contoso.com en alle subdomeinen (bijvoorbeeld contoso.com, www.contoso.com en xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ee254-189">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="ee254-190">Aangezien we de parameters voor ExpirationDate en verstrijken niet gebruiken, verloopt de invoer na 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="ee254-190">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="ee254-191">Zie [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="ee254-191">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ee254-192">PowerShell gebruiken om vermeldingen weer te geven in de lijst met toegestane/geblokkeerde tenants</span><span class="sxs-lookup"><span data-stu-id="ee254-192">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ee254-193">Als u vermeldingen wilt weergeven in de lijst Tenant toestaan/blokkeren, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="ee254-193">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="ee254-194">In het volgende voorbeeld worden alle geblokkeerde Url's geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="ee254-194">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="ee254-195">Zie [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="ee254-195">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ee254-196">PowerShell gebruiken om vermeldingen te wijzigen in de lijst met toegestane/geblokkeerde tenants</span><span class="sxs-lookup"><span data-stu-id="ee254-196">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ee254-197">U kunt de URL-waarde zelf niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="ee254-197">You can't modify the URL value itself.</span></span> <span data-ttu-id="ee254-198">In plaats daarvan moet u de vermelding verwijderen en opnieuw maken.</span><span class="sxs-lookup"><span data-stu-id="ee254-198">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="ee254-199">Gebruik de volgende syntaxis om vermeldingen te wijzigen in de lijst toestaan/blokkeren van de Tenant:</span><span class="sxs-lookup"><span data-stu-id="ee254-199">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="ee254-200">In dit voorbeeld wordt de vervaldatum van het opgegeven item gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="ee254-200">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="ee254-201">Zie [set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="ee254-201">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="ee254-202">PowerShell gebruiken om vermeldingen te verwijderen uit de lijst toestaan/blokkeren van de Tenant</span><span class="sxs-lookup"><span data-stu-id="ee254-202">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="ee254-203">Gebruik de volgende syntaxis om vermeldingen te verwijderen uit de lijst toestaan/blokkeren van de Tenant:</span><span class="sxs-lookup"><span data-stu-id="ee254-203">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="ee254-204">In dit voorbeeld wordt de opgegeven URL-vermelding uit de lijst toestaan/blok Tenant verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ee254-204">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="ee254-205">Zie [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="ee254-205">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="ee254-206">URL-syntaxis voor de lijst met toegestane/geblokkeerde tenants</span><span class="sxs-lookup"><span data-stu-id="ee254-206">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="ee254-207">IP4v en IPv6-adressen zijn toegestaan, maar de TCP/UDP-poorten zijn niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="ee254-207">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="ee254-208">Bestandsextensies zijn niet toegestaan (bijvoorbeeld test.pdf).</span><span class="sxs-lookup"><span data-stu-id="ee254-208">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="ee254-209">Unicode wordt niet ondersteund, maar punycode is.</span><span class="sxs-lookup"><span data-stu-id="ee254-209">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="ee254-210">Hostnamen zijn toegestaan als alle volgende instructies waar zijn:</span><span class="sxs-lookup"><span data-stu-id="ee254-210">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="ee254-211">De hostname bevat een punt.</span><span class="sxs-lookup"><span data-stu-id="ee254-211">The hostname contains a period.</span></span>
  - <span data-ttu-id="ee254-212">Het teken links van de periode moet minimaal één teken bevatten.</span><span class="sxs-lookup"><span data-stu-id="ee254-212">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="ee254-213">Rechts van de periode bestaan minimaal twee tekens.</span><span class="sxs-lookup"><span data-stu-id="ee254-213">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="ee254-214">Dit is bijvoorbeeld `t.co` toegestaan; `.com` of `contoso.` niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="ee254-214">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="ee254-215">Subpaden zijn niet impliciet.</span><span class="sxs-lookup"><span data-stu-id="ee254-215">Subpaths are not implied.</span></span>

  <span data-ttu-id="ee254-216">Dit is bijvoorbeeld `contoso.com` niet inbegrepen `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="ee254-216">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="ee254-217">Jokertekens (\*) zijn toegestaan in de volgende scenario's:</span><span class="sxs-lookup"><span data-stu-id="ee254-217">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="ee254-218">Een sterretje links moet worden gevolgd door een punt voor het opgeven van een subdomein.</span><span class="sxs-lookup"><span data-stu-id="ee254-218">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="ee254-219">`*.contoso.com`Is bijvoorbeeld toegestaan; mag `*contoso.com` niet worden toegestaan.</span><span class="sxs-lookup"><span data-stu-id="ee254-219">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="ee254-220">Een jokerteken voor rechts moet de volgende schuine streep (/) volgen om een pad op te geven.</span><span class="sxs-lookup"><span data-stu-id="ee254-220">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="ee254-221">Dit is bijvoorbeeld `contoso.com/*` toegestaan; `contoso.com*` of `contoso.com/ab*` niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="ee254-221">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="ee254-222">Alle subpaden zijn niet impliciet door een juiste jokerteken.</span><span class="sxs-lookup"><span data-stu-id="ee254-222">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="ee254-223">Dit is bijvoorbeeld `contoso.com/*` niet inbegrepen `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="ee254-223">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="ee254-224">`*.com*` is ongeldig (geen oplosbaar domein en de juiste jokertekens volgen geen schuine streep naar rechts).</span><span class="sxs-lookup"><span data-stu-id="ee254-224">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="ee254-225">Jokertekens zijn niet toegestaan in IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="ee254-225">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="ee254-226">Het tilde (~) is beschikbaar in de volgende scenario's:</span><span class="sxs-lookup"><span data-stu-id="ee254-226">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="ee254-227">Een wegge tilde houdt een domein en alle subdomeinen in.</span><span class="sxs-lookup"><span data-stu-id="ee254-227">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="ee254-228">Bijvoorbeeld `~contoso.com` bevat `contoso.com` en `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="ee254-228">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="ee254-229">URL-vermeldingen die protocollen bevatten (bijvoorbeeld, `http://` `https://` of `ftp://` ), mislukken omdat URL-vermeldingen op alle protocollen van toepassing zijn.</span><span class="sxs-lookup"><span data-stu-id="ee254-229">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="ee254-230">Een gebruikersnaam of wachtwoord wordt niet ondersteund of vereist.</span><span class="sxs-lookup"><span data-stu-id="ee254-230">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="ee254-231">Aanhalingstekens (' of ') zijn ongeldige tekens.</span><span class="sxs-lookup"><span data-stu-id="ee254-231">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="ee254-232">Een URL moet alle redirecties bevatten, waar mogelijk.</span><span class="sxs-lookup"><span data-stu-id="ee254-232">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="ee254-233">Scenario's voor URL-invoer</span><span class="sxs-lookup"><span data-stu-id="ee254-233">URL entry scenarios</span></span>

<span data-ttu-id="ee254-234">Geldige URL-vermeldingen en de bijbehorende resultaten worden beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="ee254-234">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="ee254-235">Scenario: geen jokertekens</span><span class="sxs-lookup"><span data-stu-id="ee254-235">Scenario: No wildcards</span></span>

<span data-ttu-id="ee254-236">**Invoer**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="ee254-236">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="ee254-237">**Overeenkomst toestaan**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee254-237">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="ee254-238">Mag **niet worden vergeleken**:</span><span class="sxs-lookup"><span data-stu-id="ee254-238">**Allow not matched**:</span></span>

  - <span data-ttu-id="ee254-239">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee254-239">abc-contoso.com</span></span>
  - <span data-ttu-id="ee254-240">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ee254-240">contoso.com/a</span></span>
  - <span data-ttu-id="ee254-241">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee254-241">payroll.contoso.com</span></span>
  - <span data-ttu-id="ee254-242">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee254-242">test.com/contoso.com</span></span>
  - <span data-ttu-id="ee254-243">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee254-243">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="ee254-244">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee254-244">www.contoso.com</span></span>
  - <span data-ttu-id="ee254-245">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="ee254-245">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="ee254-246">**Blok treffer**:</span><span class="sxs-lookup"><span data-stu-id="ee254-246">**Block match**:</span></span>

  - <span data-ttu-id="ee254-247">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee254-247">contoso.com</span></span>
  - <span data-ttu-id="ee254-248">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ee254-248">contoso.com/a</span></span>
  - <span data-ttu-id="ee254-249">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee254-249">payroll.contoso.com</span></span>
  - <span data-ttu-id="ee254-250">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee254-250">test.com/contoso.com</span></span>
  - <span data-ttu-id="ee254-251">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee254-251">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="ee254-252">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee254-252">www.contoso.com</span></span>
  - <span data-ttu-id="ee254-253">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="ee254-253">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="ee254-254">**Blok niet-gerelateerde** waarde: ABC-contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee254-254">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="ee254-255">Scenario: links jokerteken (subdomein)</span><span class="sxs-lookup"><span data-stu-id="ee254-255">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="ee254-256">**Invoer**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="ee254-256">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="ee254-257">Overeenkomst toestaan en **blokkeren** **toestaan** :</span><span class="sxs-lookup"><span data-stu-id="ee254-257">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ee254-258">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee254-258">www.contoso.com</span></span>
  - <span data-ttu-id="ee254-259">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee254-259">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="ee254-260">**Niet-gematchte** en **geblokkeerde blokkeren**:</span><span class="sxs-lookup"><span data-stu-id="ee254-260">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ee254-261">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee254-261">123contoso.com</span></span>
  - <span data-ttu-id="ee254-262">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee254-262">contoso.com</span></span>
  - <span data-ttu-id="ee254-263">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee254-263">test.com/contoso.com</span></span>
  - <span data-ttu-id="ee254-264">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="ee254-264">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="ee254-265">Scenario: rechts jokerteken boven aan het pad</span><span class="sxs-lookup"><span data-stu-id="ee254-265">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="ee254-266">**Invoer**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="ee254-266">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="ee254-267">Overeenkomst toestaan en **blokkeren** **toestaan** :</span><span class="sxs-lookup"><span data-stu-id="ee254-267">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ee254-268">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="ee254-268">contoso.com/a/b</span></span>
  - <span data-ttu-id="ee254-269">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="ee254-269">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="ee254-270">contoso. com/a/? q = joe@t. com</span><span class="sxs-lookup"><span data-stu-id="ee254-270">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="ee254-271">**Niet-gematchte** en **geblokkeerde blokkeren**:</span><span class="sxs-lookup"><span data-stu-id="ee254-271">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ee254-272">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee254-272">contoso.com</span></span>
  - <span data-ttu-id="ee254-273">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ee254-273">contoso.com/a</span></span>
  - <span data-ttu-id="ee254-274">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee254-274">www.contoso.com</span></span>
  - <span data-ttu-id="ee254-275">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="ee254-275">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="ee254-276">Scenario: de tilde links</span><span class="sxs-lookup"><span data-stu-id="ee254-276">Scenario: Left tilde</span></span>

<span data-ttu-id="ee254-277">**Invoer**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="ee254-277">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="ee254-278">Overeenkomst toestaan en **blokkeren** **toestaan** :</span><span class="sxs-lookup"><span data-stu-id="ee254-278">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ee254-279">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee254-279">contoso.com</span></span>
  - <span data-ttu-id="ee254-280">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee254-280">www.contoso.com</span></span>
  - <span data-ttu-id="ee254-281">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee254-281">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="ee254-282">**Niet-gematchte** en **geblokkeerde blokkeren**:</span><span class="sxs-lookup"><span data-stu-id="ee254-282">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ee254-283">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee254-283">123contoso.com</span></span>
  - <span data-ttu-id="ee254-284">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="ee254-284">contoso.com/abc</span></span>
  - <span data-ttu-id="ee254-285">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="ee254-285">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="ee254-286">Scenario: achtervoegsel van jokerteken</span><span class="sxs-lookup"><span data-stu-id="ee254-286">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="ee254-287">**Invoer**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="ee254-287">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="ee254-288">Overeenkomst toestaan en **blokkeren** **toestaan** :</span><span class="sxs-lookup"><span data-stu-id="ee254-288">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ee254-289">contoso. com/? q = whatever@fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="ee254-289">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="ee254-290">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ee254-290">contoso.com/a</span></span>
  - <span data-ttu-id="ee254-291">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="ee254-291">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="ee254-292">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="ee254-292">contoso.com/ab</span></span>
  - <span data-ttu-id="ee254-293">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="ee254-293">contoso.com/b</span></span>
  - <span data-ttu-id="ee254-294">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="ee254-294">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="ee254-295">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="ee254-295">contoso.com/ba</span></span>

- <span data-ttu-id="ee254-296">**Niet-afgestemde** en niet- **gematchte blokkeren** toestaan: contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee254-296">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="ee254-297">Scenario: het subdomein met jokertekens en het achtervoegsel rechts</span><span class="sxs-lookup"><span data-stu-id="ee254-297">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="ee254-298">**Invoer**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="ee254-298">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="ee254-299">Overeenkomst toestaan en **blokkeren** **toestaan** :</span><span class="sxs-lookup"><span data-stu-id="ee254-299">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ee254-300">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="ee254-300">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="ee254-301">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="ee254-301">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="ee254-302">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ee254-302">www.contoso.com/a</span></span>
  - <span data-ttu-id="ee254-303">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="ee254-303">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="ee254-304">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="ee254-304">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="ee254-305">**Niet-afgestemde** en niet- **gematchte blokkeren** toestaan: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="ee254-305">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="ee254-306">Scenario: linker-en rechter tilde</span><span class="sxs-lookup"><span data-stu-id="ee254-306">Scenario: Left and right tilde</span></span>

<span data-ttu-id="ee254-307">**Invoer**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="ee254-307">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="ee254-308">Overeenkomst toestaan en **blokkeren** **toestaan** :</span><span class="sxs-lookup"><span data-stu-id="ee254-308">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ee254-309">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee254-309">contoso.com</span></span>
  - <span data-ttu-id="ee254-310">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ee254-310">contoso.com/a</span></span>
  - <span data-ttu-id="ee254-311">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee254-311">www.contoso.com</span></span>
  - <span data-ttu-id="ee254-312">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="ee254-312">www.contoso.com/b</span></span>
  - <span data-ttu-id="ee254-313">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee254-313">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="ee254-314">**Niet-gematchte** en **geblokkeerde blokkeren**:</span><span class="sxs-lookup"><span data-stu-id="ee254-314">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ee254-315">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee254-315">123contoso.com</span></span>
  - <span data-ttu-id="ee254-316">contoso.org</span><span class="sxs-lookup"><span data-stu-id="ee254-316">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="ee254-317">Scenario: IP-adres</span><span class="sxs-lookup"><span data-stu-id="ee254-317">Scenario: IP address</span></span>

<span data-ttu-id="ee254-318">**Invoer**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="ee254-318">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="ee254-319">**Overeenkomst toestaan** en **blokkeren** toestaan: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="ee254-319">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="ee254-320">**Niet-gematchte** en **geblokkeerde blokkeren**:</span><span class="sxs-lookup"><span data-stu-id="ee254-320">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ee254-321">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="ee254-321">1.2.3.4/a</span></span>
  - <span data-ttu-id="ee254-322">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="ee254-322">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="ee254-323">IP-adres met jokerteken rechts</span><span class="sxs-lookup"><span data-stu-id="ee254-323">IP address with right wildcard</span></span>

<span data-ttu-id="ee254-324">**Invoer**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="ee254-324">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="ee254-325">Overeenkomst toestaan en **blokkeren** **toestaan** :</span><span class="sxs-lookup"><span data-stu-id="ee254-325">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ee254-326">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="ee254-326">1.2.3.4/b</span></span>
  - <span data-ttu-id="ee254-327">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="ee254-327">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="ee254-328">Voorbeelden van ongeldige vermeldingen</span><span class="sxs-lookup"><span data-stu-id="ee254-328">Examples of invalid entries</span></span>

<span data-ttu-id="ee254-329">De volgende vermeldingen zijn ongeldig:</span><span class="sxs-lookup"><span data-stu-id="ee254-329">The following entries are invalid:</span></span>

- <span data-ttu-id="ee254-330">**Ontbrekende of ongeldige domein waarden**:</span><span class="sxs-lookup"><span data-stu-id="ee254-330">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="ee254-331">uitgeverij</span><span class="sxs-lookup"><span data-stu-id="ee254-331">contoso</span></span>
  - <span data-ttu-id="ee254-332">\*uitgeverij.\*</span><span class="sxs-lookup"><span data-stu-id="ee254-332">\*.contoso.\*</span></span>
  - <span data-ttu-id="ee254-333">\*. com</span><span class="sxs-lookup"><span data-stu-id="ee254-333">\*.com</span></span>
  - <span data-ttu-id="ee254-334">\*. PDF</span><span class="sxs-lookup"><span data-stu-id="ee254-334">\*.pdf</span></span>

- <span data-ttu-id="ee254-335">**Jokertekens voor tekst of zonder spaties**:</span><span class="sxs-lookup"><span data-stu-id="ee254-335">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="ee254-336">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee254-336">\*contoso.com</span></span>
  - <span data-ttu-id="ee254-337">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="ee254-337">contoso.com\*</span></span>
  - <span data-ttu-id="ee254-338">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="ee254-338">\*1.2.3.4</span></span>
  - <span data-ttu-id="ee254-339">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="ee254-339">1.2.3.4\*</span></span>
  - <span data-ttu-id="ee254-340">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="ee254-340">contoso.com/a\*</span></span>
  - <span data-ttu-id="ee254-341">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="ee254-341">contoso.com/ab\*</span></span>

- <span data-ttu-id="ee254-342">**IP-adressen met poorten**:</span><span class="sxs-lookup"><span data-stu-id="ee254-342">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="ee254-343">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="ee254-343">contoso.com:443</span></span>
  - <span data-ttu-id="ee254-344">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="ee254-344">abc.contoso.com:25</span></span>

- <span data-ttu-id="ee254-345">**Niet-beschrijvende jokertekens**:</span><span class="sxs-lookup"><span data-stu-id="ee254-345">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="ee254-346">\*.\*</span><span class="sxs-lookup"><span data-stu-id="ee254-346">\*.\*</span></span>

- <span data-ttu-id="ee254-347">**Jokertekens** voor het midden:</span><span class="sxs-lookup"><span data-stu-id="ee254-347">**Middle wildcards**:</span></span>

  - <span data-ttu-id="ee254-348">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="ee254-348">conto\*so.com</span></span>
  - <span data-ttu-id="ee254-349">rel. com</span><span class="sxs-lookup"><span data-stu-id="ee254-349">conto~so.com</span></span>

- <span data-ttu-id="ee254-350">**Dubbele jokertekens**</span><span class="sxs-lookup"><span data-stu-id="ee254-350">**Double wildcards**</span></span>

  - <span data-ttu-id="ee254-351">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="ee254-351">contoso.com/\*\*</span></span>
  - <span data-ttu-id="ee254-352">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="ee254-352">contoso.com/\*/\*</span></span>
