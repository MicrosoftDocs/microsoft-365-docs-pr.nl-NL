---
title: Prioriteitsaccounts beheren en controleren
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
description: Controleer mislukte en vertraagde e-mailberichten die zijn verzonden naar of van accounts die grote gevolgen hebben voor het bedrijf.
ms.openlocfilehash: dbdd692a41d341564376960788054e70623daf5a
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233360"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="eafcc-103">Prioriteitsaccounts beheren en controleren</span><span class="sxs-lookup"><span data-stu-id="eafcc-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="eafcc-104">In elke Microsoft 365-organisatie zijn er essentiële personen, zoals leidinggevenden, leidinggevenden, managers of andere gebruikers, die toegang hebben tot gevoelige, eigendomsinformatie of informatie met hoge prioriteit.</span><span class="sxs-lookup"><span data-stu-id="eafcc-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="eafcc-105">Om uw organisatie te helpen deze accounts te beveiligen, kunt u nu specifieke gebruikers als prioriteitsaccounts aanwijzen en app-specifieke functies gebruiken die hen extra beveiliging bieden.</span><span class="sxs-lookup"><span data-stu-id="eafcc-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="eafcc-106">In de toekomst ondersteunen meer apps en functies prioriteitsaccounts. Om te  beginnen hebben we twee mogelijkheden aangekondigd: prioriteitsaccountbeveiliging en **premium-e-mailstroomcontrole.**</span><span class="sxs-lookup"><span data-stu-id="eafcc-106">In the future, more apps and features will support priority accounts, and to start with, we’ve announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="eafcc-107">**Prioriteitsaccountbeveiliging:** Microsoft Defender voor Office 365 (voorheen Office 365 Advanced Threat Protection) ondersteunt prioriteitsaccounts als tags die kunnen worden gebruikt in filters in waarschuwingen, rapporten en onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="eafcc-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="eafcc-108">Bekijk gebruikerstags in Microsoft Defender voor [Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="eafcc-108">For more information, check out [User tags in Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags).</span></span>
- <span data-ttu-id="eafcc-109">**Premium Mail Flow Monitoring:** een goede e-mailstroom kan essentieel zijn voor bedrijfssuccessen en bezorgingsvertra laten of mislukte bezorging kunnen een negatieve invloed hebben op het bedrijf.</span><span class="sxs-lookup"><span data-stu-id="eafcc-109">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="eafcc-110">U kunt een drempelwaarde kiezen voor mislukte of vertraagde e-mailberichten, waarschuwingen ontvangen wanneer deze drempel wordt overschreden en een rapport bekijken van e-mailproblemen voor prioriteitsaccounts.</span><span class="sxs-lookup"><span data-stu-id="eafcc-110">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="eafcc-111">Raadpleeg het rapport [E-mailproblemen voor prioriteitaccounts in](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) het moderne EAC voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="eafcc-111">For more information, check out [Email issues for priority accounts report in the modern EAC](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span></span>

<span data-ttu-id="eafcc-112">Zie Beveiligingsaanbevelingen voor prioriteitsaccounts voor aanbevolen beveiligingsprocedures [voor prioriteitsaccounts.](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-recommendations-for-priority-accounts)</span><span class="sxs-lookup"><span data-stu-id="eafcc-112">For security best practices for priority accounts, see [Security recommendations for priority accounts](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-recommendations-for-priority-accounts).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="eafcc-113">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="eafcc-113">Before you begin</span></span>

<span data-ttu-id="eafcc-114">De **functie Accountbeveiliging met** prioriteit die in dit onderwerp wordt beschreven, is alleen beschikbaar voor organisaties die aan de volgende vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="eafcc-114">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="eafcc-115">Microsoft Defender voor Office 365 Abonnement 2, inclusief personen met Office 365 E3, Office 365 E5, Microsoft 365 E5 of Microsoft 365 E5-beveiliging.</span><span class="sxs-lookup"><span data-stu-id="eafcc-115">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="eafcc-116">De **functie Premium e-mailstroomcontrole** die in dit onderwerp wordt beschreven, is alleen beschikbaar voor organisaties die aan de volgende vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="eafcc-116">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="eafcc-117">Uw organisatie moet het aantal licenties hebben van ten minste 10.000, van een of meer, of een combinatie van de volgende producten: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="eafcc-117">Your organization needs to have a license count of at least 10,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="eafcc-118">Uw organisatie kan bijvoorbeeld 3000 Office 365 E3-licenties en 8500 Microsoft 365 E5 hebben voor een totaal van 11.500 licenties van de in aanmerking komende producten.</span><span class="sxs-lookup"><span data-stu-id="eafcc-118">For example, your organization can have 3000 Office 365 E3 licenses and 8500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="eafcc-119">Je organisatie heeft ten minste 50 maandelijks actieve Exchange Online-gebruikers nodig.</span><span class="sxs-lookup"><span data-stu-id="eafcc-119">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="eafcc-120">U kunt maximaal 250 accounts met prioriteit controleren.</span><span class="sxs-lookup"><span data-stu-id="eafcc-120">You can monitor up to 250 priority accounts.</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="eafcc-121">Prioriteitsaccounts toevoegen vanaf de pagina Setup</span><span class="sxs-lookup"><span data-stu-id="eafcc-121">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="eafcc-122">Voeg prioriteitsaccounts toe op de **pagina Setup.**</span><span class="sxs-lookup"><span data-stu-id="eafcc-122">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="eafcc-123">Ga naar het Microsoft 365-beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="eafcc-123">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="eafcc-124">Ga naar **Kennis over** de  >  **organisatie instellen** en kies **Weergeven** onder Uw belangrijkste **accounts controleren.**</span><span class="sxs-lookup"><span data-stu-id="eafcc-124">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="eafcc-125">Selecteer **Aan de slag** of **Beheren.**</span><span class="sxs-lookup"><span data-stu-id="eafcc-125">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="eafcc-126">Typ op **de pagina Prioriteitsaccounts** toevoegen in het zoekveld de naam of het e-mailadres van de persoon die u wilt toevoegen aan de lijst met prioriteitsaccounts.</span><span class="sxs-lookup"><span data-stu-id="eafcc-126">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="eafcc-127">U kunt ook uw e-mail drempelwaarde instellen voor mislukte of vertraagde e-mailberichten en een wekelijks rapport ontvangen van problemen voor prioriteitsaccounts.</span><span class="sxs-lookup"><span data-stu-id="eafcc-127">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="eafcc-128">Selecteer de gebruiker en kies **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="eafcc-128">Select the user and choose **Save**.</span></span>

<span data-ttu-id="eafcc-129">U kunt ook prioriteitsaccounts toevoegen vanaf de pagina Actieve gebruikers.</span><span class="sxs-lookup"><span data-stu-id="eafcc-129">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="eafcc-130">Pagina Prioriteitsaccounts toevoegen van de pagina Actieve gebruikers</span><span class="sxs-lookup"><span data-stu-id="eafcc-130">Add priority accounts from Active users page</span></span>

<span data-ttu-id="eafcc-131">Voeg prioriteitsaccounts toe op de pagina Actieve gebruikers.</span><span class="sxs-lookup"><span data-stu-id="eafcc-131">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="eafcc-132">Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="eafcc-132">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="eafcc-133">Ga naar **Gebruikers**  >  **actieve gebruikers** en kies **...** boven aan de pagina.</span><span class="sxs-lookup"><span data-stu-id="eafcc-133">Go to **Users** > **Active users** and choose **...** at the top of the page.</span></span> <span data-ttu-id="eafcc-134">Selecteer **Prioriteitsaccounts beheren.**</span><span class="sxs-lookup"><span data-stu-id="eafcc-134">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="eafcc-135">Selecteer **Accounts toevoegen** en  typ op de pagina Prioriteitsaccounts toevoegen in het zoekveld de naam van de persoon die u wilt toevoegen aan de lijst met prioriteitsaccounts.</span><span class="sxs-lookup"><span data-stu-id="eafcc-135">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="eafcc-136">Selecteer de gebruiker en kies **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="eafcc-136">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="eafcc-137">Een gebruiker verwijderen uit de lijst met prioriteitsaccounts</span><span class="sxs-lookup"><span data-stu-id="eafcc-137">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="eafcc-138">Ga naar het Microsoft 365-beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="eafcc-138">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="eafcc-139">Ga naar **Kennis over** de  >  **organisatie instellen** en kies **Weergeven** onder Uw belangrijkste **accounts controleren.**</span><span class="sxs-lookup"><span data-stu-id="eafcc-139">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="eafcc-140">Kies op **de pagina Uw meeste accounts controleren** de optie **Prioriteitsaccounts** onder **Deze functie beheren.**</span><span class="sxs-lookup"><span data-stu-id="eafcc-140">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="eafcc-141">Selecteer op **de pagina Prioriteit-accounts** de gebruiker of gebruikers die u wilt verwijderen uit de lijst en kies **Accounts verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="eafcc-141">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="eafcc-142">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="eafcc-142">Related topics</span></span>

[<span data-ttu-id="eafcc-143">Prioriteitsaccounts gebruiken in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="eafcc-143">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)