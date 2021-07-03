---
title: Afdrukbronnen voorbereiden voor Microsoft Managed Desktop
description: Belangrijke stappen om ervoor te zorgen dat afdrukken soepel verloopt
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 3f77074aa11e9dc82c8fac9763fdebfd2fc49d99
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287207"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a><span data-ttu-id="83910-104">Afdrukbronnen voorbereiden voor Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="83910-104">Prepare printing resources for Microsoft Managed Desktop</span></span>

<span data-ttu-id="83910-105">Als u klaar bent om u aan te melden voor Microsoft Managed Desktop, moet u uw afdrukvereisten evalueren en de juiste aanpak voor uw omgeving bepalen.</span><span class="sxs-lookup"><span data-stu-id="83910-105">As you get ready to enroll in Microsoft Managed Desktop, you should evaluate your printing requirements and determine the right approach for your environment.</span></span> <span data-ttu-id="83910-106">U hebt drie opties:</span><span class="sxs-lookup"><span data-stu-id="83910-106">You have three options:</span></span>

- <span data-ttu-id="83910-107">Implementeer de Microsoft Universal Print-oplossing om het eenvoudig te maken Microsoft Managed Desktop printers te ontdekken.</span><span class="sxs-lookup"><span data-stu-id="83910-107">Deploy the Microsoft Universal Print solution to make it easy for Microsoft Managed Desktop devices to discover printers.</span></span> <span data-ttu-id="83910-108">Zie Wat is universeel afdrukken [voor meer informatie.](/universal-print/fundamentals/universal-print-whatis)</span><span class="sxs-lookup"><span data-stu-id="83910-108">For more information, see [What is Universal Print](/universal-print/fundamentals/universal-print-whatis).</span></span>
- <span data-ttu-id="83910-109">Implementeer printers rechtstreeks met een aangepast PowerShell-script.</span><span class="sxs-lookup"><span data-stu-id="83910-109">Deploy printers directly by using a custom PowerShell script.</span></span> <span data-ttu-id="83910-110">Volg de stappen in [de sectie Lokale printers](#set-up-local-printers) instellen.</span><span class="sxs-lookup"><span data-stu-id="83910-110">Follow the steps in the [Set up local printers](#set-up-local-printers) section.</span></span>
- <span data-ttu-id="83910-111">Gebruik een niet-Microsoft cloudprinter die compatibel is met Windows 10 apparaten die zijn verbonden met een Azure Active Directory domein.</span><span class="sxs-lookup"><span data-stu-id="83910-111">Use a non-Microsoft cloud printing solution that is compatible with Windows 10 devices that are joined to an Azure Active Directory domain.</span></span> <span data-ttu-id="83910-112">De oplossing moet voldoen aan de softwarevereisten voor Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="83910-112">The solution must meet the software requirements for Microsoft Managed Desktop.</span></span> <span data-ttu-id="83910-113">Zie voor meer informatie [Microsoft Managed Desktop app-vereisten.](../service-description/mmd-app-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="83910-113">For more information, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>
 
<span data-ttu-id="83910-114">Als de printerstuurprogramma's niet beschikbaar zijn via Microsoft Update of de Microsoft Store, moet u ze in alle gevallen zelf verkrijgen en ze laten verpakken voor implementatie naar uw Microsoft Managed Desktop-apparaten met Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="83910-114">In all cases, if the printer drivers are not available from Microsoft Update or the Microsoft Store, you'll have to obtain them yourself and have them packaged for deployment to your Microsoft Managed Desktop devices with Microsoft Intune.</span></span> <span data-ttu-id="83910-115">Zie [Intune Standalone - Win32 app management](/mem/intune/apps/apps-win32-app-management) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="83910-115">For more, see [Intune Standalone - Win32 app management](/mem/intune/apps/apps-win32-app-management)</span></span>

## <a name="set-up-local-printers"></a><span data-ttu-id="83910-116">Lokale printers instellen</span><span class="sxs-lookup"><span data-stu-id="83910-116">Set up local printers</span></span>

<span data-ttu-id="83910-117">Als u hebt besloten printers te implementeren met een aangepast PowerShell-script en de afdrukresources hebt voorbereid, volgt u de volgende stappen om gedeelde printers te implementeren:</span><span class="sxs-lookup"><span data-stu-id="83910-117">If you've decided to deploy printers by using a custom PowerShell script and have prepared the printing resources, follow these steps to have shared printers deployed:</span></span>

1. <span data-ttu-id="83910-118">Ga naar de Microsoft Managed Desktop portal.</span><span class="sxs-lookup"><span data-stu-id="83910-118">Navigate to the Microsoft Managed Desktop portal.</span></span>
2. <span data-ttu-id="83910-119">Een aanvraag indienen met de naam *Printerimplementatie* in de **> ondersteuningsaanvragen** van de beheerportal, met de volgende details:</span><span class="sxs-lookup"><span data-stu-id="83910-119">Submit a request labeled *Printer deployment* in the **Support > Support requests** section of the Admin Portal, providing these details:</span></span>
    - <span data-ttu-id="83910-120">Alle UNC-paden naar gedeelde printerlocaties die moeten worden geïmplementeerd voor Microsoft Managed Desktop apparaten</span><span class="sxs-lookup"><span data-stu-id="83910-120">All UNC paths to shared printer locations that will need to be deployed for Microsoft Managed Desktop devices</span></span>
    - <span data-ttu-id="83910-121">Gebruikersgroepen die toegang nodig hebben tot deze gedeelde printers</span><span class="sxs-lookup"><span data-stu-id="83910-121">User groups that require access to these shared printers</span></span>
3. <span data-ttu-id="83910-122">Via de beheerportal laten we u weten wanneer de aanvraag is voltooid.</span><span class="sxs-lookup"><span data-stu-id="83910-122">Using the Admin Portal, we'll let you know when the request has been completed.</span></span> <span data-ttu-id="83910-123">In eerste instantie implementeren we de configuratie alleen op apparaten in de groep Testimplementatie.</span><span class="sxs-lookup"><span data-stu-id="83910-123">Initially we'll only deploy the configuration to devices in the Test deployment group.</span></span>
4. <span data-ttu-id="83910-124">U moet testen en controleren of de configuratie werkt zoals u verwacht.</span><span class="sxs-lookup"><span data-stu-id="83910-124">You must test and confirm whether the configuration works as you expect.</span></span> <span data-ttu-id="83910-125">Reageer via het **tabblad Discussie** in het ondersteuningsverzoek om ons te laten weten wanneer u de test hebt voltooid.</span><span class="sxs-lookup"><span data-stu-id="83910-125">Reply by using the **Discussion** tab in the Support request to let us know when you've completed your testing.</span></span>
5. <span data-ttu-id="83910-126">Vervolgens implementeren we de configuratie naar de andere implementatiegroepen.</span><span class="sxs-lookup"><span data-stu-id="83910-126">We'll then deploy the configuration to the other deployment groups.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="83910-127">Stappen om u klaar te maken</span><span class="sxs-lookup"><span data-stu-id="83910-127">Steps to get ready</span></span>

1. <span data-ttu-id="83910-128">Controleer [Vereisten voor Microsoft Managed Desktop.](prerequisites.md)</span><span class="sxs-lookup"><span data-stu-id="83910-128">Review [Prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="83910-129">Gebruik [gereedheidsbeoordelingshulpmiddelen.](readiness-assessment-tool.md)</span><span class="sxs-lookup"><span data-stu-id="83910-129">Use [Readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. [<span data-ttu-id="83910-130">Vereisten voor gast-accounts</span><span class="sxs-lookup"><span data-stu-id="83910-130">Prerequisites for guest accounts</span></span>](guest-accounts.md)
4. [<span data-ttu-id="83910-131">Netwerkconfiguratie voor Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="83910-131">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="83910-132">Certificaten en netwerkprofielen voorbereiden voor Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="83910-132">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="83910-133">Toegang voorbereiden tot on-premises bronnen voor Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="83910-133">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. [<span data-ttu-id="83910-134">Apps in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="83910-134">Apps in Microsoft Managed Desktop</span></span>](apps.md)
8. [<span data-ttu-id="83910-135">Toegewezen stations voorbereiden voor Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="83910-135">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. <span data-ttu-id="83910-136">[Afdrukbronnen voorbereiden voor Microsoft Managed Desktop](printing.md) (Dit artikel)</span><span class="sxs-lookup"><span data-stu-id="83910-136">[Prepare printing resources for Microsoft Managed Desktop](printing.md) (This article)</span></span>
