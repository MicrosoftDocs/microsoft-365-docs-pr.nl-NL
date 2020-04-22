---
title: Vereisten voor Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b6ee70ca577d58661cabee9e2a597b061c4cc190
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632825"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Vereisten voor Microsoft Managed Desktop

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

In dit onderwerp worden de infrastructuurvereisten beschreven waaraan u moet voldoen om succes met Microsoft Managed Desktop te verzekeren. 

Microsoft FastTrack is beschikbaar om u te helpen aan deze vereisten te voldoen en u te helpen zich voor te bereiden op deelname aan Microsoft Managed Desktop. Zie [Microsoft FastTrack voor](https://fasttrack.microsoft.com/about)meer informatie. 

Gebied | Vereiste details
--- | ---
Licenties |Microsoft Managed Desktop vereist een van de volgende Microsoft 365-licenties (of equivalenten):<br>-Microsoft 365 E5<br>-Microsoft 365 E3 met de Microsoft 365 E5 Security add-on<br><br>Zie Meer informatie over licenties in dit onderwerp [voor](#more-about-licenses) meer informatie over de specifieke serviceplannen en hun rol in Microsoft Managed Desktop.<br>Zie [Microsoft 365-licenties](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)voor meer informatie over beschikbare licenties.
Connectiviteit |  Alle Microsoft Managed Desktop-apparaten vereisen connectiviteit met tal van Microsoft-serviceeindpunten uit het bedrijfsnetwerk.<br><br>Zie [Netwerkconfiguratie](../get-ready/network.md)voor de volledige lijst met vereiste IP's en URL's. 
Microsoft Azure Active Directory |    Azure Active Directory (Azure AD) moet de bron van autoriteit zijn voor alle gebruikersaccounts of gebruikersaccounts moeten worden gesynchroniseerd vanuit on-premises Active Directory met behulp van de nieuwste ondersteunde versie van Azure AD Connect.<br><br>[Enterprise State Roaming](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) moet zijn ingeschakeld voor Microsoft Managed Desktop-gebruikers.<br><br>Zie [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)voor meer informatie.<br><br>Zie [Azure AD Connect:Releasehistory voor](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history)meer informatie over ondersteunde Azure AD Connect-versies .
Verificatie |    Als Azure AD niet de bron van autoriteit voor gebruikersaccounts is, moet u een van deze instellingen configureren in Azure AD Connect:<br>- Synchronisatie van wachtwoordhash<br>- Pass-through authenticatie<br>- Federatie met ADFS<br><br>Wanneer u verificatieopties instelt met Azure AD Connect, wordt ook het terugschrijven van wachtwoorden aanbevolen. Zie [Terugschrijven voor wachtwoorden](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)voor meer informatie. <br><br>Zie [Aanmeldingsopties voor Azure AD Connect-gebruikers](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin)voor meer informatie over verificatieopties met Azure AD.
Microsoft 365 | OneDrive voor Bedrijven moet zijn ingeschakeld voor Microsoft Managed Desktop-gebruikers.<br><br>Hoewel het niet nodig is om u in te schrijven bij Microsoft Managed Desktop, raden we ten zeerste aan om de volgende services naar de cloud te migreren:<br>- E-mail: migreer naar postvakken in de cloud, Exchange online of configureer met Exchange Online Hybrid met Exchange 2013 of hoger, on-premises.<br>- Bestanden en mappen: migreren naar OneDrive voor Bedrijven of SharePoint Online.<br>- Online samenwerkingstools: migreren naar Teams.
Apparaatbeheer | Microsoft Managed Desktop-apparaten vereisen beheer met Microsoft Intune. Intune moet worden ingesteld als de autoriteit Voor beheer van mobiele apparaten.<br><br>Zie [Microsoft Intune voor](https://www.microsoft.com/cloud-platform/microsoft-intune)meer informatie. 
Back-up smaken van gegevens en herstel | Voor Microsoft Managed Desktop moeten bestanden worden gesynchroniseerd met OneDrive voor Bedrijven voor bescherming. Bestanden die niet zijn gesynchroniseerd met OneDrive voor Bedrijven, worden niet gegarandeerd door Microsoft Managed Desktop en gaan mogelijk verloren tijdens apparaatuitwisselingen of ondersteuningsgesprekken waarvoor een apparaat opnieuw moet worden ingesteld.<br><br>Hoewel dit niet vereist is, raadt Microsoft Managed Desktop migratie van toegewezen netwerkstations naar de juiste cloudoplossing ten zeerste aan. Zie [Toegewezen stations voorbereiden voor Microsoft Managed Desktop voor](mapped-drives.md) meer informatie

Neem contact op met Microsoft Accountbeheer wanneer u klaar bent om aan de slag te gaan met Microsoft Managed Desktop. 

## <a name="more-about-licenses"></a>Meer informatie over licenties

Microsoft Managed Desktop vereist bepaalde licentieopties om te kunnen functioneren. Deze opties zijn beschikbaar in een aantal verschillende licentiebundels, waarvan u sommige al bezit. In deze tabel ziet u welke benodigde opties beschikbaar zijn in welke licenties en een overzicht van hun rol in Microsoft Managed Desktop.

> [!TIP]
> Als u deze licentieopties wilt toewijzen aan specifieke gebruikers, raden we u aan gebruik te maken van de [groepslicentiefunctie](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) van Azure Active Directory.



|Licentieoptie |Beschikbaar in *een* van deze licentieproducten |Hoe Microsoft Managed Desktop het gebruikt|
|-------------|-------------|-------------|
|Azure Active Directory Premium P1     |- Microsoft 365 E5<br>- Microsoft 365 E3 + Microsoft 365 *E5-beveiligingstoepassing*<br>- Enterprise Mobility + Beveiliging E5<br>- Enterprise Mobility + Beveiliging E3<br>- Azure Active Directory Premium P1|  Biedt toegang tot Microsoft Cloud Services; stelt AutoPilot in staat om apparaten te registreren      |
|Microsoft Intune | - Microsoft 365 E5<br>- Microsoft 365 E3 + Microsoft 365 *E5-beveiligingstoepassing*<br>- Enterprise Mobility + Beveiliging E5<br>- Enterprise Mobility + Beveiliging E3<br>- Microsoft Intune  |  Noodzakelijk om apparaten te registreren, updates te implementeren en apparaten te beheren       |
|Windows 10 Enterprise  |- Microsoft 365 E5<br>- Microsoft 365 E3 + Microsoft 365 *E5-beveiligingstoepassing*<br>- Windows 10 Enterprise E3<br>- Windows 10 Enterprise E5 | Biedt bedrijfsfuncties van Windows 10       |
|Microsoft Defender Advanced Threat Protection | - Microsoft 365 E5<br>- Microsoft 365 E3 + Microsoft 365 *E5-beveiligingstoepassing*<br>- Windows 10 Enterprise E5<br>- Geavanceerde bescherming tegen geavanceerde bedreigingen van Microsoft Defender   |  Biedt detectie, monitoring, waarschuwingen en respons op bedreigingen  |
|Microsoft 365 Apps voor bedrijven  |- Microsoft 365 E5<br>- Microsoft 365 E3<br>- Office 365 E5<br>- Office 365 E3| Activeert office- en productiviteits- en samenwerkingstools    |

> [!TIP]
> Met Uw Microsoft-accountmanager u uw huidige licenties en serviceplannen bekijken en het meest efficiënte pad voor u vinden om extra licenties of serviceplannen te krijgen die u mogelijk nodig hebt, terwijl dubbel werk wordt voorkomen.
