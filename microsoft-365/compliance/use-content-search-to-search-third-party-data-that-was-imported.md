---
title: Inhoud zoeken gebruiken om geïmporteerde gegevens van derden te doorzoeken
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: Gebruik het hulpprogramma Inhoud zoeken eDiscovery om te zoeken naar items die zijn geïmporteerd in postvakken in Microsoft 365 van een externe gegevensbron door query's te maken.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 24ca63cf78b85f7b8b5181d5babd16058b641128
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/01/2020
ms.locfileid: "52161487"
---
# <a name="use-content-search-to-search-third-party-data-imported-by-a-custom-partner-connector"></a><span data-ttu-id="c4316-103">Inhoud zoeken gebruiken om door een aangepaste partnerconnector geïmporteerde gegevens van derden te doorzoeken</span><span class="sxs-lookup"><span data-stu-id="c4316-103">Use Content Search to search third-party data imported by a custom partner connector</span></span>

<span data-ttu-id="c4316-104">U kunt het hulpprogramma Inhoud zoeken [eDiscovery](content-search.md) in het beveiligings- & compliancecentrum gebruiken om te zoeken naar items die zijn geïmporteerd in postvakken in Microsoft 365 van een externe gegevensbron.</span><span class="sxs-lookup"><span data-stu-id="c4316-104">You can use the [Content Search eDiscovery tool](content-search.md) in the Security & Compliance Center to search for items imported to mailboxes in Microsoft 365 from a third-party data source.</span></span> <span data-ttu-id="c4316-105">U kunt een query maken om alle geïmporteerde gegevensitems van derden te doorzoeken of u kunt een query maken om specifieke gegevensitems van derden te doorzoeken.</span><span class="sxs-lookup"><span data-stu-id="c4316-105">You can create a query to search all imported third-party data items or you can create a query to search specific third-party data items.</span></span> <span data-ttu-id="c4316-106">U kunt ook een bewaarbeleid op basis van query's of een eDiscovery-bewaring op basis van query's maken om gegevens van derden te behouden.</span><span class="sxs-lookup"><span data-stu-id="c4316-106">Also, you can also create a query-based retention policy or a query-based eDiscovery hold to preserve third-party data.</span></span>
  
<span data-ttu-id="c4316-107">Zie Werken met een partner om gegevens van derden te archiveren in Office 365 voor meer informatie over het werken met een partner om gegevens van derden te importeren en een lijst met de gegevenstypen van derden die u kunt importeren [in](work-with-partner-to-archive-third-party-data.md)Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c4316-107">For more information about working with a partner to import third-party data and a list of the third-party data types that you can import to Microsoft 365, see [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c4316-108">De richtlijnen in dit artikel zijn alleen van toepassing op gegevens van derden die zijn geïmporteerd door een aangepaste partnerconnector.</span><span class="sxs-lookup"><span data-stu-id="c4316-108">The guidance in this article only applies to third-party data that was imported by a custom partner connector.</span></span> <span data-ttu-id="c4316-109">Dit artikel is niet van toepassing op gegevens van derden die worden geïmporteerd met behulp van de gegevensconnectoren van derden in het [Microsoft-compliancecentrum.](archiving-third-party-data.md#third-party-data-connectors)</span><span class="sxs-lookup"><span data-stu-id="c4316-109">This article doesn't apply to third-party data that is imported by using the [third-party data connectors](archiving-third-party-data.md#third-party-data-connectors) in the Microsoft compliance center.</span></span>
  
## <a name="creating-a-query-to-search-all-third-party-data"></a><span data-ttu-id="c4316-110">Een query maken om alle gegevens van derden te doorzoeken</span><span class="sxs-lookup"><span data-stu-id="c4316-110">Creating a query to search all third-party data</span></span>

<span data-ttu-id="c4316-111">Als u elk type gegevens van derden wilt doorzoeken (of in de wacht wilt zetten) dat u hebt geïmporteerd in Office 365, kunt u het eigenschap-waardepaar bericht gebruiken in het trefwoordvak voor een inhoudszoekactie of bij het maken van een op query's gebaseerde `kind:externaldata` hold.</span><span class="sxs-lookup"><span data-stu-id="c4316-111">To search (or place on hold) any type of third-party data that you've imported to Office 365, you can use the  `kind:externaldata` message property-value pair in the keyword box for a Content Search or when creating a query-based hold.</span></span> <span data-ttu-id="c4316-112">Als u bijvoorbeeld wilt zoeken naar items die zijn geïmporteerd uit een externe gegevensbron en het woord 'contoso' in de eigenschap Onderwerp van het geïmporteerde item wilt bevatten, gebruikt u de volgende query:</span><span class="sxs-lookup"><span data-stu-id="c4316-112">For example, to search for items imported from any third-party data source and contain the word "contoso" in the Subject property of the imported item, you would use the following query:</span></span> 
  
```powershell
kind:externaldata AND subject:contoso
```

<span data-ttu-id="c4316-113">Het vorige trefwoordqueryvoorbeeld bevat de eigenschap onderwerp.</span><span class="sxs-lookup"><span data-stu-id="c4316-113">The previous keyword query example includes the subject property.</span></span> <span data-ttu-id="c4316-114">Zie de sectie Meer informatie in Samenwerken met een partner om gegevens van derden te archiveren in Office 365 voor een lijst met andere eigenschappen voor gegevensitems van derden die kunnen worden opgenomen in een [trefwoordquery.](work-with-partner-to-archive-third-party-data.md#more-information)</span><span class="sxs-lookup"><span data-stu-id="c4316-114">For a list of other properties for third-party data items that can include in a keyword query, see the "More information" section in [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md#more-information).</span></span>
  
<span data-ttu-id="c4316-115">Wanneer u query's maakt om gegevens van derden te doorzoeken en vast te houden, kunt u ook voorwaarden gebruiken om de zoekresultaten te beperken.</span><span class="sxs-lookup"><span data-stu-id="c4316-115">When creating queries to search and hold third-party data, you can also use conditions to narrow the search results.</span></span> <span data-ttu-id="c4316-116">Zie Trefwoordenquery's en zoekvoorwaarden voor Inhoud zoeken voor meer informatie over het maken van [inhoudszoekquery's.](keyword-queries-and-search-conditions.md)</span><span class="sxs-lookup"><span data-stu-id="c4316-116">For more information about creating Content Search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a><span data-ttu-id="c4316-117">Een query maken om specifieke typen gegevens van derden te doorzoeken</span><span class="sxs-lookup"><span data-stu-id="c4316-117">Creating a query to search specific types of third-party data</span></span>

<span data-ttu-id="c4316-118">In plaats van alle typen gegevens van derden te doorzoeken, kunt u query's maken die alleen zoeken naar een opgegeven type gegevens van derden met behulp van de volgende bericht *eigenschap:* waardepaar in het trefwoordvak voor een inhoudszoekactie:</span><span class="sxs-lookup"><span data-stu-id="c4316-118">Instead of searching all types of third-party data, you can create queries that only search for a specify type of third-party data by using the following message *property: value* pair in the keyword box for a Content Search:</span></span>
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

<span data-ttu-id="c4316-119">Als u bijvoorbeeld wilt zoeken in Facebook-gegevens met het woord 'contoso' in de eigenschap Onderwerp, gebruikt u de volgende query:</span><span class="sxs-lookup"><span data-stu-id="c4316-119">For example, to search Facebook data that contains the word "contoso" in the Subject property, you would use the following query:</span></span>
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

<span data-ttu-id="c4316-120">De volgende tabel bevat de gegevenstypen van derden die u kunt zoeken en de waarde die u kunt gebruiken voor de eigenschap bericht om specifiek te zoeken naar dat type gegevens  `itemclass:` van derden.</span><span class="sxs-lookup"><span data-stu-id="c4316-120">The following table lists the third-party data types that you can search, and the value to use for the  `itemclass:` message property to specifically search for that type of third-party data.</span></span> <span data-ttu-id="c4316-121">De syntaxis van de query is niet case-sensitive.</span><span class="sxs-lookup"><span data-stu-id="c4316-121">The query syntax isn't case-sensitive.</span></span> 
  
|<span data-ttu-id="c4316-122">**Gegevenstype van derden**</span><span class="sxs-lookup"><span data-stu-id="c4316-122">**Third-party data type**</span></span>|<span data-ttu-id="c4316-123">**Waarde voor  `itemclass:` eigenschap**</span><span class="sxs-lookup"><span data-stu-id="c4316-123">**Value for  `itemclass:` property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c4316-124">AIM</span><span class="sxs-lookup"><span data-stu-id="c4316-124">AIM</span></span>  <br/> | `ipm.externaldata.AIM*` <br/> |
|<span data-ttu-id="c4316-125">American Idool</span><span class="sxs-lookup"><span data-stu-id="c4316-125">American Idol</span></span>  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|<span data-ttu-id="c4316-126">AOL met draaitabelclient</span><span class="sxs-lookup"><span data-stu-id="c4316-126">AOL with Pivot Client</span></span>  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|<span data-ttu-id="c4316-127">Appelsap</span><span class="sxs-lookup"><span data-stu-id="c4316-127">Apple Juice</span></span>  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|<span data-ttu-id="c4316-128">Ares</span><span class="sxs-lookup"><span data-stu-id="c4316-128">Ares</span></span>  <br/> | `ipm.externaldata.Ares*` <br/> |
|<span data-ttu-id="c4316-129">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="c4316-129">Axs Encrypted</span></span>  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|<span data-ttu-id="c4316-130">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="c4316-130">Axs Exchange</span></span>  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|<span data-ttu-id="c4316-131">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="c4316-131">Axs Local Archive</span></span>  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|<span data-ttu-id="c4316-132">Tijdelijke aanduiding Axs</span><span class="sxs-lookup"><span data-stu-id="c4316-132">Axs Placeholder</span></span>  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|<span data-ttu-id="c4316-133">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="c4316-133">Axs Signed</span></span>  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|<span data-ttu-id="c4316-134">Bazarvoice</span><span class="sxs-lookup"><span data-stu-id="c4316-134">Bazaarvoice</span></span>  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|<span data-ttu-id="c4316-135">Bearshare</span><span class="sxs-lookup"><span data-stu-id="c4316-135">Bearshare</span></span>  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|<span data-ttu-id="c4316-136">BitTorrent</span><span class="sxs-lookup"><span data-stu-id="c4316-136">BitTorrent</span></span>  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|<span data-ttu-id="c4316-137">Blackberry</span><span class="sxs-lookup"><span data-stu-id="c4316-137">Blackberry</span></span>  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|<span data-ttu-id="c4316-138">BlackBerry-oproeplogboeken</span><span class="sxs-lookup"><span data-stu-id="c4316-138">BlackBerry Call Logs</span></span>  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|<span data-ttu-id="c4316-139">BlackBerry Messenger</span><span class="sxs-lookup"><span data-stu-id="c4316-139">BlackBerry Messenger</span></span>  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|<span data-ttu-id="c4316-140">BlackBerry-pincode</span><span class="sxs-lookup"><span data-stu-id="c4316-140">BlackBerry PIN</span></span>  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|<span data-ttu-id="c4316-141">BlackBerry Sms</span><span class="sxs-lookup"><span data-stu-id="c4316-141">BlackBerry SMS</span></span>  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|<span data-ttu-id="c4316-142">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="c4316-142">Bloomberg</span></span>  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|<span data-ttu-id="c4316-143">Bloomberg-bericht</span><span class="sxs-lookup"><span data-stu-id="c4316-143">Bloomberg Message</span></span>  <br/> | `ipm.externaldata.conversation.Bloomberg Message*` <br/> |
|<span data-ttu-id="c4316-144">Berichten van Bloomberg</span><span class="sxs-lookup"><span data-stu-id="c4316-144">Bloomberg Messaging</span></span>  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|<span data-ttu-id="c4316-145">Vak</span><span class="sxs-lookup"><span data-stu-id="c4316-145">Box</span></span>  <br/> | `ipm.externaldata.Box*` <br/> |
|<span data-ttu-id="c4316-146">Cisco IM &amp; Presence Server</span><span class="sxs-lookup"><span data-stu-id="c4316-146">Cisco IM &amp; Presence Server</span></span>  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|<span data-ttu-id="c4316-147">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="c4316-147">Cisco Jabber</span></span>  <br/> | `ipm.externaldata.Jabber*` <br/> |
|<span data-ttu-id="c4316-148">CipherCloud voor Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="c4316-148">CipherCloud for Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|<span data-ttu-id="c4316-149">Directe Verbinding maken</span><span class="sxs-lookup"><span data-stu-id="c4316-149">Direct Connect</span></span>  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|<span data-ttu-id="c4316-150">Facebook</span><span class="sxs-lookup"><span data-stu-id="c4316-150">Facebook</span></span>  <br/> | `ipm.externaldata.Facebook*` <br/> |
|<span data-ttu-id="c4316-151">FastTrack</span><span class="sxs-lookup"><span data-stu-id="c4316-151">FastTrack</span></span>  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|<span data-ttu-id="c4316-152">FXConnect</span><span class="sxs-lookup"><span data-stu-id="c4316-152">FXConnect</span></span>  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|<span data-ttu-id="c4316-153">Flickr</span><span class="sxs-lookup"><span data-stu-id="c4316-153">Flickr</span></span>  <br/> | `ipm.externaldata.Flickr*` <br/> |
|<span data-ttu-id="c4316-154">Gnutella</span><span class="sxs-lookup"><span data-stu-id="c4316-154">Gnutella</span></span>  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|<span data-ttu-id="c4316-155">Google+</span><span class="sxs-lookup"><span data-stu-id="c4316-155">Google+</span></span>  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|<span data-ttu-id="c4316-156">Google Talk</span><span class="sxs-lookup"><span data-stu-id="c4316-156">Google Talk</span></span>  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|<span data-ttu-id="c4316-157">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="c4316-157">GoToMyPC</span></span>  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|<span data-ttu-id="c4316-158">HipChat</span><span class="sxs-lookup"><span data-stu-id="c4316-158">HipChat</span></span>  <br/> | `ipm.externaldata.HipChat*` <br/> |
|<span data-ttu-id="c4316-159">Hopster</span><span class="sxs-lookup"><span data-stu-id="c4316-159">Hopster</span></span>  <br/> | `ipm.externaldata.Hopster*` <br/> |
|<span data-ttu-id="c4316-160">HubConnex</span><span class="sxs-lookup"><span data-stu-id="c4316-160">HubConnex</span></span>  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|<span data-ttu-id="c4316-161">IBM Connections</span><span class="sxs-lookup"><span data-stu-id="c4316-161">IBM Connections</span></span>  <br/> | `ipm.externaldata.Connections*` <br/> |
|<span data-ttu-id="c4316-162">IBM SameTime</span><span class="sxs-lookup"><span data-stu-id="c4316-162">IBM SameTime</span></span>  <br/> | `ipm.externaldata.Sametime*` <br/> |
|<span data-ttu-id="c4316-163">ICE Chat</span><span class="sxs-lookup"><span data-stu-id="c4316-163">ICE Chat</span></span>  <br/> | `ipm.externaldata.conversation.Ice Chat*` <br/> |
|<span data-ttu-id="c4316-164">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="c4316-164">Indii Messenger</span></span>  <br/> | `ipm.externaldata.Indii*` <br/> |
|<span data-ttu-id="c4316-165">Instagram</span><span class="sxs-lookup"><span data-stu-id="c4316-165">Instagram</span></span>  <br/> | `ipm.externaldata.Instagram*` <br/> |
|<span data-ttu-id="c4316-166">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="c4316-166">Instant Bloomberg</span></span>  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|<span data-ttu-id="c4316-167">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="c4316-167">InvestEdge</span></span>  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|<span data-ttu-id="c4316-168">IRC</span><span class="sxs-lookup"><span data-stu-id="c4316-168">IRC</span></span>  <br/> | `ipm.externaldata.IRC*` <br/> |
|<span data-ttu-id="c4316-169">Jive</span><span class="sxs-lookup"><span data-stu-id="c4316-169">Jive</span></span>  <br/> | `ipm.externaldata.Jive*` <br/> |
|<span data-ttu-id="c4316-170">JiveApiRetention</span><span class="sxs-lookup"><span data-stu-id="c4316-170">JiveApiRetention</span></span>  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|<span data-ttu-id="c4316-171">JXTA</span><span class="sxs-lookup"><span data-stu-id="c4316-171">JXTA</span></span>  <br/> | `ipm.externaldata.JXTA*` <br/> |
|<span data-ttu-id="c4316-172">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="c4316-172">LinkedIn</span></span>  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|<span data-ttu-id="c4316-173">MFTP</span><span class="sxs-lookup"><span data-stu-id="c4316-173">MFTP</span></span>  <br/> | `ipm.externaldata.MFTP*` <br/> |
|<span data-ttu-id="c4316-174">Microsoft UC</span><span class="sxs-lookup"><span data-stu-id="c4316-174">Microsoft UC</span></span>  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|<span data-ttu-id="c4316-175">Mind Align</span><span class="sxs-lookup"><span data-stu-id="c4316-175">Mind Align</span></span>  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|<span data-ttu-id="c4316-176">Mobiele beveiliging</span><span class="sxs-lookup"><span data-stu-id="c4316-176">Mobile Guard</span></span>  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|<span data-ttu-id="c4316-177">MSN</span><span class="sxs-lookup"><span data-stu-id="c4316-177">MSN</span></span>  <br/> | `ipm.externaldata.MSN*` <br/> |
|<span data-ttu-id="c4316-178">MySpace</span><span class="sxs-lookup"><span data-stu-id="c4316-178">MySpace</span></span>  <br/> | `ipm.externaldata.MySpace*` <br/> |
|<span data-ttu-id="c4316-179">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="c4316-179">NEONetwork</span></span>  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|<span data-ttu-id="c4316-180">OpenNap</span><span class="sxs-lookup"><span data-stu-id="c4316-180">OpenNap</span></span>  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|<span data-ttu-id="c4316-181">Pinterest</span><span class="sxs-lookup"><span data-stu-id="c4316-181">Pinterest</span></span>  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|<span data-ttu-id="c4316-182">Pivot</span><span class="sxs-lookup"><span data-stu-id="c4316-182">Pivot</span></span>  <br/> | `ipm.externaldata.Pivot*` <br/> |
|<span data-ttu-id="c4316-183">QQ</span><span class="sxs-lookup"><span data-stu-id="c4316-183">QQ</span></span>  <br/> | `ipm.externaldata.QQ*` <br/> |
|<span data-ttu-id="c4316-184">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="c4316-184">Microsoft SharePoint</span></span>  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|<span data-ttu-id="c4316-185">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="c4316-185">Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter*` <br/> |
|<span data-ttu-id="c4316-186">Skype voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="c4316-186">Skype for Business</span></span>  <br/> | `ipm.externaldata.Skype*` <br/> |
|<span data-ttu-id="c4316-187">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="c4316-187">Slack Enterprise Grid</span></span>  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|<span data-ttu-id="c4316-188">SoftEther</span><span class="sxs-lookup"><span data-stu-id="c4316-188">SoftEther</span></span>  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|<span data-ttu-id="c4316-189">Squawker</span><span class="sxs-lookup"><span data-stu-id="c4316-189">Squawker</span></span>  <br/> | `ipm.externaldata.Squawker*` <br/> |
|<span data-ttu-id="c4316-190">Symphony</span><span class="sxs-lookup"><span data-stu-id="c4316-190">Symphony</span></span>  <br/> | `ipm.externaldata.Symphony*` <br/> |
|<span data-ttu-id="c4316-191">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="c4316-191">Thomson Reuters</span></span>  <br/> | `ipm.externaldata.Reuters*` <br/> |
| <span data-ttu-id="c4316-192">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="c4316-192">Thomson Reuters Eikon Messenger</span></span>  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|<span data-ttu-id="c4316-193">Tor</span><span class="sxs-lookup"><span data-stu-id="c4316-193">Tor</span></span>  <br/> | `ipm.externaldata.Tor*` <br/> |
|<span data-ttu-id="c4316-194">TTT</span><span class="sxs-lookup"><span data-stu-id="c4316-194">TTT</span></span>  <br/> | `ipm.externaldata.TTT*` <br/> |
|<span data-ttu-id="c4316-195">Twitter</span><span class="sxs-lookup"><span data-stu-id="c4316-195">Twitter</span></span>  <br/> | `ipm.externaldata.Twitter*` <br/> |
|<span data-ttu-id="c4316-196">UBS-chat</span><span class="sxs-lookup"><span data-stu-id="c4316-196">UBS Chat</span></span>  <br/> | `ipm.externaldata.UBS*` <br/> |
|<span data-ttu-id="c4316-197">Vimeo</span><span class="sxs-lookup"><span data-stu-id="c4316-197">Vimeo</span></span>  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|<span data-ttu-id="c4316-198">WinMX</span><span class="sxs-lookup"><span data-stu-id="c4316-198">WinMX</span></span>  <br/> | `ipm.externaldata.WinMX*` <br/> |
|<span data-ttu-id="c4316-199">Winny</span><span class="sxs-lookup"><span data-stu-id="c4316-199">Winny</span></span>  <br/> | `ipm.externaldata.Winny*` <br/> |
|<span data-ttu-id="c4316-200">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="c4316-200">Yahoo!</span></span>  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|<span data-ttu-id="c4316-201">Yammer</span><span class="sxs-lookup"><span data-stu-id="c4316-201">Yammer</span></span>  <br/> | `ipm.externaldata.Yammer*` <br/> |
|<span data-ttu-id="c4316-202">YellowJacket</span><span class="sxs-lookup"><span data-stu-id="c4316-202">YellowJacket</span></span>  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|<span data-ttu-id="c4316-203">YouTube</span><span class="sxs-lookup"><span data-stu-id="c4316-203">YouTube</span></span>  <br/> | `ipm.externaldata.YouTube*` <br/> |
