---
title: Windows 10 Pro-apparaatbeleid beheren met Microsoft 365 Business Premium
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
description: Meer informatie over het beheren van beleid voor Windows 10 Pro-apparaat met Microsoft 365 Business Premium.
ms.openlocfilehash: 9052859f03035a76bf69b7c8c23c75ae00353846
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702386"
---
# <a name="manage-windows-10-pro-device-policies"></a><span data-ttu-id="9689e-103">Windows 10 Pro-apparaatbeleid beheren</span><span class="sxs-lookup"><span data-stu-id="9689e-103">Manage Windows 10 Pro device policies</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSL?autoplay=false]

<span data-ttu-id="9689e-104">U kunt Microsoft 365 Business gebruiken om te controleren of Windows Defender antivirus is geactiveerd op Windows 10-apparaten en Microsoft updates automatisch worden gedownload naar de apparaten van gebruikers.</span><span class="sxs-lookup"><span data-stu-id="9689e-104">You can use Microsoft 365 Business to ensure that Windows Defender Antivirus is activated on Windows 10 devices and Microsoft updates are automatically downloaded to users' devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="9689e-105">Probeer het zelf!</span><span class="sxs-lookup"><span data-stu-id="9689e-105">Try it!</span></span>

1. <span data-ttu-id="9689e-106">Meld u aan bij het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="9689e-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="9689e-107">Kies onder **beleid** de optie beleid toevoegen.</span><span class="sxs-lookup"><span data-stu-id="9689e-107">Under **Policies**, choose Add policy.</span></span>
1. <span data-ttu-id="9689e-108">Voer in het deelvenster **beleid toevoegen** een naam in onder **Beleidsnaam** en selecteer vervolgens **Windows 10-apparaatconfiguratie** onder **type beleid**.</span><span class="sxs-lookup"><span data-stu-id="9689e-108">In the **Add policy** pane, enter a name under **Policy name**, and then select **Windows 10 Device Configuration** under **Policy type**.</span></span>
1. <span data-ttu-id="9689e-109">Kies **Windows 10-apparaten beveiligen** om de subinstellingen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="9689e-109">Choose **Secure Windows 10 devices** to see the sub-settings.</span></span>
1. <span data-ttu-id="9689e-110">Zorg ervoor dat u **pc's beschermt tegen virussen en andere bedreigingen met Windows Defender antivirus** en **Windows 10-apparaten automatisch up-to-date wilt houden** .</span><span class="sxs-lookup"><span data-stu-id="9689e-110">Make sure that **Help protect PCs from viruses and other threats using Windows Defender Antivirus** and **Keep Windows 10 devices up to date automatically** are turned on.</span></span>
1. <span data-ttu-id="9689e-111">Onder **wie krijgt deze instellingen?** zijn alle gebruikers standaard geselecteerd, maar u kunt de optie **wijzigen** selecteren om beveiligingsgroepen te selecteren die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="9689e-111">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="9689e-112">Als u het maken van het beleid wilt voltooien, kiest u **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="9689e-112">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="9689e-113">Kies op de pagina **beleid toevoegen** de optie **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="9689e-113">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="9689e-114">Op de startpagina van het Beheercentrum controleert u of het nieuwe beleid is toegevoegd door **beleid** te kiezen en uw beleid te controleren op de pagina **beleid** .</span><span class="sxs-lookup"><span data-stu-id="9689e-114">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>
1. <span data-ttu-id="9689e-115">Als u wilt controleren of het beleid is overgenomen, gaat u naar Windows Update, kiest u **Geavanceerde opties** en controleert u of de instellingen niet beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="9689e-115">To verify that the policy has taken effect, on a user's Windows 10 device, go to Windows Update, choose **Advanced options**, and confirm that settings are grayed out.</span></span>

    <span data-ttu-id="9689e-116">Klik vervolgens op **kiezen hoe updates worden afgeleverd** en controleer of de instellingen niet beschikbaar zijn en of het volgende bericht wordt weergegeven: **bepaalde instellingen zijn verborgen of worden beheerd door uw organisatie**.</span><span class="sxs-lookup"><span data-stu-id="9689e-116">Then, click **Choose how updates are delivered**, and confirm that settings are grayed out and the following message appears: **Some settings are hidden or managed by your organization**.</span></span>

