---
title: 'Aanbevolen beleidsregels voor beveiliging van e-mail: Microsoft 365 for Enterprise | Microsoft docs'
description: Een beschrijving van de beleidsregels voor Microsoft-aanbevelingen over het toepassen van e-mail beleidsregels en configuraties.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- remotework
- m365solution-identitydevice
- m365solution-scenario
ms.openlocfilehash: c8a1609bed124789229c6ae6d1f80b7d9c70bb66
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646809"
---
# <a name="policy-recommendations-for-securing-email"></a>Beleids aanbevelingen voor beveiliging van e-mail

In dit artikel wordt uitgelegd hoe u de aanbevolen identiteit en het beleid voor het openen van e-mailberichten en e-mail cliënten voor e-mail en e-mail clients beschermt die ondersteuning bieden voor moderne verificatie en voorwaardelijke toegang. Deze richtlijnen zijn van toepassing op de [gangbare beleidsregels voor identiteits-en Apparaattoegang](identity-access-policies.md) en bevat ook een paar extra aanbevelingen.

Deze aanbevelingen maken deel uit van drie verschillende niveaus voor beveiliging en bescherming die op basis van de granulatie van uw behoeften kunnen worden toegepast: **basislijn**, **gevoelige**en **nadrukkelijk gereglementeerde**. U vindt meer informatie over deze beveiligingslagen en de aanbevolen besturingssystemen van de client, waarnaar wordt verwezen door deze aanbevelingen in het [Aanbevolen beveiligingsbeleid en de introductie van configuraties](microsoft-365-policies-configurations.md).

Voor deze aanbevelingen moeten uw gebruikers moderne e-mailclients gebruiken, waaronder Outlook voor iOS en Android op een mobiel apparaat. Outlook voor iOS en Android bieden ondersteuning voor de beste functies van Office 365. Deze mobiele Outlook-apps zijn ook samengesteld met beveiligingsfuncties die ondersteuning bieden voor mobiele gebruikers en werken samen met andere mogelijkheden van Microsoft Cloud-beveiliging. Voor meer informatie raadpleegt u [Veelgestelde vragen over Outlook voor IOS en Android](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).

## <a name="update-common-policies-to-include-email"></a>Veelgebruikte beleidsregels bijwerken voor het opnemen van e-mail

In het volgende diagram ziet u welke beleidsregels u moet bijwerken vanuit de veelgebruikte beleidsregels voor identiteit en Apparaattoegang.

[![Overzicht van beleidsupdates voor de bescherming van de toegang tot teams en de afhankelijke services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

[Een grotere versie van deze afbeelding weergeven](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

Let op het toevoegen van een nieuw beleid voor Exchange Online om ActiveSync-clients te blokkeren. Hiermee wordt het gebruik van Outlook Mobile geforceerd.

Als u Exchange Online en Outlook hebt opgenomen in het bereik van de beleidsregels wanneer u deze instelt, hoeft u alleen het nieuwe beleid te maken om ActiveSync-clients te blokkeren. Bekijk de beleidsregels die in de volgende tabel worden vermeld en maak de aanbevolen toevoegingen, of Controleer of deze al zijn opgenomen. Elk beleid koppelt aan de gekoppelde configuratie-instructies in een [gemeenschappelijk identiteits-en toegangsbeleid voor apparaten](identity-access-policies.md).

|Beveiligingsniveau|Lijnen|Meer informatie|
|:---------------|:-------|:----------------|
|**Basislijn**|[MFA vereisen wanneer het aanmeld risico *normaal* of *hoog* is](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Exchange Online opnemen in de toewijzing van Cloud-apps|
|        |[Clients blokkeren die moderne verificatie niet ondersteunen](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Exchange Online opnemen in de toewijzing van Cloud-apps|
|        |[Beleid voor APP-gegevensbeveiliging toepassen](identity-access-policies.md#apply-app-data-protection-policies)|Zorg ervoor dat Outlook is opgenomen in de lijst met apps. Zorg ervoor dat u het beleid voor elk platform (iOS, Android, Windows) bijwerkt.|
|        |[Goedgekeurde apps en APP-beveiliging vereisen](identity-access-policies.md#require-approved-apps-and-app-protection)|Exchange Online opnemen in de lijst met Cloud-apps|
|        |[Eis conforme pc’s](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Exchange Online opnemen in de lijst met Cloud-apps|
|        |[ActiveSync-clients blokkeren](#block-activesync-clients)|Dit nieuwe beleid toevoegen| 
|**Gevoelig**|[MFA vereisen wanneer het aanmeld risico *slecht*, *gemiddeld* of *hoog* is](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| Exchange Online opnemen in de toewijzing van Cloud-apps|
|         |[Compatibele Pc's *en* mobiele apparaten vereisen](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Exchange Online opnemen in de lijst met Cloud-apps|
|**Sterk gereglementeerd**|[*Altijd* MFA vereisen](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Exchange Online opnemen in de toewijzing van Cloud-apps|

## <a name="block-activesync-clients"></a>ActiveSync-clients blokkeren

Dit beleid voorkomt dat ActiveSync-clients andere beleidsregels voor voorwaardelijke toegang negeren. De beleidsconfiguratie geldt alleen voor ActiveSync-clients. Met dit beleid moet u ActiveSync-clients blokkeren om het **[beveiligingsbeleid voor apps vereisen](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)**. Meer informatie over het maken van dit beleid vindt u in het [beleid voor app-beveiliging vereisen voor toegang tot de Cloud-app met voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

- Ga als volgt te werk: ' stap 2: Configureer een Azure AD-beleid voor voorwaardelijke toegang voor Exchange Online met ActiveSync (EAS) ' in [scenario 1: voor Office 365-apps zijn goedgekeurde apps vereist met een app-beveiligingsbeleid](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), waardoor Exchange ActiveSync-clients niet via basisverificatie verbinding maken met Exchange Online.

U kunt ook authenticatiebeleid gebruiken om [Basisverificatie uit te schakelen](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online), waardoor alle aanvragen voor clienttoegang worden gebruikt voor moderne verificatie.

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a>Toegang tot Exchange Online vanuit de webversie van Outlook beperken

U kunt beperkingen instellen voor de mogelijkheid dat gebruikers bijlagen downloaden van de webversie van Outlook op umnanaged-apparaten. Gebruikers op deze apparaten kunnen deze bestanden weergeven en bewerken met behulp van Office Online zonder de bestanden op het apparaat te lekt en op te slaan. U kunt ervoor zorgen dat gebruikers ook bijlagen kunnen zien op een niet-beheerd apparaat.

Dit doet u als volgt:

1. [Maak verbinding met een externe PowerShell-sessie van Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).
2. Als u nog geen OWA-postvak beleid hebt, kunt u er een maken met de [nieuwe OwaMailboxPolicy-](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy) cmdlet.
3. Gebruik de volgende opdracht als u het weergeven van bijlagen wilt toestaan, maar niet wilt downloaden:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. Als u bijlagen wilt blokkeren, gebruikt u deze opdracht:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

4. Maak in de Azure-Portal een nieuw beleid voor voorwaardelijke toegang met de volgende instellingen:

   **Toewijzingen > gebruikers en groepen**: Selecteer de juiste gebruikers en groepen die u wilt opnemen en uitsluiten.

   **Toewijzingen > Cloud-apps of-acties > Cloud-apps > zijn > Select apps**: **Office 365 Exchange Online** selecteren

   **> sessie van Access-besturingselementen**: Selecteer door **apps gehandhaafde beperkingen gebruiken**

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a>Vereisen dat iOS-en Android-apparaten Outlook gebruiken

Om ervoor te zorgen dat de gebruikers van iOS-en Android-apparaten alleen toegang hebben tot uw werk-of school inhoud met behulp van Outlook voor iOS en Android, moet u beschikken over een voorwaardelijk toegangsbeleid dat de potentiële gebruikers bedoelt.

Zie de stappen voor het configureren van dit beleid in [Access voor samenwerking via E-mail beheren met Outlook voor IOS en Android]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access).


## <a name="set-up-message-encryption"></a>Bericht versleuteling instellen

Met de nieuwe functies voor het versleutelen van Office 365-berichten versleutelen (OME) die gebruikmaken van de beveiligingsfuncties in azure Information Protection kunt u in uw organisatie eenvoudig beveiligde e-mail delen met iedereen op elk apparaat. Gebruikers kunnen beveiligde berichten verzenden en ontvangen met andere Microsoft 365-organisaties, evenals niet-klanten die gebruikmaken van Outlook.com, Gmail en andere e-mailservices.

Voor meer informatie raadpleegt [u nieuwe functies in Office 365-berichten versleutelen instellen](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities).

## <a name="next-steps"></a>Volgende stappen

![Stap 4: beleidsregels voor Microsoft 365 Cloud-apps](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Beleidsregels voor voorwaardelijke toegang configureren voor:

- [Microsoft Teams](teams-access-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)