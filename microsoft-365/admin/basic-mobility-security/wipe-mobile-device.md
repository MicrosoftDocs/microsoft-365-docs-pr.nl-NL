---
title: Een mobiel apparaat wissen in eenvoudige mobiliteit en beveiliging
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
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Gebruik ingebouwde basis mobiliteit en beveiliging om informatie van ingeschreven apparaten te verwijderen.
ms.openlocfilehash: 4d854c7d4d81cd0b49ec7f81a49de5478b08f049
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336815"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a><span data-ttu-id="32d62-103">Een mobiel apparaat wissen in eenvoudige mobiliteit en beveiliging</span><span class="sxs-lookup"><span data-stu-id="32d62-103">Wipe a mobile device in Basic Mobility and Security</span></span>

<span data-ttu-id="32d62-104">U kunt ingebouwde mobiliteit en beveiliging voor Microsoft 365 gebruiken om alleen organisatiegegevens te verwijderen, of om de fabrieksinstellingen te herstellen om alle gegevens van een mobiel apparaat te verwijderen en de fabrieksinstellingen te herstellen.</span><span class="sxs-lookup"><span data-stu-id="32d62-104">You can use built-in Basic Mobility and Security for Microsoft 365 to remove only organizational information, or to perform a factory reset to delete all information from a mobile device and restore it to factory settings.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="32d62-105">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="32d62-105">Before you begin</span></span>

<span data-ttu-id="32d62-106">Op mobiele apparaten kunnen gevoelige organisatiegegevens worden opgeslagen en krijgt u toegang tot de Microsoft 365-bronnen van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="32d62-106">Mobile devices can store sensitive organizational information and provide access to your organization's Microsoft 365 resources.</span></span> <span data-ttu-id="32d62-107">Als u de gegevens van uw organisatie wilt beschermen, kunt u de fabrieks gegevens opnieuw instellen of verwijderen:</span><span class="sxs-lookup"><span data-stu-id="32d62-107">To help protect your organization's information, you can do Factory reset or Remove company data:</span></span>
    
- <span data-ttu-id="32d62-108">**Fabrieksinstellingen**: Hiermee verwijdert u alle gegevens op het mobiele apparaat van een gebruiker, waaronder geïnstalleerde toepassingen, Foto's en persoonlijke gegevens.</span><span class="sxs-lookup"><span data-stu-id="32d62-108">**Factory reset**: Deletes all data on a user's mobile device, including installed applications, photos, and personal information.</span></span> <span data-ttu-id="32d62-109">Wanneer het wissen is voltooid, wordt het apparaat hersteld naar de fabrieksinstellingen.</span><span class="sxs-lookup"><span data-stu-id="32d62-109">When the wipe is complete, the device is restored to its factory settings.</span></span>
    
- <span data-ttu-id="32d62-110">**Bedrijfsgegevens verwijderen**: Hiermee verwijdert u alleen bedrijfsgegevens en laat u geïnstalleerde toepassingen, Foto's en persoonlijke gegevens op het mobiele apparaat van een gebruiker ongewijzigd.</span><span class="sxs-lookup"><span data-stu-id="32d62-110">**Remove company data**: Removes only organization data and leaves installed applications, photos, and personal information on a user's mobile device.</span></span>   

- <span data-ttu-id="32d62-111">**Wanneer een apparaat wordt gewist (Factory opnieuw instellen of verwijderen van bedrijfsgegevens)**, wordt het apparaat verwijderd uit de lijst met beheerde apparaten.</span><span class="sxs-lookup"><span data-stu-id="32d62-111">**When a device is wiped (Factory Reset or Remove Company Data)**, the device is removed from the list of managed devices.</span></span>
    
- <span data-ttu-id="32d62-112">**Automatisch een apparaat opnieuw instellen**: u kunt een basisniveau voor mobiliteit en beveiliging instellen waarmee automatisch de instelling van een apparaat wordt hersteld nadat de gebruiker het wachtwoord van het apparaat een bepaald aantal keren probeert in te voeren.</span><span class="sxs-lookup"><span data-stu-id="32d62-112">**Automatically reset a device**: You can set up a Basic Mobility and Security policy that automatically factory resets a device after the user unsuccessfully tries to enter the device password a specific number of times.</span></span> <span data-ttu-id="32d62-113">Als u dit wilt doen, volgt u de stappen in [beveiligingsbeleid voor apparaat maken in eenvoudige mobiliteit en beveiliging](create-device-security-policies-in-basic-mmobility-and-security.md).</span><span class="sxs-lookup"><span data-stu-id="32d62-113">To do this, follow the steps in [Create device security policies in basic mobility and security](create-device-security-policies-in-basic-mmobility-and-security.md).</span></span>
    
- <span data-ttu-id="32d62-114">**Als u wilt weten wat de gebruikerservaring** zijn wanneer u zijn of haar apparaat wist, raadpleegt u  [Wat zijn de gevolgen voor gebruiker en apparaat?](#whats-the-user-and-device-impact).</span><span class="sxs-lookup"><span data-stu-id="32d62-114">**If you want to know the user experience** when you wipe their device, see  [What's the user and device impact?](#whats-the-user-and-device-impact).</span></span>   

## <a name="wipe-a-mobile-device"></a><span data-ttu-id="32d62-115">Een mobiel apparaat wissen</span><span class="sxs-lookup"><span data-stu-id="32d62-115">Wipe a mobile device</span></span>

1. <span data-ttu-id="32d62-116">Ga naar het [Microsoft 365-Beheercentrum](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).</span><span class="sxs-lookup"><span data-stu-id="32d62-116">Go to the [Microsoft 365 admin center](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).</span></span>
    
2. <span data-ttu-id="32d62-117">Typ Mobile Device Management in het zoekveld en selecteer **Mobile Device Management** in de lijst met resultaten.</span><span class="sxs-lookup"><span data-stu-id="32d62-117">Type Mobile Device Management into the search field, and select **Mobile Device Management** from the list of results.</span></span> 

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Basisopties voor mobiele apparaten en Secruity":::

3. <span data-ttu-id="32d62-119">Selecteer **apparaten beheren**.</span><span class="sxs-lookup"><span data-stu-id="32d62-119">Select **Manage devices**.</span></span>

4. <span data-ttu-id="32d62-120">Selecteer het apparaat dat u wilt wissen.</span><span class="sxs-lookup"><span data-stu-id="32d62-120">Select the device you want to wipe.</span></span>

5. <span data-ttu-id="32d62-121">Selecteer **beheren**.</span><span class="sxs-lookup"><span data-stu-id="32d62-121">Select **Manage**.</span></span>

6. <span data-ttu-id="32d62-122">Selecteer het type wissen op afstand dat u wilt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="32d62-122">Select the type of remote wipe you want to do.</span></span>

    - <span data-ttu-id="32d62-123">Als u volledig wilt wissen en de fabrieksinstellingen van het apparaat wilt herstellen, selecteert u **fabrieksinstellingen opnieuw instellen**.</span><span class="sxs-lookup"><span data-stu-id="32d62-123">To do a full wipe and restore the device to its factory settings, select **Factory reset**.</span></span>
    - <span data-ttu-id="32d62-124">Als u selectief wilt wissen en alleen Microsoft 365-organisatiegegevens wilt verwijderen, selecteert u **bedrijfsgegevens verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="32d62-124">To do a selective wipe and delete only Microsoft 365 organization information, select **Remove company data**.</span></span>
    - <span data-ttu-id="32d62-125">Als u het apparaat wilt verwijderen uit uw organisatie, selecteert u **apparaat verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="32d62-125">To remove the device from your organization, select **Remove device**.</span></span>

7. <span data-ttu-id="32d62-126">Selecteer **Ja** om te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="32d62-126">Select **Yes** to confirm.</span></span>

## <a name="how-do-i-know-it-worked"></a><span data-ttu-id="32d62-127">Hoe weet ik dat het werkt?</span><span class="sxs-lookup"><span data-stu-id="32d62-127">How do I know it worked?</span></span>

<span data-ttu-id="32d62-128">Het mobiele apparaat in de lijst met beheerde apparaten wordt niet meer weergegeven.</span><span class="sxs-lookup"><span data-stu-id="32d62-128">You no longer see the mobile device in the list of managed devices.</span></span>

## <a name="why-would-you-want-to-wipe-a-device"></a><span data-ttu-id="32d62-129">Waarom zou u een apparaat willen wissen?</span><span class="sxs-lookup"><span data-stu-id="32d62-129">Why would you want to wipe a device?</span></span>

<span data-ttu-id="32d62-130">Een apparaat wissen om de volgende redenen:</span><span class="sxs-lookup"><span data-stu-id="32d62-130">Wipe a device for these reasons:</span></span>

- <span data-ttu-id="32d62-131">Mobiele apparaten zoals smartphones en tablets worden altijd langer uitgebreid.</span><span class="sxs-lookup"><span data-stu-id="32d62-131">Mobile devices like smartphones and tablets are becoming more full-featured all the time.</span></span> <span data-ttu-id="32d62-132">Dit houdt in dat uw gebruikers gevoelige bedrijfsinformatie, zoals een persoonlijke identificatie of vertrouwelijke communicatie, bewaren en overal ter verduidelijking kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="32d62-132">This means it’s easier for your users to store sensitive corporate information such as personal identification or confidential communications and access it on the go.</span></span> <span data-ttu-id="32d62-133">Als een van deze mobiele apparaten verloren gaat of wordt gestolen, kunt u het apparaat wissen, zodat de gegevens van uw organisatie niet op de juiste basis worden beëindigd.</span><span class="sxs-lookup"><span data-stu-id="32d62-133">If one of these mobile devices is lost or stolen, wiping the device can help prevent your organization’s information from ending up in the wrong hands.</span></span>
- <span data-ttu-id="32d62-134">Wanneer een gebruiker de organisatie verlaat met een persoonlijk apparaat dat is geregistreerd voor basis mobiliteit en beveiliging, kunt u het voorkomen dat bedrijfsgegevens met die gebruiker worden gebruikt door de fabrieksinstellingen opnieuw in te voeren.</span><span class="sxs-lookup"><span data-stu-id="32d62-134">When a user leaves the organization with a personal device that is enrolled in Basic Mobility and Security, you can help prevent organizational information from going with that user by performing a factory reset.</span></span>
- <span data-ttu-id="32d62-135">Als uw organisatie mobiele apparaten biedt aan gebruikers, moet u mogelijk uw apparaten van tijd tot tijd opnieuw toewijzen.</span><span class="sxs-lookup"><span data-stu-id="32d62-135">If your organization provides mobile devices to users, you might need to reassign devices from time to time.</span></span> <span data-ttu-id="32d62-136">Door een fabriek opnieuw in te stellen op een apparaat voordat u deze aan een nieuwe gebruiker toewijst, zorgt u ervoor dat eventuele gevoelige informatie van de vorige eigenaar wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="32d62-136">Doing a Factory Reset on a device before assigning it to a new user helps ensures that any sensitive information from the previous owner is deleted.</span></span>

## <a name="whats-the-user-and-device-impact"></a><span data-ttu-id="32d62-137">Wat zijn de gevolgen voor gebruiker en apparaat?</span><span class="sxs-lookup"><span data-stu-id="32d62-137">What's the user and device impact?</span></span>

<span data-ttu-id="32d62-138">Het wissen wordt onmiddellijk naar het mobiele apparaat verzonden en het apparaat is gemarkeerd als niet-compatibel in azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="32d62-138">The wipe is sent immediately to the mobile device and the device is marked as not compliant in Azure active directory.</span></span> <span data-ttu-id="32d62-139">Wanneer alle gegevens worden verwijderd wanneer een apparaat opnieuw is ingesteld op de fabrieksinstellingen, wordt in de volgende tabel beschreven welke inhoud wordt verwijderd voor elk type apparaat wanneer u bedrijfsgegevens verwijdert.</span><span class="sxs-lookup"><span data-stu-id="32d62-139">While all data is removed when a device is reset to factory defaults, the following table describes what content is removed for each device type when a device when you remove company data.</span></span>

|<span data-ttu-id="32d62-140">**Inhouds dispace**</span><span class="sxs-lookup"><span data-stu-id="32d62-140">**Content impace**</span></span>|<span data-ttu-id="32d62-141">**iOS 10 en hoger**</span><span class="sxs-lookup"><span data-stu-id="32d62-141">**iOS 10 and later**</span></span>|<span data-ttu-id="32d62-142">**Android 5 en hoger**</span><span class="sxs-lookup"><span data-stu-id="32d62-142">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="32d62-143">Microsoft 365-app-gegevens worden gewist als het apparaat is beveiligd met de beveiligings beleidsregels van de intune-app.</span><span class="sxs-lookup"><span data-stu-id="32d62-143">Microsoft 365 app data is wiped if the device is protected by Intune App Protection policies.</span></span> <span data-ttu-id="32d62-144">De apps worden niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="32d62-144">The apps aren't removed.</span></span> <span data-ttu-id="32d62-145">Voor apparaten die niet zijn beveiligd met een Mobile Application Management-beleid (MAM), worden in Outlook en OneDrive geen gegevens in de cache verwijderd.</span><span class="sxs-lookup"><span data-stu-id="32d62-145">For devices not protected by Mobile Application Management (MAM) policies, Outlook and OneDrive won't remove cached data.</span></span><br/><span data-ttu-id="32d62-146">**Opmerking** Voor het toepassen van een intune-beveiligingsbeleid moet u een intune-licentie hebben.</span><span class="sxs-lookup"><span data-stu-id="32d62-146">**Note** For applying Intune App protection policies you must have an Intune license.</span></span>|<span data-ttu-id="32d62-147">Ja</span><span class="sxs-lookup"><span data-stu-id="32d62-147">Yes</span></span>|<span data-ttu-id="32d62-148">Ja</span><span class="sxs-lookup"><span data-stu-id="32d62-148">Yes</span></span>|
|<span data-ttu-id="32d62-149">Beleidsinstellingen die zijn toegepast op basis mobiliteit en beveiliging op apparaten, worden niet meer afgedwongen. gebruikers kunnen de instellingen wijzigen.</span><span class="sxs-lookup"><span data-stu-id="32d62-149">Policy settings applied by Basic Mobility and Security to devices are no longer enforced; users can change the settings.</span></span>|<span data-ttu-id="32d62-150">Ja</span><span class="sxs-lookup"><span data-stu-id="32d62-150">Yes</span></span>|<span data-ttu-id="32d62-151">Ja</span><span class="sxs-lookup"><span data-stu-id="32d62-151">Yes</span></span>|
|<span data-ttu-id="32d62-152">E-mail profielen die zijn gemaakt door basis mobiliteit en beveiliging, worden verwijderd en e-mail in de cache op het apparaat wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="32d62-152">Email profiles created by Basic Mobility and Security are removed and cached email on the device is deleted.</span></span>|<span data-ttu-id="32d62-153">Ja</span><span class="sxs-lookup"><span data-stu-id="32d62-153">Yes</span></span>|<span data-ttu-id="32d62-154">N.v.t.</span><span class="sxs-lookup"><span data-stu-id="32d62-154">N/A</span></span>|
>[!NOTE] 
><span data-ttu-id="32d62-155">De bedrijfs portal-app is beschikbaar in de App Store voor iOS en de Play Store voor Android-apparaten.</span><span class="sxs-lookup"><span data-stu-id="32d62-155">Company Portal app is available at the App Store for iOS and the Play Store for Android devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="32d62-156">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="32d62-156">Related topics</span></span>

[<span data-ttu-id="32d62-157">Eenvoudige mobiliteit en beveiliging instellen</span><span class="sxs-lookup"><span data-stu-id="32d62-157">Set up Basic Mobility and Security</span></span>](set-up-basic-mobility-and-security.md)