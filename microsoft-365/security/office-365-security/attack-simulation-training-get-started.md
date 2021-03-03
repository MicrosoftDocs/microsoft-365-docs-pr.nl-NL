---
title: Aan de slag met aanvalssimulatietraining
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen meer informatie krijgen over het gebruik van de training voor de aanvalsaanvallen op de nabootsing van phishing en wachtwoordaanvallen in hun organisaties met Microsoft 365 E5 of Microsoft Defender voor Office 365 Plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a33c212f7d0fd6b0617a8059b03ac90de03fba16
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407471"
---
# <a name="get-started-using-attack-simulation-training"></a>Aan de slag met aanvalssimulatietraining

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Als uw organisatie beschikt over Microsoft 365 E5 of Microsoft Defender voor Office 365 Plan 2, waarin de mogelijkheden voor bedreigingen onderzoeken en antwoorden zijn [betrokken,](office-365-ti.md)kunt u de analysetraining voor aanvallen in het Microsoft Beveiligingscentrum gebruiken om realistische scenario's met aanvallen uit te voeren in uw organisatie. Deze gesimuleerde aanvallen kunnen u helpen om kwetsbaar gebruikers te identificeren en te vinden voordat een echte aanval uw onderlijn beïnvloedt. Lees dit artikel voor meer informatie.

> [!NOTE]
> Trainingstraining voor de aanval vervangt de oude Attack Simulator v1-ervaring die wordt beschreven in [Attack Simulator in Microsoft Defender voor Office 365.](attack-simulator.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Als u het Microsoft-beveiligingscentrum wilt openen, gaat u naar <https://security.microsoft.com/> . Training voor de aanvalstraining voor de aanval is beschikbaar op de training voor de **e-mail-** en \> **samenwerkingstraining voor de aanvals-aanval.** Als u rechtstreeks naar de training voor de aanvalsen wilt gaan, opent <https://security.microsoft.com/attacksimulator> u .

- Zie de servicebeschrijving van de Microsoft Defender voor [Office 365-service](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)voor meer informatie over de beschikbaarheid van de training voor de aanvalstraining voor verschillende Microsoft 365-abonnementen.

- U moet machtigingen toegewezen krijgen in het beveiligings- & compliancecentrum of in Azure Active Directory voordat u de procedures in dit artikel kunt uitvoeren. U moet lid zijn van **Organisatiebeheer,** Beveiligingsbeheerder of een van de volgende rollen:
  - **Administrators van de Attack Simulator:** alle aspecten van de aanvalscampagnes maken en beheren.
  - **Attack Simulator Payload Authors:** Maak nettoladingen voor aanvallen die een beheerder later kan starten.

  Zie Machtigingen in het [beveiligings-](permissions-in-the-security-and-compliance-center.md) en & of informatie over [beheerdersrollen voor meer informatie.](../../admin/add-users/about-admin-roles.md)

- Er zijn geen bijbehorende PowerShell-cmdlets voor de training voor de attack-training.

- Het analyseren van aanvallen en trainingsgerelateerde gegevens worden opgeslagen met andere klantgegevens voor Microsoft 365-services. Zie Microsoft [365-gegevenslocaties voor meer informatie.](../../enterprise/o365-data-locations.md) In de volgende regio's kan een aanval worden uitgevoerd: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN en KOR.

## <a name="simulations"></a>Vereenspelingen

*Phishing* is een algemene term voor e-mailaanvallen die proberen gevoelige informatie te stelen in berichten die afkomstig lijken te zijn van legitieme of vertrouwde afzenders. *Phishing* maakt deel uit van een subset van technieken die we classificeren als _social engineering._

In de training voor de aanvals-ulatie zijn meerdere soorten social engineering-technieken beschikbaar:

- **Referentiegegevens**: een aanvaller stuurt de ontvanger een bericht met een URL. Wanneer de geadresseerde op de URL klikt, wordt deze naar een website gestuurd waar meestal een dialoogvenster wordt weergegeven waarin de gebruiker wordt gevraagd om de gebruikersnaam en het wachtwoord. Meestal heeft de doelpagina een eigen site met een bekende naam om het vertrouwen in de gebruiker op te bouwen.

- **Malwarebijlage:** een aanvaller stuurt de ontvanger een bericht dat een bijlage bevat. Wanneer de ontvanger de bijlage opent, wordt er willekeurige code (bijvoorbeeld een macro) uitgevoerd op het apparaat van de gebruiker, om de aanvaller te helpen aanvullende code te installeren of zichzelf verder te beschermen.

- **Koppeling in bijlage:** Dit is een hybride voor het gebruik van referenties. Een aanvaller stuurt de ontvanger een bericht dat een URL in een bijlage bevat. Wanneer de geadresseerde de bijlage opent en op de URL klikt, wordt deze naar een website gestuurd waar meestal een dialoogvenster wordt weergegeven waarin de gebruiker wordt gevraagd om zijn gebruikersnaam en wachtwoord. Meestal heeft de doelpagina een eigen site met een bekende naam om het vertrouwen in de gebruiker op te bouwen.

- **Koppeling naar malware:** een aanvaller stuurt de ontvanger een bericht met een koppeling naar een bijlage op een bekende site voor het delen van bestanden (bijvoorbeeld SharePoint Online of Dropbox). Wanneer de ontvanger op de URL klikt, wordt de bijlage geopend en wordt er willekeurige code (bijvoorbeeld een macro) uitgevoerd op het apparaat van de gebruiker, om de aanvaller te helpen bij het installeren van extra code of om zichzelf verder te beschermen.

- **Drive-by-url:** een aanvaller stuurt de ontvanger een bericht dat een URL bevat. Wanneer de geadresseerde op de URL klikt, wordt deze naar een website geleid die achtergrondcode probeert uit te voeren. Met deze achtergrondcode wordt geprobeerd informatie over de ontvanger te verzamelen of willekeurige code op het apparaat te implementeren. Meestal is de doelwebsite een bekende website die is gekloond of een kloon van een bekende website. Als u bekend bent met de website, zorgt u ervoor dat de gebruiker ervan op de koppeling klikt. Deze techniek wordt ook wel een _gat-aanval met water genoemd._

> [!NOTE]
> Controleer de beschikbaarheid van de gesimuleerde phishing-URL in de ondersteunde webbrowsers voordat u de URL gebruikt in een phishing-campagne. Hoewel we met veel leveranciers van URL-reputaties werken om deze url's altijd toe te staan, hebben we niet altijd volledige dekking (bijvoorbeeld Veilig browsen van Google). De meeste leveranciers bieden richtlijnen waarmee u altijd specifieke URL's (bijvoorbeeld) kunt <https://support.google.com/chrome/a/answer/7532419> toestaan.

In de volgende lijst worden de URL's beschreven die worden gebruikt bij de training voor de aanvalstraining voor de aanvallen:

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

### <a name="create-a-simulation"></a>Eenulatie maken

Zie Een phishing-aanval simuleren voor stapsgewijse [instructies](attack-simulation-training.md)over het maken en verzenden van een nieuwe ulatie.

### <a name="create-a-payload"></a>Een nettolading maken

Zie Een aangepaste nettolading maken voor de attack-training voor stapsgewijre [instructies](attack-simulation-training-payloads.md)over het maken van een nettolading voor gebruik in eenulatie.

### <a name="gaining-insights"></a>Inzichten verkrijgen

Zie Inzichten krijgen via de trainingstraining voor de aanvalstraining voor stapsgewijse instructies over hoe u inzichten kunt verkrijgen met [rapporten.](attack-simulation-training-insights.md)
