---
title: Migreren naar Microsoft 365 Business vanuit Office 365 Business Premium
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Meer informatie over hoe u uw bedrijf verplaatsen naar Microsoft 365 Business.
ms.openlocfilehash: a3f77bd18b9b900151c50f923b705e4ff0150519
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982436"
---
# <a name="migrate-to-microsoft-365-business-from-office-365-business-premium"></a>Migreren naar Microsoft 365 Business vanuit Office 365 Business Premium

Als u al een abonnement op Office 365 voor bedrijven hebt, bijvoorbeeld Office 365 Business Premium, u eenvoudig licenties toevoegen aan Microsoft 365 Business en deze toewijzen aan sommige of alle gebruikers.
  
> [!NOTE]
> U de knop [Switch plannen](https://support.office.com/article/73318661-8f33-478b-bcc7-fb8d69dbb22a?.aspx#switchbutton) niet gebruiken om te upgraden naar microsoft 365 Business nog. 
  
## <a name="add-microsoft-365-business-licenses"></a>Microsoft 365 Business-licenties toevoegen

U hebt twee manieren om Microsoft 365 Business te krijgen. Een partner kan Microsoft 365 Business aanschaffen bij [Microsoft Partner Center](get-microsoft-365-business.md). Uw partner kan u ook helpen bij de overgang naar Microsoft 365 Business.
  
Als u uw eigen abonnement beheert, u [contact opnemen met Sales](https://www.microsoft.com/microsoft-365/business) om microsoft 365 Business-licenties te kopen. 
  
Zie [een partner van Subscription Advisor toevoegen, wijzigen of verwijderen](https://support.office.com/article/f86e8177-936e-491e-9024-44dea2b296ff) om erachter te komen hoe u met een partner gaan werken. 
  
Als je een link krijgt om je licenties te kopen, loop je door een wizard zoals hieronder. Kies **Ja, voeg het toe aan mijn account**. U ook het aantal licenties en de betalingsmethode kiezen.
  
![Kies op de koppeling Microsoft 365 Business direct kopen om toe te voegen aan uw huidige account of Meld u aan voor een nieuw account.](media/8bc54fd1-9cab-44d5-af91-c471e89aea46.png)
  
## <a name="assign-microsoft-365-licenses"></a>Microsoft 365-licenties toewijzen

1. Zodra u nieuwe licenties hebt aangeschaft, en dit is de eerste keer dat u hebt gedaan, wordt de setup-banner voor Microsoft 365 Business weergegeven op de top van het Admin Center.
    
    > [!NOTE]
    > De setup-banner is een mogelijkheid om nieuwe gebruikers toe te voegen, een nieuw domein en e-mail voor nieuwe gebruikers te migreren. Als u niet van plan bent om te doen, moet u nog steeds door de wizard en kies standaardopties om het te laten verdwijnen uit de admin homepage. 
  
   ![Kies Start Setup op de Microsoft 365 Business is klaar om banner in te stellen.](media/8d3b0d97-7cca-497f-9364-4b00ad670209.png)
  
    Kies **Setup starten**.
    
2. Op de pagina **uw aanmelding en E-mail personaliseren** u een domein toevoegen door **een domein koppelen dat u al bezit** te kiezen als u deze mogelijkheid wilt gebruiken om een ander domein aan uw abonnement toe te voegen. 
    
    Als u al een domein hebt ingesteld, geeft het tweede veld aan dat en zal zeggen **blijven met behulp van** \< _uw domeinnaam_ \> **voor e-mail en aanmelden**.   Als u een domein met uw abonnement nog niet hebt ingesteld, wordt er gezegd dat u _uw bedrijfs name.onmicrosoft.com_ \> **blijven gebruiken** \< **voor e-mail en aanmelden**.  
    
    Kies **Volgende**.
    
    ![Kies op de pagina uw aanmeldings-en e-mailadres aanpassen of u een domein wilt toevoegen of gebruik de optie die u hebt gebruikt.](media/c3f5cfb2-1189-4d2f-803b-c9feb008a7a3.png)
  
3. Op de pagina **nieuwe gebruikers toevoegen** u nieuwe gebruikers toevoegen als u nieuwe werknemers hebt waaraan u de microsoft 365 Business-licenties wilt toewijzen. 
    
    Als er geen nieuwe werknemers zijn die u wilt toevoegen en licenties wilt toewijzen aan bestaande gebruikers, kiest u **volgende**.
    
4. Op de * * migreren e-mail berichten * * pagina u kiezen voor het migreren van e-mail voor een van de nieuwe gebruikers die u in stap 3 hebt toegevoegd. U deze stap ook overslaan. Kies **Volgende**.
    
5. Kies op de laatste pagina **Ga naar het Admin Center**, en ga verder met Setup daar.
    
6. In het Admin Center, gaat u naar **gebruikers** \> **actieve gebruikers**.
    
7. Selecteer de gebruiker aan wie u de **Microsoft 365 Business** -licentie wilt toewijzen en kies vervolgens **bewerken** naast **product licenties**.
    
    ![Kies in de gebruikerskaart bewerken naast product licenties.](media/be0fe2d8-7ff8-447c-88f6-d212ed78451c.png)
  
8. In **product licenties** dia **Microsoft 365 Business** **op** \> **Opslaan**en **sluit**.
    
Zodra u de eerste licentie voor Microsoft 365 Business hebt aangeschaft, u nu ook meer toevoegen aan de **Inkoop Services**voor **facturering** \> . Op de pagina **Inkoop Services** u klikken op de weglatingstekens op het visitekaartje van **Microsoft 365** en kiest u **licentie hoeveelheid wijzigen** om meer te kopen. 
  
## <a name="protect-user-devices-and-files"></a>Gebruikers apparaten en bestanden beveiligen

Nadat u licenties hebt toegewezen aan Microsoft 365 Business, u beginnen met het beveiligen van de apparaten en bestanden van de gebruikers.
  
1. In het Admin Center, in de linker NAV, gaat u naar **apparaten** \> **beleid**.
    
2. Kies op de pagina **apparaatbeleid** de optie **toevoegen**.
    
3. Geef in het deelvenster **beleid toevoegen** het beleid een naam en kies vervolgens een **beleidstype** in de vervolgkeuzelijst. 
    
    U toepassingsbeleid instellen voor het beveiligen van bestanden op Android-en iPhone-apparaten, evenals Windows 10, en u apparaatconfiguratiebeleid instellen voor Windows 10-apparaten die eigendom zijn van het bedrijf. Zie de volgende koppelingen voor meer informatie:
    
  - [Instellingen voor app-beveiliging instellen voor Android- of iOS-apparaten](app-protection-settings-for-android-and-ios.md)
    
  - [Instellingen voor toepassingsbeveiliging instellen voor Windows 10-apparaten](protection-settings-for-windows-10-devices.md)
    
  - [Instellingen voor apparaatbeveiliging instellen voor Windows 10-Pc's](protection-settings-for-windows-10-pcs.md)
    
   ![Voer in het deelvenster beleid toevoegen een naam voor het in en kies het beleidstype in het dropdownmenu.](media/76ef37e4-1d18-4f34-8a0f-391ab1d0ae2b.png)
  
4. Zodra u beleid hebt ingesteld, kunnen u en uw werknemers apparaten instellen:
    
  - Als uw Windows nog niet is geïnstalleerd op de Windows Pro Creator-update, moet u [deze upgraden naar Windows Pro Creators update](upgrade-to-windows-pro-creators-update.md).
    
  - Zie [Windows-apparaten instellen voor Microsoft 365 zakelijke gebruikers](set-up-windows-devices.md) voor stappen voor Windows-apparaten. 
    
  - Zie [mobiele apparaten instellen voor Microsoft 365 zakelijke gebruikers](set-up-mobile-devices.md) voor stappen voor Android-telefoons en iPhones. 
    
5. Voor het automatisch installeren van Office-client-apps, Zie [voorbereiden voor Office-clientimplementatie door Microsoft 365 Business](prepare-for-office-client-deployment.md) en [automatisch installeren of verwijderen van Office op Windows 10-apparaten](auto-install-or-uninstall-office.md).
    


