---
title: Samenwerken met gasten in een team
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: sharepoint-online
ms.collection: SPO_Content
localization_priority: Normal
f1.keywords: NOCSH
description: Meer informatie over hoe u samenwerken met gasten in Teams.
ms.openlocfilehash: 54bf52eebc77e1cce8e1c05a708572d7d1e7fdae
ms.sourcegitcommit: 21338a9287017a66298e0ff557e80051946ebf13
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/11/2020
ms.locfileid: "42806265"
---
# <a name="collaborate-with-guests-in-a-team"></a>Samenwerken met gasten in een team

Als u met gasten wilt samenwerken in documenten, taken en gesprekken, raden we u aan Microsoft Teams te gebruiken. Teams biedt alle samenwerkingsfuncties die beschikbaar zijn in Office en SharePoint met permanente chat en een aanpasbare en uitbreidbare set samenwerkingstools in een uniforme gebruikerservaring.

In dit artikel doorlopen we de Microsoft 365-configuratiestappen die nodig zijn om een team op te zetten voor samenwerking met gasten.

## <a name="video-demonstration"></a>Videodemonstratie

In deze video worden de configuratiestappen weergegeven die in dit document worden beschreven.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a>Instellingen voor Azure Organizational Relationships

Delen in Microsoft 365 wordt op het hoogste niveau geregeld door de instellingen voor organisatierelaties in Azure Active Directory. Als het delen van gasten is uitgeschakeld of beperkt in Azure AD, worden alle instellingen voor delen die u configureert in Microsoft 365, overschreven.

Controleer de instellingen voor organisatierelaties om ervoor te zorgen dat delen met gasten niet wordt geblokkeerd.

![Schermafbeelding van de pagina Instellingen voor Azure Active Directory-organisatierelaties](../media/azure-ad-organizational-relationships-settings.png)

Instellingen voor organisatierelatie instellen

1. Log in bij [https://portal.azure.com](https://portal.azure.com)Microsoft Azure bij .
2. Klik in de linkernavigatie op **Azure Active Directory**.
3. Klik in het deelvenster **Overzicht** op **Organisatierelaties**.
4. Klik in het deelvenster **Organisatierelaties** op **Instellingen**.
5. Zorg ervoor dat **beheerders en gebruikers in de rol gastgenodigden kunnen uitnodigen** en leden kunnen **uitnodigen,** zijn beide ingesteld op **Ja**.
6. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

Let op de instellingen in de sectie **Beperkingen voor samenwerking.** Zorg ervoor dat de domeinen van de gasten waarmee u wilt samenwerken niet worden geblokkeerd.

## <a name="teams-guest-access-settings"></a>Instellingen voor gasttoegang teams

Teams heeft een master aan/uit-schakelaar voor gasttoegang en een verscheidenheid aan instellingen beschikbaar om te bepalen wat gasten in een team kunnen doen. De master switch, **Toestaan dat gasttoegang in Teams** moet **ingeschakeld** zijn voor gasttoegang tot het werk in Teams.

Controleer of de toegang tot gasten is ingeschakeld in Teams en elke aanpassing aan de gastinstellingen aan te passen op basis van uw zakelijke behoeften. Houd er rekening mee dat deze instellingen van invloed zijn op alle teams.

![Schermafbeelding van de toegang tot Teams-gasten om te schakelen](../media/teams-guest-access-toggle-on.png)

Instellingen voor gasttoegang van Teams instellen

1. Log in bij het Microsoft 365-beheercentrum bij [https://admin.microsoft.com](https://admin.microsoft.com).
2. Klik in de linkernavigatie op **Alles weergeven**.
3. Klik onder **Beheercentra**op **Teams**.
4. Vouw in het beheercentrum Teams in de linkernavigatie **organigrambrede instellingen** uit en klik op **Gasttoegang.**
5. Zorg ervoor dat **gasttoegang toestaan in Teams** is ingesteld op **Aan.**
6. Breng de gewenste wijzigingen aan in de extra gastinstellingen en klik op **Opslaan.**

> [!NOTE]
> Het kan tot vierentwintig uur duren voordat de teams-gastinstelling actief zijn nadat u de instelling hebt ingeschakeld.

## <a name="office-365-groups-guest-settings"></a>Gastinstellingen voor Office 365-groepen

Teams gebruiken Office 365-groepen voor het lidmaatschap van het team. De gastinstellingen voor Office 365-groepen moeten zijn ingeschakeld om gasttoegang in Teams te laten werken.

![Schermafbeelding van gastinstellingen voor Office 365-groepen in het Microsoft 365-beheercentrum](../media/office-365-groups-guest-settings.png)

Gastinstellingen voor Office 365-groepen instellen

1. Vouw instellingen in het Microsoft 365-beheercentrum in de linkernavigatie **uit**.
2. Klik op **Services & invoegins**.
3. Klik in de lijst op **Office 365-groepen**.
4. Zorg ervoor dat de **groepsleden buiten de groepsinhoud van uw organisatie toegang hebben tot groepsinhoud** en **dat groepseigenaren mensen buiten uw organisatie aan groepen** laten toevoegen, beide worden gecontroleerd.
5. Als u wijzigingen hebt aangebracht, klikt u op **Wijzigingen opslaan**.


## <a name="sharepoint-organization-level-sharing-settings"></a>Instellingen voor delen op sharepoint-organisatieniveau

Teams-inhoud zoals bestanden, mappen en lijsten worden allemaal opgeslagen in SharePoint. Om gasten toegang te geven tot deze items in Teams, moeten de instellingen voor delen op organisatieniveau het delen met gasten mogelijk maken.

De instellingen op organisatieniveau bepalen welke instellingen beschikbaar zijn voor afzonderlijke sites, inclusief sites die zijn gekoppeld aan teams. Site-instellingen kunnen niet toleranter zijn dan de instellingen op organisatieniveau.

Als u het delen van bestanden en mappen met niet-geverifieerde personen wilt toestaan, kiest u **Iedereen**. Als u ervoor wilt zorgen dat alle gasten zich moeten authenticeren, kiest u **Nieuwe en bestaande gasten.** Kies de meest tolerante instelling die nodig is voor elke site in uw organisatie.

![Schermafbeelding van instellingen voor delen op sharepoint-organisatieniveau](../media/sharepoint-organization-external-sharing-controls.png)


Instellingen voor delen op sharepoint-organisatieniveau instellen

1. Klik in het Microsoft 365-beheercentrum in de linkernavigatie onder **Beheercentra**op **SharePoint**.
2. Klik in het SharePoint-beheercentrum in de linkernavigatie op **Delen**.
3. Zorg ervoor dat extern delen voor SharePoint is ingesteld op **iedereen** of **nieuwe en bestaande gasten.**
4. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.


## <a name="sharepoint-organization-level-default-link-settings"></a>Standaardkoppelingsinstellingen voor SharePoint-organisatieniveau

De instellingen voor standaardbestands- en mapkoppelingen bepalen welke koppelingsoptie standaard aan de gebruiker wordt weergegeven wanneer deze een bestand of map deelt. Gebruikers kunnen het koppelingstype wijzigen in een van de andere opties voordat ze desgewenst delen.

Houd er rekening mee dat deze instelling van invloed is op alle teams en SharePoint-sites in uw organisatie.

Kies het type koppeling dat standaard is geselecteerd wanneer gebruikers bestanden en mappen delen:

- **Iedereen met de link** - Kies deze optie als je verwacht dat je veel niet-geverifieerde delen van bestanden en mappen zult doen. Als u *Koppelingen* wilt toestaan, maar zich zorgen maakt over het per ongeluk niet-geverifieerde delen, beschouw dan een van de andere opties als standaard. Dit koppelingstype is alleen beschikbaar als u iedereen hebt ingeschakeld om **te** delen.
- **Alleen mensen in uw organisatie** - Kies deze optie als u verwacht dat het delen van bestanden en mappen het meest met mensen binnen uw organisatie is.
- **Specifieke mensen** - Overweeg deze optie als u verwacht veel bestanden en mappen te delen met gasten. Dit type koppeling werkt samen met gasten en vereist dat ze zich verifiëren.
 
![Schermafbeelding van instellingen voor delen op organisatieniveau](../media/sharepoint-organization-files-folders-sharing-settings.png)


Standaardkoppelingsinstellingen voor SharePoint-organisatieniveau instellen

1. Navigeer naar de pagina Delen in het SharePoint-beheercentrum.
2. Selecteer onder **Bestands- en mapkoppelingen**de standaardkoppeling voor delen die u wilt gebruiken.
3. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="create-a-team"></a>Een team maken

De volgende stap is het maken van het team dat u wilt gebruiken om samen te werken met gasten.

Een team maken
1. Klik in Teams op het tabblad **Teams** op **Deelnemen of maak een team** onder aan het linkerdeelvenster.
2. Klik op **Een team maken**.
3. Klik **op Een team helemaal opnieuw samenstellen.**
4. Kies **Privé** of **Openbaar**.
5. Typ een naam en beschrijving voor het team en klik op **Maken**.
6. Klik op **Overslaan**.

We nodigen gebruikers later uit. Vervolgens is het belangrijk om de instellingen voor delen op siteniveau te controleren voor de SharePoint-site die aan het team is gekoppeld.

## <a name="sharepoint-site-level-sharing-settings"></a>Instellingen voor delen op sharepoint-siteniveau

Controleer de instellingen voor delen op siteniveau om ervoor te zorgen dat ze het gewenste type toegang voor dit team toestaan. Als u bijvoorbeeld de instellingen op organisatieniveau instelt op **Iedereen,** maar u wilt dat alle gasten zich voor dit team verifiëren, controleert u of de instellingen voor delen op siteniveau zijn ingesteld op **nieuwe en bestaande gasten.**

![Schermafbeelding van instellingen voor extern delen van de SharePoint-site](../media/sharepoint-site-external-sharing-settings.png)


Instellingen voor delen op siteniveau instellen
1. Vouw **sites** in het SharePoint-beheercentrum uit en klik op **Actieve sites**in het SharePoint-beheercentrum.
2. Selecteer de site voor het team dat u zojuist hebt gemaakt.
3. Klik op het lint op **Delen**.
4. Zorg ervoor dat delen is ingesteld op **iedereen** of **nieuwe en bestaande gasten.**
5. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="invite-users"></a>Gebruikers uitnodigen

Instellingen voor het delen van gasten zijn nu geconfigureerd, zodat u interne gebruikers en gasten toevoegen aan uw team. 

Interne gebruikers uitnodigen voor een team
1. Klik in het team**\*\*** op **Meer opties** ( ) en klik vervolgens op **Lid toevoegen**.
2. Typ de naam van de persoon die u wilt uitnodigen.
3. Klik op **Toevoegen**en klik vervolgens op **Sluiten**.

Gasten uitnodigen voor een team
1. Klik in het team**\*\*** op **Meer opties** ( ) en klik vervolgens op **Lid toevoegen**.
2. Typ het e-mailadres van de gast die u wilt uitnodigen.
3. Klik **op Gastgegevens bewerken**.
4. Typ de volledige naam van de gast en klik op het vinkje.
5. Klik op **Toevoegen**en klik vervolgens op **Sluiten**.

## <a name="see-also"></a>Zie ook

[Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers](best-practices-anonymous-sharing.md)

[Onbedoelde blootstelling aan bestanden beperken wanneer u deelt met gasten](share-limit-accidental-exposure.md)

[Een veilige omgeving voor het delen van gasten creëren](create-secure-guest-sharing-environment.md)

[Maak een B2B extranet met beheerde gasten](b2b-extranet.md)
