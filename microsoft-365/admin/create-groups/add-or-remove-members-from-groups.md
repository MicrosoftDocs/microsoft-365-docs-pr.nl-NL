---
title: Leden toevoegen aan of verwijderen uit Microsoft 365-groepen
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
ms.assetid: e186d224-a324-4afa-8300-0e4fc0c3000a
description: Leer hoe u een lid aan een groep toevoegt, lid uit een groep verwijdert en de status van groepseigenaar beheert in het Microsoft 365-Beheercentrum.
ms.openlocfilehash: 34c026bced5563e07a1ae0d13f4c691cfaf3f624
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663241"
---
# <a name="add-or-remove-members-from-microsoft-365-groups-using-the-admin-center"></a>Leden toevoegen aan of verwijderen uit Microsoft 365 groepen met behulp van het Beheercentrum

In Microsoft 365 worden groepsleden meestal hun eigen groepen gemaakt, toegevoegd aan groepen waaraan ze willen deelnemen, of die zijn uitgenodigd voor groepseigenaren. Als u wijzigingen aanbrengt in de groep of als u vaststelt dat er een lid moet worden toegevoegd of verwijderd, aangezien de beheerder u kunt wijzigen. Alleen globale beheerders, Exchange-beheerders, groepen beheerders of gebruikers beheerders kunnen deze wijzigingen aanbrengen. [Wat is een Microsoft 365-groep?](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

> [!TIP]
> Als u geen beheerder bent, kunt u [leden toevoegen of verwijderen met behulp van Outlook](https://support.microsoft.com/office/3b650f4a-5c9b-4f94-a1bb-0cca4b1091de).
  
## <a name="add-a-member-to-a-group-in-the-admin-center"></a>Een lid toevoegen aan een groep in het Beheercentrum

1. Ga in het Beheercentrum naar de pagina [**actieve groepen**](https://admin.microsoft.com/Adminportal/Home?#/groups) .  

2. Klik op de naam van een groep.

3. Ga in het deelvenster Details naar het tabblad **leden** , selecteer **AllesWeergeven en leden beheren**, en selecteer vervolgens **leden toevoegen**.

4. Zoek of selecteer de naam van het lid dat u wilt toevoegen.

5. Kies **Opslaan**.

## <a name="add-a-group-to-a-member-in-the-admin-center"></a>Een groep aan een lid toevoegen in het Beheercentrum

1. Ga naar de pagina [**actieve gebruikers**](https://admin.microsoft.com/Adminportal/Home?#/users) in het Beheercentrum.  

2. Klik op een gebruiker.

3. Selecteer in het deelvenster Details, op het tabblad **account** , de optie **groepen beheren**.

4. Zoek of selecteer de naam van de groep die u wilt toevoegen.

5. Kies **Opslaan**.

## <a name="remove-a-member-from-a-group-in-the-admin-center"></a>Een lid verwijderen uit een groep in het Beheercentrum

> [!NOTE]
> Wanneer u een lid uit een privégroep verwijdert, duurt het 5 minuten voordat die persoon wordt geblokkeerd in de groep.

1. Ga in het Beheercentrum naar de pagina [**actieve groepen**](https://admin.microsoft.com/Adminportal/Home?#/groups) .  

2. Klik op de naam van een groep.

3. Selecteer in het deelvenster Details, op het tabblad **leden** , de optie **AllesWeergeven en leden beheren**.

4. Selecteer de X naast het lid dat u wilt verwijderen.

5. Selecteer **Opslaan** om het lid te verwijderen.

## <a name="manage-group-owner-status"></a>De status van groepseigenaar beheren

Standaard is de maker van de groep de groepseigenaar. Vaak heeft een groep meerdere eigenaren als back-upondersteuning of om andere redenen. Leden kunnen worden gepromoveerd naar de status van eigenaar. Eigenaren kunnen worden gedegradeerd naar de lidstatus.
  
### <a name="promote-a-member-to-owner-status-in-the-admin-center"></a>Het niveau van een lid verhogen naar de status van eigenaar in het Beheercentrum

1. Ga in het Beheercentrum naar de pagina [**actieve groepen**](https://admin.microsoft.com/Adminportal/Home?#/groups) .  

2. Klik op de naam van een groep.

3. Selecteer in het deelvenster Details, op het tabblad **leden** , de optie **AllesWeergeven en eigenaren beheren**.

4. Selecteer **eigenaren toevoegen**.

5. Schakel het selectievakje in naast de naam van het lid dat u wilt toevoegen.

6. Selecteer **Opslaan** en vervolgens **sluiten**.

### <a name="remove-owner-status-in-the-admin-center"></a>De status van eigenaar verwijderen in het Beheercentrum

1. Ga in het Beheercentrum naar de pagina [**actieve groepen**](https://admin.microsoft.com/Adminportal/Home?#/groups) .  

2. Klik op de naam van een groep.

3. Selecteer in het deelvenster Details, op het tabblad **leden** , de optie **AllesWeergeven en eigenaren beheren**.

4. Selecteer de X naast de naam van de eigenaar.

5. Kies **Opslaan**.

## <a name="more-on-managing-membership"></a>Meer informatie over het beheren van het lidmaatschap

- [Groepen beheren in Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=847632): zie de sectie Hoe kan ik het lidmaatschap van een groep dynamisch beheren?

- Als u honderden of duizenden gebruikers wilt toevoegen aan groepen, gebruikt u de [add-UnifiedGroupLinks](https://docs.microsoft.com/powershell/module/exchange/add-unifiedgrouplinks).

- [Een nieuwe eigenaar toewijzen aan een groep zonder eigenaar](https://support.microsoft.com/office/86bb3db6-8857-45d1-95c8-f6d540e45732)

## <a name="articles-about-managing-groups"></a>Artikelen over het beheren van groepen

- [Distributielijsten upgraden naar Microsoft 365-groepen in Outlook](../manage/upgrade-distribution-lists.md)

- [Waarom u uw distributielijsten moet upgraden naar groepen in Outlook](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

- [Gasttoegang beheren in Microsoft 365 groepen](manage-guest-access-in-groups.md)

- [Microsoft 365-groepen beheren met PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell): dit artikel is een inleiding tot de belangrijkste cmdlets en biedt voorbeelden

- [Naam beleid voor Microsoft 365-groepen](groups-naming-policy.md)
