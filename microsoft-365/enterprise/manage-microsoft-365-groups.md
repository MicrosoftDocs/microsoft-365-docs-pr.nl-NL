---
title: Microsoft 365-groepen beheren
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Meer informatie over het beheren van Microsoft 365 groepen.
ms.openlocfilehash: 529bdb874661329497b103a1207b90625ad33a4b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911005"
---
# <a name="manage-microsoft-365-groups"></a>Microsoft 365-groepen beheren

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

U kunt Microsoft 365 groepen op verschillende manieren beheren, afhankelijk van uw configuratie. U kunt gebruikersaccounts beheren in [het Microsoft 365-beheercentrum](../admin/add-users/index.yml), PowerShell, in Ad DS (Active Directory Domain Services) of in het Azure Active Directory [(Azure AD) -beheercentrum.](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal) 

## <a name="plan-for-where-and-how-you-will-manage-your-groups"></a>Plannen voor waar en hoe u uw groepen gaat beheren

Waar en hoe u uw gebruikersaccounts kunt beheren, is afhankelijk van het identiteitsmodel dat u wilt gebruiken voor uw Microsoft 365. De twee algemene modellen zijn alleen-in de cloud en hybride.
  
### <a name="cloud-only"></a>Alleen in de cloud

U maakt en beheert groepen met:

- [Het Microsoft 365-beheercentrum](../admin/add-users/index.yml)
- [PowerShell](maintain-group-membership-with-microsoft-365-powershell.md)
- [Azure AD-beheercentrum](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    
### <a name="hybrid"></a>Hybride

AD DS-groepen worden gesynchroniseerd met Microsoft 365 ad DS, dus u moet on-premises AD DS-hulpprogramma's gebruiken om deze groepen te beheren.

U kunt ook Azure AD-groepen maken en beheren die los staan van AD DS-groepen, maar die gebruikers en groepen van AD DS kunnen bevatten. In dit geval kunt u het volgende gebruiken:

- [Het Microsoft 365-beheercentrum](../admin/add-users/index.yml)
- [PowerShell](maintain-group-membership-with-microsoft-365-powershell.md)
- [Azure AD-beheercentrum](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

## <a name="allow-users-to-create-and-manage-their-own-groups"></a>Bied gebruikers de mogelijkheid om hun eigen groepen te maken en beheren

Azure AD staat groepen toe die kunnen worden beheerd door groepseigenaren in plaats van DOOR IT-beheerders. Met deze functie, die *selfservice-groepsbeheer* wordt genoemd, kunnen groepseigenaren waaraan geen beheerdersrol is toegewezen, beveiligingsgroepen maken en beheren. 

Gebruikers kunnen lidmaatschap van een beveiligingsgroep aanvragen en dit verzoek wordt vervolgens naar de eigenaar van de groep gestuurd, in plaats van een IT-beheerder. Dit maakt het mogelijk om het groepslidmaatschap te laten beheren door team-, project- of bedrijfseigenaren die het zakelijke doel van de groep begrijpen en het lidmaatschap ervan kunnen beheren.

>[!Note]
>Selfservice-groepsbeheer is alleen beschikbaar voor Azure AD-beveiligingsgroepen en Microsoft 365-groepen. Deze is niet beschikbaar voor groepen met e-mail, distributielijsten of groepen die zijn gesynchroniseerd vanuit AD DS.
>

Zie de [instructies voor het configureren van een Azure AD-groep voor selfservice-beheer](/azure/active-directory/active-directory-accessmanagement-self-service-group-management) voor meer informatie.

## <a name="set-up-dynamic-group-membership"></a>Dynamisch groepslidmaatschap instellen

Azure AD ondersteunt het configureren van een reeks regels die gebruikersaccounts automatisch toevoegen of verwijderen als leden van een Azure AD-groep. Dit wordt *dynamisch groepslidmaatschap* genoemd. De regels zijn gebaseerd op kenmerken van gebruikersaccounts, zoals Afdeling of Land.

De regels worden als volgt toegepast:

- Als een nieuw gebruikersaccount aan alle regels voor de groep voldoet, wordt het lid.
- Als een gebruikersaccount geen lid is van de groep, maar de bijbehorende kenmerken zodanig worden gewijzigd dat deze voldoen aan alle regels voor de groep, wordt het account lid van die groep.
- Als een gebruikersaccount niet voldoet aan alle regels voor de groep, wordt het niet toegevoegd aan de groep.
- Als een gebruikersaccount lid is van de groep, maar de bijbehorende kenmerken zodanig worden gewijzigd dat het niet meer voldoet aan alle regels voor de groep, wordt het account als lid van de groep verwijderd.

Als u dynamisch lidmaatschap wilt gebruiken, moet u eerst bepalen welke sets groepen een gemeenschappelijke set gebruikersaccountkenmerken hebben. Zo moeten bijvoorbeeld alle leden van de afdeling Verkoop zich bevinden in de Azure AD-groep Verkoop op basis van het gebruikersaccountkenmerk Afdeling met de waarde 'Verkoop'.

Zie de [instructies voor het maken en configureren van de regels voor een dynamische Azure AD-groep](/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

## <a name="set-up-automatic-licensing"></a>Automatische licentie instellen

U kunt beveiligingsgroepen configureren in Azure AD om automatisch licenties van een set abonnementen toe te wijzen aan alle leden van de groep. Dit wordt *licenties op groepsbasis* genoemd. Als een gebruikersaccount wordt toegevoegd aan of verwijderd uit de groep, worden de licenties voor de groepsabonnementen automatisch toegewezen aan of verwijderd van het gebruikersaccount. 

Voor Microsoft 365 Enterprise worden Azure AD-beveiligingsgroepen geconfigureerd om de juiste Microsoft 365 Enterprise-licentie toe te wijzen.

Zorg ervoor dat u genoeg licenties hebt voor alle groepsleden. Als u niet genoeg licenties hebt, krijgen nieuwe gebruikers geen licenties totdat er weer licenties beschikbaar zijn.

>[!Note]
>Voor groepen die Azure B2B-accounts (business-to-business) bevatten, dient u licenties op groepsbasis niet te configureren.
>

Zie Basisbeginselen voor licenties op [basis van groepen in Azure AD voor meer informatie.](/azure/active-directory/active-directory-licensing-whatis-azure-portal)

Zie de [instructies voor het configureren van groepslicenties voor een Azure-beveiligingsgroep.](/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)