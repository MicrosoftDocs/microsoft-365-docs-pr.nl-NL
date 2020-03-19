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
ms.openlocfilehash: 4dc52c25c3a9351be1a9f4d094d664bc4ed527f9
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42805580"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="9a4a3-103">Meervoudige verificatie instellen</span><span class="sxs-lookup"><span data-stu-id="9a4a3-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="9a4a3-104">De standaardinstellingen voor beveiliging zijn automatisch ingeschakeld in elk nieuw abonnement op Office 365 voor bedrijven of Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-104">Every new Office 365 for business or Microsoft 365 Business subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="9a4a3-105">Dit betekent dat alle gebruikers meervoudige verificatie (MFA) moeten instellen en de verificatie-app op hun mobiele apparaat moeten installeren.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-105">This means that every user will have to set up multi-factor authentication (MFA) and install the Authenticator app on their mobile device.</span></span> <span data-ttu-id="9a4a3-106">Zie [Verificatie in twee stappen instellen voor Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-106">For more information, see [Set up 2-step verification for Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>  

<span data-ttu-id="9a4a3-107">De volgende negen beheerdersrollen moeten aanvullende verificatie uitvoeren wanneer ze zich aanmelden:</span><span class="sxs-lookup"><span data-stu-id="9a4a3-107">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>
- <span data-ttu-id="9a4a3-108">Globale beheerder</span><span class="sxs-lookup"><span data-stu-id="9a4a3-108">Global administrator</span></span>
- <span data-ttu-id="9a4a3-109">SharePoint-beheerder</span><span class="sxs-lookup"><span data-stu-id="9a4a3-109">SharePoint administrator</span></span>
- <span data-ttu-id="9a4a3-110">Exchange-beheerder</span><span class="sxs-lookup"><span data-stu-id="9a4a3-110">Exchange administrator</span></span>
- <span data-ttu-id="9a4a3-111">Beheerder van voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="9a4a3-111">Conditional Access administrator</span></span>
- <span data-ttu-id="9a4a3-112">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="9a4a3-112">Security administrator</span></span>
- <span data-ttu-id="9a4a3-113">Helpdesk- of wachtwoordbeheerder</span><span class="sxs-lookup"><span data-stu-id="9a4a3-113">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="9a4a3-114">Factureringsbeheerder</span><span class="sxs-lookup"><span data-stu-id="9a4a3-114">Billing administrator</span></span>
- <span data-ttu-id="9a4a3-115">Gebruikersbeheerder</span><span class="sxs-lookup"><span data-stu-id="9a4a3-115">User administrator</span></span>
- <span data-ttu-id="9a4a3-116">Verificatiebeheerder</span><span class="sxs-lookup"><span data-stu-id="9a4a3-116">Authentication administrator</span></span>

<span data-ttu-id="9a4a3-117">Alle andere gebruikers wordt gevraagd om indien nodig extra verificatie uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-117">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="9a4a3-118">Zie [Wat zijn standaardinstellingen voor beveiliging?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="9a4a3-118">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

> [!NOTE]
> <span data-ttu-id="9a4a3-p103">U moet een globale beheerder van Office 365 zijn om meervoudige verificatie in te stellen of te wijzigen. </span><span class="sxs-lookup"><span data-stu-id="9a4a3-p103">You must be an Office 365 global admin to set up or modify multi-factor authentication. </span></span><br><br>
> <span data-ttu-id="9a4a3-120">Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-120">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="9a4a3-121">Als u al een MFA hebt ingesteld met basislijnbeleid, dan [moet u deze uitschakelen en de standaardinstellingen voor beveiliging inschakelen](#move-from-baseline-policies-to-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="9a4a3-121">If you have previously set up MFA with baseline policies, [you must turn them off and turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="9a4a3-122">Maar als u Microsoft 365 Business hebt of uw abonnement bevat [Azure Active Directory Premium 1 of Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/), dan kunt u ook beleid voor [voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) instellen.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-122">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium 1, or Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="9a4a3-123">Als u beleid voor voorwaardelijke toegang wilt gebruiken, moet u controleren of [moderne verificatie is ingeschakeld](#enable-multi-factor-authentication-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="9a4a3-123">To use conditional access policies, you need to make sure [modern authentication is enabled](#enable-multi-factor-authentication-for-your-organization).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="9a4a3-124">Standaardinstellingen voor beveiliging beheren</span><span class="sxs-lookup"><span data-stu-id="9a4a3-124">Manage security defaults</span></span>

1. <span data-ttu-id="9a4a3-125">Meld u aan bij het [beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=834822) met uw referenties als globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-125">Sign in to [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with your Global admin credentials.</span></span>
2. <span data-ttu-id="9a4a3-126">Ga naar [Azure Active Directory-eigenschappen](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="9a4a3-126">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>

3. <span data-ttu-id="9a4a3-127">Kies onderaan de pagina de optie **Standaardinstellingen voor beveiliging beheren**.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-127">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="9a4a3-128">Kies **Ja** als u de standaardinstellingen voor de beveiliging wilt inschakelen en **Nee** om de beveiligingsinstellingen uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-128">Choose **Yes** to enable security defaults and **No** to disable security defaults.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="9a4a3-129">Overstappen van basislijnbeleid op standaardinstellingen voor beveiliging</span><span class="sxs-lookup"><span data-stu-id="9a4a3-129">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="9a4a3-130">Selecteer in het [Beheercentrum de ](https://go.microsoft.com/fwlink/p/?linkid=834822)optie **Setup**.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-130">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Setup**.</span></span>

2. <span data-ttu-id="9a4a3-131">Selecteer naast **Aanmelden en beveiliging** onder **Aanmelding veiliger maken** de optie **Weergeven**.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-131">Next to **Sign-in and security**, under **Make sign-in more secure**, select **View**.</span></span>

3. <span data-ttu-id="9a4a3-132">Selecteer onder **Aanmelding veiliger maken** de optie **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-132">Under **Make sign-in more secure**, select **Manage**.</span></span> 

4. <span data-ttu-id="9a4a3-133">Ga naar de pagina **Beleid voor voorwaardelijke toegang voor Azure-portal** en selecteer elk basislijnbeleid dat is ingesteld op **Aan**. Stel deze vervolgens in op **Uit**.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-133">On the **Azure portal Conditional Access - Policies** page,  choose each Baseline policy that is **On**, and set them to **Off**.</span></span>
5. <span data-ttu-id="9a4a3-134">Ga naar de pagina [Azure Active Directory-eigenschappen](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="9a4a3-134">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) page.</span></span>
6. <span data-ttu-id="9a4a3-135">Kies onderaan de pagina de optie **Standaardwaarden voor beveiliging beheren** en stel de wisselknop **Standaardwaarden voor beveiliging inschakelen** in het deelvenster **Standaardwaarden voor beveiliging inschakelen** in op **Ja**.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-135">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="9a4a3-136">Moderne verificatie inschakelen voor uw organisatie</span><span class="sxs-lookup"><span data-stu-id="9a4a3-136">Enable Modern authentication for your organization</span></span>

<span data-ttu-id="9a4a3-137">Alle Office 2016-clienttoepassingen bieden ondersteuning voor MFA door middel van de Active Directory Authentication Library (ADAL).</span><span class="sxs-lookup"><span data-stu-id="9a4a3-137">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="9a4a3-138">Dit betekent dat app-wachtwoorden niet vereist zijn voor Office 2016-clients.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-138">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="9a4a3-139">U moet er echter voor zorgen dat uw Office 365-abonnement is ingeschakeld voor ADAL of voor moderne verificatie.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-139">However, you need to make sure your Office 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="9a4a3-140">Als u moderne verificatie wilt inschakelen, gaat u naar het [Beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=834822) en selecteert u **Instellingen** \> **Instellingen**. Vervolgens kiest u op het tabblad **Services** de optie \*\* Moderne verificatie\*\* in de lijst.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-140">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="9a4a3-141">Vink het selectievakje **Moderne verificatie inschakelen** in het deelvenster **Moderne verificatie** aan.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-141">Check the **Enable modern authentication** box in the **Modern authentication** panel.</span></span> 

    ![Moderne verificatievenster met selectievakje inschakelen aangevinkt.](../../media/enablemodernauth.png)
    
## <a name="enable-multi-factor-authentication-for-your-organization"></a><span data-ttu-id="9a4a3-143">Meervoudige verificatie inschakelen voor uw organisatie</span><span class="sxs-lookup"><span data-stu-id="9a4a3-143">Enable multi-factor authentication for your organization</span></span>
    
1. <span data-ttu-id="9a4a3-144">Selecteer in het [beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=834822) **Gebruikers** en **actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-144">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Users** and **Active Users**.</span></span>

2. <span data-ttu-id="9a4a3-145">Klik in de sectie **Actieve gebruikers** op **meervoudige verificatie**.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-145">In the **Active Users** section, Click on  **multi-factor authentication**.</span></span>

3. <span data-ttu-id="9a4a3-146">Selecteer op de pagina **Meervoudige verificatie** **de gebruiker** als u dit voor één gebruiker inschakelt of **selecteert Bulkupdate** om meerdere gebruikers in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-146">On the **Multi-factor authentication** page, select **user** if you are enabling this for one user or select **Bulk Update** to enable multiple users.</span></span>

4. <span data-ttu-id="9a4a3-147">CLick **ingeschakeld** onder **Snelle stappen**.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-147">CLick on **Enable** under **Quick Steps**.</span></span>

5. <span data-ttu-id="9a4a3-148">Klik in het pop-upvenster op **Multifactorverificatie inschakelen**.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-148">In the Pop-up window, Click on **Enable Multi-Factor Authentication**.</span></span>

<span data-ttu-id="9a4a3-149">Nadat u meervoudige verificatie voor uw organisatie hebt ingesteld, moeten uw gebruikers tweestapsverificatie op hun apparaten instellen.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-149">After you set up multi-factor authentication for your organization, your users will be required to set up two-step verification on their devices.</span></span> <span data-ttu-id="9a4a3-150">Zie [Verificatie in twee stappen instellen voor Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-150">For more information, see [Set up 2-step verification for Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>
    
> [!TIP]
> <span data-ttu-id="9a4a3-151">Ga naar [Microsoft Authenticator gebruiken met Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1) als u uw gebruikers wilt uitleggen hoe ze de Authenticator-app moeten instellen.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-151">To explain to your users how to set up the Authenticator app, please visit [Use Microsoft Authenticator with office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="9a4a3-152">Moderne verificatie is vanaf augustus 2017 standaard ingeschakeld voor alle nieuwe Office 365-tenants met de webversie van Skype voor Bedrijven en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-152">As of August of 2017, all new Office 365 tenants that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="9a4a3-153">U kunt de status van moderne verificatie voor de webversie van Skype voor Bedrijven controleren via de webversie van Skype voor Bedrijven PowerShell met globale beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-153">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="9a4a3-154">Voer Get-CsOAuthConfiguration uit om de uitvoer van ClientADALAuthOverride te controleren.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-154">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="9a4a3-155">Als -ClientADALAuthOverride is 'toegestaan', is moderne verificatie ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-155">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="9a4a3-156">Als u uw MA-status wilt controleren voor Exchange Online, gaat u naar [Moderne verificatie inschakelen in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="9a4a3-156">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="9a4a3-157">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="9a4a3-157">Related articles</span></span>

[<span data-ttu-id="9a4a3-158">De 10 beste manieren om Office 365- en Microsoft 365 Business-abonnementen te beveiligen</span><span class="sxs-lookup"><span data-stu-id="9a4a3-158">Top 10 ways to secure Office 365 and Microsoft 365 Business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="9a4a3-159">Moderne verificatie inschakelen voor Office 2013 op Windows-apparaten</span><span class="sxs-lookup"><span data-stu-id="9a4a3-159">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
