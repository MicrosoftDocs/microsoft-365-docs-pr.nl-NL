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
localization_priority: Normal
f1.keywords: NOCSH
description: Meer informatie over de configuratiestappen van Microsoft 365 die nodig zijn voor het instellen van een team voor samenwerking aan taken, gesprekken en documentatie met gasten in Teams.
ms.openlocfilehash: 66c5692dd8cd233d8b3639f8ce0755ce51b60c0a
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233072"
---
# <a name="collaborate-with-guests-in-a-team"></a>Samenwerken met gasten in een team

Als u met gasten wilt samenwerken in documenten, taken en gesprekken, raden we u aan Microsoft Teams te gebruiken. Teams biedt alle samenwerkingsfuncties die beschikbaar zijn in Office en SharePoint met permanente chat en een aanpasbare en uitvouwbare set hulpprogramma's voor samenwerking in een geïntegreerde gebruikerservaring.

In dit artikel worden de configuratiestappen voor Microsoft 365 beschreven die nodig zijn om een team in te stellen voor samenwerking met gasten. Nadat u gasttoegang hebt geconfigureerd, kunt u gasten voor teams uitnodigen door de stappen te volgen in Gasten toevoegen [aan een team in Teams.](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f)

## <a name="video-demonstration"></a>Videodemonstratie

In deze video ziet u de configuratiestappen die in dit document worden beschreven.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Instellingen voor externe samenwerking van Azure

Delen in Microsoft 365 wordt op het hoogste niveau beheerd door de instellingen voor externe samenwerking van [B2B in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations) Als delen voor gasten is uitgeschakeld of beperkt in Azure AD, overschrijven deze instelling alle instellingen voor delen die u configureert in Microsoft 365.

Controleer de instellingen voor externe samenwerking in B2B om ervoor te zorgen dat delen met gasten niet wordt geblokkeerd.

![Schermafbeelding van de instellingenpagina voor organisatierelaties in Microsoft Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Instellingen voor externe samenwerking instellen

1. Meld u aan bij Azure Active Directory op [https://aad.portal.azure.com](https://aad.portal.azure.com) .
2. Klik in het linkernavigatiedeelvenster op **Azure Active Directory.**
3. Klik **op Externe identiteiten.**
4. Klik in **het scherm Aan de** slag in het linkernavigatiedeelvenster op Instellingen voor externe **samenwerking.**
5. Zorg ervoor **dat beheerders en gebruikers in** de rol van gast genodigden kunnen uitnodigen en dat Leden kunnen **uitnodigen** beide zijn ingesteld op **Ja.**
6. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

Let op de instellingen in **de sectie Beperkingen voor** samenwerking. Zorg ervoor dat de domeinen van de gasten met wie u wilt samenwerken, niet zijn geblokkeerd.

Als u met gasten van meerdere organisaties werkt, wilt u mogelijk de toegang tot adreslijstgegevens beperken. Hierdoor kunnen ze niet zien wie er nog meer gast is in de adreslijst. Selecteer hiervoor gastgebruikers die beperkte toegang hebben tot eigenschappen en het lidmaatschap van de instellingen voor adreslijstobjecten **of** de toegang van gastgebruikers **tot** eigenschappen en lidmaatschap van hun eigen adreslijstobjecten. 

## <a name="teams-guest-access-settings"></a>Instellingen voor gasttoegang in Teams

Teams heeft een schakelknop voor het in-/uitschakelen van gasten en er zijn diverse instellingen beschikbaar om te bepalen wat gasten in een team kunnen doen. De hoofdwisselknop, **Gasttoegang in Teams toestaan,** moet **zijn aan** staan om gasttoegang in Teams te kunnen werken.

Controleer of gasttoegang is ingeschakeld in Teams en controleer of de gastinstellingen worden aangepast op basis van uw zakelijke behoeften. Houd er rekening mee dat deze instellingen van invloed zijn op alle teams.

![Schermafbeelding van wisselknop Gasttoegang in Teams](../media/teams-guest-access-toggle-on.png)

Instellingen voor gasttoegang in Teams instellen

1. Meld u aan bij het Microsoft 365-beheercentrum op [https://admin.microsoft.com](https://admin.microsoft.com).
2. Klik in het linkernavigatiedeelvenster op **Alles weergeven.**
3. Klik onder **Beheercentra** op **Teams**.
4. Vouw in het teams-beheercentrum in het linkernavigatiedeelvenster **de instellingen** voor de hele organisatie uit en klik op **Gasttoegang.**
5. Zorg ervoor dat **Gasttoegang in Teams toestaan** is ingesteld op **Aan**.
6. Breng de gewenste wijzigingen aan in de extra gastinstellingen en klik vervolgens op **Opslaan**.

Zodra gasttoegang in Teams is ingeschakeld, kunt u desgewenst de gasttoegang tot afzonderlijke teams en de bijbehorende SharePoint-sites bepalen aan de hand van gevoeligheidslabels. Zie [Gevoeligheidslabels gebruiken om inhoud te beveiligen in Microsoft Teams, Microsoft 365-groepen en SharePoint-sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) voor meer informatie.

> [!NOTE]
> Het kan tot 24 uur duren voordat de instellingen voor teams-gasten actief worden nadat u deze hebt in schakeld.

## <a name="microsoft-365-groups-guest-settings"></a>Gastinstellingen voor Microsoft 365 Groepen

Teams gebruikt Microsoft 365 Groepen voor teamlidmaatschap. De gastinstellingen voor Microsoft 365 Groepen moeten zijn ingeschakeld om de gasttoegang in Teams te laten werken.

![Schermopname van gastinstellingen van Microsoft 365 Groepen in het Microsoft 365-beheercentrum](../media/office-365-groups-guest-settings.png)

Gastinstellingen voor Microsoft 365 Groepen instellen

1. Vouw in het Microsoft 365-beheercentrum in het linkernavigatiedeelvenster Instellingen **uit.**
2. Klik **op Organisatie-instellingen.**
3. Klik in de lijst op **Microsoft 365 Groepen.**
4. Zorg ervoor dat groepseigenaren personen van buiten uw organisatie als  gast aan **Microsoft 365** Groepen kunnen toevoegen en dat leden van de gastgroep toegang hebben tot de inhoud van de groep beide zijn ingeschakeld.
5. Als u wijzigingen hebt aangebracht, klikt u **op Wijzigingen opslaan.**


## <a name="sharepoint-organization-level-sharing-settings"></a>Instellingen voor delen op organisatieniveau van SharePoint

Inhoud van Teams, zoals bestanden, mappen en lijsten, worden allemaal opgeslagen in SharePoint. Om gasten toegang te geven tot deze items in Teams, moeten de instellingen voor delen op organisatieniveau toestaan dat ze kunnen delen met gasten.

De instellingen op organisatieniveau bepalen welke instellingen beschikbaar zijn voor afzonderlijke sites, inclusief sites die zijn gekoppeld aan teams. Site-instellingen mogen niet meer ruim zijn dan de instellingen op organisatieniveau.

Als u het delen van bestanden en mappen met niet-geauteerde personen wilt toestaan, kiest u **Iedereen.** Als u ervoor wilt zorgen dat alle gasten zich moeten verifiëren, kiest u **Nieuwe en bestaande gasten.** Kies de meest recente instelling die nodig is voor elke site in uw organisatie.

![Schermafbeelding van de instellingen voor delen op organisatieniveau van SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


Instellingen voor delen op organisatieniveau instellen in SharePoint

1. Klik in het Microsoft 365-beheercentrum in het linkernavigatiedeelvenster, onder **Beheercentra,** op **SharePoint.**
2. Vouw in het SharePoint-beheercentrum in het linkernavigatiedeelvenster **Beleid** uit en klik op **Delen.**
3. Zorg ervoor dat extern delen voor SharePoint is ingesteld op **Iedereen** of **Nieuw en bestaande gasten.**
4. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.


## <a name="sharepoint-organization-level-default-link-settings"></a>Standaardkoppelingsinstellingen op organisatieniveau in SharePoint

De standaardinstellingen voor bestands- en mapkoppelingen bepalen de koppelingsoptie die standaard aan gebruikers wordt weergegeven wanneer ze een bestand of map delen. Gebruikers kunnen desgewenst het koppelingstype wijzigen in een van de andere opties voordat ze gaan delen.

Houd er rekening mee dat deze instelling van invloed is op alle teams en SharePoint-sites in uw organisatie.

Kies een van de volgende koppelingstypen die standaard wordt geselecteerd wanneer gebruikers bestanden en mappen delen:

- **Iedereen met de koppeling:** kies deze optie als u verwacht dat er veel bestanden en mappen niet geauverticeerd worden gedeeld. Als u iedereen-koppelingen *wilt* toestaan, maar u zich zorgen maakt over onbedoeld niet-geauteerde delen, kunt u een van de andere opties als standaardwaarde gebruiken. Dit type koppeling is alleen beschikbaar als delen met iedereen **is** ingeschakeld.
- **Alleen personen in uw organisatie:** kies deze optie als u verwacht dat de meeste bestanden en mappen worden gedeeld met personen binnen uw organisatie.
- **Specifieke personen:** overweeg deze optie als u veel bestanden en mappen met gasten wilt delen. Dit type koppeling werkt met gasten en vereist verificatie.
 
![Schermafbeelding van de instellingen voor delen van bestanden en mappen op organisatieniveau van SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


De standaardkoppelingsinstellingen op organisatieniveau van SharePoint instellen

1. Ga naar de pagina Delen in het SharePoint-beheercentrum.
2. Selecteer **onder Koppelingen naar bestanden en** mappen de standaardkoppeling voor delen die u wilt gebruiken.
3. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="create-a-team"></a>Een team maken

De volgende stap is het maken van het team dat u wilt gebruiken om samen te werken met gasten.

Een team maken
1. Klik in Teams op het **tabblad Teams** op Deelnemen of maak een **team** onderaan het linkerdeelvenster.
2. Klik **op Een team maken.**
3. Klik **op Een nieuw team maken.**
4. Kies **Privé** of **Openbaar.**
5. Typ een naam en beschrijving voor het team en klik op **Maken.**
6. Klik **op Overslaan.**

We nodigen gebruikers later uit. Vervolgens is het belangrijk dat u de instellingen voor delen op siteniveau controleert voor de SharePoint-site die aan het team is gekoppeld.

## <a name="sharepoint-site-level-sharing-settings"></a>Instellingen voor delen op siteniveau van SharePoint

Controleer de instellingen voor delen op siteniveau om er zeker van te zijn dat het type toegang is toegestaan dat u voor dit team wilt gebruiken. Als u bijvoorbeeld de instellingen op organisatieniveau in stelt op **Iedereen,** maar u wilt dat alle gasten worden geverifieerd voor dit team, moet u ervoor zorgen dat de instellingen voor delen op siteniveau zijn ingesteld op Nieuwe en bestaande **gasten.**

![Schermafbeelding van de instellingen voor extern delen van SharePoint](../media/sharepoint-site-external-sharing-settings.png)

Instellingen voor delen op siteniveau instellen
1. Vouw in het SharePoint-beheercentrum in het linkernavigatiedeelvenster **Sites uit en** klik op Actieve **sites.**
2. Selecteer de site voor het team dat u zojuist hebt gemaakt.
3. Klik op ... en kies **Delen.**
4. Zorg ervoor dat delen is ingesteld **op Iedereen** of Nieuw en **bestaande gasten.**
5. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="invite-users"></a>Gebruikers uitnodigen

Instellingen voor het delen van gasten zijn nu geconfigureerd, zodat u kunt beginnen met het toevoegen van interne gebruikers en gasten aan uw team. 

Interne gebruikers uitnodigen voor een team
1. Klik in het team op **Meer opties** ( ) en klik vervolgens op **\*\*\*** Lid **toevoegen.**
2. Typ de naam van de persoon die u wilt uitnodigen.
3. Klik **op** Toevoegen en klik vervolgens op **Sluiten.**

Gasten uitnodigen voor een team
1. Klik in het team op **Meer opties** ( ) en klik vervolgens op **\*\*\*** Lid **toevoegen.**
2. Typ het e-mailadres van de gast die u wilt uitnodigen.
3. Klik **op Gastgegevens bewerken.**
4. Typ de volledige naam van de gast en klik op het vinkje.
5. Klik **op** Toevoegen en klik vervolgens op **Sluiten.**

## <a name="see-also"></a>Zie ook

[Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers](best-practices-anonymous-sharing.md)

[Accidentele blootstelling aan bestanden beperken tijdens het delen met gasten](share-limit-accidental-exposure.md)

[Een beveiligde omgeving voor het delen met gasten maken](create-secure-guest-sharing-environment.md)

[Een B2B-extranet maken met beheerde gasten](b2b-extranet.md)

[Integratie van SharePoint en OneDrive met Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)

[Opties voor delen worden grijs 2010 wanneer u deelt vanuit SharePoint of OneDrive](https://docs.microsoft.com/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)
