---
title: Aan de slag met vertrouwelijkheidslabels
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
description: Bent u klaar voor het implementeren van gevoeligheidslabels om de gegevens van uw organisatie te beschermen, maar weet u niet zeker waar u moet beginnen? Lees enkele praktische richtlijnen om u op weg te helpen met labelen.
ms.openlocfilehash: c87289fc7017e75db3b8a5b84a8af3a42dc16a10
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689119"
---
# <a name="get-started-with-sensitivity-labels"></a>Aan de slag met vertrouwelijkheidslabels

>*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Zie [Meer informatie over vertrouwelijkheidslabels](sensitivity-labels.md) voor informatie over vertrouwelijkheidslabels en hoe ze u kunnen helpen bij het beschermen van de gegevens van uw organisatie.

Als u [Azure Information Protection](/azure/information-protection/what-is-information-protection) hebt en nog steeds labels van Azure Information Protection gebruikt die zijn beheerd vanuit de Azure-portal, moet u deze labels migreren naar het [platform voor labeling](/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform). Voor Windows-computers kunt u vervolgens [kiezen welke labelclient u](/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers) voor uw gepubliceerde gevoeligheidslabels.

Wanneer u klaar bent om te beginnen met het beveiligen van de gegevens van uw organisatie met behulp van gevoeligheidslabels:

1. **Maak de labels.** Maak en benoem uw gevoeligheidslabels volgens de classificatie-taxonomie van uw organisatie voor verschillende gevoeligheidsniveaus voor inhoud. Gebruik veelgebruikte namen of termen die voor uw gebruikers zinvol zijn. Als u nog geen taxonomie hebt, kunt u overwegen om te beginnen met labelnamen zoals Persoonlijk, Openbaar, Algemeen, Vertrouwelijk en Zeer vertrouwelijk. U kunt vervolgens sublabels gebruiken om soortgelijke labels te groepeert op categorie. Wanneer u een label maakt, gebruikt u de tekst in de knopinfo om gebruikers te helpen het juiste label te selecteren.
    
    Voor uitgebreidere instructies voor het definiëren van een classificatie taxonomie downloadt u het whitepaper 'Data Classification & Sensitivity Label Taxonomy' van de [Service Trust Portal](https://aka.ms/DataClassificationWhitepaper).

2. **Bepalen wat elk label kan doen.** Configureer de beveiligingsinstellingen die u aan elk label wilt koppelen. U wilt bijvoorbeeld dat inhoud met een lagere gevoeligheid (zoals een label 'Algemeen') alleen een koptekst of voettekst krijgt, terwijl inhoud met een hogere gevoeligheid (zoals een label 'Vertrouwelijk') een watermerk en versleuteling.

3. **De labels publiceren.** Wanneer uw gevoeligheidslabels zijn geconfigureerd, kunt u deze publiceren met een labelbeleid. Bepaal welke gebruikers en groepen de labels moeten hebben en welke beleidsinstellingen u wilt gebruiken. Een enkel label is herbruikbaar: u definieert het eenmaal en vervolgens kunt u het opnemen in verschillende labelbeleidsregels die aan verschillende gebruikers zijn toegewezen. U kunt bijvoorbeeld uw gevoeligheidslabels piloten door een labelbeleid toe te wijzen aan slechts een paar gebruikers. Wanneer u klaar bent om de etiketten in uw organisatie uit te rollen, kunt u een nieuw etiketbeleid maken voor uw etiketten en deze keer alle gebruikers opgeven.

De basisstroom voor het implementeren en toepassen van gevoeligheidslabels:

![Diagram met werkstroom voor gevoeligheidslabels](../media/Sensitivity-label-flow.png)

## <a name="subscription-and-licensing-requirements-for-sensitivity-labels"></a>Abonnements- en licentievereisten voor vertrouwelijkheidslabels

Een aantal verschillende abonnementen ondersteunen vertrouwelijkheidslabels en de licentievereisten voor gebruikers zijn afhankelijk van de functies die u gebruikt.

Zie de [Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) om de opties te zien voor de licentieverlening aan uw gebruikers om voordeel te halen uit de functies van Microsoft 365-compliance. Zie de sectie [privacylabels](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection) de bijbehorende PDF- of Excel-download voor gevoelige labels.

## <a name="permissions-required-to-create-and-manage-sensitivity-labels"></a>Gevoeligheidslabels maken en beheren

Leden van uw nalevingsteam die bewaarbeleidsregels en bewaarlabels maken en beheren, hebben machtigingen nodig voor het compliancecentrum. 

Standaard heeft de tenantbeheerder (globale beheerder) toegang tot deze locatie en kan deze **compliance officers** en andere personen toegang verlenen zonder hen alle machtigingen van een tenantbeheerder te geven. Als u machtigingen wilt verlenen voor dit beperkte beheer, raden we u aan gebruikers toe te voegen aan de **beheerdersrolgroep** **Compliancebeheerder**. 

U kunt ook de standaardrollen gebruiken. U kunt ook een nieuwe rollengroep maken en **Vertrouwelijkheidslabelbeheerder** of **Organisatieconfiguratie** rollen toevoegen aan deze groep. Als u een alleen-lezenrol nodig hebt, **De lezer voor gevoeligheidslabels**. 

Zie [Gebruikers toegang geven tot het Beveiligings- en compliancecentrum](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md) voor instructies om gebruikers aan rolgroepen toe te voegen en rollen toe te wijzen.

Deze machtigingen zijn alleen vereist om gevoeligheidslabels en het labelbeleid te maken en configureren. Ze zijn niet vereist om de labels in apps of services toe te passen. Als er extra machtigingen nodig zijn voor specifieke configuraties die betrekking hebben op gevoeligheidslabels, worden die machtigingen vermeld in de desbetreffende documentatie-instructies.

## <a name="deployment-strategy-for-sensitivity-labels"></a>Implementatiestrategie voor gevoeligheidslabels
Een succesvolle strategie voor de implementatie van gevoeligheidslabels voor een organisatie is het maken van een virtueel team dat de zakelijke en technische vereisten identificeert en beheert, test van concept, interne controlepunten en goedkeuringen, en de uiteindelijke implementatie voor de productieomgeving.

Aan de hand van de tabel in het volgende gedeelte wordt u aangeraden de belangrijkste een of twee scenario's te identificeren die zijn toe te passen op de meest impactvolle bedrijfsvereisten. Nadat deze scenario's zijn geïmplementeerd, gaat u terug naar de lijst om vast te stellen wat de volgende een of twee prioriteiten zijn voor implementatie.

In de downloadbare richtlijnen voor preventie van gegevensverlies en implementatieversnelling voor Microsoft Information Protection vindt u aanvullende algemene richtlijnen voor implementatie. Zie voor meer informatie het blogbericht [Microsoft 365 Information Protection and Compliance Deployment Acceleration Guides](https://techcommunity.microsoft.com/t5/microsoft-security-and/microsoft-365-information-protection-and-compliance-deployment/ba-p/2076404).

## <a name="common-scenarios-for-sensitivity-labels"></a>Gebruikelijke scenario's voor vertrouwelijkheidslabels

Voor alle scenario's moet u [Gevoeligheidslabels en hun beleid maken en configureren](create-sensitivity-labels.md).

|Ik wil het volgende doen|Documentatie|
|----------------|---------------|
|Beheer gevoeligheidslabels voor Office-apps, zodat inhoud wordt gelabeld terwijl deze wordt gemaakt. Dit omvat ondersteuning voor handmatige labeling op alle platforms |[Vertrouwelijkheidslabels in Office-apps beheren](sensitivity-labels-office-apps.md)|
|Gebruikers in staat stellen bestanden van Windows-computers te labelen en te beveiligen met Office-apps, Verkenner en PowerShell|[Geïntegreerde Azure Information Protection-labelclient en -scanner:](/azure/information-protection/rms-client/aip-clientv2)|
|Documenten en e-mailberichten versleutelen met gevoeligheidslabels en beperken wie toegang heeft tot die inhoud en hoe deze kan worden gebruikt |[Toegang tot inhoud beperken door versleuteling toe te passen met vertrouwelijkheidslabels](encryption-sensitivity-labels.md)|
|Schakel gevoeligheidslabels in voor Office op het web, met ondersteuning voor coauthoring, eDiscovery, preventie van gegevensverlies, zoeken, zelfs wanneer documenten zijn versleuteld | [Vertrouwelijkheidslabels inschakelen voor Office-bestanden in SharePoint en OneDrive](sensitivity-labels-sharepoint-onedrive-files.md)
|Co authoring en automatisch opslaan gebruiken in Office-bureaublad-apps wanneer documenten zijn versleuteld | [Cocreatie inschakelen voor bestanden die zijn versleuteld met gevoeligheidslabels](sensitivity-labels-coauthoring.md)
|Automatisch gevoeligheidslabels toepassen op uw documenten en e-mails | [Een vertrouwelijkheidslabel automatisch toepassen op inhoud](apply-sensitivity-label-automatically.md)|
|Zie Gevoeligheidslabels gebruiken om inhoud te beveiligen in Microsoft Teams, Office 365-groepen en SharePoint-sites voor meer informatie. |[Vertrouwelijkheidslabels gebruiken met Microsoft Teams, Microsoft 365 Groepen en SharePoint-sites](sensitivity-labels-teams-groups-sites.md)|
|Voorkomen of waarschuwen voor het delen van bestanden of e-mailberichten met een specifiek gevoeligheidslabel |[Vertrouwelijkheidslabels gebruiken als voorwaarden in DLP-beleid (preview)](dlp-sensitivity-label-as-condition.md) |
|Bestanden ontdekken, labelen en beveiligen die zijn opgeslagen in on-premises gegevensopslag |[De Azure Information Protection-scanner implementeren om bestanden automatisch te classificeren en te beveiligen](/azure/information-protection/deploy-aip-scanner)|
|Bestanden ontdekken, labelen en beveiligen die zijn opgeslagen in de cloud gegevensopslag|[Ontdek, classificeer, label en bescherm gereguleeerde en vertrouwelijke gegevens die zijn opgeslagen in de cloud](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|Labels toepassen en weergeven in Power BI en gegevens beveiligen wanneer deze buiten de service worden opgeslagen|[Gevoeligheidslabels in Power BI](/power-bi/admin/service-security-sensitivity-label-overview)|
|Controleren en begrijpen hoe gevoeligheidslabels worden gebruikt in mijn organisatie|[Ken uw gegevens - meer informatie over gegevensclassificatie](data-classification-overview.md) <br /><br /> [Aan de slag met gegevensclassificatie](data-classification-overview.md).|
|Vertrouwelijkheidslabels uitbreiden naar apps en services van derden.|[Microsoft Information Protection SDK](/information-protection/develop/overview#microsoft-information-protection-sdk)|
|De gevoeligheidslabels uitbreiden voor inhoud in Azure Blob Storage, Azure-bestanden, Azure Data Lake Storage Generatie1 en Azure Data Lake Storage Generatie12|[Automatisch uw inhoud labelen in Azure Purview](/azure/purview/create-sensitivity-label) |


## <a name="end-user-documentation-for-sensitivity-labels"></a>Documentatie voor eindgebruikers voor gevoeligheidslabels

De meest effectieve documentatie voor eindgebruikers bestaat uit aangepaste begeleiding en instructies voor de namen en configuraties van labels die u kiest. U kunt de instelling voor labelbeleid **Geef gebruikers een koppeling naar een aangepaste Help-pagina** gebruiken om een interne koppeling voor deze documentatie op te geven. Gebruikers kunnen deze vervolgens eenvoudig openen via de knop **Vertrouwelijkheid**:

- Voor ingebouwde labeling: menuoptie **Meer informatie**.
- Voor de geïntegreerde Azure Information Protection-labelclient: menuoptie **Help en Feedback** > koppeling **Meer informatie** in het dialoogvenster Microsoft Azure Information Protection.

Bekijk, om u te helpen bij het bieden van aangepaste documentatie, de volgende pagina en downloads die u kunt gebruiken voor het trainen van gebruikers: [Eindgebruikerstraining voor Retentielabels](https://microsoft.github.io/ComplianceCxE/enduser/sensitivity/). 

U kunt ook de volgende bronnen gebruiken voor basisinstructies:

- [Gevoeligheidslabels toepassen op uw documenten en e-mail in Office](https://support.microsoft.com/nl-NL/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
    - [Bekende problemen met vertrouwelijkheidslabels in Office](https://support.microsoft.com/nl-NL/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [Vertrouwelijkheidslabels automatisch toepassen op of aanbevelen voor uw bestanden en e-mailberichten in Office](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)
    - [Bekende problemen met het automatisch toepassen of aanbevelen van vertrouwelijkheidslabels](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)

- [Geïntegreerde Azure Information Protection-labelhandleiding](/azure/information-protection/rms-client/clientv2-user-guide)

Als uw gevoeligheidslabels versleuteling toepassen op PDF-documenten, kunnen deze documenten worden geopend met Microsoft Edge op Windows of Mac. Zie voor meer informatie en alternatieve lezers [Welke PDF-lezers worden ondersteund voor beveiligde PDF-bestanden?](/azure/information-protection/rms-client/protected-pdf-readers#viewing-protected-pdfs-in-microsoft-edge-on-windows-or-mac)
