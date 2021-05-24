---
title: Microsoft Viva Learning (Preview) instellen in het Teams beheercentrum
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/24/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Meer informatie over het configureren van Microsoft Viva Learning (Preview) in het Teams beheercentrum.
ms.openlocfilehash: a96a2f3ecf7d4e1ee0c136ae155868218f08aaf4
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636132"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a>Microsoft Viva Learning (Preview) instellen in het Teams beheercentrum

> [!NOTE]
> De informatie in dit artikel heeft betrekking op een voorbeeldproduct dat aanzienlijk kan worden gewijzigd voordat het commercieel wordt uitgebracht. 

De Teams beheerder installeert Viva Learning (Preview) en past machtigingsbeleid toe via het Teams beheercentrum.

1. Voor Viva Learning (Preview) moet u eerst het updatebeleid instellen in Teams. Zie openbare Microsoft Teams [voor meer informatie.](/MicrosoftTeams/public-preview-doc-updates)

    1. Meld u aan bij het Teams beheercentrum.

    2. Selecteer **Teams**  >  **Beleid bijwerken**.

    3. Kies **Toevoegen**. 

    4. Geef het updatebeleid een naam, voeg een beleid toe en schakel **Voorbeeldfuncties weergeven in.**

2. De beheerder moet gebruikers op de hoogte stellen van de beleidsupdate, zodat ze hun build kunnen verplaatsen naar het openbare voorbeeld voor Teams. 

    1. Gebruikers moeten hun profielafbeelding selecteren > **Over**  >  **openbare preview.**
   
        ![Bovenste navigatie in de Teams met het profiel van de gebruiker](../media/learning/learning-app-select-profile-teams.png)
    
    2. Gebruikers moeten de algemene voorwaarden **voor openbare preview-weergave** accepteren.

        ![Overschakelen naar openbare preview-build](../media/learning/learning-app-switch-to-public-preview.png)
 
3. Voor organisaties die een beperkend beleid hebben en Viva Learning (Preview) moeten inschakelen, volgt u het proces in de volgende sectie.

## <a name="manage-settings-for-viva-learning-preview"></a>Instellingen voor Viva Learning beheren (voorbeeld)

U moet een beheerder zijn in het Teams beheercentrum om deze taken uit te voeren.

Als u Viva Learning (Preview) beschikbaar wilt maken voor gebruikers in uw organisatie, volgt u de volgende stappen:

1. Ga in de linkernavigatie van het Teams beheercentrum naar Teams **Apps**  >  **beheren.**

   ![Navigatie links in het Teams beheercentrum met Teams apps en de sectie Apps beheren.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. Typ op **de pagina Apps** beheren in het zoekvak Viva *learning* en selecteer vervolgens Viva **Learning (Preview).**

   ![De pagina Apps beheren in het Teams beheercentrum met het zoekvak.](../media/learning/learning-app-teams-manage-apps-page.png)

3. Op de **pagina Viva Learning (Preview)** :

   1. Selecteer **onder Status** de optie **Toegestaan** om Viva Learning (Preview) in te zetten.

   2. Ga op **Instellingen** tabblad Onder **App-instellingen** naar het Microsoft 365 beheercentrum om [leerinhoudsbronnen te configureren.](content-sources-365-admin-center.md)

   ![Leerpagina in het Teams beheercentrum met de sectie Status- en App-instellingen.](../media/learning/learning-app-teams-learning-page.png)

4. Nadat **u app-instellingen** beheren  hebt ingesteld, gaat u naar Machtigingsbeleid en Installatiebeleid om toestemming te verlenen aan werknemers die toegang moeten hebben tot Viva Learning (Preview) als onderdeel van de deelname van uw organisatie aan het voorbeeld. 

> [!NOTE]
>  Als uw organisatie ring 4.0 heeft als onderdeel van Teams TAP100-programma, moet u mogelijk goedgekeurde gebruikers in Ring 3.0 inschakelen voor toegang tot Viva Learning (Preview). <br><br>Als onderdeel van het voorbeeld wordt Viva Learning (Preview) uitgebracht in Ring 3.0. Als uw organisatie Ring 4.0 gebruikt, ziet u Viva Learning (Preview) niet op de **pagina Apps beheren.** Als u de app wilt testen, moet u een aangepast machtigingsbeleid voor apps maken, instellen op Alle **apps** toestaan en deze toewijzen aan goedgekeurde gebruikers van Ring 3.0. <br><br>   ![Tap-AppsPermission-Plcy-pagina met alle geselecteerde apps toestaan.](../media/learning/learning-app-tap-appspermission-plcy.png)

## <a name="next-step"></a>Volgende stap

[Bronnen voor leerinhoud configureren voor Viva Learning (preview) in het Microsoft 365-beheercentrum](content-sources-365-admin-center.md)
