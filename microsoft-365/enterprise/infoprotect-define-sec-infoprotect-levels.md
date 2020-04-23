---
title: 'Stap 1: beveiligings- en gegevensbeschermingsniveaus definiëren'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Beveiligings- en gegevensbeschermingsniveaus begrijpen en configureren voor uw organisatie.
ms.openlocfilehash: 0fa3e9fa11070ea505752d781ecdd21b344c8222
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636962"
---
# <a name="step-1-define-security-and-information-protection-levels"></a><span data-ttu-id="c8f43-103">Stap 1: beveiligings- en gegevensbeschermingsniveaus definiëren</span><span class="sxs-lookup"><span data-stu-id="c8f43-103">Step 1: Define security and information protection levels</span></span>

<span data-ttu-id="c8f43-104">*Deze stap is vereist en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="c8f43-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 6: gegevensbescherming](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="c8f43-106">In deze stap definieert u het beveiligingsniveau en de beveiliging voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="c8f43-106">In this step, you'll define the levels of security and protection for your organization.</span></span> <span data-ttu-id="c8f43-107">De afdeling verkoop heeft bijvoorbeeld mogelijk slechts een laag beveiligingsniveau nodig.</span><span class="sxs-lookup"><span data-stu-id="c8f43-107">For example, your sales department might only require a low security level.</span></span> <span data-ttu-id="c8f43-108">Het kan echter zijn dat uw onderzoeksafdeling en haar zeer waardevolle intellectuele eigendom een hoog beveiligingsniveau vereisen, waarbij bestanden worden gecodeerd en de toegang wordt beperkt tot alleen onderzoekspersoneel.</span><span class="sxs-lookup"><span data-stu-id="c8f43-108">However, your research department and its highly valuable intellectual property might require a high security level that encrypts files and limits access to only research staff.</span></span>

<span data-ttu-id="c8f43-109">Hoewel u uw eigen beveiligingsniveaus kunt definiëren en er mogelijk al een hebt, raadt Microsoft u aan een plan te ontwikkelen om ten minste drie verschillende beveiligings- en beschermingsniveaus te gebruiken die kunnen worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="c8f43-109">Although you can define your own security levels and might already have some in place, Microsoft recommends that you develop a plan to use at least three different levels of security and protection that can be applied.</span></span> <span data-ttu-id="c8f43-110">Dit is een lijst om u op weg te helpen:</span><span class="sxs-lookup"><span data-stu-id="c8f43-110">Here is a list to get you started:</span></span> 

- <span data-ttu-id="c8f43-111">**Basislijn:** Dit is een minimale norm voor de bescherming van gegevens en de identiteiten en apparaten die toegang hebben tot uw gegevens.</span><span class="sxs-lookup"><span data-stu-id="c8f43-111">**Baseline:** This is a minimum standard for protecting data and for the identities and devices that access your data.</span></span> <span data-ttu-id="c8f43-112">U kunt de basisaanbevelingen voor beveiliging en bescherming opvolgen en zo een sterke standaardbescherming bieden die voldoet aan de behoeften van veel organisaties en hun afdelingen.</span><span class="sxs-lookup"><span data-stu-id="c8f43-112">You can follow baseline security and protection recommendations to provide strong default protection that meets the needs of many organizations or their departments.</span></span>
- <span data-ttu-id="c8f43-113">**Vertrouwelijk:** dit is aanvullende bescherming voor een subverzameling van uw gegevens die beter moeten worden beschermd dan de basisbescherming.</span><span class="sxs-lookup"><span data-stu-id="c8f43-113">**Sensitive:** This is additional protection for a subset of your data that must be protected beyond the baseline level.</span></span> <span data-ttu-id="c8f43-114">U kunt deze verhoogde beveiliging toepassen op specifieke gegevenssets in uw Microsoft 365-omgeving.</span><span class="sxs-lookup"><span data-stu-id="c8f43-114">You can apply this increased protection to specific data sets in your Microsoft 365 environment.</span></span> <span data-ttu-id="c8f43-115">Microsoft raadt ook aan om het vertrouwelijke beveiligingsniveau toe te passen op identiteiten en apparaten die toegang hebben tot vertrouwelijke gegevens.</span><span class="sxs-lookup"><span data-stu-id="c8f43-115">Microsoft also recommends applying the sensitive security level to identities and devices that access sensitive data.</span></span>
- <span data-ttu-id="c8f43-116">**Sterk gereguleerd:** dit is het hoogste beschermingsniveau voor organisaties die doorgaans een zeer kleine hoeveelheid gegevens hebben die hoog geclassificeerd zijn, beschouwd worden als intellectueel eigendom of bedrijfsgeheimen, of gegevens die moeten voldoen aan strikte beveiligingsregels.</span><span class="sxs-lookup"><span data-stu-id="c8f43-116">**Highly regulated:** This is the highest level of protection for organizations that typically have a very small amount of data that is highly classified, considered intellectual property or trade secrets, or data that must adhere to strict security regulations.</span></span> <span data-ttu-id="c8f43-117">Microsoft 365 Enterprise biedt mogelijkheden om organisaties te helpen tegemoet te komen aan deze strenge beveiligingsvereisten, waaronder gelijkwaardige bescherming voor identiteiten en apparaten.</span><span class="sxs-lookup"><span data-stu-id="c8f43-117">Microsoft 365 Enterprise has capabilities to help organizations meet these high security requirements, including equivalent protection for identities and devices.</span></span>

<span data-ttu-id="c8f43-118">Zie [Drie beschermingsniveaus](microsoft-365-policies-configurations.md#three-tiers-of-protection) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c8f43-118">For more information, see [Three tiers of protection](microsoft-365-policies-configurations.md#three-tiers-of-protection).</span></span>

<span data-ttu-id="c8f43-119">Als tussentijds controlepunt kunt u de [afsluitcriteria](infoprotect-exit-criteria.md#crit-infoprotect-step1) voor deze stap bekijken.</span><span class="sxs-lookup"><span data-stu-id="c8f43-119">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step1) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="c8f43-120">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="c8f43-120">Next step</span></span>

|||
|:-------|:-----|
|![Stap 2](../media/stepnumbers/Step2.png)|[<span data-ttu-id="c8f43-122">Classificatie voor uw omgeving configureren</span><span class="sxs-lookup"><span data-stu-id="c8f43-122">Configure classification for your environment</span></span>](infoprotect-configure-classification.md)|
