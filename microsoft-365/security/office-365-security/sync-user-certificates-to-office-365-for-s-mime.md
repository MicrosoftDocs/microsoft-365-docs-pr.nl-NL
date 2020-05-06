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
# <a name="sync-user-certificates-to-office-365-for-smime"></a>Gebruikerscertificaten synchroniseren met Office 365 voor S/MIME

Voordat iemand s/mime-beveiligde berichten kan verzenden in Exchange Online, moeten de juiste certificaten worden ingesteld. Om versleutelde berichten via Exchange Online te verzenden, gebruikt de e-mailapp van de afzender het openbare certificaat van de ontvanger om het bericht te versleutelen. Dit openbare X.509-certificaat moet worden gepubliceerd naar Office 365.

## <a name="to-sync-certificates-that-support-smime"></a>Certificaten synchroniseren die S/MIME ondersteunen

Begin met het instellen van S/MIME door certificaten uit te geven en te publiceren in uw lokale Active Directory Domain Service. Zie [Overzicht van Active Directory Certificate Services](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11))voor meer informatie.

Nadat uw certificaten zijn gepubliceerd, gebruikt u het hulpprogramma Azure AD Connect om gebruikersgegevens van uw on-premises Exchange-omgeving te synchroniseren met Office 365. Zie [Azure AD Connect-synchronisatie: Synchronisatie begrijpen en aanpassen](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)voor meer informatie over dit proces.

Samen met het synchroniseren van andere directorygegevens synchroniseert het hulpprogramma voor S/MIME-doeleinden de **gebruikerscertificaat-** en **gebruikersmimecertificaatkenmerken** voor elk gebruikersobject, zodat de gegevens kunnen worden gebruikt om berichten te ondertekenen en te versleutelen.

## <a name="more-information"></a>Meer informatie

[S/MIME voor het ondertekenen en versleutelen van berichten](s-mime-for-message-signing-and-encryption.md)

[Wat is Azure AD Connect?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
