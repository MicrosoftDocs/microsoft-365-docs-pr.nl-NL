---
title: Meervoudige verificatie voor Office 365-gebruikers instellen
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
description: Leer hoe u met de standaardinstellingen voor beveiliging meervoudige verificatie kunt instellen voor Office 365-gebruikers.
monikerRange: o365-worldwide
ms.openlocfilehash: 7e48f72f2fd8cfc5042bd15f994cc98bfa5fca8c
ms.sourcegitcommit: dbbdeca5a6cd048e1bde9e820a8b8a0d6022c7a2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2020
ms.locfileid: "43503969"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="0e875-103">Meervoudige verificatie instellen</span><span class="sxs-lookup"><span data-stu-id="0e875-103">Set up multi-factor authentication</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0e875-104">Als u uw abonnement of proefversie na 21 oktober 2019 hebt gekocht en u onverwacht wordt gevraagd om multi-factor authenticatie (MFA), zijn [beveiligingsstandaards](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) automatisch ingeschakeld voor uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="0e875-104">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for multi-factor authentication (MFA), [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

<span data-ttu-id="0e875-105">De standaardinstellingen voor beveiliging zijn automatisch ingeschakeld in elk nieuw abonnement op Office 365 voor bedrijven of Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="0e875-105">Every new Office 365 for business or Microsoft 365 Business subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="0e875-106">Dit betekent dat elke gebruiker MFA moet instellen en de Microsoft Authenticator-app op zijn mobiele apparaat moet installeren.</span><span class="sxs-lookup"><span data-stu-id="0e875-106">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span> <span data-ttu-id="0e875-107">Zie [Verificatie in twee stappen instellen voor Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0e875-107">For more information, see [Set up 2-step verification for Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>  

<span data-ttu-id="0e875-108">De volgende negen beheerdersrollen moeten aanvullende verificatie uitvoeren wanneer ze zich aanmelden:</span><span class="sxs-lookup"><span data-stu-id="0e875-108">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>

- <span data-ttu-id="0e875-109">Globale beheerder</span><span class="sxs-lookup"><span data-stu-id="0e875-109">Global administrator</span></span>
- <span data-ttu-id="0e875-110">SharePoint-beheerder</span><span class="sxs-lookup"><span data-stu-id="0e875-110">SharePoint administrator</span></span>
- <span data-ttu-id="0e875-111">Exchange-beheerder</span><span class="sxs-lookup"><span data-stu-id="0e875-111">Exchange administrator</span></span>
- <span data-ttu-id="0e875-112">Beheerder van voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="0e875-112">Conditional Access administrator</span></span>
- <span data-ttu-id="0e875-113">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="0e875-113">Security administrator</span></span>
- <span data-ttu-id="0e875-114">Helpdesk- of wachtwoordbeheerder</span><span class="sxs-lookup"><span data-stu-id="0e875-114">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="0e875-115">Factureringsbeheerder</span><span class="sxs-lookup"><span data-stu-id="0e875-115">Billing administrator</span></span>
- <span data-ttu-id="0e875-116">Gebruikersbeheerder</span><span class="sxs-lookup"><span data-stu-id="0e875-116">User administrator</span></span>
- <span data-ttu-id="0e875-117">Verificatiebeheerder</span><span class="sxs-lookup"><span data-stu-id="0e875-117">Authentication administrator</span></span>

<span data-ttu-id="0e875-118">Alle andere gebruikers wordt gevraagd om indien nodig extra verificatie uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="0e875-118">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="0e875-119">Zie [Wat zijn beveiligingsstandaardinstellingen voor](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)meer informatie?</span><span class="sxs-lookup"><span data-stu-id="0e875-119">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

> [!NOTE]
> <span data-ttu-id="0e875-120">U moet een globale office 365-beheerder zijn om MFA in te stellen of te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="0e875-120">You must be an Office 365 global admin to set up or modify MFA.</span></span> <br><br>
> <span data-ttu-id="0e875-121">Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.</span><span class="sxs-lookup"><span data-stu-id="0e875-121">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="0e875-122">Als u al een MFA hebt ingesteld met basislijnbeleid, dan [moet u deze uitschakelen en de standaardinstellingen voor beveiliging inschakelen](#move-from-baseline-policies-to-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="0e875-122">If you have previously set up MFA with baseline policies, [you must turn them off and turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="0e875-123">Als u echter Microsoft 365 Business hebt of als uw abonnement [Azure Active Directory Premium P1 of Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/)bevat, u ook beleid voor voorwaardelijke [toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) instellen.</span><span class="sxs-lookup"><span data-stu-id="0e875-123">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium P1 or Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="0e875-124">Als u beleid voor voorwaardelijke toegang wilt gebruiken, moet u ervoor zorgen dat [moderne verificatie](#enable-modern-authentication-for-your-organization) is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="0e875-124">To use conditional access policies, you need to make sure [modern authentication](#enable-modern-authentication-for-your-organization) is enabled.</span></span>

> [!TIP]
> <span data-ttu-id="0e875-125">Ga naar [Microsoft Authenticator gebruiken met Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1) als u uw gebruikers wilt uitleggen hoe ze de Authenticator-app moeten instellen.</span><span class="sxs-lookup"><span data-stu-id="0e875-125">To explain to your users how to set up the Authenticator app, please visit [Use Microsoft Authenticator with office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="0e875-126">Standaardinstellingen voor beveiliging beheren</span><span class="sxs-lookup"><span data-stu-id="0e875-126">Manage security defaults</span></span>

1. <span data-ttu-id="0e875-127">Meld u aan bij het [beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=834822) met uw globale-beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="0e875-127">Sign in to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with your Global admin credentials.</span></span>
2. <span data-ttu-id="0e875-128">Ga naar [Azure Active Directory-eigenschappen](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="0e875-128">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3. <span data-ttu-id="0e875-129">Kies onderaan de pagina de optie **Standaardinstellingen voor beveiliging beheren**.</span><span class="sxs-lookup"><span data-stu-id="0e875-129">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="0e875-130">Kies **Ja** om beveiligingsstandaards in te schakelen of **Nee** om beveiligingsstandaards uit te schakelen en kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0e875-130">Choose **Yes** to enable security defaults or **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="0e875-131">Overstappen van basislijnbeleid op standaardinstellingen voor beveiliging</span><span class="sxs-lookup"><span data-stu-id="0e875-131">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="0e875-132">Selecteer in het [beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=834822) **Alles weergeven**en vervolgens **Azure Active Directory** onder **Beheercentra**.</span><span class="sxs-lookup"><span data-stu-id="0e875-132">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Show all**, and then **Azure Active Directory** under **Admin centers**.</span></span>

2. <span data-ttu-id="0e875-133">Kies azure **Active Directory** > **Security**in het Azure **Active Directory-beheercentrum** .</span><span class="sxs-lookup"><span data-stu-id="0e875-133">In the  **Azure Active Directory admin center** choose **Azure Active Directory** > **Security**.</span></span>

3. <span data-ttu-id="0e875-134">Wat de **zekerheid heeft : Aan de slag** pagina, kies **Voorwaardelijke toegang**.</span><span class="sxs-lookup"><span data-stu-id="0e875-134">On the **Security | Getting started** page, choose **Conditional Access**.</span></span> 

4. <span data-ttu-id="0e875-135">Kies op de pagina **Voorwaardelijke toegang tot beleid** elk basislijnbeleid dat is **ingeschakeld**en stel deze in op **Uit**.</span><span class="sxs-lookup"><span data-stu-id="0e875-135">On the **Conditional Access - Policies** page, choose each Baseline policy that is **On**, and set them to **Off**.</span></span>
5. <span data-ttu-id="0e875-136">Ga naar de pagina [Azure Active Directory-eigenschappen](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="0e875-136">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) page.</span></span>
6. <span data-ttu-id="0e875-137">Kies onder aan de pagina **De standaardinstellingen voor Beveiliging beheren**en stel in het venster **Standaardinstellingen voor beveiliging inschakelen** **standaard** in om in te schakelen op **Ja**en kies **Vervolgens Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0e875-137">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**, and then choose **Save**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="0e875-138">Moderne verificatie inschakelen voor uw organisatie</span><span class="sxs-lookup"><span data-stu-id="0e875-138">Enable modern authentication for your organization</span></span>

<span data-ttu-id="0e875-139">Alle Office 2016-clienttoepassingen bieden ondersteuning voor MFA door middel van de Active Directory Authentication Library (ADAL).</span><span class="sxs-lookup"><span data-stu-id="0e875-139">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="0e875-140">Dit betekent dat app-wachtwoorden niet vereist zijn voor Office 2016-clients.</span><span class="sxs-lookup"><span data-stu-id="0e875-140">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="0e875-141">U moet er echter voor zorgen dat uw Office 365-abonnement is ingeschakeld voor ADAL of voor moderne verificatie.</span><span class="sxs-lookup"><span data-stu-id="0e875-141">However, you need to make sure your Office 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="0e875-142">Als u moderne verificatie wilt inschakelen, gaat u naar het [Beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=834822) en selecteert u **Instellingen** \> **Instellingen**. Vervolgens kiest u op het tabblad **Services** de optie \*\* Moderne verificatie\*\* in de lijst.</span><span class="sxs-lookup"><span data-stu-id="0e875-142">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="0e875-143">Schakel het selectievakje **Moderne verificatie inschakelen (aanbevolen)** in het deelvenster **Moderne verificatie** in en kies **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0e875-143">Check the **Enable modern authentication (recommended)** box in the **Modern authentication** panel, and then choose **Save changes**.</span></span> 

    ![Moderne verificatievenster met selectievakje inschakelen aangevinkt.](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> <span data-ttu-id="0e875-145">Moderne verificatie is vanaf augustus 2017 standaard ingeschakeld voor alle nieuwe Office 365-tenants met de webversie van Skype voor Bedrijven en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0e875-145">As of August of 2017, all new Office 365 tenants that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="0e875-146">U kunt de status van moderne verificatie voor de webversie van Skype voor Bedrijven controleren via de webversie van Skype voor Bedrijven PowerShell met globale beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="0e875-146">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="0e875-147">Voer Get-CsOAuthConfiguration uit om de uitvoer van ClientADALAuthOverride te controleren.</span><span class="sxs-lookup"><span data-stu-id="0e875-147">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="0e875-148">Als -ClientADALAuthOverride is 'toegestaan', is moderne verificatie ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="0e875-148">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>

<span data-ttu-id="0e875-149">Als u uw MA-status wilt controleren voor Exchange Online, gaat u naar [Moderne verificatie inschakelen in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="0e875-149">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="0e875-150">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="0e875-150">Related articles</span></span>

[<span data-ttu-id="0e875-151">De 10 beste manieren om Office 365- en Microsoft 365 Business-abonnementen te beveiligen</span><span class="sxs-lookup"><span data-stu-id="0e875-151">Top 10 ways to secure Office 365 and Microsoft 365 Business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="0e875-152">Moderne verificatie inschakelen voor Office 2013 op Windows-apparaten</span><span class="sxs-lookup"><span data-stu-id="0e875-152">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
