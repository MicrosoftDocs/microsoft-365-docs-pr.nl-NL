---
title: Meervoudige verificatie instellen voor gebruikers
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Meer informatie over het gebruik van beveiligingsstandaards voor het instellen van meervoudige verificatie voor gebruikers.
monikerRange: o365-worldwide
ms.openlocfilehash: c4ea6037b34d29f2d1e05e248e03e49ee6b06f56
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262373"
---
# <a name="set-up-multi-factor-authentication"></a>Meervoudige verificatie instellen
  
> [!IMPORTANT]
> Als u uw abonnement of proefversie na 21 oktober 2019 hebt gekocht en u onverwacht wordt gevraagd om multi-factor authenticatie (MFA), zijn [beveiligingsstandaards](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) automatisch ingeschakeld voor uw abonnement.

Bij elk nieuw Microsoft 365-abonnement is automatisch [beveiligingsstandaards](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) ingeschakeld. Dit betekent dat elke gebruiker multi-factor authenticatie (MFA) moet instellen en de Microsoft Authenticator-app op zijn mobiele apparaat moet installeren. Zie [MFA instellen voor een Microsoft 365-account voor](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14)meer informatie .

De volgende negen beheerdersrollen moeten aanvullende verificatie uitvoeren wanneer ze zich aanmelden:

- Globale beheerder
- SharePoint-beheerder
- Exchange-beheerder
- Beheerder van voorwaardelijke toegang
- Beveiligingsbeheerder
- Helpdesk- of wachtwoordbeheerder
- Factureringsbeheerder
- Gebruikersbeheerder
- Verificatiebeheerder

Alle andere gebruikers wordt gevraagd om indien nodig extra verificatie uit te voeren.

> [!NOTE]
> U moet een globale beheerder zijn om MFA in te stellen of te wijzigen <br><br>
> Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.

Als u MFA eerder hebt ingesteld met basislijnbeleid, [moet u deze uitschakelen om beveiligingsstandaardinstellingen in te schakelen.](#move-from-baseline-policies-to-security-defaults) Als u echter Microsoft 365 Business hebt of als uw abonnement [Azure Active Directory Premium P1 of Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/)bevat, u ook beleid voor voorwaardelijke [toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) instellen. Als u beleid voor voorwaardelijke toegang wilt gebruiken, moet u ervoor zorgen dat beveiligingsstandaards zijn uitgeschakeld en [moderne verificatie](#enable-modern-authentication-for-your-organization) is ingeschakeld.

> [!TIP]
> Zie [Microsoft Authenticator gebruiken met Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411)om uw gebruikers uit te leggen hoe ze de Microsoft Authenticator-app kunnen instellen.

## <a name="manage-security-defaults"></a>Standaardinstellingen voor beveiliging beheren

1. Meld u aan bij het [beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=834822) met globale-beheerdersreferenties.
2. Ga naar de [pagina Azure Active Directory - Eigenschappen](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
3. Kies onderaan de pagina de optie **Standaardinstellingen voor beveiliging beheren**.
4. Kies **Ja** om beveiligingsstandaards in te schakelen en **Nee** om beveiligingsstandaards uit te schakelen en kies **Opslaan**.

## <a name="move-from-baseline-policies-to-security-defaults"></a>Overstappen van basislijnbeleid op standaardinstellingen voor beveiliging

1. Ga naar de [pagina Voorwaardelijke toegang - Beleid](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).
2. Kies elk basislijnbeleid dat is **ingeschakeld** en stel **Beleid inschakelen** in **op Uit**.
3. Ga naar de [pagina Azure Active Directory - Eigenschappen](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
4. Kies onder aan de pagina **De standaardinstellingen voor Beveiliging beheren**en stel in het venster **Standaardinstellingen voor beveiliging inschakelen** **standaard** in om in te schakelen op **Ja**en kies **Vervolgens Opslaan**. 

## <a name="enable-modern-authentication-for-your-organization"></a>Moderne verificatie inschakelen voor uw organisatie

Alle Office 2016-clienttoepassingen bieden ondersteuning voor MFA door middel van de Active Directory Authentication Library (ADAL). Dit betekent dat app-wachtwoorden niet vereist zijn voor Office 2016-clients. Zie [dit artikel](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings#app-passwords) voor meer informatie.

U moet er echter voor zorgen dat uw Microsoft 365-abonnement is ingeschakeld voor ADAL of moderne verificatie.

1. Als u moderne verificatie wilt inschakelen, selecteert u in het [beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=834822) **instellingen** \> **instellingen** en kiest u vervolgens op het tabblad **Services** **Moderne verificatie** in de lijst.

2. Schakel het selectievakje **Moderne verificatie inschakelen (aanbevolen)** in het deelvenster **Moderne verificatie** in en kies **Wijzigingen opslaan**. 

    ![Moderne verificatievenster met selectievakje inschakelen aangevinkt.](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> Vanaf augustus 2017 hebben alle nieuwe Microsoft 365-abonnementen, waaronder Skype voor Bedrijven online en Exchange online, standaard moderne verificatie ingeschakeld. U kunt de status van moderne verificatie voor de webversie van Skype voor Bedrijven controleren via de webversie van Skype voor Bedrijven PowerShell met globale beheerdersreferenties. Voer Get-CsOAuthConfiguration uit om de uitvoer van ClientADALAuthOverride te controleren. Als -ClientADALAuthOverride is 'toegestaan', is moderne verificatie ingeschakeld.
Als u uw MA-status wilt controleren voor Exchange Online, gaat u naar [Moderne verificatie inschakelen in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).

## <a name="related-articles"></a>Verwante artikelen

[Top 10 manieren om Microsoft 365 te beveiligen voor bedrijfsabonnementen](secure-your-business-data.md)

[Moderne verificatie inschakelen voor Office 2013 op Windows-apparaten](enable-modern-authentication.md)
