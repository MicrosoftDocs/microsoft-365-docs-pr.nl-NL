---
title: Microsoft Defender voor eindpunt op macOS-apparaten registreren bij Jamf Pro
description: Microsoft Defender voor eindpunt op macOS-apparaten registreren bij Jamf Pro
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0fa0db3ba85ff003d91b43d06c709ab66c37ce02
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933095"
---
# <a name="enroll-microsoft-defender-for-endpoint-on-macos-devices-into-jamf-pro"></a><span data-ttu-id="ad267-104">Microsoft Defender voor eindpunt op macOS-apparaten registreren bij Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="ad267-104">Enroll Microsoft Defender for Endpoint on macOS devices into Jamf Pro</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ad267-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="ad267-105">**Applies to:**</span></span>
- [<span data-ttu-id="ad267-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="ad267-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ad267-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ad267-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ad267-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="ad267-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ad267-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="ad267-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="enroll-macos-devices"></a><span data-ttu-id="ad267-110">MacOS-apparaten registreren</span><span class="sxs-lookup"><span data-stu-id="ad267-110">Enroll macOS devices</span></span>

<span data-ttu-id="ad267-111">Er zijn meerdere methoden om u te laten inschrijven bij JamF.</span><span class="sxs-lookup"><span data-stu-id="ad267-111">There are multiple methods of getting enrolled to JamF.</span></span>

<span data-ttu-id="ad267-112">In dit artikel worden twee methoden beschreven:</span><span class="sxs-lookup"><span data-stu-id="ad267-112">This article will guide you on two methods:</span></span>

- [<span data-ttu-id="ad267-113">Methode 1: Uitnodigingen voor inschrijving</span><span class="sxs-lookup"><span data-stu-id="ad267-113">Method 1:  Enrollment Invitations</span></span>](#enrollment-method-1-enrollment-invitations)
- [<span data-ttu-id="ad267-114">Methode 2: Inschrijving vooraf</span><span class="sxs-lookup"><span data-stu-id="ad267-114">Method 2:  Prestage Enrollments</span></span>](#enrollment-method-2-prestage-enrollments)

<span data-ttu-id="ad267-115">Zie Over [computerinschrijving](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html)voor een volledige lijst.</span><span class="sxs-lookup"><span data-stu-id="ad267-115">For a complete list, see [About Computer Enrollment](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html).</span></span>


## <a name="enrollment-method-1-enrollment-invitations"></a><span data-ttu-id="ad267-116">Inschrijvingsmethode 1: Uitnodigingen voor inschrijving</span><span class="sxs-lookup"><span data-stu-id="ad267-116">Enrollment Method 1: Enrollment Invitations</span></span>

1. <span data-ttu-id="ad267-117">Navigeer in het dashboard Van Jamf Pro naar **Uitnodigingen voor inschrijving.**</span><span class="sxs-lookup"><span data-stu-id="ad267-117">In the Jamf Pro dashboard, navigate to **Enrollment invitations**.</span></span>

    ![Afbeelding van configuratie-instellingen1](images/a347307458d6a9bbfa88df7dbe15398f.png)

2. <span data-ttu-id="ad267-119">Selecteer **+ Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="ad267-119">Select **+ New**.</span></span>

    ![Een close-up van een automatisch gegenereerde logobeschrijving](images/b6c7ad56d50f497c38fc14c1e315456c.png)

3. <span data-ttu-id="ad267-121">Voer **in Geadresseerden opgeven voor** de > onder **E-mailadressen** het e-mailadres(es) van de geadresseerden in.</span><span class="sxs-lookup"><span data-stu-id="ad267-121">In **Specify Recipients for the Invitation** > under **Email Addresses** enter the e-mail address(es) of the recipients.</span></span>

    ![Afbeelding van configuratie-instellingen2](images/718b9d609f9f77c8b13ba88c4c0abe5d.png)

    ![Afbeelding van configuratie-instellingen3](images/ae3597247b6bc7c5347cf56ab1e820c0.png)

    <span data-ttu-id="ad267-124">Bijvoorbeeld: janedoe@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad267-124">For example: janedoe@contoso.com</span></span>

    ![Afbeelding van configuratie-instellingen4](images/4922c0fcdde4c7f73242b13bf5e35c19.png)

4. <span data-ttu-id="ad267-126">Configureer het bericht voor de uitnodiging.</span><span class="sxs-lookup"><span data-stu-id="ad267-126">Configure the message for the invitation.</span></span>

    ![Afbeelding van configuratie-instellingen5](images/ce580aec080512d44a37ff8e82e5c2ac.png)

    ![Afbeelding van configuratie-instellingen6](images/5856b765a6ce677caacb130ca36b1a62.png)

    ![Afbeelding van configuratie-instellingen7](images/3ced5383a6be788486d89d407d042f28.png)

    ![Afbeelding van configuratie-instellingen8](images/54be9c6ed5b24cebe628dc3cd9ca4089.png)

## <a name="enrollment-method-2-prestage-enrollments"></a><span data-ttu-id="ad267-131">Inschrijvingsmethode 2: Inschrijving vooraf</span><span class="sxs-lookup"><span data-stu-id="ad267-131">Enrollment Method 2: Prestage Enrollments</span></span>

1. <span data-ttu-id="ad267-132">Navigeer in het Dashboard van Jamf Pro naar **Inschrijvingen vooraf.**</span><span class="sxs-lookup"><span data-stu-id="ad267-132">In the Jamf Pro dashboard, navigate to **Prestage enrollments**.</span></span>

    ![Afbeelding van configuratie-instellingen9](images/6fd0cb2bbb0e60a623829c91fd0826ab.png)

2. <span data-ttu-id="ad267-134">Volg de instructies in [Computer PreStage Enrollments](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html).</span><span class="sxs-lookup"><span data-stu-id="ad267-134">Follow the instructions in [Computer PreStage Enrollments](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html).</span></span>

## <a name="enroll-macos-device"></a><span data-ttu-id="ad267-135">MacOS-apparaat registreren</span><span class="sxs-lookup"><span data-stu-id="ad267-135">Enroll macOS device</span></span>

1. <span data-ttu-id="ad267-136">Selecteer **Doorgaan** en installeer het CA-certificaat in een **venster Systeemvoorkeuren.**</span><span class="sxs-lookup"><span data-stu-id="ad267-136">Select **Continue** and install the CA certificate from a **System Preferences** window.</span></span>

    ![Afbeelding van de registratie van Jamf Pro1](images/jamfpro-ca-certificate.png)

2. <span data-ttu-id="ad267-138">Nadat het CA-certificaat is geïnstalleerd, gaat u terug naar het browservenster en **selecteert u Doorgaan** en installeert u het MDM-profiel.</span><span class="sxs-lookup"><span data-stu-id="ad267-138">Once CA certificate is installed, return to the browser window and select **Continue** and install the MDM profile.</span></span> 

    ![Afbeelding van de registratie van Jamf Pro2](images/jamfpro-install-mdm-profile.png)

3. <span data-ttu-id="ad267-140">Selecteer **Toestaan** om te downloaden van JAMF.</span><span class="sxs-lookup"><span data-stu-id="ad267-140">Select **Allow** to downloads from JAMF.</span></span>

    ![Afbeelding van de registratie van Jamf Pro3](images/jamfpro-download.png)

4. <span data-ttu-id="ad267-142">Selecteer **Doorgaan om** door te gaan met de installatie van het MDM-profiel.</span><span class="sxs-lookup"><span data-stu-id="ad267-142">Select **Continue** to proceed with the MDM Profile installation.</span></span> 

    ![Afbeelding van de registratie van Jamf Pro4](images/jamfpro-install-mdm.png)

5. <span data-ttu-id="ad267-144">Selecteer **Doorgaan** om het MDM-profiel te installeren.</span><span class="sxs-lookup"><span data-stu-id="ad267-144">Select **Continue** to install the MDM Profile.</span></span>

    ![Afbeelding van de registratie van Jamf Pro5](images/jamfpro-mdm-unverified.png)

6. <span data-ttu-id="ad267-146">Selecteer **Doorgaan**  om de configuratie te voltooien.</span><span class="sxs-lookup"><span data-stu-id="ad267-146">Select **Continue**  to complete the configuration.</span></span> 

    ![Afbeelding van de registratie van Jamf Pro6](images/jamfpro-mdm-profile.png)
