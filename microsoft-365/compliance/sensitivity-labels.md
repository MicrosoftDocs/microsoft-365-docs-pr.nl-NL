---
title: Meer informatie over vertrouwelijkheidslabels
f1.keywords:
- CSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Gebruik vertrouwelijkheidslabels van Microsoft Information Protection (MIP) om vertrouwelijke inhoud te classificeren en te beveiligen.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: e1de507dd5ec9508df0318c8ba2ef30af795e25b
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430790"
---
# <a name="learn-about-sensitivity-labels"></a>Meer informatie over vertrouwelijkheidslabels

>*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!NOTE]
> Zie [Vertrouwelijkheidslabels toepassen op uw bestanden en e-mail in Office](https://support.microsoft.com/topic/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9) als u meer informatie zoekt over vertrouwelijkheidslabels die u in uw Office-apps ziet.
>
> De informatie op deze pagina is bedoeld voor IT-beheerders die dergelijke labels kunnen maken en configureren.

Om hun werk af te krijgen, werken personen in uw organisatie samen met anderen binnen de organisatie, maar ook met externe personen. Dit betekent dat de inhoud niet langer achter een firewall blijft. De inhoud kan overal worden gebruikt, op verschillende apparaten, apps en services. Wanneer de inhoud elders wordt gebruikt, wilt u dat dat gebeurt in een veilige, beschermde manier die voldoet aan het bedrijfs- en nalevingsbeleid van uw organisatie.

Met vertrouwelijkheidslabels uit het Microsoft Information Protection-oplossing kunt u de gegevens van uw organisatie classificeren en beschermen en ervoor zorgen dat de productiviteit van gebruikers en hun vermogen om samen te werken niet wordt belemmerd.

Voorbeeld met beschikbare vertrouwelijkheidslabels in Excel op het tabblad **Start** op het lint. In dit voorbeeld wordt het toegepaste label weergegeven op de statusbalk:

![Vertrouwelijkheidslabel op het lint en de statusbalk van Excel](../media/Sensitivity-label-in-Excel.png)

Om vertrouwelijkheidslabels toe te passen, moeten gebruikers zijn aangemeld met hun Microsoft 365-werk- of schoolaccount.

> [!NOTE]
> Voor tenants van de Amerikaanse overheid worden vertrouwelijkheidslabels nu ondersteund voor alle platforms:
> - Voor GCC- en GCC Hoog-omgevingen: Opmerkingen bij de release voor [Office voor Windows](/officeupdates/current-channel#version-2101-january-26) en [Office voor Mac](/officeupdates/release-notes-office-for-mac#feature-updates-2)
> - Voor DoD-omgevingen: Opmerkingen bij de release voor [Office voor Windows](/officeupdates/current-channel#version-2103-march-30)
>
> Zie [Azure Information Protection Premium Government Service Description](/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description) als u de geïntegreerde labelclient en scanner van Azure Information Protection gebruikt voor deze omgevingen.

U kunt vertrouwelijkheidslabels gebruiken om:
  
- **Beveiligingsinstellingen te bieden met versleuteling en inhoudsmarkeringen.** Pas bijvoorbeeld een label 'Vertrouwelijk' toe op een document of e-mail en het label versleutelt de inhoud en past een watermerk 'Vertrouwelijk' toe. Inhoudsmarkeringen omvatten kopteksten, voetteksten en watermerken en versleuteling kan ook beperken welke acties geautoriseerde personen kunnen uitvoeren op de inhoud.

- **Inhoud te beveiligen in Office-apps op verschillende platforms en apparaten.** Ondersteund door Word, Excel, PowerPoint en Outlook in de Office-bureaubladtoepassingen en de webversie van Office. Ondersteund in Windows, macOS, iOS en Android.

- **Inhoud te beveiligen in apps en services van derden** door Microsoft Cloud App Security te gebruiken. Met Cloud App Security kunt u inhoud detecteren, classificeren, labelen en beveiligen in apps en services van derden, zoals SalesForce, Box of Dropbox, zelfs als de app of service van derden geen vertrouwelijkheidslabels leest of ondersteunt.

- **Containers te beveiligen** die Teams-, Microsoft 365 Groepen- en SharePoint-sites bevatten. Stel bijvoorbeeld privacy-instellingen, toegang van externe gebruikers en extern delen en toegang van onbeheerde apparaten in.

- **Vertrouwelijkheidslabels uit te breiden naar Power BI**: wanneer u deze mogelijkheid inschakelt, kunt u labels toepassen en zien in Power BI en gegevens beveiligen wanneer die buiten de service worden opgeslagen.

- **Vertrouwelijkheidslabels uit te breiden naar assets in Azure Purview**: wanneer u deze mogelijkheid inschakelt (momenteel in preview), kunt u uw vertrouwelijkheidslabels toepassen op assets zoals SQL-kolommen, bestanden in Azure Blob Storage en meer. 

- **Vertrouwelijkheidslabels uitbreiden naar apps en services van derden.** Met Microsoft Information Protection SDK kunnen apps van derden vertrouwelijkheidslabels lezen en beveiligingsinstellingen toepassen.

- **Inhoud te classificeren zonder beveiligingsinstellingen.** U kunt ook gewoon een label toepassen als resultaat van de classificatie van de inhoud. Hierdoor kunnen gebruikers een visuele toewijzing krijgen van de classificatie van de labelnamen van uw organisatie en kunnen ze de labels gebruiken om gebruiksrapporten te genereren en activiteitsgegevens te zien van uw vertrouwelijke inhoud. Op basis van deze informatie kunt u er altijd voor kiezen om de beveiligingsinstellingen later toe te passen.

In al deze gevallen kunnen vertrouwelijkheidslabels in Microsoft 365 u helpen de juiste acties op de juiste inhoud uit te voeren. Met vertrouwelijkheidslabels kunt u gegevens in uw organisatie classificeren en beveiligingsinstellingen afdwingen op basis van die classificatie.

Zie [Veelvoorkomende scenario's voor vertrouwelijkheidslabels](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels) voor meer informatie over dit en andere scenario's die worden ondersteund door vertrouwelijkheidslabels. Er worden voortdurend nieuwe functies ontwikkeld die vertrouwelijkheidslabels ondersteunen, daarom is het mogelijk handig om te verwijzen naar de [Microsoft 365 roadmap](https://aka.ms/MIPC/Roadmap).

## <a name="what-a-sensitivity-label-is"></a>Wat is een vertrouwelijkheidslabel?

Wanneer u een vertrouwelijkheidslabel toewijst aan inhoud, lijkt het op een stempel dat wordt toegepast en is dit:

- **Aanpasbaar.** U kunt specifiek voor uw organisatie- en bedrijfsbehoeften categorieën maken voor verschillende niveaus van vertrouwelijke inhoud binnen uw organisatie. Bijvoorbeeld: Persoonlijk, Openbaar, Algemeen, Vertrouwelijk en Zeer vertrouwelijk.

- **Niet-versleutelde tekst.** Aangezien een label wordt opgeslagen in niet-versleutelde tekst in de metagegevens van bestanden en e-mailberichten, kunnen apps en services deze lezen en zo nodig vervolgens hun eigen beveiligingsacties toepassen.

- **Persistent.** Aangezien het label wordt opgeslagen in de metagegevens van bestanden en e-mailberichten blijft het label bij de inhoud, ongeacht waar die wordt opgeslagen. De unieke labelidentificatie wordt de basis voor het toepassen en afdwingen van beleid dat u configureert.

Wanneer een vertrouwelijkheidslabel wordt weergegeven voor gebruikers, lijkt het een tag in de apps die ze gebruiken en kan het eenvoudig worden geïntegreerd in hun bestaande werkstromen.

Er kan één vertrouwelijkheidslabel worden toegepast op elk item dat vertrouwelijkheidslabels ondersteunt. Op documenten en e-mailberichten kunnen zowel een vertrouwelijkheidslabel als een [retentielabel](retention.md#retention-labels) worden toegepast.

> [!div class="mx-imgBorder"]
> ![Vertrouwelijkheidslabel toegepast op een e-mail](../media/Sensitivity-label-on-email.png)

## <a name="what-sensitivity-labels-can-do"></a>Wat vertrouwelijkheidslabels kunnen doen

Nadat een vertrouwelijkheidslabel is toegepast op een e-mail of document worden alle geconfigureerde beveiligingsinstellingen voor dat label afgedwongen op de inhoud. U kunt een vertrouwelijkheidslabel configureren om:

- **Versleutelen** van e-mailberichten en documenten om te voorkomen dat onbevoegden toegang hebben tot deze gegevens. U kunt er daarnaast voor kiezen welke gebruikers of groep machtigingen hebben om welke acties uit te voeren voor hoelang. U kunt er bijvoorbeeld voor kiezen om alle gebruikers in uw organisatie een document te laten bewerken, terwijl een specifieke groep in een andere organisatie dit alleen mag bekijken. In plaats van door de beheerder gedefinieerde machtigingen kunt u uw gebruikers machtigingen laten toewijzen aan de inhoud wanneer zij een label toepassen. 
    
    Zie [Toegang tot inhoud beperken met versleuteling en vertrouwelijkheidslabels](encryption-sensitivity-labels.md) voor meer informatie over de **Versleutelings** instellingen bij het maken of bewerken van een vertrouwelijkheidslabel.

- **Markeren van de inhoud** wanneer u Office-apps gebruikt door watermerken, kopteksten of voetteksten toe te voegen aan e-mail of documenten waarop een label is toegepast. Watermerken kunnen worden toegepast op documenten, maar niet op e-mailberichten. Voorbeeld koptekst en watermerk:
    
    ![Watermerk en koptekst toegepast op document](../media/Sensitivity-label-watermark-header.png)
    
    Wilt u controleren wanneer inhoudsmarkeringen worden toegepast? Zie [Wanneer Office-apps inhoudsmarkering en versleuteling toepassen](sensitivity-labels-office-apps.md#when-office-apps-apply-content-marking-and-encryption).
    
    Bepaalde, maar niet alle apps ondersteunen dynamische markeringen door het gebruik van variabelen. Voeg bijvoorbeeld de labelnaam of documentnaam in de koptekst, voettekst of het watermerk in. Zie [Dynamische markeringen met variabelen](sensitivity-labels-office-apps.md#dynamic-markings-with-variables) voor meer informatie.
    
    Lengte van tekenreeksen: watermerken mogen niet langer zijn dan 255 tekens. Kop- en voetteksten mogen niet langer zijn dan 1024 tekens, behalve in Excel. In Excel zijn kop- en voetteksten beperkt tot maximaal 255 tekens, maar deze limiet omvat ook tekens die niet zichtbaar zijn, zoals opmaakcodes. Wanneer die limiet wordt bereikt, wordt de tekenreeks die u invoert niet weergegeven in Excel.

- **Inhoud beveiligen in containers, zoals sites en groepen** wanneer u de mogelijkheid inschakelt om [vertrouwelijkheidslabels te gebruiken met Microsoft Teams-, Microsoft 365 Groepen- en SharePoint-sites](sensitivity-labels-teams-groups-sites.md).
    
    U kunt beveiligingsinstellingen pas configureren voor groepen en sites wanneer u deze mogelijkheid inschakelt. Met deze labelconfiguratie worden documenten of e-mailberichten niet automatisch gelabeld, maar de inhoud wordt beveiligd door de labelinstellingen door de toegang te beheren tot de container waar de inhoud kan worden opgeslagen. Deze privacy-instellingen omvatten toegang van externe gebruikers en extern delen en toegang van onbeheerde apparaten.

- **Het label automatisch toepassen op bestanden en e-mailberichten of een label aanbevelen.** Kies hoe vertrouwelijke gegevens die u wilt labelen, worden geïdentificeerd. Het label kan automatisch worden toegepast of u kunt gebruikers vragen om het label dat u aanbeveelt toe te passen. Wanneer u een label aanbeveelt, wordt de prompt weergegeven bij elke tekst. Bijvoorbeeld:
    
    ![Vraag om een verplicht label toe te wijzen](../media/Sensitivity-label-Prompt-for-required-label.png)
    
    Zie [Automatisch een vertrouwelijkheidslabel toepassen op inhoud](apply-sensitivity-label-automatically.md) voor Office-apps en [Automatisch een label toepassen op uw gegevens in Azure Purview](/azure/purview/create-sensitivity-label) voor meer informatie over de instellingen voor het **Automatisch labelen van bestanden en e-mailberichten** bij het maken of bewerken van een vertrouwelijkheidslabel.

### <a name="label-scopes"></a>Labelbereiken

Wanneer u een vertrouwelijkheidslabel maakt, wordt u gevraagd om het bereik van het label te configureren. Hierdoor worden twee dingen bepaald:
- welke labelinstellingen u kunt configureren voor dat label
- waar het label zichtbaar is voor de gebruikers

Met deze bereikconfiguratie kunt u vertrouwelijkheidslabels maken die alleen gelden voor documenten en e-mailberichten en niet kunnen worden geselecteerd voor containers.  En zo kunt u ook vertrouwelijkheidslabels maken die alleen gelden voor containers en niet kunnen worden geselecteerd voor documenten en e-mailberichten. Nieuw en momenteel in preview: u kunt ook het bereik selecteren voor Azure Purview-assets:

![Bereikopties voor vertrouwelijkheidslabels](../media/sensitivity-labels-scopes.png)

Standaard is altijd het bereik **Bestanden en e-mailberichten** geselecteerd. De andere bereikwaarden worden standaard geselecteerd wanneer de functies voor uw tenant zijn ingeschakeld: 

- **Groepen en sites**: [vertrouwelijkheidslabels voor containers inschakelen en labels synchroniseren](sensitivity-labels-teams-groups-sites.md#how-to-enable-sensitivity-labels-for-containers-and-synchronize-labels)

- **Azure Purview-assets (preview)**: [automatisch uw inhoud labelen in Azure Purview](/azure/purview/create-sensitivity-label)

Wanneer u de standaardinstellingen wijzigt zodat net alle bereiken zijn geselecteerd, ziet u de eerste pagina van de configuratie-instellingen voor de bereiken die u niet hebt geselecteerd, maar kunt u de instellingen niet configureren. Wanneer het bereik voor bestanden en e-mailberichten bijvoorbeeld niet is geselecteerd, kunt u de opties op de volgende pagina niet selecteren:

![Niet-beschikbare opties voor vertrouwelijkheidslabels](../media/sensitivity-labels-unavailable-settings.png)

Selecteer **Volgende** voor de pagina's met niet-beschikbare opties om door te gaan. Of selecteer **Terug** om het bereik van het label te wijzigen.

### <a name="label-priority-order-matters"></a>Labelprioriteit (volgorde is van belang)

Wanneer u in uw beheercentrum vertrouwelijkheidslabels maakt, verschijnen ze in een lijst in het tabblad **Vertrouwelijkheid** op de pagina **Labels**. In deze lijst is de volgorde belangrijk, want dat geeft de prioriteit weer. U wilt dat het meest beperkende vertrouwelijkheidslabel, zoals Zeer vertrouwelijk **onderaan** de lijst staat en het minst beperkende vertrouwelijkheidslabel, zoals Openbaar **bovenaan**.

U kunt maar een vertrouwelijkheidslabel toepassen op een item als een document, e-mail of container. Als u een optie instelt waarvoor het vereist is dat uw gebruikers een reden hebben om het label te wijzigen naar een lagere classificatie, geeft de volgorde van deze lijst de lagere classificaties weer. Deze optie is echter niet van toepassing op sublabels.

De volgorde van sublabels wordt echter wel gebruikt met [automatisch labelen](apply-sensitivity-label-automatically.md). Wanneer u labels configureert om automatisch te worden toegepast of als aanbeveling, kunnen meerdere overeenkomsten mogelijk zijn voor meer dan één label. Om te bepalen welk label wordt toegepast of aanbevolen, wordt de volgorde van de labels gebruikt: het laatste vertrouwelijkheidslabel wordt geselecteerd en dan, indien van toepassing, het laatste sublabel.

![Optie om een sublabel te maken](../media/Sensitivity-label-sublabel-options.png)

### <a name="sublabels-grouping-labels"></a>Sublabels (groeperingslabels)

Met sublabels kunt u één of meerdere labels groeperen onder een bovenliggend label dat een gebruiker ziet in een Office-app. Onder Vertrouwelijk kan uw organisatie bijvoorbeeld verschillende andere labels gebruiken voor specifieke typen van die classificatie. In dit voorbeeld is het bovenliggende label Vertrouwelijk eenvoudig een tekstlabel, zonder beveiligingsinstellingen en omdat het sublabels heeft, kan het niet worden toegepast op inhoud. In plaats daarvan moeten gebruikers Vertrouwelijk kiezen om de sublabels te zien en kunnen ze een sublabel kiezen om toe te passen op inhoud.

Sublabels zijn gewoon een manier om labels te presenteren aan gebruikers in logische groepen. Sublabels nemen geen instellingen over van het bovenliggende label. Wanneer u een sublabel publiceert voor een gebruiker, kan die gebruiker dat sublabel dan toepassen op inhoud, maar niet alleen het bovenliggende label toepassen.

Kies geen bovenliggend label als standaardlabel en configureer geen bovenliggend label om automatisch te worden toegepast (of aanbevolen). Als u dat doet, wordt het bovenliggende label niet toegepast op inhoud.

Voorbeeld hoe sublabels worden weergegeven voor gebruikers:

![Gegroepeerde sublabels op het lint](../media/Sensitivity-label-grouped-labels2.png)

### <a name="editing-or-deleting-a-sensitivity-label"></a>Een vertrouwelijkheidslabel bewerken of verwijderen

Als u een vertrouwelijkheidslabel verwijdert uit uw beheercentrum, wordt het label niet automatisch verwijderd van inhoud en blijven alle beveiligingsinstellingen van kracht op inhoud waarop dat label was toegepast.

Wanneer u een vertrouwelijkheidslabel bewerkt, wordt de versie van het label dat is toegepast op inhoud, afgedwongen op die inhoud.

## <a name="what-label-policies-can-do"></a>Wat labelbeleid inhoudt

Nadat u uw vertrouwelijkheidslabels hebt gemaakt, moet u ze publiceren om ze beschikbaar te stellen aan personen en services in uw organisatie. De vertrouwelijkheidslabels kunnen dan worden toegepast op Office-documenten en e-mailberichten en andere items die vertrouwelijkheidslabels ondersteunen. 

In tegenstelling tot retentielabels, die worden gepubliceerd in locaties zoals alle Exchange-postvakken, worden vertrouwelijkheidslabels gepubliceerd naar gebruikers of groepen. Apps die vertrouwelijkheidslabels ondersteunen, kunnen die weergeven aan gebruikers als toegepaste labels of als labels die zij kunnen toepassen.

Wanneer u labelbeleid configureert, kunt u:

- **kiezen welke gebruikers en groepen de labels zien.** Labels kunnen worden gepubliceerd aan specifieke gebruikers of beveiligingsgroepen met e-mailberichten, distributiegroepen of Microsoft 365-groepen (die een[dynamisch lidmaatschap](/azure/active-directory/users-groups-roles/groups-create-rule) kunnen hebben) in Azure AD.

- **Een standaardlabel specificeren** voor nieuwe documenten, e-mails zonder label en nieuwe containers [(als u gevoeligheidslabels hebt ingeschakeld voor Microsoft Teams, Microsoft 365-groepen en SharePoint-sites](sensitivity-labels-teams-groups-sites.md)). U kunt hetzelfde label opgeven voor alle drie de typen items, of  verschillende labels. Wanneer u een standaardlabel voor documenten opgeeft, past de geïntegreerde labelclient van Azure Information Protection dit standaardlabel ook toe op bestaande documenten die niet zijn gelabeld. Gebruikers kunnen het standaardlabel altijd wijzigen als het niet het juiste label is voor hun document of e-mail.
    
    Overweeg om een standaardlabel te gebruiken om een basisniveau in te stellen van beveiligingsinstellingen dat u wilt toepassen op al uw inhoud. Zonder gebruikerstraining en ander beheer kan deze instelling echter ook resulteren in onjuiste labeling. Het is gewoonlijk geen goed idee om een label te kiezen dat versleuteling toepast als standaardlabel op documenten. Veel organisaties moeten bijvoorbeeld documenten verzenden naar en delen met externe gebruikers die mogelijk geen apps hebben die de versleuteling ondersteunen of ze gebruiken mogelijk een account die niet geautoriseerd kan worden. Zie [Versleutelde documenten delen met externe gebruikers](sensitivity-labels-office-apps.md#sharing-encrypted-documents-with-external-users) voor meer informatie over dit scenario.

- **argumenten eisen voor het wijzigen van een label.** Als een gebruiker probeert een label te verwijderen of te vervangen door een label met een lager volgnummer, kunt u eisen dat de gebruiker een reden geeft om deze actie uit te kunnen voeren. Een gebruiker opent bijvoorbeeld een document met het label Vertrouwelijk (volgnummer 3) en vervangt dat label met een Openbaar-label (volgnummer 1). Voor Office-apps wordt deze redenprompt eenmaal per app-sessie geactiveerd wanneer u ingebouwde labels gebruikt en per bestand wanneer u de Azure Information Protection Unified labeling-client gebruikt. Beheerders kunnen de reden samen met de labelwijziging lezen in [Activiteitenverkenner](data-classification-activity-explorer.md).

    ![Prompt wanneer gebruikers een reden invoeren](../media/Sensitivity-label-justification-required.png)

- **Vereisen dat gebruikers een label toepassen** voor documenten en e-mails, alleen documenten, voor containers en Power BI-inhoud. Deze opties, ook wel verplicht labelen genoemd, zorgen ervoor dat een label moet worden toegepast voordat gebruikers documenten kunnen opslaan en e-mailberichten kunnen verzenden, nieuwe groepen of sites kunnen maken en wanneer ze niet-gelabelde inhoud gebruiken voor Power BI.
    
    Aan documenten en e-mailberichten kan door een gebruiker handmatig een label worden toegewezen, automatisch als gevolg van een voorwaarde die u hebt geconfigureerd of standaard worden toegewezen (de hiervoor beschreven optie standaardlabel). Een voorbeeldprompt die in Outlook wordt weergegeven wanneer een gebruiker een label moet toewijzen:

    ![Prompt in Outlook waarin de gebruiker wordt gevraagd een verplicht label toe te passen](../media/sensitivity-labels-mandatory-prompt-aipv2-outlook.PNG)
    
    Zie [Vereisen dat gebruikers een label toepassen op hun e-mail en documenten](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents) voor meer informatie.
    
    Aan containers moet een label worden toegewezen op het moment dat de groep of site wordt gemaakt.
    
    Voor meer informatie over verplicht labelen voor Power BI, raadpleegt u [Beleid voor verplichte labels voor Power BI](/power-bi/admin/service-security-sensitivity-label-mandatory-label-policy).
    
    U kunt deze optie gebruiken om de dekking van uw labels te vergroten. Zonder gebruikerstraining kunnen deze instellingen echter leiden tot onnauwkeurige labels. Tenzij u ook een bijbehorend standaardlabel instelt, kan verplicht labelen met de geregelde prompts leiden tot frustratie bij uw gebruikers.

- **Biedt een help-koppeling naar een aangepaste help-pagina.** Als uw gebruikers niet zeker weten wat uw vertrouwelijkheidslabels betekenen of hoe ze moeten worden gebruikt, kunt u een Meer informatie-URL bieden die verschijnt onderaan het menu **Vertrouwelijkheidslabels** in de Office-apps:

    ![Meer informatie-koppeling op knop Vertrouwelijkheid in Lint](../media/Sensitivity-label-learn-more.png)

Nadat u labelbeleid hebt gemaakt dat nieuwe vertrouwelijkheidslabels toewijst aan gebruikers en groepen, beginnen gebruikers die labels te zien in hun Office-apps. Het duurt maximaal 24 uur totdat de laatste wijzigingen binnen uw organisatie zijn gerepliceerd.

Er is geen limiet voor het aantal vertrouwelijkheidslabels dat u kunt maken en publiceren, met één uitzondering: als het label versleuteling toepast die de gebruikers en machtigingen specificeert, wordt er een maximum van 500 labels ondersteund met deze configuratie. Probeer echter het aantal labels tot een minimum te beperken om de overhead voor beheerders en de complexiteit voor uw gebruikers te verminderen. De praktijk heeft uitgewezen dat de effectiviteit aanzienlijk afneemt als gebruikers meer dan vijf hoofdlabels of meer dan vijf sublabels per hoofdlabel hebben.

### <a name="label-policy-priority-order-matters"></a>Labelbeleidprioriteit (volgorde is van belang)

U stelt uw vertrouwelijkheidslabels beschikbaar aan gebruikers door ze te publiceren in een vertrouwelijkheidsbeleid dat wordt weergegeven in een lijst in het tabblad **Vertrouwelijkheidsbeleid** op de pagina **Labelbeleid**. Net als bij vertrouwelijkheidslabels (zie [Labelprioriteit (volgorde is van belang)](#label-priority-order-matters)) is de volgorde van vertrouwelijkheidsbeleid belangrijk, want dat bepaalt de prioriteit. Het labelbeleid met de laagste prioriteit wordt **bovenaan** weergegeven en het beleid met de hoogste prioriteit wordt **onderaan** weergegeven.

Labelbeleid bestaat uit:

- Een verzameling labels.
- De gebruikers en groepen waaraan het beleid met labels wordt toegewezen.
- Het bereik van het beleid en de beleidsinstellingen voor dat bereik (zoals standaardlabel voor bestanden en e-mailberichten).

U kunt een gebruiker opnemen in meerdere labelbeleidsregels en de gebruiker krijgt alle vertrouwelijkheidslabels en -instellingen van die beleidsregels. Als er een conflict is tussen de instellingen van meerdere beleidsregels, worden de instellingen van het beleid met de hoogste prioriteit (laagste positie) toegepast. Met andere woorden: de hoogste prioriteit wint voor elke instelling.

Als u niet de verwachte resultaten ziet voor de label- of labelbeleidsinstelling voor een gebruiker of groep, controleer dan de volgorde van het vertrouwelijkheidsbeleid. Mogelijk moet u het beleid omlaag verplaatsen. Als u de volgorde van het labelbeleid wilt wijzigen, selecteert u een beleidsregel > kies het beletselteken aan de rechterkant > kies dan **Omlaag** of **Omhoog**.

![Optie verplaatsen op de pagina voor vertrouwelijkheidsbeleid](../media/sensitivity-label-policy-priority.png)

> [!NOTE]
> Ter herinnering: Wanneer er een conflict met instellingen is voor een gebruiker aan wie meerdere beleidsregels zijn toegewezen, wordt de instelling van het beleid met de hoogste prioriteit (laagste positie) toegepast.

## <a name="sensitivity-labels-and-azure-information-protection"></a>Vertrouwelijkheidslabels en Azure Information Protection

Wanneer u vertrouwelijkheidslabels gebruikt in Microsoft 365-apps op Windows-computers kunt u ervoor kiezen labels te gebruiken die zijn ingebouwd in Office-apps of de Azure Information Protection-client.

Standaard is de ingebouwde labeling uitgeschakeld in deze apps wanneer de Azure Information Protection-client wordt geïnstalleerd. Zie [Ingebouwde Office-labelclient en de Azure Information Protection-client](sensitivity-labels-office-apps.md#office-built-in-labeling-client-and-the-azure-information-protection-client) voor meer informatie, waaronder het wijzigen van dit standaardgedrag.

Zelfs wanneer u de ingebouwde labeling in Office-apps gebruikt, kunt u ook de geïntegreerde Azure Information Protection-labelclient met vertrouwelijkheidslabels gebruiken voor het volgende:

- Een scanner om vertrouwelijke gegevens op te sporen die on-premises zijn opgeslagen en dan optioneel die inhoud labelen.

- Opties voor het klikken met de rechtermuisknop in Verkenner zodat gebruikers labels toe kunnen passen op alle bestandstypen

- Een viewer om versleutelde bestanden voor tekst, afbeeldingen of PDF-bestanden weer te geven

- Een PowerShell-module om vertrouwelijke gegevens op te sporen in on-premises bestanden en labels en versleuteling toe te passen op of te verwijderen van deze bestanden.

Zie [Kies uw Windows-labeloplossing](/azure/information-protection/rms-client/use-client#choose-your-windows-labeling-solution) in de Azure Information Protection-documentatie als u nog niet bekend bent met Azure Information Protection of als u een bestaande Azure Information Protection-klant bent die recentelijk labels heeft gemigreerd.

### <a name="azure-information-protection-labels"></a>Azure Information Protection-labels

> [!NOTE]
> Labelbeheer voor Azure Information Protection-labels in Azure Portal is **31 maart 2021** afgeschaft. Vind meer informatie in de officiële [afschaffingsmelding](https://techcommunity.microsoft.com/t5/azure-information-protection/announcing-timelines-for-sunsetting-label-management-in-the/ba-p/1226179).

Wanneer uw tenant zich nog niet op het [geïntegreerde labelplatform](/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform) bevindt, moet u eerst geïntegreerde labeling activeren voordat u vertrouwelijkheidslabels kunt gebruiken. Zie [Azure Information Protection-labels migreren naar geïntegreerde vertrouwelijkheidslabels](/azure/information-protection/configure-policy-migrate-labels) voor instructies. 

## <a name="sensitivity-labels-and-the-microsoft-information-protection-sdk"></a>Vertrouwelijkheidslabels en de Microsoft Information Protection SDK

Aangezien een vertrouwelijkheidslabel wordt opgeslagen in de metagegevens van een document kunnen apps en services van derden deze labelmetagegevens lezen en schrijven als aanvulling op uw labelimplementatie. Daarnaast kunnen softwareontwikkelaars de [Microsoft Information Protection SDK](/information-protection/develop/overview#microsoft-information-protection-sdk) gebruiken om ondersteuning te bieden voor label- en versleutelingsmogelijkheden op meerdere platforms. Zie [Melding algemene beschikbaarheid in het Tech Community-blog](https://techcommunity.microsoft.com/t5/Microsoft-Information-Protection/Microsoft-Information-Protection-SDK-Now-Generally-Available/ba-p/263144) voor meer informatie. 

U vindt hier ook meer informatie over [partneroplossingen die zijn geïntegreerd met Microsoft Information Protection](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Microsoft-Information-Protection-showcases-integrated-partner/ba-p/262657).

## <a name="deployment-guidance"></a>Implementatiebegeleiding

Zie [Aan de slag met vertrouwelijkheidslabels](get-started-with-sensitivity-labels.md) voor planning en begeleiding van implementaties met onder meer licentiegegevens, machtigingen, implementatiestrategie, een lijst met ondersteunde scenario's en documentatie voor eindgebruikers.

Zie [Informatiebescherming implementeren voor gegevensprivacyvoorschriften met Microsoft 365](../solutions/information-protection-deploy.md)  (aka.ms/m365dataprivacy) voor informatie over hoe u vertrouwelijkheidslabels kunt gebruiken om aan de privacyvoorschriften voor gegevens te voldoen.