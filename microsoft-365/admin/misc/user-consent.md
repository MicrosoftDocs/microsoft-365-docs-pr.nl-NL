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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: Meer informatie over toestemming van gebruikers voor apps en hoe u deze in kunt stellen om apps van derden toegang te geven tot de Microsoft 365 gebruikersgegevens.
ms.openlocfilehash: 629e64494c6d72a13c3b155370a8f47505e9fa20
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53391229"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a><span data-ttu-id="5dbe3-103">Gebruikers toestemming voor apps beheren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5dbe3-103">Managing user consent to apps in Microsoft 365</span></span>

<span data-ttu-id="5dbe3-104">Met deze instelling bepaalt u of gebruikers die toestemming kunnen geven voor apps die OpenID-Verbinding maken en OAuth 2.0 gebruiken voor aanmelding en aanvragen voor toegang tot gegevens.</span><span class="sxs-lookup"><span data-stu-id="5dbe3-104">This setting controls whether users can give that consent to apps that use OpenID Connect and OAuth 2.0 for sign-in and requests to access data.</span></span> <span data-ttu-id="5dbe3-105">Een app kan worden gemaakt vanuit uw eigen organisatie, of deze kan afkomstig zijn van een andere Office 365 of een externe organisatie.</span><span class="sxs-lookup"><span data-stu-id="5dbe3-105">An app can be created from within your own organization, or it can come from another Office 365 organization or a third-party.</span></span>

<span data-ttu-id="5dbe3-106">Als u deze instelling int, vragen deze apps gebruikers om toestemming voor toegang tot de gegevens van uw organisatie en kunnen gebruikers kiezen of ze deze mogen toestaan.</span><span class="sxs-lookup"><span data-stu-id="5dbe3-106">If you turn this setting on, those apps will ask users for permission to access your organization’s data, and users can choose whether to allow it.</span></span> <span data-ttu-id="5dbe3-107">Als u deze instelling uit schakelen, moeten beheerders toestemming geven voor deze apps voordat gebruikers deze kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="5dbe3-107">If you turn this setting off, then admins must consent to those apps before users may use them.</span></span> <span data-ttu-id="5dbe3-108">In dit geval kunt u overwegen een toestemmingswerkstroom voor beheerders in te stellen in de Azure-portal, zodat gebruikers een aanvraag voor goedkeuring van beheerders kunnen verzenden om een geblokkeerde app te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="5dbe3-108">In this case, consider setting up an admin consent workflow in the Azure portal so users can send a request for admin approval to use any blocked app.</span></span>

<span data-ttu-id="5dbe3-109">Een gebruiker kan alleen toegang geven voor apps waarvan ze de eigenaar zijn en waarvoor toegang tot hun Office 365-gegevens is vereist.</span><span class="sxs-lookup"><span data-stu-id="5dbe3-109">A user can give access only to apps they own that access their Office 365 information.</span></span> <span data-ttu-id="5dbe3-110">Ze kunnen apps geen toestemming geven voor het gebruik van gegevens van anderen.</span><span class="sxs-lookup"><span data-stu-id="5dbe3-110">They can't give an app access to any other user's information.</span></span>

## <a name="turning-user-consent-on-or-off"></a><span data-ttu-id="5dbe3-111">Toestemming van gebruikers in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="5dbe3-111">Turning user consent on or off</span></span>

<span data-ttu-id="5dbe3-112">U kunt als eerste de toestemming van gebruikers voor apps in- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="5dbe3-112">Here's how to turn User consent to apps on or off.</span></span>

1. <span data-ttu-id="5dbe3-113">Ga in het beheercentrum naar de **pagina Instellingen** Instellingen \> **voor Organisaties**  >  [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) en selecteer vervolgens Gebruikers **toestemming voor apps.**</span><span class="sxs-lookup"><span data-stu-id="5dbe3-113">In the admin center, go to the **Settings** \> **Org settings** > [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) page, and then select **User consent to apps**.</span></span>

2. <span data-ttu-id="5dbe3-114">Selecteer op **de pagina Gebruikers toestemming voor apps** de optie om toestemming van gebruikers in of uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="5dbe3-114">On the **User consent to apps** page, select the option to turn user consent on or off.</span></span>

## <a name="related-content"></a><span data-ttu-id="5dbe3-115">Verwante inhoud</span><span class="sxs-lookup"><span data-stu-id="5dbe3-115">Related content</span></span> 

<span data-ttu-id="5dbe3-116">[De werkstroom voor beheerdersmachtiging](/azure/active-directory/manage-apps/configure-admin-consent-workflow) configureren (artikel)</span><span class="sxs-lookup"><span data-stu-id="5dbe3-116">[Configure the admin consent workflow](/azure/active-directory/manage-apps/configure-admin-consent-workflow) (article)</span></span>\
<span data-ttu-id="5dbe3-117">[Toestemming voor toepassingen beheren en toestemmingsaanvragen evalueren](/azure/active-directory/manage-apps/manage-consent-requests) (artikel)</span><span class="sxs-lookup"><span data-stu-id="5dbe3-117">[Managing consent to applications and evaluating consent requests](/azure/active-directory/manage-apps/manage-consent-requests) (article)</span></span>