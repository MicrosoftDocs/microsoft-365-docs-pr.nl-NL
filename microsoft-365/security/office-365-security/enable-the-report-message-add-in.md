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
description: Meer informatie over het inschakelen van de invoegtoepassing Bericht rapport voor de webversie van Outlook en Outlook, voor individuele gebruikers of uw hele organisatie.
ms.openlocfilehash: 0024e8c87ef6326c1df4547349631c4f1fd4cab8
ms.sourcegitcommit: d929fa32fc2dfb0749fa2420eddbc2251d8489dc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/28/2020
ms.locfileid: "43921574"
---
# <a name="enable-the-report-message-add-in"></a>De invoegtoepassing Bericht rapporteren inschakelen

> [!NOTE]
> Als u een beheerder bent in een organisatie met Exchange Online-postvakken, raden we u aan de portal Inzendingen te gebruiken in het Beveiligings- & Compliance Center. Zie [Het indienen van beheerders gebruiken om vermoedelijke spam, phish, URL's en bestanden in te dienen bij Microsoft.](admin-submission.md)

Met de invoegtoepassing Rapportbericht voor Outlook en Outlook op het web (voorheen Outlook Web App) kunnen mensen eenvoudig valse positieven (goede e-mail gemarkeerd als slecht) of valse negatieven (slechte e-mail toegestaan) melden aan Microsoft en haar gelieerde ondernemingen voor analyse. Microsoft gebruikt deze inzendingen om de effectiviteit van e-mailbeveiligingstechnologieën te verbeteren.

Stel dat mensen veel berichten melden als phishing. Deze informatie wordt weergegeven in het [beveiligingsdashboard](security-dashboard.md) en andere rapporten. Het beveiligingsteam van uw organisatie kan deze informatie gebruiken als een indicatie dat het antiphishingbeleid mogelijk moet worden bijgewerkt. Als mensen veel berichten rapporteren die als ongewenste e-mail zijn gemarkeerd als Niet-ongewenstee e-mail met behulp van de invoegtoepassing Rapportbericht, moet het beveiligingsteam van uw organisatie mogelijk [het antispambeleid](configure-your-spam-filter-policies.md)aanpassen.

Als uw organisatie bovendien [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) of Plan [2](office-365-ti.md)gebruikt, biedt de invoegtoepassing Rapportbericht het beveiligingsteam van uw organisatie nuttige informatie die ze kunnen gebruiken om het beveiligingsbeleid te bekijken en bij te werken.

Beheerders kunnen de invoegtoepassing Rapportbericht voor de organisatie inschakelen en individuele gebruikers kunnen het zelf installeren.

Als u een individuele gebruiker bent, u [de invoegtoepassing Bericht melden voor uzelf inschakelen.](#get-the-report-message-add-in-for-yourself)

Als u een globale beheerder of een Exchange Online-beheerder bent en Exchange is geconfigureerd om OAuth-verificatie te gebruiken, u [de invoegtoepassing Bericht rapport voor uw organisatie inschakelen.](#get-and-enable-the-report-message-add-in-for-your-organization) De invoegtoepassing Rapportbericht is nu beschikbaar via [gecentraliseerde implementatie.](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- De invoegtoepassing Rapportbericht werkt met de meeste Microsoft 365-abonnementen en de volgende producten:

  - De webversie van Outlook
  - Outlook 2013 SP1 of hoger
  - Outlook 2016 voor Mac
  - Outlook opgenomen in Microsoft 365-apps voor Enterprise

- De invoegtoepassing Rapportbericht is momenteel niet beschikbaar voor:

  - Postvakken in on-premises Exchange-organisaties
  - GCC-, GCC HIGH- of DoD-abonnementen

- U configureren dat gerapporteerde berichten worden gekopieerd of doorgestuurd naar een postvak dat u opgeeft. Zie [Een postvak opgeven voor het indienen van spam- en phishingberichten in Office 365 voor](user-submission.md)meer informatie.

- Uw bestaande webbrowser moet werken met de invoegtoepassing Bericht rapporteren. Maar als u merkt dat de invoegtoepassing niet beschikbaar is of niet werkt zoals verwacht, probeert u een andere browser.

- Voor organisatorische installaties moet de organisatie worden geconfigureerd om OAuth-verificatie te gebruiken. Zie [Bepalen of gecentraliseerde implementatie van invoegingen voor uw organisatie werkt](../../admin/manage/centralized-deployment-of-add-ins.md)voor meer informatie.

- Beheerders moeten lid zijn van de rolgroep Globale beheerders. Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

## <a name="get-the-report-message-add-in-for-yourself"></a>De invoegtoepassing Rapportbericht zelf opvragen

1. Ga naar de Microsoft <https://appsource.microsoft.com/marketplace/apps> AppSource bij en zoek naar de invoegtoepassing Bericht rapport. Ga naar <https://appsource.microsoft.com/product/office/wa104381180>.

2. Klik **op NU KRIJGEN.**

   ![Rapportbericht - Nu verzenden](../../media/ReportMessageGETITNOW.png)

3. Bekijk in het dialoogvenster dat wordt weergegeven de gebruiksvoorwaarden en het privacybeleid en klik op **Doorgaan**.

4. Meld u aan met uw werk- of schoolaccount (voor zakelijk gebruik) of uw Microsoft-account (voor persoonlijk gebruik).

Nadat de invoegtoepassing is geïnstalleerd en ingeschakeld, ziet u de volgende pictogrammen:

- In Outlook ziet het pictogram er als volgt uit:

  ![Pictogram Invoegtoepassing Bericht rapporteren voor Outlook](../../media/OutlookReportMessageIcon.png)

- In de webversie van Outlook ziet het pictogram er als volgt uit:

  ![Pictogram Invoegtoepassing Van het webrapportbericht](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

Zie [De invoegtoepassing Rapportbericht gebruiken](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)voor meer informatie over het gebruik van de invoegtoepassing Rapport.

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>De invoegtoepassing Rapportbericht voor uw organisatie opvragen en inschakelen

> [!NOTE]
> Het kan tot 12 uur duren voordat de invoegtoepassing in uw organisatie wordt weergegeven.

1. Ga in het Microsoft 365-beheercentrum naar de pagina <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> **Services &-invoegtoepassing** op , en klik vervolgens op **Invoegtoepassing implementeren**.

   ![Pagina Services en invoegtoepassing in het Microsoft 365-beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. Bekijk de informatie in de flyout Implementeren die wordt weergegeven door een nieuwe flyout voor **invoeging** en klik op **Volgende**.

3. Klik op de volgende pagina op **Kiezen uit de Store**.

   ![Een nieuwe invoegpagina implementeren](../../media/NewAddInScreen2.png)

4. Klik op de **invoegpagina Selecteren** die wordt weergegeven in het vak **Zoeken,** voer **Bericht melden**in en klik vervolgens op Zoekpictogram](../../media/search-icon.png) **zoeken** ![. Zoek in de lijst met resultaten **rapportbericht** en klik op **Toevoegen**.

   ![Invoegzoekresultaten selecteren](../../media/NewAddInScreen3.png)

5. Bekijk in het dialoogvenster dat wordt weergegeven de licentie- en privacygegevens en klik op **Doorgaan**.

6. Configureer de volgende instellingen op de pagina **Invoegpagina configureren** die wordt weergegeven:

   - **Toegewezen gebruikers**: Selecteer een van de volgende waarden:

     - **Iedereen** (standaard)
     - **Specifieke gebruikers /groepen**
     - **Alleen ik**

   - **Implementatiemethode:** Selecteer een van de volgende waarden:

     - **Fixed (Default)**: De invoegtoepassing wordt automatisch geïmplementeerd bij de opgegeven gebruikers en deze kunnen niet worden verwijderd.
     - **Beschikbaar:** Gebruikers kunnen de add-in installeren bij **Home** \> **Get-ins** \> **Admin-managed**.
     - **Optioneel**: de invoegtoepassing wordt automatisch geïmplementeerd bij de opgegeven gebruikers, maar ze kunnen ervoor kiezen om de invoeging te verwijderen.

   ![Invoegpagina configureren](../../media/configure-add-in.png)

   Klik op **Implementeren**als u klaar bent.

7. Op de pagina **Bericht implementeren** dat wordt weergegeven, ziet u een voortgangsrapport gevolgd door een bevestiging dat de invoegtoepassing is geïmplementeerd. Nadat u de informatie hebt gelezen, klikt u op **Volgende**.

   ![Pagina Rapportbericht implementeren](../../media/deploy-report-message-page.png)

8. Bekijk de informatie op de **invoegpagina aankondigen** die wordt weergegeven en klik op **Sluiten**.

   ![Invoegpagina aankondigen](../../media/announce-add-in-page.png)

### <a name="learn-how-to-use-the-report-message-add-in"></a>Meer informatie over het gebruik van de invoegtoepassing Rapportbericht

Mensen die de invoegtoepassing aan hen hebben toegewezen, zien de volgende pictogrammen:

- In Outlook ziet het pictogram er als volgt uit:

  ![Pictogram Invoegtoepassing rapport voor Outlook](../../media/OutlookReportMessageIcon.png)

- In de webversie van Outlook ziet het pictogram er als volgt uit:

  ![Pictogram Invoegtoepassing van het Web-rapportbericht](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

Wanneer u gebruikers op de hoogte stelt van de invoegtoepassing Bericht melden, voegt u een koppeling toe naar [De invoegtoepassing Rapportbericht gebruiken.](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)

### <a name="review-or-edit-settings-for-the-report-message-add-in"></a>Instellingen voor de invoegtoepassing Rapportbericht controleren of bewerken

1. Ga in het Microsoft 365-beheercentrum naar de pagina <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> **Services &-invoegtoepassing** op .

   ![Pagina Services en invoegtoepassing in het nieuwe Microsoft 365-beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. Zoek en selecteer de **invoegtoepassing Rapportbericht.**

3. Bekijk en bewerk de instellingen waar nodig voor uw organisatie in de flyout **Van rapportbericht bewerken** die wordt weergegeven. Klik op **Opslaan** wanneer u gereed bent.

   ![Instellingen voor de invoegtoepassing Rapportbericht](../../media/EditReportMessageAddIn.png)
