---
title: Aan de slag met Privileged Access Management
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: ''
description: Gebruik dit artikel voor meer informatie over het inschakelen en configureren van bevoorrecht toegangsbeheer in Office 365.
ms.openlocfilehash: 0b8d79c3012ecd321d7b00c1566aa557077d55f1
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/06/2021
ms.locfileid: "52161685"
---
# <a name="get-started-with-privileged-access-management"></a><span data-ttu-id="65ee1-103">Aan de slag met Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="65ee1-103">Get started with privileged access management</span></span>

<span data-ttu-id="65ee1-104">Dit onderwerp begeleidt u bij het inschakelen en configureren van bevoorrecht toegangsbeheer in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="65ee1-104">This topic guides you through enabling and configuring privileged access management in your organization.</span></span> <span data-ttu-id="65ee1-105">U kunt het beheercentrum Microsoft 365 of Exchange PowerShell gebruiken om bevoorrechte toegang te beheren en te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="65ee1-105">You can use either the Microsoft 365 admin center or Exchange Management PowerShell to manage and use privileged access.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="65ee1-106">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="65ee1-106">Before you begin</span></span>

<span data-ttu-id="65ee1-107">Voordat u aan de slag gaat met privileged access management, moet u uw Microsoft 365 [en](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) eventuele invoegtoepassingen bevestigen.</span><span class="sxs-lookup"><span data-stu-id="65ee1-107">Before you get started with privileged access management, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) and any add-ons.</span></span> <span data-ttu-id="65ee1-108">Als u toegang wilt krijgen tot en gebruik wilt maken van bevoorrecht toegangsbeheer, moet uw organisatie een van de volgende abonnementen of invoegtoepassingen hebben:</span><span class="sxs-lookup"><span data-stu-id="65ee1-108">To access and use privileged access management, your organization must have one of the following subscriptions or add-ons:</span></span>

- <span data-ttu-id="65ee1-109">Microsoft 365 E5 (betaalde of proefversie)</span><span class="sxs-lookup"><span data-stu-id="65ee1-109">Microsoft 365 E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="65ee1-110">Microsoft 365 E3 abonnement (of Office 365 E3-abonnement + Enterprise Mobility and Security E3-abonnement) + de Microsoft 365 E5 Compliance-invoegabonnement</span><span class="sxs-lookup"><span data-stu-id="65ee1-110">Microsoft 365 E3 subscription (or Office 365 E3 subscription + Enterprise Mobility and Security E3 subscription) + the Microsoft 365 E5 Compliance add-on</span></span>
- <span data-ttu-id="65ee1-111">Elk Microsoft 365, Office 365, Exchange, SharePoint of OneDrive voor Bedrijven abonnement + de Microsoft 365 E5 Insider Risk Management-invoeging</span><span class="sxs-lookup"><span data-stu-id="65ee1-111">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Business subscription + the Microsoft 365 E5 Insider Risk Management add-on</span></span>  
- <span data-ttu-id="65ee1-112">Microsoft 365 A5-abonnement (betaalde versie of proefversie)</span><span class="sxs-lookup"><span data-stu-id="65ee1-112">Microsoft 365 A5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="65ee1-113">Microsoft 365 A3-abonnement (of Office 365 A3 + Enterprise Mobility and Security A3-abonnement) + de Microsoft A5 Compliance-invoegvoegvoeging</span><span class="sxs-lookup"><span data-stu-id="65ee1-113">Microsoft 365 A3 subscription (or Office 365 A3 subscription + Enterprise Mobility and Security A3 subscription) + the Microsoft A5 Compliance add-on</span></span>
- <span data-ttu-id="65ee1-114">Alle Microsoft 365, Office 365, Exchange, SharePoint of OneDrive voor onderwijsabonnementen + de Microsoft 365 A5 Insider Risk Management-invoeging</span><span class="sxs-lookup"><span data-stu-id="65ee1-114">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Education subscription + the Microsoft 365 A5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="65ee1-115">Office 365 Enterprise E5-abonnement (betaalde of proefversie)</span><span class="sxs-lookup"><span data-stu-id="65ee1-115">Office 365 Enterprise E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="65ee1-116">Office 365 Enterprise E3-abonnement + de Office 365 Advanced Compliance-invoegabonnement (niet meer beschikbaar voor nieuwe abonnementen, zie opmerking)</span><span class="sxs-lookup"><span data-stu-id="65ee1-116">Office 365 Enterprise E3 subscription + the Office 365 Advanced Compliance add-on (no longer available for new subscriptions, see note)</span></span>

<span data-ttu-id="65ee1-117">Gebruikers die een bevoorrechte toegangsbeheerverzoek indienen en beantwoorden, moeten een van de bovenstaande licenties krijgen toegewezen.</span><span class="sxs-lookup"><span data-stu-id="65ee1-117">Users submitting and responding to privileged access management requests must be assigned one of the licenses above.</span></span>

>[!IMPORTANT]
><span data-ttu-id="65ee1-118">Office 365 Advanced Compliance wordt niet meer als zelfstandig abonnement verkocht.</span><span class="sxs-lookup"><span data-stu-id="65ee1-118">Office 365 Advanced Compliance is no longer sold as a standalone subscription.</span></span> <span data-ttu-id="65ee1-119">Wanneer huidige abonnementen verlopen, moeten klanten overstappen op een van de bovenstaande abonnementen, die dezelfde of aanvullende compliancefuncties bevatten.</span><span class="sxs-lookup"><span data-stu-id="65ee1-119">When current subscriptions expire, customers should transition to one of the subscriptions above, which contain the same or additional compliance features.</span></span>

<span data-ttu-id="65ee1-120">Als u geen bestaand Office 365 Enterprise E5-abonnement hebt en u bevoorrecht toegangsbeheer wilt proberen, kunt u [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) toevoegen aan uw bestaande Office 365-abonnement [of](https://www.microsoft.com/microsoft-365/enterprise) u registreren voor een proefversie van Microsoft 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="65ee1-120">If you don't have an existing Office 365 Enterprise E5 plan and want to try privileged access management, you can [add Microsoft 365](/office365/admin/try-or-buy-microsoft-365) to your existing Office 365 subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 Enterprise E5.</span></span>

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="65ee1-121">Bevoorrecht toegangsbeheer in- en configureren</span><span class="sxs-lookup"><span data-stu-id="65ee1-121">Enable and configure privileged access management</span></span>

<span data-ttu-id="65ee1-122">Volg deze stappen om geprivilegieerde toegang in uw organisatie in te stellen en te gebruiken:</span><span class="sxs-lookup"><span data-stu-id="65ee1-122">Follow these steps to set up and use privileged access in your organization:</span></span>

- [<span data-ttu-id="65ee1-123">Stap 1: De groep van een goedkeurder maken</span><span class="sxs-lookup"><span data-stu-id="65ee1-123">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="65ee1-124">Voordat u toegang tot bevoegdheden gaat gebruiken, bepaalt u wie goedkeuringsinstantie nodig heeft voor inkomende aanvragen voor toegang tot verhoogde en bevoorrechte taken.</span><span class="sxs-lookup"><span data-stu-id="65ee1-124">Before you start using privilege access, determine who needs approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="65ee1-125">Elke gebruiker die deel uitmaakt van de groep Goedkeurders, kan toegangsaanvragen goedkeuren.</span><span class="sxs-lookup"><span data-stu-id="65ee1-125">Any user who is part of the Approvers' group is able to approve access requests.</span></span> <span data-ttu-id="65ee1-126">Deze groep is ingeschakeld door een beveiligingsgroep met e-mail te maken in Office 365.</span><span class="sxs-lookup"><span data-stu-id="65ee1-126">This group is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="65ee1-127">Stap 2: Geprivilegieerde toegang inschakelen</span><span class="sxs-lookup"><span data-stu-id="65ee1-127">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="65ee1-128">Geprivilegieerde toegang moet expliciet zijn ingeschakeld in Office 365 met de standaard goedkeurdergroep, inclusief een set systeemaccounts die u wilt uitsluiten van het besturingselement voor toegangsbeheer voor bevoorrechte toegang.</span><span class="sxs-lookup"><span data-stu-id="65ee1-128">Privileged access must be explicitly enabled in Office 365 with the default approver group, including a set of system accounts that you want excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="65ee1-129">Stap 3: Een toegangsbeleid maken</span><span class="sxs-lookup"><span data-stu-id="65ee1-129">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="65ee1-130">Als u een goedkeuringsbeleid maakt, kunt u de specifieke goedkeuringsvereisten definiëren voor afzonderlijke taken.</span><span class="sxs-lookup"><span data-stu-id="65ee1-130">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks.</span></span> <span data-ttu-id="65ee1-131">De goedkeuringstypeopties zijn **Automatisch** of **Handmatig.**</span><span class="sxs-lookup"><span data-stu-id="65ee1-131">The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="65ee1-132">Stap 4: Aanvragen voor geprivilegieerde toegang indienen/goedkeuren</span><span class="sxs-lookup"><span data-stu-id="65ee1-132">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="65ee1-133">Wanneer deze optie is ingeschakeld, moeten voor bevoorrechte toegang goedkeuringen worden verleend voor een taak die een gekoppeld goedkeuringsbeleid heeft gedefinieerd.</span><span class="sxs-lookup"><span data-stu-id="65ee1-133">Once enabled, privileged access requires approvals for any task that has an associated approval policy defined.</span></span> <span data-ttu-id="65ee1-134">Voor taken die zijn opgenomen in een goedkeuringsbeleid, moeten gebruikers toegangsgoedkeuring aanvragen en worden verleend om over machtigingen te kunnen vragen die nodig zijn om de taak uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="65ee1-134">For tasks included in an approval policy, users must request and be granted access approval to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="65ee1-135">Nadat goedkeuring is verleend, kan de verzoekende gebruiker de beoogde taak uitvoeren en wordt de taak geautoriseerd en uitgevoerd namens de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="65ee1-135">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on behalf of the user.</span></span> <span data-ttu-id="65ee1-136">De goedkeuring blijft geldig voor de gevraagde duur (standaardduur is 4 uur), waarbij de aanvraager de beoogde taak meerdere keren kan uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="65ee1-136">The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times.</span></span> <span data-ttu-id="65ee1-137">Al deze uitvoeringen worden geregistreerd en beschikbaar gesteld voor beveiligings- en compliancecontrole.</span><span class="sxs-lookup"><span data-stu-id="65ee1-137">All such executions are logged and made available for security and compliance auditing.</span></span> 

>[!NOTE]
><span data-ttu-id="65ee1-138">Als u Exchange Management PowerShell wilt gebruiken om geprivilegieerde toegang in te schakelen en te configureren, volgt u de stappen in Verbinding maken naar [Exchange Online PowerShell met](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) meervoudige verificatie om verbinding te maken met Exchange Online PowerShell met uw Office 365-referenties.</span><span class="sxs-lookup"><span data-stu-id="65ee1-138">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) to connect to Exchange Online PowerShell with your Office 365 credentials.</span></span> <span data-ttu-id="65ee1-139">U hoeft geen meervoudige verificatie in te schakelen voor uw organisatie om de stappen te gebruiken om geprivilegieerde toegang in te schakelen terwijl u verbinding maakt met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65ee1-139">You do not need to enable multi-factor authentication for your organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell.</span></span> <span data-ttu-id="65ee1-140">Als u verbinding maakt met meervoudige verificatie, wordt een OAuth-token gemaakt dat wordt gebruikt door bevoorrechte toegang voor het ondertekenen van uw aanvragen.</span><span class="sxs-lookup"><span data-stu-id="65ee1-140">Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="65ee1-141"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="65ee1-141"><a name="step1"> </a></span></span>

## <a name="step-1-create-an-approvers-group"></a><span data-ttu-id="65ee1-142">Stap 1: De groep van een goedkeurder maken</span><span class="sxs-lookup"><span data-stu-id="65ee1-142">Step 1: Create an approver's group</span></span>

1. <span data-ttu-id="65ee1-143">Meld u aan [bij Microsoft 365 beheercentrum met](https://admin.microsoft.com) referenties voor een beheerdersaccount in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="65ee1-143">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="65ee1-144">Ga in het beheercentrum naar **Groepen**  >  **een groep toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="65ee1-144">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="65ee1-145">Selecteer **beveiligingsgroep met e-mail** en vul vervolgens de  velden **Naam,** E-mailadres groep **en** Beschrijving voor de nieuwe groep in.</span><span class="sxs-lookup"><span data-stu-id="65ee1-145">Select **mail-enabled security group** and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="65ee1-146">Sla de groep op.</span><span class="sxs-lookup"><span data-stu-id="65ee1-146">Save the group.</span></span> <span data-ttu-id="65ee1-147">Het kan enkele minuten duren voordat de groep volledig is geconfigureerd en wordt weergegeven in het Microsoft 365 beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="65ee1-147">It may take a few minutes for the group to be fully configured and to appear in the Microsoft 365 admin center.</span></span>

5. <span data-ttu-id="65ee1-148">Selecteer de groep nieuwe goedkeurder en selecteer **Bewerken om** gebruikers aan de groep toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="65ee1-148">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="65ee1-149">Sla de groep op.</span><span class="sxs-lookup"><span data-stu-id="65ee1-149">Save the group.</span></span>

<span data-ttu-id="65ee1-150"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="65ee1-150"><a name="step2"> </a></span></span>

## <a name="step-2-enable-privileged-access"></a><span data-ttu-id="65ee1-151">Stap 2: Geprivilegieerde toegang inschakelen</span><span class="sxs-lookup"><span data-stu-id="65ee1-151">Step 2: Enable privileged access</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="65ee1-152">In het Microsoft 365 beheercentrum</span><span class="sxs-lookup"><span data-stu-id="65ee1-152">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="65ee1-153">Meld u aan [bij Microsoft 365 beheercentrum met](https://admin.microsoft.com) referenties voor een beheerdersaccount in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="65ee1-153">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="65ee1-154">Ga in het beheercentrum naar **Instellingen**  >  **Organisatie Instellingen**  >  **Beveiligings- & privacyprivilegetoegang.**  >  </span><span class="sxs-lookup"><span data-stu-id="65ee1-154">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="65ee1-155">Schakel het **besturingselement Goedkeuringen vereisen voor bevoorrechte taken** in.</span><span class="sxs-lookup"><span data-stu-id="65ee1-155">Enable the **Require approvals for privileged tasks** control.</span></span>

4. <span data-ttu-id="65ee1-156">Wijs de groep goedkeurder toe die u in stap 1 hebt gemaakt als de **groep Standaardkeurders.**</span><span class="sxs-lookup"><span data-stu-id="65ee1-156">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="65ee1-157">**Opslaan** en **sluiten.**</span><span class="sxs-lookup"><span data-stu-id="65ee1-157">**Save** and **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="65ee1-158">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="65ee1-158">In Exchange Management PowerShell</span></span>

<span data-ttu-id="65ee1-159">Als u geprivilegieerde toegang wilt inschakelen en de groep van de goedkeurder wilt toewijzen, moet u de volgende opdracht uitvoeren in Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="65ee1-159">To enable privileged access and to assign the approver's group, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

<span data-ttu-id="65ee1-160">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="65ee1-160">Example:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', 'sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
><span data-ttu-id="65ee1-161">De functie Systeemaccounts wordt beschikbaar gesteld om ervoor te zorgen dat bepaalde automatiseringen binnen uw organisaties kunnen werken zonder afhankelijk te zijn van geprivilegieerde toegang, maar het wordt aanbevolen dat dergelijke uitsluitingen bijzonder zijn en dat deze worden toegestaan, regelmatig moeten worden goedgekeurd en gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="65ee1-161">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="65ee1-162"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="65ee1-162"><a name="step3"> </a></span></span>

## <a name="step-3-create-an-access-policy"></a><span data-ttu-id="65ee1-163">Stap 3: Een toegangsbeleid maken</span><span class="sxs-lookup"><span data-stu-id="65ee1-163">Step 3: Create an access policy</span></span>

<span data-ttu-id="65ee1-164">U kunt maximaal 30 beleidsregels voor geprivilegieerde toegang voor uw organisatie maken en configureren.</span><span class="sxs-lookup"><span data-stu-id="65ee1-164">You can create and configure up to 30 privileged access policies for your organization.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="65ee1-165">In het Microsoft 365 beheercentrum</span><span class="sxs-lookup"><span data-stu-id="65ee1-165">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="65ee1-166">Meld u aan [bij Microsoft 365 beheercentrum met](https://admin.microsoft.com) referenties voor een beheerdersaccount in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="65ee1-166">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="65ee1-167">Ga in het beheercentrum naar **Instellingen**  >  **Organisatie Instellingen**  >  **Beveiligings- & privacyprivilegetoegang.**  >  </span><span class="sxs-lookup"><span data-stu-id="65ee1-167">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="65ee1-168">Selecteer **Toegangsbeleid en -aanvragen beheren.**</span><span class="sxs-lookup"><span data-stu-id="65ee1-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="65ee1-169">Selecteer **Beleid configureren** en selecteer **Beleid toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="65ee1-169">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="65ee1-170">Selecteer in de vervolgkeuzevelden de juiste waarden voor uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="65ee1-170">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="65ee1-171">**Beleidstype**: Taak, Rol of Rollengroep</span><span class="sxs-lookup"><span data-stu-id="65ee1-171">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="65ee1-172">**Beleidsbereik:** Exchange</span><span class="sxs-lookup"><span data-stu-id="65ee1-172">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="65ee1-173">**Beleidsnaam:** Selecteren uit het beschikbare beleid</span><span class="sxs-lookup"><span data-stu-id="65ee1-173">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="65ee1-174">**Goedkeuringstype**: Handmatig of Automatisch</span><span class="sxs-lookup"><span data-stu-id="65ee1-174">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="65ee1-175">**Goedkeuringsgroep**: Selecteer de groep goedkeurders die is gemaakt in stap 1</span><span class="sxs-lookup"><span data-stu-id="65ee1-175">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="65ee1-176">Selecteer **Maken** en vervolgens **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="65ee1-176">Select **Create** and then **Close**.</span></span> <span data-ttu-id="65ee1-177">Het kan enkele minuten duren voordat het beleid volledig is geconfigureerd en ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="65ee1-177">It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="65ee1-178">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="65ee1-178">In Exchange Management PowerShell</span></span>

<span data-ttu-id="65ee1-179">Als u een goedkeuringsbeleid wilt maken en definiëren, moet u de volgende opdracht uitvoeren in Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="65ee1-179">To create and define an approval policy, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

<span data-ttu-id="65ee1-180">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="65ee1-180">Example:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="65ee1-181"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="65ee1-181"><a name="step4"> </a></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="65ee1-182">Stap 4: Aanvragen voor geprivilegieerde toegang indienen/goedkeuren</span><span class="sxs-lookup"><span data-stu-id="65ee1-182">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="65ee1-183">Hoogteautorisatie aanvragen om bevoorrechte taken uit te voeren</span><span class="sxs-lookup"><span data-stu-id="65ee1-183">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="65ee1-184">Aanvragen voor bevoorrechte toegang zijn geldig tot 24 uur nadat de aanvraag is ingediend.</span><span class="sxs-lookup"><span data-stu-id="65ee1-184">Requests for privileged access are valid for up to 24 hours after the request is submitted.</span></span> <span data-ttu-id="65ee1-185">Als de aanvragen niet zijn goedgekeurd of geweigerd, verlopen de aanvragen en wordt de toegang niet goedgekeurd.</span><span class="sxs-lookup"><span data-stu-id="65ee1-185">If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="65ee1-186">In het Microsoft 365 beheercentrum</span><span class="sxs-lookup"><span data-stu-id="65ee1-186">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="65ee1-187">Meld u aan [bij Microsoft 365 beheercentrum](https://admin.microsoft.com) met uw referenties.</span><span class="sxs-lookup"><span data-stu-id="65ee1-187">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using your credentials.</span></span>

2. <span data-ttu-id="65ee1-188">Ga in het beheercentrum naar **Instellingen**  >  **Organisatie Instellingen**  >  **Beveiligings- & privacyprivilegetoegang.**  >  </span><span class="sxs-lookup"><span data-stu-id="65ee1-188">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="65ee1-189">Selecteer **Toegangsbeleid en -aanvragen beheren.**</span><span class="sxs-lookup"><span data-stu-id="65ee1-189">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="65ee1-190">Selecteer **Nieuwe aanvraag.**</span><span class="sxs-lookup"><span data-stu-id="65ee1-190">Select **New request**.</span></span> <span data-ttu-id="65ee1-191">Selecteer in de vervolgkeuzevelden de juiste waarden voor uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="65ee1-191">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="65ee1-192">**Aanvraagtype**: Taak, Rol of Rollengroep</span><span class="sxs-lookup"><span data-stu-id="65ee1-192">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="65ee1-193">**Aanvraagbereik**: Exchange</span><span class="sxs-lookup"><span data-stu-id="65ee1-193">**Request scope**: Exchange</span></span>

    <span data-ttu-id="65ee1-194">**Aanvraag voor**: Selecteren uit het beschikbare beleid</span><span class="sxs-lookup"><span data-stu-id="65ee1-194">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="65ee1-195">**Duur (uren)**: Aantal uren van aangevraagde toegang.</span><span class="sxs-lookup"><span data-stu-id="65ee1-195">**Duration (hours)**: Number of hours of requested access.</span></span> <span data-ttu-id="65ee1-196">Er is geen limiet voor het aantal uren dat kan worden aangevraagd.</span><span class="sxs-lookup"><span data-stu-id="65ee1-196">There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="65ee1-197">**Opmerkingen**: Tekstveld voor opmerkingen met betrekking tot uw toegangsaanvraag</span><span class="sxs-lookup"><span data-stu-id="65ee1-197">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="65ee1-198">Selecteer **Opslaan** en vervolgens **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="65ee1-198">Select **Save** and then **Close**.</span></span> <span data-ttu-id="65ee1-199">Uw aanvraag wordt per e-mail naar de groep van de goedkeurder verzonden.</span><span class="sxs-lookup"><span data-stu-id="65ee1-199">Your request will be sent to the approver's group via email.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="65ee1-200">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="65ee1-200">In Exchange Management PowerShell</span></span>

<span data-ttu-id="65ee1-201">Voer de volgende opdracht uit in Exchange Online PowerShell om een goedkeuringsaanvraag te maken en in te dienen bij de groep van de goedkeurder:</span><span class="sxs-lookup"><span data-stu-id="65ee1-201">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

<span data-ttu-id="65ee1-202">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="65ee1-202">Example:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="65ee1-203">Status van hoogte-aanvragen weergeven</span><span class="sxs-lookup"><span data-stu-id="65ee1-203">View status of elevation requests</span></span>

<span data-ttu-id="65ee1-204">Nadat een goedkeuringsaanvraag is gemaakt, kan de status van de aanvraag voor hoogte worden gecontroleerd in het beheercentrum of in Exchange Management PowerShell met behulp van de bijbehorende aanvraag-id.</span><span class="sxs-lookup"><span data-stu-id="65ee1-204">After an approval request is created, elevation request status can be reviewed in the admin center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="65ee1-205">In het Microsoft 365 beheercentrum</span><span class="sxs-lookup"><span data-stu-id="65ee1-205">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="65ee1-206">Meld u aan [bij Microsoft 365 beheercentrum](https://admin.microsoft.com) met uw referenties.</span><span class="sxs-lookup"><span data-stu-id="65ee1-206">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="65ee1-207">Ga in het beheercentrum naar **Instellingen**  >  **Organisatie Instellingen** Beveiliging &  >  **Privacy**  >  **privileged access**.</span><span class="sxs-lookup"><span data-stu-id="65ee1-207">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="65ee1-208">Selecteer **Toegangsbeleid en -aanvragen beheren.**</span><span class="sxs-lookup"><span data-stu-id="65ee1-208">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="65ee1-209">Selecteer **Weergave om** ingediende aanvragen te filteren op Status **in** behandeling, Goedgekeurd, **Geweigerd** of **Klantenvergrendeling.** </span><span class="sxs-lookup"><span data-stu-id="65ee1-209">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="65ee1-210">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="65ee1-210">In Exchange Management PowerShell</span></span>

<span data-ttu-id="65ee1-211">Voer de volgende opdracht uit in Exchange Online PowerShell om de status van een goedkeuringsaanvraag voor een specifieke aanvraag-id weer te geven:</span><span class="sxs-lookup"><span data-stu-id="65ee1-211">Run the following command in Exchange Online PowerShell to view an approval request status for a specific request ID:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

<span data-ttu-id="65ee1-212">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="65ee1-212">Example:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="65ee1-213">Goedkeuring van een aanvraag voor verhogingsautorisatie</span><span class="sxs-lookup"><span data-stu-id="65ee1-213">Approving an elevation authorization request</span></span>

<span data-ttu-id="65ee1-214">Wanneer een goedkeuringsaanvraag wordt gemaakt, ontvangen leden van de relevante groep goedkeurder een e-mailmelding en kunnen ze de aanvraag goedkeuren die is gekoppeld aan de aanvraag-id.</span><span class="sxs-lookup"><span data-stu-id="65ee1-214">When an approval request is created, members of the relevant approver group receive an email notification and can approve the request associated with the request ID.</span></span> <span data-ttu-id="65ee1-215">De aanmelder wordt via een e-mailbericht op de hoogte gesteld van de goedkeuring of weigering van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="65ee1-215">The requestor is notified of the request approval or denial via email message.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="65ee1-216">In het Microsoft 365 beheercentrum</span><span class="sxs-lookup"><span data-stu-id="65ee1-216">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="65ee1-217">Meld u aan [bij Microsoft 365 beheercentrum](https://admin.microsoft.com) met uw referenties.</span><span class="sxs-lookup"><span data-stu-id="65ee1-217">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="65ee1-218">Ga in het beheercentrum naar **Instellingen**  >  **Organisatie Instellingen** Beveiliging &  >  **Privacy**  >  **privileged access**.</span><span class="sxs-lookup"><span data-stu-id="65ee1-218">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="65ee1-219">Selecteer **Toegangsbeleid en -aanvragen beheren.**</span><span class="sxs-lookup"><span data-stu-id="65ee1-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="65ee1-220">Selecteer een lijst met aanvragen om de details te bekijken en actie te ondernemen op de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="65ee1-220">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="65ee1-221">Selecteer **Goedkeuren** om de aanvraag goed te keuren of selecteer **Weigeren om** de aanvraag te weigeren.</span><span class="sxs-lookup"><span data-stu-id="65ee1-221">Select **Approve** to approve the request or select **Deny** to deny the request.</span></span> <span data-ttu-id="65ee1-222">Eerder goedgekeurde aanvragen kunnen toegang intrekken door **Intrekken te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="65ee1-222">Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="65ee1-223">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="65ee1-223">In Exchange Management PowerShell</span></span>

<span data-ttu-id="65ee1-224">Voer de volgende opdracht uit in PowerShell om een aanvraag voor hoogtetoestemming goed te Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="65ee1-224">To approve an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

<span data-ttu-id="65ee1-225">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="65ee1-225">Example:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="65ee1-226">Als u een machtigingsaanvraag voor hoogte-verhoging wilt weigeren, moet u de volgende opdracht uitvoeren in Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="65ee1-226">To deny an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

<span data-ttu-id="65ee1-227">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="65ee1-227">Example:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="65ee1-228">Een beleid voor geprivilegieerde toegang verwijderen in Office 365</span><span class="sxs-lookup"><span data-stu-id="65ee1-228">Delete a privileged access policy in Office 365</span></span>

<span data-ttu-id="65ee1-229">Als dit niet meer nodig is in uw organisatie, kunt u een beleid voor geprivilegieerde toegang verwijderen.</span><span class="sxs-lookup"><span data-stu-id="65ee1-229">If it is no longer needed in your organization, you can delete a privileged access policy.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="65ee1-230">In het Microsoft 365 beheercentrum</span><span class="sxs-lookup"><span data-stu-id="65ee1-230">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="65ee1-231">Meld u aan [bij Microsoft 365 beheercentrum met](https://admin.microsoft.com) referenties voor een beheerdersaccount in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="65ee1-231">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="65ee1-232">Ga in het beheercentrum naar **Instellingen**  >  **Organisatie Instellingen** Beveiliging &  >  **Privacy**  >  **privileged access**.</span><span class="sxs-lookup"><span data-stu-id="65ee1-232">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="65ee1-233">Selecteer **Toegangsbeleid en -aanvragen beheren.**</span><span class="sxs-lookup"><span data-stu-id="65ee1-233">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="65ee1-234">Selecteer **Beleid configureren.**</span><span class="sxs-lookup"><span data-stu-id="65ee1-234">Select **Configure policies**.</span></span>

5. <span data-ttu-id="65ee1-235">Selecteer het beleid dat u wilt verwijderen en selecteer Beleid **verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="65ee1-235">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="65ee1-236">Selecteer **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="65ee1-236">Select **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="65ee1-237">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="65ee1-237">In Exchange Management PowerShell</span></span>

<span data-ttu-id="65ee1-238">Als u een beleid voor geprivilegieerde toegang wilt verwijderen, moet u de volgende opdracht uitvoeren in Exchange Online Powershell:</span><span class="sxs-lookup"><span data-stu-id="65ee1-238">To delete a privileged access policy, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="65ee1-239">Bevoorrechte toegang uitschakelen in Office 365</span><span class="sxs-lookup"><span data-stu-id="65ee1-239">Disable privileged access in Office 365</span></span>

<span data-ttu-id="65ee1-240">Indien nodig kunt u bevoorrecht toegangsbeheer voor uw organisatie uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="65ee1-240">If needed, you can disable privileged access management for your organization.</span></span> <span data-ttu-id="65ee1-241">Als u geprivilegieerde toegang uit kunt uitschakelen, worden geen bijbehorend goedkeuringsbeleid of goedkeuringsgroepen verwijderd.</span><span class="sxs-lookup"><span data-stu-id="65ee1-241">Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="65ee1-242">In het Microsoft 365 beheercentrum</span><span class="sxs-lookup"><span data-stu-id="65ee1-242">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="65ee1-243">Meld u aan [bij Microsoft 365 beheercentrum](https://admin.microsoft.com) met referenties voor een beheerdersaccount in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="65ee1-243">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="65ee1-244">Ga in het beheercentrum naar **Instellingen**  >  **Organisatie Instellingen**  >  **Beveiligings- & privacyprivilegetoegang.**  >  </span><span class="sxs-lookup"><span data-stu-id="65ee1-244">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="65ee1-245">Schakel het **besturingselement Goedkeuringen vereisen voor bevoorrechte toegang** in.</span><span class="sxs-lookup"><span data-stu-id="65ee1-245">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="65ee1-246">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="65ee1-246">In Exchange Management PowerShell</span></span>

<span data-ttu-id="65ee1-247">Als u geprivilegieerde toegang wilt uitschakelen, moet u de volgende opdracht uitvoeren in Exchange Online Powershell:</span><span class="sxs-lookup"><span data-stu-id="65ee1-247">To disable privileged access, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Disable-ElevatedAccessControl
```
