---
title: Een aangepaste gebruikersweergave maken, bewerken of verwijderen in Office 365
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 4fe7f6ac-be8e-4b57-9e13-24ff889a4b28
description: Informatie over het gebruik van filters om aangepaste gebruikersweergave in Office 365 te maken, bewerken of verwijderen.
ms.openlocfilehash: ba03d3da3e8bfdc4f2a661d1dc59845a8a22609f
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42810279"
---
# <a name="create-edit-or-delete-a-custom-user-view-in-office-365"></a>Een aangepaste gebruikersweergave maken, bewerken of verwijderen in Office 365

Als u een hoofdbeheerder of een beheerder voor gebruikerstoegang van Office 365 bent, kunt u aangepaste gebruikersweergaven maken waarmee een specifieke subset van gebruikers kan worden weergegeven. Deze weergaven vormen een aanvulling op de standaardweergaven van Office 365. U kunt aangepaste gebruikersweergaven maken, bewerken of verwijderen en de aangepaste weergaven die u maakt, zijn beschikbaar voor alle beheerders.

::: moniker range="o365-worldwide"

> [!NOTE]
> Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.

::: moniker-end
  
## <a name="custom-user-views-in-the-admin-center"></a>Aangepaste gebruikersweergaven in het beheercentrum

::: moniker range="o365-worldwide"

Wanneer u een aangepaste gebruikersweergave maakt, bewerkt of verwijdert, worden de wijzigingen weergegeven in de lijst **Filter** die alle beheerders in uw bedrijf zien wanneer ze naar de pagina **Gebruikers** gaan. U kunt maximaal vijftig aangepaste weergaven maken. 

::: moniker-end

::: moniker range="o365-germany"

Wanneer u een aangepaste gebruikersweergave maakt, bewerkt of verwijdert, worden de wijzigingen weergegeven in de lijst **Weergaven** die alle beheerders in uw bedrijf zien wanneer ze naar de pagina **Gebruikers** gaan. U kunt maximaal vijftig aangepaste weergaven maken. 

::: moniker-end

::: moniker range="o365-21vianet"

Wanneer u een aangepaste gebruikersweergave maakt, bewerkt of verwijdert, worden de wijzigingen weergegeven in de lijst **Weergaven** die alle beheerders in uw bedrijf zien wanneer ze naar de pagina **Gebruikers** gaan. U kunt maximaal vijftig aangepaste weergaven maken. 

::: moniker-end

> [!TIP]
>  Standaard worden standaardgebruikersweergaven weergegeven in de vervolgkeuzelijst **Filters**. De standaardfilters omvatten **alle gebruikers**, **gelicentieerde gebruikers,** **gastgebruikers**, **Aanmelden toegestaan,** **Aanmelden geblokkeerd,** **gebruikers zonder licentie**, gebruikers **met fouten,** **factureringsbeheerders,** **globale beheerders,** **helpdeskbeheerders,** **servicebeheerders**en **gebruikersbeheerbeheerders**. U kunt standaardweergaven niet bewerken of verwijderen. 

Let op het volgende in verband met standaardweergaven: 

- In bepaalde standaardweergaven wordt een ongesorteerde lijst weergegeven als de lijst meer dan 2.000 gebruikers bevat. Via het zoekvak kunt u vervolgens zoeken naar specifieke gebruikers in deze lijst. 
- Als u Office 365 niet bij Microsoft hebt gekocht, wordt **Financieel medewerkers** niet weergegeven in de lijst met standaardweergaven. Zie [Beheerdersrollen toewijzen](assign-admin-roles.md) voor meer informatie. 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a>Kies de filters voor de aangepaste gebruikersweergave

U uw aangepaste weergaven maken en bewerken in het **deelvenster Aangepast filter.** Als u meerdere filteropties selecteert, bevatten de resultaten de gebruikers die voldoen aan alle geselecteerde criteria. In het volgende voorbeeld ziet u hoe u een aangepaste weergave met de naam 'Canadese gebruikers' maakt, waarin alle gebruikers worden weergegeven op een specifiek domein en in Canada. 

  
 **A - Domein** Als u meerdere domeinen voor uw organisatie hebt, u kiezen uit een vervolgkeuzelijst met domeinen die beschikbaar zijn. 
  
 **B - Aanmeldingsstatus** Kies gebruikers die zijn toegestaan of geblokkeerd. 
  
 **C - Locatie** Kies een locatie uit een vervolgkeuzelijst met landen. 
  
 **D - Toegewezen productlicentie** Kies uit een vervolgkeuzelijst met licenties die beschikbaar zijn bij uw organisatie. Gebruik dit filter als u gebruikers wilt weergeven waaraan de geselecteerde licentie is toegewezen. Gebruikers kunnen meerdere licenties hebben. 
  
Ook kunt u filteren op andere gegevens uit het gebruikersprofiel die worden gebruikt in uw organisatie, zoals afdeling, plaats, staat of provincie, land of regio, of functie.
  
 **Overige voorwaarden:**
  
- **Alleen gesynchroniseerde gebruikers** Selecteer dit vakje als u alle gebruikers wilt weergeven die zijn gesynchroniseerd met de lokale Active Directory, ongeacht of ze zijn geactiveerd. 
    
- **Gebruikers met fouten** Selecteer dit vakje als u gebruikers wilt weergeven waarvoor mogelijk inrichtingsfouten zijn opgetreden. 
    
- **Gebruikers zonder licentie** Selecteer dit vakje als u alle gebruikers wilt weergeven waaraan geen licentie is toegewezen. Het resultaat van deze weergave kan ook gebruikers omvatten die een Exchange-postvak hebben maar geen licentie. Als u deze gebruikers specifiek wilt opsporen, gebruikt u het filter **Gebruikers zonder licentie met Exchange-postvakken of -archieven**. Het resultaat van deze weergave kan ook gebruikers omvatten die een Exchange-archief hebben maar geen licentie.
    
- **Gebruikers zonder licentie met Exchange-postvakken of -archieven** Selecteer dit vakje als u gebruikersaccounts wilt weergeven die zijn gemaakt in Exchange Online en een Exchange-postvak hebben, maar waaraan geen Office 365-licentie is toegewezen. De resultaten van dit filter omvatten gebruikers met een Exchange-archief of waaraan een archief is toegewezen. 
    
> [!TIP]
> Als u een aangepaste weergave maakt die meer dan 2.000 gebruikers oplevert, is de resulterende lijst ongesorteerd. Gebruik in dit geval het zoekvak om gebruikers te vinden of uw aangepaste weergave te bewerken om uw zoekopdracht te verfijnen. 
  
## <a name="create-a-custom-user-view"></a>Een aangepaste gebruikersweergave maken

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.
    
2. Selecteer op de pagina **Actieve gebruikers** de optie **Filters** en selecteer **Nieuw filter**.
  
3. Voer **op** de pagina Aangepast filter de naam voor uw filter in, kies de voorwaarden voor uw aangepaste filter en selecteer **Toevoegen**. Uw aangepaste weergave is nu opgenomen in de vervolgkeuzelijst met filters.
    
::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.  

2. Selecteer **weergaven** op de pagina **Actieve gebruikers** en selecteer Aangepaste **weergave toevoegen**.
  
3. Voer op de pagina **Aangepaste weergave** de naam voor uw filter in, kies de voorwaarden voor uw aangepaste filter en selecteer **Toevoegen**. Uw aangepaste weergave is nu opgenomen in de vervolgkeuzelijst met filters.

::: moniker-end


::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>. 

2. Selecteer **weergaven** op de pagina **Actieve gebruikers** en selecteer Aangepaste **weergave toevoegen**.
  
3. Voer op de pagina **Aangepaste weergave** de naam voor uw filter in, kies de voorwaarden voor uw aangepaste filter en selecteer **Toevoegen**. Uw aangepaste weergave is nu opgenomen in de vervolgkeuzelijst met filters.

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a>Een aangepaste gebruikersweergave bewerken of verwijderen

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.
    
2. Selecteer op de pagina **Actieve gebruikers** De optie **Filter,** selecteer het filter dat u wilt wijzigen en selecteer **vervolgens Filter bewerken**. 
    
    > [!TIP]
    > U kunt alleen aangepaste weergaven bewerken. 
  
3. Bewerk de gegevens op de pagina **Aangepast filter** indien nodig en selecteer **Opslaan**. Of, als u het filter wilt verwijderen, selecteert u onder aan de pagina **Verwijderen**. 
    
::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.  

2. Selecteer op de pagina **Actieve gebruikers** **weergaven,** selecteer het filter dat u wilt wijzigen en selecteer **deze weergave bewerken**. 
    
    > [!TIP]
    > U kunt alleen aangepaste weergaven bewerken. 
  
3. Bewerk de gegevens indien nodig op de pagina **Aangepaste weergave** en selecteer **Opslaan**. Als u het filter wilt verwijderen, selecteert u onder aan de pagina **Aangepaste weergave verwijderen**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>. 

2. Selecteer op de pagina **Actieve gebruikers** **weergaven,** selecteer het filter dat u wilt wijzigen en selecteer **deze weergave bewerken**. 
    
    > [!TIP]
    > U kunt alleen aangepaste weergaven bewerken. 
  
3. Bewerk de gegevens indien nodig op de pagina **Aangepaste weergave** en selecteer **Opslaan**. Als u het filter wilt verwijderen, selecteert u onder aan de pagina **Aangepaste weergave verwijderen**. 

::: moniker-end


     

