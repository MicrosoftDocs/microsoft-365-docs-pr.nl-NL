---
title: Vereisten voor Microsoft Managed Desktop
description: Licenties, Azure-accounts, verificatie-instellingen en Microsoft 365-instellingen die moeten worden ingesteld voordat u zich inschrijft in Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: c298c0d07b73966fe3946f0e3f2706da5d2d30fc
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453895"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Vereisten voor Microsoft Managed Desktop

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

In dit onderwerp vindt u een overzicht van de vereisten voor de infrastructuur waar u aan moet voldoen om succes te garanderen met beheerd bureaublad van Microsoft. 


Gebied | Vereiste details
--- | ---
Licenties |Voor Microsoft Managed Desktop is de Microsoft 365 E3-licentie met Microsoft Defender voor eindpunt (of equivalenten) toegewezen aan uw gebruikers vereist. Er moeten twee licenties voor Azure Active Directory Premium 2 beschikbaar zijn in de tenant, maar gebruikers hebben deze licentie niet nodig. <br>Zie meer informatie over licenties in dit onderwerp voor [meer](#more-about-licenses) informatie over specifieke serviceplannen.<br>Zie Microsoft [365-licenties](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)voor meer informatie over beschikbare licenties.
Connectiviteit |  Alle beheerde desktopapparaten van Microsoft hebben verbinding nodig met verschillende service-eindpunten van Microsoft vanuit het bedrijfsnetwerk.<br><br>Zie Netwerkconfiguratie voor de volledige lijst met vereiste URL's [en URL's.](../get-ready/network.md) 
Microsoft Azure Active Directory |    Azure Active Directory (Azure AD) moet de bron van de autoriteit zijn voor alle gebruikersaccounts of gebruikersaccounts moeten worden gesynchroniseerd vanuit on-premises Active Directory met de nieuwste ondersteunde versie van Azure AD Connect.<br><br>[Enterprise State Roaming moet](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) zijn ingeschakeld voor beheerde desktopgebruikers van Microsoft.<br><br>Zie Azure AD Connect voor [meer informatie.](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)<br><br>Zie de releasegeschiedenis van Azure AD [Connect:Version](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history)voor meer informatie over ondersteunde Versies van Azure AD Connect.
Verificatie |    Als Azure AD niet de bron is van primaire verificatie voor gebruikersaccounts, moet u een van deze configureren in Azure AD Connect:<br>- Wachtwoord-hashsynchronisatie<br>- Pass Through-verificatie<br>- Een externe id-provider (met inbegrip van Windows Server ADFS en niet-Microsoft-id's) die is geconfigureerd om te voldoen aan de integratievereisten voor Azure AD. Zie de [richtlijnen](https://www.microsoft.com/download/details.aspx?id=56843) voor meer informatie. <br><br>Als u verificatieopties invoegt met Azure AD Connect, wordt wachtwoordschrijven ook aanbevolen. Zie Wachtwoord terugschrijven [voor meer informatie.](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback) <br><br>Als een externe identiteitsprovider wordt geïmplementeerd, moet u de oplossing valideren:<br>- Voldoet aan de integratievereisten voor Azure AD<br>- Ondersteunt voorwaardelijke toegang voor Azure AD, waarmee het beleid voor de naleving van het Microsoft Managed Desktop-apparaat kan worden geconfigureerd<br>- Schakelt apparaatinschrijving en gebruik van Microsoft 365-services of -functies in die zijn vereist als onderdeel van Het beheerde bureaublad van Microsoft <br><br>Zie aanmeldingsopties voor gebruikers van Azure AD Connect voor meer informatie [over verificatieopties met Azure AD.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin)
Microsoft 365 | OneDrive voor Bedrijven moet zijn ingeschakeld voor gebruikers van het beheerde bureaublad van Microsoft.<br><br>Hoewel het niet is vereist om u te registreren met Microsoft Managed Desktop, raden we u ten zeerste aan om de volgende services te migreren naar de cloud:<br>- E-mail: Migreren naar postvakken in de cloud, Exchange Online of configureren met Exchange Online Hybrid met Exchange 2013 of hoger, on-premises.<br>- Bestanden en mappen: Migreren naar OneDrive voor Bedrijven of SharePoint Online.<br>- Hulpprogramma's voor onlinesamenwerking: Migreren naar Teams.
Apparaatbeheer | Voor beheerde Microsoft-desktopapparaten is beheer van Microsoft Intune vereist. Intune moet worden ingesteld als de mobile device management authority.<br><br>Zie [Microsoft Intune voor meer informatie.](https://www.microsoft.com/cloud-platform/microsoft-intune) 
Back-up en herstel van gegevens |  Voor de beveiliging van Microsoft Beheerd bureaublad moeten bestanden worden gesynchroniseerd met OneDrive voor Bedrijven. Bestanden die niet worden gesynchroniseerd met OneDrive voor Bedrijven, worden niet gegarandeerd door Microsoft Managed Desktop en gaan mogelijk verloren tijdens apparaatuitwisseling of ondersteuningsgesprekken waarbij het apparaat opnieuw moet worden ingesteld.<br><br>Hoewel dit niet vereist is, raadt Microsoft Beheerd bureaublad ten zeerste aan om migratie van kaartnetwerkstations naar de juiste cloudoplossing uit te breiden. Zie Kaartstations voorbereiden voor Het beheerde bureaublad [van Microsoft voor meer informatie](mapped-drives.md)

Wanneer u klaar bent om aan de slag te gaan met het beheerde bureaublad van Microsoft, neem dan contact op met uw Microsoft Account Manager. 

## <a name="more-about-licenses"></a>Meer informatie over licenties

Voor de werking van Microsoft Managed Desktop zijn bepaalde licentieopties vereist. Zie [Microsoft Managed Desktop-technologieën](../intro/technologies.md) voor informatie over hoe deze licenties worden gebruikt.

> [!TIP]
> Als u deze licentieopties wilt toewijzen aan specifieke gebruikers, raden we u aan gebruik te maken van de functie voor groepslicenties [van](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) Azure Active Directory.

- Azure Active Directory Premium P1
- Microsoft Intune 
- Windows 10 Enterprise  
- Microsoft Defender for Endpoint
- Microsoft 365-apps voor ondernemingen
- Microsoft Teams
- [SharePoint Online, abonnement 2](https://www.microsoft.com/microsoft-365/sharepoint/compare-sharepoint-plans)
- [Exchange Online Abonnement 2](https://www.microsoft.com/microsoft-365/exchange/compare-microsoft-exchange-online-plans) 


> [!TIP]
> Uw Microsoft Account Manager helpt u uw huidige licenties en serviceplannen te controleren en het meest efficiënte pad voor u te vinden om extra licenties of serviceplannen te krijgen die u mogelijk nodig hebt, terwijl u duplicatie vermijdt.
