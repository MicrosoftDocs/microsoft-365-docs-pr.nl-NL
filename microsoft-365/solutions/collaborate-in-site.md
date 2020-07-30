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
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Meer informatie over de Microsoft 365-configuratiestappen die nodig zijn om een SharePoint-site in te stellen voor samenwerking met gasten.
ms.openlocfilehash: 320fb21f19c9616e78f56e519cb804e3e03b2b45
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527904"
---
# <a name="collaborate-with-guests-in-a-site"></a>Samenwerken met gasten op een site

Als u met gasten moet samenwerken in documenten, gegevens en lijsten, u een SharePoint-site gebruiken. Moderne SharePoint-sites zijn verbonden met Microsoft 365-groepen en kunnen het sitelidmaatschap beheren en aanvullende samenwerkingstools bieden, zoals een gedeeld postvak en agenda.

In dit artikel doorlopen we de Microsoft 365-configuratiestappen die nodig zijn om een SharePoint-site in te stellen voor samenwerking met gasten.

## <a name="video-demonstration"></a>Videodemonstratie

In deze video worden de configuratiestappen weergegeven die in dit document worden beschreven.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a>Azure-instellingen voor organisatierelaties

Delen in Microsoft 365 wordt op het hoogste niveau bepaald door de instellingen voor organisatierelaties in Azure Active Directory. Als het delen van gasten is uitgeschakeld of beperkt in Azure AD, worden alle instellingen voor delen die u in Microsoft 365 configureert, overschrijven.

Controleer de instellingen voor organisatorische relaties om ervoor te zorgen dat delen met gasten niet wordt geblokkeerd.

![Schermafbeelding van de instellingenpagina voor organisatierelaties in Microsoft Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Instellingen voor organisatierelaties instellen

1. Log in bij Microsoft Azure op [https://portal.azure.com](https://portal.azure.com) .
2. Klik in de linkernavigatie op **Azure Active Directory**.
3. Klik **in het** deelvenster Overzicht op **Organisatierelaties**.
4. Klik in het deelvenster **Organisatierelaties** op **Instellingen**.
5. Zorg ervoor dat **beheerders en gebruikers in de rol van gastuitnodiger kunnen worden uitgenodigd** en dat leden kunnen **uitnodigen,** zijn beide ingesteld op **Ja.**
6. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

Let op de instellingen in de sectie **Samenwerkingsbeperkingen.** Zorg ervoor dat de domeinen van de gasten waarmee u wilt samenwerken, niet worden geblokkeerd.

## <a name="microsoft-365-groups-guest-settings"></a>Gasteninstellingen voor Microsoft 365-groepen

Moderne SharePoint-sites gebruiken Microsoft 365-groepen om de toegang tot de site te beheren. De gastinstellingen voor Microsoft 365-groepen moeten zijn ingeschakeld om toegang tot gasten op SharePoint-sites te laten werken.

![Schermopname van gastinstellingen van Microsoft 365 Groepen in het Microsoft 365-beheercentrum](../media/office-365-groups-guest-settings.png)

Gastinstellingen voor Microsoft 365-groepen instellen

1. Vouw in het Microsoft 365-beheercentrum in de linkernavigatie **Instellingen**uit.
2. Klik **op Services & invoegtoepassingen**.
3. Klik in de lijst op **Microsoft 365-groepen**.
4. Controleer de selectievakjes **Groepsleden van De groep Laten buiten uw organisatie toegang krijgen tot groepsinhoud** en **Groepeigenaren personen buiten uw organisatie aan groepen toevoegen.**
5. Als u wijzigingen hebt aangebracht, klikt u op **Wijzigingen opslaan**.


## <a name="sharepoint-organization-level-sharing-settings"></a>Instellingen voor delen op niveau van SharePoint-organisatie

Om gasten toegang te geven tot SharePoint-sites, moeten de instellingen voor delen op SharePoint-organisatieniveau het delen met gasten mogelijk maken.

De instellingen op organisatieniveau bepalen welke instellingen beschikbaar zijn voor afzonderlijke sites. Site-instellingen kunnen niet toleranter zijn dan de instellingen op organisatieniveau.

Als u het delen van niet-geverifieerde bestanden en mappen wilt toestaan, kiest **u Iedereen**. Als u ervoor wilt zorgen dat alle mensen buiten uw organisatie zich moeten authenticeren, kiest u **Nieuwe en bestaande gasten.** Kies de meest tolerante instelling die nodig is voor elke site in uw organisatie.

![Schermafbeelding van de instellingen voor delen op organisatieniveau van SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


Instellingen voor delen op niveau van SharePoint instellen

1. Klik in het Microsoft 365-beheercentrum in de linkernavigatie onder **Beheercentra**op **SharePoint**.
2. Klik in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant op **delen**.
3. Zorg ervoor dat extern delen voor SharePoint is ingesteld op **Iedereen** of **Nieuw en bestaande gasten**.
4. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="create-a-site"></a>Een site maken

De volgende stap is het maken van de site die u van plan bent te gebruiken voor samenwerking met gasten.

Een site maken
1. Klik in het SharePoint-beheercentrum onder **Sites** op **Actieve sites**.
2. Klik op **Maken**.
3. Klik op **Teamsite**.
4. Typ een sitenaam en voer een naam in voor de eigenaar van de groep (site-eigenaar).
5. Kies onder **Geavanceerde instellingen**of u wilt dat dit een openbare of privésite is.
6. Klik op **Volgende**.
7. Klik op **Voltooien**.

We nodigen gebruikers later uit. Vervolgens is het belangrijk om de instellingen voor het delen van siteniveau voor deze site te controleren.

## <a name="sharepoint-site-level-sharing-settings"></a>Instellingen voor delen op SharePoint-siteniveau

Controleer de instellingen voor delen op siteniveau om er zeker van te zijn dat ze het gewenste type toegang voor deze site toestaan. Als u bijvoorbeeld de instellingen op organisatieniveau instelt op **Iedereen,** maar u wilt dat alle gasten zich voor deze site verifiëren, controleert u of de instellingen voor delen op siteniveau zijn ingesteld op **Nieuwe en bestaande gasten.**

Houd er rekening mee dat de site niet kan worden gedeeld met niet-geverifieerde personen **(Iedereen** instelling), maar individuele bestanden en mappen kunnen.

![Schermafbeelding van de instellingen voor extern delen van SharePoint](../media/sharepoint-site-external-sharing-settings.png)

Instellingen voor delen op siteniveau instellen
1. Vouw **Sites** uit in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant en klik op **Delen**.
2. Selecteer de site die u zojuist hebt gemaakt.
3. Klik op het lint op **Delen**.
4. Zorg ervoor dat delen is ingesteld op **iedereen** of **nieuwe en bestaande gasten**.
5. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="invite-users"></a>Gebruikers uitnodigen

Instellingen voor het delen van gasten zijn nu geconfigureerd, zodat u interne gebruikers en gasten aan uw site toevoegen. Toegang tot de site wordt beheerd via de bijbehorende Microsoft 365-groep, dus we voegen daar gebruikers toe.

Interne gebruikers uitnodigen voor een groep
1. Navigeer naar de site waar u gebruikers wilt toevoegen.
2. Klik rechtsboven op **Leden.**
3. Klik **op Leden toevoegen**.
4. Typ de namen of e-mailadressen van de gebruikers die u wilt uitnodigen voor de site en klik op **Opslaan**.

Gastgebruikers kunnen niet worden toegevoegd vanaf de site. U moet ze toevoegen met de webversie van Outlook.

Gasten uitnodigen voor een groep
1. Klik in de webversie van Outlook onder **Groepen**op de groep waar u leden wilt toevoegen.
2. Open het groepscontactkaart en klik vervolgens onder **Meer opties** (...)op **Leden toevoegen**.
3. Typ de e-mailadressen van de gasten die u wilt uitnodigen en klik op **Toevoegen**.
4. Klik op **Sluiten**.

## <a name="see-also"></a>Zie ook

[Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers](best-practices-anonymous-sharing.md)

[Accidentele blootstelling aan bestanden beperken tijdens het delen met gasten](share-limit-accidental-exposure.md)

[Een beveiligde omgeving voor het delen met gasten maken](create-secure-guest-sharing-environment.md)

[Een B2B-extranet maken met beheerde gasten](b2b-extranet.md)

