---
title: Hulpprogramma's voor beoordeling van gereedheid
description: Hier worden de twee hulpprogramma's, de controles en de betekenis van de resultaten uitgelegd
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1a00f7d5fb37cc9eea3f9454d473703084960864
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142931"
---
# <a name="readiness-assessment-tools"></a>Hulpprogramma's voor beoordeling van gereedheid

Voor een zo soepel mogelijke ervaring bij het registreren bij Microsoft Managed Desktop zijn er instellingen en andere parameters die u van tevoren moet instellen, en bepaalde apparaat- en netwerkvereisten om te voldoen. Eén hulpprogramma, dat toegankelijk is via de portal Beheerd bureaubladbeheer van Microsoft, controleert beheerinstellingen. Een ander hulpprogramma, dat kan worden gedownload, controleert de vereisten voor afzonderlijke apparaten en de netwerkinstellingen. U kunt deze hulpprogramma's gebruiken om deze instellingen te controleren en gedetailleerde stappen te ontvangen voor het oplossen van fouten die niet juist zijn.

## <a name="downloadable-readiness-assessment-checker-for-devices-and-network"></a>Downloadbare gereedheidscontrole voor apparaten en netwerk

Zie De evaluatiecontrole voor downloadbare gereedheid voor meer informatie over het gebruik van de evaluatiecontrole voor [downloadbare gereedheid.](readiness-assessment-downloadable.md)

## <a name="online-readiness-assessment-tool-for-management-settings"></a>Hulpprogramma voor online gereedheidsbeoordeling voor beheerinstellingen

Het onlinehulpprogramma controleert de instellingen in Microsoft Endpoint Manager (met name Microsoft Intune), Azure Active Directory (Azure AD) en Microsoft 365 om ervoor te zorgen dat deze werken met het beheerde bureaublad van Microsoft. Het beheerde bureaublad van Microsoft behoudt de gegevens die aan deze controles zijn gekoppeld, 12 maanden na de laatste keer dat u een controle hebt uitgevoerd in uw Azure AD-organisatie (tenant). Na 12 maanden bewaren we het in gedeïdentificeerde vorm. U kunt ervoor kiezen om de gegevens te verwijderen die we verzamelen.

Iedereen met ten minste de rol Globale lezer of Intune-beheerder kan dit hulpprogramma uitvoeren, maar twee van de controles[(beleid](readiness-assessment-fix.md#conditional-access-policies) voor voorwaardelijke toegang en [Meervoudige](readiness-assessment-fix.md#multifactor-authentication) verificatie vereisen extra machtigingen).
 
Het evaluatieprogramma controleert deze items:

## <a name="microsoft-intune-settings"></a>Microsoft Intune-instellingen

|Cheque  |Beschrijving  |
|---------|---------|
|Autopilot-implementatieprofiel     | Controleert of toewijzing van het Autopilot-implementatieprofiel niet van  toepassing is op alle apparaten (Het profiel mag niet worden toegewezen aan beheerde Desktop-apparaten van Microsoft.)       |
|Connectors voor certificaten     | Controleert de status van certificaatconnectoren om na te gaan of ze actief zijn   |
|Voorwaardelijke toegang     | Controleert of beleidsregels voor voorwaardelijke toegang niet aan  alle gebruikers zijn toegewezen (beleidsregels voor voorwaardelijke toegang moeten niet worden toegewezen aan serviceaccounts met het beheerde bureaublad van Microsoft.)    |
|Beleid voor apparaat compliance     | Hiermee wordt gecontroleerd of Intune-nalevingsbeleid niet aan  alle gebruikers is toegewezen (het beleid mag niet worden toegewezen aan beheerde bureaubladapparaten van Microsoft.)    |
|Apparaatconfiguratieprofielen     | Bevestigt dat configuratieprofielen niet zijn toegewezen aan alle gebruikers  of alle apparaten (Configuratieprofielen moeten niet worden toegewezen aan beheerde Desktop-apparaten van Microsoft.)     |
|Beperkingen voor apparaattype     | Hiermee wordt gecontroleerd of Windows 10-apparaten in uw organisatie zijn toegestaan zich te registreren bij Intune        |
|Pagina Inschrijvingsstatus     | Controleert of registratiestatuspagina niet is ingeschakeld      |
|Intune-inschrijving     | Controleert of Windows 10-apparaten in uw Azure AD-organisatie automatisch zijn geregistreerd in Intune         |
|Microsoft Store voor Bedrijven     | Bevestigt dat Microsoft Store voor Bedrijven is ingeschakeld en gesynchroniseerd met Intune        |
|Meervoudige verificatie | Controleert of meervoudige verificatie niet wordt toegepast op accounts van de Microsoft Managed Desktop-service.
|PowerShell-scripts     | Hiermee wordt gecontroleerd of  Windows PowerShell-scripts niet zijn toegewezen op een manier die is gericht op beheerde bureaubladapparaten van Microsoft    |
|Regio     | Hiermee wordt gecontroleerd of uw regio wordt ondersteund door het beheerde bureaublad van Microsoft        |
|Beveiligingsbasislijnen     | Hiermee wordt gecontroleerd of het basislijnprofiel van de beveiliging  niet op alle gebruikers of alle apparaten is gericht (het beveiligingsbasislijnbeleid is niet gericht op beheerde bureaubladapparaten van Microsoft).       |
|Windows-apps     | Controleren welke apps u wilt toewijzen aan beheerde Desktop-apparaten van Microsoft      |
|Windows Hello voor Bedrijven     | Hiermee wordt gecontroleerd of Windows Hello voor Bedrijven is ingeschakeld        |
|Update-ring voor Windows 10     | Hiermee wordt gecontroleerd of het 'Windows 10-updateringsbeleid' van Intune niet  op alle gebruikers of alle apparaten is gericht (het beleid is niet van toepassing op beheerde bureaubladapparaten van Microsoft.)     |


## <a name="azure-active-directory-settings"></a>Azure Active Directory-instellingen

|Cheque  |Beschrijving  |
|---------|---------|
|'Ad hoc'-abonnementen voor Enterprise State Roaming     | Adviseert hoe u een instelling kunt controleren die (indien ingesteld op 'onwaar') kan verhinderen dat Enterprise State Roaming correct werkt  |
|Enterprise State Roaming     | Adviseert hoe u kunt controleren of Enterprise State Roaming is ingeschakeld       |
|Licenties     | Controleert of u de benodigde [licenties hebt verkregen](prerequisites.md#more-about-licenses)         |
|Meervoudige verificatie     | Hiermee wordt gecontroleerd of meervoudige verificatie niet op alle gebruikers wordt toegepast (Multi-Factor Authentication mag niet per ongeluk worden toegepast op accounts van de Microsoft Managed Desktop-service).|
|Namen van beveiligingsaccounts   | Hiermee wordt gecontroleerd of er geen gebruikersnamen conflicteren met de namen die door Microsoft Beheerd bureaublad zijn voor eigen gebruik        |
|Rollen van beveiligingsbeheerders     | Bevestigt dat aan gebruikers met een beveiligingslezer, beveiligingsoperator of globale lezer deze rollen zijn toegewezen in Microsoft Defender voor eindpunt         |
|Standaardinstellingen voor beveiliging | Hiermee wordt gecontroleerd of voor uw Azure AD-organisatie beveiligingsinstellingen zijn ingeschakeld in Azure Active Directory |
|Self-service voor wachtwoordherstel     | Bevestigt dat selfservice voor wachtwoord opnieuw instellen is ingeschakeld        |
|Standaardgebruikersrol     | Controleert of gebruikers standaardgebruikers zijn en geen lokale beheerdersrechten hebben         |


## <a name="microsoft-365-apps-for-enterprise-settings"></a>Microsoft 365-apps voor bedrijfsinstellingen

|Cheque  |Beschrijving  |
|---------|---------|
|OneDrive voor Bedrijven     | Hiermee wordt gecontroleerd of OneDrive voor Bedrijven niet-ondersteunde instellingen gebruikt.        |


Bij elke controle wordt een van de vier mogelijke resultaten door het hulpmiddel rapporteren:


|Resultaat  |Betekenis  |
|---------|---------|
|Klaar     | U hoeft niets te doen voordat u de inschrijving voltooit.        |
|Advies    | Volg de stappen in het hulpprogramma voor een optimaal gebruik van de inschrijving en voor gebruikers. U *kunt* de inschrijving voltooien, maar u moet deze problemen oplossen voordat u uw eerste apparaat implementeert.        |
|Nog niet gereed | *De inschrijving mislukt als* u deze problemen niet op kunt lossen. Volg de stappen in het hulpprogramma om ze op te lossen.        |
|Error | De Ad-rol (Azure Active Director) die u gebruikt, heeft onvoldoende machtigingen om deze controle uit te voeren. |

## <a name="after-enrollment"></a>Na inschrijving

Nadat u zich hebt ingeschreven bij Microsoft Managed Desktop, vergeet dan niet om terug te gaan en bepaalde Intune- en Azure AD-instellingen aan te passen. Zie Instellingen aanpassen [na de inschrijving voor meer informatie.](../get-started/conditional-access.md)
