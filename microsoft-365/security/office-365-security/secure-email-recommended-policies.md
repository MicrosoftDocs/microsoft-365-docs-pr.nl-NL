---
title: Aanbevolen e-mailbeleid beveiligen- Microsoft 365 voor bedrijven | Microsoft Docs
description: Beschrijft het beleid voor Microsoft-aanbevelingen voor het toepassen van e-mailbeleid en -configuraties.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
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
ms.technology: mdo
ms.openlocfilehash: c5f5837f4e4069a67bc080178fefd10bd2a08629
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599849"
---
# <a name="policy-recommendations-for-securing-email"></a>Beleidsaanbevelingen voor het beveiligen van e-mail

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)

In dit artikel wordt beschreven hoe u het aanbevolen beleid voor identiteits- en apparaattoegang implementeert om e-mail- en e-mail clients van organisaties te beschermen die moderne verificatie en voorwaardelijke toegang ondersteunen. Deze richtlijnen zijn gebaseerd op het beleid voor algemene [identiteits-](identity-access-policies.md) en apparaattoegang en bevat ook enkele extra aanbevelingen.

Deze aanbevelingen zijn gebaseerd op drie verschillende beveiligings- en beveiligingslagen die kunnen worden toegepast op basis van de granulariteit van uw behoeften: **basislijn** **,** gevoelig en sterk **geregeld**. U vindt meer informatie over deze beveiligingslagen en de aanbevolen clientbesturingssystemen, waarnaar wordt verwezen in deze aanbevelingen in de aanbevolen introductie van beveiligingsbeleid [en configuraties.](microsoft-365-policies-configurations.md)

Deze aanbevelingen vereisen dat uw gebruikers moderne e-mailcl clients gebruiken, Outlook voor iOS en Android op mobiele apparaten. Outlook voor iOS en Android bieden ondersteuning voor de beste functies van Office 365. Deze mobiele Outlook apps zijn ook ontworpen met beveiligingsmogelijkheden die mobiel gebruik ondersteunen en samenwerken met andere beveiligingsmogelijkheden voor microsoft-cloud. Zie veelgestelde vragen [Outlook voor iOS en Android](/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)voor meer informatie.

## <a name="update-common-policies-to-include-email"></a>Algemene beleidsregels bijwerken om e-mail op te nemen

Als u e-mail wilt beveiligen, wordt in het volgende diagram weergegeven welk beleid moet worden bijgewerkt op basis van het algemene beleid voor identiteits- en apparaattoegang.

[![Overzicht van beleidsupdates voor het beschermen van de Teams en de afhankelijke services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

Let op de toevoeging van een nieuw beleid voor Exchange Online ActiveSync-clients te blokkeren. Dit dwingt het gebruik van Outlook mobiele apparaten.

Als u tijdens het instellen Exchange Online en Outlook in het bereik van het beleid hebt opgenomen, hoeft u alleen het nieuwe beleid te maken om ActiveSync-clients te blokkeren. Bekijk de beleidsregels in de volgende tabel en maak de aanbevolen toevoegingen of bevestig dat deze al zijn opgenomen. Elk beleid wordt gekoppeld aan de bijbehorende configuratie-instructies in [Gemeenschappelijk beleid voor identiteits- en apparaattoegang.](identity-access-policies.md)

|Beveiligingsniveau|Beleid|Meer informatie|
|---|---|---|
|**Basislijn**|[MFA vereisen wanneer het aanmeldingsrisico gemiddeld *of* *hoog* is](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Een Exchange Online opnemen in de toewijzing van cloud-apps|
||[Clients blokkeren die moderne verificatie niet ondersteunen](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Een Exchange Online opnemen in de toewijzing van cloud-apps|
||[APP-beleid voor gegevensbescherming toepassen](identity-access-policies.md#apply-app-data-protection-policies)|Zorg ervoor Outlook is opgenomen in de lijst met apps. Zorg ervoor dat u het beleid voor elk platform bijwerkt (iOS, Android, Windows)|
||[Goedgekeurde apps en APP-beveiliging vereisen](identity-access-policies.md#require-approved-apps-and-app-protection)|Een Exchange Online opnemen in de lijst met cloud-apps|
||[Eis conforme pc’s](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Een Exchange Online opnemen in de lijst met cloud-apps|
||[ActiveSync-clients blokkeren](#block-activesync-clients)|Dit nieuwe beleid toevoegen|
|**Gevoelig**|[MFA vereisen wanneer het aanmeldingsrisico *laag,* *gemiddeld* of *hoog is*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Een Exchange Online opnemen in de toewijzing van cloud-apps|
||[Compatibele pc's *en mobiele* apparaten vereisen](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Een Exchange Online opnemen in de lijst met cloud-apps|
|**Sterk gereglementeerd**|[*Altijd* MFA vereisen](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Een Exchange Online opnemen in de toewijzing van cloud-apps|
|

## <a name="block-activesync-clients"></a>ActiveSync-clients blokkeren

Dit beleid voorkomt dat ActiveSync-clients andere beleidsregels voor voorwaardelijke toegang omzeilen. De beleidsconfiguratie is alleen van toepassing op ActiveSync-clients. Door **[App-beveiligingsbeleid vereisen te selecteren,](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)** worden ActiveSync-clients met dit beleid blokkeert. Details over het maken van dit beleid vindt u in [App-beveiligingsbeleid vereisen voor toegang tot cloud-apps met voorwaardelijke toegang.](/azure/active-directory/conditional-access/app-protection-based-conditional-access)

- Volg 'Stap 2: Een Azure AD Conditional Access-beleid configureren voor Exchange Online met ActiveSync (EAS)' in [scenario 1: Office 365-apps](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)vereisen goedgekeurde apps met app-beveiligingsbeleid, waardoor Exchange ActiveSync-clients geen verbinding kunnen maken met Exchange Online.

U kunt ook verificatiebeleid gebruiken om [Basisverificatie uit te](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)schakelen, waardoor alle aanvragen voor clienttoegang moderne verificatie moeten gebruiken.

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a>De toegang tot Exchange Online van Outlook op internet beperken

U kunt de mogelijkheid voor gebruikers om bijlagen te downloaden van Outlook op internet op umnanaged-apparaten beperken. Gebruikers op deze apparaten kunnen deze bestanden bekijken en bewerken met Office Online zonder de bestanden op het apparaat te lekken en op te slaan. U kunt ook blokkeren dat gebruikers bijlagen zien op een niet-bemand apparaat.

Dit doet u als volgt:

1. [Verbinding maken naar een Exchange Online Externe PowerShell-sessie](/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).
2. Als u nog geen OWA-postvakbeleid hebt, maakt u er een met de [cmdlet New-OwaMailboxPolicy.](/powershell/module/exchange/new-owamailboxpolicy)
3. Als u het weergeven van bijlagen wilt toestaan, maar niet wilt downloaden, gebruikt u deze opdracht:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. Als u bijlagen wilt blokkeren, gebruikt u deze opdracht:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

5. Maak in de Azure-portal een nieuw beleid voor voorwaardelijke toegang met de volgende instellingen:

   **Opdrachten** \> **Gebruikers en groepen:** Selecteer de juiste gebruikers en groepen die u wilt opnemen en uitsluiten.

   **Opdrachten** \> **Cloud-apps of -acties** \> **Cloud-apps** \> **Opnemen** \> **Apps selecteren**: Selecteer **Office 365 Exchange Online**

   **Toegangsbesturingselementen** \> **Sessie:** Selecteer **App afdwingbare beperkingen gebruiken**

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a>Vereisen dat iOS- en Android-apparaten deze Outlook

Als u ervoor wilt zorgen dat gebruikers van iOS- en Android-apparaten alleen toegang hebben tot werk- of schoolinhoud met Outlook voor iOS en Android, hebt u een beleid voor voorwaardelijke toegang nodig dat is gericht op die potentiële gebruikers.

Bekijk de stappen voor het configureren van dit beleid in Toegang tot samenwerking via berichten beheren met [Outlook voor iOS en Android.](/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access)

## <a name="set-up-message-encryption"></a>Berichtversleuteling instellen

Met de nieuwe Office 365-berichtversleuteling (OME) die gebruikmaken van de beveiligingsfuncties in Azure Information Protection, kan uw organisatie eenvoudig beveiligde e-mail delen met iedereen op elk apparaat. Gebruikers kunnen beveiligde berichten verzenden en ontvangen met andere Microsoft 365 organisaties en niet-klanten met Outlook.com, Gmail en andere e-mailservices.

Zie Nieuwe functies voor [Office 365-berichtversleuteling instellen voor meer informatie.](../../compliance/set-up-new-message-encryption-capabilities.md)

## <a name="next-steps"></a>Volgende stappen

![Stap 4: Beleid voor Microsoft 365 cloud-apps](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Beleid voor voorwaardelijke toegang configureren voor:

- [Microsoft Teams](teams-access-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
