---
title: Microsoft 365-compliance-ondersteuning voor release-notes van dubbel-byte-tekenset (preview)
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Release-notes voor ondersteuning van dubbel-byte-tekensets.
ms.openlocfilehash: 1c2244c49a92aa2c00fad06caa8194cf7e32220e
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/22/2020
ms.locfileid: "52161543"
---
# <a name="support-for-double-byte-character-set-release-notes-preview"></a><span data-ttu-id="4b163-103">Ondersteunding voor release-notes van dubbel-byte-tekenset (preview)</span><span class="sxs-lookup"><span data-stu-id="4b163-103">Support for double byte character set release notes (preview)</span></span>

 <span data-ttu-id="4b163-104">Microsoft 365 Information Protection ondersteunt momenteel talen voor preview van dubbel-byte-tekensets voor:</span><span class="sxs-lookup"><span data-stu-id="4b163-104">Microsoft 365 Information Protection now supports in preview double byte character set languages for:</span></span>

- <span data-ttu-id="4b163-105">Chinees (vereenvoudigd)</span><span class="sxs-lookup"><span data-stu-id="4b163-105">Chinese (simplified)</span></span>
- <span data-ttu-id="4b163-106">Chinees (traditioneel)</span><span class="sxs-lookup"><span data-stu-id="4b163-106">Chinese (traditional)</span></span>
- <span data-ttu-id="4b163-107">Koreaans</span><span class="sxs-lookup"><span data-stu-id="4b163-107">Korean</span></span>
- <span data-ttu-id="4b163-108">Japans</span><span class="sxs-lookup"><span data-stu-id="4b163-108">Japanese</span></span>

<span data-ttu-id="4b163-109">Deze ondersteuning is beschikbaar voor gevoelige informatietypen en sleutelwoordboeken. Deze wordt weerspiegeld in preventie van gegevensverlies, communicatiecompliance, Exchange Online, SharePoint Online, OneDrive voor Bedrijven en Teams-oplossingen.</span><span class="sxs-lookup"><span data-stu-id="4b163-109">This support is available for sensitive information types and keyword dictionaries and will be reflected in data loss prevention, communications compliance, Exchange Online, SharePoint Online, OneDrive for Business, and Teams solutions.</span></span>

## <a name="known-issues"></a><span data-ttu-id="4b163-110">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="4b163-110">Known issues</span></span>

- <span data-ttu-id="4b163-111">Als een tekstbestand dat als bijlage is toegevoegd aan een e-mailbericht in UTF-8-formaat zonder bytevolgordemarkering (BOM), wordt het e-mailbericht niet gedetecteerd door het communicatie-compliancebeleid.</span><span class="sxs-lookup"><span data-stu-id="4b163-111">When a text file attached to an email is in UTF-8 format without byte order mark (BOM), the email is not detected by the Communication Compliance policy.</span></span>

- <span data-ttu-id="4b163-112">Communicatie-compliancebeleid kan waarden niet detecteren als een zin is ingevoerd voor de beleidsvoorwaarde: 'Bericht bevat de volgende woorden'.</span><span class="sxs-lookup"><span data-stu-id="4b163-112">Communication Compliance policies cannot detect values if a sentence is entered for the policy condition: “Message contains any of these words”.</span></span> <span data-ttu-id="4b163-113">Als de opgegeven tekst in het beleid als een woord is uitgeschreven, kan het gedetecteerd worden. Als het echter in het midden van een zin is geschreven, zal het niet gedetecteerd worden.</span><span class="sxs-lookup"><span data-stu-id="4b163-113">If the text specified in the policy is written as a word, it can be detected; however, if it is written in the middle of a sentence, it will not be detected.</span></span>

- <span data-ttu-id="4b163-114">Communicatie-compliancebeleid dat woordenboeken specificeert als letterbeeldinformatie, kan privé-chats en kanaalchats in Teams niet detecteren.</span><span class="sxs-lookup"><span data-stu-id="4b163-114">Communication Compliance policies that specify dictionaries as type information do not detect Teams private chats and channel chats.</span></span>

- <span data-ttu-id="4b163-115">De volgende voorwaarden worden in deze fase niet ondersteund door communicatie-compliance (er wordt aan een oplossing voor deze problemen gewerkt):</span><span class="sxs-lookup"><span data-stu-id="4b163-115">The following conditions are not supported for Communication Compliance at this stage (we plan to fix these issues in the future):</span></span> 
  - <span data-ttu-id="4b163-116">'Bericht bevat deze worden'</span><span class="sxs-lookup"><span data-stu-id="4b163-116">“Message contains any of these words”</span></span>
  - <span data-ttu-id="4b163-117">'Bericht bevat geen van deze worden'</span><span class="sxs-lookup"><span data-stu-id="4b163-117">“Message contains none of these words”</span></span>
  - <span data-ttu-id="4b163-118">'Bijlage bevat deze worden'</span><span class="sxs-lookup"><span data-stu-id="4b163-118">“Attachment contains any of these words”</span></span>
  - <span data-ttu-id="4b163-119">'Bijlage bevat deze worden'</span><span class="sxs-lookup"><span data-stu-id="4b163-119">“Attachment contains any of these words”</span></span>

<span data-ttu-id="4b163-120">We raden in plaats daarvan aan een aangepast type gevoelige gegevens (SIT) met sleutelwoordenboek te maken, dat patronen in berichten en bijlagen kan detecteren. Gebruik deze aangepaste SIT als een voorwaarde voor communicatie-compliancebeleid.</span><span class="sxs-lookup"><span data-stu-id="4b163-120">Instead we recommend creating a custom Sensitive Information Type (SIT) with keyword dictionary which will detect patterns across messages and attachments, and using this custom SIT as a Communication Compliance policy condition.</span></span>
