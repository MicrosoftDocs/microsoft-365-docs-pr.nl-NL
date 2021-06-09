---
title: Methoden en eigenschappen van herstelactiviteiten
description: De API-reactie bevat bedreigingen & vulnerability management herstelactiviteiten die zijn gemaakt in uw tenant. U kunt alle herstelactiviteiten, slechts één herstelactiviteit of informatie over blootgestelde apparaten voor een geselecteerde hersteltaak aanvragen.
keywords: api's, herstel, herstel-api, get, hersteltaken, herstelmethoden, hersteleigenschappen,
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 67009961ecc3755b5af21b2e773bc817ea46bec0
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769231"
---
# <a name="remediation-activity-methods-and-properties"></a>Methoden en eigenschappen van herstelactiviteiten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Het API-antwoord bevat [bedreigings- & vulnerability management](next-gen-threat-and-vuln-mgt.md)   herstelactiviteiten die zijn gemaakt in uw tenant.  

## <a name="methods"></a>Methoden

Methode | Gegevenstype | Beschrijving
:---|:---|:---
[Alle herstelactiviteiten weergeven](get-remediation-all-activities.md) | Onderzoeksverzameling | Retourneert informatie over alle herstelactiviteiten.
[Weergegeven apparaten van één herstelactiviteit weergeven](get-remediation-exposed-devices-activities.md) | Onderzoeksentiteit | Retourneert informatie over blootgestelde apparaten voor de opgegeven herstelactiviteit.
[Eén herstelactiviteit krijgen op id](get-remediation-one-activity.md) | Onderzoeksentiteit | Retourneert gegevens voor de opgegeven herstelactiviteit.

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

- [Eén herstelactiviteit krijgen op id](get-remediation-one-activity.md)

- [Alle herstelactiviteiten weergeven](get-remediation-all-activities.md)

- [Weergegeven apparaten van één herstelactiviteit weergeven](get-remediation-exposed-devices-activities.md)

- [Risicogebaseerd & vulnerability management](next-gen-threat-and-vuln-mgt.md)

- [Beveiligingslekken in uw organisatie](tvm-weaknesses.md)
