---
title: Gebruikers toestemming voor apps beheren in Microsoft 365
f1.keywords:
- CSH
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: Lees meer over de gebruikers vergunning voor apps en hoe u ze kunt inschakelen om apps van derden toegang te geven tot de Microsoft 365-informatie van gebruikers.
ms.openlocfilehash: 955ae9e58c14dbb8012a440ef6c336f44b0760a4
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999563"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a><span data-ttu-id="ac43a-103">Gebruikers toestemming voor apps beheren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ac43a-103">Managing user consent to apps in Microsoft 365</span></span>

<span data-ttu-id="ac43a-104">Met deze instelling wordt bepaald of gebruikers die toestemming kunnen geven voor apps die gebruikmaken van OpenID Connect en OAuth 2,0 voor aanmelding en verzoeken om toegang tot gegevens.</span><span class="sxs-lookup"><span data-stu-id="ac43a-104">This setting controls whether users can give that consent to apps that use OpenID Connect and OAuth 2.0 for sign-in and requests to access data.</span></span> <span data-ttu-id="ac43a-105">U kunt een app maken vanuit uw eigen organisatie of deze afkomstig zijn van een andere Office 365-organisatie of een derde partij.</span><span class="sxs-lookup"><span data-stu-id="ac43a-105">An app can be created from within your own organization, or it can come from another Office 365 organization or a third-party.</span></span>

<span data-ttu-id="ac43a-106">Als u deze instelling inschakelt, vragen de Apps gebruikers om toegang te krijgen tot de gegevens van uw organisatie, en kunnen gebruikers kiezen of ze dit mogen doen.</span><span class="sxs-lookup"><span data-stu-id="ac43a-106">If you turn this setting on, those apps will ask users for permission to access your organization’s data, and users can choose whether to allow it.</span></span> <span data-ttu-id="ac43a-107">Als u deze instelling uitschakelt, moeten beheerders toestemming verlenen aan deze apps voordat ze ze kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ac43a-107">If you turn this setting off, then admins must consent to those apps before users may use them.</span></span> <span data-ttu-id="ac43a-108">In dit geval kunt u een werkstroom voor het beheer van toestemming van de beheerder instellen voor de Azure-Portal, zodat gebruikers een aanvraag voorgoed keuring van de beheerder kunnen verzenden om een geblokkeerde app te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ac43a-108">In this case, consider setting up an admin consent workflow in the Azure portal so users can send a request for admin approval to use any blocked app.</span></span>

<span data-ttu-id="ac43a-109">Een gebruiker kan alleen toegang geven voor apps waarvan ze de eigenaar zijn en waarvoor toegang tot hun Office 365-gegevens is vereist.</span><span class="sxs-lookup"><span data-stu-id="ac43a-109">A user can give access only to apps they own that access their Office 365 information.</span></span> <span data-ttu-id="ac43a-110">Ze kunnen apps geen toestemming geven voor het gebruik van gegevens van anderen.</span><span class="sxs-lookup"><span data-stu-id="ac43a-110">They can't give an app access to any other user's information.</span></span>

## <a name="turning-user-consent-on-or-off"></a><span data-ttu-id="ac43a-111">Toestemming verlenen om gebruikers in of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="ac43a-111">Turning user consent on or off</span></span>
<span data-ttu-id="ac43a-112"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="ac43a-112"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="ac43a-113">Ga als volgt te werk om gebruikers toestemming voor apps in of uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="ac43a-113">Here's how to turn User consent to apps on or off.</span></span>

1. <span data-ttu-id="ac43a-114">Ga in het Beheercentrum naar de pagina **instellingen** voor de services voor \> **organisatie**  >  [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) -instellingen en selecteer **gebruikers instemming met apps**.</span><span class="sxs-lookup"><span data-stu-id="ac43a-114">In the admin center, go to the **Settings** \> **Org settings** > [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) page, and then select **User consent to apps**.</span></span>

2. <span data-ttu-id="ac43a-115">Selecteer op de pagina **gebruikers toestemming voor apps** de optie om toestemming van de gebruiker in of uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="ac43a-115">On the **User consent to apps** page, select the option to turn user consent on or off.</span></span>

## <a name="more-info"></a><span data-ttu-id="ac43a-116">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="ac43a-116">More info</span></span>
<span data-ttu-id="ac43a-117"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="ac43a-117"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="ac43a-118">Zie [de werkstroom voor het beheer van de beheerder configureren](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow)voor meer informatie over het configureren van de instellingen voor toestemming in azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ac43a-118">To learn about how to configure your consent settings in Azure active directory, read [Configure the admin consent workflow](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow).</span></span>

<span data-ttu-id="ac43a-119">Voor meer informatie over het beheren van gebruikers toestemming voor apps raadpleegt [u de instemming met toepassingen beheren en verzoeken om toestemming te beoordelen](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests).</span><span class="sxs-lookup"><span data-stu-id="ac43a-119">To learn about managing user consent to apps, read [Managing consent to applications and evaluating consent requests](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests).</span></span>