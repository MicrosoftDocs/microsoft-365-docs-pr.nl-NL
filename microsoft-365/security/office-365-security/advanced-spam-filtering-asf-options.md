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
description: Beheerders kunnen meer informatie krijgen over de instellingen van het Geavanceerde spamfilter (ASF) die beschikbaar zijn in antispambeleid in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0b6db02815f5b50d199e10685e2895a174997fd2
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288679"
---
# <a name="advanced-spam-filter-asf-settings-in-eop"></a>Asf-instellingen (Advanced Spam Filter) in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!NOTE]
> ASF-instellingen die momenteel beschikbaar zijn in antispambeleid worden afgeschaft. Het is raadzaam deze instellingen niet te gebruiken in antispambeleid. De functionaliteit van deze ASF-instellingen wordt opgenomen in andere onderdelen van de filterstack. Zie de instellingen voor het [antispambeleid van EOP voor meer informatie.](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

In alle Microsoft 365-organisaties kunnen beheerders met de instellingen voor het Geavanceerde spamfilter (ASF) in antispambeleid in EOP berichten markeren als spam op basis van specifieke berichteigenschappen. ASF is specifiek bedoeld voor deze eigenschappen omdat ze vaak voorkomen in spam. Afhankelijk van de eigenschap wordt het bericht gemarkeerd als **Spam** of Zeer **vertrouwelijkheidsspam.**

> [!NOTE]
> Het inschakelen van een of meer ASF-instellingen is een agressieve aanpak van spamfilters. U kunt berichten die op ASF zijn gefilterd, niet als fout-positieven rapporteren. U kunt berichten identificeren die door ASF zijn gefilterd op:
>
> - Periodieke spam quarantainemeldingen voor eindgebruikers.
>
> - De aanwezigheid van gefilterde berichten in quarantaine.
>
> - De specifieke `X-CustomSpam:` X-koptekstvelden die aan berichten worden toegevoegd, zoals beschreven in dit artikel.

In de volgende secties worden de ASF-instellingen en -opties beschreven die beschikbaar zijn in antispambeleid in het beveiligings- & compliancecentrum en in Exchange Online PowerShell of zelfstandige EOP PowerShell[(New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy) en [Set-HostedContentFilterPolicy).](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy) Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.

## <a name="enable-disable-or-test-asf-settings"></a>ASF-instellingen inschakelen, uitschakelen of testen

Voor elke ASF-instelling zijn de volgende opties beschikbaar in het antispambeleid:

- **On:** ASF adds the corresponding X-header field to the message, and either marks the message as **Spam** (SCL 5 or 6 for [Increase spam score settings)](#increase-spam-score-settings)or **High confidence spam** (SCL 9 for Mark as [spam settings).](#mark-as-spam-settings)

- **Uit:** de instelling ASF is uitgeschakeld. Dit is de standaardwaarde en het is raadzaam deze niet te wijzigen.

- **Test:** ASF voegt het bijbehorende veld met de X-koptekst toe aan het bericht. Wat er met het bericht gebeurt, wordt bepaald door de waarde voor **de testmodus** *(TestModeAction).*

  - **Geen:** berichtbezorging wordt niet beïnvloed door de ASF-detectie. Het bericht is nog steeds onderworpen aan andere typen filters en regels in EOP.

  - **Standaard X-koptekst toevoegen (*AddXHeader*)**: De X-koptekstwaarde `X-CustomSpam: This message was filtered by the custom spam filter option` wordt toegevoegd aan het bericht. U kunt deze waarde gebruiken in regels voor Postvak IN of regels voor de e-mailstroom (ook wel transportregels genoemd) om de bezorging van het bericht te beïnvloeden.

  - **Bericht BCC verzenden *(BccMessage:*** De opgegeven e-mailadressen (de parameterwaarde *TestModeBccToRecipients* in PowerShell) worden toegevoegd aan het veld BCC van het bericht en het bericht wordt bezorgd bij de extra BCC-geadresseerden. In het & Compliancecentrum voor beveiliging scheidt u meerdere e-mailadressen door puntkomma's (;). In PowerShell scheidt u meerdere e-mailadressen door komma's.

  **Opmerkingen**:

  - Testmodus is niet beschikbaar voor de volgende ASF-instellingen:

    - **Filteren van voorwaardelijke afzender-id: mislukt** *(MarkAsSpamFromAddressAuthFail)*
    - **NDR-backscatter**(*MarkAsSpamNdrBackscatter*)
    - **SPF-record: harde fail** *(MarkAsSpamSpfRecordHardFail*)

  - Dezelfde testmodusactie wordt toegepast *op* alle ASF-instellingen die zijn ingesteld op **Testen.** U kunt geen verschillende testmodusacties configureren voor verschillende ASF-instellingen.

## <a name="increase-spam-score-settings"></a>Spamscore-instellingen verhogen

Met de volgende ASF-instellingen wordt het betrouwbaarheidsniveau voor spam van gedetecteerde berichten ingesteld  op 5 of 6, die overeenkomt met het filter voor ongewenste e-mail en de bijbehorende actie in het antispambeleid.

****

|Beleidsinstelling voor antispambeleid|Beschrijving|X-koptekst toegevoegd|
|---|---|---|
|**Afbeeldingskoppelingen naar externe sites** <p> *IncreaseScoreWithImageLinks*|Berichten die `<Img>` HTML-codekoppelingen naar externe sites bevatten (bijvoorbeeld via http), worden gemarkeerd als spam.|`X-CustomSpam: Image links to remote sites`|
|**URL omleiden naar andere poort** <p> *IncreaseScoreWithRedirectToOtherPort*|Bericht met hyperlinks die worden omgeleid naar andere TCP-poorten dan 80 (HTTP), 8080 (alternatief HTTP) of 443 (HTTPS) worden gemarkeerd als spam.|`X-CustomSpam: URL redirect to other port`|
|**Numeriek IP-adres in URL** <p> *IncreaseScoreWithNumericIps*|Berichten met numerieke URL's (meestal IP-adressen) worden gemarkeerd als spam.|`X-CustomSpam: Numeric IP in URL`|
|**URL naar websites van .biz of .info** <p> *IncreaseScoreWithBizOrInfoUrls*|Berichten die de bericht zelf bevatten of koppelingen bevatten, worden `.biz` `.info` gemarkeerd als spam.|`X-CustomSpam: URL to .biz or .info websites`|
|

## <a name="mark-as-spam-settings"></a>Markeren als spaminstellingen

Met de volgende asf-instellingen wordt de SCL van gedetecteerde  berichten ingesteld op 9, die overeenkomt met de spamfilter met hoge betrouwbaarheid en de bijbehorende actie in het antispambeleid.

****

|Beleidsinstelling voor antispambeleid|Beschrijving|X-koptekst toegevoegd|
|---|---|---|
|**Lege berichten** <p> *MarkAsSpamEmptyMessages*|Berichten zonder onderwerp, geen inhoud in de bericht zelf en geen bijlagen worden gemarkeerd als zeer vertrouwelijkheidspam.|`X-CustomSpam: Empty Message`|
|**JavaScript of VBScript in HTML** <p> *MarkAsSpamJavaScriptInHtml*|Berichten die JavaScript of Visual Basic Script Edition in HTML gebruiken, worden gemarkeerd als zeer spam. <p> Deze talen voor scripts worden in e-mailberichten gebruikt om ervoor te zorgen dat specifieke acties automatisch worden uitgevoerd.|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**Frame- of IFrame-codes in HTML** <p> *MarkAsSpamFramesInHtml*|Berichten met of `<frame>` `<iframe>` HTML-codes worden gemarkeerd als zeer spam. <p> Deze tags worden in e-mailberichten gebruikt om de pagina op te maken voor het weergeven van tekst of graphics.|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**Objectlabels in HTML** <p> *MarkAsSpamObjectTagsInHtml*|Berichten die `<object>` HTML-codes bevatten, worden gemarkeerd als zeer spam. <p> Met deze code kunnen in plug-ins of toepassingen worden uitgevoerd in een HTML-venster.|`X-CustomSpam: Object tag in html`|
|**Labels insluiten in HTML** <p> *MarkAsSpamEmbedTagsInHtml*|Berichten die `<embed>` HTML-codes bevatten, worden gemarkeerd als zeer spam. <p> Met deze code kunt u verschillende soorten documenten insluiten in een HTML-document (bijvoorbeeld geluiden, video's of afbeeldingen).|`X-CustomSpam: Embed tag in html`|
|**Formuliercodes in HTML** <p> *MarkAsSpamFormTagsInHtml*|Berichten die `<form>` HTML-codes bevatten, worden gemarkeerd als zeer spam. <p> Deze tag wordt gebruikt om websiteformulieren te maken. E-mailadvertenties bevatten vaak dit label om informatie van de geadresseerde te vragen.|`X-CustomSpam: Form tag in html`|
|**Web bugs in HTML** <p> *MarkAsSpamWebBugsInHtml*|Een *web* bug (ook wel een *webbaken* genoemd) is een grafisch element (vaak slechts één pixel bij één pixel) dat wordt gebruikt in e-mailberichten om te bepalen of het bericht is gelezen door de geadresseerde. <p> Berichten die web bugs bevatten, worden gemarkeerd als zeer spam. <p> Legitieme nieuwsbrieven maken mogelijk gebruik van web bugs, maar veel beschouwen dit als een inbreuk op de privacy. |`X-CustomSpam: Web bug`|
|**Lijst met gevoelige woorden toepassen** <p> *MarkAsSpamSensitiveWordList*|Microsoft onderhoudt een dynamische, maar niet-bewerkbare lijst met woorden die zijn gekoppeld aan potentieel aanstootgevende berichten. <p> Berichten die woorden uit de lijst met gevoelige woorden in het onderwerp of de bericht zelf bevatten, worden gemarkeerd als zeer vertrouwelijke spam.|`X-CustomSpam: Sensitive word in subject/body`|
|**SPF-record: harde fail** <p> *MarkAsSpamSpfRecordHardFail*|Berichten die zijn verzonden vanaf een IP-adres dat niet is opgegeven in de SPF Sender Policy Framework-record (SPF) in DNS voor het bron-e-maildomein, worden gemarkeerd als zeer vertrouwde spam. <p> De testmodus is niet beschikbaar voor deze instelling.|`X-CustomSpam: SPF Record Fail`|
|**Filteren van voorwaardelijke afzender-id's: de fout werkt niet** <p> *MarkAsSpamFromAddressAuthFail*|Berichten waarvan de voorwaardelijke afzender-id-controle mislukt, worden gemarkeerd als spam. <p> Met deze instelling wordt een SPF-controle gecombineerd met een afzender-id-controle om u te beschermen tegen berichtkoppen die vervalste afzenders bevatten. <p> De testmodus is niet beschikbaar voor deze instelling.|`X-CustomSpam: SPF From Record Fail`|
|**NDR-backscatter** <p> *MarkAsSpamNdrBackscatter*|*Backscatter* is nutteloos meldingen over niet-bezorging (ook wel NDR's of niet-bezorgdberichten genoemd) die worden veroorzaakt door vervalste afzenders in e-mailberichten. Zie [Backscatter-berichten en EOP voor meer informatie.](backscatter-messages-and-eop.md) <p> U hoeft deze instelling niet te configureren in de volgende omgevingen, omdat er legitieme NDR's worden geleverd en backscatter wordt gemarkeerd als spam: <ul><li>Microsoft 365-organisaties met Exchange Online-postvakken.</li><li>On-premises e-mailorganisaties waar u *uitgaande e-mail routeert* via EOP.</li></ul> <p> In zelfstandige EOP-omgevingen waarin inkomende e-mail naar on-premises postvakken wordt beschermd, heeft het in- of uitschakelen van deze instelling het volgende resultaat: <ul><li> **Aan:** Legitieme NDR's worden geleverd en backscatter wordt gemarkeerd als spam.</li><li>**Uit:** Legitieme NR's en backscatter door middel van normale spamfilters. De meest legitieme NR's worden bezorgd bij de afzender van het oorspronkelijke bericht. Sommige, maar niet alle, backscatter worden gemarkeerd als zeer spam. Backscatter kan per definitie alleen worden bezorgd bij de vervalste afzender, niet bij de oorspronkelijke afzender.</li></ul> <p> De testmodus is niet beschikbaar voor deze instelling.|`X-CustomSpam: Backscatter NDR`|
|
