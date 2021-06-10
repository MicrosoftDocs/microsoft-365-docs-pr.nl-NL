---
title: Een Azure Rights Management instellen voor de vorige versie van berichtversleuteling
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: De vorige versie van Office 365-berichtversleuteling is afhankelijk van Microsoft Azure Rights Management (voorheen Windows Azure Active Directory Rights Management).
ms.openlocfilehash: 978a8027c79de574b80aeedabcbbd51fa6f9e2a0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161974"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-message-encryption"></a><span data-ttu-id="79dfb-103">Een Azure Rights Management instellen voor de vorige versie van berichtversleuteling</span><span class="sxs-lookup"><span data-stu-id="79dfb-103">Set up Azure Rights Management for the previous version of Message Encryption</span></span>

<span data-ttu-id="79dfb-104">In dit onderwerp worden de stappen beschreven die u moet volgen om Azure Rights Management (RMS), onderdeel van Azure Information Protection, te activeren en in te stellen voor gebruik met de vorige versie van Office 365-berichtversleuteling (OME).</span><span class="sxs-lookup"><span data-stu-id="79dfb-104">This topic describes the steps you need to follow in order to activate and then set up Azure Rights Management (RMS), part of Azure Information Protection, for use with the previous version of Office 365 Message Encryption (OME).</span></span>

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a><span data-ttu-id="79dfb-105">Dit artikel is alleen van toepassing op de vorige versie van OME</span><span class="sxs-lookup"><span data-stu-id="79dfb-105">This article only applies to the previous version of OME</span></span>

<span data-ttu-id="79dfb-106">Als u uw organisatie nog niet hebt verplaatst naar de nieuwe OME-mogelijkheden, maar u OME al hebt geïmplementeerd, is de informatie in dit artikel van toepassing op uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="79dfb-106">If you haven't yet moved your organization to the new OME capabilities, but you have already deployed OME, then the information in this article applies to your organization.</span></span> <span data-ttu-id="79dfb-107">Microsoft raadt u aan een plan te maken om over te gaan naar de nieuwe OME-mogelijkheden zodra dit redelijk is voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="79dfb-107">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="79dfb-108">Zie Nieuwe functies voor Office 365-berichtversleuteling instellen voor [instructies.](set-up-new-message-encryption-capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="79dfb-108">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="79dfb-109">Als u eerst wilt weten hoe de nieuwe mogelijkheden werken, bekijkt [u Office 365-berichtversleuteling.](ome.md)</span><span class="sxs-lookup"><span data-stu-id="79dfb-109">If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md).</span></span> <span data-ttu-id="79dfb-110">De rest van dit artikel verwijst naar OME-gedrag vóór de release van de nieuwe OME-mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="79dfb-110">The rest of this article refers to OME behavior before the release of the new OME capabilities.</span></span>

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="79dfb-111">Vereisten voor het gebruik van de vorige versie van Office 365-berichtversleuteling</span><span class="sxs-lookup"><span data-stu-id="79dfb-111">Prerequisites for using the previous version of Office 365 Message Encryption</span></span>
<span data-ttu-id="79dfb-112"><a name="warmprereqs"> </a></span><span class="sxs-lookup"><span data-stu-id="79dfb-112"><a name="warmprereqs"> </a></span></span>

<span data-ttu-id="79dfb-113">Office 365-berichtversleuteling (OME), inclusief IRM, is afhankelijk van Azure Rights Management (Azure RMS).</span><span class="sxs-lookup"><span data-stu-id="79dfb-113">Office 365 Message Encryption (OME), including IRM, depends on Azure Rights Management (Azure RMS).</span></span> <span data-ttu-id="79dfb-114">Azure RMS is de beveiligingstechnologie die wordt gebruikt door Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="79dfb-114">Azure RMS is the protection technology used by Azure Information Protection.</span></span> <span data-ttu-id="79dfb-115">Als u OME wilt gebruiken, moet uw organisatie een abonnement Exchange Online of Exchange Online Protection dat op zijn beurt een Azure Rights Management bevat.</span><span class="sxs-lookup"><span data-stu-id="79dfb-115">To use OME, your organization must include an Exchange Online or Exchange Online Protection subscription that, in turn, includes an Azure Rights Management subscription.</span></span>
  
- <span data-ttu-id="79dfb-116">Als u niet zeker weet wat uw abonnement bevat, bekijkt u Exchange Online servicebeschrijvingen voor [berichtenbeleid, herstel en naleving.](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)</span><span class="sxs-lookup"><span data-stu-id="79dfb-116">If you're not sure of what your subscription includes, see the Exchange Online service descriptions for [Message Policy, Recovery, and Compliance](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).</span></span>

- <span data-ttu-id="79dfb-117">Als u Azure Rights Management hebt, maar deze niet is ingesteld voor Exchange Online of Exchange Online Protection, wordt in dit artikel uitgelegd hoe u Azure Rights Management activeert en beschrijft u de beste manier om OME in te stellen voor het werken met Azure Rights Management.</span><span class="sxs-lookup"><span data-stu-id="79dfb-117">If you have Azure Rights Management but it's not set up for Exchange Online or Exchange Online Protection, this article explains how to activate Azure Rights Management and then the describes the best way to set up OME to work with Azure Rights Management.</span></span>

- <span data-ttu-id="79dfb-118">Als u OME al hebt ingesteld voor gebruik met Azure Rights Management voor Exchange Online of Exchange Online Protection, kunt u, afhankelijk van hoe u het hebt ingesteld, direct aan de slag met OME en de nieuwe mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="79dfb-118">If you've already set up OME to work with Azure Rights Management for Exchange Online or Exchange Online Protection, depending on how you set it up, you may be ready to start using OME and its new capabilities right away.</span></span> <span data-ttu-id="79dfb-119">In dit artikel wordt uitgelegd hoe u kunt bepalen of u OME correct hebt ingesteld, wat u moet doen als u de instelling wilt wijzigen en wat er gebeurt als u ervoor kiest de instelling niet te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="79dfb-119">This article explains how to determine if you've set OME up correctly, what to do if you need to change your setup, and what happens if you choose not to change your setup.</span></span> <span data-ttu-id="79dfb-120">Als u bijvoorbeeld de nieuwe mogelijkheden wilt gebruiken, moet u Azure RMS met OME gebruiken.</span><span class="sxs-lookup"><span data-stu-id="79dfb-120">For example, in order to use the new capabilities, you must use Azure RMS with OME.</span></span> <span data-ttu-id="79dfb-121">U kunt de nieuwe mogelijkheden niet gebruiken met een on-premises Active Directory RMS.</span><span class="sxs-lookup"><span data-stu-id="79dfb-121">You can't use the new capabilities with an on-premises Active Directory RMS.</span></span>

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a><span data-ttu-id="79dfb-122">Activeer Azure Rights Management voor de vorige versie van OME in Office 365</span><span class="sxs-lookup"><span data-stu-id="79dfb-122">Activate Azure Rights Management for  the previous version of OME in Office 365</span></span>

<span data-ttu-id="79dfb-123">U moet Azure Rights Management activeren zodat de gebruikers in uw organisatie informatiebeveiliging kunnen toepassen op berichten die ze verzenden en berichten en bestanden kunnen openen die zijn beveiligd door de Azure Rights Management service.</span><span class="sxs-lookup"><span data-stu-id="79dfb-123">You need to activate Azure Rights Management so that the users in your organization can apply information protection to messages that they send, and open messages and files that have been protected by the Azure Rights Management service.</span></span> <span data-ttu-id="79dfb-124">Zie Activeren van Azure Rights Management voor [instructies.](/azure/information-protection/activate-service)</span><span class="sxs-lookup"><span data-stu-id="79dfb-124">For instructions, see [Activating Azure Rights Management](/azure/information-protection/activate-service).</span></span> <span data-ttu-id="79dfb-125">Nadat u de activering hebt voltooid, keert u hier terug en gaat u verder met de taken in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="79dfb-125">Once you've completed the activation, return here and continue with the tasks in this article.</span></span>
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a><span data-ttu-id="79dfb-126">De vorige versie van OME instellen om Azure RMS te gebruiken door vertrouwde publicatiedomeinen (TPD's) te importeren</span><span class="sxs-lookup"><span data-stu-id="79dfb-126">Set up the previous version of OME to use Azure RMS by importing trusted publishing domains (TPDs)</span></span>

<span data-ttu-id="79dfb-127">Een TPD is een XML-bestand dat informatie bevat over de instellingen voor rechtenbeheer van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="79dfb-127">A TPD is an XML file that contains information about your organization's rights management settings.</span></span> <span data-ttu-id="79dfb-128">De TPD bevat bijvoorbeeld informatie over het certificaat van de licentiegever voor de server (SLC) dat wordt gebruikt voor het ondertekenen en versleutelen van certificaten en licenties, de URL's die worden gebruikt voor licenties en publiceren, en meer.</span><span class="sxs-lookup"><span data-stu-id="79dfb-128">For example, the TPD contains information about the server licensor certificate (SLC) used for signing and encrypting certificates and licenses, the URLs used for licensing and publishing, and so on.</span></span> <span data-ttu-id="79dfb-129">U importeert de TPD in uw organisatie met Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="79dfb-129">You import the TPD into your organization by using Windows PowerShell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="79dfb-130">Voorheen kon u ervoor kiezen om TPD's uit de Active Directory Rights Management-service (AD RMS) in uw organisatie te importeren.</span><span class="sxs-lookup"><span data-stu-id="79dfb-130">Previously, you could choose to import TPDs from the Active Directory Rights Management service (AD RMS) into your organization.</span></span> <span data-ttu-id="79dfb-131">Dit voorkomt echter dat u de nieuwe OME-mogelijkheden gebruikt en wordt niet aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="79dfb-131">However, doing so will prevent you from using the new OME capabilities and is not recommended.</span></span> <span data-ttu-id="79dfb-132">Als uw organisatie op dit moment op deze manier is geconfigureerd, raadt Microsoft u aan een plan te maken om te migreren van uw on-premises Active Directory RMS naar Azure Information Protection in de cloud.</span><span class="sxs-lookup"><span data-stu-id="79dfb-132">If your organization is currently configured this way, Microsoft recommends that you create a plan to migrate from your on-premises Active Directory RMS to cloud-based Azure Information Protection.</span></span> <span data-ttu-id="79dfb-133">Zie Migreren van AD RMS naar Azure Information Protection voor [meer informatie.](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)</span><span class="sxs-lookup"><span data-stu-id="79dfb-133">For more information, see [Migrating from AD RMS to Azure Information Protection](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms).</span></span> <span data-ttu-id="79dfb-134">U kunt de nieuwe OME-mogelijkheden pas gebruiken als u de migratie naar Azure Information Protection hebt voltooid.</span><span class="sxs-lookup"><span data-stu-id="79dfb-134">You will not be able to use the new OME capabilities until you have completed the migration to Azure Information Protection.</span></span>
  
 <span data-ttu-id="79dfb-135">**TPD's importeren vanuit Azure RMS**</span><span class="sxs-lookup"><span data-stu-id="79dfb-135">**To import TPDs from Azure RMS**</span></span>
  
1. <span data-ttu-id="79dfb-136">[Verbinding maken om Exchange Online Externe PowerShell te gebruiken.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="79dfb-136">[Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="79dfb-137">Kies de URL voor het delen van sleutels die overeenkomt met de geografische locatie van uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="79dfb-137">Choose the key-sharing URL that corresponds to your organization's geographic location:</span></span>

|<span data-ttu-id="79dfb-138">**Locatie**</span><span class="sxs-lookup"><span data-stu-id="79dfb-138">**Location**</span></span>|<span data-ttu-id="79dfb-139">**Url voor het delen van sleutels**</span><span class="sxs-lookup"><span data-stu-id="79dfb-139">**Key sharing location URL**</span></span>|
|:-----|:-----|
|<span data-ttu-id="79dfb-140">Noord-Amerika</span><span class="sxs-lookup"><span data-stu-id="79dfb-140">North America</span></span>  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="79dfb-141">Europese Unie</span><span class="sxs-lookup"><span data-stu-id="79dfb-141">European Union</span></span>  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="79dfb-142">Azië</span><span class="sxs-lookup"><span data-stu-id="79dfb-142">Asia</span></span>  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="79dfb-143">Zuid-Amerika</span><span class="sxs-lookup"><span data-stu-id="79dfb-143">South America</span></span>  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="79dfb-144">Office 365 voor de overheid (Government Community Cloud)</span><span class="sxs-lookup"><span data-stu-id="79dfb-144">Office 365 for Government (Government Community Cloud)</span></span>  <br/> <span data-ttu-id="79dfb-145">Deze RMS-locatie voor het delen van sleutels is gereserveerd voor klanten die een Office 365 voor SKU's van de overheid hebben gekocht.</span><span class="sxs-lookup"><span data-stu-id="79dfb-145">This RMS key-sharing location is reserved for customers who have purchased Office 365 for Government SKUs.</span></span>  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
  
3. <span data-ttu-id="79dfb-146">Configureer de locatie voor het delen van sleutels door [de cmdlet Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) als volgt uit te stellen:</span><span class="sxs-lookup"><span data-stu-id="79dfb-146">Configure the key-sharing location by running the [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet as follows:</span></span> 

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
   ```
  
   <span data-ttu-id="79dfb-147">Als u bijvoorbeeld de locatie voor het delen van sleutels wilt configureren als uw organisatie zich in Noord-Amerika bevindt:</span><span class="sxs-lookup"><span data-stu-id="79dfb-147">For example, to configure the key sharing location if your organization is located in North America:</span></span>

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
   ```

4. <span data-ttu-id="79dfb-148">Voer de [cmdlet Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain) uit met de schakelknop -RMSOnline om de TPD te importeren uit Azure Rights Management:</span><span class="sxs-lookup"><span data-stu-id="79dfb-148">Run the [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain) cmdlet with the -RMSOnline switch to import the TPD from Azure Rights Management:</span></span> 

   ```powershell
   Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
   ```

   <span data-ttu-id="79dfb-149">Waarbij  *TPDName*  de naam is die u wilt gebruiken voor de TPD.</span><span class="sxs-lookup"><span data-stu-id="79dfb-149">Where  *TPDName*  is the name you want to use for the TPD.</span></span> <span data-ttu-id="79dfb-150">Bijvoorbeeld 'Contoso North American TPD'.</span><span class="sxs-lookup"><span data-stu-id="79dfb-150">For example, "Contoso North American TPD".</span></span> 

5. <span data-ttu-id="79dfb-151">Als u wilt controleren of u uw organisatie hebt geconfigureerd voor het gebruik van de Azure Rights Management-service, moet u de [cmdlet Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) als volgt uitvoeren met de -RMSOnline-schakelknop:</span><span class="sxs-lookup"><span data-stu-id="79dfb-151">To verify that you successfully configured your organization to use the Azure Rights Management service, run the [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) cmdlet with the -RMSOnline switch as follows:</span></span>

   ```powershell
   Test-IRMConfiguration -RMSOnline
   ```

   <span data-ttu-id="79dfb-152">Deze cmdlet controleert onder andere de connectiviteit met de Azure Rights Management service, downloadt de TPD en controleert de geldigheid.</span><span class="sxs-lookup"><span data-stu-id="79dfb-152">Among other things, this cmdlet checks connectivity with the Azure Rights Management service, downloads the TPD, and checks its validity.</span></span>

6. <span data-ttu-id="79dfb-153">Voer de [cmdlet Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) als volgt uit om Azure Rights Management-sjablonen uit te schakelen in Outlook web en Outlook:</span><span class="sxs-lookup"><span data-stu-id="79dfb-153">Run the [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet as follows to disable Azure Rights Management templates from being available in Outlook on the web and Outlook:</span></span> 

   ```powershell
   Set-IRMConfiguration -ClientAccessServerEnabled $false
   ```

7. <span data-ttu-id="79dfb-154">Voer de cmdlet [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) als volgt uit om Azure Rights Management in te stellen voor uw e-mailorganisatie in de cloud en deze te configureren voor Azure Rights Management voor Office 365-berichtversleuteling:</span><span class="sxs-lookup"><span data-stu-id="79dfb-154">Run the [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet as follows to enable Azure Rights Management for your cloud-based email organization and configure it to use Azure Rights Management for Office 365 Message Encryption:</span></span>

   ```powershell
   Set-IRMConfiguration -InternalLicensingEnabled $true
   ```

8. <span data-ttu-id="79dfb-155">Als u wilt controleren of u de TPD hebt geïmporteerd en Azure Rights Management hebt ingeschakeld, gebruikt u de Test-IRMConfiguration cmdlet om de functionaliteit Azure Rights Management testen.</span><span class="sxs-lookup"><span data-stu-id="79dfb-155">To verify that you have successfully imported the TPD and enabled Azure Rights Management, use the Test-IRMConfiguration cmdlet to test Azure Rights Management functionality.</span></span> <span data-ttu-id="79dfb-156">Zie 'Voorbeeld 1' in [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="79dfb-156">For details, see "Example 1" in [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration).</span></span>

## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a><span data-ttu-id="79dfb-157">Ik heb de vorige versie van OME ingesteld met Active Directory Rights Management niet Azure Information Protection, wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="79dfb-157">I have the previous version of OME set up with Active Directory Rights Management not Azure Information Protection, what do I do?</span></span>
<span data-ttu-id="79dfb-158"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="79dfb-158"><a name="importTPDs"> </a></span></span>

<span data-ttu-id="79dfb-159">U kunt uw bestaande Office 365-berichtversleuteling e-mailstroomregels blijven gebruiken met Active Directory Rights Management, maar u kunt de nieuwe OME-mogelijkheden niet configureren of gebruiken.</span><span class="sxs-lookup"><span data-stu-id="79dfb-159">You can continue to use your existing Office 365 Message Encryption mail flow rules with Active Directory Rights Management, but you can't configure or use the new OME capabilities.</span></span> <span data-ttu-id="79dfb-160">In plaats daarvan moet u migreren naar Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="79dfb-160">Instead, you need to migrate to Azure Information Protection.</span></span> <span data-ttu-id="79dfb-161">Zie Migreren van AD RMS naar Azure Information Protection voor informatie over migratie en wat dit betekent voor [uw organisatie.](/information-protection/deploy-use/prepare-environment-adrms)</span><span class="sxs-lookup"><span data-stu-id="79dfb-161">For information about migration and what this means for your organization, see [Migrating from AD RMS to Azure Information Protection](/information-protection/deploy-use/prepare-environment-adrms).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="79dfb-162">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="79dfb-162">Next steps</span></span>
<span data-ttu-id="79dfb-163"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="79dfb-163"><a name="importTPDs"> </a></span></span>

<span data-ttu-id="79dfb-164">Als u de configuratie van Azure Rights Management hebt voltooid en u de nieuwe OME-mogelijkheden wilt inschakelen, gaat u naar Nieuwe Office 365-berichtversleuteling-functies instellen die bovenop Azure Information Protection zijn [gebouwd.](./set-up-new-message-encryption-capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="79dfb-164">Once you've completed Azure Rights Management setup, if you want to enable the new OME capabilities, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection.](./set-up-new-message-encryption-capabilities.md)</span></span>
  
<span data-ttu-id="79dfb-165">Nadat u uw organisatie hebt ingesteld voor het gebruik van de nieuwe OME-mogelijkheden, kunt u regels voor e-mailstroom definiëren om e-mailberichten te beveiligen met nieuwe [OME-mogelijkheden.](define-mail-flow-rules-to-encrypt-email.md)</span><span class="sxs-lookup"><span data-stu-id="79dfb-165">After you've set up your organization to use the new OME capabilities, you're ready to [Define mail flow rules to protect email messages with new OME capabilities](define-mail-flow-rules-to-encrypt-email.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="79dfb-166">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="79dfb-166">Related topics</span></span>
<span data-ttu-id="79dfb-167"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="79dfb-167"><a name="importTPDs"> </a></span></span>

[<span data-ttu-id="79dfb-168">Versleuteling in Office 365</span><span class="sxs-lookup"><span data-stu-id="79dfb-168">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="79dfb-169">Technische naslaginformatie over versleuteling in Office 365</span><span class="sxs-lookup"><span data-stu-id="79dfb-169">Technical reference details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="79dfb-170">Wat is Azure Rights Management?</span><span class="sxs-lookup"><span data-stu-id="79dfb-170">What is Azure Rights Management?</span></span>](/information-protection/understand-explore/what-is-azure-rms)