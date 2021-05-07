---
title: Een bewaring vanwege juridische procedure maken
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
description: Meer informatie over het plaatsen van een postvak in De wacht houden van rechtszaken, met behoud van alle postvakinhoud tijdens een onderzoek.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 81d3bf7bba0aadbcd2d52b5f7707caeea96e26c1
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "52162586"
---
# <a name="create-a-litigation-hold"></a>Een bewaring vanwege juridische procedure maken

U kunt een postvak in de wacht houden om alle postvakinhoud te behouden, inclusief verwijderde items en de oorspronkelijke versies van gewijzigde items. Wanneer u een postvak van een gebruiker in De juridische procedure in de wacht houdt, blijft inhoud in het archiefpostvak van de gebruiker (als dit is ingeschakeld) ook behouden. Wanneer u een wachtperiode maakt, kunt u een duur opgeven (ook wel een tijdsinstelling *genoemd)* zodat verwijderde en gewijzigde items gedurende een bepaalde periode worden bewaard en vervolgens definitief uit het postvak worden verwijderd. Of u kunt inhoud voor onbepaalde tijd behouden (een oneindige *greep* genoemd) of totdat de Procesvoeringsophoudt wordt verwijderd. Als u een duur van de wachtperiode opgeeft, wordt dit berekend vanaf de datum waarop een bericht wordt ontvangen of een postvakitem wordt gemaakt. 
  
Dit gebeurt er als u een proces in de wacht houdt.
  
- Items die permanent door de gebruiker worden verwijderd, blijven bewaard in de map Herstelbare items in het postvak van de gebruiker gedurende de duur van de wacht.

- Items die door de gebruiker uit de map Herstelbare items worden verwijderd, blijven bewaard gedurende de duur van de wacht.

- Het opslagquotum voor de map Herstelbare items wordt verhoogd van 30 GB naar 110 GB.

- Items in het primaire postvak van de gebruiker en de archiefpostvakken blijven behouden

## <a name="assign-an-exchange-online-plan-2-license"></a>Een abonnementslicentie Exchange Online abonnement 2 toewijzen

Als u een postvak Exchange Online bij Procesvoeringsberechting, moet er een licentie Exchange Online abonnement 2 worden toegewezen. Als aan een postvak een licentie Exchange Online abonnement 1 is toegewezen, moet u het een afzonderlijke Exchange Online Archiving toewijzen om het in de wacht te zetten.

> [!NOTE]
> Voor Office 365 Education organisaties wordt Litigation Hold ondersteund in Office 365 A1 abonnementen, waaronder een licentie Exchange Online Abonnement 1 met aanvullende functies. Zie de sectie 'Exchange Online functies' in de [Office 365 Education servicebeschrijving voor meer informatie.](/office365/servicedescriptions/office-365-platform-service-description/office-365-education#exchange-online-features)

## <a name="place-a-mailbox-on-litigation-hold"></a>Een postvak in de wacht houden voor rechtszaken plaatsen

Hier volgen de stappen om een postvak in de wacht te zetten via het Exchange beheercentrum.

1. Ga naar [https://outlook.office.com/ecp](https://outlook.office.com/ecp) en meld u aan met uw globale beheerdersaccount.

2. Klik **op Geadresseerden > postvakken** in het linkernavigatiedeelvenster.

3. Selecteer het postvak dat u wilt plaatsen in De procesvoering en klik vervolgens op **Bewerken.**

4. Klik op de pagina Postvakeigenschappen op **Postvakfuncties.**
    
5. Klik **onder Procesberechting: Uitgeschakeld** op **Inschakelen** om het postvak in de wacht te zetten.
    
6. Voer op **de pagina Procesvoering** de volgende optionele informatie in: 
    
    - **Duur van de procesduur (dagen)** - Gebruik dit vak om een op tijd gebaseerde wachttijd te maken en op te geven hoe lang postvakitems worden gehouden wanneer het postvak in de wacht wordt geplaatst. De duur wordt berekend vanaf de datum waarop een postvakitem wordt ontvangen of gemaakt. Wanneer de duur van de bewaartermijn voor een bepaald item verloopt, wordt dat item niet meer bewaard. Als u dit vak leeg laat, blijven items voor onbepaalde tijd behouden of totdat de wacht wordt verwijderd. Gebruik dagen om de duur op te geven.
    
    - **Opmerking-** Gebruik dit vak om de gebruiker te informeren dat het postvak van de gebruiker in de wacht staat. De notitie wordt weergegeven op de pagina Accountgegevens in het postvak van de gebruiker als deze Outlook 2010 of hoger. Als u deze pagina wilt openen, kunnen gebruikers klikken **op Bestand** in Outlook.
    
    - **URL-** Gebruik dit vak om de gebruiker naar een website te leiden voor meer informatie over procesvoering. Deze URL wordt weergegeven op de pagina Accountgegevens in het postvak van de gebruiker als deze Outlook 2010 of hoger. Als u deze pagina wilt openen, kunnen gebruikers klikken **op Bestand** in Outlook..

7. Klik **op Opslaan** op de pagina Litigation **Hold** en klik vervolgens **op Opslaan** op de pagina postvakeigenschappen.

### <a name="create-a-litigation-hold-using-powershell"></a>Een geschil in de wacht zetten met PowerShell

U kunt ook een procesopvolging maken door de volgende opdracht uit te voeren in [Exchange Online PowerShell:](/powershell/exchange/connect-to-exchange-online-powershell)

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true
```

Met de vorige opdracht blijven items voor onbepaalde tijd behouden omdat de duur van de bewaartijd niet is opgegeven. Gebruik de volgende opdracht om een tijdsgebaseerde wachttijd te maken:

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true -LitigationHoldDuration <number of days>
```

Zie Postvak [instellen voor meer informatie.](/powershell/module/exchange/set-mailbox)

## <a name="how-does-litigation-hold-work"></a>Hoe werkt Litigation Hold?

In de normale werkstroom van verwijderde items wordt een postvakitem verplaatst naar de submap Verwijderingen in de map Herstelbare items wanneer een gebruiker het item permanent verwijdert (Shift + Delete) of verwijdert uit de map Verwijderde items. Een verwijderingsbeleid (een bewaarlabel dat is geconfigureerd met een bewaaractie Verwijderen) verplaatst items ook naar de submap Verwijderingen wanneer de bewaarperiode verloopt. Wanneer een gebruiker een item in de map Herstelbare items opslossert of wanneer de bewaarperiode van het verwijderde item voor een item verloopt, wordt het verplaatst naar de submap Purges in de map Herstelbare items en gemarkeerd voor permanente verwijdering. Het wordt verwijderd uit Exchange de volgende keer dat het postvak wordt verwerkt door de MFA (Managed Folder Assistant).

Wanneer een postvak in de bewaartijd voor rechtszaken wordt geplaatst, blijven items in de submap Purges behouden voor de duur van de bewaartijd die is opgegeven in de bewaartijd voor rechtszaken. De duur van de wacht wordt berekend op basis van de oorspronkelijke datum waarop een item is ontvangen of gemaakt en definieert hoe lang items in de submap Purges worden gehouden. Wanneer de duur van de wachttijd verloopt voor een item in de submap Purges, wordt het item gemarkeerd voor permanente verwijdering en wordt het verwijderd uit Exchange de volgende keer dat het postvak door de MFA wordt verwerkt. Als een postvak voor onbepaalde tijd in de wacht wordt geplaatst, worden items nooit verwijderd uit de submap Purges.

In de volgende afbeelding ziet u de submappen in de mappen Herstelbare items en het werkstroomproces in de wacht houden.

![Rechtszaken Houd de levenscyclus vast](../media/LitigationHoldLifeCycle.png)

> [!NOTE]
> Als een bewaargreep die is gekoppeld aan een eDiscovery-zaak in een postvak wordt geplaatst, worden verwijderde items verplaatst van de submap Verwijderingen naar de discoveryHolds-submap en blijven ze behouden totdat het postvak wordt vrijgegeven uit de eDiscovery-bewaarplaats.
