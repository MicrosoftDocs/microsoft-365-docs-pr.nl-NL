---
title: Microsoft feedback voor uw organisatie beheren
f1.keywords:
- NOCSH
ms.author: Kwekua
author: Kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Beheer feedback die uw gebruikers naar Microsoft kunnen sturen over Microsoft-producten.
ms.openlocfilehash: 490081ace32203d015ee8cf3561ccf0ae978bace
ms.sourcegitcommit: dcc6bfd228ca9070975ce9eb14574e084f9ed92c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2021
ms.locfileid: "51657005"
---
# <a name="manage-microsoft-feedback-for-your-organization"></a>Microsoft feedback voor uw organisatie beheren

Als beheerder van een Microsoft 365-organisatie zijn er nu verschillende beleidsregels voor het beheren van de feedbackverzameling en de klantcontactervaring van uw gebruikers bij het gebruik van Microsoft 365-toepassingen. U kunt bestaande Azure Active Directory-groepen in uw organisatie maken en gebruiken voor elk van deze beleidsregels. Met deze agenten kunt u bepalen hoe verschillende afdelingen in uw organisatie feedback naar Microsoft kunnen verzenden. Microsoft bekijkt alle feedback van klanten en gebruikt deze feedback om het product te verbeteren. Als u de feedback-ervaringen **ingeschakeld houdt,** kunt u zien wat uw gebruikers zeggen over de Microsoft-producten die ze gebruiken. De feedback die we van uw gebruikers verzamelen, is binnenkort beschikbaar in het Microsoft 365-beheercentrum.

Zie Meer informatie over [Microsoft-feedback voor uw organisatie](../misc/feedback-user-control.md)voor meer informatie over de typen feedback en hoe Microsoft feedback van gebruikers gebruikt.

In de onderstaande tabel wordt aangegeven welke apps en services momenteel zijn verbonden met het feedbackbeleid dat wordt weergegeven in de onderstaande tabel feedbackbeleid. Zie onder de tabel voor schermafbeeldingen.

|**Apps & Services**|**Feedback in het product** <br> |**In-product enquêtes** <br> |**Metagegevensverzameling** <br> |**Klantafspraak** <br> |
|:-----|:-----|:-----|:-----|:-----|
|**Toegang**|Ja|Ja|Ja|Ja|
|**Excel**|Ja|Ja|Ja|Ja|
|**Office.com**|Binnenkort beschikbaar|Binnenkort beschikbaar|Binnenkort beschikbaar|Binnenkort beschikbaar|
|**OneNote**|Ja|Ja|Ja|Ja|
|**OneDrive**|[Sommige instellingen worden momenteel beheerd door andere besturingselementen.](/onedrive/disable-contact-support-send-feedback)||||
|**Outlook**|Binnenkort beschikbaar|Binnenkort beschikbaar|Binnenkort beschikbaar|Binnenkort beschikbaar|
|**PowerPoint**|Ja|Ja|Ja|Ja|
|**Project**|Binnenkort beschikbaar|Binnenkort beschikbaar|Binnenkort beschikbaar|Binnenkort beschikbaar|
|**Publisher**|Ja|Ja|Ja|Ja|
|**SharePoint**|[Sommige instellingen worden momenteel beheerd door andere besturingselementen.](/powershell/module/sharepoint-online/set-spotenant)||||
|**Teams**|[Sommige instellingen worden momenteel beheerd door andere besturingselementen.](/microsoftteams/manage-feedback-policies-in-teams)||||
|**Word**|Ja|Ja|Ja|Ja|
|**Visio**|Ja|Ja|Ja|Ja|
|**Yammer**|Ja|Ja|Ja|Ja|

[Zie hier enkele voorbeelden van in-product enquêtes en feedback.](https://docs.microsoft.com/microsoft-365/admin/misc/feedback-user-control?view=o365-worldwide#in-product-surveys)

**Metagegevensverzameling**

:::image type="content" source="../../media/feedback-metadata2.png" alt-text="Schermafbeelding: Feedbackpagina met voorbeeld van metagegevens":::

**Klantafspraak**

:::image type="content" source="../../media/feedback-in-product-customer-engagement.png" alt-text="Schermafbeelding: Voorbeeld van onderzoek van klanten in een product":::

## <a name="before-you-begin"></a>Voordat u begint

Uw apparaten moeten een minimaal buildnummer hebben om dit beleid te kunnen gebruiken. Zie de onderstaande tabel voor meer informatie.

|**Build #**|**Win32**|**iOS**|**Android**|**Mac**|**Web**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Feedback in het product|Ten minste 16.0.13328|Ten minste 2,42|Ten minste 16.0.13328|Ten minste 16,42|Openbaar beschikbaar|
|In-product enquêtes|Ten minste 16.0.13328|Ten minste 2,42|Ten minste 16.0.13426|Ten minste 16,42|Uitrol in behandeling|
|Metagegevensverzameling|Ten minste 16.0.13328|Ten minste 2,42|Ten minste 16.0.13328|Ten minste 16,42|Openbaar beschikbaar|
|Klantafspraak|Ten minste 16.0.13328|Ten minste 2,42|Ten minste 16.0.13426|Ten minste 16,42|Uitrol in behandeling|

## <a name="specific-policies-you-can-configure"></a>Specifiek beleid dat u kunt configureren

### <a name="feedback-policies"></a>Feedbackbeleid

|**Beleidsnaam**|**Standaardtoestand**|**Overzicht van besturingselementen**|
|:-----|:-----|:-----|
|Gebruikers toestaan feedback te verzenden naar Microsoft|Aan|Feedbackinvoerpunten in verschillende toepassingen besturingselementen|
|Gebruikers toestaan enquêtes in producten van Microsoft te ontvangen en te beantwoorden|Aan|Enquêteprompts in product besturingselementen|
|Gebruikers toestaan schermafbeeldingen en bijlagen op te nemen wanneer ze feedback verzenden naar Microsoft|Uit|Bepaalt welke metagegevens de gebruiker kan indienen met feedback/enquête|
|Microsoft toestaan feedback van gebruikers op te volgen|Uit|Bepaalt of de gebruiker contactgegevens kan delen met feedback/enquête|
|Gebruikers toestaan logboekbestanden en inhoudsvoorbeelden op te nemen wanneer feedback wordt verzonden naar Microsoft|Uit|Hiermee bepaalt u metagegevens die de gebruiker kan verzenden met feedback/enquête|

## <a name="configure-policies"></a>Beleid configureren

1. Ga naar [https://config.office.com](https://config.office.com) en meld u aan als gebruiker met globale beheerdersmachtigingen.
1. Selecteer **Vervolgens Aanpassen** **beleidsbeheer.**
1. Selecteer **Maken**. 
1. Voer **naam en** beschrijving **in.**
1. Kies de Azure Active Directory-groepen die u wilt configureren.
1. Zoek naar **feedback** en **enquête.**
1. Voor elk beleid dat wordt weergegeven, stelt u de beste waarde in.

Zie Overzicht van de [Office-cloudbeleidsservice](/deployoffice/overview-office-cloud-policy-service)voor meer informatie.

Deze beleidsinstellingen zijn ook beschikbaar als u Groepsbeleid gebruikt. Als u deze beleidsinstellingen wilt gebruiken, downloadt u ten minste versie 5146.1000 van de bestanden met beheerderssjabloon [(ADMX/ADML)](https://www.microsoft.com/download/details.aspx?id=49030)die zijn uitgebracht op 22 maart 2021.

U vindt deze beleidsinstellingen onder Gebruikersconfiguratie -> Beleid -> Beheersjablonen -> Microsoft Office 2016 -> Privacy -> Vertrouwenscentrum.

> [!NOTE]
> Het duurt enkele uren voordat de clienttoepassingen zijn bijgewerkt.
