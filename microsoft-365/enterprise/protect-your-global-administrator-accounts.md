---
title: Uw globale beheerdersaccounts in Microsoft 365 beveiligen
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
description: Dit artikel bevat informatie over het beschermen van globale beheerderstoegang tot uw Microsoft 365-abonnement.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1f84ca33a620c3ea3c24f46eb29c1a39c28840e7
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289637"
---
# <a name="protect-your-microsoft-365-global-administrator-accounts"></a>Uw globale beheerdersaccounts in Microsoft 365 beveiligen

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Beveiligingsinbreuken van een Microsoft 365-abonnement, waaronder phishingaanvallen en het verzamelen van gegevens, worden meestal uitgevoerd door de referenties van een globale beheerdersaccount van Microsoft 365 te onderzenden. Beveiliging in de cloud is een partnerschap tussen u en Microsoft:
  
- Microsoft-cloudservices zijn gebouwd op basis van vertrouwen en beveiliging. Microsoft biedt u besturingselementen voor beveiliging en mogelijkheden om u te helpen uw gegevens en toepassingen te beschermen.
    
- U bent de eigenaar van uw gegevens en identiteiten en bent verantwoordelijk voor de beveiliging ervan, de beveiliging van uw on-premises resources en de beveiliging van cloudonderdelen die u controleert.
    
Microsoft biedt mogelijkheden om uw organisatie te helpen beschermen, maar deze zijn alleen effectief als u ze gebruikt. Als u ze niet gebruikt, bent u mogelijk kwetsbaar voor een aanval. Om uw globale beheerdersaccounts te beschermen, is Microsoft er om u te helpen met gedetailleerde instructies voor:
  
1. Maak toegewezen globale beheerdersaccounts in Microsoft 365 en gebruik ze alleen wanneer dat nodig is.
    
2. Configureer meervoudige verificatie voor uw toegewezen globale beheerdersaccounts in Microsoft 365 en gebruik de strongste vorm van secundaire verificatie.
    
> [!Note]
> Hoewel dit artikel is gericht op globale beheerdersaccounts, moet u overwegen of extra accounts met uitgebreide machtigingen voor toegang tot de gegevens in uw abonnement, zoals eDiscovery-beheerdersaccounts of beveiligings- of nalevingsbeheerdersaccounts, op dezelfde manier moeten worden beveiligd. <br > Een globale beheerdersaccount kan worden gemaakt zonder licenties toe te voegen.
  
## <a name="step-1-create-dedicated-microsoft-365-global-administrator-accounts-and-use-them-only-when-necessary"></a>Stap 1. Toegewezen globale beheerdersaccounts in Microsoft 365 maken en alleen gebruiken indien nodig

Er zijn relatief weinig beheertaken, zoals het toewijzen van rollen aan gebruikersaccounts, waarvoor globale beheerdersbevoegdheden zijn vereist. Ga daarom als volgende stappen te werk in plaats van gebruik te maken van gewone gebruikersaccounts aan welke de globale beheerdersrol is toegewezen:
  
1. Bepaal de set gebruikersaccounts aan wie de globale beheerdersrol is toegewezen. U kunt dit doen in het Microsoft 365-beheercentrum of met de volgende Azure Active (Azure AD) Directory PowerShell for Graph-opdracht:
  
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Global Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

2. Meld u aan bij uw Microsoft 365-abonnement met een gebruikersaccount aan welke de globale beheerdersrol is toegewezen.
    
3. Maak maximaal vier toegewezen globale beheerdersaccounts. **Gebruik sterke wachtwoorden van minstens 12 tekens.** Zie [Een sterk wachtwoord maken](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) voor meer informatie. Bewaar de wachtwoorden voor de nieuwe accounts op een veilige locatie. 
    
4. Wijs de globale beheerdersrol toe aan elk nieuw toegewezen globale beheerdersaccount.
    
5. Meld u af bij Microsoft 365.
    
6. Meld u aan met een van de nieuwe toegewezen globale beheerdersaccounts.
    
7. Voor elk bestaand gebruikersaccount aan welke de globale beheerdersrol uit stap 1 is toegewezen:
    
  - Verwijder de globale beheerdersrol.
    
  - Wijs beheerdersrollen toe aan het account die geschikt zijn voor de functie en verantwoordelijkheid voor de functie van die gebruiker. Zie Over beheerdersrollen voor meer informatie over [](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)verschillende beheerdersrollen in Microsoft 365.
    
8. Meld u af bij Microsoft 365.
    
De resultaten moeten zijn:
  
- De enige gebruikersaccounts in uw abonnement met de globale beheerdersrol zijn de nieuwe toegewezen globale beheerdersaccounts. Controleer dit met de volgende PowerShell-opdracht:
    
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

- Aan alle andere gewone gebruikersaccounts die uw abonnement beheren, zijn beheerdersrollen toegewezen die zijn gekoppeld aan hun taakverantwoordelijkheden.
    
Vanaf dit moment kunt u zich alleen met de toegewezen globale beheerdersaccounts aanmelden voor taken waarvoor globale beheerdersbevoegdheden zijn vereist. Alle andere Microsoft 365-beheerfuncties moeten worden uitgevoerd door andere beheerdersrollen toe te wijzen aan gebruikersaccounts.
  
> [!NOTE]
> Hiervoor zijn wel extra stappen nodig om u af te melden bij uw gewone gebruikersaccount en u aan te melden met een toegewezen globale beheerdersaccount. Maar dit hoeft u slechts af en toe te doen bij bewerkingen die globale beheerders uitvoeren. Houd er rekening mee dat voor het herstellen van uw Microsoft 365-abonnement na een schending van een globale beheerdersaccount veel meer stappen zijn vereist.
  
## <a name="step-2-configure-multi-factor-authentication-for-your-dedicated-microsoft-365-global-administrator-accounts"></a>Stap 2. Meervoudige verificatie configureren voor uw toegewezen globale beheerdersaccounts in Microsoft 365

Voor meervoudige verificatie (Multi-Factor Authentication, MFA) zijn aanvullende gegevens vereist, naast de accountnaam en het wachtwoord. Microsoft 365 ondersteunt deze aanvullende verificatiemethoden:
  
- De Microsoft Authenticator-app

- Een telefonische oproep
    
- Een willekeurig gegenereerde verificatiecode verzonden via een sms-bericht
    
- Een smartcard (al dan niet virtueel)
    
- Een biometrisch apparaat
    
>[!Note]
>Voor organisaties die moeten voldoen aan de NIST-standaarden (National Institute of Standards and Technology), wordt het gebruik van aanvullende verificatiemethoden via telefoon of sms beperkt. Klik [hier](https://pages.nist.gov/800-63-FAQ/#q-b01) voor meer informatie.
>

Als u een klein bedrijf bent dat gebruik maakt van gebruikersaccounts die alleen zijn opgeslagen in de cloud (het identiteitsmodel voor alleen de cloud), stelt u MFA in om [MFA](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) te configureren via een telefonische oproep of een verificatiecode voor sms-berichten die voor elk toegewezen globale beheerdersaccount naar een smartphone wordt verzonden.
    
Als u een grotere organisatie bent die gebruik maakt van een hybride identiteitsmodel voor Microsoft 365, hebt u meer verificatieopties. Als u de beveiligingsinfrastructuur al hebt ingesteld voor een sterkere secundaire verificatiemethode, stelt u [MFA](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication) in en configureert u elk toegewezen globale beheerdersaccount voor de juiste verificatiemethode.
  
Als de beveiligingsinfrastructuur voor de gewenste krachtigere verificatiemethode niet ingesteld en functionerend is voor Microsoft 365 MFA, raden we u ten zeerste aan om globale beheerdersaccounts met MFA te configureren met behulp van de Microsoft Authenticator-app, een telefoongesprek of een verificatiecode voor sms-berichten die als tussentijdse beveiligingsmaatregel naar een smartphone is verzonden voor uw globale beheerdersaccounts. Verlaat uw toegewezen globale beheerdersaccounts niet zonder de extra beveiliging die door MFA wordt geboden.
  
Zie MFA voor [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365)voor meer informatie.
  
Zie de volgende artikelen als u verbinding wilt maken met Microsoft 365-services met MFA en PowerShell:

- [PowerShell voor Microsoft 365 voor gebruikersaccounts, groepen en licenties](connect-to-microsoft-365-powershell.md)
- [Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
- [Exchange Online](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa)
- [SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online#to-connect-with-multifactor-authentication-mfa)
- [Skype voor Bedrijven Online](manage-skype-for-business-online-with-microsoft-365-powershell.md#connect-using-an-admin-account-with-multi-factor-authentication)

## <a name="additional-protections-for-enterprise-organizations"></a>Aanvullende beveiliging voor ondernemingen

Gebruik deze aanvullende methoden om ervoor te zorgen dat uw globale beheerdersaccount en de configuratie die u op deze manier gebruikt, zo veilig mogelijk zijn.
  
### <a name="privileged-access-workstation"></a>Bevoorrechte toegangswerkstation

Gebruik een bevoorrecht werkstation VOOR TOEGANG (PRIVILEGED) om ervoor te zorgen dat de uitvoering van taken met veel bevoegdheden zo veilig mogelijk is. Een WELT.A. is een speciale computer die alleen wordt gebruikt voor gevoelige configuratietaken, zoals een Microsoft 365-configuratie die een globale beheerdersaccount vereist. Omdat deze computer niet dagelijks wordt gebruikt voor browsen of e-mail op internet, is de computer beter beveiligd tegen internetaanvallen en -bedreigingen.
  
Zie voor instructies over het instellen van een [https://aka.ms/cyberpaw](https://aka.ms/cyberpaw) WAS.IN.

Als u Azure PIM wilt inschakelen voor uw Azure Active Directory tenant -en beheerdersaccounts, raadpleegt u de [stappen voor het configureren van PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).

U kunt een uitgebreide roadmap ontwikkelen om bevoegde toegang te beveiligen tegen cyberaanvallers, zie [Bevoegde toegang voor hybride en cloudimplementaties in Azure Active Directory beveiligen](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

### <a name="azure-ad-privileged-identity-management"></a>Azure AD Privileged Identity Management

In plaats van dat de globale beheerdersaccounts permanent worden toegewezen, kunt u Azure AD Privileged Identity Management (PIM) gebruiken om op aanvraag just-in-time de globale beheerdersrol toe te staan wanneer deze nodig is.
  
Uw globale beheerdersaccounts worden permanente beheerders en beheerders die hiervoor in aanmerking komen. De globale beheerdersrol is inactief totdat iemand deze nodig heeft. Vervolgens voltooit u een activeringsproces om de globale beheerdersrol voor een vooraf bepaalde tijd toe te voegen aan het globale beheerdersaccount. Als de tijd is verstreken, verwijdert PIM de globale beheerdersrol uit het globale beheerdersaccount.
  
Door PIM te gebruiken en dit proces te gebruiken, wordt de tijd die uw globale beheerdersaccounts kwetsbaar zijn voor aanvallen en gebruik door kwaadwillende gebruikers aanzienlijk verminderd.

PIM is beschikbaar met Azure Active Directory Premium P2, dat inbegrepen is bij Microsoft 365 E5. U kunt ook afzonderlijke Azure Active Directory Premium P2-licenties aanschaffen voor uw beheerdersaccounts.
  
Zie Azure [AD Privileged Identity Management voor meer informatie.](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)
  

### <a name="privileged-access-management"></a>Privileged Access Management

Geprivilegieerd toegangsbeheer wordt ingeschakeld door beleid te configureren dat just-in-time-toegang specificeert voor taakactiviteiten in uw tenant. Deze functie kan helpen uw organisatie te beschermen tegen inbreuken die mogelijk bestaande geprivilegieerde beheerdersaccounts gebruiken met permanente toegang tot gevoelige gegevens of toegang tot belangrijker configuratie-instellingen. U kunt bijvoorbeeld geprivilegieerd toegangsbeheerbeleid configureren dat expliciete goedkeuring vereist voor toegang tot en het wijzigen van postvakinstellingen van de organisatie in uw tenant.

In deze stap schakelt u geprivilegieerd toegangsbeheer in uw tenant in en configureert u geprivilegieerd toegangsbeleid dat aanvullende bescherming biedt voor taaktoegang tot gegevens en configuratie-instellingen voor uw organisatie. Er zijn drie basisstappen om aan de slag te gaan met geprivilegieerde toegang in uw organisatie:

- Een groep met fiatteurs maken
- Geprivilegieerde toegang inschakelen
- Goedkeuringsbeleid maken

Met bevoorrechte toegangsbeheer kan uw organisatie zonder machtigingen werken en een verdediging bieden tegen beveiligingslekken die ontstaan vanwege dergelijke staande administratieve toegang. Geprivilegieerde toegang vereist goedkeuring voor het uitvoeren van taken met een bijbehorend goedkeuringsbeleid. Gebruikers die taken moeten uitvoeren die zijn opgenomen in het goedkeuringsbeleid, moeten goedkeuring aanvragen en krijgen.

Zie Bevoorrechte toegangsbeheer configureren om bevoorrechte [toegangsbeheer in te stellen.](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)

Zie Privileged [access management (Bevoorrechte toegangsbeheer) voor meer informatie.](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)

### <a name="security-information-and-event-management-siem-software-for-microsoft-365-logging"></a>SIEM-software (Security Information and Event Management) voor Microsoft 365-logboekregistratie

SIEM-software die op een server wordt uitgevoerd, voert een realtime-analyse uit van beveiligingswaarschuwingen en -gebeurtenissen die zijn gemaakt door toepassingen en netwerkhardware. Als u wilt dat uw SIEM-server beveiligingswaarschuwingen en -gebeurtenissen van Microsoft 365 kan opnemen in de analyse- en rapportagefuncties, integreert u Azure AD in uw SEIM. Zie [Inleiding tot de integratie van Azure Log.](https://docs.microsoft.com/azure/security/security-azure-log-integration-overview)

## <a name="next-step"></a>Volgende stap

Als u identiteit instelt voor uw Microsoft 365-abonnement, gaat u naar:

- [Alleen cloudidentiteiten](cloud-only-identities.md) als u identiteiten in de cloud gebruikt
- [Voorbereiden op adreslijstsynchronisatie](prepare-for-directory-synchronization.md) als u hybride identiteit gebruikt

  
## <a name="see-also"></a>Zie ook

[Roadmap voor microsoft 365-beveiliging](https://docs.microsoft.com/office365/securitycompliance/security-roadmap)
