---
title: Veilige bijlagen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- seo-marvel-apr2020
description: Beheerders kunnen meer informatie over de functie Safe bijlagen in Microsoft Defender voor Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cc5fabf7b0bb4a649aeb7c4e09155037fc09e9f9
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625003"
---
# <a name="safe-attachments-in-microsoft-defender-for-office-365"></a>Safe Bijlagen in Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Safe Bijlagen in [Microsoft Defender voor Office 365](defender-for-office-365.md) biedt een extra beveiligingslaag voor e-mailbijlagen die al zijn gescand door [anti-malwarebeveiliging in Exchange Online Protection (EOP).](anti-malware-protection.md) In Safe bijlagen wordt een virtuele omgeving gebruikt om bijlagen in e-mailberichten te controleren voordat ze worden bezorgd bij geadresseerden (een proces dat detonatie _wordt genoemd)._

Safe De beveiliging van bijlagen voor e-mailberichten wordt bepaald Safe bijlagenbeleid. Er is geen standaardbeleid Safe bijlagen, dus als u de beveiliging van Safe Bijlagen wilt krijgen, moet u een of meer Safe **Bijlagen-beleid maken.** Zie Het [beleid Safe bijlagen instellen in Defender](set-up-safe-attachments-policies.md)voor Office 365.

In de volgende tabel worden scenario's beschreven voor Safe Bijlagen in Microsoft 365 en Office 365-organisaties met Microsoft Defender voor Office 365 (met andere woorden: een gebrek aan licenties is nooit een probleem in de voorbeelden).

<br>

****

|Scenario|Resultaat|
|---|---|
|De organisatie van Pat Microsoft 365 E5 heeft geen Safe bijlagen geconfigureerd.|Pat is niet beveiligd door Safe bijlagen. <p> Een beheerder moet ten minste één Safe bijlagenbeleid maken om Safe bijlagen te kunnen beschermen om actief te zijn. Bovendien moeten de voorwaarden van het beleid Pat bevatten als Pat moet worden beschermd door Safe bijlagen.|
|De organisatie van Lee heeft een Safe bijlagenbeleid dat alleen van toepassing is op werknemers financieren. Lee is lid van de verkoopafdeling.|Lee is niet beveiligd door Safe bijlagen. <p> Financiële werknemers worden beschermd door Safe bijlagen, maar verkoopmedewerkers (en andere werknemers) niet.|
|Gisteren heeft een beheerder in de organisatie van Jean een Safe bijlagebeleid gemaakt dat van toepassing is op alle werknemers. Eerder vandaag heeft Jean een e-mailbericht ontvangen met een bijlage.|Jean wordt beschermd door Safe bijlagen. <p> Meestal duurt het ongeveer 30 minuten voordat een nieuw beleid van kracht wordt.|
|De organisatie van Chris heeft al lange tijd Safe bijlagenbeleid voor iedereen in de organisatie. Chris ontvangt een e-mailbericht met een bijlage en stuurt het bericht door naar externe geadresseerden.|Chis wordt beveiligd door Safe bijlagen. <p> Als de externe geadresseerden ook een Safe in hun organisatie hebben, zijn de doorgestuurde berichten onderworpen aan dit beleid.|
|

Safe Het scannen van bijlagen vindt plaats in dezelfde regio waar uw Microsoft 365 gegevens zich bevindt. Zie Waar bevinden uw gegevens zich? voor meer informatie over geografie van [datacenters.](https://products.office.com/where-is-your-data-located?geo=All)

> [!NOTE]
> De volgende functies bevinden zich in de algemene instellingen van Safe bijlagenbeleid in het beveiligings- & compliancecentrum. Deze instellingen zijn echter globaal ingeschakeld of uitgeschakeld en vereisen geen Safe bijlagen:
>
> - [Safe bijlagen voor SharePoint, OneDrive en Microsoft Teams.](mdo-for-spo-odb-and-teams.md)
> - [Veilige documenten in Microsoft 365 E5](safe-docs.md)

## <a name="safe-attachments-policy-settings"></a>Safe Instellingen voor bijlagenbeleid

In deze sectie worden de instellingen beschreven in Safe bijlagenbeleid:

- **Safe Attachments unknown malware response**: Deze instelling bepaalt de actie voor het Safe Malware scannen van bijlagen in e-mailberichten. De beschikbare opties worden in de volgende tabel beschreven:

  <br>

  ****

  |Optie|Effect|Gebruik het volgende wanneer u het volgende wilt doen:|
  |---|---|---|
  |**Uit**|Bijlagen worden niet gescand op malware door Safe bijlagen. Berichten worden nog steeds gescand op malware door [anti-malwarebeveiliging in EOP.](anti-malware-protection.md)|Het scannen uitschakelen voor geselecteerde geadresseerden. <p> Voorkom onnodige vertragingen bij het routeren van interne e-mail. <p> **Deze optie wordt niet aanbevolen voor de meeste gebruikers. Gebruik deze optie alleen om het scannen Safe bijlagen uit te schakelen voor geadresseerden die alleen berichten ontvangen van vertrouwde afzenders.**|
  |**Monitor**|Bezorgt berichten met bijlagen en houdt bij wat er gebeurt met gedetecteerde malware. <p> De bezorging van veilige berichten kan worden vertraagd doordat Safe bijlagen worden gescand.|Bekijk waar gedetecteerde malware in uw organisatie wordt gebruikt.|
  |**Blokkeren**|Voorkomt dat berichten met gedetecteerde malwarebijlagen worden bezorgd. <p> Berichten worden [in quarantaine](manage-quarantined-messages-and-files.md) geplaatst waar alleen beheerders (niet eindgebruikers) de berichten kunnen controleren, vrijgeven of verwijderen. <p> Toekomstige exemplaren van de berichten en bijlagen worden automatisch blokkeert. <p> De bezorging van veilige berichten kan worden vertraagd doordat Safe bijlagen worden gescand.|Beschermt uw organisatie tegen herhaalde aanvallen met dezelfde malwarebijlagen. <p> Dit is de standaardwaarde en de aanbevolen waarde in standaard- en strikt [vooraf ingestelde beveiligingsbeleidsregels.](preset-security-policies.md)|
  |**Vervangen**|Hiermee verwijdert u gedetecteerde malwarebijlagen. <p> Geadresseerden krijgen een bericht dat bijlagen zijn verwijderd. <p>  Berichten worden [in quarantaine](manage-quarantined-messages-and-files.md) geplaatst waar alleen beheerders (niet eindgebruikers) de berichten kunnen controleren, vrijgeven of verwijderen. <p> De bezorging van veilige berichten kan worden vertraagd doordat Safe bijlagen worden gescand.|Verhecht de zichtbaarheid van geadresseerden dat bijlagen zijn verwijderd vanwege gedetecteerde malware.|
  |**Dynamische bezorging**|Berichten worden onmiddellijk verzonden, maar bijlagen worden vervangen door tijdelijke aanduidingen totdat Safe het scannen van bijlagen is voltooid. <p> Zie de sectie [Dynamic Delivery in Safe attachments policies](#dynamic-delivery-in-safe-attachments-policies) verder in dit artikel voor meer informatie.|Vermijd berichtvertraging terwijl geadresseerden worden beschermd tegen schadelijke bestanden. <p> Schakel geadresseerden in om een voorbeeld van bijlagen in de veilige modus te bekijken terwijl het scannen plaatsvindt.|
  |

-  Bijlage omleiden bij **detectie:** Schakel omleiding in en verzend de bijlage naar het volgende e-mailadres: Voor acties **blokkeren,** controleren of vervangen, verzendt u berichten met malwarebijlagen naar het opgegeven interne of externe e-mailadres voor analyse en onderzoek.

  De aanbeveling voor standaard- en strikte beleidsinstellingen is om omleiding in te stellen. Zie de instellingen Safe [Bijlagen voor meer informatie.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)

- Pas de bovenstaande selectie toe als **er malware** wordt gescand op bijlagen of er een fout optreedt: De actie die is opgegeven door **Safe Attachments unknown malware response** wordt uitgevoerd op berichten, zelfs wanneer Safe Bijlagen scannen niet kan worden voltooid. Selecteer deze optie altijd als u Omleiding **inschakelen selecteert.** Anders kunnen berichten verloren gaan.

- **Filters voor geadresseerden:** u moet de voorwaarden en uitzonderingen voor de geadresseerde opgeven die bepalen op wie het beleid van toepassing is. U kunt deze eigenschappen gebruiken voor voorwaarden en uitzonderingen:
  - **De geadresseerde is**
  - **Het domein van de geadresseerde is**
  - **De geadresseerde is lid van**

  U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar de voorwaarde of uitzondering kan meerdere waarden bevatten. Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_). Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).

- **Prioriteit:** Als u meerdere beleidsregels maakt, kunt u de volgorde opgeven waarin ze worden toegepast. Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.

  Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).

### <a name="dynamic-delivery-in-safe-attachments-policies"></a>Dynamische bezorging in Safe bijlagen-beleid

> [!NOTE]
> Dynamische bezorging werkt alleen voor Exchange Online postvakken.

Met de actie Dynamische bezorging in Safe bijlagen-beleid wordt getypeerd om eventuele vertragingen bij e-mailbezorging te voorkomen die kunnen worden veroorzaakt door Safe bijlagen scannen. De inhoud van het e-mailbericht wordt bezorgd bij de geadresseerde met een tijdelijke aanduiding voor elke bijlage. De tijdelijke aanduiding blijft staan totdat de bijlage veilig is en de bijlage vervolgens beschikbaar is om te openen of te downloaden.

Als een bijlage schadelijk blijkt te zijn, wordt het bericht in quarantaine geplaatst. Alleen beheerders (geen eindgebruikers) kunnen berichten bekijken, vrijgeven of verwijderen die in quarantaine zijn geplaatst Safe bijlagen scannen. Zie Berichten en bestanden in quarantaine beheren als beheerder voor [meer informatie.](manage-quarantined-messages-and-files.md)

De meeste PDF-bestanden en Office documenten kunnen in de veilige modus worden bekeken terwijl Safe bijlagen wordt gescand. Als een bijlage niet compatibel is met de voorbeeldweergave voor dynamische bezorging, zien de geadresseerden een tijdelijke aanduiding voor de bijlage totdat Safe bijlagen is gescand.

Als u een mobiel apparaat gebruikt en PDF's niet worden weergegeven in de dynamic delivery previewer op uw mobiele apparaat, opent u het bericht in Outlook op het web (voorheen bekend als Outlook Web App) met uw mobiele browser.

Hier zijn enkele aandachtspunten voor dynamische bezorging en doorgestuurde berichten:

- Als de doorgestuurde geadresseerde is beveiligd door een Safe-bijlagebeleid dat de optie Dynamische bezorging gebruikt, ziet de geadresseerde de tijdelijke aanduiding, met de mogelijkheid om een voorbeeld van compatibele bestanden te bekijken.
- Als de doorgestuurde geadresseerde niet wordt beveiligd door een Safe-bijlagebeleid, worden het bericht en de bijlagen bezorgd zonder Safe bijlagen of tijdelijke aanduidingen voor bijlagen.

Er zijn scenario's waarin Dynamische bezorging bijlagen in berichten niet kan vervangen. Deze scenario's omvatten:

- Berichten in openbare mappen.
- Berichten die met aangepaste regels uit het postvak van een gebruiker worden gerouteerd en vervolgens worden teruggeleid naar het postvak van een gebruiker.
- Berichten die (automatisch of handmatig) uit cloudpostvakken worden verplaatst naar andere locaties, waaronder archiefmappen.
- Regels voor Postvak IN verplaatsen het bericht uit het Postvak IN naar een andere map.
- Verwijderde berichten.
- De zoekmap voor het postvak van de gebruiker heeft een fouttoestand.
- Exchange Online organisaties waar Exclaimer is ingeschakeld. Zie [KB4014438](https://support.microsoft.com/help/4014438)om dit probleem op te lossen.
- [S/MIME)](/exchange/security-and-compliance/smime-exo/smime-exo) versleutelde berichten.
- U hebt de actie Dynamische bezorging geconfigureerd in een Safe-bijlagebeleid, maar de geadresseerde biedt geen ondersteuning voor Dynamische bezorging (de geadresseerde is bijvoorbeeld een postvak in een on-premises Exchange organisatie). Safe [Koppelingen in Microsoft Defender](set-up-safe-links-policies.md) voor Office 365 kunnen echter Office bestandsbijlagen met URL's scannen (afhankelijk van hoe de algemene instellingen voor [Safe-koppelingen](configure-global-settings-for-safe-links.md) zijn geconfigureerd).

## <a name="submitting-files-for-malware-analysis"></a>Bestanden indienen voor malwareanalyse

- Zie Malware en [niet-malware](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)verzenden naar Microsoft voor analyse als u een bestand ontvangt dat u naar Microsoft wilt verzenden voor analyse.
- Zie Berichten en bestanden rapporteren bij Microsoft als u een e-mailbericht (met of zonder bijlage) ontvangt dat u wilt indienen bij Microsoft voor [analyse.](report-junk-email-messages-to-microsoft.md)
