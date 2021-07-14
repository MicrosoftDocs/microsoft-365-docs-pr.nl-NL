---
title: Groepen vergelijken
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 758759ad-63ee-4ea9-90a3-39f941897b7d
description: Leden van een Microsoft 365-groep ontvangen een groeps e-mail en een gedeelde werkruimte voor gesprekken, bestanden, agenda-items, Stream en Planner.
ms.openlocfilehash: 12da954beb4d019b7652ef4df2e18cb30ff542ed
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393257"
---
# <a name="compare-groups"></a>Groepen vergelijken

In de sectie **Groepen** van het Microsoft 365-beheercentrum kunt u de volgende typen groepen maken en beheren: 

- **Microsoft 365-groepen** (voorheen Office 365-groepen) worden gebruikt voor samenwerking tussen gebruikers, zowel binnen als buiten uw bedrijf.
- **Distributiegroepen** worden gebruikt voor het verzenden van e-mailmeldingen aan een groep personen.
- **Beveiligingsgroepen** worden gebruikt voor het verlenen van toegang tot SharePoint-bronnen zoals websites.
- **Beveiligingsgroepen met e-mail** worden gebruikt om toegang te verlenen tot SharePoint-bronnen en het verzenden van meldingen aan die gebruikers.
- **Gedeelde postvakken** worden gebruikt als meerdere mensen toegang tot hetzelfde postvak nodig hebben, zoals bedrijfsgegevens of ondersteuningsadressen.

## <a name="microsoft-365-groups"></a>Microsoft 365-groepen

Microsoft 365-groepen worden gebruikt voor samenwerking tussen gebruikers, zowel binnen als buiten uw bedrijf. Met elke Microsoft 365-groep ontvangen leden een groeps-e-mail en een gedeelde werkruimte voor gesprekken, bestanden, agenda-items, Stream en Planner.

U kunt personen buiten uw organisatie toevoegen aan een groep zolang dit is [ingeschakeld door de beheerder](manage-guest-access-in-groups.md). U kunt ook externe afzenders toestemming geven e-mail te verzenden naar het groeps-e-mailadres.

Microsoft 365-groepen kunnen worden [geconfigureerd voor dynamisch lidmaatschap van Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type), zodat groepsleden automatisch kunnen worden toegevoegd of verwijderd op basis van gebruikerskenmerken zoals afdeling, locatie, titel, enzovoort.

Microsoft 365-groepen kunnen worden geopend via mobiele apps zoals Outlook voor iOS en Outlook voor Android.

Groepsleden kunnen verzenden als of verzenden namens het e-mailadres van de groep als dit is [ingeschakeld door de beheerder](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md).

Microsoft 365-groepen bieden geen ondersteuning voor nesting met andere Microsoft 365-groepen of met distributie- of beveiligingsgroepen.

## <a name="distribution-groups"></a>Distributiegroepen

[Distributiegroepen](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups) worden gebruikt voor het verzenden van meldingen aan een groep personen. Deze groepen kunnen externe e-mail ontvangen als dit is ingeschakeld door de beheerder.

Distributiegroepen zijn het meest geschikt voor situaties waarin u informatie wilt publiceren aan een bepaalde groep personen, zoals 'Medewerkers in gebouw A' of 'Iedereen bij Contoso'.

Distributiegroepen kunnen worden [bijgewerkt naar Microsoft 365-groepen](../manage/upgrade-distribution-lists.md).

Distributiegroepen kunnen worden toegevoegd aan een team in Microsoft Teams.

Microsoft 365-groepen kunnen geen lid zijn van distributiegroepen.

## <a name="security-groups"></a>Beveiligingsgroepen

[Beveiligingsgroepen](../email/create-edit-or-delete-a-security-group.md) worden gebruikt voor het verlenen van toegang tot Microsoft 365-bronnen, zoals SharePoint. Deze groepen kunnen het beheer vereenvoudigen, omdat u alleen de groep hoeft te beheren in plaats van afzonderlijke gebruikers aan afzonderlijke bronnen toe te voegen.

Beveiligingsgroepen kunnen gebruikers en apparaten bevatten. Het maken van een beveiligingsgroep voor apparaten kan worden gebruikt met services voor het beheer van mobiele apparaten, zoals Intune.

Beveiligingsgroepen kunnen worden [geconfigureerd voor dynamisch lidmaatschap van Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type), zodat groepsleden of apparaten automatisch kunnen worden toegevoegd of verwijderd op basis van gebruikerskenmerken zoals afdeling, locatie of titel of apparaatkenmerken zoals de versie van het besturingssystem.

Beveiligingsgroepen kunnen worden toegevoegd aan een team.

Microsoft 365-groepen kunnen geen lid zijn van beveiligingsgroepen.

## <a name="mail-enabled-security-groups"></a>Beveiligingsgroepen met e-mail

Beveiligingsgroepen met e-mail zijn hetzelfde als gewone beveiligingsgroepen, behalve dat ze niet dynamisch kunnen worden beheerd via Azure Active Directory en geen apparaten kunnen bevatten.

Deze groepen hebben de mogelijkheid e-mail te verzenden aan alle groepsleden.

Beveiligingsgroepen met e-mail kunnen worden toegevoegd aan een team.

## <a name="shared-mailboxes"></a>Gedeelde postvakken

[Gedeelde postvakken](../email/create-a-shared-mailbox.md) worden gebruikt als meerdere mensen toegang tot hetzelfde postvak nodig hebben, zoals bedrijfsgegevens, ondersteuningsadressen, recepties of andere functies die gedeeld worden door meerdere mensen.

Gedeelde postvakken kunnen externe mail ontvangen als de beheerder dit heeft ingeschakeld.

Gedeelde postvakken kunnen een agenda bevatten die kan worden gebruikt om samen te werken.

Gebruikers met machtigingen voor het groepspostvak kunnen verzenden als of namens het groeps-e-mailadres als de beheerder die gebruiker daarvoor heeft gemachtigd. Dit is bijzonder handig voor helpdesk- en ondersteuningspostvakken, omdat gebruikers e-mails kunnen verzenden vanuit 'Contoso-ondersteuning' of 'Receptie gebouw A'.

Het is niet mogelijk een gedeeld postvak te migreren naar een Microsoft 365-groep. 

## <a name="related-content"></a>Verwante inhoud

[Meer informatie over Microsoft 365-groepen](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Distributielijsten upgraden naar Microsoft 365-groepen in Outlook](/microsoft-365/admin/manage/upgrade-distribution-lists)

[Waarom u uw distributielijsten moet upgraden naar groepen in Outlook](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)
