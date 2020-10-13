---
title: Geautomatiseerd onderzoek en antwoord (lucht)-aan de slag
keywords: AIR, autoIR, ATP, automatisch, onderzoek, antwoord, herstel, bedreiging, Geavanceerd, bedreiging, bescherming
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 09/29/2020
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Ga aan de slag met het gebruik van geautomatiseerde onderzoek-en antwoord mogelijkheden in Microsoft Defender voor Office 365.
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 340fc4851043ff917eaff6f237c3ad7d5810a4cb
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430917"
---
# <a name="get-started-using-automated-investigation-and-response-air-in-office-365"></a><span data-ttu-id="11463-104">Aan de slag met geautomatiseerd onderzoek en antwoord (lucht) in Office 365</span><span class="sxs-lookup"><span data-stu-id="11463-104">Get started using automated investigation and response (AIR) in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="11463-105">[Microsoft Defender voor Office 365](office-365-atp.md) bevat krachtige functies voor automatisch onderzoek en Reacties (lucht) waarmee u tijd en inspanningen van uw beveiligingsactiviteiten kunnen opslaan.</span><span class="sxs-lookup"><span data-stu-id="11463-105">[Microsoft Defender for Office 365](office-365-atp.md) includes powerful automated investigation and response (AIR) capabilities that can save your security operations team time and effort.</span></span> <span data-ttu-id="11463-106">Aangezien waarschuwingen worden geactiveerd, kunt u deze meldingen nakijken, van een prioriteit voorzien en hierop reageren.</span><span class="sxs-lookup"><span data-stu-id="11463-106">As alerts are triggered, it's up to your security operations team to review, prioritize, and respond to those alerts.</span></span> <span data-ttu-id="11463-107">U kunt het volume van inkomende waarschuwingen overweldigen.</span><span class="sxs-lookup"><span data-stu-id="11463-107">Keeping up with the volume of incoming alerts can be overwhelming.</span></span> <span data-ttu-id="11463-108">Een deel van dit helpt te automatiseren.</span><span class="sxs-lookup"><span data-stu-id="11463-108">Automating some of this can help.</span></span> <span data-ttu-id="11463-109">Met lucht kan uw beveiligingsteam zich richten op taken met een hoge prioriteit zonder dat dit de activering van waarschuwingen verliest.</span><span class="sxs-lookup"><span data-stu-id="11463-109">With AIR, your security operations team can focus on higher-priority tasks without losing sight of alerts that are triggered.</span></span>

<span data-ttu-id="11463-110">Dit artikel bevat:</span><span class="sxs-lookup"><span data-stu-id="11463-110">This article includes:</span></span>
- <span data-ttu-id="11463-111">De [algehele stroom](#the-overall-flow-of-air) van lucht;</span><span class="sxs-lookup"><span data-stu-id="11463-111">The [overall flow](#the-overall-flow-of-air) of AIR;</span></span>
- <span data-ttu-id="11463-112">[Hoe u lucht verzorgt](#how-to-get-air); en</span><span class="sxs-lookup"><span data-stu-id="11463-112">[How to get AIR](#how-to-get-air); and</span></span> 
- <span data-ttu-id="11463-113">De [vereiste machtigingen](#required-permissions-to-use-air-capabilities) voor het configureren of gebruiken van lucht capaciteiten.</span><span class="sxs-lookup"><span data-stu-id="11463-113">The [required permissions](#required-permissions-to-use-air-capabilities) to configure or use AIR capabilities.</span></span> 

## <a name="the-overall-flow-of-air"></a><span data-ttu-id="11463-114">De totale luchtstroom</span><span class="sxs-lookup"><span data-stu-id="11463-114">The overall flow of AIR</span></span>

<span data-ttu-id="11463-115">Op een hoog niveau wordt een waarschuwing geactiveerd en wordt een geautomatiseerd onderzoek gestart, wat leidt tot bevindingen en aanbevelingen.</span><span class="sxs-lookup"><span data-stu-id="11463-115">At a high level, an alert is triggered, and a security playbook starts an automated investigation, which results in findings and recommendations.</span></span> <span data-ttu-id="11463-116">Dit is de algemene stroom van lucht, stap voor stap:</span><span class="sxs-lookup"><span data-stu-id="11463-116">Here's the overall flow of AIR, step by step:</span></span>

1. <span data-ttu-id="11463-117">Een geautomatiseerd onderzoek wordt op een van de volgende manieren gestart:</span><span class="sxs-lookup"><span data-stu-id="11463-117">An automated investigation is initiated in one of the following ways:</span></span>

   - <span data-ttu-id="11463-118">Een [waarschuwing](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) wordt geactiveerd door een gebeurtenis in Office waarmee een incident wordt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="11463-118">An [alert](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) is triggered by an Office event, which creates an incident.</span></span> <span data-ttu-id="11463-119">Afhankelijk van het type incident, begint een [beveiligings Playbook](automated-investigation-response-office.md#security-playbooks) een geautomatiseerd onderzoek.</span><span class="sxs-lookup"><span data-stu-id="11463-119">Depending on the type of incident, a [security playbook](automated-investigation-response-office.md#security-playbooks) starts an automated investigation.</span></span> 

     <span data-ttu-id="11463-120">------</span><span class="sxs-lookup"><span data-stu-id="11463-120">--- or ---</span></span>
   
   - <span data-ttu-id="11463-121">Een beveiligings analist [Start een automatisch onderzoek](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) tijdens het gebruik van de [Threat Explorer](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="11463-121">A security analyst [starts an automated investigation](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) while using [Threat Explorer](threat-explorer.md).</span></span>

2. <span data-ttu-id="11463-122">Tijdens een geautomatiseerde onderzoek wordt er extra informatie verzameld over het e-mailbericht in kwestie en de entiteiten die aan die e-mail zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="11463-122">While an automated investigation runs, it gathers additional data about the email in question and entities related to that email.</span></span> <span data-ttu-id="11463-123">Deze entiteiten kunnen bestanden, Url's en geadresseerden bevatten.</span><span class="sxs-lookup"><span data-stu-id="11463-123">Such entities can include files, URLs, and recipients.</span></span>  <span data-ttu-id="11463-124">Het vernieuwings bereik kan toenemen omdat er nieuwe en gerelateerde waarschuwingen worden geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="11463-124">The investigation's scope can increase as new and related alerts are triggered.</span></span>

3. <span data-ttu-id="11463-125">Tijdens en na een geautomatiseerd onderzoek zijn er [gegevens en resultaten](air-view-investigation-results.md) beschikbaar voor weergave.</span><span class="sxs-lookup"><span data-stu-id="11463-125">During and after an automated investigation, [details and results](air-view-investigation-results.md) are available to view.</span></span> <span data-ttu-id="11463-126">Resultaten omvatten [aanbevolen acties](air-remediation-actions.md) die kunnen worden uitgevoerd om bedreigingen te beantwoorden en te herstellen.</span><span class="sxs-lookup"><span data-stu-id="11463-126">Results include [recommended actions](air-remediation-actions.md) that can be taken to respond and remediate any threats that were found.</span></span> <span data-ttu-id="11463-127">Daarnaast is er een [Playbook-logboek](air-view-investigation-results.md#playbook-log) beschikbaar waarmee alle onderzoekactiviteiten worden bijgehouden.</span><span class="sxs-lookup"><span data-stu-id="11463-127">In addition, a [playbook log](air-view-investigation-results.md#playbook-log) is available that tracks all investigation activity.</span></span>

    <span data-ttu-id="11463-128">Als uw organisatie een aangepaste rapportage oplossing of een oplossing van een andere leverancier gebruikt, kunt u [de API Office 365 Management Activity gebruiken](air-custom-reporting.md) om informatie over geautomatiseerde onderzoeken en bedreigingen te bekijken.</span><span class="sxs-lookup"><span data-stu-id="11463-128">If your organization is using a custom reporting solution or a third-party solution, you can [use the Office 365 Management Activity API](air-custom-reporting.md) to view information about automated investigations and threats.</span></span>

4. <span data-ttu-id="11463-129">Uw team van beveiligingsactiviteiten beoordeelt het [onderzoek resultaat en aanbevelingen](air-view-investigation-results.md), en [keurt of weigert herstelacties](air-review-approve-pending-completed-actions.md).</span><span class="sxs-lookup"><span data-stu-id="11463-129">Your security operations team reviews the [investigation results and recommendations](air-view-investigation-results.md), and [approves or rejects remediation actions](air-review-approve-pending-completed-actions.md).</span></span> 

    <span data-ttu-id="11463-130">Wanneer herstelacties in behandeling zijn goedgekeurd (of afgekeurd), is het geautomatiseerde onderzoek voltooid.</span><span class="sxs-lookup"><span data-stu-id="11463-130">As pending remediation actions are approved (or rejected), the automated investigation completes.</span></span>

> [!NOTE]
> <span data-ttu-id="11463-131">In Office 365 ATP worden geen herstelacties automatisch uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="11463-131">In Office 365 ATP, no remediation actions are taken automatically.</span></span> <span data-ttu-id="11463-132">Herstelacties worden alleen uitgevoerd na goedkeuring van het beveiligingsteam van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="11463-132">Remediation actions are taken only upon approval by your organization's security team.</span></span> 

<span data-ttu-id="11463-133">Tijdens en na een proces van een geautomatiseerde onderzoek kan uw beveiligingsteam het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="11463-133">During and after an automated investigation process, your security team can do the following:</span></span>

- [<span data-ttu-id="11463-134">Details weergeven van een waarschuwing die is gerelateerd aan een onderzoek</span><span class="sxs-lookup"><span data-stu-id="11463-134">View details about an alert related to an investigation</span></span>](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [<span data-ttu-id="11463-135">De resultaten gegevens van een onderzoek weergeven</span><span class="sxs-lookup"><span data-stu-id="11463-135">View the results details of an investigation</span></span>](air-view-investigation-results.md#view-details-of-an-investigation)

- [<span data-ttu-id="11463-136">Acties controleren en goedkeuren als gevolg van een onderzoek</span><span class="sxs-lookup"><span data-stu-id="11463-136">Review and approve actions as a result of an investigation</span></span>](air-review-approve-pending-completed-actions.md)

> [!TIP]
> <span data-ttu-id="11463-137">Zie de werking van [lucht werken](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="11463-137">For more details, see [How AIR works](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).</span></span>

## <a name="how-to-get-air"></a><span data-ttu-id="11463-138">Hoe u lucht verzorgt</span><span class="sxs-lookup"><span data-stu-id="11463-138">How to get AIR</span></span>

<span data-ttu-id="11463-139">De lucht mogelijkheden zijn opgenomen in [Microsoft Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2).</span><span class="sxs-lookup"><span data-stu-id="11463-139">AIR capabilities are included in [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2).</span></span> <span data-ttu-id="11463-140">Uw [beleid moet echter zodanig zijn geconfigureerd](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) dat lucht goed werkt zoals verwacht.</span><span class="sxs-lookup"><span data-stu-id="11463-140">However, your [policies must be configured](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) in order for AIR to work as expected.</span></span> <span data-ttu-id="11463-141">Zorg er ook voor dat u het [waarschuwings beleid](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)van uw organisatie controleert en configureert.</span><span class="sxs-lookup"><span data-stu-id="11463-141">In addition, make sure to review and potentially configure your organization's [alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span></span> 

<span data-ttu-id="11463-142">Microsoft 365 biedt een groot aantal ingebouwde waarschuwingen waarmee beheerdersmachtigingen van Exchange kunnen identificeren, schadelijke activiteiten, potentiële externe en interne bedreigingen en informatiebeheer Risico's.</span><span class="sxs-lookup"><span data-stu-id="11463-142">Microsoft 365 provides many built-in alert policies that help identify Exchange admin permissions abuse, malware activity, potential external and internal threats, and information governance risks.</span></span> <span data-ttu-id="11463-143">Een aantal [standaard waarschuwings beleidsregels](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) kan automatisch onderzoek activeren.</span><span class="sxs-lookup"><span data-stu-id="11463-143">Several of the [default alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) can trigger automated investigations.</span></span> <span data-ttu-id="11463-144">Deze omvatten de volgende:</span><span class="sxs-lookup"><span data-stu-id="11463-144">These include the following:</span></span>

- <span data-ttu-id="11463-145">Er is een potentieel schadelijke URL klik gedetecteerd</span><span class="sxs-lookup"><span data-stu-id="11463-145">A potentially malicious URL click is detected</span></span>

- <span data-ttu-id="11463-146">Een e-mailbericht wordt door een gebruiker gemeldd als phishing</span><span class="sxs-lookup"><span data-stu-id="11463-146">An email message is reported by a user as phish</span></span>

- <span data-ttu-id="11463-147">E-mailberichten met malware worden verwijderd na levering</span><span class="sxs-lookup"><span data-stu-id="11463-147">Email messages containing malware are removed after delivery</span></span>

- <span data-ttu-id="11463-148">E-mailberichten met phishing-Url's worden verwijderd na levering</span><span class="sxs-lookup"><span data-stu-id="11463-148">Email messages containing phish URLs are removed after delivery</span></span>

- <span data-ttu-id="11463-149">Verdachte patronen voor het verzenden van e-mail worden gedetecteerd</span><span class="sxs-lookup"><span data-stu-id="11463-149">Suspicious email sending patterns are detected</span></span>

- <span data-ttu-id="11463-150">Een gebruiker mag geen e-mail verzenden</span><span class="sxs-lookup"><span data-stu-id="11463-150">A user is restricted from sending email</span></span>

<span data-ttu-id="11463-151">[Meer informatie over waarschuwingen en Air](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).</span><span class="sxs-lookup"><span data-stu-id="11463-151">[Learn more about alerts and AIR](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).</span></span>

## <a name="required-permissions-to-use-air-capabilities"></a><span data-ttu-id="11463-152">Vereiste machtigingen voor het gebruik van lucht mogelijkheden</span><span class="sxs-lookup"><span data-stu-id="11463-152">Required permissions to use AIR capabilities</span></span>

<span data-ttu-id="11463-153">Machtigingen worden toegekend via bepaalde rollen, zoals de functies die in de volgende tabel worden beschreven:</span><span class="sxs-lookup"><span data-stu-id="11463-153">Permissions are granted through certain roles, such as those that are described in the following table:</span></span> 

|<span data-ttu-id="11463-154">Taak</span><span class="sxs-lookup"><span data-stu-id="11463-154">Task</span></span> |<span data-ttu-id="11463-155">Vereiste functie (s)</span><span class="sxs-lookup"><span data-stu-id="11463-155">Role(s) required</span></span> |
|--|--|
|<span data-ttu-id="11463-156">LUCHT functies instellen</span><span class="sxs-lookup"><span data-stu-id="11463-156">To set up AIR features</span></span> |<span data-ttu-id="11463-157">Een van de volgende rollen:</span><span class="sxs-lookup"><span data-stu-id="11463-157">One of the following roles:</span></span> <br/><span data-ttu-id="11463-158">-Globale beheerder</span><span class="sxs-lookup"><span data-stu-id="11463-158">- Global Administrator</span></span><br/><span data-ttu-id="11463-159">-Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="11463-159">- Security Administrator</span></span> <br/><span data-ttu-id="11463-160">U kunt deze rollen toewijzen in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) of in het [beveiligings & nalevings centrum](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="11463-160">These roles can be assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) or in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span> |
|<span data-ttu-id="11463-161">Aanbevolen acties goedkeuren of afwijzen</span><span class="sxs-lookup"><span data-stu-id="11463-161">To approve or reject recommended actions</span></span>|<span data-ttu-id="11463-162">Een van de volgende rollen, toegewezen in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) of in het [beveiligings & nalevings centrum](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center):</span><span class="sxs-lookup"><span data-stu-id="11463-162">One of the following roles, assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) or in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)):</span></span><br/><span data-ttu-id="11463-163">-Globale beheerder</span><span class="sxs-lookup"><span data-stu-id="11463-163">- Global Administrator</span></span> <br/><span data-ttu-id="11463-164">-Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="11463-164">- Security Administrator</span></span><br/><span data-ttu-id="11463-165">-Beveiligings lezer</span><span class="sxs-lookup"><span data-stu-id="11463-165">- Security Reader</span></span> <br/><span data-ttu-id="11463-166">---en---</span><span class="sxs-lookup"><span data-stu-id="11463-166">--- and ---</span></span><br/><span data-ttu-id="11463-167">-Zoeken en wissen (deze rol wordt alleen toegewezen in het [nalevings centrum voor de beveiliging &](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="11463-167">- Search and Purge (this role is assigned only in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span> <span data-ttu-id="11463-168">Mogelijk moet u een nieuwe rolgroep maken en de rol zoeken en permanent toevoegen aan de nieuwe rollen groep toevoegen.)</span><span class="sxs-lookup"><span data-stu-id="11463-168">You might have to create a new role group there and add the Search and Purge role to that new role group.)</span></span>

<span data-ttu-id="11463-169">[Voor Microsoft Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) -licenties moet worden toegewezen:</span><span class="sxs-lookup"><span data-stu-id="11463-169">[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) licenses should be assigned to:</span></span>
- <span data-ttu-id="11463-170">Beveiligingsbeheerders (waaronder globale beheerders)</span><span class="sxs-lookup"><span data-stu-id="11463-170">Security administrators (including global administrators)</span></span>
- <span data-ttu-id="11463-171">Het bedrijfsactiviteiten team van uw organisatie (met inbegrip van beveiligings lezers en de functies met de rol zoeken en wissen)</span><span class="sxs-lookup"><span data-stu-id="11463-171">Your organization's security operations team (including security readers and those with the Search and Purge role)</span></span>
- <span data-ttu-id="11463-172">Eindgebruikers</span><span class="sxs-lookup"><span data-stu-id="11463-172">End users</span></span>

<span data-ttu-id="11463-173">Daarnaast moet u [Microsoft Defender voor Office 365-beleid](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) definiëren en toepassen om de beveiliging ter plaatse te kunnen indelen.</span><span class="sxs-lookup"><span data-stu-id="11463-173">In addition, [Microsoft Defender for Office 365 policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) must be defined and applied in order for protection to be in place.</span></span>

## <a name="next-steps"></a><span data-ttu-id="11463-174">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="11463-174">Next steps</span></span>

- [<span data-ttu-id="11463-175">Details en resultaten van een geautomatiseerd onderzoek weergeven</span><span class="sxs-lookup"><span data-stu-id="11463-175">See details and results of an automated investigation</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [<span data-ttu-id="11463-176">In behandeling zijnde acties controleren en goedkeuren</span><span class="sxs-lookup"><span data-stu-id="11463-176">Review and approve pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a><span data-ttu-id="11463-177">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="11463-177">Related articles</span></span>

- [<span data-ttu-id="11463-178">Automatisch onderzoek en herstel in Microsoft Defender voor eindpunten</span><span class="sxs-lookup"><span data-stu-id="11463-178">Automated investigation and remediation in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="11463-179">Automatisch onderzoek en antwoord in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="11463-179">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
