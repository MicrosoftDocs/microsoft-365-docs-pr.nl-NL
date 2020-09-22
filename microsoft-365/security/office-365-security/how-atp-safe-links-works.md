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
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: De functie voor veilige koppelingen biedt de optie voor het in-of uitschakelen van hyperlinks in Office-documenten en e-mailberichten. Lees dit artikel voor meer informatie over de werking van veilige koppelingen voor ATP.
ms.openlocfilehash: 09357b20173e2609587137764737c8aba044190e
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201463"
---
# <a name="how-atp-safe-links-works"></a><span data-ttu-id="fde89-104">Hoe Veilige koppelingen in ATP werkt</span><span class="sxs-lookup"><span data-stu-id="fde89-104">How ATP Safe Links works</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT] 
> <span data-ttu-id="fde89-105">Als u wilt dat Office 365 op de juiste manier werkt, moeten alle services dezelfde versie hebben.</span><span class="sxs-lookup"><span data-stu-id="fde89-105">For Office 365 ATP Safe Links to operate correctly, all of the services need to be at the same version.</span></span>
         
## <a name="how-atp-safe-links-works"></a><span data-ttu-id="fde89-106">Hoe Veilige koppelingen in ATP werkt</span><span class="sxs-lookup"><span data-stu-id="fde89-106">How ATP Safe Links works</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]
 <span data-ttu-id="fde89-107">met Url's per e-mail</span><span class="sxs-lookup"><span data-stu-id="fde89-107">with URLs in email</span></span>

<span data-ttu-id="fde89-108">Met een hoog niveau gaat u als volgt te werk: een veilige beveiliging van [ATP](atp-safe-links.md) werkt voor url's in e-mail (gehost in Office 365, niet on-premises):</span><span class="sxs-lookup"><span data-stu-id="fde89-108">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="fde89-109">Mensen ontvangen e-mailberichten, waarvan sommige Url's bevatten.</span><span class="sxs-lookup"><span data-stu-id="fde89-109">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="fde89-110">Alle e-mailberichten worden doorgevoerd via Exchange Online Protection, waaronder IP-en envelop filters, op handtekening gebaseerde beveiliging van malware, anti-spam en anti-malware-filters.</span><span class="sxs-lookup"><span data-stu-id="fde89-110">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="fde89-111">E-mail ontvangt in de postvakken van anderen.</span><span class="sxs-lookup"><span data-stu-id="fde89-111">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="fde89-112">Een gebruiker meldt zich aan bij Office 365 en gaat naar het postvak in van de e-mail.</span><span class="sxs-lookup"><span data-stu-id="fde89-112">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="fde89-113">De gebruiker opent een e-mailbericht en klikt op een URL in het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="fde89-113">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="fde89-114">De functie voor veilige vrije verbindingen controleert onmiddellijk de URL voordat u de website opent.</span><span class="sxs-lookup"><span data-stu-id="fde89-114">The ATP Safe Links feature immediately checks the URL before opening the website.</span></span> <span data-ttu-id="fde89-115">De URL wordt aangeduid als geblokkeerd, schadelijk of veilig.</span><span class="sxs-lookup"><span data-stu-id="fde89-115">The URL is identified as blocked, malicious, or safe.</span></span>
        
   - <span data-ttu-id="fde89-116">Als de URL verwijst naar een website die is opgenomen in de [lijst aangepaste geblokkeerde url's](set-up-a-custom-blocked-urls-list-atp.md)van de organisatie, wordt een [waarschuwingspagina](atp-safe-links-warning-pages.md) geopend.</span><span class="sxs-lookup"><span data-stu-id="fde89-116">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="fde89-117">Als de URL verwijst naar een website die is ingesteld als schadelijk, wordt een [waarschuwingspagina](atp-safe-links-warning-pages.md) geopend.</span><span class="sxs-lookup"><span data-stu-id="fde89-117">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="fde89-118">Als u de URL naar een downloadbaar bestand gaat en de [beleidsregels voor veilige koppelingen](set-up-atp-safe-links-policies.md) van uw organisatie zijn geconfigureerd voor het scannen van dergelijke inhoud, is het downloadbare bestand geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="fde89-118">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="fde89-119">Als u zeker weet dat de URL veilig is, wordt de website geopend.</span><span class="sxs-lookup"><span data-stu-id="fde89-119">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works"></a><span data-ttu-id="fde89-120">Hoe Veilige koppelingen in ATP werkt</span><span class="sxs-lookup"><span data-stu-id="fde89-120">How ATP Safe Links works</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]
 <span data-ttu-id="fde89-121">met Url's in Office-documenten</span><span class="sxs-lookup"><span data-stu-id="fde89-121">with URLs in Office documents</span></span> 

<span data-ttu-id="fde89-122">Met een hoog niveau gaat u als volgt te werk: een [veilige](atp-safe-links.md) beveiliging van de apps in microsoft 365-apps voor Enterprise-of Business Premium-toepassingen (actuele versies van Word, Excel en PowerPoint voor Windows, Mac of in een browser, Office-apps op een IOS-of Android-apparaat, Visio op Windows, OneNote in een browser):</span><span class="sxs-lookup"><span data-stu-id="fde89-122">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in Microsoft 365 Apps for enterprise or Business Premium applications (current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a browser, Office apps on iOS or Android devices, Visio on Windows, OneNote in a browser):</span></span>
  
1. <span data-ttu-id="fde89-123">Personen hebben Microsoft 365-apps voor Enterprise of Business Premium geïnstalleerd op hun computer, smartphone of Tablet.</span><span class="sxs-lookup"><span data-stu-id="fde89-123">People have installed Microsoft 365 Apps for enterprise or Business Premium on their computer, smartphone, or tablet.</span></span> <span data-ttu-id="fde89-124">(Of ze gebruiken Office in hun browser.)</span><span class="sxs-lookup"><span data-stu-id="fde89-124">(Or, they are using Office in their browser.)</span></span>
    
2. <span data-ttu-id="fde89-125">Een gebruiker opent een Word-, Excel-, PowerPoint-, OneNote-, PowerPoint-, OneNote-, PowerPoint-, PowerPoint-, PowerPoint-, OneNote-, PowerPoint-, OneNote-, PowerPoint-, PowerPoint-, 365 OneNote-</span><span class="sxs-lookup"><span data-stu-id="fde89-125">A user opens a Word, Excel, PowerPoint, OneNote (in the browser), or Visio (on desktop), and signs in to Office 365 Enterprise using their work or school account.</span></span> <span data-ttu-id="fde89-126">Het document bevat Url's.</span><span class="sxs-lookup"><span data-stu-id="fde89-126">The document contains URLs.</span></span>
    
3. <span data-ttu-id="fde89-127">Wanneer de gebruiker op een URL in het document klikt, wordt de koppeling gecontroleerd via de service voor veilige koppelingen voor ATP.</span><span class="sxs-lookup"><span data-stu-id="fde89-127">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
   - <span data-ttu-id="fde89-128">Als de URL verwijst naar een website die is opgenomen in de [lijst aangepaste geblokkeerde url's](set-up-a-custom-blocked-urls-list-atp.md)van de organisatie, wordt de gebruiker [gewaarschuwd voor een waarschuwingspagina](atp-safe-links-warning-pages.md).</span><span class="sxs-lookup"><span data-stu-id="fde89-128">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="fde89-129">Als de URL verwijst naar een website die schadelijk is, wordt de gebruiker [gewaarschuwd voor een waarschuwingspagina](atp-safe-links-warning-pages.md).</span><span class="sxs-lookup"><span data-stu-id="fde89-129">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="fde89-130">Als u de URL naar een downloadbaar bestand gaat en de [beleidsregels voor veilige koppelingen](set-up-atp-safe-links-policies.md) voor het scannen van dergelijke downloads zijn geconfigureerd, is het downloadbare bestand geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="fde89-130">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="fde89-131">Als de URL als veilig wordt beschouwd, wordt de gebruiker gekeken naar de website.</span><span class="sxs-lookup"><span data-stu-id="fde89-131">If the URL is considered safe, the user is taken to the website.</span></span>
      
   - <span data-ttu-id="fde89-132">Als de URL niet kan worden gecontroleerd, wordt de beveiliging van veilige koppelingen niet geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="fde89-132">If the URL check fails, Safe Links' protection will not trigger.</span></span> <span data-ttu-id="fde89-133">Op de bureaublad client wordt de gebruiker gewaarschuwd voordat u verdergaat met de site.</span><span class="sxs-lookup"><span data-stu-id="fde89-133">On the desktop clients, the user will be warned before proceeding through to the site.</span></span>
      
> [!NOTE]
> <span data-ttu-id="fde89-134">Het kan een paar minuten duren voordat een sessie wordt uitgevoerd om te controleren of de gebruiker voor de gebruiker gebruik moet hebben van ATP voor Office ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="fde89-134">It may take several seconds at the beginning of each session to verify that the user has ATP Safe Links for Office enabled.</span></span> 
      
