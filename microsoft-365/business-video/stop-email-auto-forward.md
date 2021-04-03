---
title: Automatisch doorsturen van e-mailberichten stoppen
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
description: Meer informatie over het stoppen van het automatisch doorsturen van e-mailberichten.
ms.openlocfilehash: b6715cfdf8622521d977e0746cb9a340a8f70a5c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578601"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="2f268-103">E-mail automatisch doorsturen stoppen</span><span class="sxs-lookup"><span data-stu-id="2f268-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="2f268-104">Als een hacker toegang krijgt tot het postvak van een gebruiker, kunnen ze de e-mail van de gebruiker automatisch doorsturen naar een buitenadres en bedrijfseigen gegevens stelen.</span><span class="sxs-lookup"><span data-stu-id="2f268-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="2f268-105">U kunt dit stoppen door een regel voor de e-mailstroom te maken.</span><span class="sxs-lookup"><span data-stu-id="2f268-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="2f268-106">Probeer het zelf!</span><span class="sxs-lookup"><span data-stu-id="2f268-106">Try it!</span></span>

1. <span data-ttu-id="2f268-107">Selecteer in het Microsoft 365-beheercentrum **Exchange**,  **e-mailstroom** en selecteer op het tabblad Regels het plusteken en kies **een nieuwe regel maken.**</span><span class="sxs-lookup"><span data-stu-id="2f268-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="2f268-108">Selecteer **Meer opties.**</span><span class="sxs-lookup"><span data-stu-id="2f268-108">Select **More options**.</span></span> <span data-ttu-id="2f268-109">De nieuwe regel een naam geven.</span><span class="sxs-lookup"><span data-stu-id="2f268-109">Name your new rule.</span></span>
1. <span data-ttu-id="2f268-110">Open vervolgens de vervolgkeuzekeuze voor het **toepassen van deze regel als**, selecteer **de** afzender en is vervolgens **extern intern**.</span><span class="sxs-lookup"><span data-stu-id="2f268-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="2f268-111">Selecteer **Binnen de organisatie** en klik vervolgens op **OK.**</span><span class="sxs-lookup"><span data-stu-id="2f268-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="2f268-112">Kies **voorwaarde toevoegen,** open de vervolgkeuzekeuze, selecteer **De berichteigenschappen** en voeg **vervolgens het berichttype toe.**</span><span class="sxs-lookup"><span data-stu-id="2f268-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="2f268-113">Open de **vervolgkeuze** van het type bericht, kies **Automatisch doorsturen** en vervolgens **OK.**</span><span class="sxs-lookup"><span data-stu-id="2f268-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="2f268-114">Open de **vervolgkeuzeop** Doe het volgende, selecteer **Het bericht blokkeren** en weiger het bericht en voeg een uitleg **toe.**</span><span class="sxs-lookup"><span data-stu-id="2f268-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="2f268-115">Voer de berichttekst in voor uw uitleg en selecteer **OK.**</span><span class="sxs-lookup"><span data-stu-id="2f268-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="2f268-116">Schuif naar de onderkant en selecteer **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="2f268-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="2f268-117">Uw regel is gemaakt en hackers kunnen berichten niet meer automatisch doorsturen.</span><span class="sxs-lookup"><span data-stu-id="2f268-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>