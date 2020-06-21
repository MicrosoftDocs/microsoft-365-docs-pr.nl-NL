---
title: Hoe Veilige bijlagen in ATP werkt
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Ontdek hoe u uw organisatie beschermen tegen schadelijke bestanden met ATP Safe Attachments voor Office 365.
ms.openlocfilehash: f4f355d4def1f108a72854c3796e0e9373cb5ef1
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819398"
---
# <a name="how-atp-safe-attachments-works"></a>Hoe Veilige bijlagen in ATP werkt

De functie Veilige atp-bijlagen controleert e-mailbijlagen voor mensen in uw organisatie. Wanneer er een atp-beleid voor veilige bijlagen is ingevoerd en iemand die onder dat beleid valt, zijn e-mail bekijkt in Office 365, worden de e-mailbijlagen gecontroleerd en worden passende acties ondernomen op basis van uw beleid voor veilige bijlagen atp. Afhankelijk van hoe uw beleid wordt gedefinieerd, kunnen mensen blijven werken zonder ooit te weten dat ze schadelijke bestanden hebben verzonden.
  
Hier zijn twee voorbeelden van ATP Safe Attachments op het werk.
  
- **Voorbeeld 1: E-mailbijlage** Stel dat Lee een e-mailbericht ontvangt met een bijlage. Het is niet duidelijk voor Lee of die bijlage veilig is of daadwerkelijk malware bevat die is ontworpen om Lee's gebruikersreferenties te stelen. In de organisatie van Lee heeft een beveiligingsbeheerder een paar dagen geleden een ATP Safe Attachments-beleid gedefinieerd. Met de ATP Safe Attachments-functie wordt de e-mailbijlage geopend en getest in een virtuele omgeving voordat Lee deze ontvangt. Als de bijlage wordt vastgesteld dat deze kwaadaardig is, wordt deze automatisch verwijderd. Als de bijlage veilig is, wordt deze geopend zoals verwacht wanneer Lee erop klikt.

- **Voorbeeld 2: Bestand in SharePoint Online** Stel dat Jean een bestand heeft ontvangen en het heeft geüpload naar een bibliotheek in SharePoint Online. Jean deelt de link naar het bestand met de rest van het team, niet wetende dat het bestand daadwerkelijk kwaadaardig is. Gelukkig detecteert [ATP voor SharePoint, OneDrive en Microsoft Teams](atp-for-spo-odb-and-teams.md) het schadelijke bestand en blokkeert het. Een paar dagen later gaat Chris het document openen. Hoewel Chris kan zien het bestand is er, Chris kan niet openen of delen, die Chris's computer en anderen beschermt tegen het kwaadaardige bestand.

Atp Safe Attachments-beleid kan worden toegepast op specifieke personen of groepen in uw organisatie of op uw hele domein. Bovendien kan atp-beleid voor veilige bijlagen worden geconfigureerd om tijdelijke aanduidingen te gebruiken terwijl de werkelijke bijlagen worden gescand. Zie **[Atp-beleid voor veilige bijlagen instellen in Office 365](set-up-atp-safe-attachments-policies.md)** voor meer informatie.

> [!NOTE]
> ATP Safe Attachments scannen vindt plaats in dezelfde regio waar uw gegevens zich bevinden. Voor meer informatie over de geografie in datacenters raadpleegt u [waar bevinden uw gegevens zich?](https://products.office.com/where-is-your-data-located?geo=All) 

