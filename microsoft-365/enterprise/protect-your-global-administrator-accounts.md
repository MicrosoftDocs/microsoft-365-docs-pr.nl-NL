---
title: Uw globale Microsoft 365 beheerdersaccounts beveiligen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- m365initiative-coredeploy
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
f1.keywords:
- NOCSH
ms.assetid: 6b4ded77-ac8d-42ed-8606-c014fd947560
description: In dit artikel vindt u informatie over het beveiligen van globale beheerderstoegang tot uw Microsoft 365 abonnement.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4ade5fd8070a656f976caa75c16ab92cadb7b64a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929046"
---
# <a name="protect-your-microsoft-365-global-administrator-accounts"></a>Uw globale Microsoft 365 beheerdersaccounts beveiligen

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Beveiligingsinbreuken van een Microsoft 365-abonnement, waaronder het verzamelen van gegevens en phishingaanvallen, worden meestal uitgevoerd door de referenties van een Microsoft 365 globale beheerdersaccount in gevaar te brengen. Beveiliging in de cloud is een partnerschap tussen u en Microsoft:
  
- Microsoft-cloudservices zijn gebaseerd op een fundament van vertrouwen en beveiliging. Microsoft biedt u beveiligingsbesturingselementen en -mogelijkheden om u te helpen uw gegevens en toepassingen te beveiligen.
    
- U bent eigenaar van uw gegevens en identiteiten en bent verantwoordelijk voor het beschermen van deze gegevens, de beveiliging van uw on-premises resources en de beveiliging van cloudonderdelen die u controleert.
    
Microsoft biedt mogelijkheden om uw organisatie te beschermen, maar ze zijn alleen effectief als u ze gebruikt. Als u deze niet gebruikt, kunt u mogelijk kwetsbaar zijn voor aanvallen. Om uw globale beheerdersaccounts te beschermen, is Microsoft hier om u te helpen met gedetailleerde instructies voor:
  
1. Maak speciale Microsoft 365 globale beheerdersaccounts en gebruik deze alleen wanneer dat nodig is.
    
2. Configureer meervoudige verificatie voor uw toegewezen Microsoft 365 globale beheerdersaccounts en gebruik de sterkste vorm van secundaire verificatie.
    
> [!Note]
> Hoewel dit artikel is gericht op globale beheerdersaccounts, moet u overwegen of extra accounts met uitgebreide machtigingen voor toegang tot de gegevens in uw abonnement, zoals eDiscovery-beheerders- of beveiligings- of compliancebeheerdersaccounts, op dezelfde manier moeten worden beveiligd. <br > Er kan een globaal beheerdersaccount worden gemaakt zonder licenties toe te voegen.
  
## <a name="step-1-create-dedicated-microsoft-365-global-administrator-accounts-and-use-them-only-when-necessary"></a>Stap 1. Speciale accounts Microsoft 365 globale beheerdersaccounts maken en deze alleen gebruiken wanneer dat nodig is

Er zijn relatief weinig beheertaken, zoals het toewijzen van rollen aan gebruikersaccounts, waarvoor globale beheerdersbevoegdheden zijn vereist. Ga daarom als volgende stappen te werk in plaats van dagelijkse gebruikersaccounts te gebruiken die aan de globale beheerdersrol zijn toegewezen:
  
1. Bepaal de set gebruikersaccounts aan wie de globale beheerdersrol is toegewezen. U kunt dit doen in het Microsoft 365 beheercentrum of met de volgende Azure Active (Azure AD) Directory PowerShell voor Graph opdracht:
  
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Global Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

2. Meld u aan bij Microsoft 365 abonnement met een gebruikersaccount dat is toegewezen aan de globale beheerdersrol.
    
3. Maak maximaal vier toegewezen globale beheerdersaccounts. **Gebruik sterke wachtwoorden van ten minste 12 tekens lang.** Zie [Een sterk wachtwoord maken](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) voor meer informatie. Sla de wachtwoorden voor de nieuwe accounts op een veilige locatie op. 
    
4. Wijs de rol van globale beheerder toe aan elk van de nieuwe toegewezen globale beheerdersaccounts.
    
5. Meld u af bij Microsoft 365.
    
6. Meld u aan met een van de nieuwe toegewezen globale beheerdersaccounts.
    
7. Voor elk bestaand gebruikersaccount dat de globale beheerdersrol van stap 1 heeft gekregen:
    
  - Verwijder de rol van globale beheerder.
    
  - Wijs beheerdersrollen toe aan het account dat geschikt is voor de functie en verantwoordelijkheid van die gebruiker. Zie Meer informatie over verschillende beheerdersrollen in Microsoft 365 meer [informatie over beheerdersrollen.](/office365/admin/add-users/about-admin-roles)
    
8. Meld u af bij Microsoft 365.
    
De resultaten moeten zijn:
  
- De enige gebruikersaccounts in uw abonnement die de rol van globale beheerder hebben, zijn de nieuwe set toegewezen globale beheerdersaccounts. Controleer dit met de volgende PowerShell-opdracht:
    
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

- Alle andere dagelijkse gebruikersaccounts die uw abonnement beheren, hebben beheerdersrollen toegewezen die zijn gekoppeld aan hun taakverantwoordelijkheden.
    
Vanaf dit moment kunt u zich alleen aanmelden met de toegewezen globale beheerdersaccounts voor taken waarvoor globale beheerdersbevoegdheden zijn vereist. Alle andere Microsoft 365 beheer moet worden uitgevoerd door andere beheerrollen toe te wijzen aan gebruikersaccounts.
  
> [!NOTE]
> Hiervoor zijn extra stappen nodig om u af te melden als uw dagelijkse gebruikersaccount en u aan te melden met een toegewezen globale beheerdersaccount. Maar dit hoeft alleen af en toe te gebeuren voor globale beheerdersbewerkingen. Houd er rekening mee dat het herstellen Microsoft 365 abonnement na een globale beheerdersaccountbreuk veel meer stappen vereist.
  
## <a name="step-2-configure-multi-factor-authentication-for-your-dedicated-microsoft-365-global-administrator-accounts"></a>Stap 2. Meervoudige verificatie configureren voor uw toegewezen Microsoft 365 globale beheerdersaccounts

Voor meervoudige verificatie (MFA) is meer informatie nodig dan de accountnaam en het wachtwoord. Microsoft 365 ondersteunt deze aanvullende verificatiemethoden:
  
- De Microsoft Authenticator-app

- Een telefonische oproep
    
- Een willekeurig gegenereerde verificatiecode die via een sms-bericht wordt verzonden
    
- Een smartcard (al dan niet virtueel)
    
- Een biometrisch apparaat
    
>[!Note]
>Voor organisaties die zich moeten houden aan de NIST-standaarden (National Institute of Standards and Technology) is het gebruik van aanvullende verificatiemethoden voor telefoongesprekken of sms-berichten beperkt. Klik [hier](https://pages.nist.gov/800-63-FAQ/#q-b01) voor de details.
>

Als u een klein bedrijf bent dat gebruik maakt van gebruikersaccounts die alleen zijn opgeslagen in de cloud (het cloudidentiteitsmodel), stelt u MFA in om [MFA](/office365/admin/security-and-compliance/set-up-multi-factor-authentication) te configureren met behulp van een telefoongesprek of een verificatiecode voor sms-berichten die naar een smartphone is verzonden voor elk toegewezen globale beheerdersaccount.
    
Als u een grotere organisatie bent die een hybride Microsoft 365 gebruikt, hebt u meer verificatieopties. Als u de beveiligingsinfrastructuur al hebt ingesteld voor een sterkere secundaire verificatiemethode, stelt u [MFA](../admin/security-and-compliance/set-up-multi-factor-authentication.md) in en configureert u elk toegewezen globale beheerdersaccount voor de juiste verificatiemethode.
  
Als de beveiligingsinfrastructuur voor de gewenste sterkere verificatiemethode niet beschikbaar is en niet werkt voor Microsoft 365 MFA, raden we u ten zeerste aan om speciale globale beheerdersaccounts te configureren met MFA met behulp van de Microsoft Authenticator-app, een telefoongesprek of een verificatiecode voor sms-berichten die naar een smartphone is verzonden voor uw globale beheerdersaccounts als tussentijdse beveiligingsmaatregel. Verlaat uw toegewezen globale beheerdersaccounts niet zonder de extra beveiliging die door MFA wordt geboden.
  
Zie [MFA](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)voor Microsoft 365.
  
Zie de volgende artikelen Microsoft 365 verbinding maken met Microsoft 365 services met MFA en PowerShell:

- [PowerShell voor Microsoft 365 gebruikersaccounts, groepen en licenties](connect-to-microsoft-365-powershell.md)
- [Microsoft Teams](/microsoftteams/teams-powershell-install)
- [Exchange Online](/powershell/exchange/mfa-connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa)
- [SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online#to-connect-with-multifactor-authentication-mfa)
- [Skype voor Bedrijven Online](manage-skype-for-business-online-with-microsoft-365-powershell.md#connect-using-an-admin-account-with-multi-factor-authentication)

## <a name="additional-protections-for-enterprise-organizations"></a>Aanvullende beveiligingen voor ondernemingsorganisaties

Gebruik deze aanvullende methoden om ervoor te zorgen dat uw globale beheerdersaccount en de configuratie die u erop gebruikt, zo veilig mogelijk zijn.
  
### <a name="privileged-access-workstation"></a>Bevoorrechte toegangswerkstation

Gebruik een bevoorrecht toegangswerkstation (PAW) om ervoor te zorgen dat de uitvoering van zeer bevoorrechte taken zo veilig mogelijk is. Een PAW is een speciale computer die alleen wordt gebruikt voor gevoelige configuratietaken, zoals Microsoft 365 configuratie die een globale beheerdersaccount vereist. Omdat deze computer niet dagelijks wordt gebruikt voor surfen op internet of e-mail, is deze beter beveiligd tegen internetaanvallen en bedreigingen.
  
Zie voor instructies over het instellen van een [https://aka.ms/cyberpaw](/security/compass/privileged-access-devices) PAW.

Als u Azure PIM wilt inschakelen voor uw Azure Active Directory tenant -en beheerdersaccounts, raadpleegt u de [stappen voor het configureren van PIM](/azure/active-directory/active-directory-privileged-identity-management-configure).

U kunt een uitgebreide roadmap ontwikkelen om bevoegde toegang te beveiligen tegen cyberaanvallers, zie [Bevoegde toegang voor hybride en cloudimplementaties in Azure Active Directory beveiligen](/azure/active-directory/admin-roles-best-practices).

### <a name="azure-ad-privileged-identity-management"></a>Azure AD Privileged Identity Management

In plaats van dat uw globale beheerdersaccounts permanent de rol van globale beheerder worden toegewezen, kunt u Azure AD Privileged Identity Management (PIM) gebruiken om op aanvraag, just-in-time toewijzing van de globale beheerdersrol in te stellen wanneer dit nodig is.
  
Uw globale beheerdersaccounts gaan van permanente beheerders naar in aanmerking komende beheerders. De globale beheerdersrol is inactief totdat iemand deze nodig heeft. Vervolgens voltooit u een activeringsproces om de rol van globale beheerder voor een vooraf bepaalde tijd toe te voegen aan het globale beheerdersaccount. Als de tijd is verstreken, verwijdert PIM de globale beheerdersrol uit het globale beheerdersaccount.
  
Met behulp van PIM en dit proces wordt de tijd die uw globale beheerdersaccounts kwetsbaar zijn voor aanvallen en gebruik door kwaadwillende gebruikers aanzienlijk verminderd.

PIM is beschikbaar met Azure Active Directory Premium P2, dat inbegrepen is bij Microsoft 365 E5. U kunt ook afzonderlijke Azure Active Directory Premium P2-licenties aanschaffen voor uw beheerdersaccounts.
  
Zie Azure AD-Privileged Identity Management voor [meer informatie.](/azure/active-directory/active-directory-privileged-identity-management-configure)
  

### <a name="privileged-access-management"></a>Privileged Access Management

Geprivilegieerd toegangsbeheer wordt ingeschakeld door beleid te configureren dat just-in-time-toegang specificeert voor taakactiviteiten in uw tenant. Deze functie kan helpen uw organisatie te beschermen tegen inbreuken die mogelijk bestaande geprivilegieerde beheerdersaccounts gebruiken met permanente toegang tot gevoelige gegevens of toegang tot belangrijker configuratie-instellingen. U kunt bijvoorbeeld geprivilegieerd toegangsbeheerbeleid configureren dat expliciete goedkeuring vereist voor toegang tot en het wijzigen van postvakinstellingen van de organisatie in uw tenant.

In deze stap schakelt u geprivilegieerd toegangsbeheer in uw tenant in en configureert u geprivilegieerd toegangsbeleid dat aanvullende bescherming biedt voor taaktoegang tot gegevens en configuratie-instellingen voor uw organisatie. Er zijn drie basisstappen om aan de slag te gaan met geprivilegieerde toegang in uw organisatie:

- Een groep met fiatteurs maken
- Geprivilegieerde toegang inschakelen
- Goedkeuringsbeleid maken

Met bevoorrecht toegangsbeheer kan uw organisatie werken met nul staande bevoegdheden en een beschermingslaag bieden tegen beveiligingsproblemen die ontstaan als gevolg van dergelijke permanente beheerderstoegang. Geprivilegieerde toegang vereist goedkeuring voor het uitvoeren van taken met een bijbehorend goedkeuringsbeleid. Gebruikers die taken moeten uitvoeren die zijn opgenomen in het goedkeuringsbeleid, moeten om toegangsgoedkeuring vragen en deze toestemming krijgen.

Zie Bevoorrecht toegangsbeheer configureren als u het beheer van [geprivilegieerde toegang wilt inschakelen.](/office365/securitycompliance/privileged-access-management-configuration)

Zie Privileged access management (Bevoorrecht [toegangsbeheer)](/office365/securitycompliance/privileged-access-management-overview)voor meer informatie.

### <a name="security-information-and-event-management-siem-software-for-microsoft-365-logging"></a>SIEM-software (Security Information and Event Management) voor Microsoft 365 logboekregistratie

SIEM-software die wordt uitgevoerd op een server, voert realtime analyse uit van beveiligingswaarschuwingen en gebeurtenissen die zijn gemaakt door toepassingen en netwerkhardware. Als u wilt toestaan dat uw SIEM-server beveiligingswaarschuwingen Microsoft 365 en gebeurtenissen in de analyse- en rapportagefuncties op te nemen, integreert u Azure AD in u SEIM. Zie [Inleiding tot Azure Log Integration.](/azure/security/security-azure-log-integration-overview)

## <a name="next-step"></a>Volgende stap

Als u een identiteit voor uw Microsoft 365 instelt, gaat u als volgende te werk:

- [Alleen-cloudidentiteiten](cloud-only-identities.md) als u cloud-only-identiteit gebruikt
- [Voorbereidingen treffen voor adreslijstsynchronisatie](prepare-for-directory-synchronization.md) als u hybride identiteit gebruikt

  
## <a name="see-also"></a>Zie ook

[Microsoft 365 routekaart voor beveiliging](/office365/securitycompliance/security-roadmap)