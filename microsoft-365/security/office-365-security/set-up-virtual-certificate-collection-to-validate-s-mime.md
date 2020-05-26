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
ms.openlocfilehash: 5bd453383a263fdb2c0c7e2ce0014ad205e5fdc2
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352167"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a><span data-ttu-id="4a659-103">Virtuele certificaatverzameling instellen in Exchange Online om S/MIME te valideren</span><span class="sxs-lookup"><span data-stu-id="4a659-103">Set up virtual certificate collection in Exchange Online to validate S/MIME</span></span>

<span data-ttu-id="4a659-104">Als beheerder moet u een virtuele certificaatverzameling configureren in Exchange Online die wordt gebruikt om S/MIME-certificaten te valideren.</span><span class="sxs-lookup"><span data-stu-id="4a659-104">As an admin, you will need to configure a virtual certificate collection in Exchange Online that will be used to validate S/MIME certificates.</span></span> <span data-ttu-id="4a659-105">Deze virtuele certificaatverzameling is ingesteld als certificaatarchief met een SST-bestandsnaamextensie.</span><span class="sxs-lookup"><span data-stu-id="4a659-105">This virtual certificate collection is set up as a certificate store with an SST filename extension.</span></span> <span data-ttu-id="4a659-106">Het SST-bestand bevat alle basis- en tussenliggende certificaten die worden gebruikt bij het valideren van een S/MIME-certificaat.</span><span class="sxs-lookup"><span data-stu-id="4a659-106">The SST file contains all the root and intermediate certificates that are used when validating an S/MIME certificate.</span></span>

## <a name="create-and-save-an-sst"></a><span data-ttu-id="4a659-107">Een SST maken en opslaan</span><span class="sxs-lookup"><span data-stu-id="4a659-107">Create and save an SST</span></span>

<span data-ttu-id="4a659-108">U dit SST-certificaatarchief maken door de certificaten van een vertrouwde machine te exporteren met de cmdlet **Exportcertificaat** in Windows PowerShell en de _typewaarde_ als SST op te geven.</span><span class="sxs-lookup"><span data-stu-id="4a659-108">You can create this SST certificate store file by exporting the certificates from a trusted machine using the **Export-Certificate** cmdlet in Windows PowerShell and specifying the _Type_ value as SST.</span></span> <span data-ttu-id="4a659-109">Zie [Exportcertificaat](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate)voor instructies .</span><span class="sxs-lookup"><span data-stu-id="4a659-109">For instructions, see [Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).</span></span>

<span data-ttu-id="4a659-110">Zodra u het SST-certificaatarchief hebt, gebruikt u de volgende syntaxis in Exchange Online PowerShell om de inhoud van het SST-bestand op te slaan in het virtuele certificaatarchief Van Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4a659-110">Once you have the SST certificate store file, use the following syntax in Exchange Online PowerShell to save the SST file contents in the Exchange Online virtual certificate store.</span></span> <span data-ttu-id="4a659-111">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4a659-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

<span data-ttu-id="4a659-112">In dit voorbeeld wordt het SST-bestand C:\Mijn documenten\Geëxporteerd certificaatarchief.sst geïmporteerd.</span><span class="sxs-lookup"><span data-stu-id="4a659-112">This example imports the SST file C:\My Documents\Exported Certificate Store.sst.</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

<span data-ttu-id="4a659-113">Zie [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="4a659-113">For detailed syntax and parameter information, see [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="ensuring-a-certificate-is-valid"></a><span data-ttu-id="4a659-114">Ervoor zorgen dat een certificaat geldig is</span><span class="sxs-lookup"><span data-stu-id="4a659-114">Ensuring a certificate is valid</span></span>

<span data-ttu-id="4a659-115">In Exchange Online wordt alleen de SST gebruikt voor certificaatvalidatie.</span><span class="sxs-lookup"><span data-stu-id="4a659-115">In Exchange Online, only the SST is used for certificate validation.</span></span>

## <a name="more-information"></a><span data-ttu-id="4a659-116">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="4a659-116">More Information</span></span>

[<span data-ttu-id="4a659-117">S/MIME voor het ondertekenen en versleutelen van berichten</span><span class="sxs-lookup"><span data-stu-id="4a659-117">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="4a659-118">Get-SmimeConfig</span><span class="sxs-lookup"><span data-stu-id="4a659-118">Get-SmimeConfig</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig)
