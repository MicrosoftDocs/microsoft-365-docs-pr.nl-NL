---
title: Prioriteitsaccounts beheren en bewaken
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
ms.custom: AdminSurgePortfolio
description: Controleren mislukt en vertraagde e-mailberichten die zijn verzonden naar of van accounts met een hoge zakelijke impact.
ms.openlocfilehash: 2a58f4090244fc6d68be69cf6b3c8ab6e00874fa
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535804"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="0ba83-103">Prioriteitsaccounts beheren en bewaken</span><span class="sxs-lookup"><span data-stu-id="0ba83-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="0ba83-104">In elke Microsoft 365 zijn er mensen die essentieel zijn, zoals leidinggevenden, leidinggevenden, managers of andere gebruikers die toegang hebben tot gevoelige, eigendomsgebonden of hoge prioriteitsinformatie.</span><span class="sxs-lookup"><span data-stu-id="0ba83-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="0ba83-105">Als u uw organisatie wilt helpen deze accounts te beveiligen, kunt u nu specifieke gebruikers aanwijzen als prioriteitsaccounts en gebruikmaken van app-specifieke functies die hen extra bescherming bieden.</span><span class="sxs-lookup"><span data-stu-id="0ba83-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="0ba83-106">In de toekomst ondersteunen meer apps en functies prioriteitsaccounts en om te  beginnen hebben we twee mogelijkheden aangekondigd: prioriteitsaccountbeveiliging en premium **e-mailstroomcontrole.**</span><span class="sxs-lookup"><span data-stu-id="0ba83-106">In the future, more apps and features will support priority accounts, and to start with, we've announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="0ba83-107">**Prioriteitsaccountbeveiliging:** Microsoft Defender voor Office 365 (voorheen Office 365 Advanced Threat Protection) ondersteunt prioriteitsaccounts als tags die kunnen worden gebruikt in filters in waarschuwingen, rapporten en onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="0ba83-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="0ba83-108">Zie Gebruikerslabels [in Microsoft Defender voor](../../security/office-365-security/user-tags.md)meer Office 365.</span><span class="sxs-lookup"><span data-stu-id="0ba83-108">For more information, check out [User tags in Microsoft Defender for Office 365](../../security/office-365-security/user-tags.md).</span></span>

  <span data-ttu-id="0ba83-109">Een natuurlijke vraag is: 'Zijn niet alle gebruikers een prioriteit?</span><span class="sxs-lookup"><span data-stu-id="0ba83-109">A natural question is, "Aren't all users a priority?</span></span> <span data-ttu-id="0ba83-110">Waarom worden niet alle gebruikers aangewezen als prioriteitsaccounts?</span><span class="sxs-lookup"><span data-stu-id="0ba83-110">Why not designate all users as priority accounts?"</span></span> <span data-ttu-id="0ba83-111">Ja, alle gebruikers hebben een prioriteit, maar accountbeveiliging met prioriteit biedt de volgende extra voordelen:</span><span class="sxs-lookup"><span data-stu-id="0ba83-111">Yes, all users are a priority, but priority account protection offers the following additional benefits:</span></span>

  - <span data-ttu-id="0ba83-112">**Extra heuristische functies:** Onze analyse van de e-mailstroom in de Microsoft-datacenters geeft aan dat de e-mailstroompatronen voor leidinggevenden van het bedrijf verschillen van de gemiddelde werknemer.</span><span class="sxs-lookup"><span data-stu-id="0ba83-112">**Additional heuristics**: Our analysis of mail flow in the Microsoft datacenters indicates that mail flow patterns for company executives are different than the average employee.</span></span> <span data-ttu-id="0ba83-113">Prioriteitsaccountbeveiliging biedt extra heuristische functies die specifiek zijn afgestemd op leidinggevenden van het bedrijf die niet ten goede komen aan een gewone werknemer.</span><span class="sxs-lookup"><span data-stu-id="0ba83-113">Priority account protection offers additional heuristics that are specifically tailored to company executives that wouldn't benefit a regular employee.</span></span>
  - <span data-ttu-id="0ba83-114">**Extra zichtbaarheid in rapportage:** In feite is informatie voor alle gebruikers (of alle betrokken gebruikers) al beschikbaar in waarschuwingen, rapporten en onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="0ba83-114">**Additional visibility in reporting**: In effect, information for all users (or all affected users) is already available in alerts, reports, and investigations.</span></span> <span data-ttu-id="0ba83-115">Met de tag prioriteitsaccounts als filter kunt u uw onderzoeken specifiek richten.</span><span class="sxs-lookup"><span data-stu-id="0ba83-115">The priority accounts tag as a filter allows you to specifically target your investigations.</span></span>

- <span data-ttu-id="0ba83-116">**Premium Mail Flow Monitoring:** een gezonde e-mailstroom kan van essentieel belang zijn voor bedrijfssucces en vertragingen of storingen van bezorging kunnen een negatieve invloed hebben op het bedrijf.</span><span class="sxs-lookup"><span data-stu-id="0ba83-116">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="0ba83-117">U kunt een drempel voor mislukte of vertraagde e-mailberichten kiezen, waarschuwingen ontvangen wanneer deze drempel wordt overschreden en een rapport bekijken met e-mailproblemen voor prioriteitsaccounts.</span><span class="sxs-lookup"><span data-stu-id="0ba83-117">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="0ba83-118">Zie E-mailproblemen voor het rapport [Prioriteitsaccounts in](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) het moderne EAC voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0ba83-118">For more information, check out [Email issues for priority accounts report in the modern EAC](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span></span>

<span data-ttu-id="0ba83-119">Zie Beveiligingsaanbevelingen voor prioriteitsaccounts voor aanbevolen beveiligingsprocedures [voor prioriteitsaccounts.](../../security/office-365-security/security-recommendations-for-priority-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="0ba83-119">For security best practices for priority accounts, see [Security recommendations for priority accounts](../../security/office-365-security/security-recommendations-for-priority-accounts.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0ba83-120">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="0ba83-120">Before you begin</span></span>

<span data-ttu-id="0ba83-121">De **functie Accountbeveiliging prioriteit** die in dit onderwerp wordt beschreven, is alleen beschikbaar voor organisaties die aan de volgende vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="0ba83-121">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="0ba83-122">Microsoft Defender voor Office 365 abonnement 2, inclusief personen met Office 365 E3, Office 365 E5, Microsoft 365 E5 of Microsoft 365 E5 Security.</span><span class="sxs-lookup"><span data-stu-id="0ba83-122">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="0ba83-123">De **functie Premium Mail Flow monitoring** die in dit onderwerp wordt beschreven, is alleen beschikbaar voor organisaties die voldoen aan de volgende vereisten:</span><span class="sxs-lookup"><span data-stu-id="0ba83-123">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="0ba83-124">Uw organisatie moet een licentie tellen van ten minste 10.000, van een van of een combinatie van de volgende producten: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="0ba83-124">Your organization needs to have a license count of at least 10,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="0ba83-125">Uw organisatie kan bijvoorbeeld 3000 Office 365 E3-licenties en 8500 Microsoft 365 E5 hebben, voor in totaal 11.500 licenties van de in aanmerking komende producten.</span><span class="sxs-lookup"><span data-stu-id="0ba83-125">For example, your organization can have 3000 Office 365 E3 licenses and 8500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="0ba83-126">Je organisatie heeft ten minste 50 maandelijks actieve Exchange Online-gebruikers nodig.</span><span class="sxs-lookup"><span data-stu-id="0ba83-126">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="0ba83-127">U kunt maximaal 250 prioriteitsaccounts controleren.</span><span class="sxs-lookup"><span data-stu-id="0ba83-127">You can monitor up to 250 priority accounts.</span></span>

<span data-ttu-id="0ba83-128">Wanneer u prioriteitsaccountbeveiliging op een postvak gebruikt, moet u ook prioriteitsaccountbeveiliging toepassen op gebruikers die toegang hebben tot het postvak (bijvoorbeeld de CEO en de executive assistant van de CEO die de agenda van de CEO beheert).</span><span class="sxs-lookup"><span data-stu-id="0ba83-128">When you apply priority account protection to a mailbox, you should also apply priority account protection to users who have access to the mailbox (for example, the CEO and the CEO's executive assistant who manages the CEO's calendar).</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="0ba83-129">Prioriteitsaccounts toevoegen vanaf de pagina Setup</span><span class="sxs-lookup"><span data-stu-id="0ba83-129">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="0ba83-130">Voeg prioriteitsaccounts toe vanaf **de pagina Setup.**</span><span class="sxs-lookup"><span data-stu-id="0ba83-130">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="0ba83-131">Ga naar het Microsoft 365 beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="0ba83-131">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="0ba83-132">Ga naar  >  **Organisatiekennis instellen** en kies **Weergeven** onder Uw belangrijkste **accounts controleren.**</span><span class="sxs-lookup"><span data-stu-id="0ba83-132">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="0ba83-133">Selecteer **Aan de slag** of **Beheren.**</span><span class="sxs-lookup"><span data-stu-id="0ba83-133">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="0ba83-134">Typ op **de pagina Prioriteitsaccounts** toevoegen in het zoekveld de naam of het e-mailadres van de persoon die u wilt toevoegen aan de lijst met prioriteitsaccounts.</span><span class="sxs-lookup"><span data-stu-id="0ba83-134">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="0ba83-135">U kunt ook de drempel voor e-mail instellen voor mislukte of vertraagde e-mailberichten en een wekelijks rapport krijgen van problemen voor prioriteitsaccounts.</span><span class="sxs-lookup"><span data-stu-id="0ba83-135">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="0ba83-136">Selecteer de gebruiker en kies **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="0ba83-136">Select the user and choose **Save**.</span></span>

<span data-ttu-id="0ba83-137">U kunt ook prioriteitsaccounts toevoegen vanaf de pagina Actieve gebruikers.</span><span class="sxs-lookup"><span data-stu-id="0ba83-137">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="0ba83-138">Prioriteitsaccounts toevoegen vanaf de pagina Actieve gebruikers</span><span class="sxs-lookup"><span data-stu-id="0ba83-138">Add priority accounts from Active users page</span></span>

<span data-ttu-id="0ba83-139">Voeg prioriteitsaccounts toe vanaf de pagina Actieve gebruikers.</span><span class="sxs-lookup"><span data-stu-id="0ba83-139">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="0ba83-140">Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="0ba83-140">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="0ba83-141">Ga naar **Gebruikers**  >  **Actieve gebruikers** en selecteer de drie puntjes (meer acties) boven aan de pagina.</span><span class="sxs-lookup"><span data-stu-id="0ba83-141">Go to **Users** > **Active users** and select the three dots (more actions) at the top of the page.</span></span> <span data-ttu-id="0ba83-142">Selecteer **Prioriteitsaccounts beheren.**</span><span class="sxs-lookup"><span data-stu-id="0ba83-142">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="0ba83-143">Selecteer **Accounts toevoegen** en typ op de pagina **Prioriteitsaccounts** toevoegen in het zoekveld de naam van de persoon die u wilt toevoegen aan de lijst met prioriteitsaccounts.</span><span class="sxs-lookup"><span data-stu-id="0ba83-143">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="0ba83-144">Selecteer de gebruiker en kies **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="0ba83-144">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="0ba83-145">Een gebruiker verwijderen uit de lijst met prioriteitsaccounts</span><span class="sxs-lookup"><span data-stu-id="0ba83-145">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="0ba83-146">Ga naar het Microsoft 365 beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="0ba83-146">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="0ba83-147">Ga naar  >  **Organisatiekennis instellen** en kies **Weergeven** onder Uw belangrijkste **accounts controleren.**</span><span class="sxs-lookup"><span data-stu-id="0ba83-147">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="0ba83-148">Kies op **de pagina Uw meeste accounts controleren** de optie **Prioriteitsaccounts** onder **Deze functie beheren.**</span><span class="sxs-lookup"><span data-stu-id="0ba83-148">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="0ba83-149">Selecteer op **de pagina Prioriteitsaccounts** de gebruiker of gebruikers die u uit de lijst wilt verwijderen en kies Accounts **verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="0ba83-149">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0ba83-150">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="0ba83-150">Related topics</span></span>

[<span data-ttu-id="0ba83-151">Prioriteitsaccounts gebruiken in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0ba83-151">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)
