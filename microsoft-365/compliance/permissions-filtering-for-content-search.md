---
title: Machtigingen filteren voor zoeken naar inhoud configureren
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: 1adffc35-38e5-4f7d-8495-8e0e8721f377
description: Gebruik filtermachtigingen voor Inhoud zoeken om een eDiscovery-manager alleen te laten zoeken in een subset met postvakken en sites in uw organisatie.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c36263466e103c0401e51b42b5d7ec3f6e2b4f9c
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245346"
---
# <a name="configure-permissions-filtering-for-content-search"></a>Machtigingen filteren voor zoeken naar inhoud configureren

U kunt het filteren van zoekmachtigingen gebruiken om een eDiscovery-manager alleen te laten zoeken in een subset met postvakken en sites in uw organisatie. U kunt ook machtigingenfilters gebruiken om dezelfde eDiscovery-manager alleen te laten zoeken naar postvak- of site-inhoud die voldoet aan een specifiek zoekcriterium. U kunt bijvoorbeeld een eDiscovery-manager alleen laten zoeken in de postvakken van gebruikers op een specifieke locatie of afdeling. U doet dit door een filter te maken dat een ondersteund geadresseerdenfilter gebruikt om te beperken welke postvakken een specifieke gebruiker of groep gebruikers kan zoeken. U kunt ook een filter maken dat aangeeft naar welke postvakinhoud een gebruiker kan zoeken. Dit wordt gedaan door een filter te maken waarin een doorzoekbare berichtfunctie wordt gebruikt. Op dezelfde manier kunt u een eDiscovery-manager alleen laten zoeken op specifieke SharePoint sites in uw organisatie. U doet dit door een filter te maken waarmee wordt beperkt welke site kan worden doorzocht. U kunt ook een filter maken dat aangeeft welke site-inhoud kan worden doorzocht. Dit wordt gedaan door een filter te maken dat een doorzoekbare site-eigenschap gebruikt.

U kunt ook filteren op zoekmachtigingen gebruiken om logische grenzen (compliancegrenzen *genoemd)* te maken binnen een organisatie die de locaties van de gebruikersinhoud (zoals postvakken, SharePoint-sites en OneDrive-accounts) die specifieke eDiscovery-beheerders kunnen zoeken. Zie Compliancegrenzen instellen [voor eDiscovery-onderzoeken in](tagging-and-assessment-in-advanced-ediscovery.md)Office 365.
  
Het filteren van zoekmachtigingen wordt ondersteund door de functie Inhoud zoeken in & Compliancecentrum. Met deze vier cmdlets kunt u zoekmachtigingenfilters configureren en beheren:
  
[New-ComplianceSecurityFilter](#new-compliancesecurityfilter)

[Get-ComplianceSecurityFilter](#get-compliancesecurityfilter)

[Set-ComplianceSecurityFilter](#set-compliancesecurityfilter)

[Remove-ComplianceSecurityFilter](#remove-compliancesecurityfilter)

## <a name="requirements-to-configure-permissions-filtering"></a>Vereisten voor het configureren van machtigingenfilters

- Als u de compliancebeveiligingsfilter-cmdlets wilt uitvoeren, moet u lid zijn van de rollengroep Organisatiebeheer in het beveiligings- & Compliancecentrum. Zie [Machtigingen in het Beveiligings- & compliancecentrum](../security/office-365-security/permissions-in-the-security-and-compliance-center.md) voor meer informatie.

- U moet verbinding maken met Exchange Online en & Compliance center PowerShell om de compliancebeveiligingsfilter-cmdlets te gebruiken. Dit is nodig omdat voor deze cmdlets toegang tot postvakeigenschappen is vereist. Daarom moet u verbinding maken met Exchange Online PowerShell. Bekijk de stappen in de volgende sectie.

- Zie de [sectie Meer informatie](#more-information) voor meer informatie over zoekmachtigingenfilters.

- Het filteren van zoekmachtigingen is van toepassing op inactieve postvakken, wat betekent dat u het filteren van postvakken en postvakinhoud kunt gebruiken om te beperken wie in een inactief postvak kan zoeken. Zie de [sectie Meer informatie](#more-information) voor meer informatie over het filteren van machtigingen en inactieve postvakken.

- Zoekmachtigingen filteren kan niet worden gebruikt om te beperken wie in openbare mappen in Exchange.

- Er is geen limiet voor het aantal zoekmachtigingenfilters dat in een organisatie kan worden gemaakt. Maar de zoekprestaties worden beïnvloed wanneer er meer dan 100 zoekmachtigingenfilters zijn. Als u het aantal zoekmachtigingenfilters in uw organisatie zo klein mogelijk wilt houden, maakt u filters die regels voor Exchange, SharePoint en OneDrive zoveel mogelijk in één filter combineren.

## <a name="connect-to-exchange-online-and-security--compliance-center-powershell-in-a-single-session"></a>Verbinding maken in Exchange Online en &-compliancecentrum PowerShell in één sessie

Voordat u het script in deze sectie kunt uitvoeren, moet u de PowerShell V2-module Exchange Online downloaden en installeren. Zie Info over [de Exchange Online PowerShell V2-module](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)voor meer informatie.

1. Sla de volgende tekst op in een Windows PowerShell scriptbestand met een achtervoegsel van een bestandsnaam van **.ps1.** U kunt het bestand bijvoorbeeld opslaan in een bestand met **de naamConnectEXO-SCC.ps1.**

    ```powershell
    Import-Module ExchangeOnlineManagement
    $UserCredential = Get-Credential
    Connect-ExchangeOnline -Credential $UserCredential -ShowBanner:$false
    Connect-IPPSSession -Credential $UserCredential
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. Open op uw lokale computer Windows PowerShell naar de map waar het script dat u in de vorige stap hebt gemaakt zich bevindt en voer het script uit. bijvoorbeeld:

    ```powershell
    .\ConnectEXO-SCC.ps1
    ```

Hoe weet u of dit heeft gewerkt? Nadat u het script hebt uitgevoerd, worden cmdlets van Exchange Online en & Compliance PowerShell geïmporteerd in uw lokale Windows PowerShell sessie. Als er geen fouten worden ontvangen, bent u succesvol verbonden. Een snelle test is om een cmdlet Exchange Online en & compliancecentrum uit te voeren. U kunt bijvoorbeeld Uitvoeren en **Postvak krijgen en** **Get-ComplianceSearch uitvoeren.**

Zie het volgende voor het oplossen van problemen met PowerShell-verbindingsfouten:

- [Verbinding maken powershell Exchange Online gebruiken](/powershell/exchange/connect-to-exchange-online-powershell#how-do-you-know-this-worked)

- [Verbinding maken beveiligingscentrum & PowerShell](/powershell/exchange/connect-to-scc-powershell#how-do-you-know-this-worked)

## <a name="new-compliancesecurityfilter"></a>New-ComplianceSecurityFilter

Het **New-ComplianceSecurityFilter** wordt gebruikt om een zoekmachtigingsfilter te maken. In de volgende tabel worden de parameters voor deze cmdlet beschreven. Alle parameters zijn vereist om een compliancebeveiligingsfilter te maken.
  
| Parameter | Omschrijving |
|:-----|:-----|
| _Actie_ <br/> | De  _parameter_ Actie geeft aan op welk type zoekactie het filter wordt toegepast. De mogelijke acties voor zoeken naar inhoud zijn:  <br/><br/> **Exporteren:** Het filter wordt toegepast bij het exporteren van zoekresultaten.  <br/> **Voorbeeld:** Het filter wordt toegepast bij het bekijken van zoekresultaten.  <br/> **Zuiveren:** Het filter wordt toegepast bij het verwijderen van zoekresultaten.  <br/> **Zoeken:** Het filter wordt toegepast bij het uitvoeren van een zoekopdracht.  <br/> **Alles:** Het filter wordt toegepast op alle zoekacties.  <br/> |
| _Filternaam_ <br/> |De  _parameter FilterName_ geeft de naam van het machtigingsfilter aan. Deze naam wordt gebruikt om een filter te identiteiten wanneer u de **cmdlets Get-ComplianceSecurityFilter,** **Set-ComplianceSecurityFilter** en **Remove-ComplianceSecurityFilter** gebruikt.  <br/> |
| _Filters_ <br/> | De  _parameter_ Filters geeft de zoekcriteria voor het compliancebeveiligingsfilter aan. U kunt drie verschillende typen filters maken:  <br/><br/> **Postvakfilters:** Met dit type filter worden de postvakken opgegeven die de toegewezen gebruikers (opgegeven door de parameter  _Gebruikers)_ kunnen zoeken. De syntaxis voor dit type filter **wordt Mailbox_** _PostvakEigennaam,_ waarbij  _PostvakEigennaam_ een eigenschap voor postvak aangeeft die wordt gebruikt voor het bereik van de postvakken die kunnen worden doorzocht. Met het postvakfilter kan de gebruiker aan dit filter bijvoorbeeld alleen zoeken in de postvakken met de waarde  `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` 'OttawaUsers' in de eigenschap CustomAttribute10.  <br/>  Elke ondersteunde filterbare geadresseerde-eigenschap kan worden gebruikt voor de _eigenschap MailboxPropertyName._ Zie Filterbare eigenschappen voor de parameter -RecipientFilter voor een lijst met [ondersteunde eigenschappen.](/powershell/exchange/recipientfilter-properties)  <br/><br/> **Filteren van postvakinhoud:** Dit type filter wordt toegepast op de inhoud die kan worden doorzocht. Hiermee geeft u de postvakinhoud op die de toegewezen gebruikers kunnen zoeken. De syntaxis voor dit type filter is **MailboxContent_** _SearchablePropertyName: value_, waarbij  _SearchablePropertyName_ een eigenschap Keyword Query Language (KQL) aangeeft die kan worden opgegeven in een inhoudszoekactie. Met het inhoudsfilter van het postvak kan de gebruiker dit filter bijvoorbeeld alleen zoeken naar berichten die naar geadresseerden in het contoso.com  `MailboxContent_recipients:contoso.com` worden verzonden.  <br/>  Zie Trefwoordenquery's en zoekvoorwaarden voor Inhoud [zoeken](keyword-queries-and-search-conditions.md)voor een lijst met doorzoekbare berichteigenschappen. <br/> <br/> **Belangrijk:**  Eén zoekfilter kan geen postvakfilter en een postvakinhoudsfilter bevatten. Als u deze in één filter wilt combineren, moet u een [lijst met filters gebruiken.](#using-a-filters-list-to-combine-filter-types)  Maar een filter kan een complexere query van hetzelfde type bevatten. Bijvoorbeeld:  `"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"`  <br/><br/> **Filteren van site- en site-inhoud:** Er zijn twee SharePoint en OneDrive voor Bedrijven sitegerelateerde filters die u kunt gebruiken om op te geven welke site- of site-inhoud de toegewezen gebruikers kunnen zoeken:  <br/><br/> - **Site_** _SearchableSiteProperty_ <br/> - **SiteContent_** _SearchableSiteProperty_ <br/><br/>  Deze twee filters zijn uitwisselbaar. U kunt bijvoorbeeld  `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"`  `"SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` dezelfde resultaten retourneren. Maar als u wilt weten wat een filter doet, kunt u sitegerelateerde eigenschappen opgeven (zoals een site-URL) en inhoudsgerelateerde eigenschappen  `Site_`  `SiteContent_` opgeven (zoals documenttypen). Met het filter kan de gebruiker aan dit filter bijvoorbeeld alleen zoeken naar  `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` inhoud in de https://contoso.sharepoint.com/sites/doctors siteverzameling. Met het filter kan de gebruiker die dit filter heeft toegewezen, alleen zoeken naar  `"SiteContent_FileExtension -eq 'docx'"` Word-documenten (Word 2007 en hoger).  <br/><br/>  Zie Overzicht van verkende en beheerde eigenschappen [in](/SharePoint/technical-reference/crawled-and-managed-properties-overview)SharePoint. Eigenschappen die zijn gemarkeerd met **een Ja** in de **kolom Queryable,** kunnen worden gebruikt om een site- of site-inhoudsfilter te maken.  <br/><br/> **Belangrijk:** U moet een filter voor zoekmachtigingen maken om expliciet te voorkomen dat gebruikers inhoudslocaties in een bepaalde service zoeken (zoals voorkomen dat een gebruiker in een Exchange-postvak of op een andere site SharePoint zoeken). Met andere woorden, het maken van een filter voor zoekmachtigingen waarmee een gebruiker alle SharePoint sites in de organisatie kan doorzoeken, voorkomt niet dat die gebruiker postvakken zoekt. Als u bijvoorbeeld wilt toestaan dat SharePoint alleen op sites SharePoint zoeken, moet u een filter maken waarmee wordt voorkomen dat ze in postvakken zoeken. Als u beheerders wilt toestaan Exchange alleen postvakken te zoeken, moet u een filter maken waarmee wordt voorkomen dat ze zoeken op sites.           |
| _Gebruikers_ <br/> |De  _parameter Gebruikers_ geeft de gebruikers aan die dit filter laten toepassen op hun zoekopdrachten voor inhoud. Identificeer gebruikers met hun alias of primaire SMTP-adres. U kunt meerdere waarden opgeven, gescheiden door komma's, of u kunt het filter aan alle gebruikers toewijzen met de waarde **Alles.**  <br/> U kunt ook de parameter  _Gebruikers_ gebruiken om een rollengroep & Beveiligingscentrum op te geven. Hiermee kunt u een aangepaste rollengroep maken en vervolgens die rollengroep een zoekmachtigingsfilter toewijzen. Stel dat u een aangepaste rollengroep hebt voor eDiscovery-managers voor de Amerikaanse dochteronderneming van een multinational. U kunt de parameter  _Gebruikers_ gebruiken om deze rollengroep op te geven (met behulp van de eigenschap Naam van de rollengroep) en vervolgens de parameter  _Filter_ gebruiken om alleen postvakken in de Verenigde Staten te laten zoeken.  <br/> U kunt geen distributiegroepen opgeven met deze parameter.  <br/> |
   
### <a name="using-a-filters-list-to-combine-filter-types"></a>Een filterslijst gebruiken om filtertypen te combineren

Een *filterslijst* is een filter met een postvakfilter en een sitefilter gescheiden door een komma. Het gebruik van een filterslijst is de enige ondersteunde methode voor het combineren van verschillende typen filters. In het volgende voorbeeld ziet u dat een komma de filters **Postvak en** **Site** scheidt:

```powershell
-Filters "Mailbox_CustomAttribute10 -eq 'OttawaUsers'", "Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"
```

Wanneer een filter met een filterslijst wordt verwerkt tijdens het uitvoeren van een inhoudszoekactie, worden er twee zoekmachtigingenfilters gemaakt uit de lijst met filters: een filter voor elk filter dat wordt gescheiden door een komma. In het vorige voorbeeld worden er dus één zoekmachtigingenfilter voor postvakken en één filter voor sitezoekmachtigingen gemaakt. 

Een alternatief voor het gebruik van een filterslijst is het maken van twee afzonderlijke zoekmachtigingenfilters. In het vorige voorbeeld maakt u dus één filter voor het postvakkenmerk en één filter voor het sitekenmerk. In beide gevallen zijn de resultaten hetzelfde. Het gebruik van een filterslijst of het maken van afzonderlijke zoekmachtigingenfilters is een kwestie van voorkeur.

Houd rekening met de volgende zaken bij het gebruik van een lijst met filters:

- U moet een lijst met filters gebruiken  om een filter te maken dat een postvakfilter en een **PostvakContent-filter** bevat. 

- Zoals eerder is voorgesteld, hoeft u geen filterslijst te gebruiken om een **site-** en **sitecontentfilter** op te nemen in één filter voor zoekmachtigingen. U kunt bijvoorbeeld **Site-** en **sitecontentfilters** combineren met behulp van **een operator.**

   ```powershell
   -Filters "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"
   ```

- Elk onderdeel van een filterslijst kan een complexe syntaxis van het filter bevatten. Het postvak- en sitefilters kunnen bijvoorbeeld meerdere filters bevatten, gescheiden door **een operator:**

   ```powershell
   -Filters "Mailbox_Department -eq 'CohoWinery' -or Mailbox_CustomAttribute10 -eq 'CohoUsers'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'"
   ```

## <a name="examples-of-creating-search-permissions-filters"></a>Voorbeelden van het maken van zoekmachtigingenfilters

Hier zijn voorbeelden van het gebruik van **de cmdlet New-ComplianceSecurityFilter** om een zoekmachtigingsfilter te maken. 
  
In dit voorbeeld kan de gebruiker annb@contoso.com alle acties voor zoeken naar inhoud alleen voor postvakken in Canada uitvoeren. Dit filter bevat de driecijferige numerieke landcode voor Canada van ISO 3166-1.

```powershell
New-ComplianceSecurityFilter -FilterName CountryFilter  -Users annb@contoso.com -Filters "Mailbox_CountryCode  -eq '124'" -Action All
```

In dit voorbeeld kunnen de gebruikers donh en suzanf alleen zoeken in de postvakken met de waarde 'Marketing' voor de eigenschap CustomAttribute1-postvak.

```powershell
New-ComplianceSecurityFilter -FilterName MarketingFilter  -Users donh,suzanf -Filters "Mailbox_CustomAttribute1  -eq 'Marketing'" -Action Search
```

In dit voorbeeld kunnen leden van de rollengroep 'US Discovery Managers' alle acties voor Zoeken naar inhoud alleen uitvoeren op postvakken in de Verenigde Staten. Dit filter bevat de driecijferige numerieke landcode voor de Verenigde Staten van ISO 3166-1.
  
```powershell
New-ComplianceSecurityFilter -FilterName USDiscoveryManagers  -Users "US Discovery Managers" -Filters "Mailbox_CountryCode  -eq '840'" -Action All
```

In dit voorbeeld kunnen leden van de rollengroep eDiscovery Manager alleen zoeken in de postvakken van leden van de distributiegroep Gebruikers van Ottawa. De Get-DistributionGroup cmdlet in Exchange Online PowerShell wordt gebruikt om de leden van de groep Gebruikers van Ottawa te vinden.
  
```powershell
$DG = Get-DistributionGroup "Ottawa Users"
```

```powershell
New-ComplianceSecurityFilter -FilterName DGFilter  -Users eDiscoveryManager -Filters "Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'" -Action Search
```

In dit voorbeeld wordt voorkomen dat gebruikers inhoud uit de postvakken van leden van de distributiegroep Uitvoerend team verwijderen. De Get-DistributionGroup cmdlet in Exchange Online PowerShell wordt gebruikt om de leden van de groep Uitvoerend team te zoeken.

```powershell
$DG = Get-DistributionGroup "Executive Team"
```

```powershell
New-ComplianceSecurityFilter -FilterName NoExecutivesPreview  -Users All -Filters "Mailbox_MemberOfGroup -ne '$($DG.DistinguishedName)'" -Action Purge
```

In dit voorbeeld kunnen leden van de OneDrive eDiscovery Managers aangepaste rollengroep alleen zoeken naar inhoud op OneDrive voor Bedrijven locaties in de organisatie.

```powershell
New-ComplianceSecurityFilter -FilterName OneDriveOnly  -Users "OneDrive eDiscovery Managers" -Filters "Site_Path -like 'https://contoso-my.sharepoint.com/personal*'" -Action Search
```

> [!NOTE]
> Als u gebruikers wilt beperken tot het zoeken naar specifieke sites, gebruikt u het filter  `Site_Path` , zoals wordt weergegeven in het vorige voorbeeld. Het  `Site_Site` gebruik werkt niet. 
  
In dit voorbeeld wordt de gebruiker beperkt tot het uitvoeren van alle acties voor zoeken naar inhoud alleen voor e-mailberichten die tijdens het kalenderjaar 2015 zijn verzonden.

```powershell
New-ComplianceSecurityFilter -FilterName EmailDateRestrictionFilter -Users donh@contoso.com -Filters "MailboxContent_Received -ge '01-01-2015' -and MailboxContent_Received -le '12-31-2015'" -Action All
```

Net als in het vorige voorbeeld beperkt dit voorbeeld de gebruiker tot het uitvoeren van alle acties voor zoeken naar inhoud op documenten die ergens in het kalenderjaar 2015 voor het laatst zijn gewijzigd.

```powershell
New-ComplianceSecurityFilter -FilterName DocumentDateRestrictionFilter -Users donh@contoso.com -Filters "SiteContent_LastModifiedTime -ge '01-01-2015' -and SiteContent_LastModifiedTime -le '12-31-2015'" -Action All
```

In dit voorbeeld wordt voorkomen dat leden van de OneDrive Discovery Managers inhoudszoekacties kunnen uitvoeren op een postvak in de organisatie. 

```powershell
New-ComplianceSecurityFilter -FilterName NoEXO -Users "OneDrive Discovery Managers" -Filters "Mailbox_Alias -notlike '*'"  -Action All
```

In dit voorbeeld wordt voorkomen dat iedereen in de organisatie e-mailberichten zoekt die zijn verzonden of ontvangen door een of meer mensen in de organisatie.

```powershell
New-ComplianceSecurityFilter -FilterName NoSaraJanet -Users All -Filters "MailboxContent_Participants -notlike 'janets@contoso.onmicrosoft.com' -and MailboxContent_Participants -notlike 'sarad@contoso.onmicrosoft.com'" -Action Search
```

In dit voorbeeld wordt een lijst met filters gebruikt om postvak- en sitefilters te combineren.

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="get-compliancesecurityfilter"></a>Get-ComplianceSecurityFilter

**Get-ComplianceSecurityFilter** wordt gebruikt om een lijst met zoekmachtigingenfilters te retourneren. Gebruik de  _parameter FilterName_ om informatie te retourneren voor een specifiek zoekfilter. 
  
## <a name="set-compliancesecurityfilter"></a>Set-ComplianceSecurityFilter

Het **filter Set-ComplianceSecurityFilter** wordt gebruikt om een bestaand zoekmachtigingsfilter te wijzigen. De enige vereiste parameter is _FilterName._ 
  
| Parameter | Omschrijving |
|:-----|:-----|
| _Actie_| De  _parameter_ Actie geeft aan op welk type zoekactie het filter wordt toegepast. De mogelijke acties voor zoeken naar inhoud zijn: <br/><br/> **Exporteren:** Het filter wordt toegepast bij het exporteren van zoekresultaten.  <br/> **Voorbeeld:** Het filter wordt toegepast bij het bekijken van zoekresultaten.  <br/> **Zuiveren:** Het filter wordt toegepast bij het verwijderen van zoekresultaten.  <br/> **Zoeken:** Het filter wordt toegepast bij het uitvoeren van een zoekopdracht.  <br/> **Alles:** Het filter wordt toegepast op alle zoekacties.  <br/> |
| _Filternaam_|De  _parameter FilterName_ geeft de naam van het machtigingsfilter aan. |
| _Filters_| De  _parameter_ Filters geeft de zoekcriteria voor het compliancebeveiligingsfilter aan. U kunt twee verschillende typen filters maken: <br/><br/>**Postvakfilters:** Met dit type filter worden de postvakken opgegeven die de toegewezen gebruikers (opgegeven door de parameter  _Gebruikers)_ kunnen zoeken. De syntaxis voor dit type filter **wordt Mailbox_** _PostvakEigennaam,_ waarbij  _PostvakEigennaam_ een eigenschap voor postvak aangeeft die wordt gebruikt voor het bereik van de postvakken die kunnen worden doorzocht. Met het postvakfilter kan de gebruiker aan dit filter bijvoorbeeld alleen zoeken in de postvakken met de waarde  `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` 'OttawaUsers' in de eigenschap CustomAttribute10.  Elke ondersteunde filterbare geadresseerde-eigenschap kan worden gebruikt voor de _eigenschap MailboxPropertyName._ Zie Filterbare eigenschappen voor de parameter -RecipientFilter voor een lijst met [ondersteunde eigenschappen.](/powershell/exchange/recipientfilter-properties) <br/><br/>**Filteren van postvakinhoud:** Dit type filter wordt toegepast op de inhoud die kan worden doorzocht. Hiermee geeft u de postvakinhoud op die de toegewezen gebruikers kunnen zoeken. De syntaxis voor dit type filter is **MailboxContent_** _SearchablePropertyName:value,_ waarbij  _SearchablePropertyName_ een eigenschap Keyword Query Language (KQL) aangeeft die kan worden opgegeven in een inhoudszoekactie. Met het inhoudsfilter van het postvak kan de gebruiker dit filter bijvoorbeeld alleen zoeken naar berichten die naar geadresseerden in het contoso.com  `MailboxContent_recipients:contoso.com` worden verzonden.  Zie Trefwoordenquery's voor Inhoud [zoeken](keyword-queries-and-search-conditions.md)voor een lijst met doorzoekbare berichteigenschappen. <br/><br/>**Filteren van site- en site-inhoud:** Er zijn twee SharePoint en OneDrive voor Bedrijven sitegerelateerde filters die u kunt gebruiken om op te geven welke site- of site-inhoud de toegewezen gebruikers kunnen zoeken: <br/><br/>- **Site_** *SearchableSiteProperty* <br/>- **SiteContent** _ *DoorzoekbaarSiteProperty*<br/><br/>Deze twee filters zijn uitwisselbaar. U geeft bijvoorbeeld  `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"`  `"SiteContent_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` dezelfde resultaten als resultaat. Maar als u wilt weten wat een filter doet, kunt u sitegerelateerde eigenschappen opgeven (zoals een site-URL) en inhoudsgerelateerde eigenschappen  `Site_`  `SiteContent_` opgeven (zoals documenttypen). Met het filter kan de gebruiker aan dit filter bijvoorbeeld alleen zoeken naar  `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` inhoud in de https://contoso.spoppe.com/sites/doctors siteverzameling. Met het filter kan de gebruiker die dit filter heeft toegewezen, alleen zoeken naar  `"SiteContent_FileExtension -eq 'docx'"` Word-documenten (Word 2007 en hoger).  <br/><br/>Zie Overzicht van verkende en beheerde eigenschappen [in](/SharePoint/technical-reference/crawled-and-managed-properties-overview)SharePoint. Eigenschappen die zijn gemarkeerd met **een Ja** in de **kolom Queryable,** kunnen worden gebruikt om een site- of site-inhoudsfilter te maken. <br/><br/>          |
| _Gebruikers_|De  _parameter Gebruikers_ geeft de gebruikers aan die dit filter laten toepassen op hun zoekopdrachten voor inhoud. Omdat dit een eigenschap met meerdere waarden is, wordt de bestaande lijst met gebruikers overschreven door een gebruiker of groep gebruikers met deze parameter op te geven. Zie de volgende voorbeelden voor de syntaxis voor het toevoegen en verwijderen van geselecteerde gebruikers. <br/><br/>U kunt ook de parameter  _Gebruikers_ gebruiken om een rollengroep & Beveiligingscentrum op te geven. Hiermee kunt u een aangepaste rollengroep maken en vervolgens die rollengroep een zoekmachtigingsfilter toewijzen. Stel dat u een aangepaste rollengroep hebt voor eDiscovery-managers voor de Amerikaanse dochteronderneming van een multinational. U kunt de parameter  _Gebruikers_ gebruiken om deze rollengroep op te geven (met behulp van de eigenschap Naam van de rollengroep) en vervolgens de parameter  _Filter_ gebruiken om alleen postvakken in de Verenigde Staten te laten zoeken. <br/><br/>U kunt geen distributiegroepen opgeven met deze parameter. |

## <a name="examples-of-changing-search-permissions-filters"></a>Voorbeelden van het wijzigen van zoekmachtigingenfilters

In deze voorbeelden wordt weergegeven hoe u de **cmdlets Get-ComplianceSecurityFilter** en **Set-ComplianceSecurityFilter** kunt gebruiken om een gebruiker toe te voegen of te verwijderen aan de bestaande lijst met gebruikers aan welke het filter is toegewezen. Wanneer u gebruikers aan een filter toevoegt of verwijdert, geeft u de gebruiker op met behulp van het SMTP-adres. 
  
In dit voorbeeld wordt een gebruiker toegevoegd aan het filter.

```powershell
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```

```powershell
$filterusers.users.add("pilarp@contoso.com")
```

```powershell
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```

In dit voorbeeld wordt een gebruiker uit het filter verwijderd.

```powershell
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```

```powershell
$filterusers.users.remove("annb@contoso.com")
```

```powershell
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```

## <a name="remove-compliancesecurityfilter"></a>Remove-ComplianceSecurityFilter

Het **Remove-ComplianceSecurityFilter** wordt gebruikt om een zoekfilter te verwijderen. Gebruik de  _parameter FilterName_ om het filter op te geven dat u wilt verwijderen. 
  
## <a name="more-information"></a>Meer informatie

- **Hoe werkt het filteren van zoekmachtigingen?** Het machtigingsfilter wordt toegevoegd aan de zoekquery wanneer een inhoudszoekactie wordt uitgevoerd. Het machtigingsfilter wordt door de operator **AND** Boolean aan de zoekquery samengevoegd. U hebt bijvoorbeeld een machtigingsfilter waarmee Bob alle zoekacties kan uitvoeren op de postvakken van leden van de distributiegroep Werknemers. Vervolgens voert Bob een inhoudszoekactie uit op alle postvakken in de organisatie met de  `sender:jerry@adatum.com` zoekquery. Omdat het machtigingsfilter en de zoekquery logisch worden gecombineerd door een **OPERATOR EN,** retourneert de zoekopdracht elk bericht dat door jerry@adatum.com is verzonden naar een lid van de distributiegroep Werknemers. 
    
- **Wat gebeurt er als u meerdere filters voor zoekmachtigingen hebt?** In een inhoudszoekquery worden meerdere machtigingenfilters gecombineerd door **OF** Booleaanse operatoren. Resultaten worden dus geretourneerd als een van de filters waar is. In een inhoudszoekactie worden  alle filters (gecombineerd door OF-operatoren) vervolgens gecombineerd met de zoekquery door de **operator AND.** Laten we het vorige voorbeeld nemen, waarin met een zoekfilter Alleen de postvakken van de leden van de distributiegroep Werknemers kunnen worden doorzocht. Vervolgens maken we een ander filter dat voorkomt dat Bob in het postvak van Phil kan zoeken ("Mailbox_Alias -ne 'Phil'). En laten we er ook van uitgaan dat Phil lid is van de groep Werknemers. Wanneer Bob een inhoudszoekactie (uit het vorige voorbeeld) op alle postvakken in de organisatie voert, worden zoekresultaten geretourneerd voor het postvak van Phil, ook al hebt u filter toegepast om te voorkomen dat Bob in het postvak van Phil zou zoeken. Dit komt omdat het eerste filter, waarmee Bob in de groep Werknemers kan zoeken, waar is. En omdat Phil lid is van de groep Werknemers, kan Bob in het postvak van Phil zoeken. 
    
- **Werkt het filteren van zoekmachtigingen voor inactieve postvakken?** Ja, u kunt filters voor postvak- en postvakinhoud gebruiken om te beperken wie inactieve postvakken in uw organisatie kan zoeken. Net als een normaal postvak moet een inactief postvak worden geconfigureerd met de eigenschap geadresseerde die wordt gebruikt om een machtigingsfilter te maken. Zo nodig kunt u de opdracht Postvak inactief **-InactiefMailboxOnly** gebruiken om de eigenschappen van inactieve postvakken weer te geven. Zie Inactieve postvakken maken en beheren in Office 365 voor [meer Office 365.](create-and-manage-inactive-mailboxes.md)
    
- **Werkt het filteren van zoekmachtigingen voor openbare mappen?** Nee. Zoals eerder is uitgelegd, kunnen zoekmachtigingen niet worden gebruikt om te beperken wie in openbare mappen in Exchange. Items in openbare maplocaties kunnen bijvoorbeeld niet worden uitgesloten van de zoekresultaten door een machtigingsfilter. 

- **Voorkomt het dat een gebruiker alle inhoudslocaties in een bepaalde service kan doorzoeken, ook niet in inhoudslocaties in een andere service?** Nee. Zoals eerder uitgelegd, moet u een zoekmachtigingsfilter maken om expliciet te voorkomen dat gebruikers inhoudslocaties zoeken in een specifieke service (zoals voorkomen dat een gebruiker een Exchange-postvak of een andere SharePoint-site zoekt). Met andere woorden, het maken van een filter voor zoekmachtigingen waarmee een gebruiker alle SharePoint sites in de organisatie kan doorzoeken, voorkomt niet dat die gebruiker postvakken zoekt. Als u bijvoorbeeld wilt toestaan dat SharePoint alleen op sites SharePoint zoeken, moet u een filter maken waarmee wordt voorkomen dat ze in postvakken zoeken. Als u beheerders wilt toestaan Exchange alleen postvakken te zoeken, moet u een filter maken waarmee wordt voorkomen dat ze zoeken op sites.

- **Tellen zoekmachtigingenfilters mee voor de tekenlimieten voor zoekquery's?** Ja. Zoekmachtigingen filters tellen mee met de tekenlimiet voor zoekquery's. Zie Limieten [in Advanced eDiscovery.](limits-ediscovery20.md)

