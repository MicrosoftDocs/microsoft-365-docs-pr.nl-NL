---
title: Werken met een partner voor het archiveren van gegevens van derden
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Meer informatie over het instellen van een aangepaste connector om gegevens van derden te importeren uit gegevensbronnen zoals Salesforce Chatter, Yahoo Messenger of Yammer.
ms.openlocfilehash: 2026e3c584cb0bc467a2db3903c51b7ed50e51e1
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228757"
---
# <a name="work-with-a-partner-to-archive-third-party-data"></a><span data-ttu-id="c4f1d-103">Werken met een partner voor het archiveren van gegevens van derden</span><span class="sxs-lookup"><span data-stu-id="c4f1d-103">Work with a partner to archive third-party data</span></span>

<span data-ttu-id="c4f1d-104">U kunt met een Microsoft-partner werken om gegevens uit een externe gegevensbron te importeren en te archiveren Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-104">You can work with a Microsoft Partner to import and archive data from a third-party data source to Microsoft 365.</span></span> <span data-ttu-id="c4f1d-105">Een partner kan u een aangepaste verbindingslijn bieden die is geconfigureerd om items uit de gegevensbron van derden op te halen (op regelmatige basis) en vervolgens deze items te importeren.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-105">A partner can provide you with a custom connector that is configured to extract items from the third-party data source (on a regular basis) and then import those items.</span></span> <span data-ttu-id="c4f1d-106">De partnerconnector converteert de inhoud van een item uit de gegevensbron naar een e-mailberichtindeling en slaat de items vervolgens op in postvakken.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-106">The partner connector converts the content of an item from the data source to an email message format and then stores the items in mailboxes.</span></span> <span data-ttu-id="c4f1d-107">Nadat gegevens van derden zijn geïmporteerd, kunt u Microsoft 365 compliancefuncties zoals Litigation Hold, eDiscovery, In-Place Archiving, Auditing en Microsoft 365 bewaarbeleid toepassen op deze gegevens.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-107">After third-party data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, In-Place Archiving, Auditing, and Microsoft 365 retention policies to this data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c4f1d-108">De [communicatie complianceoplossing](communication-compliance.md) in Microsoft 365 kan niet worden toegepast op de gegevens van derden die zijn geïmporteerd door partnerconnectoren die in dit artikel worden vermeld.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-108">The [Communication compliance](communication-compliance.md) solution in Microsoft 365 can't be applied to the third-party data imported by partner connectors mentioned in this article.</span></span>

<span data-ttu-id="c4f1d-109">Hier volgen een overzicht van het proces en de stappen die nodig zijn om samen met een Microsoft-partner gegevens van derden te importeren.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-109">Here's an overview of the process and the steps necessary to work with a Microsoft Partner to import third-party data.</span></span>

[<span data-ttu-id="c4f1d-110">Stap 1: Een externe gegevenspartner zoeken</span><span class="sxs-lookup"><span data-stu-id="c4f1d-110">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="c4f1d-111">Stap 2: Een gegevenspostvak van derden maken en configureren</span><span class="sxs-lookup"><span data-stu-id="c4f1d-111">Step 2: Create and configure a third-party data mailbox</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365)

[<span data-ttu-id="c4f1d-112">Stap 3: Gebruikerspostvakken configureren voor gegevens van derden</span><span class="sxs-lookup"><span data-stu-id="c4f1d-112">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="c4f1d-113">Stap 4: Geef uw partner informatie</span><span class="sxs-lookup"><span data-stu-id="c4f1d-113">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="c4f1d-114">Stap 5: De gegevensconnector van derden registreren in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c4f1d-114">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="c4f1d-115">Hoe het gegevensimportproces van derden werkt</span><span class="sxs-lookup"><span data-stu-id="c4f1d-115">How the third-party data import process works</span></span>

<span data-ttu-id="c4f1d-116">In de volgende afbeelding en beschrijving wordt uitgelegd hoe het importproces voor gegevens van derden werkt wanneer u met een partner werkt.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-116">The following illustration and description explain how the third-party data import process works when working with a partner.</span></span>

![Hoe het gegevensimportproces van derden werkt](../media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)

1. <span data-ttu-id="c4f1d-118">De klant werkt samen met zijn of haar partner om een connector te configureren die items uit de gegevensbron van derden haalt en vervolgens deze items importeert in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-118">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Microsoft 365.</span></span>

2. <span data-ttu-id="c4f1d-119">De partnerconnector maakt verbinding met gegevensbronnen van derden via een API van derden (gepland of geconfigureerd) en haalt items uit de gegevensbron op.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-119">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source.</span></span> <span data-ttu-id="c4f1d-120">De partnerconnector converteert de inhoud van een item naar een e-mailberichtindeling.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-120">The partner connector converts the content of an item to an email message format.</span></span> <span data-ttu-id="c4f1d-121">Zie de [sectie Meer informatie](#more-information) voor een beschrijving van het schema voor berichtindeling.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-121">See the [More information](#more-information) section for a description of the message-format schema.</span></span>

3. <span data-ttu-id="c4f1d-122">Partnerconnector maakt verbinding met de Azure-service in Microsoft 365 via Exchange Web Service (EWS) via een bekend eindpunt.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-122">Partner connector connects to the Azure service in Microsoft 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>

4. <span data-ttu-id="c4f1d-123">Items worden geïmporteerd in het postvak van een specifieke gebruiker of in een 'catch-all' gegevenspostvak van derden.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-123">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox.</span></span> <span data-ttu-id="c4f1d-124">Of een item wordt geïmporteerd in een specifiek gebruikerspostvak of in het gegevenspostvak van derden, is gebaseerd op de volgende criteria:</span><span class="sxs-lookup"><span data-stu-id="c4f1d-124">Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>

   1. <span data-ttu-id="c4f1d-125">**Items met een gebruikers-id die overeenkomt met een gebruikersaccount:** Als de partnerconnector de gebruikers-id van het item in de gegevensbron van derden kan in kaart brengen aan een specifieke gebruikers-id in Microsoft 365, wordt het item gekopieerd naar de map **Purges** in de map Herstelbare items van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-125">**Items that have a user ID that corresponds to a user account:** If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Microsoft 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="c4f1d-126">Gebruikers hebben geen toegang tot items in de map Purges.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-126">Users can't access items in the Purges folder.</span></span> <span data-ttu-id="c4f1d-127">U kunt echter eDiscovery-hulpprogramma's gebruiken om te zoeken naar items in de map Purges.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-127">However, you can use eDiscovery tools to search for items in the Purges folder.</span></span>

   1. <span data-ttu-id="c4f1d-128">**Items die geen gebruikers-id hebben die overeenkomen met een gebruikersaccount:** Als de partnerconnector de gebruikers-id van een item niet aan een specifieke gebruikers-id kan toevoegen, wordt het item gekopieerd naar de map **Postvak IN** van het gegevenspostvak van derden.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-128">**Items that don't have a user ID that corresponds to a user account:** If the partner connector can't map the user ID of an item to a specific user ID, the item is copied to the **Inbox** folder of the third-party data mailbox.</span></span> <span data-ttu-id="c4f1d-129">Als u items importeert in het Postvak IN, kunt u of iemand in uw organisatie zich aanmelden bij het postvak van derden om deze items weer te geven en te beheren, en te kijken of er wijzigingen moeten worden aangebracht in de configuratie van de partnerconnector.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-129">Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>

## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="c4f1d-130">Stap 1: Een externe gegevenspartner zoeken</span><span class="sxs-lookup"><span data-stu-id="c4f1d-130">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="c4f1d-131">Een belangrijk onderdeel voor het archiveren van gegevens van derden in Microsoft 365 is het zoeken en werken met een Microsoft-partner die zich specialiseert in het vastleggen van gegevens van een externe gegevensbron en het importeren ervan in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-131">A key component for archiving third-party data in Microsoft 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Microsoft 365.</span></span> <span data-ttu-id="c4f1d-132">Nadat de gegevens zijn geïmporteerd, kunnen deze worden gearchiveerd en bewaard, samen met de andere Microsoft-gegevens van uw organisatie, zoals e-mail van Exchange en documenten uit SharePoint en OneDrive voor Bedrijven.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-132">After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="c4f1d-133">Een partner maakt een verbindingslijn die gegevens uit de gegevensbronnen van derden van uw organisatie haalt (zoals BlackBerry, Facebook, Google+, Thomson Reuters, Twitter en YouTube) en deze gegevens doorverzend naar een Microsoft 365-API die items importeert naar Exchange-postvakken als e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-133">A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to a Microsoft 365 API that imports items to Exchange mailboxes as email messages.</span></span>

<span data-ttu-id="c4f1d-134">In de volgende secties worden de Microsoft-partners (en de gegevensbronnen van derden die ze ondersteunen) vermeld die deelnemen aan het programma voor het archiveren van gegevens van derden in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-134">The following sections list the Microsoft partners (and the third-party data sources they support) that are participating in the program for archiving third-party data in Microsoft 365.</span></span>

[<span data-ttu-id="c4f1d-135">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="c4f1d-135">17a-4 LLC</span></span>](#17a-4-llc)

[<span data-ttu-id="c4f1d-136">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="c4f1d-136">ArchiveSocial</span></span>](#archivesocial)

[<span data-ttu-id="c4f1d-137">Veritas</span><span class="sxs-lookup"><span data-stu-id="c4f1d-137">Veritas</span></span>](#veritas)

[<span data-ttu-id="c4f1d-138">OpenText</span><span class="sxs-lookup"><span data-stu-id="c4f1d-138">OpenText</span></span>](#opentext)

[<span data-ttu-id="c4f1d-139">Smarsh</span><span class="sxs-lookup"><span data-stu-id="c4f1d-139">Smarsh</span></span>](#smarsh)

[<span data-ttu-id="c4f1d-140">Verba</span><span class="sxs-lookup"><span data-stu-id="c4f1d-140">Verba</span></span>](#verba)

### <a name="17a-4-llc"></a><span data-ttu-id="c4f1d-141">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="c4f1d-141">17a-4 LLC</span></span>

<span data-ttu-id="c4f1d-142">[17a-4 LLC](https://www.17a-4.com) ondersteunt de volgende gegevensbronnen van derden:</span><span class="sxs-lookup"><span data-stu-id="c4f1d-142">[17a-4 LLC](https://www.17a-4.com) supports the following third-party data sources:</span></span>

- <span data-ttu-id="c4f1d-143">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="c4f1d-143">BlackBerry</span></span>

- <span data-ttu-id="c4f1d-144">Gegevens van Bloomberg Streams</span><span class="sxs-lookup"><span data-stu-id="c4f1d-144">Bloomberg Data Streams</span></span>

- <span data-ttu-id="c4f1d-145">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="c4f1d-145">Cisco Jabber</span></span>

- <span data-ttu-id="c4f1d-146">FactSet</span><span class="sxs-lookup"><span data-stu-id="c4f1d-146">FactSet</span></span>

- <span data-ttu-id="c4f1d-147">HipChat</span><span class="sxs-lookup"><span data-stu-id="c4f1d-147">HipChat</span></span>

- <span data-ttu-id="c4f1d-148">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="c4f1d-148">InvestEdge</span></span>

- <span data-ttu-id="c4f1d-149">LivePerson</span><span class="sxs-lookup"><span data-stu-id="c4f1d-149">LivePerson</span></span>

- <span data-ttu-id="c4f1d-150">MessageLabs Data Streams</span><span class="sxs-lookup"><span data-stu-id="c4f1d-150">MessageLabs Data Streams</span></span>

- <span data-ttu-id="c4f1d-151">OpenText</span><span class="sxs-lookup"><span data-stu-id="c4f1d-151">OpenText</span></span>

- <span data-ttu-id="c4f1d-152">Oracle/ATG 'click-to-call' Live Help</span><span class="sxs-lookup"><span data-stu-id="c4f1d-152">Oracle/ATG 'click-to-call' Live Help</span></span>

- <span data-ttu-id="c4f1d-153">Pivot IMTRADER</span><span class="sxs-lookup"><span data-stu-id="c4f1d-153">Pivot IMTRADER</span></span>

- <span data-ttu-id="c4f1d-154">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="c4f1d-154">Microsoft SharePoint</span></span>

- <span data-ttu-id="c4f1d-155">MindAlign</span><span class="sxs-lookup"><span data-stu-id="c4f1d-155">MindAlign</span></span>

- <span data-ttu-id="c4f1d-156">Sitrion One (Newsgator)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-156">Sitrion One (Newsgator)</span></span>

- <span data-ttu-id="c4f1d-157">Skype voor Bedrijven (Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-157">Skype for Business (Lync/OCS)</span></span>

- <span data-ttu-id="c4f1d-158">Skype voor Bedrijven Online (Lync Online)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-158">Skype for Business Online (Lync Online)</span></span>

- <span data-ttu-id="c4f1d-159">SQL Databases</span><span class="sxs-lookup"><span data-stu-id="c4f1d-159">SQL Databases</span></span>

- <span data-ttu-id="c4f1d-160">Squawker</span><span class="sxs-lookup"><span data-stu-id="c4f1d-160">Squawker</span></span>

- <span data-ttu-id="c4f1d-161">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="c4f1d-161">Thomson Reuters Eikon Messenger</span></span>

### <a name="archivesocial"></a><span data-ttu-id="c4f1d-162">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="c4f1d-162">ArchiveSocial</span></span>

<span data-ttu-id="c4f1d-163">[ArchiveSocial](https://www.archivesocial.com) ondersteunt de volgende gegevensbronnen van derden:</span><span class="sxs-lookup"><span data-stu-id="c4f1d-163">[ArchiveSocial](https://www.archivesocial.com) supports the following third-party data sources:</span></span>

- <span data-ttu-id="c4f1d-164">Facebook</span><span class="sxs-lookup"><span data-stu-id="c4f1d-164">Facebook</span></span>

- <span data-ttu-id="c4f1d-165">Flickr</span><span class="sxs-lookup"><span data-stu-id="c4f1d-165">Flickr</span></span>

- <span data-ttu-id="c4f1d-166">Instagram</span><span class="sxs-lookup"><span data-stu-id="c4f1d-166">Instagram</span></span>

- <span data-ttu-id="c4f1d-167">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="c4f1d-167">LinkedIn</span></span>

- <span data-ttu-id="c4f1d-168">Pinterest</span><span class="sxs-lookup"><span data-stu-id="c4f1d-168">Pinterest</span></span>

- <span data-ttu-id="c4f1d-169">Twitter</span><span class="sxs-lookup"><span data-stu-id="c4f1d-169">Twitter</span></span>

- <span data-ttu-id="c4f1d-170">YouTube</span><span class="sxs-lookup"><span data-stu-id="c4f1d-170">YouTube</span></span>

- <span data-ttu-id="c4f1d-171">Vimeo</span><span class="sxs-lookup"><span data-stu-id="c4f1d-171">Vimeo</span></span>

### <a name="veritas"></a><span data-ttu-id="c4f1d-172">Veritas</span><span class="sxs-lookup"><span data-stu-id="c4f1d-172">Veritas</span></span>

<span data-ttu-id="c4f1d-173">[Veritas](https://www.globanet.com) ondersteunt de volgende gegevensbronnen van derden:</span><span class="sxs-lookup"><span data-stu-id="c4f1d-173">[Veritas](https://www.globanet.com) supports the following third-party data sources:</span></span>

- <span data-ttu-id="c4f1d-174">AOL met draaitabelclient</span><span class="sxs-lookup"><span data-stu-id="c4f1d-174">AOL with Pivot Client</span></span>

- <span data-ttu-id="c4f1d-175">BlackBerry-oproeplogboeken (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-175">BlackBerry Call Logs (v5, v10, v12)</span></span>

- <span data-ttu-id="c4f1d-176">BlackBerry Messenger (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-176">BlackBerry Messenger (v5, v10, v12)</span></span>

- <span data-ttu-id="c4f1d-177">BlackBerry-pincode (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-177">BlackBerry PIN (v5, v10, v12)</span></span>

- <span data-ttu-id="c4f1d-178">BlackBerry SMS (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-178">BlackBerry SMS (v5, v10, v12)</span></span>

- <span data-ttu-id="c4f1d-179">Bloomberg Chat</span><span class="sxs-lookup"><span data-stu-id="c4f1d-179">Bloomberg Chat</span></span>

- <span data-ttu-id="c4f1d-180">E-mail van Bloomberg</span><span class="sxs-lookup"><span data-stu-id="c4f1d-180">Bloomberg Mail</span></span>

- <span data-ttu-id="c4f1d-181">Vak</span><span class="sxs-lookup"><span data-stu-id="c4f1d-181">Box</span></span>

- <span data-ttu-id="c4f1d-182">CipherCloud voor Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="c4f1d-182">CipherCloud for Salesforce Chatter</span></span>

- <span data-ttu-id="c4f1d-183">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-183">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="c4f1d-184">Cisco Webex Teams</span><span class="sxs-lookup"><span data-stu-id="c4f1d-184">Cisco Webex Teams</span></span>

- <span data-ttu-id="c4f1d-185">Citrix Workspace &amp; ShareFile</span><span class="sxs-lookup"><span data-stu-id="c4f1d-185">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="c4f1d-186">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="c4f1d-186">CrowdCompass</span></span>

- <span data-ttu-id="c4f1d-187">Aangepaste tekstbestanden met scheidingstekens</span><span class="sxs-lookup"><span data-stu-id="c4f1d-187">Custom-delimited text files</span></span>

- <span data-ttu-id="c4f1d-188">Aangepaste XML-bestanden</span><span class="sxs-lookup"><span data-stu-id="c4f1d-188">Custom XML files</span></span>

- <span data-ttu-id="c4f1d-189">Facebook (pagina's)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-189">Facebook (Pages)</span></span>

- <span data-ttu-id="c4f1d-190">Factset</span><span class="sxs-lookup"><span data-stu-id="c4f1d-190">Factset</span></span>

- <span data-ttu-id="c4f1d-191">FXConnect</span><span class="sxs-lookup"><span data-stu-id="c4f1d-191">FXConnect</span></span>

- <span data-ttu-id="c4f1d-192">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="c4f1d-192">ICE Chat/YellowJacket</span></span>

- <span data-ttu-id="c4f1d-193">Jive</span><span class="sxs-lookup"><span data-stu-id="c4f1d-193">Jive</span></span>

- <span data-ttu-id="c4f1d-194">Macgregor XIP</span><span class="sxs-lookup"><span data-stu-id="c4f1d-194">Macgregor XIP</span></span>

- <span data-ttu-id="c4f1d-195">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="c4f1d-195">Microsoft Exchange Server</span></span>

- <span data-ttu-id="c4f1d-196">Microsoft OneDrive voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="c4f1d-196">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="c4f1d-197">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c4f1d-197">Microsoft Teams</span></span>

- <span data-ttu-id="c4f1d-198">Microsoft Yammer</span><span class="sxs-lookup"><span data-stu-id="c4f1d-198">Microsoft Yammer</span></span>

- <span data-ttu-id="c4f1d-199">Mobiele beveiliging</span><span class="sxs-lookup"><span data-stu-id="c4f1d-199">Mobile Guard</span></span>

- <span data-ttu-id="c4f1d-200">Pivot</span><span class="sxs-lookup"><span data-stu-id="c4f1d-200">Pivot</span></span>

- <span data-ttu-id="c4f1d-201">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="c4f1d-201">Salesforce Chatter</span></span>

- <span data-ttu-id="c4f1d-202">Skype voor Bedrijven Online</span><span class="sxs-lookup"><span data-stu-id="c4f1d-202">Skype for Business Online</span></span>

- <span data-ttu-id="c4f1d-203">Skype voor Bedrijven versie 2007 R2 - 2016 (on-premises)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-203">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>

- <span data-ttu-id="c4f1d-204">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="c4f1d-204">Slack Enterprise Grid</span></span>

- <span data-ttu-id="c4f1d-205">Symphony</span><span class="sxs-lookup"><span data-stu-id="c4f1d-205">Symphony</span></span>

- <span data-ttu-id="c4f1d-206">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="c4f1d-206">Thomson Reuters Eikon</span></span>

- <span data-ttu-id="c4f1d-207">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="c4f1d-207">Thomson Reuters Messenger</span></span>

- <span data-ttu-id="c4f1d-208">Thomson Reuters Dealings 3000 / FX Trading</span><span class="sxs-lookup"><span data-stu-id="c4f1d-208">Thomson Reuters Dealings 3000 / FX Trading</span></span>

- <span data-ttu-id="c4f1d-209">Twitter</span><span class="sxs-lookup"><span data-stu-id="c4f1d-209">Twitter</span></span>

- <span data-ttu-id="c4f1d-210">UBS-chat</span><span class="sxs-lookup"><span data-stu-id="c4f1d-210">UBS Chat</span></span>

- <span data-ttu-id="c4f1d-211">YouTube</span><span class="sxs-lookup"><span data-stu-id="c4f1d-211">YouTube</span></span>

### <a name="opentext"></a><span data-ttu-id="c4f1d-212">OpenText</span><span class="sxs-lookup"><span data-stu-id="c4f1d-212">OpenText</span></span>

<span data-ttu-id="c4f1d-213">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) ondersteunt de volgende gegevensbronnen van derden:</span><span class="sxs-lookup"><span data-stu-id="c4f1d-213">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span>

- <span data-ttu-id="c4f1d-214">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="c4f1d-214">Axs Encrypted</span></span>

- <span data-ttu-id="c4f1d-215">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="c4f1d-215">Axs Exchange</span></span>

- <span data-ttu-id="c4f1d-216">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="c4f1d-216">Axs Local Archive</span></span>

- <span data-ttu-id="c4f1d-217">Tijdelijke aanduiding Axs</span><span class="sxs-lookup"><span data-stu-id="c4f1d-217">Axs PlaceHolder</span></span>

- <span data-ttu-id="c4f1d-218">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="c4f1d-218">Axs Signed</span></span>

- <span data-ttu-id="c4f1d-219">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="c4f1d-219">Bloomberg</span></span>

- <span data-ttu-id="c4f1d-220">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="c4f1d-220">Thomson Reuters</span></span>

### <a name="smarsh"></a><span data-ttu-id="c4f1d-221">Smarsh</span><span class="sxs-lookup"><span data-stu-id="c4f1d-221">Smarsh</span></span>

<span data-ttu-id="c4f1d-222">[Smarsh ondersteunt](https://www.smarsh.com) de volgende gegevensbronnen van derden:</span><span class="sxs-lookup"><span data-stu-id="c4f1d-222">[Smarsh](https://www.smarsh.com) supports the following third-party data sources:</span></span>

- <span data-ttu-id="c4f1d-223">AIM</span><span class="sxs-lookup"><span data-stu-id="c4f1d-223">AIM</span></span>

- <span data-ttu-id="c4f1d-224">American Idool</span><span class="sxs-lookup"><span data-stu-id="c4f1d-224">American Idol</span></span>

- <span data-ttu-id="c4f1d-225">Appelsap</span><span class="sxs-lookup"><span data-stu-id="c4f1d-225">Apple Juice</span></span>

- <span data-ttu-id="c4f1d-226">AOL met draaitabelclient</span><span class="sxs-lookup"><span data-stu-id="c4f1d-226">AOL with Pivot client</span></span>

- <span data-ttu-id="c4f1d-227">Ares</span><span class="sxs-lookup"><span data-stu-id="c4f1d-227">Ares</span></span>

- <span data-ttu-id="c4f1d-228">De stem van Dezaar</span><span class="sxs-lookup"><span data-stu-id="c4f1d-228">Bazaar Voice</span></span>

- <span data-ttu-id="c4f1d-229">Bear Share</span><span class="sxs-lookup"><span data-stu-id="c4f1d-229">Bear Share</span></span>

- <span data-ttu-id="c4f1d-230">Bit-torrent</span><span class="sxs-lookup"><span data-stu-id="c4f1d-230">Bit Torrent</span></span>

- <span data-ttu-id="c4f1d-231">BlackBerry-oproeplogboeken (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-231">BlackBerry Call Logs (v5, v10, v12)</span></span>

- <span data-ttu-id="c4f1d-232">BlackBerry Messenger (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-232">BlackBerry Messenger (v5, v10, v12)</span></span>

- <span data-ttu-id="c4f1d-233">BlackBerry-pincode (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-233">BlackBerry PIN (v5, v10, v12)</span></span>

- <span data-ttu-id="c4f1d-234">BlackBerry SMS (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-234">BlackBerry SMS (v5, v10, v12)</span></span>

- <span data-ttu-id="c4f1d-235">E-mail van Bloomberg</span><span class="sxs-lookup"><span data-stu-id="c4f1d-235">Bloomberg Mail</span></span>

- <span data-ttu-id="c4f1d-236">CellTrust</span><span class="sxs-lookup"><span data-stu-id="c4f1d-236">CellTrust</span></span>

- <span data-ttu-id="c4f1d-237">Chat importeren</span><span class="sxs-lookup"><span data-stu-id="c4f1d-237">Chat Import</span></span>

- <span data-ttu-id="c4f1d-238">Realtime logboekregistratie en beleid chatten</span><span class="sxs-lookup"><span data-stu-id="c4f1d-238">Chat Real Time Logging and Policy</span></span>

- <span data-ttu-id="c4f1d-239">Chatter</span><span class="sxs-lookup"><span data-stu-id="c4f1d-239">Chatter</span></span>

- <span data-ttu-id="c4f1d-240">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-240">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>

- <span data-ttu-id="c4f1d-241">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-241">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>

- <span data-ttu-id="c4f1d-242">Samenwerking importeren</span><span class="sxs-lookup"><span data-stu-id="c4f1d-242">Collaboration Import</span></span>

- <span data-ttu-id="c4f1d-243">Realtime logboekregistratie voor samenwerking</span><span class="sxs-lookup"><span data-stu-id="c4f1d-243">Collaboration Real Time Logging</span></span>

- <span data-ttu-id="c4f1d-244">Directe Verbinding maken</span><span class="sxs-lookup"><span data-stu-id="c4f1d-244">Direct Connect</span></span>

- <span data-ttu-id="c4f1d-245">Facebook</span><span class="sxs-lookup"><span data-stu-id="c4f1d-245">Facebook</span></span>

- <span data-ttu-id="c4f1d-246">FactSet</span><span class="sxs-lookup"><span data-stu-id="c4f1d-246">FactSet</span></span>

- <span data-ttu-id="c4f1d-247">FastTrack</span><span class="sxs-lookup"><span data-stu-id="c4f1d-247">FastTrack</span></span>

- <span data-ttu-id="c4f1d-248">Gnutella</span><span class="sxs-lookup"><span data-stu-id="c4f1d-248">Gnutella</span></span>

- <span data-ttu-id="c4f1d-249">Google+</span><span class="sxs-lookup"><span data-stu-id="c4f1d-249">Google+</span></span>

- <span data-ttu-id="c4f1d-250">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="c4f1d-250">GoToMyPC</span></span>

- <span data-ttu-id="c4f1d-251">Hopster</span><span class="sxs-lookup"><span data-stu-id="c4f1d-251">Hopster</span></span>

- <span data-ttu-id="c4f1d-252">HubConnex</span><span class="sxs-lookup"><span data-stu-id="c4f1d-252">HubConnex</span></span>

- <span data-ttu-id="c4f1d-253">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-253">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>

- <span data-ttu-id="c4f1d-254">IBM Connections Chat Cloud</span><span class="sxs-lookup"><span data-stu-id="c4f1d-254">IBM Connections Chat Cloud</span></span>

- <span data-ttu-id="c4f1d-255">IBM Connections Social Cloud</span><span class="sxs-lookup"><span data-stu-id="c4f1d-255">IBM Connections Social Cloud</span></span>

- <span data-ttu-id="c4f1d-256">IBM SameTime Advanced 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="c4f1d-256">IBM SameTime Advanced 8.5.2 IFR1</span></span>

- <span data-ttu-id="c4f1d-257">IBM SameTime Communicate 9.0</span><span class="sxs-lookup"><span data-stu-id="c4f1d-257">IBM SameTime Communicate 9.0</span></span>

- <span data-ttu-id="c4f1d-258">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-258">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>

- <span data-ttu-id="c4f1d-259">IBM SameTime Complete 9.0</span><span class="sxs-lookup"><span data-stu-id="c4f1d-259">IBM SameTime Complete 9.0</span></span>

- <span data-ttu-id="c4f1d-260">IBM SameTime Conference 9.0</span><span class="sxs-lookup"><span data-stu-id="c4f1d-260">IBM SameTime Conference 9.0</span></span>

- <span data-ttu-id="c4f1d-261">IBM SameTime Meeting 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="c4f1d-261">IBM SameTime Meeting 8.5.2 IFR1</span></span>

- <span data-ttu-id="c4f1d-262">ICE/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="c4f1d-262">ICE/YellowJacket</span></span>

- <span data-ttu-id="c4f1d-263">Chat importeren</span><span class="sxs-lookup"><span data-stu-id="c4f1d-263">IM Import</span></span>

- <span data-ttu-id="c4f1d-264">Realtime logboekregistratie en beleid chatberichten</span><span class="sxs-lookup"><span data-stu-id="c4f1d-264">IM Real Time Logging and Policy</span></span>

- <span data-ttu-id="c4f1d-265">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="c4f1d-265">Indii Messenger</span></span>

- <span data-ttu-id="c4f1d-266">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="c4f1d-266">Instant Bloomberg</span></span>

- <span data-ttu-id="c4f1d-267">IRC</span><span class="sxs-lookup"><span data-stu-id="c4f1d-267">IRC</span></span>

- <span data-ttu-id="c4f1d-268">Jive</span><span class="sxs-lookup"><span data-stu-id="c4f1d-268">Jive</span></span>

- <span data-ttu-id="c4f1d-269">Jive 6 Realtime logboekregistratie (v6, v7)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-269">Jive 6 Real Time Logging (v6, v7)</span></span>

- <span data-ttu-id="c4f1d-270">Jive-import</span><span class="sxs-lookup"><span data-stu-id="c4f1d-270">Jive Import</span></span>

- <span data-ttu-id="c4f1d-271">JXTA</span><span class="sxs-lookup"><span data-stu-id="c4f1d-271">JXTA</span></span>

- <span data-ttu-id="c4f1d-272">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="c4f1d-272">LinkedIn</span></span>

- <span data-ttu-id="c4f1d-273">Microsoft Lync (2010, 2013)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-273">Microsoft Lync (2010, 2013)</span></span>

- <span data-ttu-id="c4f1d-274">MFTP</span><span class="sxs-lookup"><span data-stu-id="c4f1d-274">MFTP</span></span>

- <span data-ttu-id="c4f1d-275">Microsoft Lync 2013 Voice</span><span class="sxs-lookup"><span data-stu-id="c4f1d-275">Microsoft Lync 2013 Voice</span></span>

- <span data-ttu-id="c4f1d-276">Microsoft SharePoint (2010, 2013)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-276">Microsoft SharePoint (2010, 2013)</span></span>

- <span data-ttu-id="c4f1d-277">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="c4f1d-277">Microsoft SharePoint Online</span></span>

- <span data-ttu-id="c4f1d-278">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-278">Microsoft UC (Unified Communications)</span></span>

- <span data-ttu-id="c4f1d-279">MindAlign</span><span class="sxs-lookup"><span data-stu-id="c4f1d-279">MindAlign</span></span>

- <span data-ttu-id="c4f1d-280">Mobiele beveiliging</span><span class="sxs-lookup"><span data-stu-id="c4f1d-280">Mobile Guard</span></span>

- <span data-ttu-id="c4f1d-281">MSN</span><span class="sxs-lookup"><span data-stu-id="c4f1d-281">MSN</span></span>

- <span data-ttu-id="c4f1d-282">Mijn ruimte</span><span class="sxs-lookup"><span data-stu-id="c4f1d-282">My Space</span></span>

- <span data-ttu-id="c4f1d-283">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="c4f1d-283">NEONetwork</span></span>

- <span data-ttu-id="c4f1d-284">Microsoft 365 Lync Dedicated</span><span class="sxs-lookup"><span data-stu-id="c4f1d-284">Microsoft 365 Lync Dedicated</span></span>

- <span data-ttu-id="c4f1d-285">Microsoft 365 Gedeeld chatbericht</span><span class="sxs-lookup"><span data-stu-id="c4f1d-285">Microsoft 365 Shared IM</span></span>

- <span data-ttu-id="c4f1d-286">Pinterest</span><span class="sxs-lookup"><span data-stu-id="c4f1d-286">Pinterest</span></span>

- <span data-ttu-id="c4f1d-287">Pivot</span><span class="sxs-lookup"><span data-stu-id="c4f1d-287">Pivot</span></span>

- <span data-ttu-id="c4f1d-288">QQ</span><span class="sxs-lookup"><span data-stu-id="c4f1d-288">QQ</span></span>

- <span data-ttu-id="c4f1d-289">Skype voor Bedrijven 2015</span><span class="sxs-lookup"><span data-stu-id="c4f1d-289">Skype for Business 2015</span></span>

- <span data-ttu-id="c4f1d-290">SoftEther</span><span class="sxs-lookup"><span data-stu-id="c4f1d-290">SoftEther</span></span>

- <span data-ttu-id="c4f1d-291">Symphony</span><span class="sxs-lookup"><span data-stu-id="c4f1d-291">Symphony</span></span>

- <span data-ttu-id="c4f1d-292">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="c4f1d-292">Thomson Reuters Eikon</span></span>

- <span data-ttu-id="c4f1d-293">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="c4f1d-293">Thomson Reuters Messenger</span></span>

- <span data-ttu-id="c4f1d-294">Tor</span><span class="sxs-lookup"><span data-stu-id="c4f1d-294">Tor</span></span>

- <span data-ttu-id="c4f1d-295">TTT</span><span class="sxs-lookup"><span data-stu-id="c4f1d-295">TTT</span></span>

- <span data-ttu-id="c4f1d-296">Twitter</span><span class="sxs-lookup"><span data-stu-id="c4f1d-296">Twitter</span></span>

- <span data-ttu-id="c4f1d-297">WinMX</span><span class="sxs-lookup"><span data-stu-id="c4f1d-297">WinMX</span></span>

- <span data-ttu-id="c4f1d-298">Winny</span><span class="sxs-lookup"><span data-stu-id="c4f1d-298">Winny</span></span>

- <span data-ttu-id="c4f1d-299">Yahoo</span><span class="sxs-lookup"><span data-stu-id="c4f1d-299">Yahoo</span></span>

- <span data-ttu-id="c4f1d-300">Yammer</span><span class="sxs-lookup"><span data-stu-id="c4f1d-300">Yammer</span></span>

- <span data-ttu-id="c4f1d-301">YouTube</span><span class="sxs-lookup"><span data-stu-id="c4f1d-301">YouTube</span></span>


### <a name="verba"></a><span data-ttu-id="c4f1d-302">Verba</span><span class="sxs-lookup"><span data-stu-id="c4f1d-302">Verba</span></span>

<span data-ttu-id="c4f1d-303">[Verba ondersteunt](https://www.verba.com) de volgende gegevensbronnen van derden:</span><span class="sxs-lookup"><span data-stu-id="c4f1d-303">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span>

- <span data-ttu-id="c4f1d-304">Avaya Aura Video</span><span class="sxs-lookup"><span data-stu-id="c4f1d-304">Avaya Aura Video</span></span>

- <span data-ttu-id="c4f1d-305">Avaya Aura Voice</span><span class="sxs-lookup"><span data-stu-id="c4f1d-305">Avaya Aura Voice</span></span>

- <span data-ttu-id="c4f1d-306">Avtec Radio</span><span class="sxs-lookup"><span data-stu-id="c4f1d-306">Avtec Radio</span></span>

- <span data-ttu-id="c4f1d-307">Bosch/Telex Radio</span><span class="sxs-lookup"><span data-stu-id="c4f1d-307">Bosch/Telex Radio</span></span>

- <span data-ttu-id="c4f1d-308">BroadSoft Video</span><span class="sxs-lookup"><span data-stu-id="c4f1d-308">BroadSoft Video</span></span>

- <span data-ttu-id="c4f1d-309">BroadSoft Voice</span><span class="sxs-lookup"><span data-stu-id="c4f1d-309">BroadSoft Voice</span></span>

- <span data-ttu-id="c4f1d-310">Centile Voice</span><span class="sxs-lookup"><span data-stu-id="c4f1d-310">Centile Voice</span></span>

- <span data-ttu-id="c4f1d-311">Cisco Jabber-chatbericht</span><span class="sxs-lookup"><span data-stu-id="c4f1d-311">Cisco Jabber IM</span></span>

- <span data-ttu-id="c4f1d-312">Cisco UC Video</span><span class="sxs-lookup"><span data-stu-id="c4f1d-312">Cisco UC Video</span></span>

- <span data-ttu-id="c4f1d-313">Cisco UC Voice</span><span class="sxs-lookup"><span data-stu-id="c4f1d-313">Cisco UC Voice</span></span>

- <span data-ttu-id="c4f1d-314">Cisco UCCX/UCCE Video</span><span class="sxs-lookup"><span data-stu-id="c4f1d-314">Cisco UCCX/UCCE Video</span></span>

- <span data-ttu-id="c4f1d-315">Cisco UCCX/UCCE Voice</span><span class="sxs-lookup"><span data-stu-id="c4f1d-315">Cisco UCCX/UCCE Voice</span></span>

- <span data-ttu-id="c4f1d-316">ESChat Radio</span><span class="sxs-lookup"><span data-stu-id="c4f1d-316">ESChat Radio</span></span>

- <span data-ttu-id="c4f1d-317">Geoman Contact Expert</span><span class="sxs-lookup"><span data-stu-id="c4f1d-317">Geoman Contact Expert</span></span>

- <span data-ttu-id="c4f1d-318">IP Trade Voice</span><span class="sxs-lookup"><span data-stu-id="c4f1d-318">IP Trade Voice</span></span>

- <span data-ttu-id="c4f1d-319">Luware LUCS Contact Center</span><span class="sxs-lookup"><span data-stu-id="c4f1d-319">Luware LUCS Contact Center</span></span>

- <span data-ttu-id="c4f1d-320">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-320">Microsoft UC (Unified Communications)</span></span>

- <span data-ttu-id="c4f1d-321">Mitel MiContact Center voor Lync (prairieFyre)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-321">Mitel MiContact Center for Lync (prairieFyre)</span></span>

- <span data-ttu-id="c4f1d-322">Oracle / Acme Packet Session Border Controller Video</span><span class="sxs-lookup"><span data-stu-id="c4f1d-322">Oracle / Acme Packet Session Border Controller Video</span></span>

- <span data-ttu-id="c4f1d-323">Oracle / Acme Packet Session Border Controller Voice</span><span class="sxs-lookup"><span data-stu-id="c4f1d-323">Oracle / Acme Packet Session Border Controller Voice</span></span>

- <span data-ttu-id="c4f1d-324">Singtel Mobile Voice</span><span class="sxs-lookup"><span data-stu-id="c4f1d-324">Singtel Mobile Voice</span></span>

- <span data-ttu-id="c4f1d-325">SIPREC Video</span><span class="sxs-lookup"><span data-stu-id="c4f1d-325">SIPREC Video</span></span>

-  <span data-ttu-id="c4f1d-326">SIPREC Voice</span><span class="sxs-lookup"><span data-stu-id="c4f1d-326">SIPREC Voice</span></span>

- <span data-ttu-id="c4f1d-327">Skype voor Bedrijven / Lync-chatbericht</span><span class="sxs-lookup"><span data-stu-id="c4f1d-327">Skype for Business / Lync IM</span></span>

- <span data-ttu-id="c4f1d-328">Skype voor Bedrijven / Lync Video</span><span class="sxs-lookup"><span data-stu-id="c4f1d-328">Skype for Business / Lync Video</span></span>

- <span data-ttu-id="c4f1d-329">Skype voor Bedrijven / Lync Voice</span><span class="sxs-lookup"><span data-stu-id="c4f1d-329">Skype for Business / Lync Voice</span></span>

- <span data-ttu-id="c4f1d-330">Luidsprekerbus-stem</span><span class="sxs-lookup"><span data-stu-id="c4f1d-330">Speakerbus Voice</span></span>

- <span data-ttu-id="c4f1d-331">Standaard SIP/H.323 Video</span><span class="sxs-lookup"><span data-stu-id="c4f1d-331">Standard SIP/H.323 Video</span></span>

- <span data-ttu-id="c4f1d-332">Standaard SIP/H.323 Voice</span><span class="sxs-lookup"><span data-stu-id="c4f1d-332">Standard SIP/H.323 Voice</span></span>

- <span data-ttu-id="c4f1d-333">Truphone-stem</span><span class="sxs-lookup"><span data-stu-id="c4f1d-333">Truphone Voice</span></span>

- <span data-ttu-id="c4f1d-334">TwistedPair Radio</span><span class="sxs-lookup"><span data-stu-id="c4f1d-334">TwistedPair Radio</span></span>

- <span data-ttu-id="c4f1d-335">Windows Bureaubladcomputerscherm</span><span class="sxs-lookup"><span data-stu-id="c4f1d-335">Windows Desktop Computer Screen</span></span>

## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365"></a><span data-ttu-id="c4f1d-336">Stap 2: Een gegevenspostvak van derden maken en configureren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c4f1d-336">Step 2: Create and configure a third-party data mailbox in Microsoft 365</span></span>

<span data-ttu-id="c4f1d-337">Hier volgen de stappen voor het maken en configureren van een gegevenspostvak van derden voor het importeren van gegevens in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-337">Here are the steps for creating and configuring a third-party data mailbox for importing data to Microsoft 365.</span></span> <span data-ttu-id="c4f1d-338">Zoals eerder is uitgelegd, worden items geïmporteerd in dit postvak als de partnerconnector de gebruikers-id van het item niet aan een gebruikersaccount kan toevoegen.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-338">As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to a user account.</span></span>

 <span data-ttu-id="c4f1d-339">**Voltooi deze taken in de Microsoft 365-beheercentrum**</span><span class="sxs-lookup"><span data-stu-id="c4f1d-339">**Complete these tasks in the Microsoft 365 admin center**</span></span>

1. <span data-ttu-id="c4f1d-340">Maak een gebruikersaccount en wijs het een licentie Exchange Online abonnement 2 toe. zie [Gebruikers toevoegen aan Microsoft 365.](../admin/add-users/add-users.md)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-340">Create a user account and assign it an Exchange Online Plan 2 license; see [Add users to Microsoft 365](../admin/add-users/add-users.md).</span></span> <span data-ttu-id="c4f1d-341">Een abonnement 2-licentie is vereist om het postvak in de bewaring voor rechtszaken te plaatsen of om een archiefpostvak met een onbeperkt opslagquotum in te stellen.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-341">A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>

2. <span data-ttu-id="c4f1d-342">Voeg het gebruikersaccount voor het gegevenspostvak van derden toe aan **Exchange beheerdersrol** in Microsoft 365; zie [Beheerdersrollen toewijzen in Microsoft 365.](../admin/add-users/assign-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-342">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Microsoft 365; see [Assign admin roles in Microsoft 365](../admin/add-users/assign-admin-roles.md).</span></span>

    > [!TIP]
    > <span data-ttu-id="c4f1d-343">Noteert u de referenties voor dit gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-343">Write down the credentials for this user account.</span></span> <span data-ttu-id="c4f1d-344">U moet deze aan uw partner verstrekken, zoals beschreven in stap 4.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-344">You need to provide them to your partner, as described in Step 4.</span></span>

 <span data-ttu-id="c4f1d-345">**Deze taken uitvoeren in het Exchange beheercentrum**</span><span class="sxs-lookup"><span data-stu-id="c4f1d-345">**Complete these tasks in the Exchange admin center**</span></span>

1. <span data-ttu-id="c4f1d-346">Het gegevenspostvak van derden verbergen in het adresboek en andere adreslijsten in uw organisatie; zie [Gebruikerspostvakken beheren.](/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-346">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes).</span></span> <span data-ttu-id="c4f1d-347">U kunt ook de volgende PowerShell-opdracht uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="c4f1d-347">Alternatively, you can run the following PowerShell command:</span></span>

    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="c4f1d-348">Wijs **de machtiging FullAccess** toe aan het gegevenspostvak van derden, zodat beheerders of compliancemedewerkers het gegevenspostvak van derden kunnen openen in de Outlook desktopclient; zie [Machtigingen voor geadresseerden beheren.](https://go.microsoft.com/fwlink/p/?LinkId=692104)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-348">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>

3. <span data-ttu-id="c4f1d-349">Schakel de volgende compliance-gerelateerde functies in voor het gegevenspostvak van derden:</span><span class="sxs-lookup"><span data-stu-id="c4f1d-349">Enable the following compliance-related features for the third-party data mailbox:</span></span>

    - <span data-ttu-id="c4f1d-350">Het archiefpostvak inschakelen. zie [Archiefpostvakken inschakelen en](enable-archive-mailboxes.md) [Onbeperkt archiveren inschakelen.](enable-unlimited-archiving.md)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-350">Enable the archive mailbox; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span> <span data-ttu-id="c4f1d-351">Hiermee kunt u opslagruimte vrij maken in het primaire postvak door een archiefbeleid in te stellen waarmee gegevensitems van derden naar het archiefpostvak worden verplaatst.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-351">This lets you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox.</span></span> <span data-ttu-id="c4f1d-352">Dit biedt u onbeperkte opslagruimte voor gegevens van derden.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-352">This provides you with unlimited storage for third-party data.</span></span>

    - <span data-ttu-id="c4f1d-353">Plaats het gegevenspostvak van derden in de procedure voor het in de wacht houden van rechtszaken.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-353">Place the third-party data mailbox on Litigation Hold.</span></span> <span data-ttu-id="c4f1d-354">U kunt ook een bewaarbeleid Microsoft 365 in het beveiligings- en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-354">You can also apply a Microsoft 365 retention policy in the security and compliance center.</span></span> <span data-ttu-id="c4f1d-355">Als u dit postvak in de wacht zet, blijven gegevensitems van derden (voor onbepaalde tijd of voor een bepaalde duur) behouden en worden ze niet uit het postvak verwijderd.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-355">Placing this mailbox on hold retains third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox.</span></span> <span data-ttu-id="c4f1d-356">Zie een van de volgende onderwerpen:</span><span class="sxs-lookup"><span data-stu-id="c4f1d-356">See one of the following topics:</span></span>

      - [<span data-ttu-id="c4f1d-357">Een postvak in de wacht houden voor rechtszaken plaatsen</span><span class="sxs-lookup"><span data-stu-id="c4f1d-357">Place a mailbox on Litigation Hold</span></span>](./create-a-litigation-hold.md)

      - [<span data-ttu-id="c4f1d-358">Meer informatie over bewaarbeleid en retentielabels</span><span class="sxs-lookup"><span data-stu-id="c4f1d-358">Learn about retention policies and retention labels</span></span>](retention.md)

    - <span data-ttu-id="c4f1d-359">Logboekregistratie voor postvakcontrole inschakelen voor toegang van eigenaar, gedelegeerde en beheerder tot het gegevenspostvak van derden; zie [Postvakcontrole inschakelen.](enable-mailbox-auditing.md)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-359">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing](enable-mailbox-auditing.md).</span></span> <span data-ttu-id="c4f1d-360">Hiermee kunt u alle activiteiten controleren die worden uitgevoerd door elke gebruiker die toegang heeft tot het gegevenspostvak van derden.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-360">This allows you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="c4f1d-361">Stap 3: Gebruikerspostvakken configureren voor gegevens van derden</span><span class="sxs-lookup"><span data-stu-id="c4f1d-361">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="c4f1d-362">De volgende stap is het configureren van postvakken van gebruikers om gegevens van derden te ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-362">The next step is to configure user mailboxes to support third-party data.</span></span> <span data-ttu-id="c4f1d-363">Voltooi deze taken met behulp van het Exchange beheercentrum of met de bijbehorende Windows PowerShell cmdlets.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-363">Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>

1. <span data-ttu-id="c4f1d-364">Schakel het archiefpostvak voor elke gebruiker in; zie [Archiefpostvakken inschakelen en](enable-archive-mailboxes.md) [Onbeperkt archiveren inschakelen.](enable-unlimited-archiving.md)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-364">Enable the archive mailbox for each user; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>

2. <span data-ttu-id="c4f1d-365">Gebruikerspostvakken in bewaring plaatsen of een bewaarbeleid Microsoft 365 toepassen; zie een van de volgende onderwerpen:</span><span class="sxs-lookup"><span data-stu-id="c4f1d-365">Place user mailboxes on Litigation Hold or apply a Microsoft 365 retention policy; see one of the following topics:</span></span>

    - [<span data-ttu-id="c4f1d-366">Een postvak in de wacht houden voor rechtszaken plaatsen</span><span class="sxs-lookup"><span data-stu-id="c4f1d-366">Place a mailbox on Litigation Hold</span></span>](./create-a-litigation-hold.md)

    - [<span data-ttu-id="c4f1d-367">Meer informatie over bewaarbeleid en retentielabels</span><span class="sxs-lookup"><span data-stu-id="c4f1d-367">Learn about retention policies and retention labels</span></span>](retention.md)

    <span data-ttu-id="c4f1d-368">Zoals eerder is aangegeven, kunt u, wanneer u postvakken in de wacht houdt, een duur instellen voor de duur van het opslaan van items uit de gegevensbron van derden of u kunt ervoor kiezen items voor onbepaalde tijd vast te houden.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-368">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="c4f1d-369">Stap 4: Geef uw partner informatie</span><span class="sxs-lookup"><span data-stu-id="c4f1d-369">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="c4f1d-370">De laatste stap is om uw partner de volgende informatie te verstrekken, zodat deze de verbindingslijn kan configureren om verbinding te maken met uw organisatie om gegevens te importeren in gebruikerspostvakken en in het gegevenspostvak van derden.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-370">The final step is to provide your partner with the following information so they can configure the connector to connect to your organization to import data to user mailboxes and to the third-party data mailbox.</span></span>

- <span data-ttu-id="c4f1d-371">Het eindpunt dat wordt gebruikt om verbinding te maken met de Azure-service in Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="c4f1d-371">The endpoint used to connect to the Azure service in Microsoft 365:</span></span>

    ```http
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="c4f1d-372">De aanmeldingsreferenties (Microsoft 365 gebruikers-id en wachtwoord) van het gegevenspostvak van derden dat u hebt gemaakt in stap 2.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-372">The sign-in credentials (Microsoft 365 user ID and password) of the third-party data mailbox that you created in Step 2.</span></span> <span data-ttu-id="c4f1d-373">Deze referenties zijn vereist, zodat de partnerconnector items kan openen en importeren in postvakken van gebruikers en in het gegevenspostvak van derden.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-373">These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>

## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="c4f1d-374">Stap 5: De gegevensconnector van derden registreren in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c4f1d-374">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="c4f1d-375">Vanaf 30 september 2018 wordt met de Azure-service in Microsoft 365 moderne verificatie in Exchange Online gebruikt om gegevensconnectoren van derden te verifiëren die verbinding proberen te maken met uw organisatie om gegevens te importeren.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-375">Starting September 30, 2018, the Azure service in Microsoft 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your organization to import data.</span></span> <span data-ttu-id="c4f1d-376">De reden voor deze wijziging is dat moderne verificatie meer beveiliging biedt dan de huidige methode, die is gebaseerd op een lijst met toegestane connectors van derden die het eerder beschreven eindpunt gebruiken om verbinding te maken met de Azure-service.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-376">The reason for this change is that modern authentication provides more security than the current method, which was based on an allow list for third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="c4f1d-377">Als u een externe gegevensconnector wilt inschakelen om verbinding te maken met Microsoft 365 met de nieuwe moderne verificatiemethode, moet een beheerder in uw organisatie toestemming geven om de verbindingslijn te registreren als een vertrouwde servicetoepassing in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-377">To enable a third-party data connector to connect to Microsoft 365 using the new modern authentication method, an administrator in your organization must consent to register the connector as a trusted service application in Azure Active Directory.</span></span> <span data-ttu-id="c4f1d-378">Dit wordt gedaan door een machtigingsaanvraag te accepteren om de verbindingslijn toegang te geven tot de gegevens van uw organisatie in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-378">This is done by accepting a permission request to allow the connector to access your organization's data in Azure Active Directory.</span></span> <span data-ttu-id="c4f1d-379">Nadat u deze aanvraag hebt geaccepteerd, wordt de gegevensconnector van derden toegevoegd als een ondernemingstoepassing om Azure Active Directory worden weergegeven als serviceprincipaal.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-379">After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal.</span></span> <span data-ttu-id="c4f1d-380">Zie Toestemming van tenantbeheerder voor meer informatie over het [toestemmingsproces.](/skype-sdk/trusted-application-api/docs/tenantadminconsent)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-380">For more information the consent process, see  [Tenant Admin Consent](/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="c4f1d-381">Hier volgen de stappen voor het openen en accepteren van de aanvraag om de verbindingslijn te registreren:</span><span class="sxs-lookup"><span data-stu-id="c4f1d-381">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="c4f1d-382">Ga naar [deze pagina en](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) meld u aan met de referenties van een globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-382">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of a global administrator.</span></span>

   <span data-ttu-id="c4f1d-383">Het volgende dialoogvenster wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-383">The following dialog box is displayed.</span></span> <span data-ttu-id="c4f1d-384">U kunt de carets uitbreiden om de machtigingen te bekijken die aan de verbindingslijn worden toegewezen.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-384">You can expand the carets to review the permissions that will be assigned to the connector.</span></span>

   ![Het dialoogvenster Machtigingenaanvraag wordt weergegeven](../media/O365-ThirdPartyDataConnector-OptIn1.png)

2. <span data-ttu-id="c4f1d-386">Klik **op Accepteren.**</span><span class="sxs-lookup"><span data-stu-id="c4f1d-386">Click **Accept**.</span></span>

<span data-ttu-id="c4f1d-387">Nadat u de aanvraag hebt geaccepteerd, wordt de [Azure-portal](https://portal.azure.com) weergegeven.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-387">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed.</span></span> <span data-ttu-id="c4f1d-388">Als u de lijst met toepassingen voor uw organisatie wilt weergeven, klikt u **Azure Active Directory**  >  **Enterprise-toepassingen.**</span><span class="sxs-lookup"><span data-stu-id="c4f1d-388">To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**.</span></span> <span data-ttu-id="c4f1d-389">De Microsoft 365 gegevensconnector van derden wordt weergegeven op het **enterprise-toepassingenblad.**</span><span class="sxs-lookup"><span data-stu-id="c4f1d-389">The Microsoft 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c4f1d-390">Na 30 september 2018 worden gegevens van derden niet meer geïmporteerd in postvakken in uw organisatie als u geen gegevensconnector van derden registreert in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-390">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory.</span></span> <span data-ttu-id="c4f1d-391">Houd er rekening mee dat bestaande gegevensconnectoren van derden (die zijn gemaakt vóór 30 september 2018) ook moeten worden geregistreerd in Azure Active Directory door de procedure in stap 5 te volgen.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-391">Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="c4f1d-392">Toestemming intrekken voor een gegevensconnector van derden</span><span class="sxs-lookup"><span data-stu-id="c4f1d-392">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="c4f1d-393">Nadat uw organisatie instemt met de machtigingenaanvraag voor het registreren van een gegevensconnector van derden in Azure Active Directory, kan uw organisatie deze toestemming op elk moment intrekken.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-393">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time.</span></span> <span data-ttu-id="c4f1d-394">Het intrekken van de toestemming voor een verbindingslijn betekent echter dat gegevens uit de gegevensbron van derden niet meer worden geïmporteerd in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-394">However, revoking the consent for a connector means that data from the third-party data source will no longer be imported into Microsoft 365.</span></span>

<span data-ttu-id="c4f1d-395">Als u de toestemming voor een gegevensconnector van derden wilt intrekken, kunt u de toepassing  (door de bijbehorende serviceprincipaal te verwijderen) verwijderen uit Azure Active Directory met behulp van het enterprise-toepassingenblad in de Azure-portal of met behulp van [remove-MsolServicePrincipal](/powershell/module/msonline/remove-msolserviceprincipal) in Microsoft 365 PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-395">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](/powershell/module/msonline/remove-msolserviceprincipal) in Microsoft 365 PowerShell.</span></span> <span data-ttu-id="c4f1d-396">U kunt ook de [cmdlet Remove-AzureADServicePrincipal](/powershell/module/azuread/remove-azureadserviceprincipal) gebruiken in Azure Active Directory PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-396">You can also use the [Remove-AzureADServicePrincipal](/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>

## <a name="more-information"></a><span data-ttu-id="c4f1d-397">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="c4f1d-397">More information</span></span>

- <span data-ttu-id="c4f1d-398">Zoals eerder is uitgelegd, worden items uit gegevensbronnen van derden geïmporteerd in Exchange postvakken als e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-398">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages.</span></span> <span data-ttu-id="c4f1d-399">De partnerconnector importeert het item met behulp van een schema dat is vereist door Microsoft 365 API.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-399">The partner connector imports the item using a schema required by the Microsoft 365 API.</span></span> <span data-ttu-id="c4f1d-400">In de volgende tabel worden de berichteigenschappen van een item uit een gegevensbron van derden beschreven nadat het is geïmporteerd in een postvak Exchange een e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-400">The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message.</span></span> <span data-ttu-id="c4f1d-401">In de tabel wordt ook aangegeven of de eigenschap bericht verplicht is.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-401">The table also indicates if the message property is mandatory.</span></span> <span data-ttu-id="c4f1d-402">Verplichte eigenschappen moeten worden ingevuld.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-402">Mandatory properties must be populated.</span></span> <span data-ttu-id="c4f1d-403">Als een item een verplichte eigenschap mist, wordt dit niet geïmporteerd in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-403">If an item is missing a mandatory property, it won't be imported to Microsoft 365.</span></span> <span data-ttu-id="c4f1d-404">Het importproces retourneert een foutbericht waarin wordt uitgelegd waarom een item niet is geïmporteerd en welke eigenschap ontbreekt.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-404">The import process returns an error message explaining why an item wasn't imported and which property is missing.</span></span><br/><br/>

    |<span data-ttu-id="c4f1d-405">**Bericht, eigenschap**</span><span class="sxs-lookup"><span data-stu-id="c4f1d-405">**Message property**</span></span>|<span data-ttu-id="c4f1d-406">**Verplicht?**</span><span class="sxs-lookup"><span data-stu-id="c4f1d-406">**Mandatory?**</span></span>|<span data-ttu-id="c4f1d-407">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="c4f1d-407">**Description**</span></span>|<span data-ttu-id="c4f1d-408">**Voorbeeldwaarde**</span><span class="sxs-lookup"><span data-stu-id="c4f1d-408">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c4f1d-409">**Van**</span><span class="sxs-lookup"><span data-stu-id="c4f1d-409">**FROM**</span></span> <br/> |<span data-ttu-id="c4f1d-410">Ja</span><span class="sxs-lookup"><span data-stu-id="c4f1d-410">Yes</span></span>  <br/> |<span data-ttu-id="c4f1d-411">De gebruiker die het item oorspronkelijk heeft gemaakt of verzonden in de gegevensbron van derden.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-411">The user who originally created or sent the item in the third-party data source.</span></span> <span data-ttu-id="c4f1d-412">De partnerconnector probeert de gebruikers-id van het bronitem (bijvoorbeeld een Twitter-greep) toe te wijden aan een gebruikersaccount voor alle deelnemers (gebruikers in de velden VAN en TO).</span><span class="sxs-lookup"><span data-stu-id="c4f1d-412">The partner connector attempts to map the user ID from the source item (for example a Twitter handle) to a user account for all participants (users in the FROM and TO fields).</span></span> <span data-ttu-id="c4f1d-413">Een kopie van het bericht wordt geïmporteerd in het postvak van elke deelnemer.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-413">A copy of the message will be imported to the mailbox of every participant.</span></span> <span data-ttu-id="c4f1d-414">Als geen van de deelnemers van het item kan worden toegeschreven aan een gebruikersaccount, wordt het item geïmporteerd in het archiefpostvak van derden in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-414">If none of the participants from the item can be mapped to a user account, the item will be imported to the third-party archiving mailbox in Microsoft 365.</span></span>  <br/> <br/> <span data-ttu-id="c4f1d-415">De deelnemer die is geïdentificeerd als de afzender van het item, moet een actief postvak hebben in de organisatie waarin het item wordt geïmporteerd.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-415">The participant who's identified as the sender of the item must have an active mailbox in the organization that the item is being imported to.</span></span> <span data-ttu-id="c4f1d-416">Als de afzender geen actief postvak heeft, wordt de volgende fout geretourneerd:</span><span class="sxs-lookup"><span data-stu-id="c4f1d-416">If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="c4f1d-417">**Aan**</span><span class="sxs-lookup"><span data-stu-id="c4f1d-417">**TO**</span></span> <br/> |<span data-ttu-id="c4f1d-418">Ja</span><span class="sxs-lookup"><span data-stu-id="c4f1d-418">Yes</span></span>  <br/> |<span data-ttu-id="c4f1d-419">De gebruiker die een item heeft ontvangen, indien van toepassing voor een item in de gegevensbron.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-419">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="c4f1d-420">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="c4f1d-420">**SUBJECT**</span></span> <br/> |<span data-ttu-id="c4f1d-421">Nee</span><span class="sxs-lookup"><span data-stu-id="c4f1d-421">No</span></span>  <br/> |<span data-ttu-id="c4f1d-422">Het onderwerp van het bronitem.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-422">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="c4f1d-423">**DATUM**</span><span class="sxs-lookup"><span data-stu-id="c4f1d-423">**DATE**</span></span> <br/> |<span data-ttu-id="c4f1d-424">Ja</span><span class="sxs-lookup"><span data-stu-id="c4f1d-424">Yes</span></span>  <br/> |<span data-ttu-id="c4f1d-425">De datum waarop het item oorspronkelijk is gemaakt of gepost in de klantgegevensbron.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-425">The date the item was originally created or posted in the customer data source.</span></span> <span data-ttu-id="c4f1d-426">Bijvoorbeeld de datum waarop een Twitter-bericht is getwitteerd.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-426">For example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="c4f1d-427">**BODY**</span><span class="sxs-lookup"><span data-stu-id="c4f1d-427">**BODY**</span></span> <br/> |<span data-ttu-id="c4f1d-428">Nee</span><span class="sxs-lookup"><span data-stu-id="c4f1d-428">No</span></span>  <br/> |<span data-ttu-id="c4f1d-429">De inhoud van het bericht of bericht.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-429">The contents of the message or post.</span></span> <span data-ttu-id="c4f1d-430">Voor sommige gegevensbronnen kan de inhoud van deze eigenschap hetzelfde zijn als de inhoud van de eigenschap **SUBJECT.**</span><span class="sxs-lookup"><span data-stu-id="c4f1d-430">For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property.</span></span> <span data-ttu-id="c4f1d-431">Tijdens het importproces probeert de partnerconnector de volledige kwaliteit van de inhoudsbron zo mogelijk te behouden.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-431">During the import process, the partner connector attempts to maintain full fidelity from the content source as possible.</span></span> <span data-ttu-id="c4f1d-432">Indien mogelijk worden bestanden, afbeeldingen of andere inhoud uit de body van het bronitem opgenomen in deze eigenschap.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-432">If possible files, graphics, or other content from the body of the source item is included in this property.</span></span> <span data-ttu-id="c4f1d-433">Anders wordt inhoud uit het bronitem opgenomen in de eigenschap **BIJLAGE.**</span><span class="sxs-lookup"><span data-stu-id="c4f1d-433">Otherwise, content from the source item is included in the **ATTACHMENT** property.</span></span> <span data-ttu-id="c4f1d-434">De inhoud van deze eigenschap is afhankelijk van de partnerconnector en van de mogelijkheden van het bronplatform.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-434">The contents of this property depends on the partner connector and on the capability of the source platform.</span></span>  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="c4f1d-435">**BIJLAGE**</span><span class="sxs-lookup"><span data-stu-id="c4f1d-435">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="c4f1d-436">Nee</span><span class="sxs-lookup"><span data-stu-id="c4f1d-436">No</span></span>  <br/> |<span data-ttu-id="c4f1d-437">Als een item in de gegevensbron (zoals een tweet in Twitter of een chatgesprek) een bijgevoegd bestand heeft of afbeeldingen bevat, wordt eerst geprobeerd om bijlagen in de eigenschap **BODY** op te nemen.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-437">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property.</span></span> <span data-ttu-id="c4f1d-438">Als dat niet mogelijk is, wordt deze toegevoegd aan de eigenschap \*\* BIJLAGE \*\*.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-438">If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property.</span></span> <span data-ttu-id="c4f1d-439">Andere voorbeelden van bijlagen zijn Vind ik leuks in Facebook, metagegevens uit de inhoudsbron en antwoorden op een bericht of bericht.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-439">Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.</span></span>  <br/> | `image.gif` <br/> |
    |<span data-ttu-id="c4f1d-440">**BERICHTKLASSE**</span><span class="sxs-lookup"><span data-stu-id="c4f1d-440">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="c4f1d-441">Ja</span><span class="sxs-lookup"><span data-stu-id="c4f1d-441">Yes</span></span>  <br/> | <span data-ttu-id="c4f1d-442">Dit is een eigenschap met meerdere waarden, die wordt gemaakt en ingevuld door partnerconnector.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-442">This is a multi-value property, which is created and populated by partner connector.</span></span> <span data-ttu-id="c4f1d-443">De notatie van deze eigenschap is  `IPM.NOTE.Source.Event` .</span><span class="sxs-lookup"><span data-stu-id="c4f1d-443">The format of this property is  `IPM.NOTE.Source.Event`.</span></span> <span data-ttu-id="c4f1d-444">(Deze eigenschap moet beginnen met  `IPM.NOTE` .</span><span class="sxs-lookup"><span data-stu-id="c4f1d-444">(This property must begin with  `IPM.NOTE`.</span></span> <span data-ttu-id="c4f1d-445">Deze indeling is vergelijkbaar met de indeling voor de  `IPM.NOTE.X` berichtenklasse.) Deze eigenschap bevat de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="c4f1d-445">This format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:</span></span>  <br/><br/><span data-ttu-id="c4f1d-446">`Source`: geeft de gegevensbron van derden aan; bijvoorbeeld Twitter, Facebook of BlackBerry.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-446">`Source`: Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="c4f1d-447">`Event`: geeft het type activiteit aan dat is uitgevoerd in de gegevensbron van derden die de items heeft geproduceerd; bijvoorbeeld een tweet in Twitter of een bericht op Facebook.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-447">`Event`: Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook.</span></span> <span data-ttu-id="c4f1d-448">Gebeurtenissen zijn specifiek voor de gegevensbron.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-448">Events are specific to the data source.</span></span>  <br/> <br/>  <span data-ttu-id="c4f1d-449">Een van de doeleinden van deze eigenschap is om specifieke items te filteren op basis van de gegevensbron waar een item vandaan komt of op basis van het type gebeurtenis.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-449">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event.</span></span> <span data-ttu-id="c4f1d-450">In een eDiscovery-zoekopdracht kunt u bijvoorbeeld een zoekquery maken om alle tweets te vinden die door een specifieke gebruiker zijn gepost.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-450">For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.</span></span>  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |

- <span data-ttu-id="c4f1d-451">Wanneer items zijn geïmporteerd in postvakken in Microsoft 365, wordt een unieke id als onderdeel van het HTTP-antwoord teruggegeven aan de beller.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-451">When items are successfully imported to mailboxes in Microsoft 365, a unique identifier is returned back to the caller as part of the HTTP response.</span></span> <span data-ttu-id="c4f1d-452">Deze id, genaamd , kan worden gebruikt voor latere probleemoplossingsdoeleinden door partners voor  `x-IngestionCorrelationID` het end-to-end bijhouden van items.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-452">This identifier, called  `x-IngestionCorrelationID`, can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items.</span></span> <span data-ttu-id="c4f1d-453">Het wordt aangeraden dat partners deze gegevens vastleggen en dienovereenkomstig aan hun einde aanmelden.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-453">It's recommended that partners capture this information and log it accordingly at their end.</span></span> <span data-ttu-id="c4f1d-454">Hier is een voorbeeld van een HTTP-antwoord met deze id:</span><span class="sxs-lookup"><span data-stu-id="c4f1d-454">Here's an example of an HTTP response showing this identifier:</span></span>

    ```http
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT
    ```

- <span data-ttu-id="c4f1d-455">U kunt het hulpprogramma Inhoud zoeken in het beveiligings- en compliancecentrum gebruiken om te zoeken naar items die zijn geïmporteerd in postvakken van een externe gegevensbron.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-455">You can use the Content Search tool in the security and compliance center to search for items that were imported to mailboxes from a third-party data source.</span></span> <span data-ttu-id="c4f1d-456">Als u specifiek wilt zoeken naar deze geïmporteerde items, kunt u de volgende eigenschapswaardeparen voor berichten gebruiken in het trefwoordvak voor een inhoudszoekactie.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-456">To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search.</span></span>

  - <span data-ttu-id="c4f1d-457">**`kind:externaldata`**: Gebruik dit eigenschapswaardepaar om alle gegevenstypen van derden te doorzoeken.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-457">**`kind:externaldata`**: Use this property-value pair to search all third-party data types.</span></span> <span data-ttu-id="c4f1d-458">Als u bijvoorbeeld wilt zoeken naar items die zijn geïmporteerd uit een externe gegevensbron en het woord 'contoso' bevatten in de eigenschap Onderwerp van het geïmporteerde item, gebruikt u de trefwoordquery. `kind:externaldata AND subject:contoso`</span><span class="sxs-lookup"><span data-stu-id="c4f1d-458">For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>

  - <span data-ttu-id="c4f1d-459">**`itemclass:ipm.externaldata.<third-party data type>`**: Gebruik dit eigenschapswaardepaar om alleen te zoeken in een opgegeven type gegevens van derden.</span><span class="sxs-lookup"><span data-stu-id="c4f1d-459">**`itemclass:ipm.externaldata.<third-party data type>`**: Use this property-value pair to only search a specify type of third-party data.</span></span> <span data-ttu-id="c4f1d-460">Als u bijvoorbeeld alleen wilt zoeken op Facebook-gegevens met het woord 'contoso' in de eigenschap Onderwerp, gebruikt u de trefwoordquery. `itemclass:ipm.externaldata.Facebook* AND subject:contoso`</span><span class="sxs-lookup"><span data-stu-id="c4f1d-460">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span>

  <span data-ttu-id="c4f1d-461">Zie Inhoud zoeken gebruiken om te zoeken naar gegevens van derden die zijn geïmporteerd in Microsoft 365 voor een volledige lijst met waarden die u wilt gebruiken voor gegevenstypen van derden `itemclass` [voor de eigenschap.](use-content-search-to-search-third-party-data-that-was-imported.md)</span><span class="sxs-lookup"><span data-stu-id="c4f1d-461">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Microsoft 365](use-content-search-to-search-third-party-data-that-was-imported.md).</span></span>

   <span data-ttu-id="c4f1d-462">Zie voor meer informatie over het gebruik van Inhoud zoeken en het maken van zoekquery's voor trefwoorden:</span><span class="sxs-lookup"><span data-stu-id="c4f1d-462">For more information about using Content Search and creating keyword search queries, see:</span></span>

  - [<span data-ttu-id="c4f1d-463">Zoeken naar inhoud</span><span class="sxs-lookup"><span data-stu-id="c4f1d-463">Content Search</span></span>](content-search.md)

  - [<span data-ttu-id="c4f1d-464">Trefwoordquery's en zoekvoorwaarden voor Zoeken naar inhoud</span><span class="sxs-lookup"><span data-stu-id="c4f1d-464">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)