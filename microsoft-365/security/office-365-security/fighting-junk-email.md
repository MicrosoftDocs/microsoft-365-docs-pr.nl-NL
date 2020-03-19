---
title: Ongewenste e-mail naar Office 365 verzenden
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5fd7d05b-96db-456f-81d6-1ac0e5bff530
ms.collection:
- M365-security-compliance
description: Microsoft's e-mail veiligheid roadmap omvat een ongeëvenaarde cross-product aanpak. Exchange Online Protection (EOP) anti-spam en anti-phishing filtering technologie wordt toegepast op de e-mailplatforms van Microsoft om gebruikers te voorzien van de nieuwste anti-spam en anti-phishing tools en innovaties in het hele netwerk. Het doel van EOP is om een uitgebreide en bruikbare e-mailservice aan te bieden die gebruikers helpt detecteren en beschermen tegen ongewenste e-mail, frauduleuze e-mailbedreigingen (phishing) en malware.
ms.openlocfilehash: 888df6224007471db46b669ac4ffe33983057115
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42806299"
---
# <a name="fighting-junk-email-sent-to-office-365"></a>Ongewenste e-mail naar Office 365 verzenden

Microsoft's e-mail veiligheid roadmap omvat een ongeëvenaarde cross-product aanpak. Exchange Online Protection (EOP) anti-spam en anti-phishing filtering technologie wordt toegepast op de e-mailplatforms van Microsoft om gebruikers te voorzien van de nieuwste anti-spam en anti-phishing tools en innovaties in het hele netwerk. Het doel van EOP is om een uitgebreide en bruikbare e-mailservice aan te bieden die gebruikers helpt detecteren en beschermen tegen ongewenste e-mail, frauduleuze e-mailbedreigingen (phishing) en malware.
  
## <a name="the-challenge"></a>De uitdaging

E-mail is een belangrijk communicatiemiddel geworden, niet alleen voor consumenten, maar ook voor marketeers, ondersteunend personeel, verkooporganisaties en bedrijven van elke omvang. Naarmate het gebruik van e-mail is gegroeid, is dat ook misbruik van e-mail. Ongecontroleerde ongewenste e-mail kan inboxen en netwerken verstoppen, de tevredenheid van de gebruiker beïnvloeden en de effectiviteit van legitieme e-mailcommunicatie belemmeren. Daarom blijft Microsoft investeren in antispamtechnologieën. Simpel gezegd, het begint met het bevatten en filteren van ongewenste e-mail. 
  
## <a name="our-efforts"></a>Onze inspanningen

EOP biedt een aantal stappen om de negatieve impact van ongewenste e-mail op de e-mailervaring van onze gebruikers te minimaliseren.
  
### <a name="exchange-online-protection-technology"></a>Exchange Online Protection-technologie

Om ongewenste e-mail te helpen verminderen, bevat EOP bescherming tegen ongewenste e-mail met behulp van eigen EOP-filtertechnologieën die e-mail screenen om ongewenste e-mail te identificeren en te scheiden van legitieme e-mail. Het EOP-inhoudsfilter leert van bekende spam- en phishingbedreigingen en feedback van gebruikers van ons consumentenplatform, Outlook.com. Deze typen gegevens helpen EOP-technologieën te trainen om legitieme e-mail en ongewenste e-mail te herkennen en zijn belangrijke ingangen in de reputatie van afzenders. Voortdurende feedback van EOP-gebruikers in het classificatieprogramma voor ongewenste e-mail helpt ervoor te zorgen dat de EOP-technologieën voortdurend worden getraind en verbeterd.
  
#### <a name="how-does-eop-work"></a>Hoe werkt EOP?

Wanneer een externe gebruiker een e-mailbericht naar een EOP-gebruiker stuurt, evalueren eop-filtertechnologieën de inhoud van het bericht en wijst een beoordeling toe aan het bericht op basis van de waarschijnlijkheid dat het bericht ongewenste e-mail is. Deze beoordeling wordt opgeslagen als een berichteigenschap die een Spam Confidence Level (SCL) wordt genoemd in het bericht zelf. De SCL-beoordeling blijft bij het bericht omdat het wordt verzonden naar andere antispambeveiliginglagen binnen EOP. 
  
Regels binnen EOP zijn ingesteld om e-mailberichten te verwerken met verschillende SCL-classificaties. Als een bericht een SCL-classificatie heeft die hoger is dan een bepaalde drempelwaarde, wordt het als spam beschouwd. Het bericht wordt in quarantaine geplaatst of geleverd aan de map ongewenste e-mail van de gebruiker, afhankelijk van hoe de systeembeheerder de optie voor het bezorgen van spam configureert.
  
#### <a name="eop-filters"></a>EOP-filters

Naast de anti-spam filtertechnologieën geeft EOP de systeembeheerder ook de mogelijkheid om filterniveaus in te stellen om de levering van e-mail aan hun gebruikersaccounts verder aan te passen. Beheerders kunnen eenvoudig een afzender of domeinnaam toevoegen aan de lijst Veilige afzenders en domeinen, zodat de e-mail van die afzender of het domein nooit als ongewenste e-mail wordt behandeld, ongeacht de inhoud van het bericht. Zie Lijsten [met afzenders en geblokkeerde afzenders in Exchange Online](safe-sender-and-blocked-sender-lists-faq.md)voor informatie.
  
### <a name="phishing-protection"></a>Bescherming tegen phishing

Phishing (uitgesproken als "vissen") is een vorm van identiteitsdiefstal en een van de snelst groeiende bedreigingen op het internet. U vaak een phishingbericht identificeren wanneer het om persoonlijke of financiële informatie vraagt of een link bevat naar een website die om dergelijke informatie verzoekt. EOP biedt bescherming tegen phishing als onderdeel van de gepatenteerde EOP-filtertechnologieën. EOP-filtertechnologieën analyseren e-mail om frauduleuze links of vervalste domeinen te detecteren om gebruikers te beschermen tegen dit soort online oplichting.
  
#### <a name="how-does-phishing-protection-work"></a>Hoe werkt phishingbescherming?

Vaak wordt een phishing-e-mail verzonden met een link, zodra geklikt de link stuurt gebruikers naar een frauduleuze website die geldig lijkt (zoals uw financiële instelling of online dienst). Deze phishing-site vraagt gebruikers meestal om persoonlijke gegevens in te voeren, zoals gebruikersnamen, wachtwoorden en burgerservicenummers. Alle informatie die u invoert op de phishing-site helpt de phisher stelen van uw identiteit. Door het gebruik van bekende vertrouwde merknamen en logo's, phishers zijn in staat om legitiem lijken. Phishing filter technologie aangeboden in EOP controles voor mogelijke phishing kenmerken in e-mail. Als deze optie is gevonden, wordt de e-mail verplaatst naar de map Ongewenste e-mail.
  
Microsoft richt zijn inspanningen op anti-phishingtechnologie op twee fronten: ten eerste door te helpen voorkomen dat phishing-e-mailberichten onze gebruikers bereiken en ten tweede door te helpen de mogelijkheid te elimineren dat gebruikers worden misleid door vervalste e-mails en websites. 
  
> [!TIP]
> Internet Explorer versie 7 en hoger zal blokkeren of waarschuwen gebruikers wanneer ze bekende of potentiële phishing-sites te bezoeken, zodat ze niet worden misleid in het verstrekken van persoonlijke informatie. [Zorg ervoor dat u de nieuwste versie van Internet Explorer hebt.](https://www.microsoft.com/windows/ie/default.mspx) 
  
#### <a name="authentication"></a>Verificatie

Domein spoofing is een manier van het imiteren van een legitiem e-mailadres om frauduleuze e-mail kijken legitiem. Spoofing wordt gebruikt door kwaadwillende personen of organisaties in phishing om mensen te verleiden tot het onthullen van gevoelige persoonlijke informatie. Openbaarmaking van dergelijke informatie kan leiden tot het identificeren van diefstal en andere vormen van fraude.
  
EOP maakt gebruik van Sender Protection Framework (SPF), DomainKeys Identified Mail (DKIM) en Domain-based Message Authentication, Reporting en Conformance (DMARC) en andere impliciete verificaties om te controleren of berichten afkomstig zijn uit het domein waarvan ze beweren afkomstig te zijn . We raden alle afzenders aan SPF en DKIM te gebruiken om hun ontvangers te beschermen tegen ongewenste e-mail en phishing. We raden afzenders aan om een DMARC te publiceren om e-mail die is verzonden van onbevoegde afzenders te weigeren of in quarantaine te plaatsen.
  
- Zie [RFC 7208](https://tools.ietf.org/html/rfc7208) en [Sender Policy Framework](https://www.openspf.org/)voor meer informatie over SPF.
    
- Zie [RFC 6376](https://tools.ietf.org/html/rfc6376) en [DKIM.org](https://dkim.org/)voor meer informatie over DKIM.
    
- Zie [DMARC.org](https://dmarc.org/)voor meer informatie over DMARC.
    
### <a name="legislation"></a>Wetgeving

Bij Microsoft zijn we van mening dat de ontwikkeling van nieuwe technologieën en zelfregulering de ondersteuning vereist van effectief overheidsbeleid en juridische kaders. De wereldwijde spam proliferatie heeft aangespoord tal van wetgevende instanties om commerciële e-mail te reguleren. Veel landen / regio's hebben nu spam-bestrijding wetten op zijn plaats. De Verenigde Staten heeft zowel federale als staatswetten die spam regeren, en deze complementaire aanpak helpt om spam in te perken terwijl legitieme e-commerce kan floreren. De CAN-SPAM Act breidt de beschikbare tools voor het beteugelen van frauduleuze en misleidende e-mailberichten.
  

