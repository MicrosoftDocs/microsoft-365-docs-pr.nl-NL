---
title: Onderwerpen over functies instellen in Microsoft 365
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
description: Meer informatie over het instellen van onderwerps functies in Microsoft 365
ms.openlocfilehash: df4dccead4b627a215ec7ebd11932aa0f2b6ac08
ms.sourcegitcommit: 18f95c4b7f74881b4a6ce71ad2ffa78a6ead5584
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731365"
---
# <a name="set-up-topic-experiences-in-microsoft-365"></a>Onderwerpen over functies instellen in Microsoft 365

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LBp7]  

</br>

Met het Microsoft 365-Beheercentrum kunt u [topic Experience](topic-experiences-overview.md)instellen en configureren. 

Het is belangrijk dat u de beste manier voor het plannen en configureren van onderwerpen in uw omgeving van plan bent. Zorg ervoor dat u de ervaringen van het [plan](plan-topic-experiences.md) vindt voordat u de procedures in dit artikel start.

U moet een globale beheerder of SharePoint-beheerder zijn om toegang te krijgen tot het Microsoft 365-Beheercentrum en de functies voor het onderwerp in te stellen.

## <a name="set-up-topic-experiences"></a>Onderwerpservaringen instellen

Topic Experience instellen in Microsoft 365

1. Selecteer in het [Microsoft 365-Beheercentrum](https://admin.microsoft.com)de optie **Setup** en vervolgens de sectie **bestanden en inhoud** weergeven.
2. Klik in de sectie **bestanden en inhoud** op **personen verbinden met kennis**.

    ![Mensen verbinden met kennis](../media/admin-org-knowledge-options.png) 

3. Klik op de pagina **personen verbinden met kennis** op aan de slag om u door te **gaan** met het instellen van het installatieproces.

    ![Aan de slag](../media/k-get-started.png) 

4. Ga naar de pagina **Kies hoe u de pagina wilt zoeken** in het onderwerp: detectie van een kennis netwerk. Selecteer in de sectie **SharePoint-onderwerpen selecteren** welke SharePoint-sites worden verkend als bronnen voor uw onderwerpen tijdens de detectie. Kies uit:
    - **Alle sites**: alle SharePoint-sites in uw organisatie. Dit geldt ook voor huidige en toekomstige sites.
    - **Alles, met uitzondering van geselecteerde sites**: Typ de namen van de sites die u wilt uitsluiten.  U kunt ook een lijst uploaden met sites die u wilt afmelden bij ontdekking. Sites die in de toekomst zijn gemaakt, worden opgenomen als bronnen voor de detectie van het onderwerp. 
    - **Alleen geselecteerde sites**: Typ de namen van de sites die u wilt opnemen. U kunt ook een lijst met sites uploaden. Sites die u later maakt, worden niet opgenomen als bronnen voor de detectie van het onderwerp.
    - **Geen sites**: geen SharePoint-sites opnemen.

    ![Kiezen hoe u onderwerpen kunt zoeken](../media/ksetup1.png) 
   
5. In de sectie **onderwerpen uitsluiten van naam** kunt u namen van onderwerpen toevoegen die u wilt uitsluiten van het detecteren van het onderwerp. Met deze instelling kunt u voorkomen dat vertrouwelijke informatie wordt opgenomen in de onderwerpen. De opties zijn:
    - **Geen onderwerpen uitsluiten** 
    - **Onderwerpen uitsluiten op naam**

    ![Onderwerpen uitsluiten](../media/topics-excluded-by-name.png) 

    (Kennis managers kunnen onderwerpen in het onderwerp centrum ook uitsluiten na ontdekking.)

    #### <a name="how-to-exclude-topics-by-name"></a>Onderwerpen uitsluiten op naam    

    Als **u onderwerpen moet** uitsluiten, selecteert u de sjabloon. csv downloaden en bijwerken met de lijst met onderwerpen die u wilt uitsluiten van de resultaten van de zoekresultaten.

    ![Onderwerpen in CSV-sjabloon uitsluiten](../media/exclude-topics-csv.png) 

    Voer de volgende informatie over de onderwerpen die u wilt uitsluiten in het CSV-sjabloon in:

    - **Naam**: Typ de naam van het onderwerp dat u wilt uitsluiten. U kunt dit op twee manieren doen:
        - Exacte overeenkomst: u kunt de exacte naam of het acroniem opnemen, bijvoorbeeld *Contoso* of *ATL*.
        - Gedeeltelijke overeenkomst: u kunt alle onderwerpen met een specifiek woord uitsluiten.  Met de *boog* worden bijvoorbeeld alle onderwerpen met het woord *boog* weggelaten, zoals *boog cirkel*, *plasma boog lassen* of *boog boog*. Houd er rekening mee dat onderwerpen waarvan de tekst deel uitmaakt van een woord, zoals de *architectuur*, niet worden uitgesloten.
    - **Staat voor (optioneel)**: als u een acroniem wilt uitsluiten, typt u de woorden waarop het acroniem staat.
    - **MatchType-exact/gedeeltelijk**: Typ of de ingevoerde naam een *exact* of *gedeeltelijk* overeenkomend type is.

    Wanneer u het CSV-bestand hebt voltooid en opgeslagen, selecteert u **Bladeren** om naar het bestand te zoeken en te selecteren.
    
    Selecteer **Volgende**.

6. Als u in de sectie **wie kan de onderwerpen zien en waar kan ze** de pagina zien, wordt de zichtbaarheid van het onderwerp geconfigureerd. In de instelling **wie kan de onderwerpen zien in de instelling van het kennis netwerk** , kiest u wie toegang heeft tot de details van het onderwerp, zoals gemarkeerde onderwerpen, topic cards, onderwerp Answers in Search en topic Pages. U kunt kiezen voor:
    - **Iedereen binnen mijn organisatie**
    - **Alleen geselecteerde personen of beveiligingsgroepen**
    - **Niemand**

    ![Wie kan onderwerpen zien?](../media/ksetup2.png)  

 > [!Note] 
 > Met deze instelling kunt u een gebruiker in de organisatie selecteren, zodat alleen gebruikers met een onderwerp licenties die aan hen zijn toegewezen, onderwerpen kunnen weergeven.

7. Op de pagina **machtigingen voor onderwerp beheren** kiest u wie onderwerpen kan maken, bewerken en beheren. In de sectie **wie kan onderwerpen maken en bewerken** , kunt u het volgende selecteren:
    - **Iedereen binnen mijn organisatie**
    - **Alleen geselecteerde personen of beveiligingsgroepen**
    - **Niemand**

    ![Machtigingen voor het beheer van onderwerpen, die onderwerpen kunnen maken en bewerken](../media/ksetup3.png) 

8. In de sectie **wie kan secties beheren** , kunt u het volgende selecteren:
    - **Iedereen binnen mijn organisatie**
    - **Alleen geselecteerde personen of beveiligingsgroepen**

    ![Machtigingen voor onderwerp beheren](../media/km-setup-create-edit-topics.png) 

    Selecteer **Volgende**.

9. Op de pagina **topic maken** kunt u de site van het onderwerp maken waarin de onderwerpen kunnen worden weergegeven en de onderwerpen kunnen worden beheerd. Typ in het vak **site naam** een naam voor het onderwerp Center. U kunt desgewenst een korte beschrijving typen in het vak **Beschrijving** . 

Selecteer **Volgende**.

   ![Kennis centrum maken](../media/ksetup4.png)  

10. Op de pagina **Controleren en voltooien** kunt u de geselecteerde instelling bekijken en wijzigingen aanbrengen. Selecteer **Activeren** wanneer u tevreden bent met uw selecties.

11. De pagina voor **geactiveerde kennis netwerk** wordt weergegeven en u wordt bevestigd dat het systeem nu begint met het analyseren van de geselecteerde sites voor onderwerpen en de site van de Knowledge Center-site maakt. Selecteer **Gereed**.

12. U gaat terug naar de pagina contact **personen verbinden met kennis** . Op deze pagina kunt u **Beheren** selecteren om wijzigingen aan te brengen in de configuratie-instellingen. 

    ![Instellingen toegepast](../media/ksetup7.png)    

## <a name="assign-licenses"></a>Licenties toewijzen

Wanneer u onderwerpen hebt geconfigureerd, moet u een licentie toewijzen voor de gebruikers die gebruikmaken van de functies van het onderwerp. Alleen gebruikers met een licentie kunnen informatie over onderwerpen, waaronder hooglichten, topic cards, topic pagina's en het onderwerp centrum zien. 

Licenties toewijzen:

1. Klik in het Microsoft 365-beheercentrum onder **Gebruikers** op **Actieve gebruikers**.

2. Selecteer de gebruikers aan wie u een licentie wilt toewijzen en klik op **Productlicenties beheren**.

3. Selecteer **Meer toewijzen**.

4. Selecteer onder **licenties** de optie **onderwerp**.

5. Zorg ervoor dat onder **apps** de optie **Graph-verbindingslijnen zoeken met** de functies index en **onderwerp** zijn geselecteerd.

    > [!div class="mx-imgBorder"]
    > ![SharePoint Syntex-licenties in het Microsoft 365-beheercentrum](../media/topic-experiences-licenses.png)

6. Klik op **Wijzigingen opslaan**.

## <a name="manage-topic-experiences"></a>Onderwerp ervaring beheren

Wanneer u de ervaringen met het onderwerp hebt ingesteld, kunt u de instellingen wijzigen die u tijdens de installatie hebt gekozen in het [Microsoft 365-Beheercentrum](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement). Zie de volgende verwijzingen:

- [Detectie van onderwerp beheren in Microsoft 365](topic-experiences-discovery.md)
- [De zichtbaarheid van een onderwerp beheren in Microsoft 365](topic-experiences-knowledge-rules.md)
- [Machtigingen voor onderwerp beheren in Microsoft 365](topic-experiences-user-permissions.md)
- [De naam van het onderwerp centreren in Microsoft 365](topic-experiences-administration.md)

## <a name="see-also"></a>Zie ook

[Overzicht van onderwerpen](topic-experiences-overview.md)
