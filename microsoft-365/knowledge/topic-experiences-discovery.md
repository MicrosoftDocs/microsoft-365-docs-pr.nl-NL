---
title: Onderwerpdetectie beheren in Microsoft Viva-onderwerpen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Informatie over het beheren van onderwerpdetectie in Microsoft Viva-onderwerpen.
ms.openlocfilehash: 36b64433726479dc2a46c809ae9504c6f12f4ab8
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107757"
---
# <a name="manage-topic-discovery-in-microsoft-viva-topics"></a>Onderwerpdetectie beheren in Microsoft Viva-onderwerpen

U kunt instellingen voor onderwerpdetectie beheren in het [Microsoft 365-beheercentrum.](https://admin.microsoft.com) U moet een globale beheerder of SharePoint-beheerder zijn om deze taken uit te voeren.

## <a name="to-access-topics-management-settings"></a>Voor toegang tot instellingen voor onderwerpenbeheer:

1. Klik in het Microsoft 365-beheercentrum op **Instellingen** en vervolgens **op Organisatie-instellingen.**
2. Klik op **het tabblad** Services op **Onderwerpervaringen.**

    ![Personen verbinden met kennis](../media/admin-org-knowledge-options-completed.png) 

3. Selecteer het **tabblad Onderwerpdetectie.** Zie de volgende secties voor meer informatie over elke instelling.

    ![knowledge-network-settings](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a>SharePoint-onderwerpbronnen selecteren

U kunt de SharePoint-sites in uw organisatie wijzigen die worden verkend voor onderwerpen.

Als u een specifieke lijst met sites wilt opnemen of uitsluiten, kunt u de volgende CSV-sjabloon gebruiken:

``` csv
Site name,URL
```

Als u sites toevoegt met behulp van de site picker, worden deze toegevoegd aan de bestaande lijst met sites die u wilt opnemen of uitsluiten. Als u een CSV-bestand uploadt, wordt elke bestaande lijst overschreven. Als u eerder specifieke sites hebt opgenomen of uitgesloten, downloadt en downloadt u de lijst als een CSV-bestand, wijzigt u en uploadt u de nieuwe lijst.

Sites kiezen voor onderwerpdetectie

1. Selecteer Bewerken **op het tabblad** Onderwerpdetectie onder **SharePoint-onderwerpbronnen** **selecteren.**
2. Selecteer op **de pagina SharePoint-onderwerpbronnen** selecteren welke SharePoint-sites tijdens de detectie worden verkend als bronnen voor uw onderwerpen. Dit omvat:
    - **Alle sites:** alle SharePoint-sites in uw tenant. Hiermee worden huidige en toekomstige sites vastleggen.
    - **Alle, behalve geselecteerde sites:** typ de namen van de sites die u wilt uitsluiten.  U kunt ook een lijst met sites uploaden die u niet wilt ontdekken. Sites die in de toekomst worden gemaakt, worden opgenomen als bronnen voor onderwerpdetectie. 
    - **Alleen geselecteerde sites:** typ de namen van de sites die u wilt opnemen. U kunt ook een lijst met sites uploaden. Sites die in de toekomst worden gemaakt, worden niet opgenomen als bronnen voor onderwerpdetectie.
    - **Geen sites:** onderwerpen worden niet automatisch gegenereerd of bijgewerkt met SharePoint-inhoud. Bestaande onderwerpen blijven in het onderwerpcentrum staan.

    ![Schermafbeelding van de gebruikersinterface van SharePoint-onderwerpbronnen](../media/k-manage-select-topic-source.png)
   
3. Klik op **Opslaan**.

## <a name="exclude-topics-by-name"></a>Onderwerpen uitsluiten op naam

U kunt onderwerpen uitsluiten van detectie door een lijst te uploaden met een CSV-bestand. Als u eerder onderwerpen hebt uitgesloten, kunt u het CSV-bestand downloaden, wijzigingen aanbrengen en opnieuw uploaden.

1. Selecteer Bewerken **op het tabblad** Onderwerpdetectie onder **Onderwerpen** **uitsluiten.**
2. Klik **op Onderwerpen uitsluiten op naam.**
3. Als u een lijst moet maken, downloadt u de CSV-sjabloon en voegt u de onderwerpen toe die u wilt uitsluiten (zie Werken met de *CSV-sjabloon* hieronder). Wanneer het bestand klaar is, klikt u **op Bladeren en** het bestand uploaden. Als er een bestaande lijst is, kunt u het CSV-bestand downloaden dat de lijst bevat.
4. Klik op **Opslaan**.

    ![Schermafbeelding van de gebruikersinterface voor het uitsluiten van onderwerpen](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a>Werken met de CSV-sjabloon

U kunt de csv-sjabloon hieronder kopiëren:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

Voer in de CSV-sjabloon de volgende informatie in over de onderwerpen die u wilt uitsluiten:

- **Naam:** typ de naam van het onderwerp dat u wilt uitsluiten. U kunt dit op twee manieren doen:
    - Exacte overeenkomst: u kunt de exacte naam of het acroniem opnemen (bijvoorbeeld *Contoso* of *ATL).*
    - Gedeeltelijke overeenkomst: U kunt alle onderwerpen met een specifiek woord uitsluiten.  Zo worden met *de boog* bijvoorbeeld alle onderwerpen met de *woordcirkel* uitgesloten, zoals Boogcirkel,  *Arc-boog* of *Trainingsbogen.* Onderwerpen waarin de tekst is opgenomen als onderdeel van een woord, zoals Architectuur, worden niet *uitgesloten.*
- **Staat voor (optioneel:** als u een acroniem wilt uitsluiten, typt u de woorden waar het acroniem voor staat.
- **MatchType-Exact/Gedeeltelijk:** typ of de naam die u hebt ingevoerd *een exact* of *gedeeltelijk* overeenkomsttype is.

    ![Onderwerpen uitsluiten in CSV-sjabloon](../media/exclude-topics-csv.png) 

## <a name="see-also"></a>Zie ook

[Zichtbaarheid van onderwerpen beheren in Microsoft 365](topic-experiences-knowledge-rules.md)

[Onderwerpmachtigingen beheren in Microsoft 365](topic-experiences-user-permissions.md)

[De naam van het onderwerpcentrum wijzigen in Microsoft 365](topic-experiences-administration.md)
