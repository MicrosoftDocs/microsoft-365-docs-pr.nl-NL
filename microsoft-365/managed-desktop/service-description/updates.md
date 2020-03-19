---
title: Hoe updates worden verwerkt in Microsoft Managed Desktop
description: Het up-to-date houden van Microsoft Managed Desktop is een evenwicht tussen snelheid en stabiliteit.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0acbb82001d8856639f5b67daa99323f333e26ad
ms.sourcegitcommit: 213b33cbf14e35e6dc563e0b700a4eed5e42e91d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/26/2020
ms.locfileid: "42806814"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Hoe updates worden verwerkt in Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop verbindt alle apparaten met een moderne cloudinfrastructuur. Het up-to-date houden van Windows-, Office-, stuurprogramma's, firmware- en Microsoft Store-toepassingen is een evenwicht tussen snelheid en stabiliteit. Implementatiegroepen worden gebruikt om ervoor te zorgen dat updates van het besturingssysteem en het beleid op een veilige manier worden uitgerold. Zie de video Microsoft [Managed Desktop Change and Release Process](https://www.microsoft.com/videoplayer/embed/RE4mWqP)voor meer informatie.

Updates die door Microsoft worden uitgebracht, zijn cumulatief en worden gecategoriseerd als kwaliteits- of functie-updates.
Zie [Windows Update voor Bedrijven: Typen bijwerken](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types)voor meer informatie. 

## <a name="update-groups"></a>Groepen bijwerken

Microsoft Managed Desktop gebruikt vier Azure AD-groepen om updates te beheren:

- **Test:** Wordt gebruikt om microsoft Managed Desktop-beleidswijzigingen, updates van het besturingssysteem, functie-updates en andere wijzigingen die naar de tenant worden geduwd, te valideren. Er mogen geen eindgebruikers in de testgroep worden geplaatst. De testgroep is vrijgesteld van afspraken op serviceniveau en ondersteuning van eindgebruikers. Deze groep is beschikbaar voor gebruik om compatibiliteit van toepassingen te valideren met nieuwe beleids- of besturingssysteemwijzigingen.  
- **Ten eerste:** Bevat early software adopters en apparaten die kunnen worden onderworpen aan pre-release updates. Apparaten in deze groep kunnen storingen ondervinden als er scenario's zijn die niet zijn behandeld tijdens het testen in de testring.
- **Snel**: Geeft prioriteit aan snelheid boven stabiliteit. Handig voor het detecteren van kwaliteitsproblemen voordat ze worden aangeboden aan de Broad-groep. Deze groep dient als een volgende laag validatie, maar is over het algemeen stabieler dan de groepen Test en Eerste. 
- **Breed**: Laatste groep om functie- en kwaliteitsupdates beschikbaar te hebben. Deze groep bevat de meerderheid van de gebruikers in de tenant en bevordert daarom stabiliteit boven snelheid bij implementatie. Het testen van apps moet hier worden gedaan als de omgeving is het meest stabiel. 

> [!NOTE]
> Als u een gebruiker naar een andere updategroep wilt verplaatsen, dient u een ondersteuningsverzoek in. Zie [Ondersteuning voor Microsoft Managed Desktop](support.md) voor meer informatie over het indienen van ondersteuningsverzoeken. Als u zelf een gebruiker verplaatst, wordt de verhuizing teruggedraaid.

Zie [Microsoft Managed Desktop Rollen en verantwoordelijkheden](../intro/roles-and-responsibilities.md) voor meer informatierollen en verantwoordelijkheden met deze implementatiegroepen

Hoe de implementatie van updates werkt:
- Microsoft Managed Desktop implementeert een nieuwe functie of kwaliteitsupdate volgens het onderstaande schema.
- Tijdens de implementatie controleert Microsoft Managed Desktop op tekenen van storingen of storingen (op basis van diagnostische gegevens en het ondersteuningssysteem van de eindgebruiker). Als er een wordt gedetecteerd, wordt de implementatie naar alle huidige en toekomstige groepen onmiddellijk onderbroken.
    - Voorbeeld: als een probleem wordt ontdekt tijdens het implementeren van een kwaliteitsupdate naar de eerste groep, worden implementaties bijgewerkt naar First, Fast en Broad allemaal onderbroken totdat het probleem is opgelost.
    - Compatibiliteitsproblemen kunnen worden gemeld door een ticket in te dienen in de Microsoft Managed Desktop Admin-portal.
- Functie- en kwaliteitsupdates worden onafhankelijk van elkaar onderbroken. Pauze is standaard 35 dagen van kracht, maar kan worden verminderd of verlengd, afhankelijk van of het probleem wordt verholpen.
- Zodra de groepen niet zijn onderbroken, wordt de implementatie hervat volgens het onderstaande schema.
- Dit implementatieproces is van toepassing op zowel functie- als kwaliteitsupdates, hoewel de tijdlijn voor elk van deze functies varieert.




<table>
<tr><th colspan="5">Implementatie-instellingen bijwerken</th></tr>
<tr><th>Type bijwerken</th><th>Test</th><th>Eerste</th><th>Snel</th><th>Brede</th></tr>
<tr><td>Kwaliteitsupdates voor het besturingssysteem</td><td>0 dagen</td><td>0 dagen</td><td>0 dagen</td><td>3 dagen</td></tr>
<tr><td>Functie-updates voor het besturingssysteem</td><td>0 dagen</td><td>30 dagen</td><td>60 dagen</td><td>90 dagen</td></tr>
<tr><td>Stuurprogramma's/firmware</td><td colspan="4">Volgt het schema voor kwaliteitsupdates</td></tr>
<tr><td>Anti-virusdefinitie</td><td colspan="4">Bijgewerkt bij elke scan</td></tr>
<tr><td>Office 365 ProPlus</td><td colspan="4">Volgt het maandelijkse kanaal van Office
</table>

Zie [Overzicht van updatekanalen voor Office 365 ProPlus](https://docs.microsoft.com/deployoffice/overview-of-update-channels-for-office-365-proplus)voor meer informatie over het maandelijkse kanaal voor Office 365 ProPlus.

>[!NOTE]
>Deze uitstelperiodes zijn opzettelijk ontworpen om hoge beveiligings- en prestatienormen voor alle gebruikers te garanderen. Bovendien behoudt Microsoft Managed Desktop op basis van gegevens die zijn verzameld voor alle Beheerde Desktop-apparaten van Microsoft en de verschillende omvang en impact van updates de flexibiliteit voor om de lengte van de bovenstaande uitstelperioden voor alle implementatiegroepen in een advertentie te wijzigen hocbasis.
>
>Microsoft Managed Desktop voert een onafhankelijke beoordeling uit van elke Windows-functieversie om de noodzaak en het nut ervan voor de beheerde tenants te evalueren. Daarom kan Microsoft Managed Desktop al dan niet alle Windows-functie-updates implementeren. 

## <a name="windows-insider-program"></a>Windows Insider-programma

Microsoft Managed Desktop biedt geen ondersteuning voor apparaten die deel uitmaken van het Windows Insider-programma. Het Windows Insider-programma wordt gebruikt om pre-release Windows-software te valideren en is bedoeld voor apparaten die niet bedrijfskritisch zijn. Hoewel dit een belangrijk Microsoft-initiatief is, is het niet bedoeld voor een brede implementatie in productieomgevingen. 

Alle apparaten die worden gevonden met Windows Insider-builds, worden mogelijk in de testgroep geplaatst en zijn vrijgesteld van afspraken over updateserviceniveau en ondersteuning van eindgebruikers van Microsoft Managed Desktop.

## <a name="bandwidth-management"></a>Bandbreedtebeheer

We gebruiken [Delivery Optimization](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) voor alle besturingssysteem- en stuurprogramma-updates. Dit minimaliseert de downloadgrootte van de Windows Update-service door updates te zoeken van collega's binnen het bedrijfsnetwerk.


