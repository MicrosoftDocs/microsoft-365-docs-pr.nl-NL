---
title: Aangepaste detectieregels maken en beheren in Microsoft 365 Defender
description: Informatie over het maken en beheren van aangepaste detectieregels op basis van geavanceerde zoekquery's
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, custom detections, rules, schema, kusto, microsoft 365, Microsoft Threat Protection, RBAC, permissions, Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 220e4e6546899dd00f3a02bf83039a928be4f8dc
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498849"
---
# <a name="create-and-manage-custom-detections-rules"></a>Aangepaste detectieregels maken en beheren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Aangepaste detectieregels zijn regels die u kunt ontwerpen en aanpassen met behulp van [geavanceerde zoekquery's.](advanced-hunting-overview.md) Met deze regels kunt u proactief verschillende gebeurtenissen en systeemstaten controleren, waaronder verdachte inbreukactiviteiten en verkeerd geconfigureerde eindpunten. U kunt instellen dat ze regelmatig worden uitgevoerd, waarschuwingen genereren en antwoordacties uitvoeren wanneer er overeenkomsten zijn.

## <a name="required-permissions-for-managing-custom-detections"></a>Vereiste machtigingen voor het beheren van aangepaste detecties

Als u aangepaste detecties wilt beheren, moet u een van de volgende rollen krijgen:

- **Beveiligingsbeheerder:** gebruikers met deze [Azure Active Directory-rol](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) kunnen beveiligingsinstellingen beheren in het Microsoft 365-beveiligingscentrum en andere portals en services.

- **Beveiligingsoperator:** gebruikers met deze [Azure Active Directory-rol](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) kunnen waarschuwingen beheren en hebben globale alleen-lezen toegang tot beveiligingsfuncties, inclusief alle informatie in het Microsoft 365-beveiligingscentrum. Deze rol is alleen voldoende voor het beheren van aangepaste detecties als RBAC (Role Based Access Control) is uitgeschakeld in Microsoft Defender voor Eindpunt. Als u RBAC hebt geconfigureerd,  hebt u ook de machtiging beveiligingsinstellingen voor Defender voor Eindpunt nodig.

Als u vereiste machtigingen wilt beheren, kan een **globale beheerder** het volgende doen:

- Wijs de **rol van de** beveiligingsbeheerder of **beveiligingsoperator** toe in [het Microsoft 365-beheercentrum](https://admin.microsoft.com/) onder   >  **Rollenbeveiligingsbeheerder.**
- Controleer RBAC-instellingen voor Microsoft Defender voor Eindpunt in [het Microsoft Defender-beveiligingscentrum](https://securitycenter.windows.com/) onder **Instellingen**  >  **Machtigingen**  >  **Rollen**. Selecteer de bijbehorende rol om de machtiging **beveiligingsinstellingen beheren toe te** wijzen.

> [!NOTE]
> Als u aangepaste detecties wilt  beheren, hebben **beveiligingsoperatoren** de machtiging beveiligingsinstellingen in Microsoft Defender voor Eindpunt nodig als RBAC is ingeschakeld.

## <a name="create-a-custom-detection-rule"></a>Een aangepaste detectieregel maken
### <a name="1-prepare-the-query"></a>1. De query voorbereiden.

Ga in het Microsoft 365-beveiligingscentrum naar Geavanceerd **zoeken** en selecteer een bestaande query of maak een nieuwe query. Wanneer u een nieuwe query gebruikt, moet u de query uitvoeren om fouten te identificeren en mogelijke resultaten te begrijpen.

>[!IMPORTANT]
>Als u wilt voorkomen dat de service te veel waarschuwingen retourneert, is elke regel beperkt tot het genereren van slechts 100 waarschuwingen wanneer deze wordt uitgevoerd. Voordat u een regel maakt, kunt u de query aanpassen om te voorkomen dat u een waarschuwing voor normale, dagelijkse activiteiten uitvoert.


#### <a name="required-columns-in-the-query-results"></a>Vereiste kolommen in de queryresultaten
Als u een aangepaste detectieregel wilt maken, moet de query de volgende kolommen retourneren:

- `Timestamp`—gebruikt om de tijdstempel in te stellen voor gegenereerde waarschuwingen
- `ReportId`—hiermee kunt u opzoekingen voor de oorspronkelijke records in
- Een van de volgende kolommen die specifieke apparaten, gebruikers of postvakken identificeren:
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - `SenderFromAddress` (afzender van envelop of Return-Path adres)
    - `SenderMailFromAddress` (afzenderadres weergegeven door e-mailclient)
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
>Ondersteuning voor extra entiteiten wordt toegevoegd als er nieuwe tabellen worden toegevoegd aan het [geavanceerde schema voor de jacht.](advanced-hunting-schema-tables.md)

Eenvoudige query's, zoals query's die de operator of operator niet gebruiken om resultaten aan te passen of te aggregeren, retourneert meestal `project` `summarize` deze algemene kolommen.

Er zijn verschillende manieren om ervoor te zorgen dat complexere query's deze kolommen retourneren. Als u bijvoorbeeld liever wilt aggregeren en tellen per entiteit onder een kolom zoals , kunt u deze nog steeds retourneren en deze verkrijgen van de meest recente gebeurtenis waarbij elke unieke gebeurtenis `DeviceId` `Timestamp` betrokken `ReportId` `DeviceId` is.

De voorbeeldquery hieronder telt het aantal unieke apparaten () met antivirusdetecties en gebruikt dit aantal om alleen de apparaten met meer dan `DeviceId` vijf detecties te vinden. Als u de meest recente `Timestamp` en de bijbehorende `ReportId` functie wilt retourneren, wordt de `summarize` operator met de functie `arg_max` gebruikt.

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> Voor betere queryprestaties stelt u een tijdfilter in dat overeenkomt met de geplande runfrequentie voor de regel. Aangezien de minst voorkomende run elke _24 uur_ is, worden alle nieuwe gegevens bestrijken door te filteren op de afgelopen dag.

### <a name="2-create-new-rule-and-provide-alert-details"></a>2. Maak een nieuwe regel en geef waarschuwingsdetails op.

Met de query in de queryeditor selecteert u **Detectieregel maken** en geeft u de volgende waarschuwingsdetails op:

- **Detectienaam**:naam van de detectieregel
- **Frequentie:** interval voor het uitvoeren van de query en het uitvoeren van actie. [Zie aanvullende richtlijnen hieronder](#rule-frequency)
- **Waarschuwingstitel**: titel weergegeven met waarschuwingen die door de regel worden geactiveerd
- **Ernst :** potentieel risico van het onderdeel of de activiteit die door de regel is geïdentificeerd
- **Categorie**:bedreigingscomponent of activiteit die door de regel is geïdentificeerd
- **MITRE ATT&CK-technieken**( een of meer aanvalstechnieken die door de regel zijn geïdentificeerd zoals beschreven in het [MITRE ATT-&CK-framework](https://attack.mitre.org/). Deze sectie is verborgen voor bepaalde waarschuwingscategorieën, waaronder malware, ransomware, verdachte activiteiten en ongewenste software
- **Beschrijving**: meer informatie over het onderdeel of de activiteit die door de regel is geïdentificeerd 
- **Aanbevolen acties**: aanvullende acties die reageren op een waarschuwing

#### <a name="rule-frequency"></a>Regelfrequentie
Wanneer u een nieuwe regel op te slaan, wordt deze uitgevoerd en gecontroleerd op overeenkomsten uit de afgelopen 30 dagen met gegevens. De regel wordt vervolgens opnieuw uitgevoerd met vaste intervallen, met een terugslagduur op basis van de frequentie die u kiest:

- **Elke 24 uur :** wordt elke 24 uur uitgevoerd en controleert gegevens uit de afgelopen 30 dagen
- **Elke 12 uur :** wordt elke 12 uur uitgevoerd en controleert gegevens uit de afgelopen 24 uur
- **Elke 3 uur :** wordt elke 3 uur uitgevoerd en controleert gegevens uit de afgelopen 6 uur
- **Elk uur**: wordt elk uur uitgevoerd en de gegevens van de afgelopen 2 uur worden gecontroleerd

Wanneer u een regel bewerkt, worden deze uitgevoerd met de toegepaste wijzigingen in de volgende run time die is gepland op basis van de frequentie die u hebt ingesteld.



>[!TIP]
> De tijdfilters in de query overeenkomen met de duur van de terugblik. Resultaten buiten de terugblikduur worden genegeerd.  

Selecteer de frequentie die overeenkomt met hoe nauw u detecties wilt controleren. Houd rekening met de capaciteit van uw organisatie om op de waarschuwingen te reageren.

### <a name="3-choose-the-impacted-entities"></a>3. Kies de beïnvloede entiteiten.
Identificeer de kolommen in de queryresultaten waar u de belangrijkste beïnvloede of beïnvloede entiteit verwacht te vinden. Een query kan bijvoorbeeld adressen van afzender `SenderFromAddress` (of `SenderMailFromAddress` ) en geadresseerde `RecipientEmailAddress` () retourneren. Door te bepalen welke van deze kolommen de belangrijkste beïnvloede entiteit vertegenwoordigt, kan de service relevante waarschuwingen, correlerende incidenten en doelreactieacties aggregeren.

U kunt slechts één kolom selecteren voor elk entiteitstype (postvak, gebruiker of apparaat). Kolommen die niet door uw query worden geretourneerd, kunnen niet worden geselecteerd.

### <a name="4-specify-actions"></a>4. Geef acties op.
Uw aangepaste detectieregel kan automatisch acties uitvoeren op apparaten, bestanden of gebruikers die door de query worden geretourneerd.

#### <a name="actions-on-devices"></a>Acties op apparaten
Deze acties worden toegepast op apparaten in de `DeviceId` kolom van de queryresultaten:
- **Apparaat isoleren:** hiermee wordt Microsoft Defender voor Eindpunt gebruikt om volledige netwerkisolatie toe te passen, waardoor het apparaat geen verbinding kan maken met een toepassing of service. [Meer informatie over machineisolatie van Microsoft Defender voor eindpunten](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- **Verzamel onderzoekspakket:** verzamelt apparaatgegevens in een ZIP-bestand. [Meer informatie over het Microsoft Defender for Endpoint-onderzoekspakket](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- **Antivirusscan uitvoeren**: voert een volledige Windows Defender Antivirus-scan uit op het apparaat
- **Onderzoek starten**: start een [geautomatiseerd onderzoek](m365d-autoir.md) op het apparaat
- **De uitvoering van apps** beperken: hiermee stelt u beperkingen in op het apparaat om alleen bestanden toe te staan die zijn ondertekend met een door Microsoft uitgegeven certificaat. [Meer informatie over app-beperkingen met Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a>Acties op bestanden
Wanneer geselecteerd, kunt u ervoor kiezen om de actie **Quarantainebestand** toe te passen op bestanden in `SHA1` de , of kolom van de `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` queryresultaten. Met deze actie wordt het bestand van de huidige locatie verwijderd en wordt een kopie in quarantaine geplaatst.

#### <a name="actions-on-users"></a>Acties voor gebruikers
Wanneer deze optie **is** geselecteerd, wordt de actie Gebruiker markeren als gecompromitteerd uitgevoerd op gebruikers in de , of kolom van de `AccountObjectId` `InitiatingProcessAccountObjectId` `RecipientObjectId` queryresultaten. Met deze actie wordt het risiconiveau voor gebruikers in Azure Active Directory op 'hoog' gebracht, wat het [bijbehorende identiteitsbeveiligingsbeleid activeert.](/azure/active-directory/identity-protection/overview-identity-protection)

> [!NOTE]
> De actie toestaan of blokkeren voor aangepaste detectieregels wordt momenteel niet ondersteund in Microsoft 365 Defender.

### <a name="5-set-the-rule-scope"></a>5. Stel het regelbereik in.
Stel het bereik in om op te geven welke apparaten onder de regel vallen. Het bereik is van invloed op regels die apparaten controleren en hebben geen invloed op regels die alleen postvakken en gebruikersaccounts of identiteiten controleren.

Wanneer u het bereik instelt, kunt u het volgende selecteren:

- Alle apparaten
- Specifieke apparaatgroepen

Alleen gegevens van apparaten in bereik worden opgevraagd. Acties worden ook alleen op die apparaten ondernomen.

### <a name="6-review-and-turn-on-the-rule"></a>6. Controleer de regel en schakel deze in.
Nadat u de regel heeft beoordeeld, **selecteert u Maken om** deze op te slaan. De aangepaste detectieregel wordt onmiddellijk uitgevoerd. Deze wordt opnieuw uitgevoerd op basis van de geconfigureerde frequentie om te controleren op overeenkomsten, waarschuwingen te genereren en antwoordacties uit te voeren.


>[!Important] 
>Aangepaste detecties moeten regelmatig worden gecontroleerd op efficiëntie en effectiviteit. Als u wilt controleren of u detecties maakt die echte waarschuwingen activeren, neemt u de tijd om uw bestaande aangepaste detecties te bekijken door de stappen in Bestaande aangepaste detectieregels [beheren te volgen.](#manage-existing-custom-detection-rules) <br>  
U behoudt de controle over de breedheid of specificiteit van uw aangepaste detecties, zodat eventuele foutmeldingen die door aangepaste detecties worden gegenereerd, kunnen aangeven dat bepaalde parameters van de regels moeten worden gewijzigd.


## <a name="manage-existing-custom-detection-rules"></a>Bestaande aangepaste detectieregels beheren
U kunt de lijst met bestaande aangepaste detectieregels bekijken, de eerdere versies controleren en de waarschuwingen bekijken die ze hebben geactiveerd. U kunt ook een regel op aanvraag uitvoeren en deze wijzigen.

### <a name="view-existing-rules"></a>Bestaande regels weergeven

Als u alle bestaande aangepaste detectieregels wilt weergeven, gaat u naar **Aangepaste**  >  **detecties opzoeken.** Op de pagina vindt u alle regels met de volgende gegevens:

- **Laatst uitgevoerd:** wanneer een regel voor het laatst is uitgevoerd om te controleren op query's en waarschuwingen te genereren
- **Status laatst uitgevoerd**: of een regel is uitgevoerd
- **Volgende run**: de volgende geplande run
- **Status**, ongeacht of een regel is ingeschakeld of uitgeschakeld

### <a name="view-rule-details-modify-rule-and-run-rule"></a>Regeldetails weergeven, regel wijzigen en regel uitvoeren

Als u uitgebreide informatie over een aangepaste detectieregel wilt weergeven, gaat u naar **Op** zoek naar aangepaste  >  **detecties** en selecteert u vervolgens de naam van de regel. U kunt vervolgens algemene informatie over de regel bekijken, inclusief de status en het bereik van de regel. De pagina bevat ook de lijst met geactiveerde waarschuwingen en acties.

![Pagina Met details van aangepaste detectieregel](../../media/custom-detection-details.png)<br>
*Details van aangepaste detectieregel*

U kunt ook de volgende acties uitvoeren op de regel op deze pagina:

- **Uitvoeren:** voer de regel onmiddellijk uit. Hiermee wordt ook het interval voor de volgende run opnieuw ingesteld.
- **Bewerken**: wijzig de regel zonder de query te wijzigen
- **Query wijzigen:** bewerk de query in geavanceerde zoekopdrachten
- **In- en uit-**  /  **Uitschakelen :de** regel inschakelen of stoppen met uitvoeren
- **Verwijderen**: schakel de regel uit en verwijder deze

### <a name="view-and-manage-triggered-alerts"></a>Getriggerde waarschuwingen weergeven en beheren

Ga in het scherm Met regeldetails **(Op** zoek naar aangepaste  >  **detecties**  >  **[regelnaam] naar** Geactiveerde waarschuwingen , waarin de waarschuwingen worden weergegeven die worden gegenereerd door overeenkomsten met de regel. Selecteer een waarschuwing om gedetailleerde informatie over de waarschuwing weer te geven en de volgende acties uit te voeren:

- De waarschuwing beheren door de status en classificatie in te stellen (waar of onwaar)
- De waarschuwing koppelen aan een incident
- Voer de query uit die de waarschuwing bij geavanceerd zoeken heeft geactiveerd

### <a name="review-actions"></a>Acties controleren
Ga in het scherm Met regeldetails **(Op** zoek naar aangepaste  >  **detecties**  >  **[regelnaam] naar** Geactiveerde acties , waarin de acties worden vermeld die zijn gemaakt op basis van overeenkomsten met de regel.

>[!TIP]
>Als u snel informatie wilt weergeven en actie wilt ondernemen voor een item in een tabel, gebruikt u de selectiekolom [&#10003;] links van de tabel.

## <a name="see-also"></a>Zie ook
- [Overzicht van aangepaste detectie](custom-detections-overview.md)
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De geavanceerde zoekquerytaal leren](advanced-hunting-query-language.md)
- [Geavanceerde zoekquery's migreren van Microsoft Defender voor Eindpunt](advanced-hunting-migrate-from-mde.md)
