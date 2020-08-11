---
title: 'Werken met onderwerpen in het onderwerp centrum (preview) '
description: Werken met onderwerpen in het onderwerp centrum.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: e4a9917464e22c6220d26619e7b5ca60f090abb7
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612488"
---
# <a name="work-with-topics-in-the-topic-center-preview"></a>Werken met onderwerpen in het onderwerp centrum (preview)

> [!Note] 
> De inhoud in dit artikel is bedoeld voor project cortex private preview. [Lees meer over project cortex](https://aka.ms/projectcortex).


In het onderwerp centrum kan een Knowledge Manager onderwerpen controleren die zijn mined en gedetecteerd in de door u opgegeven SharePoint-bronlocaties, en deze kunnen ofwel bevestigen of weigeren. Een Knowledge Manager kan ook nieuwe topic pagina's maken en publiceren als die niet is gevonden in het detecteren van een onderwerp of bestaande pagina's bewerken als ze moeten worden bijgewerkt.

## <a name="requirements"></a>Vereisten

Om in het onderwerp te kunnen werken, moet u beschikken over de vereiste machtigingen. Uw beheerder kan u tijdens het [instellen van Knowledge Management](set-up-knowledge-network.md)toevoegen of nieuwe gebruikers kunnen [later worden toegevoegd](give-user-permissions-to-the-topic-center.md).

De gebruikers van het onderwerp centrum kunnen twee groepen machtigingen krijgen:

- Onderwerpen maken en bewerken: nieuwe onderwerpen maken of inhoud van een onderwerp bijwerken, zoals de beschrijving, documenten en gekoppelde personen
- Onderwerpen beheren: gebruik het dashboard van het onderwerp-beheer om de onderwerpen binnen de organisatie te reviseren. Gebruikers kunnen acties uitvoeren, zoals onderwerpen voor bevestigen en negeren


## <a name="review-unconfirmed-topics"></a>Onbevestigde onderwerpen controleren

Op de startpagina van het onderwerp Center worden de onderwerpen die zijn gevonden in de opgegeven SharePoint-bronlocaties weergegeven op het tabblad **onbevestigd** . Een gebruiker met machtigingen voor het beheren van onderwerpen kan onbevestigde onderwerpen controleren en ervoor zorgen dat deze worden bevestigd of genegeerd.


Een niet-bevestigd onderwerp bekijken:

1. Selecteer op het tabblad niet- **bevestigd** het onderwerp om de onderwerpenpagina te openen.</br>

2. Op de pagina onderwerp controleert u het onderwerp en selecteert u **bewerken** als u wijzigingen wilt aanbrengen aan de pagina.
3. Op de startpagina van het kennis centrum voor het geselecteerde onderwerp, kunt u het volgende doen:</br>
    a. Selecteer de controleren om te bevestigen dat u het onderwerp wilt bewaren.</br>
    b. Selecteer de **x** als u het onderwerp wilt negeren.</br>

    Bevestigde onderwerpen worden verwijderd uit de niet- **bevestigde** lijst en worden nu weergegeven op het tabblad **bevestigd** .</br>

    Genegeerde onderwerpen worden verwijderd uit de niet- **bevestigde** lijst en worden nu weergegeven in het tabblad **afgekeurd of uitgesloten** .</br>
    
   
## <a name="create-a-new-topic"></a>Een nieuw onderwerp maken

Gebruikers met de machtiging onderwerp maken of bewerken kunnen een nieuw onderwerp maken, indien nodig. U moet dit mogelijk doen als het onderwerp niet is gevonden via Discovery of als de AI-technologie niet voldoende bewijs heeft gevonden om dit als onderwerp te verkrijgen.

Een nieuw onderwerp maken:
1. Selecteer op de pagina onderwerp centrum de optie **Nieuw**en selecteer vervolgens **onderwerpenpagina**.</br>

    ![Nieuw onderwerp](../media/content-understanding/k-new-topic.png) </br>

2. Op de nieuwe pagina voor het onderwerp kunt u de gegevens invullen van de nieuwe sjabloon:</br>
    a. Typ in het gedeelte **naam van dit onderwerp** de naam van het nieuwe onderwerp.</br>
    b. Typ in de sectie **alternatieve namen** de namen of acroniemen die ook worden gebruikt om het onderwerp te raadplegen.</br>
    c. Typ in het gedeelte **korte beschrijving** de beschrijving van een of twee zinnen van het onderwerp. Deze tekst wordt gebruikt voor het bijbehorende onderwerpvenster.</br>
    d. Typ in de sectie **personen** de namen van de experts voor het onderwerp.</br>
    e. Selecteer in de sectie **bestanden en pagina's** de optie **toevoegen** en op de volgende pagina kunt u de bijbehorende OneDrive-bestanden of SharePoint Online-pagina's selecteren.</br>
    f. Selecteer in de sectie **sites** de optie **toevoegen**. Selecteer de sites die zijn gekoppeld aan het onderwerp in het deelvenster **sites** dat wordt weergegeven.</br>

    ![Nieuwe onderwerpenpagina](../media/content-understanding/k-new-topic-page.png) </br>
3. Als u andere onderdelen aan de pagina wilt toevoegen, zoals tekst, afbeeldingen, webonderdelen, koppelingen, enzovoort, selecteert u het canvas pictogram in het midden van de pagina om deze te zoeken en toe te voegen.
    ![Items aan een pagina toevoegen](../media/content-understanding/static-icon.png) </br> 

4. Wanneer u klaar bent, selecteert u **publiceren** om de onderwerpenpagina te publiceren. Gepubliceerde topic pagina's worden weergegeven op het tabblad **pagina's** .

> [!Note] 
> De nieuwe topic wordt gemaakt van webonderdelen die bekend zijn met het *kennis netwerk*. Dit betekent dat zo veel meer informatie over het onderwerp wordt verzameld, maar de informatie in deze webonderdelen wordt bijgewerkt met suggesties om de pagina nuttiger te maken voor gebruikers.


## <a name="edit-an-existing-topic-page"></a>Een bestaande onderwerpenpagina bewerken

Bestaande topic pagina's vindt u op de pagina **pagina's** . 

1. Selecteer op de pagina onderwerp centrum de optie **pagina's**.</br>
2. Op de pagina **pagina's** ziet u een lijst met onderwerpen over pagina's. Gebruik het zoekvak om te zoeken naar het onderwerp dat u wilt bijwerken. Klik op de naam van het onderwerp dat u wilt bewerken.</br>
3. Selecteer **bewerken**op de pagina onderwerp. </br>
4. Breng de gewenste wijzigingen aan in de pagina. Dit omvat updates voor de volgende velden:</br>
    a. Alternatieve namen</br>
    b. Beschrijving</br>
    c. Personen</br>
    d. Bestanden en pagina's</br>
    e. Sites</br>
    f. U kunt ook statische items toevoegen aan de pagina, zoals tekst, afbeeldingen of koppeling, door het papier pictogram te selecteren.</br>

5. Selecteer **opnieuw publiceren** om uw wijzigingen op te slaan.

## <a name="see-also"></a>Zie ook



  






