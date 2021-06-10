---
title: Apparaten beheren die zijn geregistreerd bij Mobile Device Management in Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Basismobiliteit en beveiliging kunnen u helpen bij het beveiligen en beheren van mobiele apparaten.
ms.openlocfilehash: 4ff1c43343e00b7eac7aa38b2d266f163f79e2a7
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023879"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-microsoft-365"></a>Apparaten beheren die zijn geregistreerd bij Mobile Device Management in Microsoft 365

Met het ingebouwde beheer van mobiele apparaten voor Microsoft 365 kunt u de mobiele apparaten van uw gebruikers beveiligen en beheren, zoals iPhones, iPads, Androids en Windows telefoons. De eerste stap is om u aan te melden Microsoft 365 basismobiliteit en beveiliging in te stellen. Zie Basismobiliteit en beveiliging instellen voor [meer informatie.](set-up.md)

Nadat u deze hebt ingesteld, moeten de personen in uw organisatie hun apparaten registreren voor de service. Zie Uw mobiele apparaat registreren met [basismobiliteit en beveiliging voor meer informatie.](enroll-your-mobile-device.md)Vervolgens kunt u basismobiliteit en beveiliging gebruiken om apparaten in uw organisatie te beheren. U kunt bijvoorbeeld apparaatbeveiligingsbeleid gebruiken om e-mailtoegang of andere services te beperken, apparatenrapporten weer te geven en een apparaat op afstand te wissen. U gaat meestal naar het Beveiligingscentrum & compliancecentrum om deze taken uit te voeren. Zie Microsoft 365 [compliancecentrum voor meer informatie.](../../compliance/microsoft-365-compliance-center.md)

## <a name="device-management-tasks"></a>Apparaatbeheertaken

Ga als volgt te werk om naar het apparaatbeheervenster te gaan:

1. Ga naar het [Microsoft 365 beheercentrum.](../../admin/admin-overview/about-the-admin-center.md)

2. Typ Mobile Device Management in het zoekveld en selecteer **Mobile Device Management** in de lijst met   resultaten.

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Optie voor mobiel apparaatbeheer":::

3. Selecteer  **Laten we aan de slag gaan.**

## <a name="manage-mobile-devices"></a>Mobiele apparaten beheren

Nadat u Basismobiliteit en Beveiliging hebt ingesteld, zijn hier enkele manieren waarop u de mobiele apparaten in uw organisatie kunt beheren.

|**Om dit te doen**|**Doe dit**|
|:----------------|:------------------------------------------------------------------------------|
|Een apparaat wissen |Selecteer in het deelvenster Apparaatbeheer  **** de naam van het apparaat *en* vervolgens Volledig wissen om alle gegevens te verwijderen of Selectief wissen om alleen organisatiegegevens op het apparaat   te  ****   verwijderen. Zie Een mobiel apparaat [wissen in Basismobiliteit en Beveiliging voor meer informatie.](wipe-mobile-device.md)|
|Niet-ondersteunde apparaten blokkeren om toegang te krijgen tot Exchange e-mail via Exchange ActiveSync |Selecteer blokkeren in het deelvenster  **Apparaatbeheer.** |
|Apparaatbeleid instellen, zoals wachtwoordvereisten en beveiligingsinstellingen |Selecteer in het deelvenster Apparaatbeheer de optie **Apparaatbeveiligingsbeleid**   >  **Toevoegen +**. Zie Apparaatbeveiligingsbeleid maken [in Basismobiliteit en Beveiliging voor meer informatie.](create-device-security-policies.md)|
|Lijst met geblokkeerde apparaten weergeven  |Selecteer in het deelvenster Apparaatbeheer onder  **Selecteer een weergave** de optie     **Geblokkeerd.** |
|Niet-compatibele of niet-ondersteunde apparaten deblokkeren voor een gebruiker of groep gebruikers  |Kies een van de volgende opties om de blokkering van apparaten te deblokkeren:<br/>- Verwijder de gebruiker of gebruikers uit de beveiligingsgroep waar het beleid op is toegepast. Ga naar Microsoft 365 beheercentrum > **Groepen** en selecteer vervolgens groepsnaam. Selecteer **Leden en beheerders bewerken.**<br/>- Verwijder de beveiligingsgroep waar de gebruikers lid van zijn uit het apparaatbeleid. Ga naar Beveiligings- & compliancecentrum > **beveiligingsbeleid**   >  **Apparaatbeveiligingsbeleid.** Selecteer apparaatbeleidsnaam en selecteer **vervolgens Implementatie**  >  **bewerken.**<br/>- Blokkering opheffen van alle niet-compatibele apparaten voor een apparaatbeleid. Ga naar Beveiligings- & compliancecentrum > **beveiligingsbeleid**   >  **Apparaatbeveiligingsbeleid.** Selecteer apparaatbeleidsnaam en selecteer **vervolgens**  >  **Access-vereisten bewerken.** Selecteer  **Toegangs- en rapportovertreding toestaan.**<br/>- Als u een niet-compatibel of niet-ondersteund apparaat wilt deblokkeren voor een gebruiker of een groep gebruikers, gaat u naar Beveiligings- & Compliancecentrum > **Beveiligingsbeleid**   >  **Apparaatbeheer** Apparaattoegangsinstellingen   >  **beheren.** Voeg een beveiligingsgroep toe met de leden die u wilt uitsluiten van geblokkeerde toegang tot Microsoft 365. Zie Een beveiligingsgroep maken, bewerken of verwijderen in het Microsoft 365 [voor meer informatie.](../../admin/email/create-edit-or-delete-a-security-group.md)|
|Gebruikers verwijderen zodat hun apparaten niet meer worden beheerd door Basismobiliteit en Beveiliging |Als u de gebruiker wilt verwijderen, bewerkt u de beveiligingsgroep met apparaatbeheerbeleid voor Basismobiliteit en Beveiliging. Zie Een beveiligingsgroep maken, bewerken of verwijderen in het Microsoft 365  [voor meer informatie.](../../admin/email/create-edit-or-delete-a-security-group.md)<br/>Zie Basismobiliteit en beveiliging uitschakelen als u basismobiliteit en beveiliging wilt verwijderen Microsoft 365 [gebruikers.](turn-off.md)|

Live (v14)