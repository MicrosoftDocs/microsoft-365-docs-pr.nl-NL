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
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe ze gebruikers kunnen verwijderen van de pagina voor gebruikers met beperkte rechten in de Microsoft 365 Defender-portal. Gebruikers worden toegevoegd aan de portal voor gebruikers met beperkte rechten voor het verzenden van uitgaande spam, meestal vanwege een inbreuk op het account.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 924db948103a4d3b45c499f433961762a45931af
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082850"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-microsoft-365"></a><span data-ttu-id="a566d-104">Geblokkeerde gebruikers verwijderen uit de portal voor gebruikers met beperkte rechten in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a566d-104">Remove blocked users from the Restricted users portal in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a566d-105">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="a566d-105">**Applies to**</span></span>
- [<span data-ttu-id="a566d-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a566d-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a566d-107">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="a566d-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a566d-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a566d-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="a566d-109">Als een gebruiker een van de uitgaande verzendlimieten overschrijdt zoals beschreven in [de service-limieten](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) of in [uitgaande spambeleid](configure-the-outbound-spam-policy.md), is het verzenden van e-mail door de gebruiker beperkt, maar kunnen ze wel e-mail ontvangen.</span><span class="sxs-lookup"><span data-stu-id="a566d-109">If a user exceeds one of the outbound sending limits as specified in [the service limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or in [outbound spam policies](configure-the-outbound-spam-policy.md), the user is restricted from sending email, but they can still receive email.</span></span>

<span data-ttu-id="a566d-110">De gebruiker wordt toegevoegd aan de pagina voor **gebruikers met beperkte rechten** in de Microsoft 365 Defender-portal.</span><span class="sxs-lookup"><span data-stu-id="a566d-110">The user is added to the **Restricted users** page in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="a566d-111">Wanneer ze een e-mailbericht proberen te verzenden, wordt het bericht teruggestuurd in een rapport over niet-uitgevoerde bezorging (ook wel een NDR genoemd of niet-bezorgd berichten) met de foutcode [5.1.8](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) en de volgende tekst:</span><span class="sxs-lookup"><span data-stu-id="a566d-111">When they try to send email, the message is returned in a non-delivery report (also known as an NDR or bounce messages) with the error code [5.1.8](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) and the following text:</span></span>

> <span data-ttu-id="a566d-112">'Uw bericht kan niet worden bezorgd omdat u niet als een geldige afzender bent herkend.</span><span class="sxs-lookup"><span data-stu-id="a566d-112">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="a566d-113">De meest voorkomende reden hiervoor is dat het e-mailadres verdacht is van het verzenden van spam en dat er geen e-mail meer mag worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="a566d-113">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="a566d-114">Neemt u contact op met de beheerder voor hulp.</span><span class="sxs-lookup"><span data-stu-id="a566d-114">Contact  your email admin for assistance.</span></span> <span data-ttu-id="a566d-115">Externe server retourneerde '550 5.1.8 Toegang geweigerd, slechte uitgaande afzender.'</span><span class="sxs-lookup"><span data-stu-id="a566d-115">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

<span data-ttu-id="a566d-116">Beheerders kunnen gebruikers verwijderen van de pagina voor gebruikers met beperkte rechten in Microsoft 365 Defender of in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a566d-116">Admins can remove users from the Restricted users page in the Microsoft 365 Defender or in Exchange Online PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a566d-117">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="a566d-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a566d-118">U opent de Microsoft 365 Defender-portal bij <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="a566d-118">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="a566d-119">Als u rechtstreeks naar de pagina voor **gebruikers met beperkte rechten** wilt gaan, gebruikt u <https://security.microsoft.com/restrictedusers>.</span><span class="sxs-lookup"><span data-stu-id="a566d-119">Too go directly to the **Restricted users** page, use <https://security.microsoft.com/restrictedusers>.</span></span>

- <span data-ttu-id="a566d-120">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als je verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a566d-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="a566d-121">U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="a566d-121">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="a566d-122">Als u gebruikers wilt verwijderen uit de portal voor gebruikers met beperkte rechten, moet u lid zijn van de rollengroep **Organisatiebeheer** of **Beveiligingsadministrator**.</span><span class="sxs-lookup"><span data-stu-id="a566d-122">To remove users from the Restricted users portal, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="a566d-123">Voor alleen-lezen toegang tot de portal voor gebruikers met beperkte rechten, moet u lid zijn van de rollengroep **Globale lezer** of **Beveiligingslezer**.</span><span class="sxs-lookup"><span data-stu-id="a566d-123">For read-only access to the Restricted users portal, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="a566d-124">Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a566d-124">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="a566d-125">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a566d-125">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="a566d-126">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a566d-126">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="a566d-127">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="a566d-127">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="a566d-128">Een afzender die de uitgaande e-maillimieten overschrijdt, is een indicator van een verdacht account.</span><span class="sxs-lookup"><span data-stu-id="a566d-128">A sender exceeding the outbound email limits is an indicator of a compromised account.</span></span> <span data-ttu-id="a566d-129">Voordat u de gebruiker verwijdert uit de portal voor gebruikers met beperkte rechten, moet u de vereiste stappen volgen om het beheer van het account te herstellen.</span><span class="sxs-lookup"><span data-stu-id="a566d-129">Before you remove the user from the Restricted users portal, be sure to follow the required steps to regain control of their account.</span></span> <span data-ttu-id="a566d-130">Zie voor meer informatie [Reageren op een verdacht e-mailaccount in Office 365](responding-to-a-compromised-email-account.md).</span><span class="sxs-lookup"><span data-stu-id="a566d-130">For more information, see [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-a-user-from-the-restricted-users-list"></a><span data-ttu-id="a566d-131">Ga naar de Microsoft 365 Defender-portal om een gebruiker te verwijderen uit de lijst met gebruikers met beperkte rechten</span><span class="sxs-lookup"><span data-stu-id="a566d-131">Use the Microsoft 365 Defender portal to remove a user from the Restricted users list</span></span>

1. <span data-ttu-id="a566d-132">Ga in de Microsoft 365 Defender-portal naar **E-mail en samenwerking** > **Controleren** > **Gebruikers met beperkte rechten**.</span><span class="sxs-lookup"><span data-stu-id="a566d-132">In the Microsoft 365 Defender portal, go to **Email & collaboration** > **Review** > **Restricted users**.</span></span>

2. <span data-ttu-id="a566d-133">Zoek en selecteer op de pagina **Gebruikers met beperkte rechten** de gebruiker die u wilt deblokkeren door op de gebruiker te klikken.</span><span class="sxs-lookup"><span data-stu-id="a566d-133">On the **Restricted users** page, find and select the user that you want to unblock by clicking on the user.</span></span>

3. <span data-ttu-id="a566d-134">Klik op de actie **Deblokkeren** die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a566d-134">Click the **Unblock** action that appears.</span></span>

4. <span data-ttu-id="a566d-135">Ga naar de flyout **Gebruiker deblokkeren** die wordt weergegeven, en lees de details over het account met beperkte rechten.</span><span class="sxs-lookup"><span data-stu-id="a566d-135">In the **Unblock user** flyout that appears, read the details about the restricted account.</span></span> <span data-ttu-id="a566d-136">Neem de aanbevelingen door om er zeker van te zijn dat u de juiste acties onderneemt voor het geval dat het account werkelijk is gecompromitteerd.</span><span class="sxs-lookup"><span data-stu-id="a566d-136">You should go through the recommendations to ensure you're taking the proper actions in case the account is compromised.</span></span>

   <span data-ttu-id="a566d-137">Wanneer u klaar bent, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="a566d-137">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="a566d-138">Het volgende scherm biedt aanbevelingen om toekomstige inbreuk te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="a566d-138">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="a566d-139">Het inschakelen van meervoudige verificatie (MFA) en het opnieuw instellen van het wachtwoord zijn een goede verdediging.</span><span class="sxs-lookup"><span data-stu-id="a566d-139">Enabling multi-factor authentication (MFA) and resetting the password are a good defense.</span></span>

   <span data-ttu-id="a566d-140">Wanneer u gereed bent, klikt u op **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="a566d-140">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="a566d-141">Klik op **Ja** ter bevestiging.</span><span class="sxs-lookup"><span data-stu-id="a566d-141">Click **Yes** to confirm the change.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a566d-142">Het kan tot 24 uur duren voordat alle beperkingen voor de gebruiker zijn verwijderd.</span><span class="sxs-lookup"><span data-stu-id="a566d-142">It might take up to 24 hours for all restrictions to be removed from the user.</span></span>

## <a name="verify-the-alert-settings-for-restricted-users"></a><span data-ttu-id="a566d-143">De instellingen voor de waarschuwing voor gebruikers met beperkte toegang verifiëren</span><span class="sxs-lookup"><span data-stu-id="a566d-143">Verify the alert settings for restricted users</span></span>

<span data-ttu-id="a566d-144">In het standaard waarschuwingsbeleid genaamd **Gebruiker beperkt tot het verzenden van e-mail** worden beheerders automatisch gewaarschuwd wanneer gebruikers geblokkeerd zijn bij het verzend van e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="a566d-144">The default alert policy named **User restricted from sending email** will automatically notify admins when users are blocked from sending outbound mail.</span></span> <span data-ttu-id="a566d-145">U kunt deze instellingen controleren en aanvullende gebruikers toevoegen om op de hoogte te stellen.</span><span class="sxs-lookup"><span data-stu-id="a566d-145">You can verify these settings and add additional users to notify.</span></span> <span data-ttu-id="a566d-146">Zie voor meer informatie over waarschuwingsbeleid, [Waarschuwingsbeleid in Microsoft 365](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a566d-146">For more information about alert policies, see [Alert policies in Microsoft 365](../../compliance/alert-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a566d-147">Om meldingen te laten werken, moet zoeken in het auditlogboek zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="a566d-147">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="a566d-148">Voor meer informatie, zie [Auditlogboeken zoeken in- of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="a566d-148">For more information, see [Turn the audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="a566d-149">Ga in de Microsoft 365 Defender-portal naar **E-mail en samenwerking** \> **Beleidsregels** \> **Waarschuwingsbeleid**.</span><span class="sxs-lookup"><span data-stu-id="a566d-149">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Alert policy**.</span></span>

2. <span data-ttu-id="a566d-150">Zoek en selecteer op de pagina **Waarschuwingsbeleid** de waarschuwing met de naam **Gebruiker heeft beperkte rechten voor het verzenden van e-mail**.</span><span class="sxs-lookup"><span data-stu-id="a566d-150">On the **Alert policy** page, find and select the alert named **User restricted from sending email**.</span></span> <span data-ttu-id="a566d-151">U kunt de beleidsregels sorteren op naam of het **zoekvak** gebruiken om het beleid te vinden.</span><span class="sxs-lookup"><span data-stu-id="a566d-151">You can sort the policies by name, or use the **Search box** to find the policy.</span></span>

3. <span data-ttu-id="a566d-152">In de flyout **Gebruiker heeft beperkte rechten voor het verzenden van e-mail** die wordt weergegeven, controleert of configureert u de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="a566d-152">In the **User restricted from sending email** flyout that appears, verify or configure the following settings:</span></span>
   - <span data-ttu-id="a566d-153">**Status**: Controleer of de waarschuwing is ingesteld op ![Wisselknop aan](../../media/scc-toggle-on.png).</span><span class="sxs-lookup"><span data-stu-id="a566d-153">**Status**: Verify the alert is turned on ![Toggle on](../../media/scc-toggle-on.png).</span></span>
   - <span data-ttu-id="a566d-154">**Geadresseerden**: Klik op **Bewerken** en controleer of configureer de volgende instellingen in het snelmenu **Geadresseerden bewerken**:</span><span class="sxs-lookup"><span data-stu-id="a566d-154">**Email recipients**: Click **Edit** and verify or configure the following settings in the **Edit recipients** flyout that appears:</span></span>
     - <span data-ttu-id="a566d-155">**E-mailmeldingen verzenden**: Controleer of dit is ingeschakeld (**Aan**).</span><span class="sxs-lookup"><span data-stu-id="a566d-155">**Send email notifications**: Verify this is selected (**On**).</span></span>
     - <span data-ttu-id="a566d-156">**Geadresseerden**: de standaardwaarde is **HuurderBeheerders** (betekenis, **wereldwijde beheerder** leden).</span><span class="sxs-lookup"><span data-stu-id="a566d-156">**Email recipients**: The default value is **TenantAdmins** (meaning, **Global admin** members).</span></span> <span data-ttu-id="a566d-157">Als u meer geadresseerden wilt toevoegen, klikt u in een leeg gebied van het vak.</span><span class="sxs-lookup"><span data-stu-id="a566d-157">To add more recipients, click in a blank area of the box.</span></span> <span data-ttu-id="a566d-158">Een lijst met geadresseerden wordt weergegeven en u kunt een naam typen om een geadresseerde te filteren en te selecteren.</span><span class="sxs-lookup"><span data-stu-id="a566d-158">A list of recipients will appear, and you can start typing a name to filter and select a recipient.</span></span> <span data-ttu-id="a566d-159">U kunt een bestaande geadresseerde verwijderen uit het vak door te klikken op ![Pictogram verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) naast de naam.</span><span class="sxs-lookup"><span data-stu-id="a566d-159">You can remove an existing recipient from the box by clicking ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to their name.</span></span>
     - <span data-ttu-id="a566d-160">**Dagelijkse meldingslimiet**: de standaardwaarde is **Geen limiet** maar u kunt een limiet selecteren voor het maximum aantal meldingen per dag.</span><span class="sxs-lookup"><span data-stu-id="a566d-160">**Daily notification limit**: The default value is **No limit** but you can select a limit for the maximum number of notifications per day.</span></span>

     <span data-ttu-id="a566d-161">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="a566d-161">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="a566d-162">Wanneer u terug bent de doorlopende informatie **Gebruiker valt onder beperkte verzending van e-mail**, klikt u op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="a566d-162">Back on the **User restricted from sending email** flyout, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a><span data-ttu-id="a566d-163">Exchange Online PowerShell gebruiken om gebruikers weer te geven en te verwijderen uit de lijst met gebruikers met beperkte rechten</span><span class="sxs-lookup"><span data-stu-id="a566d-163">Use Exchange Online PowerShell to view and remove users from the Restricted users list</span></span>

<span data-ttu-id="a566d-164">Voer de volgende opdracht uit om deze lijst weer te geven met gebruikers die geen e-mail kunnen verzenden:</span><span class="sxs-lookup"><span data-stu-id="a566d-164">To view this list of users that are restricted from sending email, run the following command:</span></span>

```powershell
Get-BlockedSenderAddress
```

<span data-ttu-id="a566d-165">Als u meer informatie over een specifieke gebruiker wilt bekijken, vervangt u \<emailaddress\> door het e-mailadres van die gebruiker en voert u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="a566d-165">To view details about a specific user, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="a566d-166">Zie [OntvangAdresGeblokkeerdeVerzender](/powershell/module/exchange/get-blockedsenderaddress) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="a566d-166">For detailed syntax and parameter information, see [Get-BlockedSenderAddress](/powershell/module/exchange/get-blockedsenderaddress).</span></span>

<span data-ttu-id="a566d-167">Als u een gebruiker wilt verwijderen uit de lijst met gebruikers met beperkte rechten, vervangt u \<emailaddress\> door het e-mailadres van die gebruiker en voert u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="a566d-167">To remove a user from the Restricted users list, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="a566d-168">Zie [VerwijderAdresGeblokkeerdeVerzender](/powershell/module/exchange/remove-blockedsenderaddress) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="a566d-168">For detailed syntax and parameter information, see [Remove-BlockedSenderAddress](/powershell/module/exchange/remove-blockedsenderaddress).</span></span>
