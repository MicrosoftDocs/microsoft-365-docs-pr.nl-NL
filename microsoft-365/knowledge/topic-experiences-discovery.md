---
title: Detectie van onderwerp beheren in Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Meer informatie over het beheren van topic Discovery in Microsoft 365.
ms.openlocfilehash: dec8aeef9dda390fb19f5067638c2ebea6b6a2fe
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698541"
---
# <a name="manage-topic-discovery-in-microsoft-365"></a>Detectie van onderwerp beheren in Microsoft 365

U kunt de instellingen voor de detectie van het onderwerp beheren in het [Microsoft 365-Beheercentrum](https://admin.microsoft.com). U moet een globale beheerder of SharePoint-beheerder zijn om deze taken uit te voeren.

## <a name="to-access-topics-management-settings"></a>De instellingen voor het beheer van onderwerpen raadplegen:

1. Klik in het Microsoft 365-Beheercentrum op **instellingen** en vervolgens op **organisatie-instellingen**.
2. Klik op het tabblad **Services** op **kennis netwerk**.

    ![Mensen verbinden met kennis](../media/admin-org-knowledge-options-completed.png) 

3. Selecteer het tabblad **detectie van onderwerp** . Zie de volgende secties voor informatie over elke instelling.

    ![kennis netwerk-instellingen](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a>Selecteer SharePoint-onderwerpen bronnen

U kunt de SharePoint-sites in uw organisatie wijzigen die worden verkend voor onderwerpen.

Als u een bepaalde lijst met sites wilt opnemen of uitsluiten, kunt u de volgende CSV-sjabloon gebruiken:

``` csv
Site name,URL
```

Als u sites toevoegt met behulp van de site kiezer, worden deze toegevoegd aan de bestaande lijst met sites die u wilt opnemen of uitsluiten. Als u een CSV-bestand uploadt, wordt een bestaande lijst overschreven. Als u eerder specifieke sites hebt opgenomen of uitgesloten, downloadt u de lijst als een. CSV-bestand, brengt u wijzigingen aan en uploadt u de nieuwe lijst.

Sites kiezen voor detectie van een onderwerp

1. Selecteer op het tabblad **topic Discovery** onder **Select SharePoint topics** de optie **Edit**.
2. Selecteer op de pagina **SharePoint-onderwerpen selecteren** welke SharePoint-sites worden verkend als bronnen voor uw onderwerpen tijdens de detectie. Dit omvat:
    - **Alle sites**: alle SharePoint-sites in de Tenant. Hiermee worden de huidige en toekomstige sites vastgelegd.
    - **Alles, met uitzondering van geselecteerde sites**: Typ de namen van de sites die u wilt uitsluiten.  U kunt ook een lijst uploaden met sites die u wilt afmelden bij ontdekking. Sites die u later maakt, worden opgenomen als bronnen voor het detecteren van het onderwerp. 
    - **Alleen geselecteerde sites**: Typ de namen van de sites die u wilt opnemen. U kunt ook een lijst met sites uploaden. Sites die u later maakt, worden niet opgenomen als bronnen voor de detectie van het onderwerp.
    - **Geen sites**: onderwerpen worden niet automatisch aangemaakt of bijgewerkt met SharePoint-inhoud. Bestaande onderwerpen blijven behouden in het onderwerp centrum.

    ![Schermafbeelding van de gebruikersinterface van de SharePoint-onderwerp bronnen](../media/k-manage-select-topic-source.png)
   
3. Klik op **Opslaan**.

## <a name="exclude-topics-by-name"></a>Onderwerpen uitsluiten op naam

U kunt onderwerpen uitsluiten van detectie door een lijst te uploaden met een. CSV-bestand. Als u eerder uitgesloten onderwerpen hebt, kunt u het CSV-bestand downloaden, wijzigingen aanbrengen en opnieuw uploaden.

1. Selecteer op het tabblad **onderwerp detecteren** onder **onderwerpen uitsluiten** de optie **bewerken**.
2. Klik op **onderwerpen uitsluiten op naam**.
3. Als u een lijst wilt maken, downloadt u de. CSV-sjabloon en voegt u de onderwerpen toe die u wilt uitsluiten (Zie *werken met de. CSV-sjabloon* hieronder). Wanneer het bestand klaar is, klikt u op **Bladeren** en uploadt u het bestand. Als u een bestaande lijst hebt, kunt u het. CSV-bestand met de lijst downloaden.
4. Klik op **Opslaan**.

    ![Schermafbeelding van de gebruikersinterface van de onderdelen uitsluiten](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a>Werken met de. CSV-sjabloon

U kunt de onderstaande CSV-sjabloon kopiëren:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

Voer de volgende informatie over de onderwerpen die u wilt uitsluiten in het CSV-sjabloon in:

- **Naam**: Typ de naam van het onderwerp dat u wilt uitsluiten. U kunt dit op twee manieren doen:
    - Exacte overeenkomst: u kunt de exacte naam of het acroniem opnemen, bijvoorbeeld *Contoso* of *ATL*.
    - Gedeeltelijke overeenkomst: u kunt alle onderwerpen met een specifiek woord uitsluiten.  Met de *boog* worden bijvoorbeeld alle onderwerpen met het woord *boog* weggelaten, zoals *boog cirkel*, *plasma boog lassen* of *boog boog*. Houd er rekening mee dat onderwerpen waarvan de tekst deel uitmaakt van een woord, zoals de *architectuur*, niet worden uitgesloten.
- **Staat voor (optioneel)**: als u een acroniem wilt uitsluiten, typt u de woorden waarop het acroniem staat.
- **MatchType-exact/gedeeltelijk**: Typ of de ingevoerde naam een *exact* of *gedeeltelijk* overeenkomend type is.

    ![Onderwerpen in CSV-sjabloon uitsluiten](../media/exclude-topics-csv.png) 

## <a name="see-also"></a>Zie ook

[De zichtbaarheid van een onderwerp beheren in Microsoft 365](topic-experiences-knowledge-rules.md)

[Machtigingen voor onderwerp beheren in Microsoft 365](topic-experiences-user-permissions.md)

[De naam van het onderwerp centreren in Microsoft 365](topic-experiences-administration.md)
