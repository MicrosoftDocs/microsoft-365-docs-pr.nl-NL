---
title: Apps in Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: adb6423d5c014b5f02fc272f9653abebc14cf543
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/07/2020
ms.locfileid: "42805876"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Apps in Microsoft Managed Desktop

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>Apps in het algemeen

Microsoft bevat bepaalde belangrijke apps, samen met de Microsoft 365 E3- of E5-licentie die nodig is om deel te nemen aan Microsoft Managed Desktop. Hoewel we deze apps aanbieden, hebt u nog steeds bepaalde verantwoordelijkheden en acties om te voltooien.

U ook extra niet-Microsoft-apps implementeren voor uw eindgebruikers voor selfservice via de Bedrijfsportal of een vereiste achtergrondinstallatie, die allemaal de implementatiepijplijn van Microsoft Intune gebruikt. Als je de expertise hebt, kun je die apps die je nodig hebt zelf migreren; Als alternatief helpen Microsoft Consulting Services (MCS) of niet-Microsoft-leveranciers u graag met een verpakkings- en migratieproject. Zie Werken met Microsoft Consulting [Services](apps-MCS.md)voor meer informatie over het werken met MCS.


## <a name="apps-provided-by-microsoft"></a>Apps van Microsoft

Inbegrepen bij uw Microsoft Managed Desktop-licentie zijn 64-bits versies van de apps in de Office 365 ProPlus Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype voor Bedrijven en OneNote.) Klik-en-klaarversies van Microsoft Project en Visio zijn *niet* standaard opgenomen, maar u ze aanvragen om te worden toegevoegd. Zie Microsoft Project of [Microsoft Visio installeren op Microsoft Managed Desktop-apparaten](../get-started/project-visio.md)voor meer informatie over deze apps.

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Wat Microsoft doet om de apps die we bieden te ondersteunen

Microsoft biedt volledige service voor de implementatie, update en ondersteuning voor de meegeleverde Office 365 ProPlus-apps. Klik-en-klaarversies van Microsoft Project en Visio zijn *niet* standaard opgenomen, maar Microsoft Managed Desktop biedt implementatiegroepen waarmee uw IT-beheerder licenties kan beheren en deze toepassingen op de juiste manier voor uw organisatie kan implementeren. Microsoft ondersteunt eindgebruikers van deze toepassingen via de ondersteuningskanalen van Microsoft Managed Desktop.

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>Wat u moet doen om de apps die wij bieden te ondersteunen

Er zijn nog bepaalde dingen die je moet doen met deze apps:

- **Licenties toewijzen** - U bent verantwoordelijk voor het verkrijgen en toewijzen van de juiste licenties aan eindgebruikers voor Office 365 ProPlus.
- **Gebruikers toevoegen aan beveiligingsgroepen** - Als u Microsoft Project of Visio gebruikt, moet uw IT-beheerder deze gebruikers toevoegen aan de juiste implementatiegroepen. IT-beheerders zijn ook verantwoordelijk voor het terugvorderen van licenties van die gebruikers als ze het bedrijf verlaten.
- **Office 365-addons implementeren** - Als u addons nodig hebt voor een van de Office 365 ProPlus-apps, implementeert u ze centraal, net als elke andere Windows 32-app. 

## <a name="apps-you-provide"></a>Apps die u opgeeft

Natuurlijk hebt u waarschijnlijk een aantal andere apps die u nodig hebt voor uw bedrijfsactiviteiten. Deze kunnen alleen worden geïmplementeerd op Microsoft Managed Desktop-apparaten met behulp van de implementatiepijplijn van Microsoft Intune. Als de app het nodig heeft, u ze laten verpakken door een leverancier (wat een niet-Microsoft-leverancier of Microsoft Consulting Services (MCS)) kan zijn of als u de middelen hebt, u ze zelf verpakken. U voegt deze pakketten vervolgens toe aan de Microsoft Managed Desktop-portal en wijst ze toe aan Azure Active Directory-groepen om de implementatie te activeren. 

Als u uw apps momenteel implementeert met Behulp van Microsoft Endpoint Configuration Manager, kan Microsoft Managed Desktop u een query aanbieden om uw apps te beoordelen en te ontdekken welke apps klaar zijn om te migreren naar Microsoft Intune en welke mogelijk een aantal Aanpassing.


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Uw eigen apps voorbereiden op opname in Microsoft Managed Desktop
Bekijk uw apps en controleer:

- Geen van de apps is verboden of heeft beperkt gedrag, zoals beschreven in [de vereisten van de Microsoft Managed Desktop-app.](https://aka.ms/app-req)
- Apps moeten klaar zijn voor beheer door Microsoft Intune. Zie de implementatie [van Windows 10-apps met Microsoft Intune](https://docs.microsoft.com/intune/apps-windows-10-app-deploy) en [Apps toevoegen aan Microsoft Intune](https://docs.microsoft.com/intune/apps-add)voor meer informatie.
- Andere vereisten voor voor verpakkingen, zoals het verstrekken van licentiesleutels, overeenkomst met licentievoorwaarden en vooraf instellende serververbindingen.

### <a name="decide-how-to-package-apps"></a>Bepalen hoe u apps wilt verpakken

Sommige onafhankelijke softwareleveranciers vereisen mogelijk dat uw apps worden verpakt voordat ze centraal worden geïmplementeerd. 'Verpakking' betekent dat het installatieprogramma van de app is geconfigureerd met instellingen zoals licentiesleutels, externe serverlocaties of snelkoppelingen op het bureaublad, zodat de app op de achtergrond kan worden geïnstalleerd.

Er zijn drie opties om uw apps verpakt te krijgen: 


- U zelf apps verpakken
- U werken met een niet-Microsoft-leverancier
- U contact opnemen met MCS om uw apps te verpakken. Werk samen met uw Microsoft-accountvertegenwoordiger. Zie [Werken met Microsoft Consulting Services](apps-MCS.md)voor meer informatie.







## <a name="deploying-apps"></a>Apps implementeren

Welke methode u ook gebruikt om apps verpakt te krijgen, zodra dat is voltooid, u de stappen volgen in [Apps implementeren op Microsoft Managed Desktop-apparaten.](../get-started/deploy-apps.md)


