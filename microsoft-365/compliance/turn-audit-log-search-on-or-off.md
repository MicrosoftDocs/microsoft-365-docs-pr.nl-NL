---
title: Mobiele meldingen in- of uitschakelen
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
description: De zoekfunctie auditlogboek in- of uitschakelen in de Microsoft 365-compliancecentrum om beheerders in of uit te schakelen om het auditlogboek te doorzoeken.
ms.openlocfilehash: 7c55443eda9a99ff4ef153d8564fd9ac43fcc549
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105306"
---
# <a name="turn-auditing-on-or-off"></a>Mobiele meldingen in- of uitschakelen

Auditlogboekregistratie is standaard ingeschakeld voor organisaties met Microsoft 365 en Office 365 Enterprise. Dit geldt ook voor organisaties met een E3/G3- of E5/G5-abonnement. Wanneer de controle in het compliancecentrum is ingeschakeld, worden activiteiten van gebruikers en beheerders van uw organisatie opgenomen in het auditlogboek en bewaard voor 90 dagen en maximaal één jaar, afhankelijk van de licentie die aan gebruikers is toegewezen. Het is echter mogelijk dat uw organisatie redenen heeft om geen controlelogboekgegevens op te nemen en te bewaren. In die gevallen kan een globale beheerder besluiten de controle in de Microsoft 365.

> [!IMPORTANT]
> Als u auditing in Microsoft 365 uitschakelen, kunt u de Office 365 Management Activity API of Azure Sentinel niet gebruiken om toegang te krijgen tot controlegegevens voor uw organisatie. Als u auditing uitkeert door de stappen in dit artikel uit te voeren, worden er geen resultaten geretourneerd wanneer u in het auditlogboek zoekt met behulp van het Beveiligings- & Compliancecentrum of wanneer u de cmdlet **Search-UnifiedAuditLog** in Exchange Online PowerShell gebruikt. Dit betekent ook dat auditlogboeken niet beschikbaar zijn via de Office 365 Management Activity API of Azure Sentinel.
  
## <a name="before-you-turn-auditing-on-or-off"></a>Voordat u controle in- of uitschakelen

- U moet de rol Auditlogboeken toegewezen krijgen in Exchange Online auditing in of uit te schakelen in uw Microsoft 365 organisatie. Deze rol is standaard toegewezen aan de rollengroepen Compliancebeheer  en Organisatiebeheer op de pagina Machtigingen in het Exchange beheercentrum. Globale beheerders in Microsoft 365 zijn lid van de rollengroep Organisatiebeheer in Exchange Online. 

    > [!NOTE]
    > Aan gebruikers moeten machtigingen zijn toegewezen in Exchange Online controle in- of uitschakelen. Als u gebruikers de rol Auditlogboeken **toewijst** op de pagina Machtigingen in het Beveiligings- & Compliancecentrum, kunnen ze de controle niet in- of uitschakelen. De onderliggende cmdlet is namelijk een Exchange Online PowerShell-cmdlet.

- Zie Het auditlogboek doorzoeken in het beveiligings- & compliancecentrum voor stapsgewijse instructies over het [doorzoeken van het auditlogboek.](search-the-audit-log-in-security-and-compliance.md) Zie Aan de slag met Microsoft 365 Management [API's](/office/office-365-management-api/get-started-with-office-365-management-apis)voor meer informatie over Microsoft 365 Management Activity API.

- Als u wilt controleren of auditing is ingeschakeld, kunt u de volgende opdracht uitvoeren in Exchange Online PowerShell:

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    De waarde van  `True` voor de  _eigenschap UnifiedAuditLogIngestionEnabled_ geeft aan dat auditing is ingeschakeld. 

## <a name="turn-on-auditing"></a>Controle in- en uit-

Als auditing niet is ingeschakeld voor uw organisatie, kunt u deze in het compliancecentrum in- of Exchange Online PowerShell. Het kan enkele uren duren nadat u de controle hebt in- of uitgevoerd voordat u resultaten kunt retourneren wanneer u in het auditlogboek zoekt.
  
### <a name="use-the-compliance-center-to-turn-on-auditing"></a>Het compliancecentrum gebruiken om controle in te zetten

1. Ga naar <https://compliance.microsoft.com> en meld u aan.

2. Klik in het linkernavigatiedeelvenster Microsoft 365-compliancecentrum **op Alles weergeven** en klik vervolgens op **Controleren.**

   Als auditing niet is ingeschakeld voor uw organisatie, wordt er een banner weergegeven waarin u wordt gevraagd gebruikers- en beheerdersactiviteiten op te nemen.

   ![Banner op de pagina Controle](../media/AuditingBanner.png)

3. Klik op **de banner Start recording user and admin activity** banner.

   Het kan tot 60 minuten duren voordat de wijziging van kracht wordt.

### <a name="use-powershell-to-turn-on-auditing"></a>PowerShell gebruiken om controle in te zetten

1. [Verbinding maken powershell Exchange Online gebruiken](/powershell/exchange/connect-to-exchange-online-powershell)

2. Voer de volgende PowerShell-opdracht uit om auditing in te Office 365.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    Er wordt een bericht weergegeven met de melding dat het tot 60 minuten kan duren voordat de wijziging van kracht wordt.
  
## <a name="turn-off-auditing"></a>Controle uitschakelen

U moet de Exchange Online PowerShell gebruiken om auditing uit te schakelen.
  
1. [Verbinding maken powershell Exchange Online gebruiken](/powershell/exchange/connect-to-exchange-online-powershell)

2. Voer de volgende PowerShell-opdracht uit om auditing uit te schakelen.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. Controleer na een tijdje of de controle is uitgeschakeld (uitgeschakeld). U kunt dit op twee manieren doen:

    - Voer Exchange Online PowerShell de volgende opdracht uit:

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      De waarde van  `False` voor de  _eigenschap UnifiedAuditLogIngestionEnabled_ geeft aan dat auditing is uitgeschakeld.

    - Ga naar de **pagina Audit** in de Microsoft 365-compliancecentrum.

      Als auditing niet is ingeschakeld voor uw organisatie, wordt er een banner weergegeven waarin u wordt gevraagd gebruikers- en beheerdersactiviteiten op te nemen.
