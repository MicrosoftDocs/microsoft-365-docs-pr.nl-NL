---
title: E-mailregels maken om ransomware te voorkomen
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
description: Meer informatie over het maken van e-mailregels om ransomware te voorkomen.
ms.openlocfilehash: 96822916753f2f70d481c213e7e31046f7081446
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580496"
---
# <a name="create-email-rules-to-prevent-ransomware"></a><span data-ttu-id="6b28c-103">E-mailregels maken om ransomware te voorkomen</span><span class="sxs-lookup"><span data-stu-id="6b28c-103">Create email rules to prevent ransomware</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

<span data-ttu-id="6b28c-104">Microsoft 365 helpt uw bedrijf te beschermen tegen ransomware door te voorkomen dat potentieel gevaarlijke bestanden, zoals JavaScript, batch en uitvoerbare bestanden, worden geopend in Outlook.</span><span class="sxs-lookup"><span data-stu-id="6b28c-104">Microsoft 365 helps protect your business against ransomware by preventing potentially dangerous files, like JavaScript, batch, and executables, from being opened in Outlook.</span></span> <span data-ttu-id="6b28c-105">Als u dit beschermingsniveau wilt verhogen door regels toe te voegen die u blokkeren of waarschuwen voor extra typen bestanden, volgt u deze stappen.</span><span class="sxs-lookup"><span data-stu-id="6b28c-105">To increase this level of protection by adding rules that block or warn you of additional types of files, follow these steps.</span></span>

## <a name="try-it"></a><span data-ttu-id="6b28c-106">Probeer het zelf!</span><span class="sxs-lookup"><span data-stu-id="6b28c-106">Try it!</span></span>

1. <span data-ttu-id="6b28c-107">Kies in het beheercentrum op [https://admin.microsoft.com](https://admin.microsoft.com) , Exchange onder **Beheercentra.** </span><span class="sxs-lookup"><span data-stu-id="6b28c-107">From the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), choose **Exchange** under **Admin centers**.</span></span>
1. <span data-ttu-id="6b28c-108">Kies e-mailstroom in het menu aan **de linkerkant.**</span><span class="sxs-lookup"><span data-stu-id="6b28c-108">From the menu on the left, choose **mail flow**.</span></span>
1. <span data-ttu-id="6b28c-109">Kies op het tabblad Regels de pijl naast het plusteken (+) en kies **vervolgens Een nieuwe regel maken.**</span><span class="sxs-lookup"><span data-stu-id="6b28c-109">On the rules tab, choose the arrow next to the plus (+) symbol, and then choose **Create a new rule**.</span></span>
1. <span data-ttu-id="6b28c-110">Voer op **de nieuwe regelpagina** een naam voor de regel in, schuif naar de onderkant en kies **meer opties.**</span><span class="sxs-lookup"><span data-stu-id="6b28c-110">On the **new rule** page, enter a name for your rule, scroll to the bottom, and then choose **More options**.</span></span>
1. <span data-ttu-id="6b28c-111">Selecteer **onder Deze regel toepassen als**, selecteer Elke **bijlage** en selecteer **vervolgens bestandsextensie bevat deze woorden.**</span><span class="sxs-lookup"><span data-stu-id="6b28c-111">Under **Apply this rule if**, select **Any attachment**, and then select **file extension includes these words**.</span></span>
1. <span data-ttu-id="6b28c-112">Voer in het vak onder woorden of woordgroepen de bestandsextensies in die u wilt toepassen op de regel, zoals **bestandsextensies** die macro's kunnen bevatten.</span><span class="sxs-lookup"><span data-stu-id="6b28c-112">In the box under **specify words or phrases**, enter the file extensions that you want the rule to be applied to, such as file extensions that can contain macros.</span></span> <span data-ttu-id="6b28c-113">Gebruik het plusteken (+) om ze een voor een toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="6b28c-113">Use the plus (+) symbol to add them one at a time.</span></span>

    <span data-ttu-id="6b28c-114">Lees Beschermen tegen ransomware voor meer informatie over [bestandstypen.](../admin/security-and-compliance/secure-your-business-data.md#ransomware)</span><span class="sxs-lookup"><span data-stu-id="6b28c-114">Learn more about file types by reading [Protect against ransomware](../admin/security-and-compliance/secure-your-business-data.md#ransomware).</span></span>

1. <span data-ttu-id="6b28c-115">Schuif omlaag om de lijst te bekijken en kies **OK.**</span><span class="sxs-lookup"><span data-stu-id="6b28c-115">Scroll down to review your list, and then choose **OK**.</span></span>
1. <span data-ttu-id="6b28c-116">Kies op **de pagina** Nieuwe regel de optie **Voorwaarde toevoegen** en kies vervolgens een voorwaarde onder Ga als volgt **te werk.**</span><span class="sxs-lookup"><span data-stu-id="6b28c-116">On the **new rule** page, choose **add condition**, and then choose a condition under **Do the following**.</span></span>
1. <span data-ttu-id="6b28c-117">U hebt een groot aantal regelopties om uit te kiezen, maar in dit voorbeeld kiezen we ervoor om de geadresseerde op de hoogte te stellen **met een bericht.**</span><span class="sxs-lookup"><span data-stu-id="6b28c-117">You have many rule options to choose from, but in this example we'll choose to **Notify the recipient with a message**.</span></span>
1. <span data-ttu-id="6b28c-118">Voer berichttekst in voor uw melding en kies **OK.**</span><span class="sxs-lookup"><span data-stu-id="6b28c-118">Enter message text for your notification, and then chose **OK**.</span></span>
1. <span data-ttu-id="6b28c-119">Optioneel: Kies op de  **nieuwe regelpagina** uitzondering toevoegen en voer alle details in voor uitzonderingen op de regel, zoals berichten van vertrouwde afzenders.</span><span class="sxs-lookup"><span data-stu-id="6b28c-119">Optional: On the **new rule** page, choose **add exception**, and enter any details for exceptions to your rule, such as messages from trusted senders.</span></span>
1. <span data-ttu-id="6b28c-120">Kies op de nieuwe regelpagina **Opslaan** en bekijk de overzichtsgegevens van de regel.</span><span class="sxs-lookup"><span data-stu-id="6b28c-120">On the new rule page, choose **Save**, and review the rule summary information provided.</span></span>