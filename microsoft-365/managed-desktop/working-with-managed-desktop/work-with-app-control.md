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
ms.openlocfilehash: 0b76a14a30caeb75cfdcb8acc5715fe6710e0625
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289457"
---
# <a name="work-with-app-control"></a>Werken met App-beheer

Wanneer het app-besturingselement is geïmplementeerd in uw omgeving, hebben zowel u als door Microsoft beheerde bureaublad bewerkingen voortdurend verantwoordelijkheden. U kunt bijvoorbeeld een nieuwe app toevoegen aan de omgeving of een vertrouwde ondertekenaar toevoegen of verwijderen. Ter verbetering van de beveiliging moeten alle apps met een code zijn ondertekend voordat u ze vrijgeeft aan gebruikers. De details van de app van een app bevatten informatie over de ondertekenaar.


## <a name="add-a-new-app"></a>Een nieuwe app toevoegen

Voer de volgende stappen uit om een nieuwe app toe te voegen:

1. Voeg de app toe aan [Microsoft intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management).
2. Implementeer de app op een willekeurig apparaat in de test ring. 
3. Test de app op basis van uw standaardbedrijfsprocessen. 
4. Ga naar Logboekinzage onder **toepassingen en services Logs\Microsoft\Windows\AppLocker**en zoek naar gebeurtenissen van **8003** of **8006** . Deze gebeurtenissen geven aan dat de app wordt geblokkeerd. Zie voor meer informatie over de app-waarschuwingen en hun betekenissen [Logboeken met behulp van AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).
5. Als u een van deze gebeurtenissen vindt, opent u een aanvraag voor een afzender met Microsoft beheerde bureaublad bewerkingen.

## <a name="add-or-remove-a-trusted-signer"></a>Een vertrouwde ondertekenaar toevoegen (of verwijderen)

Wanneer u een Onderteken aanvraag opent, moet u eerst enkele belangrijke details van de uitgever geven. Voer daarna de volgende stappen uit:

1. [Details van de uitgever verzamelen](#gather-publisher-details).
2. Open een ticket met door Microsoft beheerde bureaublad bewerkingen om de ondertekenaars regel te aanvragen en de volgende details weer te geven:  
    - Naam van toepassing 
    - Toepassingsversie 
    - Beschrijving 
    - Type wijzigen (' toevoegen ' of ' verwijderen ')  
    - Details van de uitgever (bijvoorbeeld: "O = <publisher name> , L = <location> , S = staat, C = Country") 

> [!NOTE]
> Als u het vertrouwen voor een app wilt verwijderen, voert u dezelfde stappen uit maar stelt u het **type wijzigen** in dat u wilt *verwijderen*.

Met bewerkingen worden de beleidsregels progressief geïmplementeerd voor implementatie groepen die het volgende schema volgen:


|Implementatiegroep  |Beleidstype  |Tijdsinstellingen  |
|---------|---------|---------|
|Wedstrijden     |  Oordeel       |  Dag 0       |
|Eerste     | Afgedwongen        | Dag 1        |
|Razendsnelle     | Afgedwongen        |  Dag 2       |
|Scala     | Afgedwongen        |  Dag 3       |


U kunt op elk gewenst moment tijdens de implementatie de implementatie onderbreken of terugdraaien. Open hiervoor een andere serviceaanvraag met bewerkingen.

> [!NOTE]
> Als u de release van een handtekeningregel onderbreekt, moet die regel worden hersteld of voltooid voordat een andere implementatie kan worden gestart.

## <a name="gather-publisher-details"></a>Details van de uitgever verzamelen

Voer de volgende stappen uit om toegang te krijgen tot de gegevens van de uitgever van de app:

1. Zoek een Microsoft-beheerapparaat in de test ring waarop een beleid voor controlemodus is toegepast. 
2. Probeer de app op het apparaat te installeren.
3. Open de logboek viewer op dat apparaat. 
4. Ga in logboeken naar **toepassingen en services Logs\Microsoft\Windows**en selecteer vervolgens **AppLocker**. 
5. Zoek een willekeurige gebeurtenis in **8003** of **8006** en kopieer de gegevens uit de gebeurtenis: 
    - Naam van toepassing 
    - Toepassingsversie 
    - Beschrijving 
    - Details van de uitgever (bijvoorbeeld: "O = <publisher name> , L = <location> , S = staat, C = Country") 
