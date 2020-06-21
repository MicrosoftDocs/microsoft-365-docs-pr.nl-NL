---
title: Leden toestaan om namens een groep te verzenden of te verzenden
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
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
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: Meer informatie over het toestaan van leden om e-mail te verzenden als Microsoft 365-groep of e-mail te verzenden namens een Microsoft 365-groep.
ms.openlocfilehash: 3a93dda83b10d7c38c8c6e7d8fd484b37df565d0
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780467"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>Leden toestaan om namens een groep te verzenden of te verzenden

Een lid van een Microsoft 365-groep die namens machtigingen **verzenden of** **verzenden** heeft gekregen, kan e-mail verzenden als groep of namens de groep. In dit onderwerp wordt uitgelegd hoe een beheerder deze machtigingen kan instellen.
  
Als Megan Bowen bijvoorbeeld deel uitmaakt van de Microsoft 365-groep **Training** en **als** machtigingen voor de groep heeft verzonden, lijkt het erop dat de **groep Training** de e-mail heeft verzonden als ze een e-mail stuurt als de groep. 
  
Met de machtiging **Verzenden namens naam** kan een gebruiker e-mail verzenden namens een Microsoft 365-groep. Als Alex Wilber bijvoorbeeld deel uitmaakt van de **Marketing** Microsoft 365-groep en **machtigingen namens verzenden** heeft en een e-mail als groep verzendt, ziet de e-mail eruit alsof deze is verzonden door Alex **Wilber namens Marketing.**

> [!IMPORTANT]
> U **Verzenden als** of Verzenden **namens** een bepaalde gebruiker configureren, maar niet beide. Als u beide configureert, wordt deze standaard **verzonden als**.

> [!TIP]
> Zie [E-mail verzenden vanuit of namens een Microsoft 365-groep](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) voor meer informatie over het gebruik van Outlook en Outlook op internet om e-mail vanuit een groep te verzenden.
    
## <a name="allow-members-to-send-email-as-a-group"></a>Leden toestaan om e-mail als groep te verzenden

In deze sectie wordt uitgelegd hoe gebruikers e-mail als groep kunnen verzenden in het [Exchange-beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.
  
1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>naar **Groepen ontvangers** \> **Groups**.
    
2. Selecteer **Het** ![ groeppictogram Bewerken bewerken in groep dat gebruikers ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) als of te sturen wilt toestaan.   
    
3. Selecteer **delegering van groepen**.
    
4. Selecteer **in** de sectie Verzenden als het **+** teken om de gebruikers toe te voegen die u als groep wilt verzenden. 
    
    ![Selecteer het plusteken om de gebruikers toe te voegen die u als Microsoft 365-groep wilt verzenden](../../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. Typ om te zoeken of kies een gebruiker uit de lijst. Selecteer **OK** en **Opslaan**.
    
    ![Typ om een gebruiker uit de lijst te zoeken of te kiezen](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>Leden toestaan om namens een groep e-mail te verzenden

In deze sectie wordt uitgelegd hoe gebruikers e-mail namens een groep kunnen verzenden in het Exchange-beheercentrum (EAC) in Exchange Online.
  
1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>naar **Groepen ontvangers** \> **Groups**.
    
2. Selecteer **Het** ![ groeppictogram Bewerken bewerken in de groep die ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) gebruikers als of te sturen wilt toestaan. 
    
3. Selecteer **delegering van groepen**.
    
4. Selecteer in de sectie Verzenden namens naam het **+** teken om de gebruikers toe te voegen die u als groep wilt verzenden. 
    
    ![Selecteer het plusteken om de gebruikers toe te voegen die u als Microsoft 365-groep wilt verzenden](../../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. Typ om te zoeken of kies een gebruiker uit de lijst. Selecteer **OK** en **Opslaan**.
    
    ![Typ om een gebruiker uit de lijst te zoeken of te kiezen](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a>Verwante artikelen

[Meer informatie over Microsoft 365-groepen](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Bijvoegtoepassing Permissie](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[Set-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616189)
