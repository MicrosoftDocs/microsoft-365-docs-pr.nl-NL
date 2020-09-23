---
title: Extra eindpunten die niet zijn opgenomen in het Office 365 IP Address en de webservice URL-webservice
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/29/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: ''
description: "Overzicht: de nieuwe webservice van het eindpunt biedt geen klein aantal eindpunten voor specifieke scenario's."
hideEdit: true
ms.openlocfilehash: 30d0c7af8420f85abf820839a26c989704860c0a
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235580"
---
# <a name="additional-endpoints-not-included-in-the-office-365-ip-address-and-url-web-service"></a>Extra eindpunten die niet zijn opgenomen in het Office 365 IP Address en de webservice URL-webservice

Sommige netwerkeindpunten zijn eerder gepubliceerd en zijn niet opgenomen in de [IP-adressen en url's van Office 365](microsoft-365-ip-web-service.md). Het web service-bereik is netwerkeindpunten die vereist zijn voor de connectiviteit van een gebruiker van Office 365 via een Enterprise perimeternetwerk. Dit omvat momenteel niet:

1. Netwerkverbinding die mogelijk is vereist van een Microsoft-datacenter voor een klanten netwerk (inkomende netwerkverkeer voor hybride servers).
2. Netwerkverbinding van servers in het netwerk van de klant in de gehele organisatie (uitgaande server netwerkverkeer).
3. Niet-veelvoorkomende scenario's voor de vereisten voor netwerkverbindingen van een gebruiker.
4. Connectiviteits vereisten voor DNS-omzetting (niet hieronder genoemd).
5. Vertrouwde sites in Internet Explorer of Microsoft Edge.

Naast de DNS zijn deze allemaal optioneel voor de meeste klanten, tenzij u een specifiek scenario nodig hebt.

| Rubriek | Doel | Destination | Type |
|:-----|:-----|:-----|:-----|
| 1  | [Service](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6) voor het importeren van PST-bestanden en bestands ingestie | Raadpleeg de [import Service](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6) voor aanvullende vereisten. | Ongebruikelijk uitgaand scenario |
| 3  | [Microsoft ondersteuning en herstel ondersteuning voor Office 365](https://diagnostics.office.com/#/)  | https<span>://</span>Autodiscover.Outlook.com <BR> <span>https://</span>officecdn.Microsoft.com <BR> <span>https://</span>API.Diagnostics.Office.com <BR> <span>https://</span>apibasic.Diagnostics.Office.com <BR> <span>https://</span>Autodiscover-s.Outlook.com <BR> <span>https://</span>cloudcheckenabler.azurewebsites.net <BR> <span>https://</span>DCS-staging.Azure-API.net <BR> <span>https://</span>login.live.com <BR> <span>https://</span>login.microsoftonline.com <BR> <span>https://</span>login.Windows.net <BR> <span>https://</span>o365diagtelemetry.trafficmanager.net <BR> <span>https://</span>ODC.officeapps.live.com <BR> <span>https://</span>offcatedge.azureedge.net <BR> <span>https://</span>officeapps.live.com <BR> <span>https://</span>Outlook.office365.com <BR> <span>https://</span>outlookdiagnostics.azureedge.net | Verkeer uitgaande server |
| driefasig  | Azure AD Connect (met de optie eenmalige aanmelding) – WinRM & externe PowerShell | STS-omgeving klant (AD FS-server en AD FS-proxy) \| TCP-poorten 80 & 443 | Binnenkomende serververkeer |
| 3  | STS, zoals AD FS-proxy server (s) (alleen voor federatieve klanten) | Klant-STS (zoals AD FS-proxy) \| poorten tcp 443 of tcp 49443 w/met clienttls | Binnenkomende serververkeer |
| vijf  | [Exchange Online Unified Messaging/SBC-integratie](https://technet.microsoft.com/library/jj673565.aspx) | Bidirectionele tussen de on-premises sessie-rand controller en *. um.outlook.com | Alleen uitgaande serververkeer |
| zes  | Postvak migratie. Wanneer de migratie van postvakken wordt geïnitieerd vanuit on-premises [Exchange hybride](https://docs.microsoft.com/exchange/exchange-deployment-assistant) met Office 365, maakt Office 365 verbinding met uw gepubliceerde Exchange Web Services (EWS)/Mailbox Replication Services (Mevr)-server. Als u de NAT-IP-adressen die worden gebruikt door Exchange Online-servers, wilt beperken, worden deze weergegeven in de [URL van Office 365 & IP-bereiken](urls-and-ip-address-ranges.md) onder het servicegebied van Exchange Online. U dient ervoor te zorgen dat toegang tot gepubliceerde EWS-eindpunten, zoals OWA, geen invloed heeft op een afzonderlijke FQDN en een openbaar IP-adres voordat u TCP 443-verbindingen via specifieke IP-bereiken beperkt. | On-premises EWS/MEVR klant van klant<br> TCP-poort 443 | Binnenkomende serververkeer |
| 7,5  | [Hybride](https://docs.microsoft.com/exchange/exchange-deployment-assistant) , cocreatie functies van Exchange, zoals vrij/bezet delen. | On-premises Exchange-Server van klant | Binnenkomende serververkeer |
| 8:00  | [Hybride](https://docs.microsoft.com/exchange/exchange-deployment-assistant) verificatie van Exchange | On-premises STS klant | Binnenkomende serververkeer |
| aanhaling  | Voor het configureren van [Exchange Hybrid](https://docs.microsoft.com/exchange/exchange-deployment-assistant)met behulp van de [wizard hybride configuratie van Exchange](https://docs.microsoft.com/exchange/hybrid-configuration-wizard) <br> Opmerking: deze eindpunten zijn alleen vereist voor het configureren van Exchange hybride  | domains.live.com op TCP-poorten 80 & 443, alleen vereist voor de wizard Exchange 2010 SP3 voor hybride configuratie<BR> <BR> GCC High, DoD IP addresses: 40.118.209.192/32; 168.62.190.41/32 <BR> <BR> Wereldwijde Commercial & GCC: *. store.core.windows.net; asl.configure.office.com; mshrcstorageprod.blob.core.windows.net; tds.configure.office.com; mshybridservice.trafficmanager.net <BR>  | Alleen uitgaande serververkeer |
| 10  | De autodetectie-service wordt gebruikt in hybride scenario's van [Exchange](https://docs.microsoft.com/exchange/exchange-deployment-assistant) met [hybride moderne verificatie met Outlook voor IOS en Android](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth) <BR> <BR> ```*.acompli.net``` <BR> <BR> ```*.outlookmobile.com``` <BR> <BR> ```*.outlookmobile.us``` <BR> <BR> ```52.125.128.0/20``` <BR> ```52.127.96.0/23``` <BR> | On-premises Exchange-Server van klant op TCP 443 | Binnenkomende serververkeer |
| 23:00  | Exchange hybride Azure AD-verificatie | *. msappproxy.net | Alleen voor TCP-uitgaande servers |
| 12  | Skype voor bedrijven in Office 2016 bevat scherm delen op basis van video die UDP-poorten gebruiken. Eerdere Skype voor bedrijven-clients in Office 2013 en eerder gebruikte RDP via TCP-poort 443. | TCP-poort 443, geopend in 52.112.0.0/14 | Oudere versies van Skype voor bedrijven-clients in Office 2013 en eerder |
| dertien  | Hybride on-premises server verbinding van Skype voor bedrijven met Skype voor bedrijven online | 13.107.64.0/18, 52.112.0.0/14  <BR> UDP-poorten 50.000-59.999 <BR>  TCP-poorten 50.000-59.999; 5061 | Uitgaande verbinding met Skype voor bedrijven voor lokale servers |
| 14  | Voor Cloud PSTN met een lokale hybride verbinding moet de netwerkverbinding zijn geopend met de on-premises hosts. Meer informatie over hybride configuraties voor Skype voor bedrijven online  | Zie [hybride connectiviteit tussen Skype voor bedrijven server en Office 365 plannen](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-hybrid-connectivity) | Skype voor bedrijven on-premises hybride inkomende versie |
| 15  | **FQDN voor verificatie en identiteit** <br> De FQDN ```secure.aadcdn.microsoftonline-p.com``` moet zich in de zone Internet Explorer (IE) van de client of de zone Vertrouwde websites bevinden om te functioneren. |  | Vertrouwde sites |
| zestien  |  **FQDN-naam Microsoft teams** <br> Als u Internet Explorer of Microsoft Edge gebruikt, moet u de directe cookies van derden inschakelen en de FQDN voor teams toevoegen aan uw vertrouwde sites. Dit is een aanvulling op de FQDN, Cdn's en telemetrie die worden weergegeven in rij 14. Zie [bekende problemen voor Microsoft teams](https://docs.microsoft.com/microsoftteams/known-issues) voor meer informatie. |  | Vertrouwde sites |
| 19  |  **FQDN-naam van SharePoint Online en OneDrive voor bedrijven** <br> Alle '. sharepoint.com ' FQDN-naam '; ' \<tenant> ' in de FQDN-naam moet zich in de zone van de client van IE of Edge te vinden zijn. Naast de FQDN-naam, Cdn's en telemetrie die worden weergegeven in rij 14, moet u ook deze eindpunten toevoegen. |  | Vertrouwde sites |
| Mini  | **Yammer**  <br> Yammer is alleen beschikbaar in de browser en de geverifieerde gebruiker moet door een proxy worden doorgestuurd. Alle Yammer-FQDN-naam moet zich in de zone van de client van Internet Explorer of de site met vertrouwde websites bevinden om te functioneren. |  | Vertrouwde sites |
| 19  | Gebruik [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/) om on-premises gebruikersaccounts te synchroniseren met Azure AD. | Zie [hybride identiteit vereiste poorten en protocollen](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-ports), [problemen oplossen met de Azure AD-verbinding](https://docs.microsoft.com/azure/active-directory/hybrid/tshoot-connect-connectivity)en de [installatie van Azure AD Connect Health Agent](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-health-agent-install#outbound-connectivity-to-the-azure-service-endpoints). | Alleen uitgaande serververkeer |
| Maxi  | [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/) met 21 ViaNet in China om on-premises gebruikersaccounts te synchroniseren met Azure AD. | \*. digicert.com:80 <BR> \*. entrust.net:80 <BR> \*. chinacloudapi.cn:443 <BR> secure.aadcdn.partner.microsoftonline-p.cn:443 <BR>*. partner.microsoftonline.cn:443 <BR> <BR>Zie ook [problemen met de Azure AD-verbinding oplossen](https://docs.azure.cn/zh-cn/active-directory/hybrid/tshoot-connect-connectivity). | Alleen uitgaande serververkeer |
| 22  | Microsoft stream (nodig de Azure AD-gebruikerstoken). <BR> Office 365 wereldwijd (inclusief GCC) | \*. cloudapp.net <BR> \*. api.microsoftstream.com <BR> \*. notification.api.microsoftstream.com <BR> amp.azure.net <BR> api.microsoftstream.com <BR> az416426.vo.msecnd.net <BR> s0.assets-yammer.com <BR> vortex.data.microsoft.com <BR> web.microsoftstream.com <BR> TCP-poort 443  | Binnenkomende serververkeer |
| centimeter  | Gebruik MFA server voor verificatieaanvragen van meervoudige authenticatie, zowel nieuwe installaties van de server als het instellen van Active Directory Domain Services (AD DS). | Zie [aan de slag met de Azure multi-factor Authentication-Server](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-deploy#plan-your-deployment).  | Alleen uitgaande serververkeer |
| 19  | Meldingen van Microsoft Graph wijzigen | Ontwikkelaars kunnen [meldingen wijzigen](https://docs.microsoft.com/graph/webhooks?context=graph%2Fapi%2F1.0&view=graph-rest-1.0) om een abonnement te nemen in Microsoft Graph. | *. cloudapp.net<BR> 104.43.130.21, 137.116.169.230, 13.79.38.63, 104.214.39.228, openbare Cloud: 168.63.250.205, 52.161.9.202, 40.68.103.62, 13.89.60.223, 23.100.95.104, 40.113.95.219, 104.214.32.10, 168.63.237.145, 52.161.110.176, 52.174.177.183, 13.85.192.59, 13.85.192.123, 13.86.37.15, 13.89.108.233, 13.89.104.147, 20.44.210.83, 20.44.210.146, 40.76.162.99, 40.76.162.42, 40.74.203.28, 40.74.203.27, 51.104.159.213, 51.104.159.181, 51.124.75.43, 51.124.73.177, 51.138.90.7, 51.138.90.52, 52.139.153.222, 52.139.170.157, 52.139.170.47, 52.142.114.29, 52.142.115.31, 52.147.213.251, 52.147.213.181, 52.148.24.136, 52.148.27.39, 52.148.115.48, 52.148.114.238, 52.154.246.238, 52.159.23.209, 52.159.17.84, 52.184.94.140 <BR> Microsoft Cloud voor US Government: 52.244.231.173, 52.238.76.151, 52.244.250.211, 52.238.78.108, 52.243.147.249, 52.243.148.19, 52.243.157.104, 52.243.157.105, 52.244.33.45, 52.244.35.174, 52.244.111.156, 52.244.111.170 <BR> Microsoft Cloud Duitsland: 51.4.231.136, 51.5.243.223, 51.4.226.154, 51.5.244.215, 51.4.150.206, 51.4.150.235, 51.5.147.130, 51.5.148.103 <BR> Microsoft Cloud China beheerd door 21Vianet: 139.219.15.33, 42.159.154.223, 42.159.88.79, 42.159.155.77, 40.72.155.199, 40.72.155.216, 40.125.138.23, 40.125.136.69, 42.159.72.35, 42.159.72.47, 42.159.180.55, 42.159.180.56<BR> TCP-poort 443 <BR> Opmerking: ontwikkelaars kunnen verschillende poorten opgeven wanneer ze een abonnement maken.  | Binnenkomende serververkeer |
|||||

## <a name="related-topics"></a>Verwante onderwerpen

[Office 365-eindpunten beheren](managing-office-365-endpoints.md)
  
[Verbindingsproblemen met Office 365 oplossen](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d.aspx)
  
[Clientconnectiviteit](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[Netwerken voor contentlevering](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[IP-bereiken van Microsoft Azure Datacenter](https://www.microsoft.com/download/details.aspx?id=41653)
  
[Microsoft Public IP Space](https://www.microsoft.com/download/details.aspx?id=53602)
