---
title: Handtekeningen en disclaimers voor de hele organisatie maken
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2d75860f-c527-4352-a7f6-73eba54c0c72
description: Leer om e-mailhandtekening, wettelijke disclaimer of openbaarmakingsverklaring toe te voegen aan alle e-mailberichten die uw organisatie binnenkomen of verlaten.
ms.openlocfilehash: 5149f6f4a0276cc1384f15a8134d1ede0b673b8c
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44398952"
---
# <a name="create-organization-wide-signatures-and-disclaimers"></a>Handtekeningen en disclaimers voor de hele organisatie maken

 U kunt een e-mailhandtekening, juridische vrijwaring of openbaarmakingsverklaring toevoegen aan de binnenkomende of uitgaande e-mailberichten van de organisatie. U kunt dit toepassen op alle binnenkomende en uitgaande berichten zoals hieronder wordt weergegeven. Of u kunt dit toepassen op bepaalde berichten, zoals berichten met specifieke woorden of tekstpatronen.

 Bekijk een korte video over het maken van een bedrijfsbrede e-mailhandtekening. <br><br>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf] 

Als u deze video nuttig vond, raadpleegt u dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="create-a-signature-that-applies-to-all-messages"></a>Een handtekening maken die van toepassing is op alle berichten

> [!TIP]
> Organisatiebrede handtekeningen worden 'disclaimers' genoemd, ongeacht wat ze bevatten. Ze kunnen bijvoorbeeld gewoon een handtekening zijn, of ook uw adres, wettelijke disclaimer of andere informatie bevatten die u wilt.
    
::: moniker range="o365-worldwide"

Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a>.

::: moniker-end

1. Selecteer het startprogramma voor apps ![ Het pictogram van het startprogramma voor apps en selecteer Vervolgens ](../../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) **Beheerder**.
   
    Kunt u de app die u zoekt niet vinden? Selecteer in het startprogramma voor apps **Alle apps** om een alfabetische lijst te zien met de apps die voor u beschikbaar zijn. Van daaruit kunt u zoeken naar een specifieke app. 
    
2. Selecteer **Beheercentra**en kies **Vervolgens Exchange**.
    
3. Selecteer Onder E-mailstroom de optie **Regels**.
    
4. Selecteer het **+** pictogram (Toevoegen) en kies **Disclaimers toepassen**.
    
5. Geef een naam op voor de regel.
    
6. Selecteer **onder Deze regel toepassen**de optie **[Toepassen op alle berichten]**.
    
    > [!TIP]
    > [Meer informatie](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#Scoping) over het toepassen van voorwaarden als u niet wilt dat de vrijwaring wordt toegepast op alle berichten. (Dit scoping-artikel is voor Exchange Server, maar het is ook van toepassing op Microsoft 365.) 
  
7. Laat onder Ga als volgt te werk de optie **De vrijwaring toevoegen** ingeschakeld. 
    
8.  Selecteer **Tekst invoeren** en typ uw disclaimer. 
    
    > [!TIP]
    > [Meer informatie](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#FormatDisclaimer) over het opmaken van vrijwaringen. (Dit opmaakartikel is voor Exchange Server, maar is ook van toepassing op Microsoft 365.) 

9. Selecteer **Selecteer Er een** en kies **Wrap** als terugvaloptie. Klik op **OK**. Dit betekent dat als de vrijwaring niet kan worden toegevoegd vanwege versleuteling of een andere e-mailinstelling, deze wordt ingesloten in een berichtenvelop.
    
10. Laat **De regel controleren met niveau van ernst** ingeschakeld. Kies nu **Laag**, **Normaal** of **Hoog** voor gebruik in het berichtenlogboek. 
    
11. Kies **Afdwingen** om de vrijwaring direct in te schakelen, tenzij u deze eerst wilt testen. 
    
12. Kies **Meer opties** om extra voorwaarden of uitzonderingen op te nemen. 
    
13. Kies **Opslaan** wanneer u klaar bent. 
    
## <a name="limitations-of-organization-wide-signatures"></a>Beperkingen van organisatiebrede handtekeningen

U het volgende niet doen met Microsoft 365-handtekeningen:
  
- De handtekening direct onder het laatste e-mailantwoord of doorsturen
    
- E-mailhandtekeningen aan de serverzijde weergeven in de mappen Verzonden items van gebruikers
    
- Afbeeldingen insluiten in e-mailhandtekeningen
    
- Regels overslaan die variabelen bevatten die niet kunnen worden bijgewerkt (bijvoorbeeld omdat de waarde niet voor een gebruiker is opgegeven)
    
Gebruik een tool van derden om deze en andere mogelijkheden te verkrijgen. Doe een internet zoeken naar **e-mail handtekening software**. Een aantal van deze providers zijn Microsoft Gold Partners en hun software biedt deze mogelijkheden. 
  
## <a name="more-resources"></a>Meer informatie

- Zie [Disclaimers, handtekeningen, voetteksten of kopteksten voor berichten in de hele organisatie in Microsoft 365](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers) voor informatie over het gebruik van PowerShell. 
    

