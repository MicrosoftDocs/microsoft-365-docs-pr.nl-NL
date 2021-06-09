---
title: Azure-integratie met Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: a5efce5d-9c9c-4190-b61b-fd273c1d425f
description: Integreer Microsoft 365 met Azure AD als u wachtwoordsynchronisatie of een enkele aanmelding wilt met uw on-premises omgeving.
ms.openlocfilehash: f977969634401d59d7598136f9323cb0e37f9ece
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905330"
---
# <a name="azure-integration-with-microsoft-365"></a><span data-ttu-id="85618-103">Azure-integratie met Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="85618-103">Azure integration with Microsoft 365</span></span>

<span data-ttu-id="85618-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="85618-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="85618-105">Microsoft 365 gebruikt Azure Active Directory (Azure AD) om gebruikersidentiteiten achter de schermen te beheren.</span><span class="sxs-lookup"><span data-stu-id="85618-105">Microsoft 365 uses Azure Active Directory (Azure AD) to manage user identities behind the scenes.</span></span> <span data-ttu-id="85618-106">Uw Microsoft 365-abonnement bevat een gratis Azure AD-abonnement, zodat u uw on-premises Active Directory Domain Services (AD DS) kunt integreren om gebruikersaccounts en wachtwoorden te synchroniseren of een enkele aanmelding in te stellen.</span><span class="sxs-lookup"><span data-stu-id="85618-106">Your Microsoft 365 subscription includes a free Azure AD subscription so that you can integrate your on-premises Active Directory Domain Services (AD DS) to synchronize user accounts and passwords or set up single sign-on.</span></span> <span data-ttu-id="85618-107">U kunt ook geavanceerde functies kopen om uw accounts beter te beheren.</span><span class="sxs-lookup"><span data-stu-id="85618-107">You can also purchase advanced features to better manage your accounts.</span></span>
  
<span data-ttu-id="85618-108">Azure AD biedt ook andere functionaliteit, zoals het beheren van geïntegreerde apps, die u kunt gebruiken om uw Microsoft 365 aanpassen.</span><span class="sxs-lookup"><span data-stu-id="85618-108">Azure AD also offers other functionality, like managing integrated apps, that you can use to extend and customize your Microsoft 365 subscriptions.</span></span>
  
<span data-ttu-id="85618-109">U kunt de Azure AD-implementatieadviseurs gebruiken voor een begeleide installatie- en configuratie-ervaring in het Microsoft 365-beheercentrum (u moet zijn aangemeld bij Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="85618-109">You can use the Azure AD deployment advisors for a guided setup and configuration experience in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

 - [<span data-ttu-id="85618-110">Azure AD Verbinding maken adviseur</span><span class="sxs-lookup"><span data-stu-id="85618-110">Azure AD Connect advisor</span></span>](https://aka.ms/aadconnectpwsync)
 - [<span data-ttu-id="85618-111">AD FS-implementatieadviseur</span><span class="sxs-lookup"><span data-stu-id="85618-111">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
 - [<span data-ttu-id="85618-112">Installatiehandleiding voor Azure AD</span><span class="sxs-lookup"><span data-stu-id="85618-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a><span data-ttu-id="85618-113">Azure AD-edities en Microsoft 365 identiteitsbeheer</span><span class="sxs-lookup"><span data-stu-id="85618-113">Azure AD editions and Microsoft 365 identity management</span></span>

<span data-ttu-id="85618-114">Als u een betaald abonnement hebt voor Microsoft 365, hebt u ook een gratis Azure AD-abonnement.</span><span class="sxs-lookup"><span data-stu-id="85618-114">If you have a paid subscription to Microsoft 365, you also have a free Azure AD subscription.</span></span> <span data-ttu-id="85618-115">U kunt Azure AD gebruiken om gebruikers- en groepsaccounts te maken en te beheren.</span><span class="sxs-lookup"><span data-stu-id="85618-115">You can use Azure AD to create and manage user and group accounts.</span></span> <span data-ttu-id="85618-116">Als u dit abonnement wilt activeren, moet u een eenjarige registratie voltooien.</span><span class="sxs-lookup"><span data-stu-id="85618-116">To activate this subscription, you have to complete a one-time registration.</span></span> <span data-ttu-id="85618-117">Daarna hebt u toegang tot Azure AD vanuit uw Microsoft 365 beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="85618-117">Afterward, you can access Azure AD from your Microsoft 365 admin center.</span></span> 

<span data-ttu-id="85618-118">Zie uw gratis Azure AD-abonnement gebruiken voor instructies voor het registreren van uw gratis [Azure AD-abonnement.](../compliance/use-your-free-azure-ad-subscription-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="85618-118">For instructions to register your free Azure AD subscription, see [use your free Azure AD subscription](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span></span> <span data-ttu-id="85618-119">Ga niet rechtstreeks naar azure.microsoft.com om u aan te melden of u krijgt een proefabonnement of betaald abonnement op Microsoft Azure dat los staat van uw gratis Azure AD-abonnement met Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="85618-119">Don't go directly to azure.microsoft.com to sign up or you'll end up with a trial or paid subscription to Microsoft Azure that is separate from your free Azure AD subscription with Microsoft 365.</span></span> 
  
<span data-ttu-id="85618-120">Met het gratis abonnement kunt u synchroniseren met on-premises directories, een enkele aanmelding instellen en synchroniseren met veel software als servicetoepassingen, zoals Salesforce, DropBox en nog veel meer.</span><span class="sxs-lookup"><span data-stu-id="85618-120">With the free subscription you can synchronize with on-premises directories, set up single sign-on, and synchronize with many software as service applications, such as Salesforce, DropBox, and many more.</span></span>
  
<span data-ttu-id="85618-121">Als u uitgebreide AD DS-functionaliteit, bi-directionele synchronisatie en andere beheermogelijkheden wilt, kunt u uw gratis abonnement upgraden naar een betaald premium-abonnement.</span><span class="sxs-lookup"><span data-stu-id="85618-121">If you want enhanced AD DS functionality, bi-directional synchronization, and other management capabilities, you can upgrade your free subscription to a paid premium subscription.</span></span> <span data-ttu-id="85618-122">Zie voor meer informatie [Azure Active Directory edities.](https://azure.microsoft.com/pricing/details/active-directory/)</span><span class="sxs-lookup"><span data-stu-id="85618-122">For the details, see [Azure Active Directory editions](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>
  
<span data-ttu-id="85618-123">Zie voor meer informatie Microsoft 365 en Azure AD [Microsoft 365 identiteitsmodellen.](about-microsoft-365-identity.md)</span><span class="sxs-lookup"><span data-stu-id="85618-123">For more information about Microsoft 365 and Azure AD, see [Microsoft 365 identity models](about-microsoft-365-identity.md).</span></span>
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a><span data-ttu-id="85618-124">De mogelijkheden van uw Microsoft 365 uitbreiden</span><span class="sxs-lookup"><span data-stu-id="85618-124">Extend the capabilities of your Microsoft 365 tenant</span></span>

|<span data-ttu-id="85618-125">**Functie**</span><span class="sxs-lookup"><span data-stu-id="85618-125">**Feature**</span></span>|<span data-ttu-id="85618-126">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="85618-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="85618-127">Geïntegreerde apps</span><span class="sxs-lookup"><span data-stu-id="85618-127">Integrated apps</span></span>  <br/> |<span data-ttu-id="85618-128">U kunt afzonderlijke apps toegang verlenen tot uw Microsoft 365, zoals e-mail, agenda's, contactpersonen, gebruikers, groepen, bestanden en mappen.</span><span class="sxs-lookup"><span data-stu-id="85618-128">You can grant individual apps access to your Microsoft 365 data, such as mail, calendars, contacts, users, groups, files, and folders.</span></span> <span data-ttu-id="85618-129">U kunt deze apps ook autoreren op globaal beheerniveau en deze beschikbaar maken voor uw hele bedrijf door de apps te registreren in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="85618-129">You can also authorize these apps at global admin level and make them available to your entire company by registering the apps in Azure AD.</span></span> <span data-ttu-id="85618-130">Zie Geïntegreerde apps en Azure AD voor Microsoft 365 beheerders voor [meer informatie.](integrated-apps-and-azure-ads.md)</span><span class="sxs-lookup"><span data-stu-id="85618-130">Formore information, see [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md).</span></span>  <br/> <span data-ttu-id="85618-131">Zie ook [Een aanmelding](/azure/active-directory/manage-apps/what-is-single-sign-on).</span><span class="sxs-lookup"><span data-stu-id="85618-131">Also see [Single sign-on](/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span>  <br/> |
|<span data-ttu-id="85618-132">PowerApps</span><span class="sxs-lookup"><span data-stu-id="85618-132">PowerApps</span></span>  <br/> | <span data-ttu-id="85618-133">Power-apps zijn gerichte apps voor mobiele apparaten die verbinding kunnen maken met uw bestaande gegevensbronnen, SharePoint lijsten en andere gegevens-apps.</span><span class="sxs-lookup"><span data-stu-id="85618-133">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists and other data apps.</span></span> <span data-ttu-id="85618-134">Zie [Een PowerApp maken voor een lijst in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) en de [PowerApps-pagina](https://powerapps.microsoft.com/) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="85618-134">See [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and the [PowerApps page](https://powerapps.microsoft.com/) for details.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="85618-135">Zie ook</span><span class="sxs-lookup"><span data-stu-id="85618-135">See also</span></span>

[<span data-ttu-id="85618-136">Microsoft 365 Enterprise overzicht</span><span class="sxs-lookup"><span data-stu-id="85618-136">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)