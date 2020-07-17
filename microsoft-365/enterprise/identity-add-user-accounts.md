---
title: 'Stap 4: uw gebruikersaccounts toevoegen'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Voeg gebruikersaccounts en groepen rechtstreeks toe aan de Cloud of door ze te synchroniseren met uw on-premises adreslijst.
ms.openlocfilehash: 2a54044737f5b924bd619d5a6c7c72091dc7a0d1
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005832"
---
# <a name="step-4-add-your-user-accounts"></a><span data-ttu-id="d11b2-103">Stap 4: uw gebruikersaccounts toevoegen</span><span class="sxs-lookup"><span data-stu-id="d11b2-103">Step 4: Add your user accounts</span></span>

![Fase 2: identiteit](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-cloud-only"></a>
## <a name="create-your-user-accounts-for-cloud-only-identity"></a><span data-ttu-id="d11b2-105">De gebruikersaccounts maken voor de Cloud-identiteit</span><span class="sxs-lookup"><span data-stu-id="d11b2-105">Create your user accounts for cloud-only identity</span></span>

<span data-ttu-id="d11b2-106">Voor Cloud-identiteit maakt u uw gebruikers en groepen in Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="d11b2-106">For cloud-only identity, create your users and groups in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="d11b2-107">U kunt het volgende gebruiken:</span><span class="sxs-lookup"><span data-stu-id="d11b2-107">You can use:</span></span>

- <span data-ttu-id="d11b2-108">Het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="d11b2-108">The Microsoft 365 admin center</span></span>
- <span data-ttu-id="d11b2-109">De Azure-portal</span><span class="sxs-lookup"><span data-stu-id="d11b2-109">The Azure portal</span></span>
- <span data-ttu-id="d11b2-110">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="d11b2-110">Azure PowerShell</span></span>

<a name="identity-sync"></a>
## <a name="synchronize-identities-for-hybrid-identity"></a><span data-ttu-id="d11b2-111">Identiteiten voor hybride identiteit synchroniseren</span><span class="sxs-lookup"><span data-stu-id="d11b2-111">Synchronize identities for hybrid identity</span></span>

<span data-ttu-id="d11b2-112">*Deze stap is vereist voor hybride omgevingen en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="d11b2-112">*This is required for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="d11b2-113">In deze sectie synchroniseert u uw on-premises Active Directory Domain Services (AD DS) met de Azure AD-tenant die wordt gebruikt door Office 365, Microsoft Intune en andere Cloud-services die zijn opgenomen in Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="d11b2-113">In this section, you'll synchronize your on-premises Active Directory Domain Services (AD DS) with the Azure AD tenant used by Office 365, Microsoft Intune, and other cloud-based services included with Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="d11b2-114">Azure AD Connect is het ondersteunde Microsoft-hulpprogramma dat u helpt bij het synchroniseren van alleen de identiteiten die u echt nodig hebt, van AD DS-omgevingen met één of meerdere forests tot uw Azure AD-tenant.</span><span class="sxs-lookup"><span data-stu-id="d11b2-114">Azure AD Connect is the supported Microsoft tool that guides you through synchronizing only the identities you really need from single or multi-forest AD DS environments to your Azure AD tenant.</span></span> <span data-ttu-id="d11b2-115">In de volgende afbeelding ziet u het basisproces voor Azure AD Connect-synchronisatie.</span><span class="sxs-lookup"><span data-stu-id="d11b2-115">The following figure shows the basic process for Azure AD Connect synchronization.</span></span>

![Hoe Azure AD Connect uw on-premises adreslijst synchroniseert met Azure AD](../media/identity-add-user-accounts/azure-ad-connect.png)

1. <span data-ttu-id="d11b2-117">Met Azure AD Connect dat op een server wordt uitgevoerd, wordt AD DS gecontroleerd op wijzigingen in accounts, groepen en contactpersonen.</span><span class="sxs-lookup"><span data-stu-id="d11b2-117">Azure AD Connect running on a server polls AD DS for changes in accounts, groups, and contacts.</span></span>
2. <span data-ttu-id="d11b2-118">Azure AD Connect stuurt die wijzigingen naar de Azure AD-tenant van uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="d11b2-118">Azure AD Connect sends those changes to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

<span data-ttu-id="d11b2-119">De eerste beslissing in uw hybride identiteitsoplossing is uw verificatievereiste.</span><span class="sxs-lookup"><span data-stu-id="d11b2-119">The first decision in your hybrid identity solution is your authentication requirement.</span></span> <span data-ttu-id="d11b2-120">De volgende opties zijn beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="d11b2-120">The following options are options:</span></span>

- <span data-ttu-id="d11b2-121">Met **beheerde verificatie**wordt het verificatieproces voor gebruikersaanmelding door Azure AD afgehandeld.</span><span class="sxs-lookup"><span data-stu-id="d11b2-121">With **managed authentication**, Azure AD handles the authentication process for user sign-in.</span></span> <span data-ttu-id="d11b2-122">Beheerde verificatie bestaat uit twee methoden:</span><span class="sxs-lookup"><span data-stu-id="d11b2-122">There are two methods for managed authentication:</span></span> 
    - <span data-ttu-id="d11b2-123">**Wachtwoord-hash-synchronisatie (PHS)** [aanbevolen en vereist voor enkele Premium-functies].</span><span class="sxs-lookup"><span data-stu-id="d11b2-123">**Password Hash Sync (PHS)** [Recommended and required for some premium features].</span></span> <span data-ttu-id="d11b2-124">Dit is de eenvoudigste manier om verificatie in te schakelen voor on-premises adreslijstobjecten in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d11b2-124">This is the simplest way to enable authentication for on-premises directory objects in Azure AD.</span></span> <span data-ttu-id="d11b2-125">Azure AD Connect haalt het gehashte wachtwoord uit AD DS, voert extra beveiligingsverwerking uit op de wachtwoordhash en synchroniseert het met Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d11b2-125">Azure AD Connect extracts the hashed password from AD DS, does extra security processing on the password hash, and synchronizes it to Azure AD.</span></span> <span data-ttu-id="d11b2-126">Zie voor meer informatie [wachtwoord hash-synchronisatie implementeren met Azure AD Connect-synchronisatie](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span><span class="sxs-lookup"><span data-stu-id="d11b2-126">For more information, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>
    - <span data-ttu-id="d11b2-127">**Pass Through-verificatie (PTA)** biedt een eenvoudige oplossing voor wachtwoordvalidatie voor Azure AD-services.</span><span class="sxs-lookup"><span data-stu-id="d11b2-127">**Pass-through Authentication (PTA)** provides a simple password validation solution for Azure AD-based services.</span></span> <span data-ttu-id="d11b2-128">PTA gebruikt een agent die op een of meer on-premises servers wordt uitgevoerd om de gebruikersverificaties rechtstreeks met uw lokale AD DS te valideren.</span><span class="sxs-lookup"><span data-stu-id="d11b2-128">PTA uses an agent running on one or more on-premises servers to validate the user authentications directly with your on-premises AD DS.</span></span> <span data-ttu-id="d11b2-129">Voor meer informatie raadpleegt u [aanmelden als gebruiker met Azure Active Directory Pass Through-verificatie](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).</span><span class="sxs-lookup"><span data-stu-id="d11b2-129">For more information, see [User sign-in with Azure Active Directory Pass-through Authentication](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).</span></span>
- <span data-ttu-id="d11b2-130">Met **federatieve verificatie**wordt het verificatieproces omgeleid naar een andere identiteitsprovider via een identiteitsfederatieserver, zoals Active Directory Federation Services (AD FS), voor aanmelding van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="d11b2-130">With **federated authentication**, the authentication process is redirected to another identity provider through an identity federation server, such as Active Directory Federation Services (AD FS), for a user’s sign-in.</span></span> <span data-ttu-id="d11b2-131">De identiteitsprovider kan aanvullende verificatiemethoden bieden, zoals op smartcards gebaseerde verificatie.</span><span class="sxs-lookup"><span data-stu-id="d11b2-131">The identity provider can provide additional authentication methods, such as smartcard-based authentication.</span></span> <span data-ttu-id="d11b2-132">Zie voor meer informatie [het kiezen van de juiste verificatiemethode voor uw Azure Active Directory hybride identiteitsoplossing](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn).</span><span class="sxs-lookup"><span data-stu-id="d11b2-132">For more information, see [Choosing the right authentication method for your Azure Active Directory hybrid identity solution](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn).</span></span>

<span data-ttu-id="d11b2-133">Bekijk deze video voor een overzicht van identiteitsmodellen en verificatie voor Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="d11b2-133">Watch this video for an overview of identity models and authentication for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="d11b2-134"><p> </p></span><span class="sxs-lookup"><span data-stu-id="d11b2-134"><p> </p></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="d11b2-135">Nadat u de hybride-identiteitsoplossing hebt vastgesteld, downloadt en voert u het [hulpprogramma voor het oplossen van fouten met IdFix Directory-synchronisatie](https://www.microsoft.com/download/details.aspx?id=36832) uit om uw AD DS te analyseren op problemen.</span><span class="sxs-lookup"><span data-stu-id="d11b2-135">After you've determined your hybrid identity solution, download and run the [IdFix Directory Synchronization Error Remediation Tool](https://www.microsoft.com/download/details.aspx?id=36832) to analyze your AD DS for issues.</span></span>

<span data-ttu-id="d11b2-136">Wanneer u alle problemen hebt opgelost die met het hulpprogramma IdFix zijn geïdentificeerd, raadpleegt u [wachtwoord hash-synchronisatie implementeren](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) voor hulp bij het installeren van de Azure AD Connect-hulpmiddelen en het configureren van adreslijstsynchronisatie tussen uw on-premises AD DS en de Azure AD-tenant voor uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="d11b2-136">After resolving all of the issues identified by the IdFix tool, see [Implement password hash synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) for guidance on installing the Azure AD Connect tool and configuring directory synchronization between your on-premises AD DS and the Azure AD tenant for your Microsoft 365 subscription.</span></span> <span data-ttu-id="d11b2-137">Nadat de synchronisatie is gestart, houdt u uw gebruikersaccounts en -groepen bij met uw on-premises-identiteitsprovider, zoals AD DS.</span><span class="sxs-lookup"><span data-stu-id="d11b2-137">After synchronization starts, you'll maintain your user accounts and groups with your on-premises identity provider, such as AD DS.</span></span>

<span data-ttu-id="d11b2-138">Microsoft biedt een aantal aanbevelingen voor [identiteits- en apparaattoegang](microsoft-365-policies-configurations.md) om te zorgen dat uw personeel veilig en productief blijft.</span><span class="sxs-lookup"><span data-stu-id="d11b2-138">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> 

- <span data-ttu-id="d11b2-139">Zie voor meer informatie over de aanbevolen vereisten voor hybride omgevingen de kolom **Active Directory met hash-synchronisatie** onder [vereisten](identity-access-prerequisites.md#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="d11b2-139">For recommended requirements for hybrid environments, see the **Active Directory with password hash sync** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span> 

- <span data-ttu-id="d11b2-140">Zie de kolom **alleen Cloud** onder [vereisten](identity-access-prerequisites.md#prerequisites)voor aanbevolen vereisten voor alleen Cloud omgevingen.</span><span class="sxs-lookup"><span data-stu-id="d11b2-140">For recommended requirements for cloud only environments, see the **Cloud only** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span>

<span data-ttu-id="d11b2-141">Wanneer uw on-premises gebruikers en groepen in Azure AD aanwezig zijn, kunt u beginnen met het toewijzen van licenties en het gebruik van productiviteitslasten zoals OneDrive voor Bedrijven en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d11b2-141">Once your on-premises users and groups are present in Azure AD, you can start assigning licenses and using productivity workloads such as OneDrive for Business and Exchange Online.</span></span>

|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="d11b2-143">Testlabrichtlijn: wachtwoord-hash-synchronisatie</span><span class="sxs-lookup"><span data-stu-id="d11b2-143">Test Lab Guide: Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)<br> [<span data-ttu-id="d11b2-144">Testlabrichtlijn: pass-through-verificatie</span><span class="sxs-lookup"><span data-stu-id="d11b2-144">Test Lab Guide: Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md) |
|||

<span data-ttu-id="d11b2-145">Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-sync) voor deze sectie bekijken.</span><span class="sxs-lookup"><span data-stu-id="d11b2-145">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync) corresponding to this section.</span></span>

<a name="identity-sync-health"></a>
## <a name="monitor-synchronization-health"></a><span data-ttu-id="d11b2-146">Synchronisatiestatus bewaken</span><span class="sxs-lookup"><span data-stu-id="d11b2-146">Monitor synchronization health</span></span>

<span data-ttu-id="d11b2-147">*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="d11b2-147">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="d11b2-148">In deze sectie installeert u een Azure AD Connect Health-agent op elk van uw on-premises AD DS-domeincontrollers om uw identiteitsinfrastructuur en de synchronisatieservices van Azure AD Connect te bewaken.</span><span class="sxs-lookup"><span data-stu-id="d11b2-148">In this section, you'll install an Azure AD Connect Health agent on each of your on-premises AD DS domain controllers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect.</span></span> <span data-ttu-id="d11b2-149">De bewakingsinformatie wordt beschikbaar gesteld in een Azure AD Connect Health-portal waar u waarschuwingen, prestatiebewaking, gebruiksanalyses en andere informatie kunt bekijken.</span><span class="sxs-lookup"><span data-stu-id="d11b2-149">The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

![Onderdelen van Azure AD Connect Health](../media/identity-add-user-accounts/identity-azure-ad-connect-health.png)

<span data-ttu-id="d11b2-151">De belangrijkste ontwerpbeslissing over hoe u Azure AD Connect Health gaat gebruiken, is gebaseerd op hoe u Azure AD Connect gebruikt:</span><span class="sxs-lookup"><span data-stu-id="d11b2-151">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="d11b2-152">Als u de optie **beheerde verificatie** gebruikt, begint u met [Azure AD Connect Health gebruiken met synchronisatie](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync), om Azure AD Connect Health te begrijpen en te configureren.</span><span class="sxs-lookup"><span data-stu-id="d11b2-152">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="d11b2-153">Als u alleen de namen synchroniseert van de accounts en groepen met **federatieve verificatie** met Active Directory Federation Services (AD FS), begint u met [Azure AD Connect Health gebruiken met AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) om Azure AD Connect Health te begrijpen en te configureren.</span><span class="sxs-lookup"><span data-stu-id="d11b2-153">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="d11b2-154">Wanneer u deze stap hebt voltooid, hebt u:</span><span class="sxs-lookup"><span data-stu-id="d11b2-154">When you complete this section, you’ll have:</span></span>

- <span data-ttu-id="d11b2-155">De Azure AD Connect Health-agent die is geïnstalleerd op uw on-premises servers van de identiteitsprovider.</span><span class="sxs-lookup"><span data-stu-id="d11b2-155">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="d11b2-156">De Azure AD Connect Health-portal met de huidige status van uw on-premises infrastructuur en synchronisatieactiviteiten met de Azure AD-tenant voor uw Microsoft 365- en EMS-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="d11b2-156">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Microsoft 365 subscription.</span></span>

<span data-ttu-id="d11b2-157">Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-sync-health) voor deze stap bekijken.</span><span class="sxs-lookup"><span data-stu-id="d11b2-157">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync-health) for this section.</span></span>



<a name="identity-pw-writeback"></a>
## <a name="simplify-password-updates"></a><span data-ttu-id="d11b2-158">Wachtwoordupdates vereenvoudigen</span><span class="sxs-lookup"><span data-stu-id="d11b2-158">Simplify password updates</span></span>

<span data-ttu-id="d11b2-159">*Deze stap is optioneel voor hybride omgevingen en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="d11b2-159">*This is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="d11b2-160">In deze sectie staat u gebruikers toe hun wachtwoorden opnieuw in te stellen via Azure Active Directory (Azure AD), die vervolgens wordt gerepliceerd naar uw lokale Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="d11b2-160">In this section, you'll allow users to reset their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="d11b2-161">Dit proces wordt het terugschrijven van wachtwoorden genoemd.</span><span class="sxs-lookup"><span data-stu-id="d11b2-161">This process is known as password writeback.</span></span> <span data-ttu-id="d11b2-162">Met het terugschrijven van wachtwoorden hoeven gebruikers hun wachtwoorden niet bij te werken via de on-premises AD DS waar de gebruikersaccounts en de bijbehorende kenmerken zijn opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="d11b2-162">With password writeback, users don’t need to update their passwords through the on-premises AD DS where user accounts and their attributes are stored.</span></span> <span data-ttu-id="d11b2-163">Dit is handig bij roaming en gebruikers die extern werken die geen RAS-verbinding met het on-premises netwerk hebben.</span><span class="sxs-lookup"><span data-stu-id="d11b2-163">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="d11b2-164">Wachtwoord terugschrijven is vereist om volledig gebruik te kunnen maken van de mogelijkheden van Identity Protection-functies, zoals vereisen dat gebruikers hun on-premises wachtwoorden wijzigen wanneer er een hoog risico op inbreuk van accounts is gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="d11b2-164">Password writeback is required to fully utilize Azure AD Identity Protection capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="d11b2-165">Zie [Azure AD SSPR met wachtwoord terugschrijven](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback) voor meer informatie en configuratie-instructies.</span><span class="sxs-lookup"><span data-stu-id="d11b2-165">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="d11b2-166">Voer een upgrade uit naar de nieuwste versie van Azure AD Connect om te zorgen voor een optimale ervaring en nieuwe functies zodra deze beschikbaar komen.</span><span class="sxs-lookup"><span data-stu-id="d11b2-166">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released.</span></span> <span data-ttu-id="d11b2-167">Zie [Aangepaste installatie van Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d11b2-167">For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="d11b2-169">Testlabrichtlijn: wachtwoord terugschrijven</span><span class="sxs-lookup"><span data-stu-id="d11b2-169">Test Lab Guide: Password writeback</span></span>](password-writeback-m365-ent-test-environment.md) |
|||

<span data-ttu-id="d11b2-170">Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-pw-writeback) voor deze stap bekijken.</span><span class="sxs-lookup"><span data-stu-id="d11b2-170">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-writeback) for this section.</span></span>

|||
|:-------|:-----|
|![Stap 5](../media/stepnumbers/Step5.png)| [<span data-ttu-id="d11b2-172">Groepen gebruiken voor beheer</span><span class="sxs-lookup"><span data-stu-id="d11b2-172">Use groups for management</span></span>](identity-use-group-management.md) |
