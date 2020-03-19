---
title: Aanbevolen beleid voor beveiligde e-mail - Microsoft 365 Enterprise | Microsoft Documenten
description: Beschrijft het beleid voor Microsoft-aanbevelingen voor het toepassen van e-mailbeleid en -configuraties.
author: brendacarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: aea95dae0165eb23331b2fa24d5fc752df3f4345
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42807292"
---
# <a name="policy-recommendations-for-securing-email"></a>Beleidsaanbevelingen voor het beveiligen van e-mail

In dit artikel wordt beschreven hoe u het aanbevolen beleid voor identiteits- en apparaattoegangs implementeren om e-mail- en e-mailclients van organisaties te beschermen die moderne verificatie en voorwaardelijke toegang ondersteunen. Deze richtlijnen bouwen voort op het [beleid voor algemene identiteits- en apparaattoegangsbeleid](identity-access-policies.md) en bevatten ook een paar aanvullende aanbevelingen.

Deze aanbevelingen zijn gebaseerd op drie verschillende beveiligings- en beschermingsniveaus die kunnen worden toegepast op basis van de granulariteit van uw behoeften: **basislijn,** **gevoelig**en **sterk gereguleerd**. U meer informatie krijgen over deze beveiligingsniveaus en de aanbevolen clientbesturingssystemen, waarnaar wordt verwezen door deze aanbevelingen in de [aanbevolen beveiligingsbeleidsregels en -configuratiesinleiding.](microsoft-365-policies-configurations.md)

Deze aanbevelingen vereisen dat uw gebruikers moderne e-mailclients gebruiken, waaronder Outlook voor iOS en Android op mobiele apparaten. Outlook voor iOS en Android bieden ondersteuning voor de beste functies van Office 365. Deze mobiele Outlook-apps zijn ook ontworpen met beveiligingsmogelijkheden die mobiel gebruik ondersteunen en samenwerken met andere Cloud-beveiligingsmogelijkheden van Microsoft. Zie [veelgestelde vragen over Outlook voor iOS en Android voor](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)meer informatie.

## <a name="updating-common-policies-to-include-email"></a>Algemeen beleid bijwerken om e-mail op te nemen

In het volgende diagram wordt het algemene beleid voor identiteits- en apparaattoegangsweer uitgelegd en wordt aangegeven welk beleid moet worden bijgewerkt om e-mail te beschermen. Let op de toevoeging van een nieuwe regel voor Exchange Online om ActiveSync-clients te blokkeren. Dit dwingt het gebruik van Outlook mobile.

![Overzicht van beleidsupdates voor het beveiligen van e-mail](../media/identity-access-ruleset-mail.png)

Als u Exchange Online en Outlook hebt opgenomen in het toepassingsgebied van het beleid wanneer u ze instelt, hoeft u alleen het nieuwe beleid te maken om ActiveSync-clients te blokkeren. Bekijk het beleid in de volgende tabel en maak de aanbevolen toevoegingen of bevestig of deze al zijn opgenomen. Elke regel verwijst naar de bijbehorende configuratie-instructies in het artikel [Algemene identiteits- en apparaattoegangsbeleidsregels.](identity-access-policies.md)

|Beschermingsniveau|Beleid|Meer informatie|
|:---------------|:-------|:----------------|
|**Basislijn**|[MFA vereisen wanneer het aanmeldingsrisico *gemiddeld* of *hoog* is](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Exchange Online opnemen in de toewijzing van cloud-apps|
|        |[Clients blokkeren die geen moderne verificatie ondersteunen](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Exchange Online opnemen in de toewijzing van cloud-apps|
|        |[Beleid voor app-beveiliging definiëren](identity-access-policies.md#high-risk-users-must-change-password)|Zorg ervoor dat Outlook is opgenomen in de lijst met apps. Zorg ervoor dat u het beleid voor elk platform bijwerkt (iOS, Android, Windows)|
|        |[Goedgekeurde apps vereisen](identity-access-policies.md#require-approved-apps)|Exchange Online opnemen in de lijst met cloud-apps|
|        |[Compatibele pc's vereisen](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Exchange Online opnemen in lijst met cloud-apps|
|        |[ActiveSync-clients blokkeren](#block-activesync-clients)|Dit nieuwe beleid toevoegen| 
|**Gevoelige**|[MFA vereisen wanneer het aanmeldingsrisico *laag,* *gemiddeld* of *hoog* is](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| Exchange Online opnemen in de toewijzing van cloud-apps|
|         |[Compatibele pc's *en* mobiele apparaten vereisen](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Exchange Online opnemen in de lijst met cloud-apps|
|**Sterk gereguleerd**|[*Altijd* mfa nodig](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Exchange Online opnemen in de toewijzing van cloud-apps|

## <a name="block-activesync-clients"></a>ActiveSync-clients blokkeren

Met dit beleid voorkomt u dat ActiveSync-clients andere regels voor voorwaardelijke toegang omzeilen. De regelconfiguratie is alleen van toepassing op ActiveSync-clients. Door **de goedgekeurde clientapp vereisen te**selecteren, blokkeert dit beleid ActiveSync-clients. Ga als volgt te werk om dit beleid te configureren:

1. Ga naar de [Azure-portal](https://portal.azure.com)en meld u aan met uw referenties. Nadat u zich hebt aangemeld, ziet u het Azure-dashboard.

2. Kies **Azure Active Directory** in het linkermenu.

3. Kies voorwaardelijke **toegang**onder de sectie **Beveiliging** .

4. Kies **Nieuw beleid**.

5. Voer een beleidsnaam in en kies vervolgens de **gebruikers en groepen** waarvoor u het beleid wilt toepassen.

6. Kies **Cloud-apps**.

7. Kies **Apps selecteren**en selecteer Office **365 Exchange Online**. Kies **Selecteren** en **gereed**.

8. Kies **Voorwaarden**en kies **client-apps**.

9. Selecteer **Ja**voor **Configureren.** Controleer alleen het volgende: **mobiele apps en desktopclients** en **Exchange ActiveSync-clients**. Kies **Done**.

10. Kies **Verlenen** in de sectie **Toegangsbesturingselementen.**

11. Kies **Toegang verlenen,** selecteer **Goedgekeurde clientapp vereisen**.  Selecteer Voor meerdere besturingselementen **De geselecteerde besturingselementen vereisen**en kies Selecteer **Selecteren**.

12. Kies **Create**.

## <a name="setup-office-365-message-encryption"></a>Office 365-berichtversleuteling instellen

Met de nieuwe OME-mogelijkheden (Office 365 Message Encryption), die gebruikmaken van de beveiligingsfuncties in Azure Information Protection, kan uw organisatie beveiligde e-mail eenvoudig met iedereen op elk apparaat delen. Gebruikers kunnen beveiligde berichten verzenden en ontvangen met andere Office 365-organisaties en niet-Office 365-klanten die Outlook.com, Gmail en andere e-mailservices gebruiken.

Zie [Nieuwe Office 365-berichtenversleutelingsmogelijkheden instellen](https://support.office.com/article/set-up-new-office-365-message-encryption-capabilities-7ff0c040-b25c-4378-9904-b1b50210d00e)voor meer informatie.

## <a name="next-steps"></a>Volgende stappen

[Meer informatie over beleidsaanbevelingen voor het beveiligen van SharePoint-sites en -bestanden](sharepoint-file-access-policies.md)
