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
description: In dit artikel leert u hoe u de juiste certificaten publiceert naar Office 365 voordat u met S/MIME beveiligde berichten verstuurt in Exchange Online.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 387f9f405afd45254c6568aa92334a7ee5b4171f
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204624"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>Gebruikerscertificaten synchroniseren met Office 365 voor S/MIME

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Voordat iemand met S/MIME beveiligde berichten kan verzenden in Exchange Online, moeten de juiste certificaten zijn ingesteld. Als u versleutelde berichten wilt verzenden via Exchange Online, gebruikt de e-mail-app van de afzender het openbare certificaat van de geadresseerde om het bericht te versleutelen. Dit openbare X.509-certificaat moet worden gepubliceerd naar Office 365.

## <a name="to-sync-certificates-that-support-smime"></a>Certificaten synchroniseren die S/MIME ondersteunen

Begin met het instellen van S/MIME door certificaten uit te geven en deze te publiceren in uw lokale Active Directory Domain Service. Zie Overzicht van Active Directory Certificate Services voor meer [informatie.](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11))

Nadat uw certificaten zijn gepubliceerd, gebruikt u het hulpprogramma Azure AD Connect om gebruikersgegevens vanuit uw on-premises Exchange-omgeving te synchroniseren met Office 365. Zie Synchronisatie van Azure AD Connect voor meer informatie over dit [proces: Synchronisatie](/azure/active-directory/hybrid/how-to-connect-sync-whatis)begrijpen en aanpassen.

Naast het synchroniseren van andere adreslijstgegevens worden met het hulpprogramma voor S/MIME-doeleinden de  **userCertificate-** en **userSMIMECertificate-kenmerken** voor elk gebruikersobject gesynchroniseerd, zodat de gegevens kunnen worden gebruikt om berichten te ondertekenen en te versleutelen.

## <a name="more-information"></a>Meer informatie

[S/MIME voor het ondertekenen en versleutelen van berichten](s-mime-for-message-signing-and-encryption.md)

[Wat is Azure AD Connect?](/azure/active-directory/hybrid/whatis-azure-ad-connect)