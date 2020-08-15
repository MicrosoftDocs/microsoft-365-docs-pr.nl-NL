---
title: Netwerken voor content levering
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
description: Gebruik deze informatie voor informatie over de manier waarop Office 365 gebruikmaakt van netwerken voor content levering (Cdn's) om de prestaties te verbeteren.
ms.openlocfilehash: 1c2230b76f354bf6f3de524b2b8c75b7d8c380e7
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689132"
---
# <a name="content-delivery-networks-cdns"></a>Netwerken voor content levering (Cdn's)

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Cdn's helpt Office 365 sneller en betrouwbaarder te houden voor eindgebruikers. Cloud Services zoals Office 365 Cdn's gebruiken voor het opslaan van statische activa dichter bij de browsers die hen vragen om de downloads te versnellen en de beschikbare latentie van de eindgebruikers te verminderen. In dit onderwerp vindt u meer informatie over netwerken voor content levering (Cdn's) en hoe deze worden gebruikt in Office 365.

## <a name="what-exactly-is-a-cdn"></a>Wat is een CDN precies?

Een CDN is een zeer grafisch Distributed netwerk met proxy-en bestandsservers in de datacenters die verbonden zijn via hogesnelheids backbone netwerken. Cdn's wordt gebruikt om latentie en laadtijden te beperken voor een opgegeven set bestanden en objecten op een website of service. Een CDN mag veel duizenden eindpunten bevatten voor optimale service van inkomende aanvragen van inkomende aanvragen van een locatie.

Cdn's worden vaak gebruikt voor betere downloads van algemene inhoud voor een website of service, zoals JavaScript-bestanden, pictogrammen en afbeeldingen, en kunnen ook persoonlijke toegang bieden aan gebruikers inhoud, zoals bestanden in SharePoint Online-documentbibliotheken, streaming-mediabestanden en aangepaste code.

Cdn's worden gebruikt door de meeste Enterprise Cloud-Services. Met beondersteuning van Cloud Services zoals Office 365 kunnen miljoenen klanten een mix van eigen inhoud (zoals e-mailberichten) en algemene inhoud (zoals pictogrammen) downloaden. Het is efficiënter om afbeeldingen in te stellen, zoals pictogrammen, zo dicht mogelijk bij de computer van de gebruiker. Het is niet praktisch voor elke cloudservice om CDN-datacenters te maken die deze algemene inhoud in elk terrein van de wereld opslaan, of zelfs in elke grote hub op internet, zodat sommige van deze Cdn's worden gedeeld.

## <a name="how-do-cdns-make-services-work-faster"></a>Hoe kunnen Cdn's de services sneller werken?

Gemeenschappelijke objecten zoals site afbeeldingen en pictogrammen die opnieuw kunnen worden gedownload, kunnen de netwerkbandbreedte overnemen die beter kan worden gebruikt voor het downloaden van belangrijke persoonlijke inhoud, zoals e-mail of documenten. Aangezien Office 365 gebruikmaakt van een architectuur die Cdn's bevat, kunt u de pictogrammen, scripts en andere algemene inhoud downloaden van servers dichter bij clientcomputers, zodat u de downloads sneller kunt uitvoeren. Dit betekent dat u sneller toegang hebt tot uw persoonlijke inhoud, die veilig wordt opgeslagen in Office 365-datacenters.

Cdn's Help om de prestaties van de cloudservice op verschillende manieren te verbeteren:

- Cdn's-verplaatsings onderdeel van het netwerk en het downloaden van bestanden van de cloudservice, het vrijmaken van cloudservice bronnen voor het uitvoeren van gebruikers inhoud en andere services, is minder nodig om aanvragen voor statische activa te dienen.
- Cdn's zijn gebouwd om toegang te bieden tot een bestands latentie door krachtige netwerken en bestandsservers te implementeren, en door gebruik te maken van bijgewerkte netwerkprotocollen zoals [http/2](https://en.wikipedia.org/wiki/HTTP/2) met zeer efficiënte compressie en aanvragen van multiplexing.
- CDN-netwerken gebruikmaken van een groot aantal globaal gedistribueerde eindpunten, zodat de inhoud zo dicht mogelijk toegankelijk is voor gebruikers.

## <a name="the-office-365-cdn"></a>Het Office 365 CDN

Het ingebouwde Office 365 Content Delivery Network (CDN) biedt beheerders van Office 365 de mogelijkheid om de prestaties van de SharePoint Online-pagina's van hun organisatie te verbeteren door de vaste activa dichter bij de door u gevraagde browsers te sparen, zodat downloads sneller en minder latentie kunnen worden. In Office 365 CDN wordt het [protocol http/2](https://en.wikipedia.org/wiki/HTTP/2) gebruikt voor verbeterde compressie-en downloadsnelheid.

> [!NOTE]
> Het Office 365 CDN is alleen beschikbaar voor tenants in de **productie** -Cloud (wereldwijd). Tenants in de Verenigde Staten voor de overheid, China en Duitsland ondersteunen momenteel het Office 365 CDN.

Het CDN van Office 365 is samengesteld uit meerdere Cdn's die u in staat stellen statische activa te hosten op meerdere locaties of _herkomst_en ze van wereldwijde hogesnelheids netwerken te bezorgen. Afhankelijk van het type inhoud dat u in het Office 365 CDN wilt hosten, kunt u **openbare** oorsprong, **persoonlijke** Origins of beide toevoegen.

![Office 365 CDN-conceptueel diagram](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN-conceptueel diagram")

Inhoud in **openbare** Origins in Office 365 CDN is anoniem toegankelijk en kan worden geopend door iedereen die url's heeft voor gehoste assets. Aangezien toegang tot inhoud in openbare Origin anoniem is, moet u deze alleen gebruiken voor het opslaan van niet-gevoelige algemene inhoud, zoals JavaScript-bestanden, scripts, pictogrammen en afbeeldingen. Het Office 365 CDN wordt standaard gebruikt voor het downloaden van algemene resource activa zoals de Office 365-clienttoepassingen van een openbare Origin.

**Persoonlijke** Origins in Office 365 CDN bieden persoonlijke toegang tot gebruikers inhoud, zoals documentbibliotheken van SharePoint Online, sites en eigen afbeeldingen. Toegang tot inhoud in persoonlijke Origins is beveiligd met dynamisch gegenereerde tokens, zodat deze alleen kan worden geopend door gebruikers met machtigingen voor de oorspronkelijke documentbibliotheek of opslaglocatie. Persoonlijke Origins in het Office 365-CDN kunnen alleen worden gebruikt voor SharePoint Online-inhoud en u kunt geen toegang krijgen tot activa via omleiding van de SharePoint Online-Tenant.

De Office 365 CDN-service maakt deel uit van uw SharePoint Online-abonnement.

Ga voor meer informatie over het gebruik van Office 365 CDN naar [het inhouds leverings netwerk van office 365 met SharePoint Online](use-microsoft-365-cdn-with-spo.md).

Als u een reeks korte Video's wilt bekijken over informatie over het gebruik van Office 365 CDN, gaat u naar het [YouTube-kanaal van de SharePoint-ontwikkel patronen en-procedures](https://aka.ms/sppnp-videos).

## <a name="other-microsoft-cdns"></a>Andere Microsoft-Cdn's

Hoewel u geen onderdeel van Office 365 CDN hebt, kunt u deze Cdn's in de Office 365-Tenant gebruiken voor toegang tot de ontwikkel bibliotheken van SharePoint, aangepaste code en andere functies die buiten het bereik van het Office 365-CDN vallen.

### <a name="azure-cdn"></a>Azure CDN

>[!NOTE]
>Vanaf Q3 2020 begint SharePoint Online om Video's in te zetten in het Azure CDN, zodat de video sneller en betrouwbaarder wordt. Populaire Video's worden vanaf het CDN-eindpunt naar de gebruiker gestreamd. Deze gegevens blijven binnen de nalevings grenzen van Microsoft 365. Dit is een gratis service voor alle tenants waarvoor geen klant actie hoeft te worden geconfigureerd.

U kunt met behulp van **Azure CDN** uw eigen CDN-exemplaar implementeren voor het hosten van aangepaste webonderdelen, Bibliotheken en andere bron activa, zodat u toegangstoetsen kunt toepassen op uw CDN-opslag en meer controle hebt over uw CDN-configuratie. Het gebruik van het Azure CDN is niet gratis en vereist een Azure-abonnement.

Zie voor meer informatie over het configureren van een Azure CDN-exemplaar [: een Azure-opslagaccount integreren met Azure CDN](https://docs.microsoft.com/azure/cdn/cdn-create-a-storage-account-with-cdn).

Zie [het webonderdeel SharePoint-client toepassen op Azure CDN](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/deploy-web-part-to-cdn)voor een voorbeeld van hoe het Azure-CDN kan worden gebruikt om SharePoint-webonderdelen te hosten.

Zie voor meer informatie over de Azure CDN PowerShell-module [Azure CDN beheren met PowerShell](https://docs.microsoft.com/azure/cdn/cdn-manage-powershell).

### <a name="microsoft-ajax-cdn"></a>Microsoft Ajax-CDN

De **Ajax-CDN** van Microsoft is een alleen-lezen CDN die tal van populaire ontwikkelaars bevat, waaronder jQuery (en alle andere bibliotheken), ASP.NET AJAX, bootstrap, Knockout.js en overige.
  
Als u deze scripts in uw project wilt opnemen, vervangt u verwijzingen naar de beschikbare bibliotheken met verwijzingen naar het CDN-adres in plaats van de scripts op te nemen in uw project zelf. Gebruik bijvoorbeeld de volgende code om een koppeling te maken naar jQuery:

``` html
<script src=https://ajax.aspnetcdn.com/ajax/jquery-2.1.1.js> </script>
```

Zie voor meer informatie over het gebruik van Microsoft Ajax CDN [Microsoft Ajax CDN](https://docs.microsoft.com/aspnet/ajax/cdn/overview).

## <a name="how-does-office-365-use-content-from-a-cdn"></a>Hoe gebruikt Office 365 inhoud van een CDN?

Ongeacht de CDN die u voor uw Office 365-Tenant configureert, is het basisproces voor het ophalen van gegevens hetzelfde.

1. De client (een browser of Office-clienttoepassing) vraagt om gegevens uit Office 365.

2. In Office 365 worden de gegevens rechtstreeks naar de client geretourneerd of wordt de client omgeleid naar de CDN-URL als de gegevens deel uitmaken van een set met gehoste inhoud van de CDN.

    a. Als de gegevens al _in de cache_ zijn opgeslagen, worden de gegevens in de client rechtstreeks vanaf de dichtstbijzijnde CDN-locatie naar uw client gedownload.

    b. Als de gegevens al in de cache zijn opgeslagen in een _persoonlijke_ Origin, controleert de CDN-service de machtigingen voor uw Office 365-gebruikersaccount voor de oorsprong. Als u over de juiste machtigingen beschikt, wordt in SharePoint Online een aangepaste URL met een aangepaste URL samengesteld die bestaat uit het pad naar het activum in de CDN en twee toegangstokens, en wordt de aangepaste URL van de client geretourneerd. De gegevens worden vervolgens via de aangepaste URL rechtstreeks vanaf de dichtstbijzijnde CDN-locatie naar de client gedownload.

3. Als de gegevens niet in de cache zijn opgeslagen, worden de gegevens uit Office 365 opgevraagd en worden de gegevens vervolgens in de cache opgeslagen wanneer de client de gegevens heeft gedownload.

De CDN ontstaat op het dichtstbijzijnde datacenter in de browser van de gebruiker en via omleiding wordt de gevraagde gegevens gedownload. CDN-omleiding is snel en bespaart gebruikers veel tijd om het bestand te downloaden.

## <a name="how-should-i-set-up-my-network-so-that-cdns-work-best-with-office-365"></a>Hoe kan ik mijn netwerk zo instellen dat Cdn's het beste werken met Office 365?

Het minimaliseren van de latentie tussen clients in uw netwerk en CDN-eindpunten is de belangrijkste overweging om optimale prestaties te garanderen. U kunt de aanbevolen procedures gebruiken voor het beheren van [Office 365-eindpunten voor het beheren van Office-eindpunten](managing-office-365-endpoints.md) om ervoor te zorgen dat uw netwerkconfiguratie door de centrale proxy's direct wordt gebruikt in plaats van het routeren van het gegevensblad.

U kunt ook de basis [principes van office 365-netwerkverbindingen](https://aka.ms/o365networkingprinciples) raadplegen voor informatie over de concepten achter het optimaliseren van de prestaties van het netwerk van Office 365.

## <a name="is-there-a-list-of-all-the-cdns-that-office-365-uses"></a>Is er een lijst met alle Cdn's die door Office 365 worden gebruikt?

Het Cdn's dat door Office 365 wordt gebruikt, is altijd te wijzigen en in veel gevallen zijn er meerdere CDN-partners geconfigureerd in het gebeurtenis account. De primaire Cdn's die wordt gebruikt door Office 365, zijn:

|CDN  |Company  |Gebruikt  |Verbindings  |
|---------|---------|---------|---------|
|Office 365 CDN     |Akamai         |Algemene activa in openbare Origin, SharePoint-gebruikers inhoud in persoonlijke oorsprong         |[Het Office 365-inhouds leverings netwerk gebruiken met SharePoint Online](use-microsoft-365-cdn-with-spo.md)         |
|Azure CDN     |Microsoft         |Aangepaste code, SharePoint Framework-oplossingen         |[Microsoft Azure CDN](https://azure.microsoft.com/documentation/services/cdn/)         |
|Microsoft Ajax CDN (alleen-lezen)     |Microsoft         |Veelgebruikte bibliotheken voor Ajax, jQuery, ASP.NET, bootstrap, Knockout.js etc.         |[Microsoft Ajax-CDN](https://docs.microsoft.com/aspnet/ajax/cdn/overview)         |

## <a name="what-performance-gains-does-a-cdn-provide"></a>Welke prestatieverbeteringen levert een CDN op?

Er bestaan diverse factoren waarmee de prestaties van bepaalde verschillen tussen de gegevens rechtstreeks vanuit Office 365 en gegevens uit een specifieke CDN, zoals uw locatie ten opzichte van de Tenant en het dichtstbijzijnde CDN-eindpunt, worden gemeten, het aantal assets op een pagina dat op een pagina wordt bediend, en overgangen in netwerklatentie en bandbreedte. Met een eenvoudige A/B-toets kunt u echter het verschil in de downloadtijd voor een specifiek bestand weergeven.

In de volgende schermafbeeldingen wordt het verschil tussen de downloadsnelheid weergegeven tussen de bestandslocatie in Office 365 en het bestand dat wordt gehost op het [Microsoft Ajax Content Delivery Network](https://docs.microsoft.com/aspnet/ajax/cdn/overview). Deze schermafbeeldingen zijn afkomstig van het tabblad **netwerk** in de hulpmiddelen voor ontwikkelaars van Internet Explorer 11. In deze schermafbeeldingen wordt de latentie weergegeven op de populaire bibliotheek jQuery. Als u dit scherm wilt weergeven, drukt u in Internet Explorer op **F12** en selecteert u het tabblad **netwerk** op basis van een Wi-Fi-pictogram.
  
![Schermafbeelding van F12-netwerk](../media/930541fd-af9b-434a-ae18-7bda867be128.png)
  
In deze schermafbeelding ziet u de bibliotheek die is geüpload naar de galerie met basispagina's op de SharePoint Online-site zelf. De tijd die het uploaden van de bibliotheek duurt 1,51 seconden.
  
![Schermafbeelding van laadtijd documentbibliotheek s](../media/64225c79-fa53-480f-81cd-0d351674320e.png)
  
De tweede schermafbeelding toont het bestand dat wordt bezorgd in het Microsoft CDN. Wanneer de latentie rondom 496 milliseconden valt. Dit is een grote verbetering en geeft aan dat een hele seconde de totale tijd voor het downloaden van het object verscheert.
  
![Schermafbeelding van laadtijden in 469 MS](../media/6a553cc3-25a0-42c1-aae7-4aebbc2eb4c3.png)

## <a name="is-my-data-safe"></a>Zijn mijn gegevens veilig?

We nemen ons de bescherming van de gegevens die uw bedrijf uitvoert. Gegevens die zijn opgeslagen in Office 365 CDN, worden versleuteld in transit en op rest, en toegang tot gegevens in het Office 365 SharePoint CDN wordt beveiligd door Office 365-gebruikersmachtigingen en Token autorisatie. Voor de gegevens in het Office 365 SharePoint-CDN moet een verwijzing worden gemaakt van de Office 365-Tenant of wordt er geen autorisatietoken gegenereerd.

Om ervoor te zorgen dat uw gegevens veilig blijven, raden we u aan dat u geen gebruikers inhoud of andere gevoelige gegevens opslaat in een openbaar CDN. Aangezien de toegang tot gegevens in een openbaar CDN anoniem is, mag openbare Cdn's alleen worden gebruikt om algemene inhoud te hosten, zoals Webbe schrift bestanden, pictogrammen, afbeeldingen en andere niet-gevoelige assets.

> [!NOTE]
> derden kunnen CDN-en compliance-providers hebben die verschillen van de toezeggingen die worden beschreven in het Vertrouwenscentrum van Office 365. Gegevens die via de CDN-service zijn gecached, komen mogelijk niet overeen met de Microsoft Data processing term (DPT) en mogelijk buiten de nalevings grenzen van het Office 365 Vertrouwenscentrum.

Voor uitgebreide informatie over privacy en gegevensbescherming voor Office 365 CDN-providers, gaat u naar het volgende:  

- Meer informatie over privacy en gegevensbescherming van Office 365 vindt u in het [Microsoft Vertrouwenscentrum](https://www.microsoft.com/trustcenter)
- Meer informatie over privacy en gegevensbescherming van Akamai in het [Akamai privacy Vertrouwenscentrum](https://www.akamai.com/us/en/about/compliance/data-protection-at-akamai.jsp)
- Meer informatie over Azure privacy en gegevensbescherming in het [Azure Vertrouwenscentrum](https://azure.microsoft.com/overview/trusted-cloud/)

## <a name="how-can-i-secure-my-network-with-all-these-3rd-party-services"></a>Hoe kan ik mijn netwerk beveiligen met al deze services van derden?

Met een uitgebreide set partnerservices kan Office 365 de beschikbaarheid van de beschikbaarheid en de beschikbaarheid voldoen en de gebruikerservaring verbeteren wanneer u Office 365 gebruikt. De Office 365-producten van derden bestaan uit beide certificaat intrekkingslijsten. zoals crl.microsoft.com of sa.symcb.com, en Cdn's; zoals r3.res.outlook.com. Elke CDN-FQDN die wordt gegenereerd door Office 365 is een aangepaste FQDN voor Office 365. Als u in het verzoek van Office 365 naar een FQDN verzendt, kunt u waarborgen dat de CDN-provider de FQDN en de onderliggende inhoud op die locatie beheert.
  
Voor klanten die aanvragen voor een Microsoft-of Office 365-datacenter met behulp van aanvragen die zijn bestemd voor een Microsoft-of Office-datacenter, hebben we instructies over het [beheren van Office 365-eindpunten](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)beschreven.

## <a name="is-there-a-list-of-all-the-fqdns-that-leverage-cdns"></a>Is er een lijst met alle FQDN-namen die gebruikmaken van Cdn's?

De lijst met FQDN-namen en hoe deze in de loop van de tijd Cdn's wijzigen. Zie de gepubliceerde pagina met [url's en IP-](https://go.microsoft.com/fwlink/p/?LinkID=293744) adresbereiken voor Office 365 om up-to-date te blijven van de meest recente FQDN-gegevens die gebruikmaken van cdn's.

U kunt ook het [IP-adres en de URL van office 365](microsoft-365-ip-web-service.md) gebruiken om de huidige Office 365-url's en IP-adresbereiken die zijn OPGEMAAKT als CSV of JSON aan te vragen.

## <a name="can-i-use-my-own-cdn-and-cache-content-on-my-local-network"></a>Kan ik mijn eigen CDN en cache-inhoud gebruiken op mijn lokale netwerk?

We zullen voortdurend op de aandacht voorzien van nieuwe manieren om onze klanten te ondersteunen en momenteel het gebruik van proxy oplossingen met cache en andere on-premises CDN-oplossingen verkennen.

Hoewel dit geen onderdeel uitmaakt van Office 365 CDN, kunt u ook het Azure- **CDN** gebruiken voor het hosten van aangepaste webonderdelen, Bibliotheken en andere bron activa, zodat u toegangstoetsen kunt toepassen op uw CDN-opslag en meer controle hebt over uw CDN-configuratie. Het gebruik van het Azure CDN is niet gratis en vereist een Azure-abonnement. Zie voor meer informatie over het configureren van een Azure CDN-exemplaar [: een Azure-opslagaccount integreren met Azure CDN](https://docs.microsoft.com/azure/cdn/cdn-create-a-storage-account-with-cdn).

## <a name="im-using-azure-expressroute-for-office-365-does-that-change-things"></a>Ik gebruik Azure ExpressRoute voor Office 365 en wil deze wijzigen?

[Azure ExpressRoute voor Office 365](azure-expressroute.md) biedt een speciale verbinding met de Office 365-infrastructuur die is gescheiden van het openbare Internet. Dit betekent dat clients nog steeds verbinding hoeven te maken via niet-ExpressRoute verbindingen, zodat ze verbinding kunnen maken met Cdn's en andere infrastructuur van Microsoft die niet expliciet is opgenomen in de lijst met services die worden ondersteund door ExpressRoute. Raadpleeg voor meer informatie over het routeren van specifieke verkeer, zoals aanvragen die zijn bestemd voor Cdn's, naar [Office 365 Network Traffic Management](routing-with-expressroute.md).

## <a name="can-i-use-cdns-with-sharepoint-server-on-premises"></a>Kan ik Cdn's gebruiken met SharePoint Server on-premises?

Het gebruik van Cdn's maakt alleen gebruik van een SharePoint Online-context en moet worden vermeden met de SharePoint-Server. Dit komt doordat alle voordelen van de geografische locatie niet waar zijn als de server on-premises of geografisch dicht bij de server staat. Als er ook een netwerkverbinding is met de servers waarop deze is gehost, kan de site worden gebruikt zonder Internet verbinding en de CDN-bestanden daarom niet ophalen. Anders moet u een CDN gebruiken als er een CDN beschikbaar en stabiel is voor de bibliotheek en bestanden die u nodig hebt voor uw site.
  
Met deze korte koppeling kunt u teruggaan: [https://aka.ms/o365cdns](https://aka.ms/o365cdns)
  
## <a name="see-also"></a>Zie ook

[Methoden voor netwerkverbindingen in Office 365](https://aka.ms/o365networkingprinciples)

[Een beoordeling van de netwerkverbinding van Office 365](assessing-network-connectivity.md)

[Office 365-eindpunten beheren](managing-office-365-endpoints.md)

[URL's en IP-adresbereiken voor Office 365](https://go.microsoft.com/fwlink/p/?LinkID=293744)

[Het Office 365-inhouds leverings netwerk gebruiken met SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[Microsoft-vertrouwenscentrum](https://www.microsoft.com/trustcenter)

[Prestaties van Office 365 afstemmen](tune-microsoft-365-performance.md)
