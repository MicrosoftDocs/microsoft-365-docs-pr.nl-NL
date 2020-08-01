---
title: Apps in Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: bc7192cf82c825a13780567663695d96a760b3ef
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530101"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Apps in Microsoft Managed Desktop

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>Apps in het algemeen

Microsoft bevat bepaalde belangrijke apps samen met de Microsoft 365 E3- of E5-licentie die nodig is om deel te nemen aan Microsoft Managed Desktop. Hoewel we deze apps aanbieden, heb je nog steeds bepaalde verantwoordelijkheden en acties om te voltooien.

U ook extra niet-Microsoft-apps implementeren voor uw eindgebruikers voor selfservice via de Bedrijfsportal of een vereiste achtergrondinstallatie, allemaal met behulp van de implementatiepijplijn van Microsoft Intune. Als je de expertise hebt, kun je de apps migreren die je zelf nodig hebt; Als alternatief helpen Microsoft Consulting Services (MCS) of niet-Microsoft-leveranciers u graag met een verpakkings- en migratieproject. Zie Werken met Microsoft Consulting [Services](apps-MCS.md)voor meer informatie over het werken met MCS.


## <a name="apps-provided-by-microsoft"></a>Apps van Microsoft

Inbegrepen bij uw Microsoft Managed Desktop-licentie zijn 64-bits versies van de apps in de Microsoft 365 Apps for enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype voor Bedrijven en OneNote.) Click-to-Run-versies van Microsoft Project en Visio zijn *niet* standaard inbegrepen, maar u ze wel aanvragen om ze toe te voegen. Zie Microsoft Project of [Microsoft Visio installeren op Microsoft Managed Desktop-apparaten voor](../get-started/project-visio.md)meer informatie over deze apps.

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Wat Microsoft doet om de apps die we leveren te ondersteunen

Microsoft biedt volledige service voor de implementatie, update en ondersteuning voor de meegeleverde Microsoft 365-apps voor bedrijfsapps. Click-to-Run-versies van Microsoft Project en Visio worden *niet* standaard opgenomen, maar Microsoft Managed Desktop biedt implementatiegroepen waarmee uw IT-beheerder licenties kan beheren en deze toepassingen op de juiste manier voor uw organisatie kan implementeren. Microsoft ondersteunt eindgebruikers van deze toepassingen via de ondersteuningskanalen voor Microsoft Managed Desktop.

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>Wat u moet doen om de apps te ondersteunen die we aanbieden

Er zijn nog steeds bepaalde dingen die je moet doen met deze apps:

- **Licenties toewijzen** - U bent verantwoordelijk voor het verkrijgen en toewijzen van de juiste licenties aan eindgebruikers voor Microsoft 365 Apps voor ondernemingen.
- **Gebruikers toevoegen aan beveiligingsgroepen** : als u Microsoft Project of Visio gebruikt, moet uw IT-beheerder deze gebruikers toevoegen aan de juiste implementatiegroepen. IT-beheerders zijn ook verantwoordelijk voor het terugvorderen van licenties van die gebruikers als ze het bedrijf verlaten.
- **Microsoft 365-invoegtoepassingen** implementeren - Als u invoegtoepassingen nodig hebt voor een van de Microsoft 365-apps voor bedrijfsapps, implementeert u deze centraal, net als elke andere Windows 32-app. 

## <a name="apps-you-provide"></a>Apps die u opsziet

Natuurlijk heb je waarschijnlijk een aantal andere apps die je nodig hebt voor je bedrijfsvoering. Deze kunnen alleen worden geïmplementeerd op Microsoft Managed Desktop-apparaten met behulp van de implementatiepijplijn van Microsoft Intune. Als de app deze nodig heeft, u ze laten verpakken door een leverancier (wat een niet-Microsoft-leverancier of Microsoft Consulting Services (MCS) kan zijn of als u de middelen hebt, u ze zelf verpakken. U voegt deze pakketten vervolgens toe aan de Microsoft Managed Desktop-portal en wijst ze toe aan Azure Active Directory-groepen om de implementatie te activeren. 

Als u uw apps momenteel implementeert met Microsoft Endpoint Configuration Manager, kan Microsoft Managed Desktop u een query geven om uw apps te beoordelen en te ontdekken welke apps klaar zijn om te migreren naar Microsoft Intune en welke mogelijk enige aanpassing vereisen.


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Uw eigen apps voorbereiden op opname in Microsoft Managed Desktop
Bekijk uw apps en controleer:

- Geen van de apps is verboden of heeft beperkt gedrag, zoals beschreven in [microsoft Managed Desktop-appvereisten.](https://aka.ms/app-req)
- Apps moeten klaar zijn voor beheer door Microsoft Intune. Zie de implementatie van [windows 10-apps met Microsoft Intune](https://docs.microsoft.com/intune/apps-windows-10-app-deploy) en [Apps toevoegen aan Microsoft Intune](https://docs.microsoft.com/intune/apps-add)voor meer informatie.
- Andere vereisten voor het verpakken, zoals het verstrekken van licentiesleutels, overeenkomst met licentievoorwaarden en vooraf in te stellen serververbindingen.

### <a name="decide-how-to-package-apps"></a>Bepalen hoe u apps verpakt

Sommige onafhankelijke softwareleveranciers vereisen mogelijk dat uw apps worden verpakt voordat ze centraal worden geïmplementeerd. 'Verpakking' betekent dat het installatieprogramma van de app is geconfigureerd met instellingen zoals licentiesleutels, externe serverlocaties of bureaubladsnelkoppelingen, zodat de app op de achtergrond kan worden geïnstalleerd.

Er zijn drie opties om uw apps verpakt te krijgen: 


- U apps zelf verpakken
- U werken met een niet-Microsoft-leverancier
- U contact opnemen met MCS om uw apps te verpakken. Werk met uw Microsoft-accountvertegenwoordiger. Zie [Werken met Microsoft Consulting Services](apps-MCS.md)voor meer informatie.







## <a name="deploying-apps"></a>Apps implementeren

Welke methode u ook gebruikt om apps verpakt te krijgen, zodra dat is voltooid, bent u klaar om de stappen in [Apps implementeren naar Microsoft Managed Desktop-apparaten te](../get-started/deploy-apps.md)volgen.


