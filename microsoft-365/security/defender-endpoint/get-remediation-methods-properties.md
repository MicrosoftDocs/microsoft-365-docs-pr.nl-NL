---
title: Methoden en eigenschappen voor herstelactiviteiten
description: De API-reactie bevat bedreigingen & herstelactiviteiten voor kwetsbaarheidsbeheer die in uw tenant zijn gemaakt. U kunt alle herstelactiviteiten, slechts één herstelactiviteit of informatie over blootgestelde apparaten voor een geselecteerde hersteltaak aanvragen.
keywords: api's, herstel, herstel-api, get, hersteltaken,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f720d638ec469523a1d567dee9c01fa0974b0090
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061122"
---
# <a name="remediation-activity-methods-and-properties"></a>Methoden en eigenschappen voor herstelactiviteiten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

De API-reactie bevat [herstelactiviteiten & beveiligingsprobleembeheer](next-gen-threat-and-vuln-mgt.md)   die zijn gemaakt in uw tenant.  

## <a name="methods"></a>Methoden

Methode | Gegevenstype | Beschrijving
:---|:---|:---
[Alle herstelactiviteiten op een lijst zetten](get-remediation-all-activities.md) | Onderzoeksverzameling | Retourneert informatie over alle herstelactiviteiten.
[Belichte apparaten van één herstelactiviteit op de lijst](get-remediation-exposed-devices-activities.md) | Onderzoeksentiteit | Retourneert informatie over blootgestelde apparaten voor de opgegeven herstelactiviteit.
[Eén herstelactiviteit per id](get-remediation-one-activity.md) | Onderzoeksentiteit | Retourneert gegevens voor de opgegeven herstelactiviteit.

Meer informatie over [herstelactiviteiten.](tvm-remediation.md)

## <a name="properties"></a>Eigenschappen

Eigenschaps-id | Gegevenstype | Beschrijving
:---|:---|:---
categorie | Tekenreeks | Categorie van de herstelactiviteit (software-/beveiligingsconfiguratie)
completerEmail | Tekenreeks | Als de herstelactiviteit handmatig is voltooid door iemand, bevat deze kolom zijn of haar e-mail
completerId | Tekenreeks | Als de herstelactiviteit handmatig is voltooid door iemand, bevat deze kolom de object-id
completionMethod | Tekenreeks | Een herstelactiviteit kan 'automatisch' worden voltooid (als alle apparaten zijn gepatcht) of 'handmatig' door een persoon die 'markeren als voltooid' selecteert.
gemaaktOn | DateTime | Tijd dat deze herstelactiviteit is gemaakt
beschrijving | Tekenreeks | Beschrijving van deze herstelactiviteit
dueOn | DateTime | Einddatum die de maker heeft ingesteld voor deze herstelactiviteit
fixedDevices |  | Het aantal apparaten dat is opgelost
id | Tekenreeks | Id van deze herstelactiviteit
nameId | Tekenreeks | Verwante productnaam
prioriteit | Tekenreeks | Prioriteit die de maker heeft ingesteld voor deze herstelactiviteit (Hoog\Gemiddeld\Laag)
productId | Tekenreeks | Gerelateerde product-id
productiviteitImpactRemediationType | Tekenreeks | Er kunnen alleen enkele configuratiewijzigingen worden aangevraagd voor apparaten zonder dat dit gevolgen heeft voor de gebruiker. Deze waarde geeft de selectie aan tussen 'alle blootgestelde apparaten' of 'alleen apparaten zonder invloed van de gebruiker'.
rbacGroupNames | Tekenreeks | Namen van gerelateerde apparaatgroep
aanbevolenProgram | Tekenreeks | Aanbevolen programma om een upgrade uit te voeren naar
aanbevolenVendor | Tekenreeks | Aanbevolen leverancier om een upgrade uit te voeren naar
aanbevolenVersie | Tekenreeks | Aanbevolen versie om bij te werken/upgraden naar
relatedComponent | Tekenreeks | Gerelateerd onderdeel van deze herstelactiviteit (vergelijkbaar met het gerelateerde onderdeel voor een beveiligingsaanbeveling)
requesterEmail | Tekenreeks | E-mailadres maker
requesterId | Tekenreeks | Creator-object-id
requesterNotes | Tekenreeks | De notities (vrije tekst) die de maker heeft toegevoegd voor deze herstelactiviteit
scid | Tekenreeks | SCID van de gerelateerde beveiligingsaanbeveling
status | Tekenreeks | Status van herstelactiviteit (actief/voltooid)
statusLastModifiedOn | DateTime | Datum waarop het statusveld is bijgewerkt
targetDevices | Lang | Het aantal blootgestelde apparaten dat door deze herstel wordt toegepast op
titel | Tekenreeks | Titel van deze herstelactiviteit
type | Tekenreeks | Hersteltype
vendorId | Tekenreeks | Naam van gerelateerde leverancier

## <a name="see-also"></a>Zie ook

- [Eén herstelactiviteit per id](get-remediation-one-activity.md)

- [Alle herstelactiviteiten op een lijst zetten](get-remediation-all-activities.md)

- [Belichte apparaten van één herstelactiviteit op de lijst](get-remediation-exposed-devices-activities.md)

- [Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer](next-gen-threat-and-vuln-mgt.md)

- [Beveiligingslekken in uw organisatie](tvm-weaknesses.md)
