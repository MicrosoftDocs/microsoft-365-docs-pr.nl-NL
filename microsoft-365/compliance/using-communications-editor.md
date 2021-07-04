---
title: De communicatie editor gebruiken
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Gebruik de communicatieeditor om tekst te wijzigen en veldvariabelen samen te voegen bij het opmaken van uw inhoud.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 26076ff82ba226c2993c7c40e36bca2e08cbf683
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288117"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="6b431-103">De communicatie editor gebruiken</span><span class="sxs-lookup"><span data-stu-id="6b431-103">Use the communications editor</span></span>

<span data-ttu-id="6b431-104">Terwijl u de inhoud van uw portalinhoud, meldingen voor wettelijke wacht en verwante herinneringen/escalaties definieert, kunt u de communicatieeditor gebruiken om uw inhoud op te maken en dynamisch aan te passen.</span><span class="sxs-lookup"><span data-stu-id="6b431-104">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can use the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="6b431-105">Teksteditor met uitgebreide tekst</span><span class="sxs-lookup"><span data-stu-id="6b431-105">Rich text editor</span></span>

<span data-ttu-id="6b431-106">Met de communicatieeditor kan de gebruiker de tekst aanpassen met de editoropties.</span><span class="sxs-lookup"><span data-stu-id="6b431-106">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="6b431-107">Gebruikers kunnen bijvoorbeeld lettertypen wijzigen, lijsten met opsommingstekens maken, inhoud markeren en meer.</span><span class="sxs-lookup"><span data-stu-id="6b431-107">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span>

## <a name="merge-field-variables"></a><span data-ttu-id="6b431-108">Veldvariabelen samenvoegen</span><span class="sxs-lookup"><span data-stu-id="6b431-108">Merge field variables</span></span>

<span data-ttu-id="6b431-109">U kunt variabelen voor e-mail samenvoegen van de Communicatieeditor gebruiken om aangepaste bewaarkenmerken in te voegen in de hoofdtekst van een communicatie.</span><span class="sxs-lookup"><span data-stu-id="6b431-109">You can use email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="6b431-110">Wanneer het veld wordt verzonden naar de beheerder, wordt het samenvoegveld gevuld met het bijbehorende veld.</span><span class="sxs-lookup"><span data-stu-id="6b431-110">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="6b431-111">Wanneer het bijvoorbeeld naar beheerder John Smith wordt verzonden, wordt het samenvoegveld [Bewaarnaam] vertaald met de bijbehorende naam.</span><span class="sxs-lookup"><span data-stu-id="6b431-111">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span>

<span data-ttu-id="6b431-112">U kunt samenvoegvelden voor e-mail gebruiken door de pictogrammen voor het **samenvoegveld** boven aan het besturingselement voor editor met tekst met rijke tekst te selecteren.</span><span class="sxs-lookup"><span data-stu-id="6b431-112">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="6b431-113">De tijdelijke aanduiding wordt toegevoegd op basis van de locatie van de cursor van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="6b431-113">The placeholder will be added based off the location of the users' cursor.</span></span>

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="6b431-114">Lijst met samenvoegveldvariabelen</span><span class="sxs-lookup"><span data-stu-id="6b431-114">List of merge field variables</span></span>

<br>

****

|<span data-ttu-id="6b431-115">Veldnaam</span><span class="sxs-lookup"><span data-stu-id="6b431-115">Field name</span></span>|<span data-ttu-id="6b431-116">Velddetails</span><span class="sxs-lookup"><span data-stu-id="6b431-116">Field details</span></span>|
|---|---|
|<span data-ttu-id="6b431-117">Weergavenaam</span><span class="sxs-lookup"><span data-stu-id="6b431-117">Display Name</span></span>|<span data-ttu-id="6b431-118">De voor- en achternaam van de bewaarder.</span><span class="sxs-lookup"><span data-stu-id="6b431-118">The custodian's first and last name.</span></span>|
|<span data-ttu-id="6b431-119">Bevestigingskoppeling</span><span class="sxs-lookup"><span data-stu-id="6b431-119">Acknowledgment Link</span></span>|<span data-ttu-id="6b431-120">Een aangepaste koppeling om de bevestiging van elke bewaarder op te nemen.</span><span class="sxs-lookup"><span data-stu-id="6b431-120">A customized link to record each custodian's acknowledgment.</span></span>|
|<span data-ttu-id="6b431-121">Portalkoppeling</span><span class="sxs-lookup"><span data-stu-id="6b431-121">Portal Link</span></span>|<span data-ttu-id="6b431-122">Een aangepaste koppeling voor de complianceportal van de beheerder.</span><span class="sxs-lookup"><span data-stu-id="6b431-122">A customized link for the custodian's Compliance Portal.</span></span>|
|<span data-ttu-id="6b431-123">Uitgiftemedewerker</span><span class="sxs-lookup"><span data-stu-id="6b431-123">Issuing Officer</span></span>|<span data-ttu-id="6b431-124">Het e-mailadres van de opgegeven uitgiftemedewerker.</span><span class="sxs-lookup"><span data-stu-id="6b431-124">The email address of the specified issuing officer.</span></span>|
|<span data-ttu-id="6b431-125">Uitgiftedatum</span><span class="sxs-lookup"><span data-stu-id="6b431-125">Issuing Date</span></span>|<span data-ttu-id="6b431-126">De datum waarop de kennisgeving is uitgegeven (UTC).</span><span class="sxs-lookup"><span data-stu-id="6b431-126">The date that the notice was issued (UTC).</span></span>|
|
