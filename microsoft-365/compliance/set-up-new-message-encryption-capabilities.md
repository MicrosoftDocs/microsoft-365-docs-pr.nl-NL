---
title: De nieuwe mogelijkheden van Message Encryption instellen
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Meer informatie over de nieuwe mogelijkheden voor berichtversleuteling van Office 365 waarmee beveiligde e-mailcommunicatie mogelijk wordt met personen binnen en buiten uw organisatie.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9b738c0f93b8958e441b34b458942c2b34c16661
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228577"
---
# <a name="set-up-new-message-encryption-capabilities"></a><span data-ttu-id="791b1-103">De nieuwe mogelijkheden van Message Encryption instellen</span><span class="sxs-lookup"><span data-stu-id="791b1-103">Set up new Message Encryption capabilities</span></span>

<span data-ttu-id="791b1-104">Met de nieuwe mogelijkheden voor berichtversleuteling van Office 365 kunnen organisaties beveiligde e-mail delen met iedereen, op elk apparaat.</span><span class="sxs-lookup"><span data-stu-id="791b1-104">The new Office 365 Message Encryption (OME) capabilities allow organizations to share protected email with anyone on any device.</span></span> <span data-ttu-id="791b1-105">Gebruikers kunnen beveiligde berichten uitwisselen met andere Microsoft 365-organisaties en niet-klanten met Outlook.com, Gmail en andere e-mailservices.</span><span class="sxs-lookup"><span data-stu-id="791b1-105">Users can exchange protected messages with other Microsoft 365 organizations, as well as non-customers using Outlook.com, Gmail, and other email services.</span></span>

<span data-ttu-id="791b1-106">Volg de onderstaande stappen om ervoor te zorgen dat de nieuwe OME-mogelijkheden beschikbaar zijn in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="791b1-106">Follow the steps below to ensure that the new OME capabilities are available in your organization.</span></span>

## <a name="verify-that-azure-rights-management-is-active"></a><span data-ttu-id="791b1-107">Controleren of Azure Rights Management actief is</span><span class="sxs-lookup"><span data-stu-id="791b1-107">Verify that Azure Rights Management is active</span></span>

<span data-ttu-id="791b1-108">De nieuwe mogelijkheden vaan OME maken gebruik van de beveiligingsfuncties in [Azure Rights Management Services (Azure RMS)](/azure/information-protection/what-is-information-protection), de technologie die door [Azure Information Protection](/azure/information-protection/what-is-azure-rms) wordt gebruikt om e-mailberichten en documenten te beveiligen via versleuteling en toegangscontrole.</span><span class="sxs-lookup"><span data-stu-id="791b1-108">The new OME capabilities leverage the protection features in [Azure Rights Management Services (Azure RMS)](/azure/information-protection/what-is-information-protection), the technology used by [Azure Information Protection](/azure/information-protection/what-is-azure-rms) to protect emails and documents via encryption and access controls.</span></span>

<span data-ttu-id="791b1-109">De enige vereiste voor het gebruik van de nieuwe OME-mogelijkheden is dat [Azure Rights Management](/azure/information-protection/what-is-azure-rms) moet worden geactiveerd op de tenant van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="791b1-109">The only prerequisite for using the new OME capabilities is that [Azure Rights Management](/azure/information-protection/what-is-azure-rms) must be activated in your organization's tenant.</span></span> <span data-ttu-id="791b1-110">Als dat zo is, activeert Microsoft 365 automatisch de nieuwe OME-mogelijkheden en hoeft u niets te doen.</span><span class="sxs-lookup"><span data-stu-id="791b1-110">If it is, Microsoft 365 activates the new OME capabilities automatically and you don't need to do anything.</span></span>

<span data-ttu-id="791b1-111">Azure RMS wordt ook automatisch geactiveerd voor de meeste abonnementen die hiervoor in aanmerking komen, dus u hoeft hiervoor waarschijnlijk ook niets te doen.</span><span class="sxs-lookup"><span data-stu-id="791b1-111">Azure RMS is also activated automatically for most eligible plans, so you probably don't have to do anything in this regard either.</span></span> <span data-ttu-id="791b1-112">Zie [Azure Rights Management activeren](/azure/information-protection/activate-service) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="791b1-112">See [Activating Azure Rights Management](/azure/information-protection/activate-service) for more information.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="791b1-113">Als u de Active Directory Rights Management-service (AD RMS) gebruikt met Exchange Online, moet u [migreren naar Azure Information Protection](/azure/information-protection/migrate-from-ad-rms-to-azure-rms) voordat u de nieuwe OME-mogelijkheden kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="791b1-113">If you use Active Directory Rights Management service (AD RMS) with Exchange Online, you need to [migrate to Azure Information Protection](/azure/information-protection/migrate-from-ad-rms-to-azure-rms) before you can use the new OME capabilities.</span></span> <span data-ttu-id="791b1-114">OME is niet compatibel met AD RMS.</span><span class="sxs-lookup"><span data-stu-id="791b1-114">OME is not compatible with AD RMS.</span></span>

<span data-ttu-id="791b1-115">Zie voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="791b1-115">For more information, see:</span></span>

- <span data-ttu-id="791b1-116">[Welke abonnementen heb ik nodig om de nieuwe OME-mogelijkheden te kunnen gebruiken?](ome-faq.yml#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities-) om te controleren of uw abonnement Azure Information Protection (met Azure RMS-functionaliteit) omvat.</span><span class="sxs-lookup"><span data-stu-id="791b1-116">[What subscriptions do I need to use the new OME capabilities?](ome-faq.yml#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities-) to check whether your subscription plan includes Azure Information Protection (which includes Azure RMS functionality).</span></span>
- <span data-ttu-id="791b1-117">[Azure Information Protection](https://azure.microsoft.com/services/information-protection/) voor informatie over de aankoop van een in aanmerking komend abonnement.</span><span class="sxs-lookup"><span data-stu-id="791b1-117">[Azure Information Protection](https://azure.microsoft.com/services/information-protection/) for information about purchasing an eligible subscription.</span></span>

### <a name="manually-activating-azure-rights-management"></a><span data-ttu-id="791b1-118">Azure Rights Management handmatig activeren</span><span class="sxs-lookup"><span data-stu-id="791b1-118">Manually activating Azure Rights Management</span></span>

<span data-ttu-id="791b1-119">Als u Azure RMS heeft uitgeschakeld, of als het niet automatisch geactiveerd is, dan kunt u het handmatig activeren in het:</span><span class="sxs-lookup"><span data-stu-id="791b1-119">If you disabled Azure RMS, or if it was not automatically activated for any reason, you can activate it manually in the:</span></span>

- <span data-ttu-id="791b1-120">**Beheercentrum van Microsoft 365**: zie [Azure Rights Management activeren vanuit het beheercentrum](/azure/information-protection/activate-office365) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="791b1-120">**Microsoft 365 admin center**: See [How to activate Azure Rights Management from the admin center](/azure/information-protection/activate-office365) for instructions.</span></span>
- <span data-ttu-id="791b1-121">**Azure-portaal**: zie [Azure Rights Management activeren vanuit het Azure-portaal](/azure/information-protection/activate-azure) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="791b1-121">**Azure portal**: See [How to activate Azure Rights Management from the Azure portal](/azure/information-protection/activate-azure) for instructions.</span></span>

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a><span data-ttu-id="791b1-122">Beheer van de tenantsleutel van Azure Information Protection configureren</span><span class="sxs-lookup"><span data-stu-id="791b1-122">Configure management of your Azure Information Protection tenant key</span></span>

<span data-ttu-id="791b1-123">Deze stap is optioneel.</span><span class="sxs-lookup"><span data-stu-id="791b1-123">This is an optional step.</span></span> <span data-ttu-id="791b1-124">Microsoft toestaan de hoofdsleutel voor Azure Information Protection te beheren, is de standaardinstelling en aanbevolen praktijk voor de meeste organisaties.</span><span class="sxs-lookup"><span data-stu-id="791b1-124">Allowing Microsoft to manage the root key for Azure Information Protection is the default setting and recommended best practice for most organizations.</span></span> <span data-ttu-id="791b1-125">Als dit het geval is, hoeft u niets te doen.</span><span class="sxs-lookup"><span data-stu-id="791b1-125">If this is the case, you don't need to do anything.</span></span>

<span data-ttu-id="791b1-126">Er zijn diverse redenen, zoals compliancevereisten, waardoor u mogelijk uw eigen hoofdsleutel moet genereren en beheren (ook wel 'bring your own key' of BYOK).</span><span class="sxs-lookup"><span data-stu-id="791b1-126">There are many reasons, for example compliance requirements, that may necessitate you generating and managing your own root key (also known as bring your own key (BYOK)).</span></span> <span data-ttu-id="791b1-127">Als dit het geval is, raden we u aan de vereiste stappen uit te voeren voordat u de nieuwe OME-mogelijkheden instelt.</span><span class="sxs-lookup"><span data-stu-id="791b1-127">If this is the case, we recommend that you complete the required steps before setting up the new OME capabilities.</span></span> <span data-ttu-id="791b1-128">Zie [Azure Information Protection-tenantsleutels plannen en implementeren](/information-protection/plan-design/plan-implement-tenant-key) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="791b1-128">See [Planning and implementing your Azure Information Protection tenant key](/information-protection/plan-design/plan-implement-tenant-key) for more.</span></span>

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a><span data-ttu-id="791b1-129">Nieuwe OME-configuratie controleren in Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="791b1-129">Verify new OME configuration in Exchange Online PowerShell</span></span>

<span data-ttu-id="791b1-130">U kunt controleren of uw Microsoft 365-tenant correct is geconfigureerd voor het gebruik van de nieuwe OME-mogelijkheden in [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="791b1-130">You can verify that your Microsoft 365 tenant is properly configured to use the new OME capabilities in [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell).</span></span>

1. <span data-ttu-id="791b1-131">[Maak verbinding met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) met een account met algemene beheerdersmachtigingen in uw Microsoft 365-tenant.</span><span class="sxs-lookup"><span data-stu-id="791b1-131">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) using an account with global administrator permissions in your Microsoft 365 tenant.</span></span>

2. <span data-ttu-id="791b1-132">Voer de cmdlet Get-OrganizationConfig uit.</span><span class="sxs-lookup"><span data-stu-id="791b1-132">Run the Get-IRMConfiguration cmdlet.</span></span>

     <span data-ttu-id="791b1-133">U ziet nu een waarde $True voor de parameter AzureRMSLicensingEnabled, wat aangeeft dat OME is geconfigureerd in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="791b1-133">You should see a value of $True for the AzureRMSLicensingEnabled parameter, which indicates that OME is configured in your tenant.</span></span> <span data-ttu-id="791b1-134">Als dat niet zo is, gebruikt u Set-IRMConfiguration om de waarde van AzureRMSLicensingEnabled in te stellen op $True om OME in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="791b1-134">If it is not, use Set-IRMConfiguration to set the value of AzureRMSLicensingEnabled to $True to enable OME.</span></span>

3. <span data-ttu-id="791b1-135">Voer de cmdlet Test-IRMConfiguration uit met de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="791b1-135">Run the Test-IRMConfiguration cmdlet using the following syntax:</span></span>

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```

   <span data-ttu-id="791b1-136">**Voorbeeld**:</span><span class="sxs-lookup"><span data-stu-id="791b1-136">**Example**:</span></span>

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - <span data-ttu-id="791b1-137">Een e-mailadres van afzender opgeven is optioneel, maar indien u dit doet moet het systeem extra controles uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="791b1-137">Providing a sender email is optional, but forces the system to perform additional checks.</span></span> <span data-ttu-id="791b1-138">Gebruik het e-mailadres van een gebruiker in uw Microsoft 365-tenant.</span><span class="sxs-lookup"><span data-stu-id="791b1-138">Use the email address of any user in your Microsoft 365 tenant.</span></span>

     <span data-ttu-id="791b1-139">Uw resultaten zouden vergelijkbaar moeten zijn met:</span><span class="sxs-lookup"><span data-stu-id="791b1-139">Your results should be similar to:</span></span>

     ```text
     Results : Acquiring RMS Templates ...
                - PASS: RMS Templates acquired.  Templates available: Contoso  - Confidential View Only, Contoso  - Confidential, Do Not
            Forward.
            Verifying encryption ...
                - PASS: Encryption verified successfully.
            Verifying decryption ...
                - PASS: Decryption verified successfully.
            Verifying IRM is enabled ...
                - PASS: IRM verified successfully.

            OVERALL RESULT: PASS
     ```

   - <span data-ttu-id="791b1-140">De naam van uw organisatie vervangt *Contoso*.</span><span class="sxs-lookup"><span data-stu-id="791b1-140">Your organization name will replace *Contoso*.</span></span>

   - <span data-ttu-id="791b1-141">De standaard sjabloonnamen kunnen afwijken van de namen die hierboven worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="791b1-141">The default template names may be different from those displayed above.</span></span> <span data-ttu-id="791b1-142">Zie [Sjablonen voor Azure Information Protection configureren en beheren](/azure/information-protection/configure-policy-templates) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="791b1-142">See [Configuring and managing templates for Azure Information Protection](/azure/information-protection/configure-policy-templates) for more.</span></span>

4. <span data-ttu-id="791b1-143">Voer de cmdlet Remove-PSSession uit om de verbinding met de Rights Management-service te verbreken.</span><span class="sxs-lookup"><span data-stu-id="791b1-143">Run the Remove-PSSession cmdlet to disconnect from the Rights Management service.</span></span>

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a><span data-ttu-id="791b1-144">Volgende stappen: e-mailstroomregels definiëren om nieuwe OME-mogelijkheden te gebruiken</span><span class="sxs-lookup"><span data-stu-id="791b1-144">Next steps: Define mail flow rules to use new OME capabilities</span></span>

<span data-ttu-id="791b1-p110">Als er eerder geconfigureerde e-mailstroomregels zijn voor het versleutelen van e-mail in uw organisatie, moet u de bestaande regels bijwerken om de nieuwe OME-functionaliteit te gebruiken. Voor nieuwe implementaties moet u nieuwe e-mailstroomregels maken.</span><span class="sxs-lookup"><span data-stu-id="791b1-p110">If there are previously configured mail flow rules to encrypt email in your organization, you need to update the existing rules to use the new OME capabilities. For new deployments, you need to create new mail flow rules.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="791b1-147">Als u bestaande e-mailstroomregels niet bijwerkt, blijven uw gebruikers versleutelde e-mail ontvangen die de vorige HTML-bijlageindeling gebruikt, in plaats van de nieuwe, probleemloze OME-ervaring.</span><span class="sxs-lookup"><span data-stu-id="791b1-147">If you do not update existing mail flow rules, your users will continue to receive encrypted mail that uses the previous HTML attachment format, instead of the new seamless OME experience.</span></span>

<span data-ttu-id="791b1-148">E-mailstroomregels bepalen onder welke voorwaarden e-mailberichten moeten worden versleuteld, evenals voorwaarden voor het verwijderen van die versleuteling.</span><span class="sxs-lookup"><span data-stu-id="791b1-148">Mail flow rules determine under what conditions email messages should be encrypted, as well as conditions for removing that encryption.</span></span> <span data-ttu-id="791b1-149">Wanneer u een actie voor een regel in stelt, worden alle berichten die voldoen aan de voorwaarden voor de regel versleuteld bij verzending.</span><span class="sxs-lookup"><span data-stu-id="791b1-149">When you set an action for a rule, any messages that match the rule conditions are encrypted when they're sent.</span></span>

<span data-ttu-id="791b1-150">Zie [Regels voor de e-mailstroom definiëren om e-mailberichten in Office 365 te versleutelen in Office 365 voor](define-mail-flow-rules-to-encrypt-email.md) voor stappen om e-mailstroomregels voor OME aan te maken.</span><span class="sxs-lookup"><span data-stu-id="791b1-150">For steps on creating mail flow rules for OME, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

<span data-ttu-id="791b1-151">Bestaande regels bijwerken om de nieuwe OME-mogelijkheden te gebruiken:</span><span class="sxs-lookup"><span data-stu-id="791b1-151">To update existing rules to use the new OME capabilities:</span></span>

1. <span data-ttu-id="791b1-152">Ga in het Microsoft 365-beheercentrum naar **Beheercentrum > Exchange**.</span><span class="sxs-lookup"><span data-stu-id="791b1-152">In the Microsoft 365 admin center, go to **Admin centers > Exchange**.</span></span>
2. <span data-ttu-id="791b1-153">Ga in het Exchange-beheercentrum naar **E-mailstroom > Regels**.</span><span class="sxs-lookup"><span data-stu-id="791b1-153">In the Exchange admin center, go to **Mail flow > Rules**.</span></span>
3. <span data-ttu-id="791b1-154">Doe voor elke regel **het volgende**:</span><span class="sxs-lookup"><span data-stu-id="791b1-154">For each rule, in **Do the following**:</span></span>
    - <span data-ttu-id="791b1-155">Selecteer **Het beveiligingsbeleid voor berichten wijzigen**.</span><span class="sxs-lookup"><span data-stu-id="791b1-155">Select **Modify the message security**.</span></span>
    - <span data-ttu-id="791b1-156">Selecteer **Office 365-berichtversleuteling en rechtenbescherming toepassen**.</span><span class="sxs-lookup"><span data-stu-id="791b1-156">Select **Apply Office 365 Message Encryption and rights protection**.</span></span>
    - <span data-ttu-id="791b1-157">Selecteer een RMS-sjabloon in de lijst.</span><span class="sxs-lookup"><span data-stu-id="791b1-157">Select an RMS template from the list.</span></span>
    - <span data-ttu-id="791b1-158">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="791b1-158">Select **Save**.</span></span>
    - <span data-ttu-id="791b1-159">Selecteer **OK**.</span><span class="sxs-lookup"><span data-stu-id="791b1-159">Select **OK**.</span></span>
