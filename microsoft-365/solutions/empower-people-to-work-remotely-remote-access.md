---
title: Stap 2. Externe toegang bieden tot on-premises apps en services
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom:
- M365solutions
description: Zorg ervoor dat uw externe medewerkers toegang hebben tot on-premises informatiebronnen terwijl de toegang tot Microsoft 365-cloudservices wordt geoptimaliseerd.
ms.openlocfilehash: fb91451b52c55f2cad1e0efefe19a044ce1cc37b
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/01/2020
ms.locfileid: "44002646"
---
# <a name="step-2-provide-remote-access-to-on-premises-apps-and-services"></a>Stap 2. Externe toegang bieden tot on-premises apps en services

Als uw organisatie een VPN-oplossing voor externe toegang gebruikt, meestal met VPN-servers aan de rand van uw netwerk en VPN-clients geïnstalleerd op de apparaten van uw gebruikers, kunnen uw gebruikers VPN-verbindingen voor externe toegang gebruiken voor toegang tot on-premises apps en servers. Het kan zijn dat u het verkeer naar de Microsoft 365-cloudservices moet optimaliseren.

Als uw gebruikers geen VPN-oplossing gebruiken, kunt u Azure AD-toepassingsproxy (Active Directory) en Azure P2S-VPN (Point-to-Site) gebruiken om toegang te bieden, afhankelijk van het feit of al uw apps webversies zijn.

Er zijn drie primaire configuraties:

1. U gebruikt al een VPN-oplossing voor externe toegang.
2. U gebruikt geen VPN-oplossing voor externe toegang, u hebt een hybride identiteit en u hebt alleen externe toegang nodig tot on-premises web-apps.
3. U gebruikt geen VPN-oplossing voor externe toegang en u hebt toegang nodig tot on-premises apps, waarvan sommige niet op internet zijn gebaseerd.

Met externe toegangsverbindingen kunt u ook [Extern bureaublad](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) gebruiken om uw gebruikers verbinding te laten maken met een on-premises pc. Een externe medewerker kan bijvoorbeeld Extern bureaublad gebruiken om verbinding te maken met de pc op zijn kantoor vanuit zijn Windows-, iOS- of Android-apparaat. Zodra hij extern verbinding heeft gemaakt, kan hij deze gebruiken alsof hij erachter zit.

## <a name="optimize-performance-for-remote-access-vpn-clients-to-microsoft-365-cloud-services"></a>Prestaties optimaliseren voor VPN-clients voor externe toegang tot Microsoft 365-cloudservices

Als uw externe medewerkers een traditionele VPN-client gebruiken om extern toegang te krijgen tot uw bedrijfsnetwerk, verifieer dan dat de VPN-client split tunneling ondersteunt.

Zonder split tunneling wordt al uw externe werk verzonden via de VPN-verbinding, terwijl het moet worden doorgestuurd naar de edge-apparaten van uw bedrijf, worden verwerkt en dan verzonden op internet.

![Netwerkverkeer van VPN-clients zonder tunneling](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

Microsoft 365-verkeer moet een indirecte route gebruiken binnen uw organisatie dat dan kan worden doorgestuurd naar een Microsoft-netwerkingangspunt ver verwijderd van de fysieke locatie van de VPN-client. Met dit indirecte pad wordt een vertraging toegevoegd aan het netwerkverkeer en wordt de algehele prestatie negatief beïnvloed.  

Met split tunneling kunt u uw VPN-client zo configureren dat specifieke typen verkeer niet via de VPN-verbinding naar het bedrijfsnetwerk worden verzonden.

Configureer uw split tunneling VPN-clients zodanig dat verkeer wordt uitgesloten naar de Microsoft 365-eindpuntcategorie **Optimaliseren** over de VPN-verbinding om toegang tot Microsoft 365-cloudresources te optimaliseren. Zie [Office 365-eindpuntcategorieën](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories) voor meer informatie.  Bekijk [hier](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) de lijst met eindpunten met categorie Optimaliseren.

![Netwerkverkeer van VPN-clients met tunneling](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

Hiermee kan de VPN-client cruciaal Microsoft 365-cloudserviceverkeer direct over internet verzenden en ontvangen en via het dichtstbijzijnde ingangspunt in het Microsoft-netwerk.

Bekijk [Office 365-connectiviteit optimaliseren voor externe gebruikers met VPN-split-tunneling](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel) voor meer informatie en richtlijnen.

## <a name="deploy-remote-access-when-all-your-apps-are-web-apps-and-you-have-hybrid-identity"></a>Externe toegang implementeren wanneer al uw apps web-apps zijn en u een hybride identiteit hebt

Als uw externe medewerkers geen traditionele VPN-client gebruiken en uw on-premises gebruikersaccounts en -groepen worden gesynchroniseerd met Azure AD, kunt u Azure AD-toepassingsproxy gebruiken om veilige externe toegang te bieden voor webtoepassingen die worden gehost op intranetservers. Webtoepassingen omvatten onder meer SharePoint-sites, Outlook-webtoegangsservers of andere bedrijfswebtoepassingen. 

Hier vindt u de onderdelen van Azure AD-toepassingsproxy.

![Onderdelen van Azure AD-toepassingsproxy](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-application-proxy.png)

Zie dit [overzicht van Azure AD-toepassingsproxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)voor meer informatie.

## <a name="deploy-remote-access-when-not-all-your-apps-are-web-apps"></a>Externe toegang implementeren wanneer niet al uw apps web-apps zijn

Als uw externe medewerkers geen traditionele VPN-client gebruiken en sommige van uw apps zijn geen web-apps, kunt u een Azure P2S-VPN (Point-to-Site) gebruiken.

Een P2S VPN-verbinding maakt een beveiligde verbinding met uw bedrijfsnetwerk vanaf het apparaat van de externe medewerker via een virtueel Azure-netwerk. 

![Onderdelen van Azure P2S VPN](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-p2s-vpn.png)

Zie dit [overzicht van P2S VPN](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about) voor meer informatie.

## <a name="deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices"></a>Windows-virtueel bureaublad implementeren om externe toegang te bieden voor externe medewerkers met persoonlijke apparaten 

Om externe medewerkers te ondersteunen die alleen hun persoonlijke en onbeheerde apparaten kunnen gebruiken, gebruikt u Windows-virtueel bureaublad in Azure om virtuele bureaubladen te maken en toe te wijzen aan uw gebruikers die thuiswerken.

Gevirtualiseerde pc's werken net als pc's die verbinding hebben met uw bedrijfsnetwerk.

Voor meer informatie raadpleegt u dit [overzicht van Windows-virtueel bureaublad](https://docs.microsoft.com/azure/virtual-desktop/overview).

## <a name="admin-technical-resources-for-remote-access"></a>Technische bronnen voor beheerders voor externe toegang

- [Office 365-verkeer snel optimaliseren voor externe medewerkers en de belasting van uw infrastructuur verminderen](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571)
- [Office 365-connectiviteit optimaliseren voor externe gebruikers met VPN-split-tunneling](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel)

## <a name="results-of-step-2"></a>Resultaten van stap 2

Na de implementatie van een oplossing voor externe toegang voor uw externe medewerkers:

| Configuratie voor externe toegang | Resultaten |
|:-------|:-----|
| Er is een VPN-oplossing voor externe toegang geïnstalleerd | U hebt uw VPN-client voor externe toegang voor split tunneling en de Microsoft 365-eindpuncategorie Optimaliseren geconfigureerd. |
| Geen VPN-oplossing voor externe toegang en u hebt alleen externe toegang nodig tot on-premises web-apps | U hebt Azure-toepassingsproxy geconfigureerd. |
| Geen VPN-oplossing voor externe toegang en u hebt externe toegang nodig tot on-premises apps, waarvan sommige niet op internet zijn gebaseerd | U hebt Azure P2S VPN geconfigureerd. |
| Externe medewerkers gebruiken hun persoonlijke apparaten thuis | U hebt Windows-virtueel bureaublad geconfigureerd. |
|||

## <a name="next-step"></a>Volgende stap

Ga door met [Stap 3](empower-people-to-work-remotely-manage-endpoints.md) om uw apparaten, pc's en andere eindpunten te beheren.
