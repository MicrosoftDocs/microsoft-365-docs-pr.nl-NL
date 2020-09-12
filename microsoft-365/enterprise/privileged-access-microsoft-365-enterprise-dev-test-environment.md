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
ms.openlocfilehash: d8d92aa86076e323e4b5bb5c8eb1385edcac420c
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545940"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="80ad3-103">Toegangsbeheer met toegangsrechten voor uw testomgeving Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="80ad3-103">Privileged access management for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="80ad3-104">*U kunt deze test lab-handleiding gebruiken voor zowel Microsoft 365 voor Enterprise als Office 365 Enterprise test omgevingen.*</span><span class="sxs-lookup"><span data-stu-id="80ad3-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="80ad3-105">Aan de hand van de instructies in dit artikel configureert u het toegangsbeheer om het beveiligingsniveau van uw Microsoft 365 voor Enterprise testomgeving te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="80ad3-105">With the instructions in this article, you configure privileged access management to increase security in your Microsoft 365 for enterprise test environment.</span></span>

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

>[!TIP]
><span data-ttu-id="80ad3-107">Klik op [Hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de stack van Microsoft 365 voor Enterprise-testlabrichtlijnen.</span><span class="sxs-lookup"><span data-stu-id="80ad3-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="80ad3-108">Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken</span><span class="sxs-lookup"><span data-stu-id="80ad3-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="80ad3-109">Als u alleen een eenvoudig toegangsbeheer wilt configureren met de minimale vereisten, volgt u de instructies in de [Lightweight Base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="80ad3-109">If you just want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="80ad3-110">Als u het toegangsbeheer voor bevoegdheden in een gesimuleerde onderneming wilt configureren, volgt u de instructies in de [verificatie](pass-through-auth-m365-ent-test-environment.md)procedure.</span><span class="sxs-lookup"><span data-stu-id="80ad3-110">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
>[!NOTE]
><span data-ttu-id="80ad3-111">Voor het testen van het toegangsbeheer is het niet mogelijk de gesimuleerde Enterprise testomgeving te gebruiken, waaronder een gesimuleerd intranet dat verbonden is met internet en adreslijstsynchronisatie van een AD DS-forest.</span><span class="sxs-lookup"><span data-stu-id="80ad3-111">Testing privileged access management does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an AD DS forest.</span></span> <span data-ttu-id="80ad3-112">Dit wordt hier als optie geboden, zodat u het beheer van de toegangsrechten kunt testen en een proef kunt uitvoeren in een omgeving die een typische organisatie voorstelt.</span><span class="sxs-lookup"><span data-stu-id="80ad3-112">It is provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="80ad3-113">Fase 2: geprivilegieerd toegangsbeheer configureren</span><span class="sxs-lookup"><span data-stu-id="80ad3-113">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="80ad3-114">In deze fase configureert u een groep goedkeurders en schakelt u het beheer van de juiste toegang in voor uw Microsoft 365 voor Enterprise-testomgeving.</span><span class="sxs-lookup"><span data-stu-id="80ad3-114">In this phase, you configure an approvers group and enable privileged access management for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="80ad3-115">Zie [toegangsbeheer](../compliance/privileged-access-management-overview.md)voor meer informatie en een overzicht van toegangsbeheer met bevoegdheden.</span><span class="sxs-lookup"><span data-stu-id="80ad3-115">For additional details and an overview of privileged access management, see [Privileged access management](../compliance/privileged-access-management-overview.md).</span></span>

<span data-ttu-id="80ad3-116">Voer de volgende stappen uit om geprivilegieerde toegang in uw organisatie in te stellen en te gebruiken:</span><span class="sxs-lookup"><span data-stu-id="80ad3-116">Follow these steps to set up and use privileged access in your organization:</span></span>

- [<span data-ttu-id="80ad3-117">Stap 1: een groep goedkeurder maken</span><span class="sxs-lookup"><span data-stu-id="80ad3-117">Step 1: Create an approver's group</span></span>](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

    <span data-ttu-id="80ad3-118">Voordat u bevoegdheden toegang kunt gaan gebruiken, moet u bepalen wie de goedkeuringsbevoegdheid heeft voor binnenkomende verzoeken om toegang te krijgen tot taken met verhoogde bevoegdheid en bevoegdheden.</span><span class="sxs-lookup"><span data-stu-id="80ad3-118">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="80ad3-119">Gebruikers die lid zijn van de groep goedkeurders, kunnen toegangsaanvragen goedkeuren.</span><span class="sxs-lookup"><span data-stu-id="80ad3-119">Any user who is part of the Approvers’ group will be able to approve access requests.</span></span> <span data-ttu-id="80ad3-120">Dit is ingeschakeld door een beveiligingsgroep met e-mail te maken in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="80ad3-120">This is enabled by creating a mail-enabled security group in Microsoft 365.</span></span> <span data-ttu-id="80ad3-121">Maak een nieuwe beveiligingsgroep met de naam ' goedkeurders van toegankelijkheid ' in uw testomgeving, en voeg de ' gebruiker 3 ' toe die eerder is gemaakt in de stappen voor voorafgaand test lab-handleiding.</span><span class="sxs-lookup"><span data-stu-id="80ad3-121">Create a new security group named "Privileged Access Approvers" in your test environment and add the "User 3" previously created in prior test lab guide steps.</span></span>

- [<span data-ttu-id="80ad3-122">Stap 2: geprivilegieerde toegang inschakelen</span><span class="sxs-lookup"><span data-stu-id="80ad3-122">Step 2: Enable privileged access</span></span>](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

    <span data-ttu-id="80ad3-123">Geautoriseerde toegang moet expliciet worden ingeschakeld in Microsoft 365 met de standaardgroep goedkeurder en met een reeks systeemaccounts die u wilt uitsluiten van het toegangsbeheer toegangsbeheer.</span><span class="sxs-lookup"><span data-stu-id="80ad3-123">Privileged access needs to be explicitly turned on in Microsoft 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control.</span></span> <span data-ttu-id="80ad3-124">Zorg ervoor dat u de toegang tot uw organisatie hebt ingeschakeld voordat u fase 3 van deze handleiding start.</span><span class="sxs-lookup"><span data-stu-id="80ad3-124">Be sure to enable privileged access in your organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="80ad3-125">Fase 3: controleren of de goedkeuring is vereist voor verhoogde en geprivilegieerde taken</span><span class="sxs-lookup"><span data-stu-id="80ad3-125">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="80ad3-126">In deze fase dient u te controleren of het beleid voor toegangsrechten en de gebruikers moeten worden goedgekeurd voor het uitvoeren van gedefinieerde, uitgebreide en geprivilegieerde taken.</span><span class="sxs-lookup"><span data-stu-id="80ad3-126">In this phase, you verify that the privileged access policy is working and users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="80ad3-127">De mogelijkheid om een taak uit te voeren die niet is gedefinieerd in een beleid voor toegangsrechten testen</span><span class="sxs-lookup"><span data-stu-id="80ad3-127">Test ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="80ad3-128">Maak eerst verbinding met Exchange Management PowerShell met de referenties van een gebruiker die is geconfigureerd als globale beheerder in uw testomgeving en probeer een nieuwe logboek regel te maken.</span><span class="sxs-lookup"><span data-stu-id="80ad3-128">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="80ad3-129">De [nieuwe JournalRule-](https://docs.microsoft.com/powershell/module/exchange/new-journalrule) taak is op dit moment niet gedefinieerd in het toegangsbeleid voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="80ad3-129">The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="80ad3-130">Open op uw lokale computer de naam van de Exchange Online Remote PowerShell-module op **Microsoft Corporation**  >  **Microsoft Exchange Online Remote PowerShell-module** met behulp van het globale beheerdersaccount voor uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="80ad3-130">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="80ad3-131">Maak in Exchange Management PowerShell een nieuwe logboek regel voor uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="80ad3-131">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```

4. <span data-ttu-id="80ad3-132">Weergave van de nieuwe logboek regel is gemaakt in Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80ad3-132">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="80ad3-133">Een nieuw beleid voor toegangsrechten maken voor de nieuwe taak JournalRule</span><span class="sxs-lookup"><span data-stu-id="80ad3-133">Create a new privileged access policy for the New-JournalRule task</span></span>

>[!NOTE]
><span data-ttu-id="80ad3-134">Als u de stappen 1 en 2 uit fase 2 van deze handleiding nog niet hebt uitgevoerd, moet u de stappen uitvoeren om de groep met bevoegdheden voor het goedkeuren van bevoegdheden te maken en geprivilegieerde toegang in uw testomgeving in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="80ad3-134">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" and to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="80ad3-135">Meld u aan bij het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) met behulp van het gebruikersaccount van de globale beheerder voor uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="80ad3-135">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="80ad3-136">Ga in het Beheercentrum naar **instellingen**  >  **beveiliging & privacy**  >  **bevoorrechte toegang**.</span><span class="sxs-lookup"><span data-stu-id="80ad3-136">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="80ad3-137">Selecteer **toegangsbeleidsregels en aanvragen beheren**.</span><span class="sxs-lookup"><span data-stu-id="80ad3-137">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="80ad3-138">Selecteer **beleid configureren** en selecteer **een beleid toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="80ad3-138">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="80ad3-139">Selecteer of typ de volgende waarden in de vervolgkeuzelijst:</span><span class="sxs-lookup"><span data-stu-id="80ad3-139">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="80ad3-140">**Beleidstype**: taak</span><span class="sxs-lookup"><span data-stu-id="80ad3-140">**Policy type**: Task</span></span>

    <span data-ttu-id="80ad3-141">**Beleids bereik**: Exchange</span><span class="sxs-lookup"><span data-stu-id="80ad3-141">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="80ad3-142">**Beleidsnaam**: nieuwe logboek regel</span><span class="sxs-lookup"><span data-stu-id="80ad3-142">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="80ad3-143">**Goedkeurings type**: handmatig</span><span class="sxs-lookup"><span data-stu-id="80ad3-143">**Approval type**: Manual</span></span>

    <span data-ttu-id="80ad3-144">**Goedkeuringsgroep**: geautoriseerde toegang goedkeurders</span><span class="sxs-lookup"><span data-stu-id="80ad3-144">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="80ad3-145">Selecteer **maken** en vervolgens **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="80ad3-145">Select **Create** and then **Close**.</span></span> <span data-ttu-id="80ad3-146">Het kan een paar minuten duren voordat het beleid volledig is geconfigureerd en is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="80ad3-146">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="80ad3-147">Zorg ervoor dat het beleid volledig is ingeschakeld voordat u de goedkeurings vereiste gaat testen in de volgende stap.</span><span class="sxs-lookup"><span data-stu-id="80ad3-147">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="80ad3-148">Goedkeurings vereiste testen voor de nieuwe JournalRule-taak die is gedefinieerd in een toegangsbeleid</span><span class="sxs-lookup"><span data-stu-id="80ad3-148">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="80ad3-149">Open op uw lokale computer, open en meld u aan bij de Microsoft Exchange Online Remote PowerShell-module op **Microsoft Corporation**  >  **Microsoft Exchange Online Remote PowerShell-module** met behulp van een account van de globale beheerder voor uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="80ad3-149">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="80ad3-150">Maak in Exchange Management PowerShell een nieuwe logboek regel voor uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="80ad3-150">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="80ad3-151">De fout ' onvoldoende machtigingen ' in Exchange Management PowerShell weergeven:</span><span class="sxs-lookup"><span data-stu-id="80ad3-151">View "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

```ExchangeManagementPowerShell
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="80ad3-152">Toegang aanvragen voor het maken van een nieuwe logboek regel met de taak New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="80ad3-152">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="80ad3-153">Meld u aan bij het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) met het account van de globale beheerder voor uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="80ad3-153">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="80ad3-154">Ga in het Beheercentrum naar **instellingen**  >  **beveiliging & privacy**  >  **bevoorrechte toegang**.</span><span class="sxs-lookup"><span data-stu-id="80ad3-154">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="80ad3-155">Selecteer **toegangsbeleidsregels en aanvragen beheren**.</span><span class="sxs-lookup"><span data-stu-id="80ad3-155">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="80ad3-156">Selecteer **nieuwe aanvraag**.</span><span class="sxs-lookup"><span data-stu-id="80ad3-156">Select **New request**.</span></span> <span data-ttu-id="80ad3-157">Selecteer in de vervolgkeuzelijsten de juiste waarden voor uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="80ad3-157">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="80ad3-158">**Type aanvraag**: taak</span><span class="sxs-lookup"><span data-stu-id="80ad3-158">**Request type**: Task</span></span>

    <span data-ttu-id="80ad3-159">**Aanvraagbereik**: Exchange</span><span class="sxs-lookup"><span data-stu-id="80ad3-159">**Request scope**: Exchange</span></span>

    <span data-ttu-id="80ad3-160">**Aanvraag voor**: nieuwe logboek regel</span><span class="sxs-lookup"><span data-stu-id="80ad3-160">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="80ad3-161">**Duur (uren)**: 2</span><span class="sxs-lookup"><span data-stu-id="80ad3-161">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="80ad3-162">**Opmerkingen**: vraagt om toestemming voor het maken van een nieuwe logboek regel</span><span class="sxs-lookup"><span data-stu-id="80ad3-162">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="80ad3-163">Selecteer **Opslaan** en vervolgens **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="80ad3-163">Select **Save** and then **Close**.</span></span> <span data-ttu-id="80ad3-164">Uw verzoek wordt via e-mail naar de groep van de goedkeurder verzonden.</span><span class="sxs-lookup"><span data-stu-id="80ad3-164">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="80ad3-165">Aanvraag voor toegangsrechten goedkeuren voor het maken van een nieuwe logboek regel</span><span class="sxs-lookup"><span data-stu-id="80ad3-165">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="80ad3-166">Meld u aan bij het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) met behulp van de referenties voor gebruikers 3 in uw testomgeving (lid van de beveiligingsgroep geautoriseerde toegang goedkeurders in uw testomgeving).</span><span class="sxs-lookup"><span data-stu-id="80ad3-166">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="80ad3-167">Ga in het Beheercentrum naar **instellingen**  >  **beveiliging & privacy**  >  **bevoorrechte toegang**.</span><span class="sxs-lookup"><span data-stu-id="80ad3-167">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="80ad3-168">Selecteer **toegangsbeleidsregels en aanvragen beheren**.</span><span class="sxs-lookup"><span data-stu-id="80ad3-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="80ad3-169">Selecteer de aanvraag in behandeling en selecteer **goedkeuren** om toegang te verlenen aan het account van de globale beheerder om een nieuwe logboek regel te maken.</span><span class="sxs-lookup"><span data-stu-id="80ad3-169">Select the pending request and select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="80ad3-170">Een e-mailbericht met de mededeling dat de goedkeuring is verleend, wordt verzonden naar het account van de globale beheerder (de aanvraag voor de gebruiker).</span><span class="sxs-lookup"><span data-stu-id="80ad3-170">A notification email confirming that approval has been granted will be sent to the Global Admin account (the requesting user).</span></span>  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="80ad3-171">Test het maken van een nieuwe logboek regel met geprivilegieerde toegang goedgekeurd voor de nieuwe taak JournalRule</span><span class="sxs-lookup"><span data-stu-id="80ad3-171">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="80ad3-172">Open op uw lokale computer de naam van de Exchange Online Remote PowerShell-module op **Microsoft Corporation**  >  **Microsoft Exchange Online Remote PowerShell-module** met behulp van het globale beheerdersaccount voor uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="80ad3-172">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="80ad3-173">Maak in Exchange Management PowerShell een nieuwe logboek regel voor uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="80ad3-173">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="80ad3-174">Weergave van de nieuwe logboek regel is gemaakt in Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80ad3-174">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="80ad3-175">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="80ad3-175">Next step</span></span>

<span data-ttu-id="80ad3-176">Verken de functies en mogelijkheden van extra [informatiebescherming](m365-enterprise-test-lab-guides.md#information-protection) in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="80ad3-176">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="80ad3-177">Raadpleeg ook</span><span class="sxs-lookup"><span data-stu-id="80ad3-177">See also</span></span>

[<span data-ttu-id="80ad3-178">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="80ad3-178">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="80ad3-179">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="80ad3-179">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="80ad3-180">Documentatie voor Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="80ad3-180">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
