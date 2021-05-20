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
description: Meer informatie over het toevoegen van gasten aan een Microsoft 365 groep, het weergeven van gast gebruikers en het gebruik van PowerShell om de toegang van gasten te beheren.
ms.openlocfilehash: c52f0094e724040b71d5d72cded049fed57e3969
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571935"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Gasttoegang beheren in Microsoft 365 groepen

Gasttoegang voor Microsoft 365 groepen is standaard ingeschakeld voor uw organisatie. Beheerders kunnen bepalen of gasten toegang moeten krijgen tot groepen voor hun hele organisatie of voor afzonderlijke groepen.

Wanneer deze is ingeschakeld, kunnen groepsleden gastgebruikers uitnodigen voor een Microsoft 365 groep via Outlook op internet. Uitnodigingen worden ter goedkeuring naar de groepseigenaar gestuurd.

Na goedkeuring wordt de gastgebruiker toegevoegd aan de map en de groep.

> [!Note]
> Yammer Enterprise netwerken die zich in de native modus of de [EU Geo](/yammer/manage-security-and-compliance/manage-data-compliance) bevinden, ondersteunen geen netwerkgasten.
> Microsoft 365 Verbonden Yammer groepen bieden momenteel geen ondersteuning voor gasttoegang, maar u kunt wel niet-verbonden, externe groepen maken in uw Yammer netwerk. Zie [Externe groepen maken en beheren in Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) voor instructies.

Gasttoegang in groepen wordt vaak gebruikt als onderdeel van een breder scenario met SharePoint of Teams. Deze services hebben hun eigen instellingen voor het delen van gasten. Zie voor volledige instructies voor het instellen van het delen van gasten tussen groepen, SharePoint en Teams:

- [Samenwerken met gasten op een site](../../solutions/collaborate-in-site.md)
- [Samenwerken met gasten in een team](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Gasttoegang voor groepen beheren

Als u gasttoegang in groepen wilt in- of uitschakelen, kunt u dit doen in het Microsoft 365-beheercentrum.

1. Ga in het beheercentrum naar **Alle** \> **Instellingen** \> **organisatie-instellingen** weergeven en selecteer op het tabblad **Services** **Microsoft 365 groepen**.
  
2. Kies **op** de pagina Microsoft 365 Groepen of u mensen buiten uw organisatie toegang wilt geven tot groepsresources of dat groepseigenaren mensen buiten uw organisatie aan groepen willen toevoegen.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Gasten toevoegen aan een Microsoft 365 groep vanuit het beheercentrum

Als de gast al in uw map bestaat, kunt u deze toevoegen aan uw groepen vanuit het Microsoft 365-beheercentrum. (Groepen met een dynamisch lidmaatschap moeten [worden beheerd in Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)
  
1. Ga in het beheercentrum naar de pagina **Groepen**  >  **groepen.**
  
2. Klik op de groep waaraan u de gast wilt toevoegen en selecteer **Alle leden weergeven en beheren** op het tabblad **Leden.** 
  
4. Selecteer **Leden toevoegen** en kies de naam van de gast die u wilt toevoegen.
    
5. Selecteer **Opslaan**.

Als u een gast rechtstreeks aan de directory wilt toevoegen, kunt u [Azure Active Directory B2B-samenwerkings gebruikers toevoegen in de Azure Portal](/azure/active-directory/b2b/add-users-administrator).

Als u de gegevens van een gast wilt bewerken, kunt u [de profielgegevens](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)van een gebruiker toevoegen of bijwerken met behulp van Azure Active Directory .

## <a name="related-content"></a>Verwante onderwerpen

[Gastgebruikers uit een specifieke groep blokkeren](../../solutions/per-group-guest-access.md) (artikel)

[Groepslidmaatschap beheren in het Microsoft 365-beheercentrum](add-or-remove-members-from-groups.md) (artikel)
  
[Azure Active Directory toegang tot beoordelingen](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (artikel)

[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (artikel)