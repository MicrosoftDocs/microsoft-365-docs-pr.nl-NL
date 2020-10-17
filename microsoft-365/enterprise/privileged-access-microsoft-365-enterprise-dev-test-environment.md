---
title: Toegangsbeheer met toegangsrechten voor uw testomgeving Microsoft 365 for Enterprise
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
description: Gebruik deze test lab-handleiding om het toegangsbeheer voor uw Microsoft 365 voor Enterprise testomgeving in te schakelen.
ms.openlocfilehash: 24ca7a6408a4290c54dd2bcd7c3f6061eb8f6c05
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487586"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="4c9ca-103">Toegangsbeheer met toegangsrechten voor uw testomgeving Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="4c9ca-103">Privileged access management for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="4c9ca-104">*U kunt deze test lab-handleiding gebruiken voor zowel Microsoft 365 voor Enterprise als Office 365 Enterprise test omgevingen.*</span><span class="sxs-lookup"><span data-stu-id="4c9ca-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="4c9ca-105">In dit artikel wordt beschreven hoe u het toegangsbeheer voor ongeautoriseerde toegang kunt configureren om de beveiliging in uw Microsoft 365 voor Enterprise testomgeving te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-105">This article describes how to configure privileged access management to increase security in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="4c9ca-106">Het configureren van de priviledged-toegangsbeheer omvat drie fasen:</span><span class="sxs-lookup"><span data-stu-id="4c9ca-106">Configuring priviledged access management involves three phases:</span></span>
- [<span data-ttu-id="4c9ca-107">Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken</span><span class="sxs-lookup"><span data-stu-id="4c9ca-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="4c9ca-108">Fase 2: geprivilegieerd toegangsbeheer configureren</span><span class="sxs-lookup"><span data-stu-id="4c9ca-108">Phase 2: Configure privileged access management</span></span>](#phase-2-configure-privileged-access-management)
- [<span data-ttu-id="4c9ca-109">Fase 3: controleren of de goedkeuring is vereist voor verhoogde en geprivilegieerde taken</span><span class="sxs-lookup"><span data-stu-id="4c9ca-109">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="4c9ca-111">Ga naar [Microsoft 365 for Enterprise test lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)van een visuele kaart voor alle artikelen in de stack microsoft 365 for Enterprise test lab Guide.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="4c9ca-112">Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken</span><span class="sxs-lookup"><span data-stu-id="4c9ca-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="4c9ca-113">Als u het toegangsbeheer op een lichte manier met de minimale vereisten wilt configureren, volgt u de instructies in de [Lightweight Base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="4c9ca-113">If you want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="4c9ca-114">Als u het toegangsbeheer voor bevoegdheden in een gesimuleerde onderneming wilt configureren, volgt u de instructies in de [verificatie](pass-through-auth-m365-ent-test-environment.md)procedure.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-114">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
>[!NOTE]
><span data-ttu-id="4c9ca-115">Voor het testen van het toegankelijkheids beheer is de gesimuleerde Enterprise-testomgeving niet vereist, dat een gesimuleerd intranet bevat dat verbonden is met internet en adreslijstsynchronisatie van een Active Directory Domain Services-forest.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-115">Testing privileged access management doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services forest.</span></span> <span data-ttu-id="4c9ca-116">Dit wordt hier als optie geboden, zodat u het beheer van de toegangsrechten kunt testen en een proef kunt uitvoeren in een omgeving die een typische organisatie voorstelt.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-116">It's provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="4c9ca-117">Fase 2: geprivilegieerd toegangsbeheer configureren</span><span class="sxs-lookup"><span data-stu-id="4c9ca-117">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="4c9ca-118">In deze fase configureert u een groep goedkeurders en schakelt u het beheer van de juiste toegang in voor uw Microsoft 365 voor Enterprise testomgeving.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-118">In this phase, configure an approvers group and enable privileged access management for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="4c9ca-119">Zie [toegangsbeheer](../compliance/privileged-access-management-overview.md)voor meer informatie en een overzicht van toegangsbeheer met bevoegdheden.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-119">For additional details and an overview of privileged access management, see [Privileged access management](../compliance/privileged-access-management-overview.md).</span></span>

<span data-ttu-id="4c9ca-120">Voer de volgende stappen uit om geprivilegieerde toegang in uw organisatie in te stellen en te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-120">To set up and use privileged access in your organization, perform the following steps.</span></span>

#### <a name="step-1-create-an-approvers-group"></a>[<span data-ttu-id="4c9ca-121">Stap 1: een groep goedkeurder maken</span><span class="sxs-lookup"><span data-stu-id="4c9ca-121">Step 1: Create an approver's group</span></span>](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

<span data-ttu-id="4c9ca-122">Voordat u met geprivilegieerde toegang begint te werken, moet u bepalen wie de goedkeuringsbevoegdheid heeft voor binnenkomende verzoeken om toegang te krijgen tot taken met verhoogde bevoegdheid en bevoegdheden.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-122">Before you start using privileged access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="4c9ca-123">Alle gebruikers die lid zijn van de groep goedkeurders kunnen toegangsaanvragen goedkeuren.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-123">All users who are part of the Approvers’ group can approve access requests.</span></span> <span data-ttu-id="4c9ca-124">Als u geprivilegieerde toegang wilt gebruiken, moet u een beveiligingsgroep met e-mail maken in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-124">To use privileged access, you must create a mail-enabled security group in Microsoft 365.</span></span> <span data-ttu-id="4c9ca-125">Geef in uw testomgeving de naam van de nieuwe beveiligingsgroep ' goedkeurders van toegang ' aan, en voeg ' gebruiker 3 ' toe die eerder is gemaakt in de stappen van de eerdere testomgeving.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-125">In your test environment, name the new security group "Privileged Access Approvers" and add the "User 3" that was previously created in previous test lab guide steps.</span></span>

#### <a name="step-2-enable-privileged-access"></a>[<span data-ttu-id="4c9ca-126">Stap 2: geprivilegieerde toegang inschakelen</span><span class="sxs-lookup"><span data-stu-id="4c9ca-126">Step 2: Enable privileged access</span></span>](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

<span data-ttu-id="4c9ca-127">Geautoriseerde toegang moet expliciet worden ingeschakeld in Microsoft 365 met de standaardgroep goedkeurder en moet een set systeemaccounts bevatten die u wilt uitsluiten van het toegangsbeheer toegangsbeheer.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-127">Privileged access needs to be explicitly turned on in Microsoft 365 with the default approver group, and it must include a set of system accounts that you want excluded from the privileged access management access control.</span></span> <span data-ttu-id="4c9ca-128">Zorg ervoor dat u de toegang tot uw organisatie hebt ingeschakeld voordat u fase 3 van deze handleiding start.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-128">Be sure to enable privileged access in your organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="4c9ca-129">Fase 3: controleren of de goedkeuring is vereist voor verhoogde en geprivilegieerde taken</span><span class="sxs-lookup"><span data-stu-id="4c9ca-129">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="4c9ca-130">In deze fase controleert u of het beleid voor toegangsrechten werkt en dat gebruikers goedkeuring vereisen voor het uitvoeren van gedefinieerde, uitgebreide, geprivilegieerde taken.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-130">In this phase, verify that the privileged access policy is working and that users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="4c9ca-131">De mogelijkheid om een taak uit te voeren die niet is gedefinieerd in een beleid voor toegangsrechten testen</span><span class="sxs-lookup"><span data-stu-id="4c9ca-131">Test the ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="4c9ca-132">Maak eerst verbinding met Exchange Management PowerShell met de referenties van een gebruiker die is geconfigureerd als globale beheerder in uw testomgeving en probeer een nieuwe logboek regel te maken.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-132">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="4c9ca-133">De [nieuwe JournalRule-](https://docs.microsoft.com/powershell/module/exchange/new-journalrule) taak is op dit moment niet gedefinieerd in het toegangsbeleid voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-133">The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="4c9ca-134">Open op uw lokale computer en meld u aan bij de Exchange Online Remote PowerShell-module op **Microsoft Corporation**  >  **Microsoft Exchange Online Remote PowerShell-module** met behulp van het globale beheerdersaccount voor uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-134">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="4c9ca-135">Maak in Exchange Management PowerShell een nieuwe logboek regel voor uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="4c9ca-135">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="4c9ca-136">Weergave van de nieuwe logboek regel is gemaakt in Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-136">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="4c9ca-137">Een nieuw toegangsbeleid voor toegangsrechten maken voor de New-JournalRule taak</span><span class="sxs-lookup"><span data-stu-id="4c9ca-137">Create a new privileged access policy for the New-JournalRule task</span></span>

>[!NOTE]
><span data-ttu-id="4c9ca-138">Als u de stappen 1 en 2 uit fase 2 van deze handleiding nog niet hebt uitgevoerd, moet u de stappen uitvoeren om de groep bevoegdheden voorgoed keuring van bevoegdheden te maken om toegang te krijgen tot uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-138">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="4c9ca-139">Meld u aan bij het [Beheercentrum van Microsoft 365](https://admin.microsoft.com) met behulp van het globale beheerdersaccount voor uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-139">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="4c9ca-140">Ga in het Beheercentrum naar **instellingen**  >  **beveiliging & privacy**  >  **bevoorrechte toegang**.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-140">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="4c9ca-141">Selecteer **toegangsbeleidsregels en aanvragen beheren**.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-141">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="4c9ca-142">Selecteer **beleid configureren**en selecteer vervolgens **beleid toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-142">Select **Configure policies**, and then select **Add a policy**.</span></span>

5. <span data-ttu-id="4c9ca-143">Selecteer of typ de volgende waarden in de vervolgkeuzelijst:</span><span class="sxs-lookup"><span data-stu-id="4c9ca-143">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="4c9ca-144">**Beleidstype**: taak</span><span class="sxs-lookup"><span data-stu-id="4c9ca-144">**Policy type**: Task</span></span>

    <span data-ttu-id="4c9ca-145">**Beleids bereik**: Exchange</span><span class="sxs-lookup"><span data-stu-id="4c9ca-145">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="4c9ca-146">**Beleidsnaam**: nieuwe logboek regel</span><span class="sxs-lookup"><span data-stu-id="4c9ca-146">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="4c9ca-147">**Goedkeurings type**: handmatig</span><span class="sxs-lookup"><span data-stu-id="4c9ca-147">**Approval type**: Manual</span></span>

    <span data-ttu-id="4c9ca-148">**Goedkeuringsgroep**: geautoriseerde toegang goedkeurders</span><span class="sxs-lookup"><span data-stu-id="4c9ca-148">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="4c9ca-149">Selecteer **maken**en selecteer vervolgens **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-149">Select **Create**, and then select **Close**.</span></span> <span data-ttu-id="4c9ca-150">Het kan een paar minuten duren voordat het beleid volledig is geconfigureerd en is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-150">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="4c9ca-151">Zorg ervoor dat het beleid volledig is ingeschakeld voordat u de goedkeurings vereiste gaat testen in de volgende stap.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-151">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="4c9ca-152">De vereiste voorgoed keuring testen voor de New-JournalRule taak die is gedefinieerd in een beleid voor toegangsrechten</span><span class="sxs-lookup"><span data-stu-id="4c9ca-152">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="4c9ca-153">Open op uw lokale computer en meld u aan bij de Exchange Online Remote PowerShell-module op **Microsoft Corporation**  >  **Microsoft Exchange Online Remote PowerShell-module** met behulp van een globale beheerdersaccount voor uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-153">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="4c9ca-154">Maak in Exchange Management PowerShell een nieuwe logboek regel voor uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="4c9ca-154">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. <span data-ttu-id="4c9ca-155">De fout ' onvoldoende machtigingen ' in Exchange Management PowerShell weergeven:</span><span class="sxs-lookup"><span data-stu-id="4c9ca-155">View the "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="4c9ca-156">Toegang aanvragen om een nieuwe logboek regel te maken met behulp van de New-JournalRule taak</span><span class="sxs-lookup"><span data-stu-id="4c9ca-156">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="4c9ca-157">Meld u aan bij het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) met het account van de globale beheerder voor uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-157">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="4c9ca-158">Ga in het Beheercentrum naar **instellingen**  >  **beveiliging & privacy**  >  **bevoorrechte toegang**.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-158">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="4c9ca-159">Selecteer **toegangsbeleidsregels en aanvragen beheren**.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-159">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="4c9ca-160">Selecteer **nieuwe aanvraag**.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-160">Select **New request**.</span></span> <span data-ttu-id="4c9ca-161">Selecteer in de vervolgkeuzelijsten de juiste waarden voor uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="4c9ca-161">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="4c9ca-162">**Type aanvraag**: taak</span><span class="sxs-lookup"><span data-stu-id="4c9ca-162">**Request type**: Task</span></span>

    <span data-ttu-id="4c9ca-163">**Aanvraagbereik**: Exchange</span><span class="sxs-lookup"><span data-stu-id="4c9ca-163">**Request scope**: Exchange</span></span>

    <span data-ttu-id="4c9ca-164">**Aanvraag voor**: nieuwe logboek regel</span><span class="sxs-lookup"><span data-stu-id="4c9ca-164">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="4c9ca-165">**Duur (uren)**: 2</span><span class="sxs-lookup"><span data-stu-id="4c9ca-165">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="4c9ca-166">**Opmerkingen**: vraagt om toestemming voor het maken van een nieuwe logboek regel</span><span class="sxs-lookup"><span data-stu-id="4c9ca-166">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="4c9ca-167">Selecteer **Opslaan**en selecteer vervolgens **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-167">Select **Save**, and then select **Close**.</span></span> <span data-ttu-id="4c9ca-168">Uw verzoek wordt via e-mail naar de groep van de goedkeurder verzonden.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-168">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="4c9ca-169">Aanvraag voor toegangsrechten goedkeuren voor het maken van een nieuwe logboek regel</span><span class="sxs-lookup"><span data-stu-id="4c9ca-169">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="4c9ca-170">Meld u aan bij het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) met behulp van de referenties voor gebruikers 3 in uw testomgeving (lid van de beveiligingsgroep geautoriseerde toegang goedkeurders in uw testomgeving).</span><span class="sxs-lookup"><span data-stu-id="4c9ca-170">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="4c9ca-171">Ga in het Beheercentrum naar **instellingen**  >  **beveiliging & privacy**  >  **bevoorrechte toegang**.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-171">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="4c9ca-172">Selecteer **toegangsbeleidsregels en aanvragen beheren**.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-172">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="4c9ca-173">Selecteer de aanvraag in behandeling en selecteer vervolgens **goedkeuren** om toegang te verlenen aan het account van de globale beheerder om een nieuwe logboek regel te maken.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-173">Select the pending request, and then select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="4c9ca-174">Het account van de globale beheerder (de gebruiker die de gebruiker aanvraagt) ontvangt een e-mail bevestiging dat de goedkeuring is verleend.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-174">The Global Admin account (the requesting user) will receive an email confirmation that approval was granted.</span></span>

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="4c9ca-175">Test het maken van een nieuwe logboek regel met geprivilegieerde toegang goedgekeurd voor de New-JournalRule taak</span><span class="sxs-lookup"><span data-stu-id="4c9ca-175">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="4c9ca-176">Open op uw lokale computer en meld u aan bij de Exchange Online Remote PowerShell-module op **Microsoft Corporation**  >  **Microsoft Exchange Online Remote PowerShell-module** met behulp van het globale beheerdersaccount voor uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-176">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="4c9ca-177">Maak in Exchange Management PowerShell een nieuwe logboek regel voor uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="4c9ca-177">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="4c9ca-178">Weergave van de nieuwe logboek regel is gemaakt in Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-178">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="4c9ca-179">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="4c9ca-179">Next step</span></span>

<span data-ttu-id="4c9ca-180">Verken de functies en mogelijkheden van extra [informatiebescherming](m365-enterprise-test-lab-guides.md#information-protection) in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="4c9ca-180">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="4c9ca-181">Zie ook</span><span class="sxs-lookup"><span data-stu-id="4c9ca-181">See also</span></span>

[<span data-ttu-id="4c9ca-182">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="4c9ca-182">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="4c9ca-183">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="4c9ca-183">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="4c9ca-184">Documentatie voor Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="4c9ca-184">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
