---
title: Weergaven in de bedreigings Verkenner en de real-time detectie
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 05/15/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
description: Lees meer over het gebruik van bedreigings Verkenner en het rapport realtime detectie om bedreigingen te onderzoeken en te beantwoorden in het Security &amp; compliance Center.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5064c3a250ba9e7dcf48d6bc360102b3ab4b8504
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656943"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a>Weergaven in de bedreigings Verkenner en de real-time detectie

![Bedreigingsverkenner](../../media/ThreatExplorerFirstOpened.png)

[Threat Explorer](threat-explorer.md) (en het rapport realtime detectie) is een krachtig hulpmiddel in het nabije realtime-hulpmiddel om beveiligingsactiviteiten teams te helpen bij het onderzoeken en beantwoorden van bedreigingen in het beveiligings &amp; centrum. Explorer (en het rapport realtime detectie) bevat informatie over verdachte malware en phishing in e-mail en in bestanden in Office 365, evenals andere beveiligingsrisico's en risico's voor uw organisatie.

- Als u [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP)-abonnement 2 hebt, dan hebt u Explorer.
- Als u Office 365 ATP, abonnement 1 hebt, hebt u realtime detecties.

Wanneer u het voor het eerst opent (of het rapport realtime-detectie), ziet u in de standaardweergave voor de afgelopen 7 dagen een malware van de malware van de e-mail. In dit rapport kunnen ook ATP-detectie worden weergegeven, zoals schadelijke Url's die zijn gedetecteerd door [veilige koppelingen](atp-safe-links.md), en schadelijke bestanden die zijn gedetecteerd door [veilige bijlagen](atp-safe-attachments.md). U kunt dit rapport wijzigen, zodat de gegevens van de afgelopen 30 dagen worden weergegeven (met een betaald ATP-abonnement). Met proefabonnementen worden alleen de afgelopen zeven dagen gegevens opgenomen.

****

|Leden|Netsh|Dagen van gegevens|
|---|---|---|
|ATP P1-proefabonnement|Realtime detectie|7,5|
|ATP P1 betaald|Realtime detectie|dertig|
|ATP P1 betaalde proefperiode van ATP|Bedreigingsverkenner|7,5|
|ATP-proefabonnement|Bedreigingsverkenner|7,5|
|ATP, betaald|Bedreigingsverkenner|dertig|
|

Gebruik het menu **beeld** om te wijzigen welke gegevens worden weergegeven. Met knopinfo kunt u bepalen welke weergave u wilt gebruiken.

![Het menu Beeld van bedreigings Verkenner](../../media/ThreatExplorerViewMenu.png)

Wanneer u een weergave hebt geselecteerd, kunt u filters toepassen en query's instellen om verdere analyses uit te voeren. In de volgende secties vindt u een beknopt overzicht van de verschillende weergaven die beschikbaar zijn in de Verkenner (of realtime gedetecteerde).

## <a name="email--malware"></a>E-mail > malware

Als u dit rapport wilt weergeven, kiest u in Verkenner (of realtime detectie) **View**de optie  >  **e-mail**  >  **malware**weergeven. In deze weergave ziet u informatie over e-mailberichten die zijn geïdentificeerd met malware.

![Gegevens voor e-mail identificeren als malware weergeven](../../media/ExplorerEmailMalwareMenu.png)

Klik op **afzender** om uw lijst met weergaveopties te openen. Gebruik deze lijst om gegevens weer te geven per afzender, geadresseerden, het domein van de afzender, het onderwerp, de detectietechnologie, de beschermingsstatus en nog veel meer.

Als u bijvoorbeeld wilt zien welke acties zijn uitgevoerd voor gedetecteerde e-mailberichten, kiest u de **beveiligingsstatus** in de lijst. Selecteer een optie en klik vervolgens op de knop Vernieuwen om het filter toe te passen op uw rapport.

![Status opties voor bedreigingsbeveiliging voor de bedreigings Verkenner](../../media/ThreatExplorerProtectionStatusOptions.png)

Bekijk de details van specifieke berichten onder de grafiek. Wanneer u een item in de lijst selecteert, wordt een deelvenster dat wordt weergegeven, waar u meer informatie kunt vinden over het item dat u hebt geselecteerd.

![Bedreigings Verkenner met flyout geopend](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a>E-mail > phishing

Als u dit rapport wilt weergeven, kiest u **View**  >  **e-mail**beantwoorde e-mail weergeven in Verkenner (of realtime-detectie)  >  **Phish**. In deze weergave ziet u e-mailberichten die zijn aangegeven als phishing-pogingen.

![Gegevens van e-mailberichten die zijn geïdentificeerd als phishing weergeven](../../media/ThreatExplorerEmailPhish.png)

Klik op **afzender** om uw lijst met weergaveopties te openen. Gebruik deze lijst om gegevens weer te geven op afzender, geadresseerden, het domein van de afzender, IP-adressen, URL Domain, verdict en meer.

Als u bijvoorbeeld wilt zien welke acties zijn uitgevoerd wanneer personen op Url's klikken die zijn geïdentificeerd als phishing, kiest u **verdict** in de lijst, selecteert u een of meer opties en klikt u op de knop Vernieuwen.

![Afbeelding van het dialoog formulier verdict](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

Onder de grafiek vindt u meer informatie over specifieke berichten, URL-klikken, Url's en e-mail oorsprong.

![Url's die zijn gedetecteerd als phishing in e-mailberichten](../../media/ThreatExplorerEmailPhishURLs.png)

Wanneer u een item in de lijst selecteert, zoals een URL die is gedetecteerd, wordt een deelvenster dat wordt weergegeven, waar u meer informatie kunt vinden over het item dat u hebt geselecteerd.

![Details van een gedetecteerde URL](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a>E-mail > ingediende items

Als u dit rapport wilt weergeven, kiest u in Verkenner (of realtime-detectie **View**) de optie  >  **e-mail**  >  **missies**weergeven. In deze weergave ziet u e-mail die gebruikers hebben gerapporteerd als ongewenste e-mail, geen ongewenste e-mail of phishing-e-mail.

![Door gebruikers gemelde e-mailberichten](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

Klik op **afzender** om uw lijst met weergaveopties te openen. In deze lijst kunt u informatie weergeven per afzender, geadresseerden, rapporttype (de vaststelling van de e-mail is ongewenste e-mail, geen ongewenste e-mail of phishing) en meer.

Als u bijvoorbeeld informatie wilt weergeven over e-mailberichten die zijn Gereedgemeld voor phishing, klikt u op **Sender**  >  **Rapporttype**afzender, selecteert u **phishing**en klikt u op de knop Vernieuwen.

![Phishing geselecteerd voor rapport type filter](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

Onder de grafiek vindt u meer informatie over specifieke e-mailberichten, zoals onderwerpregel, het IP-adres van de afzender, de gebruiker die het bericht heeft gemeld als ongewenst, geen ongewenste e-mail of phishing.

![Berichten die als phishing-pogingen zijn gerapporteerd](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

Selecteer een item in de lijst om meer details weer te geven.

## <a name="email--all-email"></a>E-mail > alle e-mail

Als u dit rapport wilt weergeven, kiest **View**u in Verkenner de optie  >  **e-mail**van  >  **alle e-mail**weergeven. Deze weergaven toont een weergave van een weergave van e-mail activiteiten, waaronder e-mail die als schadelijk is geïdentificeerd vanwege phishing of malware, en alle niet-schadelijke e-mail (normaal e-mail, spam en bulkmail).

> [!NOTE]
> Als er een foutbericht wordt weergegeven met de melding dat er **te veel gegevens worden weergegeven**, voegt u een filter toe en beperkt u zo nodig het datumbereik dat u bekijkt.

Als u een filter wilt toepassen, kiest u **afzender**, selecteert u een item in de lijst en klikt u op de knop Vernieuwen. In ons voorbeeld hebben we de **detectietechnologie** als een filter gebruikt (er zijn verschillende opties beschikbaar). Bekijk de informatie per afzender, het domein van de afzender, de geadresseerden, het onderwerp, de naam van de bijlage, de malware-serie, de beveiligingsstatus (acties die worden uitgevoerd door de functies en beleidsregels van bedreigingen in Office 365), de detectietechnologie (hoe de malware is gedetecteerd) en meer.

![Gegevens voor gedetecteerde e-mail weergeven in de detectietechnologie](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

Onder de grafiek vindt u meer informatie over specifieke e-mailberichten, zoals onderwerpregel, geadresseerde, afzender, status, enzovoort.

## <a name="content--malware"></a>Inhoud > malware

Als u dit rapport wilt weergeven, kiest u in Verkenner (of realtime detectie) de optie malware van inhoud **weergeven**  >  **Content**  >  **Malware**. In deze weergave worden de bestanden weergegeven die zijn geïdentificeerd als schadelijk door [Office 365 Advanced Threat Protection in SharePoint Online, OneDrive voor bedrijven en Microsoft teams](atp-for-spo-odb-and-teams.md).

Bekijk de informatie op malware-serie, detectietechnologie (hoe de malware is gedetecteerd) en werkbelasting (OneDrive, SharePoint of teams).

![Gegevens over gedetecteerde malware weergeven](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)

Onder de grafiek vindt u meer informatie over specifieke bestanden, zoals BIJLAGENAAM, werkbelasting, bestandsgrootte, wie het bestand het laatst heeft gewijzigd en meer.

## <a name="click-to-filter-capabilities"></a>Mogelijkheden voor klik-en-filter

Met Explorer (en realtime-detectie) kunt u een filter in een klik toepassen. Klik op een item in de legenda en dat item wordt een filter voor het rapport. Stel dat we de malware-weergave in Verkenner bekijken:

![Ga naar Threat Management \> Explorer](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

In **het** volgende diagram wordt een weergave als volgt in een weergave in een weergave weergegeven:

![Verkenner gefilterd zodat alleen de resultaten van de ATP-detonatie worden weergegeven](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

In deze weergave kijken we naar gegevens voor bestanden die zijn gedoofd in [Office 365 ATP voor veilige bijlagen](atp-safe-attachments.md). Onder de grafiek worden de details weergegeven van specifieke e-mailberichten met bijlagen die zijn gevonden met veilige ATP-bijlagen.

![Specifieke details van e-mailberichten met vastgestelde bijlagen](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

Als u een of meer items selecteert, wordt het menu **acties** geactiveerd, dat verschillende keuzes bevat waaruit u kunt kiezen voor het geselecteerde item (s).

![Wanneer u een item selecteert, wordt het menu acties geactiveerd.](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

De mogelijkheid om te filteren in een klik en naar specifieke gegevens te navigeren, kan veel tijd besparen bij het onderzoeken van bedreigingen.

## <a name="queries-and-filters"></a>Query's en filters

Verkenner (en het rapport realtime-detectie) bevat diverse krachtige filters en functies waarmee u gegevens kunt inzoomen, zoals beste gerichte gebruikers, belangrijkste families van malware, detectietechnologie en meer. Elk type rapport biedt diverse manieren om gegevens te bekijken en te verkennen.

> [!IMPORTANT]
> Gebruik geen jokertekens, zoals een sterretje of een vraagteken, in de query balk voor Explorer (of realtime detecteren). Wanneer u zoekt in het **veld onderwerp** voor e-mailberichten, worden in de Verkenner (of realtime-detectie) gedeeltelijke resultaten gegeven en wordt het resultaat van de functie jokertekens weergegeven.
