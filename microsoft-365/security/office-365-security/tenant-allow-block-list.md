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
ms.openlocfilehash: 12139708fc5cde133819713fd7185435e594a1a9
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809177"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="12dc2-103">Tenant Toestaan/Blokkeren-lijst beheren</span><span class="sxs-lookup"><span data-stu-id="12dc2-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="12dc2-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="12dc2-104">**Applies to**</span></span>
- [<span data-ttu-id="12dc2-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="12dc2-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="12dc2-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="12dc2-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="12dc2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="12dc2-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="12dc2-108">De functies die in dit artikel worden beschreven, zijn in Preview, kunnen worden gewijzigd en zijn niet beschikbaar in alle organisaties.</span><span class="sxs-lookup"><span data-stu-id="12dc2-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="12dc2-109">Als uw organisatie niet beschikt over de spooffuncties zoals beschreven in dit artikel, bekijkt u de oudere spoofbeheerervaring bij Vervalste afzenders beheren met behulp van het spoof intelligence-beleid en het inzicht in spoof [intelligence in EOP.](walkthrough-spoof-intelligence-insight.md)</span><span class="sxs-lookup"><span data-stu-id="12dc2-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="12dc2-110">U kunt op dit **moment geen** toegestane URL- of bestandsitems configureren in de lijst Tenant toestaan/blokkeren.</span><span class="sxs-lookup"><span data-stu-id="12dc2-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="12dc2-111">In Microsoft 365 organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken, kunt u het niet eens zijn met de uitspraak over EOP-filtering.</span><span class="sxs-lookup"><span data-stu-id="12dc2-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="12dc2-112">Een goed bericht kan bijvoorbeeld worden gemarkeerd als slecht (een onwaar positief) of een slecht bericht kan worden toegestaan (een onwaar negatief).</span><span class="sxs-lookup"><span data-stu-id="12dc2-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="12dc2-113">Met de tenantlijst Toestaan/blokkeren in het Beveiligings- & Compliancecentrum kunt u handmatig de regels voor filteren Microsoft 365 overschrijven.</span><span class="sxs-lookup"><span data-stu-id="12dc2-113">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="12dc2-114">De lijst Tenant toestaan/blokkeren wordt gebruikt tijdens de e-mailstroom en op het moment dat de gebruiker klikt.</span><span class="sxs-lookup"><span data-stu-id="12dc2-114">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="12dc2-115">U kunt de volgende typen overschrijven opgeven:</span><span class="sxs-lookup"><span data-stu-id="12dc2-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="12dc2-116">URL's die u wilt blokkeren.</span><span class="sxs-lookup"><span data-stu-id="12dc2-116">URLs to block.</span></span>
- <span data-ttu-id="12dc2-117">Bestanden die u wilt blokkeren.</span><span class="sxs-lookup"><span data-stu-id="12dc2-117">Files to block.</span></span>
- <span data-ttu-id="12dc2-118">Vervalste afzenders om dit toe te staan of te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="12dc2-118">Spoofed senders to allow or block.</span></span> <span data-ttu-id="12dc2-119">Als u de uitspraak toestaan of blokkeren overschrijven in het inzicht van spoof [intelligence,](learn-about-spoof-intelligence.md)wordt de vervalste afzender een handmatige invoer toestaan of blokkeren die alleen wordt weergegeven op het tabblad **Spoof** in de lijst Toestaan/blokkeren van tenants.</span><span class="sxs-lookup"><span data-stu-id="12dc2-119">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="12dc2-120">U kunt hier ook handmatig vermeldingen voor vervalste afzenders maken of blokkeren voordat ze worden gedetecteerd door spoofinformatie.</span><span class="sxs-lookup"><span data-stu-id="12dc2-120">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="12dc2-121">In dit artikel wordt beschreven hoe u vermeldingen configureert in de lijst Tenant toestaan/blokkeren in het Beveiligings- & Compliancecentrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).</span><span class="sxs-lookup"><span data-stu-id="12dc2-121">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="12dc2-122">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="12dc2-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="12dc2-123">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="12dc2-123">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="12dc2-124">Als u rechtstreeks naar de **pagina Lijst met tenants toestaan/blokkeren wilt** gaan, gebruikt u <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="12dc2-124">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="12dc2-125">U geeft bestanden op met de hashwaarde SHA256 van het bestand.</span><span class="sxs-lookup"><span data-stu-id="12dc2-125">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="12dc2-126">Als u de hashwaarde SHA256 van een bestand in Windows wilt zoeken, voer u de volgende opdracht uit in een opdrachtprompt:</span><span class="sxs-lookup"><span data-stu-id="12dc2-126">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="12dc2-127">Een voorbeeldwaarde is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="12dc2-127">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="12dc2-128">Perceptuele hashwaarden (pHash) worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="12dc2-128">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="12dc2-129">De beschikbare URL-waarden worden beschreven in de syntaxis van de URL voor de sectie Lijst met tenants [toestaan/blokkeren](#url-syntax-for-the-tenant-allowblock-list) verderop in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="12dc2-129">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="12dc2-130">De lijst Tenant toestaan/blokkeren staat maximaal 500 vermeldingen voor URL's en 500 vermeldingen voor bestandshashes toe.</span><span class="sxs-lookup"><span data-stu-id="12dc2-130">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="12dc2-131">Het maximum aantal tekens voor elke vermelding is:</span><span class="sxs-lookup"><span data-stu-id="12dc2-131">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="12dc2-132">Bestandshashes = 64</span><span class="sxs-lookup"><span data-stu-id="12dc2-132">File hashes = 64</span></span>
  - <span data-ttu-id="12dc2-133">URL = 250</span><span class="sxs-lookup"><span data-stu-id="12dc2-133">URL = 250</span></span>

- <span data-ttu-id="12dc2-134">Een item moet binnen 30 minuten actief zijn.</span><span class="sxs-lookup"><span data-stu-id="12dc2-134">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="12dc2-135">Standaard verlopen vermeldingen in de lijst Tenant toestaan/blokkeren na 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="12dc2-135">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="12dc2-136">U kunt een datum opgeven of instellen dat deze nooit verloopt.</span><span class="sxs-lookup"><span data-stu-id="12dc2-136">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="12dc2-137">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12dc2-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="12dc2-138">Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12dc2-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="12dc2-139">U moet over toegewezen machtigingen beschikken in Exchange Online voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="12dc2-139">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="12dc2-140">**URL's en bestanden:**</span><span class="sxs-lookup"><span data-stu-id="12dc2-140">**URLs and files**:</span></span>
    - <span data-ttu-id="12dc2-141">Als u waarden wilt toevoegen en verwijderen uit de lijst Tenant toestaan/blokkeren, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="12dc2-141">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="12dc2-142">Voor alleen-lezen toegang tot de tenantlijst toestaan/blokkeren moet  u lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="12dc2-142">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="12dc2-143">**Spoofing:** Een van de volgende combinaties:</span><span class="sxs-lookup"><span data-stu-id="12dc2-143">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="12dc2-144">**Organisatiebeheer**</span><span class="sxs-lookup"><span data-stu-id="12dc2-144">**Organization Management**</span></span>
    - <span data-ttu-id="12dc2-145">**Beveiligingsbeheerder** <u>en</u> **Alleen-weergeven-configuratie** of **Alleen-weergeven organisatiebeheer**.</span><span class="sxs-lookup"><span data-stu-id="12dc2-145">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="12dc2-146">Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="12dc2-146">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="12dc2-147">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="12dc2-147">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="12dc2-148">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="12dc2-148">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="12dc2-149">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="12dc2-149">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="12dc2-150">Gebruik het Beveiligings- & compliancecentrum om URL-items voor blokkering te maken in de lijst Toestaan/blokkeren van tenant</span><span class="sxs-lookup"><span data-stu-id="12dc2-150">Use the Security & Compliance Center to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="12dc2-151">Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="12dc2-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="12dc2-152">Controleer op de pagina Lijst met **tenants toestaan/blokkeren** of het tabblad **URL's** is geselecteerd en klik vervolgens op **Blokkeren**</span><span class="sxs-lookup"><span data-stu-id="12dc2-152">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="12dc2-153">Configureer **de volgende** instellingen in het flyout URL's blokkeren dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="12dc2-153">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="12dc2-154">**URL's toevoegen om te blokkeren:** Voer één URL per regel in, maximaal 20.</span><span class="sxs-lookup"><span data-stu-id="12dc2-154">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="12dc2-155">Zie de syntaxis van de URL voor de sectie Lijst met tenants [toestaan/blokkeren](#url-syntax-for-the-tenant-allowblock-list) verderop in dit artikel voor meer informatie over de syntaxis van URL-vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="12dc2-155">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="12dc2-156">**Nooit verlopen:** Ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="12dc2-156">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="12dc2-157">Controleer of de instelling is uitgeschakeld (schakel uit) en gebruik het vak Verloopt aan om de vervaldatum voor de ![ ](../../media/scc-toggle-off.png) vermeldingen op te geven. </span><span class="sxs-lookup"><span data-stu-id="12dc2-157">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="12dc2-158">of</span><span class="sxs-lookup"><span data-stu-id="12dc2-158">or</span></span>

     - <span data-ttu-id="12dc2-159">Verplaats de schakelknop naar rechts om de items zo te configureren dat ze nooit verlopen:</span><span class="sxs-lookup"><span data-stu-id="12dc2-159">Move the toggle to the right to configure the entries to never expire:</span></span> ![Inschakelen](../../media/scc-toggle-on.png)<span data-ttu-id="12dc2-161">.</span><span class="sxs-lookup"><span data-stu-id="12dc2-161">.</span></span>

   - <span data-ttu-id="12dc2-162">**Optionele opmerking:** Voer beschrijvende tekst in voor de vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="12dc2-162">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="12dc2-163">Wanneer u klaar bent, klikt u op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="12dc2-163">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="12dc2-164">Gebruik het beveiligings- & compliancecentrum om blokbestandsgegevens te maken in de lijst Toestaan/blokkeren van tenants</span><span class="sxs-lookup"><span data-stu-id="12dc2-164">Use the Security & Compliance Center to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="12dc2-165">Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="12dc2-165">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="12dc2-166">Selecteer op de pagina Lijst met  **tenants toestaan/blokkeren** het tabblad Bestanden en klik vervolgens op **Blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="12dc2-166">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="12dc2-167">Configureer **de volgende instellingen in het flyout** add files to block flyout that appears:</span><span class="sxs-lookup"><span data-stu-id="12dc2-167">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="12dc2-168">**Bestandshashes toevoegen:** Voer één SHA256-hashwaarde per regel in, maximaal 20.</span><span class="sxs-lookup"><span data-stu-id="12dc2-168">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="12dc2-169">**Nooit verlopen:** Ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="12dc2-169">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="12dc2-170">Controleer of de instelling is uitgeschakeld (schakel uit) en gebruik het vak Verloopt aan om de vervaldatum voor de ![ ](../../media/scc-toggle-off.png) vermeldingen op te geven. </span><span class="sxs-lookup"><span data-stu-id="12dc2-170">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="12dc2-171">of</span><span class="sxs-lookup"><span data-stu-id="12dc2-171">or</span></span>

     - <span data-ttu-id="12dc2-172">Verplaats de schakelknop naar rechts om de items zo te configureren dat ze nooit verlopen:</span><span class="sxs-lookup"><span data-stu-id="12dc2-172">Move the toggle to the right to configure the entries to never expire:</span></span> ![Inschakelen](../../media/scc-toggle-on.png)<span data-ttu-id="12dc2-174">.</span><span class="sxs-lookup"><span data-stu-id="12dc2-174">.</span></span>

   - <span data-ttu-id="12dc2-175">**Optionele opmerking:** Voer beschrijvende tekst in voor de vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="12dc2-175">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="12dc2-176">Wanneer u klaar bent, klikt u op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="12dc2-176">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="12dc2-177">Gebruik het Beveiligings- & compliancecentrum om vervalste afzenders toe te staan of te blokkeren in de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="12dc2-177">Use the Security & Compliance Center to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="12dc2-178">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="12dc2-178">**Notes**:</span></span>

- <span data-ttu-id="12dc2-179">Alleen de _combinatie_ van de vervalste _gebruiker_ en de verzendende infrastructuur zoals gedefinieerd in het domeinpaar is specifiek toegestaan of geblokkeerd voor spoofing.</span><span class="sxs-lookup"><span data-stu-id="12dc2-179">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="12dc2-180">Wanneer u een invoer toestaan of blokkeren configureert voor een domeinpaar, worden berichten van dat domeinpaar niet meer weergegeven in het inzicht van de spoof intelligence.</span><span class="sxs-lookup"><span data-stu-id="12dc2-180">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="12dc2-181">Vermeldingen voor vervalste afzenders verlopen nooit.</span><span class="sxs-lookup"><span data-stu-id="12dc2-181">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="12dc2-182">Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="12dc2-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="12dc2-183">Selecteer op de pagina Lijst met tenants **toestaan/blokkeren** het tabblad **Spoofing** en klik vervolgens op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="12dc2-183">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="12dc2-184">Configureer **de volgende** instellingen in het fly-out Nieuwe domeinparen toevoegen dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="12dc2-184">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="12dc2-185">**Nieuwe domeinparen toevoegen met jokertekens:** Voer één domeinpaar per regel in, maximaal 20.</span><span class="sxs-lookup"><span data-stu-id="12dc2-185">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="12dc2-186">Zie de syntaxis van het domeinpaar voor vervalste afzendergegevens in de sectie [Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) verderop in dit artikel voor meer informatie over de syntaxis van vervalste afzenders.</span><span class="sxs-lookup"><span data-stu-id="12dc2-186">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="12dc2-187">**Type spoof:** Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="12dc2-187">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="12dc2-188">**Intern:** De vervalste afzender is een domein dat deel uitmaken van uw organisatie (een [geaccepteerd domein).](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="12dc2-188">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="12dc2-189">**Extern:** De vervalste afzender is een extern domein.</span><span class="sxs-lookup"><span data-stu-id="12dc2-189">**External**: The spoofed sender is in an external domain.</span></span>

   - <span data-ttu-id="12dc2-190">**Actie:** Selecteer **Toestaan** of **Blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="12dc2-190">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="12dc2-191">Wanneer u klaar bent, klikt u op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="12dc2-191">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="12dc2-192">Het beveiligings- & compliancecentrum gebruiken om items in de lijst Tenant toestaan/blokkeren weer te geven</span><span class="sxs-lookup"><span data-stu-id="12dc2-192">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="12dc2-193">Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="12dc2-193">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="12dc2-194">Selecteer het beste tabblad.</span><span class="sxs-lookup"><span data-stu-id="12dc2-194">Select the tab you want.</span></span> <span data-ttu-id="12dc2-195">De beschikbare kolommen zijn afhankelijk van het tabblad dat u hebt geselecteerd:</span><span class="sxs-lookup"><span data-stu-id="12dc2-195">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="12dc2-196">**URL's**:</span><span class="sxs-lookup"><span data-stu-id="12dc2-196">**URLs**:</span></span>
     - <span data-ttu-id="12dc2-197">**Waarde:** De URL.</span><span class="sxs-lookup"><span data-stu-id="12dc2-197">**Value**: The URL.</span></span>
     - <span data-ttu-id="12dc2-198">**Actie**: Het **waardeblok**.</span><span class="sxs-lookup"><span data-stu-id="12dc2-198">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="12dc2-199">**Laatst bijgewerkte datum**</span><span class="sxs-lookup"><span data-stu-id="12dc2-199">**Last updated date**</span></span>
     - <span data-ttu-id="12dc2-200">**Vervaldatum**</span><span class="sxs-lookup"><span data-stu-id="12dc2-200">**Expiration date**</span></span>
     - <span data-ttu-id="12dc2-201">**Opmerking**</span><span class="sxs-lookup"><span data-stu-id="12dc2-201">**Note**</span></span>

   - <span data-ttu-id="12dc2-202">**Bestanden**</span><span class="sxs-lookup"><span data-stu-id="12dc2-202">**Files**</span></span>
     - <span data-ttu-id="12dc2-203">**Waarde:** De bestandshash.</span><span class="sxs-lookup"><span data-stu-id="12dc2-203">**Value**: The file hash.</span></span>
     - <span data-ttu-id="12dc2-204">**Actie**: Het **waardeblok**.</span><span class="sxs-lookup"><span data-stu-id="12dc2-204">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="12dc2-205">**Laatst bijgewerkte datum**</span><span class="sxs-lookup"><span data-stu-id="12dc2-205">**Last updated date**</span></span>
     - <span data-ttu-id="12dc2-206">**Vervaldatum**</span><span class="sxs-lookup"><span data-stu-id="12dc2-206">**Expiration date**</span></span>
     - <span data-ttu-id="12dc2-207">**Opmerking**</span><span class="sxs-lookup"><span data-stu-id="12dc2-207">**Note**</span></span>

   - <span data-ttu-id="12dc2-208">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="12dc2-208">**Spoofing**</span></span>
     - <span data-ttu-id="12dc2-209">**Vervalste gebruiker**</span><span class="sxs-lookup"><span data-stu-id="12dc2-209">**Spoofed user**</span></span>
     - <span data-ttu-id="12dc2-210">**Verzendende infrastructuur**</span><span class="sxs-lookup"><span data-stu-id="12dc2-210">**Sending infrastructure**</span></span>
     - <span data-ttu-id="12dc2-211">**Spooftype:** De waarde **Intern** of **Extern**.</span><span class="sxs-lookup"><span data-stu-id="12dc2-211">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="12dc2-212">**Actie:** De waarde **Blokkeren of** **Toestaan.**</span><span class="sxs-lookup"><span data-stu-id="12dc2-212">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="12dc2-213">U kunt op een kolomkoppen klikken om in oplopende of aflopende volgorde te sorteren.</span><span class="sxs-lookup"><span data-stu-id="12dc2-213">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="12dc2-214">U kunt klikken op **Groep om** de resultaten te groepen.</span><span class="sxs-lookup"><span data-stu-id="12dc2-214">You can click **Group** to group the results.</span></span> <span data-ttu-id="12dc2-215">De waarden die beschikbaar zijn, zijn afhankelijk van het tabblad dat u hebt geselecteerd:</span><span class="sxs-lookup"><span data-stu-id="12dc2-215">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="12dc2-216">**URL's:** U kunt de resultaten groepen op **Actie.**</span><span class="sxs-lookup"><span data-stu-id="12dc2-216">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="12dc2-217">**Bestanden:** U kunt de resultaten groepren op **Actie.**</span><span class="sxs-lookup"><span data-stu-id="12dc2-217">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="12dc2-218">**Afzenderdomeinen voor BCL-bypass:** **Groep** is niet beschikbaar op dit tabblad.</span><span class="sxs-lookup"><span data-stu-id="12dc2-218">**Sender domains for BCL bypass**: **Group** is not available on this tab.</span></span>
   - <span data-ttu-id="12dc2-219">**Spoofing:** U kunt de resultaten groeperen op **Actie** of **Spooftype.**</span><span class="sxs-lookup"><span data-stu-id="12dc2-219">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="12dc2-220">Klik **op Zoeken,** voer een hele of een deel van een waarde in en druk vervolgens op Enter om een specifieke waarde te zoeken.</span><span class="sxs-lookup"><span data-stu-id="12dc2-220">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="12dc2-221">Wanneer u klaar bent, klikt u op **Zoek verwijderen Zoekpictogram** ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) verwijderen.</span><span class="sxs-lookup"><span data-stu-id="12dc2-221">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

   <span data-ttu-id="12dc2-222">Klik **op Filteren** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="12dc2-222">Click **Filter** to filter the results.</span></span> <span data-ttu-id="12dc2-223">De waarden die beschikbaar zijn in **de flyout Filter** die wordt weergegeven, zijn afhankelijk van het tabblad dat u hebt geselecteerd:</span><span class="sxs-lookup"><span data-stu-id="12dc2-223">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="12dc2-224">**URL's**</span><span class="sxs-lookup"><span data-stu-id="12dc2-224">**URLs**</span></span>
     - <span data-ttu-id="12dc2-225">**Actie**</span><span class="sxs-lookup"><span data-stu-id="12dc2-225">**Action**</span></span>
     - <span data-ttu-id="12dc2-226">**Nooit verlopen**</span><span class="sxs-lookup"><span data-stu-id="12dc2-226">**Never expire**</span></span>
     - <span data-ttu-id="12dc2-227">**Laatst bijgewerkte datum**</span><span class="sxs-lookup"><span data-stu-id="12dc2-227">**Last updated date**</span></span>
     - <span data-ttu-id="12dc2-228">**Vervaldatum**</span><span class="sxs-lookup"><span data-stu-id="12dc2-228">**Expiration date**</span></span>

   - <span data-ttu-id="12dc2-229">**Bestanden**</span><span class="sxs-lookup"><span data-stu-id="12dc2-229">**Files**</span></span>
     - <span data-ttu-id="12dc2-230">**Actie**</span><span class="sxs-lookup"><span data-stu-id="12dc2-230">**Action**</span></span>
     - <span data-ttu-id="12dc2-231">**Nooit verlopen**</span><span class="sxs-lookup"><span data-stu-id="12dc2-231">**Never expire**</span></span>
     - <span data-ttu-id="12dc2-232">**Laatst bijgewerkte datum**</span><span class="sxs-lookup"><span data-stu-id="12dc2-232">**Last updated date**</span></span>
     - <span data-ttu-id="12dc2-233">**Vervaldatum**</span><span class="sxs-lookup"><span data-stu-id="12dc2-233">**Expiration date**</span></span>

   - <span data-ttu-id="12dc2-234">**Afzenderdomeinen voor BCL-bypass**</span><span class="sxs-lookup"><span data-stu-id="12dc2-234">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="12dc2-235">**Nooit verlopen**</span><span class="sxs-lookup"><span data-stu-id="12dc2-235">**Never expire**</span></span>
     - <span data-ttu-id="12dc2-236">**Laatst bijgewerkte datum**</span><span class="sxs-lookup"><span data-stu-id="12dc2-236">**Last updated date**</span></span>
     - <span data-ttu-id="12dc2-237">**Vervaldatum**</span><span class="sxs-lookup"><span data-stu-id="12dc2-237">**Expiration date**</span></span>

   - <span data-ttu-id="12dc2-238">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="12dc2-238">**Spoofing**</span></span>
     - <span data-ttu-id="12dc2-239">**Actie**</span><span class="sxs-lookup"><span data-stu-id="12dc2-239">**Action**</span></span>
     - <span data-ttu-id="12dc2-240">**Spooftype**</span><span class="sxs-lookup"><span data-stu-id="12dc2-240">**Spoof type**</span></span>

   <span data-ttu-id="12dc2-241">Wanneer u klaar bent, klikt u op **Toepassen.**</span><span class="sxs-lookup"><span data-stu-id="12dc2-241">When you're finished, click **Apply**.</span></span> <span data-ttu-id="12dc2-242">Als u bestaande filters wilt wissen, klikt u **op Filter** en klikt u in het **fly-out** Filter dat wordt weergegeven op Filters **wissen.**</span><span class="sxs-lookup"><span data-stu-id="12dc2-242">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="12dc2-243">Gebruik het beveiligings- & compliancecentrum om items in de lijst Tenant Allow/Block te wijzigen</span><span class="sxs-lookup"><span data-stu-id="12dc2-243">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="12dc2-244">Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="12dc2-244">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="12dc2-245">Selecteer het tabblad met het type vermelding dat u wilt wijzigen:</span><span class="sxs-lookup"><span data-stu-id="12dc2-245">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="12dc2-246">**URL's**</span><span class="sxs-lookup"><span data-stu-id="12dc2-246">**URLs**</span></span>
   - <span data-ttu-id="12dc2-247">**Bestanden**</span><span class="sxs-lookup"><span data-stu-id="12dc2-247">**Files**</span></span>
   - <span data-ttu-id="12dc2-248">**Afzenderdomeinen voor BCL-bypass**</span><span class="sxs-lookup"><span data-stu-id="12dc2-248">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="12dc2-249">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="12dc2-249">**Spoofing**</span></span>

3. <span data-ttu-id="12dc2-250">Selecteer het item dat u wilt wijzigen en klik vervolgens op **Pictogram** ![ Bewerken ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) bewerken.</span><span class="sxs-lookup"><span data-stu-id="12dc2-250">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span> <span data-ttu-id="12dc2-251">De waarden die u kunt wijzigen in het flyout dat wordt weergegeven, zijn afhankelijk van het tabblad dat u in de vorige stap hebt geselecteerd:</span><span class="sxs-lookup"><span data-stu-id="12dc2-251">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>

   - <span data-ttu-id="12dc2-252">**URL's**</span><span class="sxs-lookup"><span data-stu-id="12dc2-252">**URLs**</span></span>
     - <span data-ttu-id="12dc2-253">**Nooit verlopen** en/of vervaldatum.</span><span class="sxs-lookup"><span data-stu-id="12dc2-253">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="12dc2-254">**Optionele notitie**</span><span class="sxs-lookup"><span data-stu-id="12dc2-254">**Optional note**</span></span>

   - <span data-ttu-id="12dc2-255">**Bestanden**</span><span class="sxs-lookup"><span data-stu-id="12dc2-255">**Files**</span></span>
     - <span data-ttu-id="12dc2-256">**Nooit verlopen** en/of vervaldatum.</span><span class="sxs-lookup"><span data-stu-id="12dc2-256">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="12dc2-257">**Optionele notitie**</span><span class="sxs-lookup"><span data-stu-id="12dc2-257">**Optional note**</span></span>

   - <span data-ttu-id="12dc2-258">**Afzenderdomeinen voor BCL-bypass**</span><span class="sxs-lookup"><span data-stu-id="12dc2-258">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="12dc2-259">**Nooit verlopen** en/of vervaldatum.</span><span class="sxs-lookup"><span data-stu-id="12dc2-259">**Never expire** and/or expiration date.</span></span>

   - <span data-ttu-id="12dc2-260">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="12dc2-260">**Spoofing**</span></span>
     - <span data-ttu-id="12dc2-261">**Actie:** U kunt de waarde wijzigen in **Toestaan** of **Blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="12dc2-261">**Action**: You can change the value to **Allow** or **Block**.</span></span>

4. <span data-ttu-id="12dc2-262">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="12dc2-262">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="12dc2-263">Gebruik het beveiligings- & compliancecentrum om items te verwijderen uit de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="12dc2-263">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="12dc2-264">Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="12dc2-264">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="12dc2-265">Selecteer het tabblad met het type invoer dat u wilt verwijderen:</span><span class="sxs-lookup"><span data-stu-id="12dc2-265">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="12dc2-266">**URL's**</span><span class="sxs-lookup"><span data-stu-id="12dc2-266">**URLs**</span></span>
   - <span data-ttu-id="12dc2-267">**Bestanden**</span><span class="sxs-lookup"><span data-stu-id="12dc2-267">**Files**</span></span>
   - <span data-ttu-id="12dc2-268">**Afzenderdomeinen voor BCL-bypass**</span><span class="sxs-lookup"><span data-stu-id="12dc2-268">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="12dc2-269">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="12dc2-269">**Spoofing**</span></span>

3. <span data-ttu-id="12dc2-270">Selecteer het item dat u wilt verwijderen en klik vervolgens op **Pictogram** ![ Verwijderen ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) verwijderen.</span><span class="sxs-lookup"><span data-stu-id="12dc2-270">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="12dc2-271">Klik in het waarschuwingsvenster dat wordt weergegeven op **Verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="12dc2-271">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="12dc2-272">Gebruik Exchange Online PowerShell of zelfstandige EOP PowerShell om de lijst met tenants toestaan/blokkeren te configureren</span><span class="sxs-lookup"><span data-stu-id="12dc2-272">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="12dc2-273">PowerShell gebruiken om blokbestands- of URL-vermeldingen toe te voegen aan de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="12dc2-273">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="12dc2-274">Gebruik de volgende syntaxis om blokbestands- of URL-vermeldingen toe te voegen aan de lijst Tenant toestaan/blokkeren:</span><span class="sxs-lookup"><span data-stu-id="12dc2-274">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="12dc2-275">In dit voorbeeld wordt een blokbestandsinvoer toegevoegd voor de opgegeven bestanden die nooit verlopen.</span><span class="sxs-lookup"><span data-stu-id="12dc2-275">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="12dc2-276">In dit voorbeeld wordt een blok-URL-vermelding voor contoso.com en alle subdomeinen (bijvoorbeeld contoso.com, www.contoso.com en xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="12dc2-276">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="12dc2-277">Omdat we de parameters Vervaldatum of NoExpiration niet hebben gebruikt, verloopt de vermelding na 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="12dc2-277">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="12dc2-278">Zie [New-TenantAllowBlockListItems voor](/powershell/module/exchange/new-tenantallowblocklistitems)gedetailleerde syntaxis en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="12dc2-278">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="12dc2-279">PowerShell gebruiken om vervalste afzendergegevens toe te voegen of te blokkeren aan de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="12dc2-279">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="12dc2-280">Gebruik de volgende syntaxis om vervalste afzendergegevens toe te voegen aan de lijst Tenant Allow/Block:</span><span class="sxs-lookup"><span data-stu-id="12dc2-280">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="12dc2-281">Zie [New-TenantAllowBlockListSpoofItems voor](/powershell/module/exchange/new-tenantallowblocklistspoofitems)gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="12dc2-281">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="12dc2-282">PowerShell gebruiken om blokbestands- of URL-items weer te geven in de lijst Tenant Allow/Block</span><span class="sxs-lookup"><span data-stu-id="12dc2-282">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="12dc2-283">Als u blokbestands- of URL-vermeldingen wilt weergeven in de lijst Tenant toestaan/blokkeren, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="12dc2-283">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="12dc2-284">In dit voorbeeld worden gegevens voor de opgegeven waarde voor bestandshash als resultaat gegeven.</span><span class="sxs-lookup"><span data-stu-id="12dc2-284">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="12dc2-285">In dit voorbeeld worden alle geblokkeerde URL's als retourneert.</span><span class="sxs-lookup"><span data-stu-id="12dc2-285">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="12dc2-286">Zie [Get-TenantAllowBlockListItems voor](/powershell/module/exchange/get-tenantallowblocklistitems)gedetailleerde syntaxis en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="12dc2-286">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="12dc2-287">PowerShell gebruiken om vervalste afzenders toe te staan of te blokkeren in de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="12dc2-287">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="12dc2-288">Gebruik de volgende syntaxis om vervalste afzendergegevens weer te geven in de lijst Tenant Allow/Block:</span><span class="sxs-lookup"><span data-stu-id="12dc2-288">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="12dc2-289">Dit voorbeeld retourneert alle vervalste afzendergegevens in de lijst Tenant toestaan/blokkeren.</span><span class="sxs-lookup"><span data-stu-id="12dc2-289">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="12dc2-290">Dit voorbeeld retourneert alle toegestane vermeldingen van vervalste afzenders die intern zijn.</span><span class="sxs-lookup"><span data-stu-id="12dc2-290">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="12dc2-291">In dit voorbeeld worden alle geblokkeerde vermeldingen van vervalste afzenders die extern zijn, als retourneert.</span><span class="sxs-lookup"><span data-stu-id="12dc2-291">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="12dc2-292">Zie [Get-TenantAllowBlockListSpoofItems (Get-TenantAllowBlockListSpoofItems)](/powershell/module/exchange/get-tenantallowblocklistspoofitems)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="12dc2-292">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="12dc2-293">PowerShell gebruiken om blokbestands- en URL-items in de lijst Tenant allow/block te wijzigen</span><span class="sxs-lookup"><span data-stu-id="12dc2-293">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="12dc2-294">Gebruik de volgende syntaxis om blokbestands- en URL-vermeldingen in de lijst Tenant toestaan/blokkeren te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="12dc2-294">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="12dc2-295">In dit voorbeeld wordt de vervaldatum van de opgegeven blok-URL-vermelding gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="12dc2-295">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="12dc2-296">Zie [Set-TenantAllowBlockListItems (Set-TenantAllowBlockListItems)](/powershell/module/exchange/set-tenantallowblocklistitems)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="12dc2-296">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="12dc2-297">PowerShell gebruiken om vervalste afzenders toe te staan of te blokkeren in de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="12dc2-297">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="12dc2-298">Gebruik de volgende syntaxis om vervalste afzendergegevens in de lijst Tenant Allow/Block te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="12dc2-298">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="12dc2-299">In dit voorbeeld wordt de vermelding van vervalste afzenders gewijzigd in toestaan om te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="12dc2-299">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="12dc2-300">Zie [Set-TenantAllowBlockListSpoofItems (Set-TenantAllowBlockListSpoofItems)](/powershell/module/exchange/set-tenantallowblocklistspoofitems)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="12dc2-300">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="12dc2-301">PowerShell gebruiken om URL- of bestandsgegevens te verwijderen uit de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="12dc2-301">Use PowerShell to remove URL or file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="12dc2-302">Gebruik de volgende syntaxis om bestands- en URL-vermeldingen te verwijderen uit de lijst Tenant toestaan/blokkeren:</span><span class="sxs-lookup"><span data-stu-id="12dc2-302">To remove file and URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="12dc2-303">In dit voorbeeld wordt de opgegeven blok-URL-vermelding verwijderd uit de lijst Tenant toestaan/blokkeren.</span><span class="sxs-lookup"><span data-stu-id="12dc2-303">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="12dc2-304">Zie [Remove-TenantAllowBlockListItems (Verwijderen-TenantAllowBlockListItems)](/powershell/module/exchange/remove-tenantallowblocklistitems)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="12dc2-304">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="12dc2-305">PowerShell gebruiken om vervalste afzenders toe te staan of te blokkeren uit de tenantlijst toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="12dc2-305">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="12dc2-306">Gebruik de volgende syntaxis als u spoofing sender items wilt verwijderen uit de tenant allow/block list:</span><span class="sxs-lookup"><span data-stu-id="12dc2-306">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="12dc2-307">Zie [Remove-TenantAllowBlockListSpoofItems (Verwijderen-TenantAllowBlockListSpoofItems)](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="12dc2-307">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="12dc2-308">URL-syntaxis voor de lijst Toestaan/blokkeren van tenant</span><span class="sxs-lookup"><span data-stu-id="12dc2-308">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="12dc2-309">IP4v- en IPv6-adressen zijn toegestaan, maar TCP/UDP-poorten niet.</span><span class="sxs-lookup"><span data-stu-id="12dc2-309">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="12dc2-310">Bestandsnaamextensies zijn niet toegestaan (bijvoorbeeld test.pdf).</span><span class="sxs-lookup"><span data-stu-id="12dc2-310">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="12dc2-311">Unicode wordt niet ondersteund, maar Punycode wel.</span><span class="sxs-lookup"><span data-stu-id="12dc2-311">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="12dc2-312">Hostnamen zijn toegestaan als alle volgende instructies waar zijn:</span><span class="sxs-lookup"><span data-stu-id="12dc2-312">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="12dc2-313">De hostnaam bevat een punt.</span><span class="sxs-lookup"><span data-stu-id="12dc2-313">The hostname contains a period.</span></span>
  - <span data-ttu-id="12dc2-314">Er is ten minste één teken links van de periode.</span><span class="sxs-lookup"><span data-stu-id="12dc2-314">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="12dc2-315">Er zijn ten minste twee tekens rechts van de periode.</span><span class="sxs-lookup"><span data-stu-id="12dc2-315">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="12dc2-316">Is bijvoorbeeld `t.co` toegestaan of `.com` niet `contoso.` toegestaan.</span><span class="sxs-lookup"><span data-stu-id="12dc2-316">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="12dc2-317">Subpathen worden niet geïmpliceerd.</span><span class="sxs-lookup"><span data-stu-id="12dc2-317">Subpaths are not implied.</span></span>

  <span data-ttu-id="12dc2-318">Bevat bijvoorbeeld `contoso.com` geen `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="12dc2-318">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="12dc2-319">Jokertekens (\*) zijn toegestaan in de volgende scenario's:</span><span class="sxs-lookup"><span data-stu-id="12dc2-319">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="12dc2-320">Een linker jokerteken moet worden gevolgd door een punt om een subdomein op te geven.</span><span class="sxs-lookup"><span data-stu-id="12dc2-320">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="12dc2-321">Is bijvoorbeeld `*.contoso.com` toegestaan; `*contoso.com` is niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="12dc2-321">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="12dc2-322">Een jokerteken rechts moet een slash (/) volgen om een pad op te geven.</span><span class="sxs-lookup"><span data-stu-id="12dc2-322">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="12dc2-323">Is bijvoorbeeld `contoso.com/*` toegestaan of `contoso.com*` niet `contoso.com/ab*` toegestaan.</span><span class="sxs-lookup"><span data-stu-id="12dc2-323">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="12dc2-324">Alle subpathen worden niet geïmpliceerd door een rechter jokerteken.</span><span class="sxs-lookup"><span data-stu-id="12dc2-324">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="12dc2-325">Bevat bijvoorbeeld `contoso.com/*` geen `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="12dc2-325">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="12dc2-326">`*.com*` ongeldig is (geen op te lossen domein en het jokerteken rechts volgt geen slash voor vooruit).</span><span class="sxs-lookup"><span data-stu-id="12dc2-326">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="12dc2-327">Jokertekens zijn niet toegestaan in IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="12dc2-327">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="12dc2-328">Het tildeteken (~) is beschikbaar in de volgende scenario's:</span><span class="sxs-lookup"><span data-stu-id="12dc2-328">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="12dc2-329">Een linker tilde houdt een domein en alle subdomeinen in.</span><span class="sxs-lookup"><span data-stu-id="12dc2-329">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="12dc2-330">Bijvoorbeeld inclusief `~contoso.com` `contoso.com` en `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="12dc2-330">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="12dc2-331">URL-vermeldingen die protocollen bevatten (bijvoorbeeld , of ) mislukken, omdat URL-vermeldingen van toepassing zijn `http://` `https://` op alle `ftp://` protocollen.</span><span class="sxs-lookup"><span data-stu-id="12dc2-331">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="12dc2-332">Een gebruikersnaam of wachtwoord wordt niet ondersteund of vereist.</span><span class="sxs-lookup"><span data-stu-id="12dc2-332">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="12dc2-333">Aanhalingstekens (' of ") zijn ongeldige tekens.</span><span class="sxs-lookup"><span data-stu-id="12dc2-333">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="12dc2-334">Een URL moet waar mogelijk alle omleidingen bevatten.</span><span class="sxs-lookup"><span data-stu-id="12dc2-334">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="12dc2-335">Scenario's voor URL-invoer</span><span class="sxs-lookup"><span data-stu-id="12dc2-335">URL entry scenarios</span></span>

<span data-ttu-id="12dc2-336">Geldige URL-vermeldingen en de resultaten worden beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="12dc2-336">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="12dc2-337">Scenario: Geen jokertekens</span><span class="sxs-lookup"><span data-stu-id="12dc2-337">Scenario: No wildcards</span></span>

<span data-ttu-id="12dc2-338">**Vermelding**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="12dc2-338">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="12dc2-339">**Overeenkomst toestaan**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-339">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="12dc2-340">**Niet-overeenkomende toestaan:**</span><span class="sxs-lookup"><span data-stu-id="12dc2-340">**Allow not matched**:</span></span>

  - <span data-ttu-id="12dc2-341">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-341">abc-contoso.com</span></span>
  - <span data-ttu-id="12dc2-342">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="12dc2-342">contoso.com/a</span></span>
  - <span data-ttu-id="12dc2-343">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-343">payroll.contoso.com</span></span>
  - <span data-ttu-id="12dc2-344">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-344">test.com/contoso.com</span></span>
  - <span data-ttu-id="12dc2-345">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-345">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="12dc2-346">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-346">www.contoso.com</span></span>
  - <span data-ttu-id="12dc2-347">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-347">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="12dc2-348">**Blok overeenkomst**:</span><span class="sxs-lookup"><span data-stu-id="12dc2-348">**Block match**:</span></span>

  - <span data-ttu-id="12dc2-349">contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-349">contoso.com</span></span>
  - <span data-ttu-id="12dc2-350">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="12dc2-350">contoso.com/a</span></span>
  - <span data-ttu-id="12dc2-351">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-351">payroll.contoso.com</span></span>
  - <span data-ttu-id="12dc2-352">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-352">test.com/contoso.com</span></span>
  - <span data-ttu-id="12dc2-353">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-353">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="12dc2-354">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-354">www.contoso.com</span></span>
  - <span data-ttu-id="12dc2-355">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-355">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="12dc2-356">**Blok niet overeenkomend**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-356">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="12dc2-357">Scenario: Jokerteken links (subdomein)</span><span class="sxs-lookup"><span data-stu-id="12dc2-357">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="12dc2-358">**Vermelding**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="12dc2-358">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="12dc2-359">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="12dc2-359">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="12dc2-360">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-360">www.contoso.com</span></span>
  - <span data-ttu-id="12dc2-361">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-361">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="12dc2-362">**Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**</span><span class="sxs-lookup"><span data-stu-id="12dc2-362">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="12dc2-363">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-363">123contoso.com</span></span>
  - <span data-ttu-id="12dc2-364">contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-364">contoso.com</span></span>
  - <span data-ttu-id="12dc2-365">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-365">test.com/contoso.com</span></span>
  - <span data-ttu-id="12dc2-366">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="12dc2-366">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="12dc2-367">Scenario: Jokerteken rechts boven aan pad</span><span class="sxs-lookup"><span data-stu-id="12dc2-367">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="12dc2-368">**Vermelding**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="12dc2-368">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="12dc2-369">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="12dc2-369">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="12dc2-370">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="12dc2-370">contoso.com/a/b</span></span>
  - <span data-ttu-id="12dc2-371">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="12dc2-371">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="12dc2-372">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-372">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="12dc2-373">**Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**</span><span class="sxs-lookup"><span data-stu-id="12dc2-373">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="12dc2-374">contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-374">contoso.com</span></span>
  - <span data-ttu-id="12dc2-375">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="12dc2-375">contoso.com/a</span></span>
  - <span data-ttu-id="12dc2-376">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-376">www.contoso.com</span></span>
  - <span data-ttu-id="12dc2-377">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-377">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="12dc2-378">Scenario: Tilde links</span><span class="sxs-lookup"><span data-stu-id="12dc2-378">Scenario: Left tilde</span></span>

<span data-ttu-id="12dc2-379">**Vermelding**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="12dc2-379">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="12dc2-380">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="12dc2-380">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="12dc2-381">contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-381">contoso.com</span></span>
  - <span data-ttu-id="12dc2-382">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-382">www.contoso.com</span></span>
  - <span data-ttu-id="12dc2-383">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-383">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="12dc2-384">**Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**</span><span class="sxs-lookup"><span data-stu-id="12dc2-384">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="12dc2-385">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-385">123contoso.com</span></span>
  - <span data-ttu-id="12dc2-386">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="12dc2-386">contoso.com/abc</span></span>
  - <span data-ttu-id="12dc2-387">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="12dc2-387">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="12dc2-388">Scenario: Het achtervoegsel van het jokerteken rechts</span><span class="sxs-lookup"><span data-stu-id="12dc2-388">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="12dc2-389">**Vermelding**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="12dc2-389">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="12dc2-390">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="12dc2-390">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="12dc2-391">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-391">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="12dc2-392">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="12dc2-392">contoso.com/a</span></span>
  - <span data-ttu-id="12dc2-393">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="12dc2-393">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="12dc2-394">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="12dc2-394">contoso.com/ab</span></span>
  - <span data-ttu-id="12dc2-395">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="12dc2-395">contoso.com/b</span></span>
  - <span data-ttu-id="12dc2-396">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="12dc2-396">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="12dc2-397">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="12dc2-397">contoso.com/ba</span></span>

- <span data-ttu-id="12dc2-398">**Niet-overeenkomende en** **niet-overeenkomende** blokkering toestaan: contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-398">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="12dc2-399">Scenario: Linker jokertekensubdomein en rechterachtervoegsel jokerteken</span><span class="sxs-lookup"><span data-stu-id="12dc2-399">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="12dc2-400">**Vermelding**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="12dc2-400">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="12dc2-401">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="12dc2-401">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="12dc2-402">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="12dc2-402">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="12dc2-403">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="12dc2-403">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="12dc2-404">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="12dc2-404">www.contoso.com/a</span></span>
  - <span data-ttu-id="12dc2-405">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="12dc2-405">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="12dc2-406">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="12dc2-406">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="12dc2-407">**Niet-overeenkomende en** **niet-overeenkomende** blokkering toestaan : contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="12dc2-407">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="12dc2-408">Scenario: Tilde links en rechts</span><span class="sxs-lookup"><span data-stu-id="12dc2-408">Scenario: Left and right tilde</span></span>

<span data-ttu-id="12dc2-409">**Vermelding**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="12dc2-409">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="12dc2-410">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="12dc2-410">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="12dc2-411">contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-411">contoso.com</span></span>
  - <span data-ttu-id="12dc2-412">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="12dc2-412">contoso.com/a</span></span>
  - <span data-ttu-id="12dc2-413">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-413">www.contoso.com</span></span>
  - <span data-ttu-id="12dc2-414">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="12dc2-414">www.contoso.com/b</span></span>
  - <span data-ttu-id="12dc2-415">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-415">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="12dc2-416">**Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**</span><span class="sxs-lookup"><span data-stu-id="12dc2-416">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="12dc2-417">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-417">123contoso.com</span></span>
  - <span data-ttu-id="12dc2-418">contoso.org</span><span class="sxs-lookup"><span data-stu-id="12dc2-418">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="12dc2-419">Scenario: IP-adres</span><span class="sxs-lookup"><span data-stu-id="12dc2-419">Scenario: IP address</span></span>

<span data-ttu-id="12dc2-420">**Vermelding**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="12dc2-420">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="12dc2-421">**Overeenkomst toestaan** **en overeenkomst blokkeren**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="12dc2-421">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="12dc2-422">**Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**</span><span class="sxs-lookup"><span data-stu-id="12dc2-422">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="12dc2-423">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="12dc2-423">1.2.3.4/a</span></span>
  - <span data-ttu-id="12dc2-424">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="12dc2-424">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="12dc2-425">IP-adres met jokerteken rechts</span><span class="sxs-lookup"><span data-stu-id="12dc2-425">IP address with right wildcard</span></span>

<span data-ttu-id="12dc2-426">**Vermelding**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="12dc2-426">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="12dc2-427">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="12dc2-427">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="12dc2-428">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="12dc2-428">1.2.3.4/b</span></span>
  - <span data-ttu-id="12dc2-429">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="12dc2-429">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="12dc2-430">Voorbeelden van ongeldige vermeldingen</span><span class="sxs-lookup"><span data-stu-id="12dc2-430">Examples of invalid entries</span></span>

<span data-ttu-id="12dc2-431">De volgende vermeldingen zijn ongeldig:</span><span class="sxs-lookup"><span data-stu-id="12dc2-431">The following entries are invalid:</span></span>

- <span data-ttu-id="12dc2-432">**Ontbrekende of ongeldige domeinwaarden:**</span><span class="sxs-lookup"><span data-stu-id="12dc2-432">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="12dc2-433">contoso</span><span class="sxs-lookup"><span data-stu-id="12dc2-433">contoso</span></span>
  - <span data-ttu-id="12dc2-434">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="12dc2-434">\*.contoso.\*</span></span>
  - <span data-ttu-id="12dc2-435">\*.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-435">\*.com</span></span>
  - <span data-ttu-id="12dc2-436">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="12dc2-436">\*.pdf</span></span>

- <span data-ttu-id="12dc2-437">**Jokerteken op tekst of zonder spatiëringstekens:**</span><span class="sxs-lookup"><span data-stu-id="12dc2-437">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="12dc2-438">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-438">\*contoso.com</span></span>
  - <span data-ttu-id="12dc2-439">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="12dc2-439">contoso.com\*</span></span>
  - <span data-ttu-id="12dc2-440">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="12dc2-440">\*1.2.3.4</span></span>
  - <span data-ttu-id="12dc2-441">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="12dc2-441">1.2.3.4\*</span></span>
  - <span data-ttu-id="12dc2-442">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="12dc2-442">contoso.com/a\*</span></span>
  - <span data-ttu-id="12dc2-443">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="12dc2-443">contoso.com/ab\*</span></span>

- <span data-ttu-id="12dc2-444">**IP-adressen met poorten:**</span><span class="sxs-lookup"><span data-stu-id="12dc2-444">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="12dc2-445">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="12dc2-445">contoso.com:443</span></span>
  - <span data-ttu-id="12dc2-446">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="12dc2-446">abc.contoso.com:25</span></span>

- <span data-ttu-id="12dc2-447">**Niet-beschrijvende jokertekens:**</span><span class="sxs-lookup"><span data-stu-id="12dc2-447">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="12dc2-448">\*.\*</span><span class="sxs-lookup"><span data-stu-id="12dc2-448">\*.\*</span></span>

- <span data-ttu-id="12dc2-449">**Middelste jokertekens:**</span><span class="sxs-lookup"><span data-stu-id="12dc2-449">**Middle wildcards**:</span></span>

  - <span data-ttu-id="12dc2-450">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-450">conto\*so.com</span></span>
  - <span data-ttu-id="12dc2-451">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-451">conto~so.com</span></span>

- <span data-ttu-id="12dc2-452">**Dubbele jokertekens**</span><span class="sxs-lookup"><span data-stu-id="12dc2-452">**Double wildcards**</span></span>

  - <span data-ttu-id="12dc2-453">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="12dc2-453">contoso.com/\*\*</span></span>
  - <span data-ttu-id="12dc2-454">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="12dc2-454">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="12dc2-455">Syntaxis van domeinparen voor vervalste afzendergegevens in de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="12dc2-455">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="12dc2-456">Een domeinpaar voor een vervalste afzender in de lijst Tenant toestaan/blokkeren gebruikt de volgende syntaxis: `<Spoofed user>, <Sending infrastructure>` .</span><span class="sxs-lookup"><span data-stu-id="12dc2-456">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="12dc2-457">**Vervalste gebruiker:** Deze waarde betreft het e-mailadres van de vervalste gebruiker die wordt weergegeven in het vak **Van** in e-mail clients.</span><span class="sxs-lookup"><span data-stu-id="12dc2-457">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="12dc2-458">Dit adres wordt ook wel het adres `5322.From` genoemd.</span><span class="sxs-lookup"><span data-stu-id="12dc2-458">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="12dc2-459">Geldige waarden zijn:</span><span class="sxs-lookup"><span data-stu-id="12dc2-459">Valid values include:</span></span>
  - <span data-ttu-id="12dc2-460">Een afzonderlijk e-mailadres (bijvoorbeeld chris@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="12dc2-460">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="12dc2-461">Een e-maildomein (bijvoorbeeld contoso.com).</span><span class="sxs-lookup"><span data-stu-id="12dc2-461">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="12dc2-462">Het jokerteken \* (bijvoorbeeld).</span><span class="sxs-lookup"><span data-stu-id="12dc2-462">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="12dc2-463">**Verzendende infrastructuur:** deze waarde geeft de bron aan van berichten van de vervalste gebruiker.</span><span class="sxs-lookup"><span data-stu-id="12dc2-463">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="12dc2-464">Geldige waarden zijn:</span><span class="sxs-lookup"><span data-stu-id="12dc2-464">Valid values include:</span></span>
  - <span data-ttu-id="12dc2-465">Het domein dat is gevonden in een REVERSE DNS lookup (PTR-record) van het IP-adres van de bron-e-mailserver (bijvoorbeeld fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="12dc2-465">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="12dc2-466">Als het bron-IP-adres geen PTR-record heeft, wordt de verzendende infrastructuur geïdentificeerd als \<source IP\> /24 (bijvoorbeeld 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="12dc2-466">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="12dc2-467">Hier zijn enkele voorbeelden van geldige domeinparen om vervalste afzenders te identificeren:</span><span class="sxs-lookup"><span data-stu-id="12dc2-467">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="12dc2-468">Het maximum aantal vervalste afzenders is 1000.</span><span class="sxs-lookup"><span data-stu-id="12dc2-468">The maximum number of spoofed sender entries is 1000.</span></span> 

<span data-ttu-id="12dc2-469">Als u een domeinpaar toevoegt, wordt  de *combinatie* van de vervalste gebruiker en de verzendende infrastructuur alleen mogelijk of blokkeert.</span><span class="sxs-lookup"><span data-stu-id="12dc2-469">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="12dc2-470">E-mail van de vervalste gebruiker van welke bron dan ook is niet toegestaan en e-mail uit de bron van de verzendende infrastructuur wordt niet toegestaan voor vervalste gebruikers.</span><span class="sxs-lookup"><span data-stu-id="12dc2-470">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span> 

<span data-ttu-id="12dc2-471">U voegt bijvoorbeeld een toegestane vermelding toe voor het volgende domeinpaar:</span><span class="sxs-lookup"><span data-stu-id="12dc2-471">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="12dc2-472">**Domein:** gmail.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-472">**Domain**: gmail.com</span></span>
- <span data-ttu-id="12dc2-473">**Infrastructuur**: tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="12dc2-473">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="12dc2-474">Alleen berichten uit dat domein *en het* verzenden van infrastructuurparen mogen spoofen.</span><span class="sxs-lookup"><span data-stu-id="12dc2-474">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="12dc2-475">Andere afzenders die proberen te spoofen gmail.com zijn niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="12dc2-475">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="12dc2-476">Berichten van afzenders in andere domeinen die afkomstig zijn van tms.mx.com worden gecontroleerd door spoof intelligence.</span><span class="sxs-lookup"><span data-stu-id="12dc2-476">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
