---
title: IRM configureren voor gebruik van een on-premises AD RMS-server
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3ecde857-4b7c-451d-b4aa-9eeffc8a8c61
ms.collection:
- M365-security-compliance
description: Informatie over het configureren van IRM (Information Rights Management) in Exchange Online om een AD RMS-server (Active Directory Rights Management Service) te gebruiken.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5e430f9c6ad5d377b568d22e9de53ab79d19165a
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2021
ms.locfileid: "52162681"
---
# <a name="configure-irm-to-use-an-on-premises-ad-rms-server"></a><span data-ttu-id="785a5-103">IRM configureren voor gebruik van een on-premises AD RMS-server</span><span class="sxs-lookup"><span data-stu-id="785a5-103">Configure IRM to use an on-premises AD RMS server</span></span>
  
<span data-ttu-id="785a5-104">Voor gebruik met on-premises implementaties gebruikt IRM (Information Rights Management) in Exchange Online Active Directory Rights Management Services (AD RMS), een informatiebeveiligingstechnologie in Windows Server 2008 en hoger.</span><span class="sxs-lookup"><span data-stu-id="785a5-104">For use with on-premises deployments, Information Rights Management (IRM) in Exchange Online uses Active Directory Rights Management Services (AD RMS), an information protection technology in Windows Server 2008 and later.</span></span> <span data-ttu-id="785a5-105">IRM-beveiliging wordt toegepast op e-mail door een AD RMS-beleidssjabloon voor rechten toe te passen op een e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="785a5-105">IRM protection is applied to email by applying an AD RMS rights policy template to an email message.</span></span> <span data-ttu-id="785a5-106">Rechten zijn gekoppeld aan het bericht zelf, zodat de beveiliging online en offline en binnen en buiten de firewall van uw organisatie plaatsvindt.</span><span class="sxs-lookup"><span data-stu-id="785a5-106">Rights are attached to the message itself so that protection occurs online and offline and inside and outside of your organization's firewall.</span></span>
  
<span data-ttu-id="785a5-107">In dit onderwerp ziet u hoe u IRM configureert voor het gebruik van een AD RMS-server.</span><span class="sxs-lookup"><span data-stu-id="785a5-107">This topic shows you how to configure IRM to use an AD RMS server.</span></span> <span data-ttu-id="785a5-108">Zie de veelgestelde vragen over het gebruik van de nieuwe Office 365-berichtversleuteling voor Azure Active Directory en Azure Rights Management [Office 365-berichtversleuteling.](./ome-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="785a5-108">For information about using the new capabilities for Office 365 Message Encryption with Azure Active Directory and Azure Rights Management, see the [Office 365 Message Encryption FAQ](./ome-faq.yml).</span></span>
  
<span data-ttu-id="785a5-109">Zie Information Rights Management in Exchange Online voor meer informatie over IRM [in Exchange Online.](information-rights-management-in-exchange-online.md)</span><span class="sxs-lookup"><span data-stu-id="785a5-109">To learn more about IRM in Exchange Online, see [Information Rights Management in Exchange Online](information-rights-management-in-exchange-online.md).</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="785a5-110">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="785a5-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="785a5-111">Geschatte tijd om deze taak te voltooien: 30 minuten</span><span class="sxs-lookup"><span data-stu-id="785a5-111">Estimated time to complete this task: 30 minutes</span></span>

- <span data-ttu-id="785a5-112">U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="785a5-112">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="785a5-113">Zie de vermelding 'Information Rights Management' in het onderwerp Berichtbeleid en [compliancemachtigingen](/Exchange/permissions/feature-permissions/policy-and-compliance-permissions) om te zien welke machtigingen u nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="785a5-113">To see what permissions you need, see the "Information Rights Management" entry in the [Messaging policy and compliance permissions](/Exchange/permissions/feature-permissions/policy-and-compliance-permissions) topic.</span></span> 

- <span data-ttu-id="785a5-114">De AD RMS-server moet worden uitgevoerd Windows Server 2008 of hoger.</span><span class="sxs-lookup"><span data-stu-id="785a5-114">The AD RMS server must be running Windows Server 2008 or later.</span></span> <span data-ttu-id="785a5-115">Zie Een [AD RMS-cluster installeren](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc726041(v=ws.11))voor meer informatie over het implementeren van AD RMS.</span><span class="sxs-lookup"><span data-stu-id="785a5-115">For details about how to deploy AD RMS, see [Installing an AD RMS Cluster](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc726041(v=ws.11)).</span></span>

- <span data-ttu-id="785a5-116">Zie Voor meer informatie over het installeren en configureren Windows PowerShell en verbinding maken met de service, Verbinding maken om Exchange Online [Remote PowerShell te gebruiken.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="785a5-116">For details about how to install and configure Windows PowerShell and connect to the service, see [Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="785a5-117">Zie Sneltoetsen voor het Exchange beheercentrum in Exchange Online voor informatie over sneltoetsen die van toepassing kunnen zijn op de procedures [in dit onderwerp.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="785a5-117">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="785a5-118">Hebt u problemen?</span><span class="sxs-lookup"><span data-stu-id="785a5-118">Having problems?</span></span> <span data-ttu-id="785a5-119">Vraag om hulp in de Exchange forums.</span><span class="sxs-lookup"><span data-stu-id="785a5-119">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="785a5-120">Ga naar de forums [op Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)of [Exchange Online Protection.](https://go.microsoft.com/fwlink/p/?linkId=285351)</span><span class="sxs-lookup"><span data-stu-id="785a5-120">Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="how-do-you-do-this"></a><span data-ttu-id="785a5-121">Hoe doet u dit?</span><span class="sxs-lookup"><span data-stu-id="785a5-121">How do you do this?</span></span>
<span data-ttu-id="785a5-122"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="785a5-122"><a name="sectionSection1"> </a></span></span>

### <a name="step-1-use-the-ad-rms-console-to-export-a-trusted-publishing-domain-tpd-from-an-ad-rms-server"></a><span data-ttu-id="785a5-123">Stap 1: De AD RMS-console gebruiken om een vertrouwde publicatiedomein (TPD) te exporteren vanaf een AD RMS-server</span><span class="sxs-lookup"><span data-stu-id="785a5-123">Step 1: Use the AD RMS console to export a trusted publishing domain (TPD) from an AD RMS server</span></span>

<span data-ttu-id="785a5-124">De eerste stap is het exporteren van een vertrouwd publicatiedomein (TPD) van de on-premises AD RMS-server naar een XML-bestand.</span><span class="sxs-lookup"><span data-stu-id="785a5-124">The first step is to export a trusted publishing domain (TPD) from the on-premises AD RMS server to an XML file.</span></span> <span data-ttu-id="785a5-125">De TPD bevat de volgende instellingen die nodig zijn voor het gebruik van RMS-functies:</span><span class="sxs-lookup"><span data-stu-id="785a5-125">The TPD contains the following settings needed to use RMS features:</span></span>
  
- <span data-ttu-id="785a5-126">Het serverlicentiecertificaat (SLC) dat wordt gebruikt voor het ondertekenen en versleutelen van certificaten en licenties</span><span class="sxs-lookup"><span data-stu-id="785a5-126">The server licensor certificate (SLC) used for signing and encrypting certificates and licenses</span></span>

- <span data-ttu-id="785a5-127">De URL's die worden gebruikt voor licenties en publiceren</span><span class="sxs-lookup"><span data-stu-id="785a5-127">The URLs used for licensing and publishing</span></span>

- <span data-ttu-id="785a5-128">De AD RMS-sjablonen voor rechtenbeleid die zijn gemaakt met de specifieke SLC voor die TPD</span><span class="sxs-lookup"><span data-stu-id="785a5-128">The AD RMS rights policy templates that were created with the specific SLC for that TPD</span></span>

<span data-ttu-id="785a5-129">Wanneer u de TPD importeert, wordt deze opgeslagen en beveiligd in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="785a5-129">When you import the TPD, it's stored and protected in Exchange Online.</span></span>
  
1. <span data-ttu-id="785a5-130">Open de Active Directory Rights Management Services console en vouw het AD RMS-cluster uit.</span><span class="sxs-lookup"><span data-stu-id="785a5-130">Open the Active Directory Rights Management Services console, and then expand the AD RMS cluster.</span></span>

2. <span data-ttu-id="785a5-131">Vouw in de consolestructuur Het **vertrouwensbeleid uit** en klik vervolgens **op Vertrouwde publicatiedomeinen.**</span><span class="sxs-lookup"><span data-stu-id="785a5-131">In the console tree, expand **Trust Policies**, and then click **Trusted Publishing Domains**.</span></span>

3. <span data-ttu-id="785a5-132">Selecteer in het deelvenster Resultaten het certificaat voor het domein dat u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="785a5-132">In the results pane, select the certificate for the domain you want to export.</span></span>

4. <span data-ttu-id="785a5-133">Klik in **het deelvenster** Acties op **Vertrouwde publicatiedomein exporteren.**</span><span class="sxs-lookup"><span data-stu-id="785a5-133">In the **Actions** pane, click **Export Trusted Publishing Domain**.</span></span>

5. <span data-ttu-id="785a5-134">Klik in **het vak Publicatiedomeinbestand** op **Opslaan als** om het bestand op te slaan op een specifieke locatie op de lokale computer.</span><span class="sxs-lookup"><span data-stu-id="785a5-134">In the **Publishing domain file** box, click **Save As** to save the file to a specific location on the local computer.</span></span> <span data-ttu-id="785a5-135">Typ een bestandsnaam, geef de bestandsnaamextensie op `.xml` en klik op **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="785a5-135">Type a file name, making sure to specify the  `.xml` file name extension, and then click **Save**.</span></span>

6. <span data-ttu-id="785a5-136">Typ in **de** vakken **Wachtwoord** en Wachtwoord bevestigen een sterk wachtwoord dat wordt gebruikt om het vertrouwde publicatiedomeinbestand te versleutelen.</span><span class="sxs-lookup"><span data-stu-id="785a5-136">In the **Password** and **Confirm Password** boxes, type a strong password that will be used to encrypt the trusted publishing domain file.</span></span> <span data-ttu-id="785a5-137">U moet dit wachtwoord opgeven wanneer u de TPD importeert in uw e-mailorganisatie in de cloud.</span><span class="sxs-lookup"><span data-stu-id="785a5-137">You will have to specify this password when you import the TPD to your cloud-based email organization.</span></span> 

### <a name="step-2-use-the-exchange-management-shell-to-import-the-tpd-to-exchange-online"></a><span data-ttu-id="785a5-138">Stap 2: Gebruik de Exchange Management Shell om de TPD te importeren in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="785a5-138">Step 2: Use the Exchange Management Shell to import the TPD to Exchange Online</span></span>

<span data-ttu-id="785a5-139">Nadat de TPD is geëxporteerd naar een XML-bestand, moet u het importeren in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="785a5-139">After the TPD is exported to an XML file, you have to import it to Exchange Online.</span></span> <span data-ttu-id="785a5-140">Wanneer een TPD wordt geïmporteerd, worden de AD RMS-sjablonen van uw organisatie ook geïmporteerd.</span><span class="sxs-lookup"><span data-stu-id="785a5-140">When a TPD is imported, your organization's AD RMS templates are also imported.</span></span> <span data-ttu-id="785a5-141">Wanneer de eerste TPD wordt geïmporteerd, wordt deze de standaard TPD voor uw cloudorganisatie.</span><span class="sxs-lookup"><span data-stu-id="785a5-141">When the first TPD is imported, it becomes the default TPD for your cloud-based organization.</span></span> <span data-ttu-id="785a5-142">Als u een andere TPD  importeert, kunt u de standaardschakelknop gebruiken om deze de standaard TPD te maken die beschikbaar is voor gebruikers.</span><span class="sxs-lookup"><span data-stu-id="785a5-142">If you import another TPD, you can use the **Default** switch to make it the default TPD that is available to users.</span></span> 
  
<span data-ttu-id="785a5-143">Als u de TPD wilt importeren, moet u de volgende opdracht uitvoeren in Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="785a5-143">To import the TPD, run the following command in Windows PowerShell:</span></span>
  
```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path <path to exported TPD file> -ReadCount 0)) -Name "<name of TPD>" -ExtranetLicensingUrl <URL> -IntranetLicensingUrl <URL>
```

<span data-ttu-id="785a5-144">U kunt de waarden voor de _parameters ExtranetLicensingUrl_ en _IntranetLicensingUrl_ in de Active Directory Rights Management Services verkrijgen.</span><span class="sxs-lookup"><span data-stu-id="785a5-144">You can obtain the values for the  _ExtranetLicensingUrl_ and  _IntranetLicensingUrl_ parameters in the Active Directory Rights Management Services console.</span></span> <span data-ttu-id="785a5-145">Selecteer het AD RMS-cluster in de consolestructuur.</span><span class="sxs-lookup"><span data-stu-id="785a5-145">Select the AD RMS cluster in the console tree.</span></span> <span data-ttu-id="785a5-146">De licentie-URL's worden weergegeven in het resultatenvenster.</span><span class="sxs-lookup"><span data-stu-id="785a5-146">The licensing URLs are displayed in the results pane.</span></span> <span data-ttu-id="785a5-147">Deze URL's worden gebruikt door e-mail clients wanneer inhoud moet worden ontsleuteld en wanneer Exchange Online moet bepalen welke TPD moet worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="785a5-147">These URLs are used by email clients when content has to be decrypted and when Exchange Online needs to determine which TPD to use.</span></span>
  
<span data-ttu-id="785a5-148">Wanneer u deze opdracht uit te voeren, wordt u gevraagd om een wachtwoord.</span><span class="sxs-lookup"><span data-stu-id="785a5-148">When you run this command, you'll be prompted for a password.</span></span> <span data-ttu-id="785a5-149">Voer het wachtwoord in dat u hebt opgegeven toen u de TPD exporteerde vanaf uw AD RMS-server.</span><span class="sxs-lookup"><span data-stu-id="785a5-149">Enter the password that you specified when you exported the TPD from your AD RMS server.</span></span>
  
<span data-ttu-id="785a5-150">Met de volgende opdracht wordt bijvoorbeeld de TPD met de naam Geëxporteerde TPD geïmporteerd met het XML-bestand dat u hebt geëxporteerd vanaf uw AD RMS-server en opgeslagen op het bureaublad van het Administrator-account.</span><span class="sxs-lookup"><span data-stu-id="785a5-150">For example, the following command imports the TPD named Exported TPD using the XML file that you exported from your AD RMS server and saved to the desktop of the Administrator account.</span></span> <span data-ttu-id="785a5-151">De parameter Naam wordt gebruikt om een naam op te geven voor de TPD.</span><span class="sxs-lookup"><span data-stu-id="785a5-151">The Name parameter is used to specify a name to the TPD.</span></span>
  
```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path C:\Users\Administrator\Desktop\ExportTPD.xml -ReadCount 0)) -Name "Exported TPD" -ExtranetLicensingUrl https://corp.contoso.com/_wmcs/licensing -IntranetLicensingUrl https://rmsserver/_wmcs/licensing
```

<span data-ttu-id="785a5-152">Zie [Import-RMSTrustedPublishingDomain (Importeren-RMSTrustedPublishingDomain)](/powershell/module/exchange/import-rmstrustedpublishingdomain)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="785a5-152">For detailed syntax and parameter information, see [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain).</span></span>
  
#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="785a5-153">Hoe weet u dat deze stap heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="785a5-153">How do you know this step worked?</span></span>

<span data-ttu-id="785a5-154">Als u wilt controleren of u de TPD hebt geïmporteerd, kunt u de **cmdlet Get-RMSTrustedPublishingDomain** uitvoeren om TPD's op te halen in uw Exchange Online organisatie.</span><span class="sxs-lookup"><span data-stu-id="785a5-154">To verify that you have successfully imported the TPD, run the **Get-RMSTrustedPublishingDomain** cmdlet to retrieve TPDs in your Exchange Online organization.</span></span> <span data-ttu-id="785a5-155">Zie de voorbeelden in [Get-RMSTrustedPublishingDomain](/powershell/module/exchange/get-rmstrustedpublishingdomain)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="785a5-155">For details, see the examples in [Get-RMSTrustedPublishingDomain](/powershell/module/exchange/get-rmstrustedpublishingdomain).</span></span>
  
### <a name="step-3-use-the-exchange-management-shell-to-distribute-an-ad-rms-rights-policy-template"></a><span data-ttu-id="785a5-156">Stap 3: Gebruik de Exchange Management Shell om een AD RMS-beleidssjabloon voor rechten te distribueren</span><span class="sxs-lookup"><span data-stu-id="785a5-156">Step 3: Use the Exchange Management Shell to distribute an AD RMS rights policy template</span></span>

<span data-ttu-id="785a5-157">Nadat u de TPD hebt geïmporteerd, moet u ervoor zorgen dat een AD RMS-beleidssjabloon voor rechten is verdeeld.</span><span class="sxs-lookup"><span data-stu-id="785a5-157">After you import the TPD, you must make sure an AD RMS rights policy template is distributed.</span></span> <span data-ttu-id="785a5-158">Een gedistribueerde sjabloon is zichtbaar Outlook op internet (voorheen bekend als Outlook Web App) gebruikers, die de sjablonen vervolgens kunnen toepassen op een e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="785a5-158">A distributed template is visible to Outlook on the web (formerly known as Outlook Web App) users, who can then apply the templates to an email message.</span></span>
  
<span data-ttu-id="785a5-159">Voer de volgende opdracht uit als u een lijst wilt retourneren met alle sjablonen in de standaard-TPD:</span><span class="sxs-lookup"><span data-stu-id="785a5-159">To return a list of all templates contained in the default TPD, run the following command:</span></span>
  
```powershell
Get-RMSTemplate -Type All | fl
```

<span data-ttu-id="785a5-160">Als de waarde van de parameter  _Type_  `Archived` is, is de sjabloon niet zichtbaar voor gebruikers.</span><span class="sxs-lookup"><span data-stu-id="785a5-160">If the value of the  _Type_ parameter is  `Archived`, the template isn't visible to users.</span></span> <span data-ttu-id="785a5-161">Alleen gedistribueerde sjablonen in de standaard-TPD zijn beschikbaar in Outlook op het web.</span><span class="sxs-lookup"><span data-stu-id="785a5-161">Only distributed templates in the default TPD are available in Outlook on the web.</span></span>
  
<span data-ttu-id="785a5-162">Voer de volgende opdracht uit om een sjabloon te distribueren:</span><span class="sxs-lookup"><span data-stu-id="785a5-162">To distribute a template, run the following command:</span></span>
  
```powershell
Set-RMSTemplate -Identity "<name of the template>" -Type Distributed
```

<span data-ttu-id="785a5-163">Met de volgende opdracht wordt bijvoorbeeld de sjabloon Bedrijfs vertrouwelijk geïmporteerd.</span><span class="sxs-lookup"><span data-stu-id="785a5-163">For example, the following command imports the Company Confidential template.</span></span>
  
```powershell
Set-RMSTemplate -Identity "Company Confidential" -Type Distributed
```

<span data-ttu-id="785a5-164">Zie [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate) en [Set-RMSTemplate](/powershell/module/exchange/set-rmstemplate)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="785a5-164">For detailed syntax and parameter information, see [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate) and [Set-RMSTemplate](/powershell/module/exchange/set-rmstemplate).</span></span>
  
<span data-ttu-id="785a5-165">**De sjabloon Niet doorsturen**</span><span class="sxs-lookup"><span data-stu-id="785a5-165">**The Do Not Forward template**</span></span>
  
<span data-ttu-id="785a5-166">Wanneer u de standaard-TPD uit uw on-premises organisatie importeert in Exchange Online, wordt een AD RMS-beleidssjabloon met de naam Niet doorsturen geïmporteerd. </span><span class="sxs-lookup"><span data-stu-id="785a5-166">When you import the default TPD from your on-premises organization into Exchange Online, one AD RMS rights policy template named **Do Not Forward** is imported.</span></span> <span data-ttu-id="785a5-167">Deze sjabloon wordt standaard gedistribueerd wanneer u de standaard-TPD importeert.</span><span class="sxs-lookup"><span data-stu-id="785a5-167">By default, this template is distributed when you import the default TPD.</span></span> <span data-ttu-id="785a5-168">U kunt de cmdlet **Set-RMSTemplate** niet gebruiken om de sjabloon Niet doorsturen **te** wijzigen.</span><span class="sxs-lookup"><span data-stu-id="785a5-168">You can't use the **Set-RMSTemplate** cmdlet to modify the **Do Not Forward** template.</span></span> 
  
<span data-ttu-id="785a5-169">Wanneer de **sjabloon Niet doorsturen** is toegepast op een bericht, kunnen alleen de geadresseerden die in het bericht zijn geadresseerd, het bericht lezen.</span><span class="sxs-lookup"><span data-stu-id="785a5-169">When the **Do Not Forward** template is applied to a message, only the recipients addressed in the message can read the message.</span></span> <span data-ttu-id="785a5-170">Bovendien kunnen geadresseerden het volgende niet doen:</span><span class="sxs-lookup"><span data-stu-id="785a5-170">Additionally, recipients can't do the following:</span></span>
  
- <span data-ttu-id="785a5-171">Het bericht doorsturen naar een andere persoon.</span><span class="sxs-lookup"><span data-stu-id="785a5-171">Forward the message to another person.</span></span>

- <span data-ttu-id="785a5-172">Inhoud uit het bericht kopiëren.</span><span class="sxs-lookup"><span data-stu-id="785a5-172">Copy content from the message.</span></span>

- <span data-ttu-id="785a5-173">Druk het bericht af.</span><span class="sxs-lookup"><span data-stu-id="785a5-173">Print the message.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="785a5-174">De **sjabloon Niet** doorsturen kan niet voorkomen dat gegevens in een bericht worden gekopieerd met schermopnameprogramma's, camera's of gebruikers die de gegevens handmatig transcriberen</span><span class="sxs-lookup"><span data-stu-id="785a5-174">The **Do Not Forward** template can't prevent information in a message from being copied with third-party screen capture programs, cameras, or users manually transcribing the information</span></span> 
  
<span data-ttu-id="785a5-175">U kunt extra AD RMS-sjablonen voor rechtenbeleid maken op de AD RMS-server in uw on-premises organisatie om te voldoen aan uw IRM-beveiligingsvereisten.</span><span class="sxs-lookup"><span data-stu-id="785a5-175">You can create additional AD RMS rights policy templates on the AD RMS server in your on-premises organization to meet your IRM protection requirements.</span></span> <span data-ttu-id="785a5-176">Als u aanvullende AD RMS-sjablonen voor rechtenbeleid maakt, moet u de TPD opnieuw exporteren van de on-premises AD RMS-server en de TPD vernieuwen in de cloud-e-mailorganisatie.</span><span class="sxs-lookup"><span data-stu-id="785a5-176">If you create additional AD RMS rights policy templates, you have to export the TPD from the on-premises AD RMS server again and refresh the TPD in the cloud-based email organization.</span></span>
  
#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="785a5-177">Hoe weet u dat deze stap heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="785a5-177">How do you know this step worked?</span></span>

<span data-ttu-id="785a5-178">Voer de **cmdlet Get-RMSTemplate** uit om de eigenschappen van de sjabloon te controleren om te controleren of u de sjabloon hebt gedistribueerd en of de beleidssjabloon VOOR AD RMS-rechten is gedistribueerd.</span><span class="sxs-lookup"><span data-stu-id="785a5-178">To verify that you have successfully distributed and AD RMS rights policy template, run the **Get-RMSTemplate** cmdlet to check the template's properties.</span></span> <span data-ttu-id="785a5-179">Zie de voorbeelden in [Get-RMSTemplate voor meer informatie.](/powershell/module/exchange/get-rmstemplate)</span><span class="sxs-lookup"><span data-stu-id="785a5-179">For details, see the examples in [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate).</span></span>
  
### <a name="step-4-use-the-exchange-management-shell-to-enable-irm"></a><span data-ttu-id="785a5-180">Stap 4: Gebruik de Exchange Management Shell om IRM in te stellen</span><span class="sxs-lookup"><span data-stu-id="785a5-180">Step 4: Use the Exchange Management Shell to enable IRM</span></span>

<span data-ttu-id="785a5-181">Nadat u de TPD hebt geïmporteerd en een AD RMS-beleidssjabloon voor rechten hebt verdeeld, kunt u de volgende opdracht uitvoeren om IRM in te stellen voor uw e-mailorganisatie in de cloud.</span><span class="sxs-lookup"><span data-stu-id="785a5-181">After you import the TPD and distribute an AD RMS rights policy template, run the following command to enable IRM for your cloud-based email organization.</span></span>
  
```powershell
Set-IRMConfiguration -InternalLicensingEnabled $true
```

<span data-ttu-id="785a5-182">Zie [Set-IRMConfiguration (Set-IRMConfiguration)](/powershell/module/exchange/set-irmconfiguration)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="785a5-182">For detailed syntax and parameter information, see [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration).</span></span>
  
#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="785a5-183">Hoe weet u dat deze stap heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="785a5-183">How do you know this step worked?</span></span>

<span data-ttu-id="785a5-184">Als u wilt controleren of IRM is ingeschakeld, moet u de [cmdlet Get-IRMConfiguration](/powershell/module/exchange/get-irmconfiguration) uitvoeren om de IRM-configuratie in de Exchange Online controleren.</span><span class="sxs-lookup"><span data-stu-id="785a5-184">To verify that you have successfully enabled IRM, run the [Get-IRMConfiguration](/powershell/module/exchange/get-irmconfiguration) cmdlet to check IRM configuration in the Exchange Online organization.</span></span>
  
## <a name="how-do-you-know-this-task-worked"></a><span data-ttu-id="785a5-185">Hoe weet u dat deze taak heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="785a5-185">How do you know this task worked?</span></span>
<span data-ttu-id="785a5-186"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="785a5-186"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="785a5-187">Ga als volgt te werk om te controleren of u de TPD hebt geïmporteerd en IRM hebt ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="785a5-187">To verify that you have successfully imported the TPD and enabled IRM, do the following:</span></span>
  
- <span data-ttu-id="785a5-188">Gebruik de **cmdlet Test-IRMConfiguration** om de IRM-functionaliteit te testen.</span><span class="sxs-lookup"><span data-stu-id="785a5-188">Use the **Test-IRMConfiguration** cmdlet to test IRM functionality.</span></span> <span data-ttu-id="785a5-189">Zie 'Voorbeeld 1' in [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="785a5-189">For details, see "Example 1" in [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration).</span></span>

- <span data-ttu-id="785a5-190">Stel een nieuw bericht op in Outlook op internet en IRM-beveiligen door de optie Machtigingen instellen te selecteren in het uitgebreide menu ( Pictogram Meer  ![ ](../media/ITPro-EAC-MoreOptionsIcon.gif) opties).</span><span class="sxs-lookup"><span data-stu-id="785a5-190">Compose a new message in Outlook on the web and IRM-protect it by selecting **Set permissions** option from the extended menu ( ![More Options Icon](../media/ITPro-EAC-MoreOptionsIcon.gif)).</span></span>