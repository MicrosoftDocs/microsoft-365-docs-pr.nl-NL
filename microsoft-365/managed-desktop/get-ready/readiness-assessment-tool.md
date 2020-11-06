---
title: Hulpmiddel voor gereedheids beoordeling
description: Een beschrijving van de controles die het programma uitvoert en de betekenis van de resultaten
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 347266f71dada3de1bbd9b1434cb1e6628249147
ms.sourcegitcommit: 24826e1b61e7aace12fc9e8ae84ae3e760658b50
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/06/2020
ms.locfileid: "48931922"
---
# <a name="readiness-assessment-tool"></a>Hulpmiddel voor gereedheids beoordeling

Voor de soepelste ervaring wanneer u zich registreert bij Microsoft Managed Desktop, zijn er een aantal instellingen en andere parameters die u moet instellen voor de periode. Met dit hulpprogramma kunt u deze instellingen controleren en gedetailleerde stappen ontvangen voor het oplossen van de juiste instellingen.

Met de Tool controleert u de instellingen in Microsoft Endpoint Manager (specifiek, Microsoft intune), Azure Active Directory (Azure AD) en Microsoft 365 om te controleren of deze geschikt zijn voor Microsoft beheerde bureaublad. Microsoft Managed Desktop houdt de gegevens van deze controles gedurende 12 maanden na de laatste keer dat u een cheque uitvoert in uw Azure AD-organisatie (Tenant). Na 12 maanden behoudt Skype het in de aangegeven vorm.  U kunt ervoor kiezen de gegevens te verwijderen die we verzamelen.

Iedereen met een minimum van de beheerder van intune heeft de mogelijkheid dit hulpprogramma uit te voeren, maar twee van de controles ([certificaat connectors](readiness-assessment-fix.md#certificate-connectors) en [Meervoudige verificatie](readiness-assessment-fix.md#multi-factor-authentication) vereisen extra machtigingen).
 
Het beoordelingsprogramma controleert de volgende items:

## <a name="microsoft-intune-settings"></a>Microsoft intune-instellingen

|Cheque  |Beschrijving  |
|---------|---------|
|Auto Pilot-implementatie profiel     | Hiermee wordt gecontroleerd of de toewijzing van het profiel voor automatische prototype-implementatie niet van toepassing is op alle apparaten (het profiel moet *niet* worden toegewezen aan een beheerde bureaubladtoepassing voor Microsoft-apparaten.)       |
|Certificaat verbindingslijnen     | Controleert de status van de certificaat connectors om ervoor te zorgen dat deze actief zijn   |
|Voorwaardelijke toegang     | Hiermee wordt gecontroleerd of het beleid voor voorwaardelijke toegang niet aan alle gebruikers wordt toegewezen (het beleid voor voorwaardelijke toegang mag *niet* worden toegewezen aan de beheerde bureaublad service-accounts van Microsoft).    |
|Nalevingsbeleid voor apparaten     | Hiermee wordt gecontroleerd of het intune-nalevingsbeleid niet is toegewezen aan alle gebruikers (de beleidsregels dienen *niet* te worden toegewezen aan een beheerde bureaubladtoepassing van Microsoft).    |
|Configuratieprofielen voor apparaten     | Bevestigt dat configuratieprofielen niet zijn toegewezen aan alle gebruikers of alle apparaten (configuratieprofielen dienen *niet* te worden toegewezen aan een beheerde bureaubladtoepassing voor Microsoft-apparaten.)     |
|Beperkingen voor apparaattype     | Controleert of Windows 10-apparaten in uw organisatie kunnen worden ingeschreven voor intune        |
|Pagina met inschrijvings status     | Bevestigt dat de pagina inschrijvings status niet is ingeschakeld      |
|InTune-registratie     | Controleert of Windows 10-apparaten in uw Azure AD-organisatie automatisch zijn ingeschreven in intune         |
|Microsoft Store voor Bedrijven     | Hiermee wordt bevestigd dat Microsoft Store voor bedrijven is ingeschakeld en gesynchroniseerd met intune        |
|Meervoudige verificatie | Controleert of multi-factor Authentication niet is toegepast op beheerde bureaublad serviceaccounts van Microsoft.
|PowerShell-scripts     | Hiermee wordt gecontroleerd of Windows PowerShell-scripts *niet* zijn toegewezen op de manier waarop door Microsoft beheerde bureaublad apparaten wordt gestreefd    |
|Regio     | Hiermee wordt gecontroleerd of uw regio wordt ondersteund door Microsoft Managed Desktop        |
|Basislijnen voor beveiliging     | Hiermee wordt gecontroleerd of het profiel van de basislijn voor *beveiliging niet alle* gebruikers of alle apparaten heeft.       |
|Windows-apps     | Controleren welke apps u wilt toewijzen aan Microsoft beheerde bureaublad apparaten      |
|Windows Hello voor Bedrijven     | Controleert of Windows hello voor bedrijven is ingeschakeld        |
|Windows 10 update ring     | Hiermee wordt gecontroleerd of het beleid Windows 10 update-uittune niet alle gebruikers of alle apparaten is, (het beleid *dient geen* Microsoft-bureaublad apparaten te bestemmen.)     |


## <a name="azure-active-directory-settings"></a>Azure Active Directory-instellingen

|Cheque  |Beschrijving  |
|---------|---------|
|Ad hoc-abonnementen voor Enterprise State roaming     | Adviseert te controleren of een instelling die (indien ingesteld op ' onwaar ') wordt gebruikt om te voorkomen dat roaming via een Enterprise-versie goed werkt  |
|Enterprise State Roaming     | Adviseren hoe u kunt controleren of het zwerven van ondernemings Staten is ingeschakeld       |
|Licenties     | Controleert of u de benodigde [licenties](prerequisites.md#more-about-licenses) hebt verkregen         |
|Meervoudige verificatie     | Hiermee wordt gecontroleerd of multi-factor Authentication niet wordt toegepast op alle gebruikers (meervoudige verificatie mag niet per ongeluk worden toegepast op Microsoft Managed Desktop service-accounts).|
|Namen van beveiligingsaccounts   | Hiermee wordt gecontroleerd of gebruikersnamen geen conflict opleveren met de namen van de gebruikers die door Microsoft worden beheerd hun eigen gebruik        |
|Rollen van beveiligingsbeheerders     | Controleert of gebruikers met beveiligings lezer, beveiligings operator of algemene lezers rollen aan deze rollen zijn toegewezen in Microsoft Defender voor eindpunt         |
|Standaardinstellingen voor beveiliging | Controleert of in de Azure AD-organisatie beveiligingsstandaarden zijn ingeschakeld in azure Active Directory |
|Self-service voor wachtwoordherstel     | Bevestigt dat de selfservice voor wachtwoordherstel is ingeschakeld        |
|Standaard gebruikersrol     | Controleert of gebruikers standaardgebruikers zijn en geen lokale beheerdersrechten hebben         |


## <a name="microsoft-365-apps-for-enterprise-settings"></a>Microsoft 365-apps voor Enterprise Settings

|Cheque  |Beschrijving  |
|---------|---------|
|OneDrive voor Bedrijven     | Controleert of in OneDrive voor bedrijven niet-ondersteunde instellingen worden gebruikt.        |


Voor elke controle wordt in het hulpmiddel een van de vier mogelijke resultaten weergegeven:


|Resultaat  |Betekenis  |
|---------|---------|
|Gereedgemaakt     | U hoeft niets te doen voordat u de registratie voltooit.        |
|Adviser    | Volg de stappen in het hulpprogramma voor een optimale ervaring met inschrijving en voor gebruikers. U *kunt* de inschrijving voltooien, maar u moet deze problemen oplossen voordat u uw eerste apparaat implementeert.        |
|Niet gereed | De *registratie mislukt* als u deze problemen niet oplost. Voer de stappen in het hulpprogramma uit om ze op te lossen.        |
|Error | De rol van Azure Active Director (AD) die u gebruikt, heeft onvoldoende machtigingen om deze controle uit te voeren. |
