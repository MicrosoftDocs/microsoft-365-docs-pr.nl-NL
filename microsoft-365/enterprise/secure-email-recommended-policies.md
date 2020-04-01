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
- remotework
ms.openlocfilehash: d04070bfcec0649c5c4a1a79c082f5c5b43ad5eb
ms.sourcegitcommit: a7b2cd892cb65a61ee246268e1af2f8b9e526f6b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2020
ms.locfileid: "43081290"
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
|        |[Cliënten blokkeren die geen moderne verificatie ondersteunen](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Exchange Online opnemen in de toewijzing van cloud-apps|
|        |[App-beleid voor gegevensbescherming toepassen](identity-access-policies.md#apply-app-data-protection-policies)|Zorg ervoor dat Outlook is opgenomen in de lijst met apps. Zorg ervoor dat u het beleid voor elk platform bijwerkt (iOS, Android, Windows)|
|        |[Goedgekeurde apps en APP-beveiliging vereisen](identity-access-policies.md#require-approved-apps-and-app-protection)|Exchange Online opnemen in de lijst met cloud-apps|
|        |[Eis conforme pc’s](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Exchange Online opnemen in lijst met cloud-apps|
|        |[ActiveSync-clients blokkeren](#block-activesync-clients)|Dit nieuwe beleid toevoegen| 
|**Gevoelig**|[MFA vereisen wanneer het aanmeldingsrisico *laag,* *gemiddeld* of *hoog* is](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| Exchange Online opnemen in de toewijzing van cloud-apps|
|         |[Compatibele pc's *en* mobiele apparaten vereisen](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Exchange Online opnemen in de lijst met cloud-apps|
|**Sterk gereglementeerd**|[*Altijd* mfa nodig](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Exchange Online opnemen in de toewijzing van cloud-apps|

## <a name="block-activesync-clients"></a>ActiveSync-clients blokkeren

Met dit beleid voorkomt u dat ActiveSync-clients andere regels voor voorwaardelijke toegang omzeilen. De regelconfiguratie is alleen van toepassing op ActiveSync-clients. Door **[het beleid voor app-beveiliging vereisen te selecteren,](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)** blokkeert dit beleid ActiveSync-clients. Details over het maken van dit beleid vindt u in [Het beveiligingsbeleid voor apps vereisen voor toegang tot de cloud-app met voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Volg 'Stap 2: Configureer een Azure AD Conditional Access-beleid voor Exchange Online met ActiveSync (EAS)" in [scenario 1: Voor Office 365-apps zijn goedgekeurde apps met een beleid voor app-beveiliging vereist,](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)waardoor Exchange ActiveSync-clients geen basisverificatie kunnen gebruiken voor Exchange Online.

## <a name="setup-office-365-message-encryption"></a>Office 365-berichtversleuteling instellen

Met de nieuwe OME-mogelijkheden (Office 365 Message Encryption), die gebruikmaken van de beveiligingsfuncties in Azure Information Protection, kan uw organisatie beveiligde e-mail eenvoudig met iedereen op elk apparaat delen. Gebruikers kunnen beveiligde berichten verzenden en ontvangen met andere Office 365-organisaties en niet-Office 365-klanten die Outlook.com, Gmail en andere e-mailservices gebruiken.

Zie [Nieuwe Office 365-berichtenversleutelingsmogelijkheden instellen](https://support.office.com/article/set-up-new-office-365-message-encryption-capabilities-7ff0c040-b25c-4378-9904-b1b50210d00e)voor meer informatie.

## <a name="next-steps"></a>Volgende stappen

[Meer informatie over beleidsaanbevelingen voor het beveiligen van SharePoint-sites en -bestanden](sharepoint-file-access-policies.md)
