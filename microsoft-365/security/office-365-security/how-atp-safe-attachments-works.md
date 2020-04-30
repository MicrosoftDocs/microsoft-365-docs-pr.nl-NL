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
description: De functie Veilige bijlagen biedt time-of-click verificatie van e-mailbijlagen. Gebruik veilige bijlagen om uw organisatie te beschermen tegen schadelijke bestanden die mensen per e-mail verzenden of ontvangen.
ms.openlocfilehash: 14a1b37ce08e0ab63c23515fcf0fb03d99e59cc8
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943757"
---
# <a name="how-atp-safe-attachments-works"></a>Hoe Veilige bijlagen in ATP werkt

## <a name="how-it-works"></a>Hoe het werkt

De functie Veilige bijlagen ATP controleert e-mailbijlagen voor mensen in uw organisatie. Wanneer er een ATP-beleid voor veilige bijlagen is ingevoerd en iemand die onder dat beleid valt, zijn e-mail in Office 365 bekijkt, worden de e-mailbijlagen gecontroleerd en worden passende acties uitgevoerd op basis van uw beleid voor veilige bijlagen atp. Afhankelijk van hoe uw beleid is gedefinieerd, kunnen mensen blijven werken zonder ooit te weten dat ze schadelijke bestanden hebben verzonden.
  
Hier zijn twee voorbeelden van ATP Safe Attachments op het werk.
  
- **Voorbeeld 1: E-mailbijlage** Stel dat Lee een e-mailbericht ontvangt met een bijlage. Het is niet duidelijk voor Lee of die bijlage veilig is of eigenlijk malware bevat die is ontworpen om Lee's gebruikersreferenties te stelen. In lee's organisatie heeft een beveiligingsbeheerder een paar dagen geleden een ATP-beleid voor veilige bijlagen gedefinieerd. Met de ATP Safe Attachments-functie wordt de e-mailbijlage geopend en getest in een virtuele omgeving voordat Lee deze ontvangt. Als wordt vastgesteld dat de bijlage kwaadaardig is, wordt deze automatisch verwijderd. Als de bijlage veilig is, wordt deze geopend zoals verwacht wanneer Lee erop klikt.

- **Voorbeeld 2: Bestand in SharePoint Online** Stel dat Jean een bestand heeft ontvangen en geüpload naar een bibliotheek in SharePoint Online. Jean deelt de link naar het bestand met de rest van het team, niet wetende dat het bestand daadwerkelijk kwaadaardig is. Gelukkig detecteert [ATP voor SharePoint, OneDrive en Microsoft Teams](atp-for-spo-odb-and-teams.md) het schadelijke bestand en blokkeert het. Een paar dagen later gaat Chris het document openen. Hoewel Chris kan zien dat het bestand er is, kan Chris het niet openen of delen, wat Chris's computer en anderen beschermt tegen het schadelijke bestand.

Het beleid voor veilige bijlagen van ATP kan worden toegepast op specifieke personen of groepen in uw organisatie of op uw hele domein. Bovendien kan het beleid voor veilige bijlagen van ATP worden geconfigureerd om tijdelijke aanduidingsbijlagen te gebruiken terwijl werkelijke bijlagen worden gescand. Zie Beleid voor **[veilige bijlagen van ATP instellen in Office 365](set-up-atp-safe-attachments-policies.md)** voor meer informatie.

> [!NOTE]
> Het scannen van ATP Safe Attachments vindt plaats in dezelfde regio waar uw gegevens zich bevinden. Voor meer informatie over de geografie in datacenters raadpleegt u [waar bevinden uw gegevens zich?](https://products.office.com/where-is-your-data-located?geo=All) 

