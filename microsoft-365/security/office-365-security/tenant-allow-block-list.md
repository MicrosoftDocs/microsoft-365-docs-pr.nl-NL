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
ms.openlocfilehash: 2f97308bfc3600e4e85f5ac92d951b12d9a50f24
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928530"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="fa282-103">Tenant Toestaan/Blokkeren-lijst beheren</span><span class="sxs-lookup"><span data-stu-id="fa282-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="fa282-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="fa282-104">**Applies to**</span></span>
- [<span data-ttu-id="fa282-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="fa282-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="fa282-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="fa282-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="fa282-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fa282-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
>
> <span data-ttu-id="fa282-108">De functies die in dit artikel worden beschreven, zijn in Preview, kunnen worden gewijzigd en zijn niet beschikbaar in alle organisaties.</span><span class="sxs-lookup"><span data-stu-id="fa282-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>
>
> <span data-ttu-id="fa282-109">U kunt op dit **moment geen toegestane** items configureren in de lijst Tenant toestaan/blokkeren.</span><span class="sxs-lookup"><span data-stu-id="fa282-109">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="fa282-110">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken, bent u het mogelijk niet eens met de uitspraak over EOP-filtering.</span><span class="sxs-lookup"><span data-stu-id="fa282-110">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="fa282-111">Een goed bericht kan bijvoorbeeld worden gemarkeerd als slecht (een onwaar positief) of een slecht bericht kan worden toegestaan (een onwaar negatief).</span><span class="sxs-lookup"><span data-stu-id="fa282-111">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="fa282-112">Met de tenantlijst Toestaan/blokkeren in het Beveiligings- & Compliancecentrum kunt u handmatig de filterinspraken van Microsoft 365 overschrijven.</span><span class="sxs-lookup"><span data-stu-id="fa282-112">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="fa282-113">De lijst Tenant toestaan/blokkeren wordt gebruikt tijdens de e-mailstroom en op het moment dat de gebruiker klikt.</span><span class="sxs-lookup"><span data-stu-id="fa282-113">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="fa282-114">U kunt URL's of bestanden opgeven die u altijd wilt blokkeren.</span><span class="sxs-lookup"><span data-stu-id="fa282-114">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="fa282-115">In dit artikel wordt beschreven hoe u vermeldingen configureert in de lijst Tenant toestaan/blokkeren in het beveiligings- & compliancecentrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).</span><span class="sxs-lookup"><span data-stu-id="fa282-115">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fa282-116">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="fa282-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="fa282-117">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="fa282-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="fa282-118">Als u rechtstreeks naar de **pagina Lijst met tenants toestaan/blokkeren wilt** gaan, gebruikt u <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="fa282-118">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="fa282-119">U geeft bestanden op met de hashwaarde SHA256 van het bestand.</span><span class="sxs-lookup"><span data-stu-id="fa282-119">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="fa282-120">Als u de hashwaarde SHA256 van een bestand in Windows wilt zoeken, voer u de volgende opdracht uit in een opdrachtprompt:</span><span class="sxs-lookup"><span data-stu-id="fa282-120">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="fa282-121">Een voorbeeldwaarde is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="fa282-121">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="fa282-122">Perceptuele hashwaarden (pHash) worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="fa282-122">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="fa282-123">De beschikbare URL-waarden worden beschreven in de syntaxis van de URL voor de sectie Lijst met tenants [toestaan/blokkeren](#url-syntax-for-the-tenant-allowblock-list) verderop in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="fa282-123">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="fa282-124">De lijst Tenant toestaan/blokkeren staat maximaal 500 vermeldingen voor URL's en 500 vermeldingen voor bestandshashes toe.</span><span class="sxs-lookup"><span data-stu-id="fa282-124">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="fa282-125">Het maximum aantal tekens voor elke vermelding is:</span><span class="sxs-lookup"><span data-stu-id="fa282-125">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="fa282-126">Bestandshashes = 64</span><span class="sxs-lookup"><span data-stu-id="fa282-126">File hashes = 64</span></span>
  - <span data-ttu-id="fa282-127">URL = 250</span><span class="sxs-lookup"><span data-stu-id="fa282-127">URL = 250</span></span>

- <span data-ttu-id="fa282-128">Een item moet binnen 30 minuten actief zijn.</span><span class="sxs-lookup"><span data-stu-id="fa282-128">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="fa282-129">Standaard verlopen vermeldingen in de lijst Tenant toestaan/blokkeren na 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="fa282-129">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="fa282-130">U kunt een datum opgeven of instellen dat deze nooit verloopt.</span><span class="sxs-lookup"><span data-stu-id="fa282-130">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="fa282-131">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fa282-131">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="fa282-132">Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fa282-132">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="fa282-133">U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="fa282-133">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="fa282-134">Als u waarden wilt toevoegen en verwijderen uit de lijst Tenant toestaan/blokkeren, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="fa282-134">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="fa282-135">Voor alleen-lezen toegang tot de tenantlijst toestaan/blokkeren moet  u lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="fa282-135">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="fa282-136">Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="fa282-136">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="fa282-137">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fa282-137">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="fa282-138">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="fa282-138">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  > - <span data-ttu-id="fa282-139">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="fa282-139">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="fa282-140">Gebruik het beveiligings- & compliancecentrum om URL-vermeldingen te maken in de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="fa282-140">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="fa282-141">Zie de syntaxis van de URL voor de sectie Lijst met tenants [toestaan/blokkeren](#url-syntax-for-the-tenant-allowblock-list) verderop in dit artikel voor meer informatie over de syntaxis van URL-vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="fa282-141">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="fa282-142">Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="fa282-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="fa282-143">Controleer op de pagina Lijst met **tenants toestaan/blokkeren** of het tabblad **URL's** is geselecteerd en klik vervolgens op **Blokkeren**</span><span class="sxs-lookup"><span data-stu-id="fa282-143">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="fa282-144">Configureer **de volgende** instellingen in het flyout URL's blokkeren dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="fa282-144">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="fa282-145">**URL's toevoegen om te blokkeren:** Voer één URL per regel in, maximaal 20.</span><span class="sxs-lookup"><span data-stu-id="fa282-145">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="fa282-146">**Nooit verlopen:** Ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="fa282-146">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="fa282-147">Controleer of de instelling is uitgeschakeld (schakel uit) en gebruik het vak Verloopt aan om de vervaldatum voor de ![ ](../../media/scc-toggle-off.png) vermeldingen op te geven. </span><span class="sxs-lookup"><span data-stu-id="fa282-147">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="fa282-148">of</span><span class="sxs-lookup"><span data-stu-id="fa282-148">or</span></span>

     - <span data-ttu-id="fa282-149">Verplaats de schakelknop naar rechts om de items zo te configureren dat ze nooit verlopen:</span><span class="sxs-lookup"><span data-stu-id="fa282-149">Move the toggle to the right to configure the entries to never expire:</span></span> ![Inschakelen](../../media/scc-toggle-on.png)<span data-ttu-id="fa282-151">.</span><span class="sxs-lookup"><span data-stu-id="fa282-151">.</span></span>

   - <span data-ttu-id="fa282-152">**Optionele opmerking:** Voer beschrijvende tekst in voor de vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="fa282-152">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="fa282-153">Wanneer u klaar bent, klikt u op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="fa282-153">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="fa282-154">Gebruik het beveiligings- & compliancecentrum om bestandsgegevens te maken in de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="fa282-154">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="fa282-155">Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="fa282-155">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="fa282-156">Selecteer op de pagina Lijst met **tenants toestaan/blokkeren** de optie **Tabblad** Bestanden en klik vervolgens op **Blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="fa282-156">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="fa282-157">Configureer **de volgende instellingen in het flyout** add files to block flyout that appears:</span><span class="sxs-lookup"><span data-stu-id="fa282-157">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="fa282-158">**Bestandshashes toevoegen:** Voer één SHA256-hashwaarde per regel in, maximaal 20.</span><span class="sxs-lookup"><span data-stu-id="fa282-158">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="fa282-159">**Nooit verlopen:** Ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="fa282-159">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="fa282-160">Controleer of de instelling is uitgeschakeld (schakel uit) en gebruik het vak Verloopt aan om de vervaldatum voor de ![ ](../../media/scc-toggle-off.png) vermeldingen op te geven. </span><span class="sxs-lookup"><span data-stu-id="fa282-160">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="fa282-161">of</span><span class="sxs-lookup"><span data-stu-id="fa282-161">or</span></span>

     - <span data-ttu-id="fa282-162">Verplaats de schakelknop naar rechts om de items zo te configureren dat ze nooit verlopen:</span><span class="sxs-lookup"><span data-stu-id="fa282-162">Move the toggle to the right to configure the entries to never expire:</span></span> ![Inschakelen](../../media/scc-toggle-on.png)<span data-ttu-id="fa282-164">.</span><span class="sxs-lookup"><span data-stu-id="fa282-164">.</span></span>

   - <span data-ttu-id="fa282-165">**Optionele opmerking:** Voer beschrijvende tekst in voor de vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="fa282-165">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="fa282-166">Wanneer u klaar bent, klikt u op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="fa282-166">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="fa282-167">Het beveiligings- & compliancecentrum gebruiken om items in de lijst Tenant toestaan/blokkeren weer te geven</span><span class="sxs-lookup"><span data-stu-id="fa282-167">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="fa282-168">Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="fa282-168">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="fa282-169">Selecteer het **tabblad URL's** of het **tabblad** Bestanden.</span><span class="sxs-lookup"><span data-stu-id="fa282-169">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="fa282-170">Klik op de volgende kolomkoppen om in oplopende of aflopende volgorde te sorteren:</span><span class="sxs-lookup"><span data-stu-id="fa282-170">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="fa282-171">**Waarde:** De URL of de bestandshash.</span><span class="sxs-lookup"><span data-stu-id="fa282-171">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="fa282-172">**Laatst bijgewerkte datum**</span><span class="sxs-lookup"><span data-stu-id="fa282-172">**Last updated date**</span></span>
- <span data-ttu-id="fa282-173">**Vervaldatum**</span><span class="sxs-lookup"><span data-stu-id="fa282-173">**Expiration date**</span></span>
- <span data-ttu-id="fa282-174">**Opmerking**</span><span class="sxs-lookup"><span data-stu-id="fa282-174">**Note**</span></span>

<span data-ttu-id="fa282-175">Klik **op Zoeken,** voer een hele of een deel van een waarde in en druk vervolgens op Enter om een specifieke waarde te zoeken.</span><span class="sxs-lookup"><span data-stu-id="fa282-175">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="fa282-176">Wanneer u klaar bent, klikt u op **Zoek verwijderen Zoekpictogram** ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) verwijderen.</span><span class="sxs-lookup"><span data-stu-id="fa282-176">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="fa282-177">Klik **op Filteren.**</span><span class="sxs-lookup"><span data-stu-id="fa282-177">Click **Filter**.</span></span> <span data-ttu-id="fa282-178">Configureer **een van** de volgende instellingen in het flyout Filter dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="fa282-178">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="fa282-179">**Nooit verlopen:** Uit- of ![ ](../../media/scc-toggle-off.png) uitschakelen: ![ In- of uitschakelen: In- of ](../../media/scc-toggle-on.png) uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="fa282-179">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="fa282-180">**Laatst bijgewerkt:** Selecteer een begindatum **(Van),** een einddatum **(Aan)** of beide.</span><span class="sxs-lookup"><span data-stu-id="fa282-180">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="fa282-181">**Vervaldatum:** Selecteer een begindatum (**Van**), een einddatum (**Aan**) of beide.</span><span class="sxs-lookup"><span data-stu-id="fa282-181">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="fa282-182">Wanneer u klaar bent, klikt u op **Toepassen.**</span><span class="sxs-lookup"><span data-stu-id="fa282-182">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="fa282-183">Als u bestaande filters wilt wissen, klikt u **op Filter** en klikt u in het **fly-out** Filter dat wordt weergegeven op Filters **wissen.**</span><span class="sxs-lookup"><span data-stu-id="fa282-183">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="fa282-184">Gebruik het beveiligings- & compliancecentrum om blokinzendingen in de lijst Tenant toestaan/blokkeren te wijzigen</span><span class="sxs-lookup"><span data-stu-id="fa282-184">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="fa282-185">U kunt de bestaande geblokkeerde URL of bestandswaarden in een item niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="fa282-185">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="fa282-186">Als u deze waarden wilt wijzigen, moet u de vermelding verwijderen en opnieuw maken.</span><span class="sxs-lookup"><span data-stu-id="fa282-186">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="fa282-187">Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="fa282-187">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="fa282-188">Selecteer het **tabblad URL's** of het **tabblad** Bestanden.</span><span class="sxs-lookup"><span data-stu-id="fa282-188">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="fa282-189">Selecteer de blokinvoer die u wilt wijzigen en klik vervolgens op **Pictogram** ![ Bewerken ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) bewerken.</span><span class="sxs-lookup"><span data-stu-id="fa282-189">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="fa282-190">Configureer de volgende instellingen in het flyout dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="fa282-190">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="fa282-191">**Nooit verlopen:** Ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="fa282-191">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="fa282-192">Controleer of de instelling is uitgeschakeld (schakelknop uit) en gebruik het vak Verloopt op om de vervaldatum voor ![ de vermelding op te ](../../media/scc-toggle-off.png) geven. </span><span class="sxs-lookup"><span data-stu-id="fa282-192">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

       <span data-ttu-id="fa282-193">of</span><span class="sxs-lookup"><span data-stu-id="fa282-193">or</span></span>

     - <span data-ttu-id="fa282-194">Verplaats de schakelknop naar rechts om de vermelding zo te configureren dat deze nooit verloopt:</span><span class="sxs-lookup"><span data-stu-id="fa282-194">Move the toggle to the right to configure the entry to never expire:</span></span> ![Inschakelen](../../media/scc-toggle-on.png)<span data-ttu-id="fa282-196">.</span><span class="sxs-lookup"><span data-stu-id="fa282-196">.</span></span>

   - <span data-ttu-id="fa282-197">**Optionele opmerking:** Voer beschrijvende tekst in voor de vermelding.</span><span class="sxs-lookup"><span data-stu-id="fa282-197">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="fa282-198">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="fa282-198">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="fa282-199">Het beveiligings- & compliancecentrum gebruiken om blokinzendingen uit de lijst Met tenant toestaan/blokkeren te verwijderen</span><span class="sxs-lookup"><span data-stu-id="fa282-199">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="fa282-200">Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="fa282-200">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="fa282-201">Selecteer het **tabblad URL's** of het **tabblad** Bestanden.</span><span class="sxs-lookup"><span data-stu-id="fa282-201">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="fa282-202">Selecteer de blokinvoer die u wilt verwijderen en klik vervolgens op **Pictogram** ![ Verwijderen ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) verwijderen.</span><span class="sxs-lookup"><span data-stu-id="fa282-202">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="fa282-203">Klik in het waarschuwingsvenster dat wordt weergegeven op **Verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="fa282-203">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="fa282-204">Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken om de tenantlijst toestaan/blokkeren te configureren</span><span class="sxs-lookup"><span data-stu-id="fa282-204">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="fa282-205">PowerShell gebruiken om blokgegevens toe te voegen aan de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="fa282-205">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="fa282-206">Gebruik de volgende syntaxis om blokgegevens toe te voegen in de lijst Tenant Allow/Block:</span><span class="sxs-lookup"><span data-stu-id="fa282-206">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="fa282-207">In dit voorbeeld wordt een blok-URL-vermelding voor contoso.com en alle subdomeinen (bijvoorbeeld contoso.com, www.contoso.com en xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="fa282-207">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="fa282-208">Omdat we de parameters Vervaldatum of NoExpiration niet hebben gebruikt, verloopt de vermelding na 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="fa282-208">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="fa282-209">In dit voorbeeld wordt een blokbestandsinvoer toegevoegd voor de opgegeven bestanden die nooit verlopen.</span><span class="sxs-lookup"><span data-stu-id="fa282-209">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="fa282-210">Zie [New-TenantAllowBlockListItems voor](/powershell/module/exchange/new-tenantallowblocklistitems)gedetailleerde syntaxis en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="fa282-210">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="fa282-211">PowerShell gebruiken om items in de lijst Tenant toestaan/blokkeren weer te geven</span><span class="sxs-lookup"><span data-stu-id="fa282-211">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="fa282-212">Gebruik de volgende syntaxis om vermeldingen in de lijst Tenant toestaan/blokkeren weer te geven:</span><span class="sxs-lookup"><span data-stu-id="fa282-212">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="fa282-213">In dit voorbeeld worden alle geblokkeerde URL's als retourneert.</span><span class="sxs-lookup"><span data-stu-id="fa282-213">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="fa282-214">In dit voorbeeld worden gegevens voor de opgegeven waarde voor bestandshash als resultaat gegeven.</span><span class="sxs-lookup"><span data-stu-id="fa282-214">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="fa282-215">Zie [Get-TenantAllowBlockListItems voor](/powershell/module/exchange/get-tenantallowblocklistitems)gedetailleerde syntaxis en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="fa282-215">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="fa282-216">PowerShell gebruiken om blokgegevens in de lijst Tenant toestaan/blokkeren te wijzigen</span><span class="sxs-lookup"><span data-stu-id="fa282-216">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="fa282-217">U kunt de bestaande URL- of bestandswaarden in een blokinvoer niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="fa282-217">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="fa282-218">Als u deze waarden wilt wijzigen, moet u de vermelding verwijderen en opnieuw maken.</span><span class="sxs-lookup"><span data-stu-id="fa282-218">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="fa282-219">Gebruik de volgende syntaxis om blokgegevens in de lijst Tenant toestaan/blokkeren te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="fa282-219">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="fa282-220">In dit voorbeeld wordt de vervaldatum van de opgegeven blokinvoer gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="fa282-220">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="fa282-221">Zie [Set-TenantAllowBlockListItems (Set-TenantAllowBlockListItems)](/powershell/module/exchange/set-tenantallowblocklistitems)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="fa282-221">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="fa282-222">PowerShell gebruiken om blokgegevens te verwijderen uit de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="fa282-222">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="fa282-223">Als u blokinzendingen wilt verwijderen uit de lijst Tenant toestaan/blokkeren, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="fa282-223">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="fa282-224">In dit voorbeeld wordt de opgegeven blok-URL-vermelding verwijderd uit de lijst Tenant toestaan/blokkeren.</span><span class="sxs-lookup"><span data-stu-id="fa282-224">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="fa282-225">Zie [Remove-TenantAllowBlockListItems (Verwijderen-TenantAllowBlockListItems)](/powershell/module/exchange/remove-tenantallowblocklistitems)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="fa282-225">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="fa282-226">URL-syntaxis voor de lijst Toestaan/blokkeren van tenant</span><span class="sxs-lookup"><span data-stu-id="fa282-226">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="fa282-227">IP4v- en IPv6-adressen zijn toegestaan, maar TCP/UDP-poorten niet.</span><span class="sxs-lookup"><span data-stu-id="fa282-227">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="fa282-228">Bestandsnaamextensies zijn niet toegestaan (bijvoorbeeld test.pdf).</span><span class="sxs-lookup"><span data-stu-id="fa282-228">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="fa282-229">Unicode wordt niet ondersteund, maar Punycode wel.</span><span class="sxs-lookup"><span data-stu-id="fa282-229">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="fa282-230">Hostnamen zijn toegestaan als alle volgende instructies waar zijn:</span><span class="sxs-lookup"><span data-stu-id="fa282-230">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="fa282-231">De hostnaam bevat een punt.</span><span class="sxs-lookup"><span data-stu-id="fa282-231">The hostname contains a period.</span></span>
  - <span data-ttu-id="fa282-232">Er is ten minste één teken links van de periode.</span><span class="sxs-lookup"><span data-stu-id="fa282-232">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="fa282-233">Er zijn ten minste twee tekens rechts van de periode.</span><span class="sxs-lookup"><span data-stu-id="fa282-233">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="fa282-234">Is bijvoorbeeld `t.co` toegestaan of `.com` niet `contoso.` toegestaan.</span><span class="sxs-lookup"><span data-stu-id="fa282-234">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="fa282-235">Subpathen worden niet geïmpliceerd.</span><span class="sxs-lookup"><span data-stu-id="fa282-235">Subpaths are not implied.</span></span>

  <span data-ttu-id="fa282-236">Bevat bijvoorbeeld `contoso.com` geen `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="fa282-236">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="fa282-237">Jokertekens (\*) zijn toegestaan in de volgende scenario's:</span><span class="sxs-lookup"><span data-stu-id="fa282-237">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="fa282-238">Een linker jokerteken moet worden gevolgd door een punt om een subdomein op te geven.</span><span class="sxs-lookup"><span data-stu-id="fa282-238">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="fa282-239">Is bijvoorbeeld `*.contoso.com` toegestaan; `*contoso.com` is niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="fa282-239">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="fa282-240">Een jokerteken rechts moet een slash (/) volgen om een pad op te geven.</span><span class="sxs-lookup"><span data-stu-id="fa282-240">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="fa282-241">Is bijvoorbeeld `contoso.com/*` toegestaan of `contoso.com*` niet `contoso.com/ab*` toegestaan.</span><span class="sxs-lookup"><span data-stu-id="fa282-241">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="fa282-242">Alle subpathen worden niet geïmpliceerd door een rechter jokerteken.</span><span class="sxs-lookup"><span data-stu-id="fa282-242">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="fa282-243">Bevat bijvoorbeeld `contoso.com/*` geen `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="fa282-243">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="fa282-244">`*.com*` ongeldig is (geen op te lossen domein en het jokerteken rechts volgt geen slash voor vooruit).</span><span class="sxs-lookup"><span data-stu-id="fa282-244">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="fa282-245">Jokertekens zijn niet toegestaan in IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="fa282-245">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="fa282-246">Het tildeteken (~) is beschikbaar in de volgende scenario's:</span><span class="sxs-lookup"><span data-stu-id="fa282-246">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="fa282-247">Een linker tilde houdt een domein en alle subdomeinen in.</span><span class="sxs-lookup"><span data-stu-id="fa282-247">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="fa282-248">Bijvoorbeeld inclusief `~contoso.com` `contoso.com` en `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="fa282-248">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="fa282-249">URL-vermeldingen die protocollen bevatten (bijvoorbeeld , of ) mislukken, omdat URL-vermeldingen van toepassing zijn `http://` `https://` op alle `ftp://` protocollen.</span><span class="sxs-lookup"><span data-stu-id="fa282-249">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="fa282-250">Een gebruikersnaam of wachtwoord wordt niet ondersteund of vereist.</span><span class="sxs-lookup"><span data-stu-id="fa282-250">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="fa282-251">Aanhalingstekens (' of ") zijn ongeldige tekens.</span><span class="sxs-lookup"><span data-stu-id="fa282-251">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="fa282-252">Een URL moet waar mogelijk alle omleidingen bevatten.</span><span class="sxs-lookup"><span data-stu-id="fa282-252">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="fa282-253">Scenario's voor URL-invoer</span><span class="sxs-lookup"><span data-stu-id="fa282-253">URL entry scenarios</span></span>

<span data-ttu-id="fa282-254">Geldige URL-vermeldingen en de resultaten worden beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="fa282-254">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="fa282-255">Scenario: Geen jokertekens</span><span class="sxs-lookup"><span data-stu-id="fa282-255">Scenario: No wildcards</span></span>

<span data-ttu-id="fa282-256">**Vermelding**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="fa282-256">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="fa282-257">**Overeenkomst toestaan**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-257">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="fa282-258">**Niet-overeenkomende toestaan:**</span><span class="sxs-lookup"><span data-stu-id="fa282-258">**Allow not matched**:</span></span>

  - <span data-ttu-id="fa282-259">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-259">abc-contoso.com</span></span>
  - <span data-ttu-id="fa282-260">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="fa282-260">contoso.com/a</span></span>
  - <span data-ttu-id="fa282-261">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-261">payroll.contoso.com</span></span>
  - <span data-ttu-id="fa282-262">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-262">test.com/contoso.com</span></span>
  - <span data-ttu-id="fa282-263">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-263">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="fa282-264">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-264">www.contoso.com</span></span>
  - <span data-ttu-id="fa282-265">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-265">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="fa282-266">**Blok overeenkomst**:</span><span class="sxs-lookup"><span data-stu-id="fa282-266">**Block match**:</span></span>

  - <span data-ttu-id="fa282-267">contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-267">contoso.com</span></span>
  - <span data-ttu-id="fa282-268">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="fa282-268">contoso.com/a</span></span>
  - <span data-ttu-id="fa282-269">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-269">payroll.contoso.com</span></span>
  - <span data-ttu-id="fa282-270">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-270">test.com/contoso.com</span></span>
  - <span data-ttu-id="fa282-271">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-271">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="fa282-272">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-272">www.contoso.com</span></span>
  - <span data-ttu-id="fa282-273">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-273">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="fa282-274">**Blok niet overeenkomend**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-274">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="fa282-275">Scenario: Jokerteken links (subdomein)</span><span class="sxs-lookup"><span data-stu-id="fa282-275">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="fa282-276">**Vermelding**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="fa282-276">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="fa282-277">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="fa282-277">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="fa282-278">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-278">www.contoso.com</span></span>
  - <span data-ttu-id="fa282-279">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-279">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="fa282-280">**Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**</span><span class="sxs-lookup"><span data-stu-id="fa282-280">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="fa282-281">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-281">123contoso.com</span></span>
  - <span data-ttu-id="fa282-282">contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-282">contoso.com</span></span>
  - <span data-ttu-id="fa282-283">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-283">test.com/contoso.com</span></span>
  - <span data-ttu-id="fa282-284">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="fa282-284">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="fa282-285">Scenario: Jokerteken rechts boven aan pad</span><span class="sxs-lookup"><span data-stu-id="fa282-285">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="fa282-286">**Vermelding**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="fa282-286">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="fa282-287">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="fa282-287">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="fa282-288">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="fa282-288">contoso.com/a/b</span></span>
  - <span data-ttu-id="fa282-289">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="fa282-289">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="fa282-290">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="fa282-290">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="fa282-291">**Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**</span><span class="sxs-lookup"><span data-stu-id="fa282-291">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="fa282-292">contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-292">contoso.com</span></span>
  - <span data-ttu-id="fa282-293">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="fa282-293">contoso.com/a</span></span>
  - <span data-ttu-id="fa282-294">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-294">www.contoso.com</span></span>
  - <span data-ttu-id="fa282-295">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-295">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="fa282-296">Scenario: Tilde links</span><span class="sxs-lookup"><span data-stu-id="fa282-296">Scenario: Left tilde</span></span>

<span data-ttu-id="fa282-297">**Vermelding**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="fa282-297">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="fa282-298">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="fa282-298">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="fa282-299">contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-299">contoso.com</span></span>
  - <span data-ttu-id="fa282-300">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-300">www.contoso.com</span></span>
  - <span data-ttu-id="fa282-301">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-301">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="fa282-302">**Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**</span><span class="sxs-lookup"><span data-stu-id="fa282-302">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="fa282-303">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-303">123contoso.com</span></span>
  - <span data-ttu-id="fa282-304">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="fa282-304">contoso.com/abc</span></span>
  - <span data-ttu-id="fa282-305">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="fa282-305">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="fa282-306">Scenario: Het achtervoegsel van het jokerteken rechts</span><span class="sxs-lookup"><span data-stu-id="fa282-306">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="fa282-307">**Vermelding**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="fa282-307">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="fa282-308">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="fa282-308">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="fa282-309">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="fa282-309">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="fa282-310">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="fa282-310">contoso.com/a</span></span>
  - <span data-ttu-id="fa282-311">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="fa282-311">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="fa282-312">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="fa282-312">contoso.com/ab</span></span>
  - <span data-ttu-id="fa282-313">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="fa282-313">contoso.com/b</span></span>
  - <span data-ttu-id="fa282-314">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="fa282-314">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="fa282-315">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="fa282-315">contoso.com/ba</span></span>

- <span data-ttu-id="fa282-316">**Niet-overeenkomende en** **niet-overeenkomende** blokkering toestaan: contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-316">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="fa282-317">Scenario: Linker jokertekensubdomein en rechterachtervoegsel jokerteken</span><span class="sxs-lookup"><span data-stu-id="fa282-317">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="fa282-318">**Vermelding**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="fa282-318">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="fa282-319">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="fa282-319">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="fa282-320">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="fa282-320">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="fa282-321">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="fa282-321">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="fa282-322">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="fa282-322">www.contoso.com/a</span></span>
  - <span data-ttu-id="fa282-323">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="fa282-323">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="fa282-324">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="fa282-324">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="fa282-325">**Niet-overeenkomende en** **niet-overeenkomende** blokkering toestaan : contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="fa282-325">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="fa282-326">Scenario: Tilde links en rechts</span><span class="sxs-lookup"><span data-stu-id="fa282-326">Scenario: Left and right tilde</span></span>

<span data-ttu-id="fa282-327">**Vermelding**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="fa282-327">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="fa282-328">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="fa282-328">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="fa282-329">contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-329">contoso.com</span></span>
  - <span data-ttu-id="fa282-330">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="fa282-330">contoso.com/a</span></span>
  - <span data-ttu-id="fa282-331">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-331">www.contoso.com</span></span>
  - <span data-ttu-id="fa282-332">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="fa282-332">www.contoso.com/b</span></span>
  - <span data-ttu-id="fa282-333">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-333">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="fa282-334">**Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**</span><span class="sxs-lookup"><span data-stu-id="fa282-334">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="fa282-335">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-335">123contoso.com</span></span>
  - <span data-ttu-id="fa282-336">contoso.org</span><span class="sxs-lookup"><span data-stu-id="fa282-336">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="fa282-337">Scenario: IP-adres</span><span class="sxs-lookup"><span data-stu-id="fa282-337">Scenario: IP address</span></span>

<span data-ttu-id="fa282-338">**Vermelding**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="fa282-338">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="fa282-339">**Overeenkomst toestaan** **en overeenkomst blokkeren**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="fa282-339">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="fa282-340">**Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**</span><span class="sxs-lookup"><span data-stu-id="fa282-340">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="fa282-341">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="fa282-341">1.2.3.4/a</span></span>
  - <span data-ttu-id="fa282-342">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="fa282-342">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="fa282-343">IP-adres met jokerteken rechts</span><span class="sxs-lookup"><span data-stu-id="fa282-343">IP address with right wildcard</span></span>

<span data-ttu-id="fa282-344">**Vermelding**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="fa282-344">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="fa282-345">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="fa282-345">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="fa282-346">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="fa282-346">1.2.3.4/b</span></span>
  - <span data-ttu-id="fa282-347">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="fa282-347">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="fa282-348">Voorbeelden van ongeldige vermeldingen</span><span class="sxs-lookup"><span data-stu-id="fa282-348">Examples of invalid entries</span></span>

<span data-ttu-id="fa282-349">De volgende vermeldingen zijn ongeldig:</span><span class="sxs-lookup"><span data-stu-id="fa282-349">The following entries are invalid:</span></span>

- <span data-ttu-id="fa282-350">**Ontbrekende of ongeldige domeinwaarden:**</span><span class="sxs-lookup"><span data-stu-id="fa282-350">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="fa282-351">contoso</span><span class="sxs-lookup"><span data-stu-id="fa282-351">contoso</span></span>
  - <span data-ttu-id="fa282-352">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="fa282-352">\*.contoso.\*</span></span>
  - <span data-ttu-id="fa282-353">\*.com</span><span class="sxs-lookup"><span data-stu-id="fa282-353">\*.com</span></span>
  - <span data-ttu-id="fa282-354">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="fa282-354">\*.pdf</span></span>

- <span data-ttu-id="fa282-355">**Jokerteken op tekst of zonder spatiëringstekens:**</span><span class="sxs-lookup"><span data-stu-id="fa282-355">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="fa282-356">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa282-356">\*contoso.com</span></span>
  - <span data-ttu-id="fa282-357">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="fa282-357">contoso.com\*</span></span>
  - <span data-ttu-id="fa282-358">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="fa282-358">\*1.2.3.4</span></span>
  - <span data-ttu-id="fa282-359">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="fa282-359">1.2.3.4\*</span></span>
  - <span data-ttu-id="fa282-360">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="fa282-360">contoso.com/a\*</span></span>
  - <span data-ttu-id="fa282-361">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="fa282-361">contoso.com/ab\*</span></span>

- <span data-ttu-id="fa282-362">**IP-adressen met poorten:**</span><span class="sxs-lookup"><span data-stu-id="fa282-362">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="fa282-363">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="fa282-363">contoso.com:443</span></span>
  - <span data-ttu-id="fa282-364">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="fa282-364">abc.contoso.com:25</span></span>

- <span data-ttu-id="fa282-365">**Niet-beschrijvende jokertekens:**</span><span class="sxs-lookup"><span data-stu-id="fa282-365">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="fa282-366">\*.\*</span><span class="sxs-lookup"><span data-stu-id="fa282-366">\*.\*</span></span>

- <span data-ttu-id="fa282-367">**Middelste jokertekens:**</span><span class="sxs-lookup"><span data-stu-id="fa282-367">**Middle wildcards**:</span></span>

  - <span data-ttu-id="fa282-368">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="fa282-368">conto\*so.com</span></span>
  - <span data-ttu-id="fa282-369">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="fa282-369">conto~so.com</span></span>

- <span data-ttu-id="fa282-370">**Dubbele jokertekens**</span><span class="sxs-lookup"><span data-stu-id="fa282-370">**Double wildcards**</span></span>

  - <span data-ttu-id="fa282-371">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="fa282-371">contoso.com/\*\*</span></span>
  - <span data-ttu-id="fa282-372">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="fa282-372">contoso.com/\*/\*</span></span>