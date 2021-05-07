---
title: Door de klant beheerde versleutelingsfuncties
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
ms.custom:
- seo-marvel-mar2020
description: In dit artikel vindt u informatie over versleutelingstechnologieën die u kunt beheren en configureren in Microsoft 365.
ms.openlocfilehash: 6a693c512100c59eef47414fdd6eab4a2924e835
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162117"
---
# <a name="customer-managed-encryption-features"></a>Door de klant beheerde versleutelingsfuncties

Naast de versleutelingstechnologieën in Microsoft 365 beheerd door Microsoft, werkt Microsoft 365 ook met aanvullende versleutelingstechnologieën die u kunt beheren en configureren, zoals:

- [Azure Rights Management](/azure/information-protection/what-is-azure-rms)

- [Secure Multipurpose Internet Mail Extension](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)

- [Office 365-berichtversleuteling](https://products.office.com/en-us/exchange/office-365-message-encryption)

- [E-mailstroom beveiligen met een partnerorganisatie](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

Zie de beschrijvingen van de Microsoft 365 [voor meer informatie over deze technologieën.](/office365/servicedescriptions/office-365-service-descriptions-technet-library)

## <a name="azure-rights-management"></a>Azure Rights Management

[Azure Rights Management](/azure/information-protection/what-is-azure-rms) (Azure RMS) is de beveiligingstechnologie die wordt gebruikt door [Azure Information Protection](/information-protection/understand-explore/what-is-information-protection). Er wordt gebruikgemaakt van versleutelings-, identiteits- en autorisatiebeleid om uw bestanden en e-mail te beveiligen op meerdere platforms en apparaten, zoals telefoons, tablets en pc's. Informatie kan zowel binnen als buiten uw organisatie worden beveiligd, omdat de gegevens nog steeds worden beschermd. Azure RMS biedt permanente beveiliging van alle bestandstypen, beschermt bestanden overal, ondersteunt samenwerking tussen bedrijven en een groot aantal Windows en niet-Windows apparaten. Azure RMS-beveiliging kan ook [DLP-beleid (Data Loss Prevention) verbeteren.](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention) Zie How applications support the Azure Rights Management service voor meer informatie over welke toepassingen en services de Azure Rights Management service van Azure Information Protection [kunnen gebruiken.](/information-protection/understand-explore/applications-support)

Azure RMS is geïntegreerd met Microsoft 365 en beschikbaar voor alle klanten. Zie IRM configureren voor het gebruik van Azure Rights Management en [IRM (Information Rights Management)](../enterprise/activate-rms-in-microsoft-365.md)instellen in SharePoint beheercentrum als u wilt configureren Microsoft 365 Azure RMS. Als u on-premises Active Directory (AD) RMS-server (AD) gebruikt, kunt u ook IRM configureren om een [on-premises AD RMS-server](/office365/SecurityCompliance/configure-irm-to-use-an-on-premises-ad-rms-server)te gebruiken, maar we raden u ten zeerste aan om te migreren naar [Azure RMS](/azure/information-protection/migrate-from-ad-rms-to-azure-rms) om nieuwe functies te gebruiken, zoals veilige samenwerking met andere organisaties.

Wanneer u klantgegevens beschermt met Azure RMS, gebruikt Azure RMS een 2048-bits RSA-asymmetrische sleutel met sha-256-hashalgoritme voor integriteit om de gegevens te versleutelen. De symmetrische sleutel voor Office documenten en e-mail is AES 128-bits. Voor elk document of e-mailbericht dat is beveiligd door Azure RMS, wordt in Azure RMS één AES-toets (de 'inhoudstoets') gemaakt. Deze sleutel is ingesloten in het document en blijft bestaan via edities van het document. De inhoudssleutel is beveiligd met de RSA-sleutel van de organisatie (de tenantsleutel Azure Information Protection) als onderdeel van het beleid in het document en het beleid wordt ook ondertekend door de auteur van het document. Deze tenantsleutel is gebruikelijk voor alle documenten en e-mailberichten die zijn beveiligd door Azure RMS voor de organisatie en deze sleutel kan alleen worden gewijzigd door een Azure Information Protection-beheerder als de organisatie een tenantsleutel gebruikt die door de klant wordt beheerd. Zie Hoe werkt Azure RMS? voor meer informatie over de cryptografische besturingselementen die worden gebruikt door Azure [RMS. Onder de motorkap.](/information-protection/understand-explore/how-does-it-work)

In een standaard Azure RMS-implementatie genereert en beheert Microsoft de hoofdsleutel die uniek is voor elke tenant. Klanten kunnen de levenscyclus van hun hoofdsleutel in Azure RMS beheren met Azure Key Vault Services met behulp van een sleutelbeheermethode genaamd [Bring Your Own Key (BYOK)](/azure/information-protection/plan-implement-tenant-key) waarmee u uw sleutel kunt genereren in on-premises HSMs (hardwarebeveiligingsmodules) en de controle over deze sleutel kunt houden na de overdracht naar microsofts FIPS 140-2-gevalideerde HSMs op niveau 2. Toegang tot de hoofdsleutel wordt niet gegeven aan personeel, omdat de sleutels niet kunnen worden geëxporteerd of geëxtraheerd uit de HSM's die ze beveiligen. Bovendien hebt u op elk moment toegang tot een logboek in realtime met alle toegang tot de hoofdsleutel. Zie Logboekregistratie en analyse [van Azure Rights Management gebruik voor meer informatie.](/azure/information-protection/log-analyze-usage)

Azure Rights Management helpt bij het beperken van bedreigingen, zoals aftappen, man-in-the-middle-aanvallen, gegevensdiefstal en onbedoelde schendingen van beleidsregels voor het delen van organisaties. Tegelijkertijd wordt elke ongerechtvaardigde toegang van klantgegevens tijdens de overdracht of in rust door een niet-geautoriseerde gebruiker die niet over de juiste machtigingen heeft, voorkomen via beleidsregels die op die gegevens volgen, waardoor het risico wordt voorkomen dat die gegevens bewust of onbewust in verkeerde handen vallen en gegevensverlies voorkomen. Als azure RMS wordt gebruikt als onderdeel van Azure Information Protection, biedt Azure RMS ook mogelijkheden voor gegevensclassificatie en labeling, inhoudsmarkering, documenttoegangsregistratie en herroepingsmogelijkheden voor toegang. Zie Wat [is Azure Information Protection,](/information-protection/understand-explore/what-is-information-protection)Azure [Information Protection deployment roadmap](/information-protection/plan-design/deployment-roadmap)en Quick start tutorial for Azure Information Protection voor meer informatie over deze [mogelijkheden.](/information-protection/get-started/infoprotect-quick-start-tutorial)

## <a name="secure-multipurpose-internet-mail-extension"></a>Secure Multipurpose Internet Mail Extension

Secure/Multipurpose Internet Mail Extensions (S/MIME) is een standaard voor openbare sleutelversleuteling en digitale ondertekening van MIME-gegevens. S/MIME wordt gedefinieerd in RFCs 3369, 3370, 3850, 3851 en andere. Hiermee kan een gebruiker een e-mail versleutelen en een e-mailbericht digitaal ondertekenen. Een e-mailbericht dat is versleuteld met S/MIME kan alleen worden ontsleuteld door de geadresseerde van de e-mail met de persoonlijke sleutel, die alleen beschikbaar is voor die geadresseerde. De e-mailberichten kunnen dus niet worden ontsleuteld door iemand anders dan de geadresseerde van de e-mail.

[Microsoft ondersteunt S/MIME](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx). Openbare certificaten worden gedistribueerd naar de on-premises Active Directory van de klant en opgeslagen in kenmerken die kunnen worden gerepliceerd naar een Microsoft 365 tenant. De privésleutels die overeenkomen met de openbare sleutels blijven on-premises en worden nooit verzonden naar Office 365. Gebruikers kunnen e-mailberichten opstellen, versleutelen, ontsleutelen, lezen en digitaal ondertekenen tussen twee gebruikers in een organisatie met behulp van Outlook, Outlook op het web en Exchange ActiveSync clients. Zie [S/MIME-versleuteling nu in](https://blogs.office.com/2014/02/26/smime-encryption-now-in-office-365/)Office 365.

## <a name="office-365-message-encryption"></a>Office 365-berichtversleuteling

[Office 365-berichtversleuteling](https://products.office.com/exchange/office-365-message-encryption) (OME) die bovenop [Azure Information Protection](/information-protection/understand-explore/what-is-information-protection) (AIP) is gebouwd, kunt u versleutelde en met rechten beveiligde e-mail naar iedereen verzenden. OME beperkt bedreigingen zoals aftappen en man-in-the-middle-aanvallen en andere bedreigingen, zoals onrechtmatige toegang tot gegevens door een niet-geautoriseerde gebruiker die niet over de juiste machtigingen heeft. We hebben investeringen gedaan die u een eenvoudigere, intuïtievere, veilige e-mailervaring bieden die is gebaseerd op Azure Information Protection. U kunt berichten die zijn verzonden vanuit Microsoft 365 naar iedereen binnen of buiten uw organisatie beveiligen. Deze berichten kunnen worden bekeken in een diverse set e-mailcl clients met elke identiteit, waaronder Azure Active Directory, Microsoft-account en Google-id's. Zie voor meer informatie over hoe uw organisatie versleutelde berichten kan gebruiken [Office 365-berichtversleuteling.](./ome.md)

## <a name="transport-layer-security"></a>Beveiliging van transportlagen

Als u veilige communicatie met een partner wilt garanderen, kunt u binnenkomende en uitgaande connectors gebruiken om beveiliging en berichtintegriteit te bieden. U kunt gedwongen binnenkomende en uitgaande TLS op elke connector configureren met behulp van een certificaat. Als u een versleuteld SMTP-kanaal gebruikt, kunt u voorkomen dat gegevens worden gestolen via een man-in-the-middle-aanval. Zie How Exchange Online uses TLS to secure email connections (Hoe wordt TLS gebruikt om e-mailverbindingen [te beveiligen)](./exchange-online-uses-tls-to-secure-email-connections.md)voor meer informatie.

## <a name="domain-keys-identified-mail"></a>Domeinsleutels geïdentificeerde e-mail

Exchange Online Protection (EOP) en Exchange Online ondersteuning voor inkomende validatie van DKIM-berichten (Domain Keys Identified Mail). DKIM is een methode om te valideren dat een bericht is verzonden vanuit het domein waar het bericht vandaan komt en dat het niet is vervalst door iemand anders. Er wordt een e-mailbericht aan de organisatie verbonden die verantwoordelijk is voor het verzenden van het bericht en maakt deel uit van een groter paradigma van e-mailversleuteling. Zie voor meer informatie over de drie onderdelen van dit paradigma:

- [SPF instellen om adresvervalsing te helpen voorkomen](/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)

- [DKIM gebruiken om uitgaande e-mail te valideren die wordt verzonden vanuit uw aangepaste domein](/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)

- [DMARC gebruiken om e-mail te valideren](/office365/SecurityCompliance/use-dmarc-to-validate-email)