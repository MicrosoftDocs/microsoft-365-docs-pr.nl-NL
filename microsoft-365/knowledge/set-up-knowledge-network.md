---
title: 'Kennisbeheer instellen (Voorbeeld) '
description: Hoe het opzetten van Kennismanagement.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: Normal
ms.openlocfilehash: d4bc45bd1c88d4043df661972399dc6740dbed84
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540128"
---
# <a name="set-up-knowledge-management-preview"></a>Kennisbeheer instellen (Voorbeeld)

> [!Note] 
> De inhoud in dit artikel is voor Project Cortex Private Preview. [Lees meer over Project Cortex](https://aka.ms/projectcortex).

U het Microsoft 365-beheercentrum gebruiken om [Kennisbeheer](knowledge-management-overview.md)in te stellen en te configureren. 

> [!Important]
> Het is belangrijk om de beste manier te plannen om Kennisbeheer in uw omgeving in te stellen en te configureren. U moet bijvoorbeeld overwegingen maken over het volgende:
- Welke SharePoint-sites u wilt analyseren voor onderwerpen.
- Voor welke gebruikers u onderwerpen zichtbaar wilt maken.
- Welke gebruikers u machtigingen wilt geven om onderwerpen in het onderwerpcentrum te beheren.
- Welke gebruikers u machtigingen wilt geven om onderwerpen in het onderwerpcentrum te maken of te bewerken.
- Welke naam u uw onderwerpcentrum wilt geven.

> [!Note]
> Mogelijk vindt u het handig om beveiligingsgroepen te maken om uw gebruikers de machtigingen toe te wijzen die nodig zijn om onderwerpen te bekijken, onderwerpen te beheren en onderwerpen te maken en te bewerken.

Een beheerder kan ook [wijzigingen aanbrengen in uw geselecteerde instellingen op elk gewenst moment na de installatie](manage-knowledge-network.md) via de instellingen voor kennisbeheer in het Microsoft 365-beheercentrum.

## <a name="requirements"></a>Vereisten 
U moet globale beheerders- of SharePoint-beheerdersmachtigingen hebben om toegang te krijgen tot het Microsoft 365-beheercentrum en organisatorische kennistaken in te stellen.

## <a name="set-up-your-knowledge-network"></a>Uw kennisnetwerk opzetten

Het opzetten van uw kennisnetwerk leidt u door het volgende:

- Onderwerpdetectie: Onderwerpbronnen en onderwerpen selecteren om uit te sluiten van detectie.
- Zichtbaarheid van het onderwerp: selecteren wie onderwerpen als hoogtepunten kan bekijken, in zoek- en onderwerppagina's.
- Onderwerpmachtigingen: selecteren wie onderwerpen kan maken, bewerken en beheren.
- Onderwerpcentrum: maak uw onderwerpcentrum.
- Review: Controleer en pas je instellingen toe.

Ga als u naar het opzetten van uw kennisnetwerk:

1. Selecteer **Setup**in het Microsoft 365-beheercentrum (admin.microsoft.com) en bekijk de sectie **Organisatiekennis.**
2. Klik in de sectie **Organisatorische kennis** op **Mensen verbinden met kennis.**<br/>

    ![Mensen verbinden met kennis](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. Klik **op** de pagina Mensen verbinden met kennis op De klik **op Aan** de slag om u door het installatieproces te leiden.<br/>

    ![Aan de slag](../media/content-understanding/k-get-started.png) </br>

4. Op de pagina **Kies hoe het kennisnetwerk onderwerpen kan vinden,** configureert u onderwerpdetectie. Selecteer in de sectie **SharePoint-onderwerpbronnen** selecteren welke SharePoint-sites tijdens de detectie als bronnen voor uw onderwerpen worden gecrawld. Dit omvat:</br>
    a. **Alle sites:** Alle SharePoint-sites in uw tenant. Dit vangt huidige en toekomstige sites.</br>
    b. **Alles, behalve geselecteerde sites:** Typ de namen van de sites die u wilt uitsluiten.  U ook een lijst uploaden met sites die u wilt afmelden voor detectie. Sites die in de toekomst zijn gemaakt, worden opgenomen als bronnen voor onderwerpdetectie. </br>
    c. **Alleen geselecteerde sites**: Typ de namen van de sites die u wilt opnemen. U ook een lijst met sites uploaden. Sites die in de toekomst zijn gemaakt, worden niet opgenomen als bronnen voor onderwerpdetectie. </br>

    ![Kiezen hoe u onderwerpen vinden](../media/content-understanding/ksetup1.png) </br>
   
5. In de sectie **Onderwerpen uitsluiten op naam** u ervoor kiezen namen op te nemen van onderwerpen die u niet wilt in de gedetecteerde resultaten. Gebruik deze instelling om te voorkomen dat gevoelige onderwerpen worden opgenomen als onderdeel van het kennisnetwerk. Uw opties zijn onder andere:</br>
    a. **Sluit onderwerpen niet uit** </br>
    b. **Onderwerp uitsluiten dat deze termen bevat:** Als u onderwerpen hebt die u niet aan gebruikers wilt laten zien als onderdeel van het kennisnetwerk.
   - Download de meegeleverde template.
   - Voer de onderwerpnamen in die u wilt uitsluiten. U moet het type overeenkomst als exact of gedeeltelijk opgeven. Exacte overeenkomst betekent dat onderwerpen die passen bij de exacte term worden uitgesloten. Gedeeltelijke overeenkomst is strenger en betekent dat onderwerpen die de term bevatten, worden uitgesloten. Als u bijvoorbeeld *Doc* als onderwerpnaam invoert, wordt *doc-assemblage* uitgesloten terwijl *Docker* dat niet doet. De namen van het onderwerp zijn geval ongevoelig.  
        - Selecteer  **+**   om het ingevulde CSV-bestand te importeren. Selecteer vervolgens **Uploaden**. U ziet een groen vinkje als uw bestand is verwerkt. Selecteer **Volgende**.</br>


6. Op de **wie kan onderwerpen zien en waar ze ze kunnen zien** pagina, zult u configureren onderwerp zichtbaarheid. In de instelling Wie kunnen onderwerpen zien in de instelling **kennisnetwerk,** kiest u wie toegang heeft tot onderwerpdetails, zoals gemarkeerde onderwerpen, onderwerpkaarten, onderwerpantwoorden in zoekopdrachten en onderwerppagina's. U kiezen:</br>
    a. **Iedereen in uw organisatie**</br>
    b. **Alleen geselecteerde personen of beveiligingsgroepen**</br>
    c. **Niemand.**</br>

    ![Wie kan onderwerpen zien](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > Met deze instelling u een gebruiker in uw organisatie selecteren, maar alleen gebruikers die kennisbeheerlicenties aan hen hebben toegewezen, kunnen onderwerpen bekijken. 

7. Op de pagina **Machtigingen voor onderwerpbeheer** kiest u wie onderwerpen kan maken, bewerken of beheren. In de sectie **Wie kan onderwerpen maken en bewerken,** u het volgende selecteren:</br>
    a. **Iedereen in uw organisatie**</br>
    b. **Alleen geselecteerde personen of beveiligingsgroepen**</br>
8. In de sectie **Wie kan onderwerpen beheren,** u het volgende selecteren:</br>
    a. **Iedereen in uw organisatie**</br>
    b. **Geselecteerde personen of beveiligingsgroepen**</br>

    ![Machtigingen voor onderwerpbeheer](../media/content-understanding/ksetup3.png) </br>

    Selecteer **Volgende**.</br>
9. Op de pagina **Onderwerpcentrum maken** u uw onderwerpcentrumsite maken waarin onderwerppagina's kunnen worden bekeken en onderwerpen kunnen worden beheerd.  Typ in het **vak Naam van het onderwerpcentrum** een naam voor het onderwerpcentrum. U optioneel een korte beschrijving typen in het vak **Sitebeschrijving.** </br>

Selecteer **Volgende**.</br>

   ![Kenniscentrum maken](../media/content-understanding/ksetup4.png) </br> 

10. Op de pagina **Controleren en eindigen** u de geselecteerde instelling bekijken en ervoor kiezen wijzigingen aan te brengen. Als u tevreden bent met uw selecties, selecteert u **Activeren**.

    ![Afwerking en beoordeling](../media/content-understanding/ksetup5.png) </br> 

11. De geactiveerde pagina **kennisnetwerk** wordt weergegeven, die bevestigt dat het systeem nu begint met het analyseren van uw geselecteerde sites op onderwerpen en het maken van de Knowledge Center-site. Selecteer **Gereed**.</br>

    ![Geactiveerd](../media/content-understanding/ksetup6.png) </br> 

12. Je wordt teruggestuurd naar je **contact met mensen die met elkaar in contact** komen. Op deze pagina u **Beheren** selecteren om wijzigingen aan te brengen in uw configuratie-instellingen. 

    ![Instellingen toegepast](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> Na de installatie kan een beheerder op elk gewenst moment [wijzigingen aanbrengen in de geselecteerde instellingen voor kennisbeheer](manage-knowledge-network.md) door terug te keren naar deze pagina.


## <a name="see-also"></a>Zie ook



  






