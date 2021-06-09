---
title: Rollen en verantwoordelijkheden voor Microsoft Managed Desktop
description: In dit artikel worden de rollen en verantwoordelijkheden beschreven die microsoft voor Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 94389fbb9a13b9a880b0c4dcaf67d8adcaff0f98
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841313"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Rollen en verantwoordelijkheden voor Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

Wanneer uw organisatie is geregistreerd voor Microsoft Managed Desktop, wat doet Microsoft voor u? En wat zijn de verantwoordelijkheden van uw organisatie?

## <a name="microsofts-roles-and-responsibilities"></a>De rollen en verantwoordelijkheden van Microsoft

Microsoft biedt de volgende belangrijke rollen en verantwoordelijkheden:

Rol of verantwoordelijkheid | Beschrijving
--- | ---
MDM-beleidsbeleid | Microsoft past MDM-beleid toe op basis van best practices en overweegt verzoeken om beleidswijzigingen. We brengen ook wijzigingen aan in uw tenant, zoals is voorgeschreven in [apparaatbeleid.](../service-description/device-policies.md)
gebruikersondersteuning | We bieden gebruikersondersteuning voor apparaten, Windows en de Microsoft 365-apps voor ondernemingen-productsuite voor alle geregistreerde gebruikers via de Hulp vragen-app die vooraf is geïnstalleerd op alle Microsoft Managed Desktop-apparaten. 
Microsoft Managed Desktop serviceondersteuning | Microsoft biedt ondersteuning aan uw IT-afdeling via een Microsoft Managed Desktop Operations Team. Dit team ondersteunt technische probleemoplossing, wijzigingsaanvragen en incidentbeheer voor de Microsoft Managed Desktop klant. Zie Ondersteuning voor beheerders [voor](../working-with-managed-desktop/admin-support.md)Microsoft Managed Desktop.
Beveiligingscontrole | Microsoft controleert uw Microsoft Managed Desktop apparaten met Microsoft Defender voor Eindpunt. Als de Microsoft Managed Desktop Security Operations Center (SOC) een bedreiging detecteert, zullen we u op de hoogte stellen, het apparaat isoleren en het probleem op afstand verhelpen. Zie Beveiliging voor [meer informatie.](../service-description/security.md)
Controle en beheer bijwerken | We controleren uw apparaten Microsoft Managed Desktop om ervoor te zorgen dat de meest recente kwaliteits- en functieupdates worden geïnstalleerd voor Microsoft Windows en Microsoft Office. Zie Hoe updates worden verwerkt voor [meer informatie.](../service-description/updates.md)
Groeperen van gebruikers en apparaten | Microsoft Managed Desktop operations team maakt en beheert vereiste apparaat- en gebruikersgroepen als onderdeel van IT-bewerkingen. Er zijn geen lidmaatschaps- of configuratiewijzigingen toegestaan voor deze groepen. Als u deze groepen wijzigt, kan dit leiden tot onverwachte configuratie van apparaten en verlies van functionaliteit. Voor eventuele problemen of vragen rond deze groepen die eenmaal zijn vastgesteld, kunnen IT-beheerders contact opnemen met Microsoft Managed Desktop bewerkingen. Zie Ondersteuning voor beheerders [voor](../working-with-managed-desktop/admin-support.md)Microsoft Managed Desktop.

## <a name="your-roles-and-responsibilities"></a>Uw rollen en verantwoordelijkheden

Deze set algemene rollen en verantwoordelijkheden is vereist voor implementatie, maar wordt niet geleverd door Microsoft. Het is niet volledig, maar is van toepassing voor de meeste organisaties. Er zijn een paar items waar u en Microsoft verantwoordelijkheid voor delen. 

Rol of verantwoordelijkheid | Beschrijving
--- | ---
Beheer wijzigen | Microsoft informeert klanten van tevoren wanneer wijzigingen moeten worden aangebracht in hun Microsoft Managed Desktop omgeving. Zie servicewijzigingen en [communicatie voor meer informatie.](../service-description/servicechanges.md)<br><br>U moet uw eigen proces voor wijzigingsbeheer hebben en een contact hebben met Microsoft Managed Desktop Operations-team. U moet ook over resources beschikken om deze wijzigingen te controleren en goed te keuren. Zie Operations and monitoring (Bewerkingen en [monitoring) voor meer informatie.](../service-description/operations-and-monitoring.md)  
Identiteitsbeheer | U bent verantwoordelijk voor het maken van gebruikersaccounts, het toewijzen van gebruikers aan groepen en het up-to-date houden van metagegevens. 
Microsoft 365-apps voor ondernemingen configuratie en beheer | Microsoft is verantwoordelijk voor het Office toepassingen worden geïmplementeerd voor gebruikers en deze toepassingen worden up-to-date gehouden. <br><br> U bent verantwoordelijk voor het beheer Microsoft 365 services en beleidsregels, Exchange Online verantwoordelijkheden voor beheer:<br>- E-mailbeheer<br>- Configuratie van postvak en regel<br>- Exchange on-premises beheer<br><br>U bent ook verantwoordelijk voor samenwerkingshulpmiddelen, SharePoint serverbeheer, domeinbeheer en beveiligings- en informatiebeleid dat is ingesteld in het Microsoft 365 beheercentrum. 
Ondersteuning voor gebruikers | U moet gebruikersondersteuning bieden voor: <br>- On-site infrastructuur: alle netwerk- en internetverbinding, VPN-infrastructuur en clientconfiguratie, lokale apparatuur voor vergaderruimten, printers, proxyserver en -configuratie en firewalls.<br><br>- Cloudbronnen voor het hele bedrijf: e-mail, SharePoint, samenwerkingsservices en andere cloudinfrastructuur die betrekking heeft op de bedrijfsbrede technologievoetafdruk.<br><br>- Bedrijfslijn en andere bedrijfsspecifieke toepassingen.
Apps | Rollen en verantwoordelijkheden verschillen enigszins voor de apps die worden geleverd als onderdeel van Microsoft Managed Desktop ten opzichte van de apps die u verstrekt. <br><br>Voor apps van Microsoft (Microsoft 365-apps voor ondernemingen bestaande uit Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype voor Bedrijven, Teams en OneNote), biedt **Microsoft** volledige service voor de implementatie, update en ondersteuning. **U** moet licenties voor deze apps verkrijgen en toewijzen, gebruikers toevoegen aan beveiligingsgroepen, het einde van de levensduur beheren en eventuele invoegtoepassingen implementeren die u nodig hebt.<br><br>Voor apps die u oplevert (zoals uw line-of-business-apps), ongeacht of u deze zelf inpakt of een niet-Microsoft-leverancier in de hand **werkt,** bent u verantwoordelijk voor deze acties: <br><br>- Toepassingen identificeren die nodig zijn voor gerichte gebruikersgroepen<br>- Azure AD-groepen maken en beheren voor app-implementatie<br>- Apps verpakken om te voldoen aan Microsoft Intune implementatiestandaarden<br>- Apps uploaden naar Microsoft Intune<br>- Apps testen in Microsoft Managed Desktop omgeving<br>- Apps testen met uw gebruikers<br>- Gebruikers beheren en toewijzen aan toepassingen<br>- Toepassingsupdates identificeren en implementeren via Microsoft Intune<br>- Toepassingen verwijderen en verwijderen wanneer ze zijn verwijderd<br>- Licenties aanschaffen en toewijzen<br>- Gebruikersondersteuning bieden voor line-of-business-apps<br>- App-instellingen op afstand beheren<br><br>**Microsoft** levert Microsoft Intune implementatiehulpprogramma's voor het leveren van de toepassingen aan externe clients.<br><br>Zie Apps voor meer [informatie.](../get-ready/apps.md)
Beveiligingscontrole en -antwoord | U bent verantwoordelijk voor het onderzoeken en oplossen van incidenten voor apparaten die niet Microsoft Managed Desktop apparaten zijn en ervoor te zorgen dat het Microsoft Managed Desktop Operations Team op de hoogte is van eventuele problemen die van invloed kunnen zijn op de service.
Ondersteuning voor Bewerkingen | U moet een lijst met voorkeurscontactcontacten en deskundigen op het gebied van onderwerp in uw organisatie verstrekken. We hebben deze contactpersonen nodig als er een operationeel incident is dat niet gerelateerd is aan Microsoft Managed Desktop. <br><br>U bent ook verantwoordelijk voor het onderzoeken en oplossen van incidenten voor apparaten en services die niet in Microsoft Managed Desktop staan en ervoor te zorgen dat het Microsoft Managed Desktop Operations Team altijd op de hoogte is.
Netwerkinfrastructuur, inclusief VPN | U bent verantwoordelijk voor het instellen, configureren en beheren (inclusief probleemoplossing en foutopsporing) van alle netwerkinfrastructuur en -services, waaronder internetverbinding, netwerkbesturingselementen, proxyconfiguratie en externe connectiviteitsinfrastructuur.<br><br>Als een proxy is geconfigureerd (in hardware of software), is er een verzameling URL's die moeten worden toegestaan door de proxy. U bent verantwoordelijk voor het oplossen van conflicten of incompatibiliteiten als gevolg van meerdere proxies. U kunt netwerkproxies toevoegen die specifiek zijn voor uw organisatie met configureerbare instellingen. Zie Configureerbare instellingen [voor meer informatie.](../working-with-managed-desktop/config-setting-ref.md#proxy)<br><br>Zie Proxyconfiguratie voor meer [informatie.](../get-ready/network.md)
Afdrukken | U bent verantwoordelijk voor het installeren, onderhouden en beheren van printers en het afdrukken van wachtrijen. Afdrukken in de cloud is een aanbevolen oplossing, maar is niet vereist. 




