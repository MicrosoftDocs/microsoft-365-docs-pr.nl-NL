---
title: 'Stap 8: Synchronisatiestatus bewaken'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Azure AD Connect Health doorgronden en configureren.
ms.openlocfilehash: 21cfd88617bccab3f0a2bdb51c0d320cd4568a56
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2019
ms.locfileid: "42810207"
---
# <a name="step-8-monitor-synchronization-health"></a><span data-ttu-id="fe7c6-103">Stap 8: Synchronisatiestatus bewaken</span><span class="sxs-lookup"><span data-stu-id="fe7c6-103">Step 8: Monitor synchronization health</span></span>

<span data-ttu-id="fe7c6-104">*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="fe7c6-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="fe7c6-105">In deze stap wordt op elke on-premises identiteitsserver een Azure AD Connect Health-agent geïnstalleerd om de identiteitsinfrastructuur en de synchronisatieservices te bewaken die worden geleverd door Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="fe7c6-105">In this step, you'll install an Azure AD Connect Health agent on each of your on-premises identity servers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect.</span></span> <span data-ttu-id="fe7c6-106">De bewakingsinformatie wordt beschikbaar gesteld in een Azure AD Connect Health-portal waar u waarschuwingen, prestatiebewaking, gebruiksanalyses en andere informatie kunt bekijken.</span><span class="sxs-lookup"><span data-stu-id="fe7c6-106">The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

![Componenten van Azure AD Connect Health](./media/identity-azure-ad-connect-health/identity-azure-ad-connect-health.png)

<span data-ttu-id="fe7c6-108">De belangrijkste ontwerpbeslissing over hoe u Azure AD Connect Health gaat gebruiken, is gebaseerd op hoe u Azure AD Connect gebruikt:</span><span class="sxs-lookup"><span data-stu-id="fe7c6-108">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="fe7c6-109">Als u de optie **beheerde verificatie** gebruikt, begint u met [Azure Ad Connect Health gebruiken met synchronisatie](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) om Azure AD Connect Health te doorgronden en te configureren.</span><span class="sxs-lookup"><span data-stu-id="fe7c6-109">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="fe7c6-110">Als u alleen de namen synchroniseert van de accounts en groepen met **federatieve verificatie** met Active Directory Federation Services (AD FS), begint u met [Azure AD Connect Health gebruiken met AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) om Azure AD Connect Health te doorgronden en te configureren.</span><span class="sxs-lookup"><span data-stu-id="fe7c6-110">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="fe7c6-111">Wanneer u deze stap hebt voltooid, hebt u:</span><span class="sxs-lookup"><span data-stu-id="fe7c6-111">When you complete this step, you’ll have:</span></span>

- <span data-ttu-id="fe7c6-112">De Azure AD Connect Health-agent geïnstalleerd op elke on-premises identiteitsserver.</span><span class="sxs-lookup"><span data-stu-id="fe7c6-112">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="fe7c6-113">De Azure AD Connect Health-portal met de huidige status van uw on-premises infrastructuur en synchronisatieactiviteiten met de Azure AD-tenant voor uw Office 365- en EMS-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="fe7c6-113">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Office 365 and EMS subscriptions.</span></span>

<span data-ttu-id="fe7c6-114">Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-sync-health) voor deze stap bekijken.</span><span class="sxs-lookup"><span data-stu-id="fe7c6-114">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync-health) for this step.</span></span>


## <a name="next-step"></a><span data-ttu-id="fe7c6-115">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="fe7c6-115">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step9.png)| [<span data-ttu-id="fe7c6-116">Wachtwoordupdates vereenvoudigen</span><span class="sxs-lookup"><span data-stu-id="fe7c6-116">Simplify password updates</span></span>](identity-password-writeback.md) |

