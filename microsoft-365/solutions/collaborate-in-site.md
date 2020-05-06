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
ms.custom:
- M365solutions
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Meer informatie over de Microsoft 365-configuratiestappen die nodig zijn om een SharePoint-site in te stellen voor samenwerking met gasten.
ms.openlocfilehash: f79846de5d4fd8661205e549db3457a7696e9770
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035993"
---
# <a name="collaborate-with-guests-in-a-site"></a>Samenwerken met gasten op een site

Als u met gasten wilt samenwerken in alle documenten, gegevens en lijsten, u een SharePoint-site gebruiken. Moderne SharePoint-sites zijn verbonden met Microsoft 365-groepen en kunnen het sitelidmaatschap beheren en aanvullende samenwerkingstools bieden, zoals een gedeeld postvak en agenda.

In dit artikel doorlopen we de Microsoft 365-configuratiestappen die nodig zijn om een SharePoint-site in te stellen voor samenwerking met gasten.

## <a name="video-demonstration"></a>Videodemonstratie

In deze video worden de configuratiestappen weergegeven die in dit document worden beschreven.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a>Instellingen voor Azure-organisatierelaties

Delen in Microsoft 365 wordt op het hoogste niveau bepaald door de instellingen voor organisatierelaties in Azure Active Directory. Als het delen van gasten is uitgeschakeld of beperkt in Azure AD, worden alle instellingen voor delen die u configureert in Microsoft 365 overschreven.

Controleer de instellingen voor organisatorische relaties om ervoor te zorgen dat delen met gasten niet wordt geblokkeerd.

![Schermafbeelding van de instellingenpagina voor organisatierelaties in Microsoft Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Instellingen voor organisatierelaties instellen

1. Meld u aan [https://portal.azure.com](https://portal.azure.com)bij Microsoft Azure op .
2. Klik in de linkernavigatie op **Azure Active Directory**.
3. Klik in het deelvenster **Overzicht** op **Organisatierelaties**.
4. Klik in het deelvenster **Organisatierelaties** op **Instellingen**.
5. Zorg ervoor dat **beheerders en gebruikers in de gastuitnodigingsrol kunnen uitnodigen** en dat leden kunnen **uitnodigen,** beide zijn ingesteld op **Ja**.
6. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

Let op de instellingen in de sectie **Samenwerkingsbeperkingen.** Zorg ervoor dat de domeinen van de gasten waarmee u wilt samenwerken, niet worden geblokkeerd.

## <a name="microsoft-365-groups-guest-settings"></a>Gastinstellingen voor Microsoft 365-groepen

Moderne SharePoint-sites gebruiken Microsoft 365-groepen om de toegang tot de site te beheren. De gastinstellingen van Microsoft 365-groepen moeten zijn ingeschakeld om gasttoegang in SharePoint-sites te laten werken.

![Schermopname van gastinstellingen van Microsoft 365 Groepen in het Microsoft 365-beheercentrum](../media/office-365-groups-guest-settings.png)

Gastinstellingen voor Microsoft 365-groepen instellen

1. Vouw in het Microsoft 365-beheercentrum in de linkernavigatie **instellingen**uit .
2. Klik **op Services &-invoegtoepassing .**
3. Klik in de lijst op **Microsoft 365-groepen**.
4. Zorg ervoor dat de **groepsleden buiten uw organisatie toegang krijgen tot groepsinhoud** en **groepseigenaren mensen buiten uw organisatie toevoegen aan de** selectievakjes groepen, beide zijn ingeschakeld.
5. Als u wijzigingen hebt aangebracht, klikt u op **Wijzigingen opslaan**.


## <a name="sharepoint-organization-level-sharing-settings"></a>Instellingen voor delen van SharePoint-organisatieniveau

Om ervoor te zorgen dat gasten toegang hebben tot SharePoint-sites, moeten de instellingen voor delen op SharePoint-organisatieniveau het delen met gasten mogelijk maken.

De instellingen op organisatieniveau bepalen welke instellingen beschikbaar zijn voor afzonderlijke sites. Site-instellingen kunnen niet toleranter zijn dan de instellingen op organisatieniveau.

Als u het delen van niet-geverifieerde bestanden en mappen wilt toestaan, kiest u **Iedereen**. Als u ervoor wilt zorgen dat alle mensen buiten uw organisatie zich moeten verifiëren, kiest u **Nieuwe en bestaande gasten.** Kies de meest tolerante instelling die nodig is voor elke site in uw organisatie.

![Schermafbeelding van de instellingen voor delen op organisatieniveau van SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


Instellingen voor delen van SharePoint-organisatieniveau instellen

1. Klik in het Microsoft 365-beheercentrum in de linkernavigatie onder **Beheercentra**op **SharePoint**.
2. Klik in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant op **Delen**.
3. Controleer of extern delen voor SharePoint is ingesteld op **iedereen** of **nieuwe en bestaande gasten.**
4. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="create-a-site"></a>Een site maken

De volgende stap is het maken van de site die u van plan bent te gebruiken om samen te werken met gasten.

Een site maken
1. Klik in het SharePoint-beheercentrum onder **Sites** op **Actieve sites**.
2. Klik op **Maken**.
3. Klik **op Teamsite**.
4. Typ een sitenaam en voer een naam in voor de eigenaar van de groep (site-eigenaar).
5. Kies **onder Geavanceerde instellingen**of u wilt dat dit een openbare of privésite is.
6. Klik op **Volgende**.
7. Klik op **Voltooien**.

We nodigen gebruikers later uit. Vervolgens is het belangrijk om de instellingen voor het delen op siteniveau voor deze site te controleren.

## <a name="sharepoint-site-level-sharing-settings"></a>Instellingen voor delen op SharePoint-siteniveau

Controleer de instellingen voor delen op siteniveau om ervoor te zorgen dat deze toegang voor deze site mogelijk maken. Als u bijvoorbeeld de instellingen op organisatieniveau instelt op **Iedereen,** maar u wilt dat alle gasten zich voor deze site verifiëren, controleert u of de instellingen voor delen op siteniveau zijn ingesteld op **nieuwe en bestaande gasten.**

Houd er rekening mee dat de site niet kan worden gedeeld met niet-geverifieerde personen **(Instellingen voor iedereen),** maar afzonderlijke bestanden en mappen wel.

![Schermafbeelding van de instellingen voor extern delen van SharePoint](../media/sharepoint-site-external-sharing-settings.png)

Instellingen voor delen op siteniveau instellen
1. Vouw **Sites** uit in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant en klik op **Delen**.
2. Selecteer de site die u zojuist hebt gemaakt.
3. Klik op het lint op **Delen**.
4. Zorg ervoor dat delen is ingesteld op **iedereen** of **nieuwe en bestaande gasten.**
5. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="invite-users"></a>Gebruikers uitnodigen

Instellingen voor het delen van gasten zijn nu geconfigureerd, zodat u beginnen met het toevoegen van interne gebruikers en gasten aan uw site. Toegang tot de site wordt beheerd via de bijbehorende Microsoft 365-groep, dus we voegen daar gebruikers toe.

Interne gebruikers uitnodigen voor een groep
1. Navigeer naar de site waar u gebruikers wilt toevoegen.
2. Klik rechtsboven op **Leden.**
3. Klik **op Leden toevoegen**.
4. Typ de namen of e-mailadressen van de gebruikers die u wilt uitnodigen voor de site en klik op **Opslaan**.

Gastgebruikers kunnen niet worden toegevoegd vanaf de site. U moet ze toevoegen met de webversie van Outlook.

Gasten uitnodigen voor een groep
1. Klik in de webversie van Outlook onder **Groepen**op de groep waar u leden wilt toevoegen.
2. Open het groepsvisitekaartje en klik onder **Meer opties** (...)op **Leden toevoegen**.
3. Typ de e-mailadressen van de gasten die u wilt uitnodigen en klik op **Toevoegen**.
4. Klik **op Sluiten**.

## <a name="see-also"></a>Zie ook

[Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers](best-practices-anonymous-sharing.md)

[Accidentele blootstelling aan bestanden beperken tijdens het delen met gasten](share-limit-accidental-exposure.md)

[Een beveiligde omgeving voor het delen met gasten maken](create-secure-guest-sharing-environment.md)

[Een B2B-extranet maken met beheerde gasten](b2b-extranet.md)

