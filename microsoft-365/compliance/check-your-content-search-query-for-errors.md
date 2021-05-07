---
title: Uw inhoudszoekquery controleren op fouten
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
ms.custom: seo-marvel-apr2020
description: Lees hoe u fouten en typfouten kunt detecteren in uw trefwoordquery voor zoeken naar inhoud voordat u de zoekopdracht uitvoert.
ms.openlocfilehash: 939ac3d227f176a0b74138107ced5dd5b7142bcd
ms.sourcegitcommit: 7ebed5810480d7c49f8ca03207b5ea84993d253f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/31/2021
ms.locfileid: "52162514"
---
# <a name="check-your-content-search-query-for-errors"></a>Uw inhoudszoekquery controleren op fouten
  
Hier is een lijst met de niet-ondersteunde tekens die we controleren. Niet-ondersteunde tekens worden vaak verborgen en veroorzaken meestal een zoekfout of geven onbedoelde resultaten als resultaat.
  
- **Slimme aanhalingstekens-** Slimme enkele en dubbele aanhalingstekens (ook wel gekrulde aanhalingstekens genoemd) worden niet ondersteund. Alleen rechte aanhalingstekens kunnen worden gebruikt in een zoekquery. 

- **Niet-afdrukbare en besturingselementtekens:** niet-afdrukbare en besturingselementtekens vertegenwoordigen geen geschreven symbool, zoals een alfa-numeriek teken. Voorbeelden van niet-afdrukbare en besturingselementtekens zijn tekens die tekst of afzonderlijke regels tekst opmaken. 

- **Markeringen** van links naar rechts en van rechts naar links : dit zijn besturingselementtekens die worden gebruikt om tekstrichting aan te geven voor talen van links naar rechts (zoals Engels en Spaans) en talen van rechts naar links (zoals Arabisch en Hebreeuws).

- **Kleine letters Booleaanse operatoren:** als u een Booleaanse operator gebruikt, zoals **AND**, **OF** en **NIET** in een zoekquery, moet deze hoofdletters zijn. Wanneer we een query controleren op typfouten, geeft de syntaxis van de query vaak aan dat er een Booleaanse operator wordt gebruikt, ook al worden kleine letters gebruikt.  `(WordA or WordB) and (WordC or WordD)`bijvoorbeeld.

## <a name="what-happens-if-a-query-has-an-unsupported-character"></a>Wat gebeurt er als een query een niet-ondersteund teken heeft?

Als er niet-ondersteunde tekens worden gevonden in uw query, wordt een waarschuwingsbericht weergegeven met de melding dat er niet-ondersteunde tekens zijn gevonden en wordt een alternatief gesuggereerd. U hebt dan de optie om de oorspronkelijke query te behouden of te vervangen door de voorgestelde herziene query.

Hier ziet u een voorbeeld van het waarschuwingsbericht dat wordt weergegeven nadat u in de vorige schermafbeelding op Query controleren op **typfouten** voor de zoekquery hebt geklikt. Let op de oorspronkelijke query met slimme aanhalingstekens en kleine letters booleaanse operatoren.
  
![Er wordt een waarschuwingsbericht weergegeven met een voorgestelde revisie voor uw query](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a>Niet-ondersteunde tekens in uw zoekquery's voorkomen

Niet-ondersteunde tekens worden meestal toegevoegd aan een query wanneer u de query of delen van de query kopieert uit andere toepassingen (zoals Microsoft Word of Microsoft Excel) en deze in het trefwoordvak op de querypagina van een inhoudszoekactie plakt. De beste manier om niet-ondersteunde tekens te voorkomen, is door de query in het vak trefwoord te typen. U kunt ook een query kopiëren vanuit Word of Excel en deze vervolgens plakken in een tekst zonder opmaak, zoals Microsoft Kladblok. Sla het tekstbestand op en selecteer **ANSI** in de **vervolgkeuzelijst** Codering. Hiermee worden alle opmaak en niet-ondersteunde tekens verwijderd. Vervolgens kunt u de query uit het tekstbestand kopiëren en plakken naar het vak trefwoordquery. 
