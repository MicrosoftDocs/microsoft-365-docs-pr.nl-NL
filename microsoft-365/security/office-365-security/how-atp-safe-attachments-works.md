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
description: Meer informatie over hoe u uw organisatie veilig kunt beschermen tegen kwaadaardige bestanden met behulp van veilige vrije documenten voor Office 365.
ms.openlocfilehash: d13674a5d3e769fc10a1f5fd2fd80a4f07c063de
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201471"
---
# <a name="how-atp-safe-attachments-works"></a>Hoe Veilige bijlagen in ATP werkt

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Met de functie voor het beveiligen van ATP worden e-mailbijlagen gecontroleerd voor de personen in uw organisatie. Wanneer een beleid voor veilige bijlagen van ATP wordt uitgevoerd en iemand waarop dit beleid van toepassing is, de e-mail weergeeft in Office 365, worden de bijbehorende e-mailbijlagen gecontroleerd en de benodigde acties gemaakt op basis van uw beleid voor veilige bijlagen. Afhankelijk van de manier waarop uw beleid is gedefinieerd, kunnen mensen verder werken zonder dat ze op de hoogte waren van de bestanden.
  
Hier volgen twee voorbeelden van veilige bijlagen met ATP op het werk.
  
- **Voorbeeld 1: e-mailbijlage** Stel dat Lee een e-mailbericht met een bijlage ontvangt. Het is niet duidelijk voor de waarde van Lee of de bijlage veilig of werkelijk schadelijke software bevat om gebruikersreferenties van Lee te stelen. In de organisatie van Lee heeft een beveiligingsbeheerder een paar dagen geleden een beveiligingsbeleid voor ATP met ATP. Met de functie voor het beveiligen van ATP wordt de e-mailbijlage geopend en getest in een virtuele omgeving voordat u deze ontvangt. Als de bijlage is vastgesteld om schadelijk te zijn, wordt deze automatisch verwijderd. Als de bijlage veilig is, wordt deze geopend als verwacht wanneer Lee op de bijlage klikt.

- **Voorbeeld 2: bestand in SharePoint Online** Stel, Jean heeft een bestand ontvangen en geüpload naar een bibliotheek in SharePoint Online. Met Jean wordt de koppeling naar het bestand gedeeld met de rest van het team, en weet niet dat het bestand daadwerkelijk schadelijk is. Gelukkig, [ATP voor SharePoint, OneDrive en Microsoft teams](atp-for-spo-odb-and-teams.md) detecteren het schadelijke bestand en blokkeert dit. Een paar dagen later, Chris gaat het document openen. Hoewel Chris de naam van het bestand kan zien, kan Chris het bestand niet openen of delen, waardoor de computer van Chris en andere personen de computer van het schadelijke bestand beschermt.

U kunt beleidsregels voor veilige bijlagen voor gebruikers toepassen op specifieke personen of groepen in uw organisatie, of op het hele domein. Daarnaast kunnen ook beleidsregels voor veilige beveiliging van de vrije dagen worden geconfigureerd voor het gebruik van tijdelijke aanduidingen voor bijlagen wanneer feitelijke bijlagen worden gescand. Zie voor meer informatie het **[beleid voor het instellen van documenten voor veilige bijlagen in Office 365](set-up-atp-safe-attachments-policies.md)**.

> [!NOTE]
> Met de functie voor het scannen van ATP-virussen wordt gebruikgemaakt van de regio waar uw gegevens zich bevinden. Voor meer informatie over de geografie in datacenters raadpleegt u [waar bevinden uw gegevens zich?](https://products.office.com/where-is-your-data-located?geo=All) 

