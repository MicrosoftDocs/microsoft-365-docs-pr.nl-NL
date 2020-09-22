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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b286f853-b484-4af0-b01f-281fffd85e7a
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen informatie lezen over de instellingen voor geavanceerde spam filters (ASF) die beschikbaar zijn in het antispambeleid van Exchange Online Protection (EOP).
ms.openlocfilehash: f2c58349bc1ffd2bb231eadf83bd4d70582925a2
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199945"
---
# <a name="advanced-spam-filter-asf-settings-in-eop"></a>Geavanceerde instellingen voor spam filter (ASF) in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> ASF-instellingen die momenteel beschikbaar zijn in het antispambeleid worden verouderd. U wordt aangeraden deze instellingen niet te gebruiken in antispambeleid. De functionaliteit van deze ASF-instellingen wordt opgenomen in andere onderdelen van de filterstack. Zie voor meer informatie [EOP antispam beleidsinstellingen](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).

In alle Microsoft 365-organisaties zijn de ASF-instellingen (Advanced spam filter) in anti spam beleid in EOP toegestaan dat beheerders berichten als spam markeren op basis van specifieke berichteigenschappen. ASF verrichtt specifiek op deze eigenschappen, omdat deze vaak worden gevonden in spam. Afhankelijk van de eigenschap, markeren ASF-detectie berichten als **spam** of spam met een **hoge betrouwbaarheid**.

> [!NOTE]
> Het inschakelen van een of meer ASF-instellingen is een agressieve aanpak van spamfilters. U kunt geen berichten rapporteren die met ASF zijn gefilterd als onwaar, positief. U kunt berichten identificeren die door ASF zijn gefilterd door:
>
> - Periodieke meldingen van de Quarantine voor eindgebruikers van spam.
>
> - De aanwezigheid van gefilterde berichten in quarantaine.
>
> - De specifieke `X-CustomSpam:` X-header velden die worden toegevoegd aan berichten, zoals beschreven in dit onderwerp.

In de volgende secties worden de ASF-instellingen en-opties beschreven die beschikbaar zijn in Antispambeleid in het beveiligings & compliance Center, en in Exchange Online PowerShell of standalone EOP PowerShell ([New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy) en [set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy)). Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.

## <a name="enable-disable-or-test-asf-settings"></a>ASF-instellingen in-of uitschakelen of testen

Voor elke instelling van ASF zijn de volgende opties beschikbaar in Antispambeleid:

- **Aan**: ASF voegt het bijbehorende veld van de X-header toe aan het bericht en markeert het bericht als **spam** (SCL 5 of 6 voor het verhogen van de [instellingen voor spam score](#increase-spam-score-settings)) of **hoge betrouwbaarheid van spam** (SCL 9 voor [markeren als spam instellingen](#mark-as-spam-settings)).

- **Uitgeschakeld**: de instelling ASF is uitgeschakeld. Dit is de standaardwaarde en het is raadzaam deze niet te wijzigen.

- **Test**: ASF voegt het bijbehorende veld met de X-header toe aan het bericht. Wat gebeurt er met het bericht, wordt bepaald door de waarde van de **test modus opties** (*TestModeAction*):

  - **Geen**: de bezorging van het bericht wordt niet beïnvloed door de ASF-detectie. Het bericht is nog steeds onderworpen aan andere typen filtering en regels in EOP.

  - **Standaardtekst met de x-header (*AddXHeader*) toevoegen**: de x-headerwaarde `X-CustomSpam: This message was filtered by the custom spam filter option` wordt toegevoegd aan het bericht. U kunt deze waarde gebruiken in regels voor Postvak in of de regels voor e-mail stroom (ook wel een transportregel genoemd) om de bezorging van het bericht te beïnvloeden.

  - **BCC-bericht verzenden (*BccMessage*)**: de opgegeven e-mailadressen (de *TestModeBccToRecipients* -parameterwaarde in PowerShell) worden toegevoegd aan het veld BCC van het bericht en het bericht wordt bezorgd bij de extra BCC-geadresseerden. U scheidt meerdere e-mailadressen in het nalevings centrum van de beveiligings & door puntkomma's (;). In PowerShell scheidt u meerdere e-mailadressen met komma's.

  **Opmerkingen**:

  - De test modus is niet beschikbaar voor de volgende ASF-instellingen:

    - **Filteren van voorwaardelijke Sender-ID: harde fout** (*MarkAsSpamFromAddressAuthFail*)
    - **Ndr's Backscatter**(*MarkAsSpamNdrBackscatter*)
    - **SPF-record: vast failed** (*MarkAsSpamSpfRecordHardFail*)

  - De actie op de testmodus wordt toegepast op *alle* ASF-instellingen die zijn ingesteld om te worden **getest**. U kunt verschillende stappen voor de testmodus niet configureren voor verschillende ASF-instellingen.

## <a name="increase-spam-score-settings"></a>Instellingen voor de spam score verhogen

Met de volgende ASF-instellingen wordt het betrouwbaarheidsniveau (SCL) van gevonden berichten ingesteld op 5 of 6, dat overeenkomt met het **spam** filter verdict en de bijbehorende actie in antispambeleid.

****

|Beleidsinstelling voor anti spam beleid|Beschrijving|Toegevoegde X-koptekst|
|---|---|---|
|**Afbeeldingskoppelingen naar externe sites** <br/><br/> *IncreaseScoreWithImageLinks*|Berichten met `<Img>` HTML-code koppelingen naar externe sites (bijvoorbeeld http gebruiken) worden als spam gemarkeerd.|`X-CustomSpam: Image links to remote sites`|
|**URL-omleiding naar andere poort** <br/><br/> *IncreaseScoreWithRedirectToOtherPort*|Bericht met hyperlinks die verwijzen naar andere TCP-poorten dan 80 (HTTP), 8080 (alternatief HTTP) of 443 (HTTPS) als spam worden gemarkeerd.|`X-CustomSpam: URL redirect to other port`|
|**Het numerieke IP-adres in de URL** <br/><br/> *IncreaseScoreWithNumericIps*|Berichten die numerieke Url's (doorgaans IP-adressen) bevatten, zijn gemarkeerd als spam.|`X-CustomSpam: Numeric IP in URL`|
|**URL naar. info-of. info-websites** <br/><br/> *IncreaseScoreWithBizOrInfoUrls*|Berichten met `.biz` `.info` een koppeling in de hoofdtekst van het bericht zijn gemarkeerd als spam.|`X-CustomSpam: URL to .biz or .info websites`|
|

## <a name="mark-as-spam-settings"></a>Instellingen voor spam markeren

Met de volgende ASF-instellingen wordt de SCL met gevonden berichten ingesteld op 9, wat overeenkomt met het filter verdict voor **hoge betrouwbaarheid** en de bijbehorende actie in antispambeleid.

****

|Beleidsinstelling voor anti spam beleid|Beschrijving|Toegevoegde X-koptekst|
|---|---|---|
|**Lege berichten** <br/><br/> *MarkAsSpamEmptyMessages*|Berichten zonder onderwerp, geen inhoud in de berichttekst en geen bijlagen zijn gemarkeerd als spam van hoge betrouwbaarheid.|`X-CustomSpam: Empty Message`|
|**JavaScript of VBScript in HTML** <br/><br/> *MarkAsSpamJavaScriptInHtml*|Berichten die gebruikmaken van JavaScript of Visual Basic Scripting Edition in HTML, zijn gemarkeerd als spam van hoge betrouwbaarheid. <br/><br/> Deze scripttalen worden in e-mailberichten gebruikt om bepaalde acties automatisch te laten uitvoeren.|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**Tags van het kader of IFrame in HTML** <br><br/> *MarkAsSpamFramesInHtml*|Berichten met de `<frame>` `<iframe>` HTML-code worden gemarkeerd als spam van hoge betrouwbaarheid. <br/><br/> Deze tags worden in e-mailberichten gebruikt om de pagina in te delen voor het weergeven van tekst of afbeeldingen.|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**Object Tags in HTML** <br><br/> *MarkAsSpamObjectTagsInHtml*|Berichten die `<object>` HTML-code bevatten, zijn gemarkeerd als spam van hoge betrouwbaarheid. <br/><br/> Met deze tag kunnen invoegtoepassingen of toepassingen worden uitgevoerd in een HTML-venster.|`X-CustomSpam: Object tag in html`|
|**Tags insluiten in HTML** <br><br/> *MarkAsSpamEmbedTagsInHtml*|Berichten die `<embed>` HTML-code bevatten, zijn gemarkeerd als spam van hoge betrouwbaarheid. <br/><br/> Met deze tag kan verschillende soorten documenten worden ingesloten in een HTML-document, bijvoorbeeld geluiden, Video's of afbeeldingen.|`X-CustomSpam: Embed tag in html`|
|**Formulier Tags in HTML** <br><br/> *MarkAsSpamFormTagsInHtml*|Berichten die `<form>` HTML-code bevatten, zijn gemarkeerd als spam van hoge betrouwbaarheid. <br/><br/> Dit label wordt gebruikt om website formulieren te maken. Voor e-mail advertenties wordt dit label vaak opgenomen om informatie van de ontvanger te vragen.|`X-CustomSpam: Form tag in html`|
|**Web fouten in HTML** <br><br/> *MarkAsSpamWebBugsInHtml*|Een *Web-fout* (ook wel een *webbaken*genoemd) is een grafisch element (vaak zo klein als één pixel voor één pixel) dat wordt gebruikt in een e-mailbericht om te bepalen of het bericht door de geadresseerde is gelezen. <br/><br/> Berichten die web-fouten bevatten, zijn gemarkeerd als spam van hoge betrouwbaarheid. <br/><br/> U kunt ook web bugs gebruiken, maar veel van deze Invasion privacy. |`X-CustomSpam: Web bug`|
|**Gevoelige woordenlijst toepassen** <br><br/> *MarkAsSpamSensitiveWordList*|Microsoft houdt een dynamische maar niet-bewerkbare lijst met woorden die zijn gekoppeld aan mogelijk aanstootgevende berichten. <br/><br/> Berichten met woorden uit de lijst met gevoelige woorden in het onderwerp of de hoofdtekst van het bericht worden gemarkeerd als spam van hoge betrouwbaarheid.|`X-CustomSpam: Sensitive word in subject/body`|
|**SPF-record: moeilijk mislukt** <br><br/> *MarkAsSpamSpfRecordHardFail*|Berichten die zijn verzonden via een IP-adres dat niet is opgegeven in de SPF Sender Policy Framework-record (SPF Sender Policy Framework) van het bron-e-mail domein, worden gemarkeerd als spam van hoge betrouwbaarheid. <br/><br/> De test modus is niet beschikbaar voor deze instelling.|`X-CustomSpam: SPF Record Fail`|
|**Filteren van voorwaardelijke Sender-ID: moeilijk mislukt** <br><br/> *MarkAsSpamFromAddressAuthFail*|Berichten die een voorwaardelijke afzender van een voorwaardelijke Sender-ID niet hebben gecontroleerd, worden als spam gemarkeerd. <br/><br/> Met deze instelling wordt een SPF-controle gecombineerd met een afzender-ID-controle om berichten te beschermen tegen berichtkoppen die vervalste afzenders bevatten. <br/><br/> De test modus is niet beschikbaar voor deze instelling.|`X-CustomSpam: SPF From Record Fail`|
|**NDR'S Backscatter** <br><br/> *MarkAsSpamNdrBackscatter*|*Backscatter* is overbodige rapporten over niet-uitgevoerde bezorging (ook wel ndr's genoemd), veroorzaakt door vervalste afzenders in e-mailberichten. Zie [Backscatter-berichten en EOP](backscatter-messages-and-eop.md)voor meer informatie. <br/><br/> U hoeft deze instelling niet te configureren in de volgende omgevingen omdat er originele Ndr's worden afgeleverd en Backscatter is gemarkeerd als spam: <ul><li>Microsoft 365-organisaties met postvakken van Exchange Online.</li><li>On-premises e-mail organisaties waarbij u *uitgaande* e-mail omrouteeert via EOP.</li></ul><br/> In zelfstandige EOP-omgevingen die de instelling van inkomende e-mail naar on-premises postvakken beschermen, heeft dit het volgende resultaat: <ul><li> **Op**: legitieme ndr's worden afgeleverd en Backscatter is gemarkeerd als spam.</li><li>**Uit**: legitieme ndr's en Backscatter gaan normaal spam filteren. De meest legitieme Ndr's worden afgeleverd bij de oorspronkelijke afzender van het bericht. Een aantal, maar niet alle Backscatter zijn gemarkeerd als spam van hoge betrouwbaarheid. Per definitie kan Backscatter alleen worden afgeleverd bij de vervalste afzender, niet aan de oorspronkelijke afzender.</li></ul><br/> De test modus is niet beschikbaar voor deze instelling.|`X-CustomSpam: Backscatter NDR`|
|
