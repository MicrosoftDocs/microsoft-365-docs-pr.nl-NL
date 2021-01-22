---
title: Automatisch doorsturen van e-mailberichten stoppen
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
description: Lees hoe u het automatisch doorsturen van e-mailberichten kunt stoppen.
ms.openlocfilehash: ebbe37ab5c4a60c6ac4b6ebf8877247199460fa1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925884"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="49031-103">Automatisch doorsturen van e-mail stoppen</span><span class="sxs-lookup"><span data-stu-id="49031-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="49031-104">Als een hacker toegang krijgt tot het postvak van een gebruiker, kan deze de e-mail van de gebruiker automatisch doorsturen naar een buitenadres en bedrijfseigen informatie stelen.</span><span class="sxs-lookup"><span data-stu-id="49031-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="49031-105">U kunt dit stoppen door een regel voor de e-mailstroom te maken.</span><span class="sxs-lookup"><span data-stu-id="49031-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="49031-106">Probeer het zelf!</span><span class="sxs-lookup"><span data-stu-id="49031-106">Try it!</span></span>

1. <span data-ttu-id="49031-107">Selecteer **Exchange,**  de **e-mailstroom** in het Microsoft 365-beheercentrum en selecteer op het tabblad Regels het plusteken en kies een **nieuwe regel maken.**</span><span class="sxs-lookup"><span data-stu-id="49031-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="49031-108">Selecteer **Meer opties.**</span><span class="sxs-lookup"><span data-stu-id="49031-108">Select **More options**.</span></span> <span data-ttu-id="49031-109">De nieuwe regel een naam geven.</span><span class="sxs-lookup"><span data-stu-id="49031-109">Name your new rule.</span></span>
1. <span data-ttu-id="49031-110">Open vervolgens de vervolgkeuzepijt om **deze regel toe te passen** als, selecteer **de** afzender en is vervolgens **extern intern.**</span><span class="sxs-lookup"><span data-stu-id="49031-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="49031-111">Selecteer **Binnen de organisatie en** vervolgens **OK.**</span><span class="sxs-lookup"><span data-stu-id="49031-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="49031-112">Kies **voorwaarde toevoegen,** open de vervolgkeuzekeuze, selecteer **De** berichteigenschappen en voeg vervolgens **het berichttype toe.**</span><span class="sxs-lookup"><span data-stu-id="49031-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="49031-113">Open de **vervolgkeuzekeuzegroep Berichttype** selecteren, kies **Automatisch doorsturen** en vervolgens **OK.**</span><span class="sxs-lookup"><span data-stu-id="49031-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="49031-114">Open de **vervolgkeuzen van Doe** het volgende, selecteer Het bericht **blokkeren,** weiger het bericht en **voeg een uitleg toe.**</span><span class="sxs-lookup"><span data-stu-id="49031-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="49031-115">Voer de berichttekst in voor uw uitleg en selecteer **vervolgens OK.**</span><span class="sxs-lookup"><span data-stu-id="49031-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="49031-116">Schuif naar beneden en selecteer **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="49031-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="49031-117">De regel is aangemaakt en hackers kunnen berichten niet meer automatisch doorsturen.</span><span class="sxs-lookup"><span data-stu-id="49031-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>