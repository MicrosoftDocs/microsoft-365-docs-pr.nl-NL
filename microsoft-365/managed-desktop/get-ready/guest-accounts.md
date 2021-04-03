---
title: Vereisten voor gast-accounts
description: Configuratierichtlijnen voor gastaccounts en hoe u deze kunt aanpassen
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: bbf679a01716fc48d37b241d69740f50a985f048
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574605"
---
# <a name="prerequisites-for-guest-accounts"></a>Vereisten voor gast-accounts

Microsoft Managed Desktop vereist de volgende instellingen in uw Azure AD-organisatie voor toegang tot gastaccounts. U kunt deze instellingen aanpassen in de [Azure-portal](https://portal.azure.com) onder **Externe identiteiten / Externe samenwerking:**

-   **Beheerders en gebruikers in de rol van gastvernodiger kunnen** de set uitnodigen op **Ja**
-   Kies een van de volgende opties voor **samenwerkingsbeperkingen:**
    -   Als u **Uitnodigingen toestaan om te worden verzonden naar** een domein (inclusief) selecteert, is er geen andere configuratie vereist.
    -   Als u **Uitnodigingen weigeren voor** de opgegeven domeinen selecteert, moet u ervoor zorgen dat Microsoft.com niet wordt weergegeven in de doeldomeinen.
    -   Als u Uitnodigingen alleen toestaan voor de opgegeven domeinen **(meest beperkende)** selecteert, moet u ervoor zorgen dat Microsoft.com wordt weergegeven in de doeldomeinen. 

Als u beperkingen in stelt die met deze instellingen werken, moet u de Serviceaccounts voor moderne werkplekken van Azure Active Directory **uitsluiten.** Als u bijvoorbeeld een beleid voor voorwaardelijke toegang hebt dat verhindert dat gastaccounts toegang krijgen tot de Intune-portal, sluit u de groep Moderne **werkplekserviceaccounts** uit van dit beleid.

## <a name="steps-to-get-ready"></a>Stappen om u klaar te maken

1. Controleer [vereisten voor Microsoft Managed Desktop](prerequisites.md).
2. Gebruik [gereedheidsbeoordelingshulpmiddelen.](readiness-assessment-tool.md)
3. [Vereisten voor gastaccounts](guest-accounts.md) (Dit artikel)
4. [Netwerkconfiguratie voor Microsoft Managed Desktop](network.md)
5. [Certificaten en netwerkprofielen voorbereiden voor Microsoft Managed Desktop](certs-wifi-lan.md)
6. [Toegang voorbereiden tot on-premises bronnen voor Microsoft Managed Desktop](authentication.md)
7. [Apps in Microsoft Managed Desktop](apps.md)
8. [Toegewezen stations voorbereiden voor Microsoft Managed Desktop](mapped-drives.md)
9. [Printbronnen voorbereiden voor Microsoft Managed Desktop](printing.md)