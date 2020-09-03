---
title: Microsoft 365 cloudservices beschermen tegen denial-of-service-aanvallen
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: In dit artikel leest u hoe de cloudservices van Microsoft de cloudservices beschermt tegen denial-of-service-aanvallen (DoS).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 21b38950ec06874f8c1d959eeb6a8b60179636e3
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332494"
---
# <a name="defending-microsoft-365-cloud-services-against-denial-of-service-attacks"></a>Microsoft 365 cloudservices beschermen tegen denial-of-service-aanvallen

Microsoft-datacenters zijn auteurs beveiliging tegen een verdedigingslinie, waaronder verbindings omheining, videocamera's, beveiligingspersoneel en veilige ingangen die gebruikmaken van biometrie, smartcardverificatie en meervoudige verificatie. De ingrijpende beveiliging gaat door elk gebied van de faciliteit en tot elke fysieke server eenheid. De [Cloud infrastructuur en de groep activiteiten van Microsoft](https://www.microsoft.com/cloud-platform/global-datacenters) bieden de kern infrastructuur en de Foundation Technologies voor onze Cloud Services. Onze datacenters voldoen aan de industrienormen voor fysieke beveiliging en betrouwbaarheid en worden beheerd, bewaakt en beheerd door Microsoft Operations medewerkers.

Om onze cloudservices verder te beschermen, biedt Microsoft een DDoS-defensie systeem dat deel uitmaakt van de voortdurend bezorgings processen van Microsoft Azure en voor de penetratie. Het Azure DDoS-verdedigings systeem is niet alleen bedoeld voor aanvallen van buiten de kant, maar ook van andere Azure-tenants. Azure gebruikt standaard detectie-en beperkings technieken, zoals SYN-cookies, tarief beperkingen en limieten voor verbindingen, zodat u zich kunt beschermen tegen DDoS-aanvallen.

De cloudservices van Microsoft zijn onderhevig aan de dreiging van aanval via meerdere bronnen. Voor het beperken en beschermen tegen de diverse DoS-bedreigingen zijn er een zeer schaalbare, dynamische, op Azure gebaseerde bedreigings detectie-en risico detectie systemen ontwikkeld en geïmplementeerd met de primaire doelstelling van de bescherming van de onderliggende infrastructuur tegen DoS-aanvallen en om te voorkomen dat de service wordt onderbroken voor klanten van de cloudservices. Het systeem met een beperking van Azure DoS beschermt inkomende en uitgaande berichten en verkeer tussen regio's en regio's.

De meeste DoS-aanvallen die worden gestart tegen doelen op de netwerk (L3) en transport (N4-lagen) van het OSI-model ( [Open Systems Interconnect](https://docs.microsoft.com/windows-hardware/drivers/network/windows-network-architecture-and-the-osi-model) ). Aanvallen die worden doorgestuurd naar de L3-en N4-lagen, zijn ontworpen om een netwerkinterface of service met aanvals verkeer te belopen en de mogelijkheid te weigeren om te reageren op een legitiem verkeer. Met name: gebruik van L3 en N4 probeert de capaciteit van netwerkkoppelingen,-apparaten of-services te verzadigen of de Cpu's te overspoelen van servers of virtuele machines die een toepassing ondersteunen.

Om te beschermen tegen een L3-en N4-aanval, is Microsoft ontworpen, ontwikkeld en geïmplementeerd een oplossing waarmee u de infrastructuur en de doelen van de klant onder aanval kunt beschermen door deze lagen te beschermen. Met het beschermen van de infrastructuur zorgt u ervoor dat er geen schade wordt ondergebracht die bedoeld is voor één klant, geen gevolgen biedt voor onderpand schade of verminderde netwerkkwaliteit van service voor andere klanten Voor de oplossing worden verkeersgegevens gebruikt van datacenter routers. Deze gegevens worden geanalyseerd door een service voor netwerk bewaking om aanvallen te detecteren. Wanneer een aanval wordt gedetecteerd, kunt u geautomatiseerde verdedigings mechanismen starten.

## <a name="application-level-defenses"></a>Verdediging op toepassingsniveau
Microsoft engineering teams volgen de rigoureuze normen die zijn ingesteld door [Microsoft Operational Security Assurance](https://www.microsoft.com/SDL/OperationalSecurityAssurance) om klantgegevens te helpen beschermen. De cloudservices van Microsoft zijn bedoeld voor de ondersteuning van een zeer hoge belasting, en voor het beschermen en verhelpen van aanvallen op toepassingsniveau. We hebben een gescaleeerde architectuur geïmplementeerd waarbij services worden gedistribueerd via meerdere wereldwijde datacenters met regionale isolatie en vertraaging van functies in sommige werklasten.

Het land of de regio van iedere klant die de beheerder van de klant identificeert tijdens de eerste configuratie van de services, bepaalt de primaire opslaglocatie van de gegevens van de klant. Klantgegevens worden via een primaire/back-up van een datacenter gerepliceerd. Een hoofd centrum fungeert voor de software van de toepassing samen met alle primaire klantgegevens die worden uitgevoerd op de software. Een back-up-datacenter biedt automatische failover. Als het primaire datacenter niet meer functioneert vanwege een reden, worden aanvragen omgeleid naar de kopie van de software en CustomerData in de back-up. Op elk gewenst moment kunnen klantgegevens worden verwerkt op de primaire of back-up-datacenter. Als u gegevens in meerdere datacenters distribueert, wordt het desbetreffende oppervlaktegebied verkleind wanneer één datacenter wordt aangetast. Daarnaast kunnen de services in het desbetreffende datacenter snel worden omgeleid naar het tweede datacenter als een van de herstel mechanismen, en vice versa (omgeleid naar het hoofd centrum wanneer de service wordt hersteld).

Afzonderlijke werkbelasting bevat ingebouwde functies waarmee Resourcegebruik wordt beheerd. De beperkings mechanismen in Exchange Online en SharePoint Online maken bijvoorbeeld deel uit van een aanpak met meerdere lagen om DoS-aanvallen te verdedigen. Beperking voor Exchange Online-gebruikers wordt gebaseerd op het niveau van de resources die door de eindgebruiker worden gebruikt, ongeacht of de bronnen zich in de Active Directory, het Exchange Online Information Store of elders bevinden. Voor elke klant wordt een budget toegewezen om de bronnen die door een gebruiker worden gebruikt te beperken. Exchange Online beperken voor de activiteiten van gebruikers en de systeemonderdelen is gebaseerd op het beheer van de [werkbelasting](https://technet.microsoft.com/library/jj150503(v=exchg.150).aspx). Een Exchange Online-werkbelasting is een functie, protocol of service van Exchange Online die expliciet is gedefinieerd voor de doeleinden van Exchange Online System Resource Management. Voor elke Exchange Online-database zijn systeembronnen, zoals processor, Postvakdatabase en Active Directory-aanvragen voor het uitvoeren van gebruikersaanvragen of achtergrond werk. Voorbeelden van Exchange Online-werkbelastingen zijn de webversie van Outlook, Exchange ActiveSync, Postvak migratie en Postvak assistenten. Tenant beheerders kunnen instellingen voor het beheren van de limieten voor Exchange-beheertaken voor gebruikers met de Exchange-beheer shell beheren. Er zijn verschillende vormen van beperking die in Exchange Online zijn geïmplementeerd, waaronder PowerShell, Exchange-webservices, en POP-en IMAP-, Exchange ActiveSync-, mobiele apparaten en andere geadresseerden. Beheerders van on-premises Exchange-implementaties kunnen beperkingsbeleid configureren, en beheerders kunnen geen beperkingsbeleid configureren voor Exchange Online.

De meest voorkomende trigger voor vertraging in SharePoint Online is een CSOM-code (object model voor de client-aan de clientzijde) waarmee te veel acties met een frequentie te hoge tijd worden uitgevoerd. Met CSOM kunt u veel acties uitvoeren met een enkele aanvraag die de gebruiks limieten kan overschrijden en wat de beperking van de gebruiker kan veroorzaken.

Ongeacht de activiteit die kan leiden tot vertraging, wanneer een gebruiker de gebruikslimiet overschrijdt, vertraagt SharePoint Online eventuele verdere aanvragen van dat gebruikersaccount, meestal voor een korte periode. Hoewel een gebruikers beperking in werking is, worden alle acties van die gebruiker vertraagd totdat de vertraging verloopt, op basis van de volgende criteria:
- Voor aanvragen die door de gebruiker rechtstreeks in een browser worden uitgevoerd, wordt door SharePoint Online omgeleid naar een pagina met beperkings informatie en mislukt de verzoeken.
- Voor alle andere aanvragen, waaronder CSOM-gesprekken, retourneert SharePoint Online HTTP-statuscode 429 (' te veel aanvragen ') en worden de aanvragen mislukt.

Als het probleem zich blijft voordoen, kan SharePoint Online het proces volledig blokkeren en de HTTP-statuscode 503 (' service niet beschikbaar ').

## <a name="vulnerability-and-penetration-testing"></a>Beveiligingslek en penetratie tests
Microsoft gebruikt veel [beveiligingstechnologieën en-procedures](https://www.microsoft.com/trustcenter/security/threatmanagement) om [de Cloud infrastructuur](https://blogs.technet.microsoft.com/hybridcloud/2015/05/05/protecting-your-datacenter-and-cloud-from-emerging-threats/) en on-premises netwerken te beschermen tegen moderne, verfijnde bedreigingen, waaronder het gebruik van antimalware-onderdelen en-services voor cloudservices, virtuele machines (VMS) en andere systemen. Advanced Threat Analytics, waarmee normaal gebruikspatronen voor netwerken, systemen en gebruikers worden gecontroleerd en machine learning kan worden gebruikt om het gedrag te markeren dat niet op de normale manier wordt getest, en regelmatige penetratie tests.

Naast de mogelijkheid onze eigen penetratie tests uit te voeren en aan onze klanten een [Microsoft Cloud-programma voor centrale penetratie](https://technet.microsoft.com/mt784683)van bekrachtigen te leveren, bieden we ook ondersteuning voor beveiligings professionals van derden die regelmatig het beveiligingslek willen testen en de bepenetratie van de cloudservices. We maken de rapporten van deze beoordelingen van derden die u kunt downloaden via de [service Trust](https://aka.ms/STP) en de portals voor [service](https://aka.ms/ServiceAssurance) onderzoek.
