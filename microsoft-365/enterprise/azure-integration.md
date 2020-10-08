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
description: Microsoft 365 integreren met Azure AD als u een Wachtwoordsynchronisatie of eenmalige aanmelding met uw on-premises omgeving wilt.
ms.openlocfilehash: b1f20ebc692421ed6df0d6f7c31a4d80347133e3
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384742"
---
# <a name="azure-integration-with-microsoft-365"></a><span data-ttu-id="b4635-103">Azure-integratie met Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b4635-103">Azure integration with Microsoft 365</span></span>

<span data-ttu-id="b4635-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="b4635-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b4635-105">Microsoft 365 maakt gebruik van Azure Active Directory (Azure AD) voor het beheren van gebruikersidentiteiten achter de schermen.</span><span class="sxs-lookup"><span data-stu-id="b4635-105">Microsoft 365 uses Azure Active Directory (Azure AD) to manage user identities behind the scenes.</span></span> <span data-ttu-id="b4635-106">Uw Microsoft 365-abonnement bevat een gratis Azure AD-abonnement, zodat u uw on-premises Active Directory Domain Services (AD DS) kunt integreren om gebruikersaccounts en wachtwoorden te synchroniseren of eenmalige aanmelding in te stellen.</span><span class="sxs-lookup"><span data-stu-id="b4635-106">Your Microsoft 365 subscription includes a free Azure AD subscription so that you can integrate your on-premises Active Directory Domain Services (AD DS) to synchronize user accounts and passwords or set up single sign-on.</span></span> <span data-ttu-id="b4635-107">U kunt ook geavanceerde functies kopen om uw accounts beter te kunnen beheren.</span><span class="sxs-lookup"><span data-stu-id="b4635-107">You can also purchase advanced features to better manage your accounts.</span></span>
  
<span data-ttu-id="b4635-108">Azure AD biedt ook andere functionaliteit, zoals het beheren van geïntegreerde apps, die u kunt gebruiken om uw Microsoft 365-abonnementen uit te breiden en aan te passen.</span><span class="sxs-lookup"><span data-stu-id="b4635-108">Azure AD also offers other functionality, like managing integrated apps, that you can use to extend and customize your Microsoft 365 subscriptions.</span></span>
  
<span data-ttu-id="b4635-109">In het Microsoft 365-Beheercentrum kunt u ook Azure AD Deployment adviseurs gebruiken voor een geleide installatie en configuratie van het Microsoft-Beheercentrum (u moet zijn aangemeld bij Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="b4635-109">You can use the Azure AD deployment advisors for a guided setup and configuration experience in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

 - [<span data-ttu-id="b4635-110">Azure AD Connect-adviseur</span><span class="sxs-lookup"><span data-stu-id="b4635-110">Azure AD Connect advisor</span></span>](https://aka.ms/aadconnectpwsync)
 - [<span data-ttu-id="b4635-111">AD FS-implementatie adviseur</span><span class="sxs-lookup"><span data-stu-id="b4635-111">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
 - [<span data-ttu-id="b4635-112">Installatiehandleiding voor Azure AD</span><span class="sxs-lookup"><span data-stu-id="b4635-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a><span data-ttu-id="b4635-113">Azure AD-edities en Microsoft 365 Identity Management</span><span class="sxs-lookup"><span data-stu-id="b4635-113">Azure AD editions and Microsoft 365 identity management</span></span>

<span data-ttu-id="b4635-114">Als u een betaald abonnement hebt op Microsoft 365, hebt u ook een gratis Azure AD-abonnement.</span><span class="sxs-lookup"><span data-stu-id="b4635-114">If you have a paid subscription to Microsoft 365, you also have a free Azure AD subscription.</span></span> <span data-ttu-id="b4635-115">U kunt Azure AD gebruiken om gebruikers-en groepsaccounts te maken en te beheren.</span><span class="sxs-lookup"><span data-stu-id="b4635-115">You can use Azure AD to create and manage user and group accounts.</span></span> <span data-ttu-id="b4635-116">Om dit abonnement te activeren, moet u eenmalige registratie voltooien.</span><span class="sxs-lookup"><span data-stu-id="b4635-116">To activate this subscription, you have to complete a one-time registration.</span></span> <span data-ttu-id="b4635-117">Later kunt u Azure AD openen vanuit uw Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="b4635-117">Afterward, you can access Azure AD from your Microsoft 365 admin center.</span></span> 

<span data-ttu-id="b4635-118">Voor instructies voor het registreren van uw gratis Azure AD-abonnement raadpleegt u [het gratis Azure AD-abonnement gebruiken](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="b4635-118">For instructions to register your free Azure AD subscription, see [use your free Azure AD subscription](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span></span> <span data-ttu-id="b4635-119">Ga niet rechtstreeks naar azure.microsoft.com om u aan te melden of u eindigt met een proefabonnement of een betaald abonnement op Microsoft Azure dat losstaat van uw gratis Azure AD-abonnement met Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b4635-119">Don't go directly to azure.microsoft.com to sign up or you'll end up with a trial or paid subscription to Microsoft Azure that is separate from your free Azure AD subscription with Microsoft 365.</span></span> 
  
<span data-ttu-id="b4635-120">Met het gratis abonnement kunt u synchroniseren met on-premises directory's, eenmalige aanmelding instellen en synchroniseren met veel software als servicetoepassingen, zoals Salesforce, DropBox en nog veel meer.</span><span class="sxs-lookup"><span data-stu-id="b4635-120">With the free subscription you can synchronize with on-premises directories, set up single sign-on, and synchronize with many software as service applications, such as Salesforce, DropBox, and many more.</span></span>
  
<span data-ttu-id="b4635-121">Als u de verbeterde functionaliteit van de AD DS, bidirectionele synchronisatie en andere beheermogelijkheden wilt, kunt u uw gratis abonnement upgraden naar een betaald Premium-abonnement.</span><span class="sxs-lookup"><span data-stu-id="b4635-121">If you want enhanced AD DS functionality, bi-directional synchronization, and other management capabilities, you can upgrade your free subscription to a paid premium subscription.</span></span> <span data-ttu-id="b4635-122">Zie [Azure Active Directory-edities](https://azure.microsoft.com/pricing/details/active-directory/)voor de details.</span><span class="sxs-lookup"><span data-stu-id="b4635-122">For the details, see [Azure Active Directory editions](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>
  
<span data-ttu-id="b4635-123">Zie [Microsoft 365-identiteits modellen](about-microsoft-365-identity.md)voor meer informatie over microsoft 365 en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b4635-123">For more information about Microsoft 365 and Azure AD, see [Microsoft 365 identity models](about-microsoft-365-identity.md).</span></span>
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a><span data-ttu-id="b4635-124">De mogelijkheden van uw Microsoft 365-Tenant uitbreiden</span><span class="sxs-lookup"><span data-stu-id="b4635-124">Extend the capabilities of your Microsoft 365 tenant</span></span>

|<span data-ttu-id="b4635-125">**Functie**</span><span class="sxs-lookup"><span data-stu-id="b4635-125">**Feature**</span></span>|<span data-ttu-id="b4635-126">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="b4635-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b4635-127">Geïntegreerde apps</span><span class="sxs-lookup"><span data-stu-id="b4635-127">Integrated apps</span></span>  <br/> |<span data-ttu-id="b4635-128">U kunt afzonderlijke apps toegang verlenen tot uw Microsoft 365-gegevens, zoals e-mail, agenda's, contactpersonen, gebruikers, groepen, bestanden en mappen.</span><span class="sxs-lookup"><span data-stu-id="b4635-128">You can grant individual apps access to your Microsoft 365 data, such as mail, calendars, contacts, users, groups, files, and folders.</span></span> <span data-ttu-id="b4635-129">U kunt deze apps ook op algemeen beheerdersniveau machtigen en ze beschikbaar maken voor uw gehele bedrijf door de apps te registreren in azure AD.</span><span class="sxs-lookup"><span data-stu-id="b4635-129">You can also authorize these apps at global admin level and make them available to your entire company by registering the apps in Azure AD.</span></span> <span data-ttu-id="b4635-130">Formore-informatie, Zie [geïntegreerde apps en Azure AD voor Microsoft 365-beheerders](integrated-apps-and-azure-ads.md).</span><span class="sxs-lookup"><span data-stu-id="b4635-130">Formore information, see [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md).</span></span>  <br/> <span data-ttu-id="b4635-131">Zie ook [eenmalige aanmelding](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span><span class="sxs-lookup"><span data-stu-id="b4635-131">Also see [Single sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>  <br/> |
|<span data-ttu-id="b4635-132">PowerApps</span><span class="sxs-lookup"><span data-stu-id="b4635-132">PowerApps</span></span>  <br/> | <span data-ttu-id="b4635-133">Power apps zijn gerichte apps voor mobiele apparaten die verbinding kunnen maken met uw bestaande gegevensbronnen, zoals SharePoint-lijsten en andere data-apps.</span><span class="sxs-lookup"><span data-stu-id="b4635-133">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists and other data apps.</span></span> <span data-ttu-id="b4635-134">Zie [een PowerApp maken voor een lijst in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) en de [PowerApps-pagina](https://powerapps.microsoft.com/) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b4635-134">See [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and the [PowerApps page](https://powerapps.microsoft.com/) for details.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="b4635-135">Zie ook</span><span class="sxs-lookup"><span data-stu-id="b4635-135">See also</span></span>

[<span data-ttu-id="b4635-136">Overzicht van Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b4635-136">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
