---
title: Microsoft Productivityity-privacy
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ROBOTS: NOINDEX, NOFOLLOW
description: Hoe de privacy van de productiviteits score wordt beschermd.
ms.openlocfilehash: 799d532ca1f0abd5fa6234052d4875a79d629601
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/26/2020
ms.locfileid: "48287246"
---
# <a name="privacy-controls-for-productivity-score"></a>Privacy-instellingen voor de productiviteits Score

Met productiviteits Score kunnen organisaties transformeren hoe werk wordt gedaan met inzichten over de manier waarop mensen Microsoft 365 gebruiken en de technologie ervaring die deze ondersteunen. De Score weerspiegelt uw organisatie&#39;de prestaties van werknemers en technologie ervaring en vergelijkt uw score met organisaties als uw eigen. Ga voor meer informatie naar het onderwerp [overzicht van de productiviteits Score](productivity-score.md) .

Uw privacy is belangrijk voor ons en u kunt [hier](https://privacy.microsoft.com/privacystatement)de privacyverklaring van Microsoft bekijken. Bij een goede productiviteit is er sprake van cruciale informatie die we bieden over de werking van personen in uw organisatie. Daarom streven we er ook van te zorgen dat de gegevens op een duidelijke manier kunnen worden gewijzigd, maar niet in de door u gewenste vertrouwen in ons.

We bieden de volgende besturingselementen waarmee u veilig gegevens kunt afhandelen:

- Flexibele beheerdersrollen om te bepalen wie de informatie in de productiviteits Score kan zien.
- Anonimiseren van de metrieken van gebruikersniveaus.
- Mogelijkheid om te profiteren van de ervaring van een werknemer.

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>Flexibele beheerdersrollen om te bepalen wie de informatie in de productiviteits Score kan zien

Als u de volledige productiviteits ervaring met een beheerdersrol wilt bekijken, waaronder inzichten op tenantniveau en Details per gebruikersniveau, moet u een van de volgende rollen maken:

- Algemene beheerder
- Exchange-beheerders
- SharePoint-beheerder
- Skype voor Bedrijven-beheerder
- Teams-beheerder
- Algemene lezer
- Rapporten lezer

Als u personen wilt uitnodigen die verantwoordelijk zijn voor het wijzigen van het beheer en de aanneming, maar niet IT-beheerders de ervaring willen bieden, en ze toegang hebben tot de volledige ervaring, waaronder inzichten op tenantniveau en Details per gebruikersniveau, kunt u ze de rol van rapporten aangeven.

In de ervaring voor werknemers bieden we gegevens op het niveau van de gegevens op het gebruikersniveau in de rasterindeling voor elke detailpagina van elke categorie. Aangezien dit detailniveau niet geschikt is voor alle potentiële bezoekers van de productiviteits Score, hebben we een aangepaste rol gemaakt in azure AD-Gebruiksoverzicht rapporten van de lezer, zodat u toegang hebt tot een groter aantal bezoekers binnen uw organisatie zodat alleen de samengestelde metrische gegevens en geen gegevens per niveau binnen de ervaring kunnen worden weergegeven.

:::image type="content" source="../../media/communicationspage.jpg" alt-text="Communicatie pagina in productiviteits rapporten.":::

## <a name="anonymization-of-user-level-metrics"></a>Anonimiseren van metrieke gegevens van gebruikersniveau

U moet een globale beheerder zijn als u de gegevens die worden verzameld voor alle rapporten anoniem wilt maken. Hiermee kunt u identificeerbare informatie zoals namen van gebruikers, groepen en sites verbergen in alle rapporten, waaronder productiviteits Score en Microsoft 365-gebruik.

1. Ga in het Beheercentrum naar instellingen voor **Settings**   >   **organisatie** en kies op het tabblad **Services** de optie **rapporten**.
2. Selecteer  **rapporten** en kies vervolgens voor het  **weergeven van anonieme id's voor namen van gebruikers, groepen en sites in de rapporten voor de productiviteits Score en de gebruiksrapporten**. Deze instelling wordt zowel toegepast op de gebruiksrapporten als voor de sjabloon-app.
3. Selecteer  **Save Changes**.

:::image type="content" source="../../media/orgsettings_anonymous.jpg" alt-text="Gebruikers informatie anoniem maken voor rapporten.":::

## <a name="capability-to-opt-out-of-employee-experience"></a>Mogelijkheid om u af te melden voor de ervaring van een werknemer

Ook bieden we de mogelijkheid deel te nemen aan het gebied voor werknemers in de productiviteits Score tegen algemene beschikbaarheid. Als u deze instelling inschakelt, kan iedereen van uw organisatie deze metrieken niet zien en uw organisatie verwijderen uit elke berekening met categorieën van communicatie, vergaderingen, teamwork, samenwerken aan inhoud en mobiliteit.

1. Ga in het Beheercentrum naar instellingen voor **Settings**   >   **organisatie** en kies op het tabblad **Services** de optie **rapporten**.
2. Selecteer  **rapporten** en schakel vervolgens het selectievakje in om  **uw organisatie te delen&#39;en uw organisatie met productiviteits informatie over werknemers ervaring met productiviteit**. Als u meer wilt weten over het wijzigen van de instellingen voor het delen van gegevens voor eindpunten in de intune Configuration Manager, klikt u op meer **informatie**.
3. Selecteer  **Save Changes**.

:::image type="content" source="../../media/orgsettingspageoptout.jpg" alt-text="Pagina instellingen voor organisatie waar u zich kunt afmelden voor de werknemers ervaring.":::