---
title: Hoe updates worden verwerkt in Microsoft Managed Desktop
description: Het Microsoft Managed Desktop up-to-date houden is een evenwicht tussen snelheid en stabiliteit.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5961ac4eb16928754849f5f32ecd06d4d2e4650d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917714"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Hoe updates worden verwerkt in Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop maakt verbinding met een moderne cloudinfrastructuur. Het up-Windows, Office, stuurprogramma's, firmware en Microsoft Store voor Bedrijven-toepassingen up-to-date houden is een evenwicht tussen snelheid en stabiliteit. Implementatiegroepen worden gebruikt om ervoor te zorgen dat updates en beleidsregels van het besturingssysteem op een veilige manier worden geïmplementeerd. Zie voor meer informatie de video [Microsoft Managed Desktop Change and Release Process](https://www.microsoft.com/videoplayer/embed/RE4mWqP).

Updates die door Microsoft zijn uitgebracht, zijn cumulatief en worden gecategoriseerd als kwaliteits- of functie-updates.
Zie voor meer informatie [Windows Update voor Bedrijven: Updatetypen.](/windows/deployment/update/waas-manage-updates-wufb#update-types) 

## <a name="update-groups"></a>Groepen bijwerken

Microsoft Managed Desktop gebruikt vier Azure AD-groepen om updates te beheren:

- **Test:** Wordt gebruikt om Microsoft Managed Desktop wijzigingen in het beleid, updates van besturingssysteem, functie-updates en andere wijzigingen die naar de tenant worden doorgevoerd te valideren. Er mogen geen gebruikers in de testgroep worden geplaatst. De testgroep is vrijgesteld van bestaande serviceovereenkomsten en gebruikersondersteuning. Deze groep is beschikbaar voor gebruik voor het valideren van de compatibiliteit van toepassingen met nieuwe beleids- of besturingssysteemwijzigingen.  
- **Ten** eerste: Bevat early software adopters en apparaten die onderhevig kunnen zijn aan pre-release updates. Apparaten in deze groep kunnen uitval krijgen als er scenario's zijn die niet zijn behandeld tijdens het testen in de testring.
- **Snel:** prioriteit geeft prioriteit aan snelheid boven stabiliteit. Handig om kwaliteitsproblemen op te sporen voordat ze worden aangeboden aan de groep Breed. Deze groep fungeert als een volgende laag validatie, maar is meestal stabieler dan de groepen Testen en Eerste. 
- **Breed:** Laatste groep om functie- en kwaliteitsupdates beschikbaar te hebben. Deze groep bevat de meeste gebruikers in de tenant en geeft daarom de voorkeur aan stabiliteit ten opzichte van de snelheid in de implementatie. Het testen van apps moet hier worden uitgevoerd, omdat de omgeving het meest stabiel is. 

### <a name="moving-devices-between-update-groups"></a>Apparaten verplaatsen tussen updategroepen
Mogelijk wilt u dat sommige apparaten updates als laatste ontvangen en andere apparaten die u als eerste wilt gebruiken. Als u deze apparaten naar de juiste updategroep wilt verplaatsen, dient u [een ondersteuningsaanvraag](../working-with-managed-desktop/admin-support.md?view=o365-worldwide) voor beheerders in en worden de apparaten voor u verplaatst. 

> [!NOTE]
> Als u een gebruiker naar een andere updategroep wilt verplaatsen, dient u een ondersteuningsaanvraag in. Verplaats apparaten niet zelf tussen updategroepen. Er zijn ernstige gevolgen als een apparaat onjuist wordt verplaatst. Het apparaat kan onverwacht worden bijgewerkt en beleid kan conflicteren en de apparaatconfiguratie wijzigen.

Zie rollen en verantwoordelijkheden voor meer informatie over rollen en verantwoordelijkheden in [deze implementatiegroepen Microsoft Managed Desktop rollen en verantwoordelijkheden](../intro/roles-and-responsibilities.md)

### <a name="using-microsoft-managed-desktop-update-groups"></a>Groepen Microsoft Managed Desktop bijwerken 
Er zijn onderdelen van de service die u beheert, zoals app-implementatie, waar het mogelijk nodig is om alle beheerde apparaten te targeten. In deze gevallen is het zinvol om updategroepen te gebruiken om deze gebruikers te bereiken met de informatie dat u het lidmaatschap van deze groepen niet kunt toevoegen, verwijderen of wijzigen. 

## <a name="how-update-deployment-works"></a>Hoe update-implementatie werkt:
1. Microsoft Managed Desktop implementeert een nieuwe functie of kwaliteitsupdate volgens de planning die is opgegeven in de volgende tabel.
2. Tijdens de implementatie worden Microsoft Managed Desktop op tekenen van fouten of verstoringen op basis van diagnostische gegevens en het ondersteuningssysteem van de gebruiker. Als er een wordt gedetecteerd, wordt de implementatie onmiddellijk onderbroken voor alle huidige en toekomstige groepen.
    - Voorbeeld: als er een probleem wordt ontdekt tijdens het implementeren van een kwaliteitsupdate naar de eerste groep, worden implementaties bijgewerkt naar First, Fast en Broad totdat het probleem is opgelost.
    - U kunt compatibiliteitsproblemen melden door een ticket in te dienen in de Microsoft Managed Desktop Admin portal.
    - Functie- en kwaliteitsupdates worden onafhankelijk van elkaar onderbroken. Pauze is standaard 35 dagen van kracht, maar kan worden verkleind of uitgebreid, afhankelijk van of het probleem is opgelost.
3. Wanneer de groepen niet zijn onderbroken, wordt de implementatie hervat volgens de planning in de tabel.

Dit implementatieproces is van toepassing op zowel functie- als kwaliteitsupdates, maar de tijdlijn verschilt per functie.




<table>
    <tr><th colspan="5">Implementatie-instellingen bijwerken</th></tr>
    <tr><th>Updatetype</th><th>Test</th><th>Eerst</th><th>Snel</th><th>Breed</th></tr>
    <tr><td>Kwaliteitsupdates voor besturingssysteem</td><td>0 dagen</td><td>0 dagen</td><td>0 dagen</td><td>3 dagen</td></tr>
    <tr><td>Functie-updates voor besturingssysteem</td><td>0 dagen</td><td>30 dagen</td><td>60 dagen</td><td>90 dagen</td></tr>
    <tr><td>Stuurprogramma's/firmware</td><td colspan="4">Volgt de planning voor kwaliteitsupdates</td></tr>
    <tr><td>Anti-virusdefinitie</td><td colspan="4">Bijgewerkt bij elke scan</td></tr>
    <tr><td>Microsoft 365-apps voor ondernemingen</td><td colspan="4"><a href="/microsoft-365/managed-desktop/get-started/m365-apps#updates-to-microsoft-365-apps">Meer informatie</a></td></tr>
    <tr><td>Microsoft Edge</td><td colspan="4"><a href="/microsoft-365/managed-desktop/get-started/edge-browser-app#updates-to-microsoft-edge">Meer informatie</a></td></tr>
    <tr><td>Microsoft Teams</td><td colspan="4"><a href="/microsoft-365/managed-desktop/get-started/teams#updates">Meer informatie</a></td></tr>
</table>

>[!NOTE]
>Deze uitstelperioden zijn opzettelijk ontworpen om hoge beveiligings- en prestatiestandaarden voor alle gebruikers te garanderen. Op basis van gegevens die zijn verzameld op alle Microsoft Managed Desktop-apparaten en het variërende bereik en de invloed van updates, behoudt Microsoft Managed Desktop zich bovendien flexibiliteit voor het wijzigen van de lengte van de bovenstaande uitstelperioden voor alle implementatiegroepen op ad-hocbasis.
>
>Microsoft Managed Desktop voert een onafhankelijke beoordeling uit van Windows functiere release om de noodzaak en het nut ervan voor de beheerde tenants te evalueren. Daarom kunnen Microsoft Managed Desktop al dan niet alle functies Windows implementeren. 

## <a name="windows-insider-program"></a>Windows Insider-programma

Microsoft Managed Desktop biedt geen ondersteuning voor apparaten die deel uitmaken van het Windows Insider-programma. Het Windows Insider-programma wordt gebruikt om pre-releasesoftware Windows te valideren en is bedoeld voor apparaten die niet essentieel zijn voor de missie. Hoewel het een belangrijk Microsoft-initiatief is, is het niet bedoeld voor een brede implementatie in productieomgevingen. 

Alle apparaten die met Windows Insider-builds worden gevonden, kunnen worden toegevoegd aan de groep Test en worden vrijgesteld van updateovereenkomsten op serviceniveau en gebruikersondersteuning van Microsoft Managed Desktop.

## <a name="bandwidth-management"></a>Bandbreedtebeheer

We gebruiken [Delivery Optimization voor](/windows/deployment/update/waas-delivery-optimization) alle besturingssysteem- en stuurprogramma-updates. Hierdoor wordt de downloadgrootte van de Windows Update-service geminimaliseerd door te zoeken naar updates van collega's binnen het bedrijfsnetwerk.