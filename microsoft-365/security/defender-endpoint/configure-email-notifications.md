---
title: Waarschuwingsmeldingen configureren in Microsoft Defender voor Eindpunt
description: U kunt Microsoft Defender voor Eindpunt gebruiken om instellingen voor e-mailmeldingen te configureren voor beveiligingswaarschuwingen, op basis van ernst en andere criteria.
keywords: e-mailmeldingen, waarschuwingsmeldingen configureren, Microsoft Defender voor eindpunten, Microsoft Defender voor eindpuntmeldingen, Microsoft Defender voor eindpuntwaarschuwingen, Windows 10 Enterprise, Windows 10 Education
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2b638742e29d5ca0a8b74adfa6796380114d24a3
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339500"
---
# <a name="configure-alert-notifications-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="64c59-104">Waarschuwingsmeldingen configureren in Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="64c59-104">Configure alert notifications in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="64c59-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="64c59-105">**Applies to:**</span></span>
- [<span data-ttu-id="64c59-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="64c59-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="64c59-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64c59-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="64c59-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="64c59-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="64c59-109">Meld u aan voor een gratis proefversie.</span><span class="sxs-lookup"><span data-stu-id="64c59-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-emailconfig-abovefoldlink)

<span data-ttu-id="64c59-110">U kunt Defender voor Eindpunt zo configureren dat e-mailmeldingen worden verzonden naar opgegeven geadresseerden voor nieuwe waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="64c59-110">You can configure Defender for Endpoint to send email notifications to specified recipients for new alerts.</span></span> <span data-ttu-id="64c59-111">Met deze functie kunt u een groep personen identificeren die onmiddellijk worden geïnformeerd en die kunnen reageren op waarschuwingen op basis van hun ernst.</span><span class="sxs-lookup"><span data-stu-id="64c59-111">This feature enables you to identify a group of individuals who will immediately be informed and can act on alerts based on their severity.</span></span>

> [!NOTE]
> <span data-ttu-id="64c59-112">Alleen gebruikers met machtigingen voor beveiligingsinstellingen beheren kunnen e-mailmeldingen configureren.</span><span class="sxs-lookup"><span data-stu-id="64c59-112">Only users with 'Manage security settings' permissions can configure email notifications.</span></span> <span data-ttu-id="64c59-113">Als u ervoor hebt gekozen om basismachtigingenbeheer te gebruiken, kunnen gebruikers met beveiligingsbeheerder- of globale beheerdersrollen e-mailmeldingen configureren.</span><span class="sxs-lookup"><span data-stu-id="64c59-113">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications.</span></span>

<span data-ttu-id="64c59-114">U kunt de ernstniveaus voor waarschuwingen instellen die meldingen activeren.</span><span class="sxs-lookup"><span data-stu-id="64c59-114">You can set the alert severity levels that trigger notifications.</span></span> <span data-ttu-id="64c59-115">U kunt ook geadresseerden van de e-mailmelding toevoegen of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="64c59-115">You can also add or remove recipients of the email notification.</span></span> <span data-ttu-id="64c59-116">Nieuwe geadresseerden krijgen een melding over waarschuwingen die worden geactiveerd nadat ze zijn toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="64c59-116">New recipients get notified about alerts triggered after they're added.</span></span> <span data-ttu-id="64c59-117">Zie De wachtrij Waarschuwingen weergeven en organiseren voor meer informatie over [waarschuwingen.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="64c59-117">For more information about alerts, see [View and organize the Alerts queue](alerts-queue.md).</span></span>

<span data-ttu-id="64c59-118">Als u RBAC (Role Based Access Control) gebruikt, ontvangen geadresseerden alleen meldingen op basis van de apparaatgroepen die zijn geconfigureerd in de meldingsregel.</span><span class="sxs-lookup"><span data-stu-id="64c59-118">If you're using role-based access control (RBAC), recipients will only receive notifications based on the device groups that were configured in the notification rule.</span></span>
<span data-ttu-id="64c59-119">Gebruikers met de juiste machtigingen kunnen alleen meldingen maken, bewerken of verwijderen die zijn beperkt tot het beheerbereik van hun apparaatgroep.</span><span class="sxs-lookup"><span data-stu-id="64c59-119">Users with the proper permission can only create, edit, or delete notifications that are limited to their device group management scope.</span></span>
<span data-ttu-id="64c59-120">Alleen gebruikers die zijn toegewezen aan de rol globale beheerder kunnen meldingsregels beheren die zijn geconfigureerd voor alle apparaatgroepen.</span><span class="sxs-lookup"><span data-stu-id="64c59-120">Only users assigned to the Global administrator role can manage notification rules that are configured for all device groups.</span></span>

<span data-ttu-id="64c59-121">De e-mailmelding bevat basisinformatie over de waarschuwing en een koppeling naar de portal waar u verder onderzoek kunt doen.</span><span class="sxs-lookup"><span data-stu-id="64c59-121">The email notification includes basic information about the alert and a link to the portal where you can do further investigation.</span></span>

## <a name="create-rules-for-alert-notifications"></a><span data-ttu-id="64c59-122">Regels voor waarschuwingsmeldingen maken</span><span class="sxs-lookup"><span data-stu-id="64c59-122">Create rules for alert notifications</span></span>
<span data-ttu-id="64c59-123">U kunt regels maken om de ernst van de apparaten en waarschuwingen te bepalen voor het verzenden van e-mailmeldingen voor en de geadresseerden van de melding.</span><span class="sxs-lookup"><span data-stu-id="64c59-123">You can create rules that determine the devices and alert severities to send email notifications for and the notification recipients.</span></span>


1. <span data-ttu-id="64c59-124">Selecteer in het navigatiedeelvenster **Instellingen** algemene e-mailmeldingen  >    >    >  **voor eindpunten.**</span><span class="sxs-lookup"><span data-stu-id="64c59-124">In the navigation pane, select **Settings** > **Endpoints** > **General** > **Email notifications**.</span></span>

2. <span data-ttu-id="64c59-125">Klik **op Item toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="64c59-125">Click **Add item**.</span></span>

3. <span data-ttu-id="64c59-126">Geef de algemene gegevens op:</span><span class="sxs-lookup"><span data-stu-id="64c59-126">Specify the General information:</span></span>
    - <span data-ttu-id="64c59-127">**Regelnaam:** geef een naam op voor de meldingsregel.</span><span class="sxs-lookup"><span data-stu-id="64c59-127">**Rule name** - Specify a name for the notification rule.</span></span>
    - <span data-ttu-id="64c59-128">**Naam van organisatie opnemen:** geef de klantnaam op die wordt weergegeven in de e-mailmelding.</span><span class="sxs-lookup"><span data-stu-id="64c59-128">**Include organization name** - Specify the customer name that appears on the email notification.</span></span>
    - <span data-ttu-id="64c59-129">**Tenantspecifieke portalkoppeling opnemen:** hiermee voegt u een koppeling met de tenant-id toe om toegang tot een specifieke tenant toe te staan.</span><span class="sxs-lookup"><span data-stu-id="64c59-129">**Include tenant-specific portal link** - Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    - <span data-ttu-id="64c59-130">**Apparaatgegevens opnemen** : bevat de naam van het apparaat in de instantie voor e-mailmelding.</span><span class="sxs-lookup"><span data-stu-id="64c59-130">**Include device information** - Includes the device name in the email alert body.</span></span>

        > [!NOTE]
        > <span data-ttu-id="64c59-131">Deze gegevens kunnen worden verwerkt door e-mailservers van geadresseerden die niet op de geografische locatie staan die u hebt geselecteerd voor uw Defender voor eindpuntgegevens.</span><span class="sxs-lookup"><span data-stu-id="64c59-131">This information might be processed by recipient mail servers that ar not in the geographic location you have selected for your Defender for Endpoint data.</span></span>

    - <span data-ttu-id="64c59-132">**Apparaten:** kies of geadresseerden moeten worden gewaarschuwd voor waarschuwingen op alle apparaten (alleen globale beheerdersrol) of op geselecteerde apparaatgroepen.</span><span class="sxs-lookup"><span data-stu-id="64c59-132">**Devices** - Choose whether to notify recipients for alerts on all devices (Global administrator role only) or on selected device groups.</span></span> <span data-ttu-id="64c59-133">Zie Apparaatgroepen maken en beheren voor meer [informatie.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="64c59-133">For more information, see [Create and manage device groups](machine-groups.md).</span></span>
    - <span data-ttu-id="64c59-134">**Ernst van waarschuwing:** kies het ernstniveau van de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="64c59-134">**Alert severity** - Choose the alert severity level.</span></span>

4. <span data-ttu-id="64c59-135">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="64c59-135">Click **Next**.</span></span>

5. <span data-ttu-id="64c59-136">Voer het e-mailadres van de geadresseerde in en klik op **Geadresseerde toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="64c59-136">Enter the recipient's email address then click **Add recipient**.</span></span> <span data-ttu-id="64c59-137">U kunt meerdere e-mailadressen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="64c59-137">You can add multiple email addresses.</span></span>

6. <span data-ttu-id="64c59-138">Controleer of e-mailontvangers de e-mailmeldingen kunnen ontvangen door **Test-e-mail verzenden te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="64c59-138">Check that email recipients can receive the email notifications by selecting **Send test email**.</span></span>

7. <span data-ttu-id="64c59-139">Klik **op Meldingsregel opslaan.**</span><span class="sxs-lookup"><span data-stu-id="64c59-139">Click **Save notification rule**.</span></span>

## <a name="edit-a-notification-rule"></a><span data-ttu-id="64c59-140">Een meldingsregel bewerken</span><span class="sxs-lookup"><span data-stu-id="64c59-140">Edit a notification rule</span></span>

1. <span data-ttu-id="64c59-141">Selecteer de meldingsregel die u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="64c59-141">Select the notification rule you'd like to edit.</span></span>

2. <span data-ttu-id="64c59-142">Werk de tabbladgegevens Algemeen en Geadresseerde bij.</span><span class="sxs-lookup"><span data-stu-id="64c59-142">Update the General and Recipient tab information.</span></span>

3. <span data-ttu-id="64c59-143">Klik **op Meldingsregel opslaan.**</span><span class="sxs-lookup"><span data-stu-id="64c59-143">Click **Save notification rule**.</span></span>

## <a name="delete-notification-rule"></a><span data-ttu-id="64c59-144">Meldingsregel verwijderen</span><span class="sxs-lookup"><span data-stu-id="64c59-144">Delete notification rule</span></span>

1. <span data-ttu-id="64c59-145">Selecteer de meldingsregel die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="64c59-145">Select the notification rule you'd like to delete.</span></span>

2. <span data-ttu-id="64c59-146">Klik op **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="64c59-146">Click **Delete**.</span></span>

## <a name="troubleshoot-email-notifications-for-alerts"></a><span data-ttu-id="64c59-147">Problemen met e-mailmeldingen oplossen voor waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="64c59-147">Troubleshoot email notifications for alerts</span></span>

<span data-ttu-id="64c59-148">In deze sectie worden verschillende problemen vermeld die u kunt tegenkomen bij het gebruik van e-mailmeldingen voor waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="64c59-148">This section lists various issues that you may encounter when using email notifications for alerts.</span></span>

<span data-ttu-id="64c59-149">**Probleem:** Beoogde geadresseerden melden dat ze de meldingen niet ontvangen.</span><span class="sxs-lookup"><span data-stu-id="64c59-149">**Problem:** Intended recipients report they're not getting the notifications.</span></span>

<span data-ttu-id="64c59-150">**Oplossing:** Zorg ervoor dat de meldingen niet worden geblokkeerd door e-mailfilters:</span><span class="sxs-lookup"><span data-stu-id="64c59-150">**Solution:** Make sure that the notifications aren't blocked by email filters:</span></span>

1. <span data-ttu-id="64c59-151">Controleer of de e-mailmeldingen van Defender voor Eindpunt niet naar de map Ongewenste e-mail worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="64c59-151">Check that the Defender for Endpoint email notifications aren't sent to the Junk Email folder.</span></span> <span data-ttu-id="64c59-152">Markeer ze als Geen ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="64c59-152">Mark them as Not junk.</span></span>
2. <span data-ttu-id="64c59-153">Controleer of uw e-mailbeveiligingsproduct de e-mailmeldingen van Defender voor Eindpunt niet blokkeert.</span><span class="sxs-lookup"><span data-stu-id="64c59-153">Check that your email security product isn't blocking the email notifications from Defender for Endpoint.</span></span>
3. <span data-ttu-id="64c59-154">Controleer de regels voor e-mailtoepassing die mogelijk uw Defender voor endpoint-e-mailmeldingen kunnen vangen en verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="64c59-154">Check your email application rules that might be catching and moving your Defender for Endpoint email notifications.</span></span>

## <a name="related-topics"></a><span data-ttu-id="64c59-155">Gerelateerde onderwerpen</span><span class="sxs-lookup"><span data-stu-id="64c59-155">Related topics</span></span>

- [<span data-ttu-id="64c59-156">Instellingen voor gegevensretentie bijwerken</span><span class="sxs-lookup"><span data-stu-id="64c59-156">Update data retention settings</span></span>](data-retention-settings.md)
- [<span data-ttu-id="64c59-157">Geavanceerde functies configureren</span><span class="sxs-lookup"><span data-stu-id="64c59-157">Configure advanced features</span></span>](advanced-features.md)
- [<span data-ttu-id="64c59-158">Meldingen van beveiligingsleed configureren in Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="64c59-158">Configure vulnerability email notifications in Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/configure-vulnerability-email-notifications)
