---
title: eDiscovery-machtigingen toewijzen in het Microsoft 365 compliancecentrum
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7
description: Wijs de machtigingen toe die nodig zijn voor het uitvoeren van eDiscovery-gerelateerde taken met het Microsoft 365 compliancecentrum.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 63afafbb8254169e266e5a3305df64aa9d271f79
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782451"
---
# <a name="assign-ediscovery-permissions-in-the-microsoft-365-compliance-center"></a>eDiscovery-machtigingen toewijzen in het Microsoft 365 compliancecentrum

Als u wilt dat personen een van de [eDiscovery-gerelateerde](ediscovery.md) hulpprogramma's gebruiken in het Microsoft 365 compliancecentrum, moet u ze de juiste machtigingen toewijzen. De eenvoudigste manier om dit te doen is door  de persoon de juiste rollengroep toe te voegen op de pagina Machtigingen in het compliancecentrum. In dit onderwerp worden de machtigingen beschreven die nodig zijn voor het uitvoeren van eDiscovery-taken.
  
De primaire eDiscovery-gerelateerde rollengroep in Microsoft 365 compliancecentrum heet **eDiscovery Manager.** Deze rollengroep bestaat uit twee subgroepen.
  
- **eDiscovery-managers:** een eDiscovery Manager kan eDiscovery-zoekhulpmiddelen gebruiken om inhoudslocaties in de organisatie te zoeken en verschillende zoekacties uit te voeren, zoals voorbeeld van zoekresultaten en het exporteren van zoekresultaten. Leden kunnen ook zaken maken en beheren in Core eDiscovery en Advanced eDiscovery, leden aan een zaak toevoegen en verwijderen, case-holds maken, zoekopdrachten uitvoeren die zijn gekoppeld aan een zaak en casegegevens openen. eDiscovery-managers hebben alleen toegang tot de zaken die ze maken en beheren. Ze hebben geen toegang tot of beheren van zaken die zijn gemaakt door andere eDiscovery-managers.
  
- **eDiscovery-beheerders:** een eDiscovery-beheerder maakt deel uit van de rollengroep eDiscovery Manager en kan dezelfde taken voor zoeken naar inhoud en casebeheer uitvoeren die een eDiscovery Manager kan uitvoeren. Bovendien kan een eDiscovery-beheerder:
  
  - Toegang tot alle zaken die worden vermeld op de **pagina's Core eDiscovery** **en Advanced eDiscovery** in het Microsoft 365 compliancecentrum.

  - Access case data in Advanced eDiscovery for any case in the organization.
  
  - Beheer een eDiscovery-zaak nadat ze zichzelf hebben toevoegen als lid van de zaak.
  
  Zie Meer informatie om redenen waarom u mogelijk eDiscovery-beheerders in uw organisatie [wilt hebben.](#more-information)

> [!NOTE]
> Als u de gegevens van een gebruiker wilt analyseren met Advanced eDiscovery, moet de gebruiker (de beheerder van de gegevens) een Office 365 E5- of Microsoft 365 E5-licentie. Gebruikers met een Office 365 E1- of Office 365- of Microsoft 365 E3-licentie kunnen ook een Microsoft 365 E5 Compliance- Microsoft 365 eDiscovery- en Audit-invoeglicentie krijgen. Beheerders, compliancemedewerkers of juridisch personeel die als lid aan zaken zijn toegewezen en Advanced eDiscovery gebruiken om gegevens te verzamelen, weergeven en analyseren, hebben geen E5-licentie nodig. Zie Abonnementen en licenties in Advanced eDiscovery licenties [in](overview-ediscovery-20.md#subscriptions-and-licensing)Advanced eDiscovery.
  
## <a name="before-you-assign-permissions"></a>Voordat u machtigingen toewijst

- U moet lid zijn van de rollengroep Organisatiebeheer of de rol Rollenbeheer krijgen toegewezen om eDiscovery-machtigingen toe te wijzen in het Microsoft 365 compliancecentrum.

- U kunt de cmdlet [Add-RoleGroupMember](/powershell/module/exchange/Add-RoleGroupMember) in Security & Compliance Center PowerShell gebruiken om een beveiligingsgroep met e-mail toe te voegen als lid van de subgroep eDiscovery Managers in de rollengroep eDiscovery Manager. U kunt echter geen beveiligingsgroep met e-mail toevoegen aan de subgroep eDiscovery-beheerders. Zie Meer [informatie voor meer informatie.](#more-information) 
  
## <a name="assign-ediscovery-permissions"></a>eDiscovery-machtigingen toewijzen

1. Ga naar <https://compliance.microsoft.com> en meld u aan met een account dat machtigingen kan toewijzen.
  
2. Selecteer machtigingen in het linkerdeelvenster Microsoft 365 compliancecentrum.

3. Klik op **de pagina Machtigingen & Rollen** onder **Compliancecentrum** op **Rollen.**

4. Selecteer op **de pagina Rollen van compliancecentrum** de optie **eDiscovery Manager.**
  
5. Ga op **de flyoutpagina van eDiscovery Manager** op een van de volgende stappen uit op basis van de eDiscovery-machtigingen die u wilt toewijzen.
  
    **Een gebruiker een eDiscovery Manager maken:** Selecteer bewerken **naast eDiscovery Manager.**  Klik op **de wizard Kies eDiscovery Manager** op Pictogram toevoegen ![ ](../media/ITPro-EAC-AddIcon.gif) **toevoegen.** Selecteer de gebruiker (of gebruikers) die u wilt toevoegen als eDiscovery-manager en selecteer **vervolgens Toevoegen.** Wanneer u klaar bent met het toevoegen van gebruikers, selecteert u **Gereed.** Selecteer vervolgens op de **wizard Bewerken kies eDiscovery Manager** de optie Opslaan om de wijzigingen op te slaan in het eDiscovery Manager-lidmaatschap. 
  
    **Een gebruiker een eDiscovery-beheerder maken:** Selecteer bewerken **naast eDiscovery-beheerder.**  Klik op **de pagina EDiscovery-beheerder** kiezen op ![ Pictogram toevoegen ](../media/ITPro-EAC-AddIcon.gif) **toevoegen.** Selecteer de gebruiker (of gebruikers) die u wilt toevoegen als **eDiscovery-beheerder** en vervolgens **Toevoegen.** Wanneer u klaar bent met het toevoegen van gebruikers, selecteert u **Gereed.** Selecteer vervolgens op de **wizard Bewerken kiezen eDiscovery-beheerder** opslaan om de wijzigingen op te slaan in het eDiscovery-beheerderslidmaatschap. 
  
> [!NOTE]
> U kunt ook de **cmdlet Add-eDiscoveryCaseAdmin** gebruiken om van een gebruiker een eDiscovery-beheerder te maken. De gebruiker moet echter de rol Case Management krijgen toegewezen voordat u deze cmdlet kunt gebruiken om van de gebruiker een eDiscovery-beheerder te maken. Zie [Add-eDiscoveryCaseAdmin](/powershell/module/exchange/add-ediscoverycaseadmin)voor meer informatie. 
  
Op de **pagina** Machtigingen in het Microsoft 365 compliancecentrum kunt u gebruikers ook eDiscovery-gerelateerde machtigingen toewijzen door ze toe te voegen aan de rollengroepen Compliancebeheerder, Organisatiebeheer en Revisor. Zie RBAC-rollen met betrekking tot [eDiscovery](#rbac-roles-related-to-ediscovery)voor een beschrijving van de eDiscovery-gerelateerde RBAC-rollen die aan elk van deze rollengroepen zijn toegewezen.

## <a name="rbac-roles-related-to-ediscovery"></a>RBAC-rollen met betrekking tot eDiscovery

De volgende tabel bevat de eDiscovery-gerelateerde RBAC-rollen in het Microsoft 365 compliancecentrum en geeft de ingebouwde rollengroepen aan waar elke rol standaard aan is toegewezen.
  
| Rol | Compliancebeheerder | eDiscovery Manager & beheerder | Organisatiebeheer | Revisor |
|:-----|:-----:|:-----:|:-----:|:-----:|
|Case Management <br/> |![Vinkje](../media/checkmark.png) <br/> |![Vinkje](../media/checkmark.png) <br/> |![Vinkje](../media/checkmark.png) <br/> | <br/> |
|Communicatie <br/> | <br/> |![Vinkje](../media/checkmark.png) <br/> | <br/> | <br/> |
|Compliancezoekactie <br/> |![Vinkje](../media/checkmark.png) <br/> |![Vinkje](../media/checkmark.png) <br/> |![Vinkje](../media/checkmark.png) <br/> | <br/> |
|Bewaarder <br/> | <br/> |![Vinkje](../media/checkmark.png) <br/> | <br/> | <br/> |
|Exporteren <br/> | <br/> |![Vinkje](../media/checkmark.png) <br/> | <br/> | <br/> |
|Wacht houden <br/>  |![Vinkje](../media/checkmark.png) <br/> |![Vinkje](../media/checkmark.png) <br/> |![Vinkje](../media/checkmark.png) <br/> | <br/> |
|Voorbeeld <br/>  | <br/> |![Vinkje](../media/checkmark.png) <br/> | <br/> | <br/> |
|Beoordelen <br/>  | <br/> |![Vinkje](../media/checkmark.png) <br/> | <br/> |![Vinkje](../media/checkmark.png) <br/> |
|RMS Decrypt <br/>  ||![Vinkje](../media/checkmark.png) <br/> |||
|Zoeken en zuiveren <br/> | <br/> | <br/> |![Vinkje](../media/checkmark.png)           <br/> | <br/> |
||||
  
In de volgende secties worden alle eDiscovery-gerelateerde RBAC-rollen in de vorige tabel beschreven.

### <a name="case-management"></a>Case Management

Met deze rol kunnen gebruikers toegang tot Core eDiscovery en Advanced eDiscovery in het Microsoft 365 compliancecentrum. Zoals eerder is uitgelegd, moet aan een gebruiker de rol Case Management worden toegewezen voordat u de **cmdlet Add-eDiscoveryCaseAdmin** kunt gebruiken om van de gebruiker een eDiscovery-beheerder te maken.

Zie voor meer informatie:

- [Aan de slag met Core eDiscovery](get-started-core-ediscovery.md)

- [Aan de slag met Advanced eDiscovery](get-started-with-advanced-ediscovery.md)

### <a name="communication"></a>Communicatie

Met deze rol kunnen gebruikers alle communicatie met de beheerders beheren die zijn geïdentificeerd in Advanced eDiscovery geval. Dit omvat het maken van wachtnotificaties, herinneringen in de wacht houden en escalaties naar beheer. De gebruiker kan ook beheerdersbevestiging van wachtbevestigingsmeldingen bijhouden en de toegang beheren tot de bewaarderportal die door elke bewaarder wordt gebruikt om de communicatie bij te houden voor de gevallen waarin ze zijn geïdentificeerd als een bewaarder.

Zie Werken met communicatie [in Advanced eDiscovery.](managing-custodian-communications.md)

### <a name="compliance-search"></a>Compliancezoekactie

Met deze rol kunnen gebruikers het hulpprogramma Inhoud zoeken uitvoeren in het Microsoft 365-compliancecentrum om te zoeken in postvakken en openbare mappen, SharePoint Online-sites, OneDrive voor Bedrijven-sites, Skype voor Bedrijven-gesprekken, Microsoft 365-groepen en Microsoft Teams- en Yammer-groepen. Met deze rol kan een gebruiker een schatting van de zoekresultaten krijgen en exportrapporten maken, maar er zijn andere rollen nodig om inhoudszoekacties te starten, zoals het bekijken, exporteren of verwijderen van zoekresultaten.

Gebruikers aan wie de rol Compliance zoeken is toegewezen, maar de voorbeeldrol niet hebben, kunnen een voorbeeld bekijken van de resultaten van een zoekopdracht waarin de voorbeeldactie is gestart door een gebruiker die de voorbeeldrol heeft toegewezen. De gebruiker zonder de voorbeeldrol kan een voorbeeld van de resultaten bekijken tot twee weken nadat de eerste voorbeeldactie is gemaakt.

Op dezelfde manier kunnen gebruikers die de rol Compliance zoeken hebben toegewezen maar niet de rol Exporteren hebben, de resultaten downloaden van een zoekopdracht waarin de exportactie is gestart door een gebruiker die de rol Exporteren heeft toegewezen. De gebruiker zonder de rol Exporteren kan de resultaten van een zoekopdracht downloaden tot twee weken nadat de eerste exportactie is gemaakt. Daarna kunnen ze de resultaten alleen downloaden als iemand met de rol Exporteren de export opnieuw start.

Zie Zoeken naar inhoud [in Office 365.](content-search.md)

### <a name="custodian"></a>Bewaarder

Met deze rol kunnen gebruikers beheerders identificeren en beheren voor Advanced eDiscovery gevallen en de gegevens uit Azure Active Directory en andere bronnen gebruiken om gegevensbronnen te vinden die zijn gekoppeld aan bewaarders. De gebruiker kan andere gegevensbronnen, zoals postvakken, SharePoint sites en Teams in een zaak, koppelen aan bewaarders. De gebruiker kan ook de gegevensbronnen die aan bewaarders zijn gekoppeld, juridisch in de wacht houden om inhoud in de context van een zaak te behouden.

Zie Werken met beheerders [in](managing-custodians.md)Advanced eDiscovery.

### <a name="export"></a>Exporteren

Met de rol kunnen gebruikers de resultaten van een inhoudszoekactie exporteren naar een lokale computer. Hiermee kunnen ze ook zoekresultaten voorbereiden op analyse in Advanced eDiscovery.

Zie Zoekresultaten exporteren vanuit Microsoft 365 [compliancecentrum voor](export-search-results.md)meer informatie over het exporteren van zoekresultaten.

### <a name="hold"></a>Wacht houden

Met deze rol kunnen gebruikers inhoud in de wacht zetten in postvakken, openbare mappen, sites, Skype voor Bedrijven gesprekken en Microsoft 365 groepen. Wanneer inhoud in de wacht staat, kunnen inhoudseigenaren de oorspronkelijke inhoud nog steeds wijzigen of verwijderen, maar de inhoud blijft behouden totdat de bewaartermijn is verwijderd of totdat de duur van de bewaartermijn verloopt.

Zie:

- [Een hold maken in Core eDiscovery](create-ediscovery-holds.md) 

- [Een wacht in een Advanced eDiscovery](add-custodians-to-case.md)

### <a name="preview"></a>Voorbeeld

Met deze rol kunnen gebruikers een lijst bekijken met items die zijn geretourneerd uit een inhoudszoekactie. Ze kunnen ook elk item uit de lijst openen en weergeven om de inhoud ervan weer te geven.

### <a name="review"></a>Beoordelen

Met deze rol hebben gebruikers toegang tot revisiesets in [Advanced eDiscovery.](overview-ediscovery-20.md) Gebruikers aan wie deze rol is toegewezen, kunnen de lijst met zaken zien en openen op de **pagina eDiscovery > Advanced** in het Microsoft 365 compliancecentrum waar ze lid van zijn. Nadat de gebruiker toegang heeft tot een Advanced eDiscovery, kunnen ze Sets **controleren** selecteren om toegang te krijgen tot casegegevens. Met deze rol kan de gebruiker geen voorbeeld bekijken van de resultaten van een verzamelingszoekactie die is gekoppeld aan de zaak of andere zoek- of casebeheertaken uitvoeren. Gebruikers met deze rol hebben alleen toegang tot de gegevens in een revisieset.

### <a name="rms-decrypt"></a>RMS Decrypt

Met deze rol kunnen gebruikers met rechten beveiligde e-mailberichten bekijken bij het bekijken van zoekresultaten en het exporteren van ontsleutelde met rechten beveiligde e-mailberichten. Met deze rol kunnen gebruikers ook een bestand weergeven (en exporteren) dat is versleuteld met een Microsoft-versleutelingstechnologie wanneer het versleutelde bestand is gekoppeld aan een e-mailbericht dat is opgenomen in de resultaten van een eDiscovery-zoekopdracht. [](encryption.md) Bovendien kunnen gebruikers met deze rol versleutelde e-mailbijlagen bekijken en opvragen die zijn toegevoegd aan een revisieset in Advanced eDiscovery. Zie Ontsleuteling in eDiscovery voor meer informatie over ontsleuteling in eDiscovery Microsoft 365 [eDiscovery-hulpprogramma's.](ediscovery-decryption.md)

### <a name="search-and-purge"></a>Zoeken en zuiveren

Met deze rol kunnen gebruikers gegevens bulksgewijs verwijderen die overeenkomen met de criteria van een inhoudszoekactie. Zie E-mailberichten zoeken en verwijderen in uw organisatie voor [meer informatie.](search-for-and-delete-messages-in-your-organization.md)

## <a name="more-information"></a>Meer informatie

- **Waarom een eDiscovery-beheerder maken?** Zoals eerder uitgelegd, is een eDiscovery-beheerder lid van de eDiscovery Manager-rollengroep die alle eDiscovery-zaken in uw organisatie kan bekijken en openen. Deze mogelijkheid om toegang te krijgen tot alle eDiscovery-zaken heeft twee belangrijke doeleinden:

  - Als een persoon die het enige lid is van een eDiscovery-zaak uw organisatie verlaat, heeft niemand (inclusief leden van de rollengroep Organisatiebeheer of een ander lid van de eDiscovery Manager-rollengroep) toegang tot die eDiscovery-zaak omdat ze geen lid zijn van een zaak. In dit geval is er geen manier om toegang te krijgen tot de gegevens in het geval. Maar omdat een eDiscovery-beheerder toegang heeft tot alle eDiscovery-zaken in de organisatie, kunnen ze de zaak bekijken en zichzelf of een andere eDiscovery-manager toevoegen als lid van de zaak.

  - Omdat een eDiscovery-beheerder alle core eDiscovery- en Advanced eDiscovery-cases kan bekijken en openen, kunnen ze alle zaken en bijbehorende compliancezoekingen controleren en controleren. Dit kan helpen om misbruik van compliancezoekingen of eDiscovery-zaken te voorkomen. En omdat eDiscovery-beheerders toegang hebben tot mogelijk gevoelige informatie in de resultaten van een compliancezoekactie, moet u het aantal personen beperken dat eDiscovery-beheerders zijn.

- **Kan ik een groep toevoegen als lid van de rollengroep eDiscovery Manager?** Zoals eerder uitgelegd, kunt u een beveiligingsgroep met e-mail toevoegen als lid van de subgroep eDiscovery Managers in de rollengroep eDiscovery Manager met behulp van de cmdlet **Add-RoleGroupMember** in Security & Compliance Center PowerShell. U kunt bijvoorbeeld de volgende opdracht uitvoeren om een beveiligingsgroep met e-mail toe te voegen aan de rollengroep eDiscovery Manager. 

  ```powershell
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    Exchange distributiegroepen en Microsoft 365 groepen worden niet ondersteund. U moet een beveiligingsgroep met e-mail gebruiken, die u kunt maken in Exchange Online PowerShell door het uitvoeren `New-DistributionGroup -Type Security` van . U kunt ook een beveiligingsgroep met e-mail maken (en leden toevoegen) in het Exchange beheercentrum of in het Microsoft 365 beheercentrum. Het kan tot 60 minuten duren nadat u deze hebt gemaakt, zodat er een nieuwe beveiligingsfunctie voor e-mail beschikbaar is om toe te voegen aan de rollengroep eDiscovery Managers. 

    Zoals eerder is aangegeven, kunt u van een beveiligingsgroep met e-mail geen eDiscovery-beheerder maken met de cmdlet **Add-eDiscoveryCaseAdmin** in Security & Compliance Center PowerShell. U kunt alleen afzonderlijke gebruikers toevoegen als eDiscovery-beheerders.

    U kunt ook geen beveiligingsgroep met e-mail toevoegen als lid van een zaak.