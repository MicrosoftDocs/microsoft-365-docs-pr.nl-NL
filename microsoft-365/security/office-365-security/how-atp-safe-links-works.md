---
title: Hoe Office 365 ATP Safe Links werkt
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
description: De functie Veilige koppelingen biedt tijd-van-klikverificatie van hyperlinks in Office-documenten en in e-mailberichten. Lees dit artikel om te leren hoe ATP Safe Links werkt.
ms.openlocfilehash: c87eef2afbb3a694d9906de0c6c43bfeb576782b
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42809159"
---
# <a name="how-office-365-atp-safe-links-works"></a><span data-ttu-id="86794-104">Hoe Office 365 ATP Safe Links werkt</span><span class="sxs-lookup"><span data-stu-id="86794-104">How Office 365 ATP Safe Links works</span></span>
> [!IMPORTANT] 
> <span data-ttu-id="86794-105">Om veilig gebruik te maken van Office 365 ATP-koppelingen moeten alle Office 365-services op dezelfde versie staan.</span><span class="sxs-lookup"><span data-stu-id="86794-105">For Office 365 ATP Safe Links to operate correctly, all of the Office 365 services need to be at the same version.</span></span>
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a><span data-ttu-id="86794-106">Hoe ATP Safe Links werkt met URL's in e-mail</span><span class="sxs-lookup"><span data-stu-id="86794-106">How ATP Safe Links works with URLs in email</span></span>

<span data-ttu-id="86794-107">Op een hoog niveau werkt [ATP Safe Links-beveiliging](atp-safe-links.md) voor URL's in e-mail (gehost in Office 365, niet on-premises):</span><span class="sxs-lookup"><span data-stu-id="86794-107">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="86794-108">Mensen ontvangen e-mailberichten, waarvan sommige URL's bevatten.</span><span class="sxs-lookup"><span data-stu-id="86794-108">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="86794-109">Alle e-mail gaat via Exchange Online Protection, waar internetprotocol (IP) en envelopfilters, malwarebescherming op basis van handtekeningen, antispam- en anti-malwarefilters worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="86794-109">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="86794-110">E-mail komt binnen in de inboxen van mensen.</span><span class="sxs-lookup"><span data-stu-id="86794-110">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="86794-111">Een gebruiker meldt zich aan bij Office 365 en gaat naar zijn e-mailpostvak.</span><span class="sxs-lookup"><span data-stu-id="86794-111">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="86794-112">De gebruiker opent een e-mailbericht en klikt op een URL in het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="86794-112">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="86794-113">De FUNCTIE ATP Safe Links controleert onmiddellijk de URL voordat u de website opent.</span><span class="sxs-lookup"><span data-stu-id="86794-113">The ATP Safe Links feature immediately checks the URL before opening the website.</span></span> <span data-ttu-id="86794-114">De URL wordt geïdentificeerd als geblokkeerd, kwaadaardig of veilig.</span><span class="sxs-lookup"><span data-stu-id="86794-114">The URL is identified as blocked, malicious, or safe.</span></span>
        
   - <span data-ttu-id="86794-115">Als de URL naar een website gaat die is opgenomen in de [aangepaste geblokkeerde URL'slijst](set-up-a-custom-blocked-urls-list-wtih-atp.md)van de organisatie, wordt een [waarschuwingspagina](atp-safe-links-warning-pages.md) geopend.</span><span class="sxs-lookup"><span data-stu-id="86794-115">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="86794-116">Als de URL naar een website gaat waarvan is vastgesteld dat deze kwaadaardig is, wordt een [waarschuwingspagina](atp-safe-links-warning-pages.md) geopend.</span><span class="sxs-lookup"><span data-stu-id="86794-116">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="86794-117">Als de URL naar een downloadbaar bestand gaat en het [ATP Safe Links-beleid](set-up-atp-safe-links-policies.md) van uw organisatie is geconfigureerd om dergelijke inhoud te scannen, wordt het downloadbare bestand gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="86794-117">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="86794-118">Als wordt vastgesteld dat de URL veilig is, wordt de website geopend.</span><span class="sxs-lookup"><span data-stu-id="86794-118">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a><span data-ttu-id="86794-119">Hoe ATP Safe Links werkt met URL's in Office-documenten</span><span class="sxs-lookup"><span data-stu-id="86794-119">How ATP Safe Links works with URLs in Office documents</span></span> 

<span data-ttu-id="86794-120">Op een hoog niveau werkt [ATP Safe Links-beveiliging](atp-safe-links.md) voor URL's in Office 365 ProPlus- of Business Premium-toepassingen (huidige versies van Word, Excel en PowerPoint op Windows, Mac of in een browser, Office-apps op iOS- of Android-apparaten, Visio op Windows, OneNote in een browser):</span><span class="sxs-lookup"><span data-stu-id="86794-120">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in Office 365 ProPlus or Business Premium applications (current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a browser, Office apps on iOS or Android devices, Visio on Windows, OneNote in a browser):</span></span>
  
1. <span data-ttu-id="86794-121">Mensen hebben Office 365 ProPlus of Business Premium geïnstalleerd op hun computer, smartphone of tablet.</span><span class="sxs-lookup"><span data-stu-id="86794-121">People have installed Office 365 ProPlus or Business Premium on their computer, smartphone, or tablet.</span></span> <span data-ttu-id="86794-122">(Of ze gebruiken Office in hun browser.)</span><span class="sxs-lookup"><span data-stu-id="86794-122">(Or, they are using Office in their browser.)</span></span>
    
2. <span data-ttu-id="86794-123">Een gebruiker opent een Word, Excel, PowerPoint, OneNote (in de browser) of Visio (op het bureaublad) en meldt zich aan bij Office 365 Enterprise met zijn werk- of schoolaccount.</span><span class="sxs-lookup"><span data-stu-id="86794-123">A user opens a Word, Excel, PowerPoint, OneNote (in the browser), or Visio (on desktop), and signs in to Office 365 Enterprise using their work or school account.</span></span> <span data-ttu-id="86794-124">Het document bevat URL's.</span><span class="sxs-lookup"><span data-stu-id="86794-124">The document contains URLs.</span></span>
    
3. <span data-ttu-id="86794-125">Wanneer de gebruiker op een URL in het document klikt, wordt de koppeling gecontroleerd door de ATP Safe Links-service.</span><span class="sxs-lookup"><span data-stu-id="86794-125">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
   - <span data-ttu-id="86794-126">Als de URL naar een website gaat die is opgenomen in de [aangepaste geblokkeerde URL'slijst](set-up-a-custom-blocked-urls-list-wtih-atp.md)van de organisatie, wordt de gebruiker naar een [waarschuwingspagina](atp-safe-links-warning-pages.md)geleid.</span><span class="sxs-lookup"><span data-stu-id="86794-126">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="86794-127">Als de URL naar een website gaat waarvan is vastgesteld dat deze schadelijk is, wordt de gebruiker naar een [waarschuwingspagina geleid.](atp-safe-links-warning-pages.md)</span><span class="sxs-lookup"><span data-stu-id="86794-127">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="86794-128">Als de URL naar een downloadbaar bestand gaat en het [ATP Safe Links-beleid](set-up-atp-safe-links-policies.md) is geconfigureerd om dergelijke downloads te scannen, wordt het downloadbare bestand gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="86794-128">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="86794-129">Als de URL als veilig wordt beschouwd, wordt de gebruiker naar de website geleid.</span><span class="sxs-lookup"><span data-stu-id="86794-129">If the URL is considered safe, the user is taken to the website.</span></span>
      
   - <span data-ttu-id="86794-130">Als de URL-controle mislukt, wordt de beveiliging van Safe Links niet geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="86794-130">If the URL check fails, Safe Links' protection will not trigger.</span></span> <span data-ttu-id="86794-131">Op de desktopclients wordt de gebruiker gewaarschuwd voordat deze doorgaat naar de site.</span><span class="sxs-lookup"><span data-stu-id="86794-131">On the desktop clients, the user will be warned before proceeding through to the site.</span></span>
      
> [!NOTE]
> <span data-ttu-id="86794-132">Het kan enkele seconden duren aan het begin van elke sessie om te controleren of de gebruiker ATP Safe Links voor Office heeft ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="86794-132">It may take several seconds at the beginning of each session to verify that the user has ATP Safe Links for Office enabled.</span></span> 
      
