---
title: Schakel de evaluatieomgeving voor Microsoft Defender in voor Office 365 in uw productieomgeving, activeer uw evaluatie, activering
description: Stappen voor het activeren van Microsoft Defender voor Office365-evaluatie, met proeflicenties, MX-recordafhandeling, & controle van geaccepteerde domeinen en binnenkomende verbindingen.
keywords: Microsoft 365 Defender proefversie, probeer Microsoft 365 Defender, evalueer Microsoft 365 Defender, Microsoft 365 Defender evaluatielaboratorium, Microsoft 365 Defender-pilot, cyberbeveiliging, geavanceerde permanente bedreiging, bedrijfsbeveiliging, apparaten, apparaat, identiteit, gebruikers, gegevens, toepassingen, incidenten, geautomatiseerd onderzoek en herstel, geavanceerd zoeken
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 07/01/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: c0736b93c314c3086f8a52477622c6bcfa4096a0
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457919"
---
# <a name="enable-the-evaluation-environment"></a><span data-ttu-id="db5e8-104">De evaluatieomgeving inschakelen</span><span class="sxs-lookup"><span data-stu-id="db5e8-104">Enable the evaluation environment</span></span>

<span data-ttu-id="db5e8-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="db5e8-105">**Applies to:**</span></span>
- <span data-ttu-id="db5e8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="db5e8-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="db5e8-107">Dit artikel is [stap 2 van 3](eval-defender-office-365-overview.md) in het proces van het instellen van de evaluatieomgeving voor Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="db5e8-107">This article is [Step 2 of 3](eval-defender-office-365-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Office 365.</span></span> <span data-ttu-id="db5e8-108">Zie het [overzichtsartikel](eval-defender-office-365-overview.md)voor meer informatie over dit proces.</span><span class="sxs-lookup"><span data-stu-id="db5e8-108">For more information about this process, see the [overview article](eval-defender-office-365-overview.md).</span></span>

<span data-ttu-id="db5e8-109">Gebruik de volgende stappen om de evaluatie voor Microsoft Defender in te Office 365.</span><span class="sxs-lookup"><span data-stu-id="db5e8-109">Use the following steps to enable the evaluation for Microsoft Defender for Office 365.</span></span>


![Stappen voor het inschakelen van Microsoft Defender Office 365 in de evaluatieomgeving van Microsoft Defender](../../media/defender/m365-defender-office-eval-enable-steps.png)

- [<span data-ttu-id="db5e8-111">Stap 1: Proeflicenties activeren</span><span class="sxs-lookup"><span data-stu-id="db5e8-111">Step 1: Activate trial licenses</span></span>](#step-1-activate-trial-licenses)
- [<span data-ttu-id="db5e8-112">Stap 2: de openbare MX-record controleren en controleren</span><span class="sxs-lookup"><span data-stu-id="db5e8-112">Step 2: Audit and verify the public MX record</span></span>](#step-2-audit-and-verify-the-public-mx-record)
- [<span data-ttu-id="db5e8-113">Stap 3: Geaccepteerde domeinen controleren</span><span class="sxs-lookup"><span data-stu-id="db5e8-113">Step 3: Audit accepted domains</span></span>](#step-3-audit-accepted-domains)
- [<span data-ttu-id="db5e8-114">Stap 4: Binnenkomende connectors controleren</span><span class="sxs-lookup"><span data-stu-id="db5e8-114">Step 4: Audit inbound connectors</span></span>](#step-4-audit-inbound-connectors)
- [<span data-ttu-id="db5e8-115">Stap 5: De evaluatie activeren</span><span class="sxs-lookup"><span data-stu-id="db5e8-115">Step 5: Activate the evaluation</span></span>](#step-5-activate-the-evaluation)

## <a name="step-1-activate-trial-licenses"></a><span data-ttu-id="db5e8-116">Stap 1: Proeflicenties activeren</span><span class="sxs-lookup"><span data-stu-id="db5e8-116">Step 1: Activate trial licenses</span></span>

<span data-ttu-id="db5e8-117">Meld u aan bij uw bestaande Microsoft Defender voor Office 365 of tenantbeheerportal.</span><span class="sxs-lookup"><span data-stu-id="db5e8-117">Log on to your existing Microsoft Defender for Office 365 environment or tenant administration portal.</span></span>

1. <span data-ttu-id="db5e8-118">Ga naar de beheerportal.</span><span class="sxs-lookup"><span data-stu-id="db5e8-118">Navigate to the administration portal.</span></span>
2. <span data-ttu-id="db5e8-119">Selecteer Services aanschaffen in de werkbalk Snel starten.</span><span class="sxs-lookup"><span data-stu-id="db5e8-119">Select Purchase Services from the quick launch.</span></span>

:::image type="content" source="../../media/mdo-eval/1_m365-purchase-services.png" alt-text="Klik op Services aanschaffen in het navigatiedeelvenster van Office 365.":::

3.  <span data-ttu-id="db5e8-121">Schuif omlaag naar de Add-On sectie (of zoek naar 'Defender') om de Microsoft Defender te zoeken voor Office 365 abonnementen.</span><span class="sxs-lookup"><span data-stu-id="db5e8-121">Scroll down to the Add-On section (or search for "Defender") to locate the Microsoft Defender for Office 365 plans.</span></span>
4.  <span data-ttu-id="db5e8-122">Klik op Details naast het plan dat u wilt evalueren.</span><span class="sxs-lookup"><span data-stu-id="db5e8-122">Click Details next the plan you want to evaluate.</span></span>

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="Klik vervolgens op de knop Details.":::

5. <span data-ttu-id="db5e8-124">Klik op *de koppeling Gratis proefabonnement* starten.</span><span class="sxs-lookup"><span data-stu-id="db5e8-124">Click the *Start free trial* link.</span></span>

:::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="Klik op de gratis proefversie van start *hyperlink* in dit deelvenster.":::

6. <span data-ttu-id="db5e8-126">Bevestig uw aanvraag en klik op *de knop Nu* proberen.</span><span class="sxs-lookup"><span data-stu-id="db5e8-126">Confirm your request and click the *Try now* button.</span></span>

:::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="Klik nu op de knop Nu proberen *.":::

## <a name="step-2-audit-and-verify-the-public-mx-record"></a><span data-ttu-id="db5e8-128">Stap 2: de openbare MX-record controleren en controleren</span><span class="sxs-lookup"><span data-stu-id="db5e8-128">Step 2: Audit and verify the public MX record</span></span>

<span data-ttu-id="db5e8-129">Als u Microsoft Defender effectief wilt evalueren voor Office 365, is het belangrijk dat binnenkomende externe e-mail wordt doorgegeven via het EOP-exemplaar (Exchange Online Protection) dat is gekoppeld aan uw tenant.</span><span class="sxs-lookup"><span data-stu-id="db5e8-129">To effectively evaluate Microsoft Defender for Office 365, it's important that inbound external email be relayed through the Exchange Online Protection (EOP) instance associated with your tenant.</span></span>

1. <span data-ttu-id="db5e8-130">Meld u aan bij de M365-beheerportal, vouw Instellingen uit en selecteer Domeinen.</span><span class="sxs-lookup"><span data-stu-id="db5e8-130">Log on to the M365 Admin Portal, expand Settings, and select Domains.</span></span>
2. <span data-ttu-id="db5e8-131">Selecteer uw geverifieerde e-maildomein en klik op DNS beheren.</span><span class="sxs-lookup"><span data-stu-id="db5e8-131">Select your verified email domain and click Manage DNS.</span></span>
3. <span data-ttu-id="db5e8-132">Noteer de MX-record die is gegenereerd en toegewezen aan uw EOP-tenant.</span><span class="sxs-lookup"><span data-stu-id="db5e8-132">Make note of the MX record generated and assigned to your EOP tenant.</span></span>
4. <span data-ttu-id="db5e8-133">Open uw externe (openbare) DNS-zone en controleer de primaire MX-record die is gekoppeld aan uw e-maildomein.</span><span class="sxs-lookup"><span data-stu-id="db5e8-133">Access your external (public) DNS zone and check the primary MX record associated with your email domain.</span></span>
    - <span data-ttu-id="db5e8-134">Als uw openbare MX-record momenteel overeenkomt met het toegewezen EOP-adres (bijvoorbeeld tenant-com.mail.protection.outlook.com), moeten er geen verdere *routeringswijzigingen nodig zijn.*</span><span class="sxs-lookup"><span data-stu-id="db5e8-134">*If your public MX record currently matches the assigned EOP address (e.g. tenant-com.mail.protection.outlook.com) then no further routing changes should be required*.</span></span>
    - <span data-ttu-id="db5e8-135">Als uw openbare MX-record momenteel wordt overgeslagen naar een externe of on-premises SMTP-gateway, zijn mogelijk aanvullende routeringsconfiguraties vereist.</span><span class="sxs-lookup"><span data-stu-id="db5e8-135">If your public MX record currently resolves to a third-party or on-premises SMTP gateway then additional routing configurations may be required.</span></span>
    - <span data-ttu-id="db5e8-136">Als uw openbare MX-record momenteel wordt overgeslagen naar on-premises Exchange, is het mogelijk dat u nog steeds in een hybride model zit waarin sommige postvakken van geadresseerden nog niet zijn gemigreerd naar EXO.</span><span class="sxs-lookup"><span data-stu-id="db5e8-136">If your public MX record currently resolves to on-premises Exchange then you may still be in a hybrid model where some recipient mailbox have not yet been migrated to EXO.</span></span>

## <a name="step-3-audit-accepted-domains"></a><span data-ttu-id="db5e8-137">Stap 3: Geaccepteerde domeinen controleren</span><span class="sxs-lookup"><span data-stu-id="db5e8-137">Step 3: Audit accepted domains</span></span>

1. <span data-ttu-id="db5e8-138">Meld u aan Exchange Online beheerportal, selecteer E-mail Flow en klik vervolgens op Geaccepteerde domeinen.</span><span class="sxs-lookup"><span data-stu-id="db5e8-138">Log on the Exchange Online Admin Portal, select Mail Flow, and then click Accepted Domains.</span></span>
2. <span data-ttu-id="db5e8-139">Noteer het domeintype voor uw primaire e-maildomein in de  lijst met geaccepteerde domeinen die zijn toegevoegd en geverifieerd in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="db5e8-139">From the list of accepted domains that have been added and verified in your tenant, make note of the **domain type** for your primary email domain.</span></span>
    - <span data-ttu-id="db5e8-140">Als het domeintype  is ingesteld op Gezaghebbend, wordt ervan uitgegaan dat alle postvakken voor geadresseerden voor uw organisatie zich momenteel in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="db5e8-140">If the domain type is set to ***Authoritative*** then it is assumed all recipient mailboxes for your organization currently reside in Exchange Online.</span></span>
    - <span data-ttu-id="db5e8-141">Als het domeintype is ingesteld op ***Interne*** relay, bevindt u zich mogelijk nog steeds in een hybride model waarin sommige postvakken van geadresseerden zich nog steeds on-premises bevinden.</span><span class="sxs-lookup"><span data-stu-id="db5e8-141">If the domain type is set to ***Internal Relay*** then you may still be in a hybrid model where some recipient mailboxes still reside on-premises.</span></span>

## <a name="step-4-audit-inbound-connectors"></a><span data-ttu-id="db5e8-142">Stap 4: Binnenkomende connectors controleren</span><span class="sxs-lookup"><span data-stu-id="db5e8-142">Step 4: Audit inbound connectors</span></span>

1. <span data-ttu-id="db5e8-143">Meld u aan bij Exchange Online-beheerportal, selecteer E-mail Flow en klik vervolgens op Verbindingslijnen.</span><span class="sxs-lookup"><span data-stu-id="db5e8-143">Log on the Exchange Online Admin Portal, select Mail Flow, and then click Connectors.</span></span>
2. <span data-ttu-id="db5e8-144">Noteer in de lijst met geconfigureerde connectors alle vermeldingen die afkomstig zijn van **Partnerorganisatie** en die kunnen correleren met een SMTP-gateway van derden.</span><span class="sxs-lookup"><span data-stu-id="db5e8-144">From the list of configured connectors, make note of any entries which are from **Partner Organization** and may correlate to a third-party SMTP gateway.</span></span>
3. <span data-ttu-id="db5e8-145">Noteer in de lijst met geconfigureerde connectors  alle vermeldingen met het label Van de e-mailserver van uw organisatie, wat kan aangeven dat u nog steeds in een hybride scenario zit.</span><span class="sxs-lookup"><span data-stu-id="db5e8-145">From the list of configured connectors, make note of any entries labeled **From your organization's email server** which may indicate that you are still in hybrid scenario.</span></span>

## <a name="step-5-activate-the-evaluation"></a><span data-ttu-id="db5e8-146">Stap 5: De evaluatie activeren</span><span class="sxs-lookup"><span data-stu-id="db5e8-146">Step 5: Activate the evaluation</span></span>

<span data-ttu-id="db5e8-147">Gebruik de instructies hier om uw Microsoft Defender te activeren voor Office 365 evaluatie vanuit de Microsoft 365 Defender portal.</span><span class="sxs-lookup"><span data-stu-id="db5e8-147">Use the instructions here to activate your Microsoft Defender for Office 365 evaluation from the Microsoft 365 Defender portal.</span></span>

1. <span data-ttu-id="db5e8-148">Meld u aan bij uw tenant met een account dat toegang heeft tot de Microsoft 365 Defender portal.</span><span class="sxs-lookup"><span data-stu-id="db5e8-148">Log on to your tenant with an account that has access to the Microsoft 365 Defender portal.</span></span>
2. <span data-ttu-id="db5e8-149">Kies of u van de portal Microsoft 365 Defender **de** standaardinterface voor Microsoft Defender wilt maken voor Office 365 beheer (aanbevolen).</span><span class="sxs-lookup"><span data-stu-id="db5e8-149">Choose whether you want to make the **Microsoft 365 Defender portal** your default interface for Microsoft Defender for Office 365 administration (recommended).</span></span>

:::image type="content" source="../../media/mdo-eval/1_mdo-eval-activate-eval.png" alt-text="Klik op de knop Instellingen in-/uitschakelen om de gecentraliseerde en verbeterde Microsoft 365 Defender voor beheer te gebruiken.":::

3. <span data-ttu-id="db5e8-151">Selecteer in het navigatiemenu **Beleidsregels & onder** *E-mail & Samenwerking.*</span><span class="sxs-lookup"><span data-stu-id="db5e8-151">From the navigation menu, select **Policies & Rules** under *Email & Collaboration*.</span></span>

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-activate-eval.png" alt-text="Hier ziet u een menuafbeelding & e-mail en samenwerking die verwijst naar Beleidsregels & regels. Klik erop!":::

4. <span data-ttu-id="db5e8-153">Klik op *het & beleidsregels* op **Bedreigingsbeleid.**</span><span class="sxs-lookup"><span data-stu-id="db5e8-153">On the *Policy & Rules* dashboard, click **Threat Policies**.</span></span>

:::image type="content" source="../../media/mdo-eval/3_mdo-eval-activate-eval.png" alt-text="Afbeelding van het dashboard Beleid & regels en een pijl die naar bedreigingsbeleid wijst. Klik op dat volgende!":::

5. <span data-ttu-id="db5e8-155">Schuif omlaag naar *Extra beleid* en selecteer de tegel Defender evalueren **Office 365** tegel.</span><span class="sxs-lookup"><span data-stu-id="db5e8-155">Scroll down to *Additional Policies* and select the **Evaluate Defender for Office 365** tile.</span></span>

:::image type="content" source="../../media/mdo-eval/4_mdo-eval-activate-eval.png" alt-text="De tegel Eval Defender voor Office 365 zegt dat het een proefversie van 30 dagen is via e-mail & samenwerkingsvectoren. Klik door.":::

6. <span data-ttu-id="db5e8-157">Kies nu of externe e-mailroutes rechtstreeks Exchange Online of naar een gateway of service van derden en klik op Volgende.</span><span class="sxs-lookup"><span data-stu-id="db5e8-157">Now choose whether external email routes to Exchange Online directly, or to a third-party gateway or service, and click Next.</span></span>

:::image type="content" source="../../media/mdo-eval/5_mdo-eval-activate-eval.png" alt-text="Defender for Office 365 evalueert het verzenden van e-mail naar uw Exchange Online postvakken. Geef de details van de manier waarop uw e-mail nu wordt gerouteerd, inclusief de naam van de uitgaande verbindingslijn die uw e-mail omsingeed. Als u alleen Exchange Online Protection (EOP) gebruikt, hebt u geen verbindingslijn. Kies een van de 3rd-party of on-premises provider, of ik gebruik alleen EOP.":::

7. <span data-ttu-id="db5e8-159">Als u een gateway van derden gebruikt, selecteert u de naam van de leverancier in de vervolgkeuzelijn samen met de inkomende connector die aan die oplossing is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="db5e8-159">If you use a third-party gateway, select the vendor name from the drop-down along with the inbound connector associated with that solution.</span></span> <span data-ttu-id="db5e8-160">Wanneer u uw antwoorden hebt vermeld, klikt u op Volgende.</span><span class="sxs-lookup"><span data-stu-id="db5e8-160">When you've listed your answers, click Next.</span></span>

:::image type="content" source="../../media/mdo-eval/6-mdo-eval-activate-eval-settings.png" alt-text="In dit dialoogvenster kiest u de leverancierservice van derden die uw organisatie gebruikt of selecteert u *Overige*. Selecteer in het volgende dialoogvenster omlaag de inkomende verbindingslijn. Klik vervolgens op Volgende.":::

8. <span data-ttu-id="db5e8-162">Controleer uw instellingen en klik op **de knop Evaluatie** maken.</span><span class="sxs-lookup"><span data-stu-id="db5e8-162">Review your settings and click the **Create Evaluation** button.</span></span>

|  |  |
|---------|---------|
|  :::image type="content" source="../../media/mdo-eval/7-mdo-eval-activate-review.png" alt-text="Dit deelvenster heeft een vervolgkeuzemenu om uw instellingen te bekijken. Er is ook een klikbare koppeling naar Het routeringstype bewerken als dat nodig is. Wanneer u klaar bent, klikt u op de grote blauwe knop Evaluatie maken.":::   |   :::image type="content" source="../../media/mdo-eval/8-mdo-eval-activate-complete.png" alt-text="En nu is de set-up voltooid. Op de blauwe knop op deze pagina staat 'Ga naar evaluatie'.":::      |

## <a name="next-steps"></a><span data-ttu-id="db5e8-165">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="db5e8-165">Next steps</span></span>

<span data-ttu-id="db5e8-166">Stap 3 van 3: De pilot voor Microsoft Defender instellen voor Office 365</span><span class="sxs-lookup"><span data-stu-id="db5e8-166">Step 3 of 3: Set up the pilot for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="db5e8-167">Ga terug naar het overzicht voor [Microsoft Defender evalueren voor Office 365](eval-defender-office-365-overview.md)</span><span class="sxs-lookup"><span data-stu-id="db5e8-167">Return to the overview for [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)</span></span>

<span data-ttu-id="db5e8-168">Ga terug naar het overzicht voor [Evalueren en Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="db5e8-168">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>