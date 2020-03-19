---
title: Spammeldingen voor eindgebruikers configureren in Exchange Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
ms.collection:
- M365-security-compliance
description: U spammeldingen voor eindgebruikers configureren voor het standaard beleid voor spamfilters voor het hele bedrijf of voor aangepaste spamfilterbeleidsregels die worden toegepast op domeinen.
ms.openlocfilehash: c8690a64e222bca2bbdc6be62d1077a9d361ae85
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/29/2020
ms.locfileid: "42810223"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a><span data-ttu-id="43834-103">Spammeldingen voor eindgebruikers configureren in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="43834-103">Configure end-user spam notifications in Exchange Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="43834-104">Dit onderwerp is voor Exchange Online-klanten die postvakken die in de cloud worden gehost, beschermen.</span><span class="sxs-lookup"><span data-stu-id="43834-104">This topic is for Exchange Online customers who are protecting cloud-hosted mailboxes.</span></span> <span data-ttu-id="43834-105">Zelfstandige klanten van Exchange Online Protection (EOP) die on-premises postvakken beschermen, moeten in plaats daarvan het volgende onderwerp lezen: [Spammeldingen voor eindgebruikers configureren in EOP](configure-end-user-spam-notifications-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="43834-105">Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes should read the following topic instead: [Configure end-user spam notifications in EOP](configure-end-user-spam-notifications-in-eop.md).</span></span> 
  
<span data-ttu-id="43834-106">U spammeldingen voor eindgebruikers configureren voor het standaard beleid voor spamfilters voor het hele bedrijf of voor het aangepaste beleid voor spamfilters.</span><span class="sxs-lookup"><span data-stu-id="43834-106">You can configure end-user spam notifications for the default company-wide spam filter policy or for custom spam filter policies.</span></span> <span data-ttu-id="43834-107">Met spammeldingen van eindgebruikers kunnen uw gebruikers hun eigen in quarantaine geplaatste spam-, bulk- en phishingberichten beheren.</span><span class="sxs-lookup"><span data-stu-id="43834-107">Enabling end-user spam notification messages lets your users manage their own quarantined spam, bulk, and phishing messages.</span></span>   
  
<span data-ttu-id="43834-108">Spammeldingen van eindgebruikers bevatten een lijst met alle spam-quarantaine berichten die de eindgebruiker heeft ontvangen gedurende een periode die u configureert (u een waarde opgeven tussen 1 en 15 dagen).</span><span class="sxs-lookup"><span data-stu-id="43834-108">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days).</span></span> <span data-ttu-id="43834-109">U ook de taal configureren waarin het meldingsbericht is geschreven.</span><span class="sxs-lookup"><span data-stu-id="43834-109">You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="43834-110">Na ontvangst van een melding kunnen eindgebruikers kiezen uit de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="43834-110">After receiving a notification message, end users can choose from the following options:</span></span>

<span data-ttu-id="43834-111">**Afzender blokkeren** als u wilt dat Office 365 de afzender toevoegt aan de lijst met geblokkeerde afzenders.</span><span class="sxs-lookup"><span data-stu-id="43834-111">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

<span data-ttu-id="43834-112">**Laat u los** als het bericht geen spam is en u wilt dat Office 365 het bericht naar uw postvak verzendt.</span><span class="sxs-lookup"><span data-stu-id="43834-112">**Release** if the message isn't spam and you want Office 365 to send the message to your mailbox.</span></span>

<span data-ttu-id="43834-113">**Controleer of** u naar de quarantaineportal in het Beveiligingscentrum & wilt navigeren als u andere acties wilt uitvoeren, zoals Voorbeeld of Release.</span><span class="sxs-lookup"><span data-stu-id="43834-113">**Review** to navigate to the Quarantine Portal within the Security & Compliance Center if you want to take other actions, such as Preview or Release.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="43834-114">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="43834-114">What do you need to know before you begin?</span></span>

<span data-ttu-id="43834-115">Geschatte tijd om te voltooien: 2 minuten</span><span class="sxs-lookup"><span data-stu-id="43834-115">Estimated time to complete: 2 minutes</span></span>
  
<span data-ttu-id="43834-116">U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="43834-116">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="43834-117">Zie het item 'Antispam' in het onderwerp [Functiemachtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) om te zien welke machtigingen u nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="43834-117">To see what permissions you need, see the "Anti-spam" entry in the [Feature Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) topic.</span></span> 
  
<span data-ttu-id="43834-118">Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="43834-118">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="43834-119">De EAC gebruiken om spammeldingen van eindgebruikers te configureren</span><span class="sxs-lookup"><span data-stu-id="43834-119">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="43834-120">Navigeer in het Exchange-beheercentrum (EAC) naar het filter **Beveiligingspam** \> **Spam filter**.</span><span class="sxs-lookup"><span data-stu-id="43834-120">In the Exchange admin center (EAC), navigate to **Protection** \> **Spam filter**.</span></span>
    
2. <span data-ttu-id="43834-121">Selecteer het spamfilterbeleid waarvoor u spammeldingen van eindgebruikers wilt inschakelen (deze zijn standaard uitgeschakeld).</span><span class="sxs-lookup"><span data-stu-id="43834-121">Select the spam filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="43834-122">Klik in het rechterdeelvenster, waar de overzichtsgegevens over uw beleid worden weergegeven, op de koppeling **Spammeldingen voor eindgebruikers configureren.**</span><span class="sxs-lookup"><span data-stu-id="43834-122">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="43834-123">In het volgende dialoogvenster u de volgende opties configureren:</span><span class="sxs-lookup"><span data-stu-id="43834-123">In the subsequent dialog box, you can configure the following options:</span></span>
    
   - <span data-ttu-id="43834-124">**Spammeldingen van eindgebruikers inschakelen** Schakel dit selectievakje in om spammeldingen van eindgebruikers voor dit beleid in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="43834-124">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy.</span></span> <span data-ttu-id="43834-125">(Als dit beleid daarentegen is ingeschakeld, u dit selectievakje uitschakelen om spammeldingen van eindgebruikers voor dit beleid uit te schakelen.)</span><span class="sxs-lookup"><span data-stu-id="43834-125">(Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
   - <span data-ttu-id="43834-126">**Elke (dag) spammeldingen van eindgebruikers verzenden** Geef op hoe vaak spammeldingen van eindgebruikers moeten worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="43834-126">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications.</span></span> <span data-ttu-id="43834-127">De standaardinstelling is 3 dagen.</span><span class="sxs-lookup"><span data-stu-id="43834-127">The default is 3 days.</span></span> <span data-ttu-id="43834-128">U tussen 1 en 15 dagen opgeven.</span><span class="sxs-lookup"><span data-stu-id="43834-128">You can specify between 1 and 15 days.</span></span> <span data-ttu-id="43834-129">Als u bijvoorbeeld 7 dagen opgeeft, bevat de melding een lijst met alle berichten die in de afgelopen zeven dagen voor die gebruiker zijn bedoeld en die in plaats daarvan naar de spamquarantaine zijn verzonden.</span><span class="sxs-lookup"><span data-stu-id="43834-129">If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
   - <span data-ttu-id="43834-130">**Meldingstaal** Selecteer met de vervolgkeuzelijst de taal waarin u spammeldingen voor eindgebruikers voor dit beleid wilt schrijven.</span><span class="sxs-lookup"><span data-stu-id="43834-130">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
   - <span data-ttu-id="43834-131">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="43834-131">Click **Save**.</span></span> <span data-ttu-id="43834-132">In het rechterdeelvenster verschijnt een overzicht van de beleidsinstellingen voor spamfilters, inclusief de instellingen voor spammeldingen van eindgebruikers.</span><span class="sxs-lookup"><span data-stu-id="43834-132">A summary of your spam filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="43834-133">Spammeldingen van eindgebruikers zijn alleen functioneel voor het beleid voor spamfilters dat is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="43834-133">End-user spam notifications will only be functional for spam filter policies that are enabled.</span></span> <span data-ttu-id="43834-134">> Spammeldingen van eindgebruikers worden slechts één keer per dag verzonden.</span><span class="sxs-lookup"><span data-stu-id="43834-134">>  End-user spam notifications are only sent once per day.</span></span> <span data-ttu-id="43834-135">De levertijd van de melding kan niet worden gegarandeerd voor een specifieke klant en is niet configureerbaar.</span><span class="sxs-lookup"><span data-stu-id="43834-135">The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="43834-136">**Tip:** Als u spammeldingen van eindgebruikers wilt testen door ze naar een beperkte groep gebruikers te sturen voordat u ze volledig implementeert, maakt u een aangepast spamfilterbeleid waarmee spammeldingen van eindgebruikers worden ingesteld voor de domeinen waarin de gebruikers zich bevinden.</span><span class="sxs-lookup"><span data-stu-id="43834-136">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom spam filter policy that enables end-user spam notifications for the domains in which the users reside.</span></span> <span data-ttu-id="43834-137">Maak vervolgens in de EAC onder \*\*E-mailstroomregels \> \*\*een e-mailstroomregel (ook wel een transportregel genoemd) om berichten te blokkeren van quarantine@messaging.microsoft.com (het e-mailadres dat meldingen verzendt) met uitzonderingen voor de gebruikers die u de meldingen wilt ontvangen.</span><span class="sxs-lookup"><span data-stu-id="43834-137">Then, in the EAC, under **Mail flow \> rules**, create a mail flow rule (also known as a transport rule) to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications.</span></span> <span data-ttu-id="43834-138">De volgende afbeelding is een voorbeeld van het maken van een uitzondering voor twee gebruikers (SaraD en AlexD) van domein Contoso.com:</span><span class="sxs-lookup"><span data-stu-id="43834-138">The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![Transportregel om spammeldingen van eindgebruikers te testen](../../media/EOP-ESN-testspecificusers.jpg)
  
## <a name="use-the-scc-to-configure-end-user-spam-notifications"></a><span data-ttu-id="43834-140">De SCC gebruiken om spammeldingen van eindgebruikers te configureren</span><span class="sxs-lookup"><span data-stu-id="43834-140">Use the SCC to configure end-user spam notifications</span></span>

<span data-ttu-id="43834-141">U ook het Beveiligings- en Compliancecenter (SCC) gebruiken om spammeldingen van eindgebruikers te configureren.</span><span class="sxs-lookup"><span data-stu-id="43834-141">You can also use the Security and Compliance Center (SCC) to configure end-user spam notifications.</span></span> <span data-ttu-id="43834-142">Voer de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="43834-142">Follow these steps:</span></span>

1. <span data-ttu-id="43834-143">Open het Beveiligings- en Compliancecenter, navigeer naar **Threat** \> Management https://protection.office.com/antispam **Policy** \> **Anti-spam** of gebruik de directe link.</span><span class="sxs-lookup"><span data-stu-id="43834-143">Open the Security and Compliance Center, navigate to **Threat management** \> **Policy** \> **Anti-spam** or use the direct link https://protection.office.com/antispam.</span></span>

2. <span data-ttu-id="43834-144">Klik op de pijl-omlaag naast het spamfilterbeleid waarvoor u spammeldingen van eindgebruikers wilt inschakelen.</span><span class="sxs-lookup"><span data-stu-id="43834-144">Click the down arrow next to the spam filter policy for which you want to enable end-user spam notifications.</span></span>

3. <span data-ttu-id="43834-145">Klik op de link **Spammeldingen voor eindgebruikers configureren.**</span><span class="sxs-lookup"><span data-stu-id="43834-145">Click on the **Configure End-user spam notifications** link.</span></span>

4. <span data-ttu-id="43834-146">In het volgende dialoogvenster u de volgende opties configureren:</span><span class="sxs-lookup"><span data-stu-id="43834-146">In the subsequent dialog box, you can configure the following options:</span></span>
    
   - <span data-ttu-id="43834-147">**Spammeldingen van eindgebruikers inschakelen** Schakel dit selectievakje in om spammeldingen van eindgebruikers voor dit beleid in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="43834-147">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy.</span></span> <span data-ttu-id="43834-148">(Als dit beleid daarentegen is ingeschakeld, u dit selectievakje uitschakelen om spammeldingen van eindgebruikers voor dit beleid uit te schakelen.)</span><span class="sxs-lookup"><span data-stu-id="43834-148">(Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
   - <span data-ttu-id="43834-149">**Elke (dag) spammeldingen van eindgebruikers verzenden** Geef op hoe vaak spammeldingen van eindgebruikers moeten worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="43834-149">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications.</span></span> <span data-ttu-id="43834-150">De standaardinstelling is 3 dagen.</span><span class="sxs-lookup"><span data-stu-id="43834-150">The default is 3 days.</span></span> <span data-ttu-id="43834-151">U tussen 1 en 15 dagen opgeven.</span><span class="sxs-lookup"><span data-stu-id="43834-151">You can specify between 1 and 15 days.</span></span> <span data-ttu-id="43834-152">Als u bijvoorbeeld 7 dagen opgeeft, bevat de melding een lijst met alle berichten die in de afgelopen zeven dagen voor die gebruiker zijn bedoeld en die in plaats daarvan naar de spamquarantaine zijn verzonden.</span><span class="sxs-lookup"><span data-stu-id="43834-152">If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
   - <span data-ttu-id="43834-153">**Meldingstaal** Selecteer met de vervolgkeuzelijst de taal waarin u spammeldingen voor eindgebruikers voor dit beleid wilt schrijven.</span><span class="sxs-lookup"><span data-stu-id="43834-153">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
   - <span data-ttu-id="43834-154">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="43834-154">Click **Save**.</span></span> <span data-ttu-id="43834-155">In het deelvenster verschijnt een overzicht van de beleidsinstellingen voor spamfilters, inclusief de instellingen voor spammeldingen van eindgebruikers.</span><span class="sxs-lookup"><span data-stu-id="43834-155">A summary of your spam filter policy settings, including your end-user spam notification settings, appears in the pane.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="43834-156">Voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="43834-156">For more information</span></span>

[<span data-ttu-id="43834-157">Uw beleid voor spamfilters configureren</span><span class="sxs-lookup"><span data-stu-id="43834-157">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)

[<span data-ttu-id="43834-158">Beleid voor set-hostedcontentfilter</span><span class="sxs-lookup"><span data-stu-id="43834-158">Set-HostedContentFilterPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy)
  
