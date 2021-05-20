---
title: Kies het domein dat u wilt gebruiken bij het maken van Microsoft 365 groepen
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
recommendations: false
description: Informatie over het domein dat u wilt gebruiken bij het maken Microsoft 365 door e-mailadresbeleid te configureren met PowerShell.
ms.openlocfilehash: 4d620c3344f83f56afd05c00d78615331dd413ed
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583146"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a>Kies het domein dat u wilt gebruiken bij het maken van Microsoft 365 groepen

Sommige organisaties gebruiken afzonderlijke e-maildomeinen om verschillende onderdelen van het bedrijf te segmenteren. U kunt opgeven welk domein moet worden gebruikt wanneer uw gebruikers Microsoft 365 maken.
  
Als uw organisatie vereist dat gebruikers hun groepen maken in andere domeinen dan het standaard geaccepteerde domein van uw bedrijf, kunt u dit toestaan door met PowerShell e-mailadresbeleidsregels (EAP's) te configureren.

Voordat u de PowerShell-cmdlets kunt uitvoeren, downloadt en installeert u een module om met uw organisatie te praten. Zie [Verbinding maken met Exchange Online via externe PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)

## <a name="example-scenarios"></a>Voorbeeldscenario's

Stel dat Contoso.com het primaire domein van uw bedrijf is. Het standaard geaccepteerde domein van uw organisatie is echter service.contoso.com. Dit betekent dat groepen worden gemaakt in service.contoso.com (bijvoorbeeld jimsteam@service.contoso.com).
  
Stel dat er ook subdomeinen zijn geconfigureerd in uw organisatie. U wilt ook groepen maken in deze domeinen:
  
- students.contoso.com voor studenten
    
- faculty.contoso.com voor faculteitsleden
    
In de volgende twee scenario's wordt uitgelegd hoe u dit kunt doen.

> [!NOTE]
> Als u meerdere EAP's hebt, worden deze in volgorde van prioriteit geëvalueerd. De waarde 1 betekent de hoogste prioriteit. Wanneer een EAP overeenkomt, wordt er geen EAP meer geëvalueerd en worden adressen die op de groep worden gestempeld, volgens het overeenkomende EAP geëvalueerd. > Als er geen EPP's voldoen aan de opgegeven criteria, wordt de groep ingericht in het standaard geaccepteerde domein van de organisatie. Bekijk [Geaccepteerd domeinen beheren in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) voor meer informatie over het toevoegen van een geaccepteerd domein.
  
### <a name="scenario-1"></a>Scenario 1

In het volgende voorbeeld ziet u hoe u alle Microsoft 365 groepen in uw organisatie kunt inrichten in het groups.contoso.com domein.
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a>Scenario 2

Stel dat u wilt bepalen in welke subdomeinen Microsoft 365 groepen worden gemaakt. U wilt dat:
  
- Groepen die zijn gemaakt door leerlingen/studenten (gebruikers die **afdeling** hebben ingesteld op **Studenten)** in het students.groups.contoso.com domein. Gebruik deze opdracht:
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- Groepen die zijn gemaakt door  faculteitsleden (gebruikers die afdeling hebben ingesteld op Faculteit of e-mailadres bevat **faculty.contoso.com)** in het faculty.groups.contoso.com domein. Gebruik deze opdracht:
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- Groepen die door iemand anders zijn gemaakt, worden gemaakt in het groups.contoso.com domein. Gebruik deze opdracht:
    
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

Als uw organisatie is geconfigureerd in een hybride scenario, raadpleegt u Microsoft 365-groepen configureren met [on-premises Exchange hybride](/exchange/hybrid-deployment/set-up-microsoft-365-groups) om ervoor te zorgen dat uw organisatie voldoet aan de vereisten voor het maken van Microsoft 365 groepen. 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a>Aanvullende informatie over het gebruik van e-mailadresbeleidsgroepen:

Er zijn nog een paar dingen die u moet weten:
  
- De snelheid waarmee groepen worden gemaakt, hangt af van het aantal EAP's dat in uw organisatie is geconfigureerd.
    
- Beheerders en gebruikers kunnen ook domeinen wijzigen wanneer ze groepen maken.
    
- De groep gebruikers wordt bepaald met standaardquery's (Gebruikerseigenschappen), die al beschikbaar zijn. Bekijk [Filterbare eigenschappen voor de parameter -RecipientFilter](/powershell/exchange/recipientfilter-properties) voor ondersteunde filterbare eigenschappen. 
    
- Als u geen EAP's voor groepen configureert, wordt het standaard geaccepteerd domein voor het maken van groepen geselecteerd.
    
- Als u een geaccepteerd domein verwijdert, moet u eerst de EAP's bijwerken, anders heeft dit invloed op de inrichting van de groep.
    
- Er kunnen maximaal 100 e-mailadresbeleidsregel voor een organisatie worden geconfigureerd.
    
## <a name="related-content"></a>Verwante inhoud

[Planning van samenwerkingsbeheer stapsgewijs](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step) (artikel)

[Uw samenwerkingsbeheerplan maken](collaboration-governance-first.md) (artikel)

[Een groep Microsoft 365 maken in het beheercentrum](../admin/create-groups/create-groups.md) (artikel)