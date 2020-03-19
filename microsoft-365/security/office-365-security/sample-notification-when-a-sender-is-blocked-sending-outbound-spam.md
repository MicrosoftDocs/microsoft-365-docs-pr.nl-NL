---
title: Voorbeeldmelding wanneer een afzender wordt geblokkeerd bij het verzenden van uitgaande spam
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/02/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c33fd406-a4c8-4ac8-ad85-123996c5cded
ms.collection:
- M365-security-compliance
description: 'Wanneer een afzender wordt geblokkeerd voor de service vanwege het verzenden van uitgaande spam, ontvangt de domeinbeheerder die is opgegeven wanneer u het uitgaande spambeleid configureert, een meldingse-mail die vergelijkbaar is met de volgende:'
ms.openlocfilehash: 537e97fe952ad9a5b2ca854c44fe6c53b642e3ac
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42811661"
---
# <a name="sample-notification-when-a-sender-is-blocked-sending-outbound-spam"></a><span data-ttu-id="4a05c-103">Voorbeeldmelding wanneer een afzender wordt geblokkeerd bij het verzenden van uitgaande spam</span><span class="sxs-lookup"><span data-stu-id="4a05c-103">Sample notification when a sender is blocked sending outbound spam</span></span>

<span data-ttu-id="4a05c-104">Wanneer een afzender wordt geblokkeerd voor de service vanwege het verzenden van uitgaande spam, ontvangt de domeinbeheerder die is opgegeven wanneer u [het uitgaande spambeleid configureert,](configure-the-outbound-spam-policy.md) een meldingse-mail die vergelijkbaar is met de volgende:</span><span class="sxs-lookup"><span data-stu-id="4a05c-104">When a sender is blocked from the service due to sending outbound spam, the domain admin specified when you [Configure the outbound spam policy](configure-the-outbound-spam-policy.md) will receive a notification email similar to the following:</span></span> 
  
 <span data-ttu-id="4a05c-105">**Afzenderadres:** spamalerts@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4a05c-105">**Sender address:** spamalerts@microsoft.com</span></span> 
  
 <span data-ttu-id="4a05c-106">**Betreft:** Uitgaande spammelding \<- *accountnaam* \> geblokkeerd voor het verzenden van uitgaande e-mail    </span><span class="sxs-lookup"><span data-stu-id="4a05c-106">**Subject:** Outbound spam notification - \<  *account name*  \> blocked from sending outbound mail</span></span> 
  
 <span data-ttu-id="4a05c-107">**Lichaam:** Dit is een geautomatiseerd antwoord van het Exchange Online Protection Spam Analysis System.</span><span class="sxs-lookup"><span data-stu-id="4a05c-107">**Body:** This is an automated reply from the Exchange Online Protection Spam Analysis System.</span></span> 
  
<span data-ttu-id="4a05c-108">Er wordt contact met u opgenomen omdat we grote hoeveelheden e-mail hebben gedetecteerd die zijn gemarkeerd als spam of ander verdacht gedrag afkomstig van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="4a05c-108">You are being contacted because we have detected high volumes of email marked as spam, or other suspicious behavior, originating from your organization.</span></span> <span data-ttu-id="4a05c-109">De volgende e-mailaccounts zijn geblokkeerd voor het verzenden van e-mail (ze kunnen nog steeds e-mail ontvangen):</span><span class="sxs-lookup"><span data-stu-id="4a05c-109">The following email accounts have been blocked from sending email (they can still receive email):</span></span>
  
<span data-ttu-id="4a05c-110">\<*accountnaam*  \></span><span class="sxs-lookup"><span data-stu-id="4a05c-110">\< *account name*  \></span></span> 
  
<span data-ttu-id="4a05c-111">Het is waarschijnlijk dat dit e-mailaccount is gecompromitteerd.</span><span class="sxs-lookup"><span data-stu-id="4a05c-111">It is likely that this email account has been compromised.</span></span> <span data-ttu-id="4a05c-112">Volg de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="4a05c-112">Please follow these steps:</span></span>
  
1. <span data-ttu-id="4a05c-113">Los dit probleem aan uw zijde op door:</span><span class="sxs-lookup"><span data-stu-id="4a05c-113">Resolve this issue on your side by:</span></span>
    
  - <span data-ttu-id="4a05c-114">Het wachtwoord van het account wijzigen.</span><span class="sxs-lookup"><span data-stu-id="4a05c-114">Changing the password of the account.</span></span>
    
  - <span data-ttu-id="4a05c-115">Bepalen hoe de rekening is gecompromitteerd.</span><span class="sxs-lookup"><span data-stu-id="4a05c-115">Determining how the account was compromised.</span></span>
    
  - <span data-ttu-id="4a05c-116">Voorzorgsmaatregelen nemen om ervoor te zorgen dat dit beveiligingslek niet opnieuw wordt misbruikt.</span><span class="sxs-lookup"><span data-stu-id="4a05c-116">Taking precautions to ensure that this vulnerability will not be exploited again.</span></span>
    
  - <span data-ttu-id="4a05c-117">U bevestigt dat uw uitgaande e-mailwachtrij is gewist voor alle beledigende berichten.</span><span class="sxs-lookup"><span data-stu-id="4a05c-117">Confirming that your outbound mail queue has been cleared of all offending messages.</span></span>
    
2. <span data-ttu-id="4a05c-118">Neem contact op met de ondersteuning van Microsoft via uw reguliere contactkanaal.</span><span class="sxs-lookup"><span data-stu-id="4a05c-118">Contact Microsoft support by using your regular contact channel.</span></span>
    
3. <span data-ttu-id="4a05c-119">Leg uit dat u een gebruiker hebt die is geblokkeerd voor het verzenden van e-mail en dat het probleem is opgelost.</span><span class="sxs-lookup"><span data-stu-id="4a05c-119">Explain that you have a user that is blocked from sending mail and that the problem has been dealt with.</span></span>
    
4. <span data-ttu-id="4a05c-120">De agent maakt een ondersteuningsticket met de informatie die u verstrekt en escaleert het om het e-mailadres of domein te hebben gedeblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="4a05c-120">The agent will create a support ticket with the information that you provide and escalate it to have the email address or domain unblocked.</span></span>
    
5. <span data-ttu-id="4a05c-121">Nadat het adres is gedeblokkeerd en in afwachting van geen andere problemen, wordt u gecontacteerd en gewaarschuwd voor de deblokkering.</span><span class="sxs-lookup"><span data-stu-id="4a05c-121">After the address has been unblocked, and pending no other issues, you will be contacted and alerted to the unblocking.</span></span>
    
<span data-ttu-id="4a05c-122">Bedankt voor het helpen van ons bij het beheersen van ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="4a05c-122">Thank you for assisting us in controlling unwanted email.</span></span>
  
<span data-ttu-id="4a05c-123">Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="4a05c-123">Exchange Online Protection.</span></span>
  
<span data-ttu-id="4a05c-124">\*\*OPMERKING - Reageer niet op deze e-mail omdat deze wordt verzonden vanaf een niet-gecontroleerd adres\*\*</span><span class="sxs-lookup"><span data-stu-id="4a05c-124">\*\*NOTE - Please do not respond to this email as it is sent from an unmonitored address\*\*</span></span>
  
> [!TIP]
> <span data-ttu-id="4a05c-125">U ook contact opnemen met ondersteuning via de opties gedocumenteerd bij [Help en ondersteuning voor EOP](help-and-support-for-eop.md).</span><span class="sxs-lookup"><span data-stu-id="4a05c-125">You can also contact support via the options documented at [Help and support for EOP](help-and-support-for-eop.md).</span></span> 
  

