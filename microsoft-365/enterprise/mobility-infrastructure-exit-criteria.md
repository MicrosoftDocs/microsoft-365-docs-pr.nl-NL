---
title: Criteria voor het afsluiten van infrastructuur voor mobiele apparaten
description: Microsoft 365 Enterprise omvat beheer van mobiele apparaten met Microsoft Intune. Bekijk de vereisten en vereisten, stel Intune in met uw Azure Active Directory-bron, schrijf iOS-, macOS-, Android- en Windows-apparaten in, implementeer apps, maak een profiel configureren, gebruik een nalevingsbeleid en schakel Voorwaardelijke toegang in voor mobiel apparaatbeheer met Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365-documentatie, beheer van mobiele apparaten, Intune
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/03/2019
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: 3e8013426983584783488e6f937f8ba5b02d7a1a
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806610"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a>Criteria voor het afsluiten van infrastructuur voor mobiele apparaten

![Fase 5: Beheer van mobiele apparaten](../media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

*Dit geldt voor de E3- en E5-versies van Microsoft 365 Enterprise*

Zorg ervoor dat uw configuratie voldoet aan de volgende vereisten voor infrastructuur voor het beheer van mobiele apparaten.

- Intune is ingesteld, inclusief het maken van Azure Active Directory -gebruikers en groepen (Azure AD) om de regels van uw organisatie toe te passen voor apparaten.
- U hebt apparaten ingeschreven in Intune, zodat de apparaten het beleid kunnen ontvangen dat u maakt.
- Apps worden toegevoegd aan apparaten, zodat uw gebruikers toegang krijgen tot de Microsoft 365-cloudservices van uw organisatie, zoals Exchange Online en SharePoint Online.
- Functies en instellingen worden geconfigureerd en toegepast op uw apparaten met behulp van de Azure AD-gebruikers en groepen die u maakt, waaronder het inschakelen van anti-virus en het beperken van specifieke apps.
- Er zijn nalevingsbeleidsregels vereist om een firewall of een wachtwoordlengte op een apparaat te vereisen. Als apparaten niet compatibel zijn, blokkeert Voorwaardelijke toegang de toegang tot de gegevens van uw organisatie.

## <a name="results-and-next-steps"></a>Resultaten en volgende stappen

Uw apparaten zijn ingeschreven in Intune en geconfigureerd met het juiste beleid.

|||
|:-------|:-----|
|![Fase 6: Informatiebescherming](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| Als u de fasen voor de end-to-end implementatie van Microsoft 365 Enterprise volgt, is uw volgende fase [informatiebeveiliging.](infoprotect-infrastructure.md) |
