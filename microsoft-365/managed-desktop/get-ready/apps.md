---
title: Apps in Microsoft Managed Desktop
description: Hier wordt uitgelegd hoe apps worden verwerkt, inclusief hoe u ze kunt verpakken, implementeren en ondersteunen.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 571acc9c240fc0243998050ac3013258a2f85a3e
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2021
ms.locfileid: "52028942"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Apps in Microsoft Managed Desktop

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>Apps in het algemeen

Microsoft bevat bepaalde belangrijke apps samen met de Microsoft 365 E3- of E5-licentie die nodig is om deel te nemen aan Microsoft Managed Desktop. Hoewel we deze apps leveren, hebt u echter nog steeds bepaalde verantwoordelijkheden en acties die u moet uitvoeren.

U kunt ook extra niet-Microsoft-apps implementeren voor uw gebruikers voor selfservice via de bedrijfsportal of een vereiste achtergrondinstallatie, allemaal met de implementatiepijplijn van Microsoft Intune. 

## <a name="apps-provided-by-microsoft"></a>Apps van Microsoft

Inbegrepen bij uw Microsoft Managed Desktop-licentie zijn 64-bits versies van de apps in de Microsoft 365 Apps voor enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype voor Bedrijven en OneNote.) Klik-en-Run-versies van Microsoft Project  en Visio zijn niet standaard opgenomen, maar u kunt ze wel vragen om ze toe te voegen. Zie Microsoft Project of Microsoft Visio installeren op [Microsoft Managed Desktop-apparaten](../get-started/project-visio.md)voor meer informatie over deze apps.

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Wat Microsoft doet om de apps die we bieden te ondersteunen

Microsoft biedt volledige service voor de implementatie, update en ondersteuning voor de meegeleverde Microsoft 365 Apps voor enterprise-apps. Klik-en-Run-versies van Microsoft Project  en Visio zijn standaard niet opgenomen, maar Microsoft Managed Desktop biedt implementatiegroepen waarmee uw IT-beheerder licenties kan beheren en deze toepassingen op de juiste manier voor uw organisatie kan implementeren. Microsoft ondersteunt gebruikers van deze toepassingen via de ondersteuningskanalen voor Microsoft Managed Desktop.

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>Wat u moet doen om de apps te ondersteunen die we bieden

Er zijn nog bepaalde dingen die u met deze apps moet doen:

- **Licenties toewijzen:** u bent verantwoordelijk voor het verkrijgen en toewijzen van de juiste licenties aan gebruikers voor Microsoft 365 Apps voor ondernemingen.
- **Gebruikers toevoegen aan beveiligingsgroepen:** als u Microsoft Project of Visio gebruikt, moet uw IT-beheerder deze gebruikers toevoegen aan de juiste implementatiegroepen. IT-beheerders zijn ook verantwoordelijk voor het terugvorderen van licenties van deze gebruikers als ze het bedrijf verlaten.
- **Microsoft 365-invoegtoepassingen** implementeren: als u invoegtoepassingen nodig hebt voor een van de Microsoft 365-apps voor enterprise-apps, implementeert u deze centraal, net als elke andere Windows 32-app. 

## <a name="apps-you-provide"></a>Apps die u verstrekt

U hebt waarschijnlijk andere apps die u nodig hebt voor uw bedrijfsactiviteiten. Deze apps kunnen alleen worden geïmplementeerd op Microsoft Managed Desktop-apparaten met behulp van de implementatiepijplijn van Microsoft Intune. Volg de stappen in Apps implementeren op Microsoft Managed Desktop-apparaten voor meer informatie over [toepassingsimplementatie.](../get-started/deploy-apps.md)

### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Uw eigen apps voorbereiden voor opname in Microsoft Managed Desktop
Controleer uw apps en controleer:

- Geen van de apps is verboden of heeft beperkt gedrag, zoals beschreven in [microsoft Managed Desktop-appvereisten.](../service-description/mmd-app-requirements.md)
- Apps moeten klaar zijn voor beheer door Microsoft Intune. Zie Implementatie van [Windows 10-apps met Microsoft Intune](/intune/apps-windows-10-app-deploy) en Apps toevoegen aan Microsoft [Intune](/intune/apps-add)voor meer informatie over dit onderwerp.
- Andere vereisten voor het vooraf verpakken, zoals het verstrekken van licentiesleutels, het akkoord met licentievoorwaarden en het vooraf instellen van serververbindingen.

## <a name="steps-to-get-ready"></a>Stappen om u klaar te maken

1. Controleer [Vereisten voor Microsoft Managed Desktop](prerequisites.md).
2. Gebruik [gereedheidsbeoordelingshulpmiddelen.](readiness-assessment-tool.md)
3. [Vereisten voor gast-accounts](guest-accounts.md)
4. [Netwerkconfiguratie voor Microsoft Managed Desktop](network.md)
5. [Certificaten en netwerkprofielen voorbereiden voor Microsoft Managed Desktop](certs-wifi-lan.md)
6. [Toegang voorbereiden tot on-premises bronnen voor Microsoft Managed Desktop](authentication.md)
7. [Apps in Microsoft Managed Desktop](apps.md) (Dit artikel)
8. [Toegewezen stations voorbereiden voor Microsoft Managed Desktop](mapped-drives.md)
9. [Afdrukbronnen voorbereiden voor Microsoft Managed Desktop](printing.md)
