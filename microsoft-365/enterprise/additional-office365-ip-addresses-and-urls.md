---
title: Extra eindpunten die niet zijn opgenomen in de Webservice voor IP-adressen en URL's van Office 365
ms.author: kvice
author: kelleyvice-msft
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
description: "Overzicht: De nieuwe eindpuntwebservice bevat geen klein aantal eindpunten voor specifieke scenario's."
hideEdit: true
ms.openlocfilehash: 7922730957be93b2cdfbd06a48d39fc54ac4af89
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711974"
---
# <a name="additional-endpoints-not-included-in-the-office-365-ip-address-and-url-web-service"></a>Extra eindpunten die niet zijn opgenomen in de Webservice voor IP-adressen en URL's van Office 365

Sommige netwerk-eindpunten zijn eerder gepubliceerd en zijn niet opgenomen in de [Ip-adres- en URL-webservice van Office 365.](microsoft-365-ip-web-service.md) Het webservicebereik bestaat uit netwerk-eindpunten die zijn vereist voor verbinding tussen een gebruiker van Office 365 en een perimeternetwerk voor ondernemingen. Dit omvat momenteel niet:

1. Netwerkconnectiviteit die mogelijk is vereist van een Microsoft-datacenter naar een klantnetwerk (netwerkverkeer voor binnenkomende hybride server).
2. Netwerkconnectiviteit van servers op een klantnetwerk binnen de ondernemingsperimeter (uitgaand servernetwerkverkeer).
3. Ongebruikelijke scenario's van de vereisten voor netwerkconnectiviteit van een gebruiker.
4. Vereiste voor DNS-resolutieconnectiviteit (hieronder niet vermeld).
5. Vertrouwde websites van Internet Explorer of Microsoft Edge.

Afgezien van de DNS zijn deze allemaal optioneel voor de meeste klanten, tenzij u het specifieke scenario nodig hebt dat wordt beschreven.

| Rij | Doel | Destination | Type |
|:-----|:-----|:-----|:-----|
| 1  | [Service importeren](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6) voor PST en bestandsingestie | Raadpleeg de [importservice voor](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6) aanvullende vereisten. | Niet vaak uitgaande scenario |
| 2  | [Microsoft Ondersteunings- en herstelassistent voor Office 365](https://diagnostics.office.com/#/)  | https<span>://</span>autodiscover.outlook.com <BR> <span>https://</span>officecdn.microsoft.com <BR> <span>https://</span>api.diagnostics.office.com <BR> <span>https://</span>apibasic.diagnostics.office.com <BR> <span>https://</span>autodiscover-s.outlook.com <BR> <span>https://</span>cloudcheckenabler.azurewebsites.net <BR> <span>https://</span>dcs-staging.azure-api.net <BR> <span>https://</span>login.live.com <BR> <span>https://</span>login.microsoftonline.com <BR> <span>https://</span>login.windows.net <BR> <span>https://</span>o365diagtelemetry.trafficmanager.net <BR> <span>https://</span>odc.officeapps.live.com <BR> <span>https://</span>offcatedge.azureedge.net <BR> <span>https://</span>officeapps.live.com <BR> <span>https://</span>outlook.office365.com <BR> <span>https://</span>outlookdiagnostics.azureedge.net | Uitgaand serververkeer |
| 3  | Azure AD Connect (optie w/SSO) – WinRM & externe PowerShell | TCP-poorten 80 & 443 klant-STS-omgeving (AD FS-server en AD \| FS-proxy) | Binnenkomende serververkeer |
| 4  | STS, zoals AD FS-proxyservers (alleen voor federatief klanten) | STS-poorten voor klanten (zoals AD FS-proxy) \| TCP 443 of TCP 49443 met ClientTLS | Binnenkomende serververkeer |
| 5  | [Integratie van Exchange Online Unified Messaging/SBC](https://technet.microsoft.com/library/jj673565.aspx) | Bidirectioneel tussen on-premises session border controller en *.um.outlook.com | Alleen verkeer voor uitgaande server |
| 6  | Migratie van postvakken. Wanneer de migratie van postvakken wordt gestart van on-premises [Exchange Hybrid](https://docs.microsoft.com/exchange/exchange-deployment-assistant) naar Office 365, maakt Office 365 verbinding met uw gepubliceerde Exchange Web Services (EWS)/Mailbox Replication Services (MRS)-server. Als u de NAT-IP-adressen wilt gebruiken die door Exchange Online-servers worden gebruikt om binnenkomende verbindingen van specifieke bron-IP-bereiken te beperken, worden deze vermeld in DE [URL van Office 365 &-IP-bereik](urls-and-ip-address-ranges.md) onder het servicegebied Exchange Online. Zorg ervoor dat de toegang tot gepubliceerde EWS-eindpunten, zoals OWA, niet wordt beïnvloed door ervoor te zorgen dat de MRS-proxy wordt omgeslagen in een afzonderlijk FQDN- en openbaar IP-adres voordat TCP 443-verbindingen van specifieke bron-IP-bereiken worden beperkt. | On-premises EWS/MRS-proxy klant<br> TCP-poort 443 | Binnenkomende serververkeer |
| 7  | [Exchange Hybrid-functies](https://docs.microsoft.com/exchange/exchange-deployment-assistant) voor naast elkaar bestaan, zoals het delen van bezet/vrij/bezet. | On-premises Exchange-server klant | Binnenkomende serververkeer |
| 8  | [Hybride Exchange-proxyverificatie](https://docs.microsoft.com/exchange/exchange-deployment-assistant) | On-premises STS klant | Binnenkomende serververkeer |
| 9  | Wordt gebruikt voor het [configureren van Exchange Hybrid](https://docs.microsoft.com/exchange/exchange-deployment-assistant)met behulp van de [wizard Hybride configuratie van Exchange](https://docs.microsoft.com/exchange/hybrid-configuration-wizard) <br> Opmerking: Deze eindpunten zijn alleen vereist voor het configureren van een hybride versie van Exchange  | domains.live.com op TCP-poorten 80 & 443, alleen vereist voor wizard Hybride configuratie van Exchange 2010 SP3<BR> <BR> GCC High, DOD IP addresses: 40.118.209.192/32; 168.62.190.41/32 <BR> <BR> Worldwide Commercial & GCC: *.store.core.windows.net; asl.configure.office.com; tds.configure.office.com; mshybridservice.trafficmanager.net ; <BR> aka.ms/hybridwizard; <BR> shcwreleaseprod.blob.core.windows.net/shcw/ \* ;<BR>  | Alleen verkeer voor uitgaande server |
| 10  | De AutoDetect-service wordt gebruikt in hybride Exchange-scenario's met [hybride moderne verificatie met Outlook voor iOS en Android](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth) [](https://docs.microsoft.com/exchange/exchange-deployment-assistant) <BR> <BR> ```*.acompli.net``` <BR> <BR> ```*.outlookmobile.com``` <BR> <BR> ```*.outlookmobile.us``` <BR> <BR> ```52.125.128.0/20``` <BR> ```52.127.96.0/23``` <BR> | On-premises Exchange-server klant op TCP 443 | Binnenkomende serververkeer |
| 11  | Hybride Azure AD-verificatie voor Exchange | *.msappproxy.net | Alleen verkeer voor uitgaande TCP-server |
| 12  | Skype voor Bedrijven in Office 2016 bevat scherm delen op basis van video, waarbij UDP-poorten worden gebruikt. Vorige Skype voor Bedrijven-clients in Office 2013 en eerder gebruikten RDP via TCP-poort 443. | TCP-poort 443 geopend tot 52.112.0.0/14 | Oudere clientversies van Skype voor Bedrijven in Office 2013 en eerder |
| 13  | Hybride Skype voor Bedrijven-serverconnectiviteit met Skype voor Bedrijven Online | 13.107.64.0/18, 52.112.0.0/14  <BR> UDP-poorten 50.000-59.999 <BR>  TCP-poorten 50.000-59.999; 5061 | Uitgaande verbindingen voor de on-premises Server van Skype voor Bedrijven |
| 14  | Voor PSTN voor de cloud met on-premises hybride connectiviteit is een open netwerkverbinding met de on-premises hosts vereist. Voor meer informatie over hybride configuraties voor Skype voor Bedrijven Online  | Zie [Hybride connectiviteit plannen tussen Skype voor Bedrijven Server en Office 365](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-hybrid-connectivity) | Inkomende on-premises hybride versie van Skype voor Bedrijven |
| 15  | **FQDN's voor verificatie en identiteit** <br> De FQDN moet zich in de zone Met Internet Explorer (IE) of vertrouwde websites in Edge van uw ```secure.aadcdn.microsoftonline-p.com``` client bevindt om te kunnen functioneren. |  | Vertrouwde websites |
| 16  |  **FQDN's voor Microsoft Teams** <br> Als u Internet Explorer of Microsoft Edge gebruikt, moet u eerst en externe cookies inschakelen en de FQDN's voor Teams toevoegen aan uw vertrouwde websites. Dit is een aanvulling op de FQDN's, CDN's en telemetrie voor de hele suite die worden vermeld in rij 14. Zie [Bekende problemen voor Microsoft Teams](https://docs.microsoft.com/microsoftteams/known-issues) voor meer informatie. |  | Vertrouwde websites |
| 17  |  **FQDN's voor SharePoint Online en OneDrive voor Bedrijven** <br> Alle '.sharepoint.com'-FQDN's met ' in de FQDN moeten zich in de zone Vertrouwde websites op internet of in de zone Vertrouwde websites van Edge van uw client bevindt om \<tenant> te kunnen functioneren. Naast de FQDN's, CDN's en telemetrie voor de hele suite die worden vermeld in rij 14, moet u ook deze eindpunten toevoegen. |  | Vertrouwde websites |
| 18  | **Yammer**  <br> Yammer is alleen beschikbaar in de browser en vereist dat de geverifieerde gebruiker via een proxy wordt doorgegeven. Alle FQDN's voor Yammer moeten zich in de zone Vertrouwde websites van InternetZone of Edge van uw client bevindt om te kunnen functioneren. |  | Vertrouwde websites |
| 19  | Gebruik [Azure AD Connect om](https://docs.microsoft.com/azure/active-directory/hybrid/) on-premises gebruikersaccounts te synchroniseren met Azure AD. | Zie Vereiste poorten en protocollen [voor hybride identiteit,](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-ports)problemen [met Azure AD-connectiviteit oplossen](https://docs.microsoft.com/azure/active-directory/hybrid/tshoot-connect-connectivity)en installatie van azure AD [Connect-statusagenten.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-health-agent-install#outbound-connectivity-to-the-azure-service-endpoints) | Alleen verkeer voor uitgaande server |
| 20  | [Azure AD Connect met](https://docs.microsoft.com/azure/active-directory/hybrid/) 21 ViaNet in China om on-premises gebruikersaccounts te synchroniseren met Azure AD. | \*.digicert.com:80 <BR> \*.entrust.net:80 <BR> \*.chinacloudapi.cn:443 <BR> secure.aadcdn.partner.microsoftonline-p.cn:443 <BR>*.partner.microsoftonline.cn:443 <BR> <BR>Zie ook [Ingressie oplossen met verbindingsproblemen met Azure AD.](https://docs.azure.cn/zh-cn/active-directory/hybrid/tshoot-connect-connectivity) | Alleen verkeer voor uitgaande server |
| 21  | Microsoft Stream (heeft het azure AD-gebruikers token nodig). <BR> Office 365 Worldwide (inclusief GCC) | \*.cloudapp.net <BR> \*.api.microsoftstream.com <BR> \*.notification.api.microsoftstream.com <BR> amp.azure.net <BR> api.microsoftstream.com <BR> az416426.vo.msecnd.net <BR> s0.assets-yammer.com <BR> vortex.data.microsoft.com <BR> web.microsoftstream.com <BR> TCP-poort 443  | Binnenkomende serververkeer |
| 22  | Gebruik de MFA-server voor meervoudige verificatieaanvragen, zowel nieuwe installaties van de server als voor het instellen ervan met Active Directory Domain Services (AD DS). | Zie [Aan de slag met de Azure AD Multi-Factor Authentication Server.](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-deploy#plan-your-deployment)  | Alleen verkeer voor uitgaande server |
| 23  | Microsoft Graph- wijzigingsmeldingen | Ontwikkelaars kunnen [wijzigingsmeldingen gebruiken om](https://docs.microsoft.com/graph/webhooks?context=graph%2Fapi%2F1.0&view=graph-rest-1.0) zich te abonneren op gebeurtenissen in Microsoft Graph. | *.cloudapp.net<BR> 104.43.130.21, 137.116.169.230, 13.79.38.63, 104.214.39.228, Public Cloud: 168.63.250.205, 52.161.9.202, 40.68.103.62, 13.89.60.223, 23.100.95.104, 40.113.95.219, 104.214.32.10, 168.63.237.145, 52.161.110.176, 52.174.177.183, 13.85.192.59, 13.85.192.123, 13.86.37.15, 13.89.108.233, 13.89.104.147, 20.44.210.83, 20.44.210.146, 40.76.162.99, 40.76.162.42, 40.74.203.28, 40.74.203.27, 51.104.159.213, 51.104.159.181, 51.124.75.43, 51.124.73.177, 51.138.90.7, 51.138.90.52, 52.139.153.222, 52.139.170.157, 52.139.170.47, 52.142.114.29, 52.142.115.31, 52.147.213.251, 52.147.213.181, 52.148.24.136, 52.148.27.39, 52.148.115.48, 52.148.114.238, 52.154.246.238, 52.159.23.209, 52.159.17.84, 52.184.94.140 <BR> Microsoft Cloud voor amerikaanse overheid: 52.244.231.173, 52.238.76.151, 52.244.250.211, 52.238.78.108, 52.243.147.249, 52.243.148.19, 52.243.157.104, 52.243.157.105, 52.244.33.45, 52.244.35.174, 52.244.111.156, 52.244.111.170 <BR> Microsoft Cloud Germany: 51.4.231.136, 51.5.243.223, 51.4.226.154, 51.5.244.215, 51.4.150.206, 51.4.150.235, 51.5.147.130, 51.5.148.103 <BR> Microsoft Cloud China beheerd door 21Vianet: 139.219.15.33, 42.159.154.223, 42.159.88.79, 42.159.155.77, 40.72.155.199, 40.72.155.216, 40.125.138.23, 40.125.136.69, 42.159.72.35, 42.159.72.47, 42.159.180.55, 42.159.180.56<BR> TCP-poort 443 <BR> Opmerking: Ontwikkelaars kunnen verschillende poorten opgeven bij het maken van abonnementen.  | Binnenkomende serververkeer |
|||||

## <a name="related-topics"></a>Verwante onderwerpen

[Office 365-eindpunten beheren](managing-office-365-endpoints.md)
  
[Microsoft 365-connectiviteit controleren](https://docs.microsoft.com/microsoft-365/enterprise/monitor-connectivity?view=o365-worldwide)
  
[Clientconnectiviteit](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[Netwerken voor contentlevering](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[IP-adresbereiken en servicelabels voor Azure – Openbare cloud](https://www.microsoft.com/download/details.aspx?id=56519)

[Azure IP Ranges and Service Tags ( US Government Cloud)](https://www.microsoft.com/download/details.aspx?id=57063)

[Ip-adresbereiken en servicelabels voor Azure ( Duitsland Cloud)](https://www.microsoft.com/download/details.aspx?id=57064)

[Ip-adresseringen en servicelabels voor Azure - China Cloud](https://www.microsoft.com/download/details.aspx?id=57062)
  
[Microsoft Public IP Space](https://www.microsoft.com/download/details.aspx?id=53602)
