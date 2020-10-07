---
title: Toestaan dat leden namens een groep verzenden of verzenden
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
description: Lees hoe u leden toestaat e-mail te verzenden als een Microsoft 365-groep of e-mail te verzenden namens een groep Microsoft 365.
ms.openlocfilehash: 9ccaeff49914dd5b510beb80f40a3a3b790ce831
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377591"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>Toestaan dat leden namens een groep verzenden of verzenden

Een lid van een Microsoft 365-groep aan wie de machtiging **verzenden als** of **Verzenden namens** is toegewezen, kan e-mail verzenden als de groep of namens de groep. In dit artikel wordt uitgelegd hoe een beheerder deze machtigingen kan instellen.
  
Als Megan Bowen deel uitmaakt van de groep **training** microsoft 365 en als ze een e-mailbericht **verzendt als de** groep, ziet het er als volgt uit: de **trainings** groep stuurt de e-mail. 
  
Met de machtiging **Verzenden namens** kan een gebruiker e-mail verzenden namens een groep microsoft 365. Als Alex Wilber een onderdeel is van de groep **marketing** microsoft 365 en de machtiging **Verzenden namens** en een e-mailbericht verzendt als de groep, ziet de e-mail eruit alsof de E-mail is verzonden door **Alex Wilber namens marketing**.

> [!IMPORTANT]
> U kunt **verzenden als** of **Verzenden namens** configureren voor een bepaalde gebruiker, maar niet beide. Als u beide configureert, wordt het standaard **bericht verzonden als**.

> [!TIP]
> Zie [E-mail verzenden vanuit of namens een Microsoft 365-groep](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) voor meer informatie over het gebruik van Outlook en de webversie van Outlook om e-mail te verzenden vanuit een groep.
    
## <a name="allow-members-to-send-email-as-a-group"></a>Toestaan dat leden e-mail verzenden als groep

In deze sectie wordt uitgelegd hoe u gebruikers kunt toestaan e-mail te verzenden als een groep in het [Exchange-Beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=2059104) in Exchange Online.
  
1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>naar groepen met **geadresseerden** \> **Groups**.
    
2. Selecteer **bewerkings** ![ pictogram bewerken ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) voor de groep die u wilt toestaan dat gebruikers verzenden als.   
    
3. Selecteer **delegering van groepen**.
    
4. Selecteer in de sectie **verzenden als** het **+** teken om de gebruikers toe te voegen die u als de groep wilt verzenden. 
    
    ![Schermafbeelding van het dialoogvenster verzenden als](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. Typ om te zoeken of kies een gebruiker uit de lijst. Selecteer **OK** en **Opslaan**.
    
    ![Typ om te zoeken of selecteer een gebruiker in de lijst](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>Toestaan dat leden e-mail verzenden namens een groep

In deze sectie wordt uitgelegd hoe u gebruikers kunt toestaan e-mail te verzenden namens een groep in het Exchange-Beheercentrum in Exchange Online.
  
1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>naar groepen met **geadresseerden** \> **Groups**.
    
2. Selecteer **bewerkings** ![ pictogram bewerken ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) voor de groep die u wilt toestaan dat gebruikers verzenden als. 
    
3. Selecteer **delegering van groepen**.
    
4. Selecteer in de sectie verzenden namens het **+** teken om de gebruikers toe te voegen die u als de groep wilt verzenden. 
    
    ![Schermafbeelding van het dialoogvenster Verzenden namens](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. Typ om te zoeken of kies een gebruiker uit de lijst. Selecteer **OK** en **Opslaan**.
    
    ![Typ om te zoeken of selecteer een gebruiker in de lijst](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a>Verwante artikelen

[Meer informatie over Microsoft 365-groepen](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Add-RecipientPermission](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[Set-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616189)
