---
title: Office 365-berichtversleuteling beheren
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 5/8/2019
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Wanneer u klaar bent met het instellen van Office 365-berichtversleuteling (OME), leert u hoe u uw implementatie op verschillende manieren kunt aanpassen.
ms.openlocfilehash: a2b3dde44ea541deb41eeb9d55d5ed745fa6c719
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "52650982"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="c8637-103">Office 365-berichtversleuteling beheren</span><span class="sxs-lookup"><span data-stu-id="c8637-103">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="c8637-104">Wanneer u klaar bent met het instellen van Office 365-berichtversleuteling (OME), kunt u de configuratie van uw implementatie op verschillende manieren aanpassen.</span><span class="sxs-lookup"><span data-stu-id="c8637-104">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in several ways.</span></span> <span data-ttu-id="c8637-105">U kunt bijvoorbeeld configureren of u een een  keer pascodes wilt inschakelen, de knop Versleutelen wilt weergeven in Outlook op internet en meer.</span><span class="sxs-lookup"><span data-stu-id="c8637-105">For example, you can configure whether to enable one-time pass codes, display the **Encrypt** button in Outlook on the web, and more.</span></span> <span data-ttu-id="c8637-106">In de taken in dit artikel wordt beschreven hoe.</span><span class="sxs-lookup"><span data-stu-id="c8637-106">The tasks in this article describe how.</span></span>

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="c8637-107">Beheren of geadresseerden van Google, Yahoo en Microsoft-account deze accounts kunnen gebruiken om zich aan te melden bij de Office 365-berichtversleuteling portal</span><span class="sxs-lookup"><span data-stu-id="c8637-107">Manage whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="c8637-108">Wanneer u de nieuwe functies Office 365-berichtversleuteling, kunnen gebruikers in uw organisatie berichten verzenden naar geadresseerden buiten uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="c8637-108">When you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your organization.</span></span> <span data-ttu-id="c8637-109">Als de ontvanger een *sociale* id gebruikt, zoals een Google-account, Yahoo-account of Microsoft-account, kan de ontvanger zich aanmelden bij de OME-portal met een sociale id.</span><span class="sxs-lookup"><span data-stu-id="c8637-109">If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal with a social ID.</span></span> <span data-ttu-id="c8637-110">Als u wilt, kunt u ervoor kiezen om geadresseerden niet toe te staan zich aan te melden bij de OME-portal.</span><span class="sxs-lookup"><span data-stu-id="c8637-110">If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="c8637-111">Beheren of geadresseerden sociale IDs kunnen gebruiken om zich aan te melden bij de OME-portal</span><span class="sxs-lookup"><span data-stu-id="c8637-111">To manage whether recipients can use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="c8637-112">[Verbinding maken om Exchange Online Externe PowerShell te gebruiken.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="c8637-112">[Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="c8637-113">Voer de Set-OMEConfiguration cmdlet uit met de parameter SocialIdSignIn als volgt:</span><span class="sxs-lookup"><span data-stu-id="c8637-113">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   <span data-ttu-id="c8637-114">Als u bijvoorbeeld sociale-1D's wilt uitschakelen:</span><span class="sxs-lookup"><span data-stu-id="c8637-114">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="c8637-115">Ga als volgende te werk om sociale--eds in te stellen:</span><span class="sxs-lookup"><span data-stu-id="c8637-115">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a><span data-ttu-id="c8637-116">Het gebruik van een een tijdspascodes voor de Office 365-berichtversleuteling beheren</span><span class="sxs-lookup"><span data-stu-id="c8637-116">Manage the use of one-time pass codes for the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="c8637-117">Als de geadresseerde van een bericht dat door OME is versleuteld, geen Outlook gebruikt, ongeacht het account dat door de geadresseerde wordt gebruikt, ontvangt de geadresseerde een koppeling voor een beperkte webweergave waarmee hij of zij het bericht kan lezen.</span><span class="sxs-lookup"><span data-stu-id="c8637-117">If the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message.</span></span> <span data-ttu-id="c8637-118">Deze koppeling bevat een een time pass-code.</span><span class="sxs-lookup"><span data-stu-id="c8637-118">This link includes a one-time pass code.</span></span> <span data-ttu-id="c8637-119">Als beheerder kunt u bepalen of geadresseerden een eentijdspascodes kunnen gebruiken om zich aan te melden bij de OME-portal.</span><span class="sxs-lookup"><span data-stu-id="c8637-119">As an administrator, you can decide if recipients can use one-time pass codes to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a><span data-ttu-id="c8637-120">Beheren of OME een eentijdspascodes genereert</span><span class="sxs-lookup"><span data-stu-id="c8637-120">To manage whether OME generates one-time pass codes</span></span>
  
1. <span data-ttu-id="c8637-121">Gebruik een werk- of schoolaccount met globale beheerdersmachtigingen in uw organisatie en start een Windows PowerShell en maak verbinding met Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c8637-121">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="c8637-122">Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="c8637-122">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="c8637-123">Voer de Set-OMEConfiguration cmdlet uit met de OTPEnabled-parameter:</span><span class="sxs-lookup"><span data-stu-id="c8637-123">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="c8637-124">Als u bijvoorbeeld een een-time passcodes wilt uitschakelen:</span><span class="sxs-lookup"><span data-stu-id="c8637-124">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="c8637-125">Een een time pass codes inschakelen:</span><span class="sxs-lookup"><span data-stu-id="c8637-125">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a><span data-ttu-id="c8637-126">De weergave van de knop Versleutelen beheren in Outlook web</span><span class="sxs-lookup"><span data-stu-id="c8637-126">Manage the display of the Encrypt button in Outlook on the web</span></span>

<span data-ttu-id="c8637-127">Als beheerder kunt u beheren of u deze knop wilt weergeven voor eindgebruikers.</span><span class="sxs-lookup"><span data-stu-id="c8637-127">As an administrator, you can manage whether to display this button to end users.</span></span>
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="c8637-128">Beheren of de knop Versleutelen wordt weergegeven in Outlook web</span><span class="sxs-lookup"><span data-stu-id="c8637-128">To manage whether the Encrypt button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="c8637-129">Gebruik een werk- of schoolaccount met globale beheerdersmachtigingen in uw organisatie en start een Windows PowerShell en maak verbinding met Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c8637-129">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="c8637-130">Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="c8637-130">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="c8637-131">Voer de Set-IRMConfiguration cmdlet uit met de parameter -SimplifiedClientAccessEnabled:</span><span class="sxs-lookup"><span data-stu-id="c8637-131">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="c8637-132">Als u bijvoorbeeld de knop **Versleutelen wilt** uitschakelen:</span><span class="sxs-lookup"><span data-stu-id="c8637-132">For example, to disable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="c8637-133">De knop **Versleutelen inschakelen:**</span><span class="sxs-lookup"><span data-stu-id="c8637-133">To enable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="c8637-134">Ontsleuteling van e-mailberichten aan de servicezijde inschakelen voor gebruikers van de iOS-e-mailapp</span><span class="sxs-lookup"><span data-stu-id="c8637-134">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="c8637-135">De iOS-e-mailapp kan geen berichten ontsleutelen die zijn beveiligd met Office 365-berichtversleuteling.</span><span class="sxs-lookup"><span data-stu-id="c8637-135">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption.</span></span> <span data-ttu-id="c8637-136">Als beheerder Microsoft 365 kunt u ontsleuteling aan de servicezijde toepassen voor berichten die worden bezorgd in de e-mailapp van iOS.</span><span class="sxs-lookup"><span data-stu-id="c8637-136">As a Microsoft 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app.</span></span> <span data-ttu-id="c8637-137">Wanneer u ervoor kiest om de ontsleuteling aan de servicezijde te gebruiken, stuurt de service een ontsleutelde kopie van het bericht naar het iOS-apparaat.</span><span class="sxs-lookup"><span data-stu-id="c8637-137">When you choose to do use service-side decryption, the service sends a decrypted copy of the message to the iOS device.</span></span> <span data-ttu-id="c8637-138">Het clientapparaat slaat een ontsleutelde kopie van het bericht op.</span><span class="sxs-lookup"><span data-stu-id="c8637-138">The client device stores a decrypted copy of the message.</span></span> <span data-ttu-id="c8637-139">Het bericht behoudt ook informatie over gebruiksrechten, ook al past de e-mail-app voor iOS geen gebruiksrechten aan de client toe op de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="c8637-139">The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="c8637-140">De gebruiker kan het bericht kopiëren of afdrukken, zelfs als hij of zij niet de oorspronkelijke rechten heeft om dit te doen.</span><span class="sxs-lookup"><span data-stu-id="c8637-140">The user can copy or print the message even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="c8637-141">Als de gebruiker echter een actie probeert uit te voeren die vereist is voor de e-mailserver van Microsoft 365, zoals het doorsturen van het bericht, staat de server de actie niet toe als de gebruiker oorspronkelijk niet het gebruiksrecht had om dit te doen.</span><span class="sxs-lookup"><span data-stu-id="c8637-141">However, if the user attempts to complete an action that requires the Microsoft 365 mail server, such as forwarding the message, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span> <span data-ttu-id="c8637-142">Eindgebruikers kunnen echter de gebruiksbeperking 'Niet doorsturen' gebruiken door het bericht door te sturen vanuit een ander account in de e-mail-app van iOS.</span><span class="sxs-lookup"><span data-stu-id="c8637-142">However, end users can work around "Do Not Forward" usage restriction by forwarding the message from a different account within the iOS mail app.</span></span> <span data-ttu-id="c8637-143">Ongeacht of u de ontsleuteling van e-mail aan de servicezijde hebt ingesteld, bijlagen voor versleutelde en rechten beveiligde e-mail kunnen niet worden bekeken in de e-mailapp van iOS.</span><span class="sxs-lookup"><span data-stu-id="c8637-143">Regardless of whether you set up service-side decryption of mail, attachments to encrypted and rights protected mail can't be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="c8637-144">Als u ervoor kiest om niet toe te staan dat ontsleutelde berichten worden verzonden naar gebruikers van de e-mailapp van iOS, ontvangen gebruikers een bericht waarin staat dat ze niet de rechten hebben om het bericht te bekijken.</span><span class="sxs-lookup"><span data-stu-id="c8637-144">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message.</span></span> <span data-ttu-id="c8637-145">Standaard is het ontsleutelen van e-mailberichten aan de servicezijde niet ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="c8637-145">By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="c8637-146">Zie Versleutelde berichten weergeven op uw iPhone of iPad voor meer informatie en voor een weergave van de [clientervaring.](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)</span><span class="sxs-lookup"><span data-stu-id="c8637-146">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="c8637-147">Beheren of gebruikers van de iOS-e-mailapp berichten kunnen bekijken die zijn beveiligd met Office 365-berichtversleuteling</span><span class="sxs-lookup"><span data-stu-id="c8637-147">To manage whether iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="c8637-148">Gebruik een werk- of schoolaccount met globale beheerdersmachtigingen in uw organisatie en start een Windows PowerShell en maak verbinding met Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c8637-148">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="c8637-149">Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="c8637-149">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="c8637-150">Voer de Set-ActiveSyncOrganizations cmdlet uit met de parameter AllowRMSSupportForUnenlightenedApps:</span><span class="sxs-lookup"><span data-stu-id="c8637-150">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="c8637-151">Als u de service bijvoorbeeld zo wilt configureren dat berichten worden ontsleuteld voordat ze worden verzonden naar niet-gelichte apps, zoals de e-mail-app voor iOS:</span><span class="sxs-lookup"><span data-stu-id="c8637-151">For example, to configure the service to decrypt messages before they're sent to unenlightened apps like the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="c8637-152">Of als u de service zo wilt configureren dat er geen ontsleutelde berichten worden verzonden naar niet-gelichte apps:</span><span class="sxs-lookup"><span data-stu-id="c8637-152">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> <span data-ttu-id="c8637-153">Afzonderlijke postvakbeleidsregels (OWA/ActiveSync) overschrijven deze instellingen (dat wil zeggen als -IRMEnabled is ingesteld op Onwaar binnen het betreffende OWA-postvakbeleid of ActiveSync-postvakbeleid, dan zijn deze configuraties niet van toepassing).</span><span class="sxs-lookup"><span data-stu-id="c8637-153">Individual mailbox policies (OWA/ActiveSync) override these settings (i.e. if -IRMEnabled is set to False within the respective OWA Mailbox policy, or ActiveSync Mailbox policy, then these configurations would not apply).</span></span>

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="c8637-154">Ontsleuteling van e-mailbijlagen aan de servicezijde inschakelen voor e-mail clients in webbrowser</span><span class="sxs-lookup"><span data-stu-id="c8637-154">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="c8637-155">Normaal gesproken worden bijlagen automatisch versleuteld wanneer Office 365 berichtversleuteling gebruikt.</span><span class="sxs-lookup"><span data-stu-id="c8637-155">Normally, when you use Office 365 message encryption, attachments are automatically encrypted.</span></span> <span data-ttu-id="c8637-156">Als beheerder kunt u ontsleuteling aan de service toepassen voor e-mailbijlagen die gebruikers downloaden vanuit een webbrowser.</span><span class="sxs-lookup"><span data-stu-id="c8637-156">As an administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="c8637-157">Wanneer u de ontsleuteling aan de servicezijde gebruikt, verzendt de service een ontsleutelde kopie van het bestand naar het apparaat.</span><span class="sxs-lookup"><span data-stu-id="c8637-157">When you use service-side decryption, the service sends a decrypted copy of the file to the device.</span></span> <span data-ttu-id="c8637-158">Het bericht is nog steeds versleuteld.</span><span class="sxs-lookup"><span data-stu-id="c8637-158">The message is still encrypted.</span></span> <span data-ttu-id="c8637-159">De e-mailbijlage bewaart ook informatie over gebruiksrechten, ook al wordt in de browser geen gebruiksrechten aan de client op de gebruiker toegepast.</span><span class="sxs-lookup"><span data-stu-id="c8637-159">The email attachment also keeps information about usage rights even though the browser doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="c8637-160">De gebruiker kan de e-mailbijlage kopiëren of afdrukken, zelfs als hij of zij niet de oorspronkelijke rechten heeft om dit te doen.</span><span class="sxs-lookup"><span data-stu-id="c8637-160">The user can copy or print the email attachment even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="c8637-161">Als de gebruiker echter een actie probeert uit te voeren die vereist is voor de e-mailserver van Microsoft 365, zoals het doorsturen van de bijlage, staat de server de actie niet toe als de gebruiker oorspronkelijk niet het gebruiksrecht had om dit te doen.</span><span class="sxs-lookup"><span data-stu-id="c8637-161">However, if the user tries to complete an action that requires the Microsoft 365 mail server, such as forwarding the attachment, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span>
  
<span data-ttu-id="c8637-162">Ongeacht of u het ontsleutelen van bijlagen aan de servicezijde hebt ingesteld, gebruikers kunnen geen bijlagen weergeven voor versleutelde en rechten beveiligde e-mail in de e-mail-app voor iOS.</span><span class="sxs-lookup"><span data-stu-id="c8637-162">Regardless of whether you set up service-side decryption of attachments, users can't view any attachments to encrypted and rights protected mail in the iOS mail app.</span></span>
  
<span data-ttu-id="c8637-163">Als u ervoor kiest om ontsleutelde e-mailbijlagen niet toe te staan, wat de standaardinstelling is, ontvangen gebruikers een bericht waarin staat dat ze niet de rechten hebben om de bijlage te bekijken.</span><span class="sxs-lookup"><span data-stu-id="c8637-163">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="c8637-164">Zie Versleutelen-alleen-optie voor e-mailberichten voor meer Microsoft 365 voor e-mails en e-mailbijlagen met de optie Encrypt-Only [e-mail.](/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="c8637-164">For more information about how Microsoft 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="c8637-165">Beheren of e-mailbijlagen worden ontsleuteld bij downloaden vanuit een webbrowser</span><span class="sxs-lookup"><span data-stu-id="c8637-165">To manage whether email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="c8637-166">Gebruik een werk- of schoolaccount met globale beheerdersmachtigingen in uw organisatie en start een Windows PowerShell en maak verbinding met Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c8637-166">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="c8637-167">Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="c8637-167">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="c8637-168">Voer de Set-IRMConfiguration cmdlet uit met de parameter DecryptAttachmentForEncryptOnly:</span><span class="sxs-lookup"><span data-stu-id="c8637-168">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentForEncryptOnly parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   <span data-ttu-id="c8637-169">Als u bijvoorbeeld de service wilt configureren voor het ontsleutelen van e-mailbijlagen wanneer een gebruiker deze downloadt vanuit een webbrowser:</span><span class="sxs-lookup"><span data-stu-id="c8637-169">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   <span data-ttu-id="c8637-170">U kunt de service zo configureren dat versleutelde e-mailbijlagen worden verlaten zoals ze zijn bij het downloaden:</span><span class="sxs-lookup"><span data-stu-id="c8637-170">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a><span data-ttu-id="c8637-171">Controleer of alle externe geadresseerden de OME Portal gebruiken om versleutelde e-mail te lezen</span><span class="sxs-lookup"><span data-stu-id="c8637-171">Ensure all external recipients use the OME Portal to read encrypted mail</span></span>

<span data-ttu-id="c8637-172">U kunt aangepaste huisstijlsjablonen gebruiken om geadresseerden te dwingen een wrapper-e-mail te ontvangen, zodat ze versleutelde e-mail moeten lezen in de OME Portal in plaats van Outlook of Outlook op het web.</span><span class="sxs-lookup"><span data-stu-id="c8637-172">You can use custom branding templates to force recipients to receive a wrapper mail that directs them to read encrypted email in the OME Portal instead of using Outlook or Outlook on the web.</span></span> <span data-ttu-id="c8637-173">U kunt dit doen als u meer controle wilt over de manier waarop geadresseerden de e-mail gebruiken die ze ontvangen.</span><span class="sxs-lookup"><span data-stu-id="c8637-173">You might want to do this if you use want greater control over how recipients use the mail they receive.</span></span> <span data-ttu-id="c8637-174">Als externe geadresseerden bijvoorbeeld e-mail weergeven in de webportal, kunt u een vervaldatum instellen voor de e-mail en kunt u de e-mail intrekken.</span><span class="sxs-lookup"><span data-stu-id="c8637-174">For example, if external recipients view email in the web portal, you can set an expiration date for the email, and you can revoke the email.</span></span> <span data-ttu-id="c8637-175">Deze functies worden alleen ondersteund via de OME Portal.</span><span class="sxs-lookup"><span data-stu-id="c8637-175">These features are only supported through the OME Portal.</span></span> <span data-ttu-id="c8637-176">U kunt de optie Versleutelen en de optie Niet doorsturen gebruiken bij het maken van de regels voor de e-mailstroom.</span><span class="sxs-lookup"><span data-stu-id="c8637-176">You can use the Encrypt option and the Do Not Forward option when creating the mail flow rules.</span></span>

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a><span data-ttu-id="c8637-177">Een aangepaste sjabloon gebruiken om alle externe geadresseerden te dwingen de OME-portal te gebruiken en voor versleutelde e-mail</span><span class="sxs-lookup"><span data-stu-id="c8637-177">Use a custom template to force all external recipients to use the OME Portal and for encrypted email</span></span>

1. <span data-ttu-id="c8637-178">Gebruik een werk- of schoolaccount met globale beheerdersmachtigingen in uw organisatie en start een Windows PowerShell en maak verbinding met Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c8637-178">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="c8637-179">Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="c8637-179">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="c8637-180">Voer de New-TransportRule cmdlet uit:</span><span class="sxs-lookup"><span data-stu-id="c8637-180">Run the New-TransportRule cmdlet:</span></span>

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    <span data-ttu-id="c8637-181">waarbij:</span><span class="sxs-lookup"><span data-stu-id="c8637-181">where:</span></span>

   - <span data-ttu-id="c8637-182">`mail flow rule name` is de naam die u wilt gebruiken voor de nieuwe regel voor de e-mailstroom.</span><span class="sxs-lookup"><span data-stu-id="c8637-182">`mail flow rule name` is the name you want to use for the new mail flow rule.</span></span>

   - <span data-ttu-id="c8637-183">`option name` is of `Encrypt` `Do Not Forward` .</span><span class="sxs-lookup"><span data-stu-id="c8637-183">`option name` is either `Encrypt` or `Do Not Forward`.</span></span>

   - <span data-ttu-id="c8637-184">`template name` is bijvoorbeeld de naam die u de aangepaste huisstijlsjabloon hebt `OME Configuration` gegeven.</span><span class="sxs-lookup"><span data-stu-id="c8637-184">`template name` is the name you gave the custom branding template, for example `OME Configuration`.</span></span>

   <span data-ttu-id="c8637-185">Alle externe e-mail versleutelen met de sjabloon 'OME-configuratie' en de optie Encrypt-Only toepassen:</span><span class="sxs-lookup"><span data-stu-id="c8637-185">To encrypt all external email with the "OME Configuration" template and apply the Encrypt-Only option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   <span data-ttu-id="c8637-186">Alle externe e-mail versleutelen met de sjabloon OME-configuratie en de optie Niet doorsturen toepassen:</span><span class="sxs-lookup"><span data-stu-id="c8637-186">To encrypt all external email with the "OME Configuration" template and apply the Do Not Forward option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="c8637-187">Het uiterlijk van e-mailberichten en de OME-portal aanpassen</span><span class="sxs-lookup"><span data-stu-id="c8637-187">Customize the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="c8637-188">Zie Het merk van uw organisatie toevoegen aan uw versleutelde berichten voor meer informatie over hoe u OME voor uw organisatie [kunt aanpassen.](add-your-organization-brand-to-encrypted-messages.md)</span><span class="sxs-lookup"><span data-stu-id="c8637-188">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disable-the-new-capabilities-for-ome"></a><span data-ttu-id="c8637-189">De nieuwe mogelijkheden voor OME uitschakelen</span><span class="sxs-lookup"><span data-stu-id="c8637-189">Disable the new capabilities for OME</span></span>

<span data-ttu-id="c8637-190">We hopen dat het er niet bij komt, maar als het nodig is, is het uitschakelen van de nieuwe mogelijkheden voor OME heel eenvoudig.</span><span class="sxs-lookup"><span data-stu-id="c8637-190">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward.</span></span> <span data-ttu-id="c8637-191">Eerst moet u alle e-mailstroomregels verwijderen die u hebt gemaakt met de nieuwe OME-mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="c8637-191">First, you'll need to remove any mail flow rules you've created that use the new OME capabilities.</span></span> <span data-ttu-id="c8637-192">Zie Regels voor e-mailstroom beheren voor informatie over het verwijderen van regels voor [e-mailstroom.](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="c8637-192">For information about removing mail flow rules, see [Manage mail flow rules](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).</span></span> <span data-ttu-id="c8637-193">Voltooi vervolgens deze stappen in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c8637-193">Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="c8637-194">De nieuwe mogelijkheden voor OME uitschakelen</span><span class="sxs-lookup"><span data-stu-id="c8637-194">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="c8637-195">Als u een werk- of schoolaccount gebruikt met globale beheerdersmachtigingen in uw organisatie, start u een Windows PowerShell en maakt u verbinding met Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c8637-195">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="c8637-196">Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="c8637-196">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="c8637-197">Als u de  knop Versleutelen hebt ingeschakeld in Outlook web, schakelt u deze uit door de Set-IRMConfiguration-cmdlet met de parameter SimplifiedClientAccessEnabled uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="c8637-197">If you enabled the **Encrypt** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter.</span></span> <span data-ttu-id="c8637-198">Anders slaat u deze stap over.</span><span class="sxs-lookup"><span data-stu-id="c8637-198">Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="c8637-199">Schakel de nieuwe mogelijkheden voor OME uit door de Set-IRMConfiguration met de parameter AzureRMSLicensingEnabled uit te stellen op onwaar:</span><span class="sxs-lookup"><span data-stu-id="c8637-199">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
