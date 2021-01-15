---
title: Aan de slag met simulatie van aanvals oefeningen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe u simulatie training kunt gebruiken voor het uitvoeren van simulaties voor phishing en wachtwoorden in hun Microsoft 365 E5 of Microsoft Defender for Office 365-abonnement 2-organisaties.
ms.openlocfilehash: 9d97816edf7d59c002658fc8bb3f39e72dbc2430
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/15/2021
ms.locfileid: "49871242"
---
# <a name="get-started-using-attack-simulation-training"></a>Aan de slag met simulatie van aanvals oefeningen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Als uw organisatie gebruikmaakt van Microsoft 365 E5 of Microsoft Defender for Office 365 (abonnement 2), waaronder het [onderzoek en de antwoord mogelijkheden](office-365-ti.md)van de organisatie, kunt u simulatie training voor hacken gebruiken in het Microsoft-Beveiligingscentrum voor het uitvoeren van realistische aanvalsscenario's in uw organisatie. Met de gesimuleerde aanvallen kunt u gebruikers kwetsbaar maken en kwetsbaar maken voor een echte aanval met uw onderste regel. Lees dit artikel voor meer informatie.

> [!NOTE]
> Simulatie training aanval vervangt de oude ervaring van een aanval van de versie van Office Simulator die wordt beschreven in [aanvals Simulator in Microsoft Defender voor Office 365](attack-simulator.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Als u het Microsoft Beveiligingscentrum wilt openen, gaat u naar <https://security.microsoft.com/> . Simulatie voor simulatie van aanval via **e-mail en samenwerking** is beschikbaar op een \> **simulatie training** voor e-mail en samenwerking. Als u direct naar een aanvals training wilt gaan, opent u <https://security.microsoft.com/attacksimulator> .

- Zie voor meer informatie over de beschikbaarheid van een aanvals training in diverse Microsoft 365-abonnementen de [servicebeschrijving van Microsoft Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

- U moet beschikken over machtigingen voor de beveiliging & nalevings centrum of Azure Active Directory voordat u de procedures in dit artikel kunt uitvoeren. Specifiek moet u lid zijn van **Organisatiebeheer**, **beveiligingsbeheerder** of een van de volgende rollen:
  - **Kwaadwillende Simulator-beheerders**: alle aspecten van simulaties van aanvals campagnes maken en beheren.
  - **Schrijvers** van een aanval van de nettolading van een aanval: een aanval maken die een beheerder later kan initiëren.

  Zie voor meer informatie [machtigingen in het artikel over naleving van beveiligings &](permissions-in-the-security-and-compliance-center.md) of [over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

- Er zijn geen bijbehorende PowerShell-cmdlets voor simulaties van aanvals oefeningen.

- Simulatie van aanval en opleidingen met betrekking tot de training voor Microsoft 365-Services met andere klantgegevens. Zie [Microsoft 365-gegevenslocaties](/microsoft-365/enterprise/o365-data-locations)voor meer informatie. Simulatie van aanval is op dit moment niet beschikbaar in de volgende regio's: SGP, noch, UAE, ZAF, GER, BRA en CHE.

## <a name="simulations"></a>Simulaties

*Phishing* is een algemene term voor e-mail aanvallen waarbij gevoelige informatie wordt gestolen voor berichten die afkomstig lijken te zijn van legitieme of vertrouwde afzenders. *Phishing* is een onderdeel van een subset van technieken die we als _Social Engineering_ classificeren.

In het geval van een aanval met simulatie zijn er meerdere soorten technieken voor Social engineering.

- **Credential oogst**: een aanvaller verzendt een bericht dat de ontvanger een URL bevat. Wanneer de geadresseerde op de URL klikt, wordt deze doorgestuurd naar een website die meestal een dialoogvenster wordt weergegeven waarin de gebruiker om de gebruikersnaam en wachtwoord vraagt. Meestal is de doelpagina bedoeld om een bekende website aan te geven om het vertrouwen van de gebruiker te maken.

- **Bijlage met schadelijke software**: een aanvaller verzendt de geadresseerde een bericht dat een bijlage bevat. Wanneer de geadresseerde de bijlage opent, wordt willekeurige code (bijvoorbeeld een macro) uitgevoerd op het apparaat van de gebruiker, zodat de aanvaller een extra code of verdere entrench zichzelf kan installeren.

- **Koppeling in bijlage**: dit is een Hybrid van een Credential oogst. Een aanvaller verzendt de geadresseerde een bericht met een URL in een bijlage. Wanneer de geadresseerde de bijlage opent en op de URL klikt, wordt deze doorgestuurd naar een website die normaalgesproken een dialoogvenster toont waarin de gebruiker om de gebruikersnaam en wachtwoord vraagt. Meestal is de doelpagina bedoeld om een bekende website aan te geven om het vertrouwen van de gebruiker te maken.

- **Koppeling naar malware**: een aanvaller verzendt de geadresseerde een bericht met een koppeling naar een bijlage op een bekende bestandsshare site (bijvoorbeeld SharePoint Online of Dropbox). Wanneer de geadresseerde op de URL klikt, wordt de bijlage geopend en willekeurige code (zoals een macro), op het apparaat van de gebruiker, zodat de aanvaller een extra code of verdere entrench zichzelf kan installeren.

- **Drive by-URL**: een aanvaller verzendt een e-mailbericht met een URL. Wanneer de geadresseerde op de URL klikt, wordt deze gezocht naar een website die wordt gebruikt om de achtergrond code uit te voeren. Met deze achtergrond code wordt geprobeerd informatie over de ontvanger te verzamelen of willekeurige code op hun apparaat te implementeren. Meestal is de bestemmingswebsite een bekende website met een ongeoorloofde of een kloon van een bekende website. Vertrouwd met de website helpt bij het overtuigen van de gebruiker dat de link veilig kan worden geklikt. Deze methode wordt ook wel een _aanval met bewaterings hole_ genoemd.

> [!NOTE]
> Controleer de beschikbaarheid van de gesimuleerde phishingwebsite in de ondersteunde webbrowsers voordat u de URL in een malafide campagne gebruikt. Hoewel we met veel URL-reputatie leveranciers werken om deze simulatie-Url's altijd toe te staan, hebben we niet altijd de volledige behoefte, zoals Google Safe Browse. De meeste leveranciers bieden richtlijnen waarmee u altijd specifieke Url's kunt toestaan (bijvoorbeeld <https://support.google.com/chrome/a/answer/7532419> ).

De Url's die worden gebruikt voor de simulatie van aanvals oefeningen, worden beschreven in de volgende lijst:

- <https://www.mcsharepoint.com>
- <https://www.attemplate.com>
- <https://www.doctricant.com>
- <https://www.mesharepoint.com>
- <https://www.officence.com>
- <https://www.officenced.com>
- <https://www.officences.com>
- <https://www.officentry.com>
- <https://www.officested.com>
- <https://www.prizegives.com>
- <https://www.prizemons.com>
- <https://www.prizewel.com>
- <https://www.prizewings.com>
- <https://www.shareholds.com>
- <https://www.sharepointen.com>
- <https://www.sharepointin.com>
- <https://www.sharepointle.com>
- <https://www.sharesbyte.com>
- <https://www.sharession.com>
- <https://www.sharestion.com>
- <https://www.templateau.com>
- <https://www.templatent.com>
- <https://www.templatern.com>
- <https://www.windocyte.com>

### <a name="create-a-simulation"></a>Een simulatie maken

Zie [een malafide aanval simuleren](attack-simulation-training.md)voor stapsgewijze instructies voor het maken en verzenden van een nieuwe simulatie.

### <a name="create-a-payload"></a>Een nettolading maken

Zie [een aangepaste nettolading maken voor simulatie van aanvals training](attack-simulation-training-payloads.md)voor stapsgewijze instructies voor het maken van een nettolading voor gebruik binnen een simulatie.

### <a name="gaining-insights"></a>Inzichten krijgen

Zie [inzichten maken via simulatie van aanval via een aanval](attack-simulation-training-insights.md)voor stapsgewijze instructies voor het maken van inzichten met rapporten.
