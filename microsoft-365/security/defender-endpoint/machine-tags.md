---
title: Apparaatlabels maken en beheren
description: Apparaatlabels gebruiken om apparaten te groepen om context vast te leggen en het maken van dynamische lijst in te stellen als onderdeel van een incident
keywords: tags, apparaatlabels, apparaatgroepen, groepen, herstel, niveau, regels, aadgroep, rol, toewijzen, rang
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ffe7d13ca0943e8927d0d9ce663527fedf880e48
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187587"
---
# <a name="create-and-manage-device-tags"></a>Apparaatlabels maken en beheren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Voeg tags toe aan apparaten om een logische groep te maken. Apparaatlabels ondersteunen de juiste toewijzing van het netwerk, zodat u verschillende tags kunt koppelen om context vast te leggen en dynamische lijstcreatie als onderdeel van een incident kunt inschakelen. Tags kunnen worden gebruikt als filter in de lijstweergave **Apparaten** of om apparaten te groeperen. Zie Apparaatgroepen maken en beheren voor meer informatie over [apparaatgroepering.](machine-groups.md)

U kunt op de volgende manieren tags toevoegen op apparaten:

- De portal gebruiken
- Een registersleutelwaarde instellen

> [!NOTE]
> Er kan enige latentie zijn tussen het moment dat een tag wordt toegevoegd aan een apparaat en de beschikbaarheid ervan in de lijst met apparaten en de pagina met apparaten.  

Zie Api voor apparaatlabels toevoegen of verwijderen als u apparaatlabels wilt toevoegen met [API.](add-or-remove-machine-tags.md)

## <a name="add-and-manage-device-tags-using-the-portal"></a>Apparaatlabels toevoegen en beheren met de portal

1. Selecteer het apparaat waar u tags op wilt beheren. U kunt een apparaat selecteren of zoeken in een van de volgende weergaven:

   - **Dashboard Beveiligingsbewerkingen:** selecteer de naam van het apparaat in de sectie Topapparaten met actieve waarschuwingen.
   - **Waarschuwingenwachtrij:** selecteer de naam van het apparaat naast het apparaatpictogram in de waarschuwingenwachtrij.
   - **Lijst met** apparaten: selecteer de naam van het apparaat in de lijst met apparaten.
   - **Zoekvak:** selecteer Apparaat in de vervolgkeuzelijst en voer de naam van het apparaat in.

     U kunt ook naar de waarschuwingspagina gaan via de bestands- en IP-weergaven.

2. Selecteer **Tags beheren** in de rij met antwoordacties.

    ![Afbeelding van de knop Tags beheren](images/manage-tags.png)

3. Typen om tags te zoeken of te maken

    ![Afbeelding van het toevoegen van tags op een apparaat1](images/new-tags.png)

Tags worden toegevoegd aan de apparaatweergave en worden ook weergegeven in de **lijstweergave** Apparaten. Vervolgens kunt u het filter **Tags gebruiken** om de relevante lijst met apparaten te bekijken.

>[!NOTE]
> Filteren werkt mogelijk niet op tagnamen die haakjes bevatten.<br>
> Wanneer u een nieuwe tag maakt, wordt een lijst met bestaande tags weergegeven. In de lijst worden alleen tags weergegeven die zijn gemaakt via de portal. Bestaande tags die zijn gemaakt op clientapparaten, worden niet weergegeven.

U kunt ook tags uit deze weergave verwijderen.

![Afbeelding van het toevoegen van tags op een apparaat2](images/more-manage-tags.png)

## <a name="add-device-tags-by-setting-a-registry-key-value"></a>Apparaatlabels toevoegen door een registersleutelwaarde in te stellen

>[!NOTE]
> Alleen van toepassing op de volgende apparaten:
>- Windows 10, versie 1709 of hoger
>- Windows Server, versie 1803 of hoger
>- Windows Server 2016
>- Windows Server 2012 R2
>- Windows Server 2008 R2 SP1
>- Windows 8.1
>- Windows 7 SP1

> [!NOTE] 
> Het maximum aantal tekens dat in een tag kan worden ingesteld, is 200.

Apparaten met vergelijkbare tags kunnen handig zijn wanneer u contextuele actie moet toepassen op een specifieke lijst met apparaten.

Gebruik de volgende registersleutelinvoer om een tag toe te voegen op een apparaat:

- Registersleutel: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`
- Registersleutelwaarde (REG_SZ): `Group`
- Registersleutelgegevens: `Name of the tag you want to set`

>[!NOTE]
>De apparaattag maakt deel uit van het apparaatinformatierapport dat eenmaal per dag wordt gegenereerd. Als alternatief kunt u ervoor kiezen om het eindpunt opnieuw op te starten dat een nieuw apparaatinformatierapport zou overbrengen.
> 
> Als u een tag wilt verwijderen die is toegevoegd met de bovenstaande registersleutel, verwijdert u de inhoud van de registersleutelgegevens in plaats van de 'Groep'-toets te verwijderen.
