---
title: Automatisch doorsturen van e-mail stoppen
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
description: Meer informatie over het stoppen van e-mailberichten voor automatisch doorsturen.
ms.openlocfilehash: 0683e133f6c261dc19cc098b13be298cd8086001
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701734"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="35678-103">Automatisch doorsturen van e-mail stoppen</span><span class="sxs-lookup"><span data-stu-id="35678-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="35678-104">Als een hacker toegang krijgt tot het postvak van een gebruiker, kunnen ze de e-mail van de gebruiker automatisch doorsturen naar een extern adres en de informatie over het eigendom stelen.</span><span class="sxs-lookup"><span data-stu-id="35678-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="35678-105">U kunt dit beëindigen door een e-mail stroom regel te maken.</span><span class="sxs-lookup"><span data-stu-id="35678-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="35678-106">Probeer het zelf!</span><span class="sxs-lookup"><span data-stu-id="35678-106">Try it!</span></span>

1. <span data-ttu-id="35678-107">Selecteer in het Microsoft 365-Beheercentrum de optie **Exchange**, **e-mail stroom** en klik op het tabblad **regels** op het plusteken en kies **een nieuwe regel maken**.</span><span class="sxs-lookup"><span data-stu-id="35678-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="35678-108">Selecteer **meer opties**.</span><span class="sxs-lookup"><span data-stu-id="35678-108">Select **More options**.</span></span> <span data-ttu-id="35678-109">Geef een naam op voor de nieuwe regel.</span><span class="sxs-lookup"><span data-stu-id="35678-109">Name your new rule.</span></span>
1. <span data-ttu-id="35678-110">Open vervolgens de vervolgkeuzelijst voor het **toepassen van deze regel**, en selecteer vervolgens **extern intern**.</span><span class="sxs-lookup"><span data-stu-id="35678-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="35678-111">Selecteer **binnen de organisatie** en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="35678-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="35678-112">Kies **voorwaarde toevoegen**, open de vervolgkeuzelijst, selecteer **de berichteigenschappen** en **Voeg vervolgens het berichttype toe**.</span><span class="sxs-lookup"><span data-stu-id="35678-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="35678-113">Open de vervolgkeuzelijst **berichttype selecteren** , kies **automatisch doorsturen** en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="35678-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="35678-114">Open de vervolgkeuzelijst **Ga als volgt** te werk, selecteer **het bericht blokkeren**, vervolgens **het bericht afwijzen en een uitleg toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="35678-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="35678-115">Voer de berichttekst voor de uitleg in en selecteer **OK**.</span><span class="sxs-lookup"><span data-stu-id="35678-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="35678-116">Schuif naar de onderkant en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="35678-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="35678-117">Uw regel is gemaakt en hackers kunnen geen berichten meer automatisch doorsturen.</span><span class="sxs-lookup"><span data-stu-id="35678-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>