---
title: Een interne beheerovername uitvoeren in Office 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Meer informatie over het verifiëren van uw e-mail- en domeineigendom om een niet-beheerde tenant in Office 365 over te nemen
ms.openlocfilehash: 3c732d55c533c72983aaa59e39e7bb8ff130f280
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212243"
---
# <a name="perform-an-internal-admin-takeover-in-office-365"></a><span data-ttu-id="9bc5a-103">Een interne beheerovername uitvoeren in Office 365</span><span class="sxs-lookup"><span data-stu-id="9bc5a-103">Perform an internal admin takeover in Office 365</span></span>

 <span data-ttu-id="9bc5a-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="9bc5a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="9bc5a-105">Als u een beheerder bent en een onbeheerde tenant wilt overnemen die is gemaakt door een selfservicegebruiker, u dit doen met een interne beheerovername.</span><span class="sxs-lookup"><span data-stu-id="9bc5a-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="9bc5a-106">Als u zich aanmeldt voor een zelfservice voor elke cloudservice die Azure AD gebruikt, wordt de gebruiker toegevoegd aan een niet-beheerde of 'schaduw' Azure AD-map en wordt een onbeheerde tenant gemaakt.</span><span class="sxs-lookup"><span data-stu-id="9bc5a-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="9bc5a-107">Een niet-beheerde tenant is een directory zonder globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="9bc5a-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="9bc5a-108">Zie [Tenanttype bepalen](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)om te bepalen of een tenant wordt beheerd of niet wordt beheerd.</span><span class="sxs-lookup"><span data-stu-id="9bc5a-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="9bc5a-109">Stap 1: Uw e-mailadres verifiëren</span><span class="sxs-lookup"><span data-stu-id="9bc5a-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="9bc5a-110">Als selfservice is ingeschakeld in uw tenant, kunnen gebruikers zich alleen abonneren op gratis services, zoals Power BI.</span><span class="sxs-lookup"><span data-stu-id="9bc5a-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="9bc5a-111">Deze stappen gaan ervan uit dat een selfservice-gebruikersabonnement de onbeheerde tenant heeft gemaakt die u als beheerder wilt overnemen. In de eerste stap maakt u een gebruikerscontext in de onbeheerde tenant, waarbij u Power BI gebruikt om het overnamepad voor beheerders te illustreren.</span><span class="sxs-lookup"><span data-stu-id="9bc5a-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="9bc5a-112">Als u zich wilt aanmelden voor Power BI, gaat u naar de [Power BI-site](https://powerbi.com) en selecteert **u Gratis** > **start starten** (in het vak Delen met Power BI Pro).</span><span class="sxs-lookup"><span data-stu-id="9bc5a-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="9bc5a-113">Meld u aan met een gebruikersaccount dat de `powerbiadmin@contoso.com`domeinnaam van uw organisatie gebruikt (zoals).</span><span class="sxs-lookup"><span data-stu-id="9bc5a-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="9bc5a-114">Als uw account al in gebruik is, meldt u zich aan met uw huidige wachtwoord.</span><span class="sxs-lookup"><span data-stu-id="9bc5a-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="9bc5a-115">Controleer uw e-mail op de **verificatiecode** en voer de code in om uw e-mailadres te valideren.</span><span class="sxs-lookup"><span data-stu-id="9bc5a-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="9bc5a-116">Stap 2: Een nieuw account maken</span><span class="sxs-lookup"><span data-stu-id="9bc5a-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="9bc5a-117">Wanneer u de verificatiecode invoert, wordt u naar een pagina gebracht waar u een nieuw account maken.</span><span class="sxs-lookup"><span data-stu-id="9bc5a-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="9bc5a-118">Vul de gebruikersnaam en wachtwoordvelden in met het account dat u wilt gebruiken en selecteer **Start**.</span><span class="sxs-lookup"><span data-stu-id="9bc5a-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="9bc5a-119">Stap 3: Domeineigendom verifiëren en beheerder worden</span><span class="sxs-lookup"><span data-stu-id="9bc5a-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="9bc5a-120">De wizard **Word de beheerder** wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="9bc5a-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="9bc5a-121">Als de wizard niet wordt gestart, zoekt u de tegel **Beheerder** en selecteert u deze.</span><span class="sxs-lookup"><span data-stu-id="9bc5a-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="9bc5a-122">Selecteer **Ja, ik wil de beheerder zijn.**</span><span class="sxs-lookup"><span data-stu-id="9bc5a-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="9bc5a-123">Controleer of u eigenaar bent van het domein dat u wilt overnemen door een TXT-record toe te voegen aan uw domeinregistrar.</span><span class="sxs-lookup"><span data-stu-id="9bc5a-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="9bc5a-124">De wizard geeft u de TXT-record toe te voegen, evenals een link naar de website van uw registrar, en een link naar stapsgewijze instructies.</span><span class="sxs-lookup"><span data-stu-id="9bc5a-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="9bc5a-125">Zodra u de TXT-record aan uw registrarsite hebt toegevoegd, gaat u terug naar de wizard en selecteert **u Oké, ik heb de record toegevoegd.**</span><span class="sxs-lookup"><span data-stu-id="9bc5a-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9bc5a-126">De overname van de schaduwtenant heeft geen invloed op bestaande informatie of services.</span><span class="sxs-lookup"><span data-stu-id="9bc5a-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="9bc5a-127">Als gebruikers in het domein zich echter hebben aangemeld voor services waarvoor een licentie vereist is, wordt u gevraagd licenties voor hen te kopen als onderdeel van de overname van de beheerdersrol.</span><span class="sxs-lookup"><span data-stu-id="9bc5a-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="9bc5a-128">U licenties toevoegen of verwijderen zodra het beheerproces is voltooid.</span><span class="sxs-lookup"><span data-stu-id="9bc5a-128">You can add or remove licenses once the admin setup process is finished.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="9bc5a-129">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="9bc5a-129">Related articles</span></span>

<span data-ttu-id="9bc5a-130">YouTube: [Drie te volgen stappen om een overname als IT-beheerder voor Power BI en Office 365 uit te voeren](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span><span class="sxs-lookup"><span data-stu-id="9bc5a-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Office 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span></span>

[<span data-ttu-id="9bc5a-131">Overname van beheerders in Azure AD</span><span class="sxs-lookup"><span data-stu-id="9bc5a-131">Admin takeover in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[<span data-ttu-id="9bc5a-132">Hulp krijgen bij Office 365-domeinen</span><span class="sxs-lookup"><span data-stu-id="9bc5a-132">Get help with Office 365 domains</span></span>](../get-help-with-domains/get-help-with-domains.md)

[<span data-ttu-id="9bc5a-133">Zelfserviceaanmelden in uw organisatie gebruiken</span><span class="sxs-lookup"><span data-stu-id="9bc5a-133">Using self-service sign up in your organization</span></span>](self-service-sign-up.md)
  
[<span data-ttu-id="9bc5a-134">De functie Power BI-servicebeheerder begrijpen</span><span class="sxs-lookup"><span data-stu-id="9bc5a-134">Understanding the Power BI service administrator role</span></span>](https://docs.microsoft.com/power-bi/service-admin-role)

