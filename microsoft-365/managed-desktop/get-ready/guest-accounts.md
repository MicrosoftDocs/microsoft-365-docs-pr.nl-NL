---
title: Vereisten voor gastaccounts
description: Configuratie richtlijnen voor gastaccounts en hoe u deze kunt aanpassen
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d8953e9f451daa02671a1e1544f2dfe6649ab1b3
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073200"
---
# <a name="prerequisites-for-guest-accounts"></a>Vereisten voor gastaccounts

Voor het Microsoft-beheer bureaublad zijn de volgende instellingen nodig in de Azure AD-organisatie voor toegang tot een gastaccount. U kunt deze instellingen wijzigen bij [Azure Portal](https://portal.azure.com) onder **externe identiteiten/extern samenwerken** :

-   **Beheerders en gebruikers in de rol van gast invite kunnen de set uitnodigen** op **Ja**
-   Kies voor **samenwerkings beperkingen** een van deze opties:
    -   Als u **uitnodigingen toestaan selecteert voor het verzenden van een domein (meestal)** , hoeft u geen andere configuratie uit te schakelen.
    -   Als u **uitnodigingen voor de opgegeven domeinen weigeren** selecteert, controleert u of Microsoft.com niet wordt vermeld in de doeldomeinen.
    -   Als u **alleen uitnodigingen toestaan selecteert voor de opgegeven domeinen (de meeste beperkingen)** , controleert u of Microsoft.com in de doeldomeinen *wordt* weergegeven.

Als u beperkingen instelt voor de instellingen van deze instellingen, moet u ervoor zorgen dat de service accounts van Azure Active Directory voor de **moderne werkplek** worden uitgesloten. Als u bijvoorbeeld een beleid voor voorwaardelijke toegang hebt om te voorkomen dat gastaccounts toegang krijgen tot de intune-Portal, moet u de groep **service accounts van modern werk** stroom uitsluiten van dit beleid.

