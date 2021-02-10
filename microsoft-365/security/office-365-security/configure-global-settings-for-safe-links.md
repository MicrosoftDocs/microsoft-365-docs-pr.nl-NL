---
title: Algemene instellingen configureren voor instellingen voor veilige koppelingen in Defender voor Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Beheerders kunnen meer informatie krijgen over het weergeven en configureren van globale instellingen (de lijst 'De volgende URL's blokkeren' en beveiliging voor Office 365-apps) voor veilige koppelingen in Microsoft Defender voor Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 885fe6a06cce054bea6d6f20c24c5c1f2a159c07
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165725"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="1fe18-103">Algemene instellingen configureren voor veilige koppelingen in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="1fe18-103">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1fe18-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="1fe18-104">**Applies to**</span></span>
- [<span data-ttu-id="1fe18-105">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="1fe18-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="1fe18-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1fe18-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="1fe18-107">Dit artikel is bedoeld voor zakelijke klanten die [Microsoft Defender voor Office 365](office-365-atp.md) hebben.</span><span class="sxs-lookup"><span data-stu-id="1fe18-107">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="1fe18-108">Als u een thuisgebruiker bent en op zoek bent naar informatie over Safelinks in Outlook, gaat u naar [Advanced Outlook.com security.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="1fe18-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="1fe18-109">Veilige koppelingen is een functie in Microsoft Defender voor [Office 365](office-365-atp.md) waarmee de URL wordt gescand van binnenkomende e-mailberichten in de e-mailstroom en het tijdstip van klikverificatie van URL's en koppelingen in e-mailberichten en op andere locaties.</span><span class="sxs-lookup"><span data-stu-id="1fe18-109">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="1fe18-110">Zie Veilige koppelingen [in Microsoft Defender voor Office 365](atp-safe-links.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1fe18-110">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="1fe18-111">U configureert de meeste instellingen voor veilige koppelingen in het beleid voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="1fe18-111">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="1fe18-112">Zie Beleidsregels voor veilige [koppelingen instellen in Microsoft Defender voor Office 365](set-up-atp-safe-links-policies.md)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="1fe18-112">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

<span data-ttu-id="1fe18-113">Veilige koppelingen maken echter ook gebruik van globale instellingen die van toepassing zijn op alle gebruikers die zijn opgenomen in een actief beleid voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="1fe18-113">But, Safe Links also uses global settings that apply to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="1fe18-114">Dit gebied met globale instellingen:</span><span class="sxs-lookup"><span data-stu-id="1fe18-114">These global settings area:</span></span>

- <span data-ttu-id="1fe18-115">De **lijst met de volgende URL's** blokkeren.</span><span class="sxs-lookup"><span data-stu-id="1fe18-115">The **Block the following URLs** list.</span></span> <span data-ttu-id="1fe18-116">Zie de lijst ['De volgende URL's blokkeren'](atp-safe-links.md#block-the-following-urls-list-for-safe-links) voor meer informatie over veilige koppelingen</span><span class="sxs-lookup"><span data-stu-id="1fe18-116">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="1fe18-117">Beveiliging tegen veilige koppelingen voor Office 365-apps.</span><span class="sxs-lookup"><span data-stu-id="1fe18-117">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="1fe18-118">Zie instellingen voor veilige koppelingen [voor Office 365-apps](atp-safe-links.md#safe-links-settings-for-office-365-apps)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1fe18-118">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="1fe18-119">U kunt de globale instellingen voor veilige koppelingen configureren in het beveiligings- &-compliancecentrum of in PowerShell (Exchange Online PowerShell voor in aanmerking komende Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken, maar met Microsoft Defender voor Office 365-invoegabonnementen).</span><span class="sxs-lookup"><span data-stu-id="1fe18-119">You can configure the global Safe Links settings in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1fe18-120">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="1fe18-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1fe18-121">De functies die worden geboden door globale instellingen voor veilige koppelingen, worden alleen toegepast op gebruikers die zijn opgenomen in het actieve beleid voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="1fe18-121">The features provided by global settings for Safe Links are only applied to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="1fe18-122">Er is geen ingebouwd of standaardbeleid voor veilige koppelingen. U moet dus ten minste één beleid voor veilige koppelingen maken om deze globale instellingen actief te maken.</span><span class="sxs-lookup"><span data-stu-id="1fe18-122">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for these global settings to be active.</span></span> <span data-ttu-id="1fe18-123">Zie Beleidsregels voor veilige [koppelingen instellen in Microsoft Defender voor Office 365](set-up-atp-safe-links-policies.md)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="1fe18-123">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

- <span data-ttu-id="1fe18-124">U opent het beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="1fe18-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="1fe18-125">Als u rechtstreeks naar de pagina **Veilige koppelingen wilt** gaan, gebruikt u <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="1fe18-125">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="1fe18-126">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1fe18-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="1fe18-127">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1fe18-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="1fe18-128">Je moet beschikken over toegewezen machtigingen in het Beveiligings- en compliancecentrum voor het uitvoeren van de procedures in dit onderwerp:</span><span class="sxs-lookup"><span data-stu-id="1fe18-128">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="1fe18-129">Als u de algemene instellingen voor veilige koppelingen wilt configureren, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="1fe18-129">To configure the global settings for Safe Links, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="1fe18-130">Voor alleen-lezen toegang tot de globale instellingen voor veilige koppelingen  moet u lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="1fe18-130">For read-only access to the global settings for Safe Links, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="1fe18-131">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1fe18-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="1fe18-132">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="1fe18-132">**Notes**:</span></span>

  - <span data-ttu-id="1fe18-133">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1fe18-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="1fe18-134">Zie[Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1fe18-134">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="1fe18-135">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="1fe18-135">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="1fe18-136">Zie instellingen voor veilige koppelingen voor de aanbevolen waarden voor de globale instellingen [voor veilige koppelingen.](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)</span><span class="sxs-lookup"><span data-stu-id="1fe18-136">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).</span></span>

- <span data-ttu-id="1fe18-137">Het kan 30 minuten duren voordat een nieuw of bijgewerkt beleid wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="1fe18-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="1fe18-138">[Nieuwe functies worden voortdurend toegevoegd aan Microsoft Defender voor Office 365.](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="1fe18-138">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="1fe18-139">Naarmate er nieuwe functies worden toegevoegd, moet u mogelijk uw bestaande beleidsregels voor veilige koppelingen aanpassen.</span><span class="sxs-lookup"><span data-stu-id="1fe18-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a><span data-ttu-id="1fe18-140">De lijst 'De volgende URL's blokkeren' configureren in het & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="1fe18-140">Configure the "Block the following URLs" list in the Security & Compliance Center</span></span>

<span data-ttu-id="1fe18-141">In **de lijst Met de volgende URL's** blokkeren worden de koppelingen geïdentificeerd die altijd moeten worden geblokkeerd door het scannen van veilige koppelingen in ondersteunde apps.</span><span class="sxs-lookup"><span data-stu-id="1fe18-141">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="1fe18-142">Zie de lijst ['De volgende URL's blokkeren' voor meer](atp-safe-links.md#block-the-following-urls-list-for-safe-links)informatie over veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="1fe18-142">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="1fe18-143">Ga in het & compliancecentrum naar  Veilige koppelingen van ATP voor bedreigingsbeheerbeleid en klik op \>  \>  **Globale instellingen.**</span><span class="sxs-lookup"><span data-stu-id="1fe18-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="1fe18-144">In het **beleid voor veilige koppelingen voor uw** organisatie dat wordt weergegeven, gaat u naar het vak De volgende **URL's blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="1fe18-144">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="1fe18-145">Configureer een of meer vermeldingen zoals wordt beschreven in de syntaxis voor invoer voor de lijst 'De volgende [URL's blokkeren'.](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="1fe18-145">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="1fe18-146">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="1fe18-146">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="1fe18-147">De lijst 'De volgende URL's blokkeren' configureren in PowerShell</span><span class="sxs-lookup"><span data-stu-id="1fe18-147">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="1fe18-148">Zie de syntaxis voor invoer voor de lijst 'De volgende [URL's blokkeren'](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)voor meer informatie over de syntaxis van de invoer.</span><span class="sxs-lookup"><span data-stu-id="1fe18-148">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="1fe18-149">U kunt de cmdlet **Get-AtpPolicyForO365** gebruiken om bestaande vermeldingen in de eigenschap _BlockURLs te_ bekijken.</span><span class="sxs-lookup"><span data-stu-id="1fe18-149">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="1fe18-150">Als u waarden wilt toevoegen die eventuele bestaande items vervangen, gebruikt u de volgende syntaxis in Exchange Online PowerShell of Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1fe18-150">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="1fe18-151">In dit voorbeeld worden de volgende items toegevoegd aan de lijst:</span><span class="sxs-lookup"><span data-stu-id="1fe18-151">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="1fe18-152">Blokkeer het domein, subdomeinen en paden voor fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="1fe18-152">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="1fe18-153">Het subdomeinonderzoek blokkeren, maar niet het bovenliggende domein of andere subdomeinen in tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="1fe18-153">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="1fe18-154">Gebruik de volgende syntaxis om waarden toe te voegen of te verwijderen zonder dat dit van invloed is op andere bestaande gegevens:</span><span class="sxs-lookup"><span data-stu-id="1fe18-154">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="1fe18-155">In dit voorbeeld wordt een nieuw item voor adatum.com toegevoegd en wordt de vermelding voor fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="1fe18-155">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a><span data-ttu-id="1fe18-156">Beveiliging van veilige koppelingen configureren voor Office 365-apps in het & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="1fe18-156">Configure Safe Links protection for Office 365 apps in the Security & Compliance Center</span></span>

<span data-ttu-id="1fe18-157">Beveiliging tegen veilige koppelingen voor Office 365-apps is van toepassing op documenten in ondersteunde Office-bureaublad-, mobiele en web-apps.</span><span class="sxs-lookup"><span data-stu-id="1fe18-157">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="1fe18-158">Zie instellingen voor veilige koppelingen [voor Office 365-apps](atp-safe-links.md#safe-links-settings-for-office-365-apps)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1fe18-158">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="1fe18-159">Ga in het & compliancecentrum naar  Veilige koppelingen van ATP voor bedreigingsbeheerbeleid en klik op \>  \>  **Globale instellingen.**</span><span class="sxs-lookup"><span data-stu-id="1fe18-159">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="1fe18-160">In het **beleid voor veilige koppelingen voor uw** organisatie dat wordt weergegeven, configureert u de volgende instellingen in de instellingen die van toepassing zijn op inhoud behalve **e-mailsectie:**</span><span class="sxs-lookup"><span data-stu-id="1fe18-160">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content except email** section:</span></span>

   - <span data-ttu-id="1fe18-161">**Office 365-toepassingen:** controleer of de schakelknop aan de rechterkant staat om Veilige koppelingen in te schakelen voor ondersteunde Office 365-apps: ![ In-/uitschakelen. ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="1fe18-161">**Office 365 applications**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="1fe18-162">**Houd niet bij** wanneer gebruikers op Veilige koppelingen klikken: zet de schakelaar naar links om klikken van gebruikers met betrekking tot geblokkeerde URL's in ondersteunde Office 365-apps bij te ![ houden: In-/uitschakelen. ](../../media/scc-toggle-off.png)</span><span class="sxs-lookup"><span data-stu-id="1fe18-162">**Do not track when users click Safe Links**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="1fe18-163">Laat gebruikers niet doorklikken naar de oorspronkelijke **URL:** controleer of de schakelknop aan de rechterkant is om te voorkomen dat gebruikers doorklikken naar de oorspronkelijke, geblokkeerde URL in ondersteunde Office 365-apps: In-/uitschakelen. ![ ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="1fe18-163">**Do not let users click through Safe Links to the original URL**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="1fe18-164">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="1fe18-164">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="1fe18-165">Beveiliging van veilige koppelingen configureren voor Office 365-apps in PowerShell</span><span class="sxs-lookup"><span data-stu-id="1fe18-165">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="1fe18-166">Als u liever PowerShell gebruikt om beveiliging tegen veilige koppelingen voor Office 365-apps te configureren, gebruikt u de volgende syntaxis in Exchange Online PowerShell of Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1fe18-166">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="1fe18-167">In dit voorbeeld worden de volgende instellingen geconfigureerd voor beveiliging tegen veilige koppelingen in Office 365-apps:</span><span class="sxs-lookup"><span data-stu-id="1fe18-167">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="1fe18-168">Veilige koppelingen voor Office 365-apps is ingeschakeld (we gebruiken niet de parameter _EnableSafeLinksForO365Clients_ en de standaardwaarde is $true).</span><span class="sxs-lookup"><span data-stu-id="1fe18-168">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="1fe18-169">Klikken van gebruikers met betrekking tot geblokkeerde URL's in ondersteunde Office 365-apps worden bijgehouden.</span><span class="sxs-lookup"><span data-stu-id="1fe18-169">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="1fe18-170">Gebruikers kunnen niet doorklikken naar de oorspronkelijke, geblokkeerde URL in ondersteunde Office 365-apps (we gebruiken de parameter _AllowClickThrough_ niet en de standaardwaarde is $false).</span><span class="sxs-lookup"><span data-stu-id="1fe18-170">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="1fe18-171">Zie [Set-AtpPolicyForO365 voor](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="1fe18-171">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="1fe18-172">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="1fe18-172">How do you know these procedures worked?</span></span>

<span data-ttu-id="1fe18-173">Als u wilt controleren of u de globale instellingen voor veilige koppelingen hebt geconfigureerd (de lijst met de volgende **URL's** en de beveiligingsinstellingen voor Office 365-apps blokkeren), gaat u op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="1fe18-173">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="1fe18-174">Ga in het & compliancecentrum naar  Veilige koppelingen van ATP voor risicobeheerbeleid, klik op Globale instellingen en controleer de instellingen in de \>  \> fly out die wordt weergegeven. </span><span class="sxs-lookup"><span data-stu-id="1fe18-174">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="1fe18-175">Voer in Exchange Online PowerShell of Exchange Online Protection PowerShell de volgende opdracht uit en controleer de instellingen:</span><span class="sxs-lookup"><span data-stu-id="1fe18-175">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="1fe18-176">Zie [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="1fe18-176">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>
