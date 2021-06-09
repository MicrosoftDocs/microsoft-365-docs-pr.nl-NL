---
title: Azure AD Identity Protection voor uw Microsoft 365 voor bedrijfstestomgeving
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configureer Azure AD Identity Protection en analyseer de huidige accounts in uw Microsoft 365 voor bedrijfstestomgeving.
ms.openlocfilehash: 0cb0acf3faee13676573b04178bd6b4d3d36da4d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905342"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a>Azure AD Identity Protection voor uw Microsoft 365 voor bedrijfstestomgeving

*Deze testlaborator kan alleen worden gebruikt Microsoft 365 voor bedrijfstestomgevingen.*

U kunt Azure Active Directory (Azure AD) Identity Protection gebruiken om mogelijke beveiligingsproblemen op te sporen die van invloed zijn op de identiteiten van uw organisatie, geautomatiseerde antwoorden configureren en incidenten onderzoeken. In dit artikel wordt beschreven hoe u Azure AD Identity Protection gebruikt om de analyse van uw testomgevingaccounts weer te geven.

Het instellen van Azure AD Identity Protection in uw Microsoft 365 voor ondernemingstestomgeving omvat twee fasen:

- [Fase 1: uw Microsoft 365 voor bedrijfstestomgeving](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Azure AD Identity Protection gebruiken](#phase-2-use-azure-ad-identity-protection)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Voor een visuele kaart van alle artikelen in de Microsoft 365 voor enterprise Test Lab Guide stack, gaat u naar Microsoft 365 voor [enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: uw Microsoft 365 voor bedrijfstestomgeving

Als u Azure AD Identity Protection alleen op een lichtgewicht manier wilt testen met de minimumvereisten, volgt u de instructies in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Als u Azure AD Identity Protection wilt testen in een gesimuleerde onderneming, volgt u de instructies in [Pass-through-verificatie.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Voor het testen van Azure AD Identity Protection is geen gesimuleerde bedrijfstestomgeving vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services). Het is hier beschikbaar als een optie, zodat u Azure AD Identity Protection kunt testen en erop kunt experimenteren in een omgeving die een normale organisatie vertegenwoordigt.
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>Fase 2: Azure AD Identity Protection gebruiken

1. Open een privé-exemplaar van uw browser en meld u aan bij de Azure-portal bij met het globale beheerdersaccount van uw Microsoft 365 [https://portal.azure.com](https://portal.azure.com) voor ondernemingstestomgeving.
2. Typ in de Azure-portal **identiteitsbeveiliging** in het zoekvak en selecteer **vervolgens Azure AD Identity Protection**.
3. Selecteer in **het blad Identiteitsbeveiliging - Overzicht** elk rapport om te zien wat het rapport rapporteert.
4. Selecteer **onder Aanmelden** de optie Gebruikers met risico **gedetecteerde waarschuwingen.**
5. Selecteer in **het deelvenster Gebruikers met risico gedetecteerde waarschuwingen** de optie **Medium**.
6. Als **e-mailberichten naar de volgende gebruikers worden verzonden,** **selecteert** u Opgenomen en controleert u of uw globale beheerdersaccount in de lijst met geselecteerde leden staat.
7. Klik op **Opslaan**.

Selecteer **onder** Beveiligen verschillende agenten om te zien hoe u deze configureert. Als u een beleid maakt en activeert, moet u ervoor zorgen dat de toegang niet voor alle gebruikers wordt geblokkeerd of dat u zich mogelijk niet kunt aanmelden. U kunt dit voorkomen door specifieke gebruikersaccounts uit te sluiten, zoals globale beheerders.

Zie Risicogebeurtenissen simuleren voor meer testen [en experimenteren.](/azure/active-directory/active-directory-identityprotection-playbook)

## <a name="next-step"></a>Volgende stap

Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Routekaart voor identiteit](identity-roadmap-microsoft-365.md)

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Microsoft 365 enterprise-documentatie](/microsoft-365-enterprise/)