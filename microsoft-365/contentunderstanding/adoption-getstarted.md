---
title: 'Microsoft SharePoint Syntex: Aan de slag'
description: Meer informatie over het gebruik en implementeren SharePoint Syntex in uw organisatie om u te helpen uw zakelijke problemen op te lossen.
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 8a5442fcf8dd50cdee6be97ba7c9bbf5e21408a3
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288153"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a><span data-ttu-id="14142-103">Microsoft SharePoint Syntex: Aan de slag</span><span class="sxs-lookup"><span data-stu-id="14142-103">Microsoft SharePoint Syntex adoption: Get started</span></span>

<span data-ttu-id="14142-104">Denk aan de intelligente inhoudsservices die beschikbaar zijn in SharePoint Syntex als drie onderdelen:</span><span class="sxs-lookup"><span data-stu-id="14142-104">Think of the intelligent content services available in SharePoint Syntex as having three parts:</span></span>

- <span data-ttu-id="14142-105">**Inhoudskennis:** Maak AI-modellen zonder code voor het classificeren en extraheren van informatie uit inhoud om metagegevens automatisch toe te passen voor kennisdetectie en hergebruik.</span><span class="sxs-lookup"><span data-stu-id="14142-105">**Content understanding:** Create no-code AI models to classify and extract information from content to automatically apply metadata for knowledge discovery and reuse.</span></span> <span data-ttu-id="14142-106">Meer informatie over [het begrijpen van inhoud.](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="14142-106">Learn more about [content understanding](document-understanding-overview.md).</span></span>
- <span data-ttu-id="14142-107">**Inhoudsverwerking:** Automatiseer het vastleggen, opnemen en categoriseren van inhoud en stroomlijn inhoudsgerichte processen met behulp van Power Automate.</span><span class="sxs-lookup"><span data-stu-id="14142-107">**Content processing:** Automate capture, ingestion, and categorization of content and streamline content-centric processes using Power Automate.</span></span> <span data-ttu-id="14142-108">Meer informatie over [inhoudsverwerking.](form-processing-overview.md)</span><span class="sxs-lookup"><span data-stu-id="14142-108">Learn more about [content processing](form-processing-overview.md).</span></span>
- <span data-ttu-id="14142-109">**Naleving van inhoud:** Beheer en beheer inhoud om de beveiliging en het beheer te verbeteren met integratie in Microsoft Information Protection.</span><span class="sxs-lookup"><span data-stu-id="14142-109">**Content compliance:** Control and manage content to improve security and governance with integration to Microsoft Information Protection.</span></span>

<span data-ttu-id="14142-110">Met nieuwe AI-services en -mogelijkheden kunt u apps voor inhoudskennis en classificatie rechtstreeks in de inhoudsbeheerstroom bouwen met SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="14142-110">With new AI services and capabilities, you can build content understanding and classification apps directly into the content management flow using SharePoint Syntex.</span></span> <span data-ttu-id="14142-111">Er zijn twee verschillende manieren om uw inhoud te begrijpen.</span><span class="sxs-lookup"><span data-stu-id="14142-111">There are two different ways of understanding your content.</span></span> <span data-ttu-id="14142-112">Het modeltype dat u gebruikt, is gebaseerd op bestandsindeling en use case:</span><span class="sxs-lookup"><span data-stu-id="14142-112">The model type you use is based on file format and use case:</span></span>

| <span data-ttu-id="14142-113">Formulierverwerking</span><span class="sxs-lookup"><span data-stu-id="14142-113">Form processing</span></span> | <span data-ttu-id="14142-114">Documentbegrip</span><span class="sxs-lookup"><span data-stu-id="14142-114">Document understanding</span></span> |
|:-------|:-------|
| <span data-ttu-id="14142-115">Gemaakt vanuit documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="14142-115">Created from document library.</span></span> | <span data-ttu-id="14142-116">Gemaakt in het inhoudscentrum, onderdeel van SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="14142-116">Created in the content center, part of SharePoint Syntex.</span></span> |
| <span data-ttu-id="14142-117">Model gemaakt in AI builder.</span><span class="sxs-lookup"><span data-stu-id="14142-117">Model created in AI builder.</span></span> | <span data-ttu-id="14142-118">Model gemaakt in de eigen interface.</span><span class="sxs-lookup"><span data-stu-id="14142-118">Model created in native interface.</span></span> |
| <span data-ttu-id="14142-119">Wordt gebruikt voor semi-gestructureerde bestandsindelingen.</span><span class="sxs-lookup"><span data-stu-id="14142-119">Used for semi-structured file formats.</span></span> | <span data-ttu-id="14142-120">Wordt gebruikt voor ongestructureerde bestandsindelingen.</span><span class="sxs-lookup"><span data-stu-id="14142-120">Used for unstructured file formats.</span></span> |
| <span data-ttu-id="14142-121">Settable classifier.</span><span class="sxs-lookup"><span data-stu-id="14142-121">Settable classifier.</span></span> | <span data-ttu-id="14142-122">Trainable classifier with optional extractors.</span><span class="sxs-lookup"><span data-stu-id="14142-122">Trainable classifier with optional extractors.</span></span> |
| <span data-ttu-id="14142-123">Beperkt tot één bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="14142-123">Restricted to a single library.</span></span> | <span data-ttu-id="14142-124">Kan worden toegepast op meerdere bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="14142-124">Can be applied to multiple libraries.</span></span> |
| <span data-ttu-id="14142-125">Train op PDF, JPG, PNG-indeling, totaal 50 MB/500 pp.</span><span class="sxs-lookup"><span data-stu-id="14142-125">Train on PDF, JPG, PNG format, total 50 MB/500 pp.</span></span> | <span data-ttu-id="14142-126">Trainen op 5 tot 10 pdf-, Office- of e-mailbestanden, inclusief negatieve voorbeelden.</span><span class="sxs-lookup"><span data-stu-id="14142-126">Train on 5-10 PDF, Office, or email files, including negative examples.</span></span> |

<span data-ttu-id="14142-127">Zie Verschillen tussen documentkennis en formulierverwerkingsmodellen voor een completere vergelijking van [de mogelijkheden.](difference-between-document-understanding-and-form-processing-model.md)</span><span class="sxs-lookup"><span data-stu-id="14142-127">For a more complete comparison of the capabilities, see [Difference between document understanding and form processing models](difference-between-document-understanding-and-form-processing-model.md).</span></span>

## <a name="identify-pilot-business-scenarios-to-optimize"></a><span data-ttu-id="14142-128">Testscenario's identificeren om te optimaliseren</span><span class="sxs-lookup"><span data-stu-id="14142-128">Identify pilot business scenarios to optimize</span></span>

<span data-ttu-id="14142-129">Als u zich wilt voorbereiden SharePoint Syntex in uw organisatie, moet u eerst de scenario's begrijpen waarin deze nuttig zijn.</span><span class="sxs-lookup"><span data-stu-id="14142-129">To prepare for using SharePoint Syntex in your organization, you first need to understand the scenarios in which it will be useful.</span></span> <span data-ttu-id="14142-130">Het 'waarom' helpt bepalen welk model nodig is en hoe u uw organisatie structureert op basis van waar het model wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="14142-130">The "why" helps determine what model will be needed, and how to structure your org based on where the model will be applied.</span></span> <span data-ttu-id="14142-131">Hier zijn een paar scenario's waarin het begrijpen van documenten uw organisatie kan helpen:</span><span class="sxs-lookup"><span data-stu-id="14142-131">Here are a few scenarios where document understanding can help your organization:</span></span>

- <span data-ttu-id="14142-132">**Inhoudsverwerking:** Procescontracten, werkafschriften en andere formulier-achtige documenten.</span><span class="sxs-lookup"><span data-stu-id="14142-132">**Content processing:** Process contracts, statements of work, and other form-like documents.</span></span> <span data-ttu-id="14142-133">Neem de formulieren op, train het model om de velden te begrijpen en toe te geven en voer de formulieren door om de gegevens automatisch te verzamelen.</span><span class="sxs-lookup"><span data-stu-id="14142-133">Intake the forms, train the model to understand and map the fields, and then run your forms through to automatically collect the data.</span></span> <span data-ttu-id="14142-134">Zie Formulierverwerkingsoverzicht [voor meer informatie.](form-processing-overview.md)</span><span class="sxs-lookup"><span data-stu-id="14142-134">For more information, see [Form processing overview](form-processing-overview.md).</span></span>
- <span data-ttu-id="14142-135">**Factuuranalyse:** Haal de relevante gegevens uit uw facturen en zorg ervoor dat ze voldoen aan het beleid of op de juiste manier worden verwerkt.</span><span class="sxs-lookup"><span data-stu-id="14142-135">**Invoice analysis:** Pull out the relevant details from your invoices and make sure they're complying with policy or are being processed appropriately.</span></span>

<span data-ttu-id="14142-136">Denk na over manieren SharePoint Syntex uw organisatie kan helpen:</span><span class="sxs-lookup"><span data-stu-id="14142-136">Think about ways that SharePoint Syntex can help your organization:</span></span>

- <span data-ttu-id="14142-137">Bedrijfsprocessen automatiseren</span><span class="sxs-lookup"><span data-stu-id="14142-137">Automate business processes</span></span>
- <span data-ttu-id="14142-138">Zoeknauwkeurigheid verbeteren</span><span class="sxs-lookup"><span data-stu-id="14142-138">Improve search accuracy</span></span>
- <span data-ttu-id="14142-139">Compliancerisico's beheren</span><span class="sxs-lookup"><span data-stu-id="14142-139">Manage compliance risk</span></span>

<span data-ttu-id="14142-140">Als u bedenkt welke zakelijke scenario's u moet overwegen, stelt u zich de volgende vragen:</span><span class="sxs-lookup"><span data-stu-id="14142-140">When thinking about which business scenarios to consider, ask yourself the following questions:</span></span>

- <span data-ttu-id="14142-141">Lost dit een echt probleem op?</span><span class="sxs-lookup"><span data-stu-id="14142-141">Does it solve a real problem?</span></span>
- <span data-ttu-id="14142-142">Wordt het veel gebruikt of heeft het een grote impact?</span><span class="sxs-lookup"><span data-stu-id="14142-142">Will it be widely used or have broad impact?</span></span>
- <span data-ttu-id="14142-143">Is het verkrijgbaar?</span><span class="sxs-lookup"><span data-stu-id="14142-143">Is it obtainable?</span></span>
- <span data-ttu-id="14142-144">Kunt u succes meten?</span><span class="sxs-lookup"><span data-stu-id="14142-144">Can you measure success?</span></span>

<span data-ttu-id="14142-145">Geef prioriteit aan scenario's op basis van impact en implementatiegemak.</span><span class="sxs-lookup"><span data-stu-id="14142-145">Prioritize scenarios based on impact and ease of implementation.</span></span> <span data-ttu-id="14142-146">Maak uw eerste focusgebied groter effectscenario's die ook eenvoudig kunnen worden geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="14142-146">Make your initial focus area higher impact scenarios that can also be easily implemented.</span></span> <span data-ttu-id="14142-147">Geef prioriteit aan scenario's met lagere effecten die moeilijk te implementeren zijn.</span><span class="sxs-lookup"><span data-stu-id="14142-147">De-prioritize lower impact scenarios that are hard to implement.</span></span>

<span data-ttu-id="14142-148">Gebruik de [voorbeeldscenario's en gebruik cases om](adoption-scenarios.md) ideeën te vragen over hoe u uw SharePoint Syntex in uw organisatie kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="14142-148">Use the [example scenarios and use cases](adoption-scenarios.md) to prompt ideas about how you can use SharePoint Syntex in your organization.</span></span>

## <a name="identify-roles--responsibilities"></a><span data-ttu-id="14142-149">Rollen en & verantwoordelijkheden identificeren</span><span class="sxs-lookup"><span data-stu-id="14142-149">Identify roles & responsibilities</span></span>

<span data-ttu-id="14142-150">Bepalen wie in uw organisatie de modellen gaat maken en beheren?</span><span class="sxs-lookup"><span data-stu-id="14142-150">Determine who in your organization will build and manage the models?</span></span> <span data-ttu-id="14142-151">Mogelijk gaat het om de volgende rollen:</span><span class="sxs-lookup"><span data-stu-id="14142-151">The following roles might be involved:</span></span>

| <span data-ttu-id="14142-152">SharePoint/Knowledge Admin</span><span class="sxs-lookup"><span data-stu-id="14142-152">SharePoint/Knowledge admin</span></span> | <span data-ttu-id="14142-153">Power Platform-beheerder</span><span class="sxs-lookup"><span data-stu-id="14142-153">Power Platform admin</span></span> | <span data-ttu-id="14142-154">Knowledge manager</span><span class="sxs-lookup"><span data-stu-id="14142-154">Knowledge manager</span></span> | <span data-ttu-id="14142-155">Modeleigenaar</span><span class="sxs-lookup"><span data-stu-id="14142-155">Model owner</span></span> |
|:-------|:-------|:-------|:-------|
| <span data-ttu-id="14142-156">AAD-rol</span><span class="sxs-lookup"><span data-stu-id="14142-156">AAD role</span></span>| <span data-ttu-id="14142-157">AAD-rol</span><span class="sxs-lookup"><span data-stu-id="14142-157">AAD role</span></span> | <span data-ttu-id="14142-158">AAD-rol</span><span class="sxs-lookup"><span data-stu-id="14142-158">AAD role</span></span> | <span data-ttu-id="14142-159">Kampioenen</span><span class="sxs-lookup"><span data-stu-id="14142-159">Champions</span></span> |
| <span data-ttu-id="14142-160">Formulierverwerking configureren</span><span class="sxs-lookup"><span data-stu-id="14142-160">Configure form processing</span></span> | <span data-ttu-id="14142-161">Algemene gegevensserviceomgeving configureren voor formulierverwerking</span><span class="sxs-lookup"><span data-stu-id="14142-161">Configure Common data service environment for form processing</span></span> | <span data-ttu-id="14142-162">Gebruiksgevallen verzamelen</span><span class="sxs-lookup"><span data-stu-id="14142-162">Gather use cases</span></span> | <span data-ttu-id="14142-163">Zakelijke gebruiksgevallen verzamelen</span><span class="sxs-lookup"><span data-stu-id="14142-163">Gather business use cases</span></span> |
| <span data-ttu-id="14142-164">Inhoudscentra en machtigingen beheren</span><span class="sxs-lookup"><span data-stu-id="14142-164">Manage content centers and permissions</span></span>| <span data-ttu-id="14142-165">AIB-tegoed kopen en toewijzen</span><span class="sxs-lookup"><span data-stu-id="14142-165">Purchase and allocate AIB credits</span></span> | <span data-ttu-id="14142-166">Best practices opstellen en modelanalyses bekijken</span><span class="sxs-lookup"><span data-stu-id="14142-166">Establish best practices and review model analytics</span></span> | <span data-ttu-id="14142-167">Modellen maken en toepassen</span><span class="sxs-lookup"><span data-stu-id="14142-167">Create and apply models</span></span> |

<span data-ttu-id="14142-168">Knowledge manager, Eigenaar van bedrijfsprocessen en eigenaar van inhoudsmodellen maken voorbeeldmodellen en maken de acceptatie in de organisatie voor.</span><span class="sxs-lookup"><span data-stu-id="14142-168">Knowledge manager, Business Process Owner and Content model owner create sample models and champion adoption in the organization.</span></span>
<span data-ttu-id="14142-169">Anderen die mogelijk betrokken zijn: Compliancebeheerder, Taxonomiebeheerders.</span><span class="sxs-lookup"><span data-stu-id="14142-169">Others who may be involved: Compliance admin, Taxonomy managers.</span></span>

<span data-ttu-id="14142-170">Waar worden de modellen gebouwd en toegepast?</span><span class="sxs-lookup"><span data-stu-id="14142-170">Where will they build and apply the models?</span></span> <span data-ttu-id="14142-171">Zijn er bestaande processen of opslagplaatsen die kunnen worden verbeterd?</span><span class="sxs-lookup"><span data-stu-id="14142-171">Are there existing processes or repositories that could be enhanced?</span></span>

- <span data-ttu-id="14142-172">Formulierverwerking: bepaal welke sites actie voor formulierverwerking krijgen.</span><span class="sxs-lookup"><span data-stu-id="14142-172">Form processing: Decide which sites will get Form processing action.</span></span>
- <span data-ttu-id="14142-173">Documentkennis: U kunt meerdere inhoudscentra maken voor verschillende zakelijke gebieden.</span><span class="sxs-lookup"><span data-stu-id="14142-173">Document understanding: You can create multiple content centers for different business areas.</span></span>

## <a name="strategic-positioning"></a><span data-ttu-id="14142-174">Strategische positionering</span><span class="sxs-lookup"><span data-stu-id="14142-174">Strategic positioning</span></span>

<span data-ttu-id="14142-175">Werk samen met belanghebbenden om ervoor te zorgen dat ze zijn afgestemd op de strategie voor het gebruik van SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="14142-175">Work with stakeholders to make sure they are aligned on the strategy for using SharePoint Syntex.</span></span> <span data-ttu-id="14142-176">Onderzoek en geef de volgende informatiebronnen om u te helpen bij deze positionering:</span><span class="sxs-lookup"><span data-stu-id="14142-176">Research and provide the following resources to help with this positioning:</span></span>

- <span data-ttu-id="14142-177">Bedrijfsresultaten:</span><span class="sxs-lookup"><span data-stu-id="14142-177">Business outcomes:</span></span>
  - <span data-ttu-id="14142-178">Mogelijke fiscale resultaten</span><span class="sxs-lookup"><span data-stu-id="14142-178">Potential fiscal outcomes</span></span>
  - <span data-ttu-id="14142-179">Mogelijke resultaten van flexibiliteit</span><span class="sxs-lookup"><span data-stu-id="14142-179">Potential agility outcomes</span></span>
  - <span data-ttu-id="14142-180">Sjabloon voor bedrijfsresultaten</span><span class="sxs-lookup"><span data-stu-id="14142-180">Business outcome template</span></span>
- <span data-ttu-id="14142-181">Stakeholders/Exec sponsor buy-in/alignment</span><span class="sxs-lookup"><span data-stu-id="14142-181">Stakeholders/Exec sponsor buy-in/alignment</span></span>
  - <span data-ttu-id="14142-182">Business case decks</span><span class="sxs-lookup"><span data-stu-id="14142-182">Business case decks</span></span>
  - <span data-ttu-id="14142-183">Financiële modellen</span><span class="sxs-lookup"><span data-stu-id="14142-183">Financial models</span></span>
  - <span data-ttu-id="14142-184">Bedrijfsbereidheid - cultuur</span><span class="sxs-lookup"><span data-stu-id="14142-184">Company readiness - culture</span></span>

## <a name="identify-stakeholders"></a><span data-ttu-id="14142-185">Belanghebbenden identificeren</span><span class="sxs-lookup"><span data-stu-id="14142-185">Identify stakeholders</span></span>

<span data-ttu-id="14142-186">Identificeer de belanghebbenden voor uw project.</span><span class="sxs-lookup"><span data-stu-id="14142-186">Identify the stakeholders for your project.</span></span>

|<span data-ttu-id="14142-187">Rol</span><span class="sxs-lookup"><span data-stu-id="14142-187">Role</span></span> |<span data-ttu-id="14142-188">Verantwoordelijkheden</span><span class="sxs-lookup"><span data-stu-id="14142-188">Responsibilities</span></span> |<span data-ttu-id="14142-189">Department</span><span class="sxs-lookup"><span data-stu-id="14142-189">Department</span></span> |
|:-------|:-------|:--------|
| <span data-ttu-id="14142-190">Executive sponsor(s)</span><span class="sxs-lookup"><span data-stu-id="14142-190">Executive sponsor(s)</span></span>   | <span data-ttu-id="14142-191">Visie en waarden op hoog niveau communiceren met het bedrijf</span><span class="sxs-lookup"><span data-stu-id="14142-191">Communicate high-level vision and values to the company</span></span>   |  <span data-ttu-id="14142-192">Uitvoerend leiderschap</span><span class="sxs-lookup"><span data-stu-id="14142-192">Executive leadership</span></span>   |
| <span data-ttu-id="14142-193">Project lead(en)</span><span class="sxs-lookup"><span data-stu-id="14142-193">Project lead(s)</span></span> | <span data-ttu-id="14142-194">Toezicht houden op het volledige proces voor het uitvoeren en uitrollen van de lancering</span><span class="sxs-lookup"><span data-stu-id="14142-194">Oversee the entire launch execution and rollout process</span></span> | <span data-ttu-id="14142-195">Project beheer</span><span class="sxs-lookup"><span data-stu-id="14142-195">Project management</span></span> |
| <span data-ttu-id="14142-196">Kennisbeheerders</span><span class="sxs-lookup"><span data-stu-id="14142-196">Knowledge administrators</span></span>| <span data-ttu-id="14142-197">De inhoudscentra maken en beheren</span><span class="sxs-lookup"><span data-stu-id="14142-197">Create and manage the content centers</span></span> | <span data-ttu-id="14142-198">IT of andere afdeling</span><span class="sxs-lookup"><span data-stu-id="14142-198">IT or other department</span></span>|
| <span data-ttu-id="14142-199">Inhoudsmanagers en modeleigenaars</span><span class="sxs-lookup"><span data-stu-id="14142-199">Content managers and model owners</span></span>| <span data-ttu-id="14142-200">Use cases verzamelen en modellen maken en toepassen</span><span class="sxs-lookup"><span data-stu-id="14142-200">Gather use cases and create and apply models</span></span> | <span data-ttu-id="14142-201">Elke afdeling</span><span class="sxs-lookup"><span data-stu-id="14142-201">Any department</span></span>|
| <span data-ttu-id="14142-202">Kampioenen</span><span class="sxs-lookup"><span data-stu-id="14142-202">Champions</span></span> | <span data-ttu-id="14142-203">Hulp bij het evangeliseren en beheren van bezwaarafhandeling</span><span class="sxs-lookup"><span data-stu-id="14142-203">Help evangelize and manage objection handling</span></span> | <span data-ttu-id="14142-204">Elke afdeling (personeel)</span><span class="sxs-lookup"><span data-stu-id="14142-204">Any department (staff)</span></span> |
| <span data-ttu-id="14142-205">Tenantbeheerder</span><span class="sxs-lookup"><span data-stu-id="14142-205">Tenant administrator</span></span> | <span data-ttu-id="14142-206">Instellingen op tenantniveau configureren</span><span class="sxs-lookup"><span data-stu-id="14142-206">Configure tenant-level settings</span></span> | <span data-ttu-id="14142-207">IT-afdeling</span><span class="sxs-lookup"><span data-stu-id="14142-207">IT department</span></span>|
| <span data-ttu-id="14142-208">Power Platform-beheerder</span><span class="sxs-lookup"><span data-stu-id="14142-208">Power Platform administrator</span></span>| <span data-ttu-id="14142-209">Veelgebruikte omgeving voor gegevensservices configureren</span><span class="sxs-lookup"><span data-stu-id="14142-209">Configure common data services environment</span></span> | <span data-ttu-id="14142-210">IT-afdeling</span><span class="sxs-lookup"><span data-stu-id="14142-210">IT department</span></span>|

> [!Note]
> <span data-ttu-id="14142-211">Hoewel we u adviseren om elk van deze rollen tijdens de implementatie te laten vervullen, is het mogelijk dat u ze niet allemaal nodig hebt om aan de slag te gaan met uw geïdentificeerde oplossing.</span><span class="sxs-lookup"><span data-stu-id="14142-211">Though we recommend having each of these roles fulfilled throughout your rollout, you may find that you don't require them all to get started with your identified solution.</span></span>

## <a name="readiness-checklist"></a><span data-ttu-id="14142-212">Controlelijst gereedheid</span><span class="sxs-lookup"><span data-stu-id="14142-212">Readiness checklist</span></span>

<span data-ttu-id="14142-213">Als u klaar wilt zijn voor het implementeren SharePoint Syntex, moet u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="14142-213">To get ready for implementing SharePoint Syntex, you need to:</span></span>

![Gereedheid voor inhoudskennis](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. <span data-ttu-id="14142-215">De eindtoestand plannen</span><span class="sxs-lookup"><span data-stu-id="14142-215">Plan the end state</span></span>
    - <span data-ttu-id="14142-216">Documentkennismodellen zijn de middelen, niet het einde.</span><span class="sxs-lookup"><span data-stu-id="14142-216">Document understanding models are the means, not the end.</span></span>
    - <span data-ttu-id="14142-217">Plan voor het benutten van de waarde van geëxtraheerde metagegevens met:</span><span class="sxs-lookup"><span data-stu-id="14142-217">Plan for harnessing the value of extracted metadata with:</span></span>
      - <span data-ttu-id="14142-218">Zoeken</span><span class="sxs-lookup"><span data-stu-id="14142-218">Search</span></span>
      - <span data-ttu-id="14142-219">Opmaak filteren en weergeven</span><span class="sxs-lookup"><span data-stu-id="14142-219">Filtering and view formatting</span></span>
      - <span data-ttu-id="14142-220">Compliance</span><span class="sxs-lookup"><span data-stu-id="14142-220">Compliance</span></span>
      - <span data-ttu-id="14142-221">Automatisering</span><span class="sxs-lookup"><span data-stu-id="14142-221">Automation</span></span>
2. <span data-ttu-id="14142-222">Identificeren</span><span class="sxs-lookup"><span data-stu-id="14142-222">Identify</span></span>
    - <span data-ttu-id="14142-223">Inzicht in bestaande functies voor informatiearchitectuur en inhoudsbeheer.</span><span class="sxs-lookup"><span data-stu-id="14142-223">Understand existing information architecture and content management feature use.</span></span>
    - <span data-ttu-id="14142-224">Zijn bestaande inhoudstypen goede kandidaten voor modellen?</span><span class="sxs-lookup"><span data-stu-id="14142-224">Are any existing content types good candidates for models?</span></span>
    - <span data-ttu-id="14142-225">Welke bestaande processen worden verbeterd met metagegevens?</span><span class="sxs-lookup"><span data-stu-id="14142-225">What existing processes would be improved by metadata?</span></span>
3. <span data-ttu-id="14142-226">Design</span><span class="sxs-lookup"><span data-stu-id="14142-226">Design</span></span>
    - <span data-ttu-id="14142-227">Ontwerp uw benadering van informatiearchitectuur, beheerde metagegevens en inhoudstypen.</span><span class="sxs-lookup"><span data-stu-id="14142-227">Design your approach to information architecture, managed metadata and content types.</span></span>
    - <span data-ttu-id="14142-228">Ontwerp het proces voor definitie, creatie, beheer.</span><span class="sxs-lookup"><span data-stu-id="14142-228">Design the process for definition, creation, management.</span></span>

## <a name="engage-your-organization"></a><span data-ttu-id="14142-229">Uw organisatie betrekken</span><span class="sxs-lookup"><span data-stu-id="14142-229">Engage your organization</span></span>

1. <span data-ttu-id="14142-230">Identificeer ringhouders, bevestig scenario's en ontwikkel projectplannen.</span><span class="sxs-lookup"><span data-stu-id="14142-230">Identify stake holders, confirm scenarios, and develop project plan.</span></span>
1. <span data-ttu-id="14142-231">Instellingen configureren en licenties toepassen.</span><span class="sxs-lookup"><span data-stu-id="14142-231">Configure settings and apply licenses.</span></span>
1. <span data-ttu-id="14142-232">Begin bewust te worden en training te volgen: wervingskampioenen.</span><span class="sxs-lookup"><span data-stu-id="14142-232">Begin awareness and training – Recruit Champions.</span></span>
1. <span data-ttu-id="14142-233">Rol in fasen uit.</span><span class="sxs-lookup"><span data-stu-id="14142-233">Roll out in stages.</span></span>  
1. <span data-ttu-id="14142-234">Feedback verzamelen en itereren.</span><span class="sxs-lookup"><span data-stu-id="14142-234">Gather feedback and iterate.</span></span>
1. <span data-ttu-id="14142-235">Naarmate het gebruik toeneemt, wordt het plan voor eventuele AI Builder-tegoeden zo nodig groter.</span><span class="sxs-lookup"><span data-stu-id="14142-235">As usage grows plan for any AI Builder credits as needed.</span></span>

## <a name="see-also"></a><span data-ttu-id="14142-236">Zie ook</span><span class="sxs-lookup"><span data-stu-id="14142-236">See also</span></span>

[<span data-ttu-id="14142-237">Scenario's en use cases voor SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="14142-237">Scenarios and use cases for SharePoint Syntex</span></span>](adoption-scenarios.md)
