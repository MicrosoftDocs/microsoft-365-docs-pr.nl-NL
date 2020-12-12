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
description: In dit artikel leert u hoe u kunt samenwerken met gasten aan een document in SharePoint en OneDrive.
ms.openlocfilehash: 1b2fe003902b69e4c0c58852af67862ce6f2eb34
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663509"
---
# <a name="collaborate-with-guests-on-a-document"></a>Samenwerken met gasten aan een document

Als u met personen buiten uw organisatie moet samenwerken aan documenten in SharePoint of OneDrive, kunt u een koppeling naar het document verzenden. In dit artikel worden de stappen beschreven die u moet uitvoeren om delen van SharePoint en OneDrive in te stellen voor de behoeften van uw organisatie in Microsoft 365.

## <a name="video-demonstration"></a>Videodemonstratie

In deze video ziet u de configuratiestappen die in dit document worden beschreven.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Instellingen voor externe samenwerking van Azure

Delen in Microsoft 365 wordt bepaald door de [instellingen voor B2B External collaboration in azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations). Als gasten delen is uitgeschakeld of niet beschikbaar is in azure AD, worden de instellingen voordelen overschreven die u configureert in Microsoft 365.

Controleer de instellingen voor B2B externe samenwerking om ervoor te zorgen dat delen met gasten niet is geblokkeerd.

![Schermafbeelding van de instellingenpagina voor organisatierelaties in Microsoft Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Externe samenwerkings instellingen instellen

1. Meld u aan bij Azure Active Directory [https://aad.portal.azure.com](https://aad.portal.azure.com) .
2. Klik in het linker navigatiedeelvenster op **Azure Active Directory**.
3. Klik op **externe identiteiten**.
4. Klik in het scherm aan de **slag** in het linker navigatiedeelvenster op **instellingen voor externe samenwerking**.
5. Zorg ervoor dat **beheerders en gebruikers in de rol gast uitnodiging kunnen uitnodigen** en dat **leden kunnen uitnodigen** zijn ingesteld op **Ja**.
6. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

Let op de instellingen in de sectie **samenwerkings beperkingen** . Zorg ervoor dat de domeinen van de gasten waarmee u wilt samenwerken, niet zijn geblokkeerd.

Als u met gasten in meerdere organisaties werkt, is het raadzaam om de toegang van Directory-gegevens te beperken. Hiermee kunt u voorkomen dat ze zien welke iemand anders een gast is in de adreslijst. Als u dit wilt doen, selecteert u onder **toegangsbeperkingen** voor gastgebruikers de optie **gastgebruikers beperkte toegang tot eigenschappen en lidmaatschap van adreslijst objecten** of **toegang voor gastgebruikers is beperkt tot eigenschappen en lidmaatschap van eigen directoryobjecten**.

## <a name="sharepoint-organization-level-sharing-settings"></a>Instellingen voordelen op SharePoint-organisatieniveau

Als u wilt dat personen van buiten uw organisatie toegang hebben tot een document in SharePoint of OneDrive, moeten de instellingen voordelen van SharePoint en OneDrive delen toestaan voordelen met personen buiten uw organisatie.

De instellingen op organisatieniveau voor SharePoint bepalen de instellingen die beschikbaar zijn voor afzonderlijke SharePoint-sites. Site-instellingen kunnen niet hoger zijn dan de instellingen op organisatieniveau. Met de instelling op organisatieniveau voor OneDrive bepaalt u het niveau van delen dat beschikbaar is in de OneDrive-bibliotheken van de gebruikers.

Voor SharePoint en OneDrive, als u niet-geverifieerde bestanden en mappen wilt delen, kiest u **iedereen**. Als u er zeker van wilt zijn dat mensen van buiten uw organisatie verificatie hebben, kiest u **nieuwe en bestaande gasten**. *Iedereen* is de eenvoudigste manier om te delen: personen buiten uw organisatie kunnen de koppeling openen zonder verificatie en kunnen ze ook aan anderen doorgeven.

Voor SharePoint kiest u de meest strikte instelling die moet worden gebruikt door alle sites in uw organisatie.

![Schermafbeelding van de instellingen voor delen op organisatieniveau van SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


Instellingen voordelen van SharePoint op organisatieniveau instellen

1. Klik in het Microsoft 365-Beheercentrum, in het linker navigatiedeelvenster, onder **beheer centra** op **SharePoint**.
2. Klik in het SharePoint-Beheercentrum, in het linker navigatiedeelvenster, onder **beleid**, op **delen**.
3. Zorg ervoor dat extern delen voor SharePoint of OneDrive is ingesteld op **iedereen** of **nieuwe en bestaande gasten**. (Houd er rekening mee dat de instelling OneDrive niet hoger is dan de instelling van SharePoint).
4. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="sharepoint-organization-level-default-link-settings"></a>Standaard koppelingsinstellingen op SharePoint-organisatieniveau

De standaardinstellingen voor het koppelen van bestanden en mappen bepalen de koppelingsoptie die standaard wordt getoond aan gebruikers wanneer ze een bestand of map delen. Gebruikers kunnen het koppelingstype wijzigen in een van de andere opties voordat u het deelt.

Houd er rekening mee dat deze instelling van invloed is op SharePoint-sites in uw organisatie en in OneDrive.

Kies een koppeling uit een van de volgende typen die standaard wordt geselecteerd wanneer gebruikers bestanden en mappen delen:

- **Iedereen met de koppeling** : Kies deze optie als u verwacht dat u een groot aantal niet-geverifieerde bestanden en mappen wilt delen. Als u iedereen wilt toestaan die wel of niet is gemachtigd voor het delen van *onbevoegd* delen, kunt u het beste een van de andere opties als standaard instellen. Dit koppelingstype is alleen beschikbaar als **iedereen** het delen heeft toegestaan.
- **Alleen personen in uw organisatie** : Kies deze optie als u verwacht dat u de meeste bestanden en mappen wilt delen met personen binnen uw organisatie.
- **Specifieke personen** : Houd deze optie ingedrukt als u verwacht dat u een groot aantal bestanden en mappen deelt met gasten. Dit type koppeling werkt met gasten en vereist ze voor verificatie.
 
![Schermafbeelding van de instellingen voor delen van bestanden en mappen op organisatieniveau van SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


De instellingen voor de standaardkoppeling van SharePoint en OneDrive instellen op organisatieniveau

1. Ga naar de pagina delen in het SharePoint-Beheercentrum.
2. Selecteer onder **koppelingen voor bestanden en mappen** de standaardkoppeling voordelen die u wilt gebruiken.
3. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

Als u de machtiging voor de koppeling voordelen wilt instellen, klikt u onder **Kies de machtiging die standaard wordt geselecteerd voor koppelingen voordelen.**

1. Selecteer **weergeven** als u niet wilt dat niet-geverifieerde gebruikers wijzigingen aanbrengen in de bestanden en mappen.
2. Selecteer **bewerken** als u wilt dat niet-geverifieerde gebruikers wijzigingen kunnen aanbrengen in de bestanden en mappen.

Houd er rekening mee dat de twee bemissieings opties niet alleen voor gasten en externe gebruikers maar ook voor interne gebruikers kunnen worden toegepast. De optie voor de machtiging die u kiest, wordt bepaald door de eigen goeddunken.

Machtigingen instellen voor koppelingen waarmee u met iedereen kunt delen

1. In het deelvenster **deze koppelingen kunnen deze machtigingen geven:** subvenster 
    1. In de vervolgkeuzelijst **bestanden** , 
        - Selecteer **weergeven en bewerken** als u niet-geverifieerde gebruikers wilt toestaan om wijzigingen aan te brengen in de bestanden.
        - Selecteer **weergeven** als u niet wilt dat niet-geverifieerde gebruikers wijzigingen in de bestanden aanbrengen.
    2. In de vervolgkeuzelijst **mappen** ,
        - Selecteer **weergeven, bewerken en uploaden** als u niet-geverifieerde gebruikers wilt toestaan om wijzigingen aan te brengen in de mappen.
        - Selecteer **weergeven** als u niet wilt dat niet-geverifieerde gebruikers wijzigingen in de mappen aanbrengen.

## <a name="sharepoint-site-level-sharing-settings"></a>Instellingen voordelen op SharePoint-siteniveau

Als u bestanden en mappen deelt die zich op een SharePoint-site bevinden, moet u ook de instellingen voordelen op siteniveau voor die site controleren.

![Schermafbeelding van de instellingen voor extern delen van SharePoint](../media/sharepoint-site-external-sharing-settings.png)

Instellingen voordelen op siteniveau instellen

1. Vouw in het SharePoint-Beheercentrum in het linker navigatievenster **sites** uit en klik op **actieve sites**.
2. Selecteer de site waarop u bestanden en mappen wilt delen met gasten.
3. Schuif naar rechts om de rij (waarin de geselecteerde site wordt weergegeven) en klik op een willekeurige plaats in de kolom **extern delen** .
4. Op de pagina die verschijnt, klikt u op het tabblad **beleidsregels** .
5. Klik onder het deelvenster **extern delen** op **bewerken**.
6. Zorg ervoor dat delen is ingesteld op **iedereen** of **nieuwe en bestaande gasten**.
7. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="invite-users"></a>Gebruikers uitnodigen

Instellingen voor het delen van gasten zijn nu geconfigureerd; gebruikers kunnen nu bestanden en mappen delen met personen buiten uw organisatie. Zie [bestanden en mappen in OneDrive delen](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) en [SharePoint-bestanden of-mappen delen](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) voor meer informatie.

## <a name="see-also"></a>Zie ook

[Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers](best-practices-anonymous-sharing.md)

[Accidentele blootstelling aan bestanden beperken tijdens het delen met gasten](share-limit-accidental-exposure.md)

[Integratie van SharePoint en OneDrive met Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
