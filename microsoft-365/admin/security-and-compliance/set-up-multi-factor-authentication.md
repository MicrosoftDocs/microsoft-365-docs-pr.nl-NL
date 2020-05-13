---
title: Meervoudige verificatie instellen voor gebruikers
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Meer informatie over het gebruik van beveiligingsstandaards voor het instellen van meervoudige verificatie voor gebruikers.
monikerRange: o365-worldwide
ms.openlocfilehash: 4c0df9198db8154c1aa748a68eff29dd9bf3bca1
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213008"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="6801d-103">Meervoudige verificatie instellen</span><span class="sxs-lookup"><span data-stu-id="6801d-103">Set up multi-factor authentication</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6801d-104">Als u uw abonnement of proefversie na 21 oktober 2019 hebt gekocht en u onverwacht wordt gevraagd om multi-factor authenticatie (MFA), zijn [beveiligingsstandaards](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) automatisch ingeschakeld voor uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="6801d-104">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for multi-factor authentication (MFA), [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

<span data-ttu-id="6801d-105">Bij elk nieuw Microsoft 365-abonnement is automatisch [beveiligingsstandaards](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="6801d-105">Every new Microsoft 365 subscription will automatically have [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) turned on.</span></span> <span data-ttu-id="6801d-106">Dit betekent dat elke gebruiker multi-factor authenticatie (MFA) moet instellen en de Microsoft Authenticator-app op zijn mobiele apparaat moet installeren.</span><span class="sxs-lookup"><span data-stu-id="6801d-106">This means that every user will have to set up multi-factor authentication (MFA) and install the Microsoft Authenticator app on their mobile device.</span></span> <span data-ttu-id="6801d-107">Zie [MFA instellen voor een Microsoft 365-account voor](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14)meer informatie .</span><span class="sxs-lookup"><span data-stu-id="6801d-107">For more information, see [Set up MFA for a Microsoft 365 account](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>

<span data-ttu-id="6801d-108">De volgende negen beheerdersrollen moeten aanvullende verificatie uitvoeren wanneer ze zich aanmelden:</span><span class="sxs-lookup"><span data-stu-id="6801d-108">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>

- <span data-ttu-id="6801d-109">Globale beheerder</span><span class="sxs-lookup"><span data-stu-id="6801d-109">Global administrator</span></span>
- <span data-ttu-id="6801d-110">SharePoint-beheerder</span><span class="sxs-lookup"><span data-stu-id="6801d-110">SharePoint administrator</span></span>
- <span data-ttu-id="6801d-111">Exchange-beheerder</span><span class="sxs-lookup"><span data-stu-id="6801d-111">Exchange administrator</span></span>
- <span data-ttu-id="6801d-112">Beheerder van voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="6801d-112">Conditional Access administrator</span></span>
- <span data-ttu-id="6801d-113">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="6801d-113">Security administrator</span></span>
- <span data-ttu-id="6801d-114">Helpdesk- of wachtwoordbeheerder</span><span class="sxs-lookup"><span data-stu-id="6801d-114">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="6801d-115">Factureringsbeheerder</span><span class="sxs-lookup"><span data-stu-id="6801d-115">Billing administrator</span></span>
- <span data-ttu-id="6801d-116">Gebruikersbeheerder</span><span class="sxs-lookup"><span data-stu-id="6801d-116">User administrator</span></span>
- <span data-ttu-id="6801d-117">Verificatiebeheerder</span><span class="sxs-lookup"><span data-stu-id="6801d-117">Authentication administrator</span></span>

<span data-ttu-id="6801d-118">Alle andere gebruikers wordt gevraagd om indien nodig extra verificatie uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="6801d-118">All other users will be asked to perform additional authentication when needed.</span></span>

> [!NOTE]
> <span data-ttu-id="6801d-119">U moet een globale beheerder zijn om MFA in te stellen of te wijzigen</span><span class="sxs-lookup"><span data-stu-id="6801d-119">You must be a global admin to set up or modify MFA</span></span> <br><br>
> <span data-ttu-id="6801d-120">Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.</span><span class="sxs-lookup"><span data-stu-id="6801d-120">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="6801d-121">Als u MFA eerder hebt ingesteld met basislijnbeleid, [moet u deze uitschakelen om beveiligingsstandaardinstellingen in te schakelen.](#move-from-baseline-policies-to-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="6801d-121">If you have previously set up MFA with baseline policies, [you must turn them off to turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="6801d-122">Als u echter Microsoft 365 Business hebt of als uw abonnement [Azure Active Directory Premium P1 of Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/)bevat, u ook beleid voor voorwaardelijke [toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) instellen.</span><span class="sxs-lookup"><span data-stu-id="6801d-122">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium P1 or Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="6801d-123">Als u beleid voor voorwaardelijke toegang wilt gebruiken, moet u ervoor zorgen dat beveiligingsstandaards zijn uitgeschakeld en [moderne verificatie](#enable-modern-authentication-for-your-organization) is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="6801d-123">To use Conditional Access policies, you need to make sure security defaults are disabled and [modern authentication](#enable-modern-authentication-for-your-organization) is enabled.</span></span>

> [!TIP]
> <span data-ttu-id="6801d-124">Zie [Microsoft Authenticator gebruiken met Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411)om uw gebruikers uit te leggen hoe ze de Microsoft Authenticator-app kunnen instellen.</span><span class="sxs-lookup"><span data-stu-id="6801d-124">To explain to your users how to set up the Microsoft Authenticator app, see [Use Microsoft Authenticator with Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="6801d-125">Standaardinstellingen voor beveiliging beheren</span><span class="sxs-lookup"><span data-stu-id="6801d-125">Manage security defaults</span></span>

1. <span data-ttu-id="6801d-126">Meld u aan bij het [beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=834822) met globale-beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="6801d-126">Sign in to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with global admin credentials.</span></span>
2. <span data-ttu-id="6801d-127">Ga naar de [pagina Azure Active Directory - Eigenschappen](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="6801d-127">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3. <span data-ttu-id="6801d-128">Kies onderaan de pagina de optie **Standaardinstellingen voor beveiliging beheren**.</span><span class="sxs-lookup"><span data-stu-id="6801d-128">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="6801d-129">Kies **Ja** om beveiligingsstandaards in te schakelen en **Nee** om beveiligingsstandaards uit te schakelen en kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6801d-129">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="6801d-130">Overstappen van basislijnbeleid op standaardinstellingen voor beveiliging</span><span class="sxs-lookup"><span data-stu-id="6801d-130">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="6801d-131">Ga naar de [pagina Voorwaardelijke toegang - Beleid](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="6801d-131">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2. <span data-ttu-id="6801d-132">Kies elk basislijnbeleid dat is **ingeschakeld** en stel **Beleid inschakelen** in **op Uit**.</span><span class="sxs-lookup"><span data-stu-id="6801d-132">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
3. <span data-ttu-id="6801d-133">Ga naar de [pagina Azure Active Directory - Eigenschappen](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="6801d-133">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4. <span data-ttu-id="6801d-134">Kies onder aan de pagina **De standaardinstellingen voor Beveiliging beheren**en stel in het venster **Standaardinstellingen voor beveiliging inschakelen** **standaard** in om in te schakelen op **Ja**en kies **Vervolgens Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6801d-134">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**, and then choose **Save**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="6801d-135">Moderne verificatie inschakelen voor uw organisatie</span><span class="sxs-lookup"><span data-stu-id="6801d-135">Enable modern authentication for your organization</span></span>

<span data-ttu-id="6801d-136">Alle Office 2016-clienttoepassingen bieden ondersteuning voor MFA door middel van de Active Directory Authentication Library (ADAL).</span><span class="sxs-lookup"><span data-stu-id="6801d-136">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="6801d-137">Dit betekent dat app-wachtwoorden niet vereist zijn voor Office 2016-clients.</span><span class="sxs-lookup"><span data-stu-id="6801d-137">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="6801d-138">Zie [dit artikel](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings#app-passwords) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="6801d-138">See [this article](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings#app-passwords) for more information.</span></span>

<span data-ttu-id="6801d-139">U moet er echter voor zorgen dat uw Microsoft 365-abonnement is ingeschakeld voor ADAL of moderne verificatie.</span><span class="sxs-lookup"><span data-stu-id="6801d-139">However, you need to make sure your Microsoft 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="6801d-140">Als u moderne verificatie wilt inschakelen, gaat u naar het [Beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=834822) en selecteert u **Instellingen** \> **Instellingen**. Vervolgens kiest u op het tabblad **Services** de optie \*\* Moderne verificatie\*\* in de lijst.</span><span class="sxs-lookup"><span data-stu-id="6801d-140">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="6801d-141">Schakel het selectievakje **Moderne verificatie inschakelen (aanbevolen)** in het deelvenster **Moderne verificatie** in en kies **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6801d-141">Check the **Enable modern authentication (recommended)** box in the **Modern authentication** panel, and then choose **Save changes**.</span></span> 

    ![Moderne verificatievenster met selectievakje inschakelen aangevinkt.](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> <span data-ttu-id="6801d-143">Vanaf augustus 2017 hebben alle nieuwe Microsoft 365-abonnementen, waaronder Skype voor Bedrijven online en Exchange online, standaard moderne verificatie ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="6801d-143">As of August of 2017, all new Microsoft 365 subscriptions that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="6801d-144">U kunt de status van moderne verificatie voor de webversie van Skype voor Bedrijven controleren via de webversie van Skype voor Bedrijven PowerShell met globale beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="6801d-144">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="6801d-145">Voer Get-CsOAuthConfiguration uit om de uitvoer van ClientADALAuthOverride te controleren.</span><span class="sxs-lookup"><span data-stu-id="6801d-145">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="6801d-146">Als -ClientADALAuthOverride is 'toegestaan', is moderne verificatie ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="6801d-146">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="6801d-147">Als u uw MA-status wilt controleren voor Exchange Online, gaat u naar [Moderne verificatie inschakelen in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="6801d-147">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="6801d-148">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="6801d-148">Related articles</span></span>

[<span data-ttu-id="6801d-149">Top 10 manieren om Microsoft 365 te beveiligen voor bedrijfsabonnementen</span><span class="sxs-lookup"><span data-stu-id="6801d-149">Top 10 ways to secure Microsoft 365 for business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="6801d-150">Moderne verificatie inschakelen voor Office 2013 op Windows-apparaten</span><span class="sxs-lookup"><span data-stu-id="6801d-150">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
