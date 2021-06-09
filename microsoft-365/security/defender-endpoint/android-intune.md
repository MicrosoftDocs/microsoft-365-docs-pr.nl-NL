---
title: Microsoft Defender voor Eindpunt op Android implementeren via Microsoft Intune
description: Hier wordt beschreven hoe u Microsoft Defender voor Eindpunt implementeert op Android met Microsoft Intune
keywords: microsoft, defender, Microsoft Defender for Endpoint, mde, android, installation, deploy, uninstallation,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1935533ad924b7589bdfee6f3119fb667fb60b73
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841508"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-android-with-microsoft-intune"></a><span data-ttu-id="8c665-104">Microsoft Defender voor Eindpunt op Android implementeren via Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="8c665-104">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8c665-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8c665-105">**Applies to:**</span></span>
- [<span data-ttu-id="8c665-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="8c665-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8c665-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8c665-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8c665-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="8c665-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8c665-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="8c665-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="8c665-110">Meer informatie over het implementeren van Defender voor Eindpunt op Android op Intune-bedrijfsportal geregistreerde apparaten.</span><span class="sxs-lookup"><span data-stu-id="8c665-110">Learn how to deploy Defender for Endpoint on Android on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="8c665-111">Zie Uw apparaat  [registreren](/mem/intune/user-help/enroll-device-android-company-portal)voor meer informatie over intune-apparaatinschrijving.</span><span class="sxs-lookup"><span data-stu-id="8c665-111">For more information about Intune device enrollment, see  [Enroll your device](/mem/intune/user-help/enroll-device-android-company-portal).</span></span>

> [!NOTE]
> <span data-ttu-id="8c665-112">**Defender voor Eindpunt op Android is nu beschikbaar op [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span><span class="sxs-lookup"><span data-stu-id="8c665-112">**Defender for Endpoint on Android is now available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span></span> <br>
> <span data-ttu-id="8c665-113">U kunt vanuit Intune verbinding maken met Google Play om de Defender voor Endpoint-app te implementeren in de registratiemodi Apparaatbeheerder en Android Enterprise.</span><span class="sxs-lookup"><span data-stu-id="8c665-113">You can connect to Google Play from Intune to deploy Defender for Endpoint app across Device Administrator and Android Enterprise entrollment modes.</span></span>
<span data-ttu-id="8c665-114">Updates voor de app worden automatisch via Google Play.</span><span class="sxs-lookup"><span data-stu-id="8c665-114">Updates to the app are automatic via Google Play.</span></span>

## <a name="deploy-on-device-administrator-enrolled-devices"></a><span data-ttu-id="8c665-115">Implementeren op apparaten die zijn geregistreerd door apparaatbeheerder</span><span class="sxs-lookup"><span data-stu-id="8c665-115">Deploy on Device Administrator enrolled devices</span></span>

<span data-ttu-id="8c665-116">**Defender voor eindpunt implementeren op Android op Intune-bedrijfsportal - Apparatenbeheerder die zijn geregistreerd**</span><span class="sxs-lookup"><span data-stu-id="8c665-116">**Deploy Defender for Endpoint on Android on Intune Company Portal - Device Administrator enrolled devices**</span></span>

<span data-ttu-id="8c665-117">Meer informatie over het implementeren van Defender voor Eindpunt op Android op Intune-bedrijfsportal - Apparaatbeheerder ingeschreven apparaten.</span><span class="sxs-lookup"><span data-stu-id="8c665-117">Learn how to deploy Defender for Endpoint on Android on Intune Company Portal - Device Administrator enrolled devices.</span></span> 

### <a name="add-as-android-store-app"></a><span data-ttu-id="8c665-118">Toevoegen als Android Store-app</span><span class="sxs-lookup"><span data-stu-id="8c665-118">Add as Android store app</span></span>

1. <span data-ttu-id="8c665-119">Ga [Microsoft Endpoint Manager in het beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) naar **Apps** \> **Android Apps** Android \> **\> Store-app toevoegen** en kies **Selecteren.**</span><span class="sxs-lookup"><span data-stu-id="8c665-119">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) , go to **Apps** \> **Android Apps** \> **Add \> Android store app** and choose **Select**.</span></span>

   ![Afbeelding van Microsoft Endpoint Manager-beheercentrum android store-toepassing toevoegen](images/mda-addandroidstoreapp.png)

2. <span data-ttu-id="8c665-121">Voer op **de pagina App** toevoegen en in de sectie *App-informatie* het volgende in:</span><span class="sxs-lookup"><span data-stu-id="8c665-121">On the **Add app** page and in the *App Information* section enter:</span></span> 

   - <span data-ttu-id="8c665-122">**Naam**</span><span class="sxs-lookup"><span data-stu-id="8c665-122">**Name**</span></span> 
   - <span data-ttu-id="8c665-123">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="8c665-123">**Description**</span></span>
   - <span data-ttu-id="8c665-124">**Publisher** als Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8c665-124">**Publisher** as Microsoft.</span></span>
   - <span data-ttu-id="8c665-125">**App Store URL** as https://play.google.com/store/apps/details?id=com.microsoft.scmx (Defender for Endpoint app Google Play Store URL)</span><span class="sxs-lookup"><span data-stu-id="8c665-125">**App store URL** as https://play.google.com/store/apps/details?id=com.microsoft.scmx (Defender for Endpoint app Google Play Store URL)</span></span> 

   <span data-ttu-id="8c665-126">Andere velden zijn optioneel.</span><span class="sxs-lookup"><span data-stu-id="8c665-126">Other fields are optional.</span></span> <span data-ttu-id="8c665-127">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="8c665-127">Select **Next**.</span></span>

   ![Afbeelding van Microsoft Endpoint Manager-beheercentrum app-informatie toevoegen](images/mda-addappinfo.png)

3. <span data-ttu-id="8c665-129">Ga in *de sectie Opdrachten* naar de sectie **Vereist** en selecteer **Groep toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="8c665-129">In the *Assignments* section, go to the **Required** section and select **Add group.**</span></span> <span data-ttu-id="8c665-130">Vervolgens kunt u de gebruikersgroep(s) kiezen die u wilt richten op Defender voor Eindpunt in de Android-app.</span><span class="sxs-lookup"><span data-stu-id="8c665-130">You can then choose the user group(s) that you would like to target Defender for Endpoint on Android app.</span></span> <span data-ttu-id="8c665-131">Kies **Selecteren** en vervolgens **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="8c665-131">Choose **Select** and then **Next**.</span></span>

    >[!NOTE]
    ><span data-ttu-id="8c665-132">De geselecteerde gebruikersgroep moet bestaan uit intune geregistreerde gebruikers.</span><span class="sxs-lookup"><span data-stu-id="8c665-132">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]

    > ![Afbeelding van de Microsoft Endpoint Manager geselecteerde gebruikersgroepen in het beheercentrum](images/363bf30f7d69a94db578e8af0ddd044b.png)

4. <span data-ttu-id="8c665-134">Controleer in **de sectie Controleren+Maken** of alle ingevoerde gegevens juist zijn en selecteer vervolgens **Maken.**</span><span class="sxs-lookup"><span data-stu-id="8c665-134">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

    <span data-ttu-id="8c665-135">Over een paar minuten wordt de App Defender voor Eindpunt gemaakt en wordt er een melding weergegeven in de rechterbovenhoek van de pagina.</span><span class="sxs-lookup"><span data-stu-id="8c665-135">In a few moments, the Defender for Endpoint app would be created successfully, and a notification would show up at the top-right corner of the page.</span></span>

    ![Afbeelding van Microsoft Endpoint Manager melding van het beheercentrum van de Defender-eindpunt-app](images/86cbe56f88bb6e93e9c63303397fc24f.png)

5. <span data-ttu-id="8c665-137">Selecteer op de pagina met app-informatie die wordt weergegeven in de sectie Monitor de **status** apparaatinstallatie om te controleren of de installatie van het apparaat is voltooid. </span><span class="sxs-lookup"><span data-stu-id="8c665-137">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8c665-138">![Afbeelding van Microsoft Endpoint Manager installatie van het beheercentrum](images/513cf5d59eaaef5d2b5bc122715b5844.png)</span><span class="sxs-lookup"><span data-stu-id="8c665-138">![Image of Microsoft Endpoint Manager Admin Center device install](images/513cf5d59eaaef5d2b5bc122715b5844.png)</span></span>

### <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="8c665-139">De onboarding- en controlestatus voltooien</span><span class="sxs-lookup"><span data-stu-id="8c665-139">Complete onboarding and check status</span></span>

1. <span data-ttu-id="8c665-140">Zodra Defender voor Eindpunt op Android is geïnstalleerd op het apparaat, ziet u het app-pictogram.</span><span class="sxs-lookup"><span data-stu-id="8c665-140">Once Defender for Endpoint on Android has been installed on the device, you'll see the app icon.</span></span>

    ![Pictogram op mobiel apparaat](images/7cf9311ad676ec5142002a4d0c2323ca.jpg)

2. <span data-ttu-id="8c665-142">Tik op het pictogram van de Microsoft Defender voor endpoint-app en volg de instructies op het scherm om de onboarding van de app te voltooien.</span><span class="sxs-lookup"><span data-stu-id="8c665-142">Tap the Microsoft Defender for Endpoint app icon and follow the on-screen instructions to complete onboarding the app.</span></span> <span data-ttu-id="8c665-143">De details omvatten de acceptatie door eindgebruikers van Android-machtigingen die vereist zijn door Defender voor Eindpunt op Android.</span><span class="sxs-lookup"><span data-stu-id="8c665-143">The details include end-user acceptance of Android permissions required by Defender for Endpoint on Android.</span></span>

3. <span data-ttu-id="8c665-144">Na succesvolle onboarding wordt het apparaat weergegeven in de lijst Apparaten in Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="8c665-144">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    ![Afbeelding van apparaat in defender voor eindpuntportal](images/9fe378a1dce0f143005c3aa53d8c4f51.png)

## <a name="deploy-on-android-enterprise-enrolled-devices"></a><span data-ttu-id="8c665-146">Implementeren op geregistreerde Android Enterprise-apparaten</span><span class="sxs-lookup"><span data-stu-id="8c665-146">Deploy on Android Enterprise enrolled devices</span></span>

<span data-ttu-id="8c665-147">Defender voor Eindpunt op Android ondersteunt geregistreerde Android Enterprise-apparaten.</span><span class="sxs-lookup"><span data-stu-id="8c665-147">Defender for Endpoint on Android supports Android Enterprise enrolled devices.</span></span>

<span data-ttu-id="8c665-148">Zie [Inschrijvingsopties](/mem/intune/enrollment/android-enroll)voor meer informatie over de inschrijvingsopties die worden ondersteund door Intune.</span><span class="sxs-lookup"><span data-stu-id="8c665-148">For more information on the enrollment options supported by Intune, see [Enrollment Options](/mem/intune/enrollment/android-enroll).</span></span>

<span data-ttu-id="8c665-149">**Op dit moment worden persoonlijke apparaten met een werkprofiel en volledig beheerde gebruikersapparaatinschrijvingen van het bedrijf ondersteund voor implementatie.**</span><span class="sxs-lookup"><span data-stu-id="8c665-149">**Currently, Personally owned devices with work profile and Corporate-owned fully managed user device enrollments are supported for deployment.**</span></span>

## <a name="add-microsoft-defender-for-endpoint-on-android-as-a-managed-google-play-app"></a><span data-ttu-id="8c665-150">Microsoft Defender voor eindpunt toevoegen aan Android als een beheerde Google Play-app</span><span class="sxs-lookup"><span data-stu-id="8c665-150">Add Microsoft Defender for Endpoint on Android as a Managed Google Play app</span></span>

<span data-ttu-id="8c665-151">Volg de onderstaande stappen om de App Microsoft Defender voor Eindpunt toe te voegen aan uw beheerde Google Play.</span><span class="sxs-lookup"><span data-stu-id="8c665-151">Follow the steps below to add Microsoft Defender for Endpoint app into your managed Google Play.</span></span>

1. <span data-ttu-id="8c665-152">Ga [Microsoft Endpoint Manager beheercentrum naar](https://go.microsoft.com/fwlink/?linkid=2109431) **Apps** \> **Android Apps** \> **toevoegen** en selecteer **Beheerde Google Play-app.**</span><span class="sxs-lookup"><span data-stu-id="8c665-152">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) , go to **Apps** \> **Android Apps** \> **Add** and select **Managed Google Play app**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8c665-153">![Afbeelding van Microsoft Endpoint Manager beheerde google Play-beheercentrum](images/579ff59f31f599414cedf63051628b2e.png)</span><span class="sxs-lookup"><span data-stu-id="8c665-153">![Image of Microsoft Endpoint Manager admin center managed google play](images/579ff59f31f599414cedf63051628b2e.png)</span></span>

2. <span data-ttu-id="8c665-154">Ga op de beheerde Google Play-pagina die vervolgens wordt geladen naar het zoekvak en zoek **Microsoft Defender.**</span><span class="sxs-lookup"><span data-stu-id="8c665-154">On your managed Google Play page that loads subsequently, go to the search box and lookup **Microsoft Defender.**</span></span> <span data-ttu-id="8c665-155">Uw zoekopdracht moet de Microsoft Defender voor Eindpunt-app weergeven in uw beheerde Google Play.</span><span class="sxs-lookup"><span data-stu-id="8c665-155">Your search should display the Microsoft Defender for Endpoint app in your Managed Google Play.</span></span> <span data-ttu-id="8c665-156">Klik op de Microsoft Defender voor Eindpunt-app in het zoekresultaat Apps.</span><span class="sxs-lookup"><span data-stu-id="8c665-156">Click on the Microsoft Defender for Endpoint app from the Apps search result.</span></span>

    ![Afbeelding van Microsoft Endpoint Manager zoeken in apps in het beheercentrum](images/0f79cb37900b57c3e2bb0effad1c19cb.png)

3. <span data-ttu-id="8c665-158">Op de pagina App-beschrijving die hierna wordt weergegeven, kunt u app-details zien op Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="8c665-158">In the App description page that comes up next, you should be able to see app details on Defender for Endpoint.</span></span> <span data-ttu-id="8c665-159">Controleer de informatie op de pagina en selecteer **goedkeuren.**</span><span class="sxs-lookup"><span data-stu-id="8c665-159">Review the information on the page and then select **Approve**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8c665-160">![Een schermafbeelding van een beheerde Google Play](images/07e6d4119f265037e3b80a20a73b856f.png)</span><span class="sxs-lookup"><span data-stu-id="8c665-160">![A screenshot of a Managed Google Play](images/07e6d4119f265037e3b80a20a73b856f.png)</span></span>

4. <span data-ttu-id="8c665-161">U krijgt de machtigingen die Door Defender voor Eindpunt worden gekregen om het te laten werken.</span><span class="sxs-lookup"><span data-stu-id="8c665-161">You'll be presented with the permissions that Defender for Endpoint obtains for it to work.</span></span> <span data-ttu-id="8c665-162">Controleer ze en selecteer **goedkeuren.**</span><span class="sxs-lookup"><span data-stu-id="8c665-162">Review them and then select **Approve**.</span></span>

    ![Een schermafbeelding van de goedkeuring van de Preview-app van Defender voor eindpunt](images/206b3d954f06cc58b3466fb7a0bd9f74.png)

5. <span data-ttu-id="8c665-164">U ziet de pagina Goedkeuringsinstellingen.</span><span class="sxs-lookup"><span data-stu-id="8c665-164">You'll be presented with the Approval settings page.</span></span> <span data-ttu-id="8c665-165">De pagina bevestigt uw voorkeur voor het verwerken van nieuwe app-machtigingen die Defender voor Eindpunt op Android kan vragen.</span><span class="sxs-lookup"><span data-stu-id="8c665-165">The page confirms your preference to handle new app permissions that Defender for Endpoint on Android might ask.</span></span> <span data-ttu-id="8c665-166">Bekijk de keuzes en selecteer de gewenste optie.</span><span class="sxs-lookup"><span data-stu-id="8c665-166">Review the choices and select your preferred option.</span></span> <span data-ttu-id="8c665-167">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="8c665-167">Select **Done**.</span></span>

    <span data-ttu-id="8c665-168">Beheerde Google Play selecteert standaard Goedgekeurd blijven wanneer *app nieuwe machtigingen aanvraagt*</span><span class="sxs-lookup"><span data-stu-id="8c665-168">By default, managed Google Play selects *Keep approved when app requests new permissions*</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8c665-169">![Afbeelding van het tabblad Meldingen](images/ffecfdda1c4df14148f1526c22cc0236.png)</span><span class="sxs-lookup"><span data-stu-id="8c665-169">![Image of notifications tab](images/ffecfdda1c4df14148f1526c22cc0236.png)</span></span>

6. <span data-ttu-id="8c665-170">Nadat de machtigingen voor het verwerken van de selectie zijn gemaakt, **selecteert** u Synchroniseren om Microsoft Defender voor Eindpunt te synchroniseren met uw lijst met apps.</span><span class="sxs-lookup"><span data-stu-id="8c665-170">After the permissions handling selection is made, select **Sync** to sync Microsoft Defender for Endpoint to your apps list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8c665-171">![Afbeelding van synchronisatiepagina](images/34e6b9a0dae125d085c84593140180ed.png)</span><span class="sxs-lookup"><span data-stu-id="8c665-171">![Image of sync page](images/34e6b9a0dae125d085c84593140180ed.png)</span></span>

7. <span data-ttu-id="8c665-172">De synchronisatie wordt binnen enkele minuten voltooid.</span><span class="sxs-lookup"><span data-stu-id="8c665-172">The sync will complete in a few minutes.</span></span>

    ![Afbeelding van Android-app](images/9fc07ffc150171f169dc6e57fe6f1c74.png)

8. <span data-ttu-id="8c665-174">Selecteer de **knop** Vernieuwen in het scherm met Android-apps en Microsoft Defender voor Eindpunt moet zichtbaar zijn in de lijst met apps.</span><span class="sxs-lookup"><span data-stu-id="8c665-174">Select the **Refresh** button in the Android apps screen and Microsoft Defender for Endpoint should be visible in the apps list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8c665-175">![Afbeelding van lijst met Android-apps](images/fa4ac18a6333335db3775630b8e6b353.png)</span><span class="sxs-lookup"><span data-stu-id="8c665-175">![Image of list of Android apps](images/fa4ac18a6333335db3775630b8e6b353.png)</span></span>

9. <span data-ttu-id="8c665-176">Defender voor Eindpunt ondersteunt app-configuratiebeleid voor beheerde apparaten via Intune.</span><span class="sxs-lookup"><span data-stu-id="8c665-176">Defender for Endpoint supports App configuration policies for managed devices via Intune.</span></span> <span data-ttu-id="8c665-177">Deze mogelijkheid kan worden gebruikt voor autogrant toepasselijke Android-machtigingen, zodat de eindgebruiker deze machtigingen niet hoeft te accepteren.</span><span class="sxs-lookup"><span data-stu-id="8c665-177">This capability can be leveraged to autogrant applicable Android permission(s), so the end user does not need to accept these permission(s).</span></span>

    1. <span data-ttu-id="8c665-178">Ga op **de pagina Apps** naar **Beleidsbeleid > app-configuratiebeleid > Apparaten > toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="8c665-178">In the **Apps** page, go to **Policy > App configuration policies > Add > Managed devices**.</span></span>

       ![Afbeelding van Microsoft Endpoint Manager beheerde android-apparaten in het beheercentrum](images/android-mem.png)

    1. <span data-ttu-id="8c665-180">Voer op **de pagina App-configuratiebeleid** maken de volgende details in:</span><span class="sxs-lookup"><span data-stu-id="8c665-180">In the **Create app configuration policy** page, enter the following details:</span></span>
    
        - <span data-ttu-id="8c665-181">Naam: Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="8c665-181">Name: Microsoft Defender for Endpoint.</span></span>
        - <span data-ttu-id="8c665-182">Kies **Android Enterprise** als platform.</span><span class="sxs-lookup"><span data-stu-id="8c665-182">Choose **Android Enterprise** as platform.</span></span>
        - <span data-ttu-id="8c665-183">Kies **Alleen werkprofiel als** profieltype.</span><span class="sxs-lookup"><span data-stu-id="8c665-183">Choose **Work Profile only** as Profile Type.</span></span>
        - <span data-ttu-id="8c665-184">Klik **op App selecteren,** kies **Microsoft Defender ATP**, selecteer **OK** en vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="8c665-184">Click **Select App**, choose **Microsoft Defender ATP**, select **OK** and then **Next**.</span></span>
    
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="8c665-185">![Afbeelding van beleidspagina voor app-configuratie maken](images/android-create-app.png)</span><span class="sxs-lookup"><span data-stu-id="8c665-185">![Image of create app configuration policy page](images/android-create-app.png)</span></span>

    1. <span data-ttu-id="8c665-186">Ga op **Instellingen** pagina naar de sectie Machtigingen en klik op Toevoegen om de lijst met ondersteunde machtigingen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="8c665-186">In the **Settings** page, go to the Permissions section click on Add to view the list of supported permissions.</span></span> <span data-ttu-id="8c665-187">Selecteer in de sectie Machtigingen toevoegen de volgende machtigingen:</span><span class="sxs-lookup"><span data-stu-id="8c665-187">In the Add Permissions section, select the following permissions:</span></span>

       - <span data-ttu-id="8c665-188">Externe opslag (gelezen)</span><span class="sxs-lookup"><span data-stu-id="8c665-188">External storage (read)</span></span>
       - <span data-ttu-id="8c665-189">Externe opslag (schrijven)</span><span class="sxs-lookup"><span data-stu-id="8c665-189">External storage (write)</span></span>

       <span data-ttu-id="8c665-190">Selecteer vervolgens **OK**.</span><span class="sxs-lookup"><span data-stu-id="8c665-190">Then select **OK**.</span></span>

       > [!div class="mx-imgBorder"]
      > <span data-ttu-id="8c665-191">![Afbeelding van android-configuratiebeleid voor apps maken](images/android-create-app-config.png)</span><span class="sxs-lookup"><span data-stu-id="8c665-191">![Image of android create app configuration policy](images/android-create-app-config.png)</span></span>

    1. <span data-ttu-id="8c665-192">U ziet nu zowel de weergegeven machtigingen als nu kunt u beide  automatisch toevoegen door autogrant te kiezen in de vervolgkeuzelijst Machtigingstoestand en vervolgens **Volgende te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="8c665-192">You should now see both the permissions listed and now you can autogrant both by choosing autogrant in the **Permission state** drop-down and then select **Next**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="8c665-193">![Afbeelding van android auto grant create app configuration policy](images/android-auto-grant.png)</span><span class="sxs-lookup"><span data-stu-id="8c665-193">![Image of android auto grant create app configuration policy](images/android-auto-grant.png)</span></span>

    1. <span data-ttu-id="8c665-194">Selecteer op **de pagina** Toewijzingen de gebruikersgroep waaraan dit app-config-beleid zou zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="8c665-194">In the **Assignments** page, select the user group to which this app config policy would be assigned to.</span></span> <span data-ttu-id="8c665-195">Klik **op Groepen selecteren om de** betreffende groep op te nemen en te selecteren en vervolgens Volgende te **selecteren.**</span><span class="sxs-lookup"><span data-stu-id="8c665-195">Click **Select groups to include** and selecting the applicable group and then selecting **Next**.</span></span>  <span data-ttu-id="8c665-196">De groep die hier is geselecteerd, is meestal dezelfde groep waaraan u Microsoft Defender voor Endpoint Android-app zou toewijzen.</span><span class="sxs-lookup"><span data-stu-id="8c665-196">The group selected here is usually the same group to which you would assign Microsoft Defender for Endpoint Android app.</span></span> 

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="8c665-197">![Afbeelding van het configuratiebeleid voor apps maken](images/android-select-group.png)</span><span class="sxs-lookup"><span data-stu-id="8c665-197">![Image of the create app configuration policy](images/android-select-group.png)</span></span>
    

     1. <span data-ttu-id="8c665-198">Bekijk alle **informatie op de** pagina Controleren + Maken die hierna wordt weergegeven en selecteer vervolgens **Maken.**</span><span class="sxs-lookup"><span data-stu-id="8c665-198">In the **Review + Create** page that comes up next, review all the information and then select **Create**.</span></span> <br>
    
        <span data-ttu-id="8c665-199">Het app-configuratiebeleid voor Defender voor Eindpunt dat de opslagmachtigingen automatisch wordt toegewezen, is nu toegewezen aan de geselecteerde gebruikersgroep.</span><span class="sxs-lookup"><span data-stu-id="8c665-199">The app configuration policy for Defender for Endpoint autogranting the storage permission is now assigned to the selected user group.</span></span>

        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="8c665-200">![Afbeelding van android-revisie maak beleid voor app-config](images/android-review-create.png)</span><span class="sxs-lookup"><span data-stu-id="8c665-200">![Image of android review create app config policy](images/android-review-create.png)</span></span>


10. <span data-ttu-id="8c665-201">Selecteer **Microsoft Defender ATP** app in de lijst \>  \> **Eigenschappentoewijzingen** \> **bewerken**.</span><span class="sxs-lookup"><span data-stu-id="8c665-201">Select **Microsoft Defender ATP** app in the list \> **Properties** \> **Assignments** \> **Edit**.</span></span>

    ![Afbeelding van lijst met apps](images/mda-properties.png)


11. <span data-ttu-id="8c665-203">Wijs de app toe als *een vereiste* app aan een gebruikersgroep.</span><span class="sxs-lookup"><span data-stu-id="8c665-203">Assign the app as a *Required* app to a user group.</span></span> <span data-ttu-id="8c665-204">Het wordt automatisch geïnstalleerd in het *werkprofiel* tijdens de volgende synchronisatie van het apparaat via Bedrijfsportal app.</span><span class="sxs-lookup"><span data-stu-id="8c665-204">It is automatically installed in the *work profile* during the next sync of the device via Company Portal app.</span></span> <span data-ttu-id="8c665-205">U kunt deze opdracht uitvoeren door naar de groep Vereist *toevoegen* te \> **gaan,** de gebruikersgroep te selecteren en op Selecteren **te klikken.**</span><span class="sxs-lookup"><span data-stu-id="8c665-205">This assignment can be done by navigating to the *Required* section \> **Add group,** selecting the user group and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8c665-206">![Afbeelding van de pagina Toepassing bewerken](images/ea06643280075f16265a596fb9a96042.png)</span><span class="sxs-lookup"><span data-stu-id="8c665-206">![Image of edit application page](images/ea06643280075f16265a596fb9a96042.png)</span></span>


12. <span data-ttu-id="8c665-207">Bekijk op **de pagina** Toepassing bewerken alle informatie die hierboven is ingevoerd.</span><span class="sxs-lookup"><span data-stu-id="8c665-207">In the **Edit Application** page, review all the information that was entered above.</span></span> <span data-ttu-id="8c665-208">Selecteer vervolgens **Controleren + Opslaan en** vervolgens opnieuw opslaan **om** de toewijzing te starten.</span><span class="sxs-lookup"><span data-stu-id="8c665-208">Then select **Review + Save** and then **Save** again to commence assignment.</span></span>

### <a name="auto-setup-of-always-on-vpn"></a><span data-ttu-id="8c665-209">Auto Setup of Always-on VPN</span><span class="sxs-lookup"><span data-stu-id="8c665-209">Auto Setup of Always-on VPN</span></span> 
<span data-ttu-id="8c665-210">Defender voor Eindpunt ondersteunt apparaatconfiguratiebeleid voor beheerde apparaten via Intune.</span><span class="sxs-lookup"><span data-stu-id="8c665-210">Defender for Endpoint supports Device configuration policies for managed devices via Intune.</span></span> <span data-ttu-id="8c665-211">Deze mogelijkheid kan worden gebruikt voor het automatisch instellen van **Always-on VPN** op geregistreerde Android Enterprise-apparaten, zodat de eindgebruiker geen VPN-service hoeft in te stellen tijdens onboarding.</span><span class="sxs-lookup"><span data-stu-id="8c665-211">This capability can be leveraged to **Auto setup of Always-on VPN** on Android Enterprise enrolled devices, so the end user does not need to set up VPN service while onboarding.</span></span>
1.  <span data-ttu-id="8c665-212">Selecteer **op Apparaten** **configuratieprofielen**  >  **Profielplatform** maken Android  >    >  **Enterprise** Selecteer **Apparaatbeperkingen** onder een van de volgende opties, op basis van het type apparaatinschrijving</span><span class="sxs-lookup"><span data-stu-id="8c665-212">On **Devices**, select **Configuration Profiles** > **Create Profile** > **Platform** > **Android Enterprise** Select **Device restrictions** under one of the following, based on your device enrollment type</span></span> 
- <span data-ttu-id="8c665-213">**Volledig beheerd, toegewezen en Corporate-Owned werkprofiel**</span><span class="sxs-lookup"><span data-stu-id="8c665-213">**Fully Managed, Dedicated, and Corporate-Owned Work Profile**</span></span>
- <span data-ttu-id="8c665-214">**Persoonlijk werkprofiel**</span><span class="sxs-lookup"><span data-stu-id="8c665-214">**Personally owned Work Profile**</span></span>

<span data-ttu-id="8c665-215">Selecteer **Maken**.</span><span class="sxs-lookup"><span data-stu-id="8c665-215">Select **Create**.</span></span>
 
   > ![Afbeelding van het configuratieprofiel Van apparaten maken](images/1autosetupofvpn.png)
    
2. <span data-ttu-id="8c665-217">**Configuratie Instellingen** Geef een **naam en** een beschrijving **op om** het configuratieprofiel uniek te identificeren.</span><span class="sxs-lookup"><span data-stu-id="8c665-217">**Configuration Settings** Provide a **Name** and a **Description** to uniquely identify the configuration profile.</span></span> 

   > ![Afbeelding van het configuratieprofiel Naam en beschrijving van apparaten](images/2autosetupofvpn.png)
   
 3. <span data-ttu-id="8c665-219">Selecteer **Connectiviteit en** configureer VPN:</span><span class="sxs-lookup"><span data-stu-id="8c665-219">Select **Connectivity** and configure VPN:</span></span>
- <span data-ttu-id="8c665-220">**Always-on VPN inschakelen** Stel een VPN-client in het werkprofiel in om waar mogelijk automatisch verbinding te maken en opnieuw verbinding te maken met de VPN.</span><span class="sxs-lookup"><span data-stu-id="8c665-220">Enable **Always-on VPN** Setup a VPN client in the work profile to automatically connect and reconnect to the VPN whenever possible.</span></span> <span data-ttu-id="8c665-221">Er kan slechts één VPN-client worden geconfigureerd voor altijd-on VPN op een bepaald apparaat, dus zorg ervoor dat er niet meer dan één always-on VPN-beleid is geïmplementeerd op één apparaat.</span><span class="sxs-lookup"><span data-stu-id="8c665-221">Only one VPN client can be configured for always-on VPN on a given device, so be sure to have no more than one always-on VPN policy deployed to a single device.</span></span> 
- <span data-ttu-id="8c665-222">Selecteer **Aangepast** in de vervolgkeuzelijst vpn-client Aangepaste VPN is in dit geval Defender voor Endpoint VPN, dat wordt gebruikt om de webbeveiligingsfunctie te bieden.</span><span class="sxs-lookup"><span data-stu-id="8c665-222">Select **Custom** in VPN client dropdown list Custom VPN in this case is Defender for Endpoint VPN which is used to provide the Web Protection feature.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="8c665-223">Microsoft Defender voor Endpoint-app moet zijn geïnstalleerd op het apparaat van de gebruiker, zodat deze VPN automatisch kan worden ingesteld.</span><span class="sxs-lookup"><span data-stu-id="8c665-223">Microsoft Defender for Endpoint app must be installed on user’s device, in order to functioning of auto setup of this VPN.</span></span>

- <span data-ttu-id="8c665-224">Voer **pakket-id** in van de Microsoft Defender voor Eindpunt-app in de Google Play Store.</span><span class="sxs-lookup"><span data-stu-id="8c665-224">Enter **Package ID** of the Microsoft Defender for Endpoint app in Google Play store.</span></span> <span data-ttu-id="8c665-225">Voor de URL van de Defender-app https://play.google.com/store/apps/details?id=com.microsoft.scmx is Package ID **com.microsoft.scmx**</span><span class="sxs-lookup"><span data-stu-id="8c665-225">For the Defender app URL https://play.google.com/store/apps/details?id=com.microsoft.scmx, Package ID is **com.microsoft.scmx**</span></span>  
- <span data-ttu-id="8c665-226">**Vergrendelingsmodus** Niet geconfigureerd (standaard)</span><span class="sxs-lookup"><span data-stu-id="8c665-226">**Lockdown mode** Not configured (Default)</span></span> 

     ![Afbeelding van configuratieprofiel apparaten inschakelen Always-on VPN](images/3autosetupofvpn.png)
   
4. <span data-ttu-id="8c665-228">**Toewijzing** Selecteer op  **de pagina**   Toewijzingen de gebruikersgroep waaraan dit app-config-beleid zou zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="8c665-228">**Assignment** In the **Assignments** page, select the user group to which this app config policy would be assigned to.</span></span> <span data-ttu-id="8c665-229">Klik **op Groepen selecteren** om de betreffende groep op te nemen en te selecteren en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="8c665-229">Click **Select groups** to include and selecting the applicable group and then click **Next**.</span></span> <span data-ttu-id="8c665-230">De groep die hier is geselecteerd, is meestal dezelfde groep waaraan u Microsoft Defender voor Endpoint Android-app zou toewijzen.</span><span class="sxs-lookup"><span data-stu-id="8c665-230">The group selected here is usually the same group to which you would assign Microsoft Defender for Endpoint Android app.</span></span> 

     ![Afbeelding van toewijzing van het configuratieprofiel van apparaten](images/4autosetupofvpn.png)

5. <span data-ttu-id="8c665-232">Bekijk alle **informatie op de** pagina Controleren + Maken die hierna wordt weergegeven en selecteer vervolgens **Maken.**</span><span class="sxs-lookup"><span data-stu-id="8c665-232">In the **Review + Create** page that comes up next, review all the information and then select **Create**.</span></span> <span data-ttu-id="8c665-233">Het apparaatconfiguratieprofiel is nu toegewezen aan de geselecteerde gebruikersgroep.</span><span class="sxs-lookup"><span data-stu-id="8c665-233">The device configuration profile is now assigned to the selected user group.</span></span>    

    ![Afbeelding van het configuratieprofiel van apparaten Controleren en maken](images/5autosetupofvpn.png)

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="8c665-235">De onboarding- en controlestatus voltooien</span><span class="sxs-lookup"><span data-stu-id="8c665-235">Complete onboarding and check status</span></span>

1. <span data-ttu-id="8c665-236">Bevestig de installatiestatus van Microsoft Defender voor Eindpunt op Android door op de **status apparaatinstallatie te klikken.**</span><span class="sxs-lookup"><span data-stu-id="8c665-236">Confirm the installation status of Microsoft Defender for Endpoint on Android by clicking on the **Device Install Status**.</span></span> <span data-ttu-id="8c665-237">Controleer of het apparaat hier wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8c665-237">Verify that the device is displayed here.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8c665-238">![Afbeelding van de installatiestatus van het apparaat](images/900c0197aa59f9b7abd762ab2b32e80c.png)</span><span class="sxs-lookup"><span data-stu-id="8c665-238">![Image of device installation status](images/900c0197aa59f9b7abd762ab2b32e80c.png)</span></span>


2. <span data-ttu-id="8c665-239">Op het apparaat kunt u de onboarding-status valideren door naar het **werkprofiel te gaan.**</span><span class="sxs-lookup"><span data-stu-id="8c665-239">On the device, you can validate the onboarding status by going to the **work profile**.</span></span> <span data-ttu-id="8c665-240">Controleer of Defender voor Eindpunt beschikbaar is en dat u bent geregistreerd voor de apparaten van persoonlijk **eigendom met werkprofiel.**</span><span class="sxs-lookup"><span data-stu-id="8c665-240">Confirm that Defender for Endpoint is available and that you are enrolled to the **Personally owned devices with work profile**.</span></span>  <span data-ttu-id="8c665-241">Als u bent geregistreerd bij een volledig beheerd gebruikersapparaat van het **bedrijf,** hebt u één profiel op het apparaat waar u kunt bevestigen dat Defender voor Eindpunt beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="8c665-241">If you are enrolled to a **Corporate-owned, fully managed user device**, you will have a single profile on the device where you can confirm that Defender for Endpoint is available.</span></span>

    ![Afbeelding van app op mobiel apparaat](images/c2e647fc8fa31c4f2349c76f2497bc0e.png)

3. <span data-ttu-id="8c665-243">Wanneer de app is geïnstalleerd, opent u de app en accepteert u de machtigingen en moet uw onboarding succesvol zijn.</span><span class="sxs-lookup"><span data-stu-id="8c665-243">When the app is installed, open the app and accept the permissions and then your onboarding should be successful.</span></span>

    ![Afbeelding van mobiel apparaat met Microsoft Defender voor Eindpunt-app](images/mda-devicesafe.png)

4. <span data-ttu-id="8c665-245">In dit stadium is het apparaat met succes onboarded op Defender for Endpoint op Android.</span><span class="sxs-lookup"><span data-stu-id="8c665-245">At this stage the device is successfully onboarded onto Defender for Endpoint on Android.</span></span> <span data-ttu-id="8c665-246">U kunt dit controleren op de [Microsoft Defender-beveiligingscentrum](https://securitycenter.microsoft.com) door naar de pagina Apparaten **te** navigeren.</span><span class="sxs-lookup"><span data-stu-id="8c665-246">You can verify this on the [Microsoft Defender Security Center](https://securitycenter.microsoft.com) by navigating to the **Devices** page.</span></span>

    ![Afbeelding van microsoft Defender voor eindpuntportal](images/9fe378a1dce0f143005c3aa53d8c4f51.png)


## <a name="related-topics"></a><span data-ttu-id="8c665-248">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="8c665-248">Related topics</span></span>
- [<span data-ttu-id="8c665-249">Overzicht van Microsoft Defender voor Eindpunt op Android</span><span class="sxs-lookup"><span data-stu-id="8c665-249">Overview of Microsoft Defender for Endpoint on Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="8c665-250">Microsoft Defender voor Eindpunt in Android-functies configureren</span><span class="sxs-lookup"><span data-stu-id="8c665-250">Configure Microsoft Defender for Endpoint on Android features</span></span>](android-configure.md)
