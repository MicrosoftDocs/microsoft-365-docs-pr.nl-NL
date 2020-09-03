---
title: Enterprise Access-besturingselementen voor Microsoft 365 Yammer
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Dit artikel bevat een beknopt overzicht van de besturingselementen voor Enterprise-toegangsbeheer in de productieomgeving.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b7e1ceae1b7ddda4c2eac96cd581a612768f1461
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332662"
---
# <a name="yammer-enterprise-access-controls"></a><span data-ttu-id="24f86-103">Enterprise Access-besturingselementen voor Yammer</span><span class="sxs-lookup"><span data-stu-id="24f86-103">Yammer enterprise access controls</span></span> 

<span data-ttu-id="24f86-104">Fysiek en logisch toegankelijke voor de Yammer-productieomgeving is beperkt tot een klein aantal personen (infrastructuur en bewerkingen).</span><span class="sxs-lookup"><span data-stu-id="24f86-104">Physical and logical access to the Yammer production environment is restricted to a small set of people (infrastructure and operations).</span></span> <span data-ttu-id="24f86-105">Net als met andere Microsoft 365-technici hebben Yammer-ingenieurs geen toegang tot klantgegevens.</span><span class="sxs-lookup"><span data-stu-id="24f86-105">As with other Microsoft 365 engineers, Yammer engineers have zero standing access to customer data.</span></span> <span data-ttu-id="24f86-106">U moet een verzoek indienen op basis van een goedkeuringssysteem voor een goedkeuringsproces dat is gekoppeld aan de lockbox met een beperkt aantal goedkeurders.</span><span class="sxs-lookup"><span data-stu-id="24f86-106">Access must be requested using an approval-based just-in-time access control system similar to Lockbox with a limited number of approvers.</span></span> <span data-ttu-id="24f86-107">Goedkeurders verifieert de aanvraag (bijvoorbeeld de persoon controleert of de aanvraag legitiem is op basis van behoefte, zakelijk geval, tijd, etc.) en keurt de aanvraag goed of weigert.</span><span class="sxs-lookup"><span data-stu-id="24f86-107">Approvers verify the request (for example, they verify whether the request is legitimate based on need, business case, time, etc.), and then approve or deny the request.</span></span> <span data-ttu-id="24f86-108">Als de aanvraag is goedgekeurd, wordt JIT-toegang verleend voor een gedefinieerde en beperkte tijd.</span><span class="sxs-lookup"><span data-stu-id="24f86-108">If the request is approved, JIT access is granted for a defined and limited time.</span></span> <span data-ttu-id="24f86-109">Wanneer de toegangs periode is verstreken, wordt de toegang automatisch verloopt.</span><span class="sxs-lookup"><span data-stu-id="24f86-109">After access time is exceeded, the access automatically expires.</span></span>

<span data-ttu-id="24f86-110">Net als bij andere Microsoft 365-Services, maakt alle toegang tot de Yammer-productieomgeving gebruik van meervoudige verificatie.</span><span class="sxs-lookup"><span data-stu-id="24f86-110">As with other Microsoft 365 services, all access to the Yammer production environment uses multi-factor authentication.</span></span> <span data-ttu-id="24f86-111">Alle toegang-en opdrachtgeschiedenis wordt gekenmerkd aan een gebruiker, die regelmatig is aangemeld en gecontroleerd door het Yammer-beveiligingsteam.</span><span class="sxs-lookup"><span data-stu-id="24f86-111">All access and command history is attributed to a user, and logged and reviewed regularly by the Yammer security team.</span></span>

<span data-ttu-id="24f86-112">Zie [Help voor Yammer-beheerders](https://docs.microsoft.com/yammer/yammer-landing-page)voor meer informatie over Yammer-beheer en-beheer.</span><span class="sxs-lookup"><span data-stu-id="24f86-112">For more information about Yammer administration and management, see [Yammer admin help](https://docs.microsoft.com/yammer/yammer-landing-page).</span></span>