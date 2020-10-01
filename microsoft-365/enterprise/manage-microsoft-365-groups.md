---
title: Microsoft 365-groepen
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
ms.openlocfilehash: a01bf5dcc0b87cbdce8d7044b666cfb3a16a5aa9
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328498"
---
# <a name="manage-microsoft-365-groups"></a>Microsoft 365-groepen

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

U kunt Microsoft 365-groepen op verschillende manieren beheren, afhankelijk van de configuratie. U kunt gebruikersaccounts beheren in het [Microsoft 365-Beheercentrum](https://docs.microsoft.com/microsoft-365/admin/add-users/), powershell, in Active Directory Domain Services (AD DS) of in het [Azure Active Directory-beheercentrum (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal). 

## <a name="plan-for-where-and-how-you-will-manage-your-groups"></a>Plannen waar en hoe u uw groepen beheert

Waar en hoe u uw gebruikersaccounts kunt beheren, is afhankelijk van het identiteits model dat u wilt gebruiken voor uw Microsoft 365. De twee algemene modellen zijn alleen in de Cloud en hybride.
  
### <a name="cloud-only"></a>Alleen in de cloud

U maakt en beheert groepen met:

- [Het Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- [PowerShell](maintain-group-membership-with-microsoft-365-powershell.md)
- [Azure AD-Beheercentrum](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    
### <a name="hybrid"></a>Hybride

AD DS-groepen worden gesynchroniseerd met Microsoft 365 vanuit AD DS, zodat u on-premises AD DS-hulpprogramma's moet gebruiken voor het beheren van deze groepen.

U kunt ook Azure AD-groepen maken en beheren die geen deel uitmaken van Active Directory-groepen, maar u kunt ook gebruikers en groepen uit AD DS opnemen. In dit geval kunt u het volgende doen:

- [Het Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- [PowerShell](maintain-group-membership-with-microsoft-365-powershell.md)
- [Azure AD-Beheercentrum](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

## <a name="allow-users-to-create-and-manage-their-own-groups"></a>Bied gebruikers de mogelijkheid om hun eigen groepen te maken en beheren

In azure AD kunnen groepen worden beheerd door groepseigenaren in plaats van IT-beheerders. Met deze functie, die *selfservice-groepsbeheer* wordt genoemd, kunnen groepseigenaren waaraan geen beheerdersrol is toegewezen, beveiligingsgroepen maken en beheren. 

Gebruikers kunnen lidmaatschap van een beveiligingsgroep aanvragen en dit verzoek wordt vervolgens naar de eigenaar van de groep gestuurd, in plaats van een IT-beheerder. Dit maakt het mogelijk om het groepslidmaatschap te laten beheren door team-, project- of bedrijfseigenaren die het zakelijke doel van de groep begrijpen en het lidmaatschap ervan kunnen beheren.

>[!Note]
>Selfservice-groepsbeheer is alleen beschikbaar voor Azure AD-beveiligingsgroepen en Microsoft 365-groepen. Deze functie is niet beschikbaar voor groepen met e-mail, distributielijsten of groepen die zijn gesynchroniseerd vanuit AD DS.
>

Zie de [instructies voor het configureren van een Azure AD-groep voor selfservice-beheer](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) voor meer informatie.

## <a name="set-up-dynamic-group-membership"></a>Dynamisch groepslidmaatschap instellen

Azure AD biedt ondersteuning voor het configureren van een reeks regels waarmee automatisch gebruikersaccounts worden toegevoegd of verwijderd als lid van een Azure AD-groep. Dit wordt *dynamisch groepslidmaatschap* genoemd. De regels zijn gebaseerd op kenmerken van gebruikersaccounts, zoals Afdeling of Land.

De regels worden als volgt toegepast:

- Als een nieuw gebruikersaccount aan alle regels voor de groep voldoet, wordt het lid.
- Als een gebruikersaccount geen lid is van de groep, maar de bijbehorende kenmerken zodanig worden gewijzigd dat deze voldoen aan alle regels voor de groep, wordt het account lid van die groep.
- Als een gebruikersaccount niet voldoet aan alle regels voor de groep, wordt het niet toegevoegd aan de groep.
- Als een gebruikersaccount lid is van de groep, maar de bijbehorende kenmerken zodanig worden gewijzigd dat het niet meer voldoet aan alle regels voor de groep, wordt het account als lid van de groep verwijderd.

Als u dynamisch lidmaatschap wilt gebruiken, moet u eerst bepalen welke sets groepen een gemeenschappelijke set gebruikersaccountkenmerken hebben. Zo moeten bijvoorbeeld alle leden van de afdeling Verkoop zich bevinden in de Azure AD-groep Verkoop op basis van het gebruikersaccountkenmerk Afdeling met de waarde 'Verkoop'.

Zie de [instructies voor het maken en configureren van de regels voor een dynamische Azure AD-groep](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

## <a name="set-up-automatic-licensing"></a>Automatische licentie instellen

U kunt beveiligingsgroepen configureren in azure AD om automatisch licenties toe te wijzen aan een reeks abonnementen voor alle leden van de groep. Dit wordt *licenties op groepsbasis* genoemd. Als een gebruikersaccount wordt toegevoegd aan of verwijderd uit de groep, worden de licenties voor de groepsabonnementen automatisch toegewezen aan of verwijderd van het gebruikersaccount. 

Voor Microsoft 365 Enterprise worden Azure AD-beveiligingsgroepen geconfigureerd om de juiste Microsoft 365 Enterprise-licentie toe te wijzen.

Zorg ervoor dat u genoeg licenties hebt voor alle groepsleden. Als u niet genoeg licenties hebt, krijgen nieuwe gebruikers geen licenties totdat er weer licenties beschikbaar zijn.

>[!Note]
>Voor groepen die Azure B2B-accounts (business-to-business) bevatten, dient u licenties op groepsbasis niet te configureren.
>

Zie [beginselen van licentieverlening op basis van groepen in azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)voor meer informatie.

Zie de [instructies voor het configureren van de op groepen gebaseerde licentieverlening voor een Azure-beveiligingsgroep](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).
