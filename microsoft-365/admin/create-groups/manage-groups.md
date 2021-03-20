---
title: Een groep beheren in het beheercentrum
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
description: Informatie over het beheren van Microsoft 365-groepen, zoals het toevoegen van groepsleden verwijderen, het bewerken van het e-mailadres, de groepsnaam of beschrijving en het aanpassen van de manier waarop de groep werkt.
ms.openlocfilehash: 3ba3dd36ed3929e956ce6359e678d6b684f64bb9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908708"
---
# <a name="manage-a-group-in-the-microsoft-365-admin-center"></a>Een groep beheren in het Microsoft 365-beheercentrum

Nadat u een [Microsoft 365-groep hebt](create-groups.md) gemaakt en groepsleden hebt toegevoegd, kunt u de groep configureren. U kunt de naam of beschrijving van de groep bewerken, eigenaren of leden beheren en opgeven of externe afzenders een e-mail kunnen sturen naar de groep en of u kopieën van groepsgesprekken naar leden wilt verzenden.

Ga naar het Microsoft 365-beheercentrum op [https://admin.microsoft.com](https://admin.microsoft.com) .

## <a name="edit-the-group-name-or-description"></a>De naam of beschrijving van de groep bewerken

1. Vouw groepen uit in het beheercentrum **en** klik vervolgens op **Groepen.**

2. Selecteer de groep die u wilt bewerken en klik vervolgens op **Naam en beschrijving bewerken.**

3. Werk de naam en beschrijving bij en selecteer **Opslaan.**

## <a name="manage-group-owners-and-members"></a>Groepseigenaars en -leden beheren

1. Vouw groepen uit in het beheercentrum **en** klik vervolgens op **Groepen.**

2. Klik op de naam van de groep die u wilt beheren om het instellingenvenster te openen.

3. Kies op **het** tabblad Leden of u eigenaren of leden wilt beheren.

4. Kies **Toevoegen om** iemand toe te voegen of klik op **X** om iemand te verwijderen.

5. Klik op **Sluiten**.

## <a name="send-copies-of-conversations-to-group-members-inboxes"></a>Kopieën van gesprekken verzenden naar postvak IN van groepsleden
  
Wanneer u het beheercentrum gebruikt om een groep te maken, ontvangen gebruikers standaard geen kopieën van groeps-e-mailberichten en uitnodigingen voor vergadering die naar hun Postvak IN worden verzonden. Ze moeten naar de groep gaan om gesprekken en vergaderingen te zien. U kunt deze instelling wijzigen in het beheercentrum.

Wanneer u deze instelling int, ontvangen groepsleden een kopie van groeps-e-mailberichten en uitnodigingen voor vergadering die naar hun Postvak IN van Outlook zijn verzonden. De groepsleden kunnen dit exemplaar van het e-mailbericht lezen en verwijderen zonder dat dit van invloed is op iemand anders. In het Postvak IN van de groep blijft een kopie van het e-mailbericht bewaard.

Groepsleden kunnen ervoor kiezen deze e-mailberichten niet meer te ontvangen door ervoor te kiezen de groep niet meer te volgen in Outlook.

1. Vouw groepen uit in het beheercentrum **en** klik vervolgens op **Groepen.**

2. Klik op de naam van de groep die u wilt beheren om het instellingenvenster te openen.

3. Selecteer op **het**  tabblad Instellingen de optie Kopieën van groepsgesprekken en gebeurtenissen verzenden naar groepsleden als u wilt dat leden kopieën van groepsberichten en agenda-items in hun eigen Postvak IN ontvangen.

4. Kies **Opslaan**.

## <a name="let-people-outside-the-organization-email-the-group"></a>Personen buiten de organisatie e-mailen naar de groep

Deze optie is geweldig als u een e-mailadres van een bedrijf wilt hebben, zoals info@contoso.com.
 
1. Vouw groepen uit in het beheercentrum **en** klik vervolgens op **Groepen.**

2. Klik op de naam van de groep die u wilt beheren om het instellingenvenster te openen.

3. Selecteer in de lijst met beheercentrumgroepen de naam van de  groep die u wilt wijzigen en selecteer vervolgens op het tabblad Instellingen de optie Externe afzenders toestaan deze groep een e-mail **te sturen.**
    
4. Kies **Opslaan**.

## <a name="permanently-delete-a-microsoft-365-group"></a>Een Microsoft 365-groep definitief verwijderen

Soms wilt u een groep mogelijk permanent verwijderen zonder te wachten tot de periode van 30 dagen voor het verwijderen is verlopen. Hiervoor start u PowerShell en voert u deze opdracht uit om de object-id van de groep op te vragen:
 
 ```powershell
`Get-AzureADMSDeletedGroup`
```

Noteer de object-id van de groep of groepen die u permanent wilt verwijderen.
  
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

[Kies het domein dat u wilt gebruiken bij het maken van Microsoft 365-groepen](../../solutions/choose-domain-to-create-groups.md)

[Toestaan dat leden verzenden als of verzenden namens een Microsoft 365-groep](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md)

[Distributielijsten upgraden naar Microsoft 365-groepen](../manage/upgrade-distribution-lists.md)

[Microsoft 365-groepen beheren met PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md)