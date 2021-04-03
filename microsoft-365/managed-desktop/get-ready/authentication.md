---
title: Toegang voorbereiden tot on-premises bronnen voor Microsoft Managed Desktop
description: Belangrijke stappen om ervoor te zorgen dat een Azure AD kan communiceren met on-premises AD voor verificatie
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 6df23e0d7e3ea0ecd7ebacd96f00cb47b9e0aa84
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574593"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Toegang voorbereiden tot on-premises bronnen voor Microsoft Managed Desktop

In Microsoft Managed Desktop worden apparaten automatisch verbonden met Azure Active Directory (Azure AD). Als u daarom een on-premises Active Directory gebruikt, moet u enkele dingen controleren om ervoor te zorgen dat apparaten die zijn verbonden met Azure AD, kunnen communiceren met uw on-premises Active Directory. 

> [!NOTE]  
> *Hybride* Azure AD join wordt niet ondersteund door Microsoft Managed Desktop.

Met Azure Active Directory kunnen uw gebruikers profiteren van eenmalige Sign-On (SSO), wat betekent dat ze meestal niet elke keer referenties moeten verstrekken wanneer ze resources gebruiken.

Zie How to: Plan your Azure AD join implementation (Uw [Azure AD join-implementatie plannen)](/azure/active-directory/devices/azureadjoin-plan)voor informatie over het deelnemen aan Azure Active Directory. Zie How [SSO to on-premises resources works on-premises resources on-premises resources on-premises devices (SSO to on-premises resources works on-premises resources works on-premises](/azure/active-directory/devices/azuread-join-sso#how-it-works)Sign-On (SSO) on-premises devices (Single Sign-On (SSO) on devices joined to Azure AD.


In dit artikel worden de dingen beschreven die u moet controleren om ervoor te zorgen dat apps en andere bronnen die afhankelijk zijn van lokale Active Directory-connectiviteit, soepel werken met Microsoft Managed Desktop.


## <a name="single-sign-on-for-on-premises-resources"></a>Eén Sign-On voor on-premises resources

Eenmalige Sign-On (SSO) met behulp van UPN en wachtwoord is standaard ingeschakeld op Beheerde bureaubladapparaten van Microsoft. Maar uw gebruikers kunnen ook Windows Hello voor Bedrijven gebruiken, wat extra installatiestappen vereist. 

### <a name="single-sign-on-by-using-upn-and-password"></a>Eén Sign-On met behulp van UPN en wachtwoord

In de meeste organisaties kunnen uw gebruikers SSO gebruiken om te verifiëren met UPN en wachtwoord op Microsoft Managed Desktop Devices. Als u er echter zeker van wilt zijn dat deze functie werkt, moet u de volgende dingen controleren:

- Controleer of Azure AD Connect is ingesteld en gebruik een on-premises Active Directory-server met Windows Server 2008 R2 of hoger.
- Controleer of Azure AD Connect een ondersteunde versie gebruikt en is ingesteld op het synchroniseren van deze drie kenmerken met Azure AD: 
    - DNS-domeinnaam van de on-premises Active Directory (waar de gebruikers zich bevinden)
    - NetBIOS van uw on-premises Active Directory (waar de gebruikers zich bevinden)
    - SAM-accountnaam van de gebruiker


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>Eén Sign-On met Windows Hello voor Bedrijven

Microsoft Managed Desktop-apparaten bieden uw gebruikers ook een snelle, wachtwoordloze ervaring door Windows Hello voor Bedrijven te gebruiken. Ga naar Azure AD-apparaten configureren voor [on-premises Single-Sign On-premises Single-Sign](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) Aan de slag met Windows Hello voor Bedrijven om de vereisten te controleren en volg vervolgens de stappen die daar zijn opgegeven om ervoor te zorgen dat Windows Hello voor Bedrijven werkt zonder dat uw gebruikers hun upn en wachtwoord moeten opgeven.


## <a name="apps-and-resources-that-use-authentication"></a>Apps en resources die verificatie gebruiken

Raadpleeg [Aandachtspunten voor toepassingen en](/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) resources in de Azure-inhoudsset voor volledige richtlijnen voor het instellen van apps voor gebruik met Azure Active Directory. Samengevat:


- Als u **cloud-apps** gebruikt , zoals apps die zijn toegevoegd aan de galerie met Azure AD-apps, is er voor de meeste geen verdere voorbereiding nodig om met Microsoft Managed Desktop te werken. Alle Win32-apps die geen WAM (Web Account Manager) gebruiken, kunnen gebruikers echter nog steeds vragen om verificatie.

- Voor apps die **on-premises worden gehost,** moet u deze apps toevoegen aan de lijst met vertrouwde sites in uw browsers. Met deze stap kan Windows-verificatie naadloos werken, zonder dat gebruikers om referenties worden gevraagd. Als u apps wilt toevoegen, [raadpleegt u Vertrouwde sites](../working-with-managed-desktop/config-setting-ref.md#trusted-sites) in de [verwijzing naar Configureerbare instellingen.](../working-with-managed-desktop/config-setting-ref.md)

- Als u Active Directory Federated Services gebruikt, controleert u of SSO is ingeschakeld met behulp van de stappen in Eén aanmelding verifiëren en beheren [met AD FS.](/previous-versions/azure/azure-services/jj151809(v=azure.100)) 

- Voor apps die **on-premises** zijn en oudere protocollen gebruiken, is geen extra installatie vereist, zolang de apparaten toegang hebben tot een on-premises domeincontroller om te verifiëren. Als u echter veilige toegang wilt bieden voor deze toepassingen, moet u Azure AD Application Proxy implementeren. Zie Externe toegang [tot on-premises](/azure/active-directory/manage-apps/application-proxy)toepassingen via de toepassingsproxy van Azure Active Directory voor meer informatie.

- Apps die **on-premises worden uitgevoerd en** afhankelijk zijn van computerverificatie, worden niet ondersteund, dus u moet overwegen deze te vervangen door nieuwere versies.

### <a name="network-shares-that-use-authentication"></a>Netwerkaandelen die verificatie gebruiken

Er is geen extra installatie vereist voor gebruikers die toegang hebben tot netwerkaandelen, zolang de apparaten toegang hebben tot een on-premises domeincontroller via een UNC-pad.

### <a name="printers"></a>Printers

Microsoft Managed Desktop-apparaten kunnen geen verbinding maken met printers die zijn gepubliceerd naar uw on-premises Active Directory, tenzij u Hybride cloud afdrukken [hebt geconfigureerd.](/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)

Hoewel printers niet automatisch kunnen worden gevonden in een alleen-cloudomgeving, kunnen uw gebruikers on-premises printers gebruiken via het printerpad of het printerwachtrijpad, zolang de apparaten toegang hebben tot een on-premises domeincontroller.

<!--add fuller material on printers when available-->
## <a name="steps-to-get-ready"></a>Stappen om u klaar te maken

1. Controleer [Vereisten voor Microsoft Managed Desktop](prerequisites.md).
2. Gebruik [gereedheidsbeoordelingshulpmiddelen.](readiness-assessment-tool.md)
3. [Vereisten voor gast-accounts](guest-accounts.md)
4. [Netwerkconfiguratie voor Microsoft Managed Desktop](network.md)
5. [Certificaten en netwerkprofielen voorbereiden voor Microsoft Managed Desktop](certs-wifi-lan.md)
6. [On-premises toegang tot resources voorbereiden voor Microsoft Managed Desktop](authentication.md) (dit artikel)
7. [Apps in Microsoft Managed Desktop](apps.md)
8. [Toegewezen stations voorbereiden voor Microsoft Managed Desktop](mapped-drives.md)
9. [Printbronnen voorbereiden voor Microsoft Managed Desktop](printing.md)
