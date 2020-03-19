---
title: Microsoft 365-rapporten in het beheercentrum - E-mailactiviteit
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44
description: Meer informatie over het ontvangen van een e-mailactiviteitsrapport met het dashboard Microsoft 365 Reports in het Microsoft 365-beheercentrum.
ms.openlocfilehash: 34cacd3a1c4682a53fdefd8f3fe26c38651676df
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42805529"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-activity"></a>Microsoft 365-rapporten in het beheercentrum - E-mailactiviteit

Het dashboard Microsoft 365 **Reports** toont u het activiteitenoverzicht voor de producten in uw organisatie. U kunt inzoomen op rapporten op het niveau van afzonderlijke producten om een gedetailleerder inzicht te krijgen in de activiteiten binnen elk product. Bekijk [het overzichtsonderwerp over rapporten](activity-reports.md).
  
Via de pagina Rapporten kunt u bijvoorbeeld een globale weergave krijgen van het e-mailverkeer in uw organisatie, waarna u kunt inzoomen op de widget E-mailactiviteit om inzicht te krijgen in de trends en de details op gebruikersniveau van de e-mailactiviteiten in uw organisatie.
  
> [!NOTE]
> U moet een globale beheerder, globale lezer of rapportenlezer in Microsoft 365 of een Exchange-, SharePoint- of Skype voor Bedrijven-beheerder zijn om rapporten te kunnen bekijken. 

## <a name="how-to-get-to-the-email-activity-report"></a>Hoe u toegang tot het rapport E-mailactiviteit krijgt

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.

    
2. Selecteer \> **Exchange-e-mailactiviteit**in **Exchange** de vervolgkeuzelijst **Een rapport selecteren** .
  
## <a name="interpret-the-email-activity-report"></a>Het rapport E-mailactiviteit interpreteren

Met de grafieken **Activiteit** en **Gebruikers** kunt u inzicht krijgen in de e-mailactiviteiten van uw gebruikers. 
  
![E-mailactiviteitsrapport](../../media/21c1e082-317e-4b5e-b736-661ca5744def.png)
  
|||
|:-----|:-----|
|1.  <br/> |In het **e-mailactiviteitenrapport** kunnen trends worden weergegeven voor de laatste 7, 30, 90 of 180 dagen. Als u echter een bepaalde dag in het rapport selecteert, worden in de tabel (7) gegevens weergegeven gedurende maximaal 28 dagen na de huidige datum (niet de datum waarop het rapport is gegenereerd).  <br/> |
|2.  <br/> |De gegevens in elk rapport bestrijken meestal tot de laatste 24 tot 48 uur.  <br/> |
|3.  <br/> |De grafiek **Activiteit** geeft inzicht in de trend van de hoeveelheid e-mailactiviteit die zich afspeelt binnen uw organisatie. U krijgt een beeld van de onderverdeling van de verzonden, gelezen of ontvangen e-mails.  <br/> |
|4.  <br/> |De grafiek **Gebruiker** geeft een beeld van de trend van het aantal unieke gebruikers die de e-mailactiviteiten genereren. U kunt de trend bekijken van gebruikers die e-mails verzenden, lezen of ontvangen.  <br/> |
|5.  <br/> | In de grafiek **Activiteit** is de Y-as het aantal activiteiten van verzonden, ontvangen en gelezen e-mails.  <br/>  In de grafiek **Gebruikers** is de Y-as de activiteit die de gebruiker heeft uitgevoerd (e-mails verzenden, ontvangen of lezen).  <br/>  De X-as van beide grafieken is het geselecteerde datumbereik voor dit specifieke rapport.  <br/> |
|6.  <br/> |U de reeksen die u in de grafiek ziet filteren door een item in de legenda te selecteren. Selecteer in het **activiteitsdiagram** bijvoorbeeld Grafieken **Verzonden,** **Ontvangen**of **Filter lezen** ![voor specifieke gerelateerde gegevens](../../media/a3a9cb3d-b8b1-4c6a-9f6f-18aebf74c3a0.png) om alleen de informatie met betrekking tot elk schema te zien. Door deze selectie te wijzigen, verandert de informatie in de rastertabel niet.  <br/> |
|7.  <br/> | De tabel toont een onderverdeling van de e-mailactiviteiten op gebruikersniveau. Hier ziet u alle gebruikers aan wie een Exchange-product is toegewezen, en de bijbehorende e-mailactiviteiten. <br/> <br/> **Gebruikersnaam** is het e-mailadres van de gebruiker.  <br/> **Weergavenaam** is de volledige naam als de gebruiker.  <br/> **Verwijderd** verwijst naar de gebruiker van wie de huidige status Verwijderd is, maar die een deel van de rapportageperiode van het rapport actief was.  <br/> **Verwijderd op** is de datum waarop de gebruiker is verwijderd.  <br/> **Datum van laatste activiteit** verwijst naar de laatste keer dat de gebruiker een e-mail heeft gelezen of verzonden.  <br/> **Verzendacties** is het aantal keren dat een actie E-mailbericht verzenden voor de gebruiker is vastgelegd.  <br/> **Ontvangstacties** is het aantal keren dat een actie E-mail ontvangen voor de gebruiker is vastgelegd.  <br/> **Leesactie** is het aantal keren dat een actie E-mailbericht lezen voor de gebruiker is vastgelegd.  <br/> **Toegewezen product** zijn de producten die aan deze gebruiker zijn toegewezen.  <br/>  Als het beleid van uw organisatie verhindert dat u rapporten weergeeft waarin gebruikersgegevens kunnen worden geïdentificeerd, kunt u de privacy-instelling voor elk van deze rapporten wijzigen. Bekijk de details van het **gebruikersniveau?** [Activity Reports in the Microsoft 365 admin center](activity-reports.md)  <br/> |
|8.  <br/> |U de rapportgegevens ook exporteren naar een **Export** ![Csv-bestand](../../media/816a224b-6ca7-4967-a135-4f6427f64dc8.JPG) van Excel door de koppeling Exporteren exporteren te selecteren. Hiermee exporteert u de gegevens van alle gebruikers en kunt u eenvoudige sortering en filtering toepassen voor verdere analyse. Als u minder dan 2000 gebruikers hebt, kunt u de tabel in het rapport zelf sorteren en filteren. Als u meer dan 2000 gebruikers hebt, moet u de gegevens exporteren om te kunnen filteren en sorteren.  <br/> |
|||
   
Opmerking: het e-mailactiviteitenrapport is alleen beschikbaar voor postvakken die zijn gekoppeld aan gebruikers die licenties hebben.
