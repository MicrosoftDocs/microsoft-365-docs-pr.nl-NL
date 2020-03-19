---
title: Omgaan met false positives of false negatives in AIR in Microsoft Threat Protection
description: Is er iets gemist of verkeerd gedetecteerd door AIR in Microsoft Threat Protection? Meer informatie over het indienen van false positives of false negatives bij Microsoft voor analyse.
keywords: geautomatiseerd, onderzoek, alert, trigger, actie, sanering, vals-positief, vals-negatief
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 01/29/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 2f3808f599caa4ed347fc182005397c14b9f51b2
ms.sourcegitcommit: 133bf7936e5ef1a4d06998429d0d01096bda929f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42810458"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Omgaan met false positives/negatives in geautomatiseerde onderzoeks- en reactiemogelijkheden

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging

Hebben [geautomatiseerde onderzoeks- en reactiemogelijkheden](mtp-autoir.md) in Microsoft Threat Protection iets gemist of verkeerd gedetecteerd? Er zijn stappen die u nemen om het te repareren. U kunt:

- [Een fout-positief/negatief melden aan Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);

- [Pas uw waarschuwingen aan](#adjust-an-alert-to-prevent-false-positives-from-recurring) (indien nodig); En 

- [Herstelacties ongedaan maken die op apparaten zijn uitgevoerd.](#undo-a-remediation-action-that-was-taken-on-a-device) 

Gebruik dit artikel als een gids. 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Een fout-positief/negatief melden aan Microsoft voor analyse

|Object gemist of ten onrechte gedetecteerd |Service  |Wat te doen  |
|---------|---------|---------|
|- E-mailbericht <br/>- E-mailbijlage <br/>- URL in een e-mailbericht<br/>- URL in een Office-bestand      |[Geavanceerde bedreigingsbeveiliging van Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[Vermoedelijke spam, phish, URL's en bestanden verzenden naar Microsoft voor het scannen van Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|Bestand of app op een apparaat    |[Geavanceerde bescherming voor geavanceerde bedreigingen van Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection)         |[Een bestand indienen bij Microsoft voor malware-analyse](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Een waarschuwing aanpassen om te voorkomen dat fout-positieven terugkeren

|Scenario |Service |Wat te doen |
|--------|--------|--------|
|- Een waarschuwing wordt geactiveerd door legitiem gebruik <br/>- Een waarschuwing is onjuist    |[Beveiliging van Microsoft Cloud-apps](https://docs.microsoft.com/cloud-app-security)<br/> of <br/>[Azure Advanced Threat Detection](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[Waarschuwingen beheren in de cloudapp-beveiligingsportal](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|Een bestand, IP-adres, URL of domein wordt behandeld als malware op een apparaat, ook al is het veilig|[Geavanceerde bescherming voor geavanceerde bedreigingen van Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection) |[Een aangepaste indicator maken met de actie 'Toestaan'](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>Een herstelactie ongedaan maken die op een apparaat is uitgevoerd

Als er een herstelactie is uitgevoerd op een apparaat (zoals een Windows 10-apparaat) en het item daadwerkelijk schoon is, kan uw beveiligingsteam de herstelactie in het [actiecentrum](mtp-action-center.md)ongedaan maken.

> [!IMPORTANT]
> Zorg ervoor dat u over de [benodigde machtigingen beschikt](mtp-action-center.md#required-permissions-for-action-center-tasks) voordat u probeert de volgende taak uit te voeren.

1. Ga [https://security.microsoft.com](https://security.microsoft.com) naar en meld je aan. 

2. Kies In het navigatiedeelvenster de optie **Actiecentrum**. 

3. Selecteer op het tabblad **Historie** een actie die u ongedaan wilt maken. Dit opent een flyout.<br/>
    > [!TIP]
    > Gebruik filters om de lijst met resultaten te beperken. 

4. Selecteer in de flyout voor het geselecteerde item de **optie Onderzoekspagina openen**.

5. Selecteer in de weergave Onderzoeksdetails het tabblad **Handelingen.**

6. Selecteer een item met de status **Voltooid**en zoek naar een koppeling, zoals **Goedgekeurd,** in de kolom **Besluiten.** Dit opent een flyout met meer details over de actie.

7. Als u de actie ongedaan wilt maken, selecteert u **Herstel verwijderen**.

## <a name="related-articles"></a>Verwante artikelen

- [Acties met betrekking tot geautomatiseerd onderzoek en antwoord goedkeuren of afwijzen](mtp-autoir-actions.md)

- [Meer informatie over het actiecentrum](mtp-action-center.md)

- [Proactief op zoek naar bedreigingen met geavanceerde jacht in Microsoft Threat Protection](advanced-hunting-overview.md)
