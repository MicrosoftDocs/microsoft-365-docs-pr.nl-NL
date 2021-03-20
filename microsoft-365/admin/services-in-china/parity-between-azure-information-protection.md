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
ms.openlocfilehash: 77790249cbd544b2f11e9a16dd77bab297cac509
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914316"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>Ondersteuning voor Azure Information Protection voor Office 365 beheerd door 21Vianet

In dit artikel worden de verschillen beschreven tussen AIP-ondersteuning (Azure Information Protection) voor Office 365 beheerd door 21Vianet en commerciële aanbiedingen, evenals specifieke instructies voor het configureren van AIP voor klanten in China, waaronder hoe u de on-premises AIP-scanner installeert en inhoudsscantaken &mdash; beheert.

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Verschillen tussen AIP voor Office 365 beheerd door 21Vianet en commerciële aanbiedingen

Hoewel ons doel is om alle commerciële functies en functionaliteit te leveren aan klanten in China met onze AIP voor Office 365 beheerd door 21Vianet-aanbieding, is er een aantal ontbrekende functionaliteit die we willen benadrukken.

De volgende lijst bevat de bestaande hiaten tussen AIP voor Office 365 beheerd door 21Vianet en onze commerciële aanbiedingen vanaf januari 2021:

- IRM (Information Rights Management) wordt alleen ondersteund voor Microsoft 365 Apps voor ondernemingen (build 11731.10000 of hoger). Office 2010, Office 2013 en andere Office 2016-versies worden niet ondersteund.

- Migratie van Active Directory Rights Management Services (AD RMS) naar AIP is momenteel niet beschikbaar.
  
- Het delen van beveiligde e-mailberichten met gebruikers in de commerciële cloud wordt ondersteund.
  
- Het delen van documenten en e-mailbijlagen met gebruikers in de commerciële cloud is momenteel niet beschikbaar. Dit omvat Office 365 beheerd door 21Vianet-gebruikers in de commerciële cloud, niet-Office 365 beheerd door 21Vianet-gebruikers in de commerciële cloud en gebruikers met een RMS voor Individuen-licentie.
  
- IRM met SharePoint (met IRM beveiligde sites en bibliotheken) is momenteel niet beschikbaar.
  
- De mobiele apparaatextensie voor AD RMS is momenteel niet beschikbaar.

- De [mobiele viewer](/azure/information-protection/rms-client/mobile-app-faq) wordt niet ondersteund door Azure China 21Vianet.

- Het AIP-gebied van de Azure-portal is niet beschikbaar voor klanten in China. Gebruik [PowerShell-opdrachten](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) in plaats van acties uit te voeren in de portal, zoals het installeren van de on-premises scanner en het beheren van uw inhoudsscantaken.

## <a name="configure-aip-for-customers-in-china"></a>AIP configureren voor klanten in China

AIP configureren voor klanten in China:
1. [Rights Management inschakelen voor de tenant](#step-1-enable-rights-management-for-the-tenant).

2. [DNS-versleuteling configureren.](#step-2-configure-dns-encryption)

3. [Installeer en configureer de geïntegreerde AIP-labelingclient.](#step-3-install-and-configure-the-aip-unified-labeling-client)

4. [AIP-apps configureren in Windows.](#step-4-configure-aip-apps-on-windows)

5. [Installeer de on-premises AIP-scanner en beheer inhoudsscantaken.](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>Stap 1: Rights Management inschakelen voor de tenant

Om de versleuteling correct te laten werken, moet RMS zijn ingeschakeld voor de tenant.

1. Controleer of RMS is ingeschakeld:

    1. Start PowerShell als beheerder.
    2. Als de AIPService-module niet is geïnstalleerd, kunt u `Install-Module AipService` dit uitvoeren.
    3. Importeer de module met `Import-Module AipService` behulp van .
    4. Maak verbinding met de service met `Connect-AipService -environmentname azurechinacloud` behulp van .
    5. Voer `(Get-AipServiceConfiguration).FunctionalState` uit en controleer of de status `Enabled` .

2. Als de functionele status `Disabled` is, wordt `Enable-AipService` uitgevoerd.

### <a name="step-2-configure-dns-encryption"></a>Stap 2: DNS-versleuteling configureren

Als versleuteling goed werkt, moeten Office-clienttoepassingen vanaf daar verbinding maken met het China-exemplaar van de service en de bootstrap. Als u clienttoepassingen wilt omleiden naar het juiste service-exemplaar, moet de tenantbeheerder een DNS-SRV-record configureren met informatie over de AZURE RMS-URL. Zonder de DNS SRV-record probeert de clienttoepassing standaard verbinding te maken met het openbare cloud-exemplaar en mislukt deze.

De aanname is ook dat gebruikers zich zullen aanmelden met een gebruikersnaam die is gebaseerd op het domein van de tenant (bijvoorbeeld), en niet met de `joe@contoso.cn` `onmschina` gebruikersnaam `joe@contoso.onmschina.cn` (bijvoorbeeld). De domeinnaam van de gebruikersnaam wordt gebruikt voor DNS-omleiding naar het juiste service-exemplaar.

#### <a name="configure-dns-encryption---windows"></a>DNS-versleuteling configureren - Windows

1. De RMS-id krijgen:

    1. Start PowerShell als beheerder.
    2. Als de AIPService-module niet is geïnstalleerd, kunt u `Install-Module AipService` dit uitvoeren.
    3. Maak verbinding met de service met `Connect-AipService -environmentname azurechinacloud` behulp van .
    4. Voer `(Get-AipServiceConfiguration).RightsManagementServiceId` uit om de RMS-id op te halen.

2. Meld u aan bij uw DNS-provider, ga naar de DNS-instellingen voor het domein en voeg vervolgens een nieuwe SRV-record toe.

    - Service = `_rmsredir`
    - Protocol = `_http`
    - Naam = `_tcp`
    - Doel = `[GUID].rms.aadrm.cn` (waarbij GUID de RMS-id is)
    - Prioriteit, Gewicht, Seconden, TTL = standaardwaarden

3. Koppel het aangepaste domein aan de tenant in de [Azure-portal.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains) Hiermee voegt u een vermelding toe in DNS, die enkele minuten kan duren voordat u wordt geverifieerd nadat u de waarde hebt toevoegt aan de DNS-instellingen.

4. Meld u aan bij het Microsoft 365-beheercentrum met de bijbehorende globale beheerdersreferenties en voeg het domein (bijvoorbeeld) toe voor het maken `contoso.cn` van gebruikers. In het verificatieproces zijn mogelijk extra DNS-wijzigingen vereist. Wanneer verificatie is uitgevoerd, kunnen gebruikers worden gemaakt.

#### <a name="configure-dns-encryption---mac-ios-android"></a>DNS-versleuteling configureren - Mac, iOS, Android

Meld u aan bij uw DNS-provider, ga naar de DNS-instellingen voor het domein en voeg vervolgens een nieuwe SRV-record toe.

- Service = `_rmsdisco`
- Protocol = `_http`
- Naam = `_tcp`
- Doel = `api.aadrm.cn`
- Poort = `80`
- Prioriteit, Gewicht, Seconden, TTL = standaardwaarden

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a>Stap 3: De geïntegreerde AIP-labelclient installeren en configureren

Download de geïntegreerde AIP-labelingclient in het [Microsoft Downloadcentrum.](https://www.microsoft.com/download/details.aspx?id=53018)

Zie voor meer informatie:

- [AIP-documentatie](/azure/information-protection/)
- [AIP-versiegeschiedenis en ondersteuningsbeleid](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [AIP-systeemvereisten](/azure/information-protection/requirements)
- [AIP quickstart: De AIP-client implementeren](/azure/information-protection/quickstart-deploy-client)
- [AIP-beheerdershandleiding](/azure/information-protection/rms-client/clientv2-admin-guide)
- [AIP-gebruikershandleiding](/azure/information-protection/rms-client/clientv2-user-guide)
- [Meer informatie over gevoeligheidslabels voor Microsoft 365](../../compliance/sensitivity-labels.md)

### <a name="step-4-configure-aip-apps-on-windows"></a>Stap 4: AIP-apps configureren in Windows

AIP-apps in Windows hebben de volgende registersleutel nodig om ze te wijzen naar de juiste soevereine cloud voor Azure China:

- Register-knooppunt = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Naam = `CloudEnvType`
- Waarde = `6` (standaard = 0)
- Type = `REG_DWORD`

> [!IMPORTANT]
> Zorg ervoor dat u de registersleutel niet verwijdert nadat u de registersleutel hebt verwijderd. Als de sleutel leeg, onjuist of niet aanwezig is, gedraagt de functionaliteit zich als de standaardwaarde (standaardwaarde = 0 voor de commerciële cloud). Als de sleutel leeg of onjuist is, wordt er ook een afdrukfout toegevoegd aan het logboek.

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>Stap 5: De on-premises AIP-scanner installeren en inhoudsscantaken beheren

Installeer de on-premises AIP-scanner om uw netwerk- en inhoudsaandelen te scannen op gevoelige gegevens en pas classificatie- en beveiligingslabels toe zoals geconfigureerd in het beleid van uw organisatie.

Wanneer u de scanner installeert en uw inhoudsscantaken beheert, gebruikt u de volgende cmdlets in plaats van de Azure-portalinterface die door de commerciële aanbiedingen wordt gebruikt:<br><br>

| Cmdlet | Beschrijving |
|--|--|
| [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | Hiermee voegt u een nieuwe opslagplaats toe aan uw inhoudsscan. |
| [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | Hier krijgt u meer informatie over uw inhoudsscan. |
| [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | Hier krijgt u informatie over de opslagplaatsen die zijn gedefinieerd voor uw inhoudsscan. |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | Hiermee verwijdert u uw taak voor het scannen van inhoud. |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | Hiermee verwijdert u een opslagplaats uit uw taak voor inhoudsscans. |
| [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | Hiermee definieert u instellingen voor uw inhoudsscan. |
| [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | Hiermee definieert u instellingen voor een bestaande opslagplaats in uw inhoudsscan. |

Zie Wat is de geïntegreerde labelscanner voor [Azure Information Protection?](/azure/information-protection/deploy-aip-scanner) en [Uw inhoudsscantaken beheren met alleen PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)voor meer informatie.