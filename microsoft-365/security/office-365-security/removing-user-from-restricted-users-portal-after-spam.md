---
title: Geblokkeerde gebruikers verwijderen uit de portal voor gebruikers met beperkte rechten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Beheerders kunnen meer informatie krijgen over het verwijderen van gebruikers uit de portal voor gebruikers met beperkte rechten in Office 365. Gebruikers worden toegevoegd aan de portal gebruikers met beperkte rechten voor het verzenden van uitgaande spam, meestal vanwege een inbreuk op het account.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c63d50fcf24e19c6a3265d57ea34fb8ab852c61c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201553"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-office-365"></a><span data-ttu-id="5dc80-104">Geblokkeerde gebruikers verwijderen uit de portal voor gebruikers met beperkte rechten in Office 365</span><span class="sxs-lookup"><span data-stu-id="5dc80-104">Remove blocked users from the Restricted Users portal in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="5dc80-105">Als een gebruiker een van de uitgaande verzendlimieten overschrijdt zoals beschreven in [de service-limieten](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) of in [uitgaande spambeleid](configure-the-outbound-spam-policy.md), is het verzenden van e-mail door de gebruiker beperkt, maar kunnen ze wel e-mail ontvangen.</span><span class="sxs-lookup"><span data-stu-id="5dc80-105">If a user exceeds one of the outbound sending limits as specified in [the service limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or in [outbound spam policies](configure-the-outbound-spam-policy.md), the user is restricted from sending email, but they can still receive email.</span></span>

<span data-ttu-id="5dc80-106">De gebruiker wordt toegevoegd aan de portal voor gebruikers met beperkte rechten in het beveiligings- en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="5dc80-106">The user is added to the Restricted Users portal in the Security & Compliance Center.</span></span> <span data-ttu-id="5dc80-107">Wanneer ze een e-mailbericht proberen te verzenden, wordt het bericht teruggestuurd in een rapport over niet-uitgevoerde bezorging (ook wel een NDR genoemd of niet-bezorgd berichten) met de foutcode [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) en de volgende tekst:</span><span class="sxs-lookup"><span data-stu-id="5dc80-107">When they try to send email, the message is returned in a non-delivery report (also known as an NDR or bounce messages) with the error code [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) and the following text:</span></span>

> <span data-ttu-id="5dc80-108">'Uw bericht kan niet worden bezorgd omdat u niet als een geldige afzender bent herkend.</span><span class="sxs-lookup"><span data-stu-id="5dc80-108">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="5dc80-109">De meest voorkomende reden hiervoor is dat het e-mailadres verdacht is van het verzenden van spam en dat er geen e-mail meer mag worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="5dc80-109">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="5dc80-110">Neemt u contact op met de beheerder voor hulp.</span><span class="sxs-lookup"><span data-stu-id="5dc80-110">Contact  your email admin for assistance.</span></span> <span data-ttu-id="5dc80-111">Externe server retourneerde '550 5.1.8 Toegang geweigerd, slechte uitgaande afzender.'</span><span class="sxs-lookup"><span data-stu-id="5dc80-111">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

<span data-ttu-id="5dc80-112">Beheerders kunnen gebruikers verwijderen uit de portal met beperkte verzenders in het beveiligings- en compliancecentrum of in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5dc80-112">Admins can remove users from the Restricted Senders portal in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5dc80-113">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="5dc80-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5dc80-114">U opent het beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="5dc80-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="5dc80-115">Als u rechtstreeks naar de pagina met **Beperkte gebruikers** wilt gaan, gebruik dan <https://protection.office.com/restrictedusers>.</span><span class="sxs-lookup"><span data-stu-id="5dc80-115">To go directly to the **Restricted Users** page, use <https://protection.office.com/restrictedusers>.</span></span>

- <span data-ttu-id="5dc80-116">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5dc80-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="5dc80-117">U moet beschikken over bepaalde machtigingen om de procedures in dit onderwerp te kunnen uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="5dc80-117">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="5dc80-118">Als u gebruikers wilt verwijderen uit de portal voor gebruikers met beperkte rechten, moet u lid zijn van een van de volgende rolgroepen:</span><span class="sxs-lookup"><span data-stu-id="5dc80-118">To remove users from the Restricted Users portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="5dc80-119">**Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="5dc80-119">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="5dc80-120">**Organisatiebeheer** of **Hygiënebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="5dc80-120">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="5dc80-121">Voor alleen-lezentoegang voor de portal voor gebruikers met beperkte rechten, moet u lid zijn van een van de volgende rolgroepen:</span><span class="sxs-lookup"><span data-stu-id="5dc80-121">For read-only access to the Restricted Users portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="5dc80-122">**Beveiligingslezer** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="5dc80-122">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="5dc80-123">**Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="5dc80-123">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="5dc80-124">Een afzender die de uitgaande e-maillimieten overschrijdt, is een indicator van een verdacht account.</span><span class="sxs-lookup"><span data-stu-id="5dc80-124">A sender exceeding the outbound email limits is an indicator of a compromised account.</span></span> <span data-ttu-id="5dc80-125">Voordat u de gebruiker verwijdert uit de portal met beperkte gebruikers, moet u de vereiste stappen volgen om het beheer van het account te herstellen.</span><span class="sxs-lookup"><span data-stu-id="5dc80-125">Before you remove the user from the Restricted Users portal, be sure to follow the required steps to regain control of their account.</span></span> <span data-ttu-id="5dc80-126">Zie voor meer informatie [Reageren op een verdacht e-mailaccount in Office 365](responding-to-a-compromised-email-account.md).</span><span class="sxs-lookup"><span data-stu-id="5dc80-126">For more information, see [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

## <a name="use-the-security--compliance-center-to-remove-a-user-from-the-restricted-users-list"></a><span data-ttu-id="5dc80-127">Ga naar het beveiligings- en compliancecentrum om een gebruiker te verwijderen uit de lijst met beperkte gebruikers</span><span class="sxs-lookup"><span data-stu-id="5dc80-127">Use the Security & Compliance Center to remove a user from the Restricted Users list</span></span>

1. <span data-ttu-id="5dc80-128">Ga in het beveiligings- en compliancecentrum naar **Risicobeheer** \> **Bekijken** \> **Quarantaine**.</span><span class="sxs-lookup"><span data-stu-id="5dc80-128">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Restricted users**.</span></span>

2. <span data-ttu-id="5dc80-129">Zoek en selecteer de gebruiker die u wilt deblokkeren.</span><span class="sxs-lookup"><span data-stu-id="5dc80-129">Find and select the user that you want to unblock.</span></span> <span data-ttu-id="5dc80-130">Klik in de kolom **Acties** op **Blokkering opheffen**.</span><span class="sxs-lookup"><span data-stu-id="5dc80-130">In the **Actions** column, click **Unblock**.</span></span>

3. <span data-ttu-id="5dc80-131">Er wordt een doorlopende informatie weergeven over het account waarvan de verzending beperkt is.</span><span class="sxs-lookup"><span data-stu-id="5dc80-131">A fly-out will go into the details about the account whose sending is restricted.</span></span> <span data-ttu-id="5dc80-132">Neem de aanbevelingen door om er zeker van te zijn dat u de juiste acties neemt voor het geval dat het account werkelijk is aangetast.</span><span class="sxs-lookup"><span data-stu-id="5dc80-132">You should go through the recommendations to ensure you're taking the proper actions in case the account is actually compromised.</span></span> <span data-ttu-id="5dc80-133">Selecteer **Volgende** indien afgerond.</span><span class="sxs-lookup"><span data-stu-id="5dc80-133">Click **Next** when done.</span></span>

4. <span data-ttu-id="5dc80-134">Het volgende scherm biedt aanbevelingen om toekomstige inbreuk te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="5dc80-134">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="5dc80-135">Meervoudige verificatie (MFA) inschakelen en de wachtwoorden wijzigen, is een goed beveiligingsmiddel.</span><span class="sxs-lookup"><span data-stu-id="5dc80-135">Enabling multi-factor authentication (MFA) and changing the passwords are a good defense.</span></span> <span data-ttu-id="5dc80-136">Klik op **Blokkering opheffen van gebruikers** indien afgerond.</span><span class="sxs-lookup"><span data-stu-id="5dc80-136">Click **Unblock user** when done.</span></span>

5. <span data-ttu-id="5dc80-137">Klik op **Ja** ter bevestiging.</span><span class="sxs-lookup"><span data-stu-id="5dc80-137">Click **Yes** to confirm the change.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5dc80-138">Het kan 30 minuten of langer duren voordat er beperkingen zijn verwijderd.</span><span class="sxs-lookup"><span data-stu-id="5dc80-138">It may take 30 minutes or more before restrictions are removed.</span></span>

## <a name="verify-the-alert-settings-for-restricted-users"></a><span data-ttu-id="5dc80-139">De instellingen voor de waarschuwing voor gebruikers met beperkte toegang verifiëren</span><span class="sxs-lookup"><span data-stu-id="5dc80-139">Verify the alert settings for restricted users</span></span>

<span data-ttu-id="5dc80-140">In het standaard waarschuwingsbeleid genaamd **Gebruiker beperkt tot het verzenden van e-mail** worden beheerders automatisch gewaarschuwd wanneer gebruikers geblokkeerd zijn bij het verzend van e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="5dc80-140">The default alert policy named **User restricted from sending email** will automatically notify admins when users are blocked from sending outbound mail.</span></span> <span data-ttu-id="5dc80-141">U kunt deze instellingen controleren en aanvullende gebruikers toevoegen om op de hoogte te stellen.</span><span class="sxs-lookup"><span data-stu-id="5dc80-141">You can verify these settings and add additional users to notify.</span></span> <span data-ttu-id="5dc80-142">Zie voor meer informatie over waarschuwingsbeleid, [Waarschuwingsbeleid in het beveiligings- en compliancecentrum](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="5dc80-142">For more information about alert policies, see [Alert policies in the security and compliance center](../../compliance/alert-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5dc80-143">Om meldingen te laten werken, moet zoeken in het auditlogboek zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="5dc80-143">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="5dc80-144">Voor meer informatie, zie [Auditlogboeken zoeken in- of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="5dc80-144">For more information, see [Turn the audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="5dc80-145">Ga in het beveiligings- en compliancecentrum naar **Waarschuwingen** \> **Waarschuwingsbeleid**.</span><span class="sxs-lookup"><span data-stu-id="5dc80-145">In the Security & Compliance Center, go to **Alerts** \> **Alert policies**.</span></span>

2. <span data-ttu-id="5dc80-146">Zoek en selecteer een **Gebruiker valt onder beperkte verzending van e-mail**-waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="5dc80-146">Find an select the **User restricted from sending email** alert.</span></span>

3. <span data-ttu-id="5dc80-147">In de doorlopende informatie die wordt weergegeven, controleert of configureert u de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="5dc80-147">In the flyout that appears, verify or configure the following settings:</span></span>

   - <span data-ttu-id="5dc80-148">**Status**: Controleer of de waarschuwing is ingesteld op ![Wisselknop aan](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span><span class="sxs-lookup"><span data-stu-id="5dc80-148">**Status**: Verify the alert is turned on ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="5dc80-149">**Geadresseerden**: Klik op **Bewerken** en controleer of configureer de volgende instellingen in het snelmenu **Geadresseerden bewerken**:</span><span class="sxs-lookup"><span data-stu-id="5dc80-149">**Email recipients**: Click **Edit** and verify or configure the following settings in the **Edit recipients** flyout that appears:</span></span>

     - <span data-ttu-id="5dc80-150">**E-mailmeldingen verzenden**: Controleer of het selectievakje is ingeschakeld (**Aan**).</span><span class="sxs-lookup"><span data-stu-id="5dc80-150">**Send email notifications**: Verify the check box is selected (**On**).</span></span>

     - <span data-ttu-id="5dc80-151">**Geadresseerden**: de standaardwaarde is **HuurderBeheerders** (betekenis, **wereldwijde beheerder** leden).</span><span class="sxs-lookup"><span data-stu-id="5dc80-151">**Email recipients**: The default value is **TenantAdmins** (meaning, **Global admin** members).</span></span> <span data-ttu-id="5dc80-152">Als u meer geadresseerden wilt toevoegen, klikt u in een leeg gebied van het vak.</span><span class="sxs-lookup"><span data-stu-id="5dc80-152">To add more recipients, click in a blank area of the box.</span></span> <span data-ttu-id="5dc80-153">Een lijst met geadresseerden wordt weergegeven en u kunt een naam typen om een geadresseerde te filteren en te selecteren.</span><span class="sxs-lookup"><span data-stu-id="5dc80-153">A list of recipients will appear, and you can start typing a name to filter and select a recipient.</span></span> <span data-ttu-id="5dc80-154">U kunt een bestaande geadresseerde verwijderen uit het vak door te klikken op ![Pictogram verwijderen](../../media/scc-remove-icon.png) naast de naam.</span><span class="sxs-lookup"><span data-stu-id="5dc80-154">You can remove an existing recipient from the box by clicking ![Remove icon](../../media/scc-remove-icon.png) next to their name.</span></span>

     - <span data-ttu-id="5dc80-155">**Dagelijkse meldingslimiet**: de standaardwaarde is **Geen limiet** maar u kunt een limiet selecteren voor het maximum aantal meldingen per dag.</span><span class="sxs-lookup"><span data-stu-id="5dc80-155">**Daily notification limit**: The default value is **No limit** but you can select a limit for the maximum number of notifications per day.</span></span>

     <span data-ttu-id="5dc80-156">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="5dc80-156">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="5dc80-157">Wanneer u terug bent de doorlopende informatie **Gebruiker valt onder beperkte verzending van e-mail**, klikt u op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="5dc80-157">Back on the **User restricted from sending email** flyout, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a><span data-ttu-id="5dc80-158">Exchange Online PowerShell gebruiken om gebruikers weer te geven en te verwijderen uit de lijst met beperkte gebruikers</span><span class="sxs-lookup"><span data-stu-id="5dc80-158">Use Exchange Online PowerShell to view and remove users from the Restricted Users list</span></span>

<span data-ttu-id="5dc80-159">Voer de volgende opdracht uit om deze lijst weer te geven met gebruikers die geen e-mail kunnen verzenden:</span><span class="sxs-lookup"><span data-stu-id="5dc80-159">To view this list of users that are restricted from sending email, run the following command:</span></span>

```powershell
Get-BlockedSenderAddress
```

<span data-ttu-id="5dc80-160">Als u meer informatie over een specifieke gebruiker wilt bekijken, vervangt u \<emailaddress\> door het e-mailadres van die gebruiker en voert u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="5dc80-160">To view details about a specific user, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="5dc80-161">Zie [OntvangAdresGeblokkeerdeVerzender](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="5dc80-161">For detailed syntax and parameter information, see [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress).</span></span>

<span data-ttu-id="5dc80-162">Als u een gebruiker wilt verwijderen uit de lijst met beperkte gebruikers, vervangt u \<emailaddress\> door het e-mailadres van die gebruiker en voert u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="5dc80-162">To remove a user from the Restricted Users list, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="5dc80-163">Zie [VerwijderAdresGeblokkeerdeVerzender](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="5dc80-163">For detailed syntax and parameter information, see [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress).</span></span>
