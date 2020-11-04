---
title: Met gasten samenwerken in een team
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
description: Meer informatie over de Microsoft 365-configuratiestappen die nodig zijn voor het instellen van een team voor taak, discussie en de samenwerking van documenten met gasten in teams.
ms.openlocfilehash: b4eea473f03441144a0236ec53dcecde9080fc7a
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906857"
---
# <a name="collaborate-with-guests-in-a-team"></a>Met gasten samenwerken in een team

Als u met gasten in documenten, taken en gesprekken moet samenwerken, is het raadzaam Microsoft teams te gebruiken. Teams biedt alle samenwerkingsfuncties die beschikbaar zijn in Office en SharePoint met permanente chat en een aanpasbare en uitbreidbare set samenwerkingsprogramma's in een geïntegreerde gebruikerservaring.

In dit artikel worden 365 de stappen beschreven die u moet uitvoeren om een team voor samenwerking met gasten in te stellen.

## <a name="video-demonstration"></a>Videodemonstratie

In deze video ziet u de configuratiestappen die in dit document worden beschreven.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a>Instellingen van Azure organisatie relaties

Delen in Microsoft 365 wordt bepaald met het hoogste niveau van de [instellingen voor organisatie relaties in azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations). Als gasten delen is uitgeschakeld of niet beschikbaar is in azure AD, worden de instellingen voordelen overschreven die u configureert in Microsoft 365.

Controleer de instellingen van de organisatie om te controleren of delen met gasten niet is geblokkeerd.

![Schermafbeelding van de instellingenpagina voor organisatierelaties in Microsoft Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Instellingen voor organisatie relaties instellen

1. Meld u aan bij Azure Active Directory [https://aad.portal.azure.com](https://aad.portal.azure.com) .
2. Klik in het linker navigatiedeelvenster op **Azure Active Directory**.
3. Klik op **externe identiteiten**.
4. Klik in het scherm aan de **slag** in het linker navigatiedeelvenster op **instellingen voor externe samenwerking**.
5. Zorg ervoor dat **beheerders en gebruikers in de rol gast uitnodiging kunnen uitnodigen** en dat **leden kunnen uitnodigen** zijn ingesteld op **Ja**.
6. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

Let op de instellingen in de sectie **samenwerkings beperkingen** . Zorg ervoor dat de domeinen van de gasten waarmee u wilt samenwerken, niet zijn geblokkeerd.

Als u met gasten in meerdere organisaties werkt, is het raadzaam om de toegang van Directory-gegevens te beperken. Hiermee kunt u voorkomen dat ze zien welke iemand anders een gast is in de adreslijst. Als u dit wilt doen, selecteert u onder **toegangsbeperkingen** voor gastgebruikers de optie **gastgebruikers beperkte toegang tot eigenschappen en lidmaatschap van adreslijst objecten** of **toegang voor gastgebruikers is beperkt tot eigenschappen en lidmaatschap van eigen directoryobjecten**.

## <a name="teams-guest-access-settings"></a>Instellingen voor gasttoegang voor teams

Teams heeft een schakeloptie voor het in-en uitschakelen van een gast verbinding en een verscheidenheid aan instellingen die beschikbaar zijn om te bepalen wat gasten in een team kunnen doen. De schakeloptie voor het inschakelen van **gasttoegang in teams** moet zijn **ingeschakeld** voor gasttoegang om in teams te kunnen werken.

Zorg ervoor dat gasttoegang is ingeschakeld in teams en breng de gewenste wijzigingen aan in de gastinstellingen op basis van de behoeften van uw bedrijf. Houd er rekening mee dat deze instellingen van invloed zijn op alle teams.

![Schermafbeelding van wisselknop Gasttoegang in Teams](../media/teams-guest-access-toggle-on.png)

Instellingen voor gasttoegang in Teams instellen

1. Meld u aan bij het Microsoft 365-beheercentrum op [https://admin.microsoft.com](https://admin.microsoft.com).
2. Klik in het linker navigatiedeelvenster op **AllesWeergeven**.
3. Klik onder **Beheercentra** op **Teams**.
4. Vouw in het team centrum voor teams in het linker navigatiedeelvenster **instellingen voor de gehele organisatie** uit en klik op **gasttoegang**.
5. Zorg ervoor dat **Gasttoegang in Teams toestaan** is ingesteld op **Aan**.
6. Breng de gewenste wijzigingen aan in de extra gastinstellingen en klik vervolgens op **Opslaan**.

> [!NOTE]
> Het kan tot 24 uur duren voordat de instellingen van de team gast actief raken nadat u deze hebt ingeschakeld.

## <a name="microsoft-365-groups-guest-settings"></a>Gastinstellingen voor Microsoft 365-groepen

Teams gebruikt Microsoft 365-groepen voor lidmaatschap van een team. De instellingen voor gasttoegang in Microsoft 365 groepen moeten zijn ingeschakeld, zodat gasttoegang in teams kan werken.

![Schermopname van gastinstellingen van Microsoft 365 Groepen in het Microsoft 365-beheercentrum](../media/office-365-groups-guest-settings.png)

De gastinstellingen van Microsoft 365 groepen instellen

1. In het Microsoft 365-Beheercentrum, in het linker navigatiedeelvenster, vouwt u **instellingen** uit.
2. Klik op **instellingen voor organisatie**.
3. Klik in de lijst op **Microsoft 365 groepen**.
4. Zorg ervoor dat de selectievakjes **eigenaren van gebruikers buiten uw organisatie toevoegen aan Microsoft 365-groepen als gasten** en de selectievakjes voor **groepsleden toegang krijgen tot groepsinhoud** beide zijn ingeschakeld.
5. Als u wijzigingen hebt aangebracht, klikt u op **wijzigingen opslaan**.


## <a name="sharepoint-organization-level-sharing-settings"></a>Instellingen voordelen van SharePoint-organisatieniveau

Inhoud van teams, zoals bestanden, mappen en lijsten, worden allemaal opgeslagen in SharePoint. Als u wilt dat gasten toegang hebben tot deze items in teams, moet u de instellingen voordelen van SharePoint op organisatieniveau toestaan voordelen met gasten.

De instellingen op organisatieniveau bepalen welke instellingen beschikbaar zijn voor afzonderlijke sites, waaronder sites die zijn gekoppeld aan teams. Site-instellingen kunnen niet hoger zijn dan de instellingen op organisatieniveau.

Als u het delen van bestanden en mappen met niet-geverifieerde personen wilt toestaan, kiest u **iedereen**. Als u ervoor wilt zorgen dat alle gasten verificatie verifiëren, kiest u **nieuwe en bestaande gasten**. Kies de meest strikte instelling die moet worden gebruikt door alle sites in uw organisatie.

![Schermafbeelding van de instellingen voor delen op organisatieniveau in SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


Instellingen voordelen van SharePoint op organisatieniveau instellen

1. Klik in het Microsoft 365-Beheercentrum, in het linker navigatiedeelvenster, onder **beheer centra** op **SharePoint**.
2. Vouw in het SharePoint-Beheercentrum in het linker navigatievenster **beleidsregels** uit en klik vervolgens op **delen**.
3. Zorg ervoor dat extern delen voor SharePoint is ingesteld op **iedereen** of **nieuwe en bestaande gasten**.
4. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.


## <a name="sharepoint-organization-level-default-link-settings"></a>Standaard koppelingsinstellingen op SharePoint-organisatieniveau

De standaardinstellingen voor het koppelen van bestanden en mappen bepalen de koppelingsoptie die standaard wordt getoond aan gebruikers wanneer ze een bestand of map delen. Gebruikers kunnen het koppelingstype wijzigen in een van de andere opties voordat u het deelt.

Houd er rekening mee dat deze instelling van invloed is op alle teams en SharePoint-sites in uw organisatie.

Kies een van de volgende koppelingstypen die standaard worden geselecteerd wanneer gebruikers bestanden en mappen delen:

- **Iedereen met de koppeling** : Kies deze optie als u verwacht dat u niet-geverifieerde bestanden en mappen wilt delen. Als u iedereen wilt toestaan die wel of niet is gemachtigd voor het delen van *onbevoegd* delen, kunt u het beste een van de andere opties als standaard instellen. Dit koppelingstype is alleen beschikbaar als **iedereen** het delen heeft toegestaan.
- **Alleen personen in uw organisatie** : Kies deze optie als u verwacht dat u de meeste bestanden en mappen wilt delen met personen binnen uw organisatie.
- **Specifieke personen** : Houd deze optie ingedrukt als u verwacht dat u een groot aantal bestanden en mappen deelt met gasten. Dit type koppeling werkt met gasten en vereist ze voor verificatie.
 
![Schermafbeelding van de instellingen voor delen van bestanden en mappen op organisatieniveau van SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


De standaardinstellingen voor de koppeling naar het SharePoint-organisatieniveau instellen

1. Ga naar de pagina delen in het SharePoint-Beheercentrum.
2. Selecteer onder **koppelingen voor bestanden en mappen** de standaardkoppeling voordelen die u wilt gebruiken.
3. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="create-a-team"></a>Een team maken

De volgende stap is het maken van het team dat u wilt gebruiken om samen te werken met gasten.

Een team maken
1. Klik in teams op het tabblad **teams** op **lid worden van een team of een team maken** onderaan in het linkerdeelvenster.
2. Klik op **een team maken**.
3. Klik op **zelf een team samenstellen**.
4. Kies **privé** of **openbaar**.
5. Typ een naam en beschrijving voor het team en klik vervolgens op **maken**.
6. Klik op **overslaan**.

We nodigen later gebruikers uit. Vervolgens moet u de instellingen voordelen op siteniveau controleren voor de SharePoint-site die is gekoppeld aan het team.

## <a name="sharepoint-site-level-sharing-settings"></a>Instellingen voordelen op SharePoint-siteniveau

Controleer de instellingen voordelen op siteniveau om ervoor te zorgen dat u het gewenste type toegang toestaat voor dit team. Als u bijvoorbeeld de instellingen op organisatieniveau instelt op **iedereen** , maar u wilt dat alle gasten verificatie voor dit team hebben, controleert u of de instellingen voordelen op het siteniveau zijn ingesteld op **nieuwe en bestaande gasten**.

![Schermafbeelding van de instellingen voor extern delen van SharePoint](../media/sharepoint-site-external-sharing-settings.png)


Instellingen voordelen op siteniveau instellen
1. Vouw in het SharePoint-Beheercentrum in het linker navigatievenster **sites** uit en klik op **actieve sites**.
2. Selecteer de site voor het team dat u zojuist hebt gemaakt.
3. Klik op... en kies **delen**.
4. Zorg ervoor dat delen is ingesteld op **iedereen** of **nieuwe en bestaande gasten**.
5. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="invite-users"></a>Gebruikers uitnodigen

Instellingen voor het delen van gasten zijn nu geconfigureerd, zodat u interne gebruikers en gasten aan uw team kunt toevoegen. 

Interne gebruikers uitnodigen voor een team
1. Klik in het team op **meer opties** ( **\*\*\*** ) en klik vervolgens op **lid toevoegen**.
2. Typ de naam van de persoon die u wilt uitnodigen.
3. Klik op **toevoegen** en klik vervolgens op **sluiten**.

Gasten uitnodigen voor een team
1. Klik in het team op **meer opties** ( **\*\*\*** ) en klik vervolgens op **lid toevoegen**.
2. Voer het e-mailadres in van de gast die u wilt uitnodigen.
3. Klik op **gast gegevens bewerken**.
4. Typ de volledige naam van de gast en klik op het vinkje.
5. Klik op **toevoegen** en klik vervolgens op **sluiten**.

## <a name="see-also"></a>Zie ook

[Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers](best-practices-anonymous-sharing.md)

[Accidentele blootstelling aan bestanden beperken tijdens het delen met gasten](share-limit-accidental-exposure.md)

[Een beveiligde omgeving voor het delen met gasten maken](create-secure-guest-sharing-environment.md)

[Een B2B-extranet maken met beheerde gasten](b2b-extranet.md)

[Integratie van SharePoint en OneDrive met Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
