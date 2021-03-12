---
title: Toestaan dat leden verzenden als of verzenden namens een groep
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: Meer informatie over het toestaan dat groepsleden e-mail verzenden als een Microsoft 365-groep of e-mail verzenden namens een Microsoft 365-groep.
ms.openlocfilehash: 44a0a7a690c8faa9fe00732e8154f36aa5a6fe6f
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727077"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>Toestaan dat leden verzenden als of verzenden namens een groep

Een lid van een Microsoft 365-groep  die machtigingen voor Verzenden **als** of Namens verzenden heeft gekregen, kan e-mail verzenden als de groep of namens de groep. (Gasten in de groep kunnen deze machtigingen niet krijgen.)

In dit artikel wordt uitgelegd hoe een globale of Exchange-beheerder deze machtigingen kan instellen.
  
Als Megan Bowen bijvoorbeeld deel uitmaakt van de **groep** Training  Microsoft 365 en heeft verzenden als machtigingen voor de  groep, lijkt het erop dat de groep Training de e-mail heeft verzonden als ze een e-mailbericht verzendt als de groep. 
  
Met **de machtiging Namens verzenden** kan een gebruiker e-mail verzenden namens een Microsoft 365-groep. Als Alex Wilber bijvoorbeeld deel uitmaakt van de **groep Marketing** Microsoft  365 en machtigingen voor Verzenden namens heeft en een e-mailbericht als de groep verzendt, ziet het eruit alsof het e-mailbericht is verzonden door **Alex Wilber** namens Marketing.

> [!IMPORTANT]
> U kunt Verzenden **als of** Verzenden namens een bepaalde gebruiker **configureren,** maar niet beide. Als u beide configureert, wordt deze standaard ingesteld op **Verzenden als**.

> [!TIP]
> Zie [E-mail verzenden vanuit of namens een Microsoft 365-groep](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) voor meer informatie over het gebruik van Outlook en de webversie van Outlook om e-mail te verzenden vanuit een groep.
    
## <a name="allow-members-to-send-email-as-a-group"></a>Toestaan dat leden e-mail verzenden als een groep

In deze sectie wordt uitgelegd hoe gebruikers e-mail kunnen verzenden als een groep in het [Exchange-beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.
  
1. Ga in <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">het Exchange-beheercentrum</a>naar **Geadresseerdengroepen.** \> 
    
2. Selecteer **Groepspictogram** ![ Bewerken bewerken in de groep die u wilt toestaan dat gebruikers verzenden ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) als.   
    
3. Selecteer **delegering van groepen**.
    
4. Selecteer in **de sectie Verzenden als** het teken om de gebruikers toe te voegen die u als groep wilt **+** verzenden. 
    
    ![Schermafbeelding van het dialoogvenster Verzenden als](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. Typ om te zoeken of kies een gebruiker uit de lijst. Selecteer **OK** en **Opslaan.**
    
    ![Typ om een gebruiker in de lijst te zoeken of te kiezen](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>Leden toestaan e-mail te verzenden namens een groep

In deze sectie wordt uitgelegd hoe gebruikers e-mail kunnen verzenden namens een groep in het Exchange-beheercentrum (EAC) in Exchange Online.
  
1. Ga in <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">het Exchange-beheercentrum</a>naar **Geadresseerdengroepen.** \> 
    
2. Selecteer **Groepspictogram** ![ Bewerken bewerken in de groep die u wilt toestaan dat gebruikers verzenden ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) als. 
    
3. Selecteer **delegering van groepen**.
    
4. Selecteer in de sectie Namens verzenden het teken om de gebruikers toe te voegen **+** die u als groep wilt verzenden. 
    
    ![Schermafbeelding van verzenden namens dialoogvenster](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. Typ om te zoeken of kies een gebruiker uit de lijst. Selecteer **OK** en **Opslaan.**
    
    ![Typ om een gebruiker in de lijst te zoeken of te kiezen](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a>Verwante artikelen

[Planning van samenwerkingsbeheer stap voor stap](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Uw samenwerkingsbeheerplan maken](collaboration-governance-first.md)

[Meer informatie over Microsoft 365-groepen](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Add-RecipientPermission](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[Set-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616189)
