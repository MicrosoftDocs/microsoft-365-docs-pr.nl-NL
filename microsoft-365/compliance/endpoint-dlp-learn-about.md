---
title: Meer informatie over Microsoft 365 Eindpunt-DLP
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 'Microsoft 365 Preventie van gegevensverlies voor eindpunten breidt de controle van bestandsactiviteiten en beschermende maatregelen uit voor deze bestanden naar eindpunten. Bestanden worden zichtbaar gemaakt in de compliance-oplossingen van Microsoft 365 '
ms.openlocfilehash: 39474f54440ba33c8d7140981c1495a5c46bf0fc
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226681"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a>Meer informatie over Microsoft 365 Eindpunt-DLP

U kunt preventie van gegevensverlies van Microsoft 365 (DLP) gebruiken om te controleren welke acties worden ondernomen op items die u vertrouwelijk vindt en om te voorkomen dat deze items per ongeluk worden gedeeld. Zie voor meer informatie over DLP [Meer informatie over preventie van gegevensverlies](dlp-learn-about-dlp.md).

**Preventie van gegevensverlies voor eindpunten)** (Eindpunt-DLP) is een uitbreiding voor de activiteitencontrole en beveiligingsmogelijkheden van DLP voor vertrouwelijke items op Windows 10-apparaten. Zodra apparaten zijn geregistreerd bij de Microsoft 365-complianceoplossingen, wordt de informatie over wat gebruikers met gevoelige items doen, zichtbaar in [Activiteitenverkenner](data-classification-activity-explorer.md) en kunt u beschermende maatregelen voor deze items afdwingen via [DLP-beleid](create-test-tune-dlp-policy.md).

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a>EIndpuntactiviteiten die u kunt controleren en waarvoor u maatregelen kunt nemen

Met Microsoft Endpoint DLP kunt u de typen activiteiten die gebruikers uitvoeren op vertrouwelijke items, controleren en beheren op apparaten met Windows 10.

|Activiteit |Omschrijving  | Controleerbaar/beperkbaar|
|---------|---------|---------|
|Naar cloudservice uploaden of openen via niet-toegestane browsers    | Hiermee wordt gedetecteerd wanneer een gebruiker probeert om een item te uploaden naar een beperkt servicedomein of een item via een browser probeert te openen.  Als ze een browser gebruiken die in DLP is opgenomen als een niet-toegestaan browser, wordt de uploadactiviteit geblokkeerd en wordt de gebruiker omgeleid naar Edge Chromium. Edge Chromium staat vervolgens het uploaden of de toegang toe of blokkeert het op basis van de configuratie van het DLP-beleid.         |controleerbaar en beperkbaar|
|kopiëren naar andere app    |Hiermee wordt gedetecteerd wanneer een gebruiker informatie uit een beveiligd item probeert te kopiëren en vervolgens te plakken in een andere app, of in een ander proces of item. Het kopiëren en plakken van gegevens binnen dezelfde app, hetzelfde proces of item wordt niet gedetecteerd door deze activiteit.         | controleerbaar en beperkbaar|
|kopiëren naar verwisselbare USB-media |Detecteert wanneer een gebruiker een item of gegevens probeert te kopiëren naar een verwisselbaar medium of USB-apparaat.         | controleerbaar en beperkbaar|
|kopiëren naar een netwerkshare    |Detecteert wanneer een gebruiker een item probeert te kopiëren naar een netwerkshare of een netwerkstation         |controleerbaar en beperkbaar|
|een document afdrukken    |Detecteert wanneer een gebruiker een beveiligd item probeert af te drukken op een lokale printer of netwerkprinter.| controleerbaar en beperkbaar         |
|kopiëren naar een externe sessie|Detecteert wanneer een gebruiker een item naar een sessie op het extern bureaublad probeert te kopiëren |  controleerbaar en beperkbaar|
|kopiëren naar een Bluetooth-apparaat|Detecteert wanneer een gebruiker een item naar een niet-toegestane Bluetooth-app probeert te kopiëren (zoals gedefinieerd in de lijst met niet-toegestane Bluetooth-apps in de instellingen voor DLP Endpoint).| controleerbaar en beperkbaar|
|een item aanmaken|Detecteert wanneer een gebruiker een item maakt| controleerbaar|
|een item hernoemen|Detecteert wanneer een gebruiker de naam van een item wijzigt| controleerbaar|

## <a name="monitored-files"></a>Bewaakte bestanden

Endpoint DLP ondersteunt de controle van deze bestandstypen:

- Word-bestanden
- PowerPoint-bestanden
- Excel-bestanden
- PDF-bestanden
- .csv-bestand
- .tsv-bestanden
- .txt-bestanden
- .rtf-bestanden
- .c-bestanden
- .class-bestanden
- .cpp-bestanden
- .cs-bestanden
- .h-bestanden
- .java-bestanden

Standaard worden de activiteiten voor deze bestandstypen door Endpoint DLP gecontroleerd, zelfs als er geen overeenkomstig beleid is. Als u enkel de gegevens wilt controleren waarvoor overeenkomstig beleid bestaat, kunt u **Bestandsactiviteit altijd controleren voor apparaten** uitschakelen in de globale instellingen voor Endpoint DLP. Als deze instelling is ingeschakeld, worden activiteiten met alle Word-, PowerPoint-, Excel-, PDF- en CSV-bestanden altijd gecontroleerd, zelfs als het apparaat niet aan een beleid is onderworpen.

Endpoint DLP bewaakt activiteit op basis van MIME-type, zodat er zelfs activiteiten worden vastgelegd als de bestandsextensie wordt gewijzigd.

## <a name="whats-different-in-endpoint-dlp"></a>Wat is er nieuw in Endpoint DLP

Er zijn enkele extra concepten waar u rekening mee moet houden voordat u Endpoint DLP in gebruik gaat nemen.

### <a name="enabling-device-management"></a>Apparaatbeheer inschakelen

Apparaatbeheer is de functie waarmee telemetrieverzamelingen van apparaten kunnen worden gebruikt en die beschikbaar wordt in nalevingsoplossingen van Microsoft 365, zoals Endpoint DLP en [Risicobeheer voor Insiders](insider-risk-management.md). U moet alle apparaten die u wilt gebruiken als locaties in het DLP-beleid onboarden.

> [!div class="mx-imgBorder"]
> ![apparaatbeheer inschakelen](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

Onboarding en offboarding worden verwerkt via scripts die u downloadt in het Apparaatbeheercentrum. Het centrum heeft aangepaste scripts voor elk van deze implementatiemethoden:

- lokaal script (maximaal 10 computers)
- Groepsbeleid
- System Center Configuration Manager (versie 1610 of later)
- Mobile Device Management/Microsoft Intune
- Scripts voor VDI-onboarding voor niet-permanente computers

> [!div class="mx-imgBorder"]
> ![pagina voor onboarding van apparaten](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)

 Gebruik de procedures in [Aan de slag met Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) om apparaten te onboarden.

Als u apparaten heeft geïmplementeerd via [Microsoft Defender for Endpoint](/windows/security/threat-protection/), dan worden deze apparaten automatisch weergegeven in de lijst met apparaten.

> [!div class="mx-imgBorder"]
> ![lijst met beheerde apparaten](../media/endpoint-dlp-learn-about-2-device-list.png)

### <a name="viewing-endpoint-dlp-data"></a>Endpoint DLP-gegevens weergeven

U kunt waarschuwingen weergeven die zijn gerelateerd aan DLP-beleid afgedwongen op eindpuntapparaten. Ga daarvoor naar het [Dashboard DLP-waarschuwingenbeheer](dlp-configure-view-alerts-policies.md).

> [!div class="mx-imgBorder"]
> ![Waarschuwingsinformatie](../media/Alert-info-1.png)

U kunt ook details van de bijbehorende gebeurtenis met uitgebreide metagegevens in hetzelfde dashboard bekijken

> [!div class="mx-imgBorder"]
> ![gebeurtenisinformatie](../media/Event-info-1.png)

Zodra een apparaat is geïmplementeerd, wordt informatie over gecontroleerde activiteiten in Activity Explorer overgezet voordat u DLP-beleidsregels met apparaten als locatie configureert en implementeert.

> [!div class="mx-imgBorder"]
> ![endpoint dlp-gebeurtenissen in activity Explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)

Endpoint DLP verzamelt uitgebreide informatie over gecontroleerde activiteiten.

Als een bestand bijvoorbeeld is gekopieerd naar een verwisselbaar USB-medium, ziet u deze kenmerken in de activiteitsdetails:

- activiteitstype
- client-IP
- pad naar doelbestand
- timestamp gebeurtenis
- bestandsnaam
- gebruiker
- bestandsextensie
- bestandsgrootte
- type vertrouwelijke informatie (indien van toepassing)
- sha1-waarde
- sha256-waarde
- vorige bestandsnaam
- locatie
- bovenliggend
- bestandspad
- type bronlocatie
- platform
- apparaatnaam
- type doellocatie
- toepassing die de kopie heeft uitgevoerd
- Apparaat-id voor Microsoft Defender voor Endpoint
- fabrikant van verwisselbaar media-apparaat
- model van verwisselbaar media-apparaat
- serienummer van verwisselbaar media-apparaat

> [!div class="mx-imgBorder"]
> ![kopiëren naar usb-activiteitskenmerken](../media/endpoint-dlp-learn-about-5-activity-attributes.png)

## <a name="next-steps"></a>Volgende stappen

Nu u meer weet over Endpoint DLP, gaat u als volgt te werk:

1. [Aan de slag met Microsoft Eindpunt-DLP](endpoint-dlp-getting-started.md)
2. [Eindpunt-DLP gebruiken](endpoint-dlp-using.md)

## <a name="see-also"></a>Zie ook

- [Aan de slag met Microsoft Eindpunt-DLP](endpoint-dlp-getting-started.md)
- [Eindpunt-DLP gebruiken](endpoint-dlp-using.md)
- [Meer informatie over preventie van gegevensverlies](dlp-learn-about-dlp.md)
- [Een DLP-beleid maken, testen en afstemmen](create-test-tune-dlp-policy.md)
- [Aan de slag met Activity Explorer](data-classification-activity-explorer.md)
- [Microsoft Defender voor Eindpunt](/windows/security/threat-protection/)
- [Insider Risk-beheer](insider-risk-management.md)
