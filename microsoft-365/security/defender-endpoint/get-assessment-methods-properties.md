---
title: Beoordelingsmethoden en -eigenschappen per apparaat exporteren
description: Hier vindt u informatie over de API's die 'Threat and Vulnerability Management' halen. Er zijn verschillende API-oproepen om verschillende typen gegevens op te halen. Over het algemeen bevat elke API-oproep de vereiste gegevens voor apparaten in uw organisatie.
keywords: api's, api's, exportbeoordeling, per apparaatbeoordeling, per computerbeoordeling, kwetsbaarheidsbeoordelingsrapport, beoordeling van kwetsbaarheid van apparaten, rapport over apparaatproblemen, veilige configuratiebeoordeling, rapport over veilige configuratie, beoordeling van softwareproblemen, rapport over beveiligingsproblemen, kwetsbaarheidsrapport per computer,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 3e5a91a33a4207daa30f1054f03655c846d297ec
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022436"
---
# <a name="export-assessment-methods-and-properties-per-device"></a>Beoordelingsmethoden en -eigenschappen per apparaat exporteren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefversie.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="api-description"></a>API-beschrijving

Hier vindt u methoden en eigenschapsgegevens over de API's die Threat and Vulnerability Management per apparaat verzamelen. Er zijn verschillende API-oproepen om verschillende typen gegevens op te halen. Over het algemeen bevat elke API-oproep de vereiste gegevens voor apparaten in uw organisatie.

> [!Note]
>
> Tenzij anders aangegeven, zijn alle vermelde exportbeoordelingsmethoden volledig **_geëxporteerd_** en **_per apparaat_** (ook wel per **_apparaat genoemd)._**

U kunt de exportbeoordelings-API's gebruiken om verschillende soorten gegevens op te halen (exporteren:

- [1. Secure configurations assessment exporteren](#1-export-secure-configurations-assessment)

- [2. Evaluatie van de softwarevoorraad exporteren](#2-export-software-inventory-assessment)

- [3. Beoordeling van beveiligingsproblemen met software exporteren](#3-export-software-vulnerabilities-assessment)

De API's die overeenkomen met de exportgegevenstypen worden beschreven in de secties 1, 2 en 3.

Voor elke methode zijn er verschillende API-oproepen om verschillende typen gegevens op te halen. Omdat de hoeveelheid gegevens groot kan zijn, kunnen deze op twee manieren worden opgehaald:

- **JSON-antwoord**  De API haalt alle gegevens in uw organisatie op als JSON-antwoorden. Deze methode is het beste _voor kleine organisaties met minder dan 100 K-apparaten._ Het antwoord is paginated, zodat u het veld odata.nextLink uit het antwoord kunt gebruiken \@ om de volgende resultaten op te halen.

- **via bestanden** Met deze API-oplossing kunt u sneller en betrouwbaarder grotere hoeveelheden gegevens verzamelen. Daarom wordt het aanbevolen voor grote organisaties, met meer dan 100 K-apparaten. Met deze API worden alle gegevens in uw organisatie als downloadbestanden opgeslagen. Het antwoord bevat URL's om alle gegevens uit de Azure Storage. Met deze API kunt u al uw gegevens als volgt Azure Storage downloaden:

  - Bel de API om een lijst met url's te downloaden met al uw organisatiegegevens.

  - Download alle bestanden met de download-URL's en verwerkt de gegevens naar eigen goed gebruik.

Gegevens die worden verzameld (met _JSON-antwoord_ of _via_ bestanden) zijn de huidige momentopname van de huidige status en bevatten geen historische gegevens. Om historische gegevens te verzamelen, moeten klanten de gegevens opslaan in hun eigen gegevensopslag.

## <a name="1-export-secure-configurations-assessment"></a>1. Secure configurations assessment exporteren

Retourneert alle configuraties en hun status, per apparaat.

### <a name="11-methods"></a>1.1 Methoden

Methode | Gegevenstype | Beschrijving
:---|:---|:---
Veilige configuratiebeoordeling **exporteren (JSON-antwoord)** | Veilige configuratie per apparaatverzameling. Zie: [1.2 Eigenschappen (JSON-antwoord)](#12-properties-json-response) | Retourneert een tabel met een vermelding voor elke unieke combinatie van DeviceId, ConfigurationId. De API haalt alle gegevens in uw organisatie op als JSON-antwoorden. Deze methode is het beste voor kleine organisaties met minder dan 100 K-apparaten. Het antwoord is paginated, zodat u het veld @odata.nextLink uit het antwoord kunt gebruiken om de volgende resultaten op te halen.
Beveiligde configuratiebeoordeling **exporteren (via bestanden)** | Veilige configuratie per apparaatverzameling. Zie: [1.3 Eigenschappen (via bestanden)](#13-properties-via-files) | Retourneert een tabel met een vermelding voor elke unieke combinatie van DeviceId, ConfigurationId. Met deze API-oplossing kunt u sneller en betrouwbaarder grotere hoeveelheden gegevens verzamelen. Daarom wordt het aanbevolen voor grote organisaties, met meer dan 100 K-apparaten. Met deze API worden alle gegevens in uw organisatie als downloadbestanden opgeslagen. Het antwoord bevat URL's om alle gegevens uit de Azure Storage. Met deze API kunt u al uw gegevens als volgt Azure Storage downloaden: 1.  Bel de API om een lijst met url's te downloaden met al uw organisatiegegevens. 2.  Download alle bestanden met de download-URL's en verwerkt de gegevens naar eigen goed gebruik.

### <a name="12-properties-json-response"></a>1.2 Eigenschappen (JSON-antwoord)

Eigenschap (id) | Gegevenstype | Beschrijving
:---|:---|:---
ConfigurationCategory | string | Categorie of groepering waarvan de configuratie deel uitmaken: Toepassing, BE, Netwerk, Accounts, Beveiligingsbesturingselementen
ConfigurationId | string | Unieke id voor een specifieke configuratie
ConfigurationImpact | string | Beoordeelde invloed van de configuratie op de algemene configuratiescore (1-10)
ConfigurationName | string | Weergavenaam van de configuratie
ConfigurationSubcategory | string | Subcategorie of subgroepering waarvan de configuratie deel uitmaken. In veel gevallen worden hier specifieke mogelijkheden of functies beschreven.
DeviceId | string | Unieke id voor het apparaat in de service.
Apparaatnaam | string | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat.
IsApplicable | bool | Geeft aan of de configuratie of het beleid van toepassing is
IsCompliant | bool | Geeft aan of de configuratie of het beleid juist is geconfigureerd
IsExpectedUserImpact | bool | Geeft aan of er gevolgen voor de gebruiker zijn als de configuratie wordt toegepast
OSPlatform | string | Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd. Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7. Zie ondersteunde besturingssystemen en platforms van tvm voor meer informatie.
RbacGroupName | string | De groep Toegangsbeheer (RBAC) op basis van rollen. Als dit apparaat niet is toegewezen aan een RBAC-groep, is de waarde 'Niet toegewezen'. Als de organisatie geen RBAC-groepen bevat, is de waarde 'Geen'.
RecommendationReference | string | Een verwijzing naar de aanbevelings-id met betrekking tot deze software.
Tijdstempel | string | De laatste keer dat de configuratie op het apparaat is gezien

### <a name="13-properties-via-files"></a>1.3 Eigenschappen (via bestanden)

Eigenschap (id) | Gegevenstype | Beschrijving
:---|:---|:---
Bestanden exporteren | \[matrixreeks\] | Een lijst met download-URL's voor bestanden met de huidige momentopname van de organisatie.
GeneratedTime | string | De tijd dat de export is gegenereerd.

## <a name="2-export-software-inventory-assessment"></a>2. Evaluatie van de softwarevoorraad exporteren

Retourneert alle geïnstalleerde software en de gegevens op elk apparaat.

### <a name="21-methods"></a>2.1 Methoden

Methode | Gegevenstype | Beschrijving
:---|:---|:---
Beoordeling van de inventaris van software **exporteren (JSON-antwoord)** | Softwarevoorraad per apparaatverzameling. Zie: [2,2 eigenschappen (JSON-antwoord)](#22-properties-json-response) | Retourneert een tabel met een vermelding voor elke unieke combinatie van DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion. De API haalt alle gegevens in uw organisatie op als JSON-antwoorden. Deze methode is het beste voor kleine organisaties met minder dan 100 K-apparaten. Het antwoord is paginated, zodat u het veld @odata.nextLink uit het antwoord kunt gebruiken om de volgende resultaten op te halen.
Beoordeling van softwarevoorraad **exporteren (via bestanden)** | Softwarevoorraad per apparaatbestanden. Zie: [2.3 Eigenschappen (via bestanden)](#23-properties-via-files) | Retourneert een tabel met een vermelding voor elke unieke combinatie van DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion. Met deze API-oplossing kunt u sneller en betrouwbaarder grotere hoeveelheden gegevens verzamelen. Daarom wordt het aanbevolen voor grote organisaties, met meer dan 100 K-apparaten. Met deze API worden alle gegevens in uw organisatie als downloadbestanden opgeslagen. Het antwoord bevat URL's om alle gegevens uit de Azure Storage. Met deze API kunt u al uw gegevens als volgt Azure Storage downloaden: 1.  Bel de API om een lijst met url's te downloaden met al uw organisatiegegevens. 2.  Download alle bestanden met de download-URL's en verwerkt de gegevens naar eigen goed gebruik.

### <a name="22-properties-json-response"></a>2.2 Eigenschappen (JSON-antwoord)

Eigenschap (id) | Gegevenstype | Beschrijving
:---|:---|:---
DeviceId | string | Unieke id voor het apparaat in de service.
Apparaatnaam | string | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat.
DiskPaths | Matrix[tekenreeks]  | Schijf bewijs dat het product is geïnstalleerd op het apparaat.
EndOfSupportDate | string | De datum waarop de ondersteuning voor deze software is of eindigt.
EndOfSupportStatus | string | Einde van de ondersteuningsstatus. Kan deze mogelijke waarden bevatten: Geen, EOS-versie, aankomende EOS-versie, EOS-software, aankomende EOS-software.
Id | string | Unieke id voor de record.
NumberOfWeaknesses | int|Aantal zwakke punten in deze software op dit apparaat
OSPlatform | string | Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd. Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7. Zie ondersteunde besturingssystemen en platforms van tvm voor meer informatie.
RbacGroupName | string | De groep Toegangsbeheer (RBAC) op basis van rollen. Als dit apparaat niet is toegewezen aan een RBAC-groep, is de waarde 'Niet toegewezen'. Als de organisatie geen RBAC-groepen bevat, is de waarde 'Geen'.
RegistryPaths | Matrix[tekenreeks] | Registergegevens dat het product op het apparaat is geïnstalleerd.
SoftwareFirstSeenTimestamp | string | De eerste keer dat deze software op het apparaat werd gezien.
SoftwareName | string | Naam van het softwareproduct.
SoftwareVendor | string | Naam van de softwareleverancier.
SoftwareVersion | string | Versienummer van het softwareproduct.

### <a name="23-properties-via-files"></a>2.3 Eigenschappen (via bestanden)

Eigenschap (id) | Gegevenstype | Beschrijving
:---|:---|:---
Bestanden exporteren | \[matrixreeks\] | Een lijst met download-URL's voor bestanden met de huidige momentopname van de organisatie.
GeneratedTime | string | De tijd dat de export is gegenereerd.

## <a name="3-export-software-vulnerabilities-assessment"></a>3. Beoordeling van beveiligingsproblemen met software exporteren

Retourneert alle bekende beveiligingslekken op een apparaat en de details, voor alle apparaten.

### <a name="31-methods"></a>3.1 Methoden

Methode | Gegevenstype | Beschrijving
:---|:---|:---
Beoordeling van beveiligingsproblemen met software **exporteren (JSON-antwoord)** | Onderzoeksverzameling Zie: [3.2 Eigenschappen (JSON-antwoord)](#32-properties-json-response) | Retourneert een tabel met een vermelding voor elke unieke combinatie van DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId. De API haalt alle gegevens in uw organisatie op als JSON-antwoorden. Deze methode is het beste voor kleine organisaties met minder dan 100 K-apparaten. Het antwoord is paginated, zodat u het veld @odata.nextLink uit het antwoord kunt gebruiken om de volgende resultaten op te halen.
Beoordeling van beveiligingsproblemen met software **exporteren (via bestanden)** | Onderzoeksentiteit Zie: [3.3 Eigenschappen (via bestanden)](#33-properties-via-files) | Retourneert een tabel met een vermelding voor elke unieke combinatie van DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId. Met deze API-oplossing kunt u sneller en betrouwbaarder grotere hoeveelheden gegevens verzamelen. Daarom wordt het aanbevolen voor grote organisaties, met meer dan 100 K-apparaten. Met deze API worden alle gegevens in uw organisatie als downloadbestanden opgeslagen. Het antwoord bevat URL's om alle gegevens uit de Azure Storage. Met deze API kunt u al uw gegevens als volgt Azure Storage downloaden: 1.  Bel de API om een lijst met url's te downloaden met al uw organisatiegegevens. 2.  Download alle bestanden met de download-URL's en verwerkt de gegevens naar eigen goed gebruik.
**Evaluatie van beveiligingsproblemen** met Delta-exportsoftware **(JSON-antwoord)** | Onderzoeksverzameling Zie: [3.4 Properties Delta export (JSON response)](#34-properties-delta-export-json-response) | Retourneert een tabel met een vermelding voor elke unieke combinatie van: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId en EventTimestamp. <br><br> De API haalt gegevens in uw organisatie op als JSON-antwoorden. Het antwoord is paginated, zodat u het veld @odata.nextLink uit het antwoord kunt gebruiken om de volgende resultaten op te halen. In tegenstelling tot de beoordeling van volledige softwareproblemen (JSON-antwoord) - die wordt gebruikt om een volledige momentopname van de beoordeling van de beveiligingsproblemen in de software van uw organisatie per apparaat te verkrijgen - wordt de delta export OData API-oproep gebruikt om alleen de wijzigingen op te halen die zijn gebeurd tussen een geselecteerde datum en de huidige datum (de delta-API-oproep). In plaats van elke keer een volledige export met een grote hoeveelheid gegevens te krijgen, krijgt u alleen specifieke informatie over nieuwe, opgeloste en bijgewerkte beveiligingslekken. Delta export OData API-oproep kan ook worden gebruikt om verschillende KPI's te berekenen, zoals 'hoeveel beveiligingslekken zijn opgelost?' of 'hoeveel nieuwe beveiligingslekken zijn toegevoegd aan mijn organisatie?'  <br><br> Omdat de Delta Export OData API call for software vulnerabilities gegevens retourneert voor alleen een gericht datumbereik, wordt deze niet beschouwd als _een volledige export_.

### <a name="32-properties-json-response"></a>3.2 Eigenschappen (JSON-antwoord)

Eigenschap (id) | Gegevenstype | Beschrijving
:---|:---|:---
CveId | string | Unieke id die is toegewezen aan het beveiligingsprobleem onder het CVE-systeem (Common Vulnerabilities and Exposures).
CvssScore | string | De CVSS-score van de CVE.
DeviceId | string | Unieke id voor het apparaat in de service.
Apparaatnaam | string | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat.
DiskPaths | \[Matrixreeks\] | Schijf bewijs dat het product is geïnstalleerd op het apparaat.
ExploitabilityLevel | string | Het gebruiksniveau van dit beveiligingsprobleem (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)
FirstSeenTimestamp | string | De eerste keer dat de CVE van dit product op het apparaat werd gezien.
Id | string | Unieke id voor de record.
LastSeenTimestamp | string | De laatste keer dat de CVE werd gezien op het apparaat.
OSPlatform | string | Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd. Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7. Zie ondersteunde besturingssystemen en platforms van tvm voor meer informatie.
RbacGroupName | string | De groep Toegangsbeheer (RBAC) op basis van rollen. Als dit apparaat niet is toegewezen aan een RBAC-groep, is de waarde 'Niet toegewezen'. Als de organisatie geen RBAC-groepen bevat, is de waarde 'Geen'.
RecommendationReference | string | Een verwijzing naar de aanbevelings-id met betrekking tot deze software.
AanbevolenSecurityUpdate | string | Naam of beschrijving van de beveiligingsupdate die door de softwareleverancier wordt geleverd om het beveiligingsprobleem aan te pakken.
AanbevolenSecurityUpdateId | string | Id van de toepasselijke beveiligingsupdates of -id voor de bijbehorende richtlijnen of KB-artikelen (Knowledge Base)
Matrixreeks \[ registerpaden\] | Registergegevens dat het product op het apparaat is geïnstalleerd.
SoftwareName | string | Naam van het softwareproduct.
SoftwareVendor | string | Naam van de softwareleverancier.
SoftwareVersion | string | Versienummer van het softwareproduct.
VulnerabilitySeverityLevel | string | Ernstniveau dat is toegewezen aan het beveiligingsprobleem op basis van de CVSS-score en dynamische factoren die worden beïnvloed door het bedreigingslandschap.

### <a name="33-properties-via-files"></a>3.3 Eigenschappen (via bestanden)

Eigenschap (id) | Gegevenstype | Beschrijving
:---|:---|:---
Bestanden exporteren | \[matrixreeks\]  | Een lijst met download-URL's voor bestanden met de huidige momentopname van de organisatie.
GeneratedTime | string | De tijd dat de export is gegenereerd.

### <a name="34-properties-delta-export-json-response"></a>3.4 Eigenschappen (delta export JSON-antwoord)

Eigenschap (id) | Gegevenstype | Beschrijving
:---|:---|:---
CveId | string | Unieke id die is toegewezen aan het beveiligingsprobleem onder het CVE-systeem (Common Vulnerabilities and Exposures).
CvssScore | string | De CVSS-score van de CVE.
DeviceId | string | Unieke id voor het apparaat in de service.
Apparaatnaam | string | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat.
DiskPaths | Matrix[tekenreeks] | Schijf bewijs dat het product is geïnstalleerd op het apparaat.
EventTimestamp | Tekenreeks | De tijd dat deze deltagebeurtenis is gevonden.
ExploitabilityLevel | string | Het gebruiksniveau van dit beveiligingsprobleem (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)
FirstSeenTimestamp | string | De eerste keer dat de CVE van dit product op het apparaat werd gezien.
Id | string | Unieke id voor de record.  
LastSeenTimestamp | string | De laatste keer dat de CVE werd gezien op het apparaat.
OSPlatform | string | Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd. Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7. Zie ondersteunde besturingssystemen en platforms van tvm voor meer informatie.
RbacGroupName | string | De groep Toegangsbeheer (RBAC) op basis van rollen. Als dit apparaat niet is toegewezen aan een RBAC-groep, is de waarde 'Niet toegewezen'. Als de organisatie geen RBAC-groepen bevat, is de waarde 'Geen'.
RecommendationReference | string | Een verwijzing naar de aanbevelings-id met betrekking tot deze software.
AanbevolenSecurityUpdate  | string | Naam of beschrijving van de beveiligingsupdate die door de softwareleverancier wordt geleverd om het beveiligingsprobleem aan te pakken.
AanbevolenSecurityUpdateId  | string | Id van de toepasselijke beveiligingsupdates of -id voor de bijbehorende richtlijnen of KB-artikelen (Knowledge Base)
RegistryPaths  | Matrix[tekenreeks] | Registergegevens dat het product op het apparaat is geïnstalleerd.
SoftwareName | string | Naam van het softwareproduct.
SoftwareVendor | string | Naam van de softwareleverancier.
SoftwareVersion | string | Versienummer van het softwareproduct.
Status | Tekenreeks | **Nieuw**   (voor een nieuw beveiligingsprobleem dat op een apparaat is geïntroduceerd).  **Opgelost**   (voor een beveiligingsprobleem dat niet meer bestaat op het apparaat, wat betekent dat het is opgelost). **Bijgewerkt**   (voor een beveiligingsprobleem op een apparaat dat is gewijzigd. De mogelijke wijzigingen zijn: CVSS-score, exploitabilityniveau, ernstniveau, DiskPaths, RegistryPaths, RecommendedSecurityUpdate).
VulnerabilitySeverityLevel | string | Ernstniveau dat is toegewezen aan het beveiligingsprobleem op basis van de CVSS-score en dynamische factoren die worden beïnvloed door het bedreigingslandschap.

## <a name="see-also"></a>Zie ook

- [Veilige configuratiebeoordeling per apparaat exporteren](get-assessment-secure-config.md)

- [Beoordeling van de softwarevoorraad per apparaat exporteren](get-assessment-software-inventory.md)

- [Beoordeling van beveiligingsproblemen met software per apparaat exporteren](get-assessment-software-vulnerabilities.md)

Andere gerelateerde

- [Risicogebaseerd & vulnerability management](next-gen-threat-and-vuln-mgt.md)

- [Beveiligingslekken in uw organisatie](tvm-weaknesses.md)
