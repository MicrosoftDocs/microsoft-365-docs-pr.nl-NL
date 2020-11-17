---
title: SharePoint Syntex instellen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection: enabler-strategic
search.appverid: MET150
localization_priority: Priority
description: Inhoudsbegrip instellen in Project Cortex
ms.openlocfilehash: dfbcc8e41a28e3107b58ac6b8d471e3a2a08d036
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087569"
---
# <a name="set-up-sharepoint-syntex"></a>SharePoint Syntex instellen

Beheerders kunnen het Microsoft 365-beheercentrum gebruiken om [Microsoft SharePoint Syntex](index.md) in te stellen. 

Houd rekening met het volgende voordat u begint:

- Which SharePoint sites will you enable form processing? All of them, some, or select sites?
- Wat is de naam van uw standaard inhoudscentrum?

U kunt de instellingen wijzigen na de eerste installatie in het Microsoft 365-beheercentrum.

Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment. For example, you need to make considerations about the following names of:

- De SharePoint-sites waarvoor u de formulierverwerking wilt inschakelen; alle sites, enkele sites of specifieke sites
- Uw inhoudscentrum en de naam van de primaire beheerder van de site

## <a name="requirements"></a>Vereisten 

> [!NOTE]
> U moet beschikken over de machtigingen van een globale beheerder of SharePoint-beheerder om toegang te krijgen tot het Microsoft 365-beheercentrum en inhoudsbegrip in te stellen.

Als beheerder kunt u ook op elk gewenst moment wijzigingen aanbrengen in de geselecteerde instellingen en de beheerinstellingen voor inhoudsbegrip in het Microsoft 365-beheercentrum.

## <a name="to-set-up-sharepoint-syntex"></a>SharePoint Syntex instellen

1. Selecteer **Instellingen** in het Microsoft 365-beheercentrum en bekijk het gedeelte **Bestanden en inhoud**.

2. Selecteer onder **Bestanden en inhoud** de optie **Inhoudsbegrip automatiseren**.<br/>

3. Klik op de pagina **Inhoudsbegrip automatiseren** op **Aan de slag** om het installatieproces te doorlopen.<br/>

    > [!div class="mx-imgBorder"]
    > ![Installatie starten](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries. A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.
 
     Bij **Welke SharePoint-bibliotheken moeten de optie weergeven voor het maken van een formulierverwerkingsmodel**, kunt u het volgende selecteren:</br>
      - **Alle SharePoint-bibliotheken** om de optie beschikbaar te maken voor alle SharePoint-bibliotheken in uw organisatie.</br>
      - **Alleen bibliotheken op geselecteerde sites**; selecteer vervolgens de sites waar u de optie beschikbaar wilt maken of upload een lijst met maximaal 50 sites.</br>
      - **Geen SharePoint-bibliotheken** als u de optie niet beschikbaar wilt maken voor sites (u kunt dit wijzigen na de installatie).

   > [!div class="mx-imgBorder"]
   > ![Formulierverwerking configureren](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > Het verwijderen van een site nadat deze is toegevoegd is niet van invloed op bestaande modellen die zijn toegepast op de bibliotheken in die site, of de mogelijkheid om documentbegrip toe te passen op een bibliotheek. 
    
5. Op de pagina **Inhoudscentrum maken** kunt u een SharePoint-inhoudscentrumsite maken waar gebruikers documentbegripmodellen kunnen maken en beheren.

    1. Typ voor **Sitenaam** de naam die u de inhoudscentrumsite wilt geven.
    
    1. The **Site address** will show the URL for your site, based on what you selected for the site name. If you want to change it, click **Edit**.

       > [!div class="mx-imgBorder"]
       > ![Inhoudscentrum maken](../media/content-understanding/admin-cu-create-cc.png)</br>

       Selecteer **Volgende**.

6. On the **Review and finish** page, you can look at your selected setting and choose to make changes. If you are satisfied with your selections, select **Activate**.

7. Klik op **Gereed** op de bevestigingspagina.

8. You'll be returned to your **Automate content understanding** page. From this page, you can select **Manage** to make any changes to your configuration settings. 

## <a name="assign-licenses"></a>Licenties toewijzen

Nadat u SharePoint Syntex hebt geconfigureerd, moet u licenties toewijzen voor de gebruikers die een SharePoint Syntex-functie gebruiken.

Licenties toewijzen:

1. Klik in het Microsoft 365-beheercentrum onder **Gebruikers** op **Actieve gebruikers**.

2. Selecteer de gebruikers aan wie u een licentie wilt toewijzen en klik op **Productlicenties beheren**.

3. Selecteer **Meer toewijzen**.

4. Select **SharePoint Syntex**. Under **Apps**, make sure **Common Data Service for SharePoint Syntex**, **SharePoint Syntex**, and **SharePoint Syntex - SPO type** are all selected.

    > [!div class="mx-imgBorder"]
    > ![SharePoint Syntex-licenties in het Microsoft 365-beheercentrum](../media/content-understanding/sharepoint-syntex-licenses.png)

5. Klik op **Wijzigingen opslaan**.

## <a name="ai-builder-credits"></a>AI Builder-credits

If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits. If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.

U kunt een schatting maken van de benodigde AI Builder-capaciteit [AI Builder-calculator](https://powerapps.microsoft.com/ai-builder-calculator).

Ga naar het [Power platform-beheercentrum](https://admin.powerplatform.microsoft.com/resources/capacity) om uw credits en gebruiksgegevens te bekijken.

## <a name="see-also"></a>Zie ook

[Overzicht van het formulierverwerkingsmodel](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[Stap voor stap: een documentbegripmodel maken (video)](https://www.youtube.com/watch?v=DymSHObD-bg)

