---
title: Uw globale beheerdersaccounts van Microsoft 365 beveiligen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/08/2020
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
f1.keywords:
- NOCSH
ms.assetid: 6b4ded77-ac8d-42ed-8606-c014fd947560
description: Dit artikel bevat informatie over het beveiligen van globale beheerderstoegang tot uw abonnement op Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e51e75e811eefc001155bb2923b75a9dac9c0a90
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430008"
---
# <a name="protect-your-microsoft-365-global-administrator-accounts"></a>Uw globale beheerdersaccounts van Microsoft 365 beveiligen

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Schending van de beveiliging van een Microsoft 365-abonnement, waaronder het verzamelen van gegevens en het aanbrengen van phishing-aanvallen, worden meestal door de referenties van een globale-beheerdersaccount van Microsoft 365 afgeschreven. Beveiliging in de Cloud is een relatie tussen u en Microsoft:
  
- Microsoft-cloudservices zijn samengesteld op basis van een vertrouwensrelatie en beveiliging. Microsoft biedt u de beveiliging van uw gegevens en toepassingen en mogelijkheden om uw gegevens en toepassingen te beschermen.
    
- U bent de eigenaar van uw gegevens en identiteiten, en u bent verantwoordelijk voor de bescherming hiervan, de beveiliging van uw on-premises resources en de beveiliging van Cloud onderdelen die u beheert.
    
Microsoft biedt mogelijkheden om uw organisatie te beschermen, maar ze zijn alleen van kracht als u ze gebruikt. Als u ze niet gebruikt, is het mogelijk kwetsbaar voor aanvallen. Ter bescherming van uw globale beheerdersaccounts is Microsoft er om u te helpen met gedetailleerde instructies voor het volgende:
  
1. Maak toegewezen globale beheerdersaccounts van Microsoft 365 en gebruik ze alleen indien nodig.
    
2. Configureer meervoudige verificatie voor uw toegewezen globale beheerdersaccounts van Microsoft 365 en gebruik de krachtigste vorm van secundaire verificatie.
    
> [!Note]
> Hoewel dit artikel gericht is op algemene beheerdersaccounts, moet u overwegen om te bepalen of extra accounts met uitgebreide machtigingen voor toegang tot de gegevens in uw abonnement, zoals eDiscovery-beheerder of beveiligings-of compliance beheerdersaccounts, op dezelfde manier moeten worden beveiligd. <br > U kunt een globaal beheerdersaccount maken zonder licenties toe te voegen.
  
## <a name="step-1-create-dedicated-microsoft-365-global-administrator-accounts-and-use-them-only-when-necessary"></a>Stap 1. Speciale beheerdersaccounts van Microsoft 365 maken en deze alleen gebruiken wanneer dat nodig is

Er zijn relatief weinig beheertaken, zoals het toewijzen van rollen aan gebruikersaccounts waarvoor globale beheerdersbevoegdheden zijn vereist. Voer de volgende stappen uit in plaats van alledaagse gebruikersaccounts te gebruiken aan de globale beheerdersrol.
  
1. Bepaal de set gebruikersaccounts waaraan de globale beheerdersrol is toegewezen. U kunt dit doen met de volgende Azure Active Directory (Azure AD) PowerShell-opdracht voor grafieken:
  
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

2. Meld u aan bij uw Microsoft 365-abonnement met een gebruikersaccount waaraan de globale beheerdersrol is toegewezen.
    
3. Maximaal vier gespecialiseerde gebruikersaccounts voor de globale beheerder maken. **Gebruik sterke wachtwoorden van ten minste 12 tekens.** Zie [Maak een sterk wachtwoord](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) voor meer informatie. Sla de wachtwoorden voor de nieuwe accounts op een veilige locatie op. 
    
4. Wijs de globale beheerdersrol toe aan elk van de nieuwe toegewezen globale beheerdersaccounts.
    
5. Meld u af bij Microsoft 365.
    
6. Meld u aan met een van de nieuwe toegewezen globale beheerders gebruikersaccounts.
    
7. Voor elk bestaand gebruikersaccount waaraan de globale beheerdersrol uit stap 1 is toegewezen, doet u het volgende:
    
  - Verwijder de globale beheerdersrol.
    
  - Beheerdersrollen toewijzen aan het account die geschikt zijn voor de taakfunctie en de verantwoordelijkheid van deze gebruiker. Zie [info over beheerdersrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)voor meer informatie over diverse beheerdersrollen in microsoft 365.
    
8. Meld u af bij Microsoft 365.
    
Het resultaat moet zijn:
  
- De enige gebruikersaccounts in uw abonnement met de rol van globale beheerder zijn de nieuwe set toegewezen globale beheerdersaccounts. Controleer dit met de volgende PowerShell-opdracht:
    
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

- Voor alle andere alledaagse gebruikersaccounts waarmee uw abonnement wordt beheerd, zijn beheerdersrollen toegewezen die zijn gekoppeld aan hun functie verantwoordelijkheden.
    
Vanaf dit moment meldt u zich alleen aan met de toegewezen globale beheerdersaccounts voor taken waarvoor globale beheerdersmachtigingen zijn vereist. Alle overige Microsoft 365-beheertaken moeten worden uitgevoerd door andere beheerdersrollen aan gebruikersaccounts toe te wijzen.
  
> [!NOTE]
> Hiervoor moeten extra stappen worden ondermeldd voor uw dagelijkse gebruikersaccount en u meldt u aan met een toegewezen account van de globale beheerder. Dit hoeft niet af en toe voor de algemene beheerder activiteiten. Als u een abonnement op Microsoft 365 moet terugzetten na een overtreding van een hoofd beheerdersaccount, hebt u veel meer stappen nodig.
  
## <a name="step-2-configure-multi-factor-authentication-for-your-dedicated-microsoft-365-global-administrator-accounts-and-use-the-strongest-form-of-additional-verification"></a>Stap 2. Configureer meervoudige verificatie voor uw toegewezen globale beheerdersaccounts van Microsoft 365 en gebruik de krachtigste vorm van extra verificatie

Voor multi-factor Authentication (MFA) is extra informatie vereist naast de accountnaam en het wachtwoord. Microsoft 365 ondersteunt deze aanvullende verificatiemethoden:
  
- De Microsoft Authenticator-app

- Een telefonische oproep
    
- Een willekeurig gegenereerde verificatiecode die via een SMS-bericht wordt verzonden
    
- Een smartcard (al dan niet virtueel)
    
- Een biometrisch apparaat
    
>[!Note]
>Voor organisaties die moeten voldoen aan de nationale standaarden en technologieën (NIST)-normen, wordt het gebruik van een telefonische oproep of op tekst gebaseerde extra verificatiemethoden beperkt. Klik [hier](https://pages.nist.gov/800-63-FAQ/#q-b01) voor meer informatie.
>

Als u een klein bedrijf bent waarbij gebruikersaccounts alleen in de cloud worden opgeslagen (het identiteits model voor de Cloud only), gebruikt u deze stappen voor het configureren van MFA via een telefoongesprek of een verificatiecode voor SMS-berichten die naar een smartphone is verzonden:
  
1. [MFA instellen](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).
    
2. [MFA instellen voor Microsoft 365](https://support.office.com/article/Set-up-2-step-verification-for-Office-365-ace1d096-61e5-449b-a875-58eb3d74de14) om elk toegewezen globale beheerdersaccount te configureren voor een telefoongesprek of SMS-bericht als verificatiemethode. 
    
Als u een grotere organisatie bent en gebruikmaakt van een hybride Microsoft 365-identiteits model, hebt u meer opties voor verificatie. Voer de volgende stappen uit als u de beveiligingsinfrastructuur al hebt voor een sterkere secondaire verificatiemethode:
  
1. [MFA instellen](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).
    
2. [MFA instellen voor uw nieuwe globale beheerdersaccounts](https://support.office.com/article/set-up-your-microsoft-365-sign-in-for-multi-factor-authentication-ace1d096-61e5-449b-a875-58eb3d74de14) om elk toegewezen globale beheerdersaccount te configureren voor de juiste verificatiemethode. 
    
Als de beveiligingsinfrastructuur voor de gewenste sterkere verificatiemethode niet is ingesteld en functioneert voor Microsoft 365 MFA, raden we u ten zeerste aan dat u toegewezen globale beheerdersaccounts met MFA configureert met behulp van de Microsoft Authenticator-app, een telefoongesprek of een verificatiecode voor SMS-berichten die naar een smartphone worden verzonden voor uw globale-beheerdersaccounts, als tussentijdse beveiligingsmaatregel. Laat uw eigen accounts voor globale beheerders niet verlaten zonder de extra beveiliging van MFA.
  
Zie [MFA voor Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365)voor meer informatie.
  
Als u verbinding wilt maken met Microsoft 365-Services met MFA en PowerShell, raadpleegt u de volgende artikelen:

- [PowerShell voor Microsoft 365 voor gebruikersaccounts, groepen en licenties](connect-to-microsoft-365-powershell.md)
- [Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
- [Exchange Online](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa)
- [SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online#to-connect-with-multifactor-authentication-mfa)
- [Skype voor Bedrijven Online](manage-skype-for-business-online-with-microsoft-365-powershell.md#connect-using-an-admin-account-with-multi-factor-authentication)

## <a name="additional-protections-for-enterprise-organizations"></a>Extra bescherming voor Enterprise-organisaties

Na stap 1 en 2 kunt u deze extra methoden gebruiken om ervoor te zorgen dat uw account voor globale beheerders en de door u gebruikte configuratie zo veilig mogelijk zijn.
  
### <a name="privileged-access-workstation"></a>Toegankelijk werkstation met bevoegdheden

Gebruik een geprivilegieerde Access-werkstation (PAW) om ervoor te zorgen dat de uitvoering van taken met hoge bevoegdheden zo veilig mogelijk is. Een PAW is een specifieke computer die alleen wordt gebruikt voor gevoelige configuratietaken, zoals Microsoft 365-configuratie waarvoor een globale beheerdersaccount is vereist. Omdat deze computer niet dagelijks wordt gebruikt voor het internet browsen of e-mail, is het beter beveiligd tegen internetaanvallen en bedreigingen.
  
Zie voor instructies over het instellen van een PAW [https://aka.ms/cyberpaw](https://aka.ms/cyberpaw) .
  
### <a name="azure-ad-privileged-identity-management"></a>Azure AD Privileged Identity Management

In plaats van dat u uw globale beheerdersaccounts permanent aan de rol van globale beheerder hebt toegewezen, kunt u Azure AD geprivilegieerde identiteitsbeheer (PIM) gebruiken om op aanvraag een eenmalige toewijzing van de globale beheerdersrol in te schakelen wanneer dat nodig is.
  
In plaats van uw globale-beheerdersaccounts een permanente beheerder te worden, krijgen ze in aanmerking voor beheerders. De globale beheerdersrol is inactief totdat iemand deze nodig heeft. U voert vervolgens een activeringsprocedure uit om de rol van globale beheerder toe te voegen aan het globale beheerdersaccount voor een vooraf vastgesteld tijdsperiode. Als de tijd is verstreken, verwijdert PIM de globale beheerdersrol uit het globale beheerdersaccount.
  
Met behulp van PIM en hierdoor wordt de hoeveelheid tijd die uw globale beheerdersaccounts kwetsbaarder zijn voor aanvallen en het gebruik van kwaadwillende gebruikers sterk beperkt.

PIM is beschikbaar via Azure AD Premium P2, dat deel uitmaakt van Microsoft 365 Enterprise E5 of Enterprise Mobility + Security (EMS) E5, of u kunt afzonderlijke licenties kopen voor uw globale beheerdersaccounts.
  
Zie voor meer informatie het artikel over [identiteitsbeheer via Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).
  
### <a name="security-information-and-event-management-siem-software-for-microsoft-365-logging"></a>Beveiligingsinformatie en gebeurtenissen in het SIEM-programma voor Microsoft 365

SIEM-software die wordt uitgevoerd op een server voert een realtime analyse uit van beveiligingswaarschuwingen en gebeurtenissen die zijn gemaakt door toepassingen en netwerkhardware. Als u wilt toestaan dat uw SIEM-server beveiligingswaarschuwingen en gebeurtenissen in Microsoft 365 kunt opnemen in de analyse-en rapportagefuncties, integreert u Azure AD in de SEIM. Zie [Inleiding in de integratie van Azure-logboek](https://docs.microsoft.com/azure/security/security-azure-log-integration-overview).

## <a name="next-step"></a>Volgende stap

Als u de identiteit voor uw Microsoft 365-abonnement instelt, raadpleegt u:

- [Alleen voor Cloud](cloud-only-identities.md) identiteiten als u alleen Cloud-identiteit gebruikt
- [Voorbereiding voor adreslijstsynchronisatie](prepare-for-directory-synchronization.md) wanneer u een hybride identiteit gebruikt

  
## <a name="see-also"></a>Zie ook

[Beveiligingsschema van Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/security-roadmap).
