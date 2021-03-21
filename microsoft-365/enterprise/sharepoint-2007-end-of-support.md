---
title: Roadmap voor het einde van de levensduur van SharePoint Server 2007
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 01/28/2019
audience: ITPro
ms.topic: conceptual
f1.keywords:
- CSH
ms.custom:
- vsemail
- MS_WSS_DirectoryManagement
- MS_WSS_ConfigEmail
- globalemailconfig
- configssc
- AppDefToBDC
- seo-marvel-apr2020
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- OFU120
- SPS150
- OSU140
- WSU120
- OSR120
- SPO160
- PJW120
- SPB160
- OSI150
- OSI160
- BSA160
- OSU160
ms.assetid: ba124775-d5c0-4d68-b88d-8458ad4c3717
description: Ondersteuning voor SharePoint Server 2007 is beëindigd in oktober 2017. In dit artikel leert u meer over uw upgrade-, migratie- en ondersteuningsopties.
ms.openlocfilehash: 224b0af90d6a314aa15a2c0dab7b60626e5abde8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924866"
---
# <a name="sharepoint-server-2007-end-of-support-roadmap"></a>Roadmap voor het einde van de levensduur van SharePoint Server 2007

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Op **10 oktober 2017** heeft Microsoft Office SharePoint Server 2007 het einde van de ondersteuning bereikt. Als u nog niet bent gemigreerd van SharePoint Server 2007 naar Microsoft 365 of een nieuwere versie van SharePoint Server on-premises, is het nu tijd om te beginnen met plannen. In dit artikel vindt u informatiebronnen om gegevens te migreren naar SharePoint Online of om uw SharePoint Server on-premises te upgraden.
  
## <a name="what-does-end-of-support-mean"></a>Wat betekent *het einde van de ondersteuning?*

SharePoint Server heeft, net als de meeste Microsoft-producten, een levenscyclus voor ondersteuning, waarin Microsoft nieuwe functies, bugfixes, beveiligingsfixes, en meer biedt. Deze levenscyclus duurt meestal tien jaar vanaf de eerste release van het product. Het einde van deze levenscyclus wordt het einde van de ondersteuning van het product genoemd. Na het einde van de ondersteuning biedt Microsoft niet meer:
  
- Technische ondersteuning voor problemen die kunnen optreden.
    
- Oplossingen voor problemen die van invloed kunnen zijn op de stabiliteit en bruikbaarheid van de server.
    
- Beveiligingsfixes voor beveiligingsproblemen die de server kwetsbaar kunnen maken voor beveiligingsinbreuken.
    
- Tijdzone-updates.
    
Uw SharePoint Server 2007-farm is nog steeds operationeel na 10 oktober 2017, maar er worden geen verdere updates, patches of fixes uitgebracht voor het product, inclusief beveiligingspatches/fixes. Microsoft Support heeft de ondersteuningsinspanningen volledig verschoven naar recentere versies van het product. Omdat uw installatie niet meer wordt ondersteund of gepatcht, moet u het product upgraden of belangrijke gegevens migreren.
  
> [!TIP]
> Als u nog geen upgrade of migratie hebt gepland, zie: [SharePoint 2007-migratieopties](sharepoint-2007-migration-options.md) om te overwegen waar u moet beginnen. U kunt ook zoeken naar [Microsoft-partners](https://go.microsoft.com/fwlink/?linkid=841249) die u kunnen helpen bij een upgrade of Microsoft 365-migratie (of beide).
  
Zie Resources voor een upgrade van [Office 2007-servers en -clients](upgrade-from-office-2007-servers-and-products.md)voor meer informatie over Office 2007-servers en het einde van de ondersteuning.
  
## <a name="what-are-my-options"></a>Wat zijn mijn opties?

De eerste stop moet de [productlevenscyclussite zijn.](/lifecycle/products/?alpha=Microsoft+Office+SharePoint+Server+2007) Als u een on-premises Microsoft-product hebt dat ouder wordt, controleert u het einde van de ondersteuningsdatum, zodat u een jaar of zo hebt om een upgrade of migratie te plannen. Wanneer u de volgende stap kiest, bedenkt u welke productfuncties goed genoeg, beter en het beste zijn. Hier is een voorbeeld: 
  
|**Goed**|**Beter**|**Beste**|
|:-----|:-----|:-----|
|SharePoint Server 2010  <br/> |SharePoint Server 2013  <br/> |SharePoint Online  <br/> |
||Hybride SharePoint  <br/> |SharePoint Server 2016  <br/> |
| | |Hybride SharePoint  <br/> |
   
Als u een optie 'goed genoeg' kiest, moet u binnenkort beginnen met de planning voor een andere upgrade nadat de migratie van SharePoint Server 2007 is voltooid. 

>[!NOTE] 
>Einddatums van ondersteuning kunnen worden gewijzigd. Controleer de [productlevenscyclussite.](https://support.microsoft.com/lifecycle)
  
## <a name="where-can-i-go-next"></a>Waar kan ik nu heen?

SharePoint Server kan on-premises worden geïnstalleerd op uw eigen servers. U kunt ook SharePoint Online gebruiken, een onlineservice die deel uitmaakt van Microsoft 365. Uw opties zijn:
  
- Migreren naar SharePoint Online.
    
- Upgrade SharePoint Server on-premises.
    
- Doe beide van het bovenstaande.
    
- Een [hybride SharePoint-oplossing](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx) implementeren.
    
Houd rekening met verborgen kosten in verband met het onderhouden van een serverfarm, het onderhouden of migreren van aanpassingen en het upgraden van de hardware die SharePoint Server nodig heeft. Het is de moeite waard om een on-premises SharePoint Server-farm te hebben als dat nodig is. Maar als u uw farm runt op oudere SharePoint-servers zonder zware aanpassingen, kunt u profiteren van de migratie naar SharePoint Online.
  
> [!IMPORTANT]
> Er is een andere optie als de inhoud in SharePoint 2007 niet vaak wordt gebruikt. Sommige SharePoint-beheerders kiezen ervoor om een Microsoft 365-abonnement te maken, een nieuwe SharePoint Online-site in te stellen en vervolgens op een schone manier af te sluiten van SharePoint 2007, waarbij alleen essentiële documenten naar de nieuwe SharePoint Online-sites worden verwijderd. Gegevens kunnen vervolgens van de SharePoint 2007-site worden afgetapt naar archieven. Overweeg hoe uw gebruikers werken met gegevens uit uw SharePoint 2007-installatie. Er zijn mogelijk creatieve manieren om uw behoeften te beheren.
  
|**SharePoint Online (SPO)**|**On-premises SharePoint Server**|
|:-----|:-----|
|Hoge kosten in de tijd (plan/uitvoering/verificatie)  <br/> |Hoge kosten in de tijd (plan/uitvoering/verificatie)  <br/> |
|Lagere kosten in fondsen (geen hardwareaankopen)  <br/> |Hogere kosten in fondsen (hardware + ontwikkelaars/beheerders)  <br/> |
|Een een time cost in migration  <br/> |Een een time cost repeated per future migration  <br/> |
|Lage totale eigendomskosten/onderhoud  <br/> |Hoge totale eigendomskosten/onderhoud  <br/> |
   
Wanneer u migreert naar Microsoft 365, zijn de kosten van de een een-tijdsverhuis hoger, terwijl u gegevens organiseert en bepaalt wat u naar de cloud wilt verplaatsen en wat u moet achterlaten. Maar toekomstige upgrades worden automatisch en u hoeft geen hardware- en software-updates meer te beheren. Ook wordt de uptijd van uw farm gebacked door een Microsoft Service Level Agreement[(SLA).](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement)
  
### <a name="migrate-to-sharepoint-online"></a>Migreren naar SharePoint Online

Zorg ervoor dat SharePoint Online alle functies heeft die u nodig hebt. Zie [Servicebeschrijvingen voor Microsoft 365 en Office 365.](/office365/servicedescriptions/office-365-service-descriptions-technet-library)
  
U kunt niet rechtstreeks migreren van SharePoint 2007 naar SharePoint Online. Uw overstap naar SharePoint Online zou handmatig worden uitgevoerd. Als u een upgrade naar SharePoint Server 2013 of SharePoint Server 2016 hebt uitgevoerd, kunt u de SharePoint-migratie-API gebruiken (bijvoorbeeld om informatie te migreren naar OneDrive voor Bedrijven).
  
|**Onlineprof**|**Online con**|
|:-----|:-----|
|Microsoft levert SPO-hardware en alle hardwarebeheer.  <br/> |Beschikbare functies kunnen verschillen tussen on-premises en SPO van SharePoint Server.  <br/> |
|U bent de globale beheerder van uw abonnement en kunt beheerders toewijzen aan SPO-sites.  <br/> |Sommige acties die beschikbaar zijn voor een farmbeheerder in on-premises SharePoint Server, bestaan niet of worden niet noodzakelijkerwijs opgenomen in de SharePoint-beheerdersrol in Microsoft 365.  <br/> |
|Microsoft past patches, fixes en updates toe op onderliggende hardware en software. <br/> |Omdat er geen toegang is tot het onderliggende bestandssysteem in de service, is de aanpassing beperkt.  <br/> |
|Microsoft publiceert [serviceovereenkomsten en](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement) gaat snel om incidenten op serviceniveau op te lossen. <br/> |Back-up en herstel en andere herstelopties worden geautomatiseerd door de service in SharePoint Online. Back-ups worden overschreven als ze niet worden gebruikt. <br/> |
|Beveiligingstests en het afstemmen van de prestaties van de server worden doorlopend uitgevoerd in de service door Microsoft. <br/> |Wijzigingen in de gebruikersinterface en andere SharePoint-functies worden door de service geïnstalleerd en moeten mogelijk worden in- of uitgeschakeld. <br/> |
|Microsoft 365 voldoet aan veel industriestandaarden: [Microsoft-complianceaanbiedingen.](/compliance/regulatory/offering-home)  <br/> |[FastTrack-ondersteuning](https://www.microsoft.com/fasttrack/microsoft-365) voor migratie is beperkt.  <br/> Een groot deel van de upgrade is handmatig of via de SPO-migratie-API die wordt beschreven in de Roadmap voor [SharePoint Online- en OneDrive-migratie-inhoud.](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)  <br/> |
|Microsoft Support-technici en datacentermedewerkers hebben geen onbeperkte beheerderstoegang tot uw abonnement. <br/> |Er kunnen extra kosten zijn als hardware moet worden bijgewerkt ter ondersteuning van de nieuwere versie van SharePoint of als een secundaire farm vereist is voor een upgrade.  <br/> |
|Partners kunnen u helpen bij de een-time taak om uw gegevens te migreren naar SharePoint Online.  <br/> ||
|Onlineproducten worden automatisch bijgewerkt. Hoewel functies mogelijk worden afgeschaft, is er geen echt einde van de ondersteuning. <br/> ||
   
Als u hebt besloten een nieuwe Microsoft 365-site te maken en gegevens naar deze site handmatig migreert, controleert u uw [Microsoft 365-opties.](https://www.microsoft.com/microsoft-365/)
  
### <a name="upgrade-sharepoint-server-on-premises"></a>On-premises upgrade van SharePoint Server uitvoeren

Er is geen manier om versies over te slaan in SharePoint-upgrades. Upgrades gaan serieel:
  
- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016
   
Als u van SharePoint 2007 naar SharePoint Server 2016 wilt gaan, betekent dit een aanzienlijke tijdsinvestering en kosten in hardware (SQL-servers moeten ook worden bijgewerkt), software en beheer. Aanpassingen moeten worden bijgewerkt of verlaten.
  
> [!NOTE]
> Het is mogelijk om uw SharePoint 2007-farm te onderhouden, een SharePoint Server 2016-farm te installeren op nieuwe hardware (zodat de afzonderlijke farms naast elkaar worden uitgevoerd) en vervolgens een handmatige migratie van inhoud plannen en uitvoeren (bijvoorbeeld voor het downloaden en opnieuw uploaden van inhoud). Maar pas op voor enkele valkuilen van handmatige bewegingen, zoals het verplaatsen van documenten die het laatst gewijzigde account vervangen door de alias van het account die de handmatige beweging doet. Houd ook rekening met het werk dat van tevoren moet worden uitgevoerd, zoals het opnieuw maken van sites, subsites, machtigingen en lijststructuren. Bedenk vooraf welke gegevens u in opslag kunt verplaatsen of verwijderen om de impact van migratie te beperken.
  
Het is belangrijk om uw omgeving op te schonen voordat u een upgrade maakt. Zorg ervoor dat uw bestaande farm functioneel is voordat u een upgrade gaat uitvoeren, en zeker voordat u de farm buiten bedrijf gaat stellen.
  
Vergeet niet om de *ondersteunde en niet-ondersteunde upgradepaden te bekijken:* 
  
- [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)
    
Als u aanpassingen hebt, is het essentieel dat u een plan hebt voor elke stap in het migratiepad: 
  
- [SharePoint 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc263203(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)
    
|**On-premises pro**|**On-premises con**|
|:-----|:-----|
|Volledige controle over alle aspecten van uw SharePoint Farm, vanaf de serverhardware up.  <br/> |Alle onderbrekingen en fixes zijn de verantwoordelijkheid van uw bedrijf (u kunt betaalde Microsoft-ondersteuning in dienst nemen als uw product niet achter het einde van de ondersteuning ligt).  <br/> |
|Volledige functieset van SharePoint Server on-premises met de optie om uw on-premises farm via hybride verbinding te maken met een SharePoint Online-abonnement.  <br/> |Upgrade, patches, beveiligingsfixes en al het onderhoud van SharePoint Server dat on-premises wordt beheerd.  <br/> |
|Volledige toegang voor meer aanpassing.  <br/> |[Microsoft-complianceaanbiedingen](/compliance/regulatory/offering-home) moeten handmatig on-premises zijn geconfigureerd.  <br/> |
|Beveiligingstests en de prestaties van de server worden op uw locatie (onder uw beheer) uitgevoerd.  <br/> |Microsoft 365 kan functies beschikbaar stellen voor SharePoint Online die niet on-premises interopereren met SharePoint Server.  <br/> |
|Partners kunnen u helpen bij het migreren van gegevens naar de volgende versie van SharePoint Server (en daarbuiten).  <br/> |Uw SharePoint Server-sites gebruiken niet automatisch [SSL/TLS-certificaten](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) zoals wordt gezien in SharePoint Online.  <br/> |
|Volledige controle over naamgevingsconventie, back-up maken en herstellen en andere herstelopties in on-premises SharePoint Server.  <br/> |SharePoint Server on-premises is gevoelig voor productlevenscyclussen.  <br/> |
   
### <a name="upgrade-resources"></a>Resources upgraden

Zorg ervoor dat uw omgeving voldoet aan de hardware- en softwarevereisten en volg vervolgens ondersteunde upgrademethoden.
  
- **Hardware-/softwarevereisten voor:** 
    
    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)
    
- **Softwaregrenzen en -limieten voor:** 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)
    
- **Het overzicht van het upgradeproces voor**: 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Een hybride SharePoint-oplossing maken tussen SharePoint Online en on-premises

Als het antwoord op uw migratiebehoeften ergens ligt tussen de zelfcontrole die on-premises wordt geboden en de lagere eigendomskosten die Door SharePoint Online worden aangeboden, kunt u SharePoint Server 2013- of 2016-farms via hybriden verbinden met SharePoint Online. [Meer informatie over hybride SharePoint-oplossingen.](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
Als u besluit dat een hybride SharePoint Server-farm ten goede komt aan uw bedrijf, moet u vertrouwd raken met de bestaande typen hybriden en hoe u de verbinding configureert tussen uw on-premises SharePoint-farm en uw Microsoft 365-abonnement.
  
| Optie | Beschrijving |
|:-----|:-----|
[Microsoft complianceopties](/compliance/regulatory/offering-home)  <br/> |[FastTrack-ondersteuning](https://www.microsoft.com/fasttrack/microsoft-365) voor migratie is beperkt.  <br/> Een groot deel van de upgrade zal handmatig zijn, of via de SPO-migratie-API die wordt beschreven in de [SharePoint Online- en OneDrive-routekaart voor migratie-inhoud.](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)  <br/> |
|Microsoft Support-technici en medewerkers van het datacenter hebben geen onbeperkte beheerderstoegang tot uw abonnement.<br/> |Er kunnen extra kosten zijn als de hardwareinfrastructuur moet worden bijgewerkt ter ondersteuning van de nieuwere versie van SharePoint of als een secundaire farm vereist is voor een upgrade.  <br/> |
|Partners kunnen u helpen bij de een-time taak om uw gegevens te migreren naar SharePoint Online.  <br/> ||
|Onlineproducten worden automatisch bijgewerkt in de service. Hoewel functies mogelijk worden afgeschaft, is er geen echt einde van de ondersteuning.<br/> ||
   
Als u hebt besloten een nieuwe Microsoft 365-site te maken en gegevens naar deze site handmatig migreert, controleert u uw [Microsoft 365-opties.](https://www.microsoft.com/microsoft-365/)
  
### <a name="upgrade-sharepoint-server-on-premises"></a>On-premises upgrade van SharePoint Server uitvoeren

Er is geen manier om versies over te slaan in SharePoint-upgrades. Upgrades gaan serieel:
  
- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016
   
Als u van SharePoint 2007 naar SharePoint Server 2016 wilt gaan, betekent dit een aanzienlijke tijdsinvestering en kosten voor hardware (SQL-servers moeten ook worden bijgewerkt), software en beheer. Aanpassingen moeten worden bijgewerkt of verlaten.
  
> [!NOTE]
> Het is mogelijk om uw SharePoint 2007-farm te onderhouden, een SharePoint Server 2016-farm te installeren op nieuwe hardware (zodat de afzonderlijke farms naast elkaar worden uitgevoerd) en vervolgens een handmatige migratie van inhoud plannen en uitvoeren (bijvoorbeeld voor het downloaden en opnieuw uploaden van inhoud). Maar pas op voor mogelijke valkuilen van handmatige bewegingen, zoals het verplaatsen van documenten die het laatst gewijzigde account vervangen door de alias van het account die de handmatige beweging doet, en het werk dat van tevoren moet worden uitgevoerd, zoals het opnieuw maken van sites, subsites, machtigingen en lijststructuren. Overweeg welke gegevens u kunt opslaan of verwijderen om de impact van migratie te beperken.
  
Maak uw omgeving schoon vóór de upgrade. Zorg ervoor dat uw bestaande farm functioneel is voordat u een upgrade gaat uitvoeren en zeker voordat u buiten bedrijf wordt gesteld. 
  
Vergeet niet om de *ondersteunde en niet-ondersteunde upgradepaden te bekijken:* 
  
- [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)
    
Als u aanpassingen *hebt,* is het essentieel dat u een plan hebt voor uw upgrade voor elke stap in het migratiepad: 
  
- [SharePoint 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc263203(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)
    
|**On-premises Pro**|**On-premises Con**|
|:-----|:-----|
|Volledige controle over alle aspecten van uw SharePoint Farm, vanaf de serverhardware up.  <br/> |Alle onderbrekingen en fixes zijn de verantwoordelijkheid van uw bedrijf. (U kunt betaalde Microsoft-ondersteuning gebruiken als uw product nog niet voorbij het einde van de ondersteuning is.)  <br/> |
|Volledige functieset van SharePoint Server on-premises met de optie om uw on-premises farm via hybride verbinding te maken met een SharePoint Online-abonnement.  <br/> |Upgrade, patches, beveiligingsfixes en al het onderhoud van SharePoint Server dat on-premises wordt beheerd.  <br/> |
|Volledige toegang voor meer aanpassing.  <br/> |[Microsoft-complianceaanbiedingen](/compliance/regulatory/offering-home) moeten handmatig on-premises zijn geconfigureerd.  <br/> |
|Beveiligingstests en het afstemmen van de prestaties van de server worden uitgevoerd op uw locatie onder uw beheer.  <br/> |Microsoft 365 maakt mogelijk functies beschikbaar voor SharePoint Online die niet interopereren met on-premises SharePoint Server  <br/> |
|Partners kunnen helpen bij het migreren van gegevens naar de volgende versie van SharePoint Server (en daarbuiten).  <br/> |Uw SharePoint Server-sites gebruiken niet automatisch [SSL/TLS-certificaten,](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) zoals wordt gezien in SharePoint Online.  <br/> |
|Volledige controle over naamgevingsconventie, back-up maken en herstellen en andere herstelopties in on-premises SharePoint Server.  <br/> |SharePoint Server on-premises is gevoelig voor productlevenscyclussen.  <br/> |
   
### <a name="upgrade-resources"></a>Resources upgraden

Zorg ervoor dat uw omgeving voldoet aan de hardware- en softwarevereisten. Volg vervolgens de ondersteunde upgrademethoden.
  
- **Hardware-/softwarevereisten voor:** 
    
    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)
    
- **Softwaregrenzen en -limieten voor:** 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)
    
- **Het overzicht van het upgradeproces voor:** 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Een hybride SharePoint-oplossing maken tussen SharePoint Online en on-premises

Als het antwoord op uw migratiebehoeften ergens ligt tussen de zelfcontrole die on-premises wordt geboden en de lagere eigendomskosten die Door SharePoint Online worden aangeboden, kunt u SharePoint Server 2013- of 2016-farms via hybriden verbinden met SharePoint Online. [Meer informatie over hybride SharePoint-oplossingen](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
Als u besluit dat een hybride SharePoint Server-farm ten goede komt aan uw bedrijf, moet u vertrouwd raken met de bestaande typen hybriden en hoe u de verbinding configureert tussen uw on-premises SharePoint-farm en uw Microsoft 365-abonnement.
  
Een goede manier om te zien hoe dit werkt, is door een Microsoft 365-dev/testomgeving te maken, die u kunt instellen met [Test Lab Guides.](m365-enterprise-test-lab-guides.md) Nadat u een proefabonnement hebt of een Microsoft 365-abonnement hebt gekocht, kunt u de siteverzamelingen, webs en documentbibliotheken maken in SharePoint Online waar u gegevens kunt migreren. U kunt handmatig migreren met de migratie-API of, als u Mijn site-inhoud wilt migreren naar OneDrive voor Bedrijven, via de hybride wizard.
  
> [!NOTE]
> Als u de hybride optie wilt gebruiken, moet uw SharePoint 2007-farm on-premises worden bijgewerkt naar SharePoint Server 2013 of SharePoint Server 2016.
  
## <a name="related-topics"></a>Verwante onderwerpen

[Problemen oplossen en de upgrade hervatten (Office SharePoint Server 2007)](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262967(v=office.12))
  
[Upgradeproblemen oplossen (SharePoint Server 2010)](/previous-versions/office/sharepoint-server-2010/cc262967(v=office.14))
  
[Problemen met database-upgrade oplossen in SharePoint 2013](/SharePoint/upgrade-and-update/troubleshoot-database-upgrade-issues-in-sharepoint-2013)
  
[Microsoft-partners zoeken om te helpen met upgraden](https://go.microsoft.com/fwlink/?linkid=841249)
  
[Resources om u te helpen bij het upgraden van Office 2007-servers en -clients](upgrade-from-office-2007-servers-and-products.md)
