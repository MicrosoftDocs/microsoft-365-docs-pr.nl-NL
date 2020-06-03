---
title: Aangepaste detectieregels maken en beheren in Microsoft Threat Protection
description: Meer informatie over het maken en beheren van aangepaste detectieregels op basis van geavanceerde jachtquery's
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, aangepaste detecties, regels, schema, kusto, Microsoft 365, Microsoft Threat Protection, RBAC, machtigingen, Microsoft Defender ATP
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
ms.openlocfilehash: 1a84c568d1411cf21c23e59cabad955c40c18ac6
ms.sourcegitcommit: 7bb3d8a93a85246172e2499d6c58c390e46f5bb9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/02/2020
ms.locfileid: "44498361"
---
# <a name="create-and-manage-custom-detections-rules"></a>Aangepaste detectieregels maken en beheren

**Van toepassing op:**
- Microsoft Threat Protection

Met aangepaste detectieregels die zijn gebaseerd op geavanceerde jachtquery's u proactief verschillende gebeurtenissen en systeemtoestanden controleren, waaronder vermoedelijke inbreukactiviteit en verkeerd geconfigureerde eindpunten. [Advanced hunting](advanced-hunting-overview.md) U instellen dat ze op regelmatige tijdstippen worden uitgevoerd, waarschuwingen genereren en responsacties uitvoeren wanneer er overeenkomsten zijn.

## <a name="required-permissions-for-managing-custom-detections"></a>Vereiste machtigingen voor het beheren van aangepaste detecties

Als u aangepaste detecties wilt beheren, moet u een van deze rollen toegewezen krijgen:

- **Beveiligingsbeheerder** : de rol van beveiligingsbeheerder of beveiligingsbeheerder is een [Azure Active Directory-rol](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) voor het beheren van verschillende beveiligingsinstellingen in het Microsoft 365-beveiligingscentrum en verschillende portals en services.

- **Beveiligingsoperator** : de rol van de beveiligingsoperator is een [Azure Active Directory-rol](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) voor het beheren van waarschuwingen en heeft algemene alleen-lezen toegang tot beveiligingsfuncties, inclusief alle informatie in het Microsoft 365-beveiligingscentrum. Deze rol is alleen voldoende voor het beheren van aangepaste detecties als role-based access control (RBAC) is uitgeschakeld in Microsoft Defender ATP. Als u RBAC hebt geconfigureerd, hebt u ook de **machtiging voor beveiligingsinstellingen voor** Microsoft Defender ATP nodig.

Als u vereiste machtigingen wilt beheren, kan een **globale beheerder** het volgende doen:

- Wijs de rol **van beveiligingsbeheerder** of **beveiligingsoperator** toe in [het Microsoft 365-beheercentrum](https://admin.microsoft.com/) onder **Beheer van**  >  **Rollenbeveiliging**.
- Controleer RBAC-instellingen voor Microsoft Defender ATP in [Microsoft Defender Security Center](https://securitycenter.windows.com/) onder Rollen **Machtigingen**  >  **Permissions**  >  **instellingen**. Selecteer de bijbehorende rol om de **machtiging beveiligingsinstellingen beheren** toe te wijzen.

> [!NOTE]
> Om aangepaste detecties te beheren, hebben **beveiligingsoperatoren** de **machtiging voor beveiligingsinstellingen beheren** in Microsoft Defender ATP nodig als RBAC is ingeschakeld.

## <a name="create-a-custom-detection-rule"></a>Een aangepaste detectieregel maken
### <a name="1-prepare-the-query"></a>1. Bereid de query voor.

Ga in het Microsoft 365-beveiligingscentrum naar **Geavanceerd jagen** en selecteer een bestaande query of maak een nieuwe query. Voer bij het gebruik van een nieuwe query de query uit om fouten te identificeren en mogelijke resultaten te begrijpen.

#### <a name="required-columns-in-the-query-results"></a>Vereiste kolommen in de queryresultaten
Als u een aangepaste detectieregel wilt maken, moet de query de volgende kolommen retourneren:

- `Timestamp`
- Een van de volgende kolommen van het apparaat, gebruiker of postvak:
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - `SenderFromAddress`(afzender van envelop of retouradres)
    - `SenderMailFromAddress`(afzenderadres weergegeven per e-mailclient)
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`
>[!NOTE]
>Ondersteuning voor extra entiteiten wordt toegevoegd als er nieuwe tabellen worden toegevoegd aan het [geavanceerde jachtschema](advanced-hunting-schema-tables.md).

Eenvoudige query's, zoals query's die de of operator niet gebruiken `project` om resultaten aan te passen of samen te `summarize` voegen, retourneren deze algemene kolommen meestal.

Er zijn verschillende manieren om ervoor te zorgen dat complexere query's deze kolommen retourneren. Als u bijvoorbeeld liever aggregaat en telt op entiteit onder een kolom zoals `DeviceId` , u nog steeds terugkeren door deze te halen uit de meest recente gebeurtenis met elk uniek `Timestamp` `DeviceId` .

De onderstaande voorbeeldquery telt het aantal unieke apparaten `DeviceId` () met antivirusdetecties en gebruikt dit aantal om alleen de apparaten met meer dan vijf detecties te vinden. Om het laatste nieuws terug te `Timestamp` geven, wordt de `summarize` operator met de functie `arg_max` gebruikt.

```kusto
DeviceEvents
| where ActionType == "AntivirusDetection"
| summarize Timestamp = max(Timestamp), count() by DeviceId, SHA1, InitiatingProcessAccountObjectId 
| where count_ > 5
```
### <a name="2-create-new-rule-and-provide-alert-details"></a>2. Maak een nieuwe regel en geef waarschuwingsgegevens op.

Selecteer bij de query in de queryeditor **detectieregel maken** en geef de volgende waarschuwingsdetails op:

- **Detectienaam** — naam van de detectieregel
- **Frequentie** — interval voor het uitvoeren van de query en het uitvoeren van actie. [Zie hieronder aanvullende richtlijnen](#rule-frequency)
- **Waarschuwingstitel** — titel weergegeven met waarschuwingen die door de regel zijn geactiveerd
- **Ernst** — potentieel risico van de component of activiteit die door de regel wordt geïdentificeerd
- **Categorie** — bedreigingscomponent of -activiteit die door de regel wordt geïdentificeerd
- **MITRE ATT&CK-technieken** — een of meer aanvalstechnieken die door de regel zijn geïdentificeerd zoals gedocumenteerd in het [MITRE ATT&CK-framework](https://attack.mitre.org/). Deze sectie is niet van toepassing en is verborgen voor bepaalde waarschuwingscategorieën, waaronder malware, ransomware, verdachte activiteiten en ongewenste software
- **Beschrijving** — meer informatie over de component of activiteit die door de regel wordt geïdentificeerd 
- **Aanbevolen acties** — aanvullende acties die responders kunnen ondernemen als reactie op een waarschuwing

#### <a name="rule-frequency"></a>Regelfrequentie
Wanneer deze is opgeslagen, wordt er onmiddellijk een nieuwe of bewerkte aangepaste detectieregel uitgevoerd en gecontroleerd op overeenkomsten van de afgelopen 30 dagen aan gegevens. De regel wordt vervolgens opnieuw uitgevoerd met vaste intervallen en terugkijkduur op basis van de frequentie die u kiest:

- **Elke 24 uur** - draait elke 24 uur, het controleren van gegevens van de afgelopen 30 dagen
- **Elke 12 uur** - draait elke 12 uur, het controleren van gegevens van de afgelopen 24 uur
- **Elke 3 uur** - draait elke 3 uur, het controleren van gegevens van de afgelopen 6 uur
- **Elk uur** - draait elk uur, het controleren van gegevens van de afgelopen 2 uur

Selecteer de frequentie die overeenkomt met hoe nauwkeurig u detecties wilt controleren en houd rekening met het vermogen van uw organisatie om op de waarschuwingen te reageren.

### <a name="3-choose-the-impacted-entities"></a>3. Kies de getroffen entiteiten.
Identificeer de kolommen in uw queryresultaten waar u verwacht de belangrijkste betrokken of getroffen entiteit te vinden. Een query kan bijvoorbeeld adressen van afzender `SenderFromAddress` (of `SenderMailFromAddress` ) en geadresseerden ( ) `RecipientEmailAddress` retourneren. Als u identificeert welke van deze kolommen de belangrijkste beïnvloede entiteit vertegenwoordigt, kan de service relevante waarschuwingen samenvoegen, incidenten correleren en doelresponsacties uitvoeren.

U slechts één kolom selecteren voor elk entiteitstype (postvak, gebruiker of apparaat). Kolommen die niet worden geretourneerd door uw query, kunnen niet worden geselecteerd.

### <a name="4-specify-actions"></a>4. Geef acties op.
Uw aangepaste detectieregel kan automatisch acties uitvoeren op apparaten, bestanden of gebruikers die door de query worden geretourneerd.

#### <a name="actions-on-devices"></a>Acties op apparaten
Deze acties worden toegepast op apparaten in de `DeviceId` kolom van de queryresultaten:
- **Apparaat isoleren** — gebruikt Microsoft Defender ATP om volledige netwerkisolatie toe te passen, waardoor het apparaat geen verbinding kan maken met een toepassing of service. [Meer informatie over de isolatie van Microsoft Defender ATP-machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-machines-from-the-network)
- **Verzamel een onderzoekspakket** : verzamelt apparaatgegevens in een ZIP-bestand. [Meer informatie over het ATP-onderzoekspakket van Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-machines)
- **Antivirusscan uitvoeren** — voert een volledige Windows Defender Antivirus-scan uit op het apparaat
- **Onderzoek initiëren** — start een [geautomatiseerd onderzoek](mtp-autoir.md) op het apparaat
- **App-uitvoering beperken** : stelt beperkingen in op het apparaat om alleen bestanden die zijn ondertekend met een door Microsoft uitgegeven certificaat uit te voeren, toe te staan. [Meer informatie over app-beperkingen met Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a>Acties in bestanden
Wanneer u is geselecteerd, u ervoor kiezen de **actie Quarantainebestand** toe te passen op bestanden in de `SHA1` kolom, ' of kolom van de `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` queryresultaten. Met deze actie wordt het bestand verwijderd van de huidige locatie en wordt een kopie in quarantaine geplaatst.

#### <a name="actions-on-users"></a>Acties voor gebruikers
Wanneer deze optie is geselecteerd, wordt de **gebruiker markeren als gecompromitteerde** actie uitgevoerd op gebruikers in de `AccountObjectId` kolom , of kolom van de `InitiatingProcessAccountObjectId` `RecipientObjectId` queryresultaten. Met deze actie wordt het risiconiveau van gebruikers ingesteld op 'hoog' in Azure Active Directory, waardoor het bijbehorende beleid voor [identiteitsbescherming wordt geactiveerd.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)

> [!NOTE]
> De actie voor het toestaan of blokkeren van aangepaste detectieregels wordt momenteel niet ondersteund op Microsoft Threat Protection.

### <a name="5-set-the-rule-scope"></a>5. Stel het regelbereik in.
Stel het bereik in om op te geven welke apparaten onder de regel vallen. Het bereik is van invloed op regels die apparaten controleren en heeft geen invloed op regels die alleen postvakken en gebruikersaccounts of identiteiten controleren.

Wanneer u het bereik instelt, u het:' selecteren:

- Alle apparaten
- Specifieke apparaatgroepen

Alleen gegevens van apparaten in het bereik worden opgevraagd. Ook zullen acties alleen worden uitgevoerd op die apparaten.

### <a name="6-review-and-turn-on-the-rule"></a>6. Bekijk en schakel de regel in.
Nadat u de regel hebt gecontroleerd, klikt u op **Maken** om deze op te slaan. De aangepaste detectieregel wordt onmiddellijk uitgevoerd. Het wordt opnieuw uitgevoerd op basis van de geconfigureerde frequentie om te controleren op overeenkomsten, waarschuwingen te genereren en responsacties uit te voeren.

## <a name="manage-existing-custom-detection-rules"></a>Bestaande aangepaste detectieregels beheren
U de lijst met bestaande aangepaste detectieregels bekijken, de vorige runs controleren en de waarschuwingen bekijken die ze hebben geactiveerd. U ook een regel op aanvraag uitvoeren en deze wijzigen.

### <a name="view-existing-rules"></a>Bestaande regels weergeven

Als u alle bestaande aangepaste detectieregels wilt weergeven, gaat u naar aangepaste detecties **voor**  >  **jacht.** De pagina bevat alle regels met de volgende uitvoeringsinformatie:

- **Laatste run** — wanneer een regel voor het laatst werd uitgevoerd om te controleren op queryovereenkomsten en waarschuwingen te genereren
- **Laatste run-status** : of een regel is uitgevoerd
- **Volgende run** — de volgende geplande run
- **Status** — of een regel is ingeschakeld of uitgeschakeld

### <a name="view-rule-details-modify-rule-and-run-rule"></a>Regeldetails weergeven, regel wijzigen en regel uitvoeren

Als u uitgebreide informatie over een aangepaste detectieregel wilt weergeven, selecteert u de naam van de regel in de lijst met regels in **Hunting**  >  **aangepaste detecties**op jacht. Hiermee wordt een pagina geopend over de aangepaste detectieregel met algemene informatie over de regel, inclusief de details van de waarschuwing, de uitvoeringsstatus en het bereik. Het biedt ook de lijst met geactiveerde waarschuwingen en geactiveerde acties.

![Pagina met aangepaste detectieregeldetails](../../media/custom-detection-details.png)<br>
*Aangepaste detectieregeldetails*

U ook de volgende acties uitvoeren op de regel op deze pagina:

- **Uitvoeren** — voer de regel onmiddellijk uit. Hiermee wordt ook het interval voor de volgende run gereset.
- **Bewerken** — de regel wijzigen zonder de query te wijzigen
- **Query wijzigen** — de query bewerken in geavanceerde jacht
- **Inschakelen**  /  **Uitschakelen** : de regel inschakelen of voorkomen dat deze wordt uitgevoerd
- **Verwijderen:** schakel de regel uit en verwijder deze

### <a name="view-and-manage-triggered-alerts"></a>Geactiveerde waarschuwingen weergeven en beheren

Ga in het scherm met details van de regel (**Aangepaste**  >  **detecties**  >  **[Regelnaam]** op jacht ), naar **Geactiveerde waarschuwingen** om de lijst met waarschuwingen te bekijken die zijn gegenereerd door overeenkomsten met de regel. Selecteer een waarschuwing om gedetailleerde informatie over die waarschuwing weer te geven en de volgende acties op die waarschuwing uit te voeren:

- De waarschuwing beheren door de status en classificatie in te stellen (true of false alert)
- De waarschuwing koppelen aan een incident
- De query uitvoeren die de waarschuwing op geavanceerde jacht heeft geactiveerd

### <a name="review-actions"></a>Acties bekijken
Ga in het**Hunting**scherm met details van de regel (  >  **Aangepaste detecties**  >  **[Regelnaam]** op jacht naar **Geactiveerde acties** om de lijst met acties te bekijken die zijn uitgevoerd op basis van overeenkomsten met de regel.

>[!TIP]
>Als u snel informatie wilt weergeven en actie wilt ondernemen op een item in een tabel, gebruikt u de selectiekolom [&#10003;] links van de tabel.

## <a name="related-topic"></a>Gerelateerd onderwerp
- [Overzicht van aangepaste detectie](custom-detections-overview.md)
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [Leer de geavanceerde jachtquerytaal](advanced-hunting-query-language.md)