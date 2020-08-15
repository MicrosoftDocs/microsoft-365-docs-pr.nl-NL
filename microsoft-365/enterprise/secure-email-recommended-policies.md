---
title: 'Aanbevolen beleidsregels voor beveiliging van e-mail: Microsoft 365 for Enterprise | Microsoft docs'
description: Een beschrijving van de beleidsregels voor Microsoft-aanbevelingen over het toepassen van e-mail beleidsregels en configuraties.
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
ms.openlocfilehash: 39e7be86c06a471a4eefc0cacd3657c363eddae6
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685604"
---
# <a name="policy-recommendations-for-securing-email"></a>Beleids aanbevelingen voor beveiliging van e-mail

In dit artikel wordt uitgelegd hoe u de aanbevolen identiteit en het beleid voor het openen van e-mailberichten en e-mail cliënten voor e-mail en e-mail clients beschermt die ondersteuning bieden voor moderne verificatie en voorwaardelijke toegang. Deze richtlijnen zijn van toepassing op de [gangbare beleidsregels voor identiteits-en Apparaattoegang](identity-access-policies.md) en bevat ook een paar extra aanbevelingen.

Deze aanbevelingen maken deel uit van drie verschillende niveaus voor beveiliging en bescherming die op basis van de granulatie van uw behoeften kunnen worden toegepast: **basislijn**, **gevoelige**en **nadrukkelijk gereglementeerde**. U vindt meer informatie over deze beveiligingslagen en de aanbevolen besturingssystemen van de client, waarnaar wordt verwezen door deze aanbevelingen in het [Aanbevolen beveiligingsbeleid en de introductie van configuraties](microsoft-365-policies-configurations.md).

Voor deze aanbevelingen moeten uw gebruikers moderne e-mailclients gebruiken, waaronder Outlook voor iOS en Android op een mobiel apparaat. Outlook voor iOS en Android bieden ondersteuning voor de beste functies van Office 365. Deze mobiele Outlook-apps zijn ook samengesteld met beveiligingsfuncties die ondersteuning bieden voor mobiele gebruikers en werken samen met andere mogelijkheden van Microsoft Cloud-beveiliging. Voor meer informatie raadpleegt u [Veelgestelde vragen over Outlook voor IOS en Android](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).

## <a name="updating-common-policies-to-include-email"></a>Veelgebruikte beleidsregels bijwerken voor het opnemen van e-mail

In het volgende diagram ziet u de gangbare beleidsregels voor identiteits-en Apparaattoegang en wordt aangegeven welke beleidsregels moeten worden bijgewerkt om e-mail te beveiligen. Let op het toevoegen van een nieuwe regel voor Exchange Online om ActiveSync-clients te blokkeren. Hiermee wordt het gebruik van Outlook Mobile geforceerd.

![Overzicht van beleidsupdates voor de beveiliging van e-mail](../media/identity-access-ruleset-mail.png)

[Een grotere versie van deze afbeelding weergeven](https://raw.githubusercontent.com/MicrosoftDocs/microsoft-365-docs/public/microsoft-365/media/identity-access-ruleset-mail.png)

Als u Exchange Online en Outlook hebt opgenomen in het bereik van de beleidsregels wanneer u deze instelt, hoeft u alleen het nieuwe beleid te maken om ActiveSync-clients te blokkeren. Bekijk de beleidsregels die in de volgende tabel worden vermeld en maak de aanbevolen toevoegingen, of Controleer of deze al zijn opgenomen. Elke regel koppelt aan de gekoppelde configuratie-instructies in het artikel [veelgebruikte beleidsregels voor identiteit en Apparaattoegang](identity-access-policies.md) .

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

Dit beleid voorkomt dat ActiveSync-clients andere regels voor voorwaardelijke toegang overslaan. De regelconfiguratie geldt alleen voor ActiveSync-clients. Met dit beleid moet u ActiveSync-clients blokkeren om het **[beveiligingsbeleid voor apps vereisen](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)**. Meer informatie over het maken van dit beleid vindt u in het [beleid voor app-beveiliging vereisen voor toegang tot de Cloud-app met voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Ga als volgt te werk: ' stap 2: Configureer een Azure AD-beleid voor voorwaardelijke toegang voor Exchange Online met ActiveSync (EAS) ' in [scenario 1: voor Office 365-apps zijn goedgekeurde apps vereist met een app-beveiligingsbeleid](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), waardoor Exchange ActiveSync-clients niet via basisverificatie verbinding maken met Exchange Online.

## <a name="set-up-message-encryption"></a>Bericht versleuteling instellen

Met de nieuwe functies voor het versleutelen van Office 365-berichten versleutelen (OME) die gebruikmaken van de beveiligingsfuncties in azure Information Protection kunt u in uw organisatie eenvoudig beveiligde e-mail delen met iedereen op elk apparaat. Gebruikers kunnen beveiligde berichten verzenden en ontvangen met andere Microsoft 365-organisaties, evenals niet-klanten die gebruikmaken van Outlook.com, Gmail en andere e-mailservices.

Voor meer informatie raadpleegt [u nieuwe functies in Office 365-berichten versleutelen instellen](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities).

## <a name="next-steps"></a>Volgende stappen

[Meer informatie over beleids aanbevelingen voor het beveiligen van SharePoint-sites en-bestanden](sharepoint-file-access-policies.md)
