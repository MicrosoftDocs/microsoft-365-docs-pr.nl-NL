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
audience: Admin
ms.openlocfilehash: fcfddadf13e000156fa5431cc30bc72f4f3537e2
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581044"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Vereisten voor Microsoft Managed Desktop

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

In dit onderwerp worden de infrastructuurvereisten beschreven die u moet voldoen om te zorgen voor succes met Microsoft Managed Desktop. 


Gebied | Details van vereisten
--- | ---
Licenties |Voor Microsoft Managed Desktop is de Microsoft 365 E3-licentie vereist met Microsoft Defender voor eindpunten (of equivalenten) die aan uw gebruikers zijn toegewezen. Er moeten twee licenties voor Azure Active Directory Premium 2 beschikbaar zijn in de tenant, maar gebruikers hebben deze licentie niet nodig. <br>Zie Meer informatie over licenties [in](#more-about-licenses) dit onderwerp voor meer informatie over de specifieke serviceplannen.<br>Zie [Microsoft 365-licenties](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)voor meer informatie over beschikbare licenties.
Connectiviteit |  Voor alle beheerde bureaubladapparaten van Microsoft is verbinding nodig met een groot aantal Microsoft-service-eindpunten van het bedrijfsnetwerk.<br><br>Zie Netwerkconfiguratie voor de volledige lijst met vereiste IPs en [URL's.](../get-ready/network.md) 
Microsoft Azure Active Directory |    Azure Active Directory (Azure AD) moet de bron van autoriteit zijn voor alle gebruikersaccounts of gebruikersaccounts moeten worden gesynchroniseerd vanuit on-premises Active Directory met de meest recente ondersteunde versie van Azure AD Connect.<br><br>[Enterprise State Roaming](/azure/active-directory/devices/enterprise-state-roaming-overview) moet zijn ingeschakeld voor Microsoft Managed Desktop-gebruikers.<br><br>Zie Azure AD Connect voor [meer informatie.](/azure/active-directory/hybrid/whatis-azure-ad-connect)<br><br>Zie [Azure AD Connect:Version release history](/azure/active-directory/hybrid/reference-connect-version-history)voor meer informatie over ondersteunde Azure AD Connect-versies.
Verificatie |    Als Azure AD niet de bron is van primaire verificatie voor gebruikersaccounts, moet u een van deze instellingen configureren in Azure AD Connect:<br>- Wachtwoordhashsynchronisatie<br>- Pass-through-verificatie<br>- Een externe identiteitsprovider (inclusief Windows Server ADFS en niet-Microsoft-id's) die is geconfigureerd om te voldoen aan de vereisten voor Azure AD-integratie. Zie de [richtlijnen](https://www.microsoft.com/download/details.aspx?id=56843) voor meer informatie. <br><br>Wanneer u verificatieopties instelt met Azure AD Connect, wordt ook het terugschrijven van wachtwoorden aanbevolen. Zie Wachtwoord [terugschrijven voor meer informatie.](/azure/active-directory/authentication/howto-sspr-writeback) <br><br>Als een externe identiteitsprovider wordt geïmplementeerd, moet u de oplossing valideren:<br>- Voldoet aan de integratievereisten voor Azure AD<br>- Biedt ondersteuning voor Azure AD Voorwaardelijke toegang, waarmee het compliancebeleid voor Microsoft Managed Desktop-apparaten kan worden geconfigureerd<br>- Hiermee kunt u apparaten registreren en microsoft 365-services of -functies gebruiken die zijn vereist als onderdeel van Microsoft Managed Desktop <br><br>Zie Aanmeldingsopties voor Azure AD Connect voor meer informatie over [verificatieopties met Azure](/azure/active-directory/connect/active-directory-aadconnect-user-signin)AD.
Microsoft 365 | OneDrive voor Bedrijven moet zijn ingeschakeld voor Microsoft Managed Desktop-gebruikers.<br><br>Hoewel het niet verplicht is om u aan te melden bij Microsoft Managed Desktop, raden we ten zeerste aan dat de volgende services worden gemigreerd naar de cloud:<br>- E-mail: migreren naar postvakken in de cloud, Exchange online of configureren met Exchange Online Hybrid met Exchange 2013 of hoger, on-premises.<br>- Bestanden en mappen: migreren naar OneDrive voor Bedrijven of SharePoint Online.<br>- Hulpprogramma's voor onlinesamenwerking: migreren naar Teams.
Apparaatbeheer | Microsoft Managed Desktop-apparaten vereisen beheer met Microsoft Intune. Intune moet worden ingesteld als de autoriteit voor mobiel apparaatbeheer.<br><br>Zie [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune)voor meer informatie. 
Back-up en herstel van gegevens |  Voor Microsoft Managed Desktop moeten bestanden ter bescherming worden gesynchroniseerd met OneDrive voor Bedrijven. Bestanden die niet zijn gesynchroniseerd met OneDrive voor Bedrijven, worden niet gegarandeerd door Microsoft Managed Desktop en kunnen verloren gaan tijdens apparaatuitwisselingen of ondersteuningsgesprekken waarvoor een apparaat opnieuw moet worden ingesteld.<br><br>Hoewel dit niet vereist is, wordt in Microsoft Managed Desktop ten zeerste aangeraden om te migreren van netwerkstations met kaarten naar de juiste cloudoplossing. Zie Kaartstations voorbereiden voor Beheerd bureaublad van [Microsoft voor meer informatie](mapped-drives.md)

Wanneer u klaar bent om aan de slag te gaan met Microsoft Managed Desktop, neem dan contact op met uw Microsoft Account Manager. 

## <a name="more-about-licenses"></a>Meer informatie over licenties

Voor Microsoft Managed Desktop zijn bepaalde licentieopties vereist om te kunnen functioneren. Zie [Microsoft Managed Desktop-technologieën](../intro/technologies.md) voor informatie over hoe deze licenties worden gebruikt.

> [!TIP]
> Als u deze licentieopties wilt toewijzen aan specifieke gebruikers, raden we u aan te profiteren van de groepslicentiefunctie [van](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) Azure Active Directory.

- Azure Active Directory Premium P1
- Microsoft Intune 
- Windows 10 Enterprise  
- Microsoft Defender voor Eindpunt
- Microsoft 365-apps voor ondernemingen
- Microsoft Teams
- [SharePoint Online, abonnement 2](https://www.microsoft.com/microsoft-365/sharepoint/compare-sharepoint-plans)
- [Exchange Online Abonnement 2](https://www.microsoft.com/microsoft-365/exchange/compare-microsoft-exchange-online-plans) 


> [!TIP]
> Uw Microsoft Account Manager helpt u bij het controleren van uw huidige licenties en serviceplannen en het meest efficiënte pad voor u om extra licenties of serviceplannen te krijgen die u nodig hebt, zonder dubbel werk te hoeven uitvoeren.

## <a name="steps-to-get-ready"></a>Stappen om u klaar te maken

1. Controleer [Vereisten voor Microsoft Managed Desktop](prerequisites.md). (Dit artikel)
2. Gebruik [gereedheidsbeoordelingshulpmiddelen.](readiness-assessment-tool.md)
3. [Vereisten voor gast-accounts](guest-accounts.md)
4. [Netwerkconfiguratie voor Microsoft Managed Desktop](network.md)
5. [Certificaten en netwerkprofielen voorbereiden voor Microsoft Managed Desktop](certs-wifi-lan.md)
6. [Toegang voorbereiden tot on-premises bronnen voor Microsoft Managed Desktop](authentication.md)
7. [Apps in Microsoft Managed Desktop](apps.md)
8. [Toegewezen stations voorbereiden voor Microsoft Managed Desktop](mapped-drives.md)
9. [Printbronnen voorbereiden voor Microsoft Managed Desktop](printing.md)
