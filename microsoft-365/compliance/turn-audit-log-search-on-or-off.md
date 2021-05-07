---
title: Zoeken in auditlogboeken in- of uitschakelen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
ms.custom: seo-marvel-apr2020
description: De zoekfunctie auditlogboek in- of uitschakelen in het beveiligings- & compliancecentrum om de mogelijkheid van beheerders om het auditlogboek te doorzoeken in of uit te schakelen.
ms.openlocfilehash: aecd1d47592b9a5e2f134b1d9db9ff203b815b18
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161957"
---
# <a name="turn-audit-log-search-on-or-off"></a>Zoeken in auditlogboeken in- of uitschakelen

Auditregistratie is standaard ingeschakeld voor Microsoft 365 en Office 365 bedrijfsorganisaties. Dit geldt ook voor organisaties met E3/G3- of E5/G5-abonnementen. Wanneer het zoeken in het auditlogboek in het compliancecentrum is ingeschakeld, worden activiteiten van gebruikers en beheerders van uw organisatie opgenomen in het auditlogboek en bewaard voor 90 dagen en maximaal één jaar, afhankelijk van de licentie die aan gebruikers is toegewezen. Het is echter mogelijk dat uw organisatie redenen heeft om geen controlelogboekgegevens op te nemen en te bewaren. In die gevallen kan een globale beheerder besluiten de controle in de Microsoft 365.

> [!IMPORTANT]
> Als u zoeken in auditlogboek in Microsoft 365 uit schakelen, kunt u de Office 365 Management Activity API of Azure Sentinel niet gebruiken om toegang te krijgen tot controlegegevens voor uw organisatie. Als u het zoeken naar auditlogboek uit wilt schakelen door de stappen in dit artikel uit te voeren, betekent dit dat er geen resultaten worden geretourneerd wanneer u in het auditlogboek zoekt met behulp van het Beveiligings- & Compliancecentrum of wanneer u de cmdlet **Search-UnifiedAuditLog** in Exchange Online PowerShell gebruikt. Dit betekent ook dat auditlogboeken niet beschikbaar zijn via de Office 365 Management Activity API of Azure Sentinel.
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a>Voordat u de zoekfunctie voor auditlogboek in- of uitschakelen

- U moet de rol Auditlogboeken in Exchange Online toegewezen krijgen om de zoekopdracht in het auditlogboek in of uit te schakelen in uw Microsoft 365 organisatie. Deze rol is standaard toegewezen aan de rollengroepen Compliancebeheer  en Organisatiebeheer op de pagina Machtigingen in het Exchange beheercentrum. Globale beheerders in Microsoft 365 zijn lid van de rollengroep Organisatiebeheer in Exchange Online. 
    
    > [!NOTE]
    > Gebruikers moeten machtigingen krijgen toegewezen in Exchange Online om de zoekfunctie voor auditlogboek in of uit te schakelen. Als u gebruikers de rol Auditlogboeken **toewijst** op de pagina Machtigingen in het Beveiligings- & Compliancecentrum, kunnen ze de zoekfunctie voor auditlogboeken niet in- of uitschakelen. De onderliggende cmdlet is namelijk een Exchange Online PowerShell-cmdlet. 
    
- Zie Het auditlogboek doorzoeken in het beveiligings- & compliancecentrum voor stapsgewijse instructies over het [doorzoeken van het auditlogboek.](search-the-audit-log-in-security-and-compliance.md) Zie Aan de slag met Microsoft 365 Management [API's](/office/office-365-management-api/get-started-with-office-365-management-apis)voor meer informatie over Microsoft 365 Management Activity API.

- Als u wilt controleren of zoeken in het auditlogboek is ingeschakeld, kunt u de volgende opdracht uitvoeren in Exchange Online PowerShell:

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    De waarde van  `True` voor de  _eigenschap UnifiedAuditLogIngestionEnabled_ geeft aan dat de zoekfunctie voor auditlogboek is ingeschakeld. 
    
## <a name="turn-on-audit-log-search"></a>Zoeken in auditlogboek in- en uit-

Als zoeken in auditlogboek niet is ingeschakeld voor uw organisatie, kunt u het in het compliancecentrum in- of Exchange Online PowerShell. Het kan enkele uren duren voordat u de zoekresultaten in het auditlogboek kunt retourneren.
  
### <a name="use-the-compliance-center-to-turn-on-audit-log-search"></a>Het compliancecentrum gebruiken om zoeken in auditlogboek in te zetten

1. [Ga naar het compliancecentrum](https://protection.office.com) en meld u aan.

2. Ga in het compliancecentrum naar **Search**  >  **Audit log search**.

   Als zoeken in auditlogboek niet is ingeschakeld voor uw organisatie, wordt er een banner weergegeven met de tekst dat auditing moet worden ingeschakeld om gebruikers- en beheerdersactiviteiten op te nemen.

3. Klik **op Controle in- en uit-**

    ![Klik op Controle in- en uit-](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    De banner wordt bijgewerkt om te zeggen dat het auditlogboek wordt voorbereid en dat u binnen een paar uur kunt zoeken naar activiteiten van gebruikers en beheerders.

### <a name="use-powershell-to-turn-on-audit-log-search"></a>PowerShell gebruiken om zoeken in auditlogboek in te zetten

1. [Verbinding maken powershell Exchange Online gebruiken](/powershell/exchange/connect-to-exchange-online-powershell)

2. Voer de volgende PowerShell-opdracht uit om zoeken in auditlogboek in te Office 365.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    Er wordt een bericht weergegeven met de melding dat het tot 60 minuten kan duren voordat de wijziging van kracht wordt.
  
## <a name="turn-off-audit-log-search"></a>Zoeken in auditlogboek uitschakelen

U moet powershell Exchange Online gebruiken om het zoeken naar auditlogboek uit te schakelen.
  
1. [Verbinding maken powershell Exchange Online gebruiken](/powershell/exchange/connect-to-exchange-online-powershell)

2. Voer de volgende PowerShell-opdracht uit om het zoeken naar auditlogboek uit te schakelen.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. Controleer na een tijdje of de zoekopdracht in het auditlogboek is uitgeschakeld (uitgeschakeld). U kunt dit op twee manieren doen:

    - Voer Exchange Online PowerShell de volgende opdracht uit:

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      De waarde van  `False` voor de  _eigenschap UnifiedAuditLogIngestionEnabled_ geeft aan dat zoeken in auditlogboek is uitgeschakeld. 

    - Ga in [het compliancecentrum](https://protection.office.com)naar **Search** \> **Audit log search**.

      Er wordt een banner weergegeven waarin wordt gezegd dat auditing moet worden ingeschakeld om gebruikers- en beheerdersactiviteit op te nemen.