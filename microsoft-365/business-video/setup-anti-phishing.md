---
title: Anti-phishingbeveiliging instellen
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: Meer informatie over het instellen van anti-phishingbeveiliging.
ms.openlocfilehash: 32494eda4496d99e5e5f4def213ba7876f6c3183
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580412"
---
# <a name="set-up-anti-phishing"></a><span data-ttu-id="50061-103">Beleid tegen phishing instellen</span><span class="sxs-lookup"><span data-stu-id="50061-103">Set up anti-phishing</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

<span data-ttu-id="50061-104">Phishing is een kwaadaardige aanval waarbij een e-mailbericht lijkt te zijn verzonden vanuit een vertrouwde bron, maar probeert uw persoonlijke gegevens te verzamelen.</span><span class="sxs-lookup"><span data-stu-id="50061-104">Phishing is a malicious attack where an email looks like it was sent from a familiar source, but it attempts to collect your personal information.</span></span> <span data-ttu-id="50061-105">Standaard bevat Microsoft 365 bescherming tegen phishing, maar u kunt deze beveiliging vergroten door de instellingen te verfijnen.</span><span class="sxs-lookup"><span data-stu-id="50061-105">By default, Microsoft 365 includes some anti-phishing protection, but you can increase that protection by refining the settings.</span></span> <span data-ttu-id="50061-106">Laten we eens kijken.</span><span class="sxs-lookup"><span data-stu-id="50061-106">Let's take a look.</span></span>

## <a name="try-it"></a><span data-ttu-id="50061-107">Probeer het zelf!</span><span class="sxs-lookup"><span data-stu-id="50061-107">Try it!</span></span>

1. <span data-ttu-id="50061-108">Selecteer in het beheercentrum bij [https://admin.microsoft.com](https://admin.microsoft.com) , **Beveiliging**, **Bedreigingsbeheer**, **Beleid** en vervolgens **ATP Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="50061-108">In the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), select **Security**, **Threat Management**, **Policy**, then **ATP Anti-phishing**.</span></span>
1. <span data-ttu-id="50061-109">Selecteer **Standaardbeleid om** het te verfijnen.</span><span class="sxs-lookup"><span data-stu-id="50061-109">Select **Default Policy** to refine it.</span></span>
1. <span data-ttu-id="50061-110">Selecteer bewerken in de  **sectie Imitatie.**</span><span class="sxs-lookup"><span data-stu-id="50061-110">In the **Impersonation** section, select **Edit**.</span></span>
1. <span data-ttu-id="50061-111">Ga naar **Domeinen toevoegen om deze te beveiligen** en selecteer de schakelknop om automatisch de domeinen op te nemen die u bezit.</span><span class="sxs-lookup"><span data-stu-id="50061-111">Go to **Add domains to protect** and select the toggle to automatically include the domains you own.</span></span>
1. <span data-ttu-id="50061-112">Ga naar **Acties,** open de vervolgkeuzekeuze als **e-mail wordt** verzonden door een nagebootsde gebruiker en kies de juiste actie.</span><span class="sxs-lookup"><span data-stu-id="50061-112">Go to **Actions**, open the drop-down **If email is sent by an impersonated user**, and choose the action you want.</span></span>

    <span data-ttu-id="50061-113">Open de vervolgkeuzekeuze **als e-mail wordt verzonden door een nagebootsd domein** en kies de juiste actie.</span><span class="sxs-lookup"><span data-stu-id="50061-113">Open the drop-down **If email is sent by an impersonated domain** and choose the action you want.</span></span>
1. <span data-ttu-id="50061-114">Selecteer **Veiligheidstips voor imitatie in- en uit.**</span><span class="sxs-lookup"><span data-stu-id="50061-114">Select **Turn on impersonation safety tips**.</span></span> <span data-ttu-id="50061-115">Kies of gebruikers tips moeten krijgen wanneer het systeem nagebootsde gebruikers, domeinen of ongebruikelijke tekens detecteert.</span><span class="sxs-lookup"><span data-stu-id="50061-115">Choose whether tips should be provided to users when the system detects impersonated users, domains, or unusual characters.</span></span> <span data-ttu-id="50061-116">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="50061-116">Select **Save**.</span></span>
1. <span data-ttu-id="50061-117">Selecteer **Postvakintelligentie** en controleer of deze is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="50061-117">Select **Mailbox intelligence** and verify that it's turned on.</span></span> <span data-ttu-id="50061-118">Hierdoor kan uw e-mail efficiënter zijn door gebruikspatronen te leren.</span><span class="sxs-lookup"><span data-stu-id="50061-118">This allows your email to be more efficient by learning usage patterns.</span></span>
1. <span data-ttu-id="50061-119">Kies **Vertrouwde afzenders en domeinen toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="50061-119">Choose **Add trusted senders and domains**.</span></span> <span data-ttu-id="50061-120">Hier kunt u e-mailadressen of domeinen toevoegen die niet als imitatie moeten worden geclassificeerd.</span><span class="sxs-lookup"><span data-stu-id="50061-120">Here you can add email addresses or domains that shouldn't be classified as an impersonation.</span></span>
1. <span data-ttu-id="50061-121">Kies **Uw instellingen controleren,** controleer of alles juist is, selecteer **Opslaan** en vervolgens **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="50061-121">Choose **Review your settings**, make sure everything is correct, select **Save**, then **Close**.</span></span>

    <span data-ttu-id="50061-122">Uw organisatie heeft nu betere bescherming tegen phishing-bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="50061-122">Your organization now has better protection from phishing threats.</span></span>