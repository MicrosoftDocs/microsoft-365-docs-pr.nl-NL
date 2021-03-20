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
description: Meer informatie over het vereisen van MFA en het instellen van beleid voor voorwaardelijke toegang voor Microsoft 365 voor Bedrijven.
ms.openlocfilehash: dcb79ed060dd15fd288cdcfb9e3739a788f5fbc2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912184"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a><span data-ttu-id="492ac-103">Meervoudige verificatie vereisen en beleid voor voorwaardelijke toegang instellen</span><span class="sxs-lookup"><span data-stu-id="492ac-103">Require multi-factor authentication and set up conditional access policies</span></span>

<span data-ttu-id="492ac-104">U beschermt de toegang tot uw gegevens met meervoudige verificatie en beleid voor voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="492ac-104">You protect access to your data with multi-factor authentication and conditional access policies.</span></span> <span data-ttu-id="492ac-105">Deze bieden aanzienlijke extra beveiliging.</span><span class="sxs-lookup"><span data-stu-id="492ac-105">These add substantial additional security.</span></span> <span data-ttu-id="492ac-106">Microsoft biedt een set beleidsregels voor basislijn voorwaardelijke toegang die worden aanbevolen voor alle klanten.</span><span class="sxs-lookup"><span data-stu-id="492ac-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="492ac-107">Basislijnbeleid is een set vooraf gedefinieerde beleidsregels die organisaties helpen beschermen tegen veelvoorkomende aanvallen.</span><span class="sxs-lookup"><span data-stu-id="492ac-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="492ac-108">Deze veelvoorkomende aanvallen kunnen wachtwoordsproeien, herhalen en phishing zijn.</span><span class="sxs-lookup"><span data-stu-id="492ac-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="492ac-109">Voor dit beleid moeten beheerders en gebruikers onder bepaalde voorwaarden een tweede vorm van verificatie invoeren (meervoudige verificatie of MFA genoemd).</span><span class="sxs-lookup"><span data-stu-id="492ac-109">These policies require admins and users to enter a second form of authentication (called multi-factor authentication, or MFA) under certain conditions.</span></span> <span data-ttu-id="492ac-110">Als een gebruiker in uw organisatie zich bijvoorbeeld probeert aan te melden bij Microsoft 365 vanuit een ander land of vanaf een onbekend apparaat, kan de aanmelding als riskant worden beschouwd.</span><span class="sxs-lookup"><span data-stu-id="492ac-110">For example, if a user in your organization tries to sign in to Microsoft 365 from a different country or from an unknown device, the sign-in might be considered risky.</span></span> <span data-ttu-id="492ac-111">De gebruiker moet een extra vorm van verificatie (zoals een vingerafdruk of een code) verstrekken om zijn of haar identiteit te bewijzen.</span><span class="sxs-lookup"><span data-stu-id="492ac-111">The user must provide an extra form of authentication (such as a fingerprint or a code) to prove their identity.</span></span>

<span data-ttu-id="492ac-112">Op dit moment bevat het basislijnbeleid de volgende beleidsregels:</span><span class="sxs-lookup"><span data-stu-id="492ac-112">Currently, the baseline policies include the following policies:</span></span>

- <span data-ttu-id="492ac-113">Instellen in microsoft 365-beheercentrum:</span><span class="sxs-lookup"><span data-stu-id="492ac-113">Set up in Microsoft 365 admin center:</span></span>
  - <span data-ttu-id="492ac-114">**MFA vereisen voor beheerders:** vereist meervoudige verificatie voor de meest bevoorrechte beheerdersrollen, inclusief globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="492ac-114">**Require MFA for admins**: Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
  - <span data-ttu-id="492ac-115">**Beveiliging van eindgebruikers:** meervoudige verificatie is alleen vereist voor gebruikers wanneer een aanmelding riskant is.</span><span class="sxs-lookup"><span data-stu-id="492ac-115">**End-user protection**: Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="492ac-116">Instellen in de Azure Active Directory-portal:</span><span class="sxs-lookup"><span data-stu-id="492ac-116">Set up in Azure Active Directory portal:</span></span>
  - <span data-ttu-id="492ac-117">**Oudere verificatie blokkeren:** oudere client-apps en sommige nieuwe apps gebruiken geen nieuwere, veiligere verificatieprotocollen.</span><span class="sxs-lookup"><span data-stu-id="492ac-117">**Block legacy authentication**: Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="492ac-118">Deze oudere apps kunnen beleidsregels voor voorwaardelijke toegang omzeilen en ongeautoriseerde toegang krijgen tot uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="492ac-118">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="492ac-119">Dit beleid blokkeert toegang van clients die geen ondersteuning bieden voor voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="492ac-119">This policy blocks access from clients that don't support conditional access.</span></span> 
  - <span data-ttu-id="492ac-120">**MFA vereisen voor servicebeheer:** vereist meervoudige verificatie voor toegang tot beheerhulpmiddelen, waaronder Azure Portal (waar u basislijnbeleid configureert).</span><span class="sxs-lookup"><span data-stu-id="492ac-120">**Require MFA for Service Management**: Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span>

<span data-ttu-id="492ac-121">U wordt aangeraden al deze basislijnbeleidsregels in te stellen.</span><span class="sxs-lookup"><span data-stu-id="492ac-121">We recommend that you enable all of these baseline policies.</span></span> <span data-ttu-id="492ac-122">Nadat dit beleid is ingeschakeld, worden beheerders en gebruikers gevraagd zich te registreren voor Azure AD Multifactor Authentication.</span><span class="sxs-lookup"><span data-stu-id="492ac-122">After these policies are enabled, admins and users will be prompted to register for Azure AD Multifactor Authentication.</span></span>

<span data-ttu-id="492ac-123">Zie Wat zijn basislijnbeleid? voor [meer informatie over dit beleid.](/azure/active-directory/conditional-access/concept-baseline-protection)</span><span class="sxs-lookup"><span data-stu-id="492ac-123">For more information about these policies, see [What are baseline policies](/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>

## <a name="require-mfa"></a><span data-ttu-id="492ac-124">MFA vereisen</span><span class="sxs-lookup"><span data-stu-id="492ac-124">Require MFA</span></span>

<span data-ttu-id="492ac-125">Als u wilt dat alle gebruikers zich aanmelden met een tweede id-formulier:</span><span class="sxs-lookup"><span data-stu-id="492ac-125">To require that all users sign in with a second form of ID:</span></span>

1. <span data-ttu-id="492ac-126">Ga naar het beheercentrum bij <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> en kies **Setup.**</span><span class="sxs-lookup"><span data-stu-id="492ac-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> and choose **Setup**.</span></span>

2. <span data-ttu-id="492ac-127">Kies op de pagina Setup **de optie Weergeven** in de **aanmeldingskaart veiliger** maken.</span><span class="sxs-lookup"><span data-stu-id="492ac-127">On the Setup page, choose **View** in the **Make sign-in more secure** card.</span></span>

    ![Maak aanmelding veiliger.](../media/setupmfa.png)
3. <span data-ttu-id="492ac-129">Kies op de pagina Aanmelden veiliger maken de optie **Aan de slag.**</span><span class="sxs-lookup"><span data-stu-id="492ac-129">On the Make sign-in more secure page, choose **Get started**.</span></span>

4. <span data-ttu-id="492ac-130">Schakel in het deelvenster **Aanmeldingsbeveiliging** versterken de selectievakjes in naast Meervoudige verificatie vereisen voor beheerders en Gebruikers verplichten zich te registreren voor meervoudige verificatie en toegang te blokkeren als er risico **wordt gedetecteerd.**</span><span class="sxs-lookup"><span data-stu-id="492ac-130">On the Strengthen sign-in security pane, select the check boxes next to **Require multi-factor authentication for admins** and **Require users to register for multi-factor authentication and block access if risk is detected**.</span></span>
    <span data-ttu-id="492ac-131">Zorg ervoor dat u het beheerdersaccount [voor](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) noodgevallen of 'break-glass' uitsluit van de MFA-vereiste in **het vak Gebruikers zoeken.**</span><span class="sxs-lookup"><span data-stu-id="492ac-131">Be sure to exclude the [emergency](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) or "break-glass" admin account from the MFA requirement in the **Find users** box.</span></span>

    ![De beveiligingspagina voor sing-in versterken.](../media/requiremfa.png)

5. <span data-ttu-id="492ac-133">Kies **Beleid maken** onder aan de pagina.</span><span class="sxs-lookup"><span data-stu-id="492ac-133">Choose **Create policy** on the bottom of the page.</span></span>

## <a name="set-up-baseline-policies"></a><span data-ttu-id="492ac-134">Basislijnbeleid instellen</span><span class="sxs-lookup"><span data-stu-id="492ac-134">Set up baseline policies</span></span>

1. <span data-ttu-id="492ac-135">Ga naar de [Azure-portal](https://portal.azure.com)en ga vervolgens naar **voorwaardelijke toegang** voor Azure Active \> **Directory-beveiliging** \>  om een nieuw beleid **te maken.**</span><span class="sxs-lookup"><span data-stu-id="492ac-135">Go to the [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Security** \> **Conditional Access** to create a **new policy**.</span></span>

<span data-ttu-id="492ac-136">Zie de volgende specifieke instructies voor elk beleid:</span><span class="sxs-lookup"><span data-stu-id="492ac-136">See the following specific instructions for each policy:</span></span> <br>
    - [<span data-ttu-id="492ac-137">MFA vereisen voor beheerders</span><span class="sxs-lookup"><span data-stu-id="492ac-137">Require MFA for admins</span></span>](/azure/active-directory/conditional-access/howto-baseline-protect-administrators) <br>
    - [<span data-ttu-id="492ac-138">MFA vereisen voor gebruikers</span><span class="sxs-lookup"><span data-stu-id="492ac-138">Require MFA for users</span></span>](/azure/active-directory/conditional-access/howto-baseline-protect-end-users) <br>
    - [<span data-ttu-id="492ac-139">Verouderde verificatie blokkeren</span><span class="sxs-lookup"><span data-stu-id="492ac-139">Block legacy authentication</span></span>](/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth) <br>
    - [<span data-ttu-id="492ac-140">MFA vereisen voor servicebeheer</span><span class="sxs-lookup"><span data-stu-id="492ac-140">Require MFA for service management</span></span>](/azure/active-directory/conditional-access/howto-baseline-protect-azure)

> [!NOTE]
> <span data-ttu-id="492ac-141">Voorbeeldbeleid bestaat niet meer en gebruikers moeten hun eigen beleid maken.</span><span class="sxs-lookup"><span data-stu-id="492ac-141">Preview policies no longer exist and users will need to create their own policies.</span></span>

<span data-ttu-id="492ac-142">U kunt extra beleid instellen, zoals het vereisen van goedgekeurde client-apps.</span><span class="sxs-lookup"><span data-stu-id="492ac-142">You can set up extra policies, such as requiring approved client apps.</span></span> <span data-ttu-id="492ac-143">Zie de documentatie voor Voorwaardelijke toegang voor [meer informatie.](/azure/active-directory/conditional-access/)</span><span class="sxs-lookup"><span data-stu-id="492ac-143">For more information, see the [Conditional Access documentation](/azure/active-directory/conditional-access/).</span></span>