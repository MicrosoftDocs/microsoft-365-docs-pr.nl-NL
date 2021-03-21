---
title: Hybride identiteits- en adreslijstsynchronisatie voor Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.date: 09/30/2020
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
description: Beschrijft adreslijstsynchronisatie met Microsoft 365, het opschonen van Active Directory Domain Services en het hulpprogramma Azure Active Directory Connect.
ms.openlocfilehash: 7b717f65bb434918a5eb0ab2bf4a5acab2d08eea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927542"
---
# <a name="hybrid-identity-and-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="f2a76-103">Hybride identiteits- en adreslijstsynchronisatie voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f2a76-103">Hybrid identity and directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="f2a76-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f2a76-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f2a76-105">Afhankelijk van uw zakelijke behoeften en technische vereisten, is het hybride identiteitsmodel en adreslijstsynchronisatie de meest voorkomende keuze voor zakelijke klanten die Microsoft 365 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="f2a76-105">Depending on your business needs and technical requirements, the hybrid identity model and directory synchronization is the most common choice for enterprise customers who are adopting Microsoft 365.</span></span> <span data-ttu-id="f2a76-106">Met adreslijstsynchronisatie kunt u identiteiten beheren in uw Active Directory Domain Services (AD DS) en worden alle updates voor gebruikersaccounts, groepen en contactpersonen gesynchroniseerd met de Azure Active Directory-tenant (Azure AD) van uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="f2a76-106">Directory synchronization allows you to manage identities in your Active Directory Domain Services (AD DS) and all updates to user accounts, groups, and contacts are synchronized to the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span>

>[!Note]
><span data-ttu-id="f2a76-107">Wanneer AD DS-gebruikersaccounts voor de eerste keer worden gesynchroniseerd, krijgen ze niet automatisch een Microsoft 365-licentie toegewezen en hebben ze geen toegang tot Microsoft 365-services, zoals e-mail.</span><span class="sxs-lookup"><span data-stu-id="f2a76-107">When AD DS user accounts are synchronized for the first time, they are not automatically assigned a Microsoft 365 license and cannot access Microsoft 365 services, such as email.</span></span> <span data-ttu-id="f2a76-108">U moet ze eerst een gebruikslocatie toewijzen.</span><span class="sxs-lookup"><span data-stu-id="f2a76-108">You must first assign them a usage location.</span></span> <span data-ttu-id="f2a76-109">Wijs vervolgens een licentie toe aan deze gebruikersaccounts, afzonderlijk of dynamisch via groepslidmaatschap.</span><span class="sxs-lookup"><span data-stu-id="f2a76-109">Then, assign a license to these user accounts, either individually or dynamically through group membership.</span></span>
>

## <a name="authentication-for-hybrid-identity"></a><span data-ttu-id="f2a76-110">Verificatie voor hybride identiteit</span><span class="sxs-lookup"><span data-stu-id="f2a76-110">Authentication for hybrid identity</span></span>

<span data-ttu-id="f2a76-111">Er zijn twee typen verificatie wanneer u het hybride identiteitsmodel gebruikt:</span><span class="sxs-lookup"><span data-stu-id="f2a76-111">There are two types of authentication when using the hybrid identity model:</span></span>

- <span data-ttu-id="f2a76-112">Beheerde verificatie</span><span class="sxs-lookup"><span data-stu-id="f2a76-112">Managed authentication</span></span>

  <span data-ttu-id="f2a76-113">Azure AD verwerkt het verificatieproces met behulp van een lokaal opgeslagen hashed-versie van het wachtwoord of verzendt de referenties naar een on-premises softwareagent die moet worden geverifieerd door de on-premises AD DS.</span><span class="sxs-lookup"><span data-stu-id="f2a76-113">Azure AD handles the authentication process by using a locally-stored hashed version of the password or sends the credentials to an on-premises software agent to be authenticated by the on-premises AD DS.</span></span>

- <span data-ttu-id="f2a76-114">Federatieve verificatie</span><span class="sxs-lookup"><span data-stu-id="f2a76-114">Federated authentication</span></span>

  <span data-ttu-id="f2a76-115">Azure AD omgeleid de clientcomputer die verificatie aanvraagt naar een andere identiteitsprovider.</span><span class="sxs-lookup"><span data-stu-id="f2a76-115">Azure AD redirects the client computer requesting authentication to another identity provider.</span></span>

### <a name="managed-authentication"></a><span data-ttu-id="f2a76-116">Beheerde verificatie</span><span class="sxs-lookup"><span data-stu-id="f2a76-116">Managed authentication</span></span>

<span data-ttu-id="f2a76-117">Er zijn twee typen beheerde verificatie:</span><span class="sxs-lookup"><span data-stu-id="f2a76-117">There are two types of managed authentication:</span></span>

- <span data-ttu-id="f2a76-118">Wachtwoordhashsynchronisatie (PHS)</span><span class="sxs-lookup"><span data-stu-id="f2a76-118">Password hash synchronization (PHS)</span></span>

  <span data-ttu-id="f2a76-119">Azure AD voert de verificatie zelf uit.</span><span class="sxs-lookup"><span data-stu-id="f2a76-119">Azure AD performs the authentication itself.</span></span>

- <span data-ttu-id="f2a76-120">Pass Through-verificatie (PTA)</span><span class="sxs-lookup"><span data-stu-id="f2a76-120">Pass-through authentication (PTA)</span></span>

  <span data-ttu-id="f2a76-121">Azure AD heeft AD DS de verificatie laten uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="f2a76-121">Azure AD has AD DS perform the authentication.</span></span>


#### <a name="password-hash-synchronization-phs"></a><span data-ttu-id="f2a76-122">Wachtwoordhashsynchronisatie (PHS)</span><span class="sxs-lookup"><span data-stu-id="f2a76-122">Password hash synchronization (PHS)</span></span>

<span data-ttu-id="f2a76-123">Met PHS synchroniseert u uw AD DS-gebruikersaccounts met Microsoft 365 en beheert u uw gebruikers on-premises.</span><span class="sxs-lookup"><span data-stu-id="f2a76-123">With PHS, you synchronize your AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> <span data-ttu-id="f2a76-124">Hashes van gebruikerswachtwoorden worden gesynchroniseerd van uw AD DS naar Azure AD, zodat de gebruikers hetzelfde wachtwoord on-premises en in de cloud hebben.</span><span class="sxs-lookup"><span data-stu-id="f2a76-124">Hashes of user passwords are synchronized from your AD DS to Azure AD so that the users have the same password on-premises and in the cloud.</span></span> <span data-ttu-id="f2a76-125">Dit is de eenvoudigste manier om verificatie in te schakelen voor AD DS-identiteiten in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f2a76-125">This is the simplest way to enable authentication for AD DS identities in Azure AD.</span></span> 

![Wachtwoordhashsynchronisatie (PHS)](../media/plan-for-directory-synchronization/phs-authentication.png)

<span data-ttu-id="f2a76-127">Wanneer wachtwoorden on-premises worden gewijzigd of opnieuw worden ingesteld, worden de nieuwe wachtwoordhashes gesynchroniseerd met Azure AD, zodat uw gebruikers altijd hetzelfde wachtwoord kunnen gebruiken voor cloudbronnen en on-premises resources.</span><span class="sxs-lookup"><span data-stu-id="f2a76-127">When passwords are changed or reset on-premises, the new password hashes are synchronized to Azure AD so that your users can always use the same password for cloud resources and on-premises resources.</span></span> <span data-ttu-id="f2a76-128">De gebruikerswachtwoorden worden nooit in duidelijke tekst verzonden naar Azure AD of opgeslagen in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f2a76-128">The user passwords are never sent to Azure AD or stored in Azure AD in clear text.</span></span> <span data-ttu-id="f2a76-129">Voor sommige premiumfuncties van Azure AD, zoals Identiteitsbeveiliging, is PHS vereist, ongeacht welke verificatiemethode is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="f2a76-129">Some premium features of Azure AD, such as Identity Protection, require PHS regardless of which authentication method is selected.</span></span>
  
<span data-ttu-id="f2a76-130">Zie [de juiste verificatiemethode kiezen voor](/azure/active-directory/hybrid/choose-ad-authn) meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f2a76-130">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="pass-through-authentication-pta"></a><span data-ttu-id="f2a76-131">Pass Through-verificatie (PTA)</span><span class="sxs-lookup"><span data-stu-id="f2a76-131">Pass-through authentication (PTA)</span></span>

<span data-ttu-id="f2a76-132">PTA biedt een eenvoudige wachtwoordvalidatie voor Azure AD-verificatieservices met behulp van een softwareagent die op een of meer on-premises servers wordt uitgevoerd om de gebruikers rechtstreeks met uw AD DS te valideren.</span><span class="sxs-lookup"><span data-stu-id="f2a76-132">PTA provides a simple password validation for Azure AD authentication services using a software agent running on one or more on-premises servers to validate the users directly with your AD DS.</span></span> <span data-ttu-id="f2a76-133">Met PTA synchroniseert u AD DS-gebruikersaccounts met Microsoft 365 en beheert u uw gebruikers on-premises.</span><span class="sxs-lookup"><span data-stu-id="f2a76-133">With PTA, you synchronize AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> 

![Pass Through-verificatie (PTA)](../media/plan-for-directory-synchronization/pta-authentication.png)

<span data-ttu-id="f2a76-135">Met PTA kunnen uw gebruikers zich aanmelden bij zowel on-premises als Microsoft 365-resources en -toepassingen met hun on-premises account en wachtwoord.</span><span class="sxs-lookup"><span data-stu-id="f2a76-135">PTA allows your users to sign in to both on-premises and Microsoft 365 resources and applications using their on-premises account and password.</span></span> <span data-ttu-id="f2a76-136">Met deze configuratie worden gebruikerswachtwoorden rechtstreeks gevalideerd op basis van uw on-premises AD DS zonder wachtwoordhashes op te slaan in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f2a76-136">This configuration validates users passwords directly against your on-premises AD DS without storing password hashes in Azure AD.</span></span> 

<span data-ttu-id="f2a76-137">PTA is ook voor organisaties met een beveiligingsvereiste om on-premises gebruikersaccountstaten, wachtwoordbeleid en aanmeldingsuren onmiddellijk af te dwingen.</span><span class="sxs-lookup"><span data-stu-id="f2a76-137">PTA is also for organizations with a security requirement to immediately enforce on-premises user account states, password policies, and logon hours.</span></span> 
  
<span data-ttu-id="f2a76-138">Zie [de juiste verificatiemethode kiezen voor](/azure/active-directory/hybrid/choose-ad-authn) meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f2a76-138">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
### <a name="federated-authentication"></a><span data-ttu-id="f2a76-139">Federatieve verificatie</span><span class="sxs-lookup"><span data-stu-id="f2a76-139">Federated authentication</span></span>

<span data-ttu-id="f2a76-140">Federatieverificatie is voornamelijk bedoeld voor grote ondernemingen met complexere verificatievereisten.</span><span class="sxs-lookup"><span data-stu-id="f2a76-140">Federated authentication is primarily for large enterprise organizations with more complex authentication requirements.</span></span> <span data-ttu-id="f2a76-141">AD DS-identiteiten worden gesynchroniseerd met Microsoft 365 en gebruikersaccounts worden on-premises beheerd.</span><span class="sxs-lookup"><span data-stu-id="f2a76-141">AD DS identities are synchronized with Microsoft 365 and users accounts are managed on-premises.</span></span> <span data-ttu-id="f2a76-142">Met federatief verificatie hebben gebruikers hetzelfde wachtwoord on-premises en in de cloud en ze moeten zich niet opnieuw aanmelden om Microsoft 365 te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="f2a76-142">With federated authentication, users have the same password on-premises and in the cloud and they do not have to sign in again to use Microsoft 365.</span></span> 

<span data-ttu-id="f2a76-143">Federatief verificatie kan aanvullende verificatievereisten ondersteunen, zoals op smartcard gebaseerde verificatie of een meervoudige verificatie van derden en is meestal vereist wanneer organisaties een verificatievereiste hebben die niet inheems wordt ondersteund door Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f2a76-143">Federated authentication can support additional authentication requirements, such as smartcard-based authentication or a third-party multi-factor authentication and is typically required when organizations have an authentication requirement not natively supported by Azure AD.</span></span>
 
<span data-ttu-id="f2a76-144">Zie [de juiste verificatiemethode kiezen voor](/azure/active-directory/hybrid/choose-ad-authn) meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f2a76-144">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="third-party-authentication-and-identity-providers"></a><span data-ttu-id="f2a76-145">Externe verificatie- en identiteitsproviders</span><span class="sxs-lookup"><span data-stu-id="f2a76-145">Third-party authentication and identity providers</span></span>

<span data-ttu-id="f2a76-146">On-premises adreslijstobjecten kunnen worden gesynchroniseerd met Microsoft 365 en cloudresourcetoegang wordt hoofdzakelijk beheerd door een externe identiteitsprovider (IdP).</span><span class="sxs-lookup"><span data-stu-id="f2a76-146">On-premises directory objects may be synchronized to Microsoft 365 and cloud resource access is primarily managed by a third-party identity provider (IdP).</span></span> <span data-ttu-id="f2a76-147">Als uw organisatie een federatieoplossing van derden gebruikt, kunt u aanmelding met die oplossing configureren voor Microsoft 365, mits de federatieoplossing van derden compatibel is met Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f2a76-147">If your organization uses a third-party federation solution, you can configure sign-on with that solution for Microsoft 365 provided that the third-party federation solution is compatible with Azure AD.</span></span>
  
<span data-ttu-id="f2a76-148">Zie de [compatibiliteitslijst met Azure AD-federaties](/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f2a76-148">See the [Azure AD federation compatibility list](/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) to learn more.</span></span>
  
## <a name="ad-ds-preparation"></a><span data-ttu-id="f2a76-149">AD DS-voorbereiding</span><span class="sxs-lookup"><span data-stu-id="f2a76-149">AD DS Preparation</span></span>

<span data-ttu-id="f2a76-150">Als u wilt zorgen voor een naadloze overgang naar Microsoft 365 met behulp van synchronisatie, moet u uw AD DS-forest voorbereiden voordat u begint met de implementatie van de Microsoft 365-adreslijstsynchronisatie.</span><span class="sxs-lookup"><span data-stu-id="f2a76-150">To help ensure a seamless transition to Microsoft 365 by using synchronization, you must prepare your AD DS forest before you begin your Microsoft 365 directory synchronization deployment.</span></span>
  
<span data-ttu-id="f2a76-151">Uw adreslijstvoorbereiding moet zich richten op de volgende taken:</span><span class="sxs-lookup"><span data-stu-id="f2a76-151">Your directory preparation should focus on the following tasks:</span></span>

- <span data-ttu-id="f2a76-152">Dubbele **proxyAddress-** en **userPrincipalName-kenmerken** verwijderen.</span><span class="sxs-lookup"><span data-stu-id="f2a76-152">Remove duplicate **proxyAddress** and **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="f2a76-153">Lege en ongeldige **userPrincipalName-kenmerken** bijwerken met geldige **userPrincipalName-kenmerken.**</span><span class="sxs-lookup"><span data-stu-id="f2a76-153">Update blank and invalid **userPrincipalName** attributes with valid **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="f2a76-154">Verwijder ongeldige en twijfelachtige tekens in de **opgegevenname,** achternaam ( **sn** ), **sAMAccountName**, **displayName**, **e-mail**, **proxyAddresses**, **mailNickname** en **userPrincipalName-kenmerken.**</span><span class="sxs-lookup"><span data-stu-id="f2a76-154">Remove invalid and questionable characters in the **givenName**, surname ( **sn** ), **sAMAccountName**, **displayName**, **mail**, **proxyAddresses**, **mailNickname**, and **userPrincipalName** attributes.</span></span> <span data-ttu-id="f2a76-155">Zie Lijst met kenmerken die worden gesynchroniseerd met het Azure Active Directory Sync Tool voor meer informatie over het voorbereiden [van kenmerken.](https://go.microsoft.com/fwlink/p/?LinkId=396719)</span><span class="sxs-lookup"><span data-stu-id="f2a76-155">For details about preparing attributes, see [List of attributes that are synced by the Azure Active Directory Sync Tool](https://go.microsoft.com/fwlink/p/?LinkId=396719).</span></span>

    > [!NOTE]
    > <span data-ttu-id="f2a76-156">Dit zijn dezelfde kenmerken die door Azure AD Connect worden gesynchroniseerd.</span><span class="sxs-lookup"><span data-stu-id="f2a76-156">These are the same attributes that Azure AD Connect synchronizes.</span></span> 
  
## <a name="multi-forest-deployment-considerations"></a><span data-ttu-id="f2a76-157">Overwegingen voor de implementatie van meerdere forests</span><span class="sxs-lookup"><span data-stu-id="f2a76-157">Multi-forest deployment considerations</span></span>

<span data-ttu-id="f2a76-158">Gebruik een aangepaste installatie van Azure AD Connect voor meerdere forests en [SSO-opties.](/azure/active-directory/hybrid/how-to-connect-install-custom)</span><span class="sxs-lookup"><span data-stu-id="f2a76-158">For multiple forests and SSO options, use a [Custom Installation of Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-custom).</span></span>
  
<span data-ttu-id="f2a76-159">Als uw organisatie meerdere forests voor verificatie (aanmeldingsbossen) heeft, raden we ten zeerste het volgende aan:</span><span class="sxs-lookup"><span data-stu-id="f2a76-159">If your organization has multiple forests for authentication (logon forests), we highly recommend the following:</span></span>
  
- <span data-ttu-id="f2a76-160">**Overweeg uw bossen te consolideren.**</span><span class="sxs-lookup"><span data-stu-id="f2a76-160">**Consider consolidating your forests.**</span></span> <span data-ttu-id="f2a76-161">Over het algemeen is er meer overhead vereist om meerdere bossen te onderhouden.</span><span class="sxs-lookup"><span data-stu-id="f2a76-161">In general, there's more overhead required to maintain multiple forests.</span></span> <span data-ttu-id="f2a76-162">Tenzij uw organisatie beveiligingsbeperkingen heeft die de noodzaak van afzonderlijke bossen bepalen, kunt u overwegen uw on-premises omgeving te vereenvoudigen.</span><span class="sxs-lookup"><span data-stu-id="f2a76-162">Unless your organization has security constraints that dictate the need for separate forests, consider simplifying your on-premises environment.</span></span>
- <span data-ttu-id="f2a76-163">**Alleen gebruiken in uw primaire aanmeldingsbos.**</span><span class="sxs-lookup"><span data-stu-id="f2a76-163">**Use only in your primary logon forest.**</span></span> <span data-ttu-id="f2a76-164">Overweeg microsoft 365 alleen te implementeren in uw primaire aanmeldingsbos voor de eerste implementatie van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f2a76-164">Consider deploying Microsoft 365 only in your primary logon forest for your initial rollout of Microsoft 365.</span></span> 

<span data-ttu-id="f2a76-165">Als u uw AD DS-implementatie met meerdere forests niet kunt samenvoegen of andere adreslijstservices gebruikt om identiteiten te beheren, kunt u deze mogelijk synchroniseren met behulp van Microsoft of een partner.</span><span class="sxs-lookup"><span data-stu-id="f2a76-165">If you can't consolidate your multi-forest AD DS deployment or are using other directory services to manage identities, you may be able to synchronize these with the help of Microsoft or a partner.</span></span>
  
<span data-ttu-id="f2a76-166">Zie [Excuses voor Azure AD Connect voor](/azure/active-directory/hybrid/plan-connect-topologies) meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f2a76-166">See [Topologies for Azure AD Connect](/azure/active-directory/hybrid/plan-connect-topologies) for more information.</span></span>
  
## <a name="features-that-are-dependent-on-directory-synchronization"></a><span data-ttu-id="f2a76-167">Functies die afhankelijk zijn van adreslijstsynchronisatie</span><span class="sxs-lookup"><span data-stu-id="f2a76-167">Features that are dependent on directory synchronization</span></span>
  
<span data-ttu-id="f2a76-168">Adreslijstsynchronisatie is vereist voor de volgende functies en functionaliteit:</span><span class="sxs-lookup"><span data-stu-id="f2a76-168">Directory synchronization is required for the following features and functionality:</span></span>
  
- <span data-ttu-id="f2a76-169">Azure AD Seamless Single Sign-On (SSO)</span><span class="sxs-lookup"><span data-stu-id="f2a76-169">Azure AD Seamless Single Sign-On (SSO)</span></span>
- <span data-ttu-id="f2a76-170">Skype coëxistentie</span><span class="sxs-lookup"><span data-stu-id="f2a76-170">Skype coexistence</span></span>
- <span data-ttu-id="f2a76-171">Hybride implementatie van Exchange, waaronder:</span><span class="sxs-lookup"><span data-stu-id="f2a76-171">Exchange hybrid deployment, including:</span></span>
  - <span data-ttu-id="f2a76-172">Volledig gedeelde algemene adreslijst (GAL) tussen uw on-premises Exchange-omgeving en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f2a76-172">Fully shared global address list (GAL) between your on-premises Exchange environment and Microsoft 365.</span></span>
  - <span data-ttu-id="f2a76-173">Gal-informatie uit verschillende e-mailsystemen synchroniseren.</span><span class="sxs-lookup"><span data-stu-id="f2a76-173">Synchronizing GAL information from different mail systems.</span></span>
  - <span data-ttu-id="f2a76-174">De mogelijkheid om gebruikers toe te voegen aan en te verwijderen uit microsoft 365-serviceaanbiedingen.</span><span class="sxs-lookup"><span data-stu-id="f2a76-174">The ability to add users to and remove users from Microsoft 365 service offerings.</span></span> <span data-ttu-id="f2a76-175">Hiervoor zijn de volgende gegevens vereist:</span><span class="sxs-lookup"><span data-stu-id="f2a76-175">This requires the following:</span></span>
  - <span data-ttu-id="f2a76-176">Tweewegsynchronisatie moet worden geconfigureerd tijdens het instellen van adreslijstsynchronisatie.</span><span class="sxs-lookup"><span data-stu-id="f2a76-176">Two-way synchronization must be configured during directory synchronization setup.</span></span> <span data-ttu-id="f2a76-177">Adreslijstsynchronisatiehulpmiddelen schrijven standaard alleen adreslijstgegevens naar de cloud.</span><span class="sxs-lookup"><span data-stu-id="f2a76-177">By default, directory synchronization tools write directory information only to the cloud.</span></span> <span data-ttu-id="f2a76-178">Wanneer u tweewegsynchronisatie configureert, stelt u de functie voor terugschrijven in, zodat een beperkt aantal objectkenmerken vanuit de cloud wordt gekopieerd en vervolgens teruggeschreven naar uw lokale AD DS.</span><span class="sxs-lookup"><span data-stu-id="f2a76-178">When you configure two-way synchronization, you enable write-back functionality so that a limited number of object attributes are copied from the cloud, and then written them back to your local AD DS.</span></span> <span data-ttu-id="f2a76-179">Terugschrijven wordt ook wel de hybride exchange-modus genoemd.</span><span class="sxs-lookup"><span data-stu-id="f2a76-179">Write-back is also referred to as Exchange hybrid mode.</span></span> 
  - <span data-ttu-id="f2a76-180">Een on-premises hybride implementatie van Exchange</span><span class="sxs-lookup"><span data-stu-id="f2a76-180">An on-premises Exchange hybrid deployment</span></span>
  - <span data-ttu-id="f2a76-181">De mogelijkheid om bepaalde gebruikerspostvakken naar Microsoft 365 te verplaatsen terwijl andere postvakken van gebruikers on-premises blijven.</span><span class="sxs-lookup"><span data-stu-id="f2a76-181">The ability to move some user mailboxes to Microsoft 365 while keeping other user mailboxes on-premises.</span></span>
  - <span data-ttu-id="f2a76-182">Veilige afzenders en geblokkeerde afzenders on-premises worden gerepliceerd naar Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f2a76-182">Safe senders and blocked senders on-premises are replicated to Microsoft 365.</span></span>
  - <span data-ttu-id="f2a76-183">Basisdelegering en send-on-behalf-of-email-functionaliteit.</span><span class="sxs-lookup"><span data-stu-id="f2a76-183">Basic delegation and send-on-behalf-of email functionality.</span></span>
  - <span data-ttu-id="f2a76-184">U hebt een geïntegreerde on-premises smartcard of meervoudige verificatieoplossing.</span><span class="sxs-lookup"><span data-stu-id="f2a76-184">You have an integrated on-premises smart card or multi-factor authentication solution.</span></span>
- <span data-ttu-id="f2a76-185">Synchronisatie van foto's, miniaturen, vergaderruimten en beveiligingsgroepen</span><span class="sxs-lookup"><span data-stu-id="f2a76-185">Synchronization of photos, thumbnails, conference rooms, and security groups</span></span>

## <a name="next-step"></a><span data-ttu-id="f2a76-186">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="f2a76-186">Next step</span></span>

<span data-ttu-id="f2a76-187">Zie Voorbereiden op adreslijstsynchronisatie wanneer u klaar bent om hybride identiteit [te implementeren.](prepare-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="f2a76-187">When you are ready to deploy hybrid identity, see [prepare for directory synchronization](prepare-for-directory-synchronization.md).</span></span>
