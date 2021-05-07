---
title: Een voormalige werknemer verwijderen - Overzicht
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
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Volg de stappen in deze oplossing om een voormalige werknemer te verwijderen Microsoft 365 en de gegevens van uw organisatie te beveiligen.
ms.openlocfilehash: 4b4cf59fdce81b3098ee333095daa8e1af1cd5c5
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241734"
---
# <a name="overview-remove-a-former-employee-and-secure-data"></a><span data-ttu-id="dcc00-103">Overzicht: Een voormalige werknemer verwijderen en gegevens beveiligen</span><span class="sxs-lookup"><span data-stu-id="dcc00-103">Overview: Remove a former employee and secure data</span></span>

<span data-ttu-id="dcc00-104">Een veelgestelde vraag is: 'Wat moet ik doen om gegevens te beveiligen en toegang te beveiligen wanneer een werknemer mijn organisatie verlaat?'</span><span class="sxs-lookup"><span data-stu-id="dcc00-104">A question we often get is, "What should I do to secure data and protect access when an employee leaves my organization?"</span></span> <span data-ttu-id="dcc00-105">In deze artikelreeks wordt uitgelegd hoe u toegang tot Microsoft 365 blokkeren, welke stappen u moet ondernemen om uw gegevens te beveiligen en hoe u andere werknemers toegang geeft tot de gegevens.</span><span class="sxs-lookup"><span data-stu-id="dcc00-105">This article series explains how to block access to Microsoft 365, the steps you should take to secure your data, and how to allow other employees to access the data.</span></span>

<span data-ttu-id="dcc00-106">Bekijk een korte video over het verwijderen van een werknemer.</span><span class="sxs-lookup"><span data-stu-id="dcc00-106">Watch a short video about removing an employee.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

<span data-ttu-id="dcc00-107">Als je deze video nuttig vond, raadpleeg dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](../../business-video/index.yml).</span><span class="sxs-lookup"><span data-stu-id="dcc00-107">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

<span data-ttu-id="dcc00-108">Als u wilt voorkomen dat een werknemer zich aanlogt:</span><span class="sxs-lookup"><span data-stu-id="dcc00-108">To prevent an employee from logging in:</span></span>

1. <span data-ttu-id="dcc00-109">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="dcc00-109">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="dcc00-110">Schakel het vakje naast de naam van de gebruiker in en selecteer vervolgens **Wachtwoord opnieuw instellen.**</span><span class="sxs-lookup"><span data-stu-id="dcc00-110">Select the box next to the user's name, and then select **Reset password**.</span></span>
3. <span data-ttu-id="dcc00-111">Voer een nieuw wachtwoord in en selecteer Vervolgens **Opnieuw instellen.**</span><span class="sxs-lookup"><span data-stu-id="dcc00-111">Enter a new password, and then select **Reset**.</span></span> <span data-ttu-id="dcc00-112">(Verzend het niet naar hen.)</span><span class="sxs-lookup"><span data-stu-id="dcc00-112">(Don't send it to them.)</span></span>
4. <span data-ttu-id="dcc00-113">Selecteer de naam van de gebruiker om naar het eigenschappenvenster te gaan en selecteer op het tabblad **Account** de optie **Aanmelding starten.**</span><span class="sxs-lookup"><span data-stu-id="dcc00-113">Select the user's name to go to their properties pane, and on the **Account** tab, select **Initiate sign-out**.</span></span>

> [!NOTE]
> <span data-ttu-id="dcc00-114">U moet een globale beheerder zijn om de aanmelding te starten.</span><span class="sxs-lookup"><span data-stu-id="dcc00-114">You need to be a global administrator to initiate sign-out.</span></span>

<span data-ttu-id="dcc00-115">Binnen een uur - of nadat ze de huidige Microsoft 365 pagina waarin ze zich hebben geplaatst - worden ze gevraagd zich opnieuw aan te melden.</span><span class="sxs-lookup"><span data-stu-id="dcc00-115">Within an hour - or after they leave the current Microsoft 365 page they are on - they're prompted to sign in again.</span></span> <span data-ttu-id="dcc00-116">Een toegangs token is goed voor een uur, dus de tijdlijn is afhankelijk van hoeveel tijd er nog over is op dat token en of ze buiten hun huidige webpagina navigeren.</span><span class="sxs-lookup"><span data-stu-id="dcc00-116">An access token is good for an hour, so the timeline depends on how much time is left on that token, and whether they navigate out of their current webpage.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dcc00-117">Hoewel we de stappen in deze oplossing hebben genummerd en u de oplossing niet hoeft te voltooien met de exacte volgorde, raden we u aan de stappen op deze manier uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="dcc00-117">Although we've numbered the steps in this solution and you don't have to complete the solution using the exact order, we do recommend doing the steps this way.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="dcc00-118">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="dcc00-118">Before you begin</span></span>

<span data-ttu-id="dcc00-119">U moet een globale beheerder zijn om de stappen in deze oplossing uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="dcc00-119">You need to be a global administrator to complete the steps in this solution.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="dcc00-120">**Stap**</span><span class="sxs-lookup"><span data-stu-id="dcc00-120">**Step**</span></span> <br/> |<span data-ttu-id="dcc00-121">**Reden**</span><span class="sxs-lookup"><span data-stu-id="dcc00-121">**Why do this**</span></span> <br/> |
|[<span data-ttu-id="dcc00-122">Stap 1: voorkomen dat een voormalige werknemer zich aanlogt en de toegang tot Microsoft 365 services blokkeert</span><span class="sxs-lookup"><span data-stu-id="dcc00-122">Step 1 - Prevent a former employee from logging in and block access to Microsoft 365 services</span></span>](remove-former-employee-step-1.md) <br/> |<span data-ttu-id="dcc00-123">Hierdoor wordt voorkomen dat uw voormalige werknemer zich inlogt bij Microsoft 365 en voorkomt u dat de persoon toegang heeft tot Microsoft 365 services.</span><span class="sxs-lookup"><span data-stu-id="dcc00-123">This blocks your former employee from logging in to Microsoft 365 and prevents the person from accessing Microsoft 365 services.</span></span> <br/> |
|[<span data-ttu-id="dcc00-124">Stap 2 - De inhoud van het postvak van een voormalige werknemer opslaan</span><span class="sxs-lookup"><span data-stu-id="dcc00-124">Step 2 - Save the contents of a former employee's mailbox</span></span>](remove-former-employee-step-2.md) <br/> |<span data-ttu-id="dcc00-125">Dit is handig voor de persoon die het werk van de werknemer gaat overnemen of als er een geschil is.</span><span class="sxs-lookup"><span data-stu-id="dcc00-125">This is useful for the person who is going to take over the employee's work, or if there is litigation.</span></span> <br/> |
|[<span data-ttu-id="dcc00-126">Stap 3: e-mail van een voormalige werknemer doorsturen naar een andere werknemer of converteren naar een gedeeld postvak</span><span class="sxs-lookup"><span data-stu-id="dcc00-126">Step 3 - Forward a former employee's email to another employee or convert to a shared mailbox</span></span>](remove-former-employee-step-3.md) <br/> |<span data-ttu-id="dcc00-p104">Hiermee kunt u het e-mailadres van een voormalige werknemer actief houden. Als er klanten of partners zijn die hun e-mail nog steeds naar het vorige adres van de werknemer verzenden, komen ze hiermee terecht bij de persoon die het werk overneemt.</span><span class="sxs-lookup"><span data-stu-id="dcc00-p104">This lets you keep the former employee's email address active. If you have customers or partners still sending email to the former employee's address, this gets them to the person taking over the work.</span></span> <br/> |
|[<span data-ttu-id="dcc00-129">Stap 4: een andere werknemer toegang geven tot OneDrive en Outlook gegevens</span><span class="sxs-lookup"><span data-stu-id="dcc00-129">Step 4 - Give another employee access to OneDrive and Outlook data</span></span>](remove-former-employee-step-6.md) <br/> |<span data-ttu-id="dcc00-130">Als u alleen de licentie van een gebruiker verwijdert maar niet het account, blijft de inhoud van de OneDrive van de gebruiker nog maximaal dertig dagen toegankelijk.</span><span class="sxs-lookup"><span data-stu-id="dcc00-130">If you only remove a user's license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.</span></span> <br/><br/> <span data-ttu-id="dcc00-131">Voordat u het account verwijdert, moet u toegang geven tot de OneDrive en Outlook andere gebruiker.</span><span class="sxs-lookup"><span data-stu-id="dcc00-131">Before you delete the account, you should give access of their OneDrive and Outlook to another user.</span></span> <span data-ttu-id="dcc00-132">Nadat u het account van een werknemer hebt verwijderd, blijft de inhoud in OneDrive en Outlook **30 dagen** behouden.</span><span class="sxs-lookup"><span data-stu-id="dcc00-132">After you delete an employee's account, the content in their OneDrive and Outlook is retained for **30** days.</span></span> <span data-ttu-id="dcc00-133">Gedurende die 30 dagen kunt u echter het account van de gebruiker herstellen en toegang krijgen tot de inhoud.</span><span class="sxs-lookup"><span data-stu-id="dcc00-133">During that 30 days, however, you can restore the user's account, and gain access to their content.</span></span> <span data-ttu-id="dcc00-134">Als u het account van de gebruiker herstelt, blijven de OneDrive en Outlook voor u toegankelijk, zelfs na 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="dcc00-134">If you restore the user's account, the OneDrive and Outlook content will remain accessible to you even after 30 days.</span></span> <br/> |
|[<span data-ttu-id="dcc00-135">Stap 5 : het mobiele apparaat van een voormalige werknemer wissen en blokkeren</span><span class="sxs-lookup"><span data-stu-id="dcc00-135">Step 5 - Wipe and block a former employee's mobile device</span></span>](remove-former-employee-step-4.md) <br/> |<span data-ttu-id="dcc00-136">Verwijdert de zakelijke gegevens van de telefoon of tablet.</span><span class="sxs-lookup"><span data-stu-id="dcc00-136">Removes your business data from the phone or tablet.</span></span>  <br/> |
|[<span data-ttu-id="dcc00-137">Stap 6 : de licentie voor het Microsoft 365 verwijderen van een voormalige werknemer</span><span class="sxs-lookup"><span data-stu-id="dcc00-137">Step 6 - Remove and delete the Microsoft 365 license from a former employee</span></span>](remove-former-employee-step-7.md) <br/> |<span data-ttu-id="dcc00-p106">Als u een licentie verwijdert, kunt u deze aan iemand anders toewijzen. U kunt de licentie ook wissen, zodat u er niet voor hoeft te betalen totdat u een andere persoon inhuurt.  </span><span class="sxs-lookup"><span data-stu-id="dcc00-p106">When you remove a license, you can assign it to someone else. Or, you can delete the license so you don't pay for it until you hire another person. </span></span><br/><br/> <span data-ttu-id="dcc00-p107">Als u een licentie verwijdert of wist, worden de oude e-mailberichten, de contactpersonen en de agenda van de gebruiker gedurende **30 dagen** bewaard. Daarna worden ze definitief gewist. Als u de licentie van een gebruiker verwijdert of wist, maar het account niet wist, blijft de inhoud van de OneDrive van de gebruiker nog maximaal dertig dagen toegankelijk.  </span><span class="sxs-lookup"><span data-stu-id="dcc00-p107">When you remove or delete a license, the user's old email, contacts, and calendar are retained for **30 days**, then permanently deleted. If you remove or delete a license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.  </span></span><br/> |
|[<span data-ttu-id="dcc00-142">Stap 7 - Het gebruikersaccount van een voormalige werknemer verwijderen</span><span class="sxs-lookup"><span data-stu-id="dcc00-142">Step 7 - Delete a former employee's user account</span></span>](remove-former-employee-step-7.md) <br/> |<span data-ttu-id="dcc00-143">Hiermee wordt het account verwijderd uit uw beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="dcc00-143">This removes the account from your admin center.</span></span> <span data-ttu-id="dcc00-144">Houdt alles schoon.</span><span class="sxs-lookup"><span data-stu-id="dcc00-144">Keeps things clean.</span></span> <br/> |

## <a name="related-articles"></a><span data-ttu-id="dcc00-145">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="dcc00-145">Related articles</span></span>

[<span data-ttu-id="dcc00-146">Een gebruiker herstellen</span><span class="sxs-lookup"><span data-stu-id="dcc00-146">Restore a user</span></span>](restore-user.md)
