---
title: Microsoft Managed Desktop rollen en verantwoordelijkheden
description: In dit onderwerp worden de rollen en verantwoordelijkheden beschreven die Microsoft voor Microsoft Managed Desktop heeft gegeven.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0288dfd2ee84f406c4bcdf4a604d1370afeefed7
ms.sourcegitcommit: fb3815ee186b2b3ec790ee32a9d7b1628d623b0b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/22/2019
ms.locfileid: "42806621"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Microsoft Managed Desktop rollen en verantwoordelijkheden


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

Wat doet Microsoft voor u wanneer uw organisatie is ingeschreven bij Microsoft Managed Desktop? En wat zijn de verantwoordelijkheden van uw organisatie?

## <a name="microsofts-roles-and-responsibilities"></a>De rollen en verantwoordelijkheden van Microsoft

Hieronder vindt u een paar belangrijke rollen en verantwoordelijkheden die u door Microsoft worden aangeboden.

Rol of verantwoordelijkheid | Beschrijving
--- | ---
MDM beleidsbeheer | Microsoft past MDM-beleid toe op basis van aanbevolen procedures en overweegt aanvragen voor beleidswijzigingen. We zullen ook wijzigingen aanbrengen in uw tenant zoals voorgeschreven in [apparaatbeleid.](../service-description/device-policies.md)
Ondersteuning voor eindgebruikers | Microsoft biedt ondersteuning voor eindgebruikers voor apparaten, Windows en Office-productsuite voor alle ingeschreven gebruikers via de Help-app downloaden die vooraf is geïnstalleerd op alle Microsoft Managed Desktop-apparaten. 
Ondersteuning voor Microsoft Managed Desktop-service | Microsoft biedt ondersteuning aan IT-afdelingen van klanten via een Microsoft Managed Desktop Operations Team. Dit team ondersteunt technische probleemoplossing, wijzigingsverzoeken en incidentbeheer voor de Microsoft Managed Desktop-omgeving van de klant. Zie [Beheerdersondersteuning voor Microsoft Managed Desktop voor](../working-with-managed-desktop/admin-support.md)meer informatie.
Veiligheidscontrole | Microsoft controleert de microsoft managed desktop-apparaten van klanten met Microsoft Defender ATP. Als een bedreiging wordt gedetecteerd door het Microsoft Managed Desktop Security Operations Center (SOC), zal Microsoft de klant hiervan op de hoogte stellen, het apparaat isoleren en het probleem op afstand verhelpen. Zie [Beveiliging](../service-description/security.md)voor meer informatie.
Monitoring en beheer bijwerken | Microsoft controleert actief microsoft managed desktop-apparaten van klanten om ervoor te zorgen dat de nieuwste kwaliteits- en functie-updates zijn geïnstalleerd voor Microsoft Windows en Microsoft Office. Zie [Hoe updates worden verwerkt](../service-description/updates.md)voor meer informatie.
Groeping van gebruikers en apparaten | Het Operations Team van Microsoft Managed Desktop maakt en beheert de vereiste apparaat- en gebruikersgroepen als onderdeel van IT-bewerkingen. Voor deze groepen zijn geen lidmaatschaps- of configuratiewijzigingen toegestaan. Het wijzigen van deze groepen kan leiden tot onverwachte configuratie van apparaten en verlies van functionaliteit. Voor problemen of vragen rond deze groepen nadat deze zijn vastgesteld, kunnen IT-beheerders contact opnemen met de bewerkingen van Microsoft Managed Desktop. Zie [Beheerdersondersteuning voor Microsoft Managed Desktop voor](../working-with-managed-desktop/admin-support.md)meer informatie.

## <a name="your-roles-and-responsibilities"></a>Uw rollen en verantwoordelijkheden

Hieronder vindt u een extra set gemeenschappelijke rollen en verantwoordelijkheden die niet door Microsoft worden geleverd, maar die vereist zijn voor een succesvolle implementatie. Het is niet uitputtend, maar is van toepassing voor de meeste organisaties. Er zijn een paar items onder dat zowel Microsoft en de klant aandeel verantwoordelijkheden. 

Rol of verantwoordelijkheid | Beschrijving
--- | ---
Wijzigingsbeheer | Microsoft zal klanten vooraf op de hoogte stellen wanneer er wijzigingen moeten worden aangebracht in hun Microsoft Managed Desktop-omgeving. Zie [servicewijzigingen en communicatie voor](../service-description/servicechanges.md) meer informatie<br><br>De klant is verplicht om zijn eigen change management proces te hebben en een contactpersoon te hebben opgezet met het Microsoft Managed Desktop Operations-team. De klant moet ook over resources beschikken om deze wijzigingen te bekijken en goed te keuren. Zie [Operations en monitoring](../service-description/operations-and-monitoring.md)voor meer informatie.  
Identiteitsbeheer | De klant is verantwoordelijk voor het maken van gebruikersaccounts, het toewijzen van gebruikers aan groepen en het up-to-date houden van metadata. 
Configuratie en beheer van Office 365 ProPlus | Microsoft is verantwoordelijk voor het implementeren van Office-toepassingen voor eindgebruikers en deze toepassingen worden up-to-date gehouden. <br><br> De klant is verantwoordelijk voor het beheer van Office 365-services en -beleid, inclusief de administratieverantwoordelijkheden van Exchange Online:<br>- E-mailbeheer<br>- Postvak- en regelconfiguratie<br>- Exchange on-premises management<br><br>De klant is ook verantwoordelijk voor samenwerkingstools, SharePoint-serverbeheer, domeinbeheer, beveiliging en informatiebeleid dat is ingesteld in de Office 365-beheerportal. 
Ondersteuning voor eindgebruikers | De klant is verantwoordelijk voor het bieden van ondersteuning voor eindgebruikers voor: <br>- On site infrastructuur: alle netwerk- en internetverbinding, VPN-infrastructuur en clientconfiguratie, lokale vergaderruimteapparatuur, printers, proxyserver en configuratie, firewalls.<br><br>- Cloudresources voor het hele bedrijf: e-mail, SharePoint, samenwerkingsservices en andere cloudinfrastructuur die betrekking heeft op de bedrijfsbrede technologische voetafdruk.<br><br>- Bedrijfsactiviteiten en andere bedrijfsspecifieke toepassingen.
Apps | Rollen en verantwoordelijkheden verschillen enigszins voor de apps die worden geleverd als onderdeel van Microsoft Managed Desktop ten opzichte van de apps die u verstrekt. <br><br>Voor apps van Microsoft (Office 365 ProPlus bestaande uit Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype voor Bedrijven, Teams en OneNote) biedt **Microsoft** volledige service voor de implementatie, update en ondersteuning. **U** moet licenties voor deze apps verkrijgen en toewijzen, gebruikers toevoegen aan beveiligingsgroepen en het einde van de levensduur beheren en alle Office 365-addons implementeren die u nodig hebt.<br><br>Voor apps die u aanbiedt (zoals uw line-of-business-apps), of u ze nu zelf verpakt of een niet-Microsoft-leverancier inschakelt om dit te doen, bent **u** verantwoordelijk voor deze acties: <br><br>- Identificeren van toepassingen die nodig zijn voor gerichte gebruikersgroepen<br>- Azure AD-groepen maken en beheren voor app-implementatie<br>- Verpakkingsapps om te voldoen aan de implementatienormen van Microsoft Intune<br>- Apps uploaden naar Microsoft Intune<br>- Apps testen in de Microsoft Managed Desktop-omgeving<br>- Apps testen met uw eindgebruikers<br>- Gebruikers beheren en toewijzen aan applicaties<br>- Toepassingsupdates identificeren en implementeren via Microsoft Intune<br>- Het verwijderen en verwijderen van aanvragen wanneer ze zijn gestopt<br>- Aanschaf en toewijzing van licenties<br>- Ondersteuning voor eindgebruikers voor line-of-business apps<br>- App-instellingen op afstand beheren<br><br>**Microsoft** biedt microsoft-implementatietools om de toepassingen aan externe clients te leveren.<br><br>Zie [Apps](../get-ready/apps.md) voor meer informatie
Veiligheidsbewaking en -respons | De klant is verantwoordelijk voor het onderzoeken en oplossen van incidenten voor niet-Microsoft Managed Desktop-apparaten en ervoor te zorgen dat het Microsoft Managed Desktop Operations Team op de hoogte wordt gesteld van eventuele problemen die van invloed kunnen zijn op de service.
Operations support | De klant is verantwoordelijk voor het verstrekken van een lijst van favoriete klantcontacten en vakdeskundigen. Microsoft heeft deze nodig in het geval er een niet-Microsoft Managed Desktop operationeel incident. <br><br>De klant is ook verantwoordelijk voor het onderzoeken en oplossen van incidenten voor niet-Microsoft Managed Desktop-apparaten en -services en ervoor te zorgen dat het Microsoft Managed Desktop Operations Team altijd op de hoogte is.
Netwerkinfrastructuur, inclusief VPN | De klant is verantwoordelijk voor het instellen, configureren en beheren (inclusief het oplossen van problemen en foutopsporing) van alle netwerkgerelateerde infrastructuur en services, inclusief internetconnectiviteit, netwerkbesturing, proxyconfiguratie en externe connectiviteitsinfrastructuur.<br><br>Als een proxy is geconfigureerd (in hardware of software), is er een verzameling URL's die door de proxy moeten worden toegestaan. De klant is verantwoordelijk voor het oplossen van conflicten of onverenigbaarheden als gevolg van meerdere proxy's. U netwerkproxy's toevoegen die specifiek zijn voor uw organisatie met behulp van configureerbare instellingen. Zie [Configureerbare instellingen](../working-with-managed-desktop/config-setting-ref.md#proxy)voor meer informatie.<br><br>Zie [Proxyconfiguratie](../get-ready/network.md)voor meer informatie.
Afdrukken | De klant is verantwoordelijk voor het installeren, onderhouden en beheren van printers en printwachtrijen. Cloudprinting is een aanbevolen oplossing, maar is niet vereist. 




