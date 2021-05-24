---
title: Gasttoegang beheren in Microsoft 365 groepen
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
description: Lees hoe u gasten kunt toevoegen aan een Microsoft 365 groep, gastgebruikers kunt bekijken en PowerShell kunt gebruiken om gasttoegang te bepalen.
ms.openlocfilehash: 00a6353f02ae7f3675961c3ee2ee31e3715652f2
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635760"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Gasttoegang beheren in Microsoft 365 groepen

Standaard is gasttoegang voor Microsoft 365 groepen ingeschakeld voor uw organisatie. Beheerders kunnen bepalen of gasttoegang tot groepen moet worden toegestaan voor hun hele organisatie of voor afzonderlijke groepen.

Wanneer deze is ingeschakeld, kunnen groepsleden gastgebruikers uitnodigen voor een Microsoft 365 groep via Outlook web. Uitnodigingen worden ter goedkeuring naar de groepseigenaar verzonden.

Wanneer deze is goedgekeurd, wordt de gastgebruiker toegevoegd aan de adreslijst en de groep.

> [!Note]
> Yammer Enterprise netwerken die zich in de autochtone modus of de [EU-geo](/yammer/manage-security-and-compliance/manage-data-compliance) hebben, bieden geen ondersteuning voor netwerkgasten.
> Microsoft 365 Verbonden Yammer groepen bieden momenteel geen ondersteuning voor gasttoegang, maar u kunt niet-verbonden, externe groepen maken in uw Yammer netwerk. Zie [Externe groepen maken en beheren in Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) voor instructies.

Gasttoegang in groepen wordt vaak gebruikt als onderdeel van een breder scenario met SharePoint of Teams. Deze services hebben hun eigen instellingen voor het delen van gasten. Zie voor volledige instructies voor het instellen van het delen van gasten in groepen, SharePoint en Teams:

- [Samenwerken met gasten op een site](../../solutions/collaborate-in-site.md)
- [Samenwerken met gasten in een team](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Gasttoegang voor groepen beheren

Als u gasttoegang in groepen wilt in- of uitschakelen, kunt u dit doen in het Microsoft 365 beheercentrum.

1. Ga in het beheercentrum naar **Alle** organisatie-instellingen Instellingen en selecteer op het tabblad \>  \>  **Services** **Microsoft 365 groepen.**
  
2. Kies op **Microsoft 365** pagina Groepen of u personen buiten uw organisatie toegang wilt geven tot groepsbronnen of dat groepseigenaren personen buiten uw organisatie aan groepen willen toevoegen.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Gasten toevoegen aan een Microsoft 365 vanuit het beheercentrum

Als de gast al aanwezig is in uw adreslijst, kunt u deze toevoegen aan uw groepen vanuit het Microsoft 365 beheercentrum. (Groepen met dynamisch lidmaatschap moeten worden [beheerd in](/azure/active-directory/enterprise-users/groups-create-rule)Azure Active Directory .)
  
1. Ga in het beheercentrum naar de pagina  >  **Groepen groepen.**
  
2. Klik op de groep aan wie u de gast wilt toevoegen en selecteer Alle leden weergeven en **beheren** op **het tabblad** Leden. 
  
4. Selecteer **Leden toevoegen** en kies de naam van de gast die u wilt toevoegen.
    
5. Selecteer **Opslaan**.

Als u een gast rechtstreeks aan de adreslijst wilt toevoegen, kunt u Azure Active Directory [B2B-samenwerkingsgebruikers toevoegen in de Azure-portal.](/azure/active-directory/b2b/add-users-administrator)

Als u de gegevens van een gast wilt bewerken, kunt u de profielgegevens van een gebruiker toevoegen of bijwerken met behulp [van Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

## <a name="related-content"></a>Verwante onderwerpen

[Gastgebruikers blokkeren uit een specifieke groep](../../solutions/per-group-guest-access.md) (artikel)\
[Groepslidmaatschap beheren in het Microsoft 365 -beheercentrum](add-or-remove-members-from-groups.md) (artikel)\
[Azure Active Directory toegang tot reviews](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (artikel)\
[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (artikel)