---
title: De phish-invoeging rapport inschakelen
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
description: Meer informatie over het inschakelen van de invoeging Phishing melden voor Outlook en Outlook op internet, voor individuele gebruikers of uw hele organisatie.
ms.openlocfilehash: 44fa55a82462de336982d3af2e3996c14699fd7c
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625387"
---
# <a name="enable-the-report-phishing-add-in"></a>De invoegtoepassing Phishing rapporteren inschakelen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Als u een beheerder bent in een Microsoft 365 organisatie met Exchange Online postvakken, raden we u aan de portal Inzendingen te gebruiken in het Beveiligings- & Compliancecentrum. Zie Beheerdersinzending gebruiken om [verdachte spam, phish, URL's en](admin-submission.md)bestanden in te dienen bij Microsoft voor meer informatie.

Met de invoegvoegingen Rapportbericht en Phishing melden voor Outlook en Outlook op het web (voorheen bekend als Outlook Web App) kunnen personen eenvoudig onwaar positieven (goede e-mail gemarkeerd als slecht) of onwaar negatieven (slechte e-mail toegestaan) rapporteren aan Microsoft en haar gelieerde bedrijven voor analyse.

Microsoft gebruikt deze inzendingen om de effectiviteit van e-mailbeveiligingstechnologieën te verbeteren. Stel dat mensen veel berichten rapporteren met de invoeging Phishing melden. Deze informatie wordt in het [beveiligingsdashboard en](security-dashboard.md) andere rapporten opgedoken. Het beveiligingsteam van uw organisatie kan deze informatie gebruiken als een indicatie dat anti-phishingbeleid mogelijk moet worden bijgewerkt.

U kunt de invoeging Rapportbericht of Phishing melden installeren. Als u wilt dat uw gebruikers zowel spam- als phishingberichten rapporteren, implementeert u de invoeging Rapportbericht in uw organisatie. Zie De [invoegvoegapp Rapportbericht inschakelen voor meer informatie.](enable-the-report-message-add-in.md)

De invoegvoegvoegoptie Phishing melden biedt de optie om alleen phishingberichten te rapporteren. Beheerders kunnen de invoeging Phishing melden inschakelen voor de organisatie en afzonderlijke gebruikers kunnen deze zelf installeren.

Als u een individuele gebruiker bent, kunt u de invoeging [Phishing melden voor uzelf inschakelen.](#get-the-report-phishing-add-in-for-yourself)

Als u een globale beheerder of een Exchange Online-beheerder bent en Exchange is geconfigureerd voor het gebruik van OAuth-verificatie, kunt u de invoegvoeginstelling Phishingrapport voor uw organisatie [inschakelen.](#get-and-enable-the-report-phishing-add-in-for-your-organization) De phishing-Add-In rapport is nu beschikbaar via [Gecentraliseerde implementatie.](../../admin/manage/centralized-deployment-of-add-ins.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- De invoeging Report Phishing werkt met de meeste Microsoft 365 en de volgende producten:

  - Webversie van Outlook
  - Outlook 2013 SP1 of hoger
  - Outlook 2016 voor Mac of hoger
  - Outlook opgenomen in Microsoft 365 apps voor Enterprise
  - Outlook app voor iOS en Android

- De invoeging Phishing melden is niet beschikbaar voor gedeelde postvakken of postvakken in on-premises Exchange organisaties.

- U kunt gerapporteerde berichten zo configureren dat ze worden gekopieerd of omgeleid naar een postvak dat u opgeeft. Zie Beleidsregels voor [gebruikersinzendingen voor meer informatie.](user-submission.md)

- Uw bestaande webbrowser moet werken met de invoeging Phishing melden. Maar als u merkt dat de invoegvoeging niet beschikbaar is of niet werkt zoals verwacht, probeert u een andere browser.

- Voor organisatie-installaties moet de organisatie zijn geconfigureerd voor het gebruik van OAuth-verificatie. Zie Bepalen of gecentraliseerde implementatie van invoegvoegingen werkt [voor uw organisatie voor meer informatie.](../../admin/manage/centralized-deployment-of-add-ins.md)

- Beheerders moeten lid zijn van de rollengroep Globale beheerders. Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

## <a name="get-the-report-phishing-add-in-for-yourself"></a>De invoeging Report Phishing voor uzelf krijgen

1. Ga naar de Microsoft AppSource op <https://appsource.microsoft.com/marketplace/apps> en zoek naar de invoeging Phishing melden.

2. Klik **op NU krijgen.**

3. Bekijk in het dialoogvenster dat wordt weergegeven de gebruiksvoorwaarden en het privacybeleid en klik vervolgens op **Doorgaan.**

4. Meld u aan met uw werk- of schoolaccount (voor zakelijk gebruik) of uw Microsoft-account (voor persoonlijk gebruik).

Nadat de invoegvoegvoeging is geïnstalleerd en ingeschakeld, ziet u de volgende pictogrammen:

- In Outlook ziet het pictogram er als volgende uit:

  ![Pictogram Phishing-invoegvoeging melden voor Outlook](../../media/Outlook-ReportPhishing.png)

- In Outlook op internet ziet het pictogram er als volgende uit:

  ![Outlook het pictogram Phishing-invoegvoegbericht op het web](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a>De invoeging Phishingrapport voor uw organisatie inschakelen en inschakelen

> [!NOTE]
> Het kan tot 12 uur duren voordat de invoegvoeging wordt weergegeven in uw organisatie.

1. Ga in het Microsoft 365-beheercentrum naar de pagina **Instellingen-invoegvoegingen** op , Als u de invoegpagina niet ziet, gaat u naar de koppeling Instellingen Geïntegreerde apps invoegvoegingen boven aan de pagina Geïntegreerde \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \>  **apps.**

2. Selecteer **Invoegvoegvoeging implementeren** boven aan de pagina en selecteer vervolgens **Volgende.**

   ![Pagina Services en invoegingen in het Microsoft 365 beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. Controleer de informatie in het **fly-out Nieuwe invoegsel** implementeren dat wordt weergegeven en klik vervolgens op **Volgende.**

4. Klik op de volgende pagina op **Kiezen uit de Store.**

   ![Een nieuwe invoegpagina implementeren](../../media/NewAddInScreen2.png)

5. Klik in het vak Zoeken op de  **pagina** Invoeg toevoegen selecteren die wordt weergegeven, voer **Rapport phishing** in en klik vervolgens op **zoekpictogram** ![ ](../../media/search-icon.png) . Zoek in de lijst met resultaten **naar Rapport phishing** en klik vervolgens op **Toevoegen.**

6. Controleer in het dialoogvenster dat wordt weergegeven de licentie- en privacygegevens en klik vervolgens op **Doorgaan.**

7. Configureer de volgende instellingen op de **pagina Invoeging** configureren die wordt weergegeven:

   - **Toegewezen gebruikers:** Selecteer een van de volgende waarden:

     - **Iedereen** (standaard)
     - **Specifieke gebruikers/groepen**
     - **Alleen ik**

   - **Implementatiemethode:** Selecteer een van de volgende waarden:

     - **Opgelost (standaard)**: De invoeging wordt automatisch geïmplementeerd voor de opgegeven gebruikers en kan niet worden verwijderd.
     - **Beschikbaar:** Gebruikers kunnen de invoegvoeging installeren bij **Home** \> **Get-invoegvoegingen** beheerd door \> **beheerder.**
     - **Optioneel:** De invoeging wordt automatisch geïmplementeerd voor de opgegeven gebruikers, maar ze kunnen ervoor kiezen deze te verwijderen.

   Wanneer u klaar bent, klikt u op **Implementeren.**

8. Op de **pagina Rapport phishing implementeren** dat wordt weergegeven, ziet u een voortgangsrapport, gevolgd door een bevestiging dat de invoeging is geïmplementeerd. Nadat u de informatie hebt gelezen, klikt u op **Volgende**.

9. Controleer de gegevens op de **pagina Invoeging** aankondigen die wordt weergegeven en klik op **Sluiten.**

## <a name="learn-how-to-use-the-report-phishing-add-in"></a>Meer informatie over het gebruik van de invoeging Phishing melden

Personen aan wie de invoegvoeging is toegewezen, zien de volgende pictogrammen:

- In Outlook ziet het pictogram er als volgende uit:

  ![Pictogram Phishing-invoegvoeging melden voor Outlook](../../media/Outlook-ReportPhishing.png)

- In Outlook op internet ziet het pictogram er als volgende uit:

  ![Outlook invoegpictogram Phishing in het webrapport](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a>Instellingen controleren of bewerken voor de invoeging Phishingrapport

1. Ga in het Microsoft 365-beheercentrum naar de pagina **Instellingen-invoegvoegingen** op , Als u de invoegpagina niet ziet, gaat u naar de koppeling Instellingen Geïntegreerde apps invoegvoegingen boven aan de pagina Geïntegreerde \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \>  **apps.**

2. Zoek en selecteer de **invoeging Phishing** melden.

3. In het **flyout Rapport phishing bewerken** dat de instellingen voor uw organisatie wordt weergegeven, controleren en bewerken. Klik op **Opslaan** wanneer u gereed bent.

## <a name="view-and-review-reported-messages"></a>Gerapporteerde berichten weergeven en controleren

Als u berichten wilt bekijken die gebruikers rapporteren aan Microsoft, hebt u de volgende opties:

- Gebruik de portal Beheerdersinzendingen. Zie Gebruikersinzendingen [weergeven bij Microsoft voor meer informatie.](admin-submission.md#view-user-submissions-to-microsoft)

- Maak een regel voor de e-mailstroom (ook wel transportregel genoemd) om kopieën van gerapporteerde berichten te verzenden. Zie Regels voor [e-mailstroom gebruiken voor](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)instructies om te zien wat gebruikers rapporteren aan Microsoft.
