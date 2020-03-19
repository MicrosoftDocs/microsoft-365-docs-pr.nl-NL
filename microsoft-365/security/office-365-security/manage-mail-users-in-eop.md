---
title: E-mailgebruikers beheren in EOP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Het definiëren van e-mailgebruikers is een belangrijk onderdeel van het beheer van de Exchange Online Protection (EOP)-service.
ms.openlocfilehash: bdbc3cd54901d53b4a7d01bcf513a9b9a0df1c01
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42810950"
---
# <a name="manage-mail-users-in-eop"></a><span data-ttu-id="cd544-103">E-mailgebruikers beheren in EOP</span><span class="sxs-lookup"><span data-stu-id="cd544-103">Manage mail users in EOP</span></span>

<span data-ttu-id="cd544-104">Het definiëren van e-mailgebruikers is een belangrijk onderdeel van het beheer van de Exchange Online Protection (EOP)-service.</span><span class="sxs-lookup"><span data-stu-id="cd544-104">Defining mail users is an important part of managing the Exchange Online Protection (EOP) service.</span></span> <span data-ttu-id="cd544-105">Er zijn verschillende manieren waarop u gebruikers beheren in EOP:</span><span class="sxs-lookup"><span data-stu-id="cd544-105">There are several ways that you can manage users in EOP:</span></span>

- <span data-ttu-id="cd544-106">**Adreslijstsynchronisatie gebruiken om e-mailgebruikers te beheren:** als uw bedrijf bestaande gebruikersaccounts heeft in een on-premises Active Directory-omgeving, u deze accounts synchroniseren met Azure Active Directory (AD), waar een kopie van de accounts in de cloud is opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="cd544-106">**Use directory synchronization to manage mail users**: If your company has existing user accounts in an on-premises Active Directory environment, you can synchronize those accounts to Azure Active Directory (AD), where a copy of the accounts is stored in the cloud.</span></span> <span data-ttu-id="cd544-107">Wanneer u uw bestaande gebruikersaccounts synchroniseert met Azure Active Directory, u deze gebruikers weergeven in het deelvenster **Geadresseerden** van het Exchange-beheercentrum (EAC).</span><span class="sxs-lookup"><span data-stu-id="cd544-107">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC).</span></span> <span data-ttu-id="cd544-108">Het gebruik van adreslijstsynchronisatie wordt aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="cd544-108">Using directory synchronization is recommended.</span></span>

- <span data-ttu-id="cd544-109">**Gebruik de EAC om e-mailgebruikers te beheren:** E-mailgebruikers rechtstreeks toevoegen en beheren in de EAC.</span><span class="sxs-lookup"><span data-stu-id="cd544-109">**Use the EAC to manage mail users**: Add and manage mail users directly in the EAC.</span></span> <span data-ttu-id="cd544-110">Dit is de eenvoudigste manier om e-mailgebruikers toe te voegen en is handig voor het toevoegen van één gebruiker tegelijk.</span><span class="sxs-lookup"><span data-stu-id="cd544-110">This is the easiest way to add mail users and is useful for adding one user at a time.</span></span>

- <span data-ttu-id="cd544-111">**Gebruik PowerShell om e-mailgebruikers te beheren:** E-mailgebruikers toevoegen en beheren in Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cd544-111">**Use PowerShell to manage mail users**: Add and manage mail users by in Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="cd544-112">Deze methode is handig voor het toevoegen van meerdere records en het maken van scripts.</span><span class="sxs-lookup"><span data-stu-id="cd544-112">This method is useful for adding multiple records and creating scripts.</span></span>

> [!NOTE]
> <span data-ttu-id="cd544-113">U gebruikers toevoegen in het Microsoft 365-beheercentrum, maar deze gebruikers kunnen niet worden gebruikt als e-mailontvangers.</span><span class="sxs-lookup"><span data-stu-id="cd544-113">You can add users in the Microsoft 365 admin center, however these users can't be used as mail recipients.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="cd544-114">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="cd544-114">Before you begin</span></span>

- <span data-ttu-id="cd544-115">Zie [Exchange-beheercentrum in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md)als u het Exchange-beheercentrum wilt openen.</span><span class="sxs-lookup"><span data-stu-id="cd544-115">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="cd544-116">U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="cd544-116">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="cd544-117">Zie het item 'Gebruikers, contactpersonen en rolgroepen' in [Functiemachtigingen in EOP](feature-permissions-in-eop.md)om te zien welke machtigingen u nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="cd544-117">To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in [Feature permissions in EOP](feature-permissions-in-eop.md).</span></span>

- <span data-ttu-id="cd544-118">Houd er rekening mee dat bij het maken van e-mailgebruikers met Exchange Online Protection PowerShell-cmdlets u mogelijk throttling tegenkomen.</span><span class="sxs-lookup"><span data-stu-id="cd544-118">Be aware that when creating mail users by using Exchange Online Protection PowerShell cmdlets, you may encounter throttling.</span></span>

- <span data-ttu-id="cd544-119">De PowerShell-opdrachten in dit onderwerp gebruiken een batchverwerkingsmethode die resulteert in een propagatievertraging van enkele minuten voordat de resultaten van de opdrachten zichtbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="cd544-119">The PowerShell commands in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="cd544-120">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)voor meer informatie over het gebruik van Windows PowerShell om verbinding te maken met Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="cd544-120">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="cd544-121">Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="cd544-121">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="cd544-122">Heb je problemen?</span><span class="sxs-lookup"><span data-stu-id="cd544-122">Having problems?</span></span> <span data-ttu-id="cd544-123">Vraag om hulp op het [Exchange Online Protection-forum.](https://go.microsoft.com/fwlink/p/?linkId=285351)</span><span class="sxs-lookup"><span data-stu-id="cd544-123">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="cd544-124">Adreslijstsynchronisatie gebruiken om e-mailgebruikers te beheren</span><span class="sxs-lookup"><span data-stu-id="cd544-124">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="cd544-125">In deze sectie vindt u informatie over het beheren van e-mailgebruikers met behulp van adreslijstsynchronisatie.</span><span class="sxs-lookup"><span data-stu-id="cd544-125">This section provides information about managing email users by using directory synchronization.</span></span>

<span data-ttu-id="cd544-126">**Toelichting :**</span><span class="sxs-lookup"><span data-stu-id="cd544-126">**Notes**:</span></span>

- <span data-ttu-id="cd544-127">Als u adreslijstsynchronisatie gebruikt om uw geadresseerden te beheren, u nog steeds gebruikers toevoegen en beheren in het Microsoft 365-beheercentrum, maar deze worden niet gesynchroniseerd met uw on-premises Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cd544-127">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="cd544-128">Dit komt omdat adreslijstsynchronisatie alleen ontvangers **synchroniseert vanuit** uw on-premises Active Directory **naar** de cloud.</span><span class="sxs-lookup"><span data-stu-id="cd544-128">This is because directory synchronization only syncs recipients **from** your on-premises Active Directory **to** the cloud.</span></span>

- <span data-ttu-id="cd544-129">Adreslijstsynchronisatie wordt aanbevolen voor gebruik met de volgende functies:</span><span class="sxs-lookup"><span data-stu-id="cd544-129">Directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="cd544-130">**Lijsten met veilige afzenders en geblokkeerde afzenders**in Outlook: Wanneer deze lijsten zijn gesynchroniseerd met de service, hebben deze lijsten voorrang op spamfiltering in de service.</span><span class="sxs-lookup"><span data-stu-id="cd544-130">**Outlook safe sender and blocked sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="cd544-131">Hiermee kunnen gebruikers hun eigen veilige afzender en geblokkeerde afzenderlijsten per gebruiker of per domein beheren.</span><span class="sxs-lookup"><span data-stu-id="cd544-131">This lets users manage their own safe sender and blocked sender lists on a per-user or per-domain basis.</span></span>

  - <span data-ttu-id="cd544-132">**Directory Based Edge Blocking (DBEB)**: Zie [Directory Based Edge Blocking gebruiken om berichten die naar ongeldige geadresseerden worden verzonden, te weigeren.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)</span><span class="sxs-lookup"><span data-stu-id="cd544-132">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="cd544-133">**Spamquarantaine voor eindgebruikers**: Om toegang te krijgen tot de spamquarantaine van de eindgebruiker, moeten eindgebruikers in het beschikken over een geldige Office 365-gebruikersnaam en -wachtwoord.</span><span class="sxs-lookup"><span data-stu-id="cd544-133">**End user spam quarantine**: In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password.</span></span> <span data-ttu-id="cd544-134">EOP-klanten die on-premises postvakken beschermen, moeten geldige e-mailgebruikers zijn.</span><span class="sxs-lookup"><span data-stu-id="cd544-134">EOP customers protecting on-premises mailboxes must be valid email users.</span></span>

  - <span data-ttu-id="cd544-135">**Regels voor e-mailstroom:** Wanneer u adreslijstsynchronisatie gebruikt, worden uw bestaande Active Directory-gebruikers en -groepen automatisch geüpload naar de cloud en u vervolgens regels voor e-mailstroom (ook wel transportregels genoemd) maken die zich richten op specifieke gebruikers en/of groepen zonder ze handmatig toe te voegen via de EAC of Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cd544-135">**Mail flow rules**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules (also known as transport rules) that target specific users and/or groups without having to manually add them via the the EAC or Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="cd544-136">Houd er rekening mee dat [dynamische distributiegroepen](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) niet kunnen worden gesynchroniseerd via adreslijstsynchronisatie.</span><span class="sxs-lookup"><span data-stu-id="cd544-136">Note that [dynamic distribution groups](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="cd544-137">Ontvang de benodigde machtigingen en bereid u voor op adreslijstsynchronisatie, zoals beschreven in [Wat is hybride identiteit met Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span><span class="sxs-lookup"><span data-stu-id="cd544-137">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="to-synchronize-user-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="cd544-138">Gebruikersmappen synchroniseren met Azure Active Directory Connect (AAD Connect)</span><span class="sxs-lookup"><span data-stu-id="cd544-138">To synchronize user directories with Azure Active Directory Connect (AAD Connect)</span></span>

<span data-ttu-id="cd544-139">Als u gebruikers wilt synchroniseren met Azure Active Directory (AAD), moet u eerst **adreslijstsynchronisatie activeren**, zoals beschreven in [Azure AD Connect-synchronisatie: synchronisatie begrijpen en aanpassen](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span><span class="sxs-lookup"><span data-stu-id="cd544-139">To synchronize users to Azure Active Directory (AAD) you first have to **activate directory synchronization**, as described in [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

<span data-ttu-id="cd544-140">Vervolgens is de installatie en configuratie van een on-premises computer om AAD Connect uit te voeren (als u er nog geen hebt - iets dat de moeite waard is om van tevoren te controleren).</span><span class="sxs-lookup"><span data-stu-id="cd544-140">Next is the installation and configuration of an on-premises computer to run AAD Connect (if you don't already have one -- something worth checking ahead of time).</span></span> <span data-ttu-id="cd544-141">In het onderwerp [AAD Connect instellen, het onderwerp expresmanier,](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express) wordt uitgelegd hoe u uw accounts instellen en synchroniseren van on-premises naar Azure AD met AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="cd544-141">The [Setting up AAD Connect, the express way](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express) topic tells you how to setup and synchronize your accounts from on-premises to Azure AD with AAD Connect.</span></span>

<span data-ttu-id="cd544-142">Maar voordat u dat werk doet, moet u ervoor zorgen dat [u aan de vereisten voldoet](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)en uw [installatietype kiezen.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)</span><span class="sxs-lookup"><span data-stu-id="cd544-142">But before you do that work, make certain [you meet prerequisites](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites), and [choose your installation type](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation).</span></span> <span data-ttu-id="cd544-143">De eerdere link is naar een kort artikel voor express installeert.</span><span class="sxs-lookup"><span data-stu-id="cd544-143">The earlier link is to a short article for express installs.</span></span> <span data-ttu-id="cd544-144">U ook artikelen vinden over [aangepaste installaties](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)of [doorgeefverificatie](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start) als ze nodig zijn.</span><span class="sxs-lookup"><span data-stu-id="cd544-144">You can also find articles on [custom installations](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom), or [pass-through authentication](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start) if they're needed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd544-145">Wanneer u de wizard Configuratie van Azure Active Directory-synchronisatieprogramma's hebt voltooid, wordt het **MSOL_AD_SYNC-account** gemaakt in uw Active Directory-forest.</span><span class="sxs-lookup"><span data-stu-id="cd544-145">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest.</span></span> <span data-ttu-id="cd544-146">Dit account wordt gebruikt om uw on-premises Active Directory-gegevens te lezen en te synchroniseren.</span><span class="sxs-lookup"><span data-stu-id="cd544-146">This account is used to read and synchronize your on-premises Active Directory information.</span></span> <span data-ttu-id="cd544-147">Zorg ervoor dat TCP 443 op uw lokale mapsynchronisatieserver is geopend om de synchronisatie van de map correct te laten werken.</span><span class="sxs-lookup"><span data-stu-id="cd544-147">In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="cd544-148">Nadat u uw synchronisatie hebt geconfigureerd, moet u controleren of EOP correct synchroniseert.</span><span class="sxs-lookup"><span data-stu-id="cd544-148">After configuring your sync, be sure to verify that EOP is synchronizing correctly.</span></span> <span data-ttu-id="cd544-149">Ga in de EAC naar **Geadresseerden** \> **contactpersonen** en bekijk dat de lijst met gebruikers correct is gesynchroniseerd vanuit uw on-premises omgeving.</span><span class="sxs-lookup"><span data-stu-id="cd544-149">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>

## <a name="use-the-eac-to-manage-mail-users"></a><span data-ttu-id="cd544-150">De EAC gebruiken om e-mailgebruikers te beheren</span><span class="sxs-lookup"><span data-stu-id="cd544-150">Use the EAC to manage mail users</span></span>

<span data-ttu-id="cd544-151">In deze sectie vindt u informatie over het rechtstreeks toevoegen en beheren van e-mailgebruikers in de EAC.</span><span class="sxs-lookup"><span data-stu-id="cd544-151">This section provides information about adding and managing email users directly in the EAC.</span></span>

### <a name="use-the-eac-to-add-a-mail-user"></a><span data-ttu-id="cd544-152">De EAC gebruiken om een e-mailgebruiker toe te voegen</span><span class="sxs-lookup"><span data-stu-id="cd544-152">Use the EAC to add a mail user</span></span>

1. <span data-ttu-id="cd544-153">Maak een e-mailgebruiker door naar **Geadresseerden** \> **contactpersonen** in de EAC te gaan en vervolgens op **Nieuw +**.</span><span class="sxs-lookup"><span data-stu-id="cd544-153">Create an email user by going to go to **Recipients** \> **Contacts** in the EAC, and then clicking **New +**.</span></span>

2. <span data-ttu-id="cd544-154">Voer op de pagina **Nieuwe e-mailgebruiker** de gegevens van de gebruiker in, waaronder:</span><span class="sxs-lookup"><span data-stu-id="cd544-154">On the **New mail user** page, enter the user's information, including the following:</span></span>

   ****

   |<span data-ttu-id="cd544-155">**Eigenschap E-mailgebruiker**</span><span class="sxs-lookup"><span data-stu-id="cd544-155">**Mail user property**</span></span>|<span data-ttu-id="cd544-156">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="cd544-156">**Description**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="cd544-157">**Voornaam**, **Initialen**en **Achternaam**</span><span class="sxs-lookup"><span data-stu-id="cd544-157">**First name**, **Initials**, and **Last name**</span></span>|<span data-ttu-id="cd544-158">Typ de volledige naam van de gebruiker in de juiste vakken.</span><span class="sxs-lookup"><span data-stu-id="cd544-158">Type the user's full name in the appropriate boxes.</span></span>|
   |<span data-ttu-id="cd544-159">**Weergavenaam**</span><span class="sxs-lookup"><span data-stu-id="cd544-159">**Display name**</span></span>|<span data-ttu-id="cd544-160">Typ een naam met maximaal 64 tekens.</span><span class="sxs-lookup"><span data-stu-id="cd544-160">Type a name, using up to 64 characters.</span></span> <span data-ttu-id="cd544-161">Standaard worden in dit vak de namen weergegeven in de vakken **Voornaam,** **Initialen**en **Achternaam.**</span><span class="sxs-lookup"><span data-stu-id="cd544-161">By default, this box shows the names in the **First name**, **Initials**, and **Last name** boxes if any.</span></span> <span data-ttu-id="cd544-162">De weergavenaam is vereist.</span><span class="sxs-lookup"><span data-stu-id="cd544-162">The display name is required.</span></span>|
   |<span data-ttu-id="cd544-163">**Alias**</span><span class="sxs-lookup"><span data-stu-id="cd544-163">**Alias**</span></span>|<span data-ttu-id="cd544-164">Typ een unieke alias met maximaal 64 tekens voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="cd544-164">Type a unique alias, using up to 64 characters, for the user.</span></span> <span data-ttu-id="cd544-165">De alias is vereist.</span><span class="sxs-lookup"><span data-stu-id="cd544-165">The alias is required.</span></span>|
   |<span data-ttu-id="cd544-166">**Extern e-mailadres**</span><span class="sxs-lookup"><span data-stu-id="cd544-166">**External email address**</span></span>|<span data-ttu-id="cd544-167">Typ het externe e-mailadres van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="cd544-167">Type the external email address of the user.</span></span>|
   |<span data-ttu-id="cd544-168">**Gebruikersnaam**</span><span class="sxs-lookup"><span data-stu-id="cd544-168">**User id**</span></span>|<span data-ttu-id="cd544-169">Typ de naam die de e-mailgebruiker zal gebruiken om zich aan te melden bij de service.</span><span class="sxs-lookup"><span data-stu-id="cd544-169">Type the name that the mail user will use to sign in to the service.</span></span> <span data-ttu-id="cd544-170">De aanmeldingsnaam van de gebruiker bestaat uit een gebruikersnaam aan de linkerkant van het at (@) symbool en een achtervoegsel aan de rechterkant.</span><span class="sxs-lookup"><span data-stu-id="cd544-170">The user sign-in name consists of a user name on the left side of the at (@) symbol and a suffix on the right side.</span></span> <span data-ttu-id="cd544-171">Meestal is het achtervoegsel de domeinnaam waarin het gebruikersaccount zich bevindt.</span><span class="sxs-lookup"><span data-stu-id="cd544-171">Typically, the suffix is the domain name in which the user account resides.</span></span>|
   |<span data-ttu-id="cd544-172">**Nieuw wachtwoord**</span><span class="sxs-lookup"><span data-stu-id="cd544-172">**New password**</span></span>|<span data-ttu-id="cd544-173">Typ het wachtwoord dat de e-mailgebruiker gebruikt om zich aan te melden bij de service.</span><span class="sxs-lookup"><span data-stu-id="cd544-173">Type the password that the mail user will use to sign in to the service.</span></span> <span data-ttu-id="cd544-174">Zorg ervoor dat het wachtwoord dat u verstrekt voldoet aan de wachtwoordlengte, complexiteit en geschiedenisvereisten van het domein waarin u het gebruikersaccount maakt.</span><span class="sxs-lookup"><span data-stu-id="cd544-174">Make sure that the password you supply complies with the password length, complexity, and history requirements of the domain in which you're creating the user account.</span></span>|
   |<span data-ttu-id="cd544-175">**Wachtwoord bevestigen**</span><span class="sxs-lookup"><span data-stu-id="cd544-175">**Confirm password**</span></span>|<span data-ttu-id="cd544-176">Typ het wachtwoord opnieuw om het te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="cd544-176">Retype the password to confirm it.</span></span>|

3. <span data-ttu-id="cd544-177">Klik **op Opslaan** om de nieuwe e-mailgebruiker te maken.</span><span class="sxs-lookup"><span data-stu-id="cd544-177">Click **Save** to create the new email user.</span></span> <span data-ttu-id="cd544-178">De nieuwe gebruiker moet worden weergegeven in de lijst met gebruikers.</span><span class="sxs-lookup"><span data-stu-id="cd544-178">The new user should appear in the list of users.</span></span>

### <a name="use-the-eac-to-edit-or-remove-a-mail-user"></a><span data-ttu-id="cd544-179">De EAC gebruiken om een e-mailgebruiker te bewerken of te verwijderen</span><span class="sxs-lookup"><span data-stu-id="cd544-179">Use the EAC to edit or remove a mail user</span></span>

- <span data-ttu-id="cd544-180">Ga in de EAC naar **Contactpersonen voor geadresseerden** \> **Contacts**.</span><span class="sxs-lookup"><span data-stu-id="cd544-180">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="cd544-181">Klik in de lijst met gebruikers op de gebruiker die **Edit** ![u wilt weergeven of wijzigen en selecteer vervolgens het pictogram](../../media/ITPro-EAC-EditIcon.gif) Bewerken bewerken om de gebruikersinstellingen zo nodig bij te werken.</span><span class="sxs-lookup"><span data-stu-id="cd544-181">In the list of users, click the user that you want to view or change, and then select **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.gif) to update the user settings as needed.</span></span> <span data-ttu-id="cd544-182">U de naam, alias of contactgegevens van de gebruiker wijzigen en u gedetailleerde informatie opnemen over de rol van de gebruiker in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="cd544-182">You can change the user's name, alias, or contact information, and you can record detailed information about the user's role in the organization.</span></span> <span data-ttu-id="cd544-183">U ook een gebruiker **Remove** ![selecteren](../../media/ITPro-EAC-RemoveIcon.gif) en vervolgens pictogram Verwijderen kiezen om deze te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="cd544-183">You can also select a user and then choose **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to delete it.</span></span>

## <a name="use-exchange-online-protection-powershell-to-manage-mail-users"></a><span data-ttu-id="cd544-184">Exchange Online Protection PowerShell gebruiken om e-mailgebruikers te beheren</span><span class="sxs-lookup"><span data-stu-id="cd544-184">Use Exchange Online Protection PowerShell to manage mail users</span></span>

<span data-ttu-id="cd544-185">In deze sectie vindt u informatie over het toevoegen en beheren van e-mailgebruikers met behulp van externe Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cd544-185">This section provides information about adding and managing mail users by using remote Windows PowerShell.</span></span>

### <a name="use-eop-powershell-to-add-a-mail-user"></a><span data-ttu-id="cd544-186">EOP PowerShell gebruiken om een e-mailgebruiker toe te voegen</span><span class="sxs-lookup"><span data-stu-id="cd544-186">Use EOP PowerShell to add a mail user</span></span>

<span data-ttu-id="cd544-187">In dit voorbeeld wordt de cmdlet [Nieuw-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser) gebruikt om een gebruikersaccount met e-mail voor Jeffrey Zeng in EOP te maken met de volgende details:</span><span class="sxs-lookup"><span data-stu-id="cd544-187">This example uses the [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser) cmdlet to create a mail-enabled user account for Jeffrey Zeng in EOP with the following details:</span></span>

- <span data-ttu-id="cd544-188">De voornaam is Jeffrey en de achternaam is Zeng.</span><span class="sxs-lookup"><span data-stu-id="cd544-188">The first name is Jeffrey and the last name is Zeng.</span></span>

- <span data-ttu-id="cd544-189">De naam is Jeffrey en de display naam is Jeffrey Zeng.</span><span class="sxs-lookup"><span data-stu-id="cd544-189">The name is Jeffrey and the display name is Jeffrey Zeng.</span></span>

- <span data-ttu-id="cd544-190">De alias is jeffreyz.</span><span class="sxs-lookup"><span data-stu-id="cd544-190">The alias is jeffreyz.</span></span>

- <span data-ttu-id="cd544-191">Het externe e-mailadres is jzeng@tailspintoys.com.</span><span class="sxs-lookup"><span data-stu-id="cd544-191">The external email address is jzeng@tailspintoys.com.</span></span>

- <span data-ttu-id="cd544-192">De naam van het Office 365-aanmeldingsteken is jeffreyz@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="cd544-192">The Office 365 sign in name is jeffreyz@contoso.onmicrosoft.com.</span></span>

- <span data-ttu-id="cd544-193">Het wachtwoord is Pa$$word1.</span><span class="sxs-lookup"><span data-stu-id="cd544-193">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -LastName Zeng -FirstName Jeffrey -DisplayName "Jeffrey Zeng" -Name Jeffrey -Alias jeffreyz -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -ExternalEmailAddress jeffreyz@tailspintoys.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force)
```

<span data-ttu-id="cd544-194">Voer de volgende opdracht uit om informatie over nieuwe e-mailgebruiker Jeffrey Zeng weer te geven om te controleren of dit werkt:</span><span class="sxs-lookup"><span data-stu-id="cd544-194">To verify that this worked, run the following command to display information about new mail user Jeffrey Zeng:</span></span>

```PowerShell
Get-User -Identity "Jeffrey Zeng"
```

<span data-ttu-id="cd544-195">Zie [Gebruiker worden opdoen](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="cd544-195">For detailed syntax and parameter information, see [Get-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user).</span></span>

### <a name="use-eop-powershell-to-edit-the-properties-of-a-mail-user"></a><span data-ttu-id="cd544-196">EOP PowerShell gebruiken om de eigenschappen van een e-mailgebruiker te bewerken</span><span class="sxs-lookup"><span data-stu-id="cd544-196">Use EOP PowerShell to edit the properties of a mail user</span></span>

<span data-ttu-id="cd544-197">Gebruik de [cmdlets Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) en [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser) om eigenschappen voor e-mailgebruikers weer te geven of te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="cd544-197">Use the [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) and [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser) cmdlets to view or change properties for mail users.</span></span>

<span data-ttu-id="cd544-198">In dit voorbeeld wordt het externe e-mailadres voor Pilar Pinilla ingesteld.</span><span class="sxs-lookup"><span data-stu-id="cd544-198">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="cd544-199">In dit voorbeeld wordt de eigenschap Bedrijf ingesteld voor alle e-mailgebruikers op Contoso.</span><span class="sxs-lookup"><span data-stu-id="cd544-199">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')}
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="cd544-200">Als u wilt controleren of dit heeft gewerkt, gebruikt u de cmdlet [Ontvangen om](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) de wijzigingen te verifiëren.</span><span class="sxs-lookup"><span data-stu-id="cd544-200">To verify that this worked, use the [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) cmdlet to verify the changes.</span></span> <span data-ttu-id="cd544-201">(Houd er rekening mee dat u meerdere eigenschappen voor meerdere e-mailcontactpersonen weergeven.)</span><span class="sxs-lookup"><span data-stu-id="cd544-201">(Note that you can view multiple properties for multiple mail contacts.)</span></span>

```PowerShell
Get-Recipient -Identity "Pilar Pinilla" | Format-List
```

<span data-ttu-id="cd544-202">Voer in het vorige voorbeeld, waar de eigenschap Bedrijf is ingesteld op Contoso voor alle e-mailgebruikers, de volgende opdracht uit om de wijzigingen te verifiëren:</span><span class="sxs-lookup"><span data-stu-id="cd544-202">In the previous example where the Company property was set to Contoso for all mail users, run the following command to verify the changes:</span></span>

```PowerShell
Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')} | Format-List Name,Company
```

> [!IMPORTANT]
> <span data-ttu-id="cd544-203">Deze cmdlet maakt gebruik van een batchverwerkingsmethode die resulteert in een propagatievertraging van enkele minuten voordat de resultaten van de cmdlet zichtbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="cd544-203">This cmdlet uses a batch processing method that results in a propagation delay of a few minutes before the results of the cmdlet are visible.</span></span>

### <a name="use-eop-powershell-to-remove-a-mail-user"></a><span data-ttu-id="cd544-204">EOP PowerShell gebruiken om een e-mailgebruiker te verwijderen</span><span class="sxs-lookup"><span data-stu-id="cd544-204">Use EOP PowerShell to remove a mail user</span></span>

<span data-ttu-id="cd544-205">In dit voorbeeld wordt de cmdlet [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopmailuser) gebruikt om gebruiker Jeffrey Zeng te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="cd544-205">This example uses the [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopmailuser) cmdlet to delete user Jeffrey Zeng:</span></span>

```PowerShell
Remove-EOPMailUser -Identity Jeffrey
```
<span data-ttu-id="cd544-206">Voer de cmdlet [Ontvangen-ontvanger](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) uit om te controleren of de e-mailgebruiker niet meer bestaat.</span><span class="sxs-lookup"><span data-stu-id="cd544-206">To verify that this worked, run the [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) cmdlet to verify that the mail user no longer exists.</span></span>

```PowerShell
Get-Recipient Jeffrey | Format-List
```
