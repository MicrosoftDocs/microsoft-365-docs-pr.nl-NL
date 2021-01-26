---
title: SharePoint Syntex instellen
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
localization_priority: Priority
description: Inhoudsbegrip instellen in Project Cortex
ms.openlocfilehash: a9713f1d28cf863ab827d2975e84042026105b3f
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976377"
---
# <a name="set-up-sharepoint-syntex"></a>SharePoint Syntex instellen

Beheerders kunnen het Microsoft 365-beheercentrum gebruiken om [Microsoft SharePoint Syntex](index.md) in te stellen. 

Houd rekening met het volgende voordat u begint:

- Op welke SharePoint-sites schakelt u het verwerken van formulieren in? Op alle sites, enkele sites of alleen specifieke sites?
- Welke naam geeft u aan uw standaard inhoudscentrum?

U kunt de instellingen wijzigen na de eerste installatie in het Microsoft 365-beheercentrum.

Voordat u met het instellen begint, moet u plannen wat de beste manier is om inhoudsbegrip te configureren voor uw omgeving. Zo moet u bijvoorbeeld de volgende beslissingen nemen:

- De SharePoint-sites waarvoor u de formulierverwerking wilt inschakelen; alle sites, enkele sites of specifieke sites
- De naam en beheerders of het inhoudscentrum

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

4. Op de pagina **Formulierverwerking configureren** kunt u kiezen of u wilt dat gebruikers formulierverwerkingsmodellen kunnen maken in specifieke SharePoint-documentbibliotheken. Er is een menuoptie beschikbaar op het lint van de documentbibliotheek voor het **maken van een formulierverwerkingsmodel** in SharePoint-documentbibliotheken waarin dit is ingeschakeld.
 
     Bij **Welke SharePoint-bibliotheken moeten de optie weergeven voor het maken van een formulierverwerkingsmodel**, kunt u het volgende selecteren:</br>
      - **Bibliotheken op alle SharePoint-sites** om de optie beschikbaar te maken voor alle SharePoint-bibliotheken in uw organisatie.</br>
      - **Bibliotheken op geselecteerde SharePoint-sites**; selecteer vervolgens de sites waar u de optie beschikbaar wilt maken of upload een lijst met maximaal 50 sites.</br>
      - **Geen SharePoint-bibliotheken** als u de optie niet beschikbaar wilt maken voor sites (u kunt dit wijzigen na de installatie).

   > [!div class="mx-imgBorder"]
   > ![Formulierverwerking configureren](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > Het verwijderen van een site nadat deze is toegevoegd is niet van invloed op bestaande modellen die zijn toegepast op de bibliotheken in die site, of de mogelijkheid om documentbegrip toe te passen op een bibliotheek. 
    
5. Op de pagina **Inhoudscentrum maken** kunt u een SharePoint-inhoudscentrumsite maken waar gebruikers documentbegripmodellen kunnen maken en beheren.

    1. Typ voor **Sitenaam** de naam die u de inhoudscentrumsite wilt geven.
    
    1. Bij **Siteadres** wordt de URL voor uw site weergegeven op basis van wat u hebt opgegeven als sitenaam. Klik op **Bewerken** om dit te wijzigen.

       > [!div class="mx-imgBorder"]
       > ![Inhoudscentrum maken](../media/content-understanding/admin-cu-create-cc.png)</br>

       Selecteer **Volgende**.

6. Op de pagina **Controleren en voltooien** kunt u de geselecteerde instelling bekijken en wijzigingen aanbrengen. Selecteer **Activeren** wanneer u tevreden bent met uw selecties.

7. Klik op **Gereed** op de bevestigingspagina.

8. U gaat terug naar de pagina **Inhoudsbegrip automatiseren**. Op deze pagina kunt u **Beheren** selecteren om wijzigingen aan te brengen in de configuratie-instellingen. 

## <a name="assign-licenses"></a>Licenties toewijzen

Nadat u SharePoint Syntex hebt geconfigureerd, moet u licenties toewijzen voor de gebruikers die een SharePoint Syntex-functie gebruiken.

Licenties toewijzen:

1. Klik in het Microsoft 365-beheercentrum onder **Gebruikers** op **Actieve gebruikers**.

2. Selecteer de gebruikers aan wie u een licentie wilt toewijzen en klik op **Productlicenties beheren**.

3. Selecteer **Meer toewijzen**.

4. Selecteer **SharePoint Syntex**. Zorg ervoor dat onder **Apps** **Algemene Gegevens sService voor SharePoint Syntex**, **SharePoint Syntex** en **SharePoint Syntex-SPO type** allemaal zijn geselecteerd.

    > [!div class="mx-imgBorder"]
    > ![SharePoint Syntex-licenties in het Microsoft 365-beheercentrum](../media/content-understanding/sharepoint-syntex-licenses.png)

5. Klik op **Wijzigingen opslaan**.

## <a name="ai-builder-credits"></a>AI Builder-credits

Als u 300 of meer SharePoint Syntex-licenties voor SharePoint Syntex in uw organisatie hebt, worden er 1 miljoen AI Builder-credits aan u toegewezen. Als u minder dan 300 licenties hebt, moet u AI Builder-credits kopen om formulierverwerking te kunnen gebruiken.

U kunt een schatting maken van de benodigde AI Builder-capaciteit [AI Builder-calculator](https://powerapps.microsoft.com/ai-builder-calculator).

Ga naar het [Power platform-beheercentrum](https://admin.powerplatform.microsoft.com/resources/capacity) om uw credits en gebruiksgegevens te bekijken.

## <a name="see-also"></a>Zie ook

[Overzicht van het formulierverwerkingsmodel](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[Stap voor stap: een documentbegripmodel maken (video)](https://www.youtube.com/watch?v=DymSHObD-bg)
