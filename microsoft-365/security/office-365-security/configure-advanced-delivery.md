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
ms.openlocfilehash: b989b11739b5418ad14e147f76dde0e0dd7b1b1a
ms.sourcegitcommit: 233989a02a3fc6db33c995ad06b1f820f08f8f0a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53383448"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a><span data-ttu-id="d2320-103">De bezorging van phishingsimulaties van derden configureren voor gebruikers en ongefilterde berichten in SecOps-postvakken</span><span class="sxs-lookup"><span data-stu-id="d2320-103">Configure the delivery of third-party phishing simulations to users and unfiltered messages to SecOps mailboxes</span></span>

<span data-ttu-id="d2320-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="d2320-104">**Applies to**</span></span>
- [<span data-ttu-id="d2320-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d2320-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d2320-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="d2320-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="d2320-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d2320-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="d2320-108">De functie die in dit artikel wordt beschreven, is in Preview, is niet voor iedereen beschikbaar en kan worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="d2320-108">The feature that's described in this article is in Preview, isn't available to everyone, and is subject to change.</span></span>

<span data-ttu-id="d2320-109">Als u uw organisatie standaard veilig wilt [houden,](secure-by-default.md)staat Exchange Online Protection (EOP) geen veilige lijsten of filtering bypass toe voor berichten die zijn geïdentificeerd als malware of phishing met een hoog vertrouwen.</span><span class="sxs-lookup"><span data-stu-id="d2320-109">To keep your organization [secure by default](secure-by-default.md), Exchange Online Protection (EOP) does not allow safe lists or filtering bypass for messages that are identified as malware or high confidence phishing.</span></span> <span data-ttu-id="d2320-110">Er zijn echter specifieke scenario's waarvoor niet-gefilterde berichten moeten worden bezorgd.</span><span class="sxs-lookup"><span data-stu-id="d2320-110">But, there are specific scenarios that require the delivery of unfiltered messages.</span></span> <span data-ttu-id="d2320-111">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="d2320-111">For example:</span></span>

- <span data-ttu-id="d2320-112">**Phishingsimulaties** van derden: Gesimuleerde aanvallen kunnen u helpen om kwetsbare gebruikers te identificeren voordat een echte aanval van invloed is op uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d2320-112">**Third-party phishing simulations**: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="d2320-113">**Postvakken voor beveiligingsbewerkingen (SecOps)**: Speciale postvakken die door beveiligingsteams worden gebruikt om ongefilterde berichten te verzamelen en te analyseren (zowel goed als slecht).</span><span class="sxs-lookup"><span data-stu-id="d2320-113">**Security operations (SecOps) mailboxes**: Dedicated mailboxes that are used by security teams to collect and analyze unfiltered messages (both good and bad).</span></span>

<span data-ttu-id="d2320-114">U gebruikt het _geavanceerde bezorgingsbeleid_ in Microsoft 365 om te voorkomen dat deze berichten _in_ deze specifieke scenario's worden gefilterd. <sup>\*</sup> Het geavanceerde bezorgingsbeleid zorgt ervoor dat berichten in deze scenario's de volgende resultaten bereiken:</span><span class="sxs-lookup"><span data-stu-id="d2320-114">You use the _advanced delivery policy_ in Microsoft 365 to prevent these messages _in these specific scenarios_ from being filtered.<sup>\*</sup> The advanced delivery policy ensures that messages in these scenarios achieve the following results:</span></span>

- <span data-ttu-id="d2320-115">Filters in EOP en Microsoft Defender voor Office 365 actie ondernemen op deze berichten.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d2320-115">Filters in EOP and Microsoft Defender for Office 365 take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="d2320-116">[Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) voor spam en phishing onderneemt geen actie op deze berichten.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d2320-116">[Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) for spam and phishing take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="d2320-117">[Standaardsysteemwaarschuwingen](alerts.md) worden niet geactiveerd voor deze scenario's.</span><span class="sxs-lookup"><span data-stu-id="d2320-117">[Default system alerts](alerts.md) aren't triggered for these scenarios.</span></span>
- <span data-ttu-id="d2320-118">[Air en clustering in Defender voor Office 365](office-365-air.md) negeert deze berichten.</span><span class="sxs-lookup"><span data-stu-id="d2320-118">[AIR and clustering in Defender for Office 365](office-365-air.md) ignores these messages.</span></span>
- <span data-ttu-id="d2320-119">Specifiek voor phishingsimulaties van derden:</span><span class="sxs-lookup"><span data-stu-id="d2320-119">Specifically for third-party phishing simulations:</span></span>
  - <span data-ttu-id="d2320-120">[Beheerdersinzendingen genereren](admin-submission.md) een automatisch antwoord met de melding dat het bericht deel uitmaakt van een phishingsimulatiecampagne en geen echte bedreiging is.</span><span class="sxs-lookup"><span data-stu-id="d2320-120">[Admin submissions](admin-submission.md) generates an automatic response saying that the message is part of a phishing simulation campaign and isn't a real threat.</span></span> <span data-ttu-id="d2320-121">Waarschuwingen en AIR worden niet geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="d2320-121">Alerts and AIR will not be triggered.</span></span>
  - <span data-ttu-id="d2320-122">[Safe Koppelingen in Defender voor Office 365](safe-links.md) worden de specifiek geïdentificeerde URL's in deze berichten niet geblokkeerd of tot ontploffing gebracht.</span><span class="sxs-lookup"><span data-stu-id="d2320-122">[Safe Links in Defender for Office 365](safe-links.md) doesn't block or detonate the specifically identified URLs in these messages.</span></span>
  - <span data-ttu-id="d2320-123">[Safe bijlagen in Defender voor Office 365](safe-attachments.md) worden bijlagen in deze berichten niet tot ontploffing brengen.</span><span class="sxs-lookup"><span data-stu-id="d2320-123">[Safe Attachments in Defender for Office 365](safe-attachments.md) doesn't detonate attachments in these messages.</span></span>

<span data-ttu-id="d2320-124"><sup>\*</sup> U kunt malwarefilters of ZAP voor malware niet omzeilen.</span><span class="sxs-lookup"><span data-stu-id="d2320-124"><sup>\*</sup> You can't bypass malware filtering or ZAP for malware.</span></span>

<span data-ttu-id="d2320-125">Berichten die worden geïdentificeerd door het geavanceerde bezorgingsbeleid zijn geen beveiligingsrisico's, dus de berichten worden gemarkeerd als systeem overschrijven.</span><span class="sxs-lookup"><span data-stu-id="d2320-125">Messages that are identified by the advanced delivery policy aren't security threats, so the messages are marked as system overrides.</span></span> <span data-ttu-id="d2320-126">Beheerders kunnen deze systeem overschrijven en analyseren in de volgende ervaringen:</span><span class="sxs-lookup"><span data-stu-id="d2320-126">Admins can filter and analyze these system overrides in the following experiences:</span></span>

- [<span data-ttu-id="d2320-127">Threat Explorer/Real-time detecties in Defender voor Office 365 plan 2</span><span class="sxs-lookup"><span data-stu-id="d2320-127">Threat Explorer/Real-time detections in Defender for Office 365 plan 2</span></span>](threat-explorer.md)
- <span data-ttu-id="d2320-128">De [pagina E-mailentiteit in Threat Explorer/Realtime detecties](mdo-email-entity-page.md)</span><span class="sxs-lookup"><span data-stu-id="d2320-128">The [Email entity Page in Threat Explorer/Real-time detections](mdo-email-entity-page.md)</span></span>
- <span data-ttu-id="d2320-129">Het [rapport Status van bedreigingsbeveiliging](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="d2320-129">The [Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span>
- [<span data-ttu-id="d2320-130">Advanced hunting in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d2320-130">Advanced hunting in Microsoft Defender for Endpoint</span></span>](../defender-endpoint/advanced-hunting-overview.md)
- [<span data-ttu-id="d2320-131">Campagneweergaven</span><span class="sxs-lookup"><span data-stu-id="d2320-131">Campaign Views</span></span>](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d2320-132">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="d2320-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d2320-133">U opent de Microsoft 365 Defender-portal bij <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="d2320-133">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="d2320-134">Als u rechtstreeks naar de pagina **Geavanceerde bezorging wilt** gaan, opent u <https://security.microsoft.com/advanceddelivery> .</span><span class="sxs-lookup"><span data-stu-id="d2320-134">To go directly to the **Advanced delivery** page, open <https://security.microsoft.com/advanceddelivery>.</span></span>

- <span data-ttu-id="d2320-135">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d2320-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="d2320-136">U moet machtigingen hebben toegewezen voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="d2320-136">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="d2320-137">Als u geconfigureerde instellingen wilt maken, wijzigen of verwijderen in het  geavanceerde bezorgingsbeleid, moet u lid zijn van  de rollengroep Beveiligingsbeheerder in de **Microsoft 365 Defender-portal** en lid zijn van de rollengroep Organisatiebeheer in **Exchange Online.**</span><span class="sxs-lookup"><span data-stu-id="d2320-137">To create, modify, or remove configured settings in the advanced delivery policy, you need to be a member of the **Security Administrator** role group in the **Microsoft 365 Defender portal** and a member of the **Organization Management** role group in **Exchange Online**.</span></span>
  - <span data-ttu-id="d2320-138">Voor alleen-lezen toegang tot het geavanceerde bezorgingsbeleid moet u lid zijn van de rollengroepen **Globale** lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="d2320-138">For read-only access to the advanced delivery policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="d2320-139">Zie Machtigingen [in de](permissions-microsoft-365-security-center.md) Microsoft 365 Defender portal en [Machtigingen in](/exchange/permissions-exo/permissions-exo)Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d2320-139">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > <span data-ttu-id="d2320-140">Gebruikers toevoegen aan de bijbehorende Azure Active Directory functie geeft gebruikers de vereiste machtigingen in de Microsoft 365 Defender _portal_ en machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d2320-140">Adding users to the corresponding Azure Active Directory role gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="d2320-141">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d2320-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="d2320-142">Gebruik de Microsoft 365 Defender portal om SecOps-postvakken te configureren in het geavanceerde bezorgingsbeleid</span><span class="sxs-lookup"><span data-stu-id="d2320-142">Use the Microsoft 365 Defender portal to configure SecOps mailboxes in the advanced delivery policy</span></span>

1. <span data-ttu-id="d2320-143">Ga in Microsoft 365 Defender portal naar **E-mail & samenwerkingsbeleid** & pagina Regels \>  \> **bedreigingsbeleid** sectie Regels \>  \> **Geavanceerde bezorging**.</span><span class="sxs-lookup"><span data-stu-id="d2320-143">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Rules** section \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="d2320-144">Controleer op **de pagina** Geavanceerde bezorging of het **tabblad SecOps-postvak** is geselecteerd en ga vervolgens op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="d2320-144">On the **Advanced delivery** page, verify that the **SecOps mailbox** tab is selected, and then do one of the following steps:</span></span>
   - <span data-ttu-id="d2320-145">Klik ![ op Pictogram Bewerken ](../../media/m365-cc-sc-edit-icon.png) **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="d2320-145">Click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span>
   - <span data-ttu-id="d2320-146">Als er geen geconfigureerde phishingsimulaties zijn, klikt u op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="d2320-146">If there are no configured phishing simulations, click **Add**.</span></span>

3. <span data-ttu-id="d2320-147">Voer in **het flyout SecOps-postvakken** bewerken dat wordt geopend een bestaand Exchange Online-postvak in dat u wilt aanwijzen als SecOps-postvak door een van de volgende stappen uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="d2320-147">On the **Edit SecOps mailboxes** flyout that opens, enter an existing Exchange Online mailbox that you want to designate as SecOps mailbox by doing one of the following steps:</span></span>
   - <span data-ttu-id="d2320-148">Klik in het vak, laat de lijst met postvakken oplossen en selecteer het postvak.</span><span class="sxs-lookup"><span data-stu-id="d2320-148">Click in the box, let the list of mailboxes resolve, and then select the mailbox.</span></span>
   - <span data-ttu-id="d2320-149">Klik in het vak om een id voor het postvak te typen (naam, weergavenaam, alias, e-mailadres, accountnaam, enzovoort) en selecteer het postvak (weergavenaam) in de resultaten.</span><span class="sxs-lookup"><span data-stu-id="d2320-149">Click in the box start typing an identifier for the mailbox (name, display name, alias, email address, account name, etc.), and select the mailbox (display name) from the results.</span></span>

     <span data-ttu-id="d2320-150">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="d2320-150">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="d2320-151">Distributiegroepen zijn niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="d2320-151">Distribution groups are not allowed.</span></span>

     <span data-ttu-id="d2320-152">Als u een bestaande waarde wilt verwijderen, klikt u op verwijderen</span><span class="sxs-lookup"><span data-stu-id="d2320-152">To remove an existing value, click remove</span></span> ![Pictogram Verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="d2320-154">naast de waarde.</span><span class="sxs-lookup"><span data-stu-id="d2320-154">next to the value.</span></span>

4. <span data-ttu-id="d2320-155">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="d2320-155">When you're finished, click **Save**.</span></span>

<span data-ttu-id="d2320-156">De secops-postvakinzendingen die u hebt geconfigureerd, worden weergegeven op het **tabblad SecOps-postvak.** Als u wijzigingen wilt aanbrengen, klikt ![ u op Het tabblad ](../../media/m365-cc-sc-edit-icon.png) **bewerken** op Pictogram Bewerken.</span><span class="sxs-lookup"><span data-stu-id="d2320-156">The SecOps mailbox entries that you configured are displayed on the **SecOps mailbox** tab. To make changes, click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit** on the tab.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="d2320-157">Gebruik de Microsoft 365 Defender portal om phishingsimulaties van derden te configureren in het beleid voor geavanceerde bezorging</span><span class="sxs-lookup"><span data-stu-id="d2320-157">Use the Microsoft 365 Defender portal to configure third-party phishing simulations in the advanced delivery policy</span></span>

1. <span data-ttu-id="d2320-158">Ga in Microsoft 365 Defender portal naar **E-mail & samenwerkingsbeleid** & pagina Regels \>  \> **bedreigingsbeleid** sectie Regels \>  \> **Geavanceerde bezorging**.</span><span class="sxs-lookup"><span data-stu-id="d2320-158">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Rules** section \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="d2320-159">Selecteer op **de pagina** Geavanceerde bezorging het **tabblad Phishingsimulatie** en ga vervolgens op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="d2320-159">On the **Advanced delivery** page, select the **Phishing simulation** tab, and then do one of the following steps:</span></span>
   - <span data-ttu-id="d2320-160">Klik ![ op Pictogram Bewerken ](../../media/m365-cc-sc-edit-icon.png) **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="d2320-160">Click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span>
   - <span data-ttu-id="d2320-161">Als er geen geconfigureerde phishingsimulaties zijn, klikt u op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="d2320-161">If there are no configured phishing simulations, click **Add**.</span></span>

3. <span data-ttu-id="d2320-162">Configureer de volgende instellingen in het flyout **phishingsimulatie** van derden bewerken dat wordt geopend:</span><span class="sxs-lookup"><span data-stu-id="d2320-162">On the **Edit third-party phishing simulation** flyout that opens, configure the following settings:</span></span>

   - <span data-ttu-id="d2320-163">**Domein** verzenden: Vouw deze instelling uit en voer ten minste één e-mailadresdomein in (bijvoorbeeld contoso.com) door in het vak te klikken, een waarde in te voeren en vervolgens op Enter te drukken of de waarde te selecteren die onder het vak wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d2320-163">**Sending domain**: Expand this setting and enter at least one email address domain (for example, contoso.com) by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="d2320-164">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="d2320-164">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="d2320-165">U kunt maximaal tien items toevoegen.</span><span class="sxs-lookup"><span data-stu-id="d2320-165">You can add up to 10 entries.</span></span>
   - <span data-ttu-id="d2320-166">**IP verzenden:** Vouw deze instelling uit en voer ten minste één geldig IPv4-adres in door in het vak te klikken, een waarde in te voeren en vervolgens op Enter te drukken of de waarde te selecteren die onder het vak wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d2320-166">**Sending IP**: Expand this setting and enter at least one valid IPv4 address is required by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="d2320-167">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="d2320-167">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="d2320-168">U kunt maximaal tien items toevoegen.</span><span class="sxs-lookup"><span data-stu-id="d2320-168">You can add up to 10 entries.</span></span> <span data-ttu-id="d2320-169">Geldige waarden zijn:</span><span class="sxs-lookup"><span data-stu-id="d2320-169">Valid values are:</span></span>
     - <span data-ttu-id="d2320-170">Enkel IP: bijvoorbeeld 192.168.1.1.</span><span class="sxs-lookup"><span data-stu-id="d2320-170">Single IP: For example, 192.168.1.1.</span></span>
     - <span data-ttu-id="d2320-171">IP-bereik: bijvoorbeeld 192.168.0.1-192.168.0.254.</span><span class="sxs-lookup"><span data-stu-id="d2320-171">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
     - <span data-ttu-id="d2320-172">CIDR IP: Bijvoorbeeld 192.168.0.1/25.</span><span class="sxs-lookup"><span data-stu-id="d2320-172">CIDR IP: For example, 192.168.0.1/25.</span></span>
   - <span data-ttu-id="d2320-173">**Url's** voor simulaties om dit mogelijk te maken: Vouw deze instelling uit en voer desgewenst specifieke URL's in die deel uitmaken van uw phishingsimulatiecampagne die niet mogen worden geblokkeerd of gedetoneerd door in het vak te klikken, een waarde in te voeren en vervolgens op Enter te drukken of de waarde te selecteren die onder het vak wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d2320-173">**Simulation URLs to allow**: Expand this setting and optionally enter specific URLs that are part of your phishing simulation campaign that should not be blocked or detonated by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="d2320-174">U kunt maximaal tien items toevoegen.</span><span class="sxs-lookup"><span data-stu-id="d2320-174">You can add up to 10 entries.</span></span> <span data-ttu-id="d2320-175">Zie URL-syntaxis voor [de tenantlijst toestaan/blokkeren](/microsoft-365/security/office-365-security/tenant-allow-block-list#url-syntax-for-the-tenant-allowblock-list)voor de syntaxis van de URL.</span><span class="sxs-lookup"><span data-stu-id="d2320-175">For the URL syntax format, see [URL syntax for the Tenant Allow/Block List](/microsoft-365/security/office-365-security/tenant-allow-block-list#url-syntax-for-the-tenant-allowblock-list).</span></span>

   <span data-ttu-id="d2320-176">Als u een bestaande waarde wilt verwijderen, klikt u op verwijderen</span><span class="sxs-lookup"><span data-stu-id="d2320-176">To remove an existing value, click remove</span></span> ![Pictogram Verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="d2320-178">naast de waarde.</span><span class="sxs-lookup"><span data-stu-id="d2320-178">next to the value.</span></span>

4. <span data-ttu-id="d2320-179">Wanneer u klaar bent, gaat u op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="d2320-179">When you're finished, do one of the following steps:</span></span>
   - <span data-ttu-id="d2320-180">**Eerste keer:** Klik **op Toevoegen** en klik vervolgens op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="d2320-180">**First time**: Click **Add**, and then click **Close**.</span></span>
   - <span data-ttu-id="d2320-181">**Bestaand bewerken:** Klik **op Opslaan** en klik vervolgens op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="d2320-181">**Edit existing**: Click **Save** and then click **Close**.</span></span>

<span data-ttu-id="d2320-182">De phishingsimulatiegegevens van derden die u hebt geconfigureerd, worden weergegeven op het **tabblad Phishingsimulatie.** Als u wijzigingen wilt aanbrengen, klikt ![ u op Het tabblad ](../../media/m365-cc-sc-edit-icon.png) **bewerken** op Pictogram Bewerken.</span><span class="sxs-lookup"><span data-stu-id="d2320-182">The third-party phishing simulation entries that you configured are displayed on the **Phishing simulation** tab. To make changes, click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit** on the tab.</span></span>

## <a name="additional-scenarios-that-require-filtering-bypass"></a><span data-ttu-id="d2320-183">Extra scenario's waarvoor filteren moet worden omzeild</span><span class="sxs-lookup"><span data-stu-id="d2320-183">Additional scenarios that require filtering bypass</span></span>

<span data-ttu-id="d2320-184">Naast de twee scenario's waar het geavanceerde bezorgingsbeleid u bij kan helpen, zijn er andere scenario's waarvoor het filteren mogelijk moet worden overgeslagen:</span><span class="sxs-lookup"><span data-stu-id="d2320-184">In addition to the two scenarios that the advanced delivery policy can help you with, there are other scenarios that might require you bypass filtering:</span></span>

- <span data-ttu-id="d2320-185">**Filters van derden:** Als de MX-record  van uw domein niet naar Office 365 (berichten worden eerst ergens anders gerouteerd), is beveiliging standaard niet [](secure-by-default.md) *beschikbaar.*</span><span class="sxs-lookup"><span data-stu-id="d2320-185">**Third-party filters**: If your domain's MX record *doesn't* point to Office 365 (messages are routed somewhere else first), [secure by default](secure-by-default.md) *is not available*.</span></span> <span data-ttu-id="d2320-186">Als u bescherming wilt toevoegen, moet u Verbeterde filtering voor connectors (ook wel skip listing genoemd) *inschakelen.*</span><span class="sxs-lookup"><span data-stu-id="d2320-186">If you'd like to add protection, you'll need to enable Enhanced Filtering for Connectors (also known as *skip listing*).</span></span> <span data-ttu-id="d2320-187">Zie E-mailstroom beheren met [een externe cloudservice](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud)met Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d2320-187">For more information, see [Manage mail flow using a third-party cloud service with Exchange Online](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud).</span></span> <span data-ttu-id="d2320-188">Als u geen uitgebreide filtering voor connectors wilt gebruiken, gebruikt u regels voor e-mailstroom (ook wel transportregels genoemd) om Microsoft-filtering te omzeilen voor berichten die al zijn geëvalueerd door filtering van derden.</span><span class="sxs-lookup"><span data-stu-id="d2320-188">If you don't want Enhanced Filtering for Connectors,use mail flow rules (also known as transport rules) to bypass Microsoft filtering for messages that have already been evaluated by third-party filtering.</span></span> <span data-ttu-id="d2320-189">Zie E-mailstroomregels gebruiken om de SCL in berichten [in te stellen voor meer informatie.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md)</span><span class="sxs-lookup"><span data-stu-id="d2320-189">For more information, see [Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md).</span></span>

- <span data-ttu-id="d2320-190">**False positives under review**: U wilt mogelijk bepaalde berichten die nog steeds door Microsoft worden geanalyseerd [via](admin-submission.md) beheerdersinzendingen tijdelijk toestaan om bekende goede berichten te melden die ten onrechte als slecht worden gemarkeerd voor Microsoft (false positives).</span><span class="sxs-lookup"><span data-stu-id="d2320-190">**False positives under review**: You might want to temporarily allow certain messages that are still being analyzed by Microsoft via [admin submissions](admin-submission.md) to report known good messages that are incorrectly being marked as bad to Microsoft (false positives).</span></span> <span data-ttu-id="d2320-191">Net als bij alle \*\*\*\* overschrijvingen wordt ten zeerste aanbevolen dat deze vergoedingen tijdelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="d2320-191">As with all overrides, we **_highly recommended_** that these allowances are temporary.</span></span>

## <a name="exchange-online-powershell-procedures-for-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="d2320-192">Exchange Online PowerShell-procedures voor SecOps-postvakken in het beleid voor geavanceerde bezorging</span><span class="sxs-lookup"><span data-stu-id="d2320-192">Exchange Online PowerShell procedures for SecOps mailboxes in the advanced delivery policy</span></span>

<span data-ttu-id="d2320-193">In Exchange Online PowerShell zijn de basiselementen van SecOps-postvakken in het geavanceerde bezorgingsbeleid:</span><span class="sxs-lookup"><span data-stu-id="d2320-193">In Exchange Online PowerShell, the basic elements of SecOps mailboxes in the advanced delivery policy are:</span></span>

- <span data-ttu-id="d2320-194">**Het SecOps-beleid overschrijven:** beheerd door **\* de cmdlets -SecOpsOverridePolicy.**</span><span class="sxs-lookup"><span data-stu-id="d2320-194">**The SecOps override policy**: Controlled by the **\*-SecOpsOverridePolicy** cmdlets.</span></span>
- <span data-ttu-id="d2320-195">**De secops-overschrijvenregel:** wordt beheerd door **\* de cmdlets -SecOpsOverrideRuleRule.**</span><span class="sxs-lookup"><span data-stu-id="d2320-195">**The SecOps override rule**: Controlled by the **\*-SecOpsOverrideRule** cmdlets.</span></span>

<span data-ttu-id="d2320-196">Dit gedrag heeft de volgende resultaten:</span><span class="sxs-lookup"><span data-stu-id="d2320-196">This behavior has the following results:</span></span>

- <span data-ttu-id="d2320-197">U maakt eerst het beleid en vervolgens maakt u de regel die het beleid aangeeft waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="d2320-197">You create the policy first, then you create the rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="d2320-198">Wanneer u een beleid uit PowerShell verwijdert, wordt de bijbehorende regel ook verwijderd.</span><span class="sxs-lookup"><span data-stu-id="d2320-198">When you remove a policy from PowerShell, the corresponding rule is also removed.</span></span>
- <span data-ttu-id="d2320-199">Wanneer u een regel uit PowerShell verwijdert, wordt het bijbehorende beleid niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="d2320-199">When you remove a rule from PowerShell, the corresponding policy is not removed.</span></span> <span data-ttu-id="d2320-200">U moet het bijbehorende beleid handmatig verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d2320-200">You need to remove the corresponding policy manually.</span></span>

### <a name="use-powershell-to-configure-secops-mailboxes"></a><span data-ttu-id="d2320-201">PowerShell gebruiken om SecOps-postvakken te configureren</span><span class="sxs-lookup"><span data-stu-id="d2320-201">Use PowerShell to configure SecOps mailboxes</span></span>

<span data-ttu-id="d2320-202">Het configureren van een SecOps-postvak in het geavanceerde bezorgingsbeleid in PowerShell is een proces in twee stappen:</span><span class="sxs-lookup"><span data-stu-id="d2320-202">Configuring a SecOps mailbox in the advanced delivery policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="d2320-203">Het secops-overschrijvenbeleid maken.</span><span class="sxs-lookup"><span data-stu-id="d2320-203">Create the SecOps override policy.</span></span>
2. <span data-ttu-id="d2320-204">Maak de SecOps-overschrijvenregel die het beleid aangeeft waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="d2320-204">Create the SecOps override rule that specifies the policy that the rule applies to.</span></span>

#### <a name="step-1-use-powershell-to-create-the-secops-override-policy"></a><span data-ttu-id="d2320-205">Stap 1: PowerShell gebruiken om het secops-overschrijvenbeleid te maken</span><span class="sxs-lookup"><span data-stu-id="d2320-205">Step 1: Use PowerShell to create the SecOps override policy</span></span>

<span data-ttu-id="d2320-206">Als u het secops-overschrijvenbeleid wilt maken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="d2320-206">To create the SecOps override policy, use the following syntax:</span></span>

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>
```

<span data-ttu-id="d2320-207">**Opmerking:** Ongeacht de naam die u opgeeft, is de naam van het beleid SecOpsOverridePolicy, dus u kunt die waarde net zo goed gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d2320-207">**Note**: Regardless of the Name value you specify, the policy name will be SecOpsOverridePolicy, so you might as well use that value.</span></span>

<span data-ttu-id="d2320-208">In dit voorbeeld wordt het secops-postvakbeleid gemaakt.</span><span class="sxs-lookup"><span data-stu-id="d2320-208">This example creates the SecOps mailbox policy.</span></span>

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo secops@contoso.com
```

<span data-ttu-id="d2320-209">Zie [New-SecOpsOverridePolicy (Nieuw-SecOpsOverridePolicy)](/powershell/module/exchange/new-secopsoverridepolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="d2320-209">For detailed syntax and parameter information, see [New-SecOpsOverridePolicy](/powershell/module/exchange/new-secopsoverridepolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-the-secops-override-rule"></a><span data-ttu-id="d2320-210">Stap 2: PowerShell gebruiken om de secops-overschrijvenregel te maken</span><span class="sxs-lookup"><span data-stu-id="d2320-210">Step 2: Use PowerShell to create the SecOps override rule</span></span>

<span data-ttu-id="d2320-211">In dit voorbeeld wordt de regel SecOps-postvak gemaakt met de opgegeven instellingen.</span><span class="sxs-lookup"><span data-stu-id="d2320-211">This example creates the SecOps mailbox rule with the specified settings.</span></span>

```powershell
New-SecOpsOverrideRule -Name SecOpsOverrideRule -Policy SecOpsOverridePolicy
```

<span data-ttu-id="d2320-212">\*\*Opmerking:\*\*\*\*Ongeacht de waarde Naam die u opgeeft, is de regelnaam SecOpsOverrideRule waar een unieke \<GUID\> \<GUID\> GUID-waarde is (bijvoorbeeld 6fed4b63-3563-495d-a481-b24a311f8329).</span><span class="sxs-lookup"><span data-stu-id="d2320-212">**Note**: \*\*Regardless of the Name value you specify, the rule name will be SecOpsOverrideRule\<GUID\> where \<GUID\> is a unique GUID value (for example, 6fed4b63-3563-495d-a481-b24a311f8329).</span></span>

<span data-ttu-id="d2320-213">Zie [New-SecOpsOverrideRule voor](/powershell/module/exchange/new-secopsoverriderule)gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="d2320-213">For detailed syntax and parameter information, see [New-SecOpsOverrideRule](/powershell/module/exchange/new-secopsoverriderule).</span></span>

### <a name="use-powershell-to-view-the-secops-override-policy"></a><span data-ttu-id="d2320-214">PowerShell gebruiken om het beleid voor secops-overschrijven weer te geven</span><span class="sxs-lookup"><span data-stu-id="d2320-214">Use PowerShell to view the SecOps override policy</span></span>

<span data-ttu-id="d2320-215">Dit voorbeeld retourneert gedetailleerde informatie over het ene en alleen secops-postvakbeleid.</span><span class="sxs-lookup"><span data-stu-id="d2320-215">This example returns detailed information about the one and only SecOps mailbox policy.</span></span>

```powershell
Get-SecOpsOverridePolicy
```

<span data-ttu-id="d2320-216">Zie [Get-SecOpsOverridePolicy (Get-SecOpsOverridePolicy)](/powershell/module/exchange/get-secopsoverridepolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="d2320-216">For detailed syntax and parameter information, see [Get-SecOpsOverridePolicy](/powershell/module/exchange/get-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-view-secops-override-rules"></a><span data-ttu-id="d2320-217">PowerShell gebruiken om regels voor secops-overschrijven weer te geven</span><span class="sxs-lookup"><span data-stu-id="d2320-217">Use PowerShell to view SecOps override rules</span></span>

<span data-ttu-id="d2320-218">Dit voorbeeld retourneert gedetailleerde informatie over secops-regels die regels overschrijven.</span><span class="sxs-lookup"><span data-stu-id="d2320-218">This example returns detailed information about SecOps override rules.</span></span>

```powershell
Get-SecOpsOverrideRule
```

<span data-ttu-id="d2320-219">Hoewel de vorige opdracht slechts één regel moet retourneren, kunnen regels die in behandeling zijn voor verwijdering, ook worden opgenomen in de resultaten.</span><span class="sxs-lookup"><span data-stu-id="d2320-219">Although the previous command should return only one rule, any rules that are pending deletion might also be included in the results.</span></span>

<span data-ttu-id="d2320-220">In dit voorbeeld worden de geldige regel (één) en eventuele ongeldige regels geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="d2320-220">This example identifies the valid rule (one) and any invalid rules.</span></span>

```powershell
Get-SecOpsOverrideRule | Format-Table Name,Mode
```

<span data-ttu-id="d2320-221">Nadat u de ongeldige regels hebt opgegeven, kunt u deze verwijderen met de cmdlet **Remove-SecOpsOverrideRule,** zoals [verderop in dit artikel wordt beschreven.](#use-powershell-to-remove-secops-override-rules)</span><span class="sxs-lookup"><span data-stu-id="d2320-221">After you identify the invalid rules, you can remove them by using the **Remove-SecOpsOverrideRule** cmdlet as described [later in this article](#use-powershell-to-remove-secops-override-rules).</span></span>

<span data-ttu-id="d2320-222">Zie [Get-SecOpsOverrideRule (Get-SecOpsOverrideRule)](/powershell/module/exchange/get-secopsoverriderule) voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="d2320-222">For detailed syntax and parameter information, see [Get-SecOpsOverrideRule](/powershell/module/exchange/get-secopsoverriderule)</span></span>

### <a name="use-powershell-to-modify-the-secops-override-policy"></a><span data-ttu-id="d2320-223">PowerShell gebruiken om het secops-overschrijvenbeleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="d2320-223">Use PowerShell to modify the SecOps override policy</span></span>

<span data-ttu-id="d2320-224">Gebruik de volgende syntaxis om het secops-overschrijvenbeleid te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="d2320-224">To modify the SecOps override policy, use the following syntax:</span></span>

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy [-AddSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>] [-RemoveSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>]
```

<span data-ttu-id="d2320-225">In dit voorbeeld worden secops2@contoso.com toegevoegd aan het secops-overschrijvenbeleid.</span><span class="sxs-lookup"><span data-stu-id="d2320-225">This example adds secops2@contoso.com to the SecOps override policy.</span></span>

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy -AddSentTo secops2@contoso.com
```

<span data-ttu-id="d2320-226">**Opmerking:** Als er een bijbehorende, geldige SecOps-overschrijvenregel bestaat, worden de e-mailadressen in de regel ook bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="d2320-226">**Note**: If an associated, valid SecOps override rule exists, the email addresses in the rule will also be updated.</span></span>

<span data-ttu-id="d2320-227">Zie [Set-SecOpsOverridePolicy](/powershell/module/exchange/set-secopsoverridepolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="d2320-227">For detailed syntax and parameter information, see [Set-SecOpsOverridePolicy](/powershell/module/exchange/set-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-modify-a-secops-override-rule"></a><span data-ttu-id="d2320-228">PowerShell gebruiken om een SecOps-overschrijvenregel te wijzigen</span><span class="sxs-lookup"><span data-stu-id="d2320-228">Use PowerShell to modify a SecOps override rule</span></span>

<span data-ttu-id="d2320-229">De **cmdlet Set-SecOpsOverrideRule** wijzigt de e-mailadressen in de secops-overschrijvenregel niet.</span><span class="sxs-lookup"><span data-stu-id="d2320-229">The **Set-SecOpsOverrideRule** cmdlet does not modify the email addresses in the SecOps override rule.</span></span> <span data-ttu-id="d2320-230">Als u de e-mailadressen in de secops-overschrijvenregel wilt wijzigen, gebruikt u de cmdlet **Set-SecOpsOverridePolicy.**</span><span class="sxs-lookup"><span data-stu-id="d2320-230">To modify the email addresses in the SecOps override rule, use the **Set-SecOpsOverridePolicy** cmdlet.</span></span>

<span data-ttu-id="d2320-231">Zie [Set-SecOpsOverrideRule](/powershell/module/exchange/set-secopsoverriderule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="d2320-231">For detailed syntax and parameter information, see [Set-SecOpsOverrideRule](/powershell/module/exchange/set-secopsoverriderule).</span></span>

### <a name="use-powershell-to-remove-the-secops-override-policy"></a><span data-ttu-id="d2320-232">PowerShell gebruiken om het SecOps-overschrijvenbeleid te verwijderen</span><span class="sxs-lookup"><span data-stu-id="d2320-232">Use PowerShell to remove the SecOps override policy</span></span>

<span data-ttu-id="d2320-233">In dit voorbeeld worden het secopspostvakbeleid en de bijbehorende regel verwijderd.</span><span class="sxs-lookup"><span data-stu-id="d2320-233">This example removes the SecOps Mailbox policy and the corresponding rule.</span></span>

```powershell
Remove-SecOpsOverridePolicy -Identity SecOpsOverridePolicy
```

<span data-ttu-id="d2320-234">Zie [Remove-SecOpsOverridePolicy (Verwijderen-SecOpsOverridePolicy)](/powershell/module/exchange/remove-secopsoverridepolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="d2320-234">For detailed syntax and parameter information, see [Remove-SecOpsOverridePolicy](/powershell/module/exchange/remove-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-remove-secops-override-rules"></a><span data-ttu-id="d2320-235">PowerShell gebruiken om SecOps-regels te verwijderen</span><span class="sxs-lookup"><span data-stu-id="d2320-235">Use PowerShell to remove SecOps override rules</span></span>

<span data-ttu-id="d2320-236">Als u een secops-overschrijvenregel wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="d2320-236">To remove a SecOps override rule, use the following syntax:</span></span>

```powershell
Remove-SecOpsOverrideRule -Identity <RuleIdentity>
```

<span data-ttu-id="d2320-237">In dit voorbeeld wordt de opgegeven SecOps-overschrijvenregel verwijderd.</span><span class="sxs-lookup"><span data-stu-id="d2320-237">This example removes the specified SecOps override rule.</span></span>

```powershell
Remove-SecOpsOverrideRule -Identity SecOpsOverrideRule6fed4b63-3563-495d-a481-b24a311f8329
```

<span data-ttu-id="d2320-238">Zie [Remove-SecOpsOverrideRule voor](/powershell/module/exchange/remove-secopsoverriderule)gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="d2320-238">For detailed syntax and parameter information, see [Remove-SecOpsOverrideRule](/powershell/module/exchange/remove-secopsoverriderule).</span></span>

## <a name="exchange-online-powershell-procedures-for-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="d2320-239">Exchange Online PowerShell-procedures voor phishingsimulaties van derden in het beleid voor geavanceerde bezorging</span><span class="sxs-lookup"><span data-stu-id="d2320-239">Exchange Online PowerShell procedures for third-party phishing simulations in the advanced delivery policy</span></span>

<span data-ttu-id="d2320-240">In Exchange Online PowerShell zijn de basiselementen van phishingsimulaties van derden in het geavanceerde bezorgingsbeleid:</span><span class="sxs-lookup"><span data-stu-id="d2320-240">In Exchange Online PowerShell, the basic elements of third-party phishing simulations in the advanced delivery policy are:</span></span>

- <span data-ttu-id="d2320-241">**De phishingsimulatie overschrijven het beleid:** gecontroleerd door **\* de cmdlets -PhishSimOverridePolicy.**</span><span class="sxs-lookup"><span data-stu-id="d2320-241">**The phishing simulation override policy**: Controlled by the **\*-PhishSimOverridePolicy** cmdlets.</span></span>
- <span data-ttu-id="d2320-242">**De phishingsimulatie overschrijven regel:** Gecontroleerd door **\* de cmdlets -PhishSimOverrideRule.**</span><span class="sxs-lookup"><span data-stu-id="d2320-242">**The phishing simulation override rule**: Controlled by the **\*-PhishSimOverrideRule** cmdlets.</span></span>

<span data-ttu-id="d2320-243">Dit gedrag heeft de volgende resultaten:</span><span class="sxs-lookup"><span data-stu-id="d2320-243">This behavior has the following results:</span></span>

- <span data-ttu-id="d2320-244">U maakt eerst het beleid en vervolgens maakt u de regel die het beleid aangeeft waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="d2320-244">You create the policy first, then you create the rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="d2320-245">U wijzigt de instellingen in het beleid en de regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="d2320-245">You modify the settings in the policy and the rule separately.</span></span>
- <span data-ttu-id="d2320-246">Wanneer u een beleid uit PowerShell verwijdert, wordt de bijbehorende regel ook verwijderd.</span><span class="sxs-lookup"><span data-stu-id="d2320-246">When you remove a policy from PowerShell, the corresponding rule is also removed.</span></span>
- <span data-ttu-id="d2320-247">Wanneer u een regel uit PowerShell verwijdert, wordt het bijbehorende beleid niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="d2320-247">When you remove a rule from PowerShell, the corresponding policy is not removed.</span></span> <span data-ttu-id="d2320-248">U moet het bijbehorende beleid handmatig verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d2320-248">You need to remove the corresponding policy manually.</span></span>

### <a name="use-powershell-to-configure-third-party-phishing-simulations"></a><span data-ttu-id="d2320-249">PowerShell gebruiken om phishingsimulaties van derden te configureren</span><span class="sxs-lookup"><span data-stu-id="d2320-249">Use PowerShell to configure third-party phishing simulations</span></span>

<span data-ttu-id="d2320-250">Het configureren van een phishingsimulatie van derden in het beleid voor geavanceerde bezorging in PowerShell is een proces in twee stappen:</span><span class="sxs-lookup"><span data-stu-id="d2320-250">Configuring a third-party phishing simulation in the advanced delivery policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="d2320-251">Maak het beleid voor phishingsimulatie.</span><span class="sxs-lookup"><span data-stu-id="d2320-251">Create the phishing simulation override policy.</span></span>
2. <span data-ttu-id="d2320-252">Maak de overschrijvende regel voor phishingsimulatie die het beleid aangeeft waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="d2320-252">Create the phishing simulation override rule that specifies the policy that the rule applies to.</span></span>

#### <a name="step-1-use-powershell-to-create-the-phishing-simulation-override-policy"></a><span data-ttu-id="d2320-253">Stap 1: PowerShell gebruiken om het beleid voor phishingsimulatie te overschrijven</span><span class="sxs-lookup"><span data-stu-id="d2320-253">Step 1: Use PowerShell to create the phishing simulation override policy</span></span>

<span data-ttu-id="d2320-254">In dit voorbeeld wordt het beleid voor phishingsimulatie overschrijven.</span><span class="sxs-lookup"><span data-stu-id="d2320-254">This example creates the phishing simulation override policy.</span></span>

```powershell
New-PhishSimOverridePolicy -Name PhishSimOverridePolicy
```

<span data-ttu-id="d2320-255">**Opmerking:** Ongeacht de naam die u opgeeft, is de naam van het beleid PhishSimOverridePolicy, dus u kunt deze waarde net zo goed gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d2320-255">**Note**: Regardless of the Name value you specify, the policy name will be PhishSimOverridePolicy, so you might as well use that value.</span></span>

<span data-ttu-id="d2320-256">Zie [New-PhishSimOverridePolicy (Nieuw-PhishSimOverridePolicy)](/powershell/module/exchange/new-phishsimoverridepolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="d2320-256">For detailed syntax and parameter information, see [New-PhishSimOverridePolicy](/powershell/module/exchange/new-phishsimoverridepolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-the-phishing-simulation-override-rule"></a><span data-ttu-id="d2320-257">Stap 2: PowerShell gebruiken om de regel voor phishingsimulatie te maken</span><span class="sxs-lookup"><span data-stu-id="d2320-257">Step 2: Use PowerShell to create the phishing simulation override rule</span></span>

<span data-ttu-id="d2320-258">Gebruik de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="d2320-258">Use the following syntax:</span></span>

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs <Domain1>,<Domain2>,...<DomainN> -SenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>
```

<span data-ttu-id="d2320-259">Ongeacht de waarde Naam die u opgeeft, is de regelnaam PhishSimOverrideRule waar een unieke \<GUID\> \<GUID\> GUID-waarde is (bijvoorbeeld a0eae53e-d755-4a42-9320-b9c6b55c5011).</span><span class="sxs-lookup"><span data-stu-id="d2320-259">Regardless of the Name value you specify, the rule name will be PhishSimOverrideRule\<GUID\> where \<GUID\> is a unique GUID value (for example, a0eae53e-d755-4a42-9320-b9c6b55c5011).</span></span>

<span data-ttu-id="d2320-260">Een geldige IP-adresinvoer is een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="d2320-260">A valid IP address entry is one of the following values:</span></span>

- <span data-ttu-id="d2320-261">Enkel IP: bijvoorbeeld 192.168.1.1.</span><span class="sxs-lookup"><span data-stu-id="d2320-261">Single IP: For example, 192.168.1.1.</span></span>
- <span data-ttu-id="d2320-262">IP-bereik: bijvoorbeeld 192.168.0.1-192.168.0.254.</span><span class="sxs-lookup"><span data-stu-id="d2320-262">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
- <span data-ttu-id="d2320-263">CIDR IP: Bijvoorbeeld 192.168.0.1/25.</span><span class="sxs-lookup"><span data-stu-id="d2320-263">CIDR IP: For example, 192.168.0.1/25.</span></span>

<span data-ttu-id="d2320-264">In dit voorbeeld wordt de regel voor phishingsimulatie met de opgegeven instellingen overschreven.</span><span class="sxs-lookup"><span data-stu-id="d2320-264">This example creates the phishing simulation override rule with the specified settings.</span></span>

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs fabrikam.com,wingtiptoys.com -SenderIpRanges 192.168.1.55
```

<span data-ttu-id="d2320-265">Zie [New-PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="d2320-265">For detailed syntax and parameter information, see [New-PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-view-the-phishing-simulation-override-policy"></a><span data-ttu-id="d2320-266">PowerShell gebruiken om het beleid voor phishingsimulaties te bekijken</span><span class="sxs-lookup"><span data-stu-id="d2320-266">Use PowerShell to view the phishing simulation override policy</span></span>

<span data-ttu-id="d2320-267">Dit voorbeeld retourneert gedetailleerde informatie over de enige phishingsimulatie die beleid overschrijven.</span><span class="sxs-lookup"><span data-stu-id="d2320-267">This example returns detailed information about the one and only phishing simulation override policy.</span></span>

```powershell
Get-PhishSimOverridePolicy
```

<span data-ttu-id="d2320-268">Zie [Get-PhishSimOverridePolicy (Get-PhishSimOverridePolicy)](/powershell/module/exchange/get-phishsimoverridepolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="d2320-268">For detailed syntax and parameter information, see [Get-PhishSimOverridePolicy](/powershell/module/exchange/get-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-view-phishing-simulation-override-rules"></a><span data-ttu-id="d2320-269">PowerShell gebruiken om regels voor phishingsimulatie te bekijken</span><span class="sxs-lookup"><span data-stu-id="d2320-269">Use PowerShell to view phishing simulation override rules</span></span>

<span data-ttu-id="d2320-270">Dit voorbeeld retourneert gedetailleerde informatie over regels voor phishingsimulatie.</span><span class="sxs-lookup"><span data-stu-id="d2320-270">This example returns detailed information about phishing simulation override rules.</span></span>

```powershell
Get-PhishSimOverrideRule
```

<span data-ttu-id="d2320-271">Hoewel de vorige opdracht slechts één regel moet retourneren, kunnen regels die in behandeling zijn voor verwijdering, ook worden opgenomen in de resultaten.</span><span class="sxs-lookup"><span data-stu-id="d2320-271">Although the previous command should return only one rule, any rules that are pending deletion might also be included in the results.</span></span>

<span data-ttu-id="d2320-272">In dit voorbeeld worden de geldige regel (één) en eventuele ongeldige regels geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="d2320-272">This example identifies the valid rule (one) and any invalid rules.</span></span>

```powershell
Get-PhishSimOverrideRule | Format-Table Name,Mode
```

<span data-ttu-id="d2320-273">Nadat u de ongeldige regels hebt opgegeven, kunt u deze verwijderen met de **cmdlet Remove-PhisSimOverrideRule,** [zoals verder wordt beschreven in dit artikel.](#use-powershell-to-remove-phishing-simulation-override-rules)</span><span class="sxs-lookup"><span data-stu-id="d2320-273">After you identify the invalid rules, you can remove them by using the **Remove-PhisSimOverrideRule** cmdlet as described [later in this article](#use-powershell-to-remove-phishing-simulation-override-rules).</span></span>

<span data-ttu-id="d2320-274">Zie [Get-PhishSimOverrideRule](/powershell/module/exchange/get-phishsimoverriderule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="d2320-274">For detailed syntax and parameter information, see [Get-PhishSimOverrideRule](/powershell/module/exchange/get-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-modify-the-phishing-simulation-override-policy"></a><span data-ttu-id="d2320-275">PowerShell gebruiken om het beleid voor phishingsimulaties te wijzigen</span><span class="sxs-lookup"><span data-stu-id="d2320-275">Use PowerShell to modify the phishing simulation override policy</span></span>

<span data-ttu-id="d2320-276">Als u het beleid voor phishingsimulaties wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="d2320-276">To modify the phishing simulation override policy, use the following syntax:</span></span>

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy [-Comment "<DescriptiveText>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="d2320-277">In dit voorbeeld wordt het beleid voor phishingsimulatie uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="d2320-277">This example disables the phishing simulation override policy.</span></span>

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy -Enabled $false
```

<span data-ttu-id="d2320-278">Zie [Set-PhishSimOverridePolicy](/powershell/module/exchange/set-phishsimoverridepolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="d2320-278">For detailed syntax and parameter information, see [Set-PhishSimOverridePolicy](/powershell/module/exchange/set-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-modify-a-phishing-simulation-override-rule"></a><span data-ttu-id="d2320-279">PowerShell gebruiken om een phishingsimulatieregel te wijzigen</span><span class="sxs-lookup"><span data-stu-id="d2320-279">Use PowerShell to modify a phishing simulation override rule</span></span>

<span data-ttu-id="d2320-280">Als u de regel voor phishingsimulaties wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="d2320-280">To modify the phishing simulation override rule, use the following syntax:</span></span>

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 [-Comment "<DescriptiveText>"] [-AddSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-RemoveSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-AddSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>] [-RemoveSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>]
```

<span data-ttu-id="d2320-281">In dit voorbeeld wijzigt u de opgegeven phishingsimulatieregel met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="d2320-281">This example modifies the specified phishing simulation override rule with the following settings:</span></span>

- <span data-ttu-id="d2320-282">Voeg de domeininvoer blueyonderairlines.com.</span><span class="sxs-lookup"><span data-stu-id="d2320-282">Add the domain entry blueyonderairlines.com.</span></span>
- <span data-ttu-id="d2320-283">Verwijder de IP-adresinvoer 192.168.1.55.</span><span class="sxs-lookup"><span data-stu-id="d2320-283">Remove the IP address entry 192.168.1.55.</span></span>

<span data-ttu-id="d2320-284">Houd er rekening mee dat deze wijzigingen geen invloed hebben op bestaande vermeldingen.</span><span class="sxs-lookup"><span data-stu-id="d2320-284">Note that these changes don't affect existing entries.</span></span>

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 -AddSenderDomainIs blueyonderairlines.com -RemoveSenderIpRanges 192.168.1.55
```

<span data-ttu-id="d2320-285">Zie [Set-PhishSimOverrideRule](/powershell/module/exchange/set-phishsimoverriderule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="d2320-285">For detailed syntax and parameter information, see [Set-PhishSimOverrideRule](/powershell/module/exchange/set-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-remove-a-phishing-simulation-override-policy"></a><span data-ttu-id="d2320-286">PowerShell gebruiken om een beleid voor phishingsimulatie te verwijderen</span><span class="sxs-lookup"><span data-stu-id="d2320-286">Use PowerShell to remove a phishing simulation override policy</span></span>

<span data-ttu-id="d2320-287">In dit voorbeeld worden het phishingsimulatiebeleid en de bijbehorende regel verwijderd.</span><span class="sxs-lookup"><span data-stu-id="d2320-287">This example removes the phishing simulation override policy and the corresponding rule.</span></span>

```powershell
Remove-PhishSimOverridePolicy -Identity PhishSimOverridePolicy
```

<span data-ttu-id="d2320-288">Zie [Remove-PhishSimOverridePolicy (Verwijderen-PhishSimOverridePolicy)](/powershell/module/exchange/remove-phishsimoverridepolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="d2320-288">For detailed syntax and parameter information, see [Remove-PhishSimOverridePolicy](/powershell/module/exchange/remove-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-remove-phishing-simulation-override-rules"></a><span data-ttu-id="d2320-289">PowerShell gebruiken om regels voor phishingsimulatie te verwijderen</span><span class="sxs-lookup"><span data-stu-id="d2320-289">Use PowerShell to remove phishing simulation override rules</span></span>

<span data-ttu-id="d2320-290">Als u een phishingsimulatieregel wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="d2320-290">To remove a phishing simulation override rule, use the following syntax:</span></span>

```powershell
Remove-PhishSimOverrideRule -Identity <RuleIdentity>
```

<span data-ttu-id="d2320-291">In dit voorbeeld wordt de opgegeven regel voor phishingsimulatie verwijderd.</span><span class="sxs-lookup"><span data-stu-id="d2320-291">This example removes the specified phishing simulation override rule.</span></span>

```powershell
Remove-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011
```

<span data-ttu-id="d2320-292">Zie [Remove-PhishSimOverrideRule voor](/powershell/module/exchange/remove-phishsimoverriderule)gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="d2320-292">For detailed syntax and parameter information, see [Remove-PhishSimOverrideRule](/powershell/module/exchange/remove-phishsimoverriderule).</span></span>
