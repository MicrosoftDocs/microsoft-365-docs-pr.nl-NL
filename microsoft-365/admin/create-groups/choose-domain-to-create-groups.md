---
title: Het domein kiezen dat u wilt gebruiken bij het maken van Microsoft 365-groepen
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: 'Lees het domein dat u wilt gebruiken bij het maken van Microsoft 365-groepen door het beleid voor e-mailadressen te configureren met PowerShell. '
ms.openlocfilehash: 1bc8a160ffc368bc4c66a5ac17ffcb203dc678f5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630621"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a>Het domein kiezen dat u wilt gebruiken bij het maken van Microsoft 365-groepen

 Sommige organisaties gebruiken afzonderlijke e-maildomeinen om verschillende onderdelen van het bedrijf te segmenteren. U opgeven welk domein moet worden gebruikt wanneer uw gebruikers Microsoft 365-groepen maken.
  
Als uw organisatie vereist dat gebruikers hun groepen maken in andere domeinen dan het standaard geaccepteerde domein van uw bedrijf, kunt u dit toestaan door met PowerShell e-mailadresbeleidsregels (EAP's) te configureren.
  
Voordat u de PowerShell-cmdlets uitvoeren, u een module downloaden en installeren waarmee u met uw organisatie praten. Zie [Verbinding maken met Exchange Online via externe PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881)
  
## <a name="example-scenarios"></a>Voorbeelden van scenario's

Stel dat Contoso.com het primaire domein van uw bedrijf is. Het standaard geaccepteerde domein van uw organisatie is echter service.contoso.com. Dit betekent dat groepen worden gemaakt in service.contoso.com (bijvoorbeeld jimsteam@service.contoso.com).
  
Stel dat er ook subdomeinen zijn geconfigureerd in uw organisatie. U wilt ook dat groepen in deze domeinen worden gemaakt:
  
- students.contoso.com voor studenten
    
- faculty.contoso.com voor faculteitsleden
    
In de volgende twee scenario's wordt uitgelegd hoe u dit kunt doen.
  
> [!NOTE]
> Als u meerdere EAP's hebt, worden deze in volgorde van prioriteit geëvalueerd. De waarde 1 betekent de hoogste prioriteit. Zodra een EAP overeenkomt, wordt er geen verdere EAP geëvalueerd en adressen die op de groep worden gestempeld, zijn volgens het overeenkomende EAP. > Als er geen EAP's overeenkomen met de opgegeven criteria, wordt de groep ingericht in het standaard geaccepteerde domein van de organisatie. Bekijk [Geaccepteerd domeinen beheren in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) voor meer informatie over het toevoegen van een geaccepteerd domein. 
  
### <a name="scenario-1"></a>Scenario 1

In het volgende voorbeeld ziet u hoe u alle Microsoft 365-groepen in uw organisatie in het domein groups.contoso.com inrichten.
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a>Scenario 2

Stel dat u wilt bepalen in welke subdomeinen Microsoft 365-groepen zijn gemaakt. U wilt dat:
  
- Groepen die zijn gemaakt door studenten (gebruikers die **afdeling** hebben ingesteld op **studenten)** in het students.groups.contoso.com domein. Gebruik deze opdracht:
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- Groepen die zijn gemaakt door faculteitsleden (gebruikers die **de afdeling** hebben ingesteld op faculteit **of e-mailadres faculty.contoso.com)**) in het domein faculty.groups.contoso.com. Gebruik deze opdracht:
    
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

Als uw organisatie is geconfigureerd in een hybride scenario, raadpleegt u [Microsoft 365-groepen configureren met on-premises Exchange-hybride](https://go.microsoft.com/fwlink/p/?LinkId=785430) om te controleren of uw organisatie voldoet aan de vereisten voor het maken van Microsoft 365-groepen. 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a>Aanvullende informatie over het gebruik van beleidsgroepen voor e-mailadressen:

Er zijn nog een paar dingen die u moet weten:
  
- De snelheid waarmee groepen worden gemaakt, hangt af van het aantal EAP's dat in uw organisatie is geconfigureerd.
    
- Beheerders en gebruikers kunnen ook domeinen wijzigen wanneer ze groepen maken.
    
- De groep gebruikers wordt bepaald met standaardquery's (Gebruikerseigenschappen), die al beschikbaar zijn. Controleer [Filterbare eigenschappen voor de parameter -RecipientFilter](https://go.microsoft.com/fwlink/p/?LinkId=785918) voor ondersteunde filterbare eigenschappen. 
    
- Als u geen EAP's voor groepen configureert, wordt het standaard geaccepteerd domein voor het maken van groepen geselecteerd.
    
- Als u een geaccepteerd domein verwijdert, moet u eerst de EAP's bijwerken, anders heeft dit invloed op de inrichting van de groep.
    
- Er kunnen maximaal 100 e-mailadresbeleidsregel voor een organisatie worden geconfigureerd.
    
## <a name="related-articles"></a>Verwante artikelen

[Een Microsoft 365-groep maken in het beheercentrum](create-groups.md)
