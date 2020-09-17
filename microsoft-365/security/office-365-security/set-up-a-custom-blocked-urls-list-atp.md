---
title: Een aangepaste lijst met geblokkeerde Url's met behulp van behulp van vrije verbindingen instellen
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
description: Meer informatie over het instellen van een lijst met geblokkeerde Url's voor uw organisatie met behulp van Office 365 Advanced Threat Protection.
ms.openlocfilehash: f66d447b980cae4a4afbb706f26659c5976bdf37
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948088"
---
# <a name="set-up-a-custom-blocked-urls-list-using-atp-safe-links"></a><span data-ttu-id="fc4c1-103">Een aangepaste lijst met geblokkeerde Url's met behulp van behulp van vrije verbindingen instellen</span><span class="sxs-lookup"><span data-stu-id="fc4c1-103">Set up a custom blocked URLs list using ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fc4c1-104">Dit artikel is bedoeld voor zakelijke klanten die [Office 365 Advanced Threat Protection](office-365-atp.md) hebben.</span><span class="sxs-lookup"><span data-stu-id="fc4c1-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="fc4c1-105">Als u een thuisgebruiker bent die op zoek bent naar informatie over veilige koppelingen in Outlook, raadpleegt u [geavanceerde Outlook.com-beveiliging](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="fc4c1-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="fc4c1-106">Met [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) kan uw organisatie een aangepaste lijst met websites adressen (url's) hebben die zijn geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="fc4c1-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked.</span></span> <span data-ttu-id="fc4c1-107">Wanneer een URL is geblokkeerd, worden personen die op de koppeling naar de geblokkeerde URL klikken een [waarschuwingspagina](atp-safe-links-warning-pages.md) weergegeven die lijkt op de volgende afbeelding:</span><span class="sxs-lookup"><span data-stu-id="fc4c1-107">When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span>

![Deze site is geblokkeerd](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

<span data-ttu-id="fc4c1-109">De lijst met geblokkeerde Url's wordt gedefinieerd door het beveiligingsteam van Microsoft 365 voor bedrijven en de lijst is bedoeld voor iedereen in de organisatie die wordt bedekt met beleidsregels voor veilige koppelingen in Office 365.</span><span class="sxs-lookup"><span data-stu-id="fc4c1-109">The blocked URLs list is defined by your organization's Microsoft 365 for business security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span>

<span data-ttu-id="fc4c1-110">Lees dit artikel voor meer informatie over het instellen van de lijst met geblokkeerde Url's van uw organisatie voor veilige weergave-instellingen [in Office 365](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="fc4c1-110">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>

## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="fc4c1-111">Een aangepaste lijst met geblokkeerde Url's weergeven of bewerken</span><span class="sxs-lookup"><span data-stu-id="fc4c1-111">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="fc4c1-112">[Voor veilige koppelingen in Office 365](atp-safe-links.md) worden verschillende lijsten gebruikt, waaronder de aangepaste lijst met geblokkeerde url's van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="fc4c1-112">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list.</span></span> <span data-ttu-id="fc4c1-113">Als u de benodigde machtigingen hebt, kunt u de aangepaste lijst van uw organisatie instellen.</span><span class="sxs-lookup"><span data-stu-id="fc4c1-113">If you have the necessary permissions, you can set up your organization's custom list.</span></span> <span data-ttu-id="fc4c1-114">Dit doet u door het standaardbeleid voor veilige koppelingen van uw organisatie te bewerken.</span><span class="sxs-lookup"><span data-stu-id="fc4c1-114">You do this by editing your organization's default Safe Links policy.</span></span>

<span data-ttu-id="fc4c1-115">Als u een ATP-beleid wilt bewerken (of definiëren), moet u een van de rollen krijgen die in de volgende tabel worden beschreven:</span><span class="sxs-lookup"><span data-stu-id="fc4c1-115">To edit (or define) ATP policies, you must be assigned one of the roles described in the following table:</span></span>

****

|<span data-ttu-id="fc4c1-116">Rol</span><span class="sxs-lookup"><span data-stu-id="fc4c1-116">Role</span></span>|<span data-ttu-id="fc4c1-117">Where/hoe toegewezen</span><span class="sxs-lookup"><span data-stu-id="fc4c1-117">Where/how assigned</span></span>|
|---|---|
|<span data-ttu-id="fc4c1-118">globale beheerder</span><span class="sxs-lookup"><span data-stu-id="fc4c1-118">global administrator</span></span>|<span data-ttu-id="fc4c1-119">De persoon die zich registreert voor het kopen van Microsoft 365 is standaard een globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="fc4c1-119">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="fc4c1-120">(Zie [informatie over Microsoft 365-beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.)</span><span class="sxs-lookup"><span data-stu-id="fc4c1-120">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) to learn more.)</span></span>|
|<span data-ttu-id="fc4c1-121">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="fc4c1-121">Security Administrator</span></span>|<span data-ttu-id="fc4c1-122">Azure Active Directory-beheercentrum ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )</span><span class="sxs-lookup"><span data-stu-id="fc4c1-122">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="fc4c1-123">Beheer van organisatie van Exchange Online</span><span class="sxs-lookup"><span data-stu-id="fc4c1-123">Exchange Online Organization Management</span></span>|<span data-ttu-id="fc4c1-124">Exchange-Beheercentrum ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) )</span><span class="sxs-lookup"><span data-stu-id="fc4c1-124">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="fc4c1-125">of</span><span class="sxs-lookup"><span data-stu-id="fc4c1-125">or</span></span> <br>  <span data-ttu-id="fc4c1-126">PowerShell-cmdlets (Zie [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span><span class="sxs-lookup"><span data-stu-id="fc4c1-126">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span></span>|
|

> [!TIP]
> <span data-ttu-id="fc4c1-127">Als u meer wilt weten over rollen en machtigingen, raadpleegt u [machtigingen in de sectie beveiliging & nalevings centrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="fc4c1-127">To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a><span data-ttu-id="fc4c1-128">Een aangepaste lijst met geblokkeerde Url's weergeven of bewerken</span><span class="sxs-lookup"><span data-stu-id="fc4c1-128">To view or edit a custom blocked URLs list</span></span>

1. <span data-ttu-id="fc4c1-129">Ga naar [https://protection.office.com](https://protection.office.com) en meld u aan met uw werk-of schoolaccount.</span><span class="sxs-lookup"><span data-stu-id="fc4c1-129">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="fc4c1-130">Kies in het linker navigatiegedeelte onder **Threat Management**de optie **beleids** \> **veilige koppelingen**.</span><span class="sxs-lookup"><span data-stu-id="fc4c1-130">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>

3. <span data-ttu-id="fc4c1-131">Selecteer in de sectie **beleidsregels die van toepassing zijn op het hele organigram** de optie **standaard**en kies vervolgens **bewerken** (de knop bewerken lijkt op een potlood).</span><span class="sxs-lookup"><span data-stu-id="fc4c1-131">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span><br/><span data-ttu-id="fc4c1-132">![Klik op bewerken om uw standaardbeleid te bewerken voor beveiliging van beveiligde koppelingen](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span><span class="sxs-lookup"><span data-stu-id="fc4c1-132">![Click Edit to edit your default policy for Safe Links protection](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span></span><br/><span data-ttu-id="fc4c1-133">Hiermee kunt u de lijst met geblokkeerde Url's weergeven.</span><span class="sxs-lookup"><span data-stu-id="fc4c1-133">This enables you to view your list of blocked URLs.</span></span> <span data-ttu-id="fc4c1-134">Aanvankelijk zijn er mogelijk geen Url's weergegeven.</span><span class="sxs-lookup"><span data-stu-id="fc4c1-134">At first, you might not have any URLs listed here.</span></span><br/><span data-ttu-id="fc4c1-135">![Lijst met geblokkeerde Url's in het standaardbeleid voor veilige koppelingen](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span><span class="sxs-lookup"><span data-stu-id="fc4c1-135">![Blocked URLs list in the default Safe Links policy](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span></span>

4. <span data-ttu-id="fc4c1-136">Selecteer het vak **een geldige URL opgeven** , typ een URL en kies het plusteken ( **+** ).</span><span class="sxs-lookup"><span data-stu-id="fc4c1-136">Select the **Enter a valid URL** box, type a URL, and then choose the plus sign (**+**).</span></span>

5. <span data-ttu-id="fc4c1-137">Wanneer u klaar bent met het toevoegen van Url's, kiest u in de rechterbenedenhoek van het scherm de optie **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="fc4c1-137">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>

## <a name="a-few-things-to-keep-in-mind"></a><span data-ttu-id="fc4c1-138">Enkele dingen om rekening mee te houden</span><span class="sxs-lookup"><span data-stu-id="fc4c1-138">A few things to keep in mind</span></span>

<span data-ttu-id="fc4c1-139">Let op de volgende punten wanneer u Url's toevoegt aan de lijst:</span><span class="sxs-lookup"><span data-stu-id="fc4c1-139">While you add URLs to your list, keep the following points in mind:</span></span>

- <span data-ttu-id="fc4c1-140">Neem geen schuine streep naar **/** het einde van de URL.</span><span class="sxs-lookup"><span data-stu-id="fc4c1-140">Do not include a forward slash ( **/**) at the end of the URL.</span></span> <span data-ttu-id="fc4c1-141">U kunt bijvoorbeeld niet typen `https://www.contoso.com/` `https://www.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="fc4c1-141">For example, instead of entering `https://www.contoso.com/`, enter `https://www.contoso.com`.</span></span>

- <span data-ttu-id="fc4c1-142">U kunt alleen een domein-URL (zoals `contoso.com` of `tailspintoys.com` ) opgeven.</span><span class="sxs-lookup"><span data-stu-id="fc4c1-142">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`).</span></span> <span data-ttu-id="fc4c1-143">Dit blokkeert de klikken op een URL die het domein bevat.</span><span class="sxs-lookup"><span data-stu-id="fc4c1-143">This will block clicks on any URL that contains the domain.</span></span>

- <span data-ttu-id="fc4c1-144">U kunt een subdomein opgeven (like `toys.contoso.com*` ) zonder dat u een volledig domein (zoals `contoso.com` ) blokkeert.</span><span class="sxs-lookup"><span data-stu-id="fc4c1-144">You can specify a subdomain (like `toys.contoso.com*`) without blocking a full domain (like `contoso.com`).</span></span> <span data-ttu-id="fc4c1-145">Dit blokkeert de klikken op een URL die het subdomein bevat, maar blokkeert geen klikken op een URL die het volledige domein bevat.</span><span class="sxs-lookup"><span data-stu-id="fc4c1-145">This will block clicks any URL that contains the subdomain, but it won't block clicks to a URL that contains the full domain.</span></span>

- <span data-ttu-id="fc4c1-146">U kunt maximaal drie jokertekens ( \* ) per URL opnemen.</span><span class="sxs-lookup"><span data-stu-id="fc4c1-146">You can include up to three wildcard asterisks (\*) per URL.</span></span> <span data-ttu-id="fc4c1-147">In de volgende tabel ziet u enkele voorbeelden van wat u kunt invoeren en wat van invloed is op de invoer.</span><span class="sxs-lookup"><span data-stu-id="fc4c1-147">The following table lists some examples of what you can enter and what effect those entries have.</span></span>

****

|<span data-ttu-id="fc4c1-148">Voorbeeld van invoer</span><span class="sxs-lookup"><span data-stu-id="fc4c1-148">Example Entry</span></span>|<span data-ttu-id="fc4c1-149">Actie</span><span class="sxs-lookup"><span data-stu-id="fc4c1-149">What It Does</span></span>|
|---|---|
|<span data-ttu-id="fc4c1-150">`contoso.com` wel `*contoso.com*`</span><span class="sxs-lookup"><span data-stu-id="fc4c1-150">`contoso.com` or `*contoso.com*`</span></span>|<span data-ttu-id="fc4c1-151">Blokkeert het domein, subdomeinen en paden, zoals `https://www.contoso.com` , `https://sub.contoso.com` en `https://contoso.com/abc`</span><span class="sxs-lookup"><span data-stu-id="fc4c1-151">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `https://sub.contoso.com`, and `https://contoso.com/abc`</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="fc4c1-152">Blokkeert een site `https://contoso.com/a` maar geen extra subpadnamen zoals `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="fc4c1-152">Blocks a site `https://contoso.com/a` but not additional subpaths like `https://contoso.com/a/b`</span></span>|
|`https://contoso.com/a*`|<span data-ttu-id="fc4c1-153">Blokkeert een site `https://contoso.com/a` en extra subpadnamen, zoals `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="fc4c1-153">Blocks a site `https://contoso.com/a` and additional subpaths like `https://contoso.com/a/b`</span></span>|
|`https://toys.contoso.com*`|<span data-ttu-id="fc4c1-154">Blokkeert een subdomein (' Toys ' in dit geval), maar sta klikken op andere Url's voor het domein (zoals `https://contoso.com` of `https://home.contoso.com` ) toe.</span><span class="sxs-lookup"><span data-stu-id="fc4c1-154">Blocks a subdomain ("toys" in this case) but allow clicks to other domain URLs (like `https://contoso.com` or `https://home.contoso.com`).</span></span>|
|

> [!NOTE]
> <span data-ttu-id="fc4c1-155">Standaard kunt u alleen 500-Url's toevoegen aan de lijst met geblokkeerde URL'S in het standaardbeleid van Office 365 voor standaardverbindingen.</span><span class="sxs-lookup"><span data-stu-id="fc4c1-155">By default, you can only add 500 URLs to the blocked URL list in the Office 365 ATP Safe Links default policy.</span></span> <span data-ttu-id="fc4c1-156">Een individuele URL mag niet langer zijn dan 128 tekens.</span><span class="sxs-lookup"><span data-stu-id="fc4c1-156">An individual URL can't exceed 128 characters.</span></span> <span data-ttu-id="fc4c1-157">De lijst alle geblokkeerde URL'S mag niet langer zijn dan 10.000 tekens.</span><span class="sxs-lookup"><span data-stu-id="fc4c1-157">The entire Blocked URL list can't exceed 10,000 characters.</span></span>

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a><span data-ttu-id="fc4c1-158">Uitzonderingen definiëren voor bepaalde gebruikers in een organisatie</span><span class="sxs-lookup"><span data-stu-id="fc4c1-158">How to define exceptions for certain users in an organization</span></span>

<span data-ttu-id="fc4c1-159">Als u wilt dat bepaalde groepen Url's kunnen weergeven die mogelijk zijn geblokkeerd voor anderen, kunt u een beleid instellen voor veilige verbindingen voor specifieke geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="fc4c1-159">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients.</span></span> <span data-ttu-id="fc4c1-160">Zie [een aangepaste lijst met behulp van openbare koppelingen voor het maken van Url's instellen](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span><span class="sxs-lookup"><span data-stu-id="fc4c1-160">See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
