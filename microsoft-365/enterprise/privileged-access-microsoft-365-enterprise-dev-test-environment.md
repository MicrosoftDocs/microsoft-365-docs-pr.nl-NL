---
title: Privileged access management voor uw Microsoft 365 Enterprise-testomgeving
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
description: Gebruik deze Test Lab-handleiding om beheer van privileged access uw Microsoft 365 Enterprise-testomgeving in te schakelen.
ms.openlocfilehash: 27f63de138f388b0dcbc1bc896bafcb9abc9ed6a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632861"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="62386-103">Privileged access management voor uw Microsoft 365 Enterprise-testomgeving</span><span class="sxs-lookup"><span data-stu-id="62386-103">Privileged access management for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="62386-104">*Deze testlabrichtlijnen kunnen worden gebruikt voor zowel Microsoft 365 Enterprise- als Office 365 Enterprise-testomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="62386-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="62386-105">Met de instructies in dit artikel configureert u beheer van bevoegde toegang om de beveiliging in uw Microsoft 365 Enterprise-testomgeving te verhogen.</span><span class="sxs-lookup"><span data-stu-id="62386-105">With the instructions in this article, you configure privileged access management to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

>[!TIP]
><span data-ttu-id="62386-107">Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart met alle artikelen over de Microsoft 365 Enterprise-testlabrichtlijnen.</span><span class="sxs-lookup"><span data-stu-id="62386-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="62386-108">Fase 1: uw Microsoft 365 Enterprise-testomgeving uitbouwen</span><span class="sxs-lookup"><span data-stu-id="62386-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="62386-109">Als u alleen privileged access management op een lichtgewicht manier wilt configureren met de minimale vereisten, volgt u de instructies in [lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="62386-109">If you just want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="62386-110">Als u privileged access management in een gesimuleerde onderneming wilt configureren, volgt u de instructies in [Pass-through-verificatie.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="62386-110">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
>[!NOTE]
><span data-ttu-id="62386-111">Voor het testen van privileged access management is geen gesimuleerde bedrijfstestomgeving vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest.</span><span class="sxs-lookup"><span data-stu-id="62386-111">Testing privileged access management does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an AD DS forest.</span></span> <span data-ttu-id="62386-112">Het wordt hier als optie aangeboden, zodat u privileged access management testen en ermee experimenteren in een omgeving die een typische organisatie vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="62386-112">It is provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="62386-113">Fase 2: Privileged Access Management configureren</span><span class="sxs-lookup"><span data-stu-id="62386-113">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="62386-114">In deze fase configureert u een groep fiatteurs en schakelt u privileged access management in voor uw Microsoft 365 Enterprise-testomgeving.</span><span class="sxs-lookup"><span data-stu-id="62386-114">In this phase, you configure an approvers group and enable privileged access management for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="62386-115">Zie Privileged access management in Office [365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)voor meer informatie en een overzicht van privileged access management.</span><span class="sxs-lookup"><span data-stu-id="62386-115">For additional details and an overview of privileged access management, see [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span></span>

<span data-ttu-id="62386-116">Volg de volgende stappen voor het instellen en gebruiken van bevoorrechte toegang in uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="62386-116">Follow these steps to set up and use privileged access in your organization:</span></span>

- [<span data-ttu-id="62386-117">Stap 1: De groep van een goedkeurder maken</span><span class="sxs-lookup"><span data-stu-id="62386-117">Step 1: Create an approver's group</span></span>](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-1-create-an-approvers-group)

    <span data-ttu-id="62386-118">Voordat u toegang tot bevoegdheden gaat gebruiken, bepaalt u wie de goedkeuringsinstantie heeft voor binnenkomende aanvragen voor toegang tot verhoogde en bevoorrechte taken.</span><span class="sxs-lookup"><span data-stu-id="62386-118">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="62386-119">Elke gebruiker die deel uitmaakt van de groep Van de Fiatse goedkeurden, kan toegangsverzoeken goedkeuren.</span><span class="sxs-lookup"><span data-stu-id="62386-119">Any user who is part of the Approvers’ group will be able to approve access requests.</span></span> <span data-ttu-id="62386-120">Dit wordt ingeschakeld door een beveiligingsgroep met e-mail te maken in Office 365.</span><span class="sxs-lookup"><span data-stu-id="62386-120">This is enabled by creating a mail-enabled security group in Office 365.</span></span> <span data-ttu-id="62386-121">Maak een nieuwe beveiligingsgroep met de naam 'Voorkeurstoegangsgoeden' in uw testomgeving en voeg de 'Gebruiker 3' toe die eerder is gemaakt in eerdere testlabhandleidingstappen.</span><span class="sxs-lookup"><span data-stu-id="62386-121">Create a new security group named "Privileged Access Approvers" in your test environment and add the "User 3" previously created in prior test lab guide steps.</span></span>

- [<span data-ttu-id="62386-122">Stap 2: Bevoorrechte toegang inschakelen</span><span class="sxs-lookup"><span data-stu-id="62386-122">Step 2: Enable privileged access</span></span>](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-2-enable-privileged-access)

    <span data-ttu-id="62386-123">Bevoegde toegang moet expliciet worden ingeschakeld in Office 365 met de standaardgroep voor goedgekeurde accounts en een set systeemaccounts die u wilt uitsluiten van het toegangsbeheer voor toegang met toegang tot toegang.</span><span class="sxs-lookup"><span data-stu-id="62386-123">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control.</span></span> <span data-ttu-id="62386-124">Zorg ervoor dat u bevoorrechte toegang in uw organisatie inschakelt voordat u fase 3 van deze handleiding start.</span><span class="sxs-lookup"><span data-stu-id="62386-124">Be sure to enable privileged access in your organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="62386-125">Fase 3: Controleren of goedkeuring vereist is voor verhoogde en bevoorrechte taken</span><span class="sxs-lookup"><span data-stu-id="62386-125">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="62386-126">In deze fase controleert u of het beleid voor bevoegde toegang werkt en dat gebruikers goedkeuring nodig hebben om gedefinieerde verhoogde en bevoorrechte taken uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="62386-126">In this phase, you verify that the privileged access policy is working and users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="62386-127">De mogelijkheid testen om een taak uit te voeren die NIET is gedefinieerd in een beleid voor bevoegde toegang</span><span class="sxs-lookup"><span data-stu-id="62386-127">Test ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="62386-128">Maak eerst verbinding met Exchange Management PowerShell met de referenties van een gebruiker die is geconfigureerd als globale beheerder in uw testomgeving en probeer een nieuwe Journal-regel te maken.</span><span class="sxs-lookup"><span data-stu-id="62386-128">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="62386-129">De taak [Nieuw-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) is momenteel niet gedefinieerd in een beleid voor bevoegde toegang voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="62386-129">The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="62386-130">Open op uw lokale computer de Exchange Online Remote PowerShell-module bij **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** met behulp van het Global Admin-account voor uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="62386-130">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="62386-131">Maak in Exchange Management PowerShell een nieuwe Journal-regel voor uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="62386-131">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```

4. <span data-ttu-id="62386-132">Bekijk dat de nieuwe logboekregel is gemaakt in Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="62386-132">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="62386-133">Een nieuw toegangsbeleid voor bevoegde toegang maken voor de taak Nieuw-JournalRule</span><span class="sxs-lookup"><span data-stu-id="62386-133">Create a new privileged access policy for the New-JournalRule task</span></span>

>[!NOTE]
><span data-ttu-id="62386-134">Als u de stappen 1 en 2 van fase 2 van deze handleiding nog niet hebt voltooid, moet u de stappen volgen om de groep van een goedkeurder met de naam 'Privilege Access-goedkeurders' te maken en bevoorrechte toegang in uw testomgeving in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="62386-134">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" and to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="62386-135">Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met referenties het Global Admin-account voor uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="62386-135">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="62386-136">Ga in het beheercentrum naar **Instellingenbeveiliging** > & toegang tot**privacybevoegdheden** > **Privileged access**.</span><span class="sxs-lookup"><span data-stu-id="62386-136">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="62386-137">Selecteer **Toegangsbeleid en -aanvragen beheren**.</span><span class="sxs-lookup"><span data-stu-id="62386-137">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="62386-138">Selecteer **Beleid configureren** en selecteer Een beleid **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="62386-138">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="62386-139">Selecteer of voer in de vervolgkeuzelijst de volgende waarden in:</span><span class="sxs-lookup"><span data-stu-id="62386-139">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="62386-140">**Beleidstype**: Taak</span><span class="sxs-lookup"><span data-stu-id="62386-140">**Policy type**: Task</span></span>

    <span data-ttu-id="62386-141">**Beleidsscope**: Uitwisseling</span><span class="sxs-lookup"><span data-stu-id="62386-141">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="62386-142">**Beleidsnaam**: Nieuwe journaalregel</span><span class="sxs-lookup"><span data-stu-id="62386-142">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="62386-143">**Goedkeuringstype**: Handleiding</span><span class="sxs-lookup"><span data-stu-id="62386-143">**Approval type**: Manual</span></span>

    <span data-ttu-id="62386-144">**Goedkeuringsgroep**: Fiatteurs met bevoorrechte toegang</span><span class="sxs-lookup"><span data-stu-id="62386-144">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="62386-145">Selecteer **Maken** en vervolgens **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="62386-145">Select **Create** and then **Close**.</span></span> <span data-ttu-id="62386-146">Het kan enkele minuten duren voordat het beleid volledig is geconfigureerd en ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="62386-146">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="62386-147">Zorg ervoor dat u de tijd toestaat om het beleid volledig in te schakelen voordat u de goedkeuringsvereiste in de volgende stap test.</span><span class="sxs-lookup"><span data-stu-id="62386-147">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="62386-148">Goedkeuringsvereiste testen voor de taak Nieuw-JournalRule die is gedefinieerd in een beleid voor bevoorrechte toegang</span><span class="sxs-lookup"><span data-stu-id="62386-148">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="62386-149">Open op uw lokale computer de Exchange Online Remote PowerShell-module bij **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** met behulp van een account globale beheer voor uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="62386-149">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="62386-150">Maak in Exchange Management PowerShell een nieuwe Journal-regel voor uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="62386-150">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="62386-151">Fout 'Onvoldoende machtigingen' weergeven in Exchange Management PowerShell:</span><span class="sxs-lookup"><span data-stu-id="62386-151">View "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

```ExchangeManagementPowerShell
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="62386-152">Toegang aanvragen om een nieuwe journaalregel te maken met de taak Nieuw-JournalRule</span><span class="sxs-lookup"><span data-stu-id="62386-152">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="62386-153">Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met het global admin-account voor uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="62386-153">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="62386-154">Ga in het beheercentrum naar **Instellingenbeveiliging** > & toegang tot**privacybevoegdheden** > **Privileged access**.</span><span class="sxs-lookup"><span data-stu-id="62386-154">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="62386-155">Selecteer **Toegangsbeleid en -aanvragen beheren**.</span><span class="sxs-lookup"><span data-stu-id="62386-155">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="62386-156">Selecteer **Nieuw verzoek**.</span><span class="sxs-lookup"><span data-stu-id="62386-156">Select **New request**.</span></span> <span data-ttu-id="62386-157">Selecteer in de vervolgkeuzelijst de juiste waarden voor uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="62386-157">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="62386-158">**Aanvraagtype**: Taak</span><span class="sxs-lookup"><span data-stu-id="62386-158">**Request type**: Task</span></span>

    <span data-ttu-id="62386-159">**Aanvraagbereik**: Exchange</span><span class="sxs-lookup"><span data-stu-id="62386-159">**Request scope**: Exchange</span></span>

    <span data-ttu-id="62386-160">**Aanvraag voor**: Nieuwe journaalregel</span><span class="sxs-lookup"><span data-stu-id="62386-160">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="62386-161">**Duur (uren)**: 2</span><span class="sxs-lookup"><span data-stu-id="62386-161">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="62386-162">**Opmerkingen**: Toestemming vragen om een nieuwe logboekregel te maken</span><span class="sxs-lookup"><span data-stu-id="62386-162">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="62386-163">Selecteer **Opslaan** en vervolgens **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="62386-163">Select **Save** and then **Close**.</span></span> <span data-ttu-id="62386-164">Uw verzoek wordt via e-mail naar de groep van de goedkeurder gestuurd.</span><span class="sxs-lookup"><span data-stu-id="62386-164">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="62386-165">Voorkeurstoegangsaanvraag goedkeuren voor het maken van een nieuwe journaalregel</span><span class="sxs-lookup"><span data-stu-id="62386-165">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="62386-166">Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met behulp van de referenties voor gebruiker 3 in uw testomgeving (lid van de beveiligingsgroep 'Bevoegde toegangs-approvers' in uw testomgeving).</span><span class="sxs-lookup"><span data-stu-id="62386-166">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="62386-167">Ga in het beheercentrum naar **Instellingenbeveiliging** > & toegang tot**privacybevoegdheden** > **Privileged access**.</span><span class="sxs-lookup"><span data-stu-id="62386-167">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="62386-168">Selecteer **Toegangsbeleid en -aanvragen beheren**.</span><span class="sxs-lookup"><span data-stu-id="62386-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="62386-169">Selecteer de aanvraag in behandeling en selecteer **Goedkeuren** om toegang te verlenen tot het global admin-account om een nieuwe logboekregel te maken.</span><span class="sxs-lookup"><span data-stu-id="62386-169">Select the pending request and select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="62386-170">Een e-mail met een melding waarin wordt bevestigd dat er goedkeuring is verleend, wordt verzonden naar het Global Admin-account (de verzoekende gebruiker).</span><span class="sxs-lookup"><span data-stu-id="62386-170">A notification email confirming that approval has been granted will be sent to the Global Admin account (the requesting user).</span></span>  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="62386-171">Een nieuwe logboekregel maken met bevoorrechte toegang die is goedgekeurd voor de taak Nieuw-JournalRule</span><span class="sxs-lookup"><span data-stu-id="62386-171">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="62386-172">Open op uw lokale computer de Exchange Online Remote PowerShell-module bij **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** met behulp van het Global Admin-account voor uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="62386-172">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="62386-173">Maak in Exchange Management PowerShell een nieuwe Journal-regel voor uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="62386-173">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="62386-174">Bekijk dat de nieuwe logboekregel is gemaakt in Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="62386-174">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="62386-175">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="62386-175">Next step</span></span>

<span data-ttu-id="62386-176">Ontdek aanvullende functies en mogelijkheden voor [informatiebescherming](m365-enterprise-test-lab-guides.md#information-protection) in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="62386-176">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="62386-177">Zie ook</span><span class="sxs-lookup"><span data-stu-id="62386-177">See also</span></span>

[<span data-ttu-id="62386-178">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="62386-178">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="62386-179">Microsoft 365 Enterprise implementeren</span><span class="sxs-lookup"><span data-stu-id="62386-179">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="62386-180">Microsoft 365 Enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="62386-180">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
