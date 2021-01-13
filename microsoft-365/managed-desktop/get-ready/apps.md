---
title: Apps in Microsoft Managed Desktop
description: In dit artikel wordt uitgelegd hoe apps worden afgehandeld, waaronder de manier waarop u ze kunt inpakken, implementeren en ondersteunen.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 20d68ec007ccda82816ad2288428016019f6d4b2
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840691"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Apps in Microsoft Managed Desktop

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>Apps in het algemeen

Microsoft omvat bepaalde belangrijke apps, met de Microsoft 365 E3-of E5-licentie die nodig is om deel te nemen aan Microsoft Managed Desktop. Ook al bieden we deze apps te bieden, maar u kunt nog wel bepaalde verantwoordelijkheden en acties uitvoeren.

U kunt ook extra niet-Microsoft-Apps implementeren voor uw gebruikers voor selfservice via de bedrijfs portal of een vereiste achtergrond installatie, allemaal met de implementatie pijplijn van Microsoft intune. Als u de expertise hebt, kunt u de benodigde apps migreren. u kunt ook, Microsoft Consulting Services (MCS) of niet-Microsoft-leveranciers helpen met een verpakking en migratieproject. Zie voor meer informatie over het werken met MCS [werken met Microsoft Consulting Services](apps-MCS.md).


## <a name="apps-provided-by-microsoft"></a>Apps van Microsoft

Inbegrepen in Microsoft beheerde bureaublad licentie zijn 64-bits versies van de apps in de Microsoft 365-apps voor Enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype voor bedrijven en OneNote). Klik-en-klaar-versies van Microsoft Project en Visio zijn standaard *niet* opgenomen, maar u kunt ze ook aanvragen om ze toe te voegen. Zie voor meer informatie over deze apps [Microsoft Project of Microsoft Visio installeren op op Microsoft beheerde bureaublad apparaten](../get-started/project-visio.md).

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Wat Microsoft biedt voor de ondersteuning van de door u verstrekte apps

Microsoft biedt volledige service voor de implementatie, update en ondersteuning voor de opgenomen Microsoft 365-apps voor Enterprise-apps. Klik-en-klaar-versies van Microsoft Project en Visio zijn *niet* standaard opgenomen, maar Microsoft Managed Desktop biedt implementatie groepen waarmee de IT-beheerder licenties kan beheren en deze toepassingen op de juiste wijze kan implementeren voor uw organisatie. Microsoft ondersteunt gebruikers van deze toepassingen via het ondersteunings kanaal van Microsoft beheerde bureaublad.

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>Wat u moet doen voor de ondersteuning van de door u verstrekte apps

U moet nog bepaalde dingen doen met deze apps:

- **Licenties toewijzen** : u bent verantwoordelijk voor het verkrijgen en toewijzen van de juiste licenties aan gebruikers voor microsoft 365-apps voor Enterprise.
- **Gebruikers toevoegen aan beveiligingsgroepen** : als u Microsoft Project of Visio gebruikt, moet uw IT-beheerder deze gebruikers toevoegen aan de juiste implementatie groepen. IT-beheerders zijn ook verantwoordelijk voor het opnieuw toewijzen van licenties van de gebruikers als ze het bedrijf blijven.
- **Invoegtoepassingen voor Microsoft 365 implementeren** : als u invoegtoepassingen nodig hebt voor een van de microsoft 365-apps voor Enterprise-apps, kunt u deze als volgt in een andere Windows 32-app implementeren. 

## <a name="apps-you-provide"></a>Apps die u verstrekt

U hebt waarschijnlijk andere apps nodig voor uw bedrijfsactiviteiten. Met de implementatie pijplijn van Microsoft intune kunt u alleen deze apps implementeren voor Microsoft Managed Desktop devices. Als de app dit nodig heeft, kunt u deze door een leverancier laten inpakken (een niet-Microsoft-leverancier of Microsoft Consulting Services (MCS)) of kunt u de middelen zelf inpakken. Vervolgens voegt u deze pakketten toe aan de Microsoft beheerde bureaublad Portal en wijst u ze toe aan Azure Active Directory-groepen om de implementatie te activeren. 

Als u momenteel uw apps implementeert met behulp van Microsoft endpoint Configuration Manager, kan Microsoft Managed Desktop u een query leveren om uw apps te beoordelen en erachter te komen welke de apps gereed zijn om te worden gemigreerd naar Microsoft intune en welke aanpassingen mogelijk zijn vereist.


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Uw eigen apps voorbereiden voor opname in Microsoft Managed Desktop
Controleer uw apps, Controleer het volgende:

- Geen van de apps is toegestaan of heeft beperkte werking, zoals wordt beschreven in de [vereisten voor Microsoft beheerde bureaubladtoepassing](https://aka.ms/app-req).
- Apps moeten worden beheerd door Microsoft intune. Zie [Windows 10 app Deployment met Microsoft intune](https://docs.microsoft.com/intune/apps-windows-10-app-deploy) en [apps toevoegen aan Microsoft intune](https://docs.microsoft.com/intune/apps-add)voor meer informatie over dit onderwerp.
- Andere vereisten voor de verpakking, zoals het verschaffen van licentiecodes, overeenkomst met licentievoorwaarden en vooraf ingestelde serververbindingen.

### <a name="decide-how-to-package-apps"></a>Bepalen hoe apps moeten worden verpakt

Voor sommige onafhankelijke software-uitgevers moet de app zijn verpakt voordat ze centraal worden geïmplementeerd. "Verpakking" betekent dat het installatieprogramma van de app is geconfigureerd met instellingen zoals licentiecodes, externe serverlocaties of bureaublad snel toetsen, zodat de app kan worden geïnstalleerd op de achtergrond.

U kunt op drie manieren uw apps bundelen: 


- U kunt zelf apps inpakken
- U kunt werken met een leverancier van niet Microsoft
- U kunt met MCS deelnemen aan uw apps. Werk samen met uw Microsoft-accountvertegenwoordiger. Zie [werken met Microsoft Consulting Services](apps-MCS.md)voor meer informatie.



## <a name="deploying-apps"></a>Apps implementeren

Welke methode u ook gebruikt om apps te bundelen, wanneer u klaar bent, kunt u de stappen in [apps implementeren voor Microsoft beheerde bureaublad apparaten](../get-started/deploy-apps.md)doen.


