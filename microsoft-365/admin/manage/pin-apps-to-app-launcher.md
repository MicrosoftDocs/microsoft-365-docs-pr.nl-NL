---
title: Apps vastmaken aan het startprogramma voor apps van uw gebruikers
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- M365-subscription-management
ms.service: o365-administration
localization_priority: Normal
description: Als globale beheerder kunt u maximaal drie apps vastmaken aan het startprogramma voor apps van uw gebruikers.
ms.openlocfilehash: d9b95a20f332a9b1f2f6b0ebba28a70c58677b58
ms.sourcegitcommit: 87449335d9a1124ee82fa2e95e4745155a95a62f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/29/2020
ms.locfileid: "47310873"
---
# <a name="pin-apps-to-your-users-app-launcher"></a>Apps vastmaken aan het startprogramma voor apps van uw gebruikers

U kunt besturingselementen in de Azure Active Directory-Portal gebruiken om maximaal drie apps aan Office.com en het startprogramma voor apps vast te maken voor alle gebruikers in uw organisatie. U kunt groepen toepassingen ook ordenen. Apps die u toevoegt, kunnen later worden losgemaakt door de gebruiker. Als u een app wilt vastmaken voor uw gebruikers, moet u een Cloud toepassing of toepassingsbeheerder in azure Active Directory of een globale beheerder in Office 365. Zie voor meer informatie over beheerdersrollen [beheerdersrollen in azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) en [beheerdersrollen in Microsoft 365](../add-users/about-admin-roles.md). 

Zie voor meer informatie over het startprogramma voor apps en Office.com de informatie in [het startprogramma voor apps](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) en [updates voor Office.com en het blogartikel Office 365-startprogramma voor apps](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) .

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a>Het Azure Active Directory-Portal gebruiken om apps te vastmaken

1. Ga naar het Microsoft 365-Beheercentrum <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .
2. Kies in het linkernavigatievenster de optie **Toon alles**en kies onder **admin Centers**de optie **Azure Active Directory**.
3. Kies in **Azure Active Directory**de optie gebruikersinstellingen voor **Enterprise Applications**  >  **User settings**.
4. Kies in de sectie **Office 365 Settings** de optie **Add Application**.
5. Kies de toepassingen die u wilt vastmaken aan het startprogramma voor apps van gebruikers en kies vervolgens **toevoegen**.

:::image type="content" source="../../media/add-apps.png" alt-text="Microsoft 365-instellingen voor het vastmaken van apps.":::

### <a name="pin-a-custom-app"></a>Een aangepaste app vastmaken

> [!NOTE]
> In de gebruikersinterface wordt aangegeven of u extra Azure AD-licenties moet kopen om deze functie te kunnen gebruiken. Zie [prijzen van Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/)voor meer informatie.

1. Kies in **Azure Active Directory**de optie **Enterprise applications**  >  **nieuwe toepassing** voor bedrijfstoepassingen boven aan de pagina **alle toepassingen** .
2. Kies op de pagina **een toepassing toevoegen** de optie **niet-galerie toepassing** of **Maak uw eigen toepassing** als u zich in de preview-versie van Azure Active Directory bevindt. 
3. Typ een naam voor de toepassing en wijs gebruiker toe op het tabblad **gebruikers en groepen** .
4. Met het tabblad **Eigenschappen** kunt u een pictogram voor de app uploaden.
5. Als u een URL wilt toewijzen aan de app, kiest u op het tabblad **eenmalige aanmelding** de optie **gekoppeld** en voert u vervolgens een URL in.
6. Selecteer **Save**.

## <a name="create-application-collections"></a>Toepassings verzamelingen maken

U kunt ook toepassingen verzamelingen maken voor de gebruikers in uw organisatie. Zie [verzamelingen maken in de portal mijn apps in de Azure-Portal](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections)voor instructies.