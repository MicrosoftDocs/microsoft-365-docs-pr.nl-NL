---
title: Azure AD-identiteitsbeveiliging voor uw Microsoft 365 voor Enterprise testomgeving
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
description: Azure AD Identity Protection configureren en de huidige accounts in uw Microsoft 365 voor Enterprise testomgeving analyseren.
ms.openlocfilehash: 162a6504fb7541874798f5e795bd2ecd590b5035
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487706"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a>Azure AD-identiteitsbeveiliging voor uw Microsoft 365 voor Enterprise testomgeving

*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*

U kunt Azure Active Directory (Azure AD)-identiteitsbeveiliging gebruiken om potentiële beveiligingsproblemen op te sporen die van invloed zijn op de identiteiten van uw organisatie, automatische antwoorden configureren en gebeurtenissen onderzoeken. In dit artikel wordt uitgelegd hoe u Azure AD-identiteitsbeveiliging kunt gebruiken om de analyse van uw test omgevings accounts te bekijken.

Azure AD-identiteitsbeveiliging instellen voor de testomgeving Microsoft 365 voor Enterprise omvat twee fasen:

- [Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Azure AD-identiteitsbeveiliging gebruiken](#phase-2-use-azure-ad-identity-protection)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Ga naar [Microsoft 365 for Enterprise test lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)van een visuele kaart voor alle artikelen in de stack microsoft 365 for Enterprise test lab Guide.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken

Als u de beveiliging van Azure AD op een lichte manier wilt testen aan de minimumvereisten, volgt u de instructies in de [basisconfiguratie](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Als u Azure AD-identiteitsbeveiliging wilt testen in een gesimuleerde onderneming, volgt u de instructies in de [Pass Through-verificatie](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Voor het testen van Azure Active Directory-identiteitsbeveiliging is de gesimuleerde Enterprise testomgeving niet vereist, waaronder een gesimuleerd intranet dat verbonden is met internet en adreslijstsynchronisatie van een Active Directory Domain Services (AD DS)-forest. U kunt dit als optie gebruiken, zodat u de beveiliging van Azure AD-identiteit kunt testen en een proef kunt uitvoeren in een omgeving die een typische organisatie voorstelt.
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>Fase 2: Azure AD-identiteitsbeveiliging gebruiken

1. Open een privé-exemplaar van uw browser en meld u aan bij de Azure-Portal [https://portal.azure.com](https://portal.azure.com) met het account van de globale beheerder van uw Microsoft 365 voor Enterprise-testomgeving.
2. Typ in het vak Zoeken van de Azure-Portal de optie **identiteitsbeveiliging** en selecteer **Azure AD-identiteitsbeveiliging**.
3. Selecteer in de blad **identiteitsbeveiliging-overzicht** de optie elk rapport om te zien wat er wordt gerapporteerd.
4. Selecteer onder **waarschuwen** **gebruikers bij risico gedetecteerde meldingen**.
5. Selecteer in het deelvenster **gebruikers van risico gedetecteerde signalen** de optie **normaal**.
6. Voor **e-mailberichten worden de volgende gebruikers verstuurd**, selecteert u **inbegrepen** en controleert u of uw globale beheerdersaccount in de lijst met geselecteerde leden staat.
7. Kies **Opslaan**.

Onder **beveiligen**selecteert u verschillende policies om te zien hoe ze ze kunnen configureren. Als u een beleid maakt en activeert, moet u ervoor zorgen dat u de toegang voor alle gebruikers niet blokkeert of dat u zich mogelijk niet kunt aanmelden. U kunt dit voorkomen door specifieke gebruikersaccounts, zoals globale beheerders, uit te sluiten.

Zie [risico gebeurtenissen simuleren](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)voor verdere testen en experimenteren.

## <a name="next-step"></a>Volgende stap

Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Identiteitskaart](identity-roadmap-microsoft-365.md)

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Documentatie voor Microsoft 365 for Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
