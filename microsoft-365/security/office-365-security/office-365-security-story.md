---
title: Office 365-beveiliging
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 08/13/2020
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- microsoft-365-docs-pr
description: Beveiliging in Office 365, van EOP tot ATP-abonnementen 1 en 2, Standard versus strikte beveiligingsconfiguraties, en meer, zodat u kunt begrijpen wat u hebt en hoe u uw eigenschappen kunt beveiligen.
ms.openlocfilehash: 66a83d99197b8af98ef191b348b1303a8233a990
ms.sourcegitcommit: e6283e7c32ba9628fc45e9abc5cd4d21fb3f7ca9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/29/2020
ms.locfileid: "48299296"
---
# <a name="office-365-security-outline"></a>Beveiligingsoverzicht van Office 365

In dit artikel worden de nieuwe beveiligingseigenschappen in de Cloud geïntroduceerd. Ongeacht of u deel uitmaakt van een Beveiligingscentrum, bent u een beveiligingsbeheerder van de ruimte, of wilt u een nieuweder, laten we aan de slag gaan.

> [!CAUTION]
> Hallo. Als u gebruikmaakt van **Outlook.com**, **Microsoft 365-familie**of **Microsoft 365 Personal**en de informatie voor *veilige koppelingen* en *veilige bijlagen* hebt, ***klikt u op deze koppeling***: [geavanceerde Outlook.com-beveiliging voor Microsoft 365-abonnees](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2). Bedankt!

## <a name="office-365-security-spelled-out"></a>Beveiligings spelling van Office 365

Elk Office 365-abonnement bevat beveiligingsmogelijkheden. Welke doelstellingen en acties u kunt uitvoeren, hangt af van de focus van deze verschillende abonnementen. In Office 365-beveiliging zijn er drie belangrijke beveiligingsservices (of-producten) die zijn gekoppeld aan uw type abonnement:

1. Exchange Online Protection (EOP)
1. Advanced Threat Protection, abonnement 1 (ATP P1)
1. Advanced Threat Protection, abonnement 2 (ATP P2)

> [!NOTE]
> Als u uw abonnement hebt gekocht en beveiligingsfuncties *nu*moet uitvoeren, gaat u verder met de stappen in het artikel [beveiliging tegen bedreigingen](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide) . Als u nog geen ervaring hebt met uw abonnement en uw licentie wilt weten voordat u begint, kunt u door de facturering > uw producten in het [Microsoft 365-Beheercentrum](https://admin.microsoft.com/AdminPortal/#/homepage).

Beveiligings versies van Office 365 op basis van de kern beveiligingen die worden aangeboden door EOP. EOP bevindt zich in elk abonnement waar Exchange Online-postvakken kunnen worden gevonden (Let op: alle beveiligingsproducten die hier worden besproken zijn op de Cloud).

U wordt gewend de volgende drie onderdelen te zien die op deze manier worden beschreven:

|EOP  | ATP P1 | ATP P2  |
|---------|---------|---------|
|Zorgt voor geen algemene, op volume gebaseerde, bekende aanvallen.    |  Beschermt e-mail en samenwerking tegen malware van malware, phishing en zakelijke e-mail in de dag van de dag.       | Hiermee voegt u een onderzoek, jacht, reactie, automatisering en simulatie van een post-schending toe.         |

Laten we aan de hand van de architectuur eerst denken aan elk deel als cumulatieve lagen voor beveiliging, elk met een veiligheids nadruk. Meer soortgelijke informatie:

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_EOPandATPGraphic.png" alt-text="EOP en ATP, en de relaties zijn onderling onderling met Service nadruk, waaronder een opmerking voor e-mail verificatie.":::

Hoewel elk van deze services een specifiek doel opneemt onder bescherming, detecteren, onderzoeken en beantwoorden, kunnen ***alle*** Services een van de doel ***stellingen van de*** bescherming, detectie, onderzoek en het reageren uitvoeren.

De kern van Office 365 beveiliging is EOP bescherming. ATP P1 bevat EOP. ATP P2 bevat P1 en EOP. De structuur is cumulatief. Daarom moet u bij het configureren van de ATP eerst met EOP beginnen en de lagen samenwerken.

Hoewel configuratie van e-mail verificatie plaatsvindt in openbare DNS, is het belangrijk om deze functie te configureren om spoofing te verdedigen. *Als u gebruikmaakt van EOP,* ***moet u [e-mail verificatie configureren](https://docs.microsoft.com/microsoft-365/security/office-365-security/email-validation-and-authentication?view=o365-worldwide)***.

Als u een Office 365 E3 of lager hebt, hebt u EOP, maar met de optie voor het aanschaffen van zelfstandige ATP P1 via een upgrade. Als u Office 365 E5 hebt, hebt u al ATP P2.

> [!TIP]
> Als uw abonnement geen Office 365 E3 of E5 is, kunt u nog steeds controleren of u een upgrade wilt uitvoeren naar ATP P1. Als u geïnteresseerd bent, biedt [deze webpagina](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) een lijst met abonnementen die in aanmerking komen voor de ATP P1-upgrade (Controleer het einde van de pagina voor het nauwkeurig afdrukken).

## <a name="the-office-365-security-ladder-from-eop-to-atp"></a>De beveiligings ladder van Office 365 van EOP naar ATP

:::image type="content" source="../../media/tp_EOPATPEmailAuth4.gif" alt-text="EOP en ATP, met hun specifieke sterkte, van beschermen en detecteren voor onderzoek en antwoorden. Daarnaast wordt de configuratie voor e-mail verificatie weergegeven als nodig EOP.":::

> [!IMPORTANT]
> Meer informatie over deze pagina's: [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/exchange-online-protection-overview?view=o365-worldwide)en [Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide).

Met het toevoegen van ATP-abonnementen wordt een voordeel van het gebruik van echt EOP Threat Management soms moeilijk te zien. Als u wilt weten of een upgrade-pad geschikt is voor uw organisatie, kunt u het volgende doen om de mogelijkheden van elk product te bekijken:

 - bedreigingen voorkomen en detecteren
 - wordt onderzocht
 - stopt

beginnen met **Exchange Online Protection**:
<p>

|Voorkomen/detecteren  |Onderzoeken  |Vangen  |
|---------|---------|---------|
| Technologieën zijn:<ul><li>spam</li><li>Phish</li><li>malware</li><li>massale e-mail</li><li>spoof informatie</li><li>imitatie detectie</li><li>Beheerquarantaine</li><li>Beheerders en gebruikers inzendingen van onjuiste positieve en onjuiste negatieven</li><li>Toestaan/blokkeren voor Url's en bestanden</li><li>Rapporten</li></u1>|<li>Zoeken in audit logboek</li><li>Bericht traceren</li>|<li>Automatische opschooning van Zero-Hour (ZAP)</li><li>Verfijning en testen van de acceptatie-en blok lijsten</li>|

Als u de EOP wilt zien, gaat u **[naar dit artikel](https://review.docs.microsoft.com/microsoft-365/security/office-365-security/exchange-online-protection-overview?view=o365-21vianet&branch=tp_EOPOverview)**.

Omdat deze producten cumulatief zijn en u een abonnement op deze producten evalueert, voegt u deze mogelijkheden toe.

Winst met **Advanced Threat Protection, abonnement 1** (naar datum):
<p>

|Voorkomen/detecteren  |Onderzoeken  |Vangen  |
|---------|---------|---------|
| Technologieën bevatten alles in EOP plus:<u1><li>Veilige bijlagen</li><li>Veilige koppelingen<li>ATP-beveiliging voor werkbelasting (ex. SharePoint Online, teams, OneDrive voor bedrijven)</li><li>Beveiliging van de tijd van klikken op e-mail, Office-clients en teams</li><li>ATP anti-phishing</li><li>De bescherming van gebruikers en domein imitatie</li><li>Waarschuwingen en integratie-API van SIEM voor waarschuwingen</li>|<li>SIEM-integratie-API voor detecties</li><li>**Functie voor detecteren van real time**</li><li>URL-tracering</li>|<li>Datzelfde</li></u1>

Daarom is ATP P1 uitgebreid aan de ***preventie*** kant van het huis en voegt extra vormen van ***detectie***toe.

Met ATP P1 voegt u ook eenmalige **detectie van realtime** toe voor onderzoek. De naam van de *bedreiging van de* hulp van de hulp van de hulp van een programma De presentatie wordt niet weergegeven in ATP P2.

Winst met **Advanced Threat Protection, abonnement 2** (tot datum):
<p>

|Voorkomen/detecteren  |Onderzoeken  |Vangen  |
|---------|---------|---------|
| Technologieën bevatten alles in EOP en ATP P1 plus:<u1><li>Datzelfde</li>|<li>**Bedreigingsverkenner**</li><li>Bedreigingsoverzichten</li><li>Campagne weergaven</li>|<li>Geautomatiseerd onderzoek en antwoord (lucht)</li><li>AIR van bedreigings Verkenner</li><li>AIR voor gebruikers met een veraangetaste</li><li>SIEM-integratie-API voor geautomatiseerde onderzoeken</li>

Daarom is de ATP-P2 uitgebreid aan het ***onderzoek en de respons*** zijde van het huis, en wordt een nieuwe jacht sterkte toegevoegd. Automatiseringsinvoegtoepassingen.

In het hulpprogramma voor ATP wordt het hulpprogramma voor primaire jacht aangeduid met de naam **Threat Explorer** , in plaats van detectie van realtime. Als u de bedreigings Verkenner ziet wanneer u naar het Beveiligingscentrum gaat, gebruikt u de ATP-P2.

**[Ga naar dit artikel](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)** voor meer informatie over ATP P1 en P2.

> [!TIP]
> EOP en ATP worden ook verschillend wanneer het bij eindgebruikers komt. In EOP en ATP *P1 is de focus op de*aandacht gebracht en zijn deze twee services ook de *Outlook-invoegtoepassing* voor het rapporteren van berichten, zodat gebruikers e-mailberichten kunnen rapporteren die ze verdacht kunnen vinden, voor verdere analyse. <p> In de ATP-P2 (die alles in EOP en P1 bevat), wordt de focus verplaatst naar een *verdere training* voor eindgebruikers en zodat het Beveiligingscentrum toegang heeft tot een krachtig hulpmiddel voor het hulpmiddel van de *Threat Simulator* , en de metriek van de eindgebruikers biedt.

## <a name="office-365-atp-plan-1-vs-plan-2-cheat-sheet"></a>Office 365 ATP plan 1 versus abonnement 2 referentiemateriaal blad

Aan de hand van deze naslaginformatie kunt u inzicht krijgen in de mogelijkheden van elk ATP-abonnement. Wanneer deze combinatie met uw kennis van EOP-functies is, kan de IT-medewerkers van besluit om te bepalen welke ATP het meest geschikt is voor hun behoeften.

|Office 365 ATP-abonnement 1|Office 365 ATP-abonnement 2|
|---|---|
|<br/>Functies voor configuratie, beveiliging en detectie: <ul><li>[Veilige bijlagen](atp-safe-attachments.md)</li><li>[Veilige koppelingen](atp-safe-links.md)</li><li>[ATP voor SharePoint, OneDrive en Microsoft Teams](atp-for-spo-odb-and-teams.md)</li><li>[ATP-bescherming tegen phishing](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)</li><li>[Detecties in realtime](threat-explorer.md)</li></ul>|Functies van Office 365 ATP-abonnement 1<br/>--- plus ---<br/>Functies voor automatisering, onderzoek, herstel en onderwijs:</li><li>[Bedreigingsoverzichten](threat-trackers.md)</li><li>[Bedreigingsverkenner](threat-explorer.md)</li><li>[Geautomatiseerd onderzoek en reactie](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)</li><li>[Aanvalssimulator](attack-simulator.md)</li></ul>|
|

- Office 365 ATP-abonnement 2 is inbegrepen in Office 365 E5, Office 365 A5 en Microsoft 365 E5.

- Office 365 ATP-abonnement 1 is inbegrepen in Microsoft 365 Business Premium.

- Office 365 ATP-abonnement 1 en Office 365 ATP-abonnement 2 zijn elk beschikbaar als invoegtoepassing voor bepaalde abonnementen. Voor meer informatie gaat u naar de [beschikbaarheid](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)van een koppelings functie voor meer informatie over ATP-abonnementen.

- De [Veilige documenten](safe-docs.md)-functie is alleen beschikbaar voor gebruikers met Microsoft 365 E5- of Microsoft 365 E5 Security-licentie (niet opgenomen in Office 365 ATP-abonnementen).

- Als uw huidige abonnement Office 365 ATP niet bevat en u dit wilt, kunt u [contact opnemen met de verkoop om een proefabonnement te starten](https://go.microsoft.com/fwlink/p/?LinkId=518644)en erachter te komen hoe ATP in uw organisatie kan werken.

> [!TIP]
> ***Insider-tip***. Met de inhoudsopgave docs.microsoft.com kunt u meer lezen over EOP en ATP. Ga naar de beveiligings artikelen van [Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap?view=o365-worldwide) en u ziet dat de inhoudsopgave van de organisatie begint met evaluatie en implementatie (inclusief migratie), en verloopt vervolgens de preventie, detectie, onderzoek en reactie. <p> Dit is een deel van de onderdelen van **beveiligingsbeheer** , zodat onderwerpen over beveiligings **bewerkingen** worden gevolgd. Als u een nieuw lid bent van een van beide functie, gebruikt u de koppeling in deze tip en uw kennis van de inhoudsopgave om de ruimte te leren kennen. Let op het gebruik van *feedback koppelingen* en *tarief artikelen* . Feedback helpt ons wat we u bieden.
