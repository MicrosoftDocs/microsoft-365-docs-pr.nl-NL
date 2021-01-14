---
title: Incident meldingen ontvangen in Microsoft 365 Defender
description: Leer hoe u regels maakt voor het ontvangen van e-mail meldingen voor incidenten in Microsoft 365 Defender
keywords: incident, e-mail, e-notfications, configureren, gebruikers, postvak, e-mail, incidenten
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: f25be4de3f25db869957474c3cb32b20e9f7aa53
ms.sourcegitcommit: 88d358d778804b26d5e41c53b4f725d01a78112b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/13/2021
ms.locfileid: "49848889"
---
# <a name="get-incident-notifications-by-email"></a>Incident meldingen ontvangen via e-mail

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

U kunt Microsoft 365 Defender zo instellen dat u per e-mail op de hoogte wordt gesteld wanneer er nieuwe incidenten of nieuwe updates zijn voor bestaande incidenten. 

U kunt ervoor kiezen om meldingen te ontvangen op basis van de ernst van het incident of de groep apparaten. U kunt er ook voor kiezen om een melding te ontvangen bij de eerste update per incident.

U kunt geadresseerden toevoegen aan of verwijderen uit de e-mail meldingen. Toegevoegde geadresseerden ontvangen een melding over incidenten nadat ze zijn toegevoegd. 

De e-mail melding bevat belangrijke informatie over het incident, zoals de naam van het incident, de ernst en de categorieën. U kunt ook rechtstreeks naar incidenten gaan, zodat u direct aan de slag kunt met uw onderzoek. Zie [incidenten onderzoeken in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)voor meer informatie over het onderzoeken van incidenten.

>[!NOTE]
>U wilt de machtigingen van de beveiligingsinstellingen beheren om instellingen voor e-mail meldingen te configureren. Als u hebt gekozen voor het gebruik van basismachtigingen beheer, kunnen gebruikers met beveiligingsbeheerders of globale beheerdersrollen e-mail meldingen voor u configureren. <br> <br>
Ook als uw organisatie gebruikmaakt van een toegangsbeheer op basis van rollen, kunt u alleen een bericht maken, bewerken, verwijderen en ontvangen op basis van apparaatgroepen die u mag beheren.

## <a name="create-rules-for-incident-notifications"></a>Regels voor incident meldingen maken

Als u uw eerste e-mail melding voor incidenten wilt instellen, maakt u een nieuwe regel en wijzigt u de instellingen voor e-mail meldingen.

1. Selecteer in het navigatiedeelvenster **instellingen** voor  >  **e-mail meldingen van incidenten**.
2. Selecteer **item toevoegen**.
3. Geef een **naam op voor** de regel en typ een **Beschrijving**.

    ![Het venster regel maken voor e-mail notifs voor incidenten](../../media/incidentemailnotif1.png) 
4. Selecteer **volgende** om naar de **instellingen voor meldingen** te gaan. Hier kunt u het volgende opgeven:
    - **Ernst van waarschuwing** : Kies de ernst van de waarschuwing waarmee de melding van een incident wordt geactiveerd. Als u bijvoorbeeld alleen op de hoogte wilt blijven van hoge urgentie, selecteert u hoog.
    - **Bereik van apparaat** : in deze vervolgkeuzelijst worden alle apparaatgroepen weergegeven waartoe de gebruiker toegang kan krijgen. Selecteer voor welke apparaatgroepen u de regels voor incident meldingen wilt maken.
    - **Alleen op de hoogte van het eerste exemplaar per voorval melden** : als u deze optie selecteert, wordt een e-mail melding alleen verzonden bij de eerste waarschuwing die overeenkomt met uw andere keuzes. Later updates of waarschuwingen met betrekking tot het incident veroorzaken geen meldingen.
    - **Naam van organisatie opnemen** : geeft aan of de naam van de klant wordt weergegeven in de e-mail melding of niet.
    - **Tenant-specifieke Portal koppeling toevoegen** : Hiermee wordt een koppeling met de Tenant-id toegevoegd om toegang tot een specifieke Tenant mogelijk te maken.
    
    ![Venster met instellingen voor e-mailbericht voor e-mail notifs](../../media/incidentemailnotif2.png)
5. Selecteer **volgende** om naar de sectie **geadresseerden** te gaan. Hier kunt u e-mailadressen opgeven waarop e-mail meldingen van incidenten worden ontvangen. Selecteer **een geadresseerde toevoegen na het** typen van elk e-mailadres.

    ![Venster geadresseerden toevoegen voor e-mail notifs](../../media/incidentemailnotif3.png) 

6. Selecteer ten slotte **volgende** om naar de **regel controleren** te gaan zodat u alle instellingen kunt zien van de nieuwe regel. Geadresseerden ontvangen via e-mail incident meldingen via e-mail, op basis van de instellingen.

## <a name="see-also"></a>Zie ook
- [Overzicht van incidenten in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [Incidenten prioriteren in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [Gebeurtenissen onderzoeken in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

