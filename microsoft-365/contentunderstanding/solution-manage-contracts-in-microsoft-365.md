---
title: Beheer contracten met een gebruik van een Microsoft 365 oplossing
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
ms.collection: m365solution-managecontracts m365solution-overview
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: Meer informatie over het beheren van contracten met Microsoft 365 oplossing voor SharePoint Syntex, SharePoint lijsten, Microsoft Teams en Power Automate.
ms.openlocfilehash: bc2570b08add2fa93637b9f64931c5903795a079
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287315"
---
# <a name="manage-contracts-using-a-microsoft-365-solution"></a><span data-ttu-id="dc301-103">Beheer contracten met een gebruik van een Microsoft 365 oplossing</span><span class="sxs-lookup"><span data-stu-id="dc301-103">Manage contracts using a Microsoft 365 solution</span></span>

<span data-ttu-id="dc301-104">In dit artikel wordt beschreven hoe u een oplossing voor contractbeheer voor uw organisatie kunt maken met SharePoint Syntex en onderdelen van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dc301-104">This article describes how to create a contracts management solution for your organization by using SharePoint Syntex and components of Microsoft 365.</span></span> <span data-ttu-id="dc301-105">Het biedt u een kader om u te helpen bij het plannen en maken van een oplossing die past bij uw unieke zakelijke behoeften.</span><span class="sxs-lookup"><span data-stu-id="dc301-105">It provides you with a framework to help you plan and create a solution that fits your unique business needs.</span></span> <span data-ttu-id="dc301-106">Hoewel in deze oplossing wordt gesproken over contractbeheer, kunt u deze aanpassen aan andere oplossingen voor documentbeheer, zoals voor overzichten van werk of facturen.</span><span class="sxs-lookup"><span data-stu-id="dc301-106">Even though this solution talks about contract management, you can adapt it to create other document management solutions, such as for statements of work or invoices.</span></span>

<span data-ttu-id="dc301-107">*Deze inhoudsset documenteert een Microsoft 365 oplossing die is ontwikkeld door Thomas Molbach met het Modern Work Solution Strategy Team bij Microsoft.*</span><span class="sxs-lookup"><span data-stu-id="dc301-107">*This content set documents a Microsoft 365 solution developed by Thomas Molbach with the Modern Work Solution Strategy Team at Microsoft.*</span></span>

## <a name="identify-the-business-problem"></a><span data-ttu-id="dc301-108">Het zakelijke probleem identificeren</span><span class="sxs-lookup"><span data-stu-id="dc301-108">Identify the business problem</span></span>

<span data-ttu-id="dc301-109">De eerste stap bij het plannen van uw contractbeheersysteem is het begrijpen van het probleem dat u probeert op te lossen.</span><span class="sxs-lookup"><span data-stu-id="dc301-109">The first step in planning your contract management system is to understand the problem you're trying to solve.</span></span> <span data-ttu-id="dc301-110">Voor deze oplossing moeten vier belangrijke problemen worden opgelost:</span><span class="sxs-lookup"><span data-stu-id="dc301-110">For this solution, four key issues need to be addressed:</span></span>

- <span data-ttu-id="dc301-111">**Identificeer contracten**.</span><span class="sxs-lookup"><span data-stu-id="dc301-111">**Identify contracts**.</span></span> <span data-ttu-id="dc301-112">Uw organisatie werkt met veel documenten, zoals facturen, contracten, werkafschriften, en dergelijke.</span><span class="sxs-lookup"><span data-stu-id="dc301-112">Your organization works with many documents, such as invoices, contracts, statements of work, and so on.</span></span>  <span data-ttu-id="dc301-113">Sommige zijn digitale activa die via e-mail worden verzonden, en sommige zijn papieren activa die via traditionele e-mail worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="dc301-113">Some are digital assets sent through email, and some are paper assets sent through traditional mail.</span></span> <span data-ttu-id="dc301-114">U hebt een manier nodig om alle klantcontracten van alle andere documenten te identificeren en vervolgens als zodanig te classificeren.</span><span class="sxs-lookup"><span data-stu-id="dc301-114">You need a way to identify all customer contracts from all other documents, and then classifying them as such.</span></span>

- <span data-ttu-id="dc301-115">**Volg de geschiedenis van contractgoedkeuringen.**</span><span class="sxs-lookup"><span data-stu-id="dc301-115">**Track the history of contract approvals**.</span></span> <span data-ttu-id="dc301-116">Uw organisatie heeft een betrouwbare manier nodig om te bepalen of contracten zijn goedgekeurd of geweigerd en of de betaling is verwerkt.</span><span class="sxs-lookup"><span data-stu-id="dc301-116">Your organization needs a reliable way to find whether contracts have been either approved or rejected, and whether payment has been processed.</span></span> 

- <span data-ttu-id="dc301-117">**Site voor het beheren van goedkeuringen van contracten.**</span><span class="sxs-lookup"><span data-stu-id="dc301-117">**Site to manage contract approvals**.</span></span> <span data-ttu-id="dc301-118">Uw organisatie moet een samenwerkingssite instellen waarin alle vereiste belanghebbenden eenvoudig contracten kunnen bekijken.</span><span class="sxs-lookup"><span data-stu-id="dc301-118">Your organization needs to set up a collaborative site in which all required stakeholders can easily review contracts.</span></span> <span data-ttu-id="dc301-119">Belanghebbenden moeten indien nodig het hele contract kunnen bekijken, maar het is vooral belangrijk om verschillende belangrijke velden uit elk contract te zien (bijvoorbeeld klantnaam, PO-nummer en totale kosten).</span><span class="sxs-lookup"><span data-stu-id="dc301-119">Stakeholders should be able to review the whole contract if needed, but mostly care about seeing several key fields from each contract (for example, customer name, PO number, and total cost).</span></span> <span data-ttu-id="dc301-120">Belanghebbenden moeten inkomende contracten eenvoudig kunnen goedkeuren of afwijzen.</span><span class="sxs-lookup"><span data-stu-id="dc301-120">Stakeholders should be able to easily approve or reject incoming contracts.</span></span>

- <span data-ttu-id="dc301-121">**Route beoordeelde contracten**.</span><span class="sxs-lookup"><span data-stu-id="dc301-121">**Route reviewed contracts**.</span></span> <span data-ttu-id="dc301-122">Goedgekeurde en geweigerde contracten moeten worden gerouteerd via een specifieke werkstroom.</span><span class="sxs-lookup"><span data-stu-id="dc301-122">Approved and rejected contracts need to be routed through a specific workflow.</span></span> <span data-ttu-id="dc301-123">Goedgekeurde contracten moeten worden doorgeleid naar een toepassing van derden voor betalingsverwerking.</span><span class="sxs-lookup"><span data-stu-id="dc301-123">Approved contracts need to be routed to a third-party application for payment processing.</span></span> <span data-ttu-id="dc301-124">Geweigerde contracten moeten worden gerouteerd voor extra controle.</span><span class="sxs-lookup"><span data-stu-id="dc301-124">Rejected contracts need to be routed for additional review.</span></span>

## <a name="overview-of-the-solution"></a><span data-ttu-id="dc301-125">Overzicht van de oplossing</span><span class="sxs-lookup"><span data-stu-id="dc301-125">Overview of the solution</span></span>

  ![Diagram van de oplossing met SharePoint Syntex, SharePoint lijsten, Teams en Power Automate.](../media/content-understanding/syntex-solution-manage-contracts-setup-steps.png)

<span data-ttu-id="dc301-127">Deze richtlijn voor contractbeheeroplossing bevat vier onderdelen van Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="dc301-127">This contract management solution guidance includes four components of Microsoft 365:</span></span>

- <span data-ttu-id="dc301-128">**Microsoft SharePoint Syntex:** maak modellen om uw contractbestanden te identificeren en te classificeren en haal vervolgens de juiste gegevens uit deze bestanden.</span><span class="sxs-lookup"><span data-stu-id="dc301-128">**Microsoft SharePoint Syntex**: Create models to identify and classify your contract files and then extract the appropriate data from them.</span></span>

- <span data-ttu-id="dc301-129">**Microsoft SharePoint:** Gebruik de opmaak die beschikbaar is in moderne SharePoint om contracten in een bedrijfsvriendelijke indeling te presenteren.</span><span class="sxs-lookup"><span data-stu-id="dc301-129">**Microsoft SharePoint lists**: Use the formatting available in modern SharePoint lists to present contracts in a business-friendly format.</span></span>

- <span data-ttu-id="dc301-130">**Microsoft Teams:** Gebruik de functionaliteit van een Teams kanaal en bijbehorende tabbladen om uw belanghebbenden in staat te stellen contracten te bekijken en te beheren.</span><span class="sxs-lookup"><span data-stu-id="dc301-130">**Microsoft Teams**: Use the functionality of a Teams channel and associated tabs to allow your stakeholders to review and manage contracts.</span></span>

- <span data-ttu-id="dc301-131">**Power Automate**: Gebruik stromen om contracten te begeleiden bij het goedkeuringsproces en vervolgens bij een aanvraag van derden om te betalen.</span><span class="sxs-lookup"><span data-stu-id="dc301-131">**Power Automate**: Use flows to guide contracts through the approval process, and then to a third-party application for payment.</span></span>

### <a name="how-it-all-works"></a><span data-ttu-id="dc301-132">Hoe het allemaal werkt</span><span class="sxs-lookup"><span data-stu-id="dc301-132">How it all works</span></span>

  ![Diagram van de oplossing met de werkstroom om documenten te uploaden, gegevens op te halen, belanghebbenden op de hoogte te stellen en het contract goed te keuren of af te wijzen.](../media/content-understanding/syntex-solution-manage-contracts-overview.png)

1. <span data-ttu-id="dc301-134">Documenten worden geüpload naar een SharePoint documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="dc301-134">Documents are uploaded to a SharePoint document library.</span></span> <span data-ttu-id="dc301-135">Er SharePoint Syntex documentkennismodel toegepast op de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="dc301-135">A SharePoint Syntex document understanding model has been applied to the document library.</span></span> <span data-ttu-id="dc301-136">Het controleert elk bestand om te zien of er een overeenkomst is met een 'contract'-inhoudstype dat is getraind om te zoeken.</span><span class="sxs-lookup"><span data-stu-id="dc301-136">It checks each file to see if any match a "contract" content type it's trained to look for.</span></span> <span data-ttu-id="dc301-137">Als er een overeenkomst wordt gevonden, wordt het bestand als een 'contract' classificeert en wordt het inhoudstype voor het document bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="dc301-137">If it finds a match, it classifies the file as a "contract" and updates the content type for the document.</span></span>

2. <span data-ttu-id="dc301-138">Het model haalt ook specifieke gegevens op uit elk contractbestand dat belanghebbenden willen zien, zoals de *klant,* de *contractant* en het *bedrag van de kosten.*</span><span class="sxs-lookup"><span data-stu-id="dc301-138">The model also pulls out specific data from each contract file that stakeholders are interested in seeing, such as the *Client*, *Contractor*, and *Fee amount*.</span></span>

    <span data-ttu-id="dc301-139">De volgende pagina is een voorbeeld van een contract dat het model is opgeleid om te identificeren.</span><span class="sxs-lookup"><span data-stu-id="dc301-139">The following page is an example of a contract that the model is trained to identify.</span></span>

      ![Voorbeeld van een contract.](../media/content-understanding/contract.png)

3. <span data-ttu-id="dc301-141">In Microsoft Teams zijn alle belanghebbenden lid van een beveiligd Teams kanaal waarin alle contracten in de documentbibliotheek zichtbaar zijn voor goedkeuring of afwijzing.</span><span class="sxs-lookup"><span data-stu-id="dc301-141">In Microsoft Teams, all stakeholders are members of a secure Teams channel in which all contracts in the document library are visible for approval or rejection.</span></span> <span data-ttu-id="dc301-142">Door de Teams gebruiken, worden alle belanghebbenden op de hoogte gesteld wanneer nieuwe contracten moeten worden gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="dc301-142">By using Teams functionality, all stakeholders are notified when new contracts need to be reviewed.</span></span>

4. <span data-ttu-id="dc301-143">Met Power Automate worden contracten verplaatst via het goedkeuringsproces in het Teams kanaal.</span><span class="sxs-lookup"><span data-stu-id="dc301-143">By using Power Automate, contracts are moved through the approval process in the Teams channel.</span></span> <span data-ttu-id="dc301-144">Wanneer een lid een contract goedkeurt, wordt de contractstatus gewijzigd in goedgekeurd, worden alle leden via een Teams-bericht op de hoogte gesteld en wordt er een regelitem gemaakt om aan te geven dat het contract gereed is voor uitbetaling.</span><span class="sxs-lookup"><span data-stu-id="dc301-144">When a member approves a contract, the contract status is changed to approved, all members are notified through a Teams post, and a line item is created to show that the contract is ready for payout.</span></span> <span data-ttu-id="dc301-145">Dit proces kan worden uitgebreid om rechtstreeks te schrijven naar een financiële toepassing van derden voor betaling.</span><span class="sxs-lookup"><span data-stu-id="dc301-145">This process can be extended to write directly to a third-party financial application for payment.</span></span>

5. <span data-ttu-id="dc301-146">Wanneer een lid een contract weigert, wordt de status gewijzigd in geweigerd en worden alle leden op de hoogte gesteld via Teams bericht.</span><span class="sxs-lookup"><span data-stu-id="dc301-146">When a member rejects a contract, the status is changed to rejected, and all members are notified through a Teams post.</span></span>

6. <span data-ttu-id="dc301-147">Het eindresultaat van deze oplossing is een geautomatiseerd bedrijfsproces voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="dc301-147">The end result of this solution is an automated business process for your organization.</span></span> <span data-ttu-id="dc301-148">Werknemers kunnen eenvoudig de aangepaste tegelweergave in Teams om de goedkeuringswerkstroom van uw documenten te starten en te controleren.</span><span class="sxs-lookup"><span data-stu-id="dc301-148">Employees can easily use the custom tile view in Teams to initiate and monitor the approval workflow of your documents.</span></span> 

     ![Tabblad Contracten.](../media/content-understanding/tile-view.png)

### <a name="licensing-requirements"></a><span data-ttu-id="dc301-150">Licentievereisten</span><span class="sxs-lookup"><span data-stu-id="dc301-150">Licensing requirements</span></span>

<span data-ttu-id="dc301-151">Deze oplossing is afhankelijk van de volgende functionaliteit, die allemaal beschikbaar is als onderdeel van een licentie voor Microsoft 365 Enterprise (E1, E3, E5, F3) of Business (Basic, Standard of Premium) :</span><span class="sxs-lookup"><span data-stu-id="dc301-151">This solution relies on the following functionality, all available as part of a Microsoft 365 Enterprise (E1, E3, E5, F3) or Business (Basic, Standard, or Premium) license:</span></span>

- <span data-ttu-id="dc301-152">Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="dc301-152">Microsoft SharePoint Syntex</span></span>
- <span data-ttu-id="dc301-153">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dc301-153">Microsoft Teams</span></span>
- <span data-ttu-id="dc301-154">Power Automate</span><span class="sxs-lookup"><span data-stu-id="dc301-154">Power Automate</span></span>

## <a name="create-the-solution"></a><span data-ttu-id="dc301-155">De oplossing maken</span><span class="sxs-lookup"><span data-stu-id="dc301-155">Create the solution</span></span>

<span data-ttu-id="dc301-156">In de volgende secties wordt in detail beschreven hoe u de oplossing voor contractbeheer configureert.</span><span class="sxs-lookup"><span data-stu-id="dc301-156">The next sections will go into detail about how to configure your contracts management solution.</span></span> <span data-ttu-id="dc301-157">Het is onderverdeeld in drie stappen:</span><span class="sxs-lookup"><span data-stu-id="dc301-157">It's divided into three steps:</span></span>

- [<span data-ttu-id="dc301-158">Stap 1. Gebruik SharePoint Syntex om contractbestanden te identificeren en gegevens op te halen</span><span class="sxs-lookup"><span data-stu-id="dc301-158">Step 1. Use SharePoint Syntex to identify contract files and extract data</span></span>](solution-manage-contracts-step1.md)
- [<span data-ttu-id="dc301-159">Stap 2. Gebruik Microsoft Teams om uw contractbeheerkanaal te maken</span><span class="sxs-lookup"><span data-stu-id="dc301-159">Step 2. Use Microsoft Teams to create your contract management channel</span></span>](solution-manage-contracts-step2.md)
- [<span data-ttu-id="dc301-160">Stap 3. Gebruik Power Automate om uw stroom te maken om uw contracten te verwerken</span><span class="sxs-lookup"><span data-stu-id="dc301-160">Step 3. Use Power Automate to create your flow to process your contracts</span></span>](solution-manage-contracts-step3.md)
