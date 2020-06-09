---
title: Virtuele certificaatverzameling instellen - Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: Beheerders kunnen leren hoe u een virtuele certificaatverzameling maakt die wordt gebruikt om S/MIME-certificaten in Exchange Online te valideren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c8833cb50150eefea6bb786f8694fad42b52a752
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617184"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a>Virtuele certificaatverzameling instellen in Exchange Online om S/MIME te valideren

Als beheerder moet u een virtuele certificaatverzameling configureren in Exchange Online die wordt gebruikt om S/MIME-certificaten te valideren. Deze virtuele certificaatverzameling is ingesteld als een certificaatarchief met een SST-bestandsnaamextensie. Het SST-bestand bevat alle hoofd- en tussencertificaten die worden gebruikt bij het valideren van een S/MIME-certificaat.

## <a name="create-and-save-an-sst"></a>Een SST maken en opslaan

U dit SST-certificaatarchiefbestand maken door de certificaten van een vertrouwde machine te exporteren met de cmdlet **Export-Certificaat** in Windows PowerShell en de _waarde Type_ als SST op te geven. Zie [Exportcertificaat voor](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate)instructies .

Zodra u het SST-certificaatarchiefbestand hebt, gebruikt u de volgende syntaxis in Exchange Online PowerShell om de inhoud van het SST-bestand op te slaan in het virtuele certificaatarchief van Exchange Online. Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

In dit voorbeeld wordt het SST-bestand C:\Mijn documenten\Exported Certificate Store.sst importeert.

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

Zie [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)voor gedetailleerde syntaxis- en parametergegevens .

## <a name="ensuring-a-certificate-is-valid"></a>Ervoor zorgen dat een certificaat geldig is

In Exchange Online wordt alleen de SST gebruikt voor certificaatvalidatie.

## <a name="more-information"></a>Meer informatie

[S/MIME voor het ondertekenen en versleutelen van berichten](s-mime-for-message-signing-and-encryption.md)

[Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig)
