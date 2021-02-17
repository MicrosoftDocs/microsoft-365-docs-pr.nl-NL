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
description: Beheerders kunnen meer informatie krijgen over de functie Veilige bijlagen in Microsoft Defender voor Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5d2d348856dbd51cabe2b320d315406076921fee
ms.sourcegitcommit: a9ac702c9efc9defded3bfa65618b94bac00c237
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/16/2021
ms.locfileid: "50261535"
---
# <a name="safe-attachments-in-microsoft-defender-for-office-365"></a>Veilige bijlagen in Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Veilige bijlagen in Microsoft Defender voor [Office 365](office-365-atp.md) bieden een extra beveiligingslaag voor e-mailbijlagen die al zijn gescand met beveiliging tegen [malware in Exchange Online Protection (EOP).](anti-malware-protection.md) Met name Veilige bijlagen maakt gebruik van een virtuele omgeving om bijlagen in e-mailberichten te controleren voordat deze worden bezorgd bij geadresseerden (een proces dat _detoneren wordt genoemd)._

De beveiliging van veilige bijlagen voor e-mailberichten wordt bepaald door het beleid voor veilige bijlagen. Er is geen standaardbeleid voor veilige bijlagen. Als u de beveiliging van veilige bijlagen wilt instellen, moet u een of meer beleidsregels voor **veilige bijlagen maken.** Zie Beleid voor veilige bijlagen instellen [in Defender voor Office 365](set-up-atp-safe-attachments-policies.md)voor instructies.

In de volgende tabel worden scenario's beschreven voor veilige bijlagen in Microsoft 365- en Office 365-organisaties die Microsoft Defender voor Office 365 bevatten (met andere woorden, het ontbreken van licenties is nooit een probleem in de voorbeelden).

****

|Scenario|Resultaat|
|---|---|
|Er is voor de Microsoft 365 E5-organisatie van Pat geen beleid voor veilige bijlagen geconfigureerd.|Pat wordt niet beveiligd door veilige bijlagen. <p> Een beheerder moet ten minste één beleid met veilige bijlagen maken om veilige bijlagen te kunnen veiligen. Bovendien moeten aan de voorwaarden van het beleid Pat worden voldaan als Pat door veilige bijlagen moet worden beschermd.|
|De organisatie van Lusen heeft een beleid met veilige bijlagen dat alleen van toepassing is op financiële werknemers. Lee is lid van de verkoopafdeling.|Luw wordt niet beveiligd door veilige bijlagen. <p> Werknemers in de financiële sector worden beveiligd door veilige bijlagen, maar verkoopmedewerkers (en andere werknemers) niet.|
|Gisteren heeft een beheerder in de organisatie Van Eder een beleid voor veilige bijlagen gemaakt dat van toepassing is op alle werknemers. Eerder vandaag heeft John een e-mailbericht ontvangen met een bijlage.|John wordt beveiligd door veilige bijlagen. <p> Het duurt meestal ongeveer 30 minuten voordat een nieuw beleid van kracht wordt.|
|Chris's organisatie heeft al lange tijd beleidsregels voor veilige bijlagen voor iedereen in de organisatie. Chris ontvangt een e-mailbericht met een bijlage en stuurt het vervolgens door naar externe geadresseerden.|Chis wordt beveiligd door veilige bijlagen. <p> Als de externe geadresseerden ook een beleid voor veilige bijlagen in hun organisatie hebben, zijn de doorgestuurde berichten onderhevig aan dit beleid.|
|

Het scannen van veilige bijlagen vindt plaats in dezelfde regio waar uw Microsoft 365-gegevens zich bevinden. Zie Waar bevinden zich uw gegevens voor meer informatie over geografie van [datacenters?](https://products.office.com/where-is-your-data-located?geo=All)

> [!NOTE]
> De volgende functies bevinden zich in de globale instellingen van het beleid voor veilige bijlagen in het & compliancecentrum. Deze instellingen worden echter globaal in- of uitgeschakeld en er is geen beleid voor veilige bijlagen vereist:
>
> - [Veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams.](atp-for-spo-odb-and-teams.md)
>
> - [Veilige documenten in Microsoft 365 E5](safe-docs.md)

## <a name="safe-attachments-policy-settings"></a>Beleidsinstellingen voor veilige bijlagen

In deze sectie worden de instellingen in het beleid voor veilige bijlagen beschreven:

- **Safe Attachments unknown malware response:** This setting controls the action for Safe Attachments malware scanning in email messages. De beschikbare opties worden in de volgende tabel beschreven:

  ****

  |Optie|Effect|Gebruik deze als u het volgende wilt doen:|
  |---|---|---|
  |**Uit**|Bijlagen worden niet gescand op malware met veilige bijlagen. Berichten worden nog steeds gescand op malware [door middel van antimalwarebeveiliging in EOP.](anti-malware-protection.md)|Het scannen van geselecteerde geadresseerden uitschakelen. <p> Voorkom onnodige vertragingen bij het routeren van interne e-mail. <p> **Deze optie wordt niet aanbevolen voor de meeste gebruikers. Gebruik deze optie alleen om het scannen van veilige bijlagen uit te schakelen voor geadresseerden die alleen berichten ontvangen van vertrouwde afzenders.**|
  |**Monitor**|Bezorgt berichten met bijlagen en houdt vervolgens bij wat er gebeurt met gedetecteerde malware. <p> Bezorging van veilige berichten kan vertraagd zijn vanwege het scannen van veilige bijlagen.|Zien waar malware in uw organisatie wordt gevonden.|
  |**Blokkeren**|Voorkomt dat berichten met gedetecteerde malwarebijlagen worden bezorgd. <p> Berichten worden [in quarantaine](manage-quarantined-messages-and-files.md) geplaatst en alleen beheerders (niet eindgebruikers) kunnen de berichten controleren, vrijgeven of verwijderen. <p> Toekomstige exemplaren van de berichten en bijlagen worden automatisch blokkeert. <p> Bezorging van veilige berichten wordt mogelijk vertraagd vanwege het scannen van veilige bijlagen.|Beschermt uw organisatie tegen herhaalde aanvallen met dezelfde malwarebijlagen. <p> Dit is de standaardwaarde en de aanbevolen waarde in standaard- en strikt [vooraf ingestelde beveiligingsbeleidsregels.](preset-security-policies.md)|
  |**Vervangen**|Hiermee verwijdert u gedetecteerde malwarebijlagen. <p> Geadresseerden krijgen een bericht dat bijlagen zijn verwijderd. <p>  Berichten worden [in quarantaine](manage-quarantined-messages-and-files.md) geplaatst en alleen beheerders (niet eindgebruikers) kunnen de berichten controleren, vrijgeven of verwijderen. <p> Bezorging van veilige berichten wordt mogelijk vertraagd vanwege het scannen van veilige bijlagen.|Geadresseerden kunnen zien dat bijlagen zijn verwijderd vanwege gedetecteerde malware.|
  |**Dynamische bezorging**|Bezorgt berichten direct, maar vervangt bijlagen door tijdelijke aanduidingen totdat het scannen van veilige bijlagen is voltooid. <p> Zie de sectie [Beleidsregels voor dynamische bezorging in veilige](#dynamic-delivery-in-safe-attachments-policies) bijlagen verderaan in dit artikel.|Voorkom dat berichten worden vertraagd bij het beveiligen van geadresseerden tegen schadelijke bestanden. <p> Geadresseerden in staat stellen een voorbeeld van bijlagen in de veilige modus te bekijken terwijl het scannen wordt plaatsvinden.|
  |

- Bijlage omleiden bij **detectie:** Schakel omleiding en Verzenden van de  bijlage in naar het volgende e-mailadres: voor acties **blokkeren,** controleren of vervangen verzendt u berichten met malwarebijlagen naar het opgegeven interne of externe e-mailadres voor analyse en onderzoek.

  Het wordt aanbevolen voor standaard- en striktbeleidsinstellingen om omleiding in teschakelen. Zie instellingen voor [veilige bijlagen voor meer informatie.](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)

- **Pas de bovenstaande** selectie toe als malware wordt gescand op bijlagen in de tijd of als er een fout optreedt: De actie die wordt opgegeven door Safe **Attachments onbekende malwarereactie** wordt uitgevoerd op berichten, zelfs als het scannen van veilige bijlagen niet kan worden voltooid. Selecteer deze optie altijd als u Omleiding **inschakelen selecteert.** Anders kunnen berichten verloren gaan.

- **Geadresseerdenfilters:** u moet de voorwaarden van de geadresseerde opgeven en uitzonderingen die bepalen op wie het beleid van toepassing is. U kunt deze eigenschappen gebruiken voor voorwaarden en uitzonderingen:

  - **De ontvanger is**
  - **Het domein van de ontvanger is**
  - **De ontvanger is lid van**

  U kunt een voorwaarde of uitzondering slechts eenmaal gebruiken, maar de voorwaarde of uitzondering kan meerdere waarden bevatten. Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_). Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).

- **Prioriteit:** als u meerdere beleidsregels maakt, kunt u de volgorde opgeven waarin ze worden toegepast. Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.

  Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).

### <a name="dynamic-delivery-in-safe-attachments-policies"></a>Dynamische bezorging in beleidsregels voor veilige bijlagen

> [!NOTE]
> Dynamische bezorging werkt alleen voor Exchange Online-postvakken.

Met de actie Dynamische bezorging in het beleid Veilige bijlagen wordt getypd om vertragingen voor de bezorging van e-mail te voorkomen die mogelijk worden veroorzaakt door het scannen van veilige bijlagen. De tekst van het e-mailbericht wordt bij de geadresseerde bezorgd met een tijdelijke aanduiding voor elke bijlage. De tijdelijke aanduiding blijft staan totdat de bijlage veilig wordt gevonden, waarna de bijlage kan worden geopend of gedownload.

Als blijkt dat een bijlage schadelijk is, wordt het bericht in quarantaine geplaatst. Alleen beheerders (geen eindgebruikers) kunnen berichten controleren, vrijgeven of verwijderen die in quarantaine zijn geplaatst door veilige bijlagen te scannen. Zie Berichten en bestanden in quarantaine beheren als [beheerder voor meer informatie.](manage-quarantined-messages-and-files.md)

De meeste PDF-bestanden en Office-documenten kunnen in de veilige modus worden bekeken terwijl het scannen van veilige bijlagen wordt gestart. Als een bijlage niet compatibel is met voorbeeldweergave voor Dynamische bezorging, zien de geadresseerden een tijdelijke aanduiding voor de bijlage totdat het scannen van veilige bijlagen is voltooid.

Als u een mobiel apparaat gebruikt en PDF-bestanden niet worden weergegeven in de Dynamic Delivery Previewer op uw mobiele apparaat, opent u het bericht in de webversie van Outlook (voorheen Outlook Web App genoemd) in uw mobiele browser.

Hier zijn enkele aandachtspunten voor dynamische bezorging en doorgestuurde berichten:

- Als de doorgestuurde geadresseerde wordt beveiligd door een beleid voor veilige bijlagen dat gebruikmaakt van de optie Dynamische bezorging, ziet de geadresseerde de tijdelijke aanduiding, met de mogelijkheid om voorbeelden van compatibele bestanden te bekijken.

- Als de doorgestuurde geadresseerde niet wordt beveiligd door een beleid voor veilige bijlagen, worden het bericht en de bijlagen bezorgd zonder veilige bijlagen te scannen of tijdelijke aanduidingen voor bijlagen.

Er zijn scenario's waarin Dynamische bezorging bijlagen in berichten niet kan vervangen. Dit zijn de volgende scenario's:

- Berichten in openbare mappen.

- Berichten die met aangepaste regels naar het postvak van een gebruiker worden doorgeleid en vervolgens weer worden verzonden.

- Berichten die (automatisch of handmatig) uit postvakken in de cloud worden verplaatst naar andere locaties, waaronder archiefmappen.

- Verwijderde berichten.

- De zoekmap van het postvak van de gebruiker heeft een foutmelding.

- Exchange Online-organisaties waarin Uitroepen is ingeschakeld. Zie [KB4014438](https://support.microsoft.com/help/4014438)om dit op te lossen.

- [S/MIME)](s-mime-for-message-signing-and-encryption.md) versleutelde berichten.

- U hebt de actie Dynamische bezorging geconfigureerd in het beleid veilige bijlagen, maar de geadresseerde biedt geen ondersteuning voor Dynamische bezorging (de geadresseerde is bijvoorbeeld een postvak in een on-premises Exchange-organisatie). Met veilige koppelingen in Microsoft Defender voor [Office 365](set-up-atp-safe-links-policies.md) kunt u echter Office-bestandsbijlagen scannen die URL's bevatten (afhankelijk van hoe de globale instellingen voor veilige koppelingen [zijn](configure-global-settings-for-safe-links.md) geconfigureerd).

## <a name="submitting-files-for-malware-analysis"></a>Bestanden indienen voor malwareanalyse

- Als u een bestand ontvangt dat u naar Microsoft wilt verzenden voor analyse, zie Malware en [niet-malware](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)naar Microsoft verzenden voor analyse.

- Als u een e-mailbericht (met of zonder bijlage) ontvangt dat u bij Microsoft wilt verzenden voor analyse, bekijkt u Berichten en bestanden [rapporteren bij Microsoft.](report-junk-email-messages-to-microsoft.md)
