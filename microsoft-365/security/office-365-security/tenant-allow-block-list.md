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
ms.openlocfilehash: 270e38d65857de2f4d06460fb3bb77f72a165ecf
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538961"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="1d6ce-103">Tenant Toestaan/Blokkeren-lijst beheren</span><span class="sxs-lookup"><span data-stu-id="1d6ce-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1d6ce-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-104">**Applies to**</span></span>
- [<span data-ttu-id="1d6ce-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1d6ce-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="1d6ce-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="1d6ce-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1d6ce-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1d6ce-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="1d6ce-108">De functies die in dit artikel worden beschreven, zijn in Preview, kunnen worden gewijzigd en zijn niet beschikbaar in alle organisaties.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="1d6ce-109">Als uw organisatie niet beschikt over de spooffuncties zoals beschreven in dit artikel, bekijkt u de oudere spoofbeheerervaring bij Vervalste afzenders beheren met behulp van het spoof intelligence-beleid en het inzicht in spoof [intelligence in EOP.](walkthrough-spoof-intelligence-insight.md)</span><span class="sxs-lookup"><span data-stu-id="1d6ce-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="1d6ce-110">U kunt op dit **moment geen** toegestane URL- of bestandsitems configureren in de lijst Tenant toestaan/blokkeren.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="1d6ce-111">In Microsoft 365 organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken, kunt u het niet eens zijn met de uitspraak over EOP-filtering.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="1d6ce-112">Een goed bericht kan bijvoorbeeld worden gemarkeerd als slecht (een onwaar positief) of een slecht bericht kan worden toegestaan (een onwaar negatief).</span><span class="sxs-lookup"><span data-stu-id="1d6ce-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="1d6ce-113">Met de tenantlijst Toestaan/blokkeren in het Beveiligings- & Compliancecentrum kunt u handmatig de regels voor filteren Microsoft 365 overschrijven.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-113">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="1d6ce-114">De lijst Tenant toestaan/blokkeren wordt gebruikt tijdens de e-mailstroom en op het moment dat de gebruiker klikt.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-114">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="1d6ce-115">U kunt de volgende typen overschrijven opgeven:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="1d6ce-116">URL's die u wilt blokkeren.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-116">URLs to block.</span></span>
- <span data-ttu-id="1d6ce-117">Bestanden die u wilt blokkeren.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-117">Files to block.</span></span>
- <span data-ttu-id="1d6ce-118">Bulkmail sender domains to allow.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-118">Bulk mail sender domains to allow.</span></span> <span data-ttu-id="1d6ce-119">Zie Bulk [complaint level (BCL) in EOP voor](bulk-complaint-level-values.md)meer informatie over bulkmail, het bulk-betrouwbaarheidsniveau (BCL) en bulkmailfilters door antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-119">For more information about bulk mail, the bulk confidence level (BCL), and bulk mail filtering by anti-spam policies, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>
- <span data-ttu-id="1d6ce-120">Vervalste afzenders om dit toe te staan of te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-120">Spoofed senders to allow or block.</span></span> <span data-ttu-id="1d6ce-121">Als u de uitspraak toestaan of blokkeren overschrijven in het inzicht van spoof [intelligence,](learn-about-spoof-intelligence.md)wordt de vervalste afzender een handmatige invoer toestaan of blokkeren die alleen wordt weergegeven op het tabblad **Spoof** in de lijst Toestaan/blokkeren van tenants.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-121">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="1d6ce-122">U kunt hier ook handmatig vermeldingen voor vervalste afzenders maken of blokkeren voordat ze worden gedetecteerd door spoofinformatie.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-122">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="1d6ce-123">In dit artikel wordt beschreven hoe u vermeldingen configureert in de lijst Tenant toestaan/blokkeren in het Beveiligings- & Compliancecentrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).</span><span class="sxs-lookup"><span data-stu-id="1d6ce-123">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1d6ce-124">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="1d6ce-124">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1d6ce-125">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-125">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="1d6ce-126">Als u rechtstreeks naar de **pagina Lijst met tenants toestaan/blokkeren wilt** gaan, gebruikt u <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="1d6ce-126">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="1d6ce-127">U geeft bestanden op met de hashwaarde SHA256 van het bestand.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-127">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="1d6ce-128">Als u de hashwaarde SHA256 van een bestand in Windows wilt zoeken, voer u de volgende opdracht uit in een opdrachtprompt:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-128">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="1d6ce-129">Een voorbeeldwaarde is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="1d6ce-129">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="1d6ce-130">Perceptuele hashwaarden (pHash) worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-130">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="1d6ce-131">De beschikbare URL-waarden worden beschreven in de syntaxis van de URL voor de sectie Lijst met tenants [toestaan/blokkeren](#url-syntax-for-the-tenant-allowblock-list) verderop in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-131">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="1d6ce-132">De lijst Tenant toestaan/blokkeren staat maximaal 500 vermeldingen voor URL's en 500 vermeldingen voor bestandshashes toe.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-132">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="1d6ce-133">Het maximum aantal tekens voor elke vermelding is:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-133">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="1d6ce-134">Bestandshashes = 64</span><span class="sxs-lookup"><span data-stu-id="1d6ce-134">File hashes = 64</span></span>
  - <span data-ttu-id="1d6ce-135">URL = 250</span><span class="sxs-lookup"><span data-stu-id="1d6ce-135">URL = 250</span></span>

- <span data-ttu-id="1d6ce-136">Een item moet binnen 30 minuten actief zijn.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-136">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="1d6ce-137">Standaard verlopen vermeldingen in de lijst Tenant toestaan/blokkeren na 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-137">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="1d6ce-138">U kunt een datum opgeven of instellen dat deze nooit verloopt.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-138">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="1d6ce-139">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-139">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="1d6ce-140">Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-140">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="1d6ce-141">U moet over toegewezen machtigingen beschikken in Exchange Online voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-141">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="1d6ce-142">**URL's, bestanden en bulksgewijs afzenders toestaan:**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-142">**URLs, files, and allow bulk senders**:</span></span>
    - <span data-ttu-id="1d6ce-143">Als u waarden wilt toevoegen en verwijderen uit de lijst Tenant toestaan/blokkeren, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-143">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="1d6ce-144">Voor alleen-lezen toegang tot de tenantlijst toestaan/blokkeren moet  u lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-144">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="1d6ce-145">**Spoofing:** Een van de volgende combinaties:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-145">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="1d6ce-146">**Organisatiebeheer**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-146">**Organization Management**</span></span>
    - <span data-ttu-id="1d6ce-147">**Beveiligingsbeheerder** <u>en</u> **Alleen-weergeven-configuratie** of **Alleen-weergeven organisatiebeheer**.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-147">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="1d6ce-148">Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-148">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="1d6ce-149">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-149">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="1d6ce-150">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-150">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="1d6ce-151">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-151">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1d6ce-152">Gebruik het Beveiligings- & compliancecentrum om URL-items voor blokkering te maken in de lijst Toestaan/blokkeren van tenant</span><span class="sxs-lookup"><span data-stu-id="1d6ce-152">Use the Security & Compliance Center to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="1d6ce-153">Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1d6ce-154">Controleer op de pagina Lijst met **tenants toestaan/blokkeren** of het tabblad **URL's** is geselecteerd en klik vervolgens op **Blokkeren**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-154">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="1d6ce-155">Configureer **de volgende** instellingen in het flyout URL's blokkeren dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-155">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="1d6ce-156">**URL's toevoegen om te blokkeren:** Voer één URL per regel in, maximaal 20.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-156">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="1d6ce-157">Zie de syntaxis van de URL voor de sectie Lijst met tenants [toestaan/blokkeren](#url-syntax-for-the-tenant-allowblock-list) verderop in dit artikel voor meer informatie over de syntaxis van URL-vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-157">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="1d6ce-158">**Nooit verlopen:** Ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-158">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="1d6ce-159">Controleer of de instelling is uitgeschakeld (schakel uit) en gebruik het vak Verloopt aan om de vervaldatum voor de ![ ](../../media/scc-toggle-off.png) vermeldingen op te geven. </span><span class="sxs-lookup"><span data-stu-id="1d6ce-159">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="1d6ce-160">of</span><span class="sxs-lookup"><span data-stu-id="1d6ce-160">or</span></span>

     - <span data-ttu-id="1d6ce-161">Verplaats de schakelknop naar rechts om de items zo te configureren dat ze nooit verlopen:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-161">Move the toggle to the right to configure the entries to never expire:</span></span> ![Inschakelen](../../media/scc-toggle-on.png)<span data-ttu-id="1d6ce-163">.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-163">.</span></span>

   - <span data-ttu-id="1d6ce-164">**Optionele opmerking:** Voer beschrijvende tekst in voor de vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-164">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="1d6ce-165">Wanneer u klaar bent, klikt u op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-165">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1d6ce-166">Gebruik het beveiligings- & compliancecentrum om blokbestandsgegevens te maken in de lijst Toestaan/blokkeren van tenants</span><span class="sxs-lookup"><span data-stu-id="1d6ce-166">Use the Security & Compliance Center to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="1d6ce-167">Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1d6ce-168">Selecteer op de pagina Lijst met  **tenants toestaan/blokkeren** het tabblad Bestanden en klik vervolgens op **Blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-168">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="1d6ce-169">Configureer **de volgende instellingen in het flyout** add files to block flyout that appears:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-169">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="1d6ce-170">**Bestandshashes toevoegen:** Voer één SHA256-hashwaarde per regel in, maximaal 20.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-170">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="1d6ce-171">**Nooit verlopen:** Ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-171">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="1d6ce-172">Controleer of de instelling is uitgeschakeld (schakel uit) en gebruik het vak Verloopt aan om de vervaldatum voor de ![ ](../../media/scc-toggle-off.png) vermeldingen op te geven. </span><span class="sxs-lookup"><span data-stu-id="1d6ce-172">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="1d6ce-173">of</span><span class="sxs-lookup"><span data-stu-id="1d6ce-173">or</span></span>

     - <span data-ttu-id="1d6ce-174">Verplaats de schakelknop naar rechts om de items zo te configureren dat ze nooit verlopen:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-174">Move the toggle to the right to configure the entries to never expire:</span></span> ![Inschakelen](../../media/scc-toggle-on.png)<span data-ttu-id="1d6ce-176">.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-176">.</span></span>

   - <span data-ttu-id="1d6ce-177">**Optionele opmerking:** Voer beschrijvende tekst in voor de vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-177">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="1d6ce-178">Wanneer u klaar bent, klikt u op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-178">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1d6ce-179">Gebruik het Beveiligings- & compliancecentrum om domeingegevens van bulkmails in de lijst Toestaan/blokkeren van tenants toe te staan</span><span class="sxs-lookup"><span data-stu-id="1d6ce-179">Use the Security & Compliance Center to create allow bulk mail sender domain entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="1d6ce-180">Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-180">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1d6ce-181">Selecteer op de pagina Lijst met tenants **toestaan/blokkeren** het tabblad **Afzenderdomeinen voor BCL-bypass** en klik vervolgens op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-181">On the **Tenant Allow/Block List** page, select the **Sender domains for BCL bypass** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="1d6ce-182">Configureer **in het domein Afzender toevoegen voor BCL bypass** flyout dat wordt weergegeven de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-182">In the **Add sender domain for BCL bypass** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="1d6ce-183">**Afzenderdomeinen toevoegen voor BCL-bypass:** Voer één brondomein in met goede bulkmail per regel, maximaal 20.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-183">**Add sender domains for BCL bypass**: Enter one source domain of good bulk mail per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="1d6ce-184">**Nooit verlopen:** Ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-184">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="1d6ce-185">Controleer of de instelling is uitgeschakeld (schakel uit) en gebruik het vak Verloopt aan om de vervaldatum voor de ![ ](../../media/scc-toggle-off.png) vermeldingen op te geven. </span><span class="sxs-lookup"><span data-stu-id="1d6ce-185">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="1d6ce-186">of</span><span class="sxs-lookup"><span data-stu-id="1d6ce-186">or</span></span>

     - <span data-ttu-id="1d6ce-187">Verplaats de schakelknop naar rechts om de items zo te configureren dat ze nooit verlopen:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-187">Move the toggle to the right to configure the entries to never expire:</span></span> ![Inschakelen](../../media/scc-toggle-on.png)<span data-ttu-id="1d6ce-189">.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-189">.</span></span>

4. <span data-ttu-id="1d6ce-190">Wanneer u klaar bent, klikt u op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-190">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1d6ce-191">Gebruik het Beveiligings- & compliancecentrum om vervalste afzenders toe te staan of te blokkeren in de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="1d6ce-191">Use the Security & Compliance Center to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1d6ce-192">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-192">**Notes**:</span></span>

- <span data-ttu-id="1d6ce-193">Alleen de _combinatie_ van de vervalste _gebruiker_ en de verzendende infrastructuur zoals gedefinieerd in het domeinpaar is specifiek toegestaan of geblokkeerd voor spoofing.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-193">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="1d6ce-194">Wanneer u een invoer toestaan of blokkeren configureert voor een domeinpaar, worden berichten van dat domeinpaar niet meer weergegeven in het inzicht van de spoof intelligence.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-194">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="1d6ce-195">Vermeldingen voor vervalste afzenders verlopen nooit.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-195">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="1d6ce-196">Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1d6ce-197">Selecteer op de pagina Lijst met tenants **toestaan/blokkeren** het tabblad **Spoofing** en klik vervolgens op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-197">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="1d6ce-198">Configureer **de volgende** instellingen in het fly-out Nieuwe domeinparen toevoegen dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-198">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="1d6ce-199">**Nieuwe domeinparen toevoegen met jokertekens:** Voer één domeinpaar per regel in, maximaal 20.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-199">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="1d6ce-200">Zie de syntaxis van het domeinpaar voor vervalste afzendergegevens in de sectie [Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) verderop in dit artikel voor meer informatie over de syntaxis van vervalste afzenders.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-200">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="1d6ce-201">**Type spoof:** Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-201">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="1d6ce-202">**Intern:** De vervalste afzender is een domein dat deel uitmaken van uw organisatie (een [geaccepteerd domein).](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="1d6ce-202">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="1d6ce-203">**Extern:** De vervalste afzender is een extern domein.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-203">**External**: The spoofed sender is in an external domain.</span></span>

   - <span data-ttu-id="1d6ce-204">**Actie:** Selecteer **Toestaan** of **Blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-204">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="1d6ce-205">Wanneer u klaar bent, klikt u op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-205">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1d6ce-206">Het beveiligings- & compliancecentrum gebruiken om items in de lijst Tenant toestaan/blokkeren weer te geven</span><span class="sxs-lookup"><span data-stu-id="1d6ce-206">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="1d6ce-207">Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-207">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1d6ce-208">Selecteer het beste tabblad.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-208">Select the tab you want.</span></span> <span data-ttu-id="1d6ce-209">De beschikbare kolommen zijn afhankelijk van het tabblad dat u hebt geselecteerd:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-209">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="1d6ce-210">**URL's**:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-210">**URLs**:</span></span>
     - <span data-ttu-id="1d6ce-211">**Waarde:** De URL.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-211">**Value**: The URL.</span></span>
     - <span data-ttu-id="1d6ce-212">**Actie**: Het **waardeblok**.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-212">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="1d6ce-213">**Laatst bijgewerkte datum**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-213">**Last updated date**</span></span>
     - <span data-ttu-id="1d6ce-214">**Vervaldatum**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-214">**Expiration date**</span></span>
     - <span data-ttu-id="1d6ce-215">**Opmerking**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-215">**Note**</span></span>

   - <span data-ttu-id="1d6ce-216">**Bestanden**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-216">**Files**</span></span>
     - <span data-ttu-id="1d6ce-217">**Waarde:** De bestandshash.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-217">**Value**: The file hash.</span></span>
     - <span data-ttu-id="1d6ce-218">**Actie**: Het **waardeblok**.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-218">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="1d6ce-219">**Laatst bijgewerkte datum**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-219">**Last updated date**</span></span>
     - <span data-ttu-id="1d6ce-220">**Vervaldatum**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-220">**Expiration date**</span></span>
     - <span data-ttu-id="1d6ce-221">**Opmerking**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-221">**Note**</span></span>

   - <span data-ttu-id="1d6ce-222">**Afzenderdomeinen voor BCL-bypass**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-222">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="1d6ce-223">**Waarde:** het domein van de afzender van de bulkmail.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-223">**Value**: The bulk mail sender's domain.</span></span>
     - <span data-ttu-id="1d6ce-224">**Laatst bijgewerkte datum**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-224">**Last updated date**</span></span>
     - <span data-ttu-id="1d6ce-225">**Vervaldatum**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-225">**Expiration date**</span></span>

   - <span data-ttu-id="1d6ce-226">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-226">**Spoofing**</span></span>
     - <span data-ttu-id="1d6ce-227">**Vervalste gebruiker**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-227">**Spoofed user**</span></span>
     - <span data-ttu-id="1d6ce-228">**Verzendende infrastructuur**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-228">**Sending infrastructure**</span></span>
     - <span data-ttu-id="1d6ce-229">**Spooftype:** De waarde **Intern** of **Extern**.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-229">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="1d6ce-230">**Actie:** De waarde **Blokkeren of** **Toestaan.**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-230">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="1d6ce-231">U kunt op een kolomkoppen klikken om in oplopende of aflopende volgorde te sorteren.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-231">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="1d6ce-232">U kunt klikken op **Groep om** de resultaten te groepen.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-232">You can click **Group** to group the results.</span></span> <span data-ttu-id="1d6ce-233">De waarden die beschikbaar zijn, zijn afhankelijk van het tabblad dat u hebt geselecteerd:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-233">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="1d6ce-234">**URL's:** U kunt de resultaten groepen op **Actie.**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-234">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="1d6ce-235">**Bestanden:** U kunt de resultaten groepren op **Actie.**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-235">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="1d6ce-236">**Afzenderdomeinen voor BCL-bypass:** **Groep** is niet beschikbaar op dit tabblad.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-236">**Sender domains for BCL bypass**: **Group** is not available on this tab.</span></span>
   - <span data-ttu-id="1d6ce-237">**Spoofing:** U kunt de resultaten groeperen op **Actie** of **Spooftype.**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-237">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="1d6ce-238">Klik **op Zoeken,** voer een hele of een deel van een waarde in en druk vervolgens op Enter om een specifieke waarde te zoeken.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-238">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="1d6ce-239">Wanneer u klaar bent, klikt u op **Zoek verwijderen Zoekpictogram** ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) verwijderen.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-239">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

   <span data-ttu-id="1d6ce-240">Klik **op Filteren** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-240">Click **Filter** to filter the results.</span></span> <span data-ttu-id="1d6ce-241">De waarden die beschikbaar zijn in **de flyout Filter** die wordt weergegeven, zijn afhankelijk van het tabblad dat u hebt geselecteerd:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-241">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="1d6ce-242">**URL's**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-242">**URLs**</span></span>
     - <span data-ttu-id="1d6ce-243">**Actie**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-243">**Action**</span></span>
     - <span data-ttu-id="1d6ce-244">**Nooit verlopen**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-244">**Never expire**</span></span>
     - <span data-ttu-id="1d6ce-245">**Laatst bijgewerkte datum**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-245">**Last updated date**</span></span>
     - <span data-ttu-id="1d6ce-246">**Vervaldatum**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-246">**Expiration date**</span></span>

   - <span data-ttu-id="1d6ce-247">**Bestanden**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-247">**Files**</span></span>
     - <span data-ttu-id="1d6ce-248">**Actie**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-248">**Action**</span></span>
     - <span data-ttu-id="1d6ce-249">**Nooit verlopen**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-249">**Never expire**</span></span>
     - <span data-ttu-id="1d6ce-250">**Laatst bijgewerkte datum**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-250">**Last updated date**</span></span>
     - <span data-ttu-id="1d6ce-251">**Vervaldatum**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-251">**Expiration date**</span></span>

   - <span data-ttu-id="1d6ce-252">**Afzenderdomeinen voor BCL-bypass**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-252">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="1d6ce-253">**Nooit verlopen**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-253">**Never expire**</span></span>
     - <span data-ttu-id="1d6ce-254">**Laatst bijgewerkte datum**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-254">**Last updated date**</span></span>
     - <span data-ttu-id="1d6ce-255">**Vervaldatum**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-255">**Expiration date**</span></span>

   - <span data-ttu-id="1d6ce-256">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-256">**Spoofing**</span></span>
     - <span data-ttu-id="1d6ce-257">**Actie**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-257">**Action**</span></span>
     - <span data-ttu-id="1d6ce-258">**Spooftype**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-258">**Spoof type**</span></span>

   <span data-ttu-id="1d6ce-259">Wanneer u klaar bent, klikt u op **Toepassen.**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-259">When you're finished, click **Apply**.</span></span> <span data-ttu-id="1d6ce-260">Als u bestaande filters wilt wissen, klikt u **op Filter** en klikt u in het **fly-out** Filter dat wordt weergegeven op Filters **wissen.**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-260">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1d6ce-261">Gebruik het beveiligings- & compliancecentrum om items in de lijst Tenant Allow/Block te wijzigen</span><span class="sxs-lookup"><span data-stu-id="1d6ce-261">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="1d6ce-262">Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-262">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1d6ce-263">Selecteer het tabblad met het type vermelding dat u wilt wijzigen:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-263">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="1d6ce-264">**URL's**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-264">**URLs**</span></span>
   - <span data-ttu-id="1d6ce-265">**Bestanden**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-265">**Files**</span></span>
   - <span data-ttu-id="1d6ce-266">**Afzenderdomeinen voor BCL-bypass**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-266">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="1d6ce-267">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-267">**Spoofing**</span></span>

3. <span data-ttu-id="1d6ce-268">Selecteer het item dat u wilt wijzigen en klik vervolgens op **Pictogram** ![ Bewerken ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) bewerken.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-268">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span> <span data-ttu-id="1d6ce-269">De waarden die u kunt wijzigen in het flyout dat wordt weergegeven, zijn afhankelijk van het tabblad dat u in de vorige stap hebt geselecteerd:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-269">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>

   - <span data-ttu-id="1d6ce-270">**URL's**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-270">**URLs**</span></span>
     - <span data-ttu-id="1d6ce-271">**Nooit verlopen** en/of vervaldatum.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-271">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="1d6ce-272">**Optionele notitie**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-272">**Optional note**</span></span>

   - <span data-ttu-id="1d6ce-273">**Bestanden**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-273">**Files**</span></span>
     - <span data-ttu-id="1d6ce-274">**Nooit verlopen** en/of vervaldatum.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-274">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="1d6ce-275">**Optionele notitie**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-275">**Optional note**</span></span>

   - <span data-ttu-id="1d6ce-276">**Afzenderdomeinen voor BCL-bypass**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-276">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="1d6ce-277">**Nooit verlopen** en/of vervaldatum.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-277">**Never expire** and/or expiration date.</span></span>

   - <span data-ttu-id="1d6ce-278">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-278">**Spoofing**</span></span>
     - <span data-ttu-id="1d6ce-279">**Actie:** U kunt de waarde wijzigen in **Toestaan** of **Blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-279">**Action**: You can change the value to **Allow** or **Block**.</span></span>

4. <span data-ttu-id="1d6ce-280">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-280">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="1d6ce-281">Gebruik het beveiligings- & compliancecentrum om items te verwijderen uit de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="1d6ce-281">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="1d6ce-282">Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-282">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1d6ce-283">Selecteer het tabblad met het type invoer dat u wilt verwijderen:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-283">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="1d6ce-284">**URL's**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-284">**URLs**</span></span>
   - <span data-ttu-id="1d6ce-285">**Bestanden**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-285">**Files**</span></span>
   - <span data-ttu-id="1d6ce-286">**Afzenderdomeinen voor BCL-bypass**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-286">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="1d6ce-287">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-287">**Spoofing**</span></span>

3. <span data-ttu-id="1d6ce-288">Selecteer het item dat u wilt verwijderen en klik vervolgens op **Pictogram** ![ Verwijderen ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) verwijderen.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-288">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="1d6ce-289">Klik in het waarschuwingsvenster dat wordt weergegeven op **Verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-289">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="1d6ce-290">Gebruik Exchange Online PowerShell of zelfstandige EOP PowerShell om de lijst met tenants toestaan/blokkeren te configureren</span><span class="sxs-lookup"><span data-stu-id="1d6ce-290">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="1d6ce-291">PowerShell gebruiken om blokbestands- of URL-vermeldingen toe te voegen aan de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="1d6ce-291">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="1d6ce-292">Gebruik de volgende syntaxis om blokbestands- of URL-vermeldingen toe te voegen aan de lijst Tenant toestaan/blokkeren:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-292">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="1d6ce-293">In dit voorbeeld wordt een blokbestandsinvoer toegevoegd voor de opgegeven bestanden die nooit verlopen.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-293">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="1d6ce-294">In dit voorbeeld wordt een blok-URL-vermelding voor contoso.com en alle subdomeinen (bijvoorbeeld contoso.com, www.contoso.com en xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="1d6ce-294">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="1d6ce-295">Omdat we de parameters Vervaldatum of NoExpiration niet hebben gebruikt, verloopt de vermelding na 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-295">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="1d6ce-296">Zie [New-TenantAllowBlockListItems voor](/powershell/module/exchange/new-tenantallowblocklistitems)gedetailleerde syntaxis en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-296">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-bulk-mail-sender-domain-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="1d6ce-297">PowerShell gebruiken om domeingegevens van bulkmail afzender toe te voegen aan de tenantlijst toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="1d6ce-297">Use PowerShell to add allow bulk mail sender domain entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="1d6ce-298">Gebruik de volgende syntaxis om domeingegevens van bulkmail afzender toe te voegen in de lijst Tenant Allow/Block:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-298">To add allow bulk mail sender domain entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType BulkSender -Block:$false -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="1d6ce-299">In dit voorbeeld wordt een toegestane bulkinvoer voor afzenders toegevoegd voor het opgegeven domein dat nooit verloopt.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-299">This example adds an allowed bulk sender entry for the specified domain that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType BulkSender -Block:$false -Entries contosodailydeals.com
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="1d6ce-300">Zie [New-TenantAllowBlockListItems voor](/powershell/module/exchange/new-tenantallowblocklistitems)gedetailleerde syntaxis en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-300">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="1d6ce-301">PowerShell gebruiken om vervalste afzendergegevens toe te voegen of te blokkeren aan de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="1d6ce-301">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="1d6ce-302">Gebruik de volgende syntaxis om vervalste afzendergegevens toe te voegen aan de lijst Tenant Allow/Block:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-302">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="1d6ce-303">Zie [New-TenantAllowBlockListSpoofItems voor](/powershell/module/exchange/new-tenantallowblocklistspoofitems)gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-303">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1d6ce-304">PowerShell gebruiken om blokbestands- of URL-items weer te geven in de lijst Tenant Allow/Block</span><span class="sxs-lookup"><span data-stu-id="1d6ce-304">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1d6ce-305">Als u blokbestands- of URL-vermeldingen wilt weergeven in de lijst Tenant toestaan/blokkeren, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-305">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="1d6ce-306">In dit voorbeeld worden gegevens voor de opgegeven waarde voor bestandshash als resultaat gegeven.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-306">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="1d6ce-307">In dit voorbeeld worden alle geblokkeerde URL's als retourneert.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-307">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="1d6ce-308">Zie [Get-TenantAllowBlockListItems voor](/powershell/module/exchange/get-tenantallowblocklistitems)gedetailleerde syntaxis en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-308">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1d6ce-309">PowerShell gebruiken om domeingegevens van bulkmail afzenders weer te geven in de lijst Tenant Allow/Block</span><span class="sxs-lookup"><span data-stu-id="1d6ce-309">Use PowerShell to view allow bulk mail sender domain entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1d6ce-310">Gebruik de volgende syntaxis als u domeingegevens van bulkmail afzenders wilt weergeven in de lijst Tenant Allow/Block:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-310">To view allow bulk mail sender domain entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender [-Entry <BulkSenderDomainValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="1d6ce-311">In dit voorbeeld worden alle toegestane domeinen voor bulkmail afzenders als retourneert.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-311">This example returns all allowed bulk mail sender domains.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender
```

<span data-ttu-id="1d6ce-312">In dit voorbeeld worden gegevens voor het opgegeven domein voor bulksgewijs afzenders als retourneert.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-312">This example returns information for the specified bulk sender domain.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "contosodailydeals.com"
```

<span data-ttu-id="1d6ce-313">Zie [Get-TenantAllowBlockListItems voor](/powershell/module/exchange/get-tenantallowblocklistitems)gedetailleerde syntaxis en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-313">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1d6ce-314">PowerShell gebruiken om vervalste afzenders toe te staan of te blokkeren in de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="1d6ce-314">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1d6ce-315">Gebruik de volgende syntaxis om vervalste afzendergegevens weer te geven in de lijst Tenant Allow/Block:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-315">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="1d6ce-316">Dit voorbeeld retourneert alle vervalste afzendergegevens in de lijst Tenant toestaan/blokkeren.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-316">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="1d6ce-317">Dit voorbeeld retourneert alle toegestane vermeldingen van vervalste afzenders die intern zijn.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-317">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="1d6ce-318">In dit voorbeeld worden alle geblokkeerde vermeldingen van vervalste afzenders die extern zijn, als retourneert.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-318">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="1d6ce-319">Zie [Get-TenantAllowBlockListSpoofItems (Get-TenantAllowBlockListSpoofItems)](/powershell/module/exchange/get-tenantallowblocklistspoofitems)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-319">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1d6ce-320">PowerShell gebruiken om blokbestands- en URL-items in de lijst Tenant allow/block te wijzigen</span><span class="sxs-lookup"><span data-stu-id="1d6ce-320">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1d6ce-321">Gebruik de volgende syntaxis om blokbestands- en URL-vermeldingen in de lijst Tenant toestaan/blokkeren te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-321">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="1d6ce-322">In dit voorbeeld wordt de vervaldatum van de opgegeven blok-URL-vermelding gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-322">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="1d6ce-323">Zie [Set-TenantAllowBlockListItems (Set-TenantAllowBlockListItems)](/powershell/module/exchange/set-tenantallowblocklistitems)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-323">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1d6ce-324">PowerShell gebruiken om domeingegevens van bulkmail afzenders toe te staan in de lijst Tenant Allow/Block</span><span class="sxs-lookup"><span data-stu-id="1d6ce-324">Use PowerShell to modify allow bulk mail sender domain entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1d6ce-325">Gebruik de volgende syntaxis om domeingegevens van bulkmail afzender toe te staan in de lijst Tenant Allow/Block:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-325">To modify allow bulk mail sender domain entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="1d6ce-326">In dit voorbeeld wordt de vervaldatum van de opgegeven domeininvoer voor bulkmail afzenders nooit verlopen.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-326">This example changes the expiration of the specified allow bulk mail sender domain entry to never expire.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType BulkSender -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -NoExpiration
```

<span data-ttu-id="1d6ce-327">Zie [Get-TenantAllowBlockListItems voor](/powershell/module/exchange/get-tenantallowblocklistitems)gedetailleerde syntaxis en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-327">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1d6ce-328">PowerShell gebruiken om vervalste afzenders toe te staan of te blokkeren in de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="1d6ce-328">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1d6ce-329">Gebruik de volgende syntaxis om vervalste afzendergegevens in de lijst Tenant Allow/Block te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-329">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="1d6ce-330">In dit voorbeeld wordt de vermelding van vervalste afzenders gewijzigd in toestaan om te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-330">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="1d6ce-331">Zie [Set-TenantAllowBlockListSpoofItems (Set-TenantAllowBlockListSpoofItems)](/powershell/module/exchange/set-tenantallowblocklistspoofitems)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-331">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-bulk-mail-sender-domain-file-and-domain-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="1d6ce-332">PowerShell gebruiken om domein, bestands- en domeingegevens voor bulksgewijs verzenden van e-mail te verwijderen uit de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="1d6ce-332">Use PowerShell to remove bulk mail sender domain, file, and domain entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="1d6ce-333">Gebruik de volgende syntaxis als u domeingegevens voor bulksgewijs verzenden van e-mail wilt verwijderen, bestandsgegevens wilt blokkeren en URL-items wilt blokkeren uit de lijst Tenant toestaan/blokkeren:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-333">To remove allow bulk mail sender domain entries, block file entries, and block URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <BulkSender | FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="1d6ce-334">In dit voorbeeld wordt de opgegeven blok-URL-vermelding verwijderd uit de lijst Tenant toestaan/blokkeren.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-334">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="1d6ce-335">Zie [Remove-TenantAllowBlockListItems (Verwijderen-TenantAllowBlockListItems)](/powershell/module/exchange/remove-tenantallowblocklistitems)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-335">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="1d6ce-336">PowerShell gebruiken om vervalste afzenders toe te staan of te blokkeren uit de tenantlijst toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="1d6ce-336">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="1d6ce-337">Gebruik de volgende syntaxis als u spoofing sender items wilt verwijderen uit de tenant allow/block list:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-337">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="1d6ce-338">Zie [Remove-TenantAllowBlockListSpoofItems (Verwijderen-TenantAllowBlockListSpoofItems)](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-338">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="1d6ce-339">URL-syntaxis voor de lijst Toestaan/blokkeren van tenant</span><span class="sxs-lookup"><span data-stu-id="1d6ce-339">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="1d6ce-340">IP4v- en IPv6-adressen zijn toegestaan, maar TCP/UDP-poorten niet.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-340">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="1d6ce-341">Bestandsnaamextensies zijn niet toegestaan (bijvoorbeeld test.pdf).</span><span class="sxs-lookup"><span data-stu-id="1d6ce-341">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="1d6ce-342">Unicode wordt niet ondersteund, maar Punycode wel.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-342">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="1d6ce-343">Hostnamen zijn toegestaan als alle volgende instructies waar zijn:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-343">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="1d6ce-344">De hostnaam bevat een punt.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-344">The hostname contains a period.</span></span>
  - <span data-ttu-id="1d6ce-345">Er is ten minste één teken links van de periode.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-345">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="1d6ce-346">Er zijn ten minste twee tekens rechts van de periode.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-346">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="1d6ce-347">Is bijvoorbeeld `t.co` toegestaan of `.com` niet `contoso.` toegestaan.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-347">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="1d6ce-348">Subpathen worden niet geïmpliceerd.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-348">Subpaths are not implied.</span></span>

  <span data-ttu-id="1d6ce-349">Bevat bijvoorbeeld `contoso.com` geen `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="1d6ce-349">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="1d6ce-350">Jokertekens (\*) zijn toegestaan in de volgende scenario's:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-350">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="1d6ce-351">Een linker jokerteken moet worden gevolgd door een punt om een subdomein op te geven.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-351">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="1d6ce-352">Is bijvoorbeeld `*.contoso.com` toegestaan; `*contoso.com` is niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-352">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="1d6ce-353">Een jokerteken rechts moet een slash (/) volgen om een pad op te geven.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-353">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="1d6ce-354">Is bijvoorbeeld `contoso.com/*` toegestaan of `contoso.com*` niet `contoso.com/ab*` toegestaan.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-354">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="1d6ce-355">Alle subpathen worden niet geïmpliceerd door een rechter jokerteken.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-355">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="1d6ce-356">Bevat bijvoorbeeld `contoso.com/*` geen `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="1d6ce-356">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="1d6ce-357">`*.com*` ongeldig is (geen op te lossen domein en het jokerteken rechts volgt geen slash voor vooruit).</span><span class="sxs-lookup"><span data-stu-id="1d6ce-357">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="1d6ce-358">Jokertekens zijn niet toegestaan in IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-358">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="1d6ce-359">Het tildeteken (~) is beschikbaar in de volgende scenario's:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-359">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="1d6ce-360">Een linker tilde houdt een domein en alle subdomeinen in.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-360">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="1d6ce-361">Bijvoorbeeld inclusief `~contoso.com` `contoso.com` en `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="1d6ce-361">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="1d6ce-362">URL-vermeldingen die protocollen bevatten (bijvoorbeeld , of ) mislukken, omdat URL-vermeldingen van toepassing zijn `http://` `https://` op alle `ftp://` protocollen.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-362">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="1d6ce-363">Een gebruikersnaam of wachtwoord wordt niet ondersteund of vereist.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-363">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="1d6ce-364">Aanhalingstekens (' of ") zijn ongeldige tekens.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-364">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="1d6ce-365">Een URL moet waar mogelijk alle omleidingen bevatten.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-365">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="1d6ce-366">Scenario's voor URL-invoer</span><span class="sxs-lookup"><span data-stu-id="1d6ce-366">URL entry scenarios</span></span>

<span data-ttu-id="1d6ce-367">Geldige URL-vermeldingen en de resultaten worden beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-367">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="1d6ce-368">Scenario: Geen jokertekens</span><span class="sxs-lookup"><span data-stu-id="1d6ce-368">Scenario: No wildcards</span></span>

<span data-ttu-id="1d6ce-369">**Vermelding**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="1d6ce-369">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="1d6ce-370">**Overeenkomst toestaan**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-370">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="1d6ce-371">**Niet-overeenkomende toestaan:**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-371">**Allow not matched**:</span></span>

  - <span data-ttu-id="1d6ce-372">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-372">abc-contoso.com</span></span>
  - <span data-ttu-id="1d6ce-373">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1d6ce-373">contoso.com/a</span></span>
  - <span data-ttu-id="1d6ce-374">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-374">payroll.contoso.com</span></span>
  - <span data-ttu-id="1d6ce-375">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-375">test.com/contoso.com</span></span>
  - <span data-ttu-id="1d6ce-376">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-376">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="1d6ce-377">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-377">www.contoso.com</span></span>
  - <span data-ttu-id="1d6ce-378">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-378">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="1d6ce-379">**Blok overeenkomst**:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-379">**Block match**:</span></span>

  - <span data-ttu-id="1d6ce-380">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-380">contoso.com</span></span>
  - <span data-ttu-id="1d6ce-381">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1d6ce-381">contoso.com/a</span></span>
  - <span data-ttu-id="1d6ce-382">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-382">payroll.contoso.com</span></span>
  - <span data-ttu-id="1d6ce-383">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-383">test.com/contoso.com</span></span>
  - <span data-ttu-id="1d6ce-384">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-384">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="1d6ce-385">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-385">www.contoso.com</span></span>
  - <span data-ttu-id="1d6ce-386">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-386">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="1d6ce-387">**Blok niet overeenkomend**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-387">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="1d6ce-388">Scenario: Jokerteken links (subdomein)</span><span class="sxs-lookup"><span data-stu-id="1d6ce-388">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="1d6ce-389">**Vermelding**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="1d6ce-389">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="1d6ce-390">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-390">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1d6ce-391">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-391">www.contoso.com</span></span>
  - <span data-ttu-id="1d6ce-392">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-392">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="1d6ce-393">**Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-393">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="1d6ce-394">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-394">123contoso.com</span></span>
  - <span data-ttu-id="1d6ce-395">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-395">contoso.com</span></span>
  - <span data-ttu-id="1d6ce-396">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-396">test.com/contoso.com</span></span>
  - <span data-ttu-id="1d6ce-397">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="1d6ce-397">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="1d6ce-398">Scenario: Jokerteken rechts boven aan pad</span><span class="sxs-lookup"><span data-stu-id="1d6ce-398">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="1d6ce-399">**Vermelding**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="1d6ce-399">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="1d6ce-400">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-400">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1d6ce-401">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="1d6ce-401">contoso.com/a/b</span></span>
  - <span data-ttu-id="1d6ce-402">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="1d6ce-402">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="1d6ce-403">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-403">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="1d6ce-404">**Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-404">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="1d6ce-405">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-405">contoso.com</span></span>
  - <span data-ttu-id="1d6ce-406">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1d6ce-406">contoso.com/a</span></span>
  - <span data-ttu-id="1d6ce-407">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-407">www.contoso.com</span></span>
  - <span data-ttu-id="1d6ce-408">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-408">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="1d6ce-409">Scenario: Tilde links</span><span class="sxs-lookup"><span data-stu-id="1d6ce-409">Scenario: Left tilde</span></span>

<span data-ttu-id="1d6ce-410">**Vermelding**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="1d6ce-410">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="1d6ce-411">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-411">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1d6ce-412">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-412">contoso.com</span></span>
  - <span data-ttu-id="1d6ce-413">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-413">www.contoso.com</span></span>
  - <span data-ttu-id="1d6ce-414">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-414">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="1d6ce-415">**Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-415">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="1d6ce-416">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-416">123contoso.com</span></span>
  - <span data-ttu-id="1d6ce-417">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="1d6ce-417">contoso.com/abc</span></span>
  - <span data-ttu-id="1d6ce-418">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="1d6ce-418">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="1d6ce-419">Scenario: Het achtervoegsel van het jokerteken rechts</span><span class="sxs-lookup"><span data-stu-id="1d6ce-419">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="1d6ce-420">**Vermelding**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="1d6ce-420">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="1d6ce-421">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-421">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1d6ce-422">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-422">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="1d6ce-423">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1d6ce-423">contoso.com/a</span></span>
  - <span data-ttu-id="1d6ce-424">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="1d6ce-424">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="1d6ce-425">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="1d6ce-425">contoso.com/ab</span></span>
  - <span data-ttu-id="1d6ce-426">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="1d6ce-426">contoso.com/b</span></span>
  - <span data-ttu-id="1d6ce-427">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="1d6ce-427">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="1d6ce-428">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="1d6ce-428">contoso.com/ba</span></span>

- <span data-ttu-id="1d6ce-429">**Niet-overeenkomende en** **niet-overeenkomende** blokkering toestaan: contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-429">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="1d6ce-430">Scenario: Linker jokertekensubdomein en rechterachtervoegsel jokerteken</span><span class="sxs-lookup"><span data-stu-id="1d6ce-430">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="1d6ce-431">**Vermelding**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="1d6ce-431">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="1d6ce-432">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-432">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1d6ce-433">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="1d6ce-433">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="1d6ce-434">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="1d6ce-434">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="1d6ce-435">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1d6ce-435">www.contoso.com/a</span></span>
  - <span data-ttu-id="1d6ce-436">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="1d6ce-436">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="1d6ce-437">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="1d6ce-437">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="1d6ce-438">**Niet-overeenkomende en** **niet-overeenkomende** blokkering toestaan : contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="1d6ce-438">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="1d6ce-439">Scenario: Tilde links en rechts</span><span class="sxs-lookup"><span data-stu-id="1d6ce-439">Scenario: Left and right tilde</span></span>

<span data-ttu-id="1d6ce-440">**Vermelding**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="1d6ce-440">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="1d6ce-441">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-441">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1d6ce-442">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-442">contoso.com</span></span>
  - <span data-ttu-id="1d6ce-443">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1d6ce-443">contoso.com/a</span></span>
  - <span data-ttu-id="1d6ce-444">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-444">www.contoso.com</span></span>
  - <span data-ttu-id="1d6ce-445">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="1d6ce-445">www.contoso.com/b</span></span>
  - <span data-ttu-id="1d6ce-446">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-446">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="1d6ce-447">**Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-447">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="1d6ce-448">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-448">123contoso.com</span></span>
  - <span data-ttu-id="1d6ce-449">contoso.org</span><span class="sxs-lookup"><span data-stu-id="1d6ce-449">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="1d6ce-450">Scenario: IP-adres</span><span class="sxs-lookup"><span data-stu-id="1d6ce-450">Scenario: IP address</span></span>

<span data-ttu-id="1d6ce-451">**Vermelding**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="1d6ce-451">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="1d6ce-452">**Overeenkomst toestaan** **en overeenkomst blokkeren**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="1d6ce-452">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="1d6ce-453">**Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-453">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="1d6ce-454">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="1d6ce-454">1.2.3.4/a</span></span>
  - <span data-ttu-id="1d6ce-455">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="1d6ce-455">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="1d6ce-456">IP-adres met jokerteken rechts</span><span class="sxs-lookup"><span data-stu-id="1d6ce-456">IP address with right wildcard</span></span>

<span data-ttu-id="1d6ce-457">**Vermelding**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="1d6ce-457">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="1d6ce-458">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-458">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1d6ce-459">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="1d6ce-459">1.2.3.4/b</span></span>
  - <span data-ttu-id="1d6ce-460">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="1d6ce-460">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="1d6ce-461">Voorbeelden van ongeldige vermeldingen</span><span class="sxs-lookup"><span data-stu-id="1d6ce-461">Examples of invalid entries</span></span>

<span data-ttu-id="1d6ce-462">De volgende vermeldingen zijn ongeldig:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-462">The following entries are invalid:</span></span>

- <span data-ttu-id="1d6ce-463">**Ontbrekende of ongeldige domeinwaarden:**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-463">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="1d6ce-464">contoso</span><span class="sxs-lookup"><span data-stu-id="1d6ce-464">contoso</span></span>
  - <span data-ttu-id="1d6ce-465">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="1d6ce-465">\*.contoso.\*</span></span>
  - <span data-ttu-id="1d6ce-466">\*.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-466">\*.com</span></span>
  - <span data-ttu-id="1d6ce-467">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="1d6ce-467">\*.pdf</span></span>

- <span data-ttu-id="1d6ce-468">**Jokerteken op tekst of zonder spatiëringstekens:**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-468">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="1d6ce-469">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-469">\*contoso.com</span></span>
  - <span data-ttu-id="1d6ce-470">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="1d6ce-470">contoso.com\*</span></span>
  - <span data-ttu-id="1d6ce-471">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="1d6ce-471">\*1.2.3.4</span></span>
  - <span data-ttu-id="1d6ce-472">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="1d6ce-472">1.2.3.4\*</span></span>
  - <span data-ttu-id="1d6ce-473">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="1d6ce-473">contoso.com/a\*</span></span>
  - <span data-ttu-id="1d6ce-474">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="1d6ce-474">contoso.com/ab\*</span></span>

- <span data-ttu-id="1d6ce-475">**IP-adressen met poorten:**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-475">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="1d6ce-476">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="1d6ce-476">contoso.com:443</span></span>
  - <span data-ttu-id="1d6ce-477">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="1d6ce-477">abc.contoso.com:25</span></span>

- <span data-ttu-id="1d6ce-478">**Niet-beschrijvende jokertekens:**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-478">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="1d6ce-479">\*.\*</span><span class="sxs-lookup"><span data-stu-id="1d6ce-479">\*.\*</span></span>

- <span data-ttu-id="1d6ce-480">**Middelste jokertekens:**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-480">**Middle wildcards**:</span></span>

  - <span data-ttu-id="1d6ce-481">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-481">conto\*so.com</span></span>
  - <span data-ttu-id="1d6ce-482">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-482">conto~so.com</span></span>

- <span data-ttu-id="1d6ce-483">**Dubbele jokertekens**</span><span class="sxs-lookup"><span data-stu-id="1d6ce-483">**Double wildcards**</span></span>

  - <span data-ttu-id="1d6ce-484">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="1d6ce-484">contoso.com/\*\*</span></span>
  - <span data-ttu-id="1d6ce-485">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="1d6ce-485">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1d6ce-486">Syntaxis van domeinparen voor vervalste afzendergegevens in de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="1d6ce-486">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1d6ce-487">Een domeinpaar voor een vervalste afzender in de lijst Tenant toestaan/blokkeren gebruikt de volgende syntaxis: `<Spoofed user>, <Sending infrastructure>` .</span><span class="sxs-lookup"><span data-stu-id="1d6ce-487">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="1d6ce-488">**Vervalste gebruiker:** Deze waarde betreft het e-mailadres van de vervalste gebruiker die wordt weergegeven in het vak **Van** in e-mail clients.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-488">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="1d6ce-489">Dit adres wordt ook wel het adres `5322.From` genoemd.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-489">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="1d6ce-490">Geldige waarden zijn:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-490">Valid values include:</span></span>
  - <span data-ttu-id="1d6ce-491">Een afzonderlijk e-mailadres (bijvoorbeeld chris@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="1d6ce-491">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="1d6ce-492">Een e-maildomein (bijvoorbeeld contoso.com).</span><span class="sxs-lookup"><span data-stu-id="1d6ce-492">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="1d6ce-493">Het jokerteken \* (bijvoorbeeld).</span><span class="sxs-lookup"><span data-stu-id="1d6ce-493">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="1d6ce-494">**Verzendende infrastructuur:** deze waarde geeft de bron aan van berichten van de vervalste gebruiker.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-494">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="1d6ce-495">Geldige waarden zijn:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-495">Valid values include:</span></span>
  - <span data-ttu-id="1d6ce-496">Het domein dat is gevonden in een REVERSE DNS lookup (PTR-record) van het IP-adres van de bron-e-mailserver (bijvoorbeeld fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="1d6ce-496">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="1d6ce-497">Als het bron-IP-adres geen PTR-record heeft, wordt de verzendende infrastructuur geïdentificeerd als \<source IP\> /24 (bijvoorbeeld 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="1d6ce-497">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="1d6ce-498">Hier zijn enkele voorbeelden van geldige domeinparen om vervalste afzenders te identificeren:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-498">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="1d6ce-499">Als u een domeinpaar toevoegt, wordt  de *combinatie* van de vervalste gebruiker en de verzendende infrastructuur alleen mogelijk of blokkeert.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-499">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="1d6ce-500">E-mail van de vervalste gebruiker van welke bron dan ook is niet toegestaan en e-mail uit de bron van de verzendende infrastructuur wordt niet toegestaan voor vervalste gebruikers.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-500">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span>

<span data-ttu-id="1d6ce-501">U voegt bijvoorbeeld een toegestane vermelding toe voor het volgende domeinpaar:</span><span class="sxs-lookup"><span data-stu-id="1d6ce-501">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="1d6ce-502">**Domein:** gmail.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-502">**Domain**: gmail.com</span></span>
- <span data-ttu-id="1d6ce-503">**Infrastructuur**: tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="1d6ce-503">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="1d6ce-504">Alleen berichten uit dat domein *en het* verzenden van infrastructuurparen mogen spoofen.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-504">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="1d6ce-505">Andere afzenders die proberen te spoofen gmail.com zijn niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-505">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="1d6ce-506">Berichten van afzenders in andere domeinen die afkomstig zijn van tms.mx.com worden gecontroleerd door spoof intelligence.</span><span class="sxs-lookup"><span data-stu-id="1d6ce-506">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
