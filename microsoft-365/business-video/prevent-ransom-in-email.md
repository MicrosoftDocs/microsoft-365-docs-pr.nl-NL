---
title: E-mail regels voor Ransomware maken
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
description: Lees hoe u e-mail regels maakt om Ransomware te voorkomen.
ms.openlocfilehash: 85898480438225848fc09db9a9c507045f8a182c
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701675"
---
# <a name="create-email-rules-to-prevent-ransomware"></a><span data-ttu-id="4941b-103">E-mail regels maken om Ransomware te voorkomen</span><span class="sxs-lookup"><span data-stu-id="4941b-103">Create email rules to prevent ransomware</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

<span data-ttu-id="4941b-104">Microsoft 365 helpt uw bedrijf te beschermen tegen Ransomware door potentieel gevaarlijke bestanden, zoals JavaScript, batch en uitvoerbare bestanden, te voorkomen te openen in Outlook.</span><span class="sxs-lookup"><span data-stu-id="4941b-104">Microsoft 365 helps protect your business against ransomware by preventing potentially dangerous files, like JavaScript, batch, and executables, from being opened in Outlook.</span></span> <span data-ttu-id="4941b-105">Ga als volgt te werk om de beveiliging van dit niveau te verhogen door regels toe te voegen die u voor andere typen bestanden blokkeren of waarschuwen.</span><span class="sxs-lookup"><span data-stu-id="4941b-105">To increase this level of protection by adding rules that block or warn you of additional types of files, follow these steps.</span></span>

## <a name="try-it"></a><span data-ttu-id="4941b-106">Probeer het zelf!</span><span class="sxs-lookup"><span data-stu-id="4941b-106">Try it!</span></span>

1. <span data-ttu-id="4941b-107">Kies in het Beheercentrum op [https://admin.microsoft.com](https://admin.microsoft.com) **Exchange** onder **beheer centra**.</span><span class="sxs-lookup"><span data-stu-id="4941b-107">From the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), choose **Exchange** under **Admin centers**.</span></span>
1. <span data-ttu-id="4941b-108">Kies in het menu aan de linkerkant de optie **e-mail stroom**.</span><span class="sxs-lookup"><span data-stu-id="4941b-108">From the menu on the left, choose **mail flow**.</span></span>
1. <span data-ttu-id="4941b-109">Ga naar het tabblad regels, kies de pijl naast het plusteken (+) en kies vervolgens **een nieuwe regel maken**.</span><span class="sxs-lookup"><span data-stu-id="4941b-109">On the rules tab, choose the arrow next to the plus (+) symbol, and then choose **Create a new rule**.</span></span>
1. <span data-ttu-id="4941b-110">Voer op de pagina **nieuwe regel** een naam voor de regel in, schuif naar beneden en kies **meer opties**.</span><span class="sxs-lookup"><span data-stu-id="4941b-110">On the **new rule** page, enter a name for your rule, scroll to the bottom, and then choose **More options**.</span></span>
1. <span data-ttu-id="4941b-111">Selecteer een bijlage onder **deze regel toepassen als** u **een bijlage** selecteert en selecteer vervolgens **bestandsextensie bevat deze woorden**.</span><span class="sxs-lookup"><span data-stu-id="4941b-111">Under **Apply this rule if**, select **Any attachment**, and then select **file extension includes these words**.</span></span>
1. <span data-ttu-id="4941b-112">Voer in het vak onder **woorden of zinnen opgeven** de bestandsextensies in waarop de regel moet worden toegepast, zoals bestandsextensies die macro's kunnen bevatten.</span><span class="sxs-lookup"><span data-stu-id="4941b-112">In the box under **specify words or phrases**, enter the file extensions that you want the rule to be applied to, such as file extensions that can contain macros.</span></span> <span data-ttu-id="4941b-113">Gebruik het plusteken (+) om ze een voor een toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="4941b-113">Use the plus (+) symbol to add them one at a time.</span></span>

    <span data-ttu-id="4941b-114">Meer informatie over bestandstypen vindt u in [beveiliging tegen Ransomware](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware).</span><span class="sxs-lookup"><span data-stu-id="4941b-114">Learn more about file types by reading [Protect against ransomware](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware).</span></span>

1. <span data-ttu-id="4941b-115">Schuif omlaag naar de lijst en kies vervolgens **OK**.</span><span class="sxs-lookup"><span data-stu-id="4941b-115">Scroll down to review your list, and then choose **OK**.</span></span>
1. <span data-ttu-id="4941b-116">Kies op de pagina **nieuwe regel** de optie **voorwaarde toevoegen** en kies vervolgens een voorwaarde onder **Ga als volgt** te werk.</span><span class="sxs-lookup"><span data-stu-id="4941b-116">On the **new rule** page, choose **add condition**, and then choose a condition under **Do the following**.</span></span>
1. <span data-ttu-id="4941b-117">U kunt kiezen uit een groot aantal opties voor de regel, maar in dit voorbeeld zullen we kiezen **de geadresseerde op de hoogte te stellen van een bericht**.</span><span class="sxs-lookup"><span data-stu-id="4941b-117">You have many rule options to choose from, but in this example we'll choose to **Notify the recipient with a message**.</span></span>
1. <span data-ttu-id="4941b-118">Voer de berichttekst voor uw melding in en kies vervolgens **OK**.</span><span class="sxs-lookup"><span data-stu-id="4941b-118">Enter message text for your notification, and then chose **OK**.</span></span>
1. <span data-ttu-id="4941b-119">Optioneel: Kies **uitzondering toevoegen** op de pagina **nieuwe regel** en voer de gegevens voor uitzonderingen voor de regel in, zoals berichten van vertrouwde afzenders.</span><span class="sxs-lookup"><span data-stu-id="4941b-119">Optional: On the **new rule** page, choose **add exception**, and enter any details for exceptions to your rule, such as messages from trusted senders.</span></span>
1. <span data-ttu-id="4941b-120">Kies op de pagina nieuwe regel de optie **Opslaan** en Bekijk de informatie over de regel samenvatting.</span><span class="sxs-lookup"><span data-stu-id="4941b-120">On the new rule page, choose **Save**, and review the rule summary information provided.</span></span>