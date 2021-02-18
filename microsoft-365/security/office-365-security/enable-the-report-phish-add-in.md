---
title: De invoegsel Phish-rapport inschakelen
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
description: Informatie over het inschakelen van de invoegversie Phishing melden voor Outlook en de webversie van Outlook, voor individuele gebruikers of voor de hele organisatie.
ms.openlocfilehash: 8242f3fcac27f8c76f7bef5a84c70960a204e3bd
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286655"
---
# <a name="enable-the-report-phishing-add-in"></a>De invoegtoepassing Phishing rapporteren inschakelen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Als u een beheerder bent in een Microsoft 365-organisatie met Exchange Online-postvakken, raden we u aan de portal Voorzendingen te gebruiken in het beveiligings- & compliancecentrum. Zie Inzending door beheerders gebruiken om [verdachte spam, phish, URL's](admin-submission.md)en bestanden bij Microsoft in te dienen.

Met de invoegversies Bericht rapporteren en Phishing melden voor Outlook en de webversie van Outlook (voorheen Outlook Web App) kunnen personen eenvoudig fout-positieven (goede e-mail gemarkeerd als slecht) of fout-negatieven (slechte e-mail toegestaan) rapporteren aan Microsoft en haar partners voor analyse.

Microsoft gebruikt deze inzendingen om de effectiviteit van technologieën voor e-mailbeveiliging te verbeteren. Stel dat veel berichten worden verzonden via de invoeging Phishing melden. Deze informatie wordt beschikbaar in het [beveiligingsdashboard](security-dashboard.md) en andere rapporten. Het beveiligingsteam van uw organisatie kan deze informatie gebruiken om aan te geven dat het anti-phishingbeleid mogelijk moet worden bijgewerkt.

U kunt de invoegapp Bericht rapporteren of Phishing melden installeren. Als u wilt dat uw gebruikers zowel spam- als phishingberichten melden, implementeert u de invoegapp Bericht rapporteren in uw organisatie. Zie De [invoegapp Bericht rapporteren inschakelen voor meer informatie.](enable-the-report-message-add-in.md)

De invoegvoegvoeging Phishing melden biedt de optie om alleen phishingberichten te melden. Beheerders kunnen de invoeg versie phishing melden inschakelen voor de organisatie en afzonderlijke gebruikers kunnen deze voor zichzelf installeren.

Als u een individuele gebruiker bent, kunt u de invoeggebruiker [Phishing melden voor uzelf inschakelen.](#get-the-report-phishing-add-in-for-yourself)

Als u een globale beheerder of Een Exchange Online-beheerder bent en Exchange is geconfigureerd voor het gebruik van OAuth-verificatie, kunt u de invoeg toepassing Phishing melden [inschakelen voor uw organisatie.](#get-and-enable-the-report-phishing-add-in-for-your-organization) De melding Phishing-Add-In is nu beschikbaar via [Gecentraliseerde implementatie.](../../admin/manage/centralized-deployment-of-add-ins.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- De invoegvoeging Report Phishing werkt met de meeste Microsoft 365-abonnementen en de volgende producten:

  - Webversie van Outlook
  - Outlook 2013 SP1 of hoger
  - Outlook 2016 voor Mac
  - Outlook inbegrepen in Microsoft 365-apps voor Enterprise
  - Outlook-app voor iOS en Android

- De invoegbox Report Phishing is niet beschikbaar voor postvakken in on-premises Exchange-organisaties.

- U kunt gerapporteerde berichten configureren om te worden gekopieerd of omgeleid naar een postvak dat u opgeeft. Zie Beleidsregels voor [gebruikersinzending voor meer informatie.](user-submission.md)

- Uw bestaande webbrowser moet werken met de invoegonderdeel Phishing melden. Maar als u merkt dat de invoeg mail niet beschikbaar is of niet werkt zoals verwacht, probeer dan een andere browser.

- Voor installaties van de organisatie moet de organisatie worden geconfigureerd voor het gebruik van OAuth-verificatie. Zie Bepalen of [Gecentraliseerde implementatie](../../admin/manage/centralized-deployment-of-add-ins.md)van invoegvoegingen voor uw organisatie werkt voor meer informatie.

- Beheerders moeten lid zijn van de rollengroep globale beheerders. Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

## <a name="get-the-report-phishing-add-in-for-yourself"></a>De invoegvoeg voor Phishing melden voor uzelf

1. Ga naar Microsoft AppSource en zoek naar de invoegapp <https://appsource.microsoft.com/marketplace/apps> Phishing melden.

2. Klik **OP NU KRIJGEN.**

3. Controleer in het dialoogvenster dat wordt weergegeven de gebruiksvoorwaarden en het privacybeleid en klik op **Doorgaan.**

4. Meld u aan met uw werk- of schoolaccount (voor zakelijk gebruik) of uw Microsoft-account (voor persoonlijk gebruik).

Nadat de invoeg toevoegen is geïnstalleerd en ingeschakeld, ziet u de volgende pictogrammen:

- In Outlook ziet het pictogram er zo uit:

  ![Pictogram Phishing-invoeg toevoeg voor Outlook melden](../../media/Outlook-ReportPhishing.png)

- In de webversie van Outlook ziet het pictogram er zo uit:

  ![Pictogram Phishing-invoegversie van Outlook op het web](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a>De invoegvoeging Phishing melden voor uw organisatie in- en inschakelen

> [!NOTE]
> Het kan tot 12 uur duren voordat de invoeg toevoegen in uw organisatie wordt weergegeven.

1. Ga in het Microsoft 365-beheercentrum  naar de pagina \> **Instellingen-invoegvoegingen** op . Als u de pagina Invoeg toevoegen niet ziet, gaat u naar de koppeling Geïntegreerde <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \> **apps-invoeginstellingen**  instellingen boven aan de pagina Geïntegreerde apps.

2. Selecteer **Invoeg toevoegen implementeren** boven aan de pagina en selecteer vervolgens **Volgende.**

   ![Pagina Services en invoegingen in het Microsoft 365-beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. Bekijk **de informatie in de** flyout Een nieuwe invoeg toevoegen implementeren die wordt weergegeven en klik op **Volgende.**

4. Klik op de volgende pagina op **Kiezen uit de Store.**

   ![Een nieuwe invoegpagina implementeren](../../media/NewAddInScreen2.png)

5. Klik op de **pagina Invoeg mail** selecteren  die wordt weergegeven in het  zoekvak, voer **Phishing** melden in en klik vervolgens op ![ het pictogram ](../../media/search-icon.png) Zoeken. Zoek Phishing melden in de lijst **met** resultaten en klik op **Toevoegen.**

6. Controleer in het dialoogvenster dat wordt weergegeven de licentie- en privacygegevens en klik op **Doorgaan.**

7. Configureer de volgende instellingen op de pagina **Invoeg** toevoegen configureren die wordt weergegeven:

   - **Toegewezen gebruikers:** selecteer een van de volgende waarden:

     - **Iedereen** (standaard)
     - **Specifieke gebruikers/groepen**
     - **Alleen ik**

   - **Implementatiemethode:** selecteer een van de volgende waarden:

     - **Opgelost (standaard)**: De invoeg toevoegen wordt automatisch geïmplementeerd voor de opgegeven gebruikers en ze kunnen deze niet verwijderen.
     - **Beschikbaar:** gebruikers kunnen de invoeg invoeg mag installeren in **de Home** \> **Get-invoegvoegingen,** \> **beheerd door de beheerder.**
     - **Optioneel:** De invoegvoeginstelling wordt automatisch geïmplementeerd voor de opgegeven gebruikers, maar ze kunnen ervoor kiezen om deze te verwijderen.

   Klik op Implementeren wanneer u klaar **bent.**

8. Op de **phishing-pagina Rapport** implementeren die wordt weergegeven, ziet u een voortgangsrapport, gevolgd door een bevestiging dat de invoeg mail is geïmplementeerd. Nadat u de informatie hebt gelezen, klikt u op **Volgende.**

9. Controleer de gegevens op de pagina Aankondiging van **de invoeging** die wordt weergegeven en klik op **Sluiten.**

## <a name="learn-how-to-use-the-report-phishing-add-in"></a>Informatie over het gebruik van de invoeg toepassing Phishing melden

Personen aan wie de invoeg toevoeg is toegewezen, zien de volgende pictogrammen:

- In Outlook ziet het pictogram er zo uit:

  ![Pictogram Phishing-invoeg toevoeg voor Outlook melden](../../media/Outlook-ReportPhishing.png)

- In de webversie van Outlook ziet het pictogram er zo uit:

  ![Outlook on the Web Report Phishing Add-in icon](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a>Instellingen voor de phishing-invoeging melden of bewerken

1. Ga in het Microsoft 365-beheercentrum  naar de pagina \> **Instellingen-invoegvoegingen** op . Als u de pagina Invoeg toevoegen niet ziet, gaat u naar de koppeling Geïntegreerde <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \> **apps-invoeginstellingen**  instellingen boven aan de pagina Geïntegreerde apps.

2. Zoek en selecteer de **invoegvoeg voor Phishing** melden.

3. In de **Phishing-flyout Rapport** bewerken die wordt weergegeven, controleert en bewerkt, waar nodig voor uw organisatie. Klik op **Opslaan** wanneer u gereed bent.

## <a name="view-and-review-reported-messages"></a>Gerapporteerde berichten weergeven en controleren

Als u berichten wilt controleren die gebruikers rapporteren bij Microsoft, hebt u deze opties:

- Gebruik de portal Voor het indienen van beheerders. Zie Gebruikersinzendingen voor [Microsoft weergeven voor meer informatie.](admin-submission.md#view-user-submissions-to-microsoft)

- Maak een e-mailstroomregel (ook wel transportregel genoemd) om kopieën van gerapporteerde berichten te verzenden. Zie Regels voor de [e-mailstroom gebruiken om te zien](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)wat uw gebruikers melden bij Microsoft.
