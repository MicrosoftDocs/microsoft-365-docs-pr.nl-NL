---
title: 'Uw kennisbeheer netwerk beheren (preview) '
description: Het instellen van kennisbeheer.
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 3ca180dba82e677dbc0d9f112b713df14820ce61
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950770"
---
# <a name="manage-your-knowledge-management-network-preview"></a>Uw kennisbeheer netwerk beheren (preview)

> [!Note] 
> De inhoud in dit artikel is bedoeld voor project cortex private preview. [Lees meer over project cortex](https://aka.ms/projectcortex).


Nadat u [kennisbeheer hebt ingesteld](set-up-knowledge-network.md), kunt u op elk gewenst moment een beheerder de configuratie-instellingen wijzigen via het microsoft 365-Beheercentrum.

U moet bijvoorbeeld de instellingen voor de volgende opties wijzigen:
- Nieuwe SharePoint-bronnen toevoegen aan mijn onderwerpen.
- Wijzig welke gebruikers toegang hebben tot onderwerpen.
- Wijzig welke gebruikers gemachtigd zijn om taken uit te voeren in het onderwerp centrum.
- De naam van het topic Center wijzigen


## <a name="requirements"></a>Vereisten 
U moet een globale beheerder of SharePoint-beheerdersmachtigingen hebben om toegang te krijgen tot het Microsoft 365-Beheercentrum en om organisatie-kennis taken te kunnen beheren.


## <a name="to-access-knowledge-management-settings"></a>Toegang krijgen tot de instellingen van kennisbeheer:

1. Selecteer in het Microsoft 365-Beheercentrum de optie **instellen**en bekijk vervolgens de sectie **bedrijfsinformatie** .
2. Klik in de sectie **kennis van organisatie** op **personen verbinden met kennis**.<br/>

    ![Mensen verbinden met kennis](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. Selecteer op de pagina **personen verbinden met kennis** de optie **beheren** om het deelvenster instellingen van het **kennis netwerk** te openen.<br/>

    ![kennis netwerk-instellingen](../media/content-understanding/knowledge-network-settings.png) </br>

## <a name="change-how-the-knowledge-network-can-find-topics"></a>Wijzigen hoe het kennis netwerk onderwerpen kan vinden

Selecteer het tabblad detectie van het **onderwerp** als u de keuzes voor de bronnen van het SharePoint-onderwerp wilt bijwerken. Met deze instelling kunt u de SharePoint-sites in de Tenant selecteren die worden verkend en mined voor onderwerpen.

1. Selecteer op het tabblad **topic Discovery** onder **Select SharePoint topics**de optie **Edit**.
2. Selecteer op de pagina **SharePoint-onderwerpen selecteren** welke SharePoint-sites worden verkend als bronnen voor uw onderwerpen tijdens de detectie. Dit omvat:</br>
    a. **Alle sites**: alle SharePoint-sites in de Tenant. Hiermee worden de huidige en toekomstige sites vastgelegd.</br>
    b. **Alles, met uitzondering van geselecteerde sites**: Typ de namen van de sites die u wilt uitsluiten.  U kunt ook een lijst uploaden met sites die u wilt afmelden bij ontdekking. Sites die u later maakt, worden opgenomen als bronnen voor het detecteren van het onderwerp. </br>
    c. **Alleen geselecteerde sites**: Typ de namen van de sites die u wilt opnemen. U kunt ook een lijst met sites uploaden. Sites die u later maakt, worden niet opgenomen als bronnen voor de detectie van het onderwerp. </br>

    ![Kiezen hoe u onderwerpen kunt zoeken](../media/content-understanding/k-manage-select-topic-source.png) </br>
   
    Als u een aantal sites hebt die u wilt uitsluiten (als u **alles selecteert, met uitzondering van geselecteerde sites**) of opnemen (als u **alleen geselecteerde sites**hebt geselecteerd), kunt u ervoor kiezen om een CSV-bestand met de sitenamen en url's te uploaden. Selecteer **sitesjabloon. csv downloaden** als u het CSV-sjabloonbestand wilt gebruiken.

3. Selecteer **Opslaan**.

##  <a name="change-who-can-see-topics-in-your-organization"></a>Wijzigen wie de onderwerpen in uw organisatie kunnen zien

Selecteer het tabblad detectie van het **onderwerp** als u wilt bijwerken wie in uw organisatie gedetecteerde onderwerpen kan zien in zoekresultaten en wanneer onderwerpen zijn gemarkeerd met inhoud zoals SharePoint-pagina's.

1. Selecteer op het tabblad **onderwerp detecteren** onder **wie kan de onderwerpen in het kennis netwerk zien**de optie **bewerken**.
2. Op de pagina **wie kan de onderwerpen zien op de pagina van het kennis netwerk** , kiest u wie toegang heeft tot de details van het onderwerp, zoals gemarkeerde onderwerpen, topic cards, topic Answers in Search en topic Pages. U kunt kiezen voor:</br>
    a. **Iedereen in uw organisatie**</br>
    b. **Alleen geselecteerde personen of beveiligingsgroepen**</br>
    c. **Niemand**</br>

    ![Wie kan onderwerpen zien?](../media/content-understanding/k-manage-who-can-see-topics.png) </br> 
3. Selecteer **Opslaan**.  
 
> [!Note] 
> Met deze instelling kunt u een gebruiker in de organisatie selecteren, zodat alleen gebruikers met een licentie voorkennis beheer die aan hen zijn toegewezen, onderwerpen kunnen weergeven.

## <a name="change-who-has-permissions-to-do-tasks-on-the-topic-center"></a>Wijzigen wie gemachtigd is om taken uit te voeren in het onderwerp centrum

Selecteer het tabblad **onderwerp machtigingen** als u het volgende wilt bijwerken op de pagina met het onderwerp centrum:

- Welke gebruikers kunnen onderwerpen maken en bewerken: nieuwe onderwerpen maken die niet zijn gevonden tijdens het detecteren of bewerken van bestaande Details van een onderwerppagina.
- Welke gebruikers onderwerpen kunnen beheren: gedetecteerde of genegeerde onderwerpen.

Een update maken van de gebruikers die gemachtigd zijn om onderwerpen te maken en bewerken:

1. Selecteer op het tabblad **onderwerp machtigingen** onder **wie kan onderwerpen maken en bewerken**de optie **bewerken**.</br>
2. Op de pagina **wie kan onderwerpen maken en bewerken** , kunt u het volgende selecteren:</br>
    a. **Iedereen in uw organisatie**</br>
    b. **Alleen geselecteerde personen of beveiligingsgroepen**</br>

    ![Onderwerpen maken en bewerken](../media/content-understanding/k-manage-who-can-create-and-edit.png) </br> 

3. Selecteer **Opslaan**.</br>

Bijwerken met de gebruikers die gemachtigd zijn om onderwerpen te beheren:

1. Selecteer op het tabblad **machtigingen voor onderwerp** onder **wie kan onderwerpen beheren**de optie **bewerken**.</br>
2. Op de pagina **wie kan onderwerpen beheren** , kunt u de volgende opties kiezen:</br>
    a. **Iedereen in uw organisatie**</br>
    b. **Geselecteerde personen of beveiligingsgroepen**</br>

    ![Onderwerpen beheren](../media/content-understanding/k-manage-who-can-manage-topics.png) </br> 

3. Selecteer **Opslaan**.</br>


##  <a name="update-your-topic-center-name"></a>De naam van uw topic Center bijwerken

Selecteer het tabblad **onderwerp centrum** als u de naam van het onderwerp centrum wilt bijwerken. 

1. Selecteer op het tabblad **onderwerp centrum** , onder **naam onderwerp centrum**, de optie **bewerken**.
2. Typ op de paginanaam van het **centrum voor bewerken** , in het vak **naam van onderwerp centrum** , de nieuwe naam voor het onderwerp Center.
3. Selecteer **Opslaan** .

    ![Naam van onderwerp centrum bewerken](../media/content-understanding/manage-topic-center-name.png) </br> 











## <a name="see-also"></a>Zie ook



  






