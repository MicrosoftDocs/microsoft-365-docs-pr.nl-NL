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
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="79f86-103">Tenant Toestaan/Blokkeren-lijst beheren</span><span class="sxs-lookup"><span data-stu-id="79f86-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="79f86-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="79f86-104">**Applies to**</span></span>
- [<span data-ttu-id="79f86-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="79f86-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="79f86-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="79f86-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="79f86-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="79f86-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="79f86-108">De functies die in dit artikel worden beschreven, zijn in Preview, kunnen worden gewijzigd en zijn niet beschikbaar in alle organisaties.</span><span class="sxs-lookup"><span data-stu-id="79f86-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="79f86-109">Als uw organisatie niet beschikt over de spooffuncties zoals beschreven in dit artikel, bekijkt u de oudere spoofbeheerervaring bij Vervalste afzenders beheren met behulp van het spoof intelligence-beleid en het inzicht in spoof [intelligence in EOP.](walkthrough-spoof-intelligence-insight.md)</span><span class="sxs-lookup"><span data-stu-id="79f86-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="79f86-110">U kunt op dit **moment geen** toegestane URL- of bestandsitems configureren in de lijst Tenant toestaan/blokkeren.</span><span class="sxs-lookup"><span data-stu-id="79f86-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="79f86-111">In Microsoft 365 organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken, kunt u het niet eens zijn met de uitspraak over EOP-filtering.</span><span class="sxs-lookup"><span data-stu-id="79f86-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="79f86-112">Een goed bericht kan bijvoorbeeld worden gemarkeerd als slecht (een onwaar positief) of een slecht bericht kan worden toegestaan (een onwaar negatief).</span><span class="sxs-lookup"><span data-stu-id="79f86-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="79f86-113">Met de tenantlijst Toestaan/blokkeren in het Beveiligings- & Compliancecentrum kunt u handmatig de regels voor filteren Microsoft 365 overschrijven.</span><span class="sxs-lookup"><span data-stu-id="79f86-113">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="79f86-114">De lijst Tenant toestaan/blokkeren wordt gebruikt tijdens de e-mailstroom en op het moment dat de gebruiker klikt.</span><span class="sxs-lookup"><span data-stu-id="79f86-114">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="79f86-115">U kunt de volgende typen overschrijven opgeven:</span><span class="sxs-lookup"><span data-stu-id="79f86-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="79f86-116">URL's die u wilt blokkeren.</span><span class="sxs-lookup"><span data-stu-id="79f86-116">URLs to block.</span></span>
- <span data-ttu-id="79f86-117">Bestanden die u wilt blokkeren.</span><span class="sxs-lookup"><span data-stu-id="79f86-117">Files to block.</span></span>
- <span data-ttu-id="79f86-118">Vervalste afzenders om dit toe te staan of te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="79f86-118">Spoofed senders to allow or block.</span></span> <span data-ttu-id="79f86-119">Als u de uitspraak toestaan of blokkeren overschrijven in het inzicht van spoof [intelligence,](learn-about-spoof-intelligence.md)wordt de vervalste afzender een handmatige invoer toestaan of blokkeren die alleen wordt weergegeven op het tabblad **Spoof** in de lijst Toestaan/blokkeren van tenants.</span><span class="sxs-lookup"><span data-stu-id="79f86-119">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="79f86-120">U kunt hier ook handmatig vermeldingen voor vervalste afzenders maken of blokkeren voordat ze worden gedetecteerd door spoofinformatie.</span><span class="sxs-lookup"><span data-stu-id="79f86-120">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="79f86-121">In dit artikel wordt beschreven hoe u vermeldingen configureert in de lijst Tenant toestaan/blokkeren in het Beveiligings- & Compliancecentrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).</span><span class="sxs-lookup"><span data-stu-id="79f86-121">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="79f86-122">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="79f86-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="79f86-123">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="79f86-123">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="79f86-124">Als u rechtstreeks naar de **pagina Lijst met tenants toestaan/blokkeren wilt** gaan, gebruikt u <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="79f86-124">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="79f86-125">U geeft bestanden op met de hashwaarde SHA256 van het bestand.</span><span class="sxs-lookup"><span data-stu-id="79f86-125">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="79f86-126">Als u de hashwaarde SHA256 van een bestand in Windows wilt zoeken, voer u de volgende opdracht uit in een opdrachtprompt:</span><span class="sxs-lookup"><span data-stu-id="79f86-126">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="79f86-127">Een voorbeeldwaarde is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="79f86-127">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="79f86-128">Perceptuele hashwaarden (pHash) worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="79f86-128">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="79f86-129">De beschikbare URL-waarden worden beschreven in de syntaxis van de URL voor de sectie Lijst met tenants [toestaan/blokkeren](#url-syntax-for-the-tenant-allowblock-list) verderop in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="79f86-129">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="79f86-130">De lijst Tenant toestaan/blokkeren staat maximaal 500 vermeldingen voor URL's en 500 vermeldingen voor bestandshashes toe.</span><span class="sxs-lookup"><span data-stu-id="79f86-130">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="79f86-131">Het maximum aantal tekens voor elke vermelding is:</span><span class="sxs-lookup"><span data-stu-id="79f86-131">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="79f86-132">Bestandshashes = 64</span><span class="sxs-lookup"><span data-stu-id="79f86-132">File hashes = 64</span></span>
  - <span data-ttu-id="79f86-133">URL = 250</span><span class="sxs-lookup"><span data-stu-id="79f86-133">URL = 250</span></span>

- <span data-ttu-id="79f86-134">Een item moet binnen 30 minuten actief zijn.</span><span class="sxs-lookup"><span data-stu-id="79f86-134">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="79f86-135">Standaard verlopen vermeldingen in de lijst Tenant toestaan/blokkeren na 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="79f86-135">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="79f86-136">U kunt een datum opgeven of instellen dat deze nooit verloopt.</span><span class="sxs-lookup"><span data-stu-id="79f86-136">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="79f86-137">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="79f86-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="79f86-138">Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="79f86-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="79f86-139">U moet over toegewezen machtigingen beschikken in Exchange Online voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="79f86-139">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="79f86-140">**URL's en bestanden:**</span><span class="sxs-lookup"><span data-stu-id="79f86-140">**URLs and files**:</span></span>
    - <span data-ttu-id="79f86-141">Als u waarden wilt toevoegen en verwijderen uit de lijst Tenant toestaan/blokkeren, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="79f86-141">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="79f86-142">Voor alleen-lezen toegang tot de tenantlijst toestaan/blokkeren moet  u lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="79f86-142">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="79f86-143">**Spoofing:** Een van de volgende combinaties:</span><span class="sxs-lookup"><span data-stu-id="79f86-143">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="79f86-144">**Organisatiebeheer**</span><span class="sxs-lookup"><span data-stu-id="79f86-144">**Organization Management**</span></span>
    - <span data-ttu-id="79f86-145">**Beveiligingsbeheerder** <u>en</u> **Alleen-weergeven-configuratie** of **Alleen-weergeven organisatiebeheer**.</span><span class="sxs-lookup"><span data-stu-id="79f86-145">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="79f86-146">Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="79f86-146">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="79f86-147">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="79f86-147">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="79f86-148">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="79f86-148">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="79f86-149">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="79f86-149">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="79f86-150">Gebruik het Beveiligings- & compliancecentrum om URL-items voor blokkering te maken in de lijst Toestaan/blokkeren van tenant</span><span class="sxs-lookup"><span data-stu-id="79f86-150">Use the Security & Compliance Center to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="79f86-151">Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="79f86-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="79f86-152">Controleer op de pagina Lijst met **tenants toestaan/blokkeren** of het tabblad **URL's** is geselecteerd en klik vervolgens op **Blokkeren**</span><span class="sxs-lookup"><span data-stu-id="79f86-152">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="79f86-153">Configureer **de volgende** instellingen in het flyout URL's blokkeren dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="79f86-153">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="79f86-154">**URL's toevoegen om te blokkeren:** Voer één URL per regel in, maximaal 20.</span><span class="sxs-lookup"><span data-stu-id="79f86-154">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="79f86-155">Zie de syntaxis van de URL voor de sectie Lijst met tenants [toestaan/blokkeren](#url-syntax-for-the-tenant-allowblock-list) verderop in dit artikel voor meer informatie over de syntaxis van URL-vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="79f86-155">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="79f86-156">**Nooit verlopen:** Ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="79f86-156">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="79f86-157">Controleer of de instelling is uitgeschakeld (schakel uit) en gebruik het vak Verloopt aan om de vervaldatum voor de ![ ](../../media/scc-toggle-off.png) vermeldingen op te geven. </span><span class="sxs-lookup"><span data-stu-id="79f86-157">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="79f86-158">of</span><span class="sxs-lookup"><span data-stu-id="79f86-158">or</span></span>

     - <span data-ttu-id="79f86-159">Verplaats de schakelknop naar rechts om de items zo te configureren dat ze nooit verlopen:</span><span class="sxs-lookup"><span data-stu-id="79f86-159">Move the toggle to the right to configure the entries to never expire:</span></span> ![Inschakelen](../../media/scc-toggle-on.png)<span data-ttu-id="79f86-161">.</span><span class="sxs-lookup"><span data-stu-id="79f86-161">.</span></span>

   - <span data-ttu-id="79f86-162">**Optionele opmerking:** Voer beschrijvende tekst in voor de vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="79f86-162">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="79f86-163">Wanneer u klaar bent, klikt u op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="79f86-163">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="79f86-164">Gebruik het beveiligings- & compliancecentrum om blokbestandsgegevens te maken in de lijst Toestaan/blokkeren van tenants</span><span class="sxs-lookup"><span data-stu-id="79f86-164">Use the Security & Compliance Center to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="79f86-165">Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="79f86-165">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="79f86-166">Selecteer op de pagina Lijst met  **tenants toestaan/blokkeren** het tabblad Bestanden en klik vervolgens op **Blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="79f86-166">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="79f86-167">Configureer **de volgende instellingen in het flyout** add files to block flyout that appears:</span><span class="sxs-lookup"><span data-stu-id="79f86-167">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="79f86-168">**Bestandshashes toevoegen:** Voer één SHA256-hashwaarde per regel in, maximaal 20.</span><span class="sxs-lookup"><span data-stu-id="79f86-168">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="79f86-169">**Nooit verlopen:** Ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="79f86-169">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="79f86-170">Controleer of de instelling is uitgeschakeld (schakel uit) en gebruik het vak Verloopt aan om de vervaldatum voor de ![ ](../../media/scc-toggle-off.png) vermeldingen op te geven. </span><span class="sxs-lookup"><span data-stu-id="79f86-170">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="79f86-171">of</span><span class="sxs-lookup"><span data-stu-id="79f86-171">or</span></span>

     - <span data-ttu-id="79f86-172">Verplaats de schakelknop naar rechts om de items zo te configureren dat ze nooit verlopen:</span><span class="sxs-lookup"><span data-stu-id="79f86-172">Move the toggle to the right to configure the entries to never expire:</span></span> ![Inschakelen](../../media/scc-toggle-on.png)<span data-ttu-id="79f86-174">.</span><span class="sxs-lookup"><span data-stu-id="79f86-174">.</span></span>

   - <span data-ttu-id="79f86-175">**Optionele opmerking:** Voer beschrijvende tekst in voor de vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="79f86-175">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="79f86-176">Wanneer u klaar bent, klikt u op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="79f86-176">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="79f86-177">Gebruik het Beveiligings- & compliancecentrum om vervalste afzenders toe te staan of te blokkeren in de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="79f86-177">Use the Security & Compliance Center to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="79f86-178">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="79f86-178">**Notes**:</span></span>

- <span data-ttu-id="79f86-179">Alleen de _combinatie_ van de vervalste _gebruiker_ en de verzendende infrastructuur zoals gedefinieerd in het domeinpaar is specifiek toegestaan of geblokkeerd voor spoofing.</span><span class="sxs-lookup"><span data-stu-id="79f86-179">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="79f86-180">Wanneer u een invoer toestaan of blokkeren configureert voor een domeinpaar, worden berichten van dat domeinpaar niet meer weergegeven in het inzicht van de spoof intelligence.</span><span class="sxs-lookup"><span data-stu-id="79f86-180">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="79f86-181">Vermeldingen voor vervalste afzenders verlopen nooit.</span><span class="sxs-lookup"><span data-stu-id="79f86-181">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="79f86-182">Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="79f86-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="79f86-183">Selecteer op de pagina Lijst met tenants **toestaan/blokkeren** het tabblad **Spoofing** en klik vervolgens op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="79f86-183">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="79f86-184">Configureer **de volgende** instellingen in het fly-out Nieuwe domeinparen toevoegen dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="79f86-184">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="79f86-185">**Nieuwe domeinparen toevoegen met jokertekens:** Voer één domeinpaar per regel in, maximaal 20.</span><span class="sxs-lookup"><span data-stu-id="79f86-185">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="79f86-186">Zie de syntaxis van het domeinpaar voor vervalste afzendergegevens in de sectie [Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) verderop in dit artikel voor meer informatie over de syntaxis van vervalste afzenders.</span><span class="sxs-lookup"><span data-stu-id="79f86-186">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="79f86-187">**Type spoof:** Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="79f86-187">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="79f86-188">**Intern:** De vervalste afzender is een domein dat deel uitmaken van uw organisatie (een [geaccepteerd domein).](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="79f86-188">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="79f86-189">**Extern:** De vervalste afzender is een extern domein.</span><span class="sxs-lookup"><span data-stu-id="79f86-189">**External**: The spoofed sender is in an external domain.</span></span>

   - <span data-ttu-id="79f86-190">**Actie:** Selecteer **Toestaan** of **Blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="79f86-190">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="79f86-191">Wanneer u klaar bent, klikt u op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="79f86-191">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="79f86-192">Het beveiligings- & compliancecentrum gebruiken om items in de lijst Tenant toestaan/blokkeren weer te geven</span><span class="sxs-lookup"><span data-stu-id="79f86-192">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="79f86-193">Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="79f86-193">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="79f86-194">Selecteer het beste tabblad.</span><span class="sxs-lookup"><span data-stu-id="79f86-194">Select the tab you want.</span></span> <span data-ttu-id="79f86-195">De beschikbare kolommen zijn afhankelijk van het tabblad dat u hebt geselecteerd:</span><span class="sxs-lookup"><span data-stu-id="79f86-195">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="79f86-196">**URL's**:</span><span class="sxs-lookup"><span data-stu-id="79f86-196">**URLs**:</span></span>
     - <span data-ttu-id="79f86-197">**Waarde:** De URL.</span><span class="sxs-lookup"><span data-stu-id="79f86-197">**Value**: The URL.</span></span>
     - <span data-ttu-id="79f86-198">**Actie**: Het **waardeblok**.</span><span class="sxs-lookup"><span data-stu-id="79f86-198">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="79f86-199">**Laatst bijgewerkte datum**</span><span class="sxs-lookup"><span data-stu-id="79f86-199">**Last updated date**</span></span>
     - <span data-ttu-id="79f86-200">**Vervaldatum**</span><span class="sxs-lookup"><span data-stu-id="79f86-200">**Expiration date**</span></span>
     - <span data-ttu-id="79f86-201">**Opmerking**</span><span class="sxs-lookup"><span data-stu-id="79f86-201">**Note**</span></span>

   - <span data-ttu-id="79f86-202">**Bestanden**</span><span class="sxs-lookup"><span data-stu-id="79f86-202">**Files**</span></span>
     - <span data-ttu-id="79f86-203">**Waarde:** De bestandshash.</span><span class="sxs-lookup"><span data-stu-id="79f86-203">**Value**: The file hash.</span></span>
     - <span data-ttu-id="79f86-204">**Actie**: Het **waardeblok**.</span><span class="sxs-lookup"><span data-stu-id="79f86-204">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="79f86-205">**Laatst bijgewerkte datum**</span><span class="sxs-lookup"><span data-stu-id="79f86-205">**Last updated date**</span></span>
     - <span data-ttu-id="79f86-206">**Vervaldatum**</span><span class="sxs-lookup"><span data-stu-id="79f86-206">**Expiration date**</span></span>
     - <span data-ttu-id="79f86-207">**Opmerking**</span><span class="sxs-lookup"><span data-stu-id="79f86-207">**Note**</span></span>

   - <span data-ttu-id="79f86-208">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="79f86-208">**Spoofing**</span></span>
     - <span data-ttu-id="79f86-209">**Vervalste gebruiker**</span><span class="sxs-lookup"><span data-stu-id="79f86-209">**Spoofed user**</span></span>
     - <span data-ttu-id="79f86-210">**Verzendende infrastructuur**</span><span class="sxs-lookup"><span data-stu-id="79f86-210">**Sending infrastructure**</span></span>
     - <span data-ttu-id="79f86-211">**Spooftype:** De waarde **Intern** of **Extern**.</span><span class="sxs-lookup"><span data-stu-id="79f86-211">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="79f86-212">**Actie:** De waarde **Blokkeren of** **Toestaan.**</span><span class="sxs-lookup"><span data-stu-id="79f86-212">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="79f86-213">U kunt op een kolomkoppen klikken om in oplopende of aflopende volgorde te sorteren.</span><span class="sxs-lookup"><span data-stu-id="79f86-213">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="79f86-214">U kunt klikken op **Groep om** de resultaten te groepen.</span><span class="sxs-lookup"><span data-stu-id="79f86-214">You can click **Group** to group the results.</span></span> <span data-ttu-id="79f86-215">De waarden die beschikbaar zijn, zijn afhankelijk van het tabblad dat u hebt geselecteerd:</span><span class="sxs-lookup"><span data-stu-id="79f86-215">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="79f86-216">**URL's:** U kunt de resultaten groepen op **Actie.**</span><span class="sxs-lookup"><span data-stu-id="79f86-216">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="79f86-217">**Bestanden:** U kunt de resultaten groepren op **Actie.**</span><span class="sxs-lookup"><span data-stu-id="79f86-217">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="79f86-218">**Afzenderdomeinen voor BCL-bypass:** **Groep** is niet beschikbaar op dit tabblad.</span><span class="sxs-lookup"><span data-stu-id="79f86-218">**Sender domains for BCL bypass**: **Group** is not available on this tab.</span></span>
   - <span data-ttu-id="79f86-219">**Spoofing:** U kunt de resultaten groeperen op **Actie** of **Spooftype.**</span><span class="sxs-lookup"><span data-stu-id="79f86-219">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="79f86-220">Klik **op Zoeken,** voer een hele of een deel van een waarde in en druk vervolgens op Enter om een specifieke waarde te zoeken.</span><span class="sxs-lookup"><span data-stu-id="79f86-220">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="79f86-221">Wanneer u klaar bent, klikt u op **Zoek verwijderen Zoekpictogram** ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) verwijderen.</span><span class="sxs-lookup"><span data-stu-id="79f86-221">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

   <span data-ttu-id="79f86-222">Klik **op Filteren** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="79f86-222">Click **Filter** to filter the results.</span></span> <span data-ttu-id="79f86-223">De waarden die beschikbaar zijn in **de flyout Filter** die wordt weergegeven, zijn afhankelijk van het tabblad dat u hebt geselecteerd:</span><span class="sxs-lookup"><span data-stu-id="79f86-223">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="79f86-224">**URL's**</span><span class="sxs-lookup"><span data-stu-id="79f86-224">**URLs**</span></span>
     - <span data-ttu-id="79f86-225">**Actie**</span><span class="sxs-lookup"><span data-stu-id="79f86-225">**Action**</span></span>
     - <span data-ttu-id="79f86-226">**Nooit verlopen**</span><span class="sxs-lookup"><span data-stu-id="79f86-226">**Never expire**</span></span>
     - <span data-ttu-id="79f86-227">**Laatst bijgewerkte datum**</span><span class="sxs-lookup"><span data-stu-id="79f86-227">**Last updated date**</span></span>
     - <span data-ttu-id="79f86-228">**Vervaldatum**</span><span class="sxs-lookup"><span data-stu-id="79f86-228">**Expiration date**</span></span>

   - <span data-ttu-id="79f86-229">**Bestanden**</span><span class="sxs-lookup"><span data-stu-id="79f86-229">**Files**</span></span>
     - <span data-ttu-id="79f86-230">**Actie**</span><span class="sxs-lookup"><span data-stu-id="79f86-230">**Action**</span></span>
     - <span data-ttu-id="79f86-231">**Nooit verlopen**</span><span class="sxs-lookup"><span data-stu-id="79f86-231">**Never expire**</span></span>
     - <span data-ttu-id="79f86-232">**Laatst bijgewerkte datum**</span><span class="sxs-lookup"><span data-stu-id="79f86-232">**Last updated date**</span></span>
     - <span data-ttu-id="79f86-233">**Vervaldatum**</span><span class="sxs-lookup"><span data-stu-id="79f86-233">**Expiration date**</span></span>

   - <span data-ttu-id="79f86-234">**Afzenderdomeinen voor BCL-bypass**</span><span class="sxs-lookup"><span data-stu-id="79f86-234">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="79f86-235">**Nooit verlopen**</span><span class="sxs-lookup"><span data-stu-id="79f86-235">**Never expire**</span></span>
     - <span data-ttu-id="79f86-236">**Laatst bijgewerkte datum**</span><span class="sxs-lookup"><span data-stu-id="79f86-236">**Last updated date**</span></span>
     - <span data-ttu-id="79f86-237">**Vervaldatum**</span><span class="sxs-lookup"><span data-stu-id="79f86-237">**Expiration date**</span></span>

   - <span data-ttu-id="79f86-238">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="79f86-238">**Spoofing**</span></span>
     - <span data-ttu-id="79f86-239">**Actie**</span><span class="sxs-lookup"><span data-stu-id="79f86-239">**Action**</span></span>
     - <span data-ttu-id="79f86-240">**Spooftype**</span><span class="sxs-lookup"><span data-stu-id="79f86-240">**Spoof type**</span></span>

   <span data-ttu-id="79f86-241">Wanneer u klaar bent, klikt u op **Toepassen.**</span><span class="sxs-lookup"><span data-stu-id="79f86-241">When you're finished, click **Apply**.</span></span> <span data-ttu-id="79f86-242">Als u bestaande filters wilt wissen, klikt u **op Filter** en klikt u in het **fly-out** Filter dat wordt weergegeven op Filters **wissen.**</span><span class="sxs-lookup"><span data-stu-id="79f86-242">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="79f86-243">Gebruik het beveiligings- & compliancecentrum om items in de lijst Tenant Allow/Block te wijzigen</span><span class="sxs-lookup"><span data-stu-id="79f86-243">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="79f86-244">Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="79f86-244">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="79f86-245">Selecteer het tabblad met het type vermelding dat u wilt wijzigen:</span><span class="sxs-lookup"><span data-stu-id="79f86-245">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="79f86-246">**URL's**</span><span class="sxs-lookup"><span data-stu-id="79f86-246">**URLs**</span></span>
   - <span data-ttu-id="79f86-247">**Bestanden**</span><span class="sxs-lookup"><span data-stu-id="79f86-247">**Files**</span></span>
   - <span data-ttu-id="79f86-248">**Afzenderdomeinen voor BCL-bypass**</span><span class="sxs-lookup"><span data-stu-id="79f86-248">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="79f86-249">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="79f86-249">**Spoofing**</span></span>

3. <span data-ttu-id="79f86-250">Selecteer het item dat u wilt wijzigen en klik vervolgens op **Pictogram** ![ Bewerken ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) bewerken.</span><span class="sxs-lookup"><span data-stu-id="79f86-250">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span> <span data-ttu-id="79f86-251">De waarden die u kunt wijzigen in het flyout dat wordt weergegeven, zijn afhankelijk van het tabblad dat u in de vorige stap hebt geselecteerd:</span><span class="sxs-lookup"><span data-stu-id="79f86-251">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>

   - <span data-ttu-id="79f86-252">**URL's**</span><span class="sxs-lookup"><span data-stu-id="79f86-252">**URLs**</span></span>
     - <span data-ttu-id="79f86-253">**Nooit verlopen** en/of vervaldatum.</span><span class="sxs-lookup"><span data-stu-id="79f86-253">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="79f86-254">**Optionele notitie**</span><span class="sxs-lookup"><span data-stu-id="79f86-254">**Optional note**</span></span>

   - <span data-ttu-id="79f86-255">**Bestanden**</span><span class="sxs-lookup"><span data-stu-id="79f86-255">**Files**</span></span>
     - <span data-ttu-id="79f86-256">**Nooit verlopen** en/of vervaldatum.</span><span class="sxs-lookup"><span data-stu-id="79f86-256">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="79f86-257">**Optionele notitie**</span><span class="sxs-lookup"><span data-stu-id="79f86-257">**Optional note**</span></span>

   - <span data-ttu-id="79f86-258">**Afzenderdomeinen voor BCL-bypass**</span><span class="sxs-lookup"><span data-stu-id="79f86-258">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="79f86-259">**Nooit verlopen** en/of vervaldatum.</span><span class="sxs-lookup"><span data-stu-id="79f86-259">**Never expire** and/or expiration date.</span></span>

   - <span data-ttu-id="79f86-260">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="79f86-260">**Spoofing**</span></span>
     - <span data-ttu-id="79f86-261">**Actie:** U kunt de waarde wijzigen in **Toestaan** of **Blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="79f86-261">**Action**: You can change the value to **Allow** or **Block**.</span></span>

4. <span data-ttu-id="79f86-262">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="79f86-262">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="79f86-263">Gebruik het beveiligings- & compliancecentrum om items te verwijderen uit de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="79f86-263">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="79f86-264">Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="79f86-264">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="79f86-265">Selecteer het tabblad met het type invoer dat u wilt verwijderen:</span><span class="sxs-lookup"><span data-stu-id="79f86-265">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="79f86-266">**URL's**</span><span class="sxs-lookup"><span data-stu-id="79f86-266">**URLs**</span></span>
   - <span data-ttu-id="79f86-267">**Bestanden**</span><span class="sxs-lookup"><span data-stu-id="79f86-267">**Files**</span></span>
   - <span data-ttu-id="79f86-268">**Afzenderdomeinen voor BCL-bypass**</span><span class="sxs-lookup"><span data-stu-id="79f86-268">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="79f86-269">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="79f86-269">**Spoofing**</span></span>

3. <span data-ttu-id="79f86-270">Selecteer het item dat u wilt verwijderen en klik vervolgens op **Pictogram** ![ Verwijderen ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) verwijderen.</span><span class="sxs-lookup"><span data-stu-id="79f86-270">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="79f86-271">Klik in het waarschuwingsvenster dat wordt weergegeven op **Verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="79f86-271">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="79f86-272">Gebruik Exchange Online PowerShell of zelfstandige EOP PowerShell om de lijst met tenants toestaan/blokkeren te configureren</span><span class="sxs-lookup"><span data-stu-id="79f86-272">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="79f86-273">PowerShell gebruiken om blokbestands- of URL-vermeldingen toe te voegen aan de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="79f86-273">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="79f86-274">Gebruik de volgende syntaxis om blokbestands- of URL-vermeldingen toe te voegen aan de lijst Tenant toestaan/blokkeren:</span><span class="sxs-lookup"><span data-stu-id="79f86-274">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="79f86-275">In dit voorbeeld wordt een blokbestandsinvoer toegevoegd voor de opgegeven bestanden die nooit verlopen.</span><span class="sxs-lookup"><span data-stu-id="79f86-275">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="79f86-276">In dit voorbeeld wordt een blok-URL-vermelding voor contoso.com en alle subdomeinen (bijvoorbeeld contoso.com, www.contoso.com en xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="79f86-276">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="79f86-277">Omdat we de parameters Vervaldatum of NoExpiration niet hebben gebruikt, verloopt de vermelding na 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="79f86-277">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="79f86-278">Zie [New-TenantAllowBlockListItems voor](/powershell/module/exchange/new-tenantallowblocklistitems)gedetailleerde syntaxis en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="79f86-278">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="79f86-279">PowerShell gebruiken om vervalste afzendergegevens toe te voegen of te blokkeren aan de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="79f86-279">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="79f86-280">Gebruik de volgende syntaxis om vervalste afzendergegevens toe te voegen aan de lijst Tenant Allow/Block:</span><span class="sxs-lookup"><span data-stu-id="79f86-280">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="79f86-281">Zie [New-TenantAllowBlockListSpoofItems voor](/powershell/module/exchange/new-tenantallowblocklistspoofitems)gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="79f86-281">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="79f86-282">PowerShell gebruiken om blokbestands- of URL-items weer te geven in de lijst Tenant Allow/Block</span><span class="sxs-lookup"><span data-stu-id="79f86-282">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="79f86-283">Als u blokbestands- of URL-vermeldingen wilt weergeven in de lijst Tenant toestaan/blokkeren, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="79f86-283">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="79f86-284">In dit voorbeeld worden gegevens voor de opgegeven waarde voor bestandshash als resultaat gegeven.</span><span class="sxs-lookup"><span data-stu-id="79f86-284">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="79f86-285">In dit voorbeeld worden alle geblokkeerde URL's als retourneert.</span><span class="sxs-lookup"><span data-stu-id="79f86-285">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="79f86-286">Zie [Get-TenantAllowBlockListItems voor](/powershell/module/exchange/get-tenantallowblocklistitems)gedetailleerde syntaxis en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="79f86-286">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="79f86-287">PowerShell gebruiken om vervalste afzenders toe te staan of te blokkeren in de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="79f86-287">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="79f86-288">Gebruik de volgende syntaxis om vervalste afzendergegevens weer te geven in de lijst Tenant Allow/Block:</span><span class="sxs-lookup"><span data-stu-id="79f86-288">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="79f86-289">Dit voorbeeld retourneert alle vervalste afzendergegevens in de lijst Tenant toestaan/blokkeren.</span><span class="sxs-lookup"><span data-stu-id="79f86-289">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="79f86-290">Dit voorbeeld retourneert alle toegestane vermeldingen van vervalste afzenders die intern zijn.</span><span class="sxs-lookup"><span data-stu-id="79f86-290">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="79f86-291">In dit voorbeeld worden alle geblokkeerde vermeldingen van vervalste afzenders die extern zijn, als retourneert.</span><span class="sxs-lookup"><span data-stu-id="79f86-291">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="79f86-292">Zie [Get-TenantAllowBlockListSpoofItems (Get-TenantAllowBlockListSpoofItems)](/powershell/module/exchange/get-tenantallowblocklistspoofitems)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="79f86-292">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="79f86-293">PowerShell gebruiken om blokbestands- en URL-items in de lijst Tenant allow/block te wijzigen</span><span class="sxs-lookup"><span data-stu-id="79f86-293">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="79f86-294">Gebruik de volgende syntaxis om blokbestands- en URL-vermeldingen in de lijst Tenant toestaan/blokkeren te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="79f86-294">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="79f86-295">In dit voorbeeld wordt de vervaldatum van de opgegeven blok-URL-vermelding gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="79f86-295">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="79f86-296">Zie [Set-TenantAllowBlockListItems (Set-TenantAllowBlockListItems)](/powershell/module/exchange/set-tenantallowblocklistitems)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="79f86-296">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="79f86-297">PowerShell gebruiken om vervalste afzenders toe te staan of te blokkeren in de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="79f86-297">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="79f86-298">Gebruik de volgende syntaxis om vervalste afzendergegevens in de lijst Tenant Allow/Block te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="79f86-298">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="79f86-299">In dit voorbeeld wordt de vermelding van vervalste afzenders gewijzigd in toestaan om te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="79f86-299">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="79f86-300">Zie [Set-TenantAllowBlockListSpoofItems (Set-TenantAllowBlockListSpoofItems)](/powershell/module/exchange/set-tenantallowblocklistspoofitems)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="79f86-300">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="79f86-301">PowerShell gebruiken om URL- of bestandsgegevens te verwijderen uit de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="79f86-301">Use PowerShell to remove URL or file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="79f86-302">Gebruik de volgende syntaxis om bestands- en URL-vermeldingen te verwijderen uit de lijst Tenant toestaan/blokkeren:</span><span class="sxs-lookup"><span data-stu-id="79f86-302">To remove file and URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="79f86-303">In dit voorbeeld wordt de opgegeven blok-URL-vermelding verwijderd uit de lijst Tenant toestaan/blokkeren.</span><span class="sxs-lookup"><span data-stu-id="79f86-303">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="79f86-304">Zie [Remove-TenantAllowBlockListItems (Verwijderen-TenantAllowBlockListItems)](/powershell/module/exchange/remove-tenantallowblocklistitems)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="79f86-304">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="79f86-305">PowerShell gebruiken om vervalste afzenders toe te staan of te blokkeren uit de tenantlijst toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="79f86-305">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="79f86-306">Gebruik de volgende syntaxis als u spoofing sender items wilt verwijderen uit de tenant allow/block list:</span><span class="sxs-lookup"><span data-stu-id="79f86-306">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="79f86-307">Zie [Remove-TenantAllowBlockListSpoofItems (Verwijderen-TenantAllowBlockListSpoofItems)](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="79f86-307">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="79f86-308">URL-syntaxis voor de lijst Toestaan/blokkeren van tenant</span><span class="sxs-lookup"><span data-stu-id="79f86-308">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="79f86-309">IP4v- en IPv6-adressen zijn toegestaan, maar TCP/UDP-poorten niet.</span><span class="sxs-lookup"><span data-stu-id="79f86-309">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="79f86-310">Bestandsnaamextensies zijn niet toegestaan (bijvoorbeeld test.pdf).</span><span class="sxs-lookup"><span data-stu-id="79f86-310">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="79f86-311">Unicode wordt niet ondersteund, maar Punycode wel.</span><span class="sxs-lookup"><span data-stu-id="79f86-311">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="79f86-312">Hostnamen zijn toegestaan als alle volgende instructies waar zijn:</span><span class="sxs-lookup"><span data-stu-id="79f86-312">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="79f86-313">De hostnaam bevat een punt.</span><span class="sxs-lookup"><span data-stu-id="79f86-313">The hostname contains a period.</span></span>
  - <span data-ttu-id="79f86-314">Er is ten minste één teken links van de periode.</span><span class="sxs-lookup"><span data-stu-id="79f86-314">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="79f86-315">Er zijn ten minste twee tekens rechts van de periode.</span><span class="sxs-lookup"><span data-stu-id="79f86-315">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="79f86-316">Is bijvoorbeeld `t.co` toegestaan of `.com` niet `contoso.` toegestaan.</span><span class="sxs-lookup"><span data-stu-id="79f86-316">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="79f86-317">Subpathen worden niet geïmpliceerd.</span><span class="sxs-lookup"><span data-stu-id="79f86-317">Subpaths are not implied.</span></span>

  <span data-ttu-id="79f86-318">Bevat bijvoorbeeld `contoso.com` geen `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="79f86-318">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="79f86-319">Jokertekens (\*) zijn toegestaan in de volgende scenario's:</span><span class="sxs-lookup"><span data-stu-id="79f86-319">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="79f86-320">Een linker jokerteken moet worden gevolgd door een punt om een subdomein op te geven.</span><span class="sxs-lookup"><span data-stu-id="79f86-320">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="79f86-321">Is bijvoorbeeld `*.contoso.com` toegestaan; `*contoso.com` is niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="79f86-321">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="79f86-322">Een jokerteken rechts moet een slash (/) volgen om een pad op te geven.</span><span class="sxs-lookup"><span data-stu-id="79f86-322">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="79f86-323">Is bijvoorbeeld `contoso.com/*` toegestaan of `contoso.com*` niet `contoso.com/ab*` toegestaan.</span><span class="sxs-lookup"><span data-stu-id="79f86-323">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="79f86-324">Alle subpathen worden niet geïmpliceerd door een rechter jokerteken.</span><span class="sxs-lookup"><span data-stu-id="79f86-324">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="79f86-325">Bevat bijvoorbeeld `contoso.com/*` geen `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="79f86-325">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="79f86-326">`*.com*` ongeldig is (geen op te lossen domein en het jokerteken rechts volgt geen slash voor vooruit).</span><span class="sxs-lookup"><span data-stu-id="79f86-326">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="79f86-327">Jokertekens zijn niet toegestaan in IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="79f86-327">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="79f86-328">Het tildeteken (~) is beschikbaar in de volgende scenario's:</span><span class="sxs-lookup"><span data-stu-id="79f86-328">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="79f86-329">Een linker tilde houdt een domein en alle subdomeinen in.</span><span class="sxs-lookup"><span data-stu-id="79f86-329">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="79f86-330">Bijvoorbeeld inclusief `~contoso.com` `contoso.com` en `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="79f86-330">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="79f86-331">URL-vermeldingen die protocollen bevatten (bijvoorbeeld , of ) mislukken, omdat URL-vermeldingen van toepassing zijn `http://` `https://` op alle `ftp://` protocollen.</span><span class="sxs-lookup"><span data-stu-id="79f86-331">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="79f86-332">Een gebruikersnaam of wachtwoord wordt niet ondersteund of vereist.</span><span class="sxs-lookup"><span data-stu-id="79f86-332">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="79f86-333">Aanhalingstekens (' of ") zijn ongeldige tekens.</span><span class="sxs-lookup"><span data-stu-id="79f86-333">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="79f86-334">Een URL moet waar mogelijk alle omleidingen bevatten.</span><span class="sxs-lookup"><span data-stu-id="79f86-334">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="79f86-335">Scenario's voor URL-invoer</span><span class="sxs-lookup"><span data-stu-id="79f86-335">URL entry scenarios</span></span>

<span data-ttu-id="79f86-336">Geldige URL-vermeldingen en de resultaten worden beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="79f86-336">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="79f86-337">Scenario: Geen jokertekens</span><span class="sxs-lookup"><span data-stu-id="79f86-337">Scenario: No wildcards</span></span>

<span data-ttu-id="79f86-338">**Vermelding**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="79f86-338">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="79f86-339">**Overeenkomst toestaan**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-339">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="79f86-340">**Niet-overeenkomende toestaan:**</span><span class="sxs-lookup"><span data-stu-id="79f86-340">**Allow not matched**:</span></span>

  - <span data-ttu-id="79f86-341">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-341">abc-contoso.com</span></span>
  - <span data-ttu-id="79f86-342">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="79f86-342">contoso.com/a</span></span>
  - <span data-ttu-id="79f86-343">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-343">payroll.contoso.com</span></span>
  - <span data-ttu-id="79f86-344">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-344">test.com/contoso.com</span></span>
  - <span data-ttu-id="79f86-345">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-345">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="79f86-346">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-346">www.contoso.com</span></span>
  - <span data-ttu-id="79f86-347">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-347">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="79f86-348">**Blok overeenkomst**:</span><span class="sxs-lookup"><span data-stu-id="79f86-348">**Block match**:</span></span>

  - <span data-ttu-id="79f86-349">contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-349">contoso.com</span></span>
  - <span data-ttu-id="79f86-350">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="79f86-350">contoso.com/a</span></span>
  - <span data-ttu-id="79f86-351">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-351">payroll.contoso.com</span></span>
  - <span data-ttu-id="79f86-352">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-352">test.com/contoso.com</span></span>
  - <span data-ttu-id="79f86-353">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-353">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="79f86-354">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-354">www.contoso.com</span></span>
  - <span data-ttu-id="79f86-355">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-355">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="79f86-356">**Blok niet overeenkomend**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-356">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="79f86-357">Scenario: Jokerteken links (subdomein)</span><span class="sxs-lookup"><span data-stu-id="79f86-357">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="79f86-358">**Vermelding**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="79f86-358">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="79f86-359">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="79f86-359">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="79f86-360">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-360">www.contoso.com</span></span>
  - <span data-ttu-id="79f86-361">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-361">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="79f86-362">**Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**</span><span class="sxs-lookup"><span data-stu-id="79f86-362">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="79f86-363">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-363">123contoso.com</span></span>
  - <span data-ttu-id="79f86-364">contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-364">contoso.com</span></span>
  - <span data-ttu-id="79f86-365">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-365">test.com/contoso.com</span></span>
  - <span data-ttu-id="79f86-366">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="79f86-366">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="79f86-367">Scenario: Jokerteken rechts boven aan pad</span><span class="sxs-lookup"><span data-stu-id="79f86-367">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="79f86-368">**Vermelding**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="79f86-368">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="79f86-369">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="79f86-369">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="79f86-370">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="79f86-370">contoso.com/a/b</span></span>
  - <span data-ttu-id="79f86-371">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="79f86-371">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="79f86-372">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="79f86-372">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="79f86-373">**Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**</span><span class="sxs-lookup"><span data-stu-id="79f86-373">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="79f86-374">contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-374">contoso.com</span></span>
  - <span data-ttu-id="79f86-375">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="79f86-375">contoso.com/a</span></span>
  - <span data-ttu-id="79f86-376">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-376">www.contoso.com</span></span>
  - <span data-ttu-id="79f86-377">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-377">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="79f86-378">Scenario: Tilde links</span><span class="sxs-lookup"><span data-stu-id="79f86-378">Scenario: Left tilde</span></span>

<span data-ttu-id="79f86-379">**Vermelding**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="79f86-379">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="79f86-380">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="79f86-380">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="79f86-381">contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-381">contoso.com</span></span>
  - <span data-ttu-id="79f86-382">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-382">www.contoso.com</span></span>
  - <span data-ttu-id="79f86-383">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-383">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="79f86-384">**Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**</span><span class="sxs-lookup"><span data-stu-id="79f86-384">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="79f86-385">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-385">123contoso.com</span></span>
  - <span data-ttu-id="79f86-386">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="79f86-386">contoso.com/abc</span></span>
  - <span data-ttu-id="79f86-387">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="79f86-387">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="79f86-388">Scenario: Het achtervoegsel van het jokerteken rechts</span><span class="sxs-lookup"><span data-stu-id="79f86-388">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="79f86-389">**Vermelding**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="79f86-389">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="79f86-390">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="79f86-390">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="79f86-391">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="79f86-391">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="79f86-392">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="79f86-392">contoso.com/a</span></span>
  - <span data-ttu-id="79f86-393">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="79f86-393">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="79f86-394">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="79f86-394">contoso.com/ab</span></span>
  - <span data-ttu-id="79f86-395">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="79f86-395">contoso.com/b</span></span>
  - <span data-ttu-id="79f86-396">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="79f86-396">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="79f86-397">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="79f86-397">contoso.com/ba</span></span>

- <span data-ttu-id="79f86-398">**Niet-overeenkomende en** **niet-overeenkomende** blokkering toestaan: contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-398">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="79f86-399">Scenario: Linker jokertekensubdomein en rechterachtervoegsel jokerteken</span><span class="sxs-lookup"><span data-stu-id="79f86-399">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="79f86-400">**Vermelding**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="79f86-400">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="79f86-401">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="79f86-401">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="79f86-402">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="79f86-402">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="79f86-403">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="79f86-403">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="79f86-404">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="79f86-404">www.contoso.com/a</span></span>
  - <span data-ttu-id="79f86-405">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="79f86-405">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="79f86-406">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="79f86-406">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="79f86-407">**Niet-overeenkomende en** **niet-overeenkomende** blokkering toestaan : contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="79f86-407">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="79f86-408">Scenario: Tilde links en rechts</span><span class="sxs-lookup"><span data-stu-id="79f86-408">Scenario: Left and right tilde</span></span>

<span data-ttu-id="79f86-409">**Vermelding**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="79f86-409">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="79f86-410">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="79f86-410">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="79f86-411">contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-411">contoso.com</span></span>
  - <span data-ttu-id="79f86-412">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="79f86-412">contoso.com/a</span></span>
  - <span data-ttu-id="79f86-413">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-413">www.contoso.com</span></span>
  - <span data-ttu-id="79f86-414">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="79f86-414">www.contoso.com/b</span></span>
  - <span data-ttu-id="79f86-415">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-415">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="79f86-416">**Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**</span><span class="sxs-lookup"><span data-stu-id="79f86-416">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="79f86-417">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-417">123contoso.com</span></span>
  - <span data-ttu-id="79f86-418">contoso.org</span><span class="sxs-lookup"><span data-stu-id="79f86-418">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="79f86-419">Scenario: IP-adres</span><span class="sxs-lookup"><span data-stu-id="79f86-419">Scenario: IP address</span></span>

<span data-ttu-id="79f86-420">**Vermelding**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="79f86-420">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="79f86-421">**Overeenkomst toestaan** **en overeenkomst blokkeren**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="79f86-421">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="79f86-422">**Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**</span><span class="sxs-lookup"><span data-stu-id="79f86-422">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="79f86-423">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="79f86-423">1.2.3.4/a</span></span>
  - <span data-ttu-id="79f86-424">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="79f86-424">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="79f86-425">IP-adres met jokerteken rechts</span><span class="sxs-lookup"><span data-stu-id="79f86-425">IP address with right wildcard</span></span>

<span data-ttu-id="79f86-426">**Vermelding**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="79f86-426">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="79f86-427">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="79f86-427">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="79f86-428">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="79f86-428">1.2.3.4/b</span></span>
  - <span data-ttu-id="79f86-429">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="79f86-429">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="79f86-430">Voorbeelden van ongeldige vermeldingen</span><span class="sxs-lookup"><span data-stu-id="79f86-430">Examples of invalid entries</span></span>

<span data-ttu-id="79f86-431">De volgende vermeldingen zijn ongeldig:</span><span class="sxs-lookup"><span data-stu-id="79f86-431">The following entries are invalid:</span></span>

- <span data-ttu-id="79f86-432">**Ontbrekende of ongeldige domeinwaarden:**</span><span class="sxs-lookup"><span data-stu-id="79f86-432">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="79f86-433">contoso</span><span class="sxs-lookup"><span data-stu-id="79f86-433">contoso</span></span>
  - <span data-ttu-id="79f86-434">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="79f86-434">\*.contoso.\*</span></span>
  - <span data-ttu-id="79f86-435">\*.com</span><span class="sxs-lookup"><span data-stu-id="79f86-435">\*.com</span></span>
  - <span data-ttu-id="79f86-436">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="79f86-436">\*.pdf</span></span>

- <span data-ttu-id="79f86-437">**Jokerteken op tekst of zonder spatiëringstekens:**</span><span class="sxs-lookup"><span data-stu-id="79f86-437">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="79f86-438">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="79f86-438">\*contoso.com</span></span>
  - <span data-ttu-id="79f86-439">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="79f86-439">contoso.com\*</span></span>
  - <span data-ttu-id="79f86-440">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="79f86-440">\*1.2.3.4</span></span>
  - <span data-ttu-id="79f86-441">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="79f86-441">1.2.3.4\*</span></span>
  - <span data-ttu-id="79f86-442">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="79f86-442">contoso.com/a\*</span></span>
  - <span data-ttu-id="79f86-443">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="79f86-443">contoso.com/ab\*</span></span>

- <span data-ttu-id="79f86-444">**IP-adressen met poorten:**</span><span class="sxs-lookup"><span data-stu-id="79f86-444">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="79f86-445">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="79f86-445">contoso.com:443</span></span>
  - <span data-ttu-id="79f86-446">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="79f86-446">abc.contoso.com:25</span></span>

- <span data-ttu-id="79f86-447">**Niet-beschrijvende jokertekens:**</span><span class="sxs-lookup"><span data-stu-id="79f86-447">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="79f86-448">\*.\*</span><span class="sxs-lookup"><span data-stu-id="79f86-448">\*.\*</span></span>

- <span data-ttu-id="79f86-449">**Middelste jokertekens:**</span><span class="sxs-lookup"><span data-stu-id="79f86-449">**Middle wildcards**:</span></span>

  - <span data-ttu-id="79f86-450">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="79f86-450">conto\*so.com</span></span>
  - <span data-ttu-id="79f86-451">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="79f86-451">conto~so.com</span></span>

- <span data-ttu-id="79f86-452">**Dubbele jokertekens**</span><span class="sxs-lookup"><span data-stu-id="79f86-452">**Double wildcards**</span></span>

  - <span data-ttu-id="79f86-453">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="79f86-453">contoso.com/\*\*</span></span>
  - <span data-ttu-id="79f86-454">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="79f86-454">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="79f86-455">Syntaxis van domeinparen voor vervalste afzendergegevens in de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="79f86-455">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="79f86-456">Een domeinpaar voor een vervalste afzender in de lijst Tenant toestaan/blokkeren gebruikt de volgende syntaxis: `<Spoofed user>, <Sending infrastructure>` .</span><span class="sxs-lookup"><span data-stu-id="79f86-456">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="79f86-457">**Vervalste gebruiker:** Deze waarde betreft het e-mailadres van de vervalste gebruiker die wordt weergegeven in het vak **Van** in e-mail clients.</span><span class="sxs-lookup"><span data-stu-id="79f86-457">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="79f86-458">Dit adres wordt ook wel het adres `5322.From` genoemd.</span><span class="sxs-lookup"><span data-stu-id="79f86-458">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="79f86-459">Geldige waarden zijn:</span><span class="sxs-lookup"><span data-stu-id="79f86-459">Valid values include:</span></span>
  - <span data-ttu-id="79f86-460">Een afzonderlijk e-mailadres (bijvoorbeeld chris@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="79f86-460">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="79f86-461">Een e-maildomein (bijvoorbeeld contoso.com).</span><span class="sxs-lookup"><span data-stu-id="79f86-461">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="79f86-462">Het jokerteken \* (bijvoorbeeld).</span><span class="sxs-lookup"><span data-stu-id="79f86-462">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="79f86-463">**Verzendende infrastructuur:** deze waarde geeft de bron aan van berichten van de vervalste gebruiker.</span><span class="sxs-lookup"><span data-stu-id="79f86-463">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="79f86-464">Geldige waarden zijn:</span><span class="sxs-lookup"><span data-stu-id="79f86-464">Valid values include:</span></span>
  - <span data-ttu-id="79f86-465">Het domein dat is gevonden in een REVERSE DNS lookup (PTR-record) van het IP-adres van de bron-e-mailserver (bijvoorbeeld fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="79f86-465">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="79f86-466">Als het bron-IP-adres geen PTR-record heeft, wordt de verzendende infrastructuur geïdentificeerd als \<source IP\> /24 (bijvoorbeeld 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="79f86-466">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="79f86-467">Hier zijn enkele voorbeelden van geldige domeinparen om vervalste afzenders te identificeren:</span><span class="sxs-lookup"><span data-stu-id="79f86-467">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="79f86-468">Het maximum aantal vervalste afzenders is 1000.</span><span class="sxs-lookup"><span data-stu-id="79f86-468">The maximum number of spoofed sender entries is 1000.</span></span> 

<span data-ttu-id="79f86-469">Als u een domeinpaar toevoegt, wordt  de *combinatie* van de vervalste gebruiker en de verzendende infrastructuur alleen mogelijk of blokkeert.</span><span class="sxs-lookup"><span data-stu-id="79f86-469">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="79f86-470">E-mail van de vervalste gebruiker van welke bron dan ook is niet toegestaan en e-mail uit de bron van de verzendende infrastructuur wordt niet toegestaan voor vervalste gebruikers.</span><span class="sxs-lookup"><span data-stu-id="79f86-470">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span> 

<span data-ttu-id="79f86-471">U voegt bijvoorbeeld een toegestane vermelding toe voor het volgende domeinpaar:</span><span class="sxs-lookup"><span data-stu-id="79f86-471">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="79f86-472">**Domein:** gmail.com</span><span class="sxs-lookup"><span data-stu-id="79f86-472">**Domain**: gmail.com</span></span>
- <span data-ttu-id="79f86-473">**Infrastructuur**: tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="79f86-473">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="79f86-474">Alleen berichten uit dat domein *en het* verzenden van infrastructuurparen mogen spoofen.</span><span class="sxs-lookup"><span data-stu-id="79f86-474">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="79f86-475">Andere afzenders die proberen te spoofen gmail.com zijn niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="79f86-475">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="79f86-476">Berichten van afzenders in andere domeinen die afkomstig zijn van tms.mx.com worden gecontroleerd door spoof intelligence.</span><span class="sxs-lookup"><span data-stu-id="79f86-476">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
