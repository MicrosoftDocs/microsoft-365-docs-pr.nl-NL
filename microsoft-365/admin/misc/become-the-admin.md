---
title: Een interne beheerdersovername uitvoeren
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Lees hoe u uw e-mail- en domeineigenschap verifieert om een niet-beherende tenant over te nemen die is gemaakt door een selfservicegebruiker die zich in uw Microsoft 365.
ms.openlocfilehash: c37bf153edf39f53b5c10f020b0cbb8d630eb4a6
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593931"
---
# <a name="perform-an-internal-admin-takeover"></a><span data-ttu-id="993b6-103">Een interne beheerdersovername uitvoeren</span><span class="sxs-lookup"><span data-stu-id="993b6-103">Perform an internal admin takeover</span></span>

 <span data-ttu-id="993b6-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="993b6-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="993b6-105">Als u een beheerder bent en een niet-beheerde tenant wilt overnemen die is gemaakt door een selfservicegebruiker, kunt u dit doen met een interne beheerdersovername.</span><span class="sxs-lookup"><span data-stu-id="993b6-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="993b6-106">Een selfservice-aanmelding voor een cloudservice die Azure AD gebruikt, voegt de gebruiker toe aan een niet-beheerde of 'schaduw' Azure AD-adreslijst en maakt een niet-beheerde tenant.</span><span class="sxs-lookup"><span data-stu-id="993b6-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="993b6-107">Een niet-beheerde tenant is een adreslijst zonder globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="993b6-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="993b6-108">Zie Tenanttype bepalen om te bepalen of een tenant wordt beheerd of niet wordt [beheerd.](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)</span><span class="sxs-lookup"><span data-stu-id="993b6-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="993b6-109">Stap 1: Uw e-mailadres verifiëren</span><span class="sxs-lookup"><span data-stu-id="993b6-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="993b6-110">Als selfservice is ingeschakeld in uw tenant, kunnen gebruikers zich zelf abonneren op gratis services, Power BI services.</span><span class="sxs-lookup"><span data-stu-id="993b6-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="993b6-111">In deze stappen wordt ervan uitgenomen dat een selfservicegebruikerabonnement de niet-beheerde tenant heeft gemaakt die u als beheerder wilt overnemen. In de eerste stap maakt u een gebruikerscontext in de niet-beheerde tenant, met behulp van Power BI om het overnamepad van de beheerder te illustreren.</span><span class="sxs-lookup"><span data-stu-id="993b6-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="993b6-112">Als u zich wilt registreren Power BI, gaat u naar de Power BI [site](https://powerbi.com) en **selecteert** u Gratis proefabonnement starten (in Delen  >   met Power BI Pro vak).</span><span class="sxs-lookup"><span data-stu-id="993b6-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="993b6-113">Meld u aan met een gebruikersaccount dat de domeinnaam van uw organisatie gebruikt (zoals `powerbiadmin@contoso.com` ).</span><span class="sxs-lookup"><span data-stu-id="993b6-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="993b6-114">Als uw account al in gebruik is, meld u dan aan met uw huidige wachtwoord.</span><span class="sxs-lookup"><span data-stu-id="993b6-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="993b6-115">Controleer uw e-mail op **de verificatiecode** en voer de code in om uw e-mailadres te valideren.</span><span class="sxs-lookup"><span data-stu-id="993b6-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="993b6-116">Stap 2: Een nieuw account maken</span><span class="sxs-lookup"><span data-stu-id="993b6-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="993b6-117">Wanneer u de verificatiecode in typt, wordt u naar een pagina gebracht waar u een nieuw account kunt maken.</span><span class="sxs-lookup"><span data-stu-id="993b6-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="993b6-118">Vul de velden gebruikersnaam en wachtwoord in met het account dat u wilt gebruiken en selecteer **Vervolgens Start.**</span><span class="sxs-lookup"><span data-stu-id="993b6-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="993b6-119">Stap 3: Domeineigenschap verifiëren en beheerder worden</span><span class="sxs-lookup"><span data-stu-id="993b6-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="993b6-120">De **wizard Word de beheerder** wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="993b6-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="993b6-121">Als de wizard niet wordt start, gaat u naar de tegel **Beheerder** en selecteert u deze.</span><span class="sxs-lookup"><span data-stu-id="993b6-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="993b6-122">Selecteer **Ja, ik wil de beheerder zijn.**</span><span class="sxs-lookup"><span data-stu-id="993b6-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="993b6-123">Controleer of u de eigenaar bent van het domein dat u wilt overnemen door een TXT-record toe te voegen aan uw domeinregistrar.</span><span class="sxs-lookup"><span data-stu-id="993b6-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="993b6-124">De wizard geeft u de TXT-record die u wilt toevoegen, evenals een koppeling naar de website van uw registrar en een koppeling naar stapsgewijs instructies.</span><span class="sxs-lookup"><span data-stu-id="993b6-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="993b6-125">Nadat u de TXT-record hebt toegevoegd aan uw registrarsite, gaat u terug naar de wizard en selecteert u **Ok, ik heb de record toegevoegd.**</span><span class="sxs-lookup"><span data-stu-id="993b6-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="993b6-126">Het overnemen van de schaduw tenant heeft geen invloed op bestaande informatie of services.</span><span class="sxs-lookup"><span data-stu-id="993b6-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="993b6-127">Als gebruikers in het domein zich echter hebben aangemeld voor services waarvoor een licentie is vereist, wordt u gevraagd om licenties voor hen te kopen als onderdeel van het overnemen van de beheerdersrol.</span><span class="sxs-lookup"><span data-stu-id="993b6-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="993b6-128">U kunt licenties kopen of verwijderen zodra het installatieproces voor beheerders is voltooid.</span><span class="sxs-lookup"><span data-stu-id="993b6-128">You can buy or remove licenses once the admin setup process is finished.</span></span>
  
## <a name="related-content"></a><span data-ttu-id="993b6-129">Verwante inhoud</span><span class="sxs-lookup"><span data-stu-id="993b6-129">Related content</span></span>

<span data-ttu-id="993b6-130">YouTube: [3 stappen voor het overnemen](https://www.youtube.com/watch?v=xt5EsrQBZZk) van IT-beheerders voor Power BI en Microsoft 365 (video)</span><span class="sxs-lookup"><span data-stu-id="993b6-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk) (video)</span></span>

<span data-ttu-id="993b6-131">[Overname van beheerders in Azure AD](/azure/active-directory/users-groups-roles/domains-admin-takeover) (artikel)</span><span class="sxs-lookup"><span data-stu-id="993b6-131">[Admin takeover in Azure AD](/azure/active-directory/users-groups-roles/domains-admin-takeover) (article)</span></span>

<span data-ttu-id="993b6-132">[Selfservice-aanmelding gebruiken in uw organisatie](self-service-sign-up.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="993b6-132">[Using self-service sign up in your organization](self-service-sign-up.md) (article)</span></span>
  
<span data-ttu-id="993b6-133">[De rol Power BI servicebeheerder](/power-bi/service-admin-role) (artikel)</span><span class="sxs-lookup"><span data-stu-id="993b6-133">[Understanding the Power BI service administrator role](/power-bi/service-admin-role) (article)</span></span>