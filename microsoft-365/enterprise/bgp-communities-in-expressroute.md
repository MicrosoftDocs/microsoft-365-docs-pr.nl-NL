---
title: BGP-community's gebruiken in ExpressRoute voor Office 365-scenario's
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/26/2018
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099
description: Meer informatie over het gebruik van BGP-community's in Azure ExpressRoute om het aantal IP-voorvoegsels en de vereiste bandbreedte voor Office 365-scenario's te beheren.
ms.openlocfilehash: 9cb6980c1d8cc120f99cac087602856aeacf1adf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905210"
---
# <a name="using-bgp-communities-in-expressroute-for-office-365-scenarios"></a>BGP-community's gebruiken in ExpressRoute voor Office 365-scenario's

Verbinding maken met Office 365 met Azure ExpressRoute is gebaseerd op BGP-advertenties van specifieke IP-subnetten die netwerken vertegenwoordigen waarin Office 365-eindpunten worden geïmplementeerd. Vanwege het globale karakter van Office 365 en het aantal services dat Office 365 vormt, hebben klanten vaak behoefte aan het beheren van de advertenties die ze accepteren in hun netwerk. Het aantal IP-subnetten verminderen; in de rest van dit artikel ip-voorvoegsels genoemd, die moeten worden uitgelijnd met de terminologie van het BGP-netwerkbeheer, worden de volgende einddoelen voor klanten bereikt:
  
-  Het aantal geaccepteerde IP-voorvoegsels beheren: klanten met een interne netwerkinfrastructuur of netwerkprovider die slechts een beperkt aantal IP-voorvoegsels ondersteunt en klanten die een netwerkprovider hebben die kosten in rekening brengt voor het accepteren van voorvoegsels boven een beperkt aantal, willen het totale aantal voorvoegsels dat al is aangekondigd voor hun netwerk evalueren en selecteren welke Office 365-toepassingen het meest geschikt zijn voor ExpressRoute.

- Beheer de benodigde bandbreedte in het **Azure ExpressRoute-circuit:** klanten willen mogelijk de bandbreedte-envelop van de Office 365-services via het ExpressRoute-pad versus internetpad beheren. Hierdoor kunnen klanten ExpressRoute-bandbreedte reserveren voor specifieke toepassingen, zoals Skype voor Bedrijven en de resterende Office 365-toepassingen via het internetpad doorleiden.

Als u klanten met deze doelen wilt helpen, worden IP-voorvoegsels van Office 365 die via ExpressRoute worden aangekondigd, gemarkeerd met servicespecifieke BGP-communitywaarden, zoals wordt weergegeven in het onderstaande voorbeeld.
  
> [!NOTE]
> U kunt verwachten dat sommige netwerkverkeer dat is gekoppeld aan andere toepassingen, wordt opgenomen in de communitywaarde. Dit is verwacht gedrag voor een globale Software as a Service-aanbieding met gedeelde services en datacenters. Dit is waar mogelijk geminimaliseerd met de bovenstaande twee doelen, waarbij het aantal voorvoegsels en/of bandbreedte in gedachten wordt gehouden.

|**Service**|**BGP-communitywaarde**|**Opmerkingen**|
|:-----|:-----|:-----|
|Exchange Online\*  <br/> |12076:5010  <br/> |Inclusief Exchange- en EOP-services\*  <br/> |
|SharePoint Online\*  <br/> |12076:5020  <br/> |SharePoint Online  <br/> |
|Skype voor Bedrijven\*  <br/> |12076:5030  <br/> |Skype voor Bedrijven Online & Microsoft Teams-services  <br/> |
|Andere Office 365-services\*  <br/> |12076:5100  <br/> |Bevat Azure Active Directory (scenario's voor verificatie en adreslijstsynchronisatie) en Office 365 Portal-services  <br/> |
|\*Het bereik van servicescenario's in ExpressRoute wordt beschreven in het [Office 365-eindpunten-artikel.](./urls-and-ip-address-ranges.md)  <br/> \*\*In de toekomst kunnen aanvullende services en BGP-communitywaarden worden toegevoegd. [Zie de huidige lijst met BGP-community's.](/azure/expressroute/expressroute-routing)  <br/> |

## <a name="what-are-the-most-common-scenarios-for-using-bgp-communities"></a>Wat zijn de meest voorkomende scenario's voor het gebruik van BGP-community's?

Klanten kunnen BGP-community's gebruiken om groepen IP-voorvoegsels te reguleren die door hun netwerk worden geaccepteerd via Azure ExpressRoute, waardoor het totale AANTAL IP-voorvoegsels en de verwachte bandbreedte van bepaalde Office 365-services worden beïnvloed. Het is belangrijk om te begrijpen dat voor alle Office 365 internetverkeer is vereist, ongeacht het gebruik van Azure ExpressRoute- of BGP-community's. De volgende drie scenario's zijn de meest voorkomende toepassingen van deze functionaliteit.
  
### <a name="scenario-1-minimizing-the-number-of-office-365-ip-prefixes"></a>Scenario 1: Het aantal IP-voorvoegsels van Office 365 minimaliseren

Contoso Corporation is een bedrijf met 50.000 personen dat momenteel Office 365 voor Exchange Online en SharePoint Online gebruikt. Bij het controleren van ExpressRoute-vereisten bepaalt Contoso dat de netwerkapparaten op veel regionale locaties geen routeringstabelgrootten van meer dan 100 extra routegegevens kunnen verwerken. Contoso heeft het totale aantal IP-voorvoegsels beoordeeld dat ExpressRoute zou adverteren voor de volledige set Office 365-services en geconcludeerd dat het meer dan 100 is. Als u onder de 100 extra routegegevens wilt blijven, wordt het gebruik van ExpressRoute voor Office 365 door Contoso beperkt tot alleen de BGP-communitywaarde van SharePoint Online, 12076:5020, die is ontvangen via ExpressRoute Microsoft-peering.

|**BGP-communitylabel gebruikt**|**Functionaliteit die kan worden omgeleid via Azure ExpressRoute**|**Internetroutes vereist**|
|:-----|:-----|:-----|
|SharePoint  <br/> (12076:5020)  <br/> |SharePoint Online &amp; OneDrive voor Bedrijven  <br/> | DNS-, CRL-, &amp; CDN-aanvragen  <br/>  Alle andere Office 365-services die niet specifiek worden ondersteund via Azure ExpressRoute  <br/>  Alle andere Microsoft-cloudservices  <br/>  Office 365-portal, Office 365-verificatie, &amp; Office in een browser  <br/>  Exchange Online, Exchange Online Protection en Skype voor Bedrijven Online  <br/> |

> [!NOTE]
> Als u voor elke service een lager aantal voorvoegsels wilt bereiken, blijft er een minimale hoeveelheid overlap tussen services bestaan. Dit is te verwachten gedrag.
  
### <a name="scenario-2-scoping-expressroute-and-internal-bandwidth-use-to-some-office-365-services"></a>Scenario 2: ExpressRoute en interne bandbreedte gebruiken voor sommige Office 365-services

Fabrikam Inc, een grote multinational met een gedistribueerd heterogene netwerk, is abonnee van veel Office 365-services, waaronder; Exchange Online, SharePoint Online en Skype voor Bedrijven Online. De interne routeringsinfrastructuur van Fabrikam kan duizenden IP-voorvoegsels in de routeringstabellen verwerken. Fabrikam wil echter alleen ExpressRoute en interne bandbreedte inrichten voor Office 365-toepassingen die het meest gevoelig zijn voor netwerkprestaties en hun bestaande internetbandbreedte gebruiken voor alle andere Office 365-toepassingen.
  
Daarom heeft Fabrikam de bandbreedte van Azure ExpressRoute beperkt tot alleen de BGP-communitywaarde van Skype voor Bedrijven Online, 12076:5030, ontvangen via ExpressRoute Microsoft-peering. Het resterende netwerkverkeer dat is gekoppeld aan Office 365, blijft gebruikmaken van de internet-uitgangspunten.

|**BGP-communitylabel gebruikt**|**Functionaliteit die kan worden omgeleid via Azure ExpressRoute**|**Internetroutes vereist**|
|:-----|:-----|:-----|
|Skype voor Bedrijven  <br/> (12076:5030)  <br/> |Skype SIP-signalering, downloads, spraak, video en bureaublad delen  <br/> | DNS-, CRL-, &amp; CDN-aanvragen  <br/>  Alle andere Office 365-services die niet specifiek worden ondersteund via Azure ExpressRoute  <br/>  Alle andere Microsoft-cloudservices  <br/>  Office 365-portal, Office 365-verificatie, &amp; Office in een browser  <br/>  Skype voor Bedrijven-telemetrie, snelle tips voor Skype-client, openbare chatverbinding  <br/>  Exchange Online, Exchange Online Protection en SharePoint Online  <br/> |

### <a name="scenario-3-scoping-azure-expressroute-for-office-365-services-only"></a>Scenario 3: Alleen Azure ExpressRoute voor Office 365-services kopiëren

Woodgrove Bank is een klant van verschillende Microsoft-cloudservices, waaronder Office 365. Na de evaluatie van de netwerkcapaciteit en het verbruik besluit Woodgrove Bank Azure ExpressRoute te implementeren als het voorkeurspad voor de ondersteunde Office 365-services. De routeringstabellen ondersteunen de volledige set IP-voorvoegsels van Office 365 en de Azure ExpressRoute-circuits die ze hebben ingericht, ondersteunen alle verwachte bandbreedte- en latentiebehoeften.
  
Om ervoor te zorgen dat netwerkverkeer is gekoppeld aan andere Microsoft-cloudservices dan Office 365, wordt het gebruik van ExpressRoute voor Office 365 beperkt tot alle IP-voorvoegsels die zijn gemarkeerd met specifieke BGP-communitywaarden van Office 365, 12076:5010, 12076:5020, 12076:5030, 12076:5100.

|**BGP-communitylabel gebruikt**|**Functionaliteit die kan worden omgeleid via Azure ExpressRoute**|**Internetroutes vereist**|
|:-----|:-----|:-----|
|Exchange, Skype voor Bedrijven & Microsoft Teams, SharePoint, &amp; andere services  <br/> (12076:5010, 12076:5020, 12076:5030, 12076:5100)  <br/> |Exchange Online &amp; Exchange Online Protection  <br/> SharePoint Online &amp; OneDrive voor Bedrijven  <br/> Skype SIP-signalering, downloads, spraak, video en bureaublad delen  <br/> Office 365-portal, Office 365-verificatie, &amp; Office in een browser  <br/> | DNS-, CRL-, &amp; CDN-aanvragen  <br/>  Alle andere Office 365-services die niet specifiek worden ondersteund via Azure ExpressRoute  <br/>  Alle andere Microsoft-cloudservices  <br/> |

## <a name="key-planning-considerations-to-using-bgp-communities"></a>Belangrijke planningsoverwegingen voor het gebruik van BGP-community's

Klanten die gebruik willen maken van BGP-community's om te bepalen hoe ExpressRoute wordt aangekondigd en verspreid via het klantennetwerk, moeten rekening houden met de volgende overwegingen:
  
- Bij het gebruik van BGP-community's in uw netwerkontwerp is het belangrijk om ervoor te zorgen dat de routesymmetrie nog steeds behouden blijft. In sommige gevallen kan de toevoeging of verwijdering van BGP-community's leiden tot een situatie waarin symmetrische routering is verbroken en de routeringsconfiguratie moet worden bijgewerkt om symmetrische routering opnieuw tot stand te brengen.

- Het kopiëren van Azure ExpressRoute met BGP-communitywaarden is een actie van de klant. Microsoft maakt reclame voor alle IP-voorvoegsels die zijn gekoppeld aan de peeringrelatie, ongeacht de scoping die door de klant is geconfigureerd.

- Azure ExpressRoute ondersteunt geen acties op het microsoft-netwerk op basis van door klanten toegewezen BGP-community's.

- De IP-voorvoegsels die door Office 365 worden gebruikt, worden alleen gemarkeerd met servicespecifieke BGP-communitywaarden, locatiespecifieke BGP-community's worden niet ondersteund. Office 365-services zijn globaal van aard, het filteren van voorvoegsels op basis van de locatie van de tenant of gegevens in de Office 365-cloud wordt niet ondersteund. De aanbevolen methode is het configureren van uw netwerk om het kortste of meest voorkeursnetwerkpad te coördineren van de netwerklocatie van de gebruiker naar het globale Microsoft-netwerk, ongeacht de fysieke locatie van het IP-adres van de Office 365-service die ze aanvragen.

- De IP-voorvoegsels in elke BGP-communitywaarde vertegenwoordigen een subnet dat IP-adressen bevat voor de Office 365-toepassing die aan de waarde is gekoppeld. In sommige gevallen heeft meer dan één Office 365-toepassing IP-adressen in een subnet, wat resulteert in een IP-voorvoegsel dat in meer dan één communitywaarde wordt gebruikt. Dit wordt verwacht, maar zelden, als gevolg van toewijzingsfragmentatie en heeft geen invloed op de doelstellingen voor het aantal voorvoegsels of bandbreedtebeheer. Klanten worden aangeraden de benadering 'toestaan wat nodig is' te gebruiken in plaats van 'weigeren wat niet nodig is' wanneer ze gebruikmaken van BGP-community's voor Office 365 om het effect te minimaliseren.

- Als u BGP-community's gebruikt, worden de onderliggende vereisten voor netwerkconnectiviteit of -configuratie niet gewijzigd die nodig zijn voor het gebruik van Office 365. Klanten die toegang willen krijgen tot Office 365, moeten nog steeds toegang hebben tot internet.

- Het kopiëren van Azure ExpressRoute met BGP-community's is alleen van invloed op de routes die uw interne netwerk kan zien via de Microsoft-peeringrelatie. Mogelijk moet u aanvullende configuraties op toepassingsniveau maken, zoals het gebruik van een PAC- of WPAD-configuratie in combinatie met de routering met bereik.

- Naast het gebruik van de door Microsoft toegewezen BGP-community's, kunnen klanten ervoor kiezen om hun eigen BGP-community's toe te wijzen aan IP-voorvoegsels van Office 365 die via Azure ExpressRoute zijn geleerd om de interne routering te beïnvloeden. Een populaire use case is het toewijzen van een op locatie gebaseerde BGP-community aan alle routes die zijn geleerd via elke opgegeven ExpressRoute-peeringlocatie en vervolgens die informatie downstream in het klantennetwerk gebruiken om het kortste of meest voorkeursnetwerkpad naar het Microsoft-netwerk te coördineren. Het gebruik van klant toegewezen BGP-community's met ExpressRoute voor Office 365-scenario's valt buiten het bereik van Microsoft-beheer of zichtbaarheid.

Hier is een korte koppeling die u kunt gebruiken om terug te komen: [https://aka.ms/bgpexpressroute365]() .
  
## <a name="related-topics"></a>Verwante onderwerpen

[Office 365-netwerkverbinding beoordelen](assessing-network-connectivity.md)
  
[Azure ExpressRoute voor Office 365](azure-expressroute.md)
  
[ExpressRoute voor Office 365-connectiviteit beheren](managing-expressroute-for-connectivity.md)
  
[Routeren met ExpressRoute voor Office 365](routing-with-expressroute.md)
  
[Netwerkplanning met ExpressRoute voor Office 365](network-planning-with-expressroute.md)
  
[Mediakwaliteit en prestaties van de netwerkverbinding in Skype voor Bedrijven Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[ExpressRoute en QoS in Skype voor Bedrijven Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Oproepstroom met ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[ExpressRoute implementeren voor Office 365](implementing-expressroute.md)
  
[Ondersteuning voor BGP-community's](/azure/expressroute/expressroute-routing)
  
[Office 365-prestatieafstemming met behulp van basislijnen en prestatiegeschiedenis](performance-tuning-using-baselines-and-history.md)
  
[Prestatieproblemen met Office 365 oplossen: planning](performance-troubleshooting-plan.md)
  
[Azure ExpressRoute voor Office 365-training](https://channel9.msdn.com/series/aer)