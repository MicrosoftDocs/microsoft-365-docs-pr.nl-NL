---
title: Microsoft Managed Desktop-technologieën
description: In dit onderwerp worden de technologieën en apps weergegeven die worden gebruikt in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8a86220e7fcfe4c2e788b28842c77d238d98fda4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636194"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft Managed Desktop-technologieën

In dit onderwerp worden de technologieën en apps weergegeven die worden gebruikt in Microsoft Managed Desktop.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise-licenties zijn vereist voor alle Microsoft Managed Desktop-gebruikers. Zie [Voorwaarden voor Microsoft Managed Desktop voor](../get-ready/prerequisites.md)meer informatie over licentievereisten voor de service.

In dit onderwerp worden de onderdelen samengevat die zijn opgenomen in de vereiste Enterprise-licenties, met een beschrijving van hoe de service elk onderdeel gebruikt met Microsoft Managed Desktop-apparaten. Specifieke rollen en verantwoordelijkheden voor elk gebied worden gedetailleerd beschreven in de documentatie van Microsoft Managed Desktop. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 of E5
 |
 --- | ---
Microsoft 365 Apps for Enterprise (64-bits) | Deze Office-toepassingen worden verzonden met het apparaat: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype voor Bedrijven, OneNote.<br><br>De 64-bits volledige versies van Microsoft Project en Microsoft Visio zijn niet inbegrepen. Aangezien de installatie van deze toepassingen echter afhankelijk is van de installatie van Microsoft 365 Apps voor bedrijfsinstallaties, heeft Microsoft Managed Desktop standaard Microsoft Intune-implementaties en beveiligingsgroepen gemaakt die u vervolgens gebruiken om deze toepassingen te implementeren voor gelicentieerde eindgebruikers. Zie [Microsoft Project of Microsoft Visio installeren op Microsoft Managed Desktop-apparaten](../get-started/project-visio.md)voor meer informatie.
OneDrive voor Bedrijven |Azure Active Directory Single Sign On is ingeschakeld voor eindgebruikers bij het eerste aanmelden bij OneDrive voor Bedrijven.<br><br>Bekende mapomleiding voor mappen 'Bureaublad', 'Document' en 'Afbeeldingen' is inbegrepen. ingeschakeld en geconfigureerd door Microsoft Managed Desktop. 
Apps opslaan |    Microsoft Sway en Power BI worden niet met het apparaat verzonden. Deze apps zijn beschikbaar om te downloaden in de Microsoft Store.
Win32-toepassingen |    Teams worden niet met het apparaat verzonden, maar wordt verpakt en geleverd door Microsoft voor Microsoft Managed Desktop-apparaten. Azure Information Protection Client wordt niet verzonden met het apparaat, maar u dit laten verpakken voor implementatie. 
Webtoepassingen |  Yammer, Office in een browser, Delve, Flow, StaffHub, PowerApps en Planner worden niet met het apparaat verzonden. Gebruikers hebben toegang tot de webversie van deze toepassingen met een browser.


## <a name="windows-10-enterprise-e3-or-e5"></a>Windows 10 Enterprise E3 of E5

 |
 --- | ---
Toepassingsvirtualisatie (App-V) |    Klanten kunnen App-V-pakketten implementeren via de Intune Win32-appmanagementclient.
Microsoft Defender Advanced Threat Protection |  Microsoft Managed Desktop gebruikt dit om de beveiliging van apparaten te controleren. 

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Beveiliging E5

 |
 --- | ---
Enterprise Mobility + Beveiliging E3<br>Azure Active Directory Premium P2 |    U alle functies van Enterprise Mobility + Security E3 en Azure Active Directory Premium P2 gebruiken om MDM-apparaten te beheren.
Microsoft Cloud App Security |  U deze optionele functie gebruiken met Microsoft Managed Desktop.
Azure Information Protection P2  | U deze optionele functie gebruiken met Microsoft Managed Desktop.
