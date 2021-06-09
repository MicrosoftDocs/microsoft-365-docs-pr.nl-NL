---
title: Extra eindpunten die niet zijn opgenomen in de Office 365 IP-adres- en URL-webservice
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/19/2021
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
ms.openlocfilehash: 6c545b6060b44ebe234baaebd3ae1eb2fdb0fb89
ms.sourcegitcommit: 76f3c75413cc960289489d0ca29efadb8a9a5b31
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "51887207"
---
# <a name="additional-endpoints-not-included-in-the-office-365-ip-address-and-url-web-service"></a>Extra eindpunten die niet zijn opgenomen in de Office 365 IP-adres- en URL-webservice

Sommige netwerk-eindpunten zijn eerder gepubliceerd en zijn niet opgenomen in de Office 365 [IP-adres en URL-webservice.](microsoft-365-ip-web-service.md) Het webservicebereik is netwerk-eindpunten die vereist zijn voor connectiviteit van een gebruiker van Office 365 een bedrijfsperimeternetwerk. Dit geldt momenteel niet voor:

1. Netwerkconnectiviteit die mogelijk vereist is vanuit een Microsoft-datacenter naar een klantnetwerk (binnenkomende hybride servernetwerkverkeer).
2. Netwerkconnectiviteit van servers op een klantnetwerk in de bedrijfsperimeter (uitgaande servernetwerkverkeer).
3. Ongebruikelijke scenario's voor netwerkconnectiviteitsvereisten van een gebruiker.
4. VEREISTE VOOR DNS-resolutieconnectiviteit (niet hieronder vermeld).
5. Internet Explorer of Microsoft Edge vertrouwde sites.

Afgezien van DNS zijn deze allemaal optioneel voor de meeste klanten, tenzij u het specifieke scenario nodig hebt dat wordt beschreven.

| Rij | Doel | Destination | Type |
|:-----|:-----|:-----|:-----|
| 1  | [Service importeren](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6) voor PST en bestandsingestie | Raadpleeg de [Importservice voor](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6) aanvullende vereisten. | Ongebruikelijk uitgaande scenario |
| 2  | [Microsoft Ondersteunings- en herstelassistent voor Office 365](https://diagnostics.office.com/#/)  | https<span>://</span>autodiscover.outlook.com <BR> <span>https://</span>officecdn.microsoft.com <BR> <span>https://</span>api.diagnostics.office.com <BR> <span>https://</span>apibasic.diagnostics.office.com <BR> <span>https://</span>autodiscover-s.outlook.com <BR> <span>https://</span>cloudcheckenabler.azurewebsites.net <BR> <span>https://</span>login.live.com <BR> <span>https://</span>login.microsoftonline.com <BR> <span>https://</span>login.windows.net <BR> <span>https://</span>o365diagtelemetry.trafficmanager.net <BR> <span>https://</span>odc.officeapps.live.com <BR> <span>https://</span>offcatedge.azureedge.net <BR> <span>https://</span>officeapps.live.com <BR> <span>https://</span>outlook.office365.com <BR> <span>https://</span>outlookdiagnostics.azureedge.net | Uitgaande serververkeer |
| 3  | Azure AD Verbinding maken (optie w/SSO) – WinRM & externe PowerShell | Klant STS-omgeving (AD FS Server en AD FS Proxy) \| TCP-poorten 80 & 443 | Binnenkomende serververkeer |
| 4  | STS, zoals AD FS Proxy server(s) (alleen voor federatief ge federatiefe klanten) | Klant-STS-poorten (zoals AD FS-proxy) \| TCP 443 of TCP 49443 w/ClientTLS | Binnenkomende serververkeer |
| 5  | [Exchange Online Unified Messaging/SBC-integratie](/exchange/voice-mail-unified-messaging/telephone-system-integration-with-um/configuration-notes-for-session-border-controllers) | Bidirectioneel tussen on-premises Session Border Controller en *.um.outlook.com | Alleen uitgaande serververkeer |
| 6  | Postvakmigratie. Wanneer de migratie van postvakken wordt gestart van on-premises [Exchange Hybrid](/exchange/exchange-deployment-assistant) naar Office 365, maken Office 365 verbinding met uw gepubliceerde Exchange Web Services (EWS)/Mailbox Replication Services (MRS)-server. Als u de NAT-IP-adressen nodig hebt die door Exchange Online-servers worden gebruikt om binnenkomende verbindingen uit specifieke bron-IP-bereik te beperken, worden deze weergegeven in [Office 365 URL & IP-bereik](urls-and-ip-address-ranges.md) onder het servicegebied 'Exchange Online'. Zorg ervoor dat de toegang tot gepubliceerde EWS-eindpunten zoals OWA niet wordt beïnvloed door ervoor te zorgen dat de MRS-proxy wordt opgelost naar een afzonderlijk FQDN- en openbaar IP-adres voordat TCP 443-verbindingen worden beperkt vanuit specifieke bron-IP-bereiken. | Klant on-premises EWS/MRS Proxy<br> TCP-poort 443 | Binnenkomende serververkeer |
| 7  | [Exchange hybride](/exchange/exchange-deployment-assistant) co-existence functies, zoals Delen met vrije/bezet. | On-premises klant Exchange server | Binnenkomende serververkeer |
| 8  | [Exchange hybride proxyverificatie](/exchange/exchange-deployment-assistant) | Klant on-premises STS | Binnenkomende serververkeer |
| 9  | Gebruikt voor het [configureren Exchange hybride](/exchange/exchange-deployment-assistant), met de [wizard Exchange hybride configuratie](/exchange/hybrid-configuration-wizard) <br> Opmerking: Deze eindpunten zijn alleen vereist om de Exchange configureren  | domains.live.com op TCP-poorten 80 & 443, alleen vereist voor Exchange 2010 SP3 Hybrid Configuration Wizard<BR> <BR> GCC Hoog, DOD IP-adressen: 40.118.209.192/32; 168.62.190.41/32 <BR> <BR> Wereldwijde commerciële & GCC: *.store.core.windows.net; asl.configure.office.com; tds.configure.office.com; mshybridservice.trafficmanager.net ; <BR> aka.ms/hybridwizard; <BR> shcwreleaseprod.blob.core.windows.net/shcw/ \* ;<BR>  | Alleen uitgaande serververkeer |
| 10  | De AutoDetect-service wordt gebruikt in [Exchange hybride](/exchange/exchange-deployment-assistant) scenario's met hybride moderne verificatie met Outlook [voor iOS en Android](/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth) <BR> <BR> ```*.acompli.net``` <BR> <BR> ```*.outlookmobile.com``` <BR> <BR> ```*.outlookmobile.us``` <BR> <BR> ```52.125.128.0/20``` <BR> ```52.127.96.0/23``` <BR> | On-premises klantserver Exchange TCP 443 | Binnenkomende serververkeer |
| 11  | Exchange hybride Azure AD-verificatie | *.msappproxy.net | Alleen verkeer voor uitgaande TCP-server |
| 12  | Skype voor Bedrijven in Office 2016 bevat scherm delen op basis van video waarin UDP-poorten worden gebruikt. Vorige Skype voor Bedrijven clients in Office 2013 en eerder RDP gebruikt via TCP-poort 443. | TCP-poort 443 geopend naar 52.112.0.0/14 | Skype voor Bedrijven oudere clientversies in Office 2013 en eerder |
| 13  | Skype voor Bedrijven hybride on-premises serverconnectiviteit met Skype voor Bedrijven Online | 13.107.64.0/18, 52.112.0.0/14  <BR> UDP-poorten 50.000-59.999 <BR>  TCP-poorten 50.000-59.999; 5061 | Skype voor Bedrijven on-premises server uitgaande connectiviteit |
| 14  | Voor PSTN in de cloud met on-premises hybride connectiviteit is netwerkconnectiviteit vereist die toegankelijk is voor de on-premises hosts. Voor meer informatie over Skype voor Bedrijven Online hybride configuraties  | Zie [Hybride connectiviteit plannen tussen Skype voor Bedrijven Server en Office 365](/skypeforbusiness/hybrid/plan-hybrid-connectivity) | Skype voor Bedrijven on-premises hybride inkomende |
| 15  | **FQDN's voor verificatie en identiteit** <br> De FQDN moet zich in de ```secure.aadcdn.microsoftonline-p.com``` Internet Explorer -zone (IE) of edge trusted sites zone van uw client bevindt om te kunnen functioneren. |  | Vertrouwde sites |
| 16  |  **Microsoft Teams FQDN's** <br> Als u Internet Explorer of Microsoft Edge gebruikt, moet u eerst cookies van derden inschakelen en de FQDN's voor Teams toevoegen aan uw vertrouwde sites. Dit komt bovenop de FQDN's, CDN's en telemetrie voor de hele suite die in rij 14 worden vermeld. Zie [Bekende problemen voor Microsoft Teams](/microsoftteams/known-issues) voor meer informatie. |  | Vertrouwde sites |
| 17  |  **SharePoint Online en OneDrive voor Bedrijven FQDN's** <br> Alle '.sharepoint.com' FQDN's met ' ' in de FQDN moeten zich in de IE- of Edge Trusted Sites-zone van uw client bevindt om \<tenant> te kunnen functioneren. Naast de FQDN's, CDN's en telemetrie die in rij 14 worden vermeld, moet u deze eindpunten ook toevoegen. |  | Vertrouwde sites |
| 18  | **Yammer**  <br> Yammer is alleen beschikbaar in de browser en vereist dat de geverifieerde gebruiker wordt doorgegeven via een proxy. Alle Yammer FQDN's moeten zich in de IE- of Edge Trusted Sites-zone van uw client bevindt om te kunnen functioneren. |  | Vertrouwde sites |
| 19  | Gebruik [Azure AD-Verbinding maken](/azure/active-directory/hybrid/) om on-premises gebruikersaccounts te synchroniseren met Azure AD. | Zie [Hybrid Identity Required Ports and Protocols](/azure/active-directory/hybrid/reference-connect-ports), [Troubleshoot Azure AD connectivity](/azure/active-directory/hybrid/tshoot-connect-connectivity), and Azure AD Verbinding maken Health Agent [Installation](/azure/active-directory/hybrid/how-to-connect-health-agent-install#outbound-connectivity-to-the-azure-service-endpoints). | Alleen uitgaande serververkeer |
| 20  | [Azure AD Verbinding maken](/azure/active-directory/hybrid/) met 21 ViaNet in China om on-premises gebruikersaccounts te synchroniseren met Azure AD. | \*.digicert.com:80 <BR> \*.entrust.net:80 <BR> \*.chinacloudapi.cn:443 <BR> secure.aadcdn.partner.microsoftonline-p.cn:443 <BR>*.partner.microsoftonline.cn:443 <BR> <BR>Zie Ook [Problemen met de Ingressie van Azure AD-connectiviteit oplossen.](https://docs.azure.cn/zh-cn/active-directory/hybrid/tshoot-connect-connectivity) | Alleen uitgaande serververkeer |
| 21  | Microsoft Stream (heeft het Azure AD-gebruikersken nodig). <BR> Office 365 Wereldwijd (inclusief GCC) | \*.cloudapp.net <BR> \*.api.microsoftstream.com <BR> \*.notification.api.microsoftstream.com <BR> amp.azure.net <BR> api.microsoftstream.com <BR> az416426.vo.msecnd.net <BR> s0.assets-yammer.com <BR> vortex.data.microsoft.com <BR> web.microsoftstream.com <BR> TCP-poort 443  | Binnenkomende serververkeer |
| 22  | Gebruik MFA-server voor meervoudige verificatieaanvragen, zowel nieuwe installaties van de server als het instellen met Active Directory Domain Services (AD DS). | Zie [Aan de slag met de Azure AD Multi-Factor Authentication Server](/azure/active-directory/authentication/howto-mfaserver-deploy#plan-your-deployment).  | Alleen uitgaande serververkeer |
| 23  | Microsoft Graph Meldingen wijzigen | Ontwikkelaars kunnen gebruikmaken [van wijzigingsmeldingen om](/graph/webhooks?context=graph%2fapi%2f1.0&view=graph-rest-1.0) zich te abonneren op gebeurtenissen in de Microsoft-Graph. | *.cloudapp.net<BR> 104.43.130.21, 137.116.169.230, 13.79.38.63, 104.214.39.228, Public Cloud: 168.63.250.205, 52.161.9.202, 40.68.103.62, 13.89.60.223, 23.100.95.104, 40.113.95.219, 104.214.32.10, 168.63.237.145, 52.161.110.176, 52.174.177.183, 13.85.192.59, 13.85.192.123, 13.86.37.15, 13.89.108.233, 13.89.104.147, 20.44.210.83, 20.44.210.146, 40.76.162.99, 40.76.162.42, 40.74.203.28, 40.74.203.27, 51.104.159.213, 51.104.159.181, 51.124.75.43, 51.124.73.177, 51.138.90.7, 51.138.90.52, 52.139.153.222, 52.139.170.157, 52.139.170.47, 52.142.114.29, 52.142.115.31, 52.147.213.251, 52.147.213.181, 52.148.24.136, 52.148.27.39, 52.148.115.48, 52.148.114.238, 52.154.246.238, 52.159.23.209, 52.159.17.84, 52.184.94.140 <BR> Microsoft Cloud for US Government: 52.244.231.173, 52.238.76.151, 52.244.250.211, 52.238.78.108, 52.243.147.249, 52.243.148.19, 52.243.157.104, 52.243.157.105, 52.244.33.45, 52.244.35.174, 52.244.111.156, 52.244.111.170 <BR> Microsoft Cloud Germany: 51.4.231.136, 51.5.243.223, 51.4.226.154, 51.5.244.215, 51.4.150.206, 51.4.150.235, 51.5.147.130, 51.5.148.103 <BR> Microsoft Cloud China beheerd door 21Vianet: 139.219.15.33, 42.159.154.223, 42.159.88.79, 42.159.155.77, 40.72.155.199, 40.72.155.216, 40.125.138.23, 40.125.136.69, 42.159.72.35, 42.159.72.47, 42.159.180.55, 42.159.180.56<BR> TCP-poort 443 <BR> Opmerking: Ontwikkelaars kunnen verschillende poorten opgeven bij het maken van de abonnementen.  | Binnenkomende serververkeer |
|||||

## <a name="related-topics"></a>Verwante onderwerpen

[Office 365-eindpunten beheren](managing-office-365-endpoints.md)
  
[Microsoft 365-connectiviteit controleren](./monitor-connectivity.md)
  
[Clientconnectiviteit](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[Netwerken voor contentlevering](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[Azure IP-bereik en servicelabels : openbare cloud](https://www.microsoft.com/download/details.aspx?id=56519)

[Azure IP-bereik en servicelabels – Us Government Cloud](https://www.microsoft.com/download/details.aspx?id=57063)

[Azure IP-bereik en servicelabels – Germany Cloud](https://www.microsoft.com/download/details.aspx?id=57064)

[Azure IP-bereik en servicelabels – China Cloud](https://www.microsoft.com/download/details.aspx?id=57062)
  
[Microsoft Public IP Space](https://www.microsoft.com/download/details.aspx?id=53602)