---
title: Vertrouwelijkheidslabels in Office-apps beheren
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Informatie voor IT-beheerders voor het beheren van vertrouwelijkheidslabels in Office-apps voor desktop, mobiele apparaten en internet.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6e22ca460acf96151ff54e3b2bbbe03ad1a97a27
ms.sourcegitcommit: 03aa8ed22d9ef685a851e28c7d0cfb725732fe4b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52888395"
---
# <a name="manage-sensitivity-labels-in-office-apps"></a>Vertrouwelijkheidslabels in Office-apps beheren

>*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Als u gevoeligheidslabels hebt [gepubliceerd](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) vanuit het Microsoft 365-compliancecentrum of een soortgelijk labelcentrum, verschijnen ze in Office-apps, zodat gebruikers inhoud kunnen classificeren en beschermen terwijl deze wordt gemaakt of bewerkt.

Gebruik de informatie in dit artikel voor het beheren van vertrouwelijkheidslabels in Office-apps. Bepaal bijvoorbeeld welke minimale versies van apps u nodig hebt voor het ondersteunen van ingebouwd labelen en krijg inzicht in interacties met de geïntegreerde labelclient van Azure Information Protection en de compatibiliteit met andere apps en services.

## <a name="labeling-client-for-desktop-apps"></a>Labelclient voor desktop-apps

Als u vertrouwelijkheidslabels wilt gebruiken die zijn ingebouwd in Office-desktop-apps voor Windows en Mac, moet u een abonnementsversie van Office gebruiken. Deze labelclient biedt geen ondersteuning voor zelfstandige versies van Office, zoals Office 2016 of Office 2019.

Als u vertrouwelijkheidslabels wilt gebruiken voor deze zelfstandige versies van Office op Windows-computers, installeert u de [geïntegreerde labelclient van Azure Information Protection](/azure/information-protection/rms-client/aip-clientv2).

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>Ondersteuning voor functies van vertrouwelijkheidslabels in apps

In de volgende tabellen wordt voor elke functie de minimale Office-versie vermeld die u nodig hebt om vertrouwelijkheidslabels te ondersteunen met behulp van ingebouwd labelen. Of als de labelfunctie in openbare preview is of wordt beoordeeld voor een toekomstige versie. Gebruik de [Microsoft 365-roadmap](https://aka.ms/MIPC/Roadmap) voor meer informatie over toekomstige versies.

Nieuwe versies van Office-apps worden op verschillende tijdstippen beschikbaar gemaakt voor verschillende updatekanalen. Zie [Overzicht van updatekanalen voor Microsoft 365-apps](/DeployOffice/overview-update-channels) voor meer informatie, waaronder het configureren van uw updatekanaal, zodat u een nieuwe labelfunctie kunt testen waarin u mogelijk in bent geïnteresseerd. Nieuwe functies in privépreview zijn niet in de tabel opgenomen, maar u kunt mogelijk deelnemen aan deze previews door uw organisatie te nomineren voor het [Microsoft Information Protection private preview program](https://aka.ms/mip-preview) (Microsoft Information Protection-privépreviewprogramma).

> [!NOTE]
> De namen van de updatekanalen voor Office-apps zijn onlangs gewijzigd. Monthly-kanaal is nu bijvoorbeeld Huidig kanaal en Office Insider is nu bèta-kanaal. Zie [Wijzigingen aan updatekanalen voor Microsoft 365-apps](/deployoffice/update-channels-changes) voor meer informatie.

Office voor iOS en Office voor Android: vertrouwelijkheidslabels zijn ingebouwd in de [Office-app](https://www.microsoft.com/nl-NL/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/).

Er zijn extra functies beschikbaar wanneer u de geïntegreerde labelclient van Azure Information Protection installeert, die alleen op Windows-computers wordt uitgevoerd. Zie [De labelclients voor Windows-computers vergelijken](/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers) voor deze details.

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Functies van vertrouwelijkheidslabels in Word, Excel en PowerPoint

De weergegeven nummers zijn de minimale versies van Office-toepassingen die voor elke functie is vereist.

|Functie                                                                                                        |Windows |Mac |iOS    |Android      |Web                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[Label handmatig toepassen, wijzigen of verwijderen](https://support.microsoft.com/nl-NL/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Ja, deelnemen](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Een standaardlabel toepassen](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Ja, deelnemen](sensitivity-labels-sharepoint-onedrive-files.md)                                                        |
|[Een geldige reden vereisen om een label te wijzigen](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Ja, deelnemen](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Help-koppeling naar een aangepaste Help-pagina opgeven](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Ja, deelnemen](sensitivity-labels-sharepoint-onedrive-files.md) |
|[De inhoud markeren](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Ja, deelnemen](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Dynamische markeringen met variabelen](#dynamic-markings-with-variables)                                              | 2010+           | 16.42+     | 2.42+ | 16.0.13328+ | Wordt geïmplementeerd |
|[Nu machtigingen toewijzen](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Ja, deelnemen](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Gebruikers machtigingen laten toewijzen: <br /> - Gebruikers vragen](encryption-sensitivity-labels.md#let-users-assign-permissions)                     |2004+ | 16.35+   | Ter beoordeling   | Ter beoordeling         | Ter beoordeling                                                        |
|[Activiteit van gebruikers in verband met labels controleren](data-classification-activity-explorer.md)                      | 2011+ | 16.43+ | 2.46+ | Wordt geïmplementeerd: 16.0.13628+ | Ja <sup>\*</sup>                                                        |
|[Vereisen dat gebruikers een label toepassen op hun e-mail en documenten](#require-users-to-apply-a-label-to-their-email-and-documents)   | 2101+             | 16.45+         | 2.47+ | 16.0.13628+ | [Ja, deelnemen](sensitivity-labels-sharepoint-onedrive-files.md)                                            
|[Een vertrouwelijkheidslabel automatisch op inhoud toepassen](apply-sensitivity-label-automatically.md)                    | 2009+                                  | Wordt geïmplementeerd: 16.44+ | Ter beoordeling | Ter beoordeling | [Ja, deelnemen](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Ondersteuning voor cocreatie en automatisch opslaan](sensitivity-labels-coauthoring.md) voor gelabelde en versleutelde documenten | Preview: [Huidig kanaal (preview)](https://office.com/insider) | Preview: [Huidig kanaal (preview)](https://office.com/insider) | Ter beoordeling | Ter beoordeling | [Ja, deelnemen](sensitivity-labels-sharepoint-onedrive-files.md) |
|

**Voetnoot:**

<sup>\*</sup> Bevat momenteel geen tekst met geldige reden om een label te verwijderen of het classificatieniveau te verlagen

### <a name="sensitivity-label-capabilities-in-outlook"></a>Functies van gevoeligheidslabels in Outlook

De weergegeven nummers zijn de minimale versies van Office-toepassingen die voor elke functie is vereist.

|Functie                                                                                                        |Outlook voor Windows |Outlook voor Mac |Outlook voor iOS |Outlook voor Android |Webversie van Outlook |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[Label handmatig toepassen, wijzigen of verwijderen](https://support.microsoft.com/nl-NL/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Een standaardlabel toepassen](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Een geldige reden vereisen om een label te wijzigen](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Help-koppeling naar een aangepaste Help-pagina opgeven](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[De inhoud markeren](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Dynamische markeringen met variabelen](#dynamic-markings-with-variables)                                              | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Nu machtigingen toewijzen](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Gebruikers machtigingen laten toewijzen: <br /> - Niet doorsturen](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Gebruikers machtigingen laten toewijzen: <br /> - Alleen-versleutelen](encryption-sensitivity-labels.md#let-users-assign-permissions)  |2011+ | 16.48+ <sup>\*</sup> | 4.2112.0+  | 4.2112.0+ | Ja |
|[Vereisen dat gebruikers een label toepassen op hun e-mail en documenten](#require-users-to-apply-a-label-to-their-email-and-documents)   | 2101+                        | 16.43+ <sup>\*</sup>                    | 4.2111+            | 4.2111+                | Ja                |
|[Activiteit van gebruikers in verband met labels controleren](data-classification-activity-explorer.md) | 2011+ | Ter beoordeling | Ter beoordeling           | Ter beoordeling               | Ter beoordeling |
|[Een vertrouwelijkheidslabel automatisch op inhoud toepassen](apply-sensitivity-label-automatically.md)                    | 2009+                      | 16.44+ <sup>\*</sup>                    | Ter beoordeling           | Ter beoordeling               | Ja |
|[Verschillende instellingen voor standaardlabels en verplicht labelen](#outlook-specific-options-for-default-label-and-mandatory-labeling)                    | 2105+                      | 16.43.1108+ <sup>\*</sup>                   | 4.2111+           | 4.2111+               | Ja |
|

**Voetnoten:**

<sup>\*</sup> Hiervoor is het [nieuwe Outlook voor Mac](https://support.microsoft.com/office/the-new-outlook-for-mac-6283be54-e74d-434e-babb-b70cefc77439) vereist


## <a name="office-built-in-labeling-client-and-other-labeling-solutions"></a>Ingebouwde Office-labelclient en andere labeloplossingen

Met de ingebouwde Office-labelclient worden vertrouwelijkheidslabels en beleidsinstellingen voor vertrouwelijkheidslabels gedownload van de volgende beheercentra:

- Microsoft 365-compliancecentrum
- Office 365-beveiligings- en compliancecentrum (oudere beheerportal)

Als u de ingebouwde Office-labelclient wilt gebruiken, moet u een of meer [labelbeleidsregels](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) voor gebruikers hebben gepubliceerd vanuit een van de vermelde beheercentra en beschikken over een [ondersteunde versie van Office](#support-for-sensitivity-label-capabilities-in-apps).

Als aan beide voorwaarden wordt voldaan, maar u de ingebouwde Office-labelclient moet uitschakelen, gebruikt u de volgende groepsbeleidsinstelling:

1. Ga naar **Gebruikersconfiguratie/Beheersjablonen/Microsoft Office 2016/Beveiligingsinstellingen**.

2. Stel **De functie Vertrouwelijkheid in Office gebruiken om vertrouwelijkheidslabels toe te passen en weer te geven** in op **0**. 
 
Implementeer deze instelling via groepsbeleid of met behulp van de [Office-cloudbeleidsservice](/DeployOffice/overview-office-cloud-policy-service). De instelling wordt van kracht wanneer Office-apps opnieuw worden gestart.

### <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>De ingebouwde Office-labelclient en de Azure Information Protection-client

Als gebruikers de [Azure Information Protection-client hebben geïnstalleerd](/azure/information-protection/rms-client/aip-clientv2), is de ingebouwde labelclient standaard uitgeschakeld in hun Office-apps. 

Als u ingebouwd labelen wilt gebruiken in plaats van de Azure Information Protection-client voor Office-apps, wordt u aangeraden de groepsbeleidsinstelling **Lijst met beheerde invoegtoepassingen** te gebruiken, zoals gedocumenteerd in [Geen invoegvoegingen geladen vanwege groepsbeleidsinstellingen voor Office 2013- en Office 2016-programma's](https://support.microsoft.com/help/2733070/no-add-ins-loaded-due-to-group-policy-settings-for-office-2013-and-off).

Voor Microsoft Word 2016, Excel 2016, PowerPoint 2016 en Outlook 2016 geeft u de volgende programmatische id's (ProgID) op voor de Azure Information Protection-client en stelt u de optie in op **0: de invoegtoepassing is altijd uitgeschakeld (geblokkeerd)**

|Toepassing  |ProgID  |
|---------|---------|
|Word     |     `MSIP.WordAddin`    |
|Excel     |  `MSIP.ExcelAddin`       |
|PowerPoint     |   `MSIP.PowerPointAddin`      |
|Outlook | `MSIP.OutlookAddin` |
| | | 


Implementeer deze instelling via groepsbeleid of met behulp van de [Office-cloudbeleidsservice](/DeployOffice/overview-office-cloud-policy-service).

> [!NOTE]
> Als u de groepsbeleidsinstelling **De functie Vertrouwelijkheid in Office gebruiken om vertrouwelijkheidslabels toe te passen en weer te geven** gebruikt en deze instelt op **1**, zijn er situaties waarin de Azure Information Protection-client mogelijk nog steeds wordt geladen in Office-apps. Door het laden van de invoegtoepassing in elke app te blokkeren, wordt dit voorkomen.

U kunt de Office-invoegtoepassing van **Microsoft Azure Information Protection** ook interactief uitschakelen of verwijderen uit Word, Excel, PowerPoint en Outlook. Deze methode is geschikt voor één computer en ad-hoctests. Zie [Invoegtoepassingen in Office-programma's weergeven, beheren en installeren](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d) voor instructies. 

Welke methode u ook kiest, de wijzigingen worden doorgevoerd wanneer Office-apps opnieuw worden gestart. Als u deze Office-invoegtoepassing uitschakelt of verwijdert, blijft de Azure Information Protection-client op de computer geïnstalleerd, zodat u bestanden buiten uw Office-apps kunt labelen. Bijvoorbeeld met behulp van Verkenner of PowerShell.

Zie [Uw Windows-labeloplossing kiezen](/azure/information-protection/rms-client/use-client#choose-your-windows-labeling-solution) in de documentatie van Azure Information Protection voor informatie over de functies die worden ondersteund door de Azure Information Protection-clients en de ingebouwde Office-labelclient.

## <a name="office-file-types-supported"></a>Ondersteunde Office-bestandstypen

Office-apps met ingebouwd labelen voor Word-, Excel- en PowerPoint-bestanden ondersteunen de Open XML-indeling (zoals .docx en .xlsx), maar niet de Microsoft Office 97-2003-indeling (zoals .doc en .xls), de Open Document Format (zoals .odt en .ods) of andere indelingen. Wanneer een bestandstype niet wordt ondersteund voor ingebouwd labelen, is de knop **Vertrouwelijkheid** niet beschikbaar in de Office-app.

De geïntegreerde Azure Information Protection-labelclient ondersteunt zowel de Open XML-indeling als de Microsoft Office 97-2003-indeling. Zie [Bestandstypen die worden ondersteund door de geïntegreerde Azure Information Protection-labelclient](/azure/information-protection/rms-client/clientv2-admin-guide-file-types) in de beheerdershandleiding van die client voor meer informatie.

Voor andere labeloplossingen raadpleegt u de documentatie voor ondersteunde bestandstypen.

## <a name="protection-templates-and-sensitivity-labels"></a>Beveiligingssjablonen en vertrouwelijkheidslabels

Door een beheerder gedefinieerde [beveiligingssjablonen](/azure/information-protection/configure-policy-templates), zoals sjablonen die u definieert voor Office 365-berichtversleuteling, zijn niet zichtbaar in Office-apps wanneer u ingebouwd labelen gebruikt. Deze vereenvoudigde ervaring toont dat u geen beveiligingssjabloon hoeft te selecteren, omdat dezelfde instellingen zijn opgenomen in vertrouwelijkheidslabels waarvoor versleuteling is ingeschakeld.

Als u bestaande beveiligingssjablonen naar labels wilt converteren, gebruikt u Azure Portal en de volgende instructies: [Sjablonen converteren naar labels](/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels).

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>IRM-opties (Information Rights Management) en vertrouwelijkheidslabels

Door vertrouwelijkheidslabels te configureren voor het toepassen van versleuteling, hoeven gebruikers hun eigen versleutelingsinstellingen niet meer op te geven. In veel Office-apps kunnen deze afzonderlijke versleutelingsinstellingen nog steeds handmatig door gebruikers worden geconfigureerd met behulp van IRM-opties (Information Rights Management). Bijvoorbeeld voor Windows-apps:

- Voor een document: **Bestandsindeling** > **Info** > **Document beveiligen** > **Toegang beperken**
- Voor een e-mailbericht: vanaf het tabblad **Opties** > **Versleutelen** 
  
Wanneer gebruikers in eerste instantie een label aan een document of e-mail toevoegen, kunnen ze de instellingen voor de labelconfiguratie overschrijven met hun eigen versleutelingsinstellingen. Bijvoorbeeld:

- Een gebruiker past het label **Vertrouwelijk\Alle werknemers** toe op een document. Dit label wordt zodanig geconfigureerd dat versleutelingsinstellingen worden toegepast op alle gebruikers in de organisatie. Deze gebruiker configureert vervolgens handmatig de IRM-instellingen om de toegang tot een gebruiker van buiten uw organisatie te beperken. Het eindresultaat is een document met het label **Vertrouwelijk\Alle werknemers** en het is versleuteld, maar gebruikers in uw organisatie kunnen het niet openen.

- Een gebruiker past het label **Vertrouwelijk/Alleen ontvangers** toe op een e-mailbericht. Dit e-mailbericht wordt zodanig geconfigureerd zodat de versleutelingsinstelling **Niet doorsturen** wordt toegepast. In de Outlook-app selecteert deze gebruiker vervolgens handmatig de IRM-instelling voor Alleen versleutelen. Het eindresultaat is dat het e-mailbericht versleuteld blijft en door geadresseerden kan worden doorgestuurd, ook al bevat de e-mail het label **Vertrouwelijk/Alleen ontvangers**.
    
    Voor de webversie van Outlook geldt een uitzondering. Hier zijn de opties in het menu **Versleutelen** niet beschikbaar voor een gebruiker om te selecteren wanneer door het huidige geselecteerde label versleuteling wordt toegepast.

- Een gebruiker past het label **Algemeen** op een document toe en dit label wordt niet geconfigureerd om versleuteling toe te passen. Deze gebruiker configureert vervolgens handmatig de IRM-instellingen om de toegang tot het document te beperken. Het eindresultaat is een document met het label **Algemeen**, maar waarmee ook versleuteling wordt toegepast, zodat sommige gebruikers het niet kunnen openen zoals verwacht.

Als het document of e-mailbericht al een label heeft, kan een gebruiker een van deze acties uitvoeren als de inhoud nog niet is versleuteld of als de gebruiker het [gebruiksrecht](/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) Exporteren of Volledig beheer heeft. 

Voor een consistentere labelervaring met zinvolle rapportage moet u de juiste labels en richtlijnen opgeven zodat gebruikers alleen labels kunnen toepassen om documenten en e-mails te beveiligen. Bijvoorbeeld:

- In uitzonderingsgevallen waarin gebruikers hun eigen machtigingen moeten kunnen toewijzen, moet u labels opgeven waarmee [gebruikers hun eigen machtigingen kunnen toewijzen](encryption-sensitivity-labels.md#let-users-assign-permissions). 

- In plaats van dat gebruikers de versleuteling handmatig verwijderen nadat ze een label hebben geselecteerd waarmee versleuteling wordt toegepast, geeft u een alternatief sublabel op als gebruikers een label met dezelfde classificatie maar geen versleuteling nodig hebben. Zoals:
    - **Vertrouwelijk/Alle werknemers**
    - **Vertrouwelijk\Iedereen (geen versleuteling)**

- U kunt IRM-instellingen uitschakelen om te voorkomen dat gebruikers deze selecteren:
    - Outlook voor Windows: 
        - Registersleutels (DWORD:00000001) *DisableDNF* en *DisableEO* van HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Common\DRM
        - Zorg ervoor dat de groepsbeleidsinstelling **Standaardversleutelingsoptie configureren voor de knop Versleutelen** niet is geconfigureerd
    - Outlook voor Mac: 
        - Sleutels *DisableEncryptOnly* en *DisableDoNotForward* beveiligingsinstellingen beschreven in [Voorkeuren instellen voor Outlook voor Mac](/DeployOffice/mac/preferences-outlook)
    - Webversie van Outlook: 
        - Parameters *SimplifiedClientAccessDoNotForwardDisabled* en *SimplifiedClientAccessEncryptOnlyDisabled* gedocumenteerd voor [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration)
    - Outlook voor iOS en Android: Deze apps bieden geen ondersteuning voor gebruikers die versleuteling toepassen zonder labels, dus u hoeft niets uit te schakelen.

> [!NOTE]
> Als gebruikers handmatig versleuteling verwijderen uit een gelabeld document dat is opgeslagen in SharePoint of OneDrive en u [vertrouwelijkheidslabels voor Office-bestanden in SharePoint en OneDrive](sensitivity-labels-sharepoint-onedrive-files.md) hebt ingeschakeld, wordt de labelversleuteling automatisch hersteld wanneer het document de volgende keer wordt geopend of gedownload. 


## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>Vertrouwelijkheidslabels toepassen op bestanden, e-mailberichten en bijlagen

Gebruikers kunnen slechts één label tegelijk toepassen op een document of e-mailbericht.

Wanneer u een label op een e-mailbericht met bijlagen toepast, nemen de bijlagen het label alleen over als het label dat u op het e-mailbericht toepast, versleuteling toepast en de bijlage een Office-document is dat nog niet is versleuteld. Omdat het overgenomen label versleuteling toepast, wordt de bijlage opnieuw versleuteld.

Een bijlage neemt de labels van het e-mailbericht niet over wanneer het label dat op het e-mailbericht is toegepast, geen versleuteling toepast of als de bijlage al is versleuteld.

Voorbeelden van overname van labels, waarbij het label **Vertrouwelijk** versleuteling toepast en het label **Algemeen** geen versleuteling toepast:

- Een gebruiker maakt een nieuw e-mailbericht en past het label **Vertrouwelijk** op dit bericht toe. Vervolgens voegt de gebruiker een Word-document toe dat niet is gelabeld of versleuteld. Als gevolg van de overname wordt het document opnieuw voorzien van het label **Vertrouwelijk** en wordt er nu versleuteling door dit label op toegepast.

- Een gebruiker maakt een nieuw e-mailbericht en past het label **Vertrouwelijk** op dit bericht toe. Vervolgens voegt de gebruiker een Word-document toe met het label **Algemeen** en wordt dit bestand niet versleuteld. Als gevolg van de overname wordt het document opnieuw voorzien van het label **Vertrouwelijk** en wordt er nu versleuteling door dit label op toegepast.

## <a name="sensitivity-label-compatibility"></a>Compatibiliteit van vertrouwelijkheidslabels

**Met RMS uitgebreide apps**: als u een gelabeld en versleuteld document of e-mailbericht opent in een [met RMS uitgebreide toepassing](/azure/information-protection/requirements-applications#rms-enlightened-applications) die geen vertrouwelijkheidslabels ondersteunt, dwingt de app nog steeds versleuteling en beheer van rechten af.

**Met de Azure Information Protection-client**: u kunt vertrouwelijkheidslabels die u met de ingebouwde Office-labelclient op documenten en e-mailberichten toepast, weergeven en wijzigen met behulp van de Azure Information Protection-client, en omgekeerd.

**Met andere versies van Office**: elke gemachtigde gebruiker kan gelabelde documenten en e-mailberichten openen in andere versies van Office. U kunt het label echter alleen weergeven of wijzigen in ondersteunde Office-versies of met behulp van de Azure Information Protection-client. Ondersteunde versies van Office-apps staan in de [vorige sectie](#support-for-sensitivity-label-capabilities-in-apps) vermeld.

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>Ondersteuning voor SharePoint- en OneDrive-bestanden die door vertrouwelijkheidslabels zijn beveiligd

Als u de ingebouwde Office-labelclient met de webversie van Office wilt gebruiken voor documenten in SharePoint of OneDrive, moeten de [vertrouwelijkheidslabels voor Office-bestanden in SharePoint en OneDrive zijn ingeschakeld](sensitivity-labels-sharepoint-onedrive-files.md).

## <a name="support-for-external-users-and-labeled-content"></a>Ondersteuning voor externe gebruikers en gelabelde inhoud

Wanneer u een label op een document of e-mail toepast, wordt het label opgeslagen als metagegevens. Hierin zijn uw tenant en een label-GUID opgenomen. Wanneer een gelabeld document of e-mailbericht wordt geopend door een Office-app die vertrouwelijkheidslabels ondersteunt, worden deze metagegevens gelezen. Alleen als de gebruiker tot dezelfde tenant behoort, wordt het label in de app weergegeven. Voor bijvoorbeeld ingebouwd labelen voor Word, PowerPoint en Excel wordt de labelnaam weergegeven op de statusbalk. 

Dit betekent dat als u documenten deelt met een andere organisatie die verschillende labelnamen gebruikt, die organisatie het eigen label op het document kan toepassen en dit toegepaste label kan zien. De volgende elementen van een toegepast label zijn echter zichtbaar voor gebruikers van buiten uw organisatie:

- Inhoudsmarkeringen. Wanneer door een label een koptekst, voettekst of watermerk wordt toegepast, worden deze rechtstreeks aan de inhoud toegevoegd en blijven ze zichtbaar totdat iemand de inhoud wijzigt of verwijdert.

- De naam en beschrijving van de onderliggende beveiligingssjabloon op basis van een label waarmee versleuteling is toegepast. Deze informatie wordt weergegeven op een berichtenbalk boven aan het document, met informatie over wie gemachtigd is om het document te openen, en de gebruiksrechten voor dat document van die persoon of personen.

### <a name="sharing-encrypted-documents-with-external-users"></a>Versleutelde documenten delen met externe gebruikers

Naast het beperken van de toegang tot gebruikers in uw eigen organisatie, kunt u de toegang uitbreiden voor elke andere gebruiker met een account in Azure Active Directory. Als uw organisatie echter gebruikmaakt van beleidsregels voor voorwaardelijke toegang, raadpleegt u de [volgende sectie](#conditional-access-policies) voor aanvullende overwegingen.

In alle Office-apps en andere [met RMS uitgebreide toepassingen](/azure/information-protection/requirements-applications#rms-enlightened-applications) kunnen versleutelde documenten worden geopend nadat de gebruiker is geverifieerd. 

Als externe gebruikers geen account hebben in Azure Active Directory, kunnen ze zich verifiëren met behulp van gastaccounts in uw tenant. Deze gastaccounts kunnen ook worden gebruikt om gedeelde documenten in SharePoint of OneDrive te openen wanneer u [vertrouwelijkheidslabels hebt ingeschakeld voor Office-bestanden in SharePoint en OneDrive](sensitivity-labels-sharepoint-onedrive-files.md):

- U kunt deze gastaccounts zelf maken. U kunt een e-mailadres opgeven dat deze gebruikers al gebruiken. Bijvoorbeeld hun Gmail-adres.
    
    Het voordeel van deze optie is dat u de toegang en rechten tot specifieke gebruikers kunt beperken door hun e-mailadres op te geven in de versleutelingsinstellingen. Een nadeel is het extra beheer dat gepaard gaat met het maken en coördineren van het account met de labelconfiguratie.

- Een andere mogelijkheid is om [SharePoint- en OneDrive-integratie met Azure AD B2B (preview)](/sharepoint/sharepoint-azureb2b-integration-preview) te gebruiken, zodat gastaccounts automatisch worden gemaakt wanneer uw gebruikers koppelingen delen.
    
    Het voordeel van deze optie is een minimale extra hoeveelheid beheer, omdat de accounts automatisch worden gemaakt en de labelconfiguratie eenvoudiger is. Voor dit scenario moet u de versleutelingsoptie [Geverifieerde gebruiker toevoegen](encryption-sensitivity-labels.md#requirements-and-limitations-for-add-any-authenticated-users) selecteren, omdat u de e-mailadressen niet van tevoren weet. Het nadeel is dat u met deze instelling geen toegangs- en gebruiksrechten tot specifieke gebruikers kunt beperken.

Externe gebruikers kunnen ook een Microsoft-account gebruiken om versleutelde documenten te openen wanneer ze Windows- en Microsoft 365-apps ([voorheen Office 365-apps](/deployoffice/name-change)) of de zelfstandige editie van Office 2019 gebruiken. Microsoft-accounts die onlangs voor andere platforms worden ondersteund, worden ook ondersteund voor het openen van versleutelde documenten in macOS (Microsoft 365-apps, versie 16.42+), Android (versie 16.0.13029+) en iOS (versie 2.42+). Een gebruiker in uw organisatie deelt bijvoorbeeld een versleuteld document met een gebruiker van buiten uw organisatie. Met de versleutelingsinstellingen wordt een Gmail-adres voor de externe gebruiker opgegeven. Deze externe gebruiker kan een eigen Microsoft-account maken dat gebruikmaakt van het Gmail-adres. Nadat de gebruiker zich met dit account heeft aangemeld, kan deze het document openen en bewerken op basis van de gebruiksbeperkingen die voor hem of haar zijn opgegeven. Zie [Het beveiligde document openen en bewerken](/azure/information-protection/secure-collaboration-documents#opening-and-editing-the-protected-document) voor een uitgebreid voorbeeld van dit scenario.

> [!NOTE]
> Het e-mailadres voor het Microsoft-account moet overeenkomen met het e-mailadres dat is opgegeven om de toegang tot versleutelingsinstellingen te beperken.

Wanneer een gebruiker met een Microsoft-account op deze manier een versleuteld document opent, wordt automatisch een gastaccount voor de tenant gemaakt als er nog geen gastaccount met dezelfde naam bestaat. Wanneer het gastaccount bestaat, kan het vervolgens worden gebruikt om documenten te openen in SharePoint en OneDrive met behulp van de webversie van Office. Daarnaast kunnen versleutelde documenten worden geopend vanuit de ondersteunde Office-apps voor desktop en mobiel.

Vanwege replicatielatentie wordt het automatische gastaccount in dit scenario echter niet onmiddellijk gemaakt. Als u persoonlijke e-mailadressen opgeeft als onderdeel van de instellingen voor labelversleuteling, wordt u aangeraden corresponderende gastaccounts te maken in Azure Active Directory. Laat deze gebruikers vervolgens weten dat ze dit account moeten gebruiken om een versleuteld document van uw organisatie te openen.

> [!TIP]
> Aangezien u niet zeker weet of externe gebruikers een ondersteunde Office-client-app gebruiken, is het delen van koppelingen vanuit SharePoint en OneDrive na het maken van gastaccounts (voor specifieke gebruikers) of wanneer u gebruikmaakt van [integratie van SharePoint en OneDrive met Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview) (voor elke geverifieerde gebruiker) een betrouwbaardere methode ter ondersteuning van veilige samenwerking met externe gebruikers.

### <a name="conditional-access-policies"></a>Beleidsregels voor voorwaardelijke toegang

Als uw organisatie [beleid voor voorwaardelijke toegang van Azure Active Directory](/azure/active-directory/conditional-access/overview) heeft geïmplementeerd, controleert u de configuratie van dat beleid. Als het beleid **Microsoft Azure Information Protection** omvat en het beleid van kracht is voor externe gebruikers, moeten deze externe gebruikers een gastaccount in uw tenant hebben, ook als ze een Azure AD-account in hun eigen tenant hebben.

Zonder dit gastaccount kunnen ze het versleutelde document niet openen en wordt een foutbericht weergegeven. De berichttekst kan gebruikers informeren dat hun account moet worden toegevoegd als een externe gebruiker in de tenant, met de onjuiste instructie voor dit scenario om **zich af te melden en opnieuw aan te melden met een ander Azure Active Directory-gebruikersaccount**.

Als u geen gastaccounts in uw tenant kunt maken en configureren voor externe gebruikers die documenten moeten openen die zijn versleuteld door uw labels, moet u Azure Information Protection verwijderen uit het beleid voor voorwaardelijke toegang of externe gebruikers uitsluiten van het beleid.

Zie de veelgestelde vraag [Ik zie dat Azure Information Protection vermeld staat als een beschikbare cloud-app voor voorwaardelijke toegang. Hoe werkt dit?](/azure/information-protection/faqs#i-see-azure-information-protection-is-listed-as-an-available-cloud-app-for-conditional-accesshow-does-this-work) voor meer informatie over voorwaardelijke toegang en Azure Information Protection, de versleutelingsservice die door vertrouwlijkheidslabels wordt gebruikt.

## <a name="when-office-apps-apply-content-marking-and-encryption"></a>Wanneer Office-apps markering en versleuteling van inhoud toepassen

Office-apps passen markering en versleuteling van inhoud met een gevoeligheidslabel anders toe, afhankelijk van de app die u gebruikt.

| App | Inhoudsmarkering | Versleuteling |
| --- | --- | --- |
| Word, Excel, PowerPoint op alle platforms | Onmiddellijk | Onmiddellijk |
| Outlook voor pc en Mac | Nadat Exchange Online de e-mail heeft verzonden | Onmiddellijk |
| Webversie van Outlook, iOS en Android | Nadat Exchange Online de e-mail heeft verzonden | Nadat Exchange Online de e-mail heeft verzonden |
|

Oplossingen die gevoeligheidslabels toepassen op bestanden buiten Office-apps, doen dit door labelmetagegevens op het bestand toe te passen. In dit scenario wordt inhoudsmarkering op basis van de configuratie van het label niet in het bestand ingevoegd, maar wordt versleuteling toegepast. 

Wanneer deze bestanden worden geopend in een Office-desktop-app, worden de inhoudsmarkeringen automatisch toegepast door de geïntegreerde labelclient van Azure Information Protection wanneer het bestand voor het eerst wordt opgeslagen. De inhoudsmarkeringen worden niet automatisch toegepast wanneer u ingebouwd labelen gebruikt voor desktop-, mobiele of web-apps.

Scenario's waarin vertrouwelijkheidslabels buiten Office-apps worden toegepast, omvatten onder andere:

- De scanner, Verkenner en PowerShell van de geïntegreerde labelclient van Azure Information Protection 

- Beleid voor automatisch labelen voor SharePoint en OneDrive

- Vanuit Power BI geëxporteerde gelabelde en versleutelde gegevens

- Microsoft Cloud App Security

Voor deze scenario's kan een gebruiker met ingebouwd labelen vanuit de Office-apps de inhoudsmarkeringen van het label toepassen door het huidige label tijdelijk te verwijderen of te vervangen en vervolgens het oorspronkelijke label opnieuw toe te passen.

### <a name="dynamic-markings-with-variables"></a>Dynamische markeringen met variabelen

> [!IMPORTANT]
> Momenteel ondersteunen niet alle apps op alle platforms dynamische inhoudsmarkeringen die u voor kopteksten, voetteksten en watermerken kunt opgeven. Voor apps die deze mogelijkheid niet ondersteunen, worden de markeringen toegepast op de oorspronkelijke tekst die is opgegeven in de labelconfiguratie, in plaats van dat de variabelen worden omgezet.
> 
> De geïntegreerde Azure Information Protection-labelclient ondersteunt dynamische markeringen. Voor labeling die is ingebouwd in Office, bekijkt u de tabellen in de sectie [Mogelijkheden](#support-for-sensitivity-label-capabilities-in-apps) op deze pagina voor ondersteunde minimale versies.

Wanneer u een vertrouwelijkheidslabel configureert voor inhoudsmarkeringen, kunt u de volgende variabelen in de tekenreeks gebruiken voor de koptekst, voettekst of het watermerk:

| Variabele | Omschrijving | Voorbeeld van wanneer een label wordt toegepast |
| -------- | ----------- | ------- |
| `${Item.Label}` | Weergavenaam van het toegepaste label | **Algemeen**|
| `${Item.Name}` | Bestandsnaam of e-mailonderwerp van de te labelen inhoud | **Verkoop.docx** |
| `${Item.Location}` | Pad- en bestandsnaam van het te labelen document of het e-mailonderwerp voor een te labelen e-mailbericht | **\\\Verkoop\2020\K3\Rapport.docx**|
| `${User.Name}` | Weergavenaam van de gebruiker die het label toepast | **Stefan Spel** |
| `${User.PrincipalName}` | UPN (Azure AD-user principal name) van de gebruiker die het label toepast | **sspel\@contoso.com** |
| `${Event.DateTime}` | Datum en tijdstip waarop de inhoud wordt gelabeld, in de lokale tijdzone van de gebruiker die het label toepast | **10-8-2020 13:30 uur** |

> [!NOTE]
> De syntaxis voor deze variabelen is hoofdlettergevoelig.

#### <a name="setting-different-visual-markings-for-word-excel-powerpoint-and-outlook"></a>Verschillende visuele markeringen instellen voor Word, Excel, PowerPoint en Outlook

Als extra variabele kunt u visuele markeringen configureren per type Office-toepassing met behulp van een variabele If.App-instructie in de tekenreeks en kunt u het toepassingstype identificeren met behulp van de waarden **Word**, **Excel**, **PowerPoint** of **Outlook**. U kunt deze waarden ook afkorten, wat nodig is als u meerdere waarden in dezelfde If.App-instructie wilt opgeven.

Gebruik de volgende syntaxis:

```
${If.App.<application type>}<your visual markings text> ${If.End}
```

Net als met de andere dynamische visuele markeringen, is de syntaxis hoofdlettergevoelig, wat ook geldt voor de afkortingen voor elk toepassingstype (WEPO).

Voorbeelden:

- **Alleen koptekst instellen voor Word-documenten:**

    `${If.App.Word}This Word document is sensitive ${If.End}`

    Alleen in kopteksten van Word-documenten wordt de koptekst 'Dit Word-document is gevoelig' toegepast. Er wordt geen koptekst toegepast op andere Office-toepassingen.

- **Voettekst instellen voor Word, Excel en Outlook en een andere voettekst voor PowerPoint:**

    `${If.App.WXO}This content is confidential. ${If.End}${If.App.PowerPoint}This presentation is confidential. ${If.End}`

    In Word, Excel en Outlook wordt de voettekst 'Deze inhoud is vertrouwelijk' toegepast. In PowerPoint wordt de voettekst 'Deze presentatie is vertrouwelijk' toegepast.

- **Specifieke watermerktekst instellen voor Word en PowerPoint en vervolgens een watermerktekst voor Word, Excel en PowerPoint:**

    `${If.App.WP}This content is ${If.End}Confidential`

    In Word en PowerPoint wordt de watermerktekst 'Deze inhoud is vertrouwelijk' toegepast. In Excel wordt de watermerktekst 'Vertrouwelijk' toegepast. In Outlook wordt er geen watermerktekst toegepast, omdat watermerken niet als visuele markeringen in Outlook worden ondersteund.

## <a name="require-users-to-apply-a-label-to-their-email-and-documents"></a>Vereisen dat gebruikers een label toepassen op hun e-mail en documenten

> [!IMPORTANT]
> 
> De [geïntegreerde Azure Information Protection-labelclient](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) ondersteunt deze configuratie, ook wel verplicht labelen genoemd. Voor in Office ingebouwd labelen, raadpleegt u de tabellen in de sectie [Mogelijkheden](#support-for-sensitivity-label-capabilities-in-apps) op deze pagina voor ondersteunde minimale versies.
>
> Als u verplicht labelen voor documenten maar niet voor e-mailberichten wilt gebruiken, volgt u de instructies in de volgende sectie, waarin wordt uitgelegd hoe u Outlook-specifieke opties configureert.

Wanneer de beleidsinstelling **Gebruikers verplichten een label toe te passen op hun e-mail en documenten** is geselecteerd, moeten gebruikers aan wie het beleid is toegewezen, een vertrouwelijkheidslabel selecteren en toepassen in de volgende scenario's:

- Voor de geïntegreerde Azure Information Protection-labelclient:
    - Voor documenten (Word, Excel, PowerPoint): wanneer een document zonder label wordt opgeslagen of wanneer gebruikers het document sluiten.
    - Voor e-mailberichten (Outlook): op het moment dat gebruikers een bericht zonder label verzenden.

- Voor in Office-apps ingebouwd labelen:
    - Voor documenten (Word, Excel, PowerPoint): wanneer een document zonder label wordt geopend of opgeslagen.
    - Voor e-mailberichten (Outlook): op het moment dat gebruikers een e-mailbericht zonder label verzenden.

Aanvullende informatie voor ingebouwd labelen:

- Wanneer gebruikers wordt gevraagd een vertrouwelijkheidslabel toe te voegen omdat ze een document zonder label openen, kunnen ze een label toevoegen of het document openen in de modus alleen-lezen.

- Wanneer verplicht labelen is doorgevoerd, kunnen gebruikers geen vertrouwelijkheidslabels uit documenten verwijderen, maar wel een bestaand label wijzigen.

Zie de informatie over [beleidsinstellingen](sensitivity-labels.md#what-label-policies-can-do) voor hulp bij het gebruik van deze instelling.

> [!NOTE]
> Als u naast het verplichte labelen ook de standaardinstelling voor labelbeleid gebruikt voor documenten en e-mailberichten: 
>
> Het standaardlabel heeft altijd prioriteit boven verplicht labelen. Voor documenten wordt met de geïntegreerde Azure Information Protection-labelclient echter het standaardlabel toegepast op alle documenten zonder label. Met ingebouwd labelen wordt het standaardlabel op nieuwe documenten toegepast en niet op bestaande documenten zonder label. Dit verschil in gedrag betekent dat wanneer u verplicht labelen gebruikt met de standaardlabelinstelling, gebruikers vaker wordt gevraagd een vertrouwelijkheidslabel toe te passen wanneer ze ingebouwd labelen gebruiken dan wanneer ze de geïntegreerde Azure Information Protection-labelclient gebruiken.

## <a name="outlook-specific-options-for-default-label-and-mandatory-labeling"></a>Outlook-specifieke opties voor standaardlabels en verplicht labelen

Voor ingebouwd labelen bepaalt u de minimale versies van Outlook die deze functies ondersteunen met behulp van de [functietabel voor Outlook](#sensitivity-label-capabilities-in-outlook) op deze pagina en de rij **Verschillende instellingen voor standaardlabels en verplicht labelen**. Alle versies van de geïntegreerde labelclient van Azure Information Protection ondersteunen deze Outlook-specifieke opties.

Wanneer de Outlook-app een standaard labelinstelling ondersteunt die verschilt van de standaard labelinstelling voor documenten:

- In de wizard voor labelbeleid kunt u op de pagina **Een standaardlabel toepassen op e-mails** uw keuze specificeren voor een gevoeligheidslabel dat wordt toegepast op alle niet-gelabelde e-mails of geen standaardlabel. Deze instelling is onafhankelijk van de instelling **Dit label standaard toepassen op documenten** op de vorige pagina **Beleidsinstellingen voor documenten** van de wizard.

Wanneer de Outlook-app geen standaardlabelinstelling ondersteunt die afwijkt van de standaardlabelinstelling voor documenten: Outlook gebruikt altijd de waarde die u opgeeft voor **Dit label standaard toepassen op documenten** op de pagina **Beleidsinstellingen voor documenten** van de wizard voor labelbeleid.

Wanneer de Outlook-app het uitschakelen van verplichte labeling ondersteunt:

- Selecteer in de wizard voor labelbeleid op de pagina **Beleidsinstellingen** de optie **Vereisen dat gebruikers een label toepassen op hun e-mail en documenten**. Selecteer vervolgens **Volgende** > **Volgende** en schakel het selectievakje **Vereisen dat gebruikers een label toepassen op hun e-mails**. Zorg dat het selectievakje is ingeschakeld als u wilt dat verplichte labels worden toegepast op e-mails en documenten.

Wanneer de Outlook-app geen ondersteuning biedt voor het uitschakelen van verplichte labeling: als u **Vereisen dat gebruikers een label toepassen op hun e-mail of documenten** als beleidsinstelling selecteert, wordt de gebruiker altijd gevraagd een label te selecteren voor e-mails zonder label.

> [!NOTE]
> Als u de geavanceerde instellingen van PowerShell **OutlookDefaultLabel** en **DisableMandatoryInOutlook** hebt geconfigureerd met behulp van de cmdlets [Set-LabelPolicy](/powershell/module/exchange/set-labelpolicy) of [New-LabelPolicy](/powershell/module/exchange/new-labelpolicy):
> 
> De gekozen waarden voor deze PowerShell-instellingen worden weergegeven in de wizard voor labelbeleid en werken automatisch voor Outlook-apps die deze instellingen ondersteunen. De overige geavanceerde PowerShell-instellingen blijven alleen ondersteund voor de Azure Information Protection-labelclient. 

## <a name="end-user-documentation"></a>Documentatie voor eindgebruikers

- [Vertrouwelijkheidslabels toepassen op uw documenten en e-mail in Office](https://support.microsoft.com/nl-NL/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
    - [Bekende problemen met vertrouwelijkheidslabels in Office](https://support.microsoft.com/nl-NL/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [Vertrouwelijkheidslabels automatisch toepassen op of aanbevelen voor uw bestanden en e-mailberichten in Office](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)
    - [Bekende problemen met het automatisch toepassen of aanbevelen van vertrouwelijkheidslabels](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)
