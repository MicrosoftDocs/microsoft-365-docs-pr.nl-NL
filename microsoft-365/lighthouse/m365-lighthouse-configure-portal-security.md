---
title: Beveiliging Microsoft 365 Lighthouse portal configureren
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Voor MSP's (Managed Service Providers) die gebruikmaken van Microsoft 365 Lighthouse, leert u hoe u portalbeveiliging configureert.
ms.openlocfilehash: 1e67903fc6c3dfd4e1949ef8c3e80ad4af12ad5c
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395204"
---
# <a name="configure-microsoft-365-lighthouse-portal-security"></a>Beveiliging Microsoft 365 Lighthouse portal configureren

> [!NOTE]
> De functies die in dit artikel worden beschreven, zijn in Preview, kunnen worden gewijzigd en zijn alleen beschikbaar voor partners die aan de vereisten [voldoen.](m365-lighthouse-requirements.md) Als uw organisatie geen Microsoft 365 Lighthouse, zie [Registreren voor Microsoft 365 Lighthouse.](m365-lighthouse-sign-up.md)

Het beschermen van de toegang tot klantgegevens wanneer een MSP (Managed Service Provider) machtigingen voor toegang heeft gedelegeerd aan de tenants, is een prioriteit voor cyberbeveiliging. Microsoft 365 Lighthouse wordt geleverd met zowel vereiste als optionele mogelijkheden om u te helpen bij het configureren Microsoft 365 Lighthouse portalbeveiliging.

## <a name="set-up-multifactor-authentication-mfa"></a>Meervoudige verificatie (MFA) instellen

Zoals vermeld in het blogbericht [Uw Pa$$word maakt het niet uit:](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984)

> 'Uw wachtwoord maakt niet uit, maar MFA wel. Op basis van onze studies is uw account meer dan 99,9% minder waarschijnlijk in gevaar als u MFA gebruikt.

Wanneer gebruikers Microsoft 365 Lighthouse voor het eerst toegang krijgen tot de Microsoft 365, worden ze gevraagd MFA in te stellen als hun Microsoft 365-account deze nog niet heeft geconfigureerd. Gebruikers kunnen geen toegang krijgen tot Microsoft 365 Lighthouse totdat de vereiste MFA-installatiestap is voltooid. Zie Uw aanmelding Microsoft 365 meervoudige verificatie instellen voor meer informatie over [verificatiemethoden.](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)

## <a name="set-up-roles-to-manage-customer-tenants"></a>Rollen instellen voor het beheren van klantten tenants

Toegang tot klant tenantgegevens en -instellingen in Microsoft 365 Lighthouse is beperkt tot de rollen beheerder en helpdeskagent van het CSP-programma (Cloud Solutions Provider).

U kunt controleren welke gebruikers in de partnerten tenant de rol van beheerder en helpdeskagent hebben door de lidmaatschappen van de beveiligingsgroep te bekijken op de [pagina Azure AD - All Groups.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) Zie Rollen en machtigingen toewijzen aan gebruikers voor meer informatie over het toewijzen van CSP-programmarollen en andere [machtigingen aan gebruikers.](/partner-center/permissions-overview) Als U als MSP nog geen gedelegeerde [toegangsbevoegdheden](/partner-center/customers-revoke-admin-privileges)hebt voor klanttenaties, leert u hoe u deze kunt verkrijgen in het artikel Machtigingen verkrijgen voor het beheren van de service of het abonnement van een klant.

De volgende tabel bevat de verschillende Microsoft 365 Lighthouse pagina's en de machtigingen die nodig zijn om klantten tenantgegevens en -instellingen voor de rollen beheerder en helpdeskagent weer te geven en te bewerken.<br><br>

| Microsoft 365 Lighthouse pagina | Machtigingen voor beheerdersagenten | Helpdeskagentmachtigingen |
|--|--|--|
| Home | <ul><li>Alles weergeven</li></ul> | <ul><li>Alles weergeven</li></ul> |
| Tenants | <ul><li>Alles weergeven</li><li>Contactpersonen en website van klanten bijwerken</li><li>Implementatieplannen weergeven en toepassen</li></ul> | <ul><li>Alles weergeven</li><li>Contactpersonen en website van klanten bijwerken</li><li>Implementatieplannen weergeven</li></ul> |
| Gebruikers | <ul><li>Alles weergeven</li><li>Wachtwoord opnieuw instellen</li><li>Aanmelding blokkeren</li><li>MFA inschakelen</li></ul> | <ul><li>Alles weergeven</li><li>Wachtwoord opnieuw instellen</li><li>Aanmelding blokkeren</li></ul> |
| Apparaten | <ul><li>Alles weergeven</li></ul> | <ul><li>Alles weergeven</li></ul> |
| Bedreigingen | <ul><li>Alles weergeven</li><li>Snelle scan uitvoeren</li><li>Volledige scan uitvoeren</li><li>Apparaat opnieuw opstarten</li><li>Antivirusprogramma's bijwerken</li></ul> | <ul><li>Alles weergeven</li></ul> |
| Basislijnen | <ul><li>Alles weergeven</li></ul> | <ul><li>Alles weergeven</li></ul> |
| Servicestatus | <ul><li>Alles weergeven*</li></ul> | <ul><li>Alles weergeven*</li></ul> |

> [!NOTE]
> Op dit moment moeten gebruikers, als ze de acties willen uitvoeren die zijn gemarkeerd met * in de tabel, ook de Azure AD-rol hebben in de partnerten tenant met de volgende eigenschappenset: **microsoft.office365.serviceHealth/allEntities/allTasks.** Zie Ingebouwde Azure AD-rollen voor een lijst met Azure [AD-rollen.](/azure/active-directory/roles/permissions-reference)

Gezien de uitgebreide machtigingen die zijn gekoppeld aan de rol [](/azure/active-directory/develop/secure-least-privileged-access) beheerder, raden we u aan het principe van minst bevoorrechte toegang te houden bij het ontwerpen van een partnertenatiegebruiker als beheerder versus helpdeskagent. U kunt dit onder andere doen door de rol helpdeskagent toe te wijzen aan de vereiste partner tenantgebruikers. Hierdoor kunnen ze klantgegevens en -instellingen bekijken, maar geen algemene wijzigingen aanbrengen. Gebruik vervolgens indien nodig de just-in-time toegangsgoedkeuringsmogelijkheden van Azure AD Privileged Identity Management (PIM) om gebruikers een rol voor beheerdersagent met tijdbereik te geven.

## <a name="set-up-azure-ad-privileged-identity-management-pim"></a>Azure AD-Privileged Identity Management (PIM) instellen

MSP's kunnen het aantal personen dat toegang heeft tot beveiligde informatie of bronnen minimaliseren met behulp van Azure AD Privileged Identity Management (PIM). PIM verkleint de kans dat een kwaadwillende toegang krijgt tot resources of geautoriseerde gebruikers die per ongeluk een gevoelige resource beïnvloeden. MSP's kunnen gebruikers ook just-in-time geprivilegieerde toegang verlenen tot resources en controleren wat de aangewezen gebruikers doen met hun bevoorrechte toegang.

> [!NOTE]
> Voor het gebruik van Azure AD PIM is Azure AD Premium P2 licentie vereist in de partnerten tenant.

In de volgende stappen worden partnerten tenantgebruikers verheven tot time-scoped Admin Agent-rollen met Azure AD PIM:

1. Maak een groep die een rol kan toewijzen, zoals wordt beschreven in het artikel Een groep maken voor het toewijzen van rollen [in Azure Active Directory.](/azure/active-directory/roles/groups-create-eligible)

2. Ga naar [Azure AD: alle groepen](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) en voeg de nieuwe groep toe als lid van de groep Beheerdersagenten.

3. Bevoorrechte toegang tot de nieuwe groep instellen zoals beschreven in het artikel In aanmerking komende eigenaren en leden toewijzen [voor bevoorrechte toegangsgroepen.](/azure/active-directory/privileged-identity-management/groups-assign-member-owner)

Zie Wat is Privileged Identity Management? voor [meer Privileged Identity Management?](/azure/active-directory/privileged-identity-management/pim-configure)

## <a name="other-roles-and-permissions"></a>Andere rollen en machtigingen

In de volgende tabel worden partnerten tenantrollen en bijbehorende machtigingen vermeld.<br><br>

| Partner tenantrollen | Machtigingen binnen partnerten tenant |
|--|--|
| Globale beheerder van partner tenant | <ul><li>Meld u aan voor Microsoft 365 Lighthouse in de Microsoft 365-beheercentrum.</li><li>Accepteer partnercontractwijzigingen tijdens de eerste keer.</li><li>Klantten tenants weergeven op de pagina Tenants.\*</li><li>Een tenant activeren en inactiveren.\*</li><li>Klantcontacten en website bijwerken.\*</li><li>Tags maken, bijwerken en verwijderen.\*</li><li>Tags toewijzen en verwijderen uit een klant tenant.\*</li></ul> |
| Beheerder van partner tenant met ten minste één<br> Azure AD-rol toegewezen aan de volgende eigenschappenset:<br> **microsoft.office365.supportTickets/allEntities/allTasks**<br> (Zie Ingebouwde Azure AD-rollen voor een lijst met Azure [AD-rollen](/azure/active-directory/roles/permissions-reference).) | <ul><li>Maak Microsoft 365 Lighthouse serviceaanvragen.</li></ul> |

> [!NOTE]
> Als u op dit moment de acties wilt uitvoeren die zijn gemarkeerd met * in de tabel, moet de globale beheerder de rol beheerder nemen.

## <a name="related-content"></a>Verwante inhoud

[Overzicht van Microsoft 365 Lighthouse](m365-lighthouse-overview.md) (artikel)\
[Registreren voor Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md) (artikel)\
[Microsoft 365 Lighthouse veelgestelde vragen](m365-lighthouse-faq.yml) (artikel)