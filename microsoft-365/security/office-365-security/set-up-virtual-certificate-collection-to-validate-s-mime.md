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
ms.openlocfilehash: aabd234f344778b2bfad34a7046bb51c55ed4b3d
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197199"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a><span data-ttu-id="4440c-103">Virtuele certificaat verzameling instellen in Exchange Online om S/MIME te valideren</span><span class="sxs-lookup"><span data-stu-id="4440c-103">Set up virtual certificate collection in Exchange Online to validate S/MIME</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="4440c-104">Als beheerder moet u een virtuele certificaat verzameling in Exchange Online configureren die wordt gebruikt om S/MIME-certificaten te valideren.</span><span class="sxs-lookup"><span data-stu-id="4440c-104">As an admin, you will need to configure a virtual certificate collection in Exchange Online that will be used to validate S/MIME certificates.</span></span> <span data-ttu-id="4440c-105">Deze virtuele certificaat verzameling wordt ingesteld als een certificaatarchief met de bestandsextensie SST.</span><span class="sxs-lookup"><span data-stu-id="4440c-105">This virtual certificate collection is set up as a certificate store with an SST filename extension.</span></span> <span data-ttu-id="4440c-106">Het bestand SST bevat alle hoofd-en tussenliggende certificaten die worden gebruikt voor het valideren van een S/MIME-certificaat.</span><span class="sxs-lookup"><span data-stu-id="4440c-106">The SST file contains all the root and intermediate certificates that are used when validating an S/MIME certificate.</span></span>

## <a name="create-and-save-an-sst"></a><span data-ttu-id="4440c-107">Een SST maken en opslaan</span><span class="sxs-lookup"><span data-stu-id="4440c-107">Create and save an SST</span></span>

<span data-ttu-id="4440c-108">U kunt dit bestand van de SST-certificaatarchieven maken door de certificaten van een vertrouwde computer te exporteren met behulp van de cmdlet **export-Certificate** in Windows PowerShell en de waarde _type_ te specificeren als SST.</span><span class="sxs-lookup"><span data-stu-id="4440c-108">You can create this SST certificate store file by exporting the certificates from a trusted machine using the **Export-Certificate** cmdlet in Windows PowerShell and specifying the _Type_ value as SST.</span></span> <span data-ttu-id="4440c-109">Zie [Exporteer certificaat](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="4440c-109">For instructions, see [Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).</span></span>

<span data-ttu-id="4440c-110">Wanneer u het bestand van de SST-certificaatopslag hebt, gebruikt u de volgende syntaxis in Exchange Online PowerShell om de inhoud van de bestanden van de SST op te slaan in de virtuele certificaatopslag van Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4440c-110">Once you have the SST certificate store file, use the following syntax in Exchange Online PowerShell to save the SST file contents in the Exchange Online virtual certificate store.</span></span> <span data-ttu-id="4440c-111">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4440c-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

<span data-ttu-id="4440c-112">In dit voorbeeld wordt het bestand SST, C:\My Documents\Exported Certificate Store. SST geïmporteerd.</span><span class="sxs-lookup"><span data-stu-id="4440c-112">This example imports the SST file C:\My Documents\Exported Certificate Store.sst.</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

<span data-ttu-id="4440c-113">Zie [set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="4440c-113">For detailed syntax and parameter information, see [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="ensuring-a-certificate-is-valid"></a><span data-ttu-id="4440c-114">Controleren of een certificaat geldig is</span><span class="sxs-lookup"><span data-stu-id="4440c-114">Ensuring a certificate is valid</span></span>

<span data-ttu-id="4440c-115">In Exchange Online wordt alleen de SST gebruikt voor de validatie van certificaten.</span><span class="sxs-lookup"><span data-stu-id="4440c-115">In Exchange Online, only the SST is used for certificate validation.</span></span>

## <a name="more-information"></a><span data-ttu-id="4440c-116">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="4440c-116">More Information</span></span>

[<span data-ttu-id="4440c-117">S/MIME voor het ondertekenen en versleutelen van berichten</span><span class="sxs-lookup"><span data-stu-id="4440c-117">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="4440c-118">Get-SmimeConfig</span><span class="sxs-lookup"><span data-stu-id="4440c-118">Get-SmimeConfig</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig)
