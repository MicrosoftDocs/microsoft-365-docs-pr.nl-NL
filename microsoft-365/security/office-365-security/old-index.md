---
title: Office 365-beveiliging, Microsoft Defender voor Office 365, EOP, MSDO
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 08/13/2020
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Beveiliging in Office 365, van EOP tot Defender voor Office 365-abonnementen 1 en 2, standaard- en strikte beveiligingsconfiguraties en meer. Begrijpen wat u hebt en hoe u uw eigendommen kunt beveiligen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: db37718ce2feae9c79ff6b323eb22e30f24e72b2
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204373"
---
# <a name="office-365-security-overview"></a>Overzicht van Office 365-beveiliging

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)


In dit artikel worden de nieuwe beveiligingseigenschappen in de cloud beschreven. Of u nu deel uitmaakt van een beveiligingscentrum, u bent een nieuwe beveiligingsbeheerder of u wilt een opfrisser, laten we aan de slag gaan.

> [!CAUTION]
> Als u **Outlook.com**, **Microsoft 365 Family** of **Microsoft 365 Personal** gebruikt en *veilige koppelingen* of informatie over *veilige bijlagen* nodig hebt, ***klikt u op deze koppeling***: [geavanceerde Outlook.com-beveiliging voor Microsoft 365-abonnees](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

## <a name="office-365-security-spelled-out"></a>Alles over Office 365-beveiliging

Elk Office 365-abonnement biedt beveiligingsmogelijkheden. De doelstellingen en acties die u kunt ondernemen, zijn afhankelijk van de focus van deze verschillende abonnementen. Office 365-beveiliging biedt drie belangrijke beveiligingsservices (of -producten) die zijn gekoppeld aan uw abonnementstype:

1. Exchange Online Protection (EOP)
1. Microsoft Defender voor Office 365 Abonnement 1 (Defender voor Office P1)
1. Microsoft Defender voor Office 365 Abonnement 2 (Defender voor Office P2)

> [!NOTE]
> Als u uw abonnement hebt gekocht en *nu meteen* beveiligingsfuncties moet uitrollen, gaat u verder met de stappen in het artikel [Beveiliging tegen bedreigingen](protect-against-threats.md). Als u nog niet eerder een abonnement hebt gehad en de details van uw licentie voordat wilt weten voordat u begint, bladert u in Facturering > Uw producten in het [Microsoft 365-beheercentrum](https://admin.microsoft.com/AdminPortal/#/homepage).

De Office 365-beveiliging is gebaseerd op de kernbeveiligingen die door EOP worden geboden. EOP is aanwezig in elk abonnement waar Exchange Online-postvakken kunnen worden gevonden (alle beveiligingsproducten die hier worden besproken, zijn namelijk gebaseerd op de cloud).

Misschien bent u gewend om deze drie onderdelen op de volgende manier te zien:

|EOP|Microsoft Defender voor Office 365 P1|Microsoft Defender voor Office 365 P2|
|---|---|---|
|Hiermee voorkomt u brede, volumegebaseerde, bekende aanvallen.|Beschermt e-mail en samenwerking tegen zero-day-malware, phish- en zakelijke e-mailinbreuk.|Hiermee voegt u onderzoek na inbreuken, opsporing en reacties toe, evenals automatisering en simulatie (voor training).|
|

Maar wat architectuur betreft, laten we beginnen door elk onderdeel te zien als cumulatieve beveiligingslagen, elk met een speciale nadruk op beveiliging. Ziet er als volgt uit:

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP en Microsoft Defender voor Office 365 en hun relatie tot elkaar, met nadruk op de service, waaronder een notitie voor e-mailverificatie.":::

Hoewel in elk van deze services de nadruk ligt op een doel uit de groep beveiligen, detecteren, onderzoeken en reageren, kunnen***alle** _ services *_elk_** van de doelstellingen bescherming, detectie, onderzoek en reactie uitvoeren.

De kern van Office 365-beveiliging is EOP-beveiliging. Microsoft Defender voor Office 365 P1 bevat EOP. Defender voor Office 365 P2 bevat P1 en EOP. De structuur is cumulatief. Daarom moet u bij het configureren van dit product beginnen met EOP en naar Defender voor Office 365 toewerken.

Hoewel de configuratie van e-mailverificatie plaatsvindt in openbare DNS, is het belangrijk deze functie te configureren ter bescherming tegen spoofing. *Als u EOP hebt,* ***dient u [e-mailverificatie te configureren](email-validation-and-authentication.md)***.

Als u een Office 365 E3 of lager hebt, hebt u EOP, maar met de optie om zelfstandige Defender voor Office 365 P1 te kopen via een upgrade. Als u Office 365 E5 hebt, hebt u al Defender voor Office 365 P2.

> [!TIP]
> Als uw abonnement geen Office 365 E3 of E5 is, kunt u nog steeds controleren of u de optie hebt om een upgrade uit te voeren naar Microsoft Defender voor Office 365 P1. Als u geïnteresseerd bent, vindt u [op deze webpagina](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) abonnementen die in aanmerking komen voor de upgrade van Microsoft Defender voor Office 365 P1 (ga naar het einde van de pagina voor de kleine lettertjes).

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>De Office 365-beveiligingsopbouw van EOP tot aan Microsoft Defender voor Office 365

![EOP en Microsoft Defender voor Office 365 met hun nadruk op beveiliging, van beschermen en detecteren, naar onderzoek doen en reageren. Configuratie van e-mailverificatie (ten minste DKIM en DMARC) moet worden ingesteld voor EOP en hoger.](../../media/tp_EOPATPP1P2Take6.gif#lightbox)

> [!IMPORTANT]
> Informatie over de details op deze pagina's: [Exchange Online Protection](exchange-online-protection-overview.md)en [Defender voor Office 365](defender-for-office-365.md).

Wat het toevoegen van Microsoft Defender voor Office 365-abonnementen als voordeel biedt ten opzichte van puur EOP-bedreigingsbeheer, is op het eerste gezicht moeilijk te zien. Om u te helpen uitzoeken of een upgrade-traject geschikt is voor uw organisatie, bekijken we de mogelijkheden van elk product met betrekking tot:

- bedreigingen voorkomen en detecteren
- onderzoeken
- reageren

te beginnen met **Exchange Online Protection**:
<p>

|Voorkomen/Detecteren|Onderzoeken|Beantwoorden|
|---|---|---|
|De technologieën omvatten:<ul><li>spam</li><li>phishing</li><li>malware</li><li>bulkmail</li><li>adresvervalsingsanalyse</li><li>imitatiedetectie</li><li>Beheerquarantaine</li><li>Indieningen door beheerders en gebruikers van fout-positieven en fout-negatieven</li><li>URL's en bestanden toestaan/blokkeren</li><li>Rapporten</li></u1>|<li>Zoeken in het Auditlogboek</li><li>Berichttracering</li>|<li>Zero-Hour Auto Purge (ZAP)</li><li>De lijsten Toestaan en Blokkeren verfijnen en testen</li>|
|

Als u zich wilt verdiepen in EOP, **[ga dan naar dit artikel](exchange-online-protection-overview.md)**.

Omdat deze producten cumulatief zijn, voegt u deze capaciteiten toe als u Microsoft Defender voor Office 365 P1 evalueert en besluit om een abonnement op dit product te nemen.

Voordelen van **Defender voor Office 365, abonnement 1** (tot nu toe):
<p>

|Voorkomen/Detecteren|Onderzoeken|Beantwoorden|
|---|---|---|
|Technologieën bevatten alles in EOP plus:<u1><li>Veilige bijlagen</li><li>Veilige koppelingen<li>Microsoft Defender voor Office 365-beveiliging voor werkbelastingen (bijvoorbeeld SharePoint Online, Teams, OneDrive voor Bedrijven)</li><li>Time-of-click-beveiliging in e-mail, Office-clients en Teams</li><li>anti-phishing in Defender voor Office 365</li><li>Bescherming tegen gebruikers- en domeinimitatie</li><li>Waarschuwingen en SIEM-integratie-API voor waarschuwingen</li>|<li>SIEM-integratie-API voor detecties</li><li>**Hulpprogramma voor realtimedetectie**</li><li>URL-trace</li>|<li>Dezelfde</li></u1>

Microsoft Defender voor Office 365 P1 biedt uitbreiding aan de ***preventie** _kant en voegt extra vormen van _*_detectie_** toe.

Microsoft Defender voor Office 365 P1 voegt ook **realtime-detecties** toe aan onderzoek. De naam van dit bedreigingsopsporingsmiddel wordt vetgedrukt weergegeven omdat het een duidelijke manier is om *te laten weten dat* u Defender voor Office 365 P1 hebt. Het wordt niet weergegeven in Defender voor Office 365 P2.

Voordelen van **Defender voor Office 365, abonnement 2** (tot nu toe):
<p>

|Voorkomen/Detecteren|Onderzoeken|Beantwoorden|
|---|---|---|
|De technologieën omvatten alles in EOP en Microsoft Defender voor Office 365 P1 plus:<u1><li>Dezelfde</li>|<li>**Bedreigingsverkenner**</li><li>Bedreigingstrackers</li><li>Campagneweergaven</li>|<li>Geautomatiseerd onderzoek en reactie (AIR)</li><li>AIR vanuit Threat Explorer</li><li>AIR voor gecompromitteerde gebruikers</li><li>SIEM-integratie-API voor geautomatiseerd onderzoek</li>

Microsoft Defender voor Office 365 P2 voegt dus toe aan de kant van ***onderzoek en reactie*** en voegt nieuwe opsporingskracht toe. Automatisering.

In Microsoft Defender voor Office 365 P2 wordt het primaire opsporingshulpprogramma **Threat Explorer** genoemd in plaats van realtime-detectie. Als Threat Explorer wordt weergegeven wanneer u naar het beveiligingscentrum navigeert, bevindt u zich in Microsoft Defender voor Office 365 P2.

Als u meer wilt weten over Microsoft Defender voor Office 365 P1 en P2, **[gaat u naar dit artikel](defender-for-office-365.md)**.

> [!TIP]
> EOP en Microsoft Defender voor Office 365 verschillen ook als het gaat over eindgebruikers. In EOP en Defender voor Office 365 P1 ligt de focus op *bewustwording*. Deze twee services bevatten dus de *Outlook-invoegtoepassing bericht rapporteren* zodat gebruikers e-mailberichten kunnen rapporteren die ze verdacht vinden, voor verdere analyse. <p> In Defender voor Office 365 P2 (die alles bevat van EOP en P1) wordt de focus verplaatst naar *verdere training* voor eindgebruikers. Het beveiligingscentrum heeft dus toegang tot een krachtig *bedreigingssimulator* hulpprogramma en de meetwaarden voor eindgebruikers die dat genereert.

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Microsoft Defender voor Office 365 Abonnement 1 versus Abonnement 2-cheatsheet

Deze beknopte informatie geeft inzicht in de mogelijkheden van elk Microsoft Defender voor Office 365-abonnement. Gecombineerd met uw kennis van EOP-functies, kunnen besluitvormers bepalen welke versie van Microsoft Defender voor Office 365 het beste past bij hun behoeften.

|Defender voor Office 365 Abonnement 1|Defender voor Office 365 Abonnement 2|
|---|---|
|Functies voor configuratie, beveiliging en detectie: <ul><li>[Veilige bijlagen](safe-attachments.md)</li><li>[Veilige koppelingen](safe-links.md)</li><li>[Veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams](mdo-for-spo-odb-and-teams.md)</li><li>[Bescherming tegen phishing in Defender voor Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[Detecties in realtime](threat-explorer.md)</li></ul>|Mogelijkheden van Defender voor Office 365 Abonnement 1 <p> --- plus --- <p> Functies voor automatisering, onderzoek, herstel en onderwijs: <ul><li>[Bedreigingsoverzichten](threat-trackers.md)</li><li>[Bedreigingsverkenner](threat-explorer.md)</li><li>[Geautomatiseerd onderzoek en reactie](office-365-air.md)</li><li>[Aanvalssimulator](attack-simulator.md)</li></ul>|
|

- Abonnement 2 voor Microsoft Defender voor Office 365 is inbegrepen in Office 365 E5, Office 365 A5 en Microsoft 365 E5.

- Abonnement 1 voor Microsoft Defender voor Office 365 is inbegrepen in Microsoft 365 Business Premium.

- Abonnement 1 voor Microsoft Defender voor Office 365 en abonnement 2 voor Microsoft Defender voor Office 365 zijn elk beschikbaar als een invoegtoepassing voor bepaalde abonnementen. Raadpleeg voor meer informatie [Beschikbaarheid van functies in Microsoft Defender voor Office 365-abonnementen](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- De functie [Veilige documenten](safe-docs.md) is alleen beschikbaar voor gebruikers met een Microsoft 365 E5- of Microsoft 365 E5 Security-licentie (niet opgenomen in abonnementen voor Microsoft Defender voor Office 365).

- Als u huidige abonnement Microsoft Defender voor Office 365 niet bevat, [neem dan contact op met de verkoopafdeling voor een proefabonnement](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html) en bekijk hoe Defender voor Office 365 werkt voor uw organisatie.

> [!TIP]
> ***Insidertip** _. U kunt de docs.microsoft.com-inhoudsopgave gebruiken voor meer informatie over EOP en Microsoft Defender voor Office 365. Ga terug naar deze pagina, [overzicht van Office 365-beveiliging](index.yml), en u vindt de inhoudsopgave georganiseerd in de zijbalk. Het begint met de implementatie (inclusief migratie) en gaat vervolgens verder met preventie, detectie, onderzoek en reactie. <p> Deze structuur is zo verdeeld dat de _ *Beveiligingsbeheer** onderwerpen worden gevolgd door onderwerpen over **beveiligingsbewerkingen**. Als u nieuw bent in een van deze twee functies, gebruikt u de koppeling in deze tip en uw kennis van de inhoudsopgave om zich dit onderwerp eigen te maken. Vergeet niet om *feedbackkoppelingen* te gebruiken en terwijl u dat doet *de artikelen een beoordeling te geven*. Feedback helpt ons onze producten te verbeteren.

## <a name="where-to-go-next"></a>Volgende stap

Als u een beveiligingsbeheerder bent, moet u mogelijk DKIM of DMARC configureren voor uw e-mail. Mogelijk wilt u 'Strikte' beveiligingsinstellingen voor uw gebruikers met prioriteit gebruiken of kijken wat er nieuw is in het product. Of als u onderdeel uitmaakt van Security Operations, kunt u gebruikmaken van realtime detecties of Threat Explorer om onderzoek te doen en te reageren, of om detectie voor eindgebruikers te oefenen met Aanvalssimulatie. In beide gevallen ziet u hier enkele extra aanbevelingen voor de volgende stap.

[E-mailverificatie, inclusief SPF, DKIM en DMARC (met koppelingen naar het instellen van alle drie)](email-validation-and-authentication.md)

[Bekijk de specifieke aanbevolen configuratie van](recommended-settings-for-eop-and-office365.md) en [om snel beveiligingsbeleid te configureren met de aanbevolen standaardinstellingen](preset-security-policies.md)

Op de hoogte blijven van [nieuwe functies in Microsoft Defender voor Office 365 (inclusief EOP-ontwikkelingen)](whats-new-in-defender-for-office-365.md)

[Threat Explorer of realtime detecties gebruiken](threat-explorer.md)

De [Attack Simulator in Microsoft Defender voor Office 365](attack-simulator.md) gebruiken