---
title: Geavanceerde controle gebruiken om verdachte accounts te onderzoeken
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Gebruik de postvakcontroleactie MailItemsAccessed om onderzoek te doen naar gehackte gebruikersaccounts.
ms.openlocfilehash: 64f3e5f3423f5182277fe7640199a39dc11068f2
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288777"
---
# <a name="use-advanced-audit-to-investigate-compromised-accounts"></a>Geavanceerde controle gebruiken om verdachte accounts te onderzoeken

Een gehackt gebruikersaccount (ook wel een *accountovername* genoemd) is een type aanval waarbij kwaadwillende gebruikers toegang krijgen tot een gebruikersaccount en gebruikersacties kunnen uitvoeren. Dit type aanvallen kan soms meer schade veroorzaken dan de aanvaller mogelijk heeft bedoeld. Bij het onderzoeken van gehackte e-mailaccounts moet u ervan uitgaan dat er meer e-mailgegevens zijn gehackt dan op het eerste gezicht het geval lijkt door de werkelijke aanwezigheid van de aanvaller te traceren. Afhankelijk van het type gegevens in e-mailberichten, moet u ervan uitgaan dat gevoelige informatie in gevaar is gebracht of dat u te maken krijgt met wettelijke boetes, tenzij u kunt bewijzen dat gevoelige informatie niet openbaar is geworden. Zo kunnen organisaties die aan de HIPAA-regelgeving moeten voldoen rekenen op aanzienlijke boetes als er bewijs is dat patiëntenzorginformatie (PHI) openbaar is geworden. In dit geval zullen kwaadwillende gebruikers waarschijnlijk niet geïnteresseerd zijn in PHI. Toch moeten organisaties een melding maken van het lekken van gegevens, tenzij ze het tegendeel kunnen aantonen.

Om u te helpen bij het onderzoeken van gehackte e-mailaccounts controleren we nu de toegang van e-mailgegevens door e-mailprotocollen en -clients met de *MailItemsAccessed*-actie voor postvakcontrole. Deze nieuwe controleactie helpt gebruikers een beter inzicht te krijgen in inbreuken op e-mailgegevens en de omvang van aanvallen in kaart te brengen voor specifieke e-mailitems die mogelijk zijn gehackt. Deze nieuwe controleactie is bedoeld om te controleren of bepaalde e-mailgegevens niet zijn gehackt. Als kwaadwillende gebruikers toegang tot een bepaald e-mailbericht hebben gekregen, controleert Exchange Online die gebeurtenis, ook al is er geen bewijs dat het e-mailitem daadwerkelijk is gelezen.

## <a name="the-mailitemsaccessed-mailbox-auditing-action"></a>De postvakcontroleactie MailItemsAccessed

De nieuwe actie MailItemsAccessed maakt deel uit van de nieuwe functionaliteit [Geavanceerde audit](advanced-audit.md). De actie maakt deel uit van de [controle van Exchange-postvakken](/office365/securitycompliance/enable-mailbox-auditing#mailbox-auditing-actions) en is standaard ingeschakeld voor gebruikers met een Office 365- of Microsoft 365 E5-licentie of voor organisaties met een Microsoft 365 E5 compliance-abonnement.

De actie MailItemsAccessed voor postvakcontroleactie heeft betrekking op alle e-mailprotocollen: POP, IMAP, MAPI, EWS, Exchange ActiveSync en REST. Daarnaast worden beide soorten toegang tot e-mail (*sync* en *bind*) ondersteund.

### <a name="auditing-sync-access"></a>Synchronisatietoegang controleren

Synchronisatiebewerkingen worden alleen opgenomen wanneer een postvak wordt gebruikt in een bureaubladversie van de Outlook-client voor Windows of Mac. Tijdens de synchronisatie door deze clients meestal een groot aantal e-mailitems gedownload van de cloud naar een lokale computer. Het auditvolume voor synchronisatiebewerkingen is enorm. Daarom genereren we geen controlerecord voor elk e-mailitem dat wordt gesynchroniseerd, maar we een controlegebeurtenis voor de e-mailmap met items die zijn gesynchroniseerd. Daardoor wordt aangenomen dat *alle* e-mailitems in de gesynchroniseerde map zijn gehackt. Het toegangstype wordt vastgelegd in het veld OperationProperties van de auditrecord.

Zie stap 2 in de sectie [MailItemsAccessed-auditrecords gebruiken voor forenstisch onderzoek](#use-mailitemsaccessed-audit-records-for-forensic-investigations) voor een voorbeeld van het weergeven van het type synchronisatietoegang in een controlerecord.

### <a name="auditing-bind-access"></a>Bind-toegang controleren

Een bind-bewerking is een afzonderlijke toegang tot een e-mailbericht. Voor bind-toegang wordt de InternetMessageId van afzonderlijke berichten opgenomen in de auditrecord. De MailItemsAccessed-controleactie registreert bind-bewerkingen en voegt deze samen tot één controlerecord. Alle bind-bewerkingen die binnen een interval van twee minuten plaatsvinden, worden samengevoegd in één controlerecord in het veld Folders binnen de eigenschap AuditData. Elk bericht dat is geopend, wordt geïdentificeerd aan de hand van de InternetMessageId. Het aantal bind-bewerkingen dat in de record is samengevoegd, wordt weergegeven in het veld OperationCount in de eigenschap AuditData.

Zie stap 4 in de sectie [MailItemsAccessed-auditrecords gebruiken voor forenstisch onderzoek](#use-mailitemsaccessed-audit-records-for-forensic-investigations) voor een voorbeeld van het weergeven van het type bind-toegang in een controlerecord.

### <a name="throttling-of-mailitemsaccessed-audit-records"></a>MailItemsAccessed-controlerecords beperken

Als er binnen 24 uur meer dan 1000 MailItemsAccessed-controlerecords worden gegenereerd, worden er in Exchange Online geen controlerecords meer gegenereerd voor MailItemsAccessed-activiteit. Als een postvak wordt beperkt, wordt de MailItemsAccessed-activiteit pas 24 uur nadat het postvak is beperkt geregistreerd. Als dit gebeurt, is er een kans dat het postvak in de loop van de periode is gehackt. De registratie van MailItemsAccessed-activiteit wordt na 24 uur hervat.

Hier zijn enkele dingen die u in gedachten moet houden bij beperking van activiteiten:

- Minder dan 1% van alle postvakken in Exchange Online wordt beperkt
- Wanneer een postvak wordt beperkt, worden alleen controlerecords voor MailItemsAccessed-activiteiten niet gecontroleerd. Andere controleacties voor postvakken worden niet beïnvloed.
- Postvakken worden alleen beperkt voor bind-bewerkingen. Controlerecords voor synchronisatiebewerkingen worden niet beperkt.
- Als een postvak wordt beperkt, kunt u aannemen dat er MailItemsAccessed-activiteit is die niet is vastgelegd in de auditlogboeken.

Zie stap 1 in de sectie [MailItemsAccessed-auditrecords gebruiken voor forenstisch onderzoek](#use-mailitemsaccessed-audit-records-for-forensic-investigations) voor een voorbeeld van het weergeven van de eigenschap IsThrottled in een controlerecord.

## <a name="use-mailitemsaccessed-audit-records-for-forensic-investigations"></a>MailItemsAccessed-controlerecords gebruiken voor forensisch onderzoek

Met postvakcontrole worden controlerecords gegenereerd voor toegang tot e-mailberichten, zodat u zeker weet dat er geen e-mailberichten zijn gehackt. Wanneer we niet zeker weten of er wel of niet toegang tot bepaalde gegevens is gekregen, zullen we om deze reden ervan uitgaan dat dat wel het geval is door alle toegangsactiviteiten voor e-mail te registreren.

MailItemsAccessed-controlerecords voor forensische controles worden meestal gebruikt nadat een gegevenslek is opgelost en de aanvaller is buitengesloten. Om uw onderzoek te starten, moet u de reeks gehackte postvakken in kaart brengen en vaststellen in welke periode en op welk tijdstip kwaadwillende gebruikers toegang hebben gehad tot postvakken in uw organisatie. Vervolgens kunt u de **Search-UnifiedAuditLog**- of **Search-MailboxAuditLog** cmdlets in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) gebruiken om te zoeken naar controlerecords die overeenkomen met de gegevenslek.

U kunt een van de volgende opdrachten uitvoeren om te zoeken naar MailItemsAccessed-controlerecords:

**Geïntegreerd auditlogboek**:

```powershell
Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000
```

**Auditlogboek van postvak**:

```powershell
Search-MailboxAuditLog -Identity <user> -StartDate 01/06/2020 -EndDate 01/20/2020 -Operations MailItemsAccessed -ResultSize 1000 -ShowDetails
```

> [!TIP]
> Een belangrijk verschil tussen deze twee cmdlets is dat u de cmdlet **Search-UnifiedAuditLog** kunt gebruiken om te zoeken naar controlerecords voor activiteiten die door een of meer gebruikers zijn uitgevoerd. Dat komt omdat *UserIds* een parameter met meerdere waarden is. Met de **Search-MailboxAuditLog**-cmdlet wordt gezocht naar één gebruiker in het auditlogboek van het postvak.

Hier volgen de stappen voor het gebruik van MailItemsAccessed-controlerecords om hack te onderzoeken. Elke stap toont de syntaxis van de opdracht voor de **Search-UnifiedAuditLog**- of **Search-MailboxAuditLog** cmdlets.

1. Controleer of het postvak is beperkt. Dat zou betekenen dat sommige controlerecords voor postvakken niet zouden zijn vastgelegd. Wanneer 'IsThrottled' in controlerecords 'Waar' is, moet u ervan uitgaan dat gedurende 24 uur nadat deze record is gegenereerd alle toegang tot het postvak niet is gecontroleerd en dat alle e-mailgegevens zijn gehackt.

   Voer de volgende opdracht uit om te zoeken naar MailItemsAccessed-records waarbij het postvak is beperkt:

   **Geïntegreerd auditlogboek**:

   ```powershell
   Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000 | Where {$_.AuditData -like '*"IsThrottled","Value":"True"*'} | FL
   ```

   **Auditlogboek van postvak**:

   ```powershell
   Search-MailboxAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -Identity <user> -Operations MailItemsAccessed -ResultSize 10000 -ShowDetails | Where {$_.OperationProperties -like "*IsThrottled:True*"} | FL
   ```

2. Controleer op synchronisatieactiviteiten. Als een aanvaller een e-mailclient gebruikt om berichten in een postvak te downloaden, kan hij de computer loskoppelen van internet en de berichten lokaal openen zonder interactie met de server. Dit betekent dat deze activiteiten niet kunnen worden gecontroleerd door postvakcontroles.

   Voer de volgende opdracht uit als u wilt zoeken naar MailItemsAccessed-records waarbij de e-mailitems toegankelijk waren via een synchronisatiebewerking:

   **Geïntegreerd auditlogboek**:

   ```powershell
   Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 02/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000 | Where {$_.AuditData -like '*"MailAccessType","Value":"Sync"*'} | FL
   ```

   **Auditlogboek van postvak**:

   ```powershell
   Search-MailboxAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -Identity <user> -Operations MailItemsAccessed -ResultSize 10000 -ShowDetails | Where {$_.OperationProperties -like "*MailAccessType:Sync*"} | FL
   ```

3. Controleer of er synchronisatieactiviteiten hebben plaatsgevonden in dezelfde context als die die door de aanvaller is gebruikt om toegang te krijgen tot het postvak. De context wordt in kaart gebracht en onderscheiden aan de hand van het IP-adres van de clientcomputer die werd gebruikt voor toegang tot het postvak en het e-mailprotocol. Zie voor meer informatie de sectie [De toegangscontexten van verschillende controlerecords identificeren](#identifying-the-access-contexts-of-different-audit-records).

   Gebruik de onderstaande eigenschappen voor uw onderzoek. Deze eigenschappen bevinden zich in de eigenschap AuditData of OperationProperties. Als een van de synchronisaties in dezelfde context plaatsvond als de kwaadwillende activiteit kunt u ervan uitgaan dat de aanvallers alle e-mailitems naar hun client hebben gesynchroniseerd, wat betekent dat het hele postvak waarschijnlijk is gehackt.

   <br>

   ****

   |Eigenschap|Omschrijving|
   |---|---|
   |ClientInfoString|Beschrijft het protocol en de client (inclusief versie)|
   |ClientIPAddress|IP-adres van de clientmachine.|
   |SessionId|Sessie-id helpt om acties van aanvallers te onderscheiden van de dagelijkse gebruikersactiviteiten op hetzelfde account (in het geval van een gehackt account)|
   |UserID|De UPN van de gebruiker die het bericht leest.|
   |

4. Controleer op bindactiviteiten. Nadat u stap 2 en 3 hebt uitgevoerd, kunt u erop vertrouwen dat alle andere toegang tot e-mailberichten door de aanvaller zal worden vastgelegd in de controlerecords van MailItemsAccessed die de eigenschap MailAccessType hebben met de waarde 'Bind'.

   Voer de volgende opdracht uit als u wilt zoeken naar MailItemsAccessed-records waarbij de e-mailitems toegankelijk waren via een bind-bewerking.

   **Geïntegreerd auditlogboek**:

   ```powershell
   Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000 | Where {$_.AuditData -like '*"MailAccessType","Value":"Bind"*'} | FL
   ```

   **Auditlogboek van postvak**:

   ```powershell
   Search-MailboxAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -Identity <user> -Operations MailItemsAccessed -ResultSize 10000 -ShowDetails | Where {$_.OperationProperties -like "*MailAccessType:Bind*"} | FL
   ```

   E-mailberichten die zijn verzonden, worden geïdentificeerd aan de hand van de id van hun internetbericht. U kunt ook controleren of er controlerecords zijn die dezelfde context hebben als die van andere aanvallen. Zie voor meer informatie de sectie [De toegangscontexten van verschillende controlerecords identificeren](#identifying-the-access-contexts-of-different-audit-records).

   U kunt de controlegegevens op twee verschillende manieren gebruiken om bind-bewerkingen uit te voeren:

   - Bekijk of verzamel alle e-mailberichten die de kwaadwillende gebruikers kunnen openen door de InternetMessageId te gebruiken en te controleren of een van deze berichten gevoelige informatie bevat.
   - Gebruik de InternetMessageId om te zoeken naar controlerecords die zijn gerelateerd aan een reeks mogelijk gevoelige e-mailberichten. Dit is handig als u zich zorgen maakt over een klein aantal berichten.

## <a name="filtering-of-duplicate-audit-records"></a>Dubbele controlerecords filteren

Dubbele controlerecords voor dezelfde bind-bewerkingen die binnen een uur plaatsvonden, worden gefilterd om controleruis te verwijderen. Ook synchronisatiebewerkingen worden gefilterd met intervallen van één uur. De uitzondering op deze de-duplicatieprocedure geldt als een van de eigenschappen die in de volgende tabel worden beschreven afwijkt voor dezelfde InternetMessageId. Als een van deze eigenschappen in een dubbele bewerking anders is, wordt er een nieuwe auditrecord gegenereerd. Dit proces wordt uitgebreider beschreven in de volgende sectie.

<br>

****

|Eigenschap|Omschrijving|
|---|---|
|ClientIPAddress|IP-adres van de clientcomputer.|
|ClientInfoString|Het clientprotocol, dat wordt gebruikt voor toegang tot het postvak.|
|ParentFolder|Het volledige pad naar de map van het e-mailitem dat is geopend.|
|Logon_type|Het aanmeldingstype van de gebruiker die de actie heeft uitgevoerd. De aanmeldingstypen (en de bijbehorende enum-waarde) zijn Owner (0), Admin (1) of Delegate (2).|
|MailAccessType|Of de toegang een bind- of synchronisatiebewerking is.|
|MailboxUPN|De UPN van het postvak waarin zich het bericht bevindt dat is gelezen.|
|Gebruiker|De UPN van de gebruiker die het bericht leest.|
|SessionId|Met de sessie-id kunt u onderscheid maken tussen kwaadwillende acties en dagelijkse gebruikersactiviteiten in hetzelfde postvak (in het geval van een accounthack). Zie [Aanvallen contextualiseren binnen sessies in Exchange Online](https://techcommunity.microsoft.com/t5/exchange-team-blog/contextualizing-attacker-activity-within-sessions-in-exchange/ba-p/608801).|
|

## <a name="identifying-the-access-contexts-of-different-audit-records"></a>De toegangscontexten van verschillende controlerecords identificeren

Het is gebruikelijk dat aanvallers een postvak openen op hetzelfde moment dat de eigenaar van het postvak dat doet. Om onderscheid te maken tussen toegang door aanvallers en de eigenaar van het postvak zijn er eigenschappen van controlerecords die de context van de toegang definiëren. Zoals eerder uitgelegd, worden afzonderlijke controlerecords gegenereerd wanneer de waarden voor deze eigenschappen verschillen –zelfs wanneer de activiteit plaatsvindt binnen het samenvoegingsinterval. Het volgende voorbeeld toont drie verschillende controlerecords. Elke record onderscheidt zich door de eigenschappen Session Id en ClientIPAddress. Ook is te zien welke berichten werden geopend.

<br>

****

|Controlerecord 1|Controlerecord 2|Controlerecord 3|
|---|---|---|
|ClientIPAddress **1**<br/>SessionId **2**|ClientIPAddress **2**<br/>SessionId **2**|ClientIPAddress **1**<br/>SessionId **3**|
|InternetMessageId **A**<br/>InternetMessageId **D**<br/>InternetMessageId **E**<br/>InternetMessageId **F**<br/>|InternetMessageId **A**<br/>InternetMessageId **C**|InternetMessageId **B**|
|

Als een van de eigenschappen in de tabel in de [vorige sectie](#filtering-of-duplicate-audit-records) verschilt, wordt er een afzonderlijke controlerecord gegenereerd om de nieuwe context bij te houden. Toegangspogingen worden, afhankelijk van de context waarin de activiteit heeft plaatsgevonden, gesorteerd in de afzonderlijke controlerecords.

In controlerecords die in de volgende schermafbeelding worden weergegeven, worden bijvoorbeeld, afhankelijk van de context waarin de toegang heeft plaatsgevonden, de toegangsactiviteit gesorteerd in verschillende controlerecords hoewel we tegelijkertijd e-mail openen via EWSEditor en OWA. In dit geval wordt de context gedefinieerd door verschillende waarden voor de eigenschap ClientInfoString.

![Verschillende controlerecords op basis van context](../media/MailItemsAccessed4.png)

Dit is de syntaxis voor de opdracht die in de vorige schermafbeelding wordt weergegeven:

```powershell
Search-MailboxAuditLog -Identity admin -ShowDetails -Operations MailItemsAccessed -ResultSize 2000 | Select LastAccessed,Operation,AuditOperationsCountInAggregatedRecord,ClientInfoString
```
