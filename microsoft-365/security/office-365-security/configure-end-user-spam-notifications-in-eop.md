---
title: Spammeldingen voor eindgebruikers configureren in EOP
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
ms.assetid: e9947db5-1dd1-4493-872d-7362b24c7ba0
ms.collection:
- M365-security-compliance
description: U spammeldingen van eindgebruikers configureren voor het standaardbeleid voor inhoudsbrede inhoudsfilter voor het hele standaardbedrijf of voor aangepast beleid voor inhoudsfilters dat op domeinen wordt toegepast.
ms.openlocfilehash: 6ac43ee3419e7b768312b6826994a5b8f5e4a231
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42812430"
---
# <a name="configure-end-user-spam-notifications-in-eop"></a><span data-ttu-id="5ffa4-103">Spammeldingen voor eindgebruikers configureren in EOP</span><span class="sxs-lookup"><span data-stu-id="5ffa4-103">Configure end-user spam notifications in EOP</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5ffa4-104">Dit onderwerp is voor zelfstandige klanten van Exchange Online Protection (EOP) die on-premises mailboxen beschermen.</span><span class="sxs-lookup"><span data-stu-id="5ffa4-104">This topic is for Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes.</span></span> <span data-ttu-id="5ffa4-105">Exchange Online-klanten die door de cloud gehoste postvakken beschermen, moeten in plaats daarvan het volgende onderwerp lezen: [Spammeldingen](configure-end-user-spam-notifications-in-exchange-online.md)voor eindgebruikers configureren in Exchange Online .</span><span class="sxs-lookup"><span data-stu-id="5ffa4-105">Exchange Online customers who are protecting cloud-hosted mailboxes should read the following topic instead: [Configure end-user spam notifications in Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md).</span></span> 
  
<span data-ttu-id="5ffa4-106">U spammeldingen van eindgebruikers configureren voor het standaardbeleid voor spamfilter voor het hele bedrijf of voor aangepast spamfilterbeleid.</span><span class="sxs-lookup"><span data-stu-id="5ffa4-106">You can configure end-user spam notifications for the default company-wide spam filter policy or for custom spam filter policies.</span></span> <span data-ttu-id="5ffa4-107">Als u spammeldingen van eindgebruikers inschakelt, kunnen uw gebruikers hun eigen spam-, bulk- en phishingberichten beheren.</span><span class="sxs-lookup"><span data-stu-id="5ffa4-107">Enabling end-user spam notification messages lets your users manage their own quarantined spam, bulk, and phishing messages.</span></span> 
  
<span data-ttu-id="5ffa4-108">Spammeldingen van eindgebruikers bevatten een lijst met alle spamberichten die de eindgebruiker heeft ontvangen gedurende een periode die u configureert (u een waarde opgeven tussen 1 en 15 dagen).</span><span class="sxs-lookup"><span data-stu-id="5ffa4-108">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days).</span></span> <span data-ttu-id="5ffa4-109">U ook de taal configureren waarin het meldingsbericht is geschreven.</span><span class="sxs-lookup"><span data-stu-id="5ffa4-109">You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="5ffa4-110">Na ontvangst van een meldingsbericht kunnen eindgebruikers kiezen uit de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="5ffa4-110">After receiving a notification message, end users can choose from the following options:</span></span>

<span data-ttu-id="5ffa4-111">**Afzender blokkeren** als u wilt dat Office 365 de afzender toevoegt aan de lijst met geblokkeerde afzenders.</span><span class="sxs-lookup"><span data-stu-id="5ffa4-111">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

<span data-ttu-id="5ffa4-112">**Laat vrij** als het bericht geen spam is en u wilt dat Office 365 het bericht naar uw postvak verzendt.</span><span class="sxs-lookup"><span data-stu-id="5ffa4-112">**Release** if the message isn't spam and you want Office 365 to send the message to your mailbox.</span></span>

<span data-ttu-id="5ffa4-113">**Controleer** of u naar de quarantaineportal in het Beveiligings- en Nalevingscentrum wilt navigeren als u andere acties wilt uitvoeren, zoals Voorbeeld of Release.</span><span class="sxs-lookup"><span data-stu-id="5ffa4-113">**Review** to navigate to the Quarantine Portal within the Security and Compliance Center if you want to take other actions, such as Preview or Release.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5ffa4-114">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="5ffa4-114">What do you need to know before you begin?</span></span>
<span data-ttu-id="5ffa4-115"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="5ffa4-115"><a name="sectionSection0"> </a></span></span>

<span data-ttu-id="5ffa4-116">Geschatte tijd om te voltooien: 5 minuten</span><span class="sxs-lookup"><span data-stu-id="5ffa4-116">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="5ffa4-117">U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="5ffa4-117">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="5ffa4-118">Zie de vermelding 'Antispam' in het onderwerp [Functiemachtigingen in het eOP-onderwerp](feature-permissions-in-eop.md) om te zien welke machtigingen u nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="5ffa4-118">To see what permissions you need, see the "Anti-spam" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span> 
  
<span data-ttu-id="5ffa4-119">Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="5ffa4-119">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="5ffa4-120">De EAC gebruiken om spammeldingen van eindgebruikers te configureren</span><span class="sxs-lookup"><span data-stu-id="5ffa4-120">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="5ffa4-121">Navigeer in het Exchange Admin Center (EAC) naar**het spamfilter** **beveiliging** > .</span><span class="sxs-lookup"><span data-stu-id="5ffa4-121">In the Exchange Admin Center (EAC), navigate to **Protection** > **Spam filter**.</span></span>
    
2. <span data-ttu-id="5ffa4-122">Selecteer het inhoudsfilterbeleid waarvoor u spammeldingen van eindgebruikers wilt inschakelen (deze zijn standaard uitgeschakeld).</span><span class="sxs-lookup"><span data-stu-id="5ffa4-122">Select the content filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="5ffa4-123">Klik in het rechterdeelvenster, waar de overzichtsgegevens over uw beleid worden weergegeven, op de koppeling **Spammeldingen voor** eindgebruikers configureren.</span><span class="sxs-lookup"><span data-stu-id="5ffa4-123">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="5ffa4-124">In het volgende dialoogvenster u de volgende opties configureren:</span><span class="sxs-lookup"><span data-stu-id="5ffa4-124">In the subsequent dialog box, you can configure the following options:</span></span>
    
1. <span data-ttu-id="5ffa4-125">**Spammeldingen** van eindgebruikers inschakelen Schakel dit selectievakje in om spammeldingen van eindgebruikers voor dit beleid in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="5ffa4-125">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy.</span></span> <span data-ttu-id="5ffa4-126">(Als dit beleid omgekeerd is ingeschakeld, u dit selectievakje uitschakelen om spammeldingen van eindgebruikers voor dit beleid uit te schakelen.)</span><span class="sxs-lookup"><span data-stu-id="5ffa4-126">(Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
2. <span data-ttu-id="5ffa4-127">**Stuur elke (dagen) spammeldingen van eindgebruikers** Geef op hoe vaak spammeldingen van eindgebruikers moeten worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="5ffa4-127">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications.</span></span> <span data-ttu-id="5ffa4-128">De standaardinstelling is 3 dagen.</span><span class="sxs-lookup"><span data-stu-id="5ffa4-128">The default is 3 days.</span></span> <span data-ttu-id="5ffa4-129">U opgeven tussen 1 en 15 dagen.</span><span class="sxs-lookup"><span data-stu-id="5ffa4-129">You can specify between 1 and 15 days.</span></span> <span data-ttu-id="5ffa4-130">Als u bijvoorbeeld 7 dagen opgeeft, bevat de melding een lijst met alle berichten die in de afgelopen 7 dagen voor die gebruiker zijn bedoeld en die in plaats daarvan naar de spamquarantaine zijn verzonden.</span><span class="sxs-lookup"><span data-stu-id="5ffa4-130">If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
3. <span data-ttu-id="5ffa4-131">**Meldingstaal** Selecteer met de vervolgkeuzelijst de taal om spammeldingen van eindgebruikers voor dit beleid te schrijven.</span><span class="sxs-lookup"><span data-stu-id="5ffa4-131">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
5. <span data-ttu-id="5ffa4-132">Klik **op Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="5ffa4-132">Click **save**.</span></span> <span data-ttu-id="5ffa4-133">Een overzicht van de beleidsinstellingen van uw inhoudsfilter, inclusief de instellingen voor spammeldingen van uw eindgebruiker, wordt in het rechterdeelvenster weergegeven.</span><span class="sxs-lookup"><span data-stu-id="5ffa4-133">A summary of your content filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="5ffa4-134">Spammeldingen van eindgebruikers zijn alleen functioneel voor het beleid voor inhoudsfilter dat is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="5ffa4-134">End-user spam notifications will only be functional for content filter policies that are enabled.</span></span> <span data-ttu-id="5ffa4-135">> spammeldingen van eindgebruikers worden slechts één keer per dag verzonden.</span><span class="sxs-lookup"><span data-stu-id="5ffa4-135">>  End-user spam notifications are only sent once per day.</span></span> <span data-ttu-id="5ffa4-136">De levertijd van de melding kan niet worden gegarandeerd voor een specifieke klant en is niet configureerbaar.</span><span class="sxs-lookup"><span data-stu-id="5ffa4-136">The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="5ffa4-137">**Tip:** Als u spammeldingen van eindgebruikers wilt testen door ze naar een beperkte groep gebruikers te sturen voordat u ze volledig implementeert, maakt u een aangepast inhoudsfilterbeleid waarmee spammeldingen van eindgebruikers kunnen worden uitgevoerd voor de domeinen waarin de gebruikers zich bevinden.</span><span class="sxs-lookup"><span data-stu-id="5ffa4-137">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom content filter policy that enables end-user spam notifications for the domains in which the users reside.</span></span> <span data-ttu-id="5ffa4-138">Maak vervolgens in de EAC onder regels voor \*\*de e-mailstroom \> \*\*een e-mailstroomregel (ook wel een transportregel genoemd) om berichten te blokkeren vanaf quarantine@messaging.microsoft.com (het e-mailadres dat meldingen verzendt) met uitzonderingen voor de gebruikers die u de meldingen wilt ontvangen.</span><span class="sxs-lookup"><span data-stu-id="5ffa4-138">Then, in the EAC, under **Mail flow \> rules**, create a mail flow rule (also known as a transport rule) to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications.</span></span> <span data-ttu-id="5ffa4-139">De volgende afbeelding is een voorbeeld van het maken van een uitzondering voor twee gebruikers (SaraD en AlexD) van domein Contoso.com:</span><span class="sxs-lookup"><span data-stu-id="5ffa4-139">The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![Transportregel om spammeldingen van eindgebruikers te testen](../../media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a><span data-ttu-id="5ffa4-141">Voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="5ffa4-141">For more information</span></span>

[<span data-ttu-id="5ffa4-142">Uw spamfilterbeleid configureren</span><span class="sxs-lookup"><span data-stu-id="5ffa4-142">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
