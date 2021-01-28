---
title: De invoegtoepassing voor het melden van rapporten inschakelen
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Meer informatie over het inschakelen van de invoegtoepassing voor het melden van rapporten voor Outlook en de webversie van Outlook voor afzonderlijke gebruikers of voor de hele organisatie.
ms.openlocfilehash: 6d86fdc710539bc3c74eb94f8931ca48a0c992c1
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029136"
---
# <a name="enable-the-report-phishing-add-in"></a>De invoegtoepassing Phishing rapporteren inschakelen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Als u een beheerder bent van een Microsoft 365-organisatie met postvakken van Exchange Online, raden we u aan om de portal voor ingediende vragen te gebruiken in het beveiligings & nalevings centrum. Zie voor meer informatie [beheer van beheerders gebruiken om verdachte spam, phishing, url's en bestanden naar Microsoft te verzenden](admin-submission.md).

Met de functie voor het melden van e-mailberichten en het rapporteren van phishing-invoegtoepassingen voor Outlook en de webversie van Outlook (voorheen Outlook Web app) kunnen mensen eenvoudig onjuiste positief (goede e-mailberichten als beschadigd) melden

Microsoft gebruikt deze inzendingen om de effectiviteit van de technologieën voor e-mail beveiliging te verbeteren. Stel dat mensen veel berichten rapporteren met behulp van de phishing-invoegtoepassing voor rapporten. Deze informatie vlakken zijn te zien in het [beveiligings dashboard](security-dashboard.md) en andere rapporten. Het beveiligingsteam van uw organisatie kan deze gegevens gebruiken, omdat er mogelijk een anti-phishing beleid moet worden bijgewerkt.

U kunt de invoegtoepassing voor het melden van een bericht of rapport installeren. Als u wilt dat gebruikers zowel spam als phishingberichten kunnen rapporteren, moet u de invoegtoepassing bericht rapporteren in uw organisatie implementeren. Zie [de invoegtoepassing bericht rapporteren inschakelen](enable-the-report-message-add-in.md)voor meer informatie.

De invoegtoepassing voor het melden van rapporten biedt de mogelijkheid alleen phishingberichten te rapporteren. Beheerders kunnen de invoegtoepassing voor het melden van rapporten inschakelen voor de organisatie en afzonderlijke gebruikers kunnen de app voor zichzelf installeren.

Als u een individuele gebruiker bent, kunt u [de invoegtoepassing voor phishing voor uzelf inschakelen](#get-the-report-phishing-add-in-for-yourself).

Als u een globale beheerder of een beheerder van Exchange Online bent en Exchange is geconfigureerd voor gebruik van OAuth-verificatie, kunt u [de invoegtoepassing voor Phishingfilter voor uw organisatie inschakelen](#get-and-enable-the-report-phishing-add-in-for-your-organization). De phishing-Add-In voor het rapport is nu beschikbaar via [gecentraliseerde implementatie](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- De invoegtoepassing voor het melden van rapporten werkt met de meeste Microsoft 365-abonnementen en de volgende producten:

  - De webversie van Outlook
  - Outlook 2013 SP1 of hoger
  - Outlook 2016 voor Mac
  - Outlook inbegrepen in Microsoft 365 apps for Enterprise

- De invoegtoepassing voor het melden van rapporten is niet beschikbaar voor postvakken in on-premises Exchange-organisaties.

- U kunt gerapporteerde berichten configureren voor kopiëren of omleiden naar een door u opgegeven postvak. Zie voor meer informatie [beleidsregels voor gebruikers ingediend](user-submission.md).

- De bestaande webbrowser moet samenwerken met de phishing-invoegtoepassing voor het rapport. Als u merkt dat de invoegtoepassing niet beschikbaar is of niet werkt zoals verwacht, kunt u een andere browser proberen.

- Voor installaties via een organisatie moet de organisatie worden geconfigureerd voor het gebruik van OAuth-verificatie. Zie [bepalen of gecentraliseerde implementatie van invoegtoepassingen werkt voor uw organisatie](../../admin/manage/centralized-deployment-of-add-ins.md)voor meer informatie.

- Beheerders moeten lid zijn van de rollen groep globale beheerders. Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

## <a name="get-the-report-phishing-add-in-for-yourself"></a>De invoegtoepassing voor het melden van rapporten voor uzelf weergeven

1. Ga naar de website van Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> en zoek de invoegtoepassing Phishingfilter.

2. Klik op **Nu kopen**.

3. In het dialoogvenster dat wordt weergegeven, bekijkt u de gebruiksvoorwaarden en het privacybeleid en klikt u vervolgens op **Doorgaan**.

4. Meld u aan met uw werk-of schoolaccount (voor zakelijk gebruik) of uw Microsoft-account (voor persoonlijk gebruik).

Nadat de invoegtoepassing is geïnstalleerd en is ingeschakeld, ziet u de volgende pictogrammen:

- Het pictogram in Outlook ziet er als volgt uit:

  ![Pictogram voor phishing-invoegtoepassing voor Outlook rapporteren](../../media/Outlook-ReportPhishing.png)

- Het pictogram in de webversie van Outlook ziet er zo uit:

  ![Pictogram voor phishing-invoegtoepassing voor Outlook op het web](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a>De invoegtoepassing voor Phishingfilter voor uw organisatie inschakelen en inschakelen

> [!NOTE]
> Het kan 12 uur duren voordat de invoegtoepassing in uw organisatie wordt weergegeven.

1. Ga in het Microsoft 365-Beheercentrum naar de pagina **instellingen** voor \> **invoegtoepassingen** <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> weergeven als u de pagina **met invoegtoepassingen** niet ziet, gaat u naar de link invoegtoepassingen voor de instellingen van de invoegtoepassing voor de **instellingen** op de koppeling naar de \>  \> pagina **met**  geïntegreerde apps.

2. Selecteer **invoegtoepassing implementeren** boven aan de pagina en selecteer **volgende**.

   ![Pagina met Services en invoegtoepassingen in het Microsoft 365-Beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. Controleer de informatie in het vervolgmenu **een nieuwe invoegtoepassing implementeren** die wordt weergegeven en klik op **volgende**.

4. Op de volgende pagina klikt u op **kiezen uit de Store**.

   ![Een nieuwe pagina met invoegtoepassingen implementeren](../../media/NewAddInScreen2.png)

5. Klik op de pagina **invoegtoepassing selecteren** die wordt weergegeven in het vak **zoeken** , typ **phishing melden** en klik vervolgens op **Zoek** ![ actie zoeken ](../../media/search-icon.png) . Zoek in de lijst met resultaten de resultaten van **rapporten** en klik vervolgens op **toevoegen**.

6. In het dialoogvenster dat wordt weergegeven, bekijkt u de licentie-en privacygegevens en klikt u vervolgens op **Doorgaan**.

7. Configureer de volgende instellingen op de pagina **invoegtoepassing configureren** die wordt weergegeven:

   - **Toegewezen gebruikers**: Selecteer een van de volgende waarden:

     - **Iedereen** (standaard)
     - **Specifieke gebruikers/groepen**
     - **Alleen ik**

   - **Implementatiemethode**: Selecteer een van de volgende waarden:

     - **Fixed (standaardinstelling)**: de invoegtoepassing wordt automatisch geïmplementeerd voor de opgegeven gebruikers en kan de invoegtoepassing niet verwijderen.
     - **Beschikbaar**: gebruikers kunnen de invoegtoepassing installeren bij de beheerder van de **Startpagina** \> **invoegtoepassingen** \> **beheren**.
     - **Optioneel**: de invoegtoepassing wordt automatisch geïmplementeerd voor de opgegeven gebruikers, maar ze kunnen de optie wel verwijderen.

   Wanneer u klaar bent, klikt u op **toepassen**.

8. Op de pagina voor het implementeren van een **rapport** dat wordt weergegeven, wordt een voortgangsrapport weergegeven, gevolgd door een bevestiging dat de invoegtoepassing is geïmplementeerd. Nadat u de gegevens hebt gelezen, klikt u op **volgende**.

9. Controleer de gegevens op de pagina **aangekondigde invoegtoepassing** die wordt weergegeven en klik vervolgens op **sluiten**.

## <a name="learn-how-to-use-the-report-phishing-add-in"></a>Meer informatie over het gebruik van de invoegtoepassing voor phishing-rapporten

Voor personen aan wie de invoegtoepassing is toegewezen, worden de volgende pictogrammen weergegeven:

- Het pictogram in Outlook ziet er als volgt uit:

  ![Pictogram voor phishing-invoegtoepassing voor Outlook rapporteren](../../media/Outlook-ReportPhishing.png)

- Het pictogram in de webversie van Outlook ziet er zo uit:

  ![Pictogram voor phishing-invoegtoepassing voor Outlook op het web](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a>Instellingen voor de invoegtoepassing voor het melden van rapporten bekijken of bewerken

1. Ga in het Microsoft 365-Beheercentrum naar de pagina **instellingen** voor \> **invoegtoepassingen** <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> weergeven als u de pagina **met invoegtoepassingen** niet ziet, gaat u naar de link invoegtoepassingen voor de instellingen van de invoegtoepassing voor de **instellingen** op de koppeling naar de \>  \> pagina **met**  geïntegreerde apps.

2. Zoek en selecteer de invoegtoepassing voor het melden van de **phishing** .

3. Ga in het leesvenster voor het **bewerken van rapporten** dat geschikt is voor uw organisatie, naar wens weer en controleer en bewerk de instellingen. Klik op **Opslaan** wanneer u gereed bent.

## <a name="view-and-review-reported-messages"></a>Gerapporteerde berichten weergeven en controleren

Als u berichten wilt weergeven die gebruikers bij Microsoft rapporteren, hebt u de volgende opties:

- Gebruik de portal van de beheerder. Zie voor meer informatie [gebruikers items weergeven in Microsoft](admin-submission.md#view-user-submissions-to-microsoft).

- Maak een e-mail stroom regel (ook wel een transportregel genoemd) om kopieën van gerapporteerde berichten te verzenden. Zie voor instructies [de regels voor e-mail stroom gebruiken om te zien wat uw gebruikers aan Microsoft rapporteren](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).