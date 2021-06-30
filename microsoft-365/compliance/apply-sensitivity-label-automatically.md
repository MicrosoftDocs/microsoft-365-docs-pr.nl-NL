---
title: Een vertrouwelijkheidslabel automatisch op inhoud in Microsoft 365 toepassen
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
description: Wanneer u een vertrouwelijkheidslabel maakt, kunt u automatisch een label toewijzen aan bestanden en e-mailberichten of gebruikers vragen om het label te selecteren dat u aanbeveelt.
ms.openlocfilehash: 6b74c36707b9fe1fdbe00eb7058554b54ec95755
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194767"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a>Een vertrouwelijkheidslabel automatisch toepassen op inhoud

>*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!NOTE]
> Zie [Uw inhoud automatisch labelen in Azure Purview](/azure/purview/create-sensitivity-label) voor informatie over het automatisch toepassen van een vertrouwelijkheidslabel in Azure Purview (preview).

Wanneer u een vertrouwelijkheidslabel maakt, kunt u dat label automatisch toewijzen aan bestanden en e-mailberichten wanneer het overeenkomt met de voorwaarden die u opgeeft.

Deze mogelijkheid om automatisch vertrouwelijkheidslabels toe te passen op inhoud is belangrijk vanwege de volgende redenen:

- Het is niet nodig om uw gebruikers te trainen wanneer ze een van uw classificaties moeten gebruiken.

- U hoeft niet te vertrouwen op gebruikers om alle inhoud op de juiste manier te classificeren.

- Gebruikers hoeven niet meer op de hoogte te zijn van uw beleid, maar kunnen zich op hun werk richten.

Wanneer inhoud handmatig is gelabeld, wordt dat label nooit vervangen door automatisch labelen. Automatisch labelen kan echter wel een [label met een lagere prioriteit](sensitivity-labels.md#label-priority-order-matters) vervangen dat automatisch is toegepast.

Er zijn twee verschillende methoden voor het automatisch toepassen van een vertrouwelijkheidslabel op inhoud in Microsoft 365:

- **Labelen aan de clientzijde wanneer gebruikers documenten bewerken of e-mailberichten opstellen (of beantwoorden of doorsturen)**: gebruik een label dat is geconfigureerd voor het automatisch labelen van bestanden en e-mailberichten (inclusief Word, Excel, PowerPoint en Outlook). 
    
    Deze methode ondersteunt het aanbevelen van een label aan gebruikers en het automatisch toepassen van een label. Maar in beide gevallen besluit de gebruiker of het label wordt geaccepteerd of geweigerd, om ervoor te zorgen dat inhoud beter wordt gelabeld. Dit labelen aan clientzijde heeft een minimale vertraging voor documenten tot gevolg, omdat het label kan worden aangebracht voordat het document wordt opgeslagen. Niet alle client-apps ondersteunen echter automatisch labelen. Deze functionaliteit wordt ondersteund door de geïntegreerde Azure Information Protection-labelclient en [sommige versies van Office-apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps). 
    
    Zie [Configuratie van automatische labels voor Office-apps](#how-to-configure-auto-labeling-for-office-apps) op deze pagina voor configuratie-instructies.

- **Labelen aan servicezijde wanneer inhoud al is opgeslagen (in SharePoint of OneDrive) of per e-mail is verzonden (verwerkt door Exchange Online)**: gebruik een beleid voor automatisch labelen. 
    
    Soms wordt deze methode ook wel automatisch labelen voor data-at-rest genoemd (documenten in SharePoint en OneDrive) of data-in-transit (e-mail die wordt verzonden of ontvangen door Exchange). Voor Exchange bevat dit niet e-mail-at-rest (postvakken).
    
    Het labelen wordt door de service zelf toegepast en niet door de toepassingen. U hoeft zich dus geen zorgen te maken over welke apps en welke versie gebruikers hebben. Hierdoor is deze functionaliteit direct beschikbaar binnen uw gehele organisatie en geschikt om op schaal te labelen. Beleid voor automatisch labelen ondersteunt geen aanbevolen labels, omdat de gebruiker geen interactie heeft met het labelproces. In plaats daarvan voert de beheerder het beleid in de simulatiemodus uit, om ervoor te zorgen dat de inhoud juist wordt gelabeld voordat het label werkelijk wordt toegepast.
    
    Zie [Beleidsregels configureren voor automatisch labelen voor SharePoint, OneDrive en Exchange](#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) op deze pagina voor configuratie-instructies.
    
    Specifiek voor automatisch labelen voor SharePoint en OneDrive:
    - Office-bestanden voor Word, PowerPoint en Excel worden ondersteund. Open XML-indeling wordt ondersteund (zoals .docx en .xlsx), maar niet de Microsoft Office 97-2003-indeling (zoals .doc en .xls).
        - Deze bestanden kunnen automatisch at rest worden gelabeld voor of nadat de beleidsregels voor automatisch labelen worden gemaakt. Bestanden kunnen niet automatisch worden gelabeld als ze deel uitmaken van een geopende sessie (het bestand is geopend).
        - Momenteel worden bijlagen bij lijstitems niet ondersteund en niet automatisch gelabeld.
    - Maximaal 25.000 automatisch gelabelde bestanden in uw tenant per dag.
    - Maximaal tien beleidsregels voor automatisch labelen per tenant, elk voorzien voor maximaal tien sites (SharePoint of OneDrive).
    - Bestaande waarden voor gewijzigd, gewijzigd door en de datum worden niet gewijzigd als gevolg van beleidsregels voor automatisch labelen, voor de simulatiemodus en wanneer labels worden toegepast.
    - Wanneer het label versleuteling toepast, is [Rights Management-uitgever en -eigenaar](/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner) het account waaronder het bestand het laatst is gewijzigd.

    Specifiek voor automatisch labelen voor Exchange:
    - In tegenstelling tot handmatig labelen of automatisch labelen met Office-apps, worden zowel PDF-bijlagen als Office-bijlagen (Word-, Excel- en PowerPoint-bestanden) ook gescand op de voorwaarden die u opgeeft in uw beleid voor automatisch labelen. Als er een overeenkomst is, wordt de e-mail gelabeld, maar niet de bijlage.
        - Als voor PDF-bestanden versleuteling wordt toegepast op het label, worden deze bestanden versleuteld wanneer uw tenant is [ingeschakeld voor PDF-bijlagen](ome-faq.yml#are-pdf-file-attachments-supported-).
        - Voor deze Office-bestanden wordt de Open XML-indeling ondersteund (zoals .docx en .xlsx), maar niet de Microsoft Office 97-2003-indeling (zoals .doc en .xls). Als het label versleuteling toepast, worden deze bestanden versleuteld.
    - Als u beschikt over regels voor de Exchange-e-mailstroom of beleidsregels voor preventie van gegevensverlies (DLP) waarmee IRM-versleuteling wordt toegepast: wanneer inhoud door deze regels of beleidsregels en een beleid voor automatisch labelen wordt geïdentificeerd, wordt het label toegepast. Als dit label versleuteling toepast, worden de IRM-instellingen van de regels voor de Exchange-e-mailstroom of de DLP-beleidsregels genegeerd. Als dit label echter geen versleuteling toepast, worden de IRM-instellingen van de regels voor de e-mailstroom of de DLP-beleidsregels ook toegepast.
    - E-mail met IRM-versleuteling zonder label wordt vervangen door een label met versleutelingsinstellingen wanneer er een overeenkomst is door gebruik te maken van automatisch labelen.
    - Binnenkomende e-mail wordt gelabeld wanneer er een overeenkomst is met de voorwaarden voor automatisch labelen:
        - Als het label is geconfigureerd voor [versleuteling](encryption-sensitivity-labels.md), wordt deze versleuteling niet toegepast.
        - Als het label is geconfigureerd voor het toepassen van [dynamische markeringen](sensitivity-labels-office-apps.md#dynamic-markings-with-variables), moet u er rekening mee houden dat dit namen van personen van buiten uw organisatie kan opleveren.
    - Wanneer het label versleuteling toepast, is de [Rights Management-uitgever en -eigenaar](/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner) de persoon die het e-mailbericht verzendt. Er is momenteel geen manier om een Rights Manager-eigenaar in te stellen voor alle binnenkomende e-mailberichten die automatisch worden versleuteld.
    

## <a name="compare-auto-labeling-for-office-apps-with-auto-labeling-policies"></a>Automatisch labelen voor Office-apps vergelijken met beleidsregels voor automatisch labelen

Gebruik de volgende tabel om de verschillen in gedrag te herkennen voor de twee aanvullende methoden voor automatisch labelen:

|Functie of gedrag|Labelinstelling: automatisch labelen voor bestanden en e-mailberichten  |Beleid: automatisch labelen|
|:-----|:-----|:-----|
|App-afhankelijkheid|[Ja](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps) |Nee \* |
|Beperken per locatie|Nee |Ja |
|Voorwaarden: trainbare classificaties|Ja |Nee |
|Voorwaarden: opties voor delen en extra opties voor e-mail|Nee |Ja |
|Voorwaarden: uitzonderingen|Nee |Ja (alleen e-mail) |
|Aanbevelingen, beleidsinfo en overschrijvingen door gebruikers|Ja |Nee |
|Simulatiemodus|Nee |Ja |
|Exchange-bijlagen gecontroleerd op voorwaarden|Nee | Ja|
|Visuele markeringen toepassen |Ja |Ja (alleen e-mail) |
|Toepassen van IRM-versleuteling zonder label overschrijven|Ja, als de gebruiker het minimale gebruiksrecht voor exporteren heeft |Ja (alleen e-mail) |
|Labelen van binnenkomende e-mail|Nee |Ja|

\* Automatisch labelen is momenteel niet in alle regio's beschikbaar. Als uw tenant deze functionaliteit niet ondersteunt, is het tabblad Automatisch labelen niet zichtbaar in het labelcentrum voor beheerders.

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a>Hoe meerdere voorwaarden worden geëvalueerd wanneer ze van toepassing zijn op meer dan één label

De labels worden voor evaluatie gerangschikt op basis van hun positie die u in het beleid opgeeft: het label dat het eerst wordt geplaatst, heeft de laagste prioriteit (minst gevoelig) en het label dat het laatst wordt geplaatst, heeft de hoogste prioriteit (meest gevoelig). Zie [Labelprioriteit (volgorde is van belang)](sensitivity-labels.md#label-priority-order-matters) voor meer informatie over prioriteit.

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a>Configureer geen bovenliggend label dat automatisch moet worden toegepast of dat wordt aanbevolen om te worden toegepast

Vergeet niet dat u geen bovenliggend label (een label met sublabels) op inhoud kunt toepassen. Zorg ervoor dat u geen bovenliggend label zodanig configureert dat het automatisch moet worden toegepast of aanbevolen in Office-apps, en selecteer geen bovenliggend label voor een beleid voor automatisch labelen. Als u dit wel doet, wordt het bovenliggende label niet op inhoud toegepast.

Als u automatisch labelen met sublabels wilt gebruiken, moet u zowel het bovenliggende label als het sublabel publiceren.

Zie [Sublabels (groeperingslabels)](sensitivity-labels.md#sublabels-grouping-labels) voor meer informatie over bovenliggende labels en sublabels.

## <a name="how-to-configure-auto-labeling-for-office-apps"></a>Automatisch labelen configureren voor Office-apps

Automatisch labelen in Office-apps voor Windows wordt ondersteund door de geïntegreerde Azure Information Protection-labelclient. Voor ingebouwd labelen in Office-apps is deze functionaliteit beschikbaar in [verschillende fasen van beschikbaarheid voor verschillende apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).

De instellingen voor automatisch labelen voor Office-apps zijn beschikbaar wanneer u [een vertrouwelijkheidslabel wilt maken of bewerken](create-sensitivity-labels.md). Zorg ervoor dat **Bestanden en e-mailberichten** is geselecteerd voor het bereik van het label: 

![Opties voor het bereik van vertrouwelijkheidslabels voor bestanden en e-mailberichten](../media/filesandemails-scope-options-sensitivity-label.png)

Terwijl u de wizard doorloopt, ziet u de pagina **Automatisch labelen voor bestanden en e-mailberichten**. Hier kunt u kiezen uit een lijst met typen gevoelige informatie of trainbare classificaties:

![Labelvoorwaarden voor automatisch labelen in Office-apps](../media/sensitivity-labels-conditions.png)

Wanneer dit vertrouwelijkheidslabel automatisch wordt toegepast, ziet de gebruiker een melding in de Office-app. Bijvoorbeeld:

![Melding dat er automatisch een label op een document is toegepast](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

### <a name="configuring-sensitive-info-types-for-a-label"></a>Het configureren van typen gevoelige informatie voor een label

Wanneer u de optie **Typen gevoelige informatie** selecteert, ziet u dezelfde lijst met typen gevoelige informatie als wanneer u een beleid voor preventie van gegevensverlies (DLP) maakt. Zo kunt u bijvoorbeeld automatisch het label Zeer vertrouwelijk toepassen op inhoud die persoonlijke gegevens van klanten bevat, zoals creditcard-, bsn- of paspoortnummers:

![Typen gevoelige informatie voor automatisch labelen in Office-apps](../media/sensitivity-labels-sensitive-info-types.png)

Net zoals wanneer u DLP-beleid configureert, kunt u vervolgens de voorwaarde verfijnen door het aantal exemplaren en de nauwkeurigheid van de overeenstemming te wijzigen. Bijvoorbeeld:

![Opties voor de nauwkeurigheid van de overeenstemming en het aantal exemplaren](../media/sit-confidence-level.png)

U vindt meer informatie over deze configuratieopties in de DLP-documentatie: [Regels afstemmen om ze eenvoudiger of moeilijker overeen te laten komen](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).

Net als bij de configuratie van DLP-beleid kunt u ook kiezen of alle typen gevoelige informatie moeten worden gedetecteerd door een voorwaarde of slechts één van deze typen. En als u uw voorwaarden flexibeler of complexer wilt maken, kunt u [groepen toevoegen en logische operatoren tussen de groepen gebruiken](data-loss-prevention-policies.md#grouping-and-logical-operators).

> [!NOTE]
> Beleid voor automatisch labelen op basis van aangepaste typen gevoelige informatie is alleen van toepassing op nieuw gemaakte of gewijzigde inhoud in OneDrive en SharePoint; niet op bestaande inhoud. 

### <a name="configuring-trainable-classifiers-for-a-label"></a>Trainbare classificaties voor een label configureren

Deze optie is momenteel in preview. Als u deze optie gebruikt, moet u in uw tenant ten minste één ander vertrouwelijkheidslabel hebben gepubliceerd dat is geconfigureerd voor automatisch labelen en de optie [Typen gevoelige informatie](#configuring-sensitive-info-types-for-a-label).

Wanneer u de optie **Trainbare classificaties** selecteert, selecteert u een of meer ingebouwde, trainbare classificaties van Microsoft. Als u uw eigen aangepaste, trainbare classificaties hebt gemaakt, kunt u deze ook selecteren:

![Opties voor trainbare classificaties en vertrouwelijkheidslabels](../media/sensitivity-labels-classifers.png)

> [!CAUTION]
> De ingebouwde classificatie **Grof taalgebruik** wordt afgeschaft omdat er veel fout-positieven worden geproduceerd. Gebruik deze ingebouwde classificatie niet en mocht u deze momenteel gebruiken, moet u deze niet voor uw bedrijfsprocessen gebruiken. U wordt aangeraden in plaats daarvan de ingebouwde classificaties **Gerichte intimidatie**, **Scheldwoorden** en **Bedreiging** te gebruiken.

Zie [Informatie over trainbare classificaties](classifier-learn-about.md) voor meer informatie over deze classificaties.

Tijdens de previewperiode van deze optie worden trainbare classificatiess voor vertrouwelijkheidslabels ondersteund door de volgende apps:

- Microsoft 365-apps voor ondernemingen ([voorheen Office 365 ProPlus](/deployoffice/name-change)) voor Windows, nu geïmplementeerd voor het [Huidig kanaal](/deployoffice/overview-update-channels#current-channel-overview) in versie 2006 en hoger:
    - Word
    - Excel
    - PowerPoint

- Webversie van Office-apps, als u de [vertrouwelijkheidslabels voor Office-bestanden in SharePoint en OneDrive hebt ingeschakeld](sensitivity-labels-sharepoint-onedrive-files.md):
    - Word
    - Excel
    - PowerPoint
    - Outlook

### <a name="recommend-that-the-user-applies-a-sensitivity-label"></a>Aanbevelen dat de gebruiker een vertrouwelijkheidslabel toepast

Als u wilt, kunt u uw gebruikers aanraden het label toe te passen. Met deze optie kunnen uw gebruikers de classificatie en eventuele bijbehorende beveiliging accepteren of de aanbeveling negeren als het label niet geschikt is voor hun inhoud.

![Optie voor het aanbevelen van een vertrouwelijkheidslabel aan gebruikers](../media/Sensitivity-labels-Recommended-label-option.png)

Hier ziet u een voorbeeld van een prompt van de geïntegreerde Azure Information Protection-labelclient wanneer u een voorwaarde configureert om een label toe te passen als een aanbevolen actie, met een aangepaste beleidstip. U kunt kiezen wat voor tekst wordt weergegeven in de beleidstip.

![Aanwijzing om een aanbevolen label toe te passen](../media/Sensitivity-label-Prompt-for-required-label.png)

### <a name="when-automatic-or-recommended-labels-are-applied"></a>Wanneer automatische of aanbevolen labels worden toegepast

De implementatie van automatisch en aanbevolen labelen in Office-apps is afhankelijk van of u gebruikmaakt van labeling die in Office is ingebouwd of van de geïntegreerde Azure Information Protection-labelclient. Echter, in beide gevallen:

- U kunt automatisch labelen niet gebruiken voor documenten en e-mailberichten die eerder handmatig zijn gelabeld of die eerder automatisch met een hogere vertrouwelijkheid zijn gelabeld. Vergeet niet dat u slechts één vertrouwelijkheidslabel kunt toepassen op een document of e-mailbericht (naast één retentielabel).

- U kunt aanbevolen labelen niet gebruiken voor documenten of e-mailberichten die eerder met een hogere vertrouwelijkheid zijn gelabeld. Wanneer de inhoud al met een hogere vertrouwelijkheid is gelabeld, ziet de gebruiker de aanwijzing met de aanbeveling en beleidstip niet.

Specifiek voor ingebouwd labelen:

- Niet alle Office-apps ondersteunen automatisch (en aanbevolen) labelen. Zie [Ondersteuning voor functies van vertrouwelijkheidslabels in apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps) voor meer informatie.

- Voor aanbevolen labels in de desktopversies van Word wordt de vertrouwelijke inhoud die de aanbeveling heeft geactiveerd, gemarkeerd, zodat gebruikers de gevoelige inhoud kunnen beoordelen en verwijderen in plaats van het aanbevolen vertrouwelijkheidslabel toe te passen.

- Zie [Automatisch vertrouwelijkheidslabels toepassen op of aanbevelen voor uw bestanden en e-mailberichten in Office](https://support.office.com/nl-NL/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1) voor meer informatie over hoe deze labels worden toegepast in Office-apps, voorbeelden van schermafbeeldingen en hoe vertrouwelijke informatie wordt gedetecteerd.

Specifiek voor de geïntegreerde Azure Information Protection-labelclient:

-  Automatisch en aanbevolen labelen zijn van toepassing op Word, Excel en PowerPoint wanneer u een document opslaat, en op Outlook wanneer u een e-mailbericht verzendt.

- Outlook ondersteunt aanbevolen labelen als u eerst een [geavanceerde beleidsinstelling](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook) configureert.

- Er kan vertrouwelijke informatie worden gedetecteerd in de hoofdtekst van documenten en e-mailberichten, en in kop- en voetteksten, maar niet in de onderwerpregel of de bijlagen van e-mailberichten.

## <a name="how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange"></a>Beleid configureren voor automatisch labelen voor SharePoint, OneDrive en Exchange.

Zorg ervoor dat u op de hoogte bent van de vereisten voordat u beleid voor automatisch labelen configureert. 

### <a name="prerequisites-for-auto-labeling-policies"></a>Vereisten voor beleid voor automatisch labelen

- Simulatiemodus:
    - Controle voor Microsoft 365 moet zijn ingeschakeld. Zie [Zoeken in auditlogboek in- of uitschakelen](turn-audit-log-search-on-or-off.md) als u controle wilt in- of uitschakelen of niet zeker weet of de controle al is ingeschakeld.
    - Als u inhoud in bestanden of e-mailberichten wilt weergeven in de bronweergave, moet u de rol **Inhoudsviewer van Inhoudsverkenner** hebben. Globale beheerders hebben deze rol niet standaard. Als u deze machtiging niet hebt, wordt het voorbeeldvenster niet weergegeven wanneer u een item selecteert op het tabblad **Overeenkomende items**.

- Bestanden automatisch labelen in SharePoint en OneDrive:
    - U hebt [vertrouwelijkheidslabels ingeschakeld voor Office-bestanden in SharePoint en OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).
    - Op het moment dat het beleid voor automatisch labelen wordt uitgevoerd, mag het bestand niet zijn geopend door een ander proces of een andere gebruiker. Een bestand dat is uitgecheckt voor bewerking, valt in deze categorie.

- Als u van plan bent om [aangepaste typen gevoelige informatie](sensitive-information-type-learn-about.md) te gebruiken in plaats van de ingebouwde vertrouwelijkheidstypen: 
    - Aangepaste typen vertrouwelijkheidsinformatie zijn alleen van toepassing op inhoud die wordt toegevoegd of gewijzigd in SharePoint of OneDrive nadat de aangepaste typen vertrouwelijkheidsinformatie zijn opgelegd.
    - Als u nieuwe aangepaste typen gevoelige informatie wilt testen, maakt u deze voordat u het beleid voor automatisch labelen maakt. Vervolgens maakt u nieuwe documenten met voorbeeldgegevens om te testen.

- Er zijn een of meer vertrouwelijkheidslabels[gemaakt en gepubliceerd](create-sensitivity-labels.md) (voor ten minste één gebruiker) die u kunt selecteren voor uw beleid voor automatisch labelen. Voor deze labels geldt:
    - Het maakt niet uit of de labelinstelling voor automatisch labelen in Office-apps is in- of uitgeschakeld, omdat deze labelinstelling een aanvulling vormt op het beleid voor automatisch labelen, zoals in de inleiding wordt uitgelegd.
    - Als de labels die u voor automatisch labelen wilt gebruiken, zijn geconfigureerd voor het gebruik van visuele markeringen (kopteksten, voetteksten en watermerken), worden deze niet op documenten toegepast.
    - Als op de labels [versleuteling](encryption-sensitivity-labels.md) wordt toegepast:
        - Wanneer het beleid voor automatisch labelen locaties bevat voor SharePoint of OneDrive, moet het label zijn geconfigureerd voor de instelling **Nu machtigingen toewijzen**.
        - Wanneer het beleid voor automatisch labelen alleen voor Exchange geldt, kan het label worden geconfigureerd voor **Nu machtigingen toewijzen** of **Gebruikers machtigingen laten toewijzen** (voor de opties Niet doorsturen of Alleen versleutelen).

### <a name="learn-about-simulation-mode"></a>Meer informatie over de simulatiemodus

De simulatiemodus is uniek voor het beleid voor automatisch labelen en is in de werkstroom geïntegreerd. U kunt documenten en e-mailberichten pas automatisch labelen als uw beleid ten minste één simulatie heeft uitgevoerd.

Werkstroom voor beleid voor automatisch labelen:

1. Beleid voor automatisch labelen maken en configureren.

2. Voer het beleid uit in de simulatiemodus. Dit kan 48 uur duren.

3. Bekijk de resultaten en verfijn zo nodig uw beleid. Voer de simulatiemodus opnieuw uit en wacht totdat deze is voltooid.

4. Herhaal zo nodig stap 3.

5. Implementeer in productie.

De gesimuleerde implementatie wordt uitgevoerd zoals de WhatIf-parameter voor PowerShell. Resultaten worden gerapporteerd alsof het geselecteerde label is toegepast door het beleid voor automatisch labelen met behulp van de door u gedefinieerde regels. Vervolgens kunt u de regels zo nodig verfijnen qua nauwkeurigheid en de simulatie opnieuw uitvoeren. Echter, omdat automatisch labelen voor Exchange van toepassing is op e-mailberichten die worden verzonden en ontvangen, en niet op e-mailberichten die in postvakken zijn opgeslagen, kunt u niet verwachten dat resultaten voor e-mail in een simulatie consistent zijn, tenzij u exact dezelfde e-mailberichten kunt verzenden en ontvangen.

Met de simulatiemodus kunt u ook het bereik van uw beleid voor automatisch labelen geleidelijk verhogen voordat implementatie plaatsvindt. U kunt bijvoorbeeld beginnen met één locatie, zoals een SharePoint-site, met één documentbibliotheek. Met iteratieve wijzigingen kunt u vervolgens het bereik uitbreiden tot meerdere sites en vervolgens naar een andere locatie, zoals OneDrive.

Ten slotte kunt u de simulatiemodus gebruiken om bij benadering de tijdsduur voor het uitvoeren van uw beleid voor automatisch labelen op te geven, zodat u kunt plannen wanneer het zonder simulatiemodus moet worden uitgevoerd.

### <a name="creating-an-auto-labeling-policy"></a>Beleid voor automatisch labelen maken

1. Ga in het [Microsoft 365-compliancecentrum](https://compliance.microsoft.com/) naar vertrouwelijkheidslabels:
    
    - **Oplossingen** > **Informatiebescherming**
    
    Als u deze optie niet meteen ziet, selecteert u eerst **Alles weergeven**.

2. Selecteer het tabblad **Automatisch labelen**:
    
    ![Tabblad Automatisch labelen](../media/auto-labeling-tab.png)
    
    > [!NOTE]
    > Als u het tabblad **Automatisch labelen** niet ziet, is deze functionaliteit momenteel niet beschikbaar in uw regio.

3. Selecteer **+ Beleid voor automatisch labelen maken**. Hiermee wordt de wizard Nieuw beleid gestart:
    
    ![Wizard Nieuw beleid voor automatisch labelen ](../media/auto-labeling-wizard.png)

4. Voor de pagina **Informatie kiezen waarop u dit label wilt toepassen**: selecteer een van de sjablonen, bijvoorbeeld **Financieel** of **Privacy**. U kunt uw zoekopdracht verfijnen met behulp van het vervolgkeuzemenu **Opties weergeven voor**. Of selecteer **Aangepast beleid** als de sjablonen niet aan uw vereisten voldoen. Selecteer **Volgende**.

5. Voor de pagina **Uw beleid voor automatisch labelen een naam geven**: geef een unieke naam op en eventueel een beschrijving om het automatisch toegepaste label te herkennen. Geef ook locaties en voorwaarden op waarmee de te labelen inhoud kan worden herkend.

6. Voor de pagina **Locaties kiezen waarop u het label wilt toepassen**: selecteer locaties voor Exchange, SharePoint-sites en OneDrive en geef deze op. Selecteer **Volgende**.
    
    ![Pagina Locaties kiezen voor de wizard voor automatisch labelen ](../media/locations-auto-labeling-wizard.png)
    
    U moet afzonderlijke SharePoint-sites en OneDrive-accounts opgeven. Voor OneDrive heeft de URL van het OneDrive-account van een gebruiker de volgende indeling: `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`
    
    Bijvoorbeeld voor een gebruiker in de contoso-tenant met de gebruikersnaam rismone: `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`
    
    Zie [Een lijst met alle OneDrive-URL's van gebruikers in uw organisatie ophalen](/onedrive/list-onedrive-urls) om de syntaxis voor uw tenant te verifiëren en URL's voor gebruikers te identificeren.

7. Voor de pagina **Algemene of geavanceerde regels instellen** : behoud de standaardinstelling **Algemene regels** voor het definiëren van regels die inhoud herkennen die in alle geselecteerde locaties moet worden gelabeld. Als u verschillende regels per locatie nodig hebt, selecteert u **Geavanceerde regels**. Selecteer **Volgende**.
    
    De regels maken gebruik van voorwaarden die typen gevoelige informatie en opties voor delen omvatten:
    - Voor typen gevoelige informatie kunt u zowel ingebouwde als aangepaste typen gevoelige informatie selecteren.
    - Voor de opties voor delen kunt u kiezen voor **alleen met personen binnen mijn organisatie** of **met personen buiten mijn organisatie**.
    
    Als uw enige locatie **Exchange** of als u **Geavanceerde regels** selecteert, zijn er aanvullende voorwaarden die u kunt selecteren:
    - IP-adres van afzender is
    - Domein van ontvanger is
    - Ontvanger is
    - Bestandsextensie van bijlage is
    - Bijlage is met wachtwoord beveiligd
    - Inhoud van een e-mailbijlage kan niet worden gescand
    - Scannen van inhoud van een e-mailbijlage is niet voltooid
    - Koptekst komt overeen met patronen
    - Onderwerp komt overeen met patronen
    - Adres van ontvanger bevat woorden
    - Adres van ontvanger komt overeen met patronen
    - Adres van afzender komt overeen met patronen
    - Domein van afzender is
    - De ontvanger is lid van
    - Afzender is
    
    Voor elk van deze voorwaarden kunt u vervolgens uitzonderingen opgeven.
    
8. Afhankelijk van uw vorige keuzes hebt u nu de mogelijkheid nieuwe regels te maken aan de hand van voorwaarden en uitzonderingen.
    
    De configuratieopties voor typen gevoelige informatie zijn dezelfde als de opties die u selecteert voor automatisch labelen voor Office-apps. Zie [Typen gevoelige informatie voor een label configureren](#configuring-sensitive-info-types-for-a-label) voor meer informatie.
    
    Wanneer u alle regels hebt gedefinieerd die u nodig hebt en de status hebt bevestigd, selecteert u **Volgende** om een volgend label te kiezen dat u automatisch wilt toepassen.

11. Voor de pagina **Een label kiezen om automatisch toe te passen**: selecteer **+ Label kiezen**, selecteer een label in het deelvenster **Vertrouwelijkheidslabel kiezen** en selecteer vervolgens **Volgende**.

12. Voor de pagina **Bepalen of u het beleid nu of later wilt testen**: selecteer **Beleid uitvoeren in simulatiemodus** als u het beleid voor automatisch labelen nu in de simulatiemodus wilt uitvoeren. Of anders selecteert u **Beleid uitgeschakeld laten**. Selecteer **Volgende**: 
    
    ![De wizard voor het beleid voor automatisch labelen testen](../media/simulation-mode-auto-labeling-wizard.png)

13. Voor de pagina **Overzicht**: controleer de configuratie van uw beleid voor automatisch labelen, breng eventueel wijzigingen aan en voltooi de wizard.

Op de pagina **Informatiebescherming** > **Automatisch labelen** ziet u het beleid voor automatisch labelen in de sectie **Simulatie** of **Uit**, afhankelijk van uw keuze het beleid al dan niet uit te voeren in de simulatiemodus. Selecteer uw beleid om de details van de configuratie en status te bekijken (bijvoorbeeld **Simulatie van beleid is nog steeds actief**). Voor beleidsregels in de simulatiemodus selecteert u het tabblad **Overeenkomende items** om te zien welke e-mailberichten of documenten overeenkomen met de regels die u hebt opgegeven.

U kunt uw beleid rechtstreeks wijzigen vanuit deze interface:

- Voor een beleidsregel in de sectie **Uit** selecteert u knop **Beleidsregel bewerken**.

- Voor een beleidsregel in de sectie **Simulatie** selecteert u boven aan de pagina, op een van beide tabbladen, de optie **Beleidsregel bewerken**:
    
    ![Optie voor beleid voor automatisch labelen bewerken](../media/auto-labeling-edit.png)
    
    Wanneer u klaar bent om het beleid zonder simulatie uit te voeren, selecteert u de optie **Beleid inschakelen**.

Uw beleidsregels voor automatisch labelen worden continu uitgevoerd totdat ze worden verwijderd. Zo worden nieuwe en gewijzigde documenten opgenomen in de huidige beleidsinstellingen.

U kunt ook de resultaten van uw beleid voor automatisch labelen bekijken met behulp van [Inhoudsverkenner](data-classification-content-explorer.md) wanneer u over de juiste [machtigingen](data-classification-content-explorer.md#permissions) beschikt:
- Met **Lijstviewer van Inhoudsverkenner** kunt u het label van een bestand zien, maar niet de inhoud van het bestand.
- Met **Inhoudsviewer van Inhoudsverkenner** kunt u de inhoud van het bestand zien.

> [!TIP]
> U kunt Inhoudsverkenner ook gebruiken om locaties te identificeren met documenten met vertrouwelijke informatie, maar die geen label hebben. Met deze informatie kunt u overwegen deze locaties toe te voegen aan uw beleid voor automatisch labelen en de geïdentificeerde typen gevoelige informatie als regels op te nemen.

### <a name="use-powershell-for-auto-labeling-policies"></a>PowerShell gebruiken voor beleid voor automatisch labelen

U kunt [Beveiligings- en compliancecentrum PowerShell](/powershell/exchange/scc-powershell) gebruiken om beleid voor automatisch labelen te maken en configureren. Dit betekent dat u het maken en onderhouden van uw beleid voor automatisch labelen volledig met behulp van scripts kunt uitvoeren. Het biedt ook een efficiëntere methode voor het opgeven van meerdere URL's voor OneDrive- en SharePoint-locaties.

Voordat u de opdrachten in PowerShell kunt uitvoeren, moet u eerst [verbinding maken met het Beveiligings- en compliancecentrum PowerShell](/powershell/exchange/connect-to-scc-powershell).

Nieuw beleid voor automatisch labelen maken: 

```powershell
New-AutoSensitivityLabelPolicy -Name <AutoLabelingPolicyName> -SharePointLocation "<SharePointSiteLocation>" -ApplySensitivityLabel <Label> -Mode TestWithoutNotifications
```
Met deze opdracht maakt u een beleid voor automatisch labelen voor een SharePoint-site die u opgeeft. Voor een OneDrive-locatie gebruikt u echter de parameter *OneDriveLocation*. 

Extra sites toevoegen aan bestaand beleid voor automatisch labelen:

```powershell
$spoLocations = @("<SharePointSiteLocation1>","<SharePointSiteLocation2>")
Set-AutoSensitivityLabelPolicy -Identity <AutoLabelingPolicyName> -AddSharePointLocation $spoLocations -ApplySensitivityLabel <Label> -Mode TestWithoutNotifications
```

Met deze opdracht worden de extra SharePoint-URL's opgegeven in een variabele die vervolgens wordt toegevoegd aan een bestaand beleid voor automatisch labelen. Als u in plaats daarvan OneDrive-locaties wilt toevoegen, gebruikt u de parameter *AddOneDriveLocation* met een andere variabele, bijvoorbeeld *$OneDriveLocations*.

Nieuwe beleidsregel voor automatisch labelen maken:

```powershell
New-AutoSensitivityLabelRule -Policy <AutoLabelingPolicyName> -Name <AutoLabelingRuleName> -ContentContainsSensitiveInformation @{"name"= "a44669fe-0d48-453d-a9b1-2cc83f2cba77"; "mincount" = "2"} -Workload SharePoint
```

Voor een bestaand beleid voor automatisch labelen wordt met deze opdracht een nieuwe beleidsregel gemaakt voor het detecteren van het type gevoelige informatie **Amerikaans burgerservicenummer (BSN)**, dat de entiteit-id a44669fe-0d48-453d-a9b1-2cc83f2cba77 heeft. Zie [Entiteitsdefinities voor het type gevoelige informatie](sensitive-information-type-entity-definitions.md) om entiteits-id's voor overige typen gevoelige informatie te vinden.

Zie de volgende help voor cmdlets voor meer informatie over de PowerShell-cmdlets die ondersteuning bieden voor beleid voor automatisch labelen, de beschikbare parameters en enkele voorbeelden:

- [Get-AutoSensitivityLabelPolicy](/powershell/module/exchange/get-autosensitivitylabelpolicy)
- [New-AutoSensitivityLabelPolicy](/powershell/module/exchange/new-autosensitivitylabelpolicy)
- [New-AutoSensitivityLabelRule](/powershell/module/exchange/new-autosensitivitylabelrule)
- [Remove-AutoSensitivityLabelPolicy](/powershell/module/exchange/remove-autosensitivitylabelpolicy)
- [Remove-AutoSensitivityLabelRule](/powershell/module/exchange/remove-autosensitivitylabelrule)
- [Set-AutoSensitivityLabelPolicy](/powershell/module/exchange/set-autosensitivitylabelpolicy)
- [Set-AutoSensitivityLabelRule](/powershell/module/exchange/set-autosensitivitylabelrule)

## <a name="tips-to-increase-labeling-reach"></a>Tips om het labelbereik te vergroten

Hoewel automatisch labelen een van de meest efficiënte manieren is om Office-bestanden waarvan uw organisatie eigenaar is te classificeren, labelen en beveiligen, controleer of u deze kunt aanvullen met een van de aanvullende methoden om uw labelbereik te vergroten:

- Als u de geïntegreerde [Azure Information Protection-labelclient](/azure/information-protection/rms-client/aip-clientv2) gebruikt:
    
    - Voor bestanden in on-premises gegevensarchieven, zoals netwerkshares en SharePoint Server-bibliotheken: gebruik de [scanner](/azure/information-protection/deploy-aip-scanner) om gevoelige informatie in deze bestanden te ontdekken en deze op de juiste wijze te labelen. Als u van plan bent om deze bestanden te migreren of uploaden naar SharePoint in Microsoft 365, gebruikt u de scanner om de bestanden te labelen voordat u ze naar de cloud verplaatst.
    
    - Als u een andere labeloplossing hebt gebruikt voordat u vertrouwelijkheidslabels gebruikt: gebruik PowerShell en [een geavanceerde instelling om labels opnieuw te gebruiken](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#migrate-labels-from-secure-islands-and-other-labeling-solutions) uit deze oplossingen.

- Stimuleer [handmatig labelen](https://support.microsoft.com/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9) nadat u gebruikers hebt getraind welke vertrouwelijkheidslabels moeten worden toegepast. Wanneer u zeker weet dat gebruikers begrijpen welk label ze moeten toepassen, kunt u overwegen om een standaardlabel en verplicht labelen te configureren als [beleidsinstellingen](sensitivity-labels.md#what-label-policies-can-do). 

U kunt ook [nieuwe bestanden standaard markeren als gevoelig](/sharepoint/sensitive-by-default) in SharePoint om te voorkomen dat gasten toegang krijgen tot nieuw toegevoegde bestanden totdat ten minste één DLP-beleidsregel de inhoud van het bestand scant.
