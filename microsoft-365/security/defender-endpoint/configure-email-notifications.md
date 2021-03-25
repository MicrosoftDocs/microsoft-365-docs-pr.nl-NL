---
title: Waarschuwingsmeldingen configureren in Microsoft Defender voor Eindpunt
description: U kunt Microsoft Defender voor Eindpunt gebruiken om instellingen voor e-mailmeldingen te configureren voor beveiligingswaarschuwingen, op basis van ernst en andere criteria.
keywords: e-mailmeldingen, waarschuwingsmeldingen configureren, atp-meldingen van Microsoft Defender, atp-waarschuwingen voor Microsoft Defender, Windows 10 Enterprise, Windows 10 Education
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d8b68e6b6dc42de5730aa634386406d4762b1fa2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163681"
---
# <a name="configure-alert-notifications-in-microsoft-defender-atp"></a>Waarschuwingsmeldingen configureren in MICROSOFT Defender ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-emailconfig-abovefoldlink)

U kunt Defender voor Eindpunt zo configureren dat e-mailmeldingen worden verzonden naar opgegeven geadresseerden voor nieuwe waarschuwingen. Met deze functie kunt u een groep personen identificeren die onmiddellijk worden geïnformeerd en die kunnen reageren op waarschuwingen op basis van hun ernst.

> [!NOTE]
> Alleen gebruikers met machtigingen voor beveiligingsinstellingen beheren kunnen e-mailmeldingen configureren. Als u ervoor hebt gekozen om basismachtigingenbeheer te gebruiken, kunnen gebruikers met beveiligingsbeheerder- of globale beheerdersrollen e-mailmeldingen configureren.

U kunt de ernstniveaus voor waarschuwingen instellen die meldingen activeren. U kunt ook geadresseerden van de e-mailmelding toevoegen of verwijderen. Nieuwe geadresseerden krijgen een melding over waarschuwingen die worden aangetroffen nadat ze zijn toegevoegd. Zie De wachtrij Waarschuwingen weergeven en organiseren voor meer informatie over [waarschuwingen.](alerts-queue.md)

Als u RBAC (Role Based Access Control) gebruikt, ontvangen geadresseerden alleen meldingen op basis van de apparaatgroepen die zijn geconfigureerd in de meldingsregel.
Gebruikers met de juiste machtigingen kunnen alleen meldingen maken, bewerken of verwijderen die zijn beperkt tot het beheerbereik van hun apparaatgroep.
Alleen gebruikers die zijn toegewezen aan de rol globale beheerder kunnen meldingsregels beheren die zijn geconfigureerd voor alle apparaatgroepen.

De e-mailmelding bevat basisinformatie over de waarschuwing en een koppeling naar de portal waar u verder onderzoek kunt doen.


## <a name="create-rules-for-alert-notifications"></a>Regels voor waarschuwingsmeldingen maken
U kunt regels maken om de ernst van de apparaten en waarschuwingen te bepalen voor het verzenden van e-mailmeldingen voor en de geadresseerden van de melding.


1. Selecteer in het navigatiedeelvenster **Meldingen**  >  **van waarschuwingsinstellingen**.

2. Klik **op Meldingsregel toevoegen.**

3. Geef de algemene gegevens op:
    - **Regelnaam:** geef een naam op voor de meldingsregel.
    - **Naam van organisatie opnemen:** geef de klantnaam op die wordt weergegeven in de e-mailmelding.
    - **Tenantspecifieke portalkoppeling opnemen:** hiermee voegt u een koppeling met de tenant-id toe om toegang tot een specifieke tenant toe te staan.
    - **Apparaatgegevens opnemen** : bevat de naam van het apparaat in de instantie voor e-mailmelding.
    
        >[!NOTE]
        > Deze gegevens kunnen worden verwerkt door e-mailservers van geadresseerden die niet op de geografische locatie staan die u hebt geselecteerd voor uw Defender voor eindpuntgegevens.

    - **Apparaten:** kies of geadresseerden moeten worden gewaarschuwd voor waarschuwingen op alle apparaten (alleen globale beheerdersrol) of op geselecteerde apparaatgroepen. Zie Apparaatgroepen maken en beheren voor meer [informatie.](machine-groups.md)
    - **Ernst van waarschuwing:** kies het ernstniveau van de waarschuwing.

4. Klik op **Volgende**.
    
5. Voer het e-mailadres van de geadresseerde in en klik op **Geadresseerde toevoegen.** U kunt meerdere e-mailadressen toevoegen.

6. Controleer of e-mailontvangers de e-mailmeldingen kunnen ontvangen door **Test-e-mail verzenden te selecteren.**

7. Klik **op Meldingsregel opslaan.**

## <a name="edit-a-notification-rule"></a>Een meldingsregel bewerken
1. Selecteer de meldingsregel die u wilt bewerken.

2. Werk de tabbladgegevens Algemeen en Geadresseerde bij.

3. Klik **op Meldingsregel opslaan.**


## <a name="delete-notification-rule"></a>Meldingsregel verwijderen

1. Selecteer de meldingsregel die u wilt verwijderen.

2. Klik op **Verwijderen**.


## <a name="troubleshoot-email-notifications-for-alerts"></a>Problemen met e-mailmeldingen oplossen voor waarschuwingen
In deze sectie worden verschillende problemen vermeld die u kunt tegenkomen bij het gebruik van e-mailmeldingen voor waarschuwingen.

**Probleem:** Beoogde geadresseerden melden dat ze de meldingen niet ontvangen.

**Oplossing:** Zorg ervoor dat de meldingen niet worden geblokkeerd door e-mailfilters:

1. Controleer of de e-mailmeldingen van Defender voor Eindpunt niet naar de map Ongewenste e-mail worden verzonden. Markeer ze als Geen ongewenste e-mail.
2. Controleer of uw e-mailbeveiligingsproduct de e-mailmeldingen van Defender voor Eindpunt niet blokkeert.
3. Controleer de regels voor e-mailtoepassing die mogelijk uw Defender voor endpoint-e-mailmeldingen kunnen vangen en verplaatsen.

## <a name="related-topics"></a>Verwante onderwerpen
- [Instellingen voor gegevensretentie bijwerken](data-retention-settings.md)
- [Geavanceerde functies configureren](advanced-features.md)