---
title: Een interne beheerder overnemen
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
description: Meer informatie over hoe u uw e-mailadres en domein eigendom controleert voor het overnemen van een niet-beheerde Tenant in Microsoft 365
ms.openlocfilehash: 9ae09a4b88887664a0615128bcddc48ad6f57118
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645057"
---
# <a name="perform-an-internal-admin-takeover"></a><span data-ttu-id="f1889-103">Een interne beheerder overnemen</span><span class="sxs-lookup"><span data-stu-id="f1889-103">Perform an internal admin takeover</span></span>

 <span data-ttu-id="f1889-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="f1889-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="f1889-105">Als u een beheerder bent en een niet-beheerde Tenant die is gemaakt door een selfservicegebruiker, wilt overnemen, kunt u dit doen met een interne beheerder van de beheerder.</span><span class="sxs-lookup"><span data-stu-id="f1889-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="f1889-106">Een selfservice registratie voor een cloudservice waarin Azure AD wordt gebruikt, voegt de gebruiker toe aan een niet-beheerde of ' schaduw ' Azure AD-Directory en maak een niet-beheerde Tenant.</span><span class="sxs-lookup"><span data-stu-id="f1889-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="f1889-107">Een niet-beheerde Tenant is een adreslijst zonder globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="f1889-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="f1889-108">Als u wilt weten of een Tenant wordt beheerd of niet beheerd, raadpleegt u [Tenant type bepalen](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span><span class="sxs-lookup"><span data-stu-id="f1889-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="f1889-109">Stap 1: uw e-mailadres verifiëren</span><span class="sxs-lookup"><span data-stu-id="f1889-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="f1889-110">Als selfservice in de Tenant is ingeschakeld, kunnen gebruikers zich zelf abonneren op gratis services, zoals Power BI.</span><span class="sxs-lookup"><span data-stu-id="f1889-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="f1889-111">Bij deze stappen wordt ervan uitgegaan dat een selfservicegebruikers abonnement de niet-beheerde Tenant heeft gemaakt die u wilt overnemen van de beheerder. Wanneer u in de eerste stap een gebruikerscontext maakt in de niet-beheerde Tenant, maakt u gebruik van Power BI om het pad van de beheerder te illustreren.</span><span class="sxs-lookup"><span data-stu-id="f1889-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="f1889-112">Als u zich wilt registreren voor Power bi, gaat u naar de [Power bi-site](https://powerbi.com) en selecteert u **gratis**  >  **proefversie** starten (in delen met Power bi Pro box).</span><span class="sxs-lookup"><span data-stu-id="f1889-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="f1889-113">Meld u aan met een gebruikersaccount dat gebruikmaakt van de domeinnaam van uw organisatie (zoals `powerbiadmin@contoso.com` ).</span><span class="sxs-lookup"><span data-stu-id="f1889-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="f1889-114">Als uw account al wordt gebruikt, meldt u zich aan met uw huidige wachtwoord.</span><span class="sxs-lookup"><span data-stu-id="f1889-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="f1889-115">Controleer uw e-mailadres op de **verificatiecode** en voer de code in om uw e-mailadres te valideren.</span><span class="sxs-lookup"><span data-stu-id="f1889-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="f1889-116">Stap 2: een nieuw account maken</span><span class="sxs-lookup"><span data-stu-id="f1889-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="f1889-117">Wanneer u de verificatiecode invoert, wordt u overgezet naar een pagina waar u een nieuw account kunt maken.</span><span class="sxs-lookup"><span data-stu-id="f1889-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="f1889-118">Vul de velden gebruikersnaam en wachtwoord in met het account dat u wilt gebruiken en selecteer **starten**.</span><span class="sxs-lookup"><span data-stu-id="f1889-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="f1889-119">Stap 3: het eigendom van het domein verifiëren en de beheerder worden</span><span class="sxs-lookup"><span data-stu-id="f1889-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="f1889-120">De wizard wordt **de beheerder worden** geopend.</span><span class="sxs-lookup"><span data-stu-id="f1889-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="f1889-121">Als de wizard niet start, zoekt u de tegel **beheerder** en selecteert u deze.</span><span class="sxs-lookup"><span data-stu-id="f1889-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="f1889-122">Selecteer **Ja, ik wil de beheerder zijn**.</span><span class="sxs-lookup"><span data-stu-id="f1889-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="f1889-123">Zorg dat u eigenaar bent van het domein dat u wilt overnemen door een TXT-record toe te voegen aan uw domeinregistratie.</span><span class="sxs-lookup"><span data-stu-id="f1889-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="f1889-124">Met de wizard kunt u de toe te voegen TXT-record, en een koppeling naar de website van uw registratie, en een koppeling naar stapsgewijze instructies weergeven.</span><span class="sxs-lookup"><span data-stu-id="f1889-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="f1889-125">Wanneer u de TXT-record hebt toegevoegd aan de registratie site, gaat u terug naar de wizard en selecteert u **OK, ik heb de record toegevoegd**.</span><span class="sxs-lookup"><span data-stu-id="f1889-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f1889-126">Het overnemen van de Shadow-Tenant heeft geen gevolgen voor bestaande informatie of services.</span><span class="sxs-lookup"><span data-stu-id="f1889-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="f1889-127">Maar als gebruikers in het domein zich hebben geregistreerd voor services waarvoor een licentie is vereist, wordt u gevraagd om licenties voor hen te kopen als onderdeel van het overnemen van de beheerdersrol.</span><span class="sxs-lookup"><span data-stu-id="f1889-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="f1889-128">U kunt licenties kopen of verwijderen nadat het installatieproces van de beheerder is voltooid.</span><span class="sxs-lookup"><span data-stu-id="f1889-128">You can buy or remove licenses once the admin setup process is finished.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="f1889-129">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="f1889-129">Related articles</span></span>

<span data-ttu-id="f1889-130">YouTube: [3 stappen voor het overnemen van een IT-beheerder voor Power bi en Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span><span class="sxs-lookup"><span data-stu-id="f1889-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span></span>

[<span data-ttu-id="f1889-131">Beheerders overname in azure AD</span><span class="sxs-lookup"><span data-stu-id="f1889-131">Admin takeover in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[<span data-ttu-id="f1889-132">Zelfregistratie gebruiken in uw organisatie</span><span class="sxs-lookup"><span data-stu-id="f1889-132">Using self-service sign up in your organization</span></span>](self-service-sign-up.md)
  
[<span data-ttu-id="f1889-133">Wat is de rol van de Power BI-servicebeheerder?</span><span class="sxs-lookup"><span data-stu-id="f1889-133">Understanding the Power BI service administrator role</span></span>](https://docs.microsoft.com/power-bi/service-admin-role)

