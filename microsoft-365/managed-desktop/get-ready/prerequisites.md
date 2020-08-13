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
ms.openlocfilehash: 041e7dc89ddd42326ce0a5040364306e26fd2413
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653387"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Vereisten voor Microsoft Managed Desktop

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

In dit onderwerp vindt u een overzicht van de vereisten voor de infrastructuur die u moet vergaderen met Microsoft Managed Desktop. 

Microsoft FastTrack is beschikbaar om u te helpen aan deze vereisten te voldoen en helpt u bij het voorbereiden van deelnemen aan deelnemen aan Microsoft Managed Desktop. Zie [Microsoft FastTrack](https://fasttrack.microsoft.com/about)voor meer informatie. 

Ziet | Vereiste gegevens
--- | ---
Licenties |Voor Microsoft Managed Desktop is een of meer van de volgende Microsoft 365-licenties (of equivalenten) nodig:<br>-Microsoft 365 E5<br>-Microsoft 365 E3 met de Microsoft 365 E5-beveiligingstoepassing<br><br>Zie [meer informatie over licenties](#more-about-licenses) in dit onderwerp voor meer informatie over de specifieke serviceplannen en hun rol in Microsoft Managed Desktop.<br>Zie [Microsoft 365 Licensing](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)voor meer informatie over beschikbare licenties.
Connectivity |  Voor alle door Microsoft beheerde desktop apparaten is connectiviteit met talrijke service-eindpunten van het bedrijfsnetwerk vereist.<br><br>Voor de volledige lijst met vereiste IPs en Url's, raadpleegt u [Netwerkconfiguratie](../get-ready/network.md). 
Microsoft Azure Active Directory |    Azure Active Directory (Azure AD) moet de bron van de autoriteit zijn voor alle gebruikersaccounts, of gebruikersaccounts moeten worden gesynchroniseerd vanuit de on-premises Active Directory met behulp van de nieuwste ondersteunde versie van Azure AD Connect.<br><br>[Enterprise State roaming](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) moet worden ingeschakeld voor Microsoft Managed desktop users.<br><br>Zie voor meer informatie [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect).<br><br>Zie voor meer informatie over ondersteunde versies van Azure AD Connect de [versiegeschiedenis van Azure AD Connect: versie release](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history).
Verificatie |    Als Azure AD niet de bron is van primaire verificatie voor gebruikersaccounts, moet u een van deze opties configureren in azure AD Connect:<br>-Hash-synchronisatie van wachtwoord<br>Pass Through-verificatie<br>: Een externe identiteitsprovider (waaronder Windows Server ADFS en niet-Microsoft IDPs) geconfigureerd om aan de vereisten voor Azure AD-integratie te voldoen. Zie de [richtlijnen](https://www.microsoft.com/en-us/download/details.aspx?id=56843) voor meer informatie. <br><br>Bij het instellen van verificatieopties met Azure AD Connect, wordt ook aangeraden om het wachtwoord over te schrijven. Zie voor meer informatie [wachtwoord terugschrijven](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). <br><br>Als een externe identiteitsprovider wordt geïmplementeerd, moet u de oplossing valideren:<br>-Voldoet aan de vereisten voor Azure AD-integratie<br>-Ondersteuning voor voorwaardelijke toegang van Azure AD, dit is om MMD-apparaat-nalevingsbeleid in te schakelen<br>-Schakelt het registreren van apparaten en het gebruik van Microsoft 365-Services of functies die nodig zijn als onderdeel van Microsoft Managed Desktop <br><br>Zie [aanmeldingsopties voor Azure AD Connect-gebruikers](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin)voor meer informatie over verificatie-opties in azure AD.
Microsoft 365 | OneDrive voor bedrijven moet worden ingeschakeld voor Microsoft Managed desktop users.<br><br>Hoewel het niet vereist is om u aan te melden bij Microsoft Managed Desktop, wordt nadrukkelijk geadviseerd dat de volgende services worden gemigreerd naar de Cloud:<br>-E-mail: migreren naar Cloud postvakken, Exchange Online of configureren met Exchange Online Hybrid met Exchange 2013 of hoger, on-premises.<br>-Bestanden en mappen: migreren naar OneDrive voor bedrijven of SharePoint Online.<br>-Online samenwerkingsprogramma's: migreren naar teams.
Apparaatbeheer | Door Microsoft beheerde bureaublad apparaten is beheer met Microsoft intune vereist. InTune moet zijn ingesteld als de service voor het beheer van mobiele apparaten.<br><br>Zie [Microsoft intune](https://www.microsoft.com/cloud-platform/microsoft-intune)voor meer informatie. 
Gegevensback-up en herstel | Microsoft Managed Desktop vereist dat de bestanden worden gesynchroniseerd met OneDrive voor bedrijven voor beveiliging. Bestanden die niet zijn gesynchroniseerd met OneDrive voor bedrijven, worden niet door Microsoft beheerd bureaublad gegarandeerd en gaan mogelijk verloren bij het overzetten van een apparaat of door de ondersteuning ervan.<br><br>Hoewel het niet vereist is, wordt door Microsoft beheerde bureaublad sterk aanbevolen migratie van toegewezen netwerkstations naar de juiste Cloud oplossing. Zie voor meer informatie [toegewezen stations voorbereiden voor Microsoft Managed Desktop](mapped-drives.md)

Neem contact op met uw Microsoft-account beheerder als u klaar bent om aan de slag te gaan met Microsoft Managed Desktop. 

## <a name="more-about-licenses"></a>Meer informatie over licenties

Voor het Microsoft-beheer bureaublad zijn bepaalde licentieopties vereist. Deze opties zijn beschikbaar in diverse licentiepakketten, waarvan u een deel van de licentie hebt. In deze tabel ziet u de beschikbare opties die beschikbaar zijn voor de licenties en een overzicht van hun rol in Microsoft Managed Desktop.

> [!TIP]
> U wordt aangeraden om de licentie [functie voor groepen op basis](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) van Azure Active Directory te gebruiken om deze licentieopties aan specifieke gebruikers toe te wijzen.



|Licentieoptie |Beschikbaar in *deze* licentie producten |Hoe Microsoft Managed Desktop gebruikmaakt van dit|
|-------------|-------------|-------------|
|Azure Active Directory Premium P2     |-Microsoft 365 E5<br>-Microsoft 365 E3 + Microsoft 365 *E5* -beveiligingstoepassing<br>-Enterprise Mobility + Security E5<br>-Enterprise Mobility + beveiligings E3<br>-Azure Active Directory Premium P2|  Toegang tot Microsoft-Cloud Services. kan auto pilot-apparaten registreren      |
|Microsoft Intune | -Microsoft 365 E5<br>-Microsoft 365 E3 + Microsoft 365 *E5* -beveiligingstoepassing<br>-Enterprise Mobility + Security E5<br>-Enterprise Mobility + beveiligings E3<br>-Microsoft intune  |  Noodzakelijk om apparaten te registreren, updates te implementeren en apparaten te beheren       |
|Windows 10 Enterprise  |-Microsoft 365 E5<br>-Microsoft 365 E3 + Microsoft 365 *E5* -beveiligingstoepassing<br>-Windows 10 Enterprise E3<br>-Windows 10 Enterprise E5 | Voorziet in Enterprise-functies van Windows 10       |
|Microsoft Defender Advanced Threat Protection | -Microsoft 365 E5<br>-Microsoft 365 E3 + Microsoft 365 *E5* -beveiligingstoepassing<br>-Windows 10 Enterprise E5<br>-Microsoft Defender Advanced Threat Protection   |  Zorgt voor detectie, controle, signalering en respons op bedreigingen  |
|Microsoft 365-apps voor ondernemingen  |-Microsoft 365 E5<br>-Microsoft 365 E3<br>-Office 365 E5<br>-Office 365 E3| Activeert Office en productiviteit en samenwerkingshulpmiddelen    |

> [!TIP]
> Uw Microsoft-account manager helpt u bij het beoordelen van uw huidige licenties en serviceplannen, en het meest efficiënte pad voor u achterhalen voor eventuele extra licenties of serviceplannen die u mogelijk nodig hebt, terwijl u het voorkomen van dubbele gegevens.
