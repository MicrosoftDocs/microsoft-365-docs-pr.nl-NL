---
title: Hybrid Identity en Directory Synchronization for Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.date: 06/09/2020
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MOE150
- MET150
ms.assetid: d3577c90-dda5-45ca-afb0-370d2889b10f
description: Beschrijving van adreslijstsynchronisatie met Microsoft 365, Active Directory Domain Services Cleanup en het hulpprogramma Azure Active Directory Connect.
ms.openlocfilehash: 2d3161fb835073a22743ea4f3b00ac508479f0f2
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689201"
---
# <a name="hybrid-identity-and-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="ea0c2-103">Hybrid Identity en Directory Synchronization for Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ea0c2-103">Hybrid identity and directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="ea0c2-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="ea0c2-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="ea0c2-105">Afhankelijk van de behoeften van uw bedrijf en de technische vereisten, is dit de meest voorkomende optie voor Enterprise-klanten die Microsoft 365 aannemen.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-105">Depending on your business needs and technical requirements, the hybrid identity model and directory synchronization is the most common choice for enterprise customers who are adopting Microsoft 365.</span></span> <span data-ttu-id="ea0c2-106">Met adreslijstsynchronisatie kunt u identiteiten beheren in uw Active Directory Domain Services (AD DS) en alle updates voor gebruikersaccounts, groepen en contactpersonen worden gesynchroniseerd met de Azure AD-Tenant (Azure Active Directory) van uw Microsoft-abonnement voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-106">Directory synchronization allows you to manage identities in your Active Directory Domain Services (AD DS) and all updates to user accounts, groups, and contacts are synchronized to the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span>

>[!Note]
><span data-ttu-id="ea0c2-107">Wanneer Active Directory-gebruikersaccounts voor de eerste keer worden gesynchroniseerd, wordt er niet automatisch een Microsoft 365-licentie toegewezen en geen toegang tot Microsoft 365-Services, zoals e-mail.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-107">When AD DS user accounts are synchronized for the first time, they are not automatically assigned a Microsoft 365 license and cannot access Microsoft 365 services, such as email.</span></span> <span data-ttu-id="ea0c2-108">U moet ze eerst een gebruikslocatie toewijzen.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-108">You must first assign them a usage location.</span></span> <span data-ttu-id="ea0c2-109">Vervolgens kunt u een licentie toewijzen aan deze gebruikersaccounts, hetzij afzonderlijk of dynamisch via groepslidmaatschap.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-109">Then, assign a license to these user accounts, either individually or dynamically through group membership.</span></span>
>

## <a name="authentication-for-hybrid-identity"></a><span data-ttu-id="ea0c2-110">Verificatie voor hybride identiteit</span><span class="sxs-lookup"><span data-stu-id="ea0c2-110">Authentication for hybrid identity</span></span>

<span data-ttu-id="ea0c2-111">Er zijn twee typen verificatie wanneer u het Hybrid Identity model gebruikt:</span><span class="sxs-lookup"><span data-stu-id="ea0c2-111">There are two types of authentication when using the hybrid identity model:</span></span>

- <span data-ttu-id="ea0c2-112">Beheerde verificatie</span><span class="sxs-lookup"><span data-stu-id="ea0c2-112">Managed authentication</span></span>

  <span data-ttu-id="ea0c2-113">Azure AD lost het authenticatieproces op met een lokaal opgeslagen hash-versie van het wachtwoord of verzendt de referenties naar een on-premises programma-agent om te worden geverifieerd door de on-premises AD DS.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-113">Azure AD handles the authentication process by using a locally-stored hashed version of the password or sends the credentials to an on-premises software agent to be authenticated by the on-premises AD DS.</span></span>

- <span data-ttu-id="ea0c2-114">Federatieve verificatie</span><span class="sxs-lookup"><span data-stu-id="ea0c2-114">Federated authentication</span></span>

  <span data-ttu-id="ea0c2-115">Azure AD stuurt de clientcomputer om authenticatie vragen aan een andere identiteitsprovider.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-115">Azure AD redirects the client computer requesting authentication to another identity provider.</span></span>

### <a name="managed-authentication"></a><span data-ttu-id="ea0c2-116">Beheerde verificatie</span><span class="sxs-lookup"><span data-stu-id="ea0c2-116">Managed authentication</span></span>

<span data-ttu-id="ea0c2-117">Er zijn twee typen beheerde verificatie:</span><span class="sxs-lookup"><span data-stu-id="ea0c2-117">There are two types of managed authentication:</span></span>

- <span data-ttu-id="ea0c2-118">Synchronisatie van wachtwoord hash (PHS)</span><span class="sxs-lookup"><span data-stu-id="ea0c2-118">Password hash synchronization (PHS)</span></span>

  <span data-ttu-id="ea0c2-119">Azure AD voert de authenticatie zelf uit.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-119">Azure AD performs the authentication itself.</span></span>

- <span data-ttu-id="ea0c2-120">Pass Through-verificatie (PTA)</span><span class="sxs-lookup"><span data-stu-id="ea0c2-120">Pass-through authentication (PTA)</span></span>

  <span data-ttu-id="ea0c2-121">Azure AD Active Directory heeft de authenticatie uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-121">Azure AD has AD DS perform the authentication.</span></span>


#### <a name="password-hash-synchronization-phs"></a><span data-ttu-id="ea0c2-122">Synchronisatie van wachtwoord hash (PHS)</span><span class="sxs-lookup"><span data-stu-id="ea0c2-122">Password hash synchronization (PHS)</span></span>

<span data-ttu-id="ea0c2-123">Met PHS synchroniseert u uw AD DS-gebruikersaccounts met Microsoft 365 en beheert u de gebruikers on-premises.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-123">With PHS, you synchronize your AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> <span data-ttu-id="ea0c2-124">Hashes van gebruikerswachtwoorden worden gesynchroniseerd vanuit uw AD DS naar Azure AD, zodat de gebruikers hetzelfde wachtwoord en on-premises hebben in de Cloud.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-124">Hashes of user passwords are synchronized from your AD DS to Azure AD so that the users have the same password on-premises and in the cloud.</span></span> <span data-ttu-id="ea0c2-125">Dit is de eenvoudigste manier om authenticatie voor AD DS-identiteiten in te schakelen in azure AD.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-125">This is the simplest way to enable authentication for AD DS identities in Azure AD.</span></span> 

![Synchronisatie van wachtwoord hash (PHS)](../media/plan-for-directory-synchronization/phs-authentication.png)

<span data-ttu-id="ea0c2-127">Wanneer wachtwoorden worden gewijzigd of on-premises opnieuw instellen, worden de nieuwe wachtwoord hashwaarden gesynchroniseerd met Azure AD, zodat uw gebruikers altijd hetzelfde wachtwoord gebruiken voor Cloud bronnen en on-premises resources.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-127">When passwords are changed or reset on-premises, the new password hashes are synchronized to Azure AD so that your users can always use the same password for cloud resources and on-premises resources.</span></span> <span data-ttu-id="ea0c2-128">De wachtwoorden van gebruikers worden nooit naar Azure AD verzonden of opgeslagen in azure AD als gewone tekst.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-128">The user passwords are never sent to Azure AD or stored in Azure AD in clear text.</span></span> <span data-ttu-id="ea0c2-129">Voor sommige Premium-functies van Azure AD, zoals identiteitsbeveiliging, is PHS vereist, ongeacht welke verificatiemethode is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-129">Some premium features of Azure AD, such as Identity Protection, require PHS regardless of which authentication method is selected.</span></span>
  
<span data-ttu-id="ea0c2-130">Zie voor meer informatie [de juiste verificatiemethode kiezen](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) .</span><span class="sxs-lookup"><span data-stu-id="ea0c2-130">See [choosing the right authentication method](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="pass-through-authentication-pta"></a><span data-ttu-id="ea0c2-131">Pass Through-verificatie (PTA)</span><span class="sxs-lookup"><span data-stu-id="ea0c2-131">Pass-through authentication (PTA)</span></span>

<span data-ttu-id="ea0c2-132">PTA biedt een eenvoudige wachtwoordvalidatie voor Azure AD Authentication-Services met behulp van een software-agent die op een of meer on-premises servers wordt uitgevoerd om de gebruikers direct met uw AD DS te valideren.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-132">PTA provides a simple password validation for Azure AD authentication services using a software agent running on one or more on-premises servers to validate the users directly with your AD DS.</span></span> <span data-ttu-id="ea0c2-133">Met PTA synchroniseert u Active Directory-gebruikersaccounts met Microsoft 365 en beheert u de gebruikers on-premises.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-133">With PTA, you synchronize AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> 

![Pass Through-verificatie (PTA)](../media/plan-for-directory-synchronization/pta-authentication.png)

<span data-ttu-id="ea0c2-135">Met behulp van PTA kunnen uw gebruikers zich aanmelden bij zowel on-premises als Microsoft 365-bronnen en-toepassingen met behulp van hun on-premises account en wachtwoord.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-135">PTA allows your users to sign in to both on-premises and Microsoft 365 resources and applications using their on-premises account and password.</span></span> <span data-ttu-id="ea0c2-136">Deze configuratie valideert gebruikerswachtwoorden rechtstreeks op uw on-premises AD DS, zonder wachtwoord hashwaarden op te slaan in azure AD.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-136">This configuration validates users passwords directly against your on-premises AD DS without storing password hashes in Azure AD.</span></span> 

<span data-ttu-id="ea0c2-137">PTA is ook bedoeld voor organisaties met een beveiligings verplichting om direct on-premises statussen van gebruikersaccounts, wachtwoordbeleidsregels en aanmeldingstijden af te dwingen.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-137">PTA is also for organizations with a security requirement to immediately enforce on-premises user account states, password policies, and logon hours.</span></span> 
  
<span data-ttu-id="ea0c2-138">Zie voor meer informatie [de juiste verificatiemethode kiezen](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) .</span><span class="sxs-lookup"><span data-stu-id="ea0c2-138">See [choosing the right authentication method](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
### <a name="federated-authentication"></a><span data-ttu-id="ea0c2-139">Federatieve verificatie</span><span class="sxs-lookup"><span data-stu-id="ea0c2-139">Federated authentication</span></span>

<span data-ttu-id="ea0c2-140">Federatieve verificatie is hoofdzakelijk voor grote Enterprise-organisaties met meer ingewikkelde verificatievereisten.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-140">Federated authentication is primarily for large enterprise organizations with more complex authentication requirements.</span></span> <span data-ttu-id="ea0c2-141">AD DS-identiteiten worden gesynchroniseerd met Microsoft 365 en gebruikersaccounts worden on-premises beheerd.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-141">AD DS identities are synchronized with Microsoft 365 and users accounts are managed on-premises.</span></span> <span data-ttu-id="ea0c2-142">Met federatieve verificatie hebben gebruikers hetzelfde wachtwoord en wel in de Cloud en hoeven ze zich niet opnieuw aan te melden voor het gebruik van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-142">With federated authentication, users have the same password on-premises and in the cloud and they do not have to sign in again to use Microsoft 365.</span></span> 

<span data-ttu-id="ea0c2-143">Federatieve authenticatie biedt ondersteuning voor extra verificatievereisten, zoals smartcardverificatie of een meervoudige verificatie van derden, en is meestal vereist wanneer organisaties een authenticatie vereiste niet voor de ondersteuning van Azure AD ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-143">Federated authentication can support additional authentication requirements, such as smartcard-based authentication or a third-party multi-factor authentication and is typically required when organizations have an authentication requirement not natively supported by Azure AD.</span></span>
 
<span data-ttu-id="ea0c2-144">Zie voor meer informatie [de juiste verificatiemethode kiezen](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) .</span><span class="sxs-lookup"><span data-stu-id="ea0c2-144">See [choosing the right authentication method](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="third-party-authentication-and-identity-providers"></a><span data-ttu-id="ea0c2-145">Verificatie-en identiteitsproviders van derden</span><span class="sxs-lookup"><span data-stu-id="ea0c2-145">Third-party authentication and identity providers</span></span>

<span data-ttu-id="ea0c2-146">On-premises adreslijst objecten kunnen worden gesynchroniseerd met Microsoft 365 en toegang tot de Cloud wordt hoofdzakelijk beheerd door een externe identiteitsprovider (IdP).</span><span class="sxs-lookup"><span data-stu-id="ea0c2-146">On-premises directory objects may be synchronized to Microsoft 365 and cloud resource access is primarily managed by a third-party identity provider (IdP).</span></span> <span data-ttu-id="ea0c2-147">Als uw organisatie gebruikmaakt van een Federatie oplossing van derden, kunt u aanmelden met die oplossing voor Microsoft 365, mits de Federatie oplossing van derden compatibel is met Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-147">If your organization uses a third-party federation solution, you can configure sign-on with that solution for Microsoft 365 provided that the third-party federation solution is compatible with Azure AD.</span></span>
  
<span data-ttu-id="ea0c2-148">Zie de [lijst met compatibiliteit van Azure AD Federation](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-148">See the [Azure AD federation compatibility list](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) to learn more.</span></span>
  
## <a name="ad-ds-preparation"></a><span data-ttu-id="ea0c2-149">AD DS-voorbereiding</span><span class="sxs-lookup"><span data-stu-id="ea0c2-149">AD DS Preparation</span></span>

<span data-ttu-id="ea0c2-150">Voor een naadloze overgang naar Microsoft 365 met behulp van synchronisatie moet u eerst uw Active Directory-forest voorbereiden voordat u met de implementatie van Microsoft 365 Directory Synchronization begint.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-150">To help ensure a seamless transition to Microsoft 365 by using synchronization, you must prepare your AD DS forest before you begin your Microsoft 365 directory synchronization deployment.</span></span>
  
<span data-ttu-id="ea0c2-151">Het voorbereiden van de adreslijst moet u richten op de volgende taken:</span><span class="sxs-lookup"><span data-stu-id="ea0c2-151">Your directory preparation should focus on the following tasks:</span></span>

- <span data-ttu-id="ea0c2-152">Verwijder dubbele kenmerken van **proxyAddress** en **userPrincipalName** .</span><span class="sxs-lookup"><span data-stu-id="ea0c2-152">Remove duplicate **proxyAddress** and **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="ea0c2-153">Lege en ongeldige **userPrincipalName** -kenmerken bijwerken met geldige **userPrincipalName** -kenmerken.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-153">Update blank and invalid **userPrincipalName** attributes with valid **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="ea0c2-154">Verwijder ongeldige en dubieuze tekens in de kenmerken **benaming**, achternaam ( **sn** ), **sAMAccountName**, **DisplayName**, **mail**, **proxyAddresses**, **mailNickname**en **userPrincipalName** .</span><span class="sxs-lookup"><span data-stu-id="ea0c2-154">Remove invalid and questionable characters in the **givenName**, surname ( **sn** ), **sAMAccountName**, **displayName**, **mail**, **proxyAddresses**, **mailNickname**, and **userPrincipalName** attributes.</span></span> <span data-ttu-id="ea0c2-155">Zie [lijst met kenmerken die worden gesynchroniseerd met het Azure Active Directory-synchronisatieprogramma](https://go.microsoft.com/fwlink/p/?LinkId=396719)voor meer informatie over het voorbereiden van kenmerken.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-155">For details about preparing attributes, see [List of attributes that are synced by the Azure Active Directory Sync Tool](https://go.microsoft.com/fwlink/p/?LinkId=396719).</span></span>

    > [!NOTE]
    > <span data-ttu-id="ea0c2-156">Dit zijn dezelfde kenmerken die Azure AD Connect synchroniseren.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-156">These are the same attributes that Azure AD Connect synchronizes.</span></span> 
  
## <a name="multi-forest-deployment-considerations"></a><span data-ttu-id="ea0c2-157">Aandachtspunten voor de implementatie van meerdere forests</span><span class="sxs-lookup"><span data-stu-id="ea0c2-157">Multi-forest deployment considerations</span></span>

<span data-ttu-id="ea0c2-158">Voor meerdere forests en opties voor eenmalige aanmelding gebruikt u een [aangepaste installatie van Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).</span><span class="sxs-lookup"><span data-stu-id="ea0c2-158">For multiple forests and SSO options, use a [Custom Installation of Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).</span></span>
  
<span data-ttu-id="ea0c2-159">Als uw organisatie meerdere forests heeft voor verificatie (aanmeldings bossen), is het raadzaam het volgende te doen:</span><span class="sxs-lookup"><span data-stu-id="ea0c2-159">If your organization has multiple forests for authentication (logon forests), we highly recommend the following:</span></span>
  
- <span data-ttu-id="ea0c2-160">**Overweeg om uw forests samen te voegen.**</span><span class="sxs-lookup"><span data-stu-id="ea0c2-160">**Consider consolidating your forests.**</span></span> <span data-ttu-id="ea0c2-161">In het algemeen zijn er meer extra kosten nodig om meerdere forests te onderhouden.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-161">In general, there's more overhead required to maintain multiple forests.</span></span> <span data-ttu-id="ea0c2-162">U moet uw on-premises omgeving vereenvoudigen, tenzij uw organisatie beveiligingsbeperkingen heeft die de noodzaak voor afzonderlijke forests kunnen dicteren.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-162">Unless your organization has security constraints that dictate the need for separate forests, consider simplifying your on-premises environment.</span></span>
- <span data-ttu-id="ea0c2-163">**Alleen gebruiken in uw primaire aanmeldings forest.**</span><span class="sxs-lookup"><span data-stu-id="ea0c2-163">**Use only in your primary logon forest.**</span></span> <span data-ttu-id="ea0c2-164">Overweeg Microsoft 365 alleen te implementeren in uw primaire aanmeldingsdomein voor uw eerste implementatie van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-164">Consider deploying Microsoft 365 only in your primary logon forest for your initial rollout of Microsoft 365.</span></span> 

<span data-ttu-id="ea0c2-165">Als u de AD DS-implementatie van meerdere forests niet kunt samenvoegen of andere adreslijstservices gebruikt voor het beheren van identiteiten, kunt u deze mogelijk synchroniseren met de Help van Microsoft of een partner.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-165">If you can't consolidate your multi-forest AD DS deployment or are using other directory services to manage identities, you may be able to synchronize these with the help of Microsoft or a partner.</span></span>
  
<span data-ttu-id="ea0c2-166">Zie [topologieën voor Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-166">See [Topologies for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies) for more information.</span></span>
  
## <a name="features-that-are-dependent-on-directory-synchronization"></a><span data-ttu-id="ea0c2-167">Functies die afhankelijk zijn van adreslijstsynchronisatie</span><span class="sxs-lookup"><span data-stu-id="ea0c2-167">Features that are dependent on directory synchronization</span></span>
  
<span data-ttu-id="ea0c2-168">Adreslijstsynchronisatie is vereist voor de volgende functies en functionaliteit:</span><span class="sxs-lookup"><span data-stu-id="ea0c2-168">Directory synchronization is required for the following features and functionality:</span></span>
  
- <span data-ttu-id="ea0c2-169">Eenmalige aanmelding met Azure AD (SSO)</span><span class="sxs-lookup"><span data-stu-id="ea0c2-169">Azure AD Seamless Single Sign-On (SSO)</span></span>
- <span data-ttu-id="ea0c2-170">Skype-samenwerking</span><span class="sxs-lookup"><span data-stu-id="ea0c2-170">Skype coexistence</span></span>
- <span data-ttu-id="ea0c2-171">Hybride implementatie van Exchange, waaronder:</span><span class="sxs-lookup"><span data-stu-id="ea0c2-171">Exchange hybrid deployment, including:</span></span>
  - <span data-ttu-id="ea0c2-172">Volledig gedeelde algemene adreslijst (GAL) tussen uw on-premises Exchange-omgeving en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-172">Fully shared global address list (GAL) between your on-premises Exchange environment and Microsoft 365.</span></span>
  - <span data-ttu-id="ea0c2-173">GAL-gegevens van andere e-mail systemen synchroniseren.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-173">Synchronizing GAL information from different mail systems.</span></span>
  - <span data-ttu-id="ea0c2-174">De mogelijkheid om gebruikers toe te voegen aan en te verwijderen uit serviceaanbiedingen van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-174">The ability to add users to and remove users from Microsoft 365 service offerings.</span></span> <span data-ttu-id="ea0c2-175">Hiervoor hebt u het volgende nodig:</span><span class="sxs-lookup"><span data-stu-id="ea0c2-175">This requires the following:</span></span>
  - <span data-ttu-id="ea0c2-176">Synchronisatie in twee gevallen moet worden geconfigureerd tijdens het instellen van adreslijstsynchronisatie.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-176">Two-way synchronization must be configured during directory synchronization setup.</span></span> <span data-ttu-id="ea0c2-177">Standaard is Directory-synchronisatie hulpprogramma's alleen beschikbaar voor Directory-informatie in de Cloud.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-177">By default, directory synchronization tools write directory information only to the cloud.</span></span> <span data-ttu-id="ea0c2-178">Wanneer u synchronisatie in twee richting configureert, schakelt u de functie write-back functie in, zodat een beperkt aantal objectkenmerken uit de Cloud wordt gekopieerd en vervolgens weer naar uw lokale AD DS wordt geschreven.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-178">When you configure two-way synchronization, you enable write-back functionality so that a limited number of object attributes are copied from the cloud, and then written them back to your local AD DS.</span></span> <span data-ttu-id="ea0c2-179">Write-back wordt ook wel de hybride modus van Exchange genoemd.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-179">Write-back is also referred to as Exchange hybrid mode.</span></span> 
  - <span data-ttu-id="ea0c2-180">Een on-premises hybride implementatie van Exchange</span><span class="sxs-lookup"><span data-stu-id="ea0c2-180">An on-premises Exchange hybrid deployment</span></span>
  - <span data-ttu-id="ea0c2-181">De mogelijkheid om sommige postvakken van gebruikers te verplaatsen naar Microsoft 365 en andere postvakken van gebruikers on-premises te houden.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-181">The ability to move some user mailboxes to Microsoft 365 while keeping other user mailboxes on-premises.</span></span>
  - <span data-ttu-id="ea0c2-182">De on-premises veilige afzenders en geblokkeerde afzenders worden gerepliceerd naar Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-182">Safe senders and blocked senders on-premises are replicated to Microsoft 365.</span></span>
  - <span data-ttu-id="ea0c2-183">Basis overdracht en de functies voor het verzenden van e-mail.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-183">Basic delegation and send-on-behalf-of email functionality.</span></span>
  - <span data-ttu-id="ea0c2-184">U hebt een geïntegreerde on-premises smartcard of een oplossing voor meervoudige verificatie.</span><span class="sxs-lookup"><span data-stu-id="ea0c2-184">You have an integrated on-premises smart card or multi-factor authentication solution.</span></span>
- <span data-ttu-id="ea0c2-185">Synchronisatie van Foto's, miniaturen, vergaderruimten en beveiligingsgroepen</span><span class="sxs-lookup"><span data-stu-id="ea0c2-185">Synchronization of photos, thumbnails, conference rooms, and security groups</span></span>

## <a name="next-step"></a><span data-ttu-id="ea0c2-186">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="ea0c2-186">Next step</span></span>

<span data-ttu-id="ea0c2-187">Wanneer u klaar bent om de Hybrid Identity te implementeren, raadpleegt u [voorbereidingen treffen voor het inrichten van gebruikers](prepare-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="ea0c2-187">When you are ready to deploy hybrid identity, see [prepare to provision users](prepare-for-directory-synchronization.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ea0c2-188">Zie ook</span><span class="sxs-lookup"><span data-stu-id="ea0c2-188">See also</span></span>

[<span data-ttu-id="ea0c2-189">Overzicht van Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ea0c2-189">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)

