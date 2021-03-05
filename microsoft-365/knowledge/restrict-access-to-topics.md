---
title: De toegang tot onderwerpen in Microsoft Viva-onderwerpen beperken
description: Onderwerpen uitsluiten om te voorkomen dat ze worden ontdekt.
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: b8c49c96ace14ac1ba03411b5670d8e77268109a
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453906"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a><span data-ttu-id="ae421-103">De toegang tot onderwerpen in Microsoft Viva-onderwerpen beperken</span><span class="sxs-lookup"><span data-stu-id="ae421-103">Restrict access to topics in Microsoft Viva Topics</span></span>

<span data-ttu-id="ae421-104">In Microsoft Viva willen belanghebbenden in uw organisatie er mogelijk voor zorgen dat specifieke onderwerpen niet worden ontdekt en worden getoond aan uw gelicentieerde gebruikers.</span><span class="sxs-lookup"><span data-stu-id="ae421-104">In Microsoft Viva, stakeholders in your organization may want to make sure that specific topics aren't discovered and exposed to your licensed users.</span></span> <span data-ttu-id="ae421-105">Stel dat u aan een project werkt waar u nog geen informatie over wilt verstrekken.</span><span class="sxs-lookup"><span data-stu-id="ae421-105">For example, you may be working on a project that you don't want to expose any information about yet.</span></span> <span data-ttu-id="ae421-106">Hoewel office 365-machtigingen voor sites, bestanden en andere bronnen verhinderen dat gebruikers van onderwerpervaringen gevoelige informatie in onderwerpen kunnen bekijken, zijn er extra beveiligingen om te voorkomen dat er specifieke onderwerpen worden ontdekt.</span><span class="sxs-lookup"><span data-stu-id="ae421-106">While Office 365 permissions on sites, files and other resources will prevent Topic Experiences users from viewing sensitive information in topics, there are additional safeguards to prevent specific topics from ever being discovered.</span></span>

<span data-ttu-id="ae421-107">Kennisbeheerders bepalen de instellingen van het kennisnetwerk om te voorkomen dat er onderwerpen worden ontdekt, maar kennisbeheerders en andere belanghebbenden moeten weten hoe dit wordt gedaan zodat ze kunnen samenwerken.</span><span class="sxs-lookup"><span data-stu-id="ae421-107">While knowledge admins control the knowledge network settings to prevent topics from being discovered, knowledge managers and other stakeholders need to know how it is done so that they can work collaboratively.</span></span>

> [!Important] 
> <span data-ttu-id="ae421-108">In dit artikel worden manieren beschreven om te voorkomen dat onderwerpen worden geïdentificeerd via AI of in uw omgeving worden bekeken als extra beveiliging.</span><span class="sxs-lookup"><span data-stu-id="ae421-108">This article describes ways to prevent topics from being identified through AI or viewed in your environment as an additional security safeguard.</span></span> <span data-ttu-id="ae421-109">Het is belangrijk te weten dat in Viva-onderwerpen gebruikers in een onderwerp geen toegang hebben tot een onderwerp dat ze niet mogen bekijken via Office 365-machtigingen.</span><span class="sxs-lookup"><span data-stu-id="ae421-109">It is important to note that in Viva Topics, users aren't allowed to view anything in a topic that they aren't allowed to access through Office 365 permissions.</span></span> <span data-ttu-id="ae421-110">Zelfs als een gebruiker een onderwerp kan bekijken, zijn de bestanden, sites en pagina's ervan niet zichtbaar voor gebruikers zonder Office 365-machtigingen.</span><span class="sxs-lookup"><span data-stu-id="ae421-110">Even if a users is able to view a topic, its files, sites, and pages they do not have Office 365 permissions to view will not be visible to them.</span></span> <span data-ttu-id="ae421-111">Zorg ervoor dat machtigingen voor gevoelige bestanden correct worden ingesteld als primaire beveiliging.</span><span class="sxs-lookup"><span data-stu-id="ae421-111">Making sure that permissions to sensitive files are correctly set should be your primary security safeguard.</span></span>

## <a name="prevent-topics-from-being-identified"></a><span data-ttu-id="ae421-112">Voorkomen dat onderwerpen worden geïdentificeerd</span><span class="sxs-lookup"><span data-stu-id="ae421-112">Prevent topics from being identified</span></span>

<span data-ttu-id="ae421-113">De kennisbeheerder kan de toegang tot specifieke onderwerpen beperken door te voorkomen dat deze worden gevonden bij de eerste indexering.</span><span class="sxs-lookup"><span data-stu-id="ae421-113">Knowledge admin can restrict access to specific topics by preventing them from being found in initial indexing.</span></span> <span data-ttu-id="ae421-114">U kunt deze taak op twee manieren uitvoeren in de beheerinstellingen voor het Knowledge Network in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="ae421-114">There are two ways to do this task in the Knowledge Network admin settings in the Microsoft 365 admin center.</span></span>
 
- <span data-ttu-id="ae421-115">[Selecteer SharePoint-sites die u wilt](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources)uitsluiten van onderwerpdetectie. U kunt deze instelling gebruiken om te voorkomen dat bepaalde SharePoint-sites voor onderwerpen worden verkend.</span><span class="sxs-lookup"><span data-stu-id="ae421-115">[Select SharePoint sites to exclude from topic discovery](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources): You can use this setting to prevent specific SharePoint sites from being crawled for topics.</span></span>
- <span data-ttu-id="ae421-116">[Onderwerpen uitsluiten op naam:](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name)Beheerders kunnen deze instelling gebruiken om te voorkomen dat specifieke onderwerpen op naam worden gevonden.</span><span class="sxs-lookup"><span data-stu-id="ae421-116">[Exclude topics by name](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name): Admins can use this setting to prevent specific topics from being discovered by name.</span></span> <span data-ttu-id="ae421-117">In de beheerinstellingen van het Knowledge Network kan een beheerder een lijst met onderwerpen uploaden die in een CSV-bestand moeten worden uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="ae421-117">In the Knowledge Network admin settings, an admin can upload a list of topics to be excluded in a CSV file.</span></span> <span data-ttu-id="ae421-118">U kunt onderwerpen uitsluiten die exacte of gedeeltelijke overeenkomsten hebben met een onderwerpnaam.</span><span class="sxs-lookup"><span data-stu-id="ae421-118">You can exclude topics that have exact or partial matches of a topic name.</span></span>

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a><span data-ttu-id="ae421-119">Voorkomen dat specifieke gebruikers onderwerpen bekijken</span><span class="sxs-lookup"><span data-stu-id="ae421-119">Prevent topics from being viewed by specific users</span></span>

<span data-ttu-id="ae421-120">Kennisbeheerders kunnen ook [selecteren wie onderwerpen in uw organisatie mag bekijken.](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules)</span><span class="sxs-lookup"><span data-stu-id="ae421-120">Knowledge admins can also [select who can view topics in your organization](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules).</span></span> <span data-ttu-id="ae421-121">Met deze instelling kunt u selecteren welke gelicentieerde gebruikers alle onderwerpen kunnen bekijken.</span><span class="sxs-lookup"><span data-stu-id="ae421-121">This setting lets you select which licensed users can view all topics.</span></span> <span data-ttu-id="ae421-122">In een testomgeving wilt u bijvoorbeeld mogelijk dat slechts een kleine groep gebruikers onderwerpen kan bekijken.</span><span class="sxs-lookup"><span data-stu-id="ae421-122">For example, in a pilot environment, you may want to only allow a small group of users to be able to view topics.</span></span>

## <a name="remove-topics-from-being-viewed"></a><span data-ttu-id="ae421-123">Onderwerpen verwijderen voor weergave</span><span class="sxs-lookup"><span data-stu-id="ae421-123">Remove topics from being viewed</span></span>

<span data-ttu-id="ae421-124">Knowledge managers kunnen ervoor kiezen [om onderwerpen te verwijderen,](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) zodat gebruikers ze niet meer kunnen zien.</span><span class="sxs-lookup"><span data-stu-id="ae421-124">Knowledge managers can choose to [remove topics](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) so that users can no longer see them.</span></span> <span data-ttu-id="ae421-125">Op de **pagina Onderwerpen** beheren in het **Onderwerpcentrum** kunnen knowledge managers ervoor kiezen specifieke onderwerpen te weigeren om te voorkomen dat ze worden bekeken.</span><span class="sxs-lookup"><span data-stu-id="ae421-125">On the **Manage topics** page in the **Topic center**, knowledge managers can choose to reject specific topics to prevent them from being viewed.</span></span> <span data-ttu-id="ae421-126">Onderwerpen kunnen worden verwijderd, ongeacht of ze een voorgestelde of bevestigd status hebben.</span><span class="sxs-lookup"><span data-stu-id="ae421-126">Topics can be removed regardless if they are in a suggested or confirmed state.</span></span>

<span data-ttu-id="ae421-127">Verwijderde onderwerpen kunnen later zo nodig weer worden toegevoegd als weergavebare onderwerpen.</span><span class="sxs-lookup"><span data-stu-id="ae421-127">Removed topics can later be added back as viewable topics if needed.</span></span> 


## <a name="see-also"></a><span data-ttu-id="ae421-128">Zie ook</span><span class="sxs-lookup"><span data-stu-id="ae421-128">See also</span></span>



  






