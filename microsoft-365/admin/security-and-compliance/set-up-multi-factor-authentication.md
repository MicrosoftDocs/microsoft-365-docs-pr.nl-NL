---
title: Meervoudige verificatie instellen voor gebruikers
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Instructies voor het instellen van meervoudige verificatie voor uw organisatie.
monikerRange: o365-worldwide
ms.openlocfilehash: 1bbca8efe09655195605f0610f92c8f66486b940
ms.sourcegitcommit: 09518b7c9146cda7fd42839ee644ad418d48491a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/12/2020
ms.locfileid: "49001499"
---
# <a name="set-up-multi-factor-authentication"></a>Meervoudige verificatie instellen

Gezien uw ervaring met [meervoudige verificatie (MFA) en de bijbehorende ondersteuning in Microsoft 365](multi-factor-authentication-microsoft-365.md), is het tijd om dit in te stellen en te implementeren in uw organisatie.

> [!IMPORTANT]
> Als u na 21 oktober 2019 uw abonnement of proefabonnement hebt afgesloten en u wordt gevraagd om aanvullende verificatie met MFA als u zich aanmeldt, zijn de [standaardinstellingen voor beveiliging](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) automatisch ingeschakeld voor uw abonnement.

## <a name="before-you-begin"></a>Voordat u begint

- U moet een algemeen beheerder zijn om MFA te beheren. Raadpleeg [Over beheerdersrollen](../add-users/about-admin-roles.md) voor meer informatie.
- Als verouderde per persoon-MFA is ingeschakeld, [schakel dit dan uit](#turn-off-legacy-per-user-mfa).
- Als u Office 2013-clients op Windows-apparaten hebt, moet u [Moderne verificatie voor Office 2013-clients inschakelen](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).
- Geavanceerd: Als u adreslijstservices van derden van Active Directory Federation Services (AD FS) hebt, moet u de Azure MFA-server instellen. Raadpleeg [geavanceerde scenario's met Azure Multi-Factor Authentication en VPN-oplossingen van derden](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) voor meer informatie.

## <a name="turn-security-defaults-on-or-off"></a>Standaardinstellingen voor beveiliging in- of uitschakelen

Voor de meeste organisaties bieden standaardinstellingen voor beveiliging een goed niveau aanvullende aanmeldingsbeveiliging. Raadpleeg [Wat zijn standaardinstellingen voor beveiliging?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) voor meer informatie

Als uw abonnement nieuw is, zijn de standaardinstellingen voor beveiliging mogelijk al automatisch ingeschakeld.

U kunt standaardinstellingen voor beveiliging in- of uitschakelen vanuit het deelvenster **Eigenschappen** voor Azure Active Directory (Azure AD) in Azure Portal.

1. Meld u aan bij [Microsoft 365-beheercentrum](https://admin.microsoft.com) met algemeen beheerdersreferenties.
2. Kies in het linker navigatievenster **Alle weergeven** en kies onder **Beheercentra** **Azure Active Directory**.
3. Kies in het **Azure Active Directory-beheercentrum** **Azure Active Directory** \> **-eigenschappen**.
4. Kies onderaan de pagina de optie **Standaardinstellingen voor beveiliging beheren**.
5. Kies **Ja** als u de standaardinstellingen voor beveiliging wilt inschakelen of **Nee** om deze uit te schakelen en kies vervolgens **Opslaan**.

Als u [Beleid voor voorwaardelijke toegang volgens basislijn](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection) gebruikt, zal u gevraagd worden dit uit te schakelen alvorens standaardinstellingen voor beveiliging te gebruiken.

1. Ga naar de [pagina met beleidsregels voor voorwaardelijke toegang](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).
2. Kies elk basislijnbeleid dat **Aan** staat en zet **Beleid inschakelen** **Uit**.
3. Ga naar de [eigenschappenpagina van Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
4. Kies onderaan de pagina de optie **Standaardinstellingen voor beveiliging beheren**.
5. Kies **Ja** als u de standaardinstellingen voor beveiliging wilt inschakelen of **Nee** om deze uit te schakelen en kies vervolgens **Opslaan**.

## <a name="use-conditional-access-policies"></a>Gebruik Beleid voor voorwaardelijke toegang

Als uw organisatie gedetailleerdere beveiligingsbehoeften voor aanmelding heeft, kunt u met Beleid voor voorwaardelijke toegang meer controle krijgen. Met voorwaardelijke toegang kunt u regels maken en definiëren die reageren op aanmeldingsgebeurtenissen en aanvullende acties verzoeken voordat een gebruiker toegang krijgt tot een toepassing of service.

> [!IMPORTANT]
> Schakel zowel per gebruiker-MFA als Standaardinstellingen voor beveiliging uit voordat u Beleid voor voorwaardelijke toegang inschakelt.

Voorwaardelijke toegang is beschikbaar voor klanten die Azure AD Premium P1 hebben aangeschaft of licenties hebben waarin dit is inbegrepen, zoals Microsoft 365 Business Premium en Microsoft 365 E3. Raadpleeg [Een regel voor voorwaardelijke toegang maken](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-azure-mfa) voor meer informatie.

Op risico's gebaseerde voorwaardelijke toegang is beschikbaar met de Azure AD Premium P2-licentie of licenties waarin dit is inbegrepen, zoals Microsoft 365 E5. Raadpleeg [Op risico's gebaseerde voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk) voor meer informatie.

Voor meer informatie over de Azure AD P1 en P2, zie [Prijzen Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).

### <a name="turn-on-modern-authentication-for-your-organization"></a>Moderne verificatie voor uw organisatie inschakelen

Voor de meeste abonnementen wordt moderne verificatie automatisch ingeschakeld, maar als u uw abonnement lang geleden hebt aangeschaft, is dat mogelijk niet het geval. Dit moet worden ingeschakeld voordat MFA correct werkt met Office-apps.

1. In het Microsoft 365-beheercentrum kiest u in het linker navigatievenster **Instellingen** \> **Org-instellingen**.
1. Kies op het tabblad **Services** **Moderne verificatie** en zorg dat in het deelvenster **Moderne verificatie** de optie **Moderne verificatie inschakelen** is geselecteerd. Kies **Wijzigingen opslaan**.

### <a name="turn-off-legacy-per-user-mfa"></a>Verouderde per gebruiker-MFA uitschakelen

Als u eerder per gebruiker-MFA hebt ingeschakeld, moet u dit uitschakelen voordat u de standaardinstellingen voor beveiliging inschakelt.

1. In het Microsoft 365-beheercentrum kiest u in het linker navigatievenster **Gebruikers** \> **Actieve gebruikers**.
1. Kies **Meervoudige verificatie** op de pagina **Actieve gebruikers**.
1. Selecteer elke gebruiker op de pagina Meervoudige verificatie en stel hun meervoudige verificatiestatus in op **Uitgeschakeld**.

## <a name="next-steps"></a>Volgende stappen

- [hoe ze zich kunnen registreren voor de aanvullende verificatiemethode](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [Wat is meervoudige verificatie](https://support.microsoft.com/help/4577374/what-is-multifactor-authentication)
- [hoe ze zich moeten aanmelden na registratie](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [hoe ze de aanvullende verificatiemethode kunnen wijzigen](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
