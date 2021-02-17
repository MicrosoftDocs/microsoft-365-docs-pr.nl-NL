---
title: Microsoft Viva-onderwerpen instellen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Informatie over het instellen van Microsoft Viva-onderwerpen
ms.openlocfilehash: a90e75330527992f8519d625f94fe0d5ecb3de6b
ms.sourcegitcommit: a9ac702c9efc9defded3bfa65618b94bac00c237
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/16/2021
ms.locfileid: "50261467"
---
# <a name="set-up-microsoft-viva-topics"></a>Microsoft Viva-onderwerpen instellen

U kunt het Microsoft 365-beheercentrum gebruiken om Onderwerpen in te stellen en te [configureren.](topic-experiences-overview.md) 

Het is belangrijk om de beste manier te plannen voor het instellen en configureren van onderwerpen in uw omgeving. Lees de Onderwerpen over [Microsoft Viva voordat](plan-topic-experiences.md) u aan de procedures in dit artikel begint.

U moet zijn [geabonneerd op Viva-onderwerpen](https://www.microsoft.com/microsoft-viva/topics) en een globale beheerder of SharePoint-beheerder zijn om toegang te krijgen tot het Microsoft 365-beheercentrum en Onderwerpen in te stellen.

Als u Voor SharePoint beheerde apparaten [hebt](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)geconfigureerd, moet u Onderwerpen instellen vanaf een beheerd apparaat.

## <a name="video-demonstration"></a>Videodemonstratie

In deze video ziet u het proces voor het instellen van Onderwerpen in Microsoft 365.

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="set-up-topics"></a>Onderwerpen instellen

Onderwerpen instellen

1. Selecteer [Setup in het Microsoft 365-beheercentrum](https://admin.microsoft.com) en bekijk de sectie Bestanden **en** inhoud.
2. Klik in **de sectie Bestanden en** inhoud op Personen verbinden met **kennis.**

    ![Personen verbinden met kennis](../media/admin-org-knowledge-options.png) 

3. Klik op **de pagina Personen** verbinden met kennis op **Aan** de slag om u bij het installatieproces te helpen.

    ![Aan de slag](../media/k-get-started.png) 

4. Op de **pagina Kiezen hoe Viva-onderwerpen onderwerpen kunnen vinden,** configureert u onderwerpdetectie. Selecteer in **de sectie SharePoint-onderwerpbronnen** selecteren welke SharePoint-sites tijdens de detectie worden verkend als bronnen voor uw onderwerpen. Kies uit:
    - **Alle sites:** alle SharePoint-sites in uw organisatie. Dit geldt ook voor huidige en toekomstige sites.
    - **Alle, behalve geselecteerde sites:** typ de namen van de sites die u wilt uitsluiten.  U kunt ook een lijst met sites uploaden die u niet wilt ontdekken. Sites die in de toekomst worden gemaakt, worden opgenomen als bronnen voor onderwerpdetectie. 
    - **Alleen geselecteerde sites:** typ de namen van de sites die u wilt opnemen. U kunt ook een lijst met sites uploaden. Sites die in de toekomst worden gemaakt, worden niet opgenomen als bronnen voor onderwerpdetectie.
    - **Geen sites:** Geen SharePoint-sites opnemen.

    ![Kiezen hoe u onderwerpen wilt zoeken](../media/ksetup1.png) 
   
5. In de **sectie Onderwerpen uitsluiten op** naam kunt u namen toevoegen van onderwerpen die u wilt uitsluiten van onderwerpdetectie. Gebruik deze instelling om te voorkomen dat gevoelige informatie wordt opgenomen als onderwerpen. De volgende opties zijn beschikbaar:
    - **Onderwerpen niet uitsluiten** 
    - **Onderwerpen uitsluiten op naam**

    ![Onderwerpen uitsluiten](../media/topics-excluded-by-name.png) 

    (Knowledge Managers kunnen na detectie ook onderwerpen uitsluiten in het onderwerpcentrum.)

    #### <a name="how-to-exclude-topics-by-name"></a>Onderwerpen uitsluiten op naam    

    Als u onderwerpen wilt uitsluiten, selecteert u Onderwerpen uitsluiten op **naam,** downloadt u de CSV-sjabloon en werk u deze bij met de lijst met onderwerpen die u wilt uitsluiten van uw discovery-resultaten.

    ![Onderwerpen uitsluiten in CSV-sjabloon](../media/exclude-topics-csv.png) 

    Voer in de CSV-sjabloon de volgende informatie in over de onderwerpen die u wilt uitsluiten:

    - **Naam:** typ de naam van het onderwerp dat u wilt uitsluiten. U kunt dit op twee manieren doen:
        - Exacte overeenkomst: u kunt de exacte naam of het acroniem opnemen (bijvoorbeeld *Contoso* of *ATL).*
        - Gedeeltelijke overeenkomst: U kunt alle onderwerpen met een bepaald woord uitsluiten.  Zo worden met *de boog* bijvoorbeeld alle onderwerpen met de *woordcirkel* uitgesloten, zoals Boogcirkel,  *Arc-boog* of *Trainingsbogen.* Onderwerpen waarin de tekst is opgenomen als onderdeel van een woord, zoals Architectuur, worden niet *uitgesloten.*
    - **Staat voor (optioneel:** als u een acroniem wilt uitsluiten, typt u de woorden waar het acroniem voor staat.
    - **MatchType-Exact/Gedeeltelijk:** typ of de naam die u hebt ingevoerd *een exact* of *gedeeltelijk* overeenkomsttype is.

    Nadat u het CSV-bestand hebt voltooid en opgeslagen, selecteert u **Bladeren** om het te zoeken en te selecteren.
    
    Selecteer **Volgende**.

6. Op de **pagina Wie kan onderwerpen zien en waar** zij deze kunnen zien, configureert u de zichtbaarheid van het onderwerp. In de **instelling Wie kan de** onderwerpen zien, kiest u wie toegang heeft tot onderwerpdetails, zoals gemarkeerde onderwerpen, onderwerpkaarten, antwoorden op onderwerp in zoekopdrachten en onderwerppagina's. U kunt het volgende selecteren:
    - **Iedereen in mijn organisatie**
    - **Alleen geselecteerde personen of beveiligingsgroepen**
    - **Niemand**

    ![Wie kan onderwerpen zien?](../media/ksetup2.png)  

    > [!Note] 
    > Hoewel u met deze instelling elke gebruiker in uw organisatie kunt selecteren, kunnen alleen gebruikers aan wie een licentie voor onderwerpervaringen is toegewezen onderwerpen bekijken.

7. Op de **pagina Machtigingen voor** onderwerpbeheer kiest u wie onderwerpen mag maken, bewerken of beheren. In de **sectie Wie kan onderwerpen maken en bewerken,** kunt u het volgende selecteren:
    - **Iedereen in mijn organisatie**
    - **Alleen geselecteerde personen of beveiligingsgroepen**
    - **Niemand**

    ![Machtigingen voor onderwerpbeheer, wie onderwerpen kan maken en bewerken](../media/ksetup3.png) 

8. In de **sectie Wie kan onderwerpen beheren,** kunt u het volgende selecteren:
    - **Iedereen in mijn organisatie**
    - **Alleen geselecteerde personen of beveiligingsgroepen**

    ![Machtigingen voor onderwerpbeheer](../media/km-setup-create-edit-topics.png) 

    Selecteer **Volgende**.

9. Op de **pagina Onderwerpcentrum maken** kunt u uw onderwerpcentrumsite maken waarin onderwerppagina's kunnen worden bekeken en onderwerpen kunnen worden beheerd. Typ in **het vak Sitenaam** een naam voor het onderwerpcentrum. U kunt desgewenst een korte beschrijving typen in het **vak** Beschrijving. 

   Selecteer **Volgende**.

   ![Knowledge Center maken](../media/ksetup4.png)  

10. Op de pagina **Controleren en voltooien** kunt u de geselecteerde instelling bekijken en wijzigingen aanbrengen. Selecteer **Activeren** wanneer u tevreden bent met uw selecties.

11. De **pagina van Viva-onderwerpen** die is geactiveerd, wordt weergegeven en bevestigt dat het systeem nu de geselecteerde sites gaat analyseren voor onderwerpen en de onderwerpcentrumsite gaat maken. Selecteer **Gereed**.

12. U keert terug naar de **pagina Personen verbinden met kennis.** Op deze pagina kunt u **Beheren** selecteren om wijzigingen aan te brengen in de configuratie-instellingen. 

    ![Instellingen toegepast](../media/ksetup7.png)    

## <a name="assign-licenses"></a>Licenties toewijzen

Nadat u onderwerpervaringen hebt geconfigureerd, moet u licenties toewijzen voor de gebruikers die Onderwerpen gebruiken. Alleen gebruikers met een licentie kunnen informatie zien over onderwerpen zoals highlights, onderwerpkaarten, onderwerppagina's en het onderwerpcentrum. 

Licenties toewijzen:

1. Klik in het Microsoft 365-beheercentrum onder **Gebruikers** op **Actieve gebruikers**.

2. Selecteer de gebruikers die u een licentie wilt geven en klik op **Licenties en apps.**

3. Zorg **ervoor** dat **Graph Connectors Zoeken met Index** en **Onderwerpervaringen** zijn geselecteerd onder Apps.

4. Klik op **Wijzigingen opslaan**.

## <a name="manage-topic-experiences"></a>Onderwerpervaringen beheren

Nadat u Onderwerpen hebt ingesteld, kunt u de instellingen wijzigen die u tijdens de installatie hebt gekozen in het [Microsoft 365-beheercentrum.](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement) Zie de volgende referenties:

- [Onderwerpdetectie beheren in Microsoft Viva-onderwerpen](topic-experiences-discovery.md)
- [Zichtbaarheid van onderwerpen beheren in Microsoft Viva-onderwerpen](topic-experiences-knowledge-rules.md)
- [Onderwerpmachtigingen beheren in Microsoft Viva-onderwerpen](topic-experiences-user-permissions.md)
- [De naam van het onderwerpcentrum wijzigen in Microsoft Viva-onderwerpen](topic-experiences-administration.md)

## <a name="see-also"></a>Zie ook

[Overzicht van onderwerpervaringen](topic-experiences-overview.md)
