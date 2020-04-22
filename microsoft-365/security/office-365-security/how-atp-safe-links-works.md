---
title: Hoe Veilige koppelingen in ATP werkt
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: De functie Veilige koppelingen biedt time-of-click verificatie van hyperlinks in Office-documenten en in e-mailberichten. Lees dit artikel om te leren hoe ATP Safe Links werkt.
ms.openlocfilehash: b77ab718afdc4f68d8120e11fa5d1a321b66f32e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638008"
---
# <a name="how-atp-safe-links-works"></a><span data-ttu-id="d4d73-104">Hoe Veilige koppelingen in ATP werkt</span><span class="sxs-lookup"><span data-stu-id="d4d73-104">How ATP Safe Links works</span></span>
> [!IMPORTANT] 
> <span data-ttu-id="d4d73-105">Als u de veilige koppelingen van Office 365 ATP correct wilt werken, moeten alle services in dezelfde versie zijn.</span><span class="sxs-lookup"><span data-stu-id="d4d73-105">For Office 365 ATP Safe Links to operate correctly, all of the services need to be at the same version.</span></span>
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a><span data-ttu-id="d4d73-106">Hoe ATP Safe Links werkt met URL's in e-mail</span><span class="sxs-lookup"><span data-stu-id="d4d73-106">How ATP Safe Links works with URLs in email</span></span>

<span data-ttu-id="d4d73-107">Op een hoog niveau, volgt de manier waarop [ATP Safe Links-beveiliging](atp-safe-links.md) werkt voor URL's in e-mail (gehost in Office 365, niet on-premises):</span><span class="sxs-lookup"><span data-stu-id="d4d73-107">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="d4d73-108">Mensen ontvangen e-mailberichten, waarvan sommige URL's bevatten.</span><span class="sxs-lookup"><span data-stu-id="d4d73-108">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="d4d73-109">Alle e-mail gaat via Exchange Online Protection, waar internetprotocol (IP) en envelopfilters, op handtekeningen gebaseerde malwarebescherming, antispam- en anti-malwarefilters worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="d4d73-109">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="d4d73-110">E-mail komt binnen in de mailboxen van mensen.</span><span class="sxs-lookup"><span data-stu-id="d4d73-110">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="d4d73-111">Een gebruiker meldt zich aan bij Office 365 en gaat naar zijn e-mailpostvak.</span><span class="sxs-lookup"><span data-stu-id="d4d73-111">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="d4d73-112">De gebruiker opent een e-mailbericht en klikt op een URL in het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="d4d73-112">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="d4d73-113">De ATP Safe Links-functie controleert onmiddellijk de URL voordat de website wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="d4d73-113">The ATP Safe Links feature immediately checks the URL before opening the website.</span></span> <span data-ttu-id="d4d73-114">De URL wordt geïdentificeerd als geblokkeerd, kwaadaardig of veilig.</span><span class="sxs-lookup"><span data-stu-id="d4d73-114">The URL is identified as blocked, malicious, or safe.</span></span>
        
   - <span data-ttu-id="d4d73-115">Als de URL naar een website gaat die is opgenomen in de [lijst met aangepaste geblokkeerde URL's van](set-up-a-custom-blocked-urls-list-wtih-atp.md)de organisatie, wordt een [waarschuwingspagina](atp-safe-links-warning-pages.md) geopend.</span><span class="sxs-lookup"><span data-stu-id="d4d73-115">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="d4d73-116">Als de URL naar een website is waarvan is vastgesteld dat deze schadelijk is, wordt een [waarschuwingspagina](atp-safe-links-warning-pages.md) geopend.</span><span class="sxs-lookup"><span data-stu-id="d4d73-116">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="d4d73-117">Als de URL naar een downloadbaar bestand gaat en het [ATP Safe Links-beleid](set-up-atp-safe-links-policies.md) van uw organisatie is geconfigureerd om dergelijke inhoud te scannen, wordt het downloadbare bestand gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="d4d73-117">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="d4d73-118">Als de URL veilig is, wordt de website geopend.</span><span class="sxs-lookup"><span data-stu-id="d4d73-118">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a><span data-ttu-id="d4d73-119">Hoe ATP Safe Links werkt met URL's in Office-documenten</span><span class="sxs-lookup"><span data-stu-id="d4d73-119">How ATP Safe Links works with URLs in Office documents</span></span> 

<span data-ttu-id="d4d73-120">Op hoog niveau werkt [atp-beveiliging voor veilige koppelingen](atp-safe-links.md) voor URL's in Microsoft 365 Apps voor zakelijke of Zakelijke Premium-toepassingen (huidige versies van Word, Excel en PowerPoint op Windows, Mac of in een browser, Office-apps op iOS- of Android-apparaten, Visio op Windows, OneNote in een browser):</span><span class="sxs-lookup"><span data-stu-id="d4d73-120">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in Microsoft 365 Apps for enterprise or Business Premium applications (current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a browser, Office apps on iOS or Android devices, Visio on Windows, OneNote in a browser):</span></span>
  
1. <span data-ttu-id="d4d73-121">Mensen hebben Microsoft 365 Apps voor enterprise of Business Premium geïnstalleerd op hun computer, smartphone of tablet.</span><span class="sxs-lookup"><span data-stu-id="d4d73-121">People have installed Microsoft 365 Apps for enterprise or Business Premium on their computer, smartphone, or tablet.</span></span> <span data-ttu-id="d4d73-122">(Of ze gebruiken Office in hun browser.)</span><span class="sxs-lookup"><span data-stu-id="d4d73-122">(Or, they are using Office in their browser.)</span></span>
    
2. <span data-ttu-id="d4d73-123">Een gebruiker opent een Word-, Excel-, PowerPoint-, OneNote (in de browser) of Visio (op desktop) en meldt zich aan bij Office 365 Enterprise met zijn werk- of schoolaccount.</span><span class="sxs-lookup"><span data-stu-id="d4d73-123">A user opens a Word, Excel, PowerPoint, OneNote (in the browser), or Visio (on desktop), and signs in to Office 365 Enterprise using their work or school account.</span></span> <span data-ttu-id="d4d73-124">Het document bevat URL's.</span><span class="sxs-lookup"><span data-stu-id="d4d73-124">The document contains URLs.</span></span>
    
3. <span data-ttu-id="d4d73-125">Wanneer de gebruiker op een URL in het document klikt, wordt de koppeling gecontroleerd door de ATP Safe Links-service.</span><span class="sxs-lookup"><span data-stu-id="d4d73-125">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
   - <span data-ttu-id="d4d73-126">Als de URL naar een website gaat die is opgenomen in de [aangepaste geblokkeerde URL's lijst van](set-up-a-custom-blocked-urls-list-wtih-atp.md)de organisatie, wordt de gebruiker naar een [waarschuwingspagina geleid.](atp-safe-links-warning-pages.md)</span><span class="sxs-lookup"><span data-stu-id="d4d73-126">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="d4d73-127">Als de URL naar een website is waarvan is vastgesteld dat deze schadelijk is, wordt de gebruiker naar een [waarschuwingspagina geleid.](atp-safe-links-warning-pages.md)</span><span class="sxs-lookup"><span data-stu-id="d4d73-127">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="d4d73-128">Als de URL naar een downloadbaar bestand gaat en het [beleid voor veilige links](set-up-atp-safe-links-policies.md) van ATP is geconfigureerd om dergelijke downloads te scannen, wordt het downloadbare bestand gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="d4d73-128">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="d4d73-129">Als de URL als veilig wordt beschouwd, wordt de gebruiker naar de website geleid.</span><span class="sxs-lookup"><span data-stu-id="d4d73-129">If the URL is considered safe, the user is taken to the website.</span></span>
      
   - <span data-ttu-id="d4d73-130">Als de URL-controle mislukt, wordt de beveiliging van Safe Links niet geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="d4d73-130">If the URL check fails, Safe Links' protection will not trigger.</span></span> <span data-ttu-id="d4d73-131">Op de desktopclients wordt de gebruiker gewaarschuwd voordat hij doorgaat naar de site.</span><span class="sxs-lookup"><span data-stu-id="d4d73-131">On the desktop clients, the user will be warned before proceeding through to the site.</span></span>
      
> [!NOTE]
> <span data-ttu-id="d4d73-132">Het kan enkele seconden duren aan het begin van elke sessie om te controleren of de gebruiker ATP Safe Links for Office heeft ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="d4d73-132">It may take several seconds at the beginning of each session to verify that the user has ATP Safe Links for Office enabled.</span></span> 
      
