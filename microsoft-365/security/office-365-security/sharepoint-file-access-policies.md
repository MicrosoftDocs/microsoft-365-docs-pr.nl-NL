---
title: Aanbevolen veilig documentbeleid - Microsoft 365 voor | Microsoft Docs
description: Beschrijft het beleid voor Microsoft-aanbevelingen voor het beveiligen van SharePoint-bestandstoegang.
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
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 4e5f20feae5b5854107e9d0de54ef18d59d51df7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916618"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Beleidsaanbevelingen voor het beveiligen van SharePoint-sites en -bestanden

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- SharePoint Online 


In dit artikel wordt beschreven hoe u het aanbevolen beleid voor identiteits- en apparaattoegang implementeert om SharePoint en OneDrive voor Bedrijven te beveiligen. Deze richtlijnen zijn gebaseerd op [het algemene beleid voor identiteits- en apparaattoegang.](identity-access-policies.md)

Deze aanbevelingen zijn gebaseerd op drie verschillende beveiligings- en beveiligingsniveaus voor SharePoint-bestanden die kunnen worden toegepast op basis van de granulariteit van uw behoeften: **basislijn** **,** gevoelig en sterk **geregeld**. U vindt meer informatie over deze beveiligingslagen en de aanbevolen clientbesturingssystemen, waarnaar wordt verwezen in deze aanbevelingen in [het overzicht.](microsoft-365-policies-configurations.md)

Naast het implementeren van deze richtlijnen, moet u SharePoint-sites met de juiste mate van beveiliging configureren, inclusief het instellen van de juiste machtigingen voor gevoelige en sterk gereguleerde inhoud.

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>Algemene beleidsregels bijwerken met SharePoint en OneDrive voor Bedrijven

Als u bestanden in SharePoint en OneDrive wilt beveiligen, wordt in het volgende diagram weergegeven welk beleid moet worden bijgewerkt vanuit het algemene beleid voor identiteits- en apparaattoegang.

[![Overzicht van beleidsupdates voor het beschermen van de toegang tot Teams en de afhankelijke services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

Als u SharePoint hebt opgenomen bij het maken van het algemene beleid, hoeft u alleen het nieuwe beleid te maken. Voor beleid voor voorwaardelijke toegang bevat SharePoint OneDrive.

Het nieuwe beleid implementeert apparaatbeveiliging voor gevoelige en sterk gereguleerde inhoud door specifieke toegangsvereisten toe te passen op SharePoint-sites die u opgeeft.

In de volgende tabel ziet u het beleid dat u nodig hebt om sharePoint te controleren en bij te werken of nieuw te maken. De algemene beleidsregels koppelen aan de bijbehorende configuratie-instructies in het artikel Algemene [identiteits-](identity-access-policies.md) en apparaattoegangsbeleid.

|Beveiligingsniveau|Beleid|Meer informatie|
|---|---|---|
|**Basislijn**|[MFA vereisen wanneer het aanmeldingsrisico gemiddeld *of* *hoog* is](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Neem SharePoint op in de toewijzing van cloud-apps.|
||[Clients blokkeren die moderne verificatie niet ondersteunen](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Neem SharePoint op in de toewijzing van cloud-apps.|
||[APP-beleid voor gegevensbescherming toepassen](identity-access-policies.md#apply-app-data-protection-policies)|Zorg ervoor dat alle aanbevolen apps zijn opgenomen in de lijst met apps. Zorg ervoor dat u het beleid voor elk platform (iOS, Android, Windows) bijwerkt.|
||[Eis conforme pc’s](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Neem SharePoint op in de lijst met cloud-apps.|
||[App-afdwingbare beperkingen gebruiken in SharePoint](#use-app-enforced-restrictions-in-sharepoint)|Voeg dit nieuwe beleid toe. Dit geeft Azure Active Directory (Azure AD) de informatie over het gebruik van de instellingen die zijn opgegeven in SharePoint. Dit beleid is van toepassing op alle gebruikers, maar is alleen van invloed op de toegang tot sites die zijn opgenomen in SharePoint-toegangsbeleid.|
|**Gevoelig**|[MFA vereisen wanneer het aanmeldingsrisico *laag,* *gemiddeld* of *hoog is*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Neem SharePoint op in de toewijzingen van cloud-apps.|
||[Compatibele pc's *en mobiele* apparaten vereisen](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Neem SharePoint op in de lijst met cloud-apps.|
||[SharePoint-toegangscontrolebeleid:](#sharepoint-access-control-policies)Toestaan dat alleen-browsertoegang tot specifieke SharePoint-sites wordt toegestaan vanaf niet-beheerbare apparaten.|Dit voorkomt dat bestanden worden bewerkt en gedownload. Gebruik PowerShell om sites op te geven.|
|**Sterk gereglementeerd**|[*Altijd* MFA vereisen](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Neem SharePoint op in de toewijzing van cloud-apps.|
||[SharePoint-toegangscontrolebeleid:](#use-app-enforced-restrictions-in-sharepoint)Toegang tot specifieke SharePoint-sites blokkeren vanaf niet-beheerbare apparaten.|Gebruik PowerShell om sites op te geven.|
|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a>App-afdwingbare beperkingen gebruiken in SharePoint

Als u toegangsbesturingselementen implementeert in SharePoint, moet u dit beleid voor voorwaardelijke toegang maken in Azure AD om Azure AD te laten weten dat u het beleid wilt afdwingen dat u configureert in SharePoint. Dit beleid is van toepassing op alle gebruikers, maar is alleen van invloed op de toegang tot de sites die u opgeeft met PowerShell wanneer u de toegangsbesturingselementen in SharePoint maakt.

Als u dit beleid wilt configureren, ziet u 'Toegang tot specifieke SharePoint-siteverzamelingen of OneDrive-accounts blokkeren of beperken' in Toegang beheren [vanaf niet-beheerbare apparaten.](/sharepoint/control-access-from-unmanaged-devices)

## <a name="sharepoint-access-control-policies"></a>SharePoint Access Control-beleid

Microsoft raadt u aan inhoud op SharePoint-sites te beveiligen met gevoelige en sterk gereguleerde inhoud met besturingselementen voor apparaattoegang. U doet dit door een beleid te maken dat het beschermingsniveau en de sites aangeeft waar de beveiliging op moet worden toegepast.

- Gevoelige sites: Alleen-browsertoegang toestaan. Dit voorkomt dat gebruikers bestanden kunnen bewerken en downloaden.
- Sterk gereguleerde sites: Toegang blokkeren vanaf niet-bemande apparaten.

Zie 'Toegang tot specifieke SharePoint-siteverzamelingen of OneDrive-accounts blokkeren of beperken' in Control [access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).

## <a name="how-these-policies-work-together"></a>Hoe werken deze beleidsregels samen?

Het is belangrijk om te begrijpen dat SharePoint-sitemachtigingen meestal zijn gebaseerd op de zakelijke behoefte aan toegang tot sites. Deze machtigingen worden beheerd door site-eigenaren en kunnen zeer dynamisch zijn. Het gebruik van beleidsregels voor toegang tot SharePoint-apparaten zorgt ervoor dat deze sites worden beschermd, ongeacht of gebruikers zijn toegewezen aan een Azure AD-groep die is gekoppeld aan basislijnbeveiliging, gevoelige of sterk gereguleerde beveiliging.

In de volgende afbeelding vindt u een voorbeeld van de manier waarop toegangsbeleid voor SharePoint-apparaten de toegang tot sites voor een gebruiker beschermt.

[![Voorbeeld van de manier waarop sharePoint-beleid voor apparaattoegang sites beschermt](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

[Een grotere versie van deze afbeelding bekijken](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

Aan James is beleidsregels voor Voorwaardelijke toegang toegewezen, maar hij kan toegang krijgen tot SharePoint-sites met gevoelige of sterk gereguleerde beveiliging.

- Als James toegang heeft tot een gevoelige of sterk gereguleerde site waar hij lid van is, wordt zijn toegang verleend zolang zijn pc voldoet.
- Als James toegang heeft tot een gevoelige site waarvan hij lid is van het gebruik van zijn niet-gebruikte telefoon, wat is toegestaan voor basislijngebruikers, ontvangt hij alleen-browsertoegang tot de gevoelige site vanwege het beleid voor apparaattoegang dat is geconfigureerd voor deze site.
- Als James toegang heeft tot een sterk gereguleerde site waar hij lid van is, wordt hij geblokkeerd vanwege het toegangsbeleid dat is geconfigureerd voor deze site. Hij heeft alleen toegang tot deze site met zijn beheerde en compatibele pc.

## <a name="next-step"></a>Volgende stap

![Stap 4: Beleidsregels voor Cloud-apps van Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Beleid voor voorwaardelijke toegang configureren voor:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)