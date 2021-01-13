---
title: Technologieën in Microsoft Managed Desktop
description: Dit artikel bevat een overzicht van de technologieën en apps die worden gebruikt in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: cb368939e87ddbbfc8f5386c6fc5d6bff110a7ec
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840899"
---
# <a name="microsoft-managed-desktop-technologies"></a>Technologieën in Microsoft Managed Desktop

Dit artikel bevat een overzicht van de technologieën en apps die worden gebruikt in Microsoft Managed Desktop.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Voor alle door Microsoft beheerde bureaubladgebruikers is Microsoft 365 Enterprise Licensing vereist. Zie [vereisten voor Microsoft Managed Desktop](../get-ready/prerequisites.md)voor meer informatie over licentievereisten voor de service.

Dit artikel bevat een overzicht van de onderdelen die deel uitmaken van de vereiste Enterprise-licenties, met een beschrijving van de manier waarop de service elk onderdeel gebruikt met beheerde bureaublad apparaten van Microsoft. Voor elk gebied gelden specifieke rollen en verantwoordelijkheden in het Microsoft-beheer document. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 of E5
 |
 --- | ---
Microsoft 365-apps voor Enterprise (64-bits) | Deze Office-toepassingen worden met het apparaat verzonden: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype voor bedrijven, OneNote.<br><br>De 64-bits volledige versies van Microsoft Project en Microsoft Visio zijn niet opgenomen. Aangezien de installatie van deze toepassingen afhankelijk is van de installatie van de Microsoft 365-apps voor de Enterprise-installatie, heeft Microsoft Managed Desktop standaard Microsoft intune-implementaties en beveiligingsgroepen gemaakt, die u vervolgens kunt gebruiken om deze toepassingen te implementeren voor gelicentieerde gebruikers. Zie [Microsoft Project of Microsoft Visio installeren op door Microsoft beheerde bureaublad apparaten](../get-started/project-visio.md)voor meer informatie.
OneDrive |Azure Active Directory eenmalige aanmelding is ingeschakeld voor gebruikers wanneer ze zich de eerste keer aanmelden bij OneDrive.<br><br>Bekende Mapomleiding voor ' Bureaublad ', ' document ' en ' afbeeldingen ' bevat mappen. is ingeschakeld en geconfigureerd voor Microsoft Managed Desktop.
Store-apps |    Microsoft Sway en Power BI worden niet met het apparaat verzonden. U kunt deze apps downloaden in de Microsoft Store.
Win32-toepassingen |    Teams worden niet met het apparaat verzonden, maar wordt geleverd door Microsoft voor door Microsoft beheerde bureaublad apparaten. Azure Information Protection-client wordt niet met het apparaat verzonden, maar u kunt deze wel inpakken voor implementatie.
Webtoepassingen |  Yammer, Office in een browser, Delve, flow, StaffHub, PowerApps en planner worden niet met het apparaat verzonden. Gebruikers hebben toegang tot de webversie van deze toepassingen via een browser.


## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterprise E5 of E3 met Microsoft Defender voor eindpunt

 |
 --- | ---
Application Virtualization (app-V) |    Klanten kunnen app-V-pakketten implementeren met behulp van de intune Win32®-app voor app-beheer.
Microsoft Defender for Endpoint |    Microsoft Managed Desktop gebruikt dit product om beveiliging van apparaten te bewaken. 

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + beveiligings E3<br>Azure Active Directory Premium P2 |    U kunt alle functies voor Enterprise Mobility + Security E3 en Azure Active Directory Premium P2 gebruiken voor het beheren van MDM-apparaten.
Microsoft Cloud App Security |  U kunt deze optionele functie gebruiken bij Microsoft Managed Desktop.
Azure Information Protection P2  | U kunt deze optionele functie gebruiken bij Microsoft Managed Desktop.
