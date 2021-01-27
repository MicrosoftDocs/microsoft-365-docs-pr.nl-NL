---
title: Ondersteuning voor Azure Information Protection voor Office 365, beheerd door 21Vianet
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
description: Lees meer over Azure Information Protection (BEHEERDERSversie van Azure Information Protection) voor Office 365, beheerd door 21Vianet, en hoe u deze kunt configureren voor klanten in China.
monikerRange: o365-21vianet
ms.openlocfilehash: cee50384587ffc3e1e43eb9c6bb07d2e0ced7e13
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988042"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>Ondersteuning voor Azure Information Protection voor Office 365, beheerd door 21Vianet

Dit artikel gaat over de verschillen tussen de ondersteuning van Azure Information Protection (BEHEERDERSversie) van Office 365, beheerd door 21Vianet en commerciële aanbiedingen, en specifieke instructies voor het configureren van beheerders namen voor klanten in China, &mdash; waaronder het installeren van de on-premises scanner van beheerders en het beheren van inhoudsscan taken.

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Verschillen tussen beheerders van Office 365, beheerd door 21Vianet en commerciële aanbiedingen

Hoewel ons doel is om alle commerciële functies en functionaliteit te bieden aan klanten in China met onze BEHEERDERSversie van Office 365 die wordt beheerd door 21Vianet-aanbieding, is er een ontbrekende functionaliteit die we willen markeren.

De volgende lijst bevat de bestaande hiaten tussen beheerders van Office 365, beheerd door 21Vianet en onze commerciële aanbiedingen vanaf januari 2021:

- IRM (Information Rights Management) wordt alleen ondersteund voor Microsoft 365-apps voor Enterprise (build 11731,10000 of hoger). Office 2010, Office 2013 en andere Office 2016-versies worden niet ondersteund.

- Migratie van Active Directory Rights Management Services (AD RMS) naar een beheerders service is momenteel niet beschikbaar.
  
- Het delen van beveiligde e-mailberichten met gebruikers in de commerciële Cloud wordt ondersteund.
  
- Het delen van documenten en e-mailbijlagen met gebruikers in de commerciële Cloud is op dit moment niet beschikbaar. Dit omvat Office 365, beheerd door 21Vianet-gebruikers in de commerciële Cloud, niet-Office 365 die wordt beheerd door 21Vianet-gebruikers in de commerciële Cloud, en gebruikers met een RMS voor individuen-licentie.
  
- IRM met SharePoint (sites en bibliotheken met IRM-beveiliging) is op dit moment niet beschikbaar.
  
- De extensie van het mobiele apparaat voor AD RMS is op dit moment niet beschikbaar.

- De [Mobile-Viewer](/azure/information-protection/rms-client/mobile-app-faq) wordt niet ondersteund door Azure China 21vianet.

## <a name="configure-aip-for-customers-in-china"></a>Beheerders configureren voor klanten in China

Beheerders configureren voor klanten in China:
1. [Schakel Rights Management in voor de Tenant](#step-1-enable-rights-management-for-the-tenant).

2. [DNS-versleuteling configureren](#step-2-configure-dns-encryption).

3. [Installeer en configureer de toepassing beheerders Unified-labels](#step-3-install-and-configure-the-aip-unified-labeling-client).

4. Het [configureren van beheerders apps in Windows](#step-4-configure-aip-apps-on-windows).

5. [Installeer de on-premises scanner van beheerders en beheertaken voor inhouds onderzoek](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs). 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>Stap 1: het rechtenbeheer inschakelen voor de Tenant

Voor een juiste werking van de versleuteling moet RMS zijn ingeschakeld voor de Tenant.

1. Controleren of RMS is ingeschakeld:

    1. Start PowerShell als beheerder.
    2. Als de AIPService-module niet is geïnstalleerd, voert u deze opdracht uit `Install-Module AipService` .
    3. Importeer de module met `Import-Module AipService` .
    4. Maak verbinding met de service `Connect-AipService -environmentname azurechinacloud` .
    5. Voer `(Get-AipServiceConfiguration).FunctionalState` en controleer of de status is `Enabled` .

2. Voer dit uit als de functionele status wordt `Disabled` uitgevoerd `Enable-AipService` .

### <a name="step-2-configure-dns-encryption"></a>Stap 2: DNS-versleuteling configureren

Voor een juiste werking van versleuteling moet Office-clienttoepassingen verbinding maken met het exemplaar van de service en de bootstrap. Als u clienttoepassingen wilt omleiden naar het juiste service-exemplaar, moet de tenantbeheerder een DNS SRV-record configureren met informatie over de Azure RMS-URL. Zonder de DNS SRV-record probeert de clienttoepassing standaardverbinding te maken met het openbare Cloud exemplaar en mislukt de clienttoepassing.

Daarnaast is het raadzaam dat gebruikers zich aanmelden met een gebruikersnaam op basis van het domein van de Tenant domein (bijvoorbeeld `joe@contoso.cn` ), en niet de `onmschina` gebruikersnaam (bijvoorbeeld `joe@contoso.onmschina.cn` ). De domeinnaam van de gebruikersnaam wordt gebruikt voor DNS-omleiding naar het juiste service-exemplaar.

#### <a name="configure-dns-encryption---windows"></a>DNS-versleuteling configureren-Windows

1. De RMS-ID achterhalen:

    1. Start PowerShell als beheerder.
    2. Als de AIPService-module niet is geïnstalleerd, voert u deze opdracht uit `Install-Module AipService` .
    3. Maak verbinding met de service `Connect-AipService -environmentname azurechinacloud` .
    4. Uitvoeren `(Get-AipServiceConfiguration).RightsManagementServiceId` om de RMS-id te achterhalen.

2. Meld u aan bij uw DNS-provider, navigeer naar de DNS-instellingen voor het domein en voeg een nieuwe SRV-record toe.

    - Service = `_rmsredir`
    - Protocol = `_http`
    - Naam = `_tcp`
    - Target = `[GUID].rms.aadrm.cn` (waarbij GUID de RMS-id is)
    - Prioriteit, gewicht, seconden, TTL = standaardwaarden

3. Koppel het aangepaste domein aan de Tenant in de [Azure-Portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains). Hiermee voegt u een vermelding toe aan DNS, wat kan enkele minuten duren voordat deze is toegevoegd aan de DNS-instellingen.

4. Meld u aan bij het Microsoft 365-Beheercentrum met de bijbehorende globale-beheerdersreferenties en voeg het domein toe (bijvoorbeeld `contoso.cn` ) voor het maken van de gebruiker. In het verificatieproces zijn er mogelijk extra DNS-wijzigingen vereist. Wanneer de verificatie is voltooid, kunnen gebruikers maken.

#### <a name="configure-dns-encryption---mac-ios-android"></a>DNS-versleuteling configureren-Mac, iOS, Android

Meld u aan bij uw DNS-provider, navigeer naar de DNS-instellingen voor het domein en voeg een nieuwe SRV-record toe.

- Service = `_rmsdisco`
- Protocol = `_http`
- Naam = `_tcp`
- Doel = `api.aadrm.cn`
- Poort = `80`
- Prioriteit, gewicht, seconden, TTL = standaardwaarden

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a>Stap 3: de client van het beheerders bare Unified-etiket installeren en configureren

Download de BEHEERDERSversie van het [Microsoft Downloadcentrum](https://www.microsoft.com/download/details.aspx?id=53018).

Zie voor meer informatie:

- [BEHEERDERS documentatie](/azure/information-protection/)
- [Beheerdersversie geschiedenis en ondersteuningsbeleid](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [Systeemvereisten voor beheerders](/azure/information-protection/requirements)
- [BEHEERDERS-Snelstartgids: de beheerders-client implementeren](/azure/information-protection/quickstart-deploy-client)
- [Beheerdershandleiding van beheerders](/azure/information-protection/rms-client/clientv2-admin-guide)
- [Beheerdershandleiding voor beheerders](/azure/information-protection/rms-client/clientv2-user-guide)
- [Meer informatie over Microsoft 365-reductie-labels](/microsoft-365/compliance/sensitivity-labels)

### <a name="step-4-configure-aip-apps-on-windows"></a>Stap 4: beheerders-apps configureren in Windows

In de online-apps van Windows is de volgende registersleutel nodig om ze te laten verwijzen naar de juiste soevereine wolk voor Azure China:

- Register knooppunt = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Naam = `CloudEnvType`
- Waarde = `6` (standaard = 0)
- Typ = `REG_DWORD`

> [!IMPORTANT]
> Zorg dat u de registersleutel niet verwijdert na verwijdering. Als de sleutel leeg, ongeldig of niet-bestaand is, werkt de functie als standaardwaarde (standaardwaarde = 0 voor de commerciële Cloud). Als de sleutel leeg of onjuist is, wordt een afdrukfout ook toegevoegd aan het logboek.

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>Stap 5: de on-premises scanner van de BEHEERDERSversie installeren en inhoudsscan taken beheren

Installeer de on-premises on-premises scanner van de BEHEERDERSversie om uw netwerk-en inhouds aandelen te scannen op gevoelige gegevens en om classificatie-en beveiligings etiketten toe te passen, zoals geconfigureerd in het beleid van uw organisatie.

Wanneer u de scanner installeert en uw inhoudsscan taken beheert, gebruikt u de volgende cmdlets in plaats van de Azure Portal-interface die wordt gebruikt door de commerciële aanbiedingen:<br><br>

| Cmdlet | Beschrijving |
|--|--|
| [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | Hiermee voegt u een nieuwe bibliotheek toe aan uw inhoudsscan taak. |
| [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | Hiermee krijgt u meer informatie over uw inhoudsscan taak. |
| [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | Hiermee krijgt u meer informatie over opslaglocaties die zijn gedefinieerd voor uw inhoudsscan taak. |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | Hiermee verwijdert u uw inhoudsscan taak. |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | Hiermee verwijdert u een bibliotheek van uw inhoudsscan taak. |
| [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | Definieert de instellingen voor uw inhoudsscan taak. |
| [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | Definieert instellingen voor een bestaande bibliotheek in uw inhoudsscan taak. |

Zie voor meer informatie [Wat is de uitgebreide scanner van Azure Information Protection?](/azure/information-protection/deploy-aip-scanner) en [beheertaken voor inhouds onderzoek via PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).