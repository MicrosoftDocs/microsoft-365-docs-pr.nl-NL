---
title: Configureerbare instellingen implementeren in Microsoft Managed Desktop
description: Configureerbare instellingen in Microsoft Managed Desktop implementeren en bijhouden.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie, implementeren, gefaseerde implementatie, configureerbare instellingen
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: b731422e6d981b12ea576ed26b841e7c679266ae
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530257"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>Configureerbare instellingen implementeren en bijhouden - Microsoft Managed Desktop

Nadat u wijzigingen hebt aangebracht in uw instellingscategorieën en een implementatie hebt gefaseerd, u op de pagina Implementatiestatus beginnen met het implementeren van uw instellingen in groepen. Op deze pagina ziet u een overzicht van elke configureerbare instelling. Door een instellingscategorie te openen, u instellingen implementeren voor groepen en de voortgang van deze implementaties bijhouden.

## <a name="deployment-statuses"></a>Implementatiestatussen 

Dit zijn de statussen die u voor elke implementatie ziet.

Status  | Uitleg 
--- | --- 
Implementeren | Uw wijziging wacht om te worden geïmplementeerd in deze groep.
In uitvoering | De wijziging wordt toegepast op actieve apparaten in deze groep. 
Volledige | De wijziging is voltooid op alle actieve apparaten in deze groep. 
Mislukt | De wijziging is mislukt op 10 procent van de actieve apparaten in de groep, waardoor de implementatie is gestopt.<br><br> Een ondersteuningsverzoek wordt automatisch geopend met Microsoft Managed Desktop-bewerkingen om de implementatie op te lossen. 
Teruggekeerd | De wijziging is teruggezet naar de laatste wijziging die is geïmplementeerd in alle implementatiegroepen.

## <a name="deploy-changes"></a>Wijzigingen implementeren

We tonen bureaublad achtergrondfoto in deze instructies. Nadat u een implementatie hebt geënsceneerd, implementeert u wijzigingen vanaf de pagina Implementatiestatus. 

**Wijzigingen implementeren**

1. Aanmelden bij [microsoft Managed Desktop Admin-portal](https://aka.ms/mwaasportal)
2. Selecteer **Configureerbaar**onder **Instellingen**.
3. Selecteer in **de werkruimte van** de implementatiestatus de instelling die u wilt implementeren en selecteer vervolgens de gefaseerde implementatie die moet worden geïmplementeerd.
4. Selecteer **Implementeren** om de wijziging in een van de implementatiegroepen te implementeren.

> [!NOTE] 
> Het oranje waarschuwingspictogram geeft aan dat er een vorige groep beschikbaar is voor implementatie, omdat het wordt aanbevolen om in volgorde uit te rollen. 

![Werkruimte voor implementatiestatus. Deelvenster Vertrouwde sites aan de rechterkant. In de sectie Implementatiegroepen bevinden zich drie kolommen: implementatiegroepen, apparaten en status. In de statuskolom wordt 'implementeren' gemarkeerd.](../../media/1deployedit.png)
We raden u aan om in deze volgorde te implementeren in implementatiegroepen: Test, First, Fast en vervolgens Broad. 

Wanneer wijzigingen in elke groep zijn voltooid, wordt de status gewijzigd in **Voltooien**.

![Werkruimte voor implementatiestatus met kolommen voor datum bijgewerkt, versie, test, eerste, snel en breed. De rij Proxy wordt uitgebreid met een gedateerde instelling die is gemarkeerd als 'voltooid' in elk van de vier implementatiegroepen.](../../media/2completeedit.png)

## <a name="revert-deployment"></a>Implementatie terugdraaien

Nadat u een wijziging hebt geïmplementeerd, u terugkeren van **de implementatiestatus**. Wanneer u een wijziging die **wordt uitgevoerd** of **voltooid,** terugzet, wordt de huidige implementatie gestopt. De instelling wordt teruggezet naar de laatste versie die voor alle groepen is geïmplementeerd. 

We tonen de stappen om een wijziging terug te draaien met de achtergrondafbeelding bureaublad als voorbeeld. 

**Een wijziging terugdraaien**
1. Aanmelden bij [microsoft Managed Desktop Admin-portal](https://aka.ms/mwaasportal)
2. Selecteer **Configureerbaar**onder **Instellingen**.
3. Selecteer in **de werkruimte van** de implementatiestatus de instelling die u wilt terugdraaien en selecteer vervolgens de gefaseerde implementatie om terug te keren.
4. Selecteer Implementeren **van implementatie**onder Noodzaak om deze wijziging **terug te**draaien.

![Werkruimte voor implementatiestatus. Browser startpagina's is geselecteerd, het openen van een venster aan de rechterkant met gegevens over de ingediende wijziging en de status ervan. Onderaan staat het gebied 'noodzaak om deze wijziging terug te draaien' waar u 'Implementatie terugdraaien' selecteren.](../../media/3revert.png) 

## <a name="additional-resources"></a>Overige informatiebronnen
- [Overzicht van configureerbare instellingen](config-setting-overview.md)
- [Verwijzing naar configureerbare instellingen](config-setting-ref.md) 
