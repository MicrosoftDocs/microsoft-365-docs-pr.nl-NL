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
description: Voordat iemand s/MIME-beveiligde berichten kan verzenden, moeten de juiste certificaten worden ingesteld. Om versleutelde berichten via Exchange Online te verzenden, gebruikt het e-mailprogramma van de afzender het openbare certificaat van de ontvanger om het bericht te versleutelen. Dit openbare X.509-certificaat moet worden gepubliceerd in Office 365.
ms.openlocfilehash: a62af3b176f29ec2bd8c97ae02178c87b7a63544
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42809871"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="d30c8-105">Gebruikerscertificaten synchroniseren met Office 365 voor S/MIME</span><span class="sxs-lookup"><span data-stu-id="d30c8-105">Sync user certificates to Office 365 for S/MIME</span></span>

<span data-ttu-id="d30c8-106">Voordat iemand s/MIME-beveiligde berichten kan verzenden in Exchange Online, moeten de juiste certificaten worden ingesteld.</span><span class="sxs-lookup"><span data-stu-id="d30c8-106">Before anyone can send S/MIME-protected messages in Exchange Online, the appropriate certificates must be set up.</span></span> <span data-ttu-id="d30c8-107">Als u versleutelde berichten wilt verzenden via Exchange Online, gebruikt de e-mail-app van de afzender het openbare certificaat van de ontvanger om het bericht te versleutelen.</span><span class="sxs-lookup"><span data-stu-id="d30c8-107">To send encrypted messages through Exchange Online, the sender's email app uses the public certificate of the recipient to encrypt the message.</span></span> <span data-ttu-id="d30c8-108">Dit openbare X.509-certificaat moet worden gepubliceerd in Office 365.</span><span class="sxs-lookup"><span data-stu-id="d30c8-108">This public X.509 certificate has to be published to Office 365.</span></span>

## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="d30c8-109">Certificaten synchroniseren die S/MIME ondersteunen</span><span class="sxs-lookup"><span data-stu-id="d30c8-109">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="d30c8-110">Begin met het instellen van S/MIME door certificaten uit te geven en ze te publiceren in uw lokale Active Directory-domeinservice.</span><span class="sxs-lookup"><span data-stu-id="d30c8-110">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service.</span></span> <span data-ttu-id="d30c8-111">Zie [Overzicht van Active Directory Certificate Services](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11))voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d30c8-111">For more information, see [Active Directory Certificate Services Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).</span></span>

<span data-ttu-id="d30c8-112">Nadat uw certificaten zijn gepubliceerd, gebruikt u het hulpprogramma Azure AD Connect om gebruikersgegevens vanuit uw on-premises Exchange-omgeving te synchroniseren met Office 365.</span><span class="sxs-lookup"><span data-stu-id="d30c8-112">After your certificates are published, use the Azure AD Connect tool to synchronize user data from your on-premises Exchange environment to Office 365.</span></span> <span data-ttu-id="d30c8-113">Zie [Azure AD Connect-synchronisatie: Synchronisatie begrijpen en aanpassen voor](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)meer informatie over dit proces.</span><span class="sxs-lookup"><span data-stu-id="d30c8-113">For more information on this process, see [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

<span data-ttu-id="d30c8-114">Samen met het synchroniseren van andere directorygegevens synchroniseert het hulpprogramma voor S/MIME-doeleinden de kenmerken van het **userCertificate-** en **userSMIMECertificate-certificaat** voor elk gebruikersobject, zodat de gegevens kunnen worden gebruikt om berichten te ondertekenen en te versleutelen.</span><span class="sxs-lookup"><span data-stu-id="d30c8-114">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  **userCertificate** and **userSMIMECertificate** attributes for each user object so the data can be used to sign and encrypt messages.</span></span>

## <a name="more-information"></a><span data-ttu-id="d30c8-115">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="d30c8-115">More Information</span></span>

[<span data-ttu-id="d30c8-116">S/MIME voor het ondertekenen en versleutelen van berichten</span><span class="sxs-lookup"><span data-stu-id="d30c8-116">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="d30c8-117">Wat is Azure AD Connect?</span><span class="sxs-lookup"><span data-stu-id="d30c8-117">What is Azure AD Connect?</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
