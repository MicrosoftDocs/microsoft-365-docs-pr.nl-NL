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
ms.openlocfilehash: 31cc897fe28f557a65cba9c99e5dcecbf7c2b0e5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917638"
---
# <a name="work-with-app-control"></a>Werken met App-beheer

Nadat app-beheer is geïmplementeerd in uw omgeving, hebben zowel u als Microsoft Managed Desktop Operations lopende verantwoordelijkheden. U kunt bijvoorbeeld een nieuwe app in de omgeving toevoegen of een vertrouwde ondertekenaar toevoegen (of verwijderen). Om de beveiliging te verbeteren, moeten alle apps code-ondertekend zijn voordat u ze aan gebruikers los laat. De uitgeverdetails van een app bevatten informatie over de ondertekenaar.


## <a name="add-a-new-app"></a>Een nieuwe app toevoegen

Als u een nieuwe app wilt toevoegen, volgt u de volgende stappen:

1. Voeg de app toe aan [Microsoft Intune.](/mem/intune/apps/apps-win32-app-management)
2. Implementeer de app op elk apparaat in de testring. 
3. Test uw app op basis van uw standaard bedrijfsprocessen. 
4. Controleer Gebeurtenisviewer onder **Toepassings- en serviceslogboeken\Microsoft\Windows\AppLocker**, op zoek naar **8003** of **8006 gebeurtenissen.** Deze gebeurtenissen geven aan dat de app wordt geblokkeerd. Zie [Gebeurtenisviewer gebruiken met AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)voor meer informatie over alle gebeurtenissen in App Locker en hun betekenis.
5. Als u een van deze gebeurtenissen vindt, opent u een aanmeldingsaanvraag met Microsoft Managed Desktop Operations.

## <a name="add-or-remove-a-trusted-signer"></a>Een vertrouwde ondertekenaar toevoegen (of verwijderen)

Wanneer u een aanvraag voor een ondertekenaar opent, moet u eerst enkele belangrijke details van de uitgever verstrekken. Volg vervolgens de volgende stappen:

1. [Publisher-details verzamelen.](#gather-publisher-details)
2. Open een ticket met Microsoft Managed Desktop Operations om de ondertekenaarsregel aan te vragen en neem de volgende details op:  
    - Naam van toepassing 
    - Toepassingsversie 
    - Beschrijving 
    - Type wijzigen ("toevoegen" of "verwijderen")  
    - Publisher details (bijvoorbeeld: "O= <publisher name> ,L= <location> ,S=State,C=Country") 

> [!NOTE]
> Als u vertrouwen voor een app wilt verwijderen, volgt u dezelfde stappen, maar stelt u **Type wijzigen in** om deze te *verwijderen.*

In Operations worden beleidsregels geleidelijk geïmplementeerd voor implementatiegroepen volgens deze planning:


|Implementatiegroep  |Beleidstype  |Tijdsinstellingen  |
|---------|---------|---------|
|Test     |  Controle       |  Dag 0       |
|Eerst     | Afgedwongen        | Dag 1        |
|Snel     | Afgedwongen        |  Dag 2       |
|Breed     | Afgedwongen        |  Dag 3       |


U kunt de implementatie op elk moment tijdens de implementatie onderbreken of terugdraaien. Open hiervoor een andere serviceaanvraag met Operations.

> [!NOTE]
> Als u de release van een ondertekenaarsregel pauzeert, moet deze regel worden teruggedraaid of voltooid voordat een andere uitrol kan worden uitgevoerd.

## <a name="gather-publisher-details"></a>Publisher-details verzamelen

Als u de publisher-gegevens voor een app wilt openen, gaat u als volgt te werk:

1. Zoek een Microsoft Managed Desktop apparaat in de testring waarin een auditmodusbeleid is toegepast. 
2. Probeer de app op het apparaat te installeren.
3. Open Gebeurtenisviewer op dat apparaat. 
4. Ga in Gebeurtenisviewer naar **Toepassings- en serviceslogboeken\Microsoft\Windows** en selecteer **Vervolgens AppLocker.** 
5. Zoek een **8003-** of **8006-gebeurtenis** en kopieer gegevens uit de gebeurtenis: 
    - Naam van toepassing 
    - Toepassingsversie 
    - Beschrijving 
    - Publisher details (bijvoorbeeld: "O= <publisher name> , L= <location> , S=State, C=Country")