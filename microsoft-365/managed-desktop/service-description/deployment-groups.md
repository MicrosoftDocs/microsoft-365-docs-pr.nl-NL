---
title: Apparaatimplementatiegroepen
description: De implementatiegroepen die worden gebruikt voor het beheren van updates en andere wijzigingen
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2d1f2325937488b95c40600f277835cca1329d1e
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985579"
---
# <a name="device-deployment-groups"></a>Apparaatimplementatiegroepen

Microsoft Managed Desktop gebruikt implementatiegroepen om de release van updates en configuratiewijzigingen op apparaten te beheren. Apparaten worden automatisch toegevoegd aan implementatiegroepen ("ringen" of "bij te werken groepen") wanneer ze zijn geregistreerd voor Microsoft Managed Desktop. Met implementatiegroepen kunnen apparaten wijzigingen ontvangen in een gefaseerd tijdlijn.

U kunt bepaalde apparaten alleen voor testdoeleinden toewijzen of specifieke early adopters aanwijzen om de wijzigingen eerst te ontvangen. Als u kritieke apparaten hebt, zoals apparaten die door leidinggevenden worden gebruikt of die bedrijfskritische functies uitvoeren, kunt u ze in de groep houden die updates ontvangt over de traagste cadans. Microsoft Managed Desktop kunt u opgeven dat een apparaat in een van de volgende groepen moet blijven.

- **Test:** het beste voor apparaten die worden gebruikt voor testen of gebruikers die frequente wijzigingen en blootstelling aan nieuwe functies kunnen tolereren en ook vroegtijdige feedback kunnen geven. Deze groep ontvangt regelmatig wijzigingen en ervaringen in deze groep hebben een sterk effect. De groep Test is vrijgesteld van bestaande service-overeenkomsten en gebruikersondersteuning. Het is het beste om eerst slechts een paar apparaten te verplaatsen en vervolgens de gebruikerservaring te controleren. Microsoft Managed Desktop wordt niet automatisch apparaten aan deze groep toegewezen. er worden alleen apparaten gebruikt die u opgeeft.
- **Ten** eerste: ideaal voor early adopters, vrijwilligers of aangewezen validators, IT-professionals of vertegenwoordigers van zakelijke functies, dat wil zeggen mensen die wijzigingen kunnen valideren en u feedback kunnen geven over de ervaring.
- **Breed** ontvangt wijzigingen als laatste. Het grootste deel van uw organisatie maakt meestal deel uit van deze groep. U kunt ook apparaten opgeven die in deze groep moeten zijn en alleen wijzigingen als laatste moeten ontvangen omdat ze bedrijfskritische functies uitvoeren of behoren tot gebruikers in kritieke rollen. 
- **Automatisch:** selecteer deze optie wanneer u Microsoft Managed Desktop apparaten automatisch wilt toewijzen aan een van de andere groepen. (We wijzen niet automatisch apparaten toe aan Test.) Als u een apparaat wilt vrijgeven dat u eerder hebt opgegeven, zodat het automatisch opnieuw kan worden toegewezen, selecteert u deze optie. 

Microsoft Managed Desktop gebruikt een aantal extra groepen om implementaties te beheren, maar u kunt er geen apparaten aan toewijzen. U kunt echter apparaten van die groepen verplaatsen naar een van de groepen in dit artikel. Zie Hoe updates worden verwerkt in Windows groepen voor meer informatie over hoe updates [worden beheerd in Microsoft Managed Desktop.](updates.md)

Als een apparaat zich in een groep die u hebt opgegeven, groep die is toegewezen **door,** wordt beheerder **genoemd.** Als Microsoft Managed Desktop de groep heeft toegewezen, wordt de groep automatisch **toegewezen.** Terwijl een apparaat bezig is met het verplaatsen naar een groep, wordt in behandeling **.** In **het veld** Groep ziet u altijd de groep waarin het apparaat zich momenteel heeft en wordt alleen bijgewerkt wanneer een overstap is voltooid.

> [!IMPORTANT]
> Probeer het lidmaatschap van deze groepen niet rechtstreeks te wijzigen. Volg altijd de stappen die worden beschreven in [Apparaten toewijzen aan een implementatiegroep.](../working-with-managed-desktop/assign-deployment-group.md)
