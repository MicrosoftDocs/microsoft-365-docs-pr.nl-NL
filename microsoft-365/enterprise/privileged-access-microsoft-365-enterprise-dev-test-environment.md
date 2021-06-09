---
title: Bevoorrecht toegangsbeheer voor uw Microsoft 365 voor bedrijfstestomgeving
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
description: Gebruik deze testlaboratoriumhandleiding om bevoorrecht toegangsbeheer in te Microsoft 365 voor bedrijfstestomgeving.
ms.openlocfilehash: e9684ebd2aa147049dadfbda9408257ff801aff0
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126415"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="a7e4f-103">Bevoorrecht toegangsbeheer voor uw Microsoft 365 voor bedrijfstestomgeving</span><span class="sxs-lookup"><span data-stu-id="a7e4f-103">Privileged access management for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="a7e4f-104">*Deze testlaborator kan worden gebruikt voor zowel Microsoft 365 voor bedrijven als Office 365 Enterprise testomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="a7e4f-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="a7e4f-105">In dit artikel wordt beschreven hoe u bevoorrecht toegangsbeheer configureert om de beveiliging in uw Microsoft 365 voor ondernemingstestomgeving te verhogen.</span><span class="sxs-lookup"><span data-stu-id="a7e4f-105">This article describes how to configure privileged access management to increase security in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="a7e4f-106">Het configureren van priviledged access management bestaat uit drie fasen:</span><span class="sxs-lookup"><span data-stu-id="a7e4f-106">Configuring priviledged access management involves three phases:</span></span>
- [<span data-ttu-id="a7e4f-107">Fase 1: uw Microsoft 365 voor bedrijfstestomgeving</span><span class="sxs-lookup"><span data-stu-id="a7e4f-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="a7e4f-108">Fase 2: Bevoorrecht toegangsbeheer configureren</span><span class="sxs-lookup"><span data-stu-id="a7e4f-108">Phase 2: Configure privileged access management</span></span>](#phase-2-configure-privileged-access-management)
- [<span data-ttu-id="a7e4f-109">Fase 3: controleren of goedkeuring vereist is voor verhoogde en bevoorrechte taken</span><span class="sxs-lookup"><span data-stu-id="a7e4f-109">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="a7e4f-111">Voor een visuele kaart van alle artikelen in de Microsoft 365 voor enterprise Test Lab Guide stack, gaat u naar Microsoft 365 voor [enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="a7e4f-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="a7e4f-112">Fase 1: uw Microsoft 365 voor bedrijfstestomgeving</span><span class="sxs-lookup"><span data-stu-id="a7e4f-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="a7e4f-113">Als u het beheer van geprivilegieerde toegang op een lichtgewicht manier wilt configureren met de minimumvereisten, volgt u de instructies in [lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="a7e4f-113">If you want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="a7e4f-114">Als u bevoorrecht toegangsbeheer wilt configureren in een gesimuleerde onderneming, volgt u de instructies in [Pass-through-verificatie.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="a7e4f-114">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
>[!NOTE]
><span data-ttu-id="a7e4f-115">Voor het testen van bevoorrecht toegangsbeheer is geen gesimuleerde bedrijfstestomgeving vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een Active Directory Domain Services-forest.</span><span class="sxs-lookup"><span data-stu-id="a7e4f-115">Testing privileged access management doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services forest.</span></span> <span data-ttu-id="a7e4f-116">Het is hier beschikbaar als een optie, zodat u het beheer van geprivilegieerde toegang kunt testen en erop kunt experimenteren in een omgeving die een normale organisatie vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="a7e4f-116">It's provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="a7e4f-117">Fase 2: Bevoorrecht toegangsbeheer configureren</span><span class="sxs-lookup"><span data-stu-id="a7e4f-117">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="a7e4f-118">Configureer in deze fase een groep goedkeurders en schakel geprivilegieerde toegangsbeheer in voor uw Microsoft 365 voor bedrijfstestomgeving.</span><span class="sxs-lookup"><span data-stu-id="a7e4f-118">In this phase, configure an approvers group and enable privileged access management for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="a7e4f-119">Zie Geprivilegieerd toegangsbeheer voor meer informatie en een overzicht van bevoorrecht [toegangsbeheer.](../compliance/privileged-access-management-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a7e4f-119">For additional details and an overview of privileged access management, see [Privileged access management](../compliance/privileged-access-management-overview.md).</span></span>

<span data-ttu-id="a7e4f-120">Als u geprivilegieerde toegang in uw organisatie wilt instellen en gebruiken, voert u de volgende stappen uit.</span><span class="sxs-lookup"><span data-stu-id="a7e4f-120">To set up and use privileged access in your organization, perform the following steps.</span></span>

#### <a name="step-1-create-an-approvers-group"></a>[<span data-ttu-id="a7e4f-121">Stap 1: De groep van een goedkeurder maken</span><span class="sxs-lookup"><span data-stu-id="a7e4f-121">Step 1: Create an approver's group</span></span>](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

<span data-ttu-id="a7e4f-122">Voordat u bevoorrechte toegang gaat gebruiken, bepaalt u wie de goedkeuringsinstantie heeft voor inkomende aanvragen voor toegang tot verhoogde en bevoorrechte taken.</span><span class="sxs-lookup"><span data-stu-id="a7e4f-122">Before you start using privileged access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="a7e4f-123">Alle gebruikers die deel uitmaken van de groep Goedkeurders kunnen toegangsaanvragen goedkeuren.</span><span class="sxs-lookup"><span data-stu-id="a7e4f-123">All users who are part of the Approvers’ group can approve access requests.</span></span> <span data-ttu-id="a7e4f-124">Als u bevoorrechte toegang wilt gebruiken, moet u een beveiligingsgroep met e-mail maken in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a7e4f-124">To use privileged access, you must create a mail-enabled security group in Microsoft 365.</span></span> <span data-ttu-id="a7e4f-125">Geef in uw testomgeving de nieuwe beveiligingsgroep de naam 'Privileged Access Approvers' en voeg de 'Gebruiker 3' toe die eerder is gemaakt in eerdere testlaboratorstappen.</span><span class="sxs-lookup"><span data-stu-id="a7e4f-125">In your test environment, name the new security group "Privileged Access Approvers" and add the "User 3" that was previously created in previous test lab guide steps.</span></span>

#### <a name="step-2-enable-privileged-access"></a>[<span data-ttu-id="a7e4f-126">Stap 2: Geprivilegieerde toegang inschakelen</span><span class="sxs-lookup"><span data-stu-id="a7e4f-126">Step 2: Enable privileged access</span></span>](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

<span data-ttu-id="a7e4f-127">Geprivilegieerde toegang moet expliciet worden ingeschakeld in Microsoft 365 met de standaardgroep voor goedkeurder en moet een set systeemaccounts bevatten die u wilt uitsluiten van het besturingselement toegangsbeheer voor bevoorrechte toegang.</span><span class="sxs-lookup"><span data-stu-id="a7e4f-127">Privileged access needs to be explicitly turned on in Microsoft 365 with the default approver group, and it must include a set of system accounts that you want excluded from the privileged access management access control.</span></span> <span data-ttu-id="a7e4f-128">Zorg ervoor dat u geprivilegieerde toegang in uw organisatie inschakelen voordat u fase 3 van deze handleiding start.</span><span class="sxs-lookup"><span data-stu-id="a7e4f-128">Be sure to enable privileged access in your organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="a7e4f-129">Fase 3: controleren of goedkeuring vereist is voor verhoogde en bevoorrechte taken</span><span class="sxs-lookup"><span data-stu-id="a7e4f-129">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="a7e4f-130">Controleer in deze fase of het beleid voor geprivilegieerde toegang werkt en dat gebruikers goedkeuring nodig hebben om gedefinieerde verhoogde en bevoorrechte taken uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="a7e4f-130">In this phase, verify that the privileged access policy is working and that users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="a7e4f-131">Test de mogelijkheid om een taak uit te voeren DIE NIET is gedefinieerd in een beleid voor geprivilegieerde toegang</span><span class="sxs-lookup"><span data-stu-id="a7e4f-131">Test the ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="a7e4f-132">Maak eerst verbinding met Exchange Management PowerShell met de referenties van een gebruiker die is geconfigureerd als globale beheerder in uw testomgeving en probeer een nieuwe logboekregel te maken.</span><span class="sxs-lookup"><span data-stu-id="a7e4f-132">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="a7e4f-133">De [taak New-JournalRule](/powershell/module/exchange/new-journalrule) is momenteel niet gedefinieerd in een beleid voor geprivilegieerde toegang voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="a7e4f-133">The [New-JournalRule](/powershell/module/exchange/new-journalrule) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="a7e4f-134">Open en meld u op uw lokale computer aan bij de Exchange Online Externe PowerShell-module bij **Microsoft Corporation** Microsoft Exchange Online  >  **Remote PowerShell-module** met het globale beheeraccount voor uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="a7e4f-134">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="a7e4f-135">Maak in Exchange Management PowerShell een nieuwe logboekregel voor uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="a7e4f-135">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="a7e4f-136">Bekijk dat de nieuwe logboekregel is gemaakt in Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a7e4f-136">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="a7e4f-137">Een nieuw beleid voor geprivilegieerde toegang maken voor de New-JournalRule taak</span><span class="sxs-lookup"><span data-stu-id="a7e4f-137">Create a new privileged access policy for the New-JournalRule task</span></span>

>[!NOTE]
><span data-ttu-id="a7e4f-138">Als u de stappen 1 en 2 van fase 2 van deze handleiding nog niet hebt voltooid, moet u de stappen volgen om de groep van een goedkeurder met de naam 'Privilege Access Approvers' te maken om geprivilegieerde toegang in uw testomgeving in te stellen.</span><span class="sxs-lookup"><span data-stu-id="a7e4f-138">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="a7e4f-139">Meld u aan bij [het Microsoft 365 beheercentrum](https://admin.microsoft.com) met referenties van het account Globale beheerder voor uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="a7e4f-139">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="a7e4f-140">Ga in het beheercentrum naar **Instellingen**  >  **beveiligingsinstellingen &**  >  **privacyprivilegetoegang.**</span><span class="sxs-lookup"><span data-stu-id="a7e4f-140">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="a7e4f-141">Selecteer **Toegangsbeleid en -aanvragen beheren.**</span><span class="sxs-lookup"><span data-stu-id="a7e4f-141">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="a7e4f-142">Selecteer **Beleid configureren** en selecteer **vervolgens Beleid toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="a7e4f-142">Select **Configure policies**, and then select **Add a policy**.</span></span>

5. <span data-ttu-id="a7e4f-143">Selecteer of voer in de vervolgkeuzevelden de volgende waarden in:</span><span class="sxs-lookup"><span data-stu-id="a7e4f-143">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="a7e4f-144">**Beleidstype**: Taak</span><span class="sxs-lookup"><span data-stu-id="a7e4f-144">**Policy type**: Task</span></span>

    <span data-ttu-id="a7e4f-145">**Beleidsbereik:** Exchange</span><span class="sxs-lookup"><span data-stu-id="a7e4f-145">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="a7e4f-146">**Beleidsnaam**: Nieuwe logboekregel</span><span class="sxs-lookup"><span data-stu-id="a7e4f-146">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="a7e4f-147">**Goedkeuringstype**: Handmatig</span><span class="sxs-lookup"><span data-stu-id="a7e4f-147">**Approval type**: Manual</span></span>

    <span data-ttu-id="a7e4f-148">**Goedkeuringsgroep:** Privileged Access Approvers</span><span class="sxs-lookup"><span data-stu-id="a7e4f-148">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="a7e4f-149">Selecteer **Maken** en selecteer **vervolgens Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="a7e4f-149">Select **Create**, and then select **Close**.</span></span> <span data-ttu-id="a7e4f-150">Het kan enkele minuten duren voordat het beleid volledig is geconfigureerd en ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="a7e4f-150">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="a7e4f-151">Zorg ervoor dat het beleid volledig is ingeschakeld voordat u de goedkeuringsvereiste in de volgende stap test.</span><span class="sxs-lookup"><span data-stu-id="a7e4f-151">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="a7e4f-152">Testgoedkeuringsvereiste voor New-JournalRule taak die is gedefinieerd in een beleid voor geprivilegieerde toegang</span><span class="sxs-lookup"><span data-stu-id="a7e4f-152">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="a7e4f-153">Open en meld u op uw lokale computer aan bij de externe PowerShell Exchange Online-module van **Microsoft Corporation** Microsoft Exchange Online  >  **Externe PowerShell-module** met behulp van het globale beheeraccount voor uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="a7e4f-153">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="a7e4f-154">Maak in Exchange Management PowerShell een nieuwe logboekregel voor uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="a7e4f-154">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. <span data-ttu-id="a7e4f-155">De fout 'Onvoldoende machtigingen' weergeven in Exchange Management PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a7e4f-155">View the "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="a7e4f-156">Toegang aanvragen om een nieuwe logboekregel te maken met de New-JournalRule taak</span><span class="sxs-lookup"><span data-stu-id="a7e4f-156">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="a7e4f-157">Meld u aan bij het [Microsoft 365 beheercentrum](https://admin.microsoft.com) met het account Globale beheerder voor uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="a7e4f-157">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="a7e4f-158">Ga in het beheercentrum naar **Instellingen**  >  **beveiligingsinstellingen &**  >  **privacyprivilegetoegang.**</span><span class="sxs-lookup"><span data-stu-id="a7e4f-158">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="a7e4f-159">Selecteer **Toegangsbeleid en -aanvragen beheren.**</span><span class="sxs-lookup"><span data-stu-id="a7e4f-159">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="a7e4f-160">Selecteer **Nieuwe aanvraag.**</span><span class="sxs-lookup"><span data-stu-id="a7e4f-160">Select **New request**.</span></span> <span data-ttu-id="a7e4f-161">Selecteer in de vervolgkeuzevelden de juiste waarden voor uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="a7e4f-161">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="a7e4f-162">**Aanvraagtype**: Taak</span><span class="sxs-lookup"><span data-stu-id="a7e4f-162">**Request type**: Task</span></span>

    <span data-ttu-id="a7e4f-163">**Aanvraagbereik**: Exchange</span><span class="sxs-lookup"><span data-stu-id="a7e4f-163">**Request scope**: Exchange</span></span>

    <span data-ttu-id="a7e4f-164">**Aanvraag voor**: Nieuwe logboekregel</span><span class="sxs-lookup"><span data-stu-id="a7e4f-164">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="a7e4f-165">**Duur (uren)**: 2</span><span class="sxs-lookup"><span data-stu-id="a7e4f-165">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="a7e4f-166">**Opmerkingen:** Machtigingen aanvragen voor het maken van een nieuwe logboekregel</span><span class="sxs-lookup"><span data-stu-id="a7e4f-166">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="a7e4f-167">Selecteer **Opslaan** en selecteer **vervolgens Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="a7e4f-167">Select **Save**, and then select **Close**.</span></span> <span data-ttu-id="a7e4f-168">Uw aanvraag wordt per e-mail naar de groep van de goedkeurder verzonden.</span><span class="sxs-lookup"><span data-stu-id="a7e4f-168">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="a7e4f-169">Aanvraag voor geprivilegieerde toegang goedkeuren voor het maken van een nieuwe logboekregel</span><span class="sxs-lookup"><span data-stu-id="a7e4f-169">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="a7e4f-170">Meld u aan bij [het Microsoft 365-beheercentrum](https://admin.microsoft.com) met de referenties voor gebruiker 3 in uw testomgeving (lid van de beveiligingsgroep 'Privileged Access Approvers' in uw testomgeving).</span><span class="sxs-lookup"><span data-stu-id="a7e4f-170">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="a7e4f-171">Ga in het beheercentrum naar **Instellingen**  >  **beveiligingsinstellingen &**  >  **privacyprivilegetoegang.**</span><span class="sxs-lookup"><span data-stu-id="a7e4f-171">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="a7e4f-172">Selecteer **Toegangsbeleid en -aanvragen beheren.**</span><span class="sxs-lookup"><span data-stu-id="a7e4f-172">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="a7e4f-173">Selecteer de aanvraag in behandeling en selecteer goedkeuren om **toegang** te verlenen tot het account voor globale beheerders om een nieuwe logboekregel te maken.</span><span class="sxs-lookup"><span data-stu-id="a7e4f-173">Select the pending request, and then select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="a7e4f-174">Het globale beheeraccount (de gebruiker die hier om verzoekt) ontvangt een e-mailbevestiging dat goedkeuring is verleend.</span><span class="sxs-lookup"><span data-stu-id="a7e4f-174">The Global Admin account (the requesting user) will receive an email confirmation that approval was granted.</span></span>

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="a7e4f-175">Test het maken van een nieuwe logboekregel met geprivilegieerde toegang die is goedgekeurd voor de New-JournalRule taak</span><span class="sxs-lookup"><span data-stu-id="a7e4f-175">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="a7e4f-176">Open en meld u op uw lokale computer aan bij de Exchange Online Externe PowerShell-module bij **Microsoft Corporation** Microsoft Exchange Online  >  **Remote PowerShell-module** met het globale beheeraccount voor uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="a7e4f-176">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="a7e4f-177">Maak in Exchange Management PowerShell een nieuwe logboekregel voor uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="a7e4f-177">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="a7e4f-178">Bekijk dat de nieuwe logboekregel is gemaakt in Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a7e4f-178">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="a7e4f-179">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="a7e4f-179">Next step</span></span>

<span data-ttu-id="a7e4f-180">Ontdek extra [functies en](m365-enterprise-test-lab-guides.md#information-protection) mogelijkheden voor informatiebeveiliging in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="a7e4f-180">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="a7e4f-181">Zie ook</span><span class="sxs-lookup"><span data-stu-id="a7e4f-181">See also</span></span>

[<span data-ttu-id="a7e4f-182">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="a7e4f-182">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a7e4f-183">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="a7e4f-183">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="a7e4f-184">Microsoft 365 enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="a7e4f-184">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)
