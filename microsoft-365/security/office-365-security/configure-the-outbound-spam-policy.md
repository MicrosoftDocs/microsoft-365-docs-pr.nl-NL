---
title: Filteren van uitgaande spam configureren
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen informatie lezen over het weergeven, maken, wijzigen en verwijderen van beleid voor uitgaande spam in Exchange Online Protection (EOP).
ms.openlocfilehash: 792cd44d1571c407477671c6223b8ec38ad9b7f8
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572835"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="ed980-103">Uitgaande spamfilters configureren in EOP</span><span class="sxs-lookup"><span data-stu-id="ed980-103">Configure outbound spam filtering in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="ed980-104">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken worden uitgaande e-mailberichten die zijn verzonden via EOP, automatisch gecontroleerd op spam en ongebruikelijk verzenden.</span><span class="sxs-lookup"><span data-stu-id="ed980-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="ed980-105">Uitgaande spam van een gebruiker in uw organisatie geeft meestal een niet-gemanipuleerd account aan.</span><span class="sxs-lookup"><span data-stu-id="ed980-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="ed980-106">Verdachte uitgaande berichten worden gemarkeerd als spam (ongeacht het spam betrouwbaarheidsniveau of SCL) en worden gerouteerd via de groep voor [hoog risico](high-risk-delivery-pool-for-outbound-messages.md) om de reputatie van de service te helpen beschermen (dat wil zeggen dat u de e-mailservers van microsoft 365-bron uit de lijst met IP-blokken houdt).</span><span class="sxs-lookup"><span data-stu-id="ed980-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="ed980-107">Beheerders ontvangen automatisch een melding voor verdachte uitgaande e-mail activiteit en geblokkeerde gebruikers via een [waarschuwings beleid](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ed980-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="ed980-108">EOP maakt gebruik van een beleid voor uitgaande spam als onderdeel van de algemene verdediging van uw organisatie tegen spam.</span><span class="sxs-lookup"><span data-stu-id="ed980-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="ed980-109">Zie [Bescherming tegen antispam](anti-spam-protection.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ed980-109">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="ed980-110">Beheerders kunnen het standaard uitgaande spam beleid bekijken, bewerken en configureren (maar niet verwijderen).</span><span class="sxs-lookup"><span data-stu-id="ed980-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="ed980-111">Voor een grotere nauwkeurigheid kunt u ook een aangepast beleid voor uitgaande spam maken dat geldt voor specifieke gebruikers, groepen of domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ed980-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="ed980-112">Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.</span><span class="sxs-lookup"><span data-stu-id="ed980-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="ed980-113">U kunt uitgaande spam beleidsregels configureren in het beveiligings & nalevings centrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder postvakken van Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="ed980-113">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="ed980-114">De basiselementen van een uitgaand spam beleid in EOP zijn:</span><span class="sxs-lookup"><span data-stu-id="ed980-114">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="ed980-115">**Het beleid voor uitgaande spamfilters**: Hiermee wordt de actie opgegeven voor uitgaande spam filtering Verdicts en de Meldingsopties.</span><span class="sxs-lookup"><span data-stu-id="ed980-115">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="ed980-116">Met **de regel voor uitgaande spam filtering**: geeft u de prioriteit op van de filters voor een uitgaand spamfilter (waarvoor het beleid van toepassing is).</span><span class="sxs-lookup"><span data-stu-id="ed980-116">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="ed980-117">Het verschil tussen deze twee elementen is niet duidelijk wanneer u uitgaande spam policies beheert in de beveiligings & nalevings centrum:</span><span class="sxs-lookup"><span data-stu-id="ed980-117">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="ed980-118">Wanneer u een beleid maakt, maakt u eigenlijk een uitgaande spamfilter regel en het bijbehorende uitgaande spamfilter beleid tegelijk met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="ed980-118">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="ed980-119">Wanneer u een beleid wijzigt, worden de instellingen voor de regels naam, prioriteit, ingeschakeld of uitgeschakeld en de filters voor uitgaande spamfilters gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="ed980-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="ed980-120">Alle andere instellingen wijzigen het bijbehorende uitgaande spamfilter beleid.</span><span class="sxs-lookup"><span data-stu-id="ed980-120">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="ed980-121">Wanneer u een beleid verwijdert, worden de regels uitgaande spamfilter en het bijbehorende uitgaande spamfilter verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ed980-121">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="ed980-122">In Exchange Online PowerShell of standalone EOP PowerShell beheert u het beleid en de regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="ed980-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="ed980-123">Zie voor meer informatie de sectie [Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken om uitgaande spam beleidsregels](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) verderop in dit onderwerp te configureren.</span><span class="sxs-lookup"><span data-stu-id="ed980-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this topic.</span></span>

<span data-ttu-id="ed980-124">Elke organisatie heeft een ingebouwd spam beleid met de naam standaard met de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="ed980-124">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="ed980-125">Het beleid wordt toegepast op alle geadresseerden in de organisatie, ook al is er geen uitgaande spamfilter regel (Recipient filters) gekoppeld aan het beleid.</span><span class="sxs-lookup"><span data-stu-id="ed980-125">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="ed980-126">Het beleid heeft de prioriteit **Laagste** die u niet kunt wijzigen (het beleid wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="ed980-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="ed980-127">Alle beleid dat u maakt heeft altijd een hogere prioriteit dan het beleid met de naam Standaard.</span><span class="sxs-lookup"><span data-stu-id="ed980-127">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="ed980-128">Het beleid is het standaardbeleid (de eigenschap **IsDefault** heeft de waarde `True`) en u kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="ed980-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="ed980-129">Als u de efficiëntie van uitgaande spamfilters wilt verbeteren, kunt u een aangepast beleid voor uitgaande spam maken met strikte instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="ed980-129">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ed980-130">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="ed980-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ed980-131">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="ed980-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ed980-132">Gebruik <https://protection.office.com/antispam> om direct naar de pagina **Antispaminstellingen** te gaan.</span><span class="sxs-lookup"><span data-stu-id="ed980-132">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="ed980-133">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed980-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="ed980-134">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed980-134">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ed980-135">Voordat u de procedures in dit artikel kunt uitvoeren, moet u beschikken over machtigingen voor beveiliging & nalevings centrum.</span><span class="sxs-lookup"><span data-stu-id="ed980-135">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="ed980-136">Als u een beleid voor uitgaande spam wilt toevoegen, wijzigen of verwijderen, moet u lid zijn van de rollen groepen **Organisatiebeheer** of **beveiligingsbeheerder** .</span><span class="sxs-lookup"><span data-stu-id="ed980-136">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="ed980-137">Voor alleen-lezen toegang tot een uitgaand spam beleid moet u lid zijn van de rollen groepen **algemene lezer** of **beveiligings lezer** .</span><span class="sxs-lookup"><span data-stu-id="ed980-137">For read-only access to outbound spam policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="ed980-138">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ed980-138">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="ed980-139">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="ed980-139">**Notes**:</span></span>

  - <span data-ttu-id="ed980-140">Door gebruikers toe te voegen aan de bijbehorende rol van Azure Active Directory in het Microsoft 365-Beheercentrum geeft u gebruikers de vereiste machtigingen in het beveiligings & nalevings centrum _en_ machtigingen voor andere functies in microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ed980-140">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ed980-141">Raadpleeg [Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ed980-141">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="ed980-142">De functiegroep **alleen weergeven voor Organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) biedt ook alleen-lezen toegang tot de functie.</span><span class="sxs-lookup"><span data-stu-id="ed980-142">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="ed980-143">Voor de aanbevolen instellingen voor het beleid voor uitgaande spam, raadpleegt u [beleidsinstellingen voor uitgaande spamfilters EOP](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="ed980-143">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="ed980-144">De standaard [Waarschuwingsregels](../../compliance/alert-policies.md) met de naam **e-mail limieten** voor het verzenden van e-mail zijn **verdacht en verdachte patronen** voor het verzenden van e-mail, en **gebruikers die geen e-mail verzenden** , ontvangen al e-mail meldingen naar leden van de **TenantAdmins** (**algemene beheerders**) voor ongebruikelijke uitgaande e-mail activiteit en geblokkeerde gebruikers vanwege uitgaande spam.</span><span class="sxs-lookup"><span data-stu-id="ed980-144">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="ed980-145">Zie voor meer informatie [de instellingen voor meldingen voor gebruikers met beperkte toegang](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="ed980-145">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="ed980-146">We raden u aan dit waarschuwings beleid te gebruiken in plaats van de Meldingsopties in het beleid voor uitgaande spam.</span><span class="sxs-lookup"><span data-stu-id="ed980-146">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="ed980-147">Het nalevings centrum voor beveiliging & gebruiken om uitgaande spam beleidsregels te maken</span><span class="sxs-lookup"><span data-stu-id="ed980-147">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="ed980-148">Als u een aangepast beleid voor uitgaande spam maakt in de beveiligings & nalevings centrum, worden de regels voor spamfilter en het bijbehorende spamfilter beleid tegelijk gemaakt met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="ed980-148">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="ed980-149">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="ed980-149">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="ed980-150">Klik op de pagina **anti spam instellingen** op **Maak een uitgaand beleid**.</span><span class="sxs-lookup"><span data-stu-id="ed980-150">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="ed980-151">Configureer de volgende instellingen in het **filter beleid uitgaande spam** dat wordt geopend:</span><span class="sxs-lookup"><span data-stu-id="ed980-151">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="ed980-152">**Naam**: een unieke beschrijvende naam voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="ed980-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="ed980-153">**Beschrijving**: voer een optionele beschrijving in voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="ed980-153">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="ed980-154">Option Vouw de sectie **meldingen** uit om extra gebruikers weer te geven die kopieën en meldingen van verdachte uitgaande e-mailberichten moeten ontvangen:</span><span class="sxs-lookup"><span data-stu-id="ed980-154">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="ed980-155">**Een kopie van verdachte uitgaande e-mailberichten naar specifieke personen verzenden: met** deze instelling worden de opgegeven gebruikers toegevoegd als BCC-geadresseerden voor de verdachte uitgaande berichten.</span><span class="sxs-lookup"><span data-stu-id="ed980-155">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span>

     > [!NOTE]
     > <span data-ttu-id="ed980-156">Deze instelling werkt alleen met het standaardbeleid voor uitgaande spam.</span><span class="sxs-lookup"><span data-stu-id="ed980-156">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="ed980-157">Het werkt niet in een aangepast uitgaand spam beleid dat u maakt.</span><span class="sxs-lookup"><span data-stu-id="ed980-157">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="ed980-158">U schakelt deze instelling als volgt in:</span><span class="sxs-lookup"><span data-stu-id="ed980-158">To enable this setting:</span></span>

     1. <span data-ttu-id="ed980-159">Schakel het selectievakje in om de instelling in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="ed980-159">Select the check box to enable the setting.</span></span>

     1. <span data-ttu-id="ed980-160">Klik op **personen toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="ed980-160">Click **Add people**.</span></span> <span data-ttu-id="ed980-161">In het flyout voor **geadresseerden toevoegen of verwijderen** dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="ed980-161">In the **Add or remove recipients** flyout that appears:</span></span>

     1. <span data-ttu-id="ed980-162">Voert u het e-mailadres van de afzender in.</span><span class="sxs-lookup"><span data-stu-id="ed980-162">Enter the sender's email address.</span></span> <span data-ttu-id="ed980-163">U kunt meerdere e-mailadressen opgeven, gescheiden door puntkomma's (;) of één geadresseerde per regel.</span><span class="sxs-lookup"><span data-stu-id="ed980-163">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     1. <span data-ttu-id="ed980-164">Klikt u op</span><span class="sxs-lookup"><span data-stu-id="ed980-164">Click</span></span> ![Pictogram toevoegen](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="ed980-166">geadresseerden toevoegen.</span><span class="sxs-lookup"><span data-stu-id="ed980-166">to add the recipients.</span></span>

        <span data-ttu-id="ed980-167">Herhaal deze stappen zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="ed980-167">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="ed980-168">De geadresseerden die u hebt toegevoegd, worden weergegeven in de sectie **lijst met geadresseerden** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="ed980-168">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="ed980-169">Als u een geadresseerde wilt verwijderen, klikt u op de ![ knop verwijderen ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="ed980-169">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     1. <span data-ttu-id="ed980-170">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="ed980-170">When you're finished, click **Save**.</span></span>

        <span data-ttu-id="ed980-171">Als u deze instelling wilt uitschakelen, schakelt u het selectievakje uit.</span><span class="sxs-lookup"><span data-stu-id="ed980-171">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="ed980-172">**Specifieke personen op de hoogte stellen wanneer een afzender wordt geblokkeerd vanwege het verzenden van uitgaande spam**:</span><span class="sxs-lookup"><span data-stu-id="ed980-172">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="ed980-173">Deze instelling wordt afgeschaft van uitgaande spam beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="ed980-173">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="ed980-174">In het standaard [waarschuwings beleid](../../compliance/alert-policies.md) wordt de naam gebruiker voor het **verzenden van e-mail** al e-mail meldingen verzonden naar leden van de **TenantAdmins** (**algemene beheerders**) wanneer gebruikers worden geblokkeerd omdat ze de limieten voor de sectie **limieten** van de ontvanger overschrijden.</span><span class="sxs-lookup"><span data-stu-id="ed980-174">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="ed980-175">**U wordt ten zeerste aangeraden het waarschuwings beleid te gebruiken in plaats van deze instelling in het beleid voor uitgaande spam om beheerders en andere gebruikers op de hoogte te stellen**.</span><span class="sxs-lookup"><span data-stu-id="ed980-175">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users**.</span></span> <span data-ttu-id="ed980-176">Zie [de instellingen voor meldingen voor gebruikers met beperkte toegang controleren](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="ed980-176">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

5. <span data-ttu-id="ed980-177">Option Vouw de sectie **limieten voor geadresseerden** uit om de limieten en acties voor verdachte uitgaande e-mailberichten te configureren:</span><span class="sxs-lookup"><span data-stu-id="ed980-177">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="ed980-178">Deze instellingen zijn alleen van toepassing op postvakken op basis van de Cloud.</span><span class="sxs-lookup"><span data-stu-id="ed980-178">These settings are only applicable to cloud-based mailboxes.</span></span>

   - <span data-ttu-id="ed980-179">**Maximum aantal geadresseerden per gebruiker**</span><span class="sxs-lookup"><span data-stu-id="ed980-179">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="ed980-180">Een geldige waarde is 0 tot 10000.</span><span class="sxs-lookup"><span data-stu-id="ed980-180">A valid value is 0 to 10000.</span></span> <span data-ttu-id="ed980-181">De standaardwaarde is 0, wat betekent dat de service-standaardwaarden worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ed980-181">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="ed980-182">Zie [limieten verzenden](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ed980-182">For more information, see [Sending limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

     - <span data-ttu-id="ed980-183">**Extern uurtarief**: het maximale aantal externe geadresseerden per uur.</span><span class="sxs-lookup"><span data-stu-id="ed980-183">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="ed980-184">**Interne limiet voor het hele uur**: het maximale aantal interne geadresseerden per uur.</span><span class="sxs-lookup"><span data-stu-id="ed980-184">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="ed980-185">**Dagelijkse limiet**: het maximale aantal geadresseerden per dag.</span><span class="sxs-lookup"><span data-stu-id="ed980-185">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="ed980-186">**Actie wanneer een gebruiker de limieten overschrijdt**: Configureer de actie die moet worden uitgevoerd wanneer een van de **limieten** van de ontvanger wordt overschreden.</span><span class="sxs-lookup"><span data-stu-id="ed980-186">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="ed980-187">Voor alle acties zijn de geadresseerden opgegeven in de gebruikers die het beleid voor het **verzenden van e-mail waarschuwingen niet verzenden** (en in de nu overbodige **specifieke personen op de hoogte gesteld als een afzender wordt geblokkeerd vanwege het verzenden van uitgaande** spam-instelling in het uitgaande spam beleid van e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="ed980-187">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="ed980-188">**Zorgen dat de gebruiker geen e-mail meer kan verzenden voor de volgende dag**: dit is de standaardwaarde.</span><span class="sxs-lookup"><span data-stu-id="ed980-188">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="ed980-189">Er worden e-mail meldingen verzonden, en de gebruiker kan geen berichten meer naar de volgende dag verzenden, op basis van UTC-tijd.</span><span class="sxs-lookup"><span data-stu-id="ed980-189">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="ed980-190">Het is niet mogelijk dat de beheerder dit blok kan overschrijven.</span><span class="sxs-lookup"><span data-stu-id="ed980-190">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="ed980-191">De melding met de naam **gebruiker beperkt vanwege het verzenden van e-mail** (via e-mail en op de pagina **waarschuwingen weergeven** ).</span><span class="sxs-lookup"><span data-stu-id="ed980-191">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="ed980-192">Geadresseerden die zijn opgegeven in het **bericht specifieke personen op de hoogte brengen van een afzender die wordt geblokkeerd vanwege het verzenden van uitgaande spam** instelling in het beleid, worden eveneens gewaarschuwd.</span><span class="sxs-lookup"><span data-stu-id="ed980-192">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="ed980-193">De gebruiker kan geen berichten meer naar de volgende dag verzenden, op basis van UTC-tijd.</span><span class="sxs-lookup"><span data-stu-id="ed980-193">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="ed980-194">Het is niet mogelijk dat de beheerder dit blok kan overschrijven.</span><span class="sxs-lookup"><span data-stu-id="ed980-194">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="ed980-195">Voor **komen dat de gebruiker e-mail verzendt**: e-mail meldingen worden verzonden naar de portal **[beperkte gebruikers] <https://sip.protection.office.com/restrictedusers>** in het beveiligings & nalevings centrum en de gebruiker kan geen e-mail verzenden totdat deze wordt verwijderd uit de portal met **beperkte gebruikers** door een beheerder. Nadat een beheerder de gebruiker uit de lijst heeft verwijderd, wordt de gebruiker niet meer voor die dag beperkt.</span><span class="sxs-lookup"><span data-stu-id="ed980-195">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="ed980-196">Zie [een gebruiker verwijderen uit de portal met beperkte gebruikers na het verzenden van spamberichten](removing-user-from-restricted-users-portal-after-spam.md)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="ed980-196">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="ed980-197">**Geen actie, alleen waarschuwingen**: e-mail meldingen worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="ed980-197">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="ed980-198">Option Vouw **automatisch doorsturen** uit om het automatisch doorsturen van e-mail door gebruikers naar externe afzenders te regelen.</span><span class="sxs-lookup"><span data-stu-id="ed980-198">(Optional) Expand **Automatic forwarding** section to control automatic email forwarding by users to external senders.</span></span> <span data-ttu-id="ed980-199">Zie [doorsturen van E-mail configureren](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding)voor meer informatie over automatisch doorsturen.</span><span class="sxs-lookup"><span data-stu-id="ed980-199">For more information about automatic forwarding, see [Configure email forwarding](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="ed980-200">Vóór september 2020 zijn deze instellingen beschikbaar, maar worden deze niet afgedwongen.</span><span class="sxs-lookup"><span data-stu-id="ed980-200">Before September 2020, these settings are available but not enforced.</span></span>
   >
   > - <span data-ttu-id="ed980-201">Deze instellingen zijn alleen van toepassing op postvakken op basis van de Cloud.</span><span class="sxs-lookup"><span data-stu-id="ed980-201">These settings apply only to cloud-based mailboxes.</span></span>
   >
   > - <span data-ttu-id="ed980-202">Wanneer automatisch doorsturen is uitgeschakeld, ontvangt de ontvanger een rapport over niet-uitgevoerde bezorging (ook wel een NDR genoemd of bericht over een NDR) als externe afzenders een e-mail verzenden naar een postvak waarop het doorsturen is geplaatst.</span><span class="sxs-lookup"><span data-stu-id="ed980-202">When automatic forwarding is disabled, the recipient will receive a non-delivery report (also known as an NDR or bounce message) if external senders send email to a mailbox that has forwarding in place.</span></span> <span data-ttu-id="ed980-203">Als het e-mailbericht door een interne afzender wordt verzonden, krijgt de afzender de NDR.</span><span class="sxs-lookup"><span data-stu-id="ed980-203">If the email is sent by an internal sender, the sender will get the NDR.</span></span>

   <span data-ttu-id="ed980-204">De beschikbare waarden zijn:</span><span class="sxs-lookup"><span data-stu-id="ed980-204">The available values are:</span></span>

   - <span data-ttu-id="ed980-205">**Automatisch-door het systeem beheerde** functies: uitgaande spamfilters voor het beheren van automatisch externe e-mail doorsturen.</span><span class="sxs-lookup"><span data-stu-id="ed980-205">**Automatic - System-controlled**: Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="ed980-206">Dit is de standaardwaarde.</span><span class="sxs-lookup"><span data-stu-id="ed980-206">This is the default value.</span></span>
   - <span data-ttu-id="ed980-207">**Ingeschakeld**: automatisch extern doorsturen van e-mail wordt niet uitgeschakeld door het beleid.</span><span class="sxs-lookup"><span data-stu-id="ed980-207">**On**: Automatic external email forwarding is not disabled by the policy.</span></span>
   - <span data-ttu-id="ed980-208">**Uit**: alle automatische doorsturen van e-mail is uitgeschakeld door het beleid.</span><span class="sxs-lookup"><span data-stu-id="ed980-208">**Off**: All automatic external email forwarding is disabled by the policy.</span></span>
 
7. <span data-ttu-id="ed980-209">Opgestart Vouw de sectie **toegepast op** uit om de interne afzenders op te geven waarop het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="ed980-209">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="ed980-210">U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering.</span><span class="sxs-lookup"><span data-stu-id="ed980-210">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="ed980-211">Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<sender1\>_ of _\<sender2\>_).</span><span class="sxs-lookup"><span data-stu-id="ed980-211">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="ed980-212">Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<sender1\>_ en _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="ed980-212">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="ed980-213">Het eenvoudigste is drie keer te klikken op **Een voorwaarde toevoegen** om alle beschikbare voorwaarden weer te geven.</span><span class="sxs-lookup"><span data-stu-id="ed980-213">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="ed980-214">U kunt op de ![knop Verwijderen](../../media/scc-remove-icon.png) klikken om voorwaarden te verwijderen die u niet wilt configureren.</span><span class="sxs-lookup"><span data-stu-id="ed980-214">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="ed980-215">**Het domein van de afzender is**: verwijst naar afzenders in een of meer van de geconfigureerde domeinen in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="ed980-215">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in the organization.</span></span> <span data-ttu-id="ed980-216">Klik in het vak **Een tag toevoegen** om een domein weer te geven en te selecteren.</span><span class="sxs-lookup"><span data-stu-id="ed980-216">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="ed980-217">Klik opnieuw op het vak **Een tag toevoegen** om aanvullende domeinen te selecteren als er meer dan één domein beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="ed980-217">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="ed980-218">**Afzender is**: geeft een of meer gebruikers in uw organisatie aan.</span><span class="sxs-lookup"><span data-stu-id="ed980-218">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="ed980-219">Klik in het vak **Tag toevoegen** en begin te typen om de lijst te filteren.</span><span class="sxs-lookup"><span data-stu-id="ed980-219">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="ed980-220">Klik opnieuw op het vak **een tag toevoegen** om extra afzenders te selecteren.</span><span class="sxs-lookup"><span data-stu-id="ed980-220">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="ed980-221">**Afzender is een lid van**: geeft een of meer groepen op in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ed980-221">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="ed980-222">Klik in het vak **Tag toevoegen** en begin te typen om de lijst te filteren.</span><span class="sxs-lookup"><span data-stu-id="ed980-222">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="ed980-223">Klik opnieuw op het vak **een tag toevoegen** om extra afzenders te selecteren.</span><span class="sxs-lookup"><span data-stu-id="ed980-223">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="ed980-224">**Behalve als**: om uitzonderingen op de regel toe te voegen, klikt u drie keer op **Een voorwaarde toevoegen** om alle beschikbare uitzonderingen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="ed980-224">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="ed980-225">De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="ed980-225">The settings and behavior are exactly like the conditions.</span></span>

8. <span data-ttu-id="ed980-226">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="ed980-226">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="ed980-227">Het beleid voor uitgaand spam weergeven met behulp van beveiligings &</span><span class="sxs-lookup"><span data-stu-id="ed980-227">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="ed980-228">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="ed980-228">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="ed980-229">Op de pagina **anti spam instellingen** klikt u op ![ pictogram uitvouwen ](../../media/scc-expand-icon.png) om een uitgaand spam beleid uit te vouwen:</span><span class="sxs-lookup"><span data-stu-id="ed980-229">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="ed980-230">Het standaardbeleid met de naam **uitgaand spamfilter beleid**.</span><span class="sxs-lookup"><span data-stu-id="ed980-230">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="ed980-231">Een aangepast beleid dat u hebt gemaakt en waarvan de waarde in de kolom **type** een **aangepast uitgaand spam beleid** is.</span><span class="sxs-lookup"><span data-stu-id="ed980-231">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="ed980-232">De beleidsinstellingen worden weergegeven in de uitgebreide beleidsdetails die worden weergegeven, of u kunt op **beleid bewerken** klikken.</span><span class="sxs-lookup"><span data-stu-id="ed980-232">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="ed980-233">Het beleid voor de naleving van beveiligings & gebruiken om uitgaande spam beleidsregels te wijzigen</span><span class="sxs-lookup"><span data-stu-id="ed980-233">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="ed980-234">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="ed980-234">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="ed980-235">Op de pagina **anti spam instellingen** klikt u op ![ pictogram uitvouwen ](../../media/scc-expand-icon.png) om een uitgaand spam beleid uit te vouwen:</span><span class="sxs-lookup"><span data-stu-id="ed980-235">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="ed980-236">Het standaardbeleid met de naam **uitgaand spamfilter beleid**.</span><span class="sxs-lookup"><span data-stu-id="ed980-236">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="ed980-237">Een aangepast beleid dat u hebt gemaakt en waarvan de waarde in de kolom **type** een **aangepast uitgaand spam beleid** is.</span><span class="sxs-lookup"><span data-stu-id="ed980-237">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="ed980-238">Klik op **Beleid bewerken**.</span><span class="sxs-lookup"><span data-stu-id="ed980-238">Click **Edit policy**.</span></span>

<span data-ttu-id="ed980-239">Voor een aangepast uitgaand spam beleid zijn de beschikbare instellingen in de vervolgmenu die worden weergegeven, identiek aan de instellingen die worden beschreven in de sectie [het hulpmiddel beveiligings & gebruiken om uitgaande spam beleidsregels te maken](#use-the-security--compliance-center-to-create-outbound-spam-policies) .</span><span class="sxs-lookup"><span data-stu-id="ed980-239">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="ed980-240">Voor het standaardbeleid voor uitgaande spam met de naam **uitgaand spamfilter beleid** is de sectie **toegepast op** niet beschikbaar (het beleid geldt voor iedereen) en kunt u de naam van het beleid niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="ed980-240">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="ed980-241">Zie de volgende secties om beleid in- of uit te schakelen, de prioriteit van beleid te wijzigen of de quarantaine-meldingen van eindgebruiker configureren.</span><span class="sxs-lookup"><span data-stu-id="ed980-241">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="ed980-242">Beleid voor uitgaande spam in-of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="ed980-242">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="ed980-243">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="ed980-243">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="ed980-244">Op de pagina **anti spam instellingen** klikt u op ![ pictogram uitvouwen ](../../media/scc-expand-icon.png) om een aangepast beleid dat u hebt gemaakt, uit te vouwen (de waarde in de kolom **type** is **aangepast beleid voor uitgaande spam**).</span><span class="sxs-lookup"><span data-stu-id="ed980-244">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="ed980-245">Let op de waarde in de kolom **Aan** in de uitgebreide beleidsgegevens die worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ed980-245">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="ed980-246">Verplaats te wisselknop naar links om het beleid uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="ed980-246">Move the toggle to the left to disable the policy:</span></span> ![Uitschakelen](../../media/scc-toggle-off.png)

   <span data-ttu-id="ed980-248">Verplaats te wisselknop naar rechts om het beleid in te schakelen:</span><span class="sxs-lookup"><span data-stu-id="ed980-248">Move the toggle to the right to enable the policy:</span></span> ![Inschakelen](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="ed980-250">U kunt het standaardbeleid voor uitgaande spam niet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="ed980-250">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="ed980-251">De prioriteit voor aangepaste spam beleidsregels instellen</span><span class="sxs-lookup"><span data-stu-id="ed980-251">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="ed980-252">Beleidsregels voor uitgaande spam krijgen standaard een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwe policies zijn een lagere prioriteit dan oudere beleidsregels).</span><span class="sxs-lookup"><span data-stu-id="ed980-252">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="ed980-253">Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit).</span><span class="sxs-lookup"><span data-stu-id="ed980-253">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="ed980-254">Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.</span><span class="sxs-lookup"><span data-stu-id="ed980-254">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="ed980-255">Het aangepaste beleid voor uitgaande spam wordt weergegeven in de volgorde waarin ze zijn verwerkt ( **het eerste** beleid heeft de waarde 0).</span><span class="sxs-lookup"><span data-stu-id="ed980-255">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="ed980-256">Het uitgaande spam beleid met de naam **uitgaand spamfilter beleid** heeft de prioriteitswaarde **laag** en u kunt deze niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="ed980-256">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="ed980-257">Om de prioriteit van beleid te wijzigen, kunt u het beleid naar boven of beneden verplaatsen in de lijst (u kunt het **Prioriteit** snummer in het Beveiligings en compliancecentrum niet rechtstreeks wijzigen).</span><span class="sxs-lookup"><span data-stu-id="ed980-257">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="ed980-258">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="ed980-258">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="ed980-259">Zoek op de pagina **anti spam instellingen** de beleidsregels waarvan de waarde in de kolom **type** een **aangepast uitgaand spam beleid** is.</span><span class="sxs-lookup"><span data-stu-id="ed980-259">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="ed980-260">Let op de waarden in de kolom **Prioriteit**:</span><span class="sxs-lookup"><span data-stu-id="ed980-260">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="ed980-261">Het aangepaste beleid voor uitgaande spam met de hoogste prioriteit heeft een ![ pijl-omlaag ](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span><span class="sxs-lookup"><span data-stu-id="ed980-261">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="ed980-262">Het aangepaste beleid voor uitgaande spam met de laagste prioriteit heeft het ![ pijlpictogram omhoog ](../../media/ITPro-EAC-UpArrowIcon.png) **n** (bijvoorbeeld pijl- ![ omhoog ](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span><span class="sxs-lookup"><span data-stu-id="ed980-262">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="ed980-263">Als u een aangepast uitgaand spam beleid hebt, hebben de beleidsregels tussen de hoogste en de laagste prioriteit een pijl ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ -omlaag ](../../media/ITPro-EAC-DownArrowIcon.png) **n** ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **2** en pijl-omlaag-pictogram omhoog</span><span class="sxs-lookup"><span data-stu-id="ed980-263">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="ed980-264">Klik op</span><span class="sxs-lookup"><span data-stu-id="ed980-264">Click</span></span> ![het pictogram pijl-omhoog](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="ed980-266">of</span><span class="sxs-lookup"><span data-stu-id="ed980-266">or</span></span> ![het pictogram pijl-omlaag](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="ed980-268">Als u het aangepaste uitgaande spam beleid omhoog of omlaag wilt verplaatsen in de lijst prioriteit.</span><span class="sxs-lookup"><span data-stu-id="ed980-268">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="ed980-269">Het nalevings centrum voor beveiligings & gebruiken om beleid voor uitgaande spam te verwijderen</span><span class="sxs-lookup"><span data-stu-id="ed980-269">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="ed980-270">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="ed980-270">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="ed980-271">Op de pagina **anti spam instellingen** klikt u op ![ pictogram uitvouwen ](../../media/scc-expand-icon.png) om het aangepaste beleid uit te vouwen dat u wilt verwijderen (de kolom **type** is **aangepast beleid voor uitgaande spam**).</span><span class="sxs-lookup"><span data-stu-id="ed980-271">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="ed980-272">Klik in de uitgebreide beleidsgegevens op **Beleid verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="ed980-272">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="ed980-273">Klik op **Ja** in het waarschuwingsvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ed980-273">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="ed980-274">U kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="ed980-274">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="ed980-275">Uitgaande spam beleidsregels met Exchange Online PowerShell of zelfstandige EOP PowerShell configureren</span><span class="sxs-lookup"><span data-stu-id="ed980-275">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id="ed980-276">Zoals hierboven is beschreven, bestaat een uitgaand spamfilter beleid en een uitgaande spamfilter regel.</span><span class="sxs-lookup"><span data-stu-id="ed980-276">As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id="ed980-277">In Exchange Online PowerShell of zelfstandige EOP PowerShell wordt het verschil tussen het uitgaande spamfilter beleid en de regels voor uitgaande spam filteren duidelijk.</span><span class="sxs-lookup"><span data-stu-id="ed980-277">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="ed980-278">U beheert uitgaand spamfilter beleid met behulp van de cmdlets van **\* HostedOutboundSpamFilterPolicy** en u beheert de regels voor uitgaande spamfilter met behulp van de cmdlets van **\* HostedOutboundSpamFilterRule** .</span><span class="sxs-lookup"><span data-stu-id="ed980-278">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="ed980-279">In PowerShell maakt u eerst een uitgaand spamfilter beleid, en vervolgens maakt u de uitgaande spamfilter regel waarmee het beleid wordt aangegeven waarop de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="ed980-279">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="ed980-280">In PowerShell wijzigt u de instellingen in het filter beleid uitgaande spam en de regel voor uitgaande spam afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="ed980-280">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id="ed980-281">Wanneer u een uitgaand spamfilter beleid uit PowerShell verwijdert, wordt de bijbehorende regel voor uitgaande spamfilters niet automatisch verwijderd en omgekeerd.</span><span class="sxs-lookup"><span data-stu-id="ed980-281">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="ed980-282">PowerShell gebruiken om uitgaande spam beleidsregels te maken</span><span class="sxs-lookup"><span data-stu-id="ed980-282">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="ed980-283">Het maken van een beleid voor uitgaande spam in PowerShell is een procedure die bestaat uit twee stappen:</span><span class="sxs-lookup"><span data-stu-id="ed980-283">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="ed980-284">Het beleid voor uitgaande spamfilters maken.</span><span class="sxs-lookup"><span data-stu-id="ed980-284">Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id="ed980-285">Maak de uitgaande spamfilter regel waarmee u het uitgaande spamfilter beleid opgeeft waarop de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="ed980-285">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="ed980-286">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="ed980-286">**Notes**:</span></span>

- <span data-ttu-id="ed980-287">U kunt een nieuwe regel voor uitgaande spamfilters maken en een bestaand, niet-gekoppeld uitgaand spamfilter beleid toewijzen.</span><span class="sxs-lookup"><span data-stu-id="ed980-287">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="ed980-288">Uitgaande spamfilter regels kunnen niet worden gekoppeld aan meer dan één uitgaand spamfilter beleid.</span><span class="sxs-lookup"><span data-stu-id="ed980-288">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="ed980-289">U kunt de volgende instellingen configureren voor nieuwe beleidsregels voor uitgaande spam in PowerShell die niet beschikbaar zijn in het beveiligings & nalevings centrum totdat u het beleid hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="ed980-289">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="ed980-290">Het nieuwe beleid maken als uitgeschakeld (_ingeschakeld_ `$false` in de **nieuwe HostedOutboundSpamFilterRule-** cmdlet).</span><span class="sxs-lookup"><span data-stu-id="ed980-290">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
  - <span data-ttu-id="ed980-291">De prioriteit van het beleid instellen voor het maken _Priority_ van de _\<Number\>_ **nieuwe HostedOutboundSpamFilterRule-** cmdlet (prioriteit).</span><span class="sxs-lookup"><span data-stu-id="ed980-291">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="ed980-292">Een nieuw beleid voor het uitgaande spamfilter dat u in PowerShell maakt, is niet zichtbaar in het beveiligings & nalevings centrum tot u het beleid aan een spamfilter regel toewijst.</span><span class="sxs-lookup"><span data-stu-id="ed980-292">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="ed980-293">Stap 1: PowerShell gebruiken om een uitgaand spamfilter beleid te maken</span><span class="sxs-lookup"><span data-stu-id="ed980-293">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="ed980-294">U kunt als volgt een uitgaand spamfilter beleid maken:</span><span class="sxs-lookup"><span data-stu-id="ed980-294">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="ed980-295">In dit voorbeeld wordt een nieuw beleid voor uitgaande spam met de naam contoso-leidinggevenden gemaakt met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="ed980-295">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="ed980-296">De limieten voor de snelheid van de ontvanger zijn beperkt tot kleinere waarden, namelijk de standaardwaarden.</span><span class="sxs-lookup"><span data-stu-id="ed980-296">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="ed980-297">Zie limieten voor het [verzenden van alle opties in Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ed980-297">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="ed980-298">Wanneer een van de limieten is bereikt, kan de gebruiker geen berichten verzenden.</span><span class="sxs-lookup"><span data-stu-id="ed980-298">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="ed980-299">Zie [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="ed980-299">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="ed980-300">Stap 2: PowerShell gebruiken om een uitgaande spamfilter regel te maken</span><span class="sxs-lookup"><span data-stu-id="ed980-300">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="ed980-301">Als u een uitgaande spamfilter regel wilt maken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="ed980-301">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="ed980-302">In dit voorbeeld wordt een nieuwe regel voor een uitgaande spamfilter met de naam contoso leidinggevenden gemaakt met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="ed980-302">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="ed980-303">Het uitgaande spamfilter beleid met de naam contoso-leidinggevenden is gekoppeld aan de regel.</span><span class="sxs-lookup"><span data-stu-id="ed980-303">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="ed980-304">De regel is van toepassing op leden van de groep met de naam Contoso Executives Group.</span><span class="sxs-lookup"><span data-stu-id="ed980-304">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="ed980-305">Zie [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="ed980-305">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="ed980-306">PowerShell gebruiken om uitgaand spamfilter beleid weer te geven</span><span class="sxs-lookup"><span data-stu-id="ed980-306">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="ed980-307">Voer de volgende opdracht uit als u een overzicht wilt weergeven van alle uitgaande spamfilter beleid:</span><span class="sxs-lookup"><span data-stu-id="ed980-307">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="ed980-308">Gebruik de volgende syntaxis om gedetailleerde informatie weer te geven over een specifiek beleid voor uitgaand spamfilter:</span><span class="sxs-lookup"><span data-stu-id="ed980-308">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="ed980-309">In het volgende voorbeeld worden alle eigenschapswaarden geretourneerd voor het uitgaande spamfilter beleid met de naam leidinggevenden.</span><span class="sxs-lookup"><span data-stu-id="ed980-309">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="ed980-310">Zie [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="ed980-310">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="ed980-311">PowerShell gebruiken om uitgaande spamfilter regels weer te geven</span><span class="sxs-lookup"><span data-stu-id="ed980-311">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="ed980-312">Als u bestaande regels voor uitgaande spamfilters wilt weergeven, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="ed980-312">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

<span data-ttu-id="ed980-313">Voer de volgende opdracht uit als u een overzicht wilt weergeven van alle regels voor uitgaande spamfilter:</span><span class="sxs-lookup"><span data-stu-id="ed980-313">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="ed980-314">Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:</span><span class="sxs-lookup"><span data-stu-id="ed980-314">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="ed980-315">Gebruik de volgende syntaxis om gedetailleerde informatie weer te geven over een specifieke regel voor uitgaande spamfilter:</span><span class="sxs-lookup"><span data-stu-id="ed980-315">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="ed980-316">In het volgende voorbeeld worden alle eigenschapwaarden voor de uitgaande spamfilter regel met de naam contoso leidinggevenden geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="ed980-316">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="ed980-317">Zie [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="ed980-317">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="ed980-318">PowerShell gebruiken om uitgaand spamfilter beleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="ed980-318">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="ed980-319">U kunt dezelfde instellingen gebruiken als u een beleid voor het filteren van schadelijke software in PowerShell wijzigt, zoals wordt beschreven in de sectie [stap 1: PowerShell gebruiken om een uitgaand spamfilter beleid te maken](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) eerder in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="ed980-319">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="ed980-320">U kunt de naam van een uitgaand spamfilter beleid niet wijzigen (de cmdlet **set-HostedOutboundSpamFilterPolicy** heeft geen _naam_ parameter).</span><span class="sxs-lookup"><span data-stu-id="ed980-320">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="ed980-321">Wanneer u de naam van een uitgaand spam beleid wijzigt in de beveiligings & nalevings centrum, wordt de naam van de uitgaande spamfilter _regel_ alleen gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="ed980-321">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="ed980-322">Als u een uitgaand spamfilter beleid wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="ed980-322">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="ed980-323">Zie [set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="ed980-323">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="ed980-324">PowerShell gebruiken om uitgaande spamfilter regels te wijzigen</span><span class="sxs-lookup"><span data-stu-id="ed980-324">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="ed980-325">De enige instelling die niet beschikbaar is wanneer u een uitgaande spamfilter regel wijzigt in PowerShell is de _ingeschakelde_ parameter waarmee u een uitgeschakelde regel kunt maken.</span><span class="sxs-lookup"><span data-stu-id="ed980-325">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="ed980-326">Zie de volgende sectie als u bestaande regels voor uitgaande spamfilters wilt in-of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="ed980-326">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="ed980-327">Anders zijn er geen extra instellingen beschikbaar wanneer u een uitgaande spamfilter regel wijzigt in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed980-327">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="ed980-328">U kunt dezelfde instellingen gebruiken wanneer u een regel maakt zoals wordt beschreven in de sectie [stap 2: PowerShell gebruiken om een uitgaande spamfilter regel te maken](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) eerder in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="ed980-328">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="ed980-329">Als u een uitgaande spamfilter regel wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="ed980-329">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="ed980-330">Zie [set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="ed980-330">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="ed980-331">PowerShell gebruiken om uitgaande spamfilter regels in of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="ed980-331">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="ed980-332">Als u een uitgaande spamfilter regel in-of uitschakelt in PowerShell, wordt het volledige uitgaande spam beleid (de regels voor uitgaande spamfilter en het uitgaande spamfilter beleid) in-of uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="ed980-332">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="ed980-333">U kunt het standaardbeleid voor uitgaande spam niet in-of uitschakelen (het is altijd altijd van toepassing op alle geadresseerden).</span><span class="sxs-lookup"><span data-stu-id="ed980-333">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="ed980-334">Gebruik de volgende syntaxis om een uitgaande spamfilter regel in of uit te schakelen in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ed980-334">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="ed980-335">In dit voorbeeld wordt de uitgaande spamfilter regel genaamd marketing afdeling uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="ed980-335">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="ed980-336">In dit voorbeeld wordt dezelfde regel ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="ed980-336">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="ed980-337">Zie [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) en [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="ed980-337">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="ed980-338">PowerShell gebruiken voor het instellen van de prioriteit van regels voor uitgaande spamfilters</span><span class="sxs-lookup"><span data-stu-id="ed980-338">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="ed980-339">De hoogste prioriteit die u in kunt stellen op een regel is 0.</span><span class="sxs-lookup"><span data-stu-id="ed980-339">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="ed980-340">De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels.</span><span class="sxs-lookup"><span data-stu-id="ed980-340">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="ed980-341">Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ed980-341">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="ed980-342">Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels.</span><span class="sxs-lookup"><span data-stu-id="ed980-342">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="ed980-343">Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.</span><span class="sxs-lookup"><span data-stu-id="ed980-343">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="ed980-344">Als u de prioriteit wilt instellen van een uitgaande spamfilter regel in PowerShell, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="ed980-344">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="ed980-345">In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2.</span><span class="sxs-lookup"><span data-stu-id="ed980-345">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="ed980-346">Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).</span><span class="sxs-lookup"><span data-stu-id="ed980-346">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - <span data-ttu-id="ed980-347">Als u de prioriteit wilt instellen van een nieuwe regel wanneer u deze maakt, gebruikt u de parameter _Priority_ op de cmdlet **New-HostedOutboundSpamFilterRule** .</span><span class="sxs-lookup"><span data-stu-id="ed980-347">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
>
> - <span data-ttu-id="ed980-348">Het uitgaande spamfilter beleid heeft geen corresponderende regel voor spamfilters, en het is altijd de **laagste** ongewijzigde prioriteitswaarde.</span><span class="sxs-lookup"><span data-stu-id="ed980-348">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="ed980-349">PowerShell gebruiken om beleid voor uitgaande spamfilters te verwijderen</span><span class="sxs-lookup"><span data-stu-id="ed980-349">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="ed980-350">Wanneer u PowerShell gebruikt om een uitgaand spamfilter beleid te verwijderen, wordt de bijbehorende regel voor uitgaande spamfilter niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ed980-350">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="ed980-351">Als u een beleid voor uitgaande spamfilters wilt verwijderen in PowerShell, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="ed980-351">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="ed980-352">In dit voorbeeld wordt het uitgaande spamfilter beleid genaamd marketing afdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ed980-352">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="ed980-353">Zie [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="ed980-353">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="ed980-354">PowerShell gebruiken om uitgaande spamfilter regels te verwijderen</span><span class="sxs-lookup"><span data-stu-id="ed980-354">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="ed980-355">Wanneer u PowerShell gebruikt om een uitgaande spamfilter regel te verwijderen, wordt het bijbehorende uitgaande spamfilter beleid niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ed980-355">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="ed980-356">Gebruik de volgende syntaxis om een uitgaande spamfilter regel te verwijderen in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ed980-356">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="ed980-357">In dit voorbeeld wordt de uitgaande spamfilter regel genaamd marketing afdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ed980-357">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="ed980-358">Zie [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="ed980-358">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="ed980-359">Voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="ed980-359">For more information</span></span>

[<span data-ttu-id="ed980-360">Geblokkeerde gebruikers verwijderen uit de portal voor gebruikers met beperkte rechten</span><span class="sxs-lookup"><span data-stu-id="ed980-360">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="ed980-361">Groep met verhoogd risico voor uitgaande berichten</span><span class="sxs-lookup"><span data-stu-id="ed980-361">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="ed980-362">Veelgestelde vragen over beveiliging tegen ongewenste e-mail</span><span class="sxs-lookup"><span data-stu-id="ed980-362">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)

[<span data-ttu-id="ed980-363">Rapport over automatisch doorgestuurde berichten</span><span class="sxs-lookup"><span data-stu-id="ed980-363">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)
