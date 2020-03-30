---
title: Teams implementeren voor drie beveiligingslagen voor bestanden
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: Maak en configureer teams met Microsoft Teams voor verschillende niveaus gegevensbeveiliging voor bestanden.
ms.openlocfilehash: 63a4b6763165f38e1de5331324e5a7b3573ea0f1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805913"
---
# <a name="deploy-teams-for-three-tiers-of-protection-for-files"></a>Teams implementeren voor drie beveiligingslagen voor bestanden

Gebruik de stappen in dit artikel om basislijnteams en gevoelige en zeer vertrouwelijke teams te ontwerpen en te implementeren. Zie [Bestanden beveiligen in Microsoft Teams](secure-files-in-teams.md) voor meer informatie over deze drie beveiligingslagen.

## <a name="baseline-teams"></a>Basislijnteams

Basislijnbeveiliging omvat zowel openbare teams als privéteams. Openbare teams kunnen door iedereen in de organisatie worden gedetecteerd en geopend. Privéteams kunnen alleen worden gedetecteerd en geopend door leden van de Office 365-groep die is gekoppeld aan het team. Met beide typen teams kunnen leden de site delen met anderen.

### <a name="public"></a>Openbaar

Volg de instructies in [dit artikel](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) om een basislijnteam met openbare toegang en machtigingen te maken.

Dit is de resulterende configuratie.

![Basislijnbeveiliging voor een openbaar team.](../../media/baseline-public-team.png)

### <a name="private"></a>Privé

Volg de instructies in [dit artikel](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) om een basislijnteam met persoonlijke toegang en machtigingen te maken.

Dit is de resulterende configuratie.

![Basislijnbeveiliging voor een privéteam.](../../media/baseline-private-team.png)

## <a name="sensitive-teams"></a>Gevoelige teams

Voor een gevoelig team begint u met [het maken van een privéteam](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).

Vervolgens configureert u de onderliggende SharePoint-site om het delen door teamleden te voorkomen.

1. Klik op de werkbalk van het team op **Bestanden**.

2. Klik op het beletselteken en klik vervolgens op **Openen in SharePoint**.

3. Klik op de werkbalk van de onderliggende SharePoint-site op het pictogram Instellingen en vervolgens op **Sitemachtigingen**.

4. Klik in het deelvenster **Sitemachtigingen** onder **Instellingen voor delen** op **Instellingen voor delen wijzigen**.

5. Kies onder **Machtigingen voor delen** de optie **Alleen site-eigenaren kunnen bestanden, mappen en de site delen** en klik vervolgens op **Opslaan**.

Dit is de resulterende configuratie.

![Bescherming van gevoelige gegevens voor een team.](../../media/sensitive-team.png)

## <a name="highly-confidential-teams"></a>Zeer vertrouwelijke teams

Voor een zeer vertrouwelijk team begint u met [het maken van een privéteam](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).

Vervolgens configureert u de onderliggende SharePoint-site om het delen door teamleden en het aanvragen van toegang door niet-leden van het team te voorkomen.

1. Klik op de werkbalk van het team op **Bestanden**.

2. Klik op het beletselteken en klik vervolgens op **Openen in SharePoint**.

3. Klik op de werkbalk van de onderliggende SharePoint-site op het pictogram Instellingen en vervolgens op **Sitemachtigingen**.

4. Klik in het deelvenster **Sitemachtigingen** onder **Instellingen voor delen** op **Instellingen voor delen wijzigen**.

5. Kies onder **Machtigingen voor delen**, **Alleen site-eigenaren kunnen bestanden, mappen en de site delen**.

6. Schakel **Toegangsaanvragen toestaan** uit en klik op **Opslaan**.

Dit is de resulterende configuratie.

![Bescherming van zeer vertrouwelijke gegevens voor een team.](../../media/highly-confidential-team.png)

## <a name="next-step"></a>Volgende stap

[Bestanden in teams beveiligen met retentielabels en DLP](deploy-teams-retention-DLP.md)

## <a name="see-also"></a>Zie ook

[Bestanden beveiligen in Microsoft Teams](secure-files-in-teams.md)

[Cloud adoption and hybrid solutions](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions) (Overstappen op de cloud en hybride oplossingen)
