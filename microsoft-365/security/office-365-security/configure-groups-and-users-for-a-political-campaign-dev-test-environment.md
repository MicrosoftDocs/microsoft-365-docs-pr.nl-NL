---
title: Groepen en gebruikers configureren - Ontwikkel-/testomgeving voor politieke campagnes
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 0e22bcf3-bad3-42a4-b44f-276e0cf4790f
description: 'Overzicht: maak proefabonnementen voor Office 365 en Enterprise Mobility + Security (EMS) met gebruikers en groepen voor een ontwikkel-/testomgeving voor politieke campagnes.'
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 54d2543313c1a031974876d7fd09b453cc2ec24d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906538"
---
# <a name="configure-groups-and-users-for-a-political-campaign-devtest-environment"></a><span data-ttu-id="d15fd-103">Configureer groepen en gebruikers voor een ontwikkel-/testomgeving voor politieke campagnes</span><span class="sxs-lookup"><span data-stu-id="d15fd-103">Configure groups and users for a political campaign dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d15fd-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="d15fd-104">**Applies to**</span></span>
- [<span data-ttu-id="d15fd-105">Abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="d15fd-105">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)

 <span data-ttu-id="d15fd-106">**Overzicht:** maak proefabonnementen voor Office 365 en Enterprise Mobility + Security (EMS) met gebruikers en groepen voor een ontwikkel-/testomgeving voor politieke campagnes.</span><span class="sxs-lookup"><span data-stu-id="d15fd-106">**Summary:** Create Office 365 and Enterprise Mobility + Security (EMS) trial subscriptions with users and groups for a political campaign dev/test environment.</span></span>

<span data-ttu-id="d15fd-107">Gebruik de instructies in dit artikel om een ontwikkel-/testomgeving te maken met vereenvoudigde gebruikersaccounts en groepen voor de [Microsoft-beveiligingsrichtlijnen voor politieke campagnes, non-profitorganisaties en andere agile organisaties](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md).</span><span class="sxs-lookup"><span data-stu-id="d15fd-107">Use the instructions in this article to create a dev/test environment that includes simplified user accounts and groups for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution.</span></span>

## <a name="phase-1-create-your-office-365-devtest-environment"></a><span data-ttu-id="d15fd-108">Fase 1: creëer uw ontwikkel-/testomgeving voor Office 365</span><span class="sxs-lookup"><span data-stu-id="d15fd-108">Phase 1: Create your Office 365 dev/test environment</span></span>

<span data-ttu-id="d15fd-109">In deze fase creëert u proefabonnementen voor Office 365 E5 en Enterprise Mobility + Security (EMS) E5 voor een fictieve organisatie die een politieke campagne vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="d15fd-109">In this phase, you obtain trial subscriptions for Office 365 E5 and Enterprise Mobility + Security (EMS) E5 for a fictional organization that represents a political campaign.</span></span>

<span data-ttu-id="d15fd-110">Volg eerst de instructies in **Fase 2** van [de lichtgewicht basisconfiguratie](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="d15fd-110">First, follow the instructions in **Phase 2** of [The lightweight base configuration](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>

<span data-ttu-id="d15fd-111">Meld u vervolgens aan voor het proefabonnement EMS E5 en voeg het toe aan dezelfde organisatie als uw proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="d15fd-111">Next, sign up for the EMS E5 trial subscription and add it to the same organization as your trial subscription.</span></span>

1. <span data-ttu-id="d15fd-112">Indien nodig meldt u zich aan bij het beheercentrum met de inloggegevens van het algemene beheerdersaccount van uw proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="d15fd-112">If needed, sign in to the admin center with the credentials of the global administrator account of your trial subscription.</span></span> <span data-ttu-id="d15fd-113">Zie [Waar kan ik me aanmelden?](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) voor hulp.</span><span class="sxs-lookup"><span data-stu-id="d15fd-113">For help, see [Where to sign in](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="d15fd-114">Klik op de tegel **Beheerder**.</span><span class="sxs-lookup"><span data-stu-id="d15fd-114">Click the **Admin** tile.</span></span>

3. <span data-ttu-id="d15fd-115">Klik op het tabblad **Microsoft 365-beheercentrum** in uw browser in de linkernavigatiebalk op **Facturering >** Services.</span><span class="sxs-lookup"><span data-stu-id="d15fd-115">On the **Microsoft 365 admin center** tab in your browser, in the left navigation, click **Billing > Purchase services**.</span></span>

4. <span data-ttu-id="d15fd-116">Zoek op de pagina **Services aanschaffen** naar het item **Enterprise Mobility + Security E5**.</span><span class="sxs-lookup"><span data-stu-id="d15fd-116">On the **Purchase services** page, find the **Enterprise Mobility + Security E5** item.</span></span> <span data-ttu-id="d15fd-117">Plaats de muisaanwijzer erop en klik op **gratis proefversie**.</span><span class="sxs-lookup"><span data-stu-id="d15fd-117">Hover your mouse pointer over it and click **Start free trial**.</span></span>

5. <span data-ttu-id="d15fd-118">Kies op de pagina **Uw bestelling bevestigen** de optie **Nu proberen**.</span><span class="sxs-lookup"><span data-stu-id="d15fd-118">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="d15fd-119">Klik op de pagina **Ontvangst bestelling** op **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="d15fd-119">On the **Order receipt** page, click **Continue**.</span></span>

<span data-ttu-id="d15fd-120">Activeer vervolgens de EMS E5-licentie voor uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="d15fd-120">Next, enable the EMS E5 license for your global administrator account.</span></span>

1. <span data-ttu-id="d15fd-121">Klik op het tabblad **Microsoft 365-beheercentrum** in uw browser in de linkernavigatiebalk op **Gebruikers > Actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="d15fd-121">On the **Microsoft 365 admin center** tab in your browser, in the left navigation, click **Users > Active users**.</span></span>

2. <span data-ttu-id="d15fd-122">Klik op uw globale beheerdersaccount en klik vervolgens op **bewerken** voor **productlicenties**.</span><span class="sxs-lookup"><span data-stu-id="d15fd-122">Click your global administrator account, and then click **Edit** for **Product licenses**.</span></span>

3. <span data-ttu-id="d15fd-123">Schakel in het deelvenster **productlicenties** de productlicentie voor **Enterprise Mobility + Security E5** **in**, klik op **opslaan** en klik tweemaal op **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="d15fd-123">On the **Product licenses** pane, turn the product license for **Enterprise Mobility + Security E5** to **On**, click **Save,** and then click **Close** twice.</span></span>

## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups"></a><span data-ttu-id="d15fd-124">Fase 2: uw Microsoft Azure AD-groepen (Active Directory) maken en configureren</span><span class="sxs-lookup"><span data-stu-id="d15fd-124">Phase 2: Create and configure your Azure Active Directory (AD) groups</span></span>

<span data-ttu-id="d15fd-125">In deze fase maakt en configureert u de Microsoft Azure AD-groepen voor uw campagne.</span><span class="sxs-lookup"><span data-stu-id="d15fd-125">In this phase, you create and configure the Azure AD groups for your campaign.</span></span>

<span data-ttu-id="d15fd-126">Maak eerst een set groepen voor een normale politieke campagne met de Microsoft Azure-portal.</span><span class="sxs-lookup"><span data-stu-id="d15fd-126">First, create a set of groups for a typical political campaign with the Azure portal.</span></span>

1. <span data-ttu-id="d15fd-127">Open een afzonderlijk tabblad in je browser en ga naar de Microsoft Azure-portal op <https://portal.azure.com>.</span><span class="sxs-lookup"><span data-stu-id="d15fd-127">On a separate tab in your browser, go to the Azure portal at <https://portal.azure.com>.</span></span> <span data-ttu-id="d15fd-128">Indien nodig meldt u zich aan met de inloggegevens van het algemene beheerdersaccount van uw proefabonnement op Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="d15fd-128">If needed, sign in with the credentials of the global administrator account for your Office 365 E5 trial subscription.</span></span>

2. <span data-ttu-id="d15fd-129">Klik in de Microsoft Azure-portal op **Azure Active Directory > gebruikers en groepen > alle groepen**.</span><span class="sxs-lookup"><span data-stu-id="d15fd-129">In the Azure portal, click **Azure Active Directory > Users and groups > All groups**.</span></span>

3. <span data-ttu-id="d15fd-130">Voer de volgende stappen uit voor elke groepsnaam in deze lijst:</span><span class="sxs-lookup"><span data-stu-id="d15fd-130">Do the following steps for each group name in this list:</span></span>

   - <span data-ttu-id="d15fd-131">Senior en strategisch personeel</span><span class="sxs-lookup"><span data-stu-id="d15fd-131">Senior and strategic staff</span></span>

   - <span data-ttu-id="d15fd-132">IT-personeel</span><span class="sxs-lookup"><span data-stu-id="d15fd-132">IT staff</span></span>

   - <span data-ttu-id="d15fd-133">Analytisch personeel</span><span class="sxs-lookup"><span data-stu-id="d15fd-133">Analytics staff</span></span>

   - <span data-ttu-id="d15fd-134">Normaal kernpersoneel</span><span class="sxs-lookup"><span data-stu-id="d15fd-134">Regular core staff</span></span>

   - <span data-ttu-id="d15fd-135">Operationeel personeel</span><span class="sxs-lookup"><span data-stu-id="d15fd-135">Operations staff</span></span>

   - <span data-ttu-id="d15fd-136">Veldmedewerkers</span><span class="sxs-lookup"><span data-stu-id="d15fd-136">Field staff</span></span>

1. <span data-ttu-id="d15fd-137">Klik in de blade **Alle groepen** op **+ Nieuwe groep**.</span><span class="sxs-lookup"><span data-stu-id="d15fd-137">On the **All groups** blade, click **+ New group**.</span></span>

2. <span data-ttu-id="d15fd-138">Typ de naam van de groep in de lijst in **naam**.</span><span class="sxs-lookup"><span data-stu-id="d15fd-138">Type the group name from the list in **Name**.</span></span>

3. <span data-ttu-id="d15fd-139">Selecteer **dynamische gebruiker** voor **lidmaatschap**.</span><span class="sxs-lookup"><span data-stu-id="d15fd-139">Select **Dynamic user** in **Membership**.</span></span>

4. <span data-ttu-id="d15fd-140">Klik op **ja** voor **Office-functies inschakelen**.</span><span class="sxs-lookup"><span data-stu-id="d15fd-140">Click **Yes** for **Enable Office features**.</span></span>

5. <span data-ttu-id="d15fd-141">Klik op **dynamische query toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="d15fd-141">Click **Add dynamic query**.</span></span>

6. <span data-ttu-id="d15fd-142">Selecteer voor **gebruikers toevoegen waar** de optie **afdeling**.</span><span class="sxs-lookup"><span data-stu-id="d15fd-142">In **Add users where**, select **department**.</span></span>

7. <span data-ttu-id="d15fd-143">Selecteer in het volgende veld **is gelijk aan**.</span><span class="sxs-lookup"><span data-stu-id="d15fd-143">In the next field, select **Equals**.</span></span>

8. <span data-ttu-id="d15fd-144">Typ de groepsnaam uit de lijst in het volgende veld.</span><span class="sxs-lookup"><span data-stu-id="d15fd-144">In the next field, type the group name from the list.</span></span>

9. <span data-ttu-id="d15fd-145">Klik op **query toevoegen** en klik vervolgens op **maken**.</span><span class="sxs-lookup"><span data-stu-id="d15fd-145">Click **Add query**, and then click **Create**.</span></span>

10. <span data-ttu-id="d15fd-146">Klik op **gebruikers en groepen: alle groepen**.</span><span class="sxs-lookup"><span data-stu-id="d15fd-146">Click **Users and groups - All groups**.</span></span>

<span data-ttu-id="d15fd-147">Vervolgens configureert u de groepen zo dat er automatisch Office 365 E5- en EMS E5-licenties worden toegewezen aan leden.</span><span class="sxs-lookup"><span data-stu-id="d15fd-147">Next, you configure the groups so that members are automatically assigned Office 365 E5 and EMS E5 licenses.</span></span>

1. <span data-ttu-id="d15fd-148">Klik in de Microsoft Azure-portal op **licenties voor Azure Active Directory > alle producten**.</span><span class="sxs-lookup"><span data-stu-id="d15fd-148">In the Azure portal, click **Azure Active Directory > Licenses > All products**.</span></span>

2. <span data-ttu-id="d15fd-149">Selecteer in de lijst zowel **Enterprise Mobility + Security E5** als **Office 365 Enterprise E5** en klik vervolgens op **+ Toewijzen**.</span><span class="sxs-lookup"><span data-stu-id="d15fd-149">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **+ Assign**.</span></span>

3. <span data-ttu-id="d15fd-150">Klik in de blade **Licentie toewijzen** op **Gebruikers en groepen**.</span><span class="sxs-lookup"><span data-stu-id="d15fd-150">In the **Assign license** blade, click **Users and groups**.</span></span>

4. <span data-ttu-id="d15fd-151">In de lijst met groepen selecteert u het volgende:</span><span class="sxs-lookup"><span data-stu-id="d15fd-151">In the list of groups, select the following:</span></span>

   - <span data-ttu-id="d15fd-152">Analytisch personeel</span><span class="sxs-lookup"><span data-stu-id="d15fd-152">Analytics staff</span></span>

   - <span data-ttu-id="d15fd-153">Veldmedewerkers</span><span class="sxs-lookup"><span data-stu-id="d15fd-153">Field staff</span></span>

   - <span data-ttu-id="d15fd-154">IT-personeel</span><span class="sxs-lookup"><span data-stu-id="d15fd-154">IT staff</span></span>

   - <span data-ttu-id="d15fd-155">Operationeel personeel</span><span class="sxs-lookup"><span data-stu-id="d15fd-155">Operations staff</span></span>

   - <span data-ttu-id="d15fd-156">Normaal kernpersoneel</span><span class="sxs-lookup"><span data-stu-id="d15fd-156">Regular core staff</span></span>

   - <span data-ttu-id="d15fd-157">Senior en strategisch personeel</span><span class="sxs-lookup"><span data-stu-id="d15fd-157">Senior and strategic staff</span></span>

5. <span data-ttu-id="d15fd-158">Klik op **Selecteren** en klik vervolgens op **Toewijzen**.</span><span class="sxs-lookup"><span data-stu-id="d15fd-158">Click **Select**, and then click **Assign**.</span></span>

6. <span data-ttu-id="d15fd-159">Sluit het tabblad Microsoft Azure-portal in uw browser.</span><span class="sxs-lookup"><span data-stu-id="d15fd-159">Close the Azure portal tab in your browser.</span></span>

## <a name="phase-3-add-your-user-accounts"></a><span data-ttu-id="d15fd-160">Fase 3: uw gebruikersaccounts toevoegen</span><span class="sxs-lookup"><span data-stu-id="d15fd-160">Phase 3: Add your user accounts</span></span>

<span data-ttu-id="d15fd-161">In deze fase voegt u de voorbeeldgebruikersaccounts voor uw politieke campagne toe.</span><span class="sxs-lookup"><span data-stu-id="d15fd-161">In this phase, you add the example user accounts for your political campaign.</span></span>

<span data-ttu-id="d15fd-162">Eerst maakt u [Verbinding met de Windows PowerShell voor Graph-module van Azure Active Directory](../../enterprise/connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="d15fd-162">First, you [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md).</span></span>

<span data-ttu-id="d15fd-163">Vervolgens vult u de naam van uw organisatie in, uw locatie en een gemeenschappelijk wachtwoord in en voert u vervolgens deze opdrachten uit in de opdrachtprompt van Windows PowerShell of de Integrated Scripting Environment (ISE):</span><span class="sxs-lookup"><span data-stu-id="d15fd-163">Next, you fill in your organization name, your location, and a common password, and then run these commands from the PowerShell command prompt or Integrated Script Environment (ISE):</span></span>

```powershell
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$deptName="Senior and strategic staff"
$userNames=@("Candidate","ChiefOfStaff","Strategic1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="IT staff"
$userNames=@("ITAdmin1","ITAdmin2")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Analytics staff"
$userNames=@("DataScientist1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Regular core staff"
$userNames=@("Regular1","Regular2")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Operations staff"
$userNames=@("Operations1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Field staff"
$userNames=@("FieldConsultant1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
```

> [!IMPORTANT]
> <span data-ttu-id="d15fd-164">U gebruikt hier een gemeenschappelijk wachtwoord voor automatisering en configuratiegemak in een ontwikkel-/testomgeving.</span><span class="sxs-lookup"><span data-stu-id="d15fd-164">The use of a common password here is for automation and ease of configuration for a dev/test environment.</span></span> <span data-ttu-id="d15fd-165">Dit wordt afgeraden voor productie-omgevingen.</span><span class="sxs-lookup"><span data-stu-id="d15fd-165">This is not recommended for production subscriptions.</span></span> <span data-ttu-id="d15fd-166">Als u zich aanmeldt met een van deze nieuwe gebruikersaccounts, wordt u gevraagd het wachtwoord te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="d15fd-166">As you sign in with each of these new user accounts, you will be prompted to change the password.</span></span>

<span data-ttu-id="d15fd-167">Gebruik deze stappen om te controleren of lidmaatschap van een dynamische groep en groepsgebaseerde licenties correct werken.</span><span class="sxs-lookup"><span data-stu-id="d15fd-167">Use these steps to verify that dynamic group membership and group-based licensing are working correctly.</span></span>

1. <span data-ttu-id="d15fd-168">Klik in het tabblad **Microsoft Office voor Thuisgebruik** van uw browser op de tegel **Beheerder**.</span><span class="sxs-lookup"><span data-stu-id="d15fd-168">From the **Microsoft Office Home** tab of your browser, click the **Admin** tile.</span></span>

2. <span data-ttu-id="d15fd-169">Klik in het nieuwe tabblad **Microsoft 365-beheercentrum** van uw browser op **Gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="d15fd-169">From the new **Microsoft 365 admin center** tab of your browser, click **Users**.</span></span>

3. <span data-ttu-id="d15fd-170">Klik in de lijst met gebruikers op **gegadigde**.</span><span class="sxs-lookup"><span data-stu-id="d15fd-170">In the list of users, click **Candidate**.</span></span>

4. <span data-ttu-id="d15fd-171">Controleer in het deelvenster met de eigenschappen van het **kandidaat**-gebruikersaccount of:</span><span class="sxs-lookup"><span data-stu-id="d15fd-171">In the pane that lists the properties of the **Candidate** user account, verify that:</span></span>

   - <span data-ttu-id="d15fd-172">Het lid is van de groep **Senior en strategisch personeel** (in **groepslidmaatschappen**).</span><span class="sxs-lookup"><span data-stu-id="d15fd-172">It is a member of the **Senior and strategic staff** group (in **Group memberships**).</span></span>

   - <span data-ttu-id="d15fd-173">Het de licenties **Enterprise Mobility + Security E5** en **Office 365 Enterprise E5** heeft toegewezen gekregen (in **productlicenties**).</span><span class="sxs-lookup"><span data-stu-id="d15fd-173">It has been assigned the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses (in **Product licenses**).</span></span>

5. <span data-ttu-id="d15fd-174">Sluit het deelvenster voor het gebruikersaccount **gegadigde**.</span><span class="sxs-lookup"><span data-stu-id="d15fd-174">Close the **Candidate** user account pane.</span></span>

## <a name="record-values-for-future-reference"></a><span data-ttu-id="d15fd-175">Noteer waarden voor toekomstig gebruik</span><span class="sxs-lookup"><span data-stu-id="d15fd-175">Record values for future reference</span></span>

<span data-ttu-id="d15fd-176">Noteer deze waarden voor het werken met de proefabonnementen voor Office 365 en EMS voor deze ontwikkel- en testomgeving:</span><span class="sxs-lookup"><span data-stu-id="d15fd-176">Record these values for working with the Office 365 and EMS trial subscriptions for this dev/test environment:</span></span>

- <span data-ttu-id="d15fd-177">De naam van de organisatie voor uw proefabonnement:</span><span class="sxs-lookup"><span data-stu-id="d15fd-177">Your trial subscription organization name:</span></span> ![Onderstrepen](../../media/Common-Images/TableLine.png)

  <span data-ttu-id="d15fd-179">Voor de domeinnaam van het proefabonnement van contoso.onmicrosoft.com is de naam van de organisatie 'contoso'.</span><span class="sxs-lookup"><span data-stu-id="d15fd-179">For example, for the trial subscription domain name of contoso.onmicrosoft.com, the organization name is "contoso".</span></span>

- <span data-ttu-id="d15fd-180">De naam van de globale beheerder:</span><span class="sxs-lookup"><span data-stu-id="d15fd-180">The global administrator name:</span></span> ![Onderstrepen](../../media/Common-Images/TableLine.png)<span data-ttu-id="d15fd-182">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="d15fd-182">.onmicrosoft.com</span></span>

  <span data-ttu-id="d15fd-183">Sla het wachtwoord voor dit account en het algemene wachtwoord voor de andere gebruikersaccounts op een veilige locatie op.</span><span class="sxs-lookup"><span data-stu-id="d15fd-183">Record the password for this account and the common initial password for the other user accounts in a secure location.</span></span>

## <a name="next-step"></a><span data-ttu-id="d15fd-184">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="d15fd-184">Next step</span></span>

<span data-ttu-id="d15fd-185">Maak de vier verschillende soorten SharePoint Online-teamsites in deze ontwikkel-/testomgeving met [teamsites maken in een ontwikkel-en testomgeving voor politieke campagnes](create-team-sites-in-a-political-campaign-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="d15fd-185">Build the four different types of SharePoint Online team sites in this dev/test environment with [Create team sites in a political campaign dev/test environment](create-team-sites-in-a-political-campaign-dev-test-environment.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d15fd-186">Zie ook</span><span class="sxs-lookup"><span data-stu-id="d15fd-186">See also</span></span>

[<span data-ttu-id="d15fd-187">Microsoft-beveiligingsrichtlijnen voor politieke campagnes, non-profitorganisaties en andere flexibele organisaties</span><span class="sxs-lookup"><span data-stu-id="d15fd-187">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[<span data-ttu-id="d15fd-188">Team sites maken in een ontwikkel-en testomgeving voor politieke campagnes</span><span class="sxs-lookup"><span data-stu-id="d15fd-188">Create team sites in a political campaign dev/test environment</span></span>](create-team-sites-in-a-political-campaign-dev-test-environment.md)

[<span data-ttu-id="d15fd-189">Testlabrichtlijnen voor cloudacceptatie (TLG's)</span><span class="sxs-lookup"><span data-stu-id="d15fd-189">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="d15fd-190">Cloud adoption and hybrid solutions</span><span class="sxs-lookup"><span data-stu-id="d15fd-190">Cloud adoption and hybrid solutions</span></span>](/office365/enterprise/cloud-adoption-and-hybrid-solutions)