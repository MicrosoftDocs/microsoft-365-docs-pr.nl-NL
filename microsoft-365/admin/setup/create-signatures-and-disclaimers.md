---
title: Maak handtekeningen en disclaimers voor de hele organisatie
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
description: Leer e-mailhandtekening, wettelijke disclaimer of openbaarmakingsverklaring toe te voegen aan alle e-mailberichten die uw organisatie invoeren of verlaten.
ms.openlocfilehash: d7e19c6e3f425f95429aefd769d2b8992fde141e
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779879"
---
# <a name="create-organization-wide-signatures-and-disclaimers"></a>Maak handtekeningen en disclaimers voor de hele organisatie

 You can add an email signature, legal disclaimer, or disclosure statement to the email messages that enter or leave your organization. You can set it up to apply to all incoming and outgoing messages as shown below. Or you can apply it to certain messages like those containing specific words or text patterns.

 Bekijk een korte video over het maken van een bedrijfsbrede e-mailhandtekening. <br><br>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf] 

Als u deze video nuttig vond, raadpleegt u dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="create-a-signature-that-applies-to-all-messages"></a>Een handtekening maken die van toepassing is op alle berichten

> [!TIP]
> Organisatiebrede handtekeningen worden "disclaimers" genoemd, ongeacht wat ze bevatten. Ze kunnen bijvoorbeeld gewoon een handtekening zijn, of ook uw adres, wettelijke disclaimer of andere informatie bevatten die u wilt.
    
::: moniker range="o365-worldwide"

Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a>.

::: moniker-end

1. Selecteer het startpictogram voor ![ de app Het startpictogram voor apps en ](../../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) selecteer **Beheerder**.
   
    Kunt u de app die u zoekt niet vinden? Selecteer in het startprogramma voor apps de optie **Alle apps** om een alfabetische lijst te zien van de apps die voor u beschikbaar zijn. Van daaruit kunt u zoeken naar een specifieke app. 
    
2. Selecteer **Beheercentra**en kies **Exchange**.
    
3. Selecteer onder E-mailstroom **regels**.
    
4. Selecteer het **+** pictogram (Toevoegen) en kies **Disclaimers toepassen**.
    
5. Geef een naam op voor de regel.
    
6. Selecteer **onder Deze regel toepassen**de optie **[Toepassen op alle berichten]**.
    
    > [!TIP]
    > [Meer informatie](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#Scoping) over het toepassen van voorwaarden als u niet wilt dat de vrijwaring wordt toegepast op alle berichten. (Dit scoping-artikel is voor Exchange Server, maar het is ook van toepassing op Microsoft 365.) 
  
7. Laat onder Ga als volgt te werk de optie **De vrijwaring toevoegen** ingeschakeld. 
    
8.  Selecteer **Tekst invoeren** en typ uw disclaimer. 
    
    > [!TIP]
    > [Meer informatie](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#FormatDisclaimer) over het opmaken van vrijwaringen. (Dit opmaakartikel is voor Exchange Server, maar ook van toepassing op Microsoft 365.) 

9. Selecteer **Er een selecteren** en kies **Wrap** als terugvaloptie. Klik op **OK**. Dit betekent dat als de vrijwaring niet kan worden toegevoegd vanwege versleuteling of een andere e-mailinstelling, deze wordt ingesloten in een berichtenvelop.
    
10. Leave **Audit this rule with severity level** selected. Then choose **Low**, **Medium**, or **High** to be used in the message log. 
    
11. Kies **Afdwingen** om de vrijwaring direct in te schakelen, tenzij u deze eerst wilt testen. 
    
12. Kies **Meer opties** om extra voorwaarden of uitzonderingen op te nemen. 
    
13. Kies **Opslaan** wanneer u klaar bent. 
    
## <a name="limitations-of-organization-wide-signatures"></a>Beperkingen van organisatiebrede handtekeningen

U het volgende niet doen met Microsoft 365-handtekeningen:
  
- De handtekening direct onder het laatste e-mailantwoord invoegen of doorsturen
    
- E-mailhandtekeningen aan de serverzijde weergeven in de mappen Verzonden items van gebruikers
    
- Afbeeldingen insluiten in e-mailhandtekeningen
    
- Regels overslaan die variabelen bevatten die niet kunnen worden bijgewerkt (bijvoorbeeld omdat de waarde niet is opgegeven voor een gebruiker)
    
Gebruik een hulpprogramma van derden om deze en andere mogelijkheden te verkrijgen. Doe een internet zoeken naar **e-mail handtekening software**. Een aantal van deze providers zijn Microsoft Gold Partners en hun software biedt deze mogelijkheden. 
  
## <a name="more-resources"></a>Meer informatie

- Zie [Disclaimers voor berichten, handtekeningen, voetteksten of kopteksten voor berichten in Microsoft 365](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers) voor informatie over het gebruik van PowerShell. 
    

