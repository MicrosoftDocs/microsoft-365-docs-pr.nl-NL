---
title: Hoe Exchange Online TLS gebruikt om e-mailverbindingen te beveiligen
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/2/2018
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4cde0cda-3430-4dc0-b489-f2c0736c929f
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: Lees hoe Exchange Online en Microsoft 365 Transport Layer Security (TLS) en Forward Geheimhouding (FS) gebruiken om e-mailcommunicatie te beveiligen. U kunt ook informatie krijgen over het certificaat dat is uitgegeven door Microsoft voor Exchange Online.
ms.openlocfilehash: cc7ca631f9322fdc8a85cfaba197e63d06d08aee
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161872"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections"></a>Hoe Exchange Online TLS gebruikt om e-mailverbindingen te beveiligen

Lees hoe Exchange Online en Microsoft 365 Transport Layer Security (TLS) en Forward Geheimhouding (FS) gebruiken om e-mailcommunicatie te beveiligen. Geeft ook informatie over het certificaat dat is uitgegeven door Microsoft voor Exchange Online.
  
## <a name="tls-basics-for-microsoft-365-and-exchange-online"></a>TLS-basisprincipes voor Microsoft 365 en Exchange Online

Transport Layer Security (TLS) en SSL die vóór TLS zijn gebruikt, zijn cryptografische protocollen die communicatie via een netwerk beveiligen met behulp van beveiligingscertificaten om een verbinding tussen computers te versleutelen. TLS komt in plaats van Secure Sockets Layer (SSL) en wordt vaak SSL 3.1 genoemd. Voor Exchange Online gebruiken we TLS om de verbindingen tussen onze Exchange-servers en de verbindingen tussen onze Exchange-servers en andere servers te versleutelen, zoals uw on-premises Exchange-servers of de e-mailservers van uw geadresseerden. Wanneer de verbinding is versleuteld, worden alle gegevens die via die verbinding worden verzonden via het versleutelde kanaal verzonden. Als u echter een bericht doorsturen dat is verzonden via een TLS-versleutelde verbinding, is dat bericht niet per se versleuteld. Dit komt omdat TLS in eenvoudige termen het bericht niet versleutelt, alleen de verbinding.
  
Als u het bericht wilt versleutelen, moet u een versleutelingstechnologie gebruiken die de inhoud van het bericht versleutelt, bijvoorbeeld iets Office Berichtversleuteling. Zie [E-mailversleuteling in Office 365](email-encryption.md) en Office 365-berichtversleuteling [(OME)](ome.md) voor informatie over opties voor berichtversleuteling in Office 365. 
  
We raden u aan TLS te gebruiken in situaties waarin u een beveiligd communicatiekanaal wilt instellen tussen Microsoft en uw on-premises organisatie of een andere organisatie, zoals een partner. Exchange Online probeert altijd eerst TLS te gebruiken om uw e-mail te beveiligen, maar dit kan niet altijd als de andere partij geen TLS-beveiliging biedt. Lees verder om te zien hoe u alle e-mail kunt beveiligen op uw on-premises servers of belangrijke partners met behulp van *connectors.* 

Om onze klanten de beste versleuteling te bieden, heeft Microsoft de TLS-versies 1.0 en 1.1 [in](tls-1.0-and-1.1-deprecation-for-office-365.md) Office 365 en [Office 365 GCC](tls-1-2-in-office-365-gcc.md). U kunt echter wel een niet-versleutelde SMTP-verbinding zonder TLS blijven gebruiken. Het is niet raadzaam om e-mail te verzenden zonder versleuteling.  
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a>Hoe Exchange Online TLS gebruikt tussen Exchange Online klanten

Exchange Online servers versleutelen altijd verbindingen met andere Exchange Online servers in onze datacenters met TLS 1.2. Wanneer u e-mail verzendt naar een geadresseerde binnen uw organisatie, wordt die e-mail automatisch verzonden via een verbinding die wordt versleuteld met TLS. Alle e-mail die u naar andere klanten verzendt, wordt ook verzonden via verbindingen die zijn versleuteld met TLS en die zijn beveiligd met Forward Geheimhouding.
  
## <a name="how-microsoft-365-uses-tls-between-microsoft-365-and-external-trusted-partners"></a>Hoe Microsoft 365 TLS gebruikt tussen Microsoft 365 en externe, vertrouwde partners

Standaard wordt Exchange Online altijd gebruikgemaakt van een opportunistische TLS. Dit betekent dat Exchange Online altijd eerst verbindingen met de veiligste versie van TLS probeert te versleutelen en vervolgens de lijst met TLS-cijfers omlaag werkt totdat er een wordt gevonden waarover beide partijen het eens kunnen worden. Tenzij u Exchange Online hebt geconfigureerd om ervoor te zorgen dat berichten naar die geadresseerde alleen via beveiligde verbindingen worden verzonden, wordt het bericht standaard niet-versleuteld verzonden als de geadresseerde geen ondersteuning biedt voor TLS-versleuteling. Een opportunistische TLS is voldoende voor de meeste bedrijven. Voor bedrijven met nalevingsvereisten, zoals medische, bank- of overheidsorganisaties, kunt u echter Exchange Online TLS vereisen of dwingen. Zie E-mailstroom [configureren met behulp van verbindingslijnen in](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)Office 365.
  
Als u besluit om TLS te configureren tussen uw organisatie en een vertrouwde partnerorganisatie, kunnen Exchange Online gedwongen TLS gebruiken om vertrouwde communicatiekanalen te maken. Voor gedwongen TLS moet uw partnerorganisatie zich verifiëren Exchange Online met een beveiligingscertificaat om e-mail naar u te verzenden. Uw partner moet hiervoor hun eigen certificaten beheren. In Exchange Online gebruiken we verbindingslijnen om berichten te beveiligen die u vanuit niet-geautoriseerde toegang verzendt voordat ze bij de e-mailprovider van de geadresseerde aankomen. Zie E-mailstroom configureren met behulp van verbindingslijnen in Office 365 voor informatie over het gebruik van verbindingslijnen voor het [configureren van e-mailstroom.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a>TLS- en hybride Exchange Server implementaties

Als u een hybride Exchange-implementatie beheert, moet uw on-premises Exchange-server zich verifiëren bij Microsoft 365 met behulp van een beveiligingscertificaat om e-mail te verzenden naar geadresseerden van wie de postvakken alleen in Office 365. Hierdoor moet u uw eigen beveiligingscertificaten beheren voor uw on-premises Exchange servers. U moet deze servercertificaten ook veilig opslaan en onderhouden. Zie Certificaatvereisten voor hybride implementaties voor meer informatie over het beheren van certificaten in hybride [implementaties.](/exchange/certificate-requirements)
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a>Gedwongen TLS instellen voor Exchange Online in Office 365

Voor Exchange Online klanten moet u meer dan één verbindingslijn instellen die TLS vereist om te kunnen werken om al uw verzonden en ontvangen e-mail te beveiligen. U hebt één connector nodig voor e-mail die naar uw gebruikerspostvakken wordt verzonden en een andere connector voor e-mail die vanuit uw gebruikerspostvakken wordt verzonden. Maak deze verbindingslijnen in het Exchange-beheercentrum in Office 365. Zie E-mailstroom [configureren met behulp van verbindingslijnen in](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)Office 365.
  
## <a name="tls-certificate-information-for-exchange-online"></a>TLS-certificaatgegevens voor Exchange Online

De certificaatgegevens die door Exchange Online worden gebruikt, worden in de volgende tabel beschreven. Als uw zakenpartner gedwongen TLS in de e-mailserver instelt, moet u deze informatie aan hen verstrekken. Let op: om veiligheidsredenen veranderen onze certificaten van tijd tot tijd. We hebben een update voor ons certificaat in onze datacenters uitgerold. Het nieuwe certificaat is geldig vanaf 3 september 2018.
  
 **Huidige certificaatgegevens geldig vanaf 3 september 2018**
  
| Attribuut | Waarde |
|:-----|:-----|
|Hoofduitgever van certificeringsinstantie  <br/> |GlobalSign Root CA – R1 <br/> |
|Certificaatnaam  <br/> |mail.protection.outlook.com  <br/> |
|Organisatie  <br/> |Microsoft Corporation  <br/> |
|Organisatie-eenheid  <br/> |  <br/> |
|Sterkte certificaatcode  <br/> |2048  <br/> |
   
 **Afgeschafte certificaatgegevens geldig tot 3 september 2018**
  
Om ervoor te zorgen dat de overgang soepel verloopt, blijven we de oude certificaatgegevens voor uw verwijzing enige tijd verstrekken, maar vanaf nu moet u de huidige certificaatgegevens gebruiken.
  
****

| Attribuut | Waarde |
|:-----|:-----|
|Hoofduitgever van certificeringsinstantie  <br/> |Baltimore CyberTrust Root  <br/> |
|Certificaatnaam  <br/> |mail.protection.outlook.com  <br/> |
|Organisatie  <br/> |Microsoft Corporation  <br/> |
|Organisatie-eenheid  <br/> |Microsoft Corporation  <br/> |
|Sterkte certificaatcode  <br/> |2048  <br/> |
   
## <a name="prepare-for-the-new-exchange-online-certificate"></a>Voorbereiden op het nieuwe Exchange Online certificaat

Het nieuwe certificaat wordt uitgegeven door een andere certificeringsinstantie (CA) dan het vorige certificaat dat door de Exchange Online. Hierdoor moet u mogelijk enkele acties uitvoeren om het nieuwe certificaat te kunnen gebruiken.

Voor het nieuwe certificaat is verbinding nodig met de eindpunten van de nieuwe ca als onderdeel van het valideren van het certificaat. Als u dit niet doet, kan dit leiden tot negatieve gevolgen voor de e-mailstroom. Als u uw e-mailservers beschermt met firewalls die alleen de e-mailservers verbinding laten maken met bepaalde bestemmingen, moet u controleren of uw server het nieuwe certificaat kan valideren. Als u wilt bevestigen dat uw server het nieuwe certificaat kan gebruiken, gaat u als volgende stappen te werk:

1. Verbinding maken naar uw lokale Exchange Server met Windows PowerShell en voer vervolgens de volgende opdracht uit:  
  `certutil -URL https://crl.globalsign.com/gsorganizationvalsha2g3.crl`

1. Kies ophalen in het venster dat wordt **weergegeven.**

1. Wanneer het hulpprogramma de controle voltooit, wordt een status als retourneert. Als de status **OK wordt weergegeven,** kan uw e-mailserver het nieuwe certificaat valideren. Zo niet, dan moet u bepalen wat de oorzaak is van het mislukken van de verbindingen. Waarschijnlijk moet u de instellingen van een firewall bijwerken. De volledige lijst met eindpunten die moeten worden gebruikt, bevat:
    - ocsp.globalsign.com
    - crl.globalsign.com
    - secure.globalsign.com   

Normaal gesproken ontvangt u automatisch updates voor uw hoofdcertificaten via Windows Update. Sommige implementaties hebben echter extra beveiliging, waardoor deze updates niet automatisch kunnen worden geïmplementeerd. In deze vergrendelde implementaties waarbij Windows Update niet automatisch hoofdcertificaten kan bijwerken, moet u ervoor zorgen dat het juiste hoofd-CA-certificaat is geïnstalleerd door de volgende stappen uit te voeren:
1.  Verbinding maken naar uw lokale Exchange Server met Windows PowerShell en voer vervolgens de volgende opdracht uit:  
  `certmgr.msc`

2. Controleer **onder Vertrouwde hoofdcertificeringsinstantie/certificaten** of het nieuwe certificaat wordt vermeld.

## <a name="get-more-information-about-tls-and-microsoft-365"></a>Meer informatie over TLS en Microsoft 365

Zie Technische naslaginformatie over versleuteling voor een lijst met ondersteunde [cijfersuites.](technical-reference-details-about-encryption.md)
  
[Connectors instellen voor een veilige e-mailstroom met een partnerorganisatie](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)
  
[Connectors met verbeterde e-mailbeveiliging](/previous-versions/exchange-server/exchange-150/dn942516(v=exchg.150))
  
[Versleuteling in Microsoft 365](encryption.md)
