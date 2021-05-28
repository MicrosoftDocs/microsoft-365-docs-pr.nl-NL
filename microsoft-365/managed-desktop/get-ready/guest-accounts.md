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
ms.openlocfilehash: d29b9d6bdc30d981b273d95925ba740bc92304c4
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694243"
---
# <a name="prerequisites-for-guest-accounts"></a>Vereisten voor gast-accounts

Microsoft Managed Desktop vereist de volgende instellingen in uw Azure AD-organisatie voor toegang tot gastaccounts. U kunt deze instellingen aanpassen in de [Azure-portal](https://portal.azure.com) onder Instellingen voor externe **identiteiten /Externe samenwerking:**

-   Voor **beperkingen voor gast uitnodigen die** zijn ingesteld op Ledengebruikers en gebruikers die zijn toegewezen aan specifieke beheerdersrollen, kunnen gastgebruikers met inbegrip van gasten met **lidmachtigingen worden uitgenodigd**
-   Kies een van de volgende opties voor **samenwerkingsbeperkingen:**
    -   Als u **Uitnodigingen toestaan om te worden verzonden naar** een domein (inclusief) selecteert, is er geen andere configuratie vereist.
    -   Als u **Uitnodigingen weigeren voor** de opgegeven domeinen selecteert, moet u ervoor zorgen dat Microsoft.com niet wordt weergegeven in de doeldomeinen.
    -   Als u Uitnodigingen alleen toestaan voor de opgegeven domeinen **(meest beperkende)** selecteert, moet u ervoor zorgen dat Microsoft.com wordt weergegeven in de doeldomeinen. 

Als u beperkingen in stelt die met deze instellingen werken, moet u de Azure Active Directory **Moderne werkplekserviceaccounts uitsluiten.** Als u bijvoorbeeld een beleid voor voorwaardelijke toegang hebt dat verhindert dat gastaccounts toegang krijgen tot de Intune-portal, sluit u de groep Moderne **werkplekserviceaccounts** uit van dit beleid.

## <a name="steps-to-get-ready"></a>Stappen om u klaar te maken

1. Lees [vereisten voor Microsoft Managed Desktop](prerequisites.md).
2. Gebruik [hulpprogramma's voor gereedheidsevaluatie](readiness-assessment-tool.md).
3. [Vereisten voor gastaccounts](guest-accounts.md) (Dit artikel)
4. [Netwerkconfiguratie voor Microsoft Managed Desktop](network.md)
5. [Certificaten en netwerkprofielen voorbereiden voor Microsoft Managed Desktop](certs-wifi-lan.md)
6. [Toegang voorbereiden tot on-premises bronnen voor Microsoft Managed Desktop](authentication.md)
7. [Apps in Microsoft Managed Desktop](apps.md)
8. [Toegewezen stations voorbereiden voor Microsoft Managed Desktop](mapped-drives.md)
9. [Afdrukbronnen voorbereiden voor Microsoft Managed Desktop](printing.md)
