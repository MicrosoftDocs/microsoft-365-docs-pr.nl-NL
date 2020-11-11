---
title: 'Kennisbeheer instellen (preview) '
description: Het instellen van kennisbeheer.
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: c7c30c0f8c1ec4cf8836547e2a23e1e2e6f4f783
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988943"
---
# <a name="set-up-knowledge-management-preview"></a>Kennisbeheer instellen (preview)

> [!Note] 
> De inhoud in dit artikel is bedoeld voor project cortex private preview. [Meer informatie over Project Cortex](https://aka.ms/projectcortex).

Met het Microsoft 365-Beheercentrum kunt u [kennisbeheer](knowledge-management-overview.md)instellen en configureren. 

> [!Important]
> Het is belangrijk dat u de beste manier voor het instellen van kennisbeheer in uw omgeving de beste manier plant en configureert. U moet bijvoorbeeld overwegingen voor het volgende doen:
- De SharePoint-sites die u voor onderwerpen wilt analyseren.
- De gebruikers van wie u de onderwerpen zichtbaar wilt maken.
- Welke gebruikers u machtigingen wilt geven om onderwerpen te beheren in het onderwerp centrum.
- Welke gebruikers u machtigingen wilt geven om onderwerpen te maken of te bewerken in het onderwerp centrum.
- De naam van het onderwerp dat u wilt geven.

> [!Note]
> Het kan handig zijn om beveiligingsgroepen te maken om uw gebruikers de benodigde machtigingen voor het weergeven van onderwerpen te zien, onderwerp te beheren en onderwerpen te maken en bewerken.

Een beheerder kan ook [op elk gewenst moment na de installatie wijzigingen aanbrengen](topic-experiences-discovery.md) in de instellingen voorkennis beheer in het microsoft 365-Beheercentrum.

## <a name="requirements"></a>Vereisten 
U moet een globale beheerder of SharePoint-beheerdersmachtigingen hebben om toegang te krijgen tot het Microsoft 365-Beheercentrum en om bedrijfsinformatie in te stellen.

## <a name="set-up-your-knowledge-network"></a>Uw kennis netwerk instellen

Het instellen van uw kennis netwerk begeleidt u door het volgende:

- Onderwerp detecteren: het selecteren van onderwerpen bronnen en onderwerpen voor het opzeggen van detectie.
- Onderwerp zichtbaar: wanneer u een gebruiker selecteert, kunt u deze onderwerpen als aandachtspunten weergeven op de tabbladen zoeken en onderwerp.
- Onderwerp machtigingen: selecteren wie onderwerpen kan maken, bewerken en beheren.
- Onderwerpen centrum: het onderwerpen centrum maken.
- Controleren: de instellingen controleren en toepassen.

Uw kennis netwerk instellen:

1. In het Microsoft 365-Beheercentrum (admin.microsoft.com), selecteert u **instellingen** en vervolgens de afdelings informatie van de **organisatie** weergeven.
2. Klik in de sectie **kennis van organisatie** op **personen verbinden met kennis**.<br/>

    ![Mensen verbinden met kennis](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. Klik op de pagina **personen verbinden met kennis** op aan de slag om u door te **gaan** met het instellen van het installatieproces.<br/>

    ![Aan de slag](../media/content-understanding/k-get-started.png) </br>

4. Ga naar de pagina **Kies hoe u de pagina wilt zoeken** in het onderwerp: detectie van een kennis netwerk. Selecteer in de sectie **SharePoint-onderwerpen selecteren** welke SharePoint-sites worden verkend als bronnen voor uw onderwerpen tijdens de detectie. Dit omvat:</br>
    a. **Alle sites** : alle SharePoint-sites in de Tenant. Hiermee worden de huidige en toekomstige sites vastgelegd.</br>
    b. **Alles, met uitzondering van geselecteerde sites** : Typ de namen van de sites die u wilt uitsluiten.  U kunt ook een lijst uploaden met sites die u wilt afmelden bij ontdekking. Sites die in de toekomst zijn gemaakt, worden opgenomen als bronnen voor de detectie van het onderwerp. </br>
    c. **Alleen geselecteerde sites** : Typ de namen van de sites die u wilt opnemen. U kunt ook een lijst met sites uploaden. Sites die u later maakt, worden niet opgenomen als bronnen voor de detectie van het onderwerp. </br>

    ![Kiezen hoe u onderwerpen kunt zoeken](../media/content-understanding/ksetup1.png) </br>
   
5. In de sectie **onderwerpen uitsluiten van naam** kunt u kiezen of u namen wilt opnemen van onderwerpen die u niet wilt opnemen in de gedetecteerde resultaten. Gebruik deze instelling om te voorkomen dat vertrouwelijke onderwerpen worden opgenomen als onderdeel van het kennis netwerk. De opties zijn:</br>
    a. **Geen onderwerpen uitsluiten** </br>
    b. **Onderwerpen uitsluiten op naam** : als u onderwerpen hebt die u niet wilt weergeven aan gebruikers als onderdeel van het kennis netwerk.</br>

    ![Onderwerpen uitsluiten](../media/content-understanding/topics-excluded-by-name.png) </br>

    #### <a name="how-to-exclude-topics-by-name"></a>Onderwerpen uitsluiten op naam    

    Als u onderwerpen wilt uitsluiten, selecteert u **de sjabloon. csv downloaden** als u **onderwerpen uitsluiten op naam** selecteert. Gebruik Excel. CSV-sjabloon voor een lijst met onderwerpen die u niet wilt opnemen in de resultaten van detectie.

    ![Onderwerpen in CSV-sjabloon uitsluiten](../media/content-understanding/csv1.png) </br>

    Voer de volgende informatie over de onderwerpen die u wilt uitsluiten in het CSV-sjabloon in:

    - **Naam** : Typ de naam van het onderwerp dat u wilt uitsluiten. U kunt dit op twee manieren doen:</br>
        - Exacte overeenkomst: u kunt de exacte naam of het acroniem opnemen, bijvoorbeeld *Contoso* of *ATL*.</br>
        - Gedeeltelijke overeenkomst: u kunt alle onderwerpen met een specifiek woord uitsluiten.  Met de *boog* worden bijvoorbeeld alle onderwerpen met het woord *boog* weggelaten, zoals *boog cirkel* , *plasma boog lassen* of *boog boog*. Houd er rekening mee dat onderwerpen waarvan de tekst deel uitmaakt van een woord, zoals de *architectuur* , niet worden uitgesloten.</br>
    - **Expansie (optioneel)** : als u een acroniem wilt uitsluiten, typt u de woorden waarop het acroniem staat.</br>
    - **MatchType-exact/gedeeltelijk** : Typ of de ingevoerde naam een *exact* of *gedeeltelijk* overeenkomend type is.</br>

    Wanneer u het CSV-sjabloonbestand hebt voltooid en opgeslagen, selecteert u **Bladeren** om naar het bestand te zoeken en te selecteren.
    
    Selecteer **Volgende**.</br>

6. In de pagina **wie kan de onderwerpen zien en waar ze deze kunnen zien** , wordt de zichtbaarheid van het onderwerp geconfigureerd. In de instelling **wie kan de onderwerpen zien in de instelling van het kennis netwerk** , kiest u wie toegang heeft tot de details van het onderwerp, zoals gemarkeerde onderwerpen, topic cards, onderwerp Answers in Search en topic Pages. U kunt kiezen voor:</br>
    a. **Iedereen in uw organisatie**</br>
    b. **Alleen geselecteerde personen of beveiligingsgroepen**</br>
    c. **Niemand**</br>

    ![Wie kan onderwerpen zien?](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > Met deze instelling kunt u een gebruiker in de organisatie selecteren, zodat alleen gebruikers met een licentie voorkennis beheer die aan hen zijn toegewezen, onderwerpen kunnen weergeven. 

7. Op de pagina **machtigingen voor onderwerp beheren** kiest u wie onderwerpen kan maken, bewerken en beheren. In de sectie **wie kan onderwerpen maken en bewerken** , kunt u het volgende selecteren:</br>
    a. **Iedereen in uw organisatie**</br>
    b. **Alleen geselecteerde personen of beveiligingsgroepen**</br>
8. In de sectie **wie kan secties beheren** , kunt u het volgende selecteren:</br>
    a. **Iedereen in uw organisatie**</br>
    b. **Geselecteerde personen of beveiligingsgroepen**</br>

    ![Machtigingen voor onderwerp beheren](../media/content-understanding/ksetup3.png) </br>

    Selecteer **Volgende**.</br>
9. Op de pagina **topic maken** kunt u de site van het onderwerp maken waarin de onderwerpen kunnen worden weergegeven en de onderwerpen kunnen worden beheerd.  Typ in het vak **naam van onderwerp centrum** een naam voor het onderwerp Center. U kunt desgewenst een korte beschrijving typen in het vak **Beschrijving van site** . </br>

Selecteer **Volgende**.</br>

   ![Kennis centrum maken](../media/content-understanding/ksetup4.png) </br> 

10. Op de pagina **Controleren en voltooien** kunt u de geselecteerde instelling bekijken en wijzigingen aanbrengen. Selecteer **Activeren** wanneer u tevreden bent met uw selecties.

    ![Voltooien en controleren](../media/content-understanding/ksetup5.png) </br> 

11. De pagina voor **geactiveerde kennis netwerk** wordt weergegeven en u wordt bevestigd dat het systeem nu begint met het analyseren van de geselecteerde sites voor onderwerpen en de site van de Knowledge Center-site maakt. Selecteer **Gereed**.</br>

    ![Gestart](../media/content-understanding/ksetup6.png) </br> 

12. U gaat terug naar de pagina contact **personen verbinden met kennis** . Op deze pagina kunt u **Beheren** selecteren om wijzigingen aan te brengen in de configuratie-instellingen. 

    ![Instellingen toegepast](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> Na de installatie kan een beheerder op elk moment [wijzigingen aanbrengen in uw geselecteerde instellingen voorkennis beheer](topic-experiences-discovery.md) , door terug te gaan naar deze pagina.


## <a name="see-also"></a>Zie ook



  





