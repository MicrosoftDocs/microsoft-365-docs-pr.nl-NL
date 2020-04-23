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
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Meer informatie over hoe Contoso de functies voor informatiebescherming in Microsoft 365 Enterprise gebruikt om hun digitale activa in de cloud te beveiligen.
ms.openlocfilehash: 41873f14ac52000635508aca4728572556692cc4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43625300"
---
# <a name="information-protection-for-the-contoso-corporation"></a>Informatiebescherming voor Contoso Corporation

Contoso neemt de beveiliging en bescherming van informatie serieus. Diefstal of vernietiging van hun intellectuele eigendom omtrent productontwerpen en fabricagetechnieken kan hen bijvoorbeeld een concurrentienadeel opleveren.

Voordat ze hun gevoelige en meest waardevolle digitale middelen naar de cloud verplaatsten, zorgden ze ervoor dat hun on-premises informatieclassificatie en beschermingsvereisten werden ondersteund en geïmplementeerd in de cloudgebaseerde services van Microsoft 365 Enterprise.

## <a name="contosos-data-security-classification"></a>De classificatie van de gegevensbescherming van Contoso

Contoso heeft een analyse uitgevoerd op hun gegevens en heeft de volgende niveaus bepaald.

||||
|:-------|:-----|:-----|
| **Niveau 1: basislijn** | **Niveau 2: gevoelig** | **Niveau 3: sterk gereglementeerd** |
| Gegevens zijn versleuteld en alleen beschikbaar voor geverifieerde gebruikers. <BR> <BR> Geleverd voor alle gegevens die on-premises zijn opgeslagen en in cloudgebaseerde opslag en workloads, zoals Office 365. Gegevens worden versleuteld wanneer ze zich in de service bevinden en tijdens de overdracht tussen de service en de clientapparaten. <BR><BR> Voorbeelden van gegevens van niveau 1 zijn normale bedrijfscommunicatie (e-mail) en bestanden voor administratieve, verkoop- en ondersteuningsmedewerkers. | Niveau 1 plus krachtige verificatie en bescherming tegen gegevensverlies. <BR> <BR> Geavanceerde verificatie omvat Azure Meervoudige Verificatie (MFA) met SMS-validatie. Met preventie van gegevensverlies wordt voorkomen dat gevoelige of kritieke informatie wordt verzonden buiten de Microsoft-Cloud. <BR><BR> Voorbeelden van gegevens op niveau 2 zijn financiële en juridische informatie en onderzoeks- en ontwikkelingsgegevens voor nieuwe producten. | Niveau 2 plus de hoogste niveaus van versleuteling, verificatie en controle. <BR> <BR>  De hoogste niveaus van codering voor gegevens in de service en in de Cloud, conform de regionale voorschriften, gecombineerd met MFA met smartcards en granulaire controle en waarschuwingen. <BR> <BR> Voorbeelden van gegevens van niveau 3 zijn persoonlijk identificeerbare klant- en partnergegevens, product technische specificaties en speciale productietechnieken.  |
||||

## <a name="contosos-information-policies"></a>Het gegevensbeleid van Contoso
In de volgende tabel ziet u het gegevensbeleid van Contoso.

|||||
|:-------|:-----|:-----|:-----|
|  | **Toegang** | **Gegevensretentie** | **Informatiebescherming** |
| Lage bedrijfswaarde (niveau 1: basislijn) | Geef iedereen toegang  | 6 maanden | Gebruik versleuteling. |
| Gemiddelde bedrijfswaarde (niveau 2: gevoelig) | Sta toegang toe aan Contoso-medewerkers, onderaannemers en partners <BR> <BR> Gebruik MFA, TLS (Transport Layer Security) en Mobile Application Management (MAM). | 2 jaar  | Gebruik hash-waarden voor gegevensintegriteit.  |
| Hoge bedrijfswaarde (niveau 3: sterk gereglementeerd) | Sta toegang toe aan leidinggevenden en leads in engineering en productie. <BR> <BR> Rights Management System (RMS) met alleen beheerde netwerkapparaten.  | 7 jaar  | Gebruik digitale handtekeningen voor niet-afwijzing.  |
|||||

## <a name="contosos-path-to-information-protection-with-microsoft-365-enterprise"></a>Contoso‘s pad naar informatiebescherming met Microsoft 365 Enterprise

Contoso heeft de volgende stappen genomen om Microsoft 365 Enterprise voor te bereiden op de vereisten voor informatiebescherming:

1. Geïdentificeerd welke gegevens te beveiligen

   Contoso heeft een uitgebreide beoordeling uitgevoerd van hun bestaande digitale activa die zich op on-premises SharePoint-sites en bestandsshares bevinden, en heeft ze allemaal geclassificeerd.

2. Beleid voor toegang, bewaren en informatiebescherming voor gegevensniveaus bepaald

   Op basis van de gegevensniveaus heeft Contoso gedetailleerde beleidsvereisten opgesteld, die werden gebruikt om bestaande digitale activa te beveiligen zodra ze naar de Cloud werden verplaatst.

3. Gevoeligheidslabels en hun instellingen voor de verschillende informatieniveaus gemaakt

   Contoso heeft gevoeligheidslabels gemaakt voor hun gegevensniveaus, met het label Sterk gereglementeerd dat codering, machtigingen en watermerken omvat.

4. Beveiligde SharePoint-sites gemaakt voor gevoelige en sterk gereguleerde gegevens met machtigingen die de toegang blokkeren

   Zowel gevoelige als sterk gereguleerde sites zijn geconfigureerd als privé-teamsites met aanvullende machtigingsbeperkingen. Gevoelige en sterk gereguleerde SharePoint-sites werden ook geconfigureerd met een bijbehorend retentielabel. Bestanden die zijn opgeslagen op sterk gereguleerde SharePoint-sites, worden beschermd met een gevoeligheidssublabel van het label Sterk gereglementeerd. Zie de [SharePoint-sites voor een sterk gereglementeerd gegevensscenario](teams-sharepoint-online-sites-highly-regulated-data.md) voor meer informatie.

5.  Gegevens verplaatst van on-premises SharePoint-sites en bestandsshares naar de nieuwe SharePoint-sites

    De bestanden die naar de nieuwe SharePoint-sites zijn gemigreerd, hebben de standaardretentielabels overgenomen die aan de site zijn toegewezen.

6.  Getrainde medewerkers over het gebruik van gevoeligheidslabels voor nieuwe documenten, hoe om te gaan met de IT-afdeling van Contoso bij het maken van nieuwe SharePoint-sites en om altijd digitale middelen op SharePoint-sites op te slaan

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
- Exchange Online maakt gebruik van Office 365-berichtversleuteling voor Exchange Online.
- SharePoint gebruikt door de app afgedwongen beperkingen.
- SharePoint gebruikt toegangsbeleidsregels voor alleen-browser toegang en om toegang te blokkeren voor niet-beheerde apparaten.

## <a name="mapping-microsoft-365-enterprise-features-to-contosos-data-levels"></a>Microsoft 365 Enterprise-functies toewijzen aan het gegevensniveau van Contoso

In de volgende tabel worden de gegevensniveaus van Contoso aan informatiebeschermingsfuncties in Microsoft 365 Enterprise toegewezen.

|||||
|:-------|:-----|:-----|:-----|
| | **Office 365** | **Windows 10- en Microsoft 365-apps voor ondernemingen** | **EMS** |
| Niveau 1: basislijn  | Voorwaardelijke toegangsbeleidsregels voor SharePoint en Exchange Online <BR> Machtigingen op SharePoint-sites | Gevoeligheidslabels <BR> BitLocker <BR> Windows-gegevensbescherming | Beleid voor voorwaardelijke toegang van apparaten en beleid voor Mobile Application Management |
| Niveau 2: gevoelig | Niveau 1 plus: <BR> <BR> Gevoeligheidslabels <BR> Microsoft 365-bewaarlabels op SharePoint-sites <BR> Preventie van gegevensverlies voor SharePoint en Exchange Online <BR> Geïsoleerde SharePoint-sites  | Niveau 1 plus: <BR> <BR> Gevoeligheidslabels voor digitale activa  | Niveau 1 |
| Niveau 3: sterk gereglementeerd | Niveau 2 plus: <BR><BR> Bring Your Own Key (BYOK) encryptie en bescherming voor bedrijfsgeheimen <BR> Azure Key Vault voor bedrijfstoepassingen die communiceren met Microsoft 365-services | Niveau 2 | Niveau 1 |
|||||

Hier ziet u de resulterende configuratie van de informatiebescherming van Contoso.

![De resulterende configuratie van de informatiebescherming van Contoso.](../media/contoso-info-protect/contoso-info-protect-fig2.png)

## <a name="next-step"></a>Volgende stap

[Zie](contoso-security-summary.md) hoe Contoso de beveiligingsfuncties van Microsoft 365 Enterprise heeft gebruikt voor identiteits-en toegangsbeheer, bedreigingsbeveiliging, informatiebescherming en beveiligingsbeheer.

## <a name="see-also"></a>Zie ook

[informatiebescherming voor Microsoft 365 Enterprise](infoprotect-infrastructure.md)

[Implementatiehandleiding](deploy-microsoft-365-enterprise.md)

[Testlabrichtlijnen](m365-enterprise-test-lab-guides.md)


