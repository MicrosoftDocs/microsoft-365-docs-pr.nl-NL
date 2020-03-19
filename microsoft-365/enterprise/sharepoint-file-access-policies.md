---
title: Aanbevolen beveiligd documentbeleid - Microsoft 365 Enterprise | Microsoft Documenten
description: Beschrijft het beleid voor Microsoft-aanbevelingen over het beveiligen van SharePoint-bestandstoegang.
author: BrendaCarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.date: 06/07/2018
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: d11b2682b9699e61a4c9ecfa47eb73de87de5e4f
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42809135"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Beleidsaanbevelingen voor het beveiligen van SharePoint-sites en -bestanden

In dit artikel wordt beschreven hoe u het aanbevolen beleid voor identiteits- en apparaattoegang implementeert om SharePoint Online en OneDrive voor Bedrijven te beschermen. Deze richtlijnen bouwt voort op het [beleid voor algemene identiteits- en apparaattoegang](identity-access-policies.md).

Deze aanbevelingen zijn gebaseerd op drie verschillende beveiligingsniveaus en -beveiliging voor SharePoint-bestanden die kunnen worden toegepast op basis van de granulariteit van uw behoeften: **basislijn,** **gevoelig**en **sterk gereguleerd**. U meer informatie krijgen over deze beveiligingslagen en de aanbevolen clientbesturingssystemen, waarnaar wordt verwezen door deze aanbevelingen in [het overzicht.](microsoft-365-policies-configurations.md)

Naast de implementatie van deze richtlijnen moet u SharePoint-sites configureren met de juiste hoeveelheid bescherming, waaronder het instellen van de juiste machtigingen voor gevoelige en sterk gereguleerde inhoud. Zie [Secure SharePoint Online-sites en -bestanden](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)voor meer informatie over het maken van sites voor basislijn,gevoelige en sterk gereguleerde beveiliging.

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>Veelse beleidsregels bijwerken met SharePoint en OneDrive voor Bedrijven

In het volgende diagram wordt de set aanbevolen beleidsregels voor de beveiliging van bestanden in SharePoint Online en OneDrive voor Bedrijven weergegeven. Het geeft aan welk beleid moet worden bijgewerkt of nieuw moet worden gemaakt om bescherming toe te voegen voor SharePoint Online en OneDrive voor Bedrijven.

![Overzicht van het beleid voor SharePoint Online en OneDrive](../media/identity-access-ruleset-sharepoint.png)

Als u SharePoint Online hebt opgenomen toen u het algemene beleid hebt gemaakt, hoeft u alleen het nieuwe beleid te maken. Bij het configureren van regels voor voorwaardelijke toegang bevat SharePoint Online OneDrive voor Bedrijven.

Het nieuwe beleid implementeert apparaatbeveiliging voor gevoelige en sterk gereguleerde inhoud door specifieke toegangsvereisten toe te passen op SharePoint-sites die u opgeeft.

In de volgende tabel worden de beleidsregels weergegeven die u moet controleren en bijwerken of nieuw moet maken voor SharePoint Online. Het algemene beleid is gekoppeld aan de bijbehorende configuratie-instructies in het artikel [Beleid voor algemene identiteits- en apparaattoegang.](identity-access-policies.md)

|Beschermingsniveau|Beleid|Meer informatie|
|:---------------|:-------|:----------------|
|**Basislijn**|[MFA vereisen wanneer het aanmeldingsrisico *gemiddeld* of *hoog* is](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|SharePoint Online opnemen in de toewijzing van cloud-apps|
|        |[Clients blokkeren die geen ondersteuning bieden voor moderne verificatie](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|SharePoint Online opnemen in de toewijzing van cloud-apps|
|        |[App-beveiligingsbeleid definiëren](identity-access-policies.md#define-app-protection-policies)|Zorg ervoor dat alle aanbevolen apps zijn opgenomen in de lijst met apps. Zorg ervoor dat u het beleid voor elk platform (iOS, Android, Windows) bijwerkt|
|        |[Compatibele pc's vereisen](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|SharePoint Online opnemen in lijst met cloud-apps|
|        |[App-opgelegde beperkingen gebruiken in SharePoint Online](#use-app-enforced-restrictions-in-sharepoint-online)|Voeg dit nieuwe beleid toe. Dit geeft Azure AD aan de instellingen te gebruiken die zijn opgegeven in SharePoint Online. Deze regel is van toepassing op alle gebruikers, maar heeft alleen invloed op de toegang tot sites die zijn opgenomen in sharepoint online-toegangsbeleid|
|**Gevoelige**|[MFA vereisen wanneer het aanmeldingsrisico *laag,* *gemiddeld* of *hoog* is](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|SharePoint Online opnemen in de toewijzingen van cloud-apps|
|         |[Compatibele pc's *en* mobiele apparaten vereisen](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|SharePoint Online opnemen in de lijst met cloud-apps|
||[SharePoint Online toegangscontrolebeleid:](#sharepoint-online-access-control-policies)Toegang toestaan tot alleen browser tot specifieke SharePoint-sites vanaf niet-beheerde apparaten|Dit voorkomt het bewerken en downloaden van bestanden. PowerShell gebruiken om sites op te geven|
|**Sterk gereguleerd**|[*Altijd* mfa vereisen](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|SharePoint Online opnemen in de toewijzing van cloud-apps|
||[SharePoint Online toegangscontrolebeleid:](#use-app-enforced-restrictions-in-sharepoint-online)de toegang tot specifieke SharePoint-sites blokkeren vanaf niet-beheerde apparaten|PowerShell gebruiken om sites op te geven|

## <a name="use-app-enforced-restrictions-in-sharepoint-online"></a>App-opgelegde beperkingen gebruiken in SharePoint Online

Als u toegangsbesturingselementen implementeert in SharePoint Online, moet u dit beleid voor voorwaardelijke toegang maken in Azure AD om Azure AD te vertellen dat u het beleid dat u configureert in SharePoint Online moet afdwingen. Deze regel is van toepassing op alle gebruikers, maar heeft alleen invloed op de toegang tot de sites die u opgeeft met PowerShell wanneer u de toegangsbesturingselementen in SharePoint Online maakt.

Zie 'Toegang tot specifieke SharePoint-siteverzamelingen of OneDrive-accounts blokkeren of beperken' in dit artikel: Toegang beheren [vanaf niet-beheerde apparaten](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622).

## <a name="sharepoint-online-access-control-policies"></a>SharePoint Online-toegangsbeheerbeleid

Microsoft raadt u aan inhoud op SharePoint-sites te beschermen met gevoelige en sterk gereguleerde inhoud met besturingselementen voor apparaattoegang. U doet dit door een beleid te maken dat het beschermingsniveau en de sites aangeeft waarop de bescherming moet worden toegepast.

- Gevoelige sites: toegang alleen voor de browser toestaan. Dit voorkomt dat gebruikers bestanden bewerken en downloaden.
- Sterk gereguleerde sites: blokkeer toegang vanaf onbeheerde apparaten.

Zie 'Toegang tot specifieke SharePoint-siteverzamelingen of OneDrive-accounts blokkeren of beperken' in dit artikel: Toegang beheren [vanaf niet-beheerde apparaten](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622).

## <a name="how-these-policies-work-together"></a>Hoe dit beleid samenwerkt

Het is belangrijk om te begrijpen dat machtigingen voor SharePoint-sites doorgaans zijn gebaseerd op de behoefte van bedrijven aan toegang tot sites. Deze machtigingen worden beheerd door site-eigenaren en kunnen zeer dynamisch zijn. Het gebruik van sharepoint-toegangsbeleid voor apparaten garandeert bescherming voor deze sites, ongeacht of gebruikers zijn toegewezen aan een Azure AD-groep die is gekoppeld aan basislijn-, gevoelige of sterk gereguleerde beveiliging.

In de volgende afbeelding wordt een voorbeeld gegeven van hoe het toegangsbeleid voor SharePoint-apparaten de toegang tot sites beschermt.

![Hoe sharepoint-toegangsbeleid voor apparaten sites beschermt](../media/SharePoint-rules-scenario.png)

In de illustratie:

- James is toegewezen aan beleid voor voorwaardelijke toegang dat is gekoppeld aan basisbeveiliging, maar hij kan toegang krijgen tot SharePoint-sites die zijn gekoppeld aan gevoelige of sterk gereguleerde bescherming.
- Als James toegang heeft tot een gevoelige of sterk gereguleerde site waar hij lid van is van het gebruik van zijn pc, wordt zijn toegang verleend zolang zijn pc voldoet.
- Als James toegang heeft tot een gevoelige site waarvan hij lid is van het gebruik van zijn niet-beheerde telefoon, wat is toegestaan voor gebruikers bij aanvang van de basislijn, krijgt hij alleen browsertoegang tot de gevoelige site vanwege het apparaattoegangsbeleid dat voor deze site is geconfigureerd.
- Als James toegang heeft tot een sterk gereguleerde site waar hij lid van is van het gebruik van zijn onbeheerde telefoon, wordt hij geblokkeerd vanwege het toegangsbeleid dat is geconfigureerd voor deze site. Hij heeft alleen toegang tot deze site via zijn beheerde en compatibele pc.

## <a name="next-steps"></a>Volgende stappen

[SharePoint Online-sites en -bestanden beveiligen](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)
