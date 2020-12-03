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
description: Meer informatie over hoe Contoso de functies voor informatiebeveiliging in Microsoft 365 for Enterprise gebruikt om de digitale activa in de cloud te beveiligen.
ms.openlocfilehash: 7cc51110a0bc4c87e57e71b2ddb42aa0dbaa288d
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558502"
---
# <a name="information-protection-for-the-contoso-corporation"></a>Informatiebescherming voor Contoso Corporation

Contoso is een belangrijke informatiebeveiliging. Een lekkage of vernietiging van de intellectuele-eigendom waarmee hun productmodellen en producten van eigen productie worden beschreven, hebben deze op een concurrentie nadeel.

Voordat Contoso de gevoelige digitale activa naar de Cloud verplaatst, controleert contoso of hun on-premises informatie classificatie en beschermings vereisten werden ondersteund door de cloudservices van Microsoft 365 for Enterprise.

## <a name="contoso-data-security-classification"></a>Contoso gegevens beveiligings classificatie

Contoso heeft een analyse van hun gegevens uitgevoerd en heeft de volgende classificatieniveaus vastgesteld.

| Niveau 1: basislijn | Niveau 2: gevoelig | Niveau 3: sterk gereglementeerd |
|:-------|:-----|:-----|
| Gegevens zijn versleuteld en alleen beschikbaar voor geverifieerde gebruikers.<BR> <BR> Verstrekt voor alle gegevens die lokaal zijn opgeslagen, en in opslagsystemen en werkbelasting in de Cloud. Gegevens worden versleuteld wanneer ze zich in de service bevinden en tijdens de overdracht tussen de service en de clientapparaten. <BR><BR>Voorbeelden van gegevens van niveau 1 zijn normale bedrijfscommunicatie (e-mail) en bestanden voor administratieve, verkoop- en ondersteuningsmedewerkers. | Niveau 1 plus krachtige verificatie en bescherming tegen gegevensverlies.<BR> <BR> Sterke verificatie omvat Azure AD multi-factor Authentication (MFA) met SMS-validatie. Preventie van gegevensverlies zorgt ervoor dat gevoelige of kritieke informatie niet wordt verzonden buiten de Microsoft-Cloud.<BR><BR>Voorbeelden van gegevens op niveau 2 zijn financiële en juridische informatie en onderzoeks- en ontwikkelingsgegevens voor nieuwe producten. | Niveau 2 plus de hoogste niveaus van versleuteling, verificatie en controle.<BR><BR>De hoogste niveaus van codering voor gegevens in de service en in de Cloud, conform de regionale voorschriften, gecombineerd met MFA met smartcards en granulaire controle en waarschuwingen.<BR> <BR>Voorbeelden van gegevens over de klant en de partners zijn persoonlijke gegevens over de klant en de partner, specificaties voor product engineering en eigen productietechnieken.  |
||||

## <a name="contoso-information-policies"></a>Contoso Information policies
De volgende tabel bevat informatie over contoso Information policies.


| Value | Toegang | Gegevensretentie | Gegevensbescherming |
|:-------|:-----|:-----|:-----|
| Lage bedrijfswaarde (niveau 1: basislijn) | Toegang tot iedereen toestaan.  | 6 maanden | Gebruik versleuteling. |
| Gemiddelde bedrijfswaarde (niveau 2: gevoelig) | Sta toegang tot Contoso medewerkers, onderaannemers en partners. <BR><BR> Gebruik MFA, TLS (Transport Layer Security) en Mobile Application Management (MAM). | 2 jaar  | Gebruik hash-waarden voor gegevensintegriteit.  |
| Hoge bedrijfswaarde (niveau 3: sterk gereglementeerd) | Sta toegang toe aan leidinggevenden en leads in engineering en productie. <BR> <BR> Rights Management System (RMS) met alleen beheerde netwerkapparaten.  | 7 jaar  | Gebruik digitale handtekeningen voor niet-afwijzing.  |
|||||

## <a name="the-contoso-path-to-information-protection-with-microsoft-365-for-enterprise"></a>Het contoso-pad naar informatiebescherming met Microsoft 365 for Enterprise

Contoso Volg deze stappen om Microsoft 365 for Enterprise te voorbereiden op de vereisten voor informatiebescherming:

1. Opgeven welke gegevens u wilt beschermen

   Contoso deed een uitgebreide beoordeling van hun bestaande digitale activa op de on-premises SharePoint-sites en bestandsshares en heeft elk activum geclassificeerd.

2. Beleidsregels voor toegang, behoud en informatiebescherming bepalen voor gegevensniveaus

   Op basis van de gegevensniveaus heeft Contoso gedetailleerde beleidsvereisten opgesteld, die werden gebruikt om bestaande digitale activa te beveiligen zodra ze naar de Cloud werden verplaatst.

3. Maak gevoeligheids labels en hun instellingen voor de verschillende gegevensniveaus

   Contoso heeft gevoeligheidslabels gemaakt voor hun gegevensniveaus, met het label Sterk gereglementeerd dat codering, machtigingen en watermerken omvat.

4.  Gegevens verplaatsen van on-premises SharePoint-sites en bestandsshares naar hun nieuwe SharePoint-sites

    De bestanden die naar de nieuwe SharePoint-sites zijn gemigreerd, hebben de standaardretentielabels overgenomen die aan de site zijn toegewezen.

5.  Traint medewerkers voor het gebruik van codegeschiktings punten voor nieuwe documenten, hoe u kunt communiceren met Contoso wanneer u nieuwe SharePoint-sites maakt en hoe u op dit moment ook digitale assets opslaat op SharePoint-sites.

    Het wijzigen van de informatie over het opslaan van een werknemer wordt vaak beschouwd als het moeilijkste deel van de overgang van de gegevensbescherming voor de Cloud. Contoso IT en management nodig om werknemers te laten weten dat ze hun digitale activa in de cloud al willen bijvoegen en bewaren, geen on-premises bestandsshares mogen gebruiken en geen Cloud-opslagservices van derden of USB-stations gebruiken.

## <a name="conditional-access-policies-for-information-protection"></a>Beleid voor voorwaardelijke toegang voor informatiebescherming

Als onderdeel van de implementatie van Exchange Online en SharePoint, heeft Contoso de volgende set regels voor voorwaardelijke toegang geconfigureerd en worden deze op de juiste groepen toegepast:

- [Beheerde en niet-beheerde toepassingstoegang op apparaatbeleid](../security/office-365-security/identity-access-policies.md)
- [Beleid voor toegang tot Exchange Online](../security/office-365-security/secure-email-recommended-policies.md)
- [SharePoint-beleidsregels voor toegang](../security/office-365-security/sharepoint-file-access-policies.md)

Dit is de nieuwe set contoso-beleidsregels voor informatiebescherming.

![Voorwaardelijke toegangsbeleidsregels voor apparaten, SharePoint en Exchange Online](../media/contoso-info-protect/contoso-info-protect-fig1.png)

>[!Note]
>Contoso heeft ook aanvullend beleid voor voorwaardelijke toegang geconfigureerd voor identiteit en inloggen. Zie [Identiteit voor Contoso Corporation](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).
>

Dit beleid zorgt ervoor dat:

- Apps die zijn toegestaan en de acties die ze kunnen uitvoeren met de gegevens van de organisatie worden gedefinieerd door het app-beveiligingsbeleid.
- Pc's en mobiele apparaten moeten compatibel zijn.
- Exchange Online maakt gebruik van Office 365-bericht versleuteling (OME) voor Exchange Online.
- In SharePoint worden door apps afgedwongen beperkingen gebruikt.
- SharePoint gebruikt toegangsbeleidsregels voor alleen-browser toegang en om toegang te blokkeren voor niet-beheerde apparaten.

## <a name="mapping-microsoft-365-for-enterprise-features-to-contoso-data-levels"></a>Microsoft 365 for Enterprise-functies toewijzen aan contoso gegevensniveaus

In de volgende tabel worden contoso gegevensniveaus toegewezen aan functies voor informatiebeveiliging in Microsoft 365 for Enterprise.

| Concentratie | Microsoft 365-cloudservices | Windows 10- en Microsoft 365-apps voor ondernemingen | Beveiliging en compliance |
|:-------|:-----|:-----|:-----|
| Niveau 1: basislijn  | Voorwaardelijke toegangsbeleidsregels voor SharePoint en Exchange Online <BR> Machtigingen op SharePoint-sites | Gevoeligheidslabels <BR> BitLocker <BR> Windows-gegevensbescherming | Beleid voor voorwaardelijke toegang van apparaten en beleid voor Mobile Application Management |
| Niveau 2: gevoelig | Niveau 1 plus: <BR> <BR> Gevoeligheidslabels <BR> Microsoft 365-bewaarlabels op SharePoint-sites <BR> Preventie van gegevensverlies voor SharePoint en Exchange Online <BR> Geïsoleerde SharePoint-sites  | Niveau 1 plus: <BR> <BR> Gevoeligheidslabels voor digitale activa  | Niveau 1 |
| Niveau 3: sterk gereglementeerd | Niveau 2 plus: <BR><BR> Uw eigen sleutel (BYOK) versleutelen en beschermen voor informatie over handelsgeheimen <BR> Azure-sleutel kluis voor line-of-business-toepassingen die werken met Microsoft 365-Services | Niveau 2 | Niveau 1 |
|||||

Hier ziet u de informatie over de informatie-bescherming van contoso.

![De resulterende configuratie van de informatiebescherming van Contoso.](../media/contoso-info-protect/contoso-info-protect-fig2.png)

## <a name="next-step"></a>Volgende stap

Meer informatie over hoe Contoso de [beveiligingsfuncties in Microsoft 365 voor ondernemingen](contoso-security-summary.md) gebruikt voor identiteits-en toegangsbeheer, bedreigingsbeveiliging, informatiebescherming en beveiligingsbeheer.

## <a name="see-also"></a>Zie ook

[Roadmap voor beveiliging](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Testlabrichtlijnen](m365-enterprise-test-lab-guides.md)
