---
title: Azure Active Directory classificatie- en gevoeligheidslabels voor Microsoft 365 groepen
ms.reviewer: vijagan
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
f1.keywords: NOCSH
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
description: In dit artikel worden klassieke Azure Active Directory classificatie- en gevoeligheidslabels besproken.
ms.openlocfilehash: 07bc09afb3e490961a8cc5a88857ec49dd962856
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/26/2021
ms.locfileid: "52162370"
---
# <a name="azure-active-directory-classification-and-sensitivity-labels-for-microsoft-365-groups"></a>Azure Active Directory classificatie- en gevoeligheidslabels voor Microsoft 365 groepen

In dit artikel worden klassieke Azure Active Directory classificatie- en gevoeligheidslabels besproken.

Gevoeligheidslabels worden ondersteund door [deze services.](./sensitivity-labels-teams-groups-sites.md)

Zie Meer informatie over gevoeligheidslabels voor volledige informatie over [gevoeligheidslabels.](sensitivity-labels.md)

Zie Gevoeligheidslabels gebruiken om inhoud in Microsoft Teams, Microsoft 365 groepen en SharePoint te beschermen voor meer informatie over gevoeligheidslabels en hun gedrag voor sites en Microsoft 365 [SharePoint groepen.](sensitivity-labels-teams-groups-sites.md)

Bekijk de volgende scenario's voor best practices bij het migreren van de klassieke AAD-classificatie naar de gevoeligheidslabels.

## <a name="scenario-1-tenant-never-used-classic-aad-classifications-or-sensitivity-labels-for-documents-and-emails"></a>Scenario 1: Tenant heeft nooit klassieke AAD-classificaties of gevoeligheidslabels voor documenten en e-mailberichten gebruikt

- Tenantbeheerder schakelt gevoeligheidslabels voor groepen in door de tenantvlag 'EnableMIPLabels' in te stellen op true via AAD powershell-cmdlet.
- Tenantbeheerder maakt de gevoeligheidslabels in [het Microsoft 365 compliancecentrum.](https://compliance.microsoft.com)
    - Tenantbeheerder kan bestands- en e-mailgerelateerde acties kiezen, zoals versleuteling en watermerking.
    - Tenantbeheerder kan kiezen Microsoft 365 groepen en SharePoint online sitegerelateerde acties uitvoeren op de gevoeligheidslabels.
- Tenantbeheerder publiceert het beleid.
- **Compatibele werkbelastingen** geven gevoeligheidslabels weer. Gebruik de gevoeligheidslabels om groepen te maken. Compatibele werkbelastingen zijn de services die gevoeligheidslabels ondersteunen.
- **Niet-compatibele werkbelastingen** zijn de services die nog geen gevoeligheidslabels ondersteunen. Groepen kunnen worden gemaakt, maar ze kunnen niet worden gekoppeld aan het gevoeligheidslabel via niet-compatibele werkbelastingen. Als u dergelijke groepen wilt koppelen aan gevoeligheidslabels, kunnen tenantbeheerders PowerShell-cmdlets uitvoeren.

Tabel 1. Gedrag van compatibele en niet-compatibele werkbelastingen: groepen maken, bewerken of verwijderen

|Werkbelasting|Welke labellijst ziet de gebruiker in het groepsvenster?|Nieuwe groep maken |Groep bewerken |Groep verwijderen |
|:-------|:-------|:--------|:--------|:--------|   
|Compatibel   |gevoeligheidslabels. |Geen wijziging in gedrag. |Geen wijziging in gedrag. |Geen wijziging in gedrag. |
|Niet-compatibel |Er zijn geen gevoeligheidslabels zichtbaar. |Gebruiker kan een groep maken zonder gevoeligheidslabel te selecteren. <br><br> De beheerder kan cmdlets uitvoeren om gevoeligheidslabels op de achtergrond toe te passen. |**Case 1:** Geen gevoeligheidslabel dat eerder is geselecteerd. Gebruiker kan een groep bewerken.<br><br> **Case 2:** gevoeligheidslabel dat eerder op de achtergrond is toegepast met cmdlet. Gebruiker kan een groep bewerken, met uitzondering van het geval waarin de gebruiker een ongeldige combinatie van privacyinstelling selecteert met betrekking tot het label. |Geen wijziging in gedrag.|

> [!NOTE]
> In het geval van Outlook desktopclient (Win 32), nadat de beheerder gevoeligheidslabels voor de tenant heeft inschakelen en de gebruiker zich op een oudere versie van de Outlook-bureaubladclient (Win 32) heeft gebruikt:
>
> - Gebruiker ziet gevoeligheidslabels worden weergegeven in de oudere versie van de Outlook desktopclient.
> - Wanneer de gebruiker echter een groep bewerkt en de groep op slaat met een gevoeligheidslabel, wordt de geselecteerde privacyinstelling overgenomen door de privacyinstelling van het toegepaste gevoeligheidslabel.
>
> Het is raadzaam dat uw gebruikers op een oude versie van Outlook-client upgraden naar de nieuwere versie.

## <a name="scenario-2-tenant-is-already-using-classic-aad-classifications"></a>Scenario 2: Tenant gebruikt al klassieke [AAD-classificaties](../enterprise/manage-microsoft-365-groups-with-powershell.md)

### <a name="case-a-tenant-never-used-sensitivity-labels-for-documents-and-emails"></a>Case A: Tenant heeft nooit gevoeligheidslabels gebruikt voor documenten en e-mailberichten

1. In het [Microsoft 365 compliancecentrum](https://compliance.microsoft.com)wordt u aangeraden gevoeligheidslabels te maken met dezelfde naam als de bestaande klassieke Azure AD-labels.
2. Gebruik de PowerShell-cmdlet om deze gevoeligheidslabels toe te passen op bestaande Microsoft 365 groepen en SharePoint sites met naamtoewijzing.
3. Beheerder kan ervoor kiezen om de klassieke Azure AD-labels te verwijderen:
    - In compatibele werkbelastingen worden deze gevoeligheidslabels en groepen met deze labels gemaakt.
    - Niet-compatibele werkbelastingen werken bij het maken van groepen, maar er is geen gevoeligheidslabel aan gekoppeld.
4. Beheerders kunnen PowerShell-cmdlets uitvoeren om gevoeligheidslabels toe te passen op deze groepen zonder labels.
    - Een beheerder kan er ook voor kiezen om de klassieke Azure AD-labels te behouden:
        - Compatibele werkbelastingen geven deze gevoeligheidslabels weer en er worden groepen mee gemaakt. Compatibele werkbelastingen zijn de services die gevoeligheidslabels ondersteunen.
        - Niet-compatibele werkbelastingen werken bij het maken van groepen en geven klassieke Azure AD-labels weer. Deze klassieke Azure AD-labels zijn gekoppeld aan deze groepen die zijn gemaakt met niet-compatibele werkbelastingen.
5. Het wordt ten zeerste aangeraden dat beheerders PowerShell-cmdlets uitvoeren om gevoeligheidslabels toe te passen op deze groepen met klassieke Azure AD-labels.

Tabel 2. Gedrag van compatibele en niet-compatibele werkbelastingen: groepen maken, bewerken of verwijderen

|Werkbelasting|Welke labellijst ziet de gebruiker in het groepsvenster?|Nieuwe groep maken |Groep bewerken |Groep verwijderen |
|:-------|:-------|:--------|:--------|:--------|   
|Compatibel   |gevoeligheidslabels. |Geen wijziging in gedrag. |Geen wijziging in gedrag. |Geen wijziging in gedrag. |
|Niet-compatibel |Oude klassieke AAD-labels. |Gebruiker kan een groep maken met het klassieke Azure AD-label geselecteerd. <br><br>De beheerder kan cmdlets uitvoeren om gevoeligheidslabels op de achtergrond toe te passen. |**Case 1:** Geen gevoeligheidslabel dat eerder is geselecteerd. Gebruiker kan een groep bewerken.<br><br> **Case 2:** Klassieke AAD-labels die eerder zijn geselecteerd. Gebruiker kan een groep bewerken.<br><br> **Case 3:** gevoeligheidslabel dat eerder op de achtergrond is toegepast met cmdlet. De gebruiker moet een groep kunnen bewerken, met uitzondering van één geval waarin de gebruiker een ongeldige combinatie van privacyinstelling selecteert met betrekking tot het label. |Gebruiker kan een groep verwijderen. |

> [!NOTE]
> In het geval van Outlook desktopclient (Win 32), nadat de beheerder gevoeligheidslabels voor de tenant heeft inschakelen en de gebruiker zich op een oudere versie van de Outlook-bureaubladclient (Win 32) heeft gebruikt:
>
> - Gebruiker ziet gevoeligheidslabels worden weergegeven in de oudere versie van de Outlook desktopclient.
> - Wanneer de gebruiker echter een groep bewerkt en de groep op slaat met een gevoeligheidslabel, wordt de geselecteerde privacyinstelling overgenomen door de privacyinstelling van het toegepaste gevoeligheidslabel.
>
> Het is raadzaam dat uw gebruikers op een oude versie van Outlook-client upgraden naar de nieuwere versie.

### <a name="case-b-tenant-used-sensitivity-labels-for-documents-and-emails"></a>Case B: Tenant gebruikte gevoeligheidslabels voor documenten en e-mailberichten

1. Zodra beheerder gevoeligheidslabelfunctie in de tenant inschakelen door de tenantvlag 'EnableMIPLabels' in te stellen op waar, worden de document- en e-mailgevoeligheidslabels in de dialoogvensters groep/site/team maken en bewerken weergegeven.
2. Een beheerder kan dezelfde document- en e-mailgevoeligheidslabels gebruiken om privacy en externe gebruikerstoegang op de groep/site/team af te dwingen door gerelateerde groepsinstellingen op te geven:
    1. Selecteer in [Microsoft 365 compliancecentrum](https://compliance.microsoft.com)het **tabblad Sites en groepen.**
    2. Een document of e-mailgevoeligheidslabel bewerken.

## <a name="sample-script"></a>Voorbeeldscript

Zie Klassieke [Azure AD-groepsclassificatie](./sensitivity-labels-teams-groups-sites.md#classic-azure-ad-group-classification)voor een voorbeeldscript om groepen met klassieke AAD-labels te migreren naar gevoeligheidslabels.