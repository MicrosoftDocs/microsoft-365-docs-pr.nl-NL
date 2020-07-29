---
title: Werken met App-beheer
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9efe6ba6704b0e1633973d157c38827221316bbd
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430445"
---
# <a name="work-with-app-control"></a>Werken met App-beheer

Zodra app-besturingselement in uw omgeving is geïmplementeerd, hebben zowel u als Microsoft Managed Desktop Operations lopende verantwoordelijkheden. U bijvoorbeeld een nieuwe app in de omgeving toevoegen of een vertrouwde ondertekenaar toevoegen (of verwijderen). Om de beveiliging te verbeteren, moeten alle apps zijn ondertekend met code voordat u ze vrijlaat aan eindgebruikers. De uitgeversgegevens van een app bevatten informatie over de ondertekenaar.


## <a name="add-a-new-app"></a>Een nieuwe app toevoegen

Voer de volgende stappen uit om een nieuwe app toe te voegen:

1. Voeg de app toe aan [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management).
2. Implementeer de app op elk apparaat in de testring. 
3. Test uw app op basis van uw standaard bedrijfsprocessen. 
4. Controleer Logboeken onder **Toepassings- en Serviceslogboeken\Microsoft\Windows\AppLocker**, op zoek naar **8003-** of **8006-gebeurtenissen.** Deze gebeurtenissen geven aan dat de app zou worden geblokkeerd. Zie [Logboeken gebruiken met AppLocker voor](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)meer informatie over alle App Locker-evenementen en hun betekenissen.
5. Als u een van deze gebeurtenissen vindt, opent u een aanvraag voor ondertekenaars met Microsoft Managed Desktop Operations.

## <a name="add-or-remove-a-trusted-signer"></a>Een vertrouwde ondertekenaar toevoegen (of verwijderen)

Wanneer u een ondertekenaaraanvraag opent, moet u eerst een aantal belangrijke uitgeversgegevens opgeven. Volg dan de volgende stappen:

1. [Gegevens van uitgevers verzamelen.](#gather-publisher-details)
2. Open een ticket met Microsoft Managed Desktop Operations om de ondertekenaarregel op te vragen en de volgende details op te nemen:  
    - Toepassingsnaam 
    - Toepassingsversie 
    - Beschrijving 
    - Type wijzigen ('toevoegen' of 'verwijderen')  
    - Uitgeversgegevens (bijvoorbeeld: "O= <publisher name> ,L= <location> ,S=State,C=Country") 

> [!NOTE]
> Als u vertrouwen voor een app wilt verwijderen, voert u dezelfde stappen uit, maar stelt **u Type Wijzigen** in om te *verwijderen.*

Operations implementeert geleidelijk beleid naar implementatiegroepen volgens deze planning:


|Implementatiegroep  |Beleidstype  |Timing  |
|---------|---------|---------|
|Test     |  Audit       |  Dag 0       |
|Eerste     | Afgedwongen        | Dag 1        |
|Snel     | Afgedwongen        |  Dag 2       |
|Brede     | Afgedwongen        |  Dag 3       |


U de implementatie op elk gewenst moment tijdens de implementatie onderbreken of terugdraaien. Open hiervoor een andere serviceaanvraag met Operations.

> [!NOTE]
> Als u de release van een ondertekenaarregel onderbreekt, moet deze regel worden teruggedraaid of voltooid voordat een andere implementatie kan worden gestart.

## <a name="gather-publisher-details"></a>Uitgeversgegevens verzamelen

Voer de volgende stappen uit om toegang te krijgen tot de uitgeversgegevens voor een app:

1. Zoek een Microsoft Managed Desktop-apparaat in de testring waarop een controlemodusbeleid is toegepast. 
2. Probeer de app op het apparaat te installeren.
3. Open Logboeken op dat apparaat. 
4. Navigeer in Logboeken naar **toepassings- en serviceslogboeken\Microsoft\Windows**en selecteer **vervolgens AppLocker**. 
5. Zoek een gebeurtenis van **8003** of **8006** en kopieer vervolgens informatie uit de gebeurtenis: 
    - Toepassingsnaam 
    - Toepassingsversie 
    - Beschrijving 
    - Uitgeversgegevens (bijvoorbeeld: "O= <publisher name> , L= <location> , S=State, C=Country") 
