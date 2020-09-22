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
ms.openlocfilehash: 3551dbacc3cc6279d319860f1133d059216ae591
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202101"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>Gebruikerscertificaten synchroniseren met Office 365 voor S/MIME

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Voordat iedereen S/MIME-beveiligde berichten kan verzenden in Exchange Online, moeten de juiste certificaten zijn ingesteld. Voor het verzenden van versleutelde berichten via Exchange Online moet de e-mail-app van de afzender het openbare certificaat van de geadresseerde gebruiken om het bericht te versleutelen. Dit openbare X. 509-certificaat moet worden gepubliceerd naar Office 365.

## <a name="to-sync-certificates-that-support-smime"></a>Certificaten synchroniseren die ondersteuning bieden voor S/MIME

U kunt S/MIME instellen met behulp van certificaten en deze publiceren in de lokale Active Directory-domein service. Zie [overzicht van Active Directory Certificate Services](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11))voor meer informatie.

Nadat uw certificaten zijn gepubliceerd, gebruikt u het hulpprogramma van Azure AD Connect om gebruikersgegevens van de on-premises Exchange-omgeving te synchroniseren met Office 365. Zie voor meer informatie over dit proces [Azure AD Connect-synchronisatie: de synchronisatie begrijpen en aanpassen](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).

Samen met het synchroniseren van andere directorygegevens voor S/MIME-redenen, worden met het hulpprogramma de kenmerken  **userCertificate** en **userSMIMECertificate** voor elk gebruikersobject gesynchroniseerd, zodat de gegevens kunnen worden gebruikt om berichten te ondertekenen en te versleutelen.

## <a name="more-information"></a>Meer informatie

[S/MIME voor het ondertekenen en versleutelen van berichten](s-mime-for-message-signing-and-encryption.md)

[Wat is Azure AD Connect?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
