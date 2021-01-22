---
title: E-mailregels maken om ransomware te voorkomen
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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informatie over het maken van e-mailregels om ransomware te voorkomen.
ms.openlocfilehash: 3b45af71aa26beb31e21f5db662091f46343f97d
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926112"
---
# <a name="create-email-rules-to-prevent-ransomware"></a><span data-ttu-id="e2bd4-103">E-mailregels maken om ransomware te voorkomen</span><span class="sxs-lookup"><span data-stu-id="e2bd4-103">Create email rules to prevent ransomware</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

<span data-ttu-id="e2bd4-104">Microsoft 365 helpt uw bedrijf te beschermen tegen ransomware door te voorkomen dat potentieel gevaarlijke bestanden, zoals JavaScript-, batch- en uitvoerbare bestanden, in Outlook worden geopend.</span><span class="sxs-lookup"><span data-stu-id="e2bd4-104">Microsoft 365 helps protect your business against ransomware by preventing potentially dangerous files, like JavaScript, batch, and executables, from being opened in Outlook.</span></span> <span data-ttu-id="e2bd4-105">Als u dit beschermingsniveau wilt verhogen door regels toe te voegen die u voor extra typen bestanden blokkeren of waarschuwen, volgt u deze stappen.</span><span class="sxs-lookup"><span data-stu-id="e2bd4-105">To increase this level of protection by adding rules that block or warn you of additional types of files, follow these steps.</span></span>

## <a name="try-it"></a><span data-ttu-id="e2bd4-106">Probeer het zelf!</span><span class="sxs-lookup"><span data-stu-id="e2bd4-106">Try it!</span></span>

1. <span data-ttu-id="e2bd4-107">Kies in het beheercentrum [https://admin.microsoft.com](https://admin.microsoft.com) de optie **Exchange** onder **Beheercentra.**</span><span class="sxs-lookup"><span data-stu-id="e2bd4-107">From the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), choose **Exchange** under **Admin centers**.</span></span>
1. <span data-ttu-id="e2bd4-108">Kies e-mailstroom in **het menu aan de linkerkant.**</span><span class="sxs-lookup"><span data-stu-id="e2bd4-108">From the menu on the left, choose **mail flow**.</span></span>
1. <span data-ttu-id="e2bd4-109">Kies op het tabblad Regels de pijl naast het plusteken (+) en kies **vervolgens Een nieuwe regel maken.**</span><span class="sxs-lookup"><span data-stu-id="e2bd4-109">On the rules tab, choose the arrow next to the plus (+) symbol, and then choose **Create a new rule**.</span></span>
1. <span data-ttu-id="e2bd4-110">Voer op **de nieuwe regelpagina** een naam in voor de regel, schuif omlaag en kies **Meer opties.**</span><span class="sxs-lookup"><span data-stu-id="e2bd4-110">On the **new rule** page, enter a name for your rule, scroll to the bottom, and then choose **More options**.</span></span>
1. <span data-ttu-id="e2bd4-111">Selecteer **onder Deze regel toepassen een** bijlage **en** selecteer vervolgens **de bestandsextensie die deze woorden bevat.**</span><span class="sxs-lookup"><span data-stu-id="e2bd4-111">Under **Apply this rule if**, select **Any attachment**, and then select **file extension includes these words**.</span></span>
1. <span data-ttu-id="e2bd4-112">Typ in het vak onder Typ woorden of woordgroepen de bestandsextensies die u wilt toepassen op de regel, zoals **bestandsextensies** die macro's kunnen bevatten.</span><span class="sxs-lookup"><span data-stu-id="e2bd4-112">In the box under **specify words or phrases**, enter the file extensions that you want the rule to be applied to, such as file extensions that can contain macros.</span></span> <span data-ttu-id="e2bd4-113">Gebruik het plusteken (+) om ze een voor een toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="e2bd4-113">Use the plus (+) symbol to add them one at a time.</span></span>

    <span data-ttu-id="e2bd4-114">Meer informatie over bestandstypen kunt u lezen door [Beveiligen tegen ransomware te lezen.](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware)</span><span class="sxs-lookup"><span data-stu-id="e2bd4-114">Learn more about file types by reading [Protect against ransomware](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware).</span></span>

1. <span data-ttu-id="e2bd4-115">Schuif omlaag om de lijst te controleren en kies **OK.**</span><span class="sxs-lookup"><span data-stu-id="e2bd4-115">Scroll down to review your list, and then choose **OK**.</span></span>
1. <span data-ttu-id="e2bd4-116">Kies op **de pagina** Nieuwe regel de optie **Voorwaarde toevoegen** en kies vervolgens een voorwaarde onder Ga als volgt **te werk.**</span><span class="sxs-lookup"><span data-stu-id="e2bd4-116">On the **new rule** page, choose **add condition**, and then choose a condition under **Do the following**.</span></span>
1. <span data-ttu-id="e2bd4-117">U kunt uit veel regelopties kiezen, maar in dit voorbeeld kiezen we de geadresseerde op de hoogte te stellen **met een bericht.**</span><span class="sxs-lookup"><span data-stu-id="e2bd4-117">You have many rule options to choose from, but in this example we'll choose to **Notify the recipient with a message**.</span></span>
1. <span data-ttu-id="e2bd4-118">Voer berichttekst in voor de melding en kies **ok.**</span><span class="sxs-lookup"><span data-stu-id="e2bd4-118">Enter message text for your notification, and then chose **OK**.</span></span>
1. <span data-ttu-id="e2bd4-119">Optioneel: Kies op de  **nieuwe** regelpagina uitzondering toevoegen en voer eventuele details in voor uitzonderingen op de regel, zoals berichten van vertrouwde afzenders.</span><span class="sxs-lookup"><span data-stu-id="e2bd4-119">Optional: On the **new rule** page, choose **add exception**, and enter any details for exceptions to your rule, such as messages from trusted senders.</span></span>
1. <span data-ttu-id="e2bd4-120">Kies Opslaan op de nieuwe regelpagina **en** bekijk de informatie over het overzicht van de regels.</span><span class="sxs-lookup"><span data-stu-id="e2bd4-120">On the new rule page, choose **Save**, and review the rule summary information provided.</span></span>