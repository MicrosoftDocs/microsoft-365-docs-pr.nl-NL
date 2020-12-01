---
title: Pariteit tussen Azure Information Protection voor Office 365, beheerd door 21Vianet en commerciële aanbiedingen
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
description: Meer informatie over Azure Information Protection voor Office 365, beheerd door 21Vianet, en hoe u dit configureert voor klanten in China.
monikerRange: o365-21vianet
ms.openlocfilehash: 7be40466c43a49cf51a2a2c1c273cef035bee831
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519339"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Pariteit tussen Azure Information Protection voor Office 365, beheerd door 21Vianet en commerciële aanbiedingen

Hoewel ons doel is om alle commerciële functies en functionaliteit te bieden aan klanten in China met onze Azure Information Protection voor Office 365, beheerd door 21Vianet-aanbieding, is er een ontbrekende functionaliteit die we willen markeren.

De volgende lijst bevat de bestaande hiaten tussen Azure Information Protection voor Office 365, beheerd door 21Vianet en onze commerciële aanbiedingen vanaf juli 2019:

- IRM (Information Rights Management) wordt alleen ondersteund voor Microsoft 365-apps voor Enterprise (build 11731,10000 of hoger). Office 2010, Office 2013 en andere Office 2016-versies worden niet ondersteund.

- Migratie van Active Directory Rights Management Services (AD RMS) naar Azure Information Protection is momenteel niet beschikbaar.
  
- Het delen van beveiligde e-mailberichten voor gebruikers in de commerciële Cloud wordt ondersteund.
  
- Het delen van documenten en e-mailbijlagen aan gebruikers in de commerciële Cloud is op dit moment niet beschikbaar. Dit omvat Office 365, beheerd door 21Vianet-gebruikers in de commerciële Cloud, niet-Office 365 die wordt beheerd door 21Vianet-gebruikers in de commerciële Cloud, en gebruikers met een RMS voor individuen-licentie.
  
- IRM met SharePoint (sites en bibliotheken met IRM-beveiliging) is op dit moment niet beschikbaar.
  
- De extensie van het mobiele apparaat voor AD RMS is op dit moment niet beschikbaar.

## <a name="configuring-azure-information-protection-for-customers-in-china"></a>Azure Information Protection configureren voor klanten in China

### <a name="enable-rights-management-for-the-tenant"></a>Rechtenbeheer inschakelen voor de Tenant

Voor een juiste werking van de versleuteling moet RMS zijn ingeschakeld voor de Tenant.

- Controleer of de RMS is ingeschakeld:
  1. Start PowerShell als beheerder.
  2. Als de module AIPService niet is geïnstalleerd, voert u deze opdracht uit `Install-Module AipService` .
  3. Importeer de module met `Import-Module AipService` .
  4. Maak verbinding met de service `Connect-AipService -environmentname azurechinacloud` .
  5. Voer `(Get-AipServiceConfiguration).FunctionalState` en controleer of de status is `Enabled` .

- Voer dit uit als de functionele status wordt `Disabled` uitgevoerd `Enable-AipService` .

### <a name="dns-configuration-for-encryption-windows"></a>DNS-configuratie voor versleuteling (Windows)

Voor een juiste werking van versleuteling moet Office-clienttoepassingen verbinding maken met het exemplaar van de service en de bootstrap. Als u clienttoepassingen wilt omleiden naar het juiste service-exemplaar, moet de tenantbeheerder een DNS SRV-record configureren met informatie over de Azure RMS-URL. Zonder de DNS SRV-record probeert de clienttoepassing standaardverbinding te maken met het openbare Cloud exemplaar en mislukt de clienttoepassing.

Daarnaast is het raadzaam dat gebruikers zich aanmelden met een gebruikersnaam op basis van het domein van de Tenant domein (bijvoorbeeld `joe@contoso.cn` ), en niet de `onmschina` gebruikersnaam (bijvoorbeeld `joe@contoso.onmschina.cn` ). De domeinnaam van de gebruikersnaam wordt gebruikt voor DNS-omleiding naar het juiste service-exemplaar.

- De RMS-ID achterhalen:
  1. Start PowerShell als beheerder.
  2. Als de module AIPService niet is geïnstalleerd, voert u deze opdracht uit `Install-Module AipService` .
  3. Maak verbinding met de service `Connect-AipService -environmentname azurechinacloud` .
  4. Uitvoeren `(Get-AipServiceConfiguration).RightsManagementServiceId` om de RMS-id te achterhalen.

- Meld u aan bij uw DNS-provider, navigeer naar de DNS-instellingen voor het domein en voeg een nieuwe SRV-record toe.
  - Service = `_rmsredir`
  - Protocol = `_http`
  - Naam = `_tcp`
  - Target = `[GUID].rms.aadrm.cn` (waarbij GUID de RMS-id is)
  - Prioriteit, gewicht, seconden, TTL = standaardwaarden

- Koppel het aangepaste domein aan de Tenant in de [Azure-Portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains). Hiermee voegt u een vermelding toe aan DNS, wat kan enkele minuten duren voordat deze is toegevoegd aan de DNS-instellingen.

- Meld u aan bij het Microsoft 365-Beheercentrum met de bijbehorende globale-beheerdersreferenties en voeg het domein toe (bijvoorbeeld `contoso.cn` ) voor het maken van de gebruiker. In het verificatieproces zijn er mogelijk extra DNS-wijzigingen vereist. Wanneer de verificatie is voltooid, kunnen gebruikers maken.

### <a name="dns-configuration-for-encryption-mac-ios-android"></a>DNS-configuratie voor versleuteling (Mac, iOS, Android)

- Meld u aan bij uw DNS-provider, navigeer naar de DNS-instellingen voor het domein en voeg een nieuwe SRV-record toe.
  - Service = `_rmsdisco`
  - Protocol = `_http`
  - Naam = `_tcp`
  - Doel = `api.aadrm.cn`
  - Poort = `80`
  - Prioriteit, gewicht, seconden, TTL = standaardwaarden
