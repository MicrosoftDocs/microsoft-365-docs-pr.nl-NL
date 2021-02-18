---
title: Office 365-beveiliging, Microsoft Defender voor Office 365, EOP, MSDO
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
- M365-security-compliance
- m365initiative-defender-office365
description: Beveiliging in Office 365, van EOP tot Defender voor Office 365-abonnementen 1 en 2, Standard versus strikte beveiligingsconfiguraties en meer. Begrijp wat u hebt en hoe u uw eigenschappen kunt beveiligen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cbe95946ab7214efded8feca39578c364b948df0
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287899"
---
# <a name="office-365-security-overview"></a>Beveiligingsoverzicht van Office 365

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)


In dit artikel maakt u kennis met uw nieuwe beveiligingseigenschappen in de cloud. Of u nu deel uitmaakt van een Beveiligings operations Center, u bent voor het eerst beveiligingsbeheerder of u wilt de ruimte opfrisser, laten we aan de slag gaan.

> [!CAUTION]
> Als u **Outlook.com,** Microsoft **365 Family** of **Microsoft 365 Personal**  gebruikt en  veilige koppelingen of veilige bijlagen nodig ***hebt,*** klikt u op deze koppeling: Geavanceerde Outlook.com-beveiliging voor [Microsoft 365-abonnees.](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)

## <a name="office-365-security-spelled-out"></a>Office 365-beveiligings spellen

Elk Office 365-abonnement heeft beveiligingsmogelijkheden. De doelen en acties die u kunt ondernemen, zijn afhankelijk van de focus van deze verschillende abonnementen. In de beveiliging van Office 365 zijn er drie belangrijkste beveiligingsservices (of producten) die zijn gekoppeld aan uw abonnementstype:

1. Exchange Online Protection (EOP)
1. Microsoft Defender voor Office 365-abonnement 1 (Defender voor Office P1)
1. Microsoft Defender voor Office 365 Abonnement 2 (Defender voor Office P2)

> [!NOTE]
> Als u uw abonnement hebt gekocht en nu beveiligingsfuncties moet uitrollen, gaat u verder met de stappen in het artikel [Beveiligen tegen](protect-against-threats.md) bedreigingen. Als u nog niet bekend bent met uw abonnement en uw licentie wilt weten voordat u begint, bladert u naar Facturering > Uw producten in het [Microsoft 365-beheercentrum.](https://admin.microsoft.com/AdminPortal/#/homepage)

Office 365-beveiligings builds op basis van de basisbeveiligingen die door EOP worden aangeboden. EOP is aanwezig in elk abonnement waarin Exchange Online-postvakken kunnen worden gevonden (vergeet niet dat alle beveiligingsproducten die hier worden besproken, het Cloud-product zijn).

Mogelijk bent u gewend om deze drie onderdelen op deze manier te bespreken:

|EOP|Microsoft Defender voor Office 365 P1|Microsoft Defender voor Office 365 P2|
|---|---|---|
|Hiermee voorkomt u algemene, volumegebaseerde, bekende aanvallen.|Beschermt e-mail en samenwerking tegen nuldags malware, phish en zakelijke e-mailcompromitteerd.|Voegt onderzoek na inbreuk, zoeken en antwoorden toe, evenals automatisering en automatisering (voor training).|
|

Maar laten we wat betreft de architectuur eerst elk stukje als cumulatieve beveiligingslagen zien, met elk extra nadruk op de beveiliging. Meer:

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP en Microsoft Defender voor Office 365 en hun relaties met elkaar benadrukken de service, waaronder een notitie voor e-mailverificatie.":::

Hoewel elk van deze services een doel benadrukt tussen beveiligen, detecteren, onderzoeken en reageren,***** alle _ de services *_kunnen_* worden uitgevoerd _ elk * van de doelen voor beveiligen, detecteren, onderzoeken en beantwoorden.

De kern van de Office 365-beveiliging is EOP-beveiliging. Microsoft Defender voor Office 365 P1 bevat EOP. Defender voor Office 365 P2 bevat P1 en EOP. De structuur is cumulatief. Daarom moet u bij het configureren van dit product beginnen met EOP en werken met Defender voor Office 365.

Hoewel de configuratie van e-mailverificatie plaatsvindt in openbare DNS, is het belangrijk dat u deze functie configureert om u te helpen beschermen tegen spoofing. *Als u EOP hebt,* ***moet u [e-mailverificatie configureren.](email-validation-and-authentication.md)***

Als u een Office 365 E3 of lager hebt, hebt u EOP, maar kunt u een zelfstandige Defender voor Office 365 P1 kopen via de upgrade. Als u Office 365 E5 hebt, hebt u al Defender voor Office 365 P2.

> [!TIP]
> Als uw abonnement niet Office 365 E3 of E5 is, kunt u nog steeds controleren of u de optie hebt om een upgrade uit te voeren naar Microsoft Defender voor Office 365 P1. Als u geïnteresseerd bent, vindt u op deze [webpagina](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) abonnementen die in aanmerking komen voor de upgrade van Microsoft Defender voor Office 365 P1 (controleer het einde van de pagina voor de kleine lettertjes).

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>De beveiligingsupdate van Office 365 van EOP naar Microsoft Defender voor Office 365

![EOP en Microsoft Defender voor Office 365 en hun beveiligingsnadruk, die gaan van beveiligen en detecteren om te onderzoeken en reageren. De configuratie van e-mailverificatie (ten minste DKIM en DMARC) moet worden ingesteld voor EOP en up.](../../media/tp_EOPATPP1P2Take6.gif#lightbox)

> [!IMPORTANT]
> Meer informatie over deze pagina's: [Exchange Online Protection](exchange-online-protection-overview.md)en Defender voor Office [365.](office-365-atp.md)

Waardoor het toevoegen van Microsoft Defender voor Office 365-abonnementen een voordeel is van puur risicobeheer voor EOP, is dit in eerste instantie moeilijk te zien. Als u wilt weten of een upgradepad juist is voor uw organisatie, kijken we wat de mogelijkheden van elk product zijn als het gaat om:

- bedreigingen voorkomen en detecteren
- wordt onderzocht
- reageren

te beginnen met **Exchange Online Protection:**
<p>

|Voorkomen/detecteren|Onderzoeken|Beantwoorden|
|---|---|---|
|De technologieën omvatten:<ul><li>spam</li><li>phish</li><li>malware</li><li>bulkmail</li><li>spoof intelligence</li><li>imitatiedetectie</li><li>Admin Quarantine</li><li>Inzendingen door beheerders en gebruikers van fout-positieven en fout-negatieven</li><li>URL's en bestanden toestaan/blokkeren</li><li>Rapporten</li></u1>|<li>Zoeken in auditlogboek</li><li>Bericht traceren</li>|<li>Zero-hour Auto-Purge (ZAP)</li><li>De lijsten toestaan en blokkeren verfijnen en testen</li>|
|

Als u zich in EOP wilt graven, **[gaat u naar dit artikel.](exchange-online-protection-overview.md)**

Omdat deze producten cumulatief zijn, voegt u deze mogelijkheden toe als u Microsoft Defender voor Office 365 P1 evalueert en besluit een abonnement op dit product te nemen.

Winsten met **Defender voor Office 365, Abonnement 1** (tot nu toe):
<p>

|Voorkomen/detecteren|Onderzoeken|Beantwoorden|
|---|---|---|
|Technologieën omvatten alles in EOP plus:<u1><li>Veilige bijlagen</li><li>Veilige koppelingen<li>Microsoft Defender voor Office 365-beveiliging voor werkbelastingen (bijvoorbeeld. SharePoint Online, Teams, OneDrive voor Bedrijven)</li><li>Time-of-click-beveiliging in e-mail, Office-clients en Teams</li><li>anti-phishing in Defender voor Office 365</li><li>Beveiliging tegen imitatie van gebruikers en domeinen</li><li>Waarschuwingen en SIEM-integratie-API voor waarschuwingen</li>|<li>SIEM-integratie-API voor detecties</li><li>**Hulpprogramma voor realtimedetectie**</li><li>URL-trace</li>|<li>Zelfde</li></u1>

Microsoft Defender voor Office 365 P1 wordt dus uitgebreid aan de **kant** van * preventie _ van huis en voegt extra vormen van __*_ detectie **toe.

Microsoft Defender voor Office 365 P1 voegt ook **realtime detecties toe voor** onderzoeken. De naam van dit hulpprogramma voor bedreigingszoeken is  vetgedrukt, omdat u met Defender voor Office 365 P1 kunt werken. De functie wordt niet weergegeven in Defender voor Office 365 P2.

Winsten met **Defender voor Office 365, Abonnement 2** (tot nu toe):
<p>

|Voorkomen/detecteren|Onderzoeken|Beantwoorden|
|---|---|---|
|Technologieën omvatten alles in EOP en Microsoft Defender voor Office 365 P1 plus:<u1><li>Zelfde</li>|<li>**Bedreigingsverkenner**</li><li>Bedreigingsoverzichten</li><li>Campagneweergaven</li>|<li>Automated Investigation and Response (AIR)</li><li>AIR van Threat Explorer</li><li>AIR voor gecompromitteerde gebruikers</li><li>SIEM Integration API for Automated Investigations</li>

Microsoft Defender voor Office 365 P2  breidt het onderzoek en de reactie van het huis uit en voegt een nieuwe zoeksterkte toe. Automatisering.

In Microsoft Defender voor Office 365 P2  wordt het primaire hulpprogramma voor zoeken Bedreigingsverkenner genoemd in plaats van realtime detecties. Als u Bedreigingsverkenner ziet wanneer u naar het beveiligingscentrum navigeert, gebruikt u Microsoft Defender voor Office 365 P2.

Ga naar dit artikel voor meer informatie over Microsoft Defender voor Office 365 P1 **[en](office-365-atp.md)** P2.

> [!TIP]
> EOP en Microsoft Defender voor Office 365 verschillen ook voor eindgebruikers. In EOP en Defender voor Office 365 P1 *ligt* de focus op informatie, dus deze twee services bevatten de *Outlook-invoegversie* Rapport, zodat gebruikers e-mails die ze verdacht vinden, kunnen rapporteren voor verdere analyse. <p> In Defender voor Office 365 P2 (dat alles bevat in EOP en P1), wordt de focus verschuift naar verdere *training* voor eindgebruikers, zodat het Beveiligings operations Center toegang heeft tot een krachtig hulpprogramma *Threat Simulator* en de meetgegevens van de eindgebruiker.

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Microsoft Defender voor Office 365-abonnement 1 versus cheatsheet voor Abonnement 2

Deze snelzoekbalk helpt u inzicht te krijgen in de mogelijkheden die elk Microsoft Defender voor Office 365-abonnement biedt. In combinatie met uw kennis van EOP-functies kunnen besluitvormers bepalen wat Microsoft Defender voor Office 365 het beste is voor hun behoeften.

|Defender voor Office 365-abonnement 1|Defender voor Office 365 -abonnement 2|
|---|---|
|Functies voor configuratie, beveiliging en detectie: <ul><li>[Veilige bijlagen](atp-safe-attachments.md)</li><li>[Veilige koppelingen](atp-safe-links.md)</li><li>[Veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams](atp-for-spo-odb-and-teams.md)</li><li>[Anti-phishingbeveiliging in Defender voor Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[Detecties in realtime](threat-explorer.md)</li></ul>|Mogelijkheden van Defender voor Office 365 Abonnement 1 <p> --- plus --- <p> Functies voor automatisering, onderzoek, herstel en onderwijs: <ul><li>[Bedreigingsoverzichten](threat-trackers.md)</li><li>[Bedreigingsverkenner](threat-explorer.md)</li><li>[Geautomatiseerd onderzoek en reactie](office-365-air.md)</li><li>[Aanvalssimulator](attack-simulator.md)</li></ul>|
|

- Microsoft Defender voor Office 365 Abonnement 2 is opgenomen in Office 365 E5, Office 365 A5 en Microsoft 365 E5.

- Abonnement 1 voor Microsoft Defender voor Office 365 is inbegrepen in Microsoft 365 Business Premium.

- Microsoft Defender voor Office 365 Abonnement 1 en Defender voor Office 365 Plan 2 zijn elk beschikbaar als een invoegabonnement voor bepaalde abonnementen. Voor meer informatie, is hier nog een koppeling [functiebeschikbaarheid in Microsoft Defender voor Office 365-abonnementen.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)

- De functie [Veilige documenten](safe-docs.md) is alleen beschikbaar voor gebruikers met een Microsoft 365 E5- of Microsoft 365 E5 Security-licentie (niet opgenomen in abonnementen voor Microsoft Defender voor Office 365).

- Als Microsoft Defender voor Office 365 niet is opgenomen in uw huidige abonnement en u dit wilt, neemt u [contact](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html)op met Verkoop om een proefabonnement te starten en te ontdekken hoe Microsoft Defender voor Office 365 kan werken in uw organisatie.

> [!TIP]
> ***Insider-tip** _. U kunt de inhoudsopgave docs.microsoft.com informatie over EOP en Microsoft Defender voor Office 365. Ga terug naar deze pagina, [Office 365-beveiligingsoverzicht,](index.md)en u ziet dat de organisatie van de inhoudsopgave in de zijbalk staat. De toepassing begint met de implementatie (inclusief migratie) en gaat vervolgens verder met preventie, detectie, onderzoek en antwoorden. <p> Deze structuur is zo verdeeld dat onderwerpen over _ *Beveiligingsbeheer** worden gevolgd door **onderwerpen over** beveiligingsbewerkingen. Als u een nieuw lid van een functie bent, gebruikt u de koppeling in deze tip en uw kennis van de inhoudsopgave om de ruimte beter te leren leren. Vergeet niet om *feedbackkoppelingen en* *beoordeelartikelen te* gebruiken terwijl u al aan het werk bent. Feedback helpt ons bij het verbeteren van wat we u bieden.

## <a name="where-to-go-next"></a>Waar moet ik nu naartoe gaan

Als u een beveiligingsbeheerder bent, moet u mogelijk DKIM of DMARC configureren voor uw e-mail. Mogelijk wilt u strikte beveiligingsinstellingen voor uw prioriteitsgebruikers uitrollen of op zoek gaan naar nieuwe functies in het product. Als u met Security Ops werkt, kunt u gebruikmaken van realtime detecties of Bedreigingsverkenner om dit te onderzoeken en te beantwoorden, of de detectie voor eindgebruikers trainen met Attack Simulator. Hier volgen enkele aanvullende aanbevelingen voor de volgende stap.

[E-mailverificatie, met inbegrip van SPF, DKIM en DMARC (met koppelingen naar het instellen van deze drie)](email-validation-and-authentication.md)

[Bekijk de specifieke aanbevolen 'gouden' configs](recommended-settings-for-eop-and-office365-atp.md) en gebruik de aanbevolen vooraf ingestelde instellingen om [snel beveiligingsbeleid te configureren](preset-security-policies.md)

Zie wat [er nieuw is in Microsoft Defender voor Office 365 (inclusief de ontwikkeling van EOP)](whats-new-in-office-365-atp.md)

[Bedreigingsverkenner of realtime detecties gebruiken](threat-explorer.md)

Attack [Simulator gebruiken in Microsoft Defender voor Office 365](attack-simulator.md)
