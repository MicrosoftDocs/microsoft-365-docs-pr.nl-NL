---
title: Samenwerken met gasten op een site
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
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
description: Meer informatie over de configuratiestappen van Microsoft 365 die nodig zijn om een SharePoint-site in te stellen voor samenwerking met gasten.
ms.openlocfilehash: fd3cf55b3d95a5c79b9bd4d7c55855f7d73fc0d2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904646"
---
# <a name="collaborate-with-guests-in-a-site"></a>Samenwerken met gasten op een site

Als u met gasten moet samenwerken in documenten, gegevens en lijsten, kunt u een SharePoint-site gebruiken. Moderne SharePoint-sites zijn verbonden met Microsoft 365 Groepen en kunnen het lidmaatschap van de site beheren en extra samenwerkingshulpmiddelen bieden, zoals een gedeeld postvak en een agenda.

In dit artikel volgen we de configuratiestappen van Microsoft 365 die nodig zijn om een SharePoint-site in te stellen voor samenwerking met gasten.

## <a name="video-demonstration"></a>Videodemonstratie

In deze video ziet u de configuratiestappen die in dit document worden beschreven.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Externe samenwerkingsinstellingen voor Azure

Delen in Microsoft 365 wordt op het hoogste niveau bepaald door de [B2B-instellingen voor externe samenwerking in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations). Als delen met gasten is uitgeschakeld of wordt beperkt in Azure AD, overschrijft deze instelling alle instellingen voor delen die u configureert in Microsoft 365.

Controleer de B2B-instellingen voor externe samenwerking om ervoor te zorgen dat delen met gasten niet wordt geblokkeerd.

![Schermafbeelding van de pagina Externe samenwerkingsinstellingen voor Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Instellingen voor externe samenwerking instellen

1. Meld u aan bij Azure Active Directory op [https://aad.portal.azure.com](https://aad.portal.azure.com).
2. Klik in het linkernavigatiedeelvenster op **Azure Active Directory**.
3. Klik **Externe identiteiten**.
4. Klik in het linkernavigatiedeelvenster **Aan de slag** op **Instellingen voor externe samenwerking**.
5. Zorg ervoor dat **Beheerders en gebruikers in de rol van Afzender van gastuitnodigingen kunnen uitnodigingen verzenden** en **Leden kunnen uitnodigingen verzenden** beide zijn ingesteld op **Ja**.
6. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

Let op de instellingen in de sectie **Samenwerkingsbeperkingen**. Zorg ervoor dat de domeinen van de gasten met wie u wilt samenwerken, niet worden geblokkeerd.

Als u met gasten van meerdere organisaties werkt, wilt u mogelijk hun toegang tot adreslijstgegevens beperken. Hiermee voorkomt u dat ze kunnen zien wie er nog meer een gast is in de adreslijst. Hiervoor selecteert u onder **Toegangsbeperkingen voor gastgebruikers** de optie **Gastgebruikers hebben beperkte toegang tot eigenschappen en lidmaatschap van instellingen voor adreslijstobjecten** of **Toegang van gastgebruikers is beperkt tot eigenschappen en lidmaatschappen van hun eigen adreslijstobjecten**.

## <a name="microsoft-365-groups-guest-settings"></a>Gastinstellingen van Microsoft 365 Groepen

Moderne SharePoint-sites gebruiken Microsoft 365 Groepen om sitetoegang te bepalen. De gastinstellingen voor Microsoft 365 Groepen moeten zijn ingeschakeld zodat gasttoegang op SharePoint-sites kan werken.

![Schermopname van gastinstellingen van Microsoft 365 Groepen in het Microsoft 365-beheercentrum](../media/office-365-groups-guest-settings.png)

Gastinstellingen van Microsoft 365 Groepen instellen

1. Vouw in het Microsoft 365-beheercentrum **Instellingen** uit in het linkernavigatievenster.
2. Klik op **Organisatie-instellingen**.
3. Klik in de lijst op **Microsoft 365 Groepen**.
4. Zorg ervoor dat de selectievakjes **Groepseigenaren toestaan personen van buiten de organisatie als gast aan Microsoft 365 Groepen toe te voegen** en **Gastgroepsleden toegang geven tot groepsinhoud** beide zijn ingeschakeld.
5. Als u wijzigingen hebt aangebracht, klikt u op **Wijzigingen opslaan**.

## <a name="sharepoint-organization-level-sharing-settings"></a>SharePoint-instellingen voor delen op organisatieniveau

Om ervoor te zorgen dat gasten toegang hebben tot SharePoint-sites, moeten de sharePoint-instellingen voor delen op organisatieniveau toestaan dat ze kunnen delen met gasten.

De instellingen op organisatieniveau bepalen de instellingen die beschikbaar zijn voor afzonderlijke sites. Site-instellingen mogen niet meer toestaan dan de instellingen op organisatieniveau.

Als u niet-genautisch bestand en delen van mappen wilt toestaan, kiest u **Iedereen**. Als u ervoor wilt zorgen dat alle personen buiten uw organisatie zich moeten verifiëren, kiest u **Nieuwe en bestaande gasten.** Kies de ruimste instelling die nodig is voor de sites in uw organisatie.

![Schermafbeelding van de instellingen voor delen op organisatieniveau van SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


Instellingen voor delen op organisatieniveau van SharePoint instellen

1. In het Microsoft 365-beheercentrum klikt u onder **Beheercentra** op **SharePoint**.
2. Klik in het SharePoint-beheercentrum in het linkernavigatiedeelvenster onder **Beleid** op **Delen.**
3. Zorg ervoor dat extern delen voor SharePoint is ingesteld op **Iedereen** of **Nieuwe en bestaande gasten**.
4. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="create-a-site"></a>Een site maken

De volgende stap is het maken van de site die u wilt gebruiken om samen te werken met gasten.

Een site maken
1. Klik in het SharePoint-beheercentrum onder **Sites** op **Actieve sites**.
2. Klik op **Maken**.
3. Klik **op Teamsite.**
4. Typ een sitenaam en voer een naam in voor de groepseigenaar (site-eigenaar).
5. Kies **onder Geavanceerde** instellingen of u wilt dat deze site openbaar of privé is.
6. Klik op **Volgende**.
7. Klik op **Voltooien**.

We nodigen gebruikers later uit. Vervolgens is het belangrijk om de instellingen voor delen op siteniveau voor deze site te controleren.

## <a name="sharepoint-site-level-sharing-settings"></a>Instellingen voor het delen op siteniveau in SharePoint

Controleer de instellingen voor delen op siteniveau om ervoor te zorgen dat het type toegang dat u voor deze site wilt gebruiken, wordt toegestaan. Als u bijvoorbeeld de instellingen op organisatieniveau in stelt op **Iedereen,** maar u wilt dat alle gasten zich voor deze site verifiëren, moet u ervoor zorgen dat de instellingen voor delen op siteniveau zijn ingesteld op Nieuwe en bestaande **gasten.**

Houd er rekening mee dat de site niet kan worden gedeeld met niet-nautische personen **(** Iedereen instelling), maar afzonderlijke bestanden en mappen wel.

U kunt ook [gevoeligheidslabels gebruiken om instellingen voor extern delen voor SharePoint-sites te beheren.](../compliance/sensitivity-labels-teams-groups-sites.md)

![Schermafbeelding van de instellingen voor extern delen van SharePoint](../media/sharepoint-site-external-sharing-settings.png)

Instellingen voor delen op siteniveau instellen
1. Vouw **Sites** uit in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant en klik op **Delen**.
2. Selecteer de site die u wilt delen.
3. Klik op ...en klik op **Delen.**
4. Zorg ervoor dat delen is ingesteld op **Iedereen** of **Nieuwe en bestaande gasten**.
5. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="invite-users"></a>Gebruikers uitnodigen

Instellingen voor het delen van gasten zijn nu geconfigureerd, zodat u kunt beginnen met het toevoegen van interne gebruikers en gasten aan uw site. Sitetoegang wordt beheerd via de bijbehorende Microsoft 365-groep, dus daar worden gebruikers toegevoegd.

Interne gebruikers uitnodigen voor een groep
1. Ga naar de site waar u gebruikers wilt toevoegen.
2. Klik **in de** rechterbovenhoek op de koppeling Leden, waarmee het aantal leden wordt aangegeven.
3. Klik **op Leden toevoegen.**
4. Typ de namen of e-mailadressen van de gebruikers die u wilt uitnodigen voor de site en klik vervolgens op **Opslaan.**

Gasten kunnen niet worden toegevoegd vanaf de site. U moet ze toevoegen met de webversie van Outlook. Als voorwaarde voor het toevoegen en uitnodigen van gasten voor een groep, klikt u daarom op de URL van de site in de **kolom URL**  om naar de sitespecifieke pagina te gaan. Klik op deze pagina op het **startpictogram voor apps** en selecteer **Outlook.** Dit is het scherm waaruit u gasten kunt uitnodigen voor een groep, waarvoor de procedure hieronder wordt beschreven.

Gasten uitnodigen voor een groep
1. Klik **onder** Groepen op de groep waarvoor u gasten wilt uitnodigen.
2. Open het groepscontactkaart, klik rechtsboven op **De** koppeling Leden (de koppeling waarmee het aantal leden wordt aangegeven).
3. klik **op Leden toevoegen.**
4. Typ de e-mailadressen van de gasten die u wilt uitnodigen en klik vervolgens op **Toevoegen.**
5. Klik op **Sluiten**.
Houd er rekening  mee dat u alleen op Sluiten moet klikken als u niet de eigenaar van de groep bent en u daardoor de gast niet aan de groep kunt toevoegen. In dergelijke gevallen wordt de aanvraag om de gast toe te voegen aan de groep ter goedkeuring overgedragen aan de groepseigenaar.

## <a name="see-also"></a>Zie ook

[Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers](best-practices-anonymous-sharing.md)

[Accidentele blootstelling aan bestanden beperken tijdens het delen met gasten](share-limit-accidental-exposure.md)

[Een beveiligde omgeving voor het delen met gasten maken](create-secure-guest-sharing-environment.md)

[Een B2B-extranet maken met beheerde gasten](b2b-extranet.md)

[Integratie van SharePoint en OneDrive met Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview)