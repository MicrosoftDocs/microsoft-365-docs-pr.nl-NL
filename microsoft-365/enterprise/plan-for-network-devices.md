---
title: Plan voor netwerkapparaten die verbinding maken met Office 365-Services
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/29/2016
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 073433ca-3511-4db9-b173-7a2edca57691
description: 'Overzicht: hierin worden overwegingen beschreven bij de netwerkcapaciteit, WAN-accelerators en taakverdelings apparaten die worden gebruikt om verbinding te maken met Office 365.'
ms.openlocfilehash: a4ea75eb294d74004125be4d258dbe86d7d89810
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689199"
---
# <a name="plan-for-network-devices-that-connect-to-office-365-services"></a>Plan voor netwerkapparaten die verbinding maken met Office 365-Services

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*
  
Bij sommige netwerkhardware gelden er beperkingen voor het aantal gelijktijdig ondersteunde sessies. Voor organisaties die meer dan 2.000 gebruikers hebben, is het raadzaam dat ze hun netwerkapparaten volgen om ervoor te zorgen dat ze het extra service verkeer van Office 365 kunnen verwerken. U kunt dit doen met behulp van de SNMP-toezicht software (Simple Network Management Protocol).

Dit artikel maakt onderdeel uit van [netwerk planning en prestaties optimaliseren voor Office 365](https://aka.ms/tune).

On-premises uitgaande internet proxy-instellingen zijn ook van invloed op de connectiviteit met Office 365-Services voor uw clienttoepassingen. U moet ook uw netwerkproxy apparaten configureren om verbindingen voor Microsoft cloudservices-Url's en-toepassingen mogelijk te maken. Elke organisatie is verschillend. Als u een idee wilt krijgen van de manier waarop Microsoft deze procedure beheert en de bandbreedte van de hoeveelheid bandbreedte, [raadpleegt u de casestudy](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365).
  
De volgende Help-artikelen voor Skype voor bedrijven bevatten meer informatie over instellingen van Skype voor bedrijven:
  
- [Aanmeldingsproblemen met Skype voor bedrijven online oplossen voor beheerders](https://docs.microsoft.com/skypeforbusiness/set-up-skype-for-business-online/troubleshooting-sign-in-errors-for-admins)

- [U kunt geen verbinding maken met Skype voor bedrijven of bepaalde functies werken niet omdat een lokale firewall de verbinding blokkeert](https://go.microsoft.com/fwlink/p/?LinkID=243625)

> [!NOTE]
> Hoewel veel van deze instellingen specifiek zijn voor Skype voor bedrijven, zijn de algemene richtlijnen voor netwerkconfiguratie handig voor alle Office 365-Services.
  
## <a name="determining-network-capacity"></a>Netwerkcapaciteit bepalen

Elk netwerkapparaat dat zich in een verbinding bevindt, heeft de capaciteitslimiet. Op de volgende apparaten worden de netwerkhosts, routers, schakelopties en hubs van de client en server opgenomen die met elkaar zijn verbinden. Voldoende netwerkcapaciteit betekent dat geen van deze verzadigd is. Monitoring van netwerkactiviteiten is essentieel om ervoor te zorgen dat de werkelijke belastingen op alle netwerkapparaten kleiner zijn dan de maximale capaciteit. Netwerkcapaciteit is van invloed op de prestaties van het proxy apparaat.
  
In de meeste gevallen wordt met de bandbreedte van Internet verbinding de limiet voor de hoeveelheid verkeer ingesteld. De zwakke prestaties van de piekuren worden waarschijnlijk veroorzaakt door matig gebruik van de Internet link. Deze situatie is ook van toepassing op een scenario voor filiaal zaken waarbij de filialen van de filialen van de filiaalverbinding met het proxy apparaat in het hoofdkantoor van de tak liggen via een verbinding met een langzame WAN-verbinding (Wide Area Network).
  
Als u de netwerkcapaciteit wilt testen, controleert u de netwerkactiviteit op de netwerkinterface van de proxy. Als u meer dan 75 procent van de maximale bandbreedte van een netwerkinterface hebt, kunt u overwegen om de bandbreedte van de netwerkinfrastructuur te verhogen. U kunt ook geavanceerde functies gebruiken, zoals HTTP-compressie.
  
## <a name="wan-accelerators"></a>WAN-Accelerators

Als in uw organisatie omgevings toepassingen met een WAN-versnelling worden gebruikt, kunt u problemen ondervinden wanneer u toegang hebt tot de Office 365-Services. Mogelijk moet u uw netwerkapparaat of apparaten optimaliseren om ervoor te zorgen dat uw gebruikers een consistente ervaring hebben wanneer ze toegang krijgen tot Office 365. Met Office 365 services worden bijvoorbeeld enkele inhoud van Office 365 en de TCP-header versleuteld. Uw apparaat kan dit type verkeer mogelijk niet verwerken.
  
Lees onze ondersteunings instructies over het gebruik van de [WAN Optimization-controller of verkeer/inspectieapparatuur met Office 365](https://support.microsoft.com/kb/2690045).
  
## <a name="hardware-and-software-load-balancing-devices"></a>Onderverdelings apparaten voor hardware en software

Uw organisatie moet gebruikmaken van een hardware Load Balancer (HLB) of een NLB-oplossing (Network Load Balancing) voor het distribueren van aanvragen naar uw AD FS-servers (Active Directory Federation Services) en/of Exchange hybride servers. Taakverdelings apparaten regelen het netwerkverkeer naar de on-premises servers. Deze servers zijn van essentieel belang, zodat u er zeker van bent dat u de beschikbaarheid van eenmalige aanmelding en hybride implementatie van Exchange uitzorgt.
  
We bieden een software-oplossing van een NLB-oplossing ingebouwd in Windows Server. Office 365 ondersteunt deze oplossing om taken te verdelen.
  
## <a name="firewalls-and-proxies"></a>Firewalls en proxy's

Zie voor meer informatie over het configureren van firewalls en proxy's voor het configureren van verbinding met Office 365, [office 365-eindpunten beheren](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), Office [365](assessing-network-connectivity.md)-eindpunten en [Office 365-eindpunten](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d) raadplegen voor meer informatie over apparaten en Circuit selectie.
  
## <a name="see-also"></a>Zie ook

[Installatie handleidingen voor Office 365-Services](setup-guides-for-microsoft-365.md)

[Overzicht van Microsoft 365 Enterprise](microsoft-365-overview.md)
