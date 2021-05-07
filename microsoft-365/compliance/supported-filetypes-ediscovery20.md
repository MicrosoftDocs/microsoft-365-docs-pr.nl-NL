---
title: Ondersteunde bestandstypen in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Een lijst met ondersteunde bestandstypen in Microsoft 365 Advanced eDiscovery, inclusief afbeeldingsbestandstypen die worden ondersteund door de OCR-functionaliteit in Advanced eDiscovery.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 719a0474d45825114cf4ea3fbd19082bb8df7622
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/06/2021
ms.locfileid: "52162574"
---
# <a name="supported-file-types-in-advanced-ediscovery"></a>Ondersteunde bestandstypen in Advanced eDiscovery

Advanced eDiscovery ondersteunt veel bestandstypen op veel verschillende niveaus. De typen ondersteuningsbestanden worden beschreven in de volgende tabellen in dit artikel. Deze lijst is nog niet afgerond en we voegen nieuwe bestandstypen toe terwijl we doorgaan met het valideren. Deze tabellen geven aan of een bestandstype wordt ondersteund voor tekstextractie (en Optische tekenherkenning of OCR-tekstextractie voor afbeeldingsbestanden), dat kan worden bekeken in de oorspronkelijke viewer en ook wordt ondersteund in de viewer van aantekeningen in Advanced eDiscovery.

## <a name="archive--container"></a>Archiveren / Container

| Mime-type | Bestandsidentificatie | Metagegevensextractie | Containerextractie | Mogelijke extensies |
|:---- |:---- |:---- |:---- |:---- |
|toepassing/x-7z-gecomprimeerd | Ja | Ja | Ja | .7z |
|toepassing/x-rar-gecomprimeerd | Ja | Ja | Ja | .rar |
|toepassing/x-tar | Ja | Ja | Ja | .tar |
|toepassing/zip | Ja | Ja | Ja | .zip |
||||||||

## <a name="audio--video"></a>Audio /video

| Mime-type | Bestandsidentificatie | Metagegevensextractie | Tekstextractie | Native viewer | Aantekeningen maken met viewer | Mogelijke extensies |
|:------| :------| :------| :------| :------| :------| :------|
| toepassing/mp4 | Ja | Ja | Nee | Ja | Nee | .f4v; .m4a; .m4v; .mp4; .mp4v; .mpeg; .mpeg4 |
|audio/mpeg | Ja | Ja | Nee | Ja | Nee | .mpeg |
|video/3gpp | Ja | Ja | Nee | Ja | Nee | .3gp |
|video/3gpp2 | Ja | Ja | Nee | Ja | Nee | .3g2; .3gp2 |
|video/quicktime | Ja | Ja | Nee | Ja | Nee | .moov; .mov; .qt |
|video/x-m4v | Ja | Ja | Nee | Ja | Nee | .m4v |
||||||||

## <a name="database"></a>Database

| Mime-type | Bestandsidentificatie | Metagegevensextractie | Tekstextractie | Native viewer | Aantekeningen maken met viewer | Mogelijke extensies |
|:------| :------| :------| :------| :------| :------| :------|
|application/x-msaccess | Ja | Ja | Ja | Nee | Nee | .mdb |
||||||||

## <a name="email"></a>E-mail

|Mime-type |Bestandsidentificatie |Metagegevensextractie |Tekstextractie |Native viewer |Aantekeningen maken met viewer | Mogelijke extensies |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-outlook | Ja | Ja | Ja | Ja | Ja | .msg |
|bericht/rfc822 | Ja | Ja | Ja | Ja | Ja | .eml |
|tekst/vcard-contact | Ja | Ja | Ja | Ja | Ja | .vcf |
||||||||

## <a name="email-container"></a>E-mailcontainer

| Mime-type | Bestandsidentificatie | Metagegevensextractie | Containerextractie | Mogelijke extensies |
|:------| :------| :------| :------| :------|
|toepassing/mbox | Ja | Ja | Ja | .mbox |
|application/vnd.ms-outlook-pst | Ja | Ja | Ja | .pst |
||||||||

## <a name="html"></a>HTML

| Mime-type | Bestandsidentificatie | Metagegevensextractie | Tekstextractie | Native viewer | Aantekeningen maken met viewer | Mogelijke extensies |
|:------| :------| :------| :------| :------| :------| :------|
|application/xhtml+xml | Ja | Ja | Ja | Ja | Ja | .xhtml |
|toepassing/xml | Ja | Ja | Ja | Ja | Ja | .xml |
|tekst/html | Ja | Ja | Ja | Ja | Ja | .htm; .html; .shtml |
||||||||

## <a name="image"></a>Afbeelding

|Mime-type |Bestandsidentificatie |Metagegevensextractie |OCR-tekstextractie |Native viewer |Aantekeningen maken met viewer |Mogelijke extensies |
|:------| :------| :------| :------| :------| :------| :------|
|afbeelding/bmp | Ja | Ja | Ja | Ja | Ja | .bmp |
|image/emf | Ja | Ja | Ja | Ja | Ja | .emf |
|afbeelding/gif | Ja | Ja | Ja | Ja | Ja | .gif |
|image/jpeg | Ja | Ja | Ja | Ja | Ja | .jpeg; .jpg |
|afbeelding/png | Ja | Ja | Ja | Ja | Ja | .png |
|image/svg+xml | Ja | Ja | Ja | Ja | Nee | .svg |
|image/tiff | Ja | Ja | Ja | Ja | Ja | .tif |
|image/vnd.dwg | Ja | Ja | Ja | Ja | Ja | .dwg; .dxf |
|image/wmf | Ja | Ja | Ja | Ja | Ja | .wmf |
||||||||

## <a name="microsoft-excel"></a>Microsoft Excel

| Mime-type | Bestandsidentificatie | Metagegevensextractie | Tekstextractie | Native viewer | Aantekeningen maken met viewer | Mogelijke extensies |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-excel | Ja | Ja | Ja | Ja | Ja | .dat; .xls |
|application/vnd.ms-excel.sheet.binary.macroenabled.12 | Ja | Ja | Ja | Ja | Nee | .xlsb |
|application/vnd.ms-excel.sheet.macroenabled.12 | Ja | Ja | Ja | Ja | Ja | .xlsm |
|application/vnd.ms-excel.template.macroenabled.12 | Ja | Ja | Ja | Nee | Nee | .xltm |
|application/vnd.openxmlformats-officedocument.spreadsheetml.sheet | Ja | Ja | Ja | Ja | Ja | .xlsx |
|application/vnd.openxmlformats-officedocument.spreadsheetml.template | Ja | Ja | Ja | Ja | Ja | .xltx |
||||||||

## <a name="microsoft-onenote"></a>Microsoft OneNote

| Mime-type | Bestandsidentificatie | Metagegevensextractie | Tekstextractie | Native viewer | Aantekeningen maken met viewer | Mogelijke extensies |
|:------| :------| :------| :------| :------| :------| :------|
|toepassing/onenote | Ja | Ja | Ja | Nee | Nee | .one |
||||||||

## <a name="microsoft-powerpoint"></a>Microsoft PowerPoint

| Mime-type | Bestandsidentificatie | Metagegevensextractie | Tekstextractie | Native viewer | Aantekeningen maken met viewer | Mogelijke extensies |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-powerpoint | Ja | Ja | Ja | Ja | Ja | .pot; .pps; .ppt |
|application/vnd.openxmlformats-officedocument.presentationml.presentation | Ja | Ja | Ja | Ja | Ja | .pptx |
|application/vnd.openxmlformats-officedocument.presentationml.slideshow | Ja | Ja | Ja | Ja | Ja | .ppsx |
|application/vnd.openxmlformats-officedocument.presentationml.template | Ja | Ja | Ja | Ja | Ja | .potx |
||||||||

## <a name="microsoft-project"></a>Microsoft Project

| Mime-type | Bestandsidentificatie | Metagegevensextractie | Tekstextractie | Native viewer | Aantekeningen maken met viewer | Mogelijke extensies |
|:------| :------| :------| :------| :------| :------| :------|
|toepassing/vnd.ms-project | Ja | Ja | Ja | Nee | Ja | .mpp |
||||||||

## <a name="microsoft-publisher"></a>Microsoft Publisher

|Mime-type | Bestandsidentificatie | Metagegevensextractie | Tekstextractie | Native viewer | Aantekeningen maken met viewer | Mogelijke extensies |
|:------| :------| :------| :------| :------| :------| :------|
|toepassing/x-mspublisher | Ja | Ja | Ja | Ja | Ja | .pub |
||||||||

## <a name="microsoft-visio"></a>Microsoft Visio

| Mime-type | Bestandsidentificatie | Metagegevensextractie | Tekstextractie | Native viewer | Aantekeningen maken met viewer | Mogelijke extensies |
|:------| :------| :------| :------| :------| :------| :------|
|toepassing/vnd.ms-visio.drawing | Ja | Ja | Ja | Ja | Nee |  |
|toepassing/vnd.visio | Ja | Ja | Ja | Ja | Ja | .vsd |
||||||||

## <a name="microsoft-word"></a>Microsoft Word

| Mime-type | Bestandsidentificatie | Metagegevensextractie | Tekstextractie | Native viewer | Aantekeningen maken met viewer | Mogelijke extensies |
|:------| :------| :------| :------| :------| :------| :------|
|toepassing/msword | Ja | Ja | Ja | Ja | Ja | .dat; .doc |
| toepassing/rtf | Ja | Ja | Ja | Ja | Ja | .doc; .rtf |
|application/vnd.ms-word.document.macroenabled.12 | Ja | Ja | Ja | Ja | Ja | .docm |
|application/vnd.ms-word.template.macroenabled.12 | Ja | Ja | Ja | Ja | Ja | .dotm |
|toepassing/vnd.openxmlformats-officedocument.wordprocessingml.document | Ja | Ja | Ja | Ja | Ja | .docx |
|application/vnd.openxmlformats-officedocument.wordprocessingml.template | Ja | Ja | Ja | Ja | Ja | .dotx |
||||||||

## <a name="microsoft-works"></a>Microsoft Works

| Mime-type | Bestandsidentificatie | Metagegevensextractie | Tekstextractie | Native viewer | Aantekeningen maken met viewer | Mogelijke extensies |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-works-ss | Ja | Ja | Nee | Nee | Nee | .wps |
|application/vnd.ms-works-wp | Ja | Ja | Nee | Nee | Nee | .wps |
||||||||

## <a name="open-document-format"></a>Documentopmaak openen

| Mime-type | Bestandsidentificatie | Metagegevensextractie | Tekstextractie | Native viewer | Aantekeningen maken met viewer | Mogelijke extensies |
|:------| :------| :------| :------| :------| :------| :------|
|toepassing/vnd.oasis.opendocument.text | Ja | Ja | Ja | Ja | Ja | .odt |
||||||||

## <a name="other"></a>Overige

| Mime-type | Bestandsidentificatie | Metagegevensextractie | Tekstextractie | Native viewer | Aantekeningen maken met viewer | Mogelijke extensies |
|:------| :------| :------| :------| :------| :------| :------|
|toepassing/json | Ja | Ja | Ja | Ja | Ja | n/a |
|toepassing/vnd.ms-graph | Ja | Ja | Nee | Nee | Nee |  |
|toepassing/winhlp | Ja | Ja | Nee | Nee | Nee | .hlp |
|application/x-tnef | Ja | Ja | Nee | Nee | Nee |  |
||||||||

## <a name="plain-text"></a>Tekst zonder tekst

| Mime-type | Bestandsidentificatie | Metagegevensextractie | Tekstextractie | Native viewer | Aantekeningen maken met viewer | Mogelijke extensies |
|:------| :------| :------| :------| :------| :------| :------|
|tekst/csv | Ja | Ja | Ja | Ja | Ja | .csv |
|tekst/plain | Ja | Ja | Ja | Ja | Ja | .con; .css; .csv; .dat; .pl; .txt |
||||||||

## <a name="portable-document-format"></a>Portable Document Format

| Mime-type | Bestandsidentificatie | Metagegevensextractie | Tekstextractie | Native viewer | Aantekeningen maken met viewer | Mogelijke extensies |
|:------| :------| :------| :------| :------| :------| :------|
|toepassing/pdf | Ja | Ja | Ja | Ja | Ja | .pdf |
||||||||

## <a name="word-perfect"></a>Word Perfect

| Mime-type | Bestandsidentificatie | Metagegevensextractie | Tekstextractie | Native viewer | Aantekeningen maken met viewer | Mogelijke extensies |
|:------| :------| :------| :------| :------| :------| :------|
|toepassing/vnd.wordperfect; versie=5.0 | Ja | Ja | Ja | Nee | Nee | .wpd |
|toepassing/vnd.wordperfect; versie=5.1 | Ja | Ja | Ja | Nee | Nee | .wpd |
|toepassing/vnd.wordperfect; versie=6.x | Ja | Ja | Ja | Nee | Nee | .wpd |
||||||||

## <a name="word-pro"></a>Word Pro

| Mime-type | Bestandsidentificatie | Metagegevensextractie | Tekstextractie | Native viewer | Aantekeningen maken met viewer | Mogelijke extensies |
|:------| :------| :------| :------| :------| :------| :------|
|toepassing/vnd.lotus-wordpro | Ja | Ja | Nee | Nee | Nee | .lwp |
||||||||
