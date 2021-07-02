---
title: Een conceptverzameling toewijzen aan een beoordelingsset
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: nickrob
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Nadat u een conceptverzameling hebt aan een conceptverzameling hebt toegevoegd en deze hebt itereren, kunt u deze toevoegen aan een revisieset. Wanneer u een conceptverzameling gaat maken, worden de verzamelde items toegevoegd om de set in de zaak te controleren. Nadat de verzamelde items zich in de revisieset hebben verzameld, kunt u deze analyseren, controleren en exporteren.
ms.openlocfilehash: dceb661d9586e324482dc4f56bce12fafaf9b251
ms.sourcegitcommit: 8c6a5db0dab99a82a69dd8a0a7c56af1cb825931
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/02/2021
ms.locfileid: "53276975"
---
# <a name="commit-a-draft-collection-to-a-review-set-in-advanced-ediscovery"></a>Een conceptverzameling aan een revisieset in Advanced eDiscovery

Wanneer u tevreden bent over de items die u hebt verzameld in een conceptverzameling en klaar bent om deze te analyseren, te taggen en te controleren, kunt u een verzameling toevoegen aan een revisieset in de zaak. Wanneer u een conceptverzameling verbindt aan een revisieset, worden verzamelde items gekopieerd van de oorspronkelijke inhoudslocatie in Microsoft 365 naar een revisieset. Een revisieset is een veilige, door Microsoft verstrekte Azure Storage in de Microsoft-cloud.

## <a name="commit-a-draft-collection-to-a-review-set"></a>Een conceptverzameling toewijzen aan een beoordelingsset

1. Open in Microsoft 365-compliancecentrum de hoofdsyte Advanced eDiscovery en selecteer  vervolgens het tabblad Verzamelingen om een lijst met de verzamelingen in de zaak weer te geven.

   ![Lijst met verzamelingen in een zaak](../media/CommitDraftCollections1.png)

   > [!TIP]
   > Een waarde `Estimated` van in de kolom **Status** identificeert de conceptverzamelingen die kunnen worden toegevoegd aan een revisieset. Een status van `Committed` geeft aan dat een verzameling al is toegevoegd aan een revisieset.

2. Selecteer op **de** pagina Verzamelingen de conceptverzameling die u wilt verbinden met een revisieset.

3. Selecteer onder aan de flyoutpagina de optie **Acties**  >  **bewerken-verzameling.**

4. Klik in de wizard Verzameling bewerken op **Volgende totdat** de pagina Concept **opslaan** of verzamelen wordt weergegeven.

5. Configureer de volgende instellingen:

   1. Selecteer **Items verzamelen en toevoegen om de revisieset te controleren.**

   2. Bepaal of u de verzameling wilt toevoegen aan een nieuwe revisieset (die wordt gemaakt nadat u de verzameling hebt verzenden) of aan een bestaande revisieset wilt toevoegen. Voltooi deze sectie op basis van uw beslissing.

   3. De extra verzamelingsinstellingen configureren:

       - **Teams en Yammer:** Selecteer deze optie om gespreksthreads toe te voegen aan de verzameling met de chatitems die worden geretourneerd door de zoekquery in de verzameling. Dit betekent dat het chatgesprek met items die voldoen aan de zoekcriteria, wordt gereconstrueerd. Op deze manier kunt u chatitems bekijken in de context van het heen en weer gesprek. Zie [Gespreksthreading in](conversation-review-sets.md)Advanced eDiscovery.

       - **Cloudbijlagen:** Selecteer deze optie om moderne bijlagen of gekoppelde bestanden op te nemen wanneer de verzamelingsresultaten aan de revisieset worden toegevoegd. Dit betekent dat het doelbestand van een moderne bijlage of gekoppeld bestand wordt toegevoegd aan de revisieset.

       - **SharePoint versies:** Selecteer deze optie om de verzameling van alle versies van een SharePoint document in te stellen volgens de versielimieten en zoekparameters van de verzameling. Als u deze optie selecteert, wordt het aantal items dat aan de revisieset wordt toegevoegd aanzienlijk groter.

   4. Configureer de instellingen om de schaal van de verzameling te definiëren die u wilt toevoegen aan de revisieset:

      - **Alle verzamelingsresultaten toevoegen:** Selecteer deze optie om alle items die overeenkomen met de zoekcriteria van de verzameling, toe te voegen aan de revisieset.

      - **Een voorbeeld van de verzamelingsresultaten toevoegen:** Selecteer deze optie om een voorbeeld van de verzamelingsresultaten toe te voegen aan de revisieset in plaats van alle resultaten toe te voegen. Als u deze optie selecteert, klikt u **op Voorbeeldparameters bewerken** en kiest u een van de volgende opties:

         - **Voorbeeld op basis van betrouwbaarheid:** Items uit de verzameling worden toegevoegd aan de revisieset en worden bepaald door de statistische parameters die u hebt ingesteld. Als u meestal een betrouwbaarheidsniveau en interval gebruikt bij het steekproefresultaat, geeft u deze op in de vervolgkeuzevakken. Gebruik anders de standaardinstellingen.

         - **Willekeurig voorbeeld:** Items uit de verzameling worden toegevoegd aan de revisieset op basis van een willekeurige selectie van het opgegeven percentage van het totale aantal items dat door de zoekopdracht wordt geretourneerd.

6. Op de **pagina Uw verzameling** controleren kunt u de verzamelingsinstellingen bekijken die u op de vorige pagina hebt geconfigureerd. Klik **op Bewerken** als u ze wilt wijzigen.

7. Klik **op Verzenden** om de conceptverzameling te maken. Er wordt een pagina weergegeven die bevestigt dat de verzameling is gemaakt.

## <a name="what-happens-after-you-commit-a-draft-collection"></a>Wat gebeurt er nadat u een conceptverzameling hebt gepleegd

Wanneer u een conceptverzameling aan een revisieset verbindt, gebeuren de volgende dingen:

- Als u een nieuwe revisieset hebt gemaakt waar u de verzameling aan wilt verbinden, wordt de revisieset gemaakt en weergegeven op het tabblad **Revisiesets** in de zaak. De status van de nieuwe revisieset is **Gereed**. Deze statuswaarde betekent dat de revisieset is gemaakt. dit betekent niet dat de verzameling is toegevoegd aan de revisieset. De status van het toevoegen van items in de verzameling aan de revisieset wordt weergegeven op het **tabblad Verzamelingen.**

- De zoekquery voor verzamelingen wordt opnieuw uitgevoerd. Dit betekent dat de werkelijke zoekresultaten die naar de revisieset zijn gekopieerd, anders kunnen zijn dan de geschatte resultaten die zijn geretourneerd toen de verzamelingszoekactie voor het laatst werd uitgevoerd.

- Alle items in de zoekresultaten worden gekopieerd uit de oorspronkelijke gegevensbron in de liveservice en gekopieerd naar een veilige Azure Storage locatie in de Microsoft-cloud.

- Alle items (inclusief de inhoud en metagegevens) die zich niet in bewaarder of niet-bewaarder bevinden, worden opnieuw geïndexeerd (in een proces dat deep *indexing* wordt genoemd) zodat alle gegevens in de revisieset volledig kunnen worden doorzocht tijdens de beoordeling van de casegegevens. Het opnieuw indexeren van de inhoud in een verzameling resulteert in grondige en snelle zoekopdrachten wanneer u de inhoud in de revisieset zoekt of filtert tijdens het onderzoek.

- Versleutelde SharePoint en OneDrive documenten en versleutelde bestanden die zijn gekoppeld aan e-mailberichten die in de zoekresultaten worden geretourneerd, worden ontsleuteld wanneer u de verzameling aan een revisieset verbindt. U kunt de ontsleutelde bestanden in de revisieset controleren en een query uitvoeren. Zie Ontsleuteling [in Microsoft 365 eDiscovery-hulpprogramma's](ediscovery-decryption.md)voor meer informatie.

- Ocr-functionaliteit (Optical Character Recognition) haalt tekst op uit afbeeldingen en bevat de afbeeldingstekst met de inhoud die is toegevoegd aan een revisieset. Zie de sectie Optische [tekenherkenning](#optical-character-recognition) in dit artikel voor meer informatie.

- Nadat de commit is voltooid, wordt de waarde van de statuskolom van op **het** tabblad Verzamelingen gewijzigd in `Committed` .

## <a name="optical-character-recognition"></a>Optische tekenherkenning

Wanneer u een verzameling verbindt aan een revisieset, worden met de ocr-functionaliteit (Optical Character Recognition) in Advanced eDiscovery automatisch tekst uit afbeeldingen geëxtraheert en wordt de afbeeldingstekst met de inhoud toegevoegd aan een revisieset. U kunt de uitgepakte tekst weergeven in de tekstviewer van het geselecteerde afbeeldingsbestand in de revisieset. Op deze manier kunt u tekst in afbeeldingen verder bekijken en analyseren. OCR wordt ondersteund voor losse bestanden, e-mailbijlagen en ingesloten afbeeldingen. Zie Ondersteunde bestandstypen in Advanced eDiscovery voor een lijst met [afbeeldingsbestandsindelingen](supported-filetypes-ediscovery20.md#image)die worden ondersteund voor OCR.

U moet OCR-functionaliteit inschakelen voor elk geval dat u maakt in Advanced eDiscovery. Zie Zoek- en [analyseinstellingen configureren](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr)voor meer informatie.
