---
title: De invoegtoepassing Bericht rapporteren inschakelen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
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
description: Meer informatie over het inschakelen van de invoegtoepassing bericht rapporteren voor Outlook en de webversie van Outlook voor afzonderlijke gebruikers of voor de hele organisatie.
ms.openlocfilehash: d760aa5d58e628872682131efae9d9c3b3c46734
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842450"
---
# <a name="enable-the-report-message-add-in"></a>De invoegtoepassing Bericht rapporteren inschakelen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Als u een beheerder bent van een Microsoft 365-organisatie met postvakken van Exchange Online, raden we u aan om de portal voor ingediende vragen te gebruiken in het beveiligings & nalevings centrum. Zie voor meer informatie [beheer van beheerders gebruiken om verdachte spam, phishing, url's en bestanden naar Microsoft te verzenden](admin-submission.md).

Met de invoegtoepassing bericht rapporteren voor Outlook en de webversie van Outlook (voorheen Outlook Web app) kunnen gebruikers eenvoudig onjuiste positieven melden (goede e-mailberichten die als beschadigd zijn gemarkeerd) of fout-negatieven (onjuiste e-mail toegestaan) aan Microsoft en zijn gelieerde ondernemingen voor analyse. Microsoft gebruikt deze inzendingen om de effectiviteit van de technologieën voor e-mail beveiliging te verbeteren.

Stel dat personen een heleboel berichten als phishing rapporteren. Deze informatie vlakken zijn te zien in het [beveiligings dashboard](security-dashboard.md) en andere rapporten. Het beveiligingsteam van uw organisatie kan deze gegevens gebruiken, omdat er mogelijk een anti-phishing beleid moet worden bijgewerkt. Of als personen een heleboel berichten rapporteren die als ongewenste e-mail zijn gemarkeerd als niet-ongewenste e-mail met behulp van de invoegtoepassing berichten rapporteren, moet het beveiligingsteam van uw organisatie het [Antispambeleid](configure-your-spam-filter-policies.md)wellicht aanpassen.

Als uw organisatie gebruikmaakt van [Microsoft Defender voor Office 365 (abonnement 1](office-365-atp.md) of [abonnement 2](office-365-ti.md)), biedt de invoegtoepassing bericht melden het beveiligingsteam van uw organisatie nuttige informatie die kan worden gebruikt om beveiligingsbeleid te controleren en bij te werken.

Beheerders kunnen de invoegtoepassing bericht rapporteren voor de organisatie inschakelen en afzonderlijke gebruikers kunnen de invoegtoepassing voor zichzelf installeren.

Als u een individuele gebruiker bent, kunt u [de invoegtoepassing bericht rapporteren voor uzelf inschakelen](#get-the-report-message-add-in-for-yourself).

Als u een globale beheerder of een beheerder van Exchange Online bent en Exchange is geconfigureerd voor het gebruik van OAuth-verificatie, kunt u [de invoegtoepassing bericht rapporteren voor uw organisatie inschakelen](#get-and-enable-the-report-message-add-in-for-your-organization). De Add-In rapportberichten is nu beschikbaar via [gecentraliseerde implementatie](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet je weten voordat je begint?

- De invoegtoepassing bericht rapporteren werkt met de meeste Microsoft 365-abonnementen en de volgende producten:

  - De webversie van Outlook
  - Outlook 2013 SP1 of hoger
  - Outlook 2016 voor Mac
  - Outlook inbegrepen in Microsoft 365 apps for Enterprise

- De invoegtoepassing bericht rapporteren is niet beschikbaar voor postvakken in on-premises Exchange-organisaties.

- U kunt gerapporteerde berichten configureren voor kopiëren of omleiden naar een door u opgegeven postvak. Zie voor meer informatie [beleidsregels voor gebruikers ingediend](user-submission.md).

- De bestaande webbrowser moet werken met de invoegtoepassing bericht melden. Als u merkt dat de invoegtoepassing niet beschikbaar is of niet werkt zoals verwacht, kunt u een andere browser proberen.

- Voor installaties via een organisatie moet de organisatie worden geconfigureerd voor het gebruik van OAuth-verificatie. Zie [bepalen of gecentraliseerde implementatie van invoegtoepassingen werkt voor uw organisatie](../../admin/manage/centralized-deployment-of-add-ins.md)voor meer informatie.

- Beheerders moeten lid zijn van de rollen groep globale beheerders. Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

## <a name="get-the-report-message-add-in-for-yourself"></a>De invoegtoepassing bericht rapporteren voor uzelf weergeven

1. Ga naar de Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> en zoek naar de invoegtoepassing bericht melden. Als u rechtstreeks naar de invoegtoepassing bericht rapporteren wilt gaan, gaat u naar <https://appsource.microsoft.com/product/office/wa104381180> .

2. Klik op **Nu kopen**.

   ![Rapportbericht-nu kopen](../../media/ReportMessageGETITNOW.png)

3. In het dialoogvenster dat wordt weergegeven, bekijkt u de gebruiksvoorwaarden en het privacybeleid en klikt u vervolgens op **Doorgaan**.

4. Meld u aan met uw werk-of schoolaccount (voor zakelijk gebruik) of uw Microsoft-account (voor persoonlijk gebruik).

Nadat de invoegtoepassing is geïnstalleerd en is ingeschakeld, ziet u de volgende pictogrammen:

- Het pictogram in Outlook ziet er als volgt uit:

  ![Pictogram van invoegtoepassing voor berichten rapporteren voor Outlook](../../media/OutlookReportMessageIcon.png)

- Het pictogram in de webversie van Outlook ziet er zo uit:

  ![Pictogram voor de melding van de invoegtoepassing in de webversie van Outlook](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

Zie [de invoegtoepassing bericht rapporteren gebruiken](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)voor informatie over het gebruik van de invoegtoepassing.

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>De invoegtoepassing bericht rapporteren voor uw organisatie weergeven en inschakelen

> [!NOTE]
> Het kan 12 uur duren voordat de invoegtoepassing in uw organisatie wordt weergegeven.

1. Ga in het Microsoft 365-Beheercentrum naar de pagina **instellingen, geïntegreerde Apps & invoegtoepassingen** <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> en klik op **invoegtoepassing implementeren**.

   ![Pagina met Services en invoegtoepassingen in het Microsoft 365-Beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. Controleer de informatie in het vervolgmenu **een nieuwe invoegtoepassing implementeren** die wordt weergegeven en klik op **volgende**.

3. Op de volgende pagina klikt u op **kiezen uit de Store**.

   ![Een nieuwe pagina met invoegtoepassingen implementeren](../../media/NewAddInScreen2.png)

4. Klik op de pagina **invoegtoepassing selecteren** die wordt weergegeven in het **zoekvak** , Voer **rapportbericht** in en klik vervolgens op **Zoek** ![ actie zoeken ](../../media/search-icon.png) . Zoek in de lijst met resultaten naar **rapport** en klik op **toevoegen**.

   ![Zoekresultaten van invoegtoepassing selecteren](../../media/NewAddInScreen3.png)

5. In het dialoogvenster dat wordt weergegeven, bekijkt u de licentie-en privacygegevens en klikt u vervolgens op **Doorgaan**.

6. Configureer de volgende instellingen op de pagina **invoegtoepassing configureren** die wordt weergegeven:

   - **Toegewezen gebruikers** : Selecteer een van de volgende waarden:

     - **Iedereen** (standaard)
     - **Specifieke gebruikers/groepen**
     - **Alleen ik**

   - **Implementatiemethode** : Selecteer een van de volgende waarden:

     - **Fixed (standaardinstelling)** : de invoegtoepassing wordt automatisch geïmplementeerd voor de opgegeven gebruikers en kan de invoegtoepassing niet verwijderen.
     - **Beschikbaar** : gebruikers kunnen de invoegtoepassing installeren bij de beheerder van de **Startpagina** \> **invoegtoepassingen** \> **beheren**.
     - **Optioneel** : de invoegtoepassing wordt automatisch geïmplementeerd voor de opgegeven gebruikers, maar ze kunnen de optie wel verwijderen.

   ![Pagina invoegtoepassing configureren](../../media/configure-add-in.png)

   Wanneer u klaar bent, klikt u op **toepassen**.

7. Op de pagina **rapportbericht implementeren** dat wordt weergegeven, ziet u een voortgangsrapport gevolgd door een bevestiging dat de invoegtoepassing is geïmplementeerd. Nadat u de gegevens hebt gelezen, klikt u op **volgende**.

   ![Pagina rapportbericht implementeren](../../media/deploy-report-message-page.png)

8. Controleer de gegevens op de pagina **aangekondigde invoegtoepassing** die wordt weergegeven en klik vervolgens op **sluiten**.

   ![Pagina voor het aankondigen van invoegtoepassingen](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a>Meer informatie over het gebruik van de invoegtoepassing bericht melden

Voor personen aan wie de invoegtoepassing is toegewezen, worden de volgende pictogrammen weergegeven:

- Het pictogram in Outlook ziet er als volgt uit:

  ![Pictogram van invoegtoepassing voor berichten rapporteren voor Outlook](../../media/OutlookReportMessageIcon.png)

- Het pictogram in de webversie van Outlook ziet er zo uit:

  ![Pictogram voor de melding van de invoegtoepassing in de webversie van Outlook](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

Wanneer u gebruikers op de hoogte stelt van de invoegtoepassing bericht rapporteren, kunt u een koppeling opnemen om [de invoegtoepassing bericht rapporteren te gebruiken](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>Instellingen voor de invoegtoepassing bericht rapporteren controleren of bewerken

1. Ga in het Microsoft 365-Beheercentrum naar de pagina **Services & invoegtoepassingen** op <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> .

   ![Pagina Services en Add-Ins in het nieuwe Microsoft 365-Beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. Zoek en selecteer de invoegtoepassing **bericht rapporteren** .

3. Controleer en bewerk in het vervolgmenu met **berichten bewerken** dat wordt weergegeven, wat van toepassing is op uw organisatie. Klik op **Opslaan** wanneer u gereed bent.

   ![Instellingen voor de invoegtoepassing bericht melden](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a>Gerapporteerde berichten weergeven en controleren

Als u berichten wilt weergeven die gebruikers bij Microsoft rapporteren, hebt u de volgende opties:

- Gebruik de portal van de beheerder. Zie voor meer informatie [gebruikers items weergeven in Microsoft](admin-submission.md#view-user-submissions-to-microsoft).

- Maak een e-mail stroom regel (ook wel een transportregel genoemd) om kopieën van gerapporteerde berichten te verzenden. Zie voor instructies [de regels voor e-mail stroom gebruiken om te zien wat uw gebruikers aan Microsoft rapporteren](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).
