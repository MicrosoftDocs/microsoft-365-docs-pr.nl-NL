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
ms.openlocfilehash: 1548eda760b7b6b19214cb834d7fc43357dc0357
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985490"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="9be32-103">Tenant Toestaan/Blokkeren-lijst beheren</span><span class="sxs-lookup"><span data-stu-id="9be32-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9be32-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="9be32-104">**Applies to**</span></span>
- [<span data-ttu-id="9be32-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9be32-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9be32-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="9be32-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9be32-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9be32-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="9be32-108">De functies die in dit artikel worden beschreven, zijn in Preview, kunnen worden gewijzigd en zijn niet beschikbaar in alle organisaties.</span><span class="sxs-lookup"><span data-stu-id="9be32-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="9be32-109">Als uw organisatie niet beschikt over de spooffuncties zoals beschreven in dit artikel, bekijkt u de oudere spoofbeheerervaring bij Vervalste afzenders beheren met behulp van het spoof intelligence-beleid en het inzicht in spoof [intelligence in EOP.](walkthrough-spoof-intelligence-insight.md)</span><span class="sxs-lookup"><span data-stu-id="9be32-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="9be32-110">U kunt op dit **moment geen** toegestane URL- of bestandsitems configureren in de lijst Tenant toestaan/blokkeren.</span><span class="sxs-lookup"><span data-stu-id="9be32-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="9be32-111">In Microsoft 365 organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken, kunt u het niet eens zijn met de uitspraak over EOP-filtering.</span><span class="sxs-lookup"><span data-stu-id="9be32-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="9be32-112">Een goed bericht kan bijvoorbeeld worden gemarkeerd als slecht (een onwaar positief) of een slecht bericht kan worden toegestaan (een onwaar negatief).</span><span class="sxs-lookup"><span data-stu-id="9be32-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="9be32-113">Met de tenantlijst Toestaan/blokkeren in de Microsoft 365 Defender portal kunt u handmatig de Microsoft 365 filteren.</span><span class="sxs-lookup"><span data-stu-id="9be32-113">The Tenant Allow/Block List in the Microsoft 365 Defender portal gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="9be32-114">De lijst Tenant toestaan/blokkeren wordt gebruikt tijdens de e-mailstroom en op het moment dat de gebruiker klikt.</span><span class="sxs-lookup"><span data-stu-id="9be32-114">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="9be32-115">U kunt de volgende typen overschrijven opgeven:</span><span class="sxs-lookup"><span data-stu-id="9be32-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="9be32-116">URL's die u wilt blokkeren.</span><span class="sxs-lookup"><span data-stu-id="9be32-116">URLs to block.</span></span>
- <span data-ttu-id="9be32-117">Bestanden die u wilt blokkeren.</span><span class="sxs-lookup"><span data-stu-id="9be32-117">Files to block.</span></span>
- <span data-ttu-id="9be32-118">Vervalste afzenders om dit toe te staan of te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="9be32-118">Spoofed senders to allow or block.</span></span> <span data-ttu-id="9be32-119">Als u de uitspraak toestaan of blokkeren overschrijven in het inzicht van spoof [intelligence,](learn-about-spoof-intelligence.md)wordt de vervalste afzender een handmatige invoer toestaan of blokkeren die alleen wordt weergegeven op het tabblad **Spoof** in de lijst Toestaan/blokkeren van tenants.</span><span class="sxs-lookup"><span data-stu-id="9be32-119">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="9be32-120">U kunt hier ook handmatig vermeldingen voor vervalste afzenders maken of blokkeren voordat ze worden gedetecteerd door spoofinformatie.</span><span class="sxs-lookup"><span data-stu-id="9be32-120">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="9be32-121">In dit artikel wordt beschreven hoe u vermeldingen configureert in de lijst Tenant toestaan/blokkeren in de Microsoft 365 Defender-portal of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).</span><span class="sxs-lookup"><span data-stu-id="9be32-121">This article describes how to configure entries in the Tenant Allow/Block List in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9be32-122">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="9be32-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9be32-123">U opent de Microsoft 365 Defender-portal bij <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="9be32-123">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="9be32-124">Als u rechtstreeks naar de **pagina Lijst met tenants toestaan/blokkeren** wilt gaan, gebruikt <https://security.microsoft.com/tenantAllowBlockList> u .</span><span class="sxs-lookup"><span data-stu-id="9be32-124">To go directly to the **Tenant Allow/Block Lists** page, use <https://security.microsoft.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="9be32-125">U geeft bestanden op met de hashwaarde SHA256 van het bestand.</span><span class="sxs-lookup"><span data-stu-id="9be32-125">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="9be32-126">Als u de hashwaarde SHA256 van een bestand in Windows wilt zoeken, voer u de volgende opdracht uit in een opdrachtprompt:</span><span class="sxs-lookup"><span data-stu-id="9be32-126">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="9be32-127">Een voorbeeldwaarde is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="9be32-127">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="9be32-128">Perceptuele hashwaarden (pHash) worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="9be32-128">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="9be32-129">De beschikbare URL-waarden worden beschreven in de syntaxis van de URL voor de sectie Lijst met tenants [toestaan/blokkeren](#url-syntax-for-the-tenant-allowblock-list) verderop in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="9be32-129">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="9be32-130">De lijst Tenant toestaan/blokkeren staat maximaal 500 vermeldingen voor URL's en 500 vermeldingen voor bestandshashes toe.</span><span class="sxs-lookup"><span data-stu-id="9be32-130">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="9be32-131">Het maximum aantal tekens voor elke vermelding is:</span><span class="sxs-lookup"><span data-stu-id="9be32-131">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="9be32-132">Bestandshashes = 64</span><span class="sxs-lookup"><span data-stu-id="9be32-132">File hashes = 64</span></span>
  - <span data-ttu-id="9be32-133">URL = 250</span><span class="sxs-lookup"><span data-stu-id="9be32-133">URL = 250</span></span>

- <span data-ttu-id="9be32-134">Een item moet binnen 30 minuten actief zijn.</span><span class="sxs-lookup"><span data-stu-id="9be32-134">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="9be32-135">Standaard verlopen vermeldingen in de lijst Tenant toestaan/blokkeren na 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="9be32-135">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="9be32-136">U kunt een datum opgeven of instellen dat deze nooit verloopt.</span><span class="sxs-lookup"><span data-stu-id="9be32-136">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="9be32-137">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9be32-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="9be32-138">Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9be32-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="9be32-139">U moet over toegewezen machtigingen beschikken in Exchange Online voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="9be32-139">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="9be32-140">**URL's en bestanden:**</span><span class="sxs-lookup"><span data-stu-id="9be32-140">**URLs and files**:</span></span>
    - <span data-ttu-id="9be32-141">Als u waarden wilt toevoegen en verwijderen uit de lijst Tenant toestaan/blokkeren, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="9be32-141">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="9be32-142">Voor alleen-lezen toegang tot de tenantlijst toestaan/blokkeren moet  u lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="9be32-142">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="9be32-143">**Spoofing:** Een van de volgende combinaties:</span><span class="sxs-lookup"><span data-stu-id="9be32-143">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="9be32-144">**Organisatiebeheer**</span><span class="sxs-lookup"><span data-stu-id="9be32-144">**Organization Management**</span></span>
    - <span data-ttu-id="9be32-145">**Beveiligingsbeheerder** <u>en</u> **Alleen-weergeven-configuratie** of **Alleen-weergeven organisatiebeheer**.</span><span class="sxs-lookup"><span data-stu-id="9be32-145">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="9be32-146">Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9be32-146">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="9be32-147">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9be32-147">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="9be32-148">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9be32-148">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="9be32-149">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="9be32-149">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9be32-150">Gebruik de Microsoft 365 Defender portal om blok-URL-vermeldingen te maken in de lijst Tenant Allow/Block</span><span class="sxs-lookup"><span data-stu-id="9be32-150">Use the Microsoft 365 Defender portal to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="9be32-151">Ga in Microsoft 365 Defender portal naar **Beleidsregels & sectie** \> **Bedreigingsbeleidsregels** \>  \> **tenantlijsten toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="9be32-151">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9be32-152">Controleer op de pagina Lijst met tenants **toestaan/blokkeren** of het tabblad **URL's** is geselecteerd en klik vervolgens op ![ Pictogram blokkeren ](../../media/m365-cc-sc-create-icon.png) **blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="9be32-152">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click ![Block icon](../../media/m365-cc-sc-create-icon.png) **Block**.</span></span>

3. <span data-ttu-id="9be32-153">Configureer **de volgende** instellingen in het flyout URL's blokkeren dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="9be32-153">In the **Block URLs** flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="9be32-154">**URL's met jokertekens toevoegen:** Voer één URL per regel in, maximaal 20.</span><span class="sxs-lookup"><span data-stu-id="9be32-154">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="9be32-155">Zie de syntaxis van de URL voor de sectie Lijst met tenants [toestaan/blokkeren](#url-syntax-for-the-tenant-allowblock-list) verderop in dit artikel voor meer informatie over de syntaxis van URL-vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="9be32-155">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>
   - <span data-ttu-id="9be32-156">**Nooit verlopen:** Ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="9be32-156">**Never expire**: Do one of the following steps:</span></span>
     - <span data-ttu-id="9be32-157">Controleer of de instelling is uitgeschakeld (schakel uit) en gebruik het vak Verwijderen aan om de vervaldatum voor de ![ ](../../media/scc-toggle-off.png) vermeldingen op te geven. </span><span class="sxs-lookup"><span data-stu-id="9be32-157">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Remove on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="9be32-158">of</span><span class="sxs-lookup"><span data-stu-id="9be32-158">or</span></span>

     - <span data-ttu-id="9be32-159">Verplaats de schakelknop naar rechts om de items zo te configureren dat ze nooit verlopen:</span><span class="sxs-lookup"><span data-stu-id="9be32-159">Move the toggle to the right to configure the entries to never expire:</span></span> ![Inschakelen](../../media/scc-toggle-on.png)<span data-ttu-id="9be32-161">.</span><span class="sxs-lookup"><span data-stu-id="9be32-161">.</span></span>
   - <span data-ttu-id="9be32-162">**Optionele opmerking:** Voer beschrijvende tekst in voor de vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="9be32-162">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="9be32-163">Wanneer u klaar bent, klikt u op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="9be32-163">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9be32-164">Gebruik de Microsoft 365 Defender portal om blokbestandsgegevens te maken in de lijst Tenant Allow/Block</span><span class="sxs-lookup"><span data-stu-id="9be32-164">Use the Microsoft 365 Defender portal to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="9be32-165">Ga in Microsoft 365 Defender portal naar **Beleidsregels & sectie** \> **Bedreigingsbeleidsregels** \>  \> **tenantlijsten toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="9be32-165">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9be32-166">Selecteer op de pagina Lijst met  **tenants toestaan/blokkeren** het tabblad Bestanden en klik vervolgens op ![ Pictogram blokkeren ](../../media/m365-cc-sc-create-icon.png) **blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="9be32-166">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click ![Block icon](../../media/m365-cc-sc-create-icon.png) **Block**.</span></span>

3. <span data-ttu-id="9be32-167">Configureer **de volgende** instellingen in de flyout Bestanden blokkeren die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="9be32-167">In the **Block files** flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="9be32-168">**Bestandshashes toevoegen:** Voer één SHA256-hashwaarde per regel in, maximaal 20.</span><span class="sxs-lookup"><span data-stu-id="9be32-168">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>
   - <span data-ttu-id="9be32-169">**Nooit verlopen:** Ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="9be32-169">**Never expire**: Do one of the following steps:</span></span>
     - <span data-ttu-id="9be32-170">Controleer of de instelling is uitgeschakeld (schakel uit) en gebruik het vak Verwijderen aan om de vervaldatum voor de ![ ](../../media/scc-toggle-off.png) vermeldingen op te geven. </span><span class="sxs-lookup"><span data-stu-id="9be32-170">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Remove on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="9be32-171">of</span><span class="sxs-lookup"><span data-stu-id="9be32-171">or</span></span>

     - <span data-ttu-id="9be32-172">Verplaats de schakelknop naar rechts om de items zo te configureren dat ze nooit verlopen:</span><span class="sxs-lookup"><span data-stu-id="9be32-172">Move the toggle to the right to configure the entries to never expire:</span></span> ![Inschakelen](../../media/scc-toggle-on.png)<span data-ttu-id="9be32-174">.</span><span class="sxs-lookup"><span data-stu-id="9be32-174">.</span></span>
   - <span data-ttu-id="9be32-175">**Optionele opmerking:** Voer beschrijvende tekst in voor de vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="9be32-175">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="9be32-176">Wanneer u klaar bent, klikt u op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="9be32-176">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9be32-177">Gebruik de Microsoft 365 Defender portal om vervalste afzendergegevens in de lijst Toestaan/blokkeren van tenants toe te staan of te blokkeren</span><span class="sxs-lookup"><span data-stu-id="9be32-177">Use the Microsoft 365 Defender portal to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="9be32-178">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="9be32-178">**Notes**:</span></span>

- <span data-ttu-id="9be32-179">Alleen de _combinatie_ van de vervalste _gebruiker_ en de verzendende infrastructuur zoals gedefinieerd in het domeinpaar is specifiek toegestaan of geblokkeerd voor spoofing.</span><span class="sxs-lookup"><span data-stu-id="9be32-179">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="9be32-180">Wanneer u een invoer toestaan of blokkeren configureert voor een domeinpaar, worden berichten van dat domeinpaar niet meer weergegeven in het inzicht van de spoof intelligence.</span><span class="sxs-lookup"><span data-stu-id="9be32-180">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="9be32-181">Vermeldingen voor vervalste afzenders verlopen nooit.</span><span class="sxs-lookup"><span data-stu-id="9be32-181">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="9be32-182">Ga in Microsoft 365 Defender portal naar **Beleidsregels & sectie** \> **Bedreigingsbeleidsregels** \>  \> **tenantlijsten toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="9be32-182">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9be32-183">Selecteer op de pagina Lijst met tenants **toestaan/blokkeren** het tabblad **Spoofing** en klik vervolgens op ![ Pictogram Toevoegen ](../../media/m365-cc-sc-create-icon.png) **blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="9be32-183">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click ![Block icon](../../media/m365-cc-sc-create-icon.png) **Add**.</span></span>

3. <span data-ttu-id="9be32-184">Configureer **de volgende** instellingen in het fly-out Nieuwe domeinparen toevoegen dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="9be32-184">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="9be32-185">**Nieuwe domeinparen toevoegen met jokertekens:** Voer één domeinpaar per regel in, maximaal 20.</span><span class="sxs-lookup"><span data-stu-id="9be32-185">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="9be32-186">Zie de syntaxis van het domeinpaar voor vervalste afzendergegevens in de sectie [Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) verderop in dit artikel voor meer informatie over de syntaxis van vervalste afzenders.</span><span class="sxs-lookup"><span data-stu-id="9be32-186">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>
   - <span data-ttu-id="9be32-187">**Type spoof:** Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="9be32-187">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="9be32-188">**Intern:** De vervalste afzender is een domein dat deel uitmaken van uw organisatie (een [geaccepteerd domein).](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="9be32-188">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="9be32-189">**Extern:** De vervalste afzender is een extern domein.</span><span class="sxs-lookup"><span data-stu-id="9be32-189">**External**: The spoofed sender is in an external domain.</span></span>
   - <span data-ttu-id="9be32-190">**Actie:** Selecteer **Toestaan** of **Blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="9be32-190">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="9be32-191">Wanneer u klaar bent, klikt u op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="9be32-191">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9be32-192">Gebruik de Microsoft 365 Defender portal om items in de lijst Tenant toestaan/blokkeren weer te geven</span><span class="sxs-lookup"><span data-stu-id="9be32-192">Use the Microsoft 365 Defender portal to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="9be32-193">Ga in Microsoft 365 Defender portal naar **Beleidsregels & sectie** \> **Bedreigingsbeleidsregels** \>  \> **tenantlijsten toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="9be32-193">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9be32-194">Selecteer het beste tabblad.</span><span class="sxs-lookup"><span data-stu-id="9be32-194">Select the tab you want.</span></span> <span data-ttu-id="9be32-195">De beschikbare kolommen zijn afhankelijk van het tabblad dat u hebt geselecteerd:</span><span class="sxs-lookup"><span data-stu-id="9be32-195">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="9be32-196">**URL's**:</span><span class="sxs-lookup"><span data-stu-id="9be32-196">**URLs**:</span></span>
     - <span data-ttu-id="9be32-197">**Waarde:** De URL.</span><span class="sxs-lookup"><span data-stu-id="9be32-197">**Value**: The URL.</span></span>
     - <span data-ttu-id="9be32-198">**Actie**: Het **waardeblok**.</span><span class="sxs-lookup"><span data-stu-id="9be32-198">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="9be32-199">**Laatst bijgewerkt**</span><span class="sxs-lookup"><span data-stu-id="9be32-199">**Last updated**</span></span>
     - <span data-ttu-id="9be32-200">**Verwijderen aan**</span><span class="sxs-lookup"><span data-stu-id="9be32-200">**Remove on**</span></span>
     - <span data-ttu-id="9be32-201">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="9be32-201">**Notes**</span></span>
   - <span data-ttu-id="9be32-202">**Bestanden**</span><span class="sxs-lookup"><span data-stu-id="9be32-202">**Files**</span></span>
     - <span data-ttu-id="9be32-203">**Waarde:** De bestandshash.</span><span class="sxs-lookup"><span data-stu-id="9be32-203">**Value**: The file hash.</span></span>
     - <span data-ttu-id="9be32-204">**Actie**: Het **waardeblok**.</span><span class="sxs-lookup"><span data-stu-id="9be32-204">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="9be32-205">**Laatst bijgewerkt**</span><span class="sxs-lookup"><span data-stu-id="9be32-205">**Last updated**</span></span>
     - <span data-ttu-id="9be32-206">**Verwijderen aan**</span><span class="sxs-lookup"><span data-stu-id="9be32-206">**Remove on**</span></span>
     - <span data-ttu-id="9be32-207">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="9be32-207">**Notes**</span></span>
   - <span data-ttu-id="9be32-208">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="9be32-208">**Spoofing**</span></span>
     - <span data-ttu-id="9be32-209">**Vervalste gebruiker**</span><span class="sxs-lookup"><span data-stu-id="9be32-209">**Spoofed user**</span></span>
     - <span data-ttu-id="9be32-210">**Verzendende infrastructuur**</span><span class="sxs-lookup"><span data-stu-id="9be32-210">**Sending infrastructure**</span></span>
     - <span data-ttu-id="9be32-211">**Spooftype:** De waarde **Intern** of **Extern**.</span><span class="sxs-lookup"><span data-stu-id="9be32-211">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="9be32-212">**Actie:** De waarde **Blokkeren of** **Toestaan.**</span><span class="sxs-lookup"><span data-stu-id="9be32-212">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="9be32-213">U kunt op een kolomkoppen klikken om in oplopende of aflopende volgorde te sorteren.</span><span class="sxs-lookup"><span data-stu-id="9be32-213">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="9be32-214">U kunt klikken op **Groep om** de resultaten te groepen.</span><span class="sxs-lookup"><span data-stu-id="9be32-214">You can click **Group** to group the results.</span></span> <span data-ttu-id="9be32-215">De waarden die beschikbaar zijn, zijn afhankelijk van het tabblad dat u hebt geselecteerd:</span><span class="sxs-lookup"><span data-stu-id="9be32-215">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="9be32-216">**URL's:** U kunt de resultaten groepen op **Actie.**</span><span class="sxs-lookup"><span data-stu-id="9be32-216">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="9be32-217">**Bestanden:** U kunt de resultaten groepren op **Actie.**</span><span class="sxs-lookup"><span data-stu-id="9be32-217">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="9be32-218">**Spoofing:** U kunt de resultaten groeperen op **Actie** of **Spooftype.**</span><span class="sxs-lookup"><span data-stu-id="9be32-218">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="9be32-219">Klik **op Zoeken,** voer een hele of een deel van een waarde in en druk vervolgens op Enter om een specifieke waarde te zoeken.</span><span class="sxs-lookup"><span data-stu-id="9be32-219">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="9be32-220">Wanneer u klaar bent, klikt u op ![ Zoekpictogram Zoeken ](../../media/m365-cc-sc-close-icon.png) **verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="9be32-220">When you're finished, click ![Clear search icon](../../media/m365-cc-sc-close-icon.png) **Clear search**.</span></span>

   <span data-ttu-id="9be32-221">Klik **op Filteren** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="9be32-221">Click **Filter** to filter the results.</span></span> <span data-ttu-id="9be32-222">De waarden die beschikbaar zijn in **de flyout Filter** die wordt weergegeven, zijn afhankelijk van het tabblad dat u hebt geselecteerd:</span><span class="sxs-lookup"><span data-stu-id="9be32-222">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="9be32-223">**URL's**</span><span class="sxs-lookup"><span data-stu-id="9be32-223">**URLs**</span></span>
     - <span data-ttu-id="9be32-224">**Actie**</span><span class="sxs-lookup"><span data-stu-id="9be32-224">**Action**</span></span>
     - <span data-ttu-id="9be32-225">**Nooit verlopen**</span><span class="sxs-lookup"><span data-stu-id="9be32-225">**Never expire**</span></span>
     - <span data-ttu-id="9be32-226">**Laatst bijgewerkte datum**</span><span class="sxs-lookup"><span data-stu-id="9be32-226">**Last updated date**</span></span>
     - <span data-ttu-id="9be32-227">**Verwijderen aan**</span><span class="sxs-lookup"><span data-stu-id="9be32-227">**Remove on**</span></span>
   - <span data-ttu-id="9be32-228">**Bestanden**</span><span class="sxs-lookup"><span data-stu-id="9be32-228">**Files**</span></span>
     - <span data-ttu-id="9be32-229">**Actie**</span><span class="sxs-lookup"><span data-stu-id="9be32-229">**Action**</span></span>
     - <span data-ttu-id="9be32-230">**Nooit verlopen**</span><span class="sxs-lookup"><span data-stu-id="9be32-230">**Never expire**</span></span>
     - <span data-ttu-id="9be32-231">**Laatst bijgewerkt**</span><span class="sxs-lookup"><span data-stu-id="9be32-231">**Last updated**</span></span>
     - <span data-ttu-id="9be32-232">**Verwijderen aan**</span><span class="sxs-lookup"><span data-stu-id="9be32-232">**Remove on**</span></span>
   - <span data-ttu-id="9be32-233">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="9be32-233">**Spoofing**</span></span>
     - <span data-ttu-id="9be32-234">**Actie**</span><span class="sxs-lookup"><span data-stu-id="9be32-234">**Action**</span></span>
     - <span data-ttu-id="9be32-235">**Spooftype**</span><span class="sxs-lookup"><span data-stu-id="9be32-235">**Spoof type**</span></span>

   <span data-ttu-id="9be32-236">Wanneer u klaar bent, klikt u op **Toepassen.**</span><span class="sxs-lookup"><span data-stu-id="9be32-236">When you're finished, click **Apply**.</span></span> <span data-ttu-id="9be32-237">Als u bestaande filters wilt wissen, klikt u **op Filter** en klikt u in het **fly-out** Filter dat wordt weergegeven op Filters **wissen.**</span><span class="sxs-lookup"><span data-stu-id="9be32-237">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9be32-238">Gebruik de Microsoft 365 Defender portal om items in de lijst Tenant Allow/Block te wijzigen</span><span class="sxs-lookup"><span data-stu-id="9be32-238">Use the Microsoft 365 Defender portal to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="9be32-239">Ga in Microsoft 365 Defender portal naar **Beleidsregels & sectie** \> **Bedreigingsbeleidsregels** \>  \> **tenantlijsten toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="9be32-239">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9be32-240">Selecteer het tabblad met het type vermelding dat u wilt wijzigen:</span><span class="sxs-lookup"><span data-stu-id="9be32-240">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="9be32-241">**URL's**</span><span class="sxs-lookup"><span data-stu-id="9be32-241">**URLs**</span></span>
   - <span data-ttu-id="9be32-242">**Bestanden**</span><span class="sxs-lookup"><span data-stu-id="9be32-242">**Files**</span></span>
   - <span data-ttu-id="9be32-243">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="9be32-243">**Spoofing**</span></span>

3. <span data-ttu-id="9be32-244">Selecteer het item dat u wilt wijzigen en klik vervolgens op ![ Pictogram ](../../media/m365-cc-sc-edit-icon.png) Bewerken.</span><span class="sxs-lookup"><span data-stu-id="9be32-244">Select the entry that you want to modify, and then click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span> <span data-ttu-id="9be32-245">De waarden die u kunt wijzigen in het flyout dat wordt weergegeven, zijn afhankelijk van het tabblad dat u in de vorige stap hebt geselecteerd:</span><span class="sxs-lookup"><span data-stu-id="9be32-245">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>
   - <span data-ttu-id="9be32-246">**URL's**</span><span class="sxs-lookup"><span data-stu-id="9be32-246">**URLs**</span></span>
     - <span data-ttu-id="9be32-247">**Nooit verlopen** en/of vervaldatum.</span><span class="sxs-lookup"><span data-stu-id="9be32-247">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="9be32-248">**Optionele notitie**</span><span class="sxs-lookup"><span data-stu-id="9be32-248">**Optional note**</span></span>
   - <span data-ttu-id="9be32-249">**Bestanden**</span><span class="sxs-lookup"><span data-stu-id="9be32-249">**Files**</span></span>
     - <span data-ttu-id="9be32-250">**Nooit verlopen** en/of vervaldatum.</span><span class="sxs-lookup"><span data-stu-id="9be32-250">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="9be32-251">**Optionele notitie**</span><span class="sxs-lookup"><span data-stu-id="9be32-251">**Optional note**</span></span>
   - <span data-ttu-id="9be32-252">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="9be32-252">**Spoofing**</span></span>
     - <span data-ttu-id="9be32-253">**Actie:** U kunt de waarde wijzigen in **Toestaan** of **Blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="9be32-253">**Action**: You can change the value to **Allow** or **Block**.</span></span>
4. <span data-ttu-id="9be32-254">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="9be32-254">When you're finished, click **Save**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="9be32-255">Gebruik de Microsoft 365 Defender portal om items te verwijderen uit de lijst Tenant Allow/Block</span><span class="sxs-lookup"><span data-stu-id="9be32-255">Use the Microsoft 365 Defender portal to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="9be32-256">Ga in Microsoft 365 Defender portal naar **Beleidsregels & sectie** \> **Bedreigingsbeleidsregels** \>  \> **tenantlijsten toestaan/blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="9be32-256">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9be32-257">Selecteer het tabblad met het type invoer dat u wilt verwijderen:</span><span class="sxs-lookup"><span data-stu-id="9be32-257">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="9be32-258">**URL's**</span><span class="sxs-lookup"><span data-stu-id="9be32-258">**URLs**</span></span>
   - <span data-ttu-id="9be32-259">**Bestanden**</span><span class="sxs-lookup"><span data-stu-id="9be32-259">**Files**</span></span>
   - <span data-ttu-id="9be32-260">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="9be32-260">**Spoofing**</span></span>

3. <span data-ttu-id="9be32-261">Selecteer het item dat u wilt verwijderen en klik vervolgens op ![ Pictogram ](../../media/m365-cc-sc-delete-icon.png) **verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="9be32-261">Select the entry that you want to remove, and then click ![Delete icon](../../media/m365-cc-sc-delete-icon.png) **Delete**.</span></span>

4. <span data-ttu-id="9be32-262">Klik in het waarschuwingsvenster dat wordt weergegeven op **Verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="9be32-262">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="9be32-263">Gebruik Exchange Online PowerShell of zelfstandige EOP PowerShell om de lijst met tenants toestaan/blokkeren te configureren</span><span class="sxs-lookup"><span data-stu-id="9be32-263">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="9be32-264">PowerShell gebruiken om blokbestands- of URL-vermeldingen toe te voegen aan de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="9be32-264">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="9be32-265">Gebruik de volgende syntaxis om blokbestands- of URL-vermeldingen toe te voegen aan de lijst Tenant toestaan/blokkeren:</span><span class="sxs-lookup"><span data-stu-id="9be32-265">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="9be32-266">In dit voorbeeld wordt een blokbestandsinvoer toegevoegd voor de opgegeven bestanden die nooit verlopen.</span><span class="sxs-lookup"><span data-stu-id="9be32-266">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="9be32-267">In dit voorbeeld wordt een blok-URL-vermelding voor contoso.com en alle subdomeinen (bijvoorbeeld contoso.com, www.contoso.com en xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9be32-267">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="9be32-268">Omdat we de parameters Vervaldatum of NoExpiration niet hebben gebruikt, verloopt de vermelding na 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="9be32-268">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="9be32-269">Zie [New-TenantAllowBlockListItems voor](/powershell/module/exchange/new-tenantallowblocklistitems)gedetailleerde syntaxis en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="9be32-269">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="9be32-270">PowerShell gebruiken om vervalste afzendergegevens toe te voegen of te blokkeren aan de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="9be32-270">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="9be32-271">Gebruik de volgende syntaxis om vervalste afzendergegevens toe te voegen aan de lijst Tenant Allow/Block:</span><span class="sxs-lookup"><span data-stu-id="9be32-271">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="9be32-272">Zie [New-TenantAllowBlockListSpoofItems voor](/powershell/module/exchange/new-tenantallowblocklistspoofitems)gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="9be32-272">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9be32-273">PowerShell gebruiken om blokbestands- of URL-items weer te geven in de lijst Tenant Allow/Block</span><span class="sxs-lookup"><span data-stu-id="9be32-273">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="9be32-274">Als u blokbestands- of URL-vermeldingen wilt weergeven in de lijst Tenant toestaan/blokkeren, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="9be32-274">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="9be32-275">In dit voorbeeld worden gegevens voor de opgegeven waarde voor bestandshash als resultaat gegeven.</span><span class="sxs-lookup"><span data-stu-id="9be32-275">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="9be32-276">In dit voorbeeld worden alle geblokkeerde URL's als retourneert.</span><span class="sxs-lookup"><span data-stu-id="9be32-276">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="9be32-277">Zie [Get-TenantAllowBlockListItems voor](/powershell/module/exchange/get-tenantallowblocklistitems)gedetailleerde syntaxis en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="9be32-277">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9be32-278">PowerShell gebruiken om vervalste afzenders toe te staan of te blokkeren in de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="9be32-278">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="9be32-279">Gebruik de volgende syntaxis om vervalste afzendergegevens weer te geven in de lijst Tenant Allow/Block:</span><span class="sxs-lookup"><span data-stu-id="9be32-279">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="9be32-280">Dit voorbeeld retourneert alle vervalste afzendergegevens in de lijst Tenant toestaan/blokkeren.</span><span class="sxs-lookup"><span data-stu-id="9be32-280">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="9be32-281">Dit voorbeeld retourneert alle toegestane vermeldingen van vervalste afzenders die intern zijn.</span><span class="sxs-lookup"><span data-stu-id="9be32-281">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="9be32-282">In dit voorbeeld worden alle geblokkeerde vermeldingen van vervalste afzenders die extern zijn, als retourneert.</span><span class="sxs-lookup"><span data-stu-id="9be32-282">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="9be32-283">Zie [Get-TenantAllowBlockListSpoofItems (Get-TenantAllowBlockListSpoofItems)](/powershell/module/exchange/get-tenantallowblocklistspoofitems)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="9be32-283">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9be32-284">PowerShell gebruiken om blokbestands- en URL-items in de lijst Tenant allow/block te wijzigen</span><span class="sxs-lookup"><span data-stu-id="9be32-284">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="9be32-285">Gebruik de volgende syntaxis om blokbestands- en URL-vermeldingen in de lijst Tenant toestaan/blokkeren te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="9be32-285">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="9be32-286">In dit voorbeeld wordt de vervaldatum van de opgegeven blok-URL-vermelding gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="9be32-286">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="9be32-287">Zie [Set-TenantAllowBlockListItems (Set-TenantAllowBlockListItems)](/powershell/module/exchange/set-tenantallowblocklistitems)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="9be32-287">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9be32-288">PowerShell gebruiken om vervalste afzenders toe te staan of te blokkeren in de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="9be32-288">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="9be32-289">Gebruik de volgende syntaxis om vervalste afzendergegevens in de lijst Tenant Allow/Block te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="9be32-289">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="9be32-290">In dit voorbeeld wordt de vermelding van vervalste afzenders gewijzigd in toestaan om te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="9be32-290">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="9be32-291">Zie [Set-TenantAllowBlockListSpoofItems (Set-TenantAllowBlockListSpoofItems)](/powershell/module/exchange/set-tenantallowblocklistspoofitems)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="9be32-291">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="9be32-292">PowerShell gebruiken om URL- of bestandsgegevens te verwijderen uit de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="9be32-292">Use PowerShell to remove URL or file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="9be32-293">Gebruik de volgende syntaxis om bestands- en URL-vermeldingen te verwijderen uit de lijst Tenant toestaan/blokkeren:</span><span class="sxs-lookup"><span data-stu-id="9be32-293">To remove file and URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="9be32-294">In dit voorbeeld wordt de opgegeven blok-URL-vermelding verwijderd uit de lijst Tenant toestaan/blokkeren.</span><span class="sxs-lookup"><span data-stu-id="9be32-294">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="9be32-295">Zie [Remove-TenantAllowBlockListItems (Verwijderen-TenantAllowBlockListItems)](/powershell/module/exchange/remove-tenantallowblocklistitems)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="9be32-295">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="9be32-296">PowerShell gebruiken om vervalste afzenders toe te staan of te blokkeren uit de tenantlijst toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="9be32-296">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="9be32-297">Gebruik de volgende syntaxis als u spoofing sender items wilt verwijderen uit de tenant allow/block list:</span><span class="sxs-lookup"><span data-stu-id="9be32-297">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="9be32-298">Zie [Remove-TenantAllowBlockListSpoofItems (Verwijderen-TenantAllowBlockListSpoofItems)](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="9be32-298">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="9be32-299">URL-syntaxis voor de lijst Toestaan/blokkeren van tenant</span><span class="sxs-lookup"><span data-stu-id="9be32-299">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="9be32-300">IP4v- en IPv6-adressen zijn toegestaan, maar TCP/UDP-poorten niet.</span><span class="sxs-lookup"><span data-stu-id="9be32-300">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="9be32-301">Bestandsnaamextensies zijn niet toegestaan (bijvoorbeeld test.pdf).</span><span class="sxs-lookup"><span data-stu-id="9be32-301">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="9be32-302">Unicode wordt niet ondersteund, maar Punycode wel.</span><span class="sxs-lookup"><span data-stu-id="9be32-302">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="9be32-303">Hostnamen zijn toegestaan als alle volgende instructies waar zijn:</span><span class="sxs-lookup"><span data-stu-id="9be32-303">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="9be32-304">De hostnaam bevat een punt.</span><span class="sxs-lookup"><span data-stu-id="9be32-304">The hostname contains a period.</span></span>
  - <span data-ttu-id="9be32-305">Er is ten minste één teken links van de periode.</span><span class="sxs-lookup"><span data-stu-id="9be32-305">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="9be32-306">Er zijn ten minste twee tekens rechts van de periode.</span><span class="sxs-lookup"><span data-stu-id="9be32-306">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="9be32-307">Is bijvoorbeeld `t.co` toegestaan of `.com` niet `contoso.` toegestaan.</span><span class="sxs-lookup"><span data-stu-id="9be32-307">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="9be32-308">Subpathen worden niet geïmpliceerd.</span><span class="sxs-lookup"><span data-stu-id="9be32-308">Subpaths are not implied.</span></span>

  <span data-ttu-id="9be32-309">Bevat bijvoorbeeld `contoso.com` geen `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="9be32-309">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="9be32-310">Jokertekens (\*) zijn toegestaan in de volgende scenario's:</span><span class="sxs-lookup"><span data-stu-id="9be32-310">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="9be32-311">Een linker jokerteken moet worden gevolgd door een punt om een subdomein op te geven.</span><span class="sxs-lookup"><span data-stu-id="9be32-311">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="9be32-312">Is bijvoorbeeld `*.contoso.com` toegestaan; `*contoso.com` is niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="9be32-312">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="9be32-313">Een jokerteken rechts moet een slash (/) volgen om een pad op te geven.</span><span class="sxs-lookup"><span data-stu-id="9be32-313">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="9be32-314">Is bijvoorbeeld `contoso.com/*` toegestaan of `contoso.com*` niet `contoso.com/ab*` toegestaan.</span><span class="sxs-lookup"><span data-stu-id="9be32-314">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="9be32-315">Alle subpathen worden niet geïmpliceerd door een rechter jokerteken.</span><span class="sxs-lookup"><span data-stu-id="9be32-315">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="9be32-316">Bevat bijvoorbeeld `contoso.com/*` geen `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="9be32-316">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="9be32-317">`*.com*` ongeldig is (geen op te lossen domein en het jokerteken rechts volgt geen slash voor vooruit).</span><span class="sxs-lookup"><span data-stu-id="9be32-317">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="9be32-318">Jokertekens zijn niet toegestaan in IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="9be32-318">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="9be32-319">Het tildeteken (~) is beschikbaar in de volgende scenario's:</span><span class="sxs-lookup"><span data-stu-id="9be32-319">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="9be32-320">Een linker tilde houdt een domein en alle subdomeinen in.</span><span class="sxs-lookup"><span data-stu-id="9be32-320">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="9be32-321">Bijvoorbeeld inclusief `~contoso.com` `contoso.com` en `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="9be32-321">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="9be32-322">URL-vermeldingen die protocollen bevatten (bijvoorbeeld , of ) mislukken, omdat URL-vermeldingen van toepassing zijn `http://` `https://` op alle `ftp://` protocollen.</span><span class="sxs-lookup"><span data-stu-id="9be32-322">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="9be32-323">Een gebruikersnaam of wachtwoord wordt niet ondersteund of vereist.</span><span class="sxs-lookup"><span data-stu-id="9be32-323">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="9be32-324">Aanhalingstekens (' of ") zijn ongeldige tekens.</span><span class="sxs-lookup"><span data-stu-id="9be32-324">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="9be32-325">Een URL moet waar mogelijk alle omleidingen bevatten.</span><span class="sxs-lookup"><span data-stu-id="9be32-325">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="9be32-326">Scenario's voor URL-invoer</span><span class="sxs-lookup"><span data-stu-id="9be32-326">URL entry scenarios</span></span>

<span data-ttu-id="9be32-327">Geldige URL-vermeldingen en de resultaten worden beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="9be32-327">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="9be32-328">Scenario: Geen jokertekens</span><span class="sxs-lookup"><span data-stu-id="9be32-328">Scenario: No wildcards</span></span>

<span data-ttu-id="9be32-329">**Vermelding**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="9be32-329">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="9be32-330">**Overeenkomst toestaan**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-330">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="9be32-331">**Niet-overeenkomende toestaan:**</span><span class="sxs-lookup"><span data-stu-id="9be32-331">**Allow not matched**:</span></span>

  - <span data-ttu-id="9be32-332">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-332">abc-contoso.com</span></span>
  - <span data-ttu-id="9be32-333">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9be32-333">contoso.com/a</span></span>
  - <span data-ttu-id="9be32-334">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-334">payroll.contoso.com</span></span>
  - <span data-ttu-id="9be32-335">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-335">test.com/contoso.com</span></span>
  - <span data-ttu-id="9be32-336">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-336">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="9be32-337">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-337">www.contoso.com</span></span>
  - <span data-ttu-id="9be32-338">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-338">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="9be32-339">**Blok overeenkomst**:</span><span class="sxs-lookup"><span data-stu-id="9be32-339">**Block match**:</span></span>

  - <span data-ttu-id="9be32-340">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-340">contoso.com</span></span>
  - <span data-ttu-id="9be32-341">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9be32-341">contoso.com/a</span></span>
  - <span data-ttu-id="9be32-342">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-342">payroll.contoso.com</span></span>
  - <span data-ttu-id="9be32-343">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-343">test.com/contoso.com</span></span>
  - <span data-ttu-id="9be32-344">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-344">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="9be32-345">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-345">www.contoso.com</span></span>
  - <span data-ttu-id="9be32-346">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-346">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="9be32-347">**Blok niet overeenkomend**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-347">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="9be32-348">Scenario: Jokerteken links (subdomein)</span><span class="sxs-lookup"><span data-stu-id="9be32-348">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="9be32-349">**Vermelding**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="9be32-349">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="9be32-350">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="9be32-350">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9be32-351">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-351">www.contoso.com</span></span>
  - <span data-ttu-id="9be32-352">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-352">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="9be32-353">**Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**</span><span class="sxs-lookup"><span data-stu-id="9be32-353">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="9be32-354">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-354">123contoso.com</span></span>
  - <span data-ttu-id="9be32-355">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-355">contoso.com</span></span>
  - <span data-ttu-id="9be32-356">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-356">test.com/contoso.com</span></span>
  - <span data-ttu-id="9be32-357">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="9be32-357">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="9be32-358">Scenario: Jokerteken rechts boven aan pad</span><span class="sxs-lookup"><span data-stu-id="9be32-358">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="9be32-359">**Vermelding**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="9be32-359">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="9be32-360">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="9be32-360">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9be32-361">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="9be32-361">contoso.com/a/b</span></span>
  - <span data-ttu-id="9be32-362">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="9be32-362">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="9be32-363">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="9be32-363">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="9be32-364">**Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**</span><span class="sxs-lookup"><span data-stu-id="9be32-364">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="9be32-365">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-365">contoso.com</span></span>
  - <span data-ttu-id="9be32-366">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9be32-366">contoso.com/a</span></span>
  - <span data-ttu-id="9be32-367">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-367">www.contoso.com</span></span>
  - <span data-ttu-id="9be32-368">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-368">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="9be32-369">Scenario: Tilde links</span><span class="sxs-lookup"><span data-stu-id="9be32-369">Scenario: Left tilde</span></span>

<span data-ttu-id="9be32-370">**Vermelding**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="9be32-370">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="9be32-371">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="9be32-371">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9be32-372">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-372">contoso.com</span></span>
  - <span data-ttu-id="9be32-373">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-373">www.contoso.com</span></span>
  - <span data-ttu-id="9be32-374">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-374">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="9be32-375">**Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**</span><span class="sxs-lookup"><span data-stu-id="9be32-375">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="9be32-376">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-376">123contoso.com</span></span>
  - <span data-ttu-id="9be32-377">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="9be32-377">contoso.com/abc</span></span>
  - <span data-ttu-id="9be32-378">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="9be32-378">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="9be32-379">Scenario: Het achtervoegsel van het jokerteken rechts</span><span class="sxs-lookup"><span data-stu-id="9be32-379">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="9be32-380">**Vermelding**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="9be32-380">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="9be32-381">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="9be32-381">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9be32-382">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="9be32-382">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="9be32-383">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9be32-383">contoso.com/a</span></span>
  - <span data-ttu-id="9be32-384">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="9be32-384">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="9be32-385">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="9be32-385">contoso.com/ab</span></span>
  - <span data-ttu-id="9be32-386">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="9be32-386">contoso.com/b</span></span>
  - <span data-ttu-id="9be32-387">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="9be32-387">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="9be32-388">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="9be32-388">contoso.com/ba</span></span>

- <span data-ttu-id="9be32-389">**Niet-overeenkomende en** **niet-overeenkomende** blokkering toestaan: contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-389">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="9be32-390">Scenario: Linker jokertekensubdomein en rechterachtervoegsel jokerteken</span><span class="sxs-lookup"><span data-stu-id="9be32-390">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="9be32-391">**Vermelding**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="9be32-391">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="9be32-392">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="9be32-392">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9be32-393">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="9be32-393">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="9be32-394">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="9be32-394">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="9be32-395">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9be32-395">www.contoso.com/a</span></span>
  - <span data-ttu-id="9be32-396">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="9be32-396">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="9be32-397">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="9be32-397">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="9be32-398">**Niet-overeenkomende en** **niet-overeenkomende** blokkering toestaan : contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="9be32-398">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="9be32-399">Scenario: Tilde links en rechts</span><span class="sxs-lookup"><span data-stu-id="9be32-399">Scenario: Left and right tilde</span></span>

<span data-ttu-id="9be32-400">**Vermelding**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="9be32-400">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="9be32-401">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="9be32-401">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9be32-402">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-402">contoso.com</span></span>
  - <span data-ttu-id="9be32-403">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9be32-403">contoso.com/a</span></span>
  - <span data-ttu-id="9be32-404">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-404">www.contoso.com</span></span>
  - <span data-ttu-id="9be32-405">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="9be32-405">www.contoso.com/b</span></span>
  - <span data-ttu-id="9be32-406">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-406">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="9be32-407">**Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**</span><span class="sxs-lookup"><span data-stu-id="9be32-407">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="9be32-408">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-408">123contoso.com</span></span>
  - <span data-ttu-id="9be32-409">contoso.org</span><span class="sxs-lookup"><span data-stu-id="9be32-409">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="9be32-410">Scenario: IP-adres</span><span class="sxs-lookup"><span data-stu-id="9be32-410">Scenario: IP address</span></span>

<span data-ttu-id="9be32-411">**Vermelding**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="9be32-411">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="9be32-412">**Overeenkomst toestaan** **en overeenkomst blokkeren**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="9be32-412">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="9be32-413">**Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**</span><span class="sxs-lookup"><span data-stu-id="9be32-413">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="9be32-414">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="9be32-414">1.2.3.4/a</span></span>
  - <span data-ttu-id="9be32-415">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="9be32-415">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="9be32-416">IP-adres met jokerteken rechts</span><span class="sxs-lookup"><span data-stu-id="9be32-416">IP address with right wildcard</span></span>

<span data-ttu-id="9be32-417">**Vermelding**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="9be32-417">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="9be32-418">**Overeenkomst en** **overeenkomst blokkeren toestaan:**</span><span class="sxs-lookup"><span data-stu-id="9be32-418">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9be32-419">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="9be32-419">1.2.3.4/b</span></span>
  - <span data-ttu-id="9be32-420">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="9be32-420">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="9be32-421">Voorbeelden van ongeldige vermeldingen</span><span class="sxs-lookup"><span data-stu-id="9be32-421">Examples of invalid entries</span></span>

<span data-ttu-id="9be32-422">De volgende vermeldingen zijn ongeldig:</span><span class="sxs-lookup"><span data-stu-id="9be32-422">The following entries are invalid:</span></span>

- <span data-ttu-id="9be32-423">**Ontbrekende of ongeldige domeinwaarden:**</span><span class="sxs-lookup"><span data-stu-id="9be32-423">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="9be32-424">contoso</span><span class="sxs-lookup"><span data-stu-id="9be32-424">contoso</span></span>
  - <span data-ttu-id="9be32-425">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="9be32-425">\*.contoso.\*</span></span>
  - <span data-ttu-id="9be32-426">\*.com</span><span class="sxs-lookup"><span data-stu-id="9be32-426">\*.com</span></span>
  - <span data-ttu-id="9be32-427">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="9be32-427">\*.pdf</span></span>

- <span data-ttu-id="9be32-428">**Jokerteken op tekst of zonder spatiëringstekens:**</span><span class="sxs-lookup"><span data-stu-id="9be32-428">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="9be32-429">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="9be32-429">\*contoso.com</span></span>
  - <span data-ttu-id="9be32-430">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="9be32-430">contoso.com\*</span></span>
  - <span data-ttu-id="9be32-431">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="9be32-431">\*1.2.3.4</span></span>
  - <span data-ttu-id="9be32-432">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="9be32-432">1.2.3.4\*</span></span>
  - <span data-ttu-id="9be32-433">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="9be32-433">contoso.com/a\*</span></span>
  - <span data-ttu-id="9be32-434">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="9be32-434">contoso.com/ab\*</span></span>

- <span data-ttu-id="9be32-435">**IP-adressen met poorten:**</span><span class="sxs-lookup"><span data-stu-id="9be32-435">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="9be32-436">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="9be32-436">contoso.com:443</span></span>
  - <span data-ttu-id="9be32-437">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="9be32-437">abc.contoso.com:25</span></span>

- <span data-ttu-id="9be32-438">**Niet-beschrijvende jokertekens:**</span><span class="sxs-lookup"><span data-stu-id="9be32-438">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="9be32-439">\*.\*</span><span class="sxs-lookup"><span data-stu-id="9be32-439">\*.\*</span></span>

- <span data-ttu-id="9be32-440">**Middelste jokertekens:**</span><span class="sxs-lookup"><span data-stu-id="9be32-440">**Middle wildcards**:</span></span>

  - <span data-ttu-id="9be32-441">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="9be32-441">conto\*so.com</span></span>
  - <span data-ttu-id="9be32-442">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="9be32-442">conto~so.com</span></span>

- <span data-ttu-id="9be32-443">**Dubbele jokertekens**</span><span class="sxs-lookup"><span data-stu-id="9be32-443">**Double wildcards**</span></span>

  - <span data-ttu-id="9be32-444">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="9be32-444">contoso.com/\*\*</span></span>
  - <span data-ttu-id="9be32-445">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="9be32-445">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9be32-446">Syntaxis van domeinparen voor vervalste afzendergegevens in de lijst Tenant toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="9be32-446">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="9be32-447">Een domeinpaar voor een vervalste afzender in de lijst Tenant toestaan/blokkeren gebruikt de volgende syntaxis: `<Spoofed user>, <Sending infrastructure>` .</span><span class="sxs-lookup"><span data-stu-id="9be32-447">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="9be32-448">**Vervalste gebruiker:** Deze waarde betreft het e-mailadres van de vervalste gebruiker die wordt weergegeven in het vak **Van** in e-mail clients.</span><span class="sxs-lookup"><span data-stu-id="9be32-448">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="9be32-449">Dit adres wordt ook wel het adres `5322.From` genoemd.</span><span class="sxs-lookup"><span data-stu-id="9be32-449">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="9be32-450">Geldige waarden zijn:</span><span class="sxs-lookup"><span data-stu-id="9be32-450">Valid values include:</span></span>
  - <span data-ttu-id="9be32-451">Een afzonderlijk e-mailadres (bijvoorbeeld chris@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9be32-451">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="9be32-452">Een e-maildomein (bijvoorbeeld contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9be32-452">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="9be32-453">Het jokerteken \* (bijvoorbeeld).</span><span class="sxs-lookup"><span data-stu-id="9be32-453">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="9be32-454">**Verzendende infrastructuur:** deze waarde geeft de bron aan van berichten van de vervalste gebruiker.</span><span class="sxs-lookup"><span data-stu-id="9be32-454">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="9be32-455">Geldige waarden zijn:</span><span class="sxs-lookup"><span data-stu-id="9be32-455">Valid values include:</span></span>
  - <span data-ttu-id="9be32-456">Het domein dat is gevonden in een REVERSE DNS lookup (PTR-record) van het IP-adres van de bron-e-mailserver (bijvoorbeeld fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="9be32-456">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="9be32-457">Als het bron-IP-adres geen PTR-record heeft, wordt de verzendende infrastructuur geïdentificeerd als \<source IP\> /24 (bijvoorbeeld 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="9be32-457">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="9be32-458">Hier zijn enkele voorbeelden van geldige domeinparen om vervalste afzenders te identificeren:</span><span class="sxs-lookup"><span data-stu-id="9be32-458">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="9be32-459">Het maximum aantal vervalste afzenders is 1000.</span><span class="sxs-lookup"><span data-stu-id="9be32-459">The maximum number of spoofed sender entries is 1000.</span></span>

<span data-ttu-id="9be32-460">Als u een domeinpaar toevoegt, wordt  de *combinatie* van de vervalste gebruiker en de verzendende infrastructuur alleen mogelijk of blokkeert.</span><span class="sxs-lookup"><span data-stu-id="9be32-460">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="9be32-461">E-mail van de vervalste gebruiker van welke bron dan ook is niet toegestaan en e-mail uit de bron van de verzendende infrastructuur wordt niet toegestaan voor vervalste gebruikers.</span><span class="sxs-lookup"><span data-stu-id="9be32-461">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span> 

<span data-ttu-id="9be32-462">U voegt bijvoorbeeld een toegestane vermelding toe voor het volgende domeinpaar:</span><span class="sxs-lookup"><span data-stu-id="9be32-462">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="9be32-463">**Domein:** gmail.com</span><span class="sxs-lookup"><span data-stu-id="9be32-463">**Domain**: gmail.com</span></span>
- <span data-ttu-id="9be32-464">**Infrastructuur**: tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="9be32-464">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="9be32-465">Alleen berichten uit dat domein *en het* verzenden van infrastructuurparen mogen spoofen.</span><span class="sxs-lookup"><span data-stu-id="9be32-465">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="9be32-466">Andere afzenders die proberen te spoofen gmail.com zijn niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="9be32-466">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="9be32-467">Berichten van afzenders in andere domeinen die afkomstig zijn van tms.mx.com worden gecontroleerd door spoof intelligence.</span><span class="sxs-lookup"><span data-stu-id="9be32-467">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
