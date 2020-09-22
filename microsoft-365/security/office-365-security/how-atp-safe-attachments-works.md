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
# <a name="how-atp-safe-attachments-works"></a><span data-ttu-id="7f147-103">Hoe Veilige bijlagen in ATP werkt</span><span class="sxs-lookup"><span data-stu-id="7f147-103">How ATP Safe Attachments works</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="7f147-104">Met de functie voor het beveiligen van ATP worden e-mailbijlagen gecontroleerd voor de personen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="7f147-104">The ATP Safe Attachments feature checks email attachments for people in your organization.</span></span> <span data-ttu-id="7f147-105">Wanneer een beleid voor veilige bijlagen van ATP wordt uitgevoerd en iemand waarop dit beleid van toepassing is, de e-mail weergeeft in Office 365, worden de bijbehorende e-mailbijlagen gecontroleerd en de benodigde acties gemaakt op basis van uw beleid voor veilige bijlagen.</span><span class="sxs-lookup"><span data-stu-id="7f147-105">When an ATP Safe Attachments policy is in place and someone covered by that policy views their email in Office 365, their email attachments are checked and appropriate actions are taken, based on your ATP Safe Attachments policies.</span></span> <span data-ttu-id="7f147-106">Afhankelijk van de manier waarop uw beleid is gedefinieerd, kunnen mensen verder werken zonder dat ze op de hoogte waren van de bestanden.</span><span class="sxs-lookup"><span data-stu-id="7f147-106">Depending on how your policies are defined, people can continue working without ever knowing they were sent malicious files.</span></span>
  
<span data-ttu-id="7f147-107">Hier volgen twee voorbeelden van veilige bijlagen met ATP op het werk.</span><span class="sxs-lookup"><span data-stu-id="7f147-107">Here are two examples of ATP Safe Attachments at work.</span></span>
  
- <span data-ttu-id="7f147-108">**Voorbeeld 1: e-mailbijlage** Stel dat Lee een e-mailbericht met een bijlage ontvangt.</span><span class="sxs-lookup"><span data-stu-id="7f147-108">**Example 1: Email attachment** Suppose that Lee receives an email message that has an attachment.</span></span> <span data-ttu-id="7f147-109">Het is niet duidelijk voor de waarde van Lee of de bijlage veilig of werkelijk schadelijke software bevat om gebruikersreferenties van Lee te stelen.</span><span class="sxs-lookup"><span data-stu-id="7f147-109">It is not obvious to Lee whether that attachment is safe or actually contains malware designed to steal Lee's user credentials.</span></span> <span data-ttu-id="7f147-110">In de organisatie van Lee heeft een beveiligingsbeheerder een paar dagen geleden een beveiligingsbeleid voor ATP met ATP.</span><span class="sxs-lookup"><span data-stu-id="7f147-110">In Lee's organization, a security administrator defined an ATP Safe Attachments policy a few days ago.</span></span> <span data-ttu-id="7f147-111">Met de functie voor het beveiligen van ATP wordt de e-mailbijlage geopend en getest in een virtuele omgeving voordat u deze ontvangt.</span><span class="sxs-lookup"><span data-stu-id="7f147-111">With the ATP Safe Attachments feature, the email attachment is opened and tested in a virtual environment before Lee receives it.</span></span> <span data-ttu-id="7f147-112">Als de bijlage is vastgesteld om schadelijk te zijn, wordt deze automatisch verwijderd.</span><span class="sxs-lookup"><span data-stu-id="7f147-112">If the attachment is determined to be malicious, it will be removed automatically.</span></span> <span data-ttu-id="7f147-113">Als de bijlage veilig is, wordt deze geopend als verwacht wanneer Lee op de bijlage klikt.</span><span class="sxs-lookup"><span data-stu-id="7f147-113">If the attachment is safe, it will open as expected when Lee clicks on it.</span></span>

- <span data-ttu-id="7f147-114">**Voorbeeld 2: bestand in SharePoint Online** Stel, Jean heeft een bestand ontvangen en geüpload naar een bibliotheek in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7f147-114">**Example 2: File in SharePoint Online** Suppose that Jean received a file and uploaded it into a library in SharePoint Online.</span></span> <span data-ttu-id="7f147-115">Met Jean wordt de koppeling naar het bestand gedeeld met de rest van het team, en weet niet dat het bestand daadwerkelijk schadelijk is.</span><span class="sxs-lookup"><span data-stu-id="7f147-115">Jean shares the link to the file with the rest of the team, not knowing that the file is actually malicious.</span></span> <span data-ttu-id="7f147-116">Gelukkig, [ATP voor SharePoint, OneDrive en Microsoft teams](atp-for-spo-odb-and-teams.md) detecteren het schadelijke bestand en blokkeert dit.</span><span class="sxs-lookup"><span data-stu-id="7f147-116">Fortunately, [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) detects the malicious file and blocks it.</span></span> <span data-ttu-id="7f147-117">Een paar dagen later, Chris gaat het document openen.</span><span class="sxs-lookup"><span data-stu-id="7f147-117">A few days later, Chris goes to open the document.</span></span> <span data-ttu-id="7f147-118">Hoewel Chris de naam van het bestand kan zien, kan Chris het bestand niet openen of delen, waardoor de computer van Chris en andere personen de computer van het schadelijke bestand beschermt.</span><span class="sxs-lookup"><span data-stu-id="7f147-118">Although Chris can see the file is there, Chris cannot open or share it, which protects Chris's computer and others from the malicious file.</span></span>

<span data-ttu-id="7f147-119">U kunt beleidsregels voor veilige bijlagen voor gebruikers toepassen op specifieke personen of groepen in uw organisatie, of op het hele domein.</span><span class="sxs-lookup"><span data-stu-id="7f147-119">ATP Safe Attachments policies can be applied to specific people or groups in your organization, or to your entire domain.</span></span> <span data-ttu-id="7f147-120">Daarnaast kunnen ook beleidsregels voor veilige beveiliging van de vrije dagen worden geconfigureerd voor het gebruik van tijdelijke aanduidingen voor bijlagen wanneer feitelijke bijlagen worden gescand.</span><span class="sxs-lookup"><span data-stu-id="7f147-120">In addition, ATP Safe Attachments policies can be configured to use placeholder attachments while actual attachments are being scanned.</span></span> <span data-ttu-id="7f147-121">Zie voor meer informatie het **[beleid voor het instellen van documenten voor veilige bijlagen in Office 365](set-up-atp-safe-attachments-policies.md)**.</span><span class="sxs-lookup"><span data-stu-id="7f147-121">To learn more, see **[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)**.</span></span>

> [!NOTE]
> <span data-ttu-id="7f147-122">Met de functie voor het scannen van ATP-virussen wordt gebruikgemaakt van de regio waar uw gegevens zich bevinden.</span><span class="sxs-lookup"><span data-stu-id="7f147-122">ATP Safe Attachments scanning takes place in the same region where your data resides.</span></span> <span data-ttu-id="7f147-123">Voor meer informatie over de geografie in datacenters raadpleegt u [waar bevinden uw gegevens zich?](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="7f147-123">For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span> 

