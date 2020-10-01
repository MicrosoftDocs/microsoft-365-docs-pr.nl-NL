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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- M365-security-compliance
- seo-marvel-apr2020
description: Beheerders kunnen de functie voor veilige bijlagen in Office 365 Advanced Threat Protection (ATP) leren kennen.
ms.openlocfilehash: 6ff356f34f3e44752b5ad7f5fa433a8c72cd5083
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326529"
---
# <a name="safe-attachments-in-office-365-atp"></a>Veilige bijlagen in Office 365 ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Veilige bijlagen in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) biedt een extra beveiligingslaag voor e-mailbijlagen die al zijn gescand door [beveiliging tegen malware in Exchange Online Protection (EOP)](anti-malware-protection.md). Met name: veilige bijlagen gebruiken een virtuele omgeving om bijlagen in e-mailberichten te controleren voordat ze worden afgeleverd bij geadresseerden (een proces met de _detonatie_functie).

Beveiliging van bijlagen voor e-mailberichten wordt bepaald door beleidsregels voor veilige bijlagen. Er is geen standaardbeleid voor beveiliging van bijlagen, **dus als u de beveiliging van veilige bijlagen wilt achterhalen, moet u een of meer regels voor veilig bijlagen maken**. Zie voor instructies het [beleid voor veilige bijlagen instellen in ATP](set-up-atp-safe-attachments-policies.md).

In de volgende tabel wordt beschreven hoe u scenario's voor veilige bijlagen in Microsoft 365 en Office 365-organisaties met ATP (met andere woorden, gebrek aan licentieverlening in de voorbeelden) biedt.

****

|Voorbeeld|Resultaat|
|---|---|
|De organisatie van Pat Microsoft 365 E5 heeft geen beleid voor veilige bijlagen geconfigureerd.|Pat is niet beschermd door veilige bijlagen. <br/><br/> Een beheerder moet ten minste één beleid voor veilige bijlagen maken om beveiliging van veilige bijlagen te activeren. Daarnaast moet de voorwaarden van het beleid ook de voorwaarden voor de toepassing van Pat zijn, als Pat door veilige bijlagen moet worden beveiligd.|
|De organisatie van Lee heeft een veilig bijlage beleid dat alleen van toepassing is op de financiering van medewerkers. Lee maakt deel uit van de verkoopafdeling.|Lee is niet beveiligd door veilige bijlagen. <br/><br/> Werknemers kunnen werknemers beschermen door middel van veilige bijlagen, maar verkoopmedewerkers (en andere werknemers) zijn niet.|
|Gisteren, een beheerder in de organisatie heeft een veilig bijlage beleid gemaakt dat van toepassing is op alle werknemers. Eerder vandaag heeft Jean een e-mailbericht ontvangen met een bijlage.|Jean is beschermd door veilige bijlagen. <br/><br/> Meestal duurt het ongeveer 30 minuten voordat een nieuw beleid van kracht wordt.|
|Voor iedereen in de organisatie heeft Chris lang een veilig beleid voor het opstellen van bijlagen. Chris ontvangt een e-mailbericht met een bijlage en stuurt het bericht door naar externe geadresseerden.|Chis is beveiligd door veilige bijlagen. <br/><br/> Als de externe geadresseerden ook beleidsregels voor veilige bijlagen hebben in hun organisatie, zijn de doorgestuurde berichten onderworpen aan deze beleidsregels.|
|

Het scannen van veilige bijlagen vindt plaats in dezelfde regio waarin uw gegevens van Microsoft 365 zich bevinden. Zie [waar bevinden uw gegevens zich?](https://products.office.com/where-is-your-data-located?geo=All) voor meer informatie over het informatiecentrum.

> [!NOTE]
> De volgende functies bevinden zich in de algemene instellingen in het beveiligings & nalevings centrum, maar deze instellingen worden globaal in-of uitgeschakeld en vereisen geen veilige beleidsregels voor bijlagen:
>
> - [ATP voor SharePoint, OneDrive en Microsoft teams](atp-for-spo-odb-and-teams.md).
>
> - [Veilige documenten in Microsoft 365 E5](safe-docs.md)

## <a name="safe-attachments-policy-settings"></a>Beleidsinstellingen voor veilige bijlagen

In deze sectie worden de instellingen in het beleid voor veilige bijlagen beschreven:

- **Veilige bijlagen onbekende malware**: met deze instelling wordt de actie bestuurd voor het scannen van schadelijke bijlagen in e-mailberichten. In de volgende tabel vindt u een beschrijving van de beschikbare opties:

  ****

  |Optie|Actief|Gebruik dit wanneer u het volgende wilt doen:|
  |---|---|---|
  |**Uit**|Bijlagen worden niet gescand voor malware door veilige bijlagen. Berichten worden nog steeds gecontroleerd op malware via [beveiliging tegen malware in EOP](anti-malware-protection.md).|Scan uitschakelen voor geselecteerde geadresseerden. <br/><br/> Onnodige vertragingen voor het routeren van interne e-mail voorkomen. <br/><br/> **Deze optie wordt niet aanbevolen voor de meeste gebruikers. U dient deze optie alleen te gebruiken als u het scannen van veilige bijlagen wilt uitschakelen voor geadresseerden die alleen berichten van vertrouwde afzenders ontvangen.**|
  |**Monitor**|Levert berichten met bijlagen en spoort wat er gebeurt met ontdekte malware. <br/><br/> Het bezorgen van veilige berichten wordt mogelijk vertraagd door het scannen van veilige bijlagen.|Kijk waar de gedetecteerde malware in uw organisatie terechtkomt.|
  |**Blokkeren**|Hiermee voorkomt u dat berichten met gedetecteerde schadelijke bijlagen worden afgeleverd. <br/><br/> Berichten worden in [quarantaine geplaatst](manage-quarantined-messages-and-files.md) waarbij alleen beheerders (niet eindgebruikers) de berichten kunnen controleren, vrijgeven of verwijderen. <br/><br/> Toekomstige exemplaren van berichten en bijlagen automatisch blokkeren. <br/><br/> Het bezorgen van veilige berichten wordt mogelijk vertraagd door het scannen van veilige bijlagen.|Beschermt uw organisatie tegen herhaling van aanvallen met dezelfde malware-bijlagen. <br/><br/> Dit is de standaardwaarde en de aanbevolen waarde in de standaard en strikte [vooraf ingestelde beveiligingsbeleidsregels](preset-security-policies.md).|
  |**Vervangen**|Verwijdert gedetecteerde schadelijke bijlagen. <br/><br/> Hiermee wordt de ontvanger gewaarschuwd dat bijlagen zijn verwijderd. <br/><br/>  Berichten worden in [quarantaine geplaatst](manage-quarantined-messages-and-files.md) waarbij alleen beheerders (niet eindgebruikers) de berichten kunnen controleren, vrijgeven of verwijderen. <br/><br/> Het bezorgen van veilige berichten wordt mogelijk vertraagd door het scannen van veilige bijlagen.|De zichtbaarheid van de ontvangers voor de verwijdering van bijlagen is vanwege malware gedetecteerd.|
  |**Dynamische bezorging**|Hiermee worden berichten onmiddellijk bezorgd, maar worden bijlagen met tijdelijke aanduidingen vervangen totdat de scan is voltooid. <br/><br/> Zie voor meer informatie de sectie [dynamische bezorging in beleidsregels voor veilige bijlagen](#dynamic-delivery-in-safe-attachments-policies) verderop in dit onderwerp.|Voorkom dat berichten worden vertraagd wanneer u geadresseerden tegen kwaadwillende bestanden beschermt <br/> <br/> Voorbeelden van bijlagen weergeven in de veilige modus terwijl de scanfunctie plaatsvindt|
  |

- **Bijlage doorsturen naar detectie: Schakel omleiding** in en **Stuur de bijlage naar het volgende e-mailadres**: voor **blok**punten, **monitors**of **vervangen** , berichten met schadelijke bijlagen verzenden naar het opgegeven interne of externe e-mailadres voor analyse en onderzoek.

  De aanbeveling voor standaard-en strikte beleidsinstellingen is om omleiding in te schakelen. Zie [instellingen voor veilige bijlagen](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)voor meer informatie.

- **De bovenstaande selectie toepassen als u wilt dat malware wordt gescand op bijlagen wanneer een fout optreedt of als de fout zich voordoet**, wordt de actie die is opgegeven door veilige bijlagen, ook wel als gevolg van **schadelijke malware** op berichten. Altijd deze optie selecteren als u **omleiden inschakelen**selecteert. Anders zijn er mogelijk berichten verloren.

- **Filters voor geadresseerden**: u moet de voorwaarden en uitzonderingen opgeven voor de ontvanger van het beleid. U kunt deze eigenschappen gebruiken voor voorwaarden en uitzonderingen:

  - **De ontvanger is**
  - **Het domein van de ontvanger is**
  - **De ontvanger is lid van**

  U kunt slechts één voorwaarde of een uitzondering gebruiken, maar de voorwaarde of uitzondering kan meerdere waarden bevatten. Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_). Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).

- **Prioriteit**: als u meerdere beleidsregels maakt, kunt u de volgorde opgeven waarin ze worden toegepast. Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.

  Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).

### <a name="dynamic-delivery-in-safe-attachments-policies"></a>Dynamische levering in beleidsregels voor veilige bijlagen

> [!NOTE]
> Dynamische bezorging werkt alleen voor postvakken van Exchange Online.

De actie dynamische bezorging in het beleid voor veilige bijlagen zoekt naar het elimineren van e-mail vertragingen die kunnen worden veroorzaakt door het scannen van veilige bijlagen. De hoofdtekst van het e-mailbericht wordt bij de geadresseerde bezorgd met een tijdelijke aanduiding voor elke bijlage. De tijdelijke aanduiding blijft staan totdat de bijlage veilig is geworden en de bijlage beschikbaar is om te openen of te downloaden.

Als een bijlage schadelijk blijkt te zijn, wordt het bericht in quarantaine geplaatst. Alleen beheerders (niet einde van gebruikers) kunnen berichten die in quarantaine zijn gezet door het scannen op veilige bijlagen te controleren, vrijgeven of verwijderen. Zie voor meer informatie [gequarantinee berichten en bestanden beheren als beheerder](manage-quarantined-messages-and-files.md).

De meeste Pdf's en Office-documenten kunnen worden weergegeven in de veilige modus, terwijl de scanfunctie wordt uitgevoerd. Als een bijlage niet compatibel is met de dynamische voorbeeldweergave, ziet de geadresseerden een tijdelijke aanduiding voor de bijlage totdat de scan is voltooid.

Als u een mobiel apparaat gebruikt en Pdf's niet worden weergegeven in de weergave voor dynamische bezorgingen op uw mobiele apparaat, kunt u het bericht openen in de webversie van Outlook (voorheen Outlook Web app) met behulp van uw mobiele browser.

Hier volgen enkele aandachtspunten voor dynamische bezorgings-en doorgestuurde berichten:

- Als de doorgestuurde geadresseerde wordt beschermd door een beleid voor veilige bijlagen met de optie dynamische bezorging, ziet de geadresseerde de tijdelijke aanduiding, zodat deze de mogelijkheid biedt om compatibele bestanden te bekijken.

- Als de doorgestuurde geadresseerde niet is beveiligd door een beleid voor veilige bijlagen, worden de berichten en bijlagen afgeleverd zonder dat ze afbeeldingen voor veilige bijlagen of tijdelijke aanduidingen voor bijlagen worden gescand.

## <a name="scenarios-where-safe-attachments-doesnt-scan-messages"></a>Scenario's waarbij veilige bijlagen geen berichten scant

Er zijn scenario's waarin veilige bijlagen geen berichten kunnen scannen:

- Berichten in openbare mappen.

- Berichten die worden gerouteerd van en terug in het postvak van een gebruiker via aangepaste regels.

- Berichten die vanuit Cloud postvakken worden verplaatst (automatisch of handmatig) naar andere locaties, waaronder archief mappen.

- Verwijderde berichten.

- De zoekmap van het postvak van de gebruiker bevindt zich in een foutstatus.

- Exchange Online-organisaties waarbij Exclaimer is ingeschakeld. Zie [KB4014438](https://support.microsoft.com/help/4014438)voor meer informatie.

- [S/MIME)](s-mime-for-message-signing-and-encryption.md) versleutelde berichten.

- U hebt de actie voor dynamische bezorging geconfigureerd in een veilig bijlage beleid, maar de geadresseerde biedt geen ondersteuning voor dynamische bezorging (de ontvanger is bijvoorbeeld een postvak in een on-premises Exchange-organisatie). Met [veilige koppelingen in Office 365 ATP](set-up-atp-safe-links-policies.md) kunt u echter wel Office-bestandsbijlagen met url's zoeken (afhankelijk van de manier waarop de veilige koppelingen zijn geconfigureerd).

## <a name="submitting-files-for-malware-analysis"></a>Bestanden voor de analyse van malware indienen

- Als u een bestand ontvangt dat u wilt verzenden naar Microsoft voor analyse, raadpleegt u [malware en niet-malware verzenden naar Microsoft voor analyse](submitting-malware-and-non-malware-to-microsoft-for-analysis.md).

- Als u een e-mailbericht ontvangt (met of zonder bijlage) dat u bij Microsoft wilt indienen voor analyse, raadpleegt u [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).
