---
title: Virtuele certificaatverzameling instellen - Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: Beheerders kunnen informatie krijgen over het maken van een virtuele certificaatverzameling die wordt gebruikt voor het valideren van S/MIME-certificaten in Exchange Online.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4537ecfa6d800294af9572e462ce18491ce2c441
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "50290475"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a>Virtuele certificaatverzameling instellen in Exchange Online om S/MIME te valideren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Als beheerder moet u een virtuele certificaatverzameling configureren in Exchange Online die wordt gebruikt voor het valideren van S/MIME-certificaten. Deze virtuele certificaatverzameling is ingesteld als een certificaatopslag met de extensie SST. Het SST-bestand bevat alle basiscertificaten en tussenliggende certificaten die worden gebruikt bij het valideren van een S/MIME-certificaat.

## <a name="create-and-save-an-sst"></a>Een SST maken en opslaan

U kunt dit SST-certificaatopslagbestand maken door de certificaten van een vertrouwde computer te exporteren met de cmdlet **Export-Certificate** in Windows PowerShell en de _waarde van het type_ op te geven als SST. Zie [Export-Certificate voor instructies.](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate)

Wanneer u het SST-certificaatopslagbestand hebt, gebruikt u de volgende syntaxis in Exchange Online PowerShell om de inhoud van het SST-bestand op te slaan in de virtuele certificaatopslag van Exchange Online. Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als je verbinding wilt maken met Exchange Online PowerShell.

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

In dit voorbeeld wordt het SST-bestand C:\Mijn documenten\Geëxporteerde certificaatopslag.sst geïmporteerd.

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

Zie [Set-SmimeConfig voor gedetailleerde syntaxis- en parameterinformatie.](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)

## <a name="ensuring-a-certificate-is-valid"></a>Garanderen dat een certificaat geldig is

In Exchange Online wordt alleen de SST gebruikt voor certificaatvalidatie.

## <a name="more-information"></a>Meer informatie

[S/MIME voor het ondertekenen en versleutelen van berichten](s-mime-for-message-signing-and-encryption.md)

[Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig)
