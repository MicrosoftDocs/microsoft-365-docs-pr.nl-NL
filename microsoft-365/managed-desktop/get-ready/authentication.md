---
title: On-premises toegang voor bronnen voorbereiden voor Microsoft Managed Desktop
description: Belangrijke stappen om ervoor te zorgen dat een Azure AD kan communiceren met on-premises AD om verificatie te bieden
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: c4ebe0c7ad3d1e197cf90cc975366df61d3b0cb5
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/23/2019
ms.locfileid: "42809845"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>On-premises toegang voor bronnen voorbereiden voor Microsoft Managed Desktop

In Microsoft Managed Desktop worden apparaten automatisch verbonden met Azure Active Directory (Azure AD). Dit betekent dat als u een on-premises Active Directory gebruikt, u een aantal dingen moet controleren om ervoor te zorgen dat apparaten die zijn aangesloten bij Azure AD kunnen communiceren met uw on-premises Active Directory. 

> [!NOTE]  
> *Hybride* Azure AD-join wordt niet ondersteund door Microsoft Managed Desktop.

Met Azure Active Directory kunnen uw gebruikers profiteren van Single Sign-On (SSO), wat betekent dat ze doorgaans niet elke keer dat ze resources gebruiken, referenties hoeven te verstrekken.

Raadpleeg voor informatie over deelname aan Azure Active Directory hoe u deelnemen aan: de implementatie van [uw Azure AD-deelname plannen](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan). Zie [Hoe SSO naar on-premises bronnen werkt op azure AD-apparaten](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works)voor achtergrondinformatie over Single Sign-On (SSO) op apparaten die zijn samengevoegd met Azure AD.


In dit onderwerp worden de dingen uitgelegd die u moet controleren om ervoor te zorgen dat apps en andere bronnen die afhankelijk zijn van lokale Active Directory-connectiviteit soepel werken met Microsoft Managed Desktop.


## <a name="single-sign-on-for-on-premises-resources"></a>Eén aanmelding voor on-premises resources

Single Sign-On (SSO) met UPN en wachtwoord is standaard ingeschakeld op Microsoft Managed Desktop Devices. Maar uw gebruikers kunnen ook Windows Hello voor Bedrijven gebruiken, waarvoor extra installatiestappen nodig zijn. 

### <a name="single-sign-on-by-using-upn-and-password"></a>Eén aanmelding met UPN en wachtwoord

In de meeste organisaties kunnen uw gebruikers SSO gebruiken om zich te verifiëren met UPN en een wachtwoord op Microsoft Managed Desktop Devices. Echter, om ervoor te zorgen dat dit zal werken, moet u dubbel-check het volgende:

- Controleer of Azure AD Connect is ingesteld en gebruik maakt van een on-premises Active Directory-server met Windows Server 2008 R2 of hoger.
- Controleer of Azure AD Connect een ondersteunde versie uitvoert en is ingesteld om deze drie kenmerken te synchroniseren met Azure AD: 
    - DNS-domeinnaam van de on-premises Active Directory (waar de eindgebruikers zich bevinden)
    - NetBIOS van uw on-premises Active Directory (waar de eindgebruikers zich bevinden)
    - SAM-accountnaam van de gebruiker


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>Aanmelding met Windows Hello voor Bedrijven

Microsoft Managed Desktop-apparaten bieden uw gebruikers ook een snelle, wachtwoordloze ervaring door gebruik te maken van Windows Hello voor Bedrijven. Ga naar [Azure AD-apparaten configureren voor on-premises single-sign on met Windows Hello voor Bedrijven](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) om de vereisten te controleren en volg vervolgens de daar gegeven stappen.


## <a name="apps-and-resources-that-use-authentication"></a>Apps en resources die verificatie gebruiken

Raadpleeg [overwegingen begrijpen voor toepassingen en resources](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) in de Azure-inhoudsset voor volledige richtlijnen voor het instellen van apps om te werken met Azure Active Directory. Samengevat:


- Als u **cloudgebaseerde apps**gebruikt, zoals apps die zijn toegevoegd aan de Azure AD-appgalerij, hoeven de meeste geen verdere voorbereiding nodig te hebben om met Microsoft Managed Desktop te werken. Win32-apps die geen Web Account Manager (WAM) gebruiken, kunnen gebruikers echter nog steeds om verificatie vragen.

- Voor apps die **on-premises**worden gehost, moet u deze apps toevoegen aan de lijst met vertrouwde sites in uw browsers. Hierdoor kan Windows-verificatie naadloos werken, zonder dat gebruikers worden gevraagd om referenties. Raadpleeg hiervoor Vertrouwde [sites](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref#trusted-sites) in de [referentie Configureerbare instellingen.](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref)

- Als u Active Directory Federated Services gebruikt, controleert u of SSO is ingeschakeld met de stappen in [Controleren en beheren van één aanmelding met AD FS](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100)). 

- Voor apps die **on-premises**zijn en oudere protocollen gebruiken, is geen extra installatie vereist, zolang de apparaten toegang hebben tot een on-premises domeincontroller om zich te verifiëren. Als u deze toepassingen echter veilige toegang wilt bieden, moet u Azure AD-toepassingsproxy implementeren. Zie [Externe toegang tot on-premises toepassingen via de toepassingsproxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)van Azure Active Directory voor meer informatie.

- Apps die **on-premises** werken en afhankelijk zijn van machineverificatie worden niet ondersteund, dus u moet overwegen deze te vervangen door nieuwere versies.

### <a name="network-shares-that-use-authentication"></a>Netwerkshares die verificatie gebruiken

Er is geen extra installatie vereist voor gebruikers om toegang te krijgen tot netwerkshares, zolang de apparaten toegang hebben tot een on-premises domeincontroller met behulp van een UNC-pad.

### <a name="printers"></a>Printers

Microsoft Managed Desktop-apparaten kunnen geen verbinding maken met printers die zijn gepubliceerd op uw on-premises Active Directory, tenzij u [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)hebt geconfigureerd.

Hoewel printers niet automatisch kunnen worden gedetecteerd in een cloudomgeving, kunnen uw gebruikers on-premises printers gebruiken met behulp van het printerpad of het printerwachtrijpad, zolang de apparaten toegang hebben tot een on-premises domeincontroller.

<!--add fuller material on printers when available-->
