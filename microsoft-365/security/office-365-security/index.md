---
title: Office 365 beveiliging, Microsoft Defender voor Office 365, EOP, MSDO
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
- m365initiative-defender-office365
description: Beveiliging in Office 365, van EOP tot Defender voor Office 365-abonnementen 1 en 2, Standard versus strikte beveiligingsconfiguraties en meer. Begrijpt wat u hebt en hoe u uw eigenschappen kunt beveiligen.
ms.openlocfilehash: a24f71286a524c4057fd1354804b067497479493
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794518"
---
# <a name="office-365-security-overview"></a>Overzicht van Office 365-beveiliging

In dit artikel worden de nieuwe beveiligingseigenschappen in de Cloud geïntroduceerd. Ongeacht of u deel uitmaakt van een Beveiligingscentrum, bent u een beveiligingsbeheerder van de ruimte, of wilt u een nieuweder, laten we aan de slag gaan.

> [!CAUTION]
> Als u gebruikmaakt van **Outlook.com**, **Microsoft 365-familie** of **Microsoft 365 Personal**, en u hebt *veilige koppelingen* en *veilige bijlagen* met informatie nodig, ***klikt u op deze koppeling** _: [geavanceerde Outlook.com-beveiliging voor Microsoft 365-abonnees](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

## <a name="office-365-security-spelled-out"></a>Beveiligings spelling van Office 365

Elk Office 365-abonnement bevat beveiligingsmogelijkheden. Welke doelstellingen en acties u kunt uitvoeren, hangt af van de focus van deze verschillende abonnementen. In Office 365-beveiliging zijn er drie belangrijke beveiligingsservices (of-producten) die zijn gekoppeld aan uw type abonnement:

1. Exchange Online Protection (EOP)
1. Microsoft Defender voor Office 365, abonnement 1 (Defender voor Office P1)
1. Microsoft Defender voor Office 365, abonnement 2 (Defender voor Office P2)

> [!NOTE]
> Als u uw abonnement hebt gekocht en beveiligingsfuncties wilt toepassen _right nu *, gaat u verder met de stappen in het artikel [beveiliging tegen bedreigingen](protect-against-threats.md) . Als u nog geen ervaring hebt met uw abonnement en uw licentie wilt weten voordat u begint, kunt u door de facturering > uw producten in het [Microsoft 365-Beheercentrum](https://admin.microsoft.com/AdminPortal/#/homepage).

Beveiligings versies van Office 365 op basis van de kern beveiligingen die worden aangeboden door EOP. EOP bevindt zich in elk abonnement waar Exchange Online-postvakken kunnen worden gevonden (Let op: alle beveiligingsproducten die hier worden besproken zijn op de Cloud).

U wordt gewend de volgende drie onderdelen te zien die op deze manier worden beschreven:

|EOP|Microsoft Defender voor Office 365 P1|Microsoft Defender voor Office 365 P2|
|---|---|---|
|Zorgt voor geen algemene, op volume gebaseerde, bekende aanvallen.|Beschermt e-mail en samenwerking tegen malware van malware, phishing en zakelijke e-mail in de dag van de dag.|Hiermee voegt u een onderzoek, jacht, reactie, automatisering en simulatie van een post-schending toe.|
|

Laten we aan de hand van de architectuur eerst denken aan elk deel als cumulatieve lagen voor beveiliging, elk met een veiligheids nadruk. Meer soortgelijke informatie:

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP en Microsoft Defender voor Office 365 en hun onderlinge relatie met Service nadruk, waaronder een opmerking voor e-mail verificatie.":::

Hoewel elk van deze services een doelstelling opneemt van beschermen, detecteren, onderzoeken en beantwoorden, ***alle** _ de services kunnen de doelen _*_van de_*_ bescherming, detectie, onderzoek en reageren uitvoeren.

De kern van Office 365 beveiliging is EOP bescherming. Microsoft Defender voor Office 365 P1 bevat EOP. Defender voor Office 365 P2 bevat P1 en EOP. De structuur is cumulatief. Daarom moet u bij het configureren van dit product beginnen met EOP en werken met Defender voor Office 365.

Hoewel configuratie van e-mail verificatie plaatsvindt in openbare DNS, is het belangrijk om deze functie te configureren om spoofing te verdedigen. _Als u gebruikmaakt van EOP, * *,**moet u [e-mail verificatie configureren](email-validation-and-authentication.md)**_.

Als u een Office 365 E3 of lager hebt, hebt u EOP, maar u kunt ook zelfstandige versie voor Office 365 P1 installeren via een upgrade. Als u Office 365 E5 hebt, hebt u al een Defender voor Office 365 P2.

> [!TIP]
> Als uw abonnement geen Office 365 E3 of E5 is, kunt u nog steeds controleren of u beschikt over de optie om een upgrade uit te voeren naar Microsoft Defender voor Office 365 P1. Als u geïnteresseerd bent, biedt [deze webpagina](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) een lijst met abonnementen die in aanmerking komen voor de upgrade Microsoft Defender for Office 365 P1 (Controleer het einde van de pagina voor het nauwkeurig afdrukken).

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>De beveiligings ladder van Office 365 van EOP naar Microsoft Defender voor Office 365

![EOP en Microsoft Defender voor Office 365 en hun beveiliging te benadrukken, via beschermen en detecteren om te onderzoeken en te reageren. Configuratie voor e-mail verificatie (minimaal DKIM en DMARC) moet zijn ingesteld voor EOP en up.](../../media/tp_EOPATPP1P2Take6.gif#lightbox)

> [!IMPORTANT]
> Meer informatie over deze pagina's: [Exchange Online Protection](exchange-online-protection-overview.md)en [Defender voor Office 365](office-365-atp.md).

Wat maakt het toevoegen van Microsoft Defender voor Office 365 met een voordeel van het gebruik van echt EOP Threat Management is moeilijk te zien. Als u wilt weten of een upgrade-pad geschikt is voor uw organisatie, kunt u het volgende doen om de mogelijkheden van elk product te bekijken:

- bedreigingen voorkomen en detecteren
- wordt onderzocht
- stopt

beginnen met _ * Exchange Online Protection * *:
<p>

|Voorkomen/detecteren|Onderzoeken|Beantwoorden|
|---|---|---|
|Technologieën zijn:<ul><li>spam</li><li>Phish</li><li>malware</li><li>massale e-mail</li><li>spoof informatie</li><li>imitatie detectie</li><li>Beheerquarantaine</li><li>Beheerders en gebruikers inzendingen van onjuiste positieve en onjuiste negatieven</li><li>Toestaan/blokkeren voor Url's en bestanden</li><li>Rapporten</li></u1>|<li>Zoeken in audit logboek</li><li>Bericht traceren</li>|<li>Automatische opschooning van Zero-Hour (ZAP)</li><li>Verfijning en testen van de acceptatie-en blok lijsten</li>|
|

Als u de EOP wilt zien, gaat u **[naar dit artikel](exchange-online-protection-overview.md)**.

Omdat deze producten cumulatief zijn, voegt u deze mogelijkheden toe als u Microsoft Defender voor Office 365 P1 evalueert en ervoor kiest om u aan te melden.

Winst met **Defender voor Office 365, abonnement 1** (naar datum):
<p>

|Voorkomen/detecteren|Onderzoeken|Beantwoorden|
|---|---|---|
|Technologieën bevatten alles in EOP plus:<u1><li>Veilige bijlagen</li><li>Veilige koppelingen<li>Microsoft Defender voor Office 365 beveiliging voor werkbelasting (ex. SharePoint Online, teams, OneDrive voor bedrijven)</li><li>Beveiliging van de tijd van klikken op e-mail, Office-clients en teams</li><li>anti phishing in Defender voor Office 365</li><li>De bescherming van gebruikers en domein imitatie</li><li>Waarschuwingen en integratie-API van SIEM voor waarschuwingen</li>|<li>SIEM-integratie-API voor detecties</li><li>**Functie voor detecteren van real time**</li><li>URL-tracering</li>|<li>Datzelfde</li></u1>

Daarom breidt Microsoft Defender voor Office 365 P1 uit op de **_belettende_* _ zijde van het huis, en voegt extra vormen van _*_detectie_*_ toe.

Met Microsoft Defender voor Office 365 P1 voegt u ook de *constante detectie van de real time* toe * voor onderzoek. De naam van de hulp van de hulpfunctie van de Threat jacht is vetgedrukt, omdat dit duidelijk is omdat u *weet* dat u Defender voor Office 365 P1 gebruikt. Dit wordt niet weergegeven in Defender voor Office 365 P2.

Winst met **Defender voor Office 365, abonnement 2** (op datum):
<p>

|Voorkomen/detecteren|Onderzoeken|Beantwoorden|
|---|---|---|
|Technologieën bevatten alles in EOP en Microsoft Defender voor Office 365 P1 plus:<u1><li>Datzelfde</li>|<li>**Bedreigingsverkenner**</li><li>Bedreigingsoverzichten</li><li>Campagne weergaven</li>|<li>Geautomatiseerd onderzoek en antwoord (lucht)</li><li>AIR van bedreigings Verkenner</li><li>AIR voor gebruikers met een veraangetaste</li><li>SIEM-integratie-API voor geautomatiseerde onderzoeken</li>

Daarom breidt Microsoft Defender voor Office 365 P2 uit op het **_onderzoek en antwoord_* _ kant van het huis, en voegt een nieuwe jacht sterkte toe. Automatiseringsinvoegtoepassingen.

In Microsoft Defender voor Office 365 P2 wordt het hulpprogramma voor primaire jacht genoemd met de naam _ *bedreigings Verkenner** in plaats van detectie van real time. Als u de bedreigings Verkenner ziet wanneer u naar het Beveiligingscentrum gaat, hebt u Microsoft Defender voor Office 365 P2.

**[Ga naar dit artikel](office-365-atp.md)** voor informatie over Microsoft Defender voor Office 365 P1 en P2.

> [!TIP]
> EOP en Microsoft Defender voor Office 365 worden ook verschillend wanneer ze bij eindgebruikers komen. In EOP en Defender voor Office 365 *P1 is de focus op de* aandacht gebracht en zijn deze twee services ook de *Outlook-invoegtoepassing* voor het rapporteren van berichten, zodat gebruikers e-mailberichten kunnen rapporteren die ze verdacht kunnen vinden voor verdere analyse. <p> In de EOP-versie van Defender voor Office 365 (die alles bevat in en P1), wordt de focus verplaatst naar een *verdere training* voor eindgebruikers en zodat het Beveiligingscentrum toegang heeft tot een krachtig hulpmiddel voor het hulpmiddel van de *bedreiging* , en de metriek van de eindgebruikers biedt.

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Microsoft Defender voor Office 365, abonnement 1 versus abonnement 2 referentiemateriaal blad

Deze naslaggids helpt u inzicht te krijgen in de mogelijkheden van elk Microsoft Defender voor Office 365-abonnement. Wanneer deze combinatie met uw kennis van EOP-functies is, kan de IT-medewerkers van de organisatie vaststellen wat Microsoft Defender for Office 365 het beste is voor hun behoeften.

|Abonnement 1 voor Office 365|Abonnement 2 voor Office 365|
|---|---|
|Functies voor configuratie, beveiliging en detectie: <ul><li>[Veilige bijlagen](atp-safe-attachments.md)</li><li>[Veilige koppelingen](atp-safe-links.md)</li><li>[ATP voor SharePoint, OneDrive en Microsoft Teams](atp-for-spo-odb-and-teams.md)</li><li>[Bescherming tegen phishing in Defender voor Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[Detecties in realtime](threat-explorer.md)</li></ul>|De mogelijkheden van de abonnement 1 voor Defender voor Office 365 <p> --- plus --- <p> Functies voor automatisering, onderzoek, herstel en onderwijs: <ul><li>[Bedreigingsoverzichten](threat-trackers.md)</li><li>[Bedreigingsverkenner](threat-explorer.md)</li><li>[Geautomatiseerd onderzoek en reactie](office-365-air.md)</li><li>[Aanvalssimulator](attack-simulator.md)</li></ul>|
|

- Microsoft Defender voor Office 365 abonnement 2 is opgenomen in Office 365 E5, Office 365 A5 en Microsoft 365 E5.

- Abonnement 1 voor Microsoft Defender voor Office 365 is inbegrepen in Microsoft 365 Business Premium.

- Microsoft Defender voor Office 365 plan 1 en Defender for Office 365-abonnement 2 zijn elk beschikbaar als invoegtoepassing voor bepaalde abonnementen. Voor meer informatie gaat u verder met de [beschikbaarheid van een koppelings functie in Microsoft Defender for Office 365-abonnementen](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- De functie [Veilige documenten](safe-docs.md) is alleen beschikbaar voor gebruikers met een Microsoft 365 E5- of Microsoft 365 E5 Security-licentie (niet opgenomen in abonnementen voor Microsoft Defender voor Office 365).

- Als uw huidige abonnement geen Microsoft Defender voor Office 365 bevat en u dit wilt, kunt u [contact opnemen met de verkoop als u een proefabonnement wilt starten](https://go.microsoft.com/fwlink/p/?LinkId=518644)en wilt weten hoe Microsoft voor Office 365 in uw organisatie kan werken.

> [!TIP]
> ***Insider-tip** _. U kunt de docs.microsoft.com-inhoudsopgave gebruiken voor meer informatie over EOP en Microsoft Defender voor Office 365. Ga terug naar deze pagina, [Office 365 Beveiligingsoverzicht](https://docs.microsoft.com/microsoft-365/security/office-365-security), en u ziet dat de inhoudsopgave van de inhoudsopgave op de zijbalk wordt weergegeven. Het begint met de implementatie (inclusief migratie) en gaat verder met preventie, detectie, onderzoek en antwoord. <p> Deze structuur wordt gedeeld, zodat _ *beveiligingsbeheer** onderwerpen worden gevolgd door onderwerpen over **beveiligingsbewerkingen** . Als u een nieuw lid bent van een van beide functie, gebruikt u de koppeling in deze tip en uw kennis van de inhoudsopgave om de ruimte te leren kennen. Let op het gebruik van *feedback koppelingen* en *tarief artikelen* . Feedback helpt ons wat we u bieden.

## <a name="where-to-go-next"></a>Waar u verder kunt gaan

Als u een beveiligingsbeheerder bent, moet u mogelijk DKIM of DMARC configureren voor uw e-mailberichten. U kunt de strenge beveiligings vooraf voorkeuren voor uw prioriteits gebruikers invullen of de nieuwe functies in het product zoeken. Of als u met behulp van beveiligings-OPS werkt, kunt u de detectie van realtime en de bedreigings Verkenner toepassen om de detectie van eindgebruikers met aanvals Simulator te onderzoeken en te beantwoorden of te trainen. Hier volgen enkele aanvullende aanbevelingen voor wat u op de volgende manier kunt bekijken.

[Verificatie via e-mail, waaronder SPF, DKIM en DMARC (met koppelingen naar de instellingen van alle drie)](email-validation-and-authentication.md)

[Bekijk de specifieke ' gouden ' configuraties](recommended-settings-for-eop-and-office365-atp.md) en [Gebruik de aanbevolen standaardinstellingen om beveiligingsbeleid snel te configureren](preset-security-policies.md)

Bijpraten over [nieuwe functies in Microsoft Defender voor Office 365 (waaronder EOP-ontwikkelingen)](whats-new-in-office-365-atp.md)

[Bedreigings Verkenner of realtime-detectie gebruiken](threat-explorer.md)

[Aanvals Simulator gebruiken in Microsoft Defender voor Office 365](attack-simulator.md)
