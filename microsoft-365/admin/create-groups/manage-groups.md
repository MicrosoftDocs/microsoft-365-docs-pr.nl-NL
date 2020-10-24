---
title: Een groep beheren in het Beheercentrum
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 74a1ef8b-3844-4d08-9980-9f8f7a36000f
description: Meer informatie over het beheren van Microsoft 365 groepen, waaronder het toevoegen van groepsleden, het bewerken van het e-mailadres, de naam van de groep of beschrijving en het aanpassen van de werking van de groep.
ms.openlocfilehash: 8216b80ba6cd6bffe470f4fe4ace43307afba5f2
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753299"
---
# <a name="manage-a-group-in-the-microsoft-365-admin-center"></a>Een groep beheren in het Microsoft 365-Beheercentrum

Nadat u [een Microsoft 365-groep hebt gemaakt](create-groups.md) en groepsleden hebt toegevoegd, kunt u uw groep configureren. U kunt de groepsnaam of beschrijving bewerken, eigenaren en leden beheren en opgeven of externe afzenders de groep kunnen e-mailen en of ze kopieën van groepsgesprekken naar leden kunnen verzenden.

Ga naar het Microsoft 365-Beheercentrum [https://admin.microsoft.com](https://admin.microsoft.com) .

## <a name="edit-the-group-name-or-description"></a>De naam of beschrijving van de groep bewerken

1. In het Beheercentrum vouwt u **groepen**uit en klikt u vervolgens op **groepen**.

2. Selecteer de groep die u wilt bewerken en klik vervolgens op **naam en beschrijving bewerken**.

3. Werk de naam en beschrijving bij en selecteer **Opslaan**.

## <a name="manage-group-owners-and-members"></a>Groepseigenaren en leden beheren

1. In het Beheercentrum vouwt u **groepen**uit en klikt u vervolgens op **groepen**.

2. Klik op de naam van de groep die u wilt beheren om het deelvenster instellingen te openen.

3. Kies op het tabblad **leden** of u eigenaren of leden wilt beheren.

4. Kies **toevoegen** om iemand toe te voegen of klik op **X** om iemand te verwijderen.

5. Klik op **Sluiten**.

## <a name="send-copies-of-conversations-to-group-members-inboxes"></a>Kopieën van gesprekken verzenden naar de Postvak in van de groepsleden
  
Wanneer u het Beheercentrum gebruikt om een groep te maken, krijgen standaardgebruikers geen kopieën van groeps-e-mailberichten en uitnodigingen voor vergaderingen die naar hun postvak in zijn verzonden. De persoon moet naar de groep gaan om gesprekken en vergaderingen te zien. U kunt deze instelling wijzigen in het Beheercentrum.

Als u deze instelling inschakelt, krijgen groepsleden een kopie van de groeps-e-mails en uitnodigingen voor vergaderingen die naar hun postvak in van Outlook zijn verzonden. De groepsleden kunnen dit exemplaar van het e-mailbericht lezen en verwijderen zonder dat dit van invloed is op iemand anders. In het Postvak IN van de groep blijft een kopie van het e-mailbericht bewaard.

Groepsleden kunnen zich afmelden voor het ontvangen van deze e-mailberichten door het volgen van de groep in Outlook te beëindigen.

1. In het Beheercentrum vouwt u **groepen**uit en klikt u vervolgens op **groepen**.

2. Klik op de naam van de groep die u wilt beheren om het deelvenster instellingen te openen.

3. Selecteer op het tabblad **instellingen** de optie **kopieën van groepsgesprekken en gebeurtenissen verzenden naar groepsleden** als u wilt dat leden kopieën van groeps berichten en agenda-items in hun eigen postvak in ontvangen.

4. Kies **Opslaan**.

## <a name="let-people-outside-the-organization-email-the-group"></a>Toestaan dat personen buiten de organisatie e-mail sturen naar de groep

Deze optie is handig als u een zakelijk e-mailadres wilt hebben, bijvoorbeeld info@contoso.com.
 
1. In het Beheercentrum vouwt u **groepen**uit en klikt u vervolgens op **groepen**.

2. Klik op de naam van de groep die u wilt beheren om het deelvenster instellingen te openen.

3. Selecteer in de lijstbeheer centrum groepen de naam van de groep die u wilt wijzigen en selecteer vervolgens op het tabblad **instellingen** de optie **externe afzenders toestaan om deze groep te e-mailen**.
    
4. Kies **Opslaan**.

## <a name="permanently-delete-a-microsoft-365-group"></a>Een Microsoft 365-groep permanent verwijderen

Het kan soms voorkomen dat u een groep permanent wilt verwijderen zonder te hoeven wachten tot de dertig dagen dat de tijdelijke verwijdering duurt verloopt. Hiervoor start u PowerShell en voert u deze opdracht uit om de object-id van de groep op te vragen:
 
 ```powershell
`Get-AzureADMSDeletedGroup`
```

Noteer de object-ID van de groep of groepen die u permanent wilt verwijderen.
  
> [!CAUTION]
> Als u een groep permanent verwijdert, kunnen de groep en de bijbehorende gegevens niet meer worden hersteld. 
  
Voer deze opdracht uit in PowerShell om de groep permanent te verwijderen:

```powershell
`Remove-AzureADMSDeletedDirectoryObject -Id <objectId>`
```

U kunt controleren dat de groep definitief is verwijderd door de cmdlet  *Get-AzureADMSDeletedGroup*  opnieuw uit te voeren en te kijken of de groep niet meer wordt vermeld in de lijst met voorlopig verwijderde groepen. In sommige gevallen duurt het wel 24 uur voordat de groep en alle bijbehorende gegevens permanent zijn verwijderd. 
  
## <a name="related-articles"></a>Verwante artikelen

[Een Microsoft 365-groep maken](create-groups.md)

[Gasttoegang tot Microsoft 365-groepen beheren](https://support.microsoft.com/office/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Het domein kiezen dat u wilt gebruiken voor het maken van Microsoft 365-groepen](../../solutions/choose-domain-to-create-groups.md)

[Toestaan dat leden namens een Microsoft 365-groep verzenden als of verzenden](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md)

[Distributielijsten upgraden naar Microsoft 365-groepen](../manage/upgrade-distribution-lists.md)

[Microsoft 365-groepen beheren met PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
