---
title: 'Stap 9: Wachtwoordupdates vereenvoudigen'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Lees meer over het terugschrijven van wachtwoorden voor hybride omgevingen.
ms.openlocfilehash: 09679bd732e074ebedac09d1abfce53370610d0c
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2019
ms.locfileid: "42805263"
---
# <a name="step-9-simplify-password-updates"></a><span data-ttu-id="43f56-103">Stap 9: Wachtwoordupdates vereenvoudigen</span><span class="sxs-lookup"><span data-stu-id="43f56-103">Step 9: Simplify password updates</span></span>

<span data-ttu-id="43f56-104">*Deze stap is optioneel voor hybride omgevingen en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="43f56-104">*This step is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="43f56-105">In deze stap laat u gebruikers wachtwoorden opnieuw instellen via Azure Active Directory (AD), die vervolgens worden gerepliceerd naar uw lokale Windows Server Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="43f56-105">In this step, you'll allow users to reset their passwords through Azure Active Directory (AD), which is then replicated to your local Windows Server Active Directory (AD).</span></span> <span data-ttu-id="43f56-106">Dit proces wordt het terugschrijven van wachtwoorden genoemd.</span><span class="sxs-lookup"><span data-stu-id="43f56-106">This process is known as password writeback.</span></span> <span data-ttu-id="43f56-107">Met het terugschrijven van wachtwoorden hoeven gebruikers hun wachtwoorden niet bij te werken via de on-premises Windows Server AD waar de gebruikersaccounts en de bijbehorende kenmerken zijn opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="43f56-107">With password writeback, users don’t need to update their passwords through the on-premises Windows Server AD where user accounts and their attributes are stored.</span></span> <span data-ttu-id="43f56-108">Dit is handig bij roaming en gebruikers die extern werken die geen RAS-verbinding met het on-premises netwerk hebben.</span><span class="sxs-lookup"><span data-stu-id="43f56-108">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="43f56-109">Wachtwoord terugschrijven is vereist om volledig gebruik te kunnen maken van de mogelijkheden van Identity Protection-functies, zoals vereisen dat gebruikers hun on-premises wachtwoorden wijzigen wanneer er een hoog risico op inbreuk van accounts is gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="43f56-109">Password writeback is required to fully utilize Identity Protection feature capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="43f56-110">Zie [Azure AD SSPR met wachtwoord terugschrijven](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback) voor meer informatie en configuratie-instructies.</span><span class="sxs-lookup"><span data-stu-id="43f56-110">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="43f56-111">Voer een upgrade uit naar de nieuwste versie van Azure AD Connect om te zorgen voor een optimale ervaring en nieuwe functies zodra deze beschikbaar komen.</span><span class="sxs-lookup"><span data-stu-id="43f56-111">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released.</span></span> <span data-ttu-id="43f56-112">Zie [Aangepaste installatie van Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="43f56-112">For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>


|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="43f56-114">Testlabrichtlijn: wachtwoord terugschrijven</span><span class="sxs-lookup"><span data-stu-id="43f56-114">Test Lab Guide: Password writeback</span></span>](password-writeback-m365-ent-test-environment.md) |
|||

<span data-ttu-id="43f56-115">Als tussentijds controlepunt kunt u het [afsluitcriterium](identity-exit-criteria.md#crit-identity-pw-writeback) voor deze stap bekijken.</span><span class="sxs-lookup"><span data-stu-id="43f56-115">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-writeback) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="43f56-116">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="43f56-116">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step10.png)| [<span data-ttu-id="43f56-117">Gebruikersaanmelding vereenvoudigen</span><span class="sxs-lookup"><span data-stu-id="43f56-117">Simplify user sign-in</span></span>](identity-single-sign-on.md) |

