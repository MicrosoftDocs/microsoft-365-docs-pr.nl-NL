---
title: Recordbeheer in Microsoft 365
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Met recordbeheer in Microsoft 365 kunt u uw retentieschema's toepassen op een bestandsplan voor beheer van retentie, declaratie van records en verwerking.
ms.openlocfilehash: 853303dcaffcbacfcf805b8617b836254cf31ad8
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245430"
---
# <a name="learn-about-records-management-in-microsoft-365"></a>Meer informatie over recordbeheer in Microsoft 365

>*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Alle soorten organisaties vereisen een oplossing voor recordbeheer voor het beheren van wettelijke, juridische en bedrijfskritische records voor al hun bedrijfsgegevens. Recordbeheer in Microsoft 365 helpt een organisatie bij het beheren van hun wettelijke verplichtingen, biedt de mogelijkheid om de compliance van regelgeving aan te tonen en vergroot de efficiëntie bij het regelmatig verwijderen van items die niet meer bewaard moeten worden, die niet meer van waarde zijn of die niet meer nodig zijn voor zakelijke doeleinden.

Gebruik de volgende mogelijkheden ter ondersteuning van uw oplossing voor recordbeheer in Microsoft 365:

- **Inhoud labelen als een record**. Maak en configureer labels om inhoud te markeren als een [record](#records) die vervolgens kan worden toegepast door gebruikers of automatisch kan worden toegepast door vertrouwelijke informatie, trefwoorden of inhoudstypen te identificeren.

- **Migreert en beheert uw retentievereisten met bestandsplan**. Met behulp van een [bestandsplan](file-plan-manager.md)kunt u een bestaand retentieplan toevoegen aan Microsoft 365 of een nieuw abonnement maken voor verbeterde beheermogelijkheden.

- **Instellingen voor retentie en verwijdering configureren met retentielabels**. Configureer [retentielabels](retention.md#retention-labels) met de retentieperioden en -acties op basis van verschillende factoren waaronder de datum van de laatste wijziging of aanmaking.

- **Start verschillende retentieperioden wanneer een gebeurtenis plaatsvindt** met [retentie op basis van gebeurtenissen](event-driven-retention.md).

- **Controleer en valideer verwijdering** met [verwijderingscontroles](disposition.md#disposition-reviews) en bewijs van [de verwijdering van records](disposition.md#disposition-of-records).

- **Exporteer gegevens over alle verwijderde items** met de [exportoptie](disposition.md#filter-and-export-the-views).

- **Stel specifieke machtigingen in** voor recordbeheersfuncties in uw organisatie om [de juiste toegangsrechten te hebben](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).

Met deze functies kunt u de retentiechema's en vereisten van uw organisatie opnemen in een oplossing voor recordbeheer die de bewaring, declaratie en de verwijdering van records beheert, om de volledige levenscyclus van uw inhoud te ondersteunen.

Naast de online documentatie kan het handig zijn om de [webinaropname](https://aka.ms/MIPC/Video-RecordsManagementWebinar) over recordbeheer te beluisteren en het bijbehorende [deck met veelgestelde vragen](https://aka.ms/MIPC/Blog-RecordsManagementWebinar) te downloaden.

## <a name="records"></a>Records

Wanneer inhoud als record wordt gedeclareerd:

- Er gelden beperkingen voor de items wat betreft de [acties die zijn toegestaan of geblokkeerd](#compare-restrictions-for-what-actions-are-allowed-or-blocked).

- Aanvullende activiteiten over het item worden geregistreerd.

- U hebt een bewijs van de verwijdering als de items aan het einde van de bewaarperiode worden verwijderd.

U gebruik [retentielabels](retention.md#retention-labels) om content te markeren als een **record**, of een **regelgevingsrecord**. Het verschil tussen deze twee wordt uitgelegd in de volgende sectie. U kunt deze labels publiceren zodat gebruikers en beheerders deze handmatig op content kunnen toepassen of deze labels automatisch toepassen op content die u wilt markeren als een record of een regelgevingsrecord.

Door bewaarlabels te gebruiken om records te declaren, kunt u één consistente strategie implementeren voor het beheren van records in uw Microsoft 365-omgeving.

### <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a>Beperkingen vergelijken voor welke acties zijn toegestaan of geblokkeerd

Gebruik de volgende tabel om te bepalen welke beperkingen voor inhoud gelden als gevolg van het toepassen van een standaardberetentielabel en bewaarlabels die inhoud markeren als een record of record van regelgeving. 

Een standaardberetentielabel bevat instellingen en acties voor bewaren, maar geeft geen inhoud aan als een record of een regelgevingsrecord.

>[!NOTE] 
> De tabel bevat kolommen voor een vergrendelde en niet-vergrendelde record, die van toepassing zijn op SharePoint en OneDrive, maar niet op Exchange. De mogelijkheid om een record te vergrendelen en te ontgrendelen, maakt [gebruik van recordversies](record-versioning.md) die niet wordt ondersteund voor Exchange-items. Dus voor alle Exchange-items die zijn gemarkeerd als een record, wordt het gedrag toegewezen aan de kolom **Record - vergrendeld** en is de kolom **Record - ontgrendeld** niet relevant.


|Actie| Retentielabel |Record- vergrendeld| Record - ontgrendeld| Regelgevingsrecord |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Inhoud bewerken|Toegestaan | **Geblokkeerd** | Toegestaan | **Geblokkeerd**|
|Eigenschappen bewerken, inclusief naamwijzigingen|Toegestaan |Toegestaan | Toegestaan| **Geblokkeerd**|
|Verwijderen|Toegestaan <sup>1</sup> |**Geblokkeerd** |**Geblokkeerd**| **Geblokkeerd**|
|Kopiëren|Toegestaan |Toegestaan | Toegestaan| Toegestaan|
|Verplaatsen binnen container <sup>2</sup>|Toegestaan |Toegestaan | Toegestaan| Toegestaan|
|Verplaatsen tussen containers <sup>2</sup>|Toegestaan |Toegestaan indien nooit ontgrendeld | **Geblokkeerd** | **Geblokkeerd**|
|Openen/lezen|Toegestaan |Toegestaan | Toegestaan| Toegestaan|
|Label wijzigen|Toegestaan |Toegestaan - alleen voor containerbeheerder | Toegestaan - alleen voor containerbeheerder| **Geblokkeerd**
|Label verwijderen|Toegestaan |Toegestaan - alleen voor containerbeheerder | Toegestaan - alleen voor containerbeheerder| **Geblokkeerd**

Voetnoten:

<sup>1</sup> worden ondersteund door OneDrive en Exchange door een kopie op een beveiligde locatie te bewaren, maar geblokkeerd door SharePoint.

Wanneer u een bewaarlabel op een lijstitem met een documentbijlage toepast, neemt dat document de instellingen voor retentie niet over en kan het uit het lijstitem worden verwijderd. Als dat lijstitem daarentegen is gedeclareerd als een record met een bewaarlabel, neemt de documentbijlage de instellingen voor retentie over en kan het niet worden verwijderd. 

<sup>2</sup> Containers zijn onder andere SharePoint-documentbibliotheken, OneDrive-accounts en Exchange-postvakken.

>[!IMPORTANT] 
> Het belangrijkste verschil voor een regelgevingsrecord is dat nadat deze is toegepast op inhoud, niemand, zelfs niet de globale beheerder, het label kan verwijderen. 
>
> Bewaarlabels die zijn geconfigureerd voor regelgevingsrecords, hebben ook de volgende beheerdersbeperkingen:
> - De bewaarperiode kan niet korter worden gemaakt nadat het label is opgeslagen, enkel verlengd.
> - Deze labels worden niet ondersteund door beleidsregels voor automatisch labelen en moeten worden toegepast met [beleidsregels voor retentielabels](create-apply-retention-labels.md). 
>
> Bovendien kan een regelgevingslabel niet worden toegepast op een document dat is uitgecheckt in SharePoint.
> 
> Vanwege de beperkingen en onherroepelijke acties, moet u absoluut gebruikmaken van regelgevingsrecords voordat u deze optie selecteert voor uw retentielabels. Om te voorkomen dat u per ongeluk een configuratie instelt, is deze optie standaard niet beschikbaar, maar moet deze eerst worden ingeschakeld via PowerShell. Er zijn instructies opgenomen in [Records declareren met behulp van retentielabels](declare-records.md).

## <a name="configuration-guidance"></a>Configuratierichtlijnen

Zie [Aan de slag met recordbeheer](get-started-with-records-management.md). Dit artikel bevat informatie over abonnementen, machtigingen en koppelingen naar end-to-end configuratierichtlijnen voor recordbeheerscenario's.