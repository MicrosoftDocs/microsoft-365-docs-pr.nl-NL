---
title: Migreren naar Microsoft 365 Business van Office 365 Business Premium
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Informatie over hoe u uw bedrijf naar Microsoft 365 Business.
ms.openlocfilehash: fd6f18c02453e6751d6163ab79e726eae9c951a9
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2019
ms.locfileid: "26983492"
---
# <a name="migrate-to-microsoft-365-business-from-office-365-business-premium"></a>Migreren naar Microsoft 365 Business van Office 365 Business Premium

Als u al een Office 365 voor zakelijke abonnement, bijvoorbeeld Office 365 Business Premium, kunt u eenvoudig licenties toevoegen aan Microsoft 365 Business en deze toewijzen aan bepaalde of alle gebruikers.
  
> [!NOTE]
> U kunt de knop [Switch plannen](https://support.office.com/article/73318661-8f33-478b-bcc7-fb8d69dbb22a?.aspx#switchbutton) niet gebruiken voor een upgrade naar Microsoft 365 Business nog. 
  
## <a name="add-microsoft-365-business-licenses"></a>Microsoft 365 Business licenties toevoegen

Er zijn twee manieren om Microsoft 365 Business. Als u een partner hebt, kan hij of zij kopen Microsoft 365 Business voor u bij [Microsoft Partner Center](get-microsoft-365-business.md). Uw partner kunt u ook de overgang naar Microsoft 365 Business.
  
Als u zelf uw abonnement beheren, kunt u [contact op met sales](https://www.microsoft.com/microsoft-365/business) Microsoft 365 Business licenties kopen. 
  
Zie [toevoegen, wijzigen of verwijderen van een abonnement advisor partner](https://support.office.com/article/f86e8177-936e-491e-9024-44dea2b296ff) om erachter te komen hoe u kunt aan de slag met een partner. 
  
Als u een koppeling naar uw licenties te kopen, wordt een wizard zoals in de onderstaande doorlopen. Kies **Ja, voeg toe aan Mijn account**. U kunt ook het nummer van het certificaat en de betalingsmethode kiezen.
  
![Kopen op de directe Microsoft 365 Business link, kiest u toevoegen aan uw huidige account of meld u aan voor een nieuwe account.](media/8bc54fd1-9cab-44d5-af91-c471e89aea46.png)
  
## <a name="assign-microsoft-365-licenses"></a>Licenties voor Microsoft 365 toewijzen

1. Zodra u nieuwe licenties hebt aangeschaft en dit is de eerste keer dat u hebt gedaan, wordt het spandoek setup voor Microsoft 365 Business op het admin center weergegeven.
    
    > [!NOTE]
    > De setup banner is een gelegenheid voor nieuwe gebruikers, een nieuw domein toevoegen en e-mailadres voor nieuwe gebruikers migreren. Als u niet doen wilt, u nog steeds de wizard en standaardopties kiezen om te maken van de introductiepagina voor beheer. 
  
   ![Kies Start op de Microsoft 365 Business is gereed voor het instellen van een spandoek.](media/8d3b0d97-7cca-497f-9364-4b00ad670209.png)
  
    Kies **Setup starten**.
    
2. Op de pagina **aanpassen, het aanmelden en e-mailadres** , kunt u een domein door **verbinding maken met een domein dat u al eigenaar** kiezen als u gebruiken de opportunity wilt naar een ander domein toevoegen aan uw abonnement toevoegen. 
    
    Als u al een domein hebt ingesteld, het tweede veld dat wordt aangegeven en vanzelfsprekend **Doorgaan met behulp van** \< _de domeinnaam_ \> **voor e-mail en het aanmelden**. Als u een domein met u abonnement niet hebt ingesteld, wordt dat **Doorgaan met behulp van** \< _de name.onmicrosoft.com van uw bedrijf_ \> **voor e-mail en het aanmelden**.    
    
    Kies **Volgende**.
    
    ![Kies een domein toevoegen, of degene die u hebt gebruikt op de persoonlijke instellingen voor het aanmelden en e-pagina.](media/c3f5cfb2-1189-4d2f-803b-c9feb008a7a3.png)
  
3. U kunt op de pagina **nieuwe gebruikers toevoegen** , nieuwe gebruikers toevoegen als u nieuwe werknemers die u wilt toewijzen aan de licenties voor Microsoft 365 Business. 
    
    Als u geen nieuwe werknemers toevoegen en certificaten toewijzen aan bestaande gebruikers wilt, kies **volgende**.
    
4. Op de ** migreren e-mailberichten ** pagina u kiezen kunt voor het migreren van e-mailadres voor alle nieuwe gebruikers die u in stap 3 hebt toegevoegd. U kunt deze stap ook overslaan. Kies **volgende**.
    
5. Kies **Ga naar het beheercentrum**en doorgaan met setup er op de laatste pagina.
    
6. Ga in het beheercentrum op **gebruikers** \> **actieve gebruikers**.
    
7. Selecteer de gebruiker aan wie u wilt de **Microsoft 365 Business** licentie toewijzen en kies vervolgens **bewerken** naast **Productlicenties**.
    
    ![Kies Bewerken naast productlicenties in Gebruikerskaart voor de.](media/be0fe2d8-7ff8-447c-88f6-d212ed78451c.png)
  
8. Dia in de **productlicenties van** **Microsoft 365 Business** **aan** \> **Opslaan**, en vervolgens op **sluiten**.
    
Nadat u de oorspronkelijke licentie hebt aangeschaft voor Microsoft 365 Business, kunt u nu ook toevoegen meer in **Facturering** \> **Inkoop services**. U kunt op de pagina **services kopen** klikt u op de weglatingstekens op het visitekaartje van **Microsoft 365** en **licentie-aantal wijzigen** meer kiezen. 
  
## <a name="protect-user-devices-and-files"></a>Gebruikersapparaten en -bestanden beveiligen

Nadat u licenties hebt toegewezen aan Microsoft 365 Business, kunt u beginnen met het beschermen van apparaten en bestanden van de gebruikers.
  
1. Ga naar **apparaten** in het admin center, in de Linkernavigatie \> **beleid**.
    
2. Kies op de pagina **beleid voor apparaat** **toevoegen**.
    
3. Het beleid een naam geven in het deelvenster **beleid toevoegen** en kies een **type beleid** in de vervolgkeuzelijst. 
    
    U kunt beleidsregels voor toepassingen voor het beveiligen van bestanden op Android en iPhone-apparaten, evenals Windows 10 instellen en kunt u een apparaat configuratie van beleid voor een bedrijf dat eigendom is Windows 10-apparaten instellen. Zie de volgende koppelingen voor meer informatie:
    
  - [Instellingen voor app-beveiliging instellen voor Android- of iOS-apparaten](app-protection-settings-for-android-and-ios.md)
    
  - [Instellingen voor toepassingsbeveiliging instellen voor Windows 10-apparaten](protection-settings-for-windows-10-devices.md)
    
  - [Instellingen voor apparaatbeveiliging instellen voor Windows 10-pc's](protection-settings-for-windows-10-pcs.md)
    
   ![Voer een naam voor het in het venster van het beleid toevoegen en kiest u het type uit de vervolgkeuzelijst.](media/76ef37e4-1d18-4f34-8a0f-391ab1d0ae2b.png)
  
4. Als u een beleid ingesteld, kunnen u en uw medewerkers-apparaten instellen:
    
  - Als Windows niet al op Pro Maker Windows update, moet u [deze Pro makers van Update voor Windows bijwerken](upgrade-to-windows-pro-creators-update.md).
    
  - Zie [Windows-apparaten voor gebruikers van Microsoft 365 Business](set-up-windows-devices.md) voor stappen voor Windows-apparaten. 
    
  - Zie [mobiele apparaten voor gebruikers van Microsoft 365 Business](set-up-mobile-devices.md) voor stappen voor Android-telefoons en iPhones. 
    
5. Zie [voorbereiden voor clientimplementatie Office van Microsoft 365 Business](prepare-for-office-client-deployment.md) en [automatisch installeren of verwijderen van Office voor Windows 10-apparaten](auto-install-or-uninstall-office.md)automatisch installeren van Office-clienttoepassingen.
    


