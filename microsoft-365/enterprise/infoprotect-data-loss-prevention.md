---
title: 'Stap 5: preventie van gegevensverlies configureren'
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
description: Informatie over het gebruik van Preventie van gegevensverlies en implementeren in Microsoft 365.
ms.openlocfilehash: e3d18bf54ecdfe11f8233163e7f200a70606d81d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636974"
---
# <a name="step-5-configure-data-loss-prevention"></a><span data-ttu-id="9806c-103">Stap 5: preventie van gegevensverlies configureren</span><span class="sxs-lookup"><span data-stu-id="9806c-103">Step 5: Configure Data Loss Prevention</span></span>

<span data-ttu-id="9806c-104">*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="9806c-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 6: gegevensbescherming](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="9806c-106">Met een beleid voor preventie van gegevensverlies (DLP-beleid) in het Beveiligings- en nalevingscentrum kunt u gevoelige gegevens in Microsoft 365 identificeren, controleren en automatisch beschermen.</span><span class="sxs-lookup"><span data-stu-id="9806c-106">With data loss prevention (DLP) policies in the Security & Compliance center, you can identify, monitor, and automatically protect sensitive information across Microsoft 365.</span></span> <span data-ttu-id="9806c-107">Met DLP-beleid kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="9806c-107">With DLP policies, you can:</span></span>

- <span data-ttu-id="9806c-108">Gevoelige informatie identificeren op meerdere locaties, zoals Exchange Online, SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9806c-108">Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>
- <span data-ttu-id="9806c-109">Voorkomen dat gevoelige gegevens per ongeluk worden gedeeld door de toegang tot een document te blokkeren of het e-mailbericht te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="9806c-109">Prevent the accidental sharing of sensitive information by blocking access to a document or blocking the email that contains it.</span></span>
- <span data-ttu-id="9806c-110">Gevoelige informatie controleren en beveiligen in de bureaubladversies van Excel, PowerPoint en Word.</span><span class="sxs-lookup"><span data-stu-id="9806c-110">Monitor and protect sensitive information in the desktop versions of Excel, PowerPoint, and Word.</span></span>
- <span data-ttu-id="9806c-111">Gebruikers leren hoe ze compatibel blijven, zonder hun werkstroom met e-mailmeldingen en beleidstips te onderbreken.</span><span class="sxs-lookup"><span data-stu-id="9806c-111">Help users learn how to stay compliant without interrupting their workflow with email notifications and policy tips.</span></span> 
- <span data-ttu-id="9806c-112">Bekijk DLP-rapporten met inhoud die overeenkomt met het DLP-beleid van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="9806c-112">View DLP reports showing content that matches your organization's DLP policies.</span></span>

<span data-ttu-id="9806c-113">Met een DLP-beleid wordt het volgende aangegeven:</span><span class="sxs-lookup"><span data-stu-id="9806c-113">A DLP policy specifies:</span></span>

- <span data-ttu-id="9806c-114">**Waar:** locaties, zoals Exchange Online, SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams-chats en kanalen.</span><span class="sxs-lookup"><span data-stu-id="9806c-114">**Where:** Locations such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chats and channels.</span></span>
- <span data-ttu-id="9806c-115">**Wanneer:** voorwaarden dat de inhoud moet overeenstemmen met een bepaalde beleidsregel.</span><span class="sxs-lookup"><span data-stu-id="9806c-115">**When:** Conditions the content must match within a specific policy rule.</span></span>
- <span data-ttu-id="9806c-116">**Hoe:** acties binnen die overeenkomende beleidsregel automatisch moeten worden uitgevoerd voor de overeenkomende voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="9806c-116">**How:** Actions within that matching policy rule to take automatically for the matching conditions.</span></span>

<span data-ttu-id="9806c-117">Met andere woorden:</span><span class="sxs-lookup"><span data-stu-id="9806c-117">In other words:</span></span>

- <span data-ttu-id="9806c-118">Voor een document op deze locatie (waar), als de inhoud aan de voorwaarden van een regel voldoet (wanneer), worden de acties die in de regel zijn opgegeven, automatisch uitgevoerd (hoe).</span><span class="sxs-lookup"><span data-stu-id="9806c-118">For a document in this location (where), if the content matches the conditions of a rule (when), then automatically take the actions specified in the rule (how).</span></span>

<span data-ttu-id="9806c-119">Om te bepalen welke DLP-beleid u nodig hebt, moet u uw documenten analyseren en de gegevenstypen die bescherming moeten hebben tegen gegevensverlies.</span><span class="sxs-lookup"><span data-stu-id="9806c-119">To determine the set of DLP policies you need, you must analyze your documents and the types of data within them that need protection from data loss.</span></span> <span data-ttu-id="9806c-120">Als u bijvoorbeeld een financiële organisatie bent in de Verenigde Staten van Amerika, maakt u een DLP-beleid dat voorkomt dat documenten met Amerikaanse burgerservicenummers worden gedeeld buiten de organisatie of worden verzonden via e-mail naar locaties buiten de organisatie.</span><span class="sxs-lookup"><span data-stu-id="9806c-120">For example, if you are a financial organization in the United States of America, you would create a DLP policy that prevents documents with social security numbers from being shared outside the organization or sent in email to locations outside the organization.</span></span>

<span data-ttu-id="9806c-121">Vervolgens configureert en test u het beleid met testlocaties om het juiste DLP-gedrag te garanderen en om het aantal fout-positieven zo laag mogelijk te houden.</span><span class="sxs-lookup"><span data-stu-id="9806c-121">Next, you configure and test the policies with test locations to ensure the correct DLP behavior and to minimize false positives.</span></span>

<span data-ttu-id="9806c-122">Ten slotte kunt u het uitrollen in uw organisatie door de werknemers van het nieuwe beleid en het gewenste gedrag op de hoogte te stellen en het bereik van de locaties te vergroten.</span><span class="sxs-lookup"><span data-stu-id="9806c-122">Finally, you roll it out to your organization by informing the employees of the new policies and their desired behavior and widening the scope of the locations.</span></span>

<span data-ttu-id="9806c-123">Zie [Aan de slag met aanbevelingen voor DLP-beleid](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9806c-123">For more information, see [Get started with DLP policy recommendations](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations).</span></span>

<span data-ttu-id="9806c-124">Zie de [afsluitcriteria](infoprotect-exit-criteria.md#crit-infoprotect-step5) voor deze stap als tussentijds controlepunt.</span><span class="sxs-lookup"><span data-stu-id="9806c-124">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step5) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="9806c-125">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="9806c-125">Next step</span></span>

|||
|:-------|:-----|
|![Stap 6](../media/stepnumbers/Step6.png)|[<span data-ttu-id="9806c-127">E-mailversleuteling configureren</span><span class="sxs-lookup"><span data-stu-id="9806c-127">Configure email encryption</span></span>](infoprotect-email-encryption.md)|


