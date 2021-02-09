---
title: Aanbevolen veilig documentbeleid - Microsoft 365 voor ondernemingen | Microsoft Docs
description: Hier worden de beleidsregels beschreven voor aanbevelingen van Microsoft over het beveiligen van toegang tot SharePoint-bestanden.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
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
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 5c739a47ccab79561277436812c36f842b6b578c
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142811"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Beleidsaanbevelingen voor het beveiligen van SharePoint-sites en -bestanden

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender voor Office 365-abonnement 1 en abonnement 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- SharePoint Online 


In dit artikel wordt beschreven hoe u het aanbevolen identiteits- en apparaattoegangsbeleid implementeert om SharePoint en OneDrive voor Bedrijven te beschermen. Deze richtlijnen zijn gebaseerd op [het algemene beleid voor identiteits- en apparaattoegang.](identity-access-policies.md)

Deze aanbevelingen zijn gebaseerd op drie verschillende beveiligings- en beveiligingslagen voor SharePoint-bestanden die kunnen worden toegepast op basis van de granulatie van uw behoeften: **baseline,** **sensitive** en sterk **reguleerd.** In het overzicht vindt u meer informatie over deze beveiligingslagen en de aanbevolen clientbesturingssystemen waarnaar in deze aanbevelingen [wordt verwezen.](microsoft-365-policies-configurations.md)

Zorg ervoor dat u niet alleen deze richtlijnen implementeert, maar ook SharePoint-sites met de juiste bescherming configureert, waaronder het instellen van de juiste machtigingen voor gevoelige en sterk reguleerde inhoud.

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>Algemene beleidsregels bijwerken voor SharePoint en OneDrive voor Bedrijven

Als u bestanden in SharePoint en OneDrive wilt beveiligen, ziet u in het volgende diagram welk beleid moet worden bijgewerkt op basis van het algemene identiteits- en apparaattoegangsbeleid.

[![Overzicht van beleidsupdates voor het beschermen van de toegang tot Teams en de afhankelijke services ervan](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

[Een grotere versie van deze afbeelding bekijken](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

Als u SharePoint hebt opgenomen toen u het algemene beleid maakte, hoeft u alleen het nieuwe beleid te maken. Voor beleidsregels voor voorwaardelijke toegang bevat SharePoint OneDrive.

Het nieuwe beleid implementeert apparaatbeveiliging voor gevoelige en sterk reguleerde inhoud door specifieke toegangsvereisten toe te passen op SharePoint-sites die u opgeeft.

De volgende tabel bevat de beleidsregels die u moet controleren en bijwerken of nieuw moet maken voor SharePoint. De koppeling naar de bijbehorende configuratie-instructies in het artikel Common [identity and device access policies (Algemene identiteit en apparaattoegangsbeleid) is](identity-access-policies.md) gekoppeld aan de bijbehorende configuratie-instructies.

|Beveiligingsniveau|Beleidsregels|Meer informatie|
|---|---|---|
|**Basislijn**|[MFA vereisen wanneer het aanmeldingsrisico *gemiddeld* *of* hoog is](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Neem SharePoint op in de toewijzing van cloud-apps.|
||[Clients blokkeren die moderne verificatie niet ondersteunen](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Neem SharePoint op in de toewijzing van cloud-apps.|
||[Beleid voor app-gegevensbescherming toepassen](identity-access-policies.md#apply-app-data-protection-policies)|Zorg ervoor dat alle aanbevolen apps zijn opgenomen in de lijst met apps. Zorg ervoor dat u het beleid voor elk platform bijwerkt (iOS, Android, Windows).|
||[Eis conforme pc’s](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Neem SharePoint op in de lijst met cloud-apps.|
||[Door apps afgedwongen beperkingen gebruiken in SharePoint](#use-app-enforced-restrictions-in-sharepoint)|Voeg dit nieuwe beleid toe. Hiermee wordt aangegeven dat Azure Active Directory (Azure AD) de instellingen moet gebruiken die zijn opgegeven in SharePoint. Dit beleid is van toepassing op alle gebruikers, maar is alleen van invloed op de toegang tot sites die zijn opgenomen in toegangsbeleid van SharePoint.|
|**Gevoelig**|[MFA vereisen wanneer het aanmeldingsrisico *laag,* *gemiddeld* of *hoog is*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Neem SharePoint op in de toewijzingen van cloud-apps.|
||[Compatibele pc's *en mobiele* apparaten vereisen](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Neem SharePoint op in de lijst met cloud-apps.|
||[Toegangsbeleid voor SharePoint:](#sharepoint-access-control-policies)toegang tot bepaalde SharePoint-sites alleen voor browsers toestaan op onbeheerde apparaten.|Dit voorkomt het bewerken en downloaden van bestanden. Gebruik PowerShell om sites op te geven.|
|**Sterk gereglementeerd**|[*Altijd* MFA vereisen](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Neem SharePoint op in de toewijzing van cloud-apps.|
||[Toegangsbeleid voor SharePoint:](#use-app-enforced-restrictions-in-sharepoint)toegang tot bepaalde SharePoint-sites blokkeren vanaf onbeheerde apparaten.|Gebruik PowerShell om sites op te geven.|
|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a>Door apps afgedwongen beperkingen gebruiken in SharePoint

Als u toegangsbesturingselementen implementeert in SharePoint, moet u dit beleid voor voorwaardelijke toegang maken in Azure AD om azure AD te laten weten dat het beleid moet worden afgedwongen dat u in SharePoint configureert. Dit beleid is van toepassing op alle gebruikers, maar is alleen van invloed op de toegang tot de sites die u opgeeft met PowerShell wanneer u de toegangsbesturingselementen in SharePoint maakt.

Zie 'Toegang tot specifieke SharePoint-siteverzamelingen of OneDrive-accounts blokkeren of beperken' in Toegang beheren vanaf onbeheerde apparaten om dit beleid [te configureren.](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)

## <a name="sharepoint-access-control-policies"></a>Toegangsbeheerbeleid voor SharePoint

Microsoft raadt u aan inhoud op SharePoint-sites te beveiligen met gevoelige en sterk reguleerde inhoud met besturingselementen voor apparaattoegang. U doet dit door een beleid te maken dat het beveiligingsniveau en de sites specificeert om de beveiliging toe te passen.

- Gevoelige sites: toegang via alleen browsers toestaan. Hiermee voorkomt u dat gebruikers bestanden kunnen bewerken en downloaden.
- Sterk reguleerde sites: toegang blokkeren vanaf niet-beherende apparaten.

Zie 'Toegang tot specifieke SharePoint-siteverzamelingen of OneDrive-accounts blokkeren of beperken' in Toegang beheren [vanaf niet-beherende apparaten.](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)

## <a name="how-these-policies-work-together"></a>Hoe dit beleid samenwerken

Het is belangrijk om te weten dat sharePoint-sitemachtigingen meestal zijn gebaseerd op de zakelijke behoefte aan toegang tot sites. Deze machtigingen worden beheerd door site-eigenaren en kunnen zeer dynamisch zijn. Als u toegangsbeleid voor SharePoint-apparaten gebruikt, worden deze sites beschermd, ongeacht of gebruikers zijn toegewezen aan een Azure AD-groep die is gekoppeld aan basislijnbeveiliging, gevoelige of sterk reguleerde beveiliging.

In de volgende afbeelding wordt een voorbeeld getoond van hoe toegang tot SharePoint-apparaten de toegang tot sites voor een gebruiker bebeveiligen.

[![Voorbeeld van de manier waarop sharePoint-apparaattoegangsbeleid sites beschermt](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

[Een grotere versie van deze afbeelding bekijken](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

Aan Het beleid voor voorwaardelijke toegang van James is een basislijnbeleid toegewezen, maar hij kan toegang krijgen tot SharePoint-sites met gevoelige of sterk reguleerde beveiliging.

- Als James toegang heeft tot een gevoelige of sterk reguleerde site waar hij lid van is, wordt zijn toegang verleend zolang zijn pc compatibel is.
- Als James toegang heeft tot een gevoelige site waar hij lid van is en zijn onmanagede telefoon gebruikt, wat is toegestaan voor basislijngebruikers, krijgt hij alleen browsertoegang tot de gevoelige site vanwege het beleid voor apparaattoegang dat voor deze site is geconfigureerd.
- Als James een sterk reguleerde site gebruikt waar hij lid van is, wordt hij geblokkeerd vanwege het toegangsbeleid dat voor deze site is geconfigureerd. Hij heeft alleen toegang tot deze site met zijn beheerde en compatibele pc.

## <a name="next-step"></a>Volgende stap

![Stap 4: Beleid voor Microsoft 365-cloud-apps](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Beleidsregels voor voorwaardelijke toegang configureren voor:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
