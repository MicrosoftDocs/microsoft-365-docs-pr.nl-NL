---
title: Beveiligingsinstellingen in- en uit-
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Lees hoe beveiligingsinstellingen uw organisatie kunnen beschermen tegen identiteitsgerelateerde aanvallen door vooraf geconfigureerde beveiligingsinstellingen te bieden.
ms.openlocfilehash: ea36ba45af26a767b08ee1e75931dca54dacea64
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398289"
---
# <a name="turn-on-security-defaults"></a><span data-ttu-id="85cb5-103">Beveiligingsinstellingen in- en uit-</span><span class="sxs-lookup"><span data-stu-id="85cb5-103">Turn on security defaults</span></span>

<span data-ttu-id="85cb5-104">Beveiligingsinstellingen helpen uw organisatie te beschermen tegen identiteitsgerelateerde aanvallen door vooraf geconfigureerde beveiligingsinstellingen te bieden die Microsoft namens uw organisatie beheert.</span><span class="sxs-lookup"><span data-stu-id="85cb5-104">Security defaults help protect your organization from identity-related attacks by providing preconfigured security settings that Microsoft manages on behalf of your organization.</span></span> <span data-ttu-id="85cb5-105">Deze instellingen omvatten het inschakelen van meervoudige verificatie (MFA) voor alle beheerders en gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="85cb5-105">These settings include enabling multi-factor authentication (MFA) for all admins and user accounts.</span></span> <span data-ttu-id="85cb5-106">Voor de meeste organisaties bieden beveiligingsinstellingen een goed niveau van extra aanmeldingsbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="85cb5-106">For most organizations, security defaults offer a good level of additional sign-in security.</span></span>

<span data-ttu-id="85cb5-107">Zie Wat [zijn beveiligings defaults?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) voor meer informatie over beveiligingsinstellingen en het beleid dat ze afdwingen.</span><span class="sxs-lookup"><span data-stu-id="85cb5-107">For more information about security defaults and the policies they enforce, see [What are security defaults?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

<span data-ttu-id="85cb5-108">Als uw abonnement is gemaakt op of na 22 oktober 2019, zijn beveiligingsinstellingen mogelijk automatisch ingeschakeld voor u. Controleer de instellingen om dit te &mdash; bevestigen.</span><span class="sxs-lookup"><span data-stu-id="85cb5-108">If your subscription was created on or after October 22, 2019, security defaults might have been automatically enabled for you&mdash;you should check your settings to confirm.</span></span>

<span data-ttu-id="85cb5-109">Als u beveiligingsinstellingen in uw Azure Active Directory (Azure AD) wilt inschakelen of wilt controleren of deze al zijn ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="85cb5-109">To enable security defaults in your Azure Active Directory (Azure AD) or to check to see if they're already enabled:</span></span>

1. <span data-ttu-id="85cb5-110">Meld u aan bij <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">het Microsoft 365 beheercentrum</a> met globale beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="85cb5-110">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> with Global admin credentials.</span></span>

2. <span data-ttu-id="85cb5-111">Selecteer in het linkerdeelvenster **Alles weergeven en** selecteer vervolgens onder **Beheercentra** **Azure Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="85cb5-111">In the left pane, select **Show All,** and then under **Admin centers**, select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="85cb5-112">Selecteer in het linkerdeelvenster **Azure Active Directory het beheercentrum** **Azure Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="85cb5-112">In the left pane of the **Azure Active Directory admin center,** select **Azure Active Directory**.</span></span>

4. <span data-ttu-id="85cb5-113">Selecteer eigenschappen in het linkermenu van het dashboard in **de** sectie **Beheren.**</span><span class="sxs-lookup"><span data-stu-id="85cb5-113">From the left menu of the Dashboard, in the **Manage** section, select **Properties**.</span></span>

    :::image type="content" source="../media/m365-campaigns-conditional-access/azure-ad-properties.png" alt-text="Schermafbeelding van het Azure Active Directory beheercentrum met de locatie van het menu-item Eigenschappen.":::

5. <span data-ttu-id="85cb5-115">Selecteer onder aan de pagina **Eigenschappen** de optie **Beveiligingsinstellingen beheren.**</span><span class="sxs-lookup"><span data-stu-id="85cb5-115">At the bottom of the **Properties** page, select **Manage Security defaults**.</span></span>

6. <span data-ttu-id="85cb5-116">In het rechterdeelvenster ziet u de standaardinstelling **Beveiliging inschakelen.**</span><span class="sxs-lookup"><span data-stu-id="85cb5-116">In the right pane, you'll see the **Enable Security defaults** setting.</span></span> <span data-ttu-id="85cb5-117">Als **Ja** is geselecteerd, zijn beveiligingsinstellingen al ingeschakeld en is er geen verdere actie vereist.</span><span class="sxs-lookup"><span data-stu-id="85cb5-117">If **Yes** is selected, then security defaults are already enabled and no further action is required.</span></span> <span data-ttu-id="85cb5-118">Als beveiligingsinstellingen momenteel niet zijn ingeschakeld, selecteert u **Ja** om deze in te stellen en selecteert u **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="85cb5-118">If security defaults are not currently enabled, then select **Yes** to enable them, and then select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="85cb5-119">Als u beleidsregels voor voorwaardelijke toegang hebt gebruikt, moet u deze uitschakelen voordat u beveiligingsinstellingen gebruikt.</span><span class="sxs-lookup"><span data-stu-id="85cb5-119">If you've been using Conditional Access policies, you'll need to turn them off before using security defaults.</span></span>
>
> <span data-ttu-id="85cb5-120">U kunt beveiligingsinstellingen of beleidsregels voor Voorwaardelijke toegang gebruiken, maar u kunt beide niet tegelijkertijd gebruiken.</span><span class="sxs-lookup"><span data-stu-id="85cb5-120">You can use either security defaults or Conditional Access policies, but you can't use both at the same time.</span></span>

## <a name="consider-using-conditional-access"></a><span data-ttu-id="85cb5-121">Overweeg Voorwaardelijke toegang te gebruiken</span><span class="sxs-lookup"><span data-stu-id="85cb5-121">Consider using Conditional Access</span></span>

<span data-ttu-id="85cb5-122">Als uw organisatie complexe beveiligingsvereisten heeft of als u meer gedetailleerde controle over uw beveiligingsbeleid nodig hebt, moet u overwegen Voorwaardelijke toegang te gebruiken in plaats van beveiligingsinstellingen om een vergelijkbare of hogere beveiligingsinstelling te bereiken.</span><span class="sxs-lookup"><span data-stu-id="85cb5-122">If your organization has complex security requirements or you need more granular control over your security policies, then you should consider using Conditional Access instead of security defaults to achieve a similar or higher security posture.</span></span> 

<span data-ttu-id="85cb5-123">Met Voorwaardelijke toegang kunt u beleidsregels maken en definiëren die reageren op aanmeldingsgebeurtenissen en aanvullende acties aanvragen voordat een gebruiker toegang krijgt tot een toepassing of service.</span><span class="sxs-lookup"><span data-stu-id="85cb5-123">Conditional Access lets you create and define policies that react to sign-in events and request additional actions before a user is granted access to an application or service.</span></span> <span data-ttu-id="85cb5-124">Beleid voor voorwaardelijke toegang kan gedetailleerd en specifiek zijn, zodat gebruikers overal en altijd productief kunnen zijn, maar ook uw organisatie kunnen beschermen.</span><span class="sxs-lookup"><span data-stu-id="85cb5-124">Conditional Access policies can be granular and specific, empowering users to be productive wherever and whenever, but also protecting your organization.</span></span>

<span data-ttu-id="85cb5-125">Beveiligings defaults zijn beschikbaar voor alle klanten, terwijl voor Voorwaardelijke toegang een licentie is vereist voor een van de volgende abonnementen:</span><span class="sxs-lookup"><span data-stu-id="85cb5-125">Security defaults are available to all customers, while Conditional Access requires a license for one of the following plans:</span></span>

- <span data-ttu-id="85cb5-126">Azure Active Directory Premium P1 of P2</span><span class="sxs-lookup"><span data-stu-id="85cb5-126">Azure Active Directory Premium P1 or P2</span></span>
- <span data-ttu-id="85cb5-127">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="85cb5-127">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="85cb5-128">Microsoft 365 E3 of E5</span><span class="sxs-lookup"><span data-stu-id="85cb5-128">Microsoft 365 E3 or E5</span></span>
- <span data-ttu-id="85cb5-129">Enterprise Mobility & Security E3 of E5</span><span class="sxs-lookup"><span data-stu-id="85cb5-129">Enterprise Mobility & Security E3 or E5</span></span>

<span data-ttu-id="85cb5-130">Als u Voorwaardelijke toegang wilt gebruiken om beleid te configureren dat overeenkomt met beleidsregels die standaard zijn ingeschakeld, raadpleegt u de volgende stapsgewijze handleidingen:</span><span class="sxs-lookup"><span data-stu-id="85cb5-130">If you want to use Conditional Access to configure policies equivalent to those enabled by security defaults, check out the following step-by-step guides:</span></span>

- [<span data-ttu-id="85cb5-131">MFA vereisen voor beheerders</span><span class="sxs-lookup"><span data-stu-id="85cb5-131">Require MFA for administrators</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="85cb5-132">MFA vereisen voor Azure-beheer</span><span class="sxs-lookup"><span data-stu-id="85cb5-132">Require MFA for Azure management</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-azure-management)
- [<span data-ttu-id="85cb5-133">Verouderde verificatie blokkeren</span><span class="sxs-lookup"><span data-stu-id="85cb5-133">Block legacy authentication</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)
- [<span data-ttu-id="85cb5-134">MFA vereisen voor alle gebruikers</span><span class="sxs-lookup"><span data-stu-id="85cb5-134">Require MFA for all users</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- <span data-ttu-id="85cb5-135">[Azure AD MFA-registratie vereisen:](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) hiervoor is Azure AD Identity Protection vereist, dat deel uitmaakt van Azure Active Directory Premium P2</span><span class="sxs-lookup"><span data-stu-id="85cb5-135">[Require Azure AD MFA registration](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) - Requires Azure AD Identity Protection, which is part of Azure Active Directory Premium P2</span></span>

<span data-ttu-id="85cb5-136">Zie Wat [is Voorwaardelijke toegang? voor meer informatie over voorwaardelijke toegang.](/azure/active-directory/conditional-access/overview)</span><span class="sxs-lookup"><span data-stu-id="85cb5-136">To learn more about Conditional Access, see [What is Conditional Access?](/azure/active-directory/conditional-access/overview)</span></span> <span data-ttu-id="85cb5-137">Zie Een beleid voor voorwaardelijke toegang maken voor meer informatie over het maken van beleid voor voorwaardelijke [toegang.](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy)</span><span class="sxs-lookup"><span data-stu-id="85cb5-137">For more information about creating Conditional Access policies, see [Create a Conditional Access policy](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy).</span></span>

> [!NOTE]
> <span data-ttu-id="85cb5-138">Als u een abonnement of licentie hebt met voorwaardelijke toegang, maar nog geen beleid voor voorwaardelijke toegang hebt gemaakt, kunt u beveiligingsinstellingen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="85cb5-138">If you have a plan or license that provides Conditional Access but haven't yet created any Conditional Access policies, you're welcome to use security defaults.</span></span> <span data-ttu-id="85cb5-139">U moet echter beveiligingsinstellingen uitschakelen voordat u beleid voor voorwaardelijke toegang kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="85cb5-139">However, you'll need to turn off security defaults before you can use Conditional Access policies.</span></span>
