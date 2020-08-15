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
ms.openlocfilehash: bd1e7560e978b13d24e9e93a99a2567adca95c75
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694988"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a>Azure AD-identiteitsbeveiliging voor uw Microsoft 365 voor Enterprise testomgeving

*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*

Met identiteitsbeveiliging van Azure Active Directory (Azure AD) kunt u mogelijke problemen detecteren die van invloed zijn op de identiteiten van uw organisatie, automatische antwoorden configureren en incidenten onderzoeken. In dit artikel wordt uitgelegd hoe u Azure AD-identiteitsbeveiliging kunt gebruiken om de analyse van uw test omgevings accounts te bekijken.

Er zijn twee fasen om Azure AD-identiteitsbeveiliging in te stellen in uw Microsoft 365 voor Enterprise testomgeving:

1. Maak de testomgeving Microsoft 365 for Enterprise.
2. Azure Active Directory-identiteitsbeveiliging gebruiken.

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klik op [Hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de stack van Microsoft 365 voor Enterprise-testlabrichtlijnen.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken

Als u alleen de bescherming van Azure AD-identiteit op een lichte manier wilt testen aan de minimumvereisten, volgt u de instructies in de [Lightweight Base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Als u Azure AD-identiteitsbeveiliging wilt testen in een gesimuleerde onderneming, volgt u de instructies in de [Pass Through-verificatie](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Voor Azure Active Directory-identiteitsbeveiliging is geen gesimuleerde Enterprise-testomgeving vereist, dat een gesimuleerd intranet bevat dat verbonden is met internet en adreslijstsynchronisatie van een Active Directory Domain Services (AD DS)-forest. U kunt dit als optie gebruiken, zodat u de beveiliging van Azure AD-identiteit kunt testen en een proef kunt uitvoeren in een omgeving die een typische organisatie voorstelt. 
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>Fase 2: Azure AD-identiteitsbeveiliging gebruiken

1. Open een privé-exemplaar van uw browser en meld u aan bij de Azure-Portal [https://portal.azure.com](https://portal.azure.com) met het account van de globale beheerder van uw Microsoft 365 voor Enterprise-testomgeving.
2. Typ in het vak Zoeken in de Azure-Portal de tekst **identiteitsbeveiliging** en klik vervolgens op **Azure AD Identity Protection**.
3. Klik in de blad **identiteitsbeveiliging-overzicht** op elk rapport om te zien wat ze rapporteren.
4. Klik onder **waarschuwen**op **gebruikers met risico gedetecteerde meldingen**.
5. Selecteer in het deelvenster **gebruikers van risico gedetecteerde signalen** de optie **normaal**.
6. Voor **e-mailberichten worden de volgende gebruikers verzonden**: Klik op **opgenomen** en controleer of uw globale beheerdersaccount in de lijst met geselecteerde leden staat.
7. Klik op **Opslaan**.

Klik op de verschillende beleidsregels onder **beveiligen** om te zien hoe u deze kunt configureren. Als u een beleid maakt en activeert, moet u ervoor zorgen dat de toegang niet te veel voorwaarden blokkeert, of dat u zich mogelijk niet kunt aanmelden, ook niet als globale beheerder.

Zie [risico gebeurtenissen simuleren](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)voor verdere testen en experimenteren.

## <a name="next-step"></a>Volgende stap

Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Identiteitskaart](identity-roadmap-microsoft-365.md)

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Documentatie voor Microsoft 365 for Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
