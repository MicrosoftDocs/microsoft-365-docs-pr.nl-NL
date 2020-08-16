---
title: IP-adres en URL-webservice van Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/6/2019
audience: ITPro
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
ms.reviewer: pandrew
search.appverid:
- MET150
- MOE150
- BCS160
description: Informatie over het gebruik van het IP-adres en de URL-webservice van Office 365 om u te helpen bij het beter identificeren en onderscheiden van het netwerkverkeer van Office 365.
ms.openlocfilehash: abcf6eb8ab963749b451e1f0eeef91d963b76b89
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695753"
---
# <a name="office-365-ip-address-and-url-web-service"></a>IP-adres en URL-webservice van Office 365

Het IP-adres en de URL-webservice Office 365 helpen u bij het beter identificeren en onderscheiden van het Office 365-netwerkverkeer. Hierdoor is het eenvoudiger om op de hoogte te blijven van wijzigingen en deze te evalueren en te configureren. Met deze REST-webservice worden eerdere downloadbare XML-bestanden die op 2 oktober 2018 werden geïmplementeerd vervangen.

Als klant of leverancier van netwerkperimeterapparaten kunt u de vermeldingen van de Office 365-IP-adressen en -FQDN's gebruiken als bouwstenen. U kunt de gegevens rechtstreeks in een webbrowser openen met behulp van de volgende URL's:

- Gebruik [https://endpoints.office.com/version](https://endpoints.office.com/version?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) voor de nieuwste versie van de URL's en IP-adresbereiken voor Office 365
- Gebruik [https://endpoints.office.com/endpoints/worldwide](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) voor de gegevens op de pagina over de URL's en IP-adresbereiken voor Office 365 voor firewalls en proxyservers.
- Gebruik [https://endpoints.office.com/changes/worldwide/0000000000](https://endpoints.office.com/changes/worldwide/0000000000?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) om alle meest recente wijzigingen sinds juli 2018, toen de webservice voor het eerst beschikbaar was, op te halen.

Als klant kunt u deze webservice gebruiken voor:

- Het bijwerken van PowerShell-scripts voor het verkrijgen van Office 365-eindpuntgegevens en het wijzigen van de opmaak van uw netwerkapparatuur.
- Gebruik deze informatie voor het bijwerken van PAC-bestanden die voor clientcomputers zijn geïmplementeerd.

Als leverancier van netwerkperimeterapparaten kunt u deze webservice gebruiken voor:

- Het maken en testen van apparaatsoftware om de lijst voor geautomatiseerde configuratie te downloaden.
- Het controleren van de huidige versie.
- Het ophalen van de huidige wijzigingen.

> [!NOTE]
> Als u Azure ExpressRoute gebruikt om verbinding te maken met Office 365, raadpleegt u [Azure ExpressRoute voor Office 365](azure-expressroute.md) om vertrouwd te raken met de Office 365-services die worden ondersteund via Azure ExpressRoute. Raadpleeg ook het artikel [IP-adresbereiken en URL‘s van Office 365](urls-and-ip-address-ranges.md) om te lezen voor welke netwerkverzoeken van Office 365-toepassingen verbinding met internet nodig is. Hiermee kunt u het beveiligingsapparaat voor een perimeternetwerk beter configureren.

Zie voor meer informatie:

- [Announcement blog post in the Office 365 Tech Community Forum](https://techcommunity.microsoft.com/t5/Office-365-Blog/Announcing-Office-365-endpoint-categories-and-Office-365-IP/ba-p/177638)
- [Office 365 Tech Community Forum for questions about use of the web services](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)

## <a name="common-parameters"></a>Veelgebruikte parameters

De volgende parameters worden veel gebruikt in alle webservicemethoden:

- **format=<JSON | CSV>** — De standaardindeling van de geretourneerde gegevens is JSON. Gebruik deze optionele parameter als u de gegevens in een indeling met door komma's gescheiden waarden wilt hebben.
- **ClientRequestId=\<guid>** — Een verplichte GUID die u genereert voor clientkoppeling. Genereer een unieke GUID voor elke computer waarmee de webservice wordt aangeroepen (de scripts op deze pagina genereren een GUID voor u). Gebruik niet de GUID's uit het volgende voorbeeld. Deze kunnen in de toekomst door de webservice worden geblokkeerd. De indeling van de GUID is _xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx_, waarin de x voor een hexadecimaal getal staat.

  Als u een GUID wilt genereren, kunt u gebruikmaken van de opdracht [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) PowerShell of een online service zoals [Online GUID Generator](https://www.guidgenerator.com/).

## <a name="version-web-method"></a>Versiewebmethode

Microsoft werkt het IP-adres en de FQDN-vermeldingen van Office 365 aan het begin van elke maand bij. Er worden soms out-of-band updates gepubliceerd vanwege ondersteuningsincidenten, beveiligingsupdates of andere operationele vereisten.

Aan de gegevens voor elk gepubliceerd exemplaar wordt een versienummer toegewezen en met de versiewebmethode kunt u controleren op de meest recente versie van elk service-exemplaar van Office 365. U wordt aangeraden de versie niet meer dan één keer per uur te controleren.

Parameters voor de versiewebmethode zijn:

- **AllVersions=<true | false>** — Standaard is de geretourneerde versie de laatste. Neem deze optionele parameter op om alle gepubliceerde versies aan te vragen sinds de webservice voor het eerst werd uitgebracht.
- **Format=<JSON | CSV | RSS>** — Naast de JSON- en CSV-indelingen, ondersteunt de versiewebmethode ook RSS. U kunt deze optionele parameter combineren met de parameter _AllVersions=true_ om een RSS-feed aan te vragen die kan worden gebruikt met Outlook of andere RSS-lezers.
- **Instance=<Worldwide | China | Germany | USGovDoD | USGovGCCHigh>** — Deze optionele parameter specificeert het exemplaar waarvoor de versie moet worden geretourneerd. Indien niet gebruikt, worden alle exemplaren geretourneerd. Geldige exemplaren zijn: wereldwijd, China, Duitsland, USGovDoD en USGovGCCHigh.

De versiewebmethode is niet beperkt en geeft nooit 429 HTTP-antwoordcodes. Het antwoord op de versiewebmethode omvat een cache-besturingselementindeling die het in de cache opslaan van de gegevens voor 1 uur aanbeveelt. Het resultaat van de versiewebmethode kan één record zijn of een matrix van records. De elementen van elke record zijn:

- exemplaar - De korte naam van het Office 365-service-exemplaar.
- nieuwste - De nieuwste versie voor eindpunten van het opgegeven exemplaar.
- versies - Een lijst met alle voorgaande versies voor het opgegeven exemplaar. Dit element is alleen opgenomen als de parameter _AllVersions_ waar is.

### <a name="examples"></a>Voorbeelden:

Voorbeeld 1 URI aanvragen: [https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Met deze URI wordt de nieuwste versie van elk Office 365-service-exemplaar geretourneerd. Resultaat van voorbeeld:

```json
[
 {
  "instance": "Worldwide",
  "latest": "2018063000"
 },
 {
  "instance": "USGovDoD",
  "latest": "2018063000"
 },
 {
  "instance": "USGovGCCHigh",
  "latest": "2018063000"
 },
 {
  "instance": "China",
  "latest": "2018063000"
 },
 {
  "instance": "Germany",
  "latest": "2018063000"
 }
]
```

> [!IMPORTANT]
> De GUID voor de parameter ClientRequestID in deze URI's is slechts een voorbeeld. Genereer uw eigen GUID als u de URI's voor de webservice wilt uitproberen. De in deze voorbeelden getoonde GUID's kunnen in de toekomst door de webservice worden geblokkeerd.

Voorbeeld 2 URI aanvragen: [https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Met deze URI wordt de nieuwste versie van het opgegeven Office 365-service-exemplaar geretourneerd. Resultaat van voorbeeld:

```json
{
 "instance": "Worldwide",
 "latest": "2018063000"
}
```

Voorbeeld 3 URI aanvragen: [https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Met deze URI wordt de uitvoer in een CSV-indeling getoond. Resultaat van voorbeeld:

```csv
instance,latest
Worldwide,2018063000
```

Voorbeeld 4 URI aanvragen: [https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Met deze URI worden alle vorige versies getoond die voor het Office 365 Worldwide-service-exemplaar zijn gepubliceerd. Resultaat van voorbeeld:

```json
{
  "instance": "Worldwide",
  "latest": "2018063000",
  "versions": [
    "2018063000",
    "2018062000"
  ]
}
```

Voorbeeld 5 URI voor RSS-feed: [https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS](https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS)

Met deze URI wordt een RSS-feed weergegeven van de gepubliceerde versies die koppelingen bevatten naar de lijst met wijzigingen voor elke versie. Resultaat van voorbeeld:

```xml
<?xml version="1.0" encoding="ISO-8859-1"?>
<rss version="2.0" xmlns:a10="https://www.w3.org/2005/Atom">
<channel>
<link>https://aka.ms/o365ip</link>
<description/>
<language>en-us</language>
<lastBuildDate>Thu, 02 Aug 2018 00:00:00 Z</lastBuildDate>
<item>
<guid isPermaLink="false">2018080200</guid>
<link>https://endpoints.office.com/changes/Worldwide/2018080200?singleVersion&clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7</link> <description>Version 2018080200 includes 2 changes. IPs: 2 added and 0 removed.</description>
<pubDate>Thu, 02 Aug 2018 00:00:00 Z</pubDate>
</item>
```

## <a name="endpoints-web-method"></a>Eindpuntenwebmethode

Met de eindpuntenwebmethode worden alle records voor IP-adresbereiken en URL's geretourneerd waaruit de Office 365-service is opgebouwd. De meest recente gegevens uit de eindpuntenwebmethode moeten altijd worden gebruikt voor de configuratie van netwerkapparaten. Microsoft biedt 30 dagen voorafgaande kennisgeving voor het publiceren van nieuwe toevoegingen om u tijd te geven om toegangsbeheerlijsten en bypasslijsten van de proxyserver bij te werken. U wordt aangeraden de eindpuntenwebmethode pas opnieuw aan te roepen wanneer de versiewebmethode aangeeft dat er een nieuwe versie van de gegevens beschikbaar is.

Parameters voor de eindpuntenwebmethode zijn:

- **ServiceAreas=<Common | Exchange | SharePoint | Skype>** — Een door komma‘s gescheiden lijst van servicegebieden. Geldige items zijn _Common_, _Exchange_, _SharePoint_ en _Skype_. Omdat _Common_-servicegebieditems een vereiste zijn voor alle overige servicegebieden, is dit item altijd in de webservice opgenomen. Als u deze parameter niet opneemt, worden alle services geretourneerd.
- **TenantName=<tenant_name>** — De naam van uw Office 365-tenant. De webservice gebruikt de opgegeven naam en voegt deze in delen van URL's in waarin de naam van de tenant is opgenomen. Als u geen tenantnaam opgeeft, bevatten deze URL's een jokerteken (\*).
- **NoIPv6=<true | false>** — Stel de waarde in op _true_ om NoIPv6-adressen van de uitvoer uit te sluiten als u IPv6 niet gebruikt in uw netwerk.
- **Instance=<Worldwide | China | Germany | USGovDoD | USGovGCCHigh>** — Deze verplichte parameter specificeert het exemplaar waarvoor de eindpunten moeten worden geretourneerd. Geldige exemplaren zijn: _Worldwide_, _China_, _Germany_, _USGovDoD_ en _USGovGCCHigh_.

Als u de eindpuntenwebmethode te vaak oproept van hetzelfde IP-adres van de client, ontvangt u mogelijk de HTTP-antwoordcode _429 (te veel aanvragen)_. Als u deze antwoordcode krijgt, wacht u 1 uur voordat u de aanvraag herhaalt of genereert u een nieuwe GUID voor de aanvraag. Over het algemeen kunt u het beste de eindpuntenwebmethode pas opnieuw aanroepen wanneer de versiewebmethode aangeeft dat er een nieuwe versie van de gegevens beschikbaar is.

Het resultaat van de eindpuntenwebmethode bestaat uit een matrix met records, waarbij elke record een specifieke eindpuntenset voorstelt. De elementen van elke record zijn:

- id - Het onveranderlijke id-nummer van de eindpuntenset.
- serviceArea — Het servicegebied waar dit deel van uitmaakt: _Common_, _Exchange_, _SharePoint_ of _Skype_.
- urls: URL's voor de eindpuntenset. Een JSON-matrix van DNS-records. Dit argument wordt weggelaten indien leeg.
- tcpPorts — TCP-poorten voor de eindpuntenset. Alle poortelementen worden ingedeeld als een door komma's gescheiden lijst met poorten of poortbereiken die door een streepje (-) worden gescheiden. Poorten zijn van toepassing op alle IP-adressen en alle URL's in die eindpuntenset voor een bepaalde categorie. Dit argument wordt weggelaten indien leeg.
- udpPorts - UDP-poorten voor de IP-adresbereiken in deze eindpuntenset. Dit argument wordt weggelaten indien leeg.
- ips - De IP-adresbereiken die zijn gekoppeld aan deze eindpuntenset zoals gekoppeld aan de vermelde TCP- of UDP-poorten. Een JSON-matrix met IP-adresbereiken. Dit argument wordt weggelaten indien leeg.
- category - De verbindingscategorie voor de eindpuntenset. Geldige waarden zijn _Optimaliseren_, _Toestaan_ en _Standaard_. Als u de uitvoer van de eindpuntenwebmethode zoekt voor de categorie van een specifiek IP-adres of -URL, is het mogelijk dat uw query meerdere categorieën retourneert. Volg in dat geval de aanbeveling voor de categorie met de hoogste prioriteit. Als het eindpunt bijvoorbeeld wordt weergegeven in zowel _Optimaliseren_ als _Toestaan_, volgt u de vereisten voor _Optimaliseren_. Vereist.
- expressRoute — _True_ als deze eindpuntenset via ExpressRoute wordt gerouteerd, _False_ als dit niet het geval is.
- required — _True_ als deze eindpuntenset moet zijn verbonden om ondersteuning van Office 365 mogelijk te maken. _False_ als deze eindpunt serie optioneel is.
- notes - Voor optionele eindpunten beschrijft deze tekst de Office 365-functionaliteit die niet beschikbaar is als IP-adressen of URL‘s in deze eindpuntenset niet kunnen worden bereikt in de netwerklaag. Dit argument wordt weggelaten indien leeg.

### <a name="examples"></a>Voorbeelden:

Voorbeeld 1 URI aanvragen: [https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Met deze URI worden voor alle werkbelastingen alle eindpunten verkregen voor het Office 365 Worldwide-exemplaar. Voorbeeldresultaat dat een fragment van de uitvoer toont:

```json
[
 {
  "id": 1,
  "serviceArea": "Exchange",
  "serviceAreaDisplayName": "Exchange Online",
  "urls":
   [
    "*.protection.outlook.com"
   ],
  "ips":
   [
    "2a01:111:f403::/48", "23.103.132.0/22", "23.103.136.0/21", "23.103.198.0/23", "23.103.212.0/22", "40.92.0.0/14", "40.107.0.0/17", "40.107.128.0/18", "52.100.0.0/14", "213.199.154.0/24", "213.199.180.128/26", "94.245.120.64/26", "207.46.163.0/24", "65.55.88.0/24", "216.32.180.0/23", "23.103.144.0/20", "65.55.169.0/24", "207.46.100.0/24", "2a01:111:f400:7c00::/54", "157.56.110.0/23", "23.103.200.0/22", "104.47.0.0/17", "2a01:111:f400:fc00::/54", "157.55.234.0/24", "157.56.112.0/24", "52.238.78.88/32"
   ],
  "tcpPorts": "443",
  "expressRoute": true,
  "category": "Allow"
 },
 {
  "id": 2,
  "serviceArea": "Exchange",
  "serviceAreaDisplayName": "Exchange Online",
  "urls":
   [
    "*.mail.protection.outlook.com"
   ],
```

Houd er rekening mee dat de volledige uitvoer van de aanvraag in dit voorbeeld andere eindpunten sets zou kunnen bevatten.

Voorbeeld 2 URI aanvragen: [https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

In dit voorbeeld worden alleen eindpunten verkregen voor het Office 365 Worldwide-exemplaar voor Exchange Online en afhankelijkheden.

De uitvoer van voorbeeld 2 lijkt op die van voorbeeld 1, behalve dat in de resultaten geen eindpunten zijn opgenomen voor SharePoint Online of Skype voor Bedrijven Online.

## <a name="changes-web-method"></a>Wijzigingenwebmethode

Met de wijzigingenwebmethode worden de meest recente updates die zijn gepubliceerd, geretourneerd. Dit zijn gewoonlijk de wijzigingen aan IP-adresbereiken en URL's van de vorige maand.

De belangrijkste wijzigingen in de gegevens van eindpunten zijn nieuwe URL's en IP-adressen. Het niet toevoegen van een IP-adres aan een toegangsbeheerlijst van een firewall of een URL naar een bypasslijst voor een proxyserver kan een storing veroorzaken voor Office 365-gebruikers van dat netwerkapparaat. Niettegenstaande operationele vereisten worden nieuwe eindpunten op de webservice gepubliceerd 30 dagen voor de datum waarop de eindpunten zijn ingericht voor gebruik, zodat u tijd hebt om toegangsbeheerlijsten en bypasslijsten voor proxyservers over te slaan.

De vereiste parameter voor de wijzigingenwebmethode is:

- **Version=\<YYYYMMDDNN>** — Verplichte URL-routeparameter. Deze waarde is de versie die u momenteel hebt geïmplementeerd. De webservice retourneert de wijzigingen sinds die versie. De indeling is _JJJJMMDDNN_, waarbij _NN_ een natuurlijk getal is, dat is verhoogd als er meerdere versies op één dag moeten worden gepubliceerd en _00_ de eerste update voor een bepaalde dag voorstelt. Voor de webservice moet de _versie_parameter precies 10 cijfers bevatten.

De wijzigingenwebmethode is op dezelfde manier beperkt als de eindpuntenwebmethode. Als u een 429 HTTP-antwoordcode krijgt, wacht u 1 uur voordat u de aanvraag herhaalt of genereert u een nieuwe GUID voor de aanvraag.

Het resultaat van de wijzigingenwebmethode is een matrix met records, waarbij elke record een wijziging voorstelt in een bepaalde versie van de eindpunten. De elementen van elke record zijn:

- id - De onveranderlijke id van de wijzigingenrecord.
- endpointSetId - De id van de eindpuntensetrecord die is gewijzigd.
- disposition - Beschrijft wat de wijziging heeft veranderd aan de eindpuntensetrecord. Waarden zijn _wijzigen_, _toevoegen_ of _verwijderen_.
- impact — Niet alle wijzigingen zijn even belangrijk voor elke omgeving. Dit element beschrijft de verwachte uitwerking op een perimeteromgeving van een bedrijfsnetwerk als gevolg van deze wijziging. Dit element wordt alleen opgenomen in de wijzigingsrecords van versie **2018112800** en hoger. De opties voor de uitwerking zijn: — AddedIp – Er is een IP-adres toegevoegd aan Office 365 en deze wordt binnenkort live op de service. Dit is een wijziging die u moet uitvoeren op een firewall of een ander laag 3-netwerkperimeterapparaat. Als u dit niet toevoegt voordat we het gaan gebruiken, kan er mogelijk een storing optreden.
  — AddedUrl - Er is een URL toegevoegd aan Office 365 en deze wordt binnenkort live voor de service. Dit is een wijziging die u moet uitvoeren op een proxyserver of een netwerkperimeterapparaat dat de URL parseert. Als u deze URL niet toevoegt voordat we het gaan gebruiken, kan er mogelijk een storing optreden.
  — AddedIpAndUrl - Er zijn zowel een IP-adres als een URL toegevoegd. Dit is een wijziging die u moet uitvoeren op een apparaat met een laag 3-firewall of een proxyserver of apparaat dat URL parseert. Als u dit IP/URL-paar niet toevoegt voordat we het gaan gebruiken, kan er mogelijk een storing optreden.
  — RemovedIpOrUrl – Er is minstens één IP-adres of URL verwijderd van Office 365. Verwijder de netwerkeindpunten van uw perimeterapparaten, maar er is geen deadline om dit te doen.
  — ChangedIsExpressRoute - Het ExpressRoute-ondersteuningskenmerk is gewijzigd. Als u ExpressRoute gebruikt, moet u mogelijk actie ondernemen afhankelijk van uw configuratie.
  — MovedIpOrUrl – We hebben een IP-adres of URL van deze eindpuntenset naar een andere verplaatst. Over het algemeen hoeft u geen actie te ondernemen.
  — RemovedDuplicateIpOrUrl – We hebben een gedupliceerd IP-adres of URL verwijderd, maar deze is nog steeds gepubliceerd voor Office 365. Over het algemeen hoeft u geen actie te ondernemen.
  — OtherNonPriorityChanges – We hebben iets gewijzigd dat minder belangrijk is dan alle andere opties, zoals de inhoud van een notitieveld.
- version — De versie van de gepubliceerde eindpuntenset waarin de wijziging is aangebracht. Versienummers hebben de indeling _JJJJMMDDNN_, waarbij _NN_ een natuurlijk getal is, dat is verhoogd als er meerdere versies op één dag moeten worden gepubliceerd.
- previous - Een substructuur met een opsomming van vorige waarden van gewijzigde elementen in de eindpuntenset. Deze wordt niet opgenomen voor nieuw toegevoegde eindpuntensets. Bevat _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_ en _notes_.
- current - Een substructuur met een opsomming van bijgewerkte waarden van gewijzigde elementen in de eindpuntenset. Bevat _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_ en _notes_.
- add - Een substructuur met een opsomming van items die aan eindpuntensetverzamelingen moeten worden toegevoegd. Wordt weggelaten als er geen toevoegingen zijn.
  — effectiveDate — Definieert de gegevens als de toevoegingen live in de service zijn.
  — ips — Toe te voegen items aan de _ips_-matrix.
  — urls- Toe te voegen items aan de _URL‘s_-matrix.
- remove - Een substructuur met een opsomming van items die uit de eindpuntenset moeten worden verwijderd. Wordt weggelaten als er geen verwijderingen zijn.
  — ips — Items die uit de _ips_-matrix moeten worden verwijderd.
  — urls- Items die uit de _URL‘s_-matrix moeten worden verwijderd.

### <a name="examples"></a>Voorbeelden:

Voorbeeld 1 URI aanvragen: [https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Hiermee worden alle voorgaande wijzigingen aan het Office 365 Worldwide-service-exemplaar aangevraagd. Resultaat van voorbeeld:

```json
[
 {
  "id": 424,
  "endpointSetId": 32,
  "disposition": "Change",
  "version": "2018062700",
  "remove":
   {
    "urls":
     [
      "*.api.skype.com", "skypegraph.skype.com"
     ]
   }
 },
 {
  "id": 426,
  "endpointSetId": 31,
  "disposition": "Change",
  "version": "2018062700",
  "add":
   {
    "effectiveDate": "20180609",
    "ips":
     [
      "51.140.203.190/32"
     ]
   },
  "remove":
   {
    "ips":
     [
```

Voorbeeld 2 URI aanvragen: [https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Hiermee worden wijzigingen aangevraagd die zijn aangebracht na de opgegeven versie van het Office 365 Worldwide-exemplaar. In dit geval is de versie die is opgegeven de nieuwste versie. Resultaat van voorbeeld:

```json
[
  {
    "id":3,
    "endpointSetId":33,
    "changeDescription":"Removing old IP prefixes",
    "disposition":"Change",
    "version":"2018031301",
    "remove":{
      "ips":["65.55.127.0/24","66.119.157.192/26","66.119.158.0/25",
      "111.221.76.128/25","111.221.77.0/26","207.46.5.0/24"]
    }
  },
  {
    "id":4,
    "endpointSetId":45,
    "changeDescription":"Removing old IP prefixes",
    "disposition":"Change",
    "version":"2018031301",
    "remove":{
      "ips":["13.78.93.8/32","40.113.87.220/32","40.114.149.220/32",
      "40.117.100.83/32","40.118.214.164/32","104.208.31.113/32"]
    }
  }
]
```

## <a name="example-powershell-script"></a>Voorbeeld van PowerShell-script

U kunt dit PowerShell-script uitvoeren om te zien of er acties zijn die u moet ondernemen voor bijgewerkte gegevens. U kunt dit script uitvoeren als een geplande taak om te controleren of er een versie-update is. Om te voorkomen dat de webservice te zwaar belast wordt, dient u het script niet meer dan één keer per uur uit te voeren.

Het script doet het volgende:

- Het versienummer van de huidige eindpunten van het Office 365 Worldwide-exemplaar wordt gecontroleerd door de webservice REST API aan te roepen.
- Hiermee wordt gecontroleerd op een huidig versiebestand via _$Env:TEMP\O365_endpoints_latestversion.txt_. Het pad van de globale variabele **$Env:TEMP** is meestal _C:\Users\\<username\>\AppData\Local\Temp_.
- Als dit de eerste keer is dat het script wordt uitgevoerd, geeft het script de huidige versie en alle huidige IP-adressen en URL's als resultaat, schrijft het de eindpuntenversie naar het bestand _$Env: TEMP \ O365_endpoints_latestversion. txt_ en de gegevensuitvoer van de eindpunten naar het bestand _$Env: TEMP \ O365_endpoints_data. txt_. U kunt het pad en/of de naam van het uitvoerbestand wijzigen door deze regels te bewerken:

    ``` powershell
    $versionpath = $Env:TEMP + "\O365_endpoints_latestversion.txt"
    $datapath = $Env:TEMP + "\O365_endpoints_data.txt"
    ```

- Wanneer de nieuwste webserviceversie identiek is aan de versie in het bestand _O365_endpoints_latestversion. txt_, wordt het script bij elke daaropvolgende uitvoering van het script afgesloten zonder enige wijzigingen door te voeren.
- Wanneer de nieuwste versie van de webservice nieuwer is dan de versie in het bestand _O365_endpoints_latestversion.txt_, retourneert het script de eindpunten en filters voor de eindpunten in de categorie **Toestaan** en **Optimaliseren**, wordt de versie bijgewerkt in het bestand _O365_endpoints_latestversion.txt_ en worden de bijgewerkte gegevens naar het bestand _O365_endpoints_data.txt_ geschreven.

Het script genereert een unieke _ClientRequestId_ voor de computer waarop deze wordt uitgevoerd en gebruikt deze ID voor meerdere gesprekken. Deze ID wordt opgeslagen in het bestand _O365_endpoints_latestversion. txt_.

### <a name="to-run-the-powershell-script"></a>Het PowerShell-script uitvoeren

1. Kopieer het script en sla het op uw lokale harde schijf of in een scriptlocatie op als _Get-O365WebServiceUpdates.ps1_.
1. Voer het script uit in de gewenste scripteditor, zoals de PowerShell ISE of VS Code of met een PowerShell-console, met de volgende opdracht:

    ``` powershell
   powershell.exe -file <path>\Get-O365WebServiceUpdates.ps1
    ```

    Er zijn geen parameters die moeten worden doorgegeven aan het script.

```powershell
<# Get-O365WebServiceUpdates.ps1
From https://aka.ms/ipurlws
v1.1 8/6/2019

DESCRIPTION
This script calls the REST API of the Office 365 IP and URL Web Service (Worldwide instance)
and checks to see if there has been a new update since the version stored in an existing
$Env:TEMP\O365_endpoints_latestversion.txt file in your user directory's temp folder
(usually C:\Users\<username>\AppData\Local\Temp).
If the file doesn't exist, or the latest version is newer than the current version in the
file, the script returns IPs and/or URLs that have been changed, added or removed in the latest
update and writes the new version and data to the output file $Env:TEMP\O365_endpoints_data.txt.

USAGE
Run as a scheduled task every 60 minutes.

PARAMETERS
n/a

PREREQUISITES
PS script execution policy: Bypass
PowerShell 3.0 or later
Does not require elevation
#>

#Requires -Version 3.0

# web service root URL
$ws = "https://endpoints.office.com"
# path where output files will be stored
$versionpath = $Env:TEMP + "\O365_endpoints_latestversion.txt"
$datapath = $Env:TEMP + "\O365_endpoints_data.txt"

# fetch client ID and version if version file exists; otherwise create new file and client ID
if (Test-Path $versionpath) {
    $content = Get-Content $versionpath
    $clientRequestId = $content[0]
    $lastVersion = $content[1]
    Write-Output ("Version file exists! Current version: " + $lastVersion)
}
else {
    Write-Output ("First run! Creating version file at " + $versionpath + ".")
    $clientRequestId = [GUID]::NewGuid().Guid
    $lastVersion = "0000000000"
    @($clientRequestId, $lastVersion) | Out-File $versionpath
}

# call version method to check the latest version, and pull new data if version number is different
$version = Invoke-RestMethod -Uri ($ws + "/version/Worldwide?clientRequestId=" + $clientRequestId)
if ($version.latest -gt $lastVersion) {
    Write-Host "New version of Office 365 worldwide commercial service instance endpoints detected"
    # write the new version number to the version file
    @($clientRequestId, $version.latest) | Out-File $versionpath
    # invoke endpoints method to get the new data
    $endpointSets = Invoke-RestMethod -Uri ($ws + "/endpoints/Worldwide?clientRequestId=" + $clientRequestId)
    # filter results for Allow and Optimize endpoints, and transform these into custom objects with port and category
    # URL results
    $flatUrls = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $urls = $(if ($endpointSet.urls.Count -gt 0) { $endpointSet.urls } else { @() })
        $urlCustomObjects = @()
        if ($endpointSet.category -in ("Allow", "Optimize")) {
            $urlCustomObjects = $urls | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    url      = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $urlCustomObjects
    }
    # IPv4 results
    $flatIp4s = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $ips = $(if ($endpointSet.ips.Count -gt 0) { $endpointSet.ips } else { @() })
        # IPv4 strings contain dots
        $ip4s = $ips | Where-Object { $_ -like '*.*' }
        $ip4CustomObjects = @()
        if ($endpointSet.category -in ("Allow", "Optimize")) {
            $ip4CustomObjects = $ip4s | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    ip = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $ip4CustomObjects
    }
    # IPv6 results
    $flatIp6s = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $ips = $(if ($endpointSet.ips.Count -gt 0) { $endpointSet.ips } else { @() })
        # IPv6 strings contain colons
        $ip6s = $ips | Where-Object { $_ -like '*:*' }
        $ip6CustomObjects = @()
        if ($endpointSet.category -in ("Optimize")) {
            $ip6CustomObjects = $ip6s | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    ip = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $ip6CustomObjects
    }

    # write output to screen
    Write-Output ("Client Request ID: " + $clientRequestId)
    Write-Output ("Last Version: " + $lastVersion)
    Write-Output ("New Version: " + $version.latest)
    Write-Output ""
    Write-Output "IPv4 Firewall IP Address Ranges"
    ($flatIp4s.ip | Sort-Object -Unique) -join "," | Out-String
    Write-Output "IPv6 Firewall IP Address Ranges"
    ($flatIp6s.ip | Sort-Object -Unique) -join "," | Out-String
    Write-Output "URLs for Proxy Server"
    ($flatUrls.url | Sort-Object -Unique) -join "," | Out-String
    Write-Output ("IP and URL data written to " + $datapath)

    # write output to data file
    Write-Output "Office 365 IP and UL Web Service data" | Out-File $datapath
    Write-Output "Worldwide instance" | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output ("Version: " + $version.latest) | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "IPv4 Firewall IP Address Ranges" | Out-File $datapath -Append
    ($flatIp4s.ip | Sort-Object -Unique) -join "," | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "IPv6 Firewall IP Address Ranges" | Out-File $datapath -Append
    ($flatIp6s.ip | Sort-Object -Unique) -join "," | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "URLs for Proxy Server" | Out-File $datapath -Append
    ($flatUrls.url | Sort-Object -Unique) -join "," | Out-File $datapath -Append
}
else {
    Write-Host "Office 365 worldwide commercial service instance endpoints are up-to-date."
}
```

## <a name="example-python-script"></a>Voorbeeld van Python-script

Hier ziet u een Python-script, getest met Python 3.6.3 onder Windows 10. U kunt het uitvoeren om te zien of er acties zijn die u moet ondernemen voor bijgewerkte gegevens. Met dit script wordt het versienummer van de eindpunten van het Office 365 Worldwide-exemplaar gecontroleerd. Als er een wijziging is, worden de eindpunten gedownload en wordt er gefilterd op de eindpunten in de categorie _Toestaan_ en _Optimaliseren_. Er wordt ook een unieke ClientRequestId gebruikt voor meerdere aanroepen en wordt de nieuwste versie in een tijdelijk bestand opgeslagen. Roep dit script eenmaal per uur aan om te controleren op een update van de versie.

```python
import json
import tempfile
from pathlib import Path
import urllib.request
import uuid
# helper to call the webservice and parse the response
def webApiGet(methodName, instanceName, clientRequestId):
    ws = "https://endpoints.office.com"
    requestPath = ws + '/' + methodName + '/' + instanceName + '?clientRequestId=' + clientRequestId
    request = urllib.request.Request(requestPath)
    with urllib.request.urlopen(request) as response:
        return json.loads(response.read().decode())
# path where client ID and latest version number will be stored
datapath = Path(tempfile.gettempdir() + '/endpoints_clientid_latestversion.txt')
# fetch client ID and version if data exists; otherwise create new file
if datapath.exists():
    with open(datapath, 'r') as fin:
        clientRequestId = fin.readline().strip()
        latestVersion = fin.readline().strip()
else:
    clientRequestId = str(uuid.uuid4())
    latestVersion = '0000000000'
    with open(datapath, 'w') as fout:
        fout.write(clientRequestId + '\n' + latestVersion)
# call version method to check the latest version, and pull new data if version number is different
version = webApiGet('version', 'Worldwide', clientRequestId)
if version['latest'] > latestVersion:
    print('New version of Office 365 worldwide commercial service instance endpoints detected')
    # write the new version number to the data file
    with open(datapath, 'w') as fout:
        fout.write(clientRequestId + '\n' + version['latest'])
    # invoke endpoints method to get the new data
    endpointSets = webApiGet('endpoints', 'Worldwide', clientRequestId)
    # filter results for Allow and Optimize endpoints, and transform these into tuples with port and category
    flatUrls = []
    for endpointSet in endpointSets:
        if endpointSet['category'] in ('Optimize', 'Allow'):
            category = endpointSet['category']
            urls = endpointSet['urls'] if 'urls' in endpointSet else []
            tcpPorts = endpointSet['tcpPorts'] if 'tcpPorts' in endpointSet else ''
            udpPorts = endpointSet['udpPorts'] if 'udpPorts' in endpointSet else ''
            flatUrls.extend([(category, url, tcpPorts, udpPorts) for url in urls])
    flatIps = []
    for endpointSet in endpointSets:
        if endpointSet['category'] in ('Optimize', 'Allow'):
            ips = endpointSet['ips'] if 'ips' in endpointSet else []
            category = endpointSet['category']
            # IPv4 strings have dots while IPv6 strings have colons
            ip4s = [ip for ip in ips if '.' in ip]
            tcpPorts = endpointSet['tcpPorts'] if 'tcpPorts' in endpointSet else ''
            udpPorts = endpointSet['udpPorts'] if 'udpPorts' in endpointSet else ''
            flatIps.extend([(category, ip, tcpPorts, udpPorts) for ip in ip4s])
    print('IPv4 Firewall IP Address Ranges')
    print(','.join(sorted(set([ip for (category, ip, tcpPorts, udpPorts) in flatIps]))))
    print('URLs for Proxy Server')
    print(','.join(sorted(set([url for (category, url, tcpPorts, udpPorts) in flatUrls]))))

    # TODO send mail (e.g. with smtplib/email modules) with new endpoints data
else:
    print('Office 365 worldwide commercial service instance endpoints are up-to-date')
```

## <a name="web-service-interface-versioning"></a>Versiebeheer van webservice-interface

In de toekomst zijn mogelijk updates van de parameters of resultaten van deze webservicemethoden vereist. Nadat de versie voor algemene beschikbaarheid van deze webservices is gepubliceerd, zal Microsoft redelijke inspanningen betrachten om u vooraf op de hoogte te stellen van materiële updates van de webservice. Indien Microsoft van mening is dat een update wijzigingen aan clients noodzakelijk maakt met behulp van de webservice, blijft de vorige versie van de webservice beschikbaar gedurende ten minste 12 maanden na de uitgifte van de nieuwe versie. Klanten die in die periode geen upgrade uitvoeren, kunnen mogelijk geen gebruik maken van de website en de bijbehorende methoden. Klanten dienen zich ervoor te zorgen dat clients van de webservice foutloos blijven functioneren indien de volgende wijzigingen aan de handtekening van de webservice-interface worden aangebracht:

- Het toevoegen van een nieuwe, optionele parameter aan een bestaande webmethode die niet hoeft te worden opgegeven door oudere clients en die geen invloed heeft op het resultaat dat een oudere client ontvangt.
- Het toevoegen van een attribuut met een nieuwe naam aan een van de respons-REST-items of van aanvullende kolommen aan de respons-CSV.
- Het toevoegen van een nieuwe webmethode met een nieuwe naam die niet door de oudere clients wordt aangeroepen.

## <a name="update-notifications"></a>Updatemeldingen

U kunt een paar verschillende methoden gebruiken om e-mailmeldingen te ontvangen wanneer er wijzigingen in de IP-adressen en URL's worden gepubliceerd op de webservice.

- Als u een Microsoft Flow-oplossing wilt gebruiken, raadpleegt u [Microsoft Flow gebruiken om een e-mail te ontvangen over wijzigingen aan Office 365-IP-adressen en URL's](https://techcommunity.microsoft.com/t5/Office-365-Networking/Use-Microsoft-Flow-to-receive-an-email-for-changes-to-Office-365/m-p/240651).
- Als u een Azure Logic-app wilt implementeren met een ARM-sjabloon, raadpleegt u [Office 365 updatemelding (v 1.1)](https://aka.ms/ipurlws-updates-template).
- Als u uw eigen meldingenscript wilt schrijven met PowerShell, raadpleegt u [Send-MailMessage](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/send-mailmessage).

## <a name="exporting-a-proxy-pac-file"></a>Een PAC-bestand voor een proxy exporteren

[Get-PacFile](https://www.powershellgallery.com/packages/Get-PacFile) is een PowerShell-script dat de meest recente netwerkeindpunten leest uit het IP-adres en de webservice-URL van Office 365 en een voorbeeld van een PAC-bestand maakt. Voor meer informatie over het gebruiken van Get-PacFile, raadpleegt u [Een PAC-bestand gebruiken voor directe routering van belangrijk Office 365-verkeer](managing-office-365-endpoints.md#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).

## <a name="related-topics"></a>Verwante onderwerpen
  
[URL's en IP-adresbereiken voor Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Office 365-eindpunten beheren](managing-office-365-endpoints.md)
  
[Veelgestelde vragen over Office 365-eindpunten](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)

[Beginselen voor Office 365-netwerkverbinding](microsoft-365-network-connectivity-principles.md)

[Aanpassing van Office 365-netwerk en -prestaties](network-planning-and-performance.md)

[Office 365-netwerkverbinding beoordelen](assessing-network-connectivity.md)
  
[Mediakwaliteit en prestaties van de netwerkverbinding in Skype voor Bedrijven Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Uw netwerk instellen voor Skype voor Bedrijven Online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)

[Office 365-prestatieafstemming gebruikt basislijnen en prestatiegeschiedenis](performance-tuning-using-baselines-and-history.md)
  
[Prestatieproblemen met Office 365 oplossen: planning](performance-troubleshooting-plan.md)
