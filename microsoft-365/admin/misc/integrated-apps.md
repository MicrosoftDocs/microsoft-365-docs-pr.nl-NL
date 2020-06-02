---
title: Toestemming van gebruikers beheren voor apps in Microsoft 365
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
description: Meer informatie over toestemming van gebruikers voor apps en hoe u deze inschakelen om apps van derden toegang te geven tot de Microsoft 365-gegevens van gebruikers.
ms.openlocfilehash: df81d2cf3e1d796e462d2b9240b8288273ed5372
ms.sourcegitcommit: ff1af42b036bfdf75729db8c78f10cf4642616ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/01/2020
ms.locfileid: "44477170"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a><span data-ttu-id="ee9c0-103">Toestemming van gebruikers beheren voor apps in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ee9c0-103">Managing user consent to apps in Microsoft 365</span></span>

<span data-ttu-id="ee9c0-104">Met deze instelling bepaalt u of gebruikers die toestemming kunnen geven aan apps die OpenID Connect en OAuth 2.0 gebruiken voor aanmelding en verzoeken om toegang tot gegevens.</span><span class="sxs-lookup"><span data-stu-id="ee9c0-104">This setting controls whether users can give that consent to apps that use OpenID Connect and OAuth 2.0 for sign-in and requests to access data.</span></span> <span data-ttu-id="ee9c0-105">Een app kan worden gemaakt vanuit uw eigen organisatie, of deze kan afkomstig zijn van een andere Office 365-organisatie of een derde partij.</span><span class="sxs-lookup"><span data-stu-id="ee9c0-105">An app can be created from within your own organization, or it can come from another Office 365 organization or a third-party.</span></span>

<span data-ttu-id="ee9c0-106">Als u deze instelling inschakelt, vragen deze apps gebruikers om toestemming om toegang te krijgen tot de gegevens van uw organisatie en kunnen gebruikers kiezen of ze deze toestaan.</span><span class="sxs-lookup"><span data-stu-id="ee9c0-106">If you turn this setting on, those apps will ask users for permission to access your organization’s data, and users can choose whether to allow it.</span></span> <span data-ttu-id="ee9c0-107">Als u deze instelling uitschakelt, moeten beheerders toestemming geven voor deze apps voordat gebruikers ze kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ee9c0-107">If you turn this setting off, then admins must consent to those apps before users may use them.</span></span> <span data-ttu-id="ee9c0-108">Overweeg in dit geval een workflow voor beheerderstoestemming in te stellen in de Azure-portal, zodat gebruikers een verzoek om goedkeuring van beheerders kunnen verzenden om een geblokkeerde app te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ee9c0-108">In this case, consider setting up an admin consent workflow in the Azure portal so users can send a request for admin approval to use any blocked app.</span></span>

<span data-ttu-id="ee9c0-109">Een gebruiker kan alleen toegang geven voor apps waarvan ze de eigenaar zijn en waarvoor toegang tot hun Office 365-gegevens is vereist.</span><span class="sxs-lookup"><span data-stu-id="ee9c0-109">A user can give access only to apps they own that access their Office 365 information.</span></span> <span data-ttu-id="ee9c0-110">Ze kunnen apps geen toestemming geven voor het gebruik van gegevens van anderen.</span><span class="sxs-lookup"><span data-stu-id="ee9c0-110">They can't give an app access to any other user's information.</span></span>

## <a name="turning-user-consent-on-or-off"></a><span data-ttu-id="ee9c0-111">Toestemming van de gebruiker in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="ee9c0-111">Turning user consent on or off</span></span>
<span data-ttu-id="ee9c0-112"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="ee9c0-112"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="ee9c0-113">Zo schakel je toestemming van gebruikers voor apps in of uit.</span><span class="sxs-lookup"><span data-stu-id="ee9c0-113">Here's how to turn User consent to apps on or off.</span></span>

1. <span data-ttu-id="ee9c0-114">Ga in het beheercentrum naar de pagina **Instellingen** \> **voor**  >  [organisatieservices](https://go.microsoft.com/fwlink/p/?linkid=2053743) en selecteer **vervolgens Toestemming van gebruikers voor apps**.</span><span class="sxs-lookup"><span data-stu-id="ee9c0-114">In the admin center, go to the **Settings** \> **Org settings** > [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) page, and then select **User consent to apps**.</span></span>

2. <span data-ttu-id="ee9c0-115">Selecteer **op** de pagina Toestemming voor apps van gebruiker de optie om Geïntegreerde apps in of uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="ee9c0-115">On the **User consent to apps** page, select the option to turn Integrated Apps on or off.</span></span>

## <a name="more-info"></a><span data-ttu-id="ee9c0-116">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="ee9c0-116">More info</span></span>
<span data-ttu-id="ee9c0-117"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="ee9c0-117"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="ee9c0-118">Lees de werkstroom voor [beheerderstoestemming configureren](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow)voor meer informatie over het configureren van uw toestemmingsinstellingen in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ee9c0-118">To learn about how to configure your consent settings in Azure active directory, read [Configure the admin consent workflow](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow).</span></span>

<span data-ttu-id="ee9c0-119">Lees Toestemming voor toepassingen beheren [en het evalueren van toestemmingsverzoeken](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests)voor meer informatie over het beheren van toestemming voor apps.</span><span class="sxs-lookup"><span data-stu-id="ee9c0-119">To learn about managing user consent to apps, read [Managing consent to applications and evaluating consent requests](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests).</span></span>