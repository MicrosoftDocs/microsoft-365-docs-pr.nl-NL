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
description: Meer informatie over het beheren van onderwerpdetectie in Microsoft Viva-onderwerpen.
ms.openlocfilehash: 53e304dc69ccf2ca6fe01d29f0997c539406b0fe
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768972"
---
# <a name="manage-topic-discovery-in-microsoft-viva-topics"></a>Onderwerpdetectie beheren in Microsoft Viva-onderwerpen

U kunt de instellingen voor onderwerpdetectie beheren in [het Microsoft 365 beheercentrum.](https://admin.microsoft.com) U moet een globale beheerder of SharePoint zijn om deze taken uit te voeren.

## <a name="to-access-topics-management-settings"></a>Toegang tot de instellingen voor onderwerpenbeheer:

1. Klik in Microsoft 365 beheercentrum **op** Instellingen en vervolgens **op Organisatie-instellingen.**
2. Klik op **het tabblad** Services op **Onderwerpervaringen.**

    ![Verbinding maken mensen kennis te laten maken](../media/admin-org-knowledge-options-completed.png) 

3. Selecteer het **tabblad Onderwerpdetectie.** Zie de volgende secties voor informatie over elke instelling.

    ![knowledge-network-settings](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a>Selecteer SharePoint onderwerpbronnen

U kunt de SharePoint sites in uw organisatie wijzigen die worden verkend voor onderwerpen.

Als u een specifieke lijst met sites wilt opnemen of uitsluiten, kunt u de volgende .csv gebruiken:

``` csv
Site name,URL
```

Als u sites toevoegt met de site picker, worden deze toegevoegd aan de bestaande lijst met sites die u wilt opnemen of uitsluiten. Als u een .csv uploadt, wordt elke bestaande lijst overschreven. Als u eerder specifieke sites hebt opgenomen of uitgesloten, kunt u de lijst als een .csv downloaden, wijzigingen aanbrengen en de nieuwe lijst uploaden.

Sites kiezen voor onderwerpdetectie

1. Selecteer op **het tabblad** Onderwerpdetectie onder Selecteer **SharePoint onderwerpbronnen** de optie **Bewerken.**
2. Selecteer op **de pagina SharePoint onderwerpbronnen** selecteren welke sites SharePoint worden verkend als bronnen voor uw onderwerpen tijdens de detectie. Dit zijn:
    - **Alle sites:** Alle SharePoint sites in uw tenant. Hiermee worden huidige en toekomstige sites vastleggen.
    - **Alle, behalve geselecteerde sites:** Typ de namen van de sites die u wilt uitsluiten.  U kunt ook een lijst uploaden met sites die u niet wilt ontdekken. Sites die in de toekomst worden gemaakt, worden opgenomen als bronnen voor onderwerpdetectie. 
    - **Alleen geselecteerde sites:** Typ de namen van de sites die u wilt opnemen. U kunt ook een lijst met sites uploaden. Sites die in de toekomst worden gemaakt, worden niet opgenomen als bronnen voor onderwerpdetectie.
    - **Geen sites:** Onderwerpen worden niet automatisch gegenereerd of bijgewerkt met SharePoint inhoud. Bestaande onderwerpen blijven in het onderwerpcentrum staan.

    ![Schermafbeelding van SharePoint gebruikersinterface van onderwerpbronnen](../media/k-manage-select-topic-source.png)
   
3. Klik op **Opslaan**.

## <a name="exclude-topics-by-name"></a>Onderwerpen uitsluiten op naam

U kunt onderwerpen uitsluiten van detectie door een lijst te uploaden met een .csv bestand. Als u eerder onderwerpen hebt uitgesloten, kunt u de .csv downloaden, wijzigingen aanbrengen en opnieuw uploaden.

1. Selecteer op **het tabblad** Onderwerpdetectie onder **Onderwerpen uitsluiten** de optie **Bewerken.**
2. Klik **op Onderwerpen uitsluiten op naam.**
3. Als u een lijst wilt maken, downloadt u de .csv sjabloon en voegt u de onderwerpen toe die u wilt uitsluiten (zie Werken met de *.csv sjabloon* hieronder). Wanneer het bestand gereed is, klikt u **op Bladeren** en uploadt u het bestand. Als er een bestaande lijst is, kunt u de .csv met de lijst downloaden.
4. Klik op **Opslaan**.

    ![Schermafbeelding van de gebruikersinterface van onderwerpen uitsluiten](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a>Werken met de .csv sjabloon

U kunt de csv-sjabloon hieronder kopiëren:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

Voer in de CSV-sjabloon de volgende informatie in over de onderwerpen die u wilt uitsluiten:

- **Naam:** Typ de naam van het onderwerp dat u wilt uitsluiten. U kunt dit op twee manieren doen:
    - Exacte overeenkomst: U kunt de exacte naam of acroniem uitsluiten (bijvoorbeeld *Contoso* of *ATL).*
    - Gedeeltelijke overeenkomst: U kunt alle onderwerpen met een specifiek woord uitsluiten.  Met een *boog worden bijvoorbeeld* alle onderwerpen uitgesloten met de woordboog in de boog, zoals boogcirkel, lassen van de boog van Het *plasma* of *Trainingsboog.*   Houd er rekening mee dat onderwerpen waarin de tekst is opgenomen als onderdeel van een woord, zoals Architectuur, niet worden *uitgesloten.*
- **Staat voor (optioneel)**: Als u een acroniem wilt uitsluiten, typt u de woorden waar het acroniem voor staat.
- **MatchType-Exact/Gedeeltelijk:** Typ of de opgegeven naam *een exact* of *gedeeltelijk overeenkomend* type was.

    ![Onderwerpen uitsluiten in CSV-sjabloon](../media/exclude-topics-csv.png) 

## <a name="see-also"></a>Zie ook

[Zichtbaarheid van onderwerp beheren in Microsoft 365](topic-experiences-knowledge-rules.md)

[Onderwerpmachtigingen beheren in Microsoft 365](topic-experiences-user-permissions.md)

[De naam van het onderwerpcentrum wijzigen in Microsoft 365](topic-experiences-administration.md)
