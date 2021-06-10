---
title: Beveiligingsinstellingen in- en uit-
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Lees hoe beveiligingsinstellingen uw organisatie kunnen beschermen tegen identiteitsgerelateerde aanvallen door vooraf geconfigureerde beveiligingsinstellingen te bieden.
ms.openlocfilehash: ea36ba45af26a767b08ee1e75931dca54dacea64
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398289"
---
# <a name="turn-on-security-defaults"></a>Beveiligingsinstellingen in- en uit-

Beveiligingsinstellingen helpen uw organisatie te beschermen tegen identiteitsgerelateerde aanvallen door vooraf geconfigureerde beveiligingsinstellingen te bieden die Microsoft namens uw organisatie beheert. Deze instellingen omvatten het inschakelen van meervoudige verificatie (MFA) voor alle beheerders en gebruikersaccounts. Voor de meeste organisaties bieden beveiligingsinstellingen een goed niveau van extra aanmeldingsbeveiliging.

Zie Wat [zijn beveiligings defaults?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) voor meer informatie over beveiligingsinstellingen en het beleid dat ze afdwingen.

Als uw abonnement is gemaakt op of na 22 oktober 2019, zijn beveiligingsinstellingen mogelijk automatisch ingeschakeld voor u. Controleer de instellingen om dit te &mdash; bevestigen.

Als u beveiligingsinstellingen in uw Azure Active Directory (Azure AD) wilt inschakelen of wilt controleren of deze al zijn ingeschakeld:

1. Meld u aan bij <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">het Microsoft 365 beheercentrum</a> met globale beheerdersreferenties.

2. Selecteer in het linkerdeelvenster **Alles weergeven en** selecteer vervolgens onder **Beheercentra** **Azure Active Directory.**

3. Selecteer in het linkerdeelvenster **Azure Active Directory het beheercentrum** **Azure Active Directory.**

4. Selecteer eigenschappen in het linkermenu van het dashboard in **de** sectie **Beheren.**

    :::image type="content" source="../media/m365-campaigns-conditional-access/azure-ad-properties.png" alt-text="Schermafbeelding van het Azure Active Directory beheercentrum met de locatie van het menu-item Eigenschappen.":::

5. Selecteer onder aan de pagina **Eigenschappen** de optie **Beveiligingsinstellingen beheren.**

6. In het rechterdeelvenster ziet u de standaardinstelling **Beveiliging inschakelen.** Als **Ja** is geselecteerd, zijn beveiligingsinstellingen al ingeschakeld en is er geen verdere actie vereist. Als beveiligingsinstellingen momenteel niet zijn ingeschakeld, selecteert u **Ja** om deze in te stellen en selecteert u **Opslaan.**

> [!NOTE]
> Als u beleidsregels voor voorwaardelijke toegang hebt gebruikt, moet u deze uitschakelen voordat u beveiligingsinstellingen gebruikt.
>
> U kunt beveiligingsinstellingen of beleidsregels voor Voorwaardelijke toegang gebruiken, maar u kunt beide niet tegelijkertijd gebruiken.

## <a name="consider-using-conditional-access"></a>Overweeg Voorwaardelijke toegang te gebruiken

Als uw organisatie complexe beveiligingsvereisten heeft of als u meer gedetailleerde controle over uw beveiligingsbeleid nodig hebt, moet u overwegen Voorwaardelijke toegang te gebruiken in plaats van beveiligingsinstellingen om een vergelijkbare of hogere beveiligingsinstelling te bereiken. 

Met Voorwaardelijke toegang kunt u beleidsregels maken en definiëren die reageren op aanmeldingsgebeurtenissen en aanvullende acties aanvragen voordat een gebruiker toegang krijgt tot een toepassing of service. Beleid voor voorwaardelijke toegang kan gedetailleerd en specifiek zijn, zodat gebruikers overal en altijd productief kunnen zijn, maar ook uw organisatie kunnen beschermen.

Beveiligings defaults zijn beschikbaar voor alle klanten, terwijl voor Voorwaardelijke toegang een licentie is vereist voor een van de volgende abonnementen:

- Azure Active Directory Premium P1 of P2
- Microsoft 365 Business Premium
- Microsoft 365 E3 of E5
- Enterprise Mobility & Security E3 of E5

Als u Voorwaardelijke toegang wilt gebruiken om beleid te configureren dat overeenkomt met beleidsregels die standaard zijn ingeschakeld, raadpleegt u de volgende stapsgewijze handleidingen:

- [MFA vereisen voor beheerders](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [MFA vereisen voor Azure-beheer](/azure/active-directory/conditional-access/howto-conditional-access-policy-azure-management)
- [Verouderde verificatie blokkeren](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)
- [MFA vereisen voor alle gebruikers](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [Azure AD MFA-registratie vereisen:](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) hiervoor is Azure AD Identity Protection vereist, dat deel uitmaakt van Azure Active Directory Premium P2

Zie Wat [is Voorwaardelijke toegang? voor meer informatie over voorwaardelijke toegang.](/azure/active-directory/conditional-access/overview) Zie Een beleid voor voorwaardelijke toegang maken voor meer informatie over het maken van beleid voor voorwaardelijke [toegang.](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy)

> [!NOTE]
> Als u een abonnement of licentie hebt met voorwaardelijke toegang, maar nog geen beleid voor voorwaardelijke toegang hebt gemaakt, kunt u beveiligingsinstellingen gebruiken. U moet echter beveiligingsinstellingen uitschakelen voordat u beleid voor voorwaardelijke toegang kunt gebruiken.
