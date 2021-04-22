---
title: Toegang verlenen aan een beheerde beveiligingsserviceprovider (MSSP)
description: Neem de benodigde stappen voor het configureren van MSSP-integratie met Microsoft Defender voor Eindpunt
keywords: managed security service provider, mssp, configure, integration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 320355f838db5dbb1540350e95e4cc0645acd805
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932749"
---
# <a name="grant-managed-security-service-provider-mssp-access-preview"></a>Toegang verlenen voor beheerde beveiligingsserviceproviders (MSSP) (preview)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!IMPORTANT] 
>Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden. Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.

Als u een oplossing voor gedelegeerde toegang met meerdere tenants wilt implementeren, voert u de volgende stappen uit:

1. Schakel [toegangsbeheer op basis van rollen](rbac.md) in defender voor eindpunt in en maak verbinding met Ad-groepen (Active Directory).

2. [Beheertoegangspakketten configureren voor toegangsaanvraag](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) en inrichting.

3. Toegangsaanvragen en -audits beheren in [Microsoft Myaccess](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve).

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint"></a>Toegangsbesturingselementen op basis van rollen inschakelen in Microsoft Defender voor Eindpunt

1. **Toegangsgroepen maken voor MSSP-resources in Klant-AAD: Groepen**

    Deze groepen worden gekoppeld aan de rollen die u maakt in Defender voor Eindpunt. Maak in de ad-tenant van de klant drie groepen om dit te doen. In onze voorbeeldbenadering maken we de volgende groepen:

    - Tier 1 Analyst 
    - Tier 2 Analyst 
    - MSSP-analist-goedkeurders  


2. Maak Defender voor eindpuntrollen voor de juiste toegangsniveaus in Customer Defender voor Eindpunt.

    Als u RBAC wilt inschakelen in het Microsoft Defender-beveiligingscentrum van de klant, hebt u toegang tot Instellingen **> Machtigingen > Rollen** en 'Rollen inschakelen', vanuit een gebruikersaccount met globale beheerders- of beveiligingsbeheerdersrechten.

    ![Afbeelding van MSSP-toegang](images/mssp-access.png)

    Maak vervolgens RBAC-rollen om te voldoen aan de soc-laagbehoeften van MSSP. Koppel deze rollen aan de gemaakte gebruikersgroepen via 'Toegewezen gebruikersgroepen'.

    Twee mogelijke rollen:

    - **Tier 1-analisten** <br>
      Voer alle acties uit, behalve livereacties en beheer beveiligingsinstellingen.

    - **Laag 2-analisten** <br>
      Tier 1-mogelijkheden met de toevoeging aan [livereactie](live-response.md)

    Zie Op rollen gebaseerde [toegangsbeheer gebruiken](rbac.md)voor meer informatie.



## <a name="configure-governance-access-packages"></a>Governance Access-pakketten configureren

1.  **MSSP toevoegen als verbonden organisatie in Customer AAD: Identity Governance**
    
    Als u mssp toevoegt als een verbonden organisatie, kan de MSSP aanvragen en toegang hebben tot de inrichting. 

    Als u dit wilt doen, krijgt u in de ad-tenant van de klant toegang tot Identiteitsbeheer: Verbonden organisatie. Voeg een nieuwe organisatie toe en zoek naar uw MSSP Analyst-tenant via tenant-id of domein. We raden u aan een aparte AD-tenant te maken voor uw MSSP-analisten.

2. **Een resourcecatalogus maken in Customer AAD: Identity Governance**

    Resourcecatalogi zijn een logische verzameling toegangspakketten die zijn gemaakt in de AD-tenant van de klant.

    U doet dit door in de AD-tenant van de klant identiteitsbeheer: catalogi te openen en Nieuwe catalogus **toe te voegen.** In ons voorbeeld noemen we het **MSSP Accesses.** 

    ![Afbeelding van nieuwe catalogus](images/goverance-catalog.png)

    Zie Een catalogus met resources maken voor [meer informatie.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create)


3. **Access-pakketten maken voor MSSP-resources Customer AAD: Identity Governance**

    Access-pakketten zijn de verzameling rechten en toegangen die een aangever na goedkeuring wordt verleend. 

    U doet dit door in de AD-tenant van de klant identiteitsbeheer: Access-pakketten te openen en Nieuw **Access-pakket toe te voegen.** Maak een toegangspakket voor de MSSP-goedkeurders en elke analistlaag. Met de volgende configuratie van Tier 1 Analyst wordt bijvoorbeeld een toegangspakket gemaakt dat:

    - Vereist dat een lid van de AD-groep **MSSP Analyst Approvers** nieuwe aanvragen autorizert
    - Heeft jaarlijkse toegangsbeoordelingen, waarbij de SOC-analisten een toegangsextensie kunnen aanvragen
    - Kan alleen worden aangevraagd door gebruikers in de SOC-tenant van MSSP
    - Access Auto verloopt na 365 dagen

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van nieuw toegangspakket](images/new-access-package.png)

    Zie Een nieuw [toegangspakket maken](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create)voor meer informatie.


4. **Koppeling voor toegangsaanvraag naar MSSP-resources van Customer AAD: Identity Governance**

    De koppeling Mijn Access-portal wordt door MSSP-SOC-analisten gebruikt om toegang te vragen via de gemaakte toegangspakketten. De koppeling is duurzaam, wat betekent dat dezelfde koppeling in de tijd kan worden gebruikt voor nieuwe analisten. De aanvraag van de analist wordt in een wachtrij geplaatst voor goedkeuring door de **MSSP-analist-goedkeurders.**

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van access-eigenschappen](images/access-properties.png)

    De koppeling bevindt zich op de overzichtspagina van elk toegangspakket.

## <a name="manage-access"></a>Toegang beheren 

1. Toegangsaanvragen controleren en machtigen in myaccess klant en/of MSSP.

    Access-aanvragen worden beheerd in de klant My Access, door leden van de groep MsSP Analyst Approvers.

    U kunt dit doen door de myaccess van de klant te openen met behulp van:  `https://myaccess.microsoft.com/@<Customer Domain >` . 

    Voorbeeld:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`   
2. Aanvragen goedkeuren of weigeren in **de sectie Goedkeuringen** van de gebruikersinterface.

    Op dit moment is de toegang tot analisten ingericht en moet elke analist toegang hebben tot het Microsoft Defender-beveiligingscentrum van de klant: `https://securitycenter.Microsoft.com/?tid=<CustomerTenantId>`

## <a name="related-topics"></a>Verwante onderwerpen
- [Toegang tot de MSSP-klantportal](access-mssp-portal.md)
- [Waarschuwingsmeldingen configureren](configure-mssp-notifications.md)
- [Waarschuwingen ophalen van de klant-tenant](fetch-alerts-mssp.md)



 

