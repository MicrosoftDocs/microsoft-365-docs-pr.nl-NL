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
# <a name="how-atp-safe-attachments-works"></a><span data-ttu-id="db15a-103">Hoe Veilige bijlagen in ATP werkt</span><span class="sxs-lookup"><span data-stu-id="db15a-103">How ATP Safe Attachments works</span></span>

<span data-ttu-id="db15a-104">De functie Veilige atp-bijlagen controleert e-mailbijlagen voor mensen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="db15a-104">The ATP Safe Attachments feature checks email attachments for people in your organization.</span></span> <span data-ttu-id="db15a-105">Wanneer er een atp-beleid voor veilige bijlagen is ingevoerd en iemand die onder dat beleid valt, zijn e-mail bekijkt in Office 365, worden de e-mailbijlagen gecontroleerd en worden passende acties ondernomen op basis van uw beleid voor veilige bijlagen atp.</span><span class="sxs-lookup"><span data-stu-id="db15a-105">When an ATP Safe Attachments policy is in place and someone covered by that policy views their email in Office 365, their email attachments are checked and appropriate actions are taken, based on your ATP Safe Attachments policies.</span></span> <span data-ttu-id="db15a-106">Afhankelijk van hoe uw beleid wordt gedefinieerd, kunnen mensen blijven werken zonder ooit te weten dat ze schadelijke bestanden hebben verzonden.</span><span class="sxs-lookup"><span data-stu-id="db15a-106">Depending on how your policies are defined, people can continue working without ever knowing they were sent malicious files.</span></span>
  
<span data-ttu-id="db15a-107">Hier zijn twee voorbeelden van ATP Safe Attachments op het werk.</span><span class="sxs-lookup"><span data-stu-id="db15a-107">Here are two examples of ATP Safe Attachments at work.</span></span>
  
- <span data-ttu-id="db15a-108">**Voorbeeld 1: E-mailbijlage** Stel dat Lee een e-mailbericht ontvangt met een bijlage.</span><span class="sxs-lookup"><span data-stu-id="db15a-108">**Example 1: Email attachment** Suppose that Lee receives an email message that has an attachment.</span></span> <span data-ttu-id="db15a-109">Het is niet duidelijk voor Lee of die bijlage veilig is of daadwerkelijk malware bevat die is ontworpen om Lee's gebruikersreferenties te stelen.</span><span class="sxs-lookup"><span data-stu-id="db15a-109">It is not obvious to Lee whether that attachment is safe or actually contains malware designed to steal Lee's user credentials.</span></span> <span data-ttu-id="db15a-110">In de organisatie van Lee heeft een beveiligingsbeheerder een paar dagen geleden een ATP Safe Attachments-beleid gedefinieerd.</span><span class="sxs-lookup"><span data-stu-id="db15a-110">In Lee's organization, a security administrator defined an ATP Safe Attachments policy a few days ago.</span></span> <span data-ttu-id="db15a-111">Met de ATP Safe Attachments-functie wordt de e-mailbijlage geopend en getest in een virtuele omgeving voordat Lee deze ontvangt.</span><span class="sxs-lookup"><span data-stu-id="db15a-111">With the ATP Safe Attachments feature, the email attachment is opened and tested in a virtual environment before Lee receives it.</span></span> <span data-ttu-id="db15a-112">Als de bijlage wordt vastgesteld dat deze kwaadaardig is, wordt deze automatisch verwijderd.</span><span class="sxs-lookup"><span data-stu-id="db15a-112">If the attachment is determined to be malicious, it will be removed automatically.</span></span> <span data-ttu-id="db15a-113">Als de bijlage veilig is, wordt deze geopend zoals verwacht wanneer Lee erop klikt.</span><span class="sxs-lookup"><span data-stu-id="db15a-113">If the attachment is safe, it will open as expected when Lee clicks on it.</span></span>

- <span data-ttu-id="db15a-114">**Voorbeeld 2: Bestand in SharePoint Online** Stel dat Jean een bestand heeft ontvangen en het heeft geüpload naar een bibliotheek in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="db15a-114">**Example 2: File in SharePoint Online** Suppose that Jean received a file and uploaded it into a library in SharePoint Online.</span></span> <span data-ttu-id="db15a-115">Jean deelt de link naar het bestand met de rest van het team, niet wetende dat het bestand daadwerkelijk kwaadaardig is.</span><span class="sxs-lookup"><span data-stu-id="db15a-115">Jean shares the link to the file with the rest of the team, not knowing that the file is actually malicious.</span></span> <span data-ttu-id="db15a-116">Gelukkig detecteert [ATP voor SharePoint, OneDrive en Microsoft Teams](atp-for-spo-odb-and-teams.md) het schadelijke bestand en blokkeert het.</span><span class="sxs-lookup"><span data-stu-id="db15a-116">Fortunately, [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) detects the malicious file and blocks it.</span></span> <span data-ttu-id="db15a-117">Een paar dagen later gaat Chris het document openen.</span><span class="sxs-lookup"><span data-stu-id="db15a-117">A few days later, Chris goes to open the document.</span></span> <span data-ttu-id="db15a-118">Hoewel Chris kan zien het bestand is er, Chris kan niet openen of delen, die Chris's computer en anderen beschermt tegen het kwaadaardige bestand.</span><span class="sxs-lookup"><span data-stu-id="db15a-118">Although Chris can see the file is there, Chris cannot open or share it, which protects Chris's computer and others from the malicious file.</span></span>

<span data-ttu-id="db15a-119">Atp Safe Attachments-beleid kan worden toegepast op specifieke personen of groepen in uw organisatie of op uw hele domein.</span><span class="sxs-lookup"><span data-stu-id="db15a-119">ATP Safe Attachments policies can be applied to specific people or groups in your organization, or to your entire domain.</span></span> <span data-ttu-id="db15a-120">Bovendien kan atp-beleid voor veilige bijlagen worden geconfigureerd om tijdelijke aanduidingen te gebruiken terwijl de werkelijke bijlagen worden gescand.</span><span class="sxs-lookup"><span data-stu-id="db15a-120">In addition, ATP Safe Attachments policies can be configured to use placeholder attachments while actual attachments are being scanned.</span></span> <span data-ttu-id="db15a-121">Zie **[Atp-beleid voor veilige bijlagen instellen in Office 365](set-up-atp-safe-attachments-policies.md)** voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="db15a-121">To learn more, see **[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)**.</span></span>

> [!NOTE]
> <span data-ttu-id="db15a-122">ATP Safe Attachments scannen vindt plaats in dezelfde regio waar uw gegevens zich bevinden.</span><span class="sxs-lookup"><span data-stu-id="db15a-122">ATP Safe Attachments scanning takes place in the same region where your data resides.</span></span> <span data-ttu-id="db15a-123">Voor meer informatie over de geografie in datacenters raadpleegt u [waar bevinden uw gegevens zich?](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="db15a-123">For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span> 

