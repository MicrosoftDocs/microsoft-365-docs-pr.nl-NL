---
title: Ondersteuning voor Azure Information Protection voor Office 365 beheerd door 21Vianet
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEU150
- GEA150
description: Meer informatie over Azure Information Protection (AIP) voor Office 365 beheerd door 21Vianet en hoe u deze configureert voor klanten in China.
monikerRange: o365-21vianet
ms.openlocfilehash: 8b85ae43df31bb1947b841d616cc83c3a0b614e4
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535840"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>Ondersteuning voor Azure Information Protection voor Office 365 beheerd door 21Vianet

In dit artikel worden de verschillen beschreven tussen AIP-ondersteuning (Azure Information Protection) voor Office 365 beheerd door 21Vianet en commerciële aanbiedingen, evenals specifieke instructies voor het configureren van AIP voor klanten in China, waaronder hoe u de on-premises AIP-scanner installeert en inhoudsscantaken &mdash; beheert.

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Verschillen tussen AIP voor Office 365 beheerd door 21Vianet en commerciële aanbiedingen

Hoewel ons doel is om alle commerciële functies en functionaliteit te leveren aan klanten in China met onze AIP voor Office 365 beheerd door 21Vianet-aanbieding, is er een aantal ontbrekende functionaliteit die we willen benadrukken.

De volgende lijst bevat de bestaande hiaten tussen AIP Office 365 beheerd door 21Vianet en onze commerciële aanbiedingen vanaf januari 2021:

- IRM (Information Rights Management) wordt alleen ondersteund voor Microsoft 365-apps voor ondernemingen (build 11731.10000 of hoger). Office 2010, Office 2013 en andere versies Office 2016 worden niet ondersteund.

- Migratie van Active Directory Rights Management Services (AD RMS) naar AIP is momenteel niet beschikbaar.
  
- Het delen van beveiligde e-mailberichten met gebruikers in de commerciële cloud wordt ondersteund.
  
- Het delen van documenten en e-mailbijlagen met gebruikers in de commerciële cloud is momenteel niet beschikbaar. Dit omvat Office 365 beheerd door 21Vianet-gebruikers in de commerciële cloud, niet-Office 365 beheerd door 21Vianet-gebruikers in de commerciële cloud en gebruikers met een RMS voor Individuen-licentie.
  
- IRM met SharePoint (met IRM beveiligde sites en bibliotheken) is momenteel niet beschikbaar.
  
- De mobiele apparaatextensie voor AD RMS is momenteel niet beschikbaar.

- De [mobiele viewer](/azure/information-protection/rms-client/mobile-app-faq) wordt niet ondersteund door Azure China 21Vianet.

- Het AIP-gebied van de Azure-portal is niet beschikbaar voor klanten in China. Gebruik [PowerShell-opdrachten](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) in plaats van acties uit te voeren in de portal, zoals het beheren en uitvoeren van uw inhoudsscantaken.

## <a name="configure-aip-for-customers-in-china"></a>AIP configureren voor klanten in China

AIP configureren voor klanten in China:
1. [Rights Management inschakelen voor de tenant](#step-1-enable-rights-management-for-the-tenant).

1. [Voeg de microsoft information protection sync service service principal toe.](#step-2-add-the-microsoft-information-protection-sync-service-service-principal)

1. [DNS-versleuteling configureren.](#step-3-configure-dns-encryption)

1. [Installeer en configureer de geïntegreerde AIP-labelingclient.](#step-4-install-and-configure-the-aip-unified-labeling-client)

1. [AIP-apps configureren op Windows.](#step-5-configure-aip-apps-on-windows)

1. [Installeer de on-premises AIP-scanner en beheer inhoudsscantaken.](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>Stap 1: Rights Management inschakelen voor de tenant

Om de versleuteling correct te laten werken, moet RMS zijn ingeschakeld voor de tenant.

1. Controleer of RMS is ingeschakeld:

    1. Start PowerShell als beheerder.
    2. Als de AIPService-module niet is geïnstalleerd, kunt u `Install-Module AipService` dit uitvoeren.
    3. Importeer de module met `Import-Module AipService` behulp van .
    4. Verbinding maken naar de service met `Connect-AipService -environmentname azurechinacloud` behulp van .
    5. Voer `(Get-AipServiceConfiguration).FunctionalState` uit en controleer of de status `Enabled` .

2. Als de functionele status `Disabled` is, wordt `Enable-AipService` uitgevoerd.

### <a name="step-2-add-the-microsoft-information-protection-sync-service-service-principal"></a>Stap 2: De Microsoft Information Protection Sync Service-service toevoegen

De **Microsoft Information Protection Sync Service service** principal is standaard niet beschikbaar in Azure China-tenants en is vereist voor Azure Information Protection.

1. Maak deze service-principal handmatig met behulp van [de cmdlet New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) en de toepassings-id voor `870c4f2e-85b6-4d43-bdda-6ed9a579b725` de Microsoft Information Protection Sync Service. 

    ```powershell 
    New-AzADServicePrincipal -ApplicationId 870c4f2e-85b6-4d43-bdda-6ed9a579b725
    ```

1. Nadat u de serviceprincipaal hebt toegevoegd, voegt u de benodigde machtigingen toe aan de service.

### <a name="step-3-configure-dns-encryption"></a>Stap 3: DNS-versleuteling configureren

Als versleuteling goed werkt, Office clienttoepassingen vanaf daar verbinding maken met het china-exemplaar van de service en de bootstrap. Als u clienttoepassingen wilt omleiden naar het juiste service-exemplaar, moet de tenantbeheerder een DNS-SRV-record configureren met informatie over de AZURE RMS-URL. Zonder de DNS SRV-record probeert de clienttoepassing standaard verbinding te maken met het openbare cloud-exemplaar en mislukt deze.

De aanname is ook dat gebruikers zich zullen aanmelden met een gebruikersnaam die is gebaseerd op het domein van de tenant (bijvoorbeeld), en niet met de `joe@contoso.cn` `onmschina` gebruikersnaam `joe@contoso.onmschina.cn` (bijvoorbeeld). De domeinnaam van de gebruikersnaam wordt gebruikt voor DNS-omleiding naar het juiste service-exemplaar.

#### <a name="configure-dns-encryption---windows"></a>DNS-versleuteling configureren - Windows

1. De RMS-id krijgen:

    1. Start PowerShell als beheerder.
    2. Als de AIPService-module niet is geïnstalleerd, kunt u `Install-Module AipService` dit uitvoeren.
    3. Verbinding maken naar de service met `Connect-AipService -environmentname azurechinacloud` behulp van .
    4. Voer `(Get-AipServiceConfiguration).RightsManagementServiceId` uit om de RMS-id op te halen.

2. Meld u aan bij uw DNS-provider, ga naar de DNS-instellingen voor het domein en voeg vervolgens een nieuwe SRV-record toe.

    - Service = `_rmsredir`
    - Protocol = `_http`
    - Naam = `_tcp`
    - Doel = `[GUID].rms.aadrm.cn` (waarbij GUID de RMS-id is)
    - Prioriteit, Gewicht, Seconden, TTL = standaardwaarden

3. Koppel het aangepaste domein aan de tenant in de [Azure-portal.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains) Hiermee voegt u een vermelding toe in DNS, die enkele minuten kan duren voordat u wordt geverifieerd nadat u de waarde hebt toevoegt aan de DNS-instellingen.

4. Meld u aan bij het Microsoft 365 beheercentrum met de bijbehorende globale beheerdersreferenties en voeg het domein (bijvoorbeeld) toe voor het maken `contoso.cn` van gebruikers. In het verificatieproces zijn mogelijk extra DNS-wijzigingen vereist. Wanneer verificatie is uitgevoerd, kunnen gebruikers worden gemaakt.

#### <a name="configure-dns-encryption---mac-ios-android"></a>DNS-versleuteling configureren - Mac, iOS, Android

Meld u aan bij uw DNS-provider, ga naar de DNS-instellingen voor het domein en voeg vervolgens een nieuwe SRV-record toe.

- Service = `_rmsdisco`
- Protocol = `_http`
- Naam = `_tcp`
- Doel = `api.aadrm.cn`
- Poort = `80`
- Prioriteit, Gewicht, Seconden, TTL = standaardwaarden


### <a name="step-4-install-and-configure-the-aip-unified-labeling-client"></a>Stap 4: De geïntegreerde AIP-labelingclient installeren en configureren

Download en installeer de geïntegreerde AIP-labelingclient vanuit [het Microsoft Downloadcentrum.](https://www.microsoft.com/download/details.aspx?id=53018)

Zie voor meer informatie:

- [AIP-documentatie](/azure/information-protection/)
- [AIP-versiegeschiedenis en ondersteuningsbeleid](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [AIP-systeemvereisten](/azure/information-protection/requirements)
- [AIP quickstart: De AIP-client implementeren](/azure/information-protection/quickstart-deploy-client)
- [AIP-beheerdershandleiding](/azure/information-protection/rms-client/clientv2-admin-guide)
- [AIP-gebruikershandleiding](/azure/information-protection/rms-client/clientv2-user-guide)
- [Meer informatie over Microsoft 365 gevoeligheidslabels](../../compliance/sensitivity-labels.md)

### <a name="step-5-configure-aip-apps-on-windows"></a>Stap 5: AIP-apps configureren op Windows

AIP-apps op Windows hebben de volgende registersleutel nodig om ze te wijzen naar de juiste soevereine cloud voor Azure China:

- Register-knooppunt = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Naam = `CloudEnvType`
- Waarde = `6` (standaard = 0)
- Type = `REG_DWORD`

> [!IMPORTANT]
> Zorg ervoor dat u de registersleutel niet verwijdert nadat u de registersleutel hebt verwijderd. Als de sleutel leeg, onjuist of niet aanwezig is, gedraagt de functionaliteit zich als de standaardwaarde (standaardwaarde = 0 voor de commerciële cloud). Als de sleutel leeg of onjuist is, wordt er ook een afdrukfout toegevoegd aan het logboek.

### <a name="step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>Stap 6: De on-premises AIP-scanner installeren en inhoudsscantaken beheren

Installeer de on-premises AIP-scanner om uw netwerk- en inhoudsaandelen te scannen op gevoelige gegevens en pas classificatie- en beveiligingslabels toe zoals geconfigureerd in het beleid van uw organisatie.

Wanneer u uw inhoudsscantaken configureert en beheert, gebruikt u de volgende procedure in plaats van de [Azure-portalinterface](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) die door de commerciële aanbiedingen wordt gebruikt.

Zie Wat is de geïntegreerde labelscanner voor [Azure Information Protection?](/azure/information-protection/deploy-aip-scanner) en [Uw inhoudsscantaken beheren met alleen PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)voor meer informatie.

**Uw scanner installeren en configureren:**

1. Meld u aan bij Windows servercomputer waarin de scanner wordt uitgevoerd. Gebruik een account met lokale beheerdersrechten en die machtigingen heeft om naar de hoofddatabase SQL Server schrijven.

1. Begin met PowerShell gesloten. Als u eerder de AIP-client en -scanner hebt geïnstalleerd, moet u ervoor zorgen dat de **AIPScanner-service** is gestopt.

1. Open een Windows PowerShell sessie met de optie **Uitvoeren als beheerder.**

1. Voer de [cmdlet Install-AIPScanner](/powershell/module/azureinformationprotection/Install-AIPScanner) uit en geef uw SQL Server-exemplaar op waarop u een database wilt maken voor de Azure Information Protection-scanner en een duidelijke naam voor het scannercluster.

    ```PowerShell
    Install-AIPScanner -SqlServerInstance <name> -Cluster <cluster name>
    ```

    > [!TIP]
    > U kunt dezelfde clusternaam gebruiken in de opdracht [Installeren-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) om meerdere scannerknooppunten aan hetzelfde cluster te koppelen. Als u hetzelfde cluster gebruikt voor meerdere scannerknooppunten, kunnen meerdere scanners samenwerken om uw scans uit te voeren.
    > 

1. Controleer of de service nu is geïnstalleerd met **Beheerhulpmiddelen**  >  **Services.**

    De geïnstalleerde service heeft de naam **Azure Information Protection Scanner** en is geconfigureerd voor gebruik met het scannerserviceaccount dat u hebt gemaakt.

1. Een Azure-token gebruiken voor uw scanner. Met een Azure AD-token kan de scanner zich verifiëren bij de Azure Information Protection-service, zodat de scanner niet-interactief kan worden uitgevoerd. 

    1. Open de Azure-portal en maak een Azure AD-toepassing om een toegangs token voor verificatie op te geven. Zie Bestanden op een [niet-interactieve](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)manier labelen voor Azure Information Protection voor meer informatie.
    
        > [!TIP]
        > Wanneer u Azure AD-toepassingen maakt en configureert voor de opdracht  [Set-AIPAuthentication,](/powershell/module/azureinformationprotection/set-aipauthentication) worden in het deelvenster API-machtigingen aanvragen de API's weergegeven die door mijn organisatie worden gebruikt in plaats van op het tabblad Api's van **Microsoft.**  Selecteer de **API's die mijn organisatie gebruikt** om vervolgens Azure Rights Management **Services.** 
        >

    1. Meld u aan met dit account en start een  PowerShell-sessie als aan uw scannerserviceaccount lokaal is toegewezen voor de installatie, Windows servercomputer. 
    
        Als uw scannerserviceaccount niet  kan worden verleend aan het lokaal aanmelden voor de installatie, gebruikt u de parameter *OnBehalfOf* met [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), zoals wordt beschreven in Bestanden [niet-interactief](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)labelen voor Azure Information Protection .

    1. [Voer Set-AIPAuthentication uit](/powershell/module/azureinformationprotection/set-aipauthentication)en geef waarden op die zijn gekopieerd uit uw Azure AD-toepassing:

      ```PowerShell
      Set-AIPAuthentication -AppId <ID of the registered app> -AppSecret <client secret sting> -TenantId <your tenant ID> -DelegatedUser <Azure AD account>
      ```

      Bijvoorbeeld:

      ```PowerShell
      $pscreds = Get-Credential CONTOSO\scanner
      Set-AIPAuthentication -AppId "77c3c1c3-abf9-404e-8b2b-4652836c8c66" -AppSecret "OAkk+rnuYc/u+]ah2kNxVbtrDGbS47L4" -DelegatedUser scanner@contoso.com -TenantId "9c11c87a-ac8b-46a3-8d5c-f4d0b72ee29a" -OnBehalfOf $pscreds
      Acquired application access token on behalf of CONTOSO\scanner.
      ```

    De scanner heeft nu een token om te verifiëren bij Azure AD. Dit token is geldig voor één jaar, twee jaar of nooit, volgens uw configuratie van de **web-app /API-clientgeheim** in Azure AD. Wanneer het token verloopt, moet u deze procedure herhalen.

1. Voer de [cmdlet Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) uit om de scanner in te stellen op functie in de offlinemodus. Uitvoeren:

    ```powershell
    Set-AIPScannerConfiguration -OnlineConfiguration Off
    ```

1. Voer de [cmdlet Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) uit om een standaard taak voor inhoudsscans te maken.

    De enige vereiste parameter in de **cmdlet Set-AIPScannerContentScanJob** is **Afdwingen.** Mogelijk wilt u op dit moment echter andere instellingen definiëren voor uw inhoudsscan. Bijvoorbeeld:

    ```powershell
    Set-AIPScannerContentScanJob -Schedule Manual -DiscoverInformationTypes PolicyOnly -Enforce Off -DefaultLabelType PolicyDefault -RelabelFiles Off -PreserveFileDetails On -IncludeFileTypes '' -ExcludeFileTypes '.msg,.tmp' -DefaultOwner <account running the scanner>
    ```

    De syntaxis hierboven configureert de volgende instellingen terwijl u doorgaat met de configuratie:

    - De planning van de scanner wordt handmatig *uitgevoerd*
    - Hiermee stelt u de informatietypen in die moeten worden gevonden op basis van het beleid voor gevoeligheidslabels
    - Wordt *een beleid* voor het labelen van gevoeligheid niet afgedwongen
    - Bestanden automatisch labelen op basis van inhoud, met behulp van het standaardlabel dat is gedefinieerd voor het beleid voor gevoeligheidslabels
    - Het *opnieuw* labelen van bestanden is niet toegestaan
    - Behoudt bestandsdetails tijdens het scannen en automatisch labelen, inclusief *datum gewijzigd,* *laatst* gewijzigd en gewijzigd *door* waarden
    - Hiermee stelt u de scanner in om MSG- en TMP-bestanden uit te sluiten tijdens het uitvoeren
    - Stelt de standaardeigenaar in op het account dat u wilt gebruiken bij het uitvoeren van de scanner

1. Gebruik de [cmdlet Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) om de opslagplaatsen te definiëren die u wilt scannen in uw inhoudsscan. Voer bijvoorbeeld het volgende uit:

    ```powershell
    Add-AIPScannerRepository -OverrideContentScanJob Off -Path 'c:\repoToScan'
    ```
    
    Gebruik een van de volgende syntaxis, afhankelijk van het type opslagplaats dat u toevoegt:

    - Gebruik voor een netwerk delen `\\Server\Folder` .
    - Gebruik voor SharePoint bibliotheek `http://sharepoint.contoso.com/Shared%20Documents/Folder` .
    - Voor een lokaal pad: `C:\Folder`
    - Voor een UNC-pad: `\\Server\Folder`

    > [!NOTE]
    > Jokertekens worden niet ondersteund en WebDav-locaties worden niet ondersteund.
    >
    > Als u de opslagplaats later wilt wijzigen, gebruikt u in plaats daarvan [de cmdlet Set-AIPScannerRepository.](/powershell/module/azureinformationprotection/set-aipscannerrepository) 


Ga zo nodig verder met de volgende stappen:

- [Een detectiecyclus uitvoeren en rapporten voor de scanner weergeven](/azure/information-protection/deploy-aip-scanner-manage#run-a-discovery-cycle-and-view-reports-for-the-scanner)
- [PowerShell gebruiken om de scanner zo te configureren dat classificatie en beveiliging worden toegepast](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-the-scanner-to-apply-classification-and-protection)
- [PowerShell gebruiken om een DLP-beleid met de scanner te configureren](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-a-dlp-policy-with-the-scanner)

De volgende tabel bevat PowerShell-cmdlets die relevant zijn voor het installeren van de scanner en het beheren van uw inhoudsscantaken:

| Cmdlet | Omschrijving |
|--|--|
| [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | Hiermee voegt u een nieuwe opslagplaats toe aan uw inhoudsscan. |
| [Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/get-aipscannerconfiguration)|Retourneert details over uw cluster. |
| [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | Hier krijgt u meer informatie over uw inhoudsscan. |
| [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | Hier krijgt u informatie over de opslagplaatsen die zijn gedefinieerd voor uw inhoudsscan. |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | Hiermee verwijdert u uw taak voor het scannen van inhoud. |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | Hiermee verwijdert u een opslagplaats uit uw taak voor inhoudsscans. |
| [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | Hiermee definieert u instellingen voor uw inhoudsscan. |
| [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | Hiermee definieert u instellingen voor een bestaande opslagplaats in uw inhoudsscan. |
| | |

Zie voor meer informatie:

- [Wat is de geïntegreerde labelscanner voor Azure Information Protection?](/azure/information-protection/deploy-aip-scanner)
- [De geïntegreerde labelingsscanner voor Azure Information Protection (AIP) configureren en installeren](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=powershell-only)
- [Beheer uw inhoudsscantaken alleen met PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)
