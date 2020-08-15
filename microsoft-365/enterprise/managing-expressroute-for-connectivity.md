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
description: Meer informatie over het beheren van ExpressRoute voor Office 365, waaronder gemeenschappelijke gebieden die u wilt configureren, zoals het filteren van een voorvoegsels, beveiliging en naleving.
ms.openlocfilehash: 5b55150b91b68954cb7b701afb7cf46ab9b951dd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689551"
---
# <a name="managing-expressroute-for-office-365-connectivity"></a>ExpressRoute voor Office 365-connectiviteit beheren

ExpressRoute voor Office 365 biedt een alternatief routerings traject voor het bereiken van veel Office 365-Services, zonder dat dit alle verkeer hoeft te passeren voor het internet. Hoewel de internetverbinding met Office 365 nog steeds nodig is, zijn de specifieke routes die door Microsoft worden aangekondigd via BGP, de voorkeur van het directe ExpressRoute-circuit, tenzij er andere configuraties in uw netwerk zijn. De drie gangbare gebieden die u kunt configureren voor het beheren van deze routering, zijn voor het filteren van voorvoegsels, beveiliging en naleving.
  
> [!NOTE]
> Microsoft heeft gewijzigd hoe het Microsoft peering-routeringsdomein wordt gecontroleerd op Azure ExpressRoute. Vanaf 31 juli 2017 kunnen alle Azure ExpressRoute-klanten Microsoft peering rechtstreeks via de Azure Administrative console of via PowerShell inschakelen. Na het inschakelen van Microsoft peering kan elke klant routefilters maken voor het ontvangen van BGP-routeadvertenties voor Dynamics 365-toepassingen voor klant afspraken (voorheen bekend als CRM Online). Klanten die Azure ExpressRoute voor Office 365 moeten een beoordeling van Microsoft krijgen voordat ze routefilters voor Office 365 kunnen maken. Neem contact op met uw Microsoft-account team voor informatie over hoe u een beoordeling moet aanvragen voor het inschakelen van Office 365 ExpressRoute. Ongeautoriseerde abonnementen die bij het maken van routefilters voor Office 365, wordt een [foutbericht](https://support.microsoft.com/kb/3181709) weergegeven
  
## <a name="prefix-filtering"></a>Filteren op voorvoegsels

Microsoft adviseert dat klanten alle BGP-routes accepteren als aangekondigd bij Microsoft, en de door u geboden voordelen voor de toevoeging van de voordelen voor de toevoeging. ExpressRoute heeft systeemeigen de aanbevolen besturingselementen, zoals eigendom van IP-voorvoegsels, integriteit en schaal, zonder inkomende routefilters aan de klant kant.
  
Als u meer validering van route beheer nodig hebt voor de openbare peering van ExpressRoute, kunt u de aangekondigde routes controleren op de lijst met alle IPv4-en IPv6-voorvoegsels die het [openbare IP-bereiken van Microsoft](https://www.microsoft.com/download/details.aspx?id=53602)vertegenwoordigen. In deze bereiken wordt de volledige adresruimte van Microsoft besproken en wordt u vaak overgezet, met een betrouwbare reeks bereiken waarmee u kunt filteren, ook voor een extra bescherming voor klanten die zich zorgen maken over niet-Microsoft-routers die zich in hun omgeving belekken. In het geval dat er een wijziging is, wordt deze weergegeven op de 1e van de maand en wordt het versienummer in het gedeelte **Details** van de pagina gewijzigd telkens wanneer het bestand wordt bijgewerkt.
  
Er zijn verschillende redenen om te voorkomen dat de [url's en IP-adresbereiken van Office 365](https://aka.ms/o365endpoints) worden gebruikt voor het genereren van voorvoegsel filterlijsten. Waaronder de volgende:
  
- De IP-voorvoegsels van Office 365 worden op een regelmatig veel gewijzigd.

- De Url's en IP-adresbereiken voor Office 365 zijn ontworpen voor het beheer van lijsten met toegestane firewalls en proxy-infrastructuur, niet routeren.

- De Url's en IP-adresbereiken voor Office 365 staan niet voor andere Microsoft-services die mogelijk binnen het bereik vallen voor uw ExpressRoute-verbindingen.

|**Optie**|**Gecompliceerd**|**Besturingselement wijzigen**|
|:-----|:-----|:-----|
|Alle Microsoft-routes accepteren  <br/> |**Laag:** Klant is afhankelijk van de besturingselementen van Microsoft om ervoor te zorgen dat alle routes correct zijn.  <br/> |Geen  <br/> |
|Microsoft bezite supernetten filteren  <br/> |**Normaal:** De klant implementeert samengevatte voorvoegsel filterlijsten om alleen routes toe te staan die eigendom zijn van Microsoft.  <br/> |Klanten moeten ervoor zorgen dat de onregelmatige updates worden doorgevoerd in de routefilters.  <br/> |
|Office 365 IP-bereiken filteren  <br/> [!CAUTION] Niet aanbevolen |**Hoog:** Klant filtert routes op basis van gedefinieerde IP-voorvoegsels van Office 365.  <br/> |Klanten moeten voor de maandelijkse updates een krachtig proces voor wijzigingsbeheer implementeren.  <br/> [!CAUTION] Voor deze oplossing zijn belangrijke wijzigingen nodig. Wijzigingen die niet in de tijd zijn geïmplementeerd, leveren waarschijnlijk een service storing op.   |

Verbinding maken met Office 365 met behulp van Azure ExpressRoute is gebaseerd op BGP-advertisements van specifieke IP-subnetten die netwerken aangeven waarop Office 365-eindpunten zijn geïmplementeerd. Aangezien de wereldwijde aard van Office 365 en het aantal services van Office 365, hebben klanten vaak de reclame die ze in hun netwerk accepteren. Als u zich zorgen maakt over het aantal voorvoegsels dat wordt aangekondigd in uw omgeving, kunt u met de functie [BGP-Community](https://support.office.com/article/Using-BGP-communities-in-ExpressRoute-for-Office-365-scenarios-preview-9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099) de advertenties filteren op een specifieke set Office 365-Services. Deze functie is nu beschikbaar in de preview-versie.
  
Ongeacht de manier waarop u de BGP route-advertisements van Microsoft beheert, krijgt u geen speciale aandacht voor Office 365-Services wanneer ze worden vergeleken met het maken van verbinding met Office 365 via een Internet circuit. Microsoft onderhoudt dezelfde beveiligings-, compliance-en prestatieniveaus, ongeacht het type circuit dat een klant gebruikt om verbinding te maken met Office 365.
  
### <a name="security"></a>Beveiliging

Microsoft raadt u aan om uw eigen besturing voor netwerk-en beveiligings verbindingen voor verbindingen van ExpressRoute en voor Thuisgebruik en Microsoft peering te behouden, waaronder verbindingen met en van Office 365-Services zijn inbegrepen. U dient te beschikken over de juiste beveiligingsinstellingen voor netwerkaanvragen van uw netwerk naar het Microsoft-netwerk en van de inkomende berichten van het Microsoft-netwerk tot uw netwerk.
  
#### <a name="outbound-from-customer-to-microsoft"></a>Uitgaand van klant naar Microsoft
  
Wanneer computers verbinding maken met Office 365, maken ze verbinding met dezelfde set eindpunten, ongeacht of de verbinding wordt gemaakt via een Internet-of ExpressRoute-circuit. U wordt aangeraden Office 365-services te behandelen als vertrouwd dan voor de generieke Internet bestemmingen, ongeacht het gebruikte circuit. De beschikbaarheid van uitgaande beveiligingsinstellingen dient te gelden voor de poorten en protocollen, zodat de blootstelling minder wordt versoepeld en voortdurend onderhouden. De vereiste poortgegevens zijn beschikbaar in het referentie artikel [Office 365-eindpunten](https://aka.ms/o365endpoints) .
  
Voor extra besturingselementen kunt u het filteren van FQDN-niveau binnen de proxy-infrastructuur gebruiken om bepaalde of alle netwerkaanvragen te beperken of te controleren die bestemd zijn voor het internet of Office 365. De lijst met FQDN-namen worden vrijgegeven wanneer functies worden vrijgegeven en de Office 365-aanbiedingen ontwikkelen vereist meer krachtig wijzigingsbeheer en het bijhouden van wijzigingen in de gepubliceerde [Office 365-eindpunten](https://aka.ms/o365endpoints).
  
> [!CAUTION]
> Microsoft raadt u aan niet alleen te vertrouwen op IP-voorvoegsels voor het beheren van uitgaande beveiliging voor Office 365.

|**Optie**|**Gecompliceerd**|**Besturingselement wijzigen**|
|:-----|:-----|:-----|
|Geen beperkingen  <br/> |**Laag:** Klant staat onbeperkte uitgaande toegang tot Microsoft toe.  <br/> |Geen  <br/> |
|Poort beperkingen  <br/> |**Laag:** Klant beperkt uitgaande toegang tot Microsoft door de verwachte poorten.  <br/> |Onregelmatig.  <br/> |
|FQDN-beperkingen  <br/> |**Hoog:** Klant beperkt uitgaande toegang tot Office 365 op basis van de gepubliceerde FQDN-namen.  <br/> |Maandelijkse wijzigingen.  <br/> |

#### <a name="inbound-from-microsoft-to-customer"></a>Inkomend van Microsoft naar klant
  
Er zijn verschillende optionele scenario's waarvoor Microsoft verbindingen met uw netwerk moet initiëren.
  
- ADFS tijdens wachtwoordvalidatie voor aanmelden.

- [Hybride implementaties van Exchange Server](https://technet.microsoft.com/library/jj200581%28v=exchg.150%29.aspx).

- E-mail van een Exchange Online-Tenant naar een on-premises host.

- E-mail van SharePoint Online verzonden van SharePoint Online naar een on-premises host.

- [Hybride zoeken in SharePoint](https://technet.microsoft.com/library/dn197174.aspx)

- [Hybride versie van SharePoint](https://technet.microsoft.com/library/dn197239.aspx ).

- [Skype voor bedrijven](https://technet.microsoft.com/library/jj205403.aspx) -Federatie voor hybride en/of [Skype voor bedrijven](https://technet.microsoft.com/library/skype-for-business-online-federation-and-public-im-conectivity.aspx).

- [Skype voor bedrijven cloud connector](https://technet.microsoft.com/library/mt605227.aspx ).

Microsoft raadt u aan deze verbindingen te accepteren via uw Internet circuit in plaats van uw ExpressRoute-circuit om de complexiteit te reduceren. Als uw compliance of prestatiebehoeften deze inkomende verbindingen moeten accepteren via een ExpressRoute-circuit, moet u een firewall of reverse-proxy gebruiken om het bereik van de geaccepteerde verbindingen aan te bevelen. U kunt de [Office 365-eindpunten](https://aka.ms/o365endpoints) gebruiken om de juiste FQDN-en IP-voorvoegsels te achterhalen.
  
### <a name="compliance"></a>Compliance

We vertrouwen niet op het routeringspad dat u gebruikt voor een van onze nalevings functies. Ongeacht of u verbinding maakt met Office 365-Services via een ExpressRoute of Internet circuit, geen wijzigingen aanbrengen in de nalevings functies. U moet de diverse beveiligingsniveaus voor naleving en beveiliging van Office 365 nakijken om de beste keuze te bepalen voor de behoeften van uw organisatie.
  
Met deze korte koppeling kunt u teruggaan: [https://aka.ms/manageexpressroute365](https://aka.ms/manageexpressroute365)
  
## <a name="related-topics"></a>Verwante onderwerpen

[Netwerken voor content levering](content-delivery-networks.md)
  
[URL's en IP-adresbereiken voor Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Office 365-eindpunten beheren](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Azure ExpressRoute voor Office 365-training](https://channel9.msdn.com/series/aer)
