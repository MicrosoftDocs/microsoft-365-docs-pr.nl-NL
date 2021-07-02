---
title: De bezorging van phishingsimulaties van derden configureren voor gebruikers en ongefilterde berichten in SecOps-postvakken
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
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Beheerders kunnen leren hoe ze het beleid voor geavanceerde bezorging in Exchange Online Protection (EOP) kunnen gebruiken om berichten te identificeren die niet moeten worden gefilterd in specifieke ondersteunde scenario's (phishingsimulaties van derden en berichten die worden bezorgd in postvakken van beveiligingsbewerkingen (SecOps).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 053f88da96983b03ad03e75c11a4fa692ac6a850
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256865"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a><span data-ttu-id="af435-103">De bezorging van phishingsimulaties van derden configureren voor gebruikers en ongefilterde berichten in SecOps-postvakken</span><span class="sxs-lookup"><span data-stu-id="af435-103">Configure the delivery of third-party phishing simulations to users and unfiltered messages to SecOps mailboxes</span></span>

<span data-ttu-id="af435-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="af435-104">**Applies to**</span></span>
- [<span data-ttu-id="af435-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="af435-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="af435-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="af435-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="af435-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="af435-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="af435-108">De functie die in dit artikel wordt beschreven, is in Preview, is niet voor iedereen beschikbaar en kan worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="af435-108">The feature that's described in this article is in Preview, isn't available to everyone, and is subject to change.</span></span>

<span data-ttu-id="af435-109">Als u uw organisatie standaard veilig wilt [houden,](secure-by-default.md)staat Exchange Online Protection (EOP) geen veilige lijsten of filtering bypass toe voor berichten die zijn geïdentificeerd als malware of phishing met een hoog vertrouwen.</span><span class="sxs-lookup"><span data-stu-id="af435-109">To keep your organization [secure by default](secure-by-default.md), Exchange Online Protection (EOP) does not allow safe lists or filtering bypass for messages that are identified as malware or high confidence phishing.</span></span> <span data-ttu-id="af435-110">Er zijn echter specifieke scenario's waarvoor niet-gefilterde berichten moeten worden bezorgd.</span><span class="sxs-lookup"><span data-stu-id="af435-110">But, there are specific scenarios that require the delivery of unfiltered messages.</span></span> <span data-ttu-id="af435-111">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="af435-111">For example:</span></span>

- <span data-ttu-id="af435-112">**Phishingsimulaties** van derden: Gesimuleerde aanvallen kunnen u helpen om kwetsbare gebruikers te identificeren voordat een echte aanval van invloed is op uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="af435-112">**Third-party phishing simulations**: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="af435-113">**Postvakken voor beveiligingsbewerkingen (SecOps)**: Speciale postvakken die door beveiligingsteams worden gebruikt om ongefilterde berichten te verzamelen en te analyseren (zowel goed als slecht).</span><span class="sxs-lookup"><span data-stu-id="af435-113">**Security operations (SecOps) mailboxes**: Dedicated mailboxes that are used by security teams to collect and analyze unfiltered messages (both good and bad).</span></span>

<span data-ttu-id="af435-114">U gebruikt het _geavanceerde bezorgingsbeleid_ in Microsoft 365 om te voorkomen dat deze berichten _in_ deze specifieke scenario's worden gefilterd. <sup>\*</sup> Het geavanceerde bezorgingsbeleid zorgt ervoor dat berichten in deze scenario's de volgende resultaten bereiken:</span><span class="sxs-lookup"><span data-stu-id="af435-114">You use the _advanced delivery policy_ in Microsoft 365 to prevent these messages _in these specific scenarios_ from being filtered.<sup>\*</sup> The advanced delivery policy ensures that messages in these scenarios achieve the following results:</span></span>

- <span data-ttu-id="af435-115">Filters in EOP en Microsoft Defender voor Office 365 actie ondernemen op deze berichten.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="af435-115">Filters in EOP and Microsoft Defender for Office 365 take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="af435-116">[Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) voor spam en phishing onderneemt geen actie op deze berichten.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="af435-116">[Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) for spam and phishing take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="af435-117">[Standaardsysteemwaarschuwingen](alerts.md) worden niet geactiveerd voor deze scenario's.</span><span class="sxs-lookup"><span data-stu-id="af435-117">[Default system alerts](alerts.md) aren't triggered for these scenarios.</span></span>
- <span data-ttu-id="af435-118">[Air en clustering in Defender voor Office 365](office-365-air.md) negeert deze berichten.</span><span class="sxs-lookup"><span data-stu-id="af435-118">[AIR and clustering in Defender for Office 365](office-365-air.md) ignores these messages.</span></span>
- <span data-ttu-id="af435-119">Specifiek voor phishingsimulaties van derden:</span><span class="sxs-lookup"><span data-stu-id="af435-119">Specifically for third-party phishing simulations:</span></span>
  - <span data-ttu-id="af435-120">[Beheerdersinzendingen genereren](admin-submission.md) een automatisch antwoord met de melding dat het bericht deel uitmaakt van een phishingsimulatiecampagne en geen echte bedreiging is.</span><span class="sxs-lookup"><span data-stu-id="af435-120">[Admin submissions](admin-submission.md) generates an automatic response saying that the message is part of a phishing simulation campaign and isn't a real threat.</span></span> <span data-ttu-id="af435-121">Waarschuwingen en AIR worden niet geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="af435-121">Alerts and AIR will not be triggered.</span></span>
  - <span data-ttu-id="af435-122">[Safe Koppelingen in Defender voor Office 365](safe-links.md) worden de specifiek geïdentificeerde URL's in deze berichten niet geblokkeerd of tot ontploffing gebracht.</span><span class="sxs-lookup"><span data-stu-id="af435-122">[Safe Links in Defender for Office 365](safe-links.md) doesn't block or detonate the specifically identified URLs in these messages.</span></span>
  - <span data-ttu-id="af435-123">[Safe bijlagen in Defender voor Office 365](safe-attachments.md) worden bijlagen in deze berichten niet tot ontploffing brengen.</span><span class="sxs-lookup"><span data-stu-id="af435-123">[Safe Attachments in Defender for Office 365](safe-attachments.md) doesn't detonate attachments in these messages.</span></span>

<span data-ttu-id="af435-124"><sup>\*</sup> U kunt malwarefilters of ZAP voor malware niet omzeilen.</span><span class="sxs-lookup"><span data-stu-id="af435-124"><sup>\*</sup> You can't bypass malware filtering or ZAP for malware.</span></span>

<span data-ttu-id="af435-125">Berichten die worden geïdentificeerd door het geavanceerde bezorgingsbeleid zijn geen beveiligingsrisico's, dus de berichten worden gemarkeerd als systeem overschrijven.</span><span class="sxs-lookup"><span data-stu-id="af435-125">Messages that are identified by the advanced delivery policy aren't security threats, so the messages are marked as system overrides.</span></span> <span data-ttu-id="af435-126">Beheerders kunnen deze systeem overschrijven en analyseren in de volgende ervaringen:</span><span class="sxs-lookup"><span data-stu-id="af435-126">Admins can filter and analyze these system overrides in the following experiences:</span></span>

- [<span data-ttu-id="af435-127">Threat Explorer/Real-time detecties in Defender voor Office 365 plan 2</span><span class="sxs-lookup"><span data-stu-id="af435-127">Threat Explorer/Real-time detections in Defender for Office 365 plan 2</span></span>](threat-explorer.md)
- <span data-ttu-id="af435-128">De [pagina E-mailentiteit in Threat Explorer/Realtime detecties](mdo-email-entity-page.md)</span><span class="sxs-lookup"><span data-stu-id="af435-128">The [Email entity Page in Threat Explorer/Real-time detections](mdo-email-entity-page.md)</span></span>
- <span data-ttu-id="af435-129">Het [rapport Status van bedreigingsbeveiliging](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="af435-129">The [Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span>
- [<span data-ttu-id="af435-130">Advanced hunting in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="af435-130">Advanced hunting in Microsoft Defender for Endpoint</span></span>](../defender-endpoint/advanced-hunting-overview.md)
- [<span data-ttu-id="af435-131">Campagneweergaven</span><span class="sxs-lookup"><span data-stu-id="af435-131">Campaign Views</span></span>](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="af435-132">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="af435-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="af435-133">U opent de Microsoft 365 Defender-portal bij <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="af435-133">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="af435-134">Als u rechtstreeks naar de pagina **Geavanceerde bezorging wilt** gaan, opent u <https://security.microsoft.com/advanceddelivery> .</span><span class="sxs-lookup"><span data-stu-id="af435-134">To go directly to the **Advanced delivery** page, open <https://security.microsoft.com/advanceddelivery>.</span></span>

- <span data-ttu-id="af435-135">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af435-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="af435-136">U moet machtigingen hebben toegewezen voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="af435-136">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="af435-137">Als u geconfigureerde instellingen wilt maken, wijzigen of verwijderen in het  geavanceerde bezorgingsbeleid, moet u lid zijn van  de rollengroep Beveiligingsbeheerder in de **Microsoft 365 Defender-portal** en lid zijn van de rollengroep Organisatiebeheer in **Exchange Online.**</span><span class="sxs-lookup"><span data-stu-id="af435-137">To create, modify, or remove configured settings in the advanced delivery policy, you need to be a member of the **Security Administrator** role group in the **Microsoft 365 Defender portal** and a member of the **Organization Management** role group in **Exchange Online**.</span></span>
  - <span data-ttu-id="af435-138">Voor alleen-lezen toegang tot het geavanceerde bezorgingsbeleid moet u lid zijn van de rollengroepen **Globale** lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="af435-138">For read-only access to the advanced delivery policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="af435-139">Zie Machtigingen [in de](permissions-microsoft-365-security-center.md) Microsoft 365 Defender portal en [Machtigingen in](/exchange/permissions-exo/permissions-exo)Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="af435-139">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > <span data-ttu-id="af435-140">Gebruikers toevoegen aan de bijbehorende Azure Active Directory functie geeft gebruikers de vereiste machtigingen in de Microsoft 365 Defender _portal_ en machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="af435-140">Adding users to the corresponding Azure Active Directory role gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="af435-141">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="af435-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="af435-142">Gebruik de Microsoft 365 Defender portal om SecOps-postvakken te configureren in het geavanceerde bezorgingsbeleid</span><span class="sxs-lookup"><span data-stu-id="af435-142">Use the Microsoft 365 Defender portal to configure SecOps mailboxes in the advanced delivery policy</span></span>

1. <span data-ttu-id="af435-143">Ga in Microsoft 365 Defender portal naar **E-mail & samenwerkingsbeleid** & pagina Regels \>  \> **bedreigingsbeleid** sectie Regels \>  \> **Geavanceerde bezorging**.</span><span class="sxs-lookup"><span data-stu-id="af435-143">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Rules** section \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="af435-144">Controleer op **de pagina** Geavanceerde bezorging of het **tabblad SecOps-postvak** is geselecteerd en ga vervolgens op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="af435-144">On the **Advanced delivery** page, verify that the **SecOps mailbox** tab is selected, and then do one of the following steps:</span></span>
   - <span data-ttu-id="af435-145">Klik ![ op Pictogram Bewerken ](../../media/m365-cc-sc-edit-icon.png) **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="af435-145">Click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span>
   - <span data-ttu-id="af435-146">Als er geen geconfigureerde phishingsimulaties zijn, klikt u op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="af435-146">If there are no configured phishing simulations, click **Add**.</span></span>

3. <span data-ttu-id="af435-147">Voer in **het flyout SecOps-postvakken** bewerken dat wordt geopend een bestaand Exchange Online-postvak in dat u wilt aanwijzen als SecOps-postvak door een van de volgende stappen uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="af435-147">On the **Edit SecOps mailboxes** flyout that opens, enter an existing Exchange Online mailbox that you want to designate as SecOps mailbox by doing one of the following steps:</span></span>
   - <span data-ttu-id="af435-148">Klik in het vak, laat de lijst met postvakken oplossen en selecteer het postvak.</span><span class="sxs-lookup"><span data-stu-id="af435-148">Click in the box, let the list of mailboxes resolve, and then select the mailbox.</span></span>
   - <span data-ttu-id="af435-149">Klik in het vak om een id voor het postvak te typen (naam, weergavenaam, alias, e-mailadres, accountnaam, enzovoort) en selecteer het postvak (weergavenaam) in de resultaten.</span><span class="sxs-lookup"><span data-stu-id="af435-149">Click in the box start typing an identifier for the mailbox (name, display name, alias, email address, account name, etc.), and select the mailbox (display name) from the results.</span></span>

     <span data-ttu-id="af435-150">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="af435-150">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="af435-151">Distributiegroepen zijn niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="af435-151">Distribution groups are not allowed.</span></span>

     <span data-ttu-id="af435-152">Als u een bestaande waarde wilt verwijderen, klikt u op verwijderen</span><span class="sxs-lookup"><span data-stu-id="af435-152">To remove an existing value, click remove</span></span> ![Pictogram Verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="af435-154">naast de waarde.</span><span class="sxs-lookup"><span data-stu-id="af435-154">next to the value.</span></span>

4. <span data-ttu-id="af435-155">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="af435-155">When you're finished, click **Save**.</span></span>

<span data-ttu-id="af435-156">De secops-postvakinzendingen die u hebt geconfigureerd, worden weergegeven op het **tabblad SecOps-postvak.** Als u wijzigingen wilt aanbrengen, klikt ![ u op Het tabblad ](../../media/m365-cc-sc-edit-icon.png) **bewerken** op Pictogram Bewerken.</span><span class="sxs-lookup"><span data-stu-id="af435-156">The SecOps mailbox entries that you configured are displayed on the **SecOps mailbox** tab. To make changes, click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit** on the tab.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="af435-157">Gebruik de Microsoft 365 Defender portal om phishingsimulaties van derden te configureren in het beleid voor geavanceerde bezorging</span><span class="sxs-lookup"><span data-stu-id="af435-157">Use the Microsoft 365 Defender portal to configure third-party phishing simulations in the advanced delivery policy</span></span>

1. <span data-ttu-id="af435-158">Ga in Microsoft 365 Defender portal naar **E-mail & samenwerkingsbeleid** & pagina Regels \>  \> **bedreigingsbeleid** sectie Regels \>  \> **Geavanceerde bezorging**.</span><span class="sxs-lookup"><span data-stu-id="af435-158">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Rules** section \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="af435-159">Selecteer op **de pagina** Geavanceerde bezorging het **tabblad Phishingsimulatie** en ga vervolgens op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="af435-159">On the **Advanced delivery** page, select the **Phishing simulation** tab, and then do one of the following steps:</span></span>
   - <span data-ttu-id="af435-160">Klik ![ op Pictogram Bewerken ](../../media/m365-cc-sc-edit-icon.png) **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="af435-160">Click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span>
   - <span data-ttu-id="af435-161">Als er geen geconfigureerde phishingsimulaties zijn, klikt u op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="af435-161">If there are no configured phishing simulations, click **Add**.</span></span>

3. <span data-ttu-id="af435-162">Configureer de volgende instellingen in het flyout **phishingsimulatie** van derden bewerken dat wordt geopend:</span><span class="sxs-lookup"><span data-stu-id="af435-162">On the **Edit third-party phishing simulation** flyout that opens, configure the following settings:</span></span>

   - <span data-ttu-id="af435-163">**Domein** verzenden: Vouw deze instelling uit en voer ten minste één e-mailadresdomein in (bijvoorbeeld contoso.com) door in het vak te klikken, een waarde in te voeren en vervolgens op Enter te drukken of de waarde te selecteren die onder het vak wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="af435-163">**Sending domain**: Expand this setting and enter at least one email address domain (for example, contoso.com) by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="af435-164">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="af435-164">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="af435-165">U kunt maximaal tien items toevoegen.</span><span class="sxs-lookup"><span data-stu-id="af435-165">You can add up to 10 entries.</span></span>
   - <span data-ttu-id="af435-166">**IP verzenden:** Vouw deze instelling uit en voer ten minste één geldig IPv4-adres in door in het vak te klikken, een waarde in te voeren en vervolgens op Enter te drukken of de waarde te selecteren die onder het vak wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="af435-166">**Sending IP**: Expand this setting and enter at least one valid IPv4 address is required by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="af435-167">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="af435-167">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="af435-168">U kunt maximaal tien items toevoegen.</span><span class="sxs-lookup"><span data-stu-id="af435-168">You can add up to 10 entries.</span></span> <span data-ttu-id="af435-169">Geldige waarden zijn:</span><span class="sxs-lookup"><span data-stu-id="af435-169">Valid values are:</span></span>
     - <span data-ttu-id="af435-170">Enkel IP: bijvoorbeeld 192.168.1.1.</span><span class="sxs-lookup"><span data-stu-id="af435-170">Single IP: For example, 192.168.1.1.</span></span>
     - <span data-ttu-id="af435-171">IP-bereik: bijvoorbeeld 192.168.0.1-192.168.0.254.</span><span class="sxs-lookup"><span data-stu-id="af435-171">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
     - <span data-ttu-id="af435-172">CIDR IP: Bijvoorbeeld 192.168.0.1/25.</span><span class="sxs-lookup"><span data-stu-id="af435-172">CIDR IP: For example, 192.168.0.1/25.</span></span>
   - <span data-ttu-id="af435-173">**Url's** voor simulaties om dit mogelijk te maken: Vouw deze instelling uit en voer desgewenst specifieke URL's in die deel uitmaken van uw phishingsimulatiecampagne die niet mogen worden geblokkeerd of gedetoneerd door in het vak te klikken, een waarde in te voeren en vervolgens op Enter te drukken of de waarde te selecteren die onder het vak wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="af435-173">**Simulation URLs to allow**: Expand this setting and optionally enter specific URLs that are part of your phishing simulation campaign that should not be blocked or detonated by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="af435-174">U kunt maximaal tien items toevoegen.</span><span class="sxs-lookup"><span data-stu-id="af435-174">You can add up to 10 entries.</span></span>

   <span data-ttu-id="af435-175">Als u een bestaande waarde wilt verwijderen, klikt u op verwijderen</span><span class="sxs-lookup"><span data-stu-id="af435-175">To remove an existing value, click remove</span></span> ![Pictogram Verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="af435-177">naast de waarde.</span><span class="sxs-lookup"><span data-stu-id="af435-177">next to the value.</span></span>

4. <span data-ttu-id="af435-178">Wanneer u klaar bent, gaat u op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="af435-178">When you're finished, do one of the following steps:</span></span>
   - <span data-ttu-id="af435-179">**Eerste keer:** Klik **op Toevoegen** en klik vervolgens op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="af435-179">**First time**: Click **Add**, and then click **Close**.</span></span>
   - <span data-ttu-id="af435-180">**Bestaand bewerken:** Klik **op Opslaan** en klik vervolgens op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="af435-180">**Edit existing**: Click **Save** and then click **Close**.</span></span>

<span data-ttu-id="af435-181">De phishingsimulatiegegevens van derden die u hebt geconfigureerd, worden weergegeven op het **tabblad Phishingsimulatie.** Als u wijzigingen wilt aanbrengen, klikt ![ u op Het tabblad ](../../media/m365-cc-sc-edit-icon.png) **bewerken** op Pictogram Bewerken.</span><span class="sxs-lookup"><span data-stu-id="af435-181">The third-party phishing simulation entries that you configured are displayed on the **Phishing simulation** tab. To make changes, click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit** on the tab.</span></span>

## <a name="additional-scenarios-that-require-filtering-bypass"></a><span data-ttu-id="af435-182">Extra scenario's waarvoor filteren moet worden omzeild</span><span class="sxs-lookup"><span data-stu-id="af435-182">Additional scenarios that require filtering bypass</span></span>

<span data-ttu-id="af435-183">Naast de twee scenario's waar het geavanceerde bezorgingsbeleid u bij kan helpen, zijn er andere scenario's waarvoor het filteren mogelijk moet worden overgeslagen:</span><span class="sxs-lookup"><span data-stu-id="af435-183">In addition to the two scenarios that the advanced delivery policy can help you with, there are other scenarios that might require you bypass filtering:</span></span>

- <span data-ttu-id="af435-184">**Filters van derden:** Als de MX-record  van uw domein niet naar Office 365 (berichten worden eerst ergens anders gerouteerd), is beveiliging standaard niet [](secure-by-default.md) *beschikbaar.*</span><span class="sxs-lookup"><span data-stu-id="af435-184">**Third-party filters**: If your domain's MX record *doesn't* point to Office 365 (messages are routed somewhere else first), [secure by default](secure-by-default.md) *is not available*.</span></span> <span data-ttu-id="af435-185">Als u bescherming wilt toevoegen, moet u Verbeterde filtering voor connectors (ook wel skip listing genoemd) *inschakelen.*</span><span class="sxs-lookup"><span data-stu-id="af435-185">If you'd like to add protection, you'll need to enable Enhanced Filtering for Connectors (also known as *skip listing*).</span></span> <span data-ttu-id="af435-186">Zie E-mailstroom beheren met [een externe cloudservice](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud)met Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="af435-186">For more information, see [Manage mail flow using a third-party cloud service with Exchange Online](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud).</span></span> <span data-ttu-id="af435-187">Als u geen uitgebreide filtering voor connectors wilt gebruiken, gebruikt u regels voor e-mailstroom (ook wel transportregels genoemd) om Microsoft-filtering te omzeilen voor berichten die al zijn geëvalueerd door filtering van derden.</span><span class="sxs-lookup"><span data-stu-id="af435-187">If you don't want Enhanced Filtering for Connectors,use mail flow rules (also known as transport rules) to bypass Microsoft filtering for messages that have already been evaluated by third-party filtering.</span></span> <span data-ttu-id="af435-188">Zie E-mailstroomregels gebruiken om de SCL in berichten [in te stellen voor meer informatie.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md)</span><span class="sxs-lookup"><span data-stu-id="af435-188">For more information, see [Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md).</span></span>

- <span data-ttu-id="af435-189">**False positives under review**: U wilt mogelijk bepaalde berichten die nog steeds door Microsoft worden geanalyseerd [via](admin-submission.md) beheerdersinzendingen tijdelijk toestaan om bekende goede berichten te melden die ten onrechte als slecht worden gemarkeerd voor Microsoft (false positives).</span><span class="sxs-lookup"><span data-stu-id="af435-189">**False positives under review**: You might want to temporarily allow certain messages that are still being analyzed by Microsoft via [admin submissions](admin-submission.md) to report known good messages that are incorrectly being marked as bad to Microsoft (false positives).</span></span> <span data-ttu-id="af435-190">Net als bij alle \*\*\*\* overschrijvingen wordt ten zeerste aanbevolen dat deze vergoedingen tijdelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="af435-190">As with all overrides, we **_highly recommended_** that these allowances are temporary.</span></span>

## <a name="exchange-online-powershell-procedures-for-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="af435-191">Exchange Online PowerShell-procedures voor SecOps-postvakken in het beleid voor geavanceerde bezorging</span><span class="sxs-lookup"><span data-stu-id="af435-191">Exchange Online PowerShell procedures for SecOps mailboxes in the advanced delivery policy</span></span>

<span data-ttu-id="af435-192">In Exchange Online PowerShell zijn de basiselementen van SecOps-postvakken in het geavanceerde bezorgingsbeleid:</span><span class="sxs-lookup"><span data-stu-id="af435-192">In Exchange Online PowerShell, the basic elements of SecOps mailboxes in the advanced delivery policy are:</span></span>

- <span data-ttu-id="af435-193">**Het SecOps-beleid overschrijven:** beheerd door **\* de cmdlets -SecOpsOverridePolicy.**</span><span class="sxs-lookup"><span data-stu-id="af435-193">**The SecOps override policy**: Controlled by the **\*-SecOpsOverridePolicy** cmdlets.</span></span>
- <span data-ttu-id="af435-194">**De secops-overschrijvenregel:** wordt beheerd door **\* de cmdlets -SecOpsOverrideRuleRule.**</span><span class="sxs-lookup"><span data-stu-id="af435-194">**The SecOps override rule**: Controlled by the **\*-SecOpsOverrideRule** cmdlets.</span></span>

<span data-ttu-id="af435-195">Dit gedrag heeft de volgende resultaten:</span><span class="sxs-lookup"><span data-stu-id="af435-195">This behavior has the following results:</span></span>

- <span data-ttu-id="af435-196">U maakt eerst het beleid en vervolgens maakt u de regel die het beleid aangeeft waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="af435-196">You create the policy first, then you create the rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="af435-197">Wanneer u een beleid uit PowerShell verwijdert, wordt de bijbehorende regel ook verwijderd.</span><span class="sxs-lookup"><span data-stu-id="af435-197">When you remove a policy from PowerShell, the corresponding rule is also removed.</span></span>
- <span data-ttu-id="af435-198">Wanneer u een regel uit PowerShell verwijdert, wordt het bijbehorende beleid niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="af435-198">When you remove a rule from PowerShell, the corresponding policy is not removed.</span></span> <span data-ttu-id="af435-199">U moet het bijbehorende beleid handmatig verwijderen.</span><span class="sxs-lookup"><span data-stu-id="af435-199">You need to remove the corresponding policy manually.</span></span>

### <a name="use-powershell-to-configure-secops-mailboxes"></a><span data-ttu-id="af435-200">PowerShell gebruiken om SecOps-postvakken te configureren</span><span class="sxs-lookup"><span data-stu-id="af435-200">Use PowerShell to configure SecOps mailboxes</span></span>

<span data-ttu-id="af435-201">Het configureren van een SecOps-postvak in het geavanceerde bezorgingsbeleid in PowerShell is een proces in twee stappen:</span><span class="sxs-lookup"><span data-stu-id="af435-201">Configuring a SecOps mailbox in the advanced delivery policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="af435-202">Het secops-overschrijvenbeleid maken.</span><span class="sxs-lookup"><span data-stu-id="af435-202">Create the SecOps override policy.</span></span>
2. <span data-ttu-id="af435-203">Maak de SecOps-overschrijvenregel die het beleid aangeeft waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="af435-203">Create the SecOps override rule that specifies the policy that the rule applies to.</span></span>

#### <a name="step-1-use-powershell-to-create-the-secops-override-policy"></a><span data-ttu-id="af435-204">Stap 1: PowerShell gebruiken om het secops-overschrijvenbeleid te maken</span><span class="sxs-lookup"><span data-stu-id="af435-204">Step 1: Use PowerShell to create the SecOps override policy</span></span>

<span data-ttu-id="af435-205">Als u het secops-overschrijvenbeleid wilt maken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="af435-205">To create the SecOps override policy, use the following syntax:</span></span>

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>
```

<span data-ttu-id="af435-206">**Opmerking:** Ongeacht de naam die u opgeeft, is de naam van het beleid SecOpsOverridePolicy, dus u kunt die waarde net zo goed gebruiken.</span><span class="sxs-lookup"><span data-stu-id="af435-206">**Note**: Regardless of the Name value you specify, the policy name will be SecOpsOverridePolicy, so you might as well use that value.</span></span>

<span data-ttu-id="af435-207">In dit voorbeeld wordt het secops-postvakbeleid gemaakt.</span><span class="sxs-lookup"><span data-stu-id="af435-207">This example creates the SecOps mailbox policy.</span></span>

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo secops@contoso.com
```

<span data-ttu-id="af435-208">Zie [New-SecOpsOverridePolicy (Nieuw-SecOpsOverridePolicy)](/powershell/module/exchange/new-secopsoverridepolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="af435-208">For detailed syntax and parameter information, see [New-SecOpsOverridePolicy](/powershell/module/exchange/new-secopsoverridepolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-the-secops-override-rule"></a><span data-ttu-id="af435-209">Stap 2: PowerShell gebruiken om de secops-overschrijvenregel te maken</span><span class="sxs-lookup"><span data-stu-id="af435-209">Step 2: Use PowerShell to create the SecOps override rule</span></span>

<span data-ttu-id="af435-210">In dit voorbeeld wordt de regel SecOps-postvak gemaakt met de opgegeven instellingen.</span><span class="sxs-lookup"><span data-stu-id="af435-210">This example creates the SecOps mailbox rule with the specified settings.</span></span>

```powershell
New-SecOpsOverrideRule -Name SecOpsOverrideRule -Policy SecOpsOverridePolicy
```

<span data-ttu-id="af435-211">\*\*Opmerking:\*\*\*\*Ongeacht de waarde Naam die u opgeeft, is de regelnaam SecOpsOverrideRule waar een unieke \<GUID\> \<GUID\> GUID-waarde is (bijvoorbeeld 6fed4b63-3563-495d-a481-b24a311f8329).</span><span class="sxs-lookup"><span data-stu-id="af435-211">**Note**: \*\*Regardless of the Name value you specify, the rule name will be SecOpsOverrideRule\<GUID\> where \<GUID\> is a unique GUID value (for example, 6fed4b63-3563-495d-a481-b24a311f8329).</span></span>

<span data-ttu-id="af435-212">Zie [New-SecOpsOverrideRule voor](/powershell/module/exchange/new-secopsoverriderule)gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="af435-212">For detailed syntax and parameter information, see [New-SecOpsOverrideRule](/powershell/module/exchange/new-secopsoverriderule).</span></span>

### <a name="use-powershell-to-view-the-secops-override-policy"></a><span data-ttu-id="af435-213">PowerShell gebruiken om het beleid voor secops-overschrijven weer te geven</span><span class="sxs-lookup"><span data-stu-id="af435-213">Use PowerShell to view the SecOps override policy</span></span>

<span data-ttu-id="af435-214">Dit voorbeeld retourneert gedetailleerde informatie over het ene en alleen secops-postvakbeleid.</span><span class="sxs-lookup"><span data-stu-id="af435-214">This example returns detailed information about the one and only SecOps mailbox policy.</span></span>

```powershell
Get-SecOpsOverridePolicy
```

<span data-ttu-id="af435-215">Zie [Get-SecOpsOverridePolicy (Get-SecOpsOverridePolicy)](/powershell/module/exchange/get-secopsoverridepolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="af435-215">For detailed syntax and parameter information, see [Get-SecOpsOverridePolicy](/powershell/module/exchange/get-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-view-secops-override-rules"></a><span data-ttu-id="af435-216">PowerShell gebruiken om regels voor secops-overschrijven weer te geven</span><span class="sxs-lookup"><span data-stu-id="af435-216">Use PowerShell to view SecOps override rules</span></span>

<span data-ttu-id="af435-217">Dit voorbeeld retourneert gedetailleerde informatie over secops-regels die regels overschrijven.</span><span class="sxs-lookup"><span data-stu-id="af435-217">This example returns detailed information about SecOps override rules.</span></span>

```powershell
Get-SecOpsOverrideRule
```

<span data-ttu-id="af435-218">Hoewel de vorige opdracht slechts één regel moet retourneren, kunnen regels die in behandeling zijn voor verwijdering, ook worden opgenomen in de resultaten.</span><span class="sxs-lookup"><span data-stu-id="af435-218">Although the previous command should return only one rule, any rules that are pending deletion might also be included in the results.</span></span>

<span data-ttu-id="af435-219">In dit voorbeeld worden de geldige regel (één) en eventuele ongeldige regels geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="af435-219">This example identifies the valid rule (one) and any invalid rules.</span></span>

```powershell
Get-SecOpsOverrideRule | Format-Table Name,Mode
```

<span data-ttu-id="af435-220">Nadat u de ongeldige regels hebt opgegeven, kunt u deze verwijderen met de cmdlet **Remove-SecOpsOverrideRule,** zoals [verderop in dit artikel wordt beschreven.](#use-powershell-to-remove-secops-override-rules)</span><span class="sxs-lookup"><span data-stu-id="af435-220">After you identify the invalid rules, you can remove them by using the **Remove-SecOpsOverrideRule** cmdlet as described [later in this article](#use-powershell-to-remove-secops-override-rules).</span></span>

<span data-ttu-id="af435-221">Zie [Get-SecOpsOverrideRule (Get-SecOpsOverrideRule)](/powershell/module/exchange/get-secopsoverriderule) voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="af435-221">For detailed syntax and parameter information, see [Get-SecOpsOverrideRule](/powershell/module/exchange/get-secopsoverriderule)</span></span>

### <a name="use-powershell-to-modify-the-secops-override-policy"></a><span data-ttu-id="af435-222">PowerShell gebruiken om het secops-overschrijvenbeleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="af435-222">Use PowerShell to modify the SecOps override policy</span></span>

<span data-ttu-id="af435-223">Gebruik de volgende syntaxis om het secops-overschrijvenbeleid te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="af435-223">To modify the SecOps override policy, use the following syntax:</span></span>

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy [-AddSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>] [-RemoveSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>]
```

<span data-ttu-id="af435-224">In dit voorbeeld worden secops2@contoso.com toegevoegd aan het secops-overschrijvenbeleid.</span><span class="sxs-lookup"><span data-stu-id="af435-224">This example adds secops2@contoso.com to the SecOps override policy.</span></span>

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy -AddSentTo secops2@contoso.com
```

<span data-ttu-id="af435-225">**Opmerking:** Als er een bijbehorende, geldige SecOps-overschrijvenregel bestaat, worden de e-mailadressen in de regel ook bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="af435-225">**Note**: If an associated, valid SecOps override rule exists, the email addresses in the rule will also be updated.</span></span>

<span data-ttu-id="af435-226">Zie [Set-SecOpsOverridePolicy](/powershell/module/exchange/set-secopsoverridepolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="af435-226">For detailed syntax and parameter information, see [Set-SecOpsOverridePolicy](/powershell/module/exchange/set-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-modify-a-secops-override-rule"></a><span data-ttu-id="af435-227">PowerShell gebruiken om een SecOps-overschrijvenregel te wijzigen</span><span class="sxs-lookup"><span data-stu-id="af435-227">Use PowerShell to modify a SecOps override rule</span></span>

<span data-ttu-id="af435-228">De **cmdlet Set-SecOpsOverrideRule** wijzigt de e-mailadressen in de secops-overschrijvenregel niet.</span><span class="sxs-lookup"><span data-stu-id="af435-228">The **Set-SecOpsOverrideRule** cmdlet does not modify the email addresses in the SecOps override rule.</span></span> <span data-ttu-id="af435-229">Als u de e-mailadressen in de secops-overschrijvenregel wilt wijzigen, gebruikt u de cmdlet **Set-SecOpsOverridePolicy.**</span><span class="sxs-lookup"><span data-stu-id="af435-229">To modify the email addresses in the SecOps override rule, use the **Set-SecOpsOverridePolicy** cmdlet.</span></span>

<span data-ttu-id="af435-230">Zie [Set-SecOpsOverrideRule](/powershell/module/exchange/set-secopsoverriderule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="af435-230">For detailed syntax and parameter information, see [Set-SecOpsOverrideRule](/powershell/module/exchange/set-secopsoverriderule).</span></span>

### <a name="use-powershell-to-remove-the-secops-override-policy"></a><span data-ttu-id="af435-231">PowerShell gebruiken om het SecOps-overschrijvenbeleid te verwijderen</span><span class="sxs-lookup"><span data-stu-id="af435-231">Use PowerShell to remove the SecOps override policy</span></span>

<span data-ttu-id="af435-232">In dit voorbeeld worden het secopspostvakbeleid en de bijbehorende regel verwijderd.</span><span class="sxs-lookup"><span data-stu-id="af435-232">This example removes the SecOps Mailbox policy and the corresponding rule.</span></span>

```powershell
Remove-SecOpsOverridePolicy -Identity SecOpsOverridePolicy
```

<span data-ttu-id="af435-233">Zie [Remove-SecOpsOverridePolicy (Verwijderen-SecOpsOverridePolicy)](/powershell/module/exchange/remove-secopsoverridepolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="af435-233">For detailed syntax and parameter information, see [Remove-SecOpsOverridePolicy](/powershell/module/exchange/remove-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-remove-secops-override-rules"></a><span data-ttu-id="af435-234">PowerShell gebruiken om SecOps-regels te verwijderen</span><span class="sxs-lookup"><span data-stu-id="af435-234">Use PowerShell to remove SecOps override rules</span></span>

<span data-ttu-id="af435-235">Als u een secops-overschrijvenregel wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="af435-235">To remove a SecOps override rule, use the following syntax:</span></span>

```powershell
Remove-SecOpsOverrideRule -Identity <RuleIdentity>
```

<span data-ttu-id="af435-236">In dit voorbeeld wordt de opgegeven SecOps-overschrijvenregel verwijderd.</span><span class="sxs-lookup"><span data-stu-id="af435-236">This example removes the specified SecOps override rule.</span></span>

```powershell
Remove-SecOpsOverrideRule -Identity SecOpsOverrideRule6fed4b63-3563-495d-a481-b24a311f8329
```

<span data-ttu-id="af435-237">Zie [Remove-SecOpsOverrideRule voor](/powershell/module/exchange/remove-secopsoverriderule)gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="af435-237">For detailed syntax and parameter information, see [Remove-SecOpsOverrideRule](/powershell/module/exchange/remove-secopsoverriderule).</span></span>

## <a name="exchange-online-powershell-procedures-for-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="af435-238">Exchange Online PowerShell-procedures voor phishingsimulaties van derden in het beleid voor geavanceerde bezorging</span><span class="sxs-lookup"><span data-stu-id="af435-238">Exchange Online PowerShell procedures for third-party phishing simulations in the advanced delivery policy</span></span>

<span data-ttu-id="af435-239">In Exchange Online PowerShell zijn de basiselementen van phishingsimulaties van derden in het geavanceerde bezorgingsbeleid:</span><span class="sxs-lookup"><span data-stu-id="af435-239">In Exchange Online PowerShell, the basic elements of third-party phishing simulations in the advanced delivery policy are:</span></span>

- <span data-ttu-id="af435-240">**De phishingsimulatie overschrijven het beleid:** gecontroleerd door **\* de cmdlets -PhishSimOverridePolicy.**</span><span class="sxs-lookup"><span data-stu-id="af435-240">**The phishing simulation override policy**: Controlled by the **\*-PhishSimOverridePolicy** cmdlets.</span></span>
- <span data-ttu-id="af435-241">**De phishingsimulatie overschrijven regel:** Gecontroleerd door **\* de cmdlets -PhishSimOverrideRule.**</span><span class="sxs-lookup"><span data-stu-id="af435-241">**The phishing simulation override rule**: Controlled by the **\*-PhishSimOverrideRule** cmdlets.</span></span>

<span data-ttu-id="af435-242">Dit gedrag heeft de volgende resultaten:</span><span class="sxs-lookup"><span data-stu-id="af435-242">This behavior has the following results:</span></span>

- <span data-ttu-id="af435-243">U maakt eerst het beleid en vervolgens maakt u de regel die het beleid aangeeft waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="af435-243">You create the policy first, then you create the rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="af435-244">U wijzigt de instellingen in het beleid en de regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="af435-244">You modify the settings in the policy and the rule separately.</span></span>
- <span data-ttu-id="af435-245">Wanneer u een beleid uit PowerShell verwijdert, wordt de bijbehorende regel ook verwijderd.</span><span class="sxs-lookup"><span data-stu-id="af435-245">When you remove a policy from PowerShell, the corresponding rule is also removed.</span></span>
- <span data-ttu-id="af435-246">Wanneer u een regel uit PowerShell verwijdert, wordt het bijbehorende beleid niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="af435-246">When you remove a rule from PowerShell, the corresponding policy is not removed.</span></span> <span data-ttu-id="af435-247">U moet het bijbehorende beleid handmatig verwijderen.</span><span class="sxs-lookup"><span data-stu-id="af435-247">You need to remove the corresponding policy manually.</span></span>

### <a name="use-powershell-to-configure-third-party-phishing-simulations"></a><span data-ttu-id="af435-248">PowerShell gebruiken om phishingsimulaties van derden te configureren</span><span class="sxs-lookup"><span data-stu-id="af435-248">Use PowerShell to configure third-party phishing simulations</span></span>

<span data-ttu-id="af435-249">Het configureren van een phishingsimulatie van derden in het beleid voor geavanceerde bezorging in PowerShell is een proces in twee stappen:</span><span class="sxs-lookup"><span data-stu-id="af435-249">Configuring a third-party phishing simulation in the advanced delivery policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="af435-250">Maak het beleid voor phishingsimulatie.</span><span class="sxs-lookup"><span data-stu-id="af435-250">Create the phishing simulation override policy.</span></span>
2. <span data-ttu-id="af435-251">Maak de overschrijvende regel voor phishingsimulatie die het beleid aangeeft waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="af435-251">Create the phishing simulation override rule that specifies the policy that the rule applies to.</span></span>

#### <a name="step-1-use-powershell-to-create-the-phishing-simulation-override-policy"></a><span data-ttu-id="af435-252">Stap 1: PowerShell gebruiken om het beleid voor phishingsimulatie te overschrijven</span><span class="sxs-lookup"><span data-stu-id="af435-252">Step 1: Use PowerShell to create the phishing simulation override policy</span></span>

<span data-ttu-id="af435-253">In dit voorbeeld wordt het beleid voor phishingsimulatie overschrijven.</span><span class="sxs-lookup"><span data-stu-id="af435-253">This example creates the phishing simulation override policy.</span></span>

```powershell
New-PhishSimOverridePolicy -Name PhishSimOverridePolicy
```

<span data-ttu-id="af435-254">**Opmerking:** Ongeacht de naam die u opgeeft, is de naam van het beleid PhishSimOverridePolicy, dus u kunt deze waarde net zo goed gebruiken.</span><span class="sxs-lookup"><span data-stu-id="af435-254">**Note**: Regardless of the Name value you specify, the policy name will be PhishSimOverridePolicy, so you might as well use that value.</span></span>

<span data-ttu-id="af435-255">Zie [New-PhishSimOverridePolicy (Nieuw-PhishSimOverridePolicy)](/powershell/module/exchange/new-phishsimoverridepolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="af435-255">For detailed syntax and parameter information, see [New-PhishSimOverridePolicy](/powershell/module/exchange/new-phishsimoverridepolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-the-phishing-simulation-override-rule"></a><span data-ttu-id="af435-256">Stap 2: PowerShell gebruiken om de regel voor phishingsimulatie te maken</span><span class="sxs-lookup"><span data-stu-id="af435-256">Step 2: Use PowerShell to create the phishing simulation override rule</span></span>

<span data-ttu-id="af435-257">Gebruik de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="af435-257">Use the following syntax:</span></span>

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs <Domain1>,<Domain2>,...<DomainN> -SenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>
```

<span data-ttu-id="af435-258">Ongeacht de waarde Naam die u opgeeft, is de regelnaam PhishSimOverrideRule waar een unieke \<GUID\> \<GUID\> GUID-waarde is (bijvoorbeeld a0eae53e-d755-4a42-9320-b9c6b55c5011).</span><span class="sxs-lookup"><span data-stu-id="af435-258">Regardless of the Name value you specify, the rule name will be PhishSimOverrideRule\<GUID\> where \<GUID\> is a unique GUID value (for example, a0eae53e-d755-4a42-9320-b9c6b55c5011).</span></span>

<span data-ttu-id="af435-259">Een geldige IP-adresinvoer is een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="af435-259">A valid IP address entry is one of the following values:</span></span>

- <span data-ttu-id="af435-260">Enkel IP: bijvoorbeeld 192.168.1.1.</span><span class="sxs-lookup"><span data-stu-id="af435-260">Single IP: For example, 192.168.1.1.</span></span>
- <span data-ttu-id="af435-261">IP-bereik: bijvoorbeeld 192.168.0.1-192.168.0.254.</span><span class="sxs-lookup"><span data-stu-id="af435-261">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
- <span data-ttu-id="af435-262">CIDR IP: Bijvoorbeeld 192.168.0.1/25.</span><span class="sxs-lookup"><span data-stu-id="af435-262">CIDR IP: For example, 192.168.0.1/25.</span></span>

<span data-ttu-id="af435-263">In dit voorbeeld wordt de regel voor phishingsimulatie met de opgegeven instellingen overschreven.</span><span class="sxs-lookup"><span data-stu-id="af435-263">This example creates the phishing simulation override rule with the specified settings.</span></span>

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs fabrikam.com,wingtiptoys.com -SenderIpRanges 192.168.1.55
```

<span data-ttu-id="af435-264">Zie [New-PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="af435-264">For detailed syntax and parameter information, see [New-PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-view-the-phishing-simulation-override-policy"></a><span data-ttu-id="af435-265">PowerShell gebruiken om het beleid voor phishingsimulaties te bekijken</span><span class="sxs-lookup"><span data-stu-id="af435-265">Use PowerShell to view the phishing simulation override policy</span></span>

<span data-ttu-id="af435-266">Dit voorbeeld retourneert gedetailleerde informatie over de enige phishingsimulatie die beleid overschrijven.</span><span class="sxs-lookup"><span data-stu-id="af435-266">This example returns detailed information about the one and only phishing simulation override policy.</span></span>

```powershell
Get-PhishSimOverridePolicy
```

<span data-ttu-id="af435-267">Zie [Get-PhishSimOverridePolicy (Get-PhishSimOverridePolicy)](/powershell/module/exchange/get-phishsimoverridepolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="af435-267">For detailed syntax and parameter information, see [Get-PhishSimOverridePolicy](/powershell/module/exchange/get-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-view-phishing-simulation-override-rules"></a><span data-ttu-id="af435-268">PowerShell gebruiken om regels voor phishingsimulatie te bekijken</span><span class="sxs-lookup"><span data-stu-id="af435-268">Use PowerShell to view phishing simulation override rules</span></span>

<span data-ttu-id="af435-269">Dit voorbeeld retourneert gedetailleerde informatie over regels voor phishingsimulatie.</span><span class="sxs-lookup"><span data-stu-id="af435-269">This example returns detailed information about phishing simulation override rules.</span></span>

```powershell
Get-PhishSimOverrideRule
```

<span data-ttu-id="af435-270">Hoewel de vorige opdracht slechts één regel moet retourneren, kunnen regels die in behandeling zijn voor verwijdering, ook worden opgenomen in de resultaten.</span><span class="sxs-lookup"><span data-stu-id="af435-270">Although the previous command should return only one rule, any rules that are pending deletion might also be included in the results.</span></span>

<span data-ttu-id="af435-271">In dit voorbeeld worden de geldige regel (één) en eventuele ongeldige regels geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="af435-271">This example identifies the valid rule (one) and any invalid rules.</span></span>

```powershell
Get-PhishSimOverrideRule | Format-Table Name,Mode
```

<span data-ttu-id="af435-272">Nadat u de ongeldige regels hebt opgegeven, kunt u deze verwijderen met de **cmdlet Remove-PhisSimOverrideRule,** [zoals verder wordt beschreven in dit artikel.](#use-powershell-to-remove-phishing-simulation-override-rules)</span><span class="sxs-lookup"><span data-stu-id="af435-272">After you identify the invalid rules, you can remove them by using the **Remove-PhisSimOverrideRule** cmdlet as described [later in this article](#use-powershell-to-remove-phishing-simulation-override-rules).</span></span>

<span data-ttu-id="af435-273">Zie [Get-PhishSimOverrideRule](/powershell/module/exchange/get-phishsimoverriderule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="af435-273">For detailed syntax and parameter information, see [Get-PhishSimOverrideRule](/powershell/module/exchange/get-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-modify-the-phishing-simulation-override-policy"></a><span data-ttu-id="af435-274">PowerShell gebruiken om het beleid voor phishingsimulaties te wijzigen</span><span class="sxs-lookup"><span data-stu-id="af435-274">Use PowerShell to modify the phishing simulation override policy</span></span>

<span data-ttu-id="af435-275">Als u het beleid voor phishingsimulaties wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="af435-275">To modify the phishing simulation override policy, use the following syntax:</span></span>

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy [-Comment "<DescriptiveText>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="af435-276">In dit voorbeeld wordt het beleid voor phishingsimulatie uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="af435-276">This example disables the phishing simulation override policy.</span></span>

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy -Enabled $false
```

<span data-ttu-id="af435-277">Zie [Set-PhishSimOverridePolicy](/powershell/module/exchange/set-phishsimoverridepolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="af435-277">For detailed syntax and parameter information, see [Set-PhishSimOverridePolicy](/powershell/module/exchange/set-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-modify-a-phishing-simulation-override-rule"></a><span data-ttu-id="af435-278">PowerShell gebruiken om een phishingsimulatieregel te wijzigen</span><span class="sxs-lookup"><span data-stu-id="af435-278">Use PowerShell to modify a phishing simulation override rule</span></span>

<span data-ttu-id="af435-279">Als u de regel voor phishingsimulaties wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="af435-279">To modify the phishing simulation override rule, use the following syntax:</span></span>

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 [-Comment "<DescriptiveText>"] [-AddSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-RemoveSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-AddSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>] [-RemoveSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>]
```

<span data-ttu-id="af435-280">In dit voorbeeld wijzigt u de opgegeven phishingsimulatieregel met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="af435-280">This example modifies the specified phishing simulation override rule with the following settings:</span></span>

- <span data-ttu-id="af435-281">Voeg de domeininvoer blueyonderairlines.com.</span><span class="sxs-lookup"><span data-stu-id="af435-281">Add the domain entry blueyonderairlines.com.</span></span>
- <span data-ttu-id="af435-282">Verwijder de IP-adresinvoer 192.168.1.55.</span><span class="sxs-lookup"><span data-stu-id="af435-282">Remove the IP address entry 192.168.1.55.</span></span>

<span data-ttu-id="af435-283">Houd er rekening mee dat deze wijzigingen geen invloed hebben op bestaande vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="af435-283">Note that these changes don't affect existing entries.</span></span>

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 -AddSenderDomainIs blueyonderairlines.com -RemoveSenderIpRanges 192.168.1.55
```

<span data-ttu-id="af435-284">Zie [Set-PhishSimOverrideRule](/powershell/module/exchange/set-phishsimoverriderule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="af435-284">For detailed syntax and parameter information, see [Set-PhishSimOverrideRule](/powershell/module/exchange/set-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-remove-a-phishing-simulation-override-policy"></a><span data-ttu-id="af435-285">PowerShell gebruiken om een beleid voor phishingsimulatie te verwijderen</span><span class="sxs-lookup"><span data-stu-id="af435-285">Use PowerShell to remove a phishing simulation override policy</span></span>

<span data-ttu-id="af435-286">In dit voorbeeld worden het phishingsimulatiebeleid en de bijbehorende regel verwijderd.</span><span class="sxs-lookup"><span data-stu-id="af435-286">This example removes the phishing simulation override policy and the corresponding rule.</span></span>

```powershell
Remove-PhishSimOverridePolicy -Identity PhishSimOverridePolicy
```

<span data-ttu-id="af435-287">Zie [Remove-PhishSimOverridePolicy (Verwijderen-PhishSimOverridePolicy)](/powershell/module/exchange/remove-phishsimoverridepolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="af435-287">For detailed syntax and parameter information, see [Remove-PhishSimOverridePolicy](/powershell/module/exchange/remove-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-remove-phishing-simulation-override-rules"></a><span data-ttu-id="af435-288">PowerShell gebruiken om regels voor phishingsimulatie te verwijderen</span><span class="sxs-lookup"><span data-stu-id="af435-288">Use PowerShell to remove phishing simulation override rules</span></span>

<span data-ttu-id="af435-289">Als u een phishingsimulatieregel wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="af435-289">To remove a phishing simulation override rule, use the following syntax:</span></span>

```powershell
Remove-PhishSimOverrideRule -Identity <RuleIdentity>
```

<span data-ttu-id="af435-290">In dit voorbeeld wordt de opgegeven regel voor phishingsimulatie verwijderd.</span><span class="sxs-lookup"><span data-stu-id="af435-290">This example removes the specified phishing simulation override rule.</span></span>

```powershell
Remove-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011
```

<span data-ttu-id="af435-291">Zie [Remove-PhishSimOverrideRule voor](/powershell/module/exchange/remove-phishsimoverriderule)gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="af435-291">For detailed syntax and parameter information, see [Remove-PhishSimOverrideRule](/powershell/module/exchange/remove-phishsimoverriderule).</span></span>
