---
title: ATO-instellingen in Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b286f853-b484-4af0-b01f-281fffd85e7a
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Meer informatie over de instellingen van Advanced Spam Filter (AsF) in antispambeleid, waarmee beheerders berichten kunnen identificeren die specifieke berichteigenschappen bevatten die vaak in spam worden gebruikt.
ms.openlocfilehash: 31793f5996cc27cf7e5de75d9c190657e6592c57
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034132"
---
# <a name="advanced-spam-filter-asf-settings-in-office-365"></a>Instellingen voor geavanceerde spamfilters (AsF) in Office 365

> [!NOTE]
> Asf-instellingen die momenteel beschikbaar zijn in antispambeleid worden momenteel afgeschaft. We raden u aan deze instellingen niet te gebruiken in het antispambeleid. De functionaliteit van deze AsF-instellingen wordt opgenomen in andere delen van de filterstapel. Zie [EOP-beleidsinstellingen voor antispam](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)voor meer informatie .

Met de instellingen voor geavanceerde spamfilters (Asf) in antispambeleid (ook wel spamfilterbeleid of inhoudsfilterbeleid genoemd) kunnen beheerders berichten markeren als spam op basis van specifieke berichteigenschappen. Asf richt zich specifiek op deze eigenschappen omdat ze vaak worden gevonden in spam. Afhankelijk van de eigenschap, asf detecties zal ofwel markeren het bericht als **Spam** of **Hoog vertrouwen spam**.

> [!NOTE]
> Het inschakelen van een of meer van de AsF-instellingen is een agressieve benadering van spamfiltering. U geen berichten rapporteren die door AsF worden gefilterd als false positives. U berichten identificeren die door AsF zijn gefilterd door: <ul><li>Periodieke spamquarantainemeldingen voor eindgebruikers.</li><li>De aanwezigheid van gefilterde berichten in quarantaine.</li><li>De `X-CustomSpam:` specifieke X-headervelden die worden toegevoegd aan berichten zoals beschreven in dit onderwerp.</li></ul>

In de volgende secties worden de AsF-instellingen en -opties beschreven die beschikbaar zijn in antispambeleid in het Security & Compliance Center en in Exchange Online PowerShell of standalone Exchange Online Protection PowerShell[(New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedcontentfilterpolicy) en [Set-HostedContentFilterPolicy).](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy) Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md) voor meer informatie.

## <a name="enable-disable-or-test-asf-settings"></a>Asf-instellingen in- of uitschakelen of testen

Voor elke Asf-instelling zijn de volgende opties beschikbaar in antispambeleid:

- **Op**: AsF voegt de bijbehorende X-header veld aan het bericht, en ofwel markeert het bericht als **Spam** (SCL 5 of 6 voor [Verhoging spam score instellingen)](#increase-spam-score-settings)of Hoog vertrouwen **spam** (SCL 9 voor Mark [als spam-instellingen).](#mark-as-spam-settings)

- **Uit:** de AsF-instelling is uitgeschakeld. Dit is de standaardwaarde en we raden u aan deze niet te wijzigen.

- **Test:** AsF voegt het bijbehorende X-header veld toe aan het bericht. Wat er met het bericht gebeurt, wordt bepaald door de waarde **testmodus** *(TestModeAction):*

  - **Geen**: Berichtroutering en -levering wordt niet beïnvloed door de AsF-detectie. Het bericht is nog steeds onderhevig aan andere soorten filtering en regels in EOP.

  - **Standaard tekst met x-header toevoegen (*AddXHeader*)**: De x-headerwaarde `X-CustomSpam: This message was filtered by the custom spam filter option` wordt aan het bericht toegevoegd. U deze waarde gebruiken in regels voor Postvak IN of e-mailstroomregels (ook wel transportregels genoemd) om de routering en levering van het bericht te beïnvloeden.

  - **Bcc-bericht verzenden (*BCCMessage*)**: De opgegeven e-mailadressen (de parameterwaarde *TestModeBccToRecipients* in PowerShell) worden toegevoegd aan het bcc-veld van het bericht en het bericht wordt geleverd aan de BCC-ontvangers. In het Security & Compliance Center scheidt u meerdere e-mailadressen per puntkomma (; ). In PowerShell scheidt u meerdere e-mailadressen per komma.

  **Opmerkingen**:

  - De testmodus is niet beschikbaar voor de volgende Asf-instellingen:

    - **Voorwaardelijke sender ID filtering: hard fail** *(MarkAsSpamFromAddressAuthFail)*

    - **NDR backscatter**(*MarkAsSpamNdrBackscatter*)

    - **SPF record: hard fail** *(MarkAsSpamSpfRecordHardFail)*

  - Dezelfde testmodusactie wordt toegepast op *alle* AsF-instellingen die zijn ingesteld op **Testen.** U geen verschillende testmodusacties configureren voor verschillende Asf-instellingen.

## <a name="increase-spam-score-settings"></a>Instellingen voor spamscore verhogen

De volgende AsF-instellingen stellen het spamvertrouwensniveau (SCL) van gedetecteerde berichten in op 5 of 6, wat overeenkomt met **het** spamfiltervonnis en de bijbehorende actie in het antispambeleid.

||||
|:-----|:-----|:-----|
|**Instelling voor antispambeleid**|**Beschrijving**|**X-header toegevoegd**|
|**Afbeeldingskoppelingen naar externe sites** <br/><br/> *VerhogingScoreWithImageLinks*|Berichten die `<Img>` HTML-tagkoppelingen naar externe sites bevatten (bijvoorbeeld via http) worden gemarkeerd als spam.|`X-CustomSpam: Image links to remote sites`|
|**URL-omleiding naar andere poort** <br/><br/> *VerhogingScoreWithRedirecttoOtherPort*|Berichten met hyperlinks die worden omgeleid naar andere TCP-poorten dan 80 (HTTP), 8080 (alternatieve HTTP) of 443 (HTTPS) worden gemarkeerd als spam.|`X-CustomSpam: URL redirect to other port`|
|**Numeriek IP-adres in URL** <br/><br/> *IncreaseScorewithNumericIps*|Berichten die op numerieke basis URL's bevatten (meestal IP-adressen) worden gemarkeerd als spam.|`X-CustomSpam: Numeric IP in URL`|
|**URL naar .biz of .info websites** <br/><br/> *IncreaseScoreWithBizOrInfoUrls*|Berichten die .biz- of .info-links in de hoofdtekst van het bericht bevatten, worden gemarkeerd als spam.|`X-CustomSpam: URL to .biz or .info websites`|
|

## <a name="mark-as-spam-settings"></a>Markeren als spam-instellingen

De volgende AsF-instellingen stellen de SCL van gedetecteerde berichten in op 9, wat overeenkomt met het oordeel van het **spamfilter** met veel vertrouwen en de bijbehorende actie in het antispambeleid.

||||
|:-----|:-----|:-----|
|**Instelling voor antispambeleid**|**Beschrijving**|**X-header toegevoegd**|
|**Lege berichten** <br/><br/> *MarkAsSpamEmptyMessages*|Berichten zonder onderwerp, geen inhoud in de berichttekst en geen bijlagen worden gemarkeerd als spam met een hoog vertrouwen.|`X-CustomSpam: Empty Message`|
|**JavaScript of VBScript in HTML** <br/><br/> *MarkasspamJavaScriptinhtml*|Berichten die JavaScript of Visual Basic Script Edition in HTML gebruiken, worden gemarkeerd als spam met een hoog vertrouwen. <br/><br/> Deze scripttalen worden gebruikt in e-mailberichten om ervoor te zorgen dat specifieke acties automatisch plaatsvinden.|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**Frame- of IFrame-tags in HTML** <br><br/> *Markasspamframesinhtml*|Berichten die `<frame>` HTML-tags bevatten of `<iframe>` worden gemarkeerd als spam met een hoog vertrouwen. <br/><br/> Deze tags worden gebruikt in e-mailberichten om de pagina op te maken voor het weergeven van tekst of afbeeldingen.|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**Objecttags in HTML** <br><br/> *Markasspamobjecttagsinhtml*|Berichten die `<object>` HTML-tags bevatten, worden gemarkeerd als spam met een hoog vertrouwen. <br/><br/> Met deze tag kunnen plug-ins of toepassingen worden uitgevoerd in een HTML-venster.|`X-CustomSpam: Object tag in html`|
|**Tags insluiten in HTML** <br><br/> *Markasspamembedtagsinhtml*|Berichten met `<embed>` HTML-tags worden gemarkeerd als spam met een hoog vertrouwen. <br/><br/> Met deze tag kunnen verschillende soorten documenten van verschillende gegevenstypen in een HTML-document worden ingesloten (bijvoorbeeld geluiden, films of afbeeldingen).|`X-CustomSpam: Embed tag in html`|
|**Formuliertags in HTML** <br><br/> *Markasspamformtagsinhtml*|Berichten die `<form>` HTML-tags bevatten, worden gemarkeerd als spam met een hoog vertrouwen. <br/><br/> Deze tag wordt gebruikt om websiteformulieren te maken. E-mailadvertenties bevatten vaak deze tag om informatie van de ontvanger te vragen.|`X-CustomSpam: Form tag in html`|
|**Webbugs in HTML** <br><br/> *MarkasspamWebbugsinhtml*|Een *webbug* (ook wel *webbeacon genoemd)* is een grafisch element (vaak zo klein als één pixel per pixel) dat wordt gebruikt in e-mailberichten om te bepalen of het bericht is gelezen. <br/><br/> Berichten die webbugs bevatten, worden gemarkeerd als spam met een hoog vertrouwen. <br/><br/> Legitieme nieuwsbrieven kunnen webbugs gebruiken, hoewel velen dit als een inbreuk op de privacy beschouwen. |`X-CustomSpam: Web bug`|
|**Gevoelige woordenlijst toepassen** <br><br/> *MarkasspamSensitiveWordList*|Microsoft onderhoudt een dynamische, maar niet-bewerkbare lijst met woorden die zijn gekoppeld aan mogelijk aanstootgevende berichten. <br/><br/> Berichten die woorden uit de gevoelige woordenlijst in de onderwerp- of berichttekst bevatten, worden gemarkeerd als spam met een hoog vertrouwen.|`X-CustomSpam: Sensitive word in subject/body`|
|**SPF-record: harde fail** <br><br/> *MarkasspamSpfRecordHardFail*|Berichten die worden verzonden vanaf een IP-adres dat niet is opgegeven in de SPF Sender Policy Framework (SPF)-record in DNS voor het brone-maildomein, worden gemarkeerd als spam met een hoog vertrouwen. <br/><br/> De testmodus is niet beschikbaar voor deze instelling.|`X-CustomSpam: SPF Record Fail`|
|**Voorwaardelijke Sender ID-filtering: hard mislukken** <br><br/> *MarkasspamfromAddressAuthFail*|Berichten die hard mislukken bij een voorwaardelijke sender id-controle worden gemarkeerd als spam. <br/><br/> Deze instelling combineert een SPF-controle met een Sender ID-controle om te beschermen tegen berichtkoppen die vervalste afzenders bevatten. <br/><br/> De testmodus is niet beschikbaar voor deze instelling.|`X-CustomSpam: SPF From Record Fail`|
|**NDR backscatter** <br><br/> *MarkAsSpamNdrBackscatter MarkAsSpamNdrBackscatter*|*Backscatter* is nutteloos niet-levering rapporten (ook bekend als NDR's of bounce berichten) veroorzaakt door vervalste afzenders in e-mailberichten. Zie [Backscatter-berichten en EOP voor](backscatter-messages-and-eop.md)meer informatie. <br/><br/> U hoeft deze instelling niet te configureren in de volgende omgevingen, omdat legitieme NDR's worden geleverd en backscatter is gemarkeerd als spam: <ul><li>Microsoft 365-organisaties met Exchange Online-postvakken.</li><li>On-premises e-mailorganisaties waar u uitgaande e-mail *routevia* EOP.</li></ul><br/> In zelfstandige EOP-omgevingen die binnenkomende e-mail naar on-premises postvakken beschermen, heeft het in- of uitschakelen van deze instelling het volgende resultaat: <ul><li> **Aan:** Legitieme NDR's worden geleverd en backscatter is gemarkeerd als spam.</li><li>**Uit:** Legitieme NDR's en backscatter gaan door normale spam filtering. De meeste legitieme NDr's worden geleverd aan de oorspronkelijke afzender van het bericht. Sommige, maar niet alle, backscatter zijn gemarkeerd als een hoog vertrouwen spam. Per definitie kan backscatter alleen worden geleverd aan de vervalste afzender, niet aan de oorspronkelijke afzender.</li></ul><br/> De testmodus is niet beschikbaar voor deze instelling.|`X-CustomSpam: Backscatter NDR`|
|
