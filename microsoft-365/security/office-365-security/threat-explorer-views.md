---
title: Weergaven in Bedreigingsverkenner en realtime detecties
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 05/15/2020
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Meer informatie over het gebruik van Bedreigingsverkenner en het rapport detecties in realtime om bedreigingen te onderzoeken en te beantwoorden in het beveiligings- & compliancecentrum.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b00b78432a34ec982208586f2fe19c1588354293
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406478"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a>Weergaven in Bedreigingsverkenner en realtime detecties

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)


![Bedreigingsverkenner](../../media/ThreatExplorerFirstOpened.png)

[Bedreigingsverkenner](threat-explorer.md) (en het rapport realtime detecties) is een krachtig, bijna realtime hulpmiddel waarmee teams met beveiligingsbewerkingen bedreigingen kunnen onderzoeken en reageren op bedreigingen in het beveiligings- & compliancecentrum. Explorer (en het rapport realtime detecties) geeft informatie weer over verdachte malware en phish in e-mail en bestanden in Office 365, evenals andere beveiligingsrisico's en risico's voor uw organisatie.

- Als u [Microsoft Defender voor Office 365-abonnement](office-365-atp.md) 2 hebt, hebt u Explorer.
- Als u Microsoft Defender voor Office 365-abonnement 1 hebt, hebt u detecties in realtime.

Wanneer u Explorer (of het rapport realtime detecties) voor het eerst opent, ziet u in de standaardweergave malwaredetecties voor e-mail van de afgelopen zeven dagen. Dit rapport kan ook Microsoft Defender voor Office 365-detecties tonen, zoals schadelijke URL's gedetecteerd door veilige koppelingen [en](atp-safe-links.md)schadelijke bestanden gedetecteerd door [veilige bijlagen.](atp-safe-attachments.md) Dit rapport kan worden gewijzigd om gegevens voor de afgelopen 30 dagen weer te geven (met een betaald abonnement op Microsoft Defender voor Office 365 P2). Proefabonnementen bevatten alleen gegevens van de afgelopen zeven dagen.

****

|Abonnement|Hulpprogramma|Dagen van gegevens|
|---|---|---|
|Proefversie van Microsoft Defender voor Office 365 P1|Detecties in realtime|7|
|Betaalde Microsoft Defender voor Office 365 P1|Detecties in realtime|30|
|Betaalde testversie van Defender voor Office 365 P1 met Microsoft Defender voor Office 365 P2|Bedreigingsverkenner|7|
|Proefversie van Microsoft Defender voor Office 365 P2|Bedreigingsverkenner|7|
|Betaalde Microsoft Defender voor Office 365 P2|Bedreigingsverkenner|30|
|

> [!NOTE]
> De bewaar- en zoeklimiet voor proeften tenants wordt binnenkort uitgebreid van 7 naar 30 dagen. Deze wijziging wordt bijgehouden als onderdeel van roadmap-item 70544 en is momenteel in een fase van implementatie.

Gebruik **het** menu Beeld om te wijzigen welke informatie wordt weergegeven. Met knopinfo kunt u bepalen welke weergave u wilt gebruiken.

![Menu Beeld van Bedreigingsverkenner](../../media/ThreatExplorerViewMenu.png)

Nadat u een weergave hebt geselecteerd, kunt u filters toepassen en query's instellen voor verdere analyse. De volgende secties bieden een kort overzicht van de verschillende weergaven die beschikbaar zijn in Verkenner (of realtime detecties).

## <a name="email--malware"></a>E-> Malware

Als u dit rapport wilt bekijken, kiest u In Verkenner (of realtime detecties) De optie **E-mailmalware** \>  \> **weergeven.** Deze weergave toont informatie over e-mailberichten die zijn geïdentificeerd als malware.

![Gegevens weergeven over e-mail die is geïdentificeerd als malware](../../media/ExplorerEmailMalwareMenu.png)

Klik **op Afzender** om de lijst met weergaveopties te openen. Gebruik deze lijst om gegevens weer te geven op afzender, geadresseerden, domein van afzender, onderwerp, detectietechnologie, beveiligingsstatus en meer.

Als u bijvoorbeeld wilt zien welke acties zijn ondernomen bij gedetecteerde e-mailberichten, kiest u **Beveiligingsstatus** in de lijst. Selecteer een optie en klik vervolgens op de knop Vernieuwen om dat filter toe te passen op het rapport.

![Opties voor Status van bedreigingsbeveiliging voor Bedreigingsverkenner](../../media/ThreatExplorerProtectionStatusOptions.png)

Bekijk onder de grafiek meer details over specifieke berichten. Wanneer u een item in de lijst selecteert, wordt er een uitvliegend deelvenster geopend, waar u meer informatie kunt vinden over het geselecteerde item.

![Bedreigingsverkenner met geopende flyout](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a>E-> Phish

Als u dit rapport wilt bekijken, kiest u  In Verkenner (of realtime detecties) \> **E-mail** \> **phish weergeven.** In deze weergave ziet u e-mailberichten die zijn geïdentificeerd als phishing-pogingen.

![Gegevens weergeven over e-mailberichten die zijn geïdentificeerd als phishingpogingen](../../media/ThreatExplorerEmailPhish.png)

Klik **op Afzender** om de lijst met weergaveopties te openen. Gebruik deze lijst om gegevens weer te geven per afzender, geadresseerden, afzenderdomein, AFZENDER-IP, URL-domein, klik op gemaakt en meer.

Als u bijvoorbeeld wilt zien welke acties zijn ondernomen wanneer personen op URL's klikken die zijn aangemerkt als phishing-pogingen, kiest u Klik op naam **in** de lijst, selecteert u een of meer opties en klikt u vervolgens op de knop Vernieuwen.

![Klik op opties voor de opties voor het phish-rapport](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

Onder de grafiek vindt u meer informatie over specifieke berichten, klikken op URL's, URL's en e-mail origin.

![URL's gedetecteerd als phish in e-mailberichten](../../media/ThreatExplorerEmailPhishURLs.png)

Wanneer u een item in de lijst selecteert, zoals een URL die is gedetecteerd, wordt een fly-outvenster geopend, waarin u meer informatie vindt over het geselecteerde item.

![Details over een gedetecteerde URL](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a>E> mail inzendingen

Als u dit rapport wilt bekijken, kiest u in Verkenner (of realtime detecties) **E-mailinzending** \>  \> **weergeven.** In deze weergave ziet u e-mail die gebruikers hebben gerapporteerd als ongewenste e-mail, geen ongewenste e-mail of phishing-e-mail.

![E-mailberichten gerapporteerd door gebruikers](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

Klik **op Afzender** om de lijst met weergaveopties te openen. Gebruik deze lijst om informatie weer te geven per afzender, geadresseerde, rapporttype (de mening van de gebruiker dat het e-mailbericht ongewenst is, geen ongewenste e-mail of phish), en meer.

Als u bijvoorbeeld informatie wilt weergeven over e-mailberichten die zijn gerapporteerd als phishing-pogingen, klikt u op Rapporttype afzender, selecteert u  Phish en klikt u vervolgens op \> de knop Vernieuwen. 

![Phish selected for Report Type filter](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

Onder de grafiek kunt u meer details bekijken over specifieke e-mailberichten, zoals de onderwerpregel, het IP-adres van de afzender, de gebruiker die het bericht heeft gerapporteerd als ongewenste e-mail, geen ongewenste e-mail of phish, en meer.

![Berichten die zijn gerapporteerd als phishing-pogingen](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

Selecteer een item in de lijst om aanvullende details weer te geven.

## <a name="email--all-email"></a>E-> e-mail verzenden

Als u dit rapport wilt bekijken, kiest u in Verkenner **E-mail** \>  \> **weergeven alle e-mail.** In deze weergaven ziet u een overzicht van alle e-mailactiviteiten, waaronder e-mail die is geïdentificeerd als schadelijk vanwege phishing of malware, en alle niet-schadelijke e-mail (normale e-mail, spam en bulkmail).

> [!NOTE]
> Als u een foutbericht krijgt met de tekst Te veel gegevens om weer te **geven,** voegt u een filter toe en beperkt u zo nodig het datumbereik dat u bekijkt.

Als u een filter wilt toepassen, kiest **u Afzender,** selecteert u een item in de lijst en klikt u op de knop Vernieuwen. In ons voorbeeld hebben we **Detectietechnologie als** filter gebruikt (er zijn verschillende opties beschikbaar). Gegevens weergeven per afzender, het domein van de afzender, geadresseerden, onderwerp, bestandsnaam van bijlage, malwarefamilie, beveiligingsstatus (acties die zijn ondernomen door de functies en beleidsregels voor bedreigingsbeveiliging in Office 365), detectietechnologie (hoe de malware is gedetecteerd) en meer.

![Gegevens over gedetecteerde e-mail weergeven met detectietechnologie](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

Bekijk onder de grafiek meer details over specifieke e-mailberichten, zoals onderwerpregel, geadresseerde, afzender, status, en dergelijke.

## <a name="content--malware"></a>Inhoud > Malware

Als u dit rapport wilt bekijken, kiest u In Verkenner (of realtime detecties) **Inhoudsmalware** \>  \> **weergeven.** In deze weergave ziet u bestanden die zijn geïdentificeerd als schadelijk door Microsoft Defender voor [Office 365 in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.](atp-for-spo-odb-and-teams.md)

Bekijk informatie via malwarefamilie, detectietechnologie (hoe de malware is gedetecteerd) en werkbelasting (OneDrive, SharePoint of Teams).

![Gegevens over gedetecteerde malware weergeven](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)

Bekijk onder de grafiek meer details over specifieke bestanden, zoals de bestandsnaam van de bijlage, de werkbelasting, de bestandsgrootte, wie het bestand het laatst heeft gewijzigd en meer.

## <a name="click-to-filter-capabilities"></a>Klik-en-filtermogelijkheden

Met Explorer (en realtime detecties) kunt u met één klik een filter toepassen. Als u op een item in de legenda klikt, wordt dat item een filter voor het rapport. Stel dat we naar de weergave Malware in Verkenner kijken:

![Ga naar \> BedreigingsbeheerVerkenner](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Als u **op ATP-detonatie** in deze grafiek klikt, ziet dit er als volgende uit:

![Verkenner gefilterd om alleen Defender voor office 365-detonatieresultaten weer te geven](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

In deze weergave kijken we nu naar gegevens over bestanden die zijn gedetoneerd met [veilige bijlagen.](atp-safe-attachments.md) Onder de grafiek ziet u details over specifieke e-mailberichten met bijlagen die door veilige bijlagen zijn gedetecteerd.

![Specifieke details over e-mailberichten met gedetecteerde bijlagen](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

Als u een of meer items selecteert, wordt het **menu** Acties geactiveerd. Het menu biedt verschillende keuzemogelijkheden waaruit u kunt kiezen voor de geselecteerde items.

![Als u een item selecteert, wordt het menu Acties geactiveerd](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

De mogelijkheid om te filteren met één klik en naar specifieke details te gaan, kan u veel tijd besparen bij het onderzoeken van bedreigingen.

## <a name="queries-and-filters"></a>Query's en filters

Explorer (evenals het rapport realtime detecties) beschikt over verschillende krachtige filters en querymogelijkheden waarmee u in detail kunt inzoomen, zoals topgebruikers, de belangrijkste malwarefamilies, detectietechnologie en meer. Elk type rapport biedt verschillende manieren om gegevens weer te geven en te verkennen.

> [!IMPORTANT]
> Gebruik geen jokertekens, zoals een sterretje of vraagteken, in de querybalk voor Verkenner (of realtime detecties). Wanneer u in  het veld Onderwerp zoekt naar e-mailberichten, zal Explorer (of realtime detecties) gedeeltelijke overeenkomende resultaten uitvoeren en resultaten opleveren die vergelijkbaar zijn met een zoekopdracht met een jokerteken.
