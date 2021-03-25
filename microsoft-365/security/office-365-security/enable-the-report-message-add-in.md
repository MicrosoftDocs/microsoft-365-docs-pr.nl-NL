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
description: Meer informatie over het inschakelen van de invoegversie van rapportbericht voor de webversie van Outlook en Outlook, voor individuele gebruikers of uw hele organisatie.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4e85af902eaaa41eb82acf8d4b4baedc538e7888
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204044"
---
# <a name="enable-the-report-message-add-in"></a>De invoegtoepassing Bericht rapporteren inschakelen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Als u een beheerder bent in een Microsoft 365-organisatie met Exchange Online-postvakken, raden we u aan de portal Inzendingen te gebruiken in het Beveiligings- & Compliancecentrum. Zie Beheerdersinzending gebruiken om [verdachte spam, phish, URL's en](admin-submission.md)bestanden in te dienen bij Microsoft voor meer informatie.

Met de invoegvoegingen Rapportbericht en Rapport phishing voor de webversie van Outlook en Outlook (voorheen Bekend als Outlook Web App) kunnen personen eenvoudig onwaar-positieven (goede e-mail die als slecht is gemarkeerd) of onwaar negatieven (slechte e-mail toegestaan) rapporteren aan Microsoft en haar gelieerde bedrijven voor analyse.

Microsoft gebruikt deze inzendingen om de effectiviteit van e-mailbeveiligingstechnologieën te verbeteren. Als mensen bijvoorbeeld een groot aantal berichten rapporteren die als ongewenste e-mail zijn gemarkeerd als Geen ongewenste [e-mail](configure-your-spam-filter-policies.md)met behulp van de invoegmap Rapportbericht, moet het beveiligingsteam van uw organisatie mogelijk antispambeleid aanpassen.

U kunt de invoeging Rapportbericht of Phishing melden installeren. Als u wilt dat uw gebruikers alleen phishingberichten rapporteren, implementeert u de invoeging Phishing melden in uw organisatie. Zie De [invoeging Phishing melden inschakelen voor meer informatie.](enable-the-report-phish-add-in.md)

De invoegoptie Rapportbericht biedt de optie om zowel spam- als phishingberichten te rapporteren. Beheerders kunnen de invoeging Rapportbericht voor de organisatie inschakelen en afzonderlijke gebruikers kunnen het zelf installeren.

Als u een individuele gebruiker bent, kunt u de invoeging [Rapportbericht voor uzelf inschakelen.](#get-the-report-message-add-in-for-yourself)

Als u een globale beheerder of een Exchange Online-beheerder bent en Exchange is geconfigureerd voor het gebruik van OAuth-verificatie, kunt u de invoegvoeging [Rapportbericht inschakelen voor uw organisatie.](#get-and-enable-the-report-message-add-in-for-your-organization) Het rapportbericht Add-In is nu beschikbaar via [Gecentraliseerde implementatie.](../../admin/manage/centralized-deployment-of-add-ins.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- De invoegvoegapp Rapportbericht werkt met de meeste Microsoft 365-abonnementen en de volgende producten:

  - De webversie van Outlook
  - Outlook 2013 SP1 of hoger
  - Outlook 2016 voor Mac
  - Outlook inbegrepen bij Microsoft 365-apps voor Enterprise
  - Outlook-app voor iOS en Android

- De invoeging Rapportbericht is niet beschikbaar voor gedeelde postvakken of postvakken in on-premises Exchange-organisaties.

- U kunt gerapporteerde berichten zo configureren dat ze worden gekopieerd of omgeleid naar een postvak dat u opgeeft. Zie Beleidsregels voor [gebruikersinzendingen voor meer informatie.](user-submission.md)

- Uw bestaande webbrowser moet werken met de invoeging Rapportbericht. Maar als u merkt dat de invoegvoeging niet beschikbaar is of niet werkt zoals verwacht, probeert u een andere browser.

- Voor organisatie-installaties moet de organisatie zijn geconfigureerd voor het gebruik van OAuth-verificatie. Zie Bepalen of gecentraliseerde implementatie van invoegvoegingen werkt [voor uw organisatie voor meer informatie.](../../admin/manage/centralized-deployment-of-add-ins.md)

- Beheerders moeten lid zijn van de rollengroep Globale beheerders. Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

## <a name="get-the-report-message-add-in-for-yourself"></a>De invoeging Rapportbericht voor uzelf krijgen

1. Ga naar de Microsoft AppSource bij <https://appsource.microsoft.com/marketplace/apps> en zoek naar de invoeging Rapportbericht. Als u rechtstreeks naar de invoeging Rapportbericht wilt gaan, gaat u naar <https://appsource.microsoft.com/product/office/wa104381180> .

2. Klik **op NU krijgen.**

   ![Rapportbericht - Nu ontvangen](../../media/ReportMessageGETITNOW.png)

3. Bekijk in het dialoogvenster dat wordt weergegeven de gebruiksvoorwaarden en het privacybeleid en klik vervolgens op **Doorgaan.**

4. Meld u aan met uw werk- of schoolaccount (voor zakelijk gebruik) of uw Microsoft-account (voor persoonlijk gebruik).

Nadat de invoegvoegvoeging is geïnstalleerd en ingeschakeld, ziet u de volgende pictogrammen:

- In Outlook ziet het pictogram er als volgende uit:

  ![Pictogram Berichtrapport voor Outlook](../../media/OutlookReportMessageIcon.png)

- In de webversie van Outlook ziet het pictogram er als volgende uit:

  ![Pictogram Rapportbericht van Outlook op het web](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

Zie De invoeging Rapportbericht gebruiken voor meer informatie over het gebruik van [de invoeging.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>De invoeging Rapportbericht voor uw organisatie ontvangen en inschakelen

> [!NOTE]
> Het kan tot 12 uur duren voordat de invoegvoeging wordt weergegeven in uw organisatie.

1. Ga in het Microsoft 365-beheercentrum  naar de pagina Instellingen invoegvoegingen op , Als u de invoegpagina niet ziet, gaat u naar de koppeling Geïntegreerde \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \> **apps-invoeginstellingen**  boven aan de pagina Geïntegreerde apps.

2. Selecteer **Invoegvoegvoeging implementeren** boven aan de pagina en selecteer vervolgens **Volgende.**

   ![Pagina Services en invoegvoegingen in het Microsoft 365-beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

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

## <a name="learn-how-to-use-the-report-message-add-in"></a>Meer informatie over het gebruik van de invoeging Rapportbericht

Personen aan wie de invoegvoeging is toegewezen, zien de volgende pictogrammen:

- In Outlook ziet het pictogram er als volgende uit:

  ![Pictogram Berichtrapport voor Outlook](../../media/OutlookReportMessageIcon.png)

- In de webversie van Outlook ziet het pictogram er als volgende uit:

  ![Pictogram Bericht van outlook op het webrapport](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

Wanneer u gebruikers op de hoogte stelt van de invoegvoegapp Rapportbericht, voegt u een koppeling toe aan De invoeging [Rapportbericht gebruiken.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>Instellingen controleren of bewerken voor de invoegvoegbewerking Rapportbericht

1. Ga in het Microsoft 365-beheercentrum  naar de pagina Instellingen invoegvoegingen op , Als u de invoegpagina niet ziet, gaat u naar de koppeling Geïntegreerde \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \> **apps-invoeginstellingen**  boven aan de pagina Geïntegreerde apps.

   ![Services en Add-Ins in het nieuwe Microsoft 365-beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. Zoek en selecteer de **invoeging Rapportbericht.**

3. In het **flyout Rapportbericht bewerken** dat wordt weergegeven, controleert en bewerkt u de instellingen die geschikt zijn voor uw organisatie. Klik op **Opslaan** wanneer u gereed bent.

   ![Instellingen voor de invoeging Rapportbericht](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a>Gerapporteerde berichten weergeven en controleren

Als u berichten wilt bekijken die gebruikers rapporteren aan Microsoft, hebt u de volgende opties:

- Gebruik de portal Beheerdersinzendingen. Zie Gebruikersinzendingen [weergeven bij Microsoft voor meer informatie.](admin-submission.md#view-user-submissions-to-microsoft)

- Maak een regel voor de e-mailstroom (ook wel transportregel genoemd) om kopieën van gerapporteerde berichten te verzenden. Zie Regels voor [e-mailstroom gebruiken voor](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)instructies om te zien wat uw gebruikers rapporteren aan Microsoft.
