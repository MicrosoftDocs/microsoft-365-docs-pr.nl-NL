---
title: Valse positieven of valse negatieven melden in automatisch onderzoek en reactie van Office 365
description: Is er iets gemist of verkeerd gedetecteerd door Office 365 Advanced Threat Protection? Meer informatie over het indienen van false positives of false negatives bij Microsoft voor analyse.
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
ms.date: 05/15/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 2dd67af62a400f3e217f146e6d0ee213d74ad99a
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262408"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Valse positieven/negatieven melden in geautomatiseerde onderzoeks- en reactiemogelijkheden

**Geldt voor:**
- Office 365 Advanced Threat Protection

Heeft [automatische air-mogelijkheden (investigation and response) in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) iets gemist of verkeerd gedetecteerd? Er zijn stappen die u nemen om het te repareren. U kunt:
- [Een fout-positief/negatief melden aan Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);
- [Pas uw waarschuwingen aan](#adjust-an-alert-to-prevent-false-positives-from-recurring) (indien nodig); En 
- [Herstelacties ongedaan maken die op apparaten zijn uitgevoerd.](#undo-a-remediation-action) 

Gebruik dit artikel als een gids. 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Een fout-positief/negatief melden aan Microsoft voor analyse

Als Office 365 AIR een e-mailbericht, een e-mailbijlage, een URL in een e-mailbericht of een URL in een Office-bestand heeft gemist, u [verdachte spam, phish, URL's en bestanden indienen bij Microsoft voor het scannen van Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)

U ook [een bestand indienen bij Microsoft voor malwareanalyse.](https://www.microsoft.com/wdsi/filesubmission)

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Een waarschuwing aanpassen om te voorkomen dat fout-positieven terugkeren

Als een waarschuwing wordt geactiveerd door legitiem gebruik of als de waarschuwing onjuist is, u [waarschuwingen beheren in de Cloud App Security-portal.](https://docs.microsoft.com/cloud-app-security/managing-alerts)

Als uw organisatie [microsoft defender advanced threat protection](https://docs.microsoft.com/windows/security/threat-protection) gebruikt naast Office 365 en een bestand, IP-adres, URL of domein wordt behandeld als malware op een apparaat, ook al is het veilig, u een aangepaste indicator maken met een actie ['Toestaan' voor uw apparaat.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)

## <a name="undo-a-remediation-action"></a>Een herstelactie ongedaan maken

In de meeste gevallen, als een herstelactie is uitgevoerd op een e-mailbericht, e-mailbijlage of URL, en het item is eigenlijk geen bedreiging, kan uw security operations team ongedaan maken van de herstelactie en stappen ondernemen om te voorkomen dat de false positive van terugkerende. U [Threat Explorer](#undo-an-action-using-threat-explorer) of het tabblad Handelingen gebruiken [voor een onderzoek](#undo-an-action-using-the-actions-tab-for-an-investigation) om een actie ongedaan te maken. 

> [!IMPORTANT]
> Zorg ervoor dat u over de benodigde machtigingen beschikt voordat u probeert de volgende taken uit te voeren.

### <a name="undo-an-action-using-threat-explorer"></a>Een actie ongedaan maken met Threat Explorer

Met Threat Explorer kan uw beveiligingsteam een e-mail vinden die is beïnvloed door een actie en de actie mogelijk ongedaan maken.

|Scenario  |Opties ongedaan maken  |Meer informatie |
|---------|---------|---------|
|Er is een e-mailbericht doorgestuurd naar de map Ongewenste e-mail van een gebruiker     |- Het bericht verplaatsen naar de map Verwijderde items van de gebruiker<br/>- Het bericht verplaatsen naar het Postvak IN van de gebruiker <br/>- Het bericht verwijderen          |[Schadelijke e-mail zoeken en onderzoeken die is geleverd in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered) |
|Een e-mailbericht of een bestand is in quarantaine geplaatst     |- Laat de e-mail of het bestand vrij <br/>- Verwijder de e-mail of het bestand         |[In quarantaine geplaatste berichten en bestanden beheren als beheerder in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/manage-quarantined-messages-and-files) |


### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a>Een actie ongedaan maken met het tabblad Acties voor een onderzoek

In het actiecentrum u herstelacties zien die zijn uitgevoerd en mogelijk de actie ongedaan maken.

1. Ga naar [https://protection.office.com](https://protection.office.com) en meld je aan. Dit brengt u naar het Security & Compliance Center.

2. Ga naar **Threat Management**  >  **Investigations**.

3. Selecteer in de lijst met onderzoeken het pictogram **Openen in nieuw venster** naast de id van een item.

4. Selecteer het tabblad **Handelingen.**

5. Selecteer een item met de status **Voltooid**en zoek naar een koppeling, zoals **Goedgekeurd,** in de kolom **Besluit.** Dit opent een flyout met meer details over de actie.

6. Als u de actie ongedaan wilt maken, selecteert u **Herstel verwijderen**.

## <a name="related-articles"></a>Verwante artikelen

[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)

[Aan de slag met Automated Investigation and Response (AIR) in Office 365](office-365-air.md)