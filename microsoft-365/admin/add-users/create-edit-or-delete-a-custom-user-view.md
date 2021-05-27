---
title: Een aangepaste gebruikersweergave maken, bewerken of verwijderen
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 4fe7f6ac-be8e-4b57-9e13-24ff889a4b28
description: Lees hoe u filters kunt gebruiken om aangepaste gebruikersweergave te maken, te bewerken of te verwijderen in Microsoft 365.
ms.openlocfilehash: b4177a561d13d76f6d5a0a1077fe8037d469ee48
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683221"
---
# <a name="create-edit-or-delete-a-custom-user-view"></a>Een aangepaste gebruikersweergave maken, bewerken of verwijderen

Als u een globale beheerder of beheerder van gebruikersbeheer bent van een Microsoft 365 voor bedrijven-abonnement, kunt u aangepaste gebruikersweergaven maken om een specifieke subset van gebruikers weer te geven. Deze weergaven komen bovenop de standaardset weergaven. U kunt aangepaste gebruikersweergaven maken, bewerken of verwijderen en de aangepaste weergaven die u maakt, zijn beschikbaar voor alle beheerders.
  
## <a name="custom-user-views-in-the-admin-center"></a>Aangepaste gebruikersweergaven in het beheercentrum

Wanneer u een aangepaste gebruikersweergave maakt, bewerkt of verwijdert, worden de wijzigingen weergegeven in de lijst **Filter** die alle beheerders in uw bedrijf zien wanneer ze naar de pagina **Gebruikers** gaan. U kunt maximaal vijftig aangepaste weergaven maken. 

> [!TIP]
>  Standaard worden standaardgebruikersweergaven weergegeven in de vervolgkeuzelijst **Filters**. De **standaardfilters** zijn Alle gebruikers **,** Gelicentieerde gebruikers **,** **Gastgebruikers** **,** Aanmelding toegestaan **,** Aanmelding geblokkeerd , Gebruikers zonder licentie **,** Gebruikers met fouten , **Factureringsbeheerders**, **Globale beheerders**, **Helpdeskbeheerders**, **Servicebeheerders** en Beheerders van **gebruikersbeheer**. U kunt standaardweergaven niet bewerken of verwijderen. 

Let op het volgende in verband met standaardweergaven: 

- In bepaalde standaardweergaven wordt een ongesorteerde lijst weergegeven als de lijst meer dan 2.000 gebruikers bevat. Via het zoekvak kunt u vervolgens zoeken naar specifieke gebruikers in deze lijst. 
- Als u geen Microsoft 365 bij Microsoft hebt gekocht, worden **factureringsbeheerders** niet weergegeven in de lijst met standaardweergaven. Zie [Beheerdersrollen toewijzen](assign-admin-roles.md) voor meer informatie. 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a>Kies de filters voor de aangepaste gebruikersweergave

U kunt uw aangepaste weergaven maken en bewerken in **het deelvenster Aangepast filter.** Als u meerdere filteropties selecteert, bevatten de resultaten de gebruikers die voldoen aan alle geselecteerde criteria. In het volgende voorbeeld ziet u hoe u een aangepaste weergave met de naam 'Canadese gebruikers' maakt, waarin alle gebruikers worden weergegeven op een specifiek domein en in Canada. 

  
 **A - Domein** Als u meerdere domeinen voor uw organisatie hebt, kunt u kiezen uit een vervolgkeuzelijst met beschikbare domeinen. 
  
 **B - Aanmeldingsstatus** Kies gebruikers die zijn toegestaan of geblokkeerd. 
  
 **C - Locatie** Kies een locatie in een vervolgkeuzelijst met landen. 
  
 **D - Productlicentie toegewezen** Kies uit een vervolgkeuzelijst met licenties die beschikbaar zijn in uw organisatie. Gebruik dit filter als u gebruikers wilt weergeven waaraan de geselecteerde licentie is toegewezen. Gebruikers kunnen meerdere licenties hebben. 
  
Ook kunt u filteren op andere gegevens uit het gebruikersprofiel die worden gebruikt in uw organisatie, zoals afdeling, plaats, staat of provincie, land of regio, of functie.
  
 **Overige voorwaarden:**
  
- **Alleen gesynchroniseerde gebruikers** Selecteer dit vakje als u alle gebruikers wilt weergeven die zijn gesynchroniseerd met de lokale Active Directory, ongeacht of ze zijn geactiveerd. 
    
- **Gebruikers met fouten** Selecteer dit vakje als u gebruikers wilt weergeven waarvoor mogelijk inrichtingsfouten zijn opgetreden. 
    
- **Gebruikers zonder licentie** Selecteer dit vakje als u alle gebruikers wilt weergeven waaraan geen licentie is toegewezen. Het resultaat van deze weergave kan ook gebruikers omvatten die een Exchange-postvak hebben maar geen licentie. Als u deze gebruikers specifiek wilt opsporen, gebruikt u het filter **Gebruikers zonder licentie met Exchange-postvakken of -archieven**. Het resultaat van deze weergave kan ook gebruikers omvatten die een Exchange-archief hebben maar geen licentie.
    
- **Gebruikers zonder vergunning met Exchange of archieven** Schakel dit vakje in om gebruikersaccounts weer te geven die zijn gemaakt in Exchange Online en een Exchange postvak hebben, maar die geen licentie Microsoft 365 toegewezen. De resultaten van dit filter omvatten gebruikers met een Exchange-archief of waaraan een archief is toegewezen. 

> [!NOTE]
> Het **filter Niet-gelicenseerde gebruikers Exchange postvakken** werkt als:
1. Het postvak is onlangs geconverteerd van **gedeeld** naar **gebruiker** en heeft geen licentie.
2. Het postvak is onlangs gemigreerd naar Microsoft 365 maar er is geen licentie toegewezen.
3. Het postvak is gemaakt met PowerShell en er is geen licentie toegewezen.
4. Een nieuw postvak dat on-premises is gemaakt met een New-RemoteMailbox cmdlet is ingericht voor de gebruiker.
    
> [!TIP]
> Als u een aangepaste weergave maakt die meer dan 2.000 gebruikers oplevert, is de resulterende lijst ongesorteerd. Gebruik in dit geval het zoekvak om gebruikers te zoeken of uw aangepaste weergave te bewerken om uw zoekopdracht te verfijnen. 
  
## <a name="create-a-custom-user-view"></a>Een aangepaste gebruikersweergave maken

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers.</a>
  
::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers.</a> 

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers.</a>  

::: moniker-end
    
2. Selecteer op **de pagina** Actieve gebruikers de **optie Filters** en selecteer **Nieuw filter.**
  
3. Voer op **de pagina** Aangepast filter de naam voor het filter in, kies de voorwaarden voor het aangepaste filter en selecteer **vervolgens Toevoegen.** Uw aangepaste weergave wordt nu opgenomen in de vervolgkeuzelijst met filters.

## <a name="edit-or-delete-a-custom-user-view"></a>Een aangepaste gebruikersweergave bewerken of verwijderen

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers.</a>

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers.</a> 

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers.</a> 

::: moniker-end 
    
2. Selecteer op **de pagina** Actieve gebruikers de optie **Filter,** selecteer het filter dat u wilt wijzigen en selecteer **vervolgens Filter bewerken.** 
    
    > [!TIP]
    > U kunt alleen aangepaste weergaven bewerken. 
  
3. Bewerk **de gegevens op** de pagina Aangepast filter zo nodig en selecteer **opslaan.** Of als u het filter wilt verwijderen, selecteert u onder aan de pagina **Verwijderen.** 

## <a name="related-content"></a>Verwante inhoud

[Overzicht van het Microsoft 365](../../business-video/admin-center-overview.md) (video)\
[Over beheerdersrollen](../add-users/about-admin-roles.md) (video)\
[Het thema Microsoft 365 uw organisatie aanpassen](../setup/customize-your-organization-theme.md) (artikel)


     