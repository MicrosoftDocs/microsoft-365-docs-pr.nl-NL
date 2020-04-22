---
title: Rollen en verantwoordelijkheden van Microsoft Managed Desktop
description: In dit onderwerp worden de rollen en verantwoordelijkheden beschreven die Microsoft voor Microsoft Managed Desktop biedt.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 02a0b11a1a210367d76e73c75ac5c1fc7a66f94f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636206"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Rollen en verantwoordelijkheden van Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

Wat doet Microsoft voor u wanneer uw organisatie is ingeschreven voor Microsoft Managed Desktop? En wat zijn de verantwoordelijkheden van uw organisatie?

## <a name="microsofts-roles-and-responsibilities"></a>De rollen en verantwoordelijkheden van Microsoft

Hieronder vindt u een aantal belangrijke rollen en verantwoordelijkheden die door Microsoft aan u worden verstrekt.

Rol of verantwoordelijkheid | Beschrijving
--- | ---
MDM beleidsmanagement | Microsoft past MDM-beleid toe op basis van aanbevolen procedures en overweegt verzoeken om beleidswijzigingen. We zullen ook wijzigingen aanbrengen in uw tenant zoals voorgeschreven in [apparaatbeleid.](../service-description/device-policies.md)
Ondersteuning voor eindgebruikers | Microsoft biedt ondersteuning voor eindgebruikers voor apparaten, Windows en Office-productsuite voor alle ingeschreven gebruikers via de Help-app Downloaden die vooraf is geïnstalleerd op alle Microsoft Managed Desktop-apparaten. 
Ondersteuning voor Microsoft Managed Desktop-service | Microsoft biedt ondersteuning aan IT-afdelingen van klanten via een Microsoft Managed Desktop Operations Team. Dit team ondersteunt technische probleemoplossing, wijzigingsaanvragen en incidentbeheer voor de Microsoft Managed Desktop-omgeving van de klant. Zie [Beheerdersondersteuning voor Microsoft Managed Desktop voor](../working-with-managed-desktop/admin-support.md)meer informatie.
Veiligheidsbewaking | Microsoft controleert microsoft Managed Desktop-apparaten van de klant met Behulp van Microsoft Defender ATP. Als een bedreiging wordt gedetecteerd door het Microsoft Managed Desktop Security Operations Center (SOC), zal Microsoft de klant hiervan op de hoogte stellen, het apparaat isoleren en het probleem op afstand verhelpen. Zie [Beveiliging voor](../service-description/security.md)meer informatie.
Monitoring en beheer bijwerken | Microsoft zal microsoft Managed Desktop-apparaten van klanten actief controleren om ervoor te zorgen dat de nieuwste kwaliteits- en functie-updates zijn geïnstalleerd voor Microsoft Windows en Microsoft Office. Zie [Hoe updates worden verwerkt](../service-description/updates.md)voor meer informatie .
Groepering van gebruiker en apparaat | Het operations team van Microsoft Managed Desktop maakt en beheert vereiste apparaat- en gebruikersgroepen als onderdeel van IT-bewerkingen. Er zijn geen lidmaatschaps- of configuratiewijzigingen toegestaan voor deze groepen. Het wijzigen van deze groepen kan leiden tot onverwachte configuratie van apparaten en verlies van functionaliteit. Voor problemen of vragen rond deze groepen die eenmaal zijn vastgesteld, kunnen IT-beheerders contact opnemen met Microsoft Managed Desktop-bewerkingen. Zie [Beheerdersondersteuning voor Microsoft Managed Desktop voor](../working-with-managed-desktop/admin-support.md)meer informatie.

## <a name="your-roles-and-responsibilities"></a>Uw rollen en verantwoordelijkheden

Hieronder vindt u een extra set algemene rollen en verantwoordelijkheden die niet door Microsoft worden geleverd, maar die nodig zijn voor een succesvolle implementatie. Het is niet uitputtend, maar is van toepassing voor de meeste organisaties. Er zijn een paar items hieronder dat zowel Microsoft en de klant delen verantwoordelijkheden. 

Rol of verantwoordelijkheid | Beschrijving
--- | ---
Wijzigingsbeheer | Microsoft zal klanten van tevoren op de hoogte stellen wanneer er wijzigingen moeten worden aangebracht in hun Microsoft Managed Desktop-omgeving. Zie [servicewijzigingen en communicatie](../service-description/servicechanges.md) voor meer informatie<br><br>De klant is verplicht om zijn eigen change management proces te hebben en een contactpersoon te laten opstellen met het Microsoft Managed Desktop Operations-team. De klant moet ook over resources beschikken om deze wijzigingen te bekijken en goed te keuren. Zie [Operations en monitoring](../service-description/operations-and-monitoring.md)voor meer informatie.  
Identiteitsbeheer | De klant is verantwoordelijk voor het maken van gebruikersaccounts, het toewijzen van gebruikers aan groepen en het up-to-date houden van metadata. 
Microsoft 365 Apps voor bedrijfsconfiguratie en -beheer | Microsoft is verantwoordelijk voor het waarborgen dat Office-toepassingen worden geïmplementeerd voor eindgebruikers en deze toepassingen up-to-date worden gehouden. <br><br> De klant is verantwoordelijk voor het beheer van Microsoft 365-services en -beleid, inclusief de beheerverantwoordelijkheden van Exchange Online:<br>- E-mailbeheer<br>- Postvak- en regelconfiguratie<br>- Exchange on-premises management<br><br>De klant is ook verantwoordelijk voor samenwerkingstools, SharePoint-serverbeheer, domeinbeheer, beveiligings- en informatiebeleid dat is ingesteld in het Microsoft 365-beheercentrum. 
Ondersteuning voor eindgebruikers | De klant is verantwoordelijk voor het verlenen van ondersteuning door de eindgebruiker voor: <br>- On site infrastructuur: alle netwerk- en internetconnectiviteit, VPN-infrastructuur en clientconfiguratie, lokale conferentieruimteapparatuur, printers, proxyserver en configuratie, firewalls.<br><br>- Bedrijfsbrede cloudresources: e-mail, SharePoint, samenwerkingsservices en andere cloudinfrastructuur die betrekking heeft op de bedrijfsbrede technologische voetafdruk.<br><br>- Branche en andere bedrijfsspecifieke toepassingen.
Apps | Rollen en verantwoordelijkheden variëren enigszins voor de apps die worden geleverd als onderdeel van Microsoft Managed Desktop ten opzichte van de apps die u verstrekt. <br><br>Voor apps die door Microsoft worden geleverd (Microsoft 365 Apps for Enterprise, bestaande uit Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype voor Bedrijven, Teams en OneNote), biedt **Microsoft** volledige service voor de implementatie, update en ondersteuning. **U** moet licenties voor deze apps verkrijgen en toewijzen, gebruikers toevoegen aan beveiligingsgroepen en het einde van de levensduur beheren en eventuele invoegtoepassingen implementeren die u nodig hebt.<br><br>Voor apps die u opgeeft (zoals uw zakelijke apps), of u ze nu zelf verpakt of een niet-Microsoft-leverancier inschakelt om dit te doen, bent **u** verantwoordelijk voor deze acties: <br><br>- Het identificeren van toepassingen die nodig zijn voor gerichte gebruikersgroepen<br>- Azure AD-groepen maken en beheren voor app-implementatie<br>- Verpakkings-apps om te voldoen aan de implementatiestandaarden van Microsoft Intune<br>- Apps uploaden naar Microsoft Intune<br>- Apps testen in de Microsoft Managed Desktop-omgeving<br>- Apps testen met uw eindgebruikers<br>- Gebruikers beheren en toewijzen aan toepassingen<br>- Toepassingsupdates identificeren en implementeren via Microsoft Intune<br>- Het verwijderen en verwijderen van applicaties wanneer ze zijn uitgeschakeld<br>- Het verkrijgen en toewijzen van licenties<br>- Ondersteuning van eindgebruikers voor line-of-business apps<br>- App-instellingen op afstand beheren<br><br>**Microsoft** biedt Microsoft Intune-implementatietools om de toepassingen aan externe clients te leveren.<br><br>Zie [Apps voor](../get-ready/apps.md) meer informatie
Beveiligingsmonitoring en -respons | De klant is verantwoordelijk voor het onderzoeken en oplossen van incidenten voor niet-Microsoft Managed Desktop-apparaten en ervoor te zorgen dat het Microsoft Managed Desktop Operations Team op de hoogte is van eventuele problemen die van invloed kunnen zijn op de service.
Ondersteuning voor bewerkingen | De klant is verantwoordelijk voor het verstrekken van een lijst van voorkeursklantcontacten en vakdeskundigen. Microsoft heeft deze nodig in het geval er een niet-Microsoft Managed Desktop operationeel incident. <br><br>De klant is ook verantwoordelijk voor het onderzoeken en oplossen van incidenten voor niet-Microsoft Managed Desktop-apparaten en -services en ervoor te zorgen dat het Microsoft Managed Desktop Operations Team altijd op de hoogte is.
Netwerkinfrastructuur, inclusief VPN | De klant is verantwoordelijk voor het instellen, configureren en beheren (inclusief het oplossen van problemen en foutopsporing) van alle netwerkgerelateerde infrastructuur en services, waaronder internetconnectiviteit, netwerkbesturing, proxyconfiguratie en externe connectiviteitsinfrastructuur.<br><br>Als een proxy is geconfigureerd (in hardware of software), is er een verzameling URL's die door de proxy moet worden toegestaan. De klant is verantwoordelijk voor het oplossen van conflicten of onverenigbaarheden als gevolg van meerdere proxy's. U netwerkproxy's toevoegen die specifiek zijn voor uw organisatie met behulp van configureerbare instellingen. Zie [Configureerbare instellingen](../working-with-managed-desktop/config-setting-ref.md#proxy)voor meer informatie.<br><br>Zie [Proxyconfiguratie](../get-ready/network.md)voor meer informatie.
Afdrukken | De klant is verantwoordelijk voor het installeren, onderhouden en beheren van printers en het afdrukken van wachtrijen. Cloudprinten is een aanbevolen oplossing, maar is niet vereist. 




