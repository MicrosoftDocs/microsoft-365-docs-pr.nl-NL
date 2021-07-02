---
title: Microsoft Information Protection in Microsoft 365
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.collection:
- m365solution-mip
- m365initiative-compliance
recommendations: false
description: Implementeert Microsoft Information Protection (MIP) om gevoelige informatie te beveiligen waar deze zich ook bevindt of naartoe reist.
ms.openlocfilehash: bca6ce0dabaa9db2444da374b5d3ee166154fdd8
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226537"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft Information Protection in Microsoft 365

>*[Licenties voor Microsoft 365 Security & Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Implementeert Microsoft Information Protection (MIP) om gevoelige informatie te ontdekken, classificeren en beveiligen waar deze zich ook bevindt of naartoe reist.

De MIP-mogelijkheden zijn opgenomen in Microsoft 365 Compliance en bieden u de hulpprogramma's om [uw gegevens te kennen](#know-your-data), [uw gegevens te beschermen](#protect-your-data)en [gegevensverlies te voorkomen](#prevent-data-loss).

![Afbeelding van hoe MIP u helpt bij het ontdekken, classificeren en beveiligen van gevoelige gegevens](../media/powered-by-intelligent-platform.png)

Voor meer informatie over het beheer van uw gegevens, gaat u naar [Microsoft Information Governance in Microsoft 365](manage-Information-governance.md).

## <a name="know-your-data"></a>Uw gegevens kennen

> [!NOTE]
> Zie [Uw inhoud automatisch labelen in Azure Purview](/azure/purview/create-sensitivity-label) voor informatie over het automatisch classificeren en toepassen van een label in Azure Purview, momenteel in preview.

Gebruik de volgende mogelijkheden om inzicht te krijgen in uw gegevensomgeving en belangrijke gegevens te identificeren in uw hybride omgeving:

|Mogelijkheid|Welke problemen worden ermee opgelost?|Aan de slag|
|:------|:------------|:--------------------|
|[Typen gevoelige informatie](sensitive-information-type-learn-about.md)| Identificeert gevoelige gegevens met behulp van ingebouwde of aangepaste reguliere expressies of een functie. Ondersteunend bewijs zijn onder meer trefwoorden, betrouwbaarheidsniveaus en nabijheid.| [Een ingebouwd type gevoelige informatie aanpassen](customize-a-built-in-sensitive-information-type.md)|
|[Trainbare classificaties](classifier-learn-about.md)| Identificeert gevoelige gegevens aan de hand van voorbeelden van de gegevens waarin u geïnteresseerd bent in plaats van elementen in het item te identificeren (patroonovereenkomst). U kunt ingebouwde classificaties gebruiken of een classificatie trainen met uw eigen inhoud.| [Aan de slag met trainbare classificaties](classifier-get-started-with.md) |
|[Gegevensclassificatie](data-classification-overview.md) | Een grafische identificatie van items in uw organisatie met een vertrouwelijkheidslabel, een retentielabel of items die vertrouwelijk zijn. U kunt deze informatie ook gebruiken om inzicht te krijgen in de acties die uw gebruikers uitvoeren op deze items. | [Aan de slag met de inhoudsverkenner](data-classification-content-explorer.md) <p> [Aan de slag met de activiteitenverkenner](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>Uw gegevens beveiligen

Gebruik de volgende mogelijkheden om flexibele beveiligingsacties toe te passen zoals versleuteling, toegangsbeperkingen en visuele markeringen:

|Mogelijkheid|Welke problemen worden ermee opgelost?|Aan de slag|
|:------|:------------|---------------------|
|[Gevoeligheidslabels](sensitivity-labels.md)| Eén oplossing voor apps, services en apparaten om uw gegevens te labelen en te beschermen wanneer ze binnen en buiten uw organisatie reizen. <p> Voorbeeldscenario's: <p> [Vertrouwelijkheidslabels voor Office-apps beheren](sensitivity-labels-office-apps.md) <p> [Documenten en e-mailberichten versleutelen](encryption-sensitivity-labels.md) <p> [Labels toepassen en weergeven in Power BI](/power-bi/admin/service-security-apply-data-sensitivity-labels) <p> Zie de documentatie Aan de slag voor een uitgebreide lijst met scenario's voor vertrouwelijkheidslabels.|[Aan de slag met vertrouwelijkheidslabels](get-started-with-sensitivity-labels.md) |
|[Geïntegreerde Azure Information Protection-labelclient](/azure/information-protection/rms-client/aip-clientv2)| Voor Windows-computers worden de vertrouwelijkheidslabels uitgebreid met extra functies en functionaliteit, waaronde alle bestandstypen labelen en beveiligen vanuit Bestandenverkenner en PowerShell <p> Voorbeeld van aanvullende functies: [aangepaste configuraties voor de geïntegreerde Azure Information Protection-labelclient](/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Beheerdershandleiding voor de geïntegreerde Azure Information Protection-labelclient](/azure/information-protection/rms-client/clientv2-admin-guide)|
|[Dubbele sleutelcodering](double-key-encryption.md)| Onder alle omstandigheden kan alleen uw organisatie beveiligde inhoud ontsleutelen. Om te voldoen aan wettelijke vereisten moet u versleutelingssleutels binnen een geografisch begrensde locatie bijhouden. | [Dubbele sleutelcodering implementeren](double-key-encryption.md#deploy-dke)|
|[Office 365-berichtversleuteling (OME)](ome.md)| Versleutelt e-mailberichten en bijgevoegde documenten die naar elke gebruiker op elk apparaat zijn verzonden, zodat enkel geautoriseerde ontvangers de informatie kunnen lezen die per e-mail is verzonden. <p> Voorbeeldscenario: [E-mailberichten intrekken die zijn versleuteld met Advanced Message Encryption](revoke-ome-encrypted-mail.md) | [De nieuwe mogelijkheden van Message Encryption instellen](set-up-new-message-encryption-capabilities.md)|
|[Serviceversleuteling met klantsleutel](customer-key-overview.md) | Beveiligt tegen het weergeven van gegevens door onbevoegde systemen of medewerkers en vormt een aanvulling op BitLocker-schijfversleuteling in Microsoft-datacenters. | [Klantsleutel instellen voor Office 365](customer-key-set-up.md)|
|[SharePoint IRM (Information Rights Management)](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|Beveiligt SharePoint-lijsten en -bibliotheken, zodat het gedownloade bestand wordt beveiligd wanneer een gebruiker een document uitcheckt, zodat alleen geautoriseerde personen het bestand kunnen bekijken en gebruiken volgens de beleidsregels die u opgeeft. | [IRM (Information Rights Management) instellen in het SharePoint-beheercentrum](set-up-irm-in-sp-admin-center.md)|
[Rights Management-connector](/azure/information-protection/deploy-rms-connector) |Enkel beveiliging voor bestaande on-premises implementaties die gebruikmaken van Exchange of SharePoint Server, of bestandsservers met Windows Server en infrastructuur voor bestandsclassificatie. | [Stappen voor de implementatie van de RMS-connector](/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Geïntegreerde Azure Information Protection-labelclient](/azure/information-protection/deploy-aip-scanner)| Ontdekt, labelt en beschermt vertrouwelijke informatie die zich op on-premises gegevensopslag bevindt. | [Configureren en installeren van de geïntegreerde labelscanner van Azure Information Protection](/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)| Ontdekt, labelt en beschermt vertrouwelijke informatie die zich op gegevensopslag in de cloud bevindt. | [Ontdek, classificeer, label en bescherm gereguleeerde en vertrouwelijke gegevens die zijn opgeslagen in de cloud](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[Microsoft Information Protection SDK](/information-protection/develop/overview#microsoft-information-protection-sdk)|Breidt vertrouwelijkheidslabels uit naar apps en services van derden. <p> Voorbeeldscenario: [een gevoeligheidslabel instellen en gebruiken (C++)](/information-protection/develop/quick-file-set-get-label-cpp) |[Installatie en configuratie van Microsoft Information Protection (MIP) SDK](/information-protection/develop/setup-configure-mip)|


## <a name="prevent-data-loss"></a>Verlies van gegevens voorkomen

Gebruik de volgende mogelijkheden om te voorkomen dat vertrouwelijke informatie per ongeluk wordt gedeeld met iemand:


|Mogelijkheid|Welke problemen worden ermee opgelost?|Aan de slag|
|:------|:------------|:---------------------|
|[Preventie van gegevensverlies](dlp-learn-about-dlp.md)| Dit voorkomt het onbedoeld delen van vertrouwelijke items. | [Aan de slag met het standaard DLP-beleid](get-started-with-the-default-dlp-policy.md)|
|[Preventie van gegevensverlies voor eindpunten](endpoint-dlp-learn-about.md)| Breidt de DLP-mogelijkheden uit naar items die worden gebruikt en gedeeld op computers met Windows 10. | [Aan de slag met Eindpunt-DLP (gegevensverlies voor eindpunten)](endpoint-dlp-getting-started.md)|
|[Microsoft-compliance-uitbreiding](dlp-chrome-learn-about.md) | Hiermee worden de DLP-mogelijkheden naar de Chrome-browser uitgebreid | [Aan de slag met de Microsoft-compliance-extensie](dlp-chrome-get-started.md)|
|[Microsoft 365 preventie van gegevensverlies on-premises scanner (preview)](dlp-on-premises-scanner-learn.md)|Breidt het DLP-toezicht op bestandsactiviteiten en beschermende maatregelen voor die bestanden uit tot on-premises gedeelde bestanden en SharePoint-mappen en documentbibliotheken.|[Aan de slag met de Microsoft 365-preventie van gegevensverlies on-premises scanner (preview)](dlp-on-premises-scanner-get-started.md)|
|[Vertrouwelijke informatie in chat- en kanaalberichten in Microsoft Teams beveiligen](dlp-microsoft-teams.md) | Breidt een deel van de DLP-functionaliteit uit naar de chat- en kanaalberichten in Teams | [Meer informatie over het standaard preventiebeleid voor gegevensverlies in Microsoft Teams (preview)](dlp-teams-default-policy.md)|

## <a name="licensing-requirements"></a>Licentievereisten

Licentievereisten voor MIP zijn afhankelijk van de scenario's en functies die u gebruikt, in plaats van licentievereisten in te stellen voor elke functie die op deze pagina wordt vermeld. Als u meer wilt weten over uw licentievereisten en -opties, bekijkt u de secties [Informatiebeheer](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection) in de Microsoft 365-licentiedocumentatie en downloadt u het bijbehorende PDF- of Excel-bestand.
