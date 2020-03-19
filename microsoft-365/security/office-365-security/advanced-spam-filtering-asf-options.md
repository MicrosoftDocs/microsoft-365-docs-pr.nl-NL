---
title: Geavanceerde opties voor spamfilter
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/09/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b286f853-b484-4af0-b01f-281fffd85e7a
ms.collection:
- M365-security-compliance
description: Geavanceerde opties voor spamfiltering bieden beheerders de mogelijkheid om verschillende inhoudskenmerken van een bericht te inspecteren. De aanwezigheid van deze kenmerken in een bericht verhoogt ofwel de spamscore van het bericht (waardoor het potentieel voor het als spam wordt geïdentificeerd) toeneemt of het bericht als spam markeert. De ASF-opties richten zich op specifieke berichteigenschappen, zoals HTML-tags en URL-omleiding, die vaak worden gevonden in spamberichten.
ms.openlocfilehash: 07f2b32dac6ba4a04fbccac5f015be399f62e254
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42810435"
---
# <a name="advanced-spam-filtering-options"></a>Geavanceerde opties voor spamfilter

> [!NOTE]
> De instellingen voor geavanceerd spamfilter van het antispambeleid worden momenteel afgeschaft. Onze aanbevolen instellingen voor deze zijn om ze **uit**te schakelen. De functies die beschikbaar waren in het filter Geavanceerd spam worden opgenomen in andere delen van de filterstack.

Geavanceerde opties voor spamfiltering bieden beheerders de mogelijkheid om verschillende inhoudskenmerken van een bericht te inspecteren. De aanwezigheid van deze kenmerken in een bericht verhoogt ofwel de spamscore van het bericht (waardoor het potentieel voor het als spam wordt geïdentificeerd) toeneemt of het bericht als spam markeert. De ASF-opties richten zich op specifieke berichteigenschappen, zoals HTML-tags en URL-omleiding, die vaak worden gevonden in spamberichten.
  
Het inschakelen van AsF-opties is een agressieve benadering van spamfiltering en berichten die door deze opties worden gefilterd, kunnen niet worden gerapporteerd als false positives. Deze berichten kunnen worden geïdentificeerd door middel van periodieke spammeldingen van eindgebruikers en worden geborgen uit de spamquarantaine. Ze kunnen ook worden geïdentificeerd via de X-header tekst die specifiek is voor elke ASF-optie en die wordt weergegeven in de internetheader van berichten waar een AsF-optie is gekoppeld. Zie [Kopteksten voor spamberichten](anti-spam-message-headers.md)voor meer informatie.
  
Asf-opties kunnen worden ingesteld in-, uit- of testmodus wanneer u het beleid voor inhoudsfilter bewerkt. Zie [Uw spamfilterbeleid configureren](configure-your-spam-filter-policies.md)voor meer informatie. Testmodus is niet beschikbaar voor de **NDR backscatter,** **SPF record: hard fail,** **Conditional Sender ID filtering: hard fail**en Bulk **mail** opties. 
  
In de volgende tabel wordt elke geavanceerde filteroptie voor spam beschreven.
  
||||
|:-----|:-----|:-----|
|**Geavanceerde optie voor spamfilter** <br/> |**Beschrijving** <br/> |**Tekst met X-koptekst** <br/> |
|**Sectie Spamscore verhogen** <br/> |Wanneer ingeschakeld, deze opties stelt de spam vertrouwen niveau (SCL) van een overeenkomend bericht op 5 of 6, die wordt beschouwd als vermoedelijke spam. De actie die op het bericht wordt uitgevoerd, komt overeen met de **instelling Spam** in uw beleid voor inhoudsfilter.  <br/> ||
|Afbeeldingskoppelingen naar externe sites  <br/> |Wanneer deze instelling is ingeschakeld, ontvangt elk bericht met HTML-inhoud met een IMG-tag die op afstand wordt gekoppeld (bijvoorbeeld via http) een verhoogde spamscore.  <br/> |X-CustomSpam: Afbeeldingskoppelingen naar externe sites  <br/> |
|Numeriek IP-adres in URL  <br/> |Wanneer deze instelling is ingeschakeld, ontvangt elk bericht met url's op basis van numerieke gegevens (meestal in de vorm van een IP-adres) een verhoogde spamscore.  <br/> |X-CustomSpam: Numeriek IP in URL  <br/> |
|URL-omleiding naar andere poort  <br/> |Wanneer deze instelling is ingeschakeld, ontvangt elk bericht met een hyperlink die de gebruiker doorverwijst naar andere poorten dan poort 80 (reguliere HTTP-protocolpoort), 8080 (HTTP-alternatieve poort) of 443 (HTTPS-poort) een verhoogde spamscore.  <br/> |X-CustomSpam: URL-omleiding naar andere poort  <br/> |
|URL naar .biz- of .info-websites  <br/> |Wanneer deze instelling is ingeschakeld, ontvangt elk bericht met een .biz- of .info-extensie in de hoofdtekst van een bericht een verhoogde spamscore.  <br/> |X-CustomSpam: URL naar .biz- of .info-websites  <br/> |
|**Markeren als spamsectie** <br/> |Wanneer ingeschakeld, deze opties stelt de spam vertrouwen niveau (SCL) van een overeenkomend bericht op 9, die wordt beschouwd als bepaalde spam. De actie die op het bericht wordt uitgevoerd, komt overeen met de **instelling Hoog vertrouwen** spam in uw inhoudsfilterbeleid.  <br/> ||
|Lege berichten  <br/> |Wanneer deze instelling is ingeschakeld, wordt elk bericht waarin het lichaam en de onderwerpregel zowel leeg zijn als zonder bijlage, gemarkeerd als spam.  <br/> |X-CustomSpam: leeg bericht  <br/> |
|JavaScript of VBScript in HTML  <br/> |Wanneer deze instelling is ingeschakeld, wordt elk bericht dat JavaScript of Visual Basic Script Edition in HTML gebruikt, gemarkeerd als spam. Beide scripttalen worden gebruikt in een HTML-bericht om automatisch een specifieke actie te laten optreden. De browser zal ontsmet en verwerken van het script samen met de rest van het document.  <br/> |X-CustomSpam: Javascript- of VBscript-tags in HTML  <br/> |
|Frame- of IFrame-tags in HTML  <br/> |Wanneer deze instelling is ingeschakeld, wordt \<\> elk \<bericht\> met de HTML-tag Frame of IFrame gemarkeerd als spam. Deze tags worden gebruikt op websites of in HTML-berichten om de pagina op te maken voor het weergeven van tekst of afbeeldingen.  <br/> |X-CustomSpam: IFRAME of FRAME in HTML  <br/> |
|Objecttags in HTML  <br/> |Wanneer deze instelling is ingeschakeld, wordt \<\> elk bericht met de HTML-tag Object gemarkeerd als spam. Met deze HTML-tag kunnen plug-ins of toepassingen worden uitgevoerd in een HTML-venster.  <br/> |X-CustomSpam: Objecttag in html  <br/> |
|Tags insluiten in HTML  <br/> |Wanneer deze instelling is ingeschakeld, wordt \<\> elk bericht met de HTML-tag insluiten gemarkeerd als spam. Met deze HTML-tag kunnen verschillende soorten documenten van verschillende gegevenstypen worden ingesloten in een HTML-document. Voorbeelden hiervan zijn geluiden, films of foto's.  <br/> |X-CustomSpam: Tag insluiten in html  <br/> |
|Formuliertags in HTML  <br/> |Wanneer deze instelling is ingeschakeld, wordt \<\> elk bericht met de HTML-tag formulier gemarkeerd als spam. Deze HTML-tag wordt gebruikt om websiteformulieren te maken. E-mailadvertenties bevatten vaak deze tag om informatie van de ontvanger te vragen.  <br/> |X-CustomSpam: formuliertag in html  <br/> |
|Webbugs in HTML  <br/> |Wanneer deze instelling is ingeschakeld, wordt elk bericht met een webbug gemarkeerd als spam. Een webbug is een afbeelding die is ontworpen om te bepalen of een webpagina of e-mailbericht is gelezen. Webbugs zijn vaak onzichtbaar voor de ontvanger omdat ze meestal worden toegevoegd aan een bericht als een afbeelding die zo klein is als één pixel per pixel. Legitieme nieuwsbrieven kunnen ook gebruik maken van deze techniek, hoewel velen beschouwen dit als een inbreuk op de privacy.  <br/> |X-CustomSpam: Webbug  <br/> |
|Lijst met gevoelige woorden toepassen  <br/> |Wanneer deze instelling is ingeschakeld, wordt elk bericht met een woord uit de lijst met gevoelige woorden gemarkeerd als spam. Met behulp van de gevoelige woordenlijst u eenvoudig blokkeren van woorden die zijn gekoppeld aan mogelijk aanstootgevende berichten. Sommige van deze woorden zijn gevoelig voor de zaak. Als beheerder u deze lijst niet bewerken. Filteren op de lijst met gevoelige woorden wordt toegepast op zowel de onderwerp- als de berichttekst van een bericht.  <br/> |X-CustomSpam: Gevoelig woord in onderwerp/lichaam  <br/> |
|SPF-record: harde fail|Wanneer deze instelling is ingeschakeld, worden berichten die niet voldoen aan een SPF-controle (wat betekent dat ze zijn verzonden vanaf een IP-adres dat niet is opgegeven in de SPF-record) gemarkeerd als spam. Het inschakelen van deze instelling wordt aanbevolen voor organisaties die zich zorgen maken over het ontvangen van phishingberichten.  <br/> <br/> Testmodus is niet beschikbaar voor deze optie.  <br/> |X-CustomSpam: SPF Record Fail  <br/> |
|Voorwaardelijke sender ID-filtering: hard mislukt  <br/> |Wanneer deze instelling is ingeschakeld, wordt elk bericht dat hard mislukt een voorwaardelijke controle van de afzender-id gemarkeerd als spam. Deze optie combineert een SPF-controle met een Sender ID-controle om te beschermen tegen berichtkoppen die vervalste afzenders bevatten.  <br/> <br/> Testmodus is niet beschikbaar voor deze optie.  <br/> |X-CustomSpam: SPF van Record Fail  <br/> |
|NDR backscatter  <br/> |Als u EOP gebruikt om on-premises postvakken te beschermen, worden alle legitieme NDR-berichten (non-delivery report) bij het inschakelen van lokale postvakken als spam gemarkeerd. Als u deze instelling niet inschakelt, gaan alle NDR's nog steeds door spamfiltering. In dit geval worden de meeste legitieme berichten geleverd aan de oorspronkelijke afzender, terwijl sommige, maar niet alle, backscatter-berichten worden gemarkeerd als spam. Backscatter-berichten die niet zijn gemarkeerd als spam, gaan echter niet naar de oorspronkelijke afzender omdat deze naar de vervalste afzender gaat. <br/> <br/> Als u de service gebruikt om door Exchange Online gehoste postvakken te beschermen, hoeft u deze instelling niet te configureren.  <br/><br/> Voor beide scenario's (on-premises en cloudgehoste postvakken) is het ook niet nodig om deze instelling in te schakelen voor uitgaande e-mail die via de service wordt verzonden, omdat NDR's die legitieme bounceberichten zijn, automatisch worden gedetecteerd en geleverd aan de oorspronkelijke afzender . > Testmodus is niet beschikbaar voor deze optie.           <br/><br/>TIP: Zie [Backscatter-berichten en EOP](backscatter-messages-and-eop.md)voor meer informatie over backscatterberichten en EOP.           |X-CustomSpam: Backscatter NDR  <br/> |
|Bulkpost|Geavanceerde spam filtering van bulk e-mail is gestopt en vervangen door de bulk en e-mail drempel instellingen. Bekijk [wat is het verschil tussen ongewenste e-mail en bulke-mail?](what-s-the-difference-between-junk-email-and-bulk-email.md) en [Uw spamfilterbeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie en hoe u de instellingen configureert.|X-CustomSpam: Bulk Mail | Bulkmail  <br/> |
|
