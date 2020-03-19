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
# <a name="how-office-365-atp-safe-links-works"></a>Hoe Office 365 ATP Safe Links werkt
> [!IMPORTANT] 
> Om veilig gebruik te maken van Office 365 ATP-koppelingen moeten alle Office 365-services op dezelfde versie staan.
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a>Hoe ATP Safe Links werkt met URL's in e-mail

Op een hoog niveau werkt [ATP Safe Links-beveiliging](atp-safe-links.md) voor URL's in e-mail (gehost in Office 365, niet on-premises):
  
1. Mensen ontvangen e-mailberichten, waarvan sommige URL's bevatten.
    
2. Alle e-mail gaat via Exchange Online Protection, waar internetprotocol (IP) en envelopfilters, malwarebescherming op basis van handtekeningen, antispam- en anti-malwarefilters worden toegepast. 
    
3. E-mail komt binnen in de inboxen van mensen.
    
4. Een gebruiker meldt zich aan bij Office 365 en gaat naar zijn e-mailpostvak.
    
5. De gebruiker opent een e-mailbericht en klikt op een URL in het e-mailbericht.
    
6. De FUNCTIE ATP Safe Links controleert onmiddellijk de URL voordat u de website opent. De URL wordt geïdentificeerd als geblokkeerd, kwaadaardig of veilig.
        
   - Als de URL naar een website gaat die is opgenomen in de [aangepaste geblokkeerde URL'slijst](set-up-a-custom-blocked-urls-list-wtih-atp.md)van de organisatie, wordt een [waarschuwingspagina](atp-safe-links-warning-pages.md) geopend. 
    
   - Als de URL naar een website gaat waarvan is vastgesteld dat deze kwaadaardig is, wordt een [waarschuwingspagina](atp-safe-links-warning-pages.md) geopend. 
    
   - Als de URL naar een downloadbaar bestand gaat en het [ATP Safe Links-beleid](set-up-atp-safe-links-policies.md) van uw organisatie is geconfigureerd om dergelijke inhoud te scannen, wordt het downloadbare bestand gecontroleerd. 
    
   - Als wordt vastgesteld dat de URL veilig is, wordt de website geopend.
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a>Hoe ATP Safe Links werkt met URL's in Office-documenten 

Op een hoog niveau werkt [ATP Safe Links-beveiliging](atp-safe-links.md) voor URL's in Office 365 ProPlus- of Business Premium-toepassingen (huidige versies van Word, Excel en PowerPoint op Windows, Mac of in een browser, Office-apps op iOS- of Android-apparaten, Visio op Windows, OneNote in een browser):
  
1. Mensen hebben Office 365 ProPlus of Business Premium geïnstalleerd op hun computer, smartphone of tablet. (Of ze gebruiken Office in hun browser.)
    
2. Een gebruiker opent een Word, Excel, PowerPoint, OneNote (in de browser) of Visio (op het bureaublad) en meldt zich aan bij Office 365 Enterprise met zijn werk- of schoolaccount. Het document bevat URL's.
    
3. Wanneer de gebruiker op een URL in het document klikt, wordt de koppeling gecontroleerd door de ATP Safe Links-service.
    
   - Als de URL naar een website gaat die is opgenomen in de [aangepaste geblokkeerde URL'slijst](set-up-a-custom-blocked-urls-list-wtih-atp.md)van de organisatie, wordt de gebruiker naar een [waarschuwingspagina](atp-safe-links-warning-pages.md)geleid.
    
   - Als de URL naar een website gaat waarvan is vastgesteld dat deze schadelijk is, wordt de gebruiker naar een [waarschuwingspagina geleid.](atp-safe-links-warning-pages.md)
    
   - Als de URL naar een downloadbaar bestand gaat en het [ATP Safe Links-beleid](set-up-atp-safe-links-policies.md) is geconfigureerd om dergelijke downloads te scannen, wordt het downloadbare bestand gecontroleerd. 
    
   - Als de URL als veilig wordt beschouwd, wordt de gebruiker naar de website geleid.
      
   - Als de URL-controle mislukt, wordt de beveiliging van Safe Links niet geactiveerd. Op de desktopclients wordt de gebruiker gewaarschuwd voordat deze doorgaat naar de site.
      
> [!NOTE]
> Het kan enkele seconden duren aan het begin van elke sessie om te controleren of de gebruiker ATP Safe Links voor Office heeft ingeschakeld. 
      
