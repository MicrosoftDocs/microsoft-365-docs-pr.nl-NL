---
title: Beleid voor voorwaardelijke toegang instellen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
description: Meer informatie over het vereisen van MFA en het instellen van beleid voor voorwaardelijke toegang voor Microsoft 365 voor bedrijven.
ms.openlocfilehash: 917fb52eb5034c3dda28c277b9e86e04db6cac62
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527196"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a><span data-ttu-id="8cbe3-103">Multi-factor authenticatie vereisen en beleid voor voorwaardelijke toegang instellen</span><span class="sxs-lookup"><span data-stu-id="8cbe3-103">Require multi-factor authentication and set up conditional access policies</span></span>

<span data-ttu-id="8cbe3-104">U beschermt de toegang tot uw gegevens met meervoudige verificatie en beleid voor voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="8cbe3-104">You protect access to your data with multi-factor authentication and conditional access policies.</span></span> <span data-ttu-id="8cbe3-105">Deze voegen aanzienlijke extra beveiliging toe.</span><span class="sxs-lookup"><span data-stu-id="8cbe3-105">These add substantial additional security.</span></span> <span data-ttu-id="8cbe3-106">Microsoft biedt een set basislijnvoorwaarden voor voorwaardelijke toegang die voor alle klanten worden aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="8cbe3-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="8cbe3-107">Basislijnbeleid is een set vooraf gedefinieerde beleidsregels die organisaties helpen beschermen tegen veel voorkomende aanvallen.</span><span class="sxs-lookup"><span data-stu-id="8cbe3-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="8cbe3-108">Deze veelvoorkomende aanvallen kunnen wachtwoordspray, herhaling en phishing omvatten.</span><span class="sxs-lookup"><span data-stu-id="8cbe3-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="8cbe3-109">Dit beleid vereist dat beheerders en gebruikers een tweede vorm van verificatie invoeren (multi-factor authenticatie of MFA genoemd) wanneer aan bepaalde voorwaarden is voldaan.</span><span class="sxs-lookup"><span data-stu-id="8cbe3-109">These policies require admins and users to enter a second form of authentication (called multi-factor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="8cbe3-110">Als een gebruiker in uw organisatie zich bijvoorbeeld probeert aan te melden bij Microsoft 365 vanuit een ander land of vanaf een onbekend apparaat, kan de aanmelding als riskant worden beschouwd.</span><span class="sxs-lookup"><span data-stu-id="8cbe3-110">For example, if a user in your organization tries to sign in to Microsoft 365 from a different country or from an unknown device, the sign-in might be considered risky.</span></span> <span data-ttu-id="8cbe3-111">De gebruiker moet een extra vorm van authenticatie (zoals een vingerafdruk of een code) om hun identiteit te bewijzen.</span><span class="sxs-lookup"><span data-stu-id="8cbe3-111">The user must provide an extra form of authentication (such as a fingerprint or a code) to prove their identity.</span></span> 

<span data-ttu-id="8cbe3-112">Momenteel omvatten basislijnbeleid het volgende:</span><span class="sxs-lookup"><span data-stu-id="8cbe3-112">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="8cbe3-113">Instellen in microsoft 365-beheercentrum:</span><span class="sxs-lookup"><span data-stu-id="8cbe3-113">Set up in Microsoft 365 admin center:</span></span>
    - <span data-ttu-id="8cbe3-114">**MFA vereisen voor beheerders** : vereist meervoudige verificatie voor de meest bevoorrechte beheerdersrollen, inclusief globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="8cbe3-114">**Require MFA for admins** — Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
    - <span data-ttu-id="8cbe3-115">**Beveiliging van eindgebruikers** : vereist meervoudige verificatie voor gebruikers alleen wanneer een aanmelding riskant is.</span><span class="sxs-lookup"><span data-stu-id="8cbe3-115">**End user protection** — Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="8cbe3-116">Instellen in Azure Active Directory-portal:</span><span class="sxs-lookup"><span data-stu-id="8cbe3-116">Set up in Azure Active Directory portal:</span></span>
    - <span data-ttu-id="8cbe3-117">**Verouderde verificatie blokkeren** - Oudere client-apps en sommige nieuwe apps gebruiken geen nieuwere, veiligere verificatieprotocollen.</span><span class="sxs-lookup"><span data-stu-id="8cbe3-117">**Block legacy authentication** — Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="8cbe3-118">Deze oudere apps kunnen het beleid voor voorwaardelijke toegang omzeilen en ongeautoriseerde toegang tot uw omgeving krijgen.</span><span class="sxs-lookup"><span data-stu-id="8cbe3-118">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="8cbe3-119">Dit beleid blokkeert de toegang van clients die geen voorwaardelijke toegang ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="8cbe3-119">This policy blocks access from clients that don't support conditional access.</span></span> 
    - <span data-ttu-id="8cbe3-120">**MFA vereisen voor servicebeheer** : vereist meervoudige verificatie voor toegang tot beheerhulpprogramma's, waaronder Azure-portal (waar u basislijnbeleid configureert).</span><span class="sxs-lookup"><span data-stu-id="8cbe3-120">**Require MFA for Service Management** — Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="8cbe3-121">Microsoft raadt u aan al deze basislijnbeleid in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="8cbe3-121">Microsoft recommends that you enable all of these baseline policies.</span></span> <span data-ttu-id="8cbe3-122">Nadat dit beleid is ingeschakeld, worden beheerders en gebruikers gevraagd zich te registreren voor Azure Multi-Factor-verificatie.</span><span class="sxs-lookup"><span data-stu-id="8cbe3-122">After these policies are enabled, admins and users will be prompted to register for Azure Multi-Factor authentication.</span></span>

<span data-ttu-id="8cbe3-123">Zie [Wat zijn basislijnbeleid voor](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)meer informatie over dit beleid?</span><span class="sxs-lookup"><span data-stu-id="8cbe3-123">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="require-mfa"></a><span data-ttu-id="8cbe3-124">MFA vereisen</span><span class="sxs-lookup"><span data-stu-id="8cbe3-124">Require MFA</span></span>

<span data-ttu-id="8cbe3-125">Als u wilt dat alle gebruikers zich aanmelden met een tweede formulier id:</span><span class="sxs-lookup"><span data-stu-id="8cbe3-125">To require that all users sign in with a second form of ID:</span></span>

1. <span data-ttu-id="8cbe3-126">Ga naar het beheercentrum bij <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> en kies **Setup**.</span><span class="sxs-lookup"><span data-stu-id="8cbe3-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> and choose **Setup**.</span></span>

2. <span data-ttu-id="8cbe3-127">Kies op de pagina Setup de optie **Weergave** in de **aanmeldingskaart Maken.**</span><span class="sxs-lookup"><span data-stu-id="8cbe3-127">On the Setup page, choose **View** in the **Make sign-in more secure** card.</span></span>


    ![Maak aanmelden veiliger kaart.](../media/setupmfa.png)
3. <span data-ttu-id="8cbe3-129">Kies op de pagina Aanmelden veiliger maken de optie **Aan de slag**.</span><span class="sxs-lookup"><span data-stu-id="8cbe3-129">On the Make sign-in more secure page, choose **Get started**.</span></span>
 
4. <span data-ttu-id="8cbe3-130">Schakel in het beveiligingsvenster Aanmelding versterken de selectievakjes naast **Meervoudige verificatie vereisen voor beheerders** in en gebruikers **verplichten zich te registreren voor meervoudige verificatie en toegang te blokkeren als er risico's worden gedetecteerd.**</span><span class="sxs-lookup"><span data-stu-id="8cbe3-130">On the Strengthen sign-in security pane, select the check boxes next to **Require multi-factor authentication for admins** and **Require users to register for multi-factor authentication and block access if risk is detected**.</span></span>
    <span data-ttu-id="8cbe3-131">Zorg ervoor dat u het [nood-](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) of "break-glass"-beheerdersaccount uitsluit van de MFA-eis in het vak **Gebruikers zoeken.**</span><span class="sxs-lookup"><span data-stu-id="8cbe3-131">Be sure to exclude the [emergency](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) or "break-glass" admin account from the MFA requirement in the **Find users** box.</span></span>
    
    ![Versterking van de beveiligingspagina voor zingen.](../media/requiremfa.png)

5. <span data-ttu-id="8cbe3-133">Kies **Beleid maken** onder aan de pagina.</span><span class="sxs-lookup"><span data-stu-id="8cbe3-133">Choose **Create policy** on the bottom of the page.</span></span>

## <a name="set-up-baseline-policies"></a><span data-ttu-id="8cbe3-134">Basislijnbeleid instellen</span><span class="sxs-lookup"><span data-stu-id="8cbe3-134">Set up baseline policies</span></span>

1. <span data-ttu-id="8cbe3-135">Ga naar [Azure-portal](https://portal.azure.com)en navigeer naar **Azure Active Directory** Voorwaardelijke \> **toegang**.</span><span class="sxs-lookup"><span data-stu-id="8cbe3-135">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="8cbe3-136">Het basislijnbeleid wordt op de pagina weergegeven en u zien dat **MFA vereisen voor beheerders** en beveiliging van **eindgebruikers** al zijn ingeschakeld nadat u de stappen hebt voltooid [waarin MFA vereist](#require-mfa)is.</span><span class="sxs-lookup"><span data-stu-id="8cbe3-136">The baseline policies are listed on the page, and you can see that **Require MFA for admins** and **End user protection** are already enabled after you completed the steps in [require MFA](#require-mfa).</span></span>

    ![Pagina met basislijnbeleid voor voorwaardelijke toegang.](../media/casettings.png)
2. <span data-ttu-id="8cbe3-138">Zie de volgende specifieke instructies voor elk beleid:</span><span class="sxs-lookup"><span data-stu-id="8cbe3-138">See the following specific instructions for each policy:</span></span>

    - [<span data-ttu-id="8cbe3-139">MFA nodig voor beheerders</span><span class="sxs-lookup"><span data-stu-id="8cbe3-139">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
    - [<span data-ttu-id="8cbe3-140">MFA vereisen voor gebruikers</span><span class="sxs-lookup"><span data-stu-id="8cbe3-140">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
    - [<span data-ttu-id="8cbe3-141">Verouderde verificatie blokkeren</span><span class="sxs-lookup"><span data-stu-id="8cbe3-141">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
    - [<span data-ttu-id="8cbe3-142">MFA vereisen voor servicebeheer</span><span class="sxs-lookup"><span data-stu-id="8cbe3-142">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="8cbe3-143">U extra beleidsregels instellen, zoals het vereisen van goedgekeurde client-apps.</span><span class="sxs-lookup"><span data-stu-id="8cbe3-143">You can set up extra policies, such as requiring approved client apps.</span></span> <span data-ttu-id="8cbe3-144">Zie de documentatie [voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/)voor meer informatie .</span><span class="sxs-lookup"><span data-stu-id="8cbe3-144">For more information, see the [Conditional Access documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
