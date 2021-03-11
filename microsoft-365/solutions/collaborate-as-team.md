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
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Priority
f1.keywords: NOCSH
description: Lees meer over de Microsoft 365-configuratiestappen die nodig zijn om een team in te stellen voor samenwerking aan taken, gesprekken en documentatie met gasten in Teams.
ms.openlocfilehash: 986f9c1f343c8ccc3d76557291938d170923c89b
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712316"
---
# <a name="collaborate-with-guests-in-a-team"></a>Samenwerken met gasten in een team

Als u samen met gasten aan verschillende documenten, taken en gesprekken wilt werken, raden we u aan Microsoft Teams te gebruiken. Teams biedt alle samenwerkingsfuncties die beschikbaar zijn in Office en SharePoint met een permanente chatfunctie en een aanpasbare en uitbreidbare set samenwerkingshulpmiddelen in een geïntegreerde gebruikerservaring.

In dit artikel worden de benodigde Microsoft 365-configuratiestappen beschreven voor het instellen van een team voor samenwerking met gasten. Nadat u gasttoegang hebt geconfigureerd, kunt u gasten uitnodigen voor teams door de stappen te volgen in [Gasten toevoegen aan een team in Teams](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f).

## <a name="video-demonstration"></a>Videodemonstratie

In deze video ziet u de configuratiestappen die in dit document worden beschreven.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Azure External-samenwerkingsinstellingen

Delen in Microsoft 365 wordt op het hoogste niveau bepaald door de [B2B-instellingen voor externe samenwerking in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations). Als delen met gasten is uitgeschakeld of wordt beperkt in Azure AD, overschrijft deze instelling alle instellingen voor delen die u configureert in Microsoft 365.

Controleer de B2B-instellingen voor externe samenwerking om ervoor te zorgen dat delen met gasten niet wordt geblokkeerd.

![Schermafbeelding van de instellingenpagina voor organisatierelaties in Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Instellingen voor externe samenwerking instellen

1. Meld u aan bij Azure Active Directory op [https://aad.portal.azure.com](https://aad.portal.azure.com).
2. Klik in het linkernavigatiedeelvenster op **Azure Active Directory**.
3. Klik **Externe identiteiten**.
4. Klik in het linkernavigatiedeelvenster **Aan de slag** op **Instellingen voor externe samenwerking**.
5. Zorg ervoor dat **Beheerders en gebruikers in de rol van Afzender van gastuitnodigingen kunnen uitnodigingen verzenden** en **Leden kunnen uitnodigingen verzenden** beide zijn ingesteld op **Ja**.
6. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

Let op de instellingen in de sectie **Samenwerkingsbeperkingen**. Zorg ervoor dat de domeinen van de gasten met wie u wilt samenwerken, niet worden geblokkeerd.

Als u met gasten van meerdere organisaties werkt, wilt u mogelijk hun toegang tot adreslijstgegevens beperken. Hiermee voorkomt u dat ze kunnen zien wie er nog meer een gast is in de adreslijst. Hiervoor selecteert u onder **Toegangsbeperkingen voor gastgebruikers** de optie **Gastgebruikers hebben beperkte toegang tot eigenschappen en lidmaatschap van instellingen voor adreslijstobjecten** of **Toegang van gastgebruikers is beperkt tot eigenschappen en lidmaatschappen van hun eigen adreslijstobjecten**.

## <a name="teams-guest-access-settings"></a>Instellingen voor gasttoegang in Teams

Teams heeft een hoofdoptie voor het in- en uitschakelen van gasttoegang en diverse instellingen die beschikbaar om te bepalen wat gasten in een team kunnen doen. De hoofdoptie, **Gasttoegang toestaan in Teams**, moet **aan** zijn voor gasttoegang in Teams.

Controleer of gasttoegang is ingeschakeld in Teams en pas de instellingen voor gasten aan op basis van de behoeften van uw bedrijf. Houd er rekening mee dat deze instellingen van invloed zijn op alle teams.

![Schermafbeelding van wisselknop Gasttoegang in Teams](../media/teams-guest-access-toggle-on.png)

Instellingen voor gasttoegang in Teams instellen

1. Meld u aan bij het Microsoft 365-beheercentrum op [https://admin.microsoft.com](https://admin.microsoft.com).
2. Klik in het navigatievenster aan de linkerkant op **Alles weergeven**.
3. Klik onder **Beheercentra** op **Teams**.
4. Vouw in het Teams-beheercentrum in het linkernavigatievenster **Instellingen voor hele organisatie** uit en klik vervolgens op **Gasttoegang**.
5. Zorg ervoor dat **Gasttoegang in Teams toestaan** is ingesteld op **Aan**.
6. Breng de gewenste wijzigingen aan in de extra gastinstellingen en klik vervolgens op **Opslaan**.

Wanneer gasttoegang in Teams is ingeschakeld, kunt u desgewenst gasttoegang tot afzonderlijke teams en de bijbehorende SharePoint-sites bepalen met behulp van gevoeligheidslabels. Zie [Gevoeligheidslabels gebruiken om inhoud te beveiligen in Microsoft Teams, Microsoft 365-groepen en SharePoint-sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) voor meer informatie.

> [!NOTE]
> Het kan 24 uur duren voordat de instellingen voor gasten in Teams actief worden nadat u deze hebt ingeschakeld.

## <a name="microsoft-365-groups-guest-settings"></a>Gastinstellingen van Microsoft 365 Groepen

Teams gebruikt Microsoft 365 Groepen voor teamlidmaatschap. De gastinstellingen voor Microsoft 365 Groepen moeten zijn ingeschakeld om gasttoegang in Teams te laten werken.

![Schermopname van gastinstellingen van Microsoft 365 Groepen in het Microsoft 365-beheercentrum](../media/office-365-groups-guest-settings.png)

Gastinstellingen van Microsoft 365 Groepen instellen

1. Vouw in het Microsoft 365-beheercentrum **Instellingen** uit in het linkernavigatievenster.
2. Klik op **Organisatie-instellingen**.
3. Klik in de lijst op **Microsoft 365 Groepen**.
4. Zorg ervoor dat de selectievakjes **Groepseigenaren toestaan personen van buiten de organisatie als gast aan Microsoft 365 Groepen toe te voegen** en **Gastgroepsleden toegang geven tot groepsinhoud** beide zijn ingeschakeld.
5. Als u wijzigingen hebt aangebracht, klikt u op **Wijzigingen opslaan**.


## <a name="sharepoint-organization-level-sharing-settings"></a>Instellingen voor delen op organisatieniveau van SharePoint

Alle inhoud van Teams (zoals bestanden, mappen en lijsten) wordt opgeslagen in SharePoint. Om gasten toegang te geven tot deze items in Teams, moeten de SharePoint-instellingen voor delen op organisatieniveau delen met gasten toestaan.

De instellingen op organisatieniveau bepalen welke instellingen beschikbaar zijn voor afzonderlijke sites, waaronder sites die zijn gekoppeld aan teams. Site-instellingen mogen niet meer toestaan dan de instellingen op organisatieniveau.

Als u delen van bestanden en mappen met niet-geverifieerde personen wilt toestaan, kiest u **Iedereen**. Als u ervoor wilt zorgen dat alle gasten zich moeten verifiëren, kiest u **Nieuwe en bestaande gasten**. Kies de ruimste instelling die nodig is voor de sites in uw organisatie.

![Schermafbeelding van de instellingen voor delen op organisatieniveau van SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


Instellingen voor delen op organisatieniveau van SharePoint instellen

1. In het Microsoft 365-beheercentrum klikt u onder **Beheercentra** op **SharePoint**.
2. Vouw in het SharePoint-beheercentrum **Beleid** uit in het navigatievenster aan de linkerkant en klik op **Delen**.
3. Zorg ervoor dat extern delen voor SharePoint is ingesteld op **Iedereen** of **Nieuwe en bestaande gasten**.
4. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.


## <a name="sharepoint-organization-level-default-link-settings"></a>Standaardkoppelingsinstellingen op organisatieniveau van SharePoint

De standaardkoppelingsinstellingen voor bestanden en mappen bepalen de koppelingsoptie die standaard voor gebruikers wordt weergegeven wanneer ze een bestand of map delen. Gebruikers kunnen voor het delen desgewenst het koppelingstype wijzigen in een van de andere opties.

Houd er rekening mee dat deze instelling van invloed is op alle teams en SharePoint-sites in uw organisatie.

Kies een van de volgende koppelingstypen die standaard wordt geselecteerd wanneer gebruikers bestanden en mappen delen:

- **Iedereen met de koppeling** - Kies deze optie als u verwacht dat u met veel niet-geverifieerde mensen gaat delen. Als u *Iedereen*-koppelingen wilt toestaan, maar u zich zorgen maakt over onbedoeld niet-geverifieerd delen, kunt u een van de andere opties als standaardoptie gebruiken. Dit koppelingstype is alleen beschikbaar als u **Iedereen** hebt ingeschakeld.
- **Alleen personen in uw organisatie**: kies deze optie als u verwacht dat de meeste bestanden en mappen worden gedeeld met personen binnen uw organisatie.
- **Specifieke personen** - overweeg deze optie als u verwacht veel bestanden en mappen te delen met gasten. Dit type koppeling werkt met gasten en vereist verificatie.
 
![Schermafbeelding van de instellingen voor delen van bestanden en mappen op organisatieniveau van SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


Standaardkoppelingsinstellingen op organisatieniveau van SharePoint instellen

1. Navigeer naar de pagina Delen in het SharePoint-beheercentrum.
2. Selecteer onder **Koppelingen naar bestanden en mappen** de standaardkoppeling voor delen die u wilt gebruiken.
3. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="create-a-team"></a>Een team maken

De volgende stap is het maken van het team dat u wilt gebruiken voor samenwerking met gasten.

Een team maken
1. Klik in Teams op het tabblad **Teams** op **Deelnemen aan een team of een team maken** onderin het linkerdeelvenster.
2. Klik op **Een team maken**.
3. Klik op **Een volledig nieuw team maken**.
4. Kies **Privé** of **Openbaar**.
5. Typ een naam en beschrijving voor het team en klik vervolgens op **Maken**.
6. Klik op **Overslaan**.

We nodigen gebruikers later uit. Vervolgens is het belangrijk dat u de instellingen voor delen op siteniveau controleert voor de SharePoint-site die is gekoppeld aan het team.

## <a name="sharepoint-site-level-sharing-settings"></a>Instellingen voor het delen op siteniveau in SharePoint

Controleer de instellingen voor delen op siteniveau om er zeker van te zijn dat het type toegang wordt toegestaan dat u voor dit team wilt gebruiken. Als u bijvoorbeeld de instellingen op organisatieniveau instelt op **Iedereen**, maar u wilt dat alle gasten zich verifiëren voor dit team, zorg er dan voor dat de instellingen voor delen op siteniveau zijn ingesteld op **Nieuwe en bestaande gasten**.

![Schermafbeelding van de instellingen voor extern delen van SharePoint](../media/sharepoint-site-external-sharing-settings.png)

Instellingen voor delen op siteniveau instellen
1. Vouw in het SharePoint-beheercentrum **Sites** uit in het navigatievenster aan de linkerkant en klik op **Actieve sites**.
2. Selecteer de site voor het team dat u zojuist hebt gemaakt.
3. Klik ... en kies **Delen**.
4. Zorg ervoor dat delen is ingesteld op **Iedereen** of **Nieuwe en bestaande gasten**.
5. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="invite-users"></a>Gebruikers uitnodigen

Instellingen voor het delen met gasten zijn nu geconfigureerd, zodat u interne gebruikers en gasten kunt toevoegen aan uw team. 

Interne gebruikers uitnodigen voor een team
1. Klik in het team op **Meer opties** (**\*\*\***), en klik vervolgens op **Lid toevoegen**.
2. Typ de naam van de persoon die u wilt uitnodigen.
3. Klik op **Toevoegen** en klik op **Sluiten**.

Gasten uitnodigen voor een team
1. Klik in het team op **Meer opties** (**\*\*\***), en klik vervolgens op **Lid toevoegen**.
2. Typ het e-mailadres van de gast die u wilt uitnodigen.
3. Klik op **Gegevens van gasten bewerken**.
4. Typ de volledige naam van de gast en klik op het vinkje.
5. Klik op **Toevoegen** en klik op **Sluiten**.

## <a name="see-also"></a>Zie ook

[Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers](best-practices-anonymous-sharing.md)

[Accidentele blootstelling aan bestanden beperken tijdens het delen met gasten](share-limit-accidental-exposure.md)

[Een beveiligde omgeving voor het delen met gasten maken](create-secure-guest-sharing-environment.md)

[Een B2B-extranet maken met beheerde gasten](b2b-extranet.md)

[Integratie van SharePoint en OneDrive met Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)

[Opties voor delen worden grijs wanneer u deelt vanuit SharePoint of OneDrive](https://docs.microsoft.com/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)
