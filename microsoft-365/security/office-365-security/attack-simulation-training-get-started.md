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
description: Beheerders kunnen leren hoe ze training voor de aanvalssimulatie kunnen gebruiken om gesimuleerde phishing- en wachtwoordaanvallen uit te voeren in hun Microsoft 365 E5 of Microsoft Defender voor Office 365 Plan 2-organisaties.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ad86f77399cfa2a3a780d3fed7e483e3c11bc08d
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082898"
---
# <a name="get-started-using-attack-simulation-training"></a>Aan de slag met aanvalssimulatietraining

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op** [Microsoft Defender voor Office 365 abonnement 2](defender-for-office-365.md)

Als uw organisatie Microsoft 365 E5 of Microsoft Defender voor Office 365 Plan 2 heeft, inclusief mogelijkheden voor bedreigingsonderzoek en [antwoord,](office-365-ti.md)kunt u de training voor de aanvalssimulatie gebruiken in de Microsoft 365 Defender-portal om realistische aanvalsscenario's in uw organisatie uit te voeren. Deze gesimuleerde aanvallen kunnen u helpen bij het identificeren en vinden van kwetsbare gebruikers voordat een echte aanval van invloed is op uw bottom line. Lees dit artikel voor meer informatie.

> [!NOTE]
> Aanvalssimulatietraining vervangt de oude Attack Simulator v1-ervaring die wordt beschreven in [Attack Simulator in Microsoft Defender voor Office 365.](attack-simulator.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Ga naar <https://security.microsoft.com> als je de Microsoft 365 Defender-portal wilt openen. Training voor aanvalssimulaties is beschikbaar op **training voor e-mail en** \> **samenwerkingssimulaties** voor aanvallen. Als u rechtstreeks naar de training Aanvalssimulatie wilt gaan, opent u <https://security.microsoft.com/attacksimulator> .

- Zie Microsoft Defender voor Office 365 servicebeschrijving voor meer informatie over de beschikbaarheid van training voor attack-Microsoft 365 [verschillende abonnementen.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

- U moet machtigingen krijgen toegewezen in de Microsoft 365 Defender portal of in Azure Active Directory voordat u de procedures in dit artikel kunt uitvoeren. U moet lid zijn van **Organisatiebeheer,** **Beveiligingsbeheerder** of een van de volgende rollen:
  - **Aanvalssimulatorbeheerders:** maak en beheerd alle aspecten van aanvalssimulatiecampagnes.
  - **Attack Simulator Payload Authors:** Maak aanvalsladingen die een beheerder later kan starten.

  Zie Machtigingen [in de](permissions-microsoft-365-security-center.md) Microsoft 365 Defender portal of [Over beheerdersrollen voor meer informatie.](../../admin/add-users/about-admin-roles.md)

- Er zijn geen bijbehorende PowerShell-cmdlets voor de training voor de aanvalssimulatie.

- Aanvalssimulatie en trainingsgerelateerde gegevens worden opgeslagen met andere klantgegevens voor Microsoft 365 services. Zie voor meer informatie [Microsoft 365 gegevenslocaties.](../../enterprise/o365-data-locations.md) Aanvalssimulatie is beschikbaar in de volgende regio's: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN en KOR.

- Vanaf 15 juni 2021 is training voor aanvalssimulatie beschikbaar in GCC. Als uw organisatie Office 365 G5 GCC of Microsoft Defender voor Office 365 (plan 2) voor de overheid heeft, kunt u de simulatietraining Aanvallen gebruiken in de Microsoft 365 Defender-portal om realistische aanvalsscenario's in uw organisatie uit te voeren, zoals in dit artikel wordt beschreven. Training voor aanvalssimulaties is nog niet beschikbaar in GCC High- of DoD-omgevingen.

> [!NOTE]
> Training voor aanvalssimulatie biedt een subset van mogelijkheden voor E3-klanten als proefversie. Het proefabonnement bevat de mogelijkheid om een Credential Harvest-payload te gebruiken en de mogelijkheid om trainingservaringen 'ISA Phishing' of 'Mass Market Phishing' te selecteren. Er maken geen andere mogelijkheden deel uit van de proefversie van E3.

## <a name="simulations"></a>Simulaties

*Phishing* is een algemene term voor e-mailaanvallen die gevoelige informatie proberen te stelen in berichten die afkomstig lijken te zijn van legitieme of vertrouwde afzenders. *Phishing* maakt deel uit van een subset van technieken die we classificeren als _social engineering._

In de training voor de aanvalssimulatie zijn er meerdere typen technieken voor sociale techniek beschikbaar:

- **Referentieoogst:** een aanvaller stuurt de geadresseerde een bericht met een URL. Wanneer de geadresseerde op de URL klikt, wordt deze naar een website gestuurd waarin meestal een dialoogvenster wordt weergegeven waarin de gebruiker om zijn gebruikersnaam en wachtwoord wordt gevraagd. Meestal wordt de doelpagina als themed gebruikt om een bekende website te vertegenwoordigen om vertrouwen in de gebruiker op te bouwen.

- **Malwarebijlage:** een aanvaller stuurt de geadresseerde een bericht met een bijlage. Wanneer de geadresseerde de bijlage opent, wordt willekeurige code (bijvoorbeeld een macro) uitgevoerd op het apparaat van de gebruiker om de aanvaller te helpen extra code te installeren of zichzelf verder te verschansen.

- **Koppeling in bijlage:** Dit is een hybride referentieoogst. Een aanvaller stuurt de geadresseerde een bericht met een URL in een bijlage. Wanneer de geadresseerde de bijlage opent en op de URL klikt, wordt deze naar een website gestuurd waarin meestal een dialoogvenster wordt weergegeven waarin de gebruiker om zijn gebruikersnaam en wachtwoord wordt gevraagd. Meestal wordt de doelpagina als themed gebruikt om een bekende website te vertegenwoordigen om vertrouwen in de gebruiker op te bouwen.

- **Koppeling naar malware:** Een aanvaller stuurt de geadresseerde een bericht met een koppeling naar een bijlage op een bekende site voor het delen van bestanden (bijvoorbeeld SharePoint Online of Dropbox). Wanneer de geadresseerde op de URL klikt, wordt de bijlage geopend en wordt willekeurige code (bijvoorbeeld een macro) uitgevoerd op het apparaat van de gebruiker, om de aanvaller te helpen extra code te installeren of zichzelf verder te verschansen.

- **Drive-by-url:** Een aanvaller stuurt de geadresseerde een bericht met een URL. Wanneer de geadresseerde op de URL klikt, wordt deze naar een website geleid die probeert achtergrondcode uit te voeren. Met deze achtergrondcode wordt geprobeerd informatie over de ontvanger te verzamelen of willekeurige code op het apparaat te implementeren. Meestal is de doelwebsite een bekende website die is gecompromitteerd of een kloon van een bekende website. Vertrouwdheid met de website helpt de gebruiker ervan te overtuigen dat de koppeling veilig is om op te klikken. Deze techniek wordt ook wel een _watergat-aanval genoemd._

> [!NOTE]
> Controleer de beschikbaarheid van de gesimuleerde phishing-URL in uw ondersteunde webbrowsers voordat u de URL gebruikt in een phishingcampagne. Hoewel we met veel URL-reputatieleveranciers werken om deze url's altijd toe te staan, hebben we niet altijd volledige dekking (bijvoorbeeld Google Safe Browsen). De meeste leveranciers bieden richtlijnen waarmee u altijd specifieke URL's kunt toestaan <https://support.google.com/chrome/a/answer/7532419> (bijvoorbeeld).

De URL's die worden gebruikt door training voor de aanvalssimulatie worden in de volgende lijst beschreven:

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

Zie Een phishing-aanval simuleren voor stapsgewijs instructies over het maken en verzenden van een nieuwe [simulatie.](attack-simulation-training.md)

### <a name="create-a-payload"></a>Een payload maken

Zie Een aangepaste payload maken voor de trainingstraining aanvalssimulatie voor stapsgewijs instructies over het maken van een payload voor gebruik in [een simulatie.](attack-simulation-training-payloads.md)

### <a name="gaining-insights"></a>Inzichten verkrijgen

Zie Inzichten verkrijgen via de trainingstraining Aanvalssimulatie voor [stapsgewijs](attack-simulation-training-insights.md)instructies over het verkrijgen van inzichten met rapportage.

> [!NOTE]
> Attack Simulator gebruikt Safe Koppelingen in Defender voor Office 365 om veilig klikgegevens bij te houden voor de URL in het payloadbericht  dat wordt verzonden naar geadresseerden van een phishingcampagne, zelfs als de instelling Gebruikersklikken niet bijhouden in het beleid voor Safe Koppelingen is ingeschakeld.
