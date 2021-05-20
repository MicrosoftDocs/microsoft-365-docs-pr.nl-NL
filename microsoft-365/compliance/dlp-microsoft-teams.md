---
title: Preventie en preventie van gegevensverlies Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Microsoft Teams chats en kanalen ondersteunt DLP-beleid (Data Loss Prevention).
ms.openlocfilehash: e55bfa34b2495465f573bcede3ebda2308dbbbbc
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583386"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="0a00a-103">Preventie en preventie van gegevensverlies Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0a00a-103">Data loss prevention and Microsoft Teams</span></span>

<span data-ttu-id="0a00a-104">Als uw organisatie beschikt over preventie van gegevensverlies (DLP), kunt u beleidsregels definiëren om te voorkomen dat personen gevoelige informatie delen in een Microsoft Teams kanaal of chatsessie.</span><span class="sxs-lookup"><span data-stu-id="0a00a-104">If your organization has data loss prevention (DLP), you can define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="0a00a-105">Hier zijn enkele voorbeelden van hoe deze beveiliging werkt:</span><span class="sxs-lookup"><span data-stu-id="0a00a-105">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="0a00a-106">**Voorbeeld 1: Gevoelige informatie in berichten beveiligen.**</span><span class="sxs-lookup"><span data-stu-id="0a00a-106">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="0a00a-107">Stel dat iemand gevoelige informatie probeert te delen in een Teams of kanaal met gasten (externe gebruikers).</span><span class="sxs-lookup"><span data-stu-id="0a00a-107">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="0a00a-108">Als u een DLP-beleid hebt gedefinieerd om dit te voorkomen, worden berichten met gevoelige informatie die naar externe gebruikers worden verzonden, verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0a00a-108">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="0a00a-109">Dit gebeurt automatisch en binnen enkele seconden, afhankelijk van hoe uw DLP-beleid is geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="0a00a-109">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0a00a-110">DLP voor Microsoft Teams blokkeert gevoelige inhoud wanneer deze wordt gedeeld met Microsoft Teams gebruikers die:</span><span class="sxs-lookup"><span data-stu-id="0a00a-110">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="0a00a-111">- [gasttoegang](/MicrosoftTeams/guest-access) in teams en kanalen; of</span><span class="sxs-lookup"><span data-stu-id="0a00a-111">- [guest access](/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="0a00a-112">- [externe toegang](/MicrosoftTeams/manage-external-access) in vergaderingen en chatsessies.</span><span class="sxs-lookup"><span data-stu-id="0a00a-112">- [external access](/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="0a00a-113">DLP voor externe chatsessies werkt alleen als zowel de afzender als de ontvanger zich in de Teams Alleen-modus en Microsoft Teams [eigen federatie](/microsoftteams/manage-external-access).</span><span class="sxs-lookup"><span data-stu-id="0a00a-113">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="0a00a-114">DLP voor Teams blokkeert geen berichten in [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) met Skype voor Bedrijven of niet-native federatief chatsessies.</span><span class="sxs-lookup"><span data-stu-id="0a00a-114">DLP for Teams does not block messages in [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="0a00a-115">**Voorbeeld 2: Gevoelige informatie in documenten beveiligen.**</span><span class="sxs-lookup"><span data-stu-id="0a00a-115">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="0a00a-116">Stel dat iemand een document probeert te delen met gasten in een Microsoft Teams of chat en dat het document gevoelige informatie bevat.</span><span class="sxs-lookup"><span data-stu-id="0a00a-116">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="0a00a-117">Als u een DLP-beleid hebt gedefinieerd om dit te voorkomen, wordt het document niet geopend voor deze gebruikers.</span><span class="sxs-lookup"><span data-stu-id="0a00a-117">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="0a00a-118">Uw DLP-beleid moet SharePoint en OneDrive om de beveiliging te kunnen garanderen.</span><span class="sxs-lookup"><span data-stu-id="0a00a-118">Your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="0a00a-119">Dit is een voorbeeld van DLP voor SharePoint dat wordt vermeld in Microsoft Teams en daarom vereist dat gebruikers een licentie hebben voor Office 365 DLP (opgenomen in Office 365 E3), maar dat gebruikers geen licentie moeten hebben voor Office 365 Advanced Compliance.)</span><span class="sxs-lookup"><span data-stu-id="0a00a-119">This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="dlp-licensing-for-microsoft-teams"></a><span data-ttu-id="0a00a-120">DLP-licenties voor Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0a00a-120">DLP Licensing for Microsoft Teams</span></span>

<span data-ttu-id="0a00a-121">[Mogelijkheden voor preventie van gegevensverlies](dlp-learn-about-dlp.md) zijn uitgebreid met Microsoft Teams chat- en kanaalberichten, inclusief **privékanaalberichten** voor:</span><span class="sxs-lookup"><span data-stu-id="0a00a-121">[Data loss prevention](dlp-learn-about-dlp.md) capabilities were extended to include Microsoft Teams chat and channel messages, **including private channel messages** for:</span></span>

- <span data-ttu-id="0a00a-122">Office 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="0a00a-122">Office 365 E5/A5</span></span>
- <span data-ttu-id="0a00a-123">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="0a00a-123">Microsoft 365 E5/A5</span></span>
- <span data-ttu-id="0a00a-124">Microsoft 365 Informatiebeveiliging en beheer</span><span class="sxs-lookup"><span data-stu-id="0a00a-124">Microsoft 365 Information Protection and Governance</span></span>
- <span data-ttu-id="0a00a-125">Office 365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="0a00a-125">Office 365 Advanced Compliance</span></span>

<span data-ttu-id="0a00a-126">Office 365 en Microsoft 365 E3 DLP-beveiliging voor SharePoint Online, OneDrive en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0a00a-126">Office 365 and Microsoft 365 E3 include DLP protection for SharePoint Online, OneDrive, and Exchange Online.</span></span> <span data-ttu-id="0a00a-127">Dit geldt ook voor bestanden die worden gedeeld via Teams omdat Teams online SharePoint en OneDrive om bestanden te delen.</span><span class="sxs-lookup"><span data-stu-id="0a00a-127">This also includes files that are shared through Teams because Teams uses SharePoint Online and OneDrive to share files.</span></span>

<span data-ttu-id="0a00a-128">Ondersteuning voor DLP-beveiliging in Teams Chat vereist E5.</span><span class="sxs-lookup"><span data-stu-id="0a00a-128">Support for DLP protection in Teams Chat requires E5.</span></span>

<span data-ttu-id="0a00a-129">Zie voor meer informatie over licentievereisten [Microsoft 365 Tenant-Level Services Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="0a00a-129">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0a00a-130">DLP is alleen van toepassing op de werkelijke berichten in de chat- of kanaalthread.</span><span class="sxs-lookup"><span data-stu-id="0a00a-130">DLP applies only to the actual messages in the chat or channel thread.</span></span> <span data-ttu-id="0a00a-131">Activiteitsmeldingen, die een kort voorbeeld van een bericht bevatten  en worden weergegeven op basis van de meldingsinstellingen van een gebruiker, worden niet opgenomen in Teams DLP.</span><span class="sxs-lookup"><span data-stu-id="0a00a-131">Activity notifications -- which include a short message preview and appear based on a user's notification settings -- are **not** included in Teams DLP.</span></span> <span data-ttu-id="0a00a-132">Alle gevoelige informatie die aanwezig is in het deel van het bericht dat in het voorbeeld wordt weergegeven, blijft zichtbaar in de melding, zelfs nadat het DLP-beleid is toegepast en gevoelige informatie het bericht zelf heeft verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0a00a-132">Any sensitive information present in the part of the message that appears in the preview will remain visible in the notification even after the DLP policy has been applied and removed sensitive information the message itself.</span></span>

## <a name="scope-of-dlp-protection"></a><span data-ttu-id="0a00a-133">Bereik van DLP-beveiliging</span><span class="sxs-lookup"><span data-stu-id="0a00a-133">Scope of DLP protection</span></span>

<span data-ttu-id="0a00a-134">DLP-beveiliging wordt anders toegepast op Teams entiteiten.</span><span class="sxs-lookup"><span data-stu-id="0a00a-134">DLP protection are applied differently to Teams entities.</span></span>

|<span data-ttu-id="0a00a-135">Gebruikersaccounts/groepen/lijst</span><span class="sxs-lookup"><span data-stu-id="0a00a-135">User Accounts/Groups/List</span></span>  |<span data-ttu-id="0a00a-136">Teams Entiteit</span><span class="sxs-lookup"><span data-stu-id="0a00a-136">Teams Entity</span></span> |<span data-ttu-id="0a00a-137">DLP-beveiliging beschikbaar</span><span class="sxs-lookup"><span data-stu-id="0a00a-137">DLP protection available</span></span>|
|---------|---------|---------|
|<span data-ttu-id="0a00a-138">afzonderlijke gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="0a00a-138">individual user accounts</span></span>     |<span data-ttu-id="0a00a-139">1:1/n chats</span><span class="sxs-lookup"><span data-stu-id="0a00a-139">1:1/n chats</span></span>         |<span data-ttu-id="0a00a-140">ja</span><span class="sxs-lookup"><span data-stu-id="0a00a-140">yes</span></span>         |
|     |<span data-ttu-id="0a00a-141">algemene chats</span><span class="sxs-lookup"><span data-stu-id="0a00a-141">general chats</span></span>         |<span data-ttu-id="0a00a-142">nee</span><span class="sxs-lookup"><span data-stu-id="0a00a-142">no</span></span>         |
|     |<span data-ttu-id="0a00a-143">gedeelde kanalen</span><span class="sxs-lookup"><span data-stu-id="0a00a-143">shared channels</span></span>         |<span data-ttu-id="0a00a-144">nee</span><span class="sxs-lookup"><span data-stu-id="0a00a-144">no</span></span>         |
|     |<span data-ttu-id="0a00a-145">privékanalen</span><span class="sxs-lookup"><span data-stu-id="0a00a-145">private channels</span></span>         |<span data-ttu-id="0a00a-146">ja</span><span class="sxs-lookup"><span data-stu-id="0a00a-146">yes</span></span>         |
|<span data-ttu-id="0a00a-147">beveiligingsgroepen/distributielijsten</span><span class="sxs-lookup"><span data-stu-id="0a00a-147">security groups/distribution lists</span></span>  | <span data-ttu-id="0a00a-148">1:1/n chats</span><span class="sxs-lookup"><span data-stu-id="0a00a-148">1:1/n chats</span></span>         |<span data-ttu-id="0a00a-149">ja</span><span class="sxs-lookup"><span data-stu-id="0a00a-149">yes</span></span>         |
|     |<span data-ttu-id="0a00a-150">algemene chats</span><span class="sxs-lookup"><span data-stu-id="0a00a-150">general chats</span></span>         |<span data-ttu-id="0a00a-151">nee</span><span class="sxs-lookup"><span data-stu-id="0a00a-151">no</span></span>         |
|     |<span data-ttu-id="0a00a-152">gedeelde kanalen</span><span class="sxs-lookup"><span data-stu-id="0a00a-152">shared channels</span></span>         |<span data-ttu-id="0a00a-153">nee</span><span class="sxs-lookup"><span data-stu-id="0a00a-153">no</span></span>      |
|     |<span data-ttu-id="0a00a-154">privékanalen</span><span class="sxs-lookup"><span data-stu-id="0a00a-154">private channels</span></span>         |<span data-ttu-id="0a00a-155">ja</span><span class="sxs-lookup"><span data-stu-id="0a00a-155">yes</span></span>        |
|<span data-ttu-id="0a00a-156">Microsoft 365 groep</span><span class="sxs-lookup"><span data-stu-id="0a00a-156">Microsoft 365 group</span></span>    |<span data-ttu-id="0a00a-157">1:1/n chats</span><span class="sxs-lookup"><span data-stu-id="0a00a-157">1:1/n chats</span></span>          |<span data-ttu-id="0a00a-158">nee</span><span class="sxs-lookup"><span data-stu-id="0a00a-158">no</span></span>         |
|     |<span data-ttu-id="0a00a-159">algemene chats</span><span class="sxs-lookup"><span data-stu-id="0a00a-159">general chats</span></span>          |<span data-ttu-id="0a00a-160">ja</span><span class="sxs-lookup"><span data-stu-id="0a00a-160">yes</span></span>        |
|     |<span data-ttu-id="0a00a-161">gedeelde kanalen</span><span class="sxs-lookup"><span data-stu-id="0a00a-161">shared channels</span></span>|<span data-ttu-id="0a00a-162">ja</span><span class="sxs-lookup"><span data-stu-id="0a00a-162">yes</span></span> |
|     |<span data-ttu-id="0a00a-163">privékanalen</span><span class="sxs-lookup"><span data-stu-id="0a00a-163">private channels</span></span>|<span data-ttu-id="0a00a-164">nee</span><span class="sxs-lookup"><span data-stu-id="0a00a-164">no</span></span>| 


## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="0a00a-165">Beleidstips helpen gebruikers op te leiden</span><span class="sxs-lookup"><span data-stu-id="0a00a-165">Policy tips help educate users</span></span>

<span data-ttu-id="0a00a-166">Net zoals DLP werkt in [Exchange, Outlook, Outlook](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)op het web, [SharePoint Online, OneDrive voor Bedrijven-sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)en [Office-bureaubladcl clients,](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)worden beleidstips weergegeven wanneer een actie wordt triggers met een DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="0a00a-166">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action triggers with a DLP policy.</span></span> <span data-ttu-id="0a00a-167">Hier is een voorbeeld van een beleidstip:</span><span class="sxs-lookup"><span data-stu-id="0a00a-167">Here's an example of a policy tip:</span></span>

![Geblokkeerde berichtmelding in Teams](../media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="0a00a-169">Hier heeft de afzender geprobeerd een sociaal-zekerheidsnummer te delen in een Microsoft Teams kanaal.</span><span class="sxs-lookup"><span data-stu-id="0a00a-169">Here, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="0a00a-170">Met **de koppeling Wat kan ik doen?** wordt een dialoogvenster geopend met opties voor de afzender om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="0a00a-170">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="0a00a-171">De afzender kan ervoor kiezen om het beleid te overschrijven of een beheerder op de hoogte te stellen om het te controleren en op te lossen.</span><span class="sxs-lookup"><span data-stu-id="0a00a-171">Notice that, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![Opties voor het oplossen van geblokkeerd bericht](../media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="0a00a-173">In uw organisatie kunt u ervoor kiezen om gebruikers toe te staan een DLP-beleid te overschrijven.</span><span class="sxs-lookup"><span data-stu-id="0a00a-173">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="0a00a-174">Wanneer u uw DLP-beleid configureert, kunt u de standaardbeleidstips gebruiken of [beleidstips voor](#to-customize-policy-tips) uw organisatie aanpassen.</span><span class="sxs-lookup"><span data-stu-id="0a00a-174">When you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span>

<span data-ttu-id="0a00a-175">Als u teruggaat naar ons voorbeeld, waar een afzender een sociaal-zekerheidsnummer heeft gedeeld in een Teams kanaal, ziet de geadresseerde het volgende:</span><span class="sxs-lookup"><span data-stu-id="0a00a-175">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0a00a-176">![Bericht geblokkeerd](../media/dlp-teams-blockedmessage-notification-to-user.png)</span><span class="sxs-lookup"><span data-stu-id="0a00a-176">![Message blocked](../media/dlp-teams-blockedmessage-notification-to-user.png)</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="0a00a-177">Beleidstips aanpassen</span><span class="sxs-lookup"><span data-stu-id="0a00a-177">To customize policy tips</span></span>

<span data-ttu-id="0a00a-178">Als u deze taak wilt uitvoeren, moet u een rol toegewezen krijgen die machtigingen heeft om DLP-beleid te bewerken.</span><span class="sxs-lookup"><span data-stu-id="0a00a-178">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="0a00a-179">Zie Machtigingen [voor meer informatie.](data-loss-prevention-policies.md#permissions)</span><span class="sxs-lookup"><span data-stu-id="0a00a-179">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="0a00a-180">Ga naar het Compliancecentrum [https://compliance.microsoft.com](https://compliance.microsoft.com) () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="0a00a-180">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="0a00a-181">Kies **Beleid voor preventie van**  >  **gegevensverlies.**</span><span class="sxs-lookup"><span data-stu-id="0a00a-181">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="0a00a-182">Selecteer een beleid en kies naast **Beleidsinstellingen** de optie **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="0a00a-182">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="0a00a-183">Maak een nieuwe regel of bewerk een bestaande regel voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="0a00a-183">Either create a new rule, or edit an existing rule for the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a00a-184">![Een regel voor een beleid bewerken](../media/dlp-teams-editrule.png)</span><span class="sxs-lookup"><span data-stu-id="0a00a-184">![Editing a rule for a policy](../media/dlp-teams-editrule.png)</span></span>

5. <span data-ttu-id="0a00a-185">Selecteer op **het tabblad Gebruikersmeldingen** **de optie De e-mailtekst aanpassen** en/of De **tekstopties voor beleidstips** aanpassen.</span><span class="sxs-lookup"><span data-stu-id="0a00a-185">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a00a-186">![Gebruikersmeldingen en beleidstips aanpassen](../media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="0a00a-186">![Customize user notifications and policy tips](../media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="0a00a-187">Geef de tekst op die u wilt gebruiken voor e-mailmeldingen en/of beleidstips en kies **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="0a00a-187">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span>

7. <span data-ttu-id="0a00a-188">Kies opslaan **op het tabblad** Beleidsinstellingen. </span><span class="sxs-lookup"><span data-stu-id="0a00a-188">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="0a00a-189">Sta ongeveer één uur toe dat uw wijzigingen hun weg vinden in uw datacenter en worden gesynchroniseerd met gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="0a00a-189">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="0a00a-190">Een Microsoft Teams als locatie toevoegen aan bestaand DLP-beleid</span><span class="sxs-lookup"><span data-stu-id="0a00a-190">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="0a00a-191">Als u deze taak wilt uitvoeren, moet u een rol toegewezen krijgen die machtigingen heeft om DLP-beleid te bewerken.</span><span class="sxs-lookup"><span data-stu-id="0a00a-191">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="0a00a-192">Zie Machtigingen [voor meer informatie.](data-loss-prevention-policies.md#permissions)</span><span class="sxs-lookup"><span data-stu-id="0a00a-192">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="0a00a-193">Ga naar het Compliancecentrum [https://compliance.microsoft.com](https://compliance.microsoft.com) () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="0a00a-193">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="0a00a-194">Kies **Beleid voor preventie van**  >  **gegevensverlies.**</span><span class="sxs-lookup"><span data-stu-id="0a00a-194">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="0a00a-195">Selecteer een beleid en bekijk de waarden onder **Locaties.**</span><span class="sxs-lookup"><span data-stu-id="0a00a-195">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="0a00a-196">Als u **chat- Teams en kanaalberichten** ziet, bent u klaar.</span><span class="sxs-lookup"><span data-stu-id="0a00a-196">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="0a00a-197">Als u dit niet hebt, klikt u op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="0a00a-197">If you don't, click **Edit**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a00a-198">![Locaties voor bestaand beleid](../media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="0a00a-198">![Locations for existing policy](../media/dlp-teams-editexistingpolicy.png)</span></span>

4. <span data-ttu-id="0a00a-199">Schakel in **de** kolom Status het beleid in voor Teams **chat- en kanaalberichten.**</span><span class="sxs-lookup"><span data-stu-id="0a00a-199">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a00a-200">![DLP voor Teams chats en kanalen](../media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="0a00a-200">![DLP for Teams chats and channels](../media/dlp-teams-addteamschatschannels.png)</span></span>

5. <span data-ttu-id="0a00a-201">Houd op **het tabblad** Locaties kiezen de standaardinstelling van alle accounts of selecteer Laat me specifieke **locaties kiezen.**</span><span class="sxs-lookup"><span data-stu-id="0a00a-201">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="0a00a-202">U kunt het volgende opgeven:</span><span class="sxs-lookup"><span data-stu-id="0a00a-202">You can specify:</span></span>

    1. <span data-ttu-id="0a00a-203">maximaal 1000 afzonderlijke accounts om accounts op te nemen of uit te sluiten</span><span class="sxs-lookup"><span data-stu-id="0a00a-203">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="0a00a-204">distributielijsten en beveiligingsgroepen die u wilt opnemen of uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="0a00a-204">distribution lists and security groups to include or exclude.</span></span> 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. <span data-ttu-id="0a00a-205">Kies vervolgens **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0a00a-205">Then choose **Next**.</span></span>

7. <span data-ttu-id="0a00a-206">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0a00a-206">Click **Save**.</span></span>

<span data-ttu-id="0a00a-207">Sta ongeveer één uur toe dat uw wijzigingen hun weg vinden in uw datacenter en worden gesynchroniseerd met gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="0a00a-207">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="0a00a-208">Een nieuw DLP-beleid definiëren voor Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0a00a-208">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="0a00a-209">Als u deze taak wilt uitvoeren, moet u een rol toegewezen krijgen die machtigingen heeft om DLP-beleid te bewerken.</span><span class="sxs-lookup"><span data-stu-id="0a00a-209">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="0a00a-210">Zie Machtigingen [voor meer informatie.](data-loss-prevention-policies.md#permissions)</span><span class="sxs-lookup"><span data-stu-id="0a00a-210">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="0a00a-211">Ga naar het Compliancecentrum [https://compliance.microsoft.com](https://compliance.microsoft.com) () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="0a00a-211">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="0a00a-212">Kies **Beleid voor preventie van**  >    >  **gegevensverlies + Een beleid maken.**</span><span class="sxs-lookup"><span data-stu-id="0a00a-212">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span>

3. <span data-ttu-id="0a00a-213">Kies een [sjabloon](data-loss-prevention-policies.md#dlp-policy-templates)en kies vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="0a00a-213">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span>

    <span data-ttu-id="0a00a-214">In ons voorbeeld hebben we de sjabloon Voor persoonlijke gegevens in de VERENIGDE Staten gekozen.</span><span class="sxs-lookup"><span data-stu-id="0a00a-214">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a00a-215">![Privacysjabloon voor DLP-beleid](../media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="0a00a-215">![Privacy template for DLP policy](../media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="0a00a-216">Geef op **het tabblad Naam** uw beleid een naam en beschrijving op voor het beleid en kies **volgende**.</span><span class="sxs-lookup"><span data-stu-id="0a00a-216">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span>

5. <span data-ttu-id="0a00a-217">Houd op **het tabblad** Locaties kiezen de standaardinstelling van alle accounts of selecteer Laat me specifieke **locaties kiezen.**</span><span class="sxs-lookup"><span data-stu-id="0a00a-217">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="0a00a-218">U kunt het volgende opgeven:</span><span class="sxs-lookup"><span data-stu-id="0a00a-218">You can specify:</span></span>

    1. <span data-ttu-id="0a00a-219">maximaal 1000 afzonderlijke accounts om accounts op te nemen of uit te sluiten</span><span class="sxs-lookup"><span data-stu-id="0a00a-219">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="0a00a-220">distributielijsten en beveiligingsgroepen die u wilt opnemen of uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="0a00a-220">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="0a00a-221">**Dit is een openbare preview-functie.**</span><span class="sxs-lookup"><span data-stu-id="0a00a-221">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![DLP-beleidslocaties](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > <span data-ttu-id="0a00a-223">Als u wilt controleren of documenten met gevoelige informatie niet ongepast worden gedeeld in Teams, moet u ervoor zorgen dat **SharePoint-sites** en **OneDrive-accounts** zijn ingeschakeld, samen met **Teams chat-** en kanaalberichten.</span><span class="sxs-lookup"><span data-stu-id="0a00a-223">If you want to make sure documents that contain sensitive information are not shared inappropriately in Teams, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>

6. <span data-ttu-id="0a00a-224">Ga op **het tabblad Beleidsinstellingen** naar **Het type inhoud** aanpassen dat u wilt beveiligen, bewaar de standaard eenvoudige instellingen of kies Geavanceerde instellingen gebruiken **en** kies **volgende.**</span><span class="sxs-lookup"><span data-stu-id="0a00a-224">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="0a00a-225">Als u geavanceerde instellingen kiest, kunt u regels voor uw beleid maken of bewerken.</span><span class="sxs-lookup"><span data-stu-id="0a00a-225">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="0a00a-226">Zie Eenvoudige instellingen versus geavanceerde instellingen voor hulp [bij dit alles.](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)</span><span class="sxs-lookup"><span data-stu-id="0a00a-226">To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).</span></span>

7.  <span data-ttu-id="0a00a-227">Bekijk op **het tabblad** Beleidsinstellingen onder Wat wilt u doen als we gevoelige **informatie detecteren?** de instellingen.</span><span class="sxs-lookup"><span data-stu-id="0a00a-227">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="0a00a-228">Hier kunt u ervoor kiezen [](use-notifications-and-policy-tips.md)om standaardbeleidstips en e-mailmeldingen te bewaren of deze aan te passen.</span><span class="sxs-lookup"><span data-stu-id="0a00a-228">Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a00a-229">![DLP-beleidsinstellingen met tips en meldingen](../media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="0a00a-229">![DLP policy settings with tips and notifications](../media/dlp-teams-policysettings-tipsemails.png)</span></span>

    <span data-ttu-id="0a00a-230">Wanneer u klaar bent met het controleren of bewerken van instellingen, kiest u **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="0a00a-230">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="0a00a-231">Kies  op het tabblad Beleidsinstellingen onder Wilt u eerst het beleid in- of **testen?**, kies of u het beleid wilt in- of [uitschakelen,](dlp-overview-plan-for-dlp.md#policy-deployment)test het eerst of u het nu wilt uitschakelen en kies vervolgens **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0a00a-231">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](dlp-overview-plan-for-dlp.md#policy-deployment), or keep it turned off for now, and then choose **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a00a-232">![Opgeven of het beleid moet worden in- of uit-](../media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="0a00a-232">![Specify whether to turn the policy on](../media/dlp-teams-policysettings-turnonnow.png)</span></span>

9. <span data-ttu-id="0a00a-233">Bekijk op **het tabblad** Uw instellingen controleren de instellingen voor uw nieuwe beleid.</span><span class="sxs-lookup"><span data-stu-id="0a00a-233">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="0a00a-234">Kies **Bewerken om** wijzigingen aan te brengen.</span><span class="sxs-lookup"><span data-stu-id="0a00a-234">Choose **Edit** to make changes.</span></span> <span data-ttu-id="0a00a-235">Wanneer u klaar bent, kiest u **Maken.**</span><span class="sxs-lookup"><span data-stu-id="0a00a-235">When you're finished, choose **Create**.</span></span>

<span data-ttu-id="0a00a-236">Sta ongeveer één uur toe dat uw nieuwe beleid zijn weg door uw datacenter kan vinden en kan worden gesynchroniseerd met gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="0a00a-236">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="prevent-external-access-to-sensitive-documents"></a><span data-ttu-id="0a00a-237">Externe toegang tot gevoelige documenten voorkomen</span><span class="sxs-lookup"><span data-stu-id="0a00a-237">Prevent external access to sensitive documents</span></span>

<span data-ttu-id="0a00a-238">Als u wilt SharePoint documenten die gevoelige informatie bevatten, standaard niet kunnen worden gebruikt door externe gasten, SharePoint of Teams, selecteert u het volgende:</span><span class="sxs-lookup"><span data-stu-id="0a00a-238">To ensure that SharePoint documents that contain sensitive information cannot be accessed by external guests either from SharePoint or Teams by default, select the following:</span></span>

- <span data-ttu-id="0a00a-239">U kunt ervoor zorgen dat documenten worden beveiligd totdat DLP ze scant en markeert als veilig om te delen door nieuwe bestanden standaard als [gevoelig te markeren.](/sharepoint/sensitive-by-default)</span><span class="sxs-lookup"><span data-stu-id="0a00a-239">You can ensure that documents are protected until DLP scans and marks them as safe to share by [marking new files as sensitive by default](/sharepoint/sensitive-by-default).</span></span>

- <span data-ttu-id="0a00a-240">Aanbevolen DLP-beleidsstructuur</span><span class="sxs-lookup"><span data-stu-id="0a00a-240">Recommended DLP policy structure</span></span>

    - <span data-ttu-id="0a00a-241">**Voorwaarden**</span><span class="sxs-lookup"><span data-stu-id="0a00a-241">**Conditions**</span></span>
        - <span data-ttu-id="0a00a-242">Inhoud bevat een van deze gevoelige informatietypen: [Selecteer alles wat van toepassing is]</span><span class="sxs-lookup"><span data-stu-id="0a00a-242">Content contains any of these sensitive information types: [Select all that apply]</span></span>
        
        - <span data-ttu-id="0a00a-243">Inhoud wordt gedeeld vanuit Microsoft 365 met personen buiten mijn organisatie</span><span class="sxs-lookup"><span data-stu-id="0a00a-243">Content is shared from Microsoft 365 with people outside my organization</span></span>
        
          > [!div class="mx-imgBorder"]
          > <span data-ttu-id="0a00a-244">![DLP-voorwaarden voor het detecteren van extern delen van gevoelige inhoud](../media/dlp-teams-external-sharing/external-condition.png)</span><span class="sxs-lookup"><span data-stu-id="0a00a-244">![DLP conditions to detect external sharing of sensitive content](../media/dlp-teams-external-sharing/external-condition.png)</span></span>

    - <span data-ttu-id="0a00a-245">**Acties**</span><span class="sxs-lookup"><span data-stu-id="0a00a-245">**Actions**</span></span>
        - <span data-ttu-id="0a00a-246">Toegang tot de inhoud voor externe gebruikers beperken</span><span class="sxs-lookup"><span data-stu-id="0a00a-246">Restrict access to the content for external users</span></span>
        
        - <span data-ttu-id="0a00a-247">Gebruikers op de hoogte stellen met e-mail- en beleidstips</span><span class="sxs-lookup"><span data-stu-id="0a00a-247">Notify users with email and policy tips</span></span>
        
        - <span data-ttu-id="0a00a-248">Incidentrapporten verzenden naar de beheerder</span><span class="sxs-lookup"><span data-stu-id="0a00a-248">Send incident reports to the Administrator</span></span>
        
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="0a00a-249">![DLP-actie om extern delen van gevoelige inhoud te blokkeren](../media/dlp-teams-external-sharing/external-action.png)</span><span class="sxs-lookup"><span data-stu-id="0a00a-249">![DLP action to block external sharing of sensitive content](../media/dlp-teams-external-sharing/external-action.png)</span></span>

<span data-ttu-id="0a00a-250">DLP-beleid in actie bij het delen van een document in SharePoint met gevoelige informatie met een externe gast:</span><span class="sxs-lookup"><span data-stu-id="0a00a-250">DLP policy in action when attempting to share a document in SharePoint that contains sensitive information with an external guest:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0a00a-251">![Extern delen geblokkeerd](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="0a00a-251">![External sharing blocked](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span></span>


<span data-ttu-id="0a00a-252">DLP-beleid in actie wanneer gast probeert een document te openen in Teams met extern blokkeren:</span><span class="sxs-lookup"><span data-stu-id="0a00a-252">DLP policy in action when guest attempts to open a document in Teams with block external:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0a00a-253">![Externe toegang geblokkeerd](../media/dlp-teams-external-sharing/external-access-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="0a00a-253">![External access blocked](../media/dlp-teams-external-sharing/external-access-blocked.png)</span></span>

## <a name="related-articles"></a><span data-ttu-id="0a00a-254">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="0a00a-254">Related articles</span></span>

- [<span data-ttu-id="0a00a-255">Een DLP-beleid maken, testen en afstemmen</span><span class="sxs-lookup"><span data-stu-id="0a00a-255">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- <span data-ttu-id="0a00a-256">[Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md) (E-mailmeldingen verzenden en beleidstips tonen voor DLP-beleid)</span><span class="sxs-lookup"><span data-stu-id="0a00a-256">[Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md)</span></span>
