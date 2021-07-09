---
title: Gebruikers omleiden van het Office 365 beveiligings- en compliancecentrum naar het Microsoft 365-compliancecentrum
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
localization_priority: Normal
description: Meer informatie over het automatisch omleiden Office 365 beveiligings- en compliancecentrumgebruikers naar de Microsoft 365-compliancecentrum..
ms.collection: M365-security-compliance
ms.openlocfilehash: 62fc302f9f065ac7bb0475a6e72dc240a56a1fe1
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339404"
---
# <a name="redirect-users-from-the-office-365-security-and-compliance-center-to-the-microsoft-365-compliance-center"></a>Gebruikers omleiden van het Office 365 beveiligings- en compliancecentrum naar het Microsoft 365-compliancecentrum

In dit artikel wordt uitgelegd hoe automatische omleiding werkt voor gebruikers die toegang hebben tot complianceoplossingen van het Office 365 Security and Compliance Center (protection.office.com) tot de Microsoft 365-compliancecentrum (compliance.microsoft.com).

## <a name="what-to-expect"></a>Wat u kunt verwachten

Automatische omleiding is standaard ingeschakeld voor alle gebruikers die toegang hebben tot de volgende compliancegerelateerde oplossingen in Office 365 Security and Compliance (protection.office.com):

- Preventie van gegevensverlies (DLP)
- Classificatie
- Informatiebeheer
- Records Management
- Communicatie compliance (voorheen 'Supervisie')

Gebruikers worden automatisch doorgeleid naar dezelfde complianceoplossingen in de Microsoft 365-compliancecentrum (compliance.microsoft.com).

> [!NOTE]
> Voor andere complianceoplossingen in het Office 365 Beveiligings- en compliancecentrum blijven gebruikers deze oplossingen beheren in het Microsoft 365-compliancecentrum of het Office 365 Beveiligings- en compliancecentrum. De automatische omleiding voor deze complianceoplossingen is binnenkort beschikbaar.

Met deze functie en bijbehorende besturingselementen wordt de automatische omleiding van beveiligingsfuncties voor Microsoft Defender niet ingeschakeld voor Office 365. Als u de omleiding voor beveiligingsfuncties wilt inschakelen, zie Accounts van Microsoft Defender omleiden voor Office 365 naar het [Microsoft 365 beveiligingscentrum](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection) voor meer informatie.

## <a name="can-i-go-back-to-using-the-former-portal"></a>Kan ik teruggaan naar het gebruik van de voormalige portal?

Als iets niet werkt voor u of als er iets is dat u niet kunt voltooien via de Microsoft 365-compliancecentrum-portal, kunt u de automatische omleiding tijdelijk uitschakelen voor alle gebruikers.

> [!IMPORTANT]
> De Microsoft 365-compliancecentrum is de vervangingsbeheerportal voor complianceoplossingen die momenteel worden beheerd in Office 365 beveiligings- en compliancecentrum. Alle Microsoft 365 complianceoplossingen worden uitsluitend in de Microsoft 365-compliancecentrum. Het uitschakelen van omleiding naar de Microsoft 365-compliancecentrum moet een oplossing voor de korte termijn zijn.

Als u wilt teruggaan naar het Office 365 Beveiligings- en compliancecentrum (protection.microsoft.com) voor alle gebruikers, gaat u als volgt te werk:

1. Meld u aan bij [de Microsoft 365-compliancecentrum](https://compliance.microsoft.com) globale beheerder of gebruik een account met compliancebeheerdersmachtigingen in Azure Active Directory.
2. Navigeer **naar Instellingen**  >  **omleiding van het compliancecentrum**.
3. Schakel de instelling Automatische omleiding in op **Uit.**
4. Selecteer **Uitschakelen en** feedback delen wanneer u daarom wordt gevraagd.

Wanneer deze is uitgeschakeld, worden gebruikers niet meer doorgestuurd naar compliance.microsoft.com en worden ze doorgestuurd naar het Office 365 Security and Compliance center (protection.microsoft.com). Deze instelling kan op elk moment opnieuw worden ingeschakeld door globale beheerders of compliancebeheerders.

## <a name="related-information"></a>Gerelateerde informatie

- [Microsoft 365-compliancecentrum overzicht](/microsoft-365/compliance/microsoft-365-compliance-center)
