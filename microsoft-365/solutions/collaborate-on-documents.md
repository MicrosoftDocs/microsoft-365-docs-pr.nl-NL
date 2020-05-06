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
ms.custom:
- M365solutions
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: In dit artikel leert u hoe u met gasten samenwerken aan een document in SharePoint en OneDrive.
ms.openlocfilehash: 6fdf7d3ff90fb799b00da2c1ec84088b270ce009
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035981"
---
# <a name="collaborate-with-guests-on-a-document"></a>Samenwerken met gasten aan een document

Als u met mensen buiten uw organisatie wilt samenwerken aan documenten in SharePoint of OneDrive, u hen een koppeling voor delen naar het document sturen. In dit artikel doorlopen we de Microsoft 365-configuratiestappen die nodig zijn om koppelingen voor delen voor SharePoint en OneDrive in te stellen voor de behoeften van uw organisatie.

## <a name="video-demonstration"></a>Videodemonstratie

In deze video worden de configuratiestappen weergegeven die in dit document worden beschreven.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

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

## <a name="sharepoint-organization-level-sharing-settings"></a>Instellingen voor delen van SharePoint-organisatieniveau

Als mensen buiten uw organisatie toegang hebben tot een document in SharePoint of OneDrive, moeten de instellingen voor delen op sharepoint- en OneDrive-organisatieniveau het delen mogelijk maken met mensen buiten uw organisatie.

De instellingen op organisatieniveau voor SharePoint bepalen welke instellingen beschikbaar zijn voor afzonderlijke SharePoint-sites. Site-instellingen kunnen niet toleranter zijn dan de instellingen op organisatieniveau. De instelling op organisatieniveau voor OneDrive bepaalt welk deelniveau beschikbaar is in de OneDrive-bibliotheken van gebruikers.

Kies Voor SharePoint en OneDrive de optie **Iedereen**. Als u ervoor wilt zorgen dat mensen buiten uw organisatie zich moeten verifiëren, kiest u **Nieuwe en bestaande gasten.** *Iedereen* die links de gemakkelijkste manier delen: mensen buiten uw organisatie kunnen de koppeling openen zonder verificatie en zijn vrij om deze door te geven aan anderen.

Kies voor SharePoint de meest tolerante instelling die nodig is voor elke site in uw organisatie.

![Schermafbeelding van de instellingen voor delen op organisatieniveau van SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


Instellingen voor delen van SharePoint-organisatieniveau instellen

1. Klik in het Microsoft 365-beheercentrum in de linkernavigatie onder **Beheercentra**op **SharePoint**.
2. Klik in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant op **Delen**.
3. Controleer of extern delen voor SharePoint of OneDrive is ingesteld op **iedereen** of **nieuwe en bestaande gasten.** (Houd er rekening mee dat de OneDrive-instelling niet toleranter kan zijn dan de SharePoint-instelling.)
4. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="sharepoint-organization-level-default-link-settings"></a>Standaardkoppelingsinstellingen op SharePoint-organisatieniveau

De standaardinstellingen voor bestands- en mapkoppeling bepalen welke koppelingsoptie standaard aan de gebruiker wordt weergegeven wanneer ze een bestand of map delen. Gebruikers kunnen het koppelingstype wijzigen in een van de andere opties voordat ze desgewenst delen.

Houd er rekening mee dat deze instelling van invloed is op SharePoint-sites in uw organisatie en OneDrive.

Kies het type koppeling dat standaard is geselecteerd wanneer gebruikers bestanden en mappen delen:

- **Iedereen met de koppeling** - Kies deze optie als u verwacht veel niet-geverifieerde bestanden en mappen te delen. Als u *koppelingen voor iedereen* wilt toestaan, maar zich zorgen maakt over het per ongeluk niet-verifiëren delen, u een van de andere opties als standaard beschouwen. Dit koppelingstype is alleen beschikbaar als u **Delen van iedereen** hebt ingeschakeld.
- **Alleen mensen in uw organisatie** - Kies deze optie als u verwacht dat het delen van bestanden en mappen bij mensen binnen uw organisatie is.
- **Specifieke personen** - Overweeg deze optie als u verwacht veel bestanden en mappen te delen met gasten. Dit type koppeling werkt met gasten en vereist dat ze zich verifiëren.
 
![Schermafbeelding van de instellingen voor delen van bestanden en mappen op organisatieniveau van SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


De standaardkoppelingsinstellingen voor SharePoint- en OneDrive-organisatieniveau instellen

1. Navigeer naar de pagina Delen in het SharePoint-beheercentrum.
2. Selecteer **onder Koppelingen voor bestand en map**de standaardkoppeling voor delen die u wilt gebruiken.
3. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="sharepoint-site-level-sharing-settings"></a>Instellingen voor delen op SharePoint-siteniveau

Als u bestanden en fodlers deelt die zich op een SharePoint-site bevinden, moet u ook de instellingen voor delen op siteniveau voor die site controleren.

![Schermafbeelding van de instellingen voor extern delen van SharePoint](../media/sharepoint-site-external-sharing-settings.png)

Instellingen voor delen op siteniveau instellen
1. Vouw **Sites** uit in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant en klik op **Delen**.
2. Selecteer de site die u zojuist hebt gemaakt.
3. Klik op het lint op **Delen**.
4. Zorg ervoor dat delen is ingesteld op **iedereen** of **nieuwe en bestaande gasten.**
5. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="invite-users"></a>Gebruikers uitnodigen

Instellingen voor het delen van gasten zijn nu geconfigureerd, zodat gebruikers nu bestanden en mappen kunnen delen met mensen buiten uw organisatie. Zie [OneDrive-bestanden en -mappen delen](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) en [SharePoint-bestanden of -mappen](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) delen voor meer informatie.

## <a name="see-also"></a>Zie ook

[Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers](best-practices-anonymous-sharing.md)

[Accidentele blootstelling aan bestanden beperken tijdens het delen met gasten](share-limit-accidental-exposure.md)