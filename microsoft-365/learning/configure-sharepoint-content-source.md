---
title: 'Binnenkort beschikbaar: Configureer SharePoint als een leerinhoudsbron voor Microsoft Viva Learning (Preview)'
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 04/30/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Meer informatie over het configureren SharePoint als een leerinhoudsbron voor Microsoft Viva Learning (Preview).
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: da75ec0573519ed73507994afeac995c0461de0c
ms.sourcegitcommit: d3f8c69519c593b1580cfa7187ce085a99b8a846
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52100894"
---
# <a name="coming-soon-configure-sharepoint-as-a-learning-content-source-for-microsoft-viva-learning-preview"></a>Binnenkort beschikbaar: Configureer SharePoint als een leerinhoudsbron voor Microsoft Viva Learning (Preview)

> [!NOTE]
> De informatie in dit artikel heeft betrekking op een voorbeeldproduct dat aanzienlijk kan worden gewijzigd voordat het commercieel wordt uitgebracht. 

U kunt de SharePoint als een leerinhoudsbron configureren om de eigen inhoud van uw organisatie beschikbaar te maken in Viva Learning (Preview).

## <a name="overview"></a>Overzicht

De kennisbeheerder (of globale beheerder) biedt een site-URL aan waar de Learning Service een lege gecentraliseerde locatie kan maken, de Learning App Content Repository, in de vorm van een gestructureerde SharePoint lijst. Deze lijst kan door uw organisatie worden gebruikt om koppelingen naar meerdere bedrijfsmappen SharePoint bevatten die leerinhoud bevatten. Beheerders zijn verantwoordelijk voor het verzamelen en cureren van een lijst met URL's voor mappen. Deze mappen mogen alleen inhoud bevatten die beschikbaar kan worden gesteld in Viva Learning (preview).

Viva Learning (Preview) ondersteunt de volgende documenttypen:

- Word, PowerPoint, Excel, PDF
- Audio (.m4a)
- Video (.mov, .mp4, .avi)

Zie de onlinedocumentatie SharePoint [voor meer informatie.](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits?redirectSourcePath=%252farticle%252fSharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498) 

## <a name="permissions"></a>Machtigingen

URL's voor documentbibliotheekmappen kunnen worden verzameld vanaf SharePoint site in de organisatie. Viva Learning (Preview) volgt alle bestaande inhoudsmachtigingen. Daarom is alleen inhoud waarvoor een gebruiker toegang heeft, doorzoekbaar en zichtbaar in Viva Learning (Preview). Inhoud in deze mappen kan worden doorzocht, maar alleen inhoud waaraan de afzonderlijke werknemer machtigingen heeft, kan worden gebruikt.

Het verwijderen van inhoud uit de opslagplaats van uw organisatie wordt momenteel niet ondersteund.

Als u onbedoeld opgedoken inhoud wilt verwijderen, gaat u als volgt te werk:

1.  Als u de toegang tot de documentbibliotheek wilt beperken, selecteert u de optie Acties **tonen** en selecteert u **Vervolgens Toegang beheren.**
     
     ![Pagina documentbibliotheek in SharePoint met de optie Acties weergeven met Toegang hoogbeligd beheren.](../media/learning/learning-sharepoint-permissions2.png)

2.  Verwijder het oorspronkelijke document in de documentbibliotheek.

Zie Delen en machtigingen in de moderne SharePoint [voor meer informatie.](/sharepoint/modern-experience-sharing-permissions) 

## <a name="learning-service"></a>Leerservice

De Learning Service gebruikt de meegeleverde map-URL's om metagegevens op te halen uit alle inhoud die in die mappen is opgeslagen. Binnen 24 uur na het leveren van de MAP-URL in de gecentraliseerde opslagplaats kunnen werknemers de inhoud van uw organisatie zoeken en gebruiken in Viva Learning (Preview). Alle wijzigingen in inhoud, inclusief bijgewerkte metagegevens en machtigingen, worden ook binnen 24 uur toegepast in de Leerservice.

## <a name="configure-sharepoint-as-a-source"></a>Een SharePoint als bron configureren

U moet een globale Microsoft 365, beheerder SharePoint of kennisbeheerder zijn om deze taken uit te voeren.

Als u een SharePoint wilt configureren als een leerinhoudsbron in voor Viva Learning (voorbeeld), volgt u de volgende stappen:

1.  Ga in de linkernavigatie van het Microsoft 365 beheercentrum **naar Instellingen**  >  **Organisatie-instellingen.**
 
2.  Selecteer op **de pagina Organisatie-instellingen** op het **tabblad Services** de **optie Leer-app (Voorbeeld)**.

     ![Instellingen pagina in het Microsoft 365-beheercentrum met Viva Learning weergegeven.](../media/learning/learning-sharepoint-configure1.png)

3.  In het **deelvenster Leer-app (Preview)** onder SharePoint, wordt de SITE-URL weergegeven naar de SharePoint site waar u wilt dat Viva Learning een gecentraliseerde opslagplaats maakt.

     ![Leervenster in het Microsoft 365-beheercentrum met SharePoint geselecteerd.](../media/learning/learning-sharepoint-configure2.png)

4.  Een SharePoint wordt automatisch gemaakt binnen de opgegeven SharePoint site.

     ![Nieuw gemaakte SharePoint in de SharePoint site.](../media/learning/learning-sharepoint-configure3.png)

     Selecteer in de linkernavigatie van de SharePoint site **Site-inhoud**  >  **Learning App Content Repository**. 

     ![SharePoint lijst met de navigatie van site-inhoud en de sectie Inhoudsopslag voor leer-apps.](../media/learning/learning-sharepoint-configure4.png) 

5. Vul op **de pagina Inhoudsopslag** van leer-apps de SharePoint met URL's in de mappen met leerinhoud.

   1. Selecteer **Nieuw om** het deelvenster Nieuw item **te** bekijken. 

       ![Pagina Leerinhoudsopslagplaats in SharePoint met de optie Nieuw.](../media/learning/learning-sharepoint-configure5.png)
 
   2. Voeg in **het deelvenster** Nieuw item in **het** veld Titel een adreslijstnaam van uw keuze toe. Voeg in **het veld Map-URL** de URL toe aan de map leerinhoud. Selecteer **Opslaan**.

       ![Nieuw itemvenster in SharePoint met de velden Titel en Map-URL.](../media/learning/learning-sharepoint-configure6.png)

   3. De **pagina Learning App Content Repository** wordt bijgewerkt met de nieuwe leerinhoud.

       ![Pagina Learning Content Repository in SharePoint met de bijgewerkte informatie.](../media/learning/learning-sharepoint-configure7.png)

> [!NOTE]
> Als u een bredere toegang tot de Inhoudsopslagplaats voor leer-apps wilt toestaan, is er binnenkort een koppeling naar de lijst beschikbaar in de interface Viva Learning (Preview), waar gebruikers toegang kunnen aanvragen en uiteindelijk kunnen helpen de lijst in te vullen. Site-eigenaren en globale beheerders moeten toegang verlenen tot de lijst. Access is alleen specifiek voor de lijst en is niet van toepassing op de site waar de lijst is opgeslagen. Zie De inhoud van [uw](#provide-your-own-organizations-content) eigen organisatie later in dit artikel verstrekken voor meer informatie.

### <a name="folder-url-document-library-curation"></a>Map URL document library curation

Standaardmetagegevens (zoals gewijzigde datum, gemaakt door, documentnaam, inhoudstype en organisatienaam) worden automatisch in Viva Learning (Preview) getrokken door de Microsoft Graph API.
 
Als u de algehele detectie en zoekrelevantie van de inhoud wilt verbeteren, raden we u aan een kolom **Beschrijving toe te** voegen.

Als u een kolom **Beschrijving wilt** toevoegen aan de pagina van de documentbibliotheek, gaat u als volgt te werk:

1.  Selecteer op **de pagina** Documenten de optie **Kolom toevoegen.**

2. Selecteer de **optie Acties tonen** en selecteer vervolgens Enkele regel **tekst.**

     ![Pagina Documenten in SharePoint met de opties Acties weergeven met Één regel tekst gemarkeerd.](../media/learning/learning-sharepoint-curation1.png)

3. Voeg in **het deelvenster** Een kolom maken in het veld **Naam** een beschrijvende naam voor de kolom toe. Selecteer **Opslaan**.

     ![Maak een kolomvenster in SharePoint met de naam en andere velden.](../media/learning/learning-sharepoint-curation2.png)
 
4. Voeg op **de** pagina Documenten in **de** kolom Beschrijving aangepaste beschrijvingen toe voor elk item. Als er geen beschrijving wordt opgegeven, wordt in Viva Learning (Preview) een standaardbericht weergegeven waarin de inhoud wordt benadrukt als afkomstig uit uw eigen SharePoint bibliotheek. 

     ![Pagina Documenten in SharePoint met de beschrijvingen in de kolom Beschrijving.](../media/learning/learning-sharepoint-curation3.png)
 
### <a name="provide-your-own-organizations-content"></a>De inhoud van uw eigen organisatie leveren

Kennisbeheerders hebben toegang tot de Learning App Content Repository van hun organisatie in SharePoint, waar ze verwijzingen kunnen bieden naar documentbibliotheken binnen verschillende organisaties. Inhoud in deze bibliotheken wordt vervolgens weergegeven als leerinhoud in Viva Learning (Preview).

1. Selecteer in Viva Learning (Preview) **Meer opties** **(...)** en selecteer vervolgens **Instellingen.**

     ![SharePoint bibliotheekpagina met de optie Meer opties en Instellingen.](../media/learning/learning-sharepoint-library-1.png)
     
2. Selecteer **onder Instellingen** **machtigingen**.

     ![Instellingen optiepagina in SharePoint met de opties Machtigingen en Toegang controleren.](../media/learning/learning-sharepoint-library-2.png)

3. Selecteer **Toegang controleren** om verbinding te maken met de gecentraliseerde bibliotheek van uw organisatie.
     
