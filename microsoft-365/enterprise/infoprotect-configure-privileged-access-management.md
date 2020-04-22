---
title: 'Stap 7: Privileged Access Management configureren'
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Begreep en configureer privileged access management.
ms.openlocfilehash: 4fed4daacc17a34563825bf0575880ce06ec6ebd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636986"
---
# <a name="step-7-configure-privileged-access-management"></a><span data-ttu-id="66fda-103">Stap 7: Privileged Access Management configureren</span><span class="sxs-lookup"><span data-stu-id="66fda-103">Step 7: Configure privileged access management</span></span>

<span data-ttu-id="66fda-104">*Deze stap is optioneel en geldt alleen voor de E5- en Advanced Compliance-versies van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="66fda-104">*This step is optional and applies only to the E5 and Advanced Compliance versions of Microsoft 365 Enterprise*</span></span>

![Fase 6: gegevensbescherming](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="66fda-106">Privileged access management is ingeschakeld door beleid te configureren dat just-in-time toegang opgeeft voor taakgebaseerde activiteiten in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="66fda-106">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your tenant.</span></span> <span data-ttu-id="66fda-107">Deze functie kan helpen uw organisatie te beschermen tegen inbreuken die mogelijk bestaande geprivilegieerde beheerdersaccounts gebruiken met permanente toegang tot gevoelige gegevens of toegang tot belangrijker configuratie-instellingen.</span><span class="sxs-lookup"><span data-stu-id="66fda-107">It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="66fda-108">U bijvoorbeeld een beleid voor beheer van privileged access configureren waarvoor expliciete goedkeuring vereist is voor toegang tot en wijziging van de instellingen van het organisatiepostvak in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="66fda-108">For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your tenant.</span></span>

<span data-ttu-id="66fda-109">In deze stap schakelt u privileged access management in uw tenant in en configureert u beleid voor bevoegde toegang dat extra beveiliging biedt voor taakgebaseerde toegang tot gegevens en configuratie-instellingen voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="66fda-109">In this step, you'll enable privileged access management in your tenant and configure privileged access policies that provide additional security for task-based access to data and configuration settings for your organization.</span></span> <span data-ttu-id="66fda-110">Er zijn drie basisstappen om aan de slag te gaan met bevoorrechte toegang in uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="66fda-110">There are three basic steps to get started with privileged access in your organization:</span></span>
- <span data-ttu-id="66fda-111">Een groep met fiatteurs maken</span><span class="sxs-lookup"><span data-stu-id="66fda-111">Creating an approver's group</span></span>
- <span data-ttu-id="66fda-112">Geprivilegieerde toegang inschakelen</span><span class="sxs-lookup"><span data-stu-id="66fda-112">Enabling privileged access</span></span>
- <span data-ttu-id="66fda-113">Goedkeuringsbeleid maken</span><span class="sxs-lookup"><span data-stu-id="66fda-113">Creating approval policies</span></span>

<span data-ttu-id="66fda-114">Als geprivilegieerd toegangsbeheer is geconfigureerd, kan uw organisatie opereren zonder permanente bevoegdheden en een verdedigingslaag bieden tegen kwetsbaarheden die voortkomen uit dergelijke permanente beheerderstoegang.</span><span class="sxs-lookup"><span data-stu-id="66fda-114">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access.</span></span> <span data-ttu-id="66fda-115">Geprivilegieerde toegang vereist goedkeuring voor het uitvoeren van taken met een bijbehorend goedkeuringsbeleid.</span><span class="sxs-lookup"><span data-stu-id="66fda-115">Privileged access requires approvals for executing any task that has an associated approval policy defined.</span></span> <span data-ttu-id="66fda-116">Gebruikers die taken moeten uitvoeren die zijn opgenomen in het goedkeuringsbeleid, moeten toestemming voor toegang aanvragen en krijgen om de machtigingen te krijgen die nodig zijn om de taken, die zijn gedefinieerd in het beleid, uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="66fda-116">Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="66fda-117">Zie het onderwerp Privileged [Access Management configureren](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) als u privileged access management wilt inschakelen.</span><span class="sxs-lookup"><span data-stu-id="66fda-117">To enable privileged access management, see the [Configure privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="66fda-118">Zie het onderwerp [Privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="66fda-118">For more information, see the [Privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>


|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="66fda-120">Zie de [Testlabrichtlijn geprivilegieerd toegangsbeheer](privileged-access-microsoft-365-enterprise-dev-test-environment.md) om deze configuratie in een testlab-omgeving te oefenen.</span><span class="sxs-lookup"><span data-stu-id="66fda-120">To practice this configuration in a test lab environment, see the [Privileged access management Test Lab Guide](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span></span> |
|||

<span data-ttu-id="66fda-121">Zie de [afsluitcriteria](infoprotect-exit-criteria.md#crit-infoprotect-step7) voor deze stap als tussentijds controlepunt.</span><span class="sxs-lookup"><span data-stu-id="66fda-121">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step7) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="66fda-122">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="66fda-122">Next Step</span></span>

[<span data-ttu-id="66fda-123">Uitgangscriteria voor de infrastructuur voor gegevensbeveiliging</span><span class="sxs-lookup"><span data-stu-id="66fda-123">Information protection infrastructure exit criteria</span></span>](infoprotect-exit-criteria.md)
