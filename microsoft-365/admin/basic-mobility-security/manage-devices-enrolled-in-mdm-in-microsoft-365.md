---
title: Apparaten beheren die zijn geregistreerd voor Mobile Device Management in Microsoft 365
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
description: Met basis mobiliteit en beveiliging kunt u mobiele apparaten beschermen en beheren.
ms.openlocfilehash: 36ea0d12becca2e97a56aceea107fa1f5bf6ded4
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336823"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-microsoft-365"></a>Apparaten beheren die zijn geregistreerd voor Mobile Device Management in Microsoft 365

Met behulp van de ingebouwde Mobile Device Management voor Microsoft 365 kunt u de mobiele apparaten van uw gebruikers, zoals iPhones, iPads, Android-telefoons en Windows Phones beschermen en beheren. De eerste stap is om u aan te melden bij Microsoft 365 en basis mobiliteit en beveiliging in te stellen. Zie [eenvoudige mobiliteit en beveiliging instellen](set-up-basic-mobility-and-security.md)voor meer informatie.

Nadat u deze hebt ingesteld, moeten de personen in uw organisatie hun apparaten in de service registreren. Zie voor meer informatie [uw mobiele apparaat registreren met behulp van eenvoudige mobiliteit en beveiliging](enroll-your-mobile-device-using-basic-mobility-and-security.md).Vervolgens kunt u de basis mobiliteit en beveiliging gebruiken om apparaten in uw organisatie te beheren. U kunt bijvoorbeeld beveiligingsbeleid voor apparaten gebruiken om de toegang tot e-mailberichten of andere services te beperken, de rapporten van apparaten weer te geven en een apparaat op afstand te wissen. Meestal gaat u naar het beveiligings & nalevings centrum om deze taken uit te voeren. Zie [Microsoft 365 compliance Center](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8)voor meer informatie.

## <a name="device-management-tasks"></a>Beheertaken voor apparaten

Voer de volgende stappen uit om het deelvenster Apparaatbeheer te openen:

1. Ga naar het [Microsoft 365-Beheercentrum](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).
    
2. Typ Mobile Device Management in het zoekveld en selecteer **Mobile Device Management**   in de lijst met resultaten.

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Optie voor het beheer van mobiele apparaten":::

3. Selecteer  **apparaten beheren**.

## <a name="manage-mobile-devices"></a>Mobiele apparaten beheren
    
Nadat u eenvoudige mobiliteit en beveiliging hebt ingesteld, kunt u op een van de volgende manieren de mobiele apparaten in uw organisatie beheren.

|**Als u dit wilt doen**|**Werkwijze**|
|:----------------|:------------------------------------------------------------------------------|
|Een apparaat wissen |Selecteer in het deelvenster Apparaatbeheer de optie *apparaatnaam*en vervolgens  **volledig wissen**   om alle gegevens te verwijderen of  **selectief wissen**   om alleen bedrijfsgegevens op het apparaat te verwijderen. Zie [een mobiel apparaat wissen in basis mobiliteit en beveiliging](wipe-mobile-device.md)voor meer informatie.|
|Het openen van niet-ondersteunde apparaten via Exchange ActiveSync blokkeren |Selecteer in het deelvenster Apparaatbeheer de optie  **blokkeren**. |
|Beleidsregels voor apparaten instellen, zoals wachtwoordvereisten en beveiligingsinstellingen |Selecteer in het deelvenster Apparaatbeheer de optie **beveiligingsbeleid voor apparaten**   >  **Add +**. Zie voor meer informatie het artikel [beveiligingsbeleid voor apparaten maken voor eenvoudige mobiliteit en beveiliging](create-device-security-policies-in-basic-mmobility-and-security.md).|
|Lijst met geblokkeerde apparaten weergeven  |Selecteer in het deelvenster Apparaatbeheer onder  **Selecteer een weergave** de   optie  **geblokkeerd**. |
|Niet-compatibel of niet-ondersteund apparaat voor een gebruiker of groep gebruikers deblokkeren  |Selecteer een van de volgende opties om de apparaten op te heffen:<br/>-De gebruikers of gebruikers van de beveiligingsgroep verwijderen waarop het beleid is toegepast. Ga naar het Microsoft 365-Beheercentrum > **groepen**en selecteer vervolgens groepsnaam. Selecteer **leden en beheerders bewerken**.<br/>-Verwijder de beveiligingsgroep waarvan de gebruikers deel uitmaken van het apparaatbeleid. Ga naar beveiligings & compliance >Security  **Policies**   >  **Security**policies. Selecteer naam apparaatbeleid en selecteer vervolgens implementatie **bewerken**  >  **Deployment**.<br/>: Alle niet-compatibele apparaten voor een apparaatbeleid deblokkeren. Ga naar beveiligings & compliance >Security  **Policies**   >  **Security**policies. Selecteer naam apparaatbeleid en selecteer vervolgens **Edit**  >  **toegangsvereisten**bewerken. Selecteer  **toegang toestaan en schending melden**.<br/>-Als u een niet-compatibel of niet-ondersteund apparaat wilt blokkeren voor een gebruiker of een groep gebruikers, gaat u naar beveiliging & compliance > **Security Policies**   >  **Device management**   >  **Manage Settings Settings**. Een beveiligingsgroep toevoegen waarvan u de toegang tot Microsoft 365 wilt uitsluiten, is geblokkeerd. Zie [een beveiligingsgroep maken, bewerken of verwijderen in het Microsoft 365-Beheercentrum](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb)voor meer informatie.|
|Meer informatie over de apparaten in uw organisatie  |Voor details, zoals welke apparaten geregistreerd zijn en voldoen aan het beveiligingsbeleid voor apparaten, raadpleegt u [informatie over basis apparatuur voor de mobiliteit en beveiliging](get-details-about-basic-mobility-and-security-managed-devices.md).|
|Gebruikers verwijderen zodat hun apparaten niet meer worden beheerd via basis mobiliteit en beveiliging |Als u de gebruiker wilt verwijderen, bewerkt u de beveiligingsgroep met beleidsregels voor apparaten voor eenvoudige mobiliteit en beveiliging. Zie  [een beveiligingsgroep maken, bewerken of verwijderen in het Microsoft 365-Beheercentrum](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb)voor meer informatie.<br/>Als u eenvoudige mobiliteit en beveiliging van alle Microsoft 365-gebruikers wilt verwijderen, raadpleegt u [eenvoudige mobiliteit en beveiliging](turn-off-basic-mobility-and-security.md)uitschakelen.|

Live (V14)