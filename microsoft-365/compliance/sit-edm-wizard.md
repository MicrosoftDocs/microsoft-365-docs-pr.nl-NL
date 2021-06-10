---
title: De wizard voor het schema voor exacte gegevensovereenkomst en het type gevoelige informatie gebruiken
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Leer hoe u de wizard voor het schema voor exacte gegevensovereenkomst en het type gevoelige informatie gebruikt.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5fdf289c403d8c09342a1eac1434c4219bb7b13c
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861657"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a>De wizard voor het schema voor exacte gegevensovereenkomst en het type gevoelige informatie gebruiken

[Het maken van een aangepast type gevoelige informatie met EDM-gebaseerde (exacte gegevensovereenkomst) classificatie](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) bestaat uit vele stappen.  U kunt deze wizard gebruiken om bestanden met het schema en het gevoelige informatietype (SIT)-patroon (regelpakket) te maken om het proces te vereenvoudigen.

> [!NOTE]
> De wizard voor het schema voor exacte gegevensovereenkomst en het type gevoelige informatie is alleen beschikbaar voor de wereldwijde en GCC-cloud.

Deze wizard kan worden gebruikt in plaats van de:

- [Het schema voor uw database met gevoelige informatie definiëren](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [Een patroon (regelpakket) instellen](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

stappen in [Deel 1: EDM-gebaseerde classificatie instellen](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).

## <a name="pre-requisites"></a>Vereisten

1. Maak uzelf bekend met de stappen voor het maken van een aangepast type gevoelige informatie met EDM [werkstroom in een oogopslag](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).

2. Voer de stappen uit in de sectie [Gevoelige gegevens opslaan in CSV-indeling](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format).

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a>De wizard voor het schema voor exacte gegevensovereenkomst en het patroon voor het type gevoelige informatie gebruiken

1. Ga in het Microsoft 365-compliancecentrum voor uw tenant naar **Gegevensclassificatie** > **Exacte gegevensoverkomsten**.

2. Kies **EDM-schema maken** om de configuratie-flyout van de wizard te openen.

![Configuratie-flyout van de wizard EDM-schema maken](../media/edm-schema-wizard-1.png)

3. Vul een toepasselijke **Naam** en **Beschrijving** in.

4. Kies **Scheidingstekens en interpunctie negeren** voor alle schemavelden als u dat wilt. Zie Een aangepast type gevoelige informatie maken met de classificatie [Exact Data Match (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)voor meer informatie over het configureren van EDM om case's of scheidingstekens te negeren.

5. Vul de gewenste waarden in voor uw **Schemaveld #1** en voeg zo nodig meer velden toe. 

> [!IMPORTANT]
> Ten minste één (maar niet meer dan vijf) van uw schemavelden moet worden aangewezen als doorzoekbaar.

6. Kies Opslaan. Uw schema wordt nu vermeld.

7. Kies **Typen gevoelige informatie met EDM** en **Type gevoelige informatie met EDM maken** om de configuratiewizard voor typen gevoelige informatie te openen.

8. Kies **Een bestaand EDM-schema kiezen** en kies het schema dat u in stap 2-6 hebt gemaakt uit de lijst.

9. Kies **Volgende** en kies **Patroon maken**.

10. Kies het **Betrouwbaarheidsniveau** en **Primaire element**.  Zie [Een aangepast type gevoelige informatie maken in het Compliancecentrum](create-a-custom-sensitive-information-type.md) voor meer informatie over het configureren van een patroon.

11.  Kies het **Type gevoelige informatie van het primaire element** waaraan het moet worden gekoppeld. Zie [Entiteitsdefinities van typen gevoelige informatie](sensitive-information-type-entity-definitions.md) voor meer informatie over de beschikbare typen gevoelige informatie.

12. Kies **Gereed**.

13. Kies uw gewenste **Betrouwbaarheidsniveau en tekennabijheid**.  Dit is de standaardwaarde voor het hele type gevoelige informatie met EDM

13. Kies **Patroon maken** als u extra patronen wilt maken voor uw EDM-gevoelige informatietype.

14. Kies **Volgende** en vul een **Naam** en **Beschrijving voor beheerders** in.

15. Controleer uw invoer en kies **Verzenden**.

U kunt het patroon voor het type gevoelige informatie verwijderen of bewerken door het te selecteren, waarna de besturingselementen voor bewerken en verwijderen worden weergegeven.

> [!IMPORTANT]
> Als u een schema wilt verwijderen dat al is gekoppeld aan een type gevoelige informatie met EDM, moet u eerst het type gevoelige informatie met EDM verwijderen. Vervolgens kunt u het schema verwijderen.

## <a name="post-creation-steps"></a>Stappen voor het maken van berichten

Nadat u deze wizard hebt gebruikt om uw EDM-schema en patroonbestanden (regelpakket) te maken, moet u nog steeds de stappen in [Deel 2: De gevoelige gegevens hashen en uploaden](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) uitvoeren voordat u het aangepaste type gevoelige informatie met EDM kunt gebruiken.

Nadat u hebt gecontroleerd of de tabel met gevoelige informatie correct is geüpload, kunt u testen of deze correct werkt.

1. Open **Compliancecentrum**  >  **Gegevensclassificatie**  >  **Gevoelige informatietypen**.
2. Selecteer uw EDM SIT in de lijst en selecteer **vervolgens Testen** in het deelvenster Flyout. 
3. Upload item dat gegevens bevat die u wilt detecteren, bijvoorbeeld een item maken dat een deel van de gegevens in de tabel met gevoelige informatie bevat. Als u de configureerbare overeenkomstfunctie in uw schema hebt gebruikt om genegeerde scheidingstekens te definiëren, moet u ervoor zorgen dat het item voorbeelden bevat met en zonder deze scheidingstekens.
4. Nadat het bestand is geüpload en gescand, controleert u op overeenkomsten met uw EDM SIT.
5. Als de **functie Test** in de SIT een overeenkomst detecteert, controleert u of deze niet wordt bijgesneden of niet onjuist wordt geëxtraheert. Bijvoorbeeld door alleen een subtekenreeks op te halen van de volledige tekenreeks die deze moet detecteren, of door alleen het eerste woord in een tekenreeks met meerdere woorden op te halen, of door extra symbolen of tekens in de extractie op te nemen. Zie [Normale expressietaal - Snelle verwijzing voor](/dotnet/standard/base-types/regular-expression-language-quick-reference) de reguliere verwijzing naar expressietaal. 

### <a name="troubleshooting"></a>Problemen oplossen

Als u geen overeenkomsten vindt, gaat u als volgt te werk:
- Controleer of uw gevoelige gegevens correct zijn geüpload met behulp van de opdrachten die worden uitgelegd in de richtlijnen voor het uploaden van uw gevoelige gegevens met het [hulpprogramma EDM.](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- Controleer of de voorbeelden die u hebt ingevoerd in het item aanwezig zijn in de tabel met gevoelige informatie en of de genegeerde scheidingstekens juist zijn.
- **Test** de SIT die u hebt gebruikt bij het configureren van het primaire element in elk van uw patronen. Hiermee wordt bevestigd dat de SIT kan overeenkomen met de voorbeelden in het item. 
  -  Als de SIT die u hebt geselecteerd voor een primair element in het EDM-type, geen overeenkomst in het item vindt of minder overeenkomsten vindt dan u verwacht, controleert u of het scheidingstekens en scheidingstekens ondersteunt die in de inhoud aanwezig zijn. Zorg ervoor dat u de genegeerde scheidingstekens in uw schema op moet nemen. 
  -  Als de **functie Test** helemaal geen inhoud detecteert, controleert u of de sit die u hebt geselecteerd vereisten bevat voor aanvullende trefwoorden of andere validaties. Zie Entiteitsdefinities voor [](sensitive-information-type-entity-definitions.md) gevoelige informatietypen voor de ingebouwde ST's om te controleren wat de minimumvereisten zijn voor het overeenkomen van elk type.
