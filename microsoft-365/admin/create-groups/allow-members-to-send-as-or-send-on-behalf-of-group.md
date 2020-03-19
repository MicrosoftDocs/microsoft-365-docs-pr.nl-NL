---
title: Leden toestaan te verzenden als of te verzenden namens een groep
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: Meer informatie over het toestaan van leden om e-mail te verzenden als Office 365-groep of e-mail te verzenden namens een Office 365-groep.
ms.openlocfilehash: 0179dbd2e3093ce80929f6c5f9e689aece845a40
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42809218"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>Leden toestaan te verzenden als of te verzenden namens een groep

Een lid van een Office 365-groep aan wie de machtigingen **Verzenden als** en **Verzenden namens** is verleend, kan nu e-mail verzenden als de groep of namens de groep. In dit onderwerp wordt uitgelegd hoe een beheerder deze machtigingen kan instellen.
  
Als Megan Bowen bijvoorbeeld deel uitmaakt van de **Training** Office 365-groep en **verzenden als** machtigingen voor de groep heeft, ziet het eruit als de trainingsgroep de e-mail heeft verzonden als ze een e-mail stuurt als de groep, als ze een e-mail verzendt, het lijkt erop dat de **trainingsgroep** de e-mail heeft verzonden. 
  
Met de machtiging **Verzenden namens naam** kan een gebruiker e-mail verzenden namens een Office 365-groep. Als Alex Wilber bijvoorbeeld deel uitmaakt van de **Marketing** Office 365-groep en machtigingen **namens Verzenden** heeft en een e-mail als groep verzendt, lijkt de e-mail namens **Marketing.**

> [!IMPORTANT]
> U **Verzenden als** **verzenden** namens een bepaalde gebruiker configureren, maar niet beide. Als u beide configureert, wordt deze standaard **verzonden als**.

> [!TIP]
> Bekijk de stappen in [E-mail verzenden vanuit of namens een Office 365-groep](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx) voor meer informatie over het gebruik van Outlook en Outlook op internet om e-mail vanuit een groep te verzenden.
    
## <a name="allow-members-to-send-email-as-a-group"></a>Leden toestaan e-mail als groep te verzenden

In deze sectie wordt uitgelegd hoe gebruikers e-mail als groep kunnen verzenden in het [Exchange-beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.
  
1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>naar **Geadresseerdengroepen** \> **Groups**.
    
2. Selecteer **Edit**![Groepspictogram](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) Bewerken bewerken in Groep waarmee gebruikers kunnen worden verzonden.   
    
3. Selecteer **delegering van groepen**.
    
4. Selecteer in de sectie **+** Verzenden **als** het teken om de gebruikers toe te voegen die u als groep wilt verzenden. 
    
    ![Selecteer het plusteken om de gebruikers toe te voegen die u als Office 365-groep wilt verzenden](../../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. Typ om te zoeken of kies een gebruiker uit de lijst. Selecteer **OK** en **Opslaan**.
    
    ![Typ om een gebruiker in de lijst te zoeken of te kiezen](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>Leden toestaan e-mail te verzenden namens een groep

In deze sectie wordt uitgelegd hoe gebruikers e-mail kunnen verzenden namens een groep in het Exchange-beheercentrum (EAC) in Exchange Online.
  
1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>naar **Geadresseerdengroepen** \> **Groups**.
    
2. Selecteer **Edit** ![Groepspictogram](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) Bewerken bewerken in de groep die gebruikers als wilt laten verzenden. 
    
3. Selecteer **delegering van groepen**.
    
4. Selecteer in de sectie Verzenden **+** namens het teken om de gebruikers toe te voegen die u als groep wilt verzenden. 
    
    ![Selecteer het plusteken om de gebruikers toe te voegen die u als Office 365-groep wilt verzenden](../../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. Typ om te zoeken of kies een gebruiker uit de lijst. Selecteer **OK** en **Opslaan**.
    
    ![Typ om een gebruiker in de lijst te zoeken of te kiezen](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a>Verwante artikelen

[Meer informatie over Office 365-groepen](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx)

[Toestemming voor invoegontvangers](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[Set-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616189)
