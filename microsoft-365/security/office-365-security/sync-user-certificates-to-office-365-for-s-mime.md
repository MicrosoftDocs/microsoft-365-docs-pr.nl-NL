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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
ms.custom:
- seo-marvel-apr2020
description: In dit artikel leert u hoe u de juiste certificaten naar Office 365 publiceert voordat u met S/MIME beveiligde berichten verstuurt in Exchange Online.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8c6d3968d617bcb503057c47567182091010c726
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "50290199"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>Gebruikerscertificaten synchroniseren met Office 365 voor S/MIME

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Voordat iedereen met S/MIME-beveiligde berichten kan verzenden in Exchange Online, moeten de juiste certificaten worden ingesteld. Als u versleutelde berichten wilt verzenden via Exchange Online, gebruikt de e-mailapp van de afzender het openbare certificaat van de ontvanger om het bericht te versleutelen. Dit openbare X.509-certificaat moet worden gepubliceerd naar Office 365.

## <a name="to-sync-certificates-that-support-smime"></a>Certificaten synchroniseren die S/MIME ondersteunen

Begin met het instellen van S/MIME door certificaten uit te geven en deze te publiceren in uw lokale Active Directory Domain Service. Zie Active Directory Certificate Services Overview [(Overzicht van Active Directory-certificaatservices) voor meer informatie.](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11))

Nadat uw certificaten zijn gepubliceerd, gebruikt u het hulpprogramma Azure AD Connect om gebruikersgegevens vanuit uw on-premises Exchange-omgeving te synchroniseren met Office 365. Zie Azure AD Connect-synchronisatie voor meer informatie over dit [proces: Synchronisatie](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)begrijpen en aanpassen.

Samen met het synchroniseren van andere adreslijstgegevens worden voor S/MIME-doeleinden de kenmerken  **userCertificate** en **userSMIMECertificate** voor elk gebruikersobject gesynchroniseerd, zodat de gegevens kunnen worden gebruikt voor het ondertekenen en versleutelen van berichten.

## <a name="more-information"></a>Meer informatie

[S/MIME voor het ondertekenen en versleutelen van berichten](s-mime-for-message-signing-and-encryption.md)

[Wat is Azure AD Connect?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
