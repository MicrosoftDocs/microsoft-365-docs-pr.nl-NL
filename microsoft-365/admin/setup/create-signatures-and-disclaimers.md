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
description: Beheer e-mailhandtekeningen, inclusief juridische vrijwaringen of openbaarmakingsverklaringen voor alle e-mailberichten die uw organisatie binnenkomen of verlaten.
ms.openlocfilehash: f72d522c7dc592a7f719d716e22ecf726d00a6de
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635652"
---
# <a name="create-organization-wide-signatures-and-disclaimers"></a>Handtekeningen en vrijwaringen voor de hele organisatie maken

 U kunt e-mailhandtekeningen beheren door een e-mailhandtekening, wettelijke vrijwaring of openbaarmakingsverklaring toe te voegen aan de e-mailberichten die uw organisatie binnenkomen of verlaten. U kunt dit toepassen op alle binnenkomende en uitgaande berichten zoals hieronder wordt weergegeven. Of u kunt dit toepassen op bepaalde berichten, zoals berichten met specifieke woorden of tekstpatronen.

## <a name="watch-create-a-company-wide-email-signature"></a>Kijken: Een e-mailhandtekening voor het hele bedrijf maken
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf] 

Als je deze video nuttig vond, raadpleeg dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](../../business-video/index.yml).

## <a name="create-a-signature-that-applies-to-all-messages"></a>Een handtekening maken die van toepassing is op alle berichten

> [!TIP]
> Handtekeningen voor de hele organisatie worden 'vrijwaringen' genoemd, ongeacht wat ze bevatten. Ze kunnen bijvoorbeeld gewoon een handtekening zijn, of ook uw adres, wettelijke vrijwaring of andere informatie bevatten die u wilt.
    
::: moniker range="o365-worldwide"

Ga naar het beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

Ga naar het beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

Ga naar het beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a>.

::: moniker-end

1. Selecteer het startpictogram voor apps Het startpictogram voor ![ apps en selecteer vervolgens ](../../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) **Beheerder.**
   
    Kunt u de app die u zoekt niet vinden? Selecteer alle apps in het startlijst voor **apps** om een alfabetische lijst weer te geven met de apps die voor u beschikbaar zijn. Van daaruit kunt u zoeken naar een specifieke app. 
    
2. Selecteer **Beheercentra** en kies vervolgens **Exchange.**
    
3. Selecteer onder E-mailstroom de optie **Regels.**
    
4. Selecteer het **+** pictogram (Toevoegen) en kies **Vrijwaringen toepassen.**
    
5. Geef een naam op voor de regel.
    
6. Selecteer **onder Deze regel toepassen** de optie **[Toepassen op alle berichten]**.
    
    > [!TIP]
    > [Meer informatie](/Exchange/policy-and-compliance/mail-flow-rules/signatures#Scoping) over het toepassen van voorwaarden als u niet wilt dat de vrijwaring wordt toegepast op alle berichten. (Dit scoping-artikel is bedoeld Exchange Server, maar is ook van toepassing op Microsoft 365.) 
  
7. Laat onder Ga als volgt te werk de optie **De vrijwaring toevoegen** ingeschakeld. 
    
8.  Selecteer **Tekst invoeren** en typ uw vrijwaring. 
    
    > [!TIP]
    > [Meer informatie](/Exchange/policy-and-compliance/mail-flow-rules/signatures#FormatDisclaimer) over het opmaken van vrijwaringen. (Dit opmaakartikel is bedoeld voor Exchange Server, maar is ook van toepassing op Microsoft 365.) 

9. Selecteer **Selecteer een optie** en kies **Terugloop** als een terugvaloptie. Klik op **OK**. Dit betekent dat als de vrijwaring niet kan worden toegevoegd vanwege versleuteling of een andere e-mailinstelling, deze wordt ingesloten in een berichtenvelop.
    
10. Laat **De regel controleren met niveau van ernst** ingeschakeld. Kies nu **Laag**, **Normaal** of **Hoog** voor gebruik in het berichtenlogboek. 
    
11. Kies **Afdwingen** om de vrijwaring direct in te schakelen, tenzij u deze eerst wilt testen. 
    
12. Kies **Meer opties** om extra voorwaarden of uitzonderingen op te nemen. 
    
13. Kies **Opslaan** wanneer u klaar bent. 
    
## <a name="limitations-of-organization-wide-signatures"></a>Beperkingen van handtekeningen voor de hele organisatie

U kunt het volgende niet doen bij het beheren van e-mailhandtekeningen in Microsoft 365:
  
- De handtekening rechtstreeks invoegen onder het meest recente e-mailbericht beantwoorden of doorsturen
    
- E-mailhandtekeningen op de server weergeven in de mappen Verzonden items van gebruikers
    
- Afbeeldingen insluiten in e-mailhandtekeningen
    
- Regels overslaan die variabelen bevatten die niet kunnen worden bijgewerkt (bijvoorbeeld omdat de waarde niet is opgegeven voor een gebruiker)
    
Gebruik een hulpprogramma van derden om deze en andere mogelijkheden te verkrijgen voor het beheren van e-mailhandtekeningen. Zoek op internet naar software **voor e-mailhandtekeningen.** Een aantal van deze providers zijn Microsoft Gold Partners en hun software biedt deze mogelijkheden. 
  
## <a name="more-resources"></a>Meer informatie

Zie Bericht [disclaimers, handtekeningen, voetteksten](/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers)of kopteksten voor de hele organisatie in Exchange Online.

## <a name="related-content"></a>Verwante onderwerpen

[E-mail en contactpersonen](migrate-email-and-contacts-admin.md) migreren naar Microsoft 365 (video)\
[Gebruikers-e-mailinstellingen](../email/office-365-user-email-settings.md) (artikel)\
[Overzicht van het Microsoft 365-beheercentrum](../../business-video/admin-center-overview.md) (video)

