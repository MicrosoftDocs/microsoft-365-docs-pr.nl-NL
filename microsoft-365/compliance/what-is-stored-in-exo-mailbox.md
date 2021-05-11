---
title: Inhoud die is opgeslagen in Exchange Online postvakken
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ''
description: Inhoud die wordt geproduceerd door cloud-apps in Microsoft 365 wordt opgeslagen of gekoppeld aan het postvak van Exchange Online gebruiker. Deze inhoud kan worden doorzocht met microsoft eDiscovery-hulpprogramma's.
ms.openlocfilehash: 3490571a31ea69c5a8ee641a4ccc46077aced014
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311002"
---
# <a name="content-stored-in-exchange-online-mailboxes-for-ediscovery"></a>Inhoud die is opgeslagen in Exchange Online postvakken voor eDiscovery

Een postvak in Exchange Online wordt voornamelijk gebruikt voor het opslaan van e-mailgerelateerde items, zoals berichten, agenda-items, taken en notities. Maar dat verandert nu meer cloud-apps hun gegevens ook opslaan in het postvak van een gebruiker. Een voordeel van het opslaan van gegevens in een postvak is dat u de zoekhulpmiddelen kunt gebruiken in inhoud zoeken, Core eDiscovery en Advanced eDiscovery om de gegevens uit deze cloud-apps te zoeken, weer te geven en te exporteren. De gegevens van sommige van deze apps worden opgeslagen in verborgen mappen in een niet-interpersoonlijk bericht (niet-IPM) subtree in het postvak. Gegevens uit andere cloud-apps worden mogelijk niet _opgeslagen_ in  het postvak, maar wel aan het postvak en worden geretourneerd in zoekopdrachten (als deze gegevens overeenkomt met de zoekquery). Ongeacht of cloudgegevens zijn opgeslagen in of gekoppeld aan een gebruikerspostvak, de gegevens zijn meestal niet zichtbaar in een e-mailclient wanneer een gebruiker zijn postvak opent.

In de volgende tabel vindt u de apps die gegevens opslaan of associeert met een postvak in de cloud. In de tabel wordt ook beschreven welk type inhoud elke app produceert.

|Microsoft 365 app|Beschrijving|
|:---------|:---------|
|Formulieren<sup>*</sup>|Formulieren en antwoorden op een formulier worden opgeslagen in bestanden die zijn gekoppeld aan e-mailberichten en worden opgeslagen in een verborgen map in het postvak van de gebruiker die het formulier heeft gemaakt. Formulieren die vóór april 2020 zijn gemaakt, worden opgeslagen als EEN PDF-bestand. Formulieren die na 2020 zijn gemaakt, worden opgeslagen als een JSON-bestand.  Antwoorden op een formulier worden opgeslagen in een CSV-bestand. Wanneer u inhoud exporteert vanuit formulieren in een PST-bestand, bevinden deze gegevens zich in de map **ApplicationDataRoot** in een submap met de volgende globaal unieke geïdentificeerde (GUID): **c9a559d2-7aab-4f13-a6ed-e7e9c52aec87**. |
|Microsoft 365 Groepen|E-mailberichten, agenda-items, contactpersonen (Personen), notities en taken worden opgeslagen in het postvak dat is gekoppeld aan een Microsoft 365 groep.|
|Outlook/Exchange Online|E-mailberichten, agenda-items, contactpersonen (Personen), notities en taken worden opgeslagen in het postvak van een gebruiker.|
|Personen|Contactpersonen in de app Personen (die dezelfde contactpersonen zijn als contactpersonen die toegankelijk zijn in Outlook) worden opgeslagen in het postvak van een gebruiker.|
|Klasplanning|Abonnementen die zijn gemaakt in klasplanning, worden opgeslagen in het postvak van de Microsoft 365 groep die is ingericht wanneer een nieuw plan wordt gemaakt. De alias voor het groepspostvak is de naam van het plan.|
|Skype voor Bedrijven|Gesprekken in Skype voor Bedrijven worden opgeslagen in de map Gespreksgeschiedenis in het postvak van een gebruiker. Als het postvak van een deelnemer van een Skype vergadering in de bewaring van rechtszaken wordt geplaatst of is toegewezen aan een bewaarbeleid, worden bestanden die aan een vergadering zijn gekoppeld, bewaard in het postvak van de deelnemers.|
|Sway<sup>*</sup>|Sways worden opgeslagen als een HTML-bestand dat is gekoppeld aan een e-mailbericht en is opgeslagen in een verborgen map in het postvak van de gebruiker die de sway heeft gemaakt. Wanneer u inhoud exporteert vanuit Sway in een PST-bestand, bevinden deze gegevens zich in de map **ApplicationDataRoot** in een submap met de volgende GUID:  **905fcf26-4eb7-48a0-9ff0-8dcc7194b5ba**.|
|Taken|Taken in de app Taken (die dezelfde taken zijn als taken die toegankelijk zijn in Outlook) worden opgeslagen in het postvak van een gebruiker.|
|Teams|Gesprekken die deel uitmaken van een Teams kanaal, worden gekoppeld aan het Teams postvak. Gesprekken die deel uitmaken van de chatlijst in Teams (ook wel *1 x N-chats* genoemd) worden gekoppeld aan het postvak van de gebruikers die deelnemen aan de chat. Overzichtsgegevens voor vergaderingen en oproepen in een Teams kanaal zijn ook gekoppeld aan postvakken van gebruikers die inbelden bij de vergadering of oproep. Dus wanneer u naar Teams zoekt, zoekt u in het Teams postvak naar inhoud in kanaalgesprekken en zoekt u in gebruikerspostvakken naar inhoud in 1 x N-chats.|
|To-Do|Taken *(taken die worden* opgeslagen in takenlijsten) in de To-Do app worden opgeslagen in het postvak van een gebruiker.|
|Yammer|Gesprekken en opmerkingen binnen een Yammer-community zijn gekoppeld aan het postvak Microsoft 365 Groep, evenals het gebruikerspostvak van de auteur en eventuele benoemde geadresseerden (@ genoemde of CC'ed-gebruikers). Privéberichten die buiten een privé-Yammer worden opgeslagen in het postvak van de gebruikers die deelnemen aan het privébericht.|  
||||

> [!NOTE]
> <sup>*</sup>Als op dit moment een bewaarplaats in een postvak wordt geplaatst (met behulp van bewaar bewaart in Core eDiscovery- of Advanced eDiscovery-gevallen), wordt inhoud van deze app niet bewaard door de bewaarplaats.