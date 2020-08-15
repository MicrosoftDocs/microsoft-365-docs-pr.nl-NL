---
title: Overweging van SharePoint 2007-migratie opties
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- SPS150
- OSU140
- SPO160
- SPB160
- OSI150
- OSI160
- BSA160
- OSU160
ms.assetid: 66325a43-5816-4f8e-81ba-c11b71345b7c
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: Dit artikel bevat informatie voor gebruikers die gebruikmaken van SharePoint Server 2007, zodat ze hun upgrade kunnen voorbereiden.
ms.openlocfilehash: 3e37a01f1a2d387cda6723a8df1f73734fa3ba9d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694952"
---
# <a name="sharepoint-2007-migration-options-to-consider"></a>Overweging van SharePoint 2007-migratie opties

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Microsoft SharePoint 2007 en SharePoint Server 2007 hebben de ondersteuning beëindigd. Het is tijd om een upgrade uit te voeren. Dit artikel bevat informatie over de migratie opties.
  
## <a name="common-upgrade-strategies-for-sharepoint"></a>Algemene upgrade strategieën voor SharePoint

Er zijn verschillende manieren om een SharePoint Server-omgeving te upgraden. Als u een Microsoft Office SharePoint Server 2007-farm hebt, vindt u hier enkele voorbeelden van de upgrademethoden:
  
- Database bijvoegen
    
- Upgrade naast elkaar
    
- In-place upgrade
    
- Hybride upgrade (in-place met losgekoppelde databases/afzonderlijke databasekoppeling)
    
- Hybride SharePoint-omgeving (online verbinding maken met on-premises SharePoint)
    
- Gegevens handmatig verplaatsen tussen siteverzamelingen of bibliotheken
    
- Wizard FastTrack upgrade naar Microsoft 365 ([SharePoint Online Deployment adviseur](https://aka.ms/spoguidance))
    
- Migratie-API naar SharePoint Online (SPO) in Microsoft 365
    
Wat werkt het beste voor u?
  
Uw kennis van wat uw farm doet en wordt gebruikt voor een tactische sterkte wanneer een upgrade komt. Op de manier waarop mensen de SharePoint-farm gebruiken, kunt u kiezen uit uw opties.
  
> [!TIP]
> Microsoft Office SharePoint Server 2007 heeft ook een geleidelijke upgrade die hier niet wordt besproken. Zie de [SharePoint Server 2007 end-ondersteunings routekaart](sharepoint-2007-end-of-support.md)voor een lijst met stappen die specifiek voor de update werken. 
  
Let erop dat u de [product levenscyclus](https://support.microsoft.com/lifecycle/search) en systeemvereisten controleert voor de versie van SharePoint waarnaar u een upgrade uitvoert. Dit houdt in dat u weet wanneer de volgende upgrade nodig is (bijvoorbeeld als u een ouder product, zoals SharePoint Server 2010, onderbreekt voor meer upgrades, moet u weten dat het einde van de ondersteunings datum) is en zeker weten dat u hardware hebt die uw abonnement ondersteunt. 
  
Als u een deel van de SharePoint-sites wilt overzetten naar Microsoft 365 in de Cloud, kunt u het volgende doen om een koppeling naar de [servicebeschrijvingen voor Microsoft 365 en Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)te maken. U hebt de service beschrijvingen nodig voor informatie over de SharePoint Online-functies en de manier waarop ze kunnen afwijken van de on-premises SharePoint-Server. Upgrade functionele Microsoft Office SharePoint Server 2007 farms. Als de installatiesites bevat die zijn verbroken, moet u deze oplossen voordat u een upgrade uitvoert.
  
## <a name="a-note-about-managing-risk"></a>Een opmerking over het beheren van risico

Methoden als ' naast elkaar ' zijn belangrijk in het schema van upgrade logica. Wanneer u naast elkaar een upgrade uitvoert, onderneemt u uw Microsoft Office SharePoint Server 2007-Farm, maar u kunt de volgende versie van de Microsoft Office SharePoint Server (SharePoint Server 2010) van de nieuwe hardware maken. Dit helpt u op drie manieren:
  
1. U hebt een plaats voor het maken van back-ups van uw Microsoft Office SharePoint Server 2007-databases, zodat u deze afzonderlijk kunt upgraden met behulp van database bijvoegen.
    
2. Als u er zeker van bent dat slechts een klein aantal essentiële documentbibliotheken en andere gegevens in gebruik zijn in uw Microsoft Office SharePoint Server 2007-Farm, kunt u ervoor kiezen om gegevens handmatig te verplaatsen van Microsoft Office SharePoint Server 2007 naar SharePoint Server 2010 of alleen specifieke sites en webs te maken voor de volgende versie (waarmee u uw taken eenvoudiger kunt maken).
    
3. Hoe minder u doet met de serverfarm Microsoft Office SharePoint Server 2007, het veiliger maken van de gegevens in de farm omdat u de upgrade uitvoert.
    
Methoden zoals in-place upgrade handelen rechtstreeks op uw Microsoft Office SharePoint Server 2007-Farm, zodat u minder eenvoudige opties hebt om een pad te verlaten en opnieuw te beginnen met uw pristine-omgeving. U kunt zo veel mogelijk beveiligingsmaatregelen maken (zoals het maken en testen van back-ups van de oorspronkelijke omgeving). Als uw Microsoft Office SharePoint Server 2007-farm bijvoorbeeld virtueel is en wordt gedupliceerd voor het maken van back-up-en herstelfuncties, moet u de meest recente databases vóór het servicevenster voor de upgrade maken en terugzetten. Als u een back-up van databaseback-ups maakt, is het niet alleen een failsafe, maar u kunt u een gemoedsrust bieden.
  
> [!TIP]
> Documenten met best practices voor een upgrade bestaan voor [Microsoft Office SharePoint server 2007](https://technet.microsoft.com/library/cc261992%28v=office.12%29.aspx), [sharepoint Server 2010](https://technet.microsoft.com/library/cc261992%28v=office.14%29.aspx), [SharePoint Server 2013](https://technet.microsoft.com/library/cc261992%28v=office.15%29.aspx)en [SharePoint Server 2016](https://technet.microsoft.com/library/cc261992%28v=office.16%29.aspx). U kunt ook zoeken naar [Microsoft-partners](https://partnercenter.microsoft.com/pcv/search) die ervaring hebben met upgrades of microsoft 365-migraties. 
  
## <a name="make-your-plan"></a>Maak uw plan

Als u een upgrade wilt uitvoeren, hebt u een plan nodig, en één formaat past niet allemaal in deze gevallen. Uw abonnement is mogelijk zo simpel als ' een Microsoft 365-abonnement maken met SharePoint Online, een domein registreren en mensen omleiden om het bestand op te slaan. En dat is mogelijk niet het geval. Dat is alles wat u en uw gebruikers echt nodig hebben.
  
> [!NOTE]
> Het is riskant voor het uitvoeren van software waarvan de levensduur is geëindigd. Producten die niet worden ondersteund, worden niet meer bijgewerkt wanneer er problemen zijn gevonden. Dit betekent ook dat als er nieuwe beveiligingsrisico's optreden, geen beveiligingspatches of oplossingen bestaan omdat de producten voor het einde van de levenscyclus niet meer worden ondersteund. U kunt deze situatie vermijden. 
  
### <a name="first-know-your-farm"></a>Ken eerst uw farm

Wanneer u een upgrade uitvoert, moet u eerst een beslissing stellen op basis van wat uw farm voor uw organisatie doet. Wat heb ik nodig? Wat is de rol? Elke farm in uw bedrijf heeft mogelijk een andere rol. Het is mogelijk dat sommige van uw SharePoint-farms van  *essentieel belang*  zijn, wat ook voor veilig bewaren. Als in uw farm veel rollen tegelijk worden ingevuld, moet u mogelijk op de hoogte zijn van de siteverzamelingen, webs of zelfs documentbibliotheken, aanpassingen en de manier waarop ze zich bevinden. Het analyseren van uw gegevens op dit niveau lijkt veel op veel werk, maar u bespaart tijd en inspanning voor de kapitein van uw domein voordat u een upgrade uitvoert of de migratie uitvoert. Wanneer u alle bewegende gedeelten en de belangrijkste gedeelten weet, kunt u ook weten wat u uitvalt en wat u achter kunt laten. Dat is alles wat u verder gaat. 
  
En wat zeggen gebruikers die het belangrijkst zijn in uw SharePoint server-farm?
  
- Ingebouwde SharePoint-functies
    
- De grote data hoeveelheid (zoals een archief met bestanden)
    
- Beschikbaarheid
    
- Essentiële apps, webonderdelen of documenten in de farm (Mission Critical Farm)
    
- De nalevings normen voldoen
    
- Aanpassingen
    
Als u een belangrijk abonnement voor uw bedrijf voert vanuit uw SharePoint-farm, moet u dit zeggen als een grote catalogus met essentiële gegevens over client servicevereisten, kunt u een tik naast ' kritieke apps ' plaatsen, maar ook ' beschikbaarheid ', dat wil zeggen dat uw bedrijf niet langer gebruik kan maken van SharePoint. Het kan ook zijn dat u ' aanpassingen ' moet controleren omdat de kritieke services die uw farm biedt op basis van aangepaste code, sitedefinities of een aantal aanpassingen samenwerken.
  
Als u in SharePoint voldoet aan deze behoeften zonder dat u iets hoeft te doen, en u dit doorgaans bijwerkt en het normaal beheer en onderhoud uitvoert, hebt u mogelijk ook de optie ' ingebouwde versie van SharePoint ', en kunt u ook de oorzaak van een oudere versie van SharePoint maken. Met andere woorden: het is al wat u nodig hebt en u hebt nog geen upgrade nodig voor de upgrade van Microsoft Office SharePoint Server 2007.
  
Wanneer u een opsommingsteken maakt, kunt u criteria maken voor de upgrade. Met andere woorden: bij elke upgrade moet de balk aan de balk voldoen om te worden overwogen. U kunt ook methoden toepassen die u niet aan uw wensen voldoet.
  
### <a name="a-simple-sample-plan"></a>Een eenvoudig voorbeeld van een plan

U moet mogelijk een bredere consensus doen met leiderschap en andere beheerders op het pad dat de SharePoint-upgrade duurt. SharePoint Server-beheerders kunnen vaak samenwerken met Microsoft SQL Server-beheerders, werken met netwerken en beveiligings teams, en nog veel meer. Wanneer er sprake is van een groot aantal belanghebbenden, moet u mogelijk een upgrade-en migratie abonnement maken of aanpassen. Als u bijvoorbeeld gegevens migreert zodat dit deel van uw bedrijf gebruikmaakt van SharePoint Online in Microsoft 365, moet u waarschijnlijk prestatie afstemmen of testen binnen uw netwerk hebben. De betrokken teams moet op de hoogte worden gesteld.
  
In mijn eenvoudige voorbeeld ziet u het voorstel van een SharePoint-beheerder en vervolgens een lijst met alle belanghebbenden waarover u bent aangemeld. Document uw overeenkomsten en besluiten voor duidelijkheid.
  
Het abonnement begint na een uitgebreide analyse van een farm en probeert de rol van de farm, pijn punten en andere belangrijke informatie te identificeren, zodat er een aantal upgradeopties kan worden beperkt. Later wordt een upgrade voorstel van de SharePoint-beheerder gemaakt, en de belanghebbenden accepteren een actieplan.
  
De lijst met opsommingstekens van mijn belangrijkste:
  
- Beschikbaarheid, ingebouwde functies van SharePoint en normen voor naleving.
    
- De meeste gegevens bevinden zich in drie siteverzamelingen, waarbij één vergaderwerkruimte voor een team van ontwikkelaars erg belangrijk is en intensief wordt gebruikt in verschillende tijdzones.
    
- Er zijn tien andere sites die veel worden gebruikt.
    
- Twee documentbibliotheken (vergaderwerkruimte en documenten in de hoofdsiteverzameling) zijn grootste (elk van 8000 documenten). We hebben een groot aantal gearchiveerde documenten en lijsten met werkblad bijlagen.
    
- Er zijn veertien lijsten met bibliotheken die gevoelige gegevens bevatten die moeten voldoen aan de naleving.
    
- U moet de mogelijkheid om te kunnen worden bewaard en e-ontdekking, overal ter wereld.
    
- Sommige van deze gegevens moeten on-premises, vanwege blijven vanwege-regels, bewaard blijven.
    
 **Mijn keuzen voor upgrade en migratie:**
  
| Ja | Nee |
|:-----|:-----|
|Databases bijwerken met een database bijvoegen  <br/> |In-place upgrade  <br/> |
|Naast elkaar upgraden met farms  <br/> |Hybride upgrade  <br/> |
|Migratie-API naar SPO in Microsoft 365 (voor gegevens van persoonlijke site)  <br/> |Hybride SharePoint-omgeving (nog niet nodig)  <br/> |
|Sommige handmatige migraties van gegevens naar SharePoint Online voor essentiële gegevens  <br/> |Upgrade van wizard FastTrack naar Microsoft 365  <br/> |
   
 **Mijn voorgestelde abonnement:**
  
Upgrade on-premises, met versies van SharePoint side-by-side, sommige virtueel gevirtualiseerde, zodat we de databases eerst kunnen upgraden. Ga van SharePoint 2007 naar SharePoint 2010. Beheerders en onwikkelaars test de nieuwe farm. Gebruikers testen de nieuwe farm. Verhelp eventuele problemen met weergeven. Opnieuw, naast elkaar, upgrade van SharePoint 2010-databases naar SharePoint 2013. Wedstrijden. Gebruikers Test/Pilot. Verhelp eventuele problemen met weergeven.
  
- Houd rekening met een federatief zoeken in federatieve Hybrid met SPO voldoet aan uw behoeften.
    
- U kunt ook [FastTrack-hulp](https://fasttrack.microsoft.com) doen als u van hieruit een upgrade naar SharePoint Online wilt uitvoeren. 
    
- Bepalen of een siteverzameling kan worden doorgeleid naar een Microsoft 365-abonnement. (Microsoft 365 voldoet aan een groot aantal [compliantie standaarden](https://technet.microsoft.com/library/office-365-compliance.aspx). Microsoft 365 heeft [eDiscovery](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) en kan worden [bewaard](https://support.office.com/article/A18F8975-AA7F-43B4-A7D6-001D14744D8E) via het nalevings centrum.) 
    
Ga anders verder met een side-by-side upgrade naar SharePoint Server 2016.
  
> [!NOTE]
> Tussen aanbevelingen van de beheerders die de upgrade plannen en de werkelijke processen zijn de gesprekken die plaatsvinden met andere belanghebbenden waarvoor de upgrade is voltooid. Als u bijvoorbeeld een andere beheerder bent, kunnen beheerders hun plannen ook wijzigen. Ongeacht de definitieve beslissing dient u te documenteren wat het overeengekomen abonnement verder gaat. Dit kan er ongeveer als volgt uitzien: 
  
 **Mijn actieplan:**
  
On-premises gebruiken we een virtuele omgeving om standaard-SharePoint-Server 2010 en 2013 samen te stellen. SharePoint Server 2016 wordt gebouwd op nieuwe hardware die voldoet aan de systeemvereisten voor 2016. Databases van SharePoint 2007 worden bijgewerkt tot en met alle versies ertussen en SharePoint Server 2016. Kern aanpassingen worden op dit moment opnieuw gemaakt en getest in de SharePoint Server 2016-omgeving, als de functies van de native functies niet al aan onze behoeften voldoen. Als we succes hebben, hebben we een on-premises Farm op nieuwe hardware met bijgewerkte databases en minder aanpassingen. We voegen de bijgewerkte inhoudsdatabases toe aan nieuwe siteverzamelingen in SharePoint Server 2013, test, User Test/Pilot en voer vervolgens een DNS-verplaatsings koppeling naar de nieuwe SharePoint Server 2016-omgeving voor Live gebruik.
  
- De federatieve hybride versie van SharePoint Server 2016 en SharePoint Online wordt momenteel niet aangeraden.
    
- Een geschat 35% van onze sites kan worden omgezet in nieuwe SPO-sites met werden omgezet-domeinen, of uiteindelijk OneDrive voor bedrijven-opslag worden. Op zoek naar andere verkoopkansen om sites te converteren of om nieuwe sites te routeren naar SPO.
    
- Een deel van dit deel van de migratie is handmatig, via slepen en neerzetten naar persoonlijke sites in OneDrive voor bedrijven, en een aantal door migratie-API.
    
Meer gedetailleerde stappen of een aantal koppelingen naar een specifieke upgraderoute moet de volgende stappen uitvoeren. De MOSS 2007-computer mag niet buiten gebruik worden gesteld, en virtuele omgevingen dienen voor de vergelijking van de vergelijking te worden gehandhaafd. de upgrade is echter voltooid wanneer gebruikers worden omgeleid naar SharePoint Server 2016.
  
Vaak zijn belangrijke factoren voor het kiezen van een methode de totale kosten van de upgrade en de kosten in tijd (u ziet meer informatie in dit artikel in het artikel in de SharePoint-migratieroute regel). Voor de planning van tevoren verbiedt u waarschijnlijk veel meer informatie over het instellen van verwachtingen, het kiezen van een goed overzicht en het weergeven van het succes.
  
## <a name="related-links"></a>Verwante koppelingen

[Bronnen om u te helpen bij het upgraden van Office 2007-servers en-clients](upgrade-from-office-2007-servers-and-products.md)
  
[Beleidsregels voor Microsoft Lifecycle Lifecycle and Lifecycle Search](https://support.microsoft.com/lifecycle)
  
[Zoeken naar Microsoft-partners die u kunnen helpen met een upgrade of migratie](https://partnercenter.microsoft.com/pcv/search)
  

