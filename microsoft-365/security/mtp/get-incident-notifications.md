---
title: Meldingen over incidenten ontvangen in Microsoft 365 Defender
description: Informatie over het maken van regels om e-mailmeldingen te ontvangen voor incidenten in Microsoft 365 Defender
keywords: incident, e-mail, e-mailbevestigingen, configureren, gebruikers, postvak, e-mail, incidenten
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 9db025818fdd5eb2635a9a676e4a10e20f3036b6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930976"
---
# <a name="get-incident-notifications-by-email"></a>Ontvang incidentenmeldingen per e-mail

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

U kunt Microsoft 365 Defender zo instellen dat u per e-mail op de hoogte wordt gehouden wanneer er nieuwe incidenten of nieuwe updates van bestaande incidenten zijn. 

U kunt ervoor kiezen om meldingen te ontvangen op basis van de ernst van het incident of per apparaatgroep. U kunt er ook voor kiezen om alleen bij de eerste update per incident een melding te ontvangen.

U kunt geadresseerden toevoegen aan of verwijderen uit de e-mailmeldingen. Pas toegevoegde geadresseerden ontvangen een melding over incidenten nadat ze zijn toegevoegd. 

De e-mailmelding bevat belangrijke details over het incident, zoals de naam van het incident, de ernst en categorieën. U kunt ook rechtstreeks naar incidenten gaan, zodat u meteen een onderzoek kunt starten. Zie Incidenten in [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)onderzoeken voor meer informatie over het onderzoeken van incidenten.

>[!NOTE]
>U hebt machtigingen voor het beheren van beveiligingsinstellingen nodig om instellingen voor e-mailmeldingen te configureren. Als u ervoor hebt gekozen om basismachtigingenbeheer te gebruiken, kunnen gebruikers met de rollen Beveiligingsbeheerder of Globale beheerder e-mailmeldingen voor u configureren. <br> <br>
En als uw organisatie toegangsbeheer op basis van rollen gebruikt, kunt u alleen meldingen maken, bewerken, verwijderen en ontvangen op basis van apparaatgroepen die u mag beheren.

## <a name="create-rules-for-incident-notifications"></a>Regels maken voor incidentenmeldingen

Als u uw eerste e-mailmelding voor incidenten wilt instellen, maakt u een nieuwe regel en past u instellingen voor e-mailmeldingen aan.

1. Selecteer in het navigatiedeelvenster **E-mailmeldingen**  >  **instellingen-incident.**
2. Selecteer **Item toevoegen.**
3. Geef de regel een naam in **Naam** en geef een **beschrijving op.**

    ![Venster Regel maken voor e-mailincidenten](../../media/incidentemailnotif1.png) 
4. Selecteer **Volgende om** naar Instellingen voor meldingen te **gaan.** Hier kunt u het volgende opgeven:
    - **Ernst van de waarschuwing:** kies de ernst van de waarschuwing die een incidentmelding activeert. Als u bijvoorbeeld alleen op de hoogte wilt zijn van incidenten met hoge ernst, selecteert u Hoog.
    - **Bereik van apparaatgroep:** in deze vervolgkeuzen ziet u alle apparaatgroepen waar de gebruiker toegang toe heeft. Selecteer voor welke apparaatgroepen u de meldingsregels voor incidenten maakt.
    - **Alleen melden bij eerste exemplaar per incident.** Als u deze optie selecteert, wordt alleen een e-mailmelding verzonden die overeenkomt met uw andere selecties. Latere updates of waarschuwingen met betrekking tot het incident activeren geen melding.
    - **De naam van de organisatie** opnemen: hiermee wordt aangegeven of de naam van de klant al dan niet in de e-mailmelding wordt weergegeven.
    - **Inclusief tenantspecifieke portalkoppeling:** hiermee voegt u een koppeling met de tenant-id toe voor toegang tot een specifieke tenant.
    
    ![Venster Notif-instellingen voor notif-instellingen voor e-mailincidenten](../../media/incidentemailnotif2.png)
5. Selecteer **Volgende** om naar de sectie **Geadresseerden te** gaan. Hier kunt u e-mailadressen opgeven die de e-mailmeldingen voor het incident ontvangen. Selecteer **Een geadresseerde toevoegen nadat** u elk e-mailadres hebt typen.

    ![Venster Geadresseerden toevoegen voor notifs voor incidentele e-mail](../../media/incidentemailnotif3.png) 

6. Selecteer ten slotte **Volgende om** naar de regel Controleren **te gaan,** zodat u alle instellingen ziet die aan de nieuwe regel zijn gekoppeld. Geadresseerden ontvangen incidentmeldingen via e-mail op basis van de instellingen.

## <a name="see-also"></a>Zie ook
- [Overzicht van incidenten in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [Prioriteit geven aan incidenten in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [Incidenten in Microsoft 365 Defender onderzoeken](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

