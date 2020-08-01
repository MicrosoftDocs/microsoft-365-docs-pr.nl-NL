---
title: Vereisten voor Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: c958101e1f3268c706c27df6fc9e21e9914b3f46
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530281"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Vereisten voor Microsoft Managed Desktop

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

In dit onderwerp worden de infrastructuurvereisten beschreven waaraan u moet voldoen om succes te boeken met Microsoft Managed Desktop. 

Microsoft FastTrack is beschikbaar om u te helpen aan deze vereisten te voldoen en u te helpen zich voor te bereiden op deelname aan Microsoft Managed Desktop. Zie [Microsoft FastTrack](https://fasttrack.microsoft.com/about)voor meer informatie. 

Gebied | Vereiste details
--- | ---
Licenties |Microsoft Managed Desktop vereist een van de volgende Microsoft 365-licenties (of equivalenten):<br>-Microsoft 365 E5<br>-Microsoft 365 E3 met de Microsoft 365 E5 Security add-on<br><br>Zie [Meer informatie over licenties](#more-about-licenses) in dit onderwerp voor meer informatie over de specifieke serviceplannen en hun rol in Microsoft Managed Desktop.<br>Zie [Microsoft 365-licenties](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)voor meer informatie over beschikbare licenties.
Connectiviteit |  Alle Microsoft Managed Desktop-apparaten vereisen connectiviteit met tal van Microsoft-serviceeindpunten van het bedrijfsnetwerk.<br><br>Zie [Netwerkconfiguratie voor](../get-ready/network.md)de volledige lijst met vereiste IP's en URL's. 
Microsoft Azure Active Directory |    Azure Active Directory (Azure AD) moet de autoriteitsbron zijn voor alle gebruikersaccounts of gebruikersaccounts moeten worden gesynchroniseerd vanuit on-premises Active Directory met behulp van de nieuwste ondersteunde versie van Azure AD Connect.<br><br>[Enterprise State Roaming](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) moet zijn ingeschakeld voor Microsoft Managed Desktop-gebruikers.<br><br>Zie [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)voor meer informatie .<br><br>Zie [Azure AD Connect:Versiereleasegeschiedenis](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history)voor meer informatie over ondersteunde Azure AD Connect-versies.
Verificatie |    Als Azure AD niet de bron is van primaire verificatie voor gebruikersaccounts, moet u een van deze instellingen configureren in Azure AD Connect:<br>- Wachtwoord hash synchronisatie<br>- Pass-through authenticatie<br>- Een externe identiteitsprovider (inclusief Windows Server ADFS en niet-Microsoft IDPs) die is geconfigureerd om te voldoen aan azure AD-integratievereisten. Zie de [richtlijnen](https://www.microsoft.com/en-us/download/details.aspx?id=56843) voor meer informatie. <br><br>Wanneer u verificatieopties instelt met Azure AD Connect, wordt ook het schrijven van wachtwoorden aanbevolen. Zie [Wachtwoord writeback voor](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)meer informatie. <br><br>Als een externe identiteitsprovider is geïmplementeerd, moet u de oplossing valideren:<br>- Voldoet aan azure AD-integratievereisten<br>- Ondersteunt Azure AD Voorwaardelijke toegang, dit is om mmd-apparaatnalevingsbeleid te configureren<br>- Apparaatinschrijving en gebruik van Microsoft 365-services of -functies die vereist zijn als onderdeel van Microsoft Managed Desktop mogelijk maken <br><br>Zie [Aanmeldingsopties](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin)voor Azure AD AD voor gebruikers voor meer informatie over verificatieopties met Azure AD.
Microsoft 365 | OneDrive voor Bedrijven moet zijn ingeschakeld voor Microsoft Managed Desktop-gebruikers.<br><br>Hoewel het niet nodig is om u in te schrijven bij Microsoft Managed Desktop, raden we u ten zeerste aan de volgende services naar de cloud te migreren:<br>- E-mail: Migreren naar cloudpostvakken, Exchange online of configureren met Exchange Online Hybrid met Exchange 2013 of hoger, on-premises.<br>- Bestanden en mappen: migreren naar OneDrive voor Bedrijven of SharePoint Online.<br>- Online samenwerkingstools: Migreren naar Teams.
Apparaatbeheer | Microsoft Managed Desktop-apparaten vereisen beheer met Microsoft Intune. Intune moet worden ingesteld als de mobile device management autoriteit.<br><br>Zie [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune)voor meer informatie. 
Back-up en herstel van gegevens | Microsoft Managed Desktop vereist dat bestanden worden gesynchroniseerd met OneDrive voor Bedrijven voor bescherming. Bestanden die niet zijn gesynchroniseerd met OneDrive voor Bedrijven, worden niet gegarandeerd door Microsoft Managed Desktop en kunnen verloren gaan tijdens het uitwisselen van apparaten of ondersteuningsoproepen waarvoor een apparaat opnieuw moet worden ingesteld.<br><br>Hoewel dit niet vereist is, raadt Microsoft Managed Desktop ten zeerste migratie aan van toegewezen netwerkstations naar de juiste cloudoplossing. Zie Toegewezen [stations voorbereiden voor Microsoft Managed Desktop voor](mapped-drives.md) meer informatie

Neem contact op met uw Microsoft Account Manager wanneer u klaar bent om aan de slag te gaan met Microsoft Managed Desktop. 

## <a name="more-about-licenses"></a>Meer over licenties

Microsoft Managed Desktop vereist bepaalde licentieopties om te kunnen functioneren. Deze opties zijn beschikbaar in een aantal verschillende licentiebundels, waarvan sommige u misschien al bezit. In deze tabel ziet u welke benodigde opties beschikbaar zijn in welke licenties en worden hun rol in Microsoft Managed Desktop samengevat.

> [!TIP]
> Als u deze licentieopties wilt toewijzen aan specifieke gebruikers, raden we u aan gebruik te maken van de [licentiefunctie op basis](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) van groepen van Azure Active Directory.



|Licentieoptie |Beschikbaar in *een* van deze licentieproducten |Hoe Microsoft Managed Desktop het gebruikt|
|-------------|-------------|-------------|
|Azure Active Directory Premium P1     |- Microsoft 365 E5<br>- Microsoft 365 E3 + Microsoft 365 *E5* Security Add-on<br>- Enterprise Mobility + Beveiliging E5<br>- Enterprise Mobility + Beveiliging E3<br>- Azure Active Directory Premium P1|  Biedt toegang tot Microsoft Cloud Services; stelt AutoPilot in staat om apparaten te registreren      |
|Microsoft Intune | - Microsoft 365 E5<br>- Microsoft 365 E3 + Microsoft 365 *E5* Security Add-on<br>- Enterprise Mobility + Beveiliging E5<br>- Enterprise Mobility + Beveiliging E3<br>- Microsoft Intune  |  Nodig om apparaten te registreren, updates te implementeren en apparaten te beheren       |
|Windows 10 Enterprise  |- Microsoft 365 E5<br>- Microsoft 365 E3 + Microsoft 365 *E5* Security Add-on<br>- Windows 10 Enterprise E3<br>- Windows 10 Enterprise E5 | Biedt bedrijfsfuncties van Windows 10       |
|Microsoft Defender Advanced Threat Protection | - Microsoft 365 E5<br>- Microsoft 365 E3 + Microsoft 365 *E5* Security Add-on<br>- Windows 10 Enterprise E5<br>- Microsoft Defender Advanced Threat Protection   |  Biedt detectie, monitoring, waarschuwing en reactie op bedreigingen  |
|Microsoft 365-apps voor ondernemingen  |- Microsoft 365 E5<br>- Microsoft 365 E3<br>- Office 365 E5<br>- Office 365 E3| Activeert Office- en productiviteits- en samenwerkingstools    |

> [!TIP]
> Met uw Microsoft Account Manager u uw huidige licenties en serviceplannen bekijken en het meest efficiënte pad vinden voor u om extra licenties of serviceplannen te krijgen die u nodig hebt, terwijl dubbel werk wordt vermeden.
