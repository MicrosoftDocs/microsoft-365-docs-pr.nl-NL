---
title: Foutherstel voor één item
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
description: U kunt een verwerkingsfout in een document in een revisieset in Advanced eDiscovery oplossen zonder dat u het proces voor het bulksgewijs herstellen van fouten moet volgen.
ms.openlocfilehash: 8e5d8d00f507dc5792a1beda018d4c76632b82f7
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/05/2021
ms.locfileid: "52161657"
---
# <a name="single-item-error-remediation-in-advanced-ediscovery"></a>Herstel van fout met één item in Advanced eDiscovery

Foutsanering biedt Advanced eDiscovery gebruikers de mogelijkheid om gegevensproblemen op te lossen die voorkomen dat Advanced eDiscovery inhoud correct verwerkt. Bestanden die met een wachtwoord zijn beveiligd, kunnen bijvoorbeeld niet worden verwerkt omdat deze bestanden zijn vergrendeld of versleuteld. Voorheen kon u alleen bulksgewijs fouten corrigeren met [behulp van deze werkstroom.](error-remediation-when-processing-data-in-advanced-ediscovery.md) Maar soms is het niet zinvol om fouten in meerdere bestanden te corrigeren wanneer u niet zeker weet of een van deze bestanden reageert op de zaak die u onderzoekt. Het is ook mogelijk niet zinvol om fouten te corrigeren voordat u de kans hebt gehad om de bestandsmetagegevens (zoals bestandslocatie of wie toegang had) te bekijken, om u te helpen bij het nemen van beslissingen over reactiesnelheid. Een nieuwe functie met de naam single *item error remediation geeft* eDiscovery-managers de mogelijkheid om de metagegevens van bestanden te bekijken met een verwerkingsfout en zo nodig de fout rechtstreeks in de revisieset te corrigeren. In het artikel wordt beschreven hoe u bestanden kunt identificeren, negeren en corrigeren met verwerkingsfouten in een revisieset.

## <a name="identify-documents-with-errors"></a>Documenten identificeren met fouten

Documenten met verwerkingsfouten in een revisieset worden nu geïdentificeerd (met een banner). U kunt de fout corrigeren of negeren. In de volgende schermafbeelding ziet u de bewerkingsfoutbanner voor een Word-document in een revisieset die met een wachtwoord is beveiligd. U ziet ook dat u de bestandsmetagegevens van documenten met verwerkingsfouten kunt bekijken.

![Banner weergegeven voor document met verwerkingsfout](../media/SIERimage1.png)

U kunt ook zoeken naar documenten met verwerkingsfouten met behulp van de **statusstatus** verwerken bij het query's uitvoeren van [de documenten in een revisieset.](review-set-search.md)

![De voorwaarde Verwerkingsstatus gebruiken om te zoeken naar foutdocumenten](../media/SIERimage2.png)

### <a name="ignore-errors"></a>Fouten negeren

U kunt een verwerkingsfout negeren door te klikken op **Negeren** in de banner met verwerkingsfouten. Wanneer u een fout negeert, wordt het document verwijderd uit de [werkstroom bulksgewijs herstellen van fouten.](error-remediation-when-processing-data-in-advanced-ediscovery.md) Nadat een fout is genegeerd, verandert de documentbanner van kleur en wordt aangegeven dat de verwerkingsfout is genegeerd. U kunt de beslissing om de fout te negeren op elk moment herstellen door op **Terugkeren te klikken.**

![Klik op Negeren om de verwerkingsfout te negeren](../media/SIERimage3.png)

U kunt ook zoeken naar alle documenten met een verwerkingsfout die is genegeerd met de voorwaarde Genegeerde verwerkingsfouten bij het opvragen van documenten in een revisieset. 

![De voorwaarde Genegeerde verwerkingsfouten gebruiken om te zoeken naar genegeerde foutdocumenten](../media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a>Een document herstellen met fouten

Soms moet u mogelijk een verwerkingsfout in documenten herstellen (door een wachtwoord te verwijderen, een versleuteld bestand te ontsleutelen of een beschadigd document te herstellen) en vervolgens het herstelde document toe te voegen aan de revisieset. Op deze manier kunt u het foutdocument samen met de andere documenten in de revisieset bekijken en exporteren. 

Als u één document wilt herstellen, gaat u als volgt te werk:

1. Klik **op Origineel**  >  **downloaden** om een kopie van het bestand naar een lokale computer te downloaden.

   ![Het document downloaden met de verwerkingsfout](../media/SIERimage5.png)

2. Herstel de fout in het bestand offline. Voor versleutelde bestanden, waarvoor ontsleutelingssoftware vereist is, moet u wachtwoordbeveiliging verwijderen door het wachtwoord op te geven en het bestand op te slaan of een wachtwoordkraker te gebruiken. Nadat u het bestand hebt gesaneerd, gaat u naar de volgende stap.

3. Selecteer in de revisieset het bestand met de verwerkingsfout die u hebt gesaneerd en klik vervolgens op **Herstel**.

   ![Klik op Herstel in de banner van het document met verwerkingsfout](../media/SIERimage6.png)


4. Klik **op Bladeren,** ga naar de locatie van het bestand op uw lokale computer en selecteer het bestand.

   ![Klik op Bladeren en selecteer het herstelbestand op uw lokale computer](../media/SIERimage7.png)

    Nadat u het bestand hebt geselecteerd, wordt het automatisch geüpload naar de revisieset. U kunt de verwerkingsstatus van het bestand bijhouden.

    ![De status van het herstelproces wordt weergegeven](../media/SIERimage8.png)

   Nadat de verwerking is voltooid, kunt u het gesaneerd document bekijken.

    ![U kunt het gesaneerd bestand weergeven in de oorspronkelijke indeling in de revisieset](../media/SIERimage9.png)

Zie Wat gebeurt er wanneer bestanden worden gesaneerd voor meer informatie over wat er gebeurt wanneer een document [wordt gesaneerd.](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated)

## <a name="search-for-remediated-documents"></a>Zoeken naar hersteldocumenten

U kunt zoeken naar alle documenten in een revisieset  die zijn gesaneerd met behulp van de voorwaarde Trefwoorden en de volgende eigenschap:waardepaar opgeven: **IsFromErrorRemediation:true.** Deze eigenschap is ook beschikbaar in het exportladingsbestand wanneer u documenten exporteert uit een revisieset.
