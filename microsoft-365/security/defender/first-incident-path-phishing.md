---
title: Voorbeeld van een phishing-e-mail aanval
description: Stap door een voorbeeldanalyse van een phishing-aanval.
keywords: incidenten, waarschuwingen, onderzoeken, correlatie, aanval, machines, apparaten, gebruikers, identiteiten, identiteit, postvak, e-mail, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 41a2c73ce5e1c3060d88572f4fa7afe63e193f46
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/10/2021
ms.locfileid: "52299986"
---
# <a name="example-of-a-phishing-email-attack"></a><span data-ttu-id="e80da-104">Voorbeeld van een phishing-e-mail aanval</span><span class="sxs-lookup"><span data-stu-id="e80da-104">Example of a phishing email attack</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e80da-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e80da-105">**Applies to:**</span></span>
- <span data-ttu-id="e80da-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e80da-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e80da-107">Microsoft 365 Defender kan helpen bij het opsporen van schadelijke bijlagen die via e-mail worden bezorgd.</span><span class="sxs-lookup"><span data-stu-id="e80da-107">Microsoft 365 Defender can help detect malicious attachments delivered via email.</span></span> <span data-ttu-id="e80da-108">Aangezien [Office 365 beveiligings-](https://protection.office.com/) en compliancecentrum is geïntegreerd met Microsoft 365 Defender, kunnen beveiligingsanalisten inzicht hebben in bedreigingen die afkomstig zijn van Office 365, bijvoorbeeld via e-mailbijlagen.</span><span class="sxs-lookup"><span data-stu-id="e80da-108">Since the [Office 365 Security and Compliance Center](https://protection.office.com/) integrates with Microsoft 365 Defender, security analysts can have visibility on threats coming in from Office 365, such as through email attachments.</span></span>

<span data-ttu-id="e80da-109">Aan een analist is bijvoorbeeld een incident met meerdere fases toegewezen.</span><span class="sxs-lookup"><span data-stu-id="e80da-109">For example, an analyst was assigned a multi-stage incident.</span></span>
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-incident.png" alt-text="Voorbeeld van een incident met meerdere fases"::: 

<span data-ttu-id="e80da-111">Op het **tabblad Waarschuwingen** van het incident worden waarschuwingen van Defender voor Office 365 en Microsoft Cloud App Security weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e80da-111">In the **Alerts** tab of the incident, alerts from Defender for Office 365 and Microsoft Cloud App Security are displayed.</span></span> <span data-ttu-id="e80da-112">De analist kan inzoomen op de Defender voor Office 365 waarschuwingen door de waarschuwingen voor e-mailberichten te selecteren.</span><span class="sxs-lookup"><span data-stu-id="e80da-112">The analyst can drill down into the Defender for Office 365 alerts by selecting the email messages alerts.</span></span> <span data-ttu-id="e80da-113">De details van de waarschuwing worden weergegeven in het zijvenster.</span><span class="sxs-lookup"><span data-stu-id="e80da-113">The details of the alert are displayed on the side pane.</span></span>

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-alerts.png" alt-text="Voorbeeld van een e-mailwaarschuwing":::
 
<span data-ttu-id="e80da-115">Als u verder omlaag schuift, wordt er meer informatie weergegeven, met de schadelijke bestanden en gebruikers die zijn beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="e80da-115">By scrolling down further, more information is displayed, showing the malicious files and user that was impacted.</span></span>

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-impact.png" alt-text="Voorbeeld van de invloed van een e-mailwaarschuwing op de gebruiker en het bestand":::
  
<span data-ttu-id="e80da-117">Als **u De waarschuwingspagina openen** selecteert, gaat u naar de specifieke waarschuwing, waar u verschillende informatie gedetailleerder kunt bekijken door de koppeling te selecteren.</span><span class="sxs-lookup"><span data-stu-id="e80da-117">Selecting **Open alert page** takes you to the specific alert where various information can be viewed in greater detail by selecting the link.</span></span> <span data-ttu-id="e80da-118">Het werkelijke e-mailbericht kan worden weergegeven door Berichten **weergeven in Explorer** onder aan het deelvenster te selecteren.</span><span class="sxs-lookup"><span data-stu-id="e80da-118">The actual email message can be viewed by selecting **View messages in Explorer** toward the bottom of the panel.</span></span>
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-event-explorer.png" alt-text="Voorbeeld van de details van een waarschuwing"::: 

<span data-ttu-id="e80da-120">Hiermee gaat de analist naar de pagina Bedreigingsbeheer, waar het onderwerp, de geadresseerde, de afzender en andere informatie worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e80da-120">This takes the analyst to the Threat Management page where the email Subject, Recipient, Sender, and other information are displayed.</span></span> <span data-ttu-id="e80da-121">**ZAP** onder **Speciale acties** vertelt de analist dat de functie voor automatisch reinigen van nul uur is geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="e80da-121">**ZAP** under **Special Actions** tells the analyst that the Zero-hour auto purge feature was implemented.</span></span> <span data-ttu-id="e80da-122">ZAP detecteert en verwijdert automatisch schadelijke en spamberichten uit postvakken in de hele organisatie.</span><span class="sxs-lookup"><span data-stu-id="e80da-122">ZAP automatically detects and removes malicious and spam messages from mailboxes across the organization.</span></span> <span data-ttu-id="e80da-123">Zie Voor meer informatie [Zero-hour Auto Purge (ZAP) in Exchange Online.](../office-365-security/zero-hour-auto-purge.md)</span><span class="sxs-lookup"><span data-stu-id="e80da-123">For more information, see [Zero-hour auto purge (ZAP) in Exchange Online](../office-365-security/zero-hour-auto-purge.md).</span></span>

<span data-ttu-id="e80da-124">Andere acties kunnen worden ondernomen op specifieke berichten door Acties **te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="e80da-124">Other actions can be taken on specific messages by selecting **Actions**.</span></span> 
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-actions.png" alt-text="Voorbeeld van de andere acties voor e-mailberichten"::: 

## <a name="next-step"></a><span data-ttu-id="e80da-126">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="e80da-126">Next step</span></span>

<span data-ttu-id="e80da-127">Bekijk het [op identiteit gebaseerde onderzoekspad](first-incident-path-identity.md) voor aanvallen.</span><span class="sxs-lookup"><span data-stu-id="e80da-127">See the [identity-based attack](first-incident-path-identity.md) investigation path.</span></span>

## <a name="see-also"></a><span data-ttu-id="e80da-128">Zie ook</span><span class="sxs-lookup"><span data-stu-id="e80da-128">See also</span></span>

- [<span data-ttu-id="e80da-129">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="e80da-129">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="e80da-130">Incidenten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="e80da-130">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="e80da-131">Incidenten beheren</span><span class="sxs-lookup"><span data-stu-id="e80da-131">Manage incidents</span></span>](manage-incidents.md)
