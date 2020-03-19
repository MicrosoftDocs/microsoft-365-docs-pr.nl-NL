---
title: Configureerbare instellingen implementeren in Microsoft Managed Desktop
description: Configureer en volg configureerbare instellingen in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie, implementeren, gefaseerde implementatie, configureerbare instellingen
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: e6946c138cb6fde15e35374b447038d5c302187e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42810413"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>Configureerbare instellingen implementeren en bijhouden - Microsoft Managed Desktop

Nadat u wijzigingen hebt aangebracht in uw instellingscategorieën en een implementatie hebt gefaseerd, u op de pagina Implementatiestatus beginnen met het implementeren van uw instellingen in groepen. Op deze pagina wordt een overzicht van elke configureerbare instelling weergegeven. Door een instellingscategorie te openen, u instellingen implementeren voor groepen en de voortgang van deze implementaties bijhouden.

## <a name="deployment-statuses"></a>Implementatiestatussen 

Dit zijn de statussen die u voor elke implementatie ziet.

Status  | Uitleg 
--- | --- 
Implementeren | Uw wijziging wacht om in deze groep te worden geïmplementeerd.
In uitvoering | De wijziging wordt toegepast op actieve apparaten in deze groep. 
Volledige | De wijziging die is voltooid op alle actieve apparaten in deze groep. 
Mislukt | De wijziging is mislukt op een 10 procent van de actieve apparaten in de groep, zodat de implementatie is gestopt.<br><br> Een ondersteuningsaanvraag wordt automatisch geopend met Microsoft Managed Desktop-bewerkingen om de implementatie op te lossen. 
Teruggekeerd | De wijziging is teruggezet naar de laatste wijziging die is geïmplementeerd in alle implementatiegroepen.

## <a name="deploy-changes"></a>Wijzigingen implementeren

We tonen bureaublad achtergrondfoto in deze instructies. Nadat u een implementatie hebt geënsceneerd, implementeert u wijzigingen vanaf de pagina Status implementatie. 

**Wijzigingen implementeren**

1. Aanmelden bij [de portal Beheerde Desktopbeheerder](https://aka.ms/mwaasportal) van Microsoft
2. Selecteer onder **Instellingen**de optie **Configureerbaar**.
3. Selecteer in **werkruimte Implementatiestatus** de instelling die u wilt implementeren en selecteer vervolgens de gefaseerde implementatie die u wilt implementeren.
4. Selecteer **Implementeren** om de wijziging in een van de implementatiegroepen te implementeren.

> [!NOTE] 
> Het oranje waarschuwingspictogram geeft aan dat er een vorige groep beschikbaar is voor implementatie, omdat het wordt aanbevolen om in volgorde uit te rollen. 

![Werkruimte implementatiestatus. Deelvenster Vertrouwde sites aan de rechterkant. In de sectie Groepgroepen implementeren staan drie kolommen: implementatiegroepen, apparaten en status. In de statuskolom wordt 'implementeren' gemarkeerd.](../../media/1deployedit.png)
We raden u aan om in deze volgorde implementeren naar implementatiegroepen: Test, First, Fast en then Broad. 

Wanneer wijzigingen in elke groep zijn voltooid, wordt de status gewijzigd in **Voltooien**.

![Implementatiestatuswerkruimte met kolommen voor datum bijgewerkt, versie, test, eerste, snel en breed. De rij Proxy wordt uitgebreid met een gedateerde instelling die in elk van de vier implementatiegroepen als 'voltooid' wordt gemarkeerd.](../../media/2completeedit.png)

## <a name="revert-deployment"></a>Implementatie terugdraaien

Nadat u een wijziging hebt geïmplementeerd, u terugkeren van **de implementatiestatus**. Wanneer u een wijziging terugzet die **in uitvoering** is of **Voltooid,** wordt de huidige implementatie gestopt. De instelling wordt teruggezet naar de laatste versie die is geïmplementeerd in alle groepen. 

We tonen de stappen om een wijziging terug te draaien met de achtergrondafbeelding bureaublad als voorbeeld. 

**Een wijziging terugdraaien**
1. Aanmelden bij [de portal Beheerde Desktopbeheerder](https://aka.ms/mwaasportal) van Microsoft
2. Selecteer onder **Instellingen**de optie **Configureerbaar**.
3. Selecteer in **werkruimte Implementatiestatus** de instelling die u wilt terugdraaien en selecteer vervolgens de gefaseerde implementatie om terug te keren.
4. Selecteer onder **Noodzaak om deze wijziging terug te draaien?**, selecteer Implementatie **terugdraaien**.

![Werkruimte implementatiestatus. Browserstartpagina's worden geselecteerd, waarbij een deelvenster aan de rechterkant wordt geopend met gegevens over de ingediende wijziging en de status ervan. Aan de onderkant is het gebied 'Noodzaak om deze wijziging terug te zetten' waar u 'Implementatie terugdraaien' selecteren.](../../media/3revert.png) 

## <a name="additional-resources"></a>Aanvullende bronnen
- [Overzicht van configureerbare instellingen](config-setting-overview.md)
- [Referentie voor configureerbare instellingen](config-setting-ref.md) 
