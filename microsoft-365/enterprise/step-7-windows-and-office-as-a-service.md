---
title: 'Stap 7: Service van Windows en Office'
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/20/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Lees hoe u het onderhoud voor Windows en Office in uw omgeving kunt voorbereiden.
ms.openlocfilehash: d47abca74f7fea4c49f9aa28a93cd4afe40a0981
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805269"
---
# <a name="step-7-windows-and-office-servicing"></a>Stap 7: Service van Windows en Office

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-1.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-10.png" alt="Step 7" height="144" width="144" /></td>
<td><p><strong>Stap 7: Service van Windows en Office</strong></p>
<p>Er worden continu nieuwe mogelijkheden toegevoegd aan zowel Windows 10 als Office 365 ProPlus om gebruikerservaringen en de beveiliging te blijven bijwerken met de nieuwste innovaties. Lees hoe u uw versie actueel houdt met de halfjaarlijkse en maandelijkse updates, hoe het nieuwe servicemodel werkt en welke hulpmiddelen en opties u hebt.</p></td>
<td><a href="https://aka.ms/ddev7" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-20.png" alt="Step 7" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>Windows en Office onderhouden is de zevende stap in ons aanbevolen implementatieproces. In deze stap wordt de planningsaspecten van het voorbereiden van halfjaarlijkse update van functies behandeld. Ga naar het [Implementatiecentrum voor desktops](https://aka.ms/HowToShift) om het volledige desktop-implementatieproces te zien.
>

In zowel Windows 10 als Office 365 ProPlus worden nieuwe onderhoudsopties, ondersteuningsmodellen en updatetijdlijnen geïntroduceerd. Deze wijzigingen vereenvoudigen het proces om naar nieuwste functies bij te werken. Behalve deze updates zijn er ook nieuwe configuratieopties voor serviceabonnementen die aan uw behoeften voldoen. We bekijken hoe u kunt voorbereiden op Semi-annual-kanaalupdates die nieuwe functies en mogelijkheden voor Windows 10 en Office 365 ProPlus bieden en hoe u tegelijkertijd de nieuwe functies in Microsoft Endpoint Configuration Manager (huidige vertakking) kunt inzetten.

[Klanten helpen met de overstap naar Windows 10 en Office 365 ProPlus](https://www.microsoft.com/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/)

## <a name="update-types"></a>Soorten updates

Updates worden onderverdeeld in twee hoofdcategorieën: functie-updates en vervolgens op kwaliteits- en beveiligingsupdates die cumulatieve beveiligings-, betrouwbaarheids- en bugfixes bevatten. Wat de frequentie betreft, hanteren zowel Windows als Office een Semi-annual-kanaal. Nieuwe functies worden twee keer per jaar rond maart en september geleverd, maar de kwaliteits- en de beveiligingsupdates vinden maandelijks plaats. Bovendien bieden we, exclusief voor Office 365-toepassingen, een optie voor een Monthly-kanaal met volledig ondersteuning, waarbij updates zowel nieuwe functies als kwaliteitsupdates bevatten.

Als u gewend bent aan een langere cyclus tussen updates voor uw desktopbesturingssysteem en apps, vraagt u zich misschien af:

  - Zijn de updates compatibel?

  - Moet ik mijn gebruikers steeds opnieuw trainen?

  - En wat zijn de risico's?

Om deze vragen te beantwoorden en voor de logica achter het vaker leveren van nieuwe mogelijkheden, leggen we een paar voordelen van deze benadering uit.

### <a name="feature-update-benefits"></a>Voordelen van functie-updates

Allereerst zijn we afgestapt van het oude model waarbij elke drie jaar grote wijzigingsgolven werden geïntroduceerd en voeren we nu twee keer per jaar periodieke kleinere wijzigingen met functie-updates uit. Waarom? Doordat technologische trends zo snel gaan en gepaard gaan met snel veranderende beveiligingsrisico's blijven gebruikservaringen en bescherming hierdoor actueel. Sommige beveiligingsupdates kunnen bijvoorbeeld niet gewoon worden geleverd als maandelijkse beveiligingsupdates of virusdefinitiebestanden. Het gaat mogelijk om kleine wijzingen aan het platform, zoals beveiliging op basis van virtualisatie.

[Snelgids voor Windows als een service](https://docs.microsoft.com/windows/deployment/update/waas-quick-start)

[Risico's beperken met beveiligingsfuncties van Windows 10](https://docs.microsoft.com/windows/security/threat-protection/overview-of-threat-mitigations-in-windows-10%20%20)

### <a name="cumulative-update-model-benefits"></a>Voordelen van een cumulatief updatemodel

Ten tweede worden veel van de problemen uit het verleden gecorrigeerd wanneer kwaliteits- en beveiligingsupdates als een cumulatief updatepakket worden geleverd. Vroeger kon het zijn dat u iedere maand kon kiezen uit een dozijn of meer maandelijks updates voor zowel Windows als Office. Zoals u zich kunt voorstellen, zorgde dit voor u een nagenoeg onmogelijk aantal testmatrixen voor ondersteuning. Als u bovendien een versie van Windows of Office van een jaar of langer geleden installeert, kan het uren tot soms dagen duren om alle updates sinds deze versie werd uitgebracht, uit te voeren.

Met het cumulatieve model bent u altijd met één update weer up-to-date en hiermee wordt het aantal te implementeren maandelijkse updates beperkt. Elke update bouwt verder op de updates van voorgaande maanden en bevat alle oplossingen die u nodig hebt om up-to-date te blijven. Cumulatieve updates zijn vooral handig als pc's gedurende een paar maanden zijn uitgeschakeld, omdat de updates klaar liggen om opnieuw aan een andere gebruiker te worden toegewezen.

### <a name="expanded-validation-of-updates"></a>Uitgebreide validatie van updates

Een ander voordeel is dat, voordat we de updates voor algemene implementatie uitrollen, deze eerst kunnen worden uitgebracht via de Insider-Programma's voor [Office](https://products.office.com/office-insider?tab=Windows-Desktop) en [Windows](https://insider.windows.com/). Hierdoor kunnen we diagnostische gegevens verzamelen en feedback ontvangen nog voordat we de updates voor iedereen uitbrengen. De Insider-Programma's zijn nu voor iedereen toegankelijk, zodat u de updates al eerder kunt begrijpen. Tegen de tijd dat we updates uitbrengen, hebben we reeds diagnostische gegevens ontvangen van miljoenen configuraties, dus wanneer er updates worden uitgebracht, is de kwaliteit nu aanzienlijk voorspelbaarder

En wat daar nog bij komt, omdat de Monthly-kanaalupdates worden meegenomen in de builds van Office 365 ProPlus Insider, als u een Semi-Annual-kanaal voor Office gebruikt om twee keer per jaar de functie-updates te krijgen, kunt u deze builds al vroeg valideren en de gerichte versies van het Semi-Annual-kanaal gebruiken.

### <a name="supporting-management-tools"></a>Ondersteunende beheerprogramma’s

We hebben ook nagedacht hoe we de implementatie van updates voor u zo gemakkelijk mogelijk kunnen maken. Configuration Manager (huidige vertakking) wordt regelmatig bijgewerkt om de implementatie van deze updates voor Windows en Office en eventuele nieuwe mogelijkheden te ondersteunen.

[Windows 10-updates implementeren met Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)

[Office 365 ProPlus met Configuration Manager beheren](https://docs.microsoft.com/configmgr/sum/deploy-use/manage-office-365-proplus-updates)

## <a name="overview-of-windows-and-office-channels"></a>Overzicht van Windows- en Office-kanalen

Windows 10 biedt drie servicekanalen:

- Met het [**Windows Insider-programma**](https://docs.microsoft.com/windows/deployment/update/waas-overview#windows-insider) voor organisaties kunnen zij functies die worden geleverd bij de volgende functie-updates testen en feedback erover geven
- **Semi-Annual-kanaal** biedt tweemaal per jaar nieuwe functies met functie-updates
- **Long Term Servicing Channel** is alleen bedoeld voor gespecialiseerde apparaten die een langerlopende servicefunctie nodig hebben.

Office 365 biedt vier servicekanalen:

- Met het [**Office Insider-programma**](https://support.office.com/article/What-is-Office-Insider-f4208185-b63a-4b68-9c7a-9a32d2411c16) voor organisaties kunnen zij de nieuwste Office-functies en -functionaliteiten die nog in ontwikkeling zijn, testen en feedback erover geven
- **Monthly-kanaal** om gebruikers te voorzien van de nieuwste Office-functies zodra deze beschikbaar zijn
- **Semi-annual-kanaal** biedt slechts tweemaal per jaar nieuwe functies met functie-updates
- **Semi-annual-kanaal (targeted)** is een volledig ondersteunde build van Office die pilot-gebruikers en testers van toepassingscompatibiliteit de mogelijkheid biedt het volgende Semi-annual-kanaal te testen en te valideren.

Voor meer informatie over de Windows- en Office-servicekanalen raadpleegt u de onderstaande documentatie:

- [Overzicht van Windows als een service](https://docs.microsoft.com/windows/deployment/update/waas-overview#servicing-channels)
- [Overzicht van de updatekanalen voor Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus#BKMK_SAC)

## <a name="phased-deployment-of-updates"></a>Gefaseerde implementatie van updates

We gaan nu in op de manier waarop u deze updates gaat uitrollen. Voor elke versie adviseren we ten minste drie implementatiefasen voor IT: validatie, pilot en algemene productimplementatie. Zodra u eenmaal werkt met Windows 10 en Office 365 ProPlus, gebruikt u het maandelijkse onderhoud om met de kritieke beveiligings- en kwaliteitsupdates actueel te blijven. Vervolgens gaat u naar het semi-annual-onderhoud voor nieuwe functies.

### <a name="monthly-updating"></a>Maandelijkse updates

Het servicemodel is zo ontworpen dat u ervoor kunt kiezen om de uitrollen van de nieuwe functies te beperken tot twee keer per jaar en zo nodig kunt u zelfs een semi-annual-update overslaan en kwaliteits- en beveiligingsupdates blijven ontvangen. Zoals gezegd, betekent de cumulatieve aard van de maandelijkse updates dat ze elke maand groter worden.

#### <a name="express-updates"></a>Expres-updates

Door gebruik te maken van een technologie genaamd 'Expres-updates' in Windows en binaire delta-compressie in Office kunnen we de downloadgrootte aanzienlijk verkleinen. Bij beide benaderingen maakt de update-engines een vergelijking met wat er op de PC staat en zoekt alleen de aanwezige verschillen die moeten worden bijgewerkt.

[Kwaliteitsupdates voor Windows 10 uitgelegd & het einde van Delta-updates](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/Windows-10-quality-updates-explained-amp-the-end-of-delta/ba-p/214426)

Windows Update voor Bedrijven en Windows Server Update Services ondersteunen al lange tijd Expres-updates, maar we hebben dit nu uitgebreid met ondersteuning voor Microsoft Endpoint Configuration Manager (huidige vertakking), zodat deze ook Expres-updates kan gebruiken.

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-3.png)

#### <a name="binary-delta-compression"></a>Binaire delta-compressie

Binaire delta-compressie in Office wordt alleen gebruikt als u vanuit de recentste versie van Office 365 ProPlus bijwerkt. De benadering werkt dus alleen als u vanuit de vorige build gaat bijwerken en u kunt geen updates overslaan.

U kunt kanalen voor Windows- en Office-updates beheren via Configuration Manager met gebruik van het standaardproces voor goedkeuring en doelprocessen. U kunt ook beleidsinstellingen in Office en Windows gebruiken om gebruikte updatekanalen af te dwingen, evenals gerelateerde instellingen.

### <a name="semi-annual-updates"></a>Semi-annual-updates

Dit zijn de overwegingen voor maandelijkse updates. Dan nu de grotere, halfjaarlijkse updates.

Zoals we bij Gereedheid van apparaten en apps hebben behandeld, dient u de voorbereiding van deze grotere updates te beginnen met dezelfde gereedheidshulpprogramma's die we hebben ingesteld in stap 1 van het implementatieproces.

Wat de tools betreft, kunt u beleidsinstellingen gebruiken bij Windows Update voor Bedrijven, software-updatebeheer via Microsoft Endpoint Configuration Manager (huidige vertakking), Windows Server Update Services (WSUS) of beleid bijwerken dat is ingesteld door Microsoft Intune. Als u zich zorgen maakt over de netwerkbandbreedte, raadpleegt u Stap 2: Gereedheid van mappen en netwerken voor meer informatie over de opties om netwerkverkeer te beperken via Delivery Optimization en andere peer-to-peer-cachetechnologieën.

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-4.png)

[Semi-annual-kanaal voor Windows](https://docs.microsoft.com/windows/deployment/update/waas-overview#semi-annual-channel)

[Semi-annual-kanaal voor Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus#BKMK_SAC)

#### <a name="upgrade-task-sequences"></a>Takenreeksen upgraden

De installatie van de grotere functie-updates via standaard routines voor software-updates is een ondersteunde optie, maar veel organisaties verkiezen een Upgrade takenreeks te gebruiken met Microsoft Endpoint Configuration Manager (huidige vertakking) of de Microsoft Deployment Toolkit.

Met een Takenreeks kunt u aangepaste controles of taken maken VOORDAT u de functie-update installeert en kunt u aangepaste taken uitvoeren NADAT de update-installatie zelf is voltooid: taken na de update zijn mogelijk waar nodig de services tijdelijk onderbreken tijdens de update, stuurprogramma's installeren en vervangen, upgrades van toepassingen of de taakbalk en van personalisatie-instellingen voor Windows 10 Start.

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-5.png)

Als u al takenreeksen gebruikt om uw Windows 7-computers naar Windows 10 te migreren en ervaring hebt met deze hulpmiddelen goed, is dit een prima startpunt en hebt u complete controle. Hoewel u één takenreeks voor de gehele upgrade kunt gebruiken, is het heel gebruikelijk dat organisaties twee takenreeksen gebruiken. Eén takenreeks zorgt ervoor dat de computers gereed zijn voor de upgrade, waarbij alle vereiste installatiebestanden op doelcomputers in stilte worden voorbereid, en één om de daadwerkelijke upgrade uit te voeren. Op deze manier zorgt u ervoor dat de productiviteit van uw gebruikers minder wordt beïnvloed.

[Een taakreeks maken voor het upgraden van een besturingssysteem in Configuration Manager](https://docs.microsoft.com/configmgr/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system)

#### <a name="semi-annual-channel-support-for-feature-updates"></a>Ondersteuning met een Semi-annual-kanaal voor functie-updates

[Zoals aangekondigd in september 2018](https://www.microsoft.com/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/), wordt er in de ondersteuningsperiode voor de semi-annual-kanaalupdates het volgende model gebruikt.

  - Alle momenteel ondersteunde functie-updates van Windows 10 Enterprise en Education, te beginnen met versie 1607, worden gedurende 30 maanden na de oorspronkelijke releasedatum ondersteund.

  - Alle toekomstige functie-updates, te beginnen met 1809, die voor september zijn bedoeld, worden gedurende 30 maanden na de releasedatum ondersteund.

  - Toekomstige functie-updates die voor maart zijn bedoeld en te beginnen met 1903, worden nog 18 maanden na de releasedatum ondersteund.

  - Halfjaarlijkse updates voor Office 365 ProPlus worden nog 18 maanden ondersteund

#### <a name="additional-setup-automation-options-outside-of-task-sequences"></a>Aanvullende automatiseringsopties voor het instellen buiten de takenreeksen

Als u geen Upgrade takenreeks gebruikt, kunt u nu aangepaste acties uitvoeren of stuurprogrammabestanden toepassen tijdens de functie-updates in de fase voorafgaand aan de installatie (dus voordat de compatibiliteitscontrole wordt uitgevoerd door de installatie) of in de fase voordat het definitief wordt (voordat de upgrade wordt uitgevoerd).

[Wat is er nieuw in de installatie van Windows 10, versie 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803%23windows-setup)

## <a name="next-step"></a>Volgende stap 

## <a name="step-8-user-communications-and-training"></a>[Stap 8: Communicatie en training voor gebruikers](https://aka.ms/mdd8)

## <a name="previous-step"></a>Vorige stap 

## <a name="step-6-os-deployment-and-feature-updates"></a>[Stap 6: implementatie van besturingssysteem en functie-updates](https://aka.ms/mdd6)
