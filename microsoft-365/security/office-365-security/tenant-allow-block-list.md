---
title: Uw toegestane en geblokkeerde blokken beheren in de lijst Toestaan/blokkeren van tenant
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
description: Beheerders kunnen informatie krijgen over het configureren van toestaan en blokkeren in de lijst Tenant toestaan/blokkeren in de beveiligingsportal.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 103ddc9aa0858f9203582ac07a655fd7f5506cf3
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587585"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="94c46-103">Tenant Toestaan/Blokkeren-lijst beheren</span><span class="sxs-lookup"><span data-stu-id="94c46-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="94c46-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="94c46-104">**Applies to**</span></span>
- [<span data-ttu-id="94c46-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="94c46-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="94c46-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="94c46-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="94c46-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="94c46-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="94c46-108">U kunt op dit **moment geen toegestane** items configureren in de lijst Tenant toestaan/blokkeren.</span><span class="sxs-lookup"><span data-stu-id="94c46-108">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="94c46-109">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken, bent u het mogelijk niet eens met de uitspraak over EOP-filtering.</span><span class="sxs-lookup"><span data-stu-id="94c46-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="94c46-110">Een goed bericht kan bijvoorbeeld worden gemarkeerd als slecht (een onwaar positief) of een slecht bericht kan worden toegestaan (een onwaar negatief).</span><span class="sxs-lookup"><span data-stu-id="94c46-110">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="94c46-111">Met de tenantlijst Toestaan/blokkeren in het Beveiligings- & Compliancecentrum kunt u handmatig de filterinspraken van Microsoft 365 overschrijven.</span><span class="sxs-lookup"><span data-stu-id="94c46-111">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="94c46-112">De lijst Tenant toestaan/blokkeren wordt gebruikt tijdens de e-mailstroom en op het moment dat de gebruiker klikt.</span><span class="sxs-lookup"><span data-stu-id="94c46-112">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="94c46-113">U kunt URL's of bestanden opgeven die u altijd wilt blokkeren.</span><span class="sxs-lookup"><span data-stu-id="94c46-113">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="94c46-114">In dit artikel wordt beschreven hoe u vermeldingen configureert in de lijst Tenant toestaan/blokkeren in het beveiligings- & compliancecentrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).</span><span class="sxs-lookup"><span data-stu-id="94c46-114">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="94c46-115">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="94c46-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="94c46-116">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="94c46-116">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="94c46-117">Als u rechtstreeks naar de **pagina Lijst met tenants toestaan/blokkeren wilt** gaan, gebruikt u <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="94c46-117">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="94c46-118">U geeft bestanden op met de hashwaarde SHA256 van het bestand.</span><span class="sxs-lookup"><span data-stu-id="94c46-118">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="94c46-119">Als u de hashwaarde SHA256 van een bestand in Windows wilt zoeken, voer u de volgende opdracht uit in een opdrachtprompt:</span><span class="sxs-lookup"><span data-stu-id="94c46-119">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="94c46-120">Een voorbeeldwaarde is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="94c46-120">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="94c46-121">Perceptuele hashwaarden (pHash) worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="94c46-121">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="94c46-122">De beschikbare URL-waarden worden beschreven in de syntaxis van de URL voor de sectie Lijst met tenants [toestaan/blokkeren](#url-syntax-for-the-tenant-allowblock-list) verderop in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="94c46-122">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="94c46-123">De lijst Tenant toestaan/blokkeren staat maximaal 500 vermeldingen voor URL's en 500 vermeldingen voor bestandshashes toe.</span><span class="sxs-lookup"><span data-stu-id="94c46-123">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="94c46-124">Het maximum aantal tekens voor elke vermelding is:</span><span class="sxs-lookup"><span data-stu-id="94c46-124">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="94c46-125">Bestandshashes = 64</span><span class="sxs-lookup"><span data-stu-id="94c46-125">File hashes = 64</span></span>
  - <span data-ttu-id="94c46-126">URL = 250</span><span class="sxs-lookup"><span data-stu-id="94c46-126">URL = 250</span></span>

- <span data-ttu-id="94c46-127">Een item moet binnen 30 minuten actief zijn.</span><span class="sxs-lookup"><span data-stu-id="94c46-127">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="94c46-128">Standaard verlopen vermeldingen in de lijst Tenant toestaan/blokkeren na 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="94c46-128">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="94c46-129">U kunt een datum opgeven of instellen dat deze nooit verloopt.</span><span class="sxs-lookup"><span data-stu-id="94c46-129">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="94c46-130">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="94c46-130">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="94c46-131">Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="94c46-131">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="94c46-132">U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="94c46-132">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="94c46-133">Als u waarden wilt toevoegen en verwijderen uit de lijst Tenant toestaan/blokkeren, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="94c46-133">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="94c46-134">Voor alleen-lezen toegang tot de tenantlijst toestaan/blokkeren moet  u lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="94c46-134">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="94c46-135">Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="94c46-135">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="94c46-136">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="94c46-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="94c46-137">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="94c46-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  > - <span data-ttu-id="94c46-138">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="94c46-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="94c46-139">Gebruik het beveiligings- & compliancecentrum om URL-vermeldingen te maken in de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="94c46-139">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="94c46-140">Zie de syntaxis van de URL voor de sectie Lijst met tenants [toestaan/blokkeren](#url-syntax-for-the-tenant-allowblock-list) verderop in dit artikel voor meer informatie over de syntaxis van URL-vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="94c46-140">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="94c46-141">Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="94c46-141">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="94c46-142">Controleer op de pagina Lijst met **tenants toestaan/blokkeren** of het tabblad **URL's** is geselecteerd en klik vervolgens op **Blokkeren**</span><span class="sxs-lookup"><span data-stu-id="94c46-142">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="94c46-143">Configureer **de volgende** instellingen in het flyout URL's blokkeren dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="94c46-143">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="94c46-144">**URL's toevoegen om te blokkeren:** Voer één URL per regel in, maximaal 20.</span><span class="sxs-lookup"><span data-stu-id="94c46-144">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="94c46-145">**Nooit verlopen:** Ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="94c46-145">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="94c46-146">Controleer of de instelling is uitgeschakeld (schakel uit) en gebruik het vak Verloopt aan om de vervaldatum voor de ![ ](../../media/scc-toggle-off.png) vermeldingen op te geven. </span><span class="sxs-lookup"><span data-stu-id="94c46-146">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="94c46-147">of</span><span class="sxs-lookup"><span data-stu-id="94c46-147">or</span></span>

     - <span data-ttu-id="94c46-148">Verplaats de schakelknop naar rechts om de items zo te configureren dat ze nooit verlopen:</span><span class="sxs-lookup"><span data-stu-id="94c46-148">Move the toggle to the right to configure the entries to never expire:</span></span> ![Inschakelen](../../media/scc-toggle-on.png)<span data-ttu-id="94c46-150">.</span><span class="sxs-lookup"><span data-stu-id="94c46-150">.</span></span>

   - <span data-ttu-id="94c46-151">**Optionele opmerking:** Voer beschrijvende tekst in voor de vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="94c46-151">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="94c46-152">Wanneer u klaar bent, klikt u op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="94c46-152">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="94c46-153">Gebruik het beveiligings- & compliancecentrum om bestandsgegevens te maken in de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="94c46-153">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="94c46-154">Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="94c46-154">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="94c46-155">Selecteer op de pagina Lijst met **tenants toestaan/blokkeren** de optie **Tabblad** Bestanden en klik vervolgens op **Blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="94c46-155">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="94c46-156">Configureer **de volgende instellingen in het flyout** add files to block flyout that appears:</span><span class="sxs-lookup"><span data-stu-id="94c46-156">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="94c46-157">**Bestandshashes toevoegen:** Voer één SHA256-hashwaarde per regel in, maximaal 20.</span><span class="sxs-lookup"><span data-stu-id="94c46-157">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="94c46-158">**Nooit verlopen:** Ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="94c46-158">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="94c46-159">Controleer of de instelling is uitgeschakeld (schakel uit) en gebruik het vak Verloopt aan om de vervaldatum voor de ![ ](../../media/scc-toggle-off.png) vermeldingen op te geven. </span><span class="sxs-lookup"><span data-stu-id="94c46-159">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="94c46-160">of</span><span class="sxs-lookup"><span data-stu-id="94c46-160">or</span></span>

     - <span data-ttu-id="94c46-161">Verplaats de schakelknop naar rechts om de items zo te configureren dat ze nooit verlopen:</span><span class="sxs-lookup"><span data-stu-id="94c46-161">Move the toggle to the right to configure the entries to never expire:</span></span> ![Inschakelen](../../media/scc-toggle-on.png)<span data-ttu-id="94c46-163">.</span><span class="sxs-lookup"><span data-stu-id="94c46-163">.</span></span>

   - <span data-ttu-id="94c46-164">**Optionele opmerking:** Voer beschrijvende tekst in voor de vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="94c46-164">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="94c46-165">Wanneer u klaar bent, klikt u op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="94c46-165">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="94c46-166">Het beveiligings- & compliancecentrum gebruiken om items in de lijst Tenant toestaan/blokkeren weer te geven</span><span class="sxs-lookup"><span data-stu-id="94c46-166">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="94c46-167">Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="94c46-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="94c46-168">Selecteer het **tabblad URL's** of het **tabblad** Bestanden.</span><span class="sxs-lookup"><span data-stu-id="94c46-168">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="94c46-169">Klik op de volgende kolomkoppen om in oplopende of aflopende volgorde te sorteren:</span><span class="sxs-lookup"><span data-stu-id="94c46-169">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="94c46-170">**Waarde:** De URL of de bestandshash.</span><span class="sxs-lookup"><span data-stu-id="94c46-170">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="94c46-171">**Laatst bijgewerkte datum**</span><span class="sxs-lookup"><span data-stu-id="94c46-171">**Last updated date**</span></span>
- <span data-ttu-id="94c46-172">**Vervaldatum**</span><span class="sxs-lookup"><span data-stu-id="94c46-172">**Expiration date**</span></span>
- <span data-ttu-id="94c46-173">**Opmerking**</span><span class="sxs-lookup"><span data-stu-id="94c46-173">**Note**</span></span>

<span data-ttu-id="94c46-174">Klik **op Zoeken,** voer een hele of een deel van een waarde in en druk vervolgens op Enter om een specifieke waarde te zoeken.</span><span class="sxs-lookup"><span data-stu-id="94c46-174">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="94c46-175">Wanneer u klaar bent, klikt u op **Zoek verwijderen Zoekpictogram** ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) verwijderen.</span><span class="sxs-lookup"><span data-stu-id="94c46-175">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="94c46-176">Klik **op Filteren.**</span><span class="sxs-lookup"><span data-stu-id="94c46-176">Click **Filter**.</span></span> <span data-ttu-id="94c46-177">Configureer **een van** de volgende instellingen in het flyout Filter dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="94c46-177">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="94c46-178">**Nooit verlopen:** Uit- of ![ ](../../media/scc-toggle-off.png) uitschakelen: ![ In- of uitschakelen: In- of ](../../media/scc-toggle-on.png) uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="94c46-178">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="94c46-179">**Laatst bijgewerkt:** Selecteer een begindatum **(Van),** een einddatum **(Aan)** of beide.</span><span class="sxs-lookup"><span data-stu-id="94c46-179">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="94c46-180">**Vervaldatum:** Selecteer een begindatum (**Van**), een einddatum (**Aan**) of beide.</span><span class="sxs-lookup"><span data-stu-id="94c46-180">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="94c46-181">Wanneer u klaar bent, klikt u op **Toepassen.**</span><span class="sxs-lookup"><span data-stu-id="94c46-181">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="94c46-182">Als u bestaande filters wilt wissen, klikt u **op Filter** en klikt u in het **fly-out** Filter dat wordt weergegeven op Filters **wissen.**</span><span class="sxs-lookup"><span data-stu-id="94c46-182">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="94c46-183">Gebruik het beveiligings- & compliancecentrum om blokinzendingen in de lijst Tenant toestaan/blokkeren te wijzigen</span><span class="sxs-lookup"><span data-stu-id="94c46-183">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="94c46-184">U kunt de bestaande geblokkeerde URL of bestandswaarden in een item niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="94c46-184">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="94c46-185">Als u deze waarden wilt wijzigen, moet u de vermelding verwijderen en opnieuw maken.</span><span class="sxs-lookup"><span data-stu-id="94c46-185">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="94c46-186">Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="94c46-186">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="94c46-187">Selecteer het **tabblad URL's** of het **tabblad** Bestanden.</span><span class="sxs-lookup"><span data-stu-id="94c46-187">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="94c46-188">Selecteer de blokinvoer die u wilt wijzigen en klik vervolgens op **Pictogram** ![ Bewerken ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) bewerken.</span><span class="sxs-lookup"><span data-stu-id="94c46-188">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="94c46-189">Configureer de volgende instellingen in het flyout dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="94c46-189">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="94c46-190">**Nooit verlopen:** Ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="94c46-190">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="94c46-191">Controleer of de instelling is uitgeschakeld (schakelknop uit) en gebruik het vak Verloopt op om de vervaldatum voor ![ de vermelding op te ](../../media/scc-toggle-off.png) geven. </span><span class="sxs-lookup"><span data-stu-id="94c46-191">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

       <span data-ttu-id="94c46-192">of</span><span class="sxs-lookup"><span data-stu-id="94c46-192">or</span></span>

     - <span data-ttu-id="94c46-193">Verplaats de schakelknop naar rechts om de vermelding zo te configureren dat deze nooit verloopt:</span><span class="sxs-lookup"><span data-stu-id="94c46-193">Move the toggle to the right to configure the entry to never expire:</span></span> ![Inschakelen](../../media/scc-toggle-on.png)<span data-ttu-id="94c46-195">.</span><span class="sxs-lookup"><span data-stu-id="94c46-195">.</span></span>

   - <span data-ttu-id="94c46-196">**Optionele opmerking:** Voer beschrijvende tekst in voor de vermelding.</span><span class="sxs-lookup"><span data-stu-id="94c46-196">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="94c46-197">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="94c46-197">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="94c46-198">Het beveiligings- & compliancecentrum gebruiken om blokinzendingen uit de lijst Met tenant toestaan/blokkeren te verwijderen</span><span class="sxs-lookup"><span data-stu-id="94c46-198">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="94c46-199">Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="94c46-199">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="94c46-200">Selecteer het **tabblad URL's** of het **tabblad** Bestanden.</span><span class="sxs-lookup"><span data-stu-id="94c46-200">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="94c46-201">Selecteer de blokinvoer die u wilt verwijderen en klik vervolgens op **Pictogram** ![ Verwijderen ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) verwijderen.</span><span class="sxs-lookup"><span data-stu-id="94c46-201">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="94c46-202">Klik in het waarschuwingsvenster dat wordt weergegeven op **Verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="94c46-202">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="94c46-203">Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken om de tenantlijst toestaan/blokkeren te configureren</span><span class="sxs-lookup"><span data-stu-id="94c46-203">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="94c46-204">PowerShell gebruiken om blokgegevens toe te voegen aan de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="94c46-204">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="94c46-205">Gebruik de volgende syntaxis om blokgegevens toe te voegen in de lijst Tenant Allow/Block:</span><span class="sxs-lookup"><span data-stu-id="94c46-205">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="94c46-206">In dit voorbeeld wordt een blok-URL-vermelding voor contoso.com en alle subdomeinen (bijvoorbeeld contoso.com, www.contoso.com en xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="94c46-206">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="94c46-207">Omdat we de parameters Vervaldatum of NoExpiration niet hebben gebruikt, verloopt de vermelding na 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="94c46-207">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="94c46-208">In dit voorbeeld wordt een blokbestandsinvoer toegevoegd voor de opgegeven bestanden die nooit verlopen.</span><span class="sxs-lookup"><span data-stu-id="94c46-208">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="94c46-209">Zie [New-TenantAllowBlockListItems voor](/powershell/module/exchange/new-tenantallowblocklistitems)gedetailleerde syntaxis en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="94c46-209">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="94c46-210">PowerShell gebruiken om items in de lijst Tenant toestaan/blokkeren weer te geven</span><span class="sxs-lookup"><span data-stu-id="94c46-210">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="94c46-211">Gebruik de volgende syntaxis om vermeldingen in de lijst Tenant toestaan/blokkeren weer te geven:</span><span class="sxs-lookup"><span data-stu-id="94c46-211">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="94c46-212">In dit voorbeeld worden alle geblokkeerde URL's als retourneert.</span><span class="sxs-lookup"><span data-stu-id="94c46-212">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="94c46-213">In dit voorbeeld worden gegevens voor de opgegeven waarde voor bestandshash als resultaat gegeven.</span><span class="sxs-lookup"><span data-stu-id="94c46-213">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="94c46-214">Zie [Get-TenantAllowBlockListItems voor](/powershell/module/exchange/get-tenantallowblocklistitems)gedetailleerde syntaxis en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="94c46-214">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="94c46-215">PowerShell gebruiken om blokgegevens in de lijst Tenant toestaan/blokkeren te wijzigen</span><span class="sxs-lookup"><span data-stu-id="94c46-215">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="94c46-216">U kunt de bestaande URL- of bestandswaarden in een blokinvoer niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="94c46-216">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="94c46-217">Als u deze waarden wilt wijzigen, moet u de vermelding verwijderen en opnieuw maken.</span><span class="sxs-lookup"><span data-stu-id="94c46-217">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="94c46-218">Gebruik de volgende syntaxis om blokgegevens in de lijst Tenant toestaan/blokkeren te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="94c46-218">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="94c46-219">In dit voorbeeld wordt de vervaldatum van de opgegeven blokinvoer gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="94c46-219">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="94c46-220">Zie [Set-TenantAllowBlockListItems (Set-TenantAllowBlockListItems)](/powershell/module/exchange/set-tenantallowblocklistitems)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="94c46-220">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="94c46-221">PowerShell gebruiken om blokgegevens te verwijderen uit de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="94c46-221">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="94c46-222">Als u blokinzendingen wilt verwijderen uit de lijst Tenant toestaan/blokkeren, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="94c46-222">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="94c46-223">In dit voorbeeld wordt de opgegeven blok-URL-vermelding verwijderd uit de lijst Tenant toestaan/blokkeren.</span><span class="sxs-lookup"><span data-stu-id="94c46-223">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="94c46-224">Zie [Remove-TenantAllowBlockListItems (Verwijderen-TenantAllowBlockListItems)](/powershell/module/exchange/remove-tenantallowblocklistitems)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="94c46-224">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="94c46-225">URL-syntaxis voor de lijst Toestaan/blokkeren van tenant</span><span class="sxs-lookup"><span data-stu-id="94c46-225">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="94c46-226">IP4v- en IPv6-adressen zijn toegestaan, maar TCP/UDP-poorten niet.</span><span class="sxs-lookup"><span data-stu-id="94c46-226">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="94c46-227">Bestandsnaamextensies zijn niet toegestaan (bijvoorbeeld test.pdf).</span><span class="sxs-lookup"><span data-stu-id="94c46-227">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="94c46-228">Unicode wordt niet ondersteund, maar Punycode wel.</span><span class="sxs-lookup"><span data-stu-id="94c46-228">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="94c46-229">Hostnamen zijn toegestaan als alle volgende instructies waar zijn:</span><span class="sxs-lookup"><span data-stu-id="94c46-229">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="94c46-230">De hostnaam bevat een punt.</span><span class="sxs-lookup"><span data-stu-id="94c46-230">The hostname contains a period.</span></span>
  - <span data-ttu-id="94c46-231">Er is ten minste één teken links van de periode.</span><span class="sxs-lookup"><span data-stu-id="94c46-231">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="94c46-232">Er zijn ten minste twee tekens rechts van de periode.</span><span class="sxs-lookup"><span data-stu-id="94c46-232">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="94c46-233">Is bijvoorbeeld `t.co` toegestaan of `.com` niet `contoso.` toegestaan.</span><span class="sxs-lookup"><span data-stu-id="94c46-233">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="94c46-234">Subpathen worden niet geïmpliceerd.</span><span class="sxs-lookup"><span data-stu-id="94c46-234">Subpaths are not implied.</span></span>

  <span data-ttu-id="94c46-235">Bevat bijvoorbeeld `contoso.com` geen `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="94c46-235">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="94c46-236">Jokertekens (\*) zijn toegestaan in de volgende scenario's:</span><span class="sxs-lookup"><span data-stu-id="94c46-236">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="94c46-237">Een linker jokerteken moet worden gevolgd door een punt om een subdomein op te geven.</span><span class="sxs-lookup"><span data-stu-id="94c46-237">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="94c46-238">Is bijvoorbeeld `*.contoso.com` toegestaan; `*contoso.com` is niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="94c46-238">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="94c46-239">Een jokerteken rechts moet een slash (/) volgen om een pad op te geven.</span><span class="sxs-lookup"><span data-stu-id="94c46-239">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="94c46-240">Is bijvoorbeeld `contoso.com/*` toegestaan of `contoso.com*` niet `contoso.com/ab*` toegestaan.</span><span class="sxs-lookup"><span data-stu-id="94c46-240">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="94c46-241">Alle subpathen worden niet geïmpliceerd door een rechter jokerteken.</span><span class="sxs-lookup"><span data-stu-id="94c46-241">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="94c46-242">Bevat bijvoorbeeld `contoso.com/*` geen `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="94c46-242">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="94c46-243">`*.com*` ongeldig is (geen op te lossen domein en het jokerteken rechts volgt geen slash voor vooruit).</span><span class="sxs-lookup"><span data-stu-id="94c46-243">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="94c46-244">Jokertekens zijn niet toegestaan in IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="94c46-244">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="94c46-245">Het tildeteken (~) is beschikbaar in de volgende scenario's:</span><span class="sxs-lookup"><span data-stu-id="94c46-245">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="94c46-246">Een linker tilde houdt een domein en alle subdomeinen in.</span><span class="sxs-lookup"><span data-stu-id="94c46-246">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="94c46-247">Bijvoorbeeld inclusief `~contoso.com` `contoso.com` en `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="94c46-247">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="94c46-248">URL-vermeldingen die protocollen bevatten (bijvoorbeeld , of ) mislukken, omdat URL-vermeldingen van toepassing zijn `http://` `https://` op alle `ftp://` protocollen.</span><span class="sxs-lookup"><span data-stu-id="94c46-248">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="94c46-249">Een gebruikersnaam of wachtwoord wordt niet ondersteund of vereist.</span><span class="sxs-lookup"><span data-stu-id="94c46-249">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="94c46-250">Aanhalingstekens (' of ") zijn ongeldige tekens.</span><span class="sxs-lookup"><span data-stu-id="94c46-250">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="94c46-251">Een URL moet waar mogelijk alle omleidingen bevatten.</span><span class="sxs-lookup"><span data-stu-id="94c46-251">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="94c46-252">Scenario's voor URL-invoer</span><span class="sxs-lookup"><span data-stu-id="94c46-252">URL entry scenarios</span></span>

<span data-ttu-id="94c46-253">Geldige URL-vermeldingen en de resultaten worden beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="94c46-253">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="94c46-254">Scenario: Geen jokertekens</span><span class="sxs-lookup"><span data-stu-id="94c46-254">Scenario: No wildcards</span></span>

<span data-ttu-id="94c46-255">**Vermelding**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="94c46-255">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="94c46-256">**Overeenkomst toestaan**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-256">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="94c46-257">**Niet-overeenkomende toestaan:**</span><span class="sxs-lookup"><span data-stu-id="94c46-257">**Allow not matched**:</span></span>

  - <span data-ttu-id="94c46-258">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-258">abc-contoso.com</span></span>
  - <span data-ttu-id="94c46-259">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="94c46-259">contoso.com/a</span></span>
  - <span data-ttu-id="94c46-260">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-260">payroll.contoso.com</span></span>
  - <span data-ttu-id="94c46-261">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-261">test.com/contoso.com</span></span>
  - <span data-ttu-id="94c46-262">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-262">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="94c46-263">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-263">www.contoso.com</span></span>
  - <span data-ttu-id="94c46-264">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-264">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="94c46-265">**Blok overeenkomst**:</span><span class="sxs-lookup"><span data-stu-id="94c46-265">**Block match**:</span></span>

  - <span data-ttu-id="94c46-266">contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-266">contoso.com</span></span>
  - <span data-ttu-id="94c46-267">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="94c46-267">contoso.com/a</span></span>
  - <span data-ttu-id="94c46-268">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-268">payroll.contoso.com</span></span>
  - <span data-ttu-id="94c46-269">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-269">test.com/contoso.com</span></span>
  - <span data-ttu-id="94c46-270">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-270">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="94c46-271">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-271">www.contoso.com</span></span>
  - <span data-ttu-id="94c46-272">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-272">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="94c46-273">**Blok niet overeenkomend**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-273">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="94c46-274">Scenario: Jokerteken links (subdomein)</span><span class="sxs-lookup"><span data-stu-id="94c46-274">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="94c46-275">**Vermelding**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="94c46-275">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="94c46-276">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="94c46-276">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="94c46-277">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-277">www.contoso.com</span></span>
  - <span data-ttu-id="94c46-278">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-278">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="94c46-279">**Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**</span><span class="sxs-lookup"><span data-stu-id="94c46-279">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="94c46-280">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-280">123contoso.com</span></span>
  - <span data-ttu-id="94c46-281">contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-281">contoso.com</span></span>
  - <span data-ttu-id="94c46-282">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-282">test.com/contoso.com</span></span>
  - <span data-ttu-id="94c46-283">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="94c46-283">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="94c46-284">Scenario: Jokerteken rechts boven aan pad</span><span class="sxs-lookup"><span data-stu-id="94c46-284">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="94c46-285">**Vermelding**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="94c46-285">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="94c46-286">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="94c46-286">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="94c46-287">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="94c46-287">contoso.com/a/b</span></span>
  - <span data-ttu-id="94c46-288">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="94c46-288">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="94c46-289">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="94c46-289">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="94c46-290">**Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**</span><span class="sxs-lookup"><span data-stu-id="94c46-290">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="94c46-291">contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-291">contoso.com</span></span>
  - <span data-ttu-id="94c46-292">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="94c46-292">contoso.com/a</span></span>
  - <span data-ttu-id="94c46-293">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-293">www.contoso.com</span></span>
  - <span data-ttu-id="94c46-294">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-294">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="94c46-295">Scenario: Tilde links</span><span class="sxs-lookup"><span data-stu-id="94c46-295">Scenario: Left tilde</span></span>

<span data-ttu-id="94c46-296">**Vermelding**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="94c46-296">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="94c46-297">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="94c46-297">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="94c46-298">contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-298">contoso.com</span></span>
  - <span data-ttu-id="94c46-299">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-299">www.contoso.com</span></span>
  - <span data-ttu-id="94c46-300">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-300">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="94c46-301">**Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**</span><span class="sxs-lookup"><span data-stu-id="94c46-301">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="94c46-302">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-302">123contoso.com</span></span>
  - <span data-ttu-id="94c46-303">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="94c46-303">contoso.com/abc</span></span>
  - <span data-ttu-id="94c46-304">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="94c46-304">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="94c46-305">Scenario: Het achtervoegsel van het jokerteken rechts</span><span class="sxs-lookup"><span data-stu-id="94c46-305">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="94c46-306">**Vermelding**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="94c46-306">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="94c46-307">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="94c46-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="94c46-308">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="94c46-308">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="94c46-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="94c46-309">contoso.com/a</span></span>
  - <span data-ttu-id="94c46-310">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="94c46-310">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="94c46-311">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="94c46-311">contoso.com/ab</span></span>
  - <span data-ttu-id="94c46-312">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="94c46-312">contoso.com/b</span></span>
  - <span data-ttu-id="94c46-313">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="94c46-313">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="94c46-314">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="94c46-314">contoso.com/ba</span></span>

- <span data-ttu-id="94c46-315">**Niet-overeenkomende en** **niet-overeenkomende** blokkering toestaan: contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-315">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="94c46-316">Scenario: Linker jokertekensubdomein en rechterachtervoegsel jokerteken</span><span class="sxs-lookup"><span data-stu-id="94c46-316">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="94c46-317">**Vermelding**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="94c46-317">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="94c46-318">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="94c46-318">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="94c46-319">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="94c46-319">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="94c46-320">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="94c46-320">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="94c46-321">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="94c46-321">www.contoso.com/a</span></span>
  - <span data-ttu-id="94c46-322">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="94c46-322">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="94c46-323">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="94c46-323">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="94c46-324">**Niet-overeenkomende en** **niet-overeenkomende** blokkering toestaan : contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="94c46-324">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="94c46-325">Scenario: Tilde links en rechts</span><span class="sxs-lookup"><span data-stu-id="94c46-325">Scenario: Left and right tilde</span></span>

<span data-ttu-id="94c46-326">**Vermelding**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="94c46-326">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="94c46-327">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="94c46-327">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="94c46-328">contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-328">contoso.com</span></span>
  - <span data-ttu-id="94c46-329">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="94c46-329">contoso.com/a</span></span>
  - <span data-ttu-id="94c46-330">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-330">www.contoso.com</span></span>
  - <span data-ttu-id="94c46-331">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="94c46-331">www.contoso.com/b</span></span>
  - <span data-ttu-id="94c46-332">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-332">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="94c46-333">**Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**</span><span class="sxs-lookup"><span data-stu-id="94c46-333">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="94c46-334">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-334">123contoso.com</span></span>
  - <span data-ttu-id="94c46-335">contoso.org</span><span class="sxs-lookup"><span data-stu-id="94c46-335">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="94c46-336">Scenario: IP-adres</span><span class="sxs-lookup"><span data-stu-id="94c46-336">Scenario: IP address</span></span>

<span data-ttu-id="94c46-337">**Vermelding**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="94c46-337">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="94c46-338">**Overeenkomst toestaan** **en overeenkomst blokkeren**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="94c46-338">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="94c46-339">**Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**</span><span class="sxs-lookup"><span data-stu-id="94c46-339">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="94c46-340">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="94c46-340">1.2.3.4/a</span></span>
  - <span data-ttu-id="94c46-341">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="94c46-341">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="94c46-342">IP-adres met jokerteken rechts</span><span class="sxs-lookup"><span data-stu-id="94c46-342">IP address with right wildcard</span></span>

<span data-ttu-id="94c46-343">**Vermelding**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="94c46-343">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="94c46-344">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="94c46-344">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="94c46-345">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="94c46-345">1.2.3.4/b</span></span>
  - <span data-ttu-id="94c46-346">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="94c46-346">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="94c46-347">Voorbeelden van ongeldige vermeldingen</span><span class="sxs-lookup"><span data-stu-id="94c46-347">Examples of invalid entries</span></span>

<span data-ttu-id="94c46-348">De volgende vermeldingen zijn ongeldig:</span><span class="sxs-lookup"><span data-stu-id="94c46-348">The following entries are invalid:</span></span>

- <span data-ttu-id="94c46-349">**Ontbrekende of ongeldige domeinwaarden:**</span><span class="sxs-lookup"><span data-stu-id="94c46-349">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="94c46-350">contoso</span><span class="sxs-lookup"><span data-stu-id="94c46-350">contoso</span></span>
  - <span data-ttu-id="94c46-351">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="94c46-351">\*.contoso.\*</span></span>
  - <span data-ttu-id="94c46-352">\*.com</span><span class="sxs-lookup"><span data-stu-id="94c46-352">\*.com</span></span>
  - <span data-ttu-id="94c46-353">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="94c46-353">\*.pdf</span></span>

- <span data-ttu-id="94c46-354">**Jokerteken op tekst of zonder spatiëringstekens:**</span><span class="sxs-lookup"><span data-stu-id="94c46-354">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="94c46-355">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c46-355">\*contoso.com</span></span>
  - <span data-ttu-id="94c46-356">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="94c46-356">contoso.com\*</span></span>
  - <span data-ttu-id="94c46-357">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="94c46-357">\*1.2.3.4</span></span>
  - <span data-ttu-id="94c46-358">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="94c46-358">1.2.3.4\*</span></span>
  - <span data-ttu-id="94c46-359">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="94c46-359">contoso.com/a\*</span></span>
  - <span data-ttu-id="94c46-360">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="94c46-360">contoso.com/ab\*</span></span>

- <span data-ttu-id="94c46-361">**IP-adressen met poorten:**</span><span class="sxs-lookup"><span data-stu-id="94c46-361">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="94c46-362">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="94c46-362">contoso.com:443</span></span>
  - <span data-ttu-id="94c46-363">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="94c46-363">abc.contoso.com:25</span></span>

- <span data-ttu-id="94c46-364">**Niet-beschrijvende jokertekens:**</span><span class="sxs-lookup"><span data-stu-id="94c46-364">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="94c46-365">\*.\*</span><span class="sxs-lookup"><span data-stu-id="94c46-365">\*.\*</span></span>

- <span data-ttu-id="94c46-366">**Middelste jokertekens:**</span><span class="sxs-lookup"><span data-stu-id="94c46-366">**Middle wildcards**:</span></span>

  - <span data-ttu-id="94c46-367">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="94c46-367">conto\*so.com</span></span>
  - <span data-ttu-id="94c46-368">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="94c46-368">conto~so.com</span></span>

- <span data-ttu-id="94c46-369">**Dubbele jokertekens**</span><span class="sxs-lookup"><span data-stu-id="94c46-369">**Double wildcards**</span></span>

  - <span data-ttu-id="94c46-370">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="94c46-370">contoso.com/\*\*</span></span>
  - <span data-ttu-id="94c46-371">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="94c46-371">contoso.com/\*/\*</span></span>
