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
description: 'Informatie over het in- of uitschakelen van de functie Onbelangrijke e-mail voor alle of specifieke gebruikers in uw organisatie, met Behulp van Exchange PowerShell. '
ms.openlocfilehash: ac68893bc0aeea5ab214698c54524921e2b1921d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915900"
---
# <a name="configure-clutter-for-your-organization"></a>Onbelangrijke e-mail configureren voor uw organisatie

> [!TIP]
> [Postvak IN met prioriteit](../setup/configure-focused-inbox.md) gaat Onbelangrijke e-mail vervangen. Meer informatie: Update over Postvak IN met focus [en onze plannen voor Onbelangrijke e-mail](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)
  
Als beheerder moet u mogelijk de functie Onbelangrijke e-mail beheren in Microsoft 365. Als u de functie Onbelangrijke e-mail wilt in- of uitschakelen voor gebruikers in uw organisatie, moet u Exchange PowerShell gebruiken. (Personen kunnen het in- of uitschakelen met behulp van deze instructies: [Onbelangrijke e-mail in- of uitschakelen in Outlook.](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
  
Zie [Using PowerShell with Exchange Online](/powershell/exchange/exchange-online-powershell) (PowerShell gebruiken met Exchange Online) en [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor informatie over het gebruik van Exchange PowerShell. U moet een account hebben dat ten minste de rol van exchange-servicebeheerder heeft en de mogelijkheid om verbinding te maken met Exchange Online met PowerShell. 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a>Onbelangrijke e-mail inschakelen bij gebruik van Exchange PowerShell

U kunt Onbelangrijke e-mail handmatig voor een postvak inschakelen door de cmdlet [Set-Clutter](/powershell/module/exchange/set-clutter) uit te voeren. U kunt ook de instellingen voor Onbelangrijke e-mail voor postvakken in uw organisatie weergeven door de cmdlet [Get-Clutter](/powershell/module/exchange/get-clutter) uit te voeren. 
  
Onbelangrijke e-mail voor gebruiker Ilene de Crom inschakelen
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a>Onbelangrijke e-mail uitschakelen bij gebruik van Exchange PowerShell

U kunt Onbelangrijke e-mail handmatig voor een postvak uitschakelen door de cmdlet [Set-Clutter](/powershell/module/exchange/set-clutter) uit te voeren. U kunt ook de instellingen voor **Onbelangrijke e-mail** voor postvakken in uw organisatie weergeven door de cmdlet [Get-Clutter](/powershell/module/exchange/get-clutter) uit te voeren. 
  
Onbelangrijke e-mail voor gebruiker Ilene de Crom uitschakelen:
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

Als u PowerShell gebruikt om veel gebruikers ineens te maken, dan moet u [Set-Clutter](/powershell/module/exchange/set-clutter) voor elk postvak van een gebruiker uitvoeren om Onbelangrijke e-mail te beheren. 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a>Wanneer krijgen gebruikers de schakeloptie voor het in- en uitschakelen van Onbelangrijke e-mail te zien in de webversie van Outlook?
<a name="bkmk_onoff"> </a>

Als beheerder kunt u Onbelangrijke e-mail opnieuw inschakelen met Exchange PowerShell. Wanneer u dit hebt gedaan, wordt Postvak IN met prioriteit uitgeschakeld en is Onbelangrijke e-mail opnieuw actief. 
  
 **Als u de webversie van Outlook gebruikt met een Microsoft 365 Business Premium-abonnement:**
  
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

[De functie Onbelangrijke e-mail gebruiken om berichten met een lage prioriteit te sorteren in Outlook](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[Onbelangrijke e-mail gebruiken om berichten met een lage prioriteit te sorteren in OWA](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce)
    
[Onbelangrijke e-mail uitschakelen in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
