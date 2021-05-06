---
title: De wizard voor het schema voor exacte gegevensovereenkomst en het type gevoelige informatie gebruiken
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Leer hoe u de wizard voor het schema voor exacte gegevensovereenkomst en het type gevoelige informatie gebruikt.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2081de887e09794350222dac3527bb3ff932837a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/16/2020
ms.locfileid: "52161556"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a>De wizard voor het schema voor exacte gegevensovereenkomst en het type gevoelige informatie gebruiken

[Het maken van een aangepast type gevoelige informatie met EDM-gebaseerde (exacte gegevensovereenkomst) classificatie](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) bestaat uit vele stappen.  U kunt deze wizard gebruiken om uw patroonbestanden (regelpakket) voor het schema en het type gevoelige informatie te maken om het proces te vereenvoudigen.

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

4. Kies **Scheidingstekens en leestekens negeren voor alle schemavelden** als u dat wilt. Zie [Een aangepast type gevoelige informatie maken met EDM-gebaseerde (exacte gegevensovereenkomst) classificatie](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) voor meer informatie over het configureren van EDM om hoofdletters of scheidingsteken te negeren.

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

13. Kies **Patroon maken** als u aanvullende patronen wilt maken voor uw type gevoelige informatie met EDM.

14. Kies **Volgende** en vul een **Naam** en **Beschrijving voor beheerders** in.

15. Controleer uw invoer en kies **Verzenden**.

U kunt het patroon voor het type gevoelige informatie verwijderen of bewerken door het te selecteren, waarna de besturingselementen voor bewerken en verwijderen worden weergegeven.

> [!IMPORTANT]
> Als u een schema wilt verwijderen dat al is gekoppeld aan een type gevoelige informatie met EDM, moet u eerst het type gevoelige informatie met EDM verwijderen. Vervolgens kunt u het schema verwijderen.

## <a name="post-steps"></a>Volgende stappen

Nadat u deze wizard hebt gebruikt om uw EDM-schema en patroonbestanden (regelpakket) te maken, moet u nog steeds de stappen in [Deel 2: De gevoelige gegevens hashen en uploaden](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) uitvoeren voordat u het aangepaste type gevoelige informatie met EDM kunt gebruiken.