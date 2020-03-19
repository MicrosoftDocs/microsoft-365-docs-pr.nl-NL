---
title: Walkthrough spoof intelligentie inzicht
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 7/30/2018
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Bekijk hoe het nieuwe inzicht in spoofintelligentie werkt.
ms.openlocfilehash: 940203bc86339e4cc749565be355d717be9e914d
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42809169"
---
# <a name="walkthrough-spoof-intelligence-insight"></a>Walkthrough: spoof intelligentie inzicht

Door het inzicht in spoofintelligentie te gebruiken, u snel bepalen welke afzenders u legitieme e-mail verzenden. Door hen toe te staan vervalste berichten te verzenden, u het risico verminderen dat er valse positieven naar uw gebruikers gaan.
  
Daarnaast u ook de Spoof Intelligence-monitor gebruiken en toegestane domeinparen beheren om een extra beveiligingslaag te bieden en te voorkomen dat onveilige berichten in uw organisatie binnenkomen.
  
U het inzicht in &amp; de spoofinformatie gebruiken in het Security Compliance Center als uw werk- of schoolaccount office 365 algemene beheerders-, beveiligingsbeheerder- of beveiligingslezermachtigingen heeft gekregen. Zie [Machtigingen in het Office 365 &amp; Security Compliance Center](permissions-in-the-security-and-compliance-center.md)voor meer informatie.
  
Als u nieuw bent [in rapporten en inzichten &amp; in het Office 365 Security Compliance Center,](reports-and-insights-in-security-and-compliance.md)u mogelijk zien hoe u eenvoudig navigeren van een dashboard naar een inzicht en aanbevolen acties.
  
U het inzicht in spoofinformatie bekijken &amp; vanuit meer dan één dashboard in het Security Compliance Center. Ongeacht naar welk dashboard u nu kijkt, het inzicht biedt dezelfde details en stelt u in staat om snel dezelfde taken uit te voeren.
  
Dit is een van de vele &amp; walkthroughs voor het Security Compliance Center. Zie de walkthroughs in de sectie Gerelateerde onderwerpen voor het navigeren door rapporten en inzichten.
  
## <a name="getting-to-the-spoof-intelligence-insight-in-the-security-amp-compliance-center"></a>Het inzicht in spoof-informatie &amp; in het Security Compliance Center

1. Om te beginnen moet u [naar &amp; het Security Compliance Center gaan.](../../compliance/go-to-the-securitycompliance-center.md)
    
2. Ga in &amp; het Security Compliance Center naar **Threat Management** \> **Dashboard.**
    
3. Zoek in de rij **Insights** naar het inzicht in spoofintelligentie. Als u spoofinformatie hebt ingeschakeld, heeft het inzicht de titel **Vervalste domeinen die de verificatie van de afgelopen 30 dagen hebben mislukt.** Als u spoofbeveiliging niet hebt ingeschakeld, wordt u door het inzicht gevraagd dit te doen met de titel **Spoofbeveiliging inschakelen.** 
    
## <a name="about-the-insight-on-the-dashboard"></a>Over het inzicht op het dashboard

Het inzicht op het dashboard toont u informatie als deze.
  
![Schermafbeelding van inzicht in spoofintelligentie](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)
  
Dit inzicht heeft twee modi:
  
 **Insight-modus**. Als je een spoofbeleid hebt ingeschakeld, laat het inzicht zien hoeveel e-mails de afgelopen 30 dagen zijn beïnvloed door onze spoofintelligentiemogelijkheden. 
  
 **Wat als modus**. Als u geen spoofbeleid hebt ingeschakeld, toont het inzicht u hoeveel e-mails de afgelopen 30 dagen *zouden* zijn beïnvloed door onze spoofintelligentiemogelijkheden. 
  
Hoe dan ook, de vervalste domeinen die in het inzicht worden weergegeven, zijn onderverdeeld in twee categorieën; verdachte domeinparen en niet-verdachte domeinparen. Deze categorieën zijn verder onderverdeeld in drie verschillende buckets voor u om te beoordelen. 
  
Een *domeinpaar* is een combinatie van het adres 'Van:' en de verzendinfrastructuur. 
  
- Het adres 'Van' is het adres dat wordt weergegeven als het Van-adres van uw e-mailtoepassing. Dit adres identificeert de auteur van de e-mail. Dat wil zeggen, de mailbox van de persoon of het systeem die verantwoordelijk is voor het schrijven van het bericht. Dit wordt ook wel de 5322.From adres.
    
- De verzendende infrastructuur of afzender is het organisatiedomein van de PTR-record van het verzendende IP-adres. Als het verzendende IP-adres geen PTR-record heeft, wordt de afzender geïdentificeerd door het verzendende IP met het subnetmasker 255.255.0 in CIDR-notatie (/24). Als het IP-adres bijvoorbeeld 192.168.100.100 is, is het volledige IP-adres van de afzender 192.168.100.100/24.
    
 **Verdachte domeinparen** zijn: 
  
- **Met veel vertrouwen spoof**. Office 365 heeft sterke signalen ontvangen dat deze domeinen verdacht zijn, gebaseerd op de historische verzendpatronen en de reputatiescore van de domeinen. Office 365 heeft er alle vertrouwen in dat de domeinen worden vervalst en dat berichten die vanuit deze domeinen worden verzonden, minder waarschijnlijk legitiem zijn. 
    
- **Matig vertrouwen spoof**. Office 365 heeft matige signalen ontvangen dat deze domeinen verdacht zijn, gebaseerd op historische verzendpatronen en de reputatiescore van de domeinen. Office 365 heeft er matig van overtuigd dat de domeinen worden vervalst en dat berichten die vanuit deze domeinen worden verzonden legitiem zijn. Deze emmer heeft een grotere kans op het bevatten van valse positieven (FPs) dan de hoog-vertrouwen spoof emmer. 
    
 **Niet-verdachte domeinparen** bevatten **geredde spoof.** Gered spoof zijn domeinen die hebben gefaald de expliciete verificatie controles ( [SPF](https://docs.microsoft.com/office365/SecurityCompliance/how-office-365-uses-spf-to-prevent-spoofing), [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email), [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)), maar geslaagd voor onze uitgebreide verificatie controles. Als gevolg hiervan heeft Office 365 de e-mail namens u gered en is er geen anti-spoofing actie ondernomen op de e-mail. 
  
## <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>Bekijk gedetailleerde informatie over verdachte domeinparen vanuit het spoof-inzicht in intelligentie

1. Klik op het inzicht in de spoofintelligentie op een van de domeinparen (hoog, matig of gered).
  
Op de pagina **Spoofintelligence Insight** wordt een lijst weergegeven met afzenders die niet-geverifieerde e-mail naar uw organisatie verzenden. De informatie op deze pagina helpt u te bepalen of vervalste berichten zijn geautoriseerd of niet of dat u verdere actie moet ondernemen. U de informatie sorteren op aantal berichten, de datum waarop de spoof voor het laatst is gedetecteerd en meer. (Klik bijvoorbeeld op kolomkoppen, zoals **aantal berichten** of **Laatst gezien.)** 
    
2. Selecteer een item in de tabel om een detailvenster te openen met uitgebreide informatie over het domeinpaar, waaronder waarom we dit hebben opgevangen, wat u moet doen, een domeinoverzicht, WhoIs-gegevens over de afzender en vergelijkbare e-mails die we in uw tenant van dezelfde afzender hebben gezien. Vanaf hier u er ook voor kiezen om het domeinpaar toe te voegen of te verwijderen uit de lijst met veilige afzenders **allowedTospoof.** 
  
![Schermafbeelding van een domein in het detailvenster informatie over spoofintelligentie](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)
  
## <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a>Een domein toevoegen aan of verwijderen uit de lijst met veilige afzenders allowedTospoof

U voegt een domein toe of verwijdert deze uit de lijst met veilige afzenders van AllowedToSpoof terwijl u het domeinpaar bekijkt in het detailvenster van het inzicht in spoofintelligentie. Stel de schakelaar dienovereenkomstig in.
  
Dit wijzigt de unieke combinatie van het domeinpaar van het vervalste domein en de verzendende infrastructuur en biedt geen dekking voor het gehele vervalste domein of de verzendende infrastructuur in isolatie. Als u bijvoorbeeld het volgende domeinpaar toevoegt aan de lijst 'AllowedToSpoof'-afzender: *Spoofed Domain* "gmail.com" en *Infrastructure* "tms *.mx.com",* dan mag alleen e-mail van dat domeinpaar spoofen. Andere afzenders die proberen "gmail.com" te spoofen, en andere domeinen die "tms.mx.com" proberen te spoofen, blijven worden beschermd door spoofinformatie. 
  
## <a name="related-topics"></a>Verwante onderwerpen

[Meer informatie over spoofinformatie](learn-about-spoof-intelligence.md)
  
[Anti-spoofing beveiliging in Office 365](anti-spoofing-protection.md)
  
[Walkthrough - Van een dashboard naar een inzicht](from-a-dashboard-to-an-insight.md)
  
[Walkthrough - Van een gedetailleerd rapport naar een inzicht](from-a-detailed-report-to-an-insight.md)
  
[Walkthrough - Van inzicht tot een gedetailleerd rapport](from-an-insight-to-a-detailed-report.md)
  

