---
title: Office 365, beheerd door 21Vianet
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: mnirkhe
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
description: Meer informatie over Azure Information Protection voor Office 365 wordt beheerd door 21Vianet en hoe u deze configureert voor klanten in China.
monikerRange: o365-21vianet
ms.openlocfilehash: 1f5d73f5c421a545ea0085f018a2c2a703b0b374
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399036"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Pariteit tussen Azure Information Protection voor Office 365 die wordt beheerd door 21Vianet en commerciële aanbiedingen

Hoewel ons doel is om alle commerciële functies en functionaliteit te leveren aan klanten in China met onze Azure Information Protection for Office 365 die wordt beheerd door 21Vianet-aanbieding, is er een aantal ontbrekende functionaliteit die we willen benadrukken.

Dit zijn de bestaande hiaten tussen Azure Information Protection voor Office 365 die worden beheerd door 21Vianet en ons commerciële aanbod vanaf juli 2019:

- Information Rights Management (IRM) wordt alleen ondersteund voor Microsoft 365 Apps for enterprise (build 11731.10000 of hoger). Office 2010, Office 2013 en andere Office 2016-versies worden niet ondersteund.

- Migratie van Active Directory Rights Management Services (AD RMS) naar Azure Information Protection is momenteel niet beschikbaar.
  
- Het delen van beveiligde e-mails met gebruikers in de commerciële cloud wordt ondersteund.
  
- Het delen van documenten en e-mailbijlagen aan gebruikers in de commerciële cloud is momenteel niet beschikbaar. Dit omvat Office 365 dat wordt beheerd door 21Vianet-gebruikers in de commerciële cloud, niet-Office 365 die wordt beheerd door 21Vianet-gebruikers in de commerciële cloud en gebruikers met een RMS for Individuals-licentie.
  
- IRM met SharePoint (IRM-beschermde sites en bibliotheken) is momenteel niet beschikbaar.
  
- De Rights Management Connector is momenteel niet beschikbaar.
  
- De extensie Voor mobiele apparaten voor AD RMS is momenteel niet beschikbaar.

## <a name="configuring-azure-information-protection-for-customers-in-china"></a>Azure-informatiebeveiliging configureren voor klanten in China

### <a name="enable-rights-management-for-the-tenant"></a>Rechtenbeheer inschakelen voor de tenant

Om de versleuteling correct te laten werken, moet de RMS zijn ingeschakeld voor de tenant.

- Controleer of het RMS is ingeschakeld:
  1. Start PowerShell als beheerder.
  2. Als de AIPService-module niet is geïnstalleerd, voert u uit  `Install-Module AipService` .
  3. Importeer de module met behulp van `Import-Module AipService` .
  4. Maak verbinding met de service via  `Connect-AipService -environmentname azurechinacloud` .
  5. Uitvoeren  `(Get-AipServiceConfiguration).FunctionalState`   en controleren of de status  `Enabled` is.

- Als de functionele status  `Disabled` is, voert u uit  `Enable-AipService` .

### <a name="dns-configuration-for-encryption-windows"></a>DNS-configuratie voor versleuteling (Windows)

Om versleuteling correct te laten werken, moeten Office-clienttoepassingen verbinding maken met het China-exemplaar van de service en bootstrap van daaruit. Als u clienttoepassingen wilt omleiden naar de juiste service-instantie, moet de tenantbeheerder een DNS SRV-record configureren met informatie over de AZURE RMS-URL. Zonder de DNS SRV-record probeert de clienttoepassing standaard verbinding te maken met de openbare cloud-instantie en mislukt deze.

Ook is de veronderstelling dat gebruikers zullen inloggen met een gebruikersnaam op basis van de tenant-eigendom domein `joe@contoso.cn` (bijvoorbeeld), en niet de gebruikersnaam `onmschina` (bijvoorbeeld, `joe@contoso.onmschina.cn` ). De domeinnaam van de gebruikersnaam wordt gebruikt voor DNS-omleiding naar de juiste serviceinstantie.

- Haal de RMS-id op:
  1. Start PowerShell als beheerder.
  2. Als de AIPService-module niet is geïnstalleerd, voert u uit  `Install-Module AipService` .
  3. Maak verbinding met de service via  `Connect-AipService -environmentname azurechinacloud` .
  4. Ren  `(Get-AipServiceConfiguration).RightsManagementServiceId`   om de RMS-id te krijgen.

- Meld u aan bij uw DNS-provider, navigeer naar de DNS-instellingen voor het domein en voeg vervolgens een nieuwe SRV-record toe.
  - Service = `_rmsredir`
  - Protocol = `_http`
  - Naam = `_tcp`
  - Doel =  `[GUID].rms.aadrm.cn`   (waarbij GUID de RMS-id is)
  - Prioriteit, Gewicht, Seconden, TTL = standaardwaarden

- Koppel het aangepaste domein aan de tenant in de [Azure-portal.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains) Dit voegt een vermelding in DNS toe, wat enkele minuten kan duren voordat u wordt geverifieerd nadat u de waarde aan de DNS-instellingen hebt toegevoegd.

- Meld u aan bij het Microsoft 365-beheercentrum met de bijbehorende globale beheerdersreferenties en voeg het domein (bijvoorbeeld ) toe `contoso.cn` voor het maken van gebruikers. In het verificatieproces zijn mogelijk aanvullende DNS-wijzigingen vereist. Zodra de verificatie is uitgevoerd, kunnen gebruikers worden gemaakt.

### <a name="dns-configuration-for-encryption-mac-ios-android"></a>DNS-configuratie voor versleuteling (Mac, iOS, Android)

- Meld u aan bij uw DNS-provider, navigeer naar de DNS-instellingen voor het domein en voeg vervolgens een nieuwe SRV-record toe.
  - Service = `_rmsdisco`
  - Protocol = `_http`
  - Naam = `_tcp`
  - Doel = `api.aadrm.cn`
  - Poort = `80`
  - Prioriteit, Gewicht, Seconden, TTL = standaardwaarden
