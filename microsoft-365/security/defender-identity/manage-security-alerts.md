---
title: Beveiligingswaarschuwingen voor Microsoft Defender voor identiteit in Microsoft 365 Defender
description: Informatie over het beheren en controleren van beveiligingswaarschuwingen die zijn uitgegeven door Microsoft Defender voor identiteit in Microsoft 365 Defender
ms.date: 05/20/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
manager: raynew
ms.openlocfilehash: 0c48c9076d05cd352229477acc28b32185eef54f
ms.sourcegitcommit: 4f6ef4cd09c3ed36dc0be3702b0636bad6cff8a9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/26/2021
ms.locfileid: "52657800"
---
# <a name="defender-for-identity-security-alerts-in-microsoft-365-defender"></a><span data-ttu-id="8ae6e-103">Beveiligingswaarschuwingen voor Defender voor identiteit in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8ae6e-103">Defender for Identity security alerts in Microsoft 365 Defender</span></span>

<span data-ttu-id="8ae6e-104">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8ae6e-104">**Applies to:**</span></span>

- <span data-ttu-id="8ae6e-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8ae6e-105">Microsoft 365 Defender</span></span>
- <span data-ttu-id="8ae6e-106">Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="8ae6e-106">Defender for Identity</span></span>

<span data-ttu-id="8ae6e-107">In dit artikel worden de basisbeginselen beschreven van het werken met [beveiligingswaarschuwingen](/defender-for-identity) van Microsoft Defender voor identiteit in het [Microsoft 365 beveiligingscentrum.](/microsoft-365/security/defender/overview-security-center)</span><span class="sxs-lookup"><span data-stu-id="8ae6e-107">This article explains the basics of how to work with [Microsoft Defender for Identity](/defender-for-identity) security alerts in the [Microsoft 365 security center](/microsoft-365/security/defender/overview-security-center).</span></span>

<span data-ttu-id="8ae6e-108">Defender voor identiteitswaarschuwingen zijn inheems geïntegreerd in [het Microsoft 365 beveiligingscentrum](https://security.microsoft.com) met een speciale paginanotatie voor identiteitswaarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="8ae6e-108">Defender for Identity alerts are natively integrated into the [Microsoft 365 security center](https://security.microsoft.com) with a dedicated Identity alert page format.</span></span> <span data-ttu-id="8ae6e-109">Dit markeert de eerste stap in de reis om de volledige [Microsoft Defender for Identity-ervaring](/defender-for-identity/defender-for-identity-in-microsoft-365-defender)in te voeren in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="8ae6e-109">This marks the first step in the journey to [introduce the full Microsoft Defender for Identity experience into Microsoft 365 Defender](/defender-for-identity/defender-for-identity-in-microsoft-365-defender).</span></span>

<span data-ttu-id="8ae6e-110">De nieuwe pagina Identiteitsmelding biedt klanten van Microsoft Defender voor identiteit betere signaalverrijking voor meerdere domeinen en nieuwe mogelijkheden voor automatische identiteitsreacties.</span><span class="sxs-lookup"><span data-stu-id="8ae6e-110">The new Identity alert page gives Microsoft Defender for Identity customers better cross-domain signal enrichment and new automated identity response capabilities.</span></span> <span data-ttu-id="8ae6e-111">Het zorgt ervoor dat u veilig blijft en de efficiëntie van uw beveiligingsbewerkingen verbetert.</span><span class="sxs-lookup"><span data-stu-id="8ae6e-111">It ensures that you stay secure and helps improve the efficiency of your security operations.</span></span>

<span data-ttu-id="8ae6e-112">Een van de voordelen van het onderzoeken van waarschuwingen [via Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender) is dat microsoft Defender voor identiteitswaarschuwingen verder worden gecorreleerd met informatie die is verkregen uit elk van de andere producten in de suite.</span><span class="sxs-lookup"><span data-stu-id="8ae6e-112">One of the benefits of investigating alerts through [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender) is that Microsoft Defender for Identity alerts are further correlated with information obtained from each of the other products in the suite.</span></span> <span data-ttu-id="8ae6e-113">Deze verbeterde waarschuwingen komen overeen met de andere Microsoft 365 Defender-waarschuwingsindelingen die afkomstig zijn van [Microsoft Defender voor Office 365](/microsoft-365/security/office-365-security) en Microsoft Defender voor [Eindpunt.](/microsoft-365/security/defender-endpoint)</span><span class="sxs-lookup"><span data-stu-id="8ae6e-113">These enhanced alerts are consistent with the other Microsoft 365 Defender alert formats originating from [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security) and [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).</span></span> <span data-ttu-id="8ae6e-114">Met de nieuwe pagina hoeft u niet meer naar een andere productportal te gaan om waarschuwingen te onderzoeken die zijn gekoppeld aan identiteit.</span><span class="sxs-lookup"><span data-stu-id="8ae6e-114">The new page effectively eliminates the need to navigate to another product portal to investigate alerts associated with identity.</span></span>

<span data-ttu-id="8ae6e-115">Waarschuwingen die afkomstig zijn van Defender voor identiteit kunnen nu de [geautomatiseerde onderzoeks-](/microsoft-365/security/defender/m365d-autoir) en antwoordfuncties van Microsoft 365 Defender activeren, waaronder het automatisch corrigeren van waarschuwingen en het beperken van hulpmiddelen en processen die kunnen bijdragen aan de verdachte activiteit.</span><span class="sxs-lookup"><span data-stu-id="8ae6e-115">Alerts originating from Defender for Identity can now trigger the [Microsoft 365 Defender automated investigation and response (AIR)](/microsoft-365/security/defender/m365d-autoir) capabilities, including automatically remediating alerts and the mitigation of tools and processes that can contribute to the suspicious activity.</span></span>

>[!IMPORTANT]
><span data-ttu-id="8ae6e-116">Als onderdeel van de convergentie met Microsoft 365 Defender zijn sommige opties en details gewijzigd van hun locatie in de Defender for Identity-portal.</span><span class="sxs-lookup"><span data-stu-id="8ae6e-116">As part of the convergence with Microsoft 365 Defender, some options and details have changed from their location in the Defender for Identity portal.</span></span> <span data-ttu-id="8ae6e-117">Lees de onderstaande details om te ontdekken waar u de vertrouwde en nieuwe functies kunt vinden.</span><span class="sxs-lookup"><span data-stu-id="8ae6e-117">Please read the details below to discover where to find both the familiar and new features.</span></span>

## <a name="review-security-alerts"></a><span data-ttu-id="8ae6e-118">Beveiligingswaarschuwingen controleren</span><span class="sxs-lookup"><span data-stu-id="8ae6e-118">Review security alerts</span></span>

<span data-ttu-id="8ae6e-119">Waarschuwingen zijn toegankelijk vanaf meerdere locaties, waaronder  de pagina **Waarschuwingen,** de pagina Incidenten, de pagina's van afzonderlijke apparaten **en** vanaf de **pagina Geavanceerd.**</span><span class="sxs-lookup"><span data-stu-id="8ae6e-119">Alerts can be accessed from multiple locations, including the **Alerts** page, the **Incidents** page, the pages of individual **Devices**, and from the **Advanced hunting** page.</span></span> <span data-ttu-id="8ae6e-120">In dit voorbeeld bekijken we de pagina **Waarschuwingen.**</span><span class="sxs-lookup"><span data-stu-id="8ae6e-120">In this example, we'll review the **Alerts page**.</span></span>  

<span data-ttu-id="8ae6e-121">Ga in [Microsoft 365 beveiligingscentrum](https://security.microsoft.com/)naar **Incidenten & waarschuwingen** en vervolgens naar **Waarschuwingen.**</span><span class="sxs-lookup"><span data-stu-id="8ae6e-121">In the [Microsoft 365 security center](https://security.microsoft.com/), go to **Incidents & alerts** and then to **Alerts**.</span></span>

![Ga naar Incidenten en waarschuwingen en vervolgens Waarschuwingen](../../media/defender-identity/incidents-alerts.png)

<span data-ttu-id="8ae6e-123">Als u waarschuwingen van Defender voor identiteit wilt zien, selecteert u rechtsboven **Filter** en selecteert u onder **Servicebronnen** **Microsoft Defender** voor identiteit en selecteert u **Toepassen:**</span><span class="sxs-lookup"><span data-stu-id="8ae6e-123">To see alerts from Defender for Identity, on the top-right select **Filter**, and then under **Service sources** select **Microsoft Defender for Identity**, and select **Apply**:</span></span>

![Filteren op Defender voor identiteitsgebeurtenissen](../../media/defender-identity/filter-defender-for-identity.png)

<span data-ttu-id="8ae6e-125">De waarschuwingen worden weergegeven met informatie in de volgende **kolommen:** Waarschuwingsnaam **,** **Tags**, Ernst **,** Onderzoeksstatus , **Status** **,** Categorie , **Detectiebron**, **Beïnvloede** activa , **Eerste** activiteit en **Laatste activiteit**.</span><span class="sxs-lookup"><span data-stu-id="8ae6e-125">The alerts are displayed with information in the following columns: **Alert name**, **Tags**, **Severity**, **Investigation state**, **Status**, **Category**, **Detection source**, **Impacted assets**, **First activity**, and **Last activity**.</span></span>

![Defender voor identiteitsgebeurtenissen](../../media/defender-identity/filtered-alerts.png)

## <a name="manage-alerts"></a><span data-ttu-id="8ae6e-127">Waarschuwingen beheren</span><span class="sxs-lookup"><span data-stu-id="8ae6e-127">Manage alerts</span></span>

<span data-ttu-id="8ae6e-128">Als u op de **naam Waarschuwing voor** een van de waarschuwingen klikt, gaat u naar de pagina met informatie over de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="8ae6e-128">If you click the **Alert name** for one of the alerts, you'll go to the page with details about the alert.</span></span> <span data-ttu-id="8ae6e-129">In het linkerdeelvenster ziet u een overzicht van **Wat is er gebeurd:**</span><span class="sxs-lookup"><span data-stu-id="8ae6e-129">In the left pane, you'll see a summary of **What happened**:</span></span>

![Wat is er gebeurd met een waarschuwing](../../media/defender-identity/what-happened.png)

<span data-ttu-id="8ae6e-131">Boven het **vak Wat is er** gebeurd, staan knoppen voor de **accounts,** **doelhost** en **bronhost** van de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="8ae6e-131">Above the **What happened** box are buttons for the **Accounts**, **Destination Host** and **Source Host** of the alert.</span></span> <span data-ttu-id="8ae6e-132">Voor andere waarschuwingen ziet u mogelijk knoppen voor meer informatie over extra hosts, accounts, IP-adressen, domeinen en beveiligingsgroepen.</span><span class="sxs-lookup"><span data-stu-id="8ae6e-132">For other alerts, you might see buttons for details about additional hosts, accounts, IP addresses, domains, and security groups.</span></span> <span data-ttu-id="8ae6e-133">Selecteer een van deze entiteiten voor meer informatie over de betrokken entiteiten.</span><span class="sxs-lookup"><span data-stu-id="8ae6e-133">Select any of them to get more details about the entities involved.</span></span>

<span data-ttu-id="8ae6e-134">In het rechterdeelvenster ziet u de **details van waarschuwing.**</span><span class="sxs-lookup"><span data-stu-id="8ae6e-134">On the right pane, you'll see the **Alert details**.</span></span> <span data-ttu-id="8ae6e-135">Hier ziet u meer details en voert u verschillende taken uit:</span><span class="sxs-lookup"><span data-stu-id="8ae6e-135">Here you can see more details and perform several tasks:</span></span>

- <span data-ttu-id="8ae6e-136">**Classificeer deze waarschuwing-** Hier kunt u deze waarschuwing aanwijzen als **een** waarmelding **of een onwaar waarschuwing**</span><span class="sxs-lookup"><span data-stu-id="8ae6e-136">**Classify this alert** - Here you can designate this alert as a **True alert** or **False alert**</span></span>

    ![Waarschuwing classificeren](../../media/defender-identity/classify-alert.png)

- <span data-ttu-id="8ae6e-138">**Waarschuwingstoestand** : in **Classificatie instellen** kunt u de waarschuwing classificeren als **Waar** of **Onwaar.**</span><span class="sxs-lookup"><span data-stu-id="8ae6e-138">**Alert state** - In **Set Classification**, you can classify the alert as **True** or **False**.</span></span> <span data-ttu-id="8ae6e-139">In **Toegewezen aan** kunt u de waarschuwing aan uzelf toewijzen of de waarschuwing niet toewijzen.</span><span class="sxs-lookup"><span data-stu-id="8ae6e-139">In **Assigned to**, you can assign the alert to yourself or unassign it.</span></span>

    ![Waarschuwingstoestand](../../media/defender-identity/alert-state.png)

- <span data-ttu-id="8ae6e-141"> Waarschuwingsdetails: onder Waarschuwingsdetails vindt u meer informatie over de specifieke waarschuwing, volgt u een koppeling naar documentatie over het type waarschuwing, bekijkt u aan welk incident de waarschuwing is gekoppeld, bekijkt u alle geautomatiseerde onderzoeken die zijn gekoppeld aan dit waarschuwingstype en bekijkt u de beïnvloede apparaten en gebruikers. </span><span class="sxs-lookup"><span data-stu-id="8ae6e-141">**Alert details** - Under **Alert details**, you can find more information about the specific alert, follow a link to documentation about the type of alert, see which incident the alert is associated with, review any automated investigations linked to this alert type, and see the impacted devices and users.</span></span>

    ![Waarschuwingsdetails](../../media/defender-identity/alert-details.png)

- <span data-ttu-id="8ae6e-143">**Opmerkingen & geschiedenis:** hier kunt u opmerkingen toevoegen aan de waarschuwing en de geschiedenis bekijken van alle acties die aan de waarschuwing zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="8ae6e-143">**Comments & history** - Here you can add your comments to the alert, and see the history of all actions associated with the alert.</span></span>

    ![Opmerkingen en geschiedenis](../../media/defender-identity/comments-history.png)

- <span data-ttu-id="8ae6e-145">**Waarschuwing beheren:** als u **Waarschuwing beheren** selecteert, gaat u naar een deelvenster waarmee u het volgende kunt bewerken:</span><span class="sxs-lookup"><span data-stu-id="8ae6e-145">**Manage alert** - If you select **Manage alert**, you'll go to a pane that will allow you to edit the:</span></span>
  - <span data-ttu-id="8ae6e-146">**Status:** u kunt **Nieuw,** **Opgelost of** In **uitvoering kiezen.**</span><span class="sxs-lookup"><span data-stu-id="8ae6e-146">**Status** - You can choose **New**, **Resolved** or **In progress**.</span></span>
  - <span data-ttu-id="8ae6e-147">**Classificatie:** u kunt **Waar-waarschuwing of** **Onwaar-waarschuwing kiezen.**</span><span class="sxs-lookup"><span data-stu-id="8ae6e-147">**Classification** - You can choose **True alert** or **False alert**.</span></span>
  - <span data-ttu-id="8ae6e-148">**Opmerking:** u kunt een opmerking over de waarschuwing toevoegen.</span><span class="sxs-lookup"><span data-stu-id="8ae6e-148">**Comment** - You can add a comment about the alert.</span></span>

    <span data-ttu-id="8ae6e-149">Als u de drie puntjes naast Waarschuwing beheren selecteert, kunt u een bedreigingsexpert **raadplegen,** de waarschuwing exporteren naar een Excel bestand of Koppelen **aan een ander incident.**  </span><span class="sxs-lookup"><span data-stu-id="8ae6e-149">If you select the three dots next to **Manage alert**, you can **Consult a threat expert**, **Export** the alert to an Excel file, or **Link to another incident**.</span></span>

    ![Waarschuwing beheren](../../media/defender-identity/manage-alert.png)

    >[!NOTE]
    ><span data-ttu-id="8ae6e-151">In het Excel hebt u nu twee koppelingen beschikbaar: **Weergeven in Microsoft Defender** voor identiteit en weergave in Microsoft 365 **Defender.**</span><span class="sxs-lookup"><span data-stu-id="8ae6e-151">In the Excel file, you now have two links available: **View in Microsoft Defender for Identity** and **View in Microsoft 365 Defender**.</span></span> <span data-ttu-id="8ae6e-152">Elke koppeling brengt u naar de relevante portal en geeft informatie over de waarschuwing daar.</span><span class="sxs-lookup"><span data-stu-id="8ae6e-152">Each link will bring you to the relevant portal, and provide information about the alert there.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ae6e-153">Zie ook</span><span class="sxs-lookup"><span data-stu-id="8ae6e-153">See also</span></span>

- [<span data-ttu-id="8ae6e-154">Waarschuwingen onderzoeken in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8ae6e-154">Investigate alerts in Microsoft 365 Defender</span></span>](../defender/investigate-alerts.md)
