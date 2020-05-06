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
ms.custom:
- seo-marvel-apr2020
description: Meer informatie over het instellen van een lijst met geblokkeerde URL's voor uw organisatie met Office 365 Advanced Threat Protection.
ms.openlocfilehash: 9e0c6e75358c97a21ab0765edf5a15bafe53d75e
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44046314"
---
# <a name="set-up-a-custom-blocked-urls-list-using-atp-safe-links"></a><span data-ttu-id="2f818-103">Een aangepaste geblokkeerde URL-lijst instellen met ATP Safe Links</span><span class="sxs-lookup"><span data-stu-id="2f818-103">Set up a custom blocked URLs list using ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2f818-104">Dit artikel is bedoeld voor zakelijke klanten die [Office 365 Advanced Threat Protection](office-365-atp.md) hebben.</span><span class="sxs-lookup"><span data-stu-id="2f818-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="2f818-105">Zie [Geavanceerde Outlook.com beveiliging](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2)als u een thuisgebruiker bent die op zoek is naar informatie over veilige koppelingen in Outlook.</span><span class="sxs-lookup"><span data-stu-id="2f818-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="2f818-106">Met [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) kan uw organisatie een aangepaste lijst met websiteadressen (URL's) hebben die zijn geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="2f818-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked.</span></span> <span data-ttu-id="2f818-107">Wanneer een URL wordt geblokkeerd, worden mensen die op koppelingen naar de geblokkeerde URL klikken naar een [waarschuwingspagina](atp-safe-links-warning-pages.md) geleid die lijkt op de volgende afbeelding:</span><span class="sxs-lookup"><span data-stu-id="2f818-107">When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span> 
  
![Deze site is geblokkeerd](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
<span data-ttu-id="2f818-109">De lijst met geblokkeerde URL's wordt gedefinieerd door het Microsoft 365 voor zakelijke beveiligingsteam van uw organisatie en die lijst is van toepassing op iedereen in de organisatie die onder het beleid van Office 365 ATP Safe Links valt.</span><span class="sxs-lookup"><span data-stu-id="2f818-109">The blocked URLs list is defined by your organization's Microsoft 365 for business security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span> 
  
<span data-ttu-id="2f818-110">Lees dit artikel voor meer informatie over het instellen van de aangepaste geblokkeerde URL's-lijst van uw organisatie voor [ATP Safe Links in Office 365](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="2f818-110">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="2f818-111">Een aangepaste lijst met geblokkeerde URL's weergeven of bewerken</span><span class="sxs-lookup"><span data-stu-id="2f818-111">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="2f818-112">[ATP Safe Links in Office 365](atp-safe-links.md) gebruikt verschillende lijsten, waaronder de aangepaste geblokkeerde URL'slijst van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="2f818-112">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list.</span></span> <span data-ttu-id="2f818-113">Als u over de benodigde machtigingen beschikt, u de aangepaste lijst van uw organisatie instellen.</span><span class="sxs-lookup"><span data-stu-id="2f818-113">If you have the necessary permissions, you can set up your organization's custom list.</span></span> <span data-ttu-id="2f818-114">U doet dit door het standaardbeleid voor veilige koppelingen van uw organisatie te bewerken.</span><span class="sxs-lookup"><span data-stu-id="2f818-114">You do this by editing your organization's default Safe Links policy.</span></span>

<span data-ttu-id="2f818-115">Als u ATP-beleid wilt bewerken (of definiëren), moet u een van de rollen toegewezen krijgen die in de volgende tabel wordt beschreven:</span><span class="sxs-lookup"><span data-stu-id="2f818-115">To edit (or define) ATP policies, you must be assigned one of the roles described in the following table:</span></span> 

|<span data-ttu-id="2f818-116">Rol</span><span class="sxs-lookup"><span data-stu-id="2f818-116">Role</span></span>  |<span data-ttu-id="2f818-117">Waar/hoe toegewezen</span><span class="sxs-lookup"><span data-stu-id="2f818-117">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="2f818-118">globale beheerder</span><span class="sxs-lookup"><span data-stu-id="2f818-118">global administrator</span></span> |<span data-ttu-id="2f818-119">De persoon die zich aanmeldt om Microsoft 365 te kopen is standaard een globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="2f818-119">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="2f818-120">(Zie [Over Microsoft 365-beheerdersrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) voor meer informatie.)</span><span class="sxs-lookup"><span data-stu-id="2f818-120">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="2f818-121">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="2f818-121">Security Administrator</span></span> |<span data-ttu-id="2f818-122">Azure Active Directory-beheercentrum ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="2f818-122">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="2f818-123">Exchange Online Organisatiebeheer</span><span class="sxs-lookup"><span data-stu-id="2f818-123">Exchange Online Organization Management</span></span> |<span data-ttu-id="2f818-124">Exchange-beheercentrum[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)( )</span><span class="sxs-lookup"><span data-stu-id="2f818-124">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="2f818-125">of</span><span class="sxs-lookup"><span data-stu-id="2f818-125">or</span></span> <br>  <span data-ttu-id="2f818-126">PowerShell-cmdlets (Zie [Exchange Online PowerShell)](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="2f818-126">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))</span></span> |

> [!TIP]
> <span data-ttu-id="2f818-127">Zie [Machtigingen in het Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)voor meer informatie over rollen en machtigingen.</span><span class="sxs-lookup"><span data-stu-id="2f818-127">To learn more about roles and permissions, see [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a><span data-ttu-id="2f818-128">Een aangepaste geblokkeerde URL-lijst weergeven of bewerken</span><span class="sxs-lookup"><span data-stu-id="2f818-128">To view or edit a custom blocked URLs list</span></span>
  
1. <span data-ttu-id="2f818-129">Ga [https://protection.office.com](https://protection.office.com) naar en meld je aan met je werk- of schoolaccount.</span><span class="sxs-lookup"><span data-stu-id="2f818-129">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="2f818-130">Kies in de linkernavigatie onder **Bedreigingsbeheer** **de** \> optie Veilige **koppelingen beleid**.</span><span class="sxs-lookup"><span data-stu-id="2f818-130">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="2f818-131">Selecteer **Standaard**en kies Bewerken in **de sectie Beleid dat van toepassing is op de hele organisatiesectie** en kies **Bewerken** (de knop Bewerken lijkt op een potlood).</span><span class="sxs-lookup"><span data-stu-id="2f818-131">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span><br/><span data-ttu-id="2f818-132">![Klik op Bewerken om uw standaardbeleid voor beveiliging van veilige koppelingen te bewerken](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span><span class="sxs-lookup"><span data-stu-id="2f818-132">![Click Edit to edit your default policy for Safe Links protection](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span></span><br/><span data-ttu-id="2f818-133">Hiermee u uw lijst met geblokkeerde URL's bekijken.</span><span class="sxs-lookup"><span data-stu-id="2f818-133">This enables you to view your list of blocked URLs.</span></span> <span data-ttu-id="2f818-134">In eerste instantie hebt u hier mogelijk geen URL's.</span><span class="sxs-lookup"><span data-stu-id="2f818-134">At first, you might not have any URLs listed here.</span></span><br/><span data-ttu-id="2f818-135">![Lijst met geblokkeerde URL's in het standaardbeleid voor veilige koppelingen](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span><span class="sxs-lookup"><span data-stu-id="2f818-135">![Blocked URLs list in the default Safe Links policy](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span></span>
  
4. <span data-ttu-id="2f818-136">Selecteer het vak **Een geldige URL invoeren,** typ een**+** URL en kies het plusteken ( ).</span><span class="sxs-lookup"><span data-stu-id="2f818-136">Select the **Enter a valid URL** box, type a URL, and then choose the plus sign (**+**).</span></span> 

5. <span data-ttu-id="2f818-137">Wanneer u klaar bent met het toevoegen van URL's, kiest u in de rechterbenedenhoek van het scherm **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="2f818-137">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
## <a name="a-few-things-to-keep-in-mind"></a><span data-ttu-id="2f818-138">Een paar dingen om in gedachten te houden</span><span class="sxs-lookup"><span data-stu-id="2f818-138">A few things to keep in mind</span></span>

<span data-ttu-id="2f818-139">Houd de volgende punten in gedachten terwijl u URL's aan uw lijst toevoegt:</span><span class="sxs-lookup"><span data-stu-id="2f818-139">While you add URLs to your list, keep the following points in mind:</span></span> 

- <span data-ttu-id="2f818-140">Voeg geen slash (forward) **/** toe aan het einde van de URL.</span><span class="sxs-lookup"><span data-stu-id="2f818-140">Do not include a forward slash ( **/**) at the end of the URL.</span></span> <span data-ttu-id="2f818-141">Bijvoorbeeld, in plaats `https://www.contoso.com/`van `https://www.contoso.com`het invoeren , voer .</span><span class="sxs-lookup"><span data-stu-id="2f818-141">For example, instead of entering `https://www.contoso.com/`, enter `https://www.contoso.com`.</span></span>
    
- <span data-ttu-id="2f818-142">U een URL voor `contoso.com` alleen `tailspintoys.com`een domein opgeven (likeof ).</span><span class="sxs-lookup"><span data-stu-id="2f818-142">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`).</span></span> <span data-ttu-id="2f818-143">Hiermee worden klikken op elke URL die het domein bevat geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="2f818-143">This will block clicks on any URL that contains the domain.</span></span>

- <span data-ttu-id="2f818-144">U een subdomein `toys.contoso.com*`(leuk) opgeven zonder `contoso.com`een volledig domein (zoals) te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="2f818-144">You can specify a subdomain (like `toys.contoso.com*`) without blocking a full domain (like `contoso.com`).</span></span> <span data-ttu-id="2f818-145">Hiermee worden klikken op elke URL die het subdomein bevat geblokkeerd, maar worden klikken naar een URL die het volledige domein bevat, niet geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="2f818-145">This will block clicks any URL that contains the subdomain, but it won't block clicks to a URL that contains the full domain.</span></span>  
    
- <span data-ttu-id="2f818-146">U maximaal drie sterretjes\*() per URL opnemen.</span><span class="sxs-lookup"><span data-stu-id="2f818-146">You can include up to three wildcard asterisks (\*) per URL.</span></span> <span data-ttu-id="2f818-147">In de volgende tabel worden enkele voorbeelden weergegeven van wat u invoeren en welk effect deze vermeldingen hebben.</span><span class="sxs-lookup"><span data-stu-id="2f818-147">The following table lists some examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="2f818-148">**Voorbeeldvermelding**</span><span class="sxs-lookup"><span data-stu-id="2f818-148">**Example Entry**</span></span>|<span data-ttu-id="2f818-149">**Wat het doet**</span><span class="sxs-lookup"><span data-stu-id="2f818-149">**What It Does**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2f818-150">`contoso.com`Of`*contoso.com*`</span><span class="sxs-lookup"><span data-stu-id="2f818-150">`contoso.com` or `*contoso.com*`</span></span>  <br/> |<span data-ttu-id="2f818-151">Blokkeert het domein, subdomeinen en `https://www.contoso.com`paden, zoals , `https://sub.contoso.com`en`https://contoso.com/abc`</span><span class="sxs-lookup"><span data-stu-id="2f818-151">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `https://sub.contoso.com`, and `https://contoso.com/abc`</span></span>  <br/> |
|`https://contoso.com/a`  <br/> |<span data-ttu-id="2f818-152">Blokkeert een `https://contoso.com/a` site, maar geen extra subpaden zoals`https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="2f818-152">Blocks a site `https://contoso.com/a` but not additional subpaths like `https://contoso.com/a/b`</span></span>  <br/> |
|`https://contoso.com/a*`  <br/> |<span data-ttu-id="2f818-153">Blokkeert een `https://contoso.com/a` site en extra subpaden zoals`https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="2f818-153">Blocks a site `https://contoso.com/a` and additional subpaths like `https://contoso.com/a/b`</span></span>  <br/> |
|`https://toys.contoso.com*`  <br/> |<span data-ttu-id="2f818-154">Blokkeert een subdomein ("speelgoed" in dit geval), maar laat `https://contoso.com` `https://home.contoso.com`klikken toe naar andere domein-URL's (zoals of ).</span><span class="sxs-lookup"><span data-stu-id="2f818-154">Blocks a subdomain ("toys" in this case) but allow clicks to other domain URLs (like `https://contoso.com` or `https://home.contoso.com`).</span></span>  <br/> |
   

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a><span data-ttu-id="2f818-155">Uitzonderingen definiëren voor bepaalde gebruikers in een organisatie</span><span class="sxs-lookup"><span data-stu-id="2f818-155">How to define exceptions for certain users in an organization</span></span>

<span data-ttu-id="2f818-156">Als u wilt dat bepaalde groepen URL's kunnen weergeven die mogelijk voor anderen zijn geblokkeerd, u een BELEID voor veilige koppelingen van ATP opgeven dat van toepassing is op specifieke ontvangers.</span><span class="sxs-lookup"><span data-stu-id="2f818-156">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients.</span></span> <span data-ttu-id="2f818-157">Zie [Een aangepaste URL's-lijst 'niet herschrijven' instellen met BEHULP van ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span><span class="sxs-lookup"><span data-stu-id="2f818-157">See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
  

