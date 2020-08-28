---
title: Toegang voorbereiden tot on-premises bronnen voor Microsoft Managed Desktop
description: Belangrijke stappen om ervoor te zorgen dat een Azure AD kan communiceren met on-premises AD om verificatie te verschaffen
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 7181e81a2db94ce26fb8601f8b9156c65084c439
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289577"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Toegang voorbereiden tot on-premises bronnen voor Microsoft Managed Desktop

In Microsoft Managed Desktop worden apparaten automatisch lid geworden van Azure Active Directory (Azure AD). Dit betekent dat als u een on-premises Active Directory gebruikt, u een aantal zaken moet controleren om ervoor te zorgen dat apparaten die deel uitmaken van Azure AD, kunnen communiceren met uw on-premises Active Directory. 

> [!NOTE]  
> *Hybride* Azure AD join wordt niet ondersteund door Microsoft Managed Desktop.

Azure Active Directory zorgt ervoor dat uw gebruikers gebruikmaken van eenmalige aanmelding (SSO), wat betekent dat ze normaliter niet telkens wanneer ze bronnen gebruiken.

Zie voor meer informatie over het deelnemen aan Azure Active Directory [: de implementatie van Azure AD bijwonen plannen](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan). Voor achtergrondinformatie over eenmalige aanmelding (SSO) op apparaten die deel uitmaken van Azure AD, raadpleegt [u hoe SSO-on-premises resources werken op aan Azure AD gekoppelde apparaten](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works).


In dit onderwerp wordt uitgelegd wat u moet controleren om ervoor te zorgen dat apps en andere bronnen die afhankelijk zijn van lokale Active Directory-connectiviteit, soepel werken via Microsoft Managed Desktop.


## <a name="single-sign-on-for-on-premises-resources"></a>Eenmalige aanmelding voor on-premises resources

Eenmalige aanmelding (SSO) met behulp van UPN en wachtwoord is standaard ingeschakeld op door Microsoft beheerde bureaublad apparaten. Maar uw gebruikers kunnen ook Windows hello voor bedrijven gebruiken, waarvoor extra instellingsstappen zijn vereist. 

### <a name="single-sign-on-by-using-upn-and-password"></a>Eenmalige aanmelding met behulp van UPN en wachtwoord

In de meeste organisaties kunnen de gebruikers eenmalige aanmelding gebruiken om verificatie via UPN en wachtwoord op door Microsoft beheerde bureaublad apparaten te gebruiken. Als u er zeker van wilt zijn dat dit werkt, controleert u het volgende:

- Ga na of Azure AD Connect is ingesteld en gebruikmaakt van een on-premises Active Directory-server waarop Windows Server 2008 R2 of later wordt uitgevoerd.
- Ga na of Azure AD Connect een ondersteunde versie voert en is ingesteld voor het synchroniseren van deze drie kenmerken met Azure AD: 
    - DNS-domeinnaam van de on-premises Active Directory (waar de gebruikers zich bevinden)
    - NetBIOS van uw on-premises Active Directory (waar de gebruikers zich bevinden)
    - SAM-accountnaam van de gebruiker


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>Eenmalige aanmelding met Windows hello voor bedrijven

Microsoft beheerde bureaublad apparaten bieden uw gebruikers ook een snelle, wacht woordloze ervaring met Windows hello voor bedrijven. Als u er zeker van wilt zijn dat Windows hello voor bedrijven werkt zonder dat uw gebruikers de juiste UPN en het wachtwoord moeten opgeven, gaat u naar [Azure ad-apparaten met een on-premises eenmalige aanmelding configureren voor on-premises eenmalige aanmelding met Windows hello voor bedrijven](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) om de vereisten te controleren en volgt u de stappen die hier worden beschreven.


## <a name="apps-and-resources-that-use-authentication"></a>Apps en bronnen die gebruikmaken van authenticatie

Zie informatie over de manier waarop u [toepassingen en bronnen](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) in de Azure-inhoudsset hebt ingesteld voor uitgebreide informatie over het instellen van apps voor gebruik met Azure Active Directory. In het overzicht:


- Als u **Cloud-apps**gebruikt, zoals de apps die zijn toegevoegd aan de galerie van Azure AD-apps, is er geen verdere voorbereiding voor het gebruik van Microsoft beheerde bureaublad. Voor alle Win32-apps die niet gebruikmaken van web account manager (WAM), wordt er mogelijk wel gezocht naar gebruikers voor verificatie.

- Voor apps die **on-premises worden gehost**, dient u deze apps toe te voegen aan de lijst met vertrouwde websites in uw browsers. Dit schakelt Windows-verificatie in om naadloos samen te werken, zonder dat de gebruiker om referenties wordt gevraagd. U doet dit door te verwijzen naar [vertrouwde websites](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref#trusted-sites) in de [naslag voor configureerbare instellingen](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref).

- Als u gebruikmaakt van Active Directory federatieve Services, controleert u of EENMALIGe aanmelding is ingeschakeld met behulp van de stappen in [eenmalige aanmelding controleren en beheren met AD FS](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100)). 

- Voor apps die **on-premises zijn en oudere protocollen gebruiken**, is geen extra configuratie vereist, zolang de apparaten toegang hebben tot een on-premises domeincontroller om te verifiëren. Als u de toegang tot deze toepassingen wilt waarborgen, moet u ook Azure AD-toepassings proxy implementeren. Zie [externe toegang tot on-premises toepassingen via de toepassings proxy van Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)voor meer informatie.

- Apps die **on-premises worden uitgevoerd en afhankelijk zijn van computerauthenticatie** worden niet ondersteund, dus kunt u het beste deze vervangen door nieuwere versies.

### <a name="network-shares-that-use-authentication"></a>Netwerkshares die gebruikmaken van authenticatie

U hoeft geen extra instellingen voor gebruikers toegang te krijgen tot netwerkshares, mits de apparaten toegang hebben tot een on-premises domeincontroller via een UNC-pad.

### <a name="printers"></a>Faxprinter

Beheerde bureaublad apparaten van Microsoft kunnen geen verbinding maken met printers die zijn gepubliceerd in een on-premises Active Directory, tenzij u [hybride Cloud afdrukken](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)hebt geconfigureerd.

Hoewel printers niet automatisch worden gedetecteerd in een omgeving met alleen Cloud, kunnen gebruikers on-premises printers gebruiken met behulp van het pad of de naam van de printer, mits de apparaten toegang hebben tot een on-premises domeincontroller.

<!--add fuller material on printers when available-->
