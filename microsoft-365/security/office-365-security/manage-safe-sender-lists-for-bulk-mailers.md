---
title: Veilige afzenderlijsten voor bulkmailers beheren
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
ms.collection:
- M365-security-compliance
description: 'Als u veilige afzenderlijsten wilt gebruiken, moet u weten dat Exchange Online Protection (EOP) en Outlook de verwerking anders verwerken. De service respecteert veilige afzenders en domeinen door het RFC 5321.MailFrom-adres en de RFC 5322.From-adres te inspecteren, terwijl Outlook de RFC 5322 toevoegt.Van adres naar de lijst met veilige afzenders van een gebruiker. (Opmerking: De service inspecteert zowel het 5321.MailFrom-adres als 5322.Van adres voor geblokkeerde afzenders en domeinen.)'
ms.openlocfilehash: aaede7cab2e640603c20804f4015e19f61b6c2f3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42807329"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a>Veilige afzenderlijsten voor bulkmailers beheren

Als u veilige afzenderlijsten wilt gebruiken, moet u weten dat Exchange Online Protection (EOP) en Outlook de verwerking anders verwerken. De Office 365-service respecteert veilige afzenders `RFC 5321.MailFrom` en `RFC 5322.From` domeinen door het `RFC 5322.From` adres en het adres te inspecteren, terwijl Outlook het adres toevoegt aan de lijst met veilige afzenders van een gebruiker. (Opmerking: De service inspecteert zowel het adres als het `5321.MailFrom` `5322.From` adres voor geblokkeerde afzenders en domeinen.)

Het `SMTP MAIL FROM` adres, ook `RFC 5321.MailFrom address`wel bekend als het , is het e-mailadres dat wordt gebruikt om SPF-controles uit te voeren, en als de e-mail niet kan worden bezorgd, het pad waarop het teruggestuurde bericht wordt bezorgd. Het is dit e-mailadres dat `Return-Path` standaard in de berichtenkoppen wordt geplaatst, hoewel het mogelijk `Return-Path` is voor de afzender om een ander adres aan te wijzen.

Het `From:` adres in de berichtkoppen, `RFC 5322.From` ook wel het adres genoemd, is het e-mailadres dat wordt weergegeven in de e-mailclient zoals Outlook.

Veel van de `5321.MailFrom` tijd, de en `5322.From` adressen zijn hetzelfde. Dit is typisch voor persoonlijke communicatie. Wanneer e-mail echter namens iemand anders wordt verzonden, zijn de adressen vaak verschillend. Dit gebeurt meestal het vaakst voor bulk e-mailberichten.

Stel bijvoorbeeld dat Blue Yonder Airlines Margie's Travel heeft ingehuurd om haar e-mailreclame te versturen. U ontvangt dan een bericht in uw postvak in van afzender blueyonder@news.blueyonderairlines.com. In dit voorbeeld:

- Het `5321.MailFrom` adres is blueyonder.airlines@margiestravel.com.

- Het `5322.From` adres is blueyonder@news.blueyonderairlines.com, dat is wat u ziet in Outlook.

Om te voorkomen dat dit bericht wordt gefilterd, u het:

- **Als gebruiker**: `RFC 5322.From` Voeg het adres toe als veilige afzender in Outlook.

- **Als beheerder**: Stel een [e-mailstroomregel](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365) in (ook wel een transportregel genoemd).
