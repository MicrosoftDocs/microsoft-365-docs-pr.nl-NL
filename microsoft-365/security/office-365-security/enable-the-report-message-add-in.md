---
title: De invoegtoepassing Bericht rapporteren inschakelen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Meer informatie over het inschakelen van de invoegtoepassing Report Message voor Outlook en Outlook op de web, voor individuele gebruikers of uw hele organisatie.
ms.openlocfilehash: 2b074d1bd260f5c95d138577e259aee14ec9e8d7
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430505"
---
# <a name="enable-the-report-message-add-in"></a>De invoegtoepassing Bericht rapporteren inschakelen

> [!NOTE]
> Als u een beheerder bent in een Microsoft 365-organisatie met Exchange Online-postvakken, raden we u aan de portal Inzendingen te gebruiken in het Security & Compliance Center. Zie [Beheerdersinzending gebruiken om vermoedelijke spam, phish, URL's en bestanden in te dienen bij Microsoft.](admin-submission.md)

Met de invoegtoepassing Report Message voor Outlook en Outlook op het web (voorheen Bekend als Outlook Web App) kunnen mensen eenvoudig fout-positieven (goede e-mail gemarkeerd als slecht) of valse negatieven (slechte e-mail toegestaan) melden aan Microsoft en haar gelieerde ondernemingen voor analyse. Microsoft gebruikt deze inzendingen om de effectiviteit van e-mailbeveiligingstechnologieën te verbeteren.

Stel dat mensen veel berichten melden als phishing. Deze informatie duikt op in het [beveiligingsdashboard](security-dashboard.md) en andere rapporten. Het beveiligingsteam van uw organisatie kan deze informatie gebruiken als een indicatie dat het beleid voor antiphishing mogelijk moet worden bijgewerkt. Of als mensen veel berichten rapporteren die zijn gemarkeerd als ongewenste e-mail als Niet ongewenste e-mail met behulp van de invoegtoepassing Rapportbericht, moet het beveiligingsteam van uw organisatie mogelijk [het antispambeleid](configure-your-spam-filter-policies.md)aanpassen.

Als uw organisatie bovendien [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) of [Plan 2](office-365-ti.md)gebruikt, biedt de invoegtoepassing Rapportbericht het beveiligingsteam van uw organisatie nuttige informatie die ze kunnen gebruiken om beveiligingsbeleid te controleren en bij te werken.

Beheerders kunnen de invoegtoepassing Report Message voor de organisatie inschakelen en individuele gebruikers kunnen het zelf installeren.

Als u een individuele gebruiker bent, u [de invoegtoepassing Report Message zelf inschakelen.](#get-the-report-message-add-in-for-yourself)

Als u een globale beheerder of een Exchange Online-beheerder bent en Exchange is geconfigureerd om OAuth-verificatie te gebruiken, u [de invoegtoepassing Rapportbericht voor uw organisatie inschakelen.](#get-and-enable-the-report-message-add-in-for-your-organization) De invoegtoepassing Rapportberichten is nu beschikbaar via [gecentraliseerde implementatie.](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- De invoegtoepassing Report Message werkt met de meeste Microsoft 365-abonnementen en de volgende producten:

  - Webversie van Outlook
  - SP1 2013 of hoger
  - Outlook 2016 voor Mac
  - Outlook inbegrepen bij Microsoft 365-apps voor Enterprise

- De invoegtoepassing Rapportbericht is niet beschikbaar voor postvakken in on-premises Exchange-organisaties.

- U gerapporteerde berichten configureren die moeten worden gekopieerd of doorgestuurd naar een postvak dat u opgeeft. Zie [Een postvak opgeven voor gebruikersinzendingen van spam- en phishingberichten in Exchange Online](user-submission.md)voor meer informatie.

- Uw bestaande webbrowser moet werken met de invoegtoepassing Rapportbericht. Maar als u merkt dat de invoegtoepassing niet beschikbaar is of niet werkt zoals verwacht, probeer dan een andere browser.

- Voor organisatorische installaties moet de organisatie worden geconfigureerd om OAuth-verificatie te gebruiken. Zie [Bepalen of Gecentraliseerde implementatie van invoegtoepassingen werkt voor uw organisatie voor](../../admin/manage/centralized-deployment-of-add-ins.md)meer informatie.

- Beheerders moeten lid zijn van de rolgroep Globale beheerders. Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

## <a name="get-the-report-message-add-in-for-yourself"></a>De invoegtoepassing Rapportbericht voor uzelf ophalen

1. Ga naar de Microsoft AppSource bij <https://appsource.microsoft.com/marketplace/apps> en zoek naar de invoegtoepassing Rapportbericht. Ga naar <https://appsource.microsoft.com/product/office/wa104381180> .

2. Klik **op NU ophalen.**

   ![Bericht melden - Nu ophalen](../../media/ReportMessageGETITNOW.png)

3. Bekijk in het dialoogvenster dat wordt weergegeven de gebruiksvoorwaarden en het privacybeleid en klik op **Doorgaan**.

4. Meld u aan met uw werk- of schoolaccount (voor zakelijk gebruik) of uw Microsoft-account (voor persoonlijk gebruik).

Nadat de invoegtoepassing is geïnstalleerd en is ingeschakeld, ziet u de volgende pictogrammen:

- In Outlook ziet het pictogram er als volgt uit:

  ![Invoegpictogram Bericht rapporteren voor Outlook](../../media/OutlookReportMessageIcon.png)

- In de webversie van Outlook ziet het pictogram er als volgt uit:

  ![Invoegpictogram webbericht rapporteren](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

Zie De invoegtoepassing Rapportbericht gebruiken voor meer informatie over het gebruik van [de invoegtoepassing](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>De invoegtoepassing Rapportbericht voor uw organisatie ophalen en inschakelen

> [!NOTE]
> Het kan tot 12 uur duren voordat de invoegtoepassing in uw organisatie wordt weergegeven.

1. Ga in het Microsoft 365-beheercentrum naar de pagina **Services & invoegtoepassingen** op <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> en klik vervolgens op **Invoegtoepassing implementeren**.

   ![Pagina Services en invoegtoepassingen in het Microsoft 365-beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. Bekijk de informatie in de **flyout Voor de invoegtoepassing implementeren** die wordt weergegeven en controleer de informatie en klik vervolgens op **Volgende**.

3. Klik op de volgende pagina op **Kiezen uit de Winkel**.

   ![Een nieuwe invoegpagina implementeren](../../media/NewAddInScreen2.png)

4. Klik op de **invoegtoepassingspagina selecteren** die wordt weergegeven in het vak **Zoeken,** voer **Rapportbericht**in en **klik** vervolgens op ![ Zoekzoeken. ](../../media/search-icon.png) Zoek **rapportbericht** in de lijst met resultaten en klik vervolgens op **Toevoegen**.

   ![Invoegtoepassingszoeken selecteren](../../media/NewAddInScreen3.png)

5. Bekijk in het dialoogvenster dat wordt weergegeven de licentie- en privacygegevens en klik op **Doorgaan**.

6. Configureer de volgende instellingen op de **invoegpagina configureren** die wordt weergegeven:

   - **Toegewezen gebruikers**: Selecteer een van de volgende waarden:

     - **Iedereen** (standaard)
     - **Specifieke gebruikers/groepen**
     - **Alleen ik**

   - **Implementatiemethode**: Selecteer een van de volgende waarden:

     - **Opgelost (Standaard)**: De invoegtoepassing wordt automatisch geïmplementeerd voor de opgegeven gebruikers en deze kan deze niet verwijderen.
     - **Beschikbaar**: Gebruikers kunnen de invoegtoepassing **thuis** \> **installeren Door invoegtoepassingen** \> **beheerde beheerder.**
     - **Optioneel**: De invoegtoepassing wordt automatisch geïmplementeerd voor de opgegeven gebruikers, maar ze kunnen ervoor kiezen deze te verwijderen.

   ![Invoegpagina configureren](../../media/configure-add-in.png)

   Klik op **Implementeren**als u klaar bent.

7. Op de pagina **Rapportbericht implementeren** dat wordt weergegeven, ziet u een voortgangsrapport, gevolgd door een bevestiging dat de invoegtoepassing is geïmplementeerd. Nadat u de informatie hebt gelezen, klikt u op **Volgende**.

   ![Pagina Rapportbericht implementeren](../../media/deploy-report-message-page.png)

8. Bekijk de informatie op de **invoegtoepassingspagina aankondigen** en klik vervolgens op **Sluiten**.

   ![Invoegpagina aankondigen](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a>Meer informatie over het gebruik van de invoegtoepassing Rapportbericht

Mensen die de invoegtoepassing aan hen hebben toegewezen, zien de volgende pictogrammen:

- In Outlook ziet het pictogram er als volgt uit:

  ![Pictogram Invoegtoepassing rapportbericht voor Outlook](../../media/OutlookReportMessageIcon.png)

- In de webversie van Outlook ziet het pictogram er als volgt uit:

  ![Invoegtoepassingspictogram Webrapportbericht](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

Wanneer u gebruikers op de hoogte stelt van de invoegtoepassing Rapportbericht, voegt u een koppeling toe naar [De invoegtoepassing Rapportbericht](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)gebruiken .

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>Instellingen voor de invoegtoepassing Rapportbericht controleren of bewerken

1. Ga in het Microsoft 365-beheercentrum naar de pagina **Services &-invoegtoepassingen** op <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> .

   ![Pagina Services en invoegtoepassingen in het nieuwe Microsoft 365-beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. Zoek en selecteer de invoegtoepassing **Rapportbericht.**

3. Controleer en bewerk instellingen in de flyout **Rapportbericht bewerken** die wordt weergegeven, en bewerk deze zo geschikt voor uw organisatie. Klik op **Opslaan** wanneer u gereed bent.

   ![Instellingen voor de invoegtoepassing Rapportbericht](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a>Gerapporteerde berichten bekijken en bekijken

Als u berichten wilt bekijken die gebruikers aan Microsoft rapporteren, hebt u de volgende opties:

- Gebruik de portal Beheerdersinzendingen. [Zie Gebruikersinzendingen weergeven bij Microsoft](admin-submission.md#view-user-submissions-to-microsoft)voor meer informatie.

- Maak een e-mailstroomregel (ook wel een transportregel genoemd) om kopieën van gerapporteerde berichten te verzenden. Zie Regels [voor e-mailstromen gebruiken om te zien wat uw gebruikers aan Microsoft rapporteren](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)voor instructies.
