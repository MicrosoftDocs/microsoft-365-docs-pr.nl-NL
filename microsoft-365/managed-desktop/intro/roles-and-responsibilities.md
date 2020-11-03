---
title: Rollen en verantwoordelijkheden voor Microsoft Managed Desktop
description: In dit artikel worden de rollen en verantwoordelijkheden beschreven die worden geleverd door Microsoft voor Microsoft beheerde bureaublad.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: de0bc092c35c7f48c562da8d4218f7a638abe1d5
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847778"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Rollen en verantwoordelijkheden voor Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

Wat doet Microsoft voor u wanneer uw organisatie is ingeschreven voor Microsoft Managed Desktop? En wat zijn de verantwoordelijkheden van uw organisatie?

## <a name="microsofts-roles-and-responsibilities"></a>Rollen en verantwoordelijkheden van Microsoft

Microsoft biedt deze belangrijkste rollen en verantwoordelijkheden:

Rol of verantwoordelijkheid | Beschrijving
--- | ---
MDM-beleidsbeheer | Microsoft zal MDM-beleid toepassen op basis van aanbevolen procedures en verzoeken om beleidswijzigingen. We brengen u ook wijzigingen in uw Tenant aan, zoals aangegeven in het [beleid voor apparaten](../service-description/device-policies.md).
gebruikers ondersteuning | We bieden gebruikers ondersteuning voor apparaten, Windows en de Microsoft 365-apps voor Enterprise productsuite voor alle geregistreerde gebruikers via de Help-app die vooraf is geïnstalleerd op alle door Microsoft beheerde bureaublad apparaten. 
Ondersteuning voor Microsoft beheerde bureaublad service | Microsoft zal de IT-afdeling ondersteunen via een Microsoft-beheerd bureaublad operationeel team. Dit team biedt ondersteuning voor technische probleemoplossing, wijzigingsaanvragen en incidentenbeheer voor de Microsoft beheerde bureaubladomgeving van de klant. Zie voor meer informatie [beheerders ondersteuning voor Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).
Beveiligings monitoring | Microsoft beheert uw door Microsoft beheerde bureaublad apparaten met behulp van Microsoft Defender voor eindpunt. Als het Microsoft-Beheercentrum voor Microsoft-beveiliging een bedreiging detecteert, meldt u het apparaat en verstuurt u dit probleem op afstand. Zie [beveiliging](../service-description/security.md)voor meer informatie.
Controle en beheer bijwerken | We monitoren uw door Microsoft beheerde bureaublad apparaten actief en garanderen dat de nieuwste updates voor kwaliteit en onderdelen voor Microsoft Windows en Microsoft Office zijn geïnstalleerd. Zie [hoe updates worden afgehandeld](../service-description/updates.md)voor meer informatie.
Groeperen van gebruiker en apparaat | Het Microsoft beheerde bureaublad bewerkingen team maakt en beheert het vereiste apparaat en de gebruikersgroepen als onderdeel van de activiteiten. Deze groepen kunnen geen lidmaatschaps-of configuratiewijzigingen hebben. Het wijzigen van deze groepen kan leiden tot onverwachte configuratie van apparaten en verlies van functionaliteit. Voor eventuele problemen of vragen rond deze groepen, kunnen IT-beheerders contact opnemen met Microsoft beheerde bureaublad activiteiten. Zie voor meer informatie [beheerders ondersteuning voor Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).

## <a name="your-roles-and-responsibilities"></a>Uw rollen en verantwoordelijkheden

Deze extra set gemeenschappelijke rollen en verantwoordelijkheden is vereist voor implementatie, maar wordt niet door Microsoft geleverd. Dit is niet volledig, maar is van toepassing op de meeste organisaties. Er zijn een paar items waarvoor u en Microsoft delen verantwoordelijk zijn. 

Rol of verantwoordelijkheid | Beschrijving
--- | ---
Wijzigingsbeheer | Microsoft zal klanten vooraf informeren wanneer wijzigingen aan hun Microsoft-beheerde bureaubladomgeving moeten worden aangebracht. Zie voor meer informatie [Servicewijzigingen en communicatie](../service-description/servicechanges.md).<br><br>U moet uw eigen proces voor het beheren van wijzigingen hebben en een contactpersoon tot stand gebracht met het bewerkings team van Microsoft beheerde bureaublad activiteiten. U moet ook resources hebben om deze wijzigingen te controleren en goed te keuren. Zie [bewerkingen en controle](../service-description/operations-and-monitoring.md)voor meer informatie.  
Identiteitsbeheer | U bent verantwoordelijk voor het maken van gebruikersaccounts, het toewijzen van gebruikers aan groepen en het up-to-date houden van de metagegevens. 
Microsoft 365-apps voor de configuratie en het beheer van de onderneming | Microsoft is verantwoordelijk voor de naleving van Office-toepassingen bij gebruikers en die toepassingen up-to-date blijven. <br><br> U bent verantwoordelijk voor het beheren van Microsoft 365-Services en-beleid, waaronder beheerders van Exchange Online:<br>-E-mail beheer<br>-Postvak en regelconfiguratie<br>-On-premises beheer van Exchange<br><br>U bent ook verantwoordelijk voor samenwerkingsprogramma's, SharePoint Serverbeheer, domeinbeheer en beveiligings-en informatiebeleid die zijn ingesteld in het Microsoft 365-Beheercentrum. 
Ondersteuning voor gebruikers | U dient de gebruikers ondersteuning te bieden voor: <br>-On-site infrastructuur: alle netwerk-en internetverbindingen, VPN-infrastructuur en clientconfiguratie, lokale apparatuur voor vergaderruimten, printers, proxyserver en firewall.<br><br>-Bronnen voor het hele bedrijf: e-mail, SharePoint, Collaboration Services en andere infrastructuur van de infrastructuur van de organisatie.<br><br>-Line of Business en andere bedrijfsspecifieke toepassingen.
Cloud | Rollen en verantwoordelijkheden variëren enigszins voor de apps die deel uitmaken van de beheerde bureaubladversie van Microsoft, versus de apps die u opgeeft. <br><br>Voor apps die worden geleverd door Microsoft (Microsoft 365-apps voor ondernemingen met een Word-, Excel-, PowerPoint-, PowerPoint-, Publisher-, Access-, Skype voor bedrijven, teams en OneNote) kan **Microsoft** volledige service bieden voor de implementatie, update en ondersteuning. **U** moet licenties aanvragen en toewijzen voor deze apps, gebruikers toevoegen aan beveiligingsgroepen, en de levensduur beheren en eventueel benodigde invoegtoepassingen implementeren.<br><br>Voor apps die u levert (zoals uw line-of-Business-Apps), ongeacht of u deze zelf oppakt of een niet-Microsoft-leverancier bent, bent **u** verantwoordelijk voor de volgende acties: <br><br>Het identificeren van toepassingen die nodig zijn voor gerichte gebruikersgroepen<br>Het maken en beheren van Azure AD-groepen voor app-implementatie<br>-Apps inpakken om aan Microsoft intune-implementatie standaarden te voldoen<br>-Apps uploaden naar Microsoft intune<br>-Apps testen in Microsoft beheerde bureaubladomgeving<br>-Apps testen met uw gebruikers<br>-Gebruikers beheren en toewijzen aan toepassingen<br>-Toepassingsupdates identificeren en implementeren via Microsoft intune<br>-Toepassingen verwijderen en verwijderen wanneer deze buiten gebruik worden gesteld<br>-Indrukken en licenties toewijzen<br>-Gebruikers ondersteuning bieden voor line-of-Business-Apps<br>Apps-instellingen extern beheren<br><br>**Microsoft** beschikt over implementatiehulpprogramma's voor Microsoft intune waarmee de toepassingen voor externe clients worden geleverd.<br><br>Voor meer informatie raadpleegt u [apps](../get-ready/apps.md).
Beveiligingscontrole en -antwoord | U bent verantwoordelijk voor het onderzoek en het oplossen van problemen met apparaten die niet door Microsoft worden beheerd, en ervoor zorgen dat het team van Microsoft beheerde bureaublad activiteiten op de hoogte is van eventuele problemen die van invloed kunnen zijn op de service.
Ondersteuning voor bewerkingen | U dient een lijst op te geven van de voorkeur contactpersonen en de experts van de persoon in uw organisatie. We hebben deze nodig voor een operationeel incident dat niet is gerelateerd aan Microsoft Managed Desktop. <br><br>U bent ook verantwoordelijk voor onderzoek en oplossingen voor apparaten en services die niet beschikbaar zijn op Microsoft Managed Desktop en ervoor zorgen dat het team van Microsoft beheerde bureaublad activiteiten altijd op de hoogte wordt gesteld.
Netwerkinfrastructuur, waaronder VPN | U bent verantwoordelijk voor het instellen, configureren en beheren (waaronder het oplossen van problemen en foutopsporing) van alle netwerken die verband houden met het netwerk en de services, waaronder internetverbindingen, netwerkbesturing, proxyconfiguratie en connectiviteits-infrastructuur.<br><br>Als een proxy is geconfigureerd (in hardware of software), is er een verzameling Url's die door de proxy moeten worden toegestaan. U bent verantwoordelijk voor het oplossen van problemen of compatibiliteitsproblemen door meerdere proxy's. U kunt netwerkproxy's toevoegen die specifiek zijn voor uw organisatie met behulp van configureerbare instellingen. Zie [configureerbare instellingen](../working-with-managed-desktop/config-setting-ref.md#proxy)voor meer informatie.<br><br>Zie [Proxy Configuration (Proxy Configuration](../get-ready/network.md)) voor meer informatie.
Afdrukken | U bent verantwoordelijk voor het installeren, onderhouden en beheren van printers en afdrukwachtrijen. Het afdrukken van een Cloud is een aanbevolen oplossing, maar dit is niet nodig. 




