---
title: Basisinfrastructuur voor Microsoft 365 voor ondernemingen
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Krijg inzicht in de belangrijkste fasen van het implementeren van de basisinfrastructuur voor Microsoft 365 voor ondernemingen in uw organisatie, ook wel bekend als de kernimplementatie.
ms.openlocfilehash: 966fa8ad26d54328bf4d2e95c95b497e5d283e52
ms.sourcegitcommit: 6adfcf042e64b21f09f2b8e072e8eba6d3479e31
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2020
ms.locfileid: "42951956"
---
# <a name="microsoft-365-for-enterprise-foundation-infrastructure"></a>Basisinfrastructuur voor Microsoft 365 voor ondernemingen

Als u zelf de end-to-end-implementatie van Microsoft 365 voor ondernemingen uitvoert, moet u eerst een stevige basis bouwen waarop met toepassingen en services creativiteit en teamwork in een veilige omgeving mogelijk worden gemaakt. Deze basis wordt soms ook wel een *kernimplementatie* genoemd.

Voor een gedefinieerd end-to-end-pad voor implementatie kunt u deze fasen gebruiken om de basisinfrastructuur van Microsoft 365 voor ondernemingen te plannen en te implementeren:

| | Fase | Resultaten |
|:-------|:-----|:-----|
|![Fase 1: Netwerk](../media/deploy-foundation-infrastructure/networking_icon-small.png)|[Fase 1: Netwerk](networking-infrastructure.md)| Uw netwerk wordt geoptimaliseerd voor toegang tot de cloudservices van Microsoft 365. |
|![Fase 2 : Identiteit](../media/deploy-foundation-infrastructure/identity_icon-small.png)|[Fase 2: Identiteit](identity-infrastructure.md)| Uw beheerdersaccounts worden beveiligd, uw gebruikers en groepen worden gesynchroniseerd en uw gebruikersverificatie is sterk. |
|![Fase 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)|[Fase 3: Windows 10 Enterprise](windows10-infrastructure.md)| Voor uw bestaande Windows-computers kan een upgrade worden uitgevoerd naar Windows 10 Enterprise en op nieuwe apparaten wordt Windows 10 Enterprise geïnstalleerd. |
|![Fase 4: Office 365 ProPlus](../media/deploy-foundation-infrastructure/O365proplus_icon-small.png)|[Fase 4: Office 365 ProPlus](office365proplus-infrastructure.md)| Bestaande gebruikers van Microsoft Office kunnen een upgrade uitvoeren naar Office 365 ProPlus. |
|![Fase 5: Mobile Device Management](../media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)|[Fase 5: Mobile Device Management](mobility-infrastructure.md)| Uw apparaten kunnen worden geregistreerd en beheerd. |
|![Fase 6: Gegevensbeveiliging](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)|[Fase 6: Gegevensbeveiliging](infoprotect-infrastructure.md)| De beveiligingsfuncties van Office 365 worden ingeschakeld en uw labels en beleid zijn gereed om documenten en e-mail te beschermen. |

De fasen beginnen met het meest essentiële (netwerken en identiteiten) en vervolgens worden er lagen met infrastructuurinstellingen en -groepen gemaakt voor het volgende:

- De meest recente en veilige versie van Windows op uw apparaten installeren en deze up-to-date houden.
- De meest recente versie van Microsoft Office op uw apparaten installeren en deze up-to-date houden.
- De apparaten van uw organisatie en hun toegang tot apps beheren.
- De informatie op deze apparaten en in de cloud beschermen.

U hebt echter de flexibiliteit om de fasen of stappen in de fasen zo te configureren en uit te voeren dat deze passen bij uw IT-resources en zakelijke behoeften.

- **Als u een kleinere of nieuwere organisatie bent**, volgt u de fasen die nodig zijn om de infrastructuur methodisch uit te bouwen. Klik [hier](deploy-foundation-infrastructure-non-enterprises.md) voor een vereenvoudigde implementatie voor middelgrote bedrijven.

-  **Als u een grote onderneming bent**, bekijkt u de fasen als lagen IT-infrastructuur in plaats van een gedefinieerd pad en bepaalt u hoe u het beste zo te werk kunt gaan dat er wordt voldaan aan de vereisten voor elke laag in uw organisatie.

Aan het einde van elke fase moet u de *afsluitcriteria* bekijken. Hiermee worden de vereiste voorwaarden aangegeven waaraan moet worden voldaan en optionele voorwaarden die kunnen worden overwogen. Met de afsluitcriteria voor elke fase wordt gewaarborgd dat uw on-premises en cloudinfrastructuur en de resulterende end-to-end-configuratie voldoen aan de vereisten voor een Microsoft 365-implementatie voor ondernemingen.

Bekijk deze korte video als u wilt zien hoe de inhoud is gestructureerd.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE23VRG]

Hier volgt de basisinfrastructuur in de algemene implementatiehandleiding voor Microsoft 365 voor ondernemingen:

![De basisinfrastructuur in de algemene implementatiehandleiding voor Microsoft 365 voor ondernemingen](../media/deploy-foundation-infrastructure/m365-deploy-content-arch-foundation.png)

## <a name="at-a-glance"></a>In één oogopslag

De [poster Basisinfrastructuur voor Microsoft 365 voor ondernemingen](../media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf) is een centrale locatie die u voor elke fase kunt bekijken:

- De algemene doelstellingen van de fase voor beheerders en gebruikers
- De services, functies en hulpmiddelen
- De belangrijkste ontwerpbeslissingen bij de planning
- De configuratieresultaten
- Het proces voor de onboarding van een nieuwe gebruiker
- Controleren en bijwerken

[![Afbeelding voor de poster Basisinfrastructuur voor Microsoft 365 voor ondernemingen](../media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.png)](../media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf)

Als u een kopie van de poster wilt downloaden, klikt u [hier](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf).


## <a name="infrastructure-configuration-vs-user-rollout"></a>Configuratie van infrastructuur versus gebruikersimplementatie

De basisinfrastructuur bestaat uit een set geconfigureerde software en services die samen voor een gebruiker het volledige spectrum van mogelijkheden en bescherming bieden dat met Microsoft 365 voor ondernemingen mogelijk is. Het uiteindelijke doel van uw end-to-end-implementatietraject is om deze infrastructuur toe te passen voor al uw gebruikers en hun Windows-apparaten. 

Het is echter belangrijk om te weten dat de basisinfrastructuur van Microsoft 365 voor ondernemingen los staat van de implementatie van software en services voor uw gebruikers. ***U kunt de lagen van de basisinfrastructuur configureren zonder dat u die lagen voor al uw gebruikers hoeft te implementeren.***

Het is mogelijk om elementen van de basisinfrastructuur te configureren, te testen en uit te proberen ver voordat u deze elementen implementeert voor het merendeel van uw gebruikers in de kantoren, regio's of afdelingen van uw organisatie.

U kunt bijvoorbeeld de instellingen voor het volgende maken:

| Fase | Resultaten |
|:-------|:-----|
| Identiteit | Accountsynchronisatie en groepen voor voorwaardelijke toegang op basis van een identiteit. |
| Windows 10 Enterprise | Groepen om automatisch een upgrade uit te voeren voor computers met Windows 7 of Windows 8.1 naar Windows 10 Enterprise. |
| Office 365 ProPlus | Groepen voor het automatisch implementeren van Office 365 ProPlus voor gebruikers met Office 2010, Office 2013 of Office 2016. |
| Mobile Device Management | Groepen voor apparaatinschrijving en beleid voor voorwaardelijke toegang op basis van apparaten. |
| Gegevensbeveiliging | Groepen voor Office 365-gevoeligheidslabels. |

Wanneer u klaar bent om elementen van deze infrastructuur te implementeren voor gebruikers, kunt u het volgende doen:

| Fase | Implementatieactie |
|:-------|:-----|
| Identiteit | Gebruikersaccounts toevoegen aan de groepen voor beleid voor voorwaardelijke toegang op basis van een identiteit. |
| Windows 10 Enterprise | Accounts toevoegen aan de groepen om Windows 10 Enterprise automatisch te implementeren voor gebruikers met Windows 7 of Windows 8.1. |
| Office 365 ProPlus | Gebruikersaccounts toevoegen aan de groepen om Office 365 ProPlus automatisch te implementeren voor gebruikers met Office 2010, Office 2013 of Office 2016. |
| Mobile Device Management | Accounts toevoegen voor de groepen voor apparaatinschrijving en beleid voor voorwaardelijke toegang op basis van apparaten. |
| Gegevensbeveiliging | Gebruikersaccounts toevoegen aan de groepen voor gevoeligheidslabels. |

Zodra fasen of elementen van de basisinfrastructuur zijn voltooid, getest en uitgeprobeerd, kunt u geïnstalleerde software, zoals Windows 10 Enterprise en Office 365 ProPlus, en cloudservices en -bescherming, zoals apparaatinschrijving en beleid voor voorwaardelijke toegang, voor uw gebruikers implementeren op de manier die het beste past bij uw bedrijfsdoelen en IT-resources.

## <a name="deployment-and-project-management-strategies"></a>Strategieën voor implementatie en projectbeheer

Zie [Implementatiestrategieën](deployment-strategies-microsoft-365-enterprise.md) voor enkele ideeën voor het projectbeheer van de verschillende fasen van de basisinfrastructuur voor de eerste testgebruikers en de rest van uw organisatie.

## <a name="deployment-for-non-enterprises"></a>Implementatie voor middelgrote bedrijven

Als uw organisatie kleiner is en Microsoft 365 Business niet geschikt voor u is, raadpleegt u [Implementatie voor middelgrote bedrijven](deploy-foundation-infrastructure-non-enterprises.md) voor een vereenvoudigde implementatiemethode.


## <a name="next-step"></a>Volgende stap

| Waar ben ik | Waar moet ik naartoe |
|:-------|:-----|
| Ik heb een bestaande infrastructuur voor Office 365, Enterprise Mobility + Security (EMS) of Windows 10 Enterprise | Begin met het [implementeren met de bestaande infrastructuur](deploy-with-existing-infrastructure.md) waarmee u de afsluitcriteria voor elke fase doorloopt. |
| Ik start als onderneming helemaal bij het begin | Start uw end-to-end-implementatietraject met [Fase 1: Netwerk](networking-infrastructure.md). |
| Ik start als middelgroot bedrijf helemaal bij het begin | Start uw end-to-end-implementatietraject met [Implementatie voor middelgrote bedrijven](deploy-foundation-infrastructure-non-enterprises.md). |
