---
title: Geblokkeerde gebruikers verwijderen uit de portal voor gebruikers met beperkte rechten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
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
ms.openlocfilehash: f9865b409be6bce14b84a9175e8f17cdad58befe
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351005"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-office-365"></a><span data-ttu-id="5dedd-104">Geblokkeerde gebruikers verwijderen uit de portal voor gebruikers met beperkte rechten in Office 365</span><span class="sxs-lookup"><span data-stu-id="5dedd-104">Remove blocked users from the Restricted Users portal in Office 365</span></span>

<span data-ttu-id="5dedd-105">Als een gebruiker een van de uitgaande verzendlimieten overschrijdt zoals beschreven in [de service-limieten](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) of in [uitgaande spambeleid](configure-the-outbound-spam-policy.md), is het verzenden van e-mail door de gebruiker beperkt, maar kunnen ze wel e-mail ontvangen.</span><span class="sxs-lookup"><span data-stu-id="5dedd-105">If a user exceeds one of the outbound sending limits as specified in [the service limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or in [outbound spam policies](configure-the-outbound-spam-policy.md), the user is restricted from sending email, but they can still receive email.</span></span>

<span data-ttu-id="5dedd-106">De gebruiker wordt toegevoegd aan de portal voor gebruikers met beperkte rechten in het beveiligings- en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="5dedd-106">The user is added to the Restricted Users portal in the Security & Compliance Center.</span></span> <span data-ttu-id="5dedd-107">Wanneer ze een e-mailbericht proberen te verzenden, wordt het bericht teruggestuurd in een rapport over niet-uitgevoerde bezorging (ook wel een NDR genoemd of niet-bezorgd berichten) met de foutcode [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) en de volgende tekst:</span><span class="sxs-lookup"><span data-stu-id="5dedd-107">When they try to send email, the message is returned in a non-delivery report (also known as an NDR or bounce messages) with the error code [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) and the following text:</span></span>

> <span data-ttu-id="5dedd-108">'Uw bericht kan niet worden bezorgd omdat u niet als een geldige afzender bent herkend.</span><span class="sxs-lookup"><span data-stu-id="5dedd-108">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="5dedd-109">De meest voorkomende reden hiervoor is dat het e-mailadres verdacht is van het verzenden van spam en dat er geen e-mail meer mag worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="5dedd-109">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="5dedd-110">Neemt u contact op met de beheerder voor hulp.</span><span class="sxs-lookup"><span data-stu-id="5dedd-110">Contact  your email admin for assistance.</span></span> <span data-ttu-id="5dedd-111">Externe server retourneerde '550 5.1.8 Toegang geweigerd, slechte uitgaande afzender.'</span><span class="sxs-lookup"><span data-stu-id="5dedd-111">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

<span data-ttu-id="5dedd-112">Beheerders kunnen gebruikers verwijderen uit de portal met beperkte verzenders in het beveiligings- en compliancecentrum of in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5dedd-112">Admins can remove users from the Restricted Senders portal in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5dedd-113">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="5dedd-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5dedd-114">U opent het beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="5dedd-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="5dedd-115">Als u rechtstreeks naar de pagina met **Beperkte gebruikers** wilt gaan, gebruik dan <https://protection.office.com/restrictedusers>.</span><span class="sxs-lookup"><span data-stu-id="5dedd-115">To go directly to the **Restricted Users** page, use <https://protection.office.com/restrictedusers>.</span></span>

- <span data-ttu-id="5dedd-116">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5dedd-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="5dedd-117">U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="5dedd-117">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="5dedd-118">Als u gebruikers wilt verwijderen uit de portal voor gebruikers met beperkte rechten, moet u lid zijn van **Organisatiebeheer** of **Beveiligingsbeheer**-rollengroep.</span><span class="sxs-lookup"><span data-stu-id="5dedd-118">To remove users from the Restricted Users portal, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="5dedd-119">Voor alleen-lezen toegang tot de portal met beperkte gebruikers moet u lid zijn van de **Beveiligingslezer**-groep.</span><span class="sxs-lookup"><span data-stu-id="5dedd-119">For read-only access to the Restricted Users portal, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="5dedd-120">Zie [Machtigingen in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="5dedd-120">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="5dedd-121">Een afzender die de uitgaande e-maillimieten overschrijdt, is een indicator van een verdacht account.</span><span class="sxs-lookup"><span data-stu-id="5dedd-121">A sender exceeding the outbound email limits is an indicator of a compromised account.</span></span> <span data-ttu-id="5dedd-122">Voordat u de gebruiker verwijdert uit de portal met beperkte gebruikers, moet u de vereiste stappen volgen om het beheer van het account te herstellen.</span><span class="sxs-lookup"><span data-stu-id="5dedd-122">Before you remove the user from the Restricted Users portal, be sure to follow the required steps to regain control of their account.</span></span> <span data-ttu-id="5dedd-123">Zie voor meer informatie [Reageren op een verdacht e-mailaccount in Office 365](responding-to-a-compromised-email-account.md).</span><span class="sxs-lookup"><span data-stu-id="5dedd-123">For more information, see [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

## <a name="use-the-security--compliance-center-to-remove-a-user-from-the-restricted-users-list"></a><span data-ttu-id="5dedd-124">Ga naar het beveiligings- en compliancecentrum om een gebruiker te verwijderen uit de lijst met beperkte gebruikers</span><span class="sxs-lookup"><span data-stu-id="5dedd-124">Use the Security & Compliance Center to remove a user from the Restricted Users list</span></span>

1. <span data-ttu-id="5dedd-125">Ga in het beveiligings- en compliancecentrum naar **Risicobeheer** \> **Bekijken** \> **Quarantaine**.</span><span class="sxs-lookup"><span data-stu-id="5dedd-125">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Restricted users**.</span></span>

2. <span data-ttu-id="5dedd-126">Zoek en selecteer de gebruiker die u wilt deblokkeren.</span><span class="sxs-lookup"><span data-stu-id="5dedd-126">Find and select the user that you want to unblock.</span></span> <span data-ttu-id="5dedd-127">Klik in de kolom **Acties** op **Blokkering opheffen**.</span><span class="sxs-lookup"><span data-stu-id="5dedd-127">In the **Actions** column, click **Unblock**.</span></span>

3. <span data-ttu-id="5dedd-128">Er wordt een doorlopende informatie weergeven over het account waarvan de verzending beperkt is.</span><span class="sxs-lookup"><span data-stu-id="5dedd-128">A fly-out will go into the details about the account whose sending is restricted.</span></span> <span data-ttu-id="5dedd-129">Neem de aanbevelingen door om er zeker van te zijn dat u de juiste acties neemt voor het geval dat het account werkelijk is aangetast.</span><span class="sxs-lookup"><span data-stu-id="5dedd-129">You should go through the recommendations to ensure you're taking the proper actions in case the account is actually compromised.</span></span> <span data-ttu-id="5dedd-130">Selecteer **Volgende** indien afgerond.</span><span class="sxs-lookup"><span data-stu-id="5dedd-130">Click **Next** when done.</span></span>

4. <span data-ttu-id="5dedd-131">Het volgende scherm biedt aanbevelingen om toekomstige inbreuk te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="5dedd-131">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="5dedd-132">Meervoudige verificatie (MFA) inschakelen en de wachtwoorden wijzigen, is een goed beveiligingsmiddel.</span><span class="sxs-lookup"><span data-stu-id="5dedd-132">Enabling multi-factor authentication (MFA) and changing the passwords are a good defense.</span></span> <span data-ttu-id="5dedd-133">Klik op **Blokkering opheffen van gebruikers** indien afgerond.</span><span class="sxs-lookup"><span data-stu-id="5dedd-133">Click **Unblock user** when done.</span></span>

5. <span data-ttu-id="5dedd-134">Klik op **Ja** ter bevestiging.</span><span class="sxs-lookup"><span data-stu-id="5dedd-134">Click **Yes** to confirm the change.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5dedd-135">Het kan 30 minuten of langer duren voordat er beperkingen zijn verwijderd.</span><span class="sxs-lookup"><span data-stu-id="5dedd-135">It may take 30 minutes or more before restrictions are removed.</span></span>

## <a name="verify-the-alert-settings-for-restricted-users"></a><span data-ttu-id="5dedd-136">De instellingen voor de waarschuwing voor gebruikers met beperkte toegang verifiëren</span><span class="sxs-lookup"><span data-stu-id="5dedd-136">Verify the alert settings for restricted users</span></span>

<span data-ttu-id="5dedd-137">In het standaard waarschuwingsbeleid genaamd **Gebruiker beperkt tot het verzenden van e-mail** worden beheerders automatisch gewaarschuwd wanneer gebruikers geblokkeerd zijn bij het verzend van e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="5dedd-137">The default alert policy named **User restricted from sending email** will automatically notify admins when users are blocked from sending outbound mail.</span></span> <span data-ttu-id="5dedd-138">U kunt deze instellingen controleren en aanvullende gebruikers toevoegen om op de hoogte te stellen.</span><span class="sxs-lookup"><span data-stu-id="5dedd-138">You can verify these settings and add additional users to notify.</span></span> <span data-ttu-id="5dedd-139">Zie voor meer informatie over waarschuwingsbeleid, [Waarschuwingsbeleid in het beveiligings- en compliancecentrum](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="5dedd-139">For more information about alert policies, see [Alert policies in the security and compliance center](../../compliance/alert-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5dedd-140">Om meldingen te laten werken, moet zoeken in het auditlogboek zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="5dedd-140">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="5dedd-141">Voor meer informatie, zie [Auditlogboeken zoeken in- of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="5dedd-141">For more information, see [Turn the audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="5dedd-142">Ga in het beveiligings- en compliancecentrum naar **Waarschuwingen** \> **Waarschuwingsbeleid**.</span><span class="sxs-lookup"><span data-stu-id="5dedd-142">In the Security & Compliance Center, go to **Alerts** \> **Alert policies**.</span></span>

2. <span data-ttu-id="5dedd-143">Zoek en selecteer een **Gebruiker valt onder beperkte verzending van e-mail**-waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="5dedd-143">Find an select the **User restricted from sending email** alert.</span></span>

3. <span data-ttu-id="5dedd-144">In de doorlopende informatie die wordt weergegeven, controleert of configureert u de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="5dedd-144">In the flyout that appears, verify or configure the following settings:</span></span>

   - <span data-ttu-id="5dedd-145">**Status**: Controleer of de waarschuwing is ingesteld op ![Wisselknop aan](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span><span class="sxs-lookup"><span data-stu-id="5dedd-145">**Status**: Verify the alert is turned on ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="5dedd-146">**Geadresseerden**: Klik op **Bewerken** en controleer of configureer de volgende instellingen in het snelmenu **Geadresseerden bewerken**:</span><span class="sxs-lookup"><span data-stu-id="5dedd-146">**Email recipients**: Click **Edit** and verify or configure the following settings in the **Edit recipients** flyout that appears:</span></span>

     - <span data-ttu-id="5dedd-147">**E-mailmeldingen verzenden**: Controleer of het selectievakje is ingeschakeld (**Aan**).</span><span class="sxs-lookup"><span data-stu-id="5dedd-147">**Send email notifications**: Verify the check box is selected (**On**).</span></span>

     - <span data-ttu-id="5dedd-148">**Geadresseerden**: de standaardwaarde is **HuurderBeheerders** (betekenis, **wereldwijde beheerder** leden).</span><span class="sxs-lookup"><span data-stu-id="5dedd-148">**Email recipients**: The default value is **TenantAdmins** (meaning, **Global admin** members).</span></span> <span data-ttu-id="5dedd-149">Als u meer geadresseerden wilt toevoegen, klikt u in een leeg gebied van het vak.</span><span class="sxs-lookup"><span data-stu-id="5dedd-149">To add more recipients, click in a blank area of the box.</span></span> <span data-ttu-id="5dedd-150">Een lijst met geadresseerden wordt weergegeven en u kunt een naam typen om een geadresseerde te filteren en te selecteren.</span><span class="sxs-lookup"><span data-stu-id="5dedd-150">A list of recipients will appear, and you can start typing a name to filter and select a recipient.</span></span> <span data-ttu-id="5dedd-151">U kunt een bestaande geadresseerde verwijderen uit het vak door te klikken op ![Pictogram verwijderen](../../media/scc-remove-icon.png) naast de naam.</span><span class="sxs-lookup"><span data-stu-id="5dedd-151">You can remove an existing recipient from the box by clicking ![Remove icon](../../media/scc-remove-icon.png) next to their name.</span></span>

     - <span data-ttu-id="5dedd-152">**Dagelijkse meldingslimiet**: de standaardwaarde is **Geen limiet** maar u kunt een limiet selecteren voor het maximum aantal meldingen per dag.</span><span class="sxs-lookup"><span data-stu-id="5dedd-152">**Daily notification limit**: The default value is **No limit** but you can select a limit for the maximum number of notifications per day.</span></span>

     <span data-ttu-id="5dedd-153">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="5dedd-153">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="5dedd-154">Wanneer u terug bent de doorlopende informatie **Gebruiker valt onder beperkte verzending van e-mail**, klikt u op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="5dedd-154">Back on the **User restricted from sending email** flyout, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a><span data-ttu-id="5dedd-155">Exchange Online PowerShell gebruiken om gebruikers weer te geven en te verwijderen uit de lijst met beperkte gebruikers</span><span class="sxs-lookup"><span data-stu-id="5dedd-155">Use Exchange Online PowerShell to view and remove users from the Restricted Users list</span></span>

<span data-ttu-id="5dedd-156">Voer de volgende opdracht uit om deze lijst weer te geven met gebruikers die geen e-mail kunnen verzenden:</span><span class="sxs-lookup"><span data-stu-id="5dedd-156">To view this list of users that are restricted from sending email, run the following command:</span></span>

```powershell
Get-BlockedSenderAddress
```

<span data-ttu-id="5dedd-157">Als u meer informatie over een specifieke gebruiker wilt bekijken, vervangt u \<e-mailadres\> door hun e-mailadres en voert u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="5dedd-157">To view details about a specific user, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="5dedd-158">Zie [OntvangAdresGeblokkeerdeVerzender](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="5dedd-158">For detailed syntax and parameter information, see [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress).</span></span>

<span data-ttu-id="5dedd-159">Als u een gebruiker wilt verwijderen uit de lijst van beperkte gebruikers, vervangt u het \<e-mailadres\> door hun e-mailadres en voert u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="5dedd-159">To remove a user from the Restricted Users list, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="5dedd-160">Zie [VerwijderAdresGeblokkeerdeVerzender](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="5dedd-160">For detailed syntax and parameter information, see [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress).</span></span>
