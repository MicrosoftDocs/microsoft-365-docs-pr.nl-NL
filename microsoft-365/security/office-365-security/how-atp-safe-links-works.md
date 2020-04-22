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
# <a name="how-atp-safe-links-works"></a>Hoe Veilige koppelingen in ATP werkt
> [!IMPORTANT] 
> Als u de veilige koppelingen van Office 365 ATP correct wilt werken, moeten alle services in dezelfde versie zijn.
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a>Hoe ATP Safe Links werkt met URL's in e-mail

Op een hoog niveau, volgt de manier waarop [ATP Safe Links-beveiliging](atp-safe-links.md) werkt voor URL's in e-mail (gehost in Office 365, niet on-premises):
  
1. Mensen ontvangen e-mailberichten, waarvan sommige URL's bevatten.
    
2. Alle e-mail gaat via Exchange Online Protection, waar internetprotocol (IP) en envelopfilters, op handtekeningen gebaseerde malwarebescherming, antispam- en anti-malwarefilters worden toegepast. 
    
3. E-mail komt binnen in de mailboxen van mensen.
    
4. Een gebruiker meldt zich aan bij Office 365 en gaat naar zijn e-mailpostvak.
    
5. De gebruiker opent een e-mailbericht en klikt op een URL in het e-mailbericht.
    
6. De ATP Safe Links-functie controleert onmiddellijk de URL voordat de website wordt geopend. De URL wordt geïdentificeerd als geblokkeerd, kwaadaardig of veilig.
        
   - Als de URL naar een website gaat die is opgenomen in de [lijst met aangepaste geblokkeerde URL's van](set-up-a-custom-blocked-urls-list-wtih-atp.md)de organisatie, wordt een [waarschuwingspagina](atp-safe-links-warning-pages.md) geopend. 
    
   - Als de URL naar een website is waarvan is vastgesteld dat deze schadelijk is, wordt een [waarschuwingspagina](atp-safe-links-warning-pages.md) geopend. 
    
   - Als de URL naar een downloadbaar bestand gaat en het [ATP Safe Links-beleid](set-up-atp-safe-links-policies.md) van uw organisatie is geconfigureerd om dergelijke inhoud te scannen, wordt het downloadbare bestand gecontroleerd. 
    
   - Als de URL veilig is, wordt de website geopend.
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a>Hoe ATP Safe Links werkt met URL's in Office-documenten 

Op hoog niveau werkt [atp-beveiliging voor veilige koppelingen](atp-safe-links.md) voor URL's in Microsoft 365 Apps voor zakelijke of Zakelijke Premium-toepassingen (huidige versies van Word, Excel en PowerPoint op Windows, Mac of in een browser, Office-apps op iOS- of Android-apparaten, Visio op Windows, OneNote in een browser):
  
1. Mensen hebben Microsoft 365 Apps voor enterprise of Business Premium geïnstalleerd op hun computer, smartphone of tablet. (Of ze gebruiken Office in hun browser.)
    
2. Een gebruiker opent een Word-, Excel-, PowerPoint-, OneNote (in de browser) of Visio (op desktop) en meldt zich aan bij Office 365 Enterprise met zijn werk- of schoolaccount. Het document bevat URL's.
    
3. Wanneer de gebruiker op een URL in het document klikt, wordt de koppeling gecontroleerd door de ATP Safe Links-service.
    
   - Als de URL naar een website gaat die is opgenomen in de [aangepaste geblokkeerde URL's lijst van](set-up-a-custom-blocked-urls-list-wtih-atp.md)de organisatie, wordt de gebruiker naar een [waarschuwingspagina geleid.](atp-safe-links-warning-pages.md)
    
   - Als de URL naar een website is waarvan is vastgesteld dat deze schadelijk is, wordt de gebruiker naar een [waarschuwingspagina geleid.](atp-safe-links-warning-pages.md)
    
   - Als de URL naar een downloadbaar bestand gaat en het [beleid voor veilige links](set-up-atp-safe-links-policies.md) van ATP is geconfigureerd om dergelijke downloads te scannen, wordt het downloadbare bestand gecontroleerd. 
    
   - Als de URL als veilig wordt beschouwd, wordt de gebruiker naar de website geleid.
      
   - Als de URL-controle mislukt, wordt de beveiliging van Safe Links niet geactiveerd. Op de desktopclients wordt de gebruiker gewaarschuwd voordat hij doorgaat naar de site.
      
> [!NOTE]
> Het kan enkele seconden duren aan het begin van elke sessie om te controleren of de gebruiker ATP Safe Links for Office heeft ingeschakeld. 
      
