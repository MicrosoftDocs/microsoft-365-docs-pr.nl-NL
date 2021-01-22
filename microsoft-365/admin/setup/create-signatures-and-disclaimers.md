---
title: Handtekeningen en vrijwaringen voor de hele organisatie maken
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
- seo-marvel-may2020
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2d75860f-c527-4352-a7f6-73eba54c0c72
description: Lees hoe u e-mailhandtekeningen beheert, inclusief juridische vrijwaringen of openbaarmakingsverklaringen voor alle e-mailberichten die uw organisatie binnenkomen of verlaten.
ms.openlocfilehash: c8d63a11a75b9b53de9cabdf1f4baabc61cc3e42
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926916"
---
# <a name="create-organization-wide-signatures-and-disclaimers"></a>Handtekeningen en vrijwaringen voor de hele organisatie maken

 U kunt e-mailhandtekeningen beheren door een e-mailhandtekening, juridische vrijwaring of openbaarmakingsverklaring toe te voegen aan de e-mailberichten die uw organisatie binnenkomen of verlaten. U kunt dit toepassen op alle binnenkomende en uitgaande berichten zoals hieronder wordt weergegeven. Of u kunt dit toepassen op bepaalde berichten, zoals berichten met specifieke woorden of tekstpatronen.

 Bekijk een korte video over het maken van een e-mailhandtekening voor het hele bedrijf. <br><br>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf] 

Als je deze video nuttig vond, raadpleeg dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="create-a-signature-that-applies-to-all-messages"></a>Een handtekening maken die van toepassing is op alle berichten

> [!TIP]
> Handtekeningen voor de hele organisatie worden vrijwaringen genoemd, ongeacht wat deze bevatten. Ze kunnen bijvoorbeeld alleen een handtekening zijn of uw adres, juridische vrijwaring of andere informatie bevatten.
    
::: moniker range="o365-worldwide"

Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a>.

::: moniker-end

1. Selecteer het startpictogram voor apps Het startpictogram voor apps ![ en selecteer vervolgens ](../../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) **Beheerder.**
   
    Kunt u de app die u zoekt niet vinden? Selecteer alle apps in het start programma voor **apps** om een alfabetische lijst weer te geven met apps die voor u beschikbaar zijn. Van daaruit kunt u zoeken naar een specifieke app. 
    
2. Selecteer **beheercentra** en kies **Exchange.**
    
3. Selecteer Regels onder **E-mailstroom.**
    
4. Selecteer het **+** pictogram (Toevoegen) en kies **Vrijwaringen toepassen.**
    
5. Geef een naam op voor de regel.
    
6. Selecteer **onder Deze regel toepassen** de optie **[Op alle berichten toepassen].**
    
    > [!TIP]
    > [Meer informatie](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#Scoping) over het toepassen van voorwaarden als u niet wilt dat de vrijwaring wordt toegepast op alle berichten. (Dit artikel is bedoeld voor Exchange Server, maar is ook van toepassing op Microsoft 365.) 
  
7. Laat onder Ga als volgt te werk de optie **De vrijwaring toevoegen** ingeschakeld. 
    
8.  Selecteer **Tekst invoeren en** typ de vrijwaring. 
    
    > [!TIP]
    > [Meer informatie](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#FormatDisclaimer) over het opmaken van vrijwaringen. (Dit opmaakartikel is bedoeld voor Exchange Server, maar is ook van toepassing op Microsoft 365.) 

9. Selecteer **Er een selecteren** en kies **Terugloop** als terugvaloptie. Klik op **OK**. Dit betekent dat als de vrijwaring niet kan worden toegevoegd vanwege versleuteling of een andere e-mailinstelling, deze wordt ingesloten in een berichtenvelop.
    
10. Laat **De regel controleren met niveau van ernst** ingeschakeld. Kies nu **Laag**, **Normaal** of **Hoog** voor gebruik in het berichtenlogboek. 
    
11. Kies **Afdwingen** om de vrijwaring direct in te schakelen, tenzij u deze eerst wilt testen. 
    
12. Kies **Meer opties** om extra voorwaarden of uitzonderingen op te nemen. 
    
13. Kies **Opslaan** wanneer u klaar bent. 
    
## <a name="limitations-of-organization-wide-signatures"></a>Beperkingen van handtekeningen voor de hele organisatie

U kunt het volgende niet doen bij het beheren van e-mailhandtekeningen in Microsoft 365:
  
- De handtekening rechtstreeks onder de meest recente e-mail beantwoorden of doorsturen
    
- E-mailhandtekeningen op de server weergeven in de mappen Verzonden items van gebruikers
    
- Afbeeldingen insluiten in e-mailhandtekeningen
    
- Regels overslaan die variabelen bevatten die niet konden worden bijgewerkt (bijvoorbeeld omdat de waarde niet is opgegeven voor een gebruiker)
    
Gebruik een hulpprogramma van derden om deze en andere mogelijkheden te verkrijgen voor het beheren van e-mailhandtekeningen. Voer een zoekopdracht op internet uit naar software **voor e-mailhandtekeningen.** Een aantal van deze providers zijn Microsoft Gold-partners en hun software biedt deze mogelijkheden. 
  
## <a name="more-resources"></a>Meer informatie

- Zie [vrijwaringen, handtekeningen,](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers) voetteksten of kopteksten voor berichten in de hele organisatie in Exchange Online voor informatie over het gebruik van PowerShell.