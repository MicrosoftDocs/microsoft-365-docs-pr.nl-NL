---
title: Handtekeningen en disclaimers voor de gehele organisatie maken
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2d75860f-c527-4352-a7f6-73eba54c0c72
description: Meer informatie over het beheren van e-mail handtekeningen, waaronder juridische vrijwarings-of informatieoverzichten, voor alle e-mailberichten die u invoert of verlaat uw organisatie.
ms.openlocfilehash: 9e438b42eb95dced4c3b99d21c66011365b180c9
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906499"
---
# <a name="create-organization-wide-signatures-and-disclaimers"></a>Handtekeningen en disclaimers voor de gehele organisatie maken

 U kunt e-mail handtekeningen beheren door een e-mail handtekening, een juridische disclaimer of een beschrijving toe te voegen aan de e-mailberichten waarin u uw organisatie typt of verlaat. U kunt dit toepassen op alle binnenkomende en uitgaande berichten zoals hieronder wordt weergegeven. Of u kunt dit toepassen op bepaalde berichten, zoals berichten met specifieke woorden of tekstpatronen.

 Bekijk een korte video over het maken van een e-mail handtekening in het hele bedrijf. <br><br>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf] 

Als je deze video nuttig vond, raadpleeg dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="create-a-signature-that-applies-to-all-messages"></a>Een handtekening maken die van toepassing is op alle berichten

> [!TIP]
> Handtekeningen voor de hele organisatie worden verweringen genoemd, ongeacht wat ze bevatten. Ze kunnen bijvoorbeeld een handtekening zijn, maar ook uw adres, juridische vrijwaring of andere informatie.
    
::: moniker range="o365-worldwide"

Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a>.

::: moniker-end

1. Selecteer het pictogram van het startprogramma voor apps in het startprogramma voor ![ apps ](../../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) en selecteer vervolgens **beheerder**.
   
    Kunt u de app die u zoekt niet vinden? Selecteer in het startprogramma voor **apps alle apps** om een alfabetische lijst weer te geven van de apps die voor u beschikbaar zijn. Van daaruit kunt u zoeken naar een specifieke app. 
    
2. Selecteer **beheer centra** en kies vervolgens **Exchange**.
    
3. Selecteer onder e-mail stroom de optie **regels**.
    
4. Selecteer het **+** pictogram (toevoegen) en kies **vrijwaringen toepassen**.
    
5. Geef een naam op voor de regel.
    
6. Selecteer onder **deze regel toepassen de** optie **[toepassen op alle berichten]**.
    
    > [!TIP]
    > [Meer informatie](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#Scoping) over het toepassen van voorwaarden als u niet wilt dat de vrijwaring wordt toegepast op alle berichten. (Dit artikel in de bereik functie is voor Exchange Server, maar is ook van toepassing op Microsoft 365.) 
  
7. Laat onder Ga als volgt te werk de optie **De vrijwaring toevoegen** ingeschakeld. 
    
8.  Selecteer **tekst invoeren** en typ de vrijwaring. 
    
    > [!TIP]
    > [Meer informatie](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#FormatDisclaimer) over het opmaken van vrijwaringen. (Dit opmaak artikel is bedoeld voor Exchange Server, maar is ook van toepassing op Microsoft 365.) 

9. Selecteer **er een** en kies de optie **laten teruglopen** als terugval. Klik op **OK**. Dit betekent dat als de vrijwaring niet kan worden toegevoegd vanwege versleuteling of een andere e-mailinstelling, deze wordt ingesloten in een berichtenvelop.
    
10. Laat **De regel controleren met niveau van ernst** ingeschakeld. Kies nu **Laag** , **Normaal** of **Hoog** voor gebruik in het berichtenlogboek. 
    
11. Kies **Afdwingen** om de vrijwaring direct in te schakelen, tenzij u deze eerst wilt testen. 
    
12. Kies **Meer opties** om extra voorwaarden of uitzonderingen op te nemen. 
    
13. Kies **Opslaan** wanneer u klaar bent. 
    
## <a name="limitations-of-organization-wide-signatures"></a>Beperkingen van handtekeningen voor de gehele organisatie

U kunt niet het volgende doen wanneer u e-mail handtekeningen beheert in Microsoft 365:
  
- De handtekening direct invoegen onder het laatste antwoord op de e-mail of doorsturen
    
- E-mail handtekeningen aan serverzijde weergeven in mappen met verzonden items van gebruikers
    
- Afbeeldingen insluiten in e-mail handtekeningen
    
- Regels overslaan die variabelen bevatten die niet kunnen worden bijgewerkt (bijvoorbeeld omdat de waarde niet is opgegeven voor een gebruiker)
    
U kunt deze en andere mogelijkheden voor het beheren van e-mail handtekeningen gebruiken in een programma van derden. Voer Internet zoeken naar software voor **e-mail handtekeningen**. Een aantal van deze providers is Microsoft Gold partners en de software biedt deze mogelijkheden. 
  
## <a name="more-resources"></a>Meer informatie

- Zie voor meer informatie over het gebruik van PowerShell voor informatie over de [gehele organisatie, handtekeningen, voetteksten of kopteksten in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers) .