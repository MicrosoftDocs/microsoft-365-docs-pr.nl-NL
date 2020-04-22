---
title: Hoe updates worden verwerkt in Microsoft Managed Desktop
description: Het up-to-date houden van Microsoft Managed Desktop is een balans tussen snelheid en stabiliteit.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 763a9f3c7c517a5d093b9691310720468053bf24
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636472"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Hoe updates worden verwerkt in Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop verbindt alle apparaten met een moderne cloudinfrastructuur. Het up-to-date houden van Windows-, Office-, stuurprogramma's, firmware- en Microsoft Store for Business-toepassingen is een balans tussen snelheid en stabiliteit. Implementatiegroepen worden gebruikt om ervoor te zorgen dat updates en beleidsregels van het besturingssysteem op een veilige manier worden uitgerold. Zie de video Microsoft [Managed Desktop Change and Release Process](https://www.microsoft.com/videoplayer/embed/RE4mWqP)voor meer informatie hierover.

Updates die door Microsoft zijn uitgebracht, zijn cumulatief en worden gecategoriseerd als kwaliteits- of functie-updates.
Zie [Windows Update voor Bedrijven: Update-typen](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types)voor meer informatie. 

## <a name="update-groups"></a>Groepen bijwerken

Microsoft Managed Desktop gebruikt vier Azure AD-groepen om updates te beheren:

- **Test:** wordt gebruikt om wijzigingen in het Microsoft Managed Desktop-beleid, updates van het besturingssysteem, functie-updates en andere wijzigingen die naar de tenant worden gepusht, te valideren. Er mogen geen eindgebruikers in de testgroep worden geplaatst. De testgroep is vrijgesteld van gevestigde servicelevelovereenkomsten en ondersteuning van eindgebruikers. Deze groep is beschikbaar voor gebruik om de compatibiliteit van toepassingen met nieuwe beleids- of besturingssysteemwijzigingen te valideren.  
- **Eerste:** Bevat early software adopters en apparaten die kunnen worden onderworpen aan pre-release updates. Apparaten in deze groep kunnen storingen ondervinden als er scenario's zijn die niet zijn gedekt tijdens het testen in de testring.
- **Snel**: Geeft prioriteit aan snelheid boven stabiliteit. Handig voor het opsporen van kwaliteitsproblemen voordat ze worden aangeboden aan de brede groep. Deze groep dient als een volgende laag validatie, maar is over het algemeen stabieler dan de groepen Test en Eerste. 
- **Breed**: Laatste groep die functie- en kwaliteitsupdates beschikbaar heeft. Deze groep bevat de meerderheid van de gebruikers in de tenant en geeft daarom de voorkeur aan stabiliteit boven snelheid in implementatie. Het testen van apps moet hier worden gedaan als het milieu is het meest stabiel. 

> [!NOTE]
> Als u een gebruiker naar een andere updategroep wilt verplaatsen, dient u een ondersteuningsverzoek in. Zie [Ondersteuning voor Microsoft Managed Desktop](support.md) voor meer informatie over het indienen van ondersteuningsaanvragen. Als u een gebruiker zelf verplaatst, wordt de verhuizing teruggedraaid.

Zie [Microsoft Managed Desktop-rollen en -verantwoordelijkheden](../intro/roles-and-responsibilities.md) voor meer informatie rollen en verantwoordelijkheden met deze implementatiegroepen

Hoe update-implementatie werkt:
- Microsoft Managed Desktop implementeert een nieuwe functie of kwaliteitsupdate volgens het onderstaande schema.
- Tijdens de implementatie controleert Microsoft Managed Desktop op tekenen van storing of onderbreking (op basis van diagnostische gegevens en het ondersteuningssysteem voor eindgebruikers). Als deze worden gedetecteerd, wordt de implementatie naar alle huidige en toekomstige groepen onmiddellijk onderbroken.
    - Voorbeeld: als een probleem wordt ontdekt tijdens het implementeren van een kwaliteitsupdate voor de eerste groep, worden implementaties naar Eerst, Snel en Breed bijgewerkt totdat het probleem is opgelost.
    - Compatibiliteitsproblemen kunnen worden gemeld door een ticket in te dienen in de Microsoft Managed Desktop Admin-portal.
- Functie- en kwaliteitsupdates worden onafhankelijk van elkaar onderbroken. Pauze is standaard 35 dagen van kracht, maar kan worden verminderd of verlengd, afhankelijk van of het probleem wordt verholpen.
- Zodra de groepen zijn onderbroken, wordt de implementatie hervat volgens de onderstaande planning.
- Dit implementatieproces is van toepassing op zowel functie- als kwaliteitsupdates, hoewel de tijdlijn voor elk systeem varieert.




<table>
<tr><th colspan="5">Implementatie-instellingen bijwerken</th></tr>
<tr><th>Updatetype</th><th>Test</th><th>Eerste</th><th>Snel</th><th>Brede</th></tr>
<tr><td>Kwaliteitsupdates voor het besturingssysteem</td><td>0 dagen</td><td>0 dagen</td><td>0 dagen</td><td>3 dagen</td></tr>
<tr><td>Functie-updates voor het besturingssysteem</td><td>0 dagen</td><td>30 dagen</td><td>60 dagen</td><td>90 dagen</td></tr>
<tr><td>Stuurprogramma's/firmware</td><td colspan="4">Volgt het schema voor kwaliteitsupdates</td></tr>
<tr><td>Definitie van antilichamen</td><td colspan="4">Bijgewerkt met elke scan</td></tr>
<tr><td>Microsoft 365 Apps voor bedrijven</td><td colspan="4">Volgt het maandelijkse kanaal van Office
</table>

Zie [Overzicht van updatekanalen voor Microsoft 365 Apps voor ondernemingen voor](https://docs.microsoft.com/deployoffice/overview-of-update-channels-for-office-365-proplus)meer informatie over het maandelijkse kanaal voor Microsoft 365 Apps voor ondernemingen.

>[!NOTE]
>Deze uitstelperioden zijn opzettelijk ontworpen om hoge beveiligings- en prestatienormen voor alle gebruikers te garanderen. Bovendien behoudt Microsoft Managed Desktop, op basis van gegevens die zijn verzameld op alle Microsoft Managed Desktop-apparaten en de verschillende omvang en impact van updates, flexibiliteit om de duur van de bovenstaande uitstelperioden voor alle implementatiegroepen ad hoc te wijzigen.
>
>Microsoft Managed Desktop voert een onafhankelijke beoordeling uit van elke Windows-functierelease om de noodzaak en het nut ervan voor de beheerde tenants te evalueren. Microsoft Managed Desktop kan daarom al dan niet alle Windows-functie-updates implementeren. 

## <a name="windows-insider-program"></a>Windows Insider-programma

Microsoft Managed Desktop biedt geen ondersteuning voor apparaten die deel uitmaken van het Windows Insider-programma. Het Windows Insider-programma wordt gebruikt om windows-software voor het eerst uit te brengen en is bedoeld voor apparaten die niet bedrijfskritisch zijn. Hoewel dit een belangrijk Microsoft-initiatief is, is het niet bedoeld voor brede implementatie in productieomgevingen. 

Alle apparaten die met Windows Insider-builds worden gevonden, kunnen in de testgroep worden geplaatst en worden vrijgesteld van serviceniveauovereenkomsten voor updates en ondersteuning van eindgebruikers van Microsoft Managed Desktop.

## <a name="bandwidth-management"></a>Bandbreedtebeheer

We gebruiken [Delivery Optimization](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) voor alle updates van het besturingssysteem en de stuurprogramma's. Dit minimaliseert de downloadgrootte van de Windows Update-service door te zoeken naar updates van collega's binnen het bedrijfsnetwerk.


