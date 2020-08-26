---
title: Aanbevolen beveiligings document beleid-Microsoft 365 for Enterprise | Microsoft docs
description: Een beschrijving van de beleidsregels voor Microsoft-aanbevelingen over het beveiligen van toegang tot SharePoint-bestanden.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: 06/07/2018
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 1cd56b7b02dedfbdb544b49410d231f08a0d4c67
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898150"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Beleids aanbevelingen voor het beveiligen van SharePoint-sites en-bestanden

In dit artikel wordt uitgelegd hoe u de aanbevolen identiteit en het beleid voor het openen van een apparaat kunt implementeren om SharePoint Online en OneDrive voor bedrijven te beveiligen. Deze richtlijnen zijn van toepassing op de [veelgebruikte beleidsregels voor identiteit en toegang tot apparaten](identity-access-policies.md).

Deze aanbevelingen maken deel uit van drie verschillende niveaus van beveiliging en bescherming voor SharePoint-bestanden die kunnen worden toegepast op basis van de granulatie van uw behoeften: **basislijn**, **gevoelige**en **nadrukkelijk gereglementeerde**. U vindt meer informatie over deze beveiligingslagen en de aanbevolen besturingssystemen van de client, waarnaar wordt verwezen in [het overzicht](microsoft-365-policies-configurations.md).

Zorg er ook voor dat u de SharePoint-sites configureert met de juiste hoeveelheid bescherming, waaronder het instellen van de juiste machtigingen voor gevoelige en sterk gereguleerde inhoud.

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>Veelgebruikte beleidsregels bijwerken voor het opnemen van SharePoint en OneDrive voor bedrijven

In het volgende diagram ziet u de set aanbevolen beleidsregels voor het beschermen van bestanden in SharePoint Online en OneDrive voor bedrijven. Hiermee wordt aangegeven welke beleidsregels moeten worden bijgewerkt of nieuw moeten worden gemaakt om beveiliging voor SharePoint Online en OneDrive voor bedrijven toe te voegen.

[![Overzicht van beleid voor SharePoint Online en OneDrive ](../media/identity-access-ruleset-sharepoint.png)](../media/identity-access-ruleset-sharepoint.png#lightbox)

Als u bij het maken van een gemeenschappelijk beleid SharePoint Online hebt opgenomen, hoeft u alleen maar het nieuwe beleid te maken. Wanneer u regels voor voorwaardelijke toegang configureert, bevat SharePoint Online OneDrive voor bedrijven.

Het nieuwe beleid implementeert beveiliging van apparaten voor gevoelige en sterk gereguleerde inhoud door specifieke toegangsvereisten toe te passen op de SharePoint-sites die u opgeeft.

De volgende tabel bevat een overzicht van de beleidsregels die u moet controleren, bijwerken of maken van nieuwe functies in SharePoint Online. De koppeling common policies naar de gekoppelde configuratie-instructies in het artikel [common Identity en Apparaattoegang-beleid](identity-access-policies.md) .

|Beveiligingsniveau|Lijnen|Meer informatie|
|:---------------|:-------|:----------------|
|**Basislijn**|[MFA vereisen wanneer het aanmeld risico *normaal* of *hoog* is](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|SharePoint Online opnemen in de toewijzing van Cloud-apps|
|        |[Clients blokkeren die moderne verificatie niet ondersteunen](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|SharePoint Online opnemen in de toewijzing van Cloud-apps|
|        |[Beleid voor APP-gegevensbeveiliging toepassen](identity-access-policies.md#apply-app-data-protection-policies)|Zorg ervoor dat alle aanbevolen apps zijn opgenomen in de lijst met apps. Zorg ervoor dat u het beleid voor elk platform (iOS, Android, Windows) bijwerkt.|
|        |[Eis conforme pc’s](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|SharePoint Online opnemen in lijst met Cloud-apps|
|        |[Door apps afgedwongen beperkingen gebruiken in SharePoint Online](#use-app-enforced-restrictions-in-sharepoint-online)|Voeg dit nieuwe beleid toe. Hiermee wordt in azure AD aangegeven dat de instellingen van SharePoint Online worden gebruikt. Deze regel is van toepassing op alle gebruikers, maar heeft alleen invloed op de toegang tot sites die deel uitmaken van het SharePoint Online-toegangsbeleid.|
|**Gevoelig**|[MFA vereisen wanneer het aanmeld risico *slecht*, *gemiddeld* of *hoog* is](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|SharePoint Online opnemen in de toewijzingen van Cloud-apps|
|         |[Compatibele Pc's *en* mobiele apparaten vereisen](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|SharePoint Online opnemen in de lijst met Cloud-apps|
||[Toegangsbeheerbeleid van SharePoint Online](#sharepoint-online-access-control-policies): alleen browser toegang verlenen tot bepaalde SharePoint-sites van niet-beheerde apparaten|Hiermee voorkomt u dat bestanden kunnen worden bewerkt en gedownload. PowerShell gebruiken om sites op te geven|
|**Sterk gereglementeerd**|[*Altijd* MFA vereisen](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|SharePoint Online opnemen in de toewijzing van Cloud-apps|
||[Toegangsbeheerbeleid van SharePoint Online](#use-app-enforced-restrictions-in-sharepoint-online): toegang tot bepaalde SharePoint-sites blokkeren van niet-beheerde apparaten|PowerShell gebruiken om sites op te geven|

## <a name="use-app-enforced-restrictions-in-sharepoint-online"></a>Door apps afgedwongen beperkingen gebruiken in SharePoint Online

Als u Access-besturingselementen implementeert in SharePoint Online, moet u dit beleid voor voorwaardelijke toegang in azure AD maken om aan te geven dat de beleidsregels die u configureert in SharePoint Online worden afgedwongen in azure AD. Deze regel is van toepassing op alle gebruikers, maar alleen van invloed is op de sites die u met PowerShell opgeeft wanneer u de besturingselementen voor Access maakt in SharePoint Online.

Zie ' toegang tot bepaalde SharePoint-siteverzamelingen of OneDrive-accounts blokkeren of beperken ' in dit artikel voor informatie [over het beheren van de toegang vanaf niet-beheerde apparaten](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).

## <a name="sharepoint-online-access-control-policies"></a>Toegangsbeheerbeleid van SharePoint Online

Microsoft raadt u aan inhoud op SharePoint-sites met gevoelige en sterk begereguleerde inhoud met besturingselementen voor apparaten te beschermen. U doet dit door een beleid te maken waarmee het beschermingsniveau en de sites worden ingesteld waarop de beveiliging moet worden toegepast.

- Gevoelige websites: toegang tot browsers toestaan. Hiermee voorkomt u dat gebruikers bestanden bewerken en downloaden.
- Uiterst gereguleerde sites: toegang blokkeren vanaf niet-beheerde apparaten.

Zie de sectie toegang tot bepaalde SharePoint-siteverzamelingen of OneDrive-accounts blokkeren of beperken in dit artikel: [toegang beheren vanaf niet-beheerde apparaten](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).

## <a name="how-these-policies-work-together"></a>Hoe deze beleidsregels samenwerken

Het is van belang dat u begrijpt dat machtigingen van SharePoint-sites meestal gebaseerd zijn op de business behoeften voor toegang tot sites. Deze machtigingen worden beheerd door site-eigenaren en kunnen zeer dynamisch zijn. Met het beleid voor het openen van een toegangsbeleid voor SharePoint beschermt u de beveiliging van deze sites, ongeacht of gebruikers worden toegewezen aan een Azure AD-groep die is gekoppeld aan de basislijn, gevoelige beveiliging of een hoge gereguleerde bescherming.

In de volgende afbeelding ziet u een voorbeeld van de manier waarop u beleidsregels voor toegang tot sites in SharePoint-apparaten kunt beschermen.

[![Hoe SharePoint-apparaten voor toegangsbeleid voor apparaten beschermen ](../media/SharePoint-rules-scenario.png)](../media/SharePoint-rules-scenario.png#lightbox)

In de afbeelding:

- James wordt toegewezen aan het beleid voor voorwaardelijke toegang dat is gekoppeld aan de basislijn-bescherming, maar hij kan toegang krijgen tot SharePoint-sites die zijn gekoppeld aan gevoelige of zeer gereguleerde bescherming.
- Als James een gevoelige of zeer gereglementeerde site opent die lid is van zijn PC, is de toegang van de persoon, mits deze compatibel is met de PC.
- Als James een gevoelige site opent die lid is van zijn niet-beheerde telefoon, die is toegestaan voor gebruikers met een basislijn, ontvangt hij of zij alleen browser toegang tot de gevoelige site vanwege het toegangsbeleid voor apparaten die voor deze site is geconfigureerd.
- Als James een zeer gereglementeerde site opent die hij lid is van zijn niet-beheerde telefoon, wordt hij geblokkeerd vanwege het voor deze site geconfigureerde toegangsbeleid. Hij kan alleen toegang krijgen tot deze site via zijn beheerde en compatibele PC.

