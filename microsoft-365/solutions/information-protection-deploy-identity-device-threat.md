---
title: Identiteits-, apparaat- en bedreigingsbescherming gebruiken voor regelgeving voor gegevensprivacy
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
ms.custom: ''
description: Voorkom inbreuken op persoonsgegevens met identiteits-, apparaat- en bedreigingsbeveiligingsservices van Microsoft 365.
ms.openlocfilehash: a309b5d0ba5f939cf89a31d7ac91ca3aac25ce0d
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/29/2020
ms.locfileid: "46520979"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>Identiteits-, apparaat- en bedreigingsbescherming gebruiken voor regelgeving voor gegevensprivacy

Microsoft 365 biedt een aantal mogelijkheden voor identiteits-, apparaat- en bedreigingsbescherming die organisaties kunnen gebruiken om te voldoen aan de nalevingsvoorschriften voor gegevensprivacy. In dit artikel wordt beschreven wat de regelgeving inzake gegevensprivacy op deze gebieden vereist en wordt een overzicht gegeven van gerelateerde Microsoft 365-functies en -services met koppelingen naar meer informatie om u te helpen de implementatievereisten aan te pakken.

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a>Hoe identiteits-, apparaat- en bedreigingsbescherming zich verhouden tot de regelgeving voor gegevensprivacy

Hoewel de regels voor gegevensprivacy verschillen in hun specificiteit, wordt de essentie van wat zij vragen opgenomen in artikel 5, lid 1, onder f), artikel 5, lid 1, onder f), van de AVG, waarin staat dat: 

- Persoonsgegevens worden verwerkt op een wijze die een passende beveiliging van de persoonsgegevens waarst omgaat, met inbegrip van bescherming tegen ongeoorloofde of onrechtmatige verwerking en tegen onopzettelijke schade, vernietiging of schade, met behulp van passende technische of organisatorische maatregelen ('integriteit en vertrouwelijkheid').

Omdat inbreuken op persoonlijke gegevens vaak worden veroorzaakt door administratieve of eindgebruikersaccountcompromissen en schadelijke systeemtoegang. Bijvoorbeeld, een admin account hack kan resulteren in exfiltratie van klant creditcardnummers of andere persoonlijke informatie. Alle algemene aan te raden identiteit, apparaat en bedreigingsbescherming die mogelijk beschikbaar is met Microsoft 365, moeten mogelijk worden geïmplementeerd, wat wordt weerspiegeld in uw nalevingsscore.

## <a name="using-the-results-of-your-assessment-work-and-compliance-score"></a>Aan de hand van de resultaten van uw beoordelingswerk en compliancescore

Compliance Score omvat identiteits-, apparaat- en bedreigingsbescherming met behulp van deze categorieën:

- Identiteit komt overeen met de categorie **Controletoegang**
- Apparaat komt overeen met de categorie **Apparaten beheren**
- Bedreigingsbescherming komt overeen met de categorie **Protect Against Threats**
 
Als deze worden geselecteerd in onze voorbeeldset van vier belangrijke regelgeving voor gegevensprivacy, specificeert compliancescore 90 verbeteringsacties, waarvan de meeste een "27" scoren. Aangezien een dergelijk groot aantal wordt opgeroepen door Compliance Score voor deze categorieën, worden enkele van de meest voorkomende hier vermeld, ter referentie.

Gebruik [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) voor identiteit en de categorie Control **Access,** waarmee u:

- Implementeer replay-resistente authenticatie (om "Man in the middle" aanvallen te voorkomen)
- Verouderde verificatie blokkeren.
- Configureer het risicobeleid van gebruikers en het risico van gebruikers.
- Voorwaardelijke toegang en multi-factor authenticatie (MFA) inschakelen voor beheerders en niet-beheerders.
- Wachtwoordbeleid configureren en afdwingen.
- Beperk de toegang tot bevoorrechte accounts met Azure AD Privileged Identity Management.
- Schakel de toegang uit bij beëindiging.
- Gebruikersaccounts en statuswijzigingen controleren.
- Rolgroep en administratieve wijzigingen bekijken.

Gebruik [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) voor apparaten en de categorie Apparaten **beheren,** waarmee u:

- Blokkeer de gevangenis gebroken en geworteld mobiele apparaten.
- Configureer Intune voor beheer van mobiele apparaten.
- Maak nalevingsbeleid voor Android-, iOS-, macOS- en Windows-apparaten.
- Maak een apparaatconfiguratieprofiel voor Android-, iOS-, macOS- en Windows-apparaten.
- Maak beleid voor app-beveiliging voor iOS en Windows.
- Informatie verbergen met vergrendelingsscherm.
- Voer wachtwoordbeleid voor mobiele apparaten.
- Mobiele apparaten moeten vergrendelen bij inactiviteit.
- Mobiele apparaten moeten meerdere aanmeldingsfouten wissen.

Gebruik [Exchange Online Protection en Office 365 Advanced Threat Protection (ATP)](../security/office-365-security/office-365-atp.md) voor de categorie Protect Against **Threats,** waarmee u:

- Afzenderverificatie inschakelen (SPF, DMARC en DKIM).
- Het atp-beleid (Advanced Threat Protection) (Advanced Threat Protection) instellen.
- Implementeer ATP Safe Attachments.
- Implementeer ATP Safe Links.
- Implementeer het beleid voor malwaredetectie en -respons.
- Implementeer uitgaand en binnenkomend spambeleid.

### <a name="references"></a>Verwijzingen:

- [Algemeen beleid voor identiteiten en apparaattoegang](../enterprise/identity-access-policies.md)
- [Beschermen tegen bedreigingen in Office 365](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [ATP-veilige bijlagen](../security/office-365-security/atp-safe-attachments.md)
- [Veilige ATP-koppelingen](../security/office-365-security/atp-safe-links.md)
- [Veilige bijlagen in ATP](../security/office-365-security/safe-docs.md)
