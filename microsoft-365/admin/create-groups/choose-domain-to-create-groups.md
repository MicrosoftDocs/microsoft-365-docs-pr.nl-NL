---
title: Het domein kiezen dat u wilt gebruiken voor het maken van Microsoft 365-groepen
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: 'Leer het domein kiezen dat u wilt gebruiken voor het maken van Microsoft 365-groepen door e-mailadres beleidsregels te configureren met PowerShell. '
ms.openlocfilehash: 19caa4f4dfdef4895fa58f8bf5c198269844044f
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597375"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a>Het domein kiezen dat u wilt gebruiken voor het maken van Microsoft 365-groepen

 Sommige organisaties gebruiken afzonderlijke e-maildomeinen om verschillende onderdelen van het bedrijf te segmenteren. U kunt opgeven welk domein moet worden gebruikt wanneer uw gebruikers Microsoft 365-groepen maken.
  
Als uw organisatie vereist dat gebruikers hun groepen maken in andere domeinen dan het standaard geaccepteerde domein van uw bedrijf, kunt u dit toestaan door met PowerShell e-mailadresbeleidsregels (EAP's) te configureren.
  
Voordat u de PowerShell-cmdlets kunt uitvoeren, downloadt en installeert u een module waarmee u kunt communiceren met uw organisatie. Zie [Verbinding maken met Exchange Online via externe PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881)
  
## <a name="example-scenarios"></a>Voorbeelden van scenario's

Stel dat Contoso.com het primaire domein van uw bedrijf is. Het standaard geaccepteerde domein van uw organisatie is echter service.contoso.com. Dit houdt in dat groepen worden gemaakt in service.contoso.com (bijvoorbeeld jimsteam@service.contoso.com).
  
Stel dat er ook subdomeinen zijn geconfigureerd in uw organisatie. U wilt dat groepen ook in deze domeinen worden gemaakt:
  
- students.contoso.com voor studenten
    
- faculty.contoso.com voor faculteitsleden
    
In de volgende twee scenario's wordt uitgelegd hoe u dit kunt doen.
  
> [!NOTE]
> Als u meerdere EAP's hebt, worden deze in volgorde van prioriteit geëvalueerd. De waarde 1 betekent de hoogste prioriteit. Wanneer u EAP-overeenkomsten maakt, worden er geen verdere EAP geëvalueerd en worden de adressen die een stempel voor de groep bevinden, als volgt vastgesteld. Als er > geen Eap's overeenkomen met de opgegeven criteria, wordt de groep ingericht in het standaard geaccepteerd domein van de organisatie. Bekijk [Geaccepteerd domeinen beheren in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) voor meer informatie over het toevoegen van een geaccepteerd domein. 
  
### <a name="scenario-1"></a>Scenario 1

In het volgende voorbeeld ziet u hoe u in het groups.contoso.com-domein alle Microsoft 365-groepen in uw organisatie kunt inrichten.
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a>Scenario 2

Stel dat u wilt bepalen in welke subdomeinen Microsoft 365-groepen worden gemaakt. U wilt dat:
  
- Groepen die zijn gemaakt door studenten (gebruikers voor wie **afdeling** is ingesteld op **studenten**) in het students.groups.contoso.com-domein. Gebruik deze opdracht:
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- Groepen die zijn gemaakt door leden van de faculteit (gebruikers met een **afdeling** ingesteld op de **docenten of het e-mailadres Faculty.contoso.com)**) in het Faculty.groups.contoso.com-domein. Gebruik deze opdracht:
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- Alle andere gebruikers terechtkomen in het domein groups.contoso.com. Gebruik deze opdracht:
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a>E-mailadresbeleidsregels wijzigen

Gebruik de cmdlet Set-EmailAddressPolicy als u de prioriteit of e-mailadressjablonen voor een bestaand EAP wilt wijzigen.
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

Het wijzigen van een EAP heeft geen invloed op de groepen die al zijn ingericht.
  
## <a name="delete-email-address-policies"></a>E-mailadresbeleidsregels verwijderen

Gebruik de cmdlet Remove-EmailAddressPolicy om een EAP te verwijderen.
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

Het wijzigen van een EAP heeft geen invloed op de groepen die al zijn ingericht.
  
## <a name="hybrid-requirements"></a>Hybride vereisten

Als uw organisatie is geconfigureerd in een hybride scenario, raadpleegt [u Microsoft 365 groepen configureren met on-premises Exchange hybride](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups) om ervoor te zorgen dat uw organisatie voldoet aan de vereisten voor het maken van microsoft 365-groepen. 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a>Meer informatie over het gebruik van groepen voor e-mailadres beleidsregels:

Er zijn nog een paar dingen die u moet weten:
  
- De snelheid waarmee groepen worden gemaakt, hangt af van het aantal EAP's dat in uw organisatie is geconfigureerd.
    
- Beheerders en gebruikers kunnen ook domeinen wijzigen bij het maken van groepen.
    
- De groep gebruikers wordt bepaald met standaardquery's (Gebruikerseigenschappen), die al beschikbaar zijn. Zie [de Befilterbare eigenschappen voor de parameter-RecipientFilter](https://go.microsoft.com/fwlink/p/?LinkId=785918) voor ondersteunde filter-eigenschappen. 
    
- Als u geen EAP's voor groepen configureert, wordt het standaard geaccepteerd domein voor het maken van groepen geselecteerd.
    
- Als u een geaccepteerd domein verwijdert, moet u eerst de EAP's bijwerken, anders heeft dit invloed op de inrichting van de groep.
    
- Er kunnen maximaal 100 e-mailadresbeleidsregel voor een organisatie worden geconfigureerd.
    
## <a name="related-articles"></a>Verwante artikelen

[Een Microsoft 365-groep maken in het Beheercentrum](create-groups.md)
