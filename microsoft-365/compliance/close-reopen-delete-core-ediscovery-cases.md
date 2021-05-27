---
title: Core eDiscovery-zaken sluiten, opnieuw openen en verwijderen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: In dit artikel wordt beschreven hoe u Core eDiscovery-zaken kunt beheren. Dit omvat het sluiten van een zaak, het opnieuw openen van een gesloten zaak en het verwijderen van een zaak.
ms.openlocfilehash: d729c91d4e81ad12d0b4b16574aa4edad8e239a3
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684097"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a>Een Hoofd-eDiscovery-zaak sluiten, opnieuw openen en verwijderen

In dit artikel wordt beschreven hoe u core-eDiscovery-zaken sluit, opnieuw opent en verwijdert in Microsoft 365.

## <a name="close-a-case"></a>Een zaak sluiten

Wanneer de juridische zaak of het onderzoek dat wordt ondersteund door een Core eDiscovery-zaak is voltooid, kunt u de zaak sluiten. Dit gebeurt er als u een zaak sluit:
  
- Als de zaak een eDiscovery-inhoud bevat, worden deze uitgeschakeld. Nadat de wachtstand is uitgeschakeld, wordt een respijtperiode van 30 dagen (een zogenaamde *vertragingstermijn)* toegepast op inhoudslocaties die in de wachtstand stonden. Dit helpt voorkomen dat inhoud onmiddellijk wordt verwijderd en biedt beheerders de mogelijkheid om inhoud te zoeken en te herstellen voordat deze definitief kan worden verwijderd nadat de vertragingsperiode is verstreken. Zie Inhoudslocaties verwijderen uit een [eDiscovery-hold voor meer informatie.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)

- Als u een zaak sluit, worden alleen de aan die zaak gekoppelde insluiten uitgeschakeld. Als andere bewaringen worden geplaatst op een inhoudslocatie (zoals een procesovergang, een bewaarbeleid of een bewaring vanuit een andere Core eDiscovery-zaak), blijven deze bewaringen behouden.

- De zaak wordt nog steeds vermeld op de pagina Core eDiscovery in het Microsoft 365 compliancecentrum. De details, bewaart, zoekt en leden van een gesloten zaak blijven behouden.

- U kunt een zaak bewerken nadat deze is gesloten. U kunt bijvoorbeeld leden toevoegen of verwijderen, zoekopdrachten maken en zoekresultaten exporteren. Het primaire verschil tussen actieve en gesloten zaken is dat eDiscovery-holds zijn uitgeschakeld wanneer een zaak wordt gesloten.

Een zaak sluiten:
  
1. Klik in Microsoft 365 compliancecentrum op **eDiscovery** Core om de lijst weer te geven met  >   Core eDiscovery-zaken in uw organisatie.

2. Klik op de naam van de zaak die u wilt sluiten.

   ![Hoofdzaak sluiten op startpagina van zaak](../media/eDiscoveryCaseHomePage.png)

3. Klik op de startpagina onder **Status** op **Hoofdzaak sluiten.**

    Er wordt een waarschuwing weergegeven waarin wordt gezegd dat de aan de zaak gekoppelde in- en uit-standen worden uitgeschakeld.

4. Klik **op Ja** om de zaak te sluiten.

    De status op de startpagina van de zaak wordt gewijzigd van **Actief in** **Sluiten.**

5. Klik op **de pagina Core eDiscovery** **op** Vernieuwen om de status van de gesloten zaak bij te werken. Het kan tot 60 minuten duren voordat het sluitingsproces is voltooid.

    Wanneer het proces is voltooid, wordt de status van de zaak gewijzigd in **Gesloten** op de **pagina Core eDiscovery.**

## <a name="reopen-a-closed-case"></a>Een gesloten zaak opnieuw openen

Wanneer u een zaak opnieuw opent, worden eDiscovery-gegevens die waren ingesteld toen de zaak werd gesloten, niet automatisch hersteld. Nadat de zaak opnieuw is geopend, moet  u naar de pagina Houdt gaan en de vorige in- en uit te zetten. Als u een wachtruimte wilt in- of uitschakelen, selecteert u deze om de flyoutpagina weer te geven en stelt u de schakelknop **Status** in op **Aan.**
  
1. Klik in Microsoft 365 compliancecentrum op **eDiscovery** Core om de lijst weer te geven met  >   Core eDiscovery-zaken in uw organisatie.

2. Klik op de naam van de zaak die u opnieuw wilt openen.

   ![Een gesloten zaak opnieuw openen](../media/eDiscoveryCaseHomePageReopen.png)

3. Klik op de startpagina onder **Status** op **Zaak opnieuw openen.**

    Er wordt een waarschuwing weergegeven met de melding dat de aan de zaak gekoppelde in- en uitstal nen niet automatisch worden ingeschakeld.

4. Klik **op Ja** om de zaak opnieuw te openen.

    De status op de startpagina van de hoofdpagina wordt gewijzigd van **Gesloten in** **Actief.**

5. Klik op **de pagina Core eDiscovery** **op** Vernieuwen om de status van de opnieuw geopende zaak bij te werken. Het kan tot 60 minuten duren voordat het heropeningsproces is voltooid. 

    Wanneer het proces is voltooid, wordt de status van de zaak gewijzigd in **Actief** op de **pagina Core eDiscovery.**

6. (Optioneel) Als u alle wachtposities wilt in-  of in- of uit- zetten die aan de opnieuw geopende zaak zijn gekoppeld, gaat u naar het tabblad Wacht houden, selecteert u een wachtpositie en selecteert u vervolgens het selectievakje onder **Status** op de flyoutpagina van de wachtpositie.
  
## <a name="delete-a-case"></a>Een zaak verwijderen

U kunt ook actieve en gesloten Core eDiscovery-zaken verwijderen. Wanneer u een zaak verwijdert, worden alle zoekopdrachten en exporten in de zaak verwijderd en wordt de zaak verwijderd uit de lijst met zaken op de **pagina Core eDiscovery** in het Microsoft 365 compliancecentrum. U kunt een verwijderde zaak niet opnieuw openen.

Voordat u een zaak kunt verwijderen (of deze nu  actief of gesloten is), moet u eerst alle eDiscovery-items verwijderen die aan de zaak zijn gekoppeld. Dit geldt ook voor het verwijderen van in-standen met de status **Uit.** 

Een eDiscovery-hold verwijderen:

1. Ga naar het **tabblad Houdt** in het geval dat u wilt verwijderen.

2. Selecteer de wacht die u wilt verwijderen.

3. Klik op de flyoutpagina op **Verwijderen.**

      ![Een eDiscovery-hold verwijderen](../media/DeleteeDiscoveryHold.png)

Een zaak verwijderen:

1. Klik in Microsoft 365 compliancecentrum op **eDiscovery** Core om de lijst weer te geven met  >   Core eDiscovery-zaken in uw organisatie.

2. Klik op de naam van de zaak die u wilt verwijderen.

3. Klik op de startpagina van de zaak onder **Status** op **Hoofd zaak verwijderen.**

      ![Een zaak verwijderen](../media/eDiscoveryCaseHomePageDelete.png)

Als de zaak die u probeert te verwijderen nog steeds eDiscovery bevat, ontvangt u een foutbericht. U moet alle aan de zaak gekoppelde items verwijderen en vervolgens opnieuw proberen om de zaak te verwijderen.
