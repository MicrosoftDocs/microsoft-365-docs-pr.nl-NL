---
title: Plannen voor netwerkapparaten die verbinding maken met Office 365-services
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
description: 'Samenvatting: Beschrijft aandachtspunten voor netwerkcapaciteit, WAN-accelerators en apparaten voor het uitbalanceren van laden die worden gebruikt om verbinding te maken met Office 365.'
ms.openlocfilehash: e1209c13eb24d11a2cc9692957bc4ee5f6310f41
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927498"
---
# <a name="plan-for-network-devices-that-connect-to-office-365-services"></a>Plannen voor netwerkapparaten die verbinding maken met Office 365-services

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*
  
Sommige netwerkhardware kan beperkingen hebben voor het aantal gelijktijdige sessies dat wordt ondersteund. Voor organisaties met meer dan 2.000 gebruikers is het raadzaam hun netwerkapparaten te controleren om ervoor te zorgen dat ze het extra Office 365-serviceverkeer kunnen verwerken. SNMP-monitoringsoftware (Simple Network Management Protocol) kan u daarbij helpen.

Dit artikel maakt deel uit van [netwerkplanning en prestatieafstemming voor Office 365.](./network-planning-and-performance.md)

On-premises instellingen voor uitgaande internetproxy zijn ook van invloed op de connectiviteit met Office 365-services voor uw clienttoepassingen. U moet ook uw netwerkproxyapparaten configureren om verbindingen voor URL's en toepassingen van Microsoft-cloudservices toe te staan. Elke organisatie is anders. Lees de case [study](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)om een idee te krijgen van hoe Microsoft dit proces beheert en hoeveel bandbreedte we inrichten.
  
De volgende Help-artikelen voor Skype voor Bedrijven bevatten meer informatie over skype voor Bedrijven-instellingen:
  
- [Aanmeldingsfouten in Skype voor Bedrijven Online oplossen voor beheerders](/skypeforbusiness/set-up-skype-for-business-online/troubleshooting-sign-in-errors-for-admins)

- [U kunt geen verbinding maken met Skype voor Bedrijven of bepaalde functies werken niet, omdat een on-premises firewall de verbinding blokkeert](https://go.microsoft.com/fwlink/p/?LinkID=243625)

> [!NOTE]
> Hoewel veel van deze instellingen specifiek zijn voor Skype voor Bedrijven, is de algemene richtlijn voor netwerkconfiguratie handig voor alle Office 365-services.
  
## <a name="determining-network-capacity"></a>Netwerkcapaciteit bepalen

Elk netwerkapparaat dat op een verbinding aanwezig is, heeft een capaciteitslimiet. Deze apparaten omvatten de client- en servernetwerkadapters, routers, schakelopties en hubs die deze met elkaar verbinden. Voldoende netwerkcapaciteit betekent dat geen van deze netwerken is verzadigd. Het bewaken van netwerkactiviteit is essentieel om ervoor te zorgen dat de werkelijke belasting op alle netwerkapparaten kleiner is dan de maximale capaciteit. Netwerkcapaciteit is van invloed op de prestaties van proxyapparaat.
  
In de meeste situaties stelt de bandbreedte voor internetverbinding de limiet in voor de hoeveelheid verkeer. Zwakke prestaties tijdens piekuren worden waarschijnlijk veroorzaakt door overmatig gebruik van de internetkoppeling. Deze situatie is ook van toepassing op een branch office-scenario, waarbij proxyservercomputers van branch office zijn verbonden met het proxyapparaat op het hoofdkantoor van de vestiging via een trage WAN-koppeling (Wide Area Network).
  
Als u de netwerkcapaciteit wilt testen, controleert u de netwerkactiviteit op de proxynetwerkinterface. Als het meer dan 75 procent van de maximale bandbreedte van een netwerkinterface is, kunt u overwegen om de bandbreedte van de netwerkinfrastructuur te verhogen die onvoldoende is. U kunt ook geavanceerde functies gebruiken, zoals HTTP-compressie.
  
## <a name="wan-accelerators"></a>WAN-accelerators

Als uw organisatie proxyapparaten voor wanversnelling (Wide Area Network) gebruikt, kunnen er problemen zijn wanneer u toegang hebt tot de Office 365-services. Mogelijk moet u uw netwerkapparaat of -apparaten optimaliseren om ervoor te zorgen dat uw gebruikers een consistente ervaring hebben bij het openen van Office 365. Office 365-services versleutelen bijvoorbeeld bepaalde Office 365-inhoud en de TCP-koptekst. Het is mogelijk dat uw apparaat dit soort verkeer niet kan verwerken.
  
Lees onze ondersteuningsverklaring over [het gebruik van WAN Optimization Controller of Verkeers-/inspectieapparaten met Office 365.](https://support.microsoft.com/kb/2690045)
  
## <a name="hardware-and-software-load-balancing-devices"></a>Apparaten voor het laden van hardware en software

Uw organisatie moet een hardware load balancer (HLB) of een NLB-oplossing (Network Load Balancing) gebruiken om aanvragen te distribueren naar uw AD FS-servers (Active Directory Federation Services) en/of uw hybride Exchange-servers. Load-balancing-apparaten beheren het netwerkverkeer naar de on-premises servers. Deze servers zijn van cruciaal belang om ervoor te zorgen dat er één aanmeldings- en exchange-hybride implementatie beschikbaar is.
  
We bieden een softwaregebaseerde NLB-oplossing die is ingebouwd in Windows Server. Office 365 ondersteunt deze oplossing om belastingverdeling te bereiken.
  
## <a name="firewalls-and-proxies"></a>Firewalls en proxies

Voor meer informatie over het configureren van firewalls en proxies om verbinding te maken met Office 365, leest u Veelgestelde vragen over Het beheren van [Office 365-eindpunten,](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)het beoordelen van [office 365-netwerkconnectiviteit](assessing-network-connectivity.md)en veelgestelde vragen over [Office 365-eindpunten](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d) voor meer informatie over apparaten en circuitselectie.
  
## <a name="see-also"></a>Zie ook

[Installatiehandleidingen voor Office 365-services](setup-guides-for-microsoft-365.md)

[Overzicht van Microsoft 365 Enterprise](microsoft-365-overview.md)