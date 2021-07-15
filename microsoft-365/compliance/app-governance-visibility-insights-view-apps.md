---
title: Uw apps weergeven
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
description: Uw apps weergeven.
ms.openlocfilehash: 48a1a2140a3b59091796ca013a12eeefb8a284b9
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420064"
---
# <a name="view-your-apps"></a>Uw apps weergeven

>*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](https://aka.ms/ComplianceSD).*

Met Microsoft-app-beheer kunt u snel uitgebreide inzichten verkrijgen in de Microsoft 365-apps in uw tenant. U kunt bijvoorbeeld het volgende zien:

- Een lijst met OAuth-apps in de tenant die gebruikmaken van de Microsoft Graph API, samen met relevante app-metagegevens en gebruiksgegevens.
- App-details met diepere inzichten en informatie door een app in de lijst te selecteren.

## <a name="getting-a-list-of-all-the-apps-in-your-tenant"></a>Een lijst met alle apps in uw tenant ophalen

Voor een overzicht van apps in uw tenant gaat u naar **Microsoft 365-compliancecentrum > App-beveiliging en beheer > Apps**.

![De samenvattingspagina van de MAPG-app in het Microsoft 365-compliancecentrum](..\media\manage-app-protection-governance\mapg-cc-apps.png)

>[!Note]
> Uw aanmeldingsaccount moet een van [deze rollen](app-governance-get-started.md#administrator-roles) hebben om app-beheergegevens weer te geven.
>

U ziet een lijst met apps en deze informatie:

- App-naam
- Publisher
- App-certificering

  Geeft aan of de app compatibel is met Microsoft-technologieën, voldoet aan de aanbevolen procedures voor cloud-app-beveiliging en wordt ondersteund door Microsoft.

- Laatst gewijzigd

  Geeft de datum weer waarop app-beheer in de client is geïnstalleerd als die datum recenter is dan de datum waarop de app voor het laatst is gewijzigd.

- Installatiedatum
- Bevoegdhedenniveau
- Aantal gebruikers
- Toegang tot gegevens

  De som van de gegevensupload en -download in uw tenant van deze app tijdens de laatste dag, samen met de verandering ten opzichte van de dag ervoor.

App-beheer sorteert de lijst met apps standaard op **app-naam**. Selecteer de kenmerknaam om de lijst op een ander app-kenmerk te sorteren.

U kunt ook **Zoeken** selecteren om op naam naar een app te zoeken.

## <a name="getting-detailed-information-on-an-app"></a>Gedetailleerde informatie over een app ophalen

Ga voor gedetailleerde informatie over een specifieke app in uw tenant naar de pagina **Microsoft 365-compliancecentrum > App-beheer > Apps-pagina > *app-naam***.

![Het detailvenster voor app-beheer in het Microsoft 365-compliancecentrum](..\media\manage-app-protection-governance\mapg-cc-apps-app.png)

Het detailvenster van de app bevat aanvullende informatie op deze tabbladen:

| Tabbladnaam | Omschrijving |
|:-------|:-----|
| Details | Bekijk aanvullende gegevens over de app, zoals de datum waarop de eerste toestemming is verleend en de app-id. Als u de eigenschappen van de app wilt zien zoals geregistreerd in Azure AD, selecteert u **App weergeven in Azure AD**. |
| Gebruik | Bekijk de gegevens waartoe de app toegang heeft in de tenant, plot het gegevensgebruik en toon het gebruik door de top \<x>-gebruikers en gebruikers met [prioriteitsaccounts](/microsoft-365/admin/setup/priority-accounts). |
| Gebruikers | Bekijk een lijst met gebruikers die de app gebruiken, of ze een prioriteitsaccount zijn en de hoeveelheid gegevens die is gedownload en geüpload. |
| Machtigingen | Bekijk een samenvatting van de machtigingen die zijn verleend aan en gebruikt door de app en de lijst met specifieke machtigingen. Zie de verwijzing naar [Microsoft Graph-machtigingen](/graph/permissions-reference) voor meer informatie. |
|||

Voor een ingeschakelde app is er ook een besturingselement **App uitschakelen** om het gebruik van de geselecteerde app uit te schakelen en een besturingselement **App inschakelen** om het gebruik van de uitgeschakelde app in te schakelen. Deze acties vereisen deze [beheerdersrollen](app-governance-get-started.md#administrator-roles):

- Beheerder voor naleving
- Globale beheerder
- Beveiligingsbeheerder
- Beveiligingsoperator

## <a name="next-step"></a>Volgende stap

[Bepaal uw algehele app-compliancehouding](app-governance-visibility-insights-compliance-posture.md).
