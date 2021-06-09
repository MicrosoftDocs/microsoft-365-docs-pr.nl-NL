---
title: 'Microsoft 365 Client-app-ondersteuning: verificatie op basis van certificaten'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: In dit artikel vindt u meer informatie over Microsoft 365 client-app-ondersteuning voor verificatie op basis van certificaten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d5ebef7c10aa61ba28c8fb841468be244f6e8542
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904989"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Microsoft 365 Client-app-ondersteuning: verificatie op basis van certificaten

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Moderne verificatie is een overkoepelende term voor een combinatie van verificatie- en autorisatiemethoden. Deze methoden zijn:

- **Verificatiemethoden:** Meervoudige verificatie; Clientcertificaatverificatie.
- **Autorisatiemethoden**: Microsoft's implementatie van Open Authorization (OAuth).

Moderne verificatie is ingeschakeld met behulp van een verificatiebibliotheek, zoals Active Directory Authentication Library (ADAL) of Microsoft Authentication Library (MSAL). Moderne verificatie is wat clients gebruiken voor het verifiëren en machtigen van toegang tot Microsoft 365 resources. Moderne verificatie maakt gebruik van OAuth en biedt een veilig mechanisme voor clients voor toegang tot Microsoft 365 services, zonder dat hiervoor toegang tot gebruikersreferenties is vereist. Bij aanmelding verifieert de gebruiker zich rechtstreeks met Azure Active Directory en ontvangt hij/zij een access/refresh-tokenpaar. Het toegangs token verleent de client toegang tot de juiste resources in de Microsoft 365 tenant. Een vernieuwings-token wordt gebruikt om een nieuw toegangs- of vernieuwings-tokenpaar te verkrijgen wanneer het huidige toegangs-token verloopt.

Moderne verificatie ondersteunt verschillende verificatiemechanismen, zoals verificatie op basis van certificaten. Clients op Windows, Android- of iOS-apparaten kunnen verificatie op basis van certificaten (CBA) gebruiken om zich te verifiëren Azure Active Directory met behulp van een clientcertificaat op het apparaat. In plaats van een gewone gebruikersnaam/wachtwoord wordt het certificaat gebruikt om een access/refresh token pair te verkrijgen van Azure Active Directory.

Meer informatie over [verificatie op basis van certificaten.](/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started)

## <a name="supported-clients--platforms"></a>Ondersteunde clients & platforms

De nieuwste versies van de volgende clients en platforms ondersteunen verificatie op basis van certificaten wanneer u zich aanmeldt bij Azure Active Directory-accounts binnen de client (bijvoorbeeld bij het toevoegen van een account aan de app). Zie Systeemvereisten voor Microsoft 365 voor meer informatie over platformondersteuning [in Microsoft 365.](/microsoft-365/microsoft-365-and-office-resources)
<br>
<br>

[!INCLUDE [Certificate-based authentication services support table](../includes/microsoft-365-client-support-certificate-based-authentication-include.md)]

>[!NOTE]
>Edge voor iOS en Android ondersteunt verificatie op basis van certificaten tijdens account add flows. Edge voor iOS en Android biedt geen ondersteuning voor verificatie op basis van certificaten bij het uitvoeren van verificatie tegen websites, meestal intranetsites. <br><br>  In dit scenario navigeert een gebruiker naar een website (meestal op het intranet) waar de website vereist dat de gebruiker zich verifieert via een certificaat. Hierbij is helemaal geen moderne verificatie vereist en wordt geen gebruik gemaakt van een Microsoft-verificatiebibliotheek. Dit komt door een beperking met iOS: iOS voorkomt dat apps van derden toegang krijgen tot de systeemsleutelhanger waar de certificaten zijn opgeslagen (alleen Apple-apps en de [Safari-webviewcontroller](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) hebben toegang tot de systeemsleutelhanger). <br><br> Omdat Edge afhankelijk is van het [WebKit-framework](https://developer.apple.com/documentation/webkit) voor het renderen van websites, heeft Edge geen toegang tot de systeemsleutelhanger en kan de gebruiker geen certificaatkeuze geven. Dit komt helaas door de architectuur van Apple.

## <a name="supported-powershell-modules"></a>Ondersteunde PowerShell-modules

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

