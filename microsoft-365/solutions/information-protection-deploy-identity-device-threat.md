---
title: Identiteit, apparaat en bedreigings bescherming gebruiken voor data privacy verordening
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
- m365solution-scenario
ms.custom: ''
description: Voorkom dat persoonlijke gegevens worden geschonden met identiteits-, service-en Threat Protection-Services van Microsoft 365.
ms.openlocfilehash: 681ff807b734430ae864334b409fe11397f3089e
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377055"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>Identiteit, apparaat en bedreigings bescherming gebruiken voor data privacy verordening

Microsoft 365 biedt een aantal mogelijkheden voor identiteiten, apparaten en beveiliging van bedreigingen waarmee organisaties zich kunnen helpen aan de nalevings regels van de regelgeving voor informatie. In dit artikel wordt uitgelegd wat de vereisten voor data privacy op deze gebieden zijn, en een lijst met verwante Microsoft 365-functies en-services, met koppelingen naar meer informatie om de implementatievereisten te adresseren.

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a>Hoe de identiteit, het apparaat en de bedreigingsbeveiliging betrekking hebben op de regelgeving voor data privacy

Hoewel de regelgeving voor de privacy in hun eigeniteit verschilt, is de essentie van de inhoud van de inhoud van het AVG-artikel 5 (1) (f), waarin wordt aangegeven dat: 

- Persoonlijke gegevens worden verwerkt op een wijze die de juiste veiligheid van de persoonsgegevens waarborgt, met inbegrip van de bescherming tegen ongeoorloofde of onwettige verwerking en tegen toevallige verlies, vernietiging of schade, op basis van adequate technische of organisatie maatregelen (' integriteit en vertrouwelijkheid ').

Aangezien persoonlijke gegevens schendingen vaak worden veroorzaakt door een administratieve of eindgebruikers account en toegang tot een kwaadaardige systeem. Een account van een beheerder kan bijvoorbeeld hacken exfiltration van creditcardnummers van klanten of andere persoonlijke gegevens. Alle algemeen verzorg bare identiteit, apparaat en bedreigings bescherming met Microsoft 365, moet worden geïmplementeerd, welke worden weergegeven in de compliance-Score.

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a>De resultaten van uw beoordelings werk en Compliance Manager gebruiken

Nalevings beheer met identiteit, apparaat en bedreigingsbeveiliging bevat de volgende categorieën:

- Identiteit komt overeen met de categorie **toegangsbeheer**
- Apparaat komt overeen met de categorie **apparaten beheren**
- Bedreigingsbeveiliging komt overeen met de categorie **bescherming tegen bedreigingen**
 
Als deze optie is geselecteerd in onze Voorbeeldset met vier belangrijke informatie over de privacy, geeft Compliance Manager 90-verbeterings acties op, waarvan de meeste een ' 27 ' gescoorde. Aangezien een dergelijk grote nummer wordt genoemd door Compliance Manager voor deze categorieën, worden enkele van de meest voorkomende items hier weergegeven voor naslaginformatie.

Azure [Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) gebruiken voor de identiteit en de categorie **toegangsbeheer** , waarmee u het volgende kunt doen:

- Herspeel bestendige verificatie implementeren (om man in het midden te helpen voorkomen)
- Verouderde authenticatie blokkeren.
- Beleidsregels voor gebruikers risico en gebruikersaanmelding configureren.
- Schakel voorwaardelijke toegang en multi-factor Authentication (MFA) in voor beheerders en niet-beheerders.
- Wachtwoordbeleidsregels configureren en afdwingen.
- Toegang tot geprivilegieerde accounts beperken met een Azure AD-geprivilegieerde identiteitsbeheer.
- Toegang uitschakelen na beëindiging.
- Controleer gebruikersaccounts en statuswijzigingen.
- Rollen groepen en beheerders wijzigingen bekijken.

Gebruik [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) voor apparaten en de categorie **apparaten beheren** , waarmee u het volgende kunt doen:

- Blokkeer jail verbroken en geroote mobiele apparaten.
- InTune configureren voor Mobile Device Management.
- Nalevingsbeleid maken voor Android-, iOS-, macOS-en Windows-apparaten.
- Maak een apparaatconfiguratie-profiel voor Android-, iOS-, macOS-en Windows-apparaten.
- Maak app-beveiligingsbeleid voor iOS en Windows.
- Gegevens verbergen met vergrendelingsscherm.
- Beleidsregels voor het wachtwoord implementeren voor mobiele apparaten.
- Mobiele apparaten moeten worden vergrendeld bij inactiviteit.
- Vereisen dat mobiele apparaten meerdere aanmeldingsfouten wissen.

Gebruik [Exchange Online Protection en Office 365 Advanced Threat Protection (ATP)](../security/office-365-security/office-365-atp.md) voor de categorie **beveiliging tegen bedreigingen** , waarop u het volgende kunt doen:

- Verzender verificatie inschakelen (SPF, DMARC en DKIM).
- Stel Office 365 Advanced Threat Protection (ATP) anti malafide beleid in.
- Een veilige bijlage van de ATP-toepassing implementeren.
- Veilige koppelingen voor ATP implementeren.
- Detectie van malware en antwoord beleid implementeren.
- Implementeer uitgaand en inkomend spam beleid.

### <a name="references"></a>Verwijzingen

- [Algemeen beleid voor identiteiten en apparaattoegang](../enterprise/identity-access-policies.md)
- [Beveiliging tegen bedreigingen in Office 365](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [Veilige bijlage van ATP](../security/office-365-security/atp-safe-attachments.md)
- [Veilige ATP-koppelingen](../security/office-365-security/atp-safe-links.md)
- [Veilige bijlagen in ATP](../security/office-365-security/safe-docs.md)
