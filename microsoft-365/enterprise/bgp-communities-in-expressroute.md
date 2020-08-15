---
title: Het gebruik van BGP-community's in ExpressRoute voor Office 365-scenario's
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
description: Informatie over het gebruik van BGP-community's in azure ExpressRoute om het aantal IP-voorvoegsels en vereiste bandbreedte voor Office 365-scenario's te beheren.
ms.openlocfilehash: 3a1de8725ae967352723649e602d944ca6948310
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689397"
---
# <a name="using-bgp-communities-in-expressroute-for-office-365-scenarios"></a>Het gebruik van BGP-community's in ExpressRoute voor Office 365-scenario's

Verbinding maken met Office 365 met behulp van Azure ExpressRoute is gebaseerd op BGP-advertisements van specifieke IP-subnetten die netwerken aangeven waarop Office 365-eindpunten zijn geïmplementeerd. Door de algemene aard van Office 365 en het aantal services dat Office 365 vormt, hebben klanten vaak de advertenties die ze in hun netwerk willen accepteren. Het aantal IP-subnetten verminderen; naar het gebruik van IP-voorvoegsels in de rest van dit artikel voor het uitlijnen van de terminologie van het BGP-netwerkbeheer verloopt onder meer de volgende eindbereiken voor klanten:
  
- **De geadverteerde IP-voorvoegsels voor de geadverteerde IP** -voorkeuren beheren: klanten met een interne netwerkinfrastructuur of netwerkprovider die slechts ondersteuning biedt voor een beperkt aantal IP-voorvoegsels en klanten met een netwerkprovider die kosten voor het accepteren van voorvoegsels die hoger zijn dan een beperkte waarde, willen het totale aantal vooraf gedefinieerde 365 vooraf gedefinieerde oplossingen voor ExpressRoute evalueren.

- **De hoeveelheid bandbreedte die is vereist voor het Azure ExpressRoute-circuit beheren** -klanten kunnen de bandbreedte van de Office 365-Services beheren via het ExpressRoute-pad en het pad naar het internet. Hiermee kunnen klanten ExpressRoute bandbreedte reserveren voor specifieke toepassingen zoals Skype voor bedrijven en de resterende Office 365-toepassingen doorsturen via het Internet pad.

Om klanten hierbij te helpen, worden IP-voorvoegsels van Office 365 die worden aangekondigd via ExpressRoute, gelabeld met specifieke BGP-Community-waarden, zoals wordt weergegeven in het voorbeeld hieronder.
  
> [!NOTE]
> Het is mogelijk dat het netwerkverkeer dat is gekoppeld aan andere toepassingen, moet worden opgenomen in de Community value. Dit is verwacht gedrag voor een wereldwijd programma voor een service met gedeelde services en datacenters. Dit is waar mogelijk geminimaliseerd, met de twee bovenstaande doelstellingen, waarbij het aantal voorvoegsels en/of de bandbreedte in gedachten wordt beheerd.

|**Service**|**BGP-Communitywaarde**|**Opmerkingen**|
|:-----|:-----|:-----|
|Exchange Online\*  <br/> |12076:5010  <br/> |Inclusief Exchange-en EOP-Services\*  <br/> |
|SharePoint Online\*  <br/> |12076:5020  <br/> |SharePoint Online  <br/> |
|Skype voor bedrijven\*  <br/> |12076:5030  <br/> |Skype voor bedrijven online & Microsoft teams-Services  <br/> |
|Andere Office 365-Services\*  <br/> |12076:5100  <br/> |Inclusief Azure Active Directory (scenario's voor verificatie en adreslijstsynchronisatie) en Office 365 Portal-Services  <br/> |
|\* De reikwijdte service scenario's die deel uitmaken van ExpressRoute wordt beschreven in het artikel [Office 365-eindpunten](https://aka.ms/o365endpoints) .  <br/> \*\*U kunt in de toekomst extra services en BGP-Community-waarden toevoegen. [Zie de huidige lijst met BGP-community's](https://azure.microsoft.com/documentation/articles/expressroute-routing/).  <br/> |

## <a name="what-are-the-most-common-scenarios-for-using-bgp-communities"></a>Wat zijn de meest voorkomende scenario's voor het gebruik van BGP-community's?

Klanten kunnen gebruikmaken van BGP-community's voor het regelen van groepen IP-voorvoegsels die door hun netwerk worden geaccepteerd via Azure ExpressRoute, zodat het totale aantal IP-voorvoegsels en verwachte bandbreedte van bepaalde Office 365-Services wordt bepaald. Het is belangrijk dat u begrijpt dat voor alle Office 365-gebonden Internet-verkeer is vereist, ongeacht het gebruik van Azure ExpressRoute of BGP-Community's. De volgende drie scenario's vormen een veelvoorkomend gebruik van deze functie.
  
### <a name="scenario-1-minimizing-the-number-of-office-365-ip-prefixes"></a>Scenario 1: het minimaliseren van het aantal IP-voorvoegsels van Office 365

Contoso B.v. is een 50.000-persoon die momenteel gebruikmaakt van Office 365 voor Exchange Online en SharePoint Online. In de ExpressRoute-vereisten voor het beoordelen van de vereisten van Contoso worden de beschikbare routeringstabel 100 formaten voor de netwerkapparatuur voor de grote locaties niet verwerkt. Contoso heeft het totale aantal IP-voorvoegsels gecontroleerd dat ExpressRoute u adverteert voor de volledige set Office 365-Services en concludeert dat deze groter is dan 100. Om onder de 100 extra routevermeldingen te blijven staan, is het gebruik van ExpressRoute voor Office 365 uitsluitend van toepassing op de SharePoint Online-BGP-Community, 12076:5020, ontvangen via ExpressRoute Microsoft peering.

|**Gebruikte BGP-Community-tag**|**Functies die routeerbaar zijn via Azure ExpressRoute**|**Internet routes vereist**|
|:-----|:-----|:-----|
|SharePoint  <br/> (12076:5020)  <br/> |SharePoint Online &amp; OneDrive voor bedrijven  <br/> | DNS-, CRL-en &amp; CDN-aanvragen  <br/>  Alle andere Office 365-services die niet specifiek worden ondersteund via Azure ExpressRoute  <br/>  Alle andere Microsoft-cloudservices  <br/>  Office 365-Portal, Office 365-verificatie, &amp; Office in een browser  <br/>  Exchange Online, Exchange Online Protection en Skype voor bedrijven online  <br/> |

> [!NOTE]
> Als u het aantal lagere voorvoegsels voor elke service wilt bereiken, is er een minimale mate van afstand tussen de services. Dit is te verwachten gedrag.
  
### <a name="scenario-2-scoping-expressroute-and-internal-bandwidth-use-to-some-office-365-services"></a>Scenario 2: het bereik van ExpressRoute en interne bandbreedte beperken voor sommige Office 365-Services

Fabrikam Inc, een grote, multicore-onderneming met een Distributed heterod netwerk, is een abonnee van veel Office 365-Services, met inbegrip van; Exchange Online, SharePoint Online en Skype voor bedrijven online. De interne routeringsinfrastructuur van Fabrikam kan duizenden IP-voorvoegsels in de routeringstabellen verwerken. Fabrikam wil echter alleen ExpressRoute en interne bandbreedte voor Office 365-toepassingen inrichten die de meest gevoelige voor netwerkprestaties zijn en gebruikmaken van de bestaande Internet bandbreedte voor alle andere Office 365-toepassingen.
  
Daarom hebben fabrikam met fabrikam bereik de bandbreedte van Azure ExpressRoute naar de Skype voor bedrijven online-BGP-Community, 12076:5030, ontvangen via ExpressRoute Microsoft peering. Het resterende netwerkverkeer dat is gekoppeld aan Office 365, blijft gebruikmaken van de Internet eindpunten.

|**Gebruikte BGP-Community-tag**|**Functies die routeerbaar zijn via Azure ExpressRoute**|**Internet routes vereist**|
|:-----|:-----|:-----|
|Skype voor Bedrijven  <br/> (12076:5030)  <br/> |Skype SIP-signalering, downloads, spraak, video en delen van bureaublad  <br/> | DNS-, CRL-en &amp; CDN-aanvragen  <br/>  Alle andere Office 365-services die niet specifiek worden ondersteund via Azure ExpressRoute  <br/>  Alle andere Microsoft-cloudservices  <br/>  Office 365-Portal, Office 365-verificatie, &amp; Office in een browser  <br/>  Skype voor bedrijven-telemetrie, snelle tips voor de Skype-client, verbinding voor openbare CHATBERICHTEN  <br/>  Exchange Online, Exchange Online Protection en SharePoint Online  <br/> |

### <a name="scenario-3-scoping-azure-expressroute-for-office-365-services-only"></a>Scenario 3: het bereik van Azure ExpressRoute voor Office 365-Services

Woodgrove Bank is een klant van diverse Microsoft-cloudservices, waaronder Office 365. Na de beoordeling van de netwerkcapaciteit en de consumptie bank besluit om Azure ExpressRoute te implementeren als het gewenste pad voor de ondersteunde Office 365-Services. De routeringstabellen bieden ondersteuning voor de volledige set met IP-voorvoegsels van Office 365 en de Azure ExpressRoute-circuits die ze hebben ingericht voor de behoeften van de geprojecteerde bandbreedte en de latentie.
  
Om ervoor te zorgen dat netwerkverkeer dat is gekoppeld aan andere Microsoft-cloudservices dan Office 365, is het gebruik van ExpressRoute voor Office 365 voor alle IP-voorvoegsels die met Office 365 specifiek BGP-Community-waarden, 12076:5010, 12076:5020, 12076:5030, 12076:5100.

|**Gebruikte BGP-Community-tag**|**Functies die routeerbaar zijn via Azure ExpressRoute**|**Internet routes vereist**|
|:-----|:-----|:-----|
|Exchange, Skype voor bedrijven & Microsoft teams, SharePoint en &amp; andere services  <br/> (12076:5010, 12076:5020, 12076:5030, 12076:5100)  <br/> |Exchange Online &amp; Exchange Online Protection  <br/> SharePoint Online &amp; OneDrive voor bedrijven  <br/> Skype SIP-signalering, downloads, spraak, video en delen van bureaublad  <br/> Office 365-Portal, Office 365-verificatie, &amp; Office in een browser  <br/> | DNS-, CRL-en &amp; CDN-aanvragen  <br/>  Alle andere Office 365-services die niet specifiek worden ondersteund via Azure ExpressRoute  <br/>  Alle andere Microsoft-cloudservices  <br/> |

## <a name="key-planning-considerations-to-using-bgp-communities"></a>Belangrijke overwegingen bij het gebruik van BGP-community's

Klanten die het gebruik kunnen maken van BGP-community's om te bepalen hoe ExpressRoute wordt aangekondigd en doorgegeven in het klant netwerk, moeten rekening houden met de volgende aandachtspunten:
  
- Wanneer u BGP-community's in uw netwerkontwerp gebruikt, is het belangrijk om te zorgen dat route symmetrie nog steeds wordt bijgehouden. In sommige gevallen kan het toevoegen of verwijderen van BGP-community's een situatie creëren waarin symmetrische routering wordt verbroken en de routeringsconfiguratie moet worden bijgewerkt, zodat de symmetrische routering opnieuw kan worden ingesteld.

- Het bereik van Azure ExpressRoute met BGP-Community-waarden is een klant actie. Microsoft adverteert alle IP-voorvoegsels die zijn gekoppeld aan de peering-relatie, ongeacht de scopes die door de klant zijn geconfigureerd.

- Azure ExpressRoute biedt geen ondersteuning voor acties op het Microsoft-netwerk op basis van BGP-community's van de klant.

- De IP-voorvoegsels die door Office 365 worden gebruikt, worden alleen gemarkeerd met specifieke BGP-Community-waarden, locatie specifieke BGP-community's worden niet ondersteund. Services van Office 365 zijn globaal van aard, het filteren van voorvoegsels op basis van de locatie van de Tenant of gegevens in de Office 365-Cloud wordt niet ondersteund. U kunt het beste uw netwerk configureren voor de coördinatie van het kortste of het meest geschikte netwerkpad van de netwerklocatie van de gebruiker in het Microsoft Global-netwerk, ongeacht de fysieke locatie van het IP-adres van de Office 365-service waarop ze worden gevraagd.

- De IP-voorvoegsels die in de waarde van de BGP-Community zijn opgenomen, vertegenwoordigen een subnet met IP-adressen voor de Office 365-toepassing die is gekoppeld aan de waarde. In sommige gevallen zijn er in sommige gevallen meer dan één Office 365-toepassing IP-adressen binnen een subnet, wat resulteert in een IP-voorvoegsel in meer dan één communitywaarde. Dit wordt verwacht, hoewel dit niet het geval is en het niet van invloed is op de doelstellingen voor het aantal of de bandbreedtebeheer. Klanten wordt geadviseerd gebruik te maken van de aanpak van ' wat is er nodig ', in plaats van ' niet nodig ' om te zorgen dat u niet meer nodig hebt als u gebruikmaakt van BGP-community's voor Office 365 om het effect te minimaliseren.

- Met behulp van BGP-community's worden niet alle onderliggende vereisten voor Netwerkverbindingen gewijzigd of is er geen configuratie vereist voor het gebruik van Office 365. Klanten die toegang willen hebben tot Office 365, hebben nog steeds toegang tot internet nodig.

- Het bereik van Azure ExpressRoute met behulp van BGP-community's is alleen van invloed op de routes die uw interne netwerk kunnen zien over de Microsoft peering-relatie. Mogelijk moet u extra configuraties voor toepassingsniveaus maken, zoals het gebruik van een PAC-of WPAD-configuratie in combinatie met het routeren van een bereik.

- Naast het gebruik van de door Microsoft toegewezen BGP-community's, kunnen klanten ervoor kiezen hun eigen BGP-community's toe te wijzen aan Office 365 IP-voorvoegsels die zijn geleerd via Azure ExpressRoute om interne routering te beïnvloeden. Met een populaire use-case wordt een locatie op basis van een BGP-Community toegewezen aan alle routes die zijn geleerd via elke opgegeven ExpressRoute-peer locatie en vervolgens deze informatie nagaan in het netwerk van de klant, zodat u het kortste of het meest geschikte netwerkpad in het Microsoft-netwerk kunt coördineren. Het gebruik van door de klant toegewezen BGP-community's met ExpressRoute voor Office 365-scenario's valt buiten het bereik van het Microsoft-besturingselement of de zichtbaarheid.

Met deze korte koppeling kunt u teruggaan [https://aka.ms/bgpexpressroute365](https://aka.ms/bgpexpressroute365) :
  
## <a name="related-topics"></a>Verwante onderwerpen

[Een beoordeling van de netwerkverbinding van Office 365](assessing-network-connectivity.md)
  
[Azure ExpressRoute voor Office 365](azure-expressroute.md)
  
[ExpressRoute voor Office 365-connectiviteit beheren](managing-expressroute-for-connectivity.md)
  
[Routeren met ExpressRoute voor Office 365](routing-with-expressroute.md)
  
[Netwerk planning met ExpressRoute voor Office 365](network-planning-with-expressroute.md)
  
[Media kwaliteit en prestaties van de netwerkverbinding in Skype voor bedrijven online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[ExpressRoute en QoS in Skype voor bedrijven online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Oproep stroom met behulp van ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[ExpressRoute voor Office 365 implementeren](implementing-expressroute.md)
  
[Ondersteuning voor BGP-community's](https://azure.microsoft.com/documentation/articles/expressroute-routing/)
  
[Prestaties afstemmen van Office 365 met basislijnen en prestatie geschiedenis](performance-tuning-using-baselines-and-history.md)
  
[Prestatieproblemen met het plannen van Office 365](performance-troubleshooting-plan.md)
  
[Azure ExpressRoute voor Office 365-training](https://channel9.msdn.com/series/aer)
