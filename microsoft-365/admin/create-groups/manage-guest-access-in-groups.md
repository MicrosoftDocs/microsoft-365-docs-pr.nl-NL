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
description: Informatie over het toevoegen van gasten aan een Microsoft 365-groep, het weergeven van gastgebruikers en het gebruik van PowerShell om gasttoegang te bepalen.
ms.openlocfilehash: 9a713684bb9a2401316dbb3289115be19b220cff
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453655"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Gasttoegang beheren in Microsoft 365-groepen

Gasttoegang voor Microsoft 365-groepen is standaard ingeschakeld voor uw organisatie. Beheerders kunnen bepalen of gasttoegang tot groepen moet worden toegestaan voor de hele organisatie of voor afzonderlijke groepen.

Wanneer deze is ingeschakeld, kunnen groepsleden gastgebruikers via de webversie van Outlook uitnodigen voor een Microsoft 365-groep. Uitnodigingen worden ter goedkeuring verzonden naar de groepseigenaar.

Nadat de gastgebruiker is goedgekeurd, wordt deze toegevoegd aan de adreslijst en de groep.

> [!Note]
> Yammer Enterprise-netwerken in de native modus of de [geo van](https://go.microsoft.com/fwlink/?linkid=2107357) de EU ondersteunen geen netwerk gasten.
> Met Microsoft 365 verbonden Yammer-groepen worden momenteel geen gasttoegang ondersteund, maar u kunt niet-verbonden, externe groepen maken in uw Yammer-netwerk. Zie [Externe groepen maken en beheren in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) voor instructies.

Gasttoegang in groepen wordt vaak gebruikt als onderdeel van een breder scenario met SharePoint of Teams. Deze services hebben hun eigen instellingen voor het delen van gasten. Voor volledige instructies voor het instellen van delen van gasten in groepen, SharePoint en Teams, gaat u naar:

- [Samenwerken met gasten op een site](../../solutions/collaborate-in-site.md)
- [Samenwerken met gasten in een team](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Gasttoegang voor groepen beheren

Als u gasttoegang in groepen wilt in- of uitschakelen, kunt u dit doen in het Microsoft 365-beheercentrum.

1. Ga in het beheercentrum naar **Alle instellingen** van de organisatie tonen en selecteer \>  \>  **Microsoft 365-groepen**  op het tabblad Services.
  
2. Kies op **de pagina Microsoft 365-groepen** of u personen buiten uw organisatie toegang wilt geven tot groepsbronnen of dat groepseigenaren personen van buiten uw organisatie aan groepen willen toevoegen.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Gasten toevoegen aan een Microsoft 365-groep vanuit het beheercentrum

Als de gast al bestaat in uw adreslijst, kunt u deze toevoegen aan uw groepen vanuit het Microsoft 365-beheercentrum. (Groepen met dynamisch lidmaatschap moeten worden [beheerd in Azure Active Directory.)](https://docs.microsoft.com/azure/active-directory/enterprise-users/groups-create-rule)
  
1. Ga in het beheercentrum naar de pagina  >  **Groepen.**
  
2. Klik op de groep aan wie u de gast wilt toevoegen en selecteer **Alle leden weergeven** en beheren op het **tabblad** Leden. 
  
4. Selecteer **Leden toevoegen** en kies de naam van de gast die u wilt toevoegen.
    
5. Kies **Opslaan**.

Als u een gast rechtstreeks aan de adreslijst wilt toevoegen, kunt u [B2B-samenwerkingsgebruikers](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator)voor Azure Active Directory toevoegen in de Azure Portal.

Als u de gegevens van een gast wilt bewerken, kunt u de profielgegevens van een gebruiker toevoegen of [bijwerken met Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

## <a name="see-also"></a>Zie ook

[Gastgebruikers uit een specifieke groep blokkeren](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[Groepslidmaatschap beheren in het Microsoft 365-beheercentrum](add-or-remove-members-from-groups.md)
  
[Azure Active Directory-toegangsbeoordelingen](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
