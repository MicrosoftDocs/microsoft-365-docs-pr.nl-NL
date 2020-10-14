---
title: Office 365 beveiliging, Office 365 ATP, EOP, ATP, MSDO
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 08/13/2020
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Beveiliging in Office 365, van EOP tot ATP-abonnementen 1 en 2, Standard versus strikte beveiligingsconfiguraties, en nog veel meer. Begrijpt wat u hebt en hoe u uw eigenschappen kunt beveiligen.
ms.openlocfilehash: 256a24a7816a40e1bd60c687a875f84e605f5208
ms.sourcegitcommit: d76a4c07f0be2938372bdfae50e0e4d523bd8e9f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456469"
---
# <a name="office-365-security-overview"></a>Overzicht van Office 365-beveiliging

In dit artikel worden de nieuwe beveiligingseigenschappen in de Cloud geïntroduceerd. Ongeacht of u deel uitmaakt van een Beveiligingscentrum, bent u een beveiligingsbeheerder van de ruimte, of wilt u een nieuweder, laten we aan de slag gaan.

> [!CAUTION]
> Als u gebruikmaakt van **Outlook.com**, **Microsoft 365-familie**of **Microsoft 365 Personal**en de informatie voor *veilige koppelingen* en *veilige bijlagen* hebt, ***klikt u op deze koppeling***: [geavanceerde Outlook.com-beveiliging voor Microsoft 365-abonnees](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

## <a name="office-365-security-spelled-out"></a>Beveiligings spelling van Office 365

Elk Office 365-abonnement bevat beveiligingsmogelijkheden. Welke doelstellingen en acties u kunt uitvoeren, hangt af van de focus van deze verschillende abonnementen. In Office 365-beveiliging zijn er drie belangrijke beveiligingsservices (of-producten) die zijn gekoppeld aan uw type abonnement:

1. Exchange Online Protection (EOP)
1. Advanced Threat Protection, abonnement 1 (ATP P1)
1. Advanced Threat Protection, abonnement 2 (ATP P2)

> [!NOTE]
> Als u uw abonnement hebt gekocht en beveiligingsfuncties *nu*moet uitvoeren, gaat u verder met de stappen in het artikel [beveiliging tegen bedreigingen](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) . Als u nog geen ervaring hebt met uw abonnement en uw licentie wilt weten voordat u begint, kunt u door de facturering > uw producten in het [Microsoft 365-Beheercentrum](https://admin.microsoft.com/AdminPortal/#/homepage).

Beveiligings versies van Office 365 op basis van de kern beveiligingen die worden aangeboden door EOP. EOP bevindt zich in elk abonnement waar Exchange Online-postvakken kunnen worden gevonden (Let op: alle beveiligingsproducten die hier worden besproken zijn op de Cloud).

U wordt gewend de volgende drie onderdelen te zien die op deze manier worden beschreven:

|EOP  | ATP P1 | ATP P2  |
|---------|---------|---------|
|Zorgt voor geen algemene, op volume gebaseerde, bekende aanvallen.    |  Beschermt e-mail en samenwerking tegen malware van malware, phishing en zakelijke e-mail in de dag van de dag.       | Hiermee voegt u een onderzoek, jacht, reactie, automatisering en simulatie van een post-schending toe.         |

Laten we aan de hand van de architectuur eerst denken aan elk deel als cumulatieve lagen voor beveiliging, elk met een veiligheids nadruk. Meer soortgelijke informatie:

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="Placeholder graphic":::

Hoewel elk van deze services een doelstelling opneemt van het beschermen, detecteren, onderzoeken en beantwoorden, kunnen ***alle*** Services ***een van de*** doelstellingen van de beveiliging, detectie, onderzoek en reageren uitvoeren.

De kern van Office 365 beveiliging is EOP bescherming. ATP P1 bevat EOP. ATP P2 bevat P1 en EOP. De structuur is cumulatief. Daarom moet u bij het configureren van dit product beginnen met EOP en werken met ATP.

Hoewel configuratie van e-mail verificatie plaatsvindt in openbare DNS, is het belangrijk om deze functie te configureren om spoofing te verdedigen. *Als u gebruikmaakt van EOP,* ***moet u [e-mail verificatie configureren](https://docs.microsoft.com/microsoft-365/security/office-365-security/email-validation-and-authentication)***.

Als u een Office 365 E3 of lager hebt, hebt u EOP, maar met de optie voor het aanschaffen van zelfstandige ATP P1 via een upgrade. Als u Office 365 E5 hebt, hebt u al ATP P2.

> [!TIP]
> Als uw abonnement geen Office 365 E3 of E5 is, kunt u nog steeds controleren of u een upgrade wilt uitvoeren naar ATP P1. Als u geïnteresseerd bent, biedt [deze webpagina](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) een lijst met abonnementen die in aanmerking komen voor de ATP P1-upgrade (Controleer het einde van de pagina voor het nauwkeurig afdrukken).

## <a name="the-office-365-security-ladder-from-eop-to-atp"></a>De beveiligings ladder van Office 365 van EOP naar ATP

<br/>

![EOP en ATP en de nadruk op hun beveiliging, via beschermen en detecteren voor onderzoek en antwoorden.Configuratie voor e-mail verificatie (minimaal DKIM en DMARC) moet zijn ingesteld voor EOP en up.](../../media/tp_EOPATPP1P2Take6.gif#lightbox)


> [!IMPORTANT]
> Meer informatie over deze pagina's: [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/exchange-online-protection-overview)en [Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp).

Met het toevoegen van ATP-abonnementen wordt een voordeel van het gebruik van echt EOP Threat Management soms moeilijk te zien. Als u wilt weten of een upgrade-pad geschikt is voor uw organisatie, kunt u het volgende doen om de mogelijkheden van elk product te bekijken:

 - bedreigingen voorkomen en detecteren
 - wordt onderzocht
 - stopt

beginnen met **Exchange Online Protection**:
<p>

|Voorkomen/detecteren  |Onderzoeken  |Beantwoorden  |
|---------|---------|---------|
| Technologieën zijn:<ul><li>spam</li><li>Phish</li><li>malware</li><li>massale e-mail</li><li>spoof informatie</li><li>imitatie detectie</li><li>Beheerquarantaine</li><li>Beheerders en gebruikers inzendingen van onjuiste positieve en onjuiste negatieven</li><li>Toestaan/blokkeren voor Url's en bestanden</li><li>Rapporten</li></u1>|<li>Zoeken in audit logboek</li><li>Bericht traceren</li>|<li>Automatische opschooning van Zero-Hour (ZAP)</li><li>Verfijning en testen van de acceptatie-en blok lijsten</li>|

Als u de EOP wilt zien, gaat u **[naar dit artikel](https://docs.microsoft.com/microsoft-365/security/office-365-security/exchange-online-protection-overview?view=o365-worldwide#:~:text=Exchange%20Online%20Protection%20%28EOP%29%20is%20the%20cloud-based%20filtering,is%20also%20available%20in%20the%20following%20on-premises%20scenarios%3A)**.

Omdat deze producten cumulatief zijn en u een abonnement op deze producten evalueert, voegt u deze mogelijkheden toe.

Winst met **Advanced Threat Protection, abonnement 1** (naar datum):
<p>

|Voorkomen/detecteren  |Onderzoeken  |Beantwoorden  |
|---------|---------|---------|
| Technologieën bevatten alles in EOP plus:<u1><li>Veilige bijlagen</li><li>Veilige koppelingen<li>ATP-beveiliging voor werkbelasting (ex. SharePoint Online, teams, OneDrive voor bedrijven)</li><li>Beveiliging van de tijd van klikken op e-mail, Office-clients en teams</li><li>ATP anti-phishing</li><li>De bescherming van gebruikers en domein imitatie</li><li>Waarschuwingen en integratie-API van SIEM voor waarschuwingen</li>|<li>SIEM-integratie-API voor detecties</li><li>**Functie voor detecteren van real time**</li><li>URL-tracering</li>|<li>Datzelfde</li></u1>

Daarom is ATP P1 uitgebreid aan de ***preventie*** kant van het huis en voegt extra vormen van ***detectie***toe.

Met ATP P1 voegt u ook eenmalige **detectie van realtime** toe voor onderzoek. De naam van de *bedreiging van de* hulp van de hulp van de hulp van een programma De presentatie wordt niet weergegeven in ATP P2.

Winst met **Advanced Threat Protection, abonnement 2** (tot datum):
<p>

|Voorkomen/detecteren  |Onderzoeken  |Beantwoorden  |
|---------|---------|---------|
| Technologieën bevatten alles in EOP en ATP P1 plus:<u1><li>Datzelfde</li>|<li>**Bedreigingsverkenner**</li><li>Bedreigingsoverzichten</li><li>Campagne weergaven</li>|<li>Geautomatiseerd onderzoek en antwoord (lucht)</li><li>AIR van bedreigings Verkenner</li><li>AIR voor gebruikers met een veraangetaste</li><li>SIEM-integratie-API voor geautomatiseerde onderzoeken</li>

Daarom is de ATP-P2 uitgebreid aan het ***onderzoek en de respons*** zijde van het huis, en wordt een nieuwe jacht sterkte toegevoegd. Automatiseringsinvoegtoepassingen.

In het hulpprogramma voor ATP wordt het hulpprogramma voor primaire jacht aangeduid met de naam **Threat Explorer** , in plaats van detectie van realtime. Als u de bedreigings Verkenner ziet wanneer u naar het Beveiligingscentrum gaat, gebruikt u de ATP-P2.

**[Ga naar dit artikel](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)** voor meer informatie over ATP P1 en P2.

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
> ***Insider-tip***. Met de inhoudsopgave docs.microsoft.com kunt u meer lezen over EOP en ATP. Ga terug naar deze pagina, [Office 365 Beveiligingsoverzicht](https://docs.microsoft.com/microsoft-365/security/office-365-security/?view=o365-worldwide), en u ziet dat de inhoudsopgave van de inhoudsopgave op de zijbalk wordt weergegeven. Het begint met de implementatie (inclusief migratie) en gaat verder met preventie, detectie, onderzoek en antwoord. <p> Dit is een deel van de onderdelen van **beveiligingsbeheer** , zodat onderwerpen over beveiligings **bewerkingen** worden gevolgd. Als u een nieuw lid bent van een van beide functie, gebruikt u de koppeling in deze tip en uw kennis van de inhoudsopgave om de ruimte te leren kennen. Let op het gebruik van *feedback koppelingen* en *tarief artikelen* . Feedback helpt ons wat we u bieden.

## <a name="where-to-go-next"></a>Waar u verder kunt gaan

Als u een beveiligingsbeheerder bent, moet u mogelijk DKIM of DMARC configureren voor uw e-mailberichten. U kunt de strenge beveiligings vooraf voorkeuren voor uw prioriteits gebruikers invullen of de nieuwe functies in het product zoeken. Of als u met behulp van beveiligings-OPS werkt, kunt u de detectie van realtime en de bedreigings Verkenner toepassen om de detectie van eindgebruikers met aanvals Simulator te onderzoeken en te beantwoorden of te trainen. Hier volgen enkele aanvullende aanbevelingen voor wat u op de volgende manier kunt bekijken.

[Verificatie via e-mail, waaronder SPF, DKIM en DMARC (met koppelingen naar de instellingen van alle drie)](https://docs.microsoft.com/microsoft-365/security/office-365-security/email-validation-and-authentication)

[Bekijk de specifieke ' gouden ' configuraties](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) en [Gebruik de aanbevolen standaardinstellingen om beveiligingsbeleid snel te configureren](https://docs.microsoft.com/microsoft-365/security/office-365-security/preset-security-policies)

Bijpraten over [nieuwe functies in Office 365 ATP (waaronder EOP-ontwikkelingen)](https://docs.microsoft.com/microsoft-365/security/office-365-security/whats-new-in-office-365-atp)

[Bedreigings Verkenner of realtime-detectie gebruiken](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)

[Aanvals Simulator gebruiken in Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulator)