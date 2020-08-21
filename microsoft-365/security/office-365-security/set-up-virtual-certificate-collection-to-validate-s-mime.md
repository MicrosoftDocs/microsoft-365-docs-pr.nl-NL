---
title: Virtuele certificaat verzameling instellen-Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: Beheerders kunnen leren hoe u een virtuele certificaat verzameling maakt die wordt gebruikt om S/MIME-certificaten te valideren in Exchange Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 16c6d38882a69feb46aa3e8fadccd6e005426304
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825135"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a>Virtuele certificaat verzameling instellen in Exchange Online om S/MIME te valideren

Als beheerder moet u een virtuele certificaat verzameling in Exchange Online configureren die wordt gebruikt om S/MIME-certificaten te valideren. Deze virtuele certificaat verzameling wordt ingesteld als een certificaatarchief met de bestandsextensie SST. Het bestand SST bevat alle hoofd-en tussenliggende certificaten die worden gebruikt voor het valideren van een S/MIME-certificaat.

## <a name="create-and-save-an-sst"></a>Een SST maken en opslaan

U kunt dit bestand van de SST-certificaatarchieven maken door de certificaten van een vertrouwde computer te exporteren met behulp van de cmdlet **export-Certificate** in Windows PowerShell en de waarde _type_ te specificeren als SST. Zie [Exporteer certificaat](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate)voor instructies.

Wanneer u het bestand van de SST-certificaatopslag hebt, gebruikt u de volgende syntaxis in Exchange Online PowerShell om de inhoud van de bestanden van de SST op te slaan in de virtuele certificaatopslag van Exchange Online. Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

In dit voorbeeld wordt het bestand SST, C:\My Documents\Exported Certificate Store. SST geïmporteerd.

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

Zie [set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)voor gedetailleerde syntaxis-en parameterinformatie.

## <a name="ensuring-a-certificate-is-valid"></a>Controleren of een certificaat geldig is

In Exchange Online wordt alleen de SST gebruikt voor de validatie van certificaten.

## <a name="more-information"></a>Meer informatie

[S/MIME voor het ondertekenen en versleutelen van berichten](s-mime-for-message-signing-and-encryption.md)

[Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig)
