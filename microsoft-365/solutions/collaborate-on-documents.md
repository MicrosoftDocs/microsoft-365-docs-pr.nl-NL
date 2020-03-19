---
title: Samenwerken met gasten aan een document
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: sharepoint-online
ms.collection: SPO_Content
localization_priority: Normal
f1.keywords: NOCSH
description: Meer informatie over hoe u met gasten samenwerken aan een document in SharePoint en OneDrive.
ms.openlocfilehash: 139533b2d7bf65ddd9584007a5ac03800c731d0b
ms.sourcegitcommit: 21338a9287017a66298e0ff557e80051946ebf13
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/11/2020
ms.locfileid: "42810366"
---
# <a name="collaborate-with-guests-on-a-document"></a>Samenwerken met gasten aan een document

Als u met mensen buiten uw organisatie moet samenwerken aan documenten in SharePoint of OneDrive, u ze een koppeling voor delen naar het document sturen. In dit artikel doorlopen we de configuratiestappen van Microsoft 365 die nodig zijn om koppelingen voor delen voor SharePoint en OneDrive in te stellen voor de behoeften van uw organisatie.

## <a name="video-demonstration"></a>Videodemonstratie

In deze video worden de configuratiestappen weergegeven die in dit document worden beschreven.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a>Instellingen voor Azure Organizational Relationships

Delen in Microsoft 365 wordt op het hoogste niveau geregeld door de instellingen voor organisatierelaties in Azure Active Directory. Als het delen van gasten is uitgeschakeld of beperkt in Azure AD, worden alle instellingen voor delen die u configureert in Microsoft 365, overschreven.

Controleer de instellingen voor organisatierelaties om ervoor te zorgen dat delen met gasten niet wordt geblokkeerd.

![Schermafbeelding van de pagina Instellingen voor Azure Active Directory-organisatierelaties](../media/azure-ad-organizational-relationships-settings.png)

Instellingen voor organisatierelatie instellen

1. Log in bij [https://portal.azure.com](https://portal.azure.com)Microsoft Azure bij .
2. Klik in de linkernavigatie op **Azure Active Directory**.
3. Klik in het deelvenster **Overzicht** op **Organisatierelaties**.
4. Klik in het deelvenster **Organisatierelaties** op **Instellingen**.
5. Zorg ervoor dat **beheerders en gebruikers in de rol gastgenodigden kunnen uitnodigen** en leden kunnen **uitnodigen,** zijn beide ingesteld op **Ja**.
6. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

Let op de instellingen in de sectie **Beperkingen voor samenwerking.** Zorg ervoor dat de domeinen van de gasten waarmee u wilt samenwerken niet worden geblokkeerd.

## <a name="sharepoint-organization-level-sharing-settings"></a>Instellingen voor delen op sharepoint-organisatieniveau

Om ervoor te zorgen dat mensen buiten uw organisatie toegang hebben tot een document in SharePoint of OneDrive, moeten de instellingen voor delen op organisatieniveau op organisatieniveau het delen met mensen buiten uw organisatie mogelijk maken.

De instellingen op organisatieniveau voor SharePoint bepalen welke instellingen beschikbaar zijn voor afzonderlijke SharePoint-sites. Site-instellingen kunnen niet toleranter zijn dan de instellingen op organisatieniveau. De instelling op organisatieniveau voor OneDrive bepaalt welk niveau van delen beschikbaar is in de OneDrive-bibliotheken van gebruikers.

Kies Voor SharePoint en OneDrive de optie **Iedereen**kiezen als u niet-geverifieerde bestanden en mappen wilt delen. Als u ervoor wilt zorgen dat mensen buiten uw organisatie zich moeten authenticeren, kiest u **Nieuwe en bestaande gasten.** *Iedereen* links zijn de makkelijkste manier om te delen: mensen buiten uw organisatie kunnen de link openen zonder authenticatie en zijn vrij om het door te geven aan anderen.

Kies voor SharePoint de meest tolerante instelling die nodig is voor elke site in uw organisatie.

![Schermafbeelding van instellingen voor delen op sharepoint-organisatieniveau](../media/sharepoint-organization-external-sharing-controls.png)


Instellingen voor delen op sharepoint-organisatieniveau instellen

1. Klik in het Microsoft 365-beheercentrum in de linkernavigatie onder **Beheercentra**op **SharePoint**.
2. Klik in het SharePoint-beheercentrum in de linkernavigatie op **Delen**.
3. Zorg ervoor dat extern delen voor SharePoint of OneDrive is ingesteld op **iedereen** of **nieuwe en bestaande gasten.** (Houd er rekening mee dat de Instelling OneDrive niet toleranter kan zijn dan de SharePoint-instelling.)
4. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="sharepoint-organization-level-default-link-settings"></a>Standaardkoppelingsinstellingen voor SharePoint-organisatieniveau

De instellingen voor standaardbestands- en mapkoppelingen bepalen welke koppelingsoptie standaard aan de gebruiker wordt weergegeven wanneer deze een bestand of map deelt. Gebruikers kunnen het koppelingstype wijzigen in een van de andere opties voordat ze desgewenst delen.

Houd er rekening mee dat deze instelling van invloed is op SharePoint-sites in uw organisatie en op OneDrive.

Kies het type koppeling dat standaard is geselecteerd wanneer gebruikers bestanden en mappen delen:

- **Iedereen met de koppeling** - Kies deze optie als u verwacht veel niet-geverifieerde bestanden en mappen te delen. Als u *Koppelingen* wilt toestaan, maar zich zorgen maakt over het per ongeluk niet-geverifieerde delen, beschouw dan een van de andere opties als standaard. Dit koppelingstype is alleen beschikbaar als u iedereen hebt ingeschakeld om **te** delen.
- **Alleen mensen in uw organisatie** - Kies deze optie als u verwacht dat het delen van bestanden en mappen het meest met mensen binnen uw organisatie is.
- **Specifieke mensen** - Overweeg deze optie als u verwacht veel bestanden en mappen te delen met gasten. Dit type koppeling werkt samen met gasten en vereist dat ze zich verifiëren.
 
![Schermafbeelding van instellingen voor delen op organisatieniveau](../media/sharepoint-organization-files-folders-sharing-settings.png)


Standaardkoppelingsinstellingen voor SharePoint- en OneDrive-organisatieniveau instellen

1. Navigeer naar de pagina Delen in het SharePoint-beheercentrum.
2. Selecteer onder **Bestands- en mapkoppelingen**de standaardkoppeling voor delen die u wilt gebruiken.
3. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="sharepoint-site-level-sharing-settings"></a>Instellingen voor delen op sharepoint-siteniveau

Als u bestanden en fodlers deelt die zich op een SharePoint-site bevinden, moet u ook de instellingen voor het delen op siteniveau voor die site controleren.

![Schermafbeelding van instellingen voor extern delen van de SharePoint-site](../media/sharepoint-site-external-sharing-settings.png)

Instellingen voor delen op siteniveau instellen
1. Vouw **sites** in het SharePoint-beheercentrum uit en klik op **Actieve sites**in het SharePoint-beheercentrum.
2. Selecteer de site die u zojuist hebt gemaakt.
3. Klik op het lint op **Delen**.
4. Zorg ervoor dat delen is ingesteld op **iedereen** of **nieuwe en bestaande gasten.**
5. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="invite-users"></a>Gebruikers uitnodigen

Instellingen voor het delen van gasten zijn nu geconfigureerd, zodat gebruikers nu bestanden en mappen kunnen delen met mensen buiten uw organisatie. Zie [OneDrive-bestanden en -mappen delen](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) en [SharePoint-bestanden of -mappen delen](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) voor meer informatie.

## <a name="see-also"></a>Zie ook

[Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers](best-practices-anonymous-sharing.md)

[Onbedoelde blootstelling aan bestanden beperken wanneer u deelt met gasten](share-limit-accidental-exposure.md)