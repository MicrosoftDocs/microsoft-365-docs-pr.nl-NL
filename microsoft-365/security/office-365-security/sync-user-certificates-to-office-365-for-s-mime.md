---
title: Gebruikerscertificaten synchroniseren met Office 365 voor S/MIME
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
ms.custom:
- seo-marvel-apr2020
description: In dit artikel leert u hoe u de juiste certificaten kunt publiceren naar Office 365 voordat u S/MIME-beveiligde berichten verzendt in Exchange Online.
ms.openlocfilehash: 634b65e45b01186a27f9ae61c91d4b27f1a11635
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826479"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="8d745-103">Gebruikerscertificaten synchroniseren met Office 365 voor S/MIME</span><span class="sxs-lookup"><span data-stu-id="8d745-103">Sync user certificates to Office 365 for S/MIME</span></span>

<span data-ttu-id="8d745-104">Voordat iedereen S/MIME-beveiligde berichten kan verzenden in Exchange Online, moeten de juiste certificaten zijn ingesteld.</span><span class="sxs-lookup"><span data-stu-id="8d745-104">Before anyone can send S/MIME-protected messages in Exchange Online, the appropriate certificates must be set up.</span></span> <span data-ttu-id="8d745-105">Voor het verzenden van versleutelde berichten via Exchange Online moet de e-mail-app van de afzender het openbare certificaat van de geadresseerde gebruiken om het bericht te versleutelen.</span><span class="sxs-lookup"><span data-stu-id="8d745-105">To send encrypted messages through Exchange Online, the sender's email app uses the public certificate of the recipient to encrypt the message.</span></span> <span data-ttu-id="8d745-106">Dit openbare X. 509-certificaat moet worden gepubliceerd naar Office 365.</span><span class="sxs-lookup"><span data-stu-id="8d745-106">This public X.509 certificate has to be published to Office 365.</span></span>

## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="8d745-107">Certificaten synchroniseren die ondersteuning bieden voor S/MIME</span><span class="sxs-lookup"><span data-stu-id="8d745-107">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="8d745-108">U kunt S/MIME instellen met behulp van certificaten en deze publiceren in de lokale Active Directory-domein service.</span><span class="sxs-lookup"><span data-stu-id="8d745-108">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service.</span></span> <span data-ttu-id="8d745-109">Zie [overzicht van Active Directory Certificate Services](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11))voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8d745-109">For more information, see [Active Directory Certificate Services Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).</span></span>

<span data-ttu-id="8d745-110">Nadat uw certificaten zijn gepubliceerd, gebruikt u het hulpprogramma van Azure AD Connect om gebruikersgegevens van de on-premises Exchange-omgeving te synchroniseren met Office 365.</span><span class="sxs-lookup"><span data-stu-id="8d745-110">After your certificates are published, use the Azure AD Connect tool to synchronize user data from your on-premises Exchange environment to Office 365.</span></span> <span data-ttu-id="8d745-111">Zie voor meer informatie over dit proces [Azure AD Connect-synchronisatie: de synchronisatie begrijpen en aanpassen](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span><span class="sxs-lookup"><span data-stu-id="8d745-111">For more information on this process, see [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

<span data-ttu-id="8d745-112">Samen met het synchroniseren van andere directorygegevens voor S/MIME-redenen, worden met het hulpprogramma de kenmerken  **userCertificate** en **userSMIMECertificate** voor elk gebruikersobject gesynchroniseerd, zodat de gegevens kunnen worden gebruikt om berichten te ondertekenen en te versleutelen.</span><span class="sxs-lookup"><span data-stu-id="8d745-112">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  **userCertificate** and **userSMIMECertificate** attributes for each user object so the data can be used to sign and encrypt messages.</span></span>

## <a name="more-information"></a><span data-ttu-id="8d745-113">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="8d745-113">More Information</span></span>

[<span data-ttu-id="8d745-114">S/MIME voor het ondertekenen en versleutelen van berichten</span><span class="sxs-lookup"><span data-stu-id="8d745-114">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="8d745-115">Wat is Azure AD Connect?</span><span class="sxs-lookup"><span data-stu-id="8d745-115">What is Azure AD Connect?</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
