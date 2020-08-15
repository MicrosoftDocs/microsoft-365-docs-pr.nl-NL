---
title: Problemen met adreslijstsynchronisatie in Microsoft 365 oplossen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Priority
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MBS150
ms.assetid: 79c43023-5a47-45ae-8068-d8a26eee6bc2
description: Beschrijving van de meest voorkomende oorzaken van problemen met adreslijstsynchronisatie in Microsoft 365 en enkele manieren waarmee u ze kunt oplossen.
ms.openlocfilehash: 80b4a88e91230a8736f209ecd65c58b2882c25d6
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689485"
---
# <a name="fixing-problems-with-directory-synchronization-for-microsoft-365"></a>Problemen met adreslijstsynchronisatie in Microsoft 365 oplossen

Met adreslijstsynchronisatie kunt u gebruikers en groepen on-premises blijven beheren, en toevoegingen, verwijderingen en wijzigingen met de cloud synchroniseren. De installatie is een beetje ingewikkeld en het kan soms lastig zijn om de bron van de problemen te identificeren. We beschikken over informatiebronnen waarmee u potentiële problemen kunt opsporen en oplossen.
  
## <a name="how-do-i-know-if-something-is-wrong"></a>Hoe weet ik of er iets mis is?

De eerste aanwijzing dat er iets mis is, is wanneer de tegel DirSync-status in het Microsoft 365-beheercentrum aangeeft dat er een probleem is.
  
U ontvangt ook een e-mailbericht (op het alternatieve e-mailadres en uw beheerderse-mailadres) van Microsoft 365 waarin wordt aangegeven dat er adreslijstsynchronisatiefouten zijn opgetreden in uw tenant. Zie [Fouten met adreslijstsynchronisatie herkennen in Microsoft 365](identify-directory-synchronization-errors.md) voor meer informatie.
  
## <a name="how-do-i-get-azure-active-directory-connect-tool"></a>Hoe kom ik aan het hulpprogramma Azure Active Directory Connect?

Ga in het [Microsoft 365-beheercentrum](https://admin.microsoft.com) naar **Gebruikers** \> **Actieve gebruikers**. Klik op het menu **Meer** (drie puntjes) en selecteer **Adreslijstsynchronisatie**. 
  
Volg de [instructies in de wizard](set-up-directory-synchronization.md) om Azure AD Connect te downloaden. 
  
Als u nog steeds gebruikmaakt van Azure Active Directory (Azure AD) Sync (DirSync), vindt u in [Problemen oplossen met de installatie van het hulpprogramma Azure Active Directory-synchronisatie en foutberichten van de wizard Configuratie in Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=396717) informatie over de systeemvereisten voor de installatie van dirsync, de machtigingen die u nodig hebt en het oplossen van veelvoorkomende fouten. 
  
Zie [de instructies voor het uitvoeren van een upgrade](https://go.microsoft.com/fwlink/p/?LinkId=733240) als u Azure AD Sync wilt bijwerken naar Azure AD Connect.
  
## <a name="resolving-common-causes-of-problems-with-directory-synchronization-in-microsoft-365"></a>Veelvoorkomende oorzaken van problemen met adreslijstsynchronisatie in Microsoft 365 oplossen

### <a name="synchronized-objects-arent-appearing-or-updating-online-or-im-getting-synchronization-error-reports-from-the-service"></a>Gesynchroniseerde objecten worden niet online weergegeven of bijgewerkt, of ik krijg van de service foutrapporten over synchronisatie.

- [Tolerantie voor identiteitssynchronisatie en dubbele kenmerken](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency)

### <a name="i-have-an-alert-in-the-admin-center-or-am-receiving-automated-emails-that-there-hasnt-been-a-recent-synchronization-event"></a>Ik krijg een melding in het beheercentrum of ik ontvang automatisch e-mailberichten dat er geen recente synchronisatiegebeurtenis is geweest
- [Verbindingsproblemen met Azure AD Connect oplossen](https://docs.microsoft.com/azure/active-directory/hybrid/tshoot-connect-connectivity)
- [Azure AD Connect-accounts en -machtigingen](https://go.microsoft.com/fwlink/p/?LinkId=820598)
- [Azure AD Connect-synchronisatie: het Azure AD-serviceaccount beheren](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-azureadaccount)
- [Adreslijstsynchronisatie naar Azure Active Directory is gestopt of u krijgt de waarschuwing dat de synchronisatie al meer dan een dag niet is geregistreerd](https://support.microsoft.com/help/2882421/directory-synchronization-to-azure-active-directory-stops-or-you-re-warned-that-sync-hasn-t-registered-in-more-than-a-day)

### <a name="password-hashes-arent-synchronizing-or-im-seeing-an-alert-in-the-admin-center-that-there-hasnt-been-a-recent-password-hash-synchronization"></a>Wachtwoordhashes worden niet gesynchroniseerd of ik zie in het beheercentrum een melding dat er geen recente wachtwoord-hashsynchronisatie is geweest
- [Wachtwoord-hashsynchronisatie met Azure AD Connect-synchronisatie implementeren](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)

### <a name="im-seeing-an-alert-that-object-quota-exceeded"></a>Ik krijg een waarschuwing dat het objectquotum is overschreden
- We hebben een ingebouwd objectquotum ter bescherming van de service. Als er zich te veel objecten bevinden in de adreslijst die moet worden gesynchroniseerd met Microsoft 365, moet u [contact opnemen met de ondersteuning voor bedrijfsproducten](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) om het quotum verhogen.

### <a name="i-need-to-know-which-attributes-are-synchronized"></a>Ik moet weten welke kenmerken worden gesynchroniseerd
- [Hier](https://go.microsoft.com/fwlink/p/?LinkId=396719) vindt u een lijst met alle kenmerken die worden gesynchroniseerd tussen on-premises en de cloud.

### <a name="i-cant-manage-or-remove-objects-that-were-synchronized-to-the-cloud"></a>Ik kan geen objecten beheren of verwijderen die zijn gesynchroniseerd met de cloud
- Bent u er klaar voor alleen objecten in de cloud te beheren? Of is er een object dat on-premises is verwijderd, maar dat vastzit in de cloud? Raadpleeg [het oplossen van problemen met synchronisatie](https://go.microsoft.com/fwlink/p/?linkid=842044) en het [ondersteuningsartikel](https://go.microsoft.com/fwlink/p/?LinkId=396720) voor hulp bij het oplossen van deze problemen.

### <a name="i-got-an-error-message-that-my-company-has-exceeded-the-number-of-objects-that-can-be-synchronized"></a>Ik krijg het foutbericht dat mijn bedrijf het aantal objecten dat kan worden gesynchroniseerd, heeft overschreden.
- U kunt [hier](https://go.microsoft.com/fwlink/p/?LinkId=396721) meer lezen over dit probleem.
   
## <a name="other-resources"></a>Overige informatiebronnen

- [Script om dubbele UPN's op te lossen](https://go.microsoft.com/fwlink/p/?LinkId=396725)
    
- [Een niet-routeerbaar domein (zoals .lokaal) voorbereiden op adreslijstsynchronisatie](prepare-a-non-routable-domain-for-directory-synchronization.md)
    
- [Script om het totale aantal gesynchroniseerde objecten te tellen](https://go.microsoft.com/fwlink/p/?LinkId=396726)
    
- [Problemen met AD FS 2.0 oplossen](https://go.microsoft.com/fwlink/p/?LinkId=396727)
    
- [PowerShell gebruiken om lege DisplayName-kenmerken voor groepen met e-mail op te lossen](https://go.microsoft.com/fwlink/p/?LinkId=396728)
    
- [PowerShell gebruiken om dubbele UPN's op te lossen](https://go.microsoft.com/fwlink/p/?LinkId=396730)
    
- [PowerShell gebruiken om dubbele e-mailadressen op te lossen](https://go.microsoft.com/fwlink/p/?LinkId=396731)
    
