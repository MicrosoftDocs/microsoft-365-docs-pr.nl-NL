---
title: Beveiligingswaarschuwingen voor Microsoft Defender voor identiteit in Microsoft 365 Defender
description: Informatie over het beheren en controleren van beveiligingswaarschuwingen die zijn uitgegeven door Microsoft Defender voor identiteit in Microsoft 365 Defender
ms.date: 05/20/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
manager: raynew
ms.openlocfilehash: 0c48c9076d05cd352229477acc28b32185eef54f
ms.sourcegitcommit: 4f6ef4cd09c3ed36dc0be3702b0636bad6cff8a9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/26/2021
ms.locfileid: "52657800"
---
# <a name="defender-for-identity-security-alerts-in-microsoft-365-defender"></a>Beveiligingswaarschuwingen voor Defender voor identiteit in Microsoft 365 Defender

**Van toepassing op:**

- Microsoft 365 Defender
- Defender for Identity

In dit artikel worden de basisbeginselen beschreven van het werken met [beveiligingswaarschuwingen](/defender-for-identity) van Microsoft Defender voor identiteit in het [Microsoft 365 beveiligingscentrum.](/microsoft-365/security/defender/overview-security-center)

Defender voor identiteitswaarschuwingen zijn inheems geïntegreerd in [het Microsoft 365 beveiligingscentrum](https://security.microsoft.com) met een speciale paginanotatie voor identiteitswaarschuwingen. Dit markeert de eerste stap in de reis om de volledige [Microsoft Defender for Identity-ervaring](/defender-for-identity/defender-for-identity-in-microsoft-365-defender)in te voeren in Microsoft 365 Defender.

De nieuwe pagina Identiteitsmelding biedt klanten van Microsoft Defender voor identiteit betere signaalverrijking voor meerdere domeinen en nieuwe mogelijkheden voor automatische identiteitsreacties. Het zorgt ervoor dat u veilig blijft en de efficiëntie van uw beveiligingsbewerkingen verbetert.

Een van de voordelen van het onderzoeken van waarschuwingen [via Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender) is dat microsoft Defender voor identiteitswaarschuwingen verder worden gecorreleerd met informatie die is verkregen uit elk van de andere producten in de suite. Deze verbeterde waarschuwingen komen overeen met de andere Microsoft 365 Defender-waarschuwingsindelingen die afkomstig zijn van [Microsoft Defender voor Office 365](/microsoft-365/security/office-365-security) en Microsoft Defender voor [Eindpunt.](/microsoft-365/security/defender-endpoint) Met de nieuwe pagina hoeft u niet meer naar een andere productportal te gaan om waarschuwingen te onderzoeken die zijn gekoppeld aan identiteit.

Waarschuwingen die afkomstig zijn van Defender voor identiteit kunnen nu de [geautomatiseerde onderzoeks-](/microsoft-365/security/defender/m365d-autoir) en antwoordfuncties van Microsoft 365 Defender activeren, waaronder het automatisch corrigeren van waarschuwingen en het beperken van hulpmiddelen en processen die kunnen bijdragen aan de verdachte activiteit.

>[!IMPORTANT]
>Als onderdeel van de convergentie met Microsoft 365 Defender zijn sommige opties en details gewijzigd van hun locatie in de Defender for Identity-portal. Lees de onderstaande details om te ontdekken waar u de vertrouwde en nieuwe functies kunt vinden.

## <a name="review-security-alerts"></a>Beveiligingswaarschuwingen controleren

Waarschuwingen zijn toegankelijk vanaf meerdere locaties, waaronder  de pagina **Waarschuwingen,** de pagina Incidenten, de pagina's van afzonderlijke apparaten **en** vanaf de **pagina Geavanceerd.** In dit voorbeeld bekijken we de pagina **Waarschuwingen.**  

Ga in [Microsoft 365 beveiligingscentrum](https://security.microsoft.com/)naar **Incidenten & waarschuwingen** en vervolgens naar **Waarschuwingen.**

![Ga naar Incidenten en waarschuwingen en vervolgens Waarschuwingen](../../media/defender-identity/incidents-alerts.png)

Als u waarschuwingen van Defender voor identiteit wilt zien, selecteert u rechtsboven **Filter** en selecteert u onder **Servicebronnen** **Microsoft Defender** voor identiteit en selecteert u **Toepassen:**

![Filteren op Defender voor identiteitsgebeurtenissen](../../media/defender-identity/filter-defender-for-identity.png)

De waarschuwingen worden weergegeven met informatie in de volgende **kolommen:** Waarschuwingsnaam **,** **Tags**, Ernst **,** Onderzoeksstatus , **Status** **,** Categorie , **Detectiebron**, **Beïnvloede** activa , **Eerste** activiteit en **Laatste activiteit**.

![Defender voor identiteitsgebeurtenissen](../../media/defender-identity/filtered-alerts.png)

## <a name="manage-alerts"></a>Waarschuwingen beheren

Als u op de **naam Waarschuwing voor** een van de waarschuwingen klikt, gaat u naar de pagina met informatie over de waarschuwing. In het linkerdeelvenster ziet u een overzicht van **Wat is er gebeurd:**

![Wat is er gebeurd met een waarschuwing](../../media/defender-identity/what-happened.png)

Boven het **vak Wat is er** gebeurd, staan knoppen voor de **accounts,** **doelhost** en **bronhost** van de waarschuwing. Voor andere waarschuwingen ziet u mogelijk knoppen voor meer informatie over extra hosts, accounts, IP-adressen, domeinen en beveiligingsgroepen. Selecteer een van deze entiteiten voor meer informatie over de betrokken entiteiten.

In het rechterdeelvenster ziet u de **details van waarschuwing.** Hier ziet u meer details en voert u verschillende taken uit:

- **Classificeer deze waarschuwing-** Hier kunt u deze waarschuwing aanwijzen als **een** waarmelding **of een onwaar waarschuwing**

    ![Waarschuwing classificeren](../../media/defender-identity/classify-alert.png)

- **Waarschuwingstoestand** : in **Classificatie instellen** kunt u de waarschuwing classificeren als **Waar** of **Onwaar.** In **Toegewezen aan** kunt u de waarschuwing aan uzelf toewijzen of de waarschuwing niet toewijzen.

    ![Waarschuwingstoestand](../../media/defender-identity/alert-state.png)

-  Waarschuwingsdetails: onder Waarschuwingsdetails vindt u meer informatie over de specifieke waarschuwing, volgt u een koppeling naar documentatie over het type waarschuwing, bekijkt u aan welk incident de waarschuwing is gekoppeld, bekijkt u alle geautomatiseerde onderzoeken die zijn gekoppeld aan dit waarschuwingstype en bekijkt u de beïnvloede apparaten en gebruikers. 

    ![Waarschuwingsdetails](../../media/defender-identity/alert-details.png)

- **Opmerkingen & geschiedenis:** hier kunt u opmerkingen toevoegen aan de waarschuwing en de geschiedenis bekijken van alle acties die aan de waarschuwing zijn gekoppeld.

    ![Opmerkingen en geschiedenis](../../media/defender-identity/comments-history.png)

- **Waarschuwing beheren:** als u **Waarschuwing beheren** selecteert, gaat u naar een deelvenster waarmee u het volgende kunt bewerken:
  - **Status:** u kunt **Nieuw,** **Opgelost of** In **uitvoering kiezen.**
  - **Classificatie:** u kunt **Waar-waarschuwing of** **Onwaar-waarschuwing kiezen.**
  - **Opmerking:** u kunt een opmerking over de waarschuwing toevoegen.

    Als u de drie puntjes naast Waarschuwing beheren selecteert, kunt u een bedreigingsexpert **raadplegen,** de waarschuwing exporteren naar een Excel bestand of Koppelen **aan een ander incident.**  

    ![Waarschuwing beheren](../../media/defender-identity/manage-alert.png)

    >[!NOTE]
    >In het Excel hebt u nu twee koppelingen beschikbaar: **Weergeven in Microsoft Defender** voor identiteit en weergave in Microsoft 365 **Defender.** Elke koppeling brengt u naar de relevante portal en geeft informatie over de waarschuwing daar.

## <a name="see-also"></a>Zie ook

- [Waarschuwingen onderzoeken in Microsoft 365 Defender](../defender/investigate-alerts.md)
