---
title: Prioriteits accounts beheren en controleren
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
description: Controleren van mislukte en vertraagde e-mailberichten die zijn verzonden naar of van accounts die hoge bedrijfsimpact hebben.
ms.openlocfilehash: bc191873b3bbdcd84122a5430adeffe2b8c29fb1
ms.sourcegitcommit: 5ce64d510b15c6e2df32b78e6086f77156731e3c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477611"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="bdfc2-103">Prioriteits accounts beheren en controleren</span><span class="sxs-lookup"><span data-stu-id="bdfc2-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="bdfc2-104">In elke Microsoft 365-organisatie zijn er personen die essentieel zijn, zoals leidinggevenden, leidinggevenden, managers of andere gebruikers die toegang hebben tot gevoelige informatie.</span><span class="sxs-lookup"><span data-stu-id="bdfc2-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="bdfc2-105">Om uw organisatie te helpen deze accounts te beschermen, kunt u nu bepaalde gebruikers aanwijzen als prioriteits accounts en app-specifieke functies die ze bieden, extra bescherming bieden.</span><span class="sxs-lookup"><span data-stu-id="bdfc2-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="bdfc2-106">In de toekomst ondersteunen meer apps en functies prioriteits accounts, en om te beginnen met, hebben we twee mogelijkheden aangekondigd: **bescherming van prioriteits account** en een **uitgebreide e-mail stroom**.</span><span class="sxs-lookup"><span data-stu-id="bdfc2-106">In the future, more apps and features will support priority accounts, and to start with, we’ve announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="bdfc2-107">**Accountbeveiliging** voor de prioriteit: Microsoft Defender voor Office 365 (voorheen Office 365 Advanced Threat Protection) ondersteunt prioriteits accounts als tags die kunnen worden gebruikt in filters in waarschuwingen, rapporten en onderzoek.</span><span class="sxs-lookup"><span data-stu-id="bdfc2-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="bdfc2-108">Voor meer informatie raadpleegt u [gebruikers Tags in Microsoft Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="bdfc2-108">For more information, check out [User tags in Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide).</span></span>
- <span data-ttu-id="bdfc2-109">De **hoogwaardige e-mail stroom monitoring** -gezonde e-mail stroom kan essentieel zijn voor het succes van een bedrijf, en de bezorgings vertragingen of-storingen kunnen een negatieve invloed hebben op het bedrijf.</span><span class="sxs-lookup"><span data-stu-id="bdfc2-109">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="bdfc2-110">U kunt een drempel voor mislukte of vertraagde e-mailberichten kiezen, waarschuwingen ontvangen wanneer deze drempel wordt overschreden en een rapport met e-mail problemen voor prioriteit accounts weergeven.</span><span class="sxs-lookup"><span data-stu-id="bdfc2-110">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="bdfc2-111">Zie voor meer informatie [e-mail problemen voor het rapport met prioriteits accounts in de moderne](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)versie van het Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="bdfc2-111">For more information, check out [Email issues for priority accounts report in the modern EAC](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="bdfc2-112">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="bdfc2-112">Before you begin</span></span>

<span data-ttu-id="bdfc2-113">De functie voor **accountbeveiliging** van de prioriteit die wordt beschreven in dit onderwerp is alleen beschikbaar voor organisaties die aan de volgende vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="bdfc2-113">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="bdfc2-114">Microsoft Defender voor Office 365, abonnement 2, waaronder computers met Office 365 E3, Office 365 E5, Microsoft 365 E5 of Microsoft 365 E5-beveiliging.</span><span class="sxs-lookup"><span data-stu-id="bdfc2-114">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="bdfc2-115">De **Premium-functie voor het bijhouden van e-mail stromen** die in dit onderwerp wordt beschreven, is alleen beschikbaar voor organisaties die aan de volgende vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="bdfc2-115">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="bdfc2-116">Uw organisatie moet een aantal licenties hebben van ten minste 10.000, van een van, of een combinatie van de volgende producten: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="bdfc2-116">Your organization needs to have a license count of at least 10,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="bdfc2-117">Uw organisatie kan bijvoorbeeld 3000 Office 365 E3-licenties en 8500 Microsoft 365 E5 voor een totaal van de 11.500-licenties van de in aanmerking komende producten.</span><span class="sxs-lookup"><span data-stu-id="bdfc2-117">For example, your organization can have 3000 Office 365 E3 licenses and 8500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="bdfc2-118">Uw organisatie moet minimaal 50 maand actieve Exchange Online-gebruikers hebben.</span><span class="sxs-lookup"><span data-stu-id="bdfc2-118">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="bdfc2-119">U kunt maximaal 250 prioriteit accounts volgen.</span><span class="sxs-lookup"><span data-stu-id="bdfc2-119">You can monitor up to 250 priority accounts.</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="bdfc2-120">Een prioriteit toevoegen aan accounts van de instellings pagina</span><span class="sxs-lookup"><span data-stu-id="bdfc2-120">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="bdfc2-121">Voeg prioritaire accounts toe op de **pagina instellingen**.</span><span class="sxs-lookup"><span data-stu-id="bdfc2-121">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="bdfc2-122">Ga naar het Microsoft 365-Beheercentrum <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="bdfc2-122">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="bdfc2-123">Ga naar **Setup**  >  **organisatie kennis** instellen en kies **weergeven** onder **uw belangrijkste accounts bijhouden**.</span><span class="sxs-lookup"><span data-stu-id="bdfc2-123">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="bdfc2-124">Selecteer **aan de slag** of **beheren**.</span><span class="sxs-lookup"><span data-stu-id="bdfc2-124">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="bdfc2-125">Typ op de pagina **prioriteits accounts toevoegen** in het veld zoeken de naam of het e-mailadres van de persoon die u wilt toevoegen aan de lijst prioriteits accounts.</span><span class="sxs-lookup"><span data-stu-id="bdfc2-125">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="bdfc2-126">U kunt ook uw e-mail drempel instellen voor mislukte of vertraagde e-mailberichten en een wekelijks rapport van de problemen met prioriteit accounts krijgen.</span><span class="sxs-lookup"><span data-stu-id="bdfc2-126">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="bdfc2-127">Selecteer de gebruiker en kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="bdfc2-127">Select the user and choose **Save**.</span></span>

<span data-ttu-id="bdfc2-128">U kunt ook prioriteit accounts toevoegen vanaf de pagina actieve gebruikers.</span><span class="sxs-lookup"><span data-stu-id="bdfc2-128">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="bdfc2-129">Prioriteit accounts toevoegen vanaf de pagina actieve gebruikers</span><span class="sxs-lookup"><span data-stu-id="bdfc2-129">Add priority accounts from Active users page</span></span>

<span data-ttu-id="bdfc2-130">Voeg prioriteit toe aan accounts van de pagina actieve gebruikers.</span><span class="sxs-lookup"><span data-stu-id="bdfc2-130">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="bdfc2-131">Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="bdfc2-131">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="bdfc2-132">Ga naar **gebruikers** met  >  **actieve gebruikers** en kies **...** boven aan de pagina.</span><span class="sxs-lookup"><span data-stu-id="bdfc2-132">Go to **Users** > **Active users** and choose **...** at the top of the page.</span></span> <span data-ttu-id="bdfc2-133">Selecteer **prioriteit accounts beheren**.</span><span class="sxs-lookup"><span data-stu-id="bdfc2-133">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="bdfc2-134">Selecteer **accounts toevoegen** en typ in het zoekveld op de pagina **accountnamen toevoegen** de naam van de persoon die u wilt toevoegen aan de lijst prioriteits accounts.</span><span class="sxs-lookup"><span data-stu-id="bdfc2-134">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="bdfc2-135">Selecteer de gebruiker en kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="bdfc2-135">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="bdfc2-136">Een gebruiker verwijderen uit de lijst met prioriteit accounts</span><span class="sxs-lookup"><span data-stu-id="bdfc2-136">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="bdfc2-137">Ga naar het Microsoft 365-Beheercentrum <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="bdfc2-137">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="bdfc2-138">Ga naar **Setup**  >  **organisatie kennis** instellen en kies **weergeven** onder **uw belangrijkste accounts bijhouden**.</span><span class="sxs-lookup"><span data-stu-id="bdfc2-138">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="bdfc2-139">Kies op de pagina **uw meeste accounts bewaken** de optie **prioriteit accounts** onder **deze functie beheren**.</span><span class="sxs-lookup"><span data-stu-id="bdfc2-139">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="bdfc2-140">Selecteer op de pagina **Priority accounts** de gebruikers of gebruikers die u wilt verwijderen uit de lijst en kies **accounts verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="bdfc2-140">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bdfc2-141">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="bdfc2-141">Related topics</span></span>

[<span data-ttu-id="bdfc2-142">Prioritaire accounts gebruiken in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bdfc2-142">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)