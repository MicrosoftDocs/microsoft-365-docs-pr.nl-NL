---
title: Uw mobiele apparaat registreren met basis mobiliteit en beveiliging
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
description: Voordat u Microsoft 365-Services met uw apparaat kunt gebruiken, moet u zich mogelijk eerst registreren in de basis mobiliteit en beveiliging voor Microsoft 365.
ms.openlocfilehash: e31054621ba44a4d5f08de9b366fa0978b738cd9
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430141"
---
# <a name="enroll-your-mobile-device-using-basic-mobility-and-security"></a><span data-ttu-id="78be7-103">Uw mobiele apparaat registreren met basis mobiliteit en beveiliging</span><span class="sxs-lookup"><span data-stu-id="78be7-103">Enroll your mobile device using Basic Mobility and Security</span></span>

<span data-ttu-id="78be7-104">Het gebruik van uw telefoon, Tablet en andere mobiele apparaten voor werk is een fantastische manier om op de hoogte te blijven van en zakelijke projecten terwijl u niet op kantoor zit.</span><span class="sxs-lookup"><span data-stu-id="78be7-104">Using your phone, tablet, and other mobile devices for work is a great way to stay informed and work on business projects while you’re away from the office.</span></span> <span data-ttu-id="78be7-105">Voordat u Microsoft 365-Services kunt gebruiken met uw apparaat, moet u zich mogelijk eerst registreren in de basis mobiliteit en beveiliging voor Microsoft 365 via Microsoft intune-bedrijfs portal.</span><span class="sxs-lookup"><span data-stu-id="78be7-105">Before you can use Microsoft 365 services with your device, you might need to first enroll it in Basic Mobility and Security for Microsoft 365 using Microsoft Intune Company Portal.</span></span>

<span data-ttu-id="78be7-106">Organisaties kiezen eenvoudige mobiliteit en beveiliging, zodat werknemers hun mobiele apparaten kunnen gebruiken voor een veilige toegang tot e-mailberichten, agenda's en documenten van het bedrijf wanneer ze belangrijke gegevens beschermen en voldoen aan hun nalevingsvereisten.</span><span class="sxs-lookup"><span data-stu-id="78be7-106">Organizations choose Basic Mobility and Security so that employees can use their mobile devices to securely access work email, calendars, and documents while the business secures important data and meets their compliance requirements.</span></span><span data-ttu-id="78be7-107">Voor meer informatie raadpleegt u [overzicht van basis mobiliteit en beveiliging voor Microsoft 365](overview.md).</span><span class="sxs-lookup"><span data-stu-id="78be7-107"> To learn more, see [Overview of Basic Mobility and Security for Microsoft 365](overview.md).</span></span> <span data-ttu-id="78be7-108">Zie [welke gegevens kan mijn organisatie zien wanneer ik mijn apparaat Registreer?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="78be7-108">For more info, see [What information can my organization see when I enroll my device?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span></span>

>[!IMPORTANT] 
><span data-ttu-id="78be7-109">Wanneer u uw apparaat registreert onder basis en beveiliging voor Microsoft 365, is het mogelijk dat u een wachtwoord hebt ingesteld, samen met de optie voor uw werk organisatie om het apparaat te wissen.</span><span class="sxs-lookup"><span data-stu-id="78be7-109">When you enroll your device in Basic Mobility and Security for Microsoft 365, you might be required to set up a password, together with allowing the option for your work organization to wipe the device.</span></span> <span data-ttu-id="78be7-110">U kunt een apparaat wissen vanuit het Microsoft 365-Beheercentrum, bijvoorbeeld om alle gegevens van het apparaat te verwijderen als het wachtwoord niet te lang is ingevoerd of als de gebruiksvoorwaarden zijn verbroken.</span><span class="sxs-lookup"><span data-stu-id="78be7-110">A device wipe can be performed from the Microsoft 365 admin center, for example, to remove all data from the device if the password is entered incorrectly too many times or if usage terms are broken.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="78be7-111">Ondersteunde apparaten</span><span class="sxs-lookup"><span data-stu-id="78be7-111">Supported devices</span></span>

<span data-ttu-id="78be7-112">Basis mobiliteit en beveiliging voor Microsoft 365 die worden gehost door de intune-service werkt met de meeste, maar niet alle mobiele apparaten.</span><span class="sxs-lookup"><span data-stu-id="78be7-112">Basic Mobility and Security for Microsoft 365 hosted by the Intune service works with most, but not all, mobile devices.</span></span> <span data-ttu-id="78be7-113">Het volgende wordt ondersteund met eenvoudige mobiliteit en beveiliging:</span><span class="sxs-lookup"><span data-stu-id="78be7-113">The following are supported with Basic Mobility and Security:</span></span>

- <span data-ttu-id="78be7-114">iOS 10,0 of later</span><span class="sxs-lookup"><span data-stu-id="78be7-114">iOS 10.0 or later</span></span>
    
- <span data-ttu-id="78be7-115">Android 4,4 of hoger</span><span class="sxs-lookup"><span data-stu-id="78be7-115">Android 4.4 or later</span></span>
    
- <span data-ttu-id="78be7-116">Windows 8,1 en Windows 10 (telefoon en PC)</span><span class="sxs-lookup"><span data-stu-id="78be7-116">Windows 8.1 and Windows 10 (Phone and PC)</span></span>
    
<span data-ttu-id="78be7-117">Neem contact op met de beheerder van uw werk of school als uw apparaat hierboven niet wordt genoemd en u het wilt gebruiken met eenvoudige mobiliteit en beveiliging.</span><span class="sxs-lookup"><span data-stu-id="78be7-117">If your device is not listed above, and you need to use it with Basic Mobility and Security, contact your work or school administrator.</span></span>

>[!TIP] 
><span data-ttu-id="78be7-118">Als u problemen ondervindt bij het registreren van uw apparaat, raadpleegt u [problemen met eenvoudige mobiliteit en beveiliging oplossen](troubleshoot.md).</span><span class="sxs-lookup"><span data-stu-id="78be7-118">If you're having trouble enrolling your device, see [Troubleshoot Basic Mobility and Security](troubleshoot.md).</span></span>

## <a name="set-up-your-mobile-device-with-intune-and-basic-mobility-and-security"></a><span data-ttu-id="78be7-119">Uw mobiele apparaat instellen met intune en Basic, mobiliteit en beveiliging</span><span class="sxs-lookup"><span data-stu-id="78be7-119">Set up your mobile device with Intune and Basic Mobility and Security</span></span>

<span data-ttu-id="78be7-120">Met de intune-bedrijfs portal kunt u een apparaat beheren door Microsoft 365 en basis mobiliteit en beveiliging.</span><span class="sxs-lookup"><span data-stu-id="78be7-120">The Intune Company Portal enables a device to be managed by Microsoft 365 and Basic Mobility and Security.</span></span>

### <a name="iphone-or-ipad"></a><span data-ttu-id="78be7-121">iPhone of iPad</span><span class="sxs-lookup"><span data-stu-id="78be7-121">iPhone or iPad</span></span>

>[!TIP]
><span data-ttu-id="78be7-122">U kunt pas e-mail verzenden en ontvangen wanneer u deze stap voltooit.</span><span class="sxs-lookup"><span data-stu-id="78be7-122">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="78be7-123">Ga naar de App Store van Apple en download en installeer intune Company Portal.</span><span class="sxs-lookup"><span data-stu-id="78be7-123">Go to the Apple App Store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="78be7-124">Als u uw iOS-telefoon of-tablet met de bedrijfsportal wilt verbinden met Office 365, raadpleegt u de [toegang tot uw bedrijfsbronnen instellen voor IOS-apparaten](https://go.microsoft.com/fwlink/?linkid=875316).</span><span class="sxs-lookup"><span data-stu-id="78be7-124">To connect and configure your iOS phone or tablet with the Company portal to Office 365, see [Set up iOS device access to your company resources](https://go.microsoft.com/fwlink/?linkid=875316).</span></span>

### <a name="android-phone-or-tablet"></a><span data-ttu-id="78be7-125">Android-telefoon of-Tablet</span><span class="sxs-lookup"><span data-stu-id="78be7-125">Android phone or tablet</span></span>

>[!TIP]
><span data-ttu-id="78be7-126">U kunt pas e-mail verzenden en ontvangen wanneer u deze stap voltooit.</span><span class="sxs-lookup"><span data-stu-id="78be7-126">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="78be7-127">Ga naar de Google Play Store en download en installeer intune Company Portal.</span><span class="sxs-lookup"><span data-stu-id="78be7-127">Go to the Google Play store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="78be7-128">Als u uw Android-telefoon of-tablet met de bedrijfsportal naar Microsoft 365 wilt verbinden en configureren, raadpleegt u [uw apparaat registreren met de bedrijfsportal](https://go.microsoft.com/fwlink/?linkid=875317).</span><span class="sxs-lookup"><span data-stu-id="78be7-128">To connect and configure your Android phone or tablet with the Company portal to Microsoft 365, see [Enroll your device with Company Portal](https://go.microsoft.com/fwlink/?linkid=875317).</span></span>

### <a name="windows-81-and-windows-10"></a><span data-ttu-id="78be7-129">Windows 8,1 en Windows 10</span><span class="sxs-lookup"><span data-stu-id="78be7-129">Windows 8.1 and Windows 10</span></span>

<span data-ttu-id="78be7-130">Ga naar de Microsoft Store en download en installeer intune Company Portal</span><span class="sxs-lookup"><span data-stu-id="78be7-130">Go to the Microsoft Store, and download and install Intune Company Portal</span></span>

<span data-ttu-id="78be7-131">Als u uw Windows-telefoon of-PC met de bedrijfsportal wilt verbinden en configureren met Microsoft 365, raadpleegt u [Windows-apparaten registratie in intune-bedrijfsportal](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal).</span><span class="sxs-lookup"><span data-stu-id="78be7-131">To connect and configure your Windows phone or PC with the Company portal to Microsoft 365, see [Windows device enrollment in Intune Company Portal](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal).</span></span>

## <a name="whats-next"></a><span data-ttu-id="78be7-132">En nu?</span><span class="sxs-lookup"><span data-stu-id="78be7-132">What's next?</span></span>

<span data-ttu-id="78be7-133">Wanneer uw apparaat is ingeschreven voor basis mobiliteit en beveiliging, kunt u Office-apps op uw apparaat gebruiken om te werken met e-mail, agenda, contactpersonen en documenten.</span><span class="sxs-lookup"><span data-stu-id="78be7-133">After your device is enrolled in Basic Mobility and Security, you can start using Office apps on your device to work with email, calendar, contacts, and documents.</span></span>