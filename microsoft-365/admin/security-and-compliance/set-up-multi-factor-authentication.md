---
title: Meervoudige verificatie voor Office 365-gebruikers instellen
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
description: Leer hoe u met de standaardinstellingen voor beveiliging meervoudige verificatie kunt instellen voor Office 365-gebruikers.
monikerRange: o365-worldwide
ms.openlocfilehash: 7e48f72f2fd8cfc5042bd15f994cc98bfa5fca8c
ms.sourcegitcommit: dbbdeca5a6cd048e1bde9e820a8b8a0d6022c7a2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2020
ms.locfileid: "43503969"
---
# <a name="set-up-multi-factor-authentication"></a>Meervoudige verificatie instellen
  
> [!IMPORTANT]
> Als u uw abonnement of proefversie na 21 oktober 2019 hebt gekocht en u onverwacht wordt gevraagd om multi-factor authenticatie (MFA), zijn [beveiligingsstandaards](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) automatisch ingeschakeld voor uw abonnement.

De standaardinstellingen voor beveiliging zijn automatisch ingeschakeld in elk nieuw abonnement op Office 365 voor bedrijven of Microsoft 365 Business. Dit betekent dat elke gebruiker MFA moet instellen en de Microsoft Authenticator-app op zijn mobiele apparaat moet installeren. Zie [Verificatie in twee stappen instellen voor Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14) voor meer informatie.  

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

Alle andere gebruikers wordt gevraagd om indien nodig extra verificatie uit te voeren. Zie [Wat zijn beveiligingsstandaardinstellingen voor](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)meer informatie?

> [!NOTE]
> U moet een globale office 365-beheerder zijn om MFA in te stellen of te wijzigen. <br><br>
> Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.

Als u al een MFA hebt ingesteld met basislijnbeleid, dan [moet u deze uitschakelen en de standaardinstellingen voor beveiliging inschakelen](#move-from-baseline-policies-to-security-defaults). Als u echter Microsoft 365 Business hebt of als uw abonnement [Azure Active Directory Premium P1 of Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/)bevat, u ook beleid voor voorwaardelijke [toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) instellen. Als u beleid voor voorwaardelijke toegang wilt gebruiken, moet u ervoor zorgen dat [moderne verificatie](#enable-modern-authentication-for-your-organization) is ingeschakeld.

> [!TIP]
> Ga naar [Microsoft Authenticator gebruiken met Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1) als u uw gebruikers wilt uitleggen hoe ze de Authenticator-app moeten instellen.

## <a name="manage-security-defaults"></a>Standaardinstellingen voor beveiliging beheren

1. Meld u aan bij het [beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=834822) met uw globale-beheerdersreferenties.
2. Ga naar [Azure Active Directory-eigenschappen](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
3. Kies onderaan de pagina de optie **Standaardinstellingen voor beveiliging beheren**.
4. Kies **Ja** om beveiligingsstandaards in te schakelen of **Nee** om beveiligingsstandaards uit te schakelen en kies **Opslaan**.

## <a name="move-from-baseline-policies-to-security-defaults"></a>Overstappen van basislijnbeleid op standaardinstellingen voor beveiliging

1. Selecteer in het [beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=834822) **Alles weergeven**en vervolgens **Azure Active Directory** onder **Beheercentra**.

2. Kies azure **Active Directory** > **Security**in het Azure **Active Directory-beheercentrum** .

3. Wat de **zekerheid heeft : Aan de slag** pagina, kies **Voorwaardelijke toegang**. 

4. Kies op de pagina **Voorwaardelijke toegang tot beleid** elk basislijnbeleid dat is **ingeschakeld**en stel deze in op **Uit**.
5. Ga naar de pagina [Azure Active Directory-eigenschappen](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
6. Kies onder aan de pagina **De standaardinstellingen voor Beveiliging beheren**en stel in het venster **Standaardinstellingen voor beveiliging inschakelen** **standaard** in om in te schakelen op **Ja**en kies **Vervolgens Opslaan**. 

## <a name="enable-modern-authentication-for-your-organization"></a>Moderne verificatie inschakelen voor uw organisatie

Alle Office 2016-clienttoepassingen bieden ondersteuning voor MFA door middel van de Active Directory Authentication Library (ADAL). Dit betekent dat app-wachtwoorden niet vereist zijn voor Office 2016-clients. U moet er echter voor zorgen dat uw Office 365-abonnement is ingeschakeld voor ADAL of voor moderne verificatie.

1. Als u moderne verificatie wilt inschakelen, gaat u naar het [Beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=834822) en selecteert u **Instellingen** \> **Instellingen**. Vervolgens kiest u op het tabblad **Services** de optie ** Moderne verificatie** in de lijst.

2. Schakel het selectievakje **Moderne verificatie inschakelen (aanbevolen)** in het deelvenster **Moderne verificatie** in en kies **Wijzigingen opslaan**. 

    ![Moderne verificatievenster met selectievakje inschakelen aangevinkt.](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> Moderne verificatie is vanaf augustus 2017 standaard ingeschakeld voor alle nieuwe Office 365-tenants met de webversie van Skype voor Bedrijven en Exchange Online. U kunt de status van moderne verificatie voor de webversie van Skype voor Bedrijven controleren via de webversie van Skype voor Bedrijven PowerShell met globale beheerdersreferenties. Voer Get-CsOAuthConfiguration uit om de uitvoer van ClientADALAuthOverride te controleren. Als -ClientADALAuthOverride is 'toegestaan', is moderne verificatie ingeschakeld.

Als u uw MA-status wilt controleren voor Exchange Online, gaat u naar [Moderne verificatie inschakelen in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).

## <a name="related-articles"></a>Verwante artikelen

[De 10 beste manieren om Office 365- en Microsoft 365 Business-abonnementen te beveiligen](secure-your-business-data.md)

[Moderne verificatie inschakelen voor Office 2013 op Windows-apparaten](enable-modern-authentication.md)
