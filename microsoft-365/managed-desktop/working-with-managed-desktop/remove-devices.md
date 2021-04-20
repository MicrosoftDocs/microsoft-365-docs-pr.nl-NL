---
title: Apparaten verwijderen
description: Apparaten verwijderen uit Microsoft Managed Desktop Management
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: fa1cb7307fddd815a2a9249c5a98739d21bd2418
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893735"
---
# <a name="remove-devices"></a>Apparaten verwijderen

U kunt apparaten verwijderen uit Microsoft Managed Desktop Management met behulp van de beheerportal. Deze actie is permanent, maar u kunt deze opnieuw registreren bij Microsoft Managed Desktop door de [registratiestappen te volgen.](../get-started/register-devices-self.md)

Wanneer u een apparaat verwijdert, vindt u de volgende stappen:

- We verwijderen het apparaat van Autopilot.
- We verwijderen het apparaat uit alle apparaatgroepen 'Moderne werkplek'.
- We verwijderen het apparaat uit het **blad Apparaten** in de beheerportal.

Wanneer u een apparaat verwijdert, kunt u het apparaat ook verwijderen uit Azure Active Directory (Azure AD) en Microsoft Intune.
 
> [!CAUTION]
> Het verwijderen van de objecten die betrekking hebben op een apparaat uit Azure AD en Microsoft Intune is permanent. Als u de objecten verwijdert, kunt u de apparaten niet bekijken of beheren vanuit de Intune- en Azure-portals. De apparaten hebben geen toegang tot de bedrijfsresources van hun bedrijf. Bedrijfsgegevens kunnen van hen worden verwijderd als de apparaten zich proberen aan te melden nadat ze zijn verwijderd.

1. Selecteer [in Microsoft Endpoint Manager](https://endpoint.microsoft.com/)de optie **Apparaten** in het linkernavigatiedeelvenster.
2. Zoek de sectie **Microsoft Managed Desktop** van het menu en selecteer **Apparaten.**
3. Selecteer in de werkruimte Microsoft Managed Desktop Devices de apparaten die u wilt verwijderen.
4. Selecteer **Apparaatacties** en selecteer vervolgens **Apparaat verwijderen waarmee** een fly-in wordt geopend om de apparaten te verwijderen.
5. Controleer in de fly-in de geselecteerde apparaten en selecteer **vervolgens Apparaten verwijderen.** Als u de Azure AD- en Intune-objecten tegelijk wilt verwijderen, schakelt u het selectievakje in. Het verwijderen van apparaten kan enkele minuten duren.

> [!NOTE]
> U kunt apparaten met een in behandeling zijnde registratietoestand **niet** verwijderen.