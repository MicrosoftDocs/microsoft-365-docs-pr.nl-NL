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
ms.openlocfilehash: 67404df9bb2056c226eeb9370190519fc0cc8f3b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686020"
---
# <a name="information-protection-for-the-contoso-corporation"></a>Informatiebescherming voor Contoso Corporation

Contoso neemt de beveiliging en bescherming van informatie serieus. Diefstal of vernietiging van hun intellectuele eigendom omtrent productontwerpen en fabricagetechnieken kan hen bijvoorbeeld een concurrentienadeel opleveren.

Voordat ze de gevoelige en belangrijkste digitale activa naar de Cloud verplaatsen, hebben ze er zeker van dat hun on-premises informatie classificatie en beschermings vereisten werden ondersteund en geïmplementeerd in de Cloud-Services van Microsoft 365 for Enterprise.

## <a name="contosos-data-security-classification"></a>De classificatie van de gegevensbescherming van Contoso

Contoso heeft een analyse uitgevoerd op hun gegevens en heeft de volgende niveaus bepaald.

| Niveau 1: basislijn | Niveau 2: gevoelig | Niveau 3: sterk gereglementeerd |
|:-------|:-----|:-----|
| Gegevens zijn versleuteld en alleen beschikbaar voor geverifieerde gebruikers. <BR> <BR> Verstrekt voor alle gegevens die lokaal zijn opgeslagen, en in opslagsystemen en werkbelasting in de Cloud. Gegevens worden versleuteld wanneer ze zich in de service bevinden en tijdens de overdracht tussen de service en de clientapparaten. <BR><BR> Voorbeelden van gegevens van niveau 1 zijn normale bedrijfscommunicatie (e-mail) en bestanden voor administratieve, verkoop- en ondersteuningsmedewerkers. | Niveau 1 plus krachtige verificatie en bescherming tegen gegevensverlies. <BR> <BR> Geavanceerde verificatie omvat Azure Meervoudige Verificatie (MFA) met SMS-validatie. Met preventie van gegevensverlies wordt voorkomen dat gevoelige of kritieke informatie wordt verzonden buiten de Microsoft-Cloud. <BR><BR> Voorbeelden van gegevens op niveau 2 zijn financiële en juridische informatie en onderzoeks- en ontwikkelingsgegevens voor nieuwe producten. | Niveau 2 plus de hoogste niveaus van versleuteling, verificatie en controle. <BR> <BR>  De hoogste niveaus van codering voor gegevens in de service en in de Cloud, conform de regionale voorschriften, gecombineerd met MFA met smartcards en granulaire controle en waarschuwingen. <BR> <BR> Voorbeelden van gegevens van niveau 3 zijn persoonlijk identificeerbare klant- en partnergegevens, product technische specificaties en speciale productietechnieken.  |
||||

## <a name="contosos-information-policies"></a>Het gegevensbeleid van Contoso
In de volgende tabel ziet u het gegevensbeleid van Contoso.


| Value | Toegang | Gegevensretentie | Informatiebescherming |
|:-------|:-----|:-----|:-----|
| Lage bedrijfswaarde (niveau 1: basislijn) | Geef iedereen toegang  | 6 maanden | Gebruik versleuteling. |
| Gemiddelde bedrijfswaarde (niveau 2: gevoelig) | Sta toegang toe aan Contoso-medewerkers, onderaannemers en partners <BR> <BR> Gebruik MFA, TLS (Transport Layer Security) en Mobile Application Management (MAM). | 2 jaar  | Gebruik hash-waarden voor gegevensintegriteit.  |
| Hoge bedrijfswaarde (niveau 3: sterk gereglementeerd) | Sta toegang toe aan leidinggevenden en leads in engineering en productie. <BR> <BR> Rights Management System (RMS) met alleen beheerde netwerkapparaten.  | 7 jaar  | Gebruik digitale handtekeningen voor niet-afwijzing.  |
|||||

## <a name="contosos-path-to-information-protection-with-microsoft-365-for-enterprise"></a>Het pad van Contoso naar informatiebescherming met Microsoft 365 for Enterprise

Contoso gebruikt de volgende stappen om Microsoft 365 for Enterprise voor hun informatiebescherming voor te bereiden:

1. Geïdentificeerd welke gegevens te beveiligen

   Contoso heeft een uitgebreide beoordeling uitgevoerd van hun bestaande digitale activa die zich op on-premises SharePoint-sites en bestandsshares bevinden, en heeft ze allemaal geclassificeerd.

2. Beleid voor toegang, bewaren en informatiebescherming voor gegevensniveaus bepaald

   Op basis van de gegevensniveaus heeft Contoso gedetailleerde beleidsvereisten opgesteld, die werden gebruikt om bestaande digitale activa te beveiligen zodra ze naar de Cloud werden verplaatst.

3. Gevoeligheidslabels en hun instellingen voor de verschillende informatieniveaus gemaakt

   Contoso heeft gevoeligheidslabels gemaakt voor hun gegevensniveaus, met het label Sterk gereglementeerd dat codering, machtigingen en watermerken omvat.

4.  Gegevens verplaatst van on-premises SharePoint-sites en bestandsshares naar de nieuwe SharePoint-sites

    De bestanden die naar de nieuwe SharePoint-sites zijn gemigreerd, hebben de standaardretentielabels overgenomen die aan de site zijn toegewezen.

5.  Getrainde medewerkers over het gebruik van gevoeligheidslabels voor nieuwe documenten, hoe om te gaan met de IT-afdeling van Contoso bij het maken van nieuwe SharePoint-sites en om altijd digitale middelen op SharePoint-sites op te slaan

    Het moeilijkste deel van de overgang van informatiebescherming voor de cloud, was dat de IT-afdeling van Contoso en management de slechte informatieopslaggewoonten van hun werknemers moesten veranderen. Men wilde bereiken dat werknemers hun digitale activa altijd labelen en opslaan in de cloud, zich onthouden van het gebruik van on-premises bestandsshares, en nooit cloudopslagservices van derden of USB-drives gebruiken.

## <a name="conditional-access-policies-for-information-protection"></a>Beleid voor voorwaardelijke toegang voor informatiebescherming

In combinatie met hun identiteit en infrastructuur voor het beheer van mobiele apparaten en als onderdeel van hun uitrol van Exchange Online en SharePoint, heeft Contoso de volgende set voorwaardelijke toegangsbeleid geconfigureerd en toegepast op de van toepassing zijnde groepen:

- [Beheerde en niet-beheerde toepassingstoegang op apparaatbeleid](identity-access-policies.md)
- [Beleid voor toegang tot Exchange Online](secure-email-recommended-policies.md)
- [SharePoint-beleidsregels voor toegang](sharepoint-file-access-policies.md)

Hier ziet u de resulterende configuratie van de gegevensbescherming van Contoso.

![Voorwaardelijke toegangsbeleidsregels voor apparaten, SharePoint en Exchange Online](../media/contoso-info-protect/contoso-info-protect-fig1.png)

>[!Note]
>Contoso heeft ook aanvullend beleid voor voorwaardelijke toegang geconfigureerd voor identiteit en inloggen. Zie [Identiteit voor Contoso Corporation](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).
>

Dit beleid zorgt ervoor dat:

- Apps zijn toegestaan en de acties die ze kunnen ondernemen met uw organisatiegegevens worden bepaald door het app-beschermingsbeleid.
- Pc's en mobiele apparaten moeten compatibel zijn.
- Exchange Online maakt gebruik van Office 365-bericht versleuteling (OME) voor Exchange Online.
- SharePoint gebruikt door de app afgedwongen beperkingen.
- SharePoint gebruikt toegangsbeleidsregels voor alleen-browser toegang en om toegang te blokkeren voor niet-beheerde apparaten.

## <a name="mapping-microsoft-365-for-enterprise-features-to-contosos-data-levels"></a>Microsoft 365 for Enterprise-functies toewijzen aan de gegevensniveaus van contoso

In de volgende tabel wordt het gegevensniveau van Contoso toegewezen aan functies voor informatiebeveiliging in Microsoft 365 for Enterprise.

| Concentratie | Microsoft 365-cloudservices | Windows 10- en Microsoft 365-apps voor ondernemingen | Beveiliging en compliance |
|:-------|:-----|:-----|:-----|
| Niveau 1: basislijn  | Voorwaardelijke toegangsbeleidsregels voor SharePoint en Exchange Online <BR> Machtigingen op SharePoint-sites | Gevoeligheidslabels <BR> BitLocker <BR> Windows-gegevensbescherming | Beleid voor voorwaardelijke toegang van apparaten en beleid voor Mobile Application Management |
| Niveau 2: gevoelig | Niveau 1 plus: <BR> <BR> Gevoeligheidslabels <BR> Microsoft 365-bewaarlabels op SharePoint-sites <BR> Preventie van gegevensverlies voor SharePoint en Exchange Online <BR> Geïsoleerde SharePoint-sites  | Niveau 1 plus: <BR> <BR> Gevoeligheidslabels voor digitale activa  | Niveau 1 |
| Niveau 3: sterk gereglementeerd | Niveau 2 plus: <BR><BR> Bring Your Own Key (BYOK) encryptie en bescherming voor bedrijfsgeheimen <BR> Azure Key Vault voor bedrijfstoepassingen die communiceren met Microsoft 365-services | Niveau 2 | Niveau 1 |
|||||

Hier ziet u de resulterende configuratie van de informatiebescherming van Contoso.

![De resulterende configuratie van de informatiebescherming van Contoso.](../media/contoso-info-protect/contoso-info-protect-fig2.png)

## <a name="next-step"></a>Volgende stap

[Zie](contoso-security-summary.md) hoe Contoso de beveiligingsfuncties in microsoft 365 voor ondernemingen heeft gebruikt voor identiteits-en toegangsbeheer, bedreigingsbeveiliging, informatiebescherming en beveiligingsbeheer.

## <a name="see-also"></a>Zie ook

[Roadmap voor beveiliging](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Testlabrichtlijnen](m365-enterprise-test-lab-guides.md)


