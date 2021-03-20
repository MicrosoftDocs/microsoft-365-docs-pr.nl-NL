---
title: MsSP-toegang (Managed Security Service Provider) bieden
description: Meer informatie over wijzigingen van het Microsoft Defender-beveiligingscentrum in het Microsoft 365-beveiligingscentrum
keywords: Aan de slag met het Microsoft 365-beveiligingscentrum, OATP, MDATP, MDO, MDE, enkel deelvenster glas, geconvergeerde portal, beveiligingsportal, defender-beveiligingsportal
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: db9279ba1bc5fe11f3a31884a05b4403f0cb67f3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906698"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a>MsSP-toegang (Managed Security Service Provider) bieden 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Van toepassing op:**

- [Microsoft 365 Defender](./microsoft-threat-protection.md)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)

Als u een oplossing voor gedelegeerde toegang met meerdere tenants wilt implementeren, voert u de volgende stappen uit:

1. Schakel [op rollen gebaseerde toegangsbeheer](/windows/security/threat-protection/microsoft-defender-atp/rbac) in Defender voor Eindpunt in microsoft 365-beveiligingscentrum in en maak verbinding met Azure Active Directory -groepen (Azure AD).

2. [Beheertoegangspakketten configureren voor toegangsaanvraag](/azure/active-directory/governance/identity-governance-overview) en inrichting.

3. Toegangsaanvragen en -audits beheren in [Microsoft Myaccess](/azure/active-directory/governance/entitlement-management-request-approve).

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-security-center"></a>Op rollen gebaseerde toegangsbesturingselementen inschakelen in Microsoft Defender voor Eindpunt in microsoft 365-beveiligingscentrum

1. **Toegangsgroepen maken voor MSSP-resources in Klant-AAD: Groepen**

    Deze groepen worden gekoppeld aan de rollen die u maakt in Defender voor Eindpunt in het Microsoft 365-beveiligingscentrum. Maak in de ad-tenant van de klant drie groepen om dit te doen. In onze voorbeeldbenadering maken we de volgende groepen:

    - Tier 1 Analyst 
    - Tier 2 Analyst 
    - MSSP-analist-goedkeurders  


2. Maak Defender voor eindpuntrollen voor de juiste toegangsniveaus in Customer Defender voor Eindpunt in microsoft 365 beveiligingscentrumrollen en -groepen.

    Als u RBAC wilt inschakelen in het microsoft 365-beveiligingscentrum van de klant, hebt u toegang tot machtigingen > eindpunten rollen & groepen > Rollen met een gebruikersaccount met globale **beheerders- of** beveiligingsbeheerdersrechten.

    ![Afbeelding van MSSP-toegang](../../media/mssp-access.png)

    Maak vervolgens RBAC-rollen om te voldoen aan de soc-laagbehoeften van MSSP. Koppel deze rollen aan de gemaakte gebruikersgroepen via 'Toegewezen gebruikersgroepen'.

    Twee mogelijke rollen:

    - **Tier 1-analisten** <br>
      Voer alle acties uit, behalve livereacties en beheer beveiligingsinstellingen.

    - **Laag 2-analisten** <br>
      Tier 1-mogelijkheden met de toevoeging aan [livereactie](/windows/security/threat-protection/microsoft-defender-atp/live-response)

    Zie Op rollen gebaseerde [toegangsbeheer gebruiken](/windows/security/threat-protection/microsoft-defender-atp/rbac)voor meer informatie.



## <a name="configure-governance-access-packages"></a>Governance Access-pakketten configureren

1.  **MSSP toevoegen als verbonden organisatie in Customer AAD: Identity Governance**
    
    Als u mssp toevoegt als een verbonden organisatie, kan de MSSP aanvragen en toegang hebben tot de inrichting. 

    Als u dit wilt doen, krijgt u in de ad-tenant van de klant toegang tot Identiteitsbeheer: Verbonden organisatie. Voeg een nieuwe organisatie toe en zoek naar uw MSSP Analyst-tenant via tenant-id of domein. We raden u aan een aparte AD-tenant te maken voor uw MSSP-analisten.

2. **Een resourcecatalogus maken in Customer AAD: Identity Governance**

    Resourcecatalogi zijn een logische verzameling toegangspakketten die zijn gemaakt in de AD-tenant van de klant.

    U doet dit door in de AD-tenant van de klant identiteitsbeheer: catalogi te openen en Nieuwe catalogus **toe te voegen.** In ons voorbeeld noemen we het **MSSP Accesses.** 

    ![Afbeelding van nieuwe catalogus](../../media/goverance-catalog.png)

    Zie Een catalogus met resources maken voor [meer informatie.](/azure/active-directory/governance/entitlement-management-catalog-create)


3. **Access-pakketten maken voor MSSP-resources Customer AAD: Identity Governance**

    Access-pakketten zijn de verzameling rechten en toegangen die een aangever na goedkeuring wordt verleend. 

    U doet dit door in de AD-tenant van de klant identiteitsbeheer: Access-pakketten te openen en Nieuw **Access-pakket toe te voegen.** Maak een toegangspakket voor de MSSP-goedkeurders en elke analistlaag. Met de volgende configuratie van Tier 1 Analyst wordt bijvoorbeeld een toegangspakket gemaakt dat:

    - Vereist dat een lid van de AD-groep **MSSP Analyst Approvers** nieuwe aanvragen autorizert
    - Heeft jaarlijkse toegangsbeoordelingen, waarbij de SOC-analisten een toegangsextensie kunnen aanvragen
    - Kan alleen worden aangevraagd door gebruikers in de SOC-tenant van MSSP
    - Access Auto verloopt na 365 dagen

    ![Afbeelding van nieuw toegangspakket](../../media/new-access-package.png)

    Zie Een nieuw [toegangspakket maken](/azure/active-directory/governance/entitlement-management-access-package-create)voor meer informatie.


4. **Koppeling voor toegangsaanvraag naar MSSP-resources van Customer AAD: Identity Governance**

    De koppeling Mijn Access-portal wordt door MSSP-SOC-analisten gebruikt om toegang te vragen via de gemaakte toegangspakketten. De koppeling is duurzaam, wat betekent dat dezelfde koppeling in de tijd kan worden gebruikt voor nieuwe analisten. De aanvraag van de analist wordt in een wachtrij geplaatst voor goedkeuring door de **MSSP-analist-goedkeurders.**


    ![Afbeelding van access-eigenschappen](../../media/access-properties.png)

    De koppeling bevindt zich op de overzichtspagina van elk toegangspakket.

## <a name="manage-access"></a>Toegang beheren 

1. Toegangsaanvragen controleren en machtigen in myaccess klant en/of MSSP.

    Access-aanvragen worden beheerd in de klant My Access, door leden van de groep MsSP Analyst Approvers.

    U kunt dit doen door de myaccess van de klant te openen met behulp van:  `https://myaccess.microsoft.com/@<Customer Domain >` . 

    Voorbeeld:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`   
2. Aanvragen goedkeuren of weigeren in **de sectie Goedkeuringen** van de gebruikersinterface.

     Op dit moment is de toegang tot analisten ingericht en moet elke analist toegang hebben tot het Microsoft 365-beveiligingscentrum van de klant: 

    `https://security.microsoft.com/?tid=<CustomerTenantId>` met de machtigingen en rollen die aan hen zijn toegewezen.

> [!IMPORTANT]
> Gedelegeerde toegang tot Microsoft Defender voor Eindpunt in het Microsoft 365-beveiligingscentrum biedt momenteel toegang tot één tenant per browservenster.