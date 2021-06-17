---
title: Uw gebeurtenishub configureren
description: Meer informatie over het configureren van uw Event Hub
keywords: event hub, configureren, inzichten
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.openlocfilehash: d28ad22721e22dfd0dc5962bd46bab2b45469781
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985585"
---
# <a name="configure-your-event-hub"></a><span data-ttu-id="b6df0-104">Uw gebeurtenishub configureren</span><span class="sxs-lookup"><span data-stu-id="b6df0-104">Configure your Event Hub</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b6df0-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b6df0-105">**Applies to:**</span></span>
- [<span data-ttu-id="b6df0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b6df0-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="b6df0-107">Meer informatie over het configureren van uw Event Hub, zodat deze gebeurtenissen kan opnemen vanuit Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="b6df0-107">Learn how to configure your Event Hub so that it can ingest events from Microsoft 365 Defender.</span></span>


## <a name="setup-the-required-resource-provider-in-the-event-hub-subscription"></a><span data-ttu-id="b6df0-108">De vereiste resourceprovider instellen in het Event Hub-abonnement</span><span class="sxs-lookup"><span data-stu-id="b6df0-108">Setup the required Resource Provider in the Event Hub subscription</span></span>


1. <span data-ttu-id="b6df0-109">Meld u aan bij [Azure Portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="b6df0-109">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
1. <span data-ttu-id="b6df0-110">Selecteer **Abonnementen { Selecteer het abonnement dat de \> ***gebeurtenishub zal worden geïmplementeerd bij***} \> Resourceproviders.**</span><span class="sxs-lookup"><span data-stu-id="b6df0-110">Select **Subscriptions \> {***Select the subscription the event hub will be deployed to***} \> Resource providers**.</span></span>
1. <span data-ttu-id="b6df0-111">Controleer of de **Microsoft.Insights-provider** is geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="b6df0-111">Verify that the **Microsoft.Insights** Provider is registered.</span></span> <span data-ttu-id="b6df0-112">Als u dit niet doet, registreert u het.</span><span class="sxs-lookup"><span data-stu-id="b6df0-112">Otherwise, register it.</span></span>

![Afbeelding van resourceproviders in Microsoft Azure](../../media/f893db7a7b1f7aa520e8b9257cc72562.png)

## <a name="setup-azure-active-directory-app-registration"></a><span data-ttu-id="b6df0-114">Installatie Azure Active Directory app-registratie</span><span class="sxs-lookup"><span data-stu-id="b6df0-114">Setup Azure Active Directory App Registration</span></span>


><span data-ttu-id="b6df0-115">! [OPMERKING] U moet de rol beheerder of Azure Active Directory (AAD) moeten zijn ingesteld zodat niet-beheerders apps kunnen registreren.</span><span class="sxs-lookup"><span data-stu-id="b6df0-115">![NOTE] You must have Administrator role or Azure Active Directory (AAD) must be set to allow non-Administrators to register apps.</span></span> <span data-ttu-id="b6df0-116">U moet ook een rol eigenaar of beheerder van Gebruikerstoegang hebben om de serviceprincipaal een rol toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="b6df0-116">You must also have an Owner or User Access Administrator role to assign the service principal a role.</span></span>  
><span data-ttu-id="b6df0-117">Zie Een [Azure AD-app maken & service principal in de portal - Microsoft identity platform Microsoft Docs voor \| meer informatie.](/azure/active-directory/develop/howto-create-service-principal-portal)</span><span class="sxs-lookup"><span data-stu-id="b6df0-117">For more information, see [Create an Azure AD app & service principal in the portal - Microsoft identity platform \| Microsoft Docs](/azure/active-directory/develop/howto-create-service-principal-portal).</span></span>

1. <span data-ttu-id="b6df0-118">Maak een nieuwe registratie (waarmee inherent een serviceprincipaal wordt gemaakt) in Azure Active Directory **\> App-registraties \> Nieuwe registratie.**</span><span class="sxs-lookup"><span data-stu-id="b6df0-118">Create a new registration (which inherently creates a service principal) in **Azure Active Directory \> App registrations \> New registration.**</span></span>

1. <span data-ttu-id="b6df0-119">Vul het formulier in met alleen de naam (omleidings-URI is niet vereist).</span><span class="sxs-lookup"><span data-stu-id="b6df0-119">Fill out the form with just the Name (no Redirect URI is required).</span></span>

    ![Afbeelding van een toepassing registreren](../../media/336bc84e6be23900c43232b4ef0c253c.png)

    ![Afbeelding van overzichtsgegevens](../../media/06ac04c4ff713c2065cec2ef2f99a294.png)

1. <span data-ttu-id="b6df0-122">Maak een geheim door te klikken op **Certificaten & nieuwe \> clientgeheim:**</span><span class="sxs-lookup"><span data-stu-id="b6df0-122">Create a secret by clicking on **Certificates & secrets \> New client secret**:</span></span>

    ![Afbeelding van certificaten en geheimen](../../media/d2ef88d3d2310d2c60c294b569cdf02e.png)

>[!WARNING]
><span data-ttu-id="b6df0-124">**U hebt geen toegang meer tot het clientgeheim,** dus sla het op.</span><span class="sxs-lookup"><span data-stu-id="b6df0-124">**You won't be able to access the client secret again so make sure to save it**.</span></span>

## <a name="setup-event-hub-namespace"></a><span data-ttu-id="b6df0-125">Setup Event Hub namespace</span><span class="sxs-lookup"><span data-stu-id="b6df0-125">Setup Event Hub namespace</span></span>


1. <span data-ttu-id="b6df0-126">Een naamruimte voor gebeurtenishubs maken:</span><span class="sxs-lookup"><span data-stu-id="b6df0-126">Create an Event Hub Namespace:</span></span>

    <span data-ttu-id="b6df0-127">Ga **naar Event Hubs \> Add** and select the pricing tier, throughput units and Auto-Inflate (requires standard pricing and under features) appropriate for the load you are expecting.</span><span class="sxs-lookup"><span data-stu-id="b6df0-127">Go **to Event Hubs \> Add** and select the pricing tier, throughput units and Auto-Inflate (requires standard pricing and under features) appropriate for the load you are expecting.</span></span>  
    <span data-ttu-id="b6df0-128">Zie Prijzen [- Event Hubs \| ](https://azure.microsoft.com/en-us/pricing/details/event-hubs/) Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="b6df0-128">For more information, see [Pricing - Event Hubs \| Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/)</span></span>

    >[!NOTE]
    > <span data-ttu-id="b6df0-129">U kunt een bestaande gebeurtenishub gebruiken, maar de doorvoer en schaal worden ingesteld op naamruimteniveau, dus het is raadzaam om een gebeurtenishub in de eigen naamruimte te plaatsen.</span><span class="sxs-lookup"><span data-stu-id="b6df0-129">You can use an existing event hub, but the throughput and scaling are set at the namespace level so it is recommended to place an event hub in itsown namespace.</span></span>

   ![Afbeelding van de naamruimte van gebeurtenishub](../../media/ebc4ca37c342ad1da75c4aee4018e51a.png)

1. <span data-ttu-id="b6df0-131">U hebt ook de resource-id van deze naamruimte voor gebeurtenishubs nodig.</span><span class="sxs-lookup"><span data-stu-id="b6df0-131">You will also need the Resource ID of this Event Hub Namespace.</span></span> <span data-ttu-id="b6df0-132">Ga naar de naamruimte-eigenschappen van de naamruimte van Azure Event \> Hubs.</span><span class="sxs-lookup"><span data-stu-id="b6df0-132">Go to your Azure Event Hubs namespace page \> Properties.</span></span> <span data-ttu-id="b6df0-133">Kopieer de tekst onder Resource-id en neem deze op voor gebruik tijdens de sectie Configuratie M365 hieronder.</span><span class="sxs-lookup"><span data-stu-id="b6df0-133">Copy the text under Resource ID and record it for use during the M365 Configuration section below.</span></span> 

    ![Afbeelding van eigenschappen](../../media/759498162a4e93cbf17c4130d704d164.png)

1. <span data-ttu-id="b6df0-135">Nadat de naamruimte van de gebeurtenishub is gemaakt, moet u de App Registration Service Principal toevoegen als lezer, Azure Event Hubs Data Receiver en de gebruiker die zich als inzender bij Microsoft 365 Defender zal aanmelden (dit kan ook op resourcegroep- of abonnementsniveau).</span><span class="sxs-lookup"><span data-stu-id="b6df0-135">Once the Event Hub Namespace is created you will need to add the App Registration Service Principal as Reader, Azure Event Hubs Data Receiver, and the user who will be logging into Microsoft 365 Defender as Contributor (this can also be done at Resource Group or Subscription level).</span></span>

    <span data-ttu-id="b6df0-136">Dit gebeurt in **Event Hubs Namespace \> Access Control (IAM) \> Add** and verify under **Role assignments**:</span><span class="sxs-lookup"><span data-stu-id="b6df0-136">This is done in **Event Hubs Namespace \> Access Control (IAM) \> Add** and verify under **Role assignments**:</span></span>

    ![Afbeelding van toegangsbeheer](../../media/9c9c29137b90d5858920202d87680d16.png)

## <a name="setup-event-hub"></a><span data-ttu-id="b6df0-138">Setup Event Hub</span><span class="sxs-lookup"><span data-stu-id="b6df0-138">Setup Event Hub</span></span>


<span data-ttu-id="b6df0-139">**Optie 1:**</span><span class="sxs-lookup"><span data-stu-id="b6df0-139">**Option 1:**</span></span>

<span data-ttu-id="b6df0-140">U kunt een gebeurtenishub maken in uw Naamruimte **en** alle gebeurtenistypen (tabellen) die u selecteert om te exporteren, worden in deze **ene** gebeurtenishub geschreven.</span><span class="sxs-lookup"><span data-stu-id="b6df0-140">You can create an Event Hub within your Namespace and **all** the Event Types (Tables) you select to export will be written into this **one** Event Hub.</span></span>

<span data-ttu-id="b6df0-141">**Optie 2:**</span><span class="sxs-lookup"><span data-stu-id="b6df0-141">**Option 2:**</span></span>

<span data-ttu-id="b6df0-142">In plaats van alle gebeurtenistypen (tabellen) te exporteren naar één gebeurtenishub, kunt u elke tabel exporteren naar een andere gebeurtenishub in de naamruimte van de gebeurtenishub (één gebeurtenishub per gebeurtenistype).</span><span class="sxs-lookup"><span data-stu-id="b6df0-142">Instead of exporting all the Event Types (Tables) into one Event Hub, you can export each table into a different Event Hub inside your Event Hub Namespace (one Event Hub per Event Type).</span></span>  

<span data-ttu-id="b6df0-143">In deze optie maakt Microsoft 365 Defender gebeurtenishubs voor u.</span><span class="sxs-lookup"><span data-stu-id="b6df0-143">In this option, Microsoft 365 Defender will create Event Hubs for you.</span></span>  
>[!NOTE]
> <span data-ttu-id="b6df0-144">Als u een naamruimte voor  gebeurtenishubs gebruikt die geen deel uitmaakt van een gebeurtenishubcluster, kunt u alleen maximaal 10 gebeurtenistypen (tabellen) kiezen om te exporteren in elke Export-Instellingen die u definieert, vanwege een Azure-beperking van 10 gebeurtenishubs per naamruimte voor gebeurtenishubs.</span><span class="sxs-lookup"><span data-stu-id="b6df0-144">If you are using an Event Hub Namespace that is **not** part of an Event Hub Cluster, you will only be able to choose up to 10 Event Types (Tables) to export in each Export Settings you define, due to an Azure limitation of 10 Event Hubs per Event Hub Namespace.</span></span>

<span data-ttu-id="b6df0-145">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="b6df0-145">For example:</span></span>

![Afbeelding van voorbeeldgebeurtenishub](../../media/005c1f6c10c34420d387f594987f9ffe.png)

<span data-ttu-id="b6df0-147">Als u deze optie kiest, kunt u naar de sectie Configureren [Microsoft 365 Defender om e-mailtabellen te](#configure-microsoft-365-defender-to-send-email-tables) verzenden.</span><span class="sxs-lookup"><span data-stu-id="b6df0-147">If you choose this option, you can skip to the [Configure Microsoft 365 Defender to send email tables](#configure-microsoft-365-defender-to-send-email-tables) section.</span></span>

<span data-ttu-id="b6df0-148">Maak een Event Hub in uw Naamruimte door **Event Hubs \> + Event Hub te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="b6df0-148">Create an Event Hub within your Namespace by selecting **Event Hubs \> + Event Hub**.</span></span>

<span data-ttu-id="b6df0-149">Het aantal partities zorgt voor extra doorvoer via parallelisme, dus het is raadzaam om dit aantal te verhogen op basis van de belasting die u verwacht.</span><span class="sxs-lookup"><span data-stu-id="b6df0-149">The Partition Count allows for additional throughput via parallelism, so it is recommended to increase this number based on the load you are expecting.</span></span>  
<span data-ttu-id="b6df0-150">Standaardwaarden voor het bewaren en vastleggen van berichten van 1 en Uit worden aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="b6df0-150">Default Message Retention and Capture values of 1 and Off are recommended.</span></span>

![Afbeelding van gebeurtenishub maken](../../media/1db04b8ec02a6298d7cc70419ac6e6a9.png)

<span data-ttu-id="b6df0-152">Voor deze gebeurtenishub (geen naamruimte) moet u een beleid voor gedeelde toegang configureren met Verzenden, Claims beluisteren.</span><span class="sxs-lookup"><span data-stu-id="b6df0-152">For this Event Hub (not namespace) you will need to configure a Shared Access Policy with Send, Listen Claims.</span></span> <span data-ttu-id="b6df0-153">Klik op het beleid voor gedeelde toegang van de gebeurtenishub **\> + \> Toevoegen** en geef het vervolgens een beleidsnaam (niet elders gebruikt) en controleer **Verzenden** en **luisteren.**</span><span class="sxs-lookup"><span data-stu-id="b6df0-153">Click on your **Event Hub \> Shared access policies \> + Add** and then give it a Policy name (not used elsewhere) and check **Send** and **Listen**.</span></span>

![Afbeelding van beleid voor gedeelde toegang](../../media/1867d13f46dc6a0f4cdae6cf00df24db.png)

## <a name="configure-microsoft-365-defender-to-send-email-tables"></a><span data-ttu-id="b6df0-155">E-Microsoft 365 Defender voor het verzenden van e-mailtabellen configureren</span><span class="sxs-lookup"><span data-stu-id="b6df0-155">Configure Microsoft 365 Defender to send email tables</span></span>


### <a name="setup-microsoft-365-defender-send-email-tables-to-splunk-via-event-hub"></a><span data-ttu-id="b6df0-156">Installatie Microsoft 365 Defender e-mailtabellen verzenden naar Splunk via Event Hub</span><span class="sxs-lookup"><span data-stu-id="b6df0-156">Setup Microsoft 365 Defender send Email tables to Splunk via Event Hub</span></span>


1. <span data-ttu-id="b6df0-157">Meld u aan Microsoft 365 Defender <https://security.microsoft.com> bij met een account dat voldoet aan alle volgende rolvereisten:</span><span class="sxs-lookup"><span data-stu-id="b6df0-157">Login to Microsoft 365 Defender at <https://security.microsoft.com> with an account that meets all the following role requirements:</span></span>

    - <span data-ttu-id="b6df0-158">Inzenderrol op het resourceniveau *Van gebeurtenishub-naamruimte* of hoger voor de gebeurtenishub waar u naar wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="b6df0-158">Contributor role at the Event Hub *Namespace* Resource level or higher for the Event Hub that you will be exporting to.</span></span> <span data-ttu-id="b6df0-159">Zonder deze optie krijgt u een exportfout wanneer u de instellingen probeert op te slaan.</span><span class="sxs-lookup"><span data-stu-id="b6df0-159">Without this you will get an export error when you try to save the settings.</span></span>

    - <span data-ttu-id="b6df0-160">Global Admin or Security Admin Role on the tenant tied to Microsoft 365 Defender and Azure.</span><span class="sxs-lookup"><span data-stu-id="b6df0-160">Global Admin or Security Admin Role on the tenant tied to Microsoft 365 Defender and Azure.</span></span>

    ![Afbeelding van beveiligingsportal](../../media/55d5b1c21dd58692fb12a6c1c35bd4fa.png)

1. <span data-ttu-id="b6df0-162">Klik op **Raw Data Export \> +Add**.</span><span class="sxs-lookup"><span data-stu-id="b6df0-162">Click on **Raw Data Export \> +Add**.</span></span>

    <span data-ttu-id="b6df0-163">U gebruikt nu de gegevens die u hierboven hebt opgenomen.</span><span class="sxs-lookup"><span data-stu-id="b6df0-163">You will now use the data that your recorded above.</span></span>

    <span data-ttu-id="b6df0-164">**Naam:** Dit is lokaal en moet alles zijn wat in uw omgeving werkt.</span><span class="sxs-lookup"><span data-stu-id="b6df0-164">**Name**: This is local and should be whatever works in your environment.</span></span>

    <span data-ttu-id="b6df0-165">**Gebeurtenissen doorsturen naar gebeurtenishub:** Schakel dit selectievakje in.</span><span class="sxs-lookup"><span data-stu-id="b6df0-165">**Forward events to event hub**: Select this checkbox.</span></span>

    <span data-ttu-id="b6df0-166">**Event-Hub Resource-id:** dit is de naamruimteresource-id voor gebeurtenishub die u hierboven hebt opgenomen bij het instellen van de gebeurtenishub.</span><span class="sxs-lookup"><span data-stu-id="b6df0-166">**Event-Hub Resource ID**: This is the Event Hub Namespace Resource ID you  recorded above when you setup the Event Hub.</span></span>

    <span data-ttu-id="b6df0-167">**Naam van gebeurtenis-hub:** Als u een gebeurtenishub hebt gemaakt in de naamruimte van de gebeurtenishub, plakt u de naam Event Hub die u hierboven hebt opgenomen.</span><span class="sxs-lookup"><span data-stu-id="b6df0-167">**Event-Hub name**:  If you created an Event Hub inside your Event Hub Namespace, paste the Event Hub  name you recorded above.</span></span>

    <span data-ttu-id="b6df0-168">Als u ervoor kiest om Microsoft 365 Defender gebeurtenishubs per gebeurtenistypen (tabellen) voor u te laten maken, laat u dit veld leeg.</span><span class="sxs-lookup"><span data-stu-id="b6df0-168">If you choose to let Microsoft 365 Defender to create Event Hubs per Event Types  (Tables) for you, leave this field empty.</span></span>

    <span data-ttu-id="b6df0-169">**Gebeurtenistypen:** Selecteer de geavanceerde zoektabellen die u wilt doorsturen naar de gebeurtenishub en ga vervolgens verder met uw aangepaste app.</span><span class="sxs-lookup"><span data-stu-id="b6df0-169">**Event Types**: Select the Advanced Hunting tables that you want to forward to the Event Hub and then on to your custom app.</span></span> <span data-ttu-id="b6df0-170">Waarschuwingstabellen zijn afkomstig Microsoft 365 Defender, Apparatentabellen zijn afkomstig van Microsoft Defender voor Eindpunt (EDR) en E-mailtabellen zijn afkomstig van Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="b6df0-170">Alert tables are from Microsoft 365 Defender, Devices tables are from Microsoft Defender for Endpoint (EDR), and Email tables are from Microsoft Defender for Office 365.</span></span> <span data-ttu-id="b6df0-171">E-mailgebeurtenissen registreert alle e-mailtransacties.</span><span class="sxs-lookup"><span data-stu-id="b6df0-171">Email Events records all Email Transactions.</span></span> <span data-ttu-id="b6df0-172">De URL (SafeLinks), Bijlage (Safe Bijlagen) en Post Delivery Events (ZAP) worden ook opgenomen en kunnen worden gekoppeld aan het veld E-mailgebeurtenissen in het veld NetworkMessageId.</span><span class="sxs-lookup"><span data-stu-id="b6df0-172">The URL (SafeLinks), Attachment (Safe Attachments) and Post Delivery Events (ZAP) are also recorded and can be joined to the Email Events on the NetworkMessageId field.</span></span>

    ![Afbeelding van streaming API-instellingen](../../media/3b2ad64b6ef0f88cf0175f8d57ef8b97.png)

1. <span data-ttu-id="b6df0-174">Klik op **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="b6df0-174">Make sure to click **Submit**.</span></span>

### <a name="verify-that-the-events-are-being-exported-to-the-event-hub"></a><span data-ttu-id="b6df0-175">Controleren of de gebeurtenissen worden geëxporteerd naar de gebeurtenishub</span><span class="sxs-lookup"><span data-stu-id="b6df0-175">Verify that the events are being exported to the Event Hub</span></span>


<span data-ttu-id="b6df0-176">U kunt controleren of gebeurtenissen naar de gebeurtenishub worden verzonden door een basisquery geavanceerd zoeken uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="b6df0-176">You can verify that events are being sent to the Event Hub by running a basic Advanced Hunting query.</span></span> <span data-ttu-id="b6df0-177">Selecteer **Geavanceerde \> \> huntingquery en** voer de volgende query in:</span><span class="sxs-lookup"><span data-stu-id="b6df0-177">Select **Hunting \> Advanced Hunting \> Query** and enter the following query:</span></span>

```
EmailEvents
|joinkind=fullouterEmailAttachmentInfoonNetworkMessageId
|joinkind=fullouterEmailUrlInfoonNetworkMessageId
|joinkind=fullouterEmailPostDeliveryEventsonNetworkMessageId
|whereTimestamp\>ago(1h)
|count
```

<span data-ttu-id="b6df0-178">Op deze manier ziet u hoeveel e-mailberichten er in het laatste uur zijn ontvangen en hoeveel e-mailberichten in alle andere tabellen zijn samengevoegd.</span><span class="sxs-lookup"><span data-stu-id="b6df0-178">This will show you how many emails were received in the last hour joined across all the other tables.</span></span> <span data-ttu-id="b6df0-179">U ziet ook of u gebeurtenissen ziet die naar de gebeurtenishub kunnen worden geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="b6df0-179">It will also show you if you are seeing events that could be exported to the event hub.</span></span> <span data-ttu-id="b6df0-180">Als dit aantal 0 laat zien, ziet u geen gegevens die naar de gebeurtenishub gaan.</span><span class="sxs-lookup"><span data-stu-id="b6df0-180">If this count shows 0 then you won't see any data going out to the Event Hub.</span></span>

![Afbeelding van geavanceerde jacht](../../media/c305e57dc6f72fa9eb035943f244738e.png)

<span data-ttu-id="b6df0-182">Nadat u hebt geverifieerd dat er gegevens moeten worden geëxporteerd, kunt u de gebeurtenishub bekijken om te controleren of berichten binnenkomen.</span><span class="sxs-lookup"><span data-stu-id="b6df0-182">Once you have verified there is data to export, you can view the Event Hub to verify that messages are incoming.</span></span> <span data-ttu-id="b6df0-183">Dit kan maximaal één uur duren.</span><span class="sxs-lookup"><span data-stu-id="b6df0-183">This can take up to one hour.</span></span> 
 
1. <span data-ttu-id="b6df0-184">Ga in Azure naar **Event Hubs \> Klik op de Namespace Event \> Hubs Klik op de Event \> Hub.**</span><span class="sxs-lookup"><span data-stu-id="b6df0-184">In Azure, go to **Event Hubs \> Click on the Namespace \> Event Hubs \> Click on the Event Hub**.</span></span>  
1. <span data-ttu-id="b6df0-185">Schuif **onder** Overzicht omlaag en in de grafiek Berichten ziet u Inkomende berichten.</span><span class="sxs-lookup"><span data-stu-id="b6df0-185">Under **Overview**, scroll down and in the Messages graph you should see Incoming Messages.</span></span> <span data-ttu-id="b6df0-186">Als u geen resultaten ziet, worden er geen berichten voor de aangepaste app opgenomen.</span><span class="sxs-lookup"><span data-stu-id="b6df0-186">If you don't see any results, then there will be no messages for your custom app to ingest.</span></span>

    ![Afbeelding van het overzichtstabblad met berichten](../../media/e88060e315d76e74269a3fc866df047f.png)
