---
title: Hoe updates worden verwerkt in Microsoft Managed Desktop
description: Microsoft Managed Desktop up-to-date houden is een balans tussen snelheid en stabiliteit.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 7e7889cb1540cb2cb164cbbd44e9ec0e480a6fd5
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2020
ms.locfileid: "44678692"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Hoe updates worden verwerkt in Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop verbindt alle apparaten met een moderne cloudinfrastructuur. Windows-, Office-, stuurprogramma's, firmware- en Microsoft Store voor Bedrijven-toepassingen up-to-date houden is een evenwicht tussen snelheid en stabiliteit. Implementatiegroepen worden gebruikt om ervoor te zorgen dat updates van het besturingssysteem en het beleid op een veilige manier worden uitgerold. Zie de video microsoft [Managed Desktop Change and Release Process](https://www.microsoft.com/videoplayer/embed/RE4mWqP)voor meer informatie hierover.

Updates die door Microsoft zijn uitgebracht, zijn cumulatief en worden gecategoriseerd als kwaliteits- of functie-updates.
Zie [Windows Update voor Bedrijven: typen bijwerken](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types)voor meer informatie. 

## <a name="update-groups"></a>Groepen bijwerken

Microsoft Managed Desktop gebruikt vier Azure AD-groepen om updates te beheren:

- **Test:** wordt gebruikt om beleidswijzigingen van Microsoft Managed Desktop, updates van het besturingssysteem, functie-updates en andere wijzigingen die naar de tenant worden gepusht, te valideren. Er mogen geen eindgebruikers in de testgroep worden geplaatst. De testgroep is vrijgesteld van bestaande serviceleerovereenkomsten en ondersteuning voor eindgebruikers. Deze groep is beschikbaar voor gebruik om de compatibiliteit van toepassingen te valideren met nieuwe wijzigingen in het beleid of het besturingssysteem.  
- **Ten eerste:** Bevat vroege software-adopters en apparaten die kunnen worden onderworpen aan pre-release updates. Apparaten in deze groep kunnen uitval ondervinden als er scenario's zijn die niet zijn behandeld tijdens het testen in de testring.
- **Snel**: Geeft prioriteit aan snelheid boven stabiliteit. Handig voor het detecteren van kwaliteitsproblemen voordat ze worden aangeboden aan de brede groep. Deze groep dient als een volgende validatielaag, maar is over het algemeen stabieler dan de groepen Testen en Eerste. 
- **Breed**: Laatste groep met functie- en kwaliteitsupdates beschikbaar. Deze groep bevat de meerderheid van de gebruikers in de tenant en is daarom voorstander van stabiliteit boven snelheid in implementatie. Het testen van apps moet hier worden gedaan als de omgeving is het meest stabiel. 

> [!NOTE]
> Als u een gebruiker naar een andere updategroep moet verplaatsen, dient u een ondersteuningsverzoek in. Zie [Ondersteuning voor Microsoft Managed Desktop](support.md) voor meer informatie over het indienen van ondersteuningsaanvragen. Als u een gebruiker zelf verplaatst, wordt de verhuizing teruggezet.

Zie [Microsoft Managed Desktop Roles and responsibilitis](../intro/roles-and-responsibilities.md) voor meer informatierollen en verantwoordelijkheden met deze implementatiegroepen

Hoe update-implementatie werkt:
- Microsoft Managed Desktop implementeert een nieuwe functie of kwaliteitsupdate volgens de onderstaande planning.
- Tijdens de implementatie controleert Microsoft Managed Desktop op tekenen van storingen of onderbrekingen (op basis van diagnostische gegevens en het ondersteuningssysteem voor eindgebruikers). Als er een wordt gedetecteerd, wordt de implementatie naar alle huidige en toekomstige groepen onmiddellijk onderbroken.
    - Voorbeeld: als een probleem wordt ontdekt tijdens het implementeren van een kwaliteitsupdate naar de eerste groep, worden implementaties bijgewerkt naar First, Fast en Broad totdat het probleem is opgelost.
    - Compatibiliteitsproblemen kunnen worden gemeld door een ticket in te dienen in de Microsoft Managed Desktop Admin-portal.
- Functie- en kwaliteitsupdates worden onafhankelijk van ons onderbroken. Pauzeren is standaard 35 dagen van kracht, maar kan worden verminderd of verlengd, afhankelijk van of het probleem wordt verholpen.
- Zodra de groepen niet zijn onderbroken, wordt de implementatie hervat volgens de onderstaande planning.
- Dit implementatieproces is van toepassing op zowel functie- als kwaliteitsupdates, hoewel de tijdlijn per stuk verschilt.




<table>
<tr><th colspan="5">Implementatie-instellingen bijwerken</th></tr>
<tr><th>Type bijwerken</th><th>Test</th><th>Eerste</th><th>Snel</th><th>Brede</th></tr>
<tr><td>Kwaliteitsupdates voor besturingssysteem</td><td>0 dagen</td><td>0 dagen</td><td>0 dagen</td><td>3 dagen</td></tr>
<tr><td>Functie-updates voor besturingssysteem</td><td>0 dagen</td><td>30 dagen</td><td>60 dagen</td><td>90 dagen</td></tr>
<tr><td>Stuurprogramma's/firmware</td><td colspan="4">Volgt het schema voor kwaliteitsupdates</td></tr>
<tr><td>Anti-virus definitie</td><td colspan="4">Bijgewerkt met elke scan</td></tr>
<tr><td>Microsoft 365-apps voor ondernemingen</td><td colspan="4">Het huidige kanaal van Office volgen
</table>

Zie Overzicht van updatekanalen voor Microsoft 365 Apps voor meer informatie over Huidige kanaal voor Microsoft [365-apps voor](https://docs.microsoft.com/deployoffice/overview-update-channels)bedrijven.

>[!NOTE]
>Deze uitstelperioden zijn opzettelijk ontworpen om hoge beveiligings- en prestatienormen voor alle gebruikers te garanderen. Bovendien behoudt Microsoft Managed Desktop, op basis van gegevens die zijn verzameld over alle Microsoft Managed Desktop-apparaten en de verschillende reikwijdte en impact van updates, flexibiliteit om de lengte van de bovenstaande uitstelperioden voor alle implementatiegroepen op ad hoc basis te wijzigen.
>
>Microsoft Managed Desktop voert een onafhankelijke beoordeling uit van elke release van de Windows-functie om de noodzaak en het nut ervan voor de beheerde tenants te evalueren. Microsoft Managed Desktop kan daarom al dan niet alle Windows-functie-updates implementeren. 

## <a name="windows-insider-program"></a>Windows Insider-programma

Microsoft Managed Desktop biedt geen ondersteuning voor apparaten die deel uitmaken van het Windows Insider-programma. Het Windows Insider-programma wordt gebruikt om windows-software vooraf te valideren en is bedoeld voor apparaten die niet bedrijfskritisch zijn. Hoewel dit een belangrijk Microsoft-initiatief is, is het niet bedoeld voor een brede implementatie in productieomgevingen. 

Alle apparaten die worden gevonden met Windows Insider-builds kunnen in de groep Test worden geplaatst en worden vrijgesteld van overeenkomsten op het niveau van de updateservice en ondersteuning van eindgebruikers van Microsoft Managed Desktop.

## <a name="bandwidth-management"></a>Bandbreedtebeheer

We gebruiken [Delivery Optimization](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) voor alle updates van het besturingssysteem en stuurprogramma. Dit minimaliseert de downloadgrootte van de Windows Update-service door updates te zoeken van collega's binnen het bedrijfsnetwerk.


