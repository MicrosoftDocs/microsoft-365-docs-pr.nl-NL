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
ms.openlocfilehash: e19d3a1f93d11cd9873e6b5fad9952b018e0a481
ms.sourcegitcommit: 1522a6471e0c5254a6d0f592e1f4dfacd1dd473a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/24/2020
ms.locfileid: "48245879"
---
# <a name="how-atp-safe-links-works"></a>Hoe Veilige koppelingen in ATP werkt

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT] 
> Als u wilt dat Office 365 op de juiste manier werkt, moeten alle services dezelfde versie hebben.
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a>De werking van veilige koppelingen met ATP en Url's via e-mail

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]
 met Url's per e-mail

Met een hoog niveau gaat u als volgt te werk: een veilige beveiliging van [ATP](atp-safe-links.md) werkt voor url's in e-mail (gehost in Office 365, niet on-premises):
  
1. Mensen ontvangen e-mailberichten, waarvan sommige Url's bevatten.
    
2. Alle e-mailberichten worden doorgevoerd via Exchange Online Protection, waaronder IP-en envelop filters, op handtekening gebaseerde beveiliging van malware, anti-spam en anti-malware-filters. 
    
3. E-mail ontvangt in de postvakken van anderen.
    
4. Een gebruiker meldt zich aan bij Office 365 en gaat naar het postvak in van de e-mail.
    
5. De gebruiker opent een e-mailbericht en klikt op een URL in het e-mailbericht.
    
6. De functie voor veilige vrije verbindingen controleert onmiddellijk de URL voordat u de website opent. De URL wordt aangeduid als geblokkeerd, schadelijk of veilig.
        
   - Als de URL verwijst naar een website die is opgenomen in de [lijst aangepaste geblokkeerde url's](set-up-a-custom-blocked-urls-list-atp.md)van de organisatie, wordt een [waarschuwingspagina](atp-safe-links-warning-pages.md) geopend. 
    
   - Als de URL verwijst naar een website die is ingesteld als schadelijk, wordt een [waarschuwingspagina](atp-safe-links-warning-pages.md) geopend. 
    
   - Als u de URL naar een downloadbaar bestand gaat en de [beleidsregels voor veilige koppelingen](set-up-atp-safe-links-policies.md) van uw organisatie zijn geconfigureerd voor het scannen van dergelijke inhoud, is het downloadbare bestand geselecteerd. 
    
   - Als u zeker weet dat de URL veilig is, wordt de website geopend.
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a>De werking van veilige koppelingen met ATP en Url's in Office-documenten

Met een hoog niveau gaat u als volgt te werk: een [veilige](atp-safe-links.md) beveiliging van de apps in microsoft 365-apps voor Enterprise-of Business Premium-toepassingen (actuele versies van Word, Excel en PowerPoint voor Windows, Mac of in een browser, Office-apps op een IOS-of Android-apparaat, Visio op Windows, OneNote in een browser):
  
1. Personen hebben Microsoft 365-apps voor Enterprise of Business Premium geïnstalleerd op hun computer, smartphone of Tablet. (Of ze gebruiken Office in hun browser.)
    
2. Een gebruiker opent een Word-, Excel-, PowerPoint-, OneNote-, PowerPoint-, OneNote-, PowerPoint-, PowerPoint-, PowerPoint-, OneNote-, PowerPoint-, OneNote-, PowerPoint-, PowerPoint-, 365 OneNote- Het document bevat Url's.
    
3. Wanneer de gebruiker op een URL in het document klikt, wordt de koppeling gecontroleerd via de service voor veilige koppelingen voor ATP.
    
   - Als de URL verwijst naar een website die is opgenomen in de [lijst aangepaste geblokkeerde url's](set-up-a-custom-blocked-urls-list-atp.md)van de organisatie, wordt de gebruiker [gewaarschuwd voor een waarschuwingspagina](atp-safe-links-warning-pages.md).
    
   - Als de URL verwijst naar een website die schadelijk is, wordt de gebruiker [gewaarschuwd voor een waarschuwingspagina](atp-safe-links-warning-pages.md).
    
   - Als u de URL naar een downloadbaar bestand gaat en de [beleidsregels voor veilige koppelingen](set-up-atp-safe-links-policies.md) voor het scannen van dergelijke downloads zijn geconfigureerd, is het downloadbare bestand geselecteerd. 
    
   - Als de URL als veilig wordt beschouwd, wordt de gebruiker gekeken naar de website.
      
   - Als de URL niet kan worden gecontroleerd, wordt de beveiliging van veilige koppelingen niet geactiveerd. Op de bureaublad client wordt de gebruiker gewaarschuwd voordat u verdergaat met de site.
      
> [!NOTE]
> Het kan een paar minuten duren voordat een sessie wordt uitgevoerd om te controleren of de gebruiker voor de gebruiker gebruik moet hebben van ATP voor Office ingeschakeld. 
      
