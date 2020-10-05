---
title: Samenwerken met gasten aan een document
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
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: In dit artikel leert u hoe u kunt samenwerken met gasten aan een document in SharePoint en OneDrive.
ms.openlocfilehash: 1a7591915efa82f1995ce2789e181dc350cd3784
ms.sourcegitcommit: 8589323c1b4ab43aab30597ee66303b0a0eb71ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357780"
---
# <a name="collaborate-with-guests-on-a-document"></a>Samenwerken met gasten aan een document

Als u met personen buiten uw organisatie moet samenwerken aan documenten in SharePoint of OneDrive, kunt u een koppeling voordelen naar het document verzenden. In dit artikel worden 365 de stappen beschreven die u moet uitvoeren om koppelingen voordelen voor SharePoint en OneDrive in te stellen voor de behoeften van uw organisatie.

## <a name="video-demonstration"></a>Videodemonstratie

In deze video ziet u de configuratiestappen die in dit document worden beschreven.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a>Instellingen van Azure organisatie relaties

Delen in Microsoft 365 wordt bepaald met het hoogste niveau van de [instellingen voor organisatie relaties in azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations). Als gasten delen is uitgeschakeld of niet beschikbaar is in azure AD, worden de instellingen voordelen die u configureert in Microsoft 365 genegeerd.

Controleer de instellingen van de organisatie om te controleren of delen met gasten niet is geblokkeerd.

![Schermafbeelding van de instellingenpagina voor organisatierelaties in Microsoft Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Instellingen voor organisatie relaties instellen

1. Meld u aan bij Microsoft Azure at [https://portal.azure.com](https://portal.azure.com) .
2. Klik in het linkernavigatievenster op **Azure Active Directory**.
3. Klik in het deelvenster **overzicht** op **organisatie relaties**.
4. Klik in het deelvenster **relaties organisatie** op **instellingen**.
5. Zorg ervoor dat **beheerders en gebruikers in de rol gast uitnodiging kunnen uitnodigen** en dat **leden kunnen uitnodigen** zijn ingesteld op **Ja**.
6. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

Let op de instellingen in de sectie **samenwerkings beperkingen** . Zorg ervoor dat de domeinen van de gasten waarmee u wilt samenwerken, niet zijn geblokkeerd.

Als u met gasten in meerdere organisaties werkt, is het raadzaam om de toegang van Directory-gegevens te beperken. Hiermee kunt u voorkomen dat ze zien welke iemand anders een gast is in de adreslijst. Als u dit wilt doen, selecteert u onder **toegangsbeperkingen**voor gastgebruikers de optie **gastgebruikers beperkte toegang tot eigenschappen en lidmaatschap van adreslijst objecten** of **toegang voor gastgebruikers is beperkt tot eigenschappen en lidmaatschap van eigen directoryobjecten**.

## <a name="sharepoint-organization-level-sharing-settings"></a>Instellingen voordelen van SharePoint-organisatieniveau

Als u wilt dat personen van buiten uw organisatie toegang hebben tot een document in SharePoint of OneDrive, moeten de instellingen voordelen van SharePoint en OneDrive delen toestaan voordelen met personen buiten uw organisatie.

De instellingen op organisatieniveau voor SharePoint bepalen welke instellingen beschikbaar zijn voor afzonderlijke SharePoint-sites. Site-instellingen kunnen niet hoger zijn dan de instellingen op organisatieniveau. Met de instelling op organisatieniveau voor OneDrive wordt bepaald welk niveau van delen beschikbaar is in de OneDrive-bibliotheken van de gebruikers.

Voor SharePoint en OneDrive, als u niet-geverifieerde bestanden en mappen wilt delen, kiest u **iedereen**. Als u er zeker van wilt zijn dat mensen van buiten uw organisatie verificatie hebben, kiest u **nieuwe en bestaande gasten**. *Iedereen* is de eenvoudigste manier om te delen: personen buiten uw organisatie kunnen de koppeling openen zonder verificatie en kunnen deze ook aan anderen doorgeven.

Voor SharePoint kiest u de meest strikte instelling die moet worden gebruikt door alle sites in uw organisatie.

![Schermafbeelding van de instellingen voor delen op organisatieniveau in SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


Instellingen voordelen van SharePoint-organisatieniveau instellen

1. Klik in het Microsoft 365-Beheercentrum, in het linkernavigatievenster, onder **beheer centra**op **SharePoint**.
2. Klik in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant op **delen**.
3. Zorg ervoor dat extern delen voor SharePoint of OneDrive is ingesteld op **iedereen** of **nieuwe en bestaande gasten**. (Houd er rekening mee dat de instelling OneDrive niet hoger is dan de instelling van SharePoint).
4. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="sharepoint-organization-level-default-link-settings"></a>Standaard koppelingsinstellingen SharePoint-organisatieniveau

De standaardinstellingen voor het koppelen van bestanden en mappen bepalen welke koppelingsoptie standaard voor de gebruiker wordt weergegeven wanneer ze een bestand of map delen. Gebruikers kunnen het koppelingstype wijzigen in een van de andere opties voordat u het deelt.

Houd er rekening mee dat deze instelling van invloed is op SharePoint-sites in uw organisatie en in OneDrive.

Kies het type koppeling dat standaard wordt geselecteerd wanneer gebruikers bestanden en mappen delen:

- **Iedereen met de koppeling** : Kies deze optie als u verwacht dat u een groot aantal niet-geverifieerde bestanden en mappen wilt delen. Als u iedereen wilt toestaan die wel of niet is gemachtigd voor het delen van *onbevoegd* delen, kunt u het beste een van de andere opties als standaard instellen. Dit koppelingstype is alleen beschikbaar als **iedereen** het delen heeft toegestaan.
- **Alleen personen in uw organisatie** : Kies deze optie als u verwacht dat u de meeste bestanden en mappen wilt delen met personen binnen uw organisatie.
- **Specifieke personen** : Houd deze optie ingedrukt als u verwacht dat u een groot aantal bestanden en mappen deelt met gasten. Dit type koppeling werkt met gasten en vereist ze voor verificatie.
 
![Schermafbeelding van de instellingen voor delen van bestanden en mappen op organisatieniveau van SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


De standaardinstellingen voor de koppeling naar het SharePoint-en OneDrive-organisatieniveau instellen

1. Ga naar de pagina delen in het SharePoint-Beheercentrum.
2. Selecteer onder **koppelingen voor bestanden en mappen**de standaardkoppeling voordelen die u wilt gebruiken.
3. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="sharepoint-site-level-sharing-settings"></a>Instellingen voordelen op het SharePoint-siteniveau

Als u bestanden en mappen deelt die zich op een SharePoint-site bevinden, moet u ook de instellingen voordelen op siteniveau voor die site controleren.

![Schermafbeelding van de instellingen voor extern delen van SharePoint](../media/sharepoint-site-external-sharing-settings.png)

Instellingen voordelen op siteniveau instellen
1. Vouw **Sites** uit in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant en klik op **Delen**.
2. Selecteer de site die u zojuist hebt gemaakt.
3. Klik op het lint op **Delen**.
4. Zorg ervoor dat delen is ingesteld op **iedereen** of **nieuwe en bestaande gasten**.
5. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="invite-users"></a>Gebruikers uitnodigen

Instellingen voor het delen van inhoud zijn nu geconfigureerd, zodat gebruikers nu bestanden en mappen kunnen delen met personen buiten uw organisatie. Zie [bestanden en mappen in OneDrive delen](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) en [SharePoint-bestanden of-mappen delen](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) voor meer informatie.

## <a name="see-also"></a>Zie ook

[Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers](best-practices-anonymous-sharing.md)

[Accidentele blootstelling aan bestanden beperken tijdens het delen met gasten](share-limit-accidental-exposure.md)

[Integratie van SharePoint en OneDrive met Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)