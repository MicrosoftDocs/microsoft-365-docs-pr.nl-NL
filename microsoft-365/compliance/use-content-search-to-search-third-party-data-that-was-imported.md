---
title: Inhoud zoeken gebruiken om geïmporteerde gegevens van derden te doorzoeken
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: Gebruik het hulpprogramma Inhoud zoeken eDiscovery om te zoeken naar items die zijn geïmporteerd in postvakken in Microsoft 365 van een externe gegevensbron door query's te maken.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 24ca63cf78b85f7b8b5181d5babd16058b641128
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/01/2020
ms.locfileid: "52161487"
---
# <a name="use-content-search-to-search-third-party-data-imported-by-a-custom-partner-connector"></a>Inhoud zoeken gebruiken om door een aangepaste partnerconnector geïmporteerde gegevens van derden te doorzoeken

U kunt het hulpprogramma Inhoud zoeken [eDiscovery](content-search.md) in het beveiligings- & compliancecentrum gebruiken om te zoeken naar items die zijn geïmporteerd in postvakken in Microsoft 365 van een externe gegevensbron. U kunt een query maken om alle geïmporteerde gegevensitems van derden te doorzoeken of u kunt een query maken om specifieke gegevensitems van derden te doorzoeken. U kunt ook een bewaarbeleid op basis van query's of een eDiscovery-bewaring op basis van query's maken om gegevens van derden te behouden.
  
Zie Werken met een partner om gegevens van derden te archiveren in Office 365 voor meer informatie over het werken met een partner om gegevens van derden te importeren en een lijst met de gegevenstypen van derden die u kunt importeren [in](work-with-partner-to-archive-third-party-data.md)Microsoft 365.

> [!IMPORTANT]
> De richtlijnen in dit artikel zijn alleen van toepassing op gegevens van derden die zijn geïmporteerd door een aangepaste partnerconnector. Dit artikel is niet van toepassing op gegevens van derden die worden geïmporteerd met behulp van de gegevensconnectoren van derden in het [Microsoft-compliancecentrum.](archiving-third-party-data.md#third-party-data-connectors)
  
## <a name="creating-a-query-to-search-all-third-party-data"></a>Een query maken om alle gegevens van derden te doorzoeken

Als u elk type gegevens van derden wilt doorzoeken (of in de wacht wilt zetten) dat u hebt geïmporteerd in Office 365, kunt u het eigenschap-waardepaar bericht gebruiken in het trefwoordvak voor een inhoudszoekactie of bij het maken van een op query's gebaseerde `kind:externaldata` hold. Als u bijvoorbeeld wilt zoeken naar items die zijn geïmporteerd uit een externe gegevensbron en het woord 'contoso' in de eigenschap Onderwerp van het geïmporteerde item wilt bevatten, gebruikt u de volgende query: 
  
```powershell
kind:externaldata AND subject:contoso
```

Het vorige trefwoordqueryvoorbeeld bevat de eigenschap onderwerp. Zie de sectie Meer informatie in Samenwerken met een partner om gegevens van derden te archiveren in Office 365 voor een lijst met andere eigenschappen voor gegevensitems van derden die kunnen worden opgenomen in een [trefwoordquery.](work-with-partner-to-archive-third-party-data.md#more-information)
  
Wanneer u query's maakt om gegevens van derden te doorzoeken en vast te houden, kunt u ook voorwaarden gebruiken om de zoekresultaten te beperken. Zie Trefwoordenquery's en zoekvoorwaarden voor Inhoud zoeken voor meer informatie over het maken van [inhoudszoekquery's.](keyword-queries-and-search-conditions.md)
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a>Een query maken om specifieke typen gegevens van derden te doorzoeken

In plaats van alle typen gegevens van derden te doorzoeken, kunt u query's maken die alleen zoeken naar een opgegeven type gegevens van derden met behulp van de volgende bericht *eigenschap:* waardepaar in het trefwoordvak voor een inhoudszoekactie:
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

Als u bijvoorbeeld wilt zoeken in Facebook-gegevens met het woord 'contoso' in de eigenschap Onderwerp, gebruikt u de volgende query:
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

De volgende tabel bevat de gegevenstypen van derden die u kunt zoeken en de waarde die u kunt gebruiken voor de eigenschap bericht om specifiek te zoeken naar dat type gegevens  `itemclass:` van derden. De syntaxis van de query is niet case-sensitive. 
  
|**Gegevenstype van derden**|**Waarde voor  `itemclass:` eigenschap**|
|:-----|:-----|
|AIM  <br/> | `ipm.externaldata.AIM*` <br/> |
|American Idool  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|AOL met draaitabelclient  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|Appelsap  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|Ares  <br/> | `ipm.externaldata.Ares*` <br/> |
|Axs Encrypted  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|Axs Exchange  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|Axs Local Archive  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|Tijdelijke aanduiding Axs  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|Axs Signed  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|Bazarvoice  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|Bearshare  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|BitTorrent  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|Blackberry  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|BlackBerry-oproeplogboeken  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|BlackBerry Messenger  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|BlackBerry-pincode  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|BlackBerry Sms  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|Bloomberg  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|Bloomberg-bericht  <br/> | `ipm.externaldata.conversation.Bloomberg Message*` <br/> |
|Berichten van Bloomberg  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|Vak  <br/> | `ipm.externaldata.Box*` <br/> |
|Cisco IM &amp; Presence Server  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|Cisco Jabber  <br/> | `ipm.externaldata.Jabber*` <br/> |
|CipherCloud voor Salesforce Chatter  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|Directe Verbinding maken  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|Facebook  <br/> | `ipm.externaldata.Facebook*` <br/> |
|FastTrack  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|FXConnect  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|Flickr  <br/> | `ipm.externaldata.Flickr*` <br/> |
|Gnutella  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|Google+  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|Google Talk  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|GoToMyPC  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|HipChat  <br/> | `ipm.externaldata.HipChat*` <br/> |
|Hopster  <br/> | `ipm.externaldata.Hopster*` <br/> |
|HubConnex  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|IBM Connections  <br/> | `ipm.externaldata.Connections*` <br/> |
|IBM SameTime  <br/> | `ipm.externaldata.Sametime*` <br/> |
|ICE Chat  <br/> | `ipm.externaldata.conversation.Ice Chat*` <br/> |
|Indii Messenger  <br/> | `ipm.externaldata.Indii*` <br/> |
|Instagram  <br/> | `ipm.externaldata.Instagram*` <br/> |
|Instant Bloomberg  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|InvestEdge  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|IRC  <br/> | `ipm.externaldata.IRC*` <br/> |
|Jive  <br/> | `ipm.externaldata.Jive*` <br/> |
|JiveApiRetention  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|JXTA  <br/> | `ipm.externaldata.JXTA*` <br/> |
|LinkedIn  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|MFTP  <br/> | `ipm.externaldata.MFTP*` <br/> |
|Microsoft UC  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|Mind Align  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|Mobiele beveiliging  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|MSN  <br/> | `ipm.externaldata.MSN*` <br/> |
|MySpace  <br/> | `ipm.externaldata.MySpace*` <br/> |
|NEONetwork  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|OpenNap  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|Pinterest  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|Pivot  <br/> | `ipm.externaldata.Pivot*` <br/> |
|QQ  <br/> | `ipm.externaldata.QQ*` <br/> |
|Microsoft SharePoint  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|Salesforce Chatter  <br/> | `ipm.externaldata.Chatter*` <br/> |
|Skype voor Bedrijven  <br/> | `ipm.externaldata.Skype*` <br/> |
|Slack Enterprise Grid  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|SoftEther  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|Squawker  <br/> | `ipm.externaldata.Squawker*` <br/> |
|Symphony  <br/> | `ipm.externaldata.Symphony*` <br/> |
|Thomson Reuters  <br/> | `ipm.externaldata.Reuters*` <br/> |
| Thomson Reuters Eikon Messenger  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|Tor  <br/> | `ipm.externaldata.Tor*` <br/> |
|TTT  <br/> | `ipm.externaldata.TTT*` <br/> |
|Twitter  <br/> | `ipm.externaldata.Twitter*` <br/> |
|UBS-chat  <br/> | `ipm.externaldata.UBS*` <br/> |
|Vimeo  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|WinMX  <br/> | `ipm.externaldata.WinMX*` <br/> |
|Winny  <br/> | `ipm.externaldata.Winny*` <br/> |
|Yahoo!  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|Yammer  <br/> | `ipm.externaldata.Yammer*` <br/> |
|YellowJacket  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|YouTube  <br/> | `ipm.externaldata.YouTube*` <br/> |
