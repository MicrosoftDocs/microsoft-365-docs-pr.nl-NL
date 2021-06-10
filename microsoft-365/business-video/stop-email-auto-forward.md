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
description: Meer informatie over het stoppen van het automatisch doorsturen van e-mailberichten door een e-mailstroomregel te maken om diefstal van bedrijfsgegevens te voorkomen.
ms.openlocfilehash: 82e4c80b0edc501889e0fc4dc28f1ec1ad703568
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706472"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="a69ed-103">E-mail automatisch doorsturen stoppen</span><span class="sxs-lookup"><span data-stu-id="a69ed-103">Stop email auto-forward</span></span>

## <a name="watch-stop-auto-forwarding-emails"></a><span data-ttu-id="a69ed-104">Kijken: Het automatisch doorsturen van e-mailberichten stoppen</span><span class="sxs-lookup"><span data-stu-id="a69ed-104">Watch: Stop auto-forwarding emails</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="a69ed-105">Als een hacker toegang krijgt tot het postvak van een gebruiker, kunnen ze de e-mail van de gebruiker automatisch doorsturen naar een buitenadres en bedrijfseigen gegevens stelen.</span><span class="sxs-lookup"><span data-stu-id="a69ed-105">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="a69ed-106">U kunt dit stoppen door een regel voor de e-mailstroom te maken.</span><span class="sxs-lookup"><span data-stu-id="a69ed-106">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="a69ed-107">Probeer het zelf!</span><span class="sxs-lookup"><span data-stu-id="a69ed-107">Try it!</span></span>

1. <span data-ttu-id="a69ed-108">Selecteer in Microsoft 365 beheercentrum Exchange **,** **e-mailstroom** en  selecteer op het tabblad Regels het plusteken en kies **een nieuwe regel maken.**</span><span class="sxs-lookup"><span data-stu-id="a69ed-108">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="a69ed-109">Selecteer **Meer opties.**</span><span class="sxs-lookup"><span data-stu-id="a69ed-109">Select **More options**.</span></span> <span data-ttu-id="a69ed-110">De nieuwe regel een naam geven.</span><span class="sxs-lookup"><span data-stu-id="a69ed-110">Name your new rule.</span></span>
1. <span data-ttu-id="a69ed-111">Open vervolgens de vervolgkeuzekeuze voor het **toepassen van deze regel als**, selecteer **de** afzender en is vervolgens **extern intern**.</span><span class="sxs-lookup"><span data-stu-id="a69ed-111">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="a69ed-112">Selecteer **Binnen de organisatie** en klik vervolgens op **OK.**</span><span class="sxs-lookup"><span data-stu-id="a69ed-112">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="a69ed-113">Kies **voorwaarde toevoegen,** open de vervolgkeuzekeuze, selecteer **De berichteigenschappen** en voeg **vervolgens het berichttype toe.**</span><span class="sxs-lookup"><span data-stu-id="a69ed-113">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="a69ed-114">Open de **vervolgkeuze** van het type bericht, kies **Automatisch doorsturen** en vervolgens **OK.**</span><span class="sxs-lookup"><span data-stu-id="a69ed-114">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="a69ed-115">Open de **vervolgkeuzeop** Doe het volgende, selecteer **Het bericht blokkeren** en weiger het bericht en voeg een uitleg **toe.**</span><span class="sxs-lookup"><span data-stu-id="a69ed-115">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="a69ed-116">Voer de berichttekst in voor uw uitleg en selecteer **OK.**</span><span class="sxs-lookup"><span data-stu-id="a69ed-116">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="a69ed-117">Schuif naar de onderkant en selecteer **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="a69ed-117">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="a69ed-118">Uw regel is gemaakt en hackers kunnen berichten niet meer automatisch doorsturen.</span><span class="sxs-lookup"><span data-stu-id="a69ed-118">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>

## <a name="related-content"></a><span data-ttu-id="a69ed-119">Verwante inhoud</span><span class="sxs-lookup"><span data-stu-id="a69ed-119">Related content</span></span>

<span data-ttu-id="a69ed-120">[Een ander e-mailalias toevoegen voor een gebruiker](../admin/email/add-another-email-alias-for-a-user.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="a69ed-120">[Add another email alias for a user](../admin/email/add-another-email-alias-for-a-user.md) (article)</span></span>\
<span data-ttu-id="a69ed-121">[Doorsturen van e‑mail configureren in Microsoft 365](../admin/email/configure-email-forwarding.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="a69ed-121">[Configure email forwarding in Microsoft 365](../admin/email/configure-email-forwarding.md) (article)</span></span>\
<span data-ttu-id="a69ed-122">[Problemen met e-mailbezorging](/exchange/troubleshoot/email-delivery/email-delivery-issues) zoeken en oplossen als Office 365 voor zakelijke beheerder (artikel)</span><span class="sxs-lookup"><span data-stu-id="a69ed-122">[Find and fix email delivery issues as an Office 365 for business admin](/exchange/troubleshoot/email-delivery/email-delivery-issues) (article)</span></span>