---
title: Toegang voorbereiden tot on-premises bronnen voor Microsoft Managed Desktop
description: Belangrijke stappen om ervoor te zorgen dat een Azure AD kan communiceren met on-premises AD om verificatie te bieden
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 7caeee6f476fea7881884cea20bd2a59db2c13d9
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530041"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Toegang voorbereiden tot on-premises bronnen voor Microsoft Managed Desktop

In Microsoft Managed Desktop worden apparaten automatisch verbonden met Azure Active Directory (Azure AD). Dit betekent dat als u een on-premises Active Directory gebruikt, u een aantal dingen moet controleren om ervoor te zorgen dat apparaten die zijn aangesloten bij Azure AD kunnen communiceren met uw on-premises Active Directory. 

> [!NOTE]  
> *Hybride Hybride* Azure AD join wordt niet ondersteund door Microsoft Managed Desktop.

Met Azure Active Directory kunnen uw gebruikers profiteren van Single Sign-On (SSO), wat betekent dat ze doorgaans niet elke keer dat ze resources gebruiken referenties hoeven te verstrekken.

Raadpleeg Hoe: Uw [Azure AD join-implementatie](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)plannen voor informatie over lid worden van Azure Active Directory. Zie [Hoe SSO-on-premises resources werken op Azure AD-apparaten voor](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works)achtergrondinformatie over SSO -apparaten die zijn aangesloten bij Azure AD.


In dit onderwerp wordt uitgelegd wat u moet controleren om ervoor te zorgen dat apps en andere bronnen die afhankelijk zijn van lokale Active Directory-connectiviteit, soepel werken met Microsoft Managed Desktop.


## <a name="single-sign-on-for-on-premises-resources"></a>Eén aanmelding voor on-premises bronnen

Single Sign-On (SSO) met BEHULP VAN UPN en wachtwoord is standaard ingeschakeld op Microsoft Managed Desktop Devices. Maar uw gebruikers kunnen ook Windows Hello voor Bedrijven gebruiken, wat extra installatiestappen vereist. 

### <a name="single-sign-on-by-using-upn-and-password"></a>Eenmalige aanmelding met UPN en wachtwoord

In de meeste organisaties kunnen uw gebruikers SSO gebruiken om te verifiëren met UPN en wachtwoord op Microsoft Managed Desktop Devices. Echter, om ervoor te zorgen dat dit zal werken, moet u dubbel controleren het volgende:

- Controleer of Azure AD Connect is ingesteld en gebruik maakt van een on-premises Active Directory-server met Windows Server 2008 R2 of hoger.
- Controleer of Azure AD Connect een ondersteunde versie uitvoert en is ingesteld om deze drie kenmerken te synchroniseren met Azure AD: 
    - DNS-domeinnaam van de on-premises Active Directory (waar de eindgebruikers zich bevinden)
    - NetBIOS van uw on-premises Active Directory (waar de eindgebruikers zich bevinden)
    - SAM-accountnaam van de gebruiker


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>Eén aanmelding met Windows Hello voor Bedrijven

Microsoft Managed Desktop-apparaten bieden uw gebruikers ook een snelle, wachtwoordloze ervaring door Windows Hello for Business in te zetten. Ga naar [Azure AD-apparaten configureren voor on-premises aanmeldingsapparaten voor on-premises eenmalig aanmelden met Windows Hello voor Bedrijven](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) om de vereisten te controleren en vervolgens de stappen te volgen die daar zijn vermeld.


## <a name="apps-and-resources-that-use-authentication"></a>Apps en bronnen die verificatie gebruiken

Raadpleeg [Overwegingen voor toepassingen en resources begrijpen](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) in de Azure-inhoudsset voor volledige richtlijnen voor het instellen van apps om met Azure Active Directory te werken. Samengevat:


- Als u cloudgebaseerde apps gebruikt, zoals apps die zijn toegevoegd aan de Azure **AD-app-galerij,** hebben de meeste geen verdere voorbereiding nodig om met Microsoft Managed Desktop te werken. Alle Win32-apps die geen gebruik maken van Web Account Manager (WAM) kunnen gebruikers echter nog steeds om verificatie vragen.

- Voor apps die **on-premises**worden gehost, moet u deze apps toevoegen aan de lijst met vertrouwde sites in uw browsers. Hierdoor kan Windows-verificatie naadloos werken, zonder dat gebruikers om referenties worden gevraagd. Raadpleeg hiervoor Vertrouwde [sites](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref#trusted-sites) in de [referentie Configureerbare instellingen](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref).

- Als u Active Directory Federated Services gebruikt, controleert u of SSO is ingeschakeld met de stappen in [Het verifiëren en beheren van eenmalige aanmelding met AD FS](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100)). 

- Voor apps die **on-premises zijn en oudere protocollen gebruiken,** is geen extra installatie vereist, zolang de apparaten toegang hebben tot een on-premises domeincontroller om te verifiëren. Als u echter veilige toegang voor deze toepassingen wilt bieden, moet u Azure AD Application Proxy implementeren. Zie [Externe toegang tot on-premises toepassingen via de Application Proxy van Azure Active Directory voor](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)meer informatie.

- Apps die on-premises worden uitgevoerd **en afhankelijk zijn van machineverificatie** worden niet ondersteund, dus u moet overwegen deze te vervangen door nieuwere versies.

### <a name="network-shares-that-use-authentication"></a>Netwerkshares die verificatie gebruiken

Er is geen extra installatie vereist voor gebruikers om toegang te krijgen tot netwerkshares, zolang de apparaten toegang hebben tot een on-premises domeincontroller met behulp van een UNC-pad.

### <a name="printers"></a>Printers

Microsoft Managed Desktop-apparaten kunnen geen verbinding maken met printers die zijn gepubliceerd op uw on-premises Active Directory, tenzij u [Hybride cloudafdruk](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)hebt geconfigureerd.

Hoewel printers niet automatisch kunnen worden gedetecteerd in een cloudomgeving, kunnen uw gebruikers on-premises printers gebruiken met behulp van het printerpad of het printerwachtrijpad, zolang de apparaten toegang hebben tot een on-premises domeincontroller.

<!--add fuller material on printers when available-->
