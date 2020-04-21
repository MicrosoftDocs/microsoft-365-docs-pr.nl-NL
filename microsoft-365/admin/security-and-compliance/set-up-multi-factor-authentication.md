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
ms.openlocfilehash: 4a829aa597596564b9c2f468e72f3a766b198372
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627678"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="2f6a7-103">Meervoudige verificatie instellen</span><span class="sxs-lookup"><span data-stu-id="2f6a7-103">Set up multi-factor authentication</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2f6a7-104">Als u uw abonnement of proefversie na 21 oktober 2019 hebt gekocht en u onverwacht wordt gevraagd voor MFA, zijn [beveiligingsstandaards](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) automatisch ingeschakeld voor uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-104">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

<span data-ttu-id="2f6a7-105">Bij elk nieuw Microsoft 365-abonnement is automatisch beveiligingsstandaards ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-105">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="2f6a7-106">Dit betekent dat alle gebruikers meervoudige verificatie (MFA) moeten instellen en de verificatie-app op hun mobiele apparaat moeten installeren.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-106">This means that every user will have to set up multi-factor authentication (MFA) and install the Authenticator app on their mobile device.</span></span> <span data-ttu-id="2f6a7-107">Zie [Verificatie in twee stappen instellen voor Microsoft 365 voor](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-107">For more information, see [Set up 2-step verification for Microsoft 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>  

<span data-ttu-id="2f6a7-108">De volgende negen beheerdersrollen moeten aanvullende verificatie uitvoeren wanneer ze zich aanmelden:</span><span class="sxs-lookup"><span data-stu-id="2f6a7-108">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>

- <span data-ttu-id="2f6a7-109">Globale beheerder</span><span class="sxs-lookup"><span data-stu-id="2f6a7-109">Global administrator</span></span>
- <span data-ttu-id="2f6a7-110">SharePoint-beheerder</span><span class="sxs-lookup"><span data-stu-id="2f6a7-110">SharePoint administrator</span></span>
- <span data-ttu-id="2f6a7-111">Exchange-beheerder</span><span class="sxs-lookup"><span data-stu-id="2f6a7-111">Exchange administrator</span></span>
- <span data-ttu-id="2f6a7-112">Beheerder van voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="2f6a7-112">Conditional Access administrator</span></span>
- <span data-ttu-id="2f6a7-113">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="2f6a7-113">Security administrator</span></span>
- <span data-ttu-id="2f6a7-114">Helpdesk- of wachtwoordbeheerder</span><span class="sxs-lookup"><span data-stu-id="2f6a7-114">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="2f6a7-115">Factureringsbeheerder</span><span class="sxs-lookup"><span data-stu-id="2f6a7-115">Billing administrator</span></span>
- <span data-ttu-id="2f6a7-116">Gebruikersbeheerder</span><span class="sxs-lookup"><span data-stu-id="2f6a7-116">User administrator</span></span>
- <span data-ttu-id="2f6a7-117">Verificatiebeheerder</span><span class="sxs-lookup"><span data-stu-id="2f6a7-117">Authentication administrator</span></span>

<span data-ttu-id="2f6a7-118">Alle andere gebruikers wordt gevraagd om indien nodig extra verificatie uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-118">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="2f6a7-119">Zie [Wat zijn beveiligingsstandaardinstellingen voor](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)meer informatie?</span><span class="sxs-lookup"><span data-stu-id="2f6a7-119">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

> [!NOTE]
> <span data-ttu-id="2f6a7-120">U moet een globale beheerder zijn om meervoudige verificatie in te stellen of te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-120">You must be a global admin to set up or modify multi-factor authentication.</span></span> <br><br>
> <span data-ttu-id="2f6a7-121">Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-121">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="2f6a7-122">Als u al een MFA hebt ingesteld met basislijnbeleid, dan [moet u deze uitschakelen en de standaardinstellingen voor beveiliging inschakelen](#move-from-baseline-policies-to-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="2f6a7-122">If you have previously set up MFA with baseline policies, [you must turn them off and turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="2f6a7-123">Maar als u Microsoft 365 Business hebt of uw abonnement bevat [Azure Active Directory Premium 1 of Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/), dan kunt u ook beleid voor [voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) instellen.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-123">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium 1, or Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="2f6a7-124">Als u beleid voor voorwaardelijke toegang wilt gebruiken, moet u ervoor zorgen dat [moderne verificatie](#enable-modern-authentication-for-your-organization) is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-124">To use conditional access policies, you need to make sure [modern authentication](#enable-modern-authentication-for-your-organization) is enabled.</span></span>

> [!TIP]
> <span data-ttu-id="2f6a7-125">Ga naar [Microsoft Authenticator gebruiken met Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1) als u uw gebruikers wilt uitleggen hoe ze de Authenticator-app moeten instellen.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-125">To explain to your users how to set up the Authenticator app, please visit [Use Microsoft Authenticator with office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="2f6a7-126">Standaardinstellingen voor beveiliging beheren</span><span class="sxs-lookup"><span data-stu-id="2f6a7-126">Manage security defaults</span></span>

1. <span data-ttu-id="2f6a7-127">Meld u aan bij het [beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=834822) met uw globale-beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-127">Sign in to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with your Global admin credentials.</span></span>
2. <span data-ttu-id="2f6a7-128">Ga naar [Azure Active Directory-eigenschappen](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="2f6a7-128">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3. <span data-ttu-id="2f6a7-129">Kies onderaan de pagina de optie **Standaardinstellingen voor beveiliging beheren**.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-129">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="2f6a7-130">Kies **Ja** als u de standaardinstellingen voor de beveiliging wilt inschakelen en **Nee** om de beveiligingsinstellingen uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-130">Choose **Yes** to enable security defaults and **No** to disable security defaults.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="2f6a7-131">Overstappen van basislijnbeleid op standaardinstellingen voor beveiliging</span><span class="sxs-lookup"><span data-stu-id="2f6a7-131">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="2f6a7-132">Selecteer in het [Beheercentrum de ](https://go.microsoft.com/fwlink/p/?linkid=834822)optie **Setup**.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-132">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Setup**.</span></span>

2. <span data-ttu-id="2f6a7-133">Selecteer naast **Aanmelden en beveiliging** onder **Aanmelding veiliger maken** de optie **Weergeven**.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-133">Next to **Sign-in and security**, under **Make sign-in more secure**, select **View**.</span></span>

3. <span data-ttu-id="2f6a7-134">Selecteer onder **Aanmelding veiliger maken** de optie **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-134">Under **Make sign-in more secure**, select **Manage**.</span></span> 

4. <span data-ttu-id="2f6a7-135">Kies op de pagina **Voorwaardelijke toegang tot beleid** elk basislijnbeleid dat is **ingeschakeld**en stel deze in op **Uit**.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-135">On the **Conditional Access - Policies** page, choose each Baseline policy that is **On**, and set them to **Off**.</span></span>
5. <span data-ttu-id="2f6a7-136">Ga naar de pagina [Azure Active Directory-eigenschappen](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="2f6a7-136">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) page.</span></span>
6. <span data-ttu-id="2f6a7-137">Kies onder aan de pagina **De standaardinstellingen voor Beveiliging beheren**en stel in het venster **Standaardinstellingen voor beveiliging inschakelen** **standaard** in om in te schakelen op **Ja**en kies **Vervolgens Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-137">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**, and then choose **Save**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="2f6a7-138">Moderne verificatie inschakelen voor uw organisatie</span><span class="sxs-lookup"><span data-stu-id="2f6a7-138">Enable modern authentication for your organization</span></span>

<span data-ttu-id="2f6a7-139">Alle Office 2016-clienttoepassingen bieden ondersteuning voor MFA door middel van de Active Directory Authentication Library (ADAL).</span><span class="sxs-lookup"><span data-stu-id="2f6a7-139">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="2f6a7-140">Dit betekent dat app-wachtwoorden niet vereist zijn voor Office 2016-clients.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-140">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="2f6a7-141">U moet er echter voor zorgen dat uw Microsoft 365-abonnement is ingeschakeld voor ADAL of moderne verificatie.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-141">However, you need to make sure your Microsoft 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="2f6a7-142">Als u moderne verificatie wilt inschakelen, gaat u naar het [Beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=834822) en selecteert u **Instellingen** \> **Instellingen**. Vervolgens kiest u op het tabblad **Services** de optie \*\* Moderne verificatie\*\* in de lijst.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-142">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="2f6a7-143">Schakel het selectievakje **Moderne verificatie inschakelen (aanbevolen)** in het deelvenster **Moderne verificatie** in en kies **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-143">Check the **Enable modern authentication (recommended)** box in the **Modern authentication** panel, and then choose **Save changes**.</span></span> 

    ![Moderne verificatievenster met selectievakje inschakelen aangevinkt.](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> <span data-ttu-id="2f6a7-145">Vanaf augustus 2017 hebben alle nieuwe Microsoft 365-abonnementen, waaronder Skype voor Bedrijven online en Exchange online, standaard moderne verificatie ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-145">As of August of 2017, all new Microsoft 365 subscriptions that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="2f6a7-146">U kunt de status van moderne verificatie voor de webversie van Skype voor Bedrijven controleren via de webversie van Skype voor Bedrijven PowerShell met globale beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-146">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="2f6a7-147">Voer Get-CsOAuthConfiguration uit om de uitvoer van ClientADALAuthOverride te controleren.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-147">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="2f6a7-148">Als -ClientADALAuthOverride is 'toegestaan', is moderne verificatie ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-148">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="2f6a7-149">Als u uw MA-status wilt controleren voor Exchange Online, gaat u naar [Moderne verificatie inschakelen in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="2f6a7-149">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="2f6a7-150">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="2f6a7-150">Related articles</span></span>

[<span data-ttu-id="2f6a7-151">Top 10 manieren om Microsoft 365 te beveiligen voor bedrijfsabonnementen</span><span class="sxs-lookup"><span data-stu-id="2f6a7-151">Top 10 ways to secure Microsoft 365 for business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="2f6a7-152">Moderne verificatie inschakelen voor Office 2013 op Windows-apparaten</span><span class="sxs-lookup"><span data-stu-id="2f6a7-152">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
