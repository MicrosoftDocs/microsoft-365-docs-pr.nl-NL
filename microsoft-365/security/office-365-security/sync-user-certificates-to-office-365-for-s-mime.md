---
title: Gebruikerscertificaten synchroniseren met Office 365 voor S/MIME
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
ms.custom:
- seo-marvel-apr2020
description: In dit artikel leert u hoe u de juiste certificaten naar Office 365 publiceert voordat u s/mime-beveiligde berichten verzendt in Exchange Online.
ms.openlocfilehash: f9e0bef2f7d2125e2daeb86b3cf44ae433aae117
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035210"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="e7177-103">Gebruikerscertificaten synchroniseren met Office 365 voor S/MIME</span><span class="sxs-lookup"><span data-stu-id="e7177-103">Sync user certificates to Office 365 for S/MIME</span></span>

<span data-ttu-id="e7177-104">Voordat iemand s/mime-beveiligde berichten kan verzenden in Exchange Online, moeten de juiste certificaten worden ingesteld.</span><span class="sxs-lookup"><span data-stu-id="e7177-104">Before anyone can send S/MIME-protected messages in Exchange Online, the appropriate certificates must be set up.</span></span> <span data-ttu-id="e7177-105">Om versleutelde berichten via Exchange Online te verzenden, gebruikt de e-mailapp van de afzender het openbare certificaat van de ontvanger om het bericht te versleutelen.</span><span class="sxs-lookup"><span data-stu-id="e7177-105">To send encrypted messages through Exchange Online, the sender's email app uses the public certificate of the recipient to encrypt the message.</span></span> <span data-ttu-id="e7177-106">Dit openbare X.509-certificaat moet worden gepubliceerd naar Office 365.</span><span class="sxs-lookup"><span data-stu-id="e7177-106">This public X.509 certificate has to be published to Office 365.</span></span>

## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="e7177-107">Certificaten synchroniseren die S/MIME ondersteunen</span><span class="sxs-lookup"><span data-stu-id="e7177-107">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="e7177-108">Begin met het instellen van S/MIME door certificaten uit te geven en te publiceren in uw lokale Active Directory Domain Service.</span><span class="sxs-lookup"><span data-stu-id="e7177-108">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service.</span></span> <span data-ttu-id="e7177-109">Zie [Overzicht van Active Directory Certificate Services](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11))voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e7177-109">For more information, see [Active Directory Certificate Services Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).</span></span>

<span data-ttu-id="e7177-110">Nadat uw certificaten zijn gepubliceerd, gebruikt u het hulpprogramma Azure AD Connect om gebruikersgegevens van uw on-premises Exchange-omgeving te synchroniseren met Office 365.</span><span class="sxs-lookup"><span data-stu-id="e7177-110">After your certificates are published, use the Azure AD Connect tool to synchronize user data from your on-premises Exchange environment to Office 365.</span></span> <span data-ttu-id="e7177-111">Zie [Azure AD Connect-synchronisatie: Synchronisatie begrijpen en aanpassen](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)voor meer informatie over dit proces.</span><span class="sxs-lookup"><span data-stu-id="e7177-111">For more information on this process, see [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

<span data-ttu-id="e7177-112">Samen met het synchroniseren van andere directorygegevens synchroniseert het hulpprogramma voor S/MIME-doeleinden de **gebruikerscertificaat-** en **gebruikersmimecertificaatkenmerken** voor elk gebruikersobject, zodat de gegevens kunnen worden gebruikt om berichten te ondertekenen en te versleutelen.</span><span class="sxs-lookup"><span data-stu-id="e7177-112">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  **userCertificate** and **userSMIMECertificate** attributes for each user object so the data can be used to sign and encrypt messages.</span></span>

## <a name="more-information"></a><span data-ttu-id="e7177-113">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="e7177-113">More Information</span></span>

[<span data-ttu-id="e7177-114">S/MIME voor het ondertekenen en versleutelen van berichten</span><span class="sxs-lookup"><span data-stu-id="e7177-114">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="e7177-115">Wat is Azure AD Connect?</span><span class="sxs-lookup"><span data-stu-id="e7177-115">What is Azure AD Connect?</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
