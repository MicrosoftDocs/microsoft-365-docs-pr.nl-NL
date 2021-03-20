---
title: Netwerken die inhoud leveren
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/15/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 0140f704-6614-49bb-aa6c-89b75dcd7f1f
description: Gebruik deze informatie voor meer informatie over hoe Office 365 cdn's (Content Delivery Networks) gebruikt om de prestaties te verbeteren.
ms.openlocfilehash: 1a963d14df14e8644072a159e35c8590f953dae6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911094"
---
# <a name="content-delivery-networks-cdns"></a>Content Delivery Networks (CDN's)

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

CDN's helpen Office 365 snel en betrouwbaar te houden voor eindgebruikers. Cloudservices zoals Office 365 gebruiken CDN's om statische assets dichter bij de browsers te cachen met het verzoek om downloads te versnellen en de waargenomen latentie van eindgebruikers te verminderen. De informatie in dit onderwerp helpt u meer over inhoudsbezorgingsnetwerken (CDN's) en hoe ze worden gebruikt door Office 365.

## <a name="what-exactly-is-a-cdn"></a>Wat is een CDN precies?

Een CDN is een geografisch gedistribueerd netwerk dat bestaat uit proxy- en bestandsservers in datacenters die zijn verbonden door snelle backbonenetwerken. CDN's worden gebruikt om de latentie en laadtijden voor een opgegeven set bestanden en objecten op een website of service te verminderen. Een CDN kan vele duizenden eindpunten hebben voor een optimale service van binnenkomende aanvragen vanaf elke locatie.

CDN's worden vaak gebruikt voor snellere downloads van algemene inhoud voor een website of service, zoals javascript-bestanden, pictogrammen en afbeeldingen, en kunnen ook persoonlijke toegang bieden tot gebruikersinhoud, zoals bestanden in SharePoint Online-documentbibliotheken, streaming mediabestanden en aangepaste code.

CDN's worden gebruikt door de meeste zakelijke cloudservices. Cloudservices zoals Office 365 hebben miljoenen klanten die een mix van eigen inhoud (zoals e-mailberichten) en algemene inhoud (zoals pictogrammen) tegelijk downloaden. Het is efficiënter om afbeeldingen die iedereen gebruikt, zoals pictogrammen, zo dicht mogelijk bij de computer van de gebruiker te zetten. Het is niet praktisch voor elke cloudservice om CDN-datacenters te bouwen die deze algemene inhoud opslaan in elk grootstedelijk gebied, of zelfs in elke belangrijke internethub over de hele wereld, dus sommige van deze CDN's worden gedeeld.

## <a name="how-do-cdns-make-services-work-faster"></a>Hoe zorgen CDN's ervoor dat services sneller werken?

Als u veelgebruikte objecten, zoals siteafbeeldingen en pictogrammen, keer op keer downloadt, kan de netwerkbandbreedte worden overgenomen die beter kan worden gebruikt voor het downloaden van belangrijke persoonlijke inhoud, zoals e-mail of documenten. Omdat Office 365 een architectuur gebruikt die CDN's bevat, kunnen de pictogrammen, scripts en andere algemene inhoud worden gedownload van servers die dichter bij clientcomputers staan, zodat de downloads sneller verlopen. Dit betekent snellere toegang tot uw persoonlijke inhoud, die veilig is opgeslagen in Office 365-datacenters.

CDN's helpen de prestaties van de cloudservice op verschillende manieren te verbeteren:

- CDN's verplaatsen een deel van het netwerk en het downloaden van bestanden weg van de cloudservice, waardoor cloudservicebronnen worden vrij gemaakt voor het leveren van gebruikersinhoud en andere services doordat er minder behoefte is aan aanvragen voor statische assets.
- CDN's zijn speciaal ontworpen om bestandstoegang met lage latentie te bieden door krachtige netwerken en bestandsservers te implementeren en door gebruik te maken van bijgewerkte netwerkprotocollen, zoals [HTTP/2,](https://en.wikipedia.org/wiki/HTTP/2) met zeer efficiënte compressie en multiplexing aanvragen.
- CDN-netwerken gebruiken veel globaal gedistribueerde eindpunten om inhoud zo dicht mogelijk beschikbaar te maken voor gebruikers.

## <a name="the-office-365-cdn"></a>Het Office 365-CDN

Met het ingebouwde Office 365 Content Delivery Network (CDN) kunnen Office 365-beheerders betere prestaties leveren voor de SharePoint Online-pagina's van hun organisatie door statische assets dichter bij de browsers te zetten waar ze om vragen. Dit helpt downloads te versnellen en de latentie te verminderen. Het OFFICE 365-CDN gebruikt het [HTTP/2-protocol](https://en.wikipedia.org/wiki/HTTP/2) voor verbeterde compressie- en downloadsnelheden.

> [!NOTE]
> Het Office 365-CDN is alleen beschikbaar voor tenants in de **productie-cloud** (wereldwijd). Tenants in de cloud van de Amerikaanse overheid, China en Duitsland ondersteunen momenteel geen Office 365-CDN.

Het Office 365-CDN bestaat uit meerdere CDN's waarmee u statische assets op meerdere locaties of _origins_ kunt hosten en deze kunt gebruiken vanuit globale snelle netwerken. Afhankelijk van het type inhoud dat u wilt hosten in het Office  365-CDN, kunt u openbare origins, **privé-origins** of beide toevoegen.

![Conceptuele office 365-cdn-diagram](../media/O365-CDN/o365-cdn-flow-transparent.svg "Conceptuele office 365-cdn-diagram")

Inhoud in **openbare** origins binnen het Office 365-CDN is anoniem toegankelijk en kan worden gebruikt door iedereen die URL's heeft voor gehoste assets. Omdat toegang tot inhoud in openbare origins anoniem is, moet u deze alleen gebruiken om niet-gevoelige algemene inhoud in de cache op te slaan, zoals javascript-bestanden, scripts, pictogrammen en afbeeldingen. Het OFFICE 365-CDN wordt standaard gebruikt voor het downloaden van algemene resourceactiva, zoals de Office 365-clienttoepassingen van een openbare origin.

**Privé-origins** binnen het Office 365-CDN bieden persoonlijke toegang tot gebruikersinhoud, zoals SharePoint Online-documentbibliotheken, sites en eigen afbeeldingen. Toegang tot inhoud in privé-origins wordt beveiligd met dynamisch gegenereerde tokens, zodat deze alleen toegankelijk is voor gebruikers met machtigingen voor de oorspronkelijke documentbibliotheek of opslaglocatie. Privé-origins in het Office 365-CDN kunnen alleen worden gebruikt voor SharePoint Online-inhoud en u hebt alleen toegang tot activa via omleiding vanuit uw SharePoint Online-tenant.

De Office 365 CDN-service is opgenomen als onderdeel van uw SharePoint Online-abonnement.

Zie Het Office 365-netwerk voor inhoudsbezorging gebruiken met SharePoint Online voor meer informatie over het gebruik van het Office [365-CDN.](use-microsoft-365-cdn-with-spo.md)

Als u een reeks korte video's wilt bekijken met conceptuele en HOWTO-informatie over het gebruik van het Office 365-CDN, gaat u naar het [YouTube-kanaal SharePoint Developer Patterns and Practices.](https://aka.ms/sppnp-videos)

## <a name="other-microsoft-cdns"></a>Andere Microsoft CDN's

Hoewel u geen deel uitmaakt van het Office 365-CDN, kunt u deze CDN's in uw Office 365-tenant gebruiken voor toegang tot SharePoint-ontwikkelbibliotheken, aangepaste code en andere doeleinden die buiten het bereik van het Office 365-CDN vallen.

### <a name="azure-cdn"></a>Azure CDN

>[!NOTE]
>Vanaf het derde kwartaal van 2020 begint SharePoint Online met het innen van video's op het Azure CDN ter ondersteuning van verbeterde videoweergave en betrouwbaarheid. Populaire video's worden gestreamd vanaf het CDN-eindpunt dat het dichtst bij de gebruiker staat. Deze gegevens blijven binnen de nalevingsgrens van Microsoft 365. Dit is een gratis service voor alle tenants en u hoeft geen actie van de klant te configureren.

U kunt het Azure CDN gebruiken om uw eigen **CDN-exemplaar** te implementeren voor het hosten van aangepaste webonderdelen, bibliotheken en andere resourceactiva, waarmee u toegangstoetsen kunt toepassen op uw CDN-opslag en meer controle over uw CDN-configuratie kunt uitoefenen. Gebruik van het Azure CDN is niet gratis en hiervoor is een Azure-abonnement vereist.

Zie [Quickstart: Een Azure-opslagaccount integreren](/azure/cdn/cdn-create-a-storage-account-with-cdn)met Azure CDN voor meer informatie over het configureren van een Azure CDN-exemplaar.

Zie Uw [SharePoint-webonderdeel](/sharepoint/dev/spfx/web-parts/get-started/deploy-web-part-to-cdn)aan de clientzijde implementeren naar Azure CDN voor een voorbeeld van hoe het Azure CDN kan worden gebruikt voor het hosten van SharePoint-webonderdelen.

Zie Azure CDN beheren [met PowerShell](/azure/cdn/cdn-manage-powershell)voor informatie over de Azure CDN PowerShell-module.

### <a name="microsoft-ajax-cdn"></a>Microsoft Ajax CDN

Microsoft's **Ajax CDN** is een alleen-lezen CDN dat veel populaire ontwikkelbibliotheken biedt, waaronder jQuery (en alle andere bibliotheken), ASP.NET Ajax, Bootstrap, Knockout.js en anderen.
  
Als u deze scripts in uw project wilt opnemen, vervangt u alle verwijzingen naar deze openbare bibliotheken door verwijzingen naar het CDN-adres in plaats van deze op te nemen in uw project zelf. Gebruik bijvoorbeeld de volgende code om een koppeling te maken naar jQuery:

``` html
<script src=https://ajax.aspnetcdn.com/ajax/jquery-2.1.1.js> </script>
```

Zie [Microsoft Ajax CDN](/aspnet/ajax/cdn/overview)voor meer informatie over het gebruik van het Microsoft Ajax CDN.

## <a name="how-does-office-365-use-content-from-a-cdn"></a>Hoe gebruikt Office 365 inhoud van een CDN?

Ongeacht het CDN dat u configureert voor uw Office 365-tenant, is het basisproces voor het ophalen van gegevens hetzelfde.

1. Uw client (een browser of Office-clienttoepassing) vraagt gegevens op van Office 365.

2. Office 365 retourneert de gegevens rechtstreeks naar uw client of, als de gegevens deel uitmaken van een set inhoud die wordt gehost door het CDN, wordt uw client omgeleid naar de CDN-URL.

    a. Als de gegevens al in de cache zijn opgeslagen in een _openbare_ origin, downloadt uw client de gegevens rechtstreeks van de dichtstbijzijnde CDN-locatie naar uw client.

    b. Als de gegevens al in  de cache zijn opgeslagen in een privé-origin, controleert de CDN-service de machtigingen van uw Office 365-gebruikersaccount voor de origin. Als u machtigingen hebt, genereert SharePoint Online dynamisch een aangepaste URL die bestaat uit het pad naar het activum in het CDN en twee toegangstokens en retourneert de aangepaste URL naar uw client. Uw client downloadt de gegevens vervolgens rechtstreeks van de dichtstbijzijnde CDN-locatie naar uw client met de aangepaste URL.

3. Als de gegevens niet in de cache worden opgeslagen bij het CDN, worden de gegevens op het CDN-knooppunt opgeslagen vanuit Office 365 en worden de gegevens vervolgens een periode in de cache opgeslagen nadat de gegevens door de client zijn gedownload.

Het CDN becijfert het dichtstbijzijnde datacenter van de browser van de gebruiker en downloadt de gevraagde gegevens via omleiding. CDN-omleiding is snel en kan gebruikers veel downloadtijd besparen.

## <a name="how-should-i-set-up-my-network-so-that-cdns-work-best-with-office-365"></a>Hoe moet ik mijn netwerk zo instellen dat CDN's het beste werken met Office 365?

Het minimaliseren van latentie tussen clients in uw netwerk en CDN-eindpunten is de belangrijkste overweging voor het waarborgen van optimale prestaties. U kunt de best practices gebruiken die worden beschreven in Het beheren van [Office 365-eindpunten](managing-office-365-endpoints.md) om ervoor te zorgen dat clientbrowsers via uw netwerkconfiguratie rechtstreeks toegang hebben tot het CDN in plaats van cdn-verkeer te routeren via centrale proxies om onnodige latentie te voorkomen.

U kunt ook [office 365-netwerkconnectiviteitsprincipes](./microsoft-365-network-connectivity-principles.md) lezen om inzicht te krijgen in de concepten achter het optimaliseren van office 365-netwerkprestaties.

## <a name="is-there-a-list-of-all-the-cdns-that-office-365-uses"></a>Is er een lijst met alle CDN's die office 365 gebruikt?

De CDN's die door Office 365 worden gebruikt, kunnen altijd worden gewijzigd en in veel gevallen zijn er meerdere CDN-partners geconfigureerd voor het geval er een niet beschikbaar is. De primaire CDN's die door Office 365 worden gebruikt, zijn:

|CDN  |Company  |Gebruik  |Koppeling  |
|---------|---------|---------|---------|
|Office 365 CDN     |Akamai         |Algemene activa in openbare origins, SharePoint-gebruikersinhoud in privé-origins         |[Het Office 365-netwerk voor inhoudsbezorging gebruiken met SharePoint Online](use-microsoft-365-cdn-with-spo.md)         |
|Azure CDN     |Microsoft         |Aangepaste code, SharePoint Framework-oplossingen         |[Microsoft Azure CDN](https://azure.microsoft.com/documentation/services/cdn/)         |
|Microsoft Ajax CDN (alleen-lezen)     |Microsoft         |Veelgebruikte bibliotheken voor Ajax, jQuery, ASP.NET, Bootstrap, Knockout.js enzovoort.         |[Microsoft Ajax CDN](/aspnet/ajax/cdn/overview)         |

## <a name="what-performance-gains-does-a-cdn-provide"></a>Welke prestatiewinst levert een CDN op?

Er zijn veel factoren die betrokken zijn bij het meten van specifieke verschillen in prestaties tussen gegevens die rechtstreeks vanuit Office 365 zijn gedownload en gegevens die zijn gedownload van een specifiek CDN, zoals uw locatie ten opzichte van uw tenant en het dichtstbijzijnde CDN-eindpunt, het aantal activa op een pagina dat door het CDN wordt weergegeven, en tijdelijke wijzigingen in netwerklatentie en bandbreedte. Een eenvoudige A/B-test kan echter helpen om het verschil in downloadtijd voor een specifiek bestand aan te geven.

De volgende schermafbeeldingen illustreren het verschil in downloadsnelheid tussen de oorspronkelijke bestandslocatie in Office 365 en hetzelfde bestand dat wordt gehost op het [Microsoft Ajax Content Delivery Network.](/aspnet/ajax/cdn/overview) Deze schermafbeeldingen zijn afkomstig van **het tabblad Netwerk** in de hulpprogramma's voor ontwikkelaars van Internet Explorer 11. Deze schermafbeeldingen geven de latentie weer op de populaire bibliotheek jQuery. Als u dit scherm wilt weergeven, drukt u  in Internet Explorer op **F12** en selecteert u het tabblad Netwerk dat wordt gesymboliseerd met een Wi-Fi pictogram.
  
![Schermafbeelding van F12 Network](../media/930541fd-af9b-434a-ae18-7bda867be128.png)
  
In deze schermafbeelding ziet u de bibliotheek die is geüpload naar de galerie met basispagina's op de SharePoint Online-site zelf. De tijd die nodig was om de bibliotheek te uploaden, is 1,51 seconden.
  
![Schermafbeelding van laadtijd 1,51s](../media/64225c79-fa53-480f-81cd-0d351674320e.png)
  
In de tweede schermafbeelding ziet u hetzelfde bestand dat wordt geleverd door het CDN van Microsoft. Deze keer is de latentie ongeveer 496 milliseconden. Dit is een grote verbetering en laat zien dat een hele seconde wordt afgeschoren van de totale tijd om het object te downloaden.
  
![Schermafbeelding van laadtijden in 469 ms](../media/6a553cc3-25a0-42c1-aae7-4aebbc2eb4c3.png)

## <a name="is-my-data-safe"></a>Zijn mijn gegevens veilig?

We doen er alles aan om de gegevens van uw bedrijf te beschermen. Gegevens die zijn opgeslagen in het Office 365-CDN, worden zowel onderweg als in rust versleuteld en toegang tot gegevens in het Office 365 SharePoint-CDN wordt beveiligd door office 365-gebruikersmachtigingen en tokenautorisatie. Aanvragen voor gegevens in het Office 365 SharePoint-CDN moeten worden doorverwezen (omgeleid) vanuit uw Office 365-tenant of er wordt geen autorisatie-token gegenereerd.

Om ervoor te zorgen dat uw gegevens veilig blijven, raden we u aan nooit gebruikersinhoud of andere gevoelige gegevens op te slaan in een openbaar CDN. Omdat toegang tot gegevens in een openbaar CDN anoniem is, mogen openbare CDN's alleen worden gebruikt voor het hosten van algemene inhoud, zoals webscriptbestanden, pictogrammen, afbeeldingen en andere niet-gevoelige assets.

> [!NOTE]
> Cdn-providers van derden hebben mogelijk privacy- en compliancestandaarden die afwijken van de toezeggingen die zijn beschreven in het Office 365-vertrouwenscentrum. Gegevens die via de CDN-service in de cache zijn opgeslagen, voldoen mogelijk niet aan de voorwaarden voor microsoft-gegevensverwerking (DPT) en kunnen buiten de nalevingsgrenzen van het Office 365-vertrouwenscentrum staan.

Ga als volgt te werk voor uitgebreide informatie over privacy en gegevensbescherming voor Office 365 CDN-providers:  

- Meer informatie over privacy en gegevensbescherming van Office 365 in het [Microsoft Trust Center](https://www.microsoft.com/trustcenter)
- Meer informatie over de privacy en gegevensbescherming van Akamai vindt u in [het Akamai Privacy Trust Center](https://www.akamai.com/us/en/about/compliance/data-protection-at-akamai.jsp)
- Meer informatie over Azure-privacy en gegevensbescherming in [het Azure Trust Center](https://azure.microsoft.com/overview/trusted-cloud/)

## <a name="how-can-i-secure-my-network-with-all-these-3rd-party-services"></a>Hoe kan ik mijn netwerk beveiligen met al deze services van derden?

Als u gebruik maakt van een uitgebreide set partnerservices, kan Office 365 worden uitgebreid en voldaan aan de beschikbaarheidsvereisten en de gebruikerservaring verbeteren wanneer u Office 365 gebruikt. De services van derden die office 365 gebruiken, bevatten beide lijsten voor het intrekken van certificaten. zoals crl.microsoft.com of sa.symcb.com en CDN's; zoals r3.res.outlook.com. Elke CDN FQDN die wordt gegenereerd door Office 365 is een aangepaste FQDN voor Office 365. Als u op verzoek van Office 365 naar een FQDN wordt verzonden, kunt u er zeker van zijn dat de CDN-provider de FQDN en de onderliggende inhoud op die locatie beheert.
  
Voor klanten die aanvragen voor een Microsoft- of Office 365-datacenter willen scheiden van aanvragen die zijn bestemd voor een derde partij, hebben we richtlijnen voor het beheren van [Office 365-eindpunten opgeschreven.](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)

## <a name="is-there-a-list-of-all-the-fqdns-that-leverage-cdns"></a>Is er een lijst met alle FQDN's die gebruikmaken van CDN's?

De lijst met FQDN's en de manier waarop ze CDN's gebruiken, veranderen in de tijd. Raadpleeg de pagina gepubliceerde URL's en IP-adresbereiken van [Office 365](./urls-and-ip-address-ranges.md) om op de hoogte te blijven van de meest recente FQDN's die gebruikmaken van CDN's.

U kunt ook de [Office 365 IP-adres- en URL-webservice](microsoft-365-ip-web-service.md) gebruiken om de huidige OFFICE 365-URL's en IP-adresbereiken op te vragen die zijn opgemaakt als CSV of JSON.

## <a name="can-i-use-my-own-cdn-and-cache-content-on-my-local-network"></a>Kan ik mijn eigen CDN- en cache-inhoud op mijn lokale netwerk gebruiken?

We zijn voortdurend op zoek naar nieuwe manieren om de behoeften van onze klanten te ondersteunen en onderzoeken momenteel het gebruik van proxyoplossingen voor caching en andere on-premises CDN-oplossingen.

Hoewel het geen deel uitmaakt van het Office 365-CDN, kunt u ook het **Azure CDN** gebruiken voor het hosten van aangepaste webonderdelen, bibliotheken en andere resourceactiva, waarmee u toegangstoetsen kunt toepassen op uw CDN-opslag en meer controle kunt uitoefenen over uw CDN-configuratie. Gebruik van het Azure CDN is niet gratis en hiervoor is een Azure-abonnement vereist. Zie [Quickstart: Een Azure-opslagaccount integreren](/azure/cdn/cdn-create-a-storage-account-with-cdn)met Azure CDN voor meer informatie over het configureren van een Azure CDN-exemplaar.

## <a name="im-using-azure-expressroute-for-office-365-does-that-change-things"></a>Ik gebruik Azure ExpressRoute voor Office 365, verandert dat?

[Azure ExpressRoute voor Office 365](azure-expressroute.md) biedt een speciale verbinding met Office 365-infrastructuur die is gescheiden van het openbare internet. Dit betekent dat clients nog steeds verbinding moeten maken via niet-ExpressRoute-verbindingen om verbinding te maken met CDN's en andere Microsoft-infrastructuur die niet expliciet is opgenomen in de lijst met services die worden ondersteund door ExpressRoute. Raadpleeg Office 365-netwerkverkeersbeheer voor meer informatie over het routeerden van specifiek [verkeer,](routing-with-expressroute.md)zoals aanvragen die zijn bestemd voor CDN's.

## <a name="can-i-use-cdns-with-sharepoint-server-on-premises"></a>Kan ik CDN's on-premises gebruiken met SharePoint Server?

Het gebruik van CDN's is alleen zinvol in een SharePoint Online-context en moet worden vermeden met SharePoint Server. Dit komt omdat alle voordelen rond geografische locatie niet waar zijn als de server zich on-premises of geografisch toch sluit. Als er een netwerkverbinding is met de servers waarop deze wordt gehost, kan de site ook zonder internetverbinding worden gebruikt en kunnen de CDN-bestanden daarom niet worden opgehaald. Anders moet u een CDN gebruiken als er een beschikbaar en stabiel is voor de bibliotheek en bestanden die u nodig hebt voor uw site.
  
Met deze korte koppeling kunt u teruggaan: [https://aka.ms/o365cdns]()
  
## <a name="see-also"></a>Zie ook

[Beginselen voor Office 365-netwerkverbinding](./microsoft-365-network-connectivity-principles.md)

[Office 365-netwerkverbinding beoordelen](assessing-network-connectivity.md)

[Office 365-eindpunten beheren](managing-office-365-endpoints.md)

[URL's en IP-adresbereiken voor Office 365](./urls-and-ip-address-ranges.md)

[Het Office 365-netwerk voor inhoudsbezorging gebruiken met SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[Microsoft-vertrouwenscentrum](https://www.microsoft.com/trustcenter)

[Prestaties van Office 365 afstemmen](tune-microsoft-365-performance.md)