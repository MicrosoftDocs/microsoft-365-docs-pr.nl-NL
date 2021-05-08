---
title: Algemene instellingen configureren voor Safe koppelingen in Defender voor Office 365
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
description: Beheerders kunnen meer informatie krijgen over het weergeven en configureren van algemene instellingen (de lijst 'De volgende URL's blokkeren' en beveiliging voor Office 365-apps) voor Safe-koppelingen in Microsoft Defender voor Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 11544953bf348c47e697b3210da709cccdb31a7e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245838"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="4bb9b-103">Algemene instellingen configureren voor Safe koppelingen in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="4bb9b-103">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4bb9b-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="4bb9b-104">**Applies to**</span></span>
- [<span data-ttu-id="4bb9b-105">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="4bb9b-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="4bb9b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4bb9b-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="4bb9b-107">Dit artikel is bedoeld voor zakelijke klanten die [Microsoft Defender voor Office 365](defender-for-office-365.md) hebben.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="4bb9b-108">Als u een thuisgebruiker bent die informatie zoekt over Safelinks in Outlook, gaat u naar [Advanced Outlook.com-beveiliging.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="4bb9b-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="4bb9b-109">Safe Koppelingen is een functie in [Microsoft Defender voor Office 365](defender-for-office-365.md) waarmee url's worden gescand van binnenkomende e-mailberichten in de e-mailstroom en de tijd van klikverificatie van URL's en koppelingen in e-mailberichten en op andere locaties.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-109">Safe Links is a feature in [Microsoft Defender for Office 365](defender-for-office-365.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="4bb9b-110">Zie Koppelingen in Microsoft Defender voor Safe voor [meer Office 365.](safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="4bb9b-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="4bb9b-111">U configureert de Safe koppelingen in Safe koppelingenbeleid.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-111">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="4bb9b-112">Zie Beleidsregels voor [koppelingen instellen Safe Microsoft Defender voor](set-up-safe-links-policies.md)Office 365.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-112">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

<span data-ttu-id="4bb9b-113">Voor Safe koppelingen worden echter ook de volgende algemene instellingen gebruikt die u buiten het beleid Safe Koppelingen zelf configureert:</span><span class="sxs-lookup"><span data-stu-id="4bb9b-113">But, Safe Links also uses the following global settings that you configure outside of the Safe Links policies themselves:</span></span>

- <span data-ttu-id="4bb9b-114">De **lijst De volgende URL's** blokkeren.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-114">The **Block the following URLs** list.</span></span> <span data-ttu-id="4bb9b-115">Deze instelling is van toepassing op alle gebruikers die zijn opgenomen in een actief Safe Koppelingenbeleid.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-115">This setting applies to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="4bb9b-116">Zie 'De volgende [URL's blokkeren'](safe-links.md#block-the-following-urls-list-for-safe-links) voor meer Safe Koppelingen</span><span class="sxs-lookup"><span data-stu-id="4bb9b-116">For more information, see ["Block the following URLs" list for Safe Links](safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="4bb9b-117">Safe Koppelingenbeveiliging voor Office 365 apps.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-117">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="4bb9b-118">Deze instellingen zijn van toepassing op alle gebruikers in de organisatie die een licentie hebben voor Defender voor Office 365, ongeacht of de gebruikers zijn opgenomen in het beleid voor actieve Safe Koppelingen of niet.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-118">These settings apply to all users in the organization who are licensed for Defender for Office 365, regardless of whether the users are included in active Safe Links policies or not.</span></span> <span data-ttu-id="4bb9b-119">Zie de instellingen voor koppelingen Safe voor Office 365 [voor meer informatie.](safe-links.md#safe-links-settings-for-office-365-apps)</span><span class="sxs-lookup"><span data-stu-id="4bb9b-119">For more information, see [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="4bb9b-120">U kunt de algemene instellingen voor Safe Koppelingen configureren in het beveiligings- & compliancecentrum of in PowerShell (Exchange Online PowerShell voor in aanmerking komende Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken, maar met Microsoft Defender voor Office 365-invoegabonnementen).</span><span class="sxs-lookup"><span data-stu-id="4bb9b-120">You can configure the global Safe Links settings in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4bb9b-121">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="4bb9b-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4bb9b-122">Er is geen ingebouwd Safe standaardbeleid voor koppelingen, dus u moet ten minste één Safe-koppelingenbeleid maken om ervoor te zorgen dat de lijst Met de volgende **URL's** blokkeren actief is.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-122">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for the **Block the following URLs** list to be active.</span></span> <span data-ttu-id="4bb9b-123">Zie Beleidsregels voor [koppelingen instellen Safe Microsoft Defender voor](set-up-safe-links-policies.md)Office 365.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-123">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

- <span data-ttu-id="4bb9b-124">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="4bb9b-125">Als u rechtstreeks naar de pagina Safe **koppelingen wilt** gaan, gebruikt <https://protection.office.com/safelinksv2> u .</span><span class="sxs-lookup"><span data-stu-id="4bb9b-125">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="4bb9b-126">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="4bb9b-127">Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="4bb9b-128">U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="4bb9b-128">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="4bb9b-129">Als u de algemene instellingen voor Safe koppelingen wilt configureren, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="4bb9b-129">To configure the global settings for Safe Links, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="4bb9b-130">Voor alleen-lezen toegang tot de algemene instellingen voor Safe koppelingen,  moet u lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="4bb9b-130">For read-only access to the global settings for Safe Links, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="4bb9b-131">Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-131">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="4bb9b-132">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="4bb9b-132">**Notes**:</span></span>

  - <span data-ttu-id="4bb9b-133">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="4bb9b-134">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-134">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="4bb9b-135">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-135">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="4bb9b-136">Zie voor onze aanbevolen waarden voor de algemene instellingen voor Safe Koppelingen [Safe Koppelingen.](recommended-settings-for-eop-and-office365.md#safe-links-settings)</span><span class="sxs-lookup"><span data-stu-id="4bb9b-136">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365.md#safe-links-settings).</span></span>

- <span data-ttu-id="4bb9b-137">Maximaal 30 minuten toestaan dat een nieuw of bijgewerkt beleid wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="4bb9b-138">[Er worden voortdurend nieuwe functies toegevoegd aan Microsoft Defender voor Office 365.](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="4bb9b-138">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="4bb9b-139">Als er nieuwe functies worden toegevoegd, moet u mogelijk uw bestaande Safe koppelingenbeleid aanpassen.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a><span data-ttu-id="4bb9b-140">De lijst 'De volgende URL's blokkeren' configureren in het beveiligings- & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="4bb9b-140">Configure the "Block the following URLs" list in the Security & Compliance Center</span></span>

<span data-ttu-id="4bb9b-141">In **de lijst De volgende URL's** blokkeren worden de koppelingen geïdentificeerd die altijd moeten worden geblokkeerd door Safe Koppelingen scannen in ondersteunde apps.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-141">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="4bb9b-142">Zie 'De volgende [URL's blokkeren'](safe-links.md#block-the-following-urls-list-for-safe-links)voor meer Safe koppelingen.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-142">For more information, see ["Block the following URLs" list for Safe Links](safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="4bb9b-143">Ga in & Beveiligingscentrum naar  \>  \> **ATP-koppelingen** voor bedreigingsbeheerbeleid Safe en klik vervolgens op **Algemene instellingen.**</span><span class="sxs-lookup"><span data-stu-id="4bb9b-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="4bb9b-144">Ga in **Safe beleid voor koppelingen** voor uw organisatie dat wordt weergegeven naar het vak De volgende **URL's blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="4bb9b-144">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="4bb9b-145">Configureer een of meer vermeldingen zoals beschreven in [de syntaxis van entry voor de lijst 'De volgende URL's blokkeren'.](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="4bb9b-145">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="4bb9b-146">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-146">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="4bb9b-147">De lijst 'De volgende URL's blokkeren' configureren in PowerShell</span><span class="sxs-lookup"><span data-stu-id="4bb9b-147">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="4bb9b-148">Zie De syntaxis van invoer voor de lijst ['De volgende URL's blokkeren'](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)voor meer informatie over de syntaxis van het item.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-148">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="4bb9b-149">U kunt de **cmdlet Get-AtpPolicyForO365** gebruiken om bestaande items in de eigenschap _BlockURLs te_ bekijken.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-149">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="4bb9b-150">Als u waarden wilt toevoegen die bestaande vermeldingen vervangen, gebruikt u de volgende syntaxis in PowerShell Exchange Online PowerShell of Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4bb9b-150">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="4bb9b-151">In dit voorbeeld worden de volgende vermeldingen toegevoegd aan de lijst:</span><span class="sxs-lookup"><span data-stu-id="4bb9b-151">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="4bb9b-152">Blokkeer het domein, subdomeinen en paden voor fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-152">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="4bb9b-153">Het subdomeinonderzoek blokkeren, maar niet het bovenliggende domein of andere subdomeinen in tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="4bb9b-153">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="4bb9b-154">Als u waarden wilt toevoegen of verwijderen zonder dat dit van invloed is op andere bestaande vermeldingen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="4bb9b-154">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="4bb9b-155">In dit voorbeeld wordt een nieuw item voor adatum.com toegevoegd en wordt de vermelding voor fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-155">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a><span data-ttu-id="4bb9b-156">Beveiliging Safe koppelingen configureren voor Office 365 apps in het beveiligings- & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="4bb9b-156">Configure Safe Links protection for Office 365 apps in the Security & Compliance Center</span></span>

<span data-ttu-id="4bb9b-157">Safe Koppelingenbeveiliging voor Office 365 apps is van toepassing op documenten in ondersteunde Office desktop-, mobiele en web-apps.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-157">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="4bb9b-158">Zie de instellingen voor koppelingen Safe voor Office 365 [voor meer informatie.](safe-links.md#safe-links-settings-for-office-365-apps)</span><span class="sxs-lookup"><span data-stu-id="4bb9b-158">For more information, see [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="4bb9b-159">Ga in & Beveiligingscentrum naar  \>  \> **ATP-koppelingen** voor bedreigingsbeheerbeleid Safe en klik vervolgens op **Algemene instellingen.**</span><span class="sxs-lookup"><span data-stu-id="4bb9b-159">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="4bb9b-160">In het **Safe koppelingenbeleid** voor uw organisatie dat wordt weergegeven, configureert u de volgende instellingen in de Instellingen die van toepassing zijn op inhoud behalve e-mailsectie: </span><span class="sxs-lookup"><span data-stu-id="4bb9b-160">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content except email** section:</span></span>

   - <span data-ttu-id="4bb9b-161">**Office 365 toepassingen:** Controleer of de schakelknop rechts is om Safe Koppelingen in te schakelen voor ondersteunde Office 365 apps: ![ Schakel ](../../media/scc-toggle-on.png) in.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-161">**Office 365 applications**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="4bb9b-162">**Niet bijhouden wanneer** gebruikers op Safe Koppelingen klikken: Verplaats de schakelknop naar links om gebruikersklikken bij te houden die betrekking hebben op geblokkeerde URL's in ondersteunde Office 365-apps: ![ ](../../media/scc-toggle-off.png) Uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-162">**Do not track when users click Safe Links**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="4bb9b-163">Laat gebruikers niet door Safe Koppelingen naar de oorspronkelijke **URL klikken:** Controleer of de schakelknop rechts is om te voorkomen dat gebruikers doorklikken naar de oorspronkelijke geblokkeerde URL in ondersteunde Office 365-apps: Schakel ![ ](../../media/scc-toggle-on.png) in.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-163">**Do not let users click through Safe Links to the original URL**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="4bb9b-164">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-164">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="4bb9b-165">Beveiliging Safe koppelingen configureren voor Office 365 apps in PowerShell</span><span class="sxs-lookup"><span data-stu-id="4bb9b-165">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="4bb9b-166">Als u Liever PowerShell gebruikt om Safe koppelingen te configureren voor Office 365-apps, gebruikt u de volgende syntaxis in powershell Exchange Online PowerShell Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4bb9b-166">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="4bb9b-167">In dit voorbeeld worden de volgende instellingen geconfigureerd voor Safe koppelingenbeveiliging in Office 365 apps:</span><span class="sxs-lookup"><span data-stu-id="4bb9b-167">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="4bb9b-168">Safe Koppelingen voor Office 365 apps is ingeschakeld (we gebruiken de parameter _EnableSafeLinksForO365Clients_ niet en de standaardwaarde is $true).</span><span class="sxs-lookup"><span data-stu-id="4bb9b-168">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="4bb9b-169">Gebruikersklikken die betrekking hebben op geblokkeerde URL's in ondersteunde Office 365 apps worden bijgehouden.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-169">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="4bb9b-170">Gebruikers mogen niet doorklikken naar de oorspronkelijke geblokkeerde URL in ondersteunde Office 365-apps (we gebruiken de parameter _AllowClickThrough_ niet en de standaardwaarde is $false).</span><span class="sxs-lookup"><span data-stu-id="4bb9b-170">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="4bb9b-171">Zie [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-171">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="4bb9b-172">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="4bb9b-172">How do you know these procedures worked?</span></span>

<span data-ttu-id="4bb9b-173">Ga als volgt te werk om te controleren of u de algemene instellingen voor Safe-koppelingen hebt geconfigureerd (de lijst Met de volgende **URL's** blokkeren en de instellingen voor Office 365-app-beveiliging:</span><span class="sxs-lookup"><span data-stu-id="4bb9b-173">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="4bb9b-174">Ga in het & Compliancecentrum naar  \>  \> **ATP Safe-koppelingen** voor bedreigingsbeheerbeleid , klik op Algemene instellingen en controleer de instellingen in de fly-out die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-174">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="4bb9b-175">Voer in Exchange Online PowerShell of Exchange Online Protection PowerShell de volgende opdracht uit en controleer de instellingen:</span><span class="sxs-lookup"><span data-stu-id="4bb9b-175">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="4bb9b-176">Zie [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="4bb9b-176">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>
