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
description: Meer informatie over hoe u MFA moet vereisen en regels voor voorwaardelijke toegang voor Microsoft 365 voor bedrijven kunt instellen.
ms.openlocfilehash: 5908a36f09753cd8f66169c6a67be45c748807b7
ms.sourcegitcommit: 34ebec8e2bd54ba3d4ccfd9724797665c965c17f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071499"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a><span data-ttu-id="5e802-103">Meervoudige verificatie vereisen en beleid voor voorwaardelijke toegang instellen</span><span class="sxs-lookup"><span data-stu-id="5e802-103">Require multi-factor authentication and set up conditional access policies</span></span>

<span data-ttu-id="5e802-104">U kunt toegang tot uw gegevens beschermen met multi-factor Authentication en voorwaardelijk toegangsbeleid.</span><span class="sxs-lookup"><span data-stu-id="5e802-104">You protect access to your data with multi-factor authentication and conditional access policies.</span></span> <span data-ttu-id="5e802-105">Deze toevoegen substantiële extra beveiligings.</span><span class="sxs-lookup"><span data-stu-id="5e802-105">These add substantial additional security.</span></span> <span data-ttu-id="5e802-106">Microsoft biedt een set beleidsregels voor voorwaardelijke toegang die worden aanbevolen voor alle klanten.</span><span class="sxs-lookup"><span data-stu-id="5e802-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="5e802-107">Basisregels voor basisregels zijn een set vooraf gedefinieerde beleidsregels waarmee organisaties worden beschermd tegen veel voorkomende aanvallen.</span><span class="sxs-lookup"><span data-stu-id="5e802-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="5e802-108">Deze veelvoorkomende aanvallen kunnen met een wachtwoord, herhaling en phishing behoren.</span><span class="sxs-lookup"><span data-stu-id="5e802-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="5e802-109">Voor deze beleidsregels moeten beheerders en gebruikers een tweede vorm van verificatie (zogenaamde meervoudige verificatie of MFA) invoeren wanneer aan bepaalde voorwaarden wordt voldaan.</span><span class="sxs-lookup"><span data-stu-id="5e802-109">These policies require admins and users to enter a second form of authentication (called multi-factor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="5e802-110">Als een gebruiker in uw organisatie zich bijvoorbeeld probeert aan te melden bij Microsoft 365 vanuit een ander land of een onbekend apparaat, kan de aanmelding als risico worden beschouwd.</span><span class="sxs-lookup"><span data-stu-id="5e802-110">For example, if a user in your organization tries to sign in to Microsoft 365 from a different country or from an unknown device, the sign-in might be considered risky.</span></span> <span data-ttu-id="5e802-111">De gebruiker moet een extra vorm van verificatie geven (zoals een vingerafdruk of een code) om de identiteit ervan te bewijzen.</span><span class="sxs-lookup"><span data-stu-id="5e802-111">The user must provide an extra form of authentication (such as a fingerprint or a code) to prove their identity.</span></span> 

<span data-ttu-id="5e802-112">Op dit moment bevat het basislijnbeleid het volgende:</span><span class="sxs-lookup"><span data-stu-id="5e802-112">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="5e802-113">Instellen in het Microsoft 365-Beheercentrum:</span><span class="sxs-lookup"><span data-stu-id="5e802-113">Set up in Microsoft 365 admin center:</span></span>
    - <span data-ttu-id="5e802-114">**MFA vereisen voor beheerders** : hiervoor is meervoudige verificatie vereist voor de meest beheerdersrollen, waaronder de globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="5e802-114">**Require MFA for admins** — Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
    - <span data-ttu-id="5e802-115">**Beveiliging van eindgebruikers** : vereist multi-factor Authentication voor gebruikers alleen wanneer een aanmelding is riskant.</span><span class="sxs-lookup"><span data-stu-id="5e802-115">**End user protection** — Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="5e802-116">Instellen in azure Active Directory portal:</span><span class="sxs-lookup"><span data-stu-id="5e802-116">Set up in Azure Active Directory portal:</span></span>
    - <span data-ttu-id="5e802-117">**Verouderde verificatie blokkeren** : oudere clienttoepassingen en bepaalde nieuwe apps gebruiken geen nieuwere, veiliger, authenticatie protocollen.</span><span class="sxs-lookup"><span data-stu-id="5e802-117">**Block legacy authentication** — Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="5e802-118">Met deze oudere apps kunt u beleidsregels voor voorwaardelijke toegang negeren en onbevoegd toegang krijgen tot uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="5e802-118">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="5e802-119">Dit beleid blokkeert de toegang vanaf clients die geen voorwaardelijke toegang ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="5e802-119">This policy blocks access from clients that don't support conditional access.</span></span> 
    - <span data-ttu-id="5e802-120">**MFA vereisen voor Service beheer** : hiervoor is meervoudige verificatie vereist voor de toegang tot beheerprogramma's, waaronder Azure Portal (waar u beleidsregels voor basisregels configureert).</span><span class="sxs-lookup"><span data-stu-id="5e802-120">**Require MFA for Service Management** — Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="5e802-121">Microsoft raadt u aan al deze basisregels voor basisregels in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="5e802-121">Microsoft recommends that you enable all of these baseline policies.</span></span> <span data-ttu-id="5e802-122">Nadat dit beleid is ingeschakeld, wordt beheerders en gebruikers gevraagd zich aan te melden voor Azure multi-factor Authentication.</span><span class="sxs-lookup"><span data-stu-id="5e802-122">After these policies are enabled, admins and users will be prompted to register for Azure Multi-Factor authentication.</span></span>

<span data-ttu-id="5e802-123">Zie [Wat zijn basisregels voor basisregels](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)? voor meer informatie over deze beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="5e802-123">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="require-mfa"></a><span data-ttu-id="5e802-124">MFA vereisen</span><span class="sxs-lookup"><span data-stu-id="5e802-124">Require MFA</span></span>

<span data-ttu-id="5e802-125">Vereisen dat alle gebruikers zich aanmelden met een tweede vorm van ID:</span><span class="sxs-lookup"><span data-stu-id="5e802-125">To require that all users sign in with a second form of ID:</span></span>

1. <span data-ttu-id="5e802-126">Ga naar het Beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> en kies **Setup**.</span><span class="sxs-lookup"><span data-stu-id="5e802-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> and choose **Setup**.</span></span>

2. <span data-ttu-id="5e802-127">Kies op de pagina instellingen de optie **weergeven** in de **beveiligde kaart aanmelden** .</span><span class="sxs-lookup"><span data-stu-id="5e802-127">On the Setup page, choose **View** in the **Make sign-in more secure** card.</span></span>


    ![Meld u veilig een beveiligde kaart.](../media/setupmfa.png)
3. <span data-ttu-id="5e802-129">Kies op de pagina aanmelden veilig maken de optie aan de **slag**.</span><span class="sxs-lookup"><span data-stu-id="5e802-129">On the Make sign-in more secure page, choose **Get started**.</span></span>
 
4. <span data-ttu-id="5e802-130">Schakel in het deelvenster aanmeldingsbeveiliging versterken de selectievakjes in naast **Meervoudige verificatie vereisen voor beheerders** en **gebruikers moeten registreren voor meervoudige verificatie en toegang blokkeren indien risico wordt gedetecteerd**.</span><span class="sxs-lookup"><span data-stu-id="5e802-130">On the Strengthen sign-in security pane, select the check boxes next to **Require multi-factor authentication for admins** and **Require users to register for multi-factor authentication and block access if risk is detected**.</span></span>
    <span data-ttu-id="5e802-131">Zorg ervoor dat u het beheerdersaccount voor [noodgevallen](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) of een afbreek glas sluit van de MFA-vereiste in het vak **gebruikers zoeken** .</span><span class="sxs-lookup"><span data-stu-id="5e802-131">Be sure to exclude the [emergency](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) or "break-glass" admin account from the MFA requirement in the **Find users** box.</span></span>
    
    ![De pagina met ingebouwde beveiligingspagina's versterken.](../media/requiremfa.png)

5. <span data-ttu-id="5e802-133">Kies **beleid maken** onder aan de pagina.</span><span class="sxs-lookup"><span data-stu-id="5e802-133">Choose **Create policy** on the bottom of the page.</span></span>

## <a name="set-up-baseline-policies"></a><span data-ttu-id="5e802-134">Basis voor basisregels instellen</span><span class="sxs-lookup"><span data-stu-id="5e802-134">Set up baseline policies</span></span>

1. <span data-ttu-id="5e802-135">Ga naar de [Azure-Portal](https://portal.azure.com)en ga naar **Azure Active Directory** \> **voorwaardelijke toegang** om een **Nieuw beleid** te maken.</span><span class="sxs-lookup"><span data-stu-id="5e802-135">Go to the [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access** to create a **new policy**.</span></span>

<span data-ttu-id="5e802-136">Zie de volgende specifieke instructies voor elk beleid:</span><span class="sxs-lookup"><span data-stu-id="5e802-136">See the following specific instructions for each policy:</span></span> <br>
    - [<span data-ttu-id="5e802-137">MFA vereisen voor beheerders</span><span class="sxs-lookup"><span data-stu-id="5e802-137">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators) <br>
    - [<span data-ttu-id="5e802-138">MFA vereisen voor gebruikers</span><span class="sxs-lookup"><span data-stu-id="5e802-138">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users) <br>
    - [<span data-ttu-id="5e802-139">Verouderde verificatie blokkeren</span><span class="sxs-lookup"><span data-stu-id="5e802-139">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth) <br>
    - [<span data-ttu-id="5e802-140">MFA vereisen voor servicebeheer</span><span class="sxs-lookup"><span data-stu-id="5e802-140">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)
    
> [!NOTE]
> <span data-ttu-id="5e802-141">Beleidsregels voor het voorbeeld bestaan niet meer en gebruikers moeten hun eigen beleid maken.</span><span class="sxs-lookup"><span data-stu-id="5e802-141">Preview policies no longer exist and users will need to create their own policies.</span></span>


<span data-ttu-id="5e802-142">U kunt extra beleidsregels instellen, zoals goedgekeurde clienttoepassingen vereisen.</span><span class="sxs-lookup"><span data-stu-id="5e802-142">You can set up extra policies, such as requiring approved client apps.</span></span> <span data-ttu-id="5e802-143">Zie de [documentatie voor voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5e802-143">For more information, see the [Conditional Access documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
