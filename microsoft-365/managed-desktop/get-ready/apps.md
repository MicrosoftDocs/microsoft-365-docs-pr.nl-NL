---
title: Apps in Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: a24212cf69df50d00a32f17e8daf1939657dd602
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632849"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Apps in Microsoft Managed Desktop

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>Apps over het algemeen

Microsoft bevat bepaalde belangrijke apps samen met de Microsoft 365 E3- of E5-licentie die nodig is om deel te nemen aan Microsoft Managed Desktop. Hoewel we deze apps aanbieden, moet je nog steeds bepaalde verantwoordelijkheden en acties voltooien.

U ook extra niet-Microsoft-apps implementeren voor zelfbediening voor uw eindgebruikers via de bedrijfsportal of een vereiste achtergrondinstallatie, allemaal via de implementatiepijplijn van Microsoft Intune. Als je de expertise hebt, kun je die apps migreren die je zelf nodig hebt; Als alternatief helpen Microsoft Consulting Services (MCS) of niet-Microsoft-leveranciers u graag met een verpakkings- en migratieproject. Zie Werken met Microsoft Consulting [Services](apps-MCS.md)voor meer informatie over het werken met MCS.


## <a name="apps-provided-by-microsoft"></a>Apps van Microsoft

Inbegrepen bij uw Microsoft Managed Desktop-licentie zijn 64-bits versies van de apps in de Microsoft 365 Apps for enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype voor Bedrijven en OneNote.) Klik-en-Klaar-versies van Microsoft Project en Visio zijn *niet* standaard opgenomen, maar u ze wel aanvragen om te worden toegevoegd. Zie Microsoft Project of [Microsoft Visio installeren op Microsoft Managed Desktop-apparaten](../get-started/project-visio.md)voor meer informatie over deze apps.

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Wat Microsoft doet om de apps die we aanbieden te ondersteunen

Microsoft biedt volledige service voor de implementatie, update en ondersteuning voor de meegeleverde Microsoft 365 Apps voor bedrijfsapps. Click-to-Run-versies van Microsoft Project en Visio zijn *niet* standaard opgenomen, maar Microsoft Managed Desktop biedt implementatiegroepen waarmee uw IT-beheerder licenties kan beheren en deze toepassingen op de juiste manier voor uw organisatie kan implementeren. Microsoft ondersteunt eindgebruikers van deze toepassingen via de ondersteuningskanalen van Microsoft Managed Desktop.

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>Wat u moet doen om de apps die wij aanbieden te ondersteunen

Er zijn nog steeds bepaalde dingen die je moet doen met deze apps:

- **Licenties toewijzen** : u bent verantwoordelijk voor het verkrijgen en toewijzen van de juiste licenties aan eindgebruikers voor Microsoft 365 Apps voor bedrijven.
- **Gebruikers toevoegen aan beveiligingsgroepen** - Als u Microsoft Project of Visio gebruikt, moet uw IT-beheerder deze gebruikers toevoegen aan de juiste implementatiegroepen. IT-beheerders zijn ook verantwoordelijk voor het terugvorderen van licenties van die gebruikers als ze het bedrijf verlaten.
- **Microsoft 365-invoegtoepassingen implementeren** - Als u invoegtoepassingen nodig hebt voor een van de Microsoft 365-apps voor bedrijfsapps, implementeert u deze centraal, net als elke andere Windows 32-app. 

## <a name="apps-you-provide"></a>Apps die u aanbiedt

Natuurlijk hebt u waarschijnlijk een aantal andere apps die u nodig hebt voor uw bedrijfsvoering. Deze kunnen alleen worden geïmplementeerd op Microsoft Managed Desktop-apparaten met behulp van de implementatiepijplijn van Microsoft Intune. Als de app het nodig heeft, u ze laten verpakken door een leverancier (wat een niet-Microsoft-leverancier of Microsoft Consulting Services (MCS) kan zijn of als u de middelen hebt, u ze zelf verpakken. Vervolgens voegt u deze pakketten toe aan de Microsoft Managed Desktop-portal en wijst u ze toe aan Azure Active Directory-groepen om de implementatie te activeren. 

Als u uw apps momenteel implementeert met Microsoft Endpoint Configuration Manager, kan Microsoft Managed Desktop u een query bieden om uw apps te beoordelen en te ontdekken welke apps klaar zijn om te migreren naar Microsoft Intune en welke apps mogelijk enige aanpassing vereisen.


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Uw eigen apps voorbereiden op opname in Microsoft Managed Desktop
Bekijk uw apps en controleer:

- Geen van de apps is verboden of heeft beperkt gedrag, zoals beschreven in [de vereisten van microsoft Managed Desktop-apps.](https://aka.ms/app-req)
- Apps moeten klaar zijn voor beheer door Microsoft Intune. Zie [Windows 10-app-implementatie met Microsoft Intune](https://docs.microsoft.com/intune/apps-windows-10-app-deploy) en [Apps toevoegen aan Microsoft Intune](https://docs.microsoft.com/intune/apps-add)voor meer informatie hierover.
- Andere vereisten voor het vooraf verpakken, zoals het verstrekken van licentiesleutels, toestemming voor licentievoorwaarden en het vooraf instellen van serververbindingen.

### <a name="decide-how-to-package-apps"></a>Bepalen hoe u apps verpakt

Sommige onafhankelijke softwareleveranciers vereisen mogelijk dat uw apps worden verpakt voordat ze centraal worden geïmplementeerd. "Verpakking" betekent dat het installatieprogramma van de app is geconfigureerd met instellingen zoals licentiesleutels, externe serverlocaties of bureaubladsneltoetsen, zodat de app op de achtergrond kan worden geïnstalleerd.

Er zijn drie opties om uw apps verpakt te krijgen: 


- U apps zelf verpakken
- U werken met een niet-Microsoft-leverancier
- U contact opnemen met MCS om uw apps te verpakken. Werk samen met uw Microsoft-accountvertegenwoordiger. Zie [Werken met Microsoft Consulting Services](apps-MCS.md)voor meer informatie.







## <a name="deploying-apps"></a>Apps implementeren

Welke methode u ook gebruikt om apps te verpakken, zodra deze is voltooid, bent u klaar om de stappen in [Apps implementeren naar Microsoft Managed Desktop-apparaten te](../get-started/deploy-apps.md)volgen.


