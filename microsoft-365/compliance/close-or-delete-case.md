---
title: Een case sluiten of verwijderen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Lees wat er gebeurt wanneer een onderzoek of juridische zaak die wordt ondersteund door een Advanced eDiscovery zaak wordt gesloten of verwijderd.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7b11faa2ccdb44fca916b2f602d5120adadf1739
ms.sourcegitcommit: 4f6ef4cd09c3ed36dc0be3702b0636bad6cff8a9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/26/2021
ms.locfileid: "52657637"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a>Een Advanced eDiscovery sluiten of verwijderen

Wanneer de juridische zaak of het onderzoek dat wordt ondersteund door een Advanced eDiscovery is voltooid, kunt u een zaak sluiten of verwijderen. U kunt ook een gesloten zaak opnieuw openen.

## <a name="close-a-case"></a>Een zaak sluiten

Dit gebeurt er als u een Advanced eDiscovery sluit:

- Als de zaak inhoudslocaties bevat die in de wacht staan, worden deze in de wacht gezet. Nadat de wachtstand is uitgeschakeld, wordt een respijtperiode van 30 dagen (een zogenaamde *vertragingstermijn)* toegepast op inhoudslocaties die in de wachtstand stonden. Dit helpt voorkomen dat inhoud onmiddellijk wordt verwijderd en geeft beheerders de mogelijkheid om inhoud te zoeken of te herstellen die definitief wordt verwijderd nadat de vertragingsperiode is verstreken. Zie Inhoudslocaties verwijderen uit een [eDiscovery-hold voor meer informatie.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)

- Als u een zaak sluit, worden alleen de aan die zaak gekoppelde insluiten uitgeschakeld. Als andere ingehouden eDiscovery's op een inhoudslocatie (zoals een procesovergang, core eDiscovery-bezit of een andere Advanced eDiscovery-zaak) worden bewaard, blijven deze in stand.

- De zaak wordt nog steeds weergegeven op de eDiscovery-pagina in het Microsoft 365 compliancecentrum. De details, bewaart, zoekt en leden van een gesloten zaak blijven behouden.

- U kunt een zaak bewerken nadat deze is gesloten. U kunt bijvoorbeeld leden toevoegen of verwijderen, zoekopdrachten maken, zoekresultaten exporteren en zoekresultaten voorbereiden voor analyse in Advanced eDiscovery. Het primaire verschil tussen actieve en gesloten zaken is dat deze zijn uitgeschakeld wanneer een zaak wordt gesloten.

Een zaak sluiten:

1. Selecteer op **Advanced eDiscovery** pagina de zaak die u wilt sluiten.

2. Klik op **Instellingen** tabblad Onder **Hoofdgegevens** op **Selecteren.**

3. Klik onder aan de **flyoutpagina Hoofdgegevens** op (**...**) **Meer opties** en klik vervolgens op **Zaak sluiten.**

   ![Optie in het menu Meer opties om een Advanced eDiscovery sluiten](..\Media\CloseAdvancedeDiscoveryCase.png)

   Het kan tot 60 minuten duren voordat het sluitingsproces is voltooid.

## <a name="reopen-a-closed-case"></a>Een gesloten zaak opnieuw openen

Wanneer u een Advanced eDiscovery opnieuw opent, worden alle opgeslagen e-Advanced eDiscovery die waren ingesteld toen de zaak werd gesloten, niet automatisch opnieuw hersteld. Nadat de zaak opnieuw is geopend, moet  u naar het tabblad Houdt gaan en de vorige in- en uit te zetten. Als u een wachtruimte wilt in- of uitschakelen, selecteert u deze om de flyoutpagina weer te geven en stelt u de schakelknop **Status** in op **Aan.**

Een gesloten zaak opnieuw openen:

1. Selecteer op **Advanced eDiscovery** pagina de zaak die u opnieuw wilt openen.

2. Klik op **Instellingen** tabblad Onder **Hoofdgegevens** op **Selecteren.**

3. Klik onder aan de **flyoutpagina Hoofdgegevens** op (**...**) **Meer opties** en klik vervolgens op **Zaak opnieuw openen.**

   ![Optie in het menu Meer opties om een nieuwe Advanced eDiscovery openen](..\Media\ReopenAdvancedeDiscoveryCase.png)

   Het kan tot 60 minuten duren voordat het heropeningsproces is voltooid.

## <a name="delete-a-case"></a>Een zaak verwijderen

U kunt zowel actieve als gesloten Advanced eDiscovery verwijderen. Wanneer u een zaak verwijdert, worden alle onderdelen die aan de zaak zijn gekoppeld, zoals de lijst met bewaarders, communicatie, zoekopdrachten, revisiesets en exportklus, verwijderd. De zaak wordt verwijderd uit de lijst met zaken op **de** Advanced eDiscovery pagina in het Microsoft 365 compliancecentrum. U kunt een verwijderde zaak niet herstellen of opnieuw openen.

> [!NOTE]
> In scenario's voor gegevensmortage kunt u alleen items in een revisieset verwijderen door het Advanced eDiscovery verwijderen. Andere 'zoek- en verwijdermethoden' verwijderen geen items uit een revisieset.

Voordat u een zaak kunt verwijderen (of deze nu  actief of gesloten is), moet u eerst alle aan de zaak gekoppelde items verwijderen. Dit geldt ook voor het verwijderen van in-standen met de status **Uit.**

Houd in een zaak verwijderen:

1. Ga naar **het tabblad** Houdt in het Advanced eDiscovery dat u wilt verwijderen.

2. Klik op de wacht die u wilt verwijderen.

3. Klik op de flyoutpagina op **Wacht houden verwijderen.**

Een zaak verwijderen:

1. Selecteer op **Advanced eDiscovery** pagina de zaak die u wilt verwijderen.

2. Klik op **Instellingen** tabblad Onder **Hoofdgegevens** op **Selecteren.**

3. Klik onder aan de **flyoutpagina Hoofdgegevens** op (**...**) **Meer opties** en klik vervolgens op **Case verwijderen.**

   ![Optie in het menu Meer opties om een Advanced eDiscovery verwijderen](..\Media\DeleteAdvancedeDiscoveryCase.png)
