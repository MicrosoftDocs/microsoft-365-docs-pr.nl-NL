---
title: Beheer van bevoorrechte toegang voor uw Microsoft 365 Enterprise-testomgeving
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: Ent_TLGs
description: Gebruik deze Test Lab Guide om mogelijk te maken dat uw Microsoft 365 Enterprise-testomgeving kan worden beheerd door bevoegde toegang.
ms.openlocfilehash: ce637b94333f088d25e479e61ad2a98176a2f7c6
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42808414"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="06ad3-103">Beheer van bevoorrechte toegang voor uw Microsoft 365 Enterprise-testomgeving</span><span class="sxs-lookup"><span data-stu-id="06ad3-103">Privileged access management for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="06ad3-104">*Deze Test Lab Guide kan worden gebruikt voor zowel Microsoft 365 Enterprise- als Office 365 Enterprise-testomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="06ad3-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="06ad3-105">Met de instructies in dit artikel configureert u beheer van privileged access om de beveiliging in uw Microsoft 365 Enterprise-testomgeving te verhogen.</span><span class="sxs-lookup"><span data-stu-id="06ad3-105">With the instructions in this article, you configure privileged access management to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Test Lab-hulplijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

>[!TIP]
><span data-ttu-id="06ad3-107">Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de Microsoft 365 Enterprise Test Lab Guide stack.</span><span class="sxs-lookup"><span data-stu-id="06ad3-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="06ad3-108">Fase 1: Uw Microsoft 365 Enterprise-testomgeving uitbouwen</span><span class="sxs-lookup"><span data-stu-id="06ad3-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="06ad3-109">Als u gewoon privileged access management op een lichtgewicht manier wilt configureren met de minimumvereisten, volg dan de instructies in [lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="06ad3-109">If you just want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="06ad3-110">Als u beheer van bevoegde toegang wilt configureren in een gesimuleerde onderneming, volgt u de instructies in [Pass-through-verificatie](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="06ad3-110">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
>[!NOTE]
><span data-ttu-id="06ad3-111">Voor het testen van beheer van privileged access is niet de gesimuleerde bedrijfstestomgeving vereist, die een gesimuleerd intranet bevat dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest.</span><span class="sxs-lookup"><span data-stu-id="06ad3-111">Testing privileged access management does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an AD DS forest.</span></span> <span data-ttu-id="06ad3-112">Het wordt hier als optie geleverd, zodat u privileged access management testen en ermee experimenteren in een omgeving die een typische organisatie vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="06ad3-112">It is provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="06ad3-113">Fase 2: Beheer van privileged access configureren</span><span class="sxs-lookup"><span data-stu-id="06ad3-113">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="06ad3-114">In deze fase configureert u een groep met toekeurders en schakelt u privileged access-beheer in voor uw Microsoft 365 Enterprise-testomgeving.</span><span class="sxs-lookup"><span data-stu-id="06ad3-114">In this phase, you configure an approvers group and enable privileged access management for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="06ad3-115">Zie Beheer voor toegang voor bevoegde toegang [in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)voor meer informatie en een overzicht van beheer met bevoorrechte toegang.</span><span class="sxs-lookup"><span data-stu-id="06ad3-115">For additional details and an overview of privileged access management, see [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span></span>

<span data-ttu-id="06ad3-116">Voer de volgende stappen uit om bevoorrechte toegang in te stellen en te gebruiken in uw Office 365-organisatie:</span><span class="sxs-lookup"><span data-stu-id="06ad3-116">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="06ad3-117">Stap 1: De groep van een goedkeurder maken</span><span class="sxs-lookup"><span data-stu-id="06ad3-117">Step 1: Create an approver's group</span></span>](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-1-create-an-approvers-group)

    <span data-ttu-id="06ad3-118">Voordat u toegang tot bevoegdheden gaat gebruiken, bepaalt u wie goedkeuringsinstantie heeft voor binnenkomende verzoeken om toegang tot verhoogde en bevoorrechte taken.</span><span class="sxs-lookup"><span data-stu-id="06ad3-118">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="06ad3-119">Elke gebruiker die deel uitmaakt van de groep van de Fiatrovers, kan toegangsverzoeken goedkeuren.</span><span class="sxs-lookup"><span data-stu-id="06ad3-119">Any user who is part of the Approvers’ group will be able to approve access requests.</span></span> <span data-ttu-id="06ad3-120">Dit is ingeschakeld door een beveiligingsgroep met e-mail te maken in Office 365.</span><span class="sxs-lookup"><span data-stu-id="06ad3-120">This is enabled by creating a mail-enabled security group in Office 365.</span></span> <span data-ttu-id="06ad3-121">Maak een nieuwe beveiligingsgroep met de naam 'Privileged Access-fiatteurs' in uw testomgeving en voeg de 'Gebruiker 3' toe die eerder is gemaakt in eerdere testlabhandleidingstappen.</span><span class="sxs-lookup"><span data-stu-id="06ad3-121">Create a new security group named "Privileged Access Approvers" in your test environment and add the "User 3" previously created in prior test lab guide steps.</span></span>

- [<span data-ttu-id="06ad3-122">Stap 2: Bevoorrechte toegang inschakelen</span><span class="sxs-lookup"><span data-stu-id="06ad3-122">Step 2: Enable privileged access</span></span>](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-2-enable-privileged-access)

    <span data-ttu-id="06ad3-123">Bevoorrechte toegang moet expliciet worden ingeschakeld in Office 365 met de standaardgroep voor goedkeurende goedkeuring en met inbegrip van een reeks systeemaccounts die u wilt uitsluiten van het toegangscontrolebeheer voor bevoegde toegang.</span><span class="sxs-lookup"><span data-stu-id="06ad3-123">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control.</span></span> <span data-ttu-id="06ad3-124">Zorg ervoor dat u bevoorrechte toegang in uw Office 365-organisatie inschakelt voordat u fase 3 van deze handleiding start.</span><span class="sxs-lookup"><span data-stu-id="06ad3-124">Be sure to enable privileged access in your Office 365 organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="06ad3-125">Fase 3: controleren of goedkeuring vereist is voor verhoogde en bevoorrechte taken</span><span class="sxs-lookup"><span data-stu-id="06ad3-125">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="06ad3-126">In deze fase controleert u of het beleid voor bevoorrechte toegang werkt en vereisen gebruikers goedkeuring om gedefinieerde verhoogde en bevoorrechte taken uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="06ad3-126">In this phase, you verify that the privileged access policy is working and users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="06ad3-127">Testvermogen om een taak uit te voeren die NIET is gedefinieerd in een beleid voor bevoorrechte toegang</span><span class="sxs-lookup"><span data-stu-id="06ad3-127">Test ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="06ad3-128">Maak eerst verbinding met Exchange Management PowerShell met de referenties van een gebruiker die is geconfigureerd als globale beheerder in uw testomgeving en probeer een nieuwe logboekregel te maken.</span><span class="sxs-lookup"><span data-stu-id="06ad3-128">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="06ad3-129">De taak [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) is momenteel niet gedefinieerd in een beleid voor bevoorrechte toegang voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="06ad3-129">The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="06ad3-130">Open en meld u op uw lokale computer aan bij de Exchange Online Remote PowerShell Module bij **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** met behulp van het Global Admin-account voor uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="06ad3-130">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="06ad3-131">Maak in Exchange Management PowerShell een nieuwe logboekregel voor uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="06ad3-131">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```

4. <span data-ttu-id="06ad3-132">Bekijk dat de nieuwe logboekregel is gemaakt in Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06ad3-132">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="06ad3-133">Een nieuw beleid voor bevoorrechte toegang maken voor de taak New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="06ad3-133">Create a new privileged access policy for the New-JournalRule task</span></span>

>[!NOTE]
><span data-ttu-id="06ad3-134">Als u de stappen 1 en 2 van fase 2 van deze handleiding nog niet hebt voltooid, voert u de stappen uit om de groep van een goedkeurder met de naam 'Privilege Access-approvers' te maken en bevoorrechte toegang in uw testomgeving in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="06ad3-134">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" and to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="06ad3-135">Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met referenties het Account Globale beheerder voor uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="06ad3-135">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="06ad3-136">Ga in het beheercentrum naar **Instellingen** > **beveiliging & privacybevoorrechte** > **toegang**.</span><span class="sxs-lookup"><span data-stu-id="06ad3-136">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="06ad3-137">Selecteer **Toegangsbeleid en -aanvragen beheren**.</span><span class="sxs-lookup"><span data-stu-id="06ad3-137">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="06ad3-138">Selecteer **Beleid configureren** en selecteer Een beleid **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="06ad3-138">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="06ad3-139">Selecteer of voer in de vervolgkeuzevelden de volgende waarden in:</span><span class="sxs-lookup"><span data-stu-id="06ad3-139">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="06ad3-140">**Beleidstype**: Taak</span><span class="sxs-lookup"><span data-stu-id="06ad3-140">**Policy type**: Task</span></span>

    <span data-ttu-id="06ad3-141">**Beleidsbereik**: Exchange</span><span class="sxs-lookup"><span data-stu-id="06ad3-141">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="06ad3-142">**Beleidsnaam**: Nieuwe logboekregel</span><span class="sxs-lookup"><span data-stu-id="06ad3-142">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="06ad3-143">**Goedkeuringstype**: Handleiding</span><span class="sxs-lookup"><span data-stu-id="06ad3-143">**Approval type**: Manual</span></span>

    <span data-ttu-id="06ad3-144">**Goedkeuringsgroep**: Privileged Access-bekeurders</span><span class="sxs-lookup"><span data-stu-id="06ad3-144">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="06ad3-145">Selecteer **Maken** en **sluit**.</span><span class="sxs-lookup"><span data-stu-id="06ad3-145">Select **Create** and then **Close**.</span></span> <span data-ttu-id="06ad3-146">Het kan enkele minuten duren voordat het beleid volledig is geconfigureerd en ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="06ad3-146">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="06ad3-147">Zorg ervoor dat u de tijd voor het beleid volledig kan inschakelen voordat u de goedkeuringsvereiste in de volgende stap test.</span><span class="sxs-lookup"><span data-stu-id="06ad3-147">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="06ad3-148">Testgoedkeuringsvereiste voor de taak New-JournalRule gedefinieerd in een beleid voor bevoorrechte toegang</span><span class="sxs-lookup"><span data-stu-id="06ad3-148">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="06ad3-149">Open en meld u op uw lokale computer aan bij de Exchange Online Remote PowerShell Module bij **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** met behulp van het Global Admin-account voor uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="06ad3-149">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="06ad3-150">Maak in Exchange Management PowerShell een nieuwe logboekregel voor uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="06ad3-150">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="06ad3-151">Fout 'Onvoldoende machtigingen' weergeven in Exchange Management PowerShell:</span><span class="sxs-lookup"><span data-stu-id="06ad3-151">View "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

```ExchangeManagementPowerShell
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="06ad3-152">Toegang aanvragen om een nieuwe logboekregel te maken met de taak New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="06ad3-152">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="06ad3-153">Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met het Account Globale beheerder voor uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="06ad3-153">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="06ad3-154">Ga in het beheercentrum naar **Instellingen** > **beveiliging & privacybevoorrechte** > **toegang**.</span><span class="sxs-lookup"><span data-stu-id="06ad3-154">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="06ad3-155">Selecteer **Toegangsbeleid en -aanvragen beheren**.</span><span class="sxs-lookup"><span data-stu-id="06ad3-155">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="06ad3-156">Selecteer **Nieuwe aanvraag**.</span><span class="sxs-lookup"><span data-stu-id="06ad3-156">Select **New request**.</span></span> <span data-ttu-id="06ad3-157">Selecteer in de vervolgkeuzevelden de juiste waarden voor uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="06ad3-157">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="06ad3-158">**Type aanvraag**: Taak</span><span class="sxs-lookup"><span data-stu-id="06ad3-158">**Request type**: Task</span></span>

    <span data-ttu-id="06ad3-159">**Aanvraagbereik**: Exchange</span><span class="sxs-lookup"><span data-stu-id="06ad3-159">**Request scope**: Exchange</span></span>

    <span data-ttu-id="06ad3-160">**Verzoek om**: Nieuwe journaalregel</span><span class="sxs-lookup"><span data-stu-id="06ad3-160">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="06ad3-161">**Duur (uren)**: 2</span><span class="sxs-lookup"><span data-stu-id="06ad3-161">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="06ad3-162">**Commentaar**: Toestemming vragen om een nieuwe logboekregel te maken</span><span class="sxs-lookup"><span data-stu-id="06ad3-162">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="06ad3-163">Selecteer **Opslaan** en **sluit.**</span><span class="sxs-lookup"><span data-stu-id="06ad3-163">Select **Save** and then **Close**.</span></span> <span data-ttu-id="06ad3-164">Uw verzoek wordt via e-mail naar de groep van de goedkeurder gestuurd.</span><span class="sxs-lookup"><span data-stu-id="06ad3-164">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="06ad3-165">Aanvragen voor bevoorrechte toegang goedkeuren voor het maken van een nieuwe logboekregel</span><span class="sxs-lookup"><span data-stu-id="06ad3-165">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="06ad3-166">Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met behulp van de referenties voor gebruiker 3 in uw testomgeving (lid van de beveiligingsgroep 'Bevoorrechte toegangs-approvers' in uw testomgeving).</span><span class="sxs-lookup"><span data-stu-id="06ad3-166">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="06ad3-167">Ga in het beheercentrum naar **Instellingen** > **beveiliging & privacybevoorrechte** > **toegang**.</span><span class="sxs-lookup"><span data-stu-id="06ad3-167">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="06ad3-168">Selecteer **Toegangsbeleid en -aanvragen beheren**.</span><span class="sxs-lookup"><span data-stu-id="06ad3-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="06ad3-169">Selecteer het in behandeling zijnde verzoek en selecteer **Goedkeuren** om toegang te verlenen tot het account Globale beheerder om een nieuwe logboekregel te maken.</span><span class="sxs-lookup"><span data-stu-id="06ad3-169">Select the pending request and select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="06ad3-170">Een e-mail met een melding waarin wordt bevestigd dat goedkeuring is verleend, wordt verzonden naar het Global Admin-account (de verzoekende gebruiker).</span><span class="sxs-lookup"><span data-stu-id="06ad3-170">A notification email confirming that approval has been granted will be sent to the Global Admin account (the requesting user).</span></span>  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="06ad3-171">Een nieuwe logboekregel testen met bevoorrechte toegang die is goedgekeurd voor de taak New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="06ad3-171">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="06ad3-172">Open en meld u op uw lokale computer aan bij de Exchange Online Remote PowerShell Module bij **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** met behulp van het Global Admin-account voor uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="06ad3-172">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="06ad3-173">Maak in Exchange Management PowerShell een nieuwe logboekregel voor uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="06ad3-173">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="06ad3-174">Bekijk dat de nieuwe logboekregel is gemaakt in Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06ad3-174">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="06ad3-175">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="06ad3-175">Next step</span></span>

<span data-ttu-id="06ad3-176">Ontdek aanvullende functies en mogelijkheden voor [informatiebescherming](m365-enterprise-test-lab-guides.md#information-protection) in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="06ad3-176">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="06ad3-177">Zie ook</span><span class="sxs-lookup"><span data-stu-id="06ad3-177">See also</span></span>

[<span data-ttu-id="06ad3-178">Microsoft 365 Enterprise Test Lab-handleidingen</span><span class="sxs-lookup"><span data-stu-id="06ad3-178">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="06ad3-179">Microsoft 365 Enterprise implementeren</span><span class="sxs-lookup"><span data-stu-id="06ad3-179">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="06ad3-180">Microsoft 365 Enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="06ad3-180">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
