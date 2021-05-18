---
title: Aan de slag met de inhoudsverkenner
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Met inhoudsverkenner kunt u items met een label standaard weergeven.
ms.openlocfilehash: b39dd09012e7cde6c19ea88a0915154da84c712a
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162949"
---
# <a name="get-started-with-content-explorer"></a>Aan de slag met de inhoudsverkenner

Met de gegevensclassificatie-inhoudsverkenner kunt u de items die op de overzichtspagina zijn samengevat, standaard bekijken.

![schermopname van inhoudsverkenner samengevouwen](../media/data-classification-content-explorer-1.png)

## <a name="prerequisites"></a>Vereisten

Aan elk account dat toegang krijgt tot en gebruikmaakt van gegevensclassificatie moet een licentie zijn toegewezen vanuit een van deze abonnementen:

- Microsoft 365 E5
- Office 365 E5
- Geavanceerde hulpprogramma's voor compliance (E5) invoegtoepassing
- Geavanceerde bedreigingsinformatie (E5) invoegtoepassing
- Microsoft 365 E5/A5 Info Protection & Governance
- Microsoft 365 E5/A5 Compliance


### <a name="permissions"></a>Machtigingen

Als u toegang wilt krijgen tot het tabblad Inhoudsverkenner, moet aan een account een lidmaatschap zijn toegewezen voor een van deze rollen of rollengroepen. 

**Microsoft 365-rollengroepen**

- Globale beheerder
- Beheerder voor naleving
- Beveiligingsbeheerder
- Beheerder van nalevingsgegevens

> [!IMPORTANT]
> Lidmaatschap van deze rollengroepen betekent niet dat u de lijst met items in Inhoudsverkenner of de inhoud van de items in Inhoudsverkenner kunt bekijken.

### <a name="required-permissions-to-access-items-in-content-explorer"></a>Vereiste machtigingen voor toegang tot items in Inhoudsverkenner

Toegang tot Inhoudsverkenner wordt sterk beperkt omdat u hiermee de inhoud van gescande bestanden kunt lezen.

> [!IMPORTANT]
> Deze machtigingen bevatten machtigingen die lokaal zijn toegewezen aan de items, zodat de inhoud kan worden bekeken. 

Er zijn twee rollen die toegang verlenen tot Inhoudsverkenner. Deze rollen wordt toegekend via het [Beveiligings- en compliancecentrum van Microsoft](https://protection.office.com/permissions):

- **Inhoudsverkenner lijstweergave**: met lidmaatschap van deze rollengroep kunt u elk item en de locatie in de lijstweergave bekijken. De `data classification list viewer`-rol is vooraf toegewezen aan deze rollengroep.

- **Inhoudsverkenner inhoudsweergave**: met lidmaatschap van deze rollengroep kunt u de inhoud van elk item in de lijst bekijken. De `data classification content viewer`-rol is vooraf toegewezen aan deze rollengroep.

Het account dat u gebruikt voor toegang tot Inhoudsverkenner, moet zich in een van de rollengroepen of in beide rollengroepen bevinden. Dit zijn onafhankelijke rollengroepen en zijn niet cumulatief. Als u bijvoorbeeld een account de mogelijkheid wilt bieden om de items en hun locaties alleen te bekijken, verleent u de viewerrechten voor de Inhoudsverkenner-lijst. Als u wilt dat dit account ook de inhoud van de items in de lijst kan bekijken, verleent u inhoudsviewerrechten voor Inhoudsverkenner.

U kunt een van beide rollen of beide toewijzen aan een aangepaste rollengroep om de toegang tot Inhoudsverkenner aan te passen.

Een globale beheerder, compliancebeheerder of gegevensbeheerder kan het benodigde lidmaatschap van de Inhoudsverkenner-lijstviewer en inhoudsverkenner voor inhoudsviewer toewijzen.

## <a name="content-explorer"></a>Inhoudsverkenner

Inhoudsverkenner toont een huidige weergave van de items met een vertrouwelijkheidslabel of retentielabel, en items die binnen uw organisatie zijn geclassificeerd als een type gevoelige informatie.

### <a name="sensitive-information-types"></a>Typen gevoelige informatie

Met een [DLP-beleid](dlp-learn-about-dlp.md) wordt gevoelige informatie beschermd, die is gedefinieerd als een **type gevoelige informatie**. Microsoft 365 bevat [definities voor veelvoorkomende typen gevoelige informatie die](sensitive-information-type-entity-definitions.md) uit veel verschillende regio's die u direct kunt gebruiken. Bijvoorbeeld een creditcardnummer, bankrekeningnummers, nationale identiteitsnummers en Windows Live ID-servicenummers.

> [!NOTE]
> Inhoudsverkenner scant momenteel niet op typen vertrouwelijke informatie in Exchange Online.

### <a name="sensitivity-labels"></a>Vertrouwelijkheidslabels

Een [vertrouwelijkheidslabel](sensitivity-labels.md) is gewoon een label dat de waarde van het item voor uw organisatie aangeeft. Dit kan handmatig of automatisch worden toegepast. Nadat het is toegepast, wordt dit ingesloten in het document en wordt het overal toegepast. Een vertrouwelijkheidslabel biedt diverse beschermingskenmerken, zoals verplicht watermerk of versleuteling.

Vertrouwelijkheidslabels moeten zijn ingeschakeld voor bestanden in SharePoint en OneDrive, zodat de overeenkomende gegevens op de pagina met de gegevensclassificatie worden weergegeven. Zie [Vertrouwelijkheidslabels inschakelen voor Office-bestanden in SharePoint en OneDrive](sensitivity-labels-sharepoint-onedrive-files.md) voor meer informatie.

### <a name="retention-labels"></a>Bewaarlabels

Met [bewaarlabel](retention.md) kunt u definiëren hoelang een gelabeld item wordt bewaard en kunt u de stappen definiëren voordat u het verwijderd. Ze kunnen handmatig of automatisch worden toegepast via beleid. Ze kunnen een rol spelen bij het voldoen aan wettelijke en wettelijke vereisten van uw organisatie.

### <a name="how-to-use-content-explorer"></a>Inhoudsverkenner gebruiken

1. Open **Microsoft 365-compliancecentrum**  > **Gegevensclassificatie** > **Inhoudsverkenner**.
2. Als u de naam van het label of het type gevoelige informatie weet, kunt u dit typen in het filtervak.
3. U kunt ook naar het item bladeren door het labeltype uit te breiden en het label in de lijst te selecteren.
4. Selecteer een locatie onder **Alle locaties** en zoom in op de mapstructuur van het item.
5. Dubbelklik om het item te openen in Inhoudsverkenner.

### <a name="export"></a>Exporteren
Met het besturingselement voor **exporteren** wordt een CSV-bestand met een lijst weergegeven van wat wordt weergegeven in het deelvenster **Alle locaties** openen.

![exportbesturingselement voor gegevensclassificatie](../media/data_classification_export_control.png)


### <a name="search"></a>Zoeken

Wanneer u inzoomt op een locatie, zoals een Exchange-map, of een SharePoint- of OneDrive-site, wordt het hulpprogramma **zoeken** weergegeven.

![zoekrool voor Inhoudsverkenner](../media/data_classification_search_tool.png)


Het bereik van de zoektool is wat wordt weergegeven in het deelvenster **Alle locaties** en waar u op kunt zoeken varieert afhankelijk van de geselecteerde locatie. 

Wanneer **Exchange** de geselecteerde locatie is, kunt u zoeken op het volledige e-mailadres van het postvak, bijvoorbeeld `user@domainname.com`.

Wanneer **SharePoint** of **OneDrive** zijn geselecteerd, wordt de zoektool weergegeven wanneer u inzoomt op sitenamen, mappen en bestanden. 

> [!NOTE]
> **OneDrive** Tijdens ons preview-programma hebben we geluisterd naar uw waardevolle feedback over de integratie met OneDrive. Op basis van deze feedback blijft de OneDrive-functionaliteit in preview totdat alle problemen zijn opgelost. Afhankelijk van uw tenant zien sommige klanten OneDrive mogelijk niet als locatie. Wij waarderen uw ondersteuning hierbij.

U kunt zoeken op:


|waarde|Voorbeeld:  |
|---------|---------|
|volledige sitenaam    |`https://contoso.onmicrosoft.com/sites/sitename`    |
|naam van hoofdmap - alle submappen worden opgeslagen    | `/sites`        |
|Bestandsnaam    |    `RES_Resume_1234.txt`     |
|tekst aan het begin van bestandsnaam| `RES`|
|Tekst na een onderstrepingsteken (_) in bestandsnaam|`Resume` of `1234`| 
|bestandsextensie|`txt`|


## <a name="see-also"></a>Zie ook

- [Meer informatie over vertrouwelijkheidslabels](sensitivity-labels.md)
- [Meer informatie over bewaarbeleid en retentielabels](retention.md)
- [Definities van entiteiten van het type vertrouwelijke gegevens.md](sensitive-information-type-entity-definitions.md)
- [Meer informatie over preventie van gegevensverlies](dlp-learn-about-dlp.md)