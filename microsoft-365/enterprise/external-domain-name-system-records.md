---
title: Externe DNS-records (Domain Name System) voor Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/21/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0
description: Een lijst met externe DNS-records die moeten worden gebruikt bij de planning van een Office 365-implementatie.
ms.openlocfilehash: da5a9a1095e50de779ee2fc148803e31583426a2
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689492"
---
# <a name="external-domain-name-system-records-for-office-365"></a>Externe DNS-records (Domain Name System) voor Office 365

|||
|:-----|:-----|
|![Domein](../media/e05b1c78-1df0-4200-ba40-6e26b7ead68f.png)|**Wilt u een aangepaste lijst met DNS-records voor uw Office 365-organisatie zien?** U kunt de [informatie die u nodig hebt voor het maken van DNS-records](https://support.office.microsoft.com/article/Gather-the-information-you-need-to-create-Office-365-DNS-records-77f90d4a-dc7f-4f09-8972-c1b03ea85a67) in Office 365 voor uw domein vinden in Office 365.  <br/> **Stapsgewijze instructies nodig om deze records toe te voegen aan de DNS-host van uw domein, zoals GoDaddy of eNom?** [Hier vindt u koppelingen naar stapsgewijze instructies voor veel populaire DNS-hosts](https://go.microsoft.com/fwlink/?LinkId=286745). <br/>  **Blijf u hier om de verwijzingenlijst voor uw eigen aangepaste implementatie te gebruiken?** Gebruik de onderstaande lijst als verwijzing voor uw aangepaste implementatie van Office 365. U moet de records selecteren die betrekking hebben op uw organisatie en de juiste waarden invullen. <br/> **Ga terug naar **[Netwerkplanning en prestaties optimaliseren voor Office 365](https://aka.ms/tune).  <br/> |

De SPF-en MX-records zijn vaak het moeilijkst te vinden. Aan het eind van dit artikel zijn onze SPF-record richtlijnen bijgewerkt. Het is belangrijk om te onthouden dat _u slechts één SPF-record voor uw domein hebt_. U kunt meerdere MX-records hebben, maar dat kan problemen veroorzaken bij het afleveren van e-mail. Met een enkel MX-record waarmee e-mail naar een e-mailsysteem wordt omgeleid, worden veel van deze potentiële problemen weggenomen.
  
De volgende secties zijn ingedeeld op service in Office 365. Wilt u een aangepaste lijst met Office 365 DNS-records voor uw domein zien? Meldt u aan bij Office 365 en [verzamel de informatie die u nodig hebt voor het maken van Office 365 DNS-records](https://support.office.com/article/77f90d4a-dc7f-4f09-8972-c1b03ea85a67).
  
## <a name="external-dns-records-required-for-office-365-core-services"></a>Externe DNS-records vereist voor Office 365 (kernservices)
<a name="BKMK_ReqdCore"> </a>

Elke Office 365-klant moet twee records toevoegen aan de externe DNS. De eerste CNAME-record zorgt ervoor dat Office 365 werkstations voor verificatie naar het juiste identiteitsplatform kan verwijzen. De tweede vereiste record is om te bewijzen u de eigenaar bent van de domeinnaam.
  
||||
|:-----|:-----|:-----|
|**DNS-record** <br/> |**Doel** <br/> |**Te gebruiken waarde** <br/> |
|**CNAME** <br/> **(Suite)** <br/> |Gebruikt door Office 365 om verificatie te verwijzen naar het juiste identiteitsplatform. [Meer informatie](https://go.microsoft.com/fwlink/p/?LinkId=322005) <br/> **Opmerking:** Deze CNAME is alleen van toepassing op Office 365 beheerd door 21Vianet. [Meer informatie](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-operated-by-21vianet)  |**Alias:** msoid  <br/> **Target:** clientconfig.partner.microsoftonline-p.net.cn  <br/> |
|**TXT** <br/> **(Domeinverificatie)** <br/> |Wordt gebruikt door Office 365 om alleen te verifiëren dat u de eigenaar bent van uw domein. Het heeft verder nergens invloed op.  <br/> |**Host:** @ (of, voor bepaalde DNS-hostingproviders, uw domeinnaam)  <br/> **TXT-waarde:** _een tekenreeks die door_ Office 365 geleverd wordt  <br/> De wizard ** Office 365 Domeininstallatie** levert de waarden die u gebruikt om deze record te maken.   <br/> |


## <a name="external-dns-records-required-for-email-in-office-365-exchange-online"></a>Externe DNS-records vereist voor e-mail in Office 365 (Exchange Online)
<a name="BKMK_ReqdCore"> </a>

E-mail in Office 365 vereist verschillende records. De drie primaire records die alle klanten moeten gebruiken, zijn de Automatisch opsporen-, MX- en SPF-records.
  
- De **Automatisch opsporen-record** zorgt dat clientcomputers Exchange Online automatisch kunnen vinden en de client correct configureren.

- Met een **MX-record** wordt aan andere e-mailsystemen doorgegeven waar e-mail voor uw domein naartoe moet worden verzonden. **Opmerking:** Wanneer u uw e-mailadres overzet naar Office 365 door de MX-record van uw domein bij te werken, komt alle e-mail die naar dat domein wordt verzonden binnen in Office 365.  
Wilt u slechts een paar e-mailadressen overbrengen naar Office 365? U kunt [Office 365 testen met een paar e-mailadressen in uw aangepaste domein](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7).

- De **TXT-record voor SPF** wordt gebruikt door de ontvangende e-mailsystemen om te verifiëren dat de server die uw e-mailadres verzendt, de server is die u goedkeurt. Dit helpt problemen zoals e-mailspoofing en phishing te voorkomen. Zie de [externe DNS-records die zijn vereist voor SPF-](external-domain-name-system-records.md#BKMK_SPFrecords) in dit artikel voor meer informatie over wat u in de record moet opnemen.

E-mailklanten die van Exchange-federatie gebruikmaken, hebben ook de extra CNAME- en TXT-records nodig die onder aan de tabel worden vermeld.
  
||||
|:-----|:-----|:-----|
|**DNS-record** <br/> |**Doel** <br/> |**Te gebruiken waarde** <br/> |
|**CNAME** <br/> **(Exchange Online)** <br/> |Helpt Outlook-clients gemakkelijk verbinding maken met de Exchange Online-service via de Automatisch opsporen-service. Automatisch opsporen zoekt automatisch naar de juiste Exchange Server-host en configureert Outlook voor gebruikers.  <br/> |**Alias:** Autodiscover  <br/> **Doel:** autodiscover.outlook.com  <br/> |
|**MX** <br/> **(Exchange Online)** <br/> |Verzendt inkomende e-mail voor uw domein naar de Exchange Online-service in Office 365.  <br/> [!NOTE] Wanneer e-mail eenmaal naar Exchange Online gaat, verwijdert u de MX-records die naar uw oude systeem verwijzen.   |**Domein:** Bijvoorbeeld contoso.com  <br/> **Target email server:**\<MX token\>.mail.protection.outlook.com  <br/> **Voorkeur/prioriteit:** lager dan de andere MX-records (dit zorgt ervoor dat e-mail wordt afgeleverd bij Exchange Online), bijvoorbeeld 1 of 'laag'  <br/>  Vindt uw \<MX token\>door deze stappen uit te voeren:  <br/>  Meld u aan bij Office 365 en ga naar Office 365-beheerder \> domeinen.  <br/>  Kies Problemen oplossen in de kolom Actie voor uw domein.  <br/>  Kies Wat kan ik oplossen? in de sectie MX-records.  <br/>  Volg de aanwijzingen op deze pagina om uw MX-record bij te werken.  <br/> [Wat is MX-prioriteit?](https://go.microsoft.com/fwlink/p/?LinkId=396471) <br/> |
|**SPF (TXT)** <br/> **(Exchange Online)**  <br/> |Helpt voorkomen dat anderen uw domein gebruiken om spam of andere schadelijke e-mail te verzenden. Met SPF-records (Sender Policy Framework) worden de servers geïdentificeerd die zijn geautoriseerd om e-mail te verzenden vanaf uw domein.  <br/> |[Externe DNS-records vereist voor SPF](external-domain-name-system-records.md#BKMK_SPFrecords) <br/> |
|**TXT** <br/> **(Exchange-Federatie)** <br/> |Wordt gebruikt voor Exchange-federatie voor hybride implementatie.  <br/> |**TXT-record 1:** Bijvoorbeeld contoso.com en bijbehorende, speciaal gegenereerde hash-tekst voor domeinvalidatie (bijvoorbeeld Y96nu89138789315669824)  <br/> **TXT-record 2:** Bijvoorbeeld exchangedelegation.contoso.com en bijbehorende, speciaal gegenereerde hash-tekst voor domeinvalidatie (bijvoorbeeld Y3259071352452626169)  <br/> |
|**CNAME** <br/> **(Exchange-Federatie)** <br/> |Helpt Outlook-clients gemakkelijk verbinding maken met de Exchange Online-service via de Automatisch opsporen-service wanneer uw bedrijf Exchange-federatie gebruikt. Automatisch opsporen zoekt automatisch naar de juiste Exchange Server-host en configureert Outlook voor uw gebruikers.  <br/> |**Alias:** Bijvoorbeeld Autodiscover.service.contoso.com  <br/> **Doel:** autodiscover.outlook.com  <br/> |


## <a name="external-dns-records-required-for-skype-for-business-online"></a>Externe DNS-records vereist voor Skype voor Bedrijven Online
<a name="BKMK_ReqdCore"> </a>

Er zijn specifieke stappen die u moet uitvoeren wanneer u [Office 365-URL's en IP-adresbereiken](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO) gebruikt om er zeker van te zijn dat uw netwerk correct is geconfigureerd.

> [!NOTE]
> Deze DNS-records zijn ook van toepassing op Teams, met name in een scenario met hybride Teams en een Skype voor bedrijven-scenario waarin bepaalde Federatie-zaken zich kunnen voordoen.
  
||||
|:-----|:-----|:-----|
|**DNS-record** <br/> |**Doel** <br/> |**Te gebruiken waarde** <br/> |
|**SRV** <br/> **Skype voor Bedrijven Online** <br/> |Zorgt dat uw Office 365-domein functionaliteit voor chatberichten (IM) met externe clients kan delen door SIP-federatie in te schakelen. Zie [URL's en IP-adresbereiken voor Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO) voor meer informatie.  <br/> |**Service:** sipfederationtls  <br/> **Protocol:** TCP  <br/> **Prioriteit:** 100  <br/> **Gewicht:** 1  <br/> **Poort:** 5061  <br/> **Target:** sipfed.online.lync.com  <br/> **Opmerking:** Als SRV-opzoekacties op een externe DNS door de firewall of proxyserver worden geblokkeerd, moet u deze record aan de interne DNS-record toevoegen.    |
|**SRV** <br/> **Skype voor Bedrijven Online** <br/> |Wordt gebruikt door Skype voor Bedrijven om de informatiestroom tussen Lync-clients te coördineren.  <br/> |**Service:** sip  <br/> **Protocol:** TLS  <br/> **Prioriteit:** 100  <br/> **Gewicht:** 1  <br/> **Poort:** 443  <br/> **Target:** sipdir.online.lync.com  <br/> |
|**CNAME** <br/> **Skype voor Bedrijven Online** <br/> |Wordt gebruikt door de Lync-client om de Skype voor Bedrijven Online-service te helpen vinden en aan te melden.  <br/> |**Alias:** sip  <br/> **Target:** sipdir.online.lync.com  <br/> Zie [URL's en IP-adresbereiken voor Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO) voor meer informatie.  <br/> |
|**CNAME** <br/> **Skype voor Bedrijven Online** <br/> |Wordt gebruikt door de Lync-mobile client om de Skype voor Bedrijven Online-service te helpen vinden en aan te melden.  <br/> |**Alias:** lyncdiscover  <br/> **Target:** webdir.online.lync.com  <br/> |

## <a name="external-dns-records-required-for-office-365-single-sign-on"></a>Externe DNS-records vereist voor Office 365 SSO (Single Sign-On)
<a name="BKMK_ReqdCore"> </a>

||||
|:-----|:-----|:-----|
|**DNS-record** <br/> |**Doel** <br/> |**Te gebruiken waarde** <br/> |
|**Host (A)** <br/> |Wordt gebruikt voor eenmalige aanmelding (SSO). Deze fungeert als eindpunt voor uw externe gebruikers (en on-premises gebruikers, indien gewenst) om verbinding te maken met uw Active Directory Federation Services (AD FS) -federatieserverproxy's of virtuele IP (VIP) met gelijke taakverdeling.  <br/> |**Target:** Bijvoorbeeld sts.contoso.com  <br/> |

## <a name="external-dns-records-required-for-spf"></a>Externe DNS-records vereist voor SPF
<a name="BKMK_SPFrecords"> </a>

> [!IMPORTANT]
> SPF is ontworpen om spoofing te voorkomen, maar er zijn spoofing-technieken waartegen SPF geen bescherming kan bieden. Om u tegen deze technieken te beschermen, moet u, nadat u SPF hebt geconfigureerd, ook DKIM en DMARC voor Office 365 configureren. Raadpleeg [DKIM gebruiken om uitgaande e-mail te valideren die wordt verzonden vanaf uw domein in Office 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx). Zie vervolgens [DMARC gebruiken om e-mail in Office 365 te valideren](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).
  
SPF-records die helpen voorkomen dat anderen uw domein gebruiken om spam of andere schadelijke e-mail te verzenden. Met SPF-records (Sender Policy Framework) worden de servers geïdentificeerd die zijn geautoriseerd om e-mail te verzenden vanaf uw domein.
  
U kunt slechts één SPF-record hebben voor uw domein (dat wil zeggen, een TXT-record die SPF definieert). Die ene record kan verschillende andere opnamen hebben, maar het totale resultaat van de DNS-zoekopdrachten kan niet meer dan 10 zijn (dit helpt Denial of Service-aanvallen voorkomen). Zie de tabel en andere voorbeelden hieronder om u te helpen de juiste SPF-recordwaarden voor uw omgeving te maken of bij te werken.
  
### <a name="structure-of-an-spf-record"></a>Structuur van een SPF-record

Alle SPF-records bevatten drie onderdelen: de declaratie dat het een SPF-record is, de domeinen en IP-adressen die e-mail moeten verzenden en een regel voor het afdwingen. U hebt alle drie nodig in een geldig SPF-record. Hier volgt een voorbeeld van een algemene SPF-record voor Office 365 wanneer u alleen e-mail van Exchange Online gebruikt:
  
``` dns
TXT Name @
Values: v=spf1 include:spf.protection.outlook.com -all
```

Een e-mailsysteem dat een e-mailbericht vanaf uw domein ontvangt, bekijkt de SPF-record en als de e-mailserver die het bericht heeft verzonden een Office 365-server is, wordt het bericht geaccepteerd. Als de server die het bericht heeft verzonden, het oude e-mailsysteem of een schadelijk systeem op Internet is, de SPF-controle kan bijvoorbeeld mislukken en het bericht wordt niet afgeleverd. Hiermee wordt gecontroleerd om vervalsing en phishingberichten te voorkomen.
  
### <a name="choose-the-spf-record-structure-you-need"></a>Kies de SPF-recordstructuur die u nodig hebt

Voor scenario's waarin u niet alleen werkt met Exchange Online-e-mail voor Office 365 (bijvoorbeeld wanneer u ook e-mail gebruikt die afkomstig is van SharePoint Online), gebruikt u de volgende tabel om te bepalen wat u wilt opnemen in de waarde van de record.
  
> [!NOTE]
> Als u een ingewikkeld scenario hebt met bijvoorbeeld edge-mailservers voor het beheren van e-mailverkeer door uw firewall, moet u een meer gedetailleerde SPF-record instellen. Leer hoe: [SPF records instellen in Office 365 om vervalsing te helpen voorkomen](https://go.microsoft.com/fwlink/?LinkId=787656). In [How Office 365 uses Sender Policy Framework (SPF) to help prevent spoofing](https://go.microsoft.com/fwlink/?LinkId=787065) (Hoe Office 365 SPF (Sender Policy Framework) gebruikt om vervalsing te helpen voorkomen) kunt u ook veel meer informatie vinden over hoe SPF met Office 365 werkt.
  
| Nummer|Als u werkt met...  <br/> |Doel  <br/> |Voegt u deze opnamen (includes) toe  <br/> |
|:-----|:-----|:-----|:-----|
|1  <br/> |Alle e-mailsystemen (vereist)  <br/> |Alle SPF-records beginnen met deze waarde  <br/> |v=spf1  <br/> |
|2  <br/> |Exchange Online (common)  <br/> |Gebruik alleen met Exchange Online  <br/> |include:spf.protection.outlook.com  <br/> |
|3  <br/> |Extern e-mailsysteem (minder algemeen)  <br/> ||inclusief:\<email system like mail.contoso.com\>  <br/> |
|4  <br/> |On-premises e-mailsysteem (minder algemeen)  <br/> |Gebruiken als u Exchange Online Protection of Exchange Online plus een ander e-mailsysteem gebruikt  <br/> |ip4:\<0.0.0.0\>  <br/> ip6:\< : : \>  <br/> inclusief:\<mail.contoso.com\>  <br/> De waarde tussen punthaken (\<\>) moet een ander e-mailsysteem zijn waarmee e-mail voor uw domein wordt verzonden.  <br/> |
|5  <br/> |Alle e-mailsystemen (vereist)  <br/> ||-all  <br/> |

### <a name="example-adding-to-an-existing-spf-record"></a>Voorbeeld: Aan een bestaande SPF-record toevoegen
<a name="bkmk_addtospf"> </a>

Als u al een SPF-record hebt, moet u er waarden voor Office 365 aan toevoegen of updaten. Stel bijvoorbeeld dat dit uw bestaande SPF-record voor contoso.com is:
  
``` dns
TXT Name @
Values: v=spf1 ip4:60.200.100.30 include:smtp.adatum.com -all
```

Nu werkt u de SPF-record bij voor Office 365. U bewerkt de huidige record zodat u beschikt over één SPF-record waarin de waarden die u nodig hebt, zijn opgenomen. For Office 365, "spf.protection.outlook.com".
  
Juist:
  
``` dns
TXT Name @
Values: v=spf1 ip4:60.200.100.30 include:spf.protection.outlook.com include:smtp.adatum.com -all
```

Onjuist:
  
``` dns
Record 1:
TXT Name @
Values: v=spf1 ip4:60.200.100.30 include:smtp.adatum.com -all
Record 2:
Values: v=spf1 include:spf.protection.outlook.com -all
```

### <a name="more-examples-of-common-spf-values"></a>Meer voorbeelden van SPF-waarden
<a name="bkmk_addtospf"> </a>

Als u de volledige Office 365-suite gebruikt en MailChimp gebruikt om namens u marketingmails te verzenden, kan uw SPF-record op contoso.com er als volgt uitzien, waarin de rijen 1, 3 en 5 van de bovenstaande tabel worden gebruikt. Let op: rij 1 en 5 zijn vereist.
  
``` dns
TXT Name @
Values: v=spf1 include:spf.protection.outlook.com include:servers.mcsv.net -all
```

Als u een hybride implementatie van Exchange-configuratie hebt waarbij e-mail wordt verzonden vanuit zowel Office 365 als uw on-premises e-mailsysteem, zou uw SPF-record op contoso.com er als volgt uit kunnen zien:
  
``` dns
TXT Name @
Values: v=spf1 include:spf.protection.outlook.com include:mail.contoso.com -all
```

Dit zijn enkele veelvoorkomende voorbeelden die u kunnen helpen uw bestaande SPF-record aan te passen wanneer u uw domein aan Office 365 voor e-mail toevoegt. Als u een ingewikkeld scenario hebt met bijvoorbeeld edge-mailservers voor het beheren van e-mailverkeer door uw firewall, moet u een meer gedetailleerde SPF-record instellen. Leer hoe: [SPF records instellen in Office 365 om vervalsing te helpen voorkomen](https://go.microsoft.com/fwlink/?LinkId=787656).
  
Met deze korte koppeling kunt u teruggaan: [https://aka.ms/o365edns](https://aka.ms/o365edns)
