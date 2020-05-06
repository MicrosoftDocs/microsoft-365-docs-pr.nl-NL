---
title: Aangepaste detectieregels maken en beheren in Microsoft Threat Protection
description: Meer informatie over het maken en beheren van aangepaste detectieregels op basis van geavanceerde jachtquery's
keywords: geavanceerde jacht, dreigingjacht, cyberdreigingsjacht, bescherming tegen microsoft-bedreigingen, microsoft 365, mtp, m365, zoeken, query, telemetrie, aangepaste detecties, regels, schema, kusto, microsoft 365, Microsoft Threat Protection, RBAC, machtigingen, Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: cdfc23f34d90c9d725ec6fb314728553a987c025
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034862"
---
# <a name="create-and-manage-custom-detections-rules"></a>Aangepaste detectieregels maken en beheren

**Geldt voor:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Met aangepaste detectieregels die zijn gebaseerd op geavanceerde jachtquery's, u proactief verschillende gebeurtenissen en systeemstatussen controleren, waaronder vermoedelijke inbreukactiviteiten en verkeerd geconfigureerde eindpunten. [Advanced hunting](advanced-hunting-overview.md) U instellen dat ze op regelmatige tijdstippen worden uitgevoerd, waarschuwingen genereren en responsacties uitvoeren wanneer er overeenkomsten zijn.

## <a name="required-permissions-for-managing-custom-detections"></a>Vereiste machtigingen voor het beheren van aangepaste detecties

Als u aangepaste detecties wilt beheren, moet u een van deze rollen toegewezen krijgen:

- **Beveiligingsbeheerder** : de beveiligingsbeheerder of beveiligingsbeheerrol is een [Azure Active Directory-rol](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) voor het beheren van verschillende beveiligingsinstellingen in het Microsoft 365-beveiligingscentrum en verschillende portals en services.

- **Beveiligingsoperator** : de rol van de beveiligingsoperator is een [Azure Active Directory-rol](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) voor het beheren van waarschuwingen en heeft wereldwijde alleen-lezen toegang voor beveiligingsfuncties, inclusief alle informatie in het Microsoft 365-beveiligingscentrum. Deze rol is voldoende voor het beheren van aangepaste detecties alleen als role-based access control (RBAC) is uitgeschakeld in Microsoft Defender ATP. Als u RBAC hebt geconfigureerd, hebt u ook de machtiging **voor beveiligingsinstellingen voor** Microsoft Defender ATP nodig.

Als u vereiste machtigingen wilt beheren, kan een **globale beheerder** het volgende doen:

- Wijs de rol **van beveiligingsbeheerder** of **beveiligingsoperator** toe in [het Microsoft 365-beheercentrum](https://admin.microsoft.com/) onder**Debeveiligingsbeheerder** **rollen** > .
- Schakel RBAC-instellingen voor Microsoft Defender ATP in Microsoft Defender Security Center in microsoft [Defender-beveiligingscentrum](https://securitycenter.windows.com/) onder**Rollen****voor machtigingen voor** >  **instellingen** > . Selecteer de bijbehorende rol om de machtigingen **voor beveiligingsinstellingen beheren** toe te wijzen.

> [!NOTE]
> Om aangepaste detecties te beheren, hebben **beveiligingsoperators** de machtigingen **voor beveiligingsinstellingen beheren** in Microsoft Defender ATP nodig als RBAC is ingeschakeld.

## <a name="create-a-custom-detection-rule"></a>Een aangepaste detectieregel maken
### <a name="1-prepare-the-query"></a>1. Bereid de query voor.

Ga in het beveiligingscentrum van Microsoft 365 naar **Geavanceerd zoeken** en selecteer een bestaande query of maak een nieuwe query. Wanneer u een nieuwe query gebruikt, voert u de query uit om fouten te identificeren en mogelijke resultaten te begrijpen.

#### <a name="required-columns-in-the-query-results"></a>Vereiste kolommen in de queryresultaten
Als u een aangepaste detectieregel wilt maken, moet de query de volgende kolommen retourneren:

- `Timestamp`
- Een van de volgende kolommen voor apparaat, gebruiker of postvak:
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - `SenderFromAddress`(afzender envelop of retourpadadres)
    - `SenderMailFromAddress`(afzenderadres weergegeven per e-mailclient)
    - `RecipientObjectId`
    - `AccountSid`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`
>[!NOTE]
>Ondersteuning voor extra entiteiten wordt toegevoegd als er nieuwe tabellen worden toegevoegd aan het [geavanceerde jachtschema](advanced-hunting-schema-tables.md).

Eenvoudige query's, zoals query's `project` die `summarize` de operator niet gebruiken om resultaten aan te passen of samen te voegen, retourneren doorgaans deze algemene kolommen.

Er zijn verschillende manieren om ervoor te zorgen dat complexere query's deze kolommen retourneren. Als u bijvoorbeeld de voorkeur geeft aan aggregaat `DeviceId`en telt `Timestamp` op entiteit onder een kolom zoals `DeviceId`, u nog steeds terugkeren door deze te verkrijgen van de meest recente gebeurtenis waarbij elke unieke.

De onderstaande voorbeeldquery telt het`DeviceId`aantal unieke machines ( ) met antivirusdetecties en gebruikt dit aantal om alleen de machines met meer dan vijf detecties te vinden. Om de `Timestamp`laatste keer `summarize` terug te `arg_max` keren, gebruikt het de operator met de functie.

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType == "AntivirusDetection"
| summarize Timestamp = max(Timestamp), count() by DeviceId
| where count_ > 5
```
### <a name="2-create-new-rule-and-provide-alert-details"></a>2. Maak een nieuwe regel en geef waarschuwingsgegevens op.

Selecteer met de query in de queryeditor **de detectieregel maken** en geef de volgende waarschuwingsdetails op:

- **Detectienaam** — naam van de detectieregel
- **Frequentie** : interval voor het uitvoeren van de query en het uitvoeren van actie. [Zie aanvullende richtlijnen hieronder](#rule-frequency)
- **Waarschuwingstitel** — titel weergegeven met waarschuwingen die door de regel worden geactiveerd
- **Ernst** — potentieel risico van de component of activiteit die door de regel is geïdentificeerd
- **Categorie** — bedreigingscomponent of activiteit die door de regel is geïdentificeerd
- **MITRE ATT&CK technieken** - een of meer aanvalstechnieken geïdentificeerd door de regel zoals gedocumenteerd in de [MITRE ATT&CK kader](https://attack.mitre.org/)
- **Beschrijving** — meer informatie over de component of activiteit die door de regel is geïdentificeerd 
- **Aanbevolen acties** : extra acties die responders kunnen uitvoeren als reactie op een waarschuwing

#### <a name="rule-frequency"></a>Regelfrequentie
Wanneer deze wordt opgeslagen, wordt een nieuwe of bewerkte aangepaste detectieregel onmiddellijk uitgevoerd en gecontroleerd op overeenkomsten van de afgelopen 30 dagen aan gegevens. De regel wordt vervolgens opnieuw uitgevoerd met vaste intervallen en terugkijkduur op basis van de frequentie die u kiest:

- **Elke 24 uur** - loopt elke 24 uur, het controleren van gegevens van de afgelopen 30 dagen
- **Elke 12 uur** - loopt elke 12 uur, het controleren van gegevens van de afgelopen 24 uur
- **Elke 3 uur** - loopt elke 3 uur, het controleren van gegevens van de afgelopen 6 uur
- **Elk uur** - loopt per uur, het controleren van gegevens van de afgelopen 2 uur

Selecteer de frequentie die overeenkomt met hoe nauw u detecties wilt controleren en houd rekening met het vermogen van uw organisatie om op de waarschuwingen te reageren.

### <a name="3-choose-the-impacted-entities"></a>3. Kies de getroffen entiteiten.
Identificeer de kolommen in uw queryresultaten waar u verwacht de belangrijkste of getroffen entiteit te vinden. Een query kan bijvoorbeeld afzender`SenderFromAddress` `SenderMailFromAddress`- of`RecipientEmailAddress`geadresseerde () adressen retourneren. Als u identificeert welke van deze kolommen de belangrijkste getroffen entiteit zijn, kan de service relevante waarschuwingen samenvoegen, incidenten correleren en acties voor doelrespons uitvoeren.

U slechts één kolom selecteren voor elk entiteitstype (postvak, gebruiker of apparaat). Kolommen die niet door uw query worden geretourneerd, kunnen niet worden geselecteerd.

### <a name="4-specify-actions-on-files-or-machines"></a>4. Geef acties op bestanden of machines op.
Uw aangepaste detectieregel kan automatisch acties uitvoeren op bestanden of machines die door de query worden geretourneerd.

#### <a name="actions-on-machines"></a>Acties op machines
Deze acties worden toegepast `DeviceId` op machines in de kolom van de queryresultaten:
- **Machine isoleren** — gebruikt Microsoft Defender ATP om volledige netwerkisolatie toe te passen, waardoor de machine geen verbinding kan maken met een toepassing of service. [Meer informatie over Microsoft Defender ATP-machineisolatie](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-machines-from-the-network)
- **Onderzoekspakket verzamelen** — verzamelt machinegegevens in een ZIP-bestand. [Meer informatie over het Microsoft Defender ATP-onderzoekspakket](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-machines)
- **Antivirusscan uitvoeren** — voert een volledige Windows Defender Antivirus-scan uit op de machine
- **Start onderzoek** — start een [geautomatiseerd onderzoek](mtp-autoir.md) naar de machine

#### <a name="actions-on-files"></a>Acties op bestanden
Wanneer deze optie is geselecteerd, wordt de `InitiatingProcessSHA1` `SHA256`actie `InitiatingProcessSHA256` **Quarantainebestand** uitgevoerd op bestanden in de `SHA1`kolom , of kolom van de queryresultaten. Met deze actie wordt het bestand van de huidige locatie verwijderd en wordt een kopie in quarantaine geplaatst.

> [!NOTE]
> De actie voor aangepaste detectieregels toestaan of blokkeren, wordt momenteel niet ondersteund op Microsoft Threat Protection.

### <a name="5-set-the-rule-scope"></a>5. Stel het regelbereik in.
Stel het bereik in om op te geven welke apparaten onder de regel vallen. Het bereik beïnvloedt regels die apparaten controleren en heeft geen invloed op regels die alleen postvakken en gebruikersaccounts of identiteiten controleren.

Wanneer u het bereik instelt, u het beste selecteren:

- Alle apparaten
- Specifieke apparaatgroepen

Alleen gegevens van apparaten in het bereik worden opgevraagd. Ook zullen acties alleen worden uitgevoerd op deze apparaten.

### <a name="6-review-and-turn-on-the-rule"></a>6. De regel controleren en inschakelen.
Nadat u de regel hebt gecontroleerd, klikt u op **Maken** om deze op te slaan. De aangepaste detectieregel wordt onmiddellijk uitgevoerd. Het wordt opnieuw uitgevoerd op basis van geconfigureerde frequentie om te controleren op overeenkomsten, waarschuwingen te genereren en reactieacties uit te voeren.

## <a name="manage-existing-custom-detection-rules"></a>Bestaande aangepaste detectieregels beheren
U de lijst met bestaande aangepaste detectieregels bekijken, de eerdere uitvoeringen controleren en de waarschuwingen bekijken die ze hebben geactiveerd. U ook een regel op aanvraag uitvoeren en deze wijzigen.

### <a name="view-existing-rules"></a>Bestaande regels weergeven

Als u alle bestaande aangepaste detectieregels wilt weergeven, navigeert u naar**Detecties voor aangepaste** **jacht** > . De pagina bevat alle regels met de volgende run informatie:

- **Laatste run** : wanneer een regel voor het laatst is uitgevoerd om te controleren op queryovereenkomsten en waarschuwingen te genereren
- **Status van laatste run** : of een regel is uitgevoerd
- **Volgende run** — de volgende geplande run
- **Status** — of een regel is in- of uitgeschakeld

### <a name="view-rule-details-modify-rule-and-run-rule"></a>Regeldetails weergeven, regel wijzigen en regel uitvoeren

Als u uitgebreide informatie over een aangepaste detectieregel wilt weergeven, selecteert u de naam van de regel in de lijst met regels in **Detecties voor aangepaste** > **jacht**. Hiermee wordt een pagina geopend over de aangepaste detectieregel met algemene informatie over de regel, inclusief de details van de waarschuwing, de status van de uitvoeren en het bereik. Het biedt ook de lijst met geactiveerde waarschuwingen en geactiveerde acties.

![Pagina Met aangepaste detectieregeldetails](../../media/custom-detection-details.png)<br>
*Aangepaste detectieregeldetails*

Op deze pagina u ook de volgende acties op de regel uitvoeren:

- **Uitvoeren** : voer de regel onmiddellijk uit. Hiermee wordt ook het interval voor de volgende run gereset.
- **Bewerken** : de regel wijzigen zonder de query te wijzigen
- **Query wijzigen** — de query bewerken in geavanceerde jacht
- **Uitschakelen inschakelen** / **Turn off** — de regel inschakelen of stoppen met werken
- **Verwijderen** — de regel uitschakelen en verwijderen

### <a name="view-and-manage-triggered-alerts"></a>Geactiveerde waarschuwingen weergeven en beheren

Ga in het scherm regeldetails **(Aangepaste** > **detecties** > **zoeken [Regelnaam]** naar **Geactiveerde waarschuwingen** om de lijst met waarschuwingen te bekijken die worden gegenereerd door overeenkomsten met de regel. Selecteer een waarschuwing om gedetailleerde informatie over die waarschuwing weer te geven en de volgende acties uit te voeren op die waarschuwing:

- De waarschuwing beheren door de status en classificatie in te stellen (true of false alert)
- De waarschuwing koppelen aan een incident
- Voer de query uit die de waarschuwing heeft geactiveerd bij geavanceerde jacht

### <a name="review-actions"></a>Acties bekijken
Ga in het scherm regeldetails **(Aangepaste** > **detecties** > **zoeken [Regelnaam]** naar **Geactiveerde acties** om de lijst met acties te bekijken die zijn uitgevoerd op basis van overeenkomsten met de regel.

>[!TIP]
>Als u snel informatie wilt weergeven en actie wilt ondernemen voor een item in een tabel, gebruikt u de selectiekolom [&#10003;] links van de tabel.

## <a name="related-topic"></a>Gerelateerd onderwerp
- [Overzicht van aangepaste detectie](custom-detections-overview.md)
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [Leer de geavanceerde jachtquerytaal](advanced-hunting-query-language.md)
