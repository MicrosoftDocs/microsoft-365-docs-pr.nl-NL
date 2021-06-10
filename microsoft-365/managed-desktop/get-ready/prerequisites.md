---
title: Vereisten voor Microsoft Managed Desktop
description: Licenties, Azure-accounts, verificatie-instellingen en Microsoft 365 instellingen die u wilt instellen voordat u zich inschrijft in Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: e4469d8abcfa8308c64e2efa7f7dc4f0156e5718
ms.sourcegitcommit: b6763a8ab240fbdd56078a7c9452445d0c4b9545
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/22/2021
ms.locfileid: "51957525"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Vereisten voor Microsoft Managed Desktop

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

In dit onderwerp worden de infrastructuurvereisten beschreven die u moet voldoen om succes met Microsoft Managed Desktop. 


Gebied | Details van vereisten
--- | ---
Licenties |Microsoft Managed Desktop vereist dat de licentie Microsoft 365 E3 microsoft Defender voor eindpunten (of equivalenten) is toegewezen aan uw gebruikers.<br>Zie Meer informatie over licenties [in](#more-about-licenses) dit onderwerp voor meer informatie over de specifieke serviceplannen.<br>Zie Microsoft 365 licenties voor meer informatie over beschikbare [licenties.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans)
Connectiviteit |  Alle Microsoft Managed Desktop apparaten vereisen verbinding met een groot aantal Microsoft-service-eindpunten vanuit het bedrijfsnetwerk.<br><br>Zie Netwerkconfiguratie voor de volledige lijst met vereiste IPs en [URL's.](../get-ready/network.md) 
Microsoft Azure Active Directory |    Azure Active Directory (Azure AD) moet de bron van autoriteit zijn voor alle gebruikersaccounts of gebruikersaccounts moeten worden gesynchroniseerd vanuit on-premises Active Directory met behulp van de meest recente ondersteunde versie van Azure AD-Verbinding maken.<br><br>[Enterprise State Roaming](/azure/active-directory/devices/enterprise-state-roaming-overview) moet zijn ingeschakeld voor Microsoft Managed Desktop gebruikers.<br><br>Zie [Azure AD-Verbinding maken.](/azure/active-directory/hybrid/whatis-azure-ad-connect)<br><br>Zie [Azure AD Verbinding maken:Version release history](/azure/active-directory/hybrid/reference-connect-version-history)voor meer informatie over ondersteunde Azure AD-Verbinding maken-versies.
Verificatie |    Als Azure AD niet de bron is van primaire verificatie voor gebruikersaccounts, moet u een van deze gegevens configureren in Azure AD Verbinding maken:<br>- Wachtwoordhashsynchronisatie<br>- Pass-through-verificatie<br>- Een externe identiteitsprovider (inclusief Windows Server ADFS en niet-Microsoft-id's) die is geconfigureerd om te voldoen aan de vereisten voor Azure AD-integratie. Zie de [richtlijnen](https://www.microsoft.com/download/details.aspx?id=56843) voor meer informatie. <br><br>Wanneer u verificatieopties instelt met Azure AD Verbinding maken, wordt ook wachtwoordschrijven aanbevolen. Zie Wachtwoord [terugschrijven voor meer informatie.](/azure/active-directory/authentication/howto-sspr-writeback) <br><br>Als een externe identiteitsprovider wordt geïmplementeerd, moet u de oplossing valideren:<br>- Voldoet aan de integratievereisten voor Azure AD<br>- Ondersteunt Azure AD Voorwaardelijke toegang, waarmee het Microsoft Managed Desktop apparaat compliancebeleid kan worden geconfigureerd<br>- Hiermee kunt u apparaten registreren en gebruiken Microsoft 365 services of functies die nodig zijn als onderdeel van Microsoft Managed Desktop <br><br>Zie Azure AD Verbinding maken aanmeldingsopties voor gebruikers voor meer informatie over [verificatieopties met Azure AD.](/azure/active-directory/connect/active-directory-aadconnect-user-signin)
Microsoft 365 | OneDrive voor Bedrijven moet zijn ingeschakeld voor Microsoft Managed Desktop gebruikers.<br><br>Hoewel het niet nodig is om u in te schrijven met Microsoft Managed Desktop, raden we ten zeerste aan dat de volgende services worden gemigreerd naar de cloud:<br>- E-mail: migreren naar postvakken in de cloud, Exchange online of configureren met Exchange Online Hybride met Exchange 2013 of hoger, on-premises.<br>- Bestanden en mappen: migreren naar OneDrive voor Bedrijven of SharePoint Online.<br>- Hulpprogramma's voor onlinesamenwerking: migreren naar Teams.
Apparaatbeheer | Microsoft Managed Desktop apparaten vereisen beheer met Microsoft Intune. Intune moet worden ingesteld als de autoriteit voor mobiel apparaatbeheer.<br><br>Zie voor meer informatie [Microsoft Intune.](https://www.microsoft.com/cloud-platform/microsoft-intune) 
Back-up en herstel van gegevens |  Microsoft Managed Desktop vereist dat bestanden worden gesynchroniseerd met OneDrive voor Bedrijven beveiliging. Bestanden die niet zijn gesynchroniseerd met OneDrive voor Bedrijven worden niet gegarandeerd door Microsoft Managed Desktop en kunnen verloren gaan tijdens apparaatuitwisselingen of ondersteuningsgesprekken waarvoor een apparaat opnieuw moet worden ingesteld.<br><br>Hoewel dit niet vereist is, Microsoft Managed Desktop u ten zeerste de migratie van netwerkstations in kaart gebracht naar de juiste cloudoplossing. Zie Kaartstations voorbereiden [voor](mapped-drives.md) Microsoft Managed Desktop

Wanneer u klaar bent om aan de slag te gaan met Microsoft Managed Desktop, neem dan contact op met uw Microsoft Account Manager. 

## <a name="more-about-licenses"></a>Meer informatie over licenties

Microsoft Managed Desktop vereist bepaalde licentieopties om te kunnen functioneren. Zie [Microsoft Managed Desktop technologieën voor](../intro/technologies.md) informatie over hoe deze licenties worden gebruikt.

> [!TIP]
> Als u deze licentieopties wilt toewijzen aan specifieke gebruikers, raden we u aan gebruik te maken van de groepslicentiefunctie [van](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) Azure Active Directory.

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

1. Controleer [Vereisten voor Microsoft Managed Desktop.](prerequisites.md) (Dit artikel)
2. Gebruik [gereedheidsbeoordelingshulpmiddelen.](readiness-assessment-tool.md)
3. [Vereisten voor gast-accounts](guest-accounts.md)
4. [Netwerkconfiguratie voor Microsoft Managed Desktop](network.md)
5. [Certificaten en netwerkprofielen voorbereiden voor Microsoft Managed Desktop](certs-wifi-lan.md)
6. [Toegang voorbereiden tot on-premises bronnen voor Microsoft Managed Desktop](authentication.md)
7. [Apps in Microsoft Managed Desktop](apps.md)
8. [Toegewezen stations voorbereiden voor Microsoft Managed Desktop](mapped-drives.md)
9. [Afdrukbronnen voorbereiden voor Microsoft Managed Desktop](printing.md)
