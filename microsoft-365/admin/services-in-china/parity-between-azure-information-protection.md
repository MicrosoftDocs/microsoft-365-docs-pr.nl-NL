---
title: Azure Information Protection-ondersteuning voor Office 365 beheerd door 21Vianet
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
description: Meer informatie over Azure Information Protection (AIP) voor Office 365 beheerd door 21Vianet en hoe u dit configureert voor klanten in China.
monikerRange: o365-21vianet
ms.openlocfilehash: 300e7633237511fb9de64199ae7cf54594f2239e
ms.sourcegitcommit: 3b369a44b71540c8b8214ce588a7aa6f47c3bb1e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099676"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>Azure Information Protection-ondersteuning voor Office 365 beheerd door 21Vianet

In dit artikel worden de verschillen beschreven tussen AIP-ondersteuning (Azure Information Protection) voor Office 365 beheerd door 21Vianet en commerciële aanbiedingen, evenals specifieke instructies voor het configureren van AIP voor klanten in China, waaronder hoe u de on-premises AIP-scanner installeert en inhoudsscantaken &mdash; beheert.

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Verschillen tussen AIP voor Office 365 beheerd door 21Vianet en commerciële aanbiedingen

Hoewel we alle commerciële functies en functionaliteit willen aanbieden aan klanten in China met onze AIP voor Office 365 beheerd door 21Vianet, is er een aantal ontbrekende functionaliteit die we willen benadrukken.

De volgende lijst bevat de bestaande hiaten tussen AIP voor Office 365 beheerd door 21Vianet en onze commerciële aanbiedingen vanaf januari 2021:

- IRM (Information Rights Management) wordt alleen ondersteund voor Microsoft 365-apps voor ondernemingen (build 11731.10000 of hoger). Office 2010, Office 2013 en andere Office 2016-versies worden niet ondersteund.

- Migratie van AD RMS (Active Directory Rights Management Services) naar AIP is momenteel niet beschikbaar.
  
- Het delen van beveiligde e-mailberichten met gebruikers in de commerciële cloud wordt ondersteund.
  
- Het delen van documenten en e-mailbijlagen met gebruikers in de commerciële cloud is momenteel niet beschikbaar. Dit omvat Office 365 beheerd door 21Vianet-gebruikers in de commerciële cloud, niet-Office 365 beheerd door 21Vianet-gebruikers in de commerciële cloud, en gebruikers met een RMS voor individuen-licentie.
  
- IRM met SharePoint (met IRM beveiligde sites en bibliotheken) is momenteel niet beschikbaar.
  
- De extensie voor mobiele apparaten voor AD RMS is momenteel niet beschikbaar.

- De [Mobile-viewer](/azure/information-protection/rms-client/mobile-app-faq) wordt niet ondersteund door Azure China 21Vianet.

- Het gebied AIP van de Azure Portal is niet beschikbaar voor klanten in China. Gebruik [PowerShell-opdrachten](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) in plaats van acties uit te voeren in de portal, zoals het installeren van de on-premises scanner en het beheren van uw inhoudsscantaken.

## <a name="configure-aip-for-customers-in-china"></a>AIP configureren voor klanten in China

AIP configureren voor klanten in China:
1. [Rights Management inschakelen voor de tenant.](#step-1-enable-rights-management-for-the-tenant)

2. [DNS-versleuteling configureren.](#step-2-configure-dns-encryption)

3. [Installeer en configureer de geïntegreerde AIP-labelclient.](#step-3-install-and-configure-the-aip-unified-labeling-client)

4. [Configureer AIP-apps in Windows.](#step-4-configure-aip-apps-on-windows)

5. [Installeer de on-premises AIP-scanner en beheer inhoudsscantaken.](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>Stap 1: Rights Management inschakelen voor de tenant

RmS moet zijn ingeschakeld voor de tenant om de versleuteling correct te laten werken.

1. Controleer of RMS is ingeschakeld:

    1. Start PowerShell als beheerder.
    2. Voer de AIPService-module uit als deze niet is `Install-Module AipService` geïnstalleerd.
    3. Importeer de module met `Import-Module AipService` behulp van .
    4. Maak verbinding met de service via `Connect-AipService -environmentname azurechinacloud` .
    5. Voer `(Get-AipServiceConfiguration).FunctionalState` de status uit en controleer of dit de status `Enabled` is.

2. Als dit de functionele status `Disabled` is, moet u de functie `Enable-AipService` uitvoeren.

### <a name="step-2-configure-dns-encryption"></a>Stap 2: DNS-versleuteling configureren

Versleuteling werkt alleen correct als Office-clienttoepassingen verbinding maken met het China-exemplaar van de service en van daardaan bootstrap. Als u clienttoepassingen wilt omleiden naar het juiste service-exemplaar, moet de tenantbeheerder een DNS SRV-record configureren met informatie over de Azure RMS-URL. Zonder de DNS SRV-record probeert de clienttoepassing standaard verbinding te maken met het openbare cloud-exemplaar en mislukt dit.

Bovendien wordt aangenomen dat gebruikers zich zullen aanmelden met een gebruikersnaam die is gebaseerd op het domein van tenants (bijvoorbeeld ) en niet met de gebruikersnaam `joe@contoso.cn` `onmschina` `joe@contoso.onmschina.cn` (bijvoorbeeld). De domeinnaam van de gebruikersnaam wordt gebruikt voor DNS-omleiding naar het juiste service-exemplaar.

#### <a name="configure-dns-encryption---windows"></a>DNS-versleuteling configureren - Windows

1. Krijg de RMS-id:

    1. Start PowerShell als beheerder.
    2. Voer de AIPService-module uit als deze niet is `Install-Module AipService` geïnstalleerd.
    3. Maak verbinding met de service via `Connect-AipService -environmentname azurechinacloud` .
    4. Voer `(Get-AipServiceConfiguration).RightsManagementServiceId` uit om de RMS-id op te halen.

2. Meld u aan bij uw DNS-provider, ga naar de DNS-instellingen voor het domein en voeg vervolgens een nieuwe SRV-record toe.

    - Service = `_rmsredir`
    - Protocol = `_http`
    - Name = `_tcp`
    - Target = `[GUID].rms.aadrm.cn` (waarbij GUID de RMS-id is)
    - Prioriteit, Gewicht, Seconden, TTL = standaardwaarden

3. Koppel het aangepaste domein aan de tenant in de [Azure Portal.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains) Er wordt dan een vermelding in de DNS-adressen gebruikt. Dit kan enkele minuten duren voordat de waarde is geverifieerd nadat u de waarde hebt toevoegt aan de DNS-instellingen.

4. Meld u aan bij het Microsoft 365-beheercentrum met de bijbehorende globale-beheerdersreferenties en voeg het domein toe (bijvoorbeeld) voor het maken van `contoso.cn` gebruikers. Tijdens het verificatieproces zijn mogelijk extra DNS-wijzigingen vereist. Wanneer verificatie is uitgevoerd, kunnen gebruikers worden gemaakt.

#### <a name="configure-dns-encryption---mac-ios-android"></a>DNS-versleuteling configureren - Mac, iOS, Android

Meld u aan bij uw DNS-provider, ga naar de DNS-instellingen voor het domein en voeg vervolgens een nieuwe SRV-record toe.

- Service = `_rmsdisco`
- Protocol = `_http`
- Name = `_tcp`
- Target = `api.aadrm.cn`
- Poort = `80`
- Prioriteit, Gewicht, Seconden, TTL = standaardwaarden

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a>Stap 3: de geïntegreerde AIP-labelclient installeren en configureren

Download de geïntegreerde AIP-labelclient van [het Microsoft Downloadcentrum.](https://www.microsoft.com/download/details.aspx?id=53018)

Zie voor meer informatie:

- [AIP-documentatie](/azure/information-protection/)
- [AIP-versiegeschiedenis en ondersteuningsbeleid](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [AIP-systeemvereisten](/azure/information-protection/requirements)
- [AIP-snelstart: De AIP-client implementeren](/azure/information-protection/quickstart-deploy-client)
- [AIP-beheerdershandleiding](/azure/information-protection/rms-client/clientv2-admin-guide)
- [AIP-gebruikershandleiding](/azure/information-protection/rms-client/clientv2-user-guide)
- [Meer informatie over gevoeligheidslabels voor Microsoft 365](/microsoft-365/compliance/sensitivity-labels)

### <a name="step-4-configure-aip-apps-on-windows"></a>Stap 4: AIP-apps configureren in Windows

AIP-apps in Windows hebben de volgende registersleutel nodig om ze te laten wijzen naar de juiste soevereine cloud voor Azure China:

- Register-knooppunt = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Name = `CloudEnvType`
- Waarde = `6` (standaard = 0)
- Type = `REG_DWORD`

> [!IMPORTANT]
> Zorg ervoor dat u de registersleutel niet verwijdert nadat u de installatie hebt verwijderd. Als de sleutel leeg, onjuist of niet aanwezig is, gedraagt de functionaliteit zich als de standaardwaarde (standaardwaarde = 0 voor de commerciële cloud). Als de sleutel leeg of onjuist is, wordt ook een afdrukfout aan het logboek toegevoegd.

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>Stap 5: de on-premises AIP-scanner installeren en inhoudsscantaken beheren

Installeer de on-premises AIP-scanner om uw netwerk- en inhouds shares te scannen op gevoelige gegevens en pas classificatie- en beveiligingslabels toe zoals geconfigureerd in het beleid van uw organisatie.

Wanneer u de scanner installeert en uw inhoudsscantaken beheert, gebruikt u de volgende cmdlets in plaats van de Azure Portal-interface die door de commerciële aanbiedingen wordt gebruikt:<br><br>

| Cmdlet | Beschrijving |
|--|--|
| [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | Hiermee voegt u een nieuwe opslagplaats toe aan uw inhoudsscan taak. |
| [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | Hier worden details over de inhoudsscan uitgevoerd. |
| [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | Haalt informatie op over de opslagplaatsen die zijn gedefinieerd voor uw inhoudsscan.. |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | Hiermee verwijdert u de inhoudsscan. |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | Hiermee verwijdert u een opslagplaats uit de inhoudsscan. |
| [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | Hiermee definieert u instellingen voor de inhoudsscan. |
| [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | Hiermee definieert u instellingen voor een bestaande opslagplaats in uw inhoudsscan.. |

Zie wat is de geïntegreerde labelscanner van Azure Information Protection voor meer [informatie?](/azure/information-protection/deploy-aip-scanner) En beheer de taken voor inhoudsscans [met alleen PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)
