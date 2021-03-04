---
title: Anti-phishingbeveiliging instellen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informatie over het instellen van beveiliging tegen phishing.
ms.openlocfilehash: 8cef8f916a8a3e2b27dd7f76ddecd921d59ca0c4
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/04/2021
ms.locfileid: "50422001"
---
# <a name="set-up-anti-phishing"></a><span data-ttu-id="c823b-103">Beleid tegen phishing instellen</span><span class="sxs-lookup"><span data-stu-id="c823b-103">Set up anti-phishing</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

<span data-ttu-id="c823b-104">Phishing is een kwaadaardige aanval waarbij het lijkt alsof een e-mailbericht afkomstig is van een bekende bron, maar waarin wordt geprobeerd uw persoonlijke gegevens te verzamelen.</span><span class="sxs-lookup"><span data-stu-id="c823b-104">Phishing is a malicious attack where an email looks like it was sent from a familiar source, but it attempts to collect your personal information.</span></span> <span data-ttu-id="c823b-105">Microsoft 365 bevat standaard enige beveiliging tegen phishing, maar u kunt deze beveiliging verhogen door de instellingen te verfijnen.</span><span class="sxs-lookup"><span data-stu-id="c823b-105">By default, Microsoft 365 includes some anti-phishing protection, but you can increase that protection by refining the settings.</span></span> <span data-ttu-id="c823b-106">Laten we eens kijken.</span><span class="sxs-lookup"><span data-stu-id="c823b-106">Let's take a look.</span></span>

## <a name="try-it"></a><span data-ttu-id="c823b-107">Probeer het zelf!</span><span class="sxs-lookup"><span data-stu-id="c823b-107">Try it!</span></span>

1. <span data-ttu-id="c823b-108">Selecteer in het [https://admin.microsoft.com](https://admin.microsoft.com) beheercentrum Beveiliging, **Bedreigingsbeheer,** **Beleid** en vervolgens **ATP Anti-phishing.** </span><span class="sxs-lookup"><span data-stu-id="c823b-108">In the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), select **Security**, **Threat Management**, **Policy**, then **ATP Anti-phishing**.</span></span>
1. <span data-ttu-id="c823b-109">Selecteer **Standaardbeleid om** dit te verfijnen.</span><span class="sxs-lookup"><span data-stu-id="c823b-109">Select **Default Policy** to refine it.</span></span>
1. <span data-ttu-id="c823b-110">Selecteer Bewerken **in de** sectie **Imitatie.**</span><span class="sxs-lookup"><span data-stu-id="c823b-110">In the **Impersonation** section, select **Edit**.</span></span>
1. <span data-ttu-id="c823b-111">Ga naar **Domeinen toevoegen om te beveiligen en** selecteer de schakelknop om automatisch de domeinen op te nemen die u bezit.</span><span class="sxs-lookup"><span data-stu-id="c823b-111">Go to **Add domains to protect** and select the toggle to automatically include the domains you own.</span></span>
1. <span data-ttu-id="c823b-112">Ga naar **Acties,** open de vervolgkeuzekeuzen Als e-mail wordt verzonden door een **gemitmiteerde** gebruiker en kies de 3D-actie.</span><span class="sxs-lookup"><span data-stu-id="c823b-112">Go to **Actions**, open the drop-down **If email is sent by an impersonated user**, and choose the action you want.</span></span>

    <span data-ttu-id="c823b-113">Open de vervolgkeuzekeuzen **Als e-mail wordt verzonden door een gemitmiteerd** domein en kies de 3D-actie die u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c823b-113">Open the drop-down **If email is sent by an impersonated domain** and choose the action you want.</span></span>
1. <span data-ttu-id="c823b-114">Selecteer **Veiligheidstips voor imitatie in turn on.**</span><span class="sxs-lookup"><span data-stu-id="c823b-114">Select **Turn on impersonation safety tips**.</span></span> <span data-ttu-id="c823b-115">Kies of tips moeten worden gegeven aan gebruikers wanneer het systeem imitatie-gebruikers, domeinen of ongebruikelijke tekens detecteert.</span><span class="sxs-lookup"><span data-stu-id="c823b-115">Choose whether tips should be provided to users when the system detects impersonated users, domains, or unusual characters.</span></span> <span data-ttu-id="c823b-116">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c823b-116">Select **Save**.</span></span>
1. <span data-ttu-id="c823b-117">Selecteer **Postvakinformatie** en controleer of deze is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="c823b-117">Select **Mailbox intelligence** and verify that it's turned on.</span></span> <span data-ttu-id="c823b-118">Hierdoor kan uw e-mail efficiënter worden door gebruikspatronen te leren.</span><span class="sxs-lookup"><span data-stu-id="c823b-118">This allows your email to be more efficient by learning usage patterns.</span></span>
1. <span data-ttu-id="c823b-119">Kies **Vertrouwde afzenders en domeinen toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="c823b-119">Choose **Add trusted senders and domains**.</span></span> <span data-ttu-id="c823b-120">Hier kunt u e-mailadressen of domeinen toevoegen die niet moeten worden geclassificeerd als een imitatie.</span><span class="sxs-lookup"><span data-stu-id="c823b-120">Here you can add email addresses or domains that shouldn't be classified as an impersonation.</span></span>
1. <span data-ttu-id="c823b-121">Kies **Uw instellingen controleren,** controleer of alles juist is, selecteer **Opslaan** en vervolgens **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="c823b-121">Choose **Review your settings**, make sure everything is correct, select **Save**, then **Close**.</span></span>

    <span data-ttu-id="c823b-122">Uw organisatie is nu beter beschermd tegen phishing-bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="c823b-122">Your organization now has better protection from phishing threats.</span></span>