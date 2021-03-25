---
title: Identiteits-, apparaat- en bedreigingsbeveiliging gebruiken voor privacyregels voor gegevens
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
description: Voorkom inbreuken op persoonlijke gegevens met identiteits-, apparaat- en bedreigingsbeveiligingsservices van Microsoft 365.
ms.openlocfilehash: 5e08ef574e199769e572b3836b3323dc88fc4bbd
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199463"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>Identiteits-, apparaat- en bedreigingsbeveiliging gebruiken voor privacyregels voor gegevens

Microsoft 365 biedt een aantal mogelijkheden voor identiteits-, apparaat- en bedreigingsbeveiliging die organisaties kunnen gebruiken om te voldoen aan nalevingsregels voor gegevensbescherming. In dit artikel wordt beschreven wat de privacyregels voor gegevens vereisen in deze gebieden en bevat een lijst met gerelateerde Microsoft 365-functies en -services met koppelingen naar meer informatie om u te helpen bij het voldoen aan implementatievereisten.

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a>Hoe identiteits-, apparaat- en bedreigingsbeveiliging zich verhouden tot de privacyregel voor gegevens

Hoewel de privacyregels voor gegevens variëren in hun specificiteit, wordt de essentie van wat ze noemen opgenomen in artikel 5, lid 1, onder f, van de AVG, waarin wordt bepaald dat:

- Persoonsgegevens worden verwerkt op een manier die de juiste beveiliging van de persoonsgegevens garandeert, met inbegrip van bescherming tegen ongeoorloofde of onrechtmatige verwerking en tegen onbedoeld verlies, vernieling of schade, met behulp van passende technische of organisatorische maatregelen ('integriteit en vertrouwelijkheid').

Omdat inbreuken op persoonlijke gegevens vaak worden veroorzaakt door compromitteerd beheer- of eindgebruikersaccount en schadelijke systeemtoegang. Een hack van een beheerdersaccount kan bijvoorbeeld leiden tot exfiltratie van creditcardnummers van klanten of andere persoonlijke gegevens. Alle over het algemeen aanbevolen identiteits-, apparaat- en bedreigingsbeveiliging die mogelijk beschikbaar is met Microsoft 365, moet worden geïmplementeerd, wat wordt weerspiegeld in uw compliancescore, die wordt gevonden in Compliance Manager.

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a>De resultaten van uw beoordelingswerk en Compliance Manager gebruiken

Compliance Manager bevat identiteits-, apparaat- en bedreigingsbeveiliging met behulp van deze categorieën:

- Identiteit komt overeen met de **categorie Control Access**
- Apparaat komt overeen met de **categorie Apparaten** beheren
- Bedreigingsbeveiliging komt overeen met de **categorie Beschermen tegen** bedreigingen
 
Als deze zijn geselecteerd in onze voorbeeldset met vier belangrijke privacyregels voor gegevens, geeft Compliance Manager 90 verbeteracties op, waarvan de meeste een '27' krijgen. Aangezien een dergelijk groot aantal door Compliance Manager voor deze categorieën wordt uitgeroepen, worden enkele veelgebruikte categorieën hier vermeld, ter referentie.

Gebruik [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) voor identiteit en de categorie Control **Access,** waarmee u het volgende kunt doen:

- Replay-resistant authentication implementeren (om 'Man in the middle' aanvallen te voorkomen)
- Oudere verificatie blokkeren.
- Beleidsregels voor gebruikersrisico's en aanmeldingsrisico's voor gebruikers configureren.
- Voorwaardelijke toegang en meervoudige verificatie (MFA) inschakelen voor beheerders en niet-beheerders.
- Wachtwoordbeleid configureren en afdwingen.
- Toegang tot bevoorrechte accounts beperken met Azure AD Privileged Identity Management.
- De toegang uitschakelen na beëindiging.
- Controleer gebruikersaccounts en statuswijzigingen.
- Controleer rollengroep- en beheerwijzigingen.

Microsoft [Endpoint Manager gebruiken](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) voor apparaten en de categorie Apparaten beheren, waarmee u het volgende kunt doen: 

- Blokkeer de cel met gebroken en geroote mobiele apparaten.
- Intune configureren voor mobiel apparaatbeheer.
- Maak compliancebeleid voor Android-, iOS-, macOS- en Windows-apparaten.
- Maak een apparaatconfiguratieprofiel voor Android-, iOS-, macOS- en Windows-apparaten.
- Beleid voor app-beveiliging maken voor iOS en Windows.
- Verberg gegevens met vergrendelingsscherm.
- Wachtwoordbeleid implementeren voor mobiele apparaten.
- Vereisen dat mobiele apparaten worden vergrendeld bij inactiviteit.
- Vereisen dat mobiele apparaten meerdere aanmeldingsfouten wissen.

Gebruik [Exchange Online Protection en Microsoft Defender voor Office 365](../security/office-365-security/defender-for-office-365.md) voor de categorie Beschermen **tegen** bedreigingen, waarmee u het volgende kunt doen:

- Afzenderverificatie (SPF, DMARC en DKIM) inschakelen.
- Microsoft Defender voor Office 365 anti-phishingbeleid instellen.
- Veilige bijlagen implementeren.
- Veilige koppelingen implementeren.
- Implementeert malwaredetectie- en antwoordbeleid.
- Implementeert uitgaand en binnenkomende spambeleid.

### <a name="references"></a>Verwijzingen:

- [Algemeen beleid voor identiteiten en apparaattoegang](../security/office-365-security/identity-access-policies.md)
- [Beschermen tegen bedreigingen in Office 365](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [Veilige bijlagen](../security/office-365-security/safe-attachments.md)
- [Veilige koppelingen](../security/office-365-security/safe-links.md)
- [Veilige documenten](../security/office-365-security/safe-docs.md)
