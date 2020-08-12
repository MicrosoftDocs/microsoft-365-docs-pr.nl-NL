---
title: Aangepaste detectieregels maken en beheren in Microsoft Threat Protection
description: Meer informatie over het maken en beheren van aangepaste opspoor regels op basis van geavanceerde jacht-query's
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, aangepaste detectie, regels, schema, kusto, Microsoft 365, Microsoft Threat Protection, RBAC, machtigingen, Microsoft Defender ATP
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
ms.openlocfilehash: cea4dbcb42833a14980d092bd0ff168ca97e5934
ms.sourcegitcommit: 9489aaf255f8bf165e6debc574e20548ad82e882
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/11/2020
ms.locfileid: "46632149"
---
# <a name="create-and-manage-custom-detections-rules"></a>Aangepaste detectieregels maken en beheren

**Van toepassing op:**
- Microsoft Threat Protection

Met instellingen voor aangepaste detectieregels van [geavanceerde jacht](advanced-hunting-overview.md) -query's kunt u verschillende gebeurtenissen en systeem Staten proactief bijhouden, waaronder verdachte schendings activiteiten en onjuist geconfigureerde eindpunten. U kunt instellen dat ze met regelmatige tussenpozen worden uitgevoerd, en de acties voor het maken van waarschuwingen worden gegenereerd wanneer er overeenkomsten zijn.

## <a name="required-permissions-for-managing-custom-detections"></a>Vereiste machtigingen voor het beheren van aangepaste detecties

Als u aangepaste detecties wilt beheren, moet u een van de volgende rollen toewijzen:

- **Beveiligingsbeheerder** : de rol beveiligingsbeheerder of beveiligingsbeheerder is een [Azure Active Directory-rol](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) voor het beheren van diverse beveiligingsinstellingen in Microsoft 365 Beveiligingscentrum en diverse portals en services.

- **Beveiligings operator** : de rol van beveiligings operator is een [Azure Active Directory-rol](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) voor het beheren van waarschuwingen en bevat algemene alleen-lezen toegang voor beveiligingsfuncties, waaronder alle informatie in Microsoft 365 Beveiligingscentrum. Deze functie is voldoende voor het beheren van alleen aangepaste detecties als op rollen gebaseerd toegangsbeheer (RBAC) is uitgeschakeld in Microsoft Defender ATP. Als u de webversie van de webversie hebt geconfigureerd, moet u ook de machtiging **Beveiligingsinstellingen beheren** voor Microsoft Defender ATP hebben.

Een **globale beheerder** kan het volgende doen om de vereiste machtigingen te beheren:

- Wijs de rol **beveiligingsbeheerder** of **beveiligings operator** toe in [Microsoft 365-Beheercentrum](https://admin.microsoft.com/) onder **rollen**  >  **beveiligingsbeheerder**.
- Schakel in Microsoft Defender- [Beveiligingscentrum](https://securitycenter.windows.com/) de optie voor het **instellen**van  >  **toegangsrechten**voor Microsoft Defender in  >  **Roles**. Selecteer de bijbehorende rol om de machtiging **Beveiligingsinstellingen beheren** toe te wijzen.

> [!NOTE]
> Als u aangepaste detecties wilt beheren, moeten **beveiligings operatoren** de machtiging **Beveiligingsinstellingen beheren** in Microsoft Defender ATP hebben.

## <a name="create-a-custom-detection-rule"></a>Een aangepaste detectieregel maken
### <a name="1-prepare-the-query"></a>1. de query voorbereiden.

In Microsoft 365 Beveiligingscentrum gaat u naar **geavanceerde jacht** en selecteert u een bestaande query of maakt u een nieuwe query. Wanneer u een nieuwe query gebruikt, voert u de query uit om fouten te identificeren en mogelijke resultaten te begrijpen.

>[!IMPORTANT]
>Om te voorkomen dat de service te veel waarschuwingen retourneert, is elke regel beperkt tot het genereren van slechts 100 waarschuwingen, telkens wanneer deze wordt uitgevoerd. Voordat u een regel maakt, kunt u de query aanpassen om waarschuwingen voor normale, dagelijkse activiteiten te voorkomen.


#### <a name="required-columns-in-the-query-results"></a>Vereiste kolommen in de queryresultaten
Als u een aangepaste detectieregel wilt maken, moet de query de volgende kolommen retourneren:

- `Timestamp`
- Een van de volgende kolommen van het apparaat, de gebruiker of het postvak:
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - `SenderFromAddress`(envelop zender of adres van afzender)
    - `SenderMailFromAddress`(afzenderadres weergegeven via e-mailclient)
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`
>[!NOTE]
>Ondersteuning voor aanvullende entiteiten wordt toegevoegd naarmate nieuwe tabellen worden toegevoegd aan het [schema voor geavanceerde jacht](advanced-hunting-schema-tables.md).

Eenvoudige query's, zoals personen die de `project` operator or niet gebruiken `summarize` om resultaten aan te passen of te combineren, retourneren doorgaans deze veelvoorkomende kolommen.

U kunt deze kolommen op verschillende manieren weergeven. Als u bijvoorbeeld wilt samenvoegen door een entiteit onder een kolom `DeviceId` , kunt u nog steeds terugkeren met behulp `Timestamp` van de meest recente gebeurtenis waarbij deze uniek is `DeviceId` .

Met de onderstaande voorbeeldquery wordt het aantal unieke apparaten ( `DeviceId` ) geteld en wordt dit aantal gebruikt om te zoeken naar de apparaten met meer dan vijf detecties. Om de meest recente waarde te retourneren `Timestamp` , wordt de `summarize` operator met de `arg_max` functie gebruikt.

```kusto
DeviceEvents
| where ActionType == "AntivirusDetection"
| summarize Timestamp = max(Timestamp), count() by DeviceId, SHA1, InitiatingProcessAccountObjectId 
| where count_ > 5
```

### <a name="2-create-new-rule-and-provide-alert-details"></a>2. nieuwe regel maken en waarschuwingsgegevens geven.

Met de query in query editor selecteert u **detectieregel maken** en de volgende waarschuwingsdetails opgeven:

- **Detectie naam** : de naam van de detectieregel
- **Frequentie** : interval voor het uitvoeren van de query en het uitvoeren van de actie. [Zie extra richtlijnen.](#rule-frequency)
- **Naam van waarschuwing** : titel weergegeven met waarschuwingen die door de regel worden geactiveerd
- **Ernst** : potentieel risico van het onderdeel of de activiteit die door de regel wordt geïdentificeerd
- **Categorie** : bedreigings onderdeel of activiteit aangeduid door de regel
- **Mitre ATT&VERzonken technieken** : een of meer aanvals technieken, aangeduid met de regel zoals beschreven in de [Mitre att&verzonken raam](https://attack.mitre.org/). Deze sectie is niet van toepassing en is verborgen voor bepaalde waarschuwings categorieën, waaronder malware, Ransomware, verdachte activiteiten en ongewenste software
- **Beschrijving** : meer informatie over het onderdeel of de activiteit die door de regel wordt geïdentificeerd 
- **Aanbevolen acties** : aanvullende acties die reageren op antwoord in antwoord op een waarschuwing

#### <a name="rule-frequency"></a>Regel frequentie
Wanneer de gegevens zijn opgeslagen, worden de nieuwe of bewerkte aangepaste detectieregels direct uitgevoerd en gecontroleerd op resultaten van de afgelopen 30 dagen. De regel wordt vervolgens weer op vaste tijden en lookback-duur weer op basis van de frequentie die u kiest:

- **Elke 24 uur** (elke 24 uur) wordt elke 24 uur gecontroleerd en gegevens van de afgelopen 30 dagen gecontroleerd
- **Elke 12 uur** (elke 12 uur) wordt elke 12 uur gecontroleerd, met gegevens van de afgelopen 24 uur
- **Elke 3 uur** : elke 3 uur, waarop gegevens van de afgelopen 6 uur worden gecontroleerd
- **Elk uur** – loopt per uur af en controleert gegevens van de afgelopen 2 uur

Selecteer de frequentie waarmee wordt aangegeven hoe nauwkeurig opspoort en kijk of de capaciteit van uw organisatie moet reageren op meldingen.

### <a name="3-choose-the-impacted-entities"></a>3. Kies de beïnvloede entiteiten.
Identificeer de kolommen in de queryresultaten waar u naar verwachting de belangrijkste beïnvloede of geinvloedte entiteit wilt vinden. Als u bijvoorbeeld een query hebt, kunnen de adressen van de afzender ( `SenderFromAddress` of `SenderMailFromAddress` ) en de geadresseerden () worden geretourneerd `RecipientEmailAddress` . Als u identificeert welke van deze kolommen de belangrijkste impact entiteit vertegenwoordigen, helpt de service relevante waarschuwingen, relatie gebeurtenissen en doel acties te verzamelen.

U kunt slechts één kolom selecteren voor elk type entiteit (Postvak, gebruiker of apparaat). Kolommen die niet door de query worden geretourneerd, kunnen niet worden geselecteerd.

### <a name="4-specify-actions"></a>4. Geef acties op.
Met uw aangepaste detectieregel kunnen automatisch acties worden uitgevoerd op apparaten, bestanden of gebruikers die door de query worden geretourneerd.

#### <a name="actions-on-devices"></a>Acties op apparaten
Deze acties worden toegepast op apparaten in de `DeviceId` kolom van de queryresultaten:
- **Isoleer apparaat** : met Microsoft Defender ATP kunt u volledige netwerkisolatie toepassen, zodat het apparaat geen verbinding kan maken met een toepassing of service. [Meer informatie over Microsoft Defender ATP machine-isolatie](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- **Onderzoek pakket verzamelen** : apparaatgegevens in een zip-bestand verzamelen. [Meer informatie over het onderzoek pakket voor Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- **Voer antivirus scan uit** : een volledige Windows Defender antivirus scan uitvoeren op het apparaat
- **Onderzoek starten** — een [geautomatiseerd onderzoek](mtp-autoir.md) op het toestel initiëren
- **App-uitvoering beperken** : Hiermee stelt u beperkingen in voor de toegang tot bestanden die zijn ondertekend met een door Microsoft uitgegeven certificaat. [Meer informatie over app-beperkingen met Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a>Acties voor bestanden
Wanneer deze optie is geselecteerd, kunt u ervoor kiezen om de actie van het **quarantaine bestand** toe te passen op bestanden in de `SHA1` `InitiatingProcessSHA1` kolommen, `SHA256` of, of `InitiatingProcessSHA256` de kolom van de queryresultaten. Met deze actie verwijdert u het bestand van de huidige locatie en plaatst u een kopie in Quarantine.

#### <a name="actions-on-users"></a>Acties voor gebruikers
Wanneer dit selectievakje is ingeschakeld, wordt de **gebruiker markeren als ongeoorloofde** actie gebruikt voor gebruikers in de `AccountObjectId` `InitiatingProcessAccountObjectId` kolom, of de `RecipientObjectId` kolom van de queryresultaten. Met deze actie stelt u het risiconiveau van gebruikers in op ' hoog ' in azure Active Directory, waarbij het bijbehorende [beleid voor identiteitsbeveiliging](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)wordt geactiveerd.

> [!NOTE]
> De actie toestaan of blokkeren voor aangepaste detectieregels wordt momenteel niet ondersteund in Microsoft Threat Protection.

### <a name="5-set-the-rule-scope"></a>5. het regelbereik instellen.
Stel het bereik in om op te geven welke apparaten de regel bedekt. Het bereik van regels voor het controleren van apparaten en heeft geen invloed op de regels die alleen postvakken en gebruikersaccounts of identiteiten controleren.

Wanneer u het bereik instelt, kunt u het volgende selecteren:

- Alle apparaten
- Specifieke apparaatgroepen

Alleen gegevens van apparaten in het bereik worden met een query opgevraagd. Daarnaast worden de acties alleen op die apparaten gezet.

### <a name="6-review-and-turn-on-the-rule"></a>6. Controleer de regel en schakel deze in.
Wanneer u de regel hebt gecontroleerd, klikt u op **maken** om de regel op te slaan. De aangepaste detectieregel wordt onmiddellijk uitgevoerd. De app wordt opnieuw uitgevoerd op basis van de geconfigureerde frequentie om te controleren op overeenkomsten, waarschuwingen te genereren en antwoord acties te ondernemen.

## <a name="manage-existing-custom-detection-rules"></a>Bestaande aangepaste detectieregels beheren
U kunt de lijst met bestaande regels voor detectie detecteren, de eerdere uitvoering ervan controleren en de waarschuwingen bekijken die zijn geactiveerd. U kunt ook op aanvraag een regel toepassen en wijzigen.

### <a name="view-existing-rules"></a>Bestaande regels weergeven

Als u alle bestaande aangepaste detectieregels wilt weergeven, gaat u naar aangepaste detectie van **jacht**  >  **Custom detections**. Op de pagina worden alle regels met de volgende informatie over de uitvoeringsrun weergegeven:

- **Laatste uitvoering** , wanneer een regel de laatste keer is uitgevoerd om te controleren op query overeenkomsten en waarschuwingen te genereren
- **Status laatste uitvoering** : of een regel met succesvol is uitgevoerd
- **Volgende uitvoering** , de volgende geplande uitvoeringsrun
- **Status** : of een regel is in-of uitgeschakeld

### <a name="view-rule-details-modify-rule-and-run-rule"></a>Regeldetails weergeven, regel wijzigen en regel uitvoeren

Als u uitgebreide informatie over een aangepaste detectieregel wilt bekijken, selecteert u de naam van de regel in de **Hunting**lijst met regels op  >  **aangepaste detectie**van jacht. Hiermee opent u een pagina over de aangepaste detectieregel met algemene informatie over de regel, waaronder de details van de waarschuwing, de uitvoer status en het bereik. Het biedt ook de lijst met geactiveerde waarschuwingen en geactiveerde acties.

![Pagina Details van aangepaste detectieregel](../../media/custom-detection-details.png)<br>
*Details van aangepaste detectieregels*

U kunt ook de volgende acties uitvoeren op de regel van deze pagina:

- **Uitvoeren** — Voer de regel onmiddellijk uit. Hiermee wordt ook het interval voor de volgende uitvoering hersteld.
- **Bewerken** — de regel wijzigen zonder de query te wijzigen
- **Query wijzigen** : de query bewerken in de geavanceerde jacht
- **Inschakelen**  /  **Uitschakelen – de** regel inschakelen of stoppen met uitvoeren
- **Verwijderen** – de regel uitschakelen en verwijderen

### <a name="view-and-manage-triggered-alerts"></a>Geactiveerde waarschuwingen weergeven en beheren

Ga in het scherm regeldetails **(**  >  **aangepaste detectie**van de  >  **regelnaam]**) naar **geactiveerde waarschuwingen** om de lijst weer te geven met waarschuwingen die zijn gegenereerd door overeenkomsten met de regel. Selecteer een waarschuwing voor het weergeven van gedetailleerde informatie over die waarschuwing en voer de volgende handelingen uit op de melding:

- De waarschuwing beheren door de status en classificatie van de waarschuwing in te stellen (waar of onwaar)
- De waarschuwing aan een incident koppelen
- Voer de query uit om de waarschuwing te activeren voor de geavanceerde jacht

### <a name="review-actions"></a>Acties controleren
Ga in het scherm regeldetails**Hunting**(  >  **aangepaste detectie**door jacht  >  **[regelnaam]**) naar **geactiveerde acties** om de lijst met acties weer te geven die zijn gemaakt op basis van overeenkomsten met de regel.

>[!TIP]
>Om snel informatie weer te geven en actie te ondernemen voor een item in een tabel, gebruikt u de selectie kolom [&#10003;] links van de tabel.

## <a name="related-topic"></a>Verwante onderwerpen
- [Overzicht van aangepaste detectie](custom-detections-overview.md)
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [Meer informatie over de querytaal Advanced jacht](advanced-hunting-query-language.md)