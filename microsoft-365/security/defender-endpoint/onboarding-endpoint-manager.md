---
title: Onboarding met Microsoft Endpoint Manager
description: Meer informatie over het onboarden van Microsoft Defender voor Eindpunt met Microsoft Endpoint Manager
keywords: onboarding, configuratie, implementatie, implementatie, endpoint manager, mdatp, geavanceerde bedreigingsbeveiliging, verzamelingen maken, reactie op eindpuntdetectie, volgende generatie beveiliging, surface reduction van aanvallen, microsoft endpoint manager
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4028fbaedd4e0b89b37a774b79ac5302d899ec3c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056778"
---
# <a name="onboarding-using-microsoft-endpoint-manager"></a><span data-ttu-id="84299-104">Onboarding met Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="84299-104">Onboarding using Microsoft Endpoint Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="84299-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="84299-105">**Applies to:**</span></span>
- [<span data-ttu-id="84299-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="84299-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="84299-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="84299-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="84299-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="84299-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="84299-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="84299-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="84299-110">Dit artikel maakt deel uit van de implementatiehandleiding en fungeert als voorbeeld voor onboarding.</span><span class="sxs-lookup"><span data-stu-id="84299-110">This article is part of the Deployment guide and acts as an example onboarding method.</span></span> 

<span data-ttu-id="84299-111">In het [onderwerp Planning](deployment-strategy.md) zijn verschillende methoden beschikbaar gesteld voor onboard-apparaten voor de service.</span><span class="sxs-lookup"><span data-stu-id="84299-111">In the [Planning](deployment-strategy.md) topic, there were several methods provided to onboard devices to the service.</span></span> <span data-ttu-id="84299-112">Dit onderwerp heeft betrekking op de cloud-native architectuur.</span><span class="sxs-lookup"><span data-stu-id="84299-112">This topic covers the cloud-native architecture.</span></span> 

<span data-ttu-id="84299-113">![Afbeelding van cloud-native architectuur ](images/cloud-native-architecture.png)
 *Diagram van omgevingsarchitectuur*</span><span class="sxs-lookup"><span data-stu-id="84299-113">![Image of cloud-native architecture](images/cloud-native-architecture.png)
*Diagram of environment architectures*</span></span>

<span data-ttu-id="84299-114">Hoewel Defender voor Eindpunt ondersteuning biedt voor onboarding van verschillende eindpunten en hulpprogramma's, worden deze niet in dit artikel beschreven.</span><span class="sxs-lookup"><span data-stu-id="84299-114">While Defender for Endpoint supports onboarding of various endpoints and tools, this article does not cover them.</span></span> <span data-ttu-id="84299-115">Zie Onboarding overview (Overzicht van onboarding) voor informatie over algemene onboarding met behulp van andere ondersteunde implementatiehulpmiddelen en [-methoden.](onboarding.md)</span><span class="sxs-lookup"><span data-stu-id="84299-115">For information on general onboarding using other supported deployment tools and methods, see [Onboarding overview](onboarding.md).</span></span>


<span data-ttu-id="84299-116">[Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview) is een oplossingsplatform waarmee verschillende services worden geseenigd.</span><span class="sxs-lookup"><span data-stu-id="84299-116">[Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview) is a solution platform that unifies several services.</span></span> <span data-ttu-id="84299-117">Het omvat [Microsoft Intune voor](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) apparaatbeheer in de cloud.</span><span class="sxs-lookup"><span data-stu-id="84299-117">It includes [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) for cloud-based device management.</span></span>


<span data-ttu-id="84299-118">In dit onderwerp worden gebruikers begeleid in:</span><span class="sxs-lookup"><span data-stu-id="84299-118">This topic guides users in:</span></span>
- <span data-ttu-id="84299-119">Stap 1: Onboarding devices to the service by creating a group in Microsoft Endpoint Manager (MEM) to assign configurations on</span><span class="sxs-lookup"><span data-stu-id="84299-119">Step 1: Onboarding devices to the service by creating a group in Microsoft Endpoint Manager (MEM) to assign configurations on</span></span>
- <span data-ttu-id="84299-120">Stap 2: Defender configureren voor endpoint-mogelijkheden met Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="84299-120">Step 2: Configuring Defender for Endpoint capabilities using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="84299-121">Met deze onboarding-richtlijnen wordt u begeleid door de volgende basisstappen die u moet nemen bij het gebruik van Microsoft Endpoint Manager:</span><span class="sxs-lookup"><span data-stu-id="84299-121">This onboarding guidance will walk you through the following basic steps that you need to take when using Microsoft Endpoint Manager:</span></span>

-   [<span data-ttu-id="84299-122">Doelapparaten of gebruikers identificeren</span><span class="sxs-lookup"><span data-stu-id="84299-122">Identifying target devices or users</span></span>](#identify-target-devices-or-users)

    -   <span data-ttu-id="84299-123">Een Azure Active Directory-groep maken (gebruiker of apparaat)</span><span class="sxs-lookup"><span data-stu-id="84299-123">Creating an Azure Active Directory group (User or Device)</span></span>

-   [<span data-ttu-id="84299-124">Een configuratieprofiel maken</span><span class="sxs-lookup"><span data-stu-id="84299-124">Creating a Configuration Profile</span></span>](#step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities)

    -   <span data-ttu-id="84299-125">In Microsoft Endpoint Manager begeleiden we u bij het maken van een afzonderlijk beleid voor elke mogelijkheid.</span><span class="sxs-lookup"><span data-stu-id="84299-125">In Microsoft Endpoint Manager, we'll guide you in creating a separate policy for each capability.</span></span>





## <a name="resources"></a><span data-ttu-id="84299-126">Resources</span><span class="sxs-lookup"><span data-stu-id="84299-126">Resources</span></span>


<span data-ttu-id="84299-127">Hier volgen de koppelingen die u nodig hebt voor de rest van het proces:</span><span class="sxs-lookup"><span data-stu-id="84299-127">Here are the links you'll need for the rest of the process:</span></span>

-   [<span data-ttu-id="84299-128">MEM-portal</span><span class="sxs-lookup"><span data-stu-id="84299-128">MEM portal</span></span>](https://aka.ms/memac)

-   [<span data-ttu-id="84299-129">Beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="84299-129">Security Center</span></span>](https://securitycenter.windows.com/)

-   [<span data-ttu-id="84299-130">Basislijnen voor Intune-beveiliging</span><span class="sxs-lookup"><span data-stu-id="84299-130">Intune Security baselines</span></span>](https://docs.microsoft.com/mem/intune/protect/security-baseline-settings-defender-atp#microsoft-defender)

<span data-ttu-id="84299-131">Zie deze bronnen voor meer informatie over Microsoft Endpoint Manager:</span><span class="sxs-lookup"><span data-stu-id="84299-131">For more information about Microsoft Endpoint Manager, check out these resources:</span></span>
- [<span data-ttu-id="84299-132">Microsoft Endpoint Manager-pagina</span><span class="sxs-lookup"><span data-stu-id="84299-132">Microsoft Endpoint Manager page</span></span>](https://docs.microsoft.com/mem/)
- [<span data-ttu-id="84299-133">Blogbericht over convergentie van Intune en ConfigMgr</span><span class="sxs-lookup"><span data-stu-id="84299-133">Blog post on convergence of Intune and ConfigMgr</span></span>](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace/)
- [<span data-ttu-id="84299-134">Inleidingsvideo over MEM</span><span class="sxs-lookup"><span data-stu-id="84299-134">Introduction video on MEM</span></span>](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace)

## <a name="step-1-onboard-devices-by-creating-a-group-in-mem-to-assign-configurations-on"></a><span data-ttu-id="84299-135">Stap 1: Onboard-apparaten door een groep te maken in EENM om configuraties toe te wijzen aan</span><span class="sxs-lookup"><span data-stu-id="84299-135">Step 1: Onboard devices by creating a group in MEM to assign configurations on</span></span>
### <a name="identify-target-devices-or-users"></a><span data-ttu-id="84299-136">Doelapparaten of gebruikers identificeren</span><span class="sxs-lookup"><span data-stu-id="84299-136">Identify target devices or users</span></span>
<span data-ttu-id="84299-137">In deze sectie maken we een testgroep om uw configuraties aan toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="84299-137">In this section, we will create a test group to assign your configurations on.</span></span>

>[!NOTE]
><span data-ttu-id="84299-138">Intune gebruikt Azure Active Directory -groepen (Azure AD) om apparaten en gebruikers te beheren.</span><span class="sxs-lookup"><span data-stu-id="84299-138">Intune uses Azure Active Directory (Azure AD) groups to manage devices and users.</span></span> <span data-ttu-id="84299-139">Als Intune-beheerder kunt u groepen instellen die aan uw organisatiebehoeften voldoen.</span><span class="sxs-lookup"><span data-stu-id="84299-139">As an Intune admin, you can set up groups to suit your organizational needs.</span></span><br>
<span data-ttu-id="84299-140">Zie Groepen toevoegen om [gebruikers en apparaten te ordenen voor meer informatie.](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)</span><span class="sxs-lookup"><span data-stu-id="84299-140">For more information, see [Add groups to organize users and devices](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span></span>

### <a name="create-a-group"></a><span data-ttu-id="84299-141">Een groep maken</span><span class="sxs-lookup"><span data-stu-id="84299-141">Create a group</span></span>

1.  <span data-ttu-id="84299-142">Open de MEM-portal.</span><span class="sxs-lookup"><span data-stu-id="84299-142">Open the MEM portal.</span></span>

2.  <span data-ttu-id="84299-143">Open **Groepen > nieuwe groep.**</span><span class="sxs-lookup"><span data-stu-id="84299-143">Open **Groups > New Group**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-144">![Afbeelding van Microsoft Endpoint Manager-portal1](images/66f724598d9c3319cba27f79dd4617a4.png)</span><span class="sxs-lookup"><span data-stu-id="84299-144">![Image of Microsoft Endpoint Manager portal1](images/66f724598d9c3319cba27f79dd4617a4.png)</span></span>

3.  <span data-ttu-id="84299-145">Voer details in en maak een nieuwe groep.</span><span class="sxs-lookup"><span data-stu-id="84299-145">Enter details and create a new group.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-146">![Afbeelding van Microsoft Endpoint Manager-portal2](images/b1e0206d675ad07db218b63cd9b9abc3.png)</span><span class="sxs-lookup"><span data-stu-id="84299-146">![Image of Microsoft Endpoint Manager portal2](images/b1e0206d675ad07db218b63cd9b9abc3.png)</span></span>

4.  <span data-ttu-id="84299-147">Voeg uw testgebruiker of -apparaat toe.</span><span class="sxs-lookup"><span data-stu-id="84299-147">Add your test user or device.</span></span>

5.  <span data-ttu-id="84299-148">Open de **nieuwe groep in het deelvenster Groepen >** Alle groepen.</span><span class="sxs-lookup"><span data-stu-id="84299-148">From the **Groups > All groups** pane, open your new group.</span></span>

6.  <span data-ttu-id="84299-149">Selecteer **Leden > Leden toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="84299-149">Select  **Members > Add members**.</span></span>

7.  <span data-ttu-id="84299-150">Zoek uw testgebruiker of -apparaat en selecteer deze.</span><span class="sxs-lookup"><span data-stu-id="84299-150">Find your test user or device and select it.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-151">![Afbeelding van Microsoft Endpoint Manager-portal3](images/149cbfdf221cdbde8159d0ab72644cd0.png)</span><span class="sxs-lookup"><span data-stu-id="84299-151">![Image of Microsoft Endpoint Manager portal3](images/149cbfdf221cdbde8159d0ab72644cd0.png)</span></span>

8.  <span data-ttu-id="84299-152">Uw testgroep heeft nu een lid om te testen.</span><span class="sxs-lookup"><span data-stu-id="84299-152">Your testing group now has a member to test.</span></span>

## <a name="step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="84299-153">Stap 2: Configuratiebeleid maken om Microsoft Defender te configureren voor endpoint-mogelijkheden</span><span class="sxs-lookup"><span data-stu-id="84299-153">Step 2: Create configuration policies to configure Microsoft Defender for Endpoint capabilities</span></span>
<span data-ttu-id="84299-154">In de volgende sectie maakt u een aantal configuratiebeleidsregels.</span><span class="sxs-lookup"><span data-stu-id="84299-154">In the following section, you'll create a number of configuration policies.</span></span>

<span data-ttu-id="84299-155">Ten eerste is er een configuratiebeleid om te selecteren welke groepen gebruikers of apparaten worden onboarded bij Defender for Endpoint:</span><span class="sxs-lookup"><span data-stu-id="84299-155">First is a configuration policy to select which groups of users or devices will be onboarded to Defender for Endpoint:</span></span>

- [<span data-ttu-id="84299-156">Eindpuntdetectie en -antwoord</span><span class="sxs-lookup"><span data-stu-id="84299-156">Endpoint detection and response</span></span>](#endpoint-detection-and-response) 

<span data-ttu-id="84299-157">Vervolgens gaat u door met het maken van verschillende typen eindpuntbeveiligingsbeleid:</span><span class="sxs-lookup"><span data-stu-id="84299-157">Then you will continue by creating several different types of endpoint security policies:</span></span>

- [<span data-ttu-id="84299-158">Beveiliging van de volgende generatie</span><span class="sxs-lookup"><span data-stu-id="84299-158">Next-generation protection</span></span>](#next-generation-protection)
- [<span data-ttu-id="84299-159">Surface-beperking voor aanvallen</span><span class="sxs-lookup"><span data-stu-id="84299-159">Attack surface reduction</span></span>](#attack-surface-reduction--attack-surface-reduction-rules)

### <a name="endpoint-detection-and-response"></a><span data-ttu-id="84299-160">Eindpuntdetectie en -antwoord</span><span class="sxs-lookup"><span data-stu-id="84299-160">Endpoint detection and response</span></span>

1.  <span data-ttu-id="84299-161">Open de MEM-portal.</span><span class="sxs-lookup"><span data-stu-id="84299-161">Open the MEM portal.</span></span>

2.  <span data-ttu-id="84299-162">**Navigeer naar endpointbeveiliging > endpointdetectie en -antwoord.**</span><span class="sxs-lookup"><span data-stu-id="84299-162">Navigate to **Endpoint security > Endpoint detection and response**.</span></span> <span data-ttu-id="84299-163">Klik op **Profiel maken.**</span><span class="sxs-lookup"><span data-stu-id="84299-163">Click on **Create Profile**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-164">![Afbeelding van Microsoft Endpoint Manager-portal4](images/58dcd48811147feb4ddc17212b7fe840.png)</span><span class="sxs-lookup"><span data-stu-id="84299-164">![Image of Microsoft Endpoint Manager portal4](images/58dcd48811147feb4ddc17212b7fe840.png)</span></span>

3.  <span data-ttu-id="84299-165">Selecteer **onder Platform de optie Windows 10 en Hoger, Profiel - Eindpuntdetectie en -antwoord > Maken.**</span><span class="sxs-lookup"><span data-stu-id="84299-165">Under **Platform, select Windows 10 and Later, Profile - Endpoint detection and response > Create**.</span></span>

4.  <span data-ttu-id="84299-166">Voer een naam en beschrijving in en selecteer **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="84299-166">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-167">![Afbeelding van Microsoft Endpoint Manager-portal5](images/a5b2d23bdd50b160fef4afd25dda28d4.png)</span><span class="sxs-lookup"><span data-stu-id="84299-167">![Image of Microsoft Endpoint Manager portal5](images/a5b2d23bdd50b160fef4afd25dda28d4.png)</span></span>

5.  <span data-ttu-id="84299-168">Selecteer zo nodig instellingen en selecteer  **vervolgens Volgende**.</span><span class="sxs-lookup"><span data-stu-id="84299-168">Select settings as required, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-169">![Afbeelding van Microsoft Endpoint Manager-portal6](images/cea7e288b5d42a9baf1aef0754ade910.png)</span><span class="sxs-lookup"><span data-stu-id="84299-169">![Image of Microsoft Endpoint Manager portal6](images/cea7e288b5d42a9baf1aef0754ade910.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="84299-170">In dit geval is dit automatisch ingevuld omdat Defender voor Eindpunt al is geïntegreerd met Intune.</span><span class="sxs-lookup"><span data-stu-id="84299-170">In this instance, this has been auto populated as Defender for Endpoint has already been integrated with Intune.</span></span> <span data-ttu-id="84299-171">Zie Microsoft Defender voor eindpunt inschakelen [in Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp)voor meer informatie over de integratie.</span><span class="sxs-lookup"><span data-stu-id="84299-171">For more information on the integration, see [Enable Microsoft Defender for Endpoint in Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp).</span></span>
    > 
    > <span data-ttu-id="84299-172">De volgende afbeelding is een voorbeeld van wat u ziet wanneer Microsoft Defender voor Eindpunt NIET is geïntegreerd met Intune:</span><span class="sxs-lookup"><span data-stu-id="84299-172">The following image is an example of what you'll see when Microsoft Defender for Endpoint is NOT integrated with Intune:</span></span>
    >
    > ![Afbeelding van Microsoft Endpoint Manager-portal7](images/2466460812371ffae2d19a10c347d6f4.png)

6.  <span data-ttu-id="84299-174">Voeg indien nodig bereiklabels toe en selecteer **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="84299-174">Add scope tags if necessary, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-175">![Afbeelding van Microsoft Endpoint Manager-portal8](images/ef844f52ec2c0d737ce793f68b5e8408.png)</span><span class="sxs-lookup"><span data-stu-id="84299-175">![Image of Microsoft Endpoint Manager portal8](images/ef844f52ec2c0d737ce793f68b5e8408.png)</span></span>

7.  <span data-ttu-id="84299-176">Voeg de testgroep toe door op Groepen **selecteren te klikken om uw** groep op te nemen en te kiezen en selecteer vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="84299-176">Add test group by clicking on **Select groups to include** and choose your group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-177">![Afbeelding van Microsoft Endpoint Manager-portal9](images/fc3525e20752da026ec9f46ab4fec64f.png)</span><span class="sxs-lookup"><span data-stu-id="84299-177">![Image of Microsoft Endpoint Manager portal9](images/fc3525e20752da026ec9f46ab4fec64f.png)</span></span>

8.  <span data-ttu-id="84299-178">Controleer en accepteer en selecteer vervolgens **Maken.**</span><span class="sxs-lookup"><span data-stu-id="84299-178">Review and accept, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-179">![Afbeelding van Microsoft Endpoint Manager-portal10](images/289172dbd7bd34d55d24810d9d4d8158.png)</span><span class="sxs-lookup"><span data-stu-id="84299-179">![Image of Microsoft Endpoint Manager portal10](images/289172dbd7bd34d55d24810d9d4d8158.png)</span></span>

9.  <span data-ttu-id="84299-180">U kunt uw voltooide beleid bekijken.</span><span class="sxs-lookup"><span data-stu-id="84299-180">You can view your completed policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-181">![Afbeelding van Microsoft Endpoint Manager-portal11](images/5a568b6878be8243ea2b9d82d41ed297.png)</span><span class="sxs-lookup"><span data-stu-id="84299-181">![Image of Microsoft Endpoint Manager portal11](images/5a568b6878be8243ea2b9d82d41ed297.png)</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="84299-182">Beveiliging van de volgende generatie</span><span class="sxs-lookup"><span data-stu-id="84299-182">Next-generation protection</span></span>

1.  <span data-ttu-id="84299-183">Open de MEM-portal.</span><span class="sxs-lookup"><span data-stu-id="84299-183">Open the MEM portal.</span></span>

2.  <span data-ttu-id="84299-184">Ga naar **Endpoint-beveiligingsprogramma'> Antivirus > Beleid maken.**</span><span class="sxs-lookup"><span data-stu-id="84299-184">Navigate to **Endpoint security > Antivirus > Create Policy**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-185">![Afbeelding van Microsoft Endpoint Manager-portal12](images/6b728d6e0d71108d768e368b416ff8ba.png)</span><span class="sxs-lookup"><span data-stu-id="84299-185">![Image of Microsoft Endpoint Manager portal12](images/6b728d6e0d71108d768e368b416ff8ba.png)</span></span>

3.  <span data-ttu-id="84299-186">Selecteer **Platform - Windows 10 en hoger - Windows en Profiel - Microsoft Defender Antivirus > Create**.</span><span class="sxs-lookup"><span data-stu-id="84299-186">Select **Platform - Windows 10 and Later - Windows and Profile – Microsoft Defender Antivirus > Create**.</span></span>

4.  <span data-ttu-id="84299-187">Voer naam en beschrijving in en selecteer **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="84299-187">Enter name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-188">![Afbeelding van Microsoft Endpoint Manager-portal13](images/a7d738dd4509d65407b7d12beaa3e917.png)</span><span class="sxs-lookup"><span data-stu-id="84299-188">![Image of Microsoft Endpoint Manager portal13](images/a7d738dd4509d65407b7d12beaa3e917.png)</span></span>

5.  <span data-ttu-id="84299-189">Op de **pagina Configuratie-instellingen:** Stel de configuraties in die u nodig hebt voor Microsoft Defender Antivirus (Cloudbeveiliging, Uitsluitingen, Real-Time Beveiliging en Herstel).</span><span class="sxs-lookup"><span data-stu-id="84299-189">In the **Configuration settings page**: Set the configurations you require for Microsoft Defender Antivirus (Cloud Protection, Exclusions, Real-Time Protection, and Remediation).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-190">![Afbeelding van Microsoft Endpoint Manager-portal14](images/3840b1576d6f79a1d72eb14760ef5e8c.png)</span><span class="sxs-lookup"><span data-stu-id="84299-190">![Image of Microsoft Endpoint Manager portal14](images/3840b1576d6f79a1d72eb14760ef5e8c.png)</span></span>

6.  <span data-ttu-id="84299-191">Voeg indien nodig bereiklabels toe en selecteer **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="84299-191">Add scope tags if necessary, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-192">![Afbeelding van Microsoft Endpoint Manager-portal15](images/2055e4f9b9141525c0eb681e7ba19381.png)</span><span class="sxs-lookup"><span data-stu-id="84299-192">![Image of Microsoft Endpoint Manager portal15](images/2055e4f9b9141525c0eb681e7ba19381.png)</span></span>

7.  <span data-ttu-id="84299-193">Selecteer groepen die u wilt opnemen, wijs deze toe aan uw testgroep en  **selecteer** Volgende.</span><span class="sxs-lookup"><span data-stu-id="84299-193">Select groups to include, assign to your test group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-194">![Afbeelding van Microsoft Endpoint Manager-portal16](images/48318a51adee06bff3908e8ad4944dc9.png)</span><span class="sxs-lookup"><span data-stu-id="84299-194">![Image of Microsoft Endpoint Manager portal16](images/48318a51adee06bff3908e8ad4944dc9.png)</span></span>

8.  <span data-ttu-id="84299-195">Controleer en maak en selecteer vervolgens **Maken.**</span><span class="sxs-lookup"><span data-stu-id="84299-195">Review and create, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-196">![Afbeelding van Microsoft Endpoint Manager-portal17](images/dfdadab79112d61bd3693d957084b0ec.png)</span><span class="sxs-lookup"><span data-stu-id="84299-196">![Image of Microsoft Endpoint Manager portal17](images/dfdadab79112d61bd3693d957084b0ec.png)</span></span>

9.  <span data-ttu-id="84299-197">U ziet het configuratiebeleid dat u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="84299-197">You'll see the configuration policy you created.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-198">![Afbeelding van Microsoft Endpoint Manager-portal18](images/38180219e632d6e4ec7bd25a46398da8.png)</span><span class="sxs-lookup"><span data-stu-id="84299-198">![Image of Microsoft Endpoint Manager portal18](images/38180219e632d6e4ec7bd25a46398da8.png)</span></span>

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a><span data-ttu-id="84299-199">Attack Surface Reduction – Attack surface reduction rules</span><span class="sxs-lookup"><span data-stu-id="84299-199">Attack Surface Reduction – Attack surface reduction rules</span></span>

1.  <span data-ttu-id="84299-200">Open de MEM-portal.</span><span class="sxs-lookup"><span data-stu-id="84299-200">Open the MEM portal.</span></span>

2.  <span data-ttu-id="84299-201">**Navigeer naar endpointbeveiliging > Attack surface reduction**.</span><span class="sxs-lookup"><span data-stu-id="84299-201">Navigate to **Endpoint security > Attack surface reduction**.</span></span>

3.  <span data-ttu-id="84299-202">Selecteer **Beleid maken.**</span><span class="sxs-lookup"><span data-stu-id="84299-202">Select  **Create Policy**.</span></span>

4.  <span data-ttu-id="84299-203">Selecteer **Platform - Windows 10 en Hoger - Profiel - Attack surface reduction rules > Create**.</span><span class="sxs-lookup"><span data-stu-id="84299-203">Select **Platform - Windows 10 and Later – Profile - Attack surface reduction rules > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-204">![Afbeelding van Microsoft Endpoint Manager-portal19](images/522d9bb4288dc9c1a957392b51384fdd.png)</span><span class="sxs-lookup"><span data-stu-id="84299-204">![Image of Microsoft Endpoint Manager portal19](images/522d9bb4288dc9c1a957392b51384fdd.png)</span></span>

5.  <span data-ttu-id="84299-205">Voer een naam en beschrijving in en selecteer **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="84299-205">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-206">![Afbeelding van Microsoft Endpoint Manager-portal20](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)</span><span class="sxs-lookup"><span data-stu-id="84299-206">![Image of Microsoft Endpoint Manager portal20](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)</span></span>

6.  <span data-ttu-id="84299-207">Op de **pagina Configuratie-instellingen:** Stel de configuraties in die u nodig hebt voor De surface reduction-regels van Attack en selecteer vervolgens  **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="84299-207">In the **Configuration settings page**: Set the configurations you require for Attack surface reduction rules, then select  **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="84299-208">We configureren alle regels voor het verlagen van de Surface Attack in Audit.</span><span class="sxs-lookup"><span data-stu-id="84299-208">We will be configuring all of the Attack surface reduction rules to Audit.</span></span>
    > 
    > <span data-ttu-id="84299-209">Zie Surface [Reduction Rules attack (Surface Reduction Rules) voor meer informatie.](attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="84299-209">For more information, see [Attack surface reduction rules](attack-surface-reduction.md).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-210">![Afbeelding van Microsoft Endpoint Manager-portal21](images/dd0c00efe615a64a4a368f54257777d0.png)</span><span class="sxs-lookup"><span data-stu-id="84299-210">![Image of Microsoft Endpoint Manager portal21](images/dd0c00efe615a64a4a368f54257777d0.png)</span></span>

7.  <span data-ttu-id="84299-211">Voeg zo nodig bereiklabels toe en selecteer **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="84299-211">Add Scope Tags as required, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-212">![Afbeelding van Microsoft Endpoint Manager-portal22](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span><span class="sxs-lookup"><span data-stu-id="84299-212">![Image of Microsoft Endpoint Manager portal22](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span></span>

8.  <span data-ttu-id="84299-213">Selecteer groepen die u wilt opnemen en toewijzen aan de testgroep en selecteer vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="84299-213">Select groups to include and assign to test group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-214">![Afbeelding van Microsoft Endpoint Manager-portal23](images/45cefc8e4e474321b4d47b4626346597.png)</span><span class="sxs-lookup"><span data-stu-id="84299-214">![Image of Microsoft Endpoint Manager portal23](images/45cefc8e4e474321b4d47b4626346597.png)</span></span>

9. <span data-ttu-id="84299-215">Bekijk de details en selecteer vervolgens **Maken.**</span><span class="sxs-lookup"><span data-stu-id="84299-215">Review the details, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-216">![Afbeelding van Microsoft Endpoint Manager-portal24](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)</span><span class="sxs-lookup"><span data-stu-id="84299-216">![Image of Microsoft Endpoint Manager portal24](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)</span></span>

10. <span data-ttu-id="84299-217">Bekijk het beleid.</span><span class="sxs-lookup"><span data-stu-id="84299-217">View the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-218">![Afbeelding van Microsoft Endpoint Manager-portal25](images/7a631d17cc42500dacad4e995823ffef.png)</span><span class="sxs-lookup"><span data-stu-id="84299-218">![Image of Microsoft Endpoint Manager portal25](images/7a631d17cc42500dacad4e995823ffef.png)</span></span>

### <a name="attack-surface-reduction--web-protection"></a><span data-ttu-id="84299-219">Attack Surface Reduction – Web Protection</span><span class="sxs-lookup"><span data-stu-id="84299-219">Attack Surface Reduction – Web Protection</span></span>

1.  <span data-ttu-id="84299-220">Open de MEM-portal.</span><span class="sxs-lookup"><span data-stu-id="84299-220">Open the MEM portal.</span></span>

2.  <span data-ttu-id="84299-221">**Navigeer naar endpointbeveiliging > Attack surface reduction**.</span><span class="sxs-lookup"><span data-stu-id="84299-221">Navigate to **Endpoint security > Attack surface reduction**.</span></span>

3.  <span data-ttu-id="84299-222">Selecteer **Beleid maken.**</span><span class="sxs-lookup"><span data-stu-id="84299-222">Select  **Create Policy**.</span></span>

4.  <span data-ttu-id="84299-223">Selecteer **Windows 10 en Hoger : webbeveiliging > Maken.**</span><span class="sxs-lookup"><span data-stu-id="84299-223">Select **Windows 10 and Later – Web protection > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-224">![Afbeelding van Microsoft Endpoint Manager-portal26](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)</span><span class="sxs-lookup"><span data-stu-id="84299-224">![Image of Microsoft Endpoint Manager portal26](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)</span></span>

5.  <span data-ttu-id="84299-225">Voer een naam en beschrijving in en selecteer **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="84299-225">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-226">![Afbeelding van Microsoft Endpoint Manager-portal27](images/5be573a60cd4fa56a86a6668b62dd808.png)</span><span class="sxs-lookup"><span data-stu-id="84299-226">![Image of Microsoft Endpoint Manager portal27](images/5be573a60cd4fa56a86a6668b62dd808.png)</span></span>

6.  <span data-ttu-id="84299-227">Op de **pagina Configuratie-instellingen:** Stel de configuraties in die u nodig hebt voor webbeveiliging en selecteer vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="84299-227">In the **Configuration settings page**: Set the configurations you require for Web Protection, then select  **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="84299-228">We configureren Webbeveiliging op Blokkeren.</span><span class="sxs-lookup"><span data-stu-id="84299-228">We are configuring Web Protection to Block.</span></span>
    > 
    > <span data-ttu-id="84299-229">Zie Webbeveiliging voor [meer informatie.](web-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="84299-229">For more information, see [Web Protection](web-protection-overview.md).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-230">![Afbeelding van Microsoft Endpoint Manager-portal28](images/6104aa33a56fab750cf30ecabef9f5b6.png)</span><span class="sxs-lookup"><span data-stu-id="84299-230">![Image of Microsoft Endpoint Manager portal28](images/6104aa33a56fab750cf30ecabef9f5b6.png)</span></span>

7.  <span data-ttu-id="84299-231">Voeg **zo nodig bereiklabels > Volgende.**</span><span class="sxs-lookup"><span data-stu-id="84299-231">Add **Scope Tags as required > Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-232">![Afbeelding van Microsoft Endpoint Manager-portal29](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span><span class="sxs-lookup"><span data-stu-id="84299-232">![Image of Microsoft Endpoint Manager portal29](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span></span>

8.  <span data-ttu-id="84299-233">Selecteer **Toewijzen aan testgroep > Volgende**.</span><span class="sxs-lookup"><span data-stu-id="84299-233">Select **Assign to test group > Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-234">![Afbeelding van Microsoft Endpoint Manager-portal30](images/45cefc8e4e474321b4d47b4626346597.png)</span><span class="sxs-lookup"><span data-stu-id="84299-234">![Image of Microsoft Endpoint Manager portal30](images/45cefc8e4e474321b4d47b4626346597.png)</span></span>

9.  <span data-ttu-id="84299-235">Selecteer **Controleren en maken > Maken.**</span><span class="sxs-lookup"><span data-stu-id="84299-235">Select **Review and Create > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-236">![Afbeelding van Microsoft Endpoint Manager-portal31](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)</span><span class="sxs-lookup"><span data-stu-id="84299-236">![Image of Microsoft Endpoint Manager portal31](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)</span></span>

10. <span data-ttu-id="84299-237">Bekijk het beleid.</span><span class="sxs-lookup"><span data-stu-id="84299-237">View the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-238">![Afbeelding van Microsoft Endpoint Manager-portal32](images/e74f6f6c150d017a286e6ed3dffb7757.png)</span><span class="sxs-lookup"><span data-stu-id="84299-238">![Image of Microsoft Endpoint Manager portal32](images/e74f6f6c150d017a286e6ed3dffb7757.png)</span></span>

## <a name="validate-configuration-settings"></a><span data-ttu-id="84299-239">Configuratie-instellingen valideren</span><span class="sxs-lookup"><span data-stu-id="84299-239">Validate configuration settings</span></span>


### <a name="confirm-policies-have-been-applied"></a><span data-ttu-id="84299-240">Beleid bevestigen is toegepast</span><span class="sxs-lookup"><span data-stu-id="84299-240">Confirm Policies have been applied</span></span>


<span data-ttu-id="84299-241">Nadat het configuratiebeleid is toegewezen, duurt het enige tijd om toe te passen.</span><span class="sxs-lookup"><span data-stu-id="84299-241">Once the Configuration policy has been assigned, it will take some time to apply.</span></span>

<span data-ttu-id="84299-242">Zie Intune-configuratiegegevens voor [informatie over tijdsinstellingen.](https://docs.microsoft.com/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned)</span><span class="sxs-lookup"><span data-stu-id="84299-242">For information on timing, see [Intune configuration information](https://docs.microsoft.com/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).</span></span>

<span data-ttu-id="84299-243">Als u wilt bevestigen dat het configuratiebeleid is toegepast op uw testapparaat, volgt u het volgende proces voor elk configuratiebeleid.</span><span class="sxs-lookup"><span data-stu-id="84299-243">To confirm that the configuration policy has been applied to your test device, follow the following process for each configuration policy.</span></span>

1.  <span data-ttu-id="84299-244">Open de MEM-portal en ga naar het relevante beleid, zoals wordt weergegeven in de bovenstaande stappen.</span><span class="sxs-lookup"><span data-stu-id="84299-244">Open the MEM portal and navigate to the relevant policy as shown in the steps above.</span></span> <span data-ttu-id="84299-245">In het volgende voorbeeld ziet u de volgende generatie beveiligingsinstellingen.</span><span class="sxs-lookup"><span data-stu-id="84299-245">The following example shows the next generation protection settings.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-246">[![Afbeelding van Microsoft Endpoint Manager-portal33 ](images/43ab6aa74471ee2977e154a4a5ef2d39.png)](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="84299-246">[ ![Image of Microsoft Endpoint Manager portal33](images/43ab6aa74471ee2977e154a4a5ef2d39.png) ](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)</span></span>

2.  <span data-ttu-id="84299-247">Selecteer het **configuratiebeleid om** de beleidsstatus weer te geven.</span><span class="sxs-lookup"><span data-stu-id="84299-247">Select  the **Configuration Policy** to view the policy status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-248">[![Afbeelding van Microsoft Endpoint Manager-portal34 ](images/55ecaca0e4a022f0e29d45aeed724e6c.png)](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="84299-248">[ ![Image of Microsoft Endpoint Manager portal34](images/55ecaca0e4a022f0e29d45aeed724e6c.png) ](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)</span></span>

3.  <span data-ttu-id="84299-249">Selecteer  **Apparaatstatus om** de status te zien.</span><span class="sxs-lookup"><span data-stu-id="84299-249">Select  **Device Status** to see the status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-250">[![Afbeelding van Microsoft Endpoint Manager-portal35 ](images/18a50df62cc38749000dbfb48e9a4c9b.png)](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="84299-250">[ ![Image of Microsoft Endpoint Manager portal35](images/18a50df62cc38749000dbfb48e9a4c9b.png) ](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)</span></span>

4.  <span data-ttu-id="84299-251">Selecteer  **Gebruikersstatus om** de status te zien.</span><span class="sxs-lookup"><span data-stu-id="84299-251">Select  **User Status** to see the status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-252">[![Afbeelding van Microsoft Endpoint Manager-portal36 ](images/4e965749ff71178af8873bc91f9fe525.png)](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="84299-252">[ ![Image of Microsoft Endpoint Manager portal36](images/4e965749ff71178af8873bc91f9fe525.png) ](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)</span></span>

5.  <span data-ttu-id="84299-253">Selecteer  **Status per instelling om** de status te zien.</span><span class="sxs-lookup"><span data-stu-id="84299-253">Select  **Per-setting status** to see the status.</span></span>

    >[!TIP]
    ><span data-ttu-id="84299-254">Deze weergave is zeer handig om instellingen te identificeren die conflicteren met een ander beleid.</span><span class="sxs-lookup"><span data-stu-id="84299-254">This view is very useful to identify any settings that conflict with another policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-255">[![Afbeelding van Microsoft Endpoint Manager-portal37 ](images/42acc69d0128ed09804010bdbdf0a43c.png)](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="84299-255">[ ![Image of Microsoft Endpoint Manager portal37](images/42acc69d0128ed09804010bdbdf0a43c.png) ](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)</span></span>

### <a name="endpoint-detection-and-response"></a><span data-ttu-id="84299-256">Eindpuntdetectie en -antwoord</span><span class="sxs-lookup"><span data-stu-id="84299-256">Endpoint detection and response</span></span>


1.  <span data-ttu-id="84299-257">Voordat u de configuratie gaat toepassen, moet de Defender voor Endpoint Protection-service niet worden gestart.</span><span class="sxs-lookup"><span data-stu-id="84299-257">Before applying the configuration, the Defender for Endpoint Protection service should not be started.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-258">[![Afbeelding van het deelvenster Services1 ](images/b418a232a12b3d0a65fc98248dbb0e31.png)](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="84299-258">[ ![Image of Services panel1](images/b418a232a12b3d0a65fc98248dbb0e31.png) ](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)</span></span>

2.  <span data-ttu-id="84299-259">Nadat de configuratie is toegepast, moet de Defender for Endpoint Protection Service worden gestart.</span><span class="sxs-lookup"><span data-stu-id="84299-259">After the configuration has been applied, the Defender for Endpoint Protection Service should be started.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-260">[![Afbeelding van het deelvenster Services2 ](images/a621b699899f1b41db211170074ea59e.png)](images/a621b699899f1b41db211170074ea59e.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="84299-260">[ ![Image of Services panel2](images/a621b699899f1b41db211170074ea59e.png) ](images/a621b699899f1b41db211170074ea59e.png#lightbox)</span></span>

3.  <span data-ttu-id="84299-261">Nadat de services op het apparaat zijn uitgevoerd, wordt het apparaat weergegeven in het Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="84299-261">After the services are running on the device, the device appears in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-262">[![Afbeelding van Microsoft Defender-beveiligingscentrum ](images/df0c64001b9219cfbd10f8f81a273190.png)](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="84299-262">[ ![Image of Microsoft Defender Security Center](images/df0c64001b9219cfbd10f8f81a273190.png) ](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="84299-263">Beveiliging van de volgende generatie</span><span class="sxs-lookup"><span data-stu-id="84299-263">Next-generation protection</span></span>

1.  <span data-ttu-id="84299-264">Voordat u het beleid op een testapparaat kunt toepassen, moet u de instellingen handmatig kunnen beheren, zoals hieronder wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="84299-264">Before applying the policy on a test device, you should be able to manually manage the settings as shown below.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-265">![Afbeelding van instellingspagina1](images/88efb4c3710493a53f2840c3eac3e3d3.png)</span><span class="sxs-lookup"><span data-stu-id="84299-265">![Image of setting page1](images/88efb4c3710493a53f2840c3eac3e3d3.png)</span></span>

2.  <span data-ttu-id="84299-266">Nadat het beleid is toegepast, kunt u de instellingen niet handmatig beheren.</span><span class="sxs-lookup"><span data-stu-id="84299-266">After the policy has been applied, you should not be able to manually manage the settings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="84299-267">In de volgende afbeelding wordt Beveiliging  in de **cloud in-** en in-/uit-/in-/uit-beveiliging weergegeven als beheerd.</span><span class="sxs-lookup"><span data-stu-id="84299-267">In the following image **Turn on cloud-delivered protection** and **Turn on real-time protection** are being shown as managed.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84299-268">![Afbeelding van instellingspagina2](images/9341428b2d3164ca63d7d4eaa5cff642.png)</span><span class="sxs-lookup"><span data-stu-id="84299-268">![Image of setting page2](images/9341428b2d3164ca63d7d4eaa5cff642.png)</span></span>

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a><span data-ttu-id="84299-269">Attack Surface Reduction – Attack surface reduction rules</span><span class="sxs-lookup"><span data-stu-id="84299-269">Attack Surface Reduction – Attack surface reduction rules</span></span>


1.  <span data-ttu-id="84299-270">Voordat u het beleid op een testapparaat gaat toepassen, pent u een PowerShell-venster en typt `Get-MpPreference` u .</span><span class="sxs-lookup"><span data-stu-id="84299-270">Before applying the policy on a test device, pen a PowerShell Window and type `Get-MpPreference`.</span></span>

2.  <span data-ttu-id="84299-271">Dit moet reageren met de volgende regels zonder inhoud:</span><span class="sxs-lookup"><span data-stu-id="84299-271">This should respond with the following lines with no content:</span></span>

    > <span data-ttu-id="84299-272">AttackSurfaceReductionOnlyExclusions:</span><span class="sxs-lookup"><span data-stu-id="84299-272">AttackSurfaceReductionOnlyExclusions:</span></span>
    > 
    > <span data-ttu-id="84299-273">AttackSurfaceReductionRules_Actions:</span><span class="sxs-lookup"><span data-stu-id="84299-273">AttackSurfaceReductionRules_Actions:</span></span>
    > 
    > <span data-ttu-id="84299-274">AttackSurfaceReductionRules_Ids:</span><span class="sxs-lookup"><span data-stu-id="84299-274">AttackSurfaceReductionRules_Ids:</span></span>

    ![Afbeelding van opdrachtregel1](images/cb0260d4b2636814e37eee427211fe71.png)

3.  <span data-ttu-id="84299-276">Nadat u het beleid op een testapparaat hebt toegepast, opent u een PowerShell Windows en typt `Get-MpPreference` u .</span><span class="sxs-lookup"><span data-stu-id="84299-276">After applying the policy on a test device, open a PowerShell Windows and type `Get-MpPreference`.</span></span>

4.  <span data-ttu-id="84299-277">Dit moet reageren met de volgende regels met inhoud zoals hieronder wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="84299-277">This should respond with the following lines with content as shown below:</span></span>

    ![Afbeelding van opdrachtregel2](images/619fb877791b1fc8bc7dfae1a579043d.png)

### <a name="attack-surface-reduction--web-protection"></a><span data-ttu-id="84299-279">Attack Surface Reduction – Web Protection</span><span class="sxs-lookup"><span data-stu-id="84299-279">Attack Surface Reduction – Web Protection</span></span>

1.  <span data-ttu-id="84299-280">Open op het testapparaat een PowerShell Windows en typ `(Get-MpPreference).EnableNetworkProtection` .</span><span class="sxs-lookup"><span data-stu-id="84299-280">On the test device, open a PowerShell Windows and type `(Get-MpPreference).EnableNetworkProtection`.</span></span>

2.  <span data-ttu-id="84299-281">Dit moet reageren met een 0 zoals hieronder wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="84299-281">This should respond with a 0 as shown below.</span></span>

    ![Afbeelding van opdrachtregel3](images/196a8e194ac99d84221f405d0f684f8c.png)

3.  <span data-ttu-id="84299-283">Nadat u het beleid heeft toegepast, opent u een PowerShell Windows en typt `(Get-MpPreference).EnableNetworkProtection` u .</span><span class="sxs-lookup"><span data-stu-id="84299-283">After applying the policy, open a PowerShell Windows and type `(Get-MpPreference).EnableNetworkProtection`.</span></span>

4.  <span data-ttu-id="84299-284">Dit moet reageren met een 1 zoals hieronder wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="84299-284">This should respond with a 1 as shown below.</span></span>

    ![Afbeelding van opdrachtregel4](images/c06fa3bbc2f70d59dfe1e106cd9a4683.png)
