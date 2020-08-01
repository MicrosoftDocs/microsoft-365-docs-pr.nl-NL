---
title: Rollen en verantwoordelijkheden voor Microsoft Managed Desktop
description: In dit onderwerp worden de rollen en verantwoordelijkheden beschreven die microsoft voor Microsoft Managed Desktop biedt.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 85e352ec657da435e435311b2ad48beb6a0487ee
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529993"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Rollen en verantwoordelijkheden voor Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

Wat doet Microsoft voor u als uw organisatie is ingeschreven in Microsoft Managed Desktop? En wat zijn de verantwoordelijkheden van uw organisatie?

## <a name="microsofts-roles-and-responsibilities"></a>De rollen en verantwoordelijkheden van Microsoft

Hieronder vindt u een paar belangrijke rollen en verantwoordelijkheden die door Microsoft aan u worden verstrekt.

Rol of verantwoordelijkheid | Beschrijving
--- | ---
MDM-beleidsmanagement | Microsoft past MDM-beleid toe op basis van aanbevolen procedures en houdt rekening met verzoeken om beleidswijzigingen. We zullen ook wijzigingen aanbrengen in uw tenant zoals voorgeschreven in [apparaatbeleid.](../service-description/device-policies.md)
Ondersteuning voor eindgebruikers | Microsoft biedt ondersteuning voor eindgebruikers voor apparaten, Windows en Office-productsuite voor alle ingeschreven gebruikers via de Help-app Get die vooraf is geïnstalleerd op alle Microsoft Managed Desktop-apparaten. 
Ondersteuning voor Microsoft Managed Desktop-services | Microsoft biedt ondersteuning aan IT-afdelingen van klanten via een Microsoft Managed Desktop Operations Team. Dit team ondersteunt technische probleemoplossing, wijzigingsaanvragen en incidentbeheer voor de Microsoft Managed Desktop-omgeving van de klant. Zie [Beheerdersondersteuning voor Microsoft Managed Desktop voor](../working-with-managed-desktop/admin-support.md)meer informatie.
Veiligheidsbewaking | Microsoft controleert klant Microsoft Managed Desktop-apparaten met Microsoft Defender ATP. Als het Microsoft Managed Desktop Security Operations Center (SOC) een bedreiging gedetecteerd, zal Microsoft de klant hiervan op de hoogte stellen, het apparaat isoleren en het probleem op afstand verhelpen. Zie [Beveiliging voor](../service-description/security.md)meer informatie.
Monitoring en beheer bijwerken | Microsoft controleert actief microsoft Managed Desktop-apparaten van klanten om ervoor te zorgen dat de nieuwste kwaliteits- en functie-updates zijn geïnstalleerd voor Microsoft Windows en Microsoft Office. Zie [Hoe updates worden verwerkt](../service-description/updates.md)voor meer informatie.
Groepering van gebruikers en apparaten | Het Microsoft Managed Desktop-bedrijfsteam maakt en beheert vereiste apparaat- en gebruikersgroepen als onderdeel van IT-bewerkingen. Deze groepen zijn niet toegestaan om lid- of configuratiewijzigingen aan te brengen. Het wijzigen van deze groepen kan leiden tot onverwachte configuratie van apparaten en verlies van functionaliteit. Voor problemen of vragen rond deze groepen, zodra deze zijn ingesteld, kunnen IT-beheerders contact opnemen met Microsoft Managed Desktop-bewerkingen. Zie [Beheerdersondersteuning voor Microsoft Managed Desktop voor](../working-with-managed-desktop/admin-support.md)meer informatie.

## <a name="your-roles-and-responsibilities"></a>Jouw rollen en verantwoordelijkheden

Hieronder vindt u een extra reeks algemene rollen en verantwoordelijkheden die niet door Microsoft worden geleverd, maar die vereist zijn voor een succesvolle implementatie. Het is niet uitputtend, maar is van toepassing voor de meeste organisaties. Er zijn een paar items hieronder dat zowel Microsoft en de klant verantwoordelijkheden delen. 

Rol of verantwoordelijkheid | Beschrijving
--- | ---
Wijzigingsbeheer | Microsoft zal klanten van tevoren op de hoogte stellen wanneer er wijzigingen moeten worden aangebracht in hun Microsoft Managed Desktop-omgeving. Zie [servicewijzigingen en communicatie](../service-description/servicechanges.md) voor meer informatie<br><br>De klant moet een eigen wijzigingsbeheerproces hebben en contact opnemen met het Microsoft Managed Desktop Operations-team. De klant moet ook over middelen beschikken om deze wijzigingen te controleren en goed te keuren. Zie [Operations en monitoring voor](../service-description/operations-and-monitoring.md)meer informatie.  
Identiteitsbeheer | De klant is verantwoordelijk voor het maken van gebruikersaccounts, het toewijzen van gebruikers aan groepen en het up-to-date houden van metadata. 
Microsoft 365-apps voor bedrijfsconfiguratie en -beheer | Microsoft is verantwoordelijk voor de implementatie van Office-toepassingen voor eindgebruikers en deze toepassingen worden up-to-date gehouden. <br><br> De klant is verantwoordelijk voor het beheer van Microsoft 365-services en -beleidsregels, inclusief de beheerverantwoordelijkheden van Exchange Online:<br>- E-mailadministratie<br>- Postvak en regelconfiguratie<br>- On-premises beheer van exchange<br><br>De klant is ook verantwoordelijk voor samenwerkingstools, SharePoint-serverbeheer, domeinbeheer, beveiligings- en informatiebeleid dat is ingesteld in het Microsoft 365-beheercentrum. 
Ondersteuning voor eindgebruikers | De klant is verantwoordelijk voor het bieden van ondersteuning voor eindgebruikers voor: <br>- On site infrastructuur: alle netwerk- en internetverbinding, VPN-infrastructuur en clientconfiguratie, lokale vergaderruimteapparatuur, printers, proxyserver en configuratie, firewalls.<br><br>- Cloudresources voor het hele bedrijf: e-mail, SharePoint, samenwerkingsservices en andere cloudinfrastructuur die betrekking heeft op de bedrijfsbrede technologieafdruk.<br><br>- Bedrijfsactiviteiten en andere bedrijfsspecifieke toepassingen.
Apps | Rollen en verantwoordelijkheden variëren enigszins voor de apps die worden geleverd als onderdeel van Microsoft Managed Desktop ten opzichte van de apps die u verstrekt. <br><br>Voor apps die worden geleverd door Microsoft (Microsoft 365 Apps for Enterprise, bestaande uit Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype voor Bedrijven, Teams en OneNote), biedt **Microsoft** volledige service voor de implementatie, update en ondersteuning. **U** moet licenties voor deze apps verkrijgen en toewijzen, gebruikers toevoegen aan beveiligingsgroepen en het einde van de levensduur beheren en eventuele add-ons implementeren die u nodig hebt.<br><br>Voor apps die u aans verstrekt (zoals uw branchegerichte apps), of u ze nu zelf verpakt of een niet-Microsoft-leverancier inschakelt om dit te doen, bent **u** verantwoordelijk voor deze acties: <br><br>- Identificeren van toepassingen die nodig zijn voor gerichte gebruikersgroepen<br>- Azure AD-groepen maken en beheren voor app-implementatie<br>- Verpakkings-apps om te voldoen aan de implementatienormen van Microsoft Intune<br>- Apps uploaden naar Microsoft Intune<br>- Apps testen in de Microsoft Managed Desktop-omgeving<br>- Apps testen met uw eindgebruikers<br>- Gebruikers beheren en toewijzen aan toepassingen<br>- Toepassingsupdates identificeren en implementeren via Microsoft Intune<br>- Het verwijderen en verwijderen van toepassingen wanneer ze zijn buiten gebruik gesteld<br>- Aanschaf en toewijzing van licenties<br>- Ondersteuning van eindgebruikers bieden voor line-of-business apps<br>- App-instellingen op afstand beheren<br><br>**Microsoft** biedt microsoft Intune-implementatietools om de toepassingen aan externe clients te leveren.<br><br>Zie [Apps voor](../get-ready/apps.md) meer informatie
Beveiligingscontrole en -antwoord | De klant is verantwoordelijk voor het onderzoeken en oplossen van incidenten voor niet-Microsoft Managed Desktop-apparaten en ervoor te zorgen dat het Microsoft Managed Desktop Operations Team op de hoogte wordt gesteld van eventuele problemen die van invloed kunnen zijn op de service.
Ondersteuning voor operaties | De klant is verantwoordelijk voor het verstrekken van een lijst van favoriete klantcontacten en vakexperts. Microsoft heeft deze nodig voor het geval er een operationeel incident is dat niet van Microsoft Managed Desktop is. <br><br>De klant is ook verantwoordelijk voor het onderzoeken en oplossen van incidenten voor niet-Microsoft Managed Desktop-apparaten en -services en ervoor te zorgen dat het Microsoft Managed Desktop Operations Team altijd op de hoogte is.
Netwerkinfrastructuur, inclusief VPN | De klant is verantwoordelijk voor het instellen, configureren en beheren (inclusief probleemoplossing en foutopsporing) van alle netwerkgerelateerde infrastructuur en services, waaronder internetconnectiviteit, netwerkbesturingselementen, proxyconfiguratie en infrastructuur voor externe connectiviteit.<br><br>Als een proxy is geconfigureerd (in hardware of software), is er een verzameling URL's die door de proxy moeten worden toegestaan. De klant is verantwoordelijk voor het oplossen van eventuele conflicten of onverenigbaarheden als gevolg van meerdere volmachten. U netwerkproxy's toevoegen die specifiek zijn voor uw organisatie met behulp van configureerbare instellingen. Zie [Configureerbare instellingen](../working-with-managed-desktop/config-setting-ref.md#proxy)voor meer informatie.<br><br>Zie [Proxyconfiguratie](../get-ready/network.md)voor meer informatie.
Afdrukken | De klant is verantwoordelijk voor het installeren, onderhouden en beheren van printers en printwachtrijen. Afdrukken in de cloud is een aanbevolen oplossing, maar is niet vereist. 




