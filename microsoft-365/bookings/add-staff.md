---
title: Medewerkers toevoegen aan Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
description: Gebruik deze pagina om uw personeelslijst te maken en om de gegevens van personeelsleden te beheren, zoals naam, telefoonnummer en e-mailadres.
ms.openlocfilehash: 23757c492986936125eff1203e6a99231164da22
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52768943"
---
# <a name="add-staff-to-bookings"></a>Medewerkers toevoegen aan Bookings

Op de pagina Personeel in Bookings maakt u uw personeelslijst en beheert u de gegevens van personeelsleden, zoals naam, telefoonnummer en e-mailadres. U kunt hier ook werkuren instellen voor elk personeelslid.

## <a name="before-you-begin"></a>Voordat u begint

Hoewel Bookings een functie van Microsoft 365 is, zijn niet alle personeelsleden verplicht een account Microsoft 365 hebben. Alle personeelsleden moeten een geldig e-mailadres hebben, zodat ze boekingen kunnen ontvangen en wijzigingen kunnen plannen.

## <a name="watch-add-your-staff-to-bookings"></a>Kijken: Uw personeel toevoegen aan Bookings

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWuVka]

## <a name="steps"></a>Stappen

1. Ga naar de [pagina Personeel beheren en](https://outlook.office.com/bookings/staff) selecteer Personeel **toevoegen**

2. Selecteer de **knop Personeel toevoegen.**

3. Wanneer u personeel toevoegt vanuit uw  organisatie, typt u de naam in het veld Personen toevoegen en selecteert u deze wanneer deze worden weergegeven in de vervolgkeuzelijst. De andere velden worden automatisch ingevuld.

    Wanneer een personeelslid is toegevoegd, kunt u de naam bewerken die wordt weergegeven in alle Bookings-communicatie door de **x** naast hun naam te selecteren en het veld Personen toevoegen **te** bewerken. Dit kan handig zijn als u wilt dat personeelsleden een specifieke titel of naam laten zien voor klanten, zoals het weergeven van Adele Vance als 'Dr. Vance, MD'.

4. Als u personeel van buiten uw organisatie wilt toevoegen, vult u handmatig hun e-mail en andere informatie in.

    > [!NOTE]
    > Personeel van buiten uw tenant kan geen gratis/bezet informatie delen met Bookings.

5. Selecteer voor elk personeelslid een rol: Beheerder, Viewer of Gast.
    - **Beheerders kunnen** alle instellingen bewerken, personeel toevoegen en verwijderen en boekingen maken, bewerken of verwijderen.
    - **Gebruikers** kunnen alle boekingen in de agenda zien, maar ze kunnen ze niet wijzigen of verwijderen. Ze hebben alleen-lezen toegang tot instellingen.
    - **Gasten** kunnen worden toegewezen aan boekingen, maar ze kunnen het postvak van de reservering niet openen.

6. Selecteer **Alle personeelsleden per e-mail** op de hoogte stellen wanneer een reservering die aan hen is toegewezen, wordt gemaakt of gewijzigd om e-mailberichten van personeelsleden in te stellen. Hieronder volgt een voorbeeld van een e-mailbericht:

    :::image type="content" source="media/bookings-notify-all-email.jpg" alt-text="Een meldingsbericht van Bookings":::

7. Selecteer **Gebeurtenissen in Office 365 agenda** die van invloed zijn op de beschikbaarheid als u wilt dat de beschikbaarheid van boekingsservices via Bookings wordt beïnvloed door de beschikbaarheid van de agenda's van personeelsleden.

    Als een personeelslid bijvoorbeeld een teamvergadering of een persoonlijke afspraak heeft gepland voor 15.00 uur op een woensdag, wordt in Bookings het personeelslid als niet beschikbaar om in dat tijdsvak te worden geboekt, laten zien. Deze tijd wordt weergegeven als bezet of voorlopig in de weergave Bookings-agenda, zoals wordt weergegeven in het onderstaande voorbeeld.

    :::image type="content" source="media/bookings-busy-tentative-view.jpg" alt-text="Een weergave van een Bookings-agenda":::

> [!IMPORTANT]
> We raden u ten zeerste aan deze instelling aan te laten staan (deze is standaard ingeschakeld) om dubbele boekingen te voorkomen en om de beschikbaarheid van uw personeelsleden te optimaliseren.

8. Selecteer **Openingstijden gebruiken** om alle boekbare tijden in te stellen voor uw  personeelsleden om alleen binnen de werkuren te zijn die u hebt ingesteld in de sectie Werkuren op de pagina Bedrijfsgegevens.

    Door de selectie van dit vak te deselecteren, kunnen personeelsleden aangepaste uren krijgen die verder beperken wanneer ze kunnen worden geboekt. Dit is handig voor scenario's waarin een personeelslid alleen op dinsdag en woensdag ter plekke is, of wanneer hij of zij zijn of haar ochtenden wijden voor een type afspraken en hun middagen voor andere typen.

    > [!NOTE]
    > Alleen de eerste 31 personeelsleden die u aan uw personeelspagina toevoegt, worden weergegeven wanneer u personeelsleden aan een service toewijst.

## <a name="make-a-bookings-user-a-super-user-without-adding-them-as-staff-in-bookings"></a>Een Bookings-gebruiker een supergebruiker maken zonder deze toe te voegen als Staff in Bookings

Mogelijk wilt u een persoon toevoegen aan uw personeelslijst in Bookings zonder deze beschikbaar te stellen voor klanten of klanten. Wanneer u ze een supergebruiker maakt, worden ze beheerder van het postvak van de reservering. Als beheerder van een boekingspostvak wordt gedefinieerd dat u volledige toegang hebt tot het boekingspostvak en machtigingen voor verzenden als.

> [!NOTE]
> Deze stappen werken alleen als de gebruiker die  wordt toegevoegd nog geen viewerrol heeft toegewezen in Bookings.

1. [Verbinding maken om Microsoft 365 powershell te gebruiken.](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

2. Met PowerShell kunt u volledige toegang toewijzen met de volgende opdrachten:

    ```powershell
    Add-MailboxPermission -Identity <bookingmailbox@emailaddress> -User <adminusers@emailaddress> -AccessRights FullAccess -Deny:$false
    ```

3. Voer vervolgens deze opdracht uit om machtigingen voor verzenden als toe te wijzen.

    ```powershell
    Add-RecipientPermission -Identity <bookingmailbox@emailaddress> -Trustee <adminusers@emailaddress> -AccessRights SendAs -Confirm:$false
    ```

Hier is een voorbeeld van de PowerShell-opdracht om Allie Bellew toe te voegen aan het postvak van Contoso-dagopvangboek.

1. Voer eerst deze opdracht uit:

    ```powershell
    Add-MailboxPermission -Identity "daycare@contoso.com" -User "Allie Bellew" -AccessRights FullAccess -InheritanceType All
    ```

2. Voer vervolgens deze opdracht uit:

    ```powershell
    Add-RecipientPermission -Identity <bookingmailbox@emailaddress> -Trustee <adminusers@emailaddress> -AccessRights SendAs -Confirm:$false
    ```

**Allie Bellew heeft** nu beheerderstoegang, maar wordt niet weergegeven als boekbaar personeel in Bookings.
