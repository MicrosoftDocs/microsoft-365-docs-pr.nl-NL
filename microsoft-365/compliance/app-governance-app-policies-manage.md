---
title: App-beleid beheren
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Beheer uw app-beheerbeleid.
ms.openlocfilehash: 756402f86d6b65d48afb02c49b3e5bfc4e73fe3d
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420206"
---
# <a name="manage-app-policies"></a>App-beleid beheren

>*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](https://aka.ms/ComplianceSD).*

Om op de hoogte te blijven van de nieuwste apps die uw organisatie gebruikt, te reageren op nieuwe app-gebaseerde aanvallen en voor voortdurende wijzigingen in uw app-nalevingsbehoeften, moet u mogelijk uw app-beleid op de volgende manieren beheren:

- Nieuw beleid maken dat is gericht op nieuwe apps
- De status van een bestaand beleid wijzigen (actief, inactief, auditmodus)
- De voorwaarden van een bestaand beleid wijzigen
- De acties van een bestaand beleid voor automatisch herstel van waarschuwingen wijzigen

Hier is een voorbeeld van een proces voor het beheren van een bestaand beleid:

1. Bewerk het beleid:

  - Wijzig de instellingen van het beleid.
  - Wijzig indien nodig voor testdoeleinden de status in **Auditmodus**.

2. Controleer op verwacht gedrag, zoals gegenereerde waarschuwingen.
1. Als het gedrag niet wordt verwacht, gaat u terug naar stap 1.
1. Als het gedrag wordt verwacht, bewerkt u het beleid en wijzigt u de status in actief (indien nodig).

![De werkstroom voor app-beleid beheren](../media/manage-app-protection-governance/mapg-manage-policy-process.png)

## <a name="editing-an-app-policy-configuration"></a>De configuratie van een app-beleid bewerken

De configuratie van een bestaand app-beleid wijzigen:

- Selecteer het beleid in de beleidslijst en selecteer vervolgens **Bewerken** in het deelvenster App-beleid.
- Selecteer het verticale beletselteken voor het beleid in de lijst en selecteer vervolgens **Bewerken**.

Voor de pagina **Beleid bewerken** doorloopt u de pagina's en brengt u de gewenste wijzigingen aan:

- **Beschrijving**: wijzig de beschrijving om het doel van het beleid beter te begrijpen.
- **Ernst**
- **Beleidsinstellingen**: wijzig de set apps waarop het beleid van toepassing is. U kunt er ook voor kiezen om de bestaande voorwaarden te gebruiken of de voorwaarden te wijzigen
- **Acties**: wijzig de actie voor automatisch herstel voor waarschuwingen die door het beleid worden gegenereerd.
- **Status**: wijzig de beleidsstatus.

## <a name="deleting-an-app-policy"></a>Een app-beleid verwijderen

Als u een app-beleid wilt verwijderen, kunt u het volgende doen:

- Selecteer het beleid in de beleidslijst en selecteer vervolgens **Verwijderen** in het deelvenster App-beleid.
- Selecteer het verticale beletselteken voor het beleid in de lijst en selecteer vervolgens **Verwijderen**.

Een alternatief voor het verwijderen van een app-beleid is het wijzigen van de status in inactief. Zodra deze inactief is, worden er geen waarschuwingen gegenereerd. In plaats van een app-beleid te verwijderen voor een app met een specifieke set voorwaarden die nuttig zijn voor een toekomstig beleid, kunt u bijvoorbeeld de naam van het app-beleid wijzigen om het nut ervan aan te geven en de status ervan instellen op inactief. U kunt later terugkeren naar het beleid en het wijzigen voor een vergelijkbare app en de status ervan instellen op auditmodus of inactief.
