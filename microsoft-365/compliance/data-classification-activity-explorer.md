---
title: Aan de slag met de activiteitenverkenner
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Activiteitsverkenner rondt de functionaliteit van de functie gegevensclassificatie af door u te laten zien en filteren op de acties die gebruikers uitvoeren op uw gelabelde inhoud.
ms.openlocfilehash: 414ef4e5d9f6472180a5eaef391d3eba33463b02
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162883"
---
# <a name="get-started-with-activity-explorer"></a>Aan de slag met de activiteitenverkenner

Het [overzicht van de gegevensclassificatie](data-classification-overview.md) [en](data-classification-content-explorer.md) de tabbladen van de inhoudsverkenner geven u inzicht in welke inhoud is gevonden en gelabeld en waar die inhoud zich vindt. Activiteitsverkenner rondt deze suite met functionaliteit af door u te laten controleren wat er met uw gelabelde inhoud wordt gedaan. Activiteitsverkenner biedt een historische weergave van activiteiten op uw gelabelde inhoud. De activiteitsgegevens worden verzameld uit Microsoft 365 geïntegreerde auditlogboeken, getransformeerd en beschikbaar gesteld in de gebruikersinterface van Activity Explorer. 

![placeholder screenshot overview activity explorer](../media/data-classification-activity-explorer-1.png)

Er zijn meer dan 30 verschillende filters beschikbaar voor gebruik, sommige zijn:

- datumbereik
- activiteitstype
- locatie
- gebruiker
- gevoeligheidslabel
- bewaarlabel
- bestandspad
- DLP-beleid



## <a name="prerequisites"></a>Vereisten

Aan elk account dat toegang krijgt tot en gebruikmaakt van gegevensclassificatie moet een licentie zijn toegewezen vanuit een van deze abonnementen:

- Microsoft 365 E5
- Office 365 E5
- Geavanceerde hulpprogramma's voor compliance (E5) invoegtoepassing
- Geavanceerde bedreigingsinformatie (E5) invoegtoepassing
- Microsoft 365 E5/A5 Info Protection & Governance
- Microsoft 365 E5/A5 Compliance

### <a name="permissions"></a>Machtigingen

 Als u toegang wilt krijgen tot het tabblad Activiteitsverkenner, moet aan een account expliciet lidmaatschap zijn toegewezen aan een van deze rollengroepen of expliciet aan de rol zijn toegewezen.

<!--
> [!IMPORTANT]
> Access to Activity explorer via the Security reader or Device Management role groups or other has been removed-->

**Microsoft 365-rollengroepen**

- Globale beheerder
- Beheerder voor naleving
- Beveiligingsbeheerder
- Beheerder van nalevingsgegevens

**Microsoft 365 rollen**

- Beheerder voor naleving
- Beveiligingsbeheerder

## <a name="activity-types"></a>Activiteitstypen

Activiteitsverkenner verzamelt activiteitsgegevens uit de auditlogboeken op meerdere bronnen van activiteiten. Zie [Labeling events available in Activity explorer (Labeling events available in Activity explorer)](data-classification-activity-explorer-available-events.md)voor meer informatie over de labelactiviteit die activiteit maakt voor Activiteitsverkenner.

**Activiteiten voor** gevoeligheidslabels en activiteiten voor het bewaren van etiketten van Office native toepassingen, azure information protection-invoegtoepassingen, SharePoint Online, Exchange Online (alleen gevoeligheidslabels) en OneDrive.  Enkele voorbeelden zijn:

- label toegepast
- label gewijzigd (bijgewerkt, gedegradeerd of verwijderd)
- automatische labelingsimulatie
- bestand gelezen 

**AIP-scanner (Azure Information Protection) en AIP-clients**

- toegepaste beveiliging
- beveiliging gewijzigd
- beveiliging verwijderd
- bestanden die zijn gevonden 

Activiteitenverkenner  verzamelt ook DLP-beleidsgebeurtenissen uit Exchange Online, SharePoint Online, OneDrive, Teams Chat en Kanaal (preview), on-premises SharePoint-mappen en -bibliotheken, on-premises bestandsaandelen en Windows 10-apparaten via **Endpoint Data Loss Prevention (DLP).** Enkele voorbeelden van gebeurtenissen Windows 10 apparaten zijn bestand:

- verwijderingen
- creaties
- gekopieerd naar klembord
- gewijzigd
- gelezen
- afgedrukt
- naam gewijzigd
- gekopieerd naar netwerk delen
- toegankelijk via niet-toegestaan app 

De waarde van het begrijpen van de acties die worden ondernomen met uw gevoelige inhoud met [](dlp-learn-about-dlp.md) het label is dat u kunt zien of de besturingselementen die u al hebt gebruikt, zoals preventie van gegevensverlies, effectief zijn of niet. Zo niet, of als u iets onverwachts ontdekt, zoals een groot aantal items met een label en een downgrade, kunt u uw verschillende beleidsregels beheren en nieuwe acties ondernemen om ongewenst gedrag te `highly confidential` `general` beperken.

> [!NOTE]
> Activiteitsverkenner controleert momenteel geen bewaaractiviteiten voor Exchange Online.

## <a name="see-also"></a>Zie ook

- [Meer informatie over vertrouwelijkheidslabels](sensitivity-labels.md)
- [Meer informatie over bewaarbeleid en retentielabels](retention.md)
- [Meer informatie over typen gevoelige informatie](sensitive-information-type-learn-about.md)
- [Meer informatie over gegevensclassificatie](data-classification-overview.md)
