---
title: Gasttoegang beheren in Microsoft 365 groepen
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
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Meer informatie over het toevoegen van gasten aan een Microsoft 365-groep, het weergeven van gastgebruikers en het gebruik van PowerShell voor het beheer van gasttoegang.
ms.openlocfilehash: 640a35cbb1a3eb395453b224cadcf0d0db82fab8
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326517"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Gasttoegang beheren in Microsoft 365 groepen

Gasttoegang voor Microsoft 365-groepen is standaard ingeschakeld voor uw organisatie. Beheerders kunnen instellen dat gasttoegang voor groepen voor hun gehele organisatie of voor afzonderlijke groepen moet worden toegestaan.

Als u deze hebt ingeschakeld, kunnen groepsleden gastgebruikers uitnodigen voor een Microsoft 365-groep via de webversie van Outlook. Uitnodigingen worden verzonden naar de groepseigenaar voorgoed keuring.

Nadat de gastgebruiker is goedgekeurd, wordt deze toegevoegd aan de adreslijst en de groep.

> [!Note]
> Yammer Enterprise-netwerken in de native modus van de [Europese](https://go.microsoft.com/fwlink/?linkid=2107357) organisatie ondersteunen geen netwerkgasten.
> Microsoft 365 verbonden Yammer-groepen bieden momenteel geen ondersteuning voor gasttoegang, maar u kunt niet-verbonden externe groepen maken in uw Yammer-netwerk. Zie [externe groepen in Yammer maken en beheren](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) voor instructies.

Gasttoegang in groepen wordt vaak gebruikt als onderdeel van een breder scenario dat SharePoint of teams omvat. Deze services hebben hun eigen instellingen voor het delen van gasten. Voor uitgebreide instructies voor het instellen van gast delen in groepen, SharePoint en teams, raadpleegt u:

- [Samenwerken met gasten op een site](../../solutions/collaborate-in-site.md)
- [Met gasten samenwerken in een team](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Gasttoegang voor groepen beheren

Als u gasttoegang in groepen wilt in-of uitschakelen, kunt u dit doen in het Microsoft 365-Beheercentrum.

1. Ga in het Beheercentrum naar instellingen voor de organisatie van **alle instellingen weergeven** \> **Settings** \> **Org settings** en selecteer **Microsoft 365-groepen**op het tabblad **Services** .
  
2. Op de pagina **Microsoft 365 groepen** kiest u of u wilt dat mensen buiten uw organisatie de groeps resources kunnen gebruiken of Groepseigenaars mensen van buiten uw organisatie kunnen toevoegen aan groepen.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Gasten toevoegen aan een Microsoft 365-groep vanuit het Beheercentrum

Als de gast al bestaat in uw adreslijst, kunt u ze toevoegen aan uw groepen vanuit het Microsoft 365-Beheercentrum.
  
1. Ga in het Beheercentrum naar de pagina **groepen**  >  **groepen** .
  
2. Klik op de groep waaraan u de gast wilt toevoegen en selecteer **AllesWeergeven en leden weergeven** op het tabblad **leden** . 
  
4. Selecteer **leden toevoegen**en kies de naam van de gast die u wilt toevoegen.
    
5. Selecteer **Opslaan**.

Als u een gast rechtstreeks aan de adreslijst wilt toevoegen, voegt u [de gebruikers van Azure Active Directory B2B-samenwerking toe aan de Azure-Portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).

Als u de gegevens van een gast wilt bewerken, kunt u [de profielgegevens van een gebruiker toevoegen of bijwerken met behulp van Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

## <a name="see-also"></a>Zie ook

[Gastgebruikers blokkeren voor een bepaalde groep](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[Groepslidmaatschap beheren in het Microsoft 365-Beheercentrum](add-or-remove-members-from-groups.md)
  
[Azure Active Directory Access-beoordelingen](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
