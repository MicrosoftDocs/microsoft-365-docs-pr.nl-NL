---
title: Rollen en verantwoordelijkheden voor Microsoft Managed Desktop
description: In dit onderwerp worden de rollen en verantwoordelijkheden beschreven die worden verstrekt door Microsoft voor Microsoft beheerde bureaublad.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8cec5a99d2275e451ceac9004a922820e4b3e726
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289743"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Rollen en verantwoordelijkheden voor Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

Wat doet Microsoft voor u wanneer uw organisatie is ingeschreven voor Microsoft Managed Desktop? En wat zijn de verantwoordelijkheden van uw organisatie?

## <a name="microsofts-roles-and-responsibilities"></a>Rollen en verantwoordelijkheden van Microsoft

Hieronder vindt u een paar belangrijke rollen en verantwoordelijkheden die door Microsoft worden verstrekt.

Rol of verantwoordelijkheid | Beschrijving
--- | ---
MDM-beleidsbeheer | Microsoft zal MDM-beleid toepassen op basis van aanbevolen procedures en verzoeken om beleidswijzigingen. We brengen u ook wijzigingen in uw Tenant aan, zoals beschreven in de [beleidsregels van apparaten](../service-description/device-policies.md).
gebruikers ondersteuning | Microsoft zal de gebruikers ondersteuning bieden voor apparaten, Windows en Office-productsuite voor alle geregistreerde gebruikers via de Help-app die vooraf is geïnstalleerd op alle door Microsoft beheerde bureaublad apparaten. 
Ondersteuning voor Microsoft beheerde bureaublad service | Microsoft biedt ondersteuning voor IT-afdelingen van klanten via een Microsoft-beheerd bureaublad operationeel team. Dit team biedt ondersteuning voor technische probleemoplossing, wijzigingsaanvragen en incidentenbeheer voor de Microsoft beheerde bureaubladomgeving van de klant. Zie voor meer informatie [beheerders ondersteuning voor Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).
Beveiligings monitoring | Microsoft beheert klant Microsoft Managed Desktop devices met Microsoft Defender ATP. Als een bedreiging wordt gedetecteerd door het Microsoft Managed Desktop Security Operations Center (SOC), waarschuwt Microsoft de klant, isoleert u het apparaat en corrigeert u het probleem op afstand. Zie [beveiliging](../service-description/security.md)voor meer informatie.
Controle en beheer bijwerken | Microsoft beheert de door Microsoft beheerde bureaublad apparaten van klanten om ervoor te zorgen dat de nieuwste updates voor kwaliteit en functies zijn geïnstalleerd voor Microsoft Windows en Microsoft Office. Zie [hoe updates worden afgehandeld](../service-description/updates.md)voor meer informatie.
Groeperen van gebruiker en apparaat | Het Microsoft beheerde bureaublad bewerkingen team maakt en beheert het vereiste apparaat en de gebruikersgroepen als onderdeel van de activiteiten. Deze groepen kunnen geen lidmaatschaps-of configuratiewijzigingen hebben. Het wijzigen van deze groepen kan leiden tot onverwachte configuratie van apparaten en verlies van functionaliteit. Voor eventuele problemen of vragen rond deze groepen, kunnen IT-beheerders contact opnemen met Microsoft beheerde bureaublad activiteiten. Zie voor meer informatie [beheerders ondersteuning voor Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).

## <a name="your-roles-and-responsibilities"></a>Uw rollen en verantwoordelijkheden

Hieronder ziet u een extra set veelgebruikte rollen en verantwoordelijkheden die niet door Microsoft worden geleverd, maar die zijn vereist voor een succesvolle implementatie. Dit is niet volledig, maar is van toepassing op de meeste organisaties. Hieronder ziet u een paar items en de verantwoordelijkheden van klanten delen. 

Rol of verantwoordelijkheid | Beschrijving
--- | ---
Wijzigingsbeheer | Microsoft zal klanten vooraf informeren wanneer wijzigingen aan hun Microsoft-beheerde bureaubladomgeving moeten worden aangebracht. Zie voor meer informatie [Servicewijzigingen en communicatie](../service-description/servicechanges.md)<br><br>De klant moet een eigen proces voor wijzigingsbeheer hebben en een contactpersoon met het Microsoft beheerde bureaublad bewerkings team hebben opgesteld. De klant moet ook resources hebben om deze wijzigingen te controleren en goed te keuren. Zie [bewerkingen en controle](../service-description/operations-and-monitoring.md)voor meer informatie.  
Identiteitsbeheer | De klant is verantwoordelijk voor het maken van gebruikersaccounts, het toewijzen van gebruikers aan groepen en het up-to-date houden van de metagegevens. 
Microsoft 365-apps voor de configuratie en het beheer van de onderneming | Microsoft is verantwoordelijk voor de naleving van Office-toepassingen bij gebruikers en die toepassingen up-to-date blijven. <br><br> De klant is verantwoordelijk voor het beheren van Microsoft 365-Services en-beleid, waaronder beheerverantwoordelijkheden van Exchange Online:<br>-E-mail beheer<br>-Postvak en regelconfiguratie<br>-On-premises beheer van Exchange<br><br>De klant is ook verantwoordelijk voor samenwerkingsprogramma's, SharePoint Serverbeheer, domeinbeheer, beveiligings-en informatiebeleid die zijn ingesteld in het Microsoft 365-Beheercentrum. 
Gebruikers ondersteuning | De klant is verantwoordelijk voor het verlenen van de gebruikers ondersteuning voor: <br>-Op site infrastructuur: alle netwerk-en internetverbindingen, VPN-infrastructuur en clientconfiguratie, lokale apparatuur voor conferentieruimten, printers, proxyserver en configuratie, firewalls.<br><br>-Bronnen voor het hele bedrijf: e-mail, SharePoint, Collaboration Services en andere infrastructuur van de infrastructuur van de organisatie.<br><br>-Line of telebusiness en andere specifieke toepassingen van het bedrijf.
Cloud | Rollen en verantwoordelijkheden variëren enigszins voor de apps die deel uitmaken van de door Microsoft beheerde bureaubladversie en de functies die u opgeeft. <br><br>Voor apps die worden geleverd door Microsoft (Microsoft 365-apps voor ondernemingen met een Word-, Excel-, PowerPoint-, PowerPoint-, Publisher-, Access-, Skype voor bedrijven, teams en OneNote) kan **Microsoft** volledige service bieden voor de implementatie, update en ondersteuning. **U** moet licenties aanvragen en toewijzen voor deze apps, gebruikers toevoegen aan beveiligingsgroepen en het einde van de levensduur beheren en eventueel benodigde invoegtoepassingen implementeren.<br><br>Voor apps die u levert (zoals uw line-of-Business-Apps), ongeacht of u deze zelf oppakt of een niet-Microsoft-leverancier bent, bent **u** verantwoordelijk voor de volgende acties: <br><br>Het identificeren van toepassingen die nodig zijn voor gerichte gebruikersgroepen<br>Het maken en beheren van Azure AD-groepen voor app-implementatie<br>-Apps inpakken om aan Microsoft intune-implementatie standaarden te voldoen<br>-Apps uploaden naar Microsoft intune<br>-Apps testen in Microsoft beheerde bureaubladomgeving<br>-Apps testen met uw gebruikers<br>-Gebruikers beheren en toewijzen aan toepassingen<br>-Toepassingsupdates identificeren en implementeren via Microsoft intune<br>-Toepassingen verwijderen en verwijderen wanneer deze buiten gebruik worden gesteld<br>-Indrukken en licenties toewijzen<br>-Gebruikers ondersteuning bieden voor line-of-Business-Apps<br>Apps-instellingen extern beheren<br><br>**Microsoft** beschikt over implementatiehulpprogramma's voor Microsoft intune waarmee de toepassingen voor externe clients worden geleverd.<br><br>Voor meer informatie raadpleegt u [apps](../get-ready/apps.md)
Beveiligingscontrole en -antwoord | De klant is verantwoordelijk voor het onderzoek en het oplossen van problemen met niet-Microsoft beheerde bureaublad apparaten en ervoor zorgt dat het Microsoft beheerde bureaublad operationeel team op de hoogte is van problemen die van invloed kunnen zijn op de service.
Ondersteuning voor bewerkingen | De klant is verantwoordelijk voor de levering van een lijst met Voorkeursklanten van klanten en technici. Microsoft heeft deze nodig voor het geval er een niet-Microsoft-beheerd bureaublad operationeel incident is. <br><br>De klant is ook verantwoordelijk voor onderzoek en oplossing voor het oplossen van problemen met niet-Microsoft beheerde bureaublad apparaten en-services, en ervoor zorgen dat het Microsoft beheerde bureaublad operationeel team altijd op de hoogte wordt gesteld.
Netwerkinfrastructuur, waaronder VPN | De klant is verantwoordelijk voor het instellen, configureren en beheren van problemen en het oplossen van problemen met de netwerkinfrastructuur en-services, waaronder internetverbindingen, netwerkbesturing, proxyconfiguratie en Remote Connectivity-infrastructuur.<br><br>Als een proxy is geconfigureerd (in hardware of software), is er een verzameling Url's die door de proxy moeten worden toegestaan. De klant is verantwoordelijk voor het oplossen van eventuele conflicten of compatibiliteitsproblemen door meerdere proxy's. U kunt netwerkproxy's toevoegen die specifiek zijn voor uw organisatie met behulp van configureerbare instellingen. Zie [configureerbare instellingen](../working-with-managed-desktop/config-setting-ref.md#proxy)voor meer informatie.<br><br>Zie [Proxy Configuration (Proxy Configuration](../get-ready/network.md)) voor meer informatie.
Afdrukken | De klant is verantwoordelijk voor het installeren, beheren en beheren van printers en afdrukwachtrijen. Het afdrukken van een Cloud is een aanbevolen oplossing, maar dit is niet vereist. 




