---
title: Upgraden vanaf SharePoint 2010
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 04/13/2020
audience: ITPro
ms.topic: conceptual
ms.prod: office-online-server
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- WSU140
- OSU140
ms.assetid: 985a357f-6db7-401f-bf7a-1bafdf1f312c
f1.keywords:
- NOCSH
description: Informatie en bronnen zoeken om een upgrade uit SharePoint 2010 en Sharepoint Server 2010 uit te voeren. Ondersteuning voor beide eindigt op 13 april 2021.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4fa82fb0e382a244cdc126609ac62d17280b9702
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925330"
---
# <a name="upgrading-from-sharepoint-2010"></a>Upgraden vanaf SharePoint 2010

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Microsoft SharePoint 2010 en SharePoint Server 2010 eindigt op **13 april 2021.** In dit artikel vindt u informatiebronnen om uw bestaande SharePoint Server 2010-gegevens te migreren naar SharePoint Online in Microsoft 365 of uw on-premises SharePoint Server 2010-omgeving te upgraden.

## <a name="what-is-end-of-support"></a>Wat is *het einde van de ondersteuning?*

De meeste Microsoft-producten hebben een ondersteuningslevenscyclus, waarin ze nieuwe functies, bugfixes, beveiligingsfixes, en ga zo maar door krijgen. Na het einde van de ondersteuningsdatum werkt het product niet meer, maar Microsoft biedt niet meer:

- Technische ondersteuning voor problemen die kunnen optreden.

- Oplossingen voor problemen die van invloed kunnen zijn op de stabiliteit en bruikbaarheid van de server.

- Beveiligingsfixes voor beveiligingsproblemen die de server kwetsbaar kunnen maken voor beveiligingsinbreuken.

- Tijdzone-updates.

Dit betekent dat er geen verdere updates, patches of fixes voor het product zijn (inclusief beveiligingspatches/fixes). Microsoft-ondersteuning heeft de ondersteuningsinspanningen volledig verplaatst naar recentere versies.

Als het einde van de ondersteuning van SharePoint Server 2010 nadert, verwijdert u gegevens die u niet meer nodig hebt voordat u het product upgradet en uw belangrijke gegevens migreert.

> [!NOTE]
> Een levenscyclus van een software duurt meestal tien jaar vanaf de eerste release. [Microsoft-oplossingsproviders](https://go.microsoft.com/fwlink/?linkid=841249) kunnen u helpen bij het upgraden naar de volgende versie van de software of migreren naar Microsoft 365 (of beide). Zorg ervoor dat u ook op de hoogte bent van datums voor het einde van de ondersteuning voor kritieke onderliggende technologieën, met name voor de versie van Microsoft SQL Server die u gebruikt met SharePoint. Zie Beleid voor vaste levenscyclus [voor meer informatie.](https://support.microsoft.com/help/14085)

## <a name="plan-ahead"></a>Vooruit plannen

Controleer de datums die ondersteuning bieden eindigt op de [productlevenscyclussite.](https://support.microsoft.com/lifecycle/search?alpha=SharePoint%20Server%202010) Plan uw upgrades of migraties met deze datums in gedachten. Vergeet niet dat uw product *niet stopt met werken op* de vermelde datum. Maar omdat de installatie na die datum niet meer wordt gepatcht, wilt u een soepele overgang naar de volgende versie van het product plannen.

Met deze matrix kunt u een cursus tussen migratieopties plannen:

|Einde van ondersteuningsproduct|Goed |Beste|
|---|---|---|
|SharePoint Server 2010|SharePoint Server 2013 (on-premises)|SharePoint Online|
||SharePoint Server 2013 hybride met SharePoint Online|SharePoint Server 2016 (on-premises)|
|||SharePoint Hybride zoeken in de cloud|

Als u een optie kiest aan de lage kant van de schaal (goed), moet u snel na de migratie van SharePoint Server 2010 beginnen met het plannen van een nieuwe upgrade.

Hier volgen de drie paden die u kunt volgen om het einde van de ondersteuning voor SharePoint Server 2010 te voorkomen.

![SharePoint Upgradepaden voor Server 2010](../media/upgrade-from-sharepoint-2010/upgrade-from-sharepoint-2010-paths.png)

> [!NOTE]
> De ondersteuning voor SharePoint Server 2010 en SharePoint Foundation 2010 is momenteel gepland voor 13 april 2021. Maar controleer de [productlevenscyclussite op](https://support.microsoft.com/lifecycle) de meest recente datums.

## <a name="whats-next"></a>En nu?

SharePoint Server 2013 en SharePoint Foundation 2013 kunnen on-premises worden geïnstalleerd op uw eigen servers. Of u kunt SharePoint Online gebruiken, een onlineservice die deel uitmaakt van Microsoft 365. U kunt kiezen uit:

- Migreren naar SharePoint Online.

- Upgrade SharePoint Server of SharePoint Foundation on-premises.

- Doe beide van het bovenstaande.

- Implementeert [een SharePoint hybride](/sharepoint/hybrid/hybrid) oplossing.

Houd rekening met de verborgen kosten voor het onderhouden van een serverfarm, zoals het onderhouden of migreren van aanpassingen en het upgraden van hardware. Als u rekening hebt gehouden met deze factoren, is het gemakkelijker om on-premises een upgrade uit te voeren. Als u uw farm runt op oudere SharePoint servers zonder zware aanpassingen, kunt u profiteren van een geplande migratie naar SharePoint Online. Voor een on-premises SharePoint Server-omgeving kunt u ook overwegen bepaalde gegevens te verplaatsen in SharePoint Online om de overhead van hardwarebeheer te beperken.

> [!NOTE]
> SharePoint beheerders kunnen een Microsoft 365-abonnement maken, nieuwe SharePoint Online-sites instellen en vervolgens op een schone manier wegblijven van SharePoint Server 2010, waarbij alleen essentiële documenten naar de nieuwe sites worden verwijderd. Vervolgens kunnen alle resterende gegevens worden gedraineerd van SharePoint Server 2010-site naar on-premises archieven.

|SharePoint Online|SharePoint Server on-premises|
|---|---|
|Hoge kosten in de tijd (plan/uitvoering/verificatie)|Hoge kosten in de tijd (plan/uitvoering/verificatie)|
|Lagere kosten in fondsen (geen hardwareaankopen)|Hogere kosten in fondsen (hardwareaankopen)|
|Een een time cost in migration|Een een time cost repeated per future migration|
|Lage totale eigendomskosten/onderhoud|Hoge totale eigendomskosten/onderhoud|

Een een time move naar Microsoft 365 kosten hoger zijn terwijl u gegevens organiseert en bepaalt wat u naar de cloud wilt verplaatsen en wat u moet achterlaten. Maar nadat uw gegevens zijn gemigreerd, worden toekomstige upgrades automatisch geïnstalleerd, omdat u geen hardware- en software-updates meer hoeft te beheren. En de up time van uw farm wordt gebacked door een [Microsoft Service Level Agreement (SLA)](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement).

### <a name="migrate-to-sharepoint-online"></a>Migreren naar SharePoint Online

Zorg ervoor SharePoint Online alle functies biedt die u nodig hebt. Zie [SharePoint servicebeschrijving](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description).

U kunt niet rechtstreeks migreren van SharePoint Server 2010 (of SharePoint Foundation 2010) naar SharePoint Online. Een groot deel van het migratiewerk is handmatig. Maar in deze fase kunt u gegevens en sites die niet meer nodig zijn vóór de verhuizing, snoeien. U kunt andere gegevens archiveren naar opslag. 

Vergeet niet SharePoint Server 2010 en SharePoint Foundation 2010 niet stopt met werken aan het einde van de ondersteuning. Beheerders kunnen dus een periode hebben waarop SharePoint actief is als hun klanten sommige gegevens vergeten te verplaatsen.

Als u een upgrade naar SharePoint Server 2013 of SharePoint Server 2016 hebt uitgevoerd en besluit gegevens in SharePoint Online te zetten, kunt u de [SharePoint-migratie-API](https://support.office.com/article/Upload-on-premises-content-to-SharePoint-Online-using-PowerShell-cmdlets-555049c6-15ef-45a6-9a1f-a1ef673b867c?ui=en-US&amp;rs=en-US&amp;ad=US) gebruiken om gegevens te migreren naar OneDrive voor Bedrijven.

|SharePoint Onlinevoordeel|SharePoint Online nadeel|
|---|---|
|Microsoft levert SPO-hardware en alle hardwarebeheer.|Beschikbare functies kunnen verschillen tussen SharePoint Server on-premises en SPO.|
|U bent de globale beheerder van uw abonnement en kunt beheerders toewijzen aan SPO-sites.|Sommige acties die beschikbaar zijn voor een farmbeheerder in SharePoint Server on-premises bestaan niet (of zijn niet nodig) in de rol SharePoint Beheerder in Microsoft 365. Maar SharePoint beheer, beheer van siteverzamelingen en sitebezit zijn lokaal voor uw organisatie.|
|Microsoft past patches, fixes en updates toe op onderliggende hardware en software, SQL servers waarop SharePoint Online wordt uitgevoerd.|Omdat er geen toegang is tot het onderliggende bestandssysteem in de service, is de aanpassing beperkt.|
|Microsoft publiceert [serviceovereenkomsten en](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement) gaat snel om incidenten op serviceniveau op te lossen.|Back-up en herstel en andere herstelopties worden geautomatiseerd door de service in SharePoint Online. Back-ups worden overschreven als ze niet worden gebruikt.|
|Beveiligingstests en prestatieafstemming op de server worden continu uitgevoerd in de service door Microsoft.|Wijzigingen in de gebruikersinterface en andere SharePoint functies worden geïnstalleerd door de service en moeten mogelijk worden in- of uitgeschakeld.|
|Microsoft 365 voldoet aan een groot aantal industriestandaarden: [Microsoft-complianceaanbiedingen.](/compliance/regulatory/offering-home)|[FastTrack-ondersteuning](https://go.microsoft.com/fwlink/?linkid=518597) voor migratie is beperkt.  <br/> Een groot deel van de upgrade is handmatig of via de SPO-migratie-API die wordt beschreven in de SharePoint [Online en OneDrive Roadmap voor migratie-inhoud.](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)|
|Microsoft Support-technici en datacentermedewerkers hebben geen onbeperkte beheerderstoegang tot uw abonnement.|Er kunnen extra kosten zijn als de hardwareinfrastructuur moet worden bijgewerkt ter ondersteuning van de nieuwere versie van SharePoint of als een secundaire farm vereist is voor een upgrade.|
|Oplossingsproviders kunnen u helpen bij de een-time taak om uw gegevens te migreren naar SharePoint Online.|Niet alle wijzigingen in SharePoint Online zijn binnen uw beheer. Na de migratie kunnen ontwerpverschillen in menu's, bibliotheken en andere functies tijdelijk van invloed zijn op de bruikbaarheid.|
|Onlineproducten worden automatisch bijgewerkt in de service. Functies kunnen worden afgeschaft, maar er is geen echt einde van de ondersteuningscyclus.|Er is een levenscyclus voor end-of-support voor SharePoint Server of SharePoint Foundation en onderliggende SQL servers.|

Als u hebt besloten een nieuwe site Microsoft 365 maken en gegevens naar deze site handmatig migreert, controleert u de Microsoft 365 [opties.](https://www.microsoft.com/microsoft-365/)

### <a name="upgrade-sharepoint-server-on-premises"></a>On-premises SharePoint server upgraden

Vanaf SharePoint Server 2019 moeten upgrades *serieel worden gebruikt.* U kunt geen upgrade uitvoeren van SharePoint Server 2010 naar SharePoint Server 2016 of rechtstreeks SharePoint 2019. Serieel upgradepad:

- SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016

Het duurt even en het duurt even om het hele pad van SharePoint 2010 naar SharePoint Server 2016 te volgen. Upgrades brengen kosten met zich mee voor hardware (SQL servers moeten ook worden bijgewerkt), software en beheer. Het kan ook nodig zijn om aanpassingen te upgraden of zelfs te verlaten. Zorg ervoor dat u belangrijke aanpassingen documenteert voordat u een upgrade SharePoint Serverfarm.

> [!NOTE]
> Het is mogelijk om uw end-of-support SharePoint 2010-farm te behouden, een SharePoint Server 2016-farm te installeren op nieuwe hardware (zodat de afzonderlijke farms naast elkaar worden uitgevoerd) en vervolgens een handmatige migratie van inhoud plannen en uitvoeren (bijvoorbeeld voor het downloaden en opnieuw uploaden van inhoud). Maar er zijn mogelijke valkuilen voor deze handmatige bewegingen, zoals documenten die afkomstig zijn uit 2010 met een huidig, laatst gewijzigd account met de alias van het account dat de handmatige beweging doet. En sommige werkzaamheden moeten van tevoren worden uitgevoerd, zoals het opnieuw maken van sites, subsites, machtigingen en lijststructuren. Zorg ervoor dat u uw omgeving reinigt vóór de upgrade. Overweeg welke gegevens u in opslag kunt verplaatsen of niet meer nodig hebt. Dit kan de impact van migratie verminderen. Zorg ervoor dat uw bestaande farm functioneel is voordat u een upgrade gaat uitvoeren, en (zeker) voordat u de farm buiten bedrijf gaat stellen.

Vergeet niet om de *ondersteunde en niet-ondersteunde upgradepaden te bekijken:*

- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)

Als u aanpassingen *hebt,* is het essentieel dat u voor elke stap in het migratiepad van plan bent:

- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)

|On-premises voordeel|On-premises nadeel|
|---|---|
|Volledige controle over alle aspecten van uw SharePoint Farm (en de SQL), vanaf de serverhardware.|Alle onderbrekingen en fixes zijn de verantwoordelijkheid van uw bedrijf. Maar u kunt betaalde Microsoft-ondersteuning gebruiken als uw product nog niet is afgelopen met de ondersteuning.|
|Volledige functieset van SharePoint Server on-premises met de optie om uw on-premises farm te verbinden met een SharePoint Online-abonnement via hybride.|Upgrade, patches, beveiligingsverbeteringen, hardware-upgrades en al het onderhoud van SharePoint Server en de SQL farm worden on-premises beheerd.|
|Volledige toegang voor grotere aanpassingsopties dan met SharePoint Online.|[Microsoft-complianceaanbiedingen](/compliance/regulatory/offering-home) moeten handmatig on-premises zijn geconfigureerd.|
|Beveiligingstests en het afstemmen van de prestaties van de server worden uitgevoerd op uw locatie onder uw beheer.|Microsoft 365 mogelijk functies beschikbaar maken voor SharePoint Online die niet interopereren met SharePoint Server on-premises.|
|Oplossingsproviders kunnen gegevens migreren naar de volgende versie van SharePoint Server (en daarbuiten).|Uw SharePoint Serversites gebruiken niet automatisch [SSL/TLS-certificaten,](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) zoals wordt gezien in SharePoint Online.|
|Volledige controle over naamgevingsconventie en back-up- en herstelopties en andere herstelopties in SharePoint Server on-premises.|SharePoint Server on-premises is gevoelig voor productlevenscyclussen.|

### <a name="upgrade-resources"></a>Resources upgraden

Begin met het vergelijken van hardware- en softwarevereisten. Als uw huidige omgeving niet aan de basisvereisten voldoet, moet u mogelijk eerst de hardware in de farm of de SQL upgraden. 

U kunt besluiten sommige van uw sites te verplaatsen naar de 'evergreen' hardware van SharePoint Online. Nadat u de evaluatie hebt uitgevoerd, volgt u ondersteunde upgradepaden en -methoden.

- *Hardware-/softwarevereisten voor:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)

- *Softwaregrenzen en -limieten voor:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)

- *Het overzicht van het upgradeproces voor:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)

### <a name="create-a-hybrid-solution-with-sharepoint-online-and-sharepoint-server-on-premises"></a>Een hybride oplossing maken met SharePoint Online en SharePoint Server on-premises

Een hybride installatie biedt het beste van zowel on-premises als online voor bepaalde migratiebehoeften. U kunt SharePoint Server 2013-, 2016- of 2019-farms verbinden met SharePoint Online om een hybride SharePoint te maken: Meer informatie over SharePoint [hybride oplossingen.](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)

Als een hybride SharePoint serverfarm uw migratiedoel is, kunt u zien welke sites en gebruikers online moeten worden verplaatst en welke on-premises moeten blijven. Door uw SharePoint serverfarminhoud te rangschikken als hoge, gemiddelde of lage impact voor uw bedrijf, kan dit helpen bij deze beslissing. Mogelijk hoeft u alleen gebruikersaccounts te delen om u aan te melden en de SharePoint serverzoekindex met SharePoint Online. Maar deze factor is mogelijk pas duidelijk wanneer u bekijkt hoe uw sites worden gebruikt. Als uw bedrijf later besluit om al uw inhoud te migreren naar SharePoint Online, kunt u alle resterende accounts en gegevens online verplaatsen en uw on-premises farm buiten bedrijf stellen. Beheer/beheer van de SharePoint farm wordt vanaf dat moment Microsoft 365 consoles uitgevoerd.

Zorg ervoor dat u vertrouwd bent met de bestaande typen hybriden en hoe u de verbinding configureert tussen uw on-premises SharePoint farm en uw Microsoft 365 abonnement.

|Optie|Beschrijving|
|---|---|
|[Microsoft-complianceaanbiedingen](/compliance/regulatory/offering-home).|[FastTrack-ondersteuning](https://www.microsoft.com/fasttrack/microsoft-365) voor migratie is beperkt.<br/><br/> Een groot deel van de upgrade is handmatig of via de SPO-migratie-API die wordt beschreven in de SharePoint [Online en OneDrive Roadmap voor migratie-inhoud.](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)|
|Microsoft Support-technici en datacentermedewerkers hebben geen onbeperkte beheerderstoegang tot uw abonnement.|Er kunnen extra kosten zijn als de hardwareinfrastructuur moet worden bijgewerkt ter ondersteuning van de nieuwere versie van SharePoint of als een secundaire farm vereist is.|
|Partners kunnen u helpen bij de een-time taak om uw gegevens te migreren naar SharePoint Online.||
|Onlineproducten worden automatisch bijgewerkt in de service. Functies kunnen worden afgeschaft, maar er is geen echt einde van de ondersteuning.||

Als u hebt besloten een nieuwe site te maken Microsoft 365 gegevens handmatig naar de site te migreren, controleert u de Microsoft 365 [opties.](https://www.microsoft.com/microsoft-365/)

### <a name="upgrade-sharepoint-server-on-premises"></a>On-premises SharePoint server upgraden

Er is geen manier om versies over te slaan in SharePoint Upgrades. Dat betekent dat upgrades serieel worden gebruikt:

- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016

Als u het hele pad van SharePoint 2007 naar SharePoint Server 2016 wilt volgen, betekent dit een aanzienlijke tijdsinvestering en zijn hardware (SQL-servers moeten ook worden bijgewerkt), software en beheerkosten. Aanpassingen moeten worden bijgewerkt of verlaten, afhankelijk van de kritiek van de functie.

> [!NOTE]
> U kunt uw end-of-life SharePoint 2007-farm behouden, een SharePoint Server 2016-farm installeren op nieuwe hardware (zodat de afzonderlijke farms naast elkaar worden uitgevoerd) en vervolgens een handmatige migratie van inhoud plannen en uitvoeren (bijvoorbeeld voor het downloaden en opnieuw uploaden van inhoud). Maar er zijn enkele nadelen aan deze handmatige bewegingen, zoals het verplaatsen van documenten die het laatste gewijzigde account vervangen door de alias van het account dat handmatig wordt verplaatst. En er moet van tevoren veel werk worden gedaan, zoals het opnieuw maken van sites, subsites, machtigingen en lijststructuren. Bedenk in elk geval welke gegevens u in opslag kunt verplaatsen of niet meer nodig hebt om de impact van migratie te beperken.

Zorg ervoor dat u uw omgeving reinigt vóór de upgrade. Zorg ervoor dat uw bestaande farm functioneel is voordat u een upgrade gaat uitvoeren, en zeker voordat u de farm buiten bedrijf gaat stellen.

Vergeet niet om de *ondersteunde en niet-ondersteunde upgradepaden te bekijken:*

- [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))

- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)

Als u aanpassingen *hebt,* is het essentieel om de upgrade voor elke stap in het migratiepad te plannen:

- [SharePoint 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc263203(v=office.12))

- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)

|On-premises pro|On-premises con|
|---|---|
|Volledige controle over alle aspecten van uw SharePoint Farm, vanaf de serverhardware.|Alle onderbrekingen en fixes zijn de verantwoordelijkheid van uw bedrijf. (Maar u kunt betaalde Microsoft-ondersteuning gebruiken als uw product niet achter het einde van de ondersteuning ligt.)|
|Volledige functieset van SharePoint Server on-premises met de optie om uw on-premises farm te verbinden met een SharePoint Online-abonnement via hybride.|Upgrade, patches, beveiligingsfixes en al het onderhoud van SharePoint server die on-premises wordt beheerd.|
|Volledige toegang voor meer aanpassing.|[Microsoft-complianceaanbiedingen](/compliance/regulatory/offering-home) moeten handmatig on-premises zijn geconfigureerd.|
|Beveiligingstests en het afstemmen van de prestaties van de server worden uitgevoerd op uw locatie onder uw beheer.|Microsoft 365 mogelijk functies beschikbaar maken voor SharePoint Online die niet interopereren met SharePoint Server on-premises.|
|Partners kunnen gegevens migreren naar de volgende versie van SharePoint Server (en daarbuiten).|Uw SharePoint Serversites gebruiken niet automatisch [SSL/TLS-certificaten,](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) zoals wordt gezien in SharePoint Online.|
|Volledige controle over naamgevingsconventie en back-up- en herstelopties en andere herstelopties in SharePoint Server on-premises.|SharePoint Server on-premises is gevoelig voor productlevenscyclussen.|

### <a name="upgrade-resources"></a>Resources upgraden

Begin met te weten dat u voldoet aan de hardware- en softwarevereisten en volg vervolgens ondersteunde upgrademethoden.

- *Hardware-/softwarevereisten voor:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)

- *Softwaregrenzen en -limieten voor:*

    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)

- *Het overzicht van het upgradeproces voor*:

    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)

### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Een SharePoint hybride oplossing maken tussen SharePoint Online en on-premises

Als het antwoord op uw migratiebehoeften ergens tussen het besturingselement dat on-premises en de lagere eigendomskosten van SharePoint Online worden aangeboden, kunt u SharePoint Server 2013- of 2016-farms via hybriden verbinden met SharePoint Online. [Meer informatie over SharePoint hybride oplossingen](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)

Als u besluit dat een hybride SharePoint Server farm ten goede komt aan uw bedrijf, moet u vertrouwd raken met de bestaande typen hybriden en hoe u de verbinding configureert tussen uw on-premises SharePoint farm en uw Microsoft 365-abonnement.

Mogelijk wilt u een Microsoft 365 v/testomgeving maken, die u kunt instellen met [Test Lab Guides.](m365-enterprise-test-lab-guides.md) Nadat u een proefabonnement hebt of een Microsoft 365 hebt gekocht, kunt u de siteverzamelingen, webs en documentbibliotheken maken in SharePoint Online waar u gegevens naar kunt migreren. U kunt handmatig migreren met de migratie-API of, als u mijn site-inhoud wilt migreren naar OneDrive voor Bedrijven, via de hybride wizard.

> [!NOTE]
> Als u de hybride optie wilt gebruiken, moet uw SharePoint Server 2010-farm eerst on-premises worden bijgewerkt naar SharePoint Server 2013 of 2016. SharePoint Foundation 2010 en SharePoint Foundation 2013 ondersteunen geen hybride verbindingen met SharePoint Online.

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Overzicht van opties voor Office 2010-client en -servers en Windows 7

Zie het einde van de ondersteuningsposter voor een visueel overzicht van de upgrade, migreren en verplaatsen naar de [](../downloads/Office2010Windows7EndOfSupport.pdf)cloudopties voor Office 2010-clients en -servers en Windows 7.

[![Einde van ondersteuning voor Office 2010-clients en -servers en Windows 7 poster](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Deze poster illustreert de verschillende paden die u kunt volgen om te voorkomen dat Office 2010 client- en serverproducten en Windows 7 einde van ondersteuning, met voorkeurspaden en optieondersteuning in Microsoft 365 Enterprise gemarkeerd.

U kunt deze [poster ook](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) downloaden en afdrukken in de notatie letter, legal of tabloid (11 x 17).

## <a name="related-articles"></a>Aanverwante artikelen

[Resources om u te helpen bij het upgraden Office servers en clients van 2007 of 2010](upgrade-from-office-2010-servers-and-products.md)

[Overzicht van het upgradeproces van SharePoint 2010 tot SharePoint 2013](/SharePoint/upgrade-and-update/overview-of-the-upgrade-process-from-sharepoint-2010-to-sharepoint-2013)

[Best practices voor het upgraden van SharePoint 2010 naar SharePoint 2013](/SharePoint/upgrade-and-update/best-practices-for-upgrading-from-sharepoint-2010-to-sharepoint-2013)

[Problemen met database-upgrade oplossen in SharePoint 2013](/SharePoint/upgrade-and-update/troubleshoot-database-upgrade-issues-in-sharepoint-2013)

[Zoeken naar Microsoft-oplossingsproviders om te helpen met uw upgrade](https://go.microsoft.com/fwlink/?linkid=841249)

[Bijgewerkt productservicebeleid voor SharePoint 2013](/SharePoint/product-servicing-policy/updated-product-servicing-policy-for-sharepoint-2013)

[Bijgewerkt productservicebeleid voor SharePoint Server 2016](/SharePoint/product-servicing-policy/updated-product-servicing-policy-for-sharepoint-server-2016)