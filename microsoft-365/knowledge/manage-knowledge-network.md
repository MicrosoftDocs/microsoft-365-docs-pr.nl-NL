---
title: 'Uw kennisbeheernetwerk beheren(Voorbeeld) '
description: Hoe het opzetten van Kennismanagement.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: Normal
ms.openlocfilehash: 87275dba78ab402a9ea9553198ce1a84072e3351
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540116"
---
# <a name="manage-your-knowledge-management-network-preview"></a>Beheer uw kennisbeheernetwerk (Preview)

> [!Note] 
> De inhoud in dit artikel is voor Project Cortex Private Preview. [Lees meer over Project Cortex](https://aka.ms/projectcortex).


Nadat u kennisbeheer hebt [ingesteld,](set-up-knowledge-network.md)kan een beheerder op elk gewenst moment daarna uw configuratie-instellingen aanpassen via het Microsoft 365-beheercentrum.

Het kan bijvoorbeeld nodig zijn om uw instellingen aan te passen voor een van de volgende opties:
- Voeg nieuwe SharePoint-bronnen toe aan mijnonderwerpen.
- Wijzig welke gebruikers toegang hebben tot onderwerpen.
- Wijzig welke gebruikers machtigingen hebben om taken uit te voeren in het onderwerpcentrum.
- De naam van uw onderwerpcentrum wijzigen


## <a name="requirements"></a>Vereisten 
U moet globale beheerders- of SharePoint-beheerdersmachtigingen hebben om toegang te krijgen tot het Microsoft 365-beheercentrum en organisatorische kennistaken te beheren.


## <a name="to-access-knowledge-management-settings"></a>Ga alst u naar instellingen voor kennisbeheer:

1. Selecteer **Setup**in het Microsoft 365-beheercentrum en bekijk de sectie **Organisatiekennis.**
2. Klik in de sectie **Organisatorische kennis** op **Mensen verbinden met kennis.**<br/>

    ![Mensen verbinden met kennis](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. Selecteer **beheren** om het deelvenster **Instellingen** voor kennis te openen op de pagina Personen verbinden **met kennis.**<br/>

    ![kennisnetwerkinstellingen](../media/content-understanding/knowledge-network-settings.png) </br>

## <a name="change-how-the-knowledge-network-can-find-topics"></a>Wijzigen hoe het kennisnetwerk onderwerpen kan vinden

Selecteer het tabblad **Onderwerpdetectie** als u uw keuzes voor SharePoint-onderwerpbronnen wilt bijwerken. Met deze instelling u de SharePoint-sites in uw tenant selecteren die worden gecrawld en gedolven voor onderwerpen.

1. Selecteer op het tabblad **Onderwerpdetectie** onder **SharePoint-onderwerpbronnen selecteren**de optie **Bewerken**.
2. Selecteer op de pagina **SharePoint-onderwerpbronnen** selecteren welke SharePoint-sites tijdens de detectie als bronnen voor uw onderwerpen worden gecrawld. Dit omvat:</br>
    a. **Alle sites:** Alle SharePoint-sites in uw tenant. Dit vangt huidige en toekomstige sites.</br>
    b. **Alles, behalve geselecteerde sites:** Typ de namen van de sites die u wilt uitsluiten.  U ook een lijst uploaden met sites die u wilt afmelden voor detectie. Sites die in de toekomst zijn gemaakt, worden opgenomen als bronnen voor onderwerpdetectie. </br>
    c. **Alleen geselecteerde sites**: Typ de namen van de sites die u wilt opnemen. U ook een lijst met sites uploaden. Sites die in de toekomst zijn gemaakt, worden niet opgenomen als bronnen voor onderwerpdetectie. </br>

    ![Kiezen hoe u onderwerpen vinden](../media/content-understanding/k-manage-select-topic-source.png) </br>
   
    Als u een aantal sites hebt die u wilt uitsluiten (als u **Alles selecteert, behalve geselecteerde sites)** of opneemt (als u Alleen geselecteerde sites **hebt**geselecteerd), u ervoor kiezen om een CSV-bestand te uploaden met de sitenamen en URL's. U **sitesjabloon downloaden (csv)** selecteren als u het CSV-sjabloonbestand wilt gebruiken.

3. Klik op **Opslaan**.

##  <a name="change-who-can-see-topics-in-your-organization"></a>Wijzigen wie onderwerpen in uw organisatie kan zien

Selecteer het tabblad **Onderwerpdetectie** als u wilt bijwerken wie in uw organisatie gedetecteerde onderwerpen in zoekresultaten kan zien en wanneer onderwerpen worden gemarkeerd in inhoud zoals SharePoint-pagina's.

1. Selecteer op het tabblad **Onderwerpdetectie** onder **Wie onderwerpen in het kennisnetwerk kan zien**de optie **Bewerken**.
2. Op de pagina Wie kan onderwerpen zien op de pagina **kennisnetwerk,** kiest u wie toegang heeft tot onderwerpdetails, zoals gemarkeerde onderwerpen, onderwerpkaarten, onderwerpantwoorden in zoekopdrachten en onderwerppagina's. U kiezen:</br>
    a. **Iedereen in uw organisatie**</br>
    b. **Alleen geselecteerde personen of beveiligingsgroepen**</br>
    c. **Niemand.**</br>

    ![Wie kan onderwerpen zien](../media/content-understanding/k-manage-who-can-see-topics.png) </br> 
3. Klik op **Opslaan**.  
 
> [!Note] 
> Met deze instelling u een gebruiker in uw organisatie selecteren, maar alleen gebruikers die kennisbeheerlicenties aan hen hebben toegewezen, kunnen onderwerpen bekijken.

## <a name="change-who-has-permissions-to-do-tasks-on-the-topic-center"></a>Wijzigen wie machtigingen heeft om taken uit te voeren in het onderwerpcentrum

Selecteer het tabblad **Onderwerpmachtigingen** als u wilt bijwerken wie machtigingen heeft om het volgende te doen op de pagina met onderwerpcentrum:

- Welke gebruikers onderwerpen kunnen maken en bewerken: maak nieuwe onderwerpen die niet zijn gevonden tijdens de detectie of bewerk bestaande onderwerppaginadetails.
- Welke gebruikers onderwerpen kunnen beheren: Ontdekte onderwerpen bevestigen of afwijzen.

Ga als u aan de informatie over wie machtigingen heeft om onderwerpen te maken en te bewerken:

1. Selecteer op het tabblad **Onderwerpmachtigingen** onder **Wie onderwerpen kan maken en bewerken**de optie **Bewerken**.</br>
2. Op de pagina **Wie kan onderwerpen maken en bewerken,** u het:</br>
    a. **Iedereen in uw organisatie**</br>
    b. **Alleen geselecteerde personen of beveiligingsgroepen**</br>

    ![Onderwerpen maken en bewerken](../media/content-understanding/k-manage-who-can-create-and-edit.png) </br> 

3. Klik op **Opslaan**.</br>

Ga als u als gaat over het bijwerken van wie machtigingen heeft om onderwerpen te beheren:

1. Selecteer op het tabblad **Onderwerpmachtigingen** onder **Wie onderwerpen kan beheren**de optie **Bewerken**.</br>
2. Op de pagina **Wie kan onderwerpen beheren,** u het:</br>
    a. **Iedereen in uw organisatie**</br>
    b. **Geselecteerde personen of beveiligingsgroepen**</br>

    ![Onderwerpen beheren](../media/content-understanding/k-manage-who-can-manage-topics.png) </br> 

3. Klik op **Opslaan**.</br>


##  <a name="update-your-topic-center-name"></a>De naam van het onderwerpcentrum bijwerken

Selecteer het tabblad **Onderwerpcentrum** als u de naam van het onderwerpcentrum wilt bijwerken. 

1. Selecteer op het tabblad **Onderwerpcentrum** onder **Naam van het onderwerpcentrum**de optie **Bewerken**.
2. Typ op de **pagina Onderwerpcentrumnaam bewerken** in het **vak Onderwerpcentrumnaam** de nieuwe naam voor het onderwerpcentrum.
3. Selecteer **Opslaan**

    ![Naam van het onderwerpcentrum bewerken](../media/content-understanding/manage-topic-center-name.png) </br> 











## <a name="see-also"></a>Zie ook



  






