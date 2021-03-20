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
description: Beheerders kunnen leren hoe ze een virtuele certificaatverzameling kunnen maken die wordt gebruikt om S/MIME-certificaten te valideren in Exchange Online.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2a5dad897ce58b8496551535cc28e03c7a1fa964
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916654"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a>Virtuele certificaatverzameling instellen in Exchange Online om S/MIME te valideren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Als beheerder moet u een virtuele certificaatverzameling configureren in Exchange Online die wordt gebruikt om S/MIME-certificaten te valideren. Deze virtuele certificaatverzameling is ingesteld als een certificaatopslag met een SST-bestandsnaamextensie. Het SST-bestand bevat alle hoofd- en tussenliggende certificaten die worden gebruikt bij het valideren van een S/MIME-certificaat.

## <a name="create-and-save-an-sst"></a>Een SST maken en opslaan

U kunt dit SST-certificaatopslagbestand maken door de certificaten te exporteren van een vertrouwde computer met behulp van de cmdlet **Export-Certificate** in Windows PowerShell en de _waarde Type_ op te geven als SST. Zie [Export-Certificate voor instructies.](/powershell/module/pkiclient/export-certificate)

Wanneer u het SST-certificaatopslagbestand hebt, gebruikt u de volgende syntaxis in Exchange Online PowerShell om de inhoud van het SST-bestand op te slaan in de virtuele Exchange Online-certificaatopslag. Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

In dit voorbeeld wordt het SST-bestand C:\Mijn documenten\Exported Certificate Store.sst geïmporteerd.

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

Zie [Set-SmimeConfig voor](/powershell/module/exchange/set-smimeconfig)gedetailleerde syntaxis- en parametergegevens.

## <a name="ensuring-a-certificate-is-valid"></a>Ervoor zorgen dat een certificaat geldig is

In Exchange Online wordt alleen de SST gebruikt voor certificaatvalidatie.

## <a name="more-information"></a>Meer informatie

[S/MIME voor het ondertekenen en versleutelen van berichten](s-mime-for-message-signing-and-encryption.md)

[Get-SmimeConfig](/powershell/module/exchange/get-smimeconfig)