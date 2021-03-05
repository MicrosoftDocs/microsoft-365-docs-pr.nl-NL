---
title: Beleidsregels voor voorwaardelijke toegang instellen
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
description: Informatie over het verplicht stellen van MFA en het instellen van beleidsregels voor voorwaardelijke toegang voor Microsoft 365 voor Bedrijven.
ms.openlocfilehash: e16b7f4ff7d215ee749435806be214a807cc60a4
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453667"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a><span data-ttu-id="2ff09-103">Meervoudige verificatie vereisen en beleidsregels voor voorwaardelijke toegang instellen</span><span class="sxs-lookup"><span data-stu-id="2ff09-103">Require multi-factor authentication and set up conditional access policies</span></span>

<span data-ttu-id="2ff09-104">U bebeveiligen de toegang tot uw gegevens met meervoudige verificatie en beleidsregels voor voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="2ff09-104">You protect access to your data with multi-factor authentication and conditional access policies.</span></span> <span data-ttu-id="2ff09-105">Deze leveren aanzienlijke extra beveiliging op.</span><span class="sxs-lookup"><span data-stu-id="2ff09-105">These add substantial additional security.</span></span> <span data-ttu-id="2ff09-106">Microsoft biedt een reeks beleidsregels voor voorwaardelijke toegang volgens de basislijn die voor alle klanten worden aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="2ff09-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="2ff09-107">Basislijnbeleid is een reeks vooraf gedefinieerd beleidsregels die organisaties helpen beschermen tegen veel algemene aanvallen.</span><span class="sxs-lookup"><span data-stu-id="2ff09-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="2ff09-108">Deze algemene aanvallen kunnen wachtwoordaanvallen, herhaling en phishing zijn.</span><span class="sxs-lookup"><span data-stu-id="2ff09-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="2ff09-109">Voor dit beleid moeten beheerders en gebruikers onder bepaalde voorwaarden een tweede vorm van verificatie (meervoudige verificatie of MFA) invoeren.</span><span class="sxs-lookup"><span data-stu-id="2ff09-109">These policies require admins and users to enter a second form of authentication (called multi-factor authentication, or MFA) under certain conditions.</span></span> <span data-ttu-id="2ff09-110">Als een gebruiker in uw organisatie zich bijvoorbeeld probeert aan te melden bij Microsoft 365 vanuit een ander land of een onbekend apparaat, kan het aanmelden als riskant worden beschouwd.</span><span class="sxs-lookup"><span data-stu-id="2ff09-110">For example, if a user in your organization tries to sign in to Microsoft 365 from a different country or from an unknown device, the sign-in might be considered risky.</span></span> <span data-ttu-id="2ff09-111">De gebruiker moet een extra vorm van verificatie bieden (zoals een vingerafdruk of een code) om zijn of haar identiteit te bewijzen.</span><span class="sxs-lookup"><span data-stu-id="2ff09-111">The user must provide an extra form of authentication (such as a fingerprint or a code) to prove their identity.</span></span>

<span data-ttu-id="2ff09-112">Op dit moment bevat het basislijnbeleid de volgende beleidsregels:</span><span class="sxs-lookup"><span data-stu-id="2ff09-112">Currently, the baseline policies include the following policies:</span></span>

- <span data-ttu-id="2ff09-113">Instellen in het Microsoft 365-beheercentrum:</span><span class="sxs-lookup"><span data-stu-id="2ff09-113">Set up in Microsoft 365 admin center:</span></span>
  - <span data-ttu-id="2ff09-114">**MFA vereisen voor beheerders:** meervoudige verificatie is vereist voor de meest bevoegde beheerdersrollen, inclusief globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="2ff09-114">**Require MFA for admins**: Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
  - <span data-ttu-id="2ff09-115">**Beveiliging voor eindgebruikers: meervoudige** verificatie is alleen vereist voor gebruikers wanneer een aanmelding riskant is.</span><span class="sxs-lookup"><span data-stu-id="2ff09-115">**End-user protection**: Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="2ff09-116">Instellen in Azure Active Directory-portal:</span><span class="sxs-lookup"><span data-stu-id="2ff09-116">Set up in Azure Active Directory portal:</span></span>
  - <span data-ttu-id="2ff09-117">**Oude verificatie blokkeren:** oudere client-apps en sommige nieuwe apps maken geen gebruik van nieuwere, veiligere verificatieprotocollen.</span><span class="sxs-lookup"><span data-stu-id="2ff09-117">**Block legacy authentication**: Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="2ff09-118">Met deze oudere apps kan beleid voor voorwaardelijke toegang worden overgeslagen en kan er ongeautoriseerde toegang tot uw omgeving worden verkrijgen.</span><span class="sxs-lookup"><span data-stu-id="2ff09-118">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="2ff09-119">Dit beleid blokkeert toegang van clients die geen ondersteuning bieden voor voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="2ff09-119">This policy blocks access from clients that don't support conditional access.</span></span> 
  - <span data-ttu-id="2ff09-120">**MFA vereisen voor servicebeheer:** meervoudige verificatie vereist voor toegang tot beheerhulpprogramma's, met inbegrip van Azure Portal (waar u basislijnbeleid configureert).</span><span class="sxs-lookup"><span data-stu-id="2ff09-120">**Require MFA for Service Management**: Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span>

<span data-ttu-id="2ff09-121">U wordt aangeraden al deze basislijnbeleidsregels in teschakelen.</span><span class="sxs-lookup"><span data-stu-id="2ff09-121">We recommend that you enable all of these baseline policies.</span></span> <span data-ttu-id="2ff09-122">Nadat dit beleid is ingeschakeld, wordt beheerders en gebruikers gevraagd zich te registreren voor Azure AD Multi-Factor Authentication.</span><span class="sxs-lookup"><span data-stu-id="2ff09-122">After these policies are enabled, admins and users will be prompted to register for Azure AD Multifactor Authentication.</span></span>

<span data-ttu-id="2ff09-123">Zie Wat zijn basislijnbeleidsregels voor meer [informatie over dit beleid?](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)</span><span class="sxs-lookup"><span data-stu-id="2ff09-123">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>

## <a name="require-mfa"></a><span data-ttu-id="2ff09-124">MFA vereisen</span><span class="sxs-lookup"><span data-stu-id="2ff09-124">Require MFA</span></span>

<span data-ttu-id="2ff09-125">Als u wilt dat alle gebruikers zich met een tweede id aanmelden:</span><span class="sxs-lookup"><span data-stu-id="2ff09-125">To require that all users sign in with a second form of ID:</span></span>

1. <span data-ttu-id="2ff09-126">Ga naar het beheercentrum en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> kies **Setup.**</span><span class="sxs-lookup"><span data-stu-id="2ff09-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> and choose **Setup**.</span></span>

2. <span data-ttu-id="2ff09-127">Kies op de pagina Setup de **optie Weergeven** op **de** kaart Aanmelden veiliger maken.</span><span class="sxs-lookup"><span data-stu-id="2ff09-127">On the Setup page, choose **View** in the **Make sign-in more secure** card.</span></span>

    ![Zorg dat u zich beter kunt aanmelden.](../media/setupmfa.png)
3. <span data-ttu-id="2ff09-129">Kies Aan de slag op de pagina Aanmelden veiliger **maken.**</span><span class="sxs-lookup"><span data-stu-id="2ff09-129">On the Make sign-in more secure page, choose **Get started**.</span></span>

4. <span data-ttu-id="2ff09-130">Schakel in het deelvenster **Aanmeldingsbeveiliging** versterken de selectievakjes naast Meervoudige verificatie vereisen voor beheerders in en gebruikers moeten zich registreren voor meervoudige verificatie en toegang blokkeren als er een risico **is** vastgesteld.</span><span class="sxs-lookup"><span data-stu-id="2ff09-130">On the Strengthen sign-in security pane, select the check boxes next to **Require multi-factor authentication for admins** and **Require users to register for multi-factor authentication and block access if risk is detected**.</span></span>
    <span data-ttu-id="2ff09-131">Zorg ervoor dat u het beheerdersaccount [voor noodgevallen](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) of pauzes uitsluit van de MFA-vereiste in het **vak Gebruikers** zoeken.</span><span class="sxs-lookup"><span data-stu-id="2ff09-131">Be sure to exclude the [emergency](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) or "break-glass" admin account from the MFA requirement in the **Find users** box.</span></span>

    ![De beveiligingspagina voor insing verbeteren.](../media/requiremfa.png)

5. <span data-ttu-id="2ff09-133">Kies **Beleid maken** onder aan de pagina.</span><span class="sxs-lookup"><span data-stu-id="2ff09-133">Choose **Create policy** on the bottom of the page.</span></span>

## <a name="set-up-baseline-policies"></a><span data-ttu-id="2ff09-134">Basislijnbeleidsregels instellen</span><span class="sxs-lookup"><span data-stu-id="2ff09-134">Set up baseline policies</span></span>

1. <span data-ttu-id="2ff09-135">Ga naar de [Azure-portal](https://portal.azure.com)en ga naar voorwaardelijke toegang voor **Azure Active** \> **Directory-beveiliging** \> **om** een nieuw **beleid te maken.**</span><span class="sxs-lookup"><span data-stu-id="2ff09-135">Go to the [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Security** \> **Conditional Access** to create a **new policy**.</span></span>

<span data-ttu-id="2ff09-136">Zie de volgende specifieke instructies voor elk beleid:</span><span class="sxs-lookup"><span data-stu-id="2ff09-136">See the following specific instructions for each policy:</span></span> <br>
    - [<span data-ttu-id="2ff09-137">MFA vereisen voor beheerders</span><span class="sxs-lookup"><span data-stu-id="2ff09-137">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators) <br>
    - [<span data-ttu-id="2ff09-138">MFA vereisen voor gebruikers</span><span class="sxs-lookup"><span data-stu-id="2ff09-138">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users) <br>
    - [<span data-ttu-id="2ff09-139">Verouderde verificatie blokkeren</span><span class="sxs-lookup"><span data-stu-id="2ff09-139">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth) <br>
    - [<span data-ttu-id="2ff09-140">MFA vereisen voor servicebeheer</span><span class="sxs-lookup"><span data-stu-id="2ff09-140">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

> [!NOTE]
> <span data-ttu-id="2ff09-141">Preview-beleidsregels bestaan niet meer en gebruikers moeten hun eigen beleid maken.</span><span class="sxs-lookup"><span data-stu-id="2ff09-141">Preview policies no longer exist and users will need to create their own policies.</span></span>

<span data-ttu-id="2ff09-142">U kunt extra beleid instellen, zoals het vereisen van goedgekeurde client-apps.</span><span class="sxs-lookup"><span data-stu-id="2ff09-142">You can set up extra policies, such as requiring approved client apps.</span></span> <span data-ttu-id="2ff09-143">Zie de documentatie voor voorwaardelijke [toegang voor meer informatie.](https://docs.microsoft.com/azure/active-directory/conditional-access/)</span><span class="sxs-lookup"><span data-stu-id="2ff09-143">For more information, see the [Conditional Access documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
