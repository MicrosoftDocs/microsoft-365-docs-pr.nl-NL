---
title: Privileged access management for your Microsoft 365 for enterprise test environment
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
description: Gebruik deze Test Lab Guide om bevoorrechte toegangsbeheer mogelijk te maken voor uw Microsoft 365 voor bedrijfstestomgeving.
ms.openlocfilehash: e9684ebd2aa147049dadfbda9408257ff801aff0
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126415"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="d2e25-103">Privileged access management for your Microsoft 365 for enterprise test environment</span><span class="sxs-lookup"><span data-stu-id="d2e25-103">Privileged access management for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="d2e25-104">*Deze Test Lab Guide kan worden gebruikt voor zowel Microsoft 365 voor Enterprise- als Office 365 Enterprise-testomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="d2e25-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="d2e25-105">In dit artikel wordt beschreven hoe u een bevoorrecht toegangsbeheer configureert om de beveiliging te verhogen in uw Microsoft 365 voor bedrijfstestomgeving.</span><span class="sxs-lookup"><span data-stu-id="d2e25-105">This article describes how to configure privileged access management to increase security in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="d2e25-106">Bij het configureren van priviledged toegangsbeheer zijn drie fasen nodig:</span><span class="sxs-lookup"><span data-stu-id="d2e25-106">Configuring priviledged access management involves three phases:</span></span>
- [<span data-ttu-id="d2e25-107">Fase 1: De testomgeving van Microsoft 365 voor ondernemingen bouwen</span><span class="sxs-lookup"><span data-stu-id="d2e25-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="d2e25-108">Fase 2: Bevoorrecht toegangsbeheer configureren</span><span class="sxs-lookup"><span data-stu-id="d2e25-108">Phase 2: Configure privileged access management</span></span>](#phase-2-configure-privileged-access-management)
- [<span data-ttu-id="d2e25-109">Fase 3: Controleren of goedkeuring vereist is voor taken met verhoogde bevoegdheden en bevoegdheden</span><span class="sxs-lookup"><span data-stu-id="d2e25-109">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="d2e25-111">Voor een visuele plattegrond van alle artikelen in de Test Lab Guide stack van Microsoft 365 voor ondernemingen gaat u naar [Microsoft 365 for Enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="d2e25-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="d2e25-112">Fase 1: De testomgeving van Microsoft 365 voor ondernemingen bouwen</span><span class="sxs-lookup"><span data-stu-id="d2e25-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="d2e25-113">Als u een bevoorrecht beheer van de toegang wilt configureren op een lichtgewicht manier met de minimale vereisten, volgt u de instructies in [de Basis basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="d2e25-113">If you want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="d2e25-114">Als u bevoorrechte toegangsbeheer wilt configureren in een gesimuleerde onderneming, volgt u de instructies in [Pass Through-verificatie.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="d2e25-114">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
>[!NOTE]
><span data-ttu-id="d2e25-115">Voor het testen van bevoorrechte toegangsbeheer is de gesimuleerde bedrijfstestomgeving niet vereist, die een gesimuleerd intranet bevat dat is verbonden met internet en adreslijstsynchronisatie voor een Active Directory Domain Services-forest.</span><span class="sxs-lookup"><span data-stu-id="d2e25-115">Testing privileged access management doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services forest.</span></span> <span data-ttu-id="d2e25-116">Deze optie is beschikbaar als een optie, zodat u het beheer van bevoorrechte toegang kunt testen en daarmee kunt experimenteren in een omgeving waarin een gewone organisatie wordt vertegenwoordigd.</span><span class="sxs-lookup"><span data-stu-id="d2e25-116">It's provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="d2e25-117">Fase 2: Bevoorrecht toegangsbeheer configureren</span><span class="sxs-lookup"><span data-stu-id="d2e25-117">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="d2e25-118">Configureer in deze fase een goedkeurdersgroep en schakel bevoorrechte toegangsbeheer in voor uw Microsoft 365 voor bedrijfstestomgeving.</span><span class="sxs-lookup"><span data-stu-id="d2e25-118">In this phase, configure an approvers group and enable privileged access management for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="d2e25-119">Zie Privileged access management (Bevoorrechte toegangsbeheer) voor meer informatie en een overzicht [van bevoorrecht toegangsbeheer.](../compliance/privileged-access-management-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d2e25-119">For additional details and an overview of privileged access management, see [Privileged access management](../compliance/privileged-access-management-overview.md).</span></span>

<span data-ttu-id="d2e25-120">Voer de volgende stappen uit om de toegankelijkheidsrechten in uw organisatie in te stellen en te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d2e25-120">To set up and use privileged access in your organization, perform the following steps.</span></span>

#### <a name="step-1-create-an-approvers-group"></a>[<span data-ttu-id="d2e25-121">Stap 1: De groep goedkeurder maken</span><span class="sxs-lookup"><span data-stu-id="d2e25-121">Step 1: Create an approver's group</span></span>](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

<span data-ttu-id="d2e25-122">Voordat u de bevoegde toegang gaat gebruiken, moet u bepalen wie goedkeuringsrechten heeft voor inkomende verzoeken voor toegang tot verhoogde en bevoorrechte taken.</span><span class="sxs-lookup"><span data-stu-id="d2e25-122">Before you start using privileged access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="d2e25-123">Alle gebruikers die deel uitmaken van de groep Goedkeurders kunnen toegangsaanvragen goedkeuren.</span><span class="sxs-lookup"><span data-stu-id="d2e25-123">All users who are part of the Approvers’ group can approve access requests.</span></span> <span data-ttu-id="d2e25-124">Als u bevoegde toegang wilt gebruiken, moet u een beveiligingsgroep met e-mail maken in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d2e25-124">To use privileged access, you must create a mail-enabled security group in Microsoft 365.</span></span> <span data-ttu-id="d2e25-125">Geef in uw testomgeving de nieuwe beveiligingsgroep de naam 'Privileged Access Approvers' en voeg de 'Gebruiker 3' toe die eerder is gemaakt in eerdere test lab guide stappen.</span><span class="sxs-lookup"><span data-stu-id="d2e25-125">In your test environment, name the new security group "Privileged Access Approvers" and add the "User 3" that was previously created in previous test lab guide steps.</span></span>

#### <a name="step-2-enable-privileged-access"></a>[<span data-ttu-id="d2e25-126">Stap 2: Bevoorrechte toegang inschakelen</span><span class="sxs-lookup"><span data-stu-id="d2e25-126">Step 2: Enable privileged access</span></span>](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

<span data-ttu-id="d2e25-127">De toegang met bepaalde bevoegdheden moet expliciet worden ingeschakeld in Microsoft 365 met de standaard goedkeurdergroep en moet een set systeemaccounts bevatten die u wilt uitsluiten van het toegangsbeheer voor toegang tot bevoorrechte toegang.</span><span class="sxs-lookup"><span data-stu-id="d2e25-127">Privileged access needs to be explicitly turned on in Microsoft 365 with the default approver group, and it must include a set of system accounts that you want excluded from the privileged access management access control.</span></span> <span data-ttu-id="d2e25-128">Zorg ervoor dat u de bevoegde toegang in uw organisatie inschakelen voordat u fase 3 van deze handleiding start.</span><span class="sxs-lookup"><span data-stu-id="d2e25-128">Be sure to enable privileged access in your organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="d2e25-129">Fase 3: Controleren of goedkeuring vereist is voor taken met verhoogde bevoegdheden en bevoegdheden</span><span class="sxs-lookup"><span data-stu-id="d2e25-129">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="d2e25-130">In deze fase controleert u of het toegangsbeleid voor bepaalde bevoegdheden werkt en dat gebruikers goedkeuring moeten hebben om gedefinieerde verhoogde en bevoorrechte taken uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="d2e25-130">In this phase, verify that the privileged access policy is working and that users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="d2e25-131">De mogelijkheid testen om een taak uit te voeren DIE NIET is gedefinieerd in een bevoorrecht toegangsbeleid</span><span class="sxs-lookup"><span data-stu-id="d2e25-131">Test the ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="d2e25-132">Maak eerst verbinding met Exchange Management PowerShell met de referenties van een gebruiker die in uw testomgeving is geconfigureerd als globale beheerder en probeer een nieuwe logboekregel te maken.</span><span class="sxs-lookup"><span data-stu-id="d2e25-132">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="d2e25-133">De [taak Nieuwe logboekregel](/powershell/module/exchange/new-journalrule) is momenteel niet gedefinieerd in een toegangsbeleid voor bepaalde bevoegdheden voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d2e25-133">The [New-JournalRule](/powershell/module/exchange/new-journalrule) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="d2e25-134">Open de externe PowerShell-module van **Microsoft Corporation** Microsoft Exchange Online op uw lokale computer en meld u aan bij de externe  >  **PowerShell-module** van Exchange Online met behulp van het hoofdbeheerdersaccount voor uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="d2e25-134">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="d2e25-135">Maak in Exchange Management PowerShell een nieuwe logboekregel voor uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="d2e25-135">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="d2e25-136">U kunt zien dat de nieuwe logboekregel is gemaakt in Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d2e25-136">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="d2e25-137">Een nieuw toegangsbeleid voor de New-JournalRule maken</span><span class="sxs-lookup"><span data-stu-id="d2e25-137">Create a new privileged access policy for the New-JournalRule task</span></span>

>[!NOTE]
><span data-ttu-id="d2e25-138">Als u de stappen 1 en 2 van fase 2 van deze handleiding nog niet hebt voltooid, moet u de stappen volgen om de groep goedkeurders met de naam Bevoegdheden voor toegangsrechten voor goedkeurders te maken om voor uw testomgeving bevoegde toegang te krijgen.</span><span class="sxs-lookup"><span data-stu-id="d2e25-138">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="d2e25-139">Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met de referenties van het globale beheerdersaccount voor uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="d2e25-139">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="d2e25-140">Ga in het beheercentrum naar **Instellingenbeveiliging en**  >  **&**  >  **privacyprivilegetoegang.**</span><span class="sxs-lookup"><span data-stu-id="d2e25-140">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="d2e25-141">Selecteer **Toegangsbeleid en aanvragen beheren.**</span><span class="sxs-lookup"><span data-stu-id="d2e25-141">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="d2e25-142">Selecteer **Beleid configureren** en selecteer **vervolgens Beleid toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="d2e25-142">Select **Configure policies**, and then select **Add a policy**.</span></span>

5. <span data-ttu-id="d2e25-143">Selecteer of typ de volgende waarden in de vervolgkeuzevelden:</span><span class="sxs-lookup"><span data-stu-id="d2e25-143">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="d2e25-144">**Beleidstype**: Taak</span><span class="sxs-lookup"><span data-stu-id="d2e25-144">**Policy type**: Task</span></span>

    <span data-ttu-id="d2e25-145">**Beleidsbereik**: Exchange</span><span class="sxs-lookup"><span data-stu-id="d2e25-145">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="d2e25-146">**Beleidsnaam:** Nieuwe logboekregel</span><span class="sxs-lookup"><span data-stu-id="d2e25-146">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="d2e25-147">**Goedkeuringstype**: Handmatig</span><span class="sxs-lookup"><span data-stu-id="d2e25-147">**Approval type**: Manual</span></span>

    <span data-ttu-id="d2e25-148">**Goedkeuringsgroep:** Bevoegde goedkeurders voor toegang</span><span class="sxs-lookup"><span data-stu-id="d2e25-148">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="d2e25-149">Selecteer **Maken** en vervolgens **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="d2e25-149">Select **Create**, and then select **Close**.</span></span> <span data-ttu-id="d2e25-150">Het kan enkele minuten duren voordat het beleid volledig is geconfigureerd en ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="d2e25-150">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="d2e25-151">Zorg ervoor dat u de tijd voor het beleid volledig heeft ingeschakeld voordat u in de volgende stap de goedkeuringsvereiste test.</span><span class="sxs-lookup"><span data-stu-id="d2e25-151">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="d2e25-152">Goedkeuringsvereiste testen voor de New-JournalRule die is gedefinieerd in een bevoorrecht toegangsbeleid</span><span class="sxs-lookup"><span data-stu-id="d2e25-152">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="d2e25-153">Open de externe PowerShell-module van Microsoft **Corporation** Microsoft Exchange Online op uw lokale computer en meld u aan bij de externe  >  **PowerShell-module** van Exchange Online met behulp van het account van de globale beheerder voor uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="d2e25-153">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="d2e25-154">Maak in Exchange Management PowerShell een nieuwe logboekregel voor uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="d2e25-154">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. <span data-ttu-id="d2e25-155">Bekijk de fout 'Onvoldoende machtigingen' in Exchange Management PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d2e25-155">View the "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="d2e25-156">Toegang aanvragen om een nieuwe logboekregel te maken met New-JournalRule taak</span><span class="sxs-lookup"><span data-stu-id="d2e25-156">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="d2e25-157">Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met het globale beheerdersaccount voor uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="d2e25-157">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="d2e25-158">Ga in het beheercentrum naar **Instellingenbeveiliging en**  >  **&**  >  **privacyprivilegetoegang.**</span><span class="sxs-lookup"><span data-stu-id="d2e25-158">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="d2e25-159">Selecteer **Toegangsbeleid en aanvragen beheren.**</span><span class="sxs-lookup"><span data-stu-id="d2e25-159">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="d2e25-160">Selecteer **Nieuw verzoek.**</span><span class="sxs-lookup"><span data-stu-id="d2e25-160">Select **New request**.</span></span> <span data-ttu-id="d2e25-161">Selecteer in de vervolgkeuzevelden de juiste waarden voor uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="d2e25-161">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="d2e25-162">**Aanvraagtype**: Taak</span><span class="sxs-lookup"><span data-stu-id="d2e25-162">**Request type**: Task</span></span>

    <span data-ttu-id="d2e25-163">**Bereik van aanvraag**: Exchange</span><span class="sxs-lookup"><span data-stu-id="d2e25-163">**Request scope**: Exchange</span></span>

    <span data-ttu-id="d2e25-164">**Aanvraag voor:** nieuwe logboekregel</span><span class="sxs-lookup"><span data-stu-id="d2e25-164">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="d2e25-165">**Duur (uren)**: 2</span><span class="sxs-lookup"><span data-stu-id="d2e25-165">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="d2e25-166">**Opmerkingen:** Machtiging aanvragen om een nieuwe logboekregel te maken</span><span class="sxs-lookup"><span data-stu-id="d2e25-166">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="d2e25-167">Selecteer **Opslaan** en selecteer vervolgens **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="d2e25-167">Select **Save**, and then select **Close**.</span></span> <span data-ttu-id="d2e25-168">Uw aanvraag wordt per e-mail verzonden naar de groep goedkeurder.</span><span class="sxs-lookup"><span data-stu-id="d2e25-168">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="d2e25-169">Verzoek om toegang met bepaalde bevoegdheden goedkeuren voor het maken van een nieuwe logboekregel</span><span class="sxs-lookup"><span data-stu-id="d2e25-169">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="d2e25-170">Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met de referenties voor Gebruiker 3 in uw testomgeving (lid van de beveiligingsgroep Bevoegde goedkeurders voor toegang in uw testomgeving).</span><span class="sxs-lookup"><span data-stu-id="d2e25-170">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="d2e25-171">Ga in het beheercentrum naar **Instellingenbeveiliging en**  >  **&**  >  **privacyprivilegetoegang.**</span><span class="sxs-lookup"><span data-stu-id="d2e25-171">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="d2e25-172">Selecteer **Toegangsbeleid en aanvragen beheren.**</span><span class="sxs-lookup"><span data-stu-id="d2e25-172">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="d2e25-173">Selecteer de aanvraag in behandeling en selecteer Vervolgens Goedkeuren **om** toegang te verlenen tot het account van de globale beheerder om een nieuwe logboekregel te maken.</span><span class="sxs-lookup"><span data-stu-id="d2e25-173">Select the pending request, and then select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="d2e25-174">Het globale beheerdersaccount (de verzoekende gebruiker) ontvangt per e-mail een bevestiging dat goedkeuring is verleend.</span><span class="sxs-lookup"><span data-stu-id="d2e25-174">The Global Admin account (the requesting user) will receive an email confirmation that approval was granted.</span></span>

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="d2e25-175">Test het maken van een nieuwe logboekregel met bevoegde toegang goedgekeurd voor New-JournalRule taak</span><span class="sxs-lookup"><span data-stu-id="d2e25-175">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="d2e25-176">Open de externe PowerShell-module van **Microsoft Corporation** Microsoft Exchange Online op uw lokale computer en meld u aan bij de externe  >  **PowerShell-module** van Exchange Online met behulp van het hoofdbeheerdersaccount voor uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="d2e25-176">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="d2e25-177">Maak in Exchange Management PowerShell een nieuwe logboekregel voor uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="d2e25-177">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="d2e25-178">U kunt zien dat de nieuwe logboekregel is gemaakt in Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d2e25-178">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="d2e25-179">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="d2e25-179">Next step</span></span>

<span data-ttu-id="d2e25-180">Bekijk aanvullende [functies en mogelijkheden](m365-enterprise-test-lab-guides.md#information-protection) voor gegevensbeveiliging in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="d2e25-180">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="d2e25-181">Zie ook</span><span class="sxs-lookup"><span data-stu-id="d2e25-181">See also</span></span>

[<span data-ttu-id="d2e25-182">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="d2e25-182">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="d2e25-183">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="d2e25-183">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="d2e25-184">Microsoft 365 enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="d2e25-184">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)
