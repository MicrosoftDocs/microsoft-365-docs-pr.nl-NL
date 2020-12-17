---
title: Bescherming tegen phishing instellen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
description: Meer informatie over het instellen van bescherming tegen phishing.
ms.openlocfilehash: f3a1399c8a6a51c7b14af7ffea8fbaea39cd1541
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702236"
---
# <a name="set-up-anti-phishing"></a><span data-ttu-id="f9684-103">Anti phishing instellen</span><span class="sxs-lookup"><span data-stu-id="f9684-103">Set up anti-phishing</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

<span data-ttu-id="f9684-104">Phishing is een kwaadaardige aanval waarbij een e-mailbericht eruit ziet alsof het afkomstig is van een vertrouwde bron, maar de persoon probeert uw persoonlijke gegevens te verzamelen.</span><span class="sxs-lookup"><span data-stu-id="f9684-104">Phishing is a malicious attack where an email looks like it was sent from a familiar source, but it attempts to collect your personal information.</span></span> <span data-ttu-id="f9684-105">Standaard bevat Microsoft 365 enige bescherming tegen phishing, maar u kunt deze bescherming verhogen door de instellingen te verfijnen.</span><span class="sxs-lookup"><span data-stu-id="f9684-105">By default, Microsoft 365 includes some anti-phishing protection, but you can increase that protection by refining the settings.</span></span> <span data-ttu-id="f9684-106">Laten we even kijken.</span><span class="sxs-lookup"><span data-stu-id="f9684-106">Let's take a look.</span></span>

## <a name="try-it"></a><span data-ttu-id="f9684-107">Probeer het zelf!</span><span class="sxs-lookup"><span data-stu-id="f9684-107">Try it!</span></span>

1. <span data-ttu-id="f9684-108">Selecteer in het Beheercentrum op [https://admin.microsoft.com](https://admin.microsoft.com) **beveiliging**, **risicobeheer**, **beleid** en vervolgens **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="f9684-108">In the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), select **Security**, **Threat Management**, **Policy**, then **ATP Anti-phishing**.</span></span>
1. <span data-ttu-id="f9684-109">Selecteer het **standaardbeleid** om dit te verfijnen.</span><span class="sxs-lookup"><span data-stu-id="f9684-109">Select **Default Policy** to refine it.</span></span>
1. <span data-ttu-id="f9684-110">Selecteer **bewerken** in het gedeelte **imitatie** .</span><span class="sxs-lookup"><span data-stu-id="f9684-110">In the **Impersonation** section, select **Edit**.</span></span>
1. <span data-ttu-id="f9684-111">Ga naar **domeinen toevoegen om te beschermen** en selecteer de wisselknop om automatisch de domeinnamen toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="f9684-111">Go to **Add domains to protect** and select the toggle to automatically include the domains you own.</span></span>
1. <span data-ttu-id="f9684-112">Ga naar **acties**, open de vervolgkeuzelijst **Als u e-mail verzendt door een geïmiteerde gebruiker** en kies de gewenste actie.</span><span class="sxs-lookup"><span data-stu-id="f9684-112">Go to **Actions**, open the drop-down **If email is sent by an impersonated user**, and choose the action you want.</span></span>

    <span data-ttu-id="f9684-113">Open de vervolgkeuzelijst **Als u e-mail verzendt door een geïmiteerd domein** en kies de gewenste actie.</span><span class="sxs-lookup"><span data-stu-id="f9684-113">Open the drop-down **If email is sent by an impersonated domain** and choose the action you want.</span></span>
1. <span data-ttu-id="f9684-114">Selecteer **voor het inschakelen van imitatie beveiligingstips**.</span><span class="sxs-lookup"><span data-stu-id="f9684-114">Select **Turn on impersonation safety tips**.</span></span> <span data-ttu-id="f9684-115">Geef aan of de gebruikers moeten worden aangeleverd wanneer het systeem geïmiteerde gebruikers, domeinen of ongebruikelijke tekens aantreft.</span><span class="sxs-lookup"><span data-stu-id="f9684-115">Choose whether tips should be provided to users when the system detects impersonated users, domains, or unusual characters.</span></span> <span data-ttu-id="f9684-116">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f9684-116">Select **Save**.</span></span>
1. <span data-ttu-id="f9684-117">Selecteer **Mailbox Intelligence** en controleer of dit is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="f9684-117">Select **Mailbox intelligence** and verify that it's turned on.</span></span> <span data-ttu-id="f9684-118">Zo kunt u uw e-mail efficiënter maken door patronen te leren gebruiken.</span><span class="sxs-lookup"><span data-stu-id="f9684-118">This allows your email to be more efficient by learning usage patterns.</span></span>
1. <span data-ttu-id="f9684-119">Kies **vertrouwde afzenders en domeinen toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="f9684-119">Choose **Add trusted senders and domains**.</span></span> <span data-ttu-id="f9684-120">Hier kunt u e-mailadressen of domeinen toevoegen die u niet als een imitatie mag worden geclassificeerd.</span><span class="sxs-lookup"><span data-stu-id="f9684-120">Here you can add email addresses or domains that shouldn't be classified as an impersonation.</span></span>
1. <span data-ttu-id="f9684-121">Kies **instellingen controleren**, Controleer of alles klopt, selecteer **Opslaan** en vervolgens **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="f9684-121">Choose **Review your settings**, make sure everything is correct, select **Save**, then **Close**.</span></span>

    <span data-ttu-id="f9684-122">Uw organisatie heeft nu betere beveiliging tegen phishing-bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="f9684-122">Your organization now has better protection from phishing threats.</span></span>