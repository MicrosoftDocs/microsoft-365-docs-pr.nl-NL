---
title: Een vervaldatum instellen voor e-mailberichten die zijn versleuteld met Office 365 Advanced Message Encryption
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/8/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Gebruik Office 365 Advanced Message Encryption om uw e-mailbeveiliging uit te breiden door een vervaldatum in te stellen voor e-mailberichten via een aangepaste merksjabloon.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f936ffa62f31e47f51fc1bcb2765195b0ea809af
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162170"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="ef341-103">Een vervaldatum instellen voor e-mailberichten die zijn versleuteld met Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="ef341-103">Set an expiration date for email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="ef341-104">Office 365 Advanced Message Encryption is opgenomen in [Microsoft 365 Enterprise E5,](https://www.microsoft.com/microsoft-365/enterprise/home)Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing) en Office 365 Education A5.</span><span class="sxs-lookup"><span data-stu-id="ef341-104">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="ef341-105">Als uw organisatie een abonnement heeft dat geen Office 365 Advanced Message Encryption bevat, kunt u dit kopen met de Microsoft 365 E5 Compliance SKU-invoegactie voor Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing) of de Office 365 Advanced Compliance SKU-invoegactie voor Microsoft 365 E3, Microsoft 365 E3 (Non-profitmedewerkersprijzen) of Office 365 SKU's.</span><span class="sxs-lookup"><span data-stu-id="ef341-105">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="ef341-106">U kunt berichtverloop gebruiken voor e-mailberichten die uw gebruikers verzenden naar externe geadresseerden die de OME-portal gebruiken voor toegang tot versleutelde e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="ef341-106">You can use message expiration on emails that your users send to external recipients who use the OME Portal to access encrypted emails.</span></span> <span data-ttu-id="ef341-107">U dwingt geadresseerden om de OME-portal te gebruiken om versleutelde e-mailberichten te bekijken en te beantwoorden die door uw organisatie zijn verzonden met behulp van een aangepaste merksjabloon die een vervaldatum aangeeft in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef341-107">You force recipients to use the OME portal to view and reply to encrypted emails sent by your organization by using a custom branded template that specifies an expiration date in Windows PowerShell.</span></span>

<span data-ttu-id="ef341-108">Als een Office 365 globale beheerder, kunt u ook een verloopdatum opgeven voor deze e-mailberichten wanneer u uw bedrijfsmerk toe past om het uiterlijk van de e-mailberichten van uw organisatie aan te passen.</span><span class="sxs-lookup"><span data-stu-id="ef341-108">As an Office 365 global administrator, when you apply your company brand to customize the look of your organization's email messages, you can also specify an expiration for these email messages.</span></span> <span data-ttu-id="ef341-109">Met Office 365 Advanced Message Encryption kunt u meerdere sjablonen maken voor versleutelde e-mailberichten die afkomstig zijn van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ef341-109">With Office 365 Advanced Message Encryption, you can create multiple templates for encrypted emails that originate from your organization.</span></span> <span data-ttu-id="ef341-110">Met een sjabloon kunt u bepalen hoe lang geadresseerden toegang hebben tot e-mail die door uw gebruikers wordt verzonden.</span><span class="sxs-lookup"><span data-stu-id="ef341-110">Using a template, you can control how long recipients have access to mail sent by your users.</span></span>

<span data-ttu-id="ef341-111">Wanneer een eindgebruiker e-mail ontvangt met een vervaldatumset, ziet de gebruiker de vervaldatum in de e-mail van de wrapper.</span><span class="sxs-lookup"><span data-stu-id="ef341-111">When an end user receives mail that has an expiration date set, the user sees the expiration date in the wrapper email.</span></span> <span data-ttu-id="ef341-112">Als een gebruiker een verlopen e-mail probeert te openen, wordt er een fout weergegeven in de OME-portal.</span><span class="sxs-lookup"><span data-stu-id="ef341-112">If a user tries to open an expired mail, an error appears in the OME portal.</span></span>

<span data-ttu-id="ef341-113">U kunt alleen vervaldatums voor e-mailberichten instellen voor externe geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="ef341-113">You can only set expiration dates for emails to external recipients.</span></span>

<span data-ttu-id="ef341-114">Met Office 365 Advanced Message Encryption, wanneer u aangepaste huisstijl toe te passen, past de Office 365 de wrapper toe op e-mail die past bij de regel voor de e-mailstroom waarop u de sjabloon toe te passen.</span><span class="sxs-lookup"><span data-stu-id="ef341-114">With Office 365 Advanced Message Encryption, anytime you apply custom branding, the Office 365 applies the wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="ef341-115">Bovendien kunt u verloop alleen gebruiken als u aangepaste huisstijl gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ef341-115">In addition, you can only use expiration if you use custom branding.</span></span>

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a><span data-ttu-id="ef341-116">Een aangepaste huisstijlsjabloon maken om het verlopen van e-mail af te dwingen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="ef341-116">Create a custom branding template to force mail expiration by using PowerShell</span></span>

1. <span data-ttu-id="ef341-117">[Verbinding maken PowerShell Exchange Online met](/powershell/exchange/connect-to-exchange-online-powershell) een account met globale beheerdersmachtigingen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ef341-117">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) with an account that has global administrator permissions in your organization.</span></span>

2. <span data-ttu-id="ef341-118">Voer de New-OMEConfiguration cmdlet uit.</span><span class="sxs-lookup"><span data-stu-id="ef341-118">Run the New-OMEConfiguration cmdlet.</span></span>

    ```powershell
    New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
    ```

<span data-ttu-id="ef341-119">Waarbij:</span><span class="sxs-lookup"><span data-stu-id="ef341-119">Where:</span></span>

- <span data-ttu-id="ef341-120">`Identity` is de naam van de aangepaste sjabloon.</span><span class="sxs-lookup"><span data-stu-id="ef341-120">`Identity` is the name of the custom template.</span></span>

- <span data-ttu-id="ef341-121">`ExternalMailExpiryInDays` geeft het aantal dagen aan dat geadresseerden e-mail kunnen bewaren voordat deze verloopt.</span><span class="sxs-lookup"><span data-stu-id="ef341-121">`ExternalMailExpiryInDays` identifies the number of days that recipients can keep mail before it expires.</span></span> <span data-ttu-id="ef341-122">U kunt elke waarde tussen 1 en 730 dagen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ef341-122">You can use any value between 1–730 days.</span></span>

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="ef341-123">Meer informatie over Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="ef341-123">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="ef341-124">Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="ef341-124">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="ef341-125">E-mailberichten intrekken die zijn versleuteld met Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="ef341-125">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>](revoke-ome-encrypted-mail.md)

- [<span data-ttu-id="ef341-126">Beschrijving van berichtbeleid en complianceservice</span><span class="sxs-lookup"><span data-stu-id="ef341-126">Message policy and compliance service description</span></span>](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)