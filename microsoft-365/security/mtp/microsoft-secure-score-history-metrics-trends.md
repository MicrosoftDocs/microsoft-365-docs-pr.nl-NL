---
title: De geschiedenis van uw Microsoft Secure Score bijhouden en bereiken
description: U krijgt inzicht in activiteiten met gevolgen voor uw Microsoft Secure Score. Ontdekken van trends en het instellen van doelstellingen.
keywords: Microsoft Secure Score, Secure Score, Office 365 Secure Score, Microsoft Security Score, Microsoft 365 Beveiligingscentrum, verbeteringen van verbetering
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: ed937c90bbc6875ee3d72f710d5ac11d4069cbb6
ms.sourcegitcommit: a8f3c633714e934f9ad026c3bc72157ed535dcfc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/29/2020
ms.locfileid: "49738041"
---
# <a name="track-your-microsoft-secure-score-history-and-meet-goals"></a>De geschiedenis van uw Microsoft Secure Score bijhouden en bereiken

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[Secure Score van Microsoft](microsoft-secure-score.md) is een afmeting van de beveiligings Posture van een organisatie, met een hoger nummer voor het uitvoeren van extra verbeterings acties. U vindt het https://security.microsoft.com/securescore in [microsoft 365 Beveiligingscentrum](overview-security-center.md).

## <a name="gain-insights-into-activity-that-has-affected-your-score"></a>Inzicht krijgen in activiteiten die van invloed zijn op uw Score

Bekijk een grafiek van de Score van uw organisatie in de loop van de tijd op het tabblad **geschiedenis** .

Onder de grafiek bevindt zich een lijst met alle acties die zijn gemaakt in het geselecteerde tijdsbereik en de bijbehorende kenmerken, zoals de resultaten van de uitkomst, en de categorie. U kunt een datumbereik en de categorie filteren op categorie aanpassen.

![Activiteitsgeschiedenis](../../media/secure-score/secure-score-history-activity.png)

Als u de actie voor verbetering van een activiteit selecteert, wordt de actie flyout voor de volledige verbetering weergegeven.

Als u alle geschiedenis voor de specifieke actie voor verbetering wilt bekijken, selecteert u de koppeling geschiedenis in het vervolgmenu.

![Geschiedenis van verbeterings actie](../../media/secure-score/secure-score-history-flyout.png)

## <a name="discover-trends-and-set-goals"></a>Trends ontdekken en doelstellingen instellen

In het tabblad **statistieken & trends** zijn er verschillende grafieken en grafieken waarmee u inzicht kunt krijgen in trends en doelstellingen kunt instellen. U kunt het datumbereik voor de hele pagina met visualisaties instellen. De visualisaties zijn:

* **De beveiligde Score zone** , aangepast op basis van de doelstellingen en definities van uw organisatie
* **Regressie trend** : een tijdlijn van punten met regressed vanwege configuratie-, gebruikers-of apparaat-wijzigingen.  
* **Vergelijkings trend** -hoe de Secure Score van uw organisatie vergelijkt met de verschillende tijd. In deze weergave kunt u lijnen opnemen die het gemiddelde van de score voor bedrijven met een vergelijkbaar aantal gelijke stoelen en een aangepaste vergelijkings weergave kunnen instellen.
* **Trend van risico acceptatie** -tijdlijn met verbeterings acties gemarkeerd als risico geaccepteerd.
* **Wijzigingen van scores** : het aantal bereikte punten, punten regressed en wijzigingen in uw score in het opgegeven datumbereik.

### <a name="compare-your-score-to-organizations-like-yours"></a>Uw score vergelijken met organisaties zoals u

Er zijn twee locaties om te zien hoe uw score wordt vergeleken met organisaties die vergelijkbaar zijn met u. U kunt in beide grafieken de optie **vergelijkingen beheren** selecteren om de gegevens van uw organisatie weer te geven en te bewerken. U kunt ook een aangepaste vergelijking maken op basis van sector, organisatie formaat, licenties en regio's.

#### <a name="comparison-bar-chart"></a>Vergelijkings balk diagram

De vergelijkings balk grafiek is het tabblad **overzicht** . Plaats de muisaanwijzer op de grafiek om de score en de verkoopkans weer te geven. De vergelijkingsgegevens zijn geanonimiseerde, zodat we niet precies weten welke andere tenants deelnemen aan de mix.

![Staafdiagram met de scores van vergelijkbare organisatie](../../media/secure-score/secure-score-comparison-bar.png)

- **Organisaties zoals uw** eigen: een gemiddelde score van andere tenants (mits er minstens vijf of meer tenants zijn om te vergelijken) die voldoen aan de volgende criteria:
    1. Dezelfde bedrijfstak
    2. Hetzelfde formaat van organisatie
    3. Alle regio's
    4. Gebruikte Microsoft-producten zijn 80% vergelijkbaar
    5. Verkoopkans (maximale score die kan worden behaald door de huidige licentie) binnen een 20% van de Tenant

- **Aangepaste vergelijking**: u moet deze optie instellen door **vergelijking beheren** op basis van de volgende criteria te selecteren:
    1. Geselecteerde bedrijfstak ('s)
    2. Geselecteerd formaat (en) van de organisatie
    3. Geselecteerde regio ('s)
    4. Geselecteerde licentie (s)
    5. Gebruikte Microsoft-producten zijn 80% vergelijkbaar
    6. Verkoopkans (maximale score die kan worden behaald door de huidige licentie) binnen een 20% van de Tenant

Als u een aangepaste selectie hebt gemaakt, maar de resultaten kleiner zijn dan vijf andere tenants waarmee we kunnen vergelijken, ziet u ' niet beschikbaar vanwege beperkte gegevens '.

#### <a name="comparison-trend"></a>Vergelijkings trend

Bekijk op het tabblad **gegevens & trends** de manier waarop de Secure Score van uw organisatie vergelijkt met anderen.

![Lijngrafiek van vergelijkbare organisatie scores gedurende een bepaalde periode](../../media/secure-score/secure-score-comparison-trend.png)

## <a name="we-want-to-hear-from-you"></a>Wij horen graag van u

Als u problemen ondervindt, kunt u het ons laten weten dat u de community [beveiliging, Privacy & naleving](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) . We volgen de community en bieden hulp.

## <a name="related-resources"></a>Verwante informatiebronnen

- [Overzicht van Microsoft Secure Score](microsoft-secure-score.md)
- [Uw beveiligingspositie vaststellen](microsoft-secure-score-improvement-actions.md)
- [Binnenkort beschikbaar](microsoft-secure-score-whats-coming.md)
- [Wat is er nieuw](microsoft-secure-score-whats-new.md)
