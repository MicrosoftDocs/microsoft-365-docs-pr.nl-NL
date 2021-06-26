---
title: Microsoft Compliance Configuration Analyzer voor Compliance Manager
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Meer informatie over het gebruik van Microsoft Compliance Configuration Analyzer om snel aan de weg te gaan met Microsoft Compliance Manager.
ms.openlocfilehash: 36f11597eac1837e3e18885f3c0a5d8dbc89a774
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2021
ms.locfileid: "53148960"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager-preview"></a>Microsoft Compliance Configuration Analyzer for Compliance Manager (preview)

**In dit artikel:** Meer informatie over het installeren en uitvoeren van het hulpprogramma Microsoft Compliance Configure Analyzer om snel aan de slag te gaan met Microsoft Compliance Manger.

## <a name="microsoft-compliance-configuration-analyzer-mcca-preview-overview"></a>Overzicht van Microsoft Compliance Configuration Analyzer (MCCA) (preview)

De Microsoft Compliance Configuration Analyzer (MCCA) is een preview-hulpprogramma waarmee u aan de slag kunt met [Microsoft Compliance Manager.](compliance-manager.md) MCCA is een op PowerShell gebaseerd hulpprogramma dat de huidige configuraties van uw organisatie op haalt en valideert op basis van Microsoft 365 aanbevolen aanbevolen procedures. Deze best practices zijn gebaseerd op een reeks besturingselementen die belangrijke voorschriften en standaarden bevatten voor gegevensbescherming en gegevensbeheer.

Met MCCA kunt u snel zien welke verbeteracties in Compliance Manager van toepassing zijn op uw huidige Microsoft 365 omgeving. Elke actie die door MCCA wordt geïdentificeerd, geeft u aanbevelingen voor de implementatie, met directe koppelingen naar Compliance Manager en de toepasselijke oplossing om corrigerende actie te ondernemen.

Een extra bron voor het begrijpen van MCCA is door de [README-instructies op GitHub.](https://github.com/OfficeDev/MCCA#overview) Deze pagina bevat gedetailleerde informatie over vereisten en bevat volledige installatie-instructies. U hebt geen account nodig GitHub om toegang te krijgen tot deze pagina.

**Beschikbaarheid:** MCCA is beschikbaar voor alle organisaties met Office 365- en Microsoft 365-licenties en klanten van de Amerikaanse overheid (GCC) Moderate, GCC High en Ministerie van Defensie (DoD).

## <a name="install-mcca-and-run-a-report"></a>MCCA installeren en een rapport uitvoeren

U kunt het hulpprogramma MCCA installeren met Windows PowerShell. Nadat u het hulpprogramma hebt gedownload en geïnstalleerd, hoeft u deze stappen niet te herhalen om rapporten uit te voeren. Telkens wanneer u MCCA opent, wordt u om uw aanmeldingsreferenties gevraagd en wordt er een nieuw, bijgewerkt rapport gegenereerd.

#### <a name="step-1-install-windows-powershell"></a>Stap 1: Windows PowerShell
Om te beginnen hebt u de Exchange Online PowerShell-module (v2.0.3 of hoger) nodig die beschikbaar is in de PowerShell-galerie. [Installatie-instructies krijgen.](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3)

#### <a name="step-2-install-mcca"></a>Stap 2: MCCA installeren

Als u MCCA wilt installeren, gebruikt u Eerst PowerShell in de beheerdersmodus. Volg de onderstaande stappen:

1. Selecteer de Windows **startknop.**
2. Typ **PowerShell,** klik met de rechtermuisknop op **Windows PowerShell** en selecteer vervolgens Als **beheerder uitvoeren.**
1. Typ bij de opdrachtprompt:

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a>Stap 3: Een rapport uitvoeren

Nadat u MCCA hebt geïnstalleerd, kunt u MCCA uitvoeren en een rapport genereren. Een rapport uitvoeren:

1. PowerShell openen
2. Voer de cmdlet uit:

    ```powershell
    Get-MCCAReport
    ```

   Als u een GCC hoge klant bent, moet u een extra invoerparameter opgeven om het rapport uit te voeren:

    ```powershell
    Get-MCCAReport -ExchangeEnvironmentName O365USGovGCCHigh
    ```

3. Wanneer MCCA is uitgevoerd, wordt er een eerste versiecontrole uitgevoerd en wordt om referenties gevraagd. Meld u bij de prompt Invoer van de gebruikersnaam aan met uw e-mailadres Microsoft 365 account ( bekijk de rollen die in aanmerking komen om[rapporten te maken).](#role-based-reporting) Voer vervolgens uw wachtwoord in bij de wachtwoordprompt.

Het genereren van uw rapport duurt ongeveer 2-5 minuten. Wanneer het klaar is, wordt een browservenster geopend en wordt uw HTML-rapport weergegeven. Telkens wanneer u het hulpprogramma uit runt, wordt om uw referenties gevraagd en wordt er een nieuw rapport gegenereerd. Dit rapport wordt lokaal opgeslagen in de volgende adreslijst:

C:\Gebruikers \<username> \AppData\Local\Microsoft\MCCA. 

U hebt toegang tot eerder gegenereerde rapporten vanuit deze adreslijst.

## <a name="understanding-your-report"></a>Uw rapport begrijpen

Uw rapport geeft gegevens weer op basis van de datum en tijd waarop het is gegenereerd. De bovenste sectie bevat details over wanneer deze is gegenereerd, de naam van uw organisatie en de tenant-id.

#### <a name="geolocation-based-reporting"></a>Geolocation-based reporting

In **de sectie** Notitie ziet u dat uw rapport is aangepast op basis van de geografische locatie van uw tenant. Aanbevelingen in het hulpprogramma wordt vermeld, is specifiek voor uw land of regio.

Uw geolocatieselectie wordt gebruikt om gevoelige informatietypen (SIT's) te beoordelen die relevant zijn voor die geolocatie en om een rapport te genereren dat is afgestemd op uw land of regio. Kies geolocaties op basis van gegevens in uw tenant.

Als u de locatiegegevens van uw rapport wilt wijzigen, moet u een geolocatie-invoerparameter opgeven. U kunt een of meerdere geolocaties kiezen die van toepassing zijn op uw tenant.

Volg deze instructies om een rapport uit te voeren op basis van een specifieke locatie:

1. PowerShell openen
2. Als u een bepaald gebied wilt opgeven, wordt een cmdlet uitgevoerd met behulp van de getallen uit de onderstaande tabel die overeenkomen met het land of de regio. Voer meerdere getallen in door ze te scheiden met een komma. Op de cmdlet hieronder wordt bijvoorbeeld een aangepast rapport uitgevoerd voor Asia-Pacific en Japan:

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | Invoer |  Land of regio | 
  | :------------- | :------------: |
  | 1 | Asia-Pacific |
  | 2 | Australië |
  | 3 | Canada |
  | 4 | Europa (exclusief Frankrijk) / Midden-Oosten / Afrika |
  | 5 | Frankrijk |
  | 6 | India |
  | 7 | Japan  |
  | 8 | Korea  |
  | 9 | Noord-Amerika (met uitzondering van Canada) |
  | 10 | Zuid-Amerika |
  | 11 | Zuid-Afrika |
  | 12 | Zwitserland |
  | 13 | Verenigde Arabische Emiraten |
  | 14 | Verenigd Koninkrijk |


 > [!NOTE]
> Het rapport bevat altijd door MCCA ondersteunde internationale gevoelige informatietypen, zoals SWIFT-code, creditcardnummer, enzovoort.

#### <a name="role-based-reporting"></a>Rapportering op basis van rollen

Uw rapport wordt ook aangepast op basis van uw rol.

In de onderstaande tabel ziet u welke rollen toegang hebben tot welke secties van het rapport. Andere rollen binnen uw organisatie (die niet worden vermeld in de onderstaande tabel) kunnen het hulpprogramma mogelijk niet uitvoeren of ze kunnen het hulpprogramma uitvoeren en hebben beperkte toegang tot informatie in het uiteindelijke rapport.

![MCCA - rollen](../media/compliance-manager-mcca-roles.png "MCCA-rollen")

Uitzonderingen:
1. Gebruikers kunnen geen rapport voor IP genereren, afgezien van de sectie 'IRM gebruiken Exchange Online'.
2. Gebruikers kunnen rapport genereren voor IP, afgezien van de sectie 'IRM gebruiken Exchange Online'.
3. Gebruikers kunnen rapport voor IP genereren, afgezien van de sectie Communicatie compliance in O365 inschakelen.
4. Gebruikers kunnen geen rapport voor IP genereren, afgezien van de sectie 'Auditing inschakelen in Office 365' sectie.
5. Gebruikers kunnen rapport genereren voor IP, behalve 'Auditing inschakelen in Office 365' sectie.

#### <a name="solutions-summary-section"></a>Sectie Overzicht van oplossingen

De **sectie Oplossingenoverzicht** van het rapport bevat een overzicht van verbeteracties die uw organisatie in Compliance Manager kan uitvoeren om uw nalevingsstatus te verbeteren.

![MCCA - samenvatting van oplossingen](../media/compliance-manager-mcca-solutions.png "Overzichtsscherm MCCA Solutions")

MCCA evalueert uw huidige configuraties op basis van de aanbevolen verbeteringsacties in Compliance Manager. Elke verbeteringsactie die door het hulpprogramma MCCA wordt geïdentificeerd als het nodig heeft om aandacht te krijgen, wordt weergegeven in deze sectie.

Naast elke Microsoft-oplossing staan vakken met kleurcode die het aantal items aangeven dat overeenkomt met verbeteracties in Compliance Manager. De acties zijn onderverdeeld in drie statusstatussen:

- **OK:** de acties die voldoen aan aanbevolen voorwaarden en op dit moment geen aandacht nodig hebben
- **Verbetering:** acties die aandacht nodig hebben
- **Aanbeveling:** acties die geen aandacht nodig hebben, maar waarvoor we aanbevolen aanbevolen procedures
 
Selecteer een vak om verbeteringen en aanbevelingen weer te geven.

**Items met de status Verbetering**

Selecteer de vervolgkeuzekeuze naast het label **Verbetering** rechts van de verbeteringsactie. U ziet een beknopt overzicht en informatie over uw huidige instellingen en de aanbevolen verbeteracties. De samenvatting bevat directe koppelingen naar Compliance Manager, de toepasselijke oplossing in de Microsoft 365-compliancecentrum en relevante documentatie.

Als u op de koppeling Compliancebeheer klikt, gaat u naar een gefilterde weergave van alle verbeteracties binnen die oplossing die u nog niet hebt geïmplementeerd. Hier ziet u het aantal punten dat u kunt behalen om uw [nalevingsscore](compliance-score-calculation.md)te verhogen, en de beoordelingen die erop van toepassing zijn, en de toepasselijke voorschriften en certificeringen.

Voor DLP is er een knop **Herstelscript** waarmee u een vooraf gegenereerd PowerShell-script krijgt op basis van wat wordt aanbevolen. U kunt deze rechtstreeks kopiëren en plakken in uw PowerShell-console. Er wordt een DLP-beleid in de testmodus

**Items met de status Aanbeveling**

Selecteer de vervolgkeuzekeuze naast het label **Aanbeveling** rechts van de verbeteringsactie. U ziet een overzicht van de huidige omgeving van uw organisatie Microsoft 365 de verbeteringsactie, samen met aanbevolen aanbevolen aanbevolen procedures.

## <a name="resources"></a>Middelen

Zie de INSTRUCTIES VOOR LEZEN op GitHub (geen GitHub [](https://github.com/OfficeDev/MCCA#overview) vereist) voor meer informatie over het installeren, instellen en gebruiken van MCCA.

Voor meer informatie over Windows PowerShell, start u bij [How to use the PowerShell documentation](/powershell/scripting/how-to-use-docs?view=powershell-7). Zie ook [Windows PowerShell.](/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7)
