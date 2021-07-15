---
title: Aan de slag met zichtbaarheid en inzichten
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Aan de slag met zichtbaarheid en inzichten.
ms.openlocfilehash: 93be3557c32345e81c7126b669ead8edf8ebac21
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430478"
---
# <a name="get-started-with-visibility-and-insights"></a>Aan de slag met zichtbaarheid en inzichten

>*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](https://aka.ms/ComplianceSD).*

De eerste plaats om te beginnen is het app-governance-dashboard op [https://aka.ms/appgovernance](https://aka.ms/appgovernance). Merk op dat het aanmeldingsaccount één van [deze app-governancebeheerdersrollen](app-governance-get-started.md#administrator-roles) moet hebben om app-governancegegevens weer te geven.

![De overzichtpagina van de app-governance in het Microsoft 365-compliancecentrum](..\media\manage-app-protection-governance\mapg-cc-overview.png)

Je kan ook toegang krijgen tot het app-governance-dashboard vanuit **Microsoft 365-beheercentrum > Microsoft 365-compliance > App-governance > Overzichtspagina**.

## <a name="whats-available-on-the-dashboard"></a>Wat is er beschikbaar op het dashboard

Het dashboard bevat een samenvatting van de componenten van het Microsoft 365-app-ecosysteem in de tenant:

- **Tenant-samenvatting**: Het aantal categorieën voor belangrijke apps en waarschuwingen.
- **Waarschuwingen voor detectie en beleid**: De meest recente actieve waarschuwingen in de tenant
- **Toegang tot gegevens en resources**: Samengestelde toegang van toepassings-API en algemeen gebruik van belangrijkste resources in de tenant. Muis over elke maandkolom in de grafiek om de overeenkomende datum weer te geven.
- **Verbeter de bescherming en het beheer van je app**: Aanbevolen acties zoals het maken van een beleid voor gebruik en machtigingen voor de app.
- **Belangrijkste apps per categorie**: De belangrijkste apps gesorteerd op de volgende categorieën:
  
  - **Alle categorieën**: Sorteren op alle beschikbare categorieën.
  - **Hoge bevoegdheid**: Hoge bevoegdheid is een intern bepaalde categorie gebaseerd op machine learning van het platform en signalen.
  - **Te veel machtigingen**: Wanneer app-governance telemetrie ontvangt die aangeeft dat een machtiging is toegekend aan een toepassing en die niet is gebruikt in de afgelopen 90 dagen, heeft de toepassing te veel machtigingen. App-governance moet ten minste 90 dagen actief zijn om te bepalen of een app te veel machtigingen heeft.  
  - **Niet-geverifieerd**: Toepassingen die geen [uitgeverscertificering](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview) hebben gekregen worden beschouwd als niet-geverifieerd.
  - **Alleen app**: [Toegangsmachtigingen](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#permission-types) die door apps gebruikt worden die zonder een aanwezige aangemelde gebruiker kunnen uitgevoerd worden. Apps met machtigingen voor toegang tot gegevens in de hele tenant zijn een potentieel hoog risico.
  - **Nieuwe apps**: Nieuwe Microsoft 365-apps die in de afgelopen zeven dagen geregistreerd werden.  

## <a name="next-step"></a>Volgende stap

[Gedetailleerde inzichten op voor een specifieke app ophalen](app-governance-visibility-insights-view-apps.md).
