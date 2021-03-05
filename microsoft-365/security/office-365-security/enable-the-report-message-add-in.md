---
title: De invoegtoepassing Bericht rapporteren inschakelen
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
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
description: Informatie over het inschakelen van de invoegversie Bericht rapporteren voor Outlook en de webversie van Outlook, voor individuele gebruikers of voor de hele organisatie.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5eed0fc8905020ea12d3fa6a51c5c8051205b0da
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453751"
---
# <a name="enable-the-report-message-add-in"></a>De invoegtoepassing Bericht rapporteren inschakelen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!NOTE]
> Als u een beheerder bent in een Microsoft 365-organisatie met Exchange Online-postvakken, raden we u aan de portal Voorzendingen te gebruiken in het beveiligings- & compliancecentrum. Zie Inzending door beheerders gebruiken om [verdachte spam, phish, URL's](admin-submission.md)en bestanden bij Microsoft in te dienen.

Met de invoegversies Bericht rapporteren en Phishing rapporteren voor Outlook en de webversie van Outlook (voorheen Outlook Web App) kunnen personen eenvoudig fout-positieven (goede e-mail gemarkeerd als slecht) of fout-negatieven (slechte e-mail toegestaan) rapporteren aan Microsoft en haar partners voor analyse.

Microsoft gebruikt deze inzendingen om de effectiviteit van technologieën voor e-mailbeveiliging te verbeteren. Als personen bijvoorbeeld een groot aantal berichten melden die zijn gemarkeerd als ongewenste [e-mail](configure-your-spam-filter-policies.md)door de invoeging Bericht rapporteren, moet het beveiligingsteam van uw organisatie mogelijk het antispambeleid aanpassen.

U kunt de invoegapp Bericht rapporteren of Phishing melden installeren. Als u wilt dat uw gebruikers alleen phishing-berichten melden, implementeert u de invoeg procenten voor phishing in uw organisatie. Zie [Phishing-invoeging melden](enable-the-report-phish-add-in.md)inschakelen voor meer informatie.

De invoegapp Bericht rapporteren biedt de optie om zowel spam- als phishingberichten te melden. Beheerders kunnen de invoegapp Bericht rapporteren voor de organisatie inschakelen en afzonderlijke gebruikers kunnen deze voor zichzelf installeren.

Als u een individuele gebruiker bent, kunt u [de invoegapp Bericht rapporteren voor uzelf inschakelen.](#get-the-report-message-add-in-for-yourself)

Als u een globale beheerder of een beheerder van Exchange Online bent en Exchange is geconfigureerd voor het gebruik van OAuth-verificatie, kunt u de invoeginstelling Bericht rapporteren [inschakelen voor uw organisatie.](#get-and-enable-the-report-message-add-in-for-your-organization) De rapportmel Add-In dingsmelding is nu beschikbaar via [Gecentraliseerde implementatie.](../../admin/manage/centralized-deployment-of-add-ins.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- De invoegapp Bericht rapporteren werkt met de meeste Microsoft 365-abonnementen en de volgende producten:

  - Webversie van Outlook
  - Outlook 2013 SP1 of hoger
  - Outlook 2016 voor Mac
  - Outlook inbegrepen in Microsoft 365-apps voor Enterprise
  - Outlook-app voor iOS en Android

- De invoegapp Bericht rapporteren is niet beschikbaar voor gedeelde postvakken of postvakken in on-premises Exchange-organisaties.

- U kunt gerapporteerde berichten configureren om te worden gekopieerd of omgeleid naar een postvak dat u opgeeft. Zie Beleidsregels voor [gebruikersinzending voor meer informatie.](user-submission.md)

- Uw bestaande webbrowser moet werken met de invoegapp Bericht rapporteren. Maar als u merkt dat de invoeg mail niet beschikbaar is of niet werkt zoals verwacht, probeer dan een andere browser.

- Voor installaties van de organisatie moet de organisatie worden geconfigureerd voor het gebruik van OAuth-verificatie. Zie Bepalen of [Gecentraliseerde implementatie](../../admin/manage/centralized-deployment-of-add-ins.md)van invoegvoegingen voor uw organisatie werkt voor meer informatie.

- Beheerders moeten lid zijn van de rollengroep globale beheerders. Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

## <a name="get-the-report-message-add-in-for-yourself"></a>De invoegapp Bericht rapporteren voor uzelf op halen

1. Ga naar Microsoft AppSource en zoek naar de <https://appsource.microsoft.com/marketplace/apps> invoegapp Bericht rapporteren. Als u rechtstreeks naar de invoegvoegapp Bericht rapporteren wilt gaan, gaat u naar <https://appsource.microsoft.com/product/office/wa104381180> .

2. Klik **OP NU KRIJGEN.**

   ![Bericht rapporteren - Nu ontvangen](../../media/ReportMessageGETITNOW.png)

3. Controleer in het dialoogvenster dat wordt weergegeven de gebruiksvoorwaarden en het privacybeleid en klik op **Doorgaan.**

4. Meld u aan met uw werk- of schoolaccount (voor zakelijk gebruik) of uw Microsoft-account (voor persoonlijk gebruik).

Nadat de invoeg-invoeging is geïnstalleerd en ingeschakeld, ziet u de volgende pictogrammen:

- In Outlook ziet het pictogram er zo uit:

  ![Pictogram berichtrapport voor Outlook](../../media/OutlookReportMessageIcon.png)

- In de webversie van Outlook ziet het pictogram er zo uit:

  ![Outlook on the web Report Message add-in icon](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

Zie De invoegapp Rapportbericht gebruiken voor meer informatie over het gebruik [van de invoegapp.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>De invoegapp Bericht rapporteren voor uw organisatie in- en uitschakelen

> [!NOTE]
> Het kan tot 12 uur duren voordat de invoeg toevoegen in uw organisatie wordt weergegeven.

1. Ga in het Microsoft 365-beheercentrum  naar de pagina \> **Instellingen-invoegvoegingen** op . Als u de pagina Invoeg toevoegen niet ziet, gaat u naar de koppeling Geïntegreerde <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \> **apps-invoeginstellingen**  instellingen boven aan de pagina Geïntegreerde apps.

2. Selecteer **Invoeg toevoegen implementeren** boven aan de pagina en selecteer vervolgens **Volgende.**

   ![Pagina Services en invoegingen in het Microsoft 365-beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. Bekijk **de informatie in de** flyout Een nieuwe invoeg toevoegen implementeren die wordt weergegeven en klik op **Volgende.**

4. Klik op de volgende pagina op **Kiezen uit de Store.**

   ![Een nieuwe invoegpagina implementeren](../../media/NewAddInScreen2.png)

5. Klik op de **pagina Invoeg** toevoegen selecteren  die wordt weergegeven in het  zoekvak, voer **Rapportbericht** in en klik vervolgens op het ![ pictogram ](../../media/search-icon.png) Zoeken. Zoek in de lijst met resultaten **Bericht rapporteren en** klik op **Toevoegen.**

   ![Zoekresultaten voor invoegingen selecteren](../../media/NewAddInScreen3.png)

6. Controleer in het dialoogvenster dat wordt weergegeven de licentie- en privacygegevens en klik op **Doorgaan.**

7. Configureer de volgende instellingen op de pagina **Invoeg** toevoegen configureren die wordt weergegeven:

   - **Toegewezen gebruikers:** selecteer een van de volgende waarden:

     - **Iedereen** (standaard)
     - **Specifieke gebruikers/groepen**
     - **Alleen ik**

   - **Implementatiemethode:** selecteer een van de volgende waarden:

     - **Opgelost (standaard)**: De invoeg toevoegen wordt automatisch geïmplementeerd voor de opgegeven gebruikers en ze kunnen deze niet verwijderen.
     - **Beschikbaar:** gebruikers kunnen de invoeg mag installeren op **de Home** \> **Get-invoegingen,** \> **beheerd door de beheerder.**
     - **Optioneel:** De invoeg mag automatisch worden geïmplementeerd voor de opgegeven gebruikers, maar ze kunnen ervoor kiezen om deze te verwijderen.

   ![Pagina voor het configureren van invoeginstellingen](../../media/configure-add-in.png)

   Klik op Implementeren wanneer u klaar **bent.**

8. Op de **pagina Rapportbericht** implementeren dat wordt weergegeven, ziet u een voortgangsrapport, gevolgd door een bevestiging dat de invoegapp is geïmplementeerd. Nadat u de informatie hebt gelezen, klikt u op **Volgende.**

   ![Pagina Rapportbericht implementeren](../../media/deploy-report-message-page.png)

9. Controleer de gegevens op de pagina Aankondiging van **de invoegpagina** en klik op **Sluiten.**

   ![Pagina voor aankondigen van invoegvoeging](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a>Informatie over het gebruik van de invoegapp Bericht rapporteren

Personen aan wie de invoeg toevoeg is toegewezen, zien de volgende pictogrammen:

- In Outlook ziet het pictogram er zo uit:

  ![Pictogram berichtmelding rapporteren voor Outlook](../../media/OutlookReportMessageIcon.png)

- In de webversie van Outlook ziet het pictogram er zo uit:

  ![Outlook on the Web Report Message Add-in icon](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

Wanneer u gebruikers op de hoogte stelt van de invoegapp Bericht rapporteren, voegt u een koppeling toe voor het gebruik van de [invoegapp Bericht rapporteren.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>Instellingen voor de invoegapp Bericht rapporteren bekijken of bewerken

1. Ga in het Microsoft 365-beheercentrum  naar de pagina \> **Instellingen-invoegvoegingen** op . Als u de pagina Invoeg toevoegen niet ziet, gaat u naar de koppeling Geïntegreerde <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \> **apps-invoeginstellingen**  instellingen boven aan de pagina Geïntegreerde apps.

   ![Services en Add-Ins in het nieuwe Microsoft 365-beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. Zoek en selecteer de **invoegapp Bericht** rapporteren.

3. Bekijk en **bewerk** de instellingen in de flyout Rapportbericht bewerken die wordt weergegeven voor uw organisatie. Klik op **Opslaan** wanneer u gereed bent.

   ![Instellingen voor de invoegapp Bericht rapporteren](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a>Gerapporteerde berichten weergeven en controleren

Als u berichten wilt bekijken die gebruikers rapporteren bij Microsoft, hebt u deze opties:

- Gebruik de portal Voor het indienen van beheerders. Zie Gebruikersinzendingen voor [Microsoft weergeven voor meer informatie.](admin-submission.md#view-user-submissions-to-microsoft)

- Maak een e-mailstroomregel (ook wel transportregel genoemd) om kopieën van gerapporteerde berichten te verzenden. Zie Regels voor [e-mailstroom gebruiken om te zien wat uw gebruikers melden bij Microsoft.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)
