---
title: Basic Mobility en Security uitschakelen
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
description: Verwijder groepen of beleidsregels om Basismobiliteit en beveiliging uit te schakelen.
ms.openlocfilehash: 1d81aed01193fb2ba821ebc055958ac6cd8ac382
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023867"
---
# <a name="turn-off-basic-mobility-and-security"></a><span data-ttu-id="f7be8-103">Basic Mobility en Security uitschakelen</span><span class="sxs-lookup"><span data-stu-id="f7be8-103">Turn off Basic Mobility and Security</span></span>

<span data-ttu-id="f7be8-104">Als u basismobiliteit en beveiliging effectief wilt uitschakelen, verwijdert u groepen personen die zijn gedefinieerd door beveiligingsgroepen uit het beleid voor apparaatbeheer of verwijdert u het beleid zelf.</span><span class="sxs-lookup"><span data-stu-id="f7be8-104">To effectively turn off Basic Mobility and Security, you remove groups of people defined by security groups from the device management policies, or remove the policies themselves.</span></span>

- <span data-ttu-id="f7be8-105">Verwijder groepen gebruikers door gebruikersbeveiligingsgroepen te verwijderen uit het apparaatbeleid dat u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="f7be8-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span>

- <span data-ttu-id="f7be8-106">Schakel Basismobiliteit en beveiliging voor iedereen uit door alle beleidsregels voor basismobiliteits- en beveiligingsapparaat te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="f7be8-106">Disable Basic Mobility and Security for everyone by removing all Basic Mobility and Security device policies.</span></span>

<span data-ttu-id="f7be8-107">Met deze opties worden basishandhaving voor mobiliteit en beveiliging voor apparaten in uw organisatie verwijderd.</span><span class="sxs-lookup"><span data-stu-id="f7be8-107">These options remove Basic Mobility and Security enforcement for devices in your organization.</span></span> <span data-ttu-id="f7be8-108">Het is helaas niet mogelijk om basismobiliteit en beveiliging te 'onteigenen' nadat u deze hebt ingesteld.</span><span class="sxs-lookup"><span data-stu-id="f7be8-108">Unfortunately, you can't simply "unprovision" Basic Mobility and Security after you've set it up.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="f7be8-109">Let op de gevolgen voor de apparaten van gebruikers wanneer u gebruikersbeveiligingsgroepen verwijdert uit beleidsregels of het beleid zelf verwijdert.</span><span class="sxs-lookup"><span data-stu-id="f7be8-109">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves.</span></span> <span data-ttu-id="f7be8-110">E-mailprofielen en e-mailberichten met cache kunnen bijvoorbeeld worden verwijderd, afhankelijk van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="f7be8-110">For example, email profiles and cached emails might be removed, depending on the device.</span></span> <span data-ttu-id="f7be8-111">Zie Wat gebeurt er als u een beleid verwijdert of een gebruiker uit het  [beleid verwijdert voor meer informatie?](../../admin/basic-mobility-security/create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="f7be8-111">For more info, see  [What happens when you delete a policy or remove a user from the policy?](../../admin/basic-mobility-security/create-device-security-policies.md)</span></span>

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a><span data-ttu-id="f7be8-112">Gebruikersbeveiligingsgroepen verwijderen uit basisbeleid voor mobiliteits- en beveiligingsapparaat</span><span class="sxs-lookup"><span data-stu-id="f7be8-112">Remove user security groups from Basic Mobility and Security device policies</span></span>

1. <span data-ttu-id="f7be8-113">In uw browsertype:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="f7be8-113">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span>

2. <span data-ttu-id="f7be8-114">Selecteer een apparaatbeleid en selecteer **Beleid bewerken.**</span><span class="sxs-lookup"><span data-stu-id="f7be8-114">Select a device policy, and select **Edit policy**.</span></span> 

3. <span data-ttu-id="f7be8-115">Selecteer op  **de pagina** Implementatie de   optie **Verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="f7be8-115">On the  **Deployment**  page, select **Remove**.</span></span>

4. <span data-ttu-id="f7be8-116">Selecteer  **onder Groepen** een beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="f7be8-116">Under  **Groups**, select a security group.</span></span>

5. <span data-ttu-id="f7be8-117">Selecteer  **Verwijderen** en selecteer **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="f7be8-117">Select  **Remove**, and select **Save**.</span></span>

## <a name="remove-basic-mobility-and-security-device-policies"></a><span data-ttu-id="f7be8-118">Beleidsregels voor basismobiliteits- en beveiligingsapparaat verwijderen</span><span class="sxs-lookup"><span data-stu-id="f7be8-118">Remove Basic Mobility and Security device policies</span></span>

1.  <span data-ttu-id="f7be8-119">In uw browsertype:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="f7be8-119">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span> 

2.  <span data-ttu-id="f7be8-120">Selecteer een apparaatbeleid en selecteer vervolgens  **Beleid verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="f7be8-120">Select a device policy, and then select  **Delete policy**.</span></span>
    
3.  <span data-ttu-id="f7be8-121">Selecteer ja in het dialoogvenster **Waarschuwing.**</span><span class="sxs-lookup"><span data-stu-id="f7be8-121">In the Warning dialog box, select **Yes**.</span></span>

>[!NOTE]
><span data-ttu-id="f7be8-122">Zie het blogbericht Access Control verwijderen uit Mobile Device Management voor Office 365 voor meer stappen om de blokkering van apparaten te [deblokkeren als](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)uw organisatieapparaten nog steeds in een geblokkeerde staat staan.</span><span class="sxs-lookup"><span data-stu-id="f7be8-122">For more steps to unblock devices if your organization devices are still in a blocked state,  see the blog post [Removing Access Control from Mobile Device Management for Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span></span>
