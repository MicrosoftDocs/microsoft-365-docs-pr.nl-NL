---
title: 'Stap 7: Privileged Access Management configureren voor Office 365'
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
description: Beheer van bevoegde toegang voor Office 365 begrijpen en configureren.
ms.openlocfilehash: f29b1e0934a4b9a6d4e3347584f39423d446ed58
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42808416"
---
# <a name="step-7-configure-privileged-access-management-for-office-365"></a><span data-ttu-id="0189e-103">Stap 7: Privileged Access Management configureren voor Office 365</span><span class="sxs-lookup"><span data-stu-id="0189e-103">Step 7: Configure privileged access management for Office 365</span></span>

<span data-ttu-id="0189e-104">*Deze stap is optioneel en geldt alleen voor de E5- en Advanced Compliance-versies van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="0189e-104">*This step is optional and applies only to the E5 and Advanced Compliance versions of Microsoft 365 Enterprise*</span></span>

![Fase 6: Informatiebescherming](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="0189e-106">Privileged access management is ingeschakeld door beleid te configureren dat just-in-time toegang opgeeft voor taakgebaseerde activiteiten in uw Office 365-tenant.</span><span class="sxs-lookup"><span data-stu-id="0189e-106">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your Office 365 tenant.</span></span> <span data-ttu-id="0189e-107">Het kan uw organisatie beschermen tegen inbreuken die bestaande bevoegde beheerdersaccounts kunnen gebruiken met permanente toegang tot gevoelige gegevens of toegang tot kritieke configuratie-instellingen.</span><span class="sxs-lookup"><span data-stu-id="0189e-107">It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="0189e-108">U bijvoorbeeld een beleid voor beheer van privileged access configureren waarvoor expliciete goedkeuring vereist is voor toegang tot en wijziging van de instellingen van het organalaatpostvak in uw Office 365-tenant.</span><span class="sxs-lookup"><span data-stu-id="0189e-108">For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your Office 365 tenant.</span></span>

<span data-ttu-id="0189e-109">In deze stap schakelt u privileged access management in uw Office 365-tenant in en configureert u beleid voor bevoegde toegang dat extra beveiliging biedt voor taakgebaseerde toegang tot Office 365-gegevens en configuratie-instellingen voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="0189e-109">In this step, you'll enable privileged access management in your Office 365 tenant and configure privileged access policies that provide additional security for task-based access to Office 365 data and configuration settings for your organization.</span></span> <span data-ttu-id="0189e-110">Er zijn drie basisstappen om aan de slag te gaan met bevoorrechte toegang in uw Office 365-organisatie:</span><span class="sxs-lookup"><span data-stu-id="0189e-110">There are three basic steps to get started with privileged access in your Office 365 organization:</span></span>
- <span data-ttu-id="0189e-111">De groep van een goedkeurder maken</span><span class="sxs-lookup"><span data-stu-id="0189e-111">Creating an approver's group</span></span>
- <span data-ttu-id="0189e-112">Bevoorrechte toegang inschakelen</span><span class="sxs-lookup"><span data-stu-id="0189e-112">Enabling privileged access</span></span>
- <span data-ttu-id="0189e-113">Goedkeuringsbeleid maken</span><span class="sxs-lookup"><span data-stu-id="0189e-113">Creating approval policies</span></span>

<span data-ttu-id="0189e-114">Een geconfigureerd, geprivilegieerd toegangsbeheer stelt uw organisatie in staat om te werken met nul permanente bevoegdheden en biedt een laag van verdediging tegen kwetsbaarheden die ontstaan als gevolg van dergelijke permanente administratieve toegang.</span><span class="sxs-lookup"><span data-stu-id="0189e-114">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access.</span></span> <span data-ttu-id="0189e-115">Voor bevoorrechte toegang zijn goedkeuringen vereist voor het uitvoeren van een taak waarvoor een bijbehorend goedkeuringsbeleid is gedefinieerd.</span><span class="sxs-lookup"><span data-stu-id="0189e-115">Privileged access requires approvals for executing any task that has an associated approval policy defined.</span></span> <span data-ttu-id="0189e-116">Gebruikers die taken moeten uitvoeren die zijn opgenomen in het goedkeuringsbeleid, moeten toegangsgoedkeuring aanvragen en krijgen om machtigingen te hebben die nodig zijn om taken uit te voeren die in het beleid zijn gedefinieerd.</span><span class="sxs-lookup"><span data-stu-id="0189e-116">Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="0189e-117">Zie Het onderwerp Privileged Access Management [configureren in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) als u office 365-toegangsbeheer wilt inschakelen.</span><span class="sxs-lookup"><span data-stu-id="0189e-117">To enable Office 365 privileged access management, see the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="0189e-118">Zie het onderwerp [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0189e-118">For more information, see the [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>


|||
|:-------|:-----|
|![Lab-handleidingen testen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="0189e-120">Zie de Test Lab Guide voor [privileged access management](privileged-access-microsoft-365-enterprise-dev-test-environment.md)voor deze configuratie in een testlabomgeving.</span><span class="sxs-lookup"><span data-stu-id="0189e-120">To practice this configuration in a test lab environment, see the [Privileged access management Test Lab Guide](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span></span> |
|||

<span data-ttu-id="0189e-121">Zie als tussencontrole de [exitcriteria](infoprotect-exit-criteria.md#crit-infoprotect-step7) die overeenkomen met deze stap.</span><span class="sxs-lookup"><span data-stu-id="0189e-121">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step7) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="0189e-122">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="0189e-122">Next Step</span></span>

[<span data-ttu-id="0189e-123">Criteria voor het verlaten van informatiebeschermingsinfrastructuur</span><span class="sxs-lookup"><span data-stu-id="0189e-123">Information protection infrastructure exit criteria</span></span>](infoprotect-exit-criteria.md)
