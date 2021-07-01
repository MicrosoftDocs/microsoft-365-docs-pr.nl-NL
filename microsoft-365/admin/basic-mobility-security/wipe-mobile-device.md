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
ms.openlocfilehash: c3cc547ce5e135ccdabf9a09b0d572f1b2530f47
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228145"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a><span data-ttu-id="ed259-103">Een mobiel apparaat wissen in Basismobiliteit en Beveiliging</span><span class="sxs-lookup"><span data-stu-id="ed259-103">Wipe a mobile device in Basic Mobility and Security</span></span>

<span data-ttu-id="ed259-104">U kunt ingebouwde basismobiliteit en beveiliging voor Microsoft 365 gebruiken om alleen organisatiegegevens te verwijderen of om een fabrieksherstel uit te voeren om alle gegevens van een mobiel apparaat te verwijderen en deze terug te zetten naar fabrieksinstellingen.</span><span class="sxs-lookup"><span data-stu-id="ed259-104">You can use built-in Basic Mobility and Security for Microsoft 365 to remove only organizational information, or to perform a factory reset to delete all information from a mobile device and restore it to factory settings.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ed259-105">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="ed259-105">Before you begin</span></span>

<span data-ttu-id="ed259-106">Mobiele apparaten kunnen gevoelige organisatiegegevens opslaan en toegang bieden tot de Microsoft 365 uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ed259-106">Mobile devices can store sensitive organizational information and provide access to your organization's Microsoft 365 resources.</span></span> <span data-ttu-id="ed259-107">Als u de gegevens van uw organisatie wilt beschermen, kunt u fabrieksinstellingen opnieuw instellen of bedrijfsgegevens verwijderen:</span><span class="sxs-lookup"><span data-stu-id="ed259-107">To help protect your organization's information, you can do Factory reset or Remove company data:</span></span>

- <span data-ttu-id="ed259-108">**Fabrieksinstellingen:** hiermee verwijdert u alle gegevens op het mobiele apparaat van een gebruiker, inclusief geïnstalleerde toepassingen, foto's en persoonlijke gegevens.</span><span class="sxs-lookup"><span data-stu-id="ed259-108">**Factory reset**: Deletes all data on a user's mobile device, including installed applications, photos, and personal information.</span></span> <span data-ttu-id="ed259-109">Wanneer het wissen is voltooid, wordt het apparaat teruggezet naar de fabrieksinstellingen.</span><span class="sxs-lookup"><span data-stu-id="ed259-109">When the wipe is complete, the device is restored to its factory settings.</span></span>

- <span data-ttu-id="ed259-110">**Bedrijfsgegevens verwijderen:** verwijdert alleen organisatiegegevens en laat geïnstalleerde toepassingen, foto's en persoonlijke gegevens achter op het mobiele apparaat van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="ed259-110">**Remove company data**: Removes only organization data and leaves installed applications, photos, and personal information on a user's mobile device.</span></span>

- <span data-ttu-id="ed259-111">**Wanneer een apparaat wordt gewist (Fabrieksinstellingen opnieuw instellen of Bedrijfsgegevens verwijderen),** wordt het apparaat verwijderd uit de lijst met beheerde apparaten.</span><span class="sxs-lookup"><span data-stu-id="ed259-111">**When a device is wiped (Factory Reset or Remove Company Data)**, the device is removed from the list of managed devices.</span></span>
    
- <span data-ttu-id="ed259-112">**Automatisch een** apparaat opnieuw instellen: U kunt een basisbeleid voor mobiliteit en beveiliging instellen dat een apparaat automatisch in de fabriek opnieuw wordt ingesteld nadat de gebruiker het wachtwoord van het apparaat een bepaald aantal keren niet heeft geprobeerd in te voeren.</span><span class="sxs-lookup"><span data-stu-id="ed259-112">**Automatically reset a device**: You can set up a Basic Mobility and Security policy that automatically factory resets a device after the user unsuccessfully tries to enter the device password a specific number of times.</span></span> <span data-ttu-id="ed259-113">Volg hiervoor de stappen in [Apparaatbeveiligingsbeleid maken in basismobiliteit en beveiliging.](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="ed259-113">To do this, follow the steps in [Create device security policies in basic mobility and security](create-device-security-policies.md).</span></span>
    
- <span data-ttu-id="ed259-114">**Als u de gebruikerservaring wilt weten** wanneer u het apparaat wist, zie Wat is de invloed van de gebruiker   [en het apparaat?](#whats-the-user-and-device-impact).</span><span class="sxs-lookup"><span data-stu-id="ed259-114">**If you want to know the user experience** when you wipe their device, see  [What's the user and device impact?](#whats-the-user-and-device-impact).</span></span>

## <a name="wipe-a-mobile-device"></a><span data-ttu-id="ed259-115">Een mobiel apparaat wissen</span><span class="sxs-lookup"><span data-stu-id="ed259-115">Wipe a mobile device</span></span>

1. <span data-ttu-id="ed259-116">Ga naar de [Microsoft 365-beheercentrum.](../../admin/admin-overview/about-the-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="ed259-116">Go to the [Microsoft 365 admin center](../../admin/admin-overview/about-the-admin-center.md).</span></span>

2. <span data-ttu-id="ed259-117">Typ Mobile Device Management in het zoekveld en selecteer **Mobile Device Management** in de lijst met resultaten.</span><span class="sxs-lookup"><span data-stu-id="ed259-117">Type Mobile Device Management into the search field, and select **Mobile Device Management** from the list of results.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Optie Voor mobiel beheer van basismobiliteit en secruity":::

3. <span data-ttu-id="ed259-119">Selecteer **Apparaten beheren.**</span><span class="sxs-lookup"><span data-stu-id="ed259-119">Select **Manage devices**.</span></span>

4. <span data-ttu-id="ed259-120">Selecteer het apparaat dat je wilt wissen.</span><span class="sxs-lookup"><span data-stu-id="ed259-120">Select the device you want to wipe.</span></span>

5. <span data-ttu-id="ed259-121">Selecteer **Beheren.**</span><span class="sxs-lookup"><span data-stu-id="ed259-121">Select **Manage**.</span></span>

6. <span data-ttu-id="ed259-122">Selecteer het type wissen van op afstand dat je wilt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="ed259-122">Select the type of remote wipe you want to do.</span></span>

    - <span data-ttu-id="ed259-123">Als u het apparaat volledig wilt wissen en herstellen naar de fabrieksinstellingen, selecteert u **Fabrieksherstel.**</span><span class="sxs-lookup"><span data-stu-id="ed259-123">To do a full wipe and restore the device to its factory settings, select **Factory reset**.</span></span>
    - <span data-ttu-id="ed259-124">Als u een selectief wissen en alleen Microsoft 365 organisatiegegevens wilt verwijderen, **selecteert u Bedrijfsgegevens verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="ed259-124">To do a selective wipe and delete only Microsoft 365 organization information, select **Remove company data**.</span></span>
    - <span data-ttu-id="ed259-125">Als u het apparaat uit uw organisatie wilt verwijderen, selecteert u **Apparaat verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="ed259-125">To remove the device from your organization, select **Remove device**.</span></span>

7. <span data-ttu-id="ed259-126">Selecteer **Ja** om te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="ed259-126">Select **Yes** to confirm.</span></span>

## <a name="how-do-i-know-it-worked"></a><span data-ttu-id="ed259-127">Hoe weet ik of het heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="ed259-127">How do I know it worked?</span></span>

<span data-ttu-id="ed259-128">U ziet het mobiele apparaat niet meer in de lijst met beheerde apparaten.</span><span class="sxs-lookup"><span data-stu-id="ed259-128">You no longer see the mobile device in the list of managed devices.</span></span>

## <a name="why-would-you-want-to-wipe-a-device"></a><span data-ttu-id="ed259-129">Waarom wilt u een apparaat wissen?</span><span class="sxs-lookup"><span data-stu-id="ed259-129">Why would you want to wipe a device?</span></span>

<span data-ttu-id="ed259-130">Veeg een apparaat om deze redenen af:</span><span class="sxs-lookup"><span data-stu-id="ed259-130">Wipe a device for these reasons:</span></span>

- <span data-ttu-id="ed259-131">Mobiele apparaten, zoals smartphones en tablets, worden steeds voller.</span><span class="sxs-lookup"><span data-stu-id="ed259-131">Mobile devices like smartphones and tablets are becoming more full-featured all the time.</span></span> <span data-ttu-id="ed259-132">Dit betekent dat het voor uw gebruikers gemakkelijker is om gevoelige bedrijfsgegevens op te slaan, zoals persoonlijke identificatie of vertrouwelijke communicatie, en deze onderweg te openen.</span><span class="sxs-lookup"><span data-stu-id="ed259-132">This means it’s easier for your users to store sensitive corporate information such as personal identification or confidential communications and access it on the go.</span></span> <span data-ttu-id="ed259-133">Als een van deze mobiele apparaten verloren gaat of wordt gestolen, kan het wissen van het apparaat helpen voorkomen dat de gegevens van uw organisatie in verkeerde handen komen te staan.</span><span class="sxs-lookup"><span data-stu-id="ed259-133">If one of these mobile devices is lost or stolen, wiping the device can help prevent your organization’s information from ending up in the wrong hands.</span></span>
- <span data-ttu-id="ed259-134">Wanneer een gebruiker de organisatie verlaat met een persoonlijk apparaat dat is geregistreerd voor Basismobiliteit en Beveiliging, kunt u voorkomen dat organisatiegegevens met die gebruiker worden gebruikt door een fabrieksinstellingen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="ed259-134">When a user leaves the organization with a personal device that is enrolled in Basic Mobility and Security, you can help prevent organizational information from going with that user by performing a factory reset.</span></span>
- <span data-ttu-id="ed259-135">Als uw organisatie mobiele apparaten aan gebruikers levert, moet u mogelijk apparaten af en toe opnieuw toewijzen.</span><span class="sxs-lookup"><span data-stu-id="ed259-135">If your organization provides mobile devices to users, you might need to reassign devices from time to time.</span></span> <span data-ttu-id="ed259-136">Als u een fabrieksinstellingen op een apparaat doet voordat u deze aan een nieuwe gebruiker toewijst, zorgt u ervoor dat alle gevoelige informatie van de vorige eigenaar wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ed259-136">Doing a Factory Reset on a device before assigning it to a new user helps ensures that any sensitive information from the previous owner is deleted.</span></span>

## <a name="whats-the-user-and-device-impact"></a><span data-ttu-id="ed259-137">Wat zijn de gevolgen voor de gebruiker en het apparaat?</span><span class="sxs-lookup"><span data-stu-id="ed259-137">What's the user and device impact?</span></span>

<span data-ttu-id="ed259-138">Het wissen wordt direct naar het mobiele apparaat verzonden en het apparaat is gemarkeerd als niet compatibel in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ed259-138">The wipe is sent immediately to the mobile device and the device is marked as not compliant in Azure active directory.</span></span> <span data-ttu-id="ed259-139">Terwijl alle gegevens worden verwijderd wanneer een apparaat wordt teruggezet naar fabrieksinstellingen, wordt in de volgende tabel beschreven welke inhoud voor elk apparaattype wordt verwijderd wanneer een apparaat wanneer u bedrijfsgegevens verwijdert.</span><span class="sxs-lookup"><span data-stu-id="ed259-139">While all data is removed when a device is reset to factory defaults, the following table describes what content is removed for each device type when a device when you remove company data.</span></span>

|<span data-ttu-id="ed259-140">**Inhoudseffect**</span><span class="sxs-lookup"><span data-stu-id="ed259-140">**Content impact**</span></span>|<span data-ttu-id="ed259-141">**iOS 10 en hoger**</span><span class="sxs-lookup"><span data-stu-id="ed259-141">**iOS 10 and later**</span></span>|<span data-ttu-id="ed259-142">**Android 5 en hoger**</span><span class="sxs-lookup"><span data-stu-id="ed259-142">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ed259-143">Microsoft 365 app-gegevens worden gewist als het apparaat is beveiligd door intune App Protection-beleid.</span><span class="sxs-lookup"><span data-stu-id="ed259-143">Microsoft 365 app data is wiped if the device is protected by Intune App Protection policies.</span></span> <span data-ttu-id="ed259-144">De apps worden niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ed259-144">The apps aren't removed.</span></span> <span data-ttu-id="ed259-145">Voor apparaten die niet zijn beveiligd door MAM-beleid (Mobile Application Management), worden Outlook en OneDrive gegevens in de cache niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ed259-145">For devices not protected by Mobile Application Management (MAM) policies, Outlook and OneDrive won't remove cached data.</span></span><br/><span data-ttu-id="ed259-146">**Opmerking** Voor het toepassen van Intune App-beveiligingsbeleid moet u een Intune-licentie hebben.</span><span class="sxs-lookup"><span data-stu-id="ed259-146">**Note** For applying Intune App protection policies you must have an Intune license.</span></span>|<span data-ttu-id="ed259-147">Ja</span><span class="sxs-lookup"><span data-stu-id="ed259-147">Yes</span></span>|<span data-ttu-id="ed259-148">Ja</span><span class="sxs-lookup"><span data-stu-id="ed259-148">Yes</span></span>|
|<span data-ttu-id="ed259-149">Beleidsinstellingen die door Basismobiliteit en Beveiliging worden toegepast op apparaten, worden niet meer afgedwongen. gebruikers kunnen de instellingen wijzigen.</span><span class="sxs-lookup"><span data-stu-id="ed259-149">Policy settings applied by Basic Mobility and Security to devices are no longer enforced; users can change the settings.</span></span>|<span data-ttu-id="ed259-150">Ja</span><span class="sxs-lookup"><span data-stu-id="ed259-150">Yes</span></span>|<span data-ttu-id="ed259-151">Ja</span><span class="sxs-lookup"><span data-stu-id="ed259-151">Yes</span></span>|
|<span data-ttu-id="ed259-152">E-mailprofielen die zijn gemaakt door Basismobiliteit en Beveiliging worden verwijderd en e-mail in de cache op het apparaat wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ed259-152">Email profiles created by Basic Mobility and Security are removed and cached email on the device is deleted.</span></span>|<span data-ttu-id="ed259-153">Ja</span><span class="sxs-lookup"><span data-stu-id="ed259-153">Yes</span></span>|<span data-ttu-id="ed259-154">N.v.t.</span><span class="sxs-lookup"><span data-stu-id="ed259-154">N/A</span></span>|

> [!NOTE]
> <span data-ttu-id="ed259-155">Bedrijfsportal app is beschikbaar in de App Store voor iOS en de Play Store voor Android-apparaten.</span><span class="sxs-lookup"><span data-stu-id="ed259-155">Company Portal app is available at the App Store for iOS and the Play Store for Android devices.</span></span>
