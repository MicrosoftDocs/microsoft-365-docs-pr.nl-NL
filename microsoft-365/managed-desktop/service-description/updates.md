---
title: Hoe updates worden afgehandeld in Microsoft Managed Desktop
description: Het Microsoft-beheer bureaublad up-to-date houden is een balans van snelheid en stabiliteit.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1349b58bdd6243b05323f14197e0ad92c1fc0d7b
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289493"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Hoe updates worden afgehandeld in Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop verbindt alle apparaten met een moderne infrastructuur van de Cloud. Voor de up-to-date-toepassingen van Windows, Office, drivers, firmware en Microsoft Store voor bedrijven is een balans van snelheid en stabiliteit. Implementatie groepen worden gebruikt om updates en beleidsregels voor het besturingssysteem te controleren op een veilige manier. Voor meer informatie raadpleegt u de video [Microsoft Managed Desktop Change and Release Process](https://www.microsoft.com/videoplayer/embed/RE4mWqP).

Updates die door Microsoft worden uitgebracht, zijn cumulatief en zijn gecategoriseerd als kwaliteits-of functie-updates.
Zie [Windows Update voor bedrijven: typen bijwerken](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types)voor meer informatie. 

## <a name="update-groups"></a>Groepen bijwerken

Microsoft Managed Desktop gebruikt vier Azure AD-groepen om updates te beheren:

- **Test**: dit wordt gebruikt om wijzigingen in Microsoft beheerde bureaublad beleid, updates van besturingssystemen, functie-updates en andere wijzigingen in de Tenant te valideren. U mag geen gebruikers in de testgroep plaatsen. De testgroep is uitgezonderd van de vastgestelde serviceniveau overeenkomsten en de gebruikers ondersteuning. U kunt deze groep gebruiken om de compatibiliteit van toepassingen te valideren met nieuwe beleidsregels of wijzigingen in het besturingssysteem.  
- **First**: bevat oudere software-oppassers en apparaten die onder voorlopige updates konden worden bijgewerkt. Voor apparaten in deze groep kan de overlopen van de inhoud van de test ring bestaan.
- **Snel**: de prioriteit van snelheid via stabiliteit is overschreden. Geschikt voor het detecteren van kwaliteitsproblemen voordat ze voor de grote groep worden aangeboden. Deze groep fungeert als een volgende beveiligingslaag, maar is in het algemeen stabieler dan de test en eerste groepen. 
- **Algemeen**: de laatste groep om de functie-en kwaliteitsupdates te kunnen gebruiken. Deze groep bevat het merendeel van de gebruikers in de Tenant, en is daarom de nadruk op de snelheid van de migratie. Het testen van apps moet hier plaatsvinden omdat de omgeving het meest stabiel is. 

> [!NOTE]
> Als u een gebruiker naar een andere updategroep wilt verplaatsen, dient u een ondersteuningsverzoek in. Zie [ondersteuning voor Microsoft Managed Desktop](support.md) voor meer informatie over het indienen van ondersteuningsaanvragen. Als u zelf een gebruiker verplaatst, wordt de verhuizing hersteld.

Zie [rollen en verantwoordelijkheden voor Microsoft-bureaublad rollen](../intro/roles-and-responsibilities.md) voor meer informatie rollen en verantwoordelijkheden met deze implementatie groepen.

De werking van update-implementatie:
- Microsoft Managed Desktop implementeert een nieuwe functie of kwaliteitsupdate volgens de hieronder opgegeven planning.
- Tijdens de implementatie worden door Microsoft beheerde bureaublad monitoren voor tekenen van storingen of storingen (op basis van diagnostische gegevens en de gebruikers ondersteunings systeem) bijgehouden. Als dit wordt gedetecteerd, wordt de implementatie op alle huidige en toekomstige groepen direct onderbroken.
    - Voorbeeld: als er een probleem is opgetreden tijdens de implementatie van een kwaliteitsupdate voor de eerste groep, worden implementaties eerst bijgewerkt naar voornaam, snel en algemeen, totdat het probleem is opgelost.
    - U kunt compatibiliteitsproblemen rapporteren door een ticket in te dienen in de portal van de beheerde bureaublad beheerder van Microsoft.
- Functie-en kwaliteitsupdates worden apart onderbroken. PAUSE wordt standaard geactiveerd voor 35 dagen, maar kan worden verkleind of uitgebreid, afhankelijk van of het probleem wordt hersteld.
- Wanneer de groepen zijn stopgezet, wordt de implementatie hervat overeenkomstig de onderstaande planning.
- Dit implementatieproces is van toepassing op zowel functie-als kwaliteitsupdates, hoewel de tijdlijn voor elk van deze varieert.




<table>
<tr><th colspan="5">Implementatie-instellingen bijwerken</th></tr>
<tr><th>Update type</th><th>Wedstrijden</th><th>Eerste</th><th>Razendsnelle</th><th>Scala</th></tr>
<tr><td>Kwaliteitsupdates voor besturingssysteem</td><td>0 dagen</td><td>0 dagen</td><td>0 dagen</td><td>3 dagen</td></tr>
<tr><td>Onderdeel updates voor besturingssysteem</td><td>0 dagen</td><td>30 dagen</td><td>60 dagen</td><td>90 dagen</td></tr>
<tr><td>Drivers/firmware</td><td colspan="4">De planning voor kwaliteitsupdates volgen</td></tr>
<tr><td>Antivirus definitie</td><td colspan="4">Bijgewerkt bij elke scan</td></tr>
<tr><td>Microsoft 365-apps voor ondernemingen</td><td colspan="4">Het huidige kanaal van Office volgen
</table>

Zie [overzicht van update kanalen voor Microsoft 365-apps](https://docs.microsoft.com/deployoffice/overview-update-channels)voor meer informatie over het huidige kanaal voor microsoft 365-apps voor ondernemingen.

>[!NOTE]
>Deze uitstel perioden zijn bedoeld om te zorgen voor hoge beveiliging en prestatienormen voor alle gebruikers. Daarnaast is de mogelijkheid om de gegevens van de bovenstaande uitstel perioden te wijzigen, op basis van de gegevens die zijn verzameld op alle Microsoft beheerde bureaublad apparaten en de verschillende mogelijkheden en gevolgen voor updates, zodat de lengte van de bovenstaande uitstel perioden voor alle implementatie groepen op een ad-hoc basis wordt gewijzigd.
>
>Microsoft Managed Desktop voert een onafhankelijke beoordeling uit van de Windows-functie release om de noodzaak en bruikbaarheid van de beheerde tenants te beoordelen. Het kan zijn dat Microsoft de beheerde bureaubladversie van Microsoft niet alle updates voor Windows-functies implementeert. 

## <a name="windows-insider-program"></a>Windows Insider-programma

Microsoft Managed Desktop biedt geen ondersteuning voor apparaten die deel uitmaken van het Windows Insider-programma. Het Windows Insider-programma wordt gebruikt voor het valideren van pre-release van Windows-software en is bedoeld voor apparaten die geen missie essentieel zijn. Hoewel dit een belangrijke Microsoft-initiatief is, is het niet bedoeld voor uitgebreide implementatie in productieomgevingen. 

Apparaten die zijn gevonden met Windows Insider-builds, worden mogelijk in de groep testen opgenomen en van de serviceovereenkomst en de ondersteuning van de gebruikers van het Microsoft beheerde bureaublad uitgezonderd.

## <a name="bandwidth-management"></a>Bandbreedtebeheer

We gebruiken [bezorgings optimalisering](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) voor alle updates voor besturingssystemen en drivers. Hiermee wordt de downloadgrootte van de Windows Update-service geminimaliseerd door updates van collega's binnen het bedrijfsnetwerk te zoeken.


