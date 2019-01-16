---
title: Toestaan dat aan een domein toegevoegde Windows 10-apparaten door Microsoft 365 Business worden beheerd
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Informatie over het inschakelen van Microsoft 365 te beschermen lokale AD verbonden apparaten met Windows 10.
ms.openlocfilehash: 6e66a2c5417c9037232c1ada654d4cac3c520607
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2019
ms.locfileid: "26982652"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>Toestaan dat aan een domein toegevoegde Windows 10-apparaten door Microsoft 365 Business worden beheerd

Als uw organisatie gebruikmaakt van Windows Server Active Directory op lokalen, kunt u Microsoft 365 Business instellen ter bescherming van uw Windows 10-apparaten, terwijl zij toch toegang tot bronnen voor ruimten die lokale verificatie vereisen. U kunt dit instellen door de eerste synchronisatie van Active Directory met Azure Active Directory, gevolgd door de Windows 10-apparaten met Azure Active Directory registreren en deze inschrijven voor mobiel Apparaatbeheer door Microsoft 365 Business.
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a>Apparaten die deel uitmaakt van een domein wordt beheerd door Microsoft 365 Business instellen

Om in te stellen van uw organisatie deel uitmaakt van een domein apparaten om te profiteren van de mogelijkheden die Azure Active Directory ondersteunt naast Active Directory voor het bedrijf, kunt u de **hybride Azure AD verbonden apparaten**implementeren. Dit zijn apparaten die deel van zowel op ruimten Active Directory en Azure Active Directory uitmaken. Hybride Azure AD verbonden apparaten kunnen worden beveiligd en beheerd door Microsoft 365 Business... 
  
De stappen hieronder om uw Windows 10-apparaten hybride Azure AD toegevoegd en beheerd door Microsoft 365 Business.
  
1. Als u uw gebruikers, groepen en contactpersonen uit de lokale Active Directory naar Azure Active Directory, de Directory synchronisatie wizard en Azure Active Directory verbinding zoals beschreven in de [directory-synchronisatie voor Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)worden uitgevoerd.
    
    > [!NOTE]
    > De stappen zijn precies hetzelfde voor Microsoft 365 Business. 
  
2. Voordat u stap 3 waarmee Windows 10-apparaten hybride Azure AD lid worden voltooid, moet u om ervoor te zorgen dat u aan de volgende vereisten voldoen:
    
   - U gebruikt de meest recente versie van Azure AD verbinding.
    
   - Verbinding Azure AD is de computerobjecten van de gewenste hybride Azure AD verbonden apparaten gesynchroniseerd. Als u de computerobjecten behoren tot de specifieke organisatie-eenheden (OU), moeten u ervoor zorgen dat deze organisatie-eenheden zijn ingesteld voor synchronisatie in Azure AD ook verbinden.
    
3. Registreren bestaande domein behoren Windows 10-apparaten worden verbonden met Azure AD hybride en ze inschrijven voor mobiel Apparaatbeheer door Intune (Business Microsoft 365):
    
4. Volg de instructies stap voor stap in [hybride Azure Active Directory verbonden apparaten configureren](https://go.microsoft.com/fwlink/p/?linkid=872870). Hiermee schakelt u de synchronisatie van Active Directory op ruimten verbonden computers met Windows 10 en deze cloud klaar te maken.
    
5. Om te kunnen inschrijven voor een apparaat met Windows 10 voor mobile device management, Zie [inschrijven voor een Windows 10-apparaat met Intune met behulp van een Groepsbeleid](https://go.microsoft.com/fwlink/p/?linkid=872871) voor meer informatie. U kunt het groepsbeleid op een lokale computer niveau of voor bulkbewerkingen, kunt u deze instelling voor Groepsbeleid op uw server domain controller. 
    

