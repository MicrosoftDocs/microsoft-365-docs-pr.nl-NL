---
title: Buitengebruikstelling van verouderde eDiscovery-hulpprogramma's
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: In-Place eDiscovery en In-Place Hold (en de bijbehorende PowerShell-cmdlets) in Exchange Online worden in de eerste helft van 2020 met pensioen. De Search-Mailbox cmdlet en Advanced eDiscovery v1.0 worden ook binnen dezelfde periode ingetrokken.
ms.openlocfilehash: 97be285ae348b018866e3f91f92be523b03e6616
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/22/2021
ms.locfileid: "53055071"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a>Buitengebruikstelling van verouderde eDiscovery-hulpprogramma's

> [!IMPORTANT]
> De functionaliteit van de oudere eDiscovery-hulpprogramma's die in dit artikel worden beschreven, is verwijderd uit de Microsoft 365 of is nog steeds beschikbaar, maar wordt niet meer ondersteund. Alle functionaliteit die nog beschikbaar is, kan zonder kennisgeving worden verwijderd. Als u nog steeds een van deze oudere hulpprogramma's gebruikt, kunt u overwegen om te migreren naar de eDiscovery-hulpprogramma's in de Microsoft 365-compliancecentrum of een van de alternatieven die in dit artikel worden beschreven.

In de loop van de jaren heeft Microsoft eDiscovery-hulpprogramma's geleverd waarmee u e-mailinhoud kunt zoeken, bekijken en exporteren vanuit Exchange Online. Deze hulpprogramma's bieden echter geen effectieve manier meer om te zoeken naar niet-Exchange-inhoud in andere Microsoft 365-services, zoals SharePoint Online en Microsoft 365 Groepen. Hiervoor biedt Microsoft andere eDiscovery-hulpprogramma's waarmee u kunt zoeken naar een groot aantal Microsoft 365 inhoud. En we hebben hard gewerkt om de meest recente en krachtige eDiscovery-functionaliteit in de [Microsoft 365-compliancecentrum.](https://compliance.microsoft.com) Hierdoor kunnen organisaties reageren op juridische, interne en andere documentaanvragen voor inhoud in Microsoft 365 services, waaronder Exchange Online.

Als gevolg van deze nieuwe en verbeterde eDiscovery-functionaliteit in de Microsoft 365-compliancecentrum, trekken we de volgende eDiscovery-gerelateerde functies en functionaliteit in verband met het zoeken naar e-mailinhoud in Exchange Online en Microsoft 365:

- [In-Place eDiscovery](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) and [In-Place Holds](/exchange/security-and-compliance/create-or-remove-in-place-holds) in the Exchange admin center.

- De Exchange Online PowerShell-cmdlets die ondersteuning bieden voor In-Place eDiscovery en In-Place Holds (deze cmdlets worden gezamenlijk geïdentificeerd als **-MailboxSearch-cmdlets).* Dit omvat de volgende cmdlets:

  - [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch)

  - [Start-MailboxSearch](/powershell/module/exchange/start-mailboxsearch)

  - [Stop-MailboxSearch](/powershell/module/exchange/stop-mailboxsearch)

  - [Postvak zoeken instellen](/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > De [cmdlets Get-MailboxSearch](/powershell/module/exchange/get-mailboxsearch) en [Remove-MailboxSearch](/powershell/module/exchange/remove-mailboxsearch) zijn beschikbaar nadat de andere ***-MailboxSearch*** cmdlets zijn verwijderd, zodat u ze kunt gebruiken om te helpen bij de overgang naar andere eDiscovery- en wachthulpmiddelen. Na een bepaalde datum (hieronder geciteerd) biedt Microsoft Ondersteuning echter geen ondersteuning meer voor deze twee cmdlets.

- De [cmdlet Zoekpostvak](/powershell/module/exchange/search-mailbox) in Exchange Online PowerShell.

- De volgende bewerkingen in de Exchange Web Services API:

   - [GetSearchableMailboxes](/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [SearchMailboxes](/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [SetHoldOnMailboxes](/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [GetHoldOnMailboxes](/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- [Office 365 Advanced eDiscovery v1.0](./overview-ediscovery-20.md), de eerste versie van Advanced eDiscovery die wordt toegankelijk via een Core eDiscovery-zaak in het Office 365 Security & Compliance Center. De uittreding Advanced eDiscovery v1.0 heeft geen invloed op uw vermogen om Core eDiscovery-zaken te maken en te beheren.

> [!NOTE]
> De eDiscovery-functionaliteit die wordt uitgetrokken, is alleen van toepassing op cloudversies van Microsoft 365 en Office 365. eDiscovery-functionaliteit in on-premises versies van Exchange en SharePoint wordt nog steeds ondersteund tot nader order.

De volgende secties in dit artikel bevatten richtlijnen voor elke functie die wordt uitgetrokken. Deze informatie, inclusief tijdlijnen en alternatieve hulpprogramma's die u kunt gebruiken in plaats van het hulpprogramma dat u niet meer gebruikt.

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a>In-Place eDiscovery en In-Place in het Exchange-beheercentrum 

Volgens de oorspronkelijke aankondiging op 1 juli 2017 wordt de In-Place eDiscovery & Hold-functionaliteit in het Exchange-beheercentrum (EAC) ingetrokken. Met In-Place eDiscovery & in het EAC kunt u inhoud zoeken, vasthouden en exporteren vanuit Exchange Online. In-Place eDiscovery kunt u zoekresultaten ook kopiëren naar een discovery-postvak, zodat u of andere eDiscovery-beheerders inhoud kunnen beoordelen en beschikbaar kunnen maken voor juridische, regelgevende en openbare aanvragen.

Omdat al deze mogelijkheden (met uitzondering van het kopiëren van zoekresultaten naar een detectiepostvak) nu beschikbaar zijn in de hulpprogramma's inhoud zoeken, eDiscovery en Advanced eDiscovery in de [Microsoft 365-compliancecentrum](./microsoft-365-compliance-center.md) (met verbeterde functionaliteit, betrouwbaarheid en ondersteuning voor een breed scala aan Microsoft 365-services), raden we u aan deze hulpprogramma's zo snel mogelijk te gaan gebruiken. Om u te helpen bij de overgang naar deze andere eDiscovery-hulpprogramma's, bevat de onderstaande tabel de hulpprogramma's die u kunt gebruiken in plaats van In-Place eDiscovery en In-Place Hold.

### <a name="scope-of-affected-organizations"></a>Bereik van betrokken organisaties

- Office 365 en Microsoft 365 Enterprise organisaties

- Office 365 en Microsoft 365 Education organisaties

- Office 365 en Microsoft 365 overheidsorganisaties; dit omvat GCC, GCC High en DoD

- Office 365 Germany

### <a name="timeline-for-retirement"></a>Tijdlijn voor de uittreding

- 1 juli 2020: U kunt geen nieuwe zoekopdrachten en doorzoeken maken, maar u kunt bestaande zoekopdrachten op eigen risico wel uitvoeren, bewerken en verwijderen. Microsoft-ondersteuning wordt niet meer In-Place eDiscovery & in het EAC.

- 1 oktober 2020: De In-Place eDiscovery & Holds-functionaliteit in de EAC wordt in een modus alleen-lezen geplaatst. Dit betekent dat u alleen bestaande zoekopdrachten en inhoud kunt verwijderen.

### <a name="alternative-tools"></a>Alternatieve hulpmiddelen

In de volgende tabel worden andere hulpprogramma's beschreven die u kunt gebruiken om de bestaande functionaliteit te vervangen die wordt ingetrokken.

<table>
<thead>
<tr class="header">
<th>Functionaliteit</th>
<th>Alternatief hulpmiddel</th>
<th>Opmerkingen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Zoeken, exporteren en vasthouden voor juridische doeleinden</td>
<td>Core eDiscovery cases in the Microsoft 365-compliancecentrum </td>
<td><p>Het gebruik van de mogelijkheden van kern-eDiscovery-cases biedt de functionele pariteit voor In-Place eDiscovery en In-Place Holds. Dit geldt ook voor het volgende:</p>
<ul>
<li>
<p>Zoekschalen naar miljoenen locaties</p>
</li>
<li>
<p>Hogere betrouwbaarheid voor zoeken, exporteren en in de wacht zetten van inhoud</p>
</li>
<li>
<p>Zoeken naar inhoud in voor Exchange Online, SharePoint Online, OneDrive voor Bedrijven, Skype voor Bedrijven, Microsoft Teams, Yammer Groepen, Microsoft 365 Groepen en andere inhoud die is opgeslagen in Office 365-toepassingen</p></li></ul>
</td>
</tr>
<tr class="even">
<td>Bewaring voor bewaardoeleinden</td>
<td>Bewaarbeleid in de Microsoft 365-compliancecentrum</td>
<td><p>U kunt bewaarbeleid gebruiken om inhoud te behouden en desgewenst te verwijderen nadat de bewaarperiode is verlopen. Andere mogelijkheden zijn:</p>
<ul>
<li>
<p>Beleid toepassen op uw hele organisatie </p>
</li><li>
<p>Beleid toepassen op specifieke inhoudslocaties zoals Exchange Online, SharePoint Online, OneDrive voor Bedrijven, Skype voor Bedrijven, Microsoft Teams en Office 365 Groepen</p></li>
<li>
<p>Beleid toepassen op specifieke gebruikers</p></li></ul>
<p>Zie Meer informatie over bewaarbeleid en <a href="/microsoft-365/compliance/retention-policies"> bewaarlabels</a>voor meer informatie.</td>
</tr>
<tr class="odd">
<td>Zoekresultaten per e-mail kopiëren naar een detectiepostvak voor controle</td><td>Revisiesets in Advanced eDiscovery v2.0</td>
<td><p>Het controleren van inhoud in Microsoft 365 is nog nooit zo eenvoudig geweest. Revisiesets hebben veel mogelijkheden om de tijd en gegevens te beperken die nodig zijn om te controleren, zoals:</p>
<ul>
<li><p>Snelle zoekquery's uitvoeren en inhoud filteren in een revisieset</p></li>
<li><p>Inhoud in een revisieset analyseren; dit omvat e-mailthreading, detectie van bijna dubbele waarden, thema'sanalyse en voorspellende codering</p></li>
<li><p>Documenten taggen in een controleset</p></li>
<li><p>Suggesties voor het labelen van inhoud voor clientvoorrechten voor advocaten</p></li></ul>
<p>Zie Overzicht van de Advanced eDiscovery <a href="/microsoft-365/compliance/overview-ediscovery-20">oplossing in</a>Microsoft 365.</p>
<p>
<p>U kunt ook zoekresultaten exporteren naar PST-bestanden en vervolgens Microsoft 365 Service importeren gebruiken om de PST's te importeren in een detectiepostvak. Zie Netwerk uploaden gebruiken om <a href="/microsoft-365/compliance/use-network-upload-to-import-pst-files">PST-bestanden</a>te importeren in Office 365.
</tr>
<tr class=even>
  <td>Berichten van het ene postvak naar een ander postvak kopiëren</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Machtigingen toewijzen aan een postvak</a></td>
  <td>Als u een persoon toegang wilt geven tot e-mail van een andere gebruiker (bijvoorbeeld wanneer een werknemer uw organisatie verlaat en u een andere persoon toegang moet geven tot de e-mail van de voormalige werknemer), wordt u aangeraden die persoon machtigingen toe te wijzen voor toegang tot het postvak van de voormalige werknemer. Dus in plaats van postvakitems te kopiëren naar een ander gebruikerspostvak of een gedeeld postvak, wijst u een gebruiker de machtigingen toe die nodig zijn om toegang te krijgen tot het bronpostvak.</td>
  
  </tr>
<tr class="odd">
<td>Items herstellen uit de map Herstelbare items</td>
  <td><a href="/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</td>
  <td>U kunt permanent verwijderde items (ook wel <i>soft-deleted</i> items genoemd) herstellen in postvakken, zolang de bewaarperiode voor verwijderde items voor een item niet is verlopen. Zie De map <a href="/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Herstelbare items in</a>Exchange Online.</td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a>Veelgestelde vragen over In-Place eDiscovery en In-Place Holds

**Ik gebruik de functionaliteit voor zoekresultaten kopiëren van In-Place eDiscovery & Holds in het EAC om zoekresultaten te kopiëren naar een discovery-postvak voor controle door advocaten. Welke opties heb ik nu?**

Er zijn twee manieren om deze functionaliteit vandaag de dag te repliceren. De eerste is het gebruik [van revisiesets in Advanced eDiscovery v2.0](./view-documents-in-review-set.md). Revisiesets hebben veel van dezelfde mogelijkheden die u ziet in een traditioneel revisieprogramma, zoals snel zoeken naar documenten, labelen, e-mailthreading, bijna dubbele groepering, themaanalyse en voorspellende codering. Als u detectiepostvakken nog steeds wilt gebruiken voor controle, is de tweede optie om zoekresultaten te exporteren naar PST-bestanden en vervolgens de PST-bestanden te importeren in een discovery-postvak met behulp van de [pst-importfunctie](use-network-upload-to-import-pst-files.md) in het Microsoft-compliancecentrum.

**Hoe kan ik bepalen welke inhoudslocaties (zoals postvakken of sites) een eDiscovery-manager kan zoeken met de nieuwe hulpprogramma's?**

De Microsoft 365-compliancecentrum gebruikt ook compliancegrenzen om te bepalen op welke [inhoudslocaties](set-up-compliance-boundaries.md) een eDiscovery Manager kan zoeken. Compliancegrenzen zijn handig in overheidsinstanties die binnen de grenzen van de organisatie moeten blijven of multi-nationale bedrijven die nodig zijn om geografische boarders te respecteren.

**Hoe kan ik mijn huidige zoekopdrachten en -bezit naar de Microsoft 365-compliancecentrum?**

Het is mogelijk om eDiscovery-zoekopdrachten In-Place eDiscovery te migreren vanuit het EAC met behulp van PowerShell. Zie Zoekopdrachten en houdt van het [EAC](./migrate-legacy-ediscovery-searches-and-holds.md)migreren naar de Microsoft 365-compliancecentrum.

## <a name="-mailboxsearch-cmdlets"></a>\*-MailboxSearch-cmdlets

Volgens de oorspronkelijke kennisgeving die op 1 juli 2017 is aangekondigd in het Exchange-beheercentrum, worden de In-Place eDiscovery & Hold-functionaliteit en de bijbehorende **\* cmdlets -MailboxSearch** verwijderd. Deze cmdlets bieden gebruikers de mogelijkheid om postvakinhoud te doorzoeken, vast te houden en te exporteren voor wettelijke, regelgevende en openbare aanvragen.

Omdat deze mogelijkheden nu beschikbaar zijn in [<span class="underline">de Microsoft 365-compliancecentrum</span>](./microsoft-365-compliance-center.md) en Office 365 Security & Compliance Center PowerShell met verbeterde prestaties en schaalbaarheid, moet u deze verbeterde cmdlets gebruiken. Deze cmdlets zijn [<span class="underline"> \* -ComplianceCase</span>](/powershell/module/exchange/get-compliancecase), [<span class="underline"> \* -ComplianceSearch</span>](/powershell/module/exchange/get-compliancesearch), [<span class="underline"> \* -CaseHoldPolicy</span>](/powershell/module/exchange/get-caseholdpolicy), [<span class="underline"> \* -CaseHoldRule</span>](/powershell/module/exchange/get-caseholdrule)en [<span class="underline"> \* -ComplianceSearchAction</span>](/powershell/module/exchange/get-compliancesearchaction).

### <a name="scope-of-affected-organizations"></a>Bereik van betrokken organisaties

- Office 365 en Microsoft 365 Enterprise organisaties

- Office 365 en Microsoft 365 Education organisaties

- Office 365 en Microsoft 365 overheidsorganisaties; dit omvat GCC, GCC High en DoD

- Office 365 Germany

### <a name="timeline"></a>Tijdlijn

- 1 juli 2020: U kunt **New-MailboxSearch** niet gebruiken om nieuwe In-Place eDiscovery-zoekopdrachten en In-Place-bezit te maken, maar u kunt wel cmdlets gebruiken om bestaande zoekopdrachten en in- en bezit op eigen risico uit te voeren, te bewerken en te verwijderen. Microsoft-ondersteuning biedt geen hulp meer voor dit type zoekopdrachten en in- en uitzoekstanden.

- 1 oktober 2020: Zoals eerder vermeld, wordt de functie In-Place eDiscovery & Holds in de EAC in een modus alleen-lezen geplaatst. Dit betekent ook dat u de cmdlets **New-MailboxSearch,** **Start-MailboxSearch** of **Set-MailboxSearch** niet kunt gebruiken. U kunt alleen bestaande zoekopdrachten en in- en uit-standen krijgen en verwijderen.

### <a name="alternative-tools"></a>Alternatieve hulpmiddelen

In de volgende tabel worden andere hulpprogramma's beschreven die u kunt gebruiken om de bestaande functionaliteit te vervangen die wordt ingetrokken.

<table>
<thead>
<tr class="header">
<th>Functionaliteit</th>
<th>Alternatieve hulpmiddelen</th>
<th>Opmerkingen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Zoeken en exporteren</td>
<td><p><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>De cmdlets ComplianceSearch en ComplianceSearchAction werken samen om u te helpen bij het zoeken en exporteren van inhoud. U kunt een nieuwe zoekopdracht maken en de zoekschatting weergeven met de cmdlets <strong>Nieuw,</strong> <strong>Get-</strong>en <strong>Start-ComplianceSearch.</strong> Vervolgens kunt u de <strong>cmdlet New-ComplianceSearchAction</strong> gebruiken om de zoekresultaten te exporteren. U moet nog steeds de belangrijkste eDiscovery-functie in de Microsoft 365-compliancecentrum gebruiken om deze zoekresultaten naar uw lokale computer te downloaden.</p>
<p>
<p><strong>Opmerking:</strong> Als u deze cmdlets gebruikt om zoekopdrachten te maken die niet zijn gekoppeld aan een <strong></strong> hoofd-eDiscovery-zaak, bevinden deze zoekopdrachten zich op de pagina Inhoud zoeken in de Microsoft 365-compliancecentrum.</p></td>
</tr>
<tr class="even">
<td>Inhoud in een postvak vasthouden</td>
<td><p><a href="/powershell/module/exchange/get-caseholdpolicy"><span class="underline">*-CaseHoldPolicy</span></a></p>
<p><a href="/powershell/module/exchange/get-caseholdrule"><span class="underline">*-CaseHoldRule</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>In de Microsoft 365-compliancecentrum moet een ComplianceCase zijn gekoppeld. Maak eerst de compliancecase en maak vervolgens een CaseHoldPolicy en een CaseHoldRule.</p>
<p><strong>Opmerking:</strong> Als u een CaseHoldPolicy maakt zonder een CaseHoldRule te maken, wordt de wacht in de wacht gezet totdat de CaseHoldRule is gemaakt en is gekoppeld aan de CaseHoldPolicy. Zie de cmdletdocumentatie voor meer informatie.</p></td>
</tr>
<tr class="odd">
<td>Zoekresultaten kopiëren naar een detectiepostvak</td>
<td>Geen</td>
<td>Er is geen directe vervanging voor deze functionaliteit omdat deze niet toegang biedt tot alle Microsoft 365 services. Zie de volgende veelgestelde vragen hieronder voor alternatieve oplossingen.</td>
</tr>
  <tr class=even>
  <td>Berichten van het ene postvak naar een ander postvak kopiëren</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Machtigingen toewijzen aan een postvak</a></td>
  <td>Als u een persoon toegang wilt geven tot e-mail van een andere gebruiker (bijvoorbeeld wanneer een werknemer uw organisatie verlaat en u een andere persoon toegang moet geven tot de e-mail van de voormalige werknemer), wordt u aangeraden die persoon machtigingen toe te wijzen voor toegang tot het postvak van de voormalige werknemer. Dus in plaats van postvakitems te kopiëren naar een ander gebruikerspostvak of een gedeeld postvak, wijst u een gebruiker machtigingen toe om toegang te krijgen tot het bronpostvak.</td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a>Veelgestelde vragen over ***-MailboxSearch-cmdlets**

**We gebruiken Zoeken kopiëren om e-mailberichten of chatberichten te exporteren voor andere eDiscovery- en juridische onderzoeken. Welke andere opties hebben we nadat deze cmdlets zijn teruggetrokken?**

De [<span class="underline">Microsoft Graph API's</span>](https://developer.microsoft.com/en-us/graph) bieden een aantal methoden voor het extraheren van gegevens voor analyse en andere doeleinden die veel veerkrachtiger en schaalbaarder zijn dan de cmdlets **\* -MailboxSearch.**

**Hoe kan ik mijn zoekopdrachten en bezit migreren naar de Microsoft 365-compliancecentrum?**

Het is mogelijk om de In-Place eDiscovery te migreren vanuit het Exchange-beheercentrum met behulp van een PowerShell-script. Zie Oudere [eDiscovery-zoekopdrachten](migrate-legacy-eDiscovery-searches-and-holds.md)en -gegevens migreren naar de Microsoft 365-compliancecentrum.

**Kan ik nog steeds zoekopdrachten verwijderen of ophalen nadat de cmdlets zijn verwijderd?**

Ja, hoewel we de mogelijkheid om zoekopdrachten te maken en te wijzigen verwijderen, kunt u **get-mailboxSearch** en **Remove-MailboxSearch** tot nader order gebruiken. Het gebruik van deze cmdlets is echter op eigen risico na de pensioendatum en Microsoft Support kan geen hulp meer bieden.

## <a name="search-mailbox-cmdlet"></a>Search-Mailbox cmdlet

De **cmdlet Search-Mailbox** in Exchange Online PowerShell wordt ingetrokken, zoals oorspronkelijk aangekondigd in een waarschuwing in de cmdletuitvoer vanaf 2018. De **cmdlet Zoekpostvak** is oorspronkelijk gebruikt om in het postvak van een gebruiker te zoeken en schadelijke inhoud te verwijderen. U wordt aangeraden de **cmdlets New-ComplianceSearch** en **New-ComplianceSearchAction** te gebruiken in Office 365 Security & Compliance Center PowerShell om inhoud te zoeken en te verwijderen. Voor een ingebouwde beveiligingservaring bieden [<span class="underline">de Microsoft 365</span>](../security/index.yml) krachtige bedreigingsbeveiliging voor e-mail en vele andere Microsoft-services.

### <a name="scope-of-affected-organizations"></a>Bereik van betrokken organisaties

- Office 365 en Microsoft 365 Enterprise organisaties

- Office 365 en Microsoft 365 Education organisaties

- Office 365 en Microsoft 365 overheidsorganisaties; dit omvat GCC, GCC High en DoD

- Office 365 Germany

### <a name="timeline"></a>Tijdlijn

-  1 juli 2020: De cmdlet **Zoekpostvak** is niet meer beschikbaar en Microsoft-ondersteuning biedt geen hulp meer.

### <a name="alternative-tools"></a>Alternatieve hulpmiddelen

In de volgende tabel worden andere hulpprogramma's beschreven die u kunt gebruiken om de bestaande functionaliteit te vervangen die wordt ingetrokken.

<table>
<thead>
<tr class="header">
<th>Functionaliteit</th>
<th>Alternatieve hulpmiddelen</th>
<th>Opmerkingen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Zoeken in een postvak</td>
<td><p><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></a></p></td>
<td><p>De cmdlets ComplianceSearch en ComplianceSearchAction werken samen om u te helpen bij het zoeken en exporteren van inhoud. U kunt een nieuwe zoekopdracht maken en de zoekschatting weergeven met de cmdlets <strong>Nieuw,</strong> <strong>Get-</strong>en <strong>Start-ComplianceSearch.</strong> Vervolgens kunt u de opdracht <strong>New-ComplianceSearchAction -Export</strong> gebruiken om de zoekresultaten te exporteren. U moet nog steeds de belangrijkste eDiscovery-functie in de Microsoft 365-compliancecentrum gebruiken om deze zoekresultaten naar uw lokale computer te downloaden.</p></p>
</td>
</tr>
<tr class="even">
<td>Bulk-e-mail verwijderen uit een postvak</td>
<td><p><a href="/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes"><span class="underline">Een archief- en verwijderingsbeleid instellen voor postvakken</span></a></p>
<p></p></td>
<td><p>Beheerders kunnen een archiverings- en verwijderingsbeleid maken dat items automatisch naar het archiefpostvak van een gebruiker verplaatst en automatisch items uit het postvak verwijdert.</p>
</td>
</tr>
<tr class="even">
<td>Zoekresultaten kopiëren naar een detectiepostvak</td>
<td> </td>
<td>Er is geen directe vervanging voor deze functionaliteit omdat deze niet toegang biedt tot alle Microsoft 365 services. Zie de veelgestelde vragen in <strong>de sectie *-MailboxSearch-cmdlets</strong> voor alternatieve oplossingen. </td>
</tr>
<tr class=odd>
  <td>Berichten van het ene postvak naar een ander postvak kopiëren</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Machtigingen toewijzen aan een postvak</a></td>
  <td>Als u een persoon toegang wilt geven tot e-mail van een andere gebruiker (bijvoorbeeld wanneer een werknemer uw organisatie verlaat en u een andere persoon toegang moet geven tot de e-mail van de voormalige werknemer), wordt u aangeraden die persoon machtigingen toe te wijzen voor toegang tot het postvak van de voormalige werknemer. Dus in plaats van postvakitems te kopiëren naar een ander gebruikerspostvak of een gedeeld postvak, wijst u een gebruikersmachtiging toe om toegang te krijgen tot het bronpostvak.</td>
</tr>
<tr class=even>
  <td>Berichten uit een postvak verwijderen</td>
<td><p><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></p></td>
<td><p>De cmdlets ComplianceSearch en ComplianceSearchAction werken samen om u te helpen bij het zoeken en verwijderen van inhoud. U kunt een zoekopdracht maken en uitvoeren met <strong>cmdlets New-ComplianceSearch</strong> en <strong>New-ComplianceSearch,</strong> waarna u de inhoud kunt verwijderen met de opdracht <strong>New-ComplianceSearchAction -Purge -PurgeType.</strong> Zie Berichten zoeken en verwijderen voor <a href="/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">meer informatie.</span></a></p>
</td>
</tr>
<tr class="odd"> 
<td>Berichten uit een postvak verwijderen</td>
<td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Machtigingen toewijzen aan een postvak</a></td>
<td>Als u berichten uit een postvak wilt verwijderen, wijst u een beheerder machtigingen toe om toegang te krijgen tot het postvak van de werknemer. Berichten kunnen zo nodig worden verwijderd en hergebruikt, waarbij gebruik wordt gemaakt van de ingebouwde zoek- en weergavemogelijkheden in Outlook.</td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a>Exchange Web Services API-bewerkingen

Deze bewerkingen in de Exchange Web Services API worden gebruikt door de functie In-Place eDiscovery & Holds in het Exchange-beheercentrum en de bijbehorende **\* cmdlets -MailboxSearch** in Exchange Online PowerShell. Ze worden ook teruggetrokken als onderdeel van het terug trekken van de andere oudere eDiscovery-hulpprogramma's.

### <a name="scope-of-affected-organizations"></a>Bereik van betrokken organisaties

- Office 365 en Microsoft 365 Enterprise organisaties

- Office 365 en Microsoft 365 Education organisaties

- Office 365 en Microsoft 365 overheidsorganisaties; dit omvat GCC, GCC High en DoD

- Office 365 Germany

### <a name="timeline"></a>Tijdlijn

- 1 juli 2020: De bewerkingen GetSearchableMailboxes, SearchMailboxes, SetHoldOnMailboxes en GetHoldOnMailboxes zijn niet meer beschikbaar en Microsoft-ondersteuning biedt geen hulp meer.

## <a name="advanced-ediscovery-v10"></a>Advanced eDiscovery v1.0

Advanced eDiscovery v1.0, de versie van Advanced eDiscovery die beschikbaar is in een hoofd-eDiscovery-zaak door op Overstappen naar Advanced eDiscovery **te** klikken, wordt niet meer gebruikt. De functionaliteit is vervangen door de [nieuwe Advanced eDiscovery oplossing](./ediscovery.md) in de Microsoft 365-compliancecentrum.

Als u wilt bepalen of uw organisatie v1.0 gebruikt Advanced eDiscovery v1.0:

1. Ga naar het [Office 365 Beveiligings- & compliancecentrum.](https://protection.office.com)

2. Klik in het linkernavigatiedeelvenster van het beveiligings- & compliancecentrum op **eDiscovery > eDiscovery** en open een Hoofd-eDiscovery-zaak.

3. Als u de knop Overschakelen naar **Advanced eDiscovery** ziet, gaat u naar de 1.0-versie van Advanced eDiscovery, die wordt ingetrokken. De mogelijkheid om zaken te maken en te beheren in Core eDiscovery wordt niet beïnvloed. Alleen de mogelijkheid om casegegevens toe te voegen en te analyseren in Advanced eDiscovery v1.0 (door op **Overschakelen** naar Advanced eDiscovery) te klikken, wordt ingetrokken.

De nieuwe Advanced eDiscovery-oplossing in Microsoft 365 (ook wel *Advanced eDiscovery v2.0* genoemd) biedt alle mogelijkheden van de oorspronkelijke oplossing, maar bevat nu een op bewaarder gebaseerde benadering van het identificeren van inhoud in andere Microsoft 365-services, het verzamelen van die inhoud en het toevoegen aan een revisieset waarin revisoren kunnen profiteren van snelle zoekquery's, labelings- en analysefuncties om relevante documenten te verwijderen. Advanced eDiscovery nu verbeterde verwerking en native viewers voor zowel Microsoft- als niet-Microsoft-bestandstypen bevat, [is](./supported-filetypes-ediscovery20.md) hier een volledige lijst met bestandstypen en ondersteunde [metagegevensvelden.](./document-metadata-fields-in-advanced-ediscovery.md) De nieuwe Advanced eDiscovery-oplossing biedt ook een krachtige beheerfunctie voor beheerders, waarmee u inhoudsbeheer kunt toepassen op inhoud in verschillende services, gebruikers op de hoogte kunt stellen van de bewaarvoorzieningen en beheerdersreacties kunt bijhouden, allemaal binnen een Advanced eDiscovery geval.

Toegang tot Advanced eDiscovery v2.0:

1. Ga naar de [Microsoft 365-compliancecentrum.](https://compliance.microsoft.com)

2. Klik in het linkernavigatiedeelvenster Microsoft 365-compliancecentrum **op Alles weergeven** en klik vervolgens op **eDiscovery > Geavanceerd.**

Op dit moment wordt u aangeraden uw eDiscovery-werkstroom over te zetten naar de nieuwe Advanced eDiscovery functionaliteit. Als dat nodig is, kunt u uw Advanced eDiscovery 1.0-cases archiveren door de inhoud te exporteren en offline op te slaan. Hoewel u in bestaande gevallen tot 31 december 2020 nog steeds toegang hebt tot Advanced eDiscovery v1.0, biedt Microsoft Support geen ondersteuning na 1 oktober 2020. Zie de volgende tijdlijn voor meer informatie.

### <a name="scope-of-affected-organizations"></a>Bereik van betrokken organisaties

- Office 365 en Microsoft 365 Enterprise organisaties

- Office 365 en Microsoft 365 Education organisaties

- Office 365 en Microsoft 365 overheidsorganisaties; dit omvat GCC, GCC High en DoD

- Office 365 Germany

### <a name="timeline"></a>Tijdlijn

- 1 juli 2020: U kunt geen nieuwe cases Advanced eDiscovery v1.0 maken.

- 1 oktober 2020: U kunt geen nieuwe gegevens toevoegen (Zoekresultaten voorbereiden voor Advanced eDiscovery) aan alle gevallen. U kunt op eigen risico blijven werken met gegevens in bestaande gevallen. Microsoft-ondersteuning biedt geen hulp meer. 

- 31 december 2020: U hebt geen toegang tot Advanced eDiscovery v1.0-cases.

### <a name="alternative-tools"></a>Alternatieve hulpmiddelen

De [Advanced eDiscovery oplossing](./overview-ediscovery-20.md) in de Microsoft 365-compliancecentrum.