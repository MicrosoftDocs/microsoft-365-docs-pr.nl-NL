---
title: Hoe inhoud wordt geïdentificeerd voor aanbevelingen voor gegevensbeheer
f1.keywords:
- NOCSH
ms.author: brendonb
author: cabailey
manager: laurawi
ms.date: 1/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Het Microsoft 365-beveiligingscentrum en het Microsoft 365-compliancecentrum doen aanbevelingen voor gegevensbeheer op basis van de huidige instellingen van uw organisatie. U kunt met een paar klikken dingen instellen. Met sommige van deze aanbevelingen wordt specifieke inhoud in uw organisatie gedetecteerd en worden aanbevolen stappen gegeven voor het beheren van die inhoud. Zo kunnen met een aanbeveling items worden gedetecteerd die bedrijfskritische inhoud bevatten (zoals clientrechten of NDA-gegevens) en kunt u vervolgens automatisch een bewaarlabel op deze items toepassen om ervoor te zorgen dat deze worden geclassificeerd en bewaard als dat nodig is. In dit onderwerp worden aanbevelingen voor gegevensbeheer beschreven die u mogelijk ziet. Ook wordt beschreven welke inhoud wordt gedetecteerd om elk ervan te activeren.
ms.openlocfilehash: 9a022369fb783a498971c91664fa6532472d8589
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162085"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a>Hoe inhoud wordt geïdentificeerd voor aanbevelingen voor gegevensbeheer

Het Microsoft 365-beveiligingscentrum en het Microsoft 365-compliancecentrum doen aanbevelingen voor gegevensbeheer op basis van de huidige instellingen van uw organisatie. U kunt met een paar klikken dingen instellen. Met sommige van deze aanbevelingen wordt specifieke inhoud in uw organisatie gedetecteerd en worden aanbevolen stappen gegeven voor het beheren van die inhoud. Zo kunnen met een aanbeveling items worden gedetecteerd die bedrijfskritische inhoud bevatten (zoals clientrechten of NDA-gegevens) en kunt u vervolgens automatisch een bewaarlabel op deze items toepassen om ervoor te zorgen dat deze worden geclassificeerd en bewaard als dat nodig is.

In dit onderwerp worden aanbevelingen voor gegevensbeheer beschreven die u mogelijk ziet. Ook wordt beschreven welke inhoud wordt gedetecteerd om elk ervan te activeren.

## <a name="clean-up-voicemail"></a>Voicemail opschonen

Deze aanbeveling wordt weergegeven wanneer e-mailberichten die zijn geïdentificeerd als het berichttype 'voicemail' in de postvakken van gebruikers worden gedetecteerd. Meer informatie over [berichteigenschappen in Exchange](/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).

## <a name="label-attorney-client-privilege-content"></a>Labelen van inhoud met advocaat/cliënt-bevoegdheid 

Deze aanbeveling wordt weergegeven wanneer aan een van de volgende criteria wordt voldaan.

- Er wordt een combinatie van de volgende trefwoorden aangetroffen in de tekst van een e-mailbericht:
    - ACP
    - Advocaat/cliënt-bevoegdheid
    - Advocaat-cliëntbevoegdheid
    - Advocaat-cliëntbevoegdheid

- Er wordt een combinatie van de volgende trefwoorden aangetroffen in SharePoint- of OneDrive-bestanden:
    - ACP
    - Advocaat-cliëntbevoegdheid*
    - AC-bevoegdheid

## <a name="retain-audio-files"></a>Audiobestanden behouden

Deze aanbeveling wordt weergegeven wanneer een van de volgende bestandstypen wordt aangetroffen in SharePoint of OneDrive.

- .MP3
- .WMA
- .WAV
- .RA
- .RAM
- .RM
- .MID
- .OGG
- .AIFF
- .PCM
- .AAC
- .FLAC
- .ALAC

## <a name="retain-cad-files"></a>CAD-bestanden behouden

Deze aanbeveling wordt weergegeven wanneer een van de volgende bestandstypen wordt aangetroffen in SharePoint of OneDrive.

- .3DXML
- .ACIS
- .ARC
- .ASM
- .CAT*
- .CGR
- .DW*
- .DX*
- .EDRW
- .IAM
- .IGES
- .IGS
- .IPT
- .JT
- .MF1
- .NEU
- .PAR
- .PKG
- .PRC
- .PRT
- .PSM
- .PWD
- .SLD*
- .STEP
- .STL
- .STP
- .U3D
- .UNV
- .VRML
- .WRL
- .X_*
- .XAS
- .XMT*
- .XPR

## <a name="retain-image-files"></a>Afbeeldingsbestanden behouden

Deze aanbeveling wordt weergegeven wanneer een van de volgende bestandstypen wordt aangetroffen in SharePoint of OneDrive.

- .JPEG
- .GIF
- .TIF*
- .BMP
- .PNG
- .RAW
- .PSD
- .PSP
- .JPG
- .EXIF
- .PPM
- .PGM
- .PBM
- .PNM
- .WEBP

## <a name="retain-nda-content"></a>NDA-inhoud behouden 

Deze aanbeveling wordt weergegeven wanneer aan een van de volgende criteria wordt voldaan.

- Er wordt een combinatie van de volgende trefwoorden aangetroffen in de tekst van een e-mailbericht:
    - NDA
    - 'Geheimhoudingsovereenkomst'
    - 'Geheimhoudingsovereenkomst'

- Er wordt een combinatie van de volgende trefwoorden aangetroffen in .PDF- of .DOC-bestanden in SharePoint of OneDrive:
    - NDA
    - Geheimhoudingsovereenkomst

## <a name="retain-software-development-files"></a>Bestanden voor softwareontwikkeling behouden

Deze aanbeveling wordt weergegeven wanneer een van de volgende bestandstypen wordt aangetroffen in SharePoint of OneDrive.

- .ASAX
- .ASM
- .ASP*
- .BAT
- .CONFIG
- .CS
- .CSS
- .DISCO
- .HTM*
- .INC
- .JAD
- .JAVA
- .JS*
- .LIB
- .O
- .PHP
- .RC
- .RESX
- .RPT
- .RSS
- .SCPT
- .SRC
- .VB*
- .WSF
- .XCODEPROJ
- .XML
- .XSD
- .XSL*

## <a name="retain-video-files"></a>Videobestanden behouden

Deze aanbeveling wordt weergegeven wanneer een van de volgende bestandstypen wordt aangetroffen in SharePoint of OneDrive.

- .AVCHD
- .AVI
- .FLV
- .MOV
- .MP2V
- .MP4
- .MP4V
- .MPE
- .MPEG
- .MPEG1
- .MPEG2
- .MPEG4
- .MPG
- .MPG2
- .MPG4
- .WMV
- .XMV