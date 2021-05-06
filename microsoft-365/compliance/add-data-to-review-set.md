---
title: Zoekresultaten toevoegen aan een controleset
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
ms.custom:
- seo-marvel-apr2020
description: Meer informatie over het toevoegen van zoekresultaten of voorbeelden van die zoekresultaten aan een Advanced eDiscovery overzichtsset.
ms.openlocfilehash: 25ea5fe076753d4a5685f1224b98a2005d334f5f
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/05/2020
ms.locfileid: "52161549"
---
# <a name="add-search-results-to-a-review-set"></a>Zoekresultaten toevoegen aan een controleset

Wanneer u tevreden bent over de resultaten van een zoekopdracht en u klaar bent om deze zoekresultaten te bekijken en te analyseren, kunt u deze toevoegen aan een revisieset in de zaak. Als u de oorspronkelijke gegevens naar de revisieset kopieert, kunt u ook het controle- en analyseproces vergemakkelijken door u geavanceerde analysehulpmiddelen te bieden, zoals thema'sdetectie, detectie van bijna dubbele waarden en identificatie van e-mailthreads. U kunt ook gegevens uit niet-Microsoft 365 gegevensbronnen toevoegen aan een revisieset, zodat u deze gegevens kunt controleren naast de gegevens die u van uw Microsoft 365.

Wanneer u de resultaten van een zoekopdracht toevoegt aan een revisieset  (de revisiesets in een zaak worden weergegeven op het tabblad Revisiesets), treden de volgende dingen op:

- De zoekopdracht wordt opnieuw uitgevoerd. Dit betekent dat de werkelijke zoekresultaten die naar de revisieset zijn gekopieerd, anders kunnen zijn dan de geschatte resultaten die zijn geretourneerd toen de zoekopdracht voor het laatst werd uitgevoerd.

- Alle items in de zoekresultaten worden gekopieerd uit de oorspronkelijke gegevensbron in de liveservices en gekopieerd naar een veilige Azure Storage locatie in de Microsoft-cloud.

- Alle items (inclusief de inhoud en metagegevens) worden opnieuw geïndexeerd, zodat alle gegevens in de revisieset volledig kunnen worden doorzocht tijdens het controleren van de casegegevens. Het indexeren van de gegevens resulteert in grondige en snelle zoekopdrachten wanneer u tijdens het onderzoek naar de gegevens in de revisieset zoekt.

- Een bestand dat [](encryption.md) is versleuteld met een Microsoft-versleutelingstechnologie en is gekoppeld aan een e-mailbericht dat wordt geretourneerd in de zoekresultaten, wordt ontsleuteld wanneer het e-mailbericht en het bijgevoegde bestand worden toegevoegd aan de revisieset. U kunt het ontsleutelde bestand bekijken en query's uitvoeren in de revisieset. U moet de rol RMS Decrypt toegewezen krijgen om ontsleutelde e-mailbijlagen toe te voegen aan een revisieset. Zie Ontsleuteling [in Microsoft 365 eDiscovery-hulpprogramma's](ediscovery-decryption.md)voor meer informatie.

Als u gegevens wilt toevoegen aan een  revisieset, klikt u op een zoekopdracht op het tabblad Zoekopdrachten en klikt u vervolgens op Resultaten toevoegen om **de set** te controleren op de flyoutpagina.

U kunt een bestaande revisieset toevoegen of een nieuwe revisieset maken.  Als u een nieuwe revisieset toevoegt, geeft u de naam op en klikt u **op Toevoegen om** de flyoutpagina weer te geven.

![Een revisieset selecteren en verzamelingsopties configureren](../media/AeD_AddToReviewSet.png)

Het toevoegen van gegevens aan een revisieset is een langlopende procedure. Dit proces omvat het verzamelen van items uit de oorspronkelijke gegevensbronnen in Microsoft 365 (bijvoorbeeld uit postvakken en sites), het kopiëren naar de Azure Storage-locatie (dit kopieerproces wordt ook wel opname *genoemd)* en vervolgens het opnieuw indexeren van de items. U kunt de voortgang bijhouden op  **het** tabblad Taken of op het tabblad Zoekopdrachten door de status in de kolom Toegevoegde gegevens te **controleren.** Nadat de verwerking van de  revisieset is voltooid, klikt u op het tabblad Revisiesets in de zaak en klikt u vervolgens op de revisieset om het proces van het filteren, controleren, taggen en exporteren van gegevens in de revisieset te starten.

## <a name="define-options-to-scope-your-collection-for-review"></a>Opties definiëren voor het bereik van uw verzameling voor controle

Wanneer u de inhoud van een zoekopdracht toevoegt aan een bestaande of nieuwe revisieset, hebt u de volgende opties voor het verzamelen van de inhoud voor controle:

- **Versies uit SharePoint (beta)** opnemen: Gebruik deze optie om de verzameling van alle versies van een SharePoint-document in te stellen volgens de versielimieten en zoekparameters van de verzameling. Als u deze optie selecteert, wordt het aantal items dat aan de revisieset wordt toegevoegd aanzienlijk groter.

- **Opties voor het ophalen van** gesprekken: Items die aan de revisieset zijn toegevoegd, zijn ingeschakeld voor discussielijngesprekken om inhoud te bekijken in de context van het heen en weer-gesprek. Zie Gesprekken bekijken [in Advanced eDiscovery.](conversation-review-sets.md)

- **Ophalen voor moderne bijlagen inschakelen:** Gebruik deze optie om moderne bijlagen of gekoppelde bestanden in de verzameling op te nemen voor verder onderzoek. Zie Metagegevensvelden in documenten in Advanced eDiscovery voor meer informatie over de [doorzoekbare eigenschappen](document-metadata-fields-in-Advanced-eDiscovery.md)die betrekking hebben op moderne bijlagen.

## <a name="add-a-sample-to-a-review-set"></a>Een voorbeeld toevoegen aan een revisieset

Als u de resultaten van een zoekopdracht grondiger wilt valideren voordat u ze allemaal toevoegt aan een revisieset, kunt u een voorbeeld van de zoekresultaten toevoegen aan een revisieset in plaats van alles toe te voegen.

Als u een voorbeeld wilt toevoegen aan een revisieset, klikt u op een zoekopdracht op **het** tabblad Zoekopdrachten en klikt u op **Voorbeeld** op de flyoutpagina. Kies op **de pagina Steekproefparameters** een van de volgende opties:

- **Betrouwbaarheidsniveau %** en **betrouwbaarheidsinterval %** : de items die aan de revisieset zijn toegevoegd, worden bepaald door de statistische parameters die u hebt ingesteld. Als u meestal een betrouwbaarheidsniveau en interval gebruikt bij het steekproefresultaat, geeft u deze op in de vervolgkeuzevakken. Gebruik anders de standaardinstellingen.

- **Steekproef %:** de items die aan de revisieset zijn toegevoegd, zijn gebaseerd op een willekeurige selectie van het opgegeven percentage van het totale aantal items dat door de zoekopdracht wordt geretourneerd.

Nadat u een van de vorige opties hebt geselecteerd en geconfigureerd, kiest u een revisieset om het voorbeeld aan toe te voegen en klikt u vervolgens op **Verzenden.** Nogmaals, u kunt de  voortgang bijhouden op  het tabblad Taken of op het tabblad Zoekopdrachten door de status in de kolom Toegevoegde gegevens te **controleren.**

## <a name="optical-character-recognition"></a>Optische tekenherkenning

Wanneer u zoekresultaten toevoegt aan een revisieset, worden met ocr-functionaliteit (Optical Character Recognition) in Advanced eDiscovery automatisch tekst uit afbeeldingen gehaald en wordt de afbeeldingstekst met de gegevens die aan een revisieset zijn toegevoegd, toegevoegd. U kunt de uitgepakte tekst weergeven in de tekstviewer van het geselecteerde afbeeldingsbestand in de revisieset. Op deze manier kunt u tekst in afbeeldingen verder bekijken en analyseren. OCR wordt ondersteund voor losse bestanden, e-mailbijlagen en ingesloten afbeeldingen. Zie Ondersteunde bestandstypen in Advanced eDiscovery voor een lijst met [afbeeldingsbestandsindelingen](supported-filetypes-ediscovery20.md#image)die worden ondersteund voor OCR.

U moet OCR-functionaliteit inschakelen voor elk geval dat u maakt in Advanced eDiscovery. Zie Zoek- en [analyseinstellingen configureren](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr)voor meer informatie.
