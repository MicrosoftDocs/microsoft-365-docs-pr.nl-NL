---
title: Op rollen gebaseerde toegangsbeheer gebruiken om fijnkorrelige toegang te verlenen tot het Microsoft Defender-beveiligingscentrum
description: Maak rollen en groepen binnen uw beveiligingsbewerkingen om toegang te verlenen tot de portal.
keywords: rbac, rol, gebaseerd, toegang, besturingselement, groepen, besturingselement, laag, aad
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d95163bd7caf6e05295fc35b3f9c2bf95230dc83
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058182"
---
# <a name="manage-portal-access-using-role-based-access-control"></a><span data-ttu-id="e10d8-104">Portaltoegang beheren met behulp van toegangsbeheer op basis van rollen</span><span class="sxs-lookup"><span data-stu-id="e10d8-104">Manage portal access using role-based access control</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e10d8-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e10d8-105">**Applies to:**</span></span>
- <span data-ttu-id="e10d8-106">Microsoft Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e10d8-106">Azure Active Directory</span></span>
- <span data-ttu-id="e10d8-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="e10d8-107">Office 365</span></span>

> <span data-ttu-id="e10d8-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="e10d8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e10d8-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="e10d8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-rbac-abovefoldlink)

<span data-ttu-id="e10d8-110">Met behulp van RBAC (Role Based Access Control) kunt u rollen en groepen maken binnen uw beveiligingsbewerkingsteam om de juiste toegang tot de portal te verlenen.</span><span class="sxs-lookup"><span data-stu-id="e10d8-110">Using role-based access control (RBAC), you can create roles and groups within your security operations team to grant appropriate access to the  portal.</span></span> <span data-ttu-id="e10d8-111">Op basis van de rollen en groepen die u maakt, hebt u een fijnkorrelige controle over wat gebruikers met toegang tot de portal kunnen zien en doen.</span><span class="sxs-lookup"><span data-stu-id="e10d8-111">Based on the roles and groups you create, you have fine-grained control over what users with access to the portal can see and do.</span></span> 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bJ2a]

<span data-ttu-id="e10d8-112">Grote teams voor geo-gedistribueerde beveiligingsbewerkingen gebruiken meestal een op een laag gebaseerd model om toegang tot beveiligingsportals toe te wijzen en te machtigen.</span><span class="sxs-lookup"><span data-stu-id="e10d8-112">Large geo-distributed security operations teams typically adopt a tier-based model to assign and authorize access to security portals.</span></span> <span data-ttu-id="e10d8-113">Standaardlagen zijn de volgende drie niveaus:</span><span class="sxs-lookup"><span data-stu-id="e10d8-113">Typical tiers include the following three levels:</span></span>

<span data-ttu-id="e10d8-114">Laag</span><span class="sxs-lookup"><span data-stu-id="e10d8-114">Tier</span></span> | <span data-ttu-id="e10d8-115">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="e10d8-115">Description</span></span>
:---|:---
<span data-ttu-id="e10d8-116">Laag 1</span><span class="sxs-lookup"><span data-stu-id="e10d8-116">Tier 1</span></span> | <span data-ttu-id="e10d8-117">**Team voor lokale beveiligingsbewerkingen / IT-team**</span><span class="sxs-lookup"><span data-stu-id="e10d8-117">**Local security operations team / IT team**</span></span> <br> <span data-ttu-id="e10d8-118">Dit team triages and investigates alerts contained within their geocation and escalates to Tier 2 in cases where a active remediation is required.</span><span class="sxs-lookup"><span data-stu-id="e10d8-118">This team usually triages and investigates alerts contained within their geolocation and escalates to Tier 2 in cases where an active remediation is required.</span></span>
<span data-ttu-id="e10d8-119">Laag 2</span><span class="sxs-lookup"><span data-stu-id="e10d8-119">Tier 2</span></span> | <span data-ttu-id="e10d8-120">**Team voor regionale beveiligingsbewerkingen**</span><span class="sxs-lookup"><span data-stu-id="e10d8-120">**Regional security operations team**</span></span> <br> <span data-ttu-id="e10d8-121">Dit team kan alle apparaten voor hun regio zien en herstelacties uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="e10d8-121">This team can see all the devices for their region and perform remediation actions.</span></span>
<span data-ttu-id="e10d8-122">Laag 3</span><span class="sxs-lookup"><span data-stu-id="e10d8-122">Tier 3</span></span> | <span data-ttu-id="e10d8-123">**Team voor globale beveiligingsbewerkingen**</span><span class="sxs-lookup"><span data-stu-id="e10d8-123">**Global security operations team**</span></span> <br> <span data-ttu-id="e10d8-124">Dit team bestaat uit beveiligingsexperts en is gemachtigd om alle acties vanuit de portal te bekijken en uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="e10d8-124">This team consists of security experts and are authorized to see and perform all actions from the portal.</span></span>

<span data-ttu-id="e10d8-125">Defender for Endpoint RBAC is ontworpen ter ondersteuning van uw keuzemodel op basis van lagen of rollen en biedt u gedetailleerde controle over welke rollen kunnen worden gezien, apparaten die ze kunnen openen en acties die ze kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="e10d8-125">Defender for Endpoint RBAC is designed to support your tier- or role-based model of choice and gives you granular control over what roles can see, devices they can access, and actions they can take.</span></span> <span data-ttu-id="e10d8-126">Het RBAC-framework is gecentreerd rond de volgende besturingselementen:</span><span class="sxs-lookup"><span data-stu-id="e10d8-126">The RBAC framework is centered around the following controls:</span></span>

- <span data-ttu-id="e10d8-127">**Bepalen wie specifieke actie kan ondernemen**</span><span class="sxs-lookup"><span data-stu-id="e10d8-127">**Control who can take specific action**</span></span>
  - <span data-ttu-id="e10d8-128">Maak aangepaste rollen en beheer de mogelijkheden van Defender voor eindpunten die ze met granulariteit kunnen openen.</span><span class="sxs-lookup"><span data-stu-id="e10d8-128">Create custom roles and control what Defender for Endpoint capabilities they can access with granularity.</span></span>
 
- <span data-ttu-id="e10d8-129">**Bepalen wie informatie kan zien over specifieke apparaatgroepen of groepen**</span><span class="sxs-lookup"><span data-stu-id="e10d8-129">**Control who can see information on specific device group or groups**</span></span>
  - <span data-ttu-id="e10d8-130">[Maak apparaatgroepen](machine-groups.md) op basis van specifieke criteria, zoals namen, tags, domeinen en andere, en verleen vervolgens roltoegang aan deze groepen met behulp van een specifieke Azure Active Directory (Azure AD) gebruikersgroep.</span><span class="sxs-lookup"><span data-stu-id="e10d8-130">[Create device groups](machine-groups.md) by specific criteria such as names, tags, domains, and others, then grant role access to them using a specific  Azure Active Directory (Azure AD) user group.</span></span>

<span data-ttu-id="e10d8-131">Als u op rollen gebaseerde toegang wilt implementeren, moet u beheerdersrollen definiëren, bijbehorende machtigingen toewijzen en Azure AD-gebruikersgroepen toewijzen die aan de rollen zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="e10d8-131">To implement role-based access, you'll need to define admin roles, assign corresponding permissions, and assign Azure AD user groups assigned to the roles.</span></span>


### <a name="before-you-begin"></a><span data-ttu-id="e10d8-132">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="e10d8-132">Before you begin</span></span>
<span data-ttu-id="e10d8-133">Voordat u RBAC gebruikt, is het belangrijk dat u de rollen begrijpt die machtigingen kunnen verlenen en de gevolgen van het in- en uitschakelen van RBAC.</span><span class="sxs-lookup"><span data-stu-id="e10d8-133">Before using RBAC, it's important that you understand the roles that can grant permissions and the consequences of turning on RBAC.</span></span>


> [!WARNING]
> <span data-ttu-id="e10d8-134">Voordat u de functie inschakelen, is het belangrijk dat u een rol voor globale beheerder of beveiligingsbeheerder hebt in Azure AD en dat uw Azure AD-groepen klaar zijn om het risico te beperken dat u buiten de portal wordt vergrendeld.</span><span class="sxs-lookup"><span data-stu-id="e10d8-134">Before enabling the feature, it's important that you have a Global Administrator role or Security Administrator role in Azure AD and that you have your Azure AD groups ready to reduce the risk of being locked out of the portal.</span></span> 

<span data-ttu-id="e10d8-135">Wanneer u zich voor het eerst aanmeldt bij het Microsoft Defender-beveiligingscentrum, krijgt u volledige toegang of alleen-lezentoegang.</span><span class="sxs-lookup"><span data-stu-id="e10d8-135">When you first log in to Microsoft Defender Security Center, you're granted either full access or read only access.</span></span> <span data-ttu-id="e10d8-136">Volledige toegangsrechten worden verleend aan gebruikers met beveiligingsbeheerder- of globale beheerdersrollen in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e10d8-136">Full access rights are granted to users with Security Administrator or Global Administrator roles in Azure AD.</span></span> <span data-ttu-id="e10d8-137">Alleen-lezen wordt verleend aan gebruikers met een beveiligingslezerrol in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e10d8-137">Read only access is granted to users with a Security Reader role in Azure AD.</span></span> 

<span data-ttu-id="e10d8-138">Iemand met een rol van globale beheerder van Defender voor Eindpunt heeft onbeperkte toegang tot alle apparaten, ongeacht de apparaatgroepsorganisatie en de toewijzingen voor Azure AD-gebruikersgroepen</span><span class="sxs-lookup"><span data-stu-id="e10d8-138">Someone with a Defender for Endpoint Global administrator role has unrestricted access to all devices, regardless of their device group association and the Azure AD user groups assignments</span></span>

> [!WARNING]
> <span data-ttu-id="e10d8-139">In eerste instantie kunnen alleen personen met globale beheerders- of beveiligingsbeheerdersrechten van Azure AD rollen maken en toewijzen in het Microsoft Defender-beveiligingscentrum. Daarom is het belangrijk dat de juiste groepen klaar zijn in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e10d8-139">Initially, only those with Azure AD Global Administrator or Security Administrator rights will be able to create and assign roles in Microsoft Defender Security Center, therefore, having the right groups ready in Azure AD is important.</span></span>
>
> <span data-ttu-id="e10d8-140">**Als u toegangsbeheer op basis van rollen invoegt, kunnen gebruikers met alleen-lezen-machtigingen (bijvoorbeeld gebruikers die zijn toegewezen aan de lezerrol van Azure AD Security) de toegang verliezen totdat ze aan een rol zijn toegewezen.**</span><span class="sxs-lookup"><span data-stu-id="e10d8-140">**Turning on role-based access control will cause users with read-only permissions (for example, users assigned to Azure AD Security reader role) to lose access until they are assigned to a role.**</span></span> 
>
><span data-ttu-id="e10d8-141">Gebruikers met beheerdersmachtigingen krijgen automatisch de standaard ingebouwde rol van globale beheerder van Defender voor Eindpunt toegewezen met volledige machtigingen.</span><span class="sxs-lookup"><span data-stu-id="e10d8-141">Users with admin permissions are automatically assigned the default built-in Defender for Endpoint global administrator role with full permissions.</span></span> <span data-ttu-id="e10d8-142">Nadat u zich hebt voor het gebruik van RBAC hebt gekozen, kunt u extra gebruikers die geen Globale Azure AD- of Beveiligingsbeheerders zijn, toewijzen aan de globale beheerdersrol van Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="e10d8-142">After opting in to use RBAC, you can assign additional users that are not Azure AD Global or Security Administrators to the Defender for Endpoint global administrator role.</span></span> 
>
> <span data-ttu-id="e10d8-143">Nadat u zich hebt aangemeld voor het gebruik van RBAC, kunt u niet terugkeren naar de eerste rollen zoals wanneer u zich voor het eerst hebt aangemeld bij de portal.</span><span class="sxs-lookup"><span data-stu-id="e10d8-143">After opting in to use RBAC, you cannot revert to the initial roles as when you first logged into the portal.</span></span> 



## <a name="related-topic"></a><span data-ttu-id="e10d8-144">Gerelateerd onderwerp</span><span class="sxs-lookup"><span data-stu-id="e10d8-144">Related topic</span></span>
- [<span data-ttu-id="e10d8-145">Apparaatgroepen maken en beheren in Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="e10d8-145">Create and manage device groups in Microsoft Defender for Endpoint</span></span>](machine-groups.md)
