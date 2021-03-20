---
title: Gasttoegang beheren in Microsoft 365-groepen
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Lees hoe u gasten kunt toevoegen aan een Microsoft 365-groep, gastgebruikers kunt bekijken en PowerShell kunt gebruiken om gasttoegang te bepalen.
ms.openlocfilehash: 114fc1b5262f1632c7e7a8d1aa339c2470223288
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908604"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Gasttoegang beheren in Microsoft 365-groepen

Standaard is gasttoegang voor Microsoft 365-groepen ingeschakeld voor uw organisatie. Beheerders kunnen bepalen of gasttoegang tot groepen moet worden toegestaan voor hun hele organisatie of voor afzonderlijke groepen.

Wanneer deze is ingeschakeld, kunnen groepsleden gastgebruikers uitnodigen voor een Microsoft 365-groep via de webversie van Outlook. Uitnodigingen worden ter goedkeuring naar de groepseigenaar verzonden.

Wanneer deze is goedgekeurd, wordt de gastgebruiker toegevoegd aan de adreslijst en de groep.

> [!Note]
> Yammer Enterprise-netwerken in de autochtone modus of [de EU Geo](/yammer/manage-security-and-compliance/manage-data-compliance) ondersteunen geen netwerkgasten.
> Microsoft 365 Verbonden Yammer-groepen bieden momenteel geen ondersteuning voor gasttoegang, maar u kunt niet-verbonden, externe groepen maken in uw Yammer-netwerk. Zie [Externe groepen maken en beheren in Yammer voor](/yammer/work-with-external-users/create-and-manage-external-groups) instructies.

Gasttoegang in groepen wordt vaak gebruikt als onderdeel van een breder scenario met SharePoint of Teams. Deze services hebben hun eigen instellingen voor het delen van gasten. Zie voor volledige instructies voor het instellen van het delen van gasten in groepen, SharePoint en Teams:

- [Samenwerken met gasten op een site](../../solutions/collaborate-in-site.md)
- [Samenwerken met gasten in een team](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Gasttoegang voor groepen beheren

Als u gasttoegang in groepen wilt in- of uitschakelen, kunt u dit doen in het Microsoft 365-beheercentrum.

1. Ga in het beheercentrum naar **Alle instellingen** van instellingen voor organisaties tonen en selecteer microsoft \>  \>  **365-groepen** op het **tabblad** Services.
  
2. Kies op **de pagina Microsoft 365 Groepen** of u personen buiten uw organisatie toegang wilt geven tot groepsbronnen of dat groepseigenaren personen buiten uw organisatie aan groepen willen toevoegen.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Gasten toevoegen aan een Microsoft 365-groep vanuit het beheercentrum

Als de gast al aanwezig is in uw adreslijst, kunt u deze toevoegen aan uw groepen vanuit het Microsoft 365-beheercentrum. (Groepen met dynamisch lidmaatschap moeten worden [beheerd in Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)
  
1. Ga in het beheercentrum naar de pagina  >  **Groepen groepen.**
  
2. Klik op de groep aan wie u de gast wilt toevoegen en selecteer Alle leden weergeven en **beheren** op **het tabblad** Leden. 
  
4. Selecteer **Leden toevoegen** en kies de naam van de gast die u wilt toevoegen.
    
5. Kies **Opslaan**.

Als u een gast rechtstreeks aan de adreslijst wilt toevoegen, kunt u Azure Active Directory B2B-samenwerkingsgebruikers toevoegen [in de Azure-portal.](/azure/active-directory/b2b/add-users-administrator)

Als u de gegevens van een gast wilt bewerken, kunt u de profielgegevens van een gebruiker toevoegen of bijwerken [met Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

## <a name="see-also"></a>Zie ook

[Gastgebruikers uit een specifieke groep blokkeren](../../solutions/per-group-guest-access.md)

[Groepslidmaatschap beheren in het Microsoft 365-beheercentrum](add-or-remove-members-from-groups.md)
  
[Azure Active Directory-toegangsbeoordelingen](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](/powershell/module/azuread/set-azureaduser)