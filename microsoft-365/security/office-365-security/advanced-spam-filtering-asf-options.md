---
title: ASF-instellingen in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b286f853-b484-4af0-b01f-281fffd85e7a
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen meer informatie krijgen over de asf-instellingen (Advanced Spam Filter) die beschikbaar zijn in antispambeleid in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 12f193ef61205e8568341c774b957ce4a9dd7988
ms.sourcegitcommit: 50f484fc501d81506a714b127a56a6979888d849
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2021
ms.locfileid: "52779420"
---
# <a name="advanced-spam-filter-asf-settings-in-eop"></a>Geavanceerde instellingen voor spamfilter (ASF) in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> ASF-instellingen die momenteel beschikbaar zijn in antispambeleid, worden afgeschaft. U wordt aangeraden deze instellingen niet te gebruiken in antispambeleid. De functionaliteit van deze ASF-instellingen wordt opgenomen in andere onderdelen van de filtertack. Zie [EOP-instellingen voor antispambeleid](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)voor meer informatie.

In alle Microsoft 365 organisaties kunnen beheerders met de asf-instellingen (Advanced Spam Filter) in antispambeleid in EOP berichten markeren als spam op basis van specifieke berichteigenschappen. ASF richt zich specifiek op deze eigenschappen omdat ze vaak worden gevonden in spam. Afhankelijk van de eigenschap wordt het bericht door ASF-detecties gemarkeerd als **Spam** of **Spam met hoog vertrouwen.**

> [!NOTE]
> Het inschakelen van een of meer van de ASF-instellingen is een agressieve manier om spam te filteren. U kunt berichten die door ASF zijn gefilterd, niet als onwaar-positieven rapporteren. U kunt berichten identificeren die door ASF zijn gefilterd door:
>
> - Periodieke meldingen over spam door eindgebruikers.
> - De aanwezigheid van gefilterde berichten in quarantaine.
> - De specifieke `X-CustomSpam:` X-headervelden die worden toegevoegd aan berichten, zoals beschreven in dit artikel.

In de volgende secties worden de ASF-instellingen en -opties beschreven die beschikbaar zijn in antispambeleid in het Microsoft 365-beveiligingscentrum en in Exchange Online PowerShell Exchange Online zelfstandige EOP PowerShell[(New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy) en [Set-HostedContentFilterPolicy).](/powershell/module/exchange/set-hostedcontentfilterpolicy) Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.

## <a name="enable-disable-or-test-asf-settings"></a>ASF-instellingen inschakelen, uitschakelen of testen

Voor elke ASF-instelling zijn de volgende opties beschikbaar in antispambeleid:

- **Op**: ASF voegt het bijbehorende veld X-header toe aan het bericht en markeert het bericht als **Spam** (SCL 5 of 6 voor Instellingen voor het verhogen van [de spamscore)](#increase-spam-score-settings)of Spam met hoge betrouwbaarheid **(SCL** 9 voor Markeren als [spam-instellingen).](#mark-as-spam-settings)
- **Uit:** De instelling ASF is uitgeschakeld. Dit is de standaardwaarde en u wordt aangeraden deze niet te wijzigen.
- **Test:** ASF voegt het bijbehorende veld X-header toe aan het bericht. Wat er met het bericht gebeurt, wordt bepaald door de **waarde Testmodus** *(TestModeAction)*:
  - **Geen:** Berichtbezorging wordt niet beïnvloed door de ASF-detectie. Het bericht is nog steeds onderhevig aan andere typen filters en regels in EOP.
  - **Standaard X-headertekst toevoegen (*AddXHeader*)**: De X-headerwaarde `X-CustomSpam: This message was filtered by the custom spam filter option` wordt toegevoegd aan het bericht. U kunt deze waarde gebruiken in regels voor Postvak IN of regels voor e-mailstroom (ook wel transportregels genoemd) om de bezorging van het bericht te beïnvloeden.
  - **BCC-bericht verzenden *(BccMessage)***: De opgegeven e-mailadressen (de *parameterwaarde TestModeBccToRecipients* in PowerShell) worden toegevoegd aan het BCC-veld van het bericht en het bericht wordt bezorgd bij de extra BCC-geadresseerden. In het beveiligingscentrum scheidt u meerdere e-mailadressen per puntkomma (;). In PowerShell scheidt u meerdere e-mailadressen door komma's.

  **Opmerkingen**:

  - Testmodus is niet beschikbaar voor de volgende ASF-instellingen:
    - **Voorwaardelijke afzender-id-filtering: hard fail** (*MarkAsSpamFromAddressAuthFail*)
    - **NDR backscatter**(*MarkAsSpamNdrBackscatter*)
    - **SPF-record: hard fail** (*MarkAsSpamSpfRecordHardFail*)
  - Dezelfde actie in de testmodus wordt toegepast op *alle* ASF-instellingen die zijn ingesteld op **Testen.** U kunt geen verschillende acties in de testmodus configureren voor verschillende ASF-instellingen.

## <a name="increase-spam-score-settings"></a>Instellingen voor spamscores verhogen

Met de volgende ASF-instellingen wordt het betrouwbaarheidsniveau voor spam (SCL) van gedetecteerde berichten ingesteld op 5 of 6, wat overeenkomt met de uitspraak over het spamfilter en de bijbehorende actie in antispambeleid. 

<br>

****

|Antispambeleidsinstelling|Omschrijving|X-header toegevoegd|
|---|---|---|
|**Afbeeldingskoppelingen naar externe websites** <p> *IncreaseScoreWithImageLinks*|Berichten met `<Img>` HTML-tagkoppelingen naar externe sites (bijvoorbeeld http) worden gemarkeerd als spam.|`X-CustomSpam: Image links to remote sites`|
|**Numeriek IP-adres in URL** <p> *IncreaseScoreWithNumericIps*|Berichten met numerieke URL's (meestal IP-adressen) worden gemarkeerd als spam.|`X-CustomSpam: Numeric IP in URL`|
|**URL omleiden naar andere poort** <p> *IncreaseScoreWithRedirectToOtherPort*|Berichten met hyperlinks die worden omgeleid naar andere TCP-poorten dan 80 (HTTP), 8080 (alternatief HTTP) of 443 (HTTPS) worden gemarkeerd als spam.|`X-CustomSpam: URL redirect to other port`|
|**Koppelingen naar .biz- of .info-websites** <p> *IncreaseScoreWithBizOrInfoUrls*|Berichten met `.biz` of koppelingen in de tekst van het bericht worden gemarkeerd als `.info` spam.|`X-CustomSpam: URL to .biz or .info websites`|
|

## <a name="mark-as-spam-settings"></a>Markeren als spam-instellingen

Met de volgende ASF-instellingen wordt de SCL van gedetecteerde  berichten ingesteld op 9, wat overeenkomt met de uitspraak over het hoge betrouwbaarheidsfilter en de bijbehorende actie in antispambeleid.

<br>

****

|Antispambeleidsinstelling|Omschrijving|X-header toegevoegd|
|---|---|---|
|**Berichten leeg maken** <p> *MarkAsSpamEmptyMessages*|Berichten zonder onderwerp, geen inhoud in de berichtinhoud en geen bijlagen worden gemarkeerd als spam met hoog vertrouwen.|`X-CustomSpam: Empty Message`|
|**Ingesloten tags in HTML** <p> *MarkAsSpamEmbedTagsInHtml*|Berichten met `<embed>` HTML-tags worden gemarkeerd als spam met veel vertrouwen. <p> Met deze tag kunt u verschillende soorten documenten insluiten in een HTML-document (bijvoorbeeld geluiden, video's of afbeeldingen).|`X-CustomSpam: Embed tag in html`|
|**JavaScript of VBScript in HTML** <p> *MarkAsSpamJavaScriptInHtml*|Berichten die JavaScript of Visual Basic Script Edition in HTML gebruiken, worden gemarkeerd als spam met hoge betrouwbaarheid. <p> Deze scripttalen worden gebruikt in e-mailberichten om ervoor te zorgen dat specifieke acties automatisch worden uitgevoerd.|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**Formulierlabels in HTML** <p> *MarkAsSpamFormTagsInHtml*|Berichten met `<form>` HTML-tags worden gemarkeerd als spam met hoge betrouwbaarheid. <p> Deze tag wordt gebruikt om websiteformulieren te maken. E-mailadvertenties bevatten vaak deze tag om informatie van de geadresseerde te vragen.|`X-CustomSpam: Form tag in html`|
|**Frame- of iframetags in HTML** <p> *MarkAsSpamFramesInHtml*|Berichten met of `<frame>` `<iframe>` HTML-tags worden gemarkeerd als spam met hoge betrouwbaarheid. <p> Deze tags worden gebruikt in e-mailberichten om de pagina op te maken voor het weergeven van tekst of afbeeldingen.|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**Web bugs in HTML** <p> *MarkAsSpamWebBugsInHtml*|Een *webbug* (ook wel een *webbaken* genoemd) is een grafisch element (vaak zo klein als één pixel voor één pixel) dat wordt gebruikt in e-mailberichten om te bepalen of het bericht is gelezen door de geadresseerde. <p> Berichten die web bugs bevatten, worden gemarkeerd als spam met veel vertrouwen. <p> Legitieme nieuwsbrieven kunnen web bugs gebruiken, hoewel velen dit als een inbreuk op de privacy beschouwen. |`X-CustomSpam: Web bug`|
|**Objectlabels in HTML** <p> *MarkAsSpamObjectTagsInHtml*|Berichten met `<object>` HTML-tags worden gemarkeerd als spam met hoge betrouwbaarheid. <p> Met deze tag kunnen insteektoepassingen of toepassingen worden uitgevoerd in een HTML-venster.|`X-CustomSpam: Object tag in html`|
|**Gevoelige woorden** <p> *MarkAsSpamSensitiveWordList*|Microsoft behoudt een dynamische, maar niet-bewerkbare lijst met woorden die zijn gekoppeld aan mogelijk aanstootgevende berichten. <p> Berichten die woorden uit de lijst met gevoelige woorden in het onderwerp of de bericht body bevatten, worden gemarkeerd als spam met veel vertrouwen.|`X-CustomSpam: Sensitive word in subject/body`|
|**SPF-record: hard fail** <p> *MarkAsSpamSpfRecordHardFail*|Berichten die worden verzonden vanaf een IP-adres dat niet is opgegeven in de SPF Sender Policy Framework -record (SPF) in DNS voor het bron-e-maildomein, worden gemarkeerd als spam met hoge betrouwbaarheid. <p> Testmodus is niet beschikbaar voor deze instelling.|`X-CustomSpam: SPF Record Fail`|
|**Het filteren van afzender-id's mislukt hard** <p> *MarkAsSpamFromAddressAuthFail*|Berichten die moeilijk mislukken bij een voorwaardelijke afzender-idcontrole, worden gemarkeerd als spam. <p> Met deze instelling wordt een SPF-controle gecombineerd met een afzender-idcontrole om u te beschermen tegen berichtkoppen met vervalste afzenders. <p> Testmodus is niet beschikbaar voor deze instelling.|`X-CustomSpam: SPF From Record Fail`|
|**Backscatter** <p> *MarkAsSpamNdrBackscatter*|*Backscatter* is nutteloos niet-bezorgingsrapporten (ook wel NDR's of niet-bezorgde berichten genoemd) die worden veroorzaakt door vervalste afzenders in e-mailberichten. Zie [Backscatter-berichten en EOP voor meer informatie.](backscatter-messages-and-eop.md) <p> U hoeft deze instelling niet in de volgende omgevingen te configureren, omdat legitieme NDR's worden geleverd en backscatter is gemarkeerd als spam: <ul><li>Microsoft 365 organisaties met Exchange Online postvakken.</li><li>On-premises e-mailorganisaties waar u *uitgaande* e-mail routeert via EOP.</li></ul> <p> In zelfstandige EOP-omgevingen die binnenkomende e-mail beveiligen voor on-premises postvakken, heeft het in- of uitschakelen van deze instelling het volgende resultaat: <ul><li> **Op**: Legitieme NR's worden bezorgd en backscatter is gemarkeerd als spam.</li><li>**Uit:** Legitieme NR's en backscatter worden door normale spamfilters gefilterd. De meest legitieme NR's worden bezorgd bij de oorspronkelijke afzender van het bericht. Sommige, maar niet alle, backscatter worden gemarkeerd als spam met hoge betrouwbaarheid. Backscatter kan per definitie alleen worden bezorgd bij de vervalste afzender, niet bij de oorspronkelijke afzender.</li></ul> <p> Testmodus is niet beschikbaar voor deze instelling.|`X-CustomSpam: Backscatter NDR`|
|
