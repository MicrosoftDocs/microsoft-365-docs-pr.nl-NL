---
title: Onbelangrijke e-mail configureren voor uw organisatie
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'Leer de functie Rommel in- of uitschakelen voor alle of specifieke gebruikers in uw organisatie met Exchange PowerShell. '
ms.openlocfilehash: 069cf7569ebb3654e979100291f6754693b24def
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400134"
---
# <a name="configure-clutter-for-your-organization"></a>Onbelangrijke e-mail configureren voor uw organisatie

> [!TIP]
> [Postvak IN met prioriteit](../setup/configure-focused-inbox.md) gaat Onbelangrijke e-mail vervangen. Meer informatie: [Update op focused inbox en onze plannen voor rommel](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)
  
Als beheerder moet u mogelijk de functie Rommel beheren in Microsoft 365. Als u de functie Onbelangrijke e-mail wilt in- of uitschakelen voor gebruikers in uw organisatie, moet u Exchange PowerShell gebruiken. (Personen kunnen dit in- of uitschakelen met behulp van deze instructies: [Onbelangrijke e-mail uit-/inschakelen in Outlook](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx).) 
  
Zie [Using PowerShell with Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) (PowerShell gebruiken met Exchange Online) en [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) (Verbinding maken met Exchange Online PowerShell) voor informatie over het gebruik van Exchange PowerShell. U moet een account hebben dat ten minste de Exchange Service-beheerdersrol heeft en de mogelijkheid om verbinding te maken met Exchange Online met PowerShell. 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a>Onbelangrijke e-mail inschakelen bij gebruik van Exchange PowerShell

U kunt Onbelangrijke e-mail handmatig voor een postvak inschakelen door de cmdlet [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) uit te voeren. U kunt ook de instellingen voor Onbelangrijke e-mail voor postvakken in uw organisatie weergeven door de cmdlet [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) uit te voeren. 
  
Onbelangrijke e-mail voor gebruiker Ilene de Crom inschakelen
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a>Onbelangrijke e-mail uitschakelen bij gebruik van Exchange PowerShell

U kunt Onbelangrijke e-mail handmatig voor een postvak uitschakelen door de cmdlet [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) uit te voeren. U kunt ook de instellingen voor **Onbelangrijke e-mail** voor postvakken in uw organisatie weergeven door de cmdlet [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) uit te voeren. 
  
Onbelangrijke e-mail voor gebruiker Ilene de Crom uitschakelen:
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

Als u PowerShell gebruikt om veel gebruikers ineens te maken, dan moet u [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) voor elk postvak van een gebruiker uitvoeren om Onbelangrijke e-mail te beheren. 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a>Wanneer krijgen gebruikers de schakeloptie voor het in- en uitschakelen van Onbelangrijke e-mail te zien in de webversie van Outlook?
<a name="bkmk_onoff"> </a>

Als beheerder u Rommel opnieuw inschakelen met Exchange PowerShell. Wanneer u dit hebt gedaan, wordt Postvak IN met prioriteit uitgeschakeld en is Onbelangrijke e-mail opnieuw actief. 
  
 **Als u outlook op internet gebruikt met een Microsoft 365 Business Premium-abonnement:**
  
- Als een gebruiker momenteel Onbelangrijke e-mail heeft ingeschakeld: 
    
  - Instellingen voor Onbelangrijke e-mail worden weergegeven
    
- Als een gebruiker momenteel Postvak IN met prioriteit heeft ingeschakeld: 
    
  - Instellingen voor Onbelangrijke e-mail worden niet weergegeven
    
- Als Onbelangrijke e-mail en Postvak IN met prioriteit beiden zijn uitgeschakeld: 
    
  - Zowel Onbelangrijke e-mail als Postvak IN met prioriteit worden weergegeven als optie in de E-mailinstellingen van de gebruiker.
    
 **Als u Outlook.com gebruikt:**
  
- Als een gebruiker momenteel Onbelangrijke e-mail heeft ingeschakeld: 
    
  - Instellingen voor Onbelangrijke e-mail worden weergegeven
    
- Als een gebruiker momenteel Postvak IN met prioriteit heeft ingeschakeld: 
    
  - Instellingen voor Onbelangrijke e-mail worden niet weergegeven
    
- Als Onbelangrijke e-mail en Postvak IN met prioriteit beiden zijn uitgeschakeld: 
    
  - Zowel Onbelangrijke e-mail als Postvak IN met prioriteit worden weergegeven als optie in de E-mailinstellingen van de gebruiker.
    
- Als een gebruiker Postvak IN met prioriteit op enig moment in het verleden heeft ingeschakeld:
    
  - Instellingen voor Onbelangrijke e-mail worden nooit weergegeven
    
    In alle andere gevallen: 
    
  - Instellingen voor Onbelangrijke e-mail worden weergegeven
    
## <a name="related-articles"></a>Verwante artikelen
<a name="bkmk_onoff"> </a>

[De functie Onbelangrijke e-mail gebruiken om berichten met een lage prioriteit te sorteren in Outlook](https://support.office.com/article/use-clutter-to-sort-low-priority-messages-in-outlook-7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[Rommel gebruiken om berichten met een lage prioriteit te sorteren in OWA](https://support.office.com/article/fe4d64ca-bf73-48f1-91b4-9a659e008bce.aspx)
    
[Onbelangrijke e-mail uitschakelen in Outlook](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx)
    

