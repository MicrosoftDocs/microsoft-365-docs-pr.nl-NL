---
title: Netwerk-en migratieplanning voor Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132
description: Dit artikel bevat koppelingen naar informatie over netwerk planning, tests en migratie naar Office 365.
ms.openlocfilehash: 1e6973f93c65012f4ca007332a47cc6b9e67b3b0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689505"
---
# <a name="network-and-migration-planning-for-office-365"></a>Netwerk-en migratieplanning voor Office 365

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Dit artikel bevat koppelingen naar informatie over netwerk planning en testen, en migratie naar Office 365.
  
Voordat u de eerste keer implementeert of migreert naar Office 365, kunt u de informatie in deze onderwerpen gebruiken om de bandbreedte die u nodig hebt te ramen en vervolgens te testen en te controleren of u voldoende bandbreedte hebt voor de implementatie of migratie naar Office 365.

Dit artikel maakt onderdeel uit van [netwerk planning en prestaties optimaliseren voor Office 365](https://aka.ms/tune).

Voor de stappen voor het optimaliseren van uw netwerk voor Microsoft 365 en andere Microsoft Cloud-platformen en-services raadpleegt u de poster [Microsoft Cloud Networking for Enterprise Architects](https://aka.ms/cloudarchnetworking) .
   
## <a name="estimate-network-bandwidth-requirements"></a>Vereisten voor netwerkbandbreedte schatten
<a name="EstimateBandwidthRequirements"> </a>

Als u Office 365 gebruikt, is het mogelijk dat het Internet circuit van uw organisatie groter wordt. Het is belangrijk om te bepalen of de bandbreedte die op dat moment beschikbaar is, voldoende is voor het verwerken van de geschatte toename nadat Office 365 volledig is geïmplementeerd, terwijl de meeste activiteit bovenaan van de dag minstens 20% uitvalt.
  
Gebruik de volgende stappen om de bandbreedte te ramen:
  
1. Het aantal clients beoordelen dat elke Internet-uituitgang moet gebruiken. Laat onze multi-Terabit netwerk-handle zo veel mogelijk zijn. 
    
2. Bepalen welke Office 365-Services en-functies beschikbaar zijn voor gebruik door clients. U zult waarschijnlijk groepen mensen met verschillende services of gebruiks profielen hebben.
    
3. Meet het netwerk gebruik voor een testgroep clients. Zorg ervoor dat de pilot cliënten representatief zijn voor de verschillende profielen van personen in de organisatie en van de verschillende geografische locaties. U kunt uw resultaten interkijken tegen onze oude rekenmachines voor [Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/announcing-the-exchange-client-network-bandwidth-calculator-beta/ba-p/601744) en [Skype voor bedrijven](https://go.microsoft.com/fwlink/p/?LinkId=321551) [of de casestudy](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365) die we hebben uitgevoerd op ons eigen netwerk. 
    
4. Gebruik de meetwaarden van de testgroep om de behoeften van de gehele organisatie te extrapoleren, en voer de test opnieuw uit om de schattingen te valideren voordat u wijzigingen aanbrengt in uw netwerk.
    
## <a name="test-your-existing-network"></a>Uw bestaande netwerk testen
<a name="calculators"> </a>

 **Netwerkhulpprogramma's.** Test de Internet bandbreedte en valideer deze om de beperkingen voor downloaden, uploaden en latentie te bepalen. Met deze hulpmiddelen kunt u bepalen welke mogelijkheden van uw netwerk voor migratie en wanneer u volledig bent geïmplementeerd. 
    
- [Microsoft Remote Connectivity Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=517243): Hiermee wordt de verbinding naar uw Exchange Online-omgeving getest.
    
- Gebruik [Microsoft ondersteuning en herstel ondersteuning voor Office 365](https://diagnostics.office.com/#/Download?env=SOC) voor het oplossen van problemen met Outlook en Office 365. 
    
## <a name="best-practices-for-network-planning-and-improving-migration-performance-for-office-365"></a>Aanbevolen procedures voor de netwerk planning en het verbeteren van de migratie prestaties voor Office 365
<a name="BestPractices"> </a>

U vindt meer informatie over het verbeteren van de volgende aanbevolen procedures voor meer informatie over het verbeteren van uw Office 365-ervaring.
  
1. Wilt u uw gebruikers direct laten helpen? Zie [Aanbevolen procedures voor het gebruik van office 365 op een traag netwerk](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) voor tips over het gebruik van Office 365, waaronder SharePoint Online, Exchange Online en Lync online, wanneer uw netwerk gewoon niet werkt. Dit artikel bevat informatie over de inhoud van TechNet en Support.office.com voor het optimaliseren van uw Office 365-ervaring en bevat informatie over eenvoudige manieren om uw webpagina's aan te passen en over het instellen van de Internet Explorer-instellingen voor de beste Office 365-ervaring. 
    
2. Lees de beginselen van de [netwerkverbinding van office 365](https://aka.ms/o365networkingprinciples) als u inzicht wilt krijgen in de verbindings principes voor het veilig beheren van Office 365-verkeer en de best mogelijke prestaties te verkrijgen. In dit artikel vindt u informatie over de meest recente richtlijnen voor het veilig optimaliseren van Office 365-netwerkverbindingen. 
    
3. Verbeter de prestaties van de afdruk migratie door de planning voor Windows-updates nauwkeurig te beheren. U kunt de clientcomputers in batches bijwerken en ervoor zorgen dat alle clientcomputers worden bijgewerkt voordat u naar Office 365 migreert en het gebruik van de netwerkbandbreedte bepaalt. Zie voor meer informatie [het artikel bureaublad versies van Office 365 handmatig bijwerken en configureren voor de meest recente updates](https://support.microsoft.com/gp/office-2013-365-update).
    
4. Het netwerkverkeer van Office 365 presteert het best wanneer het wordt behandeld als een vertrouwde Internet service en dat het is toegestaan om het traditionele filteren te omzeilen en om te controleren of sommige organisaties het netwerkverkeer op niet-vertrouwde Internet Services plaatsen. Dit omvat meestal het verwijderen van uitgaande verwerking, zoals proxy gebruikersverificatie en pakket controle, en om lokale uitputting van Internet te garanderen met de juiste NAT (Network Address Translation) en voldoende bandbreedte voor het verwerken van de toegenomen netwerkaanvragen. Raadpleeg [office 365-eindpunten beheren](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)voor meer informatie over het configureren van uw netwerk voor het verwerken van Office 365 als een vertrouwde Internet service op uw netwerk.
    
1. Zorg ervoor dat u [Office 365-eindpunten beheert](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a). Het extra verkeer naar Office 365 resulteert in een toename van uitgaande proxyverbindingen en een toename van veilig verkeer via TLS/SSL.
    
2. Als voor uw uitgaande proxy's Gebruikersauthenticatie is vereist, kunt u trage verbinding of een verlies van functionaliteit ondervinden. Als u de authenticatie vereiste voor de Office 365-domeinen overslaat, kan dit leiden tot minder overhead.
    
3. Als u een groot aantal gedeelde agenda's en postvakken hebt, ziet u mogelijk een grotere hoeveelheid verbindingen van Outlook naar Exchange. De Outlook-client kan bijvoorbeeld tot twee extra verbindingen openen voor elke gedeelde agenda die wordt gebruikt. In deze situatie zorgt u ervoor dat de oplossings proxy de verbindingen aankan of de proxy voor verbindingen met Office 365 voor Outlook overslaan.
    
4. Het maximum aantal ondersteunde apparaten voor een openbaar IP-adres bepalen en de balans tussen meerdere IP-adressen verdelen. Zie [ondersteuning voor nat met Office 365](nat-support-with-microsoft-365.md)voor meer informatie.
    
5. Als u uitgaande verbindingen vanaf computers in uw netwerk inspecteert, is 365 het niet mogelijk om de verbinding en de prestaties van dit filter te negeren. Daarnaast verwijdert vaak ook uitgaande inspectie de noodzaak voor een enkele Internet verbinding en schakelt lokale Internet-uitsluitingen voor Office 365 met netwerkaanvragen.
    
6. Sommige klanten kunnen de prestaties van de interne netwerkinstellingen bepalen. Instellingen zoals maximale grootte van Transmission Unit (MTU), automatische onderhandeling van netwerk of automatische detectie, en de meeste optimale routering van Internet zijn algemene locaties waar u kunt zoeken.
    
## <a name="network-planning-reference-for-office-365"></a>Naslagwerk voor netwerk planning voor Office 365
<a name="NetReference"> </a>

Deze onderwerpen bevatten gedetailleerde informatie over de netwerk informatie voor Office 365.
  
- [Office 365-eindpunten beheren](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
    
- [Netwerken voor content levering](content-delivery-networks.md)
    
- [Externe DNS-records (Domain Name System) voor Office 365](external-domain-name-system-records.md)
    
- [IPv6-ondersteuning in Office 365-Services](ipv6-support.md)
    
- [Methoden voor netwerkverbindingen in Office 365](https://aka.ms/o365networkingprinciples)
    
- [Veelgestelde vragen over Office 365 video-netwerken](office-365-video-networking-faq.md)
    
- [Plan voor netwerkapparaten die verbinding maken met Office 365-Services](plan-for-network-devices.md)
    
- [Installatie handleidingen voor Office 365-Services](setup-guides-for-microsoft-365.md)
 
## <a name="see-also"></a>Zie ook

[Overzicht van Microsoft 365 Enterprise](microsoft-365-overview.md)
