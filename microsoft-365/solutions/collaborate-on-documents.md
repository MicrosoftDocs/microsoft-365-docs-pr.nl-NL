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
description: In dit artikel leert u hoe u samenwerken met gasten aan een document in SharePoint en OneDrive.
ms.openlocfilehash: cb3c527304f0d286b4a1a0147d07537b0fae4eda
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527916"
---
# <a name="collaborate-with-guests-on-a-document"></a>Samenwerken met gasten aan een document

Als u met mensen buiten uw organisatie moet samenwerken aan documenten in SharePoint of OneDrive, u ze een koppeling voor delen naar het document sturen. In dit artikel doorlopen we de microsoft 365-configuratiestappen die nodig zijn om koppelingen voor delen voor SharePoint en OneDrive in te stellen voor de behoeften van uw organisatie.

## <a name="video-demonstration"></a>Videodemonstratie

In deze video worden de configuratiestappen weergegeven die in dit document worden beschreven.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

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

## <a name="sharepoint-organization-level-sharing-settings"></a>Instellingen voor delen op niveau van SharePoint-organisatie

Als u ervoor wilt dat mensen buiten uw organisatie toegang hebben tot een document in SharePoint of OneDrive, moeten de instellingen voor delen op organisatieniveau in SharePoint en OneDrive toestaan om te delen met mensen buiten uw organisatie.

De instellingen op organisatieniveau voor SharePoint bepalen welke instellingen beschikbaar zijn voor afzonderlijke SharePoint-sites. Site-instellingen kunnen niet toleranter zijn dan de instellingen op organisatieniveau. De instelling op organisatieniveau voor OneDrive bepaalt welk niveau van delen beschikbaar is in de OneDrive-bibliotheken van gebruikers.

Als u voor SharePoint en OneDrive het delen van niet-geverifieerde bestanden en mappen wilt toestaan, kiest **u Iedereen**. Als u ervoor wilt zorgen dat mensen buiten uw organisatie zich moeten authenticeren, kiest u **Nieuwe en bestaande gasten.** *Iedereen* links zijn de makkelijkste manier om te delen: mensen buiten uw organisatie kunnen de link openen zonder authenticatie en zijn vrij om het door te geven aan anderen.

Kies voor SharePoint de meest tolerante instelling die nodig is voor elke site in uw organisatie.

![Schermafbeelding van de instellingen voor delen op organisatieniveau van SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


Instellingen voor delen op niveau van SharePoint instellen

1. Klik in het Microsoft 365-beheercentrum in de linkernavigatie onder **Beheercentra**op **SharePoint**.
2. Klik in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant op **delen**.
3. Controleer of extern delen voor SharePoint of OneDrive is ingesteld op **Iedereen** of **Nieuw en bestaande gasten**. (Houd er rekening mee dat de OneDrive-instelling niet toleranter kan zijn dan de SharePoint-instelling.)
4. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="sharepoint-organization-level-default-link-settings"></a>Standaardkoppelingsinstellingen voor SharePoint-organisatieniveau

De standaardinstellingen voor bestands- en mapkoppeling bepalen welke koppelingsoptie standaard aan de gebruiker wordt weergegeven wanneer deze een bestand of map deelt. Gebruikers kunnen het koppelingstype wijzigen in een van de andere opties voordat ze desverdeeld delen, indien gewenst.

Houd er rekening mee dat deze instelling van invloed is op SharePoint-sites in uw organisatie en op OneDrive.

Kies het type koppeling dat standaard is geselecteerd wanneer gebruikers bestanden en mappen delen:

- **Iedereen met de link** - Kies deze optie als je verwacht veel niet-geverifieerde bestanden en mappen te delen. Als u links voor iedereen wilt *toestaan,* maar zich zorgen wilt maken over het per ongeluk delen zonder toestemming, beschouw dan een van de andere opties als de standaardoptie. Dit koppelingstype is alleen beschikbaar als je Het delen van **iedereen** hebt ingeschakeld.
- **Alleen mensen in uw organisatie** - Kies deze optie als u verwacht dat het delen van bestanden en mappen met mensen binnen uw organisatie is.
- **Specifieke personen** - Overweeg deze optie als u verwacht veel bestands- en mapdelingen met gasten te doen. Dit type link werkt samen met gasten en vereist dat ze zich verifiëren.
 
![Schermafbeelding van de instellingen voor delen van bestanden en mappen op organisatieniveau van SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


De standaardkoppelingsinstellingen op SharePoint- en OneDrive-organisatieniveau instellen

1. Navigeer naar de pagina Delen in het SharePoint-beheercentrum.
2. Selecteer onder **Koppelingen bestand en mappen**de standaardkoppelingskoppeling die u wilt gebruiken.
3. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="sharepoint-site-level-sharing-settings"></a>Instellingen voor delen op SharePoint-siteniveau

Als u bestanden en fodlers deelt die zich op een SharePoint-site bevinden, moet u ook de instellingen voor delen op siteniveau voor die site controleren.

![Schermafbeelding van de instellingen voor extern delen van SharePoint](../media/sharepoint-site-external-sharing-settings.png)

Instellingen voor delen op siteniveau instellen
1. Vouw **Sites** uit in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant en klik op **Delen**.
2. Selecteer de site die u zojuist hebt gemaakt.
3. Klik op het lint op **Delen**.
4. Zorg ervoor dat delen is ingesteld op **iedereen** of **nieuwe en bestaande gasten**.
5. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="invite-users"></a>Gebruikers uitnodigen

Instellingen voor het delen van gasten zijn nu geconfigureerd, zodat gebruikers nu bestanden en mappen kunnen delen met mensen buiten uw organisatie. Zie [OneDrive-bestanden en -mappen delen](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) en [SharePoint-bestanden of -mappen delen](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) voor meer informatie.

## <a name="see-also"></a>Zie ook

[Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers](best-practices-anonymous-sharing.md)

[Accidentele blootstelling aan bestanden beperken tijdens het delen met gasten](share-limit-accidental-exposure.md)