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
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>Een vervaldatum instellen voor e-mailberichten die zijn versleuteld met Office 365 Advanced Message Encryption

Office 365 Advanced Message Encryption is opgenomen in [Microsoft 365 Enterprise E5,](https://www.microsoft.com/microsoft-365/enterprise/home)Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing) en Office 365 Education A5. Als uw organisatie een abonnement heeft dat geen Office 365 Advanced Message Encryption bevat, kunt u dit kopen met de Microsoft 365 E5 Compliance SKU-invoegactie voor Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing) of de Office 365 Advanced Compliance SKU-invoegactie voor Microsoft 365 E3, Microsoft 365 E3 (Non-profitmedewerkersprijzen) of Office 365 SKU's.

U kunt berichtverloop gebruiken voor e-mailberichten die uw gebruikers verzenden naar externe geadresseerden die de OME-portal gebruiken voor toegang tot versleutelde e-mailberichten. U dwingt geadresseerden om de OME-portal te gebruiken om versleutelde e-mailberichten te bekijken en te beantwoorden die door uw organisatie zijn verzonden met behulp van een aangepaste merksjabloon die een vervaldatum aangeeft in Windows PowerShell.

Als een Office 365 globale beheerder, kunt u ook een verloopdatum opgeven voor deze e-mailberichten wanneer u uw bedrijfsmerk toe past om het uiterlijk van de e-mailberichten van uw organisatie aan te passen. Met Office 365 Advanced Message Encryption kunt u meerdere sjablonen maken voor versleutelde e-mailberichten die afkomstig zijn van uw organisatie. Met een sjabloon kunt u bepalen hoe lang geadresseerden toegang hebben tot e-mail die door uw gebruikers wordt verzonden.

Wanneer een eindgebruiker e-mail ontvangt met een vervaldatumset, ziet de gebruiker de vervaldatum in de e-mail van de wrapper. Als een gebruiker een verlopen e-mail probeert te openen, wordt er een fout weergegeven in de OME-portal.

U kunt alleen vervaldatums voor e-mailberichten instellen voor externe geadresseerden.

Met Office 365 Advanced Message Encryption, wanneer u aangepaste huisstijl toe te passen, past de Office 365 de wrapper toe op e-mail die past bij de regel voor de e-mailstroom waarop u de sjabloon toe te passen. Bovendien kunt u verloop alleen gebruiken als u aangepaste huisstijl gebruikt.

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>Een aangepaste huisstijlsjabloon maken om het verlopen van e-mail af te dwingen met PowerShell

1. [Verbinding maken PowerShell Exchange Online met](/powershell/exchange/connect-to-exchange-online-powershell) een account met globale beheerdersmachtigingen in uw organisatie.

2. Voer de New-OMEConfiguration cmdlet uit.

    ```powershell
    New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
    ```

Waarbij:

- `Identity` is de naam van de aangepaste sjabloon.

- `ExternalMailExpiryInDays` geeft het aantal dagen aan dat geadresseerden e-mail kunnen bewaren voordat deze verloopt. U kunt elke waarde tussen 1 en 730 dagen gebruiken.

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Meer informatie over Office 365 Advanced Message Encryption

- [Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md)

- [E-mailberichten intrekken die zijn versleuteld met Office 365 Advanced Message Encryption](revoke-ome-encrypted-mail.md)

- [Beschrijving van berichtbeleid en complianceservice](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)