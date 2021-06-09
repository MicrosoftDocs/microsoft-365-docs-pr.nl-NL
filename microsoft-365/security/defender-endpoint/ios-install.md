---
title: App-implementatie voor Microsoft Defender voor Eindpunt op iOS
ms.reviewer: ''
description: Beschrijft hoe u Microsoft Defender voor Eindpunt implementeert in iOS met een app
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, app, installation, deploy, uninstallation, intune
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 371208433cbb0f65ab5a2808318c03dae6bb6d8b
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842292"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="1246c-104">Microsoft Defender voor eindpunt implementeren in iOS</span><span class="sxs-lookup"><span data-stu-id="1246c-104">Deploy Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1246c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="1246c-105">**Applies to:**</span></span>
- [<span data-ttu-id="1246c-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="1246c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1246c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1246c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1246c-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="1246c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1246c-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="1246c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="1246c-110">In dit onderwerp wordt beschreven hoe u Defender voor Eindpunt implementeert op iOS op Intune-bedrijfsportal geregistreerde apparaten.</span><span class="sxs-lookup"><span data-stu-id="1246c-110">This topic describes deploying Defender for Endpoint on iOS on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="1246c-111">Zie [IOS/iPadOS-apparaten registreren in Intune](/mem/intune/enrollment/ios-enroll)voor meer informatie over intune-apparaatinschrijvingen.</span><span class="sxs-lookup"><span data-stu-id="1246c-111">For more information about Intune device enrollment, see [Enroll iOS/iPadOS devices in Intune](/mem/intune/enrollment/ios-enroll).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1246c-112">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="1246c-112">Before you begin</span></span>

- <span data-ttu-id="1246c-113">Zorg ervoor dat u toegang hebt tot [het Beheercentrum voor Microsoft Endpoint Manager.](https://go.microsoft.com/fwlink/?linkid=2109431)</span><span class="sxs-lookup"><span data-stu-id="1246c-113">Ensure you have access to [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>

- <span data-ttu-id="1246c-114">Zorg ervoor dat iOS-registratie is gedaan voor uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="1246c-114">Ensure iOS enrollment is done for your users.</span></span> <span data-ttu-id="1246c-115">Gebruikers moeten een Defender voor Eindpunt-licentie hebben toegewezen om Defender voor Eindpunt in iOS te kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="1246c-115">Users need to have a Defender for Endpoint license assigned in order to use Defender for Endpoint on iOS.</span></span> <span data-ttu-id="1246c-116">Raadpleeg [Licenties toewijzen aan gebruikers voor](/azure/active-directory/users-groups-roles/licensing-groups-assign) instructies over het toewijzen van licenties.</span><span class="sxs-lookup"><span data-stu-id="1246c-116">Refer to [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign) for instructions on how to assign licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="1246c-117">Microsoft Defender voor Eindpunt voor iOS is beschikbaar in de [Apple App Store.](https://aka.ms/mdatpiosappstore)</span><span class="sxs-lookup"><span data-stu-id="1246c-117">Microsoft Defender for Endpoint on iOS is available in the [Apple App Store](https://aka.ms/mdatpiosappstore).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="1246c-118">Implementatiestappen</span><span class="sxs-lookup"><span data-stu-id="1246c-118">Deployment steps</span></span>

<span data-ttu-id="1246c-119">Deploy Defender for Endpoint on iOS via Intune-bedrijfsportal.</span><span class="sxs-lookup"><span data-stu-id="1246c-119">Deploy Defender for Endpoint on iOS via Intune Company Portal.</span></span>

### <a name="add-ios-store-app"></a><span data-ttu-id="1246c-120">IOS Store-app toevoegen</span><span class="sxs-lookup"><span data-stu-id="1246c-120">Add iOS store app</span></span>

1. <span data-ttu-id="1246c-121">Ga [in het Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431)naar **Apps**  ->  **iOS/iPadOS**  ->    ->  **IOS Store-app** toevoegen en klik op **Selecteren.**</span><span class="sxs-lookup"><span data-stu-id="1246c-121">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Apps** -> **iOS/iPadOS** -> **Add** -> **iOS store app** and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1246c-122">![Afbeelding van Microsoft Endpoint Manager beheercentrum1](images/ios-deploy-1.png)</span><span class="sxs-lookup"><span data-stu-id="1246c-122">![Image of Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span></span>

1. <span data-ttu-id="1246c-123">Klik op de pagina App toevoegen op **Zoeken in de App Store** en typ Microsoft **Defender-eindpunt** in de zoekbalk.</span><span class="sxs-lookup"><span data-stu-id="1246c-123">On the Add app page, click on **Search the App Store** and type **Microsoft Defender Endpoint** in the search bar.</span></span> <span data-ttu-id="1246c-124">Klik in de sectie zoekresultaten op *Microsoft Defender-eindpunt en* klik op **Selecteren.**</span><span class="sxs-lookup"><span data-stu-id="1246c-124">In the search results section, click on *Microsoft Defender Endpoint* and click **Select**.</span></span>

1. <span data-ttu-id="1246c-125">Selecteer **iOS 11.0 als** het besturingssysteem Minimum.</span><span class="sxs-lookup"><span data-stu-id="1246c-125">Select **iOS 11.0** as the Minimum operating system.</span></span> <span data-ttu-id="1246c-126">Bekijk de rest van de informatie over de app en klik op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="1246c-126">Review the rest of information about the app and click **Next**.</span></span>

1. <span data-ttu-id="1246c-127">Ga in *de sectie Opdrachten* naar de sectie **Vereist** en selecteer **Groep toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="1246c-127">In the *Assignments* section, go to the **Required** section and select **Add group**.</span></span> <span data-ttu-id="1246c-128">U kunt vervolgens de gebruikersgroep(s) kiezen die u wilt richten op Defender voor Eindpunt in de iOS-app.</span><span class="sxs-lookup"><span data-stu-id="1246c-128">You can then choose the user group(s) that you would like to target Defender for Endpoint on iOS app.</span></span> <span data-ttu-id="1246c-129">Klik **op Selecteren** en vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="1246c-129">Click **Select** and then **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1246c-130">De geselecteerde gebruikersgroep moet bestaan uit intune geregistreerde gebruikers.</span><span class="sxs-lookup"><span data-stu-id="1246c-130">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1246c-131">![Afbeelding van Microsoft Endpoint Manager beheercentrum2](images/ios-deploy-2.png)</span><span class="sxs-lookup"><span data-stu-id="1246c-131">![Image of Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span></span>

1. <span data-ttu-id="1246c-132">Controleer in *de sectie Controleren +* maken of alle ingevoerde gegevens juist zijn en selecteer vervolgens **Maken.**</span><span class="sxs-lookup"><span data-stu-id="1246c-132">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span> <span data-ttu-id="1246c-133">Over een paar minuten moet de Defender voor Eindpunt-app worden gemaakt en wordt er een melding weergegeven in de rechterbovenhoek van de pagina.</span><span class="sxs-lookup"><span data-stu-id="1246c-133">In a few moments, the Defender for Endpoint app should be created successfully, and a notification should show up at the top-right corner of the page.</span></span>

1. <span data-ttu-id="1246c-134">Selecteer op de pagina met app-informatie die wordt weergegeven in de sectie Monitor de **status** apparaatinstallatie om te controleren of de installatie van het apparaat is voltooid. </span><span class="sxs-lookup"><span data-stu-id="1246c-134">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1246c-135">![Afbeelding van Microsoft Endpoint Manager beheercentrum3](images/ios-deploy-3.png)</span><span class="sxs-lookup"><span data-stu-id="1246c-135">![Image of Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span></span>

## <a name="auto-onboarding-of-vpn-profile-simplified-onboarding"></a><span data-ttu-id="1246c-136">Auto-Onboarding van VPN-profiel (Vereenvoudigde onboarding)</span><span class="sxs-lookup"><span data-stu-id="1246c-136">Auto-Onboarding of VPN profile (Simplified Onboarding)</span></span>

<span data-ttu-id="1246c-137">Beheerders kunnen de automatische installatie van VPN-profiel configureren.</span><span class="sxs-lookup"><span data-stu-id="1246c-137">Admins can configure auto-setup of VPN profile.</span></span> <span data-ttu-id="1246c-138">Hiermee wordt het VPN-profiel van Defender voor Eindpunt automatisch ingesteld zonder dat de gebruiker dit hoeft te doen tijdens onboarding.</span><span class="sxs-lookup"><span data-stu-id="1246c-138">This will automatically setup the Defender for Endpoint VPN profile without having the user to do so while onboarding.</span></span> <span data-ttu-id="1246c-139">Houd er rekening mee dat VPN wordt gebruikt om de functie Webbeveiliging te bieden.</span><span class="sxs-lookup"><span data-stu-id="1246c-139">Note that VPN is used in order to provide the Web Protection feature.</span></span> <span data-ttu-id="1246c-140">Dit is geen gewone VPN en is een lokale/self-looping VPN die geen verkeer buiten het apparaat neemt.</span><span class="sxs-lookup"><span data-stu-id="1246c-140">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

1. <span data-ttu-id="1246c-141">Ga [in het Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431)naar Profiel maken van   ->    ->  **apparatenconfiguratieprofielen.**</span><span class="sxs-lookup"><span data-stu-id="1246c-141">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Configuration Profiles** -> **Create Profile**.</span></span>
1. <span data-ttu-id="1246c-142">Kies **Platform** als **iOS/iPadOS** en **Profieltype** als **VPN.**</span><span class="sxs-lookup"><span data-stu-id="1246c-142">Choose **Platform** as **iOS/iPadOS** and **Profile type** as **VPN**.</span></span> <span data-ttu-id="1246c-143">Klik op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="1246c-143">Click **Create**.</span></span>
1. <span data-ttu-id="1246c-144">Typ een naam voor het profiel en klik op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="1246c-144">Type a name for the profile and click **Next**.</span></span>
1. <span data-ttu-id="1246c-145">Selecteer **Aangepaste VPN** voor verbindingstype en voer in de sectie Base **VPN** het volgende in:</span><span class="sxs-lookup"><span data-stu-id="1246c-145">Select **Custom VPN** for Connection Type and in the **Base VPN** section, enter the following:</span></span>
    - <span data-ttu-id="1246c-146">Naam van verbinding = Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="1246c-146">Connection Name = Microsoft Defender for Endpoint</span></span>
    - <span data-ttu-id="1246c-147">VPN-serveradres = 127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="1246c-147">VPN server address = 127.0.0.1</span></span>
    - <span data-ttu-id="1246c-148">Auth method = "Gebruikersnaam en wachtwoord"</span><span class="sxs-lookup"><span data-stu-id="1246c-148">Auth method = "Username and password"</span></span>
    - <span data-ttu-id="1246c-149">Splits tunneling = Uitschakelen</span><span class="sxs-lookup"><span data-stu-id="1246c-149">Split Tunneling = Disable</span></span>
    - <span data-ttu-id="1246c-150">VPN-id = com.microsoft.scmx</span><span class="sxs-lookup"><span data-stu-id="1246c-150">VPN identifier = com.microsoft.scmx</span></span>
    - <span data-ttu-id="1246c-151">Voer in de sleutel-waardeparen de sleutel **AutoOnboard in** en stel de waarde in op **Waar.**</span><span class="sxs-lookup"><span data-stu-id="1246c-151">In the key-value pairs, enter the key **AutoOnboard** and set the value to **True**.</span></span>
    - <span data-ttu-id="1246c-152">Type automatische VPN = ON-demand VPN</span><span class="sxs-lookup"><span data-stu-id="1246c-152">Type of Automatic VPN = On-demand VPN</span></span>
    - <span data-ttu-id="1246c-153">Klik **op Toevoegen** voor **Regels** op aanvraag en selecteer Ik wil het volgende doen **= VPN** instellen, ik wil beperken tot = Alle **domeinen**.</span><span class="sxs-lookup"><span data-stu-id="1246c-153">Click **Add** for **On Demand Rules** and select **I want to do the following = Establish VPN**, **I want to restrict to = All domains**.</span></span>

    ![Een schermafbeelding van vpn-profielconfiguratie](images/ios-deploy-8.png)

1. <span data-ttu-id="1246c-155">Klik op Volgende en wijs het profiel toe aan gerichte gebruikers.</span><span class="sxs-lookup"><span data-stu-id="1246c-155">Click Next and assign the profile to targeted users.</span></span>
1. <span data-ttu-id="1246c-156">Controleer in *de sectie Controleren +* maken of alle ingevoerde gegevens juist zijn en selecteer vervolgens **Maken.**</span><span class="sxs-lookup"><span data-stu-id="1246c-156">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="1246c-157">De onboarding- en controlestatus voltooien</span><span class="sxs-lookup"><span data-stu-id="1246c-157">Complete onboarding and check status</span></span>

1. <span data-ttu-id="1246c-158">Zodra Defender voor Eindpunt op iOS is geïnstalleerd op het apparaat, ziet u het app-pictogram.</span><span class="sxs-lookup"><span data-stu-id="1246c-158">Once Defender for Endpoint on iOS has been installed on the device, you  will see the app icon.</span></span>

    ![Een schermafbeelding van een beschrijving van een smartphone die automatisch wordt gegenereerd](images/41627a709700c324849bf7e13510c516.png)

2. <span data-ttu-id="1246c-160">Tik op het pictogram van de Defender voor eindpunt-app (MSDefender) en volg de instructies op het scherm om de onboarding-stappen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="1246c-160">Tap the Defender for Endpoint app icon (MSDefender) and follow the on-screen instructions to complete the onboarding steps.</span></span> <span data-ttu-id="1246c-161">De details omvatten de acceptatie door eindgebruikers van iOS-machtigingen die vereist zijn door Defender voor Eindpunt in iOS.</span><span class="sxs-lookup"><span data-stu-id="1246c-161">The details include end-user acceptance of iOS permissions required by Defender for Endpoint on iOS.</span></span>

3. <span data-ttu-id="1246c-162">Na succesvolle onboarding wordt het apparaat weergegeven in de lijst Apparaten in Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="1246c-162">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1246c-163">![Een schermafbeelding van een beschrijving van een mobiele telefoon die automatisch wordt gegenereerd](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span><span class="sxs-lookup"><span data-stu-id="1246c-163">![A screenshot of a cell phone Description automatically generated](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span></span>

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a><span data-ttu-id="1246c-164">Microsoft Defender voor eindpunt configureren voor modus onder toezicht</span><span class="sxs-lookup"><span data-stu-id="1246c-164">Configure Microsoft Defender for Endpoint for Supervised Mode</span></span>

<span data-ttu-id="1246c-165">De Microsoft Defender for Endpoint-app voor iOS heeft een speciale mogelijkheid op gecontroleerde iOS-/iPadOS-apparaten, gezien de verbeterde beheermogelijkheden die het platform biedt op dit type apparaten.</span><span class="sxs-lookup"><span data-stu-id="1246c-165">The Microsoft Defender for Endpoint on iOS app has specialized ability on supervised iOS/iPadOS devices, given the increased management capabilities provided by the platform on these types of devices.</span></span> <span data-ttu-id="1246c-166">Als u van deze mogelijkheden wilt profiteren, moet de Defender voor Eindpunt-app weten of een apparaat in de modus Onder toezicht staat.</span><span class="sxs-lookup"><span data-stu-id="1246c-166">To take advantage of these capabilities, the Defender for Endpoint app needs to know if a device is in Supervised Mode.</span></span>

### <a name="configure-supervised-mode-via-intune"></a><span data-ttu-id="1246c-167">Modus onder toezicht configureren via Intune</span><span class="sxs-lookup"><span data-stu-id="1246c-167">Configure Supervised Mode via Intune</span></span>

<span data-ttu-id="1246c-168">Met Intune kunt u de Defender voor iOS-app configureren via een beleid voor app-configuratie.</span><span class="sxs-lookup"><span data-stu-id="1246c-168">Intune allows you to configure the Defender for iOS app through an App Configuration policy.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1246c-169">Dit app-configuratiebeleid voor apparaten met toezicht is alleen van toepassing op beheerde apparaten en moet als beste zijn gericht op alle beheerde iOS-apparaten.</span><span class="sxs-lookup"><span data-stu-id="1246c-169">This app configuration policy for supervised devices is applicable only to managed devices and should be targeted for all managed iOS devices as a best practice.</span></span>

1. <span data-ttu-id="1246c-170">Meld u aan bij het [Microsoft Endpoint Manager beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) en ga naar **Het configuratiebeleid** voor Apps  >  **App**  >  **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="1246c-170">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Apps** > **App configuration policies** > **Add**.</span></span> <span data-ttu-id="1246c-171">Klik op **Beheerde apparaten.**</span><span class="sxs-lookup"><span data-stu-id="1246c-171">Click on **Managed devices**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1246c-172">![Afbeelding van Microsoft Endpoint Manager beheercentrum4](images/ios-deploy-4.png)</span><span class="sxs-lookup"><span data-stu-id="1246c-172">![Image of Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span></span>

1. <span data-ttu-id="1246c-173">Geef op *de pagina Configuratiebeleid voor* apps maken de volgende informatie op:</span><span class="sxs-lookup"><span data-stu-id="1246c-173">In the *Create app configuration policy* page, provide the following information:</span></span>
    - <span data-ttu-id="1246c-174">Naam van beleid</span><span class="sxs-lookup"><span data-stu-id="1246c-174">Policy Name</span></span>
    - <span data-ttu-id="1246c-175">Platform: selecteer iOS/iPadOS</span><span class="sxs-lookup"><span data-stu-id="1246c-175">Platform: Select iOS/iPadOS</span></span>
    - <span data-ttu-id="1246c-176">Targeted app: Selecteer **Microsoft Defender Endpoint** in de lijst</span><span class="sxs-lookup"><span data-stu-id="1246c-176">Targeted app: Select **Microsoft Defender Endpoint** from the list</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1246c-177">![Afbeelding van Microsoft Endpoint Manager beheercentrum5](images/ios-deploy-5.png)</span><span class="sxs-lookup"><span data-stu-id="1246c-177">![Image of Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span></span>

1. <span data-ttu-id="1246c-178">Selecteer configuratieontwerper gebruiken als **opmaak** in het volgende scherm.</span><span class="sxs-lookup"><span data-stu-id="1246c-178">In the next screen, select **Use configuration designer** as the format.</span></span> <span data-ttu-id="1246c-179">Geef de volgende eigenschap op:</span><span class="sxs-lookup"><span data-stu-id="1246c-179">Specify the following property:</span></span>
    - <span data-ttu-id="1246c-180">Configuratiesleutel: wordt onder toezicht</span><span class="sxs-lookup"><span data-stu-id="1246c-180">Configuration Key: issupervised</span></span>
    - <span data-ttu-id="1246c-181">Waardetype: tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1246c-181">Value type: String</span></span>
    - <span data-ttu-id="1246c-182">Configuratiewaarde: {{issupervised}}</span><span class="sxs-lookup"><span data-stu-id="1246c-182">Configuration Value: {{issupervised}}</span></span>
    
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1246c-183">![Afbeelding van Microsoft Endpoint Manager beheercentrum6](images/ios-deploy-6.png)</span><span class="sxs-lookup"><span data-stu-id="1246c-183">![Image of Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span></span>

1. <span data-ttu-id="1246c-184">Klik **op Volgende** om de pagina **Bereiklabels te** openen.</span><span class="sxs-lookup"><span data-stu-id="1246c-184">Click **Next** to open the **Scope tags** page.</span></span> <span data-ttu-id="1246c-185">Bereiklabels zijn optioneel.</span><span class="sxs-lookup"><span data-stu-id="1246c-185">Scope tags are optional.</span></span> <span data-ttu-id="1246c-186">Klik **op Volgende om** door te gaan.</span><span class="sxs-lookup"><span data-stu-id="1246c-186">Click **Next** to continue.</span></span>

1. <span data-ttu-id="1246c-187">Selecteer op **de pagina** Opdrachten de groepen die dit profiel ontvangen.</span><span class="sxs-lookup"><span data-stu-id="1246c-187">On the **Assignments** page, select the groups that will receive this profile.</span></span> <span data-ttu-id="1246c-188">Voor dit scenario is het de beste manier om alle apparaten **te targeten.**</span><span class="sxs-lookup"><span data-stu-id="1246c-188">For this scenario, it is best practice to target **All Devices**.</span></span> <span data-ttu-id="1246c-189">Zie Gebruikers- en apparaatprofielen toewijzen voor meer informatie over het toewijzen [van profielen.](/mem/intune/configuration/device-profile-assign)</span><span class="sxs-lookup"><span data-stu-id="1246c-189">For more information on assigning profiles, see [Assign user and device profiles](/mem/intune/configuration/device-profile-assign).</span></span>

   <span data-ttu-id="1246c-190">Bij het implementeren naar gebruikersgroepen moet een gebruiker zich aanmelden bij een apparaat voordat het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="1246c-190">When deploying to user groups, a user must sign in to a device before the policy applies.</span></span>

   <span data-ttu-id="1246c-191">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="1246c-191">Click **Next**.</span></span>

1. <span data-ttu-id="1246c-192">Kies op **de pagina Controleren +** maken de optie Maken als u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="1246c-192">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="1246c-193">Het nieuwe profiel wordt weergegeven in de lijst met configuratieprofielen.</span><span class="sxs-lookup"><span data-stu-id="1246c-193">The new profile is displayed in the list of configuration profiles.</span></span>

1. <span data-ttu-id="1246c-194">Vervolgens kunt u een aangepast profiel implementeren op de gecontroleerde iOS-apparaten voor uitgebreide anti-phishing-mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="1246c-194">Next, for enhanced Anti-phishing capabilities, you can deploy a custom profile on the supervised iOS devices.</span></span> <span data-ttu-id="1246c-195">Volg de onderstaande stappen:</span><span class="sxs-lookup"><span data-stu-id="1246c-195">Follow the steps below:</span></span>
    - <span data-ttu-id="1246c-196">Het config-profiel downloaden van [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span><span class="sxs-lookup"><span data-stu-id="1246c-196">Download the config profile from [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span></span>
    - <span data-ttu-id="1246c-197">Ga naar **Apparaten**  ->  **iOS/iPadOS-configuratieprofielen**  ->    ->  **Profiel maken**</span><span class="sxs-lookup"><span data-stu-id="1246c-197">Navigate to **Devices** -> **iOS/iPadOS** -> **Configuration profiles** -> **Create Profile**</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1246c-198">![Afbeelding van Microsoft Endpoint Manager beheercentrum7](images/ios-deploy-7.png)</span><span class="sxs-lookup"><span data-stu-id="1246c-198">![Image of Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span></span>

    - <span data-ttu-id="1246c-199">Geef een naam op van het profiel.</span><span class="sxs-lookup"><span data-stu-id="1246c-199">Provide a name of the profile.</span></span> <span data-ttu-id="1246c-200">Wanneer u wordt gevraagd een configuratieprofielbestand te importeren, selecteert u het profiel dat hierboven is gedownload.</span><span class="sxs-lookup"><span data-stu-id="1246c-200">When prompted to import a Configuration profile file, select the one downloaded above.</span></span>
    - <span data-ttu-id="1246c-201">Selecteer in **de** sectie Toewijzing de apparaatgroep waarop u dit profiel wilt toepassen.</span><span class="sxs-lookup"><span data-stu-id="1246c-201">In the **Assignment** section, select the device group to which you want to apply this profile.</span></span> <span data-ttu-id="1246c-202">Dit moet worden toegepast op alle beheerde iOS-apparaten.</span><span class="sxs-lookup"><span data-stu-id="1246c-202">As a best practice, this should be applied to all managed iOS devices.</span></span> <span data-ttu-id="1246c-203">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="1246c-203">Click **Next**.</span></span>
    - <span data-ttu-id="1246c-204">Kies op **de pagina Controleren +** maken de optie Maken als u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="1246c-204">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="1246c-205">Het nieuwe profiel wordt weergegeven in de lijst met configuratieprofielen.</span><span class="sxs-lookup"><span data-stu-id="1246c-205">The new profile is displayed in the list of configuration profiles.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1246c-206">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="1246c-206">Next Steps</span></span>

[<span data-ttu-id="1246c-207">Defender voor eindpunt configureren voor iOS-functies</span><span class="sxs-lookup"><span data-stu-id="1246c-207">Configure Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
