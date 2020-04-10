---
title: Leden toestaan om namens een groep te verzenden of te verzenden
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: Meer informatie over het toestaan van leden om e-mail te verzenden als Office 365-groep of e-mail te verzenden namens een Office 365-groep.
ms.openlocfilehash: b85b0318587058f1c3eb4d681086ccfcad7f1d8d
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212103"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>Leden toestaan om namens een groep te verzenden of te verzenden

Een lid van een Office 365-groep aan wie **machtigingen verzenden als** of verzenden is **verleend,** kan e-mail verzenden als groep of namens de groep. In dit onderwerp wordt uitgelegd hoe een beheerder deze machtigingen kan instellen.
  
Als Megan Bowen bijvoorbeeld deel uitmaakt van de groep **Trainingsoffice** 365 en **verzenden als** machtigingen voor de groep heeft, ziet het er als ze een e-mail als groep naartoe stuurt, eruit als de **groep Training** die de e-mail heeft verzonden. 
  
Met de machtiging **Verzenden namens** kan een gebruiker e-mail verzenden namens een Office 365-groep. Als Alex Wilber bijvoorbeeld deel uitmaakt van de **groep Marketing** Office 365 en machtigingen voor verzenden **namens de** naam heeft en een e-mail als groep verzendt, ziet de e-mail eruit alsof deze is verzonden door **Alex Wilber namens Marketing.**

> [!IMPORTANT]
> U **Verzenden als** of Verzenden namens **een** bepaalde gebruiker configureren, maar niet beide. Als u beide configureert, wordt standaard **verzonden als**.

> [!TIP]
> Zie [E-mail verzenden van of namens een Office 365-groep](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx) voor meer informatie over het gebruik van Outlook en Outlook op internet om e-mail vanuit een groep te verzenden.
    
## <a name="allow-members-to-send-email-as-a-group"></a>Leden toestaan om e-mail als groep te verzenden

In dit gedeelte wordt uitgelegd hoe u gebruikers toestaat om als groep e-mail te verzenden in het [Exchange-beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.
  
1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>naar \> **Ontvangersgroepen**. **Recipients**
    
2. Selecteer **Edit**![groepspictogram](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) bewerken in Groep waarvan u gebruikers wilt toestaan als te verzenden.   
    
3. Selecteer **delegering van groepen**.
    
4. Selecteer in de sectie **+** Verzenden **als** het teken om de gebruikers toe te voegen die u als groep wilt verzenden. 
    
    ![Selecteer het plusteken om de gebruikers toe te voegen die u wilt verzenden als Office 365-groep](../../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. Typ om te zoeken of kies een gebruiker uit de lijst. Selecteer **OK** en **Opslaan**.
    
    ![Typ om een gebruiker uit de lijst te zoeken of te kiezen](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>Leden toestaan e-mail namens een groep te verzenden

In dit gedeelte wordt uitgelegd hoe u gebruikers toestaat e-mail namens een groep te verzenden in het Exchange-beheercentrum (EAC) in Exchange Online.
  
1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>naar \> **Ontvangersgroepen**. **Recipients**
    
2. Selecteer **Edit** ![groepspictogram](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) bewerken in de groep die gebruikers wilt toestaan te verzenden als. 
    
3. Selecteer **delegering van groepen**.
    
4. Selecteer in de sectie Verzenden **+** namens het teken om de gebruikers toe te voegen die u als groep wilt verzenden. 
    
    ![Selecteer het plusteken om de gebruikers toe te voegen die u wilt verzenden als Office 365-groep](../../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. Typ om te zoeken of kies een gebruiker uit de lijst. Selecteer **OK** en **Opslaan**.
    
    ![Typ om een gebruiker uit de lijst te zoeken of te kiezen](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a>Verwante artikelen

[Meer informatie over Office 365-groepen](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx)

[Machtiging voor geadresseerden toevoegen](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[Set-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616189)
