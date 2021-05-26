---
title: Zoeken naar eDiscovery-activiteiten in het auditlogboek
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 67cc7f42-a53d-4751-b929-6005c80798f7
description: Lees welke gebeurtenissen worden geregistreerd wanneer gebruikers die eDiscovery-machtigingen hebben toegewezen, inhoud zoeken, Core eDiscovery en Advanced eDiscovery uitvoeren in het Microsoft 365 compliancecentrum.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ce0dcc50c13ad705cb36f065639a4e971d032f22
ms.sourcegitcommit: 727a75b604d5ff5946a0854662ad5a8b049f2874
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "52653497"
---
# <a name="search-for-ediscovery-activities-in-the-audit-log"></a>Zoeken naar eDiscovery-activiteiten in het auditlogboek

Inhoud zoeken en eDiscovery-gerelateerde activiteiten (voor Core eDiscovery en Advanced eDiscovery) die worden uitgevoerd in Microsoft 365 compliancecentrum of door de bijbehorende PowerShell-cmdlets uit te voeren, worden geregistreerd in het auditlogboek. Gebeurtenissen worden vastgelegd wanneer beheerders of eDiscovery-beheerders (of gebruikers die eDiscovery-machtigingen hebben toegewezen) de volgende taken voor Zoeken naar inhoud en Kern eDiscovery uitvoeren in het Microsoft 365 compliancecentrum:
  
- Core- en Advanced eDiscovery maken en beheren

- Zoeken in inhoud maken, starten en bewerken

- Zoekacties uitvoeren, zoals een voorbeeld bekijken, exporteren en verwijderen van zoekresultaten

- Beheerders beheren en sets controleren in Advanced eDiscovery

- Machtigingen voor het filteren van inhoud configureren

- Het beheren van de beheerrol voor eDiscovery
  
Zie Het [auditlogboek doorzoeken in](search-the-audit-log-in-security-and-compliance.md)het Microsoft 365 compliancecentrum voor meer informatie over het doorzoeken van het auditlogboek, de vereiste machtigingen en het exporteren van zoekresultaten.
  
## <a name="how-to-search-for-and-view-ediscovery-activities"></a>EDiscovery-activiteiten zoeken en weergeven

Op dit moment moet u een paar specifieke dingen doen om eDiscovery-activiteiten weer te geven in het auditlogboek. Deze zijn als volgt.
  
1. Ga naar <https://compliance.microsoft.com> en meld u aan met uw werk- of schoolaccount.

2. Klik in het linkernavigatiedeelvenster van Microsoft 365 compliancecentrum op **Alles weergeven** en klik vervolgens op **Controleren.**

3. Klik in **de** vervolgkeuzelijst Activiteiten, onder **eDiscovery-activiteiten** Advanced eDiscovery **activiteiten,** op een of meer activiteiten om naar te zoeken.

    > [!NOTE]
    > De **vervolgkeuzelijst** Activiteiten bevat ook een groep activiteiten met de naam **eDiscovery-cmdletactiviteiten** die records uit het cmdlet-auditlogboek retourneren.
  
4. Selecteer een datum- en tijdbereik om eDiscovery-gebeurtenissen weer te geven die binnen die periode hebben plaatsgevonden.

5. Selecteer in **het** vak Gebruikers een of meer gebruikers voor het weergeven van zoekresultaten. Laat dit vak leeg om items voor alle gebruikers te retourneren.

6. Klik op **Zoeken** om de zoekopdracht met uw zoekcriteria uit te voeren. 

7. Nadat de zoekresultaten zijn weergegeven, kunt u op **Resultaten filteren** klikken om de resulterende activiteitsrecords te filteren of te sorteren. U kunt filteren helaas niet gebruiken om bepaalde activiteiten expliciet uit te sluiten. 

8. Als u details over een activiteit wilt weergeven, klikt u op de activiteitsrecord in de lijst met zoekresultaten. 

    Er **wordt** een uitvliegende pagina Details weergegeven met de gedetailleerde eigenschappen van de gebeurtenisrecord. Als u meer informatie wilt weergeven, klikt u **op Meer informatie.** Zie de sectie Gedetailleerde eigenschappen voor [eDiscovery-activiteiten](#detailed-properties-for-ediscovery-activities) voor een beschrijving van deze eigenschappen.

9. Desgewenst kunt u de zoekresultaten van het auditlogboek exporteren naar een CSV-bestand en vervolgens de functie Excel Power Query gebruiken om deze records op te maken en te filteren. Zie voor meer informatie [Auditlogboekrecords exporteren, configureren en weergeven](export-view-audit-log-records.md).

## <a name="ediscovery-activities"></a>eDiscovery-activiteiten

In de volgende tabel worden de activiteiten Inhoud zoeken en Core eDiscovery beschreven die worden geregistreerd wanneer een beheerder of eDiscovery-manager een eDiscovery-gerelateerde activiteit uitvoert met behulp van het compliancecentrum of de bijbehorende cmdlet uitvoert in Security & Compliance Center PowerShell. Houd er ook rekening mee dat sommige activiteiten die in Advanced eDiscovery worden uitgevoerd, kunnen worden geretourneerd wanneer u zoekt naar activiteiten in deze lijst.
  
> [!NOTE]
> De eDiscovery-activiteiten die in deze sectie worden beschreven, bevatten vergelijkbare informatie als de eDiscovery-cmdletactiviteiten die in de volgende sectie worden beschreven. U wordt aangeraden de eDiscovery-activiteiten te gebruiken die in deze sectie worden beschreven, omdat deze binnen 30 minuten in de zoekresultaten van het auditlogboek worden weergegeven. Het duurt maximaal 24 uur voordat de eDiscovery-cmdletactiviteiten worden weergegeven in de zoekresultaten van het auditlogboek.
  
|**Beschrijvende naam**|**Bewerking**|**Corresponderende cmdlet**|**Beschrijving**|
|:-----|:-----|:-----|:-----|
|Lid toegevoegd aan eDiscovery-zaak  <br/> |CaseMemberAdded  <br/> |Add-ComplianceCaseMember  <br/> |Een gebruiker is toegevoegd als lid van een eDiscovery-zaak. Als lid van een zaak kan een gebruiker verschillende case-gerelateerde taken uitvoeren, afhankelijk van of aan hem of haar de benodigde machtigingen zijn toegewezen.  <br/> |
|Zoeken naar inhoud gewijzigd  <br/> |SearchUpdated  <br/> |Set-ComplianceSearch  <br/> |Een bestaande inhoudszoekactie is gewijzigd. Wijzigingen kunnen bestaan uit het toevoegen of verwijderen van inhoudslocaties of het bewerken van de zoekquery.  <br/> |
|EDiscovery-beheerderslidmaatschap gewijzigd  <br/> |CaseAdminUpdated  <br/> |Update-eDiscoveryCaseAdmin  <br/> |De lijst met eDiscovery-beheerders in uw organisatie is gewijzigd. Deze activiteit wordt geregistreerd wanneer de lijst met eDiscovery-beheerders wordt vervangen door een groep nieuwe gebruikers. Als één gebruiker wordt toegevoegd of verwijderd, wordt de bewerking CaseAdminAdded geregistreerd.  <br/> |
|EDiscovery-zaak gewijzigd  <br/> |CaseUpdated  <br/> |Set-ComplianceCase  <br/> |Een eDiscovery-zaak is gewijzigd. Wijzigingen zijn onder andere het sluiten van een geopende zaak of het opnieuw openen van een gesloten zaak.  <br/> |
|EDiscovery-caselidmaatschap gewijzigd  <br/> |CaseMemberUpdated  <br/> |Update-ComplianceCaseMember  <br/> |De lidmaatschapslijst van een eDiscovery-zaak is gewijzigd. Deze activiteit wordt geregistreerd wanneer alle leden worden vervangen door een groep nieuwe gebruikers. Als één lid wordt toegevoegd of verwijderd, wordt de bewerking CaseMemberAdded of CaseMemberRemoved geregistreerd.  <br/> |
|Filter voor gewijzigde zoekmachtigingen  <br/> |SearchPermissionUpdated  <br/> |Set-ComplianceSecurityFilter  <br/> |Er is een zoekmachtigingsfilter gewijzigd.  <br/> |
|Gewijzigde zoekquery voor eDiscovery-case hold  <br/> |HoldUpdated  <br/> |Set-CaseHoldRule  <br/> |Een query-gebaseerde wacht die is gekoppeld aan een eDiscovery-zaak is gewijzigd. Mogelijke wijzigingen zijn het bewerken van de query of het datumbereik voor een op query's gebaseerde hold.  <br/> |
|Inhoudszoekvoorbeelditem gedownload  <br/> |PreviewItemDownloaded  <br/> |N.v.t.  <br/> |Een gebruiker heeft een item gedownload naar de lokale computer (door te klikken op de koppeling Oorspronkelijk **item** downloaden) bij het bekijken van zoekresultaten.  <br/> |
|Inhoudszoekvoorbeelditem weergegeven  <br/> |PreviewItemListed  <br/> |N.v.t.  <br/> |Een gebruiker heeft op **Voorbeeld van zoekresultaten geklikt** om de pagina met voorbeeldresultaten weer te geven, waarin maximaal 1000 items uit de resultaten van een inhoudszoekactie worden weergegeven.  <br/> |
|Inhoudszoekvoorbeelditem bekeken  <br/> |PreviewItemRendered  <br/> |N.v.t.  <br/> |Een eDiscovery-manager heeft een item bekeken door erop te klikken bij het bekijken van zoekresultaten.  <br/> |
|Zoeken naar inhoud gemaakt  <br/> |SearchCreated  <br/> |New-ComplianceSearch  <br/> |Er is een nieuwe inhoudszoekactie gemaakt.  <br/> |
|EDiscovery-beheerder gemaakt  <br/> |CaseAdminAdded  <br/> |Add-eDiscoveryCaseAdmin  <br/> |Een gebruiker is toegevoegd als eDiscovery-beheerder in de organisatie.  <br/> |
|EDiscovery-zaak gemaakt  <br/> |CaseAdded  <br/> |New-ComplianceCase  <br/> |Er is een eDiscovery-zaak gemaakt. Wanneer een zaak wordt gemaakt, hoeft u deze alleen een naam te geven. Andere case-gerelateerde taken, zoals het toevoegen van leden, het maken van opgeslagen inhoud en het maken van inhoudszoekopdrachten die aan de zaak zijn gekoppeld, resulteren in extra gebeurtenissen die worden vastgelegd.  <br/> |
|Filter voor gemaakt zoekmachtigingen  <br/> |SearchPermissionCreated  <br/> |New-ComplianceSecurityFilter  <br/> |Er is een filter voor zoekmachtigingen gemaakt.  <br/> |
|Gemaakt zoekquery voor eDiscovery-case hold  <br/> |HoldCreated  <br/> |New-CaseHoldRule  <br/> |Er is een query hold gemaakt die is gekoppeld aan een eDiscovery-zaak.  <br/> |
|Zoeken naar verwijderde inhoud  <br/> |SearchRemoved  <br/> |Remove-ComplianceSearch  <br/> |Een bestaande inhoudszoekactie is verwijderd.  <br/> |
|Verwijderde eDiscovery-beheerder  <br/> |CaseAdminRemoved  <br/> |Remove-eDiscoveryCaseAdmin  <br/> |Een eDiscovery-beheerder is uit uw organisatie verwijderd.  <br/> |
|Verwijderde eDiscovery-zaak  <br/> |CaseRemoved  <br/> |Remove-ComplianceCase  <br/> |Een eDiscovery-zaak is verwijderd. Alle aan de zaak gekoppelde in- of uit-wacht-items moeten worden verwijderd voordat de zaak kan worden verwijderd.  <br/> |
|Filter voor verwijderde zoekmachtigingen  <br/> |SearchPermissionRemoved  <br/> |Remove-ComplianceSecurityFilter  <br/> |Er is een zoekmachtigingsfilter verwijderd.  <br/> |
|Verwijderde zoekquery voor eDiscovery-case hold  <br/> |HoldRemoved  <br/> |Remove-CaseHoldRule  <br/> |Een op query's gebaseerde greep die is gekoppeld aan een eDiscovery-zaak, is verwijderd. Het verwijderen van de query uit de wacht is vaak het resultaat van het verwijderen van een wacht. Wanneer een wacht- of wachtquery wordt verwijderd, worden de inhoudslocaties die in de wacht stonden, vrijgegeven.  <br/> |
|Gedownloade export van zoeken naar inhoud  <br/> |SearchExportDownloaded  <br/> |N.v.t.  <br/> |Een gebruiker heeft de resultaten van een inhoudszoekactie gedownload naar de lokale computer. Een **gestarte export van inhoudszoekactiviteit** moet worden gestart voordat zoekresultaten kunnen worden gedownload.  <br/> |
|Voorbeeld van resultaten van zoeken naar inhoud  <br/> |SearchPreviewed  <br/> |N.v.t.  <br/> |Een gebruiker heeft een voorbeeld van de resultaten van een inhoudszoekactie bekeken.  <br/> |
|Verwijderde resultaten van zoeken naar inhoud  <br/> |SearchResultsPurged  <br/> |New-ComplianceSearchAction  <br/> |Een gebruiker heeft de resultaten van een inhoudszoekactie verwijderd door de opdracht **New-ComplianceSearchAction -Purge uit te** voeren.  <br/> |
|Verwijderde analyse van zoeken naar inhoud  <br/> |RemovedSearchResultsSentToZoom  <br/> |Remove-ComplianceSearchAction  <br/> |Een actie voor het voorbereiden van inhoudszoekactie (om zoekresultaten voor te bereiden op Advanced eDiscovery) is verwijderd. Als de voorbereidingsactie minder dan twee weken oud was, zijn de zoekresultaten die zijn voorbereid op Advanced eDiscovery verwijderd uit het Microsoft Azure opslagruimte. Als de voorbereidingsactie ouder is dan 2 weken, geeft deze gebeurtenis aan dat alleen de bijbehorende voorbereidingsactie is verwijderd.  <br/> |
|Verwijderde export van inhoud zoeken  <br/> |RemovedSearchExported  <br/> |Remove-ComplianceSearchAction  <br/> |Er is een exportactie voor inhoudszoekactie verwijderd. Als de exportactie minder dan twee weken oud was, zijn de zoekresultaten die zijn geüpload naar het Microsoft Azure verwijderd. Als de exportactie ouder is dan 2 weken, geeft deze gebeurtenis aan dat alleen de bijbehorende exportactie is verwijderd.  <br/> |
|Verwijderd lid uit eDiscovery-zaak  <br/> |CaseMemberRemoved  <br/> |Remove-ComplianceCaseMember  <br/> |Een gebruiker is verwijderd als lid van een eDiscovery-zaak.  <br/> |
|Voorbeeldresultaten van zoeken naar inhoud verwijderd  <br/> |RemovedSearchPreviewed  <br/> |Remove-ComplianceSearchAction  <br/> |Er is een actie voor het zoeken naar inhoud verwijderd.  <br/> |
|Verwijderde actie voor het verwijderen van inhoudszoekactie  <br/> |RemovedSearchResultsPurged  <br/> |Remove-ComplianceSearchAction  <br/> |Er is een actie voor het verwijderen van inhoudszoekactie verwijderd.  <br/> |
|Verwijderd zoekrapport  <br/> |SearchReportRemoved  <br/> |Remove-ComplianceSearchAction  <br/> |Er is een actie voor het exporteren van inhoudszoekrapport verwijderd.  <br/> |
|Analyse van inhoud zoeken gestart  <br/> |SearchResultsSentToZoom  <br/> |New-ComplianceSearchAction  <br/> |De resultaten van een inhoudszoekactie zijn voorbereid voor analyse in Advanced eDiscovery.  <br/> |
|Inhoud zoeken gestart  <br/> |SearchStarted  <br/> |Start-ComplianceSearch  <br/> |Er is een inhoudszoekactie gestart. Wanneer u een inhoudszoekactie maakt of wijzigt met de gui Microsoft 365 compliancecentrum, wordt de zoekopdracht automatisch gestart. Als u een zoekopdracht maakt of wijzigt met de cmdlet **New-ComplianceSearch** of **Set-ComplianceSearch,** moet u de **cmdlet Start-ComplianceSearch** uitvoeren om de zoekopdracht te starten.  <br/> |
|De export van inhoud zoeken gestart  <br/> |SearchExported  <br/> |New-ComplianceSearchAction  <br/> |Een gebruiker heeft de resultaten van een inhoudszoekactie geëxporteerd.  <br/> |
|Exportrapport gestart  <br/> |SearchReport  <br/> |New-ComplianceSearchAction  <br/> |Een gebruiker heeft een inhoudszoekrapport geëxporteerd.  <br/> |
|Inhoud zoeken gestopt  <br/> |SearchStopped  <br/> |Stop-ComplianceSearch  <br/> |Een gebruiker heeft een inhoudszoekactie gestopt.  <br/> |
|(geen)|CaseViewed|Get-ComplianceCase|Een gebruiker heeft de lijst met cases bekeken op de **pagina Core eDiscovery** in het compliancecentrum of door de cmdlet Get-ComplianceCase uitvoeren.|
|(geen)|SearchViewed|Get-ComplianceSearch|Een gebruiker heeft de lijst bekeken op inhoudszoekingen (weergegeven op het tabblad Zoekopdrachten) in het compliancecentrum of door de cmdlet uit te lopen.  Deze activiteit wordt ook geregistreerd wanneer een gebruiker de lijst met inhoudszoekingen bekijkt  die zijn gekoppeld aan een eDiscovery-zaak (door in een geval op het tabblad Zoekopdrachten te klikken) of door de opdracht **Get-ComplianceSearch -Case** uit te voeren.|
|(geen)|ViewedSearchExported|Get-ComplianceSearchAction -Exporteren|Een gebruiker heeft de lijst met exporttaken voor  inhoud zoeken (weergegeven op het tabblad Export) bekeken in het compliancecentrum of door de cmdlet uit te voeren. Deze activiteit wordt ook geregistreerd wanneer een gebruiker de lijst met exporttaken in  een eDiscovery-zaak bekijkt (weergegeven op het tabblad Exporten in een zaak) of door de opdracht **Get-ComplianceSearchAction -Case -Export** uit te voeren.|
|(geen)|ViewedSearchPreviewed|Get-ComplianceSearchAction -Preview|Een gebruiker bekijkt de resultaten van een inhoudszoekactie in het compliancecentrum of door de cmdlet uit te lopen.|
|||||
  
## <a name="advanced-ediscovery-activities"></a>Geavanceerde eDiscovery-activiteiten

In de volgende tabel worden de Advanced eDiscovery activiteiten beschreven die zijn geregistreerd in het auditlogboek. Deze activiteiten kunnen worden gebruikt om de voortgang van activiteiten in een Advanced eDiscovery bijhouden.

|**Beschrijvende naam**|**Bewerking**|**Beschrijving**|
|:-----|:-----|:-----|
|Gegevens toegevoegd aan een andere revisieset|AddWorkingSetQueryToWorkingSet|Gebruiker heeft documenten uit één revisieset toegevoegd aan een andere revisieset.|
|Gegevens toegevoegd om de set te controleren|AddQueryToWorkingSet|Gebruiker heeft de zoekresultaten van een inhoudszoekactie die is gekoppeld aan een Advanced eDiscovery aan een revisieset toegevoegd.|
|Niet-Microsoft 365 gegevens toegevoegd om de set te controleren|AddNonOffice365DataToWorkingSet|Gebruiker heeft niet-Microsoft 365 gegevens toegevoegd aan een revisieset.|
|Remediated documents added to review set|AddRemediatedData|Gebruiker uploadt documenten met indexeringsfouten die zijn opgelost in een revisieset.|
|Geanalyseerde gegevens in revisieset|RunAlgo|Gebruiker heeft analyses op de documenten in een revisieset.|
|Document met aantekeningen in revisieset|Aantekeningendocument|Gebruiker heeft een document in een revisieset geannoteerd. Aantekening bevat het redacteren van inhoud in een document.|
|Laadsets vergeleken|LoadComparisonJob|Gebruiker heeft twee verschillende laadsets in een revisieset vergeleken. Een laadset is wanneer gegevens uit een inhoudszoekactie die aan de zaak zijn gekoppeld, worden toegevoegd aan een revisieset.|
|Geconverteerd documenten met een andere indeling naar PDF|BurnJob|De gebruiker heeft alle opnieuw besleedde documenten in een revisieset geconverteerd naar PDF-bestanden.|
|Gemaakte revisieset|CreateWorkingSet|Gebruiker heeft een revisieset gemaakt.|
|Zoekopdrachten voor revisiesets gemaakt|CreateWorkingSetSearch|Gebruiker heeft een zoekquery gemaakt waarin de documenten in een revisieset worden doorzocht.|
|Gemaakt label|CreateTag|Gebruiker heeft een taggroep gemaakt in een revisieset. Een taggroep kan een of meer onderliggende tags bevatten. Deze tags worden vervolgens gebruikt om documenten in de revisieset te taggen.|
|Zoeken in verwijderde revisieset|DeleteWorkingSetSearch|Gebruiker heeft een zoekquery in een revisieset verwijderd.|
|Verwijderde tag|DeleteTag|Gebruiker heeft een tag of een taggroep in een revisieset verwijderd.|
|Gedownload document|DownloadDocument|Gebruiker heeft een document gedownload uit een revisieset.|
|Bewerkte tag|UpdateTag|Gebruiker heeft een tag in een revisieset gewijzigd.|
|Geëxporteerde documenten uit revisieset|ExportJob|Gebruiker exporteerde documenten uit een revisieset.|
|Gewijzigde instelling voor case|UpdateCaseSettings|Gebruiker heeft de instellingen voor een zaak gewijzigd. Case-instellingen omvatten case-informatie, toegangsmachtigingen en instellingen die het zoek- en analysegedrag bepalen.|
|Zoeken in gewijzigde revisieset|UpdateWorkingSetSearch|Gebruiker heeft een zoekquery bewerkt in een revisieset.|
|Voorbeeld van zoeken in revisieset|PreviewWorkingSetSearch|Gebruiker heeft een voorbeeld van de resultaten van een zoekquery in een revisieset bekeken.|
|Herstelfoutdocumenten|ErrorRemediationJob|Gebruiker lost bestanden op die indexeringsfouten bevatten.|
|Gelabeld document|TagFiles|Gebruiker tagt een document in een revisieset.|
|Gelabelde resultaten van een query|TagJob|Gebruikers labelen alle documenten die voldoen aan de criteria van de zoekquery in een revisieset.|
|Bekeken document in revisieset|ViewDocument|Gebruiker heeft een document in een revisieset bekeken.|
|||

## <a name="ediscovery-cmdlet-activities"></a>eDiscovery-cmdletactiviteiten

In de volgende tabel vindt u de cmdlet auditlogboekrecords die worden geregistreerd wanneer een beheerder of gebruiker een eDiscovery-gerelateerde activiteit uitvoert met behulp van het compliancecentrum of door de bijbehorende cmdlet uit te voeren in Security & Compliance Center PowerShell. De gedetailleerde informatie in de auditlogboekrecord verschilt voor de cmdletactiviteiten in deze tabel en de eDiscovery-activiteiten die in de vorige sectie worden beschreven.
  
Zoals eerder vermeld, duurt het tot 24 uur voordat eDiscovery-cmdletactiviteiten worden weergegeven in de zoekresultaten van het auditlogboek.
  
> [!TIP]
> De cmdlets in de **kolom Bewerking** in de volgende tabel zijn gekoppeld aan het bijbehorende helponderwerp voor cmdlet op TechNet. Ga naar het Help-onderwerp voor cmdlet voor een beschrijving van de beschikbare parameters voor elke cmdlet. De parameter en de parameterwaarde die met een cmdlet zijn gebruikt, worden opgenomen in de controlelogboekinvoer voor elke eDiscovery-cmdletactiviteit die is geregistreerd. 
  
|**Beschrijvende naam**|**Bewerking (cmdlet)**|**Beschrijving**|
|:-----|:-----|:-----|
|Houd in eDiscovery-zaak gemaakt  <br/> |[New-CaseHoldPolicy](/powershell/module/exchange/new-caseholdpolicy) <br/> |Er is een hold gemaakt voor een eDiscovery-zaak. Een hold kan worden gemaakt met of zonder een inhoudsbron op te geven. Als inhoudsbronnen zijn opgegeven, worden ze geïdentificeerd in de vermelding van het auditlogboek.  <br/> |
|Verwijderde greep uit eDiscovery-zaak  <br/> |[Remove-CaseHoldPolicy](/powershell/module/exchange/remove-caseholdpolicy) <br/> |Een greep die is gekoppeld aan een eDiscovery-zaak is verwijderd. Als u een wacht houdt, worden alle inhoudslocaties uit de wacht gezet. Als u de wacht houdt, worden ook de regels voor het in de wacht houden van de zaak verwijderd (zie **Remove-CaseHoldRule** hieronder).  <br/> |
|Gewijzigde wacht in eDiscovery-zaak  <br/> |[Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) <br/> |Een hold die is gekoppeld aan een eDiscovery is gewijzigd. Mogelijke wijzigingen zijn het toevoegen of verwijderen van inhoudslocaties of het uitschakelen (uitschakelen) van de wacht.  <br/> |
|Gemaakt zoekquery voor eDiscovery-case hold  <br/> |[New-CaseHoldRule](/powershell/module/exchange/new-caseholdrule) <br/> |Er is een query hold gemaakt die is gekoppeld aan een eDiscovery-zaak.  <br/> |
|Verwijderde zoekquery voor eDiscovery-case hold  <br/> |[Remove-CaseHoldRule](/powershell/module/exchange/remove-caseholdrule) <br/> |Een op query's gebaseerde greep die is gekoppeld aan een eDiscovery-zaak, is verwijderd. Het verwijderen van de query uit de wacht is vaak het resultaat van het verwijderen van een wacht. Wanneer een wacht- of wachtquery wordt verwijderd, worden de inhoudslocaties die in de wacht stonden, vrijgegeven.  <br/> |
|Gewijzigde zoekquery voor eDiscovery-case hold  <br/> |[Set-CaseHoldRule](/powershell/module/exchange/set-caseholdrule) <br/> |Een query-gebaseerde wacht die is gekoppeld aan een eDiscovery-zaak is gewijzigd. Mogelijke wijzigingen zijn het bewerken van de query of het datumbereik voor een op query's gebaseerde hold.  <br/> |
|EDiscovery-zaak gemaakt  <br/> |[New-ComplianceCase](/powershell/module/exchange/new-compliancecase) <br/> |Er is een eDiscovery-zaak gemaakt. Wanneer een zaak wordt gemaakt, hoeft u deze alleen een naam te geven. Andere case-gerelateerde taken, zoals het toevoegen van leden, het maken van opgeslagen inhoud en het maken van inhoudszoekopdrachten die aan de zaak zijn gekoppeld, resulteren in extra gebeurtenissen die worden vastgelegd.  <br/> |
|Verwijderde eDiscovery-zaak  <br/> |[Remove-ComplianceCase](/powershell/module/exchange/remove-compliancecase) <br/> |Een eDiscovery-zaak is verwijderd. Alle aan de zaak gekoppelde in- of uit-wacht-items moeten worden verwijderd voordat de zaak kan worden verwijderd.  <br/> |
|EDiscovery-zaak gewijzigd  <br/> |[Set-ComplianceCase](/powershell/module/exchange/set-compliancecase) <br/> |Een eDiscovery-zaak is gewijzigd. Wijzigingen zijn onder andere het sluiten van een geopende zaak of het opnieuw openen van een gesloten zaak.  <br/> |
|Lid toegevoegd aan eDiscovery-zaak  <br/> |[Add-ComplianceCaseMember](/powershell/module/exchange/add-compliancecasemember) <br/> |Een gebruiker is toegevoegd als lid van een eDiscovery-zaak. Als lid van een zaak kan een gebruiker verschillende case-gerelateerde taken uitvoeren, afhankelijk van of aan hem of haar de benodigde machtigingen zijn toegewezen.  <br/> |
|Verwijderd lid uit eDiscovery-zaak  <br/> |[Remove-ComplianceCaseMember](/powershell/module/exchange/remove-compliancecasemember) <br/> |Een gebruiker is verwijderd als lid van een eDiscovery-zaak.  <br/> |
|EDiscovery-caselidmaatschap gewijzigd  <br/> |[Update-ComplianceCaseMember](/powershell/module/exchange/update-compliancecasemember) <br/> |De lidmaatschapslijst van een eDiscovery-zaak is gewijzigd. Deze activiteit wordt geregistreerd wanneer alle leden worden vervangen door een groep nieuwe gebruikers. Als één lid wordt toegevoegd of verwijderd, wordt de bewerking **Add-ComplianceCaseMember** of **Remove-ComplianceCaseMember** geregistreerd.  <br/> |
|Zoeken naar inhoud gemaakt  <br/> |[New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch) <br/> |Er is een nieuwe inhoudszoekactie gemaakt.  <br/> |
|Zoeken naar verwijderde inhoud  <br/> |[Remove-ComplianceSearch](/powershell/module/exchange/remove-compliancesearch) <br/> |Een bestaande inhoudszoekactie is verwijderd.  <br/> |
|Zoeken naar inhoud gewijzigd  <br/> |[Set-ComplianceSearch](/powershell/module/exchange/set-compliancesearch) <br/> |Een bestaande inhoudszoekactie is gewijzigd. Wijzigingen kunnen bestaan uit het toevoegen of verwijderen van inhoudslocaties die worden doorzocht en het bewerken van de zoekquery.  <br/> |
|Inhoud zoeken gestart  <br/> |[Start-ComplianceSearch](/powershell/module/exchange/start-compliancesearch) <br/> |Er is een inhoudszoekactie gestart. Wanneer u een inhoudszoekactie maakt of wijzigt met de GUI van het compliancecentrum, wordt de zoekopdracht automatisch gestart. Als u een zoekopdracht maakt of wijzigt met de cmdlet **New-ComplianceSearch** of **Set-ComplianceSearch,** moet u de **cmdlet Start-ComplianceSearch** uitvoeren om de zoekopdracht te starten.  <br/> |
|Inhoud zoeken gestopt  <br/> |[Stop-ComplianceSearch](/powershell/module/exchange/stop-compliancesearch) <br/> |Een inhoudszoekactie die werd uitgevoerd, is gestopt.  <br/> |
|Actie voor het zoeken naar inhoud gemaakt  <br/> |[New-ComplianceSearchAction](/powershell/module/exchange/new-compliancesearchaction) <br/> |Er is een zoekactie voor inhoud gemaakt. Inhoudszoekacties zijn onder andere het bekijken van zoekresultaten, het exporteren van zoekresultaten, het voorbereiden van zoekresultaten voor analyse in Advanced eDiscovery en het permanent verwijderen van items die voldoen aan de zoekcriteria van een inhoudszoekactie.  <br/> |
|Zoekactie voor verwijderde inhoud  <br/> |[Remove-ComplianceSearchAction](/powershell/module/exchange/remove-compliancesearchaction) <br/> |Er is een zoekactie voor inhoud verwijderd.  <br/> |
|Filter voor gemaakt zoekmachtigingen  <br/> |[New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) <br/> |Er is een filter voor zoekmachtigingen gemaakt.  <br/> |
|Filter voor verwijderde zoekmachtigingen  <br/> |[Remove-ComplianceSecurityFilter](/powershell/module/exchange/remove-compliancesecurityfilter) <br/> |Er is een zoekmachtigingsfilter verwijderd.  <br/> |
|Filter voor gewijzigde zoekmachtigingen  <br/> |[Set-ComplianceSecurityFilter](/powershell/module/exchange/set-compliancesecurityfilter) <br/> |Er is een zoekmachtigingsfilter gewijzigd.  <br/> |
|EDiscovery-beheerder gemaakt  <br/> |[Add-eDiscoveryCaseAdmin](/powershell/module/exchange/add-ediscoverycaseadmin) <br/> |Een gebruiker is toegevoegd als eDiscovery-beheerder in uw organisatie.  <br/> |
|Verwijderde eDiscovery-beheerder  <br/> |[Remove-eDiscoveryCaseAdmin](/powershell/module/exchange/remove-ediscoverycaseadmin) <br/> |Een eDiscovery-beheerder is uit uw organisatie verwijderd.  <br/> |
|EDiscovery-beheerderslidmaatschap gewijzigd  <br/> |[Update-eDiscoveryCaseAdmin](/powershell/module/exchange/update-ediscoverycaseadmin) <br/> |De lijst met eDiscovery-beheerders in uw organisatie is gewijzigd. Deze activiteit wordt geregistreerd wanneer de lijst met eDiscovery-beheerders wordt vervangen door een groep nieuwe gebruikers. Als één gebruiker wordt toegevoegd of verwijderd, wordt de bewerking **Add-eDiscoveryCaseAdmin** of **Remove-eDiscoveryCaseAdmin** geregistreerd.  <br/> |

## <a name="detailed-properties-for-ediscovery-activities"></a>Gedetailleerde eigenschappen voor eDiscovery-activiteiten

In de volgende tabel worden de eigenschappen  beschreven die zijn opgenomen wanneer u klikt op Meer informatie op de pagina **Details** voor een eDiscovery-activiteit die wordt weergegeven in de zoekresultaten. Deze eigenschappen worden ook opgenomen in het CSV-bestand wanneer u de zoekresultaten van het auditlogboek exporteert. Een auditlogboekrecord voor een eDiscovery-activiteit bevat niet elke gedetailleerde eigenschap die hieronder wordt weergegeven.
  
> [!TIP]
> Wanneer u de zoekresultaten exporteert, bevat het CSV-bestand een kolom met de naam **Detail,** die de gedetailleerde eigenschappen bevat die in de volgende tabel in een eigenschap met meerdere waarden worden beschreven. U kunt de functie Power Query in Excel gebruiken om deze kolom te splitsen in meerdere kolommen, zodat elke eigenschap een eigen kolom heeft. Hiermee kunt u sorteren en filteren op een of meer van deze eigenschappen. Zie de sectie 'De zoekresultaten exporteren naar een bestand' in [Het auditlogboek doorzoeken](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file)voor meer informatie. 
  
|**Eigenschap**|**Beschrijving**|
|:-----|:-----|
|Case  <br/> |De identiteit (GUID) van de eDiscovery-zaak die is gemaakt, gewijzigd of verwijderd.  <br/> |
|ClientApplication  <br/> |eDiscovery-cmdletactiviteiten hebben een waarde van **EMC** voor deze eigenschap. Dit geeft aan dat de activiteit is uitgevoerd met de GUI van het compliancecentrum of met de cmdlet in PowerShell.  <br/> |
|ClientIP  <br/> |Het IP-adres van het apparaat dat is gebruikt toen de activiteit werd geregistreerd. Het IP-adres wordt weergegeven in een IPv4- of IPv6-adresindeling.  <br/> |
|ClientRequestId  <br/> | Voor eDiscovery-activiteiten is deze eigenschap meestal leeg.  <br/> |
|CmdletVersion  <br/> |Het buildnummer voor de versie van het compliancecentrum dat in uw organisatie wordt uitgevoerd.  <br/> |
|CreationTime  <br/> |De datum en tijd in UTC (Coordinated Universal Time) wanneer de eDiscovery-activiteit is voltooid.  <br/> |
|EffectiveOrganization  <br/> |De naam van de Microsoft 365-organisatie.  <br/> |
|ExchangeLocations  <br/> |De Exchange Online postvakken die zijn opgenomen in een inhoudszoekactie of in de wacht worden geplaatst in een eDiscovery-zaak.  <br/> |
|Uitsluitingen  <br/> |Postvak- of sitelocaties die zijn uitgesloten van een inhoudszoekactie of in een eDiscovery-zaak.  <br/> |
|ExtendedProperties  <br/> |Extra eigenschappen van een inhoudszoekactie, een actie voor het zoeken naar inhoud of het vasthouden van inhoud in een eDiscovery-zaak, zoals de object-GUID en de bijbehorende cmdlet- en cmdletparameters die zijn gebruikt toen de activiteit werd uitgevoerd.  <br/> |
|Id  <br/> |De id van het rapportinvoer. De id identificeert de vermelding van het auditlogboek op unieke manier.  <br/> |
|Niet-PIIParameters  <br/> |Een lijst met de parameters (zonder waarden) die zijn gebruikt met de cmdlet die is geïdentificeerd in de eigenschap Operation. De parameters die in deze eigenschap worden vermeld, zijn dezelfde als die in de eigenschap Parameters.  <br/> |
|ObjectId  <br/> |De GUID of de naam van het object (bijvoorbeeld een inhoudszoekfunctie of een eDiscovery-zaak) die is gemaakt, gewijzigd of verwijderd door de activiteit die wordt vermeld in de eigenschap Bewerking. Dit object wordt ook geïdentificeerd in de kolom Item in de zoekresultaten van het auditlogboek.  <br/> |
|ObjectType  <br/> |Het type eDiscovery-object dat de gebruiker heeft gemaakt, verwijderd of gewijzigd; bijvoorbeeld een inhoudszoekactie (voorbeeld, export of purge), een eDiscovery-zaak of een inhoudszoekactie.  <br/> |
|Bewerking  <br/> |De naam van de bewerking die overeenkomt met de eDiscovery-activiteit die is uitgevoerd.  <br/> |
|OrganizationId  <br/> |De GUID voor uw Microsoft 365 organisatie.  <br/> |
|Parameters  <br/> |De naam en waarde voor de parameters die met de bijbehorende cmdlet zijn gebruikt.  <br/> |
|PublicFolderLocations  <br/> |De openbare maplocaties in Exchange Online die zijn opgenomen in een inhoudszoekactie of in de wacht worden geplaatst in een eDiscovery-zaak.  <br/> |
|Query  <br/> |De zoekquery die is gekoppeld aan de activiteit, zoals een inhoudszoekactie of een op query gebaseerde wacht.  <br/> |
|RecordType  <br/> |Het type bewerking dat door de record wordt aangegeven. De waarde **van 18** geeft een gebeurtenis aan die betrekking heeft op een activiteit die wordt vermeld in de sectie [eDiscovery-cmdletactiviteiten.](#ediscovery-cmdlet-activities) Een waarde van **24** geeft een gebeurtenis aan die betrekking heeft op een activiteit die wordt vermeld in de sectie [EDiscovery-activiteiten](#how-to-search-for-and-view-ediscovery-activities) zoeken en weergeven.  <br/> |
|ResultStatus  <br/> |Hiermee geeft u aan of de actie (opgegeven in de eigenschap Bewerking) al dan niet is geslaagd.  <br/> |
|SecurityComplianceCenterEventType  <br/> |Geeft aan dat de activiteit een gebeurtenis in het compliancecentrum was. Alle eDiscovery-activiteiten hebben een waarde **van 0** voor deze eigenschap.  <br/> |
|SharepointLocations  <br/> |De SharePoint onlinesites die zijn opgenomen in een inhoudszoekactie of in de wacht zijn geplaatst in een eDiscovery-zaak.  <br/> |
|StartTime  <br/> |De datum en tijd in Coordinated Universal Time (UTC) toen de eDiscovery-activiteit werd gestart.  <br/> |
|UserID  <br/> |De gebruiker die de activiteit heeft uitgevoerd (opgegeven in de eigenschap Bewerking) waardoor de record is geregistreerd. Records voor eDiscovery-activiteiten die worden uitgevoerd door systeemaccounts (zoals NT AUTHORITY\SYSTEM) worden ook opgenomen in het auditlogboek.  <br/> |
|UserKey  <br/> |Een alternatieve id voor de gebruiker die is geïdentificeerd in de eigenschap UserId. Voor eDiscovery-activiteiten is de waarde voor deze eigenschap meestal hetzelfde als de eigenschap UserId.  <br/> |
|UserServicePlan  <br/> |Het abonnement dat door uw organisatie wordt gebruikt. Voor eDiscovery-activiteiten is deze eigenschap meestal leeg.  <br/> |
|UserType  <br/> |Het type gebruiker dat de bewerking heeft uitgevoerd. De volgende waarden geven het gebruikerstype aan.  <br/> 0 Een gewone gebruiker. 2 Een beheerder in uw organisatie. 3 Een Microsoft-datacenterbeheerder of datacentersysteemaccount. 4 Een systeemaccount. 5 Een toepassing. 6 Een service-principal. |
|Versie  <br/> |Geeft het versienummer aan van de activiteit (geïdentificeerd door de eigenschap Operation) die is geregistreerd.  <br/> |
|Workload  <br/> |De service waar de activiteit heeft plaatsgevonden. Voor eDiscovery-activiteiten is de waarde **SecurityComplianceCenter**.  <br/> |
