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
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d58292f658446259bfab5b1b55c8b462d081421c
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080621"
---
# <a name="create-and-manage-custom-detections-rules"></a>Aangepaste detectieregels maken en beheren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Aangepaste detectieregels zijn regels die u kunt ontwerpen en aanpassen met geavanceerde zoekquery's. [](advanced-hunting-overview.md) Met deze regels kunt u proactief diverse gebeurtenissen en systeemvoorschriften controleren, waaronder verdachte inbreuken en onjuist geconfigureerde eindpunten. U kunt instellen dat deze worden uitgevoerd met regelmatige tussenpozen, waarschuwingen genereren en actie ondernemen wanneer er overeenkomsten zijn.

## <a name="required-permissions-for-managing-custom-detections"></a>Vereiste machtigingen voor het beheren van aangepaste detecties

Als u aangepaste detecties wilt beheren, moet u een van de volgende rollen toegewezen krijgen:

- **Beveiligingsbeheerder:** gebruikers met deze [Azure Active Directory-rol](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) kunnen beveiligingsinstellingen beheren in het Microsoft 365-beveiligingscentrum en andere portals en services.

- **Beveiligingsoperator:** gebruikers met deze [Azure Active Directory-rol](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) kunnen waarschuwingen beheren en globale alleen-lezentoegang hebben tot beveiligingsfuncties, inclusief alle informatie in het Microsoft 365-beveiligingscentrum. Deze rol is alleen voldoende voor het beheren van aangepaste detecties als toegangsbeheer op basis van rollen is uitgeschakeld in Microsoft Defender for Endpoint. Als u RBAC hebt geconfigureerd,  moet u ook de machtiging Beveiligingsinstellingen beheren voor Defender voor eindpunt hebben.

Een globale beheerder kan het volgende doen om vereiste **machtigingen te** beheren:

- Wijs de **rol van beveiligingsbeheerder** of **beveiligingsoperator** toe in het [Microsoft 365-beheercentrum](https://admin.microsoft.com/) onder   >  **Rollenbeveiligingsbeheerder.**
- Controleer de toegangsstructuurinstellingen voor Microsoft Defender voor het eindpunt in [het Microsoft Defender-beveiligingscentrum](https://securitycenter.windows.com/) onder **Instellingen**  >  **Machtigingenrollen.**  >   Selecteer de bijbehorende rol om de machtiging beveiligingsinstellingen **beheren toe te** wijzen.

> [!NOTE]
> Voor het beheren van aangepaste detecties hebben **beveiligingsoperatoren** de machtiging beveiligingsinstellingen in Microsoft Defender voor eindpunt nodig als RBAC is ingeschakeld. 

## <a name="create-a-custom-detection-rule"></a>Een aangepaste detectieregel maken
### <a name="1-prepare-the-query"></a>1. Bereid de query voor.

Ga in het Microsoft 365-beveiligingscentrum naar **Geavanceerd** zoeken en selecteer een bestaande query of maak een nieuwe query. Wanneer u een nieuwe query gebruikt, kunt u de query uitvoeren om fouten te identificeren en de mogelijke resultaten te begrijpen.

>[!IMPORTANT]
>Om te voorkomen dat de service te veel waarschuwingen retourneert, is elke regel beperkt tot het genereren van slechts 100 waarschuwingen wanneer deze wordt uitgevoerd. Voordat u een regel maakt, kunt u de query aanpassen om te voorkomen dat u een waarschuwing uitvoert voor normale, dagelijkse activiteiten.


#### <a name="required-columns-in-the-query-results"></a>Vereiste kolommen in de queryresultaten
Als u een aangepaste detectieregel wilt maken, moet de query de volgende kolommen retourneren:

- `Timestamp`— gebruikt voor het instellen van de tijdstempel voor gegenereerde waarschuwingen
- `ReportId`— schakelt zoekactie naar de oorspronkelijke records in
- Een van de volgende kolommen voor het identificeren van specifieke apparaten, gebruikers of postvakken:
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - `SenderFromAddress` (afzender van enveloppen of Return-Path-adres)
    - `SenderMailFromAddress` (afzenderadres weergegeven door e-mailclient)
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
>Ondersteuning voor aanvullende entiteiten wordt toegevoegd wanneer nieuwe tabellen worden toegevoegd aan het [geavanceerde schema voor zoeken.](advanced-hunting-schema-tables.md)

Eenvoudige query's, zoals query's die de operator of operator niet gebruiken om resultaten aan te passen of samen te gebruiken, retourneren meestal `project` `summarize` deze gemeenschappelijke kolommen.

Er zijn verschillende manieren om ervoor te zorgen dat complexere query's deze kolommen retourneren. Als u bijvoorbeeld de voorkeur geeft aan aggregeren en tellen per entiteit onder een kolom, kunt u deze nog steeds retourneren van de meest recente gebeurtenis met betrekking tot `DeviceId` `Timestamp` elke unieke `ReportId` `DeviceId` gebeurtenis.

Met de onderstaande voorbeeldquery wordt het aantal unieke apparaten () met antivirusdetecties geteld en wordt dit aantal gebruikt om alleen apparaten met meer dan `DeviceId` vijf detecties te vinden. Voor het retourneren van de meest recente gegevens en de bijbehorende `Timestamp` functie wordt de operator met de functie `ReportId` `summarize` `arg_max` gebruikt.

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> Voor betere queryprestaties stelt u een tijdfilter in dat overeenkomt met de geplande frequentie van uitvoeren voor de regel. Aangezien de meest voorkomende run _om de 24 uur_ is, worden alle nieuwe gegevens verzameld door te filteren op de afgelopen dag.

### <a name="2-create-new-rule-and-provide-alert-details"></a>2. Nieuwe regel maken en details over waarschuwingen verstrekken.

Met de query in de queryeditor selecteert u **Detectieregel maken** en geeft u de volgende waarschuwingsdetails op:

- **Naam van detectie:** naam van de detectieregel
- **Interval** voor het uitvoeren van de query en het uitvoeren van actie. [Zie de onderstaande aanvullende richtlijnen](#rule-frequency)
- **Naam van waarschuwing:** titel weergegeven met waarschuwingen die worden geactiveerd door de regel
- **Ernst:** potentieel risico van het onderdeel of de activiteit die wordt geïdentificeerd door de regel
- **Category**— threat component or activity identified by the rule
- **MITRE ATT&CK-technieken**: een of meer technieken voor aanvallen die door de regel zijn geïdentificeerd zoals gedocumenteerd in het [MITRE ATT&CK Framework.](https://attack.mitre.org/) Deze sectie is verborgen voor bepaalde categorieën van waarschuwingen, waaronder malware, ransomware, verdachte activiteiten en ongewenste software.
- **Beschrijving:** meer informatie over het onderdeel of de activiteit die wordt geïdentificeerd door de regel 
- **Aanbevolen acties**: extra acties die beantwoorders kunnen uitvoeren in reactie op een waarschuwing

#### <a name="rule-frequency"></a>Regelfrequentie
Wanneer u een nieuwe regel op slaan of bewerken, wordt deze uitgevoerd en worden de overeenkomsten van de afgelopen 30 dagen met gegevens gecontroleerd. De regel wordt vervolgens opnieuw uitgevoerd met vaste intervallen, met een terugslagduur op basis van de gekozen frequentie:

- **Elke 24 uur –** elke 24 uur wordt de gegevens van de afgelopen 30 dagen gecontroleerd
- **Elke 12 uur –** elke 12 uur wordt de gegevens van de afgelopen 24 uur gecontroleerd
- **Elke 3 uur**- elke 3 uur wordt de gegevens van de afgelopen 6 uur gecontroleerd
- **Elk uur**- elk uur wordt uitgevoerd, de gegevens van de afgelopen 2 uur controleren

>[!TIP]
> De tijdfilters in de query laten overeenkomen met de duur van het terugkijken. Resultaten buiten de opgeslagen duur worden genegeerd.  

Selecteer de frequentie die overeenkomt met hoe nauw u detecties wilt controleren. Houd rekening met de capaciteit van uw organisatie om te reageren op de waarschuwingen.

### <a name="3-choose-the-impacted-entities"></a>3. Kies de beïnvloede entiteiten.
Identificeer de kolommen in de queryresultaten waarin u verwacht de belangrijkste betrokken of beïnvloede entiteit te vinden. Een query kan bijvoorbeeld adressen van afzender ( `SenderFromAddress` of ) en ontvanger `SenderMailFromAddress` `RecipientEmailAddress` () retourneren. Door te bepalen welke van deze kolommen de belangrijkste beïnvloede entiteit vertegenwoordigt, kan de service relevante waarschuwingen samenvoegen, incidenten correleren en actie op basis van doelreacties uitvoeren.

U kunt slechts één kolom selecteren voor elk entiteitstype (postvak, gebruiker of apparaat). Kolommen die niet door de query worden geretourneerd, kunnen niet worden geselecteerd.

### <a name="4-specify-actions"></a>4. Acties opgeven.
De aangepaste detectieregel kan automatisch acties uitvoeren op apparaten, bestanden of gebruikers die door de query worden geretourneerd.

#### <a name="actions-on-devices"></a>Acties op apparaten
Deze acties worden toegepast op apparaten in de `DeviceId` kolom van de queryresultaten:
- **Isoleert apparaat**— gebruikt Microsoft Defender voor eindpunt om volledige netwerkisolatie toe te passen, waardoor het apparaat geen verbinding kan maken met een toepassing of service. [Meer informatie over computerisolatie van Microsoft Defender voor eindpunt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- **Collect investigation package**— collects device information in a ZIP file. [Meer informatie over het Microsoft Defender for Endpoint-onderzoekspakket](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- **Antivirusscan uitvoeren**— voer een volledige Windows Defender Antivirus-scan uit op het apparaat
- **Onderzoek starten**: start een [geautomatiseerd onderzoek](mtp-autoir.md) op het apparaat
- **Uitvoer van apps beperken:** hiermee stelt u beperkingen in voor het apparaat, zodat alleen bestanden worden uitgevoerd die zijn ondertekend met een door Microsoft uitgegeven certificaat. [Meer informatie over app-beperkingen met Microsoft Defender voor eindpunt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a>Acties op bestanden
Als deze optie is geselecteerd, kunt u de actie **Quarantainebestand** toepassen op bestanden in `SHA1` de , of kolom van de `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` queryresultaten. Met deze actie wordt het bestand van de huidige locatie verwijderd en wordt een kopie in quarantaine geplaatst.

#### <a name="actions-on-users"></a>Acties voor gebruikers
Als deze optie **is** geselecteerd, wordt de actie Gebruiker markeren als gecompromitteerd uitgevoerd op gebruikers in de kolom of in de `AccountObjectId` `InitiatingProcessAccountObjectId` `RecipientObjectId` queryresultaten. Met deze actie stelt u het risiconiveau van gebruikers in op 'hoog' in Azure Active Directory, wat het bijbehorende [identiteitsbeveiligingsbeleid activeert.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)

> [!NOTE]
> De actie toestaan of blokkeren voor aangepaste detectieregels wordt momenteel niet ondersteund op Microsoft 365 Defender.

### <a name="5-set-the-rule-scope"></a>5. Stel het bereik van de regel in.
Stel het bereik in om aan te geven op welke apparaten de regel van toepassing is. Het bereik is van invloed op regels die apparaten controleren en is niet van invloed op regels die alleen postvakken en gebruikersaccounts of identiteiten controleren.

Wanneer u het bereik instelt, kunt u het volgende selecteren:

- Alle apparaten
- Specifieke apparaatgroepen

Alleen gegevens van apparaten binnen het bereik worden opgevraagd. Ook worden er alleen acties ondernomen op deze apparaten.

### <a name="6-review-and-turn-on-the-rule"></a>6. Controleer de regel en schakel deze in.
Nadat u de regel heeft beoordeeld, **selecteert u Maken om** deze op te slaan. De aangepaste detectieregel wordt onmiddellijk uitgevoerd. Het wordt opnieuw uitgevoerd op basis van de geconfigureerde frequentie voor het controleren op overeenkomsten, het genereren van waarschuwingen en het uitvoeren van reactieacties.

## <a name="manage-existing-custom-detection-rules"></a>Bestaande regels voor aangepaste detectie beheren
U kunt de lijst met bestaande regels voor aangepaste detectie bekijken, de vorige versies controleren en de waarschuwingen bekijken die zijn geactiveerd. U kunt ook een regel op aanvraag uitvoeren en wijzigen.

### <a name="view-existing-rules"></a>Bestaande regels weergeven

Als u alle bestaande aangepaste detectieregels wilt weergeven, gaat u naar **Aangepaste**  >  **detecties zoeken.** De pagina bevat alle regels met de volgende gegevens voor het uitvoeren van gegevens:

- **Laatst uitgevoerd:** wanneer een regel voor het laatst werd uitgevoerd om te controleren op query-overeenkomsten en waarschuwingen te genereren
- **Status laatst uitgevoerd,** ongeacht of een regel is uitgevoerd
- **Volgende run**: de volgende geplande run
- **Status:** of een regel is in- of uitgeschakeld

### <a name="view-rule-details-modify-rule-and-run-rule"></a>Regeldetails weergeven, regel wijzigen en regel uitvoeren

Als u uitgebreide informatie over een aangepaste detectieregel wilt bekijken, gaat u naar **Aangepast** zoeken en selecteert u  >   de naam van de regel. U kunt vervolgens algemene informatie over de regel bekijken, inclusief de status en het bereik van de regel. De pagina bevat ook een lijst met geactiveerde waarschuwingen en acties.

![Pagina met details van aangepaste detectieregel](../../media/custom-detection-details.png)<br>
*Details van aangepaste detectieregel*

U kunt ook vanaf deze pagina de volgende acties uitvoeren op de regel:

- **Voer** de regel direct uit. Hiermee wordt ook het interval voor de volgende run opnieuw ingesteld.
- **Bewerken**: de regel wijzigen zonder de query te wijzigen
- **Query wijzigen**: de query bewerken in geavanceerd zoeken
- **In-/uit**  /  **Uitschakelen :** schakel de regel in of stop het uitvoeren van de regel
- **Verwijderen:** de regel uitschakelen en verwijderen

### <a name="view-and-manage-triggered-alerts"></a>Geactiveerde waarschuwingen weergeven en beheren

Ga in het detailscherm van de regel **(Zoeken** naar aangepaste  >  **detecties**  >  **[regelnaam]** naar Geactiveerde waarschuwingen, waarin de waarschuwingen worden weergegeven die worden gegenereerd door overeenkomsten met de regel. Selecteer een waarschuwing om gedetailleerde informatie te bekijken en de volgende acties uit te voeren:

- De waarschuwing beheren door de status en classificatie van de waarschuwing in te stellen (waar of onwaar)
- De waarschuwing aan een incident koppelen
- Voer de query uit die de waarschuwing heeft geactiveerd op geavanceerde zoekopdrachten

### <a name="review-actions"></a>Acties controleren
Ga in het detailscherm van de regel **(zoeken** naar aangepaste  >  **detecties**  >  **[regelnaam]** naar Geactiveerde acties, waarin de acties worden weergegeven die zijn gemaakt op basis van de regel.

>[!TIP]
>Als u snel informatie wilt weergeven en actie wilt ondernemen voor een item in een tabel, gebruikt u de selectiekolom [&#10003;] links van de tabel.

## <a name="see-also"></a>Zie ook
- [Overzicht van aangepaste detectie](custom-detections-overview.md)
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De geavanceerde zoekquerytaal leren](advanced-hunting-query-language.md)
- [Geavanceerde zoekquery's migreren van Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mdatp.md)
