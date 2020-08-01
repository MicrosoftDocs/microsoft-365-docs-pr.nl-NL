---
title: Technologieën in Microsoft Managed Desktop
description: In dit onderwerp worden de technologieën en apps weergegeven die worden gebruikt in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1f82c339e8cbe4426c87eae045107d26201b0025
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530017"
---
# <a name="microsoft-managed-desktop-technologies"></a>Technologieën in Microsoft Managed Desktop

In dit onderwerp worden de technologieën en apps weergegeven die worden gebruikt in Microsoft Managed Desktop.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise-licenties zijn vereist voor alle Microsoft Managed Desktop-gebruikers. Zie [Vereisten voor Microsoft Managed Desktop voor](../get-ready/prerequisites.md)meer informatie over licentievereisten voor de service.

In dit onderwerp worden de componenten samengevat die zijn opgenomen in de vereiste Enterprise-licenties, met een beschrijving van hoe de service elk onderdeel gebruikt met Microsoft Managed Desktop-apparaten. Specifieke rollen en verantwoordelijkheden voor elk gebied worden beschreven in de documentatie van Microsoft Managed Desktop. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 of E5
 |
 --- | ---
Microsoft 365-apps voor bedrijven (64-bits) | Deze Office-toepassingen worden verzonden met het apparaat: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype voor Bedrijven, OneNote.<br><br>De 64-bits volledige versies van Microsoft Project en Microsoft Visio zijn niet inbegrepen. Aangezien de installatie van deze toepassingen echter afhankelijk is van de Microsoft 365-apps voor bedrijfsinstallatie, heeft Microsoft Managed Desktop standaard Microsoft Intune-implementaties en beveiligingsgroepen gemaakt die u vervolgens gebruiken om deze toepassingen te implementeren voor gelicentieerde eindgebruikers. Zie [Microsoft Project of Microsoft Visio installeren op Microsoft Managed Desktop-apparaten voor](../get-started/project-visio.md)meer informatie.
OneDrive voor Bedrijven |Azure Active Directory Single Sign On is ingeschakeld voor eindgebruikers bij het eerste inloggen bij OneDrive voor Bedrijven.<br><br>Bekende mapomleiding voor mappen 'Bureaublad', 'Document' en 'Afbeeldingen' is inbegrepen; ingeschakeld en geconfigureerd door Microsoft Managed Desktop. 
Apps opslaan |    Microsoft Sway en Power BI worden niet met het apparaat verzonden. Deze apps zijn beschikbaar om te downloaden in de Microsoft Store.
Win32-toepassingen |    Teams worden niet met het apparaat verzonden, maar worden verpakt en geleverd door Microsoft voor Microsoft Managed Desktop-apparaten. Azure Information Protection Client wordt niet verzonden met het apparaat, maar u deze pakket voor implementatie. 
Webtoepassingen |  Yammer, Office in een browser, Delve, Flow, StaffHub, PowerApps en Planner worden niet met het apparaat verzonden. Gebruikers hebben toegang tot de webversie van deze toepassingen met een browser.


## <a name="windows-10-enterprise-e3-or-e5"></a>Windows 10 Enterprise E3 of E5

 |
 --- | ---
Toepassingsvirtualisatie (App-V) |    Klanten kunnen App-V-pakketten implementeren met behulp van de Intune Win32-appbeheerclient.
Microsoft Defender Advanced Threat Protection |  Microsoft Managed Desktop gebruikt dit om de beveiliging van apparaten te controleren. 

## <a name="enterprise-mobility--security-e5"></a>Bedrijfsmobiliteit + Beveiliging E5

 |
 --- | ---
Bedrijfsmobiliteit + Beveiliging E3<br>Azure Active Directory Premium P2 |    U alle functies van Enterprise Mobility + Security E3 en Azure Active Directory Premium P2 gebruiken om MDM-apparaten te beheren.
Microsoft Cloud App Security |  U deze optionele functie gebruiken met Microsoft Managed Desktop.
Azure Information Protection P2  | U deze optionele functie gebruiken met Microsoft Managed Desktop.
