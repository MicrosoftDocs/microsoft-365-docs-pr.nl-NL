---
title: App-implementatie voor Microsoft Defender ATP voor iOS
ms.reviewer: ''
description: Beschrijft hoe u Microsoft Defender ATP voor iOS implementeert met een app
keywords: microsoft, defender, atp, ios, app, installatie, implementeren, verwijderen, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c7f60df38ce9f34fecae975be40206d7270b0863
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057529"
---
# <a name="deploy-microsoft-defender-for-endpoint-for-ios"></a><span data-ttu-id="631ac-104">Microsoft Defender voor eindpunt voor iOS implementeren</span><span class="sxs-lookup"><span data-stu-id="631ac-104">Deploy Microsoft Defender for Endpoint for iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="631ac-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="631ac-105">**Applies to:**</span></span>
- [<span data-ttu-id="631ac-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="631ac-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="631ac-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="631ac-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="631ac-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="631ac-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="631ac-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="631ac-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="631ac-110">In dit onderwerp wordt beschreven hoe u Defender voor Eindpunt voor iOS implementeert op intune Company Portal ingeschreven apparaten.</span><span class="sxs-lookup"><span data-stu-id="631ac-110">This topic describes deploying Defender for Endpoint for iOS on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="631ac-111">Zie [IOS/iPadOS-apparaten registreren in Intune](https://docs.microsoft.com/mem/intune/enrollment/ios-enroll)voor meer informatie over intune-apparaatinschrijvingen.</span><span class="sxs-lookup"><span data-stu-id="631ac-111">For more information about Intune device enrollment, see [Enroll iOS/iPadOS devices in Intune](https://docs.microsoft.com/mem/intune/enrollment/ios-enroll).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="631ac-112">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="631ac-112">Before you begin</span></span>

- <span data-ttu-id="631ac-113">Zorg ervoor dat u toegang hebt tot [het Beheercentrum voor Microsoft Endpoint Manager.](https://go.microsoft.com/fwlink/?linkid=2109431)</span><span class="sxs-lookup"><span data-stu-id="631ac-113">Ensure you have access to [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>

- <span data-ttu-id="631ac-114">Zorg ervoor dat iOS-registratie is gedaan voor uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="631ac-114">Ensure iOS enrollment is done for your users.</span></span> <span data-ttu-id="631ac-115">Gebruikers moeten een Defender voor Eindpunt-licentie hebben toegewezen om Defender voor Eindpunt voor iOS te kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="631ac-115">Users need to have a Defender for Endpoint license assigned in order to use Defender for Endpoint for iOS.</span></span> <span data-ttu-id="631ac-116">Raadpleeg [Licenties toewijzen aan gebruikers voor](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) instructies over het toewijzen van licenties.</span><span class="sxs-lookup"><span data-stu-id="631ac-116">Refer to [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) for instructions on how to assign licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="631ac-117">Microsoft Defender ATP (Microsoft Defender voor Eindpunt) voor iOS is nu beschikbaar in de [Apple App Store.](https://aka.ms/mdatpiosappstore)</span><span class="sxs-lookup"><span data-stu-id="631ac-117">Microsoft Defender ATP (Microsoft Defender for Endpoint) for iOS is now available in the [Apple App Store](https://aka.ms/mdatpiosappstore).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="631ac-118">Implementatiestappen</span><span class="sxs-lookup"><span data-stu-id="631ac-118">Deployment steps</span></span>

<span data-ttu-id="631ac-119">Deploy Defender for Endpoint for iOS via Intune Company Portal.</span><span class="sxs-lookup"><span data-stu-id="631ac-119">Deploy Defender for Endpoint for iOS via Intune Company Portal.</span></span>

### <a name="add-ios-store-app"></a><span data-ttu-id="631ac-120">IOS Store-app toevoegen</span><span class="sxs-lookup"><span data-stu-id="631ac-120">Add iOS store app</span></span>

1. <span data-ttu-id="631ac-121">Ga [in het Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431)naar **Apps**  ->  **iOS/iPadOS**  ->    ->  **IOS Store-app** toevoegen en klik op **Selecteren.**</span><span class="sxs-lookup"><span data-stu-id="631ac-121">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Apps** -> **iOS/iPadOS** -> **Add** -> **iOS store app** and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="631ac-122">![Afbeelding van Microsoft Endpoint Manager-beheercentrum1](images/ios-deploy-1.png)</span><span class="sxs-lookup"><span data-stu-id="631ac-122">![Image of Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span></span>

1. <span data-ttu-id="631ac-123">Klik op de pagina App toevoegen op **Zoeken in de App Store** en typ Microsoft Defender **ATP** in de zoekbalk.</span><span class="sxs-lookup"><span data-stu-id="631ac-123">On the Add app page, click on **Search the App Store** and type **Microsoft Defender ATP** in the search bar.</span></span> <span data-ttu-id="631ac-124">Klik in de sectie zoekresultaten op *Microsoft Defender ATP* en klik op **Selecteren.**</span><span class="sxs-lookup"><span data-stu-id="631ac-124">In the search results section, click on *Microsoft Defender ATP* and click **Select**.</span></span>

1. <span data-ttu-id="631ac-125">Selecteer **iOS 11.0 als** het besturingssysteem Minimum.</span><span class="sxs-lookup"><span data-stu-id="631ac-125">Select **iOS 11.0** as the Minimum operating system.</span></span> <span data-ttu-id="631ac-126">Bekijk de rest van de informatie over de app en klik op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="631ac-126">Review the rest of information about the app and click **Next**.</span></span>

1. <span data-ttu-id="631ac-127">Ga in *de sectie Opdrachten* naar de sectie **Vereist** en selecteer **Groep toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="631ac-127">In the *Assignments* section, go to the **Required** section and select **Add group**.</span></span> <span data-ttu-id="631ac-128">Vervolgens kunt u de gebruikersgroep(s) kiezen die u wilt richten op Defender voor Endpoint voor iOS-app.</span><span class="sxs-lookup"><span data-stu-id="631ac-128">You can then choose the user group(s) that you would like to target Defender for Endpoint for iOS app.</span></span> <span data-ttu-id="631ac-129">Klik **op Selecteren** en vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="631ac-129">Click **Select** and then **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="631ac-130">De geselecteerde gebruikersgroep moet bestaan uit intune geregistreerde gebruikers.</span><span class="sxs-lookup"><span data-stu-id="631ac-130">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="631ac-131">![Afbeelding van Microsoft Endpoint Manager-beheercentrum2](images/ios-deploy-2.png)</span><span class="sxs-lookup"><span data-stu-id="631ac-131">![Image of Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span></span>

1. <span data-ttu-id="631ac-132">Controleer in *de sectie Controleren +* maken of alle ingevoerde gegevens juist zijn en selecteer vervolgens **Maken.**</span><span class="sxs-lookup"><span data-stu-id="631ac-132">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span> <span data-ttu-id="631ac-133">Over een paar minuten moet de Defender voor Eindpunt-app worden gemaakt en wordt er een melding weergegeven in de rechterbovenhoek van de pagina.</span><span class="sxs-lookup"><span data-stu-id="631ac-133">In a few moments, the Defender for Endpoint app should be created successfully, and a notification should show up at the top-right corner of the page.</span></span>

1. <span data-ttu-id="631ac-134">Selecteer op de pagina met app-informatie die wordt weergegeven in de sectie Monitor de **status** apparaatinstallatie om te controleren of de installatie van het apparaat is voltooid. </span><span class="sxs-lookup"><span data-stu-id="631ac-134">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="631ac-135">![Afbeelding van Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span><span class="sxs-lookup"><span data-stu-id="631ac-135">![Image of Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span></span>

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="631ac-136">De onboarding- en controlestatus voltooien</span><span class="sxs-lookup"><span data-stu-id="631ac-136">Complete onboarding and check status</span></span>

1. <span data-ttu-id="631ac-137">Wanneer Defender voor Eindpunt voor iOS op het apparaat is geïnstalleerd, ziet u het app-pictogram.</span><span class="sxs-lookup"><span data-stu-id="631ac-137">Once Defender for Endpoint for iOS has been installed on the device, you  will see the app icon.</span></span>

    ![Een schermafbeelding van een beschrijving van een smartphone die automatisch wordt gegenereerd](images/41627a709700c324849bf7e13510c516.png)

2. <span data-ttu-id="631ac-139">Tik op het pictogram van de Defender voor eindpunt-app en volg de instructies op het scherm om de onboarding-stappen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="631ac-139">Tap the Defender for Endpoint app icon and follow the on-screen instructions to complete the onboarding steps.</span></span> <span data-ttu-id="631ac-140">De details omvatten de acceptatie door eindgebruikers van iOS-machtigingen die vereist zijn door Defender voor Eindpunt voor iOS.</span><span class="sxs-lookup"><span data-stu-id="631ac-140">The details include end-user acceptance of iOS permissions required by Defender for Endpoint for iOS.</span></span>

3. <span data-ttu-id="631ac-141">Na succesvolle onboarding wordt het apparaat weergegeven in de lijst Apparaten in het Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="631ac-141">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="631ac-142">![Een schermafbeelding van een beschrijving van een mobiele telefoon die automatisch wordt gegenereerd](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span><span class="sxs-lookup"><span data-stu-id="631ac-142">![A screenshot of a cell phone Description automatically generated](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span></span>

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a><span data-ttu-id="631ac-143">Microsoft Defender voor eindpunt configureren voor modus onder toezicht</span><span class="sxs-lookup"><span data-stu-id="631ac-143">Configure Microsoft Defender for Endpoint for Supervised Mode</span></span>

<span data-ttu-id="631ac-144">De Microsoft Defender voor Endpoint voor iOS-app heeft een speciale mogelijkheid op gecontroleerde iOS-/iPadOS-apparaten, gezien de verbeterde beheermogelijkheden die het platform biedt op dit type apparaten.</span><span class="sxs-lookup"><span data-stu-id="631ac-144">The Microsoft Defender for Endpoint for iOS app has specialized ability on supervised iOS/iPadOS devices, given the increased management capabilities provided by the platform on these types of devices.</span></span> <span data-ttu-id="631ac-145">Als u van deze mogelijkheden wilt profiteren, moet de Defender voor Eindpunt-app weten of een apparaat in de modus Onder toezicht staat.</span><span class="sxs-lookup"><span data-stu-id="631ac-145">To take advantage of these capabilities, the Defender for Endpoint app needs to know if a device is in Supervised Mode.</span></span>

### <a name="configure-supervised-mode-via-intune"></a><span data-ttu-id="631ac-146">Modus onder toezicht configureren via Intune</span><span class="sxs-lookup"><span data-stu-id="631ac-146">Configure Supervised Mode via Intune</span></span>

<span data-ttu-id="631ac-147">Met Intune kunt u de Defender voor iOS-app configureren via een beleid voor app-configuratie.</span><span class="sxs-lookup"><span data-stu-id="631ac-147">Intune allows you to configure the Defender for iOS app through an App Configuration policy.</span></span>

   > [!NOTE]
   > <span data-ttu-id="631ac-148">Dit app-configuratiebeleid voor apparaten met toezicht is alleen van toepassing op beheerde apparaten en moet als beste zijn gericht op alle beheerde iOS-apparaten.</span><span class="sxs-lookup"><span data-stu-id="631ac-148">This app configuration policy for supervised devices is applicable only to managed devices and should be targeted for all managed iOS devices as a best practice.</span></span>

1. <span data-ttu-id="631ac-149">Meld u aan bij [het Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) en ga naar **Het configuratiebeleid** voor  >  **Apps App**  >  **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="631ac-149">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Apps** > **App configuration policies** > **Add**.</span></span> <span data-ttu-id="631ac-150">Klik op **Beheerde apparaten.**</span><span class="sxs-lookup"><span data-stu-id="631ac-150">Click on **Managed devices**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="631ac-151">![Afbeelding van Beheercentrum voor Microsoft Endpoint Manager4](images/ios-deploy-4.png)</span><span class="sxs-lookup"><span data-stu-id="631ac-151">![Image of Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span></span>

1. <span data-ttu-id="631ac-152">Geef op *de pagina Configuratiebeleid voor* apps maken de volgende informatie op:</span><span class="sxs-lookup"><span data-stu-id="631ac-152">In the *Create app configuration policy* page, provide the following information:</span></span>
    - <span data-ttu-id="631ac-153">Naam van beleid</span><span class="sxs-lookup"><span data-stu-id="631ac-153">Policy Name</span></span>
    - <span data-ttu-id="631ac-154">Platform: selecteer iOS/iPadOS</span><span class="sxs-lookup"><span data-stu-id="631ac-154">Platform: Select iOS/iPadOS</span></span>
    - <span data-ttu-id="631ac-155">Gerichte app: Microsoft **Defender ATP selecteren** in de lijst</span><span class="sxs-lookup"><span data-stu-id="631ac-155">Targeted app: Select **Microsoft Defender ATP** from the list</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="631ac-156">![Afbeelding van Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span><span class="sxs-lookup"><span data-stu-id="631ac-156">![Image of Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span></span>

1. <span data-ttu-id="631ac-157">Selecteer configuratieontwerper gebruiken als **opmaak** in het volgende scherm.</span><span class="sxs-lookup"><span data-stu-id="631ac-157">In the next screen, select **Use configuration designer** as the format.</span></span> <span data-ttu-id="631ac-158">Geef de volgende eigenschap op:</span><span class="sxs-lookup"><span data-stu-id="631ac-158">Specify the following property:</span></span>
    - <span data-ttu-id="631ac-159">Configuratiesleutel: wordt onder toezicht</span><span class="sxs-lookup"><span data-stu-id="631ac-159">Configuration Key: issupervised</span></span>
    - <span data-ttu-id="631ac-160">Waardetype: tekenreeks</span><span class="sxs-lookup"><span data-stu-id="631ac-160">Value type: String</span></span>
    - <span data-ttu-id="631ac-161">Configuratiewaarde: {{issupervised}}</span><span class="sxs-lookup"><span data-stu-id="631ac-161">Configuration Value: {{issupervised}}</span></span>
    
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="631ac-162">![Afbeelding van Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span><span class="sxs-lookup"><span data-stu-id="631ac-162">![Image of Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span></span>

1. <span data-ttu-id="631ac-163">Klik **op Volgende** om de pagina **Bereiklabels te** openen.</span><span class="sxs-lookup"><span data-stu-id="631ac-163">Click **Next** to open the **Scope tags** page.</span></span> <span data-ttu-id="631ac-164">Bereiklabels zijn optioneel.</span><span class="sxs-lookup"><span data-stu-id="631ac-164">Scope tags are optional.</span></span> <span data-ttu-id="631ac-165">Klik **op Volgende om** door te gaan.</span><span class="sxs-lookup"><span data-stu-id="631ac-165">Click **Next** to continue.</span></span>

1. <span data-ttu-id="631ac-166">Selecteer op **de pagina** Opdrachten de groepen die dit profiel ontvangen.</span><span class="sxs-lookup"><span data-stu-id="631ac-166">On the **Assignments** page, select the groups that will receive this profile.</span></span> <span data-ttu-id="631ac-167">Voor dit scenario is het de beste manier om alle apparaten **te targeten.**</span><span class="sxs-lookup"><span data-stu-id="631ac-167">For this scenario, it is best practice to target **All Devices**.</span></span> <span data-ttu-id="631ac-168">Zie Gebruikers- en apparaatprofielen toewijzen voor meer informatie over het toewijzen [van profielen.](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)</span><span class="sxs-lookup"><span data-stu-id="631ac-168">For more information on assigning profiles, see [Assign user and device profiles](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

   <span data-ttu-id="631ac-169">Bij het implementeren naar gebruikersgroepen moet een gebruiker zich aanmelden bij een apparaat voordat het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="631ac-169">When deploying to user groups, a user must sign in to a device before the policy applies.</span></span>

   <span data-ttu-id="631ac-170">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="631ac-170">Click **Next**.</span></span>

1. <span data-ttu-id="631ac-171">Kies op **de pagina Controleren +** maken de optie Maken als u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="631ac-171">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="631ac-172">Het nieuwe profiel wordt weergegeven in de lijst met configuratieprofielen.</span><span class="sxs-lookup"><span data-stu-id="631ac-172">The new profile is displayed in the list of configuration profiles.</span></span>

1. <span data-ttu-id="631ac-173">Vervolgens kunt u een aangepast profiel implementeren op de gecontroleerde iOS-apparaten voor uitgebreide anti-phishing-mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="631ac-173">Next, for enhanced Anti-phishing capabilities, you can deploy a custom profile on the supervised iOS devices.</span></span> <span data-ttu-id="631ac-174">Volg de onderstaande stappen:</span><span class="sxs-lookup"><span data-stu-id="631ac-174">Follow the steps below:</span></span>
    - <span data-ttu-id="631ac-175">Het config-profiel downloaden van [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span><span class="sxs-lookup"><span data-stu-id="631ac-175">Download the config profile from [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span></span>
    - <span data-ttu-id="631ac-176">Ga naar **Apparaten**  ->  **iOS/iPadOS-configuratieprofielen**  ->    ->  **Profiel maken**</span><span class="sxs-lookup"><span data-stu-id="631ac-176">Navigate to **Devices** -> **iOS/iPadOS** -> **Configuration profiles** -> **Create Profile**</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="631ac-177">![Afbeelding van Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span><span class="sxs-lookup"><span data-stu-id="631ac-177">![Image of Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span></span>

    - <span data-ttu-id="631ac-178">Geef een naam op van het profiel.</span><span class="sxs-lookup"><span data-stu-id="631ac-178">Provide a name of the profile.</span></span> <span data-ttu-id="631ac-179">Wanneer u wordt gevraagd een configuratieprofielbestand te importeren, selecteert u het profiel dat hierboven is gedownload.</span><span class="sxs-lookup"><span data-stu-id="631ac-179">When prompted to import a Configuration profile file, select the one downloaded above.</span></span>
    - <span data-ttu-id="631ac-180">Selecteer in **de** sectie Toewijzing de apparaatgroep waarop u dit profiel wilt toepassen.</span><span class="sxs-lookup"><span data-stu-id="631ac-180">In the **Assignment** section, select the device group to which you want to apply this profile.</span></span> <span data-ttu-id="631ac-181">Dit moet worden toegepast op alle beheerde iOS-apparaten.</span><span class="sxs-lookup"><span data-stu-id="631ac-181">As a best practice, this should be applied to all managed iOS devices.</span></span> <span data-ttu-id="631ac-182">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="631ac-182">Click **Next**.</span></span>
    - <span data-ttu-id="631ac-183">Kies op **de pagina Controleren +** maken de optie Maken als u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="631ac-183">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="631ac-184">Het nieuwe profiel wordt weergegeven in de lijst met configuratieprofielen.</span><span class="sxs-lookup"><span data-stu-id="631ac-184">The new profile is displayed in the list of configuration profiles.</span></span>

## <a name="next-steps"></a><span data-ttu-id="631ac-185">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="631ac-185">Next Steps</span></span>

[<span data-ttu-id="631ac-186">Defender configureren voor endpoint voor iOS-functies</span><span class="sxs-lookup"><span data-stu-id="631ac-186">Configure Defender for Endpoint for iOS features</span></span>](ios-configure-features.md)
