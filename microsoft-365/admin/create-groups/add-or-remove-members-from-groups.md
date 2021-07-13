---
title: Leden toevoegen aan of verwijderen uit Microsoft 365 groepen
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
ms.assetid: e186d224-a324-4afa-8300-0e4fc0c3000a
description: Meer informatie over het toevoegen van een lid aan een groep, het verwijderen van leden uit de groep en het beheren van de status van groepseigenaar in de Microsoft 365-beheercentrum.
ms.openlocfilehash: 7eaa74a53ac5f27d801d1cf16c9af035c63c68b1
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393761"
---
# <a name="add-or-remove-members-from-microsoft-365-groups-using-the-admin-center"></a>Leden toevoegen of verwijderen uit Microsoft 365 groepen met behulp van het beheercentrum

In Microsoft 365 maken groepsleden meestal hun eigen groepen, voegen ze zichzelf toe aan groepen die ze willen deelnemen of worden ze uitgenodigd door groepseigenaars. Als groepseigenschap verandert of als u bepaalt dat een lid moet worden toegevoegd of verwijderd, kunt u als beheerder deze wijziging ook aanbrengen. Alleen een globale beheerder, Exchange beheerder, beheerder van groepen of gebruikersbeheerder kan deze wijzigingen aanbrengen. [Wat is een Microsoft 365 groep?](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

> [!TIP]
> Als u geen beheerder bent, kunt u [leden toevoegen of verwijderen met behulp van Outlook](https://support.microsoft.com/office/3b650f4a-5c9b-4f94-a1bb-0cca4b1091de).
  
## <a name="add-a-member-to-a-group-in-the-admin-center"></a>Een lid toevoegen aan een groep in het beheercentrum

1. Ga in het beheercentrum naar de pagina [**Actieve groepen.**](https://admin.microsoft.com/Adminportal/Home?#/groups)  

2. Klik op een groepsnaam.

3. Selecteer in het detailvenster op het tabblad **Leden** **de** optie Alle leden weergeven en beheren en selecteer vervolgens **Leden toevoegen.**

4. Zoek of selecteer de naam van het lid dat u wilt toevoegen.

5. Kies **Opslaan**.

## <a name="add-a-group-to-a-member-in-the-admin-center"></a>Een groep toevoegen aan een lid in het beheercentrum

1. Ga in het beheercentrum naar de pagina [**Actieve gebruikers.**](https://admin.microsoft.com/Adminportal/Home?#/users)  

2. Klik op een gebruiker.

3. Selecteer groepen beheren in het detailvenster op het tabblad **Account.** 

4. Zoek of selecteer de naam van de groep die u wilt toevoegen.

5. Kies **Opslaan**.

## <a name="remove-a-member-from-a-group-in-the-admin-center"></a>Een lid verwijderen uit een groep in het beheercentrum

> [!NOTE]
> Wanneer u een lid uit een privégroep verwijdert, duurt het 5 minuten voordat de persoon is geblokkeerd uit de groep.

1. Ga in het beheercentrum naar de pagina [**Actieve groepen.**](https://admin.microsoft.com/Adminportal/Home?#/groups)  

2. Klik op een groepsnaam.

3. Selecteer in het detailvenster op het tabblad **Leden** de optie **Alle leden weergeven en beheren.**

4. Selecteer de X naast het lid dat u wilt verwijderen.

5. Selecteer **Opslaan om** het lid te verwijderen.

## <a name="manage-group-owner-status"></a>Status van groepseigenaar beheren

Standaard is de maker van de groep de groepseigenaar. Vaak heeft een groep meerdere eigenaren als back-upondersteuning of om andere redenen. Leden kunnen worden gepromoveerd naar de status van eigenaar. Eigenaren kunnen worden gedegradeerd naar de lidstatus.
  
### <a name="promote-a-member-to-owner-status-in-the-admin-center"></a>Een lid promoveren naar de status van eigenaar in het beheercentrum

1. Ga in het beheercentrum naar de pagina [**Actieve groepen.**](https://admin.microsoft.com/Adminportal/Home?#/groups)  

2. Klik op een groepsnaam.

3. Selecteer in het detailvenster op het tabblad **Leden** de optie **Alle eigenaren weergeven en beheren.**

4. Selecteer **Eigenaren toevoegen.**

5. Schakel het selectievakje in naast de naam van het lid dat u wilt toevoegen.

6. Selecteer **Opslaan** en vervolgens **Sluiten.**

### <a name="remove-owner-status-in-the-admin-center"></a>Eigenaarstatus verwijderen in het beheercentrum

1. Ga in het beheercentrum naar de pagina [**Actieve groepen.**](https://admin.microsoft.com/Adminportal/Home?#/groups)  

2. Klik op een groepsnaam.

3. Selecteer in het detailvenster op het tabblad **Leden** de optie **Alle eigenaren weergeven en beheren.**

4. Selecteer de X naast de naam van de eigenaar.

5. Kies **Opslaan**.

## <a name="next-steps"></a>Volgende stappen

- [Groepen beheren in Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal): zie de sectie Hoe kan ik het lidmaatschap van een groep dynamisch beheren?

- Als u honderden of duizenden gebruikers wilt toevoegen aan groepen, gebruikt u [de Add-UnifiedGroupLinks.](/powershell/module/exchange/add-unifiedgrouplinks)

- [Een nieuwe eigenaar toewijzen aan een groep zonder eigenaar](https://support.microsoft.com/office/86bb3db6-8857-45d1-95c8-f6d540e45732)

## <a name="related-content"></a>Verwante inhoud

[Distributielijsten upgraden naar Microsoft 365 groepen in Outlook](../manage/upgrade-distribution-lists.md) (artikel)\
[Waarom moet u uw distributielijsten upgraden](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188) naar groepen in Outlook (artikel)\
[Gasttoegang beheren in Microsoft 365 groepen](manage-guest-access-in-groups.md) (artikel)\
[Beheer Microsoft 365 groepen met PowerShell:](../../enterprise/manage-microsoft-365-groups-with-powershell.md)in dit artikel wordt u kennis laten maken met belangrijke cmdlets en worden voorbeelden (artikel)\
[Microsoft 365 naamgevingsbeleid voor groepen](../../solutions/groups-naming-policy.md) (artikel)