---
title: ExpressRoute voor Office 365-connectiviteit beheren
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 7/13/2017
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: e4468915-15e1-4530-9361-cd18ce82e231
description: Meer informatie over het beheren van ExpressRoute voor Office 365, inclusief veelgebruikte gebieden om te configureren, zoals voorvoegselfilters, beveiliging en naleving.
ms.openlocfilehash: e8de0763df7d592bc41802b1ead48df06891e6dc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916666"
---
# <a name="managing-expressroute-for-office-365-connectivity"></a>ExpressRoute voor Office 365-connectiviteit beheren

ExpressRoute voor Office 365 biedt een alternatief routeringspad om veel Office 365-services te bereiken zonder dat al het verkeer naar internet hoeft te gaan. Hoewel de internetverbinding met Office 365 nog steeds nodig is, geven de specifieke routes die Microsoft via BGP aan uw netwerk aanmaakt, de voorkeur aan het directe ExpressRoute-circuit, tenzij er andere configuraties in uw netwerk zijn. De drie veelgebruikte gebieden die u wilt configureren voor het beheren van deze routering, zijn het filteren van voorvoegsels, beveiliging en naleving.
  
> [!NOTE]
> Microsoft heeft de manier gewijzigd waarop het routeringsdomein van Microsoft Peering wordt beoordeeld voor Azure ExpressRoute. Vanaf 31 juli 2017 kunnen alle Azure ExpressRoute-klanten Microsoft Peering rechtstreeks vanuit de Azure Administrative-console of via PowerShell inschakelen. Na het inschakelen van Microsoft Peering kan elke klant routefilters maken om BGP-routeadvertenties te ontvangen voor Dynamics 365 Customer Engagement-toepassingen (voorheen CRM Online genoemd). Klanten die Azure ExpressRoute voor Office 365 nodig hebben, moeten worden beoordeeld door Microsoft voordat ze routefilters voor Office 365 kunnen maken. Neem contact op met uw Microsoft-accountteam voor meer informatie over het aanvragen van een controle voor het inschakelen van Office 365 ExpressRoute. Ongeautoriseerde abonnementen die routefilters voor Office 365 proberen te maken, ontvangen een [foutbericht](https://support.microsoft.com/kb/3181709)
  
## <a name="prefix-filtering"></a>Voorvoegselfilters

Microsoft raadt klanten aan alle BGP-routes te accepteren zoals aangekondigd vanuit Microsoft, de routes die worden verstrekt, worden grondig gecontroleerd en gevalideerd, waardoor eventuele voordelen voor extra controle worden verwijderd. ExpressRoute biedt inheems de aanbevolen besturingselementen, zoals IP-voorvoegseleigenschap, integriteit en schaal, zonder binnenkomende routefilters aan de klantzijde.
  
Als u extra validatie van het eigendom van de route via openbare ExpressRoute-peering nodig hebt, kunt u de aangekondigde routes controleren in de lijst met alle IPv4- en IPv6-IP-voorvoegsels die de openbare IP-reeksen van [Microsoft vertegenwoordigen.](https://www.microsoft.com/download/details.aspx?id=53602) Deze bereiken hebben betrekking op de volledige Microsoft-adresruimte en wijzigen zelden, waardoor een betrouwbare reeks bereiken wordt verstrekt om tegen te filteren, wat ook extra bescherming biedt voor klanten die zich zorgen maken over routes van buiten Microsoft die in hun omgeving lekken. Als er een wijziging wordt aangebracht, wordt deze aangebracht op de 1e van de maand en wordt het versienummer in de **detailssectie** van de pagina gewijzigd telkens wanneer het bestand wordt bijgewerkt.
  
Er zijn een aantal redenen om te voorkomen dat de URL's en IP-adresbereiken van [Office 365](./urls-and-ip-address-ranges.md) worden gebruikt voor het genereren van filterlijsten voor voorvoegsels. Met inbegrip van het volgende:
  
- De IP-voorvoegsels van Office 365 worden regelmatig gewijzigd.

- De URL's en IP-adresbereiken van Office 365 zijn ontworpen voor het beheren van lijsten met firewalls en proxy-infrastructuur, niet voor routering.

- De URL's en IP-adresbereiken van Office 365 hebben geen betrekking op andere Microsoft-services die mogelijk binnen het bereik van uw ExpressRoute-verbindingen vallen.

|**Optie**|**Complexiteit**|**Besturingselement wijzigen**|
|:-----|:-----|:-----|
|Alle Microsoft-routes accepteren  <br/> |**Laag:** Klant vertrouwt op Microsoft-besturingselementen om ervoor te zorgen dat alle routes correct eigendom zijn.  <br/> |Geen  <br/> |
|Supernets van Microsoft filteren  <br/> |**Medium:** Klant implementeert samengevatte filterlijsten voor voorvoegsels om alleen routes in eigendom van Microsoft toe te staan.  <br/> |Klanten moeten ervoor zorgen dat de niet-regelmatig bijgewerkte updates worden weergegeven in routefilters.  <br/> |
|IP-bereik van Office 365 filteren  <br/> [!CAUTION] Not-Recommended |**Hoog:** Klant filtert routes op basis van gedefinieerde IP-voorvoegsels van Office 365.  <br/> |Klanten moeten een krachtig wijzigingsbeheerproces implementeren voor de maandelijkse updates.  <br/> [!CAUTION] Voor deze oplossing zijn aanzienlijke wijzigingen nodig. Wijzigingen die niet op tijd zijn geïmplementeerd, leiden waarschijnlijk tot een servicestoring.   |

Verbinding maken met Office 365 met Azure ExpressRoute is gebaseerd op BGP-advertenties van specifieke IP-subnetten die netwerken vertegenwoordigen waarin Office 365-eindpunten worden geïmplementeerd. Vanwege het globale karakter van Office 365 en het aantal services dat deel uit maakt van Office 365, hebben klanten vaak behoefte aan het beheren van de advertenties die ze accepteren in hun netwerk. Als u zich zorgen maakt over het aantal voorvoegsels dat in uw omgeving wordt aangekondigd, kunt u met de [BGP-communityfunctie](https://support.office.com/article/Using-BGP-communities-in-ExpressRoute-for-Office-365-scenarios-preview-9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099) de advertenties filteren op een specifieke set Office 365-services. Deze functie is nu beschikbaar in de preview-versie.
  
Ongeacht hoe u de BGP-routeadvertenties van Microsoft beheert, krijgt u geen speciale blootstelling aan Office 365-services in vergelijking met alleen verbinding maken met Office 365 via een internetcircuit. Microsoft behoudt dezelfde beveiligings-, compliance- en prestatieniveaus, ongeacht het type circuit dat een klant gebruikt om verbinding te maken met Office 365.
  
### <a name="security"></a>Beveiliging

Microsoft raadt u aan uw eigen besturingselementen voor netwerk- en beveiligingsperimeters te onderhouden voor verbindingen van en naar openbare ExpressRoute- en Microsoft-peering, waaronder verbindingen van en naar Office 365-services. Beveiligingsbesturingselementen moeten worden uitgevoerd voor netwerkaanvragen die uitgaand van uw netwerk naar het netwerk van Microsoft gaan, en voor inkomende netwerken van Microsoft naar uw netwerk.
  
#### <a name="outbound-from-customer-to-microsoft"></a>Uitgaande van klant naar Microsoft
  
Wanneer computers verbinding maken met Office 365, maken ze verbinding met dezelfde set eindpunten, ongeacht of de verbinding wordt gemaakt via een internet- of ExpressRoute-circuit. Ongeacht het circuit dat wordt gebruikt, wordt u aangeraden Office 365-services te behandelen als vertrouwder dan algemene internetbestemmingen. Uw uitgaande beveiligingsbesturingselementen moeten zich richten op de poorten en protocollen om de blootstelling te beperken en doorlopend onderhoud te minimaliseren. De vereiste poortgegevens zijn beschikbaar in het artikel naslaginformatie over [Office 365-eindpunten.](./urls-and-ip-address-ranges.md)
  
Voor extra besturingselementen kunt u FQDN-niveaufilters binnen uw proxyinfrastructuur gebruiken om bepaalde of alle netwerkaanvragen die bestemd zijn voor internet of Office 365 te beperken of te controleren. Om de lijst met FQDN's te behouden terwijl functies worden uitgebracht en de Office 365-aanbiedingen zich ontwikkelen, is een krachtiger wijzigingsbeheer en het bijhouden van wijzigingen in de gepubliceerde [Office 365-eindpunten](./urls-and-ip-address-ranges.md)vereist.
  
> [!CAUTION]
> Microsoft raadt u aan niet alleen te vertrouwen op IP-voorvoegsels om uitgaande beveiliging naar Office 365 te beheren.

|**Optie**|**Complexiteit**|**Besturingselement wijzigen**|
|:-----|:-----|:-----|
|Geen beperkingen  <br/> |**Laag:** Klant biedt onbeperkte uitgaande toegang tot Microsoft.  <br/> |Geen  <br/> |
|Poortbeperkingen  <br/> |**Laag:** Klant beperkt uitgaande toegang tot Microsoft door de verwachte poorten.  <br/> |Zelden.  <br/> |
|FQDN-beperkingen  <br/> |**Hoog:** Klant beperkt uitgaande toegang tot Office 365 op basis van de gepubliceerde FQDN's.  <br/> |Maandelijkse wijzigingen.  <br/> |

#### <a name="inbound-from-microsoft-to-customer"></a>Binnenkomende van Microsoft naar klant
  
Er zijn verschillende optionele scenario's waarvoor Microsoft verbindingen met uw netwerk moet starten.
  
- ADFS tijdens wachtwoordvalidatie voor aanmelding.

- [Hybride implementaties van Exchange Server](/exchange/exchange-hybrid).

- E-mail van een Exchange Online-tenant naar een on-premises host.

- SharePoint Online Mail wordt verzonden vanuit SharePoint Online naar een on-premises host.

- [Hybride zoeken in SharePoint federatief](/SharePoint/hybrid/display-hybrid-federated-search-results-in-sharepoint-online).

- [Hybride BCS van SharePoint.](/SharePoint/hybrid/deploy-a-business-connectivity-services-hybrid-solution)

- [Skype voor Bedrijven hybride](/skypeforbusiness/hybrid/plan-hybrid-connectivity?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) en/of [Skype voor Bedrijven-federatie](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features).

- [Skype voor Bedrijven Cloud Connector](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition).

Microsoft raadt u aan deze verbindingen via uw internetcircuit te accepteren in plaats van uw ExpressRoute-circuit om de complexiteit te verminderen. Als uw nalevings- of prestatiebehoeften bepalen dat deze binnenkomende verbindingen moeten worden geaccepteerd via een ExpressRoute-circuit, wordt het raadzaam een firewall of reverse proxy te gebruiken om de geaccepteerde verbindingen te kunnen gebruiken. U kunt de [Office 365-eindpunten](./urls-and-ip-address-ranges.md) gebruiken om de juiste FQDN's en IP-voorvoegsels te achterhalen.
  
### <a name="compliance"></a>Compliance

We zijn niet afhankelijk van het routeringspad dat u gebruikt voor een van onze compliancebesturingselementen. Ongeacht of u verbinding maakt met Office 365-services via een ExpressRoute- of internetcircuit, onze compliancebesturingselementen worden niet gewijzigd. Bekijk de verschillende nalevings- en beveiligingscertificeringsniveaus voor Office 365 om erachter te komen wat de beste keuze is voor het voldoen aan de behoeften van uw organisatie.
  
Met deze korte koppeling kunt u teruggaan: [https://aka.ms/manageexpressroute365]()
  
## <a name="related-topics"></a>Verwante onderwerpen

[Netwerken voor contentlevering](content-delivery-networks.md)
  
[URL's en IP-adresbereiken voor Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Office 365-eindpunten beheren](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Azure ExpressRoute voor Office 365-training](https://channel9.msdn.com/series/aer)