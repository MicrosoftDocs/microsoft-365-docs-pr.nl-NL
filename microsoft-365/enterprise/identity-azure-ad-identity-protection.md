---
title: 'Stap 6: bescherming tegen inbreuk op referenties'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Lees meer over en configureer Azure AD Identity Protection.
ms.openlocfilehash: b1dea9d2917c45bf87bd972f56c9eac2b074c252
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2019
ms.locfileid: "42810922"
---
# <a name="step-6-protect-against-credential-compromise"></a><span data-ttu-id="d23bf-103">Stap 6: bescherming tegen inbreuk op referenties</span><span class="sxs-lookup"><span data-stu-id="d23bf-103">Step 6: Protect against credential compromise</span></span>

<span data-ttu-id="d23bf-104">*Deze stap is optioneel en geldt voor alleen voor de E5-versie van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="d23bf-104">*This step is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="d23bf-105">In deze stap leert u hoe u beleidsregels configureert die bescherming bieden tegen inbreuken op referenties, waarbij een kwaadwillende gebruiker een aanval uitvoert op de accountnaam en wachtwoord van een gebruiker om toegang te krijgen tot de cloudservices en gegevens van een organisatie.</span><span class="sxs-lookup"><span data-stu-id="d23bf-105">In this step, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> <span data-ttu-id="d23bf-106">Azure AD Identity Protection biedt verschillende manieren om te voorkomen dat een kwaadwillende gebruiker uw accounts en groepen doorzoekt en vervolgens terecht komt bij uw meest waardevolle gegevens.</span><span class="sxs-lookup"><span data-stu-id="d23bf-106">Azure AD Identity Protection provides a number of ways to help prevent an attacker from moving laterally through your accounts and groups, and subsequently, to your most valuable data.</span></span>

<span data-ttu-id="d23bf-107">Met Azure AD Identity Protection kunt u:</span><span class="sxs-lookup"><span data-stu-id="d23bf-107">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="d23bf-108">Mogelijke beveiligingslekken in de identiteiten van uw organisatie vaststellen en verhelpen</span><span class="sxs-lookup"><span data-stu-id="d23bf-108">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="d23bf-109">Azure AD maakt gebruik van machine learning om afwijkingen en verdachte activiteiten te ontdekken, zoals aanmeldingen en activiteiten na aanmelding.</span><span class="sxs-lookup"><span data-stu-id="d23bf-109">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities.</span></span> <span data-ttu-id="d23bf-110">Met deze gegevens genereert identiteitsbescherming rapporten en waarschuwingen om u te helpen bij het evalueren van problemen en het ondernemen van actie. </span><span class="sxs-lookup"><span data-stu-id="d23bf-110">Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="d23bf-111">Verdachte acties opsporen die zijn gerelateerd aan de identiteiten van uw organisatie en automatisch op deze acties te reageren</span><span class="sxs-lookup"><span data-stu-id="d23bf-111">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="d23bf-112">U kunt beleidsregels met betrekking tot risicobeheer zodanig configureren dat deze automatisch reageren op opgespoorde problemen als een bepaald risiconiveau is bereikt.</span><span class="sxs-lookup"><span data-stu-id="d23bf-112">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached.</span></span> <span data-ttu-id="d23bf-113">Met deze beleidsregels kunt u naast andere besturingselementen voor voorwaardelijke toegang die worden geboden door Azure Active Directory en Enterprise Mobility + Security (EMS), de toegang automatisch blokkeren of corrigerende acties ondernemen, waaronder wachtwoordherstel en vereiste meervoudige verificatie voor volgende aanmeldingen.</span><span class="sxs-lookup"><span data-stu-id="d23bf-113">These policies, in addition to other conditional access controls provided by Azure Active Directory and Enterprise Mobility + Security (EMS), can either automatically block access or take corrective actions, including password resets and requiring multi-factor authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="d23bf-114">Verdachte incidenten onderzoeken en deze oplossen met beheertaken</span><span class="sxs-lookup"><span data-stu-id="d23bf-114">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="d23bf-115">U kunt risico gebeurtenissen onderzoeken door informatie over het beveiligingsincident te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d23bf-115">You can investigate risk events using information about the security incident.</span></span> <span data-ttu-id="d23bf-116">Er zijn eenvoudige werkstromen beschikbaar om onderzoek bij te houden en herstelbewerkingen uit te voeren, zoals het opnieuw instellen van wachtwoorden.</span><span class="sxs-lookup"><span data-stu-id="d23bf-116">Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="d23bf-117">Zie [meer informatie over Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span><span class="sxs-lookup"><span data-stu-id="d23bf-117">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="d23bf-118">Zie de [stappen voor het inschakelen van de Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span><span class="sxs-lookup"><span data-stu-id="d23bf-118">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="d23bf-119">Het resultaat van deze stap is dat de Azure AD Identity Protection is ingeschakeld en u deze gebruikt voor het volgende:</span><span class="sxs-lookup"><span data-stu-id="d23bf-119">The results of this step are that you've enabled Azure AD Identity protection and you are using it to:</span></span>

- <span data-ttu-id="d23bf-120">Mogelijke beveiligingslekken met een identiteit oplossen.</span><span class="sxs-lookup"><span data-stu-id="d23bf-120">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="d23bf-121">Mogelijke inbreuk op referenties opsporen.</span><span class="sxs-lookup"><span data-stu-id="d23bf-121">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="d23bf-122">Het onderzoeken en adresseren van voortdurende verdachte identiteitsincidenten.</span><span class="sxs-lookup"><span data-stu-id="d23bf-122">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Labrichtlijnen testen voor de Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="d23bf-124">Labrichtlijnen testen: Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="d23bf-124">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="d23bf-125">Als tussentijds controlepunt kunt u het [afsluitcriterium](identity-exit-criteria.md#crit-identity-ident-prot) voor deze stap bekijken.</span><span class="sxs-lookup"><span data-stu-id="d23bf-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="d23bf-126">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="d23bf-126">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step7.png)| [<span data-ttu-id="d23bf-127">Mappen synchroniseren</span><span class="sxs-lookup"><span data-stu-id="d23bf-127">Synchronize directories</span></span>](identity-azure-ad-connect.md) |


