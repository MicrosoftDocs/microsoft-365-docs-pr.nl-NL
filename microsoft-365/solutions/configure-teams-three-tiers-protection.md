---
title: Teams met drie beschermingsniveaus configureren
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
- m365solution-securecollab
- m365solution-scenario
ms.custom:
- Ent_Architecture
ms.assetid: 1d51bd87-17bf-457c-b698-61821de3afa0
description: Configuratieaanbevelingen voor het beveiligen van bestanden in Microsoft Teams.
ms.openlocfilehash: e1ec598bede2419abc19db2dbe3fd3ff63d8f583
ms.sourcegitcommit: 24ccb910ffac4d065c512a57c5decd9dd19ef4c1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/19/2020
ms.locfileid: "48594928"
---
# <a name="configure-teams-with-three-tiers-of-protection"></a>Teams met drie beschermingsniveaus configureren

De artikelen in deze serie bevatten aanbevelingen voor het configureren van teams in Microsoft Teams en de bijbehorende SharePoint-sites voor bestandsbeveiliging waardoor beveiliging en gemak van samenwerking hand in hand gaan.

In dit artikel worden vier verschillende configuraties gedefinieerd, te beginnen met een openbaar team met het meest liberale beleid voor het delen van bestanden. Elke extra configuratie vertegenwoordigt een zinvolle stap in de bescherming, terwijl de mogelijkheid om bestanden die in teams zijn opgeslagen, te openen en eraan samen te werken, is beperkt tot de desbetreffende groep teamleden. 

De configuraties in dit artikel zijn in overeenstemming met de aanbevelingen van Microsoft voor de drie beveiligingslagen voor gegevens, identiteiten en apparaten:

- Basisbescherming

- bescherming van gevoelige gegevens

- Bescherming van zeer gevoelige gegevens

Voor meer informatie over deze lagen en aanbevolen functionaliteiten voor elke afzonderlijke laag, gaat u naar [Illustraties voor Microsoft Cloud voor Enterprise Architects](https://docs.microsoft.com/microsoft-365/solutions/cloud-architecture-models)


## <a name="three-tiers-at-a-glance"></a>Drie lagen in een oogopslag

De volgende tabel bevat een overzicht van de configuraties voor elke laag. Gebruik deze configuraties als uitgangspunt en pas de configuraties aan de behoeften van uw organisatie aan. Het is mogelijk dat u niet elke laag nodig hebt.

||Basislijn (openbaar)|Basislijn (privé)|Gevoelig|Zeer gevoelig|
|:-----|:-----|:-----|:-----|:-----|
|Privé of openbaar team|Openbaar|Privé|Privé|Privé|
|Wie heeft er toegang?|Iedereen in de organisatie, waaronder B2B-gebruikers.|Alleen leden van het team. Anderen kunnen toegang aanvragen tot de bijbehorende site.|Alleen leden van het team.|Alleen leden van het team.|
|Privékanalen|Eigenaren en leden kunnen privé-kanalen maken|Eigenaren en leden kunnen privé-kanalen maken|Alleen eigenaren kunnen privé-kanalen maken|Alleen eigenaren kunnen privé-kanalen maken|
|Gasttoegang op siteniveau|**Nieuwe en bestaande gasten** (standaard).|**Nieuwe en bestaande gasten** (standaard).|**Nieuwe en bestaande gasten** of **Alleen personen in uw organisatie** afhankelijk van de behoeften van het team.|**Nieuwe en bestaande gasten** of **Alleen personen in uw organisatie** afhankelijk van de behoeften van het team.|
|Standaardinstellingen voor het delen van een site|**Site-eigenaren en -leden, en personen met machtigingen voor bewerken kunnen bestanden en mappen delen, maar alleen site-eigenaren kunnen de site delen**.|**Site-eigenaren en -leden, en personen met machtigingen voor bewerken kunnen bestanden en mappen delen, maar alleen site-eigenaren kunnen de site delen**.|**Site-eigenaren en -leden, en personen met machtigingen voor bewerken kunnen bestanden en mappen delen, maar alleen site-eigenaren kunnen de site delen**.|**Alleen site-eigenaren kunnen bestanden, mappen en de site delen**.<br>Toegangsaanvragen **Uit**.|
|Toegang tot niet-beheerde apparaten op siteniveau|**Volledige toegang vanaf de bureaublad-apps, mobiele apps en het web** (standaard).|**Volledige toegang vanaf de bureaublad-apps, mobiele apps en het web** (standaard).|**Beperkte toegang tot alleen internet toestaan**.|**Toegang blokkeren**.|
|Standaardkoppelingstype voor delen|**Alleen personen binnen uw organisatie**|**Alleen personen binnen uw organisatie**|**Specifieke personen**|**Personen met bestaande toegang**|
|Gevoeligheidslabels|Geen|Geen|Gevoeligheidslabel voor het classificeren van het team en het beheren van delen met gasten en toegang tot niet-beheerde apparaten.|Gevoeligheidslabel voor het classificeren van het team en het beheren van delen met gasten en toegang tot niet-beheerde apparaten. Label kan ook worden gebruikt voor bestanden om bestanden te versleutelen.|

Als variatie op de zeer gevoelige optie, gebruikt [Teams met beveiligingsisolatie](secure-teams-security-isolation.md) een uniek gevoeligheidslabel voor één team, dat extra beveiliging biedt. U kunt dit label gebruiken om bestanden te versleutelen, waarna alleen leden van dat team ze kunnen lezen.

Basislijnbeveiliging omvat zowel openbare teams als privéteams. Openbare teams kunnen door iedereen in de organisatie worden gedetecteerd en geopend. Privéteams kunnen alleen door leden van het team worden gedetecteerd en geopend. Bij beide configuraties wordt het delen van de gekoppelde SharePoint-site beperkt tot teameigenaren om te helpen bij het beheren van machtigingen.

Teams met gevoelige en zeer gevoelige bescherming zijn privé-teams waarin het delen en het aanvragen van toegang voor de bijbehorende site beperkt is en waarin gevoeligheidslabels worden gebruikt voor het instellen van beleidsregels voor delen met gasten, toegang tot apparaten en versleuteling van inhoud.

## <a name="sensitivity-labels"></a>Gevoeligheidslabels

De gevoelige en zeer gevoelige lagen gebruiken gevoeligheidslabels om het team en de bijbehorende bestanden te beveiligen. Om deze lagen te implementeren, moet u [gevoeligheidslabels gebruiken om inhoud te beveiligen in Microsoft Teams, Office 365-groepen en SharePoint-sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

Hoewel de basislaag geen gevoeligheidslabels vereist, kunt u overwegen een algemeen label te maken en vervolgens te vereisen dat alle teams een label hebben. Dit zorgt ervoor dat gebruikers een bewuste keuze maken over de gevoeligheid van een team dat ze maken. Als u van plan bent de gevoelige of zeer gevoelige lagen te implementeren, raden we u aan een algemeen label te maken dat u kunt gebruiken voor basislijnteams en voor bestanden die niet gevoelig zijn.

Als u nog geen ervaring hebt met het gebruiken van gevoeligheidslabels, raden we u aan [Aan de slag met gevoeligheidslabels](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-sensitivity-labels) te lezen. 

Als u al eerder gevoeligheidslabels in uw organisatie hebt geïmplementeerd, dient u te overwegen hoe de labels die worden gebruikt in de gevoelige en zeer gevoelige passen in uw algemene labelstrategie. 

## <a name="sharing-the-sharepoint-site"></a>De SharePoint-site delen

Elk team heeft een gekoppelde SharePoint-site waarop documenten worden opgeslagen. (Dit is het tabblad **Bestanden** in een Teams-kanaal.) De SharePoint-site behoudt zijn eigen machtigingsbeheer, maar is gekoppeld aan teammachtigingen. Op de bijbehorende site worden teameigenaren opgenomen als site-eigenaren en teamleden als siteleden.

Met de resulterende machtigingen kunnen:

- Teameigenaren de site beheren en beschikken over volledige controle over de inhoud van de site.
- Teamleden bestanden op de site maken en bewerken. 

Teameigenaren en -leden kunnen standaard de site zelf delen met personen buiten het team zonder ze toe te hoeven voegen aan het team. We raden dit af aangezien dit het gebruikersbeheer moeilijker maakt en ertoe kan leiden dat personen die geen lid zijn van het team toegang hebben tot teambestanden zonder dat teameigenaren dit doorhebben. Om dit te voorkomen, raden we u aan om vanaf het beveiligingsniveau op de basislijn alleen eigenaren toestemming te geven om de site rechtstreeks te delen.

Hoewel teams geen machtiging voor alleen-lezen hebben, heeft de SharePoint-site dit wel. Als er aandeelhouders of partnergroepen zijn die teambestanden moeten kunnen bekijken, maar deze niet mogen bewerken, kunt u overwegen hen rechtstreeks aan de SharePoint-site toe te voegen met de machtiging Lezen.

## <a name="sharing-files-and-folders"></a>Bestanden en mappen delen

Zowel eigenaren en leden van het team kunnen standaard bestanden en mappen delen met personen buiten het team. Dit kunnen personen van buiten uw organisatie zijn, als u delen met gasten hebt toegestaan. In alle drie de lagen wordt het standaardkoppelingstype bijgewerkt om te voorkomen dat er per ongeluk te veel wordt gedeeld. In de zeer gevoelige laag wordt dergelijk delen beperkt tot teameigenaren.

## <a name="guest-sharing"></a>Gasten delen

Als u wilt samenwerken met personen buiten uw organisatie, raden we u aan [SharePoint- en OneDrive-integratie met Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) te configureren voor de beste manier van delen en administratie.

Delen met gasten is in Teams standaard uitgeschakeld, maar delen voor Office 365-groepen (waar het teamlidmaatschap wordt opgeslagen) en SharePoint is ingeschakeld. Wij schakelen delen in Teams in op de basislijnlaag en u kunt de functie indien nodig voor de gevoelige en zeer gevoelige lagen uitschakelen met behulp van een gevoeligheidslabel.

Het gevoeligheidslabel is alleen van invloed op het delen met gasten voor het team. Instellingen voor het delen met gasten op de gekoppelde SharePoint-site worden afzonderlijk beheerd en we laten u twee instellingen doorvoeren voor zowel de gevoelige als de zeer gevoelige lagen.

In de zeer gevoelige laag configureren we het gevoeligheidslabel zo dat het de bestanden waarop het wordt toegepast versleutelt. Als u uw gasten toegang wilt geven tot deze bestanden, moet u ze machtigingen geven wanneer u het label aanmaakt.

We raden u ten zeerste aan om delen met gasten ingeschakeld te laten voor de basislijnlaag en voor de gevoelige of zeer gevoelige laag als u moet samenwerken met personen buiten uw organisatie. De functies voor het delen met gasten in Microsoft 365 bieden een veiligere en beter beheerbare manier om bestanden te delen dan het verzenden van bestanden als bijlagen in e-mails. Hiermee wordt ook het risico op schaduw-IT beperkt, waarbij gebruikers onbeheerde consumentenproducten gebruiken om te delen met legitieme externe medewerkers.

Zie de volgende verwijzingen om een veilige en productieve omgeving voor het delen met gasten te creëren voor uw organisatie:

- [Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers](best-practices-anonymous-sharing.md)
- [Het beperken van de onopzettelijke blootstelling van bestanden bij het delen met personen buiten uw organisatie](share-limit-accidental-exposure.md)
- [Een beveiligde omgeving voor het delen met gasten maken](create-secure-guest-sharing-environment.md)

## <a name="access-from-unmanaged-devices"></a>Toegang vanaf niet-beheerde apparaten

Voor de gevoelige en zeer gevoelige lagen beperken we toegang tot SharePoint-inhoud met gevoeligheidslabels. Met voorwaardelijke toegang van Azure AD kunt u op verschillende manieren vaststellen hoe gebruikers toegang hebben tot Microsoft 365, met inbegrip van beperkingen op basis van locatie, risico, apparaatcompatibiliteit en andere factoren. We raden u aan om [Wat is voorwaardelijke toegang?](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) te lezen en na te denken over welke aanvullende beleidsregels mogelijk geschikt zijn voor uw organisatie.

## <a name="next-step"></a>Volgende stap

Begin door [het niveau van de basislijn voor bescherming](configure-teams-baseline-protection.md) te configureren. Indien nodig kunt u [gevoelige beveiliging](configure-teams-sensitive-protection.md) en [zeer gevoelige beveiliging](configure-teams-highly-sensitive-protection.md) toevoegen bovenop de basislijn.

## <a name="see-also"></a>Zie ook

[Beveiliging en compliance in Microsoft Teams](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

[Meldingsbeleid in het beveiligings- en compliancecentrum](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)
