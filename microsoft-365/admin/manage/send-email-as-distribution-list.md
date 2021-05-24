---
title: E-mail verzenden als distributielijst
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
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a7c98273-067e-4162-b3a1-4ba081796012
description: Verzend e-mail als een distributielijst in Microsoft 365 zodat wanneer een lid een bericht beantwoordt, deze afkomstig lijkt te zijn van de distributielijst.
ms.openlocfilehash: eb5ce4a08fae13ee0d2631499a8df1724ef3ef66
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635712"
---
# <a name="send-email-as-a-distribution-list"></a><span data-ttu-id="b4534-103">E-mail verzenden als distributielijst</span><span class="sxs-lookup"><span data-stu-id="b4534-103">Send email as a distribution list</span></span>

<span data-ttu-id="b4534-104">In Microsoft 365 kunt u e-mail verzenden als distributielijst.</span><span class="sxs-lookup"><span data-stu-id="b4534-104">In Microsoft 365, you can send email as a distribution list.</span></span> <span data-ttu-id="b4534-105">Wanneer een persoon die lid is van de distributielijst reageert op een bericht dat is verzonden naar de distributielijst, lijkt het alsof het e-mailbericht afkomstig is van de distributielijst en niet van de afzonderlijke gebruiker.</span><span class="sxs-lookup"><span data-stu-id="b4534-105">When a person who is a member of the distribution list replies to a message sent to the distribution list, the email appears to be from the distribution list, not from the individual user.</span></span> <span data-ttu-id="b4534-106">In dit onderwerp leest u hoe u dit kunt doen.</span><span class="sxs-lookup"><span data-stu-id="b4534-106">This topic shows you how to do this.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="b4534-107">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="b4534-107">Before you begin</span></span>

<span data-ttu-id="b4534-108">Voordat u deze stappen uit te voeren, zorg ervoor dat u bent toegevoegd aan een Microsoft 365 distributielijst en u hebt gekregen Verzenden als machtiging.</span><span class="sxs-lookup"><span data-stu-id="b4534-108">Before you perform these steps, make sure you've been added to a Microsoft 365 distribution list and you've have been granted Send as permission on it.</span></span>
  
 <span data-ttu-id="b4534-109">**Beheerders:** Zorg ervoor dat u de stappen hebt gevolgd in de gebruiker [of contactpersoon](../email/add-user-or-contact-to-distribution-list.md) van een Microsoft 365 toevoegen aan een lijst en Toestaan dat leden e-mail verzenden als een [Microsoft 365 Groepsonderwerpen](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) en de juiste personen aan de distributielijst hebben toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="b4534-109">**Admins**: Make sure you've followed the steps in the [Add a Microsoft 365 user or contact to a list](../email/add-user-or-contact-to-distribution-list.md) and [Allow members to send email as a Microsoft 365 Group](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) topics, and added the correct people to the distribution list.</span></span>
  
## <a name="outlook-on-the-web"></a><span data-ttu-id="b4534-110">Webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="b4534-110">Outlook on the web</span></span>

1. <span data-ttu-id="b4534-111">Open de webversie van Outlook en ga naar uw postvak.</span><span class="sxs-lookup"><span data-stu-id="b4534-111">Open Outlook on the web and go to your inbox.</span></span> 
    
2. <span data-ttu-id="b4534-112">Open een bericht dat naar de distributielijst is verzonden.</span><span class="sxs-lookup"><span data-stu-id="b4534-112">Open a message that was sent to the distribution list.</span></span> 
    
3. <span data-ttu-id="b4534-113">Selecteer **Beantwoorden.**</span><span class="sxs-lookup"><span data-stu-id="b4534-113">Select **Reply**.</span></span> 
    
4. <span data-ttu-id="b4534-114">Selecteer onder aan het bericht **De** optie \> **Meer tonen van**.</span><span class="sxs-lookup"><span data-stu-id="b4534-114">At the bottom of the message, select **More** \> **Show from**.</span></span><br/> <span data-ttu-id="b4534-115">![Selecteer Meer en kies vervolgens Van tonen](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span><span class="sxs-lookup"><span data-stu-id="b4534-115">![Select More and then choose Show From](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span></span>
  
5. <span data-ttu-id="b4534-116">Klik met de rechtermuisknop op het Van-adres , zoals `Ina@weewalter.me` - en kies **Verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="b4534-116">Right-click on the From address - such as `Ina@weewalter.me` - and choose **Remove**.</span></span><br/> <span data-ttu-id="b4534-117">![De FROM-alias verwijderen](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span><span class="sxs-lookup"><span data-stu-id="b4534-117">![Remove the FROM alias](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span></span>
  
6. <span data-ttu-id="b4534-118">Vervolgens typt u het adres van de distributielijst, zoals support@contoso.com, en verstuurt u het bericht.</span><span class="sxs-lookup"><span data-stu-id="b4534-118">Then type the distribution list address such as support@contoso.com, and send the message.</span></span> <span data-ttu-id="b4534-119">De volgende keer dat u vanuit de distributielijst antwoordt, wordt het adres weergegeven als een optie in de **lijst Van.**</span><span class="sxs-lookup"><span data-stu-id="b4534-119">The next time you reply from the distribution list, its address will appear as an option in the **From** list.</span></span><br/><span data-ttu-id="b4534-120">![Alias van het gedeelde postvak wordt weergegeven](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span><span class="sxs-lookup"><span data-stu-id="b4534-120">![Alias of the shared mailbox appears](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span></span>

## <a name="outlook"></a><span data-ttu-id="b4534-121">Outlook</span><span class="sxs-lookup"><span data-stu-id="b4534-121">Outlook</span></span>

1. <span data-ttu-id="b4534-122">Open Outlook bureaubladclient.</span><span class="sxs-lookup"><span data-stu-id="b4534-122">Open Outlook desktop client.</span></span>

2. <span data-ttu-id="b4534-123">Een nieuw e-mailbericht opstellen.</span><span class="sxs-lookup"><span data-stu-id="b4534-123">Compose a New Email.</span></span> <span data-ttu-id="b4534-124">Klik op **het veld Van** en selecteer Ander **e-mailadres.**</span><span class="sxs-lookup"><span data-stu-id="b4534-124">Click the **From** field and select **Other email address**.</span></span> <span data-ttu-id="b4534-125">Als u het veld Van niet ziet, gaat u naar **Opties** en **selecteert** u Van in de sectie Velden tonen.</span><span class="sxs-lookup"><span data-stu-id="b4534-125">If you do not see the From field, navigate to **Options** and select **From** in the Show fields section.</span></span>

3. <span data-ttu-id="b4534-126">Selecteer het **adres van de distributielijst** in de algemene adreslijst.</span><span class="sxs-lookup"><span data-stu-id="b4534-126">Select the **Distribution List** address from the Global Address List.</span></span>

4. <span data-ttu-id="b4534-127">Verzend de e-mail.</span><span class="sxs-lookup"><span data-stu-id="b4534-127">Send the email.</span></span>

## <a name="related-content"></a><span data-ttu-id="b4534-128">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="b4534-128">Related content</span></span>

<span data-ttu-id="b4534-129">[Een beveiligingsgroep maken, bewerken of verwijderen in het Microsoft 365](../email/create-edit-or-delete-a-security-group.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="b4534-129">[Create, edit, or delete a security group in the Microsoft 365 admin center](../email/create-edit-or-delete-a-security-group.md) (article)</span></span>\
<span data-ttu-id="b4534-130">[E-mailsamenwerking](../email/email-collaboration.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="b4534-130">[Email collaboration](../email/email-collaboration.md) (article)</span></span>\
<span data-ttu-id="b4534-131">[Een gebruiker of contactpersoon toevoegen aan een distributiegroep](../email/add-user-or-contact-to-distribution-list.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="b4534-131">[Add a user or contact to a distribution group](../email/add-user-or-contact-to-distribution-list.md) (article)</span></span>