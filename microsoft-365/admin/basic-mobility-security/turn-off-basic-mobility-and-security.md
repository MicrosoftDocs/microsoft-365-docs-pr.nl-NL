---
title: Eenvoudige mobiliteit en beveiliging uitschakelen
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: Verwijder groepen of beleidsregels om basis mobiliteit en beveiliging uit te schakelen.
ms.openlocfilehash: 54f78cc30e5259ad5244ce3a8fc6d0f46a395d7c
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336810"
---
# <a name="turn-off-basic-mobility-and-security"></a><span data-ttu-id="70f08-103">Eenvoudige mobiliteit en beveiliging uitschakelen</span><span class="sxs-lookup"><span data-stu-id="70f08-103">Turn off Basic Mobility and Security</span></span>

<span data-ttu-id="70f08-104">Als u eenvoudige mobiliteit en beveiliging effectief wilt uitschakelen, verwijdert u groepen personen die zijn gedefinieerd door beveiligingsgroepen uit het beleid voor Apparaatbeheer of verwijdert u de beleidsregels zelf.</span><span class="sxs-lookup"><span data-stu-id="70f08-104">To effectively turn off Basic Mobility and Security, you remove groups of people defined by security groups from the device management policies, or remove the policies themselves.</span></span>

- <span data-ttu-id="70f08-105">Verwijder groepen gebruikers door gebruikersbeveiligingsgroepen te verwijderen uit de beleidsregels die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="70f08-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span>
    
- <span data-ttu-id="70f08-106">Schakel eenvoudige mobiliteit en beveiliging voor iedereen uit door alle basis beleidsregels voor mobiliteit en beveiliging van beveiligingsapparaten te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="70f08-106">Disable Basic Mobility and Security for everyone by removing all Basic Mobility and Security device policies.</span></span>
    
<span data-ttu-id="70f08-107">Met deze opties verwijdert u de basis mobiliteit en beveiligings naleving voor apparaten in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="70f08-107">These options remove Basic Mobility and Security enforcement for devices in your organization.</span></span> <span data-ttu-id="70f08-108">Helaas kunt u de basis mobiliteit en beveiliging van basis van de burger en beveiliging van uw site helaas niet eenvoudig opzeggen.</span><span class="sxs-lookup"><span data-stu-id="70f08-108">Unfortunately, you can't simply "unprovision" Basic Mobility and Security after you've set it up.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="70f08-109">Let op de gevolgen voor de apparaten van gebruikers wanneer u gebruikersbeveiligingsgroepen verwijdert uit beleidsregels of de beleidsregels zelf verwijdert.</span><span class="sxs-lookup"><span data-stu-id="70f08-109">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves.</span></span> <span data-ttu-id="70f08-110">U kunt bijvoorbeeld e-mail profielen en e-mailberichten in de cache verwijderen, afhankelijk van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="70f08-110">For example, email profiles and cached emails might be removed, depending on the device.</span></span> <span data-ttu-id="70f08-111">Zie  [Wat gebeurt er wanneer u een beleid verwijdert of een gebruiker uit het beleid verwijdert?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="70f08-111">For more info, see  [What happens when you delete a policy or remove a user from the policy?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)</span></span>

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a><span data-ttu-id="70f08-112">Beveiligingsgroepen van een gebruiker verwijderen uit de basis beleidsregels voor mobiliteit en beveiliging van apparaten</span><span class="sxs-lookup"><span data-stu-id="70f08-112">Remove user security groups from Basic Mobility and Security device policies</span></span>

1. <span data-ttu-id="70f08-113">In uw browsertype:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="70f08-113">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span>

2. <span data-ttu-id="70f08-114">Selecteer een apparaatbeleid en selecteer **beleid bewerken**.</span><span class="sxs-lookup"><span data-stu-id="70f08-114">Select a device policy, and select **Edit policy**.</span></span> 

3. <span data-ttu-id="70f08-115">Selecteer op de pagina  **implementatie** de   optie **verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="70f08-115">On the  **Deployment**  page, select **Remove**.</span></span>
    
4. <span data-ttu-id="70f08-116">Selecteer onder  **groepen**een beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="70f08-116">Under  **Groups**, select a security group.</span></span>

5. <span data-ttu-id="70f08-117">Selecteer  **verwijderen**en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="70f08-117">Select  **Remove**, and select **Save**.</span></span>
    

## <a name="remove-basic-mobility-and-security-device-policies"></a><span data-ttu-id="70f08-118">Basisbeleid voor mobiliteit en beveiliging van apparaten verwijderen</span><span class="sxs-lookup"><span data-stu-id="70f08-118">Remove Basic Mobility and Security device policies</span></span>

1.  <span data-ttu-id="70f08-119">In uw browsertype:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="70f08-119">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span> 

2.  <span data-ttu-id="70f08-120">Selecteer een apparaatbeleid en selecteer vervolgens  **beleid verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="70f08-120">Select a device policy, and then select  **Delete policy**.</span></span>
    
3.  <span data-ttu-id="70f08-121">Selecteer in het waarschuwingsvenster de optie **Ja**.</span><span class="sxs-lookup"><span data-stu-id="70f08-121">In the Warning dialog box, select **Yes**.</span></span>

>[!NOTE] 
><span data-ttu-id="70f08-122">Zie voor meer informatie over het deblokkeren van apparaten als uw organisatie vasthoudt, het blogbericht over het [verwijderen van toegangsbeheer van mobiele apparaten voor Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span><span class="sxs-lookup"><span data-stu-id="70f08-122">For more steps to unblock devices if your organization devices are still in a blocked state,  see the blog post [Removing Access Control from Mobile Device Management for Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span></span>
