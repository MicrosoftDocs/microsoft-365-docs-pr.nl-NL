---
title: Algemene instellingen configureren voorinstellingen voor veilige koppelingen in Defender voor Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie over het weergeven en configureren van globale instellingen (de lijst de volgende Url's blokkeren en beveiliging voor Office 365-apps) voor veilige koppelingen in Microsoft Defender voor Office 365.
ms.openlocfilehash: 655fba35bf3675bfd571c8e4923a00fbeba85304
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842426"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="5b971-103">Algemene instellingen configureren voor veilige koppelingen in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="5b971-103">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="5b971-104">Dit artikel is bedoeld voor zakelijke klanten met [Microsoft Defender voor Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="5b971-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="5b971-105">Als u een thuisgebruiker bent die op zoek bent naar informatie over Safelinks in Outlook, raadpleegt u [geavanceerde Outlook.com-beveiliging](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="5b971-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="5b971-106">Veilige koppelingen is een functie in [Microsoft Defender voor Office 365](office-365-atp.md) met het scannen van inkomende e-mailberichten in de e-mail stroom, en de tijd waarop u kunt klikken op verificatie van url's en koppelingen in e-mailberichten en andere locaties.</span><span class="sxs-lookup"><span data-stu-id="5b971-106">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="5b971-107">Zie voor meer informatie [veilige koppelingen in Microsoft Defender voor Office 365](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="5b971-107">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="5b971-108">U configureert de meeste instellingen voor veilige koppelingen in beleidsregels voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="5b971-108">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="5b971-109">Zie [beleid voor veilige koppelingen instellen in Microsoft Defender voor Office 365](set-up-atp-safe-links-policies.md)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="5b971-109">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

<span data-ttu-id="5b971-110">Voor veilige koppelingen worden ook globale instellingen gebruikt die van toepassing zijn op alle gebruikers die deel uitmaken van een actief beleid voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="5b971-110">But, Safe Links also uses global settings that apply to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="5b971-111">Dit gebied algemene instellingen:</span><span class="sxs-lookup"><span data-stu-id="5b971-111">These global settings area:</span></span>

- <span data-ttu-id="5b971-112">De lijst **de volgende Url's blokkeren** .</span><span class="sxs-lookup"><span data-stu-id="5b971-112">The **Block the following URLs** list.</span></span> <span data-ttu-id="5b971-113">Zie voor meer informatie [de lijst de volgende Url's blokkeren voor veilige koppelingen](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="5b971-113">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="5b971-114">Beveiliging van veilige koppelingen voor Office 365-apps.</span><span class="sxs-lookup"><span data-stu-id="5b971-114">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="5b971-115">Zie [instellingen voor veilige koppelingen voor Office 365-apps](atp-safe-links.md#safe-links-settings-for-office-365-apps)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5b971-115">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="5b971-116">U kunt de algemene instellingen voor veilige koppelingen in het beveiligings & nalevings centrum of in PowerShell (Exchange Online PowerShell) configureren voor in aanmerking komende Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder postvak van Exchange Online, maar met invoegtoepassingen voor Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="5b971-116">You can configure the global Safe Links settings in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5b971-117">Wat moet je weten voordat je begint?</span><span class="sxs-lookup"><span data-stu-id="5b971-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5b971-118">De functies van de algemene instellingen voor veilige koppelingen worden alleen toegepast op gebruikers die deel uitmaken van de beleidsregels voor actieve veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="5b971-118">The features provided by global settings for Safe Links are only applied to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="5b971-119">Er is geen ingebouwd of standaardbeleid voor veilige koppelingen, dus u moet minimaal één beleid voor veilige koppelingen maken om deze algemene instellingen te activeren.</span><span class="sxs-lookup"><span data-stu-id="5b971-119">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for these global settings to be active.</span></span> <span data-ttu-id="5b971-120">Zie [beleid voor veilige koppelingen instellen in Microsoft Defender voor Office 365](set-up-atp-safe-links-policies.md)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="5b971-120">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

- <span data-ttu-id="5b971-121">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="5b971-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="5b971-122">Als u rechtstreeks naar de pagina met **veilige koppelingen** wilt gaan, gebruikt u <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="5b971-122">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="5b971-123">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5b971-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="5b971-124">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5b971-124">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="5b971-125">Als u de algemene instellingen voor veilige koppelingen wilt weergeven en configureren, moet u lid zijn van een van de volgende groepen rollen:</span><span class="sxs-lookup"><span data-stu-id="5b971-125">To view and configure the global settings for Safe Links, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="5b971-126">**Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="5b971-126">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="5b971-127">**Organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="5b971-127">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="5b971-128">Zie [instellingen voor veilige koppelingen](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)voor de aanbevolen waarden voor de algemene instellingen voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="5b971-128">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).</span></span>

- <span data-ttu-id="5b971-129">Maximaal 30 minuten toegestaan voor het toepassen van een nieuwe of bijgewerkte beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="5b971-129">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="5b971-130">[Nieuwe functies worden continu toegevoegd aan Microsoft Defender voor Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="5b971-130">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="5b971-131">Wanneer nieuwe functies worden toegevoegd, moet u mogelijk uw bestaande beleid voor veilige koppelingen aanpassen.</span><span class="sxs-lookup"><span data-stu-id="5b971-131">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a><span data-ttu-id="5b971-132">De lijst ' de volgende Url's blokkeren ' in het beveiligings & nalevings centrum configureren</span><span class="sxs-lookup"><span data-stu-id="5b971-132">Configure the "Block the following URLs" list in the Security & Compliance Center</span></span>

<span data-ttu-id="5b971-133">De lijst **de volgende Url's blokkeren** identificeert de koppelingen die u altijd moet blokkeren door veilige koppelingen in ondersteunde apps te scannen.</span><span class="sxs-lookup"><span data-stu-id="5b971-133">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="5b971-134">Zie voor meer informatie [de lijst de volgende Url's blokkeren voor veilige koppelingen](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span><span class="sxs-lookup"><span data-stu-id="5b971-134">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="5b971-135">Ga in het beveiligings & nalevings centrum naar veilige koppelingen voor het beleid voor **bedreigings beheer** \> **Policy** \> **ATP Safe Links** en klik vervolgens op **algemene instellingen**.</span><span class="sxs-lookup"><span data-stu-id="5b971-135">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links** , and then click **Global settings**.</span></span>

2. <span data-ttu-id="5b971-136">Ga in het **beleid voor veilige koppelingen voor uw organisatie** dat wordt weergegeven naar het vak **Blokkeer de volgende url's** .</span><span class="sxs-lookup"><span data-stu-id="5b971-136">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="5b971-137">Configureer een of meer vermeldingen zoals beschreven in [de invoer syntaxis voor de lijst ' de volgende Url's blokkeren '](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="5b971-137">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="5b971-138">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="5b971-138">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="5b971-139">De lijst "de volgende Url's blokkeren" in PowerShell configureren</span><span class="sxs-lookup"><span data-stu-id="5b971-139">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="5b971-140">Zie de [invoer syntaxis voor de lijst ' de volgende Url's blokkeren '](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)voor meer informatie over de syntaxis van de invoer.</span><span class="sxs-lookup"><span data-stu-id="5b971-140">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="5b971-141">Met de cmdlet **Get-AtpPolicyForO365** kunt u bestaande vermeldingen in de _BlockURLs_ -eigenschap weergeven.</span><span class="sxs-lookup"><span data-stu-id="5b971-141">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="5b971-142">Als u waarden wilt toevoegen waarmee bestaande items worden vervangen, gebruikt u de volgende syntaxis in PowerShell van Exchange Online of Exchange Online Protection:</span><span class="sxs-lookup"><span data-stu-id="5b971-142">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="5b971-143">In het volgende voorbeeld worden de volgende items aan de lijst toegevoegd:</span><span class="sxs-lookup"><span data-stu-id="5b971-143">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="5b971-144">Blokkeer het domein, subdomeinen en paden voor fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="5b971-144">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="5b971-145">Het onderzoek subdomein blokkeren, maar niet het bovenliggende domein of andere subdomeinen in tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="5b971-145">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="5b971-146">Gebruik de volgende syntaxis om waarden toe te voegen of te verwijderen zonder dat dit invloed heeft op andere bestaande vermeldingen:</span><span class="sxs-lookup"><span data-stu-id="5b971-146">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="5b971-147">In dit voorbeeld wordt een nieuwe vermelding voor adatum.com toegevoegd en wordt de vermelding voor fabrikam.com verwijderd.</span><span class="sxs-lookup"><span data-stu-id="5b971-147">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a><span data-ttu-id="5b971-148">Beveiliging van veilige koppelingen voor Office 365-apps configureren in het beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="5b971-148">Configure Safe Links protection for Office 365 apps in the Security & Compliance Center</span></span>

<span data-ttu-id="5b971-149">Beveiliging van veilige koppelingen voor Office 365-apps is van toepassing op documenten in ondersteunde Office-Desktop-, mobiele en web-apps.</span><span class="sxs-lookup"><span data-stu-id="5b971-149">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="5b971-150">Zie [instellingen voor veilige koppelingen voor Office 365-apps](atp-safe-links.md#safe-links-settings-for-office-365-apps)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5b971-150">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="5b971-151">Ga in het beveiligings & nalevings centrum naar veilige koppelingen voor het beleid voor **bedreigings beheer** \> **Policy** \> **ATP Safe Links** en klik vervolgens op **algemene instellingen**.</span><span class="sxs-lookup"><span data-stu-id="5b971-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links** , and then click **Global settings**.</span></span>

2. <span data-ttu-id="5b971-152">In het **beleid voor veilige koppelingen voor uw organisatie** die wordt weergegeven, configureert u de volgende instellingen in de sectie **instellingen van toepassing op inhoud met uitzondering van e-mailberichten** :</span><span class="sxs-lookup"><span data-stu-id="5b971-152">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content except email** section:</span></span>

   - <span data-ttu-id="5b971-153">**Office 365-toepassingen** : Controleer of de wisselknop naar rechts is ingesteld voor ondersteunde Office 365-apps: Schakel ![ over ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .</span><span class="sxs-lookup"><span data-stu-id="5b971-153">**Office 365 applications** : Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="5b971-154">**Niet bijhouden wanneer gebruikers op veilige koppelingen klikken** : schuif de wisselknop naar links om de gebruikers klikken met geblokkeerde url's bij te houden in ondersteunde Office 365-apps: ![ uitschakelen ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="5b971-154">**Do not track when users click Safe Links** : Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="5b971-155">**Laat gebruikers niet via veilige koppelingen naar de oorspronkelijke URL klikken** : Controleer of de wisselknop zich rechts bevindt om te voorkomen dat gebruikers door doorgaan naar de oorspronkelijke geblokkeerde URL in ondersteunde Office 365-apps: ![ Schakel over ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .</span><span class="sxs-lookup"><span data-stu-id="5b971-155">**Do not let users click through Safe Links to the original URL** : Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   <span data-ttu-id="5b971-156">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="5b971-156">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="5b971-157">Beveiliging van veilige koppelingen voor Office 365-apps in PowerShell configureren</span><span class="sxs-lookup"><span data-stu-id="5b971-157">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="5b971-158">Als u liever met behulp van PowerShell de bescherming van veilige koppelingen voor Office 365-Apps wilt configureren, gebruikt u de volgende syntaxis in PowerShell van Exchange Online of Exchange Online Protection:</span><span class="sxs-lookup"><span data-stu-id="5b971-158">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="5b971-159">In dit voorbeeld worden de volgende instellingen geconfigureerd voor beveiliging van veilige koppelingen in Office 365-apps:</span><span class="sxs-lookup"><span data-stu-id="5b971-159">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="5b971-160">Veilige koppelingen voor Office 365-apps zijn ingeschakeld (de parameter _EnableSafeLinksForO365Clients_ wordt niet gebruikt en de standaardwaarde is $True).</span><span class="sxs-lookup"><span data-stu-id="5b971-160">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="5b971-161">De gebruiker klikt op met geblokkeerde Url's in ondersteunde Office 365-apps worden bijgehouden.</span><span class="sxs-lookup"><span data-stu-id="5b971-161">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="5b971-162">Gebruikers mogen niet op de oorspronkelijke geblokkeerde URL klikken in ondersteunde Office 365-apps (de _AllowClickThrough_ -parameter wordt niet gebruikt en de standaardwaarde is $False).</span><span class="sxs-lookup"><span data-stu-id="5b971-162">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="5b971-163">Zie [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="5b971-163">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="5b971-164">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="5b971-164">How do you know these procedures worked?</span></span>

<span data-ttu-id="5b971-165">Voer een van de volgende stappen uit om te controleren of u de algemene instellingen voor veilige koppelingen hebt geconfigureerd (de lijst **de volgende Url's blokkeren** en de instellingen voor de beveiligingsinstellingen van Office 365-apps):</span><span class="sxs-lookup"><span data-stu-id="5b971-165">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="5b971-166">Ga in het beveiligings & compliance naar veilige koppelingen voor het beleid voor **risicobeheer** \> **Policy** \> **ATP Safe Links** , klik op **algemene instellingen** en controleer de instellingen in het venster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="5b971-166">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links** , click **Global settings** , and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="5b971-167">Voer de volgende opdracht uit in PowerShell van Exchange Online of Exchange Online Protection en controleer de instellingen:</span><span class="sxs-lookup"><span data-stu-id="5b971-167">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="5b971-168">Zie [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="5b971-168">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>
