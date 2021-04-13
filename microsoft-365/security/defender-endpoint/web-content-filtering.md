---
title: Filteren van webinhoud
description: Gebruik webinhoudsfilters in Microsoft Defender voor Eindpunt om de toegang tot websites bij te houden en te reguleren op basis van hun inhoudscategorieën.
keywords: webbeveiliging, bescherming tegen webdreigingen, surfen op het web, monitoring, rapporten, kaarten, domeinlijst, beveiliging, phishing, malware, exploit, websites, netwerkbeveiliging, Edge, Internet Explorer, Chrome, Firefox, webbrowser
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c9a069deded237c5ded6bcd9f6c6a77f644e65a2
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689339"
---
# <a name="web-content-filtering"></a>Filteren van webinhoud

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> **Filteren van webinhoud is momenteel beschikbaar in een openbare preview**<br>
> Deze preview-versie wordt geleverd zonder serviceovereenkomst en wordt niet aanbevolen voor productiebelastingen. Bepaalde functies worden mogelijk niet ondersteund of hebben mogelijk beperkte mogelijkheden.
> Zie De preview-functies [van Microsoft Defender voor Eindpunt voor meer informatie.](preview.md)

>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Filteren van webinhoud maakt deel uit van de mogelijkheden voor [webbeveiliging](web-protection-overview.md) in Microsoft Defender voor Eindpunt. Hiermee kan uw organisatie de toegang tot websites bijhouden en reguleren op basis van hun inhoudscategorieën. Veel van deze websites, hoewel niet schadelijk, kunnen problematisch zijn vanwege nalevingsregels, bandbreedtegebruik of andere problemen.

Configureer beleidsregels voor uw apparaatgroepen om bepaalde categorieën te blokkeren. Als u een categorie blokkeert, wordt voorkomen dat gebruikers binnen bepaalde apparaatgroepen toegang krijgen tot URL's die aan de categorie zijn gekoppeld. Voor elke categorie die niet is geblokkeerd, worden de URL's automatisch gecontroleerd. Uw gebruikers hebben zonder onderbreking toegang tot de URL's en u verzamelt toegangsstatistieken om een meer aangepaste beleidsbeslissing te maken. Uw gebruikers zien een blokkeringsmelding als een element op de pagina die ze bekijken oproepen doet naar een geblokkeerde resource.

Filteren van webinhoud is beschikbaar in de belangrijkste webbrowsers, met blokken die worden uitgevoerd door Windows Defender SmartScreen (Microsoft Edge) en Netwerkbeveiliging (Chrome, Firefox, Moedig en Opera). Zie de sectie Vereisten voor meer informatie over browserondersteuning.

Een overzicht van de voordelen:

- Gebruikers kunnen geen toegang krijgen tot websites in geblokkeerde categorieën, ongeacht of ze on-premises of weg browsen
- Beleid eenvoudig implementeren voor groepen gebruikers met apparaatgroepen die zijn gedefinieerd in instellingen voor toegangscontrole op basis van rollen van [Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac) voor eindpunt
- Toegang tot webrapporten op dezelfde centrale locatie, met zichtbaarheid over werkelijke blokken en webgebruik

## <a name="user-experience"></a>Gebruikerservaring

De blokkeringservaring voor ondersteunde browsers van derden wordt geleverd door Netwerkbeveiliging, waarmee de gebruiker op systeemniveau wordt op de hoogte gesteld van een geblokkeerde verbinding. 

Voor een gebruiksvriendelijkere in-browserervaring kunt u microsoft Edge gebruiken.

## <a name="prerequisites"></a>Vereisten

Voordat u deze functie uit probeert, moet u de volgende vereisten hebben:

- Windows 10 Enterprise E5, Microsoft 365 E5, Microsoft 365 E5-beveiliging, Microsoft 365 E3 + Microsoft 365 E5-beveiligingsuitvoeging of de zelfstandige licentie voor Microsoft Defender voor Eindpunt. 
- Toegang tot microsoft Defender-beveiligingscentrumportal
- Apparaten met Windows 10 Jubileumupdate (versie 1607) of hoger met de nieuwste MoCAMP-update.

Als SmartScreen van Windows Defender niet is ingeschakeld, neemt Netwerkbeveiliging de blokkering over. Hiervoor moet [netwerkbeveiliging op](enable-network-protection.md) het apparaat worden inschakelen. Chrome, Firefox, Brave en Opera zijn momenteel browsers van derden waarin deze functie is ingeschakeld.

## <a name="data-handling"></a>Gegevensverwerking

We volgen de regio die u hebt gekozen om te gebruiken als onderdeel van uw instellingen voor gegevensafhandeling van Microsoft Defender voor [eindpunten.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/data-storage-privacy) Uw gegevens verlaten het datacenter niet in die regio. Bovendien worden uw gegevens niet gedeeld met derden, inclusief onze gegevensproviders.

## <a name="turn-on-web-content-filtering"></a>Filteren van webinhoud inschakelen

Selecteer in het linkernavigatiemenu Instellingen **> Algemene > Geavanceerde functies.** Schuif omlaag totdat u de vermelding voor filteren **van webinhoud ziet.** Schakel de wisselknop in **op Voorkeuren voor Aan** en **Opslaan.**

### <a name="configure-web-content-filtering-policies"></a>Filterbeleid voor webinhoud configureren

Filterbeleid voor webinhoud geeft aan welke sitecategorieën worden geblokkeerd op welke apparaatgroepen. Als u het beleid wilt beheren, gaat u naar **Instellingen > regels > filteren van webinhoud.**

Gebruik het filter om beleid te zoeken dat bepaalde geblokkeerde categorieën bevat of die worden toegepast op specifieke apparaatgroepen.

### <a name="create-a-policy"></a>Een beleid maken

Een nieuw beleid toevoegen:

1. Selecteer **Beleid toevoegen** op de **filterpagina voor webinhoud** in **Instellingen.**
2. Geef een naam op.
3. Selecteer de categorieën die u wilt blokkeren. Gebruik het pictogram Uitv om elke bovenliggende categorie volledig uit te vouwen en specifieke webinhoudscategorieën te selecteren.
4. Geef het beleidsbereik op. Selecteer de apparaatgroepen om op te geven waar u het beleid wilt toepassen. Alleen apparaten in de geselecteerde apparaatgroepen kunnen geen toegang krijgen tot websites in de geselecteerde categorieën.
5. Bekijk de samenvatting en sla het beleid op. Het kan maximaal 2 uur duren voordat de beleidsvernieuwing van toepassing is op de geselecteerde apparaten.

Tip: U kunt een beleid implementeren zonder een categorie in een apparaatgroep te selecteren. Met deze actie wordt een beleid voor alleen controle uitgevoerd, om u te helpen het gedrag van gebruikers te begrijpen voordat u een blokbeleid maakt.

>[!NOTE]
>Als u een beleid verwijdert of tegelijkertijd apparaatgroepen verandert, kan dit leiden tot vertraging bij de beleidsimplementatie.

>[!IMPORTANT]
>Het blokkeren van de categorie 'Niet-gecategoriseerd' kan leiden tot onverwachte en ongewenste resultaten.  

### <a name="allow-specific-websites"></a>Specifieke websites toestaan

U kunt de geblokkeerde categorie in het filteren van webinhoud overschrijven om één site toe te staan door een aangepast indicatorbeleid te maken. Het aangepaste indicatorbeleid zal het filterbeleid voor webinhoud overbodig maken wanneer dit wordt toegepast op de apparaatgroep in kwestie.

1. Een aangepaste indicator maken in het Microsoft Defender-beveiligingscentrum door naar **URL**  >  **instellingenindicatoren/item**  >  **voor domein** toevoegen te  >  **gaan**
2. Voer het domein van de site in
3. Stel de beleidsactie in op **Toestaan.**  

### <a name="reporting-inaccuracies"></a>Onnauwkeurigheden rapporteren

Als u een domein tegenkomt dat onjuist is gecategoriseerd, kunt u onnauwkeurigheden rechtstreeks aan ons rapporteren via de pagina Rapporten van webinhoudsfilters. Deze functie is alleen beschikbaar in het nieuwe Microsoft 365-beveiligingscentrum (security.microsoft.com).

Als u een onnauwkeurigheid wilt rapporteren, gaat u naar Rapporten > webbeveiliging > **webinhoudfilterdetails > Domeinen.** Op het tabblad Domeinen van onze rapporten voor het filteren van webinhoud ziet u een beletselteken naast elk van de domeinen. Plaats de muisaanwijzer op dit beletselteken en selecteer **Onnauwkeurigheid van rapport.**

Er wordt een deelvenster geopend waarin u de prioriteit kunt selecteren en aanvullende details kunt toevoegen, zoals de voorgestelde categorie voor hercategorisatie. Wanneer u het formulier hebt voltooid, selecteert u **Verzenden.** Ons team bekijkt de aanvraag binnen één werkdag. Als u de blokkering direct wilt opheffen, maakt u een [aangepaste indicator voor toestaan.](indicator-ip-domain.md)

## <a name="web-content-filtering-cards-and-details"></a>Filterkaarten en details voor webinhoud

Selecteer **Rapporten > webbeveiliging om** kaarten weer te geven met informatie over het filteren van webinhoud en beveiliging tegen webdreigingen. De volgende kaarten bevatten overzichtsinformatie over het filteren van webinhoud.

### <a name="web-activity-by-category"></a>Webactiviteit per categorie

Deze kaart bevat de bovenliggende webinhoudscategorieën met de grootste toename of afname van het aantal toegangspogingen. Inzicht in drastische wijzigingen in webactiviteitspatronen in uw organisatie van de afgelopen 30, 3 maanden of 6 maanden. Selecteer een categorienaam om meer informatie weer te geven.

In de eerste 30 dagen na het gebruik van deze functie heeft uw organisatie mogelijk niet genoeg gegevens om deze gegevens weer te geven.

![Afbeelding van webactiviteit per categoriekaart](images/web-activity-by-category600.png)

### <a name="web-content-filtering--summary-card"></a>Overzichtskaart voor het filteren van webinhoud

Op deze kaart wordt de verdeling weergegeven van geblokkeerde toegangspogingen over de verschillende bovenliggende webinhoudscategorieën. Selecteer een van de gekleurde balken om meer informatie over een specifieke bovenliggende webcategorie weer te geven.

![Afbeelding van overzichtskaart voor filteren van webinhoud](images/web-content-filtering-summary.png)

### <a name="web-activity-summary-card"></a>Overzichtskaart voor webactiviteit

Op deze kaart wordt het totale aantal aanvragen voor webinhoud in alle URL's weergegeven.

![Afbeelding van overzichtskaart voor webactiviteit](images/web-activity-summary.png)

### <a name="view-card-details"></a>Kaartdetails weergeven

U kunt de details **van het rapport voor** elke kaart openen door een tabelrij of gekleurde balk te selecteren in de grafiek op de kaart. De pagina rapportdetails voor elke kaart bevat uitgebreide statistische gegevens over categorieën webinhoud, websitedomeinen en apparaatgroepen.

![Afbeelding van de details van het webbeveiligingsrapport](images/web-protection-report-details.png)

- **Webcategorieën:** bevat de categorieën webinhoud die toegangspogingen hebben gehad in uw organisatie. Selecteer een specifieke categorie om een samenvattings fly-out te openen.

- **Domeinen:** bevat de webdomeinen die zijn toegankelijk of geblokkeerd in uw organisatie. Selecteer een specifiek domein om gedetailleerde informatie over dat domein weer te geven.

- **Apparaatgroepen:** bevat alle apparaatgroepen die webactiviteit hebben gegenereerd in uw organisatie

Gebruik het tijdbereikfilter linksboven op de pagina om een periode te selecteren. U kunt de gegevens ook filteren of de kolommen aanpassen. Selecteer een rij om een flyoutvenster te openen met nog meer informatie over het geselecteerde item.

## <a name="errors-and-issues"></a>Fouten en problemen

### <a name="limitations-and-known-issues-in-this-preview"></a>Beperkingen en bekende problemen in dit voorbeeld

- Alleen Microsoft Edge wordt ondersteund als de besturingssysteemconfiguratie van uw apparaat Server is (cmd > Systeminfo > osconfiguratie). Netwerkbeveiliging wordt alleen ondersteund in de controlemodus op Serverapparaten, die verantwoordelijk is voor het beveiligen van verkeer in ondersteunde browsers van derden.

- Niet-toegewezen apparaten bevatten onjuiste gegevens in het rapport. In de rapportdetails > draait u mogelijk een rij met een leeg veld Apparaatgroep. Deze groep bevat uw niet-toegewezen apparaten voordat ze in de opgegeven groep worden gezet. Het rapport voor deze rij bevat mogelijk geen nauwkeurig aantal apparaten of toegangstellingen.

- Rapporten voor webinhoudsfilters zijn momenteel beperkt tot het weergeven van de 5000 beste records. In het rapport 'Domeinen' wordt bijvoorbeeld alleen een maximum van de bovenste 5000 domeinen voor een bepaalde filterquery, indien van toepassing, gegeven. 

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht webbeveiliging](web-protection-overview.md)
- [Webbedreigingsbeveiliging](web-threat-protection.md)
- [Webbeveiliging monitoren](web-protection-monitoring.md)
- [Reageren op webbedreigingen](web-protection-response.md)
