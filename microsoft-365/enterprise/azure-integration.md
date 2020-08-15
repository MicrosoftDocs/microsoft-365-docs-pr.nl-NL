---
title: Azure-integratie met Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/09/2019
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
ms.openlocfilehash: 045760f000abdbf053e09d89b296fbafa4c24786
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689500"
---
# <a name="azure-integration-with-microsoft-365"></a><span data-ttu-id="0ff4a-103">Azure-integratie met Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0ff4a-103">Azure integration with Microsoft 365</span></span>

<span data-ttu-id="0ff4a-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="0ff4a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="0ff4a-105">Microsoft 365 maakt gebruik van Azure Active Directory (Azure AD) voor het beheren van gebruikersidentiteiten achter de schermen.</span><span class="sxs-lookup"><span data-stu-id="0ff4a-105">Microsoft 365 uses Azure Active Directory (Azure AD) to manage user identities behind the scenes.</span></span> <span data-ttu-id="0ff4a-106">Uw Microsoft 365-abonnement bevat een gratis abonnement op Azure AD, zodat u Microsoft 365 kunt integreren met Azure AD als u uw wachtwoorden wilt synchroniseren of eenmalige aanmelding wilt instellen voor uw on-premises omgeving.</span><span class="sxs-lookup"><span data-stu-id="0ff4a-106">Your Microsoft 365 subscription includes a free subscription to Azure AD so that you can integrate Microsoft 365 with Azure AD if you want to sync passwords or set up single sign-on with your on-premises environment.</span></span> <span data-ttu-id="0ff4a-107">U kunt ook geavanceerde functies kopen om uw accounts beter te kunnen beheren.</span><span class="sxs-lookup"><span data-stu-id="0ff4a-107">You can also buy advanced features to better manage your accounts.</span></span>
  
<span data-ttu-id="0ff4a-108">Azure biedt ook andere functionaliteit, zoals het beheren van geïntegreerde apps, die u kunt gebruiken om uw Microsoft 365-abonnementen uit te breiden en aan te passen.</span><span class="sxs-lookup"><span data-stu-id="0ff4a-108">Azure also offers other functionality, like managing integrated apps, that you can use to extend and customize your Microsoft 365 subscriptions.</span></span>
  
<span data-ttu-id="0ff4a-109">U kunt de Azure AD Deployment adviseurs gebruiken voor een begeleide configuratie en configuratie-ervaring (u moet zijn aangemeld bij Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="0ff4a-109">You can use the Azure AD deployment advisors for a guided setup and configuration experience (you must be signed in to Microsoft 365):</span></span>

 - [<span data-ttu-id="0ff4a-110">Azure AD Connect-adviseur</span><span class="sxs-lookup"><span data-stu-id="0ff4a-110">Azure AD Connect advisor</span></span>](https://aka.ms/aadconnectpwsync)
 - [<span data-ttu-id="0ff4a-111">AD FS-implementatie adviseur</span><span class="sxs-lookup"><span data-stu-id="0ff4a-111">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
 - [<span data-ttu-id="0ff4a-112">Installatiehandleiding voor Azure AD</span><span class="sxs-lookup"><span data-stu-id="0ff4a-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a><span data-ttu-id="0ff4a-113">Azure AD-edities en Microsoft 365 Identity Management</span><span class="sxs-lookup"><span data-stu-id="0ff4a-113">Azure AD editions and Microsoft 365 identity management</span></span>

<span data-ttu-id="0ff4a-114">Als u een betaald abonnement hebt op Microsoft 365, hebt u ook een gratis abonnement op Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0ff4a-114">If you have a paid subscription to Microsoft 365, you also have a free subscription to Azure AD.</span></span> <span data-ttu-id="0ff4a-115">U kunt Azure AD gebruiken om gebruikers-en groepsaccounts te maken en te beheren.</span><span class="sxs-lookup"><span data-stu-id="0ff4a-115">You can use Azure AD to create and manage user and group accounts.</span></span> <span data-ttu-id="0ff4a-116">Om dit abonnement te activeren, moet u eenmalige registratie voltooien.</span><span class="sxs-lookup"><span data-stu-id="0ff4a-116">To activate this subscription you have to complete a one-time registration.</span></span> <span data-ttu-id="0ff4a-117">Later kunt u Azure AD openen vanuit uw Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="0ff4a-117">Afterward, you can access Azure AD from your Microsoft 365 admin center.</span></span> 

<span data-ttu-id="0ff4a-118">Zie [uw gratis Azure AD-abonnement gebruiken](https://go.microsoft.com/fwlink/p/?LinkId=617127)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="0ff4a-118">For instructions, see [use your free Azure AD subscription](https://go.microsoft.com/fwlink/p/?LinkId=617127).</span></span> <span data-ttu-id="0ff4a-119">Volg de instructies voor het registreren van het gratis Azure AD-abonnement dat deel uitmaakt van uw abonnement op Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0ff4a-119">Follow the instructions to register the free Azure AD subscription that comes with your subscription to Microsoft 365.</span></span> <span data-ttu-id="0ff4a-120">Ga niet rechtstreeks naar azure.microsoft.com om u aan te melden of u eindigt met een proefabonnement of een betaald abonnement op Microsoft Azure dat losstaat van uw gratis abonnement voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0ff4a-120">Don't go directly to azure.microsoft.com to sign up or you'll end up with a trial or paid subscription to Microsoft Azure that is separate from your free one for Microsoft 365.</span></span> 
  
<span data-ttu-id="0ff4a-121">Met het gratis abonnement kunt u synchroniseren met on-premises directory's, eenmalige aanmelding instellen en synchroniseren met veel software als servicetoepassingen, zoals Salesforce, DropBox en nog veel meer.</span><span class="sxs-lookup"><span data-stu-id="0ff4a-121">With the free subscription you can synchronize with on-premises directories, set up single sign-on, and synchronize with many software as service applications, such as Salesforce, DropBox and many more.</span></span>
  
<span data-ttu-id="0ff4a-122">Als u de verbeterde Active Directory Domain Services (AD DS)-functionaliteit, bidirectionele synchronisatie en andere beheermogelijkheden wilt, kunt u uw gratis abonnement upgraden naar een betaald Premium-abonnement.</span><span class="sxs-lookup"><span data-stu-id="0ff4a-122">If you want enhanced Active Directory Domain Services (AD DS) functionality, bi-directional synchronization, and other management capabilities, you can upgrade your free subscription to a paid premium subscription.</span></span> <span data-ttu-id="0ff4a-123">Zie versies van [Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0ff4a-123">For details see [Azure Active Directory editions](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>
  
<span data-ttu-id="0ff4a-124">Zie [informatie over Microsoft 365 identiteit en Azure Active Directory](about-microsoft-365-identity.md)voor meer informatie over microsoft 365 en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0ff4a-124">For more information about Microsoft 365 and Azure AD, see [Understanding Microsoft 365 Identity and Azure Active Directory](about-microsoft-365-identity.md).</span></span>
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a><span data-ttu-id="0ff4a-125">De mogelijkheden van uw Microsoft 365-Tenant uitbreiden</span><span class="sxs-lookup"><span data-stu-id="0ff4a-125">Extend the capabilities of your Microsoft 365 tenant</span></span>

|<span data-ttu-id="0ff4a-126">**Functie**</span><span class="sxs-lookup"><span data-stu-id="0ff4a-126">**Feature**</span></span>|<span data-ttu-id="0ff4a-127">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="0ff4a-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0ff4a-128">Geïntegreerde apps</span><span class="sxs-lookup"><span data-stu-id="0ff4a-128">Integrated apps</span></span>  <br/> |<span data-ttu-id="0ff4a-129">U kunt individuele apps toegang verlenen tot uw Microsoft 365-gegevens, zoals e-mail, agenda's, contactpersonen, gebruikers, groepen, bestanden en mappen.</span><span class="sxs-lookup"><span data-stu-id="0ff4a-129">You can grant individual apps access to your Microsoft 365 data, like mail, calendars, contacts, users, groups, files, and folders.</span></span> <span data-ttu-id="0ff4a-130">U kunt deze apps ook op algemeen beheerdersniveau machtigen en ze beschikbaar maken voor uw gehele bedrijf door de apps te registreren in azure AD.</span><span class="sxs-lookup"><span data-stu-id="0ff4a-130">You can also authorize these apps at global admin level and make them available to your entire company by registering the apps in Azure AD.</span></span> <span data-ttu-id="0ff4a-131">Zie [geïntegreerde apps en Azure AD voor Microsoft 365-beheerders](https://support.office.com/article/cb2250e3-451e-416f-bf4e-363549652c2a)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0ff4a-131">For details see [Integrated Apps and Azure AD for Microsoft 365 administrators](https://support.office.com/article/cb2250e3-451e-416f-bf4e-363549652c2a).</span></span>  <br/> <span data-ttu-id="0ff4a-132">Zie ook [eenmalige aanmelding bij toepassingen](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span><span class="sxs-lookup"><span data-stu-id="0ff4a-132">Also see [single sign-on to applications](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>  <br/> |
|<span data-ttu-id="0ff4a-133">PowerApps</span><span class="sxs-lookup"><span data-stu-id="0ff4a-133">PowerApps</span></span>  <br/> | <span data-ttu-id="0ff4a-134">Power apps zijn gerichte apps voor mobiele apparaten die verbinding kunnen maken met uw bestaande gegevensbronnen, zoals SharePoint-lijsten en andere data-apps.</span><span class="sxs-lookup"><span data-stu-id="0ff4a-134">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists, and other data apps.</span></span> <span data-ttu-id="0ff4a-135">Zie [een PowerApp maken voor een lijst in de SharePoint Online-](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) en [PowerApps-pagina](https://powerapps.microsoft.com/) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0ff4a-135">See [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and [PowerApps page](https://powerapps.microsoft.com/) for details.</span></span>  <br/> |
   
<span data-ttu-id="0ff4a-136">Meer informatie vindt u in [geïntegreerde apps en Azure AD voor Microsoft 365-beheerders](integrated-apps-and-azure-ads.md) en de [Azure AD-toepassings galerie en eenmalige aanmelding](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).</span><span class="sxs-lookup"><span data-stu-id="0ff4a-136">Learn more at [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md) and [Azure AD application gallery and single-sign-on](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span>

## <a name="see-also"></a><span data-ttu-id="0ff4a-137">Zie ook</span><span class="sxs-lookup"><span data-stu-id="0ff4a-137">See also</span></span>

[<span data-ttu-id="0ff4a-138">Overzicht van Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="0ff4a-138">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
