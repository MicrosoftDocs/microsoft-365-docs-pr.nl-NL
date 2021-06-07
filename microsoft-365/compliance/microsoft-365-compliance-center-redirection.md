---
title: Gebruikers omleiden van het Office 365 beveiligings- en compliancecentrum naar het Microsoft 365 compliancecentrum
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
localization_priority: Normal
description: Meer informatie over het automatisch omleiden Office 365 beveiligings- en compliancecentrum naar het Microsoft 365 compliancecentrum..
ms.collection: M365-security-compliance
ms.openlocfilehash: b51b2e225c833ac499379bbee119f8cb6f4216e9
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782835"
---
# <a name="redirect-users-from-the-office-365-security-and-compliance-center-to-the-microsoft-365-compliance-center"></a>Gebruikers omleiden van het Office 365 beveiligings- en compliancecentrum naar het Microsoft 365 compliancecentrum

In dit artikel wordt uitgelegd hoe automatische omleiding werkt voor gebruikers die complianceoplossingen openen vanuit het Office 365 Security and Compliance Center (protection.office.com) naar het Microsoft 365 compliancecentrum (compliance.microsoft.com).

## <a name="what-to-expect"></a>Wat u kunt verwachten

Automatische omleiding is standaard ingeschakeld voor alle gebruikers die toegang hebben tot de volgende compliancegerelateerde oplossingen in Office 365 Security and Compliance (protection.office.com):

- Preventie van gegevensverlies (DLP)
- Classificatie
- Informatiebeheer
- Records Management
- Communicatie compliance (voorheen 'Supervisie')

Gebruikers worden automatisch doorgeleid naar dezelfde complianceoplossingen in het Microsoft 365 compliancecentrum (compliance.microsoft.com).

>[!NOTE]
>Voor andere complianceoplossingen in het Office 365 Beveiligings- en compliancecentrum blijven gebruikers deze oplossingen beheren in het Microsoft 365 compliancecentrum of het Office 365 Beveiligings- en compliancecentrum. De automatische omleiding voor deze complianceoplossingen is binnenkort beschikbaar.*

Met deze functie en bijbehorende besturingselementen wordt de automatische omleiding van beveiligingsfuncties voor Microsoft Defender niet ingeschakeld voor Office 365. Als u de omleiding voor beveiligingsfuncties wilt inschakelen, zie Accounts van Microsoft Defender omleiden voor Office 365 naar het [Microsoft 365 beveiligingscentrum](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection) voor meer informatie.

## <a name="can-i-go-back-to-using-the-former-portal"></a>Kan ik teruggaan naar het gebruik van de voormalige portal?

Als iets niet werkt voor u of als er iets is dat u niet kunt voltooien via de Microsoft 365 compliancecentrumportal, kunt u de automatische omleiding tijdelijk uitschakelen voor alle gebruikers.

>[!IMPORTANT]
>Het Microsoft 365 compliancecentrum is de vervangingsbeheerportal voor complianceoplossingen die momenteel worden beheerd in Office 365 beveiligings- en compliancecentrum. Alle Microsoft 365 complianceoplossingen worden uitsluitend beheerd in het Microsoft 365 compliancecentrum. Het uitschakelen van omleiding naar het Microsoft 365 compliancecentrum moet een oplossing voor de korte termijn zijn.*

Als u wilt teruggaan naar het Office 365 Beveiligings- en compliancecentrum (protection.microsoft.com) voor alle gebruikers, gaat u als volgt te werk:

1. Meld u aan bij [het Microsoft 365 compliancecentrum](https://compliance.microsoft.com) als globale beheerder of gebruik een account met compliancebeheerdersmachtigingen in Azure Active Directory.
2. Navigeer **naar Instellingen**  >  **omleiding van het compliancecentrum**.
3. Schakel de instelling Automatische omleiding in op **Uit.**
4. Selecteer **Uitschakelen en** feedback delen wanneer u daarom wordt gevraagd.

Wanneer deze is uitgeschakeld, worden gebruikers niet meer doorgestuurd naar compliance.microsoft.com en worden ze doorgestuurd naar het Office 365 Security and Compliance center (protection.microsoft.com). Deze instelling kan op elk moment opnieuw worden ingeschakeld door globale beheerders of compliancebeheerders.

## <a name="related-information"></a>Gerelateerde informatie

- [Microsoft 365 overzicht van het compliancecentrum](/microsoft-365/compliance/microsoft-365-compliance-center)
