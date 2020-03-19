---
title: Azure AD-identiteitsbeveiliging voor uw Microsoft 365 Enterprise-testomgeving
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
description: Configureer Azure AD-identiteitsbeveiliging en analyseer de huidige accounts in uw Microsoft 365 Enterprise-testomgeving.
ms.openlocfilehash: 3f3740e42c7ec909f44a3c761dfc743359b3f030
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42806079"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a>Azure AD-identiteitsbeveiliging voor uw Microsoft 365 Enterprise-testomgeving

*Deze Test Lab Guide kan alleen worden gebruikt voor Microsoft 365 Enterprise-testomgevingen.*

Met Azure Active Directory (Azure AD) Identity Protection u mogelijke kwetsbaarheden detecteren die de identiteit van uw organisatie beïnvloeden, geautomatiseerde antwoorden configureren en incidenten onderzoeken. In dit artikel wordt beschreven hoe u Azure AD-identiteitsbeveiliging gebruiken om de analyse van uw testomgevingsaccounts weer te geven.

Er zijn twee fasen om Azure AD-identiteitsbeveiliging in te stellen in uw Microsoft 365 Enterprise-testomgeving:

1. Maak de Microsoft 365 Enterprise-testomgeving.
2. Gebruik Azure AD-identiteitsbeveiliging.

![Test Lab-hulplijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de Microsoft 365 Enterprise Test Lab Guide stack.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Uw Microsoft 365 Enterprise-testomgeving uitbouwen

Als u Azure AD Identity Protection alleen op een lichtgewicht manier wilt testen met de minimumvereisten, volgt u de instructies in [lichtgewicht basisconfiguratie](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Als u Azure AD-identiteitsbeveiliging wilt testen in een gesimuleerde onderneming, volgt u de instructies in [Pass-through-verificatie](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Het testen van Azure AD-identiteitsbeveiliging vereist niet de gesimuleerde bedrijfstestomgeving, die een gesimuleerd intranet bevat dat is verbonden met internet- en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services). Het wordt hier als optie geleverd, zodat u Azure AD-identiteitsbescherming testen en ermee experimenteren in een omgeving die een typische organisatie vertegenwoordigt. 
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>Fase 2: Azure AD-identiteitsbeveiliging gebruiken

1. Open een privé-exemplaar van uw browser en [https://portal.azure.com](https://portal.azure.com) meld u aan bij de Azure-portal met het globale beheerdersaccount van uw Microsoft 365 Enterprise-testomgeving.
2. Typ in de Azure-portal **identiteitsbeveiliging** in het zoekvak en klik op **Azure AD-identiteitsbeveiliging**.
3. Klik in het **blade voor identiteitsbescherming - op** elk van de rapporten om te zien wat ze rapporteren.
4. Klik onder **Aanmelden**op **Gebruikers met risico gedetecteerde waarschuwingen**.
5. Selecteer **Users at risk detected alerts** **Medium**.
6. Als **e-mails naar de volgende gebruikers worden verzonden,** klikt u op **Opgenomen** en controleert u of uw globale beheerdersaccount zich in de lijst met geselecteerde leden bevindt.
7. Klik op **Opslaan**.

Klik door het verschillende beleid onder **Beveiligen** om te zien hoe u ze configureert. Als u een beleid maakt en activeert, moet u ervoor zorgen dat het de toegang niet blokkeert voor een te breed scala aan voorwaarden, of als u zich mogelijk niet aanmelden, zelfs niet als globale beheerder.

Zie [Risicogebeurtenissen simuleren](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)voor verder onderzoek en experimenten.

Zie de stap [Beveiligen tegen het compromitteren van referenties](identity-secure-user-sign-ins.md#identity-ident-prot) in de identiteitsfase voor informatie en koppelingen om Azure AD-identiteitsbeveiliging in productie te implementeren.

## <a name="next-step"></a>Volgende stap

Ontdek extra [identiteitsfuncties](m365-enterprise-test-lab-guides.md#identity) en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Fase 2: Identiteit](identity-infrastructure.md)

[Microsoft 365 Enterprise Test Lab-handleidingen](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise-implementatie](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise-documentatie](https://docs.microsoft.com/microsoft-365-enterprise/)
