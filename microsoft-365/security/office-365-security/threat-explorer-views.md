---
title: Weergaven in Threat Explorer en realtime detecties
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
description: Meer informatie over het gebruik van Threat Explorer en het rapport realtime detecties om bedreigingen te onderzoeken en erop te reageren in het Security &amp; Compliance Center.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ae063cdcbd3d9b5d371e64513c90ff46503ec982
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819471"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a>Weergaven in Threat Explorer en realtime detecties

![Bedreigingsverkenner](../../media/ThreatExplorerFirstOpened.png)

[Threat Explorer](threat-explorer.md) (en het real-time detectierapport) is een krachtig, bijna realtime hulpmiddel om security operations-teams te helpen bij het onderzoeken en reageren op bedreigingen in het Security &amp; Compliance Center. Explorer (en het realtime detectierapport) geeft informatie weer over vermoedelijke malware en phish in e-mail en bestanden in Office 365, evenals andere beveiligingsbedreigingen en -risico's voor uw organisatie. 

- Als u AtP-abonnement [(Advanced Threat Protection) (Advanced Threat Protection)](office-365-atp.md) (ATP) hebt, hebt u Explorer.
- Als u Office 365 ATP-abonnement 1 hebt, hebt u realtime detecties.

Wanneer u Explorer voor het eerst opent (of het realtime detectierapport), toont de standaardweergave detecties van e-mailmalware van de afgelopen 7 dagen. Dit rapport kan ook ATP-detecties weergeven, zoals kwaadaardige URL's die zijn gedetecteerd door [veilige koppelingen](atp-safe-links.md)en schadelijke bestanden die zijn gedetecteerd door [veilige bijlagen.](atp-safe-attachments.md) Dit rapport kan worden gewijzigd om gegevens van de afgelopen 30 dagen weer te geven (met een betaald ATP P2-abonnement). Proefabonnementen bevatten alleen gegevens van de afgelopen zeven dagen.

|Abonnement  |Utility  |Dagen van gegevens  |
|---------|---------|---------|
|ATP P1-proefversie     | Realtime detectie        |   7      |
|ATP P1 betaald     |   Realtime detectie      |    30     |
|ATP P1 betaald testen ATP P2 trial     | Bedreigingsverkenner   |   7   |
|ATP P2-proefversie     |  Bedreigingsverkenner       |     7    |
|ATP P2 betaald     |     Bedreigingsverkenner    |  30       |

Gebruik het menu **Weergave** om te wijzigen welke informatie wordt weergegeven. Met tooltips u bepalen welke weergave u wilt gebruiken.
  
![Menu Weergave bedreigingverkenner](../../media/ThreatExplorerViewMenu.png)

Zodra u een weergave hebt geselecteerd, u filters toepassen en query's instellen om verdere analyses uit te voeren. De volgende secties geven een kort overzicht van de verschillende weergaven die beschikbaar zijn in Explorer (of real-time detecties).  

## <a name="email--malware"></a>E-mail > malware

Als u dit rapport wilt bekijken, kiest u **View**in Explorer (of realtime detecties)  >  **E-mailmalware**weergeven.  >  **Malware** Deze weergave toont informatie over e-mailberichten die zijn geïdentificeerd als malware.  

![Gegevens weergeven over e-mail die als malware is geïdentificeerd](../../media/ExplorerEmailMalwareMenu.png) 

Klik **op Afzender** om uw lijst met weergaveopties te openen. Gebruik deze lijst om gegevens van afzender, geadresseerden, afzenderdomein, onderwerp, detectietechnologie, beveiligingsstatus en meer weer te geven. 

Als u bijvoorbeeld wilt zien welke acties zijn uitgevoerd op gedetecteerde e-mailberichten, kiest u **De status Beveiliging** in de lijst. Selecteer een optie en klik op de knop Vernieuwen om dat filter toe te passen op uw rapport.

![Opties voor bedreigingsbeveiligingsstatus voor Threat Explorer](../../media/ThreatExplorerProtectionStatusOptions.png)

Bekijk onder de grafiek meer details over specifieke berichten. Wanneer u een item in de lijst selecteert, wordt een fly-out-deelvenster geopend, waar u meer informatie geven over het item dat u hebt geselecteerd. 

![Threat Explorer met flyout geopend](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a>E-mail > Phish

Als u dit rapport wilt weergeven in Explorer (of realtimedetecties), kiest **u**  >  **E-mail**  >  **Phish**weergeven. In deze weergave worden e-mailberichten weergegeven die zijn geïdentificeerd als phishingpogingen.  

![Gegevens weergeven over e-mail die is geïdentificeerd als phishingpogingen](../../media/ThreatExplorerEmailPhish.png) 

Klik **op Afzender** om uw lijst met weergaveopties te openen. Gebruik deze lijst om gegevens weer te geven per afzender, geadresseerden, afzenderdomein, IP-adres voor afzenders, URL-domein, klik op vonnis en meer. 

Als u bijvoorbeeld wilt zien welke acties zijn ondernomen wanneer mensen op URL's hebben geklikt die zijn geïdentificeerd als phishingpogingen, kiest u **Klik op verdict** in de lijst, selecteert u een of meer opties en klikt u op de knop Vernieuwen.

![Klik op verdict opties voor het Phish rapport](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

Bekijk onder de grafiek meer details over specifieke berichten, URL-klikken, URL's en e-mailoorsprong. 

![URL's gedetecteerd als phish in e-mailberichten](../../media/ThreatExplorerEmailPhishURLs.png)

Wanneer u een item in de lijst selecteert, zoals een URL die is gedetecteerd, wordt een fly-out-deelvenster geopend, waar u meer informatie krijgen over het item dat u hebt geselecteerd. 

![Details over een gedetecteerde URL](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a>E->-inzendingen

Als u dit rapport wilt bekijken, kiest u **View**in Explorer (of realtimedetecties)  >  **E-mailinzendingen**  >  **weergeven**. Deze weergave toont e-mail die gebruikers hebben gerapporteerd als ongewenste, niet ongewenste e-mail of phishing. 

![E-mailberichten gerapporteerd door gebruikers](../../media/ThreatExplorerEmailUserReportedViewOptions.png) 

Klik **op Afzender** om uw lijst met weergaveopties te openen. Gebruik deze lijst om informatie te bekijken per afzender, ontvangers, rapporttype (de vaststelling van de gebruiker dat de e-mail ongewenste e-mail was, niet ongewenste of phish), en meer. 

Als u bijvoorbeeld informatie wilt weergeven over e-mailberichten die als phishingpogingen zijn gerapporteerd, klikt u op **Sender**  >  **type afzenderrapport,** selecteert u **Phish**en klikt u op de knop Vernieuwen.

![Phish geselecteerd voor filter Rapporttype](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

Bekijk onder de grafiek meer details over specifieke e-mailberichten, zoals onderwerpregel, het IP-adres van de afzender, de gebruiker die het bericht als ongewenste, niet ongewenste of phish, en meer heeft gerapporteerd. 

![Berichten die zijn gerapporteerd als phishingpogingen](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

Selecteer een item in de lijst om aanvullende details weer te geven.

## <a name="email--all-email"></a>E-> alle e-mail

Als u dit rapport wilt weergeven, kiest **u**in Explorer De optie  >  **E-mail**alle  >  **e-mail**weergeven . Deze weergave toont een all-up weergave van e-mailactiviteiten, inclusief e-mail die als kwaadaardig is geïdentificeerd als gevolg van phishing of malware, evenals alle niet-schadelijke e-mail (normale e-mail, spam en bulkmail). 

> [!NOTE]
> Als u een foutmelding krijgt die te veel gegevens leest **om weer te geven,** voegt u een filter toe en verkleint u indien nodig het datumbereik dat u bekijkt. 

Als u een filter wilt toepassen, kiest u **Afzender,** selecteert u een item in de lijst en klikt u op de knop Vernieuwen. In ons voorbeeld **gebruikten** we Detectietechnologie als filter (er zijn verschillende opties beschikbaar). Bekijk informatie per afzender, afzenderdomein, ontvangers, onderwerp, bestandsnaam van bijlagen, malwarefamilie, beveiligingsstatus (acties die zijn uitgevoerd door uw functies en beleid voor bedreigingsbescherming in Office 365), detectietechnologie (hoe de malware is gedetecteerd) en meer. 

![Gegevens over gedetecteerde e-mail weergeven door detectietechnologie](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png) 

Bekijk onder de grafiek meer details over specifieke e-mailberichten, zoals onderwerpregel, ontvanger, afzender, status, enzovoort. 

## <a name="content--malware"></a>Content > Malware

Als u dit rapport wilt bekijken, kiest u **View**in Explorer (of realtime detecties) De optie  >  **Inhoudsmalware**  >  **weergeven.** In deze weergave worden bestanden weergegeven die door Office 365 Advanced Threat Protection als kwaadaardig zijn geïdentificeerd [in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.](atp-for-spo-odb-and-teams.md)

Bekijk informatie per malwarefamilie, detectietechnologie (hoe de malware is gedetecteerd) en werkbelasting (OneDrive, SharePoint of Teams). 

![Gegevens over gedetecteerde malware weergeven](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)  

Bekijk onder de grafiek meer details over specifieke bestanden, zoals bestandsnaam van bijlagen, werkbelasting, bestandsgrootte, die het bestand voor het laatst hebben gewijzigd en meer. 
  
## <a name="click-to-filter-capabilities"></a>Klik-naar-filter mogelijkheden

Met Explorer (en realtime detecties) u met één klik een filter toepassen. Klik op een item in de legenda en dat item wordt een filter voor het rapport. Stel dat we kijken naar de malwareweergave in Explorer:
  
![Ga naar Threat management \> Explorer](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
Als u op **ATP Detonation** in deze grafiek klikt, resulteert dit in een weergave als deze: 
  
![Explorer gefilterd om alleen ATP-detonatieresultaten weer te geven](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)
  
In deze weergave kijken we nu naar gegevens voor bestanden die zijn ontploft door [Office 365 ATP Safe Attachments](atp-safe-attachments.md). Onder de grafiek kunnen we details zien over specifieke e-mailberichten met bijlagen die zijn gedetecteerd door ATP Safe Attachments.
  
![Specifieke details over e-mailberichten met gedetecteerde bijlagen](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)
  
Als u een of meer items selecteert, wordt het menu **Acties** geactiveerd, waarin verschillende opties worden aangeboden waaruit u kiezen voor het geselecteerde item(s). 
  
![Als u een item selecteert, wordt het menu Acties geactiveerd](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)
  
De mogelijkheid om in een klik te filteren en naar specifieke details te navigeren, kan u veel tijd besparen bij het onderzoeken van bedreigingen.

## <a name="queries-and-filters"></a>Query's en filters

Explorer (evenals de real-time detecties rapport) heeft een aantal krachtige filters en query's mogelijkheden die u in staat stellen om te boren in details, zoals top gerichte gebruikers, top malware families, detectie technologie en nog veel meer. Elk type rapport biedt verschillende manieren om gegevens te bekijken en te verkennen.

> [!IMPORTANT]
> Gebruik geen jokertekens, zoals een sterretje of een vraagteken, in de querybalk voor Explorer (of realtime detecties). Wanneer u in het **veld Onderwerp** zoekt naar e-mailberichten, voert Explorer (of realtime detecties) gedeeltelijke matching uit en levert resultaten op die vergelijkbaar zijn met een zoekopdracht met een wildcard.
