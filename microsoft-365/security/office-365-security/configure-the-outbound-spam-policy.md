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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen informatie krijgen over het weergeven, maken, wijzigen en verwijderen van uitgaande spambeleidsregels in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1b8c330e84716c455fa1f4759c82109ec59a3fc9
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406490"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="21915-103">Uitgaande spamfilters configureren in EOP</span><span class="sxs-lookup"><span data-stu-id="21915-103">Configure outbound spam filtering in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="21915-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="21915-104">**Applies to**</span></span>
- [<span data-ttu-id="21915-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="21915-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="21915-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="21915-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="21915-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="21915-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="21915-108">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken worden uitgaande e-mailberichten die via EOP worden verzonden, automatisch gecontroleerd op spam en ongebruikelijke verzendingsactiviteiten.</span><span class="sxs-lookup"><span data-stu-id="21915-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="21915-109">Uitgaande spam van een gebruiker in uw organisatie duidt meestal op een gekromd account.</span><span class="sxs-lookup"><span data-stu-id="21915-109">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="21915-110">Verdachte uitgaande berichten worden gemarkeerd als spam (ongeacht het betrouwbaarheidsniveau voor spam of SCL) en worden omgeleid via de bezorgingsgroep met hoog risico om de reputatie van de service te helpen beschermen (dat wil zeggen: zorg dat de bron-e-mailservers van Microsoft 365 niet op [ip-blokkeerlijsten](high-risk-delivery-pool-for-outbound-messages.md) staan).</span><span class="sxs-lookup"><span data-stu-id="21915-110">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="21915-111">Beheerders worden automatisch op de hoogte gesteld van verdachte uitgaande e-mailactiviteit en geblokkeerde gebruikers via [waarschuwingsbeleid.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="21915-111">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="21915-112">EOP maakt gebruik van uitgaand spambeleid als onderdeel van de algehele verdediging van spam in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="21915-112">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="21915-113">Zie [Bescherming tegen antispam](anti-spam-protection.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="21915-113">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="21915-114">Beheerders kunnen het standaardbeleid voor uitgaande spam bekijken, bewerken en configureren (maar niet verwijderen).</span><span class="sxs-lookup"><span data-stu-id="21915-114">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="21915-115">Voor een grotere granulatie kunt u ook aangepast beleid voor uitgaande spam maken dat van toepassing is op specifieke gebruikers, groepen of domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="21915-115">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="21915-116">Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.</span><span class="sxs-lookup"><span data-stu-id="21915-116">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="21915-117">U kunt uitgaand spambeleid configureren in het beveiligings- &-compliancecentrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).</span><span class="sxs-lookup"><span data-stu-id="21915-117">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="21915-118">De basiselementen van een uitgaand spambeleid in EOP zijn:</span><span class="sxs-lookup"><span data-stu-id="21915-118">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="21915-119">**Het beleid voor het filteren van uitgaande spam:** hiermee geeft u de acties op voor uitgaande spamfilters en de meldingsopties.</span><span class="sxs-lookup"><span data-stu-id="21915-119">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="21915-120">**De regel voor het filteren** van uitgaande spam: geeft de prioriteits- en geadresseerdefilters (op wie het beleid van toepassing is) op een uitgaand spamfilterbeleid.</span><span class="sxs-lookup"><span data-stu-id="21915-120">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="21915-121">Het verschil tussen deze twee elementen is niet duidelijk wanneer u uitgaande spambeleid beheert in het beveiligings- & compliancecentrum:</span><span class="sxs-lookup"><span data-stu-id="21915-121">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="21915-122">Wanneer u een beleid maakt, maakt u tegelijkertijd een uitgaande spamfilterregel en het bijbehorende beleid voor uitgaand spamfilter met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="21915-122">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="21915-123">Wanneer u een beleid wijzigt, worden instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld, en de geadresseerdefilters de regel voor het uitgaande spamfilter gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="21915-123">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="21915-124">Alle andere instellingen wijzigen het bijbehorende uitgaande spamfilterbeleid.</span><span class="sxs-lookup"><span data-stu-id="21915-124">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="21915-125">Wanneer u een beleid verwijdert, worden de uitgaande spamfilterregel en het bijbehorende uitgaande spamfilterbeleid verwijderd.</span><span class="sxs-lookup"><span data-stu-id="21915-125">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="21915-126">In Exchange Online PowerShell of standalone EOP PowerShell beheert u het beleid en de regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="21915-126">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="21915-127">Zie de sectie Exchange Online PowerShell of de zelfstandige [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) gebruiken om uitgaande spambeleidsregels verderop in dit artikel te configureren.</span><span class="sxs-lookup"><span data-stu-id="21915-127">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this article.</span></span>

<span data-ttu-id="21915-128">Elke organisatie heeft een ingebouwd, uitgaand spambeleid met de naam Standaard dat de volgende eigenschappen heeft:</span><span class="sxs-lookup"><span data-stu-id="21915-128">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="21915-129">Het beleid wordt toegepast op alle geadresseerden in de organisatie, ook als er geen regel voor het uitgaande spamfilter (filters voor geadresseerden) aan het beleid is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="21915-129">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="21915-130">Het beleid heeft de prioriteit **Laagste** die u niet kunt wijzigen (het beleid wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="21915-130">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="21915-131">Alle beleid dat u maakt heeft altijd een hogere prioriteit dan het beleid met de naam Standaard.</span><span class="sxs-lookup"><span data-stu-id="21915-131">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="21915-132">Het beleid is het standaardbeleid (de eigenschap **IsDefault** heeft de waarde `True`) en u kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="21915-132">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="21915-133">Als u uitgaande spamfilters effectiever wilt maken, kunt u aangepaste beleidsregels voor uitgaande spam maken met striktere instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="21915-133">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="21915-134">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="21915-134">What do you need to know before you begin?</span></span>

- <span data-ttu-id="21915-135">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="21915-135">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="21915-136">Gebruik <https://protection.office.com/antispam> om direct naar de pagina **Antispaminstellingen** te gaan.</span><span class="sxs-lookup"><span data-stu-id="21915-136">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="21915-137">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21915-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="21915-138">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21915-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="21915-139">U moet machtigingen toegewezen krijgen in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="21915-139">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="21915-140">Als u uitgaande spambeleidsregels wilt toevoegen, wijzigen **en** verwijderen, moet u lid zijn van de rollengroepen **Organisatiebeheer** of Beveiligingsbeheerder.</span><span class="sxs-lookup"><span data-stu-id="21915-140">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="21915-141">Voor alleen-lezen toegang tot uitgaand spambeleid moet u  lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="21915-141">For read-only access to outbound spam policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="21915-142">Zie Machtigingen [in Exchange Online voor meer informatie.](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="21915-142">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="21915-143">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="21915-143">**Notes**:</span></span>

  - <span data-ttu-id="21915-144">Als u gebruikers toevoegt aan de bijbehorende Azure Active Directory-rol  in het Microsoft 365-beheercentrum, krijgen gebruikers de vereiste machtigingen en machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="21915-144">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="21915-145">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="21915-145">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="21915-146">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="21915-146">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="21915-147">Zie de instellingen voor uitgaand spamfilterbeleid voor EOP voor de aanbevolen instellingen voor uitgaand [spambeleid.](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="21915-147">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="21915-148">Het [](../../compliance/alert-policies.md) standaardbeleid voor waarschuwingen met de naam Verzenden per  e-mail is **overschreden,** patronen voor verdachte e-mails verzenden gedetecteerd, en Gebruikers die het verzenden van e-mail beperken, verzenden van e-mailmeldingen al naar leden van de groep **TenantAdmins** **(globale** beheerders) over ongebruikelijke uitgaande e-mailactiviteit en geblokkeerde gebruikers vanwege uitgaande spam. </span><span class="sxs-lookup"><span data-stu-id="21915-148">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="21915-149">Zie De [waarschuwingsinstellingen voor gebruikers met beperkingen controleren voor meer informatie.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)</span><span class="sxs-lookup"><span data-stu-id="21915-149">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="21915-150">U wordt aangeraden dit waarschuwingsbeleid te gebruiken in plaats van de meldingsopties voor uitgaande spam.</span><span class="sxs-lookup"><span data-stu-id="21915-150">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="21915-151">Het beveiligings- & voor het maken van uitgaand spambeleid</span><span class="sxs-lookup"><span data-stu-id="21915-151">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="21915-152">Als u een aangepast uitgaand spambeleid maakt in het beveiligings- & compliancecentrum, worden de regel voor het filteren van ongewenste e-mail en het bijbehorende spamfilterbeleid op hetzelfde moment met dezelfde naam voor beide gemaakt.</span><span class="sxs-lookup"><span data-stu-id="21915-152">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="21915-153">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="21915-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="21915-154">Klik op **de pagina Antispaminstellingen** op **Een uitgaand beleid maken.**</span><span class="sxs-lookup"><span data-stu-id="21915-154">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="21915-155">Configureer **de volgende instellingen in** het uitgaande spamfilterbeleid dat wordt geopend:</span><span class="sxs-lookup"><span data-stu-id="21915-155">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="21915-156">**Naam**: een unieke beschrijvende naam voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="21915-156">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="21915-157">**Beschrijving**: voer een optionele beschrijving in voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="21915-157">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="21915-158">(Optioneel) Vouw de **sectie Meldingen uit** om extra gebruikers te configureren die kopieën en meldingen van verdachte uitgaande e-mailberichten moeten ontvangen:</span><span class="sxs-lookup"><span data-stu-id="21915-158">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="21915-159">**Een kopie van verdachte uitgaande** e-mailberichten naar specifieke personen verzenden: met deze instelling worden de opgegeven gebruikers als BCC-geadresseerden toegevoegd aan de verdachte uitgaande berichten.</span><span class="sxs-lookup"><span data-stu-id="21915-159">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span>

     > [!NOTE]
     > <span data-ttu-id="21915-160">Deze instelling werkt alleen in het standaardbeleid voor uitgaande spam.</span><span class="sxs-lookup"><span data-stu-id="21915-160">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="21915-161">Het werkt niet in aangepast uitgaand spambeleid dat u maakt.</span><span class="sxs-lookup"><span data-stu-id="21915-161">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="21915-162">Deze instelling inschakelen:</span><span class="sxs-lookup"><span data-stu-id="21915-162">To enable this setting:</span></span>

     1. <span data-ttu-id="21915-163">Schakel het selectievakje in om de instelling in te stellen.</span><span class="sxs-lookup"><span data-stu-id="21915-163">Select the check box to enable the setting.</span></span>

     1. <span data-ttu-id="21915-164">Klik **op Personen toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="21915-164">Click **Add people**.</span></span> <span data-ttu-id="21915-165">In de **flyout Geadresseerden toevoegen of** verwijderen die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="21915-165">In the **Add or remove recipients** flyout that appears:</span></span>

     1. <span data-ttu-id="21915-166">Voert u het e-mailadres van de afzender in.</span><span class="sxs-lookup"><span data-stu-id="21915-166">Enter the sender's email address.</span></span> <span data-ttu-id="21915-167">U kunt meerdere e-mailadressen opgeven, gescheiden door puntkomma's (;) of één geadresseerde per regel.</span><span class="sxs-lookup"><span data-stu-id="21915-167">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     1. <span data-ttu-id="21915-168">Klikt u op</span><span class="sxs-lookup"><span data-stu-id="21915-168">Click</span></span> ![Pictogram toevoegen](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="21915-170">om de geadresseerden toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="21915-170">to add the recipients.</span></span>

        <span data-ttu-id="21915-171">Herhaal deze stappen zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="21915-171">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="21915-172">De geadresseerden die u hebt toegevoegd, worden weergegeven in **de sectie Adressenlijst** in de flyout.</span><span class="sxs-lookup"><span data-stu-id="21915-172">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="21915-173">Als u een geadresseerde wilt verwijderen, klikt ![ u op de knop ](../../media/scc-remove-icon.png) Verwijderen.</span><span class="sxs-lookup"><span data-stu-id="21915-173">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     1. <span data-ttu-id="21915-174">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="21915-174">When you're finished, click **Save**.</span></span>

        <span data-ttu-id="21915-175">Als u deze instelling wilt uitschakelen, schakelt u het selectievakje uit.</span><span class="sxs-lookup"><span data-stu-id="21915-175">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="21915-176">**Specifieke personen op de hoogte stellen als een afzender is geblokkeerd vanwege het verzenden van uitgaande spam:**</span><span class="sxs-lookup"><span data-stu-id="21915-176">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="21915-177">Deze instelling wordt afgeschreven van het beleid voor uitgaande spam.</span><span class="sxs-lookup"><span data-stu-id="21915-177">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="21915-178">Het [](../../compliance/alert-policies.md) standaardwaarschuwingsbeleid  met de naam Gebruiker dat geen e-mail kan verzenden, verzendt al e-mailmeldingen naar leden van de groep **TenantAdmins** **(globale** beheerders) wanneer gebruikers worden geblokkeerd omdat ze de limieten in de sectie **Limieten** voor geadresseerden overschrijden.</span><span class="sxs-lookup"><span data-stu-id="21915-178">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="21915-179">**U wordt ten zeerste aangeraden het waarschuwingsbeleid** te gebruiken in plaats van deze instelling in het uitgaande spambeleid om beheerders en andere gebruikers op de hoogte te stellen.</span><span class="sxs-lookup"><span data-stu-id="21915-179">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users**.</span></span> <span data-ttu-id="21915-180">Zie De [waarschuwingsinstellingen voor gebruikers met beperkingen controleren voor instructies.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)</span><span class="sxs-lookup"><span data-stu-id="21915-180">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

5. <span data-ttu-id="21915-181">(Optioneel) Vouw de **sectie Geadresseerdenlimieten** uit om de limieten en acties voor verdachte uitgaande e-mailberichten te configureren:</span><span class="sxs-lookup"><span data-stu-id="21915-181">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="21915-182">Deze instellingen zijn alleen van toepassing op postvakken in de cloud.</span><span class="sxs-lookup"><span data-stu-id="21915-182">These settings are only applicable to cloud-based mailboxes.</span></span>

   - <span data-ttu-id="21915-183">**Maximum aantal geadresseerden per gebruiker**</span><span class="sxs-lookup"><span data-stu-id="21915-183">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="21915-184">Een geldige waarde is 0 tot 10000.</span><span class="sxs-lookup"><span data-stu-id="21915-184">A valid value is 0 to 10000.</span></span> <span data-ttu-id="21915-185">De standaardwaarde is 0, wat betekent dat de standaardinstellingen van de service worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="21915-185">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="21915-186">Zie Limieten voor [verzenden voor meer informatie.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)</span><span class="sxs-lookup"><span data-stu-id="21915-186">For more information, see [Sending limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

     - <span data-ttu-id="21915-187">**Externe uurlimiet:** het maximum aantal externe geadresseerden per uur.</span><span class="sxs-lookup"><span data-stu-id="21915-187">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="21915-188">**Interne uurlimiet:** het maximum aantal interne geadresseerden per uur.</span><span class="sxs-lookup"><span data-stu-id="21915-188">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="21915-189">**Daglimiet:** het maximum aantal geadresseerden per dag.</span><span class="sxs-lookup"><span data-stu-id="21915-189">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="21915-190">**Actie wanneer een gebruiker de bovenstaande limieten** overschrijdt: Configureer de actie die moet worden ondernomen wanneer een van de limieten voor **geadresseerden** wordt overschreden.</span><span class="sxs-lookup"><span data-stu-id="21915-190">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="21915-191">Voor alle acties geldt dat de  geadresseerden die zijn opgegeven in de Gebruiker, geen e-mailwaarschuwingsbeleid kunnen verzenden (en in het nu redundante hiervan specifieke personen op de hoogte stellen als een afzender is geblokkeerd vanwege het verzenden van uitgaande spam in het uitgaande **spambeleid,** e-mailmeldingen ontvangen.</span><span class="sxs-lookup"><span data-stu-id="21915-191">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="21915-192">**De gebruiker beperken tot het verzenden van e-mail tot** de volgende dag: dit is de standaardwaarde.</span><span class="sxs-lookup"><span data-stu-id="21915-192">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="21915-193">Er worden e-mailmeldingen verzonden en de gebruiker kan de volgende dag op basis van UTC-tijd geen berichten meer verzenden.</span><span class="sxs-lookup"><span data-stu-id="21915-193">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="21915-194">De beheerder kan dit blok niet overschrijven.</span><span class="sxs-lookup"><span data-stu-id="21915-194">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="21915-195">De activiteitenwaarschuwing met de **naam Gebruiker kan geen e-mailmeldingen** verzenden naar beheerders (via e-mail en op de pagina **Waarschuwingen** weergeven).</span><span class="sxs-lookup"><span data-stu-id="21915-195">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="21915-196">Geadresseerden die zijn opgegeven in de instelling Specifieke personen op de hoogte stellen als een afzender is geblokkeerd vanwege het verzenden van uitgaande **spam** in het beleid, worden ook op de hoogte gesteld.</span><span class="sxs-lookup"><span data-stu-id="21915-196">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="21915-197">De gebruiker kan de volgende dag op basis van de tijd van UTC geen berichten meer verzenden.</span><span class="sxs-lookup"><span data-stu-id="21915-197">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="21915-198">De beheerder kan dit blok niet overschrijven.</span><span class="sxs-lookup"><span data-stu-id="21915-198">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="21915-199">De gebruiker beperken van het verzenden van e-mail: e-mailmeldingen worden verzonden, de gebruiker wordt toegevoegd aan de portal **[Beperkte gebruikers] <https://sip.protection.office.com/restrictedusers>** in het beveiligings- &-compliancecentrum en de gebruiker kan pas e-mail verzenden als de gebruiker door een beheerder uit de **portal** voor beperkte gebruikers is verwijderd. Nadat een beheerder de gebruiker uit de lijst heeft verwijderd, wordt de gebruiker die dag niet opnieuw beperkt.</span><span class="sxs-lookup"><span data-stu-id="21915-199">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="21915-200">Zie Een gebruiker verwijderen uit de portal voor beperkte gebruikers na het verzenden [van ongewenste e-mail voor instructies.](removing-user-from-restricted-users-portal-after-spam.md)</span><span class="sxs-lookup"><span data-stu-id="21915-200">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="21915-201">**Geen actie, alleen waarschuwing:** e-mailmeldingen worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="21915-201">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="21915-202">(Optioneel) Vouw **de sectie Automatisch doorsturen uit** om het automatisch doorsturen van e-mail door gebruikers naar externe afzenders te bepalen.</span><span class="sxs-lookup"><span data-stu-id="21915-202">(Optional) Expand **Automatic forwarding** section to control automatic email forwarding by users to external senders.</span></span> <span data-ttu-id="21915-203">Zie Automatische doorsturen van [externe e-mail instellen in Microsoft 365 voor meer informatie.](external-email-forwarding.md)</span><span class="sxs-lookup"><span data-stu-id="21915-203">For more information, see [Control automatic external email forwarding in Microsoft 365](external-email-forwarding.md).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="21915-204">Vóór september 2020 zijn deze instellingen beschikbaar, maar niet afgedwongen.</span><span class="sxs-lookup"><span data-stu-id="21915-204">Before September 2020, these settings are available but not enforced.</span></span>
   >
   > - <span data-ttu-id="21915-205">Deze instellingen gelden alleen voor postvakken in de cloud.</span><span class="sxs-lookup"><span data-stu-id="21915-205">These settings apply only to cloud-based mailboxes.</span></span>
   >
   > - <span data-ttu-id="21915-206">Als automatisch doorsturen is uitgeschakeld, ontvangt de geadresseerde een rapport over niet-bezorging (ook wel een NDR of niet-bezorgdbericht genoemd) als externe afzenders e-mail verzenden naar een postvak waarin doorsturen is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="21915-206">When automatic forwarding is disabled, the recipient will receive a non-delivery report (also known as an NDR or bounce message) if external senders send email to a mailbox that has forwarding in place.</span></span> <span data-ttu-id="21915-207">Als het bericht wordt verzonden door een interne afzender en de methode voor doorsturen postvak doorsturen [is](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (ook wel _SMTP-doorsturen_ genoemd), krijgt de interne afzender de NDR. </span><span class="sxs-lookup"><span data-stu-id="21915-207">If the message is sent by an internal sender **and** the forwarding method is [mailbox forwarding](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_), the internal sender will get the NDR.</span></span> <span data-ttu-id="21915-208">De interne afzender krijgt geen NDR als het doorsturen is veroorzaakt door een regel voor Postvak IN.</span><span class="sxs-lookup"><span data-stu-id="21915-208">The internal sender does not get an NDR if the forwarding occurred due to an inbox rule.</span></span>

   <span data-ttu-id="21915-209">De beschikbare waarden zijn:</span><span class="sxs-lookup"><span data-stu-id="21915-209">The available values are:</span></span>

   - <span data-ttu-id="21915-210">**Automatisch - Systeembeheer:** hiermee kunt u uitgaande spam filteren om automatische doorsturen van externe e-mail te controleren.</span><span class="sxs-lookup"><span data-stu-id="21915-210">**Automatic - System-controlled**: Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="21915-211">Dit is de standaardwaarde.</span><span class="sxs-lookup"><span data-stu-id="21915-211">This is the default value.</span></span>
   - <span data-ttu-id="21915-212">**In:** automatisch extern doorsturen van e-mail wordt niet uitgeschakeld door het beleid.</span><span class="sxs-lookup"><span data-stu-id="21915-212">**On**: Automatic external email forwarding is not disabled by the policy.</span></span>
   - <span data-ttu-id="21915-213">**Uit:** alle automatische externe doorsturen van e-mail wordt uitgeschakeld door het beleid.</span><span class="sxs-lookup"><span data-stu-id="21915-213">**Off**: All automatic external email forwarding is disabled by the policy.</span></span>

7. <span data-ttu-id="21915-214">(Vereist) Vouw de **sectie Toegepast op** uit om de interne afzenders te identificeren waar het beleid op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="21915-214">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="21915-215">U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering.</span><span class="sxs-lookup"><span data-stu-id="21915-215">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="21915-216">Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<sender1\>_ of _\<sender2\>_).</span><span class="sxs-lookup"><span data-stu-id="21915-216">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="21915-217">Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<sender1\>_ en _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="21915-217">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="21915-218">Het eenvoudigste is drie keer te klikken op **Een voorwaarde toevoegen** om alle beschikbare voorwaarden weer te geven.</span><span class="sxs-lookup"><span data-stu-id="21915-218">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="21915-219">U kunt op de ![knop Verwijderen](../../media/scc-remove-icon.png) klikken om voorwaarden te verwijderen die u niet wilt configureren.</span><span class="sxs-lookup"><span data-stu-id="21915-219">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="21915-220">**Het domein van de** afzender is: hiermee geeft u afzenders op in een of meer geconfigureerde geaccepteerde domeinen in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="21915-220">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in the organization.</span></span> <span data-ttu-id="21915-221">Klik in het vak **Een tag toevoegen** om een domein weer te geven en te selecteren.</span><span class="sxs-lookup"><span data-stu-id="21915-221">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="21915-222">Klik opnieuw op het vak **Een tag toevoegen** om aanvullende domeinen te selecteren als er meer dan één domein beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="21915-222">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="21915-223">**Afzender is:** geeft een of meer gebruikers in uw organisatie aan.</span><span class="sxs-lookup"><span data-stu-id="21915-223">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="21915-224">Klik in het vak **Tag toevoegen** en begin te typen om de lijst te filteren.</span><span class="sxs-lookup"><span data-stu-id="21915-224">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="21915-225">Klik nogmaals op **het vak Een tag toevoegen** om extra afzenders te selecteren.</span><span class="sxs-lookup"><span data-stu-id="21915-225">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="21915-226">**Afzender is lid van:** geeft een of meer groepen in uw organisatie aan.</span><span class="sxs-lookup"><span data-stu-id="21915-226">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="21915-227">Klik in het vak **Tag toevoegen** en begin te typen om de lijst te filteren.</span><span class="sxs-lookup"><span data-stu-id="21915-227">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="21915-228">Klik nogmaals op **het vak Een tag toevoegen** om extra afzenders te selecteren.</span><span class="sxs-lookup"><span data-stu-id="21915-228">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="21915-229">**Behalve als**: om uitzonderingen op de regel toe te voegen, klikt u drie keer op **Een voorwaarde toevoegen** om alle beschikbare uitzonderingen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="21915-229">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="21915-230">De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="21915-230">The settings and behavior are exactly like the conditions.</span></span>

8. <span data-ttu-id="21915-231">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="21915-231">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="21915-232">Het beveiligings- & compliancecentrum gebruiken om uitgaand spambeleid weer te geven</span><span class="sxs-lookup"><span data-stu-id="21915-232">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="21915-233">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="21915-233">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="21915-234">Klik op **de pagina Antispaminstellingen** op ![ het pictogram Uitvbreken ](../../media/scc-expand-icon.png) om een uitgaand spambeleid uit te vouwen:</span><span class="sxs-lookup"><span data-stu-id="21915-234">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="21915-235">Het standaardbeleid met de **naam Uitgaand spamfilterbeleid.**</span><span class="sxs-lookup"><span data-stu-id="21915-235">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="21915-236">Een aangepast beleid dat u hebt gemaakt, waarbij de waarde in de **kolom Type** aangepast **uitgaand spambeleid is.**</span><span class="sxs-lookup"><span data-stu-id="21915-236">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="21915-237">De beleidsinstellingen worden weergegeven in de uitgebreide beleidsdetails die worden weergegeven of u kunt op **Beleid bewerken klikken.**</span><span class="sxs-lookup"><span data-stu-id="21915-237">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="21915-238">Het beveiligings- & voor het aanpassen van uitgaand spambeleid</span><span class="sxs-lookup"><span data-stu-id="21915-238">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="21915-239">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="21915-239">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="21915-240">Klik op **de pagina Antispaminstellingen** op ![ het pictogram Uitvbreken ](../../media/scc-expand-icon.png) om een uitgaand spambeleid uit te vouwen:</span><span class="sxs-lookup"><span data-stu-id="21915-240">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="21915-241">Het standaardbeleid met de **naam Uitgaand spamfilterbeleid.**</span><span class="sxs-lookup"><span data-stu-id="21915-241">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="21915-242">Een aangepast beleid dat u hebt gemaakt, waarbij de waarde in de **kolom Type** aangepast **uitgaand spambeleid is.**</span><span class="sxs-lookup"><span data-stu-id="21915-242">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="21915-243">Klik op **Beleid bewerken**.</span><span class="sxs-lookup"><span data-stu-id="21915-243">Click **Edit policy**.</span></span>

<span data-ttu-id="21915-244">Voor aangepast uitgaand spambeleid zijn de beschikbare instellingen in de flyout die wordt weergegeven identiek aan de instellingen die worden beschreven in het [beveiligings- &-compliancecentrum](#use-the-security--compliance-center-to-create-outbound-spam-policies) om de sectie Uitgaand spambeleid te maken.</span><span class="sxs-lookup"><span data-stu-id="21915-244">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="21915-245">Voor het standaard uitgaande spambeleid, het filterbeleid voor **uitgaande spam,** is de sectie Toegepast op niet beschikbaar (het beleid geldt voor iedereen) en kunt u de naam van het beleid niet wijzigen. </span><span class="sxs-lookup"><span data-stu-id="21915-245">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="21915-246">Zie de volgende secties om beleid in- of uit te schakelen, de prioriteit van beleid te wijzigen of de quarantaine-meldingen van eindgebruiker configureren.</span><span class="sxs-lookup"><span data-stu-id="21915-246">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="21915-247">Uitgaand spambeleid in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="21915-247">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="21915-248">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="21915-248">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="21915-249">Klik op **de pagina Antispaminstellingen** op het pictogram Uitviekken om een aangepast beleid dat u hebt gemaakt uit te vouwen (de waarde in de kolom Type is Aangepast ![ uitgaande ](../../media/scc-expand-icon.png) **spambeleid).** </span><span class="sxs-lookup"><span data-stu-id="21915-249">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="21915-250">Let op de waarde in de kolom **Aan** in de uitgebreide beleidsgegevens die worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="21915-250">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="21915-251">Verplaats te wisselknop naar links om het beleid uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="21915-251">Move the toggle to the left to disable the policy:</span></span> ![Uitschakelen](../../media/scc-toggle-off.png)

   <span data-ttu-id="21915-253">Verplaats te wisselknop naar rechts om het beleid in te schakelen:</span><span class="sxs-lookup"><span data-stu-id="21915-253">Move the toggle to the right to enable the policy:</span></span> ![Inschakelen](../../media/scc-toggle-on.png)

<span data-ttu-id="21915-255">U kunt het standaardbeleid voor uitgaande spam niet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="21915-255">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="21915-256">De prioriteit instellen van aangepast beleid voor uitgaande spam</span><span class="sxs-lookup"><span data-stu-id="21915-256">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="21915-257">Standaard krijgen uitgaande spambeleidsregels een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere beleidsregels hebben een lagere prioriteit dan oudere beleidsregels).</span><span class="sxs-lookup"><span data-stu-id="21915-257">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="21915-258">Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit).</span><span class="sxs-lookup"><span data-stu-id="21915-258">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="21915-259">Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.</span><span class="sxs-lookup"><span data-stu-id="21915-259">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="21915-260">Aangepaste uitgaande spambeleidsregels worden weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid heeft de **prioriteitswaarde** 0).</span><span class="sxs-lookup"><span data-stu-id="21915-260">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="21915-261">Het standaardbeleid voor uitgaande spam met de naam **Uitgaand spamfilterbeleid** heeft de prioriteit laagste waarde **en** u kunt dit niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="21915-261">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="21915-262">Om de prioriteit van beleid te wijzigen, kunt u het beleid naar boven of beneden verplaatsen in de lijst (u kunt het **Prioriteit** snummer in het Beveiligings en compliancecentrum niet rechtstreeks wijzigen).</span><span class="sxs-lookup"><span data-stu-id="21915-262">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="21915-263">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="21915-263">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="21915-264">Zoek op **de pagina met antispaminstellingen** het beleid waarbij de waarde in de kolom **Type** Aangepast uitgaande **spambeleid is.**</span><span class="sxs-lookup"><span data-stu-id="21915-264">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="21915-265">Let op de waarden in de kolom **Prioriteit**:</span><span class="sxs-lookup"><span data-stu-id="21915-265">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="21915-266">Het aangepaste uitgaande spambeleid met de hoogste prioriteit heeft de waarde ![ Pijl-omlaag ](../../media/ITPro-EAC-DownArrowIcon.png) **pictogram 0.**</span><span class="sxs-lookup"><span data-stu-id="21915-266">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="21915-267">Het aangepaste uitgaande spambeleid met de laagste prioriteit heeft de waarde Pijl-omhoog ![ ](../../media/ITPro-EAC-UpArrowIcon.png) **(bijvoorbeeld** ![ Pijl-omhoog pictogram ](../../media/ITPro-EAC-UpArrowIcon.png) **3).**</span><span class="sxs-lookup"><span data-stu-id="21915-267">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="21915-268">Als u drie of meer aangepaste uitgaande spambeleidsregels hebt, hebben de beleidsregels tussen de hoogste en laagste prioriteit de waarden Pijl-omhoog of Pijl-omlaag pictogram n (bijvoorbeeld Pijl-omhoog pictogram ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png)  Pijl-omlaag ![ pictogram ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **2).**</span><span class="sxs-lookup"><span data-stu-id="21915-268">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="21915-269">Klik op</span><span class="sxs-lookup"><span data-stu-id="21915-269">Click</span></span> ![het pictogram pijl-omhoog](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="21915-271">of</span><span class="sxs-lookup"><span data-stu-id="21915-271">or</span></span> ![het pictogram pijl-omlaag](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="21915-273">om het aangepaste uitgaande spambeleid omhoog of omlaag in de prioriteitlijst te verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="21915-273">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="21915-274">Het beveiligings- & voor het verwijderen van uitgaand spambeleid</span><span class="sxs-lookup"><span data-stu-id="21915-274">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="21915-275">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="21915-275">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="21915-276">Klik op **de pagina Antispaminstellingen** op het pictogram Uitviekken om het aangepaste beleid uit te vouwen dat u wilt verwijderen (de kolom Type is aangepast beleid voor ![ uitgaande ](../../media/scc-expand-icon.png) **spam).** </span><span class="sxs-lookup"><span data-stu-id="21915-276">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="21915-277">Klik in de uitgebreide beleidsgegevens op **Beleid verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="21915-277">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="21915-278">Klik op **Ja** in het waarschuwingsvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="21915-278">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="21915-279">U kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="21915-279">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="21915-280">Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken om uitgaand spambeleid te configureren</span><span class="sxs-lookup"><span data-stu-id="21915-280">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id="21915-281">Zoals eerder beschreven bestaat een uitgaand spambeleid uit een uitgaand spamfilterbeleid en een regel voor het filteren van uitgaande spam.</span><span class="sxs-lookup"><span data-stu-id="21915-281">As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id="21915-282">In Exchange Online PowerShell of zelfstandige EOP PowerShell is het verschil tussen beleidsregels voor uitgaande spamfilters en regels voor uitgaande spamfilters duidelijk.</span><span class="sxs-lookup"><span data-stu-id="21915-282">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="21915-283">U beheert beleidsregels voor uitgaande spamfilters met behulp van de cmdlets **\* -HostedOutboundSpamFilterPolicy** en u beheert regels voor uitgaande spamfilters met behulp van de cmdlets **\* -HostedOutboundSpamFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="21915-283">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="21915-284">In PowerShell maakt u eerst het uitgaande spamfilterbeleid en vervolgens maakt u de regel voor het uitgaande spamfilter die het beleid identificeert dat door de regel wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="21915-284">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="21915-285">In PowerShell wijzigt u de instellingen in het beleid van het uitgaande spamfilter en de regel voor het uitgaande spamfilter afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="21915-285">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id="21915-286">Wanneer u een uitgaand spamfilterbeleid uit PowerShell verwijdert, wordt de bijbehorende regel voor het filteren van uitgaande spam niet automatisch verwijderd en omgekeerd.</span><span class="sxs-lookup"><span data-stu-id="21915-286">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="21915-287">PowerShell gebruiken om uitgaand spambeleid te maken</span><span class="sxs-lookup"><span data-stu-id="21915-287">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="21915-288">Het maken van een uitgaand spambeleid in PowerShell bestaat uit twee stappen:</span><span class="sxs-lookup"><span data-stu-id="21915-288">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="21915-289">Maak het beleid voor uitgaande spamfilters.</span><span class="sxs-lookup"><span data-stu-id="21915-289">Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id="21915-290">Maak de regel voor het filteren van uitgaande spam die het beleid voor het filteren van uitgaande spam aangeeft dat de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="21915-290">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="21915-291">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="21915-291">**Notes**:</span></span>

- <span data-ttu-id="21915-292">U kunt een nieuwe regel voor uitgaand spamfilter maken en er een bestaand, niet-verbonden beleid voor uitgaande spam aan toewijzen.</span><span class="sxs-lookup"><span data-stu-id="21915-292">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="21915-293">Een uitgaande spamfilterregel kan niet worden gekoppeld aan meer dan één uitgaand spamfilterbeleid.</span><span class="sxs-lookup"><span data-stu-id="21915-293">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="21915-294">U kunt de volgende instellingen configureren voor nieuw beleid voor uitgaande spamfilters in PowerShell die pas beschikbaar zijn in het beveiligings- & compliancecentrum nadat u het beleid hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="21915-294">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="21915-295">Het nieuwe beleid maken dat is uitgeschakeld _(ingeschakeld_ op de `$false` cmdlet **New-HostedOutboundSpamFilterRule).**</span><span class="sxs-lookup"><span data-stu-id="21915-295">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
  - <span data-ttu-id="21915-296">De prioriteit van het beleid instellen tijdens het maken _(Prioriteit)_ _\<Number\>_ op de cmdlet **New-HostedOutboundSpamFilterRule).**</span><span class="sxs-lookup"><span data-stu-id="21915-296">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="21915-297">Een nieuw uitgaand spamfilterbeleid dat u in PowerShell maakt, is pas zichtbaar in het beveiligings- & compliancecentrum wanneer u het beleid toewijst aan een spamfilterregel.</span><span class="sxs-lookup"><span data-stu-id="21915-297">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="21915-298">Stap 1: PowerShell gebruiken om een beleid voor uitgaande spamfilters te maken</span><span class="sxs-lookup"><span data-stu-id="21915-298">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="21915-299">Gebruik de volgende syntaxis om een uitgaand spamfilterbeleid te maken:</span><span class="sxs-lookup"><span data-stu-id="21915-299">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="21915-300">In dit voorbeeld wordt een nieuw uitgaand spamfilterbeleid gemaakt met de naam Contoso-leidinggevenden met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="21915-300">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="21915-301">De limieten voor de geadresseerden zijn beperkt tot kleinere waarden die standaard worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="21915-301">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="21915-302">Zie Limieten voor verzenden [in microsoft 365-opties voor meer informatie.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)</span><span class="sxs-lookup"><span data-stu-id="21915-302">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="21915-303">Wanneer een van de limieten is bereikt, kan de gebruiker geen berichten verzenden.</span><span class="sxs-lookup"><span data-stu-id="21915-303">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="21915-304">Zie [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="21915-304">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="21915-305">Stap 2: PowerShell gebruiken om een uitgaande spamfilterregel te maken</span><span class="sxs-lookup"><span data-stu-id="21915-305">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="21915-306">Gebruik de volgende syntaxis om een uitgaande spamfilterregel te maken:</span><span class="sxs-lookup"><span data-stu-id="21915-306">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="21915-307">In dit voorbeeld wordt een nieuwe uitgaande spamfilterregel gemaakt met de naam Contoso-leidinggevenden met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="21915-307">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="21915-308">Het uitgaande spamfilterbeleid met de naam Contoso Leidinggevenden is aan de regel gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="21915-308">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="21915-309">De regel is van toepassing op leden van de groep met de naam Contoso Executives Group.</span><span class="sxs-lookup"><span data-stu-id="21915-309">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="21915-310">Zie [New-HostedOutboundSpamFilterRule voor](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule)gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="21915-310">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="21915-311">PowerShell gebruiken om beleidsregels voor uitgaande spamfilters weer te geven</span><span class="sxs-lookup"><span data-stu-id="21915-311">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="21915-312">Voer deze opdracht uit om een overzichtslijst met alle uitgaande spamfilterbeleidsregels te retourneren:</span><span class="sxs-lookup"><span data-stu-id="21915-312">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="21915-313">Gebruik de volgende syntaxis om gedetailleerde informatie over een specifiek beleid voor een uitgaand spamfilter te retourneren:</span><span class="sxs-lookup"><span data-stu-id="21915-313">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="21915-314">In dit voorbeeld worden alle eigenschapswaarden voor het uitgaande spamfilterbeleid met de naam Leidinggevenden als retourneert.</span><span class="sxs-lookup"><span data-stu-id="21915-314">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="21915-315">Zie [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="21915-315">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="21915-316">PowerShell gebruiken om regels voor uitgaande spamfilters weer te geven</span><span class="sxs-lookup"><span data-stu-id="21915-316">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="21915-317">Gebruik de volgende syntaxis om bestaande regels voor uitgaande spamfilters te bekijken:</span><span class="sxs-lookup"><span data-stu-id="21915-317">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

<span data-ttu-id="21915-318">Voer deze opdracht uit om een overzichtslijst met alle regels voor het filteren van uitgaande spam te retourneren:</span><span class="sxs-lookup"><span data-stu-id="21915-318">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="21915-319">Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:</span><span class="sxs-lookup"><span data-stu-id="21915-319">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="21915-320">Gebruik de volgende syntaxis om gedetailleerde informatie over een specifieke regel voor een uitgaand spamfilter te retourneren:</span><span class="sxs-lookup"><span data-stu-id="21915-320">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="21915-321">In dit voorbeeld worden alle eigenschapswaarden voor de uitgaande spamfilterregel met de naam Contoso Leidinggevenden als retourneert.</span><span class="sxs-lookup"><span data-stu-id="21915-321">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="21915-322">Zie [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="21915-322">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="21915-323">PowerShell gebruiken om beleid voor uitgaande spamfilters te wijzigen</span><span class="sxs-lookup"><span data-stu-id="21915-323">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="21915-324">Dezelfde instellingen zijn beschikbaar wanneer u een malwarefilterbeleid in PowerShell wijzigt als wanneer u het beleid maakt, zoals beschreven in stap [1: Gebruik PowerShell](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) om een sectie voor uitgaand spamfilterbeleid eerder in dit artikel te maken.</span><span class="sxs-lookup"><span data-stu-id="21915-324">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="21915-325">U kunt de naam van een uitgaand spamfilterbeleid niet wijzigen (de cmdlet **Set HostedOutboundSpamFilterPolicy** heeft _geen naamparameter)._</span><span class="sxs-lookup"><span data-stu-id="21915-325">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="21915-326">Wanneer u de naam van een uitgaand spambeleid wijzigt in het beveiligings- & compliancecentrum, wijzigt u alleen de naam van de regel voor het uitgaande _spamfilter._</span><span class="sxs-lookup"><span data-stu-id="21915-326">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="21915-327">Gebruik de volgende syntaxis om een uitgaand spamfilterbeleid te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="21915-327">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="21915-328">Zie [Set HostedOutboundSpamFilterPolicy voor](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="21915-328">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="21915-329">PowerShell gebruiken om regels voor uitgaande spamfilters te wijzigen</span><span class="sxs-lookup"><span data-stu-id="21915-329">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="21915-330">De enige instelling die niet beschikbaar is wanneer u een regel voor een uitgaand spamfilter in PowerShell wijzigt, is de parameter _Enabled_ waarmee u een uitgeschakelde regel kunt maken.</span><span class="sxs-lookup"><span data-stu-id="21915-330">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="21915-331">Zie de volgende sectie als u bestaande regels voor uitgaande spamfilters wilt in- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="21915-331">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="21915-332">Anders zijn er geen extra instellingen beschikbaar wanneer u een uitgaande spamfilterregel in PowerShell wijzigt.</span><span class="sxs-lookup"><span data-stu-id="21915-332">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="21915-333">Dezelfde instellingen zijn beschikbaar wanneer u een regel maakt, zoals beschreven in stap [2: PowerShell](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) gebruiken om een sectie voor een uitgaande spamfilterregel eerder in dit artikel te maken.</span><span class="sxs-lookup"><span data-stu-id="21915-333">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this article.</span></span>

<span data-ttu-id="21915-334">Gebruik de volgende syntaxis om een uitgaande spamfilterregel te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="21915-334">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="21915-335">Zie [Set HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="21915-335">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="21915-336">PowerShell gebruiken om regels voor uitgaande spamfilters in of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="21915-336">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="21915-337">Door een uitgaande spamfilterregel in PowerShell in of uit te schakelen, schakelt u het hele uitgaande spambeleid (de regel voor het uitgaande spamfilter en het toegewezen uitgaande spamfilterbeleid) in of uit.</span><span class="sxs-lookup"><span data-stu-id="21915-337">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="21915-338">U kunt het standaardbeleid voor uitgaande spam niet in- of uitschakelen (dit wordt altijd toegepast op alle geadresseerden).</span><span class="sxs-lookup"><span data-stu-id="21915-338">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="21915-339">Gebruik de volgende syntaxis om een uitgaande regel voor het filteren van ongewenste e-mail in PowerShell in of uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="21915-339">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="21915-340">In dit voorbeeld wordt de regel voor het filteren van uitgaande spam met de naam Marketingafdeling uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="21915-340">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="21915-341">In dit voorbeeld wordt dezelfde regel ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="21915-341">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="21915-342">Zie [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) en [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="21915-342">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="21915-343">PowerShell gebruiken om de prioriteit van regels voor uitgaande spamfilters in te stellen</span><span class="sxs-lookup"><span data-stu-id="21915-343">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="21915-344">De hoogste prioriteit die u in kunt stellen op een regel is 0.</span><span class="sxs-lookup"><span data-stu-id="21915-344">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="21915-345">De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels.</span><span class="sxs-lookup"><span data-stu-id="21915-345">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="21915-346">Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="21915-346">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="21915-347">Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels.</span><span class="sxs-lookup"><span data-stu-id="21915-347">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="21915-348">Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.</span><span class="sxs-lookup"><span data-stu-id="21915-348">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="21915-349">Gebruik de volgende syntaxis om de prioriteit in te stellen van een uitgaande spamfilterregel in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="21915-349">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="21915-350">In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2.</span><span class="sxs-lookup"><span data-stu-id="21915-350">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="21915-351">Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).</span><span class="sxs-lookup"><span data-stu-id="21915-351">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - <span data-ttu-id="21915-352">Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Prioriteit_ op de cmdlet **New-HostedOutboundSpamFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="21915-352">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
>
> - <span data-ttu-id="21915-353">Het uitgaande standaardfilterbeleid voor ongewenste e-mail heeft geen bijbehorende regel voor het filteren van ongewenste e-mail en heeft altijd de onmodifabele prioriteit **Laagste.**</span><span class="sxs-lookup"><span data-stu-id="21915-353">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="21915-354">PowerShell gebruiken om beleid voor uitgaande spamfilters te verwijderen</span><span class="sxs-lookup"><span data-stu-id="21915-354">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="21915-355">Wanneer u PowerShell gebruikt om een uitgaand spamfilterbeleid te verwijderen, wordt de bijbehorende regel voor het filteren van uitgaande spam niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="21915-355">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="21915-356">Gebruik de volgende syntaxis om een uitgaand spamfilterbeleid in PowerShell te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="21915-356">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="21915-357">In dit voorbeeld wordt het uitgaande spamfilterbeleid met de naam Marketingafdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="21915-357">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="21915-358">Zie [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="21915-358">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="21915-359">PowerShell gebruiken om regels voor uitgaande spamfilters te verwijderen</span><span class="sxs-lookup"><span data-stu-id="21915-359">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="21915-360">Wanneer u PowerShell gebruikt om een uitgaande spamfilterregel te verwijderen, wordt het bijbehorende beleid voor het filteren van uitgaande spam niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="21915-360">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="21915-361">Gebruik de volgende syntaxis om een uitgaande regel voor het filteren van ongewenste e-mail in PowerShell te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="21915-361">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="21915-362">In dit voorbeeld wordt de regel voor het filteren van uitgaande spam met de naam Marketingafdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="21915-362">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="21915-363">Zie [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="21915-363">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="21915-364">Voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="21915-364">For more information</span></span>

[<span data-ttu-id="21915-365">Geblokkeerde gebruikers verwijderen uit de portal voor gebruikers met beperkte rechten</span><span class="sxs-lookup"><span data-stu-id="21915-365">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="21915-366">Groep met verhoogd risico voor uitgaande berichten</span><span class="sxs-lookup"><span data-stu-id="21915-366">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="21915-367">Veelgestelde vragen over beveiliging tegen ongewenste e-mail</span><span class="sxs-lookup"><span data-stu-id="21915-367">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)

[<span data-ttu-id="21915-368">Rapport over automatisch doorgestuurde berichten</span><span class="sxs-lookup"><span data-stu-id="21915-368">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)
