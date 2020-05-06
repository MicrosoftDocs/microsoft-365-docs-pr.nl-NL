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
description: Beheerders kunnen leren hoe u een virtuele certificaatverzameling maakt die wordt gebruikt om S/MIME-certificaten te valideren in Exchange Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 89061e3c07803d741e25846ffe8a3325a12668a4
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035294"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a>Virtuele certificaatverzameling instellen in Exchange Online om S/MIME te valideren

Als beheerder moet u een virtuele certificaatverzameling configureren in Exchange Online die wordt gebruikt om S/MIME-certificaten te valideren. Deze virtuele certificaatverzameling is ingesteld als certificaatarchief met een SST-bestandsnaamextensie. Het SST-bestand bevat alle basis- en tussenliggende certificaten die worden gebruikt bij het valideren van een S/MIME-certificaat.

## <a name="create-and-save-an-sst"></a>Een SST maken en opslaan

U dit SST-certificaatarchief maken door de certificaten van een vertrouwde machine te exporteren met de cmdlet **Exportcertificaat** in Windows PowerShell en de _typewaarde_ als SST op te geven. Zie [Exportcertificaat](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate)voor instructies .

Zodra u het SST-certificaatarchief hebt, gebruikt u de volgende syntaxis in Exchange Online PowerShell om de inhoud van het SST-bestand op te slaan in het virtuele certificaatarchief Van Exchange Online. Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

In dit voorbeeld wordt het SST-bestand C:\Mijn documenten\Geëxporteerd certificaatarchief.sst geïmporteerd.

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

Zie [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-smimeconfig)voor gedetailleerde syntaxis- en parameterinformatie.

## <a name="ensuring-a-certificate-is-valid"></a>Ervoor zorgen dat een certificaat geldig is

In Exchange Online wordt alleen de SST gebruikt voor certificaatvalidatie.

## <a name="more-information"></a>Meer informatie

[S/MIME voor het ondertekenen en versleutelen van berichten](s-mime-for-message-signing-and-encryption.md)

[Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/get-smimeconfig)
