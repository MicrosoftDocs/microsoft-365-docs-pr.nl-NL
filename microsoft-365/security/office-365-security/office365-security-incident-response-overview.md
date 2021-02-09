---
title: Reactie op beveiligingsincident
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/27/2018
audience: ITPro
ms.topic: overview
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: Deze oplossing vertelt u hoe de meest voorkomende beveiligingsaanvallen er in Microsoft 365 uit kunnen zien en hoe u erop kunt reageren
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8dd7a90255fdd3e083a5d7306cac2e9ca6411024
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150181"
---
# <a name="security-incident-response"></a><span data-ttu-id="4753a-103">Reactie op beveiligingsincident</span><span class="sxs-lookup"><span data-stu-id="4753a-103">Security Incident Response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4753a-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="4753a-104">**Applies to**</span></span>
- [<span data-ttu-id="4753a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4753a-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="4753a-106">Microsoft Defender voor Office 365-abonnement 1 en abonnement 2</span><span class="sxs-lookup"><span data-stu-id="4753a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="4753a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4753a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

 <span data-ttu-id="4753a-108">**Overzicht:** Deze oplossing vertelt u wat de indicatoren zijn voor de meest voorkomende aanvallen in Office 365, hoe u een bepaalde aanval positief bevestigt en hoe u hierop kunt reageren.</span><span class="sxs-lookup"><span data-stu-id="4753a-108">**Summary:** This solution tells you what the indicators are for the most common cybersecurity attacks in Office 365, how to positively confirm any given attack, and how to respond to it.</span></span>

## <a name="learn-how-to-respond-to-cyberattacks"></a><span data-ttu-id="4753a-109">Meer informatie over het reageren op cyberaanvallen</span><span class="sxs-lookup"><span data-stu-id="4753a-109">Learn how to respond to cyberattacks</span></span>

<span data-ttu-id="4753a-110">Niet alle cyberaanvallen kunnen worden gedwarseerd.</span><span class="sxs-lookup"><span data-stu-id="4753a-110">Not all cyberattacks can be thwarted.</span></span> <span data-ttu-id="4753a-111">Aanvallers zijn voortdurend op zoek naar nieuwe zwakke punten in uw strategie of ze maken misbruik van oude.</span><span class="sxs-lookup"><span data-stu-id="4753a-111">Attackers are constantly looking for new weaknesses in your defensive strategy or they are exploiting old ones.</span></span> <span data-ttu-id="4753a-112">Als u weet hoe u een aanval kunt herkennen, kunt u er sneller op reageren, waardoor het beveiligingsincident korter wordt.</span><span class="sxs-lookup"><span data-stu-id="4753a-112">Knowing how to recognize an attack allows you to respond to it faster, which shortens the duration of the security incident.</span></span>

<span data-ttu-id="4753a-113">In deze reeks artikelen wordt beschreven hoe een bepaald type aanval er in Microsoft 365 uit kan zien en vindt u stappen die u kunt ondernemen om te reageren.</span><span class="sxs-lookup"><span data-stu-id="4753a-113">This series of article helps you understand what a particular type of attack might look like in Microsoft 365 and gives you steps you can take to respond.</span></span> <span data-ttu-id="4753a-114">Dit zijn snelle invoerpunten om inzicht te krijgen in:</span><span class="sxs-lookup"><span data-stu-id="4753a-114">They are quick entry points to understanding:</span></span>

- <span data-ttu-id="4753a-115">Wat de aanval is en hoe het werkt.</span><span class="sxs-lookup"><span data-stu-id="4753a-115">What the attack is and how it works.</span></span>

- <span data-ttu-id="4753a-116">Welke borden worden IOC (Indicators of compromise) genoemd) om ernaar te zoeken en hoe u ernaar kunt zoeken.</span><span class="sxs-lookup"><span data-stu-id="4753a-116">What signs, called indicators of compromise (IOC), to look for and how to look for them.</span></span>

- <span data-ttu-id="4753a-117">Hoe kan ik de aanval bevestigen?</span><span class="sxs-lookup"><span data-stu-id="4753a-117">How to positively confirm the attack.</span></span>

- <span data-ttu-id="4753a-118">Stappen om de aanval te voorkomen en uw organisatie in de toekomst beter te beschermen.</span><span class="sxs-lookup"><span data-stu-id="4753a-118">Steps to take to cut off the attack and better protect your organization in the future.</span></span>

- <span data-ttu-id="4753a-119">Koppelingen naar uitgebreide informatie over elk type aanval.</span><span class="sxs-lookup"><span data-stu-id="4753a-119">Links to in-depth information on each attack type.</span></span>

<span data-ttu-id="4753a-120">Kijk hier maandelijks nog eens, omdat er na een tijd meer artikelen worden toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="4753a-120">Check back here monthly as more articles will be added over time.</span></span>

## <a name="detect-and-remediate-articles"></a><span data-ttu-id="4753a-121">Artikelen detecteren en herstellen</span><span class="sxs-lookup"><span data-stu-id="4753a-121">Detect and remediate articles</span></span>

- [<span data-ttu-id="4753a-122">Illegale verlening van toestemming detecteren en verhelpen in Office 365</span><span class="sxs-lookup"><span data-stu-id="4753a-122">Detect and Remediate Illicit Consent Grants in Office 365</span></span>](detect-and-remediate-illicit-consent-grants.md)

- [<span data-ttu-id="4753a-123">Het opsporen en herstellen van Outlook-regels en aangepaste formulieren in Office 365</span><span class="sxs-lookup"><span data-stu-id="4753a-123">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

## <a name="incident-response-articles"></a><span data-ttu-id="4753a-124">Artikelen over reactie op incidenten</span><span class="sxs-lookup"><span data-stu-id="4753a-124">Incident response articles</span></span>

- [<span data-ttu-id="4753a-125">Reageren op een gehackt e-mailaccount in Office 365</span><span class="sxs-lookup"><span data-stu-id="4753a-125">Responding to a Compromised Email Account in Office 365</span></span>](responding-to-a-compromised-email-account.md)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="4753a-126">Microsoft 365 beveiligen als een cybersecurity pro</span><span class="sxs-lookup"><span data-stu-id="4753a-126">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="4753a-127">Uw Microsoft 365-abonnement heeft een krachtige reeks aan beveiligingsmogelijkheden die u kunt gebruiken om uw gegevens en gebruikers te beschermen.</span><span class="sxs-lookup"><span data-stu-id="4753a-127">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="4753a-128">Gebruik de beveiligings-roadmap van Microsoft 365: de belangrijkste prioriteiten voor de eerste [30, 90](security-roadmap.md) dagen en daarna voor het implementeren van aanbevolen aanbevolen procedures van Microsoft voor het beveiligen van uw Microsoft 365-organisatie.</span><span class="sxs-lookup"><span data-stu-id="4753a-128">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 organization.</span></span>

- <span data-ttu-id="4753a-129">Taken die in de eerste 30 dagen moeten worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="4753a-129">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="4753a-130">Deze hebben direct effect en weinig invloed op uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="4753a-130">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="4753a-131">Taken die binnen 90 dagen moeten worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="4753a-131">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="4753a-132">Het duurt wat langer om deze te plannen en te implementeren, maar de beveiligingsrisico's worden enorm verbeterd</span><span class="sxs-lookup"><span data-stu-id="4753a-132">These take a bit more time to plan and implement but greatly improve your security posture</span></span>

- <span data-ttu-id="4753a-133">Na 90 dagen.</span><span class="sxs-lookup"><span data-stu-id="4753a-133">Beyond 90 days.</span></span> <span data-ttu-id="4753a-134">Deze verbeteringen zijn gebaseerd op de eerste 90 dagen.</span><span class="sxs-lookup"><span data-stu-id="4753a-134">These enhancements build in your first 90 days work.</span></span>
