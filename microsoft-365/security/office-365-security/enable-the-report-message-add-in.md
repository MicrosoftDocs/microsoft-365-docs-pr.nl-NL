---
title: Het rapportbericht of de phishing-invoegvoegingen rapporteren inschakelen
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Meer informatie over het inschakelen van het rapportbericht of de phishing-invoegvoegingen voor Outlook en Outlook op internet, voor individuele gebruikers of voor uw hele organisatie.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dc54c5b74697ac41a1d4ff0818467dba662b31f5
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/10/2021
ms.locfileid: "52295817"
---
# <a name="enable-the-report-message-or-the-report-phishing-add-ins"></a>Het rapportbericht of de phishing-invoegvoegingen rapporteren inschakelen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Als u een beheerder bent in een Microsoft 365 organisatie met Exchange Online postvakken, raden we u aan de portal Inzendingen te gebruiken in het Beveiligings- & Compliancecentrum. Zie Beheerdersinzending gebruiken om [verdachte spam, phish, URL's en](admin-submission.md)bestanden in te dienen bij Microsoft voor meer informatie.

Met de invoegvoegingen Rapportbericht en Phishing melden voor Outlook en Outlook op het web (voorheen bekend als Outlook Web App) kunnen personen eenvoudig onwaar positieven (goede e-mail gemarkeerd als slecht) of onwaar negatieven (slechte e-mail toegestaan) rapporteren aan Microsoft en haar gelieerde bedrijven voor analyse. 

Microsoft gebruikt deze inzendingen om de effectiviteit van e-mailbeveiligingstechnologieën te verbeteren. Stel dat mensen veel berichten rapporteren met de invoeging Phishing melden. Deze informatie wordt in het beveiligingsdashboard en andere rapporten opgedoken. Het beveiligingsteam van uw organisatie kan deze informatie gebruiken als een indicatie dat anti-phishingbeleid mogelijk moet worden bijgewerkt. 

U kunt de invoeging Rapportbericht of Phishing melden installeren. Als u wilt dat uw gebruikers zowel spam- als phishingberichten rapporteren, implementeert u de invoeging Rapportbericht in uw organisatie. Zie De invoegvoegapp Rapportbericht inschakelen voor meer informatie. 

De invoegoptie Rapportbericht biedt de optie om zowel spam- als phishingberichten te rapporteren. Beheerders kunnen de invoeging Rapportbericht voor de organisatie inschakelen en afzonderlijke gebruikers kunnen het zelf installeren. 

De invoegvoegvoegoptie Phishing melden biedt de optie om alleen phishingberichten te rapporteren. Beheerders kunnen de invoeging Phishing melden inschakelen voor de organisatie en afzonderlijke gebruikers kunnen deze zelf installeren. 

Als u een individuele gebruiker bent, kunt u beide invoegvoegingen voor uzelf inschakelen.

f u een globale beheerder of een Exchange Online-beheerder bent en Exchange is geconfigureerd voor het gebruik van OAuth-verificatie, kunt u de invoegvoeging Rapportbericht en de invoeging Phishingrapport voor uw organisatie inschakelen. Beide invoegvoegingen zijn nu beschikbaar via [Gecentraliseerde implementatie.](../../admin/manage/centralized-deployment-of-add-ins.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Zowel de invoeging Rapportbericht als de invoeging Phishing-rapport werkt met de meeste Microsoft 365 en de volgende producten:

  - Outlook op het web
  - Outlook 2013 SP1 of hoger
  - Outlook 2016 voor Mac
  - Outlook opgenomen in Microsoft 365 apps voor Enterprise
  - Outlook app voor iOS en Android

- Beide invoegvakken zijn niet beschikbaar voor gedeelde postvakken of postvakken in on-premises Exchange organisaties.

- Uw bestaande webbrowser moet werken met zowel de invoegvoegingen Rapportbericht als Phishing melden. Maar als u merkt dat de invoegvoeging niet beschikbaar is of niet werkt zoals verwacht, probeert u een andere browser.

- Voor organisatie-installaties moet de organisatie zijn geconfigureerd voor het gebruik van OAuth-verificatie. Zie Bepalen of gecentraliseerde implementatie van invoegvoegingen werkt [voor uw organisatie voor meer informatie.](../../admin/manage/centralized-deployment-of-add-ins.md)

- Beheerders moeten lid zijn van de rollengroep Globale beheerders. Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

- Zie Fout-positieven en onwaar negatieven rapporteren in Outlook voor meer informatie over het rapporteren van een bericht met de [functie Rapportbericht.](report-false-positives-and-false-negatives.md)

## <a name="get-the-report-message-add-in"></a>De invoegvoegvoegvoeging Rapportbericht ontvangen

### <a name="get-the-add-in-for-yourself"></a>De invoeging voor uzelf krijgen

1. Ga naar de Microsoft AppSource bij <https://appsource.microsoft.com/marketplace/apps> en zoek naar de invoeging Rapportbericht. Als u rechtstreeks naar de invoeging Rapportbericht wilt gaan, gaat u naar <https://appsource.microsoft.com/product/office/wa104381180> .

2. Klik **op NU krijgen.**

   ![Rapportbericht - Nu ontvangen](../../media/ReportMessageGETITNOW.png)

3. Bekijk in het dialoogvenster dat wordt weergegeven de gebruiksvoorwaarden en het privacybeleid en klik vervolgens op **Doorgaan.**

4. Meld u aan met uw werk- of schoolaccount (voor zakelijk gebruik) of uw Microsoft-account (voor persoonlijk gebruik).

Nadat de invoegvoegvoeging is geïnstalleerd en ingeschakeld, ziet u de volgende pictogrammen:

- In Outlook ziet het pictogram er als volgende uit:

  > [!div class="mx-imgBorder"]
  > ![Pictogram Berichtrapport voor Outlook](../../media/OutlookReportMessageIcon.png)

- In Outlook op internet ziet het pictogram er als volgende uit:

  > [!div class="mx-imgBorder"]
  > ![Outlook invoegpictogram rapportbericht op het web](../../media/owa-report-message-icon.png)

### <a name="get-the-add-in-for-your-organization"></a>De invoeging voor uw organisatie krijgen

> [!NOTE]
> Het kan tot 12 uur duren voordat de invoegvoeging wordt weergegeven in uw organisatie.

1. Ga in Microsoft 365 beheercentrum naar de pagina  Instellingen \> **invoegingen** op <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> . Als u de invoegpagina niet ziet, gaat u naar de **koppeling** Instellingen geïntegreerde  apps boven aan de pagina Geïntegreerde \>  \>  **apps.**

2. Selecteer **Invoegvoegvoeging implementeren** boven aan de pagina en selecteer vervolgens **Volgende.**

   ![Pagina Services en invoegingen in het Microsoft 365 beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. Controleer de informatie in het **fly-out Nieuwe invoegsel** implementeren dat wordt weergegeven en klik vervolgens op **Volgende.**

4. Klik op de volgende pagina op **Kiezen uit de Store.**

   ![Een nieuwe invoegpagina implementeren](../../media/NewAddInScreen2.png)

5. Klik in het vak Zoeken op de  pagina Selecteer **invoegbericht** dat wordt weergegeven, voer **Rapportbericht** in en klik vervolgens op **zoekpictogram** ![ ](../../media/search-icon.png) . Zoek rapportbericht in de lijst met **resultaten** en klik vervolgens op **Toevoegen.**

   ![Zoekresultaten voor invoegingen selecteren](../../media/NewAddInScreen3.png)

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

   ![Invoegpagina configureren](../../media/configure-add-in.png)

   Wanneer u klaar bent, klikt u op **Implementeren.**

8. Op de **pagina Rapportbericht** implementeren dat wordt weergegeven, ziet u een voortgangsrapport, gevolgd door een bevestiging dat de invoegvoeging is geïmplementeerd. Nadat u de informatie hebt gelezen, klikt u op **Volgende**.

   ![Pagina Rapportbericht implementeren](../../media/deploy-report-message-page.png)

9. Controleer de gegevens op de **pagina Invoeging** aankondigen die wordt weergegeven en klik op **Sluiten.**

   ![Invoegpagina aankondigen](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>Instellingen controleren of bewerken voor de invoegvoegbewerking Rapportbericht

1. Ga in Microsoft 365 beheercentrum naar de pagina  Instellingen \> **invoegingen** op <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> . Als u de invoegpagina niet ziet, gaat u naar de **koppeling** Instellingen geïntegreerde  apps boven aan de pagina Geïntegreerde \>  \>  **apps.**

   ![Services en Add-Ins in het nieuwe Microsoft 365-beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. Zoek en selecteer de **invoeging Rapportbericht.**

3. In het **flyout Rapportbericht bewerken** dat wordt weergegeven, controleert en bewerkt u de instellingen die geschikt zijn voor uw organisatie. Klik op **Opslaan** wanneer u gereed bent.

   ![Instellingen voor de invoeging Rapportbericht](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a>De invoeging Phishing melden

### <a name="get-the-add-in-for-yourself"></a>De invoeging voor uzelf krijgen

1. Ga naar de Microsoft AppSource op <https://appsource.microsoft.com/marketplace/apps> en zoek naar de invoeging Phishing melden.

2. Klik **op NU krijgen.**

3. Bekijk in het dialoogvenster dat wordt weergegeven de gebruiksvoorwaarden en het privacybeleid en klik vervolgens op **Doorgaan.**

4. Meld u aan met uw werk- of schoolaccount (voor zakelijk gebruik) of uw Microsoft-account (voor persoonlijk gebruik).

Nadat de invoegvoegvoeging is geïnstalleerd en ingeschakeld, ziet u de volgende pictogrammen:

- In Outlook ziet het pictogram er als volgende uit:

  ![Pictogram Phishing-invoegvoeging melden voor Outlook](../../media/Outlook-ReportPhishing.png)

- In Outlook op internet ziet het pictogram er als volgende uit:

  > [!div class="mx-imgBorder"]
  > ![Outlook het pictogram Phishing-invoegvoegbericht op het web](../../media/OWA-ReportPhishing.png)

### <a name="get-the-add-in-for-your-organization"></a>De invoeging voor uw organisatie krijgen

> [!NOTE]
> Het kan tot 12 uur duren voordat de invoegvoeging wordt weergegeven in uw organisatie.

1. Ga in Microsoft 365 beheercentrum naar de pagina  Instellingen \> **invoegingen** op <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> . Als u de invoegpagina niet ziet, gaat u naar de **koppeling** Instellingen geïntegreerde  apps boven aan de pagina Geïntegreerde \>  \>  **apps.**

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

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a>Instellingen controleren of bewerken voor de invoeging Phishingrapport

1. Ga in Microsoft 365 beheercentrum naar de pagina  Instellingen \> **invoegingen** op <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> . Als u de invoegpagina niet ziet, gaat u naar de **koppeling** Instellingen geïntegreerde  apps boven aan de pagina Geïntegreerde \>  \>  **apps.**

2. Zoek en selecteer de **invoeging Phishing** melden.

3. In het **flyout Rapport phishing bewerken** dat de instellingen voor uw organisatie wordt weergegeven, controleren en bewerken. Klik op **Opslaan** wanneer u gereed bent.
