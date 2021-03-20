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
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a><span data-ttu-id="95a43-103">Virtuele certificaatverzameling instellen in Exchange Online om S/MIME te valideren</span><span class="sxs-lookup"><span data-stu-id="95a43-103">Set up virtual certificate collection in Exchange Online to validate S/MIME</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="95a43-104">Als beheerder moet u een virtuele certificaatverzameling configureren in Exchange Online die wordt gebruikt om S/MIME-certificaten te valideren.</span><span class="sxs-lookup"><span data-stu-id="95a43-104">As an admin, you will need to configure a virtual certificate collection in Exchange Online that will be used to validate S/MIME certificates.</span></span> <span data-ttu-id="95a43-105">Deze virtuele certificaatverzameling is ingesteld als een certificaatopslag met een SST-bestandsnaamextensie.</span><span class="sxs-lookup"><span data-stu-id="95a43-105">This virtual certificate collection is set up as a certificate store with an SST filename extension.</span></span> <span data-ttu-id="95a43-106">Het SST-bestand bevat alle hoofd- en tussenliggende certificaten die worden gebruikt bij het valideren van een S/MIME-certificaat.</span><span class="sxs-lookup"><span data-stu-id="95a43-106">The SST file contains all the root and intermediate certificates that are used when validating an S/MIME certificate.</span></span>

## <a name="create-and-save-an-sst"></a><span data-ttu-id="95a43-107">Een SST maken en opslaan</span><span class="sxs-lookup"><span data-stu-id="95a43-107">Create and save an SST</span></span>

<span data-ttu-id="95a43-108">U kunt dit SST-certificaatopslagbestand maken door de certificaten te exporteren van een vertrouwde computer met behulp van de cmdlet **Export-Certificate** in Windows PowerShell en de _waarde Type_ op te geven als SST.</span><span class="sxs-lookup"><span data-stu-id="95a43-108">You can create this SST certificate store file by exporting the certificates from a trusted machine using the **Export-Certificate** cmdlet in Windows PowerShell and specifying the _Type_ value as SST.</span></span> <span data-ttu-id="95a43-109">Zie [Export-Certificate voor instructies.](/powershell/module/pkiclient/export-certificate)</span><span class="sxs-lookup"><span data-stu-id="95a43-109">For instructions, see [Export-Certificate](/powershell/module/pkiclient/export-certificate).</span></span>

<span data-ttu-id="95a43-110">Wanneer u het SST-certificaatopslagbestand hebt, gebruikt u de volgende syntaxis in Exchange Online PowerShell om de inhoud van het SST-bestand op te slaan in de virtuele Exchange Online-certificaatopslag.</span><span class="sxs-lookup"><span data-stu-id="95a43-110">Once you have the SST certificate store file, use the following syntax in Exchange Online PowerShell to save the SST file contents in the Exchange Online virtual certificate store.</span></span> <span data-ttu-id="95a43-111">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95a43-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

<span data-ttu-id="95a43-112">In dit voorbeeld wordt het SST-bestand C:\Mijn documenten\Exported Certificate Store.sst geïmporteerd.</span><span class="sxs-lookup"><span data-stu-id="95a43-112">This example imports the SST file C:\My Documents\Exported Certificate Store.sst.</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

<span data-ttu-id="95a43-113">Zie [Set-SmimeConfig voor](/powershell/module/exchange/set-smimeconfig)gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="95a43-113">For detailed syntax and parameter information, see [Set-SmimeConfig](/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="ensuring-a-certificate-is-valid"></a><span data-ttu-id="95a43-114">Ervoor zorgen dat een certificaat geldig is</span><span class="sxs-lookup"><span data-stu-id="95a43-114">Ensuring a certificate is valid</span></span>

<span data-ttu-id="95a43-115">In Exchange Online wordt alleen de SST gebruikt voor certificaatvalidatie.</span><span class="sxs-lookup"><span data-stu-id="95a43-115">In Exchange Online, only the SST is used for certificate validation.</span></span>

## <a name="more-information"></a><span data-ttu-id="95a43-116">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="95a43-116">More Information</span></span>

[<span data-ttu-id="95a43-117">S/MIME voor het ondertekenen en versleutelen van berichten</span><span class="sxs-lookup"><span data-stu-id="95a43-117">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="95a43-118">Get-SmimeConfig</span><span class="sxs-lookup"><span data-stu-id="95a43-118">Get-SmimeConfig</span></span>](/powershell/module/exchange/get-smimeconfig)