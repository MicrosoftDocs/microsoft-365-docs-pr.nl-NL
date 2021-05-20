---
title: Samenwerken met gasten aan een document
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
recommendations: false
description: In dit artikel leert u hoe u met gasten kunt samenwerken aan een document in SharePoint en OneDrive.
ms.openlocfilehash: 338c7f32944bccb766ed923c12a9fceee4d81db8
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537833"
---
# <a name="collaborate-with-guests-on-a-document"></a>Samenwerken met gasten aan een document

Als u met personen buiten uw organisatie wilt samenwerken aan documenten in SharePoint of OneDrive, kunt u ze een koppeling voor delen naar het document sturen. In dit artikel volgen we de Microsoft 365 configuratiestappen die nodig zijn om koppelingen voor delen in te stellen voor SharePoint en OneDrive voor de behoeften van uw organisatie.

## <a name="video-demonstration"></a>Videodemonstratie

In deze video ziet u de configuratiestappen die in dit document worden beschreven.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Externe samenwerkingsinstellingen voor Azure

Delen in Microsoft 365 wordt op het hoogste niveau bepaald door de [B2B-instellingen voor externe samenwerking in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations). Als gast delen is uitgeschakeld of beperkt in Azure AD, worden met deze instelling alle instellingen voor delen die u configureert in Microsoft 365.

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

## <a name="sharepoint-organization-level-sharing-settings"></a>SharePoint instellingen voor delen op organisatieniveau

Als u wilt dat personen buiten uw organisatie toegang hebben tot een document in SharePoint of OneDrive, moeten de instellingen voor delen op SharePoint en OneDrive organisatieniveau toestaan dat ze kunnen delen met personen buiten uw organisatie.

De instellingen op organisatieniveau voor SharePoint bepalen de instellingen die beschikbaar zijn voor afzonderlijke SharePoint sites. Site-instellingen mogen niet meer toestaan dan de instellingen op organisatieniveau. De instelling op organisatieniveau voor OneDrive bepaalt het niveau van delen dat beschikbaar is in de bibliotheken OneDrive gebruikers.

Als SharePoint en OneDrive wilt toestaan dat niet-nautisch bestanden en mappen worden gedeeld, kiest u **Iedereen.** Als u ervoor wilt zorgen dat personen buiten uw organisatie zich moeten verifiëren, kiest u **Nieuwe en bestaande gasten.** *Iedereen* met koppelingen is de eenvoudigste manier om te delen: personen buiten uw organisatie kunnen de koppeling zonder verificatie openen en kunnen deze aan anderen doorgeven.

Kies SharePoint de meest permissieve instelling die nodig is voor elke site in uw organisatie.

![Schermafbeelding van de instellingen voor delen op organisatieniveau van SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


Instellingen voor delen op organisatieniveau van SharePoint instellen

1. In het Microsoft 365-beheercentrum klikt u onder **Beheercentra** op **SharePoint**.
2. Klik in SharePoint beheercentrum in het linkernavigatiedeelvenster onder Beleid **op** **Delen.**
3. Zorg ervoor dat extern delen voor SharePoint of OneDrive is ingesteld op **Iedereen** of **Nieuwe en bestaande gasten.** (Houd er rekening mee dat OneDrive instelling niet meer mag zijn dan de instelling SharePoint instelling.)
4. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="sharepoint-organization-level-default-link-settings"></a>Standaardkoppelingsinstellingen op organisatieniveau van SharePoint

De standaardkoppelingsinstellingen voor bestanden en mappen bepalen de koppelingsoptie die standaard voor gebruikers wordt weergegeven wanneer ze een bestand of map delen. Gebruikers kunnen voor het delen desgewenst het koppelingstype wijzigen in een van de andere opties.

Houd er rekening mee dat deze instelling van invloed is op SharePoint sites in uw organisatie, evenals OneDrive.

Kies een koppeling uit een van de volgende typen die vervolgens standaard wordt geselecteerd wanneer gebruikers bestanden en mappen delen:

- **Iedereen met de koppeling:** kies deze optie als u veel niet-genautenteerde bestanden en mappen wilt delen. Als u *Iedereen*-koppelingen wilt toestaan, maar u zich zorgen maakt over onbedoeld niet-geverifieerd delen, kunt u een van de andere opties als standaardoptie gebruiken. Dit koppelingstype is alleen beschikbaar als u **Iedereen** hebt ingeschakeld.
- **Alleen personen in uw organisatie**: kies deze optie als u verwacht dat de meeste bestanden en mappen worden gedeeld met personen binnen uw organisatie.
- **Specifieke personen** - overweeg deze optie als u verwacht veel bestanden en mappen te delen met gasten. Dit type koppeling werkt met gasten en vereist verificatie.
 
![Schermafbeelding van de instellingen voor delen van bestanden en mappen op organisatieniveau van SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


De standaardkoppelingsinstellingen SharePoint en OneDrive op organisatieniveau instellen

1. Navigeer naar de pagina Delen in het SharePoint-beheercentrum.
2. Selecteer onder **Koppelingen naar bestanden en mappen** de standaardkoppeling voor delen die u wilt gebruiken.
3. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

Als u de machtiging voor de koppeling voor delen wilt instellen, gaat u naar Kies de machtiging die standaard is **geselecteerd voor koppelingen voor delen.**

1. Selecteer **Beeld** als u niet wilt dat niet-nautische gebruikers wijzigingen aanbrengen in de bestanden en mappen.
2. Selecteer **Bewerken** als u niet-nautische gebruikers wilt toestaan wijzigingen aan te brengen in de bestanden en mappen.

Houd er rekening mee dat de bovenstaande twee premission-opties niet alleen kunnen worden toegepast voor gasten/externe gebruikers, maar ook voor interne gebruikers. De machtigingsoptie die u kiest, wordt bepaald door zelfre discretionaire bevoegdheid.

Machtigingen instellen voor koppelingen waarmee delen met iedereen kan worden toegestaan

1. Onder deze **koppelingen kunnen deze machtigingen worden gegeven:** subdeelvenster, 
    1. In de **vervolgkeuzelijst** Bestanden 
        - Selecteer **Weergeven en bewerken** als u wilt toestaan dat niet-genautische gebruikers wijzigingen in de bestanden aanbrengen.
        - Selecteer **Beeld** als u niet wilt dat niet-genauteerde gebruikers wijzigingen aanbrengen in de bestanden.
    2. In de **vervolgkeuzelijst** Mappen
        - Selecteer **Weergeven, bewerken en uploaden** als u niet-nautische gebruikers wilt toestaan wijzigingen aan te brengen in de mappen.
        - Selecteer **Beeld** als u niet wilt dat niet-genauteerde gebruikers wijzigingen aanbrengen in de mappen.

## <a name="sharepoint-site-level-sharing-settings"></a>Instellingen voor het delen op siteniveau in SharePoint

Als u bestanden en mappen deelt die zich in een SharePoint site, moet u ook de instellingen voor delen op siteniveau voor die site controleren.

![Schermafbeelding van de instellingen voor extern delen van SharePoint](../media/sharepoint-site-external-sharing-settings.png)

Instellingen voor delen op siteniveau instellen

1. Vouw in het SharePoint-beheercentrum **Sites** uit in het navigatievenster aan de linkerkant en klik op **Actieve sites**.
2. Selecteer de site waarop u bestanden en mappen met gasten wilt delen.
3. Schuif naar rechts over de rij (waarin de geselecteerde site aanwezig is) en klik ergens in **de kolom Extern** delen.
4. Klik op de pagina die wordt weergegeven op **het tabblad** Beleid.
5. Klik onder **het deelvenster** Extern delen op **Bewerken.**
6. Zorg ervoor dat delen is ingesteld op **Iedereen** of **Nieuwe en bestaande gasten**.
7. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="invite-users"></a>Gebruikers uitnodigen

Instellingen voor het delen van gasten zijn nu geconfigureerd. zodat gebruikers nu bestanden en mappen kunnen delen met personen buiten uw organisatie. Zie [Bestanden OneDrive en](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) mappen delen en SharePoint of [mappen](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) delen voor meer informatie.

## <a name="see-also"></a>Zie ook

[Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers](best-practices-anonymous-sharing.md)

[Accidentele blootstelling aan bestanden beperken tijdens het delen met gasten](share-limit-accidental-exposure.md)

[Integratie van SharePoint en OneDrive met Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview)