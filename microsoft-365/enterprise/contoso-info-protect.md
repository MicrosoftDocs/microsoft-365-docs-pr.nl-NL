---
title: Informatiebescherming voor Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Meer informatie over hoe Contoso de informatiebeveiligingsfuncties in Microsoft 365 voor bedrijven gebruikt om hun digitale assets in de cloud te beveiligen.
ms.openlocfilehash: 3bd778708e30253e53cc465e89f7b783141771de
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051494"
---
# <a name="information-protection-for-the-contoso-corporation"></a>Informatiebescherming voor Contoso Corporation

Contoso is serieus met de informatiebeveiliging. Door lekkage of vernietiging van intellectuele eigendom die hun productontwerpen en merkeigen fabricagetechnieken beschrijft, worden deze in een concurrentienadeel beschreven.

Voordat Contoso zijn gevoelige digitale assets naar de cloud verplaatst, zorgde Contoso ervoor dat hun on-premises informatieclassificatie- en beveiligingsvereisten werden ondersteund door de cloudservices van Microsoft 365 voor bedrijven.

## <a name="contoso-data-security-classification"></a>Contoso-classificatie voor gegevensbeveiliging

Contoso heeft een analyse van de gegevens uitgevoerd en de volgende classificatieniveaus bepaald.

| Niveau 1: basislijn | Niveau 2: gevoelig | Niveau 3: sterk gereglementeerd |
|:-------|:-----|:-----|
| Gegevens zijn versleuteld en alleen beschikbaar voor geverifieerde gebruikers.<BR> <BR> Beschikbaar voor alle gegevens die on-premises en in cloudopslag en -werkbelasting zijn opgeslagen. Gegevens worden versleuteld wanneer ze zich in de service bevinden en tijdens de overdracht tussen de service en de clientapparaten. <BR><BR>Voorbeelden van gegevens van niveau 1 zijn normale bedrijfscommunicatie (e-mail) en bestanden voor administratieve, verkoop- en ondersteuningsmedewerkers. | Niveau 1 plus krachtige verificatie en bescherming tegen gegevensverlies.<BR> <BR> Sterke verificatie omvat Azure AD Multi-Factor Authentication (MFA) met Sms validatie. Preventie van gegevensverlies zorgt ervoor dat gevoelige of kritieke informatie niet buiten de Microsoft-cloud wordt gebruikt.<BR><BR>Voorbeelden van gegevens op niveau 2 zijn financiële en juridische informatie en onderzoeks- en ontwikkelingsgegevens voor nieuwe producten. | Niveau 2 plus de hoogste niveaus van versleuteling, verificatie en controle.<BR><BR>De hoogste niveaus van codering voor gegevens in de service en in de Cloud, conform de regionale voorschriften, gecombineerd met MFA met smartcards en granulaire controle en waarschuwingen.<BR> <BR>Voorbeelden van gegevens op niveau 3 zijn persoonlijke gegevens van klanten en partners, producttechniekspecificaties en eigen productietechnieken.  |
||||

## <a name="contoso-information-policies"></a>Contoso-informatiebeleid
In de volgende tabel vindt u het informatiebeleid van Contoso.


| Waarde | Toegang | Gegevensretentie | Gegevensbescherming |
|:-------|:-----|:-----|:-----|
| Lage bedrijfswaarde (niveau 1: basislijn) | Toegang tot iedereen toestaan.  | 6 maanden | Gebruik versleuteling. |
| Gemiddelde bedrijfswaarde (niveau 2: gevoelig) | Toegang verlenen tot Medewerkers, onderaannemers en partners van Contoso. <BR><BR> Gebruik MFA, TLS (Transport Layer Security) en Mobile Application Management (MAM). | 2 jaar  | Gebruik hash-waarden voor gegevensintegriteit.  |
| Hoge bedrijfswaarde (niveau 3: sterk gereglementeerd) | Sta toegang toe aan leidinggevenden en leads in engineering en productie. <BR> <BR> Rights Management System (RMS) met alleen beheerde netwerkapparaten.  | 7 jaar  | Gebruik digitale handtekeningen voor niet-afwijzing.  |
|||||

## <a name="the-contoso-path-to-information-protection-with-microsoft-365-for-enterprise"></a>Het Contoso-pad naar informatiebeveiliging met Microsoft 365 voor ondernemingen

Contoso heeft deze stappen gevolgd om de Microsoft 365 voor ondernemingen voor te bereiden op hun vereisten voor informatiebeveiliging:

1. Bepalen welke informatie u moet beveiligen

   Contoso heeft de bestaande digitale activa op on-premises SharePoint sites en bestandsaandelen uitgebreid beoordeeld en elk activum geclassificeerd.

2. Beleid voor toegangs-, bewaar- en informatiebeveiliging voor gegevensniveaus bepalen

   Op basis van de gegevensniveaus heeft Contoso gedetailleerde beleidsvereisten opgesteld, die werden gebruikt om bestaande digitale activa te beveiligen zodra ze naar de Cloud werden verplaatst.

3. Gevoeligheidslabels en hun instellingen maken voor de verschillende informatieniveaus

   Contoso heeft gevoeligheidslabels gemaakt voor hun gegevensniveaus, met het label Sterk gereglementeerd dat codering, machtigingen en watermerken omvat.

4.  Gegevens verplaatsen van on-premises SharePoint sites en bestandsaandelen naar hun nieuwe SharePoint sites

    De bestanden die naar de nieuwe SharePoint-sites zijn gemigreerd, hebben de standaardretentielabels overgenomen die aan de site zijn toegewezen.

5.  Train werknemers hoe u gevoeligheidslabels gebruikt voor nieuwe documenten, hoe u met Contoso IT kunt werken bij het maken van nieuwe SharePoint-sites en om digitale assets altijd op te slaan op SharePoint sites

    Het wijzigen van slechte werkgegevensopslaggewoonten wordt vaak beschouwd als het lastigste deel van de overgang naar informatiebeveiliging voor de cloud. Contoso IT en beheer die nodig zijn om werknemers altijd te laten labelen en hun digitale assets in de cloud op te slaan, geen on-premises bestandsaandelen te gebruiken en geen cloudopslagservices of USB-stations van derden te gebruiken.

## <a name="conditional-access-policies-for-information-protection"></a>Beleid voor voorwaardelijke toegang voor informatiebescherming

Als onderdeel van de implementatie van Exchange Online en SharePoint heeft Contoso de volgende set beleidsregels voor voorwaardelijke toegang geconfigureerd en toegepast op de juiste groepen:

- [Beheerde en niet-beheerde toepassingstoegang op apparaatbeleid](../security/defender-365-security/identity-access-policies.md)
- [Beleid voor toegang tot Exchange Online](../security/defender-365-security/secure-email-recommended-policies.md)
- [SharePoint-beleidsregels voor toegang](../security/defender-365-security/sharepoint-file-access-policies.md)

Hier vindt u de resulterende set Contoso-beleidsregels voor informatiebeveiliging.

![Voorwaardelijke toegangsbeleidsregels voor apparaten, SharePoint en Exchange Online](../media/contoso-info-protect/contoso-info-protect-fig1.png)

>[!Note]
>Contoso heeft ook aanvullend beleid voor voorwaardelijke toegang geconfigureerd voor identiteit en inloggen. Zie [Identiteit voor Contoso Corporation](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).
>

Dit beleid zorgt ervoor dat:

- Apps die zijn toegestaan en de acties die ze kunnen uitvoeren met de gegevens van de organisatie, worden gedefinieerd door beleidsregels voor app-beveiliging.
- Pc's en mobiele apparaten moeten compatibel zijn.
- Exchange Online gebruikt Office 365 berichtversleuteling (OME) voor Exchange Online.
- SharePoint wordt gebruikgemaakt van app-afdwingbare beperkingen.
- SharePoint gebruikt toegangsbeleidsregels voor alleen-browser toegang en om toegang te blokkeren voor niet-beheerde apparaten.

## <a name="mapping-microsoft-365-for-enterprise-features-to-contoso-data-levels"></a>Toewijzing Microsoft 365 voor bedrijfsfuncties aan Contoso-gegevensniveaus

In de volgende tabel worden contoso-gegevensniveaus aan informatiebeveiligingsfuncties in Microsoft 365 voor ondernemingen.

| Niveau | Microsoft 365 cloudservices | Windows 10- en Microsoft 365-apps voor ondernemingen | Beveiliging en compliance |
|:-------|:-----|:-----|:-----|
| Niveau 1: basislijn  | Voorwaardelijke toegangsbeleidsregels voor SharePoint en Exchange Online <BR> Machtigingen op SharePoint-sites | Gevoeligheidslabels <BR> BitLocker <BR> Windows-gegevensbescherming | Beleid voor voorwaardelijke toegang van apparaten en beleid voor Mobile Application Management |
| Niveau 2: gevoelig | Niveau 1 plus: <BR> <BR> Gevoeligheidslabels <BR> Microsoft 365-bewaarlabels op SharePoint-sites <BR> Preventie van gegevensverlies voor SharePoint en Exchange Online <BR> Geïsoleerde SharePoint-sites  | Niveau 1 plus: <BR> <BR> Gevoeligheidslabels voor digitale activa  | Niveau 1 |
| Niveau 3: sterk gereglementeerd | Niveau 2 plus: <BR><BR> Uw eigen sleutelversleuteling (BYOK) en beveiliging voor handelsgeheime informatie meenemen <BR> Azure Key Vault voor line-of-business-toepassingen die werken met Microsoft 365 services | Niveau 2 | Niveau 1 |
|||||

Hier vindt u de resulterende Contoso-configuratie voor informatiebeveiliging.

![De resulterende configuratie van de informatiebescherming van Contoso.](../media/contoso-info-protect/contoso-info-protect-fig2.png)

## <a name="next-step"></a>Volgende stap

Lees hoe Contoso [](contoso-security-summary.md) de beveiligingsfuncties in Microsoft 365 voor ondernemingen gebruikt voor identiteits- en toegangsbeheer, bedreigingsbeveiliging, informatiebeveiliging en beveiligingsbeheer.

## <a name="see-also"></a>Zie ook

[Roadmap voor beveiliging](../security/defender-365-security/security-roadmap.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Testlabrichtlijnen](m365-enterprise-test-lab-guides.md)