---
title: De zoekquery controleren op fouten
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
description: Meer informatie over het detecteren van fouten en typfouten in uw trefwoordquery voor eDiscovery-zoekopdrachten voordat u de zoekopdracht uitvoert.
ms.openlocfilehash: 9c041ca690df3306347cbca77df3ba9639801245
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311686"
---
# <a name="check-your-search-query-for-errors"></a><span data-ttu-id="c591d-103">De zoekquery controleren op fouten</span><span class="sxs-lookup"><span data-stu-id="c591d-103">Check your search query for errors</span></span>
  
<span data-ttu-id="c591d-104">Hier is een lijst met de niet-ondersteunde tekens die we controleren in zoekquery's voor zoeken naar inhoud en Core eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="c591d-104">Here's a list of the unsupported characters that we check for in search queries for Content search and Core eDiscovery.</span></span> <span data-ttu-id="c591d-105">Niet-ondersteunde tekens worden vaak verborgen en veroorzaken meestal een zoekfout of geven onbedoelde resultaten als resultaat.</span><span class="sxs-lookup"><span data-stu-id="c591d-105">Unsupported characters are often hidden, and they typically cause a search error or return unintended results.</span></span>
  
- <span data-ttu-id="c591d-106">**Slimme aanhalingstekens-** Slimme enkele en dubbele aanhalingstekens (ook wel gekrulde aanhalingstekens genoemd) worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="c591d-106">**Smart quotation marks** - Smart single and double quotation marks (also called curly quotes) aren't supported.</span></span> <span data-ttu-id="c591d-107">Alleen rechte aanhalingstekens kunnen worden gebruikt in een zoekquery.</span><span class="sxs-lookup"><span data-stu-id="c591d-107">Only straight quotation marks can be used in a search query.</span></span> 

- <span data-ttu-id="c591d-108">**Niet-afdrukbare en besturingselementtekens:** niet-afdrukbare en besturingselementtekens vertegenwoordigen geen geschreven symbool, zoals een alfa-numeriek teken.</span><span class="sxs-lookup"><span data-stu-id="c591d-108">**Non-printable and control characters** - Non-printable and control characters don't represent a written symbol, such as an alpha-numeric character.</span></span> <span data-ttu-id="c591d-109">Voorbeelden van niet-afdrukbare en besturingselementtekens zijn tekens die tekst of afzonderlijke regels tekst opmaken.</span><span class="sxs-lookup"><span data-stu-id="c591d-109">Examples of non-printable and control characters include characters that format text or separate lines of text.</span></span> 

- <span data-ttu-id="c591d-110">**Markeringen** van links naar rechts en van rechts naar links : dit zijn besturingselementtekens die worden gebruikt om tekstrichting aan te geven voor talen van links naar rechts (zoals Engels en Spaans) en talen van rechts naar links (zoals Arabisch en Hebreeuws).</span><span class="sxs-lookup"><span data-stu-id="c591d-110">**Left-to-right and right-to-left marks** - These marks are control characters used to indicate text direction for left-to-right languages (such as English and Spanish) and right-to-left languages (such as Arabic and Hebrew).</span></span>

- <span data-ttu-id="c591d-111">**Kleine letters Booleaanse operatoren:** als u een Booleaanse operator gebruikt, zoals **AND**, **OF** en **NIET** in een zoekquery, moet deze hoofdletters zijn.</span><span class="sxs-lookup"><span data-stu-id="c591d-111">**Lowercase Boolean operators** - If you use a Boolean operator, such as **AND**, **OR**, and **NOT** in a search query, it must be uppercase.</span></span> <span data-ttu-id="c591d-112">Wanneer we een query controleren op typfouten, geeft de syntaxis van de query vaak aan dat er een Booleaanse operator wordt gebruikt, ook al worden kleine letters gebruikt.  `(WordA or WordB) and (WordC or WordD)`bijvoorbeeld.</span><span class="sxs-lookup"><span data-stu-id="c591d-112">When we check a query for typos, the query syntax will often indicate that a Boolean operator is being used even though lowercase operators might be used; for example,  `(WordA or WordB) and (WordC or WordD)`.</span></span>

## <a name="what-happens-if-a-query-has-an-unsupported-character"></a><span data-ttu-id="c591d-113">Wat gebeurt er als een query een niet-ondersteund teken heeft?</span><span class="sxs-lookup"><span data-stu-id="c591d-113">What happens if a query has an unsupported character?</span></span>

<span data-ttu-id="c591d-114">Als er niet-ondersteunde tekens worden gevonden in uw query, wordt een waarschuwingsbericht weergegeven met de melding dat er niet-ondersteunde tekens zijn gevonden en wordt een alternatief gesuggereerd.</span><span class="sxs-lookup"><span data-stu-id="c591d-114">If unsupported characters are found in your query, a warning message is displayed that says unsupported characters were found and suggests an alternative.</span></span> <span data-ttu-id="c591d-115">U hebt dan de optie om de oorspronkelijke query te behouden of te vervangen door de voorgestelde herziene query.</span><span class="sxs-lookup"><span data-stu-id="c591d-115">You then have the option keep the original query or replace it with the suggested revised query.</span></span>

<span data-ttu-id="c591d-116">Hier ziet u een voorbeeld van het waarschuwingsbericht dat wordt weergegeven nadat u in de vorige schermafbeelding op Query controleren op **typfouten** voor de zoekquery hebt geklikt.</span><span class="sxs-lookup"><span data-stu-id="c591d-116">Here's an example of the warning message that's displayed after you click **Check query for typos** for the search query in the previous screenshot.</span></span> <span data-ttu-id="c591d-117">Let op de oorspronkelijke query met slimme aanhalingstekens en kleine letters booleaanse operatoren.</span><span class="sxs-lookup"><span data-stu-id="c591d-117">Note the original query used smart quotes and lowercase Boolean operators.</span></span>
  
![Er wordt een waarschuwingsbericht weergegeven met een voorgestelde revisie voor uw query](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a><span data-ttu-id="c591d-119">Niet-ondersteunde tekens in uw zoekquery's voorkomen</span><span class="sxs-lookup"><span data-stu-id="c591d-119">How to prevent unsupported characters in your search queries</span></span>

<span data-ttu-id="c591d-120">Niet-ondersteunde tekens worden meestal toegevoegd aan een query wanneer u de query of delen van de query kopieert uit andere toepassingen (zoals Microsoft Word of Microsoft Excel) en deze in het trefwoordvak op de querypagina van een inhoudszoekactie plakt.</span><span class="sxs-lookup"><span data-stu-id="c591d-120">Unsupported characters are typically added to a query when you copy the query or parts of the query from other applications (such as Microsoft Word or Microsoft Excel) and paste them in the keyword box on the query page of a Content Search.</span></span> <span data-ttu-id="c591d-121">De beste manier om niet-ondersteunde tekens te voorkomen, is door de query in het vak trefwoord te typen.</span><span class="sxs-lookup"><span data-stu-id="c591d-121">The best way to prevent unsupported characters is to just type the query in the keyword box.</span></span> <span data-ttu-id="c591d-122">U kunt ook een query kopiëren vanuit Word of Excel en deze vervolgens plakken in een tekst zonder opmaak, zoals Microsoft Kladblok.</span><span class="sxs-lookup"><span data-stu-id="c591d-122">Or you can copy a query from Word or Excel, and then paste it in a plain text editor, such as Microsoft Notepad.</span></span> <span data-ttu-id="c591d-123">Sla het tekstbestand op en selecteer **ANSI** in de **vervolgkeuzelijst** Codering.</span><span class="sxs-lookup"><span data-stu-id="c591d-123">Save the text file and select **ANSI** in the **Encoding** drop-down list.</span></span> <span data-ttu-id="c591d-124">Hiermee worden alle opmaak en niet-ondersteunde tekens verwijderd.</span><span class="sxs-lookup"><span data-stu-id="c591d-124">This will remove any formatting and unsupported characters.</span></span> <span data-ttu-id="c591d-125">Vervolgens kunt u de query uit het tekstbestand kopiëren en plakken naar het vak trefwoordquery.</span><span class="sxs-lookup"><span data-stu-id="c591d-125">Then you can copy and paste the query from the text file to the keyword query box.</span></span>
