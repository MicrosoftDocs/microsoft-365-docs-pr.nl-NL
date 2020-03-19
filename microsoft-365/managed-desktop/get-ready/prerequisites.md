---
title: Vereisten voor Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b729712a188c105fdf8a38e208124c2ef4c27a33
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42805678"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Vereisten voor Microsoft Managed Desktop

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

In dit onderwerp worden de infrastructuurvereisten beschreven waaraan u moet voldoen om succes te garanderen met Microsoft Managed Desktop. 

Microsoft FastTrack is beschikbaar om u te helpen aan deze vereisten te voldoen en u te helpen zich voor te bereiden op deelname aan Microsoft Managed Desktop. Zie [Microsoft FastTrack](https://fasttrack.microsoft.com/about)voor meer informatie. 

Gebied | Vereiste details
--- | ---
Licenties |Microsoft Managed Desktop vereist een van de volgende Microsoft 365-licenties (of equivalenten):<br>-Microsoft 365 E5<br>-Microsoft 365 E3 met de Microsoft 365 E5 Security-invoegtoepassing<br><br>Zie Meer informatie over licenties in dit onderwerp [voor](#more-about-licenses) meer informatie over de specifieke serviceplannen en hun rol in Microsoft Managed Desktop.<br>Zie [Microsoft 365-licenties](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)voor meer informatie over beschikbare licenties.
Connectiviteit |  Alle Microsoft Managed Desktop-apparaten vereisen connectiviteit met tal van Microsoft-serviceeindpunten uit het bedrijfsnetwerk.<br><br>Zie [Netwerkconfiguratie](../get-ready/network.md)voor de volledige lijst met vereiste IP's en URL's. 
Azure Active Directory |    Azure Active Directory (Azure AD) moet de bron van autoriteit zijn voor alle gebruikersaccounts of gebruikersaccounts moeten worden gesynchroniseerd vanuit on-premises Active Directory met behulp van de nieuwste ondersteunde versie van Azure AD Connect.<br><br>[Enterprise State Roaming](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) moet zijn ingeschakeld voor Microsoft Managed Desktop-gebruikers.<br><br>Zie [Azure AD Connect voor](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)meer informatie.<br><br>Zie [Azure AD Connect:Version release history voor](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history)meer informatie over ondersteunde Azure AD Connect-versies.
Verificatie |    Als Azure AD niet de bron van autoriteit is voor gebruikersaccounts, moet u een van deze in Azure AD Connect configureren:<br>- Wachtwoordhashsynchronisatie<br>- Pass-through authenticatie<br>- Federatie met ADFS<br><br>Bij het instellen van verificatieopties met Azure AD Connect wordt ook het terugschrijven van wachtwoorden aanbevolen. Zie [Writeback voor wachtwoorden](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)voor meer informatie. <br><br>Zie [Aanmeldingsopties voor Azure AD-gebruikers](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin)voor meer informatie over verificatieopties met Azure AD.
Office 365 |    OneDrive voor Bedrijven moet zijn ingeschakeld voor Microsoft Managed Desktop-gebruikers.<br><br>Hoewel het niet verplicht is om u in te schrijven bij Microsoft Managed Desktop, raden we ten zeerste aan om de volgende services naar de cloud te migreren:<br>- E-mail: migreren naar cloud-gebaseerde postvakken, Exchange online, of configureren met Exchange Online Hybrid met Exchange 2013 of hoger, on-premises.<br>- Bestanden en mappen: migreren naar OneDrive voor Bedrijven of SharePoint Online.<br>- Online samenwerkingstools: Migreren naar teams.
Apparaatbeheer | Microsoft Managed Desktop-apparaten vereisen beheer met Microsoft Intune. Intune moet worden ingesteld als de autoriteit voor beheer van mobiele apparaten.<br><br>Zie [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune)voor meer informatie. 
Back-ups en herstel van gegevens | Microsoft Managed Desktop vereist dat bestanden worden gesynchroniseerd met OneDrive voor Bedrijven voor bescherming. Bestanden die niet zijn gesynchroniseerd met OneDrive voor Bedrijven, worden niet gegarandeerd door Microsoft Managed Desktop en kunnen verloren gaan tijdens apparaatuitwisselingen of ondersteuningsoproepen waarvoor een apparaat opnieuw moet worden ingesteld.<br><br>Hoewel dit niet nodig is, raadt Microsoft Managed Desktop ten zeerste migratie van toegewezen netwerkstations naar de juiste cloudoplossing aan. Zie [Toegewezen stations voorbereiden voor Microsoft Managed Desktop](mapped-drives.md) voor meer informatie

Neem contact op met uw Microsoft Account Manager wanneer u klaar bent om aan de slag te gaan met Microsoft Managed Desktop. 

## <a name="more-about-licenses"></a>Meer informatie over licenties

Microsoft Managed Desktop vereist bepaalde licentieopties om te kunnen functioneren. Deze opties zijn beschikbaar in een aantal verschillende licentiebundels, waarvan sommige je misschien al bezit. In deze tabel ziet u welke benodigde opties beschikbaar zijn in welke licenties en hun rol in Microsoft Managed Desktop worden samengevat.

> [!TIP]
> Als u deze licentieopties wilt toewijzen aan specifieke gebruikers, raden we u aan gebruik te maken van de [groepslicentiefunctie](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) van Azure Active Directory.



|Licentieoptie |Beschikbaar in *een* van deze licentieproducten |Hoe Microsoft Managed Desktop het gebruikt|
|-------------|-------------|-------------|
|Azure Active Directory Premium P1     |- Microsoft 365 E5<br>- Microsoft 365 E3 + Microsoft 365 *E5* Security Add-on<br>- Enterprise Mobility + Security E5<br>- Enterprise Mobility + Security E3<br>- Azure Active Directory Premium P1|  Biedt toegang tot Microsoft Cloud Services; hiermee kan AutoPilot apparaten registreren      |
|Microsoft Intune | - Microsoft 365 E5<br>- Microsoft 365 E3 + Microsoft 365 *E5* Security Add-on<br>- Enterprise Mobility + Security E5<br>- Enterprise Mobility + Security E3<br>- Microsoft Intune  |  Nodig om apparaten te registreren, updates te implementeren en apparaten te beheren       |
|Windows 10 Enterprise  |- Microsoft 365 E5<br>- Microsoft 365 E3 + Microsoft 365 *E5* Security Add-on<br>- Windows 10 Enterprise E3<br>- Windows 10 Enterprise E5 | Biedt bedrijfsfuncties van Windows 10       |
|Microsoft Defender Advanced Threat Protection | - Microsoft 365 E5<br>- Microsoft 365 E3 + Microsoft 365 *E5* Security Add-on<br>- Windows 10 Enterprise E5<br>- Microsoft Defender Advanced Threat Protection   |  Biedt detectie, bewaking, waarschuwing en reactie op bedreigingen  |
|Office 365 ProPlus  |- Microsoft 365 E5<br>- Microsoft 365 E3<br>- Office 365 E5<br>- Office 365 E3| Activeert tools voor Office en productiviteit en samenwerking    |

> [!TIP]
> Met Uw Microsoft Account Manager u uw huidige licenties en serviceplannen bekijken en het meest efficiënte pad vinden dat u nodig hebt om extra licenties of serviceplannen te krijgen die u nodig zou kunnen hebben, terwijl u dubbel werk voorkomt.
