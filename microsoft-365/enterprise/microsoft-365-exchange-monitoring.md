---
title: Exchange Online-bewaking voor Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/03/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- NOCSH
description: Gebruik Exchange Online-bewaking voor informatie over e-mailincidenten of -adviezen in Microsoft 365.
ms.openlocfilehash: 3d88378449879d451b21ba8bf2a7b5c3032a2c07
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286439"
---
# <a name="exchange-online-monitoring-for-microsoft-365"></a><span data-ttu-id="8f20a-103">Exchange Online-bewaking voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8f20a-103">Exchange Online monitoring for Microsoft 365</span></span>

<span data-ttu-id="8f20a-104">Je kunt Exchange Online-bewaking in het Microsoft 365-beheercentrum gebruiken het controleren van de status van de Exchange Online-service voor het Microsoft 365-abonnement van je organisatie.</span><span class="sxs-lookup"><span data-stu-id="8f20a-104">You can use Exchange Online monitoring in the Microsoft 365 admin center to monitor the health of the Exchange service for your organization’s Microsoft 365 subscription.</span></span> <span data-ttu-id="8f20a-105">Exchange Online-bewaking biedt informatie over incidenten en adviezen die worden verzameld in deze categorieën:</span><span class="sxs-lookup"><span data-stu-id="8f20a-105">Exchange Online monitoring provides you with information about incidents and advisories that are collected in these categories:</span></span>

- <span data-ttu-id="8f20a-106">**Infrastructuur**: Probleem wordt gedetecteerd in de Microsoft 365-infrastructuur die Microsoft bezit voor regelmatige updates en het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="8f20a-106">**Infrastructure**: Issue is detected in the Microsoft 365 infrastructure that Microsoft owns for providing regular updates and resolving the issue.</span></span> <span data-ttu-id="8f20a-107">Gebruikers kunnen bijvoorbeeld geen toegang tot Exchange Online krijgen vanwege problemen met Exchange of andere Microsoft 365-cloudinfrastructuur.</span><span class="sxs-lookup"><span data-stu-id="8f20a-107">For example, users cannot access Exchange Online because of issues with Exchange or other Microsoft 365 cloud infrastructure.</span></span>
- <span data-ttu-id="8f20a-108">**Infrastructuur van derden**: Probleem wordt gedetecteerd in infrastructuur van derden waarvan uw organisatie afhankelijk is en vereist actie van uw organisatie voor een oplossing.</span><span class="sxs-lookup"><span data-stu-id="8f20a-108">**Third-party infrastructure**: Issue is detected in third-party infrastructure on which your organization has taken a dependency and requires action from your organization for resolution.</span></span> <span data-ttu-id="8f20a-109">Gebruikersverificatietransacties worden bijvoorbeeld beperkt door een externe beveiligingstokenservice (STS)-provider die voorkomt dat gebruikers verbinding maken met Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8f20a-109">For example, user authentication transactions are getting throttled by a third-party security token service (STS) provider that prevents users from connecting to Exchange Online.</span></span>
- <span data-ttu-id="8f20a-110">**Infrastructuur van klant**: Probleem wordt gedetecteerd in je organisatie-infrastructuur en vereist actie van je organisatie voor een oplossing.</span><span class="sxs-lookup"><span data-stu-id="8f20a-110">**Customer infrastructure**: Issue is detected in your organization's infrastructure and requires action from your organization for resolution.</span></span> <span data-ttu-id="8f20a-111">Gebruikers kunnen bijvoorbeeld geen toegang tot Exchange Online krijgen omdat ze geen verificatietoken kunnen verkrijgen van de STS-provider die door je organisatie wordt gehost, vanwege een verlopen certificaat.</span><span class="sxs-lookup"><span data-stu-id="8f20a-111">For example, users cannot access Exchange Online because they are unable to obtain an authentication token from STS provider hosted by your organization because of an expired certificate.</span></span>

<span data-ttu-id="8f20a-112">Hier volgt een voorbeeld van de pagina **Servicestatus** in het Microsoft 365-beheercentrum, beschikbaar via **Status > Servicestatus**.</span><span class="sxs-lookup"><span data-stu-id="8f20a-112">Here is an example of the **Service health** page in the Microsoft 365 admin center, available from **Health > Service health**.</span></span>

![De pagina Servicestatus in het Microsoft 365-beheercentrum](../media/microsoft-365-exchange-monitoring/service-health-dashboard-example.png)

<span data-ttu-id="8f20a-114">De waarde van de kolom **Status** geeft aan of de service in orde is of adviezen of incidenten heeft op basis van de cloudservices die Microsoft onderhoudt.</span><span class="sxs-lookup"><span data-stu-id="8f20a-114">The value of the **Status** column indicates whether the service is healthy or has advisories or incidents based on the cloud services that Microsoft maintains.</span></span> 

<span data-ttu-id="8f20a-115">De waarde van de kolom **Problemen van uw organisatie en derden** geeft aan dat de infrastructuur van uw organisatie of de software van derden de servicestatuservaring van uw gebruikers met Exchange Online beïnvloedt.</span><span class="sxs-lookup"><span data-stu-id="8f20a-115">The value of the **Your org and 3rd party issues** column indicates that your organization's infrastructure or third-party software affects your users service health experience with Exchange Online.</span></span> <span data-ttu-id="8f20a-116">Adviezen of incidenten vereisten *uw* acties om te worden opgelost.</span><span class="sxs-lookup"><span data-stu-id="8f20a-116">Advisories or incidents require *your* actions to resolve.</span></span>

<span data-ttu-id="8f20a-117">Hier volgt een voorbeeld van de **Exchange Online**-bewakingspagina in het Microsoft 365-beheercentrum, beschikbaar via **Status > Servicestatus > Exchange Online**.</span><span class="sxs-lookup"><span data-stu-id="8f20a-117">Here is an example of the **Exchange Online** monitoring page in the Microsoft 365 admin center, available from **Health > Service health > Exchange Online**.</span></span>

![De pagina Exchange Online-bewaking in het Microsoft 365-beheercentrum](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example.png)

<span data-ttu-id="8f20a-119">Met de **Exchange Online**-bewakingspagina kan je zien of de Exchange-service in orde is en of er gerelateerde incidenten of adviezen zijn.</span><span class="sxs-lookup"><span data-stu-id="8f20a-119">With the **Exchange Online** monitoring page, you can see whether the Exchange Online service is healthy or not and whether there are any associated incidents or advisories.</span></span> <span data-ttu-id="8f20a-120">Met Exchange Online-bewaking kan je de servicestatus voor specifieke e-mailscenario's bekijken en signalen in bijna realtime bekijken zodat je de impact per scenario kan bepalen.</span><span class="sxs-lookup"><span data-stu-id="8f20a-120">With Exchange Online monitoring, you can look at the service health for specific email scenarios and view near real-time signals to determine the impact by scenario.</span></span> 

## <a name="requirements"></a><span data-ttu-id="8f20a-121">Vereisten</span><span class="sxs-lookup"><span data-stu-id="8f20a-121">Requirements</span></span>

<span data-ttu-id="8f20a-122">Deze preview is ingeschakeld voor klanten die aan deze vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="8f20a-122">This preview is enabled for customers who meet these requirements:</span></span> 

- <span data-ttu-id="8f20a-123">De organisatie heeft een licentie nodig voor ten minste 5000 stuks van een van de volgende producten of een combinatie ervan: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="8f20a-123">Your organization needs to have a license count of at least 5,000, from one or a combination of these products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> 

  <span data-ttu-id="8f20a-124">Uw organisatie heeft bijvoorbeeld 3000 Office 365 E3-licenties en 2500 Microsoft 365 E5-licenties, op een totaal van 5500 licenties van in aanmerking komende producten.</span><span class="sxs-lookup"><span data-stu-id="8f20a-124">For example, your organization can have 3,000 Office 365 E3 licenses and 2,500 Microsoft 365 E5, for a total of 5,500 licenses from the qualifying products.</span></span>

- <span data-ttu-id="8f20a-125">Je organisatie heeft ten minste 50 maandelijks actieve Exchange Online-gebruikers nodig.</span><span class="sxs-lookup"><span data-stu-id="8f20a-125">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

<span data-ttu-id="8f20a-126">Met Exchange-bewaking kan je de status voor de volgende e-mailclients bekijken op basis van de leesactiviteit voor e-mail:</span><span class="sxs-lookup"><span data-stu-id="8f20a-126">With Exchange Online monitoring you can view the health for the following email clients based on email read activity:</span></span>

- <span data-ttu-id="8f20a-127">Outlook Bureaublad</span><span class="sxs-lookup"><span data-stu-id="8f20a-127">Outlook Desktop</span></span>
- <span data-ttu-id="8f20a-128">Webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="8f20a-128">Outlook on the Web</span></span>
- <span data-ttu-id="8f20a-129">Systeemeigen e-mailclients van iOS en Android</span><span class="sxs-lookup"><span data-stu-id="8f20a-129">Native mail clients of iOS and Android</span></span> 
- <span data-ttu-id="8f20a-130">Mobiele Outlook-app in iOS en Android</span><span class="sxs-lookup"><span data-stu-id="8f20a-130">Outlook Mobile app in iOS and Android</span></span> 
- <span data-ttu-id="8f20a-131">Outlook Mac-client</span><span class="sxs-lookup"><span data-stu-id="8f20a-131">Outlook Mac client</span></span>

<span data-ttu-id="8f20a-132">Voor deze clients kunt u het aantal actieve gebruikers in de afgelopen 30 minuten zien op basis van gebruikers die een e-mail lezen, evenals het aantal incidenten en adviezen in het dashboard.</span><span class="sxs-lookup"><span data-stu-id="8f20a-132">For these clients, you can see the number of active users in the last 30 minutes based on users reading an email, along with number of incidents and advisories in the dashboard.</span></span> <span data-ttu-id="8f20a-133">Deze gegevens worden vergeleken met hetzelfde interval van de vorige week om te zien of er een probleem is.</span><span class="sxs-lookup"><span data-stu-id="8f20a-133">This data is compared to the same interval for the previous week to see if there’s an issue.</span></span> 

>[!Note]
> <span data-ttu-id="8f20a-134">Het aantal actieve gebruikers wordt gemeten voor één activiteit, bijvoorbeeld een gebruiker leest een e-mail.</span><span class="sxs-lookup"><span data-stu-id="8f20a-134">Active user count is measured by a single activity, for example, when a user reads an email.</span></span> <span data-ttu-id="8f20a-135">Het geldt alleen voor de afgelopen 30 minuten van activiteit.</span><span class="sxs-lookup"><span data-stu-id="8f20a-135">It only accounts for the last 30 minutes of activity.</span></span>
>

<span data-ttu-id="8f20a-136">Je kunt de Exchange Online-status ook bewaken voor de volgende scenario's:</span><span class="sxs-lookup"><span data-stu-id="8f20a-136">You can also monitor Exchange Online health for the following scenarios:</span></span>

- <span data-ttu-id="8f20a-137">**E-mailstroom**: Het aantal berichten dat zonder vertraging in een postvak is bezorgd nadat het bericht het Microsoft 365-netwerk heeft bereikt.</span><span class="sxs-lookup"><span data-stu-id="8f20a-137">**Mail flow**: The number of messages successfully delivered to a mailbox without any delay after the message reached the Microsoft 365 network.</span></span> 
- <span data-ttu-id="8f20a-138">**Basisverificatie en Moderne verificatie**: Het aantal gebruikers dat is gevalideerd in de Exchange Online-service.</span><span class="sxs-lookup"><span data-stu-id="8f20a-138">**Basic Authentication and Modern Authentication**: The number of users successfully validated in the Exchange Online service.</span></span>

![Een voorbeeld van het bewaken van de Exchange-status voor e-mailbezorging](../media/microsoft-365-exchange-monitoring/exhange-monitoring-scenario-example.png)

<span data-ttu-id="8f20a-140">Voor al deze scenario's zijn de belangrijkste getallen voor de afgelopen 30 minuten in het hoofddashboard.</span><span class="sxs-lookup"><span data-stu-id="8f20a-140">For all these scenarios, the key numbers are for the last 30 minutes in the main dashboard.</span></span> <span data-ttu-id="8f20a-141">Gedetailleerde weergaven voor elk van deze scenario's tonen de trend in bijna realtime voor zeven dagen met aggregatie van 30 minuten vergeleken met de vorige week.</span><span class="sxs-lookup"><span data-stu-id="8f20a-141">Detailed views for each of these scenarios shows the near real-time trend for seven days with the 30-minute aggregate compared with the previous week.</span></span> 

## <a name="send-us-feedback"></a><span data-ttu-id="8f20a-142">Geef ons feedback</span><span class="sxs-lookup"><span data-stu-id="8f20a-142">Send us feedback</span></span>

<span data-ttu-id="8f20a-143">U kunt op twee manieren feedback geven:</span><span class="sxs-lookup"><span data-stu-id="8f20a-143">There are two ways you can provide feedback:</span></span>

- <span data-ttu-id="8f20a-144">Gebruik de optie **Feedback geven** die beschikbaar is op elke pagina van het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="8f20a-144">Use the **Give feedback** option available on every page of the Microsoft 365 admin center.</span></span>
- <span data-ttu-id="8f20a-145">Verzend feedback met behulp van de koppeling **Is deze post nuttig?** voor een specifiek incident of advies.</span><span class="sxs-lookup"><span data-stu-id="8f20a-145">Submit feedback using the **Is this post helpful?** link for a specific incident or advisory.</span></span>

![De koppeling 'Is deze post nuttig?'](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example-incident-feedback.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="8f20a-148">Veelgestelde vragen</span><span class="sxs-lookup"><span data-stu-id="8f20a-148">Frequently asked questions</span></span>

#### <a name="1-why-dont-i-see-exchange-online-monitoring-under-health-in-the-microsoft-365-admin-center"></a><span data-ttu-id="8f20a-149">1. Waarom zie ik 'Exchange Online-bewaking' niet onder Status in het Microsoft 365-beheercentrum?</span><span class="sxs-lookup"><span data-stu-id="8f20a-149">1. Why don’t I see “Exchange Online monitoring” under Health in the Microsoft 365 admin center?</span></span> 

<span data-ttu-id="8f20a-150">Controleer eerst of je het nieuwe beheercentrum hebt ingeschakeld op de **Startpagina** van het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="8f20a-150">First, make sure you’ve enabled the new admin center on the **Home** page of the Microsoft 365 admin center.</span></span> 

<span data-ttu-id="8f20a-151">Controleer vervolgens of je aan beide van de volgende vereisten voldoet:</span><span class="sxs-lookup"><span data-stu-id="8f20a-151">Then make sure you meet both of the following requirements:</span></span> 

- <span data-ttu-id="8f20a-152">De organisatie heeft een licentie nodig voor ten minste 5000 stuks van een van de volgende producten of een combinatie ervan: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="8f20a-152">Your organization needs to have a license count of at least 5,000, from one or a combination of these products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> 
- <span data-ttu-id="8f20a-153">Uw organisatie heeft ten minste vijftig maandelijks actieve Exchange Online-gebruikers nodig.</span><span class="sxs-lookup"><span data-stu-id="8f20a-153">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

<span data-ttu-id="8f20a-154">Als het aantal licenties voor uw organisatie minder dan 5000 gebruikers telt en het aantal maandelijks actieve gebruikers minder dan 50 gebruikers telt, wordt Exchange Online-bewaking pas ingeschakeld zodra aan deze vereisten wordt voldaan.</span><span class="sxs-lookup"><span data-stu-id="8f20a-154">If the license count for your organization goes below 5,000 users and the monthly active users goes below 50 users, Exchange Online monitoring won’t be enabled until these requirements are met.</span></span>

#### <a name="2-the-active-user-count-in-the-dashboard-for-each-client-appears-to-be-low-we-have-a-lot-of-active-licenses-assigned-to-users-what-does-this-mean"></a><span data-ttu-id="8f20a-155">2. Het aantal actieve gebruikers in het dashboard voor elke client lijkt laag te zijn.</span><span class="sxs-lookup"><span data-stu-id="8f20a-155">2. The active user count in the dashboard for each client appears to be low.</span></span> <span data-ttu-id="8f20a-156">We hebben veel actieve licenties aan gebruikers toegewezen.</span><span class="sxs-lookup"><span data-stu-id="8f20a-156">We have a lot of active licenses assigned to users.</span></span> <span data-ttu-id="8f20a-157">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="8f20a-157">What does this mean?</span></span> 

<span data-ttu-id="8f20a-158">Het aantal actieve gebruikers dat in de bewaking wordt weergegeven is gebaseerd op een periode van 30 minuten waarin gebruikers de activiteit hebben uitgevoerd die in de functie is uitgelicht.</span><span class="sxs-lookup"><span data-stu-id="8f20a-158">The active user count shown in monitoring is based on a 30-minute window where users have performed the activity called out in the feature.</span></span> <span data-ttu-id="8f20a-159">Dit mag niet worden verward met het gebruiksaantal.</span><span class="sxs-lookup"><span data-stu-id="8f20a-159">This shouldn’t be confused with usage numbers.</span></span> <span data-ttu-id="8f20a-160">Bekijk het gebruiksaantal door activiteitsrapporten te gebruiken in het Microsoft 365-beheercentrum (**Rapporten > Gebruik**).</span><span class="sxs-lookup"><span data-stu-id="8f20a-160">To view usage numbers, use activity reports in the Microsoft 365 admin center (**Reports > Usage**).</span></span>

#### <a name="3-will-there-be-other-monitoring-scenarios-for-other-services-such-as-teams-and-sharepoint"></a><span data-ttu-id="8f20a-161">3. Zullen er andere bewakingsscenario's zijn voor andere services zoals Teams en SharePoint?</span><span class="sxs-lookup"><span data-stu-id="8f20a-161">3. Will there be other monitoring scenarios for other services such as Teams and SharePoint?</span></span> 

<span data-ttu-id="8f20a-162">Microsoft heeft deze ervaring rechtstreeks geïntegreerd in het dashboard Servicestatus in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="8f20a-162">Microsoft is integrating this experience directly inside the Service Health dashboard in the Microsoft 365 admin center.</span></span> <span data-ttu-id="8f20a-163">Dit zal Microsoft mogelijkheden geven voor het uitbreiden van bewakingsscenario's naar andere services. Dit zal worden aangekondigd wanneer er nieuws over is.</span><span class="sxs-lookup"><span data-stu-id="8f20a-163">This will provide opportunities for Microsoft to extend monitoring scenarios for other services, which will be announced when there is news to share.</span></span> 

#### <a name="4-what-is-the-plan-for-general-availability-of-this-experience"></a><span data-ttu-id="8f20a-164">4. Wat is het plan voor algemene beschikbaarheid van deze ervaring?</span><span class="sxs-lookup"><span data-stu-id="8f20a-164">4. What is the plan for general availability of this experience?</span></span> 

<span data-ttu-id="8f20a-165">Microsoft heeft Exchange Online-bewaking rechtstreeks geïntegreerd in het dashboard **Servicestatus** in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="8f20a-165">Microsoft has integrated Exchange Online monitoring directly on the **Service Health** dashboard in the Microsoft 365 admin center.</span></span> 

<span data-ttu-id="8f20a-166">Met deze nieuwe geïntegreerde ervaring is Microsoft van plan om uw feedback te verzamelen en vervolgens ons plan voor algemene beschikbaarheid te definiëren.</span><span class="sxs-lookup"><span data-stu-id="8f20a-166">With this new integrated experience, Microsoft's plan is to collect your feedback and then define our plan for general availability.</span></span>

#### <a name="5-is-this-a-free-included-or-paid-extra-feature"></a><span data-ttu-id="8f20a-167">5. Is dit een gratis (inbegrepen) of betaalde (extra) functie?</span><span class="sxs-lookup"><span data-stu-id="8f20a-167">5. Is this a free (included) or paid (extra) feature?</span></span> 

<span data-ttu-id="8f20a-168">Deze functie is in openbare preview en alleen beschikbaar voor klanten die voldoen aan de vereisten in vraag 1.</span><span class="sxs-lookup"><span data-stu-id="8f20a-168">This feature is in Public preview and only available for customers that meet the requirements in question 1.</span></span>

<!--
>[!Note]
>INTERNAL: That decision is pending
>
--> 

#### <a name="6-how-do-i-provide-feedback"></a><span data-ttu-id="8f20a-169">6. Hoe kan ik feedback geven?</span><span class="sxs-lookup"><span data-stu-id="8f20a-169">6. How do I provide feedback?</span></span> 

<span data-ttu-id="8f20a-170">Voor algemene feedback gebruik je het pictogram **Feedback geven** in de rechterbenedenhoek van de **Exchange Online**-bewakingspagina.</span><span class="sxs-lookup"><span data-stu-id="8f20a-170">For general feedback, use the **Give feedback** icon on the bottom-right corner of the **Exchange Online** monitoring page.</span></span> 

<span data-ttu-id="8f20a-171">Voor feedback over incidenten of adviezen gebruik je de koppeling **Is deze post nuttig?**.</span><span class="sxs-lookup"><span data-stu-id="8f20a-171">For feedback on incidents or advisories, use the **Is this post helpful?** link.</span></span>

#### <a name="7-where-is-the-data-instrumented-for-the-scenarios-that-show-activity-trends"></a><span data-ttu-id="8f20a-172">7. Waar zijn de gegevens voor de scenario‘s die activiteitentrends weergeven geïnstrumenteerd?</span><span class="sxs-lookup"><span data-stu-id="8f20a-172">7. Where is the data instrumented for the scenarios that show activity trends?</span></span>

<span data-ttu-id="8f20a-p114">De gegevens worden in de Exchange Online-service ondergebracht. Als er een fout optreedt voordat de aanvraag Exchange Online bereikt of als er een fout in Exchange Online optreedt, krijgt u een daling van de activiteit te zien.</span><span class="sxs-lookup"><span data-stu-id="8f20a-p114">The data is instrumented in the Exchange Online service. If there is a failure that happens before the request reaches Exchange Online or there is a failure in Exchange Online, you will see a drop in the activity signal.</span></span>
