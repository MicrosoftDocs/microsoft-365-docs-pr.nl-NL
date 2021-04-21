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
ms.openlocfilehash: f8bd599c7c8bca8d4789188acbcd3574b7473dcb
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903680"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="7e259-103">E-mail automatisch doorsturen stoppen</span><span class="sxs-lookup"><span data-stu-id="7e259-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="7e259-104">Als een hacker toegang krijgt tot het postvak van een gebruiker, kunnen ze de e-mail van de gebruiker automatisch doorsturen naar een buitenadres en bedrijfseigen gegevens stelen.</span><span class="sxs-lookup"><span data-stu-id="7e259-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="7e259-105">U kunt dit stoppen door een regel voor de e-mailstroom te maken.</span><span class="sxs-lookup"><span data-stu-id="7e259-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="7e259-106">Probeer het zelf!</span><span class="sxs-lookup"><span data-stu-id="7e259-106">Try it!</span></span>

1. <span data-ttu-id="7e259-107">Selecteer in het Microsoft 365-beheercentrum **Exchange**,  **e-mailstroom** en selecteer op het tabblad Regels het plusteken en kies **een nieuwe regel maken.**</span><span class="sxs-lookup"><span data-stu-id="7e259-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="7e259-108">Selecteer **Meer opties.**</span><span class="sxs-lookup"><span data-stu-id="7e259-108">Select **More options**.</span></span> <span data-ttu-id="7e259-109">De nieuwe regel een naam geven.</span><span class="sxs-lookup"><span data-stu-id="7e259-109">Name your new rule.</span></span>
1. <span data-ttu-id="7e259-110">Open vervolgens de vervolgkeuzekeuze voor het **toepassen van deze regel als**, selecteer **de** afzender en is vervolgens **extern intern**.</span><span class="sxs-lookup"><span data-stu-id="7e259-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="7e259-111">Selecteer **Binnen de organisatie** en klik vervolgens op **OK.**</span><span class="sxs-lookup"><span data-stu-id="7e259-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="7e259-112">Kies **voorwaarde toevoegen,** open de vervolgkeuzekeuze, selecteer **De berichteigenschappen** en voeg **vervolgens het berichttype toe.**</span><span class="sxs-lookup"><span data-stu-id="7e259-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="7e259-113">Open de **vervolgkeuze** van het type bericht, kies **Automatisch doorsturen** en vervolgens **OK.**</span><span class="sxs-lookup"><span data-stu-id="7e259-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="7e259-114">Open de **vervolgkeuzeop** Doe het volgende, selecteer **Het bericht blokkeren** en weiger het bericht en voeg een uitleg **toe.**</span><span class="sxs-lookup"><span data-stu-id="7e259-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="7e259-115">Voer de berichttekst in voor uw uitleg en selecteer **OK.**</span><span class="sxs-lookup"><span data-stu-id="7e259-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="7e259-116">Schuif naar de onderkant en selecteer **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="7e259-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="7e259-117">Uw regel is gemaakt en hackers kunnen berichten niet meer automatisch doorsturen.</span><span class="sxs-lookup"><span data-stu-id="7e259-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>

## <a name="related-content"></a><span data-ttu-id="7e259-118">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="7e259-118">Related content</span></span>

<span data-ttu-id="7e259-119">[Een andere e-mailalias](https://docs.microsoft.com/microsoft-365/admin/email/add-another-email-alias-for-a-user) voor een gebruiker toevoegen (artikel) E-mail doorsturen [configureren in Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding) (artikel) Problemen met e-mailbezorging zoeken en oplossen als beheerder van [Office 365](https://docs.microsoft.com/exchange/troubleshoot/email-delivery/email-delivery-issues) voor Bedrijven (artikel)</span><span class="sxs-lookup"><span data-stu-id="7e259-119">[Add another email alias for a user](https://docs.microsoft.com/microsoft-365/admin/email/add-another-email-alias-for-a-user) (article) [Configure email forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding) (article) [Find and fix email delivery issues as an Office 365 for business admin](https://docs.microsoft.com/exchange/troubleshoot/email-delivery/email-delivery-issues) (article)</span></span>