---
title: Aanbevolen beleid voor beveiligde documenten - Microsoft 365 Enterprise | Microsoft Documenten
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
ms.openlocfilehash: 2b0d015485196bc76e7de580c888892967fe5d05
ms.sourcegitcommit: c079cc893cd1bd5d894b13814063a2f42238806e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/28/2020
ms.locfileid: "43035121"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Beleidsaanbevelingen voor het beveiligen van SharePoint-sites en -bestanden

In dit artikel wordt beschreven hoe u het aanbevolen beleid voor identiteits- en apparaattoegangs implementeren om SharePoint Online en OneDrive voor Bedrijven te beschermen. Deze richtlijnen zijn voortgebouwd op het [beleid voor algemene identiteits- en apparaattoegangsbeleid](identity-access-policies.md).

Deze aanbevelingen zijn gebaseerd op drie verschillende beveiligings- en beveiligingsniveaus voor SharePoint-bestanden die kunnen worden toegepast op basis van de granulariteit van uw behoeften: **basislijn,** **gevoelig**en **sterk gereguleerd**. U meer informatie krijgen over deze beveiligingsniveaus en de aanbevolen clientbesturingssystemen, waarnaar wordt verwezen door deze aanbevelingen in [het overzicht.](microsoft-365-policies-configurations.md)

Zorg er naast het implementeren van deze richtlijnen voor dat u SharePoint-sites configureert met de juiste hoeveelheid bescherming, inclusief het instellen van de juiste machtigingen voor gevoelige en sterk gereguleerde inhoud. Zie [Secure SharePoint Online-sites en -bestanden](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)voor meer informatie over het maken van sites voor basislijn, gevoelige en sterk gereguleerde beveiliging.

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>Algemeen beleid bijwerken om SharePoint en OneDrive voor Bedrijven op te nemen

In het volgende diagram wordt de set aanbevolen beleidsregels voor het beveiligen van bestanden in SharePoint Online en OneDrive voor Bedrijven weergegeven. Hiermee wordt aangegeven welk beleid moet worden bijgewerkt of nieuw moet worden gemaakt om bescherming voor SharePoint Online en OneDrive voor Bedrijven toe te voegen.

![Overzicht van beleidsregels voor SharePoint Online en OneDrive](../media/identity-access-ruleset-sharepoint.png)

Als u SharePoint Online hebt opgenomen toen u het algemene beleid hebt gemaakt, hoeft u alleen het nieuwe beleid te maken. Bij het configureren van regels voor voorwaardelijke toegang bevat SharePoint Online OneDrive voor Bedrijven.

Het nieuwe beleid implementeert apparaatbeveiliging voor gevoelige en sterk gereguleerde inhoud door specifieke toegangsvereisten toe te passen op SharePoint-sites die u opgeeft.

In de volgende tabel worden de beleidsregels weergegeven die u moet controleren en bijwerken of nieuwe voor SharePoint Online moet maken. De algemene beleidsregels zijn gekoppeld aan de bijbehorende configuratie-instructies in het artikel [Algemene identiteits- en apparaattoegangsbeleidsregels.](identity-access-policies.md)

|Beschermingsniveau|Beleid|Meer informatie|
|:---------------|:-------|:----------------|
|**Basislijn**|[MFA vereisen wanneer het aanmeldingsrisico *gemiddeld* of *hoog* is](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|SharePoint Online opnemen in de toewijzing van cloud-apps|
|        |[Cliënten blokkeren die geen moderne verificatie ondersteunen](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|SharePoint Online opnemen in de toewijzing van cloud-apps|
|        |[App-beleid voor gegevensbescherming toepassen](identity-access-policies.md#apply-app-data-protection-policies)|Zorg ervoor dat alle aanbevolen apps zijn opgenomen in de lijst met apps. Zorg ervoor dat u het beleid voor elk platform bijwerkt (iOS, Android, Windows)|
|        |[Eis conforme pc’s](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|SharePoint Online opnemen in lijst met cloud-apps|
|        |[Beperkingen voor app-beperkingen gebruiken in SharePoint Online](#use-app-enforced-restrictions-in-sharepoint-online)|Voeg dit nieuwe beleid toe. Hiermee moet Azure AD de instellingen gebruiken die zijn opgegeven in SharePoint Online. Deze regel is van toepassing op alle gebruikers, maar heeft alleen invloed op de toegang tot sites die zijn opgenomen in het toegangsbeleid van SharePoint Online|
|**Gevoelig**|[MFA vereisen wanneer het aanmeldingsrisico *laag,* *gemiddeld* of *hoog* is](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|SharePoint Online opnemen in de toewijzingen van cloud-apps|
|         |[Compatibele pc's *en* mobiele apparaten vereisen](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|SharePoint Online opnemen in de lijst met cloud-apps|
||[Beleid voor toegangsbeheer van SharePoint Online:](#sharepoint-online-access-control-policies)browseralleen toegang verlenen tot specifieke SharePoint-sites vanaf niet-beheerde apparaten|Dit voorkomt het bewerken en downloaden van bestanden. PowerShell gebruiken om sites op te geven|
|**Sterk gereglementeerd**|[*Altijd* mfa nodig](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|SharePoint Online opnemen in de toewijzing van cloud-apps|
||[SharePoint Online-toegangsbeheerbeleid:](#use-app-enforced-restrictions-in-sharepoint-online)Toegang tot specifieke SharePoint-sites blokkeren vanaf niet-beheerde apparaten|PowerShell gebruiken om sites op te geven|

## <a name="use-app-enforced-restrictions-in-sharepoint-online"></a>Door apps afgedwongen beperkingen gebruiken in SharePoint Online

Als u toegangsbesturingselementen implementeert in SharePoint Online, moet u dit beleid voor voorwaardelijke toegang in Azure AD maken om Azure AD te vertellen dat het beleid dat u configureert in SharePoint Online moet worden gehandhaafd. Deze regel is van toepassing op alle gebruikers, maar is alleen van invloed op de toegang tot de sites die u opgeeft met PowerShell wanneer u de toegangsbesturingselementen in SharePoint Online maakt.

Zie Toegang tot specifieke SharePoint-siteverzamelingen of OneDrive-accounts blokkeren of beperken in dit artikel voor het configureren van dit beleid: [Toegang beheren vanaf niet-beheerde apparaten](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622).

## <a name="sharepoint-online-access-control-policies"></a>Beleid voor toegangsbeheer van SharePoint Online

Microsoft raadt u aan inhoud in SharePoint-sites te beschermen met gevoelige en sterk gereguleerde inhoud met besturingselementen voor apparaattoegang. U doet dit door een beleid te maken dat het beschermingsniveau en de sites aangeeft waarop de beveiliging moet worden toegepast.

- Gevoelige sites: geef alleen browsertoegang toe. Dit voorkomt dat gebruikers bestanden bewerken en downloaden.
- Sterk gereguleerde sites: blokkeer de toegang vanaf onbeheerde apparaten.

Zie 'Toegang blokkeren of beperken tot specifieke SharePoint-siteverzamelingen of OneDrive-accounts' in dit artikel: [Toegang beheren vanaf niet-beheerde apparaten](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622).

## <a name="how-these-policies-work-together"></a>Hoe dit beleid samenwerkt

Het is belangrijk om te begrijpen dat SharePoint-sitemachtigingen doorgaans gebaseerd zijn op de zakelijke behoefte aan toegang tot sites. Deze machtigingen worden beheerd door site-eigenaren en kunnen zeer dynamisch zijn. Het gebruik van sharepoint-apparaattoegangsbeleid garandeert bescherming voor deze sites, ongeacht of gebruikers zijn toegewezen aan een Azure AD-groep die is gekoppeld aan basislijn,gevoelige of sterk gereguleerde beveiliging.

In de volgende afbeelding vindt u een voorbeeld van hoe het beleid voor toegang van SharePoint-apparaten de toegang tot sites beschermt.

![Hoe sharepoint-beleid voor toegang tot apparaten sites beschermt](../media/SharePoint-rules-scenario.png)

In de illustratie:

- James is toegewezen aan beleid voor voorwaardelijke toegang dat is gekoppeld aan basislijnbeveiliging, maar hij kan toegang krijgen tot SharePoint-sites die zijn gekoppeld aan gevoelige of sterk gereguleerde bescherming.
- Als James toegang heeft tot een gevoelige of sterk gereguleerde site waar hij lid van is, wordt zijn toegang verleend zolang zijn pc voldoet.
- Als James toegang heeft tot een gevoelige site waar hij lid van is en die zijn onbeheerde telefoon gebruikt, wat is toegestaan voor basislijngebruikers, krijgt hij alleen browsertoegang tot de gevoelige site vanwege het apparaattoegangsbeleid dat voor deze site is geconfigureerd.
- Als James toegang heeft tot een sterk gereguleerde site waar hij lid van is met behulp van zijn onbeheerde telefoon, zal hij worden geblokkeerd vanwege het toegangsbeleid geconfigureerd voor deze site. Hij heeft alleen toegang tot deze site via zijn beheerde en compatibele pc.

## <a name="next-steps"></a>Volgende stappen

[SharePoint Online-sites en -bestanden beveiligen](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)
