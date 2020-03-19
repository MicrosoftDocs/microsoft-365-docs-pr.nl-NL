---
title: Wat komt er in Microsoft Secure Score?
description: Beschrijft Microsoft Secure Score in het Microsoft 365-beveiligingscentrum, hoe details worden berekend en wat beveiligingsbeheerders kunnen verwachten.
keywords: beveiliging, malware, Microsoft 365, M365, beveiligde score, beveiligingscentrum, verbeteracties
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: efb75f26d66258880c9defa94869f27e18685052
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42812884"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="1fc3f-104">Wat komt er in Microsoft Secure Score?</span><span class="sxs-lookup"><span data-stu-id="1fc3f-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="1fc3f-105">Om van Microsoft Secure Score een betere vertegenwoordiger van uw beveiligingshouding te maken en de bruikbaarheid te verbeteren, voeren we in de nabije toekomst enkele wijzigingen door.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="1fc3f-106">Je score en de maximaal mogelijke score zullen veranderen.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="1fc3f-107">Dit impliceert echter geen verandering in uw beveiligingshouding.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="1fc3f-108">Zie Nieuwe wijzigingen in Microsoft Secure Score voor meer informatie over recente [wijzigingen?](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="1fc3f-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="march-16th-2020"></a><span data-ttu-id="1fc3f-109">16 maart 2020</span><span class="sxs-lookup"><span data-stu-id="1fc3f-109">March 16th 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="1fc3f-110">Verbeteringsacties verwijderen die niet voldoen aan de verwachtingen voor betrouwbare meting of geen nuttige weergave van beveiligingshouding bieden</span><span class="sxs-lookup"><span data-stu-id="1fc3f-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="1fc3f-111">Om ervoor te zorgen dat de Microsoft Secure Score zinvol is en dat elke verbeteringsactie meetbaar en betrouwbaar is, verwijderen we de volgende verbeteracties.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="1fc3f-112">Gebruikersdocumenten opslaan in OneDrive voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="1fc3f-112">Store user documents in OneDrive for Business</span></span>
- <span data-ttu-id="1fc3f-113">Office 365 ATP-beleid voor veilige bijlagen instellen</span><span class="sxs-lookup"><span data-stu-id="1fc3f-113">Set up Office 365 ATP Safe Attachment policies</span></span>
- <span data-ttu-id="1fc3f-114">Veilige koppelingen van Office 365 instellen om URL's te verifiëren</span><span class="sxs-lookup"><span data-stu-id="1fc3f-114">Set up Office 365 Safe Links to verify URLs</span></span>
- <span data-ttu-id="1fc3f-115">Postvakdelegatie niet toestaan</span><span class="sxs-lookup"><span data-stu-id="1fc3f-115">Do not allow mailbox delegation</span></span>
- <span data-ttu-id="1fc3f-116">Anonieme koppelingen voor het delen van gasten toestaan voor sites en documenten</span><span class="sxs-lookup"><span data-stu-id="1fc3f-116">Allow anonymous guest sharing links for sites and docs</span></span>
- <span data-ttu-id="1fc3f-117">Beveiligingsconsole voor cloudapps inschakelen</span><span class="sxs-lookup"><span data-stu-id="1fc3f-117">Turn on Cloud App Security Console</span></span>
- <span data-ttu-id="1fc3f-118">Vervaldatum configureren voor koppelingen voor extern delen</span><span class="sxs-lookup"><span data-stu-id="1fc3f-118">Configure expiration time for external sharing links</span></span>

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a><span data-ttu-id="1fc3f-119">Ondersteuning voor beveiligingsstandaarden voor Azure AD-verbeteringsacties</span><span class="sxs-lookup"><span data-stu-id="1fc3f-119">Supporting security defaults for Azure AD improvement actions</span></span>

<span data-ttu-id="1fc3f-120">Microsoft Secure Score werkt verbeteracties bij ter ondersteuning van [beveiligingsstandaarden in Azure AD,](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)waardoor het eenvoudiger wordt om uw organisatie te beschermen met vooraf geconfigureerde beveiligingsinstellingen voor veelvoorkomende aanvallen.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-120">Microsoft Secure Score will be updating improvement actions to support [security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="1fc3f-121">Het zal van invloed zijn op de volgende verbeteringsacties:</span><span class="sxs-lookup"><span data-stu-id="1fc3f-121">It will affect the following improvement actions:</span></span>

- <span data-ttu-id="1fc3f-122">Ervoor zorgen dat alle gebruikers meervoudige verificatie kunnen voltooien voor veilige toegang</span><span class="sxs-lookup"><span data-stu-id="1fc3f-122">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="1fc3f-123">MFA vereisen voor administratieve rollen</span><span class="sxs-lookup"><span data-stu-id="1fc3f-123">Require MFA for administrative roles</span></span>
- <span data-ttu-id="1fc3f-124">Beleid inschakelen om verouderde verificatie te blokkeren</span><span class="sxs-lookup"><span data-stu-id="1fc3f-124">Enable policy to block legacy authentication</span></span>
