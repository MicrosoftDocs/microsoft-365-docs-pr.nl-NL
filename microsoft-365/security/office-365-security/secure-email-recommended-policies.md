---
title: Aanbevolen e-mailbeleid beveiligen - Microsoft 365 voor ondernemingen | Microsoft Docs
description: Hier worden de beleidsregels voor Microsoft-aanbevelingen beschreven voor het toepassen van e-mailbeleid en -configuraties.
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
ms.openlocfilehash: 4651f220e88bf5161a8ddfe4e2bdde03118afa15
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288477"
---
# <a name="policy-recommendations-for-securing-email"></a>Beleidsaanbevelingen voor het beveiligen van e-mail

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)


In dit artikel wordt beschreven hoe u het aanbevolen beleid voor identiteits- en apparaattoegang implementeert ter bescherming van e-mail- en e-mail clients van de organisatie die ondersteuning bieden voor moderne verificatie en voorwaardelijke toegang. Deze richtlijnen zijn gebaseerd op het algemene beleid voor identiteits- en [apparaattoegang](identity-access-policies.md) en bevat ook een paar extra aanbevelingen.

Deze aanbevelingen zijn gebaseerd op drie verschillende beveiligingslagen en -beveiliging die kunnen worden toegepast op basis van de granulatie van uw behoeften: **baseline,** **sensitive** en **sterk reguleerd.** Meer informatie over deze beveiligingslagen en de aanbevolen clientbesturingssystemen waarnaar wordt verwezen door deze aanbevelingen in de aanbevolen inleiding tot beveiligingsbeleid [en configuraties.](microsoft-365-policies-configurations.md)

Deze aanbevelingen vereisen dat uw gebruikers moderne e-mailcl clients gebruiken, waaronder Outlook voor iOS en Android op mobiele apparaten. Outlook voor iOS en Android biedt ondersteuning voor de beste functies van Office 365. Deze mobiele Outlook-apps zijn ook ontworpen met beveiligingsmogelijkheden die mobiel gebruik ondersteunen en samenwerken met andere cloudbeveiligingsfuncties van Microsoft. Zie veelgestelde vragen [over Outlook voor iOS en Android voor meer informatie.](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)

## <a name="update-common-policies-to-include-email"></a>Algemene beleidsregels bijwerken om e-mail op te nemen

Ter bescherming van e-mail ziet u in het volgende diagram welk beleid moet worden bijgewerkt op basis van het algemene identiteits- en apparaattoegangsbeleid.

[![Overzicht van beleidsupdates voor het beschermen van de toegang tot Teams en de afhankelijke services ervan](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

[Een grotere versie van deze afbeelding bekijken](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

Houd rekening met de toevoeging van een nieuw beleid voor Exchange Online om ActiveSync-clients te blokkeren. Dit dwingt het gebruik van Outlook Mobile af.

Als u Exchange Online en Outlook hebt opgenomen in het bereik van het beleid tijdens het instellen, hoeft u alleen het nieuwe beleid te maken om ActiveSync-clients te blokkeren. Bekijk de beleidsregels in de volgende tabel en gebruik de aanbevolen toevoegingen of bevestig dat deze al zijn opgenomen. Elk beleid is gekoppeld aan de bijbehorende configuratie-instructies in [common identity- en apparaattoegangsbeleid.](identity-access-policies.md)

|Beveiligingsniveau|Beleidsregels|Meer informatie|
|---|---|---|
|**Basislijn**|[MFA vereisen wanneer het aanmeldingsrisico *gemiddeld* of *hoog is*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Exchange Online opnemen in de toewijzing van cloud-apps|
||[Clients blokkeren die moderne verificatie niet ondersteunen](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Exchange Online opnemen in de toewijzing van cloud-apps|
||[Beleid voor app-gegevensbescherming toepassen](identity-access-policies.md#apply-app-data-protection-policies)|Zorg ervoor dat Outlook is opgenomen in de lijst met apps. Zorg ervoor dat u het beleid voor elk platform bijwerkt (iOS, Android, Windows)|
||[Goedgekeurde apps en APP-beveiliging vereisen](identity-access-policies.md#require-approved-apps-and-app-protection)|Exchange Online opnemen in de lijst met cloud-apps|
||[Eis conforme pc’s](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Exchange Online opnemen in de lijst met cloud-apps|
||[ActiveSync-clients blokkeren](#block-activesync-clients)|Dit nieuwe beleid toevoegen|
|**Gevoelig**|[MFA vereisen wanneer het aanmeldingsrisico *laag,* *gemiddeld* of *hoog is*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Exchange Online opnemen in de toewijzing van cloud-apps|
||[Compatibele pc's *en mobiele* apparaten vereisen](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Exchange Online opnemen in de lijst met cloud-apps|
|**Sterk gereglementeerd**|[*Altijd* MFA vereisen](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Exchange Online opnemen in de toewijzing van cloud-apps|
|

## <a name="block-activesync-clients"></a>ActiveSync-clients blokkeren

Met dit beleid wordt voorkomen dat ActiveSync-clients andere beleidsregels voor voorwaardelijke toegang omzeilen. De beleidsconfiguratie geldt alleen voor ActiveSync-clients. Als u **[het beveiligingsbeleid voor apps vereist](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)** selecteert, wordt ActiveSync-clients met dit beleid niet meer geselecteerd. Meer informatie over het maken van dit beleid vindt u in het beveiligingsbeleid voor apps vereisen voor toegang tot [cloud-apps met voorwaardelijke toegang.](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)

- Volg 'Stap 2: Configureer een beleid voor voorwaardelijke toegang van Azure AD voor Exchange Online met ActiveSync (EAS)' in [scenario 1: Voor Office 365-apps](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)zijn goedgekeurde apps met app-beveiligingsbeleid vereist, waardoor Exchange ActiveSync-clients geen verbinding kunnen maken met Exchange Online via basisverificatie.

U kunt ook verificatiebeleid gebruiken om [basisverificatie](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)uit te schakelen, waardoor alle aanvragen voor clienttoegang moderne verificatie moeten gebruiken.

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a>Toegang tot Exchange Online beperken vanuit de webversie van Outlook

U kunt de mogelijkheid voor gebruikers beperken om bijlagen te downloaden van de webversie van Outlook op umnanaged-apparaten. Gebruikers op deze apparaten kunnen deze bestanden weergeven en bewerken met Office Online zonder dat ze de bestanden op het apparaat kunnen lekken en opslaan. U kunt ook blokkeren dat gebruikers bijlagen kunnen zien op een onmanaged apparaat.

Dit doet u als volgt:

1. [Maak verbinding met een externe PowerShell-sessie van Exchange Online.](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)
2. Als u nog geen OWA-postvakbeleid hebt, maakt u er een met de cmdlet [New-OwaMailboxPolicy.](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy)
3. Als u wilt toestaan dat bijlagen worden bekeken, maar niet worden gedownload, gebruikt u deze opdracht:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. Als u bijlagen wilt blokkeren, gebruikt u deze opdracht:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

5. Maak in de Azure Portal een nieuw beleid voor voorwaardelijke toegang met de volgende instellingen:

   **Opdrachten** \> **Gebruikers en groepen:** selecteer de juiste gebruikers en groepen die u wilt opnemen en uitsluiten.

   **Opdrachten** \> **Cloud-apps of -acties** \> **Cloud-apps** \> **Opnemen** \> **Apps selecteren:** **Office 365 Exchange Online selecteren**

   **Access-besturingselementen** \> **Sessie:** **Door app afgedwongen beperkingen gebruiken selecteren**

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a>Vereisen dat iOS- en Android-apparaten Outlook gebruiken

Om ervoor te zorgen dat gebruikers van iOS- en Android-apparaten alleen toegang hebben tot werk- of schoolinhoud met Outlook voor iOS en Android, hebt u een beleid voor voorwaardelijke toegang nodig dat is gericht op die potentiële gebruikers.

Zie de stappen voor het configureren van dit beleid in Toegang voor samenwerking via berichten beheren met [Outlook voor iOS en Android.]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access)

## <a name="set-up-message-encryption"></a>Berichtversleuteling instellen

Met de nieuwe office 365-berichtversleutelingsfuncties (OME), die gebruikmaken van de beveiligingsfuncties in Azure Information Protection, kan uw organisatie beveiligde e-mail gemakkelijk delen met iedereen op elk apparaat. Gebruikers kunnen beveiligde berichten verzenden en ontvangen met andere Microsoft 365-organisaties en niet-klanten die Outlook.com, Gmail en andere e-mailservices gebruiken.

Zie Nieuwe office [365-berichtversleutelingsfuncties instellen voor meer informatie.](../../compliance/set-up-new-message-encryption-capabilities.md)

## <a name="next-steps"></a>Volgende stappen

![Stap 4: Beleid voor Microsoft 365-cloud-apps](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Beleidsregels voor voorwaardelijke toegang configureren voor:

- [Microsoft Teams](teams-access-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
