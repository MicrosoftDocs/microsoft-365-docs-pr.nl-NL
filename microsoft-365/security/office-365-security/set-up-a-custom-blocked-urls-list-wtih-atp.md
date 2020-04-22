---
title: Een aangepaste geblokkeerde URL-lijst instellen met ATP Safe Links
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
ms.collection:
- M365-security-compliance
description: Meer informatie over het instellen van een lijst met geblokkeerde URL's voor uw organisatie met Office 365 Advanced Threat Protection. De geblokkeerde URL's zijn van toepassing op e-mailberichten en Office-documenten volgens uw ATP-beleid voor veilige koppelingen.
ms.openlocfilehash: ff8709a8bf0f8afc27ace2b3977be975f42c33a5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638402"
---
# <a name="set-up-a-custom-blocked-urls-list-using-atp-safe-links"></a><span data-ttu-id="6e1e0-104">Een aangepaste geblokkeerde URL-lijst instellen met ATP Safe Links</span><span class="sxs-lookup"><span data-stu-id="6e1e0-104">Set up a custom blocked URLs list using ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6e1e0-105">Dit artikel is bedoeld voor zakelijke klanten die [Office 365 Advanced Threat Protection](office-365-atp.md) hebben.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-105">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="6e1e0-106">Zie [Geavanceerde Outlook.com beveiliging](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2)als u een thuisgebruiker bent die op zoek is naar informatie over veilige koppelingen in Outlook.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-106">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="6e1e0-107">Met [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) kan uw organisatie een aangepaste lijst met websiteadressen (URL's) hebben die zijn geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-107">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked.</span></span> <span data-ttu-id="6e1e0-108">Wanneer een URL wordt geblokkeerd, worden mensen die op koppelingen naar de geblokkeerde URL klikken naar een [waarschuwingspagina](atp-safe-links-warning-pages.md) geleid die lijkt op de volgende afbeelding:</span><span class="sxs-lookup"><span data-stu-id="6e1e0-108">When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span> 
  
![Deze site is geblokkeerd](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
<span data-ttu-id="6e1e0-110">De lijst met geblokkeerde URL's wordt gedefinieerd door het Microsoft 365 voor zakelijke beveiligingsteam van uw organisatie en die lijst is van toepassing op iedereen in de organisatie die onder het beleid van Office 365 ATP Safe Links valt.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-110">The blocked URLs list is defined by your organization's Microsoft 365 for business security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span> 
  
<span data-ttu-id="6e1e0-111">Lees dit artikel voor meer informatie over het instellen van de aangepaste geblokkeerde URL's-lijst van uw organisatie voor [ATP Safe Links in Office 365](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="6e1e0-111">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="6e1e0-112">Een aangepaste lijst met geblokkeerde URL's weergeven of bewerken</span><span class="sxs-lookup"><span data-stu-id="6e1e0-112">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="6e1e0-113">[ATP Safe Links in Office 365](atp-safe-links.md) gebruikt verschillende lijsten, waaronder de aangepaste geblokkeerde URL'slijst van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-113">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list.</span></span> <span data-ttu-id="6e1e0-114">Als u over de benodigde machtigingen beschikt, u de aangepaste lijst van uw organisatie instellen.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-114">If you have the necessary permissions, you can set up your organization's custom list.</span></span> <span data-ttu-id="6e1e0-115">U doet dit door het standaardbeleid voor veilige koppelingen van uw organisatie te bewerken.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-115">You do this by editing your organization's default Safe Links policy.</span></span>

<span data-ttu-id="6e1e0-116">Als u ATP-beleid wilt bewerken (of definiëren), moet u een van de rollen toegewezen krijgen die in de volgende tabel wordt beschreven:</span><span class="sxs-lookup"><span data-stu-id="6e1e0-116">To edit (or define) ATP policies, you must be assigned one of the roles described in the following table:</span></span> 

|<span data-ttu-id="6e1e0-117">Rol</span><span class="sxs-lookup"><span data-stu-id="6e1e0-117">Role</span></span>  |<span data-ttu-id="6e1e0-118">Waar/hoe toegewezen</span><span class="sxs-lookup"><span data-stu-id="6e1e0-118">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="6e1e0-119">globale beheerder</span><span class="sxs-lookup"><span data-stu-id="6e1e0-119">global administrator</span></span> |<span data-ttu-id="6e1e0-120">De persoon die zich aanmeldt om Microsoft 365 te kopen is standaard een globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-120">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="6e1e0-121">(Zie [Over Microsoft 365-beheerdersrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) voor meer informatie.)</span><span class="sxs-lookup"><span data-stu-id="6e1e0-121">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="6e1e0-122">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="6e1e0-122">Security Administrator</span></span> |<span data-ttu-id="6e1e0-123">Azure Active Directory-beheercentrum ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="6e1e0-123">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="6e1e0-124">Exchange Online Organisatiebeheer</span><span class="sxs-lookup"><span data-stu-id="6e1e0-124">Exchange Online Organization Management</span></span> |<span data-ttu-id="6e1e0-125">Exchange-beheercentrum[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)( )</span><span class="sxs-lookup"><span data-stu-id="6e1e0-125">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="6e1e0-126">of</span><span class="sxs-lookup"><span data-stu-id="6e1e0-126">or</span></span> <br>  <span data-ttu-id="6e1e0-127">PowerShell-cmdlets (Zie [Exchange Online PowerShell)](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="6e1e0-127">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))</span></span> |

> [!TIP]
> <span data-ttu-id="6e1e0-128">Zie [Machtigingen in het Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)voor meer informatie over rollen en machtigingen.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-128">To learn more about roles and permissions, see [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a><span data-ttu-id="6e1e0-129">Een aangepaste geblokkeerde URL-lijst weergeven of bewerken</span><span class="sxs-lookup"><span data-stu-id="6e1e0-129">To view or edit a custom blocked URLs list</span></span>
  
1. <span data-ttu-id="6e1e0-130">Ga [https://protection.office.com](https://protection.office.com) naar en meld je aan met je werk- of schoolaccount.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-130">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="6e1e0-131">Kies in de linkernavigatie onder **Bedreigingsbeheer** **de** \> optie Veilige **koppelingen beleid**.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-131">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="6e1e0-132">Selecteer **Standaard**en kies Bewerken in **de sectie Beleid dat van toepassing is op de hele organisatiesectie** en kies **Bewerken** (de knop Bewerken lijkt op een potlood).</span><span class="sxs-lookup"><span data-stu-id="6e1e0-132">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span><br/><span data-ttu-id="6e1e0-133">![Klik op Bewerken om uw standaardbeleid voor beveiliging van veilige koppelingen te bewerken](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span><span class="sxs-lookup"><span data-stu-id="6e1e0-133">![Click Edit to edit your default policy for Safe Links protection](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span></span><br/><span data-ttu-id="6e1e0-134">Hiermee u uw lijst met geblokkeerde URL's bekijken.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-134">This enables you to view your list of blocked URLs.</span></span> <span data-ttu-id="6e1e0-135">In eerste instantie hebt u hier mogelijk geen URL's.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-135">At first, you might not have any URLs listed here.</span></span><br/><span data-ttu-id="6e1e0-136">![Lijst met geblokkeerde URL's in het standaardbeleid voor veilige koppelingen](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span><span class="sxs-lookup"><span data-stu-id="6e1e0-136">![Blocked URLs list in the default Safe Links policy](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span></span>
  
4. <span data-ttu-id="6e1e0-137">Selecteer het vak **Een geldige URL invoeren,** typ een**+** URL en kies het plusteken ( ).</span><span class="sxs-lookup"><span data-stu-id="6e1e0-137">Select the **Enter a valid URL** box, type a URL, and then choose the plus sign (**+**).</span></span> 

5. <span data-ttu-id="6e1e0-138">Wanneer u klaar bent met het toevoegen van URL's, kiest u in de rechterbenedenhoek van het scherm **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-138">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
## <a name="a-few-things-to-keep-in-mind"></a><span data-ttu-id="6e1e0-139">Een paar dingen om in gedachten te houden</span><span class="sxs-lookup"><span data-stu-id="6e1e0-139">A few things to keep in mind</span></span>

<span data-ttu-id="6e1e0-140">Houd de volgende punten in gedachten terwijl u URL's aan uw lijst toevoegt:</span><span class="sxs-lookup"><span data-stu-id="6e1e0-140">While you add URLs to your list, keep the following points in mind:</span></span> 

- <span data-ttu-id="6e1e0-141">Voeg geen slash (forward) **/** toe aan het einde van de URL.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-141">Do not include a forward slash ( **/**) at the end of the URL.</span></span> <span data-ttu-id="6e1e0-142">Bijvoorbeeld, in plaats `https://www.contoso.com/`van `https://www.contoso.com`het invoeren , voer .</span><span class="sxs-lookup"><span data-stu-id="6e1e0-142">For example, instead of entering `https://www.contoso.com/`, enter `https://www.contoso.com`.</span></span>
    
- <span data-ttu-id="6e1e0-143">U een URL voor `contoso.com` alleen `tailspintoys.com`een domein opgeven (likeof ).</span><span class="sxs-lookup"><span data-stu-id="6e1e0-143">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`).</span></span> <span data-ttu-id="6e1e0-144">Hiermee worden klikken op elke URL die het domein bevat geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-144">This will block clicks on any URL that contains the domain.</span></span>

- <span data-ttu-id="6e1e0-145">U een subdomein `toys.contoso.com*`(leuk) opgeven zonder `contoso.com`een volledig domein (zoals) te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-145">You can specify a subdomain (like `toys.contoso.com*`) without blocking a full domain (like `contoso.com`).</span></span> <span data-ttu-id="6e1e0-146">Hiermee worden klikken op elke URL die het subdomein bevat geblokkeerd, maar worden klikken naar een URL die het volledige domein bevat, niet geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-146">This will block clicks any URL that contains the subdomain, but it won't block clicks to a URL that contains the full domain.</span></span>  
    
- <span data-ttu-id="6e1e0-147">U maximaal drie sterretjes\*() per URL opnemen.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-147">You can include up to three wildcard asterisks (\*) per URL.</span></span> <span data-ttu-id="6e1e0-148">In de volgende tabel worden enkele voorbeelden weergegeven van wat u invoeren en welk effect deze vermeldingen hebben.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-148">The following table lists some examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="6e1e0-149">**Voorbeeldvermelding**</span><span class="sxs-lookup"><span data-stu-id="6e1e0-149">**Example Entry**</span></span>|<span data-ttu-id="6e1e0-150">**Wat het doet**</span><span class="sxs-lookup"><span data-stu-id="6e1e0-150">**What It Does**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6e1e0-151">`contoso.com`Of`*contoso.com*`</span><span class="sxs-lookup"><span data-stu-id="6e1e0-151">`contoso.com` or `*contoso.com*`</span></span>  <br/> |<span data-ttu-id="6e1e0-152">Blokkeert het domein, subdomeinen en `https://www.contoso.com`paden, zoals , `https://sub.contoso.com`en`https://contoso.com/abc`</span><span class="sxs-lookup"><span data-stu-id="6e1e0-152">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `https://sub.contoso.com`, and `https://contoso.com/abc`</span></span>  <br/> |
|`https://contoso.com/a`  <br/> |<span data-ttu-id="6e1e0-153">Blokkeert een `https://contoso.com/a` site, maar geen extra subpaden zoals`https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="6e1e0-153">Blocks a site `https://contoso.com/a` but not additional subpaths like `https://contoso.com/a/b`</span></span>  <br/> |
|`https://contoso.com/a*`  <br/> |<span data-ttu-id="6e1e0-154">Blokkeert een `https://contoso.com/a` site en extra subpaden zoals`https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="6e1e0-154">Blocks a site `https://contoso.com/a` and additional subpaths like `https://contoso.com/a/b`</span></span>  <br/> |
|`https://toys.contoso.com*`  <br/> |<span data-ttu-id="6e1e0-155">Blokkeert een subdomein ("speelgoed" in dit geval), maar laat `https://contoso.com` `https://home.contoso.com`klikken toe naar andere domein-URL's (zoals of ).</span><span class="sxs-lookup"><span data-stu-id="6e1e0-155">Blocks a subdomain ("toys" in this case) but allow clicks to other domain URLs (like `https://contoso.com` or `https://home.contoso.com`).</span></span>  <br/> |
   

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a><span data-ttu-id="6e1e0-156">Uitzonderingen definiëren voor bepaalde gebruikers in een organisatie</span><span class="sxs-lookup"><span data-stu-id="6e1e0-156">How to define exceptions for certain users in an organization</span></span>

<span data-ttu-id="6e1e0-157">Als u wilt dat bepaalde groepen URL's kunnen weergeven die mogelijk voor anderen zijn geblokkeerd, u een BELEID voor veilige koppelingen van ATP opgeven dat van toepassing is op specifieke ontvangers.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-157">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients.</span></span> <span data-ttu-id="6e1e0-158">Zie [Een aangepaste URL's-lijst 'niet herschrijven' instellen met BEHULP van ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span><span class="sxs-lookup"><span data-stu-id="6e1e0-158">See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
  

