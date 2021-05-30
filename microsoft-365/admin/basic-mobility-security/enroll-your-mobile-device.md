---
title: Uw mobiele apparaat registreren met basismobiliteit en beveiliging
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
description: Voordat u uw Microsoft 365 met uw apparaat kunt gebruiken, moet u deze mogelijk eerst registreren bij Basismobiliteit en beveiliging voor Microsoft 365.
ms.openlocfilehash: 2ad0aac331969696bbf53d0b06c18ee5c0ee90f6
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706164"
---
# <a name="enroll-your-mobile-device-using-basic-mobility-and-security"></a><span data-ttu-id="c6ee4-103">Uw mobiele apparaat registreren met basismobiliteit en beveiliging</span><span class="sxs-lookup"><span data-stu-id="c6ee4-103">Enroll your mobile device using Basic Mobility and Security</span></span>

<span data-ttu-id="c6ee4-104">Het gebruik van uw telefoon, tablet en andere mobiele apparaten voor werk is een uitstekende manier om op de hoogte te blijven en aan zakelijke projecten te werken terwijl u niet op kantoor bent.</span><span class="sxs-lookup"><span data-stu-id="c6ee4-104">Using your phone, tablet, and other mobile devices for work is a great way to stay informed and work on business projects while you’re away from the office.</span></span> <span data-ttu-id="c6ee4-105">Voordat u uw Microsoft 365 met uw apparaat kunt gebruiken, moet u deze mogelijk eerst registreren bij Basismobiliteit en beveiliging voor Microsoft 365 met Microsoft Intune Bedrijfsportal.</span><span class="sxs-lookup"><span data-stu-id="c6ee4-105">Before you can use Microsoft 365 services with your device, you might need to first enroll it in Basic Mobility and Security for Microsoft 365 using Microsoft Intune Company Portal.</span></span>

<span data-ttu-id="c6ee4-106">Organisaties kiezen basismobiliteit en beveiliging, zodat werknemers hun mobiele apparaten kunnen gebruiken om veilig toegang te krijgen tot werk-e-mail, agenda's en documenten, terwijl het bedrijf belangrijke gegevens beveiligt en aan de nalevingsvereisten voldoet.</span><span class="sxs-lookup"><span data-stu-id="c6ee4-106">Organizations choose Basic Mobility and Security so that employees can use their mobile devices to securely access work email, calendars, and documents while the business secures important data and meets their compliance requirements.</span></span><span data-ttu-id="c6ee4-107">Zie Overzicht van [basismobiliteit](overview.md)en beveiliging voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c6ee4-107"> To learn more, see [Overview of Basic Mobility and Security for Microsoft 365](overview.md).</span></span> <span data-ttu-id="c6ee4-108">Zie Welke informatie kan mijn organisatie zien wanneer ik mijn [apparaat inschrijf?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c6ee4-108">For more info, see [What information can my organization see when I enroll my device?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span></span>

>[!IMPORTANT] 
><span data-ttu-id="c6ee4-109">Wanneer u uw apparaat inschrijft bij Basismobiliteit en beveiliging voor Microsoft 365, moet u mogelijk een wachtwoord instellen, samen met het toestaan dat uw werkorganisatie het apparaat wist.</span><span class="sxs-lookup"><span data-stu-id="c6ee4-109">When you enroll your device in Basic Mobility and Security for Microsoft 365, you might be required to set up a password, together with allowing the option for your work organization to wipe the device.</span></span> <span data-ttu-id="c6ee4-110">U kunt een apparaat wissen vanuit het Microsoft 365-beheercentrum, bijvoorbeeld om alle gegevens van het apparaat te verwijderen als het wachtwoord te vaak onjuist is ingevoerd of als de gebruiksvoorwaarden worden verbroken.</span><span class="sxs-lookup"><span data-stu-id="c6ee4-110">A device wipe can be performed from the Microsoft 365 admin center, for example, to remove all data from the device if the password is entered incorrectly too many times or if usage terms are broken.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="c6ee4-111">Ondersteunde apparaten</span><span class="sxs-lookup"><span data-stu-id="c6ee4-111">Supported devices</span></span>

<span data-ttu-id="c6ee4-112">Basismobiliteit en beveiliging voor Microsoft 365 die worden gehost door de Intune-service werkt met de meeste, maar niet alle, mobiele apparaten.</span><span class="sxs-lookup"><span data-stu-id="c6ee4-112">Basic Mobility and Security for Microsoft 365 hosted by the Intune service works with most, but not all, mobile devices.</span></span> <span data-ttu-id="c6ee4-113">De volgende worden ondersteund met Basismobiliteit en Beveiliging:</span><span class="sxs-lookup"><span data-stu-id="c6ee4-113">The following are supported with Basic Mobility and Security:</span></span>

- <span data-ttu-id="c6ee4-114">iOS 10.0 of hoger</span><span class="sxs-lookup"><span data-stu-id="c6ee4-114">iOS 10.0 or later</span></span>

- <span data-ttu-id="c6ee4-115">Android 4.4 of hoger</span><span class="sxs-lookup"><span data-stu-id="c6ee4-115">Android 4.4 or later</span></span>

- <span data-ttu-id="c6ee4-116">Windows 8.1 en Windows 10 (Telefoon en pc)</span><span class="sxs-lookup"><span data-stu-id="c6ee4-116">Windows 8.1 and Windows 10 (Phone and PC)</span></span>

<span data-ttu-id="c6ee4-117">Als uw apparaat niet hierboven wordt vermeld en u het moet gebruiken met Basismobiliteit en Beveiliging, neem dan contact op met uw werk- of schoolbeheerder.</span><span class="sxs-lookup"><span data-stu-id="c6ee4-117">If your device is not listed above, and you need to use it with Basic Mobility and Security, contact your work or school administrator.</span></span>

>[!TIP]
><span data-ttu-id="c6ee4-118">Zie Problemen met basismobiliteit en beveiliging oplossen als u problemen hebt met het registreren [van uw apparaat.](troubleshoot.md)</span><span class="sxs-lookup"><span data-stu-id="c6ee4-118">If you're having trouble enrolling your device, see [Troubleshoot Basic Mobility and Security](troubleshoot.md).</span></span>

## <a name="set-up-your-mobile-device-with-intune-and-basic-mobility-and-security"></a><span data-ttu-id="c6ee4-119">Uw mobiele apparaat instellen met Intune en Basismobiliteit en beveiliging</span><span class="sxs-lookup"><span data-stu-id="c6ee4-119">Set up your mobile device with Intune and Basic Mobility and Security</span></span>

<span data-ttu-id="c6ee4-120">Met Intune-bedrijfsportal kan een apparaat worden beheerd door Microsoft 365 en Basismobiliteit en Beveiliging.</span><span class="sxs-lookup"><span data-stu-id="c6ee4-120">The Intune Company Portal enables a device to be managed by Microsoft 365 and Basic Mobility and Security.</span></span>

### <a name="iphone-or-ipad"></a><span data-ttu-id="c6ee4-121">iPhone of iPad</span><span class="sxs-lookup"><span data-stu-id="c6ee4-121">iPhone or iPad</span></span>

>[!TIP]
><span data-ttu-id="c6ee4-122">U kunt pas e-mail verzenden en ontvangen als u deze stap hebt voltooid.</span><span class="sxs-lookup"><span data-stu-id="c6ee4-122">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="c6ee4-123">Ga naar de Apple App Store en download en installeer Intune-bedrijfsportal.</span><span class="sxs-lookup"><span data-stu-id="c6ee4-123">Go to the Apple App Store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="c6ee4-124">Zie IOS-apparaattoegang instellen voor uw bedrijfsbronnen als u uw iOS-telefoon of -tablet wilt verbinden en [configureren](/mem/intune/user-help/enroll-your-device-in-intune-ios)met de bedrijfsportal Office 365.</span><span class="sxs-lookup"><span data-stu-id="c6ee4-124">To connect and configure your iOS phone or tablet with the Company portal to Office 365, see [Set up iOS device access to your company resources](/mem/intune/user-help/enroll-your-device-in-intune-ios).</span></span>

### <a name="android-phone-or-tablet"></a><span data-ttu-id="c6ee4-125">Android-telefoon of -tablet</span><span class="sxs-lookup"><span data-stu-id="c6ee4-125">Android phone or tablet</span></span>

>[!TIP]
><span data-ttu-id="c6ee4-126">U kunt pas e-mail verzenden en ontvangen als u deze stap hebt voltooid.</span><span class="sxs-lookup"><span data-stu-id="c6ee4-126">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="c6ee4-127">Ga naar de Google Play Store en download en installeer Intune-bedrijfsportal.</span><span class="sxs-lookup"><span data-stu-id="c6ee4-127">Go to the Google Play store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="c6ee4-128">Als u uw Android-telefoon of -tablet wilt verbinden en configureren met de bedrijfsportal voor Microsoft 365, zie Uw apparaat registreren [met Bedrijfsportal.](/mem/intune/user-help/enroll-device-android-company-portal)</span><span class="sxs-lookup"><span data-stu-id="c6ee4-128">To connect and configure your Android phone or tablet with the Company portal to Microsoft 365, see [Enroll your device with Company Portal](/mem/intune/user-help/enroll-device-android-company-portal).</span></span>

### <a name="windows-81-and-windows-10"></a><span data-ttu-id="c6ee4-129">Windows 8.1 en Windows 10</span><span class="sxs-lookup"><span data-stu-id="c6ee4-129">Windows 8.1 and Windows 10</span></span>

<span data-ttu-id="c6ee4-130">Ga naar de Microsoft Store en download en installeer Intune-bedrijfsportal</span><span class="sxs-lookup"><span data-stu-id="c6ee4-130">Go to the Microsoft Store, and download and install Intune Company Portal</span></span>

<span data-ttu-id="c6ee4-131">Als u verbinding wilt maken en configureren Windows telefoon of pc met de bedrijfsportal om Microsoft 365, bekijkt u Windows [apparaatinschrijving in Intune-bedrijfsportal.](/intune-user-help/windows-enrollment-company-portal)</span><span class="sxs-lookup"><span data-stu-id="c6ee4-131">To connect and configure your Windows phone or PC with the Company portal to Microsoft 365, see [Windows device enrollment in Intune Company Portal](/intune-user-help/windows-enrollment-company-portal).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c6ee4-132">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="c6ee4-132">Next steps</span></span>

<span data-ttu-id="c6ee4-133">Nadat uw apparaat is geregistreerd voor Basismobiliteit en beveiliging, kunt u Office apps op uw apparaat gebruiken om te werken met e-mail, agenda, contactpersonen en documenten.</span><span class="sxs-lookup"><span data-stu-id="c6ee4-133">After your device is enrolled in Basic Mobility and Security, you can start using Office apps on your device to work with email, calendar, contacts, and documents.</span></span>