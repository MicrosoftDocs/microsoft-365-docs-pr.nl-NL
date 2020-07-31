---
title: Samenwerken met gasten in een team
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Meer informatie over de Microsoft 365-configuratiestappen die nodig zijn om een team op te zetten voor samenwerking met gasten in Teams.
ms.openlocfilehash: 73f9a7a1c52c8c237cccabafd8fca24abe038ff7
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46528216"
---
# <a name="collaborate-with-guests-in-a-team"></a>Samenwerken met gasten in een team

Als u met gasten moet samenwerken voor documenten, taken en gesprekken, raden we u aan Microsoft Teams te gebruiken. Teams biedt alle samenwerkingsfuncties die beschikbaar zijn in Office en SharePoint met permanente chat en een aanpasbare en uitbreekbare set samenwerkingstools in een uniforme gebruikerservaring.

In dit artikel doorlopen we de Microsoft 365-configuratiestappen die nodig zijn om een team op te zetten voor samenwerking met gasten.

## <a name="video-demonstration"></a>Videodemonstratie

In deze video worden de configuratiestappen weergegeven die in dit document worden beschreven.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a>Azure-instellingen voor organisatierelaties

Delen in Microsoft 365 wordt op het hoogste niveau bepaald door de instellingen voor organisatierelaties in Azure Active Directory. Als het delen van gasten is uitgeschakeld of beperkt in Azure AD, worden alle instellingen voor delen die u in Microsoft 365 configureert, overschrijven.

Controleer de instellingen voor organisatorische relaties om ervoor te zorgen dat delen met gasten niet wordt geblokkeerd.

![Schermafbeelding van de instellingenpagina voor organisatierelaties in Microsoft Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Instellingen voor organisatierelaties instellen

1. Log in bij Microsoft Azure op [https://portal.azure.com](https://portal.azure.com) .
2. Klik in de linkernavigatie op **Azure Active Directory**.
3. Klik in het deelvenster **Overzicht** op **Externe identiteiten**.
4. Klik in het deelvenster **Organisatieidentiteiten** op **Instellingen voor externe samenwerking**.
5. Zorg ervoor dat **beheerders en gebruikers in de rol van gastuitnodiger kunnen worden uitgenodigd** en dat leden kunnen **uitnodigen,** zijn beide ingesteld op **Ja.**
6. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

Let op de instellingen in de sectie **Samenwerkingsbeperkingen.** Zorg ervoor dat de domeinen van de gasten waarmee u wilt samenwerken, niet worden geblokkeerd.

## <a name="teams-guest-access-settings"></a>Toegangsinstellingen voor gasten van Teams

Teams heeft een master aan/uit schakelaar voor toegang tot gasten en een verscheidenheid aan instellingen beschikbaar om te bepalen wat gasten kunnen doen in een team. De hoofdschakelaar, **Gasttoegang toestaan in Teams** moet **ingeschakeld** zijn voor gasttoegang om in Teams te werken.

Controleer of gasttoegang is ingeschakeld in Teams en breng eventuele aanpassingen aan de gastinstellingen op basis van uw zakelijke behoeften. Houd er rekening mee dat deze instellingen van invloed zijn op alle teams.

![Schermafbeelding van wisselknop Gasttoegang in Teams](../media/teams-guest-access-toggle-on.png)

Instellingen voor gasttoegang in Teams instellen

1. Meld u aan bij het Microsoft 365-beheercentrum op [https://admin.microsoft.com](https://admin.microsoft.com).
2. Klik in het navigatievenster aan de linkerkant op **Alles weergeven**.
3. Klik onder **Beheercentra** op **Teams**.
4. Vouw in het Teams-beheercentrum in het linkernavigatievenster **Instellingen voor hele organisatie** uit en klik vervolgens op **Gasttoegang**.
5. Zorg ervoor dat **Gasttoegang in Teams toestaan** is ingesteld op **Aan**.
6. Breng de gewenste wijzigingen aan in de extra gastinstellingen en klik vervolgens op **Opslaan**.

> [!NOTE]
> Het kan 24 uur duren voordat de instelling voor gasten in Teams actief wordt nadat u deze hebt ingeschakeld.

## <a name="microsoft-365-groups-guest-settings"></a>Gasteninstellingen voor Microsoft 365-groepen

Teams gebruikt Microsoft 365-groepen voor het lidmaatschap van het team. De gastinstellingen voor Microsoft 365-groepen moeten zijn ingeschakeld om toegang tot gasten in Teams te kunnen gebruiken.

![Schermopname van gastinstellingen van Microsoft 365 Groepen in het Microsoft 365-beheercentrum](../media/office-365-groups-guest-settings.png)

Gastinstellingen voor Microsoft 365-groepen instellen

1. Vouw in het Microsoft 365-beheercentrum in de linkernavigatie **Instellingen**uit.
2. Klik op **Organisatie-instellingen**.
3. Klik in de lijst op **Microsoft 365-groepen**.
4. Controleer de selectievakjes **Groepsleden van De groep Laten buiten uw organisatie toegang krijgen tot groepsinhoud** en **Groepeigenaren personen buiten uw organisatie aan groepen toevoegen.**
5. Als u wijzigingen hebt aangebracht, klikt u op **Wijzigingen opslaan**.


## <a name="sharepoint-organization-level-sharing-settings"></a>Instellingen voor delen op niveau van SharePoint-organisatie

Teams-inhoud zoals bestanden, mappen en lijsten worden allemaal opgeslagen in SharePoint. Om gasten toegang te geven tot deze items in Teams, moeten de instellingen voor delen op Organisatieniveau van SharePoint het mogelijk maken om met gasten te delen.

De instellingen op organisatieniveau bepalen welke instellingen beschikbaar zijn voor afzonderlijke sites, inclusief sites die zijn gekoppeld aan teams. Site-instellingen kunnen niet toleranter zijn dan de instellingen op organisatieniveau.

Als u het delen van bestanden en mappen met niet-geverifieerde personen wilt toestaan, kiest **u Iedereen**. Als u ervoor wilt zorgen dat alle gasten moeten verifiëren, kiest u **Nieuwe en bestaande gasten.** Kies de meest tolerante instelling die nodig is voor elke site in uw organisatie.

![Schermafbeelding van de instellingen voor delen op organisatieniveau van SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


Instellingen voor delen op niveau van SharePoint instellen

1. Klik in het Microsoft 365-beheercentrum in de linkernavigatie onder **Beheercentra**op **SharePoint**.
2. Klik in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant op **delen**.
3. Zorg ervoor dat extern delen voor SharePoint is ingesteld op **Iedereen** of **Nieuw en bestaande gasten**.
4. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.


## <a name="sharepoint-organization-level-default-link-settings"></a>Standaardkoppelingsinstellingen voor SharePoint-organisatieniveau

De standaardinstellingen voor bestands- en mapkoppeling bepalen welke koppelingsoptie standaard aan de gebruiker wordt weergegeven wanneer deze een bestand of map deelt. Gebruikers kunnen het koppelingstype wijzigen in een van de andere opties voordat ze desverdeeld delen, indien gewenst.

Houd er rekening mee dat deze instelling van invloed is op alle teams en SharePoint-sites in uw organisatie.

Kies het type koppeling dat standaard is geselecteerd wanneer gebruikers bestanden en mappen delen:

- **Iedereen met de link** - Kies deze optie als je verwacht dat je veel niet-geverifieerde delen van bestanden en mappen te doen. Als u links voor iedereen wilt *toestaan,* maar zich zorgen wilt maken over het per ongeluk delen zonder toestemming, beschouw dan een van de andere opties als de standaardoptie. Dit koppelingstype is alleen beschikbaar als je Het delen van **iedereen** hebt ingeschakeld.
- **Alleen mensen in uw organisatie** - Kies deze optie als u verwacht dat het delen van bestanden en mappen met mensen binnen uw organisatie is.
- **Specifieke personen** - Overweeg deze optie als u verwacht veel bestands- en mapdelingen met gasten te doen. Dit type link werkt samen met gasten en vereist dat ze zich verifiëren.
 
![Schermafbeelding van de instellingen voor delen van bestanden en mappen op organisatieniveau van SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


De standaardkoppelingsinstellingen op SharePoint-organisatieniveau instellen

1. Navigeer naar de pagina Delen in het SharePoint-beheercentrum.
2. Selecteer onder **Koppelingen bestand en mappen**de standaardkoppelingskoppeling die u wilt gebruiken.
3. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="create-a-team"></a>Een team maken

De volgende stap is het maken van het team dat u wilt gebruiken om samen te werken met gasten.

Een team maken
1. Klik in Teams op het tabblad **Teams** op **Deelnemen of maak een team** onder aan het linkerdeelvenster.
2. Klik **op Een team maken**.
3. Klik **op Een team helemaal opnieuw opbouwen.**
4. Kies **Privé** of **Openbaar**.
5. Typ een naam en beschrijving voor het team en klik op **Maken**.
6. Klik **op Overslaan**.

We nodigen gebruikers later uit. Vervolgens is het belangrijk om de instellingen voor het delen op siteniveau te controleren voor de SharePoint-site die aan het team is gekoppeld.

## <a name="sharepoint-site-level-sharing-settings"></a>Instellingen voor delen op SharePoint-siteniveau

Controleer de instellingen voor delen op siteniveau om er zeker van te zijn dat ze het gewenste type toegang voor dit team toestaan. Als u bijvoorbeeld de instellingen op organisatieniveau instelt op **Iedereen,** maar u wilt dat alle gasten zich voor dit team verifiëren, controleert u of de instellingen voor delen op siteniveau zijn ingesteld op **Nieuwe en bestaande gasten.**

![Schermafbeelding van de instellingen voor extern delen van SharePoint](../media/sharepoint-site-external-sharing-settings.png)


Instellingen voor delen op siteniveau instellen
1. Vouw **Sites** uit in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant en klik op **Delen**.
2. Selecteer de site voor het team dat u zojuist hebt gemaakt.
3. Klik op het lint op **Delen**.
4. Zorg ervoor dat delen is ingesteld op **iedereen** of **nieuwe en bestaande gasten**.
5. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="invite-users"></a>Gebruikers uitnodigen

Instellingen voor het delen van gasten zijn nu geconfigureerd, zodat u interne gebruikers en gasten aan uw team toevoegen. 

Interne gebruikers uitnodigen voor een team
1. Klik in het team op **Meer opties** en **\*\*\*** klik vervolgens op Lid **toevoegen**.
2. Typ de naam van de persoon die u wilt uitnodigen.
3. Klik **op Toevoegen**en klik vervolgens op **Sluiten**.

Gasten uitnodigen voor een team
1. Klik in het team op **Meer opties** en **\*\*\*** klik vervolgens op Lid **toevoegen**.
2. Typ het e-mailadres van de gast die u wilt uitnodigen.
3. Klik **op Gastgegevens bewerken**.
4. Typ de volledige naam van de gast en klik op het vinkje.
5. Klik **op Toevoegen**en klik vervolgens op **Sluiten**.

## <a name="see-also"></a>Zie ook

[Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers](best-practices-anonymous-sharing.md)

[Accidentele blootstelling aan bestanden beperken tijdens het delen met gasten](share-limit-accidental-exposure.md)

[Een beveiligde omgeving voor het delen met gasten maken](create-secure-guest-sharing-environment.md)

[Een B2B-extranet maken met beheerde gasten](b2b-extranet.md)
