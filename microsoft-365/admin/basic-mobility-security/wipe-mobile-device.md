---
title: Een mobiel apparaat wissen in Basismobiliteit en Beveiliging
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
description: Gebruik de ingebouwde basismobiliteit en beveiliging om gegevens van geregistreerde apparaten te verwijderen.
ms.openlocfilehash: ddf13ef6627d70128064e2d8bd185203244b12e4
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819806"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a><span data-ttu-id="0eb2f-103">Een mobiel apparaat wissen in Basismobiliteit en Beveiliging</span><span class="sxs-lookup"><span data-stu-id="0eb2f-103">Wipe a mobile device in Basic Mobility and Security</span></span>

<span data-ttu-id="0eb2f-104">U kunt ingebouwde basismobiliteit en beveiliging voor Microsoft 365 gebruiken om alleen organisatiegegevens te verwijderen of om een fabrieksherstel uit te voeren om alle gegevens van een mobiel apparaat te verwijderen en deze terug te zetten naar fabrieksinstellingen.</span><span class="sxs-lookup"><span data-stu-id="0eb2f-104">You can use built-in Basic Mobility and Security for Microsoft 365 to remove only organizational information, or to perform a factory reset to delete all information from a mobile device and restore it to factory settings.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0eb2f-105">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="0eb2f-105">Before you begin</span></span>

<span data-ttu-id="0eb2f-106">Mobiele apparaten kunnen gevoelige organisatiegegevens opslaan en toegang bieden tot de Microsoft 365-resources van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="0eb2f-106">Mobile devices can store sensitive organizational information and provide access to your organization's Microsoft 365 resources.</span></span> <span data-ttu-id="0eb2f-107">Als u de gegevens van uw organisatie wilt beschermen, kunt u fabrieksinstellingen opnieuw instellen of bedrijfsgegevens verwijderen:</span><span class="sxs-lookup"><span data-stu-id="0eb2f-107">To help protect your organization's information, you can do Factory reset or Remove company data:</span></span>

- <span data-ttu-id="0eb2f-108">**Fabrieksinstellingen:** hiermee verwijdert u alle gegevens op het mobiele apparaat van een gebruiker, inclusief geïnstalleerde toepassingen, foto's en persoonlijke gegevens.</span><span class="sxs-lookup"><span data-stu-id="0eb2f-108">**Factory reset**: Deletes all data on a user's mobile device, including installed applications, photos, and personal information.</span></span> <span data-ttu-id="0eb2f-109">Wanneer het wissen is voltooid, wordt het apparaat teruggezet naar de fabrieksinstellingen.</span><span class="sxs-lookup"><span data-stu-id="0eb2f-109">When the wipe is complete, the device is restored to its factory settings.</span></span>

- <span data-ttu-id="0eb2f-110">**Bedrijfsgegevens verwijderen:** verwijdert alleen organisatiegegevens en laat geïnstalleerde toepassingen, foto's en persoonlijke gegevens achter op het mobiele apparaat van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="0eb2f-110">**Remove company data**: Removes only organization data and leaves installed applications, photos, and personal information on a user's mobile device.</span></span>

- <span data-ttu-id="0eb2f-111">**Wanneer een apparaat wordt gewist (Fabrieksinstellingen opnieuw instellen of Bedrijfsgegevens verwijderen),** wordt het apparaat verwijderd uit de lijst met beheerde apparaten.</span><span class="sxs-lookup"><span data-stu-id="0eb2f-111">**When a device is wiped (Factory Reset or Remove Company Data)**, the device is removed from the list of managed devices.</span></span>
    
- <span data-ttu-id="0eb2f-112">**Automatisch een** apparaat opnieuw instellen: U kunt een basisbeleid voor mobiliteit en beveiliging instellen dat een apparaat automatisch in de fabriek opnieuw wordt ingesteld nadat de gebruiker het wachtwoord van het apparaat een bepaald aantal keren niet heeft geprobeerd in te voeren.</span><span class="sxs-lookup"><span data-stu-id="0eb2f-112">**Automatically reset a device**: You can set up a Basic Mobility and Security policy that automatically factory resets a device after the user unsuccessfully tries to enter the device password a specific number of times.</span></span> <span data-ttu-id="0eb2f-113">Volg hiervoor de stappen in [Apparaatbeveiligingsbeleid maken in basismobiliteit en beveiliging.](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="0eb2f-113">To do this, follow the steps in [Create device security policies in basic mobility and security](create-device-security-policies.md).</span></span>
    
- <span data-ttu-id="0eb2f-114">**Als u de gebruikerservaring wilt weten** wanneer u het apparaat wist, zie Wat is de invloed van de gebruiker   [en het apparaat?](#whats-the-user-and-device-impact).</span><span class="sxs-lookup"><span data-stu-id="0eb2f-114">**If you want to know the user experience** when you wipe their device, see  [What's the user and device impact?](#whats-the-user-and-device-impact).</span></span>

## <a name="wipe-a-mobile-device"></a><span data-ttu-id="0eb2f-115">Een mobiel apparaat wissen</span><span class="sxs-lookup"><span data-stu-id="0eb2f-115">Wipe a mobile device</span></span>

1. <span data-ttu-id="0eb2f-116">Ga naar het [Microsoft 365-beheercentrum.](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)</span><span class="sxs-lookup"><span data-stu-id="0eb2f-116">Go to the [Microsoft 365 admin center](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).</span></span>

2. <span data-ttu-id="0eb2f-117">Typ Mobile Device Management in het zoekveld en selecteer **Mobile Device Management** in de lijst met resultaten.</span><span class="sxs-lookup"><span data-stu-id="0eb2f-117">Type Mobile Device Management into the search field, and select **Mobile Device Management** from the list of results.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Optie Voor mobiel beheer van basismobiliteit en secruity":::

3. <span data-ttu-id="0eb2f-119">Selecteer **Apparaten beheren.**</span><span class="sxs-lookup"><span data-stu-id="0eb2f-119">Select **Manage devices**.</span></span>

4. <span data-ttu-id="0eb2f-120">Selecteer het apparaat dat je wilt wissen.</span><span class="sxs-lookup"><span data-stu-id="0eb2f-120">Select the device you want to wipe.</span></span>

5. <span data-ttu-id="0eb2f-121">Selecteer **Beheren.**</span><span class="sxs-lookup"><span data-stu-id="0eb2f-121">Select **Manage**.</span></span>

6. <span data-ttu-id="0eb2f-122">Selecteer het type wissen van op afstand dat je wilt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="0eb2f-122">Select the type of remote wipe you want to do.</span></span>

    - <span data-ttu-id="0eb2f-123">Als u het apparaat volledig wilt wissen en herstellen naar de fabrieksinstellingen, selecteert u **Fabrieksherstel.**</span><span class="sxs-lookup"><span data-stu-id="0eb2f-123">To do a full wipe and restore the device to its factory settings, select **Factory reset**.</span></span>
    - <span data-ttu-id="0eb2f-124">Als u een selectief wissen en alleen microsoft 365-organisatiegegevens wilt verwijderen, selecteert u **Bedrijfsgegevens verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="0eb2f-124">To do a selective wipe and delete only Microsoft 365 organization information, select **Remove company data**.</span></span>
    - <span data-ttu-id="0eb2f-125">Als u het apparaat uit uw organisatie wilt verwijderen, selecteert u **Apparaat verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="0eb2f-125">To remove the device from your organization, select **Remove device**.</span></span>

7. <span data-ttu-id="0eb2f-126">Selecteer **Ja** om te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="0eb2f-126">Select **Yes** to confirm.</span></span>

## <a name="how-do-i-know-it-worked"></a><span data-ttu-id="0eb2f-127">Hoe weet ik of het heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="0eb2f-127">How do I know it worked?</span></span>

<span data-ttu-id="0eb2f-128">U ziet het mobiele apparaat niet meer in de lijst met beheerde apparaten.</span><span class="sxs-lookup"><span data-stu-id="0eb2f-128">You no longer see the mobile device in the list of managed devices.</span></span>

## <a name="why-would-you-want-to-wipe-a-device"></a><span data-ttu-id="0eb2f-129">Waarom wilt u een apparaat wissen?</span><span class="sxs-lookup"><span data-stu-id="0eb2f-129">Why would you want to wipe a device?</span></span>

<span data-ttu-id="0eb2f-130">Veeg een apparaat om deze redenen af:</span><span class="sxs-lookup"><span data-stu-id="0eb2f-130">Wipe a device for these reasons:</span></span>

- <span data-ttu-id="0eb2f-131">Mobiele apparaten, zoals smartphones en tablets, worden steeds voller.</span><span class="sxs-lookup"><span data-stu-id="0eb2f-131">Mobile devices like smartphones and tablets are becoming more full-featured all the time.</span></span> <span data-ttu-id="0eb2f-132">Dit betekent dat het voor uw gebruikers gemakkelijker is om gevoelige bedrijfsgegevens op te slaan, zoals persoonlijke identificatie of vertrouwelijke communicatie, en deze onderweg te openen.</span><span class="sxs-lookup"><span data-stu-id="0eb2f-132">This means it’s easier for your users to store sensitive corporate information such as personal identification or confidential communications and access it on the go.</span></span> <span data-ttu-id="0eb2f-133">Als een van deze mobiele apparaten verloren gaat of wordt gestolen, kan het wissen van het apparaat helpen voorkomen dat de gegevens van uw organisatie in verkeerde handen komen te staan.</span><span class="sxs-lookup"><span data-stu-id="0eb2f-133">If one of these mobile devices is lost or stolen, wiping the device can help prevent your organization’s information from ending up in the wrong hands.</span></span>
- <span data-ttu-id="0eb2f-134">Wanneer een gebruiker de organisatie verlaat met een persoonlijk apparaat dat is geregistreerd voor Basismobiliteit en Beveiliging, kunt u voorkomen dat organisatiegegevens met die gebruiker worden gebruikt door een fabrieksinstellingen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="0eb2f-134">When a user leaves the organization with a personal device that is enrolled in Basic Mobility and Security, you can help prevent organizational information from going with that user by performing a factory reset.</span></span>
- <span data-ttu-id="0eb2f-135">Als uw organisatie mobiele apparaten aan gebruikers levert, moet u mogelijk apparaten af en toe opnieuw toewijzen.</span><span class="sxs-lookup"><span data-stu-id="0eb2f-135">If your organization provides mobile devices to users, you might need to reassign devices from time to time.</span></span> <span data-ttu-id="0eb2f-136">Als u een fabrieksinstellingen op een apparaat doet voordat u deze aan een nieuwe gebruiker toewijst, zorgt u ervoor dat alle gevoelige informatie van de vorige eigenaar wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0eb2f-136">Doing a Factory Reset on a device before assigning it to a new user helps ensures that any sensitive information from the previous owner is deleted.</span></span>

## <a name="whats-the-user-and-device-impact"></a><span data-ttu-id="0eb2f-137">Wat zijn de gevolgen voor de gebruiker en het apparaat?</span><span class="sxs-lookup"><span data-stu-id="0eb2f-137">What's the user and device impact?</span></span>

<span data-ttu-id="0eb2f-138">Het wissen wordt direct naar het mobiele apparaat verzonden en het apparaat is gemarkeerd als niet compatibel in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0eb2f-138">The wipe is sent immediately to the mobile device and the device is marked as not compliant in Azure active directory.</span></span> <span data-ttu-id="0eb2f-139">Terwijl alle gegevens worden verwijderd wanneer een apparaat wordt teruggezet naar fabrieksinstellingen, wordt in de volgende tabel beschreven welke inhoud voor elk apparaattype wordt verwijderd wanneer een apparaat wanneer u bedrijfsgegevens verwijdert.</span><span class="sxs-lookup"><span data-stu-id="0eb2f-139">While all data is removed when a device is reset to factory defaults, the following table describes what content is removed for each device type when a device when you remove company data.</span></span>

|<span data-ttu-id="0eb2f-140">**Inhoudseffect**</span><span class="sxs-lookup"><span data-stu-id="0eb2f-140">**Content impact**</span></span>|<span data-ttu-id="0eb2f-141">**iOS 10 en hoger**</span><span class="sxs-lookup"><span data-stu-id="0eb2f-141">**iOS 10 and later**</span></span>|<span data-ttu-id="0eb2f-142">**Android 5 en hoger**</span><span class="sxs-lookup"><span data-stu-id="0eb2f-142">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0eb2f-143">Microsoft 365-appgegevens worden gewist als het apparaat is beveiligd door intune App Protection-beleid.</span><span class="sxs-lookup"><span data-stu-id="0eb2f-143">Microsoft 365 app data is wiped if the device is protected by Intune App Protection policies.</span></span> <span data-ttu-id="0eb2f-144">De apps worden niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0eb2f-144">The apps aren't removed.</span></span> <span data-ttu-id="0eb2f-145">Voor apparaten die niet zijn beveiligd met MAM-beleid (Mobile Application Management), worden in Outlook en OneDrive geen gegevens in de cache verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0eb2f-145">For devices not protected by Mobile Application Management (MAM) policies, Outlook and OneDrive won't remove cached data.</span></span><br/><span data-ttu-id="0eb2f-146">**Opmerking** Voor het toepassen van Intune App-beveiligingsbeleid moet u een Intune-licentie hebben.</span><span class="sxs-lookup"><span data-stu-id="0eb2f-146">**Note** For applying Intune App protection policies you must have an Intune license.</span></span>|<span data-ttu-id="0eb2f-147">Ja</span><span class="sxs-lookup"><span data-stu-id="0eb2f-147">Yes</span></span>|<span data-ttu-id="0eb2f-148">Ja</span><span class="sxs-lookup"><span data-stu-id="0eb2f-148">Yes</span></span>|
|<span data-ttu-id="0eb2f-149">Beleidsinstellingen die door Basismobiliteit en Beveiliging worden toegepast op apparaten, worden niet meer afgedwongen. gebruikers kunnen de instellingen wijzigen.</span><span class="sxs-lookup"><span data-stu-id="0eb2f-149">Policy settings applied by Basic Mobility and Security to devices are no longer enforced; users can change the settings.</span></span>|<span data-ttu-id="0eb2f-150">Ja</span><span class="sxs-lookup"><span data-stu-id="0eb2f-150">Yes</span></span>|<span data-ttu-id="0eb2f-151">Ja</span><span class="sxs-lookup"><span data-stu-id="0eb2f-151">Yes</span></span>|
|<span data-ttu-id="0eb2f-152">E-mailprofielen die zijn gemaakt door Basismobiliteit en Beveiliging worden verwijderd en e-mail in de cache op het apparaat wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0eb2f-152">Email profiles created by Basic Mobility and Security are removed and cached email on the device is deleted.</span></span>|<span data-ttu-id="0eb2f-153">Ja</span><span class="sxs-lookup"><span data-stu-id="0eb2f-153">Yes</span></span>|<span data-ttu-id="0eb2f-154">N.v.t.</span><span class="sxs-lookup"><span data-stu-id="0eb2f-154">N/A</span></span>|
>[!NOTE]
><span data-ttu-id="0eb2f-155">De bedrijfsportal-app is beschikbaar in de App Store voor iOS en de Play Store voor Android-apparaten.</span><span class="sxs-lookup"><span data-stu-id="0eb2f-155">Company Portal app is available at the App Store for iOS and the Play Store for Android devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0eb2f-156">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="0eb2f-156">Related topics</span></span>

[<span data-ttu-id="0eb2f-157">Basic Mobility en Security instellen</span><span class="sxs-lookup"><span data-stu-id="0eb2f-157">Set up Basic Mobility and Security</span></span>](set-up.md)
