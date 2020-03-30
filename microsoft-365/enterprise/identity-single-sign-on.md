---
title: 'Stap 10: Gebruikersaanmelding vereenvoudigen'
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
description: Azure Active Directory naadloze SSO begrijpen en configureren
ms.openlocfilehash: 9d18cb559d3a4a9ee401e0f94fb53bc6360d88c8
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2019
ms.locfileid: "42811295"
---
# <a name="step-10-simplify-user-sign-in"></a><span data-ttu-id="ae8d0-103">Stap 10: Gebruikersaanmelding vereenvoudigen</span><span class="sxs-lookup"><span data-stu-id="ae8d0-103">Step 10: Simplify user sign-in</span></span>

<span data-ttu-id="ae8d0-104">*Deze stap is optioneel voor hybride omgevingen en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="ae8d0-104">*This step is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="ae8d0-105">In deze stap stelt u in Azure Active Directory naadloze SSO in om ervoor te zorgen dat uw gebruikers zich kunnen aanmelden bij services die gebruikmaken van Azure Active Directory-gebruikersaccounts zonder dat ze hun wachtwoorden hoeven in te voeren, en in veel gevallen hun gebruikersnamen.</span><span class="sxs-lookup"><span data-stu-id="ae8d0-105">In this step, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO) to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="ae8d0-106">Dit geeft uw gebruikers eenvoudiger toegang tot toepassingen in de cloud, zoals Office 365, zonder extra on-premises onderdelen, zoals identiteitsfederatie servers.</span><span class="sxs-lookup"><span data-stu-id="ae8d0-106">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="ae8d0-107">U configureert Azure Active Directory naadloze SSO met het hulpprogramma Azure Active Directory Connect.</span><span class="sxs-lookup"><span data-stu-id="ae8d0-107">You'll configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="ae8d0-108">Zie [Instructies voor het configureren van Azure Active Directory naadloze SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="ae8d0-108">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="ae8d0-110">Testlabrichtlijn: Azure Active Directory naadloze SSO</span><span class="sxs-lookup"><span data-stu-id="ae8d0-110">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="ae8d0-111">Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-sso) voor deze stap bekijken.</span><span class="sxs-lookup"><span data-stu-id="ae8d0-111">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="ae8d0-112">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="ae8d0-112">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step11.png)| [<span data-ttu-id="ae8d0-113">Aanmeldingspagina voor Office 365 aanpassen</span><span class="sxs-lookup"><span data-stu-id="ae8d0-113">Customize the Office 365 sign-in page</span></span>](identity-customize-office-365-sign-in.md) |

