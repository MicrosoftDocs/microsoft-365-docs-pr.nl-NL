---
title: Meldingen van incidenten per e-mail ontvangen in Microsoft 365 Defender
description: Meer informatie over het maken van regels voor het ontvangen van e-mailmeldingen voor incidenten in Microsoft 365 Defender
keywords: incident, e-mail, e-mail notfications, configureren, gebruikers, postvak, e-mail, incidenten, analyseren, antwoord
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 7ba21e08f72760654993335764df00e78abc87b2
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939716"
---
# <a name="get-incident-notifications-by-email"></a>Meldingen van incidenten per e-mail ontvangen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

U kunt Microsoft 365 Defender instellen om uw personeel via een e-mail op de hoogte te stellen van nieuwe incidenten of updates voor bestaande incidenten. U kunt ervoor kiezen om meldingen te ontvangen op basis van:

- Incident ernst.
- Apparaatgroep.
- Alleen bij de eerste update per incident.

De e-mailmelding bevat belangrijke details over het incident, zoals de naam van het incident, de ernst en de categorieën. U kunt ook rechtstreeks naar het incident gaan en uw analyse meteen starten. Zie Incidenten analyseren voor [meer informatie.](investigate-incidents.md)

U kunt geadresseerden toevoegen of verwijderen in de e-mailmeldingen. Nieuwe geadresseerden krijgen een melding over incidenten nadat ze zijn toegevoegd. 

>[!NOTE]
>U hebt de machtiging Beveiligingsinstellingen beheren nodig om instellingen voor e-mailmeldingen te configureren. Als u ervoor hebt gekozen om basismachtigingenbeheer te gebruiken, kunnen gebruikers met beveiligingsbeheerder- of globale beheerdersrollen e-mailmeldingen voor u configureren. <br> <br>
Als uw organisatie op rollen gebaseerd toegangsbeheer (RBAC) gebruikt, kunt u alleen meldingen maken, bewerken, verwijderen en ontvangen op basis van apparaatgroepen die u mag beheren.

## <a name="create-a-rule-for-email-notifications"></a>Een regel maken voor e-mailmeldingen

Volg deze stappen om een nieuwe regel te maken en instellingen voor e-mailmeldingen aan te passen.

1. Selecteer in het navigatiedeelvenster **Instellingen > Microsoft 365 Defender > Meldingen van incidenten.**
2. Selecteer **Item toevoegen.**
3. Typ op **de** pagina Basisbeginselen de regelnaam en een beschrijving en selecteer **volgende**.
4. Configureer **op de pagina** Meldingsinstellingen:
    - **Ernst van waarschuwing:** kies de ernst van de waarschuwing die een melding van een incident veroorzaakt. Als u bijvoorbeeld alleen op de hoogte wilt zijn van incidenten met hoge ernst, selecteert u **Hoog**.
    - **Bereik van apparaatgroep:** u kunt alle apparaatgroepen opgeven of selecteren in de lijst met apparaatgroepen in uw tenant.
    - **Alleen een melding bij eerste gebeurtenis per incident-** Selecteer of u alleen een melding wilt ontvangen bij de eerste waarschuwing die overeenkomt met uw andere selecties. Latere updates of waarschuwingen met betrekking tot het incident sturen geen extra meldingen.
    - **Naam van organisatie opnemen in het e-mailbericht:** selecteer of de naam van uw organisatie moet worden weergegeven in de e-mailmelding.
    - **Tenantspecifieke portalkoppeling** opnemen: selecteer of u een koppeling met de tenant-id wilt toevoegen in de e-mailmelding voor toegang tot een specifieke Microsoft 365-tenant.

    :::image type="content" source="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png" alt-text="Meldingsinstellingen voor meldingen van incidenten":::

5. Selecteer **Volgende**. Voeg op **de pagina** Geadresseerden de e-mailadressen toe die de incidentenmeldingen ontvangen. Selecteer **Toevoegen nadat** u elk nieuw e-mailadres hebt typen. Als u meldingen wilt testen en wilt controleren of de geadresseerden deze ontvangen in de Postvak IN, selecteert u **Test-e-mail verzenden.** 
6. Selecteer **Volgende**. Controleer op **de pagina** Regel controleren de instellingen van de regel en selecteer regel **maken.** Geadresseerden ontvangen incidentmeldingen via e-mail op basis van de instellingen.

Als u een bestaande regel wilt bewerken, selecteert u deze in de lijst met regels. Selecteer regel bewerken in het  deelvenster met de regelnaam en wijzig de regels op de pagina's Basisbeginselen, Instellingen voor meldingen **en** **Geadresseerden.**

Als u een bestaande regel wilt bewerken, selecteert u deze in de lijst met regels. Selecteer verwijderen in het deelvenster met de **regelnaam.**

## <a name="see-also"></a>Zie ook
- [Overzicht van incidenten](incidents-overview.md)
- [Prioriteit geven aan incidenten](incident-queue.md)
- [Incidenten analyseren](investigate-incidents.md)
